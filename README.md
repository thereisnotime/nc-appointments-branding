# Appointments App | NextCloud

### Notice: Support for floating timezones is being phased-out


![Main View](screenshots/screenshot1.jpg)

---

![Schedule Generator](screenshots/screenshot2.jpg)

---

![Public View](screenshots/screenshot3.jpg)

---
## Getting Started...
[Help/Tutorial](https://htmlpreview.github.io/?https://github.com/SergeyMosin/Appointments/blob/master/templates/help.php)

## Releases (this fork)

Releases are built by `.github/workflows/release.yml`.

1. Make sure `appinfo/info.xml` `<version>` matches the upstream version you are on (e.g. `2.8.8`).
2. On the branch you want to ship, create an annotated tag `vX.Y.Z-branding.N` (the tag message becomes the release notes) and push only that tag:
   `git tag -a v2.8.8-branding.5 -m "notes" && git push origin v2.8.8-branding.5`
3. The workflow runs `npm ci`, `make build-prod` and `php -l`, checks the version, and publishes `appointments-X.Y.Z-branding.N.tar.gz` (single `appointments/` dir) plus a `.sha256` file. The notes end with `sha256 <hash>`.
4. Deployers pin the asset URL and its sha256.

To rebuild an existing tag, run the workflow manually with the `tag` input; it replaces the assets and notes.
