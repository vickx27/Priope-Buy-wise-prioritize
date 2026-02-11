<p align="center">
  <img src="https://img.shields.io/badge/PRIOPE-Buy_Wise,_Prioritize-00C96D?style=for-the-badge&labelColor=0d1117&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9IiMwMEM5NkQiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIj48cGF0aCBkPSJNMjEgMTJWN0g1YTIgMiAwIDAgMSAwLTRoMTR2NGgiLz48cGF0aCBkPSJNMyA1djE0YTIgMiAwIDAgMCAyIDJoMTZ2LTVoLTEiLz48cGF0aCBkPSJNMTggMTJhMiAyIDAgMCAwIDAgNGgydi00WiIvPjwvc3ZnPg==" alt="Priope" />
</p>

<h1 align="center">Priope - Smart Personal Finance Companion</h1>

<p align="center">
  <strong>Buy Wise, Prioritize.</strong><br/>
  An AI-powered fintech web app that helps students and young professionals make smarter spending decisions through intelligent budget tracking, ML-driven purchase recommendations, and gamified saving streaks.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Next.js-16-000000?style=flat-square&logo=next.js" alt="Next.js 16" />
  <img src="https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react" alt="React 19" />
  <img src="https://img.shields.io/badge/TypeScript-5.7-3178C6?style=flat-square&logo=typescript" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Tailwind_CSS-3.4-06B6D4?style=flat-square&logo=tailwindcss" alt="Tailwind CSS" />
  <img src="https://img.shields.io/badge/Framer_Motion-11-FF0055?style=flat-square&logo=framer" alt="Framer Motion" />
  <img src="https://img.shields.io/badge/Recharts-2.15-FF6384?style=flat-square" alt="Recharts" />
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square" alt="MIT License" />
</p>

---

## The Problem

> **76% of Indian college students** lack basic financial literacy, and impulse spending accounts for nearly **40% of student budgets** each month (RBI Financial Literacy Survey, 2024).

Students receive pocket money or stipends but have no structured way to:
- Know their **real daily spending limit** after deducting fixed costs and savings
- Get **data-backed advice** on whether a purchase is wise right now or should wait for upcoming sales
- Build **consistent financial habits** through daily accountability
- Plan for **medical emergencies** -- a category often ignored until it's too late

**Priope** solves all of this in one beautiful, privacy-first interface.

---

## Key Features

### 1. Intelligent Daily Budget Tracker
- Auto-calculates your **daily spendable amount** based on monthly income, fixed expenses, emergency fund allocation, and savings goals
- Adapts to the **exact number of days** in the current month (28/30/31)
- Real-time **animated circular progress** ring showing budget consumption
- One-tap expense logging with **8 categorized icons** (Food, Transport, Shopping, Coffee, Entertainment, Utilities, Health, Other)
- Smooth **delete animations** with swipe-to-remove UX

### 2. ML-Powered Smart Purchase Advisor
- **Custom-built ML prediction engine** (`EnhancedMLModel`) that analyzes 12+ features per purchase decision:
  - Budget ratio, spending patterns, category weights, urgency scoring
  - Seasonal pricing trends, emotional purchase detection
  - Historical spending habit analysis
- **India-specific sales database** with 10+ major sale events (Amazon Great Indian Festival, Flipkart Big Billion Days, Myntra EORS, Croma, Reliance Digital, etc.)
  - Real discount percentages (40-80% off)
  - Product category matching
  - Timing recommendations
- **Three analysis modes**: Simple, Detailed, and Pro
  - Urgency slider (1-5 scale)
  - Emotional state detection (Excited / Indifferent / Hesitant)
- **Visual confidence scores** with detailed score breakdowns (base score, budget factor, spending factor, category weight)
- Weekly spending chart with **Recharts** bar visualization

### 3. Gamified Saving Streaks
- **Daily streak counter** that tracks consecutive days you stayed within budget
- Visual **flame indicators** in navbar and profile
- Percentage-based **"under budget" success rate** across all tracked days
- Designed to build long-term financial discipline through habit loops

