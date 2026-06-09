# DumpWindowsInsiderSettings

- ea: `0x1801adee8`
- end: `0x1801ae2b4`
- name: `DumpWindowsInsiderSettings`
- size: `972`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1801b066c`

## callees

- `0x1800031d0`
- `0x180003c64`
- `0x1800062b8`
- `0x18000aedc`
- `0x18000fe74`
- `0x180043b00`
- `0x180044170`
- `0x1800443e4`
- `0x180044f38`
- `0x1801ac520`
- `0x1801adee8`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ae04b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ae249`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ae04b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ae249`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1801adfa1`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1801adfa1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801adfc6`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801adfc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801ae037`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801ae239`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801ae037`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801ae239`

## string_xrefs

- `0x1801adf51`: `ntdll.dll`
- `0x1801adfb1`: `Failed to obtain handle to ntdll.dll`
- `0x1801ae0af`: `Not able to find Windows Insider Program settings`
- `0x1801ae162`: `Not able to read Ring`
- `0x1801ae19a`: `Not able to read IsBuildFlightingEnabled`
- `0x1801ae0f2`: `Not able to read BranchName`
- `0x1801ae12a`: `Not able to read ContentType`

## pseudocode

```c

```
