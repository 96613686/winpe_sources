# Windows::Internal::ServiceModuleBase::Uninitialize(void)

- ea: `0x18000e0a8`
- end: `0x18000e1ab`
- name: `?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ`
- size: `259`
- prototype: `__int64 __fastcall(Windows::Internal::ServiceModuleBase *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000db30`

## callees

- `0x18000e0a8`
- `0x18000e4bc`
- `0x180068010`

## import_xrefs

- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18000e11a`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18000e11a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e169`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e17c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e17c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18000e18c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18000e18c`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x18000e174`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x18000e174`

## string_xrefs

- `0x18000e12c`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c

```
