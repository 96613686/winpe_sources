# Service::Start(void)

- ea: `0x1800032e8`
- end: `0x18000337b`
- name: `?Start@Service@@QEAAJXZ`
- size: `147`
- prototype: `__int64 __fastcall(Service *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003130`

## callees

- `0x1800032e8`
- `0x180003910`
- `0x18000cb8c`
- `0x18003f130`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180003363`
- `msvcp_win!_Mtx_unlock` at `0x180003363`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x180003329`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x180003329`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180003310`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180003310`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003353`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003353`

## pseudocode

```c

```
