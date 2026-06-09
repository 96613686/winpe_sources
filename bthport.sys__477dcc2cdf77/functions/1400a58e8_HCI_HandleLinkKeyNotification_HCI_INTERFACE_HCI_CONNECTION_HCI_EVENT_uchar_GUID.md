# HCI_HandleLinkKeyNotification(HCI_INTERFACE *,_HCI_CONNECTION *,_HCI_EVENT *,uchar,_GUID *)

- ea: `0x1400a58e8`
- end: `0x1400a620a`
- name: `?HCI_HandleLinkKeyNotification@@YAXPEAUHCI_INTERFACE@@PEAU_HCI_CONNECTION@@PEAT_HCI_EVENT@@EPEAU_GUID@@@Z`
- size: `2338`
- prototype: `void __usercall(struct HCI_INTERFACE *@<rcx>, struct _HCI_CONNECTION *@<rdx>, union _HCI_EVENT *@<r8>, unsigned __int8@<r9b>, struct _GUID *)`
- caller_count: `2`
- callee_count: `26`
- tags: ``

## callers

- `0x1400a42b0`
- `0x1400ae670`

## callees

- `0x140005608`
- `0x140005690`
- `0x140005748`
- `0x14001c148`
- `0x14001fddc`
- `0x14003a890`
- `0x14003fe84`
- `0x140041474`
- `0x140052de4`
- `0x14005b388`
- `0x14005b478`
- `0x140060dc4`
- `0x1400a5550`
- `0x1400a58e8`
- `0x1400a652c`
- `0x1400a7f84`
- `0x1400a7fb4`
- `0x1400a7fd4`
- `0x1400a80d8`
- `0x1400a81d8`
- `0x14014f090`
- `0x140161d7c`
- `0x140165540`
- `0x140165940`
- `0x1401be5f8`
- `0x1401c0360`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a5c38`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a5fe1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a5c38`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a5fe1`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400a5c2c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400a5fd5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400a5c2c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400a5fd5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400a5c15`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400a5cbe`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400a5c15`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400a5cbe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a5bff`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a5cab`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a5bff`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a5cab`
- `ntoskrnl!KeCancelTimer` at `0x1400a60fc`
- `ntoskrnl!KeCancelTimer` at `0x1400a60fc`
- `ntoskrnl!ExAllocatePool2` at `0x1400a6012`
- `ntoskrnl!ExAllocatePool2` at `0x1400a6012`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400a60dd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400a60dd`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a6134`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a6134`

## pseudocode

```c

```
