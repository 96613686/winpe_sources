# SHGetDefaultConnectedIdentityProvider(_GUID *)

- ea: `0x1800dcbac`
- end: `0x1800dcc9a`
- name: `?SHGetDefaultConnectedIdentityProvider@@YAJPEAU_GUID@@@Z`
- size: `238`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c4ad0`

## callees

- `0x180050ba0`
- `0x1800dcbac`
- `0x1800dcca0`
- `0x1800dccec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dcc1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dcc1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dcc54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dcc54`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x1800dcc0b`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x1800dcc38`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x1800dcc0b`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x1800dcc38`
- `api-ms-win-security-lsalookup-l1-1-1!GetDefaultIdentityProvider` at `0x1800dcbf1`
- `api-ms-win-security-lsalookup-l1-1-1!GetDefaultIdentityProvider` at `0x1800dcbf1`

## pseudocode

```c

```
