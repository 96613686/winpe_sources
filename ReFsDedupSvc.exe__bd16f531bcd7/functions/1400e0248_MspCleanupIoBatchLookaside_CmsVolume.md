# MspCleanupIoBatchLookaside(CmsVolume *)

- ea: `0x1400e0248`
- end: `0x1400e02db`
- name: `?MspCleanupIoBatchLookaside@@YAXPEAVCmsVolume@@@Z`
- size: `147`
- prototype: `void __fastcall(struct CmsVolume *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14008bca0`
- `0x14009e434`

## callees

- `0x1400e0248`
- `0x1400e1368`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400e0264`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400e0264`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400e0295`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400e0295`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400e02a3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400e02a3`

## pseudocode

```c

```
