# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180011114`
- end: `0x180011302`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001a140`

## callees

- `0x180010e70`
- `0x180011114`
- `0x1800150cc`
- `0x180015cf4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011239`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001127a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011239`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001127a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011164`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800111ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011164`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800111ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011132`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001117b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011132`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001117b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800111d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011222`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011262`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800111d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011222`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011262`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800111e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011230`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011270`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800111e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011230`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011270`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011153`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001119c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800112a2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800112d3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011153`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001119c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800112a2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800112d3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001115c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800111a5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800112ab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800112dc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001115c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800111a5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800112ab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800112dc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011145`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001118e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011294`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800112c5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011145`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001118e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011294`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800112c5`

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
  if ( v8 && qword_1800271B0 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800271B0[25], qword_1800271B0, v8);
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
0x180011114  mov     [rsp+arg_0], rbx
0x180011119  mov     [rsp+arg_8], rsi
0x18001111e  push    rdi
0x18001111f  sub     rsp, 20h
0x180011123  mov     rdi, rcx
0x180011126  mov     byte ptr [rcx], 0
0x180011129  mov     rsi, [rcx+30h]
0x18001112d  test    rsi, rsi
0x180011130  jz      short loc_18001116A
0x180011132  call    cs:__imp_GetLastError
0x180011138  mov     ebx, eax
0x18001113a  xor     r9d, r9d; msWindowLength
0x18001113d  xor     r8d, r8d; msPeriod
0x180011140  xor     edx, edx; pftDueTime
0x180011142  mov     rcx, rsi; pti
0x180011145  call    cs:__imp_SetThreadpoolTimer
0x18001114b  mov     edx, 1; fCancelPendingCallbacks
0x180011150  mov     rcx, rsi; pti
0x180011153  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180011159  mov     rcx, rsi; pti
0x18001115c  call    cs:__imp_CloseThreadpoolTimer
0x180011162  mov     ecx, ebx; dwErrCode
0x180011164  call    cs:__imp_SetLastError
0x18001116a  mov     qword ptr [rdi+30h], 0
0x180011172  mov     rsi, [rdi+38h]
0x180011176  test    rsi, rsi
0x180011179  jz      short loc_1800111B3
0x18001117b  call    cs:__imp_GetLastError
0x180011181  mov     ebx, eax
0x180011183  xor     r9d, r9d; msWindowLength
0x180011186  xor     r8d, r8d; msPeriod
0x180011189  xor     edx, edx; pftDueTime
0x18001118b  mov     rcx, rsi; pti
0x18001118e  call    cs:__imp_SetThreadpoolTimer
0x180011194  mov     edx, 1; fCancelPendingCallbacks
0x180011199  mov     rcx, rsi; pti
0x18001119c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800111a2  mov     rcx, rsi; pti
0x1800111a5  call    cs:__imp_CloseThreadpoolTimer
0x1800111ab  mov     ecx, ebx; dwErrCode
0x1800111ad  call    cs:__imp_SetLastError
0x1800111b3  mov     qword ptr [rdi+38h], 0
0x1800111bb  mov     rbx, [rdi+100h]
0x1800111c2  mov     qword ptr [rdi+100h], 0
0x1800111cd  test    rbx, rbx
0x1800111d0  jz      short loc_1800111E6
0x1800111d2  call    cs:__imp_GetProcessHeap
0x1800111d8  mov     rcx, rax; hHeap
0x1800111db  mov     r8, rbx; lpMem
0x1800111de  xor     edx, edx; dwFlags
0x1800111e0  call    cs:__imp_HeapFree
0x1800111e6  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800111ed  test    r8, r8
0x1800111f0  jz      short loc_18001120A
0x1800111f2  mov     rdx, cs:qword_1800271B0; SRWLock
0x1800111f9  test    rdx, rdx
0x1800111fc  jz      short loc_18001120A
0x1800111fe  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180011205  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18001120a  lea     rbx, [rdi+98h]
0x180011211  mov     rsi, [rbx+40h]
0x180011215  mov     qword ptr [rbx+40h], 0
0x18001121d  test    rsi, rsi
0x180011220  jz      short loc_180011236
0x180011222  call    cs:__imp_GetProcessHeap
0x180011228  mov     rcx, rax; hHeap
0x18001122b  mov     r8, rsi; lpMem
0x18001122e  xor     edx, edx; dwFlags
0x180011230  call    cs:__imp_HeapFree
0x180011236  mov     rcx, rbx; lpCriticalSection
0x180011239  call    cs:__imp_DeleteCriticalSection
0x18001123f  lea     rcx, [rdi+90h]
0x180011246  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001124b  mov     rsi, [rdi+88h]
0x180011252  mov     qword ptr [rdi+88h], 0
0x18001125d  test    rsi, rsi
0x180011260  jz      short loc_180011276
0x180011262  call    cs:__imp_GetProcessHeap
0x180011268  mov     rcx, rax; hHeap
0x18001126b  mov     r8, rsi; lpMem
0x18001126e  xor     edx, edx; dwFlags
0x180011270  call    cs:__imp_HeapFree
0x180011276  lea     rcx, [rdi+48h]; lpCriticalSection
0x18001127a  call    cs:__imp_DeleteCriticalSection
0x180011280  mov     rbx, [rdi+38h]
0x180011284  test    rbx, rbx
0x180011287  jz      short loc_1800112B1
0x180011289  xor     r9d, r9d; msWindowLength
0x18001128c  xor     r8d, r8d; msPeriod
0x18001128f  xor     edx, edx; pftDueTime
0x180011291  mov     rcx, rbx; pti
0x180011294  call    cs:__imp_SetThreadpoolTimer
0x18001129a  mov     edx, 1; fCancelPendingCallbacks
0x18001129f  mov     rcx, rbx; pti
0x1800112a2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800112a8  mov     rcx, rbx; pti
0x1800112ab  call    cs:__imp_CloseThreadpoolTimer
0x1800112b1  mov     rbx, [rdi+30h]
0x1800112b5  test    rbx, rbx
0x1800112b8  jz      short loc_1800112E3
0x1800112ba  xor     r9d, r9d; msWindowLength
0x1800112bd  xor     r8d, r8d; msPeriod
0x1800112c0  xor     edx, edx; pftDueTime
0x1800112c2  mov     rcx, rbx; pti
0x1800112c5  call    cs:__imp_SetThreadpoolTimer
0x1800112cb  mov     edx, 1; fCancelPendingCallbacks
0x1800112d0  mov     rcx, rbx; pti
0x1800112d3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800112d9  mov     rcx, rbx; pti
0x1800112dc  call    cs:__imp_CloseThreadpoolTimer
0x1800112e2  nop
0x1800112e3  mov     rcx, [rdi+10h]; lpMem
0x1800112e7  test    rcx, rcx
0x1800112ea  jz      short loc_1800112F2
0x1800112ec  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800112f1  nop
0x1800112f2  mov     rbx, [rsp+28h+arg_0]
0x1800112f7  mov     rsi, [rsp+28h+arg_8]
0x1800112fc  add     rsp, 20h
0x180011300  pop     rdi
0x180011301  retn
```
