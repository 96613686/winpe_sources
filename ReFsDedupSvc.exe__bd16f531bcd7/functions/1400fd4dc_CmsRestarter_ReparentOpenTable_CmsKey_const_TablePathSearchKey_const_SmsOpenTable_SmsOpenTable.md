# CmsRestarter::ReparentOpenTable(_CmsKey const &,TablePathSearchKey const &,SmsOpenTable *,SmsOpenTable &)

- ea: `0x1400fd4dc`
- end: `0x1400fd5f1`
- name: `?ReparentOpenTable@CmsRestarter@@AEAAJAEBU_CmsKey@@AEBUTablePathSearchKey@@PEAUSmsOpenTable@@AEAU4@@Z`
- size: `277`
- prototype: `int(CmsRestarter *__hidden this, const struct _CmsKey *, const struct TablePathSearchKey *, struct SmsOpenTable *, struct SmsOpenTable *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1400fb998`

## callees

- `0x1400f44c4`
- `0x1400f4b74`
- `0x1400f4e9c`
- `0x1400f761c`
- `0x1400f7724`
- `0x1400fd4dc`
- `0x1400ff45c`
- `0x1400ffb90`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400fd53e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400fd53e`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400fd5ad`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400fd5ad`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400fd5bb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400fd5bb`

## pseudocode

```c

```
