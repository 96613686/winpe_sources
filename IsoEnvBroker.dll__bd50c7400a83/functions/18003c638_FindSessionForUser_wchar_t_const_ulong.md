# FindSessionForUser(wchar_t const *,ulong *)

- ea: `0x18003c638`
- end: `0x18003c794`
- name: `?FindSessionForUser@@YA_NPEB_WPEAK@Z`
- size: `348`
- prototype: `bool __fastcall(const wchar_t *, unsigned int *)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003d158`
- `0x180040d30`
- `0x1800414dc`
- `0x180049024`
- `0x180054804`
- `0x18005def4`
- `0x18005ef20`

## callees

- `0x1800075e4`
- `0x18003c638`
- `0x180068010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003c77b`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003c77b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c6fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c6fc`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18003c6f2`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18003c710`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18003c6f2`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18003c710`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18003c6d1`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18003c6d1`

## string_xrefs

- `0x18003c782`: `onecoreuap\windows\core\isoenvbroker\lib\common\UserAccountHelpers.h`

## pseudocode

```c

```
