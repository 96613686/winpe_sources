# wil::make_wnf_subscription_nothrow<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong)

- ea: `0x18002e590`
- end: `0x18002e778`
- name: `??$make_wnf_subscription_nothrow@Uempty_wnf_state@details@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@K@Z`
- size: `488`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18002c6e8`

## callees

- `0x18002e590`
- `0x18005d488`
- `0x18005d508`
- `0x18006f0d8`
- `0x18009d010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002e700`
- `KERNEL32!SetLastError` at `0x18002e700`
- `KERNEL32!GetLastError` at `0x18002e6ed`
- `KERNEL32!GetLastError` at `0x18002e6ed`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18002e6f8`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18002e6f8`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18002e6ce`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18002e6ce`
- `ntdll!NtQueryWnfStateData` at `0x18002e648`
- `ntdll!NtQueryWnfStateData` at `0x18002e648`

## pseudocode

```c

```
