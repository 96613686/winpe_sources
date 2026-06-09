# DllGetClassObject

- ea: `0x1800440c8`
- end: `0x1800441bb`
- name: `DllGetClassObject`
- size: `243`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180044080`

## callees

- `0x1800440c8`
- `0x1800441c4`
- `0x180073d0c`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memcmp` at `0x1800440f6`
- `api-ms-win-crt-private-l1-1-0!memcmp` at `0x180044113`
- `api-ms-win-crt-private-l1-1-0!memcmp` at `0x180044150`
- `api-ms-win-crt-private-l1-1-0!memcmp` at `0x1800440f6`
- `api-ms-win-crt-private-l1-1-0!memcmp` at `0x180044113`
- `api-ms-win-crt-private-l1-1-0!memcmp` at `0x180044150`

## pseudocode

```c

```
