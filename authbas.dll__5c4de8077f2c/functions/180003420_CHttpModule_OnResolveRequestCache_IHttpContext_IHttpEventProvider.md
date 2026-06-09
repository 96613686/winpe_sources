# CHttpModule::OnResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180003420`
- end: `0x180003458`
- name: `?OnResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000342b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003438`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003445`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000342b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003438`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003445`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000344b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000344b`

## string_xrefs

- `0x180003431`: `CHttpModule::OnResolveRequestCache`

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
0x180003420  sub     rsp, 28h
0x180003424  lea     rcx, OutputString; "This module subscribed to event "
0x18000342b  call    cs:__imp_OutputDebugStringA
0x180003431  lea     rcx, aChttpmoduleOnr_1; "CHttpModule::OnResolveRequestCache"
0x180003438  call    cs:__imp_OutputDebugStringA
0x18000343e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180003445  call    cs:__imp_OutputDebugStringA
0x18000344b  call    cs:__imp_DebugBreak
0x180003451  xor     eax, eax
0x180003453  add     rsp, 28h
0x180003457  retn
```
