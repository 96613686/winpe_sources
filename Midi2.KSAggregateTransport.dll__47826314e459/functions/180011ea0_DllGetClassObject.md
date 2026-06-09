# DllGetClassObject

- ea: `0x180011ea0`
- end: `0x180011fa6`
- name: `DllGetClassObject`
- size: `262`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180011ea0`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011f3d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011f3d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011f68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011f68`

## pseudocode

```c

```
