# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000326c`
- end: `0x18000345a`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800107a0`

## callees

- `0x180003128`
- `0x18000326c`
- `0x180006a90`
- `0x180007e90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003391`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800033d2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003391`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800033d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003338`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003388`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800033c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003338`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003388`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800033c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000332a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000337a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800033ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000332a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000337a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800033ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000328a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000328a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800032bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003305`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800032bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003305`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800032b4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800032fd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003403`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003434`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800032b4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800032fd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003403`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003434`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000329d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800032e6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800033ec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000341d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000329d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800032e6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800033ec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000341d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800032ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800032f4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800033fa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000342b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800032ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800032f4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800033fa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000342b`

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
  if ( v8 && qword_180017058 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180017058[25], qword_180017058, v8);
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
0x18000326c  mov     [rsp+arg_0], rbx
0x180003271  mov     [rsp+arg_8], rsi
0x180003276  push    rdi
0x180003277  sub     rsp, 20h
0x18000327b  mov     rdi, rcx
0x18000327e  mov     byte ptr [rcx], 0
0x180003281  mov     rsi, [rcx+30h]
0x180003285  test    rsi, rsi
0x180003288  jz      short loc_1800032C2
0x18000328a  call    cs:__imp_GetLastError
0x180003290  mov     ebx, eax
0x180003292  xor     r9d, r9d; msWindowLength
0x180003295  xor     r8d, r8d; msPeriod
0x180003298  xor     edx, edx; pftDueTime
0x18000329a  mov     rcx, rsi; pti
0x18000329d  call    cs:__imp_SetThreadpoolTimer
0x1800032a3  mov     edx, 1; fCancelPendingCallbacks
0x1800032a8  mov     rcx, rsi; pti
0x1800032ab  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800032b1  mov     rcx, rsi; pti
0x1800032b4  call    cs:__imp_CloseThreadpoolTimer
0x1800032ba  mov     ecx, ebx; dwErrCode
0x1800032bc  call    cs:__imp_SetLastError
0x1800032c2  mov     qword ptr [rdi+30h], 0
0x1800032ca  mov     rsi, [rdi+38h]
0x1800032ce  test    rsi, rsi
0x1800032d1  jz      short loc_18000330B
0x1800032d3  call    cs:__imp_GetLastError
0x1800032d9  mov     ebx, eax
0x1800032db  xor     r9d, r9d; msWindowLength
0x1800032de  xor     r8d, r8d; msPeriod
0x1800032e1  xor     edx, edx; pftDueTime
0x1800032e3  mov     rcx, rsi; pti
0x1800032e6  call    cs:__imp_SetThreadpoolTimer
0x1800032ec  mov     edx, 1; fCancelPendingCallbacks
0x1800032f1  mov     rcx, rsi; pti
0x1800032f4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800032fa  mov     rcx, rsi; pti
0x1800032fd  call    cs:__imp_CloseThreadpoolTimer
0x180003303  mov     ecx, ebx; dwErrCode
0x180003305  call    cs:__imp_SetLastError
0x18000330b  mov     qword ptr [rdi+38h], 0
0x180003313  mov     rbx, [rdi+100h]
0x18000331a  mov     qword ptr [rdi+100h], 0
0x180003325  test    rbx, rbx
0x180003328  jz      short loc_18000333E
0x18000332a  call    cs:__imp_GetProcessHeap
0x180003330  mov     rcx, rax; hHeap
0x180003333  mov     r8, rbx; lpMem
0x180003336  xor     edx, edx; dwFlags
0x180003338  call    cs:__imp_HeapFree
0x18000333e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180003345  test    r8, r8
0x180003348  jz      short loc_180003362
0x18000334a  mov     rdx, cs:qword_180017058; SRWLock
0x180003351  test    rdx, rdx
0x180003354  jz      short loc_180003362
0x180003356  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000335d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180003362  lea     rbx, [rdi+98h]
0x180003369  mov     rsi, [rbx+40h]
0x18000336d  mov     qword ptr [rbx+40h], 0
0x180003375  test    rsi, rsi
0x180003378  jz      short loc_18000338E
0x18000337a  call    cs:__imp_GetProcessHeap
0x180003380  mov     rcx, rax; hHeap
0x180003383  mov     r8, rsi; lpMem
0x180003386  xor     edx, edx; dwFlags
0x180003388  call    cs:__imp_HeapFree
0x18000338e  mov     rcx, rbx; lpCriticalSection
0x180003391  call    cs:__imp_DeleteCriticalSection
0x180003397  lea     rcx, [rdi+90h]
0x18000339e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800033a3  mov     rsi, [rdi+88h]
0x1800033aa  mov     qword ptr [rdi+88h], 0
0x1800033b5  test    rsi, rsi
0x1800033b8  jz      short loc_1800033CE
0x1800033ba  call    cs:__imp_GetProcessHeap
0x1800033c0  mov     rcx, rax; hHeap
0x1800033c3  mov     r8, rsi; lpMem
0x1800033c6  xor     edx, edx; dwFlags
0x1800033c8  call    cs:__imp_HeapFree
0x1800033ce  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800033d2  call    cs:__imp_DeleteCriticalSection
0x1800033d8  mov     rbx, [rdi+38h]
0x1800033dc  test    rbx, rbx
0x1800033df  jz      short loc_180003409
0x1800033e1  xor     r9d, r9d; msWindowLength
0x1800033e4  xor     r8d, r8d; msPeriod
0x1800033e7  xor     edx, edx; pftDueTime
0x1800033e9  mov     rcx, rbx; pti
0x1800033ec  call    cs:__imp_SetThreadpoolTimer
0x1800033f2  mov     edx, 1; fCancelPendingCallbacks
0x1800033f7  mov     rcx, rbx; pti
0x1800033fa  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003400  mov     rcx, rbx; pti
0x180003403  call    cs:__imp_CloseThreadpoolTimer
0x180003409  mov     rbx, [rdi+30h]
0x18000340d  test    rbx, rbx
0x180003410  jz      short loc_18000343B
0x180003412  xor     r9d, r9d; msWindowLength
0x180003415  xor     r8d, r8d; msPeriod
0x180003418  xor     edx, edx; pftDueTime
0x18000341a  mov     rcx, rbx; pti
0x18000341d  call    cs:__imp_SetThreadpoolTimer
0x180003423  mov     edx, 1; fCancelPendingCallbacks
0x180003428  mov     rcx, rbx; pti
0x18000342b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003431  mov     rcx, rbx; pti
0x180003434  call    cs:__imp_CloseThreadpoolTimer
0x18000343a  nop
0x18000343b  mov     rcx, [rdi+10h]; lpMem
0x18000343f  test    rcx, rcx
0x180003442  jz      short loc_18000344A
0x180003444  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180003449  nop
0x18000344a  mov     rbx, [rsp+28h+arg_0]
0x18000344f  mov     rsi, [rsp+28h+arg_8]
0x180003454  add     rsp, 20h
0x180003458  pop     rdi
0x180003459  retn
```
