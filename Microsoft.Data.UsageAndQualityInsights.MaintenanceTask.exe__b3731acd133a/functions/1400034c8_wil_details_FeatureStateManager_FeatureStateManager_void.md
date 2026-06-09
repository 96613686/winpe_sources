# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1400034c8`
- end: `0x1400036b6`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000b9f0`

## callees

- `0x140003224`
- `0x1400034c8`
- `0x140007110`
- `0x1400084b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400035ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000362e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400035ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000362e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003586`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400035d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003616`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003586`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400035d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003616`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003594`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400035e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003624`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003594`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400035e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003624`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400034e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000352f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400034e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000352f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003518`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003561`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003518`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003561`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140003510`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140003559`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000365f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140003690`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140003510`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140003559`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000365f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140003690`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400034f9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003542`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003648`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003679`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400034f9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003542`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003648`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003679`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140003507`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140003550`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140003656`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140003687`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140003507`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140003550`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140003656`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140003687`

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
  if ( v8 && qword_140011018 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_140011018[25], qword_140011018, v8);
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
0x1400034c8  mov     [rsp+arg_0], rbx
0x1400034cd  mov     [rsp+arg_8], rsi
0x1400034d2  push    rdi
0x1400034d3  sub     rsp, 20h
0x1400034d7  mov     rdi, rcx
0x1400034da  mov     byte ptr [rcx], 0
0x1400034dd  mov     rsi, [rcx+30h]
0x1400034e1  test    rsi, rsi
0x1400034e4  jz      short loc_14000351E
0x1400034e6  call    cs:__imp_GetLastError
0x1400034ec  mov     ebx, eax
0x1400034ee  xor     r9d, r9d; msWindowLength
0x1400034f1  xor     r8d, r8d; msPeriod
0x1400034f4  xor     edx, edx; pftDueTime
0x1400034f6  mov     rcx, rsi; pti
0x1400034f9  call    cs:__imp_SetThreadpoolTimer
0x1400034ff  mov     edx, 1; fCancelPendingCallbacks
0x140003504  mov     rcx, rsi; pti
0x140003507  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000350d  mov     rcx, rsi; pti
0x140003510  call    cs:__imp_CloseThreadpoolTimer
0x140003516  mov     ecx, ebx; dwErrCode
0x140003518  call    cs:__imp_SetLastError
0x14000351e  mov     qword ptr [rdi+30h], 0
0x140003526  mov     rsi, [rdi+38h]
0x14000352a  test    rsi, rsi
0x14000352d  jz      short loc_140003567
0x14000352f  call    cs:__imp_GetLastError
0x140003535  mov     ebx, eax
0x140003537  xor     r9d, r9d; msWindowLength
0x14000353a  xor     r8d, r8d; msPeriod
0x14000353d  xor     edx, edx; pftDueTime
0x14000353f  mov     rcx, rsi; pti
0x140003542  call    cs:__imp_SetThreadpoolTimer
0x140003548  mov     edx, 1; fCancelPendingCallbacks
0x14000354d  mov     rcx, rsi; pti
0x140003550  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140003556  mov     rcx, rsi; pti
0x140003559  call    cs:__imp_CloseThreadpoolTimer
0x14000355f  mov     ecx, ebx; dwErrCode
0x140003561  call    cs:__imp_SetLastError
0x140003567  mov     qword ptr [rdi+38h], 0
0x14000356f  mov     rbx, [rdi+100h]
0x140003576  mov     qword ptr [rdi+100h], 0
0x140003581  test    rbx, rbx
0x140003584  jz      short loc_14000359A
0x140003586  call    cs:__imp_GetProcessHeap
0x14000358c  mov     rcx, rax; hHeap
0x14000358f  mov     r8, rbx; lpMem
0x140003592  xor     edx, edx; dwFlags
0x140003594  call    cs:__imp_HeapFree
0x14000359a  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1400035a1  test    r8, r8
0x1400035a4  jz      short loc_1400035BE
0x1400035a6  mov     rdx, cs:qword_140011018; SRWLock
0x1400035ad  test    rdx, rdx
0x1400035b0  jz      short loc_1400035BE
0x1400035b2  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1400035b9  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1400035be  lea     rbx, [rdi+98h]
0x1400035c5  mov     rsi, [rbx+40h]
0x1400035c9  mov     qword ptr [rbx+40h], 0
0x1400035d1  test    rsi, rsi
0x1400035d4  jz      short loc_1400035EA
0x1400035d6  call    cs:__imp_GetProcessHeap
0x1400035dc  mov     rcx, rax; hHeap
0x1400035df  mov     r8, rsi; lpMem
0x1400035e2  xor     edx, edx; dwFlags
0x1400035e4  call    cs:__imp_HeapFree
0x1400035ea  mov     rcx, rbx; lpCriticalSection
0x1400035ed  call    cs:__imp_DeleteCriticalSection
0x1400035f3  lea     rcx, [rdi+90h]
0x1400035fa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400035ff  mov     rsi, [rdi+88h]
0x140003606  mov     qword ptr [rdi+88h], 0
0x140003611  test    rsi, rsi
0x140003614  jz      short loc_14000362A
0x140003616  call    cs:__imp_GetProcessHeap
0x14000361c  mov     rcx, rax; hHeap
0x14000361f  mov     r8, rsi; lpMem
0x140003622  xor     edx, edx; dwFlags
0x140003624  call    cs:__imp_HeapFree
0x14000362a  lea     rcx, [rdi+48h]; lpCriticalSection
0x14000362e  call    cs:__imp_DeleteCriticalSection
0x140003634  mov     rbx, [rdi+38h]
0x140003638  test    rbx, rbx
0x14000363b  jz      short loc_140003665
0x14000363d  xor     r9d, r9d; msWindowLength
0x140003640  xor     r8d, r8d; msPeriod
0x140003643  xor     edx, edx; pftDueTime
0x140003645  mov     rcx, rbx; pti
0x140003648  call    cs:__imp_SetThreadpoolTimer
0x14000364e  mov     edx, 1; fCancelPendingCallbacks
0x140003653  mov     rcx, rbx; pti
0x140003656  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000365c  mov     rcx, rbx; pti
0x14000365f  call    cs:__imp_CloseThreadpoolTimer
0x140003665  mov     rbx, [rdi+30h]
0x140003669  test    rbx, rbx
0x14000366c  jz      short loc_140003697
0x14000366e  xor     r9d, r9d; msWindowLength
0x140003671  xor     r8d, r8d; msPeriod
0x140003674  xor     edx, edx; pftDueTime
0x140003676  mov     rcx, rbx; pti
0x140003679  call    cs:__imp_SetThreadpoolTimer
0x14000367f  mov     edx, 1; fCancelPendingCallbacks
0x140003684  mov     rcx, rbx; pti
0x140003687  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000368d  mov     rcx, rbx; pti
0x140003690  call    cs:__imp_CloseThreadpoolTimer
0x140003696  nop
0x140003697  mov     rcx, [rdi+10h]; lpMem
0x14000369b  test    rcx, rcx
0x14000369e  jz      short loc_1400036A6
0x1400036a0  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1400036a5  nop
0x1400036a6  mov     rbx, [rsp+28h+arg_0]
0x1400036ab  mov     rsi, [rsp+28h+arg_8]
0x1400036b0  add     rsp, 20h
0x1400036b4  pop     rdi
0x1400036b5  retn
```
