# AslTelemetryCreate

- ea: `0x180050550`
- end: `0x1800506c9`
- name: `AslTelemetryCreate`
- size: `377`
- prototype: `__int64 __fastcall(_QWORD *, const char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180027d08`

## callees

- `0x1800197d4`
- `0x180029f70`
- `0x180031910`
- `0x180050550`
- `0x180050754`
- `0x180050b04`
- `0x18005a868`

## import_xrefs

- `ntdll!RtlInitializeCriticalSection` at `0x1800505d5`
- `ntdll!RtlInitializeCriticalSection` at `0x1800505d5`
- `ntdll!RtlAllocateHeap` at `0x18005059d`
- `ntdll!RtlAllocateHeap` at `0x18005059d`
- `KERNEL32!GetProcessHeap` at `0x180050664`
- `KERNEL32!GetProcessHeap` at `0x180050664`
- `KERNEL32!HeapFree` at `0x180050646`
- `KERNEL32!HeapFree` at `0x180050646`

## string_xrefs

- `0x1800505b8`: `AslTelemetryCreate`

## pseudocode

```c

```
