# CHttpRequest::GetProxyInfoForUrl(ushort const *,ushort const *,bool,ushort * *,ushort * *,ulong *)

- ea: `0x1801f6f68`
- end: `0x1801f72ff`
- name: `?GetProxyInfoForUrl@CHttpRequest@@QEAAJPEBG0_NPEAPEAG2PEAK@Z`
- size: `919`
- prototype: `__int64 __fastcall(CHttpRequest *__hidden this, const unsigned __int16 *, const unsigned __int16 *, bool, unsigned __int16 **, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180076e48`

## callees

- `0x180009ea0`
- `0x1800111c8`
- `0x1800d963c`
- `0x1801f6f68`
- `0x1801f7308`
- `0x1801f73f8`
- `0x1801f7650`
- `0x1801f7900`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1801f72ab`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1801f72b6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1801f72c0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1801f72ca`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1801f72d4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1801f72ab`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1801f72b6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1801f72c0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1801f72ca`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1801f72d4`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x1801f703f`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x1801f703f`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x1801f7192`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x1801f7192`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1801f70a5`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1801f70a5`

## string_xrefs

- `0x1801f7143`: `slscr.update.microsoft.com`
- `0x1801f7002`: `ppszProxyList && ppszProxyByPass && pdwAccessType`
- `0x1801f727e`: `Proxy list = %s, Proxy bypass = %s, Proxy access type = %i`

## pseudocode

```c

```
