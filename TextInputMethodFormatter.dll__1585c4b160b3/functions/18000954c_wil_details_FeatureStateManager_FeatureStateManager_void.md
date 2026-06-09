# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000954c`
- end: `0x18000973a`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180057e00`

## callees

- `0x180009084`
- `0x18000954c`
- `0x18000febc`
- `0x180011ac8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009671`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800096b2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009671`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800096b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009618`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009668`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800096a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009618`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009668`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800096a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000960a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000965a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000969a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000960a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000965a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000969a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000956a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000956a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000959c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800095e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000959c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800095e5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000957d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800095c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800096cc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800096fd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000957d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800095c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800096cc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800096fd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009594`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800095dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800096e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009714`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009594`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800095dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800096e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009714`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000958b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800095d4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800096da`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000970b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000958b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800095d4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800096da`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000970b`

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
  if ( v8 && qword_1800820F8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800820F8[25], qword_1800820F8, v8);
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
0x18000954c  mov     [rsp+arg_0], rbx
0x180009551  mov     [rsp+arg_8], rsi
0x180009556  push    rdi
0x180009557  sub     rsp, 20h
0x18000955b  mov     rdi, rcx
0x18000955e  mov     byte ptr [rcx], 0
0x180009561  mov     rsi, [rcx+30h]
0x180009565  test    rsi, rsi
0x180009568  jz      short loc_1800095A2
0x18000956a  call    cs:__imp_GetLastError
0x180009570  mov     ebx, eax
0x180009572  xor     r9d, r9d; msWindowLength
0x180009575  xor     r8d, r8d; msPeriod
0x180009578  xor     edx, edx; pftDueTime
0x18000957a  mov     rcx, rsi; pti
0x18000957d  call    cs:__imp_SetThreadpoolTimer
0x180009583  mov     edx, 1; fCancelPendingCallbacks
0x180009588  mov     rcx, rsi; pti
0x18000958b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009591  mov     rcx, rsi; pti
0x180009594  call    cs:__imp_CloseThreadpoolTimer
0x18000959a  mov     ecx, ebx; dwErrCode
0x18000959c  call    cs:__imp_SetLastError
0x1800095a2  mov     qword ptr [rdi+30h], 0
0x1800095aa  mov     rsi, [rdi+38h]
0x1800095ae  test    rsi, rsi
0x1800095b1  jz      short loc_1800095EB
0x1800095b3  call    cs:__imp_GetLastError
0x1800095b9  mov     ebx, eax
0x1800095bb  xor     r9d, r9d; msWindowLength
0x1800095be  xor     r8d, r8d; msPeriod
0x1800095c1  xor     edx, edx; pftDueTime
0x1800095c3  mov     rcx, rsi; pti
0x1800095c6  call    cs:__imp_SetThreadpoolTimer
0x1800095cc  mov     edx, 1; fCancelPendingCallbacks
0x1800095d1  mov     rcx, rsi; pti
0x1800095d4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800095da  mov     rcx, rsi; pti
0x1800095dd  call    cs:__imp_CloseThreadpoolTimer
0x1800095e3  mov     ecx, ebx; dwErrCode
0x1800095e5  call    cs:__imp_SetLastError
0x1800095eb  mov     qword ptr [rdi+38h], 0
0x1800095f3  mov     rbx, [rdi+100h]
0x1800095fa  mov     qword ptr [rdi+100h], 0
0x180009605  test    rbx, rbx
0x180009608  jz      short loc_18000961E
0x18000960a  call    cs:__imp_GetProcessHeap
0x180009610  mov     rcx, rax; hHeap
0x180009613  mov     r8, rbx; lpMem
0x180009616  xor     edx, edx; dwFlags
0x180009618  call    cs:__imp_HeapFree
0x18000961e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180009625  test    r8, r8
0x180009628  jz      short loc_180009642
0x18000962a  mov     rdx, cs:qword_1800820F8; SRWLock
0x180009631  test    rdx, rdx
0x180009634  jz      short loc_180009642
0x180009636  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000963d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180009642  lea     rbx, [rdi+98h]
0x180009649  mov     rsi, [rbx+40h]
0x18000964d  mov     qword ptr [rbx+40h], 0
0x180009655  test    rsi, rsi
0x180009658  jz      short loc_18000966E
0x18000965a  call    cs:__imp_GetProcessHeap
0x180009660  mov     rcx, rax; hHeap
0x180009663  mov     r8, rsi; lpMem
0x180009666  xor     edx, edx; dwFlags
0x180009668  call    cs:__imp_HeapFree
0x18000966e  mov     rcx, rbx; lpCriticalSection
0x180009671  call    cs:__imp_DeleteCriticalSection
0x180009677  lea     rcx, [rdi+90h]
0x18000967e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180009683  mov     rsi, [rdi+88h]
0x18000968a  mov     qword ptr [rdi+88h], 0
0x180009695  test    rsi, rsi
0x180009698  jz      short loc_1800096AE
0x18000969a  call    cs:__imp_GetProcessHeap
0x1800096a0  mov     rcx, rax; hHeap
0x1800096a3  mov     r8, rsi; lpMem
0x1800096a6  xor     edx, edx; dwFlags
0x1800096a8  call    cs:__imp_HeapFree
0x1800096ae  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800096b2  call    cs:__imp_DeleteCriticalSection
0x1800096b8  mov     rbx, [rdi+38h]
0x1800096bc  test    rbx, rbx
0x1800096bf  jz      short loc_1800096E9
0x1800096c1  xor     r9d, r9d; msWindowLength
0x1800096c4  xor     r8d, r8d; msPeriod
0x1800096c7  xor     edx, edx; pftDueTime
0x1800096c9  mov     rcx, rbx; pti
0x1800096cc  call    cs:__imp_SetThreadpoolTimer
0x1800096d2  mov     edx, 1; fCancelPendingCallbacks
0x1800096d7  mov     rcx, rbx; pti
0x1800096da  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800096e0  mov     rcx, rbx; pti
0x1800096e3  call    cs:__imp_CloseThreadpoolTimer
0x1800096e9  mov     rbx, [rdi+30h]
0x1800096ed  test    rbx, rbx
0x1800096f0  jz      short loc_18000971B
0x1800096f2  xor     r9d, r9d; msWindowLength
0x1800096f5  xor     r8d, r8d; msPeriod
0x1800096f8  xor     edx, edx; pftDueTime
0x1800096fa  mov     rcx, rbx; pti
0x1800096fd  call    cs:__imp_SetThreadpoolTimer
0x180009703  mov     edx, 1; fCancelPendingCallbacks
0x180009708  mov     rcx, rbx; pti
0x18000970b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009711  mov     rcx, rbx; pti
0x180009714  call    cs:__imp_CloseThreadpoolTimer
0x18000971a  nop
0x18000971b  mov     rcx, [rdi+10h]; lpMem
0x18000971f  test    rcx, rcx
0x180009722  jz      short loc_18000972A
0x180009724  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180009729  nop
0x18000972a  mov     rbx, [rsp+28h+arg_0]
0x18000972f  mov     rsi, [rsp+28h+arg_8]
0x180009734  add     rsp, 20h
0x180009738  pop     rdi
0x180009739  retn
```
