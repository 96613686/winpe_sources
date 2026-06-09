# HCI_RegisterConnectionUpdate(HCI_L2CAP_DATA *,_HCI_CLIENT_UPDATE *,uchar)

- ea: `0x140047994`
- end: `0x140047bc7`
- name: `?HCI_RegisterConnectionUpdate@@YAXPEAUHCI_L2CAP_DATA@@PEAU_HCI_CLIENT_UPDATE@@E@Z`
- size: `563`
- prototype: `void __fastcall(struct HCI_L2CAP_DATA *, struct _HCI_CLIENT_UPDATE *, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1400cbb00`

## callees

- `0x140005608`
- `0x140047994`
- `0x1400a536c`
- `0x140165580`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140047a45`
- `ntoskrnl!ExAllocatePool2` at `0x140047a45`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400479cd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400479cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140047a22`
- `ntoskrnl!KeReleaseSpinLock` at `0x140047a22`

## pseudocode

```c

```
