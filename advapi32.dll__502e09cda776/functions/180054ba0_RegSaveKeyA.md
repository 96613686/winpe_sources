# RegSaveKeyA

- ea: `0x180054ba0`
- end: `0x180054d49`
- name: `RegSaveKeyA`
- size: `425`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCSTR lpFile, const LPSECURITY_ATTRIBUTES lpSecurityAttributes)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180053e38`
- `0x180054ba0`
- `0x18006d834`
- `0x18006e258`

## import_xrefs

- `ntdll!RtlInitAnsiStringEx` at `0x180054c23`
- `ntdll!RtlInitAnsiStringEx` at `0x180054c23`
- `ntdll!RtlFreeHeap` at `0x180054cff`
- `ntdll!RtlFreeHeap` at `0x180054cff`
- `ntdll!RtlFreeUnicodeString` at `0x180054d10`
- `ntdll!RtlFreeUnicodeString` at `0x180054d10`
- `ntdll!RtlNtStatusToDosError` at `0x180054c35`
- `ntdll!RtlNtStatusToDosError` at `0x180054c35`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180054c55`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180054c55`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x180054c05`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x180054c05`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x180054d26`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x180054d26`

## pseudocode

```c

```
