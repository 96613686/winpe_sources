# FindSessionIDFromUserSid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong &)

- ea: `0x18012b480`
- end: `0x18012b743`
- name: `?FindSessionIDFromUserSid@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAK@Z`
- size: `707`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x18012a874`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180013b44`
- `0x180014348`
- `0x1800143c8`
- `0x180018ac0`
- `0x180019d38`
- `0x18004a5d4`
- `0x18012b480`
- `0x18012b948`
- `0x18012c77c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18012b67a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18012b67a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b4f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b6dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b4f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b6dc`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemoryExW` at `0x18012b6d2`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemoryExW` at `0x18012b6d2`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsExW` at `0x18012b4ea`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsExW` at `0x18012b4ea`

## string_xrefs

- `0x18012b523`: `FindSessionIDFromUserSid - No sessions are active`
- `0x18012b631`: `FindSessionIDFromUserSid - GetStringSIDFromUsername() failed with hr = 0x%1!x!.`
- `0x18012b6e4`: `FindSessionIDFromUserSid - Failed to free memory : 0x%1!x!`
- `0x18012b6fb`: `FindSessionIDFromUserSid - Failed hr=0x%1!x!`
- `0x18012b50b`: `FindSessionIDFromUserSid - ::WTSEnumerateSessionsEx failed with error: 0x%1!x!`

## pseudocode

```c

```
