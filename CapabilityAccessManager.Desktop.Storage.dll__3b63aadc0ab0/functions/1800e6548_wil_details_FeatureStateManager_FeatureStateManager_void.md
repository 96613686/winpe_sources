# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800e6548`
- end: `0x1800e6736`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18010c4a0`

## callees

- `0x1800e62a4`
- `0x1800e6548`
- `0x1800ea5f4`
- `0x1800ebf24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800e666d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800e66ae`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800e666d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800e66ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e6606`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e6656`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e6696`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e6606`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e6656`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e6696`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e6614`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e6664`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e66a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e6614`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e6664`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e66a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e6598`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e65e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e6598`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e65e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e6566`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e65af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e6566`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e65af`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800e6587`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800e65d0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800e66d6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800e6707`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800e6587`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800e65d0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800e66d6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800e6707`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800e6590`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800e65d9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800e66df`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800e6710`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800e6590`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800e65d9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800e66df`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800e6710`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800e6579`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800e65c2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800e66c8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800e66f9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800e6579`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800e65c2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800e66c8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800e66f9`

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
  if ( v8 && qword_18013F620 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18013F620[25], qword_18013F620, v8);
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
0x1800e6548  mov     [rsp+arg_0], rbx
0x1800e654d  mov     [rsp+arg_8], rsi
0x1800e6552  push    rdi
0x1800e6553  sub     rsp, 20h
0x1800e6557  mov     rdi, rcx
0x1800e655a  mov     byte ptr [rcx], 0
0x1800e655d  mov     rsi, [rcx+30h]
0x1800e6561  test    rsi, rsi
0x1800e6564  jz      short loc_1800E659E
0x1800e6566  call    cs:__imp_GetLastError
0x1800e656c  mov     ebx, eax
0x1800e656e  xor     r9d, r9d; msWindowLength
0x1800e6571  xor     r8d, r8d; msPeriod
0x1800e6574  xor     edx, edx; pftDueTime
0x1800e6576  mov     rcx, rsi; pti
0x1800e6579  call    cs:__imp_SetThreadpoolTimer
0x1800e657f  mov     edx, 1; fCancelPendingCallbacks
0x1800e6584  mov     rcx, rsi; pti
0x1800e6587  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800e658d  mov     rcx, rsi; pti
0x1800e6590  call    cs:__imp_CloseThreadpoolTimer
0x1800e6596  mov     ecx, ebx; dwErrCode
0x1800e6598  call    cs:__imp_SetLastError
0x1800e659e  mov     qword ptr [rdi+30h], 0
0x1800e65a6  mov     rsi, [rdi+38h]
0x1800e65aa  test    rsi, rsi
0x1800e65ad  jz      short loc_1800E65E7
0x1800e65af  call    cs:__imp_GetLastError
0x1800e65b5  mov     ebx, eax
0x1800e65b7  xor     r9d, r9d; msWindowLength
0x1800e65ba  xor     r8d, r8d; msPeriod
0x1800e65bd  xor     edx, edx; pftDueTime
0x1800e65bf  mov     rcx, rsi; pti
0x1800e65c2  call    cs:__imp_SetThreadpoolTimer
0x1800e65c8  mov     edx, 1; fCancelPendingCallbacks
0x1800e65cd  mov     rcx, rsi; pti
0x1800e65d0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800e65d6  mov     rcx, rsi; pti
0x1800e65d9  call    cs:__imp_CloseThreadpoolTimer
0x1800e65df  mov     ecx, ebx; dwErrCode
0x1800e65e1  call    cs:__imp_SetLastError
0x1800e65e7  mov     qword ptr [rdi+38h], 0
0x1800e65ef  mov     rbx, [rdi+100h]
0x1800e65f6  mov     qword ptr [rdi+100h], 0
0x1800e6601  test    rbx, rbx
0x1800e6604  jz      short loc_1800E661A
0x1800e6606  call    cs:__imp_GetProcessHeap
0x1800e660c  mov     rcx, rax; hHeap
0x1800e660f  mov     r8, rbx; lpMem
0x1800e6612  xor     edx, edx; dwFlags
0x1800e6614  call    cs:__imp_HeapFree
0x1800e661a  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800e6621  test    r8, r8
0x1800e6624  jz      short loc_1800E663E
0x1800e6626  mov     rdx, cs:qword_18013F620; SRWLock
0x1800e662d  test    rdx, rdx
0x1800e6630  jz      short loc_1800E663E
0x1800e6632  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800e6639  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800e663e  lea     rbx, [rdi+98h]
0x1800e6645  mov     rsi, [rbx+40h]
0x1800e6649  mov     qword ptr [rbx+40h], 0
0x1800e6651  test    rsi, rsi
0x1800e6654  jz      short loc_1800E666A
0x1800e6656  call    cs:__imp_GetProcessHeap
0x1800e665c  mov     rcx, rax; hHeap
0x1800e665f  mov     r8, rsi; lpMem
0x1800e6662  xor     edx, edx; dwFlags
0x1800e6664  call    cs:__imp_HeapFree
0x1800e666a  mov     rcx, rbx; lpCriticalSection
0x1800e666d  call    cs:__imp_DeleteCriticalSection
0x1800e6673  lea     rcx, [rdi+90h]
0x1800e667a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800e667f  mov     rsi, [rdi+88h]
0x1800e6686  mov     qword ptr [rdi+88h], 0
0x1800e6691  test    rsi, rsi
0x1800e6694  jz      short loc_1800E66AA
0x1800e6696  call    cs:__imp_GetProcessHeap
0x1800e669c  mov     rcx, rax; hHeap
0x1800e669f  mov     r8, rsi; lpMem
0x1800e66a2  xor     edx, edx; dwFlags
0x1800e66a4  call    cs:__imp_HeapFree
0x1800e66aa  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800e66ae  call    cs:__imp_DeleteCriticalSection
0x1800e66b4  mov     rbx, [rdi+38h]
0x1800e66b8  test    rbx, rbx
0x1800e66bb  jz      short loc_1800E66E5
0x1800e66bd  xor     r9d, r9d; msWindowLength
0x1800e66c0  xor     r8d, r8d; msPeriod
0x1800e66c3  xor     edx, edx; pftDueTime
0x1800e66c5  mov     rcx, rbx; pti
0x1800e66c8  call    cs:__imp_SetThreadpoolTimer
0x1800e66ce  mov     edx, 1; fCancelPendingCallbacks
0x1800e66d3  mov     rcx, rbx; pti
0x1800e66d6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800e66dc  mov     rcx, rbx; pti
0x1800e66df  call    cs:__imp_CloseThreadpoolTimer
0x1800e66e5  mov     rbx, [rdi+30h]
0x1800e66e9  test    rbx, rbx
0x1800e66ec  jz      short loc_1800E6717
0x1800e66ee  xor     r9d, r9d; msWindowLength
0x1800e66f1  xor     r8d, r8d; msPeriod
0x1800e66f4  xor     edx, edx; pftDueTime
0x1800e66f6  mov     rcx, rbx; pti
0x1800e66f9  call    cs:__imp_SetThreadpoolTimer
0x1800e66ff  mov     edx, 1; fCancelPendingCallbacks
0x1800e6704  mov     rcx, rbx; pti
0x1800e6707  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800e670d  mov     rcx, rbx; pti
0x1800e6710  call    cs:__imp_CloseThreadpoolTimer
0x1800e6716  nop
0x1800e6717  mov     rcx, [rdi+10h]; lpMem
0x1800e671b  test    rcx, rcx
0x1800e671e  jz      short loc_1800E6726
0x1800e6720  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800e6725  nop
0x1800e6726  mov     rbx, [rsp+28h+arg_0]
0x1800e672b  mov     rsi, [rsp+28h+arg_8]
0x1800e6730  add     rsp, 20h
0x1800e6734  pop     rdi
0x1800e6735  retn
```
