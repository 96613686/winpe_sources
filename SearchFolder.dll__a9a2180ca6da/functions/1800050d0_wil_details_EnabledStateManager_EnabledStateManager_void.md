# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800050d0`
- end: `0x18000520d`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `317`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180050b60`

## callees

- `0x1800042d0`
- `0x1800050d0`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800051ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800051cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800051ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800051cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000519d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800051be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000519d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800051be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000511b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000511b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005113`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800051fd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005113`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800051fd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800050fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800051e6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800050fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800051e6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000510a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800051f4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000510a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800051f4`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::~EnabledStateManager(wil::details::EnabledStateManager *this)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx
  void (*v4)(void); // rax
  __int64 v5; // rdx
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  void *v8; // rbx
  HANDLE v9; // rax
  struct _TP_TIMER *v10; // rbx

  *(_DWORD *)this = 0;
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 2) = 0;
  wil::details::EnabledStateManager::ProcessShutdown(this);
  if ( !*((_QWORD *)this + 13) )
  {
    v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_10;
  }
  v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_10;
    v4 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  }
  v4();
  v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_10:
  if ( !*((_QWORD *)this + 12) )
    goto LABEL_15;
  if ( !v4 )
  {
    if ( !v5 )
      goto LABEL_15;
    v4 = (void (*)(void))v5;
  }
  v4();
LABEL_15:
  v6 = (void *)*((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  v8 = (void *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v8 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v8);
  }
  v10 = (struct _TP_TIMER *)*((_QWORD *)this + 2);
  if ( v10 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 2), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v10, 1);
    CloseThreadpoolTimer(v10);
  }
}

```

## disassembly

```asm
0x1800050d0  push    rbx
0x1800050d2  push    rbp
0x1800050d3  push    rsi
0x1800050d4  push    rdi
0x1800050d5  sub     rsp, 28h
0x1800050d9  mov     rdi, rcx
0x1800050dc  xor     ebp, ebp
0x1800050de  mov     [rcx], ebp
0x1800050e0  mov     rsi, [rcx+10h]
0x1800050e4  test    rsi, rsi
0x1800050e7  jz      short loc_180005121
0x1800050e9  call    cs:__imp_GetLastError
0x1800050ef  mov     ebx, eax
0x1800050f1  xor     r9d, r9d; msWindowLength
0x1800050f4  xor     r8d, r8d; msPeriod
0x1800050f7  xor     edx, edx; pftDueTime
0x1800050f9  mov     rcx, rsi; pti
0x1800050fc  call    cs:__imp_SetThreadpoolTimer
0x180005102  mov     edx, 1; fCancelPendingCallbacks
0x180005107  mov     rcx, rsi; pti
0x18000510a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005110  mov     rcx, rsi; pti
0x180005113  call    cs:__imp_CloseThreadpoolTimer
0x180005119  mov     ecx, ebx; dwErrCode
0x18000511b  call    cs:__imp_SetLastError
0x180005121  mov     [rdi+10h], rbp
0x180005125  mov     rcx, rdi; this
0x180005128  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000512d  mov     rcx, [rdi+68h]
0x180005131  test    rcx, rcx
0x180005134  jz      short loc_180005166
0x180005136  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000513d  test    rax, rax
0x180005140  jnz     short loc_180005151
0x180005142  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180005149  test    rdx, rdx
0x18000514c  jz      short loc_180005164
0x18000514e  mov     rax, rdx
0x180005151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005156  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000515d  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180005164  jmp     short loc_180005174
0x180005166  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000516d  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180005174  mov     rcx, [rdi+60h]
0x180005178  test    rcx, rcx
0x18000517b  jz      short loc_180005190
0x18000517d  test    rax, rax
0x180005180  jnz     short loc_18000518A
0x180005182  test    rdx, rdx
0x180005185  jz      short loc_180005190
0x180005187  mov     rax, rdx
0x18000518a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000518f  nop
0x180005190  mov     rbx, [rdi+58h]
0x180005194  mov     [rdi+58h], rbp
0x180005198  test    rbx, rbx
0x18000519b  jz      short loc_1800051B1
0x18000519d  call    cs:__imp_GetProcessHeap
0x1800051a3  mov     rcx, rax; hHeap
0x1800051a6  mov     r8, rbx; lpMem
0x1800051a9  xor     edx, edx; dwFlags
0x1800051ab  call    cs:__imp_HeapFree
0x1800051b1  mov     rbx, [rdi+38h]
0x1800051b5  mov     [rdi+38h], rbp
0x1800051b9  test    rbx, rbx
0x1800051bc  jz      short loc_1800051D2
0x1800051be  call    cs:__imp_GetProcessHeap
0x1800051c4  mov     rcx, rax; hHeap
0x1800051c7  mov     r8, rbx; lpMem
0x1800051ca  xor     edx, edx; dwFlags
0x1800051cc  call    cs:__imp_HeapFree
0x1800051d2  mov     rbx, [rdi+10h]
0x1800051d6  test    rbx, rbx
0x1800051d9  jz      short loc_180005204
0x1800051db  xor     r9d, r9d; msWindowLength
0x1800051de  xor     r8d, r8d; msPeriod
0x1800051e1  xor     edx, edx; pftDueTime
0x1800051e3  mov     rcx, rbx; pti
0x1800051e6  call    cs:__imp_SetThreadpoolTimer
0x1800051ec  mov     edx, 1; fCancelPendingCallbacks
0x1800051f1  mov     rcx, rbx; pti
0x1800051f4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800051fa  mov     rcx, rbx; pti
0x1800051fd  call    cs:__imp_CloseThreadpoolTimer
0x180005203  nop
0x180005204  add     rsp, 28h
0x180005208  pop     rdi
0x180005209  pop     rsi
0x18000520a  pop     rbp
0x18000520b  pop     rbx
0x18000520c  retn
```
