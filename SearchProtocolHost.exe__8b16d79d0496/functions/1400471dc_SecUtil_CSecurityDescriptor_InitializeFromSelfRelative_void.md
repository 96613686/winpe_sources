# SecUtil::CSecurityDescriptor::InitializeFromSelfRelative(void *)

- ea: `0x1400471dc`
- end: `0x140047311`
- name: `?InitializeFromSelfRelative@CSecurityDescriptor@SecUtil@@QEAAXPEAX@Z`
- size: `309`
- prototype: `void __fastcall(PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor, PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140022778`

## callees

- `0x14003178c`
- `0x140046e98`
- `0x1400471dc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x14004725f`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1400472e2`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x14004725f`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1400472e2`

## string_xrefs

- `0x1400472f0`: `onecoreuap\base\appmodel\search\common\secutil\secutil.cxx`

## pseudocode

```c

```
