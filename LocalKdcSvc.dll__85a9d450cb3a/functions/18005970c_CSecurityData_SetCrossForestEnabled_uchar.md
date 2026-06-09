# CSecurityData::SetCrossForestEnabled(uchar)

- ea: `0x18005970c`
- end: `0x18005973c`
- name: `?SetCrossForestEnabled@CSecurityData@@QEAAXE@Z`
- size: `48`
- prototype: `void __fastcall(CSecurityData *__hidden this, unsigned __int8)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005718c`
- `0x180058f64`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180059735`
- `ntdll!RtlAcquireResourceExclusive` at `0x18005971d`
- `ntdll!RtlAcquireResourceExclusive` at `0x18005971d`

## pseudocode

```c

```
