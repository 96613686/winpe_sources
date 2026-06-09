# AppXDeleteFile(ushort *,ulong,ulong *)

- ea: `0x180184ac8`
- end: `0x180184b86`
- name: `?AppXDeleteFile@@YAJPEAGKPEAK@Z`
- size: `190`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18004057c`

## callees

- `0x180184ac8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180184b10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180184b42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180184b10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180184b42`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180184b5c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180184b5c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180184ae3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180184ae3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180184b32`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180184b32`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180184b00`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180184b00`

## pseudocode

```c

```
