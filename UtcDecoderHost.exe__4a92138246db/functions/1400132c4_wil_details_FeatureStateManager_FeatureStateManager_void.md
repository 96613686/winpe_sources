# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1400132c4`
- end: `0x1400134b2`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140017cc0`

## callees

- `0x140013034`
- `0x1400132c4`
- `0x140015610`
- `0x140015e2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400133e9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001342a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400133e9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001342a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140013390`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400133e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140013420`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140013390`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400133e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140013420`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013382`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400133d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013412`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013382`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400133d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013412`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140013314`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001335d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140013314`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001335d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400132e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001332b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400132e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001332b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140013303`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14001334c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140013452`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140013483`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140013303`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14001334c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140013452`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140013483`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400132f5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001333e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140013444`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140013475`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400132f5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001333e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140013444`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140013475`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14001330c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140013355`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14001345b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14001348c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14001330c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140013355`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14001345b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14001348c`

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
  if ( v8 && qword_140025098 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_140025098[25], qword_140025098, v8);
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
0x1400132c4  mov     [rsp+arg_0], rbx
0x1400132c9  mov     [rsp+arg_8], rsi
0x1400132ce  push    rdi
0x1400132cf  sub     rsp, 20h
0x1400132d3  mov     rdi, rcx
0x1400132d6  mov     byte ptr [rcx], 0
0x1400132d9  mov     rsi, [rcx+30h]
0x1400132dd  test    rsi, rsi
0x1400132e0  jz      short loc_14001331A
0x1400132e2  call    cs:__imp_GetLastError
0x1400132e8  mov     ebx, eax
0x1400132ea  xor     r9d, r9d; msWindowLength
0x1400132ed  xor     r8d, r8d; msPeriod
0x1400132f0  xor     edx, edx; pftDueTime
0x1400132f2  mov     rcx, rsi; pti
0x1400132f5  call    cs:__imp_SetThreadpoolTimer
0x1400132fb  mov     edx, 1; fCancelPendingCallbacks
0x140013300  mov     rcx, rsi; pti
0x140013303  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140013309  mov     rcx, rsi; pti
0x14001330c  call    cs:__imp_CloseThreadpoolTimer
0x140013312  mov     ecx, ebx; dwErrCode
0x140013314  call    cs:__imp_SetLastError
0x14001331a  mov     qword ptr [rdi+30h], 0
0x140013322  mov     rsi, [rdi+38h]
0x140013326  test    rsi, rsi
0x140013329  jz      short loc_140013363
0x14001332b  call    cs:__imp_GetLastError
0x140013331  mov     ebx, eax
0x140013333  xor     r9d, r9d; msWindowLength
0x140013336  xor     r8d, r8d; msPeriod
0x140013339  xor     edx, edx; pftDueTime
0x14001333b  mov     rcx, rsi; pti
0x14001333e  call    cs:__imp_SetThreadpoolTimer
0x140013344  mov     edx, 1; fCancelPendingCallbacks
0x140013349  mov     rcx, rsi; pti
0x14001334c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140013352  mov     rcx, rsi; pti
0x140013355  call    cs:__imp_CloseThreadpoolTimer
0x14001335b  mov     ecx, ebx; dwErrCode
0x14001335d  call    cs:__imp_SetLastError
0x140013363  mov     qword ptr [rdi+38h], 0
0x14001336b  mov     rbx, [rdi+100h]
0x140013372  mov     qword ptr [rdi+100h], 0
0x14001337d  test    rbx, rbx
0x140013380  jz      short loc_140013396
0x140013382  call    cs:__imp_GetProcessHeap
0x140013388  mov     rcx, rax; hHeap
0x14001338b  mov     r8, rbx; lpMem
0x14001338e  xor     edx, edx; dwFlags
0x140013390  call    cs:__imp_HeapFree
0x140013396  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x14001339d  test    r8, r8
0x1400133a0  jz      short loc_1400133BA
0x1400133a2  mov     rdx, cs:qword_140025098; SRWLock
0x1400133a9  test    rdx, rdx
0x1400133ac  jz      short loc_1400133BA
0x1400133ae  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1400133b5  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1400133ba  lea     rbx, [rdi+98h]
0x1400133c1  mov     rsi, [rbx+40h]
0x1400133c5  mov     qword ptr [rbx+40h], 0
0x1400133cd  test    rsi, rsi
0x1400133d0  jz      short loc_1400133E6
0x1400133d2  call    cs:__imp_GetProcessHeap
0x1400133d8  mov     rcx, rax; hHeap
0x1400133db  mov     r8, rsi; lpMem
0x1400133de  xor     edx, edx; dwFlags
0x1400133e0  call    cs:__imp_HeapFree
0x1400133e6  mov     rcx, rbx; lpCriticalSection
0x1400133e9  call    cs:__imp_DeleteCriticalSection
0x1400133ef  lea     rcx, [rdi+90h]
0x1400133f6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400133fb  mov     rsi, [rdi+88h]
0x140013402  mov     qword ptr [rdi+88h], 0
0x14001340d  test    rsi, rsi
0x140013410  jz      short loc_140013426
0x140013412  call    cs:__imp_GetProcessHeap
0x140013418  mov     rcx, rax; hHeap
0x14001341b  mov     r8, rsi; lpMem
0x14001341e  xor     edx, edx; dwFlags
0x140013420  call    cs:__imp_HeapFree
0x140013426  lea     rcx, [rdi+48h]; lpCriticalSection
0x14001342a  call    cs:__imp_DeleteCriticalSection
0x140013430  mov     rbx, [rdi+38h]
0x140013434  test    rbx, rbx
0x140013437  jz      short loc_140013461
0x140013439  xor     r9d, r9d; msWindowLength
0x14001343c  xor     r8d, r8d; msPeriod
0x14001343f  xor     edx, edx; pftDueTime
0x140013441  mov     rcx, rbx; pti
0x140013444  call    cs:__imp_SetThreadpoolTimer
0x14001344a  mov     edx, 1; fCancelPendingCallbacks
0x14001344f  mov     rcx, rbx; pti
0x140013452  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140013458  mov     rcx, rbx; pti
0x14001345b  call    cs:__imp_CloseThreadpoolTimer
0x140013461  mov     rbx, [rdi+30h]
0x140013465  test    rbx, rbx
0x140013468  jz      short loc_140013493
0x14001346a  xor     r9d, r9d; msWindowLength
0x14001346d  xor     r8d, r8d; msPeriod
0x140013470  xor     edx, edx; pftDueTime
0x140013472  mov     rcx, rbx; pti
0x140013475  call    cs:__imp_SetThreadpoolTimer
0x14001347b  mov     edx, 1; fCancelPendingCallbacks
0x140013480  mov     rcx, rbx; pti
0x140013483  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140013489  mov     rcx, rbx; pti
0x14001348c  call    cs:__imp_CloseThreadpoolTimer
0x140013492  nop
0x140013493  mov     rcx, [rdi+10h]; lpMem
0x140013497  test    rcx, rcx
0x14001349a  jz      short loc_1400134A2
0x14001349c  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1400134a1  nop
0x1400134a2  mov     rbx, [rsp+28h+arg_0]
0x1400134a7  mov     rsi, [rsp+28h+arg_8]
0x1400134ac  add     rsp, 20h
0x1400134b0  pop     rdi
0x1400134b1  retn
```
