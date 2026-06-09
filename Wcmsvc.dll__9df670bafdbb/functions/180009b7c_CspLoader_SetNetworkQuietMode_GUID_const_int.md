# CspLoader::SetNetworkQuietMode(_GUID const *,int)

- ea: `0x180009b7c`
- end: `0x180009cb6`
- name: `?SetNetworkQuietMode@CspLoader@@QEAAKPEBU_GUID@@H@Z`
- size: `314`
- prototype: `unsigned int __fastcall(CspLoader *__hidden this, const struct _GUID *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001f974`

## callees

- `0x180009b7c`
- `0x180009cbc`
- `0x180010080`
- `0x180087ab8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009b99`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009b99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009bee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009c62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009c7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009bee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009c62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009c7c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009c3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009c3d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009c14`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009c14`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009c2c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009c2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009be3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009be3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009bf6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009bf6`

## string_xrefs

- `0x180009c98`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c

```
