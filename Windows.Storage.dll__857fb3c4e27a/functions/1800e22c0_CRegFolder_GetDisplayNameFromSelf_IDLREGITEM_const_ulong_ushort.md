# CRegFolder::_GetDisplayNameFromSelf(IDLREGITEM const *,ulong,ushort * *)

- ea: `0x1800e22c0`
- end: `0x1800e2c35`
- name: `?_GetDisplayNameFromSelf@CRegFolder@@AEAAJPEFBUIDLREGITEM@@KPEAPEAG@Z`
- size: `2421`
- prototype: `int(CRegFolder *__hidden this, const struct IDLREGITEM *, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18052bf88`

## callees

- `0x18000d6cc`
- `0x1800586b0`
- `0x18009b780`
- `0x1800ccbd0`
- `0x1800d13a0`
- `0x1800dfcf0`
- `0x1800e1b30`
- `0x1800e1c70`
- `0x1800e22c0`
- `0x1800e4330`
- `0x1800e4730`
- `0x1800e5690`
- `0x1800e5a70`
- `0x18014d4e0`
- `0x1801d5d70`
- `0x18027fca0`
- `0x180288824`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x1803a96d9`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e2496`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e28e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e29fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e2a53`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e2496`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e28e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e29fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e2a53`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e2853`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e2a3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e2a95`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e2b4d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e2853`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e2a3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e2a95`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e2b4d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800e239d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800e2629`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800e239d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800e2629`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e27de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e2a1e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e2a74`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e27de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e2a1e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e2a74`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e2817`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e2817`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e2803`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e2803`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e2915`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e2915`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e2720`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e2955`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e2720`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e2955`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x1800e25e7`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x1800e25e7`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x1800e2384`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x1800e2840`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x1800e2384`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x1800e2840`
- `SHCORE!__imp_StrRetToStrW` at `0x1800e278c`
- `SHCORE!__imp_StrRetToStrW` at `0x1800e278c`

## pseudocode

```c

```
