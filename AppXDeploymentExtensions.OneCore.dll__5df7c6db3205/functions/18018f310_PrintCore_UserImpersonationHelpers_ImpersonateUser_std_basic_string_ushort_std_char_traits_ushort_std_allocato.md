# PrintCore::UserImpersonationHelpers::ImpersonateUser(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18018f310`
- end: `0x18018f51b`
- name: `?ImpersonateUser@UserImpersonationHelpers@PrintCore@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `523`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b143c`

## callees

- `0x18006cb78`
- `0x1800a6864`
- `0x1800a69f8`
- `0x1800b10c0`
- `0x1800baaac`
- `0x1800d3a40`
- `0x1800db3fc`
- `0x1800f0260`
- `0x18018f310`
- `0x18018f6f4`
- `0x18018f728`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18018f468`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18018f468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018f3ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018f3df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018f3ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018f3df`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18018f477`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18018f477`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18018f352`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18018f352`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18018f3c4`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18018f3c4`

## string_xrefs

- `0x18018f3f6`: `WTSQueryUserToken failed!`
- `0x18018f36f`: `OneCoreUap\Internal\Printscan\inc\userimpersonationhelpers.h`
- `0x18018f485`: `Failed to impersonate the user!`
- `0x18018f42c`: `Failed to get the SID attached to the token!`
- `0x18018f4df`: `Failed to find the user to impersonate!`

## pseudocode

```c

```
