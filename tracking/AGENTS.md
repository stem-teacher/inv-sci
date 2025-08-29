# Repository Guidelines

## Project Structure & Module Organization
- Root: `_quarto.yml` controls rendering; only `**/progress.qmd` files are rendered.
- Groups: each cohort/dataset lives in its own folder (e.g., `bmo/`, `fungus/`, `sugar-glider/`, `sydney-north/`) with a single `progress.qmd`.
- Outputs: HTML/PDF/Markdown render next to each `progress.qmd` (non-website project). `.quarto/` is a build cache and should not be committed.

## Build, Test, and Development Commands
- `quarto check` — verify Quarto and toolchain (LaTeX for PDF) are available.
- `quarto preview` — live-reload preview while editing all tracked `progress.qmd` files.
- `quarto render` — render all progress files to all formats defined in `_quarto.yml`.
- Examples:
  - `quarto render bmo/progress.qmd --to html`
  - `quarto render fungus/progress.qmd --to pdf`

## Coding Style & Naming Conventions
- Files: one `progress.qmd` per group directory; directory names use kebab-case (e.g., `new-group/`).
- Front matter: keep consistent with existing docs:
  - `title: "Study Progress — <group>"`, `date: last-modified`, `format: [html, pdf]`, `toc: true`, `number-sections: false`.
- Content: use `#`/`##` headings; include "Test Attempts" and "Notes" sections; under Notes include `### Pacing` (speed, accuracy trend, next action) and `### Reflection` (brief student reflection). Keep the results table columns and order consistent.

## Testing Guidelines
- No automated tests. Validate by:
  - Running `quarto check` and rendering to HTML and PDF.
  - Opening outputs to confirm headings, tables, and dates render correctly.
  - Avoid committing `.quarto/` or OS artifacts (e.g., `.DS_Store`).

## Commit & Pull Request Guidelines
- Commits: present tense, concise, and scoped. Example: `bmo: update progress with Test 2 results` or `render: refresh all progress outputs`.
- PRs: include a brief description, list affected directories, and (optionally) screenshots or links to rendered HTML/PDF. Reference related issues when applicable.

## Security & Configuration Tips
- Content hygiene: avoid personal identifiers; keep progress aggregated by group.
- PDF rendering: install LaTeX if needed (`quarto install tool tinytex`).
