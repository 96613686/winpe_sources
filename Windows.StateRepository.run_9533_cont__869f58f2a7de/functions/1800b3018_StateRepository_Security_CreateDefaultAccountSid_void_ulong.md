# StateRepository::Security::CreateDefaultAccountSid(void *,ulong)

- ea: `0x1800b3018`
- end: `0x1800b313c`
- name: `?CreateDefaultAccountSid@Security@StateRepository@@YAJPEAXK@Z`
- size: `292`
- prototype: `__int64 __fastcall(StateRepository::Security *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800b2ee0`

## callees

- `0x18000e8dc`
- `0x18000e91c`
- `0x1800b3018`
- `0x180202608`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800b30ec`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800b30ec`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800b30cc`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800b311e`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800b30cc`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800b311e`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x1800b3059`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x1800b3059`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x1800b3097`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x1800b3097`

## string_xrefs

- `0x1800b3067`: `onecore\base\appmodel\StateRepository\Common\Inc\Security.hpp`
- `0x1800b30a5`: `onecore\base\appmodel\StateRepository\Common\Inc\Security.hpp`
- `0x1800b30fa`: `onecore\base\appmodel\StateRepository\Common\Inc\Security.hpp`

## pseudocode

```c

```
