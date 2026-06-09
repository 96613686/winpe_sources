# WmsgLoad(HINSTANCE__ * *)

- ea: `0x1800b1a24`
- end: `0x1800b1c73`
- name: `?WmsgLoad@@YAJPEAPEAUHINSTANCE__@@@Z`
- size: `591`
- prototype: `__int64 __fastcall(HINSTANCE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800f9e90`

## callees

- `0x180049ec0`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800b1a24`
- `0x1800c0054`
- `0x1800eb920`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800b1b40`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800b1b40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1a78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1b58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1a78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1b58`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x1800b1a5c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x1800b1a5c`

## string_xrefs

- `0x1800b1aca`: `Failed to load WMsgApi DLL: {}`
- `0x1800b1a41`: `WMsgApi.dll`
- `0x1800b1a94`: `Could not load WMsgApi DLL from path: {}.  Continuing without shutdown messages.`

## pseudocode

```c

```
