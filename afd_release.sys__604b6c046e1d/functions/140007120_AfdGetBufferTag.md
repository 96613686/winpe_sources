# AfdGetBufferTag

- ea: `0x140007120`
- end: `0x140007346`
- name: `AfdGetBufferTag`
- size: `550`
- prototype: `signed __int16 *__fastcall(unsigned int, struct _KPROCESS *, char)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140007350`
- `0x140019364`
- `0x1400277f0`
- `0x1400406bc`

## callees

- `0x140007120`
- `0x140010948`
- `0x140013030`
- `0x1400159e0`

## import_xrefs

- `ntoskrnl!PsChargeProcessPoolQuota` at `0x1400071ce`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x1400072a2`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x1400071ce`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x1400072a2`
- `ntoskrnl!ExAllocatePool3` at `0x14000727e`
- `ntoskrnl!ExAllocatePool3` at `0x14000727e`
- `ntoskrnl!ExRaiseStatus` at `0x140007329`
- `ntoskrnl!ExRaiseStatus` at `0x140007329`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140007179`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140007179`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007206`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007206`

## pseudocode

```c

```
