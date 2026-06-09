# DllGetClassObject

- ea: `0x180003880`
- end: `0x18000399e`
- name: `DllGetClassObject`
- size: `286`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003880`
- `0x180052906`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800038d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003972`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800038d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003972`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800038a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800038a0`

## pseudocode

```c

```
