# CHttpModule::OnUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180003ee0`
- end: `0x180003f18`
- name: `?OnUpdateRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180003f0b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180003f0b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003eeb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003ef8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003f05`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003eeb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003ef8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003f05`

## string_xrefs

- `0x180003ef1`: `CHttpModule::OnUpdateRequestCache`

## pseudocode

```c
__int64 CHttpModule::OnUpdateRequestCache()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnUpdateRequestCache");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180003ee0  sub     rsp, 28h
0x180003ee4  lea     rcx, OutputString; "This module subscribed to event "
0x180003eeb  call    cs:__imp_OutputDebugStringA
0x180003ef1  lea     rcx, aChttpmoduleOnu; "CHttpModule::OnUpdateRequestCache"
0x180003ef8  call    cs:__imp_OutputDebugStringA
0x180003efe  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180003f05  call    cs:__imp_OutputDebugStringA
0x180003f0b  call    cs:__imp_DebugBreak
0x180003f11  xor     eax, eax
0x180003f13  add     rsp, 28h
0x180003f17  retn
```
