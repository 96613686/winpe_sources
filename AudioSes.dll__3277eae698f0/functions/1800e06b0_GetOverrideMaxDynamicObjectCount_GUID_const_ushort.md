# GetOverrideMaxDynamicObjectCount(_GUID const &,ushort)

- ea: `0x1800e06b0`
- end: `0x1800e0806`
- name: `?GetOverrideMaxDynamicObjectCount@@YAGAEBU_GUID@@G@Z`
- size: `342`
- prototype: `unsigned __int16 __fastcall(IID *rclsid, unsigned __int16)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800df2ac`
- `0x1800df6ac`
- `0x1800dfa4c`
- `0x1800dfbf4`
- `0x1800dfeec`

## callees

- `0x18004d5d8`
- `0x180087e80`
- `0x180088ce8`
- `0x1800e06b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e07c6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e07c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e07d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e07d9`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x1800e075e`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x1800e075e`

## pseudocode

```c

```
