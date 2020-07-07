# deploy-env
Deploy environment variables from `.env` and `.env-cmdrc.json` files to Vercel

## Installation
``` bash
npm add -g deploy-env
```
> Note: `deploy-env` expects the Vercel CLI to be installed globally with `npm add -g vercel`

## Usage
In your Vercel project directory:

Make at least one `.env.production`, `.env.preview`, or `.env.development` file with your environment variables in the following format:
``` env
API_KEY=top_secret_api_key
...
```

You can also make an `.env-cmdrc.json` file with the following format:
``` jsonc
{
  "development": {
    "API_KEY": "development value"
    // development environment variables
  },
  "preview": {
    "API_KEY": "preview value"
    // preview environment variables
  },
  "production": {
    "API_KEY": "production value"
    // production environment variables
  }
}
```

Run the command:
``` bash
deploy-env [production|preview|development] [ENV_VAR]...
```
> Note: You can use `dpl-env` as an alias for `deploy-env`

## Examples
Deploy all `preview` environment variables to the Preview deployment
``` bash
deploy-env preview
```

Deploy only the `API_KEY` environment variable to the Preview deployment
``` bash
deploy-env preview API_KEY
```

Deploy only the `API_KEY`, `SECRET`, and `GRAPHQL_ENDPOINT` environment variables to Production
``` bash
deploy-env production API_KEY SECRET GRAPHQL_ENDPOINT
```
