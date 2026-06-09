# BasepRegGetValue

- ea: `0x18013d4a0`
- end: `0x18013d717`
- name: `BasepRegGetValue`
- size: `631`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18013d1d0`
- `0x18013d300`

## callees

- `0x18013d4a0`
- `0x180188eb9`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18013d50e`
- `ntdll!RtlInitUnicodeString` at `0x18013d56f`
- `ntdll!RtlInitUnicodeString` at `0x18013d50e`
- `ntdll!RtlInitUnicodeString` at `0x18013d56f`
- `ntdll!NtOpenKey` at `0x18013d54a`
- `ntdll!NtOpenKey` at `0x18013d54a`
- `ntdll!RtlNtStatusToDosError` at `0x18013d556`
- `ntdll!RtlNtStatusToDosError` at `0x18013d556`
- `ntdll!NtQueryValueKey` at `0x18013d59b`
- `ntdll!NtQueryValueKey` at `0x18013d5f4`
- `ntdll!NtQueryValueKey` at `0x18013d59b`
- `ntdll!NtQueryValueKey` at `0x18013d5f4`
- `ntdll!NtClose` at `0x18013d6c5`
- `ntdll!NtClose` at `0x18013d6c5`
- `ntdll!RtlFreeHeap` at `0x18013d6e7`
- `ntdll!RtlFreeHeap` at `0x18013d6e7`
- `ntdll!RtlAllocateHeap` at `0x18013d5be`
- `ntdll!RtlAllocateHeap` at `0x18013d5be`

## pseudocode

```c

```
