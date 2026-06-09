# BipFindPackageForUser

- ea: `0x180053c04`
- end: `0x180053da5`
- name: `BipFindPackageForUser`
- size: `417`
- prototype: `__int64 __fastcall(PSID Sid2, OLECHAR *strIn, UINT ui)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004ecbc`

## callees

- `0x180006300`
- `0x1800121b0`
- `0x18002d280`
- `0x180038cf0`
- `0x180049660`
- `0x180053100`
- `0x180053c04`
- `0x180095010`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180053c2b`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180053c80`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180053c2b`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180053c80`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180053c6a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180053c6a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180053d8d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180053d8d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180053c4f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180053c4f`
- `OLEAUT32!__imp_SysFreeString` at `0x180053d6e`
- `OLEAUT32!__imp_SysFreeString` at `0x180053d6e`

## pseudocode

```c

```
