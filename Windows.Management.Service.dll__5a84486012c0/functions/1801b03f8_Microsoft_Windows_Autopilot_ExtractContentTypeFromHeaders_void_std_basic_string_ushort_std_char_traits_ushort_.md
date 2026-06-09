# Microsoft::Windows::Autopilot::ExtractContentTypeFromHeaders(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1801b03f8`
- end: `0x1801b05ea`
- name: `?ExtractContentTypeFromHeaders@Autopilot@Windows@Microsoft@@YAJPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `498`
- prototype: `__int64 __fastcall(HINTERNET hRequest)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1801b0b6c`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18007755c`
- `0x18008019c`
- `0x1800801fc`
- `0x18008c244`
- `0x1800fbc04`
- `0x1801b03f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b04a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b0560`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b04a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b0560`
- `WINHTTP!WinHttpQueryHeaders` at `0x1801b047a`
- `WINHTTP!WinHttpQueryHeaders` at `0x1801b0556`
- `WINHTTP!WinHttpQueryHeaders` at `0x1801b047a`
- `WINHTTP!WinHttpQueryHeaders` at `0x1801b0556`

## string_xrefs

- `0x1801b043a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`
- `0x1801b0491`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`
- `0x1801b04ff`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`
- `0x1801b0581`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\httpnetworkwrapper.cpp`

## pseudocode

```c

```
