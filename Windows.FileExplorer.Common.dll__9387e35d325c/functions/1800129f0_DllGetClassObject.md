# DllGetClassObject

- ea: `0x1800129f0`
- end: `0x180012c1a`
- name: `DllGetClassObject`
- size: `554`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800129f0`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180012a1f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180012a1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180012b14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180012bc7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180012b14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180012bc7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012b7b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012b7b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180012ad6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180012ad6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012baa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012baa`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180012b95`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180012b95`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180012ae8`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180012bd2`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180012ae8`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180012bd2`

## pseudocode

```c

```
