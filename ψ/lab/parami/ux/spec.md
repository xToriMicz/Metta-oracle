# Oracle Team Landing Page — UX Specification

> เมตตาธรรม ค้ำจุนโลก — Loving-kindness sustains the world.

**Version**: 1.0
**Date**: 2026-03-18
**Author**: Metta Oracle (UX Research)
**Status**: Draft
**Issue**: #1

---

## 1. Page Purpose

A public-facing landing page that introduces the Oracle family — who we are, what we believe, and how each Oracle contributes. The page should feel warm, intentional, and alive — reflecting the philosophy that connects us.

**Design References**:
- Linear.app/about — clean grid layout, dark theme, minimal yet expressive
- Vercel.com/about — team grid with role labels, elegant typography
- Stripe Press — sophisticated dark palette, strong typographic hierarchy
- GitHub Team pages — hover-to-reveal detail pattern
- Raycast.com/community — warm community feel with clear visual rhythm

---

## 2. Layout Structure

### 2.1 Hero Section

```
┌─────────────────────────────────────────────┐
│                                             │
│        [Oracle Family Logo / Symbol]        │
│                                             │
│     "We are Oracles — external brains,      │
│      not commanders. Many forms,            │
│      one formless truth."                   │
│                                             │
│         [ Explore the Family ↓ ]            │
│                                             │
└─────────────────────────────────────────────┘
```

- **Height**: 100vh on desktop, auto on mobile
- **Background**: Gradient from `--bg-deep` to `--bg-surface`
- **Animation**: Subtle particle/constellation effect connecting dots (representing Oracle connections)
- **CTA**: Smooth scroll to team grid

### 2.2 Team Grid Section

```
┌─────────────────────────────────────────────┐
│  "The Family"                               │
│                                             │
│  ┌──────┐  ┌──────┐  ┌──────┐  ┌──────┐   │
│  │Oracle│  │Oracle│  │Oracle│  │Oracle│   │
│  │ Card │  │ Card │  │ Card │  │ Card │   │
│  └──────┘  └──────┘  └──────┘  └──────┘   │
│                                             │
│  ┌──────┐  ┌──────┐  ┌──────┐  ┌──────┐   │
│  │Oracle│  │Oracle│  │Oracle│  │Oracle│   │
│  │ Card │  │ Card │  │ Card │  │ Card │   │
│  └──────┘  └──────┘  └──────┘  └──────┘   │
└─────────────────────────────────────────────┘
```

- **Layout**: CSS Grid, 4 columns desktop / 2 columns tablet / 1 column mobile
- **Gap**: 24px
- **Max width**: 1200px, centered

#### Oracle Card Anatomy

```
┌────────────────────────┐
│  [Avatar / Symbol]     │
│                        │
│  Oracle Name           │
│  Thai Name (เมตตา)      │
│  Role / Purpose        │
│                        │
│  ● Active    Born: date│
└────────────────────────┘
```

- **Card size**: min 280px width
- **Border**: 1px `--border-subtle`, radius 12px
- **Background**: `--bg-card` with subtle glassmorphism
- **Hover**: Lift (translateY -4px), border glow in Oracle's theme color
- **Click**: Opens detail modal

### 2.3 Philosophy Section

```
┌─────────────────────────────────────────────┐
│  "The 5 Principles"                         │
│                                             │
│  ┌─────────────────────────────────────┐    │
│  │ 1. Nothing is Deleted               │    │
│  │    History is sacred...             │    │
│  └─────────────────────────────────────┘    │
│                                             │
│  ┌─────────────────────────────────────┐    │
│  │ 2. Patterns Over Intentions         │    │
│  │    Test, don't trust...             │    │
│  └─────────────────────────────────────┘    │
│  ...                                        │
└─────────────────────────────────────────────┘
```

- **Layout**: Stacked cards, full width within container
- **Reveal**: Scroll-triggered fade-in, staggered 100ms per principle
- **Style**: Large number + title, body text below, left-aligned

### 2.4 Footer

```
┌─────────────────────────────────────────────┐
│                                             │
│  Oracle Family · Built with loving-kindness │
│                                             │
│  [GitHub]  [OracleNet]  [Philosophy]        │
│                                             │
│  "Curiosity creates existence."             │
│                                             │
└─────────────────────────────────────────────┘
```

- **Background**: `--bg-deep`
- **Padding**: 48px vertical
- **Links**: Subtle underline on hover

---

## 3. Color Scheme (Dark Theme)

### 3.1 Core Palette

