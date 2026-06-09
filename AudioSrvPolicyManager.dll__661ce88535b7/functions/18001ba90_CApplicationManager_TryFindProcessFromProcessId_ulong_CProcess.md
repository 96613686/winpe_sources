# CApplicationManager::TryFindProcessFromProcessId(ulong,CProcess * *)

- ea: `0x18001ba90`
- end: `0x18001bb1c`
- name: `?TryFindProcessFromProcessId@CApplicationManager@@QEAAJKPEAPEAVCProcess@@@Z`
- size: `140`
- prototype: `__int64 __fastcall(CApplicationManager *__hidden this, unsigned int, struct CProcess **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18002f93c`
- `0x180043bf0`

## callees

- `0x18001ba90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001bafe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001bafe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001bab0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001bab0`

## pseudocode

```c

```
