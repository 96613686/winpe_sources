# GetTsAudioProtocol(ulong)

- ea: `0x180030f98`
- end: `0x180031175`
- name: `?GetTsAudioProtocol@@YAIK@Z`
- size: `477`
- prototype: `unsigned int __fastcall(DWORD SessionId)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180030e40`

## callees

- `0x180030f98`
- `0x1800cd8d0`
- `0x1800ce774`
- `0x1800d07b8`
- `0x1800d0934`

## import_xrefs

- `ntdll!RtlGetCurrentServiceSessionId` at `0x180031087`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180031087`
- `ntdll!RtlGetActiveConsoleId` at `0x180031035`
- `ntdll!RtlGetActiveConsoleId` at `0x180031035`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x18003113e`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x18003113e`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x18003102b`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x18003102b`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800310c6`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180031106`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800310c6`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180031106`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x1800310b4`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x1800310e6`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x1800310b4`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x1800310e6`

## pseudocode

```c

```