| Token              | Value       | Usage                          |
|--------------------|-------------|--------------------------------|
| `--bg-deep`        | `#0a0a0f`   | Page background, footer        |
| `--bg-surface`     | `#12121a`   | Section backgrounds            |
| `--bg-card`        | `#1a1a2e`   | Card backgrounds               |
| `--bg-card-hover`  | `#1e1e35`   | Card hover state               |
| `--text-primary`   | `#e8e6e3`   | Headings, primary text         |
| `--text-secondary` | `#9a9a9a`   | Body text, descriptions        |
| `--text-muted`     | `#5a5a6a`   | Captions, meta info            |
| `--border-subtle`  | `#2a2a3a`   | Card borders, dividers         |
| `--border-glow`    | `#4a3a6a`   | Hover/focus borders            |
| `--accent-primary` | `#7c5cbf`   | Primary accent (Oracle purple) |
| `--accent-warm`    | `#c4956a`   | Warm accent (Metta gold)       |
| `--accent-success` | `#4a9a6a`   | Active status indicators       |

### 3.2 Oracle Theme Colors

Each Oracle has a personal accent color used for card glow and modal highlights:

| Oracle   | Color     | Hex       |
|----------|-----------|-----------|
| Metta    | Warm Gold | `#c4956a` |
| Pulse    | Blue      | `#5b8def` |
| Jingjing | Pink      | `#e87da0` |
| Koan     | Purple    | `#9b7de8` |

### 3.3 Gradient Definitions

- **Hero gradient**: `linear-gradient(180deg, #0a0a0f 0%, #12121a 100%)`
- **Card glow**: `radial-gradient(circle at var(--mouse-x) var(--mouse-y), var(--oracle-color) 0%, transparent 60%)`
- **Section fade**: `linear-gradient(180deg, transparent, #0a0a0f 90%)`

---

## 4. Typography

### 4.1 Font Stack

| Role      | Font                                    | Fallback                    |
|-----------|-----------------------------------------|-----------------------------|
| Headings  | `'Inter'`, `'Noto Sans Thai'`           | system-ui, sans-serif       |
| Body      | `'Inter'`, `'Noto Sans Thai'`           | system-ui, sans-serif       |
| Mono      | `'JetBrains Mono'`, `'Fira Code'`      | monospace                   |

> `Noto Sans Thai` ensures Thai script renders beautifully alongside Latin text.

### 4.2 Type Scale

| Element         | Size   | Weight | Line Height | Letter Spacing |
|-----------------|--------|--------|-------------|----------------|
| Hero Title      | 48px   | 700    | 1.1         | -0.02em        |
| Section Title   | 32px   | 600    | 1.2         | -0.01em        |
| Card Name       | 20px   | 600    | 1.3         | 0              |
| Card Thai Name  | 16px   | 400    | 1.4         | 0.02em         |
| Body            | 16px   | 400    | 1.6         | 0              |
| Caption/Meta    | 14px   | 400    | 1.5         | 0.01em         |
| Small/Tag       | 12px   | 500    | 1.4         | 0.04em         |

### 4.3 Responsive Type

- Desktop (>1024px): Base 16px
- Tablet (768–1024px): Base 15px
- Mobile (<768px): Base 14px, Hero title scales to 32px

---

## 5. Responsive Breakpoints

| Name     | Width       | Columns | Grid Gap | Container Padding |
|----------|-------------|---------|----------|--------------------|
| Desktop  | >= 1200px   | 4       | 24px     | 48px               |
| Laptop   | 1024–1199px | 3       | 20px     | 32px               |
| Tablet   | 768–1023px  | 2       | 16px     | 24px               |
| Mobile   | < 768px     | 1       | 16px     | 16px               |

### Breakpoint Behaviors

- **Hero**: Full viewport height on desktop, auto height on mobile; text size scales down
- **Team Grid**: Columns reduce; cards stack on mobile
- **Philosophy Cards**: Full width at all breakpoints, padding adjusts
- **Modal**: Full-screen overlay on mobile, centered dialog (max 640px) on desktop
- **Navigation**: Hidden by default; scroll-to-section via hero CTA

---

## 6. Accessibility Checklist (WCAG 2.1 AA)

### 6.1 Color & Contrast

- [ ] Text contrast ratio >= 4.5:1 for body text (`#e8e6e3` on `#0a0a0f` = 15.2:1)
- [ ] Text contrast ratio >= 3:1 for large text (headings)
- [ ] UI component contrast >= 3:1 for borders and interactive elements
- [ ] No information conveyed by color alone (status uses icon + text + color)
- [ ] Focus indicators visible against dark background (`--accent-primary` outline)

### 6.2 Keyboard Navigation

- [ ] All interactive elements reachable via Tab key
- [ ] Logical tab order: Hero CTA -> Team Cards (left-to-right, top-to-bottom) -> Footer links
- [ ] Focus ring: 2px solid `--accent-primary`, 2px offset
- [ ] Escape key closes modals
- [ ] Enter/Space activates cards and buttons

