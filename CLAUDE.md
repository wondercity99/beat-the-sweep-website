# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Marketing/landing website for the Beat the Sweep mobile app (iOS/Android) — helps users avoid street sweeping parking tickets. Static HTML site styled with Tailwind CSS, deployed on Vercel.

## Build & Development Commands

- `npm run dev` — watch mode, rebuilds CSS on file changes
- `npm run build` — production build (minifies CSS)
- `npm run watch:css` — alternative watch command

Tailwind compiles `src/input.css` → `dist/output.css`. The output file is gitignored; Vercel runs `npm run build` on deploy.

## Architecture

**Static site — no JS framework.** Five HTML pages at the root:
- `index.html` — main landing page
- `contact.html`, `privacy.html`, `terms.html`, `delete-account.html` — supporting pages

**Styling:** Tailwind CSS v3.4.0 with custom brand colors defined in `tailwind.config.js` (sweep-blue, sweep-orange, sweep-yellow variants). Custom component classes (`.btn-primary`, `.card`, `.section-heading`, etc.) are defined as Tailwind `@layer components` in `src/input.css`.

**Fonts:** Manrope from Google Fonts. Satoshi Variable is still self-hosted in `fonts/` and `@font-face`-declared in `src/input.css`, but unused.

**Deployment:** Vercel serves the repo root as static files. Config in `vercel.json`.

## Brand Colors

| Token | Hex |
|---|---|
| sweep-blue | #519bff |
| sweep-blue-dark | #3d7ed9 |
| sweep-blue-light | #7cb3ff |
| sweep-orange | #ffb500 |
| sweep-orange-dark | #c75100 |
| sweep-yellow | #ffdd00 |

## App Store Links

- Apple App ID: `6755791905` (used in smart app banner meta tag)
- Google Play: linked via smart banner in HTML
