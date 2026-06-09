# CHttpModule::OnCustomRequestNotification(IHttpContext *,ICustomNotificationProvider *)

- ea: `0x1800024c0`
- end: `0x1800024f8`
- name: `?OnCustomRequestNotification@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVICustomNotificationProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800024cb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800024d8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800024e5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800024cb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800024d8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800024e5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800024eb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800024eb`

## pseudocode

```c
__int64 CHttpModule::OnCustomRequestNotification()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnCustomRequestNotification");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x1800024c0  sub     rsp, 28h
0x1800024c4  lea     rcx, OutputString; "This module subscribed to event "
0x1800024cb  call    cs:__imp_OutputDebugStringA
0x1800024d1  lea     rcx, aChttpmoduleOnc; "CHttpModule::OnCustomRequestNotificatio"...
0x1800024d8  call    cs:__imp_OutputDebugStringA
0x1800024de  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800024e5  call    cs:__imp_OutputDebugStringA
0x1800024eb  call    cs:__imp_DebugBreak
0x1800024f1  xor     eax, eax
0x1800024f3  add     rsp, 28h
0x1800024f7  retn
```
