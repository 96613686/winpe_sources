# RegSaveKeyW

- ea: `0x1800362a0`
- end: `0x1800363ee`
- name: `RegSaveKeyW`
- size: `334`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCWSTR lpFile, const LPSECURITY_ATTRIBUTES lpSecurityAttributes)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800362a0`
- `0x18004dc60`
- `0x180060dc0`
- `0x180061728`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x180036312`
- `ntdll!RtlInitUnicodeStringEx` at `0x180036312`
- `ntdll!RtlFreeHeap` at `0x1800363c5`
- `ntdll!RtlFreeHeap` at `0x1800363c5`
- `ntdll!RtlNtStatusToDosError` at `0x18003631e`
- `ntdll!RtlNtStatusToDosError` at `0x18003631e`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x1800362fa`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x1800362fa`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x1800363d5`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x1800363d5`

## pseudocode

```c

```
