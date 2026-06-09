# BthFindChildPdoFromPsmWithCallback(DEVICE_EXTENSION *,unsigned __int64 *,ushort,void *,void (*)(void *,L2CAP_SERVER_INFO *))

- ea: `0x140028260`
- end: `0x140028492`
- name: `?BthFindChildPdoFromPsmWithCallback@@YAJPEAUDEVICE_EXTENSION@@PEA_KGPEAXP6AX2PEAUL2CAP_SERVER_INFO@@@Z@Z`
- size: `562`
- prototype: `__int64 __fastcall(struct DEVICE_EXTENSION *, unsigned __int64 *, unsigned __int16, void *, void (*)(void *, struct L2CAP_SERVER_INFO *))`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1400c7820`

## callees

- `0x140005608`
- `0x140005690`
- `0x140005b4c`
- `0x140027fe4`
- `0x140028260`
- `0x1400c6120`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140028388`
- `ntoskrnl!ExAllocatePool2` at `0x140028388`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140028356`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140028356`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400283b3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400283b3`

## pseudocode

```c

```
