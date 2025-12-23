# OAuth2 Callback Server

A simple Node.js server for handling OAuth2 callbacks for Bruno API client.

## Usage

Start the server with npx (no installation required):

```bash
npx @usebruno/oauth2-callback-server
```

The server will start on port **8090** by default (or the next available port if 8090 is busy).

Specify a custom port:

```bash
npx @usebruno/oauth2-callback-server --port 8090
npx @usebruno/oauth2-callback-server -p 8090
```

**Note:** If you specify a port and it's already in use, the server will exit with an error.

Show help:

```bash
npx @usebruno/oauth2-callback-server --help
npx @usebruno/oauth2-callback-server -h
```

Or install locally and run:

```bash
npm install @usebruno/oauth2-callback-server
npx @usebruno/oauth2-callback-server
```

Or run directly with node:

```bash
node server.js
node server.js --port 8090
```

Visit `http://localhost:<port>/callback` to see the OAuth2 redirect page.

## Development Mode

For local testing before publishing to npm:

```bash
cd /Users/lohit/Documents/code/oauth2-callback-server
npm link
npx @usebruno/oauth2-callback-server
```

## How it works

When you visit `/callback`, the server serves an HTML page that automatically redirects the OAuth2 callback (including query parameters and hash fragments) to Bruno using the `bruno://` protocol scheme.

