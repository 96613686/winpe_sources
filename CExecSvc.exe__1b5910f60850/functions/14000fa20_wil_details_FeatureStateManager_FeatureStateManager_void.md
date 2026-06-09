# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x14000fa20`
- end: `0x14000fbfb`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `475`
- prototype: `void __fastcall(wil::details::FeatureStateManager *this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400233f0`

## callees

- `0x14000f948`
- `0x14000fa20`
- `0x140011f4c`
- `0x1400126d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000fb32`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000fb73`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000fb32`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000fb73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000faec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000fb29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000fb69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000faec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000fb29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000fb69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000fade`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000fb1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000fb5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000fade`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000fb1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000fb5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fa3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fa87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fa3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fa87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000fa70`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000fab9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000fa70`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000fab9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000fa51`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000fa9a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000fb8d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000fbbe`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000fa51`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000fa9a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000fb8d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000fbbe`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000fa68`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000fab1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000fba4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000fbd5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000fa68`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000fab1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000fba4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000fbd5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000fa5f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000faa8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000fb9b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000fbcc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000fa5f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000faa8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000fb9b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000fbcc`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(
        wil::details::FeatureStateManager *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *a2)
{
  struct _TP_TIMER *v3; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *v5; // rsi
  DWORD v6; // ebx
  void *v7; // rbx
  HANDLE ProcessHeap; // rax
  wil::details *v9; // rcx
  void *v10; // rsi
  HANDLE v11; // rax
  void *v12; // rsi
  HANDLE v13; // rax
  struct _TP_TIMER *v14; // rbx
  struct _TP_TIMER *v15; // rbx
  void *v16; // rcx

  *(_BYTE *)this = 0;
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v3 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v3, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v3, 1);
    CloseThreadpoolTimer(v3);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 6) = 0;
  v5 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v5 )
  {
    v6 = GetLastError();
    SetThreadpoolTimer(v5, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v5, 1);
    CloseThreadpoolTimer(v5);
    SetLastError(v6);
  }
  *((_QWORD *)this + 7) = 0;
  v7 = (void *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
  }
  v9 = (wil::details *)*((_QWORD *)this + 28);
  if ( v9 )
    wil::details::UnsubscribeProcessWideUsageFlush(v9, a2);
  v10 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v10 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v10);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((__int64 *)this + 18);
  v12 = (void *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v12 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v12);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v14 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v14 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 7), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v14, 1);
    CloseThreadpoolTimer(v14);
  }
  v15 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v15 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 6), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v15, 1);
    CloseThreadpoolTimer(v15);
  }
  v16 = (void *)*((_QWORD *)this + 2);
  if ( v16 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v16);
}

```

## disassembly

