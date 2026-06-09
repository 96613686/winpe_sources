# StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,unsigned __int64,unsigned __int64 *)

- ea: `0x180104f40`
- end: `0x180104fb6`
- name: `?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_W_KPEA_K@Z`
- size: `118`
- prototype: `int __fastcall(HKEY *this, const WCHAR *, const wchar_t *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180105bbc`

## callees

- `0x180104f40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180104f7b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180104f7b`

## pseudocode

```c

```
