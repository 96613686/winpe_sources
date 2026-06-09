# SecUtil::AppendACL(_ACL *,_ACL *)

- ea: `0x1800b965c`
- end: `0x1800b9772`
- name: `?AppendACL@SecUtil@@YAXPEAU_ACL@@0@Z`
- size: `278`
- prototype: `void __fastcall(PACL pAcl, PACL, struct _ACL *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800ab770`

## callees

- `0x1800b965c`
- `0x1801244c0`
- `0x18013dd98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b96b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9715`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9735`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b96b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9715`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9735`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800b9707`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800b9707`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800b96e3`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800b96e3`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1800b96a7`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1800b96a7`

## string_xrefs

- `0x1800b96bc`: `onecoreuap\base\appmodel\search\common\secutil\secutil.cxx`
- `0x1800b9720`: `onecoreuap\base\appmodel\search\common\secutil\secutil.cxx`
- `0x1800b9740`: `onecoreuap\base\appmodel\search\common\secutil\secutil.cxx`

## pseudocode

```c

```
