# ConvertUserNameToSid

- ea: `0x1400735ec`
- end: `0x14007384d`
- name: `ConvertUserNameToSid`
- size: `609`
- prototype: `__int64 __fastcall(LPCWSTR lpAccountName)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14000d628`
- `0x14000d91c`
- `0x14000f170`
- `0x14000fab0`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x1400698ec`
- `0x14006998c`
- `0x1400735ec`

## import_xrefs

- `ADVAPI32!LookupAccountNameW` at `0x140073691`
- `ADVAPI32!LookupAccountNameW` at `0x1400737c8`
- `ADVAPI32!LookupAccountNameW` at `0x140073691`
- `ADVAPI32!LookupAccountNameW` at `0x1400737c8`
- `KERNEL32!GetLastError` at `0x1400736a1`
- `KERNEL32!GetLastError` at `0x140073707`
- `KERNEL32!GetLastError` at `0x1400737d8`
- `KERNEL32!GetLastError` at `0x1400736a1`
- `KERNEL32!GetLastError` at `0x140073707`
- `KERNEL32!GetLastError` at `0x1400737d8`

## pseudocode

```c

```
