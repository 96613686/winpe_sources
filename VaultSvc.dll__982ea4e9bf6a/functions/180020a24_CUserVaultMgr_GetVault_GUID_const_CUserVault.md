# CUserVaultMgr::GetVault(_GUID const *,CUserVault * *)

- ea: `0x180020a24`
- end: `0x180020b08`
- name: `?GetVault@CUserVaultMgr@@QEAAKPEBU_GUID@@PEAPEAVCUserVault@@@Z`
- size: `228`
- prototype: `__int64 __fastcall(CUserVaultMgr *this, const struct _GUID *, struct CUserVault **)`
- caller_count: `8`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180022290`
- `0x180026a80`
- `0x18002d090`
- `0x180034058`
- `0x18003c62c`
- `0x180046040`
- `0x180046920`
- `0x180046d90`

## callees

- `0x18001fe80`
- `0x180020a24`
- `0x180020b10`
- `0x18003cb70`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180020af3`
- `ntdll!RtlReleaseResource` at `0x180020af3`
- `ntdll!RtlAcquireResourceExclusive` at `0x180020a48`
- `ntdll!RtlAcquireResourceExclusive` at `0x180020a48`

## pseudocode

```c

```