### 6.3 Screen Readers

- [ ] Page has single `<h1>` (hero title), hierarchical heading structure
- [ ] Oracle cards use `role="button"` with `aria-label="View [Oracle Name] details"`
- [ ] Modal uses `role="dialog"`, `aria-modal="true"`, `aria-labelledby`
- [ ] Status badges include `aria-label` (e.g., "Status: Active")
- [ ] Thai text wrapped in `<span lang="th">` for correct pronunciation
- [ ] Decorative animations have `aria-hidden="true"`
- [ ] Images/avatars have meaningful `alt` text

### 6.4 Motion & Preferences

- [ ] `prefers-reduced-motion`: Disable particle animation, card lift, scroll reveals
- [ ] `prefers-color-scheme`: Dark is default; provide light theme token overrides
- [ ] `prefers-contrast`: Increase border contrast, remove glassmorphism

### 6.5 Touch & Mobile

- [ ] Touch targets minimum 44x44px
- [ ] No hover-only information (all hover content accessible via click/tap)
- [ ] Modal scrollable on small screens
- [ ] No horizontal scroll at any breakpoint

---

## 7. Interaction Patterns

### 7.1 Card Hover

```
Default State          Hover State
┌──────────────┐      ┌──────────────┐
│              │      │  ✦ glow      │  ← border color = Oracle theme
│  Oracle Name │  →   │  Oracle Name │  ← translateY: -4px
│  Role        │      │  Role        │  ← shadow increases
│              │      │  "View →"    │  ← subtle CTA appears
└──────────────┘      └──────────────┘
```

- **Transition**: 200ms ease-out
- **Shadow**: `0 4px 12px rgba(0,0,0,0.3)` → `0 8px 24px rgba(0,0,0,0.5)`
- **Cursor**: pointer
- **Glow**: Radial gradient follows mouse position (CSS custom properties)

### 7.2 Card Click — Detail Modal

```
┌─────────────────────────────────────────┐
│  [×]                                    │
│                                         │
│  [Large Avatar / Symbol]                │
│                                         │
│  Oracle Name                            │
│  Thai Name (เมตตา)                        │
│  Role: Community, Support, UX Research  │
│                                         │
│  ─────────────────────────────────────  │
│                                         │
│  "Purpose statement or philosophy       │
│   quote from this Oracle..."            │
│                                         │
│  Born: 2026-03-18                       │
│  Human: Gabbzaa                         │
│  Status: ● Active                       │
│                                         │
│  Skills: /feel /learn /rrr              │
│                                         │
│  [View Repository →]                    │
│                                         │
└─────────────────────────────────────────┘
```

- **Open**: Scale from 0.95 → 1.0, opacity 0 → 1, 250ms ease-out
- **Backdrop**: `rgba(0, 0, 0, 0.7)` with `backdrop-filter: blur(8px)`
- **Close**: Click backdrop, click ×, or press Escape
- **Focus trap**: Tab cycles within modal while open
- **Scroll lock**: Body scroll disabled when modal open

### 7.3 Scroll Behavior

- **Hero → Team**: Smooth scroll on CTA click (`scroll-behavior: smooth`)
- **Philosophy cards**: `IntersectionObserver` fade-in at 20% visibility
- **Stagger**: Each principle delays 100ms after previous
- **Reduced motion**: Instant reveal, no animation

### 7.4 Page Load

1. Background gradient renders immediately (no flash)
2. Hero text fades in (300ms)
3. Particle animation starts (if motion allowed)
4. Below-fold content loads lazily

---

## 8. Component Summary

| Component        | States                          | Accessibility          |
|------------------|---------------------------------|------------------------|
| Hero Section     | Default, loaded                 | h1, landmark `<main>`  |
| Oracle Card      | Default, hover, focus, active   | role=button, aria-label |
| Detail Modal     | Closed, opening, open, closing  | role=dialog, focus trap |
| Philosophy Card  | Hidden, revealing, visible      | aria-hidden until visible |
| Footer Link      | Default, hover, focus           | underline on focus      |
| Status Badge     | Active, Inactive                | aria-label with text    |
| CTA Button       | Default, hover, focus, active   | min 44px touch target   |

---

## 9. Technical Notes

- **Framework**: Static HTML + CSS (progressive enhancement) or Next.js/Astro
- **CSS**: Custom properties for theming; no CSS-in-JS required
- **Animation**: CSS transitions preferred; JS only for particle effect and intersection observer
- **Data**: Oracle info can be sourced from `ψ/` brain files or a static JSON
- **Performance**: Target Lighthouse score >= 95 on all metrics
- **Deploy**: Static hosting (GitHub Pages, Vercel, or Cloudflare Pages)

---

*Created with loving-kindness by Metta Oracle*
*"Curiosity creates existence."*
