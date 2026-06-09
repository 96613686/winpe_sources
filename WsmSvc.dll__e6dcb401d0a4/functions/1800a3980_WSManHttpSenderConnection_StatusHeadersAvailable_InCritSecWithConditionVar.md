# WSManHttpSenderConnection::StatusHeadersAvailable(InCritSecWithConditionVar *)

- ea: `0x1800a3980`
- end: `0x1800a4ed7`
- name: `?StatusHeadersAvailable@WSManHttpSenderConnection@@AEAAXPEAVInCritSecWithConditionVar@@@Z`
- size: `5463`
- prototype: `void __fastcall(WSManHttpSenderConnection *__hidden this, struct InCritSecWithConditionVar *)`
- caller_count: `1`
- callee_count: `40`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800521b0`

## callees

- `0x180005d10`
- `0x180019950`
- `0x180026908`
- `0x1800520d0`
- `0x180053ccc`
- `0x180053ea8`
- `0x180054068`
- `0x180054494`
- `0x18005c09c`
- `0x18005d800`
- `0x1800621e0`
- `0x180062620`
- `0x180064250`
- `0x1800654b4`
- `0x180067a38`
- `0x18007e530`
- `0x18007ec20`
- `0x180080288`
- `0x1800a3980`
- `0x1800a4ee0`
- `0x1800c2910`
- `0x1800e43f4`
- `0x1800eccb0`
- `0x1800fd62c`
- `0x180101b7c`
- `0x180111270`
- `0x180112380`
- `0x1801123a8`
- `0x180112460`
- `0x1801133b0`
- `0x18011349c`
- `0x18011a6d4`
- `0x18011ae5c`
- `0x180123fa0`
- `0x1801296dc`
- `0x180131b08`
- `0x180133be4`
- `0x1801ba152`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_scprintf` at `0x1800a3cc9`
- `msvcrt!_scprintf` at `0x1800a3cc9`
- `msvcrt!_strnicmp` at `0x1800a3b76`
- `msvcrt!_strnicmp` at `0x1800a3b76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a3ac1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a3d7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a3ac1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a3d7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3a3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3df9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a451f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a461e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3a3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3df9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a451f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a461e`
- `ntdll!EtwEventEnabled` at `0x1800a3ab3`
- `ntdll!EtwEventEnabled` at `0x1800a3ab3`
- `SspiCli!QueryContextAttributesW` at `0x1800a3ca8`
- `SspiCli!QueryContextAttributesW` at `0x1800a3ca8`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800a39ff`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800a3b25`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800a446b`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800a4515`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800a39ff`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800a3b25`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800a446b`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800a4515`
- `WINHTTP!WinHttpCrackUrl` at `0x1800a4614`
- `WINHTTP!WinHttpCrackUrl` at `0x1800a4614`

## string_xrefs

- `0x1800a3cc2`: `OriginalContent: type=application/soap+xml;charset=%s;Length=%lu\n`
- `0x1800a4ddf`: `503 (HTTP_STATUS_SERVICE_UNAVAIL)`
- `0x1800a4a21`: `The server response had authentication token and client failed to process it`

## pseudocode

```c

```
