# GetFinalPath

- ea: `0x180034bd4`
- end: `0x180034d26`
- name: `GetFinalPath`
- size: `338`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callers

- `0x180034b38`
- `0x180035434`

## callees

- `0x180034bd4`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180034c6b`
- `ntdll!RtlAllocateHeap` at `0x180034c6b`
- `ntdll!RtlFreeHeap` at `0x180034ca3`
- `ntdll!RtlFreeHeap` at `0x180034d04`
- `ntdll!RtlFreeHeap` at `0x180034ca3`
- `ntdll!RtlFreeHeap` at `0x180034d04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034c2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034c3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034ccd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034c2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034c3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034ccd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034c03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034c03`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180034c1b`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180034c1b`

## pseudocode

```c

```
