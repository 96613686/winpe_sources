# RegSaveKeyA

- ea: `0x18004e7d0`
- end: `0x18004e94e`
- name: `RegSaveKeyA`
- size: `382`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCSTR lpFile, const LPSECURITY_ATTRIBUTES lpSecurityAttributes)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18004dc60`
- `0x18004e7d0`
- `0x180060dc0`
- `0x180061728`

## import_xrefs

- `ntdll!RtlInitAnsiStringEx` at `0x18004e84d`
- `ntdll!RtlInitAnsiStringEx` at `0x18004e84d`
- `ntdll!RtlFreeHeap` at `0x18004e917`
- `ntdll!RtlFreeHeap` at `0x18004e917`
- `ntdll!RtlFreeUnicodeString` at `0x18004e922`
- `ntdll!RtlFreeUnicodeString` at `0x18004e922`
- `ntdll!RtlNtStatusToDosError` at `0x18004e859`
- `ntdll!RtlNtStatusToDosError` at `0x18004e859`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004e873`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004e873`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x18004e835`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x18004e835`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x18004e932`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x18004e932`

## pseudocode

```c

```
