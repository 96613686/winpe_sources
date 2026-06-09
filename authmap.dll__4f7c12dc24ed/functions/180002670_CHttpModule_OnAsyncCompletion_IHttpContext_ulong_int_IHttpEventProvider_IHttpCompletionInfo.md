# CHttpModule::OnAsyncCompletion(IHttpContext *,ulong,int,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x180002670`
- end: `0x1800026a8`
- name: `?OnAsyncCompletion@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@KHPEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000269b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000269b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000267b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002688`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002695`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000267b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002688`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002695`

## string_xrefs

- `0x180002681`: `CHttpModule::OnAsyncCompletion`

## pseudocode

```c
__int64 CHttpModule::OnAsyncCompletion()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnAsyncCompletion");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180002670  sub     rsp, 28h
0x180002674  lea     rcx, OutputString; "This module subscribed to event "
0x18000267b  call    cs:__imp_OutputDebugStringA
0x180002681  lea     rcx, aChttpmoduleOna_1; "CHttpModule::OnAsyncCompletion"
0x180002688  call    cs:__imp_OutputDebugStringA
0x18000268e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180002695  call    cs:__imp_OutputDebugStringA
0x18000269b  call    cs:__imp_DebugBreak
0x1800026a1  xor     eax, eax
0x1800026a3  add     rsp, 28h
0x1800026a7  retn
```
