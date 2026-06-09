# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000825c`
- end: `0x18000844a`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18009c0f0`

## callees

- `0x180007fb8`
- `0x18000825c`
- `0x18000c62c`
- `0x18000dddc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008381`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800083c2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008381`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800083c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000831a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000836a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800083aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000831a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000836a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800083aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008328`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008378`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800083b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008328`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008378`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800083b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000827a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000827a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082f5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000829b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800082e4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800083ea`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000841b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000829b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800082e4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800083ea`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000841b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000828d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800082d6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800083dc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000840d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000828d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800082d6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800083dc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000840d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800082a4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800082ed`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800083f3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008424`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800082a4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800082ed`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800083f3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008424`

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
  if ( v8 && qword_18012F1B8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18012F1B8[25], qword_18012F1B8, v8);
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
0x18000825c  mov     [rsp+arg_0], rbx
0x180008261  mov     [rsp+arg_8], rsi
0x180008266  push    rdi
0x180008267  sub     rsp, 20h
0x18000826b  mov     rdi, rcx
0x18000826e  mov     byte ptr [rcx], 0
0x180008271  mov     rsi, [rcx+30h]
0x180008275  test    rsi, rsi
0x180008278  jz      short loc_1800082B2
0x18000827a  call    cs:__imp_GetLastError
0x180008280  mov     ebx, eax
0x180008282  xor     r9d, r9d; msWindowLength
0x180008285  xor     r8d, r8d; msPeriod
0x180008288  xor     edx, edx; pftDueTime
0x18000828a  mov     rcx, rsi; pti
0x18000828d  call    cs:__imp_SetThreadpoolTimer
0x180008293  mov     edx, 1; fCancelPendingCallbacks
0x180008298  mov     rcx, rsi; pti
0x18000829b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800082a1  mov     rcx, rsi; pti
0x1800082a4  call    cs:__imp_CloseThreadpoolTimer
0x1800082aa  mov     ecx, ebx; dwErrCode
0x1800082ac  call    cs:__imp_SetLastError
0x1800082b2  mov     qword ptr [rdi+30h], 0
0x1800082ba  mov     rsi, [rdi+38h]
0x1800082be  test    rsi, rsi
0x1800082c1  jz      short loc_1800082FB
0x1800082c3  call    cs:__imp_GetLastError
0x1800082c9  mov     ebx, eax
0x1800082cb  xor     r9d, r9d; msWindowLength
0x1800082ce  xor     r8d, r8d; msPeriod
0x1800082d1  xor     edx, edx; pftDueTime
0x1800082d3  mov     rcx, rsi; pti
0x1800082d6  call    cs:__imp_SetThreadpoolTimer
0x1800082dc  mov     edx, 1; fCancelPendingCallbacks
0x1800082e1  mov     rcx, rsi; pti
0x1800082e4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800082ea  mov     rcx, rsi; pti
0x1800082ed  call    cs:__imp_CloseThreadpoolTimer
0x1800082f3  mov     ecx, ebx; dwErrCode
0x1800082f5  call    cs:__imp_SetLastError
0x1800082fb  mov     qword ptr [rdi+38h], 0
0x180008303  mov     rbx, [rdi+100h]
0x18000830a  mov     qword ptr [rdi+100h], 0
0x180008315  test    rbx, rbx
0x180008318  jz      short loc_18000832E
0x18000831a  call    cs:__imp_GetProcessHeap
0x180008320  mov     rcx, rax; hHeap
0x180008323  mov     r8, rbx; lpMem
0x180008326  xor     edx, edx; dwFlags
0x180008328  call    cs:__imp_HeapFree
0x18000832e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180008335  test    r8, r8
0x180008338  jz      short loc_180008352
0x18000833a  mov     rdx, cs:qword_18012F1B8; SRWLock
0x180008341  test    rdx, rdx
0x180008344  jz      short loc_180008352
0x180008346  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000834d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180008352  lea     rbx, [rdi+98h]
0x180008359  mov     rsi, [rbx+40h]
0x18000835d  mov     qword ptr [rbx+40h], 0
0x180008365  test    rsi, rsi
0x180008368  jz      short loc_18000837E
0x18000836a  call    cs:__imp_GetProcessHeap
0x180008370  mov     rcx, rax; hHeap
0x180008373  mov     r8, rsi; lpMem
0x180008376  xor     edx, edx; dwFlags
0x180008378  call    cs:__imp_HeapFree
0x18000837e  mov     rcx, rbx; lpCriticalSection
0x180008381  call    cs:__imp_DeleteCriticalSection
0x180008387  lea     rcx, [rdi+90h]
0x18000838e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180008393  mov     rsi, [rdi+88h]
0x18000839a  mov     qword ptr [rdi+88h], 0
0x1800083a5  test    rsi, rsi
0x1800083a8  jz      short loc_1800083BE
0x1800083aa  call    cs:__imp_GetProcessHeap
0x1800083b0  mov     rcx, rax; hHeap
0x1800083b3  mov     r8, rsi; lpMem
0x1800083b6  xor     edx, edx; dwFlags
0x1800083b8  call    cs:__imp_HeapFree
0x1800083be  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800083c2  call    cs:__imp_DeleteCriticalSection
0x1800083c8  mov     rbx, [rdi+38h]
0x1800083cc  test    rbx, rbx
0x1800083cf  jz      short loc_1800083F9
0x1800083d1  xor     r9d, r9d; msWindowLength
0x1800083d4  xor     r8d, r8d; msPeriod
0x1800083d7  xor     edx, edx; pftDueTime
0x1800083d9  mov     rcx, rbx; pti
0x1800083dc  call    cs:__imp_SetThreadpoolTimer
0x1800083e2  mov     edx, 1; fCancelPendingCallbacks
0x1800083e7  mov     rcx, rbx; pti
0x1800083ea  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800083f0  mov     rcx, rbx; pti
0x1800083f3  call    cs:__imp_CloseThreadpoolTimer
0x1800083f9  mov     rbx, [rdi+30h]
0x1800083fd  test    rbx, rbx
0x180008400  jz      short loc_18000842B
0x180008402  xor     r9d, r9d; msWindowLength
0x180008405  xor     r8d, r8d; msPeriod
0x180008408  xor     edx, edx; pftDueTime
0x18000840a  mov     rcx, rbx; pti
0x18000840d  call    cs:__imp_SetThreadpoolTimer
0x180008413  mov     edx, 1; fCancelPendingCallbacks
0x180008418  mov     rcx, rbx; pti
0x18000841b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008421  mov     rcx, rbx; pti
0x180008424  call    cs:__imp_CloseThreadpoolTimer
0x18000842a  nop
0x18000842b  mov     rcx, [rdi+10h]; lpMem
0x18000842f  test    rcx, rcx
0x180008432  jz      short loc_18000843A
0x180008434  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180008439  nop
0x18000843a  mov     rbx, [rsp+28h+arg_0]
0x18000843f  mov     rsi, [rsp+28h+arg_8]
0x180008444  add     rsp, 20h
0x180008448  pop     rdi
0x180008449  retn
```
