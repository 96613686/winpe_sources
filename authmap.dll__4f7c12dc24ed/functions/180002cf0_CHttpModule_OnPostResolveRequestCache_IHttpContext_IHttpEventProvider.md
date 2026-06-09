# CHttpModule::OnPostResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180002cf0`
- end: `0x180002d28`
- name: `?OnPostResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002d1b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002d1b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002cfb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002d08`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002d15`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002cfb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002d08`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002d15`

## string_xrefs

- `0x180002d01`: `CHttpModule::OnPostResolveRequestCache`

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
0x180002cf0  sub     rsp, 28h
0x180002cf4  lea     rcx, OutputString; "This module subscribed to event "
0x180002cfb  call    cs:__imp_OutputDebugStringA
0x180002d01  lea     rcx, aChttpmoduleOnp_0; "CHttpModule::OnPostResolveRequestCache"
0x180002d08  call    cs:__imp_OutputDebugStringA
0x180002d0e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180002d15  call    cs:__imp_OutputDebugStringA
0x180002d1b  call    cs:__imp_DebugBreak
0x180002d21  xor     eax, eax
0x180002d23  add     rsp, 28h
0x180002d27  retn
```
