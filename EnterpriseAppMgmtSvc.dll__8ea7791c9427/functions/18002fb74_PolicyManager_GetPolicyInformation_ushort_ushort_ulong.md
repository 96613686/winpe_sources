# PolicyManager::GetPolicyInformation(ushort * *,ushort * *,ulong *)

- ea: `0x18002fb74`
- end: `0x18002fd7e`
- name: `?GetPolicyInformation@PolicyManager@@IEAAJPEAPEAG0PEAK@Z`
- size: `522`
- prototype: `int(PolicyManager *__hidden this, unsigned __int16 **, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002f4dc`

## callees

- `0x180006780`
- `0x18000715c`
- `0x18002fb74`
- `0x180030140`
- `0x1800301b4`
- `0x180066df0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002fc41`
- `OLEAUT32!__imp_SysAllocString` at `0x18002fc60`
- `OLEAUT32!__imp_SysAllocString` at `0x18002fc41`
- `OLEAUT32!__imp_SysAllocString` at `0x18002fc60`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fc52`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fd4f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fc52`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fd4f`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetApplicationManagementPolicy_ApplicationRestrictions` at `0x18002fc02`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetApplicationManagementPolicy_ApplicationRestrictions` at `0x18002fc02`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x18002fd46`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x18002fd46`

## string_xrefs

- `0x18002fbe4`: `TestPolicyXml`
- `0x18002fc98`: `PolicyXml`

## pseudocode

```c

```
