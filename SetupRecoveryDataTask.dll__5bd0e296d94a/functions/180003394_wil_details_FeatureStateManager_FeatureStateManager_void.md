# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180003394`
- end: `0x18000356f`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `475`
- prototype: `void __fastcall(wil::details::FeatureStateManager *this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000cca0`

## callees

- `0x1800030f4`
- `0x180003394`
- `0x18000844c`
- `0x180009b50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800034a6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800034e7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800034a6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800034e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003460`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000349d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800034dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003460`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000349d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800034dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003452`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000348f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800034cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003452`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000348f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800034cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800033e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000342d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800033e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000342d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800033d3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000341c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000350f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003540`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800033d3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000341c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000350f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003540`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800033dc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003425`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003518`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003549`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800033dc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003425`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003518`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003549`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800033c5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000340e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003501`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003532`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800033c5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000340e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003501`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003532`

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
0x180003394  mov     [rsp+arg_0], rbx
0x180003399  mov     [rsp+arg_8], rsi
0x18000339e  push    rdi
0x18000339f  sub     rsp, 20h
0x1800033a3  mov     rdi, rcx
0x1800033a6  mov     byte ptr [rcx], 0
0x1800033a9  mov     rsi, [rcx+30h]
0x1800033ad  test    rsi, rsi
0x1800033b0  jz      short loc_1800033EA
0x1800033b2  call    cs:__imp_GetLastError
0x1800033b8  mov     ebx, eax
0x1800033ba  xor     r9d, r9d; msWindowLength
0x1800033bd  xor     r8d, r8d; msPeriod
0x1800033c0  xor     edx, edx; pftDueTime
0x1800033c2  mov     rcx, rsi; pti
0x1800033c5  call    cs:__imp_SetThreadpoolTimer
0x1800033cb  mov     edx, 1; fCancelPendingCallbacks
0x1800033d0  mov     rcx, rsi; pti
0x1800033d3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800033d9  mov     rcx, rsi; pti
0x1800033dc  call    cs:__imp_CloseThreadpoolTimer
0x1800033e2  mov     ecx, ebx; dwErrCode
0x1800033e4  call    cs:__imp_SetLastError
0x1800033ea  mov     qword ptr [rdi+30h], 0
0x1800033f2  mov     rsi, [rdi+38h]
0x1800033f6  test    rsi, rsi
0x1800033f9  jz      short loc_180003433
0x1800033fb  call    cs:__imp_GetLastError
0x180003401  mov     ebx, eax
0x180003403  xor     r9d, r9d; msWindowLength
0x180003406  xor     r8d, r8d; msPeriod
0x180003409  xor     edx, edx; pftDueTime
0x18000340b  mov     rcx, rsi; pti
0x18000340e  call    cs:__imp_SetThreadpoolTimer
0x180003414  mov     edx, 1; fCancelPendingCallbacks
0x180003419  mov     rcx, rsi; pti
0x18000341c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003422  mov     rcx, rsi; pti
0x180003425  call    cs:__imp_CloseThreadpoolTimer
0x18000342b  mov     ecx, ebx; dwErrCode
0x18000342d  call    cs:__imp_SetLastError
0x180003433  mov     qword ptr [rdi+38h], 0
0x18000343b  mov     rbx, [rdi+100h]
0x180003442  mov     qword ptr [rdi+100h], 0
0x18000344d  test    rbx, rbx
0x180003450  jz      short loc_180003466
0x180003452  call    cs:__imp_GetProcessHeap
0x180003458  mov     rcx, rax; hHeap
0x18000345b  mov     r8, rbx; lpMem
0x18000345e  xor     edx, edx; dwFlags
0x180003460  call    cs:__imp_HeapFree
0x180003466  mov     rcx, [rdi+0E0h]; this
0x18000346d  test    rcx, rcx
0x180003470  jz      short loc_180003477
0x180003472  call    ?UnsubscribeProcessWideUsageFlush@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::UnsubscribeProcessWideUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180003477  lea     rbx, [rdi+98h]
0x18000347e  mov     rsi, [rbx+40h]
0x180003482  mov     qword ptr [rbx+40h], 0
0x18000348a  test    rsi, rsi
0x18000348d  jz      short loc_1800034A3
0x18000348f  call    cs:__imp_GetProcessHeap
0x180003495  mov     rcx, rax; hHeap
0x180003498  mov     r8, rsi; lpMem
0x18000349b  xor     edx, edx; dwFlags
0x18000349d  call    cs:__imp_HeapFree
0x1800034a3  mov     rcx, rbx; lpCriticalSection
0x1800034a6  call    cs:__imp_DeleteCriticalSection
0x1800034ac  lea     rcx, [rdi+90h]
0x1800034b3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800034b8  mov     rsi, [rdi+88h]
0x1800034bf  mov     qword ptr [rdi+88h], 0
0x1800034ca  test    rsi, rsi
0x1800034cd  jz      short loc_1800034E3
0x1800034cf  call    cs:__imp_GetProcessHeap
0x1800034d5  mov     rcx, rax; hHeap
0x1800034d8  mov     r8, rsi; lpMem
0x1800034db  xor     edx, edx; dwFlags
0x1800034dd  call    cs:__imp_HeapFree
0x1800034e3  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800034e7  call    cs:__imp_DeleteCriticalSection
0x1800034ed  mov     rbx, [rdi+38h]
0x1800034f1  test    rbx, rbx
0x1800034f4  jz      short loc_18000351E
0x1800034f6  xor     r9d, r9d; msWindowLength
0x1800034f9  xor     r8d, r8d; msPeriod
0x1800034fc  xor     edx, edx; pftDueTime
0x1800034fe  mov     rcx, rbx; pti
0x180003501  call    cs:__imp_SetThreadpoolTimer
0x180003507  mov     edx, 1; fCancelPendingCallbacks
0x18000350c  mov     rcx, rbx; pti
0x18000350f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003515  mov     rcx, rbx; pti
0x180003518  call    cs:__imp_CloseThreadpoolTimer
0x18000351e  mov     rbx, [rdi+30h]
0x180003522  test    rbx, rbx
0x180003525  jz      short loc_180003550
0x180003527  xor     r9d, r9d; msWindowLength
0x18000352a  xor     r8d, r8d; msPeriod
0x18000352d  xor     edx, edx; pftDueTime
0x18000352f  mov     rcx, rbx; pti
0x180003532  call    cs:__imp_SetThreadpoolTimer
0x180003538  mov     edx, 1; fCancelPendingCallbacks
0x18000353d  mov     rcx, rbx; pti
0x180003540  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003546  mov     rcx, rbx; pti
0x180003549  call    cs:__imp_CloseThreadpoolTimer
0x18000354f  nop
0x180003550  mov     rcx, [rdi+10h]; lpMem
0x180003554  test    rcx, rcx
0x180003557  jz      short loc_18000355F
0x180003559  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18000355e  nop
0x18000355f  mov     rbx, [rsp+28h+arg_0]
0x180003564  mov     rsi, [rsp+28h+arg_8]
0x180003569  add     rsp, 20h
0x18000356d  pop     rdi
0x18000356e  retn
```
