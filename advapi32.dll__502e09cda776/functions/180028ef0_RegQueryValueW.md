# RegQueryValueW

- ea: `0x180028ef0`
- end: `0x180029177`
- name: `RegQueryValueW`
- size: `647`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCWSTR lpSubKey, LPWSTR lpData, PLONG lpcbData)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180028ef0`
- `0x180029180`
- `0x18003bcf0`
- `0x180072042`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180029112`
- `ntdll!RtlFreeHeap` at `0x180029112`
- `ntdll!RtlAllocateHeap` at `0x1800290b4`
- `ntdll!RtlAllocateHeap` at `0x1800290b4`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x180028f41`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x180028f41`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x180028fdc`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x180028fdc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028f93`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028f93`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029049`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029049`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800290e2`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800290e2`

## pseudocode

```c

```
