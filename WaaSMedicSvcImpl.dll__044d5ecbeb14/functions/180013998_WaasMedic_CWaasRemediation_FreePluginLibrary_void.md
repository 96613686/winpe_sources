# WaasMedic::CWaasRemediation::FreePluginLibrary(void)

- ea: `0x180013998`
- end: `0x180013a89`
- name: `?FreePluginLibrary@CWaasRemediation@WaasMedic@@QEAAJXZ`
- size: `241`
- prototype: `__int64 __fastcall(WaasMedic::CWaasRemediation *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18001558c`
- `0x180017a60`
- `0x1800184b0`

## callees

- `0x1800050a0`
- `0x18001039c`
- `0x180013998`
- `0x18002e56c`
- `0x18002e81c`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800139e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800139e7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180013a1f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180013a1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800139ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800139ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a29`

## string_xrefs

- `0x180013a59`: `Plugin library is not initialized.`

## pseudocode

```c

```
