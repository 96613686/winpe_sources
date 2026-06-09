# UmeLazyWriterWorker(void *)

- ea: `0x140086040`
- end: `0x140086143`
- name: `?UmeLazyWriterWorker@@YAKPEAX@Z`
- size: `259`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140086040`
- `0x1401b9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x140086068`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x140086068`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1400860c4`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1400860c4`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x140086093`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x140086093`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400860f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400860f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140086113`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140086129`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140086113`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140086129`

## pseudocode

```c
__int64 __fastcall UmeLazyWriterWorker(PVOID Parameter)
{
  DWORD LastError; // ebx
  HANDLE WaitableTimer; // rdi
  DWORD v3; // eax
  HANDLE Handles[3]; // [rsp+30h] [rbp-18h] BYREF
  LARGE_INTEGER DueTime; // [rsp+58h] [rbp+10h] BYREF

  DueTime.QuadPart = -40000000;
  LastError = 0;
  WaitableTimer = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
  SetWaitableTimer(WaitableTimer, &DueTime, 4000, 0, 0, 0);
  Handles[1] = CacheShutdownEvent;
  Handles[0] = WaitableTimer;
  while ( 1 )
  {
    v3 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
    if ( v3 )
      break;
    ((void (__fastcall *)(void *, void *))UmeExternalCacheCallbackEx)(UmeExternalCacheContext, &CacheDirtyPagesInfo);
  }
  if ( v3 == 1 )
  {
    UmeExternalCacheContext = 0;
    CloseHandle(CacheShutdownEvent);
    CacheShutdownEvent = 0;
  }
  else
  {
    LastError = GetLastError();
  }
  CloseHandle(WaitableTimer);
  return LastError;
}

```

## disassembly

```asm
0x140086040  mov     [rsp+arg_0], rbx
0x140086045  push    rdi
0x140086046  sub     rsp, 40h
0x14008604a  xorps   xmm0, xmm0
0x14008604d  mov     qword ptr [rsp+48h+DueTime], 0FFFFFFFFFD9DA600h
0x140086056  mov     r9d, 1F0003h; dwDesiredAccess
0x14008605c  xor     r8d, r8d; dwFlags
0x14008605f  xor     edx, edx; lpTimerName
0x140086061  xor     ecx, ecx; lpTimerAttributes
0x140086063  movups  xmmword ptr [rsp+48h+Handles], xmm0
0x140086068  call    cs:__imp_CreateWaitableTimerExW
0x14008606f  nop     dword ptr [rax+rax+00h]
0x140086074  xor     ebx, ebx
0x140086076  lea     rdx, [rsp+48h+DueTime]; lpDueTime
0x14008607b  mov     [rsp+48h+fResume], ebx; fResume
0x14008607f  mov     rcx, rax; hTimer
0x140086082  xor     r9d, r9d; pfnCompletionRoutine
0x140086085  mov     [rsp+48h+lpArgToCompletionRoutine], rbx; lpArgToCompletionRoutine
0x14008608a  mov     r8d, 0FA0h; lPeriod
0x140086090  mov     rdi, rax
0x140086093  call    cs:__imp_SetWaitableTimer
0x14008609a  nop     dword ptr [rax+rax+00h]
0x14008609f  mov     rcx, cs:?CacheShutdownEvent@@3PEAXEA; void * CacheShutdownEvent
0x1400860a6  mov     [rsp+48h+Handles+8], rcx
0x1400860ab  mov     [rsp+48h+Handles], rdi
0x1400860b0  xor     r8d, r8d; bWaitAll
0x1400860b3  mov     dword ptr [rsp+48h+lpArgToCompletionRoutine], ebx; bAlertable
0x1400860b7  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1400860bb  lea     rdx, [rsp+48h+Handles]; lpHandles
0x1400860c0  lea     ecx, [r8+2]; nCount
0x1400860c4  call    cs:__imp_WaitForMultipleObjectsEx
0x1400860cb  nop     dword ptr [rax+rax+00h]
0x1400860d0  test    eax, eax
0x1400860d2  jnz     short loc_1400860F0
0x1400860d4  mov     rcx, cs:?UmeExternalCacheContext@@3PEAXEA; void * UmeExternalCacheContext
0x1400860db  lea     rdx, ?CacheDirtyPagesInfo@@3U_CC_DIRTY_PAGES_INFO_COPY@@A; _CC_DIRTY_PAGES_INFO_COPY CacheDirtyPagesInfo
0x1400860e2  mov     rax, cs:?UmeExternalCacheCallbackEx@@3P6AXPEAXPEAU_CC_DIRTY_PAGES_INFO_COPY@@@ZEA; void (*UmeExternalCacheCallbackEx)(void *,_CC_DIRTY_PAGES_INFO_COPY *)
0x1400860e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400860ee  jmp     short loc_1400860B0
0x1400860f0  cmp     eax, 1
0x1400860f3  jz      short loc_140086105
0x1400860f5  call    cs:__imp_GetLastError
0x1400860fc  nop     dword ptr [rax+rax+00h]
0x140086101  mov     ebx, eax
0x140086103  jmp     short loc_140086126
0x140086105  mov     rcx, cs:?CacheShutdownEvent@@3PEAXEA; hObject
0x14008610c  mov     cs:?UmeExternalCacheContext@@3PEAXEA, rbx; void * UmeExternalCacheContext
0x140086113  call    cs:__imp_CloseHandle
0x14008611a  nop     dword ptr [rax+rax+00h]
0x14008611f  mov     cs:?CacheShutdownEvent@@3PEAXEA, rbx; void * CacheShutdownEvent
0x140086126  mov     rcx, rdi; hObject
0x140086129  call    cs:__imp_CloseHandle
0x140086130  nop     dword ptr [rax+rax+00h]
0x140086135  mov     eax, ebx
0x140086137  mov     rbx, [rsp+48h+arg_0]
0x14008613c  add     rsp, 40h
0x140086140  pop     rdi
0x140086141  retn
```
