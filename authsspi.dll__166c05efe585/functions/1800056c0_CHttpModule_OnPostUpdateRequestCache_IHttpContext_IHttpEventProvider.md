# CHttpModule::OnPostUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x1800056c0`
- end: `0x1800056f8`
- name: `?OnPostUpdateRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800056cb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800056d8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800056e5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800056cb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800056d8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800056e5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800056eb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800056eb`

## string_xrefs

- `0x1800056d1`: `CHttpModule::OnPostUpdateRequestCache`

## pseudocode

```c
__int64 CHttpModule::OnPostUpdateRequestCache()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnPostUpdateRequestCache");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x1800056c0  sub     rsp, 28h
0x1800056c4  lea     rcx, OutputString; "This module subscribed to event "
0x1800056cb  call    cs:__imp_OutputDebugStringA
0x1800056d1  lea     rcx, aChttpmoduleOnp; "CHttpModule::OnPostUpdateRequestCache"
0x1800056d8  call    cs:__imp_OutputDebugStringA
0x1800056de  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800056e5  call    cs:__imp_OutputDebugStringA
0x1800056eb  call    cs:__imp_DebugBreak
0x1800056f1  xor     eax, eax
0x1800056f3  add     rsp, 28h
0x1800056f7  retn
```
