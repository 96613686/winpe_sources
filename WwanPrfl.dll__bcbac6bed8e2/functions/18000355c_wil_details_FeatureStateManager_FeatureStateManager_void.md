# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000355c`
- end: `0x18000374a`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180013a00`

## callees

- `0x180003298`
- `0x18000355c`
- `0x180007510`
- `0x180008b30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000357a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000357a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800035ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800035f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800035ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800035f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003628`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003678`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003628`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003678`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000361a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000366a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000361a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000366a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036aa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003681`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800036c2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003681`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800036c2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800035a4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800035ed`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800036f3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003724`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800035a4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800035ed`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800036f3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003724`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000359b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800035e4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800036ea`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000371b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000359b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800035e4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800036ea`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000371b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000358d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800035d6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800036dc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000370d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000358d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800035d6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800036dc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000370d`

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
  if ( v8 && qword_18001F078 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18001F078[25], qword_18001F078, v8);
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
0x18000355c  mov     [rsp+arg_0], rbx
0x180003561  mov     [rsp+arg_8], rsi
0x180003566  push    rdi
0x180003567  sub     rsp, 20h
0x18000356b  mov     rdi, rcx
0x18000356e  mov     byte ptr [rcx], 0
0x180003571  mov     rsi, [rcx+30h]
0x180003575  test    rsi, rsi
0x180003578  jz      short loc_1800035B2
0x18000357a  call    cs:__imp_GetLastError
0x180003580  mov     ebx, eax
0x180003582  xor     r9d, r9d; msWindowLength
0x180003585  xor     r8d, r8d; msPeriod
0x180003588  xor     edx, edx; pftDueTime
0x18000358a  mov     rcx, rsi; pti
0x18000358d  call    cs:__imp_SetThreadpoolTimer
0x180003593  mov     edx, 1; fCancelPendingCallbacks
0x180003598  mov     rcx, rsi; pti
0x18000359b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800035a1  mov     rcx, rsi; pti
0x1800035a4  call    cs:__imp_CloseThreadpoolTimer
0x1800035aa  mov     ecx, ebx; dwErrCode
0x1800035ac  call    cs:__imp_SetLastError
0x1800035b2  mov     qword ptr [rdi+30h], 0
0x1800035ba  mov     rsi, [rdi+38h]
0x1800035be  test    rsi, rsi
0x1800035c1  jz      short loc_1800035FB
0x1800035c3  call    cs:__imp_GetLastError
0x1800035c9  mov     ebx, eax
0x1800035cb  xor     r9d, r9d; msWindowLength
0x1800035ce  xor     r8d, r8d; msPeriod
0x1800035d1  xor     edx, edx; pftDueTime
0x1800035d3  mov     rcx, rsi; pti
0x1800035d6  call    cs:__imp_SetThreadpoolTimer
0x1800035dc  mov     edx, 1; fCancelPendingCallbacks
0x1800035e1  mov     rcx, rsi; pti
0x1800035e4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800035ea  mov     rcx, rsi; pti
0x1800035ed  call    cs:__imp_CloseThreadpoolTimer
0x1800035f3  mov     ecx, ebx; dwErrCode
0x1800035f5  call    cs:__imp_SetLastError
0x1800035fb  mov     qword ptr [rdi+38h], 0
0x180003603  mov     rbx, [rdi+100h]
0x18000360a  mov     qword ptr [rdi+100h], 0
0x180003615  test    rbx, rbx
0x180003618  jz      short loc_18000362E
0x18000361a  call    cs:__imp_GetProcessHeap
0x180003620  mov     rcx, rax; hHeap
0x180003623  mov     r8, rbx; lpMem
0x180003626  xor     edx, edx; dwFlags
0x180003628  call    cs:__imp_HeapFree
0x18000362e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180003635  test    r8, r8
0x180003638  jz      short loc_180003652
0x18000363a  mov     rdx, cs:qword_18001F078; SRWLock
0x180003641  test    rdx, rdx
0x180003644  jz      short loc_180003652
0x180003646  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000364d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180003652  lea     rbx, [rdi+98h]
0x180003659  mov     rsi, [rbx+40h]
0x18000365d  mov     qword ptr [rbx+40h], 0
0x180003665  test    rsi, rsi
0x180003668  jz      short loc_18000367E
0x18000366a  call    cs:__imp_GetProcessHeap
0x180003670  mov     rcx, rax; hHeap
0x180003673  mov     r8, rsi; lpMem
0x180003676  xor     edx, edx; dwFlags
0x180003678  call    cs:__imp_HeapFree
0x18000367e  mov     rcx, rbx; lpCriticalSection
0x180003681  call    cs:__imp_DeleteCriticalSection
0x180003687  lea     rcx, [rdi+90h]
0x18000368e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180003693  mov     rsi, [rdi+88h]
0x18000369a  mov     qword ptr [rdi+88h], 0
0x1800036a5  test    rsi, rsi
0x1800036a8  jz      short loc_1800036BE
0x1800036aa  call    cs:__imp_GetProcessHeap
0x1800036b0  mov     rcx, rax; hHeap
0x1800036b3  mov     r8, rsi; lpMem
0x1800036b6  xor     edx, edx; dwFlags
0x1800036b8  call    cs:__imp_HeapFree
0x1800036be  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800036c2  call    cs:__imp_DeleteCriticalSection
0x1800036c8  mov     rbx, [rdi+38h]
0x1800036cc  test    rbx, rbx
0x1800036cf  jz      short loc_1800036F9
0x1800036d1  xor     r9d, r9d; msWindowLength
0x1800036d4  xor     r8d, r8d; msPeriod
0x1800036d7  xor     edx, edx; pftDueTime
0x1800036d9  mov     rcx, rbx; pti
0x1800036dc  call    cs:__imp_SetThreadpoolTimer
0x1800036e2  mov     edx, 1; fCancelPendingCallbacks
0x1800036e7  mov     rcx, rbx; pti
0x1800036ea  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800036f0  mov     rcx, rbx; pti
0x1800036f3  call    cs:__imp_CloseThreadpoolTimer
0x1800036f9  mov     rbx, [rdi+30h]
0x1800036fd  test    rbx, rbx
0x180003700  jz      short loc_18000372B
0x180003702  xor     r9d, r9d; msWindowLength
0x180003705  xor     r8d, r8d; msPeriod
0x180003708  xor     edx, edx; pftDueTime
0x18000370a  mov     rcx, rbx; pti
0x18000370d  call    cs:__imp_SetThreadpoolTimer
0x180003713  mov     edx, 1; fCancelPendingCallbacks
0x180003718  mov     rcx, rbx; pti
0x18000371b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003721  mov     rcx, rbx; pti
0x180003724  call    cs:__imp_CloseThreadpoolTimer
0x18000372a  nop
0x18000372b  mov     rcx, [rdi+10h]; lpMem
0x18000372f  test    rcx, rcx
0x180003732  jz      short loc_18000373A
0x180003734  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180003739  nop
0x18000373a  mov     rbx, [rsp+28h+arg_0]
0x18000373f  mov     rsi, [rsp+28h+arg_8]
0x180003744  add     rsp, 20h
0x180003748  pop     rdi
0x180003749  retn
```
