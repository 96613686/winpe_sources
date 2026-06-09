# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180014814`
- end: `0x180014a02`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002b230`

## callees

- `0x1800146d0`
- `0x180014814`
- `0x180017fe0`
- `0x180019148`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014832`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001487b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014832`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001487b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014864`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800148ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014864`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800148ad`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014939`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001497a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014939`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001497a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800148e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014930`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014970`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800148e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014930`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014970`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800148d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014922`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014962`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800148d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014922`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014962`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001485c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800148a5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800149ab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800149dc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001485c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800148a5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800149ab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800149dc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014853`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001489c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800149a2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800149d3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014853`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001489c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800149a2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800149d3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014845`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001488e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014994`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800149c5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014845`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001488e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014994`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800149c5`

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
  if ( v8 && qword_1800373F8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800373F8[25], qword_1800373F8, v8);
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
0x180014814  mov     [rsp+arg_0], rbx
0x180014819  mov     [rsp+arg_8], rsi
0x18001481e  push    rdi
0x18001481f  sub     rsp, 20h
0x180014823  mov     rdi, rcx
0x180014826  mov     byte ptr [rcx], 0
0x180014829  mov     rsi, [rcx+30h]
0x18001482d  test    rsi, rsi
0x180014830  jz      short loc_18001486A
0x180014832  call    cs:__imp_GetLastError
0x180014838  mov     ebx, eax
0x18001483a  xor     r9d, r9d; msWindowLength
0x18001483d  xor     r8d, r8d; msPeriod
0x180014840  xor     edx, edx; pftDueTime
0x180014842  mov     rcx, rsi; pti
0x180014845  call    cs:__imp_SetThreadpoolTimer
0x18001484b  mov     edx, 1; fCancelPendingCallbacks
0x180014850  mov     rcx, rsi; pti
0x180014853  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180014859  mov     rcx, rsi; pti
0x18001485c  call    cs:__imp_CloseThreadpoolTimer
0x180014862  mov     ecx, ebx; dwErrCode
0x180014864  call    cs:__imp_SetLastError
0x18001486a  mov     qword ptr [rdi+30h], 0
0x180014872  mov     rsi, [rdi+38h]
0x180014876  test    rsi, rsi
0x180014879  jz      short loc_1800148B3
0x18001487b  call    cs:__imp_GetLastError
0x180014881  mov     ebx, eax
0x180014883  xor     r9d, r9d; msWindowLength
0x180014886  xor     r8d, r8d; msPeriod
0x180014889  xor     edx, edx; pftDueTime
0x18001488b  mov     rcx, rsi; pti
0x18001488e  call    cs:__imp_SetThreadpoolTimer
0x180014894  mov     edx, 1; fCancelPendingCallbacks
0x180014899  mov     rcx, rsi; pti
0x18001489c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800148a2  mov     rcx, rsi; pti
0x1800148a5  call    cs:__imp_CloseThreadpoolTimer
0x1800148ab  mov     ecx, ebx; dwErrCode
0x1800148ad  call    cs:__imp_SetLastError
0x1800148b3  mov     qword ptr [rdi+38h], 0
0x1800148bb  mov     rbx, [rdi+100h]
0x1800148c2  mov     qword ptr [rdi+100h], 0
0x1800148cd  test    rbx, rbx
0x1800148d0  jz      short loc_1800148E6
0x1800148d2  call    cs:__imp_GetProcessHeap
0x1800148d8  mov     rcx, rax; hHeap
0x1800148db  mov     r8, rbx; lpMem
0x1800148de  xor     edx, edx; dwFlags
0x1800148e0  call    cs:__imp_HeapFree
0x1800148e6  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800148ed  test    r8, r8
0x1800148f0  jz      short loc_18001490A
0x1800148f2  mov     rdx, cs:qword_1800373F8; SRWLock
0x1800148f9  test    rdx, rdx
0x1800148fc  jz      short loc_18001490A
0x1800148fe  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180014905  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18001490a  lea     rbx, [rdi+98h]
0x180014911  mov     rsi, [rbx+40h]
0x180014915  mov     qword ptr [rbx+40h], 0
0x18001491d  test    rsi, rsi
0x180014920  jz      short loc_180014936
0x180014922  call    cs:__imp_GetProcessHeap
0x180014928  mov     rcx, rax; hHeap
0x18001492b  mov     r8, rsi; lpMem
0x18001492e  xor     edx, edx; dwFlags
0x180014930  call    cs:__imp_HeapFree
0x180014936  mov     rcx, rbx; lpCriticalSection
0x180014939  call    cs:__imp_DeleteCriticalSection
0x18001493f  lea     rcx, [rdi+90h]
0x180014946  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001494b  mov     rsi, [rdi+88h]
0x180014952  mov     qword ptr [rdi+88h], 0
0x18001495d  test    rsi, rsi
0x180014960  jz      short loc_180014976
0x180014962  call    cs:__imp_GetProcessHeap
0x180014968  mov     rcx, rax; hHeap
0x18001496b  mov     r8, rsi; lpMem
0x18001496e  xor     edx, edx; dwFlags
0x180014970  call    cs:__imp_HeapFree
0x180014976  lea     rcx, [rdi+48h]; lpCriticalSection
0x18001497a  call    cs:__imp_DeleteCriticalSection
0x180014980  mov     rbx, [rdi+38h]
0x180014984  test    rbx, rbx
0x180014987  jz      short loc_1800149B1
0x180014989  xor     r9d, r9d; msWindowLength
0x18001498c  xor     r8d, r8d; msPeriod
0x18001498f  xor     edx, edx; pftDueTime
0x180014991  mov     rcx, rbx; pti
0x180014994  call    cs:__imp_SetThreadpoolTimer
0x18001499a  mov     edx, 1; fCancelPendingCallbacks
0x18001499f  mov     rcx, rbx; pti
0x1800149a2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800149a8  mov     rcx, rbx; pti
0x1800149ab  call    cs:__imp_CloseThreadpoolTimer
0x1800149b1  mov     rbx, [rdi+30h]
0x1800149b5  test    rbx, rbx
0x1800149b8  jz      short loc_1800149E3
0x1800149ba  xor     r9d, r9d; msWindowLength
0x1800149bd  xor     r8d, r8d; msPeriod
0x1800149c0  xor     edx, edx; pftDueTime
0x1800149c2  mov     rcx, rbx; pti
0x1800149c5  call    cs:__imp_SetThreadpoolTimer
0x1800149cb  mov     edx, 1; fCancelPendingCallbacks
0x1800149d0  mov     rcx, rbx; pti
0x1800149d3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800149d9  mov     rcx, rbx; pti
0x1800149dc  call    cs:__imp_CloseThreadpoolTimer
0x1800149e2  nop
0x1800149e3  mov     rcx, [rdi+10h]; lpMem
0x1800149e7  test    rcx, rcx
0x1800149ea  jz      short loc_1800149F2
0x1800149ec  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800149f1  nop
0x1800149f2  mov     rbx, [rsp+28h+arg_0]
0x1800149f7  mov     rsi, [rsp+28h+arg_8]
0x1800149fc  add     rsp, 20h
0x180014a00  pop     rdi
0x180014a01  retn
```
