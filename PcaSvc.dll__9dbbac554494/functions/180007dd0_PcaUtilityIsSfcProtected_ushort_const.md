# PcaUtilityIsSfcProtected(ushort const *)

- ea: `0x180007dd0`
- end: `0x180007eb7`
- name: `?PcaUtilityIsSfcProtected@@YAHPEBG@Z`
- size: `231`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180007720`

## callees

- `0x180007dd0`
- `0x180012920`
- `0x1800f1f10`
- `0x1800f7010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180007e1e`
- `msvcrt!wcscat_s` at `0x180007e1e`
- `msvcrt!wcscpy_s` at `0x180007e07`
- `msvcrt!wcscpy_s` at `0x180007e07`
- `ntdll!RtlGetNtSystemRoot` at `0x180007df4`
- `ntdll!RtlGetNtSystemRoot` at `0x180007df4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007e3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007e3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ea2`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180007e29`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180007e29`

## string_xrefs

- `0x180007e0d`: `\System32\sfc_os.dll`
- `0x180007e7e`: `LoadLibrary failed: [%d]`

## pseudocode

```c

```
