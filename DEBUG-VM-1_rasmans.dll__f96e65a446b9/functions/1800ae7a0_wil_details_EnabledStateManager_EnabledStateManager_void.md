# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800ae7a0`
- end: `0x1800ae8e6`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `326`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800e8330`

## callees

- `0x1800ae7a0`
- `0x1800b5098`
- `0x1800e9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ae7f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ae7f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae7c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae7c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ae87a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ae89f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ae87a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ae89f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ae86c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ae891`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ae86c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ae891`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800ae7e2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800ae8c7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800ae7e2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800ae8c7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800ae7eb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800ae8d0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800ae7eb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800ae8d0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800ae7d4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800ae8b9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800ae7d4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800ae8b9`

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
0x1800ae7a0  mov     [rsp+arg_0], rbx
0x1800ae7a5  mov     [rsp+arg_8], rsi
0x1800ae7aa  push    rdi
0x1800ae7ab  sub     rsp, 20h
0x1800ae7af  mov     dword ptr [rcx], 0
0x1800ae7b5  mov     rdi, rcx
0x1800ae7b8  mov     rsi, [rcx+10h]
0x1800ae7bc  test    rsi, rsi
0x1800ae7bf  jz      short loc_1800AE7F9
0x1800ae7c1  call    cs:__imp_GetLastError
0x1800ae7c7  xor     r9d, r9d; msWindowLength
0x1800ae7ca  xor     r8d, r8d; msPeriod
0x1800ae7cd  xor     edx, edx; pftDueTime
0x1800ae7cf  mov     rcx, rsi; pti
0x1800ae7d2  mov     ebx, eax
0x1800ae7d4  call    cs:__imp_SetThreadpoolTimer
0x1800ae7da  mov     edx, 1; fCancelPendingCallbacks
0x1800ae7df  mov     rcx, rsi; pti
0x1800ae7e2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800ae7e8  mov     rcx, rsi; pti
0x1800ae7eb  call    cs:__imp_CloseThreadpoolTimer
0x1800ae7f1  mov     ecx, ebx; dwErrCode
0x1800ae7f3  call    cs:__imp_SetLastError
0x1800ae7f9  mov     rcx, rdi; this
0x1800ae7fc  mov     qword ptr [rdi+10h], 0
0x1800ae804  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1800ae809  mov     rcx, [rdi+68h]
0x1800ae80d  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800ae814  test    rcx, rcx
0x1800ae817  jz      short loc_1800AE839
0x1800ae819  test    rax, rax
0x1800ae81c  jnz     short loc_1800AE82D
0x1800ae81e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800ae825  test    rdx, rdx
0x1800ae828  jz      short loc_1800AE840
0x1800ae82a  mov     rax, rdx
0x1800ae82d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae832  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800ae839  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800ae840  mov     rcx, [rdi+60h]
0x1800ae844  test    rcx, rcx
0x1800ae847  jz      short loc_1800AE85B
0x1800ae849  test    rax, rax
0x1800ae84c  jnz     short loc_1800AE856
0x1800ae84e  test    rdx, rdx
0x1800ae851  jz      short loc_1800AE85B
0x1800ae853  mov     rax, rdx
0x1800ae856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae85b  mov     rbx, [rdi+58h]
0x1800ae85f  mov     qword ptr [rdi+58h], 0
0x1800ae867  test    rbx, rbx
0x1800ae86a  jz      short loc_1800AE880
0x1800ae86c  call    cs:__imp_GetProcessHeap
0x1800ae872  mov     r8, rbx; lpMem
0x1800ae875  xor     edx, edx; dwFlags
0x1800ae877  mov     rcx, rax; hHeap
0x1800ae87a  call    cs:__imp_HeapFree
0x1800ae880  mov     rbx, [rdi+38h]
0x1800ae884  mov     qword ptr [rdi+38h], 0
0x1800ae88c  test    rbx, rbx
0x1800ae88f  jz      short loc_1800AE8A5
0x1800ae891  call    cs:__imp_GetProcessHeap
0x1800ae897  mov     r8, rbx; lpMem
0x1800ae89a  xor     edx, edx; dwFlags
0x1800ae89c  mov     rcx, rax; hHeap
0x1800ae89f  call    cs:__imp_HeapFree
0x1800ae8a5  mov     rbx, [rdi+10h]
0x1800ae8a9  test    rbx, rbx
0x1800ae8ac  jz      short loc_1800AE8D6
0x1800ae8ae  xor     r9d, r9d; msWindowLength
0x1800ae8b1  xor     r8d, r8d; msPeriod
0x1800ae8b4  xor     edx, edx; pftDueTime
0x1800ae8b6  mov     rcx, rbx; pti
0x1800ae8b9  call    cs:__imp_SetThreadpoolTimer
0x1800ae8bf  mov     edx, 1; fCancelPendingCallbacks
0x1800ae8c4  mov     rcx, rbx; pti
0x1800ae8c7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800ae8cd  mov     rcx, rbx; pti
0x1800ae8d0  call    cs:__imp_CloseThreadpoolTimer
0x1800ae8d6  mov     rbx, [rsp+28h+arg_0]
0x1800ae8db  mov     rsi, [rsp+28h+arg_8]
0x1800ae8e0  add     rsp, 20h
0x1800ae8e4  pop     rdi
0x1800ae8e5  retn
```
