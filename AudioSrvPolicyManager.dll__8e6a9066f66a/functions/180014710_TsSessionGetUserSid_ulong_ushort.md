# TsSessionGetUserSid(ulong,ushort * *)

- ea: `0x180014710`
- end: `0x180014882`
- name: `?TsSessionGetUserSid@@YAJKPEAPEAG@Z`
- size: `370`
- prototype: `__int64 __fastcall(DWORD SessionId, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180012e64`
- `0x180014700`

## callees

- `0x180006fdc`
- `0x18000a384`
- `0x180014710`
- `0x180014bdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001472e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014749`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001472e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014749`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800147c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001480a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014836`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014862`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001486f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800147c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001480a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014836`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014862`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001486f`

## pseudocode

```c

```
