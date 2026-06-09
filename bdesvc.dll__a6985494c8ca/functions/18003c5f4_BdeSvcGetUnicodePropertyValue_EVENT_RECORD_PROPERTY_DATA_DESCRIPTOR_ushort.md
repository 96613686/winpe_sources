# BdeSvcGetUnicodePropertyValue(_EVENT_RECORD *,_PROPERTY_DATA_DESCRIPTOR *,ushort * *)

- ea: `0x18003c5f4`
- end: `0x18003c76b`
- name: `?BdeSvcGetUnicodePropertyValue@@YAKPEAU_EVENT_RECORD@@PEAU_PROPERTY_DATA_DESCRIPTOR@@PEAPEAG@Z`
- size: `375`
- prototype: `__int64 __fastcall(PEVENT_RECORD pEvent, PPROPERTY_DATA_DESCRIPTOR pPropertyData, BYTE **)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18003cf1c`
- `0x18003d244`
- `0x18003d3ac`
- `0x18003d718`

## callees

- `0x180009f30`
- `0x180034070`
- `0x18003c5f4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c714`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c714`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003c6a4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003c6a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c690`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c700`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c690`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c700`
- `tdh!TdhGetPropertySize` at `0x18003c676`
- `tdh!TdhGetPropertySize` at `0x18003c676`
- `tdh!TdhGetProperty` at `0x18003c6dd`
- `tdh!TdhGetProperty` at `0x18003c6dd`

## pseudocode

```c

```
