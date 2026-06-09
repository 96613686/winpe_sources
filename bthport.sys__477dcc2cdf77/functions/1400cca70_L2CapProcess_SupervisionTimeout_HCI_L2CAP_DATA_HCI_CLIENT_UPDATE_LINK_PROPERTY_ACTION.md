# L2CapProcess_SupervisionTimeout(HCI_L2CAP_DATA *,_HCI_CLIENT_UPDATE *,_LINK_PROPERTY_ACTION)

- ea: `0x1400cca70`
- end: `0x1400ccb33`
- name: `?L2CapProcess_SupervisionTimeout@@YAXPEAUHCI_L2CAP_DATA@@PEAU_HCI_CLIENT_UPDATE@@W4_LINK_PROPERTY_ACTION@@@Z`
- size: `195`
- prototype: `void __high(struct HCI_L2CAP_DATA *, struct _HCI_CLIENT_UPDATE *, enum _LINK_PROPERTY_ACTION)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x140048320`
- `0x1400cc2f0`
- `0x1400cca70`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cca9b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400ccaed`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cca9b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400ccaed`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ccab9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ccb0a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ccab9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ccb0a`

## pseudocode

```c

```
