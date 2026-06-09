# RegSaveKeyW

- ea: `0x18003a1c0`
- end: `0x18003a32d`
- name: `RegSaveKeyW`
- size: `365`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCWSTR lpFile, const LPSECURITY_ATTRIBUTES lpSecurityAttributes)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18003a1c0`
- `0x180053e38`
- `0x18006d834`
- `0x18006e258`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x18003a238`
- `ntdll!RtlInitUnicodeStringEx` at `0x18003a238`
- `ntdll!RtlFreeHeap` at `0x18003a2f7`
- `ntdll!RtlFreeHeap` at `0x18003a2f7`
- `ntdll!RtlNtStatusToDosError` at `0x18003a24a`
- `ntdll!RtlNtStatusToDosError` at `0x18003a24a`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x18003a21a`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x18003a21a`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x18003a30d`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x18003a30d`

## pseudocode

```c

```
