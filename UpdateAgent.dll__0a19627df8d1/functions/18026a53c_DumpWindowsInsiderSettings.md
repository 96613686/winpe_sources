# DumpWindowsInsiderSettings

- ea: `0x18026a53c`
- end: `0x18026a9a2`
- name: `DumpWindowsInsiderSettings`
- size: `1126`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18026d9b0`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x180006a18`
- `0x180012460`
- `0x1800125bc`
- `0x1800692fc`
- `0x18014d3d4`
- `0x18014d69c`
- `0x18014e384`
- `0x180268c84`
- `0x18026a53c`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18026a66e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18026a66e`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x18026a5fd`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x18026a5fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18026a636`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18026a6d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18026a778`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18026a924`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18026a636`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18026a6d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18026a778`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18026a924`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18026a646`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18026a6e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18026a788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18026a934`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18026a646`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18026a6e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18026a788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18026a934`

## string_xrefs

- `0x18026a5f2`: `ntdll.dll`
- `0x18026a60d`: `Failed to obtain handle to ntdll.dll`
- `0x18026a7dc`: `Not able to read BranchName`
- `0x18026a814`: `Not able to read ContentType`
- `0x18026a74f`: `Not able to find Windows Insider Program settings`
- `0x18026a84c`: `Not able to read Ring`
- `0x18026a884`: `Not able to read IsBuildFlightingEnabled`

## pseudocode

```c

```
