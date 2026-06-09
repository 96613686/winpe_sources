# WinHttpRequest::BeginSendRequest(void)

- ea: `0x180095164`
- end: `0x180095204`
- name: `?BeginSendRequest@WinHttpRequest@@AEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(DWORD_PTR dwContext)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18009507c`
- `0x18009545c`
- `0x18009c1a0`

## callees

- `0x18008aa28`
- `0x18008baec`
- `0x180095164`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095196`
- `WINHTTP!WinHttpSendRequest` at `0x18009518c`
- `WINHTTP!WinHttpSendRequest` at `0x18009518c`

## string_xrefs

- `0x1800951cc`: `EventWriteWinhttpSendFailureEvent`
- `0x1800951d3`: `Logger::WriteWinhttpSendFailureEvent`

## pseudocode

```c

```
