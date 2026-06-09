# InternetSetOptionA

- ea: `0x1800610f0`
- end: `0x180064055`
- name: `InternetSetOptionA`
- size: `12133`
- prototype: `BOOL __stdcall(HINTERNET hInternet, DWORD dwOption, LPVOID lpBuffer, DWORD dwBufferLength)`
- caller_count: `5`
- callee_count: `65`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800ccce4`
- `0x1800e45f0`
- `0x180137a20`
- `0x180182a1c`
- `0x180190790`

## callees

- `0x180009cf0`
- `0x18000c700`
- `0x180019d20`
- `0x18002658c`
- `0x18002be34`
- `0x18002cbc8`
- `0x18003e350`
- `0x180060d30`
- `0x180060f00`
- `0x1800610f0`
- `0x1800641c0`
- `0x180064560`
- `0x18007ad20`
- `0x1800b810c`
- `0x1800b8714`
- `0x1800c13c0`
- `0x1800c14f4`
- `0x1800c2d90`
- `0x1800cd820`
- `0x1800cdc70`
- `0x1800d1e00`
- `0x1800d5e78`
- `0x1800e4580`
- `0x1800e96f0`
- `0x1800f3618`
- `0x1800f4ac8`
- `0x180104410`
- `0x1801161a4`
- `0x180117ba8`
- `0x18011d544`
- `0x18011e174`
- `0x180124588`
- `0x180125ccc`
- `0x1801282a8`
- `0x180128eb0`
- `0x18012fa90`
- `0x1801316bc`
- `0x180133504`
- `0x180134cb4`
- `0x1801368c4`
- `0x18013c4c8`
- `0x18013c690`
- `0x1801417f8`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x180157e90`
- `0x180160508`
- `0x180161378`
- `0x180166c8c`
- `0x180166e34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061ba7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061f54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062231`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062302`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006285c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800628be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062afb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061ba7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061f54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062231`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062302`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006285c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800628be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062afb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180061b7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180061f1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006220d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800622de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006282f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180062882`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800629eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180061b7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180061f1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006220d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800622de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006282f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180062882`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800629eb`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180061db5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180061db5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061573`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061589`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061573`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061589`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006151e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006151e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800615bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800615bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180061631`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180062eb6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180061631`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180062eb6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180062848`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800628aa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180062848`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800628aa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006141e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006141e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180061426`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180061426`
- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x1800613dd`
- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x180061866`
- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x180061d69`
- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x1800613dd`
- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x180061866`
- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x180061d69`
- `ntdll!EtwEventActivityIdControl` at `0x1800612fe`
- `ntdll!EtwEventActivityIdControl` at `0x180061342`
- `ntdll!EtwEventActivityIdControl` at `0x180061557`
- `ntdll!EtwEventActivityIdControl` at `0x1800612fe`
- `ntdll!EtwEventActivityIdControl` at `0x180061342`
- `ntdll!EtwEventActivityIdControl` at `0x180061557`
- `ntdll!RtlGetLastNtStatus` at `0x180061642`
- `ntdll!RtlGetLastNtStatus` at `0x180061642`

## pseudocode

```c

```
