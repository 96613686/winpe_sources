# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800039b0`
- end: `0x180003b9e`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180029b70`

## callees

- `0x18000370c`
- `0x1800039b0`
- `0x1800075f0`
- `0x180008990`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003ad5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003b16`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003ad5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003b16`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a7c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003acc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a7c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003acc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a6e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003abe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003afe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a6e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003abe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003afe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003a00`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003a49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003a00`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003a49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a17`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800039e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003a2a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003b30`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003b61`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800039e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003a2a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003b30`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003b61`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800039f8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003a41`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003b47`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003b78`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800039f8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003a41`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003b47`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003b78`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800039ef`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003a38`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003b3e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003b6f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800039ef`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003a38`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003b3e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003b6f`

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
  if ( v8 && qword_180033058 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180033058[25], qword_180033058, v8);
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
0x1800039b0  mov     [rsp+arg_0], rbx
0x1800039b5  mov     [rsp+arg_8], rsi
0x1800039ba  push    rdi
0x1800039bb  sub     rsp, 20h
0x1800039bf  mov     rdi, rcx
0x1800039c2  mov     byte ptr [rcx], 0
0x1800039c5  mov     rsi, [rcx+30h]
0x1800039c9  test    rsi, rsi
0x1800039cc  jz      short loc_180003A06
0x1800039ce  call    cs:__imp_GetLastError
0x1800039d4  mov     ebx, eax
0x1800039d6  xor     r9d, r9d; msWindowLength
0x1800039d9  xor     r8d, r8d; msPeriod
0x1800039dc  xor     edx, edx; pftDueTime
0x1800039de  mov     rcx, rsi; pti
0x1800039e1  call    cs:__imp_SetThreadpoolTimer
0x1800039e7  mov     edx, 1; fCancelPendingCallbacks
0x1800039ec  mov     rcx, rsi; pti
0x1800039ef  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800039f5  mov     rcx, rsi; pti
0x1800039f8  call    cs:__imp_CloseThreadpoolTimer
0x1800039fe  mov     ecx, ebx; dwErrCode
0x180003a00  call    cs:__imp_SetLastError
0x180003a06  mov     qword ptr [rdi+30h], 0
0x180003a0e  mov     rsi, [rdi+38h]
0x180003a12  test    rsi, rsi
0x180003a15  jz      short loc_180003A4F
0x180003a17  call    cs:__imp_GetLastError
0x180003a1d  mov     ebx, eax
0x180003a1f  xor     r9d, r9d; msWindowLength
0x180003a22  xor     r8d, r8d; msPeriod
0x180003a25  xor     edx, edx; pftDueTime
0x180003a27  mov     rcx, rsi; pti
0x180003a2a  call    cs:__imp_SetThreadpoolTimer
0x180003a30  mov     edx, 1; fCancelPendingCallbacks
0x180003a35  mov     rcx, rsi; pti
0x180003a38  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003a3e  mov     rcx, rsi; pti
0x180003a41  call    cs:__imp_CloseThreadpoolTimer
0x180003a47  mov     ecx, ebx; dwErrCode
0x180003a49  call    cs:__imp_SetLastError
0x180003a4f  mov     qword ptr [rdi+38h], 0
0x180003a57  mov     rbx, [rdi+100h]
0x180003a5e  mov     qword ptr [rdi+100h], 0
0x180003a69  test    rbx, rbx
0x180003a6c  jz      short loc_180003A82
0x180003a6e  call    cs:__imp_GetProcessHeap
0x180003a74  mov     rcx, rax; hHeap
0x180003a77  mov     r8, rbx; lpMem
0x180003a7a  xor     edx, edx; dwFlags
0x180003a7c  call    cs:__imp_HeapFree
0x180003a82  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180003a89  test    r8, r8
0x180003a8c  jz      short loc_180003AA6
0x180003a8e  mov     rdx, cs:qword_180033058; SRWLock
0x180003a95  test    rdx, rdx
0x180003a98  jz      short loc_180003AA6
0x180003a9a  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180003aa1  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180003aa6  lea     rbx, [rdi+98h]
0x180003aad  mov     rsi, [rbx+40h]
0x180003ab1  mov     qword ptr [rbx+40h], 0
0x180003ab9  test    rsi, rsi
0x180003abc  jz      short loc_180003AD2
0x180003abe  call    cs:__imp_GetProcessHeap
0x180003ac4  mov     rcx, rax; hHeap
0x180003ac7  mov     r8, rsi; lpMem
0x180003aca  xor     edx, edx; dwFlags
0x180003acc  call    cs:__imp_HeapFree
0x180003ad2  mov     rcx, rbx; lpCriticalSection
0x180003ad5  call    cs:__imp_DeleteCriticalSection
0x180003adb  lea     rcx, [rdi+90h]
0x180003ae2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180003ae7  mov     rsi, [rdi+88h]
0x180003aee  mov     qword ptr [rdi+88h], 0
0x180003af9  test    rsi, rsi
0x180003afc  jz      short loc_180003B12
0x180003afe  call    cs:__imp_GetProcessHeap
0x180003b04  mov     rcx, rax; hHeap
0x180003b07  mov     r8, rsi; lpMem
0x180003b0a  xor     edx, edx; dwFlags
0x180003b0c  call    cs:__imp_HeapFree
0x180003b12  lea     rcx, [rdi+48h]; lpCriticalSection
0x180003b16  call    cs:__imp_DeleteCriticalSection
0x180003b1c  mov     rbx, [rdi+38h]
0x180003b20  test    rbx, rbx
0x180003b23  jz      short loc_180003B4D
0x180003b25  xor     r9d, r9d; msWindowLength
0x180003b28  xor     r8d, r8d; msPeriod
0x180003b2b  xor     edx, edx; pftDueTime
0x180003b2d  mov     rcx, rbx; pti
0x180003b30  call    cs:__imp_SetThreadpoolTimer
0x180003b36  mov     edx, 1; fCancelPendingCallbacks
0x180003b3b  mov     rcx, rbx; pti
0x180003b3e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003b44  mov     rcx, rbx; pti
0x180003b47  call    cs:__imp_CloseThreadpoolTimer
0x180003b4d  mov     rbx, [rdi+30h]
0x180003b51  test    rbx, rbx
0x180003b54  jz      short loc_180003B7F
0x180003b56  xor     r9d, r9d; msWindowLength
0x180003b59  xor     r8d, r8d; msPeriod
0x180003b5c  xor     edx, edx; pftDueTime
0x180003b5e  mov     rcx, rbx; pti
0x180003b61  call    cs:__imp_SetThreadpoolTimer
0x180003b67  mov     edx, 1; fCancelPendingCallbacks
0x180003b6c  mov     rcx, rbx; pti
0x180003b6f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003b75  mov     rcx, rbx; pti
0x180003b78  call    cs:__imp_CloseThreadpoolTimer
0x180003b7e  nop
0x180003b7f  mov     rcx, [rdi+10h]; lpMem
0x180003b83  test    rcx, rcx
0x180003b86  jz      short loc_180003B8E
0x180003b88  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180003b8d  nop
0x180003b8e  mov     rbx, [rsp+28h+arg_0]
0x180003b93  mov     rsi, [rsp+28h+arg_8]
0x180003b98  add     rsp, 20h
0x180003b9c  pop     rdi
0x180003b9d  retn
```
