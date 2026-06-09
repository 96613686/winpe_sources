# FlightSettingsActionManager::TimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x18008e740`
- end: `0x18008e81e`
- name: `?TimerCallback@FlightSettingsActionManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `222`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000b19c`
- `0x180013da0`
- `0x1800177bc`
- `0x1800179ec`
- `0x18008e468`
- `0x18008e740`
- `0x18008f4b4`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18008e812`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18008e812`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18008e758`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18008e758`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18008e800`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18008e800`

## pseudocode

```c

```
