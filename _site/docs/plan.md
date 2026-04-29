# Ha Tran CV Website — Design & Content Plan

**Goal:** Transform the existing Minima-themed GitHub Pages site into a standout CV portfolio that immediately impresses potential employers.

Ha Tran's content is genuinely exceptional (PhD, 7 projects, 10+ awards, 5 CAD tools), but the default Minima theme buries it. This plan removes Minima entirely and replaces it with fully custom `_layouts` and a CSS overhaul — deep navy + amber color palette, hero section, project cards, timeline education, skill badges — all pure HTML/CSS/Jekyll with zero JS dependencies, fully GitHub Pages compatible.

---

## Color Palette

| Role | Color | Hex |
|---|---|---|
| Primary | Deep navy | `#1B3A5C` |
| Accent | Amber/orange | `#E8860A` |
| Surface | Light grey-white | `#F4F6F9` |
| Text | Dark charcoal | `#1C1C2E` |
| Links/CTAs | Bright blue | `#2E7DC5` |

---

## Phase 1 — Foundation *(everything else depends on this)*

1. Remove `theme: minima` from `_config.yml` — no Minima dependency
2. Delete root `style.css`, create `assets/css/style.css` — full custom stylesheet
3. Create `_layouts/default.html` — custom sticky nav header + footer with LinkedIn/email icons
4. Create `_layouts/home.html` extending default — needed for hero treatment
5. Define CSS custom properties: color palette, typography scale, spacing system

> **Typography:** Google Fonts (Inter) via CDN, system font stack fallback. Clean, modern, engineering-appropriate.

---

## Phase 2 — Home Page (`index.md`)

5. **Hero section** — full-width navy banner, Ha Tran's name large, engineering title subtitle, two CTA buttons: "Download CV" and "View Projects". **Gracefully degrades without headshot**: when image is absent the layout shifts to centered text-only hero — no broken image or empty gap
6. **About strip** — headshot left (hidden via CSS if image absent), punchy 3-sentence bio right; bio takes full width if no headshot
7. **"What I Do" cards** — 3 icon tiles: Mechanical Design · Research & Analysis · Systems Integration
8. **Credential highlights bar** — PhD · 5 Industry Projects · 5 CAD Platforms · NZ Citizen / Open to Relocation

---

## Phase 3 — Projects Page (`projects.md`)

9. **Restyled accordions** — keep `<details>`/`<summary>` structure, fully restyle: navy header bar with amber toggle indicator, project thumbnail, tech tag chips visible on the summary line
10. Summary line shows title + 1-line scope + tags — scannable without opening; smooth expand animation via CSS `max-height` transition
11. Industry tags for visual scanning: `Industrial` · `Research` · `Marine` · `Aerospace`
12. Fix typos: "intergrated" → "integrated", "nornal" → "normal"

---

## Phase 4 — Skills Page (`skills.md`)

13. Core competencies → **2-column chip/badge grid**
14. Software tools → **styled pill badges** (Solid Edge, ANSYS, SolidWorks, etc.)
15. Capability paragraphs → **cards with amber left-border accent**

---

## Phase 5 — Education Page (`education.md`)

16. Degrees → **CSS vertical timeline** (year on left, institution + degree right)
17. Awards → **badge list with year chips**, visually distinct from body text
18. Thesis titles → blockquote-styled callouts

---

## Phase 6 — Contact Page (`contact.md`)

19. Centered card layout with icons for each contact method
20. Large prominent "Download CV" button
21. "Open to relocation" callout badge

---

## Phase 7 — Polish

22. Mobile-responsive nav (pure CSS hamburger)
23. Hover/focus states on all interactive elements
24. Add `favicon` and social meta tags to `_config.yml`

---

## File Inventory

| Action | File |
|---|---|
| Modify | `_config.yml` — add favicon/meta |
| Rewrite | `index.md` — hero + highlights |
| Rewrite | `projects.md` — card grid + typo fixes |
| Rewrite | `skills.md` — badge/chip layout |
| Rewrite | `education.md` — timeline layout |
| Rewrite | `contact.md` — icon card layout |
| Delete | `style.css` (root) |
| Create | `assets/css/style.css` — full custom stylesheet |
| Create | `_layouts/default.html` |
| Create | `_layouts/home.html` |

---

## Decisions / Scope

- **No Minima theme** — fully custom `_layouts/default.html` and `_layouts/home.html`
- Pure HTML/CSS + Jekyll Liquid only — **no JavaScript frameworks**
- Google Fonts (Inter) via CDN, system font fallback
- **Accordions kept** on projects page — restyled, not replaced with card grid
- **Hero degrades gracefully** — text-only layout when headshot image is absent
- Existing content kept intact — **restructure and restyle only**
- Actual image/video/PDF asset uploads are **out of scope** — assets must be supplied separately

---

## Verification Checklist

- [ ] `bundle exec jekyll serve` — all 5 pages render without error
- [ ] Browser DevTools confirms `style.scss` is loading (currently broken at root)
- [ ] Mobile viewport at 375px — nav collapses, cards stack correctly
- [ ] Mobile viewport at 768px — intermediate layout checks out
- [ ] All CTA links resolve: CV download, LinkedIn, Projects anchor
- [ ] All 7 project cards expand/collapse correctly
- [ ] Headshot gracefully degrades if image not yet uploaded

---

## Resolved Decisions

| Decision | Choice |
|---|---|
| Theme | Remove Minima entirely — fully custom `_layouts` |
| Project page UX | Keep `<details>` accordions — restyle with CSS |
| Headshot | Hero degrades gracefully to text-only; no placeholder needed |
