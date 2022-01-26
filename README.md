# pnpm hoisting issue

Run `pnpm install` multiple times: the erroir should appear on the third
attempt.

```
pnpm install
Scope: all 5 workspace projects
Lockfile is up-to-date, resolution step is skipped
Packages: +1821
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
node_modules/core-js-pure: Running postinstall script, done in 585ms
node_modules/core-js: Running postinstall script, done in 960ms
node_modules/watchpack-chokidar2/node_modules/fsevents: Running install script, done in 8.2s
Progress: resolved 0, reused 1488, downloaded 0, added 0, done
node_modules/vite/node_modules/esbuild: Running postinstall script, done in 996ms
node_modules/esbuild: Running postinstall script, failed in 1.4s
node_modules/esbuild postinstall$ node install.js
│ /Users/caldecor/Projects/pnpm-hoisted-storybook/node_modules/esbuild/bin/esbuild:1
│ ����
│ SyntaxError: Invalid or unexpected token
│     at Object.compileFunction (node:vm:352:18)
│     at wrapSafe (node:internal/modules/cjs/loader:1031:15)
│     at Module._compile (node:internal/modules/cjs/loader:1065:27)
│     at Object.Module._extensions..js (node:internal/modules/cjs/loader:1153:10)
│     at Module.load (node:internal/modules/cjs/loader:981:32)
│     at Function.Module._load (node:internal/modules/cjs/loader:822:12)
│     at Function.executeUserEntryPoint [as runMain] (node:internal/modules/run_main:81:12)
│     at node:internal/main/run_main_module:17:47
│ node:child_process:826
│     err = new Error(msg);
│           ^
│ Error: Command failed: node /Users/caldecor/Projects/pnpm-hoisted-storybook/node_modules/esbuild/bin/esbuild --version
│ /Users/caldecor/Projects/pnpm-hoisted-storybook/node_modules/esbuild/bin/esbuild:1
│ ����
│ SyntaxError: Invalid or unexpected token
│     at Object.compileFunction (node:vm:352:18)
│     at wrapSafe (node:internal/modules/cjs/loader:1031:15)
│     at Module._compile (node:internal/modules/cjs/loader:1065:27)
│     at Object.Module._extensions..js (node:internal/modules/cjs/loader:1153:10)
│     at Module.load (node:internal/modules/cjs/loader:981:32)
│     at Function.Module._load (node:internal/modules/cjs/loader:822:12)
│     at Function.executeUserEntryPoint [as runMain] (node:internal/modules/run_main:81:12)
│     at node:internal/main/run_main_module:17:47
│     at checkExecSyncError (node:child_process:826:11)
│     at Object.execFileSync (node:child_process:864:15)
│     at validateBinaryVersion (/Users/caldecor/Projects/pnpm-hoisted-storybook/node_modules/esbuild/install.js:94:32)
│     at /Users/caldecor/Projects/pnpm-hoisted-storybook/node_modules/esbuild/install.js:239:5 {
│   status: 1,
│   signal: null,
│   output: [
│     null,
│     Buffer(0) [Uint8Array] [],
│     Buffer(662) [Uint8Array] [
│        47,  85, 115, 101, 114, 115,  47,  99,  97, 108, 100, 101,
│        99, 111, 114,  47,  80, 114, 111, 106, 101,  99, 116, 115,
│        47, 112, 110, 112, 109,  45, 104, 111, 105, 115, 116, 101,
│       100,  45, 115, 116, 111, 114, 121,  98, 111, 111, 107,  47,
│       110, 111, 100, 101,  95, 109, 111, 100, 117, 108, 101, 115,
│        47, 101, 115,  98, 117, 105, 108, 100,  47,  98, 105, 110,
│        47, 101, 115,  98, 117, 105, 108, 100,  58,  49,  10, 239,
│       191, 189, 239, 191, 189, 239, 191, 189, 239, 191, 189,   7,
│        10,  10,  10,  83,
│       ... 562 more items
│     ]
│   ],
│   pid: 83834,
│   stdout: Buffer(0) [Uint8Array] [],
│   stderr: Buffer(662) [Uint8Array] [
│      47,  85, 115, 101, 114, 115,  47,  99,  97, 108, 100, 101,
│      99, 111, 114,  47,  80, 114, 111, 106, 101,  99, 116, 115,
│      47, 112, 110, 112, 109,  45, 104, 111, 105, 115, 116, 101,
│     100,  45, 115, 116, 111, 114, 121,  98, 111, 111, 107,  47,
│     110, 111, 100, 101,  95, 109, 111, 100, 117, 108, 101, 115,
│      47, 101, 115,  98, 117, 105, 108, 100,  47,  98, 105, 110,
│      47, 101, 115,  98, 117, 105, 108, 100,  58,  49,  10, 239,
│     191, 189, 239, 191, 189, 239, 191, 189, 239, 191, 189,   7,
│      10,  10,  10,  83,
│     ... 562 more items
│   ]
│ }
└─ Failed in 1.4s
```
