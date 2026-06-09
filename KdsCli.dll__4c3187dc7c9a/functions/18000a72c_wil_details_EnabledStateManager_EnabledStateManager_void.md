# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18000a72c`
- end: `0x18000a872`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `326`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001a850`

## callees

- `0x18000a72c`
- `0x18000c6a4`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a77f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a77f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a74d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a74d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a806`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a82b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a806`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a82b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a7f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a81d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a7f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a81d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a760`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a845`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a760`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a845`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a76e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a853`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a76e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a853`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a777`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a85c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a777`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a85c`

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
0x18000a72c  mov     [rsp+arg_0], rbx
0x18000a731  mov     [rsp+arg_8], rsi
0x18000a736  push    rdi
0x18000a737  sub     rsp, 20h
0x18000a73b  mov     dword ptr [rcx], 0
0x18000a741  mov     rdi, rcx
0x18000a744  mov     rsi, [rcx+10h]
0x18000a748  test    rsi, rsi
0x18000a74b  jz      short loc_18000A785
0x18000a74d  call    cs:__imp_GetLastError
0x18000a753  xor     r9d, r9d; msWindowLength
0x18000a756  xor     r8d, r8d; msPeriod
0x18000a759  xor     edx, edx; pftDueTime
0x18000a75b  mov     rcx, rsi; pti
0x18000a75e  mov     ebx, eax
0x18000a760  call    cs:__imp_SetThreadpoolTimer
0x18000a766  mov     edx, 1; fCancelPendingCallbacks
0x18000a76b  mov     rcx, rsi; pti
0x18000a76e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a774  mov     rcx, rsi; pti
0x18000a777  call    cs:__imp_CloseThreadpoolTimer
0x18000a77d  mov     ecx, ebx; dwErrCode
0x18000a77f  call    cs:__imp_SetLastError
0x18000a785  mov     rcx, rdi; this
0x18000a788  mov     qword ptr [rdi+10h], 0
0x18000a790  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000a795  mov     rcx, [rdi+68h]
0x18000a799  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000a7a0  test    rcx, rcx
0x18000a7a3  jz      short loc_18000A7C5
0x18000a7a5  test    rax, rax
0x18000a7a8  jnz     short loc_18000A7B9
0x18000a7aa  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000a7b1  test    rdx, rdx
0x18000a7b4  jz      short loc_18000A7CC
0x18000a7b6  mov     rax, rdx
0x18000a7b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7be  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000a7c5  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000a7cc  mov     rcx, [rdi+60h]
0x18000a7d0  test    rcx, rcx
0x18000a7d3  jz      short loc_18000A7E7
0x18000a7d5  test    rax, rax
0x18000a7d8  jnz     short loc_18000A7E2
0x18000a7da  test    rdx, rdx
0x18000a7dd  jz      short loc_18000A7E7
0x18000a7df  mov     rax, rdx
0x18000a7e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7e7  mov     rbx, [rdi+58h]
0x18000a7eb  mov     qword ptr [rdi+58h], 0
0x18000a7f3  test    rbx, rbx
0x18000a7f6  jz      short loc_18000A80C
0x18000a7f8  call    cs:__imp_GetProcessHeap
0x18000a7fe  mov     r8, rbx; lpMem
0x18000a801  xor     edx, edx; dwFlags
0x18000a803  mov     rcx, rax; hHeap
0x18000a806  call    cs:__imp_HeapFree
0x18000a80c  mov     rbx, [rdi+38h]
0x18000a810  mov     qword ptr [rdi+38h], 0
0x18000a818  test    rbx, rbx
0x18000a81b  jz      short loc_18000A831
0x18000a81d  call    cs:__imp_GetProcessHeap
0x18000a823  mov     r8, rbx; lpMem
0x18000a826  xor     edx, edx; dwFlags
0x18000a828  mov     rcx, rax; hHeap
0x18000a82b  call    cs:__imp_HeapFree
0x18000a831  mov     rbx, [rdi+10h]
0x18000a835  test    rbx, rbx
0x18000a838  jz      short loc_18000A862
0x18000a83a  xor     r9d, r9d; msWindowLength
0x18000a83d  xor     r8d, r8d; msPeriod
0x18000a840  xor     edx, edx; pftDueTime
0x18000a842  mov     rcx, rbx; pti
0x18000a845  call    cs:__imp_SetThreadpoolTimer
0x18000a84b  mov     edx, 1; fCancelPendingCallbacks
0x18000a850  mov     rcx, rbx; pti
0x18000a853  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a859  mov     rcx, rbx; pti
0x18000a85c  call    cs:__imp_CloseThreadpoolTimer
0x18000a862  mov     rbx, [rsp+28h+arg_0]
0x18000a867  mov     rsi, [rsp+28h+arg_8]
0x18000a86c  add     rsp, 20h
0x18000a870  pop     rdi
0x18000a871  retn
```
