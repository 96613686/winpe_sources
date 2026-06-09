# AlpcClientConnection::CreateClientPort(_OBJECT_ATTRIBUTES *,_OBJECT_ATTRIBUTES *,_ALPC_PORT_ATTRIBUTES *,void *,bool,ulong,ConnectionParams const &,void * *)

- ea: `0x1800639c4`
- end: `0x180063b89`
- name: `?CreateClientPort@AlpcClientConnection@@AEAAJPEAU_OBJECT_ATTRIBUTES@@0PEAU_ALPC_PORT_ATTRIBUTES@@PEAX_NKAEBUConnectionParams@@PEAPEAX@Z`
- size: `453`
- prototype: `__int64 __fastcall(AlpcClientConnection *__hidden this, struct _OBJECT_ATTRIBUTES *, struct _OBJECT_ATTRIBUTES *, struct _ALPC_PORT_ATTRIBUTES *, void *, bool, unsigned int, const struct ConnectionParams *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180063738`

## callees

- `0x180007d80`
- `0x18003773c`
- `0x18003950c`
- `0x1800639c4`
- `0x18009e054`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180063acd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180063acd`
- `ntdll!AlpcInitializeMessageAttribute` at `0x180063b0b`
- `ntdll!AlpcInitializeMessageAttribute` at `0x180063b34`
- `ntdll!AlpcInitializeMessageAttribute` at `0x180063b0b`
- `ntdll!AlpcInitializeMessageAttribute` at `0x180063b34`
- `ntdll!AlpcGetMessageAttribute` at `0x180063b49`
- `ntdll!AlpcGetMessageAttribute` at `0x180063b49`
- `ntdll!NtAlpcConnectPortEx` at `0x180063a82`
- `ntdll!NtAlpcConnectPortEx` at `0x180063a82`

## pseudocode

```c

```
