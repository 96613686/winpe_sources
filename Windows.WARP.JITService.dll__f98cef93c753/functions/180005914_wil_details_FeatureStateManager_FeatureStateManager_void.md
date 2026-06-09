# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180005914`
- end: `0x180005afa`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `486`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009a90`

## callees

- `0x1800055c8`
- `0x180005914`
- `0x180007368`
- `0x18000757c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005a39`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005a7a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005a39`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005a7a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800059e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a70`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800059e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800059d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800059d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a62`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005964`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800059ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005964`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800059ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005932`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000597b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005932`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000597b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005945`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000598e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005a94`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005ac5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005945`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000598e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005a94`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005ac5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000595c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800059a5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005aab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005adc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000595c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800059a5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005aab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005adc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005953`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000599c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005aa2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005ad3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005953`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000599c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005aa2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005ad3`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(wil::details::FeatureStateManager *this)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *v4; // rsi
  DWORD v5; // ebx
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v8; // r8
  void *v9; // rsi
  HANDLE v10; // rax
  void *v11; // rsi
  HANDLE v12; // rax
  struct _TP_TIMER *v13; // rbx
  struct _TP_TIMER *v14; // rbx

  *(_BYTE *)this = 0;
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v2 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 6) = 0;
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v4 )
  {
    v5 = GetLastError();
    SetThreadpoolTimer(v4, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v4, 1);
    CloseThreadpoolTimer(v4);
    SetLastError(v5);
  }
  *((_QWORD *)this + 7) = 0;
  v6 = (void *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  v8 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)*((_QWORD *)this + 28);
  if ( v8 && qword_18000F018 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18000F018[25], qword_18000F018, v8);
  v9 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v9 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v9);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((__int64 *)this + 18);
  v11 = (void *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v11 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v11);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v13 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v13 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 7), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v13, 1);
    CloseThreadpoolTimer(v13);
  }
  v14 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v14 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 6), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v14, 1);
    CloseThreadpoolTimer(v14);
  }
  wil::details_abi::ProcessLocalStorage<wil::details_abi::FeatureStateData>::~ProcessLocalStorage<wil::details_abi::FeatureStateData>((__int64)this + 8);
}

```

## disassembly

