# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800055bc`
- end: `0x1800057a8`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000a600`

## callees

- `0x180005478`
- `0x1800055bc`
- `0x180008b30`
- `0x18000973c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800056e1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005722`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800056e1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005722`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000560c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005655`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000560c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005655`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005623`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005623`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800055fb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005644`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000574a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000577b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800055fb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005644`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000574a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000577b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005604`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000564d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005753`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005784`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005604`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000564d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005753`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005784`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800055ed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005636`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000573c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000576d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800055ed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005636`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000573c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000576d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005688`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800056d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005718`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005688`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800056d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005718`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000567a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800056ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000570a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000567a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800056ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000570a`

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
  void *v15; // rcx

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
  if ( v8 && qword_180011048 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180011048[25], qword_180011048, v8);
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
  v15 = (void *)*((_QWORD *)this + 2);
  if ( v15 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v15);
}

```

## disassembly

```asm
0x1800055bc  mov     [rsp+arg_0], rbx
0x1800055c1  mov     [rsp+arg_8], rsi
0x1800055c6  push    rdi
0x1800055c7  sub     rsp, 20h
0x1800055cb  mov     byte ptr [rcx], 0
0x1800055ce  mov     rdi, rcx
0x1800055d1  mov     rsi, [rcx+30h]
0x1800055d5  test    rsi, rsi
0x1800055d8  jz      short loc_180005612
0x1800055da  call    cs:__imp_GetLastError
0x1800055e0  xor     r9d, r9d; msWindowLength
0x1800055e3  xor     r8d, r8d; msPeriod
0x1800055e6  xor     edx, edx; pftDueTime
0x1800055e8  mov     rcx, rsi; pti
0x1800055eb  mov     ebx, eax
0x1800055ed  call    cs:__imp_SetThreadpoolTimer
0x1800055f3  mov     edx, 1; fCancelPendingCallbacks
0x1800055f8  mov     rcx, rsi; pti
0x1800055fb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005601  mov     rcx, rsi; pti
0x180005604  call    cs:__imp_CloseThreadpoolTimer
0x18000560a  mov     ecx, ebx; dwErrCode
0x18000560c  call    cs:__imp_SetLastError
0x180005612  mov     qword ptr [rdi+30h], 0
0x18000561a  mov     rsi, [rdi+38h]
0x18000561e  test    rsi, rsi
0x180005621  jz      short loc_18000565B
0x180005623  call    cs:__imp_GetLastError
0x180005629  xor     r9d, r9d; msWindowLength
0x18000562c  xor     r8d, r8d; msPeriod
0x18000562f  xor     edx, edx; pftDueTime
0x180005631  mov     rcx, rsi; pti
0x180005634  mov     ebx, eax
0x180005636  call    cs:__imp_SetThreadpoolTimer
0x18000563c  mov     edx, 1; fCancelPendingCallbacks
0x180005641  mov     rcx, rsi; pti
0x180005644  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000564a  mov     rcx, rsi; pti
0x18000564d  call    cs:__imp_CloseThreadpoolTimer
0x180005653  mov     ecx, ebx; dwErrCode
0x180005655  call    cs:__imp_SetLastError
0x18000565b  mov     qword ptr [rdi+38h], 0
0x180005663  mov     rbx, [rdi+100h]
0x18000566a  mov     qword ptr [rdi+100h], 0
0x180005675  test    rbx, rbx
0x180005678  jz      short loc_18000568E
0x18000567a  call    cs:__imp_GetProcessHeap
0x180005680  mov     r8, rbx; lpMem
0x180005683  xor     edx, edx; dwFlags
0x180005685  mov     rcx, rax; hHeap
0x180005688  call    cs:__imp_HeapFree
0x18000568e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180005695  test    r8, r8
0x180005698  jz      short loc_1800056B2
0x18000569a  mov     rdx, cs:qword_180011048; SRWLock
0x1800056a1  test    rdx, rdx
0x1800056a4  jz      short loc_1800056B2
0x1800056a6  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800056ad  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800056b2  lea     rbx, [rdi+98h]
0x1800056b9  mov     rsi, [rbx+40h]
0x1800056bd  mov     qword ptr [rbx+40h], 0
0x1800056c5  test    rsi, rsi
0x1800056c8  jz      short loc_1800056DE
0x1800056ca  call    cs:__imp_GetProcessHeap
0x1800056d0  mov     r8, rsi; lpMem
0x1800056d3  xor     edx, edx; dwFlags
0x1800056d5  mov     rcx, rax; hHeap
0x1800056d8  call    cs:__imp_HeapFree
0x1800056de  mov     rcx, rbx; lpCriticalSection
0x1800056e1  call    cs:__imp_DeleteCriticalSection
0x1800056e7  lea     rcx, [rdi+90h]
0x1800056ee  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800056f3  mov     rsi, [rdi+88h]
0x1800056fa  mov     qword ptr [rdi+88h], 0
0x180005705  test    rsi, rsi
0x180005708  jz      short loc_18000571E
0x18000570a  call    cs:__imp_GetProcessHeap
0x180005710  mov     r8, rsi; lpMem
0x180005713  xor     edx, edx; dwFlags
0x180005715  mov     rcx, rax; hHeap
0x180005718  call    cs:__imp_HeapFree
0x18000571e  lea     rcx, [rdi+48h]; lpCriticalSection
0x180005722  call    cs:__imp_DeleteCriticalSection
0x180005728  mov     rbx, [rdi+38h]
0x18000572c  test    rbx, rbx
0x18000572f  jz      short loc_180005759
0x180005731  xor     r9d, r9d; msWindowLength
0x180005734  xor     r8d, r8d; msPeriod
0x180005737  xor     edx, edx; pftDueTime
0x180005739  mov     rcx, rbx; pti
0x18000573c  call    cs:__imp_SetThreadpoolTimer
0x180005742  mov     edx, 1; fCancelPendingCallbacks
0x180005747  mov     rcx, rbx; pti
0x18000574a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005750  mov     rcx, rbx; pti
0x180005753  call    cs:__imp_CloseThreadpoolTimer
0x180005759  mov     rbx, [rdi+30h]
0x18000575d  test    rbx, rbx
0x180005760  jz      short loc_18000578A
0x180005762  xor     r9d, r9d; msWindowLength
0x180005765  xor     r8d, r8d; msPeriod
0x180005768  xor     edx, edx; pftDueTime
0x18000576a  mov     rcx, rbx; pti
0x18000576d  call    cs:__imp_SetThreadpoolTimer
0x180005773  mov     edx, 1; fCancelPendingCallbacks
0x180005778  mov     rcx, rbx; pti
0x18000577b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005781  mov     rcx, rbx; pti
0x180005784  call    cs:__imp_CloseThreadpoolTimer
0x18000578a  mov     rcx, [rdi+10h]; lpMem
0x18000578e  test    rcx, rcx
0x180005791  jz      short loc_180005798
0x180005793  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180005798  mov     rbx, [rsp+28h+arg_0]
0x18000579d  mov     rsi, [rsp+28h+arg_8]
0x1800057a2  add     rsp, 20h
0x1800057a6  pop     rdi
0x1800057a7  retn
```
