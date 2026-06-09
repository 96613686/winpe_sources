# BipReadRegUlong

- ea: `0x1800260e8`
- end: `0x18002622d`
- name: `BipReadRegUlong`
- size: `325`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PUNICODE_STRING ValueName)`
- caller_count: `8`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800251f8`
- `0x18004786c`
- `0x1800486fc`
- `0x18004fea4`
- `0x180050420`
- `0x1800639b0`
- `0x180087600`
- `0x180087cc4`

## callees

- `0x180026080`
- `0x1800260e8`
- `0x180049844`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x18002613d`
- `ntdll!NtQueryValueKey` at `0x1800261b9`
- `ntdll!NtQueryValueKey` at `0x18002613d`
- `ntdll!NtQueryValueKey` at `0x1800261b9`
- `ntdll!RtlFreeHeap` at `0x1800261dd`
- `ntdll!RtlFreeHeap` at `0x1800261dd`
- `ntdll!RtlAllocateHeap` at `0x18002618a`
- `ntdll!RtlAllocateHeap` at `0x18002618a`

## pseudocode

```c

```
