# @node/types issue with NativeScript project

>Note: This is a NativeScript project created with NativeScript CLI. The issue at hand is build time so you don't need NativeScript to reproduce it.

To reproduce:
1. clone the repo `git clone https://github.com/vakrilov/fork-ts-checker-example.git`
2. `npm i` (tested with `npm@6.4.1 + node@10.15.0` on OSX)
3. Run tsc `tsc -p tsconfig.tns.json` (tested with `typescript@3.4.3`)

Result is the following error:
```
app/main-page.ts:33:11 - error TS2322: Type 'Timeout' is not assignable to type 'number'.

33     const id: number = setTimeout(() => {
```             ~~

It is caused because the `"fork-ts-checker-webpack-plugin": "1.3.1"` installed the `@type/node` and `setTimeout` has a different return type in node.