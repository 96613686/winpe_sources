# CHttpModule::OnMapPath(IHttpContext *,IMapPathProvider *)

- ea: `0x180002970`
- end: `0x1800029a8`
- name: `?OnMapPath@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapPathProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000299b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000299b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000297b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002988`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002995`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000297b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002988`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002995`

## string_xrefs

- `0x180002981`: `CHttpModule::OnMapPath`

## pseudocode

```c
__int64 CHttpModule::OnMapPath()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnMapPath");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180002970  sub     rsp, 28h
0x180002974  lea     rcx, OutputString; "This module subscribed to event "
0x18000297b  call    cs:__imp_OutputDebugStringA
0x180002981  lea     rcx, aChttpmoduleOnm_0; "CHttpModule::OnMapPath"
0x180002988  call    cs:__imp_OutputDebugStringA
0x18000298e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180002995  call    cs:__imp_OutputDebugStringA
0x18000299b  call    cs:__imp_DebugBreak
0x1800029a1  xor     eax, eax
0x1800029a3  add     rsp, 28h
0x1800029a7  retn
```
