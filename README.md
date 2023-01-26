# Import meta resolve with loaders

The repo reproduces the issue where `import-meta-resolve` package fails to resovle a TypeScript file when provided extension has `.js`.

## Environment

```sh
node -v
# v19.5.0
```

There are two files in this repo.

- `main.ts` - Uses the `import-meta-resolve` package
- `main-native.ts` - Uses the `import.meta.resolve` API.

Run the examples as follows to reproduce the issue.

## Works

```sh
node --loader=ts-node/esm --experimental-import-meta-resolve main-native.ts
``` 

## Does not work

```sh
node --loader=ts-node/esm main.ts
```