# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180006290`
- end: `0x18000647e`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800670d0`

## callees

- `0x180005fec`
- `0x180006290`
- `0x18000a0f8`
- `0x18000b6ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800063b5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800063f6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800063b5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800063f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000634e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000639e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000634e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000639e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000635c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000635c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800062e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006329`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800062e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006329`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800062c1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000630a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006410`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006441`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800062c1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000630a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006410`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006441`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800062d8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006321`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006427`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006458`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800062d8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006321`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006427`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006458`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800062cf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006318`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000641e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000644f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800062cf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006318`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000641e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000644f`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
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
  if ( v8 && qword_1800B8150 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800B8150[25], qword_1800B8150, v8);
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
0x180006290  mov     [rsp+arg_0], rbx
0x180006295  mov     [rsp+arg_8], rsi
0x18000629a  push    rdi
0x18000629b  sub     rsp, 20h
0x18000629f  mov     rdi, rcx
0x1800062a2  mov     byte ptr [rcx], 0
0x1800062a5  mov     rsi, [rcx+30h]
0x1800062a9  test    rsi, rsi
0x1800062ac  jz      short loc_1800062E6
0x1800062ae  call    cs:__imp_GetLastError
0x1800062b4  mov     ebx, eax
0x1800062b6  xor     r9d, r9d; msWindowLength
0x1800062b9  xor     r8d, r8d; msPeriod
0x1800062bc  xor     edx, edx; pftDueTime
0x1800062be  mov     rcx, rsi; pti
0x1800062c1  call    cs:__imp_SetThreadpoolTimer
0x1800062c7  mov     edx, 1; fCancelPendingCallbacks
0x1800062cc  mov     rcx, rsi; pti
0x1800062cf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800062d5  mov     rcx, rsi; pti
0x1800062d8  call    cs:__imp_CloseThreadpoolTimer
0x1800062de  mov     ecx, ebx; dwErrCode
0x1800062e0  call    cs:__imp_SetLastError
0x1800062e6  mov     qword ptr [rdi+30h], 0
0x1800062ee  mov     rsi, [rdi+38h]
0x1800062f2  test    rsi, rsi
0x1800062f5  jz      short loc_18000632F
0x1800062f7  call    cs:__imp_GetLastError
0x1800062fd  mov     ebx, eax
0x1800062ff  xor     r9d, r9d; msWindowLength
0x180006302  xor     r8d, r8d; msPeriod
0x180006305  xor     edx, edx; pftDueTime
0x180006307  mov     rcx, rsi; pti
0x18000630a  call    cs:__imp_SetThreadpoolTimer
0x180006310  mov     edx, 1; fCancelPendingCallbacks
0x180006315  mov     rcx, rsi; pti
0x180006318  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000631e  mov     rcx, rsi; pti
0x180006321  call    cs:__imp_CloseThreadpoolTimer
0x180006327  mov     ecx, ebx; dwErrCode
0x180006329  call    cs:__imp_SetLastError
0x18000632f  mov     qword ptr [rdi+38h], 0
0x180006337  mov     rbx, [rdi+100h]
0x18000633e  mov     qword ptr [rdi+100h], 0
0x180006349  test    rbx, rbx
0x18000634c  jz      short loc_180006362
0x18000634e  call    cs:__imp_GetProcessHeap
0x180006354  mov     rcx, rax; hHeap
0x180006357  mov     r8, rbx; lpMem
0x18000635a  xor     edx, edx; dwFlags
0x18000635c  call    cs:__imp_HeapFree
0x180006362  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180006369  test    r8, r8
0x18000636c  jz      short loc_180006386
0x18000636e  mov     rdx, cs:qword_1800B8150; SRWLock
0x180006375  test    rdx, rdx
0x180006378  jz      short loc_180006386
0x18000637a  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180006381  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180006386  lea     rbx, [rdi+98h]
0x18000638d  mov     rsi, [rbx+40h]
0x180006391  mov     qword ptr [rbx+40h], 0
0x180006399  test    rsi, rsi
0x18000639c  jz      short loc_1800063B2
0x18000639e  call    cs:__imp_GetProcessHeap
0x1800063a4  mov     rcx, rax; hHeap
0x1800063a7  mov     r8, rsi; lpMem
0x1800063aa  xor     edx, edx; dwFlags
0x1800063ac  call    cs:__imp_HeapFree
0x1800063b2  mov     rcx, rbx; lpCriticalSection
0x1800063b5  call    cs:__imp_DeleteCriticalSection
0x1800063bb  lea     rcx, [rdi+90h]
0x1800063c2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800063c7  mov     rsi, [rdi+88h]
0x1800063ce  mov     qword ptr [rdi+88h], 0
0x1800063d9  test    rsi, rsi
0x1800063dc  jz      short loc_1800063F2
0x1800063de  call    cs:__imp_GetProcessHeap
0x1800063e4  mov     rcx, rax; hHeap
0x1800063e7  mov     r8, rsi; lpMem
0x1800063ea  xor     edx, edx; dwFlags
0x1800063ec  call    cs:__imp_HeapFree
0x1800063f2  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800063f6  call    cs:__imp_DeleteCriticalSection
0x1800063fc  mov     rbx, [rdi+38h]
0x180006400  test    rbx, rbx
0x180006403  jz      short loc_18000642D
0x180006405  xor     r9d, r9d; msWindowLength
0x180006408  xor     r8d, r8d; msPeriod
0x18000640b  xor     edx, edx; pftDueTime
0x18000640d  mov     rcx, rbx; pti
0x180006410  call    cs:__imp_SetThreadpoolTimer
0x180006416  mov     edx, 1; fCancelPendingCallbacks
0x18000641b  mov     rcx, rbx; pti
0x18000641e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006424  mov     rcx, rbx; pti
0x180006427  call    cs:__imp_CloseThreadpoolTimer
0x18000642d  mov     rbx, [rdi+30h]
0x180006431  test    rbx, rbx
0x180006434  jz      short loc_18000645F
0x180006436  xor     r9d, r9d; msWindowLength
0x180006439  xor     r8d, r8d; msPeriod
0x18000643c  xor     edx, edx; pftDueTime
0x18000643e  mov     rcx, rbx; pti
0x180006441  call    cs:__imp_SetThreadpoolTimer
0x180006447  mov     edx, 1; fCancelPendingCallbacks
0x18000644c  mov     rcx, rbx; pti
0x18000644f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006455  mov     rcx, rbx; pti
0x180006458  call    cs:__imp_CloseThreadpoolTimer
0x18000645e  nop
0x18000645f  mov     rcx, [rdi+10h]; lpMem
0x180006463  test    rcx, rcx
0x180006466  jz      short loc_18000646E
0x180006468  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18000646d  nop
0x18000646e  mov     rbx, [rsp+28h+arg_0]
0x180006473  mov     rsi, [rsp+28h+arg_8]
0x180006478  add     rsp, 20h
0x18000647c  pop     rdi
0x18000647d  retn
```
