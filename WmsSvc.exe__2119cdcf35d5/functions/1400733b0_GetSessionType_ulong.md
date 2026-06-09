# GetSessionType(ulong)

- ea: `0x1400733b0`
- end: `0x14007353b`
- name: `?GetSessionType@@YA?AW4ESessionType@@K@Z`
- size: `395`
- prototype: `__int64 __fastcall(DWORD)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400192b0`
- `0x140020100`
- `0x140022820`
- `0x14002d554`
- `0x14002db34`
- `0x1400329a8`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x1400733b0`

## import_xrefs

- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x1400733d4`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x1400733d4`
- `KERNEL32!GetLastError` at `0x14007340f`
- `KERNEL32!GetLastError` at `0x14007341e`
- `KERNEL32!GetLastError` at `0x14007340f`
- `KERNEL32!GetLastError` at `0x14007341e`
- `KERNEL32!IsDebuggerPresent` at `0x140073474`
- `KERNEL32!IsDebuggerPresent` at `0x140073474`
- `msvcrt!_wcsnicmp` at `0x1400734f2`
- `msvcrt!_wcsnicmp` at `0x1400734f2`
- `WTSAPI32!WTSFreeMemory` at `0x14007351e`
- `WTSAPI32!WTSFreeMemory` at `0x14007351e`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x140073401`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x140073401`

## string_xrefs

- `0x140073457`: `termsrv\wms\src\common\srcutils\rdslistenerconfig.cpp`
- `0x140073482`: `termsrv\wms\src\common\srcutils\rdslistenerconfig.cpp`
- `0x1400734b2`: `termsrv\wms\src\common\srcutils\rdslistenerconfig.cpp`

## pseudocode

```c

```
