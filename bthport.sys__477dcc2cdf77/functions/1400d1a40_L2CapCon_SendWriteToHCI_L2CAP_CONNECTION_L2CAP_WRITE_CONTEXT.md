# L2CapCon_SendWriteToHCI(L2CAP_CONNECTION *,_L2CAP_WRITE_CONTEXT *)

- ea: `0x1400d1a40`
- end: `0x1400d1f0c`
- name: `?L2CapCon_SendWriteToHCI@@YAXPEAUL2CAP_CONNECTION@@PEAU_L2CAP_WRITE_CONTEXT@@@Z`
- size: `1228`
- prototype: `void __fastcall(struct L2CAP_CONNECTION *, struct _L2CAP_WRITE_CONTEXT *)`
- caller_count: `8`
- callee_count: `6`
- tags: ``

## callers

- `0x1400d4d70`
- `0x1400d5da4`
- `0x1400d6150`
- `0x1400d6670`
- `0x1400d6d10`
- `0x1400d6f9c`
- `0x1400d7328`
- `0x1400e5178`

## callees

- `0x140005690`
- `0x140005b4c`
- `0x14000764c`
- `0x140031b50`
- `0x1400d1a40`
- `0x1400d8380`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d1aca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d1d3a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d1aca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d1d3a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d1cdb`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d1dca`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d1ef4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d1cdb`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d1dca`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d1ef4`

## pseudocode

```c

```
