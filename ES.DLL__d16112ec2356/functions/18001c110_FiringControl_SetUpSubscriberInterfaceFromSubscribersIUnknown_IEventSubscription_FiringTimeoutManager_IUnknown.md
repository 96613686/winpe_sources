# FiringControl::SetUpSubscriberInterfaceFromSubscribersIUnknown(IEventSubscription *,FiringTimeoutManager &,IUnknown *,bool,SubscriberInterface &,bool &)

- ea: `0x18001c110`
- end: `0x18001c596`
- name: `?SetUpSubscriberInterfaceFromSubscribersIUnknown@FiringControl@@AEAAJPEAUIEventSubscription@@AEAVFiringTimeoutManager@@PEAUIUnknown@@_NAEAUSubscriberInterface@@AEA_N@Z`
- size: `1158`
- prototype: `int(FiringControl *__hidden this, struct IEventSubscription *, struct FiringTimeoutManager *, struct IUnknown *, bool, struct SubscriberInterface *, bool *)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001b698`
- `0x18002efc8`

## callees

- `0x180003d54`
- `0x180012654`
- `0x18001c094`
- `0x18001c0c8`
- `0x18001c110`
- `0x18001c59c`
- `0x18001c5f0`
- `0x18001c690`
- `0x18001c6c8`
- `0x18003f080`
- `0x180046010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x18001c4ee`
- `msvcrt!_resetstkoflw` at `0x18001c4ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001c152`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001c17c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001c28f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001c2e6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001c3d4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001c152`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001c17c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001c28f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001c2e6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001c3d4`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001c4b0`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001c564`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001c4b0`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001c564`

## string_xrefs

- `0x18001c588`: `com\complus\src\events\tier1\agent.cpp`
- `0x18001c26a`: `com\complus\src\events\shared\locality.cpp`

## pseudocode

```c

```
