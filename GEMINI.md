# Project Name

???

# Overview

The goal of this project is ???

# Page Structure

## Home (src/routes/index.tsx)

- ???

# Tech Stack

- **Framework:** React 19
- **Routing & SSR:** TanStack Router + TanStack Start (`@tanstack/react-start`)
- **Styling:** Tailwind CSS v4 (`@tailwindcss/vite`)
- **UI Components:** Shadcn UI (Base UI primitives + Tailwind)
- **Icons:** Hugeicons (`@hugeicons/react`)
- **Build Tool:** Vite 7
- **Deployment:** Cloudflare Workers (`wrangler`)
- **Testing:** Vitest

# Key Directories

- `src/routes/`: File-based routing for TanStack Router.
- `src/components/ui/`: Reusable UI components (buttons, inputs, etc.).
- `src/lib/utils.ts`: Utility functions, specifically `cn()` for conditional class merging.
- `src/styles.css`: Global styles (imported in `src/routes/__root.tsx`).

# Conventions

- **Styling:** Use Tailwind CSS utility classes. Use `cn()` helper from `src/lib/utils.ts` for dynamic classes.
- **Routing:** Create new routes in `src/routes/`. TanStack Router will auto-generate the route tree in `src/routeTree.gen.ts`.
- **Components:** Place shared UI components in `src/components/ui/`.
- **SSR:** The project uses TanStack Start for Server-Side Rendering. Ensure components are SSR-compatible where necessary.

# Commands

- `npm run build`: Build for production.
- `npm run check`: Run lint and format.
- `npm run dev`: Start development server.

# Style

- add `underline-offset-4` after `underline`, `hover:underline`

# Check List

## Check after editing

- run `npm run check`
- if error, fix it
- run `npm run build`
- if error, fix it

## Don't edit

- components/ui/\*

## Button with react-router Link

```tsx
import { Link } from '@tanstack/react-router'
import { Button } from '@/components/ui/button'

// wrong
<Button asChild>
  <Link to="/">
    <HugeiconsIcon icon={ArrowLeft01Icon} size={20} className="mr-2" />
    link
  </Link>
</Button>

// correct
<Link to="/">
  <Button>
    <HugeiconsIcon icon={ArrowLeft01Icon} size={20} className="mr-2" />
    link
  </Button>
</Link>
```

## Tailwind CSS v4

| Deprecated | Replacement |
| `bg-opacity-*` | Use opacity modifiers like `bg-black/50` |
| `text-opacity-*` | Use opacity modifiers like `text-black/50` |
| `border-opacity-*` | Use opacity modifiers like `border-black/50` |
| `divide-opacity-*` | Use opacity modifiers like `divide-black/50` |
| `ring-opacity-*` | Use opacity modifiers like `ring-black/50` |
| `placeholder-opacity-*` | Use opacity modifiers like `placeholder-black/50` |
| `flex-shrink-*` | `shrink-*` |
| `flex-grow-*` | `grow-*` |
| `overflow-ellipsis` | `text-ellipsis` |
| `decoration-slice` | `box-decoration-slice` |
| `decoration-clone` | `box-decoration-clone` |
| `aspect-[9/16]` | `aspect-9/16` |
| `bg-gradient-to-t` | `bg-linear-to-t` |

| v3 | v4 |
| `shadow-sm` | `shadow-xs` |
| `shadow` | `shadow-sm` |
| `drop-shadow-sm` | `drop-shadow-xs` |
| `drop-shadow` | `drop-shadow-sm` |
| `blur-sm` | `blur-xs` |
| `blur` | `blur-sm` |
| `backdrop-blur-sm` | `backdrop-blur-xs` |
| `backdrop-blur` | `backdrop-blur-sm` |
| `rounded-sm` | `rounded-xs` |
| `rounded` | `rounded-sm` |
| `outline-none` | `outline-hidden` |
| `ring` | `ring-3` |

## Section comment

add section comment to each section for user to identify it next time editing

```tsx
return (
  <>
    {/* section : profile */}
    <Profile />
    {/* section : career highlight */}
    <CareerHighlight />
    {/* section : contact */}
    <Contact />
  </>
)
```