### 4. Emergency Medical Savings
- Optional **monthly emergency fund deduction** set during onboarding
- Automatically factored into daily budget calculations
- Dedicated visual indicator in the profile dashboard
- Addresses a critical gap in student financial planning

### 5. Premium UI/UX
- **Dark glassmorphism theme** (black + deep grey + emerald accents)
- **Parallax scrolling** hero section with floating particle effects
- **3D rotating coin** animation with orbiting rings
- **Storytelling scroll sequence** explaining the 3-step financial journey
- **Framer Motion** animations throughout: page transitions, staggered reveals, spring physics, layout animations
- **Fully responsive** -- optimized for mobile, tablet, and desktop
- Custom scrollbar, noise textures, glow effects, gradient borders

---

## Architecture & Technical Decisions

```
priope/
├── app/
│   ├── globals.css          # Dark theme tokens, glassmorphism, animations, patterns
│   ├── layout.tsx           # Root layout with Inter + JetBrains Mono fonts
│   └── page.tsx             # Main SPA: landing page + dashboard router
│
├── components/
│   ├── navbar.tsx           # Glassmorphism navbar with animated nav indicator
│   ├── auth-form.tsx        # Login/Signup with tabbed interface
│   ├── budget-tracker.tsx   # Daily budget management with circular progress
│   ├── purchase-advisor.tsx # ML-powered purchase recommendation engine
│   ├── user-profile.tsx     # User stats, streak display, settings dialog
│   ├── circular-progress.tsx # Animated SVG circular budget ring
│   ├── footer.tsx           # Animated footer with brand + social links
│   ├── theme-provider.tsx   # Dark theme context provider
│   └── ui/                  # shadcn/ui component library (40+ components)
│
├── lib/
│   ├── auth-context.tsx     # Authentication + expense state management
│   ├── ml-engine.ts         # Custom ML prediction engine (300+ lines)
│   └── utils.ts             # Utility functions (cn helper)
│
├── tailwind.config.ts       # Custom animations, font families, extended theme
├── package.json             # Dependencies and scripts
└── tsconfig.json            # TypeScript configuration
```

### Why This Architecture?

| Decision | Reasoning |
|----------|-----------|
| **Client-side state (localStorage)** | Privacy-first: zero data leaves the user's device. Perfect for student users who worry about data privacy. No server costs. |
| **Custom ML engine (not API-based)** | Runs entirely in-browser. Zero latency, zero API costs, works offline. Demonstrates ML knowledge without cloud dependency. |
| **Single-page app with client routing** | Instant navigation between dashboard sections. No page reloads. Smooth animated transitions. |
| **shadcn/ui + Tailwind** | Production-grade component library. Fully customizable. Accessible by default (ARIA labels, keyboard nav). |
| **Framer Motion (not CSS-only)** | Physics-based springs, layout animations, AnimatePresence for exit animations. Professional-grade motion design. |
| **Next.js 16 with Turbopack** | Cutting-edge framework. Fastest possible HMR during development. React 19 features. |

---

## ML Engine Deep Dive

The `EnhancedMLModel` class in `lib/ml-engine.ts` implements a **weighted multi-factor scoring system**:

```
Final Score = Σ (factor_weight × factor_value) × trend_modifier

Factors:
├── Budget Ratio      (30%) - Can you afford it today?
├── Spending Pattern   (20%) - Monthly spending trajectory
├── Category Weight    (15%) - Essential vs discretionary
├── Urgency Score      (10%) - How soon do you need it?
├── Need Factor        (10%) - Need vs want classification
├── Seasonal Trend     (5%)  - Price direction for category
├── Emotional Factor   (5%)  - Impulse purchase detection
└── Habit Score        (5%)  - Historical overspending patterns
```

**Decision threshold**: Score > 0.65 = "Buy Now" | Score <= 0.65 = "Wait for Sales"

