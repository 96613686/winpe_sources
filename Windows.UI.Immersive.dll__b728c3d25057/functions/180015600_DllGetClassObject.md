# DllGetClassObject

- ea: `0x180015600`
- end: `0x18001582c`
- name: `DllGetClassObject`
- size: `556`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180015600`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001562f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001562f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800156e6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800156e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800157e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800157e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015728`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800157fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015728`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800157fd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001578c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001578c`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800156fc`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800157cc`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800156fc`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800157cc`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800157a6`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800157a6`

## pseudocode

```c

```
