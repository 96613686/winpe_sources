# COWSMemmgr::ReleaseLocalHeap(COWSHeap * &)

- ea: `0x1800851e0`
- end: `0x1800852e5`
- name: `?ReleaseLocalHeap@COWSMemmgr@@QEAAXAEAPEAVCOWSHeap@@@Z`
- size: `261`
- prototype: `void __fastcall(COWSMemmgr *__hidden this, struct COWSHeap **)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800859c0`
- `0x180085bc0`
- `0x1800db020`

## callees

- `0x1800838f0`
- `0x1800851e0`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x18008523d`
- `KERNEL32!InterlockedPopEntrySList` at `0x18008523d`
- `KERNEL32!InterlockedPushEntrySList` at `0x180085276`
- `KERNEL32!InterlockedPushEntrySList` at `0x180085276`
- `KERNEL32!GetCurrentProcessorNumber` at `0x180085227`
- `KERNEL32!GetCurrentProcessorNumber` at `0x180085227`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800852b8`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800852b8`
- `api-ms-win-crt-heap-l1-1-0!_aligned_malloc` at `0x18008524e`
- `api-ms-win-crt-heap-l1-1-0!_aligned_malloc` at `0x18008524e`

## pseudocode

```c

```
