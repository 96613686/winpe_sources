# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800086a4`
- end: `0x180008892`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800e9f90`

## callees

- `0x1800083b8`
- `0x1800086a4`
- `0x18000c7a0`
- `0x18000df00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800087c9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000880a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800087c9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000880a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008762`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800087b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800087f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008762`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800087b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800087f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008770`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800087c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008800`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008770`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800087c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008800`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800086f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000873d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800086f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000873d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000870b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000870b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800086d5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000871e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008824`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008855`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800086d5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000871e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008824`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008855`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800086ec`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008735`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000883b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000886c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800086ec`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008735`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000883b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000886c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800086e3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000872c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008832`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008863`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800086e3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000872c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008832`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008863`

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
  if ( v8 && qword_180119BD8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180119BD8[25], qword_180119BD8, v8);
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
0x1800086a4  mov     [rsp+arg_0], rbx
0x1800086a9  mov     [rsp+arg_8], rsi
0x1800086ae  push    rdi
0x1800086af  sub     rsp, 20h
0x1800086b3  mov     rdi, rcx
0x1800086b6  mov     byte ptr [rcx], 0
0x1800086b9  mov     rsi, [rcx+30h]
0x1800086bd  test    rsi, rsi
0x1800086c0  jz      short loc_1800086FA
0x1800086c2  call    cs:__imp_GetLastError
0x1800086c8  mov     ebx, eax
0x1800086ca  xor     r9d, r9d; msWindowLength
0x1800086cd  xor     r8d, r8d; msPeriod
0x1800086d0  xor     edx, edx; pftDueTime
0x1800086d2  mov     rcx, rsi; pti
0x1800086d5  call    cs:__imp_SetThreadpoolTimer
0x1800086db  mov     edx, 1; fCancelPendingCallbacks
0x1800086e0  mov     rcx, rsi; pti
0x1800086e3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800086e9  mov     rcx, rsi; pti
0x1800086ec  call    cs:__imp_CloseThreadpoolTimer
0x1800086f2  mov     ecx, ebx; dwErrCode
0x1800086f4  call    cs:__imp_SetLastError
0x1800086fa  mov     qword ptr [rdi+30h], 0
0x180008702  mov     rsi, [rdi+38h]
0x180008706  test    rsi, rsi
0x180008709  jz      short loc_180008743
0x18000870b  call    cs:__imp_GetLastError
0x180008711  mov     ebx, eax
0x180008713  xor     r9d, r9d; msWindowLength
0x180008716  xor     r8d, r8d; msPeriod
0x180008719  xor     edx, edx; pftDueTime
0x18000871b  mov     rcx, rsi; pti
0x18000871e  call    cs:__imp_SetThreadpoolTimer
0x180008724  mov     edx, 1; fCancelPendingCallbacks
0x180008729  mov     rcx, rsi; pti
0x18000872c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008732  mov     rcx, rsi; pti
0x180008735  call    cs:__imp_CloseThreadpoolTimer
0x18000873b  mov     ecx, ebx; dwErrCode
0x18000873d  call    cs:__imp_SetLastError
0x180008743  mov     qword ptr [rdi+38h], 0
0x18000874b  mov     rbx, [rdi+100h]
0x180008752  mov     qword ptr [rdi+100h], 0
0x18000875d  test    rbx, rbx
0x180008760  jz      short loc_180008776
0x180008762  call    cs:__imp_GetProcessHeap
0x180008768  mov     rcx, rax; hHeap
0x18000876b  mov     r8, rbx; lpMem
0x18000876e  xor     edx, edx; dwFlags
0x180008770  call    cs:__imp_HeapFree
0x180008776  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18000877d  test    r8, r8
0x180008780  jz      short loc_18000879A
0x180008782  mov     rdx, cs:qword_180119BD8; SRWLock
0x180008789  test    rdx, rdx
0x18000878c  jz      short loc_18000879A
0x18000878e  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180008795  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000879a  lea     rbx, [rdi+98h]
0x1800087a1  mov     rsi, [rbx+40h]
0x1800087a5  mov     qword ptr [rbx+40h], 0
0x1800087ad  test    rsi, rsi
0x1800087b0  jz      short loc_1800087C6
0x1800087b2  call    cs:__imp_GetProcessHeap
0x1800087b8  mov     rcx, rax; hHeap
0x1800087bb  mov     r8, rsi; lpMem
0x1800087be  xor     edx, edx; dwFlags
0x1800087c0  call    cs:__imp_HeapFree
0x1800087c6  mov     rcx, rbx; lpCriticalSection
0x1800087c9  call    cs:__imp_DeleteCriticalSection
0x1800087cf  lea     rcx, [rdi+90h]
0x1800087d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800087db  mov     rsi, [rdi+88h]
0x1800087e2  mov     qword ptr [rdi+88h], 0
0x1800087ed  test    rsi, rsi
0x1800087f0  jz      short loc_180008806
0x1800087f2  call    cs:__imp_GetProcessHeap
0x1800087f8  mov     rcx, rax; hHeap
0x1800087fb  mov     r8, rsi; lpMem
0x1800087fe  xor     edx, edx; dwFlags
0x180008800  call    cs:__imp_HeapFree
0x180008806  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000880a  call    cs:__imp_DeleteCriticalSection
0x180008810  mov     rbx, [rdi+38h]
0x180008814  test    rbx, rbx
0x180008817  jz      short loc_180008841
0x180008819  xor     r9d, r9d; msWindowLength
0x18000881c  xor     r8d, r8d; msPeriod
0x18000881f  xor     edx, edx; pftDueTime
0x180008821  mov     rcx, rbx; pti
0x180008824  call    cs:__imp_SetThreadpoolTimer
0x18000882a  mov     edx, 1; fCancelPendingCallbacks
0x18000882f  mov     rcx, rbx; pti
0x180008832  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008838  mov     rcx, rbx; pti
0x18000883b  call    cs:__imp_CloseThreadpoolTimer
0x180008841  mov     rbx, [rdi+30h]
0x180008845  test    rbx, rbx
0x180008848  jz      short loc_180008873
0x18000884a  xor     r9d, r9d; msWindowLength
0x18000884d  xor     r8d, r8d; msPeriod
0x180008850  xor     edx, edx; pftDueTime
0x180008852  mov     rcx, rbx; pti
0x180008855  call    cs:__imp_SetThreadpoolTimer
0x18000885b  mov     edx, 1; fCancelPendingCallbacks
0x180008860  mov     rcx, rbx; pti
0x180008863  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008869  mov     rcx, rbx; pti
0x18000886c  call    cs:__imp_CloseThreadpoolTimer
0x180008872  nop
0x180008873  mov     rcx, [rdi+10h]; lpMem
0x180008877  test    rcx, rcx
0x18000887a  jz      short loc_180008882
0x18000887c  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180008881  nop
0x180008882  mov     rbx, [rsp+28h+arg_0]
0x180008887  mov     rsi, [rsp+28h+arg_8]
0x18000888c  add     rsp, 20h
0x180008890  pop     rdi
0x180008891  retn
```
