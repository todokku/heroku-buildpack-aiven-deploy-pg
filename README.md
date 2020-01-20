# heroku-buildpack-aiven-deploy
Deploy postgres db to aiven.

Requires:

- https://github.com/heroku/heroku-buildpack-python

Requirements in `app.json`:
===

```json
{
  "buildpacks": [
    {
      "url": "https://github.com/heroku/heroku-buildpack-cli"
    },
    {
      "url": "https://github.com/heroku/heroku-buildpack-python"
    },
    {
      "url": "https://github.com/Property-Meld/heroku-buildpack-aiven-deploy-pg"
    }
  ]
}
```

Required environment config vars:
====

```bash
AIVEN_AUTH_TOKEN # get in aiven, be sure to set in pipeline/heroku config vars
AIVEN_PROJECT_NAME # get in aiven, be sure to set in pipeline/heroku config vars
HEROKU_API_KEY # get in aiven, be sure to set in pipeline/heroku config vars
IS_REVIEW_APP # set in pipeline/heroku config vars
STAGING_APP_NAME # name of the heroku staging app name for usage with heroku cli, and db cloning (default: "property-meld-staging")
```

Other environment config vars:
====

```bash
AIVEN_CLOUD # (default: "do-nyc")
AIVEN_PG_VERSION # (default: "pgversion=12")
AIVEN_PLAN # (default: startup-4)
AIVEN_SERVICE_TYPE # (default: "pg" for postgres)
AIVEN_DBNAME # name of the db (default: "propertymeld")
HEROKU_APP_NAME # set by heroku, is the heroku app name
```

