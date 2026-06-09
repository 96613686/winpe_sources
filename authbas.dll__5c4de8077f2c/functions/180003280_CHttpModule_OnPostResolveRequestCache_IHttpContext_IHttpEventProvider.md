# CHttpModule::OnPostResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180003280`
- end: `0x1800032b8`
- name: `?OnPostResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000328b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003298`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800032a5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000328b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003298`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800032a5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800032ab`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800032ab`

## string_xrefs

- `0x180003291`: `CHttpModule::OnPostResolveRequestCache`

## pseudocode

```c
__int64 CHttpModule::OnPostResolveRequestCache()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnPostResolveRequestCache");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180003280  sub     rsp, 28h
0x180003284  lea     rcx, OutputString; "This module subscribed to event "
0x18000328b  call    cs:__imp_OutputDebugStringA
0x180003291  lea     rcx, aChttpmoduleOnp_0; "CHttpModule::OnPostResolveRequestCache"
0x180003298  call    cs:__imp_OutputDebugStringA
0x18000329e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800032a5  call    cs:__imp_OutputDebugStringA
0x1800032ab  call    cs:__imp_DebugBreak
0x1800032b1  xor     eax, eax
0x1800032b3  add     rsp, 28h
0x1800032b7  retn
```
