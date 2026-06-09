# Microsoft::Diagnostics::Utils::Os::IsPersonalizationAllowedByPolicyForUser(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)

- ea: `0x1801976ac`
- end: `0x18019792e`
- name: `?IsPersonalizationAllowedByPolicyForUser@Os@Utils@Diagnostics@Microsoft@@SA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `642`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180197934`
- `0x180197ad8`
- `0x180197d30`

## callees

- `0x180020798`
- `0x18008a4ec`
- `0x1800e99a0`
- `0x1800fa378`
- `0x180142fcc`
- `0x1801976ac`
- `0x1801c2d0c`
- `0x18020cbd4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180197812`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801978c1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801978e1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180197812`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801978c1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801978e1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1801976c3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1801976c3`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_IsPolicySetByMobileDeviceManager` at `0x18019770e`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_IsPolicySetByMobileDeviceManager` at `0x18019770e`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18019779c`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18019779c`

## pseudocode

```c

```
