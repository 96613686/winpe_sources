# ChangeProcessPriorityState(void *,ThreadPriorityLevel,bool)

- ea: `0x18004a514`
- end: `0x18004a767`
- name: `?ChangeProcessPriorityState@@YAJPEAXW4ThreadPriorityLevel@@_N@Z`
- size: `595`
- prototype: `__int64 __fastcall(void *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180016f8c`

## callees

- `0x180003180`
- `0x1800110fc`
- `0x18001ad1c`
- `0x180045c9c`
- `0x18004a514`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x18004a54a`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x18004a54a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a561`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a5bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a65d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a561`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a5bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a65d`
- `api-ms-win-core-processthreads-l1-1-3!SetProcessInformation` at `0x18004a5b2`
- `api-ms-win-core-processthreads-l1-1-3!SetProcessInformation` at `0x18004a653`
- `api-ms-win-core-processthreads-l1-1-3!SetProcessInformation` at `0x18004a5b2`
- `api-ms-win-core-processthreads-l1-1-3!SetProcessInformation` at `0x18004a653`

## string_xrefs

- `0x18004a603`: `Attempt to %ws process EcoQos failed with hr=0x%08x`

## pseudocode

```c

```
