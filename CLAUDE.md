# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Mintlify documentation site repository. Mintlify is a documentation platform that uses MDX files and a central `docs.json` configuration file to generate documentation sites.

## Architecture

### Configuration (`docs.json`)

The `docs.json` file is the central configuration that controls:
- Site metadata (name, colors, theme, favicon, logo)
- Navigation structure (tabs, groups, pages)
- External links (navbar, footer, anchors)
- Contextual features (copy, view, AI tools integrations)

Navigation pages reference MDX files by path without the `.mdx` extension. OpenAPI specs can be referenced directly in the navigation to auto-generate API documentation.

### Content Structure

- **Root MDX files**: Landing pages (`index.mdx`, `quickstart.mdx`, `development.mdx`)
- **`essentials/`**: Core documentation features (markdown, code samples, images, navigation, settings, reusable snippets)
- **`api-reference/`**: API documentation including `openapi.json` spec and endpoint MDX files
- **`ai-tools/`**: Documentation for AI tool integrations
- **`snippets/`**: Reusable MDX content snippets
- **`images/`** and **`logo/`**: Static assets

All documentation pages use MDX (Markdown with JSX components).

## Development Commands

### Local Development

```bash
# Install Mintlify CLI globally (requires Node.js v19+)
npm i -g mint

# Start local preview server at http://localhost:3000
mint dev

# Start on custom port
mint dev --port 3333

# Update CLI to latest version
mint update

# Validate links in documentation
mint broken-links
```

### Deployment

Changes are automatically deployed to production when pushed to the main branch via the Mintlify GitHub app integration.

## Common Tasks

### Adding a New Page

1. Create an MDX file in the appropriate directory
2. Add frontmatter with `title` and optional `description`
3. Reference the page path (without `.mdx`) in `docs.json` navigation

### Modifying Navigation

Edit the `navigation` object in `docs.json`. Navigation supports:
- Tabs with groups of pages
- Global anchors (external links)
- OpenAPI spec integration for API endpoints

### Updating Site Branding

Modify `docs.json`:
- `name`: Site name
- `colors`: Theme colors (primary, light, dark)
- `logo`: Light and dark mode logo paths
- `favicon`: Site favicon path
