# GetEventProperty(void *,ushort const * *,ulong,ulong,_EVT_VARIANT * *,ulong *)

- ea: `0x1800d6c44`
- end: `0x1800d6df9`
- name: `?GetEventProperty@@YAKPEAXPEAPEBGKKPEAPEAU_EVT_VARIANT@@PEAK@Z`
- size: `437`
- prototype: `unsigned int __usercall@<eax>(EVT_HANDLE Fragment@<rcx>, const unsigned __int16 **@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, struct _EVT_VARIANT **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800d68b0`

## callees

- `0x180012920`
- `0x180019c84`
- `0x1800d6c44`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800d6d0c`
- `ntdll!RtlAllocateHeap` at `0x1800d6d0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6c7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6ce3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6d66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6c7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6ce3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6d66`
- `wevtapi!EvtRender` at `0x1800d6cd5`
- `wevtapi!EvtRender` at `0x1800d6d5c`
- `wevtapi!EvtRender` at `0x1800d6cd5`
- `wevtapi!EvtRender` at `0x1800d6d5c`
- `wevtapi!EvtCreateRenderContext` at `0x1800d6c6e`
- `wevtapi!EvtCreateRenderContext` at `0x1800d6c6e`
- `wevtapi!EvtClose` at `0x1800d6de8`
- `wevtapi!EvtClose` at `0x1800d6de8`

## pseudocode

```c

```
