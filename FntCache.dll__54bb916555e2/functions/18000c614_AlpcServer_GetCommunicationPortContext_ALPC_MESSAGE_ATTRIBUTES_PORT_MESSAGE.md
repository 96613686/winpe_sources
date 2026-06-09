# AlpcServer::GetCommunicationPortContext(_ALPC_MESSAGE_ATTRIBUTES *,_PORT_MESSAGE *)

- ea: `0x18000c614`
- end: `0x18000c66c`
- name: `?GetCommunicationPortContext@AlpcServer@@AEAAAEAVCommunicationPortContext@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@PEAU_PORT_MESSAGE@@@Z`
- size: `88`
- prototype: `struct CommunicationPortContext *__fastcall(AlpcServer *__hidden this, struct _ALPC_MESSAGE_ATTRIBUTES *, struct _PORT_MESSAGE *)`
- caller_count: `12`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c13c`
- `0x18000c20c`
- `0x18000c564`
- `0x18000ff74`
- `0x180095cac`
- `0x18009664c`
- `0x18009a610`
- `0x1800b9f84`
- `0x1800ba124`
- `0x1800ba1ec`
- `0x1800ba4ec`
- `0x1800ba6c0`

## callees

- `0x18000c614`
- `0x1800e6010`

## import_xrefs

- `ntdll!AlpcGetMessageAttribute` at `0x18000c634`
- `ntdll!AlpcGetMessageAttribute` at `0x18000c634`

## pseudocode

```c

```
