# StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,uint,uint *)

- ea: `0x180104ec4`
- end: `0x180104f37`
- name: `?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_WIPEAI@Z`
- size: `115`
- prototype: `int __fastcall(HKEY *this, const WCHAR *, const wchar_t *, _DWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801052a8`
- `0x18010551c`
- `0x180105bbc`

## callees

- `0x180104ec4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180104eff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180104eff`

## pseudocode

```c

```
