# Local development environment

Use the repository-pinned Node 22.21.1 and npm 11.7.0. Rebuild the devcontainer after changing its configuration; postCreateCommand installs locked dependencies with npm ci.

Host SSH, GitHub and Claude credential directories are not mounted automatically. Authenticate explicitly inside the container if needed; keep any additional credential mounts in local-only configuration. Do not commit tokens.

DATABASE_URL defaults to local Supabase at host.docker.internal:54322. Start local Supabase before running database-dependent services. Set a development-only URL explicitly inside the container if using another local database. Host DATABASE_URL is intentionally not inherited.

Run npm run dev for showcase/docs, or npm run dev:cloud for web/API. Forward ports 8260–8263 privately. Run npm run lint, npm run check-types and npm test before application changes are merged.

Container rebuild and database connectivity must be verified on the machine hosting Docker. Changing this configuration does not alter an already running container or any production deployment.
