# ATL::CSecurityDescriptor::GetPrincipalSID(wchar_t const *,void * *)

- ea: `0x140020cbc`
- end: `0x140020e46`
- name: `?GetPrincipalSID@CSecurityDescriptor@ATL@@SAJPEB_WPEAPEAX@Z`
- size: `394`
- prototype: `__int64 __fastcall(LPCWSTR lpAccountName, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001d34c`

## callees

- `0x140003448`
- `0x1400034d4`
- `0x14001d4e8`
- `0x14001d50c`
- `0x140020cbc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140020e0d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140020e0d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140020dbb`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140020dbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020d5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020d5f`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x140020d59`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x140020df5`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x140020d59`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x140020df5`

## pseudocode

```c

```
