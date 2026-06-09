# CHttpModule::OnPostUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180003f50`
- end: `0x180003f88`
- name: `?OnPostUpdateRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180003f7b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180003f7b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003f5b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003f68`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003f75`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003f5b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003f68`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003f75`

## string_xrefs

- `0x180003f61`: `CHttpModule::OnPostUpdateRequestCache`

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
0x180003f50  sub     rsp, 28h
0x180003f54  lea     rcx, OutputString; "This module subscribed to event "
0x180003f5b  call    cs:__imp_OutputDebugStringA
0x180003f61  lea     rcx, aChttpmoduleOnp; "CHttpModule::OnPostUpdateRequestCache"
0x180003f68  call    cs:__imp_OutputDebugStringA
0x180003f6e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180003f75  call    cs:__imp_OutputDebugStringA
0x180003f7b  call    cs:__imp_DebugBreak
0x180003f81  xor     eax, eax
0x180003f83  add     rsp, 28h
0x180003f87  retn
```
