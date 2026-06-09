# CmsVolumeHeatEngine::RemoveContainerIfTracked(CmsTransactionContext *,SmsContainer *,bool)

- ea: `0x1400f233c`
- end: `0x1400f240c`
- name: `?RemoveContainerIfTracked@CmsVolumeHeatEngine@@QEAAXPEAVCmsTransactionContext@@PEAUSmsContainer@@_N@Z`
- size: `208`
- prototype: `void __fastcall(CmsVolumeHeatEngine *__hidden this, struct CmsTransactionContext *, struct SmsContainer *, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400c3ac0`
- `0x140123f10`

## callees

- `0x1400838b4`
- `0x140095090`
- `0x1400f233c`
- `0x1400f3e80`
- `0x14011a2ec`

## import_xrefs

- `ntdll!RtlTryAcquireSRWLockExclusive` at `0x1400f2357`
- `ntdll!RtlTryAcquireSRWLockExclusive` at `0x1400f2357`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400f23e6`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400f23e6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400f23f4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400f23f4`

## pseudocode

```c

```
