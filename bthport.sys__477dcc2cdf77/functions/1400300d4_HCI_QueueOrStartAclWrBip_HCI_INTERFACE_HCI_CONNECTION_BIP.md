# HCI_QueueOrStartAclWrBip(HCI_INTERFACE *,_HCI_CONNECTION *,_BIP *)

- ea: `0x1400300d4`
- end: `0x1400302b3`
- name: `?HCI_QueueOrStartAclWrBip@@YAJPEAUHCI_INTERFACE@@PEAU_HCI_CONNECTION@@PEAU_BIP@@@Z`
- size: `479`
- prototype: `__int64 __fastcall(struct HCI_INTERFACE *, struct _HCI_CONNECTION *, struct _BIP *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140031b50`

## callees

- `0x140005690`
- `0x1400070b0`
- `0x14001be50`
- `0x14002fed0`
- `0x1400300d4`
- `0x140030f20`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400301fd`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140030217`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400301fd`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140030217`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140030188`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140030198`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140030188`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140030198`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003016b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003016b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030229`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030229`

## pseudocode

```c

```
