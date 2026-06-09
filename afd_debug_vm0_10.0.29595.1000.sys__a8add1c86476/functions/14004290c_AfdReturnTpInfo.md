# AfdReturnTpInfo

- ea: `0x14004290c`
- end: `0x140042a8b`
- name: `AfdReturnTpInfo`
- size: `383`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14003fc5c`
- `0x140042270`
- `0x140057100`
- `0x140057a30`

## callees

- `0x14004290c`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140042957`
- `ntoskrnl!IoFreeIrp` at `0x14004298b`
- `ntoskrnl!IoFreeIrp` at `0x140042957`
- `ntoskrnl!IoFreeIrp` at `0x14004298b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140042a5d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140042a5d`
- `ntoskrnl!IoFreeMdl` at `0x1400429f9`
- `ntoskrnl!IoFreeMdl` at `0x1400429f9`
- `ntoskrnl!MmUnlockPages` at `0x1400429e8`
- `ntoskrnl!MmUnlockPages` at `0x1400429e8`
- `ntoskrnl!ObfDereferenceObject` at `0x1400429c6`
- `ntoskrnl!ObfDereferenceObject` at `0x1400429c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042944`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042a24`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042a73`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042944`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042a24`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042a73`

## pseudocode

```c

```
