# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x14000b2f8`
- end: `0x14000b450`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001c5a0`

## callees

- `0x14000b2f8`
- `0x140010414`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b3d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b3fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b3d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b3fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b3e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b408`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b3e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b408`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b319`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b34b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b34b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000b32c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000b422`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000b32c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000b422`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000b343`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000b439`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000b343`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000b439`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000b33a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000b430`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000b33a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000b430`

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
0x14000b2f8  mov     [rsp+arg_0], rbx
0x14000b2fd  mov     [rsp+arg_8], rsi
0x14000b302  push    rdi
0x14000b303  sub     rsp, 20h
0x14000b307  mov     rdi, rcx
0x14000b30a  mov     dword ptr [rcx], 0
0x14000b310  mov     rsi, [rcx+10h]
0x14000b314  test    rsi, rsi
0x14000b317  jz      short loc_14000B351
0x14000b319  call    cs:__imp_GetLastError
0x14000b31f  mov     ebx, eax
0x14000b321  xor     r9d, r9d; msWindowLength
0x14000b324  xor     r8d, r8d; msPeriod
0x14000b327  xor     edx, edx; pftDueTime
0x14000b329  mov     rcx, rsi; pti
0x14000b32c  call    cs:__imp_SetThreadpoolTimer
0x14000b332  mov     edx, 1; fCancelPendingCallbacks
0x14000b337  mov     rcx, rsi; pti
0x14000b33a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000b340  mov     rcx, rsi; pti
0x14000b343  call    cs:__imp_CloseThreadpoolTimer
0x14000b349  mov     ecx, ebx; dwErrCode
0x14000b34b  call    cs:__imp_SetLastError
0x14000b351  mov     qword ptr [rdi+10h], 0
0x14000b359  mov     rcx, rdi; this
0x14000b35c  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x14000b361  mov     rcx, [rdi+68h]
0x14000b365  test    rcx, rcx
0x14000b368  jz      short loc_14000B39A
0x14000b36a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14000b371  test    rax, rax
0x14000b374  jnz     short loc_14000B385
0x14000b376  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x14000b37d  test    rdx, rdx
0x14000b380  jz      short loc_14000B398
0x14000b382  mov     rax, rdx
0x14000b385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b38a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x14000b391  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14000b398  jmp     short loc_14000B3A8
0x14000b39a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14000b3a1  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x14000b3a8  mov     rcx, [rdi+60h]
0x14000b3ac  test    rcx, rcx
0x14000b3af  jz      short loc_14000B3C4
0x14000b3b1  test    rax, rax
0x14000b3b4  jnz     short loc_14000B3BE
0x14000b3b6  test    rdx, rdx
0x14000b3b9  jz      short loc_14000B3C4
0x14000b3bb  mov     rax, rdx
0x14000b3be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b3c3  nop
0x14000b3c4  mov     rbx, [rdi+58h]
0x14000b3c8  mov     qword ptr [rdi+58h], 0
0x14000b3d0  test    rbx, rbx
0x14000b3d3  jz      short loc_14000B3E9
0x14000b3d5  call    cs:__imp_GetProcessHeap
0x14000b3db  mov     rcx, rax; hHeap
0x14000b3de  mov     r8, rbx; lpMem
0x14000b3e1  xor     edx, edx; dwFlags
0x14000b3e3  call    cs:__imp_HeapFree
0x14000b3e9  mov     rbx, [rdi+38h]
0x14000b3ed  mov     qword ptr [rdi+38h], 0
0x14000b3f5  test    rbx, rbx
0x14000b3f8  jz      short loc_14000B40E
0x14000b3fa  call    cs:__imp_GetProcessHeap
0x14000b400  mov     rcx, rax; hHeap
0x14000b403  mov     r8, rbx; lpMem
0x14000b406  xor     edx, edx; dwFlags
0x14000b408  call    cs:__imp_HeapFree
0x14000b40e  mov     rbx, [rdi+10h]
0x14000b412  test    rbx, rbx
0x14000b415  jz      short loc_14000B440
0x14000b417  xor     r9d, r9d; msWindowLength
0x14000b41a  xor     r8d, r8d; msPeriod
0x14000b41d  xor     edx, edx; pftDueTime
0x14000b41f  mov     rcx, rbx; pti
0x14000b422  call    cs:__imp_SetThreadpoolTimer
0x14000b428  mov     edx, 1; fCancelPendingCallbacks
0x14000b42d  mov     rcx, rbx; pti
0x14000b430  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000b436  mov     rcx, rbx; pti
0x14000b439  call    cs:__imp_CloseThreadpoolTimer
0x14000b43f  nop
0x14000b440  mov     rbx, [rsp+28h+arg_0]
0x14000b445  mov     rsi, [rsp+28h+arg_8]
0x14000b44a  add     rsp, 20h
0x14000b44e  pop     rdi
0x14000b44f  retn
```
