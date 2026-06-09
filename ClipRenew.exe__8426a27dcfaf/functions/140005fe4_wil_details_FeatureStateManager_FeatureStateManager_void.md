# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x140005fe4`
- end: `0x1400061d0`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400137c0`

## callees

- `0x140005d54`
- `0x140005fe4`
- `0x140010e70`
- `0x140011824`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140006109`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000614a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140006109`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000614a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400060a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400060f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006132`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400060a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400060f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006132`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400060b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006100`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006140`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400060b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006100`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006140`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006034`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000607d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006034`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000607d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006002`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000604b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006002`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000604b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140006023`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000606c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140006172`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400061a3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140006023`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000606c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140006172`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400061a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000602c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140006075`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000617b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400061ac`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000602c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140006075`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000617b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400061ac`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006015`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000605e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006164`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006195`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006015`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000605e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006164`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006195`

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
  if ( v8 && qword_140019068 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_140019068[25], qword_140019068, v8);
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
0x140005fe4  mov     [rsp+arg_0], rbx
0x140005fe9  mov     [rsp+arg_8], rsi
0x140005fee  push    rdi
0x140005fef  sub     rsp, 20h
0x140005ff3  mov     byte ptr [rcx], 0
0x140005ff6  mov     rdi, rcx
0x140005ff9  mov     rsi, [rcx+30h]
0x140005ffd  test    rsi, rsi
0x140006000  jz      short loc_14000603A
0x140006002  call    cs:__imp_GetLastError
0x140006008  xor     r9d, r9d; msWindowLength
0x14000600b  xor     r8d, r8d; msPeriod
0x14000600e  xor     edx, edx; pftDueTime
0x140006010  mov     rcx, rsi; pti
0x140006013  mov     ebx, eax
0x140006015  call    cs:__imp_SetThreadpoolTimer
0x14000601b  mov     edx, 1; fCancelPendingCallbacks
0x140006020  mov     rcx, rsi; pti
0x140006023  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140006029  mov     rcx, rsi; pti
0x14000602c  call    cs:__imp_CloseThreadpoolTimer
0x140006032  mov     ecx, ebx; dwErrCode
0x140006034  call    cs:__imp_SetLastError
0x14000603a  mov     qword ptr [rdi+30h], 0
0x140006042  mov     rsi, [rdi+38h]
0x140006046  test    rsi, rsi
0x140006049  jz      short loc_140006083
0x14000604b  call    cs:__imp_GetLastError
0x140006051  xor     r9d, r9d; msWindowLength
0x140006054  xor     r8d, r8d; msPeriod
0x140006057  xor     edx, edx; pftDueTime
0x140006059  mov     rcx, rsi; pti
0x14000605c  mov     ebx, eax
0x14000605e  call    cs:__imp_SetThreadpoolTimer
0x140006064  mov     edx, 1; fCancelPendingCallbacks
0x140006069  mov     rcx, rsi; pti
0x14000606c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140006072  mov     rcx, rsi; pti
0x140006075  call    cs:__imp_CloseThreadpoolTimer
0x14000607b  mov     ecx, ebx; dwErrCode
0x14000607d  call    cs:__imp_SetLastError
0x140006083  mov     qword ptr [rdi+38h], 0
0x14000608b  mov     rbx, [rdi+100h]
0x140006092  mov     qword ptr [rdi+100h], 0
0x14000609d  test    rbx, rbx
0x1400060a0  jz      short loc_1400060B6
0x1400060a2  call    cs:__imp_GetProcessHeap
0x1400060a8  mov     r8, rbx; lpMem
0x1400060ab  xor     edx, edx; dwFlags
0x1400060ad  mov     rcx, rax; hHeap
0x1400060b0  call    cs:__imp_HeapFree
0x1400060b6  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1400060bd  test    r8, r8
0x1400060c0  jz      short loc_1400060DA
0x1400060c2  mov     rdx, cs:qword_140019068; SRWLock
0x1400060c9  test    rdx, rdx
0x1400060cc  jz      short loc_1400060DA
0x1400060ce  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1400060d5  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1400060da  lea     rbx, [rdi+98h]
0x1400060e1  mov     rsi, [rbx+40h]
0x1400060e5  mov     qword ptr [rbx+40h], 0
0x1400060ed  test    rsi, rsi
0x1400060f0  jz      short loc_140006106
0x1400060f2  call    cs:__imp_GetProcessHeap
0x1400060f8  mov     r8, rsi; lpMem
0x1400060fb  xor     edx, edx; dwFlags
0x1400060fd  mov     rcx, rax; hHeap
0x140006100  call    cs:__imp_HeapFree
0x140006106  mov     rcx, rbx; lpCriticalSection
0x140006109  call    cs:__imp_DeleteCriticalSection
0x14000610f  lea     rcx, [rdi+90h]
0x140006116  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14000611b  mov     rsi, [rdi+88h]
0x140006122  mov     qword ptr [rdi+88h], 0
0x14000612d  test    rsi, rsi
0x140006130  jz      short loc_140006146
0x140006132  call    cs:__imp_GetProcessHeap
0x140006138  mov     r8, rsi; lpMem
0x14000613b  xor     edx, edx; dwFlags
0x14000613d  mov     rcx, rax; hHeap
0x140006140  call    cs:__imp_HeapFree
0x140006146  lea     rcx, [rdi+48h]; lpCriticalSection
0x14000614a  call    cs:__imp_DeleteCriticalSection
0x140006150  mov     rbx, [rdi+38h]
0x140006154  test    rbx, rbx
0x140006157  jz      short loc_140006181
0x140006159  xor     r9d, r9d; msWindowLength
0x14000615c  xor     r8d, r8d; msPeriod
0x14000615f  xor     edx, edx; pftDueTime
0x140006161  mov     rcx, rbx; pti
0x140006164  call    cs:__imp_SetThreadpoolTimer
0x14000616a  mov     edx, 1; fCancelPendingCallbacks
0x14000616f  mov     rcx, rbx; pti
0x140006172  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140006178  mov     rcx, rbx; pti
0x14000617b  call    cs:__imp_CloseThreadpoolTimer
0x140006181  mov     rbx, [rdi+30h]
0x140006185  test    rbx, rbx
0x140006188  jz      short loc_1400061B2
0x14000618a  xor     r9d, r9d; msWindowLength
0x14000618d  xor     r8d, r8d; msPeriod
0x140006190  xor     edx, edx; pftDueTime
0x140006192  mov     rcx, rbx; pti
0x140006195  call    cs:__imp_SetThreadpoolTimer
0x14000619b  mov     edx, 1; fCancelPendingCallbacks
0x1400061a0  mov     rcx, rbx; pti
0x1400061a3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400061a9  mov     rcx, rbx; pti
0x1400061ac  call    cs:__imp_CloseThreadpoolTimer
0x1400061b2  mov     rcx, [rdi+10h]; lpMem
0x1400061b6  test    rcx, rcx
0x1400061b9  jz      short loc_1400061C0
0x1400061bb  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1400061c0  mov     rbx, [rsp+28h+arg_0]
0x1400061c5  mov     rsi, [rsp+28h+arg_8]
0x1400061ca  add     rsp, 20h
0x1400061ce  pop     rdi
0x1400061cf  retn
```
