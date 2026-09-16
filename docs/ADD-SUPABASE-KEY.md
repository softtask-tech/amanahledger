# Add your Supabase publishable key

## On this computer

Open `.env.local` in the repository root. Paste your key after the equals sign:

```dotenv
VITE_SUPABASE_PUBLISHABLE_KEY=sb_publishable_YOUR_KEY_HERE
```

Replace the example with the complete actual key. Keep it on one line without spaces around the equals sign. The project URL is already filled in. Save the file. Once an app development server exists, restart it after environment changes.

The local file is excluded by `.gitignore` and will not be pushed to GitHub. On another computer, copy `.env.example` to `.env.local` and fill it in there. The GitHub template intentionally stays blank; editing it on GitHub does not configure your local application.

## Is the key sensitive?

A key starting with `sb_publishable_` is intended for public browser/mobile applications and is not a secret. Keeping it out of Git is a configuration choice, not the database security boundary. Database grants, row-level security and authenticated-user policies determine what can be accessed. We have not yet inspected or configured those policies in this new project.

Never put `sb_secret_` keys, legacy `service_role` keys, database passwords or access tokens in a client environment variable or public repository. A client publishable key does not provide permission to run database migrations.

For hosted builds later, enter the public URL and publishable key in that host's environment settings. Any VITE_ value used in client code can be bundled into the published app; do not place elevated secrets there.

This repository currently contains planning documents; adding the key prepares configuration but does not start an app or change the database.

Source: [Supabase API keys](https://supabase.com/docs/guides/getting-started/api-keys), checked 16 September 2026.
