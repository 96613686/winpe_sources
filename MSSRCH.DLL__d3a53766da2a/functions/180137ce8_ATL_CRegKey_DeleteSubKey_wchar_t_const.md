# ATL::CRegKey::DeleteSubKey(wchar_t const *)

- ea: `0x180137ce8`
- end: `0x180137d9d`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const wchar_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1801355e0`
- `0x18013b55c`
- `0x18013ba2c`

## callees

- `0x180137ce8`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180137d3a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180137d3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180137d22`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180137d4f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180137d22`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180137d4f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180137d0d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180137d0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180137d8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180137d8b`

## string_xrefs

- `0x180137d18`: `RegDeleteKeyExW`
- `0x180137d06`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180137d33`: `advapi32.dll`
- `0x180137d45`: `RegDeleteKeyW`

## pseudocode

```c

```
