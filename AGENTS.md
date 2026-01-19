# AGENTS.md - Homemade Games Platform Contract

## Non-negotiables
- Use the shared platform styling for consistency:
  - Always import: `<link rel="stylesheet" href="/shared/platform.css">`
- Keep the platform look consistent across games:
  - Same background, typography, spacing, card/button styles.
  - If you need a new color or spacing rule, add a CSS variable token in `/shared/platform.css` (don't invent random styles per game).
- Mobile-first, touch-first:
  - Tap targets >= 44px
  - Works well on iPad Safari and iPhone Safari.
- Static-site friendly:
  - No server required.
  - Avoid external CDNs; keep assets local.
- Accessibility basics:
  - High contrast text
  - Visible focus states
  - Clear button labels.

## Folder conventions
- Landing page: `/`
- Games live in folders:
  - `/memory/`
  - `/rushhour/`
  - `/pong/`
- Shared assets:
  - `/shared/platform.css` (theme + base components)
  - (optional later) `/shared/platform.js` (shared helpers)
  - Bump `/shared/build_id.txt` and update `?v=BUILD_ID` on shared assets/links whenever shared assets change.
  - On every release, bump `/shared/build_id.txt` so the HTML bootstrap redirects users to the latest `?v=` version.

## When adding a new game
- Create a new folder: `/<game>/`
- Include a simple `index.html` (or built output if needed).
- Import `/shared/platform.css`
- Add a card on the home page linking to `/<game>/`
