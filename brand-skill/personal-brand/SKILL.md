---
name: personal-brand
description: Esther's personal website brand system — deep navy, sage/seafoam green, and warm cream/sand, with a premium coastal-luxury feel (think Hermès craftsmanship, not tech-SaaS). Use this whenever building, styling, or reviewing pages/components for Esther's personal site (or any artifact/mockup meant to represent her brand).
---

# Personal Brand: "Deep Current"

A premium, coastal-luxury look for a personal website — closer to Hermès than to a SaaS landing page. The tone is whimsical + technical + personal, but the material feel is rich and tactile: warm neutrals instead of stark white, muted sophisticated green instead of bright/kelly green, deep navy instead of primary blue. Nothing should look like a default tech palette.

## Design principles

1. **Premium through material, not decoration.** Think Hermès, not a startup landing page: warm neutrals instead of stark white, muted couture-grade tones instead of digital-bright ones, generous whitespace, precise type. Premium comes from restraint and quality of tone, not embellishment.
2. **Coastal, not corporate.** The palette should feel like weathered navy canvas, sea glass, and sand — not "tech blue" or "eco green." Every color is slightly muted/dusty, never saturated or neon.
3. **Whimsical in small doses.** A little personality lives in micro-interactions, illustration accents, or a slightly playful line of copy — never in the core layout or type system. The grid stays clean; the charm is a garnish.
4. **Tech-personal, not tech-corporate.** Monospace or geometric touches (labels, tags, code-like details) signal "builder," but pair them with warm, human copy in first person.
5. **Cream does the heavy lifting.** Most surfaces are warm ivory/sand, not clinical white. Deep navy and sage are used as accents, headers, and moments of emphasis — not backgrounds for entire sections.

## Color palette — "coastal luxury"

Muted, couture-grade tones. Nothing saturated, nothing neon — every color reads like it was dyed, not screen-lit. Use CSS variables so dark mode is a first-class citizen.

```css
:root {
  /* Neutrals — warm sand/ivory, never stark white */
  --color-bg: #f7f2e8;           /* warm ivory, the main surface */
  --color-surface: #efe7d8;      /* slightly deeper sand, for cards */
  --color-border: #ddd1ba;
  --color-text: #1c231f;         /* near-black, warm charcoal */
  --color-text-muted: #6b6a5e;

  /* Deep navy (primary) — weathered canvas, not tech blue */
  --color-navy-900: #131c2b;
  --color-navy-700: #1c2d43;
  --color-navy-500: #34506f;     /* interactive/accent navy */
  --color-navy-300: #8fa3b8;

  /* Sage / seafoam (secondary) — muted, not kelly green */
  --color-sage-900: #2e362c;
  --color-sage-700: #556252;
  --color-sage-500: #8a9b82;     /* muted accent, CTAs */
  --color-sage-300: #c3cdb9;

  /* Brass (rare accent) — the one luxury flourish, use sparingly */
  --color-brass: #ab8654;

  --color-accent: var(--color-sage-500);
  --color-accent-alt: var(--color-navy-500);
}

@media (prefers-color-scheme: dark) {
  :root:not([data-theme="light"]) {
    --color-bg: #14181a;
    --color-surface: #1b2022;
    --color-border: #2c3234;
    --color-text: #f2ede1;
    --color-text-muted: #a6a89a;
  }
}
:root[data-theme="dark"] {
  --color-bg: #14181a;
  --color-surface: #1b2022;
  --color-border: #2c3234;
  --color-text: #f2ede1;
  --color-text-muted: #a6a89a;
}
```

