# CUserSettings::DuplicateUserToken(_SID *,void *,void * *)

- ea: `0x18019ce30`
- end: `0x18019cf4f`
- name: `?DuplicateUserToken@CUserSettings@@QEAAJPEAU_SID@@PEAXPEAPEAX@Z`
- size: `287`
- prototype: `__int64 __fastcall(CUserSettings *this, struct _SID *, void *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180067318`

## callees

- `0x180022710`
- `0x1800eb1b0`
- `0x18019ce30`
- `0x18019d12c`
- `0x18019d27c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18019cf1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18019cf1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18019cec8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18019cec8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18019cee7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18019cee7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18019cf09`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18019cf09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18019cf35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18019cf35`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18019ce8f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18019ce8f`

## pseudocode

```c

```
