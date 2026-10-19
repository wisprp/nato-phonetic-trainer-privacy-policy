# NATO Phonetic Trainer — privacy policy

Static page for the Google Play listing. No build step, no JS, no Jekyll (`.nojekyll`).

Served at: <https://nato-phonetic-trainer.scheria.me/privacy-policy/>

## Layout

| File | Purpose |
|------|---------|
| `privacy-policy/index.html` | the policy (edit this one) |
| `privacy-policy.html` | copy, so `/privacy-policy` works even without the trailing slash |
| `index.html` | redirect to `/privacy-policy/` |
| `CNAME` | custom domain for GitHub Pages |

After editing: `cp privacy-policy/index.html privacy-policy.html`

## Deploy (once)

```bash
git init -b main && git add -A && git commit -m "privacy policy"
gh repo create nato-phonetic-trainer-privacy-policy --public --source . --push
gh api repos/wisprp/nato-phonetic-trainer-privacy-policy/pages -X POST -f 'build_type=legacy' \
   -f 'source[branch]=main' -f 'source[path]=/'
```

DNS at the domain host: `CNAME  nato-phonetic-trainer.scheria.me  →  wisprp.github.io`, then tick
*Enforce HTTPS* in the Pages settings. Play Console wants this URL under
**Store settings → Privacy policy**.
