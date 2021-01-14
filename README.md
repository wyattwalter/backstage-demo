# Backstage demo app

This is a basic shell of a Backstage app that mostly works locally via Docker Compose.

It's created through trial-and-error after working my way through the [Create an app](https://backstage.io/docs/getting-started/create-an-app) from the Backstage documentation. The tutorial trails off once you get to the configuration and deployment.

Configured in this demo is:

- GitHub OAuth for Backstage
- Ability to create repositories in GitHub using the built-in templates
- Service catalog is stored in a Postgres database, rather than the in-memory database that is configured by default
- Runs entirely via docker-compose

To get started, you'll need to [register an OAuth application on GitHub](https://github.com/settings/developers) (callback is localhost:7000 for now) and a [GitHub personal access token](https://github.com/settings/tokens). For the personal access token, it needs repo, workflow, and admin:repo_hook access.

Store those secrets into the .env file in your local checkout like:

```
export GITHUB_TOKEN=<token>
export AUTH_GITHUB_CLIENT_ID=<id>
export AUTH_GITHUB_CLIENT_SECRET=<secret>
```

Then, you should be able to use `docker-compose up -d` to start the stack. The build time for Backstage is significant, so it can take a while on the first startup.

The front-end will be available at http://localhost:3000.
