# Windows::WU::WuProvider::SetUserLocale(void)

- ea: `0x1402d88c4`
- end: `0x1402d8956`
- name: `?SetUserLocale@WuProvider@WU@Windows@@AEAAXXZ`
- size: `146`
- prototype: `void __fastcall(Windows::WU::WuProvider *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1402ceebc`
- `0x1402d2fd0`

## callees

- `0x14003c578`
- `0x140268574`
- `0x1402d88c4`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1402d8936`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1402d8936`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1402d8921`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1402d8921`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1402d88f0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1402d88f0`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x1402d88ff`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x1402d88ff`

## string_xrefs

- `0x1402d8943`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuProvider.cpp`

## pseudocode

```c

```
