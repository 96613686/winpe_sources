# HCI_DibUnpairComplete(HCI_INTERFACE *,DEVICE_INFO_BLOCK *,uchar)

- ea: `0x14005d8b0`
- end: `0x14005de5c`
- name: `?HCI_DibUnpairComplete@@YAXPEAUHCI_INTERFACE@@PEAUDEVICE_INFO_BLOCK@@E@Z`
- size: `1452`
- prototype: `void __fastcall(struct HCI_INTERFACE *, struct DEVICE_INFO_BLOCK *, unsigned __int8)`
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x14005d3a0`
- `0x14005de64`
- `0x1400a5610`

## callees

- `0x140005690`
- `0x140005b4c`
- `0x140005ce8`
- `0x14001fddc`
- `0x14003b1cc`
- `0x140040834`
- `0x140041474`
- `0x140041f28`
- `0x14005d8b0`
- `0x1400638f4`
- `0x1400b9d78`
- `0x140161d7c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005d94a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005da79`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005dc2b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005d94a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005da79`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005dc2b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005d9a1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005db5b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005dd0d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005d9a1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005db5b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005dd0d`

## pseudocode

```c

```
