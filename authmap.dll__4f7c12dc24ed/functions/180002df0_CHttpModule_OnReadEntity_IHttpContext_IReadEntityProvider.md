# CHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x180002df0`
- end: `0x180002e28`
- name: `?OnReadEntity@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002e1b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002e1b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002dfb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002e08`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002e15`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002dfb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002e08`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002e15`

## string_xrefs

- `0x180002e01`: `CHttpModule::OnReadEntity`

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
0x180002df0  sub     rsp, 28h
0x180002df4  lea     rcx, OutputString; "This module subscribed to event "
0x180002dfb  call    cs:__imp_OutputDebugStringA
0x180002e01  lea     rcx, aChttpmoduleOnr_0; "CHttpModule::OnReadEntity"
0x180002e08  call    cs:__imp_OutputDebugStringA
0x180002e0e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180002e15  call    cs:__imp_OutputDebugStringA
0x180002e1b  call    cs:__imp_DebugBreak
0x180002e21  xor     eax, eax
0x180002e23  add     rsp, 28h
0x180002e27  retn
```
