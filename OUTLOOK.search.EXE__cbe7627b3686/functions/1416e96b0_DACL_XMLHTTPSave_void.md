# DACL::XMLHTTPSave(void)

- ea: `0x1416e96b0`
- end: `0x1416e9a98`
- name: `?XMLHTTPSave@DACL@@QEAAHXZ`
- size: `1000`
- prototype: `__int64 __fastcall(DACL *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1417176f0`

## callees

- `0x1402c4e18`
- `0x14050a340`
- `0x1407e9990`
- `0x1416e9048`
- `0x1416e96b0`

## import_xrefs

- `OLMAPI32!EtwTraceErrorTag` at `0x1416e9a17`
- `OLMAPI32!EtwTraceErrorTag` at `0x1416e9a17`
- `OLEAUT32!__imp_SysAllocString` at `0x1416e983a`
- `OLEAUT32!__imp_SysAllocString` at `0x1416e9863`
- `OLEAUT32!__imp_SysAllocString` at `0x1416e983a`
- `OLEAUT32!__imp_SysAllocString` at `0x1416e9863`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1416e98c7`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1416e98c7`
- `OLEAUT32!__imp_SysFreeString` at `0x1416e9a20`
- `OLEAUT32!__imp_SysFreeString` at `0x1416e9a29`
- `OLEAUT32!__imp_SysFreeString` at `0x1416e9a33`
- `OLEAUT32!__imp_SysFreeString` at `0x1416e9a40`
- `OLEAUT32!__imp_SysFreeString` at `0x1416e9a20`
- `OLEAUT32!__imp_SysFreeString` at `0x1416e9a29`
- `OLEAUT32!__imp_SysFreeString` at `0x1416e9a33`
- `OLEAUT32!__imp_SysFreeString` at `0x1416e9a40`
- `OLEAUT32!__imp_SysStringLen` at `0x1416e98a4`
- `OLEAUT32!__imp_SysStringLen` at `0x1416e98af`
- `OLEAUT32!__imp_SysStringLen` at `0x1416e98ba`
- `OLEAUT32!__imp_SysStringLen` at `0x1416e98e2`
- `OLEAUT32!__imp_SysStringLen` at `0x1416e98fc`
- `OLEAUT32!__imp_SysStringLen` at `0x1416e990b`
- `OLEAUT32!__imp_SysStringLen` at `0x1416e9928`
- `OLEAUT32!__imp_SysStringLen` at `0x1416e9933`
- `OLEAUT32!__imp_SysStringLen` at `0x1416e9941`
- `OLEAUT32!__imp_SysStringLen` at `0x1416e995d`
- `OLEAUT32!__imp_SysStringLen` at `0x1416e9968`
- `OLEAUT32!__imp_SysStringLen` at `0x1416e9973`
- `OLEAUT32!__imp_SysStringLen` at `0x1416e98a4`
- `OLEAUT32!__imp_SysStringLen` at `0x1416e98af`
- `OLEAUT32!__imp_SysStringLen` at `0x1416e98ba`
- `OLEAUT32!__imp_SysStringLen` at `0x1416e98e2`
- `OLEAUT32!__imp_SysStringLen` at `0x1416e98fc`
- `OLEAUT32!__imp_SysStringLen` at `0x1416e990b`
- `OLEAUT32!__imp_SysStringLen` at `0x1416e9928`
- `OLEAUT32!__imp_SysStringLen` at `0x1416e9933`
- `OLEAUT32!__imp_SysStringLen` at `0x1416e9941`
- `OLEAUT32!__imp_SysStringLen` at `0x1416e995d`
- `OLEAUT32!__imp_SysStringLen` at `0x1416e9968`
- `OLEAUT32!__imp_SysStringLen` at `0x1416e9973`
- `OLEAUT32!__imp_VariantInit` at `0x1416e96d9`
- `OLEAUT32!__imp_VariantInit` at `0x1416e96e3`
- `OLEAUT32!__imp_VariantInit` at `0x1416e96ed`
- `OLEAUT32!__imp_VariantInit` at `0x1416e96d9`
- `OLEAUT32!__imp_VariantInit` at `0x1416e96e3`
- `OLEAUT32!__imp_VariantInit` at `0x1416e96ed`
- `OLEAUT32!__imp_VariantClear` at `0x1416e9989`
- `OLEAUT32!__imp_VariantClear` at `0x1416e9a69`
- `OLEAUT32!__imp_VariantClear` at `0x1416e9a73`
- `OLEAUT32!__imp_VariantClear` at `0x1416e9a7e`
- `OLEAUT32!__imp_VariantClear` at `0x1416e9989`
- `OLEAUT32!__imp_VariantClear` at `0x1416e9a69`
- `OLEAUT32!__imp_VariantClear` at `0x1416e9a73`
- `OLEAUT32!__imp_VariantClear` at `0x1416e9a7e`
- `Mso20Win32Client!__imp_TWCCoCreateInstance` at `0x1416e9734`
- `Mso20Win32Client!__imp_TWCCoCreateInstance` at `0x1416e9734`

## string_xrefs

- `0x1416e9833`: `<?xml version='1.0'?>\n<d:propertyupdate xmlns:d='DAV:' xmlns:S='http://schemas.microsoft.com/security/' xmlns:exsec='http://schemas.microsoft.com/exchange/security/'>\n<d:set><d:prop><exsec:descriptor>\n<S:security_descriptor xmlns:data='urn:uuid:c2f41010-65b3-11d1-a29f-00aa00c14882/' data:dt='microsoft.security_descriptor'>\n`
- `0x1416e985c`: `</S:security_descriptor>\n</exsec:descriptor></d:prop></d:set>\n</d:propertyupdate>\n`
- `0x1416e97dc`: `text/xml`

## pseudocode

```c

```
