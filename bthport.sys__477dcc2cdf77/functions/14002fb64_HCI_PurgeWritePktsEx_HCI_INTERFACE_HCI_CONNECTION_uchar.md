# HCI_PurgeWritePktsEx(HCI_INTERFACE *,_HCI_CONNECTION *,uchar)

- ea: `0x14002fb64`
- end: `0x14002fec3`
- name: `?HCI_PurgeWritePktsEx@@YAXPEAUHCI_INTERFACE@@PEAU_HCI_CONNECTION@@E@Z`
- size: `863`
- prototype: `void __fastcall(struct HCI_INTERFACE *, struct _HCI_CONNECTION *, unsigned __int8)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14002fb2c`

## callees

- `0x140005b4c`
- `0x140005ce8`
- `0x140007028`
- `0x14000764c`
- `0x14002fb64`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14002fcb4`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14002fcd0`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14002fcb4`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14002fcd0`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14002fc53`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14002fc63`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14002fc53`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14002fc63`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002fc32`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002fcfc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002fd93`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002fc32`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002fcfc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002fd93`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002fce6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002fe33`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002fce6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002fe33`

## pseudocode

```c

```
