# sea64 brand and design system

The look of the sea64 showcase site (`website/`): a phosphor-dark theme built on the Commodore 64's
own palette. The tokens live at the top of [`website/css/style.css`](../website/css/style.css); this
page explains them and the logo.

## Name

The product and site are **sea64**, always lower case, in the wordmark followed by a cyan full stop:
`sea64.`. The npm package, the `F6502` browser global and the `f6502.min.js` bundle keep their
names; only the brand changed.

## Logo: The Curl

A breaking wave drawn on a 16 × 13 pixel grid. It is the _sea_ in sea64, and its open curl reads as
the C of the Commodore. The layers are C64 colours: foam `#d8d8f8`, cyan `#6abfc6`, purple
`#887ecb`, and the swell sinks into the C64 screen blue `#3030c8`.

| File                                  | Use                                                    |
| ------------------------------------- | ------------------------------------------------------ |
| `website/img/brand/sea64-mark.svg`      | Full-colour mark: nav, footer, emulator bar           |
| `website/img/brand/sea64-mark-mono.svg` | One colour (`currentColor`): print, below 32 px, embossing |
| `website/img/brand/sea64-app-icon.svg`  | Rounded screen tile with scanlines: avatars, app icons |
| `website/img/brand/favicon.svg`         | Mono mark; purple on light tabs, light purple on dark |
| `website/img/brand/favicon-32.png`      | PNG favicon fallback                                  |
| `website/img/brand/apple-touch-icon.png`, `icon-512.png` | Home-screen and social icons      |

Rules:

- **Grid.** Scale only in whole multiples of the grid (16, 32, 48, 64 px wide…) with
  `shape-rendering: crispEdges` / `image-rendering: pixelated`, so pixels never blur.
- **Clear space.** Keep 3 grid pixels free on every side. In the lockup the gap between mark and
  wordmark is 4 grid pixels (10 px at the nav size).
- **Small sizes.** Below 32 px wide, use the mono mark.
- **Don't** smooth, round, rotate, outline or recolour the layers, and don't put gradients on it.

The lockup is the mark followed by the wordmark set in Press Start 2P, `--primary` with the
`--primary-glow` text shadow and a `--accent` full stop.

## Colour

| Token                | Value     | Role                                         | On `--bg` |
| -------------------- | --------- | -------------------------------------------- | --------- |
| `--bg`               | `#080918` | Page                                         |           |
| `--surface` … `-3`   | `#0f1030` `#181a48` `#1f2260` | Cards, hovers, raised    |           |
| `--text`             | `#d8d8f8` | Body text                                    | 14.2:1    |
| `--text-muted`       | `#8a8ab8` | Secondary text (was `#7070a0`, 4.25:1)       | 6.0:1     |
| `--text-dim`         | `#3a3a60` | Decoration only, never text people must read | 1.8:1     |
| `--primary`          | `#887ecb` | C64 light blue: brand, primary button        | 5.6:1     |
| `--primary-bright`   | `#a090e8` | Hover, h3                                    | 7.2:1     |
| `--accent`           | `#6abfc6` | C64 cyan: labels, links, focus ring          | 9.3:1     |
| `--yellow` `--green` `--red` `--orange` | C64 palette | Tags, syntax, status  | ≥ 6.4:1   |
| `--code-comment`     | `#8080b0` | Code comments (was `#505080`, 2.6:1)         | 5.3:1     |
| `--c64-text`         | `#8f8ff0` | Text inside the ROM loader (was `#7070e8`)   |           |

Accents always come from the C64 palette; don't invent new hues. Glows (`--primary-glow`,
`--accent-glow`) mark primary actions and focus only.

## Type

| Family         | Token          | Use                                                       |
| -------------- | -------------- | --------------------------------------------------------- |
| Press Start 2P | `--font-pixel` | Logo, hero title, eyebrows and labels, stat values        |
| Space Grotesk  | `--font-body`  | Everything people read: body, titles, buttons, nav        |
| Fira Code      | `--font-mono`  | Code, file names, table keys, handles                     |
| VT323          | `--font-retro` | Only inside the C64 screen (ROM loader, boot copy)        |

Pixel labels are uppercase with `0.1–0.15em` tracking and **9 px minimum** (8 px only for
tags and decorative bezel text). Body is 17 px / 1.65.

## Shape and interaction

- Radii: `--radius-sm` 4 (tags), `--radius` 8 (buttons), `--radius-md` 10 (terminals,
  callouts), `--radius-lg` 12 (cards).
- Touch targets are at least `--tap` (44 px).
- Focus: a 2 px `--accent` outline, 2 px offset, on every interactive element.
- Callouts (`.infobox`) are fully bordered, lightly tinted boxes — no thick side stripe.
- Icons are 24 px line SVGs (`.icon`: 1.6 stroke, round caps) in `currentColor`. No emoji.
- Motion: `--ease` (`cubic-bezier(0.16, 1, 0.3, 1)`), 0.2–0.25 s; cards lift 3–4 px on hover.

## Patterns

- **CRT monitor**: bezel gradient `#2a2840 → #1a1828`, 4 px scanlines at 18 %, radial vignette,
  pixelated canvas, green power LED.
- **Terminal**: `#050510` body, `--surface-2` title bar with three dots, Fira Code 0.875 rem.
- **Showcase card**: 4:3 screenshot with light scanlines, title, author chip, one-line description.
