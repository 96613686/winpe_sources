# CStartupImpactHelper::GetCurrentUserSidStr(ushort * *)

- ea: `0x1800d9834`
- end: `0x1800d98bd`
- name: `?GetCurrentUserSidStr@CStartupImpactHelper@@AEAAJPEAPEAG@Z`
- size: `137`
- prototype: `int(CStartupImpactHelper *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800d9908`

## callees

- `0x1800cfd18`
- `0x1800d9834`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d989a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d989a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d98aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d98aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9874`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800d9866`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800d9866`

## pseudocode

```c

```
