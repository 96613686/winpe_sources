# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x140008168`
- end: `0x140008356`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140012660`

## callees

- `0x140008024`
- `0x140008168`
- `0x14000aff4`
- `0x14000c19c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140008186`
- `KERNEL32!GetLastError` at `0x1400081cf`
- `KERNEL32!GetLastError` at `0x140008186`
- `KERNEL32!GetLastError` at `0x1400081cf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000828d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400082ce`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000828d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400082ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400081b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008201`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400081b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008201`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008234`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008284`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400082c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008234`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008284`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400082c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008226`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008276`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400082b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008226`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008276`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400082b6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400081a7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400081f0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400082f6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008327`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400081a7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400081f0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400082f6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008327`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008199`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400081e2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400082e8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008319`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008199`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400081e2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400082e8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008319`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400081b0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400081f9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400082ff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008330`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400081b0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400081f9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400082ff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008330`

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
  if ( v8 && qword_14001B048 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_14001B048[25], qword_14001B048, v8);
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
0x140008168  mov     [rsp+arg_0], rbx
0x14000816d  mov     [rsp+arg_8], rsi
0x140008172  push    rdi
0x140008173  sub     rsp, 20h
0x140008177  mov     rdi, rcx
0x14000817a  mov     byte ptr [rcx], 0
0x14000817d  mov     rsi, [rcx+30h]
0x140008181  test    rsi, rsi
0x140008184  jz      short loc_1400081BE
0x140008186  call    cs:__imp_GetLastError
0x14000818c  mov     ebx, eax
0x14000818e  xor     r9d, r9d; msWindowLength
0x140008191  xor     r8d, r8d; msPeriod
0x140008194  xor     edx, edx; pftDueTime
0x140008196  mov     rcx, rsi; pti
0x140008199  call    cs:__imp_SetThreadpoolTimer
0x14000819f  mov     edx, 1; fCancelPendingCallbacks
0x1400081a4  mov     rcx, rsi; pti
0x1400081a7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400081ad  mov     rcx, rsi; pti
0x1400081b0  call    cs:__imp_CloseThreadpoolTimer
0x1400081b6  mov     ecx, ebx; dwErrCode
0x1400081b8  call    cs:__imp_SetLastError
0x1400081be  mov     qword ptr [rdi+30h], 0
0x1400081c6  mov     rsi, [rdi+38h]
0x1400081ca  test    rsi, rsi
0x1400081cd  jz      short loc_140008207
0x1400081cf  call    cs:__imp_GetLastError
0x1400081d5  mov     ebx, eax
0x1400081d7  xor     r9d, r9d; msWindowLength
0x1400081da  xor     r8d, r8d; msPeriod
0x1400081dd  xor     edx, edx; pftDueTime
0x1400081df  mov     rcx, rsi; pti
0x1400081e2  call    cs:__imp_SetThreadpoolTimer
0x1400081e8  mov     edx, 1; fCancelPendingCallbacks
0x1400081ed  mov     rcx, rsi; pti
0x1400081f0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400081f6  mov     rcx, rsi; pti
0x1400081f9  call    cs:__imp_CloseThreadpoolTimer
0x1400081ff  mov     ecx, ebx; dwErrCode
0x140008201  call    cs:__imp_SetLastError
0x140008207  mov     qword ptr [rdi+38h], 0
0x14000820f  mov     rbx, [rdi+100h]
0x140008216  mov     qword ptr [rdi+100h], 0
0x140008221  test    rbx, rbx
0x140008224  jz      short loc_14000823A
0x140008226  call    cs:__imp_GetProcessHeap
0x14000822c  mov     rcx, rax; hHeap
0x14000822f  mov     r8, rbx; lpMem
0x140008232  xor     edx, edx; dwFlags
0x140008234  call    cs:__imp_HeapFree
0x14000823a  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x140008241  test    r8, r8
0x140008244  jz      short loc_14000825E
0x140008246  mov     rdx, cs:qword_14001B048; SRWLock
0x14000824d  test    rdx, rdx
0x140008250  jz      short loc_14000825E
0x140008252  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140008259  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x14000825e  lea     rbx, [rdi+98h]
0x140008265  mov     rsi, [rbx+40h]
0x140008269  mov     qword ptr [rbx+40h], 0
0x140008271  test    rsi, rsi
0x140008274  jz      short loc_14000828A
0x140008276  call    cs:__imp_GetProcessHeap
0x14000827c  mov     rcx, rax; hHeap
0x14000827f  mov     r8, rsi; lpMem
0x140008282  xor     edx, edx; dwFlags
0x140008284  call    cs:__imp_HeapFree
0x14000828a  mov     rcx, rbx; lpCriticalSection
0x14000828d  call    cs:__imp_DeleteCriticalSection
0x140008293  lea     rcx, [rdi+90h]
0x14000829a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14000829f  mov     rsi, [rdi+88h]
0x1400082a6  mov     qword ptr [rdi+88h], 0
0x1400082b1  test    rsi, rsi
0x1400082b4  jz      short loc_1400082CA
0x1400082b6  call    cs:__imp_GetProcessHeap
0x1400082bc  mov     rcx, rax; hHeap
0x1400082bf  mov     r8, rsi; lpMem
0x1400082c2  xor     edx, edx; dwFlags
0x1400082c4  call    cs:__imp_HeapFree
0x1400082ca  lea     rcx, [rdi+48h]; lpCriticalSection
0x1400082ce  call    cs:__imp_DeleteCriticalSection
0x1400082d4  mov     rbx, [rdi+38h]
0x1400082d8  test    rbx, rbx
0x1400082db  jz      short loc_140008305
0x1400082dd  xor     r9d, r9d; msWindowLength
0x1400082e0  xor     r8d, r8d; msPeriod
0x1400082e3  xor     edx, edx; pftDueTime
0x1400082e5  mov     rcx, rbx; pti
0x1400082e8  call    cs:__imp_SetThreadpoolTimer
0x1400082ee  mov     edx, 1; fCancelPendingCallbacks
0x1400082f3  mov     rcx, rbx; pti
0x1400082f6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400082fc  mov     rcx, rbx; pti
0x1400082ff  call    cs:__imp_CloseThreadpoolTimer
0x140008305  mov     rbx, [rdi+30h]
0x140008309  test    rbx, rbx
0x14000830c  jz      short loc_140008337
0x14000830e  xor     r9d, r9d; msWindowLength
0x140008311  xor     r8d, r8d; msPeriod
0x140008314  xor     edx, edx; pftDueTime
0x140008316  mov     rcx, rbx; pti
0x140008319  call    cs:__imp_SetThreadpoolTimer
0x14000831f  mov     edx, 1; fCancelPendingCallbacks
0x140008324  mov     rcx, rbx; pti
0x140008327  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000832d  mov     rcx, rbx; pti
0x140008330  call    cs:__imp_CloseThreadpoolTimer
0x140008336  nop
0x140008337  mov     rcx, [rdi+10h]; lpMem
0x14000833b  test    rcx, rcx
0x14000833e  jz      short loc_140008346
0x140008340  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140008345  nop
0x140008346  mov     rbx, [rsp+28h+arg_0]
0x14000834b  mov     rsi, [rsp+28h+arg_8]
0x140008350  add     rsp, 20h
0x140008354  pop     rdi
0x140008355  retn
```
