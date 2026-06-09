# COWSMemmgr::AcquireLocalHeap(COWSHeap * &)

- ea: `0x1800850e0`
- end: `0x1800851de`
- name: `?AcquireLocalHeap@COWSMemmgr@@QEAAHAEAPEAVCOWSHeap@@@Z`
- size: `254`
- prototype: `__int64 __fastcall(COWSMemmgr *__hidden this, struct COWSHeap **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800859c0`
- `0x1800daf70`

## callees

- `0x180085000`
- `0x1800850e0`
- `0x18008536c`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x18008511f`
- `KERNEL32!InterlockedPopEntrySList` at `0x18008511f`
- `KERNEL32!InterlockedPushEntrySList` at `0x180085179`
- `KERNEL32!InterlockedPushEntrySList` at `0x180085179`
- `KERNEL32!GetCurrentProcessorNumber` at `0x1800850ff`
- `KERNEL32!GetCurrentProcessorNumber` at `0x1800850ff`
- `api-ms-win-crt-heap-l1-1-0!_aligned_free` at `0x18008516d`
- `api-ms-win-crt-heap-l1-1-0!_aligned_free` at `0x18008516d`

## pseudocode

```c

```
