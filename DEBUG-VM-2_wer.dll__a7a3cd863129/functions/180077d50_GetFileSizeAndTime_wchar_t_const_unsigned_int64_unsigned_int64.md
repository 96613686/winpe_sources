# GetFileSizeAndTime(wchar_t const *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x180077d50`
- end: `0x180077e21`
- name: `?GetFileSizeAndTime@@YAJPEB_WPEA_K1@Z`
- size: `209`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001b678`
- `0x1800722a0`

## callees

- `0x18000716c`
- `0x180007e10`
- `0x180077d50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077db7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077db7`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180077dd0`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180077dd0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180077da0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180077da0`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180077de7`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180077de7`

## pseudocode

```c

```
