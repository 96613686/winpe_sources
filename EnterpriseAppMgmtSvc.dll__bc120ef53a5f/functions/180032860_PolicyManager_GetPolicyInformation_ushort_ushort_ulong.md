# PolicyManager::GetPolicyInformation(ushort * *,ushort * *,ulong *)

- ea: `0x180032860`
- end: `0x180032a8f`
- name: `?GetPolicyInformation@PolicyManager@@IEAAJPEAPEAG0PEAK@Z`
- size: `559`
- prototype: `int(PolicyManager *__hidden this, unsigned __int16 **, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18003217c`

## callees

- `0x1800069dc`
- `0x180007404`
- `0x180032860`
- `0x180032e70`
- `0x180032eec`
- `0x18006c910`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180032933`
- `OLEAUT32!__imp_SysAllocString` at `0x18003295e`
- `OLEAUT32!__imp_SysAllocString` at `0x180032933`
- `OLEAUT32!__imp_SysAllocString` at `0x18003295e`
- `OLEAUT32!__imp_SysFreeString` at `0x18003294a`
- `OLEAUT32!__imp_SysFreeString` at `0x180032a59`
- `OLEAUT32!__imp_SysFreeString` at `0x18003294a`
- `OLEAUT32!__imp_SysFreeString` at `0x180032a59`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetApplicationManagementPolicy_ApplicationRestrictions` at `0x1800328ee`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetApplicationManagementPolicy_ApplicationRestrictions` at `0x1800328ee`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x180032a4a`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x180032a4a`

## string_xrefs

- `0x1800328d0`: `TestPolicyXml`
- `0x18003299c`: `PolicyXml`

## pseudocode

```c

```
