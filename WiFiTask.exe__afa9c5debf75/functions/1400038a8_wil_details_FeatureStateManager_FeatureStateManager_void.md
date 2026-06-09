# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1400038a8`
- end: `0x140003a96`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400113d0`

## callees

- `0x140003528`
- `0x1400038a8`
- `0x140009340`
- `0x14000aee0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400038e7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140003930`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140003a36`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140003a67`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400038e7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140003930`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140003a36`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140003a67`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400038d9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003922`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003a28`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003a59`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400038d9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003922`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003a28`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003a59`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400038f0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140003939`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140003a3f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140003a70`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400038f0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140003939`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140003a3f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140003a70`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400039cd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140003a0e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400039cd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140003a0e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003974`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400039c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003a04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003974`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400039c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003a04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003966`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400039b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400039f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003966`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400039b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400039f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400038f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003941`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400038f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400038c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000390f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400038c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000390f`

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
  if ( v8 && qword_1400190A8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1400190A8[25], qword_1400190A8, v8);
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
0x1400038a8  mov     [rsp+arg_0], rbx
0x1400038ad  mov     [rsp+arg_8], rsi
0x1400038b2  push    rdi
0x1400038b3  sub     rsp, 20h
0x1400038b7  mov     rdi, rcx
0x1400038ba  mov     byte ptr [rcx], 0
0x1400038bd  mov     rsi, [rcx+30h]
0x1400038c1  test    rsi, rsi
0x1400038c4  jz      short loc_1400038FE
0x1400038c6  call    cs:__imp_GetLastError
0x1400038cc  mov     ebx, eax
0x1400038ce  xor     r9d, r9d; msWindowLength
0x1400038d1  xor     r8d, r8d; msPeriod
0x1400038d4  xor     edx, edx; pftDueTime
0x1400038d6  mov     rcx, rsi; pti
0x1400038d9  call    cs:__imp_SetThreadpoolTimer
0x1400038df  mov     edx, 1; fCancelPendingCallbacks
0x1400038e4  mov     rcx, rsi; pti
0x1400038e7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400038ed  mov     rcx, rsi; pti
0x1400038f0  call    cs:__imp_CloseThreadpoolTimer
0x1400038f6  mov     ecx, ebx; dwErrCode
0x1400038f8  call    cs:__imp_SetLastError
0x1400038fe  mov     qword ptr [rdi+30h], 0
0x140003906  mov     rsi, [rdi+38h]
0x14000390a  test    rsi, rsi
0x14000390d  jz      short loc_140003947
0x14000390f  call    cs:__imp_GetLastError
0x140003915  mov     ebx, eax
0x140003917  xor     r9d, r9d; msWindowLength
0x14000391a  xor     r8d, r8d; msPeriod
0x14000391d  xor     edx, edx; pftDueTime
0x14000391f  mov     rcx, rsi; pti
0x140003922  call    cs:__imp_SetThreadpoolTimer
0x140003928  mov     edx, 1; fCancelPendingCallbacks
0x14000392d  mov     rcx, rsi; pti
0x140003930  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140003936  mov     rcx, rsi; pti
0x140003939  call    cs:__imp_CloseThreadpoolTimer
0x14000393f  mov     ecx, ebx; dwErrCode
0x140003941  call    cs:__imp_SetLastError
0x140003947  mov     qword ptr [rdi+38h], 0
0x14000394f  mov     rbx, [rdi+100h]
0x140003956  mov     qword ptr [rdi+100h], 0
0x140003961  test    rbx, rbx
0x140003964  jz      short loc_14000397A
0x140003966  call    cs:__imp_GetProcessHeap
0x14000396c  mov     rcx, rax; hHeap
0x14000396f  mov     r8, rbx; lpMem
0x140003972  xor     edx, edx; dwFlags
0x140003974  call    cs:__imp_HeapFree
0x14000397a  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x140003981  test    r8, r8
0x140003984  jz      short loc_14000399E
0x140003986  mov     rdx, cs:qword_1400190A8; SRWLock
0x14000398d  test    rdx, rdx
0x140003990  jz      short loc_14000399E
0x140003992  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140003999  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x14000399e  lea     rbx, [rdi+98h]
0x1400039a5  mov     rsi, [rbx+40h]
0x1400039a9  mov     qword ptr [rbx+40h], 0
0x1400039b1  test    rsi, rsi
0x1400039b4  jz      short loc_1400039CA
0x1400039b6  call    cs:__imp_GetProcessHeap
0x1400039bc  mov     rcx, rax; hHeap
0x1400039bf  mov     r8, rsi; lpMem
0x1400039c2  xor     edx, edx; dwFlags
0x1400039c4  call    cs:__imp_HeapFree
0x1400039ca  mov     rcx, rbx; lpCriticalSection
0x1400039cd  call    cs:__imp_DeleteCriticalSection
0x1400039d3  lea     rcx, [rdi+90h]
0x1400039da  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400039df  mov     rsi, [rdi+88h]
0x1400039e6  mov     qword ptr [rdi+88h], 0
0x1400039f1  test    rsi, rsi
0x1400039f4  jz      short loc_140003A0A
0x1400039f6  call    cs:__imp_GetProcessHeap
0x1400039fc  mov     rcx, rax; hHeap
0x1400039ff  mov     r8, rsi; lpMem
0x140003a02  xor     edx, edx; dwFlags
0x140003a04  call    cs:__imp_HeapFree
0x140003a0a  lea     rcx, [rdi+48h]; lpCriticalSection
0x140003a0e  call    cs:__imp_DeleteCriticalSection
0x140003a14  mov     rbx, [rdi+38h]
0x140003a18  test    rbx, rbx
0x140003a1b  jz      short loc_140003A45
0x140003a1d  xor     r9d, r9d; msWindowLength
0x140003a20  xor     r8d, r8d; msPeriod
0x140003a23  xor     edx, edx; pftDueTime
0x140003a25  mov     rcx, rbx; pti
0x140003a28  call    cs:__imp_SetThreadpoolTimer
0x140003a2e  mov     edx, 1; fCancelPendingCallbacks
0x140003a33  mov     rcx, rbx; pti
0x140003a36  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140003a3c  mov     rcx, rbx; pti
0x140003a3f  call    cs:__imp_CloseThreadpoolTimer
0x140003a45  mov     rbx, [rdi+30h]
0x140003a49  test    rbx, rbx
0x140003a4c  jz      short loc_140003A77
0x140003a4e  xor     r9d, r9d; msWindowLength
0x140003a51  xor     r8d, r8d; msPeriod
0x140003a54  xor     edx, edx; pftDueTime
0x140003a56  mov     rcx, rbx; pti
0x140003a59  call    cs:__imp_SetThreadpoolTimer
0x140003a5f  mov     edx, 1; fCancelPendingCallbacks
0x140003a64  mov     rcx, rbx; pti
0x140003a67  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140003a6d  mov     rcx, rbx; pti
0x140003a70  call    cs:__imp_CloseThreadpoolTimer
0x140003a76  nop
0x140003a77  mov     rcx, [rdi+10h]; lpMem
0x140003a7b  test    rcx, rcx
0x140003a7e  jz      short loc_140003A86
0x140003a80  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140003a85  nop
0x140003a86  mov     rbx, [rsp+28h+arg_0]
0x140003a8b  mov     rsi, [rsp+28h+arg_8]
0x140003a90  add     rsp, 20h
0x140003a94  pop     rdi
0x140003a95  retn
```
