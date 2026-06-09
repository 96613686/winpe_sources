# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180014364`
- end: `0x180014552`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18006f400`

## callees

- `0x18001412c`
- `0x180014364`
- `0x180018118`
- `0x18001969c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014489`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800144ca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014489`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800144ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014430`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014480`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800144c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014430`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014480`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800144c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014422`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014472`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800144b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014422`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014472`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800144b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014382`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800143cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014382`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800143cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800143b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800143fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800143b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800143fd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800143a3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800143ec`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800144f2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014523`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800143a3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800143ec`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800144f2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014523`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800143ac`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800143f5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800144fb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001452c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800143ac`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800143f5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800144fb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001452c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014395`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800143de`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800144e4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014515`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014395`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800143de`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800144e4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014515`

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
  if ( v8 && qword_1800940F8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800940F8[25], qword_1800940F8, v8);
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
0x180014364  mov     [rsp+arg_0], rbx
0x180014369  mov     [rsp+arg_8], rsi
0x18001436e  push    rdi
0x18001436f  sub     rsp, 20h
0x180014373  mov     rdi, rcx
0x180014376  mov     byte ptr [rcx], 0
0x180014379  mov     rsi, [rcx+30h]
0x18001437d  test    rsi, rsi
0x180014380  jz      short loc_1800143BA
0x180014382  call    cs:__imp_GetLastError
0x180014388  mov     ebx, eax
0x18001438a  xor     r9d, r9d; msWindowLength
0x18001438d  xor     r8d, r8d; msPeriod
0x180014390  xor     edx, edx; pftDueTime
0x180014392  mov     rcx, rsi; pti
0x180014395  call    cs:__imp_SetThreadpoolTimer
0x18001439b  mov     edx, 1; fCancelPendingCallbacks
0x1800143a0  mov     rcx, rsi; pti
0x1800143a3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800143a9  mov     rcx, rsi; pti
0x1800143ac  call    cs:__imp_CloseThreadpoolTimer
0x1800143b2  mov     ecx, ebx; dwErrCode
0x1800143b4  call    cs:__imp_SetLastError
0x1800143ba  mov     qword ptr [rdi+30h], 0
0x1800143c2  mov     rsi, [rdi+38h]
0x1800143c6  test    rsi, rsi
0x1800143c9  jz      short loc_180014403
0x1800143cb  call    cs:__imp_GetLastError
0x1800143d1  mov     ebx, eax
0x1800143d3  xor     r9d, r9d; msWindowLength
0x1800143d6  xor     r8d, r8d; msPeriod
0x1800143d9  xor     edx, edx; pftDueTime
0x1800143db  mov     rcx, rsi; pti
0x1800143de  call    cs:__imp_SetThreadpoolTimer
0x1800143e4  mov     edx, 1; fCancelPendingCallbacks
0x1800143e9  mov     rcx, rsi; pti
0x1800143ec  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800143f2  mov     rcx, rsi; pti
0x1800143f5  call    cs:__imp_CloseThreadpoolTimer
0x1800143fb  mov     ecx, ebx; dwErrCode
0x1800143fd  call    cs:__imp_SetLastError
0x180014403  mov     qword ptr [rdi+38h], 0
0x18001440b  mov     rbx, [rdi+100h]
0x180014412  mov     qword ptr [rdi+100h], 0
0x18001441d  test    rbx, rbx
0x180014420  jz      short loc_180014436
0x180014422  call    cs:__imp_GetProcessHeap
0x180014428  mov     rcx, rax; hHeap
0x18001442b  mov     r8, rbx; lpMem
0x18001442e  xor     edx, edx; dwFlags
0x180014430  call    cs:__imp_HeapFree
0x180014436  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18001443d  test    r8, r8
0x180014440  jz      short loc_18001445A
0x180014442  mov     rdx, cs:qword_1800940F8; SRWLock
0x180014449  test    rdx, rdx
0x18001444c  jz      short loc_18001445A
0x18001444e  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180014455  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18001445a  lea     rbx, [rdi+98h]
0x180014461  mov     rsi, [rbx+40h]
0x180014465  mov     qword ptr [rbx+40h], 0
0x18001446d  test    rsi, rsi
0x180014470  jz      short loc_180014486
0x180014472  call    cs:__imp_GetProcessHeap
0x180014478  mov     rcx, rax; hHeap
0x18001447b  mov     r8, rsi; lpMem
0x18001447e  xor     edx, edx; dwFlags
0x180014480  call    cs:__imp_HeapFree
0x180014486  mov     rcx, rbx; lpCriticalSection
0x180014489  call    cs:__imp_DeleteCriticalSection
0x18001448f  lea     rcx, [rdi+90h]
0x180014496  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001449b  mov     rsi, [rdi+88h]
0x1800144a2  mov     qword ptr [rdi+88h], 0
0x1800144ad  test    rsi, rsi
0x1800144b0  jz      short loc_1800144C6
0x1800144b2  call    cs:__imp_GetProcessHeap
0x1800144b8  mov     rcx, rax; hHeap
0x1800144bb  mov     r8, rsi; lpMem
0x1800144be  xor     edx, edx; dwFlags
0x1800144c0  call    cs:__imp_HeapFree
0x1800144c6  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800144ca  call    cs:__imp_DeleteCriticalSection
0x1800144d0  mov     rbx, [rdi+38h]
0x1800144d4  test    rbx, rbx
0x1800144d7  jz      short loc_180014501
0x1800144d9  xor     r9d, r9d; msWindowLength
0x1800144dc  xor     r8d, r8d; msPeriod
0x1800144df  xor     edx, edx; pftDueTime
0x1800144e1  mov     rcx, rbx; pti
0x1800144e4  call    cs:__imp_SetThreadpoolTimer
0x1800144ea  mov     edx, 1; fCancelPendingCallbacks
0x1800144ef  mov     rcx, rbx; pti
0x1800144f2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800144f8  mov     rcx, rbx; pti
0x1800144fb  call    cs:__imp_CloseThreadpoolTimer
0x180014501  mov     rbx, [rdi+30h]
0x180014505  test    rbx, rbx
0x180014508  jz      short loc_180014533
0x18001450a  xor     r9d, r9d; msWindowLength
0x18001450d  xor     r8d, r8d; msPeriod
0x180014510  xor     edx, edx; pftDueTime
0x180014512  mov     rcx, rbx; pti
0x180014515  call    cs:__imp_SetThreadpoolTimer
0x18001451b  mov     edx, 1; fCancelPendingCallbacks
0x180014520  mov     rcx, rbx; pti
0x180014523  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180014529  mov     rcx, rbx; pti
0x18001452c  call    cs:__imp_CloseThreadpoolTimer
0x180014532  nop
0x180014533  mov     rcx, [rdi+10h]; lpMem
0x180014537  test    rcx, rcx
0x18001453a  jz      short loc_180014542
0x18001453c  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180014541  nop
0x180014542  mov     rbx, [rsp+28h+arg_0]
0x180014547  mov     rsi, [rsp+28h+arg_8]
0x18001454c  add     rsp, 20h
0x180014550  pop     rdi
0x180014551  retn
```
