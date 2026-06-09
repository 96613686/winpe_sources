# RegQueryValueW

- ea: `0x1800262e0`
- end: `0x180026535`
- name: `RegQueryValueW`
- size: `597`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCWSTR lpSubKey, LPWSTR lpData, PLONG lpcbData)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1800262e0`
- `0x18002653c`
- `0x180037ba0`
- `0x180065042`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800264d6`
- `ntdll!RtlFreeHeap` at `0x1800264d6`
- `ntdll!RtlAllocateHeap` at `0x180026484`
- `ntdll!RtlAllocateHeap` at `0x180026484`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x180026331`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x180026331`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x1800263c0`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x1800263c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002637d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002637d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026422`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026422`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800264ac`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800264ac`

## pseudocode

```c

```
