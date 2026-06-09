# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180003904`
- end: `0x180003adf`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `475`
- prototype: `void __fastcall(wil::details::FeatureStateManager *this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180010f90`

## callees

- `0x1800035e0`
- `0x180003904`
- `0x18000853c`
- `0x180009e28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003a16`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003a57`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003a16`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003a57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800039c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800039ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800039c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800039ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a3f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800039d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a4d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800039d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003922`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000396b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003922`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000396b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003954`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000399d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003954`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000399d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003935`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000397e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003a71`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003aa2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003935`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000397e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003a71`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003aa2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000394c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003995`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003a88`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003ab9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000394c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003995`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003a88`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003ab9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003943`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000398c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003a7f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003ab0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003943`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000398c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003a7f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003ab0`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(
        wil::details::FeatureStateManager *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *a2)
{
  struct _TP_TIMER *v3; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *v5; // rsi
  DWORD v6; // ebx
  void *v7; // rbx
  HANDLE ProcessHeap; // rax
  wil::details *v9; // rcx
  void *v10; // rsi
  HANDLE v11; // rax
  void *v12; // rsi
  HANDLE v13; // rax
  struct _TP_TIMER *v14; // rbx
  struct _TP_TIMER *v15; // rbx
  void *v16; // rcx

  *(_BYTE *)this = 0;
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v3 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v3, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v3, 1);
    CloseThreadpoolTimer(v3);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 6) = 0;
  v5 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v5 )
  {
    v6 = GetLastError();
    SetThreadpoolTimer(v5, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v5, 1);
    CloseThreadpoolTimer(v5);
    SetLastError(v6);
  }
  *((_QWORD *)this + 7) = 0;
  v7 = (void *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
  }
  v9 = (wil::details *)*((_QWORD *)this + 28);
  if ( v9 )
    wil::details::UnsubscribeProcessWideUsageFlush(v9, a2);
  v10 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v10 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v10);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((__int64 *)this + 18);
  v12 = (void *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v12 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v12);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v14 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v14 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 7), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v14, 1);
    CloseThreadpoolTimer(v14);
  }
  v15 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v15 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 6), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v15, 1);
    CloseThreadpoolTimer(v15);
  }
  v16 = (void *)*((_QWORD *)this + 2);
  if ( v16 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v16);
}

```

## disassembly

