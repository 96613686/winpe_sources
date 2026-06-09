# CProfileManager::WMIUnloadProfile(UserRecord *,void *,IRequestContext *)

- ea: `0x18018128c`
- end: `0x180181954`
- name: `?WMIUnloadProfile@CProfileManager@@IEAAHPEAVUserRecord@@PEAXPEAVIRequestContext@@@Z`
- size: `1736`
- prototype: `int(CProfileManager *__hidden this, struct UserRecord *, void *, struct IRequestContext *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task`

## callers

- `0x180180390`
- `0x180180758`

## callees

- `0x180005d10`
- `0x18009bc00`
- `0x180112380`
- `0x1801123a8`
- `0x180180054`
- `0x18018128c`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_i64tow_s` at `0x1801815b7`
- `msvcrt!_i64tow_s` at `0x180181710`
- `msvcrt!_i64tow_s` at `0x1801815b7`
- `msvcrt!_i64tow_s` at `0x180181710`
- `OLEAUT32!__imp_SysAllocString` at `0x1801815c1`
- `OLEAUT32!__imp_SysAllocString` at `0x18018171a`
- `OLEAUT32!__imp_SysAllocString` at `0x1801815c1`
- `OLEAUT32!__imp_SysAllocString` at `0x18018171a`
- `OLEAUT32!__imp_VariantInit` at `0x1801814db`
- `OLEAUT32!__imp_VariantInit` at `0x1801814db`
- `OLEAUT32!__imp_VariantClear` at `0x18018151b`
- `OLEAUT32!__imp_VariantClear` at `0x180181673`
- `OLEAUT32!__imp_VariantClear` at `0x1801817c7`
- `OLEAUT32!__imp_VariantClear` at `0x18018151b`
- `OLEAUT32!__imp_VariantClear` at `0x180181673`
- `OLEAUT32!__imp_VariantClear` at `0x1801817c7`

## string_xrefs

- `0x18018130f`: `onecore\admin\wmi\wmx\service\profilemanager.cpp`
- `0x18018138e`: `WinRMAgent`
- `0x180181875`: `WinRMAgent`
- `0x180181505`: `ProcessId`
- `0x18018165d`: `Token`

## pseudocode

```c

```
