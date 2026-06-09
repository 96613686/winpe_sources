# CmsVolume::HaltVolumeCompressionUnderLock(EmsVolumeCompressionState)

- ea: `0x1400916fc`
- end: `0x1400917ef`
- name: `?HaltVolumeCompressionUnderLock@CmsVolume@@AEAAXW4EmsVolumeCompressionState@@@Z`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400976a8`

## callees

- `0x1400916fc`
- `0x1400ab1fc`
- `0x1400ab594`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400917b3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400917b3`
- `ntdll!RtlReleaseSRWLockShared` at `0x14009178b`
- `ntdll!RtlReleaseSRWLockShared` at `0x14009178b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140091799`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140091799`

## pseudocode

```c

```
