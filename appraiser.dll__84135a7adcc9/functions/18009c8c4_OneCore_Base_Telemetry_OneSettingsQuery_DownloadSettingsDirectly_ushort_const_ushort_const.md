# OneCore::Base::Telemetry::OneSettingsQuery::DownloadSettingsDirectly(ushort const *,ushort const *)

- ea: `0x18009c8c4`
- end: `0x18009ca8e`
- name: `?DownloadSettingsDirectly@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG0@Z`
- size: `458`
- prototype: `__int64 __fastcall(void **this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800a20bc`

## callees

- `0x180008570`
- `0x18002d06c`
- `0x18009c8c4`
- `0x18009cc74`
- `0x1800a182c`
- `0x1800a3578`

## import_xrefs

- `KERNEL32!ExitProcess` at `0x18009ca34`
- `KERNEL32!ExitProcess` at `0x18009ca64`
- `KERNEL32!ExitProcess` at `0x18009ca34`
- `KERNEL32!ExitProcess` at `0x18009ca64`
- `KERNEL32!GetLastError` at `0x18009ca2c`
- `KERNEL32!GetLastError` at `0x18009ca3b`
- `KERNEL32!GetLastError` at `0x18009ca5c`
- `KERNEL32!GetLastError` at `0x18009ca2c`
- `KERNEL32!GetLastError` at `0x18009ca3b`
- `KERNEL32!GetLastError` at `0x18009ca5c`
- `ADVAPI32!RevertToSelf` at `0x18009c9ff`
- `ADVAPI32!RevertToSelf` at `0x18009ca22`
- `ADVAPI32!RevertToSelf` at `0x18009c9ff`
- `ADVAPI32!RevertToSelf` at `0x18009ca22`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18009c968`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18009c968`
- `WINHTTP!WinHttpSetCredentials` at `0x18009c9dd`
- `WINHTTP!WinHttpSetCredentials` at `0x18009c9dd`

## pseudocode

```c

```
