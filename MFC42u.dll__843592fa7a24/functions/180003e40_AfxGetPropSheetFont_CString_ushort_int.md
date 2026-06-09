# AfxGetPropSheetFont(CString &,ushort &,int)

- ea: `0x180003e40`
- end: `0x180003fb5`
- name: `?AfxGetPropSheetFont@@YAHAEAVCString@@AEAGH@Z`
- size: `373`
- prototype: `__int64 __fastcall(struct CString *, unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800308c0`
- `0x18005995c`

## callees

- `0x180003e40`
- `0x180003fd8`
- `0x18000b3a0`
- `0x180013520`
- `0x18002da20`
- `0x18005bfb0`
- `0x1800d7010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180003f72`
- `msvcrt!wcscpy_s` at `0x180003f72`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x180003f1c`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x180003f1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003eb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003eb3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180003f2d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180003f2d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180003e8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180003ea3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180003e8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180003ea3`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180003ef9`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180003ef9`
- `KERNEL32!GlobalAlloc` at `0x180003f5a`
- `KERNEL32!GlobalAlloc` at `0x180003f5a`

## string_xrefs

- `0x180003e83`: `COMCTL32.DLL`
- `0x180003e9c`: `KERNEL32.DLL`

## pseudocode

```c

```
