# Demonstration of Jest, ESM, and @zondax/filecoin-signing-tools mishup

To reproduce:
```shell
npm install
npm run test
```

`npm run test` makes Jest use ESM preferrably. It fails, as `main` entry is imported, which is ESM,
but there is no indication it is ESM, so Jest considers it to be CJS.

Changing `main` entry to `"./nodejs/filecoin_signer_wasm.js"` makes it all work.
