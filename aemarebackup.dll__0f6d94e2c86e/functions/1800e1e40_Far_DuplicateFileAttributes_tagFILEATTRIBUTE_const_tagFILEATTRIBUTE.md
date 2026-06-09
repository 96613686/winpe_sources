# Far::DuplicateFileAttributes(tagFILEATTRIBUTE * const,tagFILEATTRIBUTE * *)

- ea: `0x1800e1e40`
- end: `0x1800e20e6`
- name: `?DuplicateFileAttributes@Far@@SAJQEAUtagFILEATTRIBUTE@@PEAPEAU2@@Z`
- size: `678`
- prototype: `__int64 __fastcall(struct tagFILEATTRIBUTE *const, struct tagFILEATTRIBUTE **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180036cf0`

## callees

- `0x18004c020`
- `0x1800e1e40`
- `0x1800e20ec`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800e1e83`
- `ntdll!RtlAllocateHeap` at `0x1800e1f68`
- `ntdll!RtlAllocateHeap` at `0x1800e1e83`
- `ntdll!RtlAllocateHeap` at `0x1800e1f68`

## string_xrefs

- `0x1800e2038`: `StringCchCopyW failed [%#x]`
- `0x1800e208d`: `StringCbCopyW failed [%#x]`

## pseudocode

```c

```
