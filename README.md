# ESLint Bug demo
## How to reproduce
1. Clone `rabbitfang/eslint-issue-demo`
1. Install ESLint `1.4.0` to `1.8.0`. (Can install local copy via `npm install`).
1. Run `eslint .`. (Can run local copy via `node_modules/.bin/eslint .`)

## Expected output
There should be a single `no-console` error for `test.js`.

## Actual output
No error occurs.

## Description of issue
The first line of `.eslintignore` is `**/*.js`, which (properly) ignores all JS files.
The next line adds an exception for `test.js` (or at least, it should).
The proper behavior can be demonstrated in ESLint version `1.3.1`.
Prepending `./` to the first line of `.eslintignore` (changing the line to `./**/*.js`) results in correct behavior in `1.8.0`.
