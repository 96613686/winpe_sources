# GetTsAudioProtocol(ulong)

- ea: `0x180030e38`
- end: `0x180031015`
- name: `?GetTsAudioProtocol@@YAIK@Z`
- size: `477`
- prototype: `unsigned int __fastcall(DWORD SessionId)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180030ce0`

## callees

- `0x180030e38`
- `0x1800cf8c0`
- `0x1800d0764`
- `0x1800d27a8`
- `0x1800d2924`

## import_xrefs

- `ntdll!RtlGetCurrentServiceSessionId` at `0x180030f27`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180030f27`
- `ntdll!RtlGetActiveConsoleId` at `0x180030ed5`
- `ntdll!RtlGetActiveConsoleId` at `0x180030ed5`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x180030fde`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x180030fde`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x180030ecb`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x180030ecb`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180030f66`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180030fa6`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180030f66`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180030fa6`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x180030f54`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x180030f86`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x180030f54`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x180030f86`

## pseudocode

```c

```
