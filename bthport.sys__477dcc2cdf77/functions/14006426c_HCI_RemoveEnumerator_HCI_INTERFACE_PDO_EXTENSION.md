# HCI_RemoveEnumerator(HCI_INTERFACE *,PDO_EXTENSION *)

- ea: `0x14006426c`
- end: `0x1400644b2`
- name: `?HCI_RemoveEnumerator@@YAXPEAUHCI_INTERFACE@@PEAUPDO_EXTENSION@@@Z`
- size: `582`
- prototype: `void __fastcall(struct HCI_INTERFACE *, struct PDO_EXTENSION *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14012d92c`

## callees

- `0x14006426c`
- `0x140161d7c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14006446e`
- `ntoskrnl!ObfDereferenceObject` at `0x14006446e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064422`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064422`
- `ntoskrnl!KeWaitForSingleObject` at `0x140064411`
- `ntoskrnl!KeWaitForSingleObject` at `0x140064411`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006429e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140064431`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006429e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140064431`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400643d8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140064451`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400643d8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140064451`

## pseudocode

```c

```
