# TimerBrokerHelper::TimerWnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x180075580`
- end: `0x18007573d`
- name: `?TimerWnfCallback@TimerBrokerHelper@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `445`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, unsigned int, struct _WNF_TYPE_ID *, void *, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18002ee38`
- `0x180075580`
- `0x1800a0b2c`
- `0x1800af0a4`
- `0x1800b99f0`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800755fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800755fd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800755cd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800755cd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18007563e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18007563e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18007560b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18007560b`

## string_xrefs

- `0x180075692`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\timerbrokerhelper.cpp`
- `0x1800756eb`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\timerbrokerhelper.cpp`

## pseudocode

```c

```
