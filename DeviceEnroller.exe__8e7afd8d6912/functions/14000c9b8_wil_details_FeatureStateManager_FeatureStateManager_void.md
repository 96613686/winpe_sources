# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x14000c9b8`
- end: `0x14000cba6`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14005c130`

## callees

- `0x14000c51c`
- `0x14000c9b8`
- `0x140016fc8`
- `0x140018fa4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000cadd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000cb1e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000cadd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000cb1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ca84`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000cad4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000cb14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ca84`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000cad4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000cb14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ca76`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000cac6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000cb06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ca76`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000cac6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000cb06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c9d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ca1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c9d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ca1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ca08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ca51`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ca08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ca51`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000ca00`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000ca49`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000cb4f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000cb80`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000ca00`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000ca49`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000cb4f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000cb80`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000c9e9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000ca32`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000cb38`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000cb69`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000c9e9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000ca32`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000cb38`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000cb69`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000c9f7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000ca40`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000cb46`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000cb77`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000c9f7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000ca40`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000cb46`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000cb77`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
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
  if ( v8 && qword_14007D948 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_14007D948[25], qword_14007D948, v8);
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
0x14000c9b8  mov     [rsp+arg_0], rbx
0x14000c9bd  mov     [rsp+arg_8], rsi
0x14000c9c2  push    rdi
0x14000c9c3  sub     rsp, 20h
0x14000c9c7  mov     rdi, rcx
0x14000c9ca  mov     byte ptr [rcx], 0
0x14000c9cd  mov     rsi, [rcx+30h]
0x14000c9d1  test    rsi, rsi
0x14000c9d4  jz      short loc_14000CA0E
0x14000c9d6  call    cs:__imp_GetLastError
0x14000c9dc  mov     ebx, eax
0x14000c9de  xor     r9d, r9d; msWindowLength
0x14000c9e1  xor     r8d, r8d; msPeriod
0x14000c9e4  xor     edx, edx; pftDueTime
0x14000c9e6  mov     rcx, rsi; pti
0x14000c9e9  call    cs:__imp_SetThreadpoolTimer
0x14000c9ef  mov     edx, 1; fCancelPendingCallbacks
0x14000c9f4  mov     rcx, rsi; pti
0x14000c9f7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000c9fd  mov     rcx, rsi; pti
0x14000ca00  call    cs:__imp_CloseThreadpoolTimer
0x14000ca06  mov     ecx, ebx; dwErrCode
0x14000ca08  call    cs:__imp_SetLastError
0x14000ca0e  mov     qword ptr [rdi+30h], 0
0x14000ca16  mov     rsi, [rdi+38h]
0x14000ca1a  test    rsi, rsi
0x14000ca1d  jz      short loc_14000CA57
0x14000ca1f  call    cs:__imp_GetLastError
0x14000ca25  mov     ebx, eax
0x14000ca27  xor     r9d, r9d; msWindowLength
0x14000ca2a  xor     r8d, r8d; msPeriod
0x14000ca2d  xor     edx, edx; pftDueTime
0x14000ca2f  mov     rcx, rsi; pti
0x14000ca32  call    cs:__imp_SetThreadpoolTimer
0x14000ca38  mov     edx, 1; fCancelPendingCallbacks
0x14000ca3d  mov     rcx, rsi; pti
0x14000ca40  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000ca46  mov     rcx, rsi; pti
0x14000ca49  call    cs:__imp_CloseThreadpoolTimer
0x14000ca4f  mov     ecx, ebx; dwErrCode
0x14000ca51  call    cs:__imp_SetLastError
0x14000ca57  mov     qword ptr [rdi+38h], 0
0x14000ca5f  mov     rbx, [rdi+100h]
0x14000ca66  mov     qword ptr [rdi+100h], 0
0x14000ca71  test    rbx, rbx
0x14000ca74  jz      short loc_14000CA8A
0x14000ca76  call    cs:__imp_GetProcessHeap
0x14000ca7c  mov     rcx, rax; hHeap
0x14000ca7f  mov     r8, rbx; lpMem
0x14000ca82  xor     edx, edx; dwFlags
0x14000ca84  call    cs:__imp_HeapFree
0x14000ca8a  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x14000ca91  test    r8, r8
0x14000ca94  jz      short loc_14000CAAE
0x14000ca96  mov     rdx, cs:qword_14007D948; SRWLock
0x14000ca9d  test    rdx, rdx
0x14000caa0  jz      short loc_14000CAAE
0x14000caa2  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14000caa9  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x14000caae  lea     rbx, [rdi+98h]
0x14000cab5  mov     rsi, [rbx+40h]
0x14000cab9  mov     qword ptr [rbx+40h], 0
0x14000cac1  test    rsi, rsi
0x14000cac4  jz      short loc_14000CADA
0x14000cac6  call    cs:__imp_GetProcessHeap
0x14000cacc  mov     rcx, rax; hHeap
0x14000cacf  mov     r8, rsi; lpMem
0x14000cad2  xor     edx, edx; dwFlags
0x14000cad4  call    cs:__imp_HeapFree
0x14000cada  mov     rcx, rbx; lpCriticalSection
0x14000cadd  call    cs:__imp_DeleteCriticalSection
0x14000cae3  lea     rcx, [rdi+90h]
0x14000caea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14000caef  mov     rsi, [rdi+88h]
0x14000caf6  mov     qword ptr [rdi+88h], 0
0x14000cb01  test    rsi, rsi
0x14000cb04  jz      short loc_14000CB1A
0x14000cb06  call    cs:__imp_GetProcessHeap
0x14000cb0c  mov     rcx, rax; hHeap
0x14000cb0f  mov     r8, rsi; lpMem
0x14000cb12  xor     edx, edx; dwFlags
0x14000cb14  call    cs:__imp_HeapFree
0x14000cb1a  lea     rcx, [rdi+48h]; lpCriticalSection
0x14000cb1e  call    cs:__imp_DeleteCriticalSection
0x14000cb24  mov     rbx, [rdi+38h]
0x14000cb28  test    rbx, rbx
0x14000cb2b  jz      short loc_14000CB55
0x14000cb2d  xor     r9d, r9d; msWindowLength
0x14000cb30  xor     r8d, r8d; msPeriod
0x14000cb33  xor     edx, edx; pftDueTime
0x14000cb35  mov     rcx, rbx; pti
0x14000cb38  call    cs:__imp_SetThreadpoolTimer
0x14000cb3e  mov     edx, 1; fCancelPendingCallbacks
0x14000cb43  mov     rcx, rbx; pti
0x14000cb46  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000cb4c  mov     rcx, rbx; pti
0x14000cb4f  call    cs:__imp_CloseThreadpoolTimer
0x14000cb55  mov     rbx, [rdi+30h]
0x14000cb59  test    rbx, rbx
0x14000cb5c  jz      short loc_14000CB87
0x14000cb5e  xor     r9d, r9d; msWindowLength
0x14000cb61  xor     r8d, r8d; msPeriod
0x14000cb64  xor     edx, edx; pftDueTime
0x14000cb66  mov     rcx, rbx; pti
0x14000cb69  call    cs:__imp_SetThreadpoolTimer
0x14000cb6f  mov     edx, 1; fCancelPendingCallbacks
0x14000cb74  mov     rcx, rbx; pti
0x14000cb77  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000cb7d  mov     rcx, rbx; pti
0x14000cb80  call    cs:__imp_CloseThreadpoolTimer
0x14000cb86  nop
0x14000cb87  mov     rcx, [rdi+10h]; lpMem
0x14000cb8b  test    rcx, rcx
0x14000cb8e  jz      short loc_14000CB96
0x14000cb90  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x14000cb95  nop
0x14000cb96  mov     rbx, [rsp+28h+arg_0]
0x14000cb9b  mov     rsi, [rsp+28h+arg_8]
0x14000cba0  add     rsp, 20h
0x14000cba4  pop     rdi
0x14000cba5  retn
```
