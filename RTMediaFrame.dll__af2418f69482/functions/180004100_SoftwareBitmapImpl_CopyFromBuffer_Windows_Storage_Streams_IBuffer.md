# SoftwareBitmapImpl::CopyFromBuffer(Windows::Storage::Streams::IBuffer *)

- ea: `0x180004100`
- end: `0x180004156`
- name: `?CopyFromBuffer@SoftwareBitmapImpl@@UEAAJPEAUIBuffer@Streams@Storage@Windows@@@Z`
- size: `86`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, struct Windows::Storage::Streams::IBuffer *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180007dac`
- `0x18001f414`

## callees

- `0x180004100`
- `0x1800041c4`
- `0x18001f3cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004119`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004119`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004143`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004143`

## pseudocode

```c

```
