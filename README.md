# How npm3 works

NOTE: THE MAIN PROJECT IS NOT WORKING !!! THIS IS ONLY FOR TESTING NPM !!!

This project tries to illustrate how Npm works as per [the article](https://npm.github.io/how-npm-works-docs/npm3/how-npm3-works.html) in Npm official page.

The libraries in this project have been created following [the tutorial](https://michalzalecki.com/creating-typescript-library-with-a-minimal-setup/) by Michal Zalecki.

## Update 14/03/2020

This project has been modified to test preleases in Npm, so that something like snapshots in Maven can be achieved, as supported in [semver](https://semver.org/) but not in Npm itself - [see discussion](https://github.com/npm/npm/pull/12936).

[Npm Version](https://docs.npmjs.com/cli/version)

[Semver Calculator](https://semver.npmjs.com/)

## Instructions

### Test version conflicts

1. Run `npm install` and `npm run build` in root folder
2. Run `npm install` and `npm run build` in folder a
3. Move to a/dist folder and run `npm link`
4. Repeat steps 2, 3 and 4 with b and c
5. Run `npm test` in root folder and check results

### Test prerelease versions

Move to "a" folder:
- First run `npm install`
- To publish a new snapshot `npm run release:snapshot`
- To publish a new snapshot `npm run release:release`

The snapshot versions are tagged as "snapshot"

The release versions are tagged as "latest"

See package.json for use of npm version and prerelease

Move to root folder:
- First run `npm install --no-save`
- In package.json set prerelease version (>=1.0.0-snapshot)
  Then run `npm update --no-save` to get latest snapshot
- In package.json set release version (~1.0.0)
  Then run `npm update --no-save` to get latest release

Bot can be combined with 1.0.0|| >=1.0.0-snapshot

See installed versions in package-lock.json

Published versions can be found in [Npm Registry](https://www.npmjs.com/package/npm-test-lib-a?activeTab=versions).
