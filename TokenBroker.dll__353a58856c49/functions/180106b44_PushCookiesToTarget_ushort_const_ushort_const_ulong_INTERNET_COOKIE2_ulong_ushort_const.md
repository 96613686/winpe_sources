# PushCookiesToTarget(ushort const *,ushort const *,ulong,INTERNET_COOKIE2 *,ulong,ushort const *)

- ea: `0x180106b44`
- end: `0x180106d08`
- name: `?PushCookiesToTarget@@YAKPEBG0KPEAUINTERNET_COOKIE2@@K0@Z`
- size: `452`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, __int64, struct INTERNET_COOKIE2 *, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800d1980`

## callees

- `0x180024000`
- `0x1800349d0`
- `0x18008e690`
- `0x18009168c`
- `0x1801066e0`
- `0x180106728`
- `0x180106b44`
- `0x180106d10`
- `0x1801072f4`
- `0x18010769c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180106c60`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180106c60`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180106cac`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180106cac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106c48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106c48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180106cc5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180106ccf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180106cc5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180106ccf`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180106c3e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180106c3e`
- `ext-ms-win-security-tokenbrokerui-l1-1-0!TokenBrokerGetEdgeSids` at `0x180106c29`
- `ext-ms-win-security-tokenbrokerui-l1-1-0!TokenBrokerGetEdgeSids` at `0x180106c29`

## pseudocode

```c

```
