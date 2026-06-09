# CHttpModule::OnResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180002e90`
- end: `0x180002ec8`
- name: `?OnResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002ebb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002ebb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002e9b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002ea8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002eb5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002e9b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002ea8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002eb5`

## string_xrefs

- `0x180002ea1`: `CHttpModule::OnResolveRequestCache`

## pseudocode

```c
__int64 CHttpModule::OnResolveRequestCache()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnResolveRequestCache");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180002e90  sub     rsp, 28h
0x180002e94  lea     rcx, OutputString; "This module subscribed to event "
0x180002e9b  call    cs:__imp_OutputDebugStringA
0x180002ea1  lea     rcx, aChttpmoduleOnr_1; "CHttpModule::OnResolveRequestCache"
0x180002ea8  call    cs:__imp_OutputDebugStringA
0x180002eae  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180002eb5  call    cs:__imp_OutputDebugStringA
0x180002ebb  call    cs:__imp_DebugBreak
0x180002ec1  xor     eax, eax
0x180002ec3  add     rsp, 28h
0x180002ec7  retn
```
