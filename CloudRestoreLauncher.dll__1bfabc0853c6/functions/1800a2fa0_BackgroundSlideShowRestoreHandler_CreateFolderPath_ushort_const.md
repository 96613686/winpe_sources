# BackgroundSlideShowRestoreHandler::CreateFolderPath(ushort const *)

- ea: `0x1800a2fa0`
- end: `0x1800a302c`
- name: `?CreateFolderPath@BackgroundSlideShowRestoreHandler@@AEAA_NPEBG@Z`
- size: `140`
- prototype: `char __fastcall(BackgroundSlideShowRestoreHandler *this, WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1800a35e8`

## callees

- `0x18001cfa4`
- `0x1800a2e18`
- `0x1800a2fa0`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x1800a2fac`
- `KERNEL32!GetFileAttributesW` at `0x1800a2fac`
- `KERNEL32!GetLastError` at `0x1800a2fb7`
- `KERNEL32!GetLastError` at `0x1800a2fb7`

## string_xrefs

- `0x1800a3017`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`

## pseudocode

```c

```
