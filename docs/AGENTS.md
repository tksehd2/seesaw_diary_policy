# Repository Guidelines

## Project Structure & Module Organization
This repository contains static policy and landing pages for multiple apps. Root-level files such as `index.html`, `privacy.html`, `terms.html`, and `privacy_play.html` serve the main Seesaw site. App-specific pages live in subdirectories like `gakusuke/` and `planb/`. Shared deployment artifacts are kept at the root, including `CNAME`, `app-ads.txt`, and verification files such as `googledaaf6b20dda0a7da.html`. Store new app pages in a dedicated folder when they have more than one related document.

## Build, Test, and Development Commands
There is no build pipeline in this repository; pages are served as plain HTML.

- `python3 -m http.server 8000` runs a local static server for review.
- `open http://localhost:8000/` previews the site in a browser on macOS.
- `git diff -- *.html` reviews content and style changes before commit.

When editing nested pages, verify direct URLs such as `/gakusuke/privacy.html` and `/planb/terms.html`.

## Coding Style & Naming Conventions
Use semantic HTML with small inline `<style>` blocks, matching the existing structure of each page. Prefer 2-space indentation in newer pages and preserve the surrounding style in files you touch. Use lowercase, hyphen-free filenames already established here: `privacy.html`, `terms.html`, `privacy_policy.html`. Keep copy concise, production-ready, and specific to the app’s data practices. Use relative links for same-folder navigation and absolute paths only when linking from a section root such as `/gakusuke/privacy.html`.

## Testing Guidelines
There is no automated test suite yet. Validate changes by loading the affected page locally, checking navigation links, and confirming responsive layout in both desktop and mobile widths. If you update legal or policy text, verify dates, app names, contact email, and referenced Google/API scopes line by line before merging.

## Commit & Pull Request Guidelines
Recent commits use short, page-focused summaries such as `privacy.html を更新` and `페이지들 정리`. Follow that pattern: keep subjects brief, specific, and tied to the changed page or app section. For pull requests, include a short description, list affected URLs/files, mention any policy or consent-screen changes, and attach screenshots when layout or styling changed.

## Deployment Notes
This repository appears to back a static host. Avoid introducing build-time dependencies unless the hosting approach changes, and keep root verification files untouched unless the related external service is being updated.
