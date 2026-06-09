# FSSourceInfo::IsControlAllowedByProfile(KSIDENTIFIER *,uchar *,ulong)

- ea: `0x180084fc8`
- end: `0x18008524b`
- name: `?IsControlAllowedByProfile@FSSourceInfo@@QEAA_NPEAUKSIDENTIFIER@@PEAEK@Z`
- size: `643`
- prototype: `bool(FSSourceInfo *__hidden this, struct KSIDENTIFIER *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x18006e348`

## callees

- `0x180009608`
- `0x180017d90`
- `0x180018998`
- `0x18003b71c`
- `0x18004d714`
- `0x18004d748`
- `0x180084fc8`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085232`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085232`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180084ff4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180084ff4`

## pseudocode

```c

```
