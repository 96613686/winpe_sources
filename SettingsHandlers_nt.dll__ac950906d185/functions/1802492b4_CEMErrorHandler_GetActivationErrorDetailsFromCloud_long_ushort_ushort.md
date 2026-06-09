# CEMErrorHandler::GetActivationErrorDetailsFromCloud(long,ushort * *,ushort * *)

- ea: `0x1802492b4`
- end: `0x180249749`
- name: `?GetActivationErrorDetailsFromCloud@CEMErrorHandler@@SAJJPEAPEAG0@Z`
- size: `1173`
- prototype: `__int64 __fastcall(int, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180095928`

## callees

- `0x180001bc0`
- `0x180003b7c`
- `0x18000c840`
- `0x18001d57c`
- `0x18001d5bc`
- `0x180091808`
- `0x18009204c`
- `0x18009206c`
- `0x18009208c`
- `0x180096e08`
- `0x180097a3c`
- `0x180099328`
- `0x18009a4a0`
- `0x18009a840`
- `0x1802492b4`
- `0x180249a1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18024940e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18024940e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1802493a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180249647`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1802493a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180249647`
- `ErrorDetailsCore!GetErrorDetailsWithContext` at `0x1802495d9`
- `ErrorDetailsCore!GetErrorDetailsWithContext` at `0x1802495d9`
- `ErrorDetailsCore!FreeErrorDetails` at `0x1802496ec`
- `ErrorDetailsCore!FreeErrorDetails` at `0x1802496ec`
- `SLC!SLGetWindowsInformationDWORD` at `0x180249549`
- `SLC!SLGetWindowsInformationDWORD` at `0x180249549`
- `WINBRAND!BrandingLoadString` at `0x1802493fe`
- `WINBRAND!BrandingLoadString` at `0x1802493fe`

## string_xrefs

- `0x180249542`: `Security-SPP-AllowStoreGetGenuine`
- `0x180249321`: `InstallType`
- `0x18024942c`: `InstallType`
- `0x18024944e`: `InstallType`

## pseudocode

```c

```
