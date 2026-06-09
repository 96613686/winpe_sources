# PhoneService::OnStopping(int)

- ea: `0x180007ef0`
- end: `0x1800081ad`
- name: `?OnStopping@PhoneService@@UEAAJH@Z`
- size: `701`
- prototype: `__int64 __fastcall(PhoneService *__hidden this, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x180006c98`

## callees

- `0x1800012b8`
- `0x180006e94`
- `0x180007b04`
- `0x180007ef0`
- `0x180009008`
- `0x1800157e0`
- `0x18004c13c`
- `0x18004c1f4`
- `0x18004c528`
- `0x180078d0c`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f65`
- `InprocLogger!ShutdownInProcLogger` at `0x18000819a`
- `InprocLogger!ShutdownInProcLogger` at `0x18000819a`
- `InprocLogger!ShutdownInProcTraceFlushTrigger` at `0x180008174`
- `InprocLogger!ShutdownInProcTraceFlushTrigger` at `0x180008174`
- `InprocLogger!ShutdownInProcTraceSession` at `0x180008194`
- `InprocLogger!ShutdownInProcTraceSession` at `0x180008194`

## string_xrefs

- `0x180007f0a`: `PhoneService: The Phone service is stopping.`
- `0x180007f99`: `PhoneService: Stopping Phone RPC server.`
- `0x18000814b`: `PhoneService: The Phone service has stopped.`
- `0x180007fd1`: `onecoreuap\net\phone\phoneservice\service\lib\securephonerpcserver.cpp`

## pseudocode

```c

```
