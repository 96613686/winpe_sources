# CActivationBrokerManager::_GetPlugin(_GUID,IActivationBrokerPlugin * *)

- ea: `0x18004ada0`
- end: `0x18004afea`
- name: `?_GetPlugin@CActivationBrokerManager@@AEAAJU_GUID@@PEAPEAUIActivationBrokerPlugin@@@Z`
- size: `586`
- prototype: `__int64 __fastcall(CActivationBrokerManager *__hidden this, struct _GUID *__struct_ptr, struct IActivationBrokerPlugin **)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014610`
- `0x180064870`

## callees

- `0x180011328`
- `0x180015b7c`
- `0x18003b4a0`
- `0x18003dc20`
- `0x18004ada0`
- `0x18004aff0`
- `0x18005ae90`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004af82`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004af82`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004adf0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004adf0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004af20`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004af20`

## pseudocode

```c

```
