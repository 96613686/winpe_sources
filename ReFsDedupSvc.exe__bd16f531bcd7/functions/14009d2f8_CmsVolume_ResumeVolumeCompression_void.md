# CmsVolume::ResumeVolumeCompression(void)

- ea: `0x14009d2f8`
- end: `0x14009d374`
- name: `?ResumeVolumeCompression@CmsVolume@@QEAAXXZ`
- size: `124`
- prototype: `void __fastcall(CmsVolume *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400852e0`

## callees

- `0x14009d2f8`
- `0x1400a31c8`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x14009d30f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14009d30f`
- `ntdll!RtlReleaseSRWLockShared` at `0x14009d34e`
- `ntdll!RtlReleaseSRWLockShared` at `0x14009d34e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14009d35c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14009d35c`

## pseudocode

```c

```
