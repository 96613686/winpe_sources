# CSecurityData::SetForestRoot(_UNICODE_STRING *)

- ea: `0x18005b294`
- end: `0x18005b32d`
- name: `?SetForestRoot@CSecurityData@@QEAAJPEAU_UNICODE_STRING@@@Z`
- size: `153`
- prototype: `int(CSecurityData *__hidden this, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005718c`

## callees

- `0x18005ad20`
- `0x18005b294`
- `0x18007c4d4`
- `0x18007dc20`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18005b315`
- `ntdll!RtlReleaseResource` at `0x18005b315`
- `ntdll!RtlAcquireResourceExclusive` at `0x18005b2af`
- `ntdll!RtlAcquireResourceExclusive` at `0x18005b2af`

## pseudocode

```c

```
