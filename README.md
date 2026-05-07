# V'NSPIRE — Corporate Website

Bilingual (English/Japanese) corporate brand site. Built as a single-page static HTML site with inline CSS/JS. No build step, no dependencies, deploy to any static host.

## Project Structure

```
vnspire/
├── design-mockup.html     # Main site — hero, services, stats, timeline, careers, contact, footer
├── privacy-policy.html    # Standalone privacy policy page
├── terms-conditions.html  # Standalone terms & conditions page
├── logo_vnspire.png       # Navbar logo (light background, 78px max)
├── hero.mp4               # Fullscreen hero background video (loop, autoplay)
└── vnspire-content.md     # Archived content reference (scraped from archive.org)
```

## Design System

### Color Palette

| Token         | Hex      | Usage                         |
|---------------|----------|-------------------------------|
| Primary       | `#19596c`| Headings, nav links, accents  |
| Secondary     | `#22728e`| Subtle gradients, hover states|
| Accent Blue   | `#3674a3`| Gradient mid-point, links     |
| Accent Green  | `#249c6c`| Gradient end-point, CTAs      |
| Background    | `#f0f7fa`| Page background, light tone   |

### Layout

| Element              | Behavior                                              |
|----------------------|-------------------------------------------------------|
| Navbar               | Fixed top, transparent → solid on scroll              |
| Logo                 | `clamp(54px, 5.5vw, 78px)` height                     |
| Hero Content (CTA)   | Mobile/tablet: 25px left · Desktop (1024px+): 400px   |
| Hero Heading         | `clamp(32px, 4.5vw, 64px)`, gradient text             |
| Max Content Width    | 1280px centered                                        |
| Responsive           | Fluid typography + hamburger menu < 768px             |

### Sections (in order)

1. **Hero** — Fullscreen video background, heading, tagline, search bar, CTA buttons
2. **Services** — 6 Drupal-inspired service cards (row of 3 on desktop, stack on mobile)
3. **Other Services** — Expanded service offerings in grid layout
4. **Stats Counter** — Animated counters (Projects, Clients, Team Members, Countries)
5. **What We Believe In** — Alternating timeline with 4 core values (Innovation, Quality, Collaboration, Integrity)
6. **Careers** — Tabbed interface (Open Positions, Culture, Benefits)
7. **Contact** — Form with math CAPTCHA, submitted via Formsubmit.co
8. **Footer** — Logo, about text, address, social links (Facebook, LinkedIn), Privacy/Terms links

### Bilingual System

- Default: English
- Toggle via navbar button — swaps content using `data-en` / `data-ja` attributes
- Form placeholders and captcha text also switch via JS
- No separate HTML files per language

## Deployment

### Option 1: Vercel (recommended)

```bash
npm i -g vercel
vercel --prod
```

No configuration needed — Vercel auto-detects static HTML. Point to `https://github.com/willfadeneva/vnspire` from the Vercel dashboard for auto-deploys on push.

### Option 2: Cloudflare Tunnel (dev preview)

```bash
npx serve . -l 3000
cloudflared tunnel --url http://localhost:3000
```

### Option 3: Any static host (Netlify, GitHub Pages, S3)

Just serve the root directory — no build step required.

## Links

- **GitHub**: https://github.com/willfadeneva/vnspire
- **Vercel**: https://vnspire.vercel.app (post-deploy)
- **Contact form**: Submits to `info@vnspire.com` via Formsubmit.co
