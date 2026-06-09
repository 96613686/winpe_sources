# GetNetworkNameFromIfIndex

- ea: `0x18003fc54`
- end: `0x180040335`
- name: `GetNetworkNameFromIfIndex`
- size: `1761`
- prototype: `__int64 __fastcall(NET_IFINDEX InterfaceIndex)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000d160`
- `0x18000e2d8`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18003fc54`
- `0x18004986c`
- `0x1800e71e2`
- `0x1800e7260`
- `0x1800e9010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180040172`
- `msvcrt!wcscpy_s` at `0x180040172`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004015b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004015b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004026c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004026c`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x18003fcf4`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x18003fcf4`
- `IPHLPAPI!ConvertInterfaceLuidToGuid` at `0x18003fd49`
- `IPHLPAPI!ConvertInterfaceLuidToGuid` at `0x18003fd49`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003fe2a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003fe2a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003fd8b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003fd8b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800402a1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800402a1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800401c0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800401c0`
- `OLEAUT32!__imp_VariantInit` at `0x180040068`
- `OLEAUT32!__imp_VariantInit` at `0x180040068`

## pseudocode

```c

```
