# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180008840`
- end: `0x180008a2e`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180023af0`

## callees

- `0x18000852c`
- `0x180008840`
- `0x18000b75c`
- `0x18000bf6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008965`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800089a6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008965`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800089a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000894e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000898e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000894e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000898e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000890c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000895c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000899c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000890c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000895c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000899c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000885e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000885e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008890`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800088d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008890`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800088d9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000887f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800088c8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800089ce`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800089ff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000887f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800088c8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800089ce`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800089ff`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008871`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800088ba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800089c0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800089f1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008871`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800088ba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800089c0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800089f1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008888`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800088d1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800089d7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008a08`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008888`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800088d1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800089d7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008a08`

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
  if ( v8 && qword_180030078 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180030078[25], qword_180030078, v8);
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
0x180008840  mov     [rsp+arg_0], rbx
0x180008845  mov     [rsp+arg_8], rsi
0x18000884a  push    rdi
0x18000884b  sub     rsp, 20h
0x18000884f  mov     rdi, rcx
0x180008852  mov     byte ptr [rcx], 0
0x180008855  mov     rsi, [rcx+30h]
0x180008859  test    rsi, rsi
0x18000885c  jz      short loc_180008896
0x18000885e  call    cs:__imp_GetLastError
0x180008864  mov     ebx, eax
0x180008866  xor     r9d, r9d; msWindowLength
0x180008869  xor     r8d, r8d; msPeriod
0x18000886c  xor     edx, edx; pftDueTime
0x18000886e  mov     rcx, rsi; pti
0x180008871  call    cs:__imp_SetThreadpoolTimer
0x180008877  mov     edx, 1; fCancelPendingCallbacks
0x18000887c  mov     rcx, rsi; pti
0x18000887f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008885  mov     rcx, rsi; pti
0x180008888  call    cs:__imp_CloseThreadpoolTimer
0x18000888e  mov     ecx, ebx; dwErrCode
0x180008890  call    cs:__imp_SetLastError
0x180008896  mov     qword ptr [rdi+30h], 0
0x18000889e  mov     rsi, [rdi+38h]
0x1800088a2  test    rsi, rsi
0x1800088a5  jz      short loc_1800088DF
0x1800088a7  call    cs:__imp_GetLastError
0x1800088ad  mov     ebx, eax
0x1800088af  xor     r9d, r9d; msWindowLength
0x1800088b2  xor     r8d, r8d; msPeriod
0x1800088b5  xor     edx, edx; pftDueTime
0x1800088b7  mov     rcx, rsi; pti
0x1800088ba  call    cs:__imp_SetThreadpoolTimer
0x1800088c0  mov     edx, 1; fCancelPendingCallbacks
0x1800088c5  mov     rcx, rsi; pti
0x1800088c8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800088ce  mov     rcx, rsi; pti
0x1800088d1  call    cs:__imp_CloseThreadpoolTimer
0x1800088d7  mov     ecx, ebx; dwErrCode
0x1800088d9  call    cs:__imp_SetLastError
0x1800088df  mov     qword ptr [rdi+38h], 0
0x1800088e7  mov     rbx, [rdi+100h]
0x1800088ee  mov     qword ptr [rdi+100h], 0
0x1800088f9  test    rbx, rbx
0x1800088fc  jz      short loc_180008912
0x1800088fe  call    cs:__imp_GetProcessHeap
0x180008904  mov     rcx, rax; hHeap
0x180008907  mov     r8, rbx; lpMem
0x18000890a  xor     edx, edx; dwFlags
0x18000890c  call    cs:__imp_HeapFree
0x180008912  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180008919  test    r8, r8
0x18000891c  jz      short loc_180008936
0x18000891e  mov     rdx, cs:qword_180030078; SRWLock
0x180008925  test    rdx, rdx
0x180008928  jz      short loc_180008936
0x18000892a  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180008931  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180008936  lea     rbx, [rdi+98h]
0x18000893d  mov     rsi, [rbx+40h]
0x180008941  mov     qword ptr [rbx+40h], 0
0x180008949  test    rsi, rsi
0x18000894c  jz      short loc_180008962
0x18000894e  call    cs:__imp_GetProcessHeap
0x180008954  mov     rcx, rax; hHeap
0x180008957  mov     r8, rsi; lpMem
0x18000895a  xor     edx, edx; dwFlags
0x18000895c  call    cs:__imp_HeapFree
0x180008962  mov     rcx, rbx; lpCriticalSection
0x180008965  call    cs:__imp_DeleteCriticalSection
0x18000896b  lea     rcx, [rdi+90h]
0x180008972  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180008977  mov     rsi, [rdi+88h]
0x18000897e  mov     qword ptr [rdi+88h], 0
0x180008989  test    rsi, rsi
0x18000898c  jz      short loc_1800089A2
0x18000898e  call    cs:__imp_GetProcessHeap
0x180008994  mov     rcx, rax; hHeap
0x180008997  mov     r8, rsi; lpMem
0x18000899a  xor     edx, edx; dwFlags
0x18000899c  call    cs:__imp_HeapFree
0x1800089a2  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800089a6  call    cs:__imp_DeleteCriticalSection
0x1800089ac  mov     rbx, [rdi+38h]
0x1800089b0  test    rbx, rbx
0x1800089b3  jz      short loc_1800089DD
0x1800089b5  xor     r9d, r9d; msWindowLength
0x1800089b8  xor     r8d, r8d; msPeriod
0x1800089bb  xor     edx, edx; pftDueTime
0x1800089bd  mov     rcx, rbx; pti
0x1800089c0  call    cs:__imp_SetThreadpoolTimer
0x1800089c6  mov     edx, 1; fCancelPendingCallbacks
0x1800089cb  mov     rcx, rbx; pti
0x1800089ce  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800089d4  mov     rcx, rbx; pti
0x1800089d7  call    cs:__imp_CloseThreadpoolTimer
0x1800089dd  mov     rbx, [rdi+30h]
0x1800089e1  test    rbx, rbx
0x1800089e4  jz      short loc_180008A0F
0x1800089e6  xor     r9d, r9d; msWindowLength
0x1800089e9  xor     r8d, r8d; msPeriod
0x1800089ec  xor     edx, edx; pftDueTime
0x1800089ee  mov     rcx, rbx; pti
0x1800089f1  call    cs:__imp_SetThreadpoolTimer
0x1800089f7  mov     edx, 1; fCancelPendingCallbacks
0x1800089fc  mov     rcx, rbx; pti
0x1800089ff  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008a05  mov     rcx, rbx; pti
0x180008a08  call    cs:__imp_CloseThreadpoolTimer
0x180008a0e  nop
0x180008a0f  mov     rcx, [rdi+10h]; lpMem
0x180008a13  test    rcx, rcx
0x180008a16  jz      short loc_180008A1E
0x180008a18  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180008a1d  nop
0x180008a1e  mov     rbx, [rsp+28h+arg_0]
0x180008a23  mov     rsi, [rsp+28h+arg_8]
0x180008a28  add     rsp, 20h
0x180008a2c  pop     rdi
0x180008a2d  retn
```
