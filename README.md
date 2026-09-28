# Cerious AASM — Unraid Community Applications

Official Unraid Community Applications metadata for **Cerious AASM**.

Cerious AASM is a self-hosted Ark: Survival Ascended server manager. This repository contains the Unraid Docker template; the application and container image are maintained in the main Cerious AASM project.

## Docker image

`ghcr.io/ryoucerious/cerious-aasm:latest`

## Unraid configuration

The template uses **host networking**. This is intentional for a game-server manager because ARK instances may use multiple game, peer, query, and RCON ports.

Persistent paths:

| Container path | Default Unraid path |
| --- | --- |
| `/home/aasm/.local/share/cerious-aasm` | `/mnt/user/appdata/cerious-aasm` |
| `/home/aasm/.config` | `/mnt/user/appdata/cerious-aasm/config` |

The Web UI is available on port `3000` by default.

## Authentication

Authentication is disabled by default to match the standard Docker configuration.

For machines reachable by untrusted networks, enable authentication and set a strong password before exposing the Web UI.

## Install locally before Community Apps approval

After this repository is pushed to GitHub, the template can be sideloaded onto an Unraid server:

```bash
mkdir -p /boot/config/plugins/dockerMan/templates-user

curl -fsSL \
  https://raw.githubusercontent.com/ryoucerious/cerious-aasm-unraid/main/templates/cerious-aasm.xml \
  -o /boot/config/plugins/dockerMan/templates-user/my-cerious-aasm.xml
```

Then open:

**Docker → Add Container → Template → User templates → Cerious-AASM**

## Community Apps submission

1. Push this repository to GitHub.
2. Verify all URLs in `ca_profile.xml` and `templates/cerious-aasm.xml`.
3. Add an application/repository icon before submission.
4. Run XML validation:
   ```bash
   xmllint --noout ca_profile.xml templates/cerious-aasm.xml
   ```
5. Use Unraid Community Applications **Validate and Scan**.
6. Submit the repository for inclusion in Community Apps.

## Project

https://github.com/ryoucerious/cerious-aasm

## Container registry

https://ghcr.io/ryoucerious/cerious-aasm
