# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1400040c0`
- end: `0x1400042ae`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400a7ba0`

## callees

- `0x140003e1c`
- `0x1400040c0`
- `0x140008440`
- `0x140009ae0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400041e5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140004226`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400041e5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140004226`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000417e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400041ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000420e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000417e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400041ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000420e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000418c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400041dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000421c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000418c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400041dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000421c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004110`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004159`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004110`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004159`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400040de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400040de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004127`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400040ff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140004148`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000424e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000427f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400040ff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140004148`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000424e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000427f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140004108`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140004151`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140004257`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140004288`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140004108`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140004151`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140004257`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140004288`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400040f1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000413a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004240`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004271`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400040f1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000413a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004240`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004271`

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
  if ( v8 && qword_1400C81C8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1400C81C8[25], qword_1400C81C8, v8);
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
0x1400040c0  mov     [rsp+arg_0], rbx
0x1400040c5  mov     [rsp+arg_8], rsi
0x1400040ca  push    rdi
0x1400040cb  sub     rsp, 20h
0x1400040cf  mov     rdi, rcx
0x1400040d2  mov     byte ptr [rcx], 0
0x1400040d5  mov     rsi, [rcx+30h]
0x1400040d9  test    rsi, rsi
0x1400040dc  jz      short loc_140004116
0x1400040de  call    cs:__imp_GetLastError
0x1400040e4  mov     ebx, eax
0x1400040e6  xor     r9d, r9d; msWindowLength
0x1400040e9  xor     r8d, r8d; msPeriod
0x1400040ec  xor     edx, edx; pftDueTime
0x1400040ee  mov     rcx, rsi; pti
0x1400040f1  call    cs:__imp_SetThreadpoolTimer
0x1400040f7  mov     edx, 1; fCancelPendingCallbacks
0x1400040fc  mov     rcx, rsi; pti
0x1400040ff  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140004105  mov     rcx, rsi; pti
0x140004108  call    cs:__imp_CloseThreadpoolTimer
0x14000410e  mov     ecx, ebx; dwErrCode
0x140004110  call    cs:__imp_SetLastError
0x140004116  mov     qword ptr [rdi+30h], 0
0x14000411e  mov     rsi, [rdi+38h]
0x140004122  test    rsi, rsi
0x140004125  jz      short loc_14000415F
0x140004127  call    cs:__imp_GetLastError
0x14000412d  mov     ebx, eax
0x14000412f  xor     r9d, r9d; msWindowLength
0x140004132  xor     r8d, r8d; msPeriod
0x140004135  xor     edx, edx; pftDueTime
0x140004137  mov     rcx, rsi; pti
0x14000413a  call    cs:__imp_SetThreadpoolTimer
0x140004140  mov     edx, 1; fCancelPendingCallbacks
0x140004145  mov     rcx, rsi; pti
0x140004148  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000414e  mov     rcx, rsi; pti
0x140004151  call    cs:__imp_CloseThreadpoolTimer
0x140004157  mov     ecx, ebx; dwErrCode
0x140004159  call    cs:__imp_SetLastError
0x14000415f  mov     qword ptr [rdi+38h], 0
0x140004167  mov     rbx, [rdi+100h]
0x14000416e  mov     qword ptr [rdi+100h], 0
0x140004179  test    rbx, rbx
0x14000417c  jz      short loc_140004192
0x14000417e  call    cs:__imp_GetProcessHeap
0x140004184  mov     rcx, rax; hHeap
0x140004187  mov     r8, rbx; lpMem
0x14000418a  xor     edx, edx; dwFlags
0x14000418c  call    cs:__imp_HeapFree
0x140004192  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x140004199  test    r8, r8
0x14000419c  jz      short loc_1400041B6
0x14000419e  mov     rdx, cs:qword_1400C81C8; SRWLock
0x1400041a5  test    rdx, rdx
0x1400041a8  jz      short loc_1400041B6
0x1400041aa  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1400041b1  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1400041b6  lea     rbx, [rdi+98h]
0x1400041bd  mov     rsi, [rbx+40h]
0x1400041c1  mov     qword ptr [rbx+40h], 0
0x1400041c9  test    rsi, rsi
0x1400041cc  jz      short loc_1400041E2
0x1400041ce  call    cs:__imp_GetProcessHeap
0x1400041d4  mov     rcx, rax; hHeap
0x1400041d7  mov     r8, rsi; lpMem
0x1400041da  xor     edx, edx; dwFlags
0x1400041dc  call    cs:__imp_HeapFree
0x1400041e2  mov     rcx, rbx; lpCriticalSection
0x1400041e5  call    cs:__imp_DeleteCriticalSection
0x1400041eb  lea     rcx, [rdi+90h]
0x1400041f2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400041f7  mov     rsi, [rdi+88h]
0x1400041fe  mov     qword ptr [rdi+88h], 0
0x140004209  test    rsi, rsi
0x14000420c  jz      short loc_140004222
0x14000420e  call    cs:__imp_GetProcessHeap
0x140004214  mov     rcx, rax; hHeap
0x140004217  mov     r8, rsi; lpMem
0x14000421a  xor     edx, edx; dwFlags
0x14000421c  call    cs:__imp_HeapFree
0x140004222  lea     rcx, [rdi+48h]; lpCriticalSection
0x140004226  call    cs:__imp_DeleteCriticalSection
0x14000422c  mov     rbx, [rdi+38h]
0x140004230  test    rbx, rbx
0x140004233  jz      short loc_14000425D
0x140004235  xor     r9d, r9d; msWindowLength
0x140004238  xor     r8d, r8d; msPeriod
0x14000423b  xor     edx, edx; pftDueTime
0x14000423d  mov     rcx, rbx; pti
0x140004240  call    cs:__imp_SetThreadpoolTimer
0x140004246  mov     edx, 1; fCancelPendingCallbacks
0x14000424b  mov     rcx, rbx; pti
0x14000424e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140004254  mov     rcx, rbx; pti
0x140004257  call    cs:__imp_CloseThreadpoolTimer
0x14000425d  mov     rbx, [rdi+30h]
0x140004261  test    rbx, rbx
0x140004264  jz      short loc_14000428F
0x140004266  xor     r9d, r9d; msWindowLength
0x140004269  xor     r8d, r8d; msPeriod
0x14000426c  xor     edx, edx; pftDueTime
0x14000426e  mov     rcx, rbx; pti
0x140004271  call    cs:__imp_SetThreadpoolTimer
0x140004277  mov     edx, 1; fCancelPendingCallbacks
0x14000427c  mov     rcx, rbx; pti
0x14000427f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140004285  mov     rcx, rbx; pti
0x140004288  call    cs:__imp_CloseThreadpoolTimer
0x14000428e  nop
0x14000428f  mov     rcx, [rdi+10h]; lpMem
0x140004293  test    rcx, rcx
0x140004296  jz      short loc_14000429E
0x140004298  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x14000429d  nop
0x14000429e  mov     rbx, [rsp+28h+arg_0]
0x1400042a3  mov     rsi, [rsp+28h+arg_8]
0x1400042a8  add     rsp, 20h
0x1400042ac  pop     rdi
0x1400042ad  retn
```
