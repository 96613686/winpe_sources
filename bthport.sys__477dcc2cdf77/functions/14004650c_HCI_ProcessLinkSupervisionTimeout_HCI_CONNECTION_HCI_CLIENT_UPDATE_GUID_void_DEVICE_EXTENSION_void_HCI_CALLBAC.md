# HCI_ProcessLinkSupervisionTimeout(_HCI_CONNECTION *,_HCI_CLIENT_UPDATE *,_GUID *,void (*)(DEVICE_EXTENSION *,void *,_HCI_CALLBACK_DATA *),void *)

- ea: `0x14004650c`
- end: `0x14004687a`
- name: `?HCI_ProcessLinkSupervisionTimeout@@YAEPEAU_HCI_CONNECTION@@PEAU_HCI_CLIENT_UPDATE@@PEAU_GUID@@P6AXPEAUDEVICE_EXTENSION@@PEAXPEAU_HCI_CALLBACK_DATA@@@Z4@Z`
- size: `878`
- prototype: `unsigned __int8 __fastcall(struct _HCI_CONNECTION *, struct _HCI_CLIENT_UPDATE *, struct _GUID *, void (*)(struct DEVICE_EXTENSION *, void *, struct _HCI_CALLBACK_DATA *), void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x14003a64c`
- `0x14004631c`

## callees

- `0x140005608`
- `0x140005690`
- `0x14003667c`
- `0x14004650c`
- `0x140048a2c`
- `0x140165580`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14004674b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14004674b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140046716`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140046716`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004663f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004663f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140046670`
- `ntoskrnl!KeReleaseSpinLock` at `0x140046786`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400467a6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140046670`
- `ntoskrnl!KeReleaseSpinLock` at `0x140046786`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400467a6`

## pseudocode

```c

```