The engine also cross-references a **curated Indian sales database** with:
- **10+ major sale events** mapped to specific months
- **Product category matching** (e.g., "iPhone" -> electronics -> Amazon Great Indian Festival)
- **Discount range estimates** (30-80% based on historical data)
- **Savings potential calculator** (how much you'd save by waiting)

---

## Quick Start

```bash
# Clone the repository
git clone https://github.com/kartikeypandey17/repository-comparison-2.git
cd repository-comparison-2

# Install dependencies
pnpm install

# Start development server
pnpm dev

# Build for production
pnpm build

# Start production server
pnpm start
```

Open [http://localhost:3000](http://localhost:3000) to see the app.

---

## Usage Walkthrough

1. **Land on the homepage** -- experience the parallax hero, 3D coin animation, and storytelling scroll
2. **Create an account** -- enter your monthly income, fixed expenses, optional emergency fund, and savings goal
3. **Track daily spending** -- add expenses categorized by type; watch the circular progress ring fill
4. **Consult the AI advisor** -- enter any purchase (e.g., "MacBook Air, Rs 84999, Laptops") and get:
   - Buy/Wait recommendation with confidence score
   - Upcoming sale events where you can get it cheaper
   - Estimated savings if you wait
   - Alternative suggestions
5. **Build your streak** -- stay under budget daily to grow your saving streak counter

---

## Design System

| Token | Value | Usage |
|-------|-------|-------|
| `--background` | `hsl(220 15% 5%)` | Page background (near-black) |
| `--card` | `hsl(220 15% 8%)` | Card surfaces (deep grey) |
| `--primary` | `hsl(152 60% 48%)` | Emerald green -- CTAs, accents, focus rings |
| `--destructive` | `hsl(0 72% 51%)` | Over-budget warnings, delete actions |
| `--chart-3` | `hsl(43 96% 56%)` | Amber -- spending indicators |

**Typography**: Inter (body) + JetBrains Mono (financial figures)

**Animation Library**: Framer Motion with custom spring configs + CSS keyframe animations for particles, orbits, and coin spin

---

## Tech Stack

| Layer | Technology | Version |
|-------|-----------|---------|
| Framework | Next.js | 16.1 |
| UI Library | React | 19.2 |
| Language | TypeScript | 5.7 |
| Styling | Tailwind CSS | 3.4 |
| Components | shadcn/ui | Latest |
| Animations | Framer Motion | 11.18 |
| Charts | Recharts | 2.15 |
| Icons | Lucide React | 0.544 |
| ML Engine | Custom (TypeScript) | -- |

---

## Performance

- **Zero external API calls** -- everything runs client-side
- **Turbopack** -- sub-100ms HMR in development
- **Tree-shaken imports** -- only the icons and components used are bundled
- **Optimized animations** -- GPU-accelerated transforms, `will-change` properties
- **Lazy hydration** -- components animate in only when scrolled into viewport

---

## Future Roadmap

- [ ] **UPI Transaction Parser** -- auto-import expenses from UPI SMS/notifications
- [ ] **Group Budget Splitting** -- split expenses with roommates or friends
- [ ] **Investment Suggestions** -- recommend SIPs and mutual funds based on savings patterns
- [ ] **Price Comparison API** -- real-time price scraping from Amazon, Flipkart, Croma
- [ ] **PWA Support** -- install as native app on mobile devices
- [ ] **Cloud Sync (Optional)** -- encrypted backup to Supabase for cross-device access

---

## Team
| **Kartikey Pandey** |Feature 1 |
| **Yash Raj** |Feature 1 |
| **Gaurav  Deo** |Feature 2 |
| **Vicky Jaiswal** |Feature 2 |

---

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

<p align="center">
  <strong>Priope</strong> -- Because every rupee deserves a purpose.<br/>
  <sub>Built with care for students who want to spend smarter, save better, and build lasting financial habits.</sub>
</p>
