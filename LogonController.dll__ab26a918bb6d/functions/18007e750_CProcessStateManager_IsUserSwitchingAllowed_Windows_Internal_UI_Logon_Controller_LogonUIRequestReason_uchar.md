# CProcessStateManager::IsUserSwitchingAllowed(Windows::Internal::UI::Logon::Controller::LogonUIRequestReason,uchar *)

- ea: `0x18007e750`
- end: `0x18007e83e`
- name: `?IsUserSwitchingAllowed@CProcessStateManager@@UEAAJW4LogonUIRequestReason@Controller@Logon@UI@Internal@Windows@@PEAE@Z`
- size: `238`
- prototype: `int __high(enum Windows::Internal::UI::Logon::Controller::LogonUIRequestReason, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task`

## callees

- `0x18000be10`
- `0x180047a7c`
- `0x18005d488`
- `0x1800636b8`
- `0x18007e750`
- `0x18009d010`

## import_xrefs

- `SHCORE!__imp_SHWindowsPolicy` at `0x18007e7fb`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18007e7fb`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18007e76c`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18007e76c`
- `SLC!SLGetWindowsInformationDWORD` at `0x18007e792`
- `SLC!SLGetWindowsInformationDWORD` at `0x18007e792`

## string_xrefs

- `0x18007e78b`: `TerminalServices-RemoteConnectionManager-AllowMultipleSessions`

## pseudocode

```c

```
