# MbaeDevNode::_GetDeviceInstanceIdForNetworkDevice(void *,_DO_DEVINFO_DATA *,ATL::CComBSTR *)

- ea: `0x1800bc1bc`
- end: `0x1800bc30f`
- name: `?_GetDeviceInstanceIdForNetworkDevice@MbaeDevNode@@KAJPEAXPEAU_DO_DEVINFO_DATA@@PEAVCComBSTR@ATL@@@Z`
- size: `339`
- prototype: `static int(void *, struct _DO_DEVINFO_DATA *, struct ATL::CComBSTR *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800bbd74`

## callees

- `0x180012300`
- `0x180019f24`
- `0x180074758`
- `0x1800b9b5c`
- `0x1800bc1bc`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800bc24a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800bc24a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800bc1ef`
- `OLEAUT32!__imp_SysFreeString` at `0x1800bc2ce`
- `OLEAUT32!__imp_SysFreeString` at `0x1800bc1ef`
- `OLEAUT32!__imp_SysFreeString` at `0x1800bc2ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc299`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc299`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x1800bc215`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x1800bc28f`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x1800bc215`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x1800bc28f`

## pseudocode

```c

```
