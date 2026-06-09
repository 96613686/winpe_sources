# SHGetParsingNameFromPropertyStore(ushort const *,INamedPropertyStore *,ushort * *)

- ea: `0x1801222ec`
- end: `0x180122689`
- name: `?SHGetParsingNameFromPropertyStore@@YAJPEBGPEAUINamedPropertyStore@@PEAPEAG@Z`
- size: `925`
- prototype: `int(const unsigned __int16 *, struct INamedPropertyStore *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1801275c0`

## callees

- `0x18000c840`
- `0x18000dfda`
- `0x1801222ec`
- `0x180126900`
- `0x180127810`
- `0x1802203ac`
- `0x18022041c`
- `0x18022045c`
- `0x1802204e0`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801225d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801225f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801225d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801225f2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180122603`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180122603`
- `OLEAUT32!__imp_SysFreeString` at `0x180122614`
- `OLEAUT32!__imp_SysFreeString` at `0x180122614`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801224e3`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801224e3`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180122639`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180122639`
- `PROPSYS!PropVariantToStringAlloc` at `0x180122486`
- `PROPSYS!PropVariantToStringAlloc` at `0x180122486`

## string_xrefs

- `0x18012236e`: `::{d84fa0c2-b0b3-4470-9345-75db0ec5a83a},ChildCLSID={267cf8a9-f4e3-41e6-95b1-af881be130ff}&`
- `0x180122394`: `::{d84fa0c2-b0b3-4470-9345-75db0ec5a83a},ChildCLSID={267cf8a9-f4e3-41e6-95b1-af881be130ff}&`

## pseudocode

```c

```
