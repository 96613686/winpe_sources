# L2CapInt_UpdateChannelCallback(_HCI_CLIENT_UPDATE *)

- ea: `0x1400cc2f0`
- end: `0x1400cc55b`
- name: `?L2CapInt_UpdateChannelCallback@@YAXPEAU_HCI_CLIENT_UPDATE@@@Z`
- size: `619`
- prototype: `void __fastcall(struct _HCI_CLIENT_UPDATE *)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1400cc570`
- `0x1400cc970`
- `0x1400cca70`

## callees

- `0x1400266f4`
- `0x1400b9d78`
- `0x1400cc2f0`
- `0x140161d7c`
- `0x14016235c`
- `0x140165640`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400cc51d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cc51d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cc4ce`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cc4ce`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cc506`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cc506`

## pseudocode

```c

```
