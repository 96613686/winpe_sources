# DllGetClassObject

- ea: `0x18000d2d0`
- end: `0x18000d3d6`
- name: `DllGetClassObject`
- size: `262`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000d2d0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d36d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d36d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d398`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d398`

## pseudocode

```c

```
