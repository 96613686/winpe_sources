# Concurrency::details::_Task_impl<std::shared_ptr<Microsoft::Windows::Autopilot::IAutopilotUpdatePayload>>::_FinalizeAndRunContinuations(std::shared_ptr<Microsoft::Windows::Autopilot::IAutopilotUpdatePayload>)

- ea: `0x180192914`
- end: `0x180192a05`
- name: `?_FinalizeAndRunContinuations@?$_Task_impl@V?$shared_ptr@VIAutopilotUpdatePayload@Autopilot@Windows@Microsoft@@@std@@@details@Concurrency@@QEAAXV?$shared_ptr@VIAutopilotUpdatePayload@Autopilot@Windows@Microsoft@@@std@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(Concurrency::details::_Task_impl_base *this)`
- caller_count: `6`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180191a04`
- `0x180191ac4`
- `0x180191b84`
- `0x180192810`
- `0x180192b8c`
- `0x180193540`

## callees

- `0x180077c04`
- `0x180094ce0`
- `0x1800966b8`
- `0x18011e0e8`
- `0x180192914`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180192981`
- `msvcp_win!_Mtx_unlock` at `0x180192996`
- `msvcp_win!_Mtx_unlock` at `0x1801929d8`
- `msvcp_win!_Mtx_unlock` at `0x180192981`
- `msvcp_win!_Mtx_unlock` at `0x180192996`
- `msvcp_win!_Mtx_unlock` at `0x1801929d8`
- `msvcp_win!_Cnd_broadcast` at `0x1801929c8`
- `msvcp_win!_Cnd_broadcast` at `0x1801929c8`

## pseudocode

```c

```
