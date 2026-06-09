# OnServiceShutdown(void *,uchar)

- ea: `0x18005cca0`
- end: `0x18005cdbc`
- name: `?OnServiceShutdown@@YAXPEAXE@Z`
- size: `284`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18005cca0`
- `0x18005d0c0`
- `0x18005d4cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005cce5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005cce5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005ccba`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005cd74`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005ccba`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005cd74`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005cd57`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005cd57`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005cd17`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005cd17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ccc7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cd45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cd7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cd94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ccc7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cd45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cd7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cd94`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18005cd33`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18005cd33`

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
0x18005cca0  push    rbx
0x18005cca2  sub     rsp, 30h
0x18005cca6  mov     rcx, cs:?hServiceStartThread@@3PEAXEA; hHandle
0x18005ccad  lea     rax, [rcx-1]
0x18005ccb1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005ccb5  ja      short loc_18005CCD8
0x18005ccb7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18005ccba  call    cs:__imp_WaitForSingleObject
0x18005ccc0  mov     rcx, cs:?hServiceStartThread@@3PEAXEA; hObject
0x18005ccc7  call    cs:__imp_CloseHandle
0x18005cccd  mov     cs:?hServiceStartThread@@3PEAXEA, 0; void * hServiceStartThread
0x18005ccd8  xor     ebx, ebx
0x18005ccda  xor     r9d, r9d; lpName
0x18005ccdd  xor     r8d, r8d; bInitialState
0x18005cce0  xor     ecx, ecx; lpEventAttributes
0x18005cce2  lea     edx, [rbx+1]; bManualReset
0x18005cce5  call    cs:__imp_CreateEventW
0x18005cceb  mov     cs:?hEventShutdownComplete@@3PEAXEA, rax; void * hEventShutdownComplete
0x18005ccf2  test    rax, rax
0x18005ccf5  jz      short loc_18005CD20
0x18005ccf7  lea     rax, [rsp+38h+ThreadId]
0x18005ccfc  mov     [rsp+38h+ThreadId], ebx
0x18005cd00  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18005cd05  lea     r8, ?ShutdownKeepaliveThread@@YAKPEAX@Z; lpStartAddress
0x18005cd0c  xor     r9d, r9d; lpParameter
0x18005cd0f  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x18005cd13  xor     edx, edx; dwStackSize
0x18005cd15  xor     ecx, ecx; lpThreadAttributes
0x18005cd17  call    cs:__imp_CreateThread
0x18005cd1d  mov     rbx, rax
0x18005cd20  call    ?MyServiceTerminate@@YAXXZ; MyServiceTerminate(void)
0x18005cd25  mov     rcx, cs:?hEventShutdownWait@@3PEAXEA; WaitHandle
0x18005cd2c  test    rcx, rcx
0x18005cd2f  jz      short loc_18005CD39
0x18005cd31  xor     edx, edx; CompletionEvent
0x18005cd33  call    cs:__imp_UnregisterWaitEx
0x18005cd39  mov     rcx, cs:?hEventShutdown@@3PEAXEA; hObject
0x18005cd40  test    rcx, rcx
0x18005cd43  jz      short loc_18005CD4B
0x18005cd45  call    cs:__imp_CloseHandle
0x18005cd4b  mov     rcx, cs:?hEventShutdownComplete@@3PEAXEA; hEvent
0x18005cd52  test    rcx, rcx
0x18005cd55  jz      short loc_18005CD64
0x18005cd57  call    cs:__imp_SetEvent
0x18005cd5d  mov     rcx, cs:?hEventShutdownComplete@@3PEAXEA; void * hEventShutdownComplete
0x18005cd64  lea     rax, [rbx-1]
0x18005cd68  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005cd6c  ja      short loc_18005CD8A
0x18005cd6e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18005cd71  mov     rcx, rbx; hHandle
0x18005cd74  call    cs:__imp_WaitForSingleObject
0x18005cd7a  mov     rcx, rbx; hObject
0x18005cd7d  call    cs:__imp_CloseHandle
0x18005cd83  mov     rcx, cs:?hEventShutdownComplete@@3PEAXEA; hObject
0x18005cd8a  lea     rax, [rcx-1]
0x18005cd8e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005cd92  ja      short loc_18005CDA5
0x18005cd94  call    cs:__imp_CloseHandle
0x18005cd9a  mov     cs:?hEventShutdownComplete@@3PEAXEA, 0; void * hEventShutdownComplete
0x18005cda5  mov     edx, cs:?dwServiceError@@3KA; ulong dwServiceError
0x18005cdab  xor     r8d, r8d
0x18005cdae  lea     ecx, [r8+1]
0x18005cdb2  add     rsp, 30h
0x18005cdb6  pop     rbx
0x18005cdb7  jmp     ReportStatusToSCMgr
```
