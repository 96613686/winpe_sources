# BipReadRegUlong64

- ea: `0x1800254e4`
- end: `0x18002562a`
- name: `BipReadRegUlong64`
- size: `326`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PUNICODE_STRING ValueName)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800251f8`
- `0x18004fea4`
- `0x1800639b0`

## callees

- `0x1800254e4`
- `0x180026080`
- `0x180049844`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x180025539`
- `ntdll!NtQueryValueKey` at `0x1800255b5`
- `ntdll!NtQueryValueKey` at `0x180025539`
- `ntdll!NtQueryValueKey` at `0x1800255b5`
- `ntdll!RtlFreeHeap` at `0x1800255da`
- `ntdll!RtlFreeHeap` at `0x1800255da`
- `ntdll!RtlAllocateHeap` at `0x180025586`
- `ntdll!RtlAllocateHeap` at `0x180025586`

## pseudocode

```c

```
