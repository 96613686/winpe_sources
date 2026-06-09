# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000366c`
- end: `0x180003858`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180013c80`

## callees

- `0x180003380`
- `0x18000366c`
- `0x180007080`
- `0x1800086f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003738`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003788`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800037c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003738`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003788`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800037c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000372a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000377a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800037ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000372a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000377a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800037ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000368a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000368a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800036bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003705`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800036bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003705`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003791`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800037d2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003791`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800037d2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800036b4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800036fd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003803`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003834`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800036b4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800036fd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003803`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003834`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000369d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800036e6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800037ec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000381d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000369d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800036e6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800037ec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000381d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800036ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800036f4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800037fa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000382b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800036ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800036f4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800037fa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000382b`

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
  if ( v8 && qword_18001A290 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18001A290[25], qword_18001A290, v8);
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
0x18000366c  mov     [rsp+arg_0], rbx
0x180003671  mov     [rsp+arg_8], rsi
0x180003676  push    rdi
0x180003677  sub     rsp, 20h
0x18000367b  mov     byte ptr [rcx], 0
0x18000367e  mov     rdi, rcx
0x180003681  mov     rsi, [rcx+30h]
0x180003685  test    rsi, rsi
0x180003688  jz      short loc_1800036C2
0x18000368a  call    cs:__imp_GetLastError
0x180003690  xor     r9d, r9d; msWindowLength
0x180003693  xor     r8d, r8d; msPeriod
0x180003696  xor     edx, edx; pftDueTime
0x180003698  mov     rcx, rsi; pti
0x18000369b  mov     ebx, eax
0x18000369d  call    cs:__imp_SetThreadpoolTimer
0x1800036a3  mov     edx, 1; fCancelPendingCallbacks
0x1800036a8  mov     rcx, rsi; pti
0x1800036ab  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800036b1  mov     rcx, rsi; pti
0x1800036b4  call    cs:__imp_CloseThreadpoolTimer
0x1800036ba  mov     ecx, ebx; dwErrCode
0x1800036bc  call    cs:__imp_SetLastError
0x1800036c2  mov     qword ptr [rdi+30h], 0
0x1800036ca  mov     rsi, [rdi+38h]
0x1800036ce  test    rsi, rsi
0x1800036d1  jz      short loc_18000370B
0x1800036d3  call    cs:__imp_GetLastError
0x1800036d9  xor     r9d, r9d; msWindowLength
0x1800036dc  xor     r8d, r8d; msPeriod
0x1800036df  xor     edx, edx; pftDueTime
0x1800036e1  mov     rcx, rsi; pti
0x1800036e4  mov     ebx, eax
0x1800036e6  call    cs:__imp_SetThreadpoolTimer
0x1800036ec  mov     edx, 1; fCancelPendingCallbacks
0x1800036f1  mov     rcx, rsi; pti
0x1800036f4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800036fa  mov     rcx, rsi; pti
0x1800036fd  call    cs:__imp_CloseThreadpoolTimer
0x180003703  mov     ecx, ebx; dwErrCode
0x180003705  call    cs:__imp_SetLastError
0x18000370b  mov     qword ptr [rdi+38h], 0
0x180003713  mov     rbx, [rdi+100h]
0x18000371a  mov     qword ptr [rdi+100h], 0
0x180003725  test    rbx, rbx
0x180003728  jz      short loc_18000373E
0x18000372a  call    cs:__imp_GetProcessHeap
0x180003730  mov     r8, rbx; lpMem
0x180003733  xor     edx, edx; dwFlags
0x180003735  mov     rcx, rax; hHeap
0x180003738  call    cs:__imp_HeapFree
0x18000373e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180003745  test    r8, r8
0x180003748  jz      short loc_180003762
0x18000374a  mov     rdx, cs:qword_18001A290; SRWLock
0x180003751  test    rdx, rdx
0x180003754  jz      short loc_180003762
0x180003756  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000375d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180003762  lea     rbx, [rdi+98h]
0x180003769  mov     rsi, [rbx+40h]
0x18000376d  mov     qword ptr [rbx+40h], 0
0x180003775  test    rsi, rsi
0x180003778  jz      short loc_18000378E
0x18000377a  call    cs:__imp_GetProcessHeap
0x180003780  mov     r8, rsi; lpMem
0x180003783  xor     edx, edx; dwFlags
0x180003785  mov     rcx, rax; hHeap
0x180003788  call    cs:__imp_HeapFree
0x18000378e  mov     rcx, rbx; lpCriticalSection
0x180003791  call    cs:__imp_DeleteCriticalSection
0x180003797  lea     rcx, [rdi+90h]
0x18000379e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800037a3  mov     rsi, [rdi+88h]
0x1800037aa  mov     qword ptr [rdi+88h], 0
0x1800037b5  test    rsi, rsi
0x1800037b8  jz      short loc_1800037CE
0x1800037ba  call    cs:__imp_GetProcessHeap
0x1800037c0  mov     r8, rsi; lpMem
0x1800037c3  xor     edx, edx; dwFlags
0x1800037c5  mov     rcx, rax; hHeap
0x1800037c8  call    cs:__imp_HeapFree
0x1800037ce  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800037d2  call    cs:__imp_DeleteCriticalSection
0x1800037d8  mov     rbx, [rdi+38h]
0x1800037dc  test    rbx, rbx
0x1800037df  jz      short loc_180003809
0x1800037e1  xor     r9d, r9d; msWindowLength
0x1800037e4  xor     r8d, r8d; msPeriod
0x1800037e7  xor     edx, edx; pftDueTime
0x1800037e9  mov     rcx, rbx; pti
0x1800037ec  call    cs:__imp_SetThreadpoolTimer
0x1800037f2  mov     edx, 1; fCancelPendingCallbacks
0x1800037f7  mov     rcx, rbx; pti
0x1800037fa  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003800  mov     rcx, rbx; pti
0x180003803  call    cs:__imp_CloseThreadpoolTimer
0x180003809  mov     rbx, [rdi+30h]
0x18000380d  test    rbx, rbx
0x180003810  jz      short loc_18000383A
0x180003812  xor     r9d, r9d; msWindowLength
0x180003815  xor     r8d, r8d; msPeriod
0x180003818  xor     edx, edx; pftDueTime
0x18000381a  mov     rcx, rbx; pti
0x18000381d  call    cs:__imp_SetThreadpoolTimer
0x180003823  mov     edx, 1; fCancelPendingCallbacks
0x180003828  mov     rcx, rbx; pti
0x18000382b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003831  mov     rcx, rbx; pti
0x180003834  call    cs:__imp_CloseThreadpoolTimer
0x18000383a  mov     rcx, [rdi+10h]; lpMem
0x18000383e  test    rcx, rcx
0x180003841  jz      short loc_180003848
0x180003843  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180003848  mov     rbx, [rsp+28h+arg_0]
0x18000384d  mov     rsi, [rsp+28h+arg_8]
0x180003852  add     rsp, 20h
0x180003856  pop     rdi
0x180003857  retn
```
