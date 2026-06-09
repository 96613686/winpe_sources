# HCI_ProcessAclRead(HCI_INTERFACE *,_BIP *)

- ea: `0x14002d1a0`
- end: `0x14002d59e`
- name: `?HCI_ProcessAclRead@@YAJPEAUHCI_INTERFACE@@PEAU_BIP@@@Z`
- size: `1022`
- prototype: `__int64 __fastcall(struct HCI_INTERFACE *, struct _BIP *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation`

## callers

- `0x1400ae8b0`

## callees

- `0x140005690`
- `0x140005c04`
- `0x140006f50`
- `0x140006ff0`
- `0x14000764c`
- `0x140011a74`
- `0x140028938`
- `0x14002cb6c`
- `0x14002d1a0`
- `0x14002d5a4`
- `0x14003cea4`
- `0x140042160`
- `0x140045eec`
- `0x14015ce38`
- `0x140161d7c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002d2f9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002d2f9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002d4e9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002d4e9`
- `HAL!KeQueryPerformanceCounter` at `0x14002d41a`
- `HAL!KeQueryPerformanceCounter` at `0x14002d41a`

## string_xrefs

- `0x14002d462`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\hciaclread.cpp`

## pseudocode

```c

```
