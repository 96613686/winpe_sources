# SepSddlGetAclForString

- ea: `0x1400aade8`
- end: `0x1400ab19c`
- name: `SepSddlGetAclForString`
- size: `948`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400aad04`

## callees

- `0x140078400`
- `0x1400aac10`
- `0x1400aade8`
- `0x1400ab1a4`
- `0x1400ab25c`

## import_xrefs

- `ntoskrnl!wcschr` at `0x1400aae13`
- `ntoskrnl!wcschr` at `0x1400aae13`
- `ntoskrnl!_wcsnicmp` at `0x1400aafac`
- `ntoskrnl!_wcsnicmp` at `0x1400ab025`
- `ntoskrnl!_wcsnicmp` at `0x1400aafac`
- `ntoskrnl!_wcsnicmp` at `0x1400ab025`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ab164`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ab164`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400aaeca`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400aaf0f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400aaeca`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400aaf0f`

## pseudocode

```c

```
