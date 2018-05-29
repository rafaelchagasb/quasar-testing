# Quasar Contributing Guide

Hi! I’m really excited that you are interested in contributing to Quasar. Before submitting your contribution though, please make sure to take a moment and read through the following guidelines.

- [Code of Conduct](https://github.com/quasarframework/quasar-test/blob/dev/.github/CODE_OF_CONDUCT.md)
- [Issue Reporting Guidelines](#issue-reporting-guidelines)
- [Pull Request Guidelines](#pull-request-guidelines)
- [Development Setup](#development-setup)
- [Project Structure](#project-structure)

## Issue Reporting Guidelines

- The issue list of this repo is **exclusively** for bug reports and feature requests. Non-conforming issues will be closed immediately.

  - For simple beginner questions, you can get quick answers from the [Quasar Discord chat room](https://discord.gg/5TDhbDg).

  - For more complicated questions, you can use [the official forum](http://forum.quasar-framework.org/). Make sure to provide enough information when asking your questions - this makes it easier for others to help you!

- Try to search for your issue, it may have already been answered or even fixed in the development branch (`dev`).

- Check if the issue is reproducible with the latest stable version of Quasar. If you are using a pre-release, please indicate the specific version you are using.

- It is **required** that you clearly describe the steps necessary to reproduce the issue you are running into. Although we would love to help our users as much as possible, diagnosing issues without clear reproduction steps is extremely time-consuming and simply not sustainable.

- Use only the minimum amount of code necessary to reproduce the unexpected behavior. A good bug report should isolate specific methods that exhibit unexpected behavior and precisely define how expectations were violated. What did you expect the method or methods to do, and how did the observed behavior differ? The more precisely you isolate the issue, the faster we can investigate.

- Issues with no clear repro steps will not be triaged. If an issue labeled "need repro" receives no further input from the issue author for more than 5 days, it will be closed.

- If your issue is resolved but still open, don’t hesitate to close it. In case you found a solution by yourself, it could be helpful to explain how you fixed it.

- Most importantly, we beg your patience: the team must balance your request against many other responsibilities — fixing other bugs, answering other questions, new features, new documentation, etc. The issue list is not paid support and we cannot make guarantees about how fast your issue can be resolved.

## Pull Request Guidelines

- The `master` branch is basically just a snapshot of the latest stable release. All development should be done in dedicated branches. **Do not submit PRs against the `master` branch.**

- Checkout a topic branch from the relevant branch, e.g. `dev`, and merge back against that branch.

- It's OK to have multiple small commits as you work on the PR - we will let GitHub automatically squash it before merging.

- If you are adding a new test-runner:
 - Please make an issue before you make a pull request. Maybe someone else has some good ideas for you or there is previous work that you can adapt.
 - Ensure that the test-runner actually works in a real quasar project.
 - Write an example test that passes the "baseline.spec.vue" file with deep coverage.
 - If you need to make additions to the host package.json, follow the format in the package_template.json
 - 

- If adding new feature:
  - Provide convincing reason to add this feature. Ideally you should open a suggestion issue first and have it greenlighted before working on it.

- If fixing a bug:
  - If you are resolving a special issue, add `(fix: #xxxx[,#xxx])` (#xxxx is the issue id) in your PR title for a better release log, e.g. `fix: update entities encoding/decoding (fix #3899)`.
  - Provide detailed description of the bug in the PR. Live demo preferred.

## Development Setup

You will need [Node.js](http://nodejs.org) **version 4+** along [NPM](https://docs.npmjs.com/getting-started/installing-node).

After cloning the repo, run:

``` bash
$ npm install
```

## Project Structure

- **`bin`**: executables

  - **`wrappers`**: code for wrappers

  - **`quasar`**: entry point for CLI

  - **`quasar-*`**: entry point for CLI command

- **`lib`**: utilities used by CLI

- **`lists`**: list of templates available which **gets downloaded directly from Github repo at runtime** by CLI