# CallerIdentity::GetPackageFamilyNameFromProcess(void *,ushort * *)

- ea: `0x1800d8974`
- end: `0x1800d8a38`
- name: `?GetPackageFamilyNameFromProcess@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `196`
- prototype: `__int64 __fastcall(HANDLE hProcess, void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d877c`

## callees

- `0x180019bd0`
- `0x1800d8974`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d89cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d8a23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d89cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d8a23`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x1800d899d`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x1800d89ff`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x1800d899d`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x1800d89ff`

## pseudocode

```c

```
