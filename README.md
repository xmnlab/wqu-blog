# wqu-blog

Quarto-based blog for WQU posts and notes.

## Setup

```bash
conda env create -f conda.yaml
conda activate wqu-blog
```

## Preview

```bash
quarto preview
```

In restricted workspaces where system temp/cache directories are read-only, use:

```bash
mkdir -p .quarto-tmp .quarto-cache
TMPDIR="$PWD/.quarto-tmp" XDG_CACHE_HOME="$PWD/.quarto-cache" quarto preview
```

## Render

```bash
quarto render
```

The rendered site is written to `_site/`.

In restricted workspaces, render with the same writable temp/cache settings:

```bash
mkdir -p .quarto-tmp .quarto-cache
TMPDIR="$PWD/.quarto-tmp" XDG_CACHE_HOME="$PWD/.quarto-cache" quarto render
```

## Makim Tasks

Build the site:

```bash
makim pages.build
```

Preview the site:

```bash
makim pages.preview
```

Generate one Typst PDF for each post:

```bash
makim pages.pdf
```

Each PDF is written next to its post and uses the post folder name:

```text
posts/my-post/my-post.pdf
```

## Add a Post

Create a new directory under `posts/` with an `index.qmd` file:

```text
posts/my-post/index.qmd
```

Use this starter front matter:

```yaml
---
title: "Post Title"
description: "Short summary of the post."
date: 2026-06-02
categories:
  - category-name
---
```
