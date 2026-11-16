# Monitor Sidebar

Firefox sidebar panel for [Monitor](https://monitor.eli.kr). Loads the app in a
sidebar iframe and strips `X-Frame-Options` / `Content-Security-Policy`
response headers (via `declarativeNetRequest`) so it can be framed. The
Cloudflare Access login domain (`homelab-eli.cloudflareaccess.com`) is
unblocked too, so the Access login can complete inside the sidebar.

## Install (development)

1. Open `about:debugging#/runtime/this-firefox`
2. **Load Temporary Add-on…** → select `manifest.json`
3. Open the sidebar: `View → Sidebar → Monitor` (or `Ctrl+B` and pick Monitor)

## Release

Push a `vX.Y.Z` tag matching `manifest.json`'s `version`. The
[release workflow](.github/workflows/release.yml) signs the add-on with AMO
(unlisted) and attaches the `.xpi` to a GitHub release. Requires repo secrets
`WEB_EXT_API_KEY` and `WEB_EXT_API_SECRET`.

## Icons

`icons/monitor.png` is the source image. The extension uses generated
`icons/icon-*.png` files for its toolbar and add-on icons.
