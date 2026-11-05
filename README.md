# Legura Site

The public presentation site for [Legura](https://github.com/vladanPro/legura),
built with Axonyx. This repository is not the installable CMS and contains no
user database, setup route, or administration surface.

## Routes

- `/` introduces the product and its current pilot scope.
- `/how-it-works` explains the public site and backoffice boundary.
- `/roadmap` separates the pilot, first install, daily CMS work, and later extensions.
- `/download` links to the current source-pilot instructions and explicitly says
  that a production installer and prebuilt release do not exist yet.

The mark in `public/brand-mark.svg` and `public/favicon.svg` is copied from the
canonical Legura mark. Product behavior and installation instructions belong in
the [Legura repository](https://github.com/vladanPro/legura). Keep this site's
claims aligned with that source before publishing changes.

## Local development

Install `cargo-axonyx` 0.8.8, then run:

```powershell
cargo ax check
cargo ax doctor --deny-warnings
cargo ax build --clean
cargo ax run dev
```

The app pins `axonyx-runtime` 0.8.3 and `axonyx-ui` 0.0.89. Commit `Cargo.lock`
to keep deployments reproducible. The site needs no database, backend actions,
or custom JavaScript.

## Deployment boundary

The proposed public URL is `legura.axonyx.dev`. Do not point the subdomain at a
CMS installation. Deploy only this presentation app's verified static output,
or serve it with the Axonyx server if the host requires that model. Do not add a
binary download until an independently tested installation and upgrade path exists.
