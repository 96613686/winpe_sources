# IsolationAwareLoadLibraryExW

- ea: `0x18001c738`
- end: `0x18001c80b`
- name: `IsolationAwareLoadLibraryExW`
- size: `211`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180014c48`
- `0x180018bf8`

## callees

- `0x18001c738`
- `0x18001c814`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001c79c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001c79c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c7ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180272461`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c7ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180272461`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c7f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18027248d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c7f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18027248d`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18001c7e5`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18027247b`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18001c7e5`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18027247b`

## pseudocode

```c

```
