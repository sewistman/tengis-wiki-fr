# Tengis Wiki — Claude Code Rules

## Product Branding

The product name is **Tengis Wiki**. Replace all user-facing instances of "Seafile" with "Tengis Wiki".

### Scope of branding changes — ALLOWED
- Visible UI strings (button labels, headings, paragraphs, tooltips, help text)
- Page `<title>` tags
- `<meta>` tag content values (e.g. `og:site_name`)
- Copyright notices (e.g. `© {year} Tengis Wiki`)
- Email template body text
- `gettext(...)` / `{% trans %}` / `{% blocktrans %}` strings that are rendered to users
- Locale `.po` file `msgstr` values for strings that are rendered to users

### Scope of branding changes — NEVER TOUCH
- Function names, method names, variable names, class names
- API endpoint paths or URL route strings
- CSS class names (e.g. `.seahub-modal-btn`, `.seahub-io-dialog`, `.seafile-multicolor-icon`)
- Backend Python logic, Django views, models, serializers, or middleware
- Import paths, module names, or package names
- Config file keys (only values visible to end users may change)
- `msgid` strings in `.po` files (these are lookup keys, not displayed text)
- Internal comments in code unless they are doc-comments rendered to users

## Color Palette

When changing color values, use only these brand colors:

| Role | Value |
|------|-------|
| Primary / accent | `#4A4EC7` |
| Black / foreground | `#0D0D0D` |
| Surface gray / background | `#F4F4F6` |

Only change color values in CSS or inline styles that are user-visible. Do not rename CSS custom properties or class names.

## Copyright

Copyright owner is **Tengis Wiki**. The copyright line should read:
```
© {year} Tengis Wiki
```

## External URLs

Any user-facing help links, support links, or `seafile.com` URLs rendered in the UI must be replaced with `https://redirish.global`.

### Examples
| Original | Replacement |
|----------|-------------|
| `https://www.seafile.com/en/download/` | `https://redirish.global` |
| `https://forum.seafile.com` | `https://redirish.global` |
| `http://seafile.com/download/` | `https://redirish.global` |

### Scope
- **ALLOWED**: replacing `href` values and visible link text in HTML templates and JS that point to `seafile.com` domains
- **NEVER TOUCH**: internal Django `{% url %}` tags, `SITE_ROOT`-relative paths, API base URLs, or any URL that routes within the application itself

## General Rules

- Never modify function names, API endpoints, URL routes, or backend logic.
- Never modify CSS class names.
- Only change visible UI strings, page titles, copyright notices, color values, and external seafile.com URLs.
- When in doubt about whether something is "user-facing", do not change it and ask first.
