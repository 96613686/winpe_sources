# Windows::COM::GetCurrentDllWin32Path(void *,Windows::Auto<_LUNICODE_STRING> *)

- ea: `0x180050b80`
- end: `0x180050fc7`
- name: `?GetCurrentDllWin32Path@COM@Windows@@YAJPEAXPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z`
- size: `1095`
- prototype: `__int64 __fastcall(LPCWSTR lpModuleName)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ea40`
- `0x180050fd0`

## callees

- `0x1800031d0`
- `0x180003bb0`
- `0x18000aedc`
- `0x18000e098`
- `0x180047e6c`
- `0x180047f24`
- `0x180049274`
- `0x180049530`
- `0x1800497c0`
- `0x18005060c`
- `0x180050a40`
- `0x180050b80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050c21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050c38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050f0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050f7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050c21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050c38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050f0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050f7a`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x180050c11`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x180050c11`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x180050d43`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x180050d43`

## string_xrefs

- `0x180050bd2`: `Not-null check failed: DirectoryOut`
- `0x180050bb4`: `onecore\base\wcp\rtllib\win32lib\dllpath_library.cpp`
- `0x180050c4e`: `onecore\base\wcp\rtllib\win32lib\dllpath_library.cpp`
- `0x180050f21`: `onecore\base\wcp\rtllib\win32lib\dllpath_library.cpp`
- `0x180050bbf`: `Windows::COM::GetCurrentDllWin32Path`
- `0x180050c59`: `Windows::COM::GetCurrentDllWin32Path`
- `0x180050f2c`: `Windows::COM::GetCurrentDllWin32Path`

## pseudocode

```c

```
