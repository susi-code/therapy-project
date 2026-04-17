## Codebase index — mindweave-lively-main

This file is an auto-created index summarizing the repository structure and the most relevant files to help navigation and quick understanding.

### Project metadata
- name: `vite_react_shadcn_ts` (see `package.json`)
- scripts: `dev`, `build`, `build:dev`, `lint`, `preview`
- tech: Vite, React, TypeScript, Tailwind CSS, shadcn-ui

### Top-level files
- `README.md` — developer notes and quick start (npm i, npm run dev).
- `package.json` — dependencies & scripts.
- `vite.config.ts`, `tsconfig.json`, `tailwind.config.ts` — build & config.
- `index.html` — Vite entry HTML.

### public/
- `placeholder.svg`, `robots.txt` — static assets served by Vite.

### src/ (app source)
- `main.tsx` — app bootstrap (mounts React app, loads providers if any).
- `App.tsx` — main app component: React Router routes and global providers (QueryClient, ThemeProvider, UserProvider, Tooltips, Toasters). Routes:
  - Auth: `/login`, `/register`
  - Patient pages: `/` (Dashboard), `/phq9`, `/therapists`, `/sessions`, `/ai-plan`
  - Therapist pages: `/therapist`, `/therapist/slots`, `/therapist/sessions`, `/therapist/profile`

#### src/components/
- `AppSidebar.tsx`, `Layout.tsx`, `NavLink.tsx`, `RoleSwitcher.tsx` — app shell and navigation.
- `ui/` — UI primitives and wrappers (many shadcn-style components): `button.tsx`, `input.tsx`, `card.tsx`, `dialog.tsx`, `toast.tsx`, `toaster.tsx`, `tooltip.tsx`, and more. These are small, reusable UI components used across pages.

#### src/contexts/
- `UserContext.tsx` — user/session context provider used by the app.

#### src/hooks/
- `use-mobile.tsx` — mobile detection hook.
- `use-toast.ts` — toast helper hook.

#### src/lib/
- `mockData.ts` — mock data for local development / demo.
- `utils.ts` — general utility helpers used by the app.

#### src/pages/
- `NotFound.tsx` — 404 page.
- `auth/` — `Login.tsx`, `Register.tsx`.
- `patient/` — `Dashboard.tsx`, `PHQ9.tsx`, `Sessions.tsx`, `Therapists.tsx`, `AIPlan.tsx`.
- `therapist/` — `Dashboard.tsx`, `Profile.tsx`, `Sessions.tsx`, `Slots.tsx`.

### Notes and where to look for common tasks
- To run locally: `npm i` then `npm run dev` (see `README.md`).
- Add UI changes in `src/components/ui/`.
- Page logic lives in `src/pages/` grouped by role (patient/therapist/auth).
- Global state (user) lives in `src/contexts/UserContext.tsx`.

### Quick pointers for contributors
- If adding a new page, create file under `src/pages/<role>/` and add route in `src/App.tsx`.
- For shared small UI pieces, add or extend files under `src/components/ui/`.

---
Generated on repository scan. If you'd like, I can also:

- produce a machine-readable JSON index (file paths + inferred type), or
- generate a smaller per-folder README files inside larger folders (e.g. `src/components/README.md`).

Open an issue or tell me which option you prefer and I will generate it.
