# CmsBlockCache::GetTotalNumberOfMappedPages(__int64 *,__int64 *)

- ea: `0x140135fb0`
- end: `0x1401360b8`
- name: `?GetTotalNumberOfMappedPages@CmsBlockCache@@QEAAXPEA_J0@Z`
- size: `264`
- prototype: `void __fastcall(CmsBlockCache *__hidden this, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140128f58`

## callees

- `0x140135fb0`
- `0x1401b9010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x140136010`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14013606f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140136010`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14013606f`
- `ntdll!RtlReleaseSRWLockShared` at `0x14013602b`
- `ntdll!RtlReleaseSRWLockShared` at `0x14013608c`
- `ntdll!RtlReleaseSRWLockShared` at `0x14013602b`
- `ntdll!RtlReleaseSRWLockShared` at `0x14013608c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140136039`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14013609a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140136039`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14013609a`

## pseudocode

```c

```
