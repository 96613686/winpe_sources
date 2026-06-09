# SdpL2cap_WriteAsyncComplete(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x140147260`
- end: `0x1401472ea`
- name: `?SdpL2cap_WriteAsyncComplete@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `138`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140146d00`
- `0x140147260`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x1401472cd`
- `ntoskrnl!IoQueueWorkItem` at `0x1401472cd`
- `ntoskrnl!IoReuseIrp` at `0x1401472aa`
- `ntoskrnl!IoReuseIrp` at `0x1401472aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140147277`
- `ntoskrnl!ExFreePoolWithTag` at `0x140147277`

## pseudocode

```c

```
