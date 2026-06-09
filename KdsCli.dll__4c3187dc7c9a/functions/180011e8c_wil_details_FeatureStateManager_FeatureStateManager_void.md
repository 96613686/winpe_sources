# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180011e8c`
- end: `0x180012078`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001a8a0`

## callees

- `0x180011d48`
- `0x180011e8c`
- `0x180015470`
- `0x180015fec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011edc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011f25`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011edc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011f25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011eaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ef3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011eaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ef3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011fb1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011ff2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011fb1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011ff2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011f58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011fa8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011fe8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011f58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011fa8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011fe8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011f4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011f9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011fda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011f4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011f9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011fda`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011ebd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011f06`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001200c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001203d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011ebd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011f06`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001200c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001203d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011ecb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011f14`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001201a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001204b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011ecb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011f14`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001201a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001204b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011ed4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011f1d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012023`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012054`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011ed4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011f1d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012023`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012054`

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
  if ( v8 && qword_180023068 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180023068[25], qword_180023068, v8);
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
0x180011e8c  mov     [rsp+arg_0], rbx
0x180011e91  mov     [rsp+arg_8], rsi
0x180011e96  push    rdi
0x180011e97  sub     rsp, 20h
0x180011e9b  mov     byte ptr [rcx], 0
0x180011e9e  mov     rdi, rcx
0x180011ea1  mov     rsi, [rcx+30h]
0x180011ea5  test    rsi, rsi
0x180011ea8  jz      short loc_180011EE2
0x180011eaa  call    cs:__imp_GetLastError
0x180011eb0  xor     r9d, r9d; msWindowLength
0x180011eb3  xor     r8d, r8d; msPeriod
0x180011eb6  xor     edx, edx; pftDueTime
0x180011eb8  mov     rcx, rsi; pti
0x180011ebb  mov     ebx, eax
0x180011ebd  call    cs:__imp_SetThreadpoolTimer
0x180011ec3  mov     edx, 1; fCancelPendingCallbacks
0x180011ec8  mov     rcx, rsi; pti
0x180011ecb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180011ed1  mov     rcx, rsi; pti
0x180011ed4  call    cs:__imp_CloseThreadpoolTimer
0x180011eda  mov     ecx, ebx; dwErrCode
0x180011edc  call    cs:__imp_SetLastError
0x180011ee2  mov     qword ptr [rdi+30h], 0
0x180011eea  mov     rsi, [rdi+38h]
0x180011eee  test    rsi, rsi
0x180011ef1  jz      short loc_180011F2B
0x180011ef3  call    cs:__imp_GetLastError
0x180011ef9  xor     r9d, r9d; msWindowLength
0x180011efc  xor     r8d, r8d; msPeriod
0x180011eff  xor     edx, edx; pftDueTime
0x180011f01  mov     rcx, rsi; pti
0x180011f04  mov     ebx, eax
0x180011f06  call    cs:__imp_SetThreadpoolTimer
0x180011f0c  mov     edx, 1; fCancelPendingCallbacks
0x180011f11  mov     rcx, rsi; pti
0x180011f14  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180011f1a  mov     rcx, rsi; pti
0x180011f1d  call    cs:__imp_CloseThreadpoolTimer
0x180011f23  mov     ecx, ebx; dwErrCode
0x180011f25  call    cs:__imp_SetLastError
0x180011f2b  mov     qword ptr [rdi+38h], 0
0x180011f33  mov     rbx, [rdi+100h]
0x180011f3a  mov     qword ptr [rdi+100h], 0
0x180011f45  test    rbx, rbx
0x180011f48  jz      short loc_180011F5E
0x180011f4a  call    cs:__imp_GetProcessHeap
0x180011f50  mov     r8, rbx; lpMem
0x180011f53  xor     edx, edx; dwFlags
0x180011f55  mov     rcx, rax; hHeap
0x180011f58  call    cs:__imp_HeapFree
0x180011f5e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180011f65  test    r8, r8
0x180011f68  jz      short loc_180011F82
0x180011f6a  mov     rdx, cs:qword_180023068; SRWLock
0x180011f71  test    rdx, rdx
0x180011f74  jz      short loc_180011F82
0x180011f76  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180011f7d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180011f82  lea     rbx, [rdi+98h]
0x180011f89  mov     rsi, [rbx+40h]
0x180011f8d  mov     qword ptr [rbx+40h], 0
0x180011f95  test    rsi, rsi
0x180011f98  jz      short loc_180011FAE
0x180011f9a  call    cs:__imp_GetProcessHeap
0x180011fa0  mov     r8, rsi; lpMem
0x180011fa3  xor     edx, edx; dwFlags
0x180011fa5  mov     rcx, rax; hHeap
0x180011fa8  call    cs:__imp_HeapFree
0x180011fae  mov     rcx, rbx; lpCriticalSection
0x180011fb1  call    cs:__imp_DeleteCriticalSection
0x180011fb7  lea     rcx, [rdi+90h]
0x180011fbe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180011fc3  mov     rsi, [rdi+88h]
0x180011fca  mov     qword ptr [rdi+88h], 0
0x180011fd5  test    rsi, rsi
0x180011fd8  jz      short loc_180011FEE
0x180011fda  call    cs:__imp_GetProcessHeap
0x180011fe0  mov     r8, rsi; lpMem
0x180011fe3  xor     edx, edx; dwFlags
0x180011fe5  mov     rcx, rax; hHeap
0x180011fe8  call    cs:__imp_HeapFree
0x180011fee  lea     rcx, [rdi+48h]; lpCriticalSection
0x180011ff2  call    cs:__imp_DeleteCriticalSection
0x180011ff8  mov     rbx, [rdi+38h]
0x180011ffc  test    rbx, rbx
0x180011fff  jz      short loc_180012029
0x180012001  xor     r9d, r9d; msWindowLength
0x180012004  xor     r8d, r8d; msPeriod
0x180012007  xor     edx, edx; pftDueTime
0x180012009  mov     rcx, rbx; pti
0x18001200c  call    cs:__imp_SetThreadpoolTimer
0x180012012  mov     edx, 1; fCancelPendingCallbacks
0x180012017  mov     rcx, rbx; pti
0x18001201a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180012020  mov     rcx, rbx; pti
0x180012023  call    cs:__imp_CloseThreadpoolTimer
0x180012029  mov     rbx, [rdi+30h]
0x18001202d  test    rbx, rbx
0x180012030  jz      short loc_18001205A
0x180012032  xor     r9d, r9d; msWindowLength
0x180012035  xor     r8d, r8d; msPeriod
0x180012038  xor     edx, edx; pftDueTime
0x18001203a  mov     rcx, rbx; pti
0x18001203d  call    cs:__imp_SetThreadpoolTimer
0x180012043  mov     edx, 1; fCancelPendingCallbacks
0x180012048  mov     rcx, rbx; pti
0x18001204b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180012051  mov     rcx, rbx; pti
0x180012054  call    cs:__imp_CloseThreadpoolTimer
0x18001205a  mov     rcx, [rdi+10h]; lpMem
0x18001205e  test    rcx, rcx
0x180012061  jz      short loc_180012068
0x180012063  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180012068  mov     rbx, [rsp+28h+arg_0]
0x18001206d  mov     rsi, [rsp+28h+arg_8]
0x180012072  add     rsp, 20h
0x180012076  pop     rdi
0x180012077  retn
```
