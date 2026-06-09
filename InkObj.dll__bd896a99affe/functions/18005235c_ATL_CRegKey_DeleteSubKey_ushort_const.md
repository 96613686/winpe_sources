# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18005235c`
- end: `0x180052410`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18003dbcc`
- `0x18005c060`

## callees

- `0x18005235c`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800523ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800523ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180052381`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180052381`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800523ae`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800523ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180052396`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800523c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180052396`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800523c3`

## string_xrefs

- `0x18005237a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18005238c`: `RegDeleteKeyExW`
- `0x1800523a5`: `advapi32.dll`
- `0x1800523b9`: `RegDeleteKeyW`

## pseudocode

```c

```
