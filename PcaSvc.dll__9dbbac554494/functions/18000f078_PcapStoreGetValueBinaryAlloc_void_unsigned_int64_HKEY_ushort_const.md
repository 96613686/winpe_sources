# PcapStoreGetValueBinaryAlloc(void * *,unsigned __int64 *,HKEY__ *,ushort const *)

- ea: `0x18000f078`
- end: `0x18000f22b`
- name: `?PcapStoreGetValueBinaryAlloc@@YAKPEAPEAXPEA_KPEAUHKEY__@@PEBG@Z`
- size: `435`
- prototype: `unsigned int(void **, unsigned __int64 *, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000f2f4`

## callees

- `0x18000f078`
- `0x180012920`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000f179`
- `ntdll!RtlFreeHeap` at `0x18000f196`
- `ntdll!RtlFreeHeap` at `0x18000f179`
- `ntdll!RtlFreeHeap` at `0x18000f196`
- `ntdll!RtlAllocateHeap` at `0x18000f0b6`
- `ntdll!RtlAllocateHeap` at `0x18000f1b3`
- `ntdll!RtlAllocateHeap` at `0x18000f0b6`
- `ntdll!RtlAllocateHeap` at `0x18000f1b3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f111`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f1e9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f111`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f1e9`

## string_xrefs

- `0x18000f203`: `Failed to read store value %S [%d]`

## pseudocode

```c

```
