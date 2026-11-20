# NutraStack post-mortem

A static, single-page retrospective of NutraStack (2023–2026), a supplement marketplace that ranked products by their nutrition labels.

Everything the site needs is in `public/`: one `index.html` with inline CSS and JS, plus `favicon.svg`. There is no build step. Fonts load from Google Fonts.

## Preview locally

```bash
npx serve public
```

Or open `public/index.html` directly in a browser.

## Deploy to Cloudflare Pages

**From the dashboard (Git integration):**

1. Cloudflare dashboard → Workers & Pages → Create → Pages → Connect to Git.
2. Pick this repository and the branch to deploy.
3. Framework preset: `None`. Build command: leave empty. Build output directory: `public`.
4. Save and deploy, then add your custom domain under the project's Custom domains tab.

**From the command line:**

```bash
npx wrangler pages deploy public --project-name nutrastack
```

## Sources

Catalog figures (products, flavors, brands, ingredients) and the schema excerpt come from the NutraStack webapp repository (`nutrastackinc/webapp`) as of November 2024. The partner list combines the 13 brands with live affiliate agreements in that repository and six brands signed later that never went live. Brand onboarding terms and the closing quote come from the 2025 brand deck. Ad spend is totaled from 161 Meta and 14 TikTok ad receipts (August 2024 to March 2025). Follower counts were checked in November 2026. The ranking demo ports `custom_sigmoid()` from the webapp's `private/db.py` and uses label data from its `private/nutrastack_database.py`.
