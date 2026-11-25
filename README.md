# TRACC Lab website

A static, responsive research lab website for the University of Rochester TRACC Lab — Translating Research into Action in Cancer Care.

## Pages

- `index.html`: mission, expertise, research overview, news, and contact.
- `research.html`: four research areas, current projects with expandable full descriptions, and future directions.
- `people.html`: principal investigator and research team biographies.
- `news.html`: lab news and symposium photographs.

## Editing

Edit `content/site.json`, then run:

```sh
python3 tools/build_site.py
```

The builder uses only the Python standard library and writes the four HTML files. Commit both the content change and regenerated HTML. Appearance is controlled by `styles.css`; `script.js` controls only the mobile navigation. Project descriptions use native HTML details elements and work without JavaScript.

To add a member, use an existing person record in `content/site.json` as a model. Place their portrait in `assets/` and reference its relative path in `photo`. Use `null` to keep an empty portrait area. Members are alphabetized by surname within each group; the PI remains first and Research management remains last.

## Preview and publication

```sh
python3 -m http.server 4186
```

Open http://localhost:4186/. GitHub Pages publishes the repository root from `main`. This site needs no dependency installation, build service, framework, or server backend. The contact action opens the visitor's email application.

Use a feature branch in the contributor fork and open a pull request against `tracclab/tracclab.github.io:main`. Merging the pull request updates the published website.
