# L2CapInt_HandleUpdateChannel(L2CAP_INTERFACE *,_IRP *,_BRB *)

- ea: `0x1400cbb00`
- end: `0x1400cbee4`
- name: `?L2CapInt_HandleUpdateChannel@@YAJPEAUL2CAP_INTERFACE@@PEAU_IRP@@PEAU_BRB@@@Z`
- size: `996`
- prototype: `int(struct L2CAP_INTERFACE *, struct _IRP *, struct _BRB *)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x14001d31c`

## callees

- `0x140047994`
- `0x1400bd984`
- `0x1400c8a58`
- `0x1400cbb00`
- `0x1400cc798`
- `0x1400cc850`
- `0x1400e1e50`
- `0x140161a44`
- `0x140161c78`
- `0x140161d7c`
- `0x140162008`
- `0x140162614`
- `0x140162f00`
- `0x140165540`
- `0x140165640`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400cbb95`
- `ntoskrnl!ExAllocatePool2` at `0x1400cbd66`
- `ntoskrnl!ExAllocatePool2` at `0x1400cbb95`
- `ntoskrnl!ExAllocatePool2` at `0x1400cbd66`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400cbc0b`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400cbc0b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cbdb2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cbdb2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cbdff`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cbdff`

## pseudocode

```c

```
