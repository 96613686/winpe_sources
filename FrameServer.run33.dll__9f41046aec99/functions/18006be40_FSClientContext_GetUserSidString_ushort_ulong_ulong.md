# FSClientContext::GetUserSidString(ushort *,ulong,ulong *)

- ea: `0x18006be40`
- end: `0x18006bf96`
- name: `?GetUserSidString@FSClientContext@@UEAAJPEAGKPEAK@Z`
- size: `342`
- prototype: `int(FSClientContext *__hidden this, unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180007bcc`
- `0x180009608`
- `0x180017014`
- `0x18006be40`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006bf81`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006bf81`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006be5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006be5d`

## pseudocode

```c

```
