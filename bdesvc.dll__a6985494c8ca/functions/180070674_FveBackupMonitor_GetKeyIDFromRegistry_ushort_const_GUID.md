# FveBackupMonitor::GetKeyIDFromRegistry(ushort const *,_GUID *)

- ea: `0x180070674`
- end: `0x180070952`
- name: `?GetKeyIDFromRegistry@FveBackupMonitor@@SAJPEBGPEAU_GUID@@@Z`
- size: `734`
- prototype: `__int64 __fastcall(LPCWSTR lpValue, struct _GUID *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180043e5c`
- `0x180070958`

## callees

- `0x180009f60`
- `0x18001b7f0`
- `0x18001b890`
- `0x180034070`
- `0x180034d28`
- `0x180070674`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800708a2`
- `ntdll!RtlInitUnicodeString` at `0x1800708a2`
- `ntdll!RtlGUIDFromString` at `0x1800708b8`
- `ntdll!RtlGUIDFromString` at `0x1800708b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007091d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007091d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800707d2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800707d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800707be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180070909`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800707be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180070909`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180070769`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007084d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180070769`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007084d`

## pseudocode

```c

```
