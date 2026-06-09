# CServiceModule::AddScmEvent(ulong,ulong,ulong,void *)

- ea: `0x180010c30`
- end: `0x180010c9a`
- name: `?AddScmEvent@CServiceModule@@QEAAJKKKPEAX@Z`
- size: `106`
- prototype: `__int64 __fastcall(CServiceModule *this, int, int, int, struct _SLIST_ENTRY *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180012700`
- `0x18002a310`
- `0x18002a380`

## callees

- `0x180010c30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180010c4e`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180010c4e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010c82`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010c82`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180010c75`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180010c75`

## pseudocode

```c

```
