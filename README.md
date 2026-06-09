# cms-public-storefront — minimal starter scaffold

> ⚠ **Not a catalog template.** This is a bare Next 16 + Convex starter
> (single landing page, stub schema, ~25 files) kept as an `rr add` base for
> custom builds. It has **none** of the fleet headless-OS machinery (no
> `/setup` wizard, admin, update/backup cards, version.json) — for a real
> deployable template, start from any `template-<slug>` OS repo instead.
> The old Vercel demo project was deleted 2026-06-05; a preview lives at
> resource.rahmanef.com/preview/cms-public-storefront.

Scaffolded with [`rahman-resources`](https://www.npmjs.com/package/rahman-resources) — Next 16 + React 19 + Convex + Tailwind 4 + shadcn/ui.

## Setup

```bash
npm install --legacy-peer-deps
cp .env.example .env.local           # fill NEXT_PUBLIC_CONVEX_URL etc.
npx convex dev --once                 # generates convex/_generated
npm run dev
```

## Add a layout / recipe / feature

```bash
npx rahman-resources list
npx rahman-resources info <slug>
npx rahman-resources add personal-brand-os .   # full-app template (T1)
npx rahman-resources add ai-sdk-openrouter .   # feature (npm install)
```

## Hard rules

- **NO Clerk.** Auth = `@convex-dev/auth`.
- **shadcn primitives only** — no raw `<dialog>`, `<input type=date|file>`.
- Use `proxy.ts` (not `middleware.ts`) on Next 16.
- `convex/_generated` MUST be committed before deploy.

## Stack

| | |
|---|---|
| Framework | Next.js 16 (App Router) |
| UI | React 19 + Tailwind 4 + shadcn |
| Backend | Convex (self-hosted compatible) |
| Auth | `@convex-dev/auth` (Password provider by default) |
