# CHttpModule::OnAcquireRequestState(IHttpContext *,IHttpEventProvider *)

- ea: `0x1800022e0`
- end: `0x180002318`
- name: `?OnAcquireRequestState@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800022eb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800022f8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002305`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800022eb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800022f8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002305`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000230b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000230b`

## pseudocode

```c
__int64 CHttpModule::OnAcquireRequestState()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnAcquireRequestState");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x1800022e0  sub     rsp, 28h
0x1800022e4  lea     rcx, OutputString; "This module subscribed to event "
0x1800022eb  call    cs:__imp_OutputDebugStringA
0x1800022f1  lea     rcx, aChttpmoduleOna_0; "CHttpModule::OnAcquireRequestState"
0x1800022f8  call    cs:__imp_OutputDebugStringA
0x1800022fe  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180002305  call    cs:__imp_OutputDebugStringA
0x18000230b  call    cs:__imp_DebugBreak
0x180002311  xor     eax, eax
0x180002313  add     rsp, 28h
0x180002317  retn
```
