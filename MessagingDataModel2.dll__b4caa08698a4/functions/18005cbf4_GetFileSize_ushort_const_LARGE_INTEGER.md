# GetFileSize(ushort const *,_LARGE_INTEGER *)

- ea: `0x18005cbf4`
- end: `0x18005ccd0`
- name: `?GetFileSize@@YAJPEBGPEAT_LARGE_INTEGER@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(const unsigned __int16 *, union _LARGE_INTEGER *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18006cba8`
- `0x18006ed88`

## callees

- `0x18005ca28`
- `0x18005cbf4`
- `0x18005cd08`
- `0x1800c6940`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cc49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cc81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cc49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cc81`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18005cc77`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18005cc77`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005cc38`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005cc38`

## pseudocode

```c

```
