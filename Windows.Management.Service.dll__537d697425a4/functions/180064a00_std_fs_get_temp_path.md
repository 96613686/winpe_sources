# __std_fs_get_temp_path

- ea: `0x180064a00`
- end: `0x180064ab3`
- name: `__std_fs_get_temp_path`
- size: `179`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1801bdf80`

## callees

- `0x180064a00`
- `0x180064abc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180064a82`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180064a82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064a25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064a25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064a78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064a78`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180064a34`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180064a34`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180064a15`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180064a15`

## pseudocode

```c

```
