# BipReadRegBinary

- ea: `0x1800263b8`
- end: `0x18002653d`
- name: `BipReadRegBinary`
- size: `389`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PUNICODE_STRING ValueName, void *)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800251f8`
- `0x18004786c`
- `0x1800486fc`
- `0x180087cc4`

## callees

- `0x180026080`
- `0x1800263b8`
- `0x180049844`
- `0x18004df58`
- `0x180094662`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x18002640b`
- `ntdll!NtQueryValueKey` at `0x180026485`
- `ntdll!NtQueryValueKey` at `0x18002640b`
- `ntdll!NtQueryValueKey` at `0x180026485`
- `ntdll!RtlFreeHeap` at `0x1800264bb`
- `ntdll!RtlFreeHeap` at `0x1800264bb`
- `ntdll!RtlAllocateHeap` at `0x180026452`
- `ntdll!RtlAllocateHeap` at `0x180026452`

## pseudocode

```c

```
