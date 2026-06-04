# Deploy this dashboard to Vercel

This folder contains a single static file: `index.html` (the full dashboard — no backend, no build step).
Vercel serves it as-is with zero configuration.

---

## Option A — Vercel CLI (fastest, no GitHub needed)

1. Install the CLI (one time):
   ```
   npm i -g vercel
   ```
2. From **inside this `vercel_deploy` folder**, run:
   ```
   vercel
   ```
   - First run asks you to log in (opens the browser).
   - Accept the defaults: scope = your account, "Link to existing project?" = **No**,
     project name = e.g. `masa-rignite-dashboard`, directory = `./` (current),
     "want to modify settings?" = **No**.
3. It gives you a preview URL. Promote it to the public production URL with:
   ```
   vercel --prod
   ```

Done — share the `*.vercel.app` link.

---

## Option B — Vercel dashboard + GitHub (auto-redeploys on every push)

1. Put `index.html` in a GitHub repo (it can be the repo root, or keep this folder).
2. Go to https://vercel.com → **Add New… → Project → Import** your repo.
3. Framework Preset: **Other**. Root Directory: the folder that holds `index.html`
   (set it to `vercel_deploy` if you committed the whole project). Build command: leave **empty**.
4. Click **Deploy**.

Every future `git push` redeploys automatically.

---

## Option C — Drag & drop (no CLI, no git)

Vercel's CLI is the supported path, but if you want pure drag-and-drop, https://app.netlify.com/drop
takes this folder and gives a link instantly. (Same file works on either host.)

---

### Notes
- The link is **public** (anyone with the URL can view). Tell your teammate if you need it private
  (Vercel password protection requires a Pro plan).
- To update the live site later: replace `index.html` with the newest dashboard and re-run
  `vercel --prod` (Option A) or `git push` (Option B).
- Custom domain (optional): add it under the project's **Settings → Domains** in Vercel.
