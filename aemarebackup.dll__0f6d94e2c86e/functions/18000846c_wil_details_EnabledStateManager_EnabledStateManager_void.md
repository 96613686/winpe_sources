# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18000846c`
- end: `0x1800085c4`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800e9f40`

## callees

- `0x18000846c`
- `0x18000b40c`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008549`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000856e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008549`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000856e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008557`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000857c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008557`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000857c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800084bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800084bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000848d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000848d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800084a0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008596`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800084a0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008596`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800084b7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800085ad`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800084b7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800085ad`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800084ae`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800085a4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800084ae`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800085a4`

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
0x18000846c  mov     [rsp+arg_0], rbx
0x180008471  mov     [rsp+arg_8], rsi
0x180008476  push    rdi
0x180008477  sub     rsp, 20h
0x18000847b  mov     rdi, rcx
0x18000847e  mov     dword ptr [rcx], 0
0x180008484  mov     rsi, [rcx+10h]
0x180008488  test    rsi, rsi
0x18000848b  jz      short loc_1800084C5
0x18000848d  call    cs:__imp_GetLastError
0x180008493  mov     ebx, eax
0x180008495  xor     r9d, r9d; msWindowLength
0x180008498  xor     r8d, r8d; msPeriod
0x18000849b  xor     edx, edx; pftDueTime
0x18000849d  mov     rcx, rsi; pti
0x1800084a0  call    cs:__imp_SetThreadpoolTimer
0x1800084a6  mov     edx, 1; fCancelPendingCallbacks
0x1800084ab  mov     rcx, rsi; pti
0x1800084ae  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800084b4  mov     rcx, rsi; pti
0x1800084b7  call    cs:__imp_CloseThreadpoolTimer
0x1800084bd  mov     ecx, ebx; dwErrCode
0x1800084bf  call    cs:__imp_SetLastError
0x1800084c5  mov     qword ptr [rdi+10h], 0
0x1800084cd  mov     rcx, rdi; this
0x1800084d0  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1800084d5  mov     rcx, [rdi+68h]
0x1800084d9  test    rcx, rcx
0x1800084dc  jz      short loc_18000850E
0x1800084de  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800084e5  test    rax, rax
0x1800084e8  jnz     short loc_1800084F9
0x1800084ea  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800084f1  test    rdx, rdx
0x1800084f4  jz      short loc_18000850C
0x1800084f6  mov     rax, rdx
0x1800084f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084fe  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180008505  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000850c  jmp     short loc_18000851C
0x18000850e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180008515  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000851c  mov     rcx, [rdi+60h]
0x180008520  test    rcx, rcx
0x180008523  jz      short loc_180008538
0x180008525  test    rax, rax
0x180008528  jnz     short loc_180008532
0x18000852a  test    rdx, rdx
0x18000852d  jz      short loc_180008538
0x18000852f  mov     rax, rdx
0x180008532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008537  nop
0x180008538  mov     rbx, [rdi+58h]
0x18000853c  mov     qword ptr [rdi+58h], 0
0x180008544  test    rbx, rbx
0x180008547  jz      short loc_18000855D
0x180008549  call    cs:__imp_GetProcessHeap
0x18000854f  mov     rcx, rax; hHeap
0x180008552  mov     r8, rbx; lpMem
0x180008555  xor     edx, edx; dwFlags
0x180008557  call    cs:__imp_HeapFree
0x18000855d  mov     rbx, [rdi+38h]
0x180008561  mov     qword ptr [rdi+38h], 0
0x180008569  test    rbx, rbx
0x18000856c  jz      short loc_180008582
0x18000856e  call    cs:__imp_GetProcessHeap
0x180008574  mov     rcx, rax; hHeap
0x180008577  mov     r8, rbx; lpMem
0x18000857a  xor     edx, edx; dwFlags
0x18000857c  call    cs:__imp_HeapFree
0x180008582  mov     rbx, [rdi+10h]
0x180008586  test    rbx, rbx
0x180008589  jz      short loc_1800085B4
0x18000858b  xor     r9d, r9d; msWindowLength
0x18000858e  xor     r8d, r8d; msPeriod
0x180008591  xor     edx, edx; pftDueTime
0x180008593  mov     rcx, rbx; pti
0x180008596  call    cs:__imp_SetThreadpoolTimer
0x18000859c  mov     edx, 1; fCancelPendingCallbacks
0x1800085a1  mov     rcx, rbx; pti
0x1800085a4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800085aa  mov     rcx, rbx; pti
0x1800085ad  call    cs:__imp_CloseThreadpoolTimer
0x1800085b3  nop
0x1800085b4  mov     rbx, [rsp+28h+arg_0]
0x1800085b9  mov     rsi, [rsp+28h+arg_8]
0x1800085be  add     rsp, 20h
0x1800085c2  pop     rdi
0x1800085c3  retn
```
