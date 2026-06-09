# SrSettings::CSrSettings::GetSetting(ushort const *,ushort const *,ushort const *,bool,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x180048ad8`
- end: `0x180048d7d`
- name: `?GetSetting@CSrSettings@SrSettings@@AEAAJPEBG00_NAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `677`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, const WCHAR *, const WCHAR *, char, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18004883c`
- `0x180048d84`

## callees

- `0x180006120`
- `0x180046b88`
- `0x180048ad8`
- `0x18004c0e8`
- `0x18004c564`
- `0x18004c6c8`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180048bad`
- `KERNEL32!GetLastError` at `0x180048bbb`
- `KERNEL32!GetLastError` at `0x180048c07`
- `KERNEL32!GetLastError` at `0x180048c29`
- `KERNEL32!GetLastError` at `0x180048c7c`
- `KERNEL32!GetLastError` at `0x180048cb9`
- `KERNEL32!GetLastError` at `0x180048cda`
- `KERNEL32!GetLastError` at `0x180048bad`
- `KERNEL32!GetLastError` at `0x180048bbb`
- `KERNEL32!GetLastError` at `0x180048c07`
- `KERNEL32!GetLastError` at `0x180048c29`
- `KERNEL32!GetLastError` at `0x180048c7c`
- `KERNEL32!GetLastError` at `0x180048cb9`
- `KERNEL32!GetLastError` at `0x180048cda`
- `KERNEL32!GetPrivateProfileStringW` at `0x180048b9f`
- `KERNEL32!GetPrivateProfileStringW` at `0x180048bf9`
- `KERNEL32!GetPrivateProfileStringW` at `0x180048b9f`
- `KERNEL32!GetPrivateProfileStringW` at `0x180048bf9`

## string_xrefs

- `0x180048b64`: `Test mode enabled. Check setting %s from test config file`
- `0x180048bc4`: `Failed to get setting %s from test config file. Error: %d`
- `0x180048ca1`: `Setting %s found in test config file`

## pseudocode

```c

```