```asm
0x14000fa20  mov     [rsp+arg_0], rbx
0x14000fa25  mov     [rsp+arg_8], rsi
0x14000fa2a  push    rdi
0x14000fa2b  sub     rsp, 20h
0x14000fa2f  mov     rdi, rcx
0x14000fa32  mov     byte ptr [rcx], 0
0x14000fa35  mov     rsi, [rcx+30h]
0x14000fa39  test    rsi, rsi
0x14000fa3c  jz      short loc_14000FA76
0x14000fa3e  call    cs:__imp_GetLastError
0x14000fa44  mov     ebx, eax
0x14000fa46  xor     r9d, r9d; msWindowLength
0x14000fa49  xor     r8d, r8d; msPeriod
0x14000fa4c  xor     edx, edx; pftDueTime
0x14000fa4e  mov     rcx, rsi; pti
0x14000fa51  call    cs:__imp_SetThreadpoolTimer
0x14000fa57  mov     edx, 1; fCancelPendingCallbacks
0x14000fa5c  mov     rcx, rsi; pti
0x14000fa5f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000fa65  mov     rcx, rsi; pti
0x14000fa68  call    cs:__imp_CloseThreadpoolTimer
0x14000fa6e  mov     ecx, ebx; dwErrCode
0x14000fa70  call    cs:__imp_SetLastError
0x14000fa76  mov     qword ptr [rdi+30h], 0
0x14000fa7e  mov     rsi, [rdi+38h]
0x14000fa82  test    rsi, rsi
0x14000fa85  jz      short loc_14000FABF
0x14000fa87  call    cs:__imp_GetLastError
0x14000fa8d  mov     ebx, eax
0x14000fa8f  xor     r9d, r9d; msWindowLength
0x14000fa92  xor     r8d, r8d; msPeriod
0x14000fa95  xor     edx, edx; pftDueTime
0x14000fa97  mov     rcx, rsi; pti
0x14000fa9a  call    cs:__imp_SetThreadpoolTimer
0x14000faa0  mov     edx, 1; fCancelPendingCallbacks
0x14000faa5  mov     rcx, rsi; pti
0x14000faa8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000faae  mov     rcx, rsi; pti
0x14000fab1  call    cs:__imp_CloseThreadpoolTimer
0x14000fab7  mov     ecx, ebx; dwErrCode
0x14000fab9  call    cs:__imp_SetLastError
0x14000fabf  mov     qword ptr [rdi+38h], 0
0x14000fac7  mov     rbx, [rdi+100h]
0x14000face  mov     qword ptr [rdi+100h], 0
0x14000fad9  test    rbx, rbx
0x14000fadc  jz      short loc_14000FAF2
0x14000fade  call    cs:__imp_GetProcessHeap
0x14000fae4  mov     rcx, rax; hHeap
0x14000fae7  mov     r8, rbx; lpMem
0x14000faea  xor     edx, edx; dwFlags
0x14000faec  call    cs:__imp_HeapFree
0x14000faf2  mov     rcx, [rdi+0E0h]; this
0x14000faf9  test    rcx, rcx
0x14000fafc  jz      short loc_14000FB03
0x14000fafe  call    ?UnsubscribeProcessWideUsageFlush@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::UnsubscribeProcessWideUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x14000fb03  lea     rbx, [rdi+98h]
0x14000fb0a  mov     rsi, [rbx+40h]
0x14000fb0e  mov     qword ptr [rbx+40h], 0
0x14000fb16  test    rsi, rsi
0x14000fb19  jz      short loc_14000FB2F
0x14000fb1b  call    cs:__imp_GetProcessHeap
0x14000fb21  mov     rcx, rax; hHeap
0x14000fb24  mov     r8, rsi; lpMem
0x14000fb27  xor     edx, edx; dwFlags
0x14000fb29  call    cs:__imp_HeapFree
0x14000fb2f  mov     rcx, rbx; lpCriticalSection
0x14000fb32  call    cs:__imp_DeleteCriticalSection
0x14000fb38  lea     rcx, [rdi+90h]
0x14000fb3f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14000fb44  mov     rsi, [rdi+88h]
0x14000fb4b  mov     qword ptr [rdi+88h], 0
0x14000fb56  test    rsi, rsi
0x14000fb59  jz      short loc_14000FB6F
0x14000fb5b  call    cs:__imp_GetProcessHeap
0x14000fb61  mov     rcx, rax; hHeap
0x14000fb64  mov     r8, rsi; lpMem
0x14000fb67  xor     edx, edx; dwFlags
0x14000fb69  call    cs:__imp_HeapFree
0x14000fb6f  lea     rcx, [rdi+48h]; lpCriticalSection
0x14000fb73  call    cs:__imp_DeleteCriticalSection
0x14000fb79  mov     rbx, [rdi+38h]
0x14000fb7d  test    rbx, rbx
0x14000fb80  jz      short loc_14000FBAA
0x14000fb82  xor     r9d, r9d; msWindowLength
0x14000fb85  xor     r8d, r8d; msPeriod
0x14000fb88  xor     edx, edx; pftDueTime
0x14000fb8a  mov     rcx, rbx; pti
0x14000fb8d  call    cs:__imp_SetThreadpoolTimer
0x14000fb93  mov     edx, 1; fCancelPendingCallbacks
0x14000fb98  mov     rcx, rbx; pti
0x14000fb9b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000fba1  mov     rcx, rbx; pti
0x14000fba4  call    cs:__imp_CloseThreadpoolTimer
0x14000fbaa  mov     rbx, [rdi+30h]
0x14000fbae  test    rbx, rbx
0x14000fbb1  jz      short loc_14000FBDC
0x14000fbb3  xor     r9d, r9d; msWindowLength
0x14000fbb6  xor     r8d, r8d; msPeriod
0x14000fbb9  xor     edx, edx; pftDueTime
0x14000fbbb  mov     rcx, rbx; pti
0x14000fbbe  call    cs:__imp_SetThreadpoolTimer
0x14000fbc4  mov     edx, 1; fCancelPendingCallbacks
0x14000fbc9  mov     rcx, rbx; pti
0x14000fbcc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000fbd2  mov     rcx, rbx; pti
0x14000fbd5  call    cs:__imp_CloseThreadpoolTimer
0x14000fbdb  nop
0x14000fbdc  mov     rcx, [rdi+10h]; lpMem
0x14000fbe0  test    rcx, rcx
0x14000fbe3  jz      short loc_14000FBEB
0x14000fbe5  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x14000fbea  nop
0x14000fbeb  mov     rbx, [rsp+28h+arg_0]
0x14000fbf0  mov     rsi, [rsp+28h+arg_8]
0x14000fbf5  add     rsp, 20h
0x14000fbf9  pop     rdi
0x14000fbfa  retn
```
