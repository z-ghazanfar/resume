# Repository Guidelines

## Project Structure & Module Organization
- Primary source lives in `latex/Zain_Ghazanfar_Resume.tex`.
- Build outputs are generated in `latex/` (for example `*.pdf`, `*.aux`, `*.log`, `*.fls`, `*.fdb_latexmk`, `*.synctex.gz`).
- Keep edits focused on the `.tex` source. Treat generated files as build artifacts unless a PDF update is intentionally part of the change.

## Build, Test, and Development Commands
- `cd latex && latexmk -pdf Zain_Ghazanfar_Resume.tex`
  - Recommended build command; resolves references and reruns as needed.
- `cd latex && latexmk -pvc -pdf Zain_Ghazanfar_Resume.tex`
  - Live-preview workflow while editing.
- `cd latex && pdflatex Zain_Ghazanfar_Resume.tex`
  - Minimal single-pass compile for quick syntax checks.
- `cd latex && latexmk -c`
  - Cleans intermediate files while keeping the generated PDF.

## Coding Style & Naming Conventions
- Use LaTeX macros already defined in the file (for example `\resumeSubheading`, `\resumeItem`) instead of ad hoc formatting.
- Keep indentation consistent with existing style (two spaces inside list/macro blocks).
- Prefer concise, metric-driven bullet text and parallel grammar across bullets.
- Preserve the current filename and top-level document structure unless there is a strong reason to refactor.

## Testing Guidelines
- There is no automated test suite in this repository.
- Validate every change by compiling the document and checking:
  - no LaTeX errors,
  - layout remains one page,
  - links/contact fields render correctly,
  - section spacing is visually consistent.

## Commit & Pull Request Guidelines
- Recent history uses short, purpose-first subjects (for example: `updated research experience`, `updated education`).
- Prefer imperative, specific commit messages such as `update experience bullets for Arrowstreet internship`.
- Keep commits scoped to one logical change.
- PRs should include:
  - brief summary of content changes,
  - why the change was made (target role, season, or audience),
  - confirmation that `latexmk -pdf` succeeds,
  - updated PDF when visual output changed.
