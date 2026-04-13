# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Mintlify documentation site hosting the SOP Binder 2026 — 83 Standard Operating Procedures for a luxury wellness/longevity hotel, organized into 11 Parts. Pages are MDX files with YAML frontmatter. Configuration is in `docs.json`. Compliance references: MEVZUAT + LQA Standards v5.1.

## Commands

```bash
# Preview locally (requires: npm i -g mint)
mint dev                  # Serves at http://localhost:3000

# Check for broken links
mint broken-links

# Update CLI if dev environment breaks
mint update
```

## Architecture

- `docs.json` — Central config: navigation (single "SOPs" tab with 11 groups), theme, logos
- `index.mdx` — Landing page with document control and card links to each Part
- `sops/` — 83 SOP pages organized by Part:
  - `arrival-emotional-intelligence/` — Part I (3 SOPs: EMO behavioral standards)
  - `intake-consultation/` — Part II (5 SOPs: phone, reservations, cancellations)
  - `assessment/` — Part III (4 SOPs: reception, arrival, orientation, scheduling)
  - `curated-program-design/` — Part IV (4 SOPs: longevity assessment, programme design)
  - `spa-services/` — Part V (9 SOPs: treatment delivery, draping, special guests)
  - `longevity-wellness/` — Part VI (16 SOPs: cryo, HBOT, IV, PBM, PEMF, float, etc.)
  - `life-optimization/` — Part VII (4 SOPs: nutrition, sleep, movement, mindfulness)
  - `movement-fitness/` — Part VIII (2 SOPs: gym, pool/beach)
  - `followup-support/` — Part IX (2 SOPs: closing, POS/billing)
  - `facility-management/` — Part X (4 SOPs: gym, courts, heat, changing rooms)
  - `safety-security-operations/` — Part XI (30 SOPs: occupational safety, fire, chemical, etc.)
- `logo/`, `images/`, `favicon.svg` — Static assets
- `.mintignore` — Files excluded from build (drafts/, *.draft.mdx)

## SOP File Naming

Files use the short SOP code: `{DEPT}-{AREA}-{NUMBER}.mdx` (e.g., `SVC-LNG-001.mdx`). The full SOP ID includes the `SOP-` prefix in the title frontmatter.

## Navigation Structure

Navigation is defined in `docs.json` under `navigation.tabs[0].groups`. Each Part is a group. Adding a new SOP requires creating the MDX file in the correct folder and adding its slug to the matching group in `docs.json`.

## SOP Page Structure

Each SOP MDX file follows this structure:
1. Frontmatter: `title`, `sidebarTitle`, `description`
2. Metadata table (version, owner, compliance refs, department)
3. Purpose, Scope, Responsibility sections
4. Procedure (numbered steps with `[P#]` identifiers)
5. Checklist (where applicable)
6. Brand Notes (deployment guidance, not auditable)
