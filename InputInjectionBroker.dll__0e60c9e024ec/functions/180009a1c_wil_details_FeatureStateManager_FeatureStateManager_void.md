# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180009a1c`
- end: `0x180009c0a`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180011a70`

## callees

- `0x1800098d8`
- `0x180009a1c`
- `0x18000dbd0`
- `0x18000e4fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009b41`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009b82`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009b41`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009b82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009ada`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009ada`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009ae8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009ae8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b78`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009a6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009ab5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009a6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009ab5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a83`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009a5b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009aa4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009baa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009bdb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009a5b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009aa4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009baa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009bdb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009a64`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009aad`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009bb3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009be4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009a64`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009aad`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009bb3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009be4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009a4d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009a96`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009b9c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009bcd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009a4d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009a96`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009b9c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009bcd`

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
  if ( v8 && qword_180022078 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180022078[25], qword_180022078, v8);
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
0x180009a1c  mov     [rsp+arg_0], rbx
0x180009a21  mov     [rsp+arg_8], rsi
0x180009a26  push    rdi
0x180009a27  sub     rsp, 20h
0x180009a2b  mov     rdi, rcx
0x180009a2e  mov     byte ptr [rcx], 0
0x180009a31  mov     rsi, [rcx+30h]
0x180009a35  test    rsi, rsi
0x180009a38  jz      short loc_180009A72
0x180009a3a  call    cs:__imp_GetLastError
0x180009a40  mov     ebx, eax
0x180009a42  xor     r9d, r9d; msWindowLength
0x180009a45  xor     r8d, r8d; msPeriod
0x180009a48  xor     edx, edx; pftDueTime
0x180009a4a  mov     rcx, rsi; pti
0x180009a4d  call    cs:__imp_SetThreadpoolTimer
0x180009a53  mov     edx, 1; fCancelPendingCallbacks
0x180009a58  mov     rcx, rsi; pti
0x180009a5b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009a61  mov     rcx, rsi; pti
0x180009a64  call    cs:__imp_CloseThreadpoolTimer
0x180009a6a  mov     ecx, ebx; dwErrCode
0x180009a6c  call    cs:__imp_SetLastError
0x180009a72  mov     qword ptr [rdi+30h], 0
0x180009a7a  mov     rsi, [rdi+38h]
0x180009a7e  test    rsi, rsi
0x180009a81  jz      short loc_180009ABB
0x180009a83  call    cs:__imp_GetLastError
0x180009a89  mov     ebx, eax
0x180009a8b  xor     r9d, r9d; msWindowLength
0x180009a8e  xor     r8d, r8d; msPeriod
0x180009a91  xor     edx, edx; pftDueTime
0x180009a93  mov     rcx, rsi; pti
0x180009a96  call    cs:__imp_SetThreadpoolTimer
0x180009a9c  mov     edx, 1; fCancelPendingCallbacks
0x180009aa1  mov     rcx, rsi; pti
0x180009aa4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009aaa  mov     rcx, rsi; pti
0x180009aad  call    cs:__imp_CloseThreadpoolTimer
0x180009ab3  mov     ecx, ebx; dwErrCode
0x180009ab5  call    cs:__imp_SetLastError
0x180009abb  mov     qword ptr [rdi+38h], 0
0x180009ac3  mov     rbx, [rdi+100h]
0x180009aca  mov     qword ptr [rdi+100h], 0
0x180009ad5  test    rbx, rbx
0x180009ad8  jz      short loc_180009AEE
0x180009ada  call    cs:__imp_GetProcessHeap
0x180009ae0  mov     rcx, rax; hHeap
0x180009ae3  mov     r8, rbx; lpMem
0x180009ae6  xor     edx, edx; dwFlags
0x180009ae8  call    cs:__imp_HeapFree
0x180009aee  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180009af5  test    r8, r8
0x180009af8  jz      short loc_180009B12
0x180009afa  mov     rdx, cs:qword_180022078; SRWLock
0x180009b01  test    rdx, rdx
0x180009b04  jz      short loc_180009B12
0x180009b06  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180009b0d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180009b12  lea     rbx, [rdi+98h]
0x180009b19  mov     rsi, [rbx+40h]
0x180009b1d  mov     qword ptr [rbx+40h], 0
0x180009b25  test    rsi, rsi
0x180009b28  jz      short loc_180009B3E
0x180009b2a  call    cs:__imp_GetProcessHeap
0x180009b30  mov     rcx, rax; hHeap
0x180009b33  mov     r8, rsi; lpMem
0x180009b36  xor     edx, edx; dwFlags
0x180009b38  call    cs:__imp_HeapFree
0x180009b3e  mov     rcx, rbx; lpCriticalSection
0x180009b41  call    cs:__imp_DeleteCriticalSection
0x180009b47  lea     rcx, [rdi+90h]
0x180009b4e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180009b53  mov     rsi, [rdi+88h]
0x180009b5a  mov     qword ptr [rdi+88h], 0
0x180009b65  test    rsi, rsi
0x180009b68  jz      short loc_180009B7E
0x180009b6a  call    cs:__imp_GetProcessHeap
0x180009b70  mov     rcx, rax; hHeap
0x180009b73  mov     r8, rsi; lpMem
0x180009b76  xor     edx, edx; dwFlags
0x180009b78  call    cs:__imp_HeapFree
0x180009b7e  lea     rcx, [rdi+48h]; lpCriticalSection
0x180009b82  call    cs:__imp_DeleteCriticalSection
0x180009b88  mov     rbx, [rdi+38h]
0x180009b8c  test    rbx, rbx
0x180009b8f  jz      short loc_180009BB9
0x180009b91  xor     r9d, r9d; msWindowLength
0x180009b94  xor     r8d, r8d; msPeriod
0x180009b97  xor     edx, edx; pftDueTime
0x180009b99  mov     rcx, rbx; pti
0x180009b9c  call    cs:__imp_SetThreadpoolTimer
0x180009ba2  mov     edx, 1; fCancelPendingCallbacks
0x180009ba7  mov     rcx, rbx; pti
0x180009baa  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009bb0  mov     rcx, rbx; pti
0x180009bb3  call    cs:__imp_CloseThreadpoolTimer
0x180009bb9  mov     rbx, [rdi+30h]
0x180009bbd  test    rbx, rbx
0x180009bc0  jz      short loc_180009BEB
0x180009bc2  xor     r9d, r9d; msWindowLength
0x180009bc5  xor     r8d, r8d; msPeriod
0x180009bc8  xor     edx, edx; pftDueTime
0x180009bca  mov     rcx, rbx; pti
0x180009bcd  call    cs:__imp_SetThreadpoolTimer
0x180009bd3  mov     edx, 1; fCancelPendingCallbacks
0x180009bd8  mov     rcx, rbx; pti
0x180009bdb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009be1  mov     rcx, rbx; pti
0x180009be4  call    cs:__imp_CloseThreadpoolTimer
0x180009bea  nop
0x180009beb  mov     rcx, [rdi+10h]; lpMem
0x180009bef  test    rcx, rcx
0x180009bf2  jz      short loc_180009BFA
0x180009bf4  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180009bf9  nop
0x180009bfa  mov     rbx, [rsp+28h+arg_0]
0x180009bff  mov     rsi, [rsp+28h+arg_8]
0x180009c04  add     rsp, 20h
0x180009c08  pop     rdi
0x180009c09  retn
```
