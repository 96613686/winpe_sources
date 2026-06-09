# _GetMUIStringFromCache

- ea: `0x1800d9360`
- end: `0x1800d963b`
- name: `_GetMUIStringFromCache`
- size: `731`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, PCWSTR SourceString@<rdx>, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800c3400`

## callees

- `0x1800d9360`
- `0x18012d119`
- `0x180188eb9`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800d9449`
- `ntdll!RtlInitUnicodeString` at `0x1800d9449`
- `ntdll!RtlNtStatusToDosError` at `0x1800d9552`
- `ntdll!RtlNtStatusToDosError` at `0x1800d9552`
- `ntdll!NtQueryValueKey` at `0x1800d947d`
- `ntdll!NtQueryValueKey` at `0x1800d95f5`
- `ntdll!NtQueryValueKey` at `0x1800d947d`
- `ntdll!NtQueryValueKey` at `0x1800d95f5`
- `ntdll!RtlFreeHeap` at `0x1800d952e`
- `ntdll!RtlFreeHeap` at `0x1800d954a`
- `ntdll!RtlFreeHeap` at `0x1800d962d`
- `ntdll!RtlFreeHeap` at `0x1800d952e`
- `ntdll!RtlFreeHeap` at `0x1800d954a`
- `ntdll!RtlFreeHeap` at `0x1800d962d`
- `ntdll!RtlAllocateHeap` at `0x1800d941c`
- `ntdll!RtlAllocateHeap` at `0x1800d95b0`
- `ntdll!RtlAllocateHeap` at `0x1800d941c`
- `ntdll!RtlAllocateHeap` at `0x1800d95b0`

## pseudocode

```c

```
