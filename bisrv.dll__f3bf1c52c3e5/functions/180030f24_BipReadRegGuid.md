# BipReadRegGuid

- ea: `0x180030f24`
- end: `0x1800310dd`
- name: `BipReadRegGuid`
- size: `441`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PUNICODE_STRING ValueName, GUID *Guid)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18004786c`
- `0x1800486fc`
- `0x18004fea4`
- `0x180087cc4`

## callees

- `0x180026080`
- `0x180030f24`
- `0x1800310e4`
- `0x180049844`
- `0x18004df58`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x180030f84`
- `ntdll!NtQueryValueKey` at `0x180030fe9`
- `ntdll!NtQueryValueKey` at `0x180030f84`
- `ntdll!NtQueryValueKey` at `0x180030fe9`
- `ntdll!RtlGUIDFromString` at `0x180031026`
- `ntdll!RtlGUIDFromString` at `0x180031026`
- `ntdll!RtlFreeHeap` at `0x18003103a`
- `ntdll!RtlFreeHeap` at `0x18003103a`
- `ntdll!RtlAllocateHeap` at `0x180030fb6`
- `ntdll!RtlAllocateHeap` at `0x180030fb6`

## pseudocode

```c

```
