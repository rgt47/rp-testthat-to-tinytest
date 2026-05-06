# Post 62: From testthat to tinytest

*2026-05-02 09:05 PDT*

This compendium accompanies the blog post 'From testthat to
tinytest: Converting an R Package Test Suite'. The body argues
the trade-offs; the deliverable is a paired-example reference.

## Contents

- `analysis/report/index.qmd` is the rendered blog post.
- `docs/testthat-to-tinytest-recipe.qmd` is the conversion
  reference, with paired before-and-after examples for the
  twenty most common idioms.
- `docs/DATA_WORKFLOW_GUIDE.md`, `docs/ZZCOLLAB_BLOG_SETUP.md`,
  and `docs/ZZCOLLAB_USER_GUIDE.md` are the generic compendium
  guides inherited from the post-47 template.

## Reading the post

The blog body is the entry point. The recipe is referenced from
the body's appendix and is intended to be consulted as a lookup
table during an actual conversion.

## Standard make targets

| Target            | Effect                                        |
|-------------------|-----------------------------------------------|
| `make r`          | Enter the Docker container                    |
| `make render`     | Render `index.qmd` to HTML and PDF            |
| `make check-renv` | Verify that `renv.lock` matches loaded packages |
| `make clean`      | Remove `_freeze/` and rendered output         |

## Directory layout

```
testthat-to-tinytest/
  index.qmd -> analysis/report/index.qmd        (symlink)
  data/     -> analysis/data                    (symlink)
  figures/  -> analysis/figures                 (symlink)
  analysis/
    report/index.qmd                            blog post body
    media/images/                               hero + 3 ambiance
    data/                                       (no analysis data)
    figures/                                    (no figures)
  docs/
    README.md                                   this file
    testthat-to-tinytest-recipe.qmd             deliverable
    DATA_WORKFLOW_GUIDE.md                      generic
    ZZCOLLAB_BLOG_SETUP.md                      generic
    ZZCOLLAB_USER_GUIDE.md                      generic
  DESCRIPTION
  Dockerfile
  Makefile
  NAMESPACE                                     (empty: no R/ code)
  renv.lock
  zzcollab.yaml
```

The post ships no R code under `R/` because the deliverable is a
documentation artefact rather than executable analysis. The
`NAMESPACE` accordingly contains only the roxygen2 boilerplate
header.

## Status

- Body: complete first draft (see `index.qmd` AUTHOR PROVIDES
  block for which checklist items are ticked).
- Recipe: complete first draft.
- Imagery: hero and three ambiance images are placeholders
  inherited from post 47. Replace before flipping
  `draft: false`.
- Real-migration appendix (Appendix B in the body): contains a
  `[PLACEHOLDER]` reserved for a link to the actual migration
  commit. Resolve before publishing.

## Reproducibility

The post is rendered inside the `ubuntu_x11_analysis` ZZCOLLAB
profile. The `renv.lock` pins all R-package versions used in the
body's example code. Versions are listed in the post's
'Reproducibility' section.
