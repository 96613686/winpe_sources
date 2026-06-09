# RegReplaceKeyW

- ea: `0x18004ee50`
- end: `0x18004efb4`
- name: `RegReplaceKeyW`
- size: `356`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpNewFile, LPCWSTR lpOldFile)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18004dbf0`
- `0x18004ee50`
- `0x180060ad4`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x18004eeca`
- `ntdll!RtlInitUnicodeStringEx` at `0x18004eeeb`
- `ntdll!RtlInitUnicodeStringEx` at `0x18004eefd`
- `ntdll!RtlInitUnicodeStringEx` at `0x18004eeca`
- `ntdll!RtlInitUnicodeStringEx` at `0x18004eeeb`
- `ntdll!RtlInitUnicodeStringEx` at `0x18004eefd`
- `ntdll!RtlNtStatusToDosError` at `0x18004eed6`
- `ntdll!RtlNtStatusToDosError` at `0x18004eed6`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x18004eeb2`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x18004eeb2`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x18004ef96`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x18004ef96`

## pseudocode

```c

```
