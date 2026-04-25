# RainbowStar Website

## Project Overview
Static website for RainbowStar — a multidimensional healing and creative practice integrating bodywork, sound, plant spirit medicine, and sacred painting. Domain: rainbowstar.net

**Core feeling to preserve:** *"This is beautiful… I feel something… I want to explore more."*

## Frontend Design Skill
Always invoke the `frontend-design` skill for any UI/frontend changes before implementing. This ensures design decisions align with the visual language below.

## Design System

### Brand Essence
- Mystical but grounded
- Artistic but clear
- Sacred but accessible
- Let the art lead — fewer, stronger images
- Spacious and uncluttered

### Color Palette (CSS variables in `css/style.css`)
| Variable | Value | Use |
|---|---|---|
| `--deep-night` | `#0a0b18` | Primary background |
| `--navy` | `#111428` | Section backgrounds |
| `--cosmic` | `#1a1d3a` | Accent backgrounds |
| `--gold` | `#c9a84c` | Primary accent, borders, icons |
| `--gold-light` | `#e8c97a` | Hover states, nav logo, headings |
| `--rainbow-violet` | `#7b4fa6` | Glow accents |
| `--rainbow-blue` | `#3a7bd5` | Glow accents |
| `--rainbow-green` | `#2ea86a` | Glow accents |
| `--white` | `#f4f0eb` | Primary text |
| `--white-soft` | `rgba(244,240,235,0.85)` | Body text |
| `--text-muted` | `rgba(244,240,235,0.55)` | Secondary text |

### Typography
- **Display / headings:** `Cinzel` (serif, uppercase, wide letter-spacing)
- **Body text:** `Josefin Sans` (sans-serif, weight 300) — `--font-body`
- **Hero subtitles & "energy artist" tagline:** `Cormorant Garamond` (serif, weight 300) — `--font-serif`
- Hero subtitles use `.hero-subtitle` class — Cormorant Garamond, not italic
- Section labels: 0.6rem, letter-spacing 0.4em, uppercase, gold
- Nav links: 0.7rem, letter-spacing 0.2em, uppercase
- Nav logo sub-label ("energy artist"): `.nav-logo-sub` class, 0.9rem, Cormorant Garamond italic

### Visual Aesthetic
- Watercolor + cosmic/starfield textures
- Original paintings as primary visuals
- Subtle sacred geometry overlays
- Nature elements: water, mountains, light
- Dark backgrounds with gold accents — never use light/white backgrounds
- Circular image treatments (especially Oracle page)
- `loading="lazy"` on all images

### Motion & Interaction
- All transitions: `0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94)` (`--transition`)
- Hero: slow Ken Burns zoom animation (`slowZoom`, 20s)
- Scroll: `.fade-in` / `.fade-in.visible` pattern (JS in `js/main.js`)
- Hover: gold border reveal, translateY(-4px) lift on cards
- Buttons: gold sweep fill on hover (translateX pseudo-element)

### Buttons
- `.btn` — outlined gold, sweep-fill on hover
- `.btn-solid` — solid gold fill, gold-light sweep on hover
- Font: Cinzel, 0.65rem, letter-spacing 0.25em, uppercase

### Layout
- Max content width: `1000px` via `.section-inner`
- Section padding: `6rem 2rem` desktop / `4rem 1.5rem` mobile
- Divider: 60px gold gradient line, centered (`<div class="divider"></div>`)
- Grid: `repeat(auto-fit, minmax(260px, 1fr))`

## Site Structure
```
index.html          — Home (hero with hero-painting.jpeg)
pages/
  sessions.html     — Temple / booking (painting-heart.jpeg banner)
  oracle.html       — Symbolic/mystical (circular photo-rainbow-rose.jpeg header)
  circles.html      — Circle offerings (Sacred Relating, 7-week in-person, Portland OR)
  art.html          — Gallery (painting-swirl-petals.jpeg banner, filterable grid + lightbox)
  book.html         — Booking
  about.html        — Practitioner bio
css/style.css       — All styles live here (no embedded <style> blocks in HTML files)
js/main.js
images/             — 80+ original paintings and photos (JPEG)
```

## CSS Architecture (as of April 2026)
All styles are in `css/style.css` — no embedded `<style>` blocks in HTML files. Page-specific classes are organized by section at the bottom of the file:
- Sessions: `.session-cards-grid`, `.session-card`, `.modality-grid`, `.modality-card`, `.expect-steps`
- Circles: `.circle-hero-image`, `.week-arc`, `.details-grid`, `.practice-list`, `.pull-quote`, `.investment-block`, `.form-field`, `.form-input`, `.form-textarea`
- Art gallery: `.gallery-filters`, `.filter-btn`, `.gallery-grid`, `.gallery-item`, `.gallery-caption`, `.lightbox`
- About: `.photo-grid`
- Shared utilities: `.hero-subtitle`, `.hero-tagline`, `.section-label`, `.section-title`, `.divider`, `.two-col`, `.fade-in`

## Rules
- Never add light/white backgrounds or break the dark cosmic theme
- Original paintings are the hero visuals — never replace with stock imagery
- Keep copy minimal, poetic, and spacious — avoid marketing language
- Preserve all `loading="lazy"` attributes on images
- Mobile nav uses `.nav-toggle` hamburger + `.nav-links.open` class (handled in `main.js`)
- Copyright: "© RainbowStar Inc. All paintings and photography are RainbowStarOriginals."
- Do not use git worktrees — work directly on the main branch
