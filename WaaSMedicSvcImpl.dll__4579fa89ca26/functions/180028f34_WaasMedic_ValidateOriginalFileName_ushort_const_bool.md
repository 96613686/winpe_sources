# WaasMedic::ValidateOriginalFileName(ushort const *,bool &)

- ea: `0x180028f34`
- end: `0x180029358`
- name: `?ValidateOriginalFileName@WaasMedic@@YAJPEBGAEA_N@Z`
- size: `1060`
- prototype: `__int64 __fastcall(LPCWSTR lpwstrFilename, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, installer_update`

## callers

- `0x180028bec`

## callees

- `0x1800050a0`
- `0x180005c28`
- `0x1800098f0`
- `0x180009cd0`
- `0x18000f860`
- `0x180010db4`
- `0x18001d3ec`
- `0x18001e5a0`
- `0x180028f34`
- `0x180029360`
- `0x18002a300`
- `0x18002a4e4`
- `0x18002e81c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002928b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002928b`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x180029037`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x180029037`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002914e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800291b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002914e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800291b6`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800291fb`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180029251`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800291fb`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180029251`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x180029142`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x180029142`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x1800291ac`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x1800291ac`

## string_xrefs

- `0x1800292f0`: `Caller passed library name that did not end in "dll".`

## pseudocode

```c

```
