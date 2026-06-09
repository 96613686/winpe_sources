# CSecurityData::GetKdcForestRoot(_UNICODE_STRING *)

- ea: `0x180057130`
- end: `0x180057186`
- name: `?GetKdcForestRoot@CSecurityData@@QEAAJPEAU_UNICODE_STRING@@@Z`
- size: `86`
- prototype: `__int64 __fastcall(CSecurityData *this, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180057634`
- `0x18005f318`

## callees

- `0x180057130`
- `0x18007c4d4`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x18005714b`
- `ntdll!RtlAcquireResourceShared` at `0x18005714b`
- `ntdll!RtlReleaseResource` at `0x180057173`
- `ntdll!RtlReleaseResource` at `0x180057173`

## pseudocode

```c

```
