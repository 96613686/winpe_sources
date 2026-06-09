# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800032fc`
- end: `0x1800034e8`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180026810`

## callees

- `0x1800031b8`
- `0x1800032fc`
- `0x180006920`
- `0x1800075bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003421`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003462`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003421`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003462`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800033ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000340a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000344a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800033ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000340a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000344a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800033c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003418`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003458`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800033c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003418`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003458`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000331a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003363`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000331a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003363`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000334c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003395`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000334c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003395`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000332d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003376`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000347c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800034ad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000332d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003376`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000347c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800034ad`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003344`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000338d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003493`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800034c4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003344`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000338d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003493`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800034c4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000333b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003384`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000348a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800034bb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000333b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003384`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000348a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800034bb`

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
  if ( v8 && qword_18002F1C8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18002F1C8[25], qword_18002F1C8, v8);
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
0x1800032fc  mov     [rsp+arg_0], rbx
0x180003301  mov     [rsp+arg_8], rsi
0x180003306  push    rdi
0x180003307  sub     rsp, 20h
0x18000330b  mov     byte ptr [rcx], 0
0x18000330e  mov     rdi, rcx
0x180003311  mov     rsi, [rcx+30h]
0x180003315  test    rsi, rsi
0x180003318  jz      short loc_180003352
0x18000331a  call    cs:__imp_GetLastError
0x180003320  xor     r9d, r9d; msWindowLength
0x180003323  xor     r8d, r8d; msPeriod
0x180003326  xor     edx, edx; pftDueTime
0x180003328  mov     rcx, rsi; pti
0x18000332b  mov     ebx, eax
0x18000332d  call    cs:__imp_SetThreadpoolTimer
0x180003333  mov     edx, 1; fCancelPendingCallbacks
0x180003338  mov     rcx, rsi; pti
0x18000333b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003341  mov     rcx, rsi; pti
0x180003344  call    cs:__imp_CloseThreadpoolTimer
0x18000334a  mov     ecx, ebx; dwErrCode
0x18000334c  call    cs:__imp_SetLastError
0x180003352  mov     qword ptr [rdi+30h], 0
0x18000335a  mov     rsi, [rdi+38h]
0x18000335e  test    rsi, rsi
0x180003361  jz      short loc_18000339B
0x180003363  call    cs:__imp_GetLastError
0x180003369  xor     r9d, r9d; msWindowLength
0x18000336c  xor     r8d, r8d; msPeriod
0x18000336f  xor     edx, edx; pftDueTime
0x180003371  mov     rcx, rsi; pti
0x180003374  mov     ebx, eax
0x180003376  call    cs:__imp_SetThreadpoolTimer
0x18000337c  mov     edx, 1; fCancelPendingCallbacks
0x180003381  mov     rcx, rsi; pti
0x180003384  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000338a  mov     rcx, rsi; pti
0x18000338d  call    cs:__imp_CloseThreadpoolTimer
0x180003393  mov     ecx, ebx; dwErrCode
0x180003395  call    cs:__imp_SetLastError
0x18000339b  mov     qword ptr [rdi+38h], 0
0x1800033a3  mov     rbx, [rdi+100h]
0x1800033aa  mov     qword ptr [rdi+100h], 0
0x1800033b5  test    rbx, rbx
0x1800033b8  jz      short loc_1800033CE
0x1800033ba  call    cs:__imp_GetProcessHeap
0x1800033c0  mov     r8, rbx; lpMem
0x1800033c3  xor     edx, edx; dwFlags
0x1800033c5  mov     rcx, rax; hHeap
0x1800033c8  call    cs:__imp_HeapFree
0x1800033ce  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800033d5  test    r8, r8
0x1800033d8  jz      short loc_1800033F2
0x1800033da  mov     rdx, cs:qword_18002F1C8; SRWLock
0x1800033e1  test    rdx, rdx
0x1800033e4  jz      short loc_1800033F2
0x1800033e6  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800033ed  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800033f2  lea     rbx, [rdi+98h]
0x1800033f9  mov     rsi, [rbx+40h]
0x1800033fd  mov     qword ptr [rbx+40h], 0
0x180003405  test    rsi, rsi
0x180003408  jz      short loc_18000341E
0x18000340a  call    cs:__imp_GetProcessHeap
0x180003410  mov     r8, rsi; lpMem
0x180003413  xor     edx, edx; dwFlags
0x180003415  mov     rcx, rax; hHeap
0x180003418  call    cs:__imp_HeapFree
0x18000341e  mov     rcx, rbx; lpCriticalSection
0x180003421  call    cs:__imp_DeleteCriticalSection
0x180003427  lea     rcx, [rdi+90h]
0x18000342e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180003433  mov     rsi, [rdi+88h]
0x18000343a  mov     qword ptr [rdi+88h], 0
0x180003445  test    rsi, rsi
0x180003448  jz      short loc_18000345E
0x18000344a  call    cs:__imp_GetProcessHeap
0x180003450  mov     r8, rsi; lpMem
0x180003453  xor     edx, edx; dwFlags
0x180003455  mov     rcx, rax; hHeap
0x180003458  call    cs:__imp_HeapFree
0x18000345e  lea     rcx, [rdi+48h]; lpCriticalSection
0x180003462  call    cs:__imp_DeleteCriticalSection
0x180003468  mov     rbx, [rdi+38h]
0x18000346c  test    rbx, rbx
0x18000346f  jz      short loc_180003499
0x180003471  xor     r9d, r9d; msWindowLength
0x180003474  xor     r8d, r8d; msPeriod
0x180003477  xor     edx, edx; pftDueTime
0x180003479  mov     rcx, rbx; pti
0x18000347c  call    cs:__imp_SetThreadpoolTimer
0x180003482  mov     edx, 1; fCancelPendingCallbacks
0x180003487  mov     rcx, rbx; pti
0x18000348a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003490  mov     rcx, rbx; pti
0x180003493  call    cs:__imp_CloseThreadpoolTimer
0x180003499  mov     rbx, [rdi+30h]
0x18000349d  test    rbx, rbx
0x1800034a0  jz      short loc_1800034CA
0x1800034a2  xor     r9d, r9d; msWindowLength
0x1800034a5  xor     r8d, r8d; msPeriod
0x1800034a8  xor     edx, edx; pftDueTime
0x1800034aa  mov     rcx, rbx; pti
0x1800034ad  call    cs:__imp_SetThreadpoolTimer
0x1800034b3  mov     edx, 1; fCancelPendingCallbacks
0x1800034b8  mov     rcx, rbx; pti
0x1800034bb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800034c1  mov     rcx, rbx; pti
0x1800034c4  call    cs:__imp_CloseThreadpoolTimer
0x1800034ca  mov     rcx, [rdi+10h]; lpMem
0x1800034ce  test    rcx, rcx
0x1800034d1  jz      short loc_1800034D8
0x1800034d3  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800034d8  mov     rbx, [rsp+28h+arg_0]
0x1800034dd  mov     rsi, [rsp+28h+arg_8]
0x1800034e2  add     rsp, 20h
0x1800034e6  pop     rdi
0x1800034e7  retn
```
