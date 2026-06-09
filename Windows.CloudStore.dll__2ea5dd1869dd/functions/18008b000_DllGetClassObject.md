# DllGetClassObject

- ea: `0x18008b000`
- end: `0x18008b262`
- name: `DllGetClassObject`
- size: `610`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18008b000`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18008b11a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18008b11a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008b1ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008b1ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008b15c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008b218`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008b15c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008b218`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008b1e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008b1e8`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18008b05d`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18008b05d`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18008b130`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18008b223`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18008b130`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18008b223`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18008b1d3`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18008b1d3`
- `RPCRT4!NdrDllGetClassObject` at `0x18008b039`
- `RPCRT4!NdrDllGetClassObject` at `0x18008b039`

## pseudocode

```c

```
