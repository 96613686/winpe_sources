# StateRepository::Security::CreateDefaultAccountSid(void *,ulong)

- ea: `0x1800665a4`
- end: `0x1800666ff`
- name: `?CreateDefaultAccountSid@Security@StateRepository@@YAJPEAXK@Z`
- size: `347`
- prototype: `__int64 __fastcall(StateRepository::Security *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800662b8`

## callees

- `0x1800665a4`
- `0x1800a021c`
- `0x1800a5970`
- `0x1800bd0ac`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180066687`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180066687`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x180066623`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x180066623`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x1800665e5`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x1800665e5`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x180066658`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800666b9`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800666dd`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x180066658`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800666b9`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800666dd`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x180066667`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x1800666ec`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x180066667`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x1800666ec`

## string_xrefs

- `0x1800665f3`: `onecore\base\appmodel\StateRepository\Common\Inc\Security.hpp`
- `0x180066631`: `onecore\base\appmodel\StateRepository\Common\Inc\Security.hpp`
- `0x180066695`: `onecore\base\appmodel\StateRepository\Common\Inc\Security.hpp`

## pseudocode

```c

```
