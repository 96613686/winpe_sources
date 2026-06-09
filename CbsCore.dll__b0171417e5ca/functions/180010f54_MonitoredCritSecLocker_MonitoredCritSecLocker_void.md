# MonitoredCritSecLocker::~MonitoredCritSecLocker(void)

- ea: `0x180010f54`
- end: `0x18001108c`
- name: `??1MonitoredCritSecLocker@@UEAA@XZ`
- size: `312`
- prototype: `void __fastcall(MonitoredCritSecLocker *__hidden this)`
- caller_count: `128`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b5fc`
- `0x18000c7e8`
- `0x18000dddc`
- `0x18000eb0c`
- `0x18000f090`
- `0x180010470`
- `0x180010eac`
- `0x180010f00`
- `0x1800115f0`
- `0x180012034`
- `0x180018ecc`
- `0x18001d160`
- `0x18001f5dc`
- `0x180022f68`
- `0x180024454`
- `0x1800268dc`
- `0x180026fe4`
- `0x18002fa74`
- `0x180031e24`
- `0x180046754`
- `0x180048118`
- `0x18004baa0`
- `0x18004da0c`
- `0x18004e388`
- `0x180052794`
- `0x180064cb0`
- `0x180067dc4`
- `0x180099700`
- `0x18009c068`
- `0x18009cabc`
- `0x1800a0acc`
- `0x1800a2404`
- `0x1800aa6dc`
- `0x1800ab1a8`
- `0x1800b0964`
- `0x1800b1c7c`
- `0x1800b21e4`
- `0x1800b2990`
- `0x1800b5f90`
- `0x1800b65dc`
- `0x1800b7dbc`
- `0x1800b851c`
- `0x1800b8854`
- `0x1800b8944`
- `0x1800b8bd8`
- `0x1800b8d9c`
- `0x1800be574`
- `0x1800be6c8`
- `0x1800c30c0`
- `0x1800c65f4`

## callees

- `0x180010f54`
- `0x180098538`
- `0x1800be858`
- `0x1800f84c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010f80`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010f80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010fe4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010ffe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010fe4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010ffe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010fc0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011036`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010fc0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011036`

## string_xrefs

- `0x18001104a`: `Lock: Error found, LeaveCriticalSection is called by the wrong thread. Owner thread: {}, current thread: {}`

## pseudocode

```c

```
