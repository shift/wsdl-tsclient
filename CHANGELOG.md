# Changelog

All notable changes to this project will be documented in this file.

## [1.5.0](https://github.com/shift/wsdl-tsclient/compare/v1.4.0...v1.5.0) (2023-07-19)


### Features

* Allow providing a tsconfig at generation time to control the output code ([b5cf8bb](https://github.com/shift/wsdl-tsclient/commit/b5cf8bbd6f2387ed7eededdab6df9f6a4be549a2))


### Bug Fixes

* **ci:** Hopefully fixes publishing. ([426d384](https://github.com/shift/wsdl-tsclient/commit/426d3844e0dda4cdd59c581fa3cba427adb059cc))
* **deps:** update dependency soap to v1 ([9916af6](https://github.com/shift/wsdl-tsclient/commit/9916af635561878df2d0a642ffe8523e842934a8))
* **deps:** update dependency ts-morph to v19 ([8b876db](https://github.com/shift/wsdl-tsclient/commit/8b876db0da5c85f543c0378aa07ed5cd3cea0c6d))
* **deps:** update typescript-eslint monorepo to v6 ([8b82e70](https://github.com/shift/wsdl-tsclient/commit/8b82e705817e79a28a04ffad6d9bc22cc8c3d1e7))
* Remove broken test temp. ([d48f4d6](https://github.com/shift/wsdl-tsclient/commit/d48f4d6ed80cb835abf9192547fd3b133a763c1c))

## [1.4.0] - 2022-04-27

- Fix issue with self recursive WSDL types [#39](https://github.com/dderevjanik/wsdl-tsclient/pull/39) by @mtranter
- Fix issue with `quiet` option not working properly
- Project: Updated several npm packages
- Project: Added eslint
- Project: Added test for typechecking generated wsdl clients [#19](https://github.com/dderevjanik/wsdl-tsclient/pull/19)
- Project: Add more jsdoc to `parseAndGenerate` and `parsedWsdl`
- ParseAndGenerate: Support for `colors`, `verbose` and `queit` options (before it was only possible through CLI)
- Docs: Mention `basicAuth` in `README.md`

## [1.3.1] - 2021-07-01

- Project: Updated several npm packages
- Parser: Fixed issue while finding name for sub-definition, which has same name as parent definition, fixes [#16](https://github.com/dderevjanik/wsdl-tsclient/issues/16)
- Generator: Sanitize method, param and property names (e.g. names with `-`), fixes [#16](https://github.com/dderevjanik/wsdl-tsclient/issues/16) [#18](https://github.com/dderevjanik/wsdl-tsclient/issues/18)

## [1.2.0] - 2021-06-26

- CLI: Add option for `maxRecursiveDefinitionName`, default `64`
- CLI: Add option for `caseInsensitiveNames`, default `false`
- Parser: Warn user if recursive definition name exceed `32`
- Parser: Option for `caseInsensitiveNames`, fix [#12](https://github.com/dderevjanik/wsdl-tsclient/pull/12) by @jakethagle
- Generator: Fix incorrect case

## [1.1.4] - 2021-05-10

- Parser: Fix `sourceName` for definitions
- Parser: Add warn logs when parsing `ComplexType` as `any`
- Parser: Partial options for `parse` function
- Generator: Partial options for `generate` function
- More meaningful source code comments

## [1.1.3] - 2021-05-03

- Fix cyclic error when parsing `ComplexType`. Now generates `any` type
- Fix problem with duplicated imports (importing same definition for client/service/port)

## [1.1.2] - 2021-05-01

- Fix wrong generated callback result
- Parser: Improved message for cyclic errors
- Parser: Improved message for finding non-collision definition name

## [1.1.1] - 2021-04-20

- Fix wrong AsyncFunction return's type generation #10
- Fix Ports importing bad definition filename
- Fix generated Port's method names

## [1.1.0] - 2021-04-17

- Engine: Is possible to pass URL to WSDL (with `http://` or `https://` prefix)
- Generator: Fix problem with generating import paths on Windows
- Parser: Pefix `targetNSAlias` and `targetNamespace` with `@`
- Parser: Parse input/output with `parts` only
- Parser: Better error reports for cyclic error
- Parser: Add verbose logs for parsing Service,Port,Method and Definitons
- Project: Add tests for generating clients from wsdl and checking Definitions
- CLI: Reworked to support more `yargs` features
- CLI: Show number of errors occured
- CLI: Detect `NO_COLOR` and `DEBUG` environment variables

## [1.0.1] - 2021-03-21

- Engine: Reworked engine completely by separating `Parser` and `Generator` logic
- Engine: `targetNSAlias` and `targetNamespace` is included in defition jsdoc instead of properties
- Engine:  Generator now generates Client interface based on wsdl name to avoid namespace merging
- Engine:  Support color logs (green for info, red for errors)
- Engine: `Write` logs are printed before file is saved
- Engine: Support for `modelNamePrefix` and `modelNameSuffix`
- Parser: Sanitize definition names by striping reserved characters (e.g. `:`)
- Parser: Definition's jsdoc includes sourcename of definition
- Generator: Generates `index.ts` with all re-exported definitions, ports, services and client
- CLI: Fixed glob
- CLI: Generating client to `outputDir/{wsdlFilename}` directory
- CLI: `--quiet` flag for suppressing all logs
- CLI: `--verbose` flag for verbose logs
- CLI: `--no-color` flag for turning off colourful logs
- CLI: `--emitDefinitionsOnly` flag to generate only Defintions files (no Ports, Service nor Clients)
- CLI: `--modelNamePrefix` and `--modelNameSuffix`
- Project: Updated README  by adding section about how to use generated client

## [0.3.5] - 2021-03-10

- Project: Fix path to dist sources #8 by @cobraz

## [0.3.4] - 2021-03-10

- Fix problem with generated methods that includes javascript keywords as param names

## [0.3.3] - 2021-03-09

- Project: Add typescript declaration #3 by @cobraz

## [0.3.2] - 2021-03-04

- CLI: Add `version` and `help` params
- Project: Add MIT license
- Project: Add minimum node engine (base on node-soap)

## [0.3.1] - 2021-03-03

- CLI: Add support for glob pattern
- Generator: Add support for generating named client

## [0.2.0] - 2021-03-01

- Generator: Use camelcase for generating definitions, filenames and function params
- CLI: Replace `-i` with `WSDL`
