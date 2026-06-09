# SensorProfile::IsControlAllowed(KSIDENTIFIER *,uchar *,ulong,int *)

- ea: `0x18001c340`
- end: `0x18001c5d2`
- name: `?IsControlAllowed@SensorProfile@@UEAAJPEAUKSIDENTIFIER@@PEAEKPEAH@Z`
- size: `658`
- prototype: `__int64 __fastcall(SensorProfile *__hidden this, struct KSIDENTIFIER *, unsigned __int8 *, unsigned int, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x180005fa0`
- `0x18001bd24`
- `0x18001c274`
- `0x18001c340`
- `0x18001c854`
- `0x18001c96c`
- `0x18001cd8c`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c3f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c3f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c3df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c3df`

## pseudocode

```c

```
