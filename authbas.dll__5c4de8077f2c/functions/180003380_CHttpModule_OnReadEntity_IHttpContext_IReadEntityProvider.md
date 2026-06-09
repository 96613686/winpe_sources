# CHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x180003380`
- end: `0x1800033b8`
- name: `?OnReadEntity@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000338b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003398`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800033a5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000338b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003398`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800033a5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800033ab`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800033ab`

## string_xrefs

- `0x180003391`: `CHttpModule::OnReadEntity`

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
0x180003380  sub     rsp, 28h
0x180003384  lea     rcx, OutputString; "This module subscribed to event "
0x18000338b  call    cs:__imp_OutputDebugStringA
0x180003391  lea     rcx, aChttpmoduleOnr_0; "CHttpModule::OnReadEntity"
0x180003398  call    cs:__imp_OutputDebugStringA
0x18000339e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800033a5  call    cs:__imp_OutputDebugStringA
0x1800033ab  call    cs:__imp_DebugBreak
0x1800033b1  xor     eax, eax
0x1800033b3  add     rsp, 28h
0x1800033b7  retn
```
