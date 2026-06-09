# BipReadRegMultiSz

- ea: `0x180030a80`
- end: `0x180030c4b`
- name: `BipReadRegMultiSz`
- size: `459`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PUNICODE_STRING ValueName, PUNICODE_STRING DestinationString)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800486fc`
- `0x180080e38`
- `0x180087cc4`

## callees

- `0x180026080`
- `0x180030a80`
- `0x1800310e4`
- `0x180049844`
- `0x18004df58`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x180030af5`
- `ntdll!NtQueryValueKey` at `0x180030b4f`
- `ntdll!NtQueryValueKey` at `0x180030af5`
- `ntdll!NtQueryValueKey` at `0x180030b4f`
- `ntdll!RtlDuplicateUnicodeString` at `0x180030bed`
- `ntdll!RtlDuplicateUnicodeString` at `0x180030bed`
- `ntdll!RtlFreeHeap` at `0x180030c30`
- `ntdll!RtlFreeHeap` at `0x180030c30`
- `ntdll!RtlAllocateHeap` at `0x180030b16`
- `ntdll!RtlAllocateHeap` at `0x180030b16`

## pseudocode

```c

```
