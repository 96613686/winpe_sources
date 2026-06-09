# HCI_CacheCleanup(HCI_INTERFACE *,unsigned __int64,_LARGE_INTEGER)

- ea: `0x1400712a0`
- end: `0x14007150f`
- name: `?HCI_CacheCleanup@@YAXPEAUHCI_INTERFACE@@_KT_LARGE_INTEGER@@@Z`
- size: `623`
- prototype: `void __fastcall(struct HCI_INTERFACE *, unsigned __int64, union _LARGE_INTEGER)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140071520`
- `0x140071710`

## callees

- `0x14000764c`
- `0x14005fe30`
- `0x14006415c`
- `0x1400712a0`
- `0x140161d7c`
- `0x1401be4a8`

## import_xrefs

- `ntoskrnl!ExSystemTimeToLocalTime` at `0x1400712fa`
- `ntoskrnl!ExSystemTimeToLocalTime` at `0x1400712fa`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1400712e6`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1400712e6`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400714bd`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400714bd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140071314`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140071314`
- `ntoskrnl!KeReleaseSpinLock` at `0x140071477`
- `ntoskrnl!KeReleaseSpinLock` at `0x140071477`

## pseudocode

```c

```
