# HCI_WriteStoredLinkKey(HCI_INTERFACE *,_IRP *)

- ea: `0x1400a6ca0`
- end: `0x1400a7197`
- name: `?HCI_WriteStoredLinkKey@@YAJPEAUHCI_INTERFACE@@PEAU_IRP@@@Z`
- size: `1271`
- prototype: `__int64 __fastcall(struct HCI_INTERFACE *, struct _IRP *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x14001d31c`

## callees

- `0x140005608`
- `0x140005690`
- `0x140005748`
- `0x140005b4c`
- `0x140005ce8`
- `0x14000764c`
- `0x14005b2d4`
- `0x14005fc60`
- `0x1400a652c`
- `0x1400a6830`
- `0x1400a6ca0`
- `0x140161d7c`
- `0x140162008`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a6f7f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a6f7f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400a6f73`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400a6f73`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400a6f29`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400a6f29`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a6f13`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a6f13`
- `ntoskrnl!ExAllocatePool2` at `0x1400a7002`
- `ntoskrnl!ExAllocatePool2` at `0x1400a708e`
- `ntoskrnl!ExAllocatePool2` at `0x1400a7002`
- `ntoskrnl!ExAllocatePool2` at `0x1400a708e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400a6f4f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400a6f4f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a6f64`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a6f64`

## pseudocode

```c

```
