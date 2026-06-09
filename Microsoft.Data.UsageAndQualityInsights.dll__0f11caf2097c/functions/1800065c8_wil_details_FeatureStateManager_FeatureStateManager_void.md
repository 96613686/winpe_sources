# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800065c8`
- end: `0x1800067b6`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180107720`

## callees

- `0x180006324`
- `0x1800065c8`
- `0x18000a4b8`
- `0x18000badc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800066ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000672e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800066ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000672e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006694`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800066e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006724`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006694`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800066e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006724`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006686`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800066d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006716`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006686`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800066d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006716`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000662f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000662f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006618`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006661`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006618`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006661`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006610`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006659`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000675f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006790`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006610`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006659`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000675f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006790`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800065f9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006642`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006748`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006779`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800065f9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006642`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006748`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006779`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006607`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006650`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006756`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006787`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006607`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006650`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006756`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006787`

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
  if ( v8 && qword_180158658 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180158658[25], qword_180158658, v8);
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
0x1800065c8  mov     [rsp+arg_0], rbx
0x1800065cd  mov     [rsp+arg_8], rsi
0x1800065d2  push    rdi
0x1800065d3  sub     rsp, 20h
0x1800065d7  mov     rdi, rcx
0x1800065da  mov     byte ptr [rcx], 0
0x1800065dd  mov     rsi, [rcx+30h]
0x1800065e1  test    rsi, rsi
0x1800065e4  jz      short loc_18000661E
0x1800065e6  call    cs:__imp_GetLastError
0x1800065ec  mov     ebx, eax
0x1800065ee  xor     r9d, r9d; msWindowLength
0x1800065f1  xor     r8d, r8d; msPeriod
0x1800065f4  xor     edx, edx; pftDueTime
0x1800065f6  mov     rcx, rsi; pti
0x1800065f9  call    cs:__imp_SetThreadpoolTimer
0x1800065ff  mov     edx, 1; fCancelPendingCallbacks
0x180006604  mov     rcx, rsi; pti
0x180006607  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000660d  mov     rcx, rsi; pti
0x180006610  call    cs:__imp_CloseThreadpoolTimer
0x180006616  mov     ecx, ebx; dwErrCode
0x180006618  call    cs:__imp_SetLastError
0x18000661e  mov     qword ptr [rdi+30h], 0
0x180006626  mov     rsi, [rdi+38h]
0x18000662a  test    rsi, rsi
0x18000662d  jz      short loc_180006667
0x18000662f  call    cs:__imp_GetLastError
0x180006635  mov     ebx, eax
0x180006637  xor     r9d, r9d; msWindowLength
0x18000663a  xor     r8d, r8d; msPeriod
0x18000663d  xor     edx, edx; pftDueTime
0x18000663f  mov     rcx, rsi; pti
0x180006642  call    cs:__imp_SetThreadpoolTimer
0x180006648  mov     edx, 1; fCancelPendingCallbacks
0x18000664d  mov     rcx, rsi; pti
0x180006650  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006656  mov     rcx, rsi; pti
0x180006659  call    cs:__imp_CloseThreadpoolTimer
0x18000665f  mov     ecx, ebx; dwErrCode
0x180006661  call    cs:__imp_SetLastError
0x180006667  mov     qword ptr [rdi+38h], 0
0x18000666f  mov     rbx, [rdi+100h]
0x180006676  mov     qword ptr [rdi+100h], 0
0x180006681  test    rbx, rbx
0x180006684  jz      short loc_18000669A
0x180006686  call    cs:__imp_GetProcessHeap
0x18000668c  mov     rcx, rax; hHeap
0x18000668f  mov     r8, rbx; lpMem
0x180006692  xor     edx, edx; dwFlags
0x180006694  call    cs:__imp_HeapFree
0x18000669a  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800066a1  test    r8, r8
0x1800066a4  jz      short loc_1800066BE
0x1800066a6  mov     rdx, cs:qword_180158658; SRWLock
0x1800066ad  test    rdx, rdx
0x1800066b0  jz      short loc_1800066BE
0x1800066b2  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800066b9  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800066be  lea     rbx, [rdi+98h]
0x1800066c5  mov     rsi, [rbx+40h]
0x1800066c9  mov     qword ptr [rbx+40h], 0
0x1800066d1  test    rsi, rsi
0x1800066d4  jz      short loc_1800066EA
0x1800066d6  call    cs:__imp_GetProcessHeap
0x1800066dc  mov     rcx, rax; hHeap
0x1800066df  mov     r8, rsi; lpMem
0x1800066e2  xor     edx, edx; dwFlags
0x1800066e4  call    cs:__imp_HeapFree
0x1800066ea  mov     rcx, rbx; lpCriticalSection
0x1800066ed  call    cs:__imp_DeleteCriticalSection
0x1800066f3  lea     rcx, [rdi+90h]
0x1800066fa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800066ff  mov     rsi, [rdi+88h]
0x180006706  mov     qword ptr [rdi+88h], 0
0x180006711  test    rsi, rsi
0x180006714  jz      short loc_18000672A
0x180006716  call    cs:__imp_GetProcessHeap
0x18000671c  mov     rcx, rax; hHeap
0x18000671f  mov     r8, rsi; lpMem
0x180006722  xor     edx, edx; dwFlags
0x180006724  call    cs:__imp_HeapFree
0x18000672a  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000672e  call    cs:__imp_DeleteCriticalSection
0x180006734  mov     rbx, [rdi+38h]
0x180006738  test    rbx, rbx
0x18000673b  jz      short loc_180006765
0x18000673d  xor     r9d, r9d; msWindowLength
0x180006740  xor     r8d, r8d; msPeriod
0x180006743  xor     edx, edx; pftDueTime
0x180006745  mov     rcx, rbx; pti
0x180006748  call    cs:__imp_SetThreadpoolTimer
0x18000674e  mov     edx, 1; fCancelPendingCallbacks
0x180006753  mov     rcx, rbx; pti
0x180006756  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000675c  mov     rcx, rbx; pti
0x18000675f  call    cs:__imp_CloseThreadpoolTimer
0x180006765  mov     rbx, [rdi+30h]
0x180006769  test    rbx, rbx
0x18000676c  jz      short loc_180006797
0x18000676e  xor     r9d, r9d; msWindowLength
0x180006771  xor     r8d, r8d; msPeriod
0x180006774  xor     edx, edx; pftDueTime
0x180006776  mov     rcx, rbx; pti
0x180006779  call    cs:__imp_SetThreadpoolTimer
0x18000677f  mov     edx, 1; fCancelPendingCallbacks
0x180006784  mov     rcx, rbx; pti
0x180006787  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000678d  mov     rcx, rbx; pti
0x180006790  call    cs:__imp_CloseThreadpoolTimer
0x180006796  nop
0x180006797  mov     rcx, [rdi+10h]; lpMem
0x18000679b  test    rcx, rcx
0x18000679e  jz      short loc_1800067A6
0x1800067a0  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800067a5  nop
0x1800067a6  mov     rbx, [rsp+28h+arg_0]
0x1800067ab  mov     rsi, [rsp+28h+arg_8]
0x1800067b0  add     rsp, 20h
0x1800067b4  pop     rdi
0x1800067b5  retn
```
