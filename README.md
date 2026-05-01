# Zeus & Fee – Landing Page

Static one-page website for **Zeus & Fee**, the mobile animal alternative therapy practice
run by Kathrin Jeske (pfotenthp.de).

## Project structure

```
Landing/
├── index.html
├── css/
│   ├── base.css        ← shared styles, variables, components
│   ├── desktop.css     ← min-width: 900px overrides
│   └── mobile.css      ← max-width: 899px overrides
├── assets/
│   ├── images/
│   │   ├── logo.png            ← replace with real logo
│   │   ├── partner-1.png       ← replace with real partner logo
│   │   ├── partner-2.png
│   │   ├── partner-3.png
│   │   └── partner-4.png
│   └── docs/
│       └── preisliste.pdf      ← replace with real price list PDF
└── README.md
```

## Swapping in real assets

### Logo & partner images

Replace the placeholder 1×1 transparent PNGs in `assets/images/` with the
real files **keeping the same filenames**. Recommended formats: PNG or WebP.

| File | Recommended size | Notes |
|------|-----------------|-------|
| `logo.png` | 80×80 px (2×: 160×160) | Square or circle crop |
| `partner-*.png` | 320×160 px max | Horizontal logos work best |

If a partner logo has a white background it will blend into the card.
Use a transparent-background PNG so the hover de-grayscale effect looks clean.

### Price list PDF

Replace `assets/docs/preisliste.pdf` with the real PDF.
The filename must stay `preisliste.pdf`, or update the `src` attribute in the
`<iframe>` inside `index.html` (search for `preisliste.pdf` — two occurrences).

## CSS breakpoints

| File | Controls |
|------|----------|
| `css/mobile.css` | `@media (max-width: 899px)` — phones & small tablets |
| `css/desktop.css` | `@media (min-width: 900px)` — tablets landscape & up |

`css/base.css` contains all base styles, CSS custom properties (colors, radii,
shadows), and layout that applies to every viewport.

To change the accent color, edit `--pft-accent` in `base.css`:

```css
--pft-accent: #0b57d0;   /* change this hex value */
```

## Serving locally

Any static file server works. Quick options:

```bash
# Python 3
python3 -m http.server 8080 --directory Landing/

# Node (npx)
npx serve Landing/

# VS Code: install the "Live Server" extension, right-click index.html → "Open with Live Server"
```

Then open `http://localhost:8080` in your browser.

## Deployment

Drop the entire `Landing/` folder onto any static host (Netlify, GitHub Pages,
Cloudflare Pages, etc.). No build step required.
