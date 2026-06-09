# HCI_ProcessSniffSubrating(_HCI_CONNECTION *,_HCI_CLIENT_UPDATE *,_GUID *,void (*)(DEVICE_EXTENSION *,void *,_HCI_CALLBACK_DATA *),void *)

- ea: `0x140046c98`
- end: `0x140047427`
- name: `?HCI_ProcessSniffSubrating@@YAEPEAU_HCI_CONNECTION@@PEAU_HCI_CLIENT_UPDATE@@PEAU_GUID@@P6AXPEAUDEVICE_EXTENSION@@PEAXPEAU_HCI_CALLBACK_DATA@@@Z4@Z`
- size: `1935`
- prototype: `unsigned __int8 __fastcall(struct _HCI_CONNECTION *, struct _HCI_CLIENT_UPDATE *, struct _GUID *, void (*)(struct DEVICE_EXTENSION *, void *, struct _HCI_CALLBACK_DATA *), void *)`
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callers

- `0x140038fc0`
- `0x14003a64c`
- `0x14004631c`

## callees

- `0x140005608`
- `0x140005690`
- `0x140005748`
- `0x140005a64`
- `0x14000bdb8`
- `0x14003667c`
- `0x140046c98`
- `0x140048590`
- `0x14004b9b4`
- `0x140165580`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140046fa5`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140046fa5`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140046f71`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140046f71`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140046db3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140046db3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140046df8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400471b6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400473f0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140046df8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400471b6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400473f0`

## pseudocode

```c

```
