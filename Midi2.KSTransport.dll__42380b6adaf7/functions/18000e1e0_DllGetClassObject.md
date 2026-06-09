# DllGetClassObject

- ea: `0x18000e1e0`
- end: `0x18000e2e6`
- name: `DllGetClassObject`
- size: `262`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000e1e0`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e2a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e2a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e27d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e27d`

## pseudocode

```c

```
