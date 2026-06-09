# GetTempPathW

- ea: `0x1800e8140`
- end: `0x1800e8369`
- name: `GetTempPathW`
- size: `553`
- prototype: `DWORD __stdcall(DWORD nBufferLength, LPWSTR lpBuffer)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180182440`

## callees

- `0x1800134a0`
- `0x180022450`
- `0x1800e8140`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800e8334`
- `ntdll!RtlFreeHeap` at `0x1800e8353`
- `ntdll!RtlFreeHeap` at `0x18018c1b4`
- `ntdll!RtlFreeHeap` at `0x1800e8334`
- `ntdll!RtlFreeHeap` at `0x1800e8353`
- `ntdll!RtlFreeHeap` at `0x18018c1b4`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x1800e81b1`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x1800e82c8`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x1800e82f6`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x1800e81b1`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x1800e82c8`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x1800e82f6`
- `ntdll!RtlGetFullPathName_U` at `0x1800e81fc`
- `ntdll!RtlGetFullPathName_U` at `0x1800e81fc`
- `ntdll!RtlAllocateHeap` at `0x1800e818f`
- `ntdll!RtlAllocateHeap` at `0x1800e818f`

## pseudocode

```c

```
