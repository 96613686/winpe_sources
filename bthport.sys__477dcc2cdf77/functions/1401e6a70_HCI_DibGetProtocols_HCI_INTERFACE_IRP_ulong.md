# HCI_DibGetProtocols(HCI_INTERFACE *,_IRP *,ulong *)

- ea: `0x1401e6a70`
- end: `0x1401e6c9d`
- name: `?HCI_DibGetProtocols@@YAJPEAUHCI_INTERFACE@@PEAU_IRP@@PEAK@Z`
- size: `557`
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
- `0x1401e6a70`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401e6b60`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401e6c5e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401e6b60`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401e6c5e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401e6b54`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401e6c52`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401e6b54`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401e6c52`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401e6b2f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401e6b2f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401e6b19`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401e6b19`

## pseudocode

```c

```
