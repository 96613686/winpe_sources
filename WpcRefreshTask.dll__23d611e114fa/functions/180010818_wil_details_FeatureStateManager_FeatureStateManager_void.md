# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180010818`
- end: `0x180010a06`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800abe30`

## callees

- `0x180010460`
- `0x180010818`
- `0x180012dbc`
- `0x180013408`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800108d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010926`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010966`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800108d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010926`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010966`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800108e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010934`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010974`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800108e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010934`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010974`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010868`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800108b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010868`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800108b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010836`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001087f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010836`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001087f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001093d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001097e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001093d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001097e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010860`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800108a9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800109af`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800109e0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010860`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800108a9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800109af`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800109e0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010857`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800108a0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800109a6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800109d7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010857`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800108a0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800109a6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800109d7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010849`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010892`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010998`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800109c9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010849`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010892`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010998`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800109c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  if ( v8 && qword_1800F0198 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800F0198[25], qword_1800F0198, v8);
  v9 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v9 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v9);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((char *)this + 144);
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
0x180010818  mov     [rsp+arg_0], rbx
0x18001081d  mov     [rsp+arg_8], rsi
0x180010822  push    rdi
0x180010823  sub     rsp, 20h
0x180010827  mov     rdi, rcx
0x18001082a  mov     byte ptr [rcx], 0
0x18001082d  mov     rsi, [rcx+30h]
0x180010831  test    rsi, rsi
0x180010834  jz      short loc_18001086E
0x180010836  call    cs:__imp_GetLastError
0x18001083c  mov     ebx, eax
0x18001083e  xor     r9d, r9d; msWindowLength
0x180010841  xor     r8d, r8d; msPeriod
0x180010844  xor     edx, edx; pftDueTime
0x180010846  mov     rcx, rsi; pti
0x180010849  call    cs:__imp_SetThreadpoolTimer
0x18001084f  mov     edx, 1; fCancelPendingCallbacks
0x180010854  mov     rcx, rsi; pti
0x180010857  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001085d  mov     rcx, rsi; pti
0x180010860  call    cs:__imp_CloseThreadpoolTimer
0x180010866  mov     ecx, ebx; dwErrCode
0x180010868  call    cs:__imp_SetLastError
0x18001086e  mov     qword ptr [rdi+30h], 0
0x180010876  mov     rsi, [rdi+38h]
0x18001087a  test    rsi, rsi
0x18001087d  jz      short loc_1800108B7
0x18001087f  call    cs:__imp_GetLastError
0x180010885  mov     ebx, eax
0x180010887  xor     r9d, r9d; msWindowLength
0x18001088a  xor     r8d, r8d; msPeriod
0x18001088d  xor     edx, edx; pftDueTime
0x18001088f  mov     rcx, rsi; pti
0x180010892  call    cs:__imp_SetThreadpoolTimer
0x180010898  mov     edx, 1; fCancelPendingCallbacks
0x18001089d  mov     rcx, rsi; pti
0x1800108a0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800108a6  mov     rcx, rsi; pti
0x1800108a9  call    cs:__imp_CloseThreadpoolTimer
0x1800108af  mov     ecx, ebx; dwErrCode
0x1800108b1  call    cs:__imp_SetLastError
0x1800108b7  mov     qword ptr [rdi+38h], 0
0x1800108bf  mov     rbx, [rdi+100h]
0x1800108c6  mov     qword ptr [rdi+100h], 0
0x1800108d1  test    rbx, rbx
0x1800108d4  jz      short loc_1800108EA
0x1800108d6  call    cs:__imp_GetProcessHeap
0x1800108dc  mov     rcx, rax; hHeap
0x1800108df  mov     r8, rbx; lpMem
0x1800108e2  xor     edx, edx; dwFlags
0x1800108e4  call    cs:__imp_HeapFree
0x1800108ea  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800108f1  test    r8, r8
0x1800108f4  jz      short loc_18001090E
0x1800108f6  mov     rdx, cs:qword_1800F0198; SRWLock
0x1800108fd  test    rdx, rdx
0x180010900  jz      short loc_18001090E
0x180010902  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180010909  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18001090e  lea     rbx, [rdi+98h]
0x180010915  mov     rsi, [rbx+40h]
0x180010919  mov     qword ptr [rbx+40h], 0
0x180010921  test    rsi, rsi
0x180010924  jz      short loc_18001093A
0x180010926  call    cs:__imp_GetProcessHeap
0x18001092c  mov     rcx, rax; hHeap
0x18001092f  mov     r8, rsi; lpMem
0x180010932  xor     edx, edx; dwFlags
0x180010934  call    cs:__imp_HeapFree
0x18001093a  mov     rcx, rbx; lpCriticalSection
0x18001093d  call    cs:__imp_DeleteCriticalSection
0x180010943  lea     rcx, [rdi+90h]
0x18001094a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001094f  mov     rsi, [rdi+88h]
0x180010956  mov     qword ptr [rdi+88h], 0
0x180010961  test    rsi, rsi
0x180010964  jz      short loc_18001097A
0x180010966  call    cs:__imp_GetProcessHeap
0x18001096c  mov     rcx, rax; hHeap
0x18001096f  mov     r8, rsi; lpMem
0x180010972  xor     edx, edx; dwFlags
0x180010974  call    cs:__imp_HeapFree
0x18001097a  lea     rcx, [rdi+48h]; lpCriticalSection
0x18001097e  call    cs:__imp_DeleteCriticalSection
0x180010984  mov     rbx, [rdi+38h]
0x180010988  test    rbx, rbx
0x18001098b  jz      short loc_1800109B5
0x18001098d  xor     r9d, r9d; msWindowLength
0x180010990  xor     r8d, r8d; msPeriod
0x180010993  xor     edx, edx; pftDueTime
0x180010995  mov     rcx, rbx; pti
0x180010998  call    cs:__imp_SetThreadpoolTimer
0x18001099e  mov     edx, 1; fCancelPendingCallbacks
0x1800109a3  mov     rcx, rbx; pti
0x1800109a6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800109ac  mov     rcx, rbx; pti
0x1800109af  call    cs:__imp_CloseThreadpoolTimer
0x1800109b5  mov     rbx, [rdi+30h]
0x1800109b9  test    rbx, rbx
0x1800109bc  jz      short loc_1800109E7
0x1800109be  xor     r9d, r9d; msWindowLength
0x1800109c1  xor     r8d, r8d; msPeriod
0x1800109c4  xor     edx, edx; pftDueTime
0x1800109c6  mov     rcx, rbx; pti
0x1800109c9  call    cs:__imp_SetThreadpoolTimer
0x1800109cf  mov     edx, 1; fCancelPendingCallbacks
0x1800109d4  mov     rcx, rbx; pti
0x1800109d7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800109dd  mov     rcx, rbx; pti
0x1800109e0  call    cs:__imp_CloseThreadpoolTimer
0x1800109e6  nop
0x1800109e7  mov     rcx, [rdi+10h]; lpMem
0x1800109eb  test    rcx, rcx
0x1800109ee  jz      short loc_1800109F6
0x1800109f0  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800109f5  nop
0x1800109f6  mov     rbx, [rsp+28h+arg_0]
0x1800109fb  mov     rsi, [rsp+28h+arg_8]
0x180010a00  add     rsp, 20h
0x180010a04  pop     rdi
0x180010a05  retn
```
