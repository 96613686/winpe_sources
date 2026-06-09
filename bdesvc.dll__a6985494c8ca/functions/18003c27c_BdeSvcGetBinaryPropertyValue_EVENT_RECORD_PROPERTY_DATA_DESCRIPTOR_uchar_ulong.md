# BdeSvcGetBinaryPropertyValue(_EVENT_RECORD *,_PROPERTY_DATA_DESCRIPTOR *,uchar * *,ulong *)

- ea: `0x18003c27c`
- end: `0x18003c3eb`
- name: `?BdeSvcGetBinaryPropertyValue@@YAKPEAU_EVENT_RECORD@@PEAU_PROPERTY_DATA_DESCRIPTOR@@PEAPEAEPEAK@Z`
- size: `367`
- prototype: `__int64 __fastcall(PEVENT_RECORD pEvent, PPROPERTY_DATA_DESCRIPTOR pPropertyData, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003d8bc`

## callees

- `0x180009f30`
- `0x180034070`
- `0x18003c27c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c399`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c399`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003c32e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003c32e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c31a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c385`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c31a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c385`
- `tdh!TdhGetPropertySize` at `0x18003c300`
- `tdh!TdhGetPropertySize` at `0x18003c300`
- `tdh!TdhGetProperty` at `0x18003c367`
- `tdh!TdhGetProperty` at `0x18003c367`

## pseudocode

```c

```
