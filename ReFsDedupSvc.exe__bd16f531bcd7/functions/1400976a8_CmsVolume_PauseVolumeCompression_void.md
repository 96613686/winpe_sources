# CmsVolume::PauseVolumeCompression(void)

- ea: `0x1400976a8`
- end: `0x140097702`
- name: `?PauseVolumeCompression@CmsVolume@@QEAAXXZ`
- size: `90`
- prototype: `void __fastcall(CmsVolume *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140084ff4`

## callees

- `0x1400916fc`
- `0x1400976a8`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400976bf`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400976bf`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400976dc`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400976dc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400976ea`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400976ea`

## pseudocode

```c

```
