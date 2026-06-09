# DllGetClassObject

- ea: `0x180033150`
- end: `0x1800331df`
- name: `DllGetClassObject`
- size: `143`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180033150`
- `0x180033260`
- `0x1800333c0`
- `0x180034e1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800331ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800331ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033175`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033175`

## pseudocode

```c

```
