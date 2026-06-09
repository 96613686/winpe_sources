# CmsRollbackProtection::SetRollbackGUID(_GUID const &)

- ea: `0x140129f04`
- end: `0x14012a01d`
- name: `?SetRollbackGUID@CmsRollbackProtection@@AEAAJAEBU_GUID@@@Z`
- size: `281`
- prototype: `__int64 __fastcall(CmsRollbackProtection *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x14012a2c8`

## callees

- `0x1400830cc`
- `0x140129b90`
- `0x140129f04`

## import_xrefs

- `ntdll!RtlStringFromGUID` at `0x140129f25`
- `ntdll!RtlStringFromGUID` at `0x140129f25`
- `ntdll!RtlFreeUnicodeString` at `0x14012a005`
- `ntdll!RtlFreeUnicodeString` at `0x14012a005`

## string_xrefs

- `0x140129f65`: `:FailMountOnMismatch`
- `0x140129f8c`: `minkernel\fs\minstore\cmsrollbackprotection.cpp`

## pseudocode

```c

```
