# lunomi-pages

The public pages for **Lunomi**, a multilingual vocabulary-learning mobile app:
its Privacy Policy, its account-deletion instructions, and its support page.
These are the URLs the Google Play listing points at.

Plain HTML and one stylesheet. No build step, no npm, no framework, no
JavaScript, no cookies, no trackers, no external requests — the pages load
nothing but themselves.

## What is here

```
index.html               the landing page
privacy/index.html       Privacy Policy
delete-account/index.html  account deletion, for Play's external-deletion requirement
support/index.html       support contact
styles.css               the whole stylesheet
icon.png                 the app icon, 192px, used as the header mark and favicon
.nojekyll                stops GitHub Pages running these through Jekyll
```

`icon.png` is generated from `assets/icon.png` in the Lunomi app repository --
resized to 192 and palette-quantised, which is what keeps it under 3 KB. Replace
it the same way if the app icon ever changes.

## Previewing it locally

Open `index.html` in a browser — it works straight from the filesystem.

To see it exactly as it will be served, run any static server from this folder:

```sh
python3 -m http.server 8000
```

then visit <http://localhost:8000/>.

## Publishing

Settings → Pages → **Source: Deploy from a branch**, branch `main`, folder `/`
(root). Nothing else to configure: there is no custom domain, no workflow and no
build.

Every link and the stylesheet are **relative**, so the site works from a
repository subpath and needs no change if it is ever moved.

Once Pages is enabled the URLs are:

```
https://<username>.github.io/lunomi-pages/
https://<username>.github.io/lunomi-pages/privacy/
https://<username>.github.io/lunomi-pages/delete-account/
https://<username>.github.io/lunomi-pages/support/
```

For this repository that is `songuelok`, so the Privacy Policy URL to give
Google Play is:

```
https://songuelok.github.io/lunomi-pages/privacy/
```

and the account-deletion URL is:

```
https://songuelok.github.io/lunomi-pages/delete-account/
```

## Editing

Change the wording in the HTML; there is nothing to compile. Two things to keep
in step by hand:

- the **Last updated** date near the top of `privacy/index.html` and
  `delete-account/index.html`, whenever the substance of either changes;
- the header and footer, which are repeated in each page rather than shared.
  Four small copies were judged better than a build step or a script.

The palette in `styles.css` is the app's own, from `constants/theme.ts` in the
Lunomi repository.
