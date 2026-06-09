# CProfileManager::WMILoadProfile(UserRecord *,void *,IRequestContext *)

- ea: `0x180180a38`
- end: `0x180181286`
- name: `?WMILoadProfile@CProfileManager@@IEAAHPEAVUserRecord@@PEAXPEAVIRequestContext@@@Z`
- size: `2126`
- prototype: `int(CProfileManager *__hidden this, struct UserRecord *, void *, struct IRequestContext *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task`

## callers

- `0x180180390`

## callees

- `0x180005d10`
- `0x18009bc00`
- `0x180112380`
- `0x1801123a8`
- `0x180180054`
- `0x180180a38`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_i64tow_s` at `0x180180d8c`
- `msvcrt!_i64tow_s` at `0x180180d8c`
- `msvcrt!_wtoi64` at `0x180181220`
- `msvcrt!_wtoi64` at `0x180181220`
- `OLEAUT32!__imp_SysAllocString` at `0x180180e0d`
- `OLEAUT32!__imp_SysAllocString` at `0x180180f5b`
- `OLEAUT32!__imp_SysAllocString` at `0x180180e0d`
- `OLEAUT32!__imp_SysAllocString` at `0x180180f5b`
- `OLEAUT32!__imp_VariantInit` at `0x180180ca8`
- `OLEAUT32!__imp_VariantInit` at `0x180180ca8`
- `OLEAUT32!__imp_VariantClear` at `0x180180ce7`
- `OLEAUT32!__imp_VariantClear` at `0x180180ebe`
- `OLEAUT32!__imp_VariantClear` at `0x180181001`
- `OLEAUT32!__imp_VariantClear` at `0x180181232`
- `OLEAUT32!__imp_VariantClear` at `0x180180ce7`
- `OLEAUT32!__imp_VariantClear` at `0x180180ebe`
- `OLEAUT32!__imp_VariantClear` at `0x180181001`
- `OLEAUT32!__imp_VariantClear` at `0x180181232`

## string_xrefs

- `0x180180abb`: `onecore\admin\wmi\wmx\service\profilemanager.cpp`
- `0x180180b4e`: `WinRMAgent`
- `0x1801810be`: `WinRMAgent`
- `0x180180cd1`: `ProcessId`
- `0x180180ea8`: `Token`

## pseudocode

```c

```
