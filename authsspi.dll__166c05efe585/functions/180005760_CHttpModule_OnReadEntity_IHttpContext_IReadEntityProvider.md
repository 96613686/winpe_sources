# CHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x180005760`
- end: `0x180005798`
- name: `?OnReadEntity@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000576b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180005778`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180005785`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000576b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180005778`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180005785`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000578b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000578b`

## string_xrefs

- `0x180005771`: `CHttpModule::OnReadEntity`

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
0x180005760  sub     rsp, 28h
0x180005764  lea     rcx, OutputString; "This module subscribed to event "
0x18000576b  call    cs:__imp_OutputDebugStringA
0x180005771  lea     rcx, aChttpmoduleOnr_0; "CHttpModule::OnReadEntity"
0x180005778  call    cs:__imp_OutputDebugStringA
0x18000577e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180005785  call    cs:__imp_OutputDebugStringA
0x18000578b  call    cs:__imp_DebugBreak
0x180005791  xor     eax, eax
0x180005793  add     rsp, 28h
0x180005797  retn
```
