# CHttpModule::OnExecuteRequestHandler(IHttpContext *,IHttpEventProvider *)

- ea: `0x180002580`
- end: `0x1800025b8`
- name: `?OnExecuteRequestHandler@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000258b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002598`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800025a5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000258b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002598`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800025a5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800025ab`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800025ab`

## pseudocode

```c
__int64 CHttpModule::OnExecuteRequestHandler()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnExecuteRequestHandler");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180002580  sub     rsp, 28h
0x180002584  lea     rcx, OutputString; "This module subscribed to event "
0x18000258b  call    cs:__imp_OutputDebugStringA
0x180002591  lea     rcx, aChttpmoduleOne; "CHttpModule::OnExecuteRequestHandler"
0x180002598  call    cs:__imp_OutputDebugStringA
0x18000259e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800025a5  call    cs:__imp_OutputDebugStringA
0x1800025ab  call    cs:__imp_DebugBreak
0x1800025b1  xor     eax, eax
0x1800025b3  add     rsp, 28h
0x1800025b7  retn
```
