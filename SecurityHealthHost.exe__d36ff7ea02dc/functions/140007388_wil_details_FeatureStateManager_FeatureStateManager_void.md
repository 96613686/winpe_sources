# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x140007388`
- end: `0x140007576`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000ff30`

## callees

- `0x140007244`
- `0x140007388`
- `0x14000a318`
- `0x14000b5cc`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400074ad`
- `KERNEL32!DeleteCriticalSection` at `0x1400074ee`
- `KERNEL32!DeleteCriticalSection` at `0x1400074ad`
- `KERNEL32!DeleteCriticalSection` at `0x1400074ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400073a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400073ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400073a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400073ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400073d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007421`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400073d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007421`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007446`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007496`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400074d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007446`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007496`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400074d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007454`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400074a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400074e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007454`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400074a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400074e4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400073d0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140007419`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000751f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140007550`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400073d0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140007419`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000751f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140007550`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400073b9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140007402`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140007508`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140007539`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400073b9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140007402`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140007508`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140007539`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400073c7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140007410`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140007516`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140007547`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400073c7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140007410`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140007516`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140007547`

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
  if ( v8 && qword_140018028 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_140018028[25], qword_140018028, v8);
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
0x140007388  mov     [rsp+arg_0], rbx
0x14000738d  mov     [rsp+arg_8], rsi
0x140007392  push    rdi
0x140007393  sub     rsp, 20h
0x140007397  mov     rdi, rcx
0x14000739a  mov     byte ptr [rcx], 0
0x14000739d  mov     rsi, [rcx+30h]
0x1400073a1  test    rsi, rsi
0x1400073a4  jz      short loc_1400073DE
0x1400073a6  call    cs:__imp_GetLastError
0x1400073ac  mov     ebx, eax
0x1400073ae  xor     r9d, r9d; msWindowLength
0x1400073b1  xor     r8d, r8d; msPeriod
0x1400073b4  xor     edx, edx; pftDueTime
0x1400073b6  mov     rcx, rsi; pti
0x1400073b9  call    cs:__imp_SetThreadpoolTimer
0x1400073bf  mov     edx, 1; fCancelPendingCallbacks
0x1400073c4  mov     rcx, rsi; pti
0x1400073c7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400073cd  mov     rcx, rsi; pti
0x1400073d0  call    cs:__imp_CloseThreadpoolTimer
0x1400073d6  mov     ecx, ebx; dwErrCode
0x1400073d8  call    cs:__imp_SetLastError
0x1400073de  mov     qword ptr [rdi+30h], 0
0x1400073e6  mov     rsi, [rdi+38h]
0x1400073ea  test    rsi, rsi
0x1400073ed  jz      short loc_140007427
0x1400073ef  call    cs:__imp_GetLastError
0x1400073f5  mov     ebx, eax
0x1400073f7  xor     r9d, r9d; msWindowLength
0x1400073fa  xor     r8d, r8d; msPeriod
0x1400073fd  xor     edx, edx; pftDueTime
0x1400073ff  mov     rcx, rsi; pti
0x140007402  call    cs:__imp_SetThreadpoolTimer
0x140007408  mov     edx, 1; fCancelPendingCallbacks
0x14000740d  mov     rcx, rsi; pti
0x140007410  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140007416  mov     rcx, rsi; pti
0x140007419  call    cs:__imp_CloseThreadpoolTimer
0x14000741f  mov     ecx, ebx; dwErrCode
0x140007421  call    cs:__imp_SetLastError
0x140007427  mov     qword ptr [rdi+38h], 0
0x14000742f  mov     rbx, [rdi+100h]
0x140007436  mov     qword ptr [rdi+100h], 0
0x140007441  test    rbx, rbx
0x140007444  jz      short loc_14000745A
0x140007446  call    cs:__imp_GetProcessHeap
0x14000744c  mov     rcx, rax; hHeap
0x14000744f  mov     r8, rbx; lpMem
0x140007452  xor     edx, edx; dwFlags
0x140007454  call    cs:__imp_HeapFree
0x14000745a  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x140007461  test    r8, r8
0x140007464  jz      short loc_14000747E
0x140007466  mov     rdx, cs:qword_140018028; SRWLock
0x14000746d  test    rdx, rdx
0x140007470  jz      short loc_14000747E
0x140007472  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140007479  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x14000747e  lea     rbx, [rdi+98h]
0x140007485  mov     rsi, [rbx+40h]
0x140007489  mov     qword ptr [rbx+40h], 0
0x140007491  test    rsi, rsi
0x140007494  jz      short loc_1400074AA
0x140007496  call    cs:__imp_GetProcessHeap
0x14000749c  mov     rcx, rax; hHeap
0x14000749f  mov     r8, rsi; lpMem
0x1400074a2  xor     edx, edx; dwFlags
0x1400074a4  call    cs:__imp_HeapFree
0x1400074aa  mov     rcx, rbx; lpCriticalSection
0x1400074ad  call    cs:__imp_DeleteCriticalSection
0x1400074b3  lea     rcx, [rdi+90h]
0x1400074ba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400074bf  mov     rsi, [rdi+88h]
0x1400074c6  mov     qword ptr [rdi+88h], 0
0x1400074d1  test    rsi, rsi
0x1400074d4  jz      short loc_1400074EA
0x1400074d6  call    cs:__imp_GetProcessHeap
0x1400074dc  mov     rcx, rax; hHeap
0x1400074df  mov     r8, rsi; lpMem
0x1400074e2  xor     edx, edx; dwFlags
0x1400074e4  call    cs:__imp_HeapFree
0x1400074ea  lea     rcx, [rdi+48h]; lpCriticalSection
0x1400074ee  call    cs:__imp_DeleteCriticalSection
0x1400074f4  mov     rbx, [rdi+38h]
0x1400074f8  test    rbx, rbx
0x1400074fb  jz      short loc_140007525
0x1400074fd  xor     r9d, r9d; msWindowLength
0x140007500  xor     r8d, r8d; msPeriod
0x140007503  xor     edx, edx; pftDueTime
0x140007505  mov     rcx, rbx; pti
0x140007508  call    cs:__imp_SetThreadpoolTimer
0x14000750e  mov     edx, 1; fCancelPendingCallbacks
0x140007513  mov     rcx, rbx; pti
0x140007516  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000751c  mov     rcx, rbx; pti
0x14000751f  call    cs:__imp_CloseThreadpoolTimer
0x140007525  mov     rbx, [rdi+30h]
0x140007529  test    rbx, rbx
0x14000752c  jz      short loc_140007557
0x14000752e  xor     r9d, r9d; msWindowLength
0x140007531  xor     r8d, r8d; msPeriod
0x140007534  xor     edx, edx; pftDueTime
0x140007536  mov     rcx, rbx; pti
0x140007539  call    cs:__imp_SetThreadpoolTimer
0x14000753f  mov     edx, 1; fCancelPendingCallbacks
0x140007544  mov     rcx, rbx; pti
0x140007547  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000754d  mov     rcx, rbx; pti
0x140007550  call    cs:__imp_CloseThreadpoolTimer
0x140007556  nop
0x140007557  mov     rcx, [rdi+10h]; lpMem
0x14000755b  test    rcx, rcx
0x14000755e  jz      short loc_140007566
0x140007560  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140007565  nop
0x140007566  mov     rbx, [rsp+28h+arg_0]
0x14000756b  mov     rsi, [rsp+28h+arg_8]
0x140007570  add     rsp, 20h
0x140007574  pop     rdi
0x140007575  retn
```
