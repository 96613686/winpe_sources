# L2CapProcess_SniffSubrating(HCI_L2CAP_DATA *,_HCI_CLIENT_UPDATE *,_LINK_PROPERTY_ACTION)

- ea: `0x1400cc970`
- end: `0x1400cca61`
- name: `?L2CapProcess_SniffSubrating@@YAXPEAUHCI_L2CAP_DATA@@PEAU_HCI_CLIENT_UPDATE@@W4_LINK_PROPERTY_ACTION@@@Z`
- size: `241`
- prototype: `void __high(struct HCI_L2CAP_DATA *, struct _HCI_CLIENT_UPDATE *, enum _LINK_PROPERTY_ACTION)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1400cc798`
- `0x1400cc850`

## callees

- `0x140048320`
- `0x1400cc2f0`
- `0x1400cc970`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cc99b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cca02`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cc99b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cca02`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cc9c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cca27`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cc9c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cca27`

## pseudocode

```c

```
