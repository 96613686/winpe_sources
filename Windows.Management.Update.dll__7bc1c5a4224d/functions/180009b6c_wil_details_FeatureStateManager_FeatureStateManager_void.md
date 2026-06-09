# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180009b6c`
- end: `0x180009d5a`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180029170`

## callees

- `0x1800097ec`
- `0x180009b6c`
- `0x18000deb0`
- `0x18000f540`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009c91`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009cd2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009c91`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009cd2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009cba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009cba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009c38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009c88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009cc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009c38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009c88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009cc8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009bbc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009c05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009bbc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009c05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009bd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009bd3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009b9d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009be6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009cec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009d1d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009b9d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009be6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009cec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009d1d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009bb4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009bfd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009d03`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009d34`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009bb4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009bfd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009d03`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009d34`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009bab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009bf4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009cfa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009d2b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009bab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009bf4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009cfa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009d2b`

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
  if ( v8 && qword_18003A080 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18003A080[25], qword_18003A080, v8);
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
0x180009b6c  mov     [rsp+arg_0], rbx
0x180009b71  mov     [rsp+arg_8], rsi
0x180009b76  push    rdi
0x180009b77  sub     rsp, 20h
0x180009b7b  mov     rdi, rcx
0x180009b7e  mov     byte ptr [rcx], 0
0x180009b81  mov     rsi, [rcx+30h]
0x180009b85  test    rsi, rsi
0x180009b88  jz      short loc_180009BC2
0x180009b8a  call    cs:__imp_GetLastError
0x180009b90  mov     ebx, eax
0x180009b92  xor     r9d, r9d; msWindowLength
0x180009b95  xor     r8d, r8d; msPeriod
0x180009b98  xor     edx, edx; pftDueTime
0x180009b9a  mov     rcx, rsi; pti
0x180009b9d  call    cs:__imp_SetThreadpoolTimer
0x180009ba3  mov     edx, 1; fCancelPendingCallbacks
0x180009ba8  mov     rcx, rsi; pti
0x180009bab  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009bb1  mov     rcx, rsi; pti
0x180009bb4  call    cs:__imp_CloseThreadpoolTimer
0x180009bba  mov     ecx, ebx; dwErrCode
0x180009bbc  call    cs:__imp_SetLastError
0x180009bc2  mov     qword ptr [rdi+30h], 0
0x180009bca  mov     rsi, [rdi+38h]
0x180009bce  test    rsi, rsi
0x180009bd1  jz      short loc_180009C0B
0x180009bd3  call    cs:__imp_GetLastError
0x180009bd9  mov     ebx, eax
0x180009bdb  xor     r9d, r9d; msWindowLength
0x180009bde  xor     r8d, r8d; msPeriod
0x180009be1  xor     edx, edx; pftDueTime
0x180009be3  mov     rcx, rsi; pti
0x180009be6  call    cs:__imp_SetThreadpoolTimer
0x180009bec  mov     edx, 1; fCancelPendingCallbacks
0x180009bf1  mov     rcx, rsi; pti
0x180009bf4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009bfa  mov     rcx, rsi; pti
0x180009bfd  call    cs:__imp_CloseThreadpoolTimer
0x180009c03  mov     ecx, ebx; dwErrCode
0x180009c05  call    cs:__imp_SetLastError
0x180009c0b  mov     qword ptr [rdi+38h], 0
0x180009c13  mov     rbx, [rdi+100h]
0x180009c1a  mov     qword ptr [rdi+100h], 0
0x180009c25  test    rbx, rbx
0x180009c28  jz      short loc_180009C3E
0x180009c2a  call    cs:__imp_GetProcessHeap
0x180009c30  mov     rcx, rax; hHeap
0x180009c33  mov     r8, rbx; lpMem
0x180009c36  xor     edx, edx; dwFlags
0x180009c38  call    cs:__imp_HeapFree
0x180009c3e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180009c45  test    r8, r8
0x180009c48  jz      short loc_180009C62
0x180009c4a  mov     rdx, cs:qword_18003A080; SRWLock
0x180009c51  test    rdx, rdx
0x180009c54  jz      short loc_180009C62
0x180009c56  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180009c5d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180009c62  lea     rbx, [rdi+98h]
0x180009c69  mov     rsi, [rbx+40h]
0x180009c6d  mov     qword ptr [rbx+40h], 0
0x180009c75  test    rsi, rsi
0x180009c78  jz      short loc_180009C8E
0x180009c7a  call    cs:__imp_GetProcessHeap
0x180009c80  mov     rcx, rax; hHeap
0x180009c83  mov     r8, rsi; lpMem
0x180009c86  xor     edx, edx; dwFlags
0x180009c88  call    cs:__imp_HeapFree
0x180009c8e  mov     rcx, rbx; lpCriticalSection
0x180009c91  call    cs:__imp_DeleteCriticalSection
0x180009c97  lea     rcx, [rdi+90h]
0x180009c9e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180009ca3  mov     rsi, [rdi+88h]
0x180009caa  mov     qword ptr [rdi+88h], 0
0x180009cb5  test    rsi, rsi
0x180009cb8  jz      short loc_180009CCE
0x180009cba  call    cs:__imp_GetProcessHeap
0x180009cc0  mov     rcx, rax; hHeap
0x180009cc3  mov     r8, rsi; lpMem
0x180009cc6  xor     edx, edx; dwFlags
0x180009cc8  call    cs:__imp_HeapFree
0x180009cce  lea     rcx, [rdi+48h]; lpCriticalSection
0x180009cd2  call    cs:__imp_DeleteCriticalSection
0x180009cd8  mov     rbx, [rdi+38h]
0x180009cdc  test    rbx, rbx
0x180009cdf  jz      short loc_180009D09
0x180009ce1  xor     r9d, r9d; msWindowLength
0x180009ce4  xor     r8d, r8d; msPeriod
0x180009ce7  xor     edx, edx; pftDueTime
0x180009ce9  mov     rcx, rbx; pti
0x180009cec  call    cs:__imp_SetThreadpoolTimer
0x180009cf2  mov     edx, 1; fCancelPendingCallbacks
0x180009cf7  mov     rcx, rbx; pti
0x180009cfa  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009d00  mov     rcx, rbx; pti
0x180009d03  call    cs:__imp_CloseThreadpoolTimer
0x180009d09  mov     rbx, [rdi+30h]
0x180009d0d  test    rbx, rbx
0x180009d10  jz      short loc_180009D3B
0x180009d12  xor     r9d, r9d; msWindowLength
0x180009d15  xor     r8d, r8d; msPeriod
0x180009d18  xor     edx, edx; pftDueTime
0x180009d1a  mov     rcx, rbx; pti
0x180009d1d  call    cs:__imp_SetThreadpoolTimer
0x180009d23  mov     edx, 1; fCancelPendingCallbacks
0x180009d28  mov     rcx, rbx; pti
0x180009d2b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009d31  mov     rcx, rbx; pti
0x180009d34  call    cs:__imp_CloseThreadpoolTimer
0x180009d3a  nop
0x180009d3b  mov     rcx, [rdi+10h]; lpMem
0x180009d3f  test    rcx, rcx
0x180009d42  jz      short loc_180009D4A
0x180009d44  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180009d49  nop
0x180009d4a  mov     rbx, [rsp+28h+arg_0]
0x180009d4f  mov     rsi, [rsp+28h+arg_8]
0x180009d54  add     rsp, 20h
0x180009d58  pop     rdi
0x180009d59  retn
```
