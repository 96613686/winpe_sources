# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180003648`
- end: `0x180003836`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000e7f0`

## callees

- `0x1800034ec`
- `0x180003648`
- `0x180006e30`
- `0x1800080c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000376d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800037ae`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000376d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800037ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003706`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003756`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003796`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003706`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003756`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003796`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003714`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003764`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800037a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003714`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003764`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800037a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003666`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003666`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003698`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800036e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003698`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800036e1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003690`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800036d9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800037df`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003810`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003690`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800036d9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800037df`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003810`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003687`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800036d0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800037d6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003807`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003687`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800036d0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800037d6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003807`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003679`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800036c2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800037c8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800037f9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003679`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800036c2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800037c8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800037f9`

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
  if ( v8 && qword_180017248 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180017248[25], qword_180017248, v8);
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
0x180003648  mov     [rsp+arg_0], rbx
0x18000364d  mov     [rsp+arg_8], rsi
0x180003652  push    rdi
0x180003653  sub     rsp, 20h
0x180003657  mov     rdi, rcx
0x18000365a  mov     byte ptr [rcx], 0
0x18000365d  mov     rsi, [rcx+30h]
0x180003661  test    rsi, rsi
0x180003664  jz      short loc_18000369E
0x180003666  call    cs:__imp_GetLastError
0x18000366c  mov     ebx, eax
0x18000366e  xor     r9d, r9d; msWindowLength
0x180003671  xor     r8d, r8d; msPeriod
0x180003674  xor     edx, edx; pftDueTime
0x180003676  mov     rcx, rsi; pti
0x180003679  call    cs:__imp_SetThreadpoolTimer
0x18000367f  mov     edx, 1; fCancelPendingCallbacks
0x180003684  mov     rcx, rsi; pti
0x180003687  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000368d  mov     rcx, rsi; pti
0x180003690  call    cs:__imp_CloseThreadpoolTimer
0x180003696  mov     ecx, ebx; dwErrCode
0x180003698  call    cs:__imp_SetLastError
0x18000369e  mov     qword ptr [rdi+30h], 0
0x1800036a6  mov     rsi, [rdi+38h]
0x1800036aa  test    rsi, rsi
0x1800036ad  jz      short loc_1800036E7
0x1800036af  call    cs:__imp_GetLastError
0x1800036b5  mov     ebx, eax
0x1800036b7  xor     r9d, r9d; msWindowLength
0x1800036ba  xor     r8d, r8d; msPeriod
0x1800036bd  xor     edx, edx; pftDueTime
0x1800036bf  mov     rcx, rsi; pti
0x1800036c2  call    cs:__imp_SetThreadpoolTimer
0x1800036c8  mov     edx, 1; fCancelPendingCallbacks
0x1800036cd  mov     rcx, rsi; pti
0x1800036d0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800036d6  mov     rcx, rsi; pti
0x1800036d9  call    cs:__imp_CloseThreadpoolTimer
0x1800036df  mov     ecx, ebx; dwErrCode
0x1800036e1  call    cs:__imp_SetLastError
0x1800036e7  mov     qword ptr [rdi+38h], 0
0x1800036ef  mov     rbx, [rdi+100h]
0x1800036f6  mov     qword ptr [rdi+100h], 0
0x180003701  test    rbx, rbx
0x180003704  jz      short loc_18000371A
0x180003706  call    cs:__imp_GetProcessHeap
0x18000370c  mov     rcx, rax; hHeap
0x18000370f  mov     r8, rbx; lpMem
0x180003712  xor     edx, edx; dwFlags
0x180003714  call    cs:__imp_HeapFree
0x18000371a  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180003721  test    r8, r8
0x180003724  jz      short loc_18000373E
0x180003726  mov     rdx, cs:qword_180017248; SRWLock
0x18000372d  test    rdx, rdx
0x180003730  jz      short loc_18000373E
0x180003732  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180003739  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000373e  lea     rbx, [rdi+98h]
0x180003745  mov     rsi, [rbx+40h]
0x180003749  mov     qword ptr [rbx+40h], 0
0x180003751  test    rsi, rsi
0x180003754  jz      short loc_18000376A
0x180003756  call    cs:__imp_GetProcessHeap
0x18000375c  mov     rcx, rax; hHeap
0x18000375f  mov     r8, rsi; lpMem
0x180003762  xor     edx, edx; dwFlags
0x180003764  call    cs:__imp_HeapFree
0x18000376a  mov     rcx, rbx; lpCriticalSection
0x18000376d  call    cs:__imp_DeleteCriticalSection
0x180003773  lea     rcx, [rdi+90h]
0x18000377a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000377f  mov     rsi, [rdi+88h]
0x180003786  mov     qword ptr [rdi+88h], 0
0x180003791  test    rsi, rsi
0x180003794  jz      short loc_1800037AA
0x180003796  call    cs:__imp_GetProcessHeap
0x18000379c  mov     rcx, rax; hHeap
0x18000379f  mov     r8, rsi; lpMem
0x1800037a2  xor     edx, edx; dwFlags
0x1800037a4  call    cs:__imp_HeapFree
0x1800037aa  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800037ae  call    cs:__imp_DeleteCriticalSection
0x1800037b4  mov     rbx, [rdi+38h]
0x1800037b8  test    rbx, rbx
0x1800037bb  jz      short loc_1800037E5
0x1800037bd  xor     r9d, r9d; msWindowLength
0x1800037c0  xor     r8d, r8d; msPeriod
0x1800037c3  xor     edx, edx; pftDueTime
0x1800037c5  mov     rcx, rbx; pti
0x1800037c8  call    cs:__imp_SetThreadpoolTimer
0x1800037ce  mov     edx, 1; fCancelPendingCallbacks
0x1800037d3  mov     rcx, rbx; pti
0x1800037d6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800037dc  mov     rcx, rbx; pti
0x1800037df  call    cs:__imp_CloseThreadpoolTimer
0x1800037e5  mov     rbx, [rdi+30h]
0x1800037e9  test    rbx, rbx
0x1800037ec  jz      short loc_180003817
0x1800037ee  xor     r9d, r9d; msWindowLength
0x1800037f1  xor     r8d, r8d; msPeriod
0x1800037f4  xor     edx, edx; pftDueTime
0x1800037f6  mov     rcx, rbx; pti
0x1800037f9  call    cs:__imp_SetThreadpoolTimer
0x1800037ff  mov     edx, 1; fCancelPendingCallbacks
0x180003804  mov     rcx, rbx; pti
0x180003807  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000380d  mov     rcx, rbx; pti
0x180003810  call    cs:__imp_CloseThreadpoolTimer
0x180003816  nop
0x180003817  mov     rcx, [rdi+10h]; lpMem
0x18000381b  test    rcx, rcx
0x18000381e  jz      short loc_180003826
0x180003820  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180003825  nop
0x180003826  mov     rbx, [rsp+28h+arg_0]
0x18000382b  mov     rsi, [rsp+28h+arg_8]
0x180003830  add     rsp, 20h
0x180003834  pop     rdi
0x180003835  retn
```
