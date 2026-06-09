# Concurrency::details::_Task_impl<std::shared_ptr<Microsoft::Windows::Autopilot::IAutopilotUpdatePayload>>::_FinalizeAndRunContinuations(std::shared_ptr<Microsoft::Windows::Autopilot::IAutopilotUpdatePayload>)

- ea: `0x18018dad4`
- end: `0x18018dbac`
- name: `?_FinalizeAndRunContinuations@?$_Task_impl@V?$shared_ptr@VIAutopilotUpdatePayload@Autopilot@Windows@Microsoft@@@std@@@details@Concurrency@@QEAAXV?$shared_ptr@VIAutopilotUpdatePayload@Autopilot@Windows@Microsoft@@@std@@@Z`
- size: `216`
- prototype: `__int64 __fastcall(Concurrency::details::_Task_impl_base *this)`
- caller_count: `6`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18018cbbc`
- `0x18018cc7c`
- `0x18018cd3c`
- `0x18018d9d0`
- `0x18018dcd0`
- `0x18018e5f8`

## callees

- `0x180077384`
- `0x180093a28`
- `0x1800953b4`
- `0x18011a7c8`
- `0x18018dad4`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18018db41`
- `msvcp_win!_Mtx_unlock` at `0x18018db50`
- `msvcp_win!_Mtx_unlock` at `0x18018db86`
- `msvcp_win!_Mtx_unlock` at `0x18018db41`
- `msvcp_win!_Mtx_unlock` at `0x18018db50`
- `msvcp_win!_Mtx_unlock` at `0x18018db86`
- `msvcp_win!_Cnd_broadcast` at `0x18018db7c`
- `msvcp_win!_Cnd_broadcast` at `0x18018db7c`

## pseudocode

```c

```
