# Cloudflare upload checklist (important)

If Cloudflare shows "site can’t be reached", the issue is usually deployment/DNS, not the HTML markup.

## 1) File name must be exact
- The main page must be named exactly: `index.html` (not `inde.html`).

## 2) Upload correctly
- If using **Cloudflare Pages**:
  - Create a Pages project.
  - Upload this repository (or drag/drop a folder/zip that contains `index.html` at the root).
  - No build command is needed.
  - Build output directory can be `/` (root).

## 3) Domain DNS
- In Cloudflare DNS for `bluestargames.online`, ensure the record points to the Pages project according to Cloudflare’s Pages custom-domain flow.
- Wait for DNS/SSL provisioning to complete.

## 4) Quick verification before upload
Run locally:

```bash
python3 -m http.server 4173
```

Then open `http://localhost:4173`.

If local works but public domain does not, the problem is Cloudflare config (DNS/domain attachment), not this HTML file.
