# Matrix Audit

The initial matrix used Ubuntu and Windows with Node 18, 20, and 22. The
following combinations failed before any fixes were applied.

## Windows, Node 18

- OS and Node: `windows-latest`, Node 18
- Failed step: `Run npm test`
- Exact error line: `Error: ENOENT: no such file or directory, open 'C:\workspace\matrix-debug-drill/src/configs/default.json'`
- Classification: OS-specific
- Planned fix: Replace forward-slash path string concatenation in `src/fileUtils.js` with `path.join`.

The same job also reported this assertion error:

- Exact error line: `Received: "line one\r\nline two\r\nline three\r\n"`
- Planned fix: Normalize `\r\n` to `\n` in the file-reading test before comparing.

## Windows, Node 20

- OS and Node: `windows-latest`, Node 20
- Failed step: `Run npm test`
- Exact error line: `Error: ENOENT: no such file or directory, open 'C:\workspace\matrix-debug-drill/src/configs/default.json'`
- Classification: OS-specific
- Planned fix: Replace forward-slash path string concatenation in `src/fileUtils.js` with `path.join`.

The same job also reported this assertion error:

- Exact error line: `Received: "line one\r\nline two\r\nline three\r\n"`
- Planned fix: Normalize `\r\n` to `\n` in the file-reading test before comparing.

## Windows, Node 22

- OS and Node: `windows-latest`, Node 22
- Failed step: `Run npm test`
- Exact error line: `Error: ENOENT: no such file or directory, open 'C:\workspace\matrix-debug-drill/src/configs/default.json'`
- Classification: OS-specific
- Planned fix: Replace forward-slash path string concatenation in `src/fileUtils.js` with `path.join`.

The same job also reported this assertion error:

- Exact error line: `Received: "line one\r\nline two\r\nline three\r\n"`
- Planned fix: Normalize `\r\n` to `\n` in the file-reading test before comparing.

## Ubuntu, Node 22

- OS and Node: `ubuntu-latest`, Node 22
- Failed step: `Run npm test`
- Exact error line: `TypeError: crypto.createCipher is not a function`
- Classification: runtime version
- Planned fix: Replace the removed `crypto.createCipher` and `crypto.createDecipher` APIs with `crypto.createCipheriv` and `crypto.createDecipheriv`, using an explicit derived key and IV.
