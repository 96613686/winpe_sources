# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x140005cec`
- end: `0x140005eda`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14005c810`

## callees

- `0x1400059e4`
- `0x140005cec`
- `0x14000a240`
- `0x14000bc4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005e11`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005e52`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005e11`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005e52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005db8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005e08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005e48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005db8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005e08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005e48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005daa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005dfa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005e3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005daa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005dfa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005e3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005d0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005d53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005d0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005d53`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005d3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005d85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005d3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005d85`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005d34`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005d7d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005e83`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005eb4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005d34`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005d7d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005e83`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005eb4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005d2b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005d74`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005e7a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005eab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005d2b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005d74`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005e7a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005eab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005d1d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005d66`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005e6c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005e9d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005d1d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005d66`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005e6c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005e9d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  if ( v8 && qword_14007A608 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_14007A608[25], qword_14007A608, v8);
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
0x140005cec  mov     [rsp+arg_0], rbx
0x140005cf1  mov     [rsp+arg_8], rsi
0x140005cf6  push    rdi
0x140005cf7  sub     rsp, 20h
0x140005cfb  mov     rdi, rcx
0x140005cfe  mov     byte ptr [rcx], 0
0x140005d01  mov     rsi, [rcx+30h]
0x140005d05  test    rsi, rsi
0x140005d08  jz      short loc_140005D42
0x140005d0a  call    cs:__imp_GetLastError
0x140005d10  mov     ebx, eax
0x140005d12  xor     r9d, r9d; msWindowLength
0x140005d15  xor     r8d, r8d; msPeriod
0x140005d18  xor     edx, edx; pftDueTime
0x140005d1a  mov     rcx, rsi; pti
0x140005d1d  call    cs:__imp_SetThreadpoolTimer
0x140005d23  mov     edx, 1; fCancelPendingCallbacks
0x140005d28  mov     rcx, rsi; pti
0x140005d2b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005d31  mov     rcx, rsi; pti
0x140005d34  call    cs:__imp_CloseThreadpoolTimer
0x140005d3a  mov     ecx, ebx; dwErrCode
0x140005d3c  call    cs:__imp_SetLastError
0x140005d42  mov     qword ptr [rdi+30h], 0
0x140005d4a  mov     rsi, [rdi+38h]
0x140005d4e  test    rsi, rsi
0x140005d51  jz      short loc_140005D8B
0x140005d53  call    cs:__imp_GetLastError
0x140005d59  mov     ebx, eax
0x140005d5b  xor     r9d, r9d; msWindowLength
0x140005d5e  xor     r8d, r8d; msPeriod
0x140005d61  xor     edx, edx; pftDueTime
0x140005d63  mov     rcx, rsi; pti
0x140005d66  call    cs:__imp_SetThreadpoolTimer
0x140005d6c  mov     edx, 1; fCancelPendingCallbacks
0x140005d71  mov     rcx, rsi; pti
0x140005d74  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005d7a  mov     rcx, rsi; pti
0x140005d7d  call    cs:__imp_CloseThreadpoolTimer
0x140005d83  mov     ecx, ebx; dwErrCode
0x140005d85  call    cs:__imp_SetLastError
0x140005d8b  mov     qword ptr [rdi+38h], 0
0x140005d93  mov     rbx, [rdi+100h]
0x140005d9a  mov     qword ptr [rdi+100h], 0
0x140005da5  test    rbx, rbx
0x140005da8  jz      short loc_140005DBE
0x140005daa  call    cs:__imp_GetProcessHeap
0x140005db0  mov     rcx, rax; hHeap
0x140005db3  mov     r8, rbx; lpMem
0x140005db6  xor     edx, edx; dwFlags
0x140005db8  call    cs:__imp_HeapFree
0x140005dbe  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x140005dc5  test    r8, r8
0x140005dc8  jz      short loc_140005DE2
0x140005dca  mov     rdx, cs:qword_14007A608; SRWLock
0x140005dd1  test    rdx, rdx
0x140005dd4  jz      short loc_140005DE2
0x140005dd6  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140005ddd  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x140005de2  lea     rbx, [rdi+98h]
0x140005de9  mov     rsi, [rbx+40h]
0x140005ded  mov     qword ptr [rbx+40h], 0
0x140005df5  test    rsi, rsi
0x140005df8  jz      short loc_140005E0E
0x140005dfa  call    cs:__imp_GetProcessHeap
0x140005e00  mov     rcx, rax; hHeap
0x140005e03  mov     r8, rsi; lpMem
0x140005e06  xor     edx, edx; dwFlags
0x140005e08  call    cs:__imp_HeapFree
0x140005e0e  mov     rcx, rbx; lpCriticalSection
0x140005e11  call    cs:__imp_DeleteCriticalSection
0x140005e17  lea     rcx, [rdi+90h]
0x140005e1e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140005e23  mov     rsi, [rdi+88h]
0x140005e2a  mov     qword ptr [rdi+88h], 0
0x140005e35  test    rsi, rsi
0x140005e38  jz      short loc_140005E4E
0x140005e3a  call    cs:__imp_GetProcessHeap
0x140005e40  mov     rcx, rax; hHeap
0x140005e43  mov     r8, rsi; lpMem
0x140005e46  xor     edx, edx; dwFlags
0x140005e48  call    cs:__imp_HeapFree
0x140005e4e  lea     rcx, [rdi+48h]; lpCriticalSection
0x140005e52  call    cs:__imp_DeleteCriticalSection
0x140005e58  mov     rbx, [rdi+38h]
0x140005e5c  test    rbx, rbx
0x140005e5f  jz      short loc_140005E89
0x140005e61  xor     r9d, r9d; msWindowLength
0x140005e64  xor     r8d, r8d; msPeriod
0x140005e67  xor     edx, edx; pftDueTime
0x140005e69  mov     rcx, rbx; pti
0x140005e6c  call    cs:__imp_SetThreadpoolTimer
0x140005e72  mov     edx, 1; fCancelPendingCallbacks
0x140005e77  mov     rcx, rbx; pti
0x140005e7a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005e80  mov     rcx, rbx; pti
0x140005e83  call    cs:__imp_CloseThreadpoolTimer
0x140005e89  mov     rbx, [rdi+30h]
0x140005e8d  test    rbx, rbx
0x140005e90  jz      short loc_140005EBB
0x140005e92  xor     r9d, r9d; msWindowLength
0x140005e95  xor     r8d, r8d; msPeriod
0x140005e98  xor     edx, edx; pftDueTime
0x140005e9a  mov     rcx, rbx; pti
0x140005e9d  call    cs:__imp_SetThreadpoolTimer
0x140005ea3  mov     edx, 1; fCancelPendingCallbacks
0x140005ea8  mov     rcx, rbx; pti
0x140005eab  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005eb1  mov     rcx, rbx; pti
0x140005eb4  call    cs:__imp_CloseThreadpoolTimer
0x140005eba  nop
0x140005ebb  mov     rcx, [rdi+10h]; lpMem
0x140005ebf  test    rcx, rcx
0x140005ec2  jz      short loc_140005ECA
0x140005ec4  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140005ec9  nop
0x140005eca  mov     rbx, [rsp+28h+arg_0]
0x140005ecf  mov     rsi, [rsp+28h+arg_8]
0x140005ed4  add     rsp, 20h
0x140005ed8  pop     rdi
0x140005ed9  retn
```
