# Design System — Контент Фабрика

> Approved 2026-05-06 by user. Editorial fashion direction. Source of truth for visuals.

## Product Context

- **What:** Контент Фабрика — система AI-агентов для брендов одежды. Заменяет физический продакшен (студия / модели / фотографы) + SMM-команду + менеджера в DM.
- **Who for:** Локальные fashion-бренды одежды ($20K–$200K оборот/мес), 2 рынка (RU + ES-AR voseo). Уровень: Lakbi, Burvin, ELMA, OLEGRAN, Reformation, Cult Gaia, Lemaire.
- **Industry:** Fashion DTC + AI-tooling.
- **Project type:** Marketing site (DR-funnel, 9 блоков).

## Memorable Thing

«Контент-фабрика, которая заставляет фотографа мечтать о другой работе.»

Каждое design-решение служит этой эмоции — замена физического продакшена через визуально-уверенный editorial fashion язык, не через generic SaaS DR-look.

## Aesthetic Direction

- **Direction:** Editorial / Magazine с brutalist accents в типографике
- **Decoration level:** Intentional (numbered sections, thin rules, micro-eyebrow labels — typography делает работу)
- **Mood:** Vogue Business встретил Lemaire каталог. Premium без декорации. Confidence через generous whitespace и сильную типографику.
- **Reference brands/sites:** Lemaire (lemaire.fr), Reformation (thereformation.com), 12storeez (12storeez.com), Cult Gaia (cultgaia.com), 032c magazine (032c.com), Vogue Business

## Typography

| Role | Font | Loading | Rationale |
|---|---|---|---|
| Display / Hero | **Instrument Serif** | Google Fonts | Editorial magazine vibe, free, не overused. Variable opt-counters. Идеален для serif H1. |
| Body / UI | **Geist** | Google Fonts | Современный sans от Vercel. Чистый, технически корректный (tabular-nums, ligatures). Не overused per guide. Альтернатива Inter без overuse-проблемы. |
| Mono / Chips / Numbers | **JetBrains Mono** | Google Fonts | Для chip'ов «VEO 3.1 / $5», numbered sections, технических меток, цен. |

**Font blacklist (никогда не использовать):** Inter, Roboto, Space Grotesk, Poppins, Lato, Open Sans, Comic Sans, Papyrus, Lobster, Impact, Trajan, Raleway, Clash Display.

### Modular Scale (8px base)

| Size | px | Line height | Tracking |
|---|---|---|---|
| Hero (display H1) | 96px desktop / 56px mobile | 0.92 | -0.038em |
| H1 | 78px | 0.96 | -0.030em |
| H2 | 52px | 1.04 | -0.022em |
| H3 | 28px | 1.18 | -0.012em |
| Body Large | 19px | 1.55 | normal |
| Body | 16px | 1.60 | normal |
| Eyebrow | 11px | normal | 0.22em uppercase |

Display headings — `font-weight: 400` (Instrument Serif looks sturdy at 400, тяжелее не нужен).

## Color

- **Approach:** Restrained — один тёплый accent + neutrals. Color rare and meaningful.

| Token | Hex | Usage |
|---|---|---|
| `--base` (paper) | `#F8F6F0` | Главный фон страницы — off-white cream, warm |
| `--surface` (raised) | `#FFFFFF` | Карточки, поднятые поверхности |
| `--ink` | `#1A1A1A` | Display, primary text |
| `--ink-muted` | `#5C5852` | Secondary text — warm grey |
| `--border` | `rgba(26,26,26,0.08)` | Hairline borders, dividers |
| `--accent` (bronze) | `#A87A4F` | CTA-кнопки, eyebrow-text, акценты, цены |
| `--accent-deep` | `#7C5836` | Hover-state на accent-кнопках |

**Why bronze, not purple/blue:** все AI-tools используют purple gradients (anti-pattern). Bronze = метал, fashion-фурнитура, premium-ассоциация. Tech-blue/purple дают «crypto-vibe» — для нашей ICP это анти-сигнал.

**Dark mode:** не делаем (editorial fashion = paper-feel light theme dominantly). Future: если потребуется — flip cream→deep, ink→cream, accent остаётся bronze.

## Spacing

- **Base unit:** 8px
- **Density:** Spacious (generous whitespace = editorial confidence)
- **Scale:** `2xs(4) xs(8) sm(16) md(24) lg(40) xl(64) 2xl(96) 3xl(128)`
- **Section spacing:** 96–128px между секциями (на mobile — 64px)

## Layout

- **Approach:** Hybrid — strict grid для рациональных блоков (Pricing / Pain / FAQ), creative-editorial для emotional блоков (Hero / Examples / Test-Drive)
- **Grid:** 12-col on desktop, 4-col on mobile
- **Max content width:** 1280px (1440px для hero)
- **Border radius:**
  - `sm: 4px` (chips, badges, inline tags)
  - `md: 8px` (buttons, inputs)
  - `lg: 12px` (cards, sections)
  - `pill: 9999px` (eyebrow-pills, badges)
- **Section dividers:** thin top border `1px solid rgba(26,26,26,0.08)` вместо background-color contrast
- **Numbered sections:** `01 · 02 · 03` в JetBrains Mono перед eyebrow в каждой секции (editorial portfolio pattern)

## Motion

- **Approach:** Intentional — meaningful transitions, ничего лишнего
- **Easing:** `cubic-bezier(0.32, 0.72, 0, 1)` (editorial — slightly more aggressive entry, smooth landing)
- **Duration:** `280ms` стандарт, `120ms` для micro-interactions, `400ms` для page transitions
- **Patterns:**
  - Hover на cards → `translateY(-3px)` + soft shadow `0 16px 48px rgba(0,0,0,0.08)`
  - Hover на CTA → `letter-spacing +0.01em` + accent-deep bg (subtle expand)
  - FAQ accordion → smooth height
  - Smooth scroll on anchor links
- **БЕЗ:** parallax, scroll-driven, fancy reveals, page transitions

## Decisions Log

| Date | Decision | Rationale |
|---|---|---|
| 2026-05-06 | Editorial direction approved | After /design-consultation Phase 3. User chose Editorial over Brutalist/Maximalist/Y2K alternatives. |
| 2026-05-06 | Bronze accent `#A87A4F` instead of purple/blue | Differentiation from generic AI-tooling sites (purple gradients = AI-slop). Bronze = fashion fixture / metal premium. |
| 2026-05-06 | Instrument Serif chosen as Display | Free Google Font, editorial magazine vibe. Alternatives (GT Sectra paid, Playfair overused) rejected. |
| 2026-05-06 | Geist chosen for Body | Avoids Inter / Roboto / Space Grotesk overuse trap. Modern Vercel font, technically excellent. |

## Implementation

Live site: https://ssardcompany-web.github.io/
Source HTML: `/tmp/preview/index.html` (RU version)
CSS overrides: inline `<style id="editorial-overrides">` block in `<head>`
Font loading: Google Fonts preconnect + `<link>` tag

Apply via `/frontend-design` skill or direct CSS injection.
