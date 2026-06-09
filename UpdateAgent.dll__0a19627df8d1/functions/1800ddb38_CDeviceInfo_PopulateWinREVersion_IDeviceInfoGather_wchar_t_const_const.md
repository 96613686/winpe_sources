# CDeviceInfo::PopulateWinREVersion(IDeviceInfoGather *,wchar_t const * const)

- ea: `0x1800ddb38`
- end: `0x1800de24e`
- name: `?PopulateWinREVersion@CDeviceInfo@@AEAAJPEAVIDeviceInfoGather@@QEB_W@Z`
- size: `1814`
- prototype: `__int64 __fastcall(CDeviceInfo *__hidden this, struct IDeviceInfoGather *, const wchar_t *const)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x1800d5ee8`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x18000a0e8`
- `0x18000c4c4`
- `0x180012d94`
- `0x180023b20`
- `0x18008b38c`
- `0x1800c4a40`
- `0x1800c67d0`
- `0x1800c94c4`
- `0x1800c9838`
- `0x1800ca984`
- `0x1800cb17c`
- `0x1800d1518`
- `0x1800ddb38`
- `0x18014a96c`
- `0x1801ef4c4`
- `0x1801f250c`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800dddec`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800dddec`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800ddcbe`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800dde9f`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800ddf87`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800de200`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800ddcbe`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800dde9f`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800ddf87`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800de200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ddcce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ddeaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ddf97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ddcce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ddeaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ddf97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de210`

## string_xrefs

- `0x1800ddc42`: `Failed to load WinReAgent.dll`
- `0x1800ddfe1`: `Failed to get the installed WinRE version`
- `0x1800ddef3`: `Failed to create IWinREServicingManager`

## pseudocode

```c

```
