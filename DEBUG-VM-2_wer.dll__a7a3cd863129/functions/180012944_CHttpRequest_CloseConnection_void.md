# CHttpRequest::CloseConnection(void)

- ea: `0x180012944`
- end: `0x1800129fe`
- name: `?CloseConnection@CHttpRequest@@IEAAXXZ`
- size: `186`
- prototype: `void __fastcall(CHttpRequest *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180039eb4`
- `0x18009a5f4`
- `0x18009b1e8`

## callees

- `0x180012944`
- `0x180012fe0`
- `0x18003e6d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012971`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012971`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800129e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800129e8`
- `WINHTTP!WinHttpCloseHandle` at `0x180012994`
- `WINHTTP!WinHttpCloseHandle` at `0x1800129af`
- `WINHTTP!WinHttpCloseHandle` at `0x180012994`
- `WINHTTP!WinHttpCloseHandle` at `0x1800129af`

## string_xrefs

- `0x1800129cc`: `CHttpRequest Waiting for WinHttp to complete`

## pseudocode

```c

```
