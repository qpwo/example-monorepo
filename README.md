## Example typescript monorepo

For https://github.com/pzavolinsky/ts-unused-exports/issues/277

```sh
# Current output:
ts-unused-exports tsconfig.json                                                                                                                 main ◼
1 module with unused exports
/Users/me/example-monorepo/logic/logic.ts: used1, used2, unused

# Desired output something like:
ts-unused-exports tsconfig.json                                                                                                                 main ◼
1 module with unused export
1 module with locally used export
/Users/me/example-monorepo/logic/logic.ts: unused: not used anywhere
/Users/me/example-monorepo/logic/logic.ts: usedWithinModule: used only within module
```

### NPM workspace instructions

```sh
# Add new package to root workspace:
npm init -w ./package-a
# Install `package-a` on `package-b`:
npm install package-a --workspace package-b
```
