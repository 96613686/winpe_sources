# CHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x180003ff0`
- end: `0x180004028`
- name: `?OnReadEntity@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000401b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000401b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003ffb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180004008`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180004015`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003ffb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180004008`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180004015`

## string_xrefs

- `0x180004001`: `CHttpModule::OnReadEntity`

## pseudocode

```c
__int64 CHttpModule::OnReadEntity()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnReadEntity");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180003ff0  sub     rsp, 28h
0x180003ff4  lea     rcx, OutputString; "This module subscribed to event "
0x180003ffb  call    cs:__imp_OutputDebugStringA
0x180004001  lea     rcx, aChttpmoduleOnr_0; "CHttpModule::OnReadEntity"
0x180004008  call    cs:__imp_OutputDebugStringA
0x18000400e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180004015  call    cs:__imp_OutputDebugStringA
0x18000401b  call    cs:__imp_DebugBreak
0x180004021  xor     eax, eax
0x180004023  add     rsp, 28h
0x180004027  retn
```
