# NgcUtils::ProcessPriorityManager::SetProcessPriorityForDuration(ulong,ulong)

- ea: `0x1800458f0`
- end: `0x1800459cc`
- name: `?SetProcessPriorityForDuration@ProcessPriorityManager@NgcUtils@@QEAAJKK@Z`
- size: `220`
- prototype: `__int64 __fastcall(NgcUtils::ProcessPriorityManager *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800315c0`
- `0x180045740`

## callees

- `0x180007964`
- `0x180029f0c`
- `0x1800458f0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180045993`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180045993`
- `api-ms-win-core-processthreads-l1-1-0!GetPriorityClass` at `0x18004590e`
- `api-ms-win-core-processthreads-l1-1-0!GetPriorityClass` at `0x18004590e`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x180045955`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x180045955`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180045902`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180045902`

## string_xrefs

- `0x180045964`: `onecore\ds\security\ngc\utils\common\lib\processutils.cpp`

## pseudocode

```c

```