```asm
0x180003904  mov     [rsp+arg_0], rbx
0x180003909  mov     [rsp+arg_8], rsi
0x18000390e  push    rdi
0x18000390f  sub     rsp, 20h
0x180003913  mov     rdi, rcx
0x180003916  mov     byte ptr [rcx], 0
0x180003919  mov     rsi, [rcx+30h]
0x18000391d  test    rsi, rsi
0x180003920  jz      short loc_18000395A
0x180003922  call    cs:__imp_GetLastError
0x180003928  mov     ebx, eax
0x18000392a  xor     r9d, r9d; msWindowLength
0x18000392d  xor     r8d, r8d; msPeriod
0x180003930  xor     edx, edx; pftDueTime
0x180003932  mov     rcx, rsi; pti
0x180003935  call    cs:__imp_SetThreadpoolTimer
0x18000393b  mov     edx, 1; fCancelPendingCallbacks
0x180003940  mov     rcx, rsi; pti
0x180003943  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003949  mov     rcx, rsi; pti
0x18000394c  call    cs:__imp_CloseThreadpoolTimer
0x180003952  mov     ecx, ebx; dwErrCode
0x180003954  call    cs:__imp_SetLastError
0x18000395a  mov     qword ptr [rdi+30h], 0
0x180003962  mov     rsi, [rdi+38h]
0x180003966  test    rsi, rsi
0x180003969  jz      short loc_1800039A3
0x18000396b  call    cs:__imp_GetLastError
0x180003971  mov     ebx, eax
0x180003973  xor     r9d, r9d; msWindowLength
0x180003976  xor     r8d, r8d; msPeriod
0x180003979  xor     edx, edx; pftDueTime
0x18000397b  mov     rcx, rsi; pti
0x18000397e  call    cs:__imp_SetThreadpoolTimer
0x180003984  mov     edx, 1; fCancelPendingCallbacks
0x180003989  mov     rcx, rsi; pti
0x18000398c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003992  mov     rcx, rsi; pti
0x180003995  call    cs:__imp_CloseThreadpoolTimer
0x18000399b  mov     ecx, ebx; dwErrCode
0x18000399d  call    cs:__imp_SetLastError
0x1800039a3  mov     qword ptr [rdi+38h], 0
0x1800039ab  mov     rbx, [rdi+100h]
0x1800039b2  mov     qword ptr [rdi+100h], 0
0x1800039bd  test    rbx, rbx
0x1800039c0  jz      short loc_1800039D6
0x1800039c2  call    cs:__imp_GetProcessHeap
0x1800039c8  mov     rcx, rax; hHeap
0x1800039cb  mov     r8, rbx; lpMem
0x1800039ce  xor     edx, edx; dwFlags
0x1800039d0  call    cs:__imp_HeapFree
0x1800039d6  mov     rcx, [rdi+0E0h]; this
0x1800039dd  test    rcx, rcx
0x1800039e0  jz      short loc_1800039E7
0x1800039e2  call    ?UnsubscribeProcessWideUsageFlush@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::UnsubscribeProcessWideUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800039e7  lea     rbx, [rdi+98h]
0x1800039ee  mov     rsi, [rbx+40h]
0x1800039f2  mov     qword ptr [rbx+40h], 0
0x1800039fa  test    rsi, rsi
0x1800039fd  jz      short loc_180003A13
0x1800039ff  call    cs:__imp_GetProcessHeap
0x180003a05  mov     rcx, rax; hHeap
0x180003a08  mov     r8, rsi; lpMem
0x180003a0b  xor     edx, edx; dwFlags
0x180003a0d  call    cs:__imp_HeapFree
0x180003a13  mov     rcx, rbx; lpCriticalSection
0x180003a16  call    cs:__imp_DeleteCriticalSection
0x180003a1c  lea     rcx, [rdi+90h]
0x180003a23  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180003a28  mov     rsi, [rdi+88h]
0x180003a2f  mov     qword ptr [rdi+88h], 0
0x180003a3a  test    rsi, rsi
0x180003a3d  jz      short loc_180003A53
0x180003a3f  call    cs:__imp_GetProcessHeap
0x180003a45  mov     rcx, rax; hHeap
0x180003a48  mov     r8, rsi; lpMem
0x180003a4b  xor     edx, edx; dwFlags
0x180003a4d  call    cs:__imp_HeapFree
0x180003a53  lea     rcx, [rdi+48h]; lpCriticalSection
0x180003a57  call    cs:__imp_DeleteCriticalSection
0x180003a5d  mov     rbx, [rdi+38h]
0x180003a61  test    rbx, rbx
0x180003a64  jz      short loc_180003A8E
0x180003a66  xor     r9d, r9d; msWindowLength
0x180003a69  xor     r8d, r8d; msPeriod
0x180003a6c  xor     edx, edx; pftDueTime
0x180003a6e  mov     rcx, rbx; pti
0x180003a71  call    cs:__imp_SetThreadpoolTimer
0x180003a77  mov     edx, 1; fCancelPendingCallbacks
0x180003a7c  mov     rcx, rbx; pti
0x180003a7f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003a85  mov     rcx, rbx; pti
0x180003a88  call    cs:__imp_CloseThreadpoolTimer
0x180003a8e  mov     rbx, [rdi+30h]
0x180003a92  test    rbx, rbx
0x180003a95  jz      short loc_180003AC0
0x180003a97  xor     r9d, r9d; msWindowLength
0x180003a9a  xor     r8d, r8d; msPeriod
0x180003a9d  xor     edx, edx; pftDueTime
0x180003a9f  mov     rcx, rbx; pti
0x180003aa2  call    cs:__imp_SetThreadpoolTimer
0x180003aa8  mov     edx, 1; fCancelPendingCallbacks
0x180003aad  mov     rcx, rbx; pti
0x180003ab0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003ab6  mov     rcx, rbx; pti
0x180003ab9  call    cs:__imp_CloseThreadpoolTimer
0x180003abf  nop
0x180003ac0  mov     rcx, [rdi+10h]; lpMem
0x180003ac4  test    rcx, rcx
0x180003ac7  jz      short loc_180003ACF
0x180003ac9  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180003ace  nop
0x180003acf  mov     rbx, [rsp+28h+arg_0]
0x180003ad4  mov     rsi, [rsp+28h+arg_8]
0x180003ad9  add     rsp, 20h
0x180003add  pop     rdi
0x180003ade  retn
```
