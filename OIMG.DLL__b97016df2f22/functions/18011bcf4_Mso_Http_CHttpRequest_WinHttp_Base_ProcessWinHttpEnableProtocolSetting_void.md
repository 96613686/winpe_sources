# Mso::Http::CHttpRequest_WinHttp_Base::ProcessWinHttpEnableProtocolSetting(void)

- ea: `0x18011bcf4`
- end: `0x18011c242`
- name: `?ProcessWinHttpEnableProtocolSetting@CHttpRequest_WinHttp_Base@Http@Mso@@IEAAXXZ`
- size: `1358`
- prototype: `void __fastcall(Mso::Http::CHttpRequest_WinHttp_Base *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1801206e8`

## callees

- `0x180012940`
- `0x180012aa0`
- `0x180013080`
- `0x180104648`
- `0x18011aa64`
- `0x18011bcf4`
- `0x18015c2ac`
- `0x18015c6cc`
- `0x18056bd00`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18011bdaf`
- `KERNEL32!GetLastError` at `0x18011bdaf`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011bf49`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011bfa6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011c006`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011c175`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011c1d6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011bf49`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011bfa6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011c006`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011c175`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011c1d6`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18011bfff`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18011c1cf`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18011bfff`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18011c1cf`
- `WINHTTP!WinHttpSetOption` at `0x18011bd98`
- `WINHTTP!WinHttpSetOption` at `0x18011c1ed`
- `WINHTTP!WinHttpSetOption` at `0x18011bd98`
- `WINHTTP!WinHttpSetOption` at `0x18011c1ed`

## string_xrefs

- `0x18011c040`: `WindowsEnabledHttpProtocol`
- `0x18011be19`: `DesiredHttpProtocol`
- `0x18011c123`: `Setting WINHTTP_OPTION_ENABLE_HTTP_PROTOCOL on the WinHttp request handle`
- `0x18011bef5`: `ProcessWinHttpEnableProtocolSetting() Setting the enabled Http protocol.`

## pseudocode

```c

```
