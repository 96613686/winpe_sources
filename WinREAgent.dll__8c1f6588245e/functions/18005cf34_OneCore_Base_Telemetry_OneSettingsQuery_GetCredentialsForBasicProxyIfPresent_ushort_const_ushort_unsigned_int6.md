# OneCore::Base::Telemetry::OneSettingsQuery::GetCredentialsForBasicProxyIfPresent(ushort const *,ushort *,unsigned __int64,ushort *,unsigned __int64)

- ea: `0x18005cf34`
- end: `0x18005d023`
- name: `?GetCredentialsForBasicProxyIfPresent@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBGPEAG_K12@Z`
- size: `239`
- prototype: `int(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18005d23c`

## callees

- `0x180012820`
- `0x18005cf34`
- `0x18006232c`

## import_xrefs

- `ADVAPI32!CredFree` at `0x18005d010`
- `ADVAPI32!CredFree` at `0x18005d010`
- `ADVAPI32!CredReadW` at `0x18005cf5d`
- `ADVAPI32!CredReadW` at `0x18005cf5d`
- `KERNEL32!GetLastError` at `0x18005cf67`
- `KERNEL32!GetLastError` at `0x18005cf67`

## pseudocode

```c

```
