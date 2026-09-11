# LG Design System — design.md

Reference distilled from the visual language of [lg.com/uk](https://www.lg.com/uk/). Companion to `design-system.html`, the live component/token reference.

## Premise

lg.com/uk stages products on near-black grounds and spends colour on exactly one thing: the call to action. This system captures that discipline as reusable tokens so any LG-adjacent surface — marketing page, support tool, internal dashboard — reads as one product.

Core rule: **one accent, one action per view.** Everything else below exists to protect that rule.

## Colour

| Token | Light value | Dark value | Usage |
|---|---|---|---|
| `--bg` (Ink / Paper) | `#FAF8F6` | `#0B0B0D` | Page ground. Dark is the product-staging black behind hero imagery; light is a warm off-white documentation ground — never stark white. |
| `--surface` | `#FFFFFF` | `#151318` | Cards, panels, form fields. |
| `--surface-2` | `#F1EEE9` | `#1D1A20` | Nested surfaces — grid demos, footer block. |
| `--text` | `#17151A` | `#F3F1EF` | Primary text. |
| `--text-muted` / Slate | `#6B6670` | `#9C97A0` | Secondary text, captions. Border hue is mixed from this, never pure grey. |
| `--border` | `#E4DFD8` | `#2C2930` | Hairlines only — no shadows for separation. |
| `--accent` (Signal Red / Ember) | `#A50034` | `#FF3E63` | The one brand action colour: CTAs, active nav state, the single key badge per view. Dark mode lifts it toward `#FF3E63` for AA contrast on Ink, same hue family. |
| `--signal` (Amber Signal) | `#C97A2B` | `#E8A33D` | Promotional badges only — NEW, SALE, %OFF. Reserved for merchandising; never used for actions. |

**Rule of one:** if a screen has a primary button and a "NEW" badge, that's the accent's one use plus the signal's merchandising use — never two accent elements competing.

## Typography

Archivo (700/800) for headlines — blunt, engineered, matches how LG names its own products. IBM Plex Sans (400/600) for body copy. IBM Plex Mono (400/500) for anything technical: prices, model numbers, token names, badges.

| Step | Family / weight | Size / line-height | Notes |
|---|---|---|---|
| Display | Archivo 800 | 44 / 46 | Hero headlines only. |
| H1 | Archivo 700 | 32 / 38 | |
| H2 | Archivo 700 | 24 / 30 | Section headers. |
| H3 | Archivo 600 | 18 / 26 | Card and panel titles. |
| Body Large | Plex Sans 400 | 18 / 29 | Lead paragraphs. |
| Body | Plex Sans 400 | 16 / 26 | Default running text. Keep lines near 65 characters. |
| Caption | Plex Sans 600, uppercase | 12.5 / 18, +0.09em | Eyebrows, field labels. |
| Mono | Plex Mono 400 | 14 / 22 | Prices, SKUs, code, token names. |

Headings use `text-wrap: balance`; body text is never justified.

## Spacing & grid

Base-4 scale. Small values (4–12px) for internal component padding; large values (48–96px) between page sections — the sparse, breathing layout of a product page rather than a dense catalogue.

`--sp-1: 4px` · `--sp-2: 8px` · `--sp-3: 12px` · `--sp-4: 16px` · `--sp-5: 24px` · `--sp-6: 32px` · `--sp-7: 48px` · `--sp-8: 64px` · `--sp-9: 96px`

Grid: 12 columns, 8px gap. Gutters follow `--sp-5` (24px) on desktop, `--sp-4` (16px) on mobile. Sidebar-driven layouts collapse to a single column and a horizontal-scroll nav strip below ~880px.

## Components

**Buttons** — square corners (max 2px radius), no drop shadow; weight comes from fill and label, not elevation.
- `.btn-primary` — accent fill. Exactly one visible per view.
- `.btn-secondary` — outlined, text-coloured border.
- `.btn-ghost` — underlined text link, no fill.
- `.btn-sm` — dense contexts: card footers, table rows.
- `[disabled]` — 40% opacity, no hover state.

**Badges & tags** — monospace, uppercase, small. They read as system labels, not decoration, so they never compete visually with a primary button.
- `.badge-new` — accent fill. Counts as the view's one accent use if a button is also present, so prefer only one or the other.
- `.badge-sale` — signal (amber) fill. Promotional only.
- `.badge-outline` — neutral border, sentence case. Specs and attributes (energy rating, resolution).

**Cards** — hairline border, ≤10px radius, no shadow. Product imagery sits on an abstract gradient or Ink background rather than a flat mid-tone — a habit borrowed directly from lg.com's promotional tiles.

**Navigation** — the primary nav is always dark (`Ink` / `#0B0B0D`), regardless of the page's own theme. It's the one component LG never renders on white. Mega-menu columns mirror the top-level link labels exactly.

**Forms** — single hairline border, transparent fill until focus. No placeholder-as-label; every field keeps a visible `<label>`.

**Footer** — link groups mirror the primary nav's structure exactly; the footer is a sitemap, not a separate hierarchy. Legal row (privacy, terms, accessibility, cookies) sits below a hairline divider.

## Guidelines

**Do**
- Use Signal Red for exactly one action per screen.
- Stage product imagery on Ink or a gradient, never a flat mid-tone.
- Set badges in Plex Mono so they read as data, not decoration.
- Keep the primary nav dark even on a light-theme page.

**Don't**
- Pair two accent-coloured elements in the same view.
- Use Amber Signal for anything but merchandising badges.
- Round card corners past 10px — the brand reads square.
- Let body copy run past ~65 characters per line.

## Source

Derived from a visual audit of `lg.com/uk` (homepage navigation, hero carousel, product grid, footer) on 2026-09-11: dark/neutral staging with a single red accent, card-based product grids, carousel heroes, badge/tag merchandising, and a multi-column sitemap footer. Exact brand hex values (`#A50034` "LG Red") are LG's published corporate colour, applied here rather than scraped, since production CSS is not exposed to static fetch.
