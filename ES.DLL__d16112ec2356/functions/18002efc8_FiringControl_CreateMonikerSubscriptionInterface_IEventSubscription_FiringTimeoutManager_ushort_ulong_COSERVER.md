# FiringControl::CreateMonikerSubscriptionInterface(IEventSubscription *,FiringTimeoutManager &,ushort *,ulong,_COSERVERINFO *,SubscriberInterface &,bool &)

- ea: `0x18002efc8`
- end: `0x18002f1d0`
- name: `?CreateMonikerSubscriptionInterface@FiringControl@@AEAAJPEAUIEventSubscription@@AEAVFiringTimeoutManager@@PEAGKPEAU_COSERVERINFO@@AEAUSubscriberInterface@@AEA_N@Z`
- size: `520`
- prototype: `__int64 __fastcall(FiringControl *__hidden this, struct IEventSubscription *, struct FiringTimeoutManager *, LPCWSTR pszName, unsigned int, struct _COSERVERINFO *, struct SubscriberInterface *, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002f1d8`

## callees

- `0x180003d54`
- `0x18001b7e0`
- `0x18001c110`
- `0x18001c59c`
- `0x18001c5f0`
- `0x18001c690`
- `0x18001c8f0`
- `0x180028f40`
- `0x18002efc8`
- `0x180043510`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002f042`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002f0a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002f0ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800456e4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002f042`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002f0a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002f0ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800456e4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002f068`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002f068`
- `ole32!CoGetObject` at `0x18002f0de`
- `ole32!CoGetObject` at `0x18002f0de`

## string_xrefs

- `0x18002f125`: `com\complus\src\events\tier1\agent.cpp`

## pseudocode

```c

```
