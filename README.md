# conscientiousengineers.github.io

Collective of conscientious engineers website.

Built with [Hugo](https://gohugo.io/) and the [Blowfish](https://blowfish.page/) theme. Deployed automatically to GitHub Pages on push to `main`.

## Local development

```bash
hugo server --buildDrafts
```

Site runs at `http://localhost:1313` with live reload.

## Creating an article

1. Create a new article folder:

```bash
hugo new content "articles/my-article-title/index.md"
```

Use hyphens instead of spaces and avoid apostrophes in folder names for cleaner URLs.

2. Edit the generated file at `content/articles/my-article-title/index.md`. It starts with frontmatter like this:

```yaml
---
title: "My Article Title"
date: 2026-08-23
draft: true
summary: "A short description shown on the article card."
tags: ["topic", "another-topic"]
---
```

3. Write the article body in Markdown below the frontmatter.

4. When ready to publish, set `draft: false`.

5. Commit and push to `main` — the GitHub Actions workflow builds and deploys automatically.

## Project structure

```
config/_default/    # Site configuration (hugo, menus, params, etc.)
content/
  _index.md         # Homepage content
  about/index.md    # About page
  articles/         # All articles live here
    _index.md       # Articles list page
    welcome/        # Each article is a folder with index.md
assets/css/
  schemes/          # Custom color scheme (neonforge)
  custom.css        # Custom styling overrides
.github/workflows/  # GitHub Actions deployment
```

## Deployment

Pushes to `main` trigger the GitHub Actions workflow which builds the site and deploys to GitHub Pages. Make sure the repo's Settings > Pages source is set to **GitHub Actions**.
