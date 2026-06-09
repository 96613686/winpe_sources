# OnServiceShutdown(void *,uchar)

- ea: `0x1801549e0`
- end: `0x180154afc`
- name: `?OnServiceShutdown@@YAXPEAXE@Z`
- size: `284`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1801549e0`
- `0x180154e00`
- `0x180155310`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801549fa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180154ab4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801549fa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180154ab4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180154a97`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180154a97`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180154a25`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180154a25`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180154a57`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180154a57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180154a07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180154a85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180154abd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180154ad4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180154a07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180154a85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180154abd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180154ad4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180154a73`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180154a73`

## pseudocode

```c
void __fastcall OnServiceShutdown(void *a1)
{
  char *v1; // rbx
  char *v2; // rcx
  DWORD ThreadId; // [rsp+50h] [rbp+18h] BYREF

  if ( (char *)hServiceStartThread - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    WaitForSingleObject(hServiceStartThread, 0xFFFFFFFF);
    CloseHandle(hServiceStartThread);
    hServiceStartThread = 0;
  }
  v1 = 0;
  hEventShutdownComplete = CreateEventW(0, 1, 0, 0);
  if ( hEventShutdownComplete )
  {
    ThreadId = 0;
    v1 = (char *)CreateThread(0, 0, ShutdownKeepaliveThread, 0, 0, &ThreadId);
  }
  MyServiceTerminate();
  if ( hEventShutdownWait )
    UnregisterWaitEx(hEventShutdownWait, 0);
  if ( hEventShutdown )
    CloseHandle(hEventShutdown);
  v2 = (char *)hEventShutdownComplete;
  if ( hEventShutdownComplete )
  {
    SetEvent(hEventShutdownComplete);
    v2 = (char *)hEventShutdownComplete;
  }
  if ( (unsigned __int64)(v1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    WaitForSingleObject(v1, 0xFFFFFFFF);
    CloseHandle(v1);
    v2 = (char *)hEventShutdownComplete;
  }
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v2);
    hEventShutdownComplete = 0;
  }
  ReportStatusToSCMgr(1, dwServiceError, 0);
}

```

## disassembly

```asm
0x1801549e0  push    rbx
0x1801549e2  sub     rsp, 30h
0x1801549e6  mov     rcx, cs:?hServiceStartThread@@3PEAXEA; hHandle
0x1801549ed  lea     rax, [rcx-1]
0x1801549f1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801549f5  ja      short loc_180154A18
0x1801549f7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1801549fa  call    cs:__imp_WaitForSingleObject
0x180154a00  mov     rcx, cs:?hServiceStartThread@@3PEAXEA; hObject
0x180154a07  call    cs:__imp_CloseHandle
0x180154a0d  mov     cs:?hServiceStartThread@@3PEAXEA, 0; void * hServiceStartThread
0x180154a18  xor     ebx, ebx
0x180154a1a  xor     r9d, r9d; lpName
0x180154a1d  xor     r8d, r8d; bInitialState
0x180154a20  xor     ecx, ecx; lpEventAttributes
0x180154a22  lea     edx, [rbx+1]; bManualReset
0x180154a25  call    cs:__imp_CreateEventW
0x180154a2b  mov     cs:?hEventShutdownComplete@@3PEAXEA, rax; void * hEventShutdownComplete
0x180154a32  test    rax, rax
0x180154a35  jz      short loc_180154A60
0x180154a37  lea     rax, [rsp+38h+ThreadId]
0x180154a3c  mov     [rsp+38h+ThreadId], ebx
0x180154a40  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180154a45  lea     r8, ?ShutdownKeepaliveThread@@YAKPEAX@Z; lpStartAddress
0x180154a4c  xor     r9d, r9d; lpParameter
0x180154a4f  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x180154a53  xor     edx, edx; dwStackSize
0x180154a55  xor     ecx, ecx; lpThreadAttributes
0x180154a57  call    cs:__imp_CreateThread
0x180154a5d  mov     rbx, rax
0x180154a60  call    ?MyServiceTerminate@@YAXXZ; MyServiceTerminate(void)
0x180154a65  mov     rcx, cs:?hEventShutdownWait@@3PEAXEA; WaitHandle
0x180154a6c  test    rcx, rcx
0x180154a6f  jz      short loc_180154A79
0x180154a71  xor     edx, edx; CompletionEvent
0x180154a73  call    cs:__imp_UnregisterWaitEx
0x180154a79  mov     rcx, cs:?hEventShutdown@@3PEAXEA; hObject
0x180154a80  test    rcx, rcx
0x180154a83  jz      short loc_180154A8B
0x180154a85  call    cs:__imp_CloseHandle
0x180154a8b  mov     rcx, cs:?hEventShutdownComplete@@3PEAXEA; hEvent
0x180154a92  test    rcx, rcx
0x180154a95  jz      short loc_180154AA4
0x180154a97  call    cs:__imp_SetEvent
0x180154a9d  mov     rcx, cs:?hEventShutdownComplete@@3PEAXEA; void * hEventShutdownComplete
0x180154aa4  lea     rax, [rbx-1]
0x180154aa8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180154aac  ja      short loc_180154ACA
0x180154aae  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180154ab1  mov     rcx, rbx; hHandle
0x180154ab4  call    cs:__imp_WaitForSingleObject
0x180154aba  mov     rcx, rbx; hObject
0x180154abd  call    cs:__imp_CloseHandle
0x180154ac3  mov     rcx, cs:?hEventShutdownComplete@@3PEAXEA; hObject
0x180154aca  lea     rax, [rcx-1]
0x180154ace  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180154ad2  ja      short loc_180154AE5
0x180154ad4  call    cs:__imp_CloseHandle
0x180154ada  mov     cs:?hEventShutdownComplete@@3PEAXEA, 0; void * hEventShutdownComplete
0x180154ae5  mov     edx, cs:?dwServiceError@@3KA; ulong dwServiceError
0x180154aeb  xor     r8d, r8d
0x180154aee  lea     ecx, [r8+1]
0x180154af2  add     rsp, 30h
0x180154af6  pop     rbx
0x180154af7  jmp     ReportStatusToSCMgr
```
