# RegDeleteKeyW

- ea: `0x180026430`
- end: `0x180026557`
- name: `RegDeleteKeyW`
- size: `295`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800263b0`

## callees

- `0x180026430`
- `0x180026560`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x180026493`
- `ntdll!RtlInitUnicodeStringEx` at `0x180026493`
- `ntdll!RtlNtStatusToDosError` at `0x1800264f6`
- `ntdll!RtlNtStatusToDosError` at `0x1800264f6`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x180026479`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x180026479`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x1800264d0`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x1800264d0`
- `RPCRT4!NdrClientCall3` at `0x18002652c`
- `RPCRT4!NdrClientCall3` at `0x18002652c`

## pseudocode

```c

```
