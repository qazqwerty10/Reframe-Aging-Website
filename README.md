# Reframe Aging Website

Static website for Reframe Aging PLLC — the professional platform of Tim Nguyen, PT, DPT, GCS.

**Live site:** [reframeaging.com](https://reframeaging.com)
**Host:** Cloudflare Pages, deploying automatically from the `main` branch of this repo.

---

## The one rule: everything lives at the root

Every file in this site sits at the **top level of the repo**. There are **no subfolders** for pages, and there is only **one `index.html`** (the homepage). If you ever see a file going into a folder, or a second `index.html`, something is wrong — stop and fix it before committing.

This flat layout is deliberate: it's what keeps uploads from getting confused.

---

## What's in the repo

| File | The page it becomes | Lives at this URL |
|------|--------------------|-------------------|
| `index.html` | Homepage | `reframeaging.com/` |
| `start-here.html` | Start Here | `reframeaging.com/start-here.html` |
| `about.html` | About Tim | `reframeaging.com/about.html` |
| `work-with.html` | Services | `reframeaging.com/work-with.html` |
| `insights.html` | Insights landing | `reframeaging.com/insights.html` |
| `the-capacity-principle.html` | First article | `reframeaging.com/the-capacity-principle.html` |
| `workshops.html` | Workshops | `reframeaging.com/workshops.html` |
| `contact.html` | Contact | `reframeaging.com/contact.html` |
| `styles.css` | Shared stylesheet (all pages) | — |
| `sitemap.xml` | Sitemap for search engines | `reframeaging.com/sitemap.xml` |
| `robots.txt` | Crawl directives | `reframeaging.com/robots.txt` |
| `README.md` | This file (not published) | — |

**Important:** `index.html` is the homepage and must always be named exactly `index.html` at the root. `insights.html` is a normal page — it is *not* a second homepage. Don't let the two get swapped.

The favicon (the little tab icon) is now **built into every page directly**, so the site does not depend on any image folder for it.

---

## Two things to delete from the repo (one-time cleanup)

If either of these still exists in the repo, delete it:

1. **`insights/` folder** — the old location of the Insights pages. They now live at the root as `insights.html` and `the-capacity-principle.html`, so the folder is obsolete and will create a confusing second `index.html`.
2. **`mnt/` folder** (e.g. `mnt/user-data/outputs/...`) — this was uploaded by accident with a full file path. It is not part of the website and should be removed entirely.

---

## How to upload changes (GitHub web)

1. Open the repo on github.com, on the `main` branch.
2. Click **Add file -> Upload files**.
3. Drag the **files themselves** (not a folder) into the page. They land at the root.
4. When GitHub asks to replace existing files, that's correct — confirm.
5. Commit. Cloudflare rebuilds automatically in about a minute.

To confirm it worked, open `reframeaging.com` on a phone: the top-left should show the `REFRAME AGING` logo, and the menu button should open the full navigation.

---

## Cloudflare Pages settings (already configured)

- Framework preset: **None**
- Build command: leave blank
- Build output directory: `/`
- Root directory: leave blank

---

## Editing the site

- **Change wording on a page:** edit that page's `.html` file directly.
- **Change colors, spacing, fonts, layout:** edit `styles.css` only — it controls every page at once.
- **Add a new article:**
  1. Make a copy of `the-capacity-principle.html` and rename it (e.g. `strength-and-age.html`).
  2. Update its `<title>`, the `canonical` link, and the `og:url` to the new filename.
  3. Replace the article content.
  4. Add a linking card to `insights.html`.
  5. Add a `<url>` line for it to `sitemap.xml`.
- **Add a new top-level page:** copy any root `.html`, update the nav highlight (`aria-current="page"`), and add the new page to the nav on every other page.

---

## Still on Tim's list (content, not code)

- [ ] Add a real headshot to `about.html` (placeholder is in place).
- [ ] Confirm/replace the LinkedIn and Instagram links in the footers.
- [ ] Add `og-image.jpg` (1200x630) for nicer social-share previews.
- [ ] Connect the newsletter form to an email service (ConvertKit / Mailchimp).
- [ ] Submit `https://reframeaging.com/sitemap.xml` in Google Search Console.
- [ ] Create a Google Business Profile (high-value, free local SEO).
- [ ] Write the second article (suggested: "Why Strength Matters More Than Age").
