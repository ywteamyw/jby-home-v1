# Jeff Brown Yachts — Home page V1

Live HTML copy of the Figma frame **"Home page - V1"**
(`MN091X2k7mLZfincVKVdjR`, node `62286-32369`).

One self-contained `index.html` plus `assets/`. No build step, no dependencies
beyond Leaflet (CDN) for the "Visit us" map.

## Sections

| # | Section | Notes |
|---|---------|-------|
| 1 | Hero | background video, 44/64 Mesmerize headline, two CTAs |
| 2 | Yachts for sale | horizontal card rail, "Open House" badge, price-reduced flag |
| 3 | Upcoming events & private experiences | card rail, navy "Request to attend" |
| 4 | Built around the owner | background video promo banner |
| 5 | Access to world-class brands | background video promo banner |
| 6 | The builders we represent | 4x2 grid, 8 brands |
| 7 | Support for every stage of ownership | 6 full-bleed bands |
| 8 | Visit us | scrolling office list + Leaflet map |
| 9 | Get expert guidance + footer | navy CTA band, footer |

## Design tokens (from the Figma variables)

```
Mesmerize   44/64  headline lg      Myriad Pro  20/28  text xl
            32/48  headline md                  18/28  text lg
            28/40  headline sm                  16/24  text md
            20/28  headline 2xs                 14/20  text sm
            16/24  headline 4xs
navy #41647b   page #fcfcfd   section #f4f6f9   ink #2f2f39
mute #575760   line #eeeef0   success #119555   soft #dcdcde
```

Gutters: `.wrap` = max-width 1440, 40px desktop / 24px mobile.
The hero and the promo banners use the Figma's wider 64px inset.

## Video

| File | Used by |
|------|---------|
| `assets/hero_aerial.mp4` | hero, and the "Access to world-class brands" banner (offset 8s) |
| `assets/promo_riva.mp4` | "Built around the owner" banner |

Promo videos are lazily hydrated by an IntersectionObserver and paused off-screen.

## Map

The office map uses **Esri "World Light Gray"** tiles. CARTO's anonymous
basemaps now return tiles stamped "API KEY REQUIRED", so they can no longer be
used unkeyed. The view frames all nine locations, Kona included.

## Deviations from the Figma frame

* Event rail sits 64px under its title (matching the yachts rail) rather than
  the Figma's 40px, so the two rails share one rhythm.
* Brand wordmarks: Riva, Axopar, Pershing, BRABUS and Sirena use the dark marks
  from the Figma file. Wally, Four Winns and Jeanneau exist only as
  white-on-transparent SVGs, so they are rendered through `brightness(0)`.
* The promo banners carry a stronger bottom scrim than the Figma still, because
  the live footage runs through bright frames the static comp never shows.
* Footer contact block follows this frame (`+1 619-222-9899`,
  `jeff@jeffbrownyachts.com`, street address) rather than the site-wide footer
  (toll-free number, `info@`, Locations column).
