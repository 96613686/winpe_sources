# RegQueryValueA

- ea: `0x180028c50`
- end: `0x180028ede`
- name: `RegQueryValueA`
- size: `654`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCSTR lpSubKey, LPSTR lpData, PLONG lpcbData)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180028c50`
- `0x180029180`
- `0x18003bcf0`
- `0x180072042`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180028ec6`
- `ntdll!RtlFreeHeap` at `0x180028ec6`
- `ntdll!RtlAllocateHeap` at `0x180028e68`
- `ntdll!RtlAllocateHeap` at `0x180028e68`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x180028cb1`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x180028cb1`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x180028d68`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x180028d68`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180028d0c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180028d0c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180028dab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180028dab`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x180028e9b`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x180028e9b`

## pseudocode

```c

```
