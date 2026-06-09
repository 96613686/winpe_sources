# Windows::Compat::Appraiser::Utilities::FindUserSession(void * *,int *)

- ea: `0x180087e70`
- end: `0x180087ff0`
- name: `?FindUserSession@Utilities@Appraiser@Compat@Windows@@SAJPEAPEAXPEAH@Z`
- size: `384`
- prototype: `__int64 __fastcall(void **, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800911bc`
- `0x180092f40`

## callees

- `0x18001a2f4`
- `0x1800301d0`
- `0x180087e70`

## import_xrefs

- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x180087e9c`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x180087e9c`
- `KERNEL32!CloseHandle` at `0x180087f85`
- `KERNEL32!CloseHandle` at `0x180087fcc`
- `KERNEL32!CloseHandle` at `0x180087f85`
- `KERNEL32!CloseHandle` at `0x180087fcc`
- `KERNEL32!GetLastError` at `0x180087ef3`
- `KERNEL32!GetLastError` at `0x180087f1e`
- `KERNEL32!GetLastError` at `0x180087f3d`
- `KERNEL32!GetLastError` at `0x180087ef3`
- `KERNEL32!GetLastError` at `0x180087f1e`
- `KERNEL32!GetLastError` at `0x180087f3d`
- `WTSAPI32!WTSQueryUserToken` at `0x180087ec6`
- `WTSAPI32!WTSQueryUserToken` at `0x180087f9b`
- `WTSAPI32!WTSQueryUserToken` at `0x180087ec6`
- `WTSAPI32!WTSQueryUserToken` at `0x180087f9b`
- `WTSAPI32!WTSFreeMemory` at `0x180087fdb`
- `WTSAPI32!WTSFreeMemory` at `0x180087fdb`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x180087ee9`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x180087ee9`

## string_xrefs

- `0x180087f58`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180087f06`: `Windows::Compat::Appraiser::Utilities::FindUserSession`
- `0x180087f47`: `Windows::Compat::Appraiser::Utilities::FindUserSession`

## pseudocode

```c

```
