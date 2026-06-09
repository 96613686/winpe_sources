# PowerProfileMgr::StartPerfBoost(void)

- ea: `0x1800904e0`
- end: `0x180090677`
- name: `?StartPerfBoost@PowerProfileMgr@@QEAAJXZ`
- size: `407`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18006d1f8`

## callees

- `0x1800010f4`
- `0x1800049a0`
- `0x1800127c0`
- `0x18008b778`
- `0x1800904e0`
- `0x180096490`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009056f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009056f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009050e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009050e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800905b2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800905b2`
- `ntdll!NtPowerInformation` at `0x1800905f3`
- `ntdll!NtPowerInformation` at `0x1800905f3`

## pseudocode

```c

```