```asm
0x180005914  mov     [rsp+arg_0], rbx
0x180005919  mov     [rsp+arg_8], rsi
0x18000591e  push    rdi
0x18000591f  sub     rsp, 20h
0x180005923  mov     byte ptr [rcx], 0
0x180005926  mov     rdi, rcx
0x180005929  mov     rsi, [rcx+30h]
0x18000592d  test    rsi, rsi
0x180005930  jz      short loc_18000596A
0x180005932  call    cs:__imp_GetLastError
0x180005938  xor     r9d, r9d; msWindowLength
0x18000593b  xor     r8d, r8d; msPeriod
0x18000593e  xor     edx, edx; pftDueTime
0x180005940  mov     rcx, rsi; pti
0x180005943  mov     ebx, eax
0x180005945  call    cs:__imp_SetThreadpoolTimer
0x18000594b  mov     edx, 1; fCancelPendingCallbacks
0x180005950  mov     rcx, rsi; pti
0x180005953  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005959  mov     rcx, rsi; pti
0x18000595c  call    cs:__imp_CloseThreadpoolTimer
0x180005962  mov     ecx, ebx; dwErrCode
0x180005964  call    cs:__imp_SetLastError
0x18000596a  mov     qword ptr [rdi+30h], 0
0x180005972  mov     rsi, [rdi+38h]
0x180005976  test    rsi, rsi
0x180005979  jz      short loc_1800059B3
0x18000597b  call    cs:__imp_GetLastError
0x180005981  xor     r9d, r9d; msWindowLength
0x180005984  xor     r8d, r8d; msPeriod
0x180005987  xor     edx, edx; pftDueTime
0x180005989  mov     rcx, rsi; pti
0x18000598c  mov     ebx, eax
0x18000598e  call    cs:__imp_SetThreadpoolTimer
0x180005994  mov     edx, 1; fCancelPendingCallbacks
0x180005999  mov     rcx, rsi; pti
0x18000599c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800059a2  mov     rcx, rsi; pti
0x1800059a5  call    cs:__imp_CloseThreadpoolTimer
0x1800059ab  mov     ecx, ebx; dwErrCode
0x1800059ad  call    cs:__imp_SetLastError
0x1800059b3  mov     qword ptr [rdi+38h], 0
0x1800059bb  mov     rbx, [rdi+100h]
0x1800059c2  mov     qword ptr [rdi+100h], 0
0x1800059cd  test    rbx, rbx
0x1800059d0  jz      short loc_1800059E6
0x1800059d2  call    cs:__imp_GetProcessHeap
0x1800059d8  mov     r8, rbx; lpMem
0x1800059db  xor     edx, edx; dwFlags
0x1800059dd  mov     rcx, rax; hHeap
0x1800059e0  call    cs:__imp_HeapFree
0x1800059e6  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800059ed  test    r8, r8
0x1800059f0  jz      short loc_180005A0A
0x1800059f2  mov     rdx, cs:qword_18000F018; SRWLock
0x1800059f9  test    rdx, rdx
0x1800059fc  jz      short loc_180005A0A
0x1800059fe  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180005a05  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180005a0a  lea     rbx, [rdi+98h]
0x180005a11  mov     rsi, [rbx+40h]
0x180005a15  mov     qword ptr [rbx+40h], 0
0x180005a1d  test    rsi, rsi
0x180005a20  jz      short loc_180005A36
0x180005a22  call    cs:__imp_GetProcessHeap
0x180005a28  mov     r8, rsi; lpMem
0x180005a2b  xor     edx, edx; dwFlags
0x180005a2d  mov     rcx, rax; hHeap
0x180005a30  call    cs:__imp_HeapFree
0x180005a36  mov     rcx, rbx; lpCriticalSection
0x180005a39  call    cs:__imp_DeleteCriticalSection
0x180005a3f  lea     rcx, [rdi+90h]
0x180005a46  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180005a4b  mov     rsi, [rdi+88h]
0x180005a52  mov     qword ptr [rdi+88h], 0
0x180005a5d  test    rsi, rsi
0x180005a60  jz      short loc_180005A76
0x180005a62  call    cs:__imp_GetProcessHeap
0x180005a68  mov     r8, rsi; lpMem
0x180005a6b  xor     edx, edx; dwFlags
0x180005a6d  mov     rcx, rax; hHeap
0x180005a70  call    cs:__imp_HeapFree
0x180005a76  lea     rcx, [rdi+48h]; lpCriticalSection
0x180005a7a  call    cs:__imp_DeleteCriticalSection
0x180005a80  mov     rbx, [rdi+38h]
0x180005a84  test    rbx, rbx
0x180005a87  jz      short loc_180005AB1
0x180005a89  xor     r9d, r9d; msWindowLength
0x180005a8c  xor     r8d, r8d; msPeriod
0x180005a8f  xor     edx, edx; pftDueTime
0x180005a91  mov     rcx, rbx; pti
0x180005a94  call    cs:__imp_SetThreadpoolTimer
0x180005a9a  mov     edx, 1; fCancelPendingCallbacks
0x180005a9f  mov     rcx, rbx; pti
0x180005aa2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005aa8  mov     rcx, rbx; pti
0x180005aab  call    cs:__imp_CloseThreadpoolTimer
0x180005ab1  mov     rbx, [rdi+30h]
0x180005ab5  test    rbx, rbx
0x180005ab8  jz      short loc_180005AE2
0x180005aba  xor     r9d, r9d; msWindowLength
0x180005abd  xor     r8d, r8d; msPeriod
0x180005ac0  xor     edx, edx; pftDueTime
0x180005ac2  mov     rcx, rbx; pti
0x180005ac5  call    cs:__imp_SetThreadpoolTimer
0x180005acb  mov     edx, 1; fCancelPendingCallbacks
0x180005ad0  mov     rcx, rbx; pti
0x180005ad3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005ad9  mov     rcx, rbx; pti
0x180005adc  call    cs:__imp_CloseThreadpoolTimer
0x180005ae2  lea     rcx, [rdi+8]
0x180005ae6  mov     rbx, [rsp+28h+arg_0]
0x180005aeb  mov     rsi, [rsp+28h+arg_8]
0x180005af0  add     rsp, 20h
0x180005af4  pop     rdi
0x180005af5  jmp     ??1?$ProcessLocalStorage@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorage<wil::details_abi::FeatureStateData>::~ProcessLocalStorage<wil::details_abi::FeatureStateData>(void)
```
