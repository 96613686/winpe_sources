# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18001f830`
- end: `0x18001f976`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `326`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18008df70`

## callees

- `0x18001f830`
- `0x18002d778`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f883`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f883`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f851`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f851`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f8fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f921`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f8fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f921`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f90a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f92f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f90a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f92f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001f864`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001f949`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001f864`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001f949`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001f87b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001f960`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001f87b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001f960`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001f872`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001f957`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001f872`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001f957`

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
  v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( *((_QWORD *)this + 13) )
  {
    if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
    {
      v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
      if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
        goto LABEL_9;
      v4 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    }
    v4();
    v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  }
  v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
LABEL_9:
  if ( !*((_QWORD *)this + 12) )
    goto LABEL_14;
  if ( !v4 )
  {
    if ( !v5 )
      goto LABEL_14;
    v4 = (void (*)(void))v5;
  }
  v4();
LABEL_14:
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
0x18001f830  mov     [rsp+arg_0], rbx
0x18001f835  mov     [rsp+arg_8], rsi
0x18001f83a  push    rdi
0x18001f83b  sub     rsp, 20h
0x18001f83f  mov     dword ptr [rcx], 0
0x18001f845  mov     rdi, rcx
0x18001f848  mov     rsi, [rcx+10h]
0x18001f84c  test    rsi, rsi
0x18001f84f  jz      short loc_18001F889
0x18001f851  call    cs:__imp_GetLastError
0x18001f857  xor     r9d, r9d; msWindowLength
0x18001f85a  xor     r8d, r8d; msPeriod
0x18001f85d  xor     edx, edx; pftDueTime
0x18001f85f  mov     rcx, rsi; pti
0x18001f862  mov     ebx, eax
0x18001f864  call    cs:__imp_SetThreadpoolTimer
0x18001f86a  mov     edx, 1; fCancelPendingCallbacks
0x18001f86f  mov     rcx, rsi; pti
0x18001f872  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001f878  mov     rcx, rsi; pti
0x18001f87b  call    cs:__imp_CloseThreadpoolTimer
0x18001f881  mov     ecx, ebx; dwErrCode
0x18001f883  call    cs:__imp_SetLastError
0x18001f889  mov     rcx, rdi; this
0x18001f88c  mov     qword ptr [rdi+10h], 0
0x18001f894  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18001f899  mov     rcx, [rdi+68h]
0x18001f89d  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18001f8a4  test    rcx, rcx
0x18001f8a7  jz      short loc_18001F8C9
0x18001f8a9  test    rax, rax
0x18001f8ac  jnz     short loc_18001F8BD
0x18001f8ae  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18001f8b5  test    rdx, rdx
0x18001f8b8  jz      short loc_18001F8D0
0x18001f8ba  mov     rax, rdx
0x18001f8bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8c2  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18001f8c9  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18001f8d0  mov     rcx, [rdi+60h]
0x18001f8d4  test    rcx, rcx
0x18001f8d7  jz      short loc_18001F8EB
0x18001f8d9  test    rax, rax
0x18001f8dc  jnz     short loc_18001F8E6
0x18001f8de  test    rdx, rdx
0x18001f8e1  jz      short loc_18001F8EB
0x18001f8e3  mov     rax, rdx
0x18001f8e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8eb  mov     rbx, [rdi+58h]
0x18001f8ef  mov     qword ptr [rdi+58h], 0
0x18001f8f7  test    rbx, rbx
0x18001f8fa  jz      short loc_18001F910
0x18001f8fc  call    cs:__imp_GetProcessHeap
0x18001f902  mov     r8, rbx; lpMem
0x18001f905  xor     edx, edx; dwFlags
0x18001f907  mov     rcx, rax; hHeap
0x18001f90a  call    cs:__imp_HeapFree
0x18001f910  mov     rbx, [rdi+38h]
0x18001f914  mov     qword ptr [rdi+38h], 0
0x18001f91c  test    rbx, rbx
0x18001f91f  jz      short loc_18001F935
0x18001f921  call    cs:__imp_GetProcessHeap
0x18001f927  mov     r8, rbx; lpMem
0x18001f92a  xor     edx, edx; dwFlags
0x18001f92c  mov     rcx, rax; hHeap
0x18001f92f  call    cs:__imp_HeapFree
0x18001f935  mov     rbx, [rdi+10h]
0x18001f939  test    rbx, rbx
0x18001f93c  jz      short loc_18001F966
0x18001f93e  xor     r9d, r9d; msWindowLength
0x18001f941  xor     r8d, r8d; msPeriod
0x18001f944  xor     edx, edx; pftDueTime
0x18001f946  mov     rcx, rbx; pti
0x18001f949  call    cs:__imp_SetThreadpoolTimer
0x18001f94f  mov     edx, 1; fCancelPendingCallbacks
0x18001f954  mov     rcx, rbx; pti
0x18001f957  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001f95d  mov     rcx, rbx; pti
0x18001f960  call    cs:__imp_CloseThreadpoolTimer
0x18001f966  mov     rbx, [rsp+28h+arg_0]
0x18001f96b  mov     rsi, [rsp+28h+arg_8]
0x18001f970  add     rsp, 20h
0x18001f974  pop     rdi
0x18001f975  retn
```
