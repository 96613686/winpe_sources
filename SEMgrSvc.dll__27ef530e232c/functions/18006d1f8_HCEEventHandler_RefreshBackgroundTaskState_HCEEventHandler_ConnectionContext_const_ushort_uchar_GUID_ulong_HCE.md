# HCEEventHandler::RefreshBackgroundTaskState(HCEEventHandler::ConnectionContext const &,ushort,uchar *,_GUID *,ulong *,HCEEventHandler::ApduCommandType *,void * *)

- ea: `0x18006d1f8`
- end: `0x18006d8e1`
- name: `?RefreshBackgroundTaskState@HCEEventHandler@@AEAAJAEBUConnectionContext@1@GPEAEPEAU_GUID@@PEAKPEAW4ApduCommandType@1@PEAPEAX@Z`
- size: `1769`
- prototype: `__int64 __usercall@<rax>(HCEEventHandler *__hidden this@<rcx>, const struct HCEEventHandler::ConnectionContext *@<rdx>, unsigned __int16@<r8w>, unsigned __int8 *@<r9>, struct _GUID *, unsigned int *, enum HCEEventHandler::ApduCommandType *, void **)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18006ce44`

## callees

- `0x1800010f4`
- `0x1800036d0`
- `0x1800049a0`
- `0x1800049c4`
- `0x180004e9c`
- `0x1800057c6`
- `0x180005840`
- `0x180005858`
- `0x180065e70`
- `0x18006808c`
- `0x18006c048`
- `0x18006c30c`
- `0x18006d1f8`
- `0x1800904e0`
- `0x18009d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006d375`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006d375`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18006d65a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18006d6a5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18006d65a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18006d6a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006d38a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006d4b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006d38a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006d4b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006d353`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006d456`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006d353`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006d456`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006d498`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006d498`

## pseudocode

```c

```
