# RegDeleteKeyW

- ea: `0x180023c20`
- end: `0x180023d1a`
- name: `RegDeleteKeyW`
- size: `250`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180023bb0`

## callees

- `0x180023c20`
- `0x180023d20`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x180023c75`
- `ntdll!RtlInitUnicodeStringEx` at `0x180023c75`
- `ntdll!RtlNtStatusToDosError` at `0x180023ccb`
- `ntdll!RtlNtStatusToDosError` at `0x180023ccb`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x180023c61`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x180023c61`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x180023cac`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x180023cac`
- `RPCRT4!NdrClientCall3` at `0x180023cfb`
- `RPCRT4!NdrClientCall3` at `0x180023cfb`

## pseudocode

```c

```
