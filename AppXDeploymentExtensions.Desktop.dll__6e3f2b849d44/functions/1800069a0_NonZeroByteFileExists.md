# NonZeroByteFileExists

- ea: `0x1800069a0`
- end: `0x180006b09`
- name: `NonZeroByteFileExists`
- size: `361`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800079d0`

## callees

- `0x18000669c`
- `0x1800069a0`
- `0x18001adb4`
- `0x1800529ec`
- `0x180087c34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a98`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800069b5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800069b5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180006a54`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180006a54`
- `KERNEL32!GetFileSizeEx` at `0x180006ab9`
- `KERNEL32!GetFileSizeEx` at `0x180006ab9`

## string_xrefs

- `0x180006a07`: `onecore\admin\appmodel\common\mrthelper.cpp`
- `0x180006a78`: `onecore\admin\appmodel\common\mrthelper.cpp`
- `0x180006ace`: `onecore\admin\appmodel\common\mrthelper.cpp`

## pseudocode

```c

```
