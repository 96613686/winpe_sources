# CHttpModule::OnMapPath(IHttpContext *,IMapPathProvider *)

- ea: `0x180002640`
- end: `0x180002678`
- name: `?OnMapPath@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapPathProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000264b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002658`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002665`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000264b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002658`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002665`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000266b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000266b`

## string_xrefs

- `0x180002651`: `CHttpModule::OnMapPath`

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
0x180002640  sub     rsp, 28h
0x180002644  lea     rcx, OutputString; "This module subscribed to event "
0x18000264b  call    cs:__imp_OutputDebugStringA
0x180002651  lea     rcx, aChttpmoduleOnm_0; "CHttpModule::OnMapPath"
0x180002658  call    cs:__imp_OutputDebugStringA
0x18000265e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180002665  call    cs:__imp_OutputDebugStringA
0x18000266b  call    cs:__imp_DebugBreak
0x180002671  xor     eax, eax
0x180002673  add     rsp, 28h
0x180002677  retn
```
