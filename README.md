# Ferretti & Figlia — bakery site

Standalone, framework-free implementation of the Claude Design project
(`claude.ai/design/p/8ae6d978-…`). No build step, no runtime — open the `.html`
files directly, or serve the folder (e.g. `python3 -m http.server`).

## Pages
- **`index.html`** (homepage) ← `Home.dc.html`
  - Fullscreen video hero (Cormorant Garamond wordmark).
  - "Our Story" — draggable photo collage that scatters/gathers on scroll (desktop),
    stacked photo grids on mobile.
  - "What We Make" — category chips + a 24-item catalog with **add-to-cart**, a sticky
    order bar, and **WhatsApp checkout** (`wa.me/919575270453`).
  - "Locations" — two cards with live Google Maps embeds, hours and phone.
  - Shared floating nav, reveal-on-scroll, card-shine, footer.
- **`Wholesale.html`** ← `Wholesale.dc.html`
  - Dark hero + lazy video, "What We Supply" shine cards, a 420vh 3D scroll-wheel
    ("The wholesale difference"), and an enquiry form → `mailto:` + inline success.

Nav/footer links point to `Home.html` / `Wholesale.html` (the `.dc.html` comps become
plain `.html`).

## Assets — IMPORTANT
Filenames match the design exactly, so dropping these `.html` files into the exported
Claude Design project folder (which already ships a full `assets/`) makes everything
resolve with no edits.

A few real assets were larger than the design API's 256 KiB read limit, so this folder
ships **branded placeholders** (each stamped "PLACEHOLDER"). Replace with the export
originals:

**Real (pulled from the design):** `logo-trimmed.png`, `cur-cake.png`,
`cur-strawberry.png`, `icon-cakes.png`, `icon-pastries.png`, `icon-seasonal.png`.

**Placeholders to swap:**
- `story-1…8.jpeg` — Our Story collage
- `w-supply-bread/pastry/catering.jpeg` — Wholesale supply cards
- `c-nonna / c-ricotta / c-crostata / c-caprese / c-millefoglie.jpeg` and
  `s-panettone / s-colomba / s-castagnaccio / s-fico / s-zeppole / s-pandoro.jpeg` — cake & seasonal photos
- `loc-carlton.jpeg`, `loc-brunswick.jpeg` — location photos
- `story-bg.jpg` — repeating paper texture
- `icon-breads.png` — Seasonal chip icon (line glyph)
- `hero-poster.jpg` — poster shown until `hero.mp4` is present
- **Missing (copy from export):** `hero.mp4` (Home), `wholesale-hero.mp4` (Wholesale)

Products in Pastries & Breads (and Tiramisù) intentionally render the design's empty
image-slot look — a soft ceramic tile with the item name — matching the comp.

## Favicon & social thumbnail (drop-in)
Both pages already reference these two files — just add them to `assets/`:
- `assets/favicon.png` — the bread-and-wheat logo (square, e.g. 512×512). Used for the
  browser tab and the iOS home-screen icon.
- `assets/thumbnail.jpg` — social share image shown when the site is linked (Open Graph /
  Twitter card; ~1200×630 recommended).

On deploy, change the two `og:image` / `twitter:image` paths to your full
`https://…/assets/thumbnail.jpg` URL — most scrapers require an absolute URL.

## Notes
- Enquiry form and footer email links use `tejxshrivastava@gmail.com` (from the comps).
  Swap for a real endpoint (e.g. Web3Forms) for server-side handling.
- Everything is theme-fixed to the brand palette; no dark-mode handling (matches design).
