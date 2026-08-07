# Vilye Farmer Producer Company

Website for Vilye Farmer Producer Company Limited (https://vilyefpc.com), built with Astro and deployed to GitHub Pages.

## Stack

- **Astro 7** — static site, no framework components or content collections
- **Tailwind CSS 4** — via the `@tailwindcss/vite` plugin, with typography support
- **Vite+** — unified toolchain (`vp` CLI) for installation, formatting, linting, and tasks
- **pnpm** — package manager (via Vite+)

## Commands

| Command          | Purpose                        |
| ---------------- | ------------------------------ |
| `vp install`     | Install dependencies           |
| `vp run dev`     | Start the development server   |
| `vp run build`   | Build to `dist/`               |
| `vp run preview` | Preview the production build   |
| `vp check`       | Format, lint, and type check   |
| `vp check --fix` | Fix formatting and lint issues |

A pre-commit hook runs `vp check --fix` on staged files automatically.

## Project Structure

- `src/pages/` — site routes (`index.astro`, `404.astro`, and `robots.txt.ts`)
- `src/layouts/Layout.astro` — shared HTML shell, metadata, and analytics setup
- `src/styles/global.css` — Tailwind CSS and typography plugin imports
- `src/types.d.ts` — shared metadata types
- `public/` — static assets, when needed

## Conventions

- Components and layouts are `.astro` files with lowercase-kebab naming
- TypeScript uses Astro's strict configuration (`astro/tsconfigs/strict`)
- Keep the site static — do not add server endpoints or SSR without a clear need
- Prefer Tailwind utilities; keep shared design tokens in `src/styles/global.css`
- Keep site metadata, canonical URLs, and SEO tags in sync when updating page content
- Commit messages use Conventional Commits (`feat:`, `fix:`, `chore:`, `ci:`, …); keep commits focused

## Deployment

Pushing to `main` triggers `.github/workflows/deploy.yaml`, which builds with the official Astro action and deploys to GitHub Pages. The workflow can also be run manually from GitHub Actions.

## Documentation

Full Astro docs: https://docs.astro.build

Consult these guides before working on related tasks:

- [Adding pages or routes](https://docs.astro.build/en/guides/routing/)
- [Astro component syntax](https://docs.astro.build/en/basics/astro-components/)
- [Styling and Tailwind](https://docs.astro.build/en/guides/styling/)
- [Integrations](https://docs.astro.build/en/guides/integrations-guide/)

<!--VITE PLUS START-->

# Using Vite+, the Unified Toolchain for the Web

This project is using Vite+, a unified toolchain built on top of Vite, Rolldown, Vitest, tsdown, Oxlint, Oxfmt, and Vite Task. Vite+ wraps runtime management, package management, and frontend tooling in a single global CLI called `vp`. Vite+ is distinct from Vite, and it invokes Vite through `vp dev` and `vp build`. Run `vp help` to print a list of commands and `vp <command> --help` for information about a specific command.

Docs are local at `node_modules/vite-plus/docs` or online at https://viteplus.dev/guide/.

## Built-in Commands vs Scripts

`vp <name>` runs a built-in command. `vp run <name>` runs a `package.json` script or a `vite.config.ts` task. Scripts cannot overwrite built-ins, so `vp dev` and `vp run dev` may do different things. Check `package.json` and `vite.config.ts` first, and run `vp run <name>` when the project defines a script or task with that name.

## Review Checklist

- [ ] Run `vp install` after pulling remote changes and before getting started.
- [ ] Run `vp check` and `vp test` to format, lint, type check and test changes.
- [ ] Check if there are `vite.config.ts` tasks or `package.json` scripts necessary for validation, run via `vp run <script>`.
- [ ] If setup, runtime, or package-manager behavior looks wrong, run `vp env doctor` and include its output when asking for help.

<!--VITE PLUS END-->
