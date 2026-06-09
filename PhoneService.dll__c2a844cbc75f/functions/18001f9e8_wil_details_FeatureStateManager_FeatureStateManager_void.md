# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18001f9e8`
- end: `0x18001fbc1`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `473`
- prototype: `void __fastcall(wil::details::FeatureStateManager *this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18008dfc0`

## callees

- `0x18001f3b8`
- `0x18001f9e8`
- `0x18002fb10`
- `0x180033b3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001fafa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001fb3b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001fafa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001fb3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fa38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fa81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fa38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fa81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa4f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001faa6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fae3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fb23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001faa6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fae3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fb23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fab4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001faf1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fb31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fab4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001faf1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fb31`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001fa19`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001fa62`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001fb55`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001fb86`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001fa19`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001fa62`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001fb55`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001fb86`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001fa30`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001fa79`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001fb6c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001fb9d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001fa30`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001fa79`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001fb6c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001fb9d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001fa27`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001fa70`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001fb63`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001fb94`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001fa27`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001fa70`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001fb63`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001fb94`

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
0x18001f9e8  mov     [rsp+arg_0], rbx
0x18001f9ed  mov     [rsp+arg_8], rsi
0x18001f9f2  push    rdi
0x18001f9f3  sub     rsp, 20h
0x18001f9f7  mov     byte ptr [rcx], 0
0x18001f9fa  mov     rdi, rcx
0x18001f9fd  mov     rsi, [rcx+30h]
0x18001fa01  test    rsi, rsi
0x18001fa04  jz      short loc_18001FA3E
0x18001fa06  call    cs:__imp_GetLastError
0x18001fa0c  xor     r9d, r9d; msWindowLength
0x18001fa0f  xor     r8d, r8d; msPeriod
0x18001fa12  xor     edx, edx; pftDueTime
0x18001fa14  mov     rcx, rsi; pti
0x18001fa17  mov     ebx, eax
0x18001fa19  call    cs:__imp_SetThreadpoolTimer
0x18001fa1f  mov     edx, 1; fCancelPendingCallbacks
0x18001fa24  mov     rcx, rsi; pti
0x18001fa27  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001fa2d  mov     rcx, rsi; pti
0x18001fa30  call    cs:__imp_CloseThreadpoolTimer
0x18001fa36  mov     ecx, ebx; dwErrCode
0x18001fa38  call    cs:__imp_SetLastError
0x18001fa3e  mov     qword ptr [rdi+30h], 0
0x18001fa46  mov     rsi, [rdi+38h]
0x18001fa4a  test    rsi, rsi
0x18001fa4d  jz      short loc_18001FA87
0x18001fa4f  call    cs:__imp_GetLastError
0x18001fa55  xor     r9d, r9d; msWindowLength
0x18001fa58  xor     r8d, r8d; msPeriod
0x18001fa5b  xor     edx, edx; pftDueTime
0x18001fa5d  mov     rcx, rsi; pti
0x18001fa60  mov     ebx, eax
0x18001fa62  call    cs:__imp_SetThreadpoolTimer
0x18001fa68  mov     edx, 1; fCancelPendingCallbacks
0x18001fa6d  mov     rcx, rsi; pti
0x18001fa70  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001fa76  mov     rcx, rsi; pti
0x18001fa79  call    cs:__imp_CloseThreadpoolTimer
0x18001fa7f  mov     ecx, ebx; dwErrCode
0x18001fa81  call    cs:__imp_SetLastError
0x18001fa87  mov     qword ptr [rdi+38h], 0
0x18001fa8f  mov     rbx, [rdi+100h]
0x18001fa96  mov     qword ptr [rdi+100h], 0
0x18001faa1  test    rbx, rbx
0x18001faa4  jz      short loc_18001FABA
0x18001faa6  call    cs:__imp_GetProcessHeap
0x18001faac  mov     r8, rbx; lpMem
0x18001faaf  xor     edx, edx; dwFlags
0x18001fab1  mov     rcx, rax; hHeap
0x18001fab4  call    cs:__imp_HeapFree
0x18001faba  mov     rcx, [rdi+0E0h]; this
0x18001fac1  test    rcx, rcx
0x18001fac4  jz      short loc_18001FACB
0x18001fac6  call    ?UnsubscribeProcessWideUsageFlush@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::UnsubscribeProcessWideUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18001facb  lea     rbx, [rdi+98h]
0x18001fad2  mov     rsi, [rbx+40h]
0x18001fad6  mov     qword ptr [rbx+40h], 0
0x18001fade  test    rsi, rsi
0x18001fae1  jz      short loc_18001FAF7
0x18001fae3  call    cs:__imp_GetProcessHeap
0x18001fae9  mov     r8, rsi; lpMem
0x18001faec  xor     edx, edx; dwFlags
0x18001faee  mov     rcx, rax; hHeap
0x18001faf1  call    cs:__imp_HeapFree
0x18001faf7  mov     rcx, rbx; lpCriticalSection
0x18001fafa  call    cs:__imp_DeleteCriticalSection
0x18001fb00  lea     rcx, [rdi+90h]
0x18001fb07  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001fb0c  mov     rsi, [rdi+88h]
0x18001fb13  mov     qword ptr [rdi+88h], 0
0x18001fb1e  test    rsi, rsi
0x18001fb21  jz      short loc_18001FB37
0x18001fb23  call    cs:__imp_GetProcessHeap
0x18001fb29  mov     r8, rsi; lpMem
0x18001fb2c  xor     edx, edx; dwFlags
0x18001fb2e  mov     rcx, rax; hHeap
0x18001fb31  call    cs:__imp_HeapFree
0x18001fb37  lea     rcx, [rdi+48h]; lpCriticalSection
0x18001fb3b  call    cs:__imp_DeleteCriticalSection
0x18001fb41  mov     rbx, [rdi+38h]
0x18001fb45  test    rbx, rbx
0x18001fb48  jz      short loc_18001FB72
0x18001fb4a  xor     r9d, r9d; msWindowLength
0x18001fb4d  xor     r8d, r8d; msPeriod
0x18001fb50  xor     edx, edx; pftDueTime
0x18001fb52  mov     rcx, rbx; pti
0x18001fb55  call    cs:__imp_SetThreadpoolTimer
0x18001fb5b  mov     edx, 1; fCancelPendingCallbacks
0x18001fb60  mov     rcx, rbx; pti
0x18001fb63  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001fb69  mov     rcx, rbx; pti
0x18001fb6c  call    cs:__imp_CloseThreadpoolTimer
0x18001fb72  mov     rbx, [rdi+30h]
0x18001fb76  test    rbx, rbx
0x18001fb79  jz      short loc_18001FBA3
0x18001fb7b  xor     r9d, r9d; msWindowLength
0x18001fb7e  xor     r8d, r8d; msPeriod
0x18001fb81  xor     edx, edx; pftDueTime
0x18001fb83  mov     rcx, rbx; pti
0x18001fb86  call    cs:__imp_SetThreadpoolTimer
0x18001fb8c  mov     edx, 1; fCancelPendingCallbacks
0x18001fb91  mov     rcx, rbx; pti
0x18001fb94  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001fb9a  mov     rcx, rbx; pti
0x18001fb9d  call    cs:__imp_CloseThreadpoolTimer
0x18001fba3  mov     rcx, [rdi+10h]; lpMem
0x18001fba7  test    rcx, rcx
0x18001fbaa  jz      short loc_18001FBB1
0x18001fbac  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18001fbb1  mov     rbx, [rsp+28h+arg_0]
0x18001fbb6  mov     rsi, [rsp+28h+arg_8]
0x18001fbbb  add     rsp, 20h
0x18001fbbf  pop     rdi
0x18001fbc0  retn
```
