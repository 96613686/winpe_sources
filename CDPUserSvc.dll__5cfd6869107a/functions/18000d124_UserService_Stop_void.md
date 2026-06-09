# UserService::Stop(void)

- ea: `0x18000d124`
- end: `0x18000d27f`
- name: `?Stop@UserService@@QEAAJXZ`
- size: `347`
- prototype: `__int64 __fastcall(UserService *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800598c0`

## callees

- `0x180003678`
- `0x180006494`
- `0x1800097d0`
- `0x18000c4dc`
- `0x18000d124`
- `0x18000d34c`
- `0x180020278`
- `0x1800259b4`
- `0x180057438`
- `0x18005a0cc`

## import_xrefs

- `msvcp_win!_Cnd_broadcast` at `0x18000d153`
- `msvcp_win!_Cnd_broadcast` at `0x18000d153`
- `msvcp_win!_Mtx_unlock` at `0x18000d266`
- `msvcp_win!_Mtx_unlock` at `0x18000d266`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x18000d22b`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x18000d22b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000d244`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000d244`
- `cdp!CDPSetAccountProviderInternal` at `0x18000d18c`
- `cdp!CDPSetAccountProviderInternal` at `0x18000d18c`
- `cdp!CDPPreShutdown` at `0x18000d159`
- `cdp!CDPPreShutdown` at `0x18000d159`

## pseudocode

```c

```
