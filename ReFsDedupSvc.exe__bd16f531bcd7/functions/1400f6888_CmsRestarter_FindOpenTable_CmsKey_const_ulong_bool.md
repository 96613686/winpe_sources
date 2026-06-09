# CmsRestarter::FindOpenTable(_CmsKey const &,ulong,bool)

- ea: `0x1400f6888`
- end: `0x1400f68f5`
- name: `?FindOpenTable@CmsRestarter@@AEAAPEAUSmsOpenTable@@AEBU_CmsKey@@K_N@Z`
- size: `109`
- prototype: `struct SmsOpenTable *__fastcall(CmsRestarter *__hidden this, const struct _CmsKey *, unsigned int, bool)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400f7a48`
- `0x1400f91a8`

## callees

- `0x1400f6888`
- `0x1400f68fc`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x1400f68ce`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400f68ce`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400f68dc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400f68dc`
- `ntdll!RtlAcquireSRWLockShared` at `0x1400f68a4`
- `ntdll!RtlAcquireSRWLockShared` at `0x1400f68a4`

## pseudocode

```c

```
