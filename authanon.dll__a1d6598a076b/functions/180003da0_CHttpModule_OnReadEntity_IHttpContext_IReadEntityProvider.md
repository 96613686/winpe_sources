# CHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x180003da0`
- end: `0x180003dd8`
- name: `?OnReadEntity@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180003dcb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180003dcb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003dab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003db8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003dc5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003dab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003db8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003dc5`

## string_xrefs

- `0x180003db1`: `CHttpModule::OnReadEntity`

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
0x180003da0  sub     rsp, 28h
0x180003da4  lea     rcx, OutputString; "This module subscribed to event "
0x180003dab  call    cs:__imp_OutputDebugStringA
0x180003db1  lea     rcx, aChttpmoduleOnr_0; "CHttpModule::OnReadEntity"
0x180003db8  call    cs:__imp_OutputDebugStringA
0x180003dbe  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180003dc5  call    cs:__imp_OutputDebugStringA
0x180003dcb  call    cs:__imp_DebugBreak
0x180003dd1  xor     eax, eax
0x180003dd3  add     rsp, 28h
0x180003dd7  retn
```
