# FltFreeFileLock

- ea: `0x1800778f0`
- end: `0x18007793c`
- name: `FltFreeFileLock`
- size: `76`
- prototype: `void __stdcall(PFILE_LOCK FileLock)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1800778f0`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18007791b`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18007791b`
- `ntoskrnl!FsRtlUninitializeFileLock` at `0x180077905`
- `ntoskrnl!FsRtlUninitializeFileLock` at `0x180077905`
- `ntoskrnl!FsRtlFreeFileLock` at `0x18007792e`
- `ntoskrnl!FsRtlFreeFileLock` at `0x18007792e`

## pseudocode

```c

```
