# RegReplaceKeyW

- ea: `0x1800552d0`
- end: `0x180055459`
- name: `RegReplaceKeyW`
- size: `393`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpNewFile, LPCWSTR lpOldFile)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180053db8`
- `0x1800552d0`
- `0x18006d4fc`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x180055350`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005537d`
- `ntdll!RtlInitUnicodeStringEx` at `0x180055395`
- `ntdll!RtlInitUnicodeStringEx` at `0x180055350`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005537d`
- `ntdll!RtlInitUnicodeStringEx` at `0x180055395`
- `ntdll!RtlNtStatusToDosError` at `0x180055362`
- `ntdll!RtlNtStatusToDosError` at `0x180055362`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x180055332`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x180055332`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x180055434`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x180055434`

## pseudocode

```c

```
