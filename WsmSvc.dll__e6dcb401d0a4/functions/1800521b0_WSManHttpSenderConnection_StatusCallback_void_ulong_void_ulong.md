# WSManHttpSenderConnection::StatusCallback(void *,ulong,void *,ulong)

- ea: `0x1800521b0`
- end: `0x18005341b`
- name: `?StatusCallback@WSManHttpSenderConnection@@AEAAXPEAXK0K@Z`
- size: `4715`
- prototype: `void __usercall(WSManHttpSenderConnection *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, void *@<r9>, unsigned int)`
- caller_count: `1`
- callee_count: `34`
- tags: `loader_planting, service_task`

## callers

- `0x180052150`

## callees

- `0x180005d10`
- `0x18002c580`
- `0x180051d20`
- `0x1800521b0`
- `0x180053424`
- `0x1800535f0`
- `0x180053ccc`
- `0x180053ea8`
- `0x180054068`
- `0x180054148`
- `0x180065ab8`
- `0x18007ec20`
- `0x1800a3980`
- `0x1800aca80`
- `0x1800af400`
- `0x1800b64b4`
- `0x1800c123c`
- `0x180112380`
- `0x1801123a8`
- `0x180112460`
- `0x18011349c`
- `0x18011a6d4`
- `0x18011d870`
- `0x180132100`
- `0x180132cd4`
- `0x180132fd4`
- `0x1801340a8`
- `0x180134118`
- `0x1801343ec`
- `0x180134450`
- `0x1801344d0`
- `0x18015b9e0`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052274`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800522f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005257f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800525af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800525df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800527b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052274`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800522f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005257f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800525af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800525df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800527b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800521e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052280`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800521e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052280`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052344`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052344`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800524d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800524d1`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800524b9`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800524b9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180052298`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800522e8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180052298`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800522e8`
- `ntdll!EtwEventProviderEnabled` at `0x180052265`
- `ntdll!EtwEventProviderEnabled` at `0x180052265`
- `WINHTTP!WinHttpCloseHandle` at `0x180052f60`
- `WINHTTP!WinHttpCloseHandle` at `0x180052f60`

## string_xrefs

- `0x18005259c`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`
- `0x1800525cc`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`

## pseudocode

```c

```
