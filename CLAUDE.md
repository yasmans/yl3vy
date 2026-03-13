# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
hugo server        # Start dev server at localhost:1313
hugo               # Build static site to /public/
hugo new posts/my-post.md  # Create a new post from archetype
```

Hugo v0.146.0+ is required.

## Architecture

This is a Hugo static site using a custom minimal theme called **basic-radio** (located in `themes/basic-radio/`).

**Template hierarchy** (`themes/basic-radio/layouts/`):
- `baseof.html` — base shell; includes `_partials/head.html`, `header.html`, `footer.html`
- `home.html`, `page.html`, `section.html`, `taxonomy.html`, `term.html` — fill the `main` block

**Asset pipeline** (`themes/basic-radio/assets/`):
- `css/main.css` — minified via Hugo pipes in production, fingerprinted with SRI
- `js/main.js` — transpiled via `js.Build`, minified in production

**Content**: The `content/` directory at the root is empty — site content goes there. The theme ships example posts under `themes/basic-radio/content/posts/` for reference.

**Taxonomies**: Tags are supported out of the box (`tags` taxonomy).

**Configuration**: Root `hugo.toml` sets base URL, title, and theme. Theme-level `hugo.toml` defines the main menu (Home, Posts, Tags).
