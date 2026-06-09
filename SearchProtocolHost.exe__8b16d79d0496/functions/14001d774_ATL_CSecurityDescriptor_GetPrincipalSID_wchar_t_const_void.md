# ATL::CSecurityDescriptor::GetPrincipalSID(wchar_t const *,void * *)

- ea: `0x14001d774`
- end: `0x14001d8fe`
- name: `?GetPrincipalSID@CSecurityDescriptor@ATL@@SAJPEB_WPEAPEAX@Z`
- size: `394`
- prototype: `__int64 __fastcall(LPCWSTR lpAccountName, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003a8e8`

## callees

- `0x140005264`
- `0x140005918`
- `0x1400124cc`
- `0x1400124f0`
- `0x14001d774`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001d8c5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001d8c5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14001d873`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14001d873`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d817`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d817`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x14001d811`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x14001d8ad`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x14001d811`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x14001d8ad`

## pseudocode

```c

```
