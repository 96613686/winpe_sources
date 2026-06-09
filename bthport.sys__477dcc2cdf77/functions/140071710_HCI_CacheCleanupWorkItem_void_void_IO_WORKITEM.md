# HCI_CacheCleanupWorkItem(void *,void *,_IO_WORKITEM *)

- ea: `0x140071710`
- end: `0x140071858`
- name: `?HCI_CacheCleanupWorkItem@@YAXPEAX0PEAU_IO_WORKITEM@@@Z`
- size: `328`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140005608`
- `0x140005b4c`
- `0x1400712a0`
- `0x140071710`
- `0x140161d7c`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x14007183e`
- `ntoskrnl!IoFreeWorkItem` at `0x14007183e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140071794`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140071794`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400717af`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400717af`

## pseudocode

```c

```
