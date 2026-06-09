# FltFreeFileLock

- ea: `0x180077840`
- end: `0x18007788c`
- name: `FltFreeFileLock`
- size: `76`
- prototype: `void __stdcall(PFILE_LOCK FileLock)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180077840`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18007786b`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18007786b`
- `ntoskrnl!FsRtlUninitializeFileLock` at `0x180077855`
- `ntoskrnl!FsRtlUninitializeFileLock` at `0x180077855`
- `ntoskrnl!FsRtlFreeFileLock` at `0x18007787e`
- `ntoskrnl!FsRtlFreeFileLock` at `0x18007787e`

## pseudocode

```c

```
