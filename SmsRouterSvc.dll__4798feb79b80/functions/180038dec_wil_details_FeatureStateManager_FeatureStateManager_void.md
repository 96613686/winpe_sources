# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180038dec`
- end: `0x180038fda`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18006ecf0`

## callees

- `0x180038b34`
- `0x180038dec`
- `0x18003b448`
- `0x18003bd44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038f11`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038f52`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038f11`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038f52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038eaa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038efa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038f3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038eaa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038efa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038f3a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038eb8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038f08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038f48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038eb8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038f08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038f48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038e0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038e53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038e0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038e53`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038e3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038e85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038e3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038e85`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180038e1d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180038e66`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180038f6c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180038f9d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180038e1d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180038e66`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180038f6c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180038f9d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180038e2b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180038e74`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180038f7a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180038fab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180038e2b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180038e74`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180038f7a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180038fab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180038e34`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180038e7d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180038f83`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180038fb4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180038e34`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180038e7d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180038f83`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180038fb4`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
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
  if ( v8 && qword_18008C168 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18008C168[25], qword_18008C168, v8);
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
0x180038dec  mov     [rsp+arg_0], rbx
0x180038df1  mov     [rsp+arg_8], rsi
0x180038df6  push    rdi
0x180038df7  sub     rsp, 20h
0x180038dfb  mov     rdi, rcx
0x180038dfe  mov     byte ptr [rcx], 0
0x180038e01  mov     rsi, [rcx+30h]
0x180038e05  test    rsi, rsi
0x180038e08  jz      short loc_180038E42
0x180038e0a  call    cs:__imp_GetLastError
0x180038e10  mov     ebx, eax
0x180038e12  xor     r9d, r9d; msWindowLength
0x180038e15  xor     r8d, r8d; msPeriod
0x180038e18  xor     edx, edx; pftDueTime
0x180038e1a  mov     rcx, rsi; pti
0x180038e1d  call    cs:__imp_SetThreadpoolTimer
0x180038e23  mov     edx, 1; fCancelPendingCallbacks
0x180038e28  mov     rcx, rsi; pti
0x180038e2b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180038e31  mov     rcx, rsi; pti
0x180038e34  call    cs:__imp_CloseThreadpoolTimer
0x180038e3a  mov     ecx, ebx; dwErrCode
0x180038e3c  call    cs:__imp_SetLastError
0x180038e42  mov     qword ptr [rdi+30h], 0
0x180038e4a  mov     rsi, [rdi+38h]
0x180038e4e  test    rsi, rsi
0x180038e51  jz      short loc_180038E8B
0x180038e53  call    cs:__imp_GetLastError
0x180038e59  mov     ebx, eax
0x180038e5b  xor     r9d, r9d; msWindowLength
0x180038e5e  xor     r8d, r8d; msPeriod
0x180038e61  xor     edx, edx; pftDueTime
0x180038e63  mov     rcx, rsi; pti
0x180038e66  call    cs:__imp_SetThreadpoolTimer
0x180038e6c  mov     edx, 1; fCancelPendingCallbacks
0x180038e71  mov     rcx, rsi; pti
0x180038e74  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180038e7a  mov     rcx, rsi; pti
0x180038e7d  call    cs:__imp_CloseThreadpoolTimer
0x180038e83  mov     ecx, ebx; dwErrCode
0x180038e85  call    cs:__imp_SetLastError
0x180038e8b  mov     qword ptr [rdi+38h], 0
0x180038e93  mov     rbx, [rdi+100h]
0x180038e9a  mov     qword ptr [rdi+100h], 0
0x180038ea5  test    rbx, rbx
0x180038ea8  jz      short loc_180038EBE
0x180038eaa  call    cs:__imp_GetProcessHeap
0x180038eb0  mov     rcx, rax; hHeap
0x180038eb3  mov     r8, rbx; lpMem
0x180038eb6  xor     edx, edx; dwFlags
0x180038eb8  call    cs:__imp_HeapFree
0x180038ebe  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180038ec5  test    r8, r8
0x180038ec8  jz      short loc_180038EE2
0x180038eca  mov     rdx, cs:qword_18008C168; SRWLock
0x180038ed1  test    rdx, rdx
0x180038ed4  jz      short loc_180038EE2
0x180038ed6  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180038edd  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180038ee2  lea     rbx, [rdi+98h]
0x180038ee9  mov     rsi, [rbx+40h]
0x180038eed  mov     qword ptr [rbx+40h], 0
0x180038ef5  test    rsi, rsi
0x180038ef8  jz      short loc_180038F0E
0x180038efa  call    cs:__imp_GetProcessHeap
0x180038f00  mov     rcx, rax; hHeap
0x180038f03  mov     r8, rsi; lpMem
0x180038f06  xor     edx, edx; dwFlags
0x180038f08  call    cs:__imp_HeapFree
0x180038f0e  mov     rcx, rbx; lpCriticalSection
0x180038f11  call    cs:__imp_DeleteCriticalSection
0x180038f17  lea     rcx, [rdi+90h]
0x180038f1e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180038f23  mov     rsi, [rdi+88h]
0x180038f2a  mov     qword ptr [rdi+88h], 0
0x180038f35  test    rsi, rsi
0x180038f38  jz      short loc_180038F4E
0x180038f3a  call    cs:__imp_GetProcessHeap
0x180038f40  mov     rcx, rax; hHeap
0x180038f43  mov     r8, rsi; lpMem
0x180038f46  xor     edx, edx; dwFlags
0x180038f48  call    cs:__imp_HeapFree
0x180038f4e  lea     rcx, [rdi+48h]; lpCriticalSection
0x180038f52  call    cs:__imp_DeleteCriticalSection
0x180038f58  mov     rbx, [rdi+38h]
0x180038f5c  test    rbx, rbx
0x180038f5f  jz      short loc_180038F89
0x180038f61  xor     r9d, r9d; msWindowLength
0x180038f64  xor     r8d, r8d; msPeriod
0x180038f67  xor     edx, edx; pftDueTime
0x180038f69  mov     rcx, rbx; pti
0x180038f6c  call    cs:__imp_SetThreadpoolTimer
0x180038f72  mov     edx, 1; fCancelPendingCallbacks
0x180038f77  mov     rcx, rbx; pti
0x180038f7a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180038f80  mov     rcx, rbx; pti
0x180038f83  call    cs:__imp_CloseThreadpoolTimer
0x180038f89  mov     rbx, [rdi+30h]
0x180038f8d  test    rbx, rbx
0x180038f90  jz      short loc_180038FBB
0x180038f92  xor     r9d, r9d; msWindowLength
0x180038f95  xor     r8d, r8d; msPeriod
0x180038f98  xor     edx, edx; pftDueTime
0x180038f9a  mov     rcx, rbx; pti
0x180038f9d  call    cs:__imp_SetThreadpoolTimer
0x180038fa3  mov     edx, 1; fCancelPendingCallbacks
0x180038fa8  mov     rcx, rbx; pti
0x180038fab  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180038fb1  mov     rcx, rbx; pti
0x180038fb4  call    cs:__imp_CloseThreadpoolTimer
0x180038fba  nop
0x180038fbb  mov     rcx, [rdi+10h]; lpMem
0x180038fbf  test    rcx, rcx
0x180038fc2  jz      short loc_180038FCA
0x180038fc4  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180038fc9  nop
0x180038fca  mov     rbx, [rsp+28h+arg_0]
0x180038fcf  mov     rsi, [rsp+28h+arg_8]
0x180038fd4  add     rsp, 20h
0x180038fd8  pop     rdi
0x180038fd9  retn
```
