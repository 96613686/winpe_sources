# HCI_DibUpdate(HCI_INTERFACE *,_IRP *,ulong *)

- ea: `0x14005e480`
- end: `0x14005efbc`
- name: `?HCI_DibUpdate@@YAJPEAUHCI_INTERFACE@@PEAU_IRP@@PEAK@Z`
- size: `2876`
- prototype: `__int64 __fastcall(struct HCI_INTERFACE *, struct _IRP *, unsigned int *)`
- caller_count: `1`
- callee_count: `26`
- tags: `installer_update`

## callers

- `0x14001e010`

## callees

- `0x1400043d0`
- `0x140005504`
- `0x140005608`
- `0x140005690`
- `0x14000bdb8`
- `0x14000c74c`
- `0x140059630`
- `0x14005a290`
- `0x14005b478`
- `0x14005e480`
- `0x14005fc60`
- `0x14006405c`
- `0x1400640fc`
- `0x1400688a8`
- `0x1400694a0`
- `0x140161d7c`
- `0x140165540`
- `0x140165940`
- `0x1401c053c`
- `0x1401c06a4`
- `0x1401c14d0`
- `0x1401c15e4`
- `0x1401c1a48`
- `0x1401e8768`
- `0x1401e88cc`
- `0x1401e8a98`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005ef74`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005ef74`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005ef68`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005ef68`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005e82f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005e82f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e81c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e81c`
- `ntoskrnl!wcsnlen` at `0x14005e7b1`
- `ntoskrnl!wcsnlen` at `0x14005e7b1`
- `ntoskrnl!RtlUnicodeToUTF8N` at `0x14005ecbe`
- `ntoskrnl!RtlUnicodeToUTF8N` at `0x14005ecbe`
- `ntoskrnl!ZwClose` at `0x14005ef55`
- `ntoskrnl!ZwClose` at `0x14005ef55`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005e845`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005ecff`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005ed4f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005edda`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005e845`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005ecff`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005ed4f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005edda`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005eb71`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005ed17`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005ed67`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005ef1c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005eb71`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005ed17`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005ed67`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005ef1c`

## pseudocode

```c

```
