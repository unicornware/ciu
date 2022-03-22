# Contributing Guide

## Overview

[Getting Started](#getting-started)  
[Contributing Code](#contributing-code)

## Getting Started

### Yarn

This project uses Yarn 2. The Yarn configuration for this project can be found
in [`.yarnrc.yml`](.yarnrc.yml).

If you're already using Yarn globally, see the [Yarn 2 Migration docs][1].

### Git Configuration

The examples in this guide contain references to custom Git aliases.

See [`.gitconfig`](.github/.gitconfig) for an exhausive list of aliases.

### Clone & Install

```zsh
git clone https://github.com/unicornware/ciu
cd ciu
yarn
```

Note that if you have a global Yarn configuration (or any `YARN_*` environment
variables set), an error will be displayed in the terminal if any settings
conflict with the project's Yarn configuration, or the Yarn 2 API.

## Contributing Code

[Husky][2] is used to run Git hooks that locally enforce coding and commit
message standards, as well as run tests associated with any files changed since
the last commit.

### Commit Messages

This project follows [Conventional Commit][3] standards and uses [commitlint][4]
to enforce those standards.

This means every commit must conform to the following format:

```zsh
<type>[optional scope]: <description>
 │     │                │
 │     │                └─⫸ summary in present tense; lowercase without period at the end
 │     │
 │     └─⫸ see .commitlintrc.ts
 │
 └─⫸ build|ci|chore|docs|feat|fix|perf|refactor|revert|style|test|wip

[optional body]

[optional footer(s)]
```

`<type>` must be one of the following values:

- `build`: Changes that affect the build system or external dependencies
- `ci`: Changes to our CI configuration files and scripts
- `chore`: Changes that don't impact external users
- `docs`: Documentation only changes
- `feat`: New features
- `fix`: Bug fixes
- `perf`: Performance improvements
- `refactor`: Code improvements
- `revert`: Revert past changes
- `style`: Changes that do not affect the meaning of the code
- `test`: Adding missing tests or correcting existing tests
- `wip`: Working on changes, but you need to go to bed :wink:

e.g:

- `git docs 'update contributing guide'` -> `docs: update contributing guide`
- `git ac 'refactor(algs)!: two sum'` -> `refactor(api)!: two sum`

See [`.commitlintrc.ts`](.commitlintrc.ts) for an exhasutive list of valid
commit scopes and types.

### Code Style

[Prettier][5] is used to format code, and [ESLint][6] to lint files.

#### Prettier Configurations

- [`.prettierrc.cjs`](.prettierrc.cjs)
- [`.prettierignore`](.prettierignore)

#### ESLint Configurations

- [`.eslintrc.base.cjs`](.eslintrc.base.cjs)
- [`.eslintrc.cjs`](.eslintrc.cjs)
- [`.eslintrc.spec.cjs`](.eslintrc.spec.cjs)
- [`.eslintrc.spellcheck.cjs`](.eslintrc.spellcheck.cjs)
- [`.eslintignore`](.eslintignore)

### Making Changes

Source code is located in [`src`](src) directory.

### Documentation

- JavaScript & TypeScript: [JSDoc][7], linted with [`eslint-plugin-jsdoc`][8]

Before making a pull request, be sure your code is well documented, as it will
be part of your code review.

### Testing

This project uses a [Mocha][9] x [Chai][10] workflow.

[Husky](#contributing-code) is configured to run tests before every push. If you
need to create a new issue regarding a test, or need to make a `wip` commit, use
`it.skip` to mark your tests as [pending][11].

#### Running Tests

- run all test suites: `yarn test`
- run all test suites (with live coverage view): `yarn test:coverage`

[1]: https://yarnpkg.com/getting-started/migration
[2]: https://github.com/typicode/husky
[3]: https://conventionalcommits.org
[4]: https://github.com/conventional-changelog/commitlint
[5]: https://prettier.io
[6]: https://eslint.org
[7]: https://jsdoc.app
[8]: https://github.com/gajus/eslint-plugin-jsdoc
[9]: https://mochajs.org
[10]: https://chaijs.com
[11]: https://mochajs.org/#inclusive-tests
