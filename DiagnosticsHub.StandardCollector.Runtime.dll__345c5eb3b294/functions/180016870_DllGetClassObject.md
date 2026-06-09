# DllGetClassObject

- ea: `0x180016870`
- end: `0x1800168f1`
- name: `DllGetClassObject`
- size: `129`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180016870`
- `0x1800169fc`
- `0x180016ba0`
- `0x180016d28`

## import_xrefs

- `VCRUNTIME140!memcmp` at `0x180016895`
- `VCRUNTIME140!memcmp` at `0x1800168bc`
- `VCRUNTIME140!memcmp` at `0x180016895`
- `VCRUNTIME140!memcmp` at `0x1800168bc`

## pseudocode

```c

```
