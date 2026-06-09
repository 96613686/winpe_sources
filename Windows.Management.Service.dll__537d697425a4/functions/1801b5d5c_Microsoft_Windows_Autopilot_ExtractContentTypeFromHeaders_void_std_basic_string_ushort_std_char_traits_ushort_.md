# Microsoft::Windows::Autopilot::ExtractContentTypeFromHeaders(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1801b5d5c`
- end: `0x1801b5f66`
- name: `?ExtractContentTypeFromHeaders@Autopilot@Windows@Microsoft@@YAJPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `522`
- prototype: `__int64 __fastcall(HINTERNET hRequest)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1801b6514`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x180077de0`
- `0x180080bac`
- `0x180080c10`
- `0x18008d290`
- `0x1800fecf4`
- `0x1801b5d5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b5e13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b5ed6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b5e13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b5ed6`
- `WINHTTP!WinHttpQueryHeaders` at `0x1801b5dde`
- `WINHTTP!WinHttpQueryHeaders` at `0x1801b5ec6`
- `WINHTTP!WinHttpQueryHeaders` at `0x1801b5dde`
- `WINHTTP!WinHttpQueryHeaders` at `0x1801b5ec6`

## string_xrefs

- `0x1801b5d9e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`
- `0x1801b5dfb`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`
- `0x1801b5e6f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`
- `0x1801b5efd`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`

## pseudocode

```c

```
