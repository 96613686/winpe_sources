# CXaSynch::EnqueueCloseTasks(IXaNotifySink *,ushort,xa_switch_t *,char *,ulong *)

- ea: `0x1800a1548`
- end: `0x1800a18c4`
- name: `?EnqueueCloseTasks@CXaSynch@@AEAAHPEAUIXaNotifySink@@GPEAUxa_switch_t@@PEADPEAK@Z`
- size: `892`
- prototype: `int(CXaSynch *__hidden this, struct IXaNotifySink *, unsigned __int16, struct xa_switch_t *, char *, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c790`
- `0x1800a2740`

## callees

- `0x1800240b0`
- `0x1800240f0`
- `0x1800240fc`
- `0x18009dfc0`
- `0x18009e080`
- `0x18009e1f4`
- `0x1800a0540`
- `0x1800a1548`
- `0x1800a2ce0`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a18a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a18a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a15a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a15a8`

## string_xrefs

- `0x1800a174b`: `com\complus\dtc\dtc\xatm\src\xasynch.cpp`

## pseudocode

```c

```
