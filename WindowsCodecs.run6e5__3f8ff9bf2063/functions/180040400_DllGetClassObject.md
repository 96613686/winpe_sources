# DllGetClassObject

- ea: `0x180040400`
- end: `0x180040482`
- name: `DllGetClassObject`
- size: `130`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180040400`
- `0x1800404fc`
- `0x180040650`
- `0x18004158c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040458`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040458`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040425`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040425`

## pseudocode

```c

```
