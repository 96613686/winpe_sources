# GetSessionString(ulong,_WTS_INFO_CLASS,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1800600dc`
- end: `0x180060195`
- name: `?GetSessionString@@YAJKW4_WTS_INFO_CLASS@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `185`
- prototype: `__int64 __fastcall(DWORD SessionId, WTS_INFO_CLASS WTSInfoClass)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180060ed8`

## callees

- `0x1800050cd`
- `0x18000a444`
- `0x180010148`
- `0x1800600dc`

## import_xrefs

- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18006017d`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18006017d`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18006010c`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18006010c`

## string_xrefs

- `0x18006011b`: `onecoreuap\windows\core\isoenvbroker\lib\common\isoenvbrokersvc.cpp`

## pseudocode

```c

```
