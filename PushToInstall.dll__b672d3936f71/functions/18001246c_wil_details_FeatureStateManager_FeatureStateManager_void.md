# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18001246c`
- end: `0x18001265a`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18004ebc0`

## callees

- `0x1800121c8`
- `0x18001246c`
- `0x180014a78`
- `0x1800153ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012591`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800125d2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012591`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800125d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012538`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012588`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800125c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012538`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012588`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800125c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001252a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001257a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800125ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001252a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001257a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800125ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001248a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800124d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001248a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800124d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800124bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012505`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800124bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012505`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800124b4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800124fd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012603`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012634`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800124b4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800124fd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012603`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012634`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800124ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800124f4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800125fa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001262b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800124ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800124f4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800125fa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001262b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001249d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800124e6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800125ec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001261d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001249d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800124e6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800125ec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001261d`

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
  if ( v8 && qword_180065348 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180065348[25], qword_180065348, v8);
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
0x18001246c  mov     [rsp+arg_0], rbx
0x180012471  mov     [rsp+arg_8], rsi
0x180012476  push    rdi
0x180012477  sub     rsp, 20h
0x18001247b  mov     rdi, rcx
0x18001247e  mov     byte ptr [rcx], 0
0x180012481  mov     rsi, [rcx+30h]
0x180012485  test    rsi, rsi
0x180012488  jz      short loc_1800124C2
0x18001248a  call    cs:__imp_GetLastError
0x180012490  mov     ebx, eax
0x180012492  xor     r9d, r9d; msWindowLength
0x180012495  xor     r8d, r8d; msPeriod
0x180012498  xor     edx, edx; pftDueTime
0x18001249a  mov     rcx, rsi; pti
0x18001249d  call    cs:__imp_SetThreadpoolTimer
0x1800124a3  mov     edx, 1; fCancelPendingCallbacks
0x1800124a8  mov     rcx, rsi; pti
0x1800124ab  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800124b1  mov     rcx, rsi; pti
0x1800124b4  call    cs:__imp_CloseThreadpoolTimer
0x1800124ba  mov     ecx, ebx; dwErrCode
0x1800124bc  call    cs:__imp_SetLastError
0x1800124c2  mov     qword ptr [rdi+30h], 0
0x1800124ca  mov     rsi, [rdi+38h]
0x1800124ce  test    rsi, rsi
0x1800124d1  jz      short loc_18001250B
0x1800124d3  call    cs:__imp_GetLastError
0x1800124d9  mov     ebx, eax
0x1800124db  xor     r9d, r9d; msWindowLength
0x1800124de  xor     r8d, r8d; msPeriod
0x1800124e1  xor     edx, edx; pftDueTime
0x1800124e3  mov     rcx, rsi; pti
0x1800124e6  call    cs:__imp_SetThreadpoolTimer
0x1800124ec  mov     edx, 1; fCancelPendingCallbacks
0x1800124f1  mov     rcx, rsi; pti
0x1800124f4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800124fa  mov     rcx, rsi; pti
0x1800124fd  call    cs:__imp_CloseThreadpoolTimer
0x180012503  mov     ecx, ebx; dwErrCode
0x180012505  call    cs:__imp_SetLastError
0x18001250b  mov     qword ptr [rdi+38h], 0
0x180012513  mov     rbx, [rdi+100h]
0x18001251a  mov     qword ptr [rdi+100h], 0
0x180012525  test    rbx, rbx
0x180012528  jz      short loc_18001253E
0x18001252a  call    cs:__imp_GetProcessHeap
0x180012530  mov     rcx, rax; hHeap
0x180012533  mov     r8, rbx; lpMem
0x180012536  xor     edx, edx; dwFlags
0x180012538  call    cs:__imp_HeapFree
0x18001253e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180012545  test    r8, r8
0x180012548  jz      short loc_180012562
0x18001254a  mov     rdx, cs:qword_180065348; SRWLock
0x180012551  test    rdx, rdx
0x180012554  jz      short loc_180012562
0x180012556  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18001255d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180012562  lea     rbx, [rdi+98h]
0x180012569  mov     rsi, [rbx+40h]
0x18001256d  mov     qword ptr [rbx+40h], 0
0x180012575  test    rsi, rsi
0x180012578  jz      short loc_18001258E
0x18001257a  call    cs:__imp_GetProcessHeap
0x180012580  mov     rcx, rax; hHeap
0x180012583  mov     r8, rsi; lpMem
0x180012586  xor     edx, edx; dwFlags
0x180012588  call    cs:__imp_HeapFree
0x18001258e  mov     rcx, rbx; lpCriticalSection
0x180012591  call    cs:__imp_DeleteCriticalSection
0x180012597  lea     rcx, [rdi+90h]
0x18001259e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800125a3  mov     rsi, [rdi+88h]
0x1800125aa  mov     qword ptr [rdi+88h], 0
0x1800125b5  test    rsi, rsi
0x1800125b8  jz      short loc_1800125CE
0x1800125ba  call    cs:__imp_GetProcessHeap
0x1800125c0  mov     rcx, rax; hHeap
0x1800125c3  mov     r8, rsi; lpMem
0x1800125c6  xor     edx, edx; dwFlags
0x1800125c8  call    cs:__imp_HeapFree
0x1800125ce  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800125d2  call    cs:__imp_DeleteCriticalSection
0x1800125d8  mov     rbx, [rdi+38h]
0x1800125dc  test    rbx, rbx
0x1800125df  jz      short loc_180012609
0x1800125e1  xor     r9d, r9d; msWindowLength
0x1800125e4  xor     r8d, r8d; msPeriod
0x1800125e7  xor     edx, edx; pftDueTime
0x1800125e9  mov     rcx, rbx; pti
0x1800125ec  call    cs:__imp_SetThreadpoolTimer
0x1800125f2  mov     edx, 1; fCancelPendingCallbacks
0x1800125f7  mov     rcx, rbx; pti
0x1800125fa  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180012600  mov     rcx, rbx; pti
0x180012603  call    cs:__imp_CloseThreadpoolTimer
0x180012609  mov     rbx, [rdi+30h]
0x18001260d  test    rbx, rbx
0x180012610  jz      short loc_18001263B
0x180012612  xor     r9d, r9d; msWindowLength
0x180012615  xor     r8d, r8d; msPeriod
0x180012618  xor     edx, edx; pftDueTime
0x18001261a  mov     rcx, rbx; pti
0x18001261d  call    cs:__imp_SetThreadpoolTimer
0x180012623  mov     edx, 1; fCancelPendingCallbacks
0x180012628  mov     rcx, rbx; pti
0x18001262b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180012631  mov     rcx, rbx; pti
0x180012634  call    cs:__imp_CloseThreadpoolTimer
0x18001263a  nop
0x18001263b  mov     rcx, [rdi+10h]; lpMem
0x18001263f  test    rcx, rcx
0x180012642  jz      short loc_18001264A
0x180012644  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180012649  nop
0x18001264a  mov     rbx, [rsp+28h+arg_0]
0x18001264f  mov     rsi, [rsp+28h+arg_8]
0x180012654  add     rsp, 20h
0x180012658  pop     rdi
0x180012659  retn
```
