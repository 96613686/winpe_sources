# RegQueryValueA

- ea: `0x180026080`
- end: `0x1800262d7`
- name: `RegQueryValueA`
- size: `599`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCSTR lpSubKey, LPSTR lpData, PLONG lpcbData)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180026080`
- `0x18002653c`
- `0x180037ba0`
- `0x180065042`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800262c5`
- `ntdll!RtlFreeHeap` at `0x1800262c5`
- `ntdll!RtlAllocateHeap` at `0x180026273`
- `ntdll!RtlAllocateHeap` at `0x180026273`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x1800260e1`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x1800260e1`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x180026188`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x180026188`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180026136`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180026136`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800261c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800261c4`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x1800262a0`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x1800262a0`

## pseudocode

```c

```
