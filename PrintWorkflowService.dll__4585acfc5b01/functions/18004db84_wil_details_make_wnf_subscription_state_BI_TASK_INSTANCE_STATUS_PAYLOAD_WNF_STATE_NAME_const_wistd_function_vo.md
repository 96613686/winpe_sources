# wil::details::make_wnf_subscription_state<_BI_TASK_INSTANCE_STATUS_PAYLOAD>(_WNF_STATE_NAME const &,wistd::function<void (_BI_TASK_INSTANCE_STATUS_PAYLOAD const &)> &&,ulong,wil::details::wnf_subscription_state<_BI_TASK_INSTANCE_STATUS_PAYLOAD> * *)

- ea: `0x18004db84`
- end: `0x18004dd5b`
- name: `??$make_wnf_subscription_state@U_BI_TASK_INSTANCE_STATUS_PAYLOAD@@@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXAEBU_BI_TASK_INSTANCE_STATUS_PAYLOAD@@@Z@wistd@@KPEAPEAU?$wnf_subscription_state@U_BI_TASK_INSTANCE_STATUS_PAYLOAD@@@01@@Z`
- size: `471`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x18004db28`

## callees

- `0x180003d14`
- `0x180010b0c`
- `0x18004db84`
- `0x18004df1c`
- `0x18004ecfc`
- `0x18005e010`

## import_xrefs

- `ntdll!NtQueryWnfStateData` at `0x18004dc5d`
- `ntdll!NtQueryWnfStateData` at `0x18004dc5d`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18004dcfa`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18004dcfa`

## pseudocode

```c

```
