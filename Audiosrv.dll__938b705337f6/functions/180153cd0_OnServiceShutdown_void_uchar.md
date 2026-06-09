# OnServiceShutdown(void *,uchar)

- ea: `0x180153cd0`
- end: `0x180153dec`
- name: `?OnServiceShutdown@@YAXPEAXE@Z`
- size: `284`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180153cd0`
- `0x1801540f0`
- `0x180154600`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180153cea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180153da4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180153cea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180153da4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180153d87`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180153d87`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180153d15`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180153d15`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180153d47`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180153d47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180153cf7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180153d75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180153dad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180153dc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180153cf7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180153d75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180153dad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180153dc4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180153d63`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180153d63`

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
0x180153cd0  push    rbx
0x180153cd2  sub     rsp, 30h
0x180153cd6  mov     rcx, cs:?hServiceStartThread@@3PEAXEA; hHandle
0x180153cdd  lea     rax, [rcx-1]
0x180153ce1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180153ce5  ja      short loc_180153D08
0x180153ce7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180153cea  call    cs:__imp_WaitForSingleObject
0x180153cf0  mov     rcx, cs:?hServiceStartThread@@3PEAXEA; hObject
0x180153cf7  call    cs:__imp_CloseHandle
0x180153cfd  mov     cs:?hServiceStartThread@@3PEAXEA, 0; void * hServiceStartThread
0x180153d08  xor     ebx, ebx
0x180153d0a  xor     r9d, r9d; lpName
0x180153d0d  xor     r8d, r8d; bInitialState
0x180153d10  xor     ecx, ecx; lpEventAttributes
0x180153d12  lea     edx, [rbx+1]; bManualReset
0x180153d15  call    cs:__imp_CreateEventW
0x180153d1b  mov     cs:?hEventShutdownComplete@@3PEAXEA, rax; void * hEventShutdownComplete
0x180153d22  test    rax, rax
0x180153d25  jz      short loc_180153D50
0x180153d27  lea     rax, [rsp+38h+ThreadId]
0x180153d2c  mov     [rsp+38h+ThreadId], ebx
0x180153d30  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180153d35  lea     r8, ?ShutdownKeepaliveThread@@YAKPEAX@Z; lpStartAddress
0x180153d3c  xor     r9d, r9d; lpParameter
0x180153d3f  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x180153d43  xor     edx, edx; dwStackSize
0x180153d45  xor     ecx, ecx; lpThreadAttributes
0x180153d47  call    cs:__imp_CreateThread
0x180153d4d  mov     rbx, rax
0x180153d50  call    ?MyServiceTerminate@@YAXXZ; MyServiceTerminate(void)
0x180153d55  mov     rcx, cs:?hEventShutdownWait@@3PEAXEA; WaitHandle
0x180153d5c  test    rcx, rcx
0x180153d5f  jz      short loc_180153D69
0x180153d61  xor     edx, edx; CompletionEvent
0x180153d63  call    cs:__imp_UnregisterWaitEx
0x180153d69  mov     rcx, cs:?hEventShutdown@@3PEAXEA; hObject
0x180153d70  test    rcx, rcx
0x180153d73  jz      short loc_180153D7B
0x180153d75  call    cs:__imp_CloseHandle
0x180153d7b  mov     rcx, cs:?hEventShutdownComplete@@3PEAXEA; hEvent
0x180153d82  test    rcx, rcx
0x180153d85  jz      short loc_180153D94
0x180153d87  call    cs:__imp_SetEvent
0x180153d8d  mov     rcx, cs:?hEventShutdownComplete@@3PEAXEA; void * hEventShutdownComplete
0x180153d94  lea     rax, [rbx-1]
0x180153d98  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180153d9c  ja      short loc_180153DBA
0x180153d9e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180153da1  mov     rcx, rbx; hHandle
0x180153da4  call    cs:__imp_WaitForSingleObject
0x180153daa  mov     rcx, rbx; hObject
0x180153dad  call    cs:__imp_CloseHandle
0x180153db3  mov     rcx, cs:?hEventShutdownComplete@@3PEAXEA; hObject
0x180153dba  lea     rax, [rcx-1]
0x180153dbe  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180153dc2  ja      short loc_180153DD5
0x180153dc4  call    cs:__imp_CloseHandle
0x180153dca  mov     cs:?hEventShutdownComplete@@3PEAXEA, 0; void * hEventShutdownComplete
0x180153dd5  mov     edx, cs:?dwServiceError@@3KA; ulong dwServiceError
0x180153ddb  xor     r8d, r8d
0x180153dde  lea     ecx, [r8+1]
0x180153de2  add     rsp, 30h
0x180153de6  pop     rbx
0x180153de7  jmp     ReportStatusToSCMgr
```
