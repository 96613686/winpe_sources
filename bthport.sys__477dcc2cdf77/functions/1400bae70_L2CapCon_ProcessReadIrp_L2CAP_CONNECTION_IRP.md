# L2CapCon_ProcessReadIrp(L2CAP_CONNECTION *,_IRP *)

- ea: `0x1400bae70`
- end: `0x1400bb30c`
- name: `?L2CapCon_ProcessReadIrp@@YAJPEAUL2CAP_CONNECTION@@PEAU_IRP@@@Z`
- size: `1180`
- prototype: `__int64 __fastcall(struct L2CAP_CONNECTION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1400bc410`

## callees

- `0x140005b4c`
- `0x14000764c`
- `0x1400ba420`
- `0x1400bae70`
- `0x1400bd984`
- `0x1400cf210`
- `0x140161a44`
- `0x140161c78`
- `0x140161d7c`
- `0x140162670`
- `0x140165580`

## import_xrefs

- `ntoskrnl!KeSetTimer` at `0x1400bb211`
- `ntoskrnl!KeSetTimer` at `0x1400bb211`
- `ntoskrnl!KeInitializeDpc` at `0x1400baf89`
- `ntoskrnl!KeInitializeDpc` at `0x1400baf89`
- `ntoskrnl!KeInitializeTimerEx` at `0x1400baf6f`
- `ntoskrnl!KeInitializeTimerEx` at `0x1400baf6f`
- `ntoskrnl!ExAllocatePool2` at `0x1400baed0`
- `ntoskrnl!ExAllocatePool2` at `0x1400baed0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bafd4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bb07c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bafd4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bb07c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bb05c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bb22c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bb05c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bb22c`

## pseudocode

```c

```
