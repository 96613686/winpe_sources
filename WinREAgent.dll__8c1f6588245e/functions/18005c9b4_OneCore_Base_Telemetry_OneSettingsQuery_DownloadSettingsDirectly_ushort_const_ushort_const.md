# OneCore::Base::Telemetry::OneSettingsQuery::DownloadSettingsDirectly(ushort const *,ushort const *)

- ea: `0x18005c9b4`
- end: `0x18005cb73`
- name: `?DownloadSettingsDirectly@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG0@Z`
- size: `447`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18005fd5c`

## callees

- `0x18005c9b4`
- `0x18005cd64`
- `0x18005f290`
- `0x18005f5cc`
- `0x18006136c`
- `0x18006c690`

## import_xrefs

- `ADVAPI32!RevertToSelf` at `0x18005cadf`
- `ADVAPI32!RevertToSelf` at `0x18005cb02`
- `ADVAPI32!RevertToSelf` at `0x18005cadf`
- `ADVAPI32!RevertToSelf` at `0x18005cb02`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18005ca4e`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18005ca4e`
- `KERNEL32!GetLastError` at `0x18005cb0c`
- `KERNEL32!GetLastError` at `0x18005cb1b`
- `KERNEL32!GetLastError` at `0x18005cb3c`
- `KERNEL32!GetLastError` at `0x18005cb0c`
- `KERNEL32!GetLastError` at `0x18005cb1b`
- `KERNEL32!GetLastError` at `0x18005cb3c`
- `KERNEL32!ExitProcess` at `0x18005cb14`
- `KERNEL32!ExitProcess` at `0x18005cb44`
- `KERNEL32!ExitProcess` at `0x18005cb14`
- `KERNEL32!ExitProcess` at `0x18005cb44`
- `WINHTTP!WinHttpSetCredentials` at `0x18005cac0`
- `WINHTTP!WinHttpSetCredentials` at `0x18005cac0`

## pseudocode

```c

```
