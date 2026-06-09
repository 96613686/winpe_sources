# Windows::COM::GetCurrentDllWin32Path(void *,Windows::Auto<_LUNICODE_STRING> *)

- ea: `0x18008eebc`
- end: `0x18008f279`
- name: `?GetCurrentDllWin32Path@COM@Windows@@YAJPEAXPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z`
- size: `957`
- prototype: `__int64 __fastcall(LPCWSTR lpModuleName)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008f280`

## callees

- `0x180019bdc`
- `0x18003ff34`
- `0x180048d24`
- `0x180050f18`
- `0x180054484`
- `0x1800704cc`
- `0x18008eebc`
- `0x1800aa104`
- `0x1800aa16c`
- `0x1800eb920`
- `0x1800ec86c`
- `0x1800ef360`
- `0x180281be8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x18008ef3d`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x18008ef3d`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18008f05b`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18008f05b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ef4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ef64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f1c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f22f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ef4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ef64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f1c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f22f`

## string_xrefs

- `0x18008ef08`: `Windows::COM::GetCurrentDllWin32Path`
- `0x18008ef8b`: `Windows::COM::GetCurrentDllWin32Path`
- `0x18008f1ee`: `Windows::COM::GetCurrentDllWin32Path`
- `0x18008ef01`: `Not-null check failed: DirectoryOut`
- `0x18008eeee`: `onecore\base\wcp\rtllib\win32lib\dllpath_library.cpp`
- `0x18008ef80`: `onecore\base\wcp\rtllib\win32lib\dllpath_library.cpp`
- `0x18008f1e3`: `onecore\base\wcp\rtllib\win32lib\dllpath_library.cpp`

## pseudocode

```c

```
