# HCI_DibGetProtocolsInfo(HCI_INTERFACE *,_IRP *,ulong *)

- ea: `0x1401e6ca4`
- end: `0x1401e6ee3`
- name: `?HCI_DibGetProtocolsInfo@@YAJPEAUHCI_INTERFACE@@PEAU_IRP@@PEAK@Z`
- size: `575`
- prototype: `__int64 __fastcall(struct HCI_INTERFACE *, struct _IRP *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001e010`

## callees

- `0x14005fc60`
- `0x140161d7c`
- `0x1401e694c`
- `0x1401e6ca4`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401e6db8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401e6eb4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401e6db8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401e6eb4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401e6dac`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401e6ea8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401e6dac`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401e6ea8`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401e6d87`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401e6d87`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401e6d71`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401e6d71`

## pseudocode

```c

```
