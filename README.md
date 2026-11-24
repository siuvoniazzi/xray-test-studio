# Xray Cloud Test Studio

A zero-dependency, keyboard-first browser studio for authoring, importing, and validating **Jira Xray Cloud** test cases with multi-project local folder persistence and compliant CSV export.

**Live app:** https://siuvoniazzi.github.io/xray-test-studio/

## Highlights

- **100% Client-Side & Private:** Runs entirely inside your browser with zero external scripts, zero backend servers, and zero telemetry. When connected to a local folder, files are read and written directly between your browser and disk—your test data never leaves your machine.
- **Direct Local Folder Persistence (`o` / `w`):** In Chrome and Edge over HTTPS (`github.io`) or `localhost`, connect any local or OneDrive/SharePoint-synced folder via `window.showDirectoryPicker()`. Projects persist cleanly as:
  - `central-config.json` — Shared Labels, Components, Priorities (`1`, `2`, `3`), and CSV settings
  - `<project>.json` — Project metadata, test cases, and steps (source of truth)
  - `<project>.xray.csv` — Auto-updated Xray Cloud import CSV (toggleable in Central Config)
- **Central Config & Team Distribution (`g`):** Configure allowed Labels, Components, Priority (`1`, `2`, `3`) labels, and CSV column headers, or click **Save Pre-Configured Team HTML** to distribute a single pre-baked `.html` file.
- **AI Smart Import (`i`):** Paste any unstructured text—user stories, Jira descriptions, emails, bullet notes, or messy spreadsheets—or attach `.xlsx` / `.csv` / `.txt` / `.md` files and let an AI API generate clean, structured Xray Cloud test cases constrained to your Central Config Labels, Components, and Priorities (`1`, `2`, `3`). Supports **Google Gemini** (`gemini-3.8-flash`), **OpenAI**, **OpenRouter**, **Anthropic Claude**, or any **Custom OpenAI-Compatible** endpoint directly from the browser (BYOK: keys stay in `sessionStorage` by default or optional browser `localStorage`, and are never saved to project files or config JSON).
- **Structured Excel / CSV / Paste Import (`i`):** Also includes a zero-API offline importer for `.xlsx`, `.csv`, `.tsv`, `.json` drafts, and pasted Excel cells (`Ctrl+V`) with column mapping and automatic cleanup of duplicate step-row summaries.
- **Built-In Onboarding & Interactive Tour:** First-time visitors get a Welcome Guide with a 7-step hands-on keyboard tutorial that walks through navigation, editing, column/step reordering, priority/labels/components, AI import, local folder sync, and Xray CSV export (replayable anytime via **Tour** in the top bar or Command Palette `/`).
- **Xray Cloud CSV Export (`e`):** Places `Test Summary`, `Test Type`, `Priority`, `Labels`, `Components`, and `Requirement` on **step 1 only**, joins multiple Labels/Components with `;` in double quotes (e.g. `"Regression;Smoke"`), and exports UTF-8 CSV (with optional BOM) in your chosen step-column order.

## Core Keyboard Shortcuts

| Keys | Action |
| :--- | :--- |
| `Arrow keys` | Move focus across the test step grid |
| `Enter` / `F2` | Edit active cell (`Tab` saves & advances, auto-adding a step at the end) |
| `Alt+↑` / `Alt+↓` | Reorder active step up / down |
| `Alt+←` / `Alt+→` | Rearrange active step column left / right |
| `1` / `2` / `3` or `p` | Set Priority (`1`, `2`, `3`) per test case |
| `l` / `c` | Multi-select Labels / Components picker |
| `s` / `r` | Edit Test Summary / Requirement key |
| `n` / `d` / `Del` | Insert / duplicate / delete test step |
| `t` / `[` / `]` | New / previous / next test case |
| `w` | Projects & Local Folder workspace manager |
| `o` | Connect or reconnect local folder |
| `g` | Open Central Config |
| `i` / `e` | Import `.xlsx`/`.csv`/paste · Validate & Export Xray CSV |
| `Ctrl+S` | Save immediately to connected folder (or download `<project>.json`) |
| `/` or `Ctrl+K` | Command Palette |
| `?` | Full keyboard shortcuts reference |
