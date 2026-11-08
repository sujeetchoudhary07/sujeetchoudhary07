# Setup guide — SuJeet animated 3D GitHub profile

This package is customized from the supplied GitHub README for **sujeetchoudhary07**.

## What's inside

```text
sujeetchoudhary07/
├── README.md
├── assets/
│   ├── hero-3d.svg            # Custom animated, faux-3D SVG hero
│   └── footer-wave.svg        # Custom animated footer
└── .github/
    └── workflows/
        └── animations.yml     # Auto-generates 3D contributions + snake
```

The following files are **not** present in the zip: the workflow creates them when run:

```text
profile-3d-contrib/profile-season-animate.svg
assets/github-snake.svg
assets/github-snake-dark.svg
```

## Publish the profile

1. Create or open the **public** GitHub repository at `https://github.com/sujeetchoudhary07/sujeetchoudhary07`. The repository name must match the username for a profile README.
2. Copy `README.md`, both files in `assets/`, and `.github/workflows/animations.yml` into the matching paths in that repository. The files must be committed to your repository's default branch.
3. In GitHub, open **Settings → Actions → General** and ensure Actions are enabled for the repository. If your organization's/repository's workflow settings restrict the built-in token, permit `GITHUB_TOKEN` to write repository contents, or keep the workflow's `permissions: contents: write` setting.
4. Open **Actions → Update 3D GitHub Profile Animations → Run workflow** to create the contribution images for the first time. Review the workflow log and generated file paths if a card remains blank.
5. Refresh the profile README after the workflow's commit completes. GitHub caches images, so updates may take a little time to display.
6. The workflow runs once daily as well. Scheduled workflow execution can be delayed or paused by GitHub, so use manual dispatch when needed.

## Customize

- Change the introduction in `README.md` without affecting the workflow.
- Edit text, colors, visual effects and timings in `assets/hero-3d.svg` and `assets/footer-wave.svg`.
- The contribution image in `README.md` is `profile-season-animate.svg`; other themes are available in `profile-3d-contrib/` after running Actions. For example, swap the link to `profile-green-animate.svg`.
- If a public stats service is unavailable or rate-limited, remove or replace just that `<img>` tag. The custom SVG hero/footer are local and do not depend on third-party image-hosting services.
- To disable animation for visitors who prefer reduced motion, the custom SVGs already honor `prefers-reduced-motion`.

## Notes

- GitHub README HTML is sanitized: arbitrary JavaScript, `<canvas>`, and interactive Three.js scenes won't run in a profile README. The custom banner is a **3D-style, animated SVG**, not an actual Three.js scene.
- Some GitHub renderers and clients may show the SVG in a static frame. The layout will remain readable.
- GitHub Actions must run once before the 3D graph and snake references resolve.
- External stats, badges, and technology icons depend on their third-party services.
- Third-party animation actions can change; review the upstream repositories periodically. To harden a production workflow, pin actions to reviewed commit SHAs instead of mutable tags.

## Upstream components

- 3D GitHub contributions: https://github.com/yoshi389111/github-profile-3d-contrib
- Contribution snake: https://github.com/Platane/snk

The uploaded README's original links and existing public username have been retained or condensed. The profile text is editable and does not claim any employment or achievements not in the supplied README.
