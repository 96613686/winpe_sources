# IsFileNotASymlink

- ea: `0x18007c85c`
- end: `0x18007c96c`
- name: `IsFileNotASymlink`
- size: `272`
- prototype: `__int64 __fastcall(HANDLE hFile, wchar_t *String1)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x18007c5d8`

## callees

- `0x18007c85c`
- `0x1800e7260`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18007c92a`
- `msvcrt!_wcsnicmp` at `0x18007c92a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c93d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c93d`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18007c8a7`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18007c8a7`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18007c8dd`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18007c8dd`

## pseudocode

```c

```