Usage rules:
- Backgrounds: warm ivory/sand (light) or near-black warm charcoal (dark). **Never pure white (#fff) or pure black** — always the warm-toned neutral. Never a full-bleed navy/sage section unless it's a single deliberate "hero moment" per page.
- Deep navy (`--color-navy-900/700`) = headings, nav, footer, "serious" structural elements.
- Sage (`--color-sage-500/700`) = supporting accent, secondary CTAs, active states — muted, never bright green.
- Brass (`--color-brass`) = the rare luxury flourish: a hairline rule, a small icon, a hover underline. Use it like jewelry — sparingly, never as a fill color for large areas.
- Never use navy and sage as equal 50/50 — pick navy as dominant per page/section and let sage be the supporting accent, with brass as the occasional accent-on-accent.

## Typography

- **Headings:** a clean geometric or humanist sans with some character — e.g. `"Fraunces"`, `"Newsreader"`, or `"General Sans"` for a touch of editorial warmth, OR a crisp grotesk (`"Inter"`, `"Söhne"`) if leaning more tech. Default recommendation: pair a serif/editorial display face for H1/H2 with a clean sans for everything else — this is where "premium + whimsical" lives.
- **Body:** `"Inter"`, `"Söhne"`, or system-ui — highly legible, neutral.
- **Mono accents:** `"JetBrains Mono"` or `"IBM Plex Mono"` for tags, labels, timestamps, code snippets, small kickers above headings (e.g. `// about`, `01 — projects`). This is the "tech-personal" signature.
- Scale: generous line-height (1.5+ body, 1.1–1.2 display), large type jumps between levels (don't crowd the scale) — part of what reads "premium."

```css
--font-display: 'Fraunces', Georgia, serif;
--font-body: 'Inter', system-ui, sans-serif;
--font-mono: 'JetBrains Mono', 'IBM Plex Mono', monospace;
```

## Voice & copy

- First person, warm, direct. Not "we" — it's a personal site.
- Short sentences. Confidence without hype — avoid "revolutionary," "cutting-edge," "game-changing."
- A dash of whimsy is fine in microcopy (button labels, empty states, 404 pages) — e.g. "still building this →" — but headlines stay clear and substantive.
- Mono-styled kickers/labels (see Typography) are a good place for personality: `// currently`, `still tinkering`, `est. 2024`.

## Layout & components

- **Spacing:** generous section padding (96–160px vertical on desktop), tight internal component spacing. Whitespace is the premium signal.
- **Cards/surfaces:** subtle border (`--color-border`) + very soft shadow, not heavy drop shadows. Rounded corners, moderate (8–14px), not pill-shaped everywhere.
- **Buttons:** solid navy for primary CTA, sage or brass-hairline outline/ghost for secondary. No gradients on buttons.
- **Dividers/accents:** thin 1px brass or sage hairlines, or small dot/dash motifs in mono style, rather than decorative icons.
- **Imagery/illustration:** if used, simple line-art or single-color (navy or sage) illustration — not busy or multicolor. Whimsy comes from *what* is illustrated (a small personal detail) more than *how* (keep the style restrained).
- **Motion:** subtle — fade/slide-in on scroll, gentle hover lifts (2–4px translate + shadow), no bouncy/elastic easing. Premium motion is quiet.

## Do / Don't

**Do:** warm ivory backgrounds, deep navy headers, muted sage as a quiet secondary accent, a single brass flourish per view, mono kicker labels, lots of whitespace, editorial-serif display type, quiet hover states.

**Don't:** pure white or pure black, bright/kelly/neon green, primary "tech" blue, gradients, drop-shadow-heavy cards, more than 2 accent colors active at once, all-caps everywhere, stock "SaaS gradient blob" backgrounds.

## Quick reference for building a page

1. Start with a warm ivory background (`--color-bg`, never `#fff`), deep-navy nav/logo.
2. Pick ONE hero accent (navy OR sage) for the primary visual moment; reserve brass for a single flourish.
3. Use mono kickers for section labels.
4. Editorial-serif for H1, clean sans for body and UI text.
5. Navy for the single primary CTA; sage for secondary; everything else stays neutral.
6. Check dark mode: near-black warm charcoal background, same accent logic inverted.
