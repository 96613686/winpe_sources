# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180005ac0`
- end: `0x180005ca5`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `485`
- prototype: `void __fastcall(wil::details::FeatureStateManager *this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180032e70`

## callees

- `0x180005804`
- `0x180005ac0`
- `0x180009e08`
- `0x18000b804`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005bdc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005c1d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005bdc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005c1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b88`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005bc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b88`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005bc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c05`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b96`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005bd3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b96`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005bd3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ae8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ae8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005b1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005b63`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005b1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005b63`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005afb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005b44`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005c37`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005c68`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005afb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005b44`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005c37`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005c68`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005b12`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005b5b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005c4e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005c7f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005b12`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005b5b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005c4e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005c7f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005b09`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005b52`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005c45`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005c76`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005b09`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005b52`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005c45`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005c76`

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
0x180005ac0  push    rdi
0x180005ac2  sub     rsp, 30h
0x180005ac6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180005acf  mov     [rsp+38h+arg_0], rbx
0x180005ad4  mov     [rsp+38h+arg_8], rsi
0x180005ad9  mov     rdi, rcx
0x180005adc  mov     byte ptr [rcx], 0
0x180005adf  mov     rsi, [rcx+30h]
0x180005ae3  test    rsi, rsi
0x180005ae6  jz      short loc_180005B20
0x180005ae8  call    cs:__imp_GetLastError
0x180005aee  mov     ebx, eax
0x180005af0  xor     r9d, r9d; msWindowLength
0x180005af3  xor     r8d, r8d; msPeriod
0x180005af6  xor     edx, edx; pftDueTime
0x180005af8  mov     rcx, rsi; pti
0x180005afb  call    cs:__imp_SetThreadpoolTimer
0x180005b01  mov     edx, 1; fCancelPendingCallbacks
0x180005b06  mov     rcx, rsi; pti
0x180005b09  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005b0f  mov     rcx, rsi; pti
0x180005b12  call    cs:__imp_CloseThreadpoolTimer
0x180005b18  mov     ecx, ebx; dwErrCode
0x180005b1a  call    cs:__imp_SetLastError
0x180005b20  mov     qword ptr [rdi+30h], 0
0x180005b28  mov     rsi, [rdi+38h]
0x180005b2c  test    rsi, rsi
0x180005b2f  jz      short loc_180005B69
0x180005b31  call    cs:__imp_GetLastError
0x180005b37  mov     ebx, eax
0x180005b39  xor     r9d, r9d; msWindowLength
0x180005b3c  xor     r8d, r8d; msPeriod
0x180005b3f  xor     edx, edx; pftDueTime
0x180005b41  mov     rcx, rsi; pti
0x180005b44  call    cs:__imp_SetThreadpoolTimer
0x180005b4a  mov     edx, 1; fCancelPendingCallbacks
0x180005b4f  mov     rcx, rsi; pti
0x180005b52  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005b58  mov     rcx, rsi; pti
0x180005b5b  call    cs:__imp_CloseThreadpoolTimer
0x180005b61  mov     ecx, ebx; dwErrCode
0x180005b63  call    cs:__imp_SetLastError
0x180005b69  mov     qword ptr [rdi+38h], 0
0x180005b71  mov     rbx, [rdi+100h]
0x180005b78  mov     qword ptr [rdi+100h], 0
0x180005b83  test    rbx, rbx
0x180005b86  jz      short loc_180005B9C
0x180005b88  call    cs:__imp_GetProcessHeap
0x180005b8e  mov     rcx, rax; hHeap
0x180005b91  mov     r8, rbx; lpMem
0x180005b94  xor     edx, edx; dwFlags
0x180005b96  call    cs:__imp_HeapFree
0x180005b9c  mov     rcx, [rdi+0E0h]; this
0x180005ba3  test    rcx, rcx
0x180005ba6  jz      short loc_180005BAD
0x180005ba8  call    ?UnsubscribeProcessWideUsageFlush@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::UnsubscribeProcessWideUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180005bad  lea     rbx, [rdi+98h]
0x180005bb4  mov     rsi, [rbx+40h]
0x180005bb8  mov     qword ptr [rbx+40h], 0
0x180005bc0  test    rsi, rsi
0x180005bc3  jz      short loc_180005BD9
0x180005bc5  call    cs:__imp_GetProcessHeap
0x180005bcb  mov     rcx, rax; hHeap
0x180005bce  mov     r8, rsi; lpMem
0x180005bd1  xor     edx, edx; dwFlags
0x180005bd3  call    cs:__imp_HeapFree
0x180005bd9  mov     rcx, rbx; lpCriticalSection
0x180005bdc  call    cs:__imp_DeleteCriticalSection
0x180005be2  lea     rcx, [rdi+90h]
0x180005be9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180005bee  mov     rsi, [rdi+88h]
0x180005bf5  mov     qword ptr [rdi+88h], 0
0x180005c00  test    rsi, rsi
0x180005c03  jz      short loc_180005C19
0x180005c05  call    cs:__imp_GetProcessHeap
0x180005c0b  mov     rcx, rax; hHeap
0x180005c0e  mov     r8, rsi; lpMem
0x180005c11  xor     edx, edx; dwFlags
0x180005c13  call    cs:__imp_HeapFree
0x180005c19  lea     rcx, [rdi+48h]; lpCriticalSection
0x180005c1d  call    cs:__imp_DeleteCriticalSection
0x180005c23  mov     rbx, [rdi+38h]
0x180005c27  test    rbx, rbx
0x180005c2a  jz      short loc_180005C54
0x180005c2c  xor     r9d, r9d; msWindowLength
0x180005c2f  xor     r8d, r8d; msPeriod
0x180005c32  xor     edx, edx; pftDueTime
0x180005c34  mov     rcx, rbx; pti
0x180005c37  call    cs:__imp_SetThreadpoolTimer
0x180005c3d  mov     edx, 1; fCancelPendingCallbacks
0x180005c42  mov     rcx, rbx; pti
0x180005c45  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005c4b  mov     rcx, rbx; pti
0x180005c4e  call    cs:__imp_CloseThreadpoolTimer
0x180005c54  mov     rbx, [rdi+30h]
0x180005c58  test    rbx, rbx
0x180005c5b  jz      short loc_180005C86
0x180005c5d  xor     r9d, r9d; msWindowLength
0x180005c60  xor     r8d, r8d; msPeriod
0x180005c63  xor     edx, edx; pftDueTime
0x180005c65  mov     rcx, rbx; pti
0x180005c68  call    cs:__imp_SetThreadpoolTimer
0x180005c6e  mov     edx, 1; fCancelPendingCallbacks
0x180005c73  mov     rcx, rbx; pti
0x180005c76  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005c7c  mov     rcx, rbx; pti
0x180005c7f  call    cs:__imp_CloseThreadpoolTimer
0x180005c85  nop
0x180005c86  mov     rcx, [rdi+10h]; lpMem
0x180005c8a  test    rcx, rcx
0x180005c8d  jz      short loc_180005C95
0x180005c8f  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180005c94  nop
0x180005c95  mov     rbx, [rsp+38h+arg_0]
0x180005c9a  mov     rsi, [rsp+38h+arg_8]
0x180005c9f  add     rsp, 30h
0x180005ca3  pop     rdi
0x180005ca4  retn
```
