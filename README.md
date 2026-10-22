# CodeLens AI

CodeLens AI turns code snippets into plain-English explanations. Paste code into the page, choose how detailed the explanation should be, and get a streamed response you can copy.

## Features

- Beginner-friendly, intermediate, and line-by-line explanations
- A sample snippet to try without preparing your own code
- Live character count and an 8,000-character input limit
- Streamed explanations with Markdown formatting
- Copy, clear, and loading/error feedback

## Run locally

This is a static web app and does not require a build step or package installation.

1. Serve the project directory with a local web server, for example:

   ```powershell
   python -m http.server 8000
   ```

2. Open <http://localhost:8000> in your browser.
3. Paste a code snippet or choose **Try a sample**, select an explanation style, and click **Explain**.

The app uses the Groq chat completions API and the `openai/gpt-oss-120b` model. A valid Groq API credential is required for explanations.

## Credential and deployment warning

The current implementation makes API requests directly from the browser and contains a hard-coded API credential in `just_explain.js`. Anything shipped to a browser is visible to users. **Revoke that credential and do not commit or deploy it.** For local testing, use a credential you can safely rotate; before sharing or deploying the app, move API calls to a server-side endpoint that keeps the credential private.

## Project files

- `index.html` — page structure, styling, and controls
- `just_explain.js` — UI behavior, Groq API requests, streaming, and rendering
