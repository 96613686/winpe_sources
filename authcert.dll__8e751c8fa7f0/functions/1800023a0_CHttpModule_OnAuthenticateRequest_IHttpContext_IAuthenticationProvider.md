# CHttpModule::OnAuthenticateRequest(IHttpContext *,IAuthenticationProvider *)

- ea: `0x1800023a0`
- end: `0x1800023d8`
- name: `?OnAuthenticateRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIAuthenticationProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800023ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800023b8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800023c5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800023ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800023b8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800023c5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800023cb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800023cb`

## pseudocode

```c
__int64 CHttpModule::OnAuthenticateRequest()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnAuthenticateRequest");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x1800023a0  sub     rsp, 28h
0x1800023a4  lea     rcx, OutputString; "This module subscribed to event "
0x1800023ab  call    cs:__imp_OutputDebugStringA
0x1800023b1  lea     rcx, aChttpmoduleOna_2; "CHttpModule::OnAuthenticateRequest"
0x1800023b8  call    cs:__imp_OutputDebugStringA
0x1800023be  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800023c5  call    cs:__imp_OutputDebugStringA
0x1800023cb  call    cs:__imp_DebugBreak
0x1800023d1  xor     eax, eax
0x1800023d3  add     rsp, 28h
0x1800023d7  retn
```
