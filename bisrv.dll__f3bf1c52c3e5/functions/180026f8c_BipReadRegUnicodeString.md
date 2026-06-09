# BipReadRegUnicodeString

- ea: `0x180026f8c`
- end: `0x18002718f`
- name: `BipReadRegUnicodeString`
- size: `515`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PUNICODE_STRING ValueName, PUNICODE_STRING DestinationString)`
- caller_count: `5`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18004786c`
- `0x1800486fc`
- `0x18004e4f0`
- `0x18004fea4`
- `0x180087cc4`

## callees

- `0x18000da30`
- `0x180026080`
- `0x180026f8c`
- `0x1800271a0`
- `0x180049844`
- `0x18004df58`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x180026fe8`
- `ntdll!NtQueryValueKey` at `0x18002703a`
- `ntdll!NtQueryValueKey` at `0x180026fe8`
- `ntdll!NtQueryValueKey` at `0x18002703a`
- `ntdll!RtlDuplicateUnicodeString` at `0x180027082`
- `ntdll!RtlDuplicateUnicodeString` at `0x180027082`
- `ntdll!RtlInitUnicodeString` at `0x18002706f`
- `ntdll!RtlInitUnicodeString` at `0x18002706f`

## pseudocode

```c

```
