# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000afe4`
- end: `0x18000b1d2`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002d2d0`

## callees

- `0x18000acd8`
- `0x18000afe4`
- `0x18000fed0`
- `0x1800119ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b109`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b14a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b109`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b14a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b0a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b0f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b132`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b0a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b0f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b132`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b0b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b100`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b140`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b0b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b100`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b002`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b04b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b002`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b04b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b034`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b07d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b034`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b07d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b023`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b06c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b172`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b1a3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b023`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b06c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b172`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b1a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b02c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b075`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b17b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b1ac`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b02c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b075`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b17b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b1ac`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b015`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b05e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b164`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b195`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b015`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b05e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b164`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b195`

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
  if ( v8 && qword_180042170 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180042170[25], qword_180042170, v8);
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
0x18000afe4  mov     [rsp+arg_0], rbx
0x18000afe9  mov     [rsp+arg_8], rsi
0x18000afee  push    rdi
0x18000afef  sub     rsp, 20h
0x18000aff3  mov     rdi, rcx
0x18000aff6  mov     byte ptr [rcx], 0
0x18000aff9  mov     rsi, [rcx+30h]
0x18000affd  test    rsi, rsi
0x18000b000  jz      short loc_18000B03A
0x18000b002  call    cs:__imp_GetLastError
0x18000b008  mov     ebx, eax
0x18000b00a  xor     r9d, r9d; msWindowLength
0x18000b00d  xor     r8d, r8d; msPeriod
0x18000b010  xor     edx, edx; pftDueTime
0x18000b012  mov     rcx, rsi; pti
0x18000b015  call    cs:__imp_SetThreadpoolTimer
0x18000b01b  mov     edx, 1; fCancelPendingCallbacks
0x18000b020  mov     rcx, rsi; pti
0x18000b023  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b029  mov     rcx, rsi; pti
0x18000b02c  call    cs:__imp_CloseThreadpoolTimer
0x18000b032  mov     ecx, ebx; dwErrCode
0x18000b034  call    cs:__imp_SetLastError
0x18000b03a  mov     qword ptr [rdi+30h], 0
0x18000b042  mov     rsi, [rdi+38h]
0x18000b046  test    rsi, rsi
0x18000b049  jz      short loc_18000B083
0x18000b04b  call    cs:__imp_GetLastError
0x18000b051  mov     ebx, eax
0x18000b053  xor     r9d, r9d; msWindowLength
0x18000b056  xor     r8d, r8d; msPeriod
0x18000b059  xor     edx, edx; pftDueTime
0x18000b05b  mov     rcx, rsi; pti
0x18000b05e  call    cs:__imp_SetThreadpoolTimer
0x18000b064  mov     edx, 1; fCancelPendingCallbacks
0x18000b069  mov     rcx, rsi; pti
0x18000b06c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b072  mov     rcx, rsi; pti
0x18000b075  call    cs:__imp_CloseThreadpoolTimer
0x18000b07b  mov     ecx, ebx; dwErrCode
0x18000b07d  call    cs:__imp_SetLastError
0x18000b083  mov     qword ptr [rdi+38h], 0
0x18000b08b  mov     rbx, [rdi+100h]
0x18000b092  mov     qword ptr [rdi+100h], 0
0x18000b09d  test    rbx, rbx
0x18000b0a0  jz      short loc_18000B0B6
0x18000b0a2  call    cs:__imp_GetProcessHeap
0x18000b0a8  mov     rcx, rax; hHeap
0x18000b0ab  mov     r8, rbx; lpMem
0x18000b0ae  xor     edx, edx; dwFlags
0x18000b0b0  call    cs:__imp_HeapFree
0x18000b0b6  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18000b0bd  test    r8, r8
0x18000b0c0  jz      short loc_18000B0DA
0x18000b0c2  mov     rdx, cs:qword_180042170; SRWLock
0x18000b0c9  test    rdx, rdx
0x18000b0cc  jz      short loc_18000B0DA
0x18000b0ce  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000b0d5  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000b0da  lea     rbx, [rdi+98h]
0x18000b0e1  mov     rsi, [rbx+40h]
0x18000b0e5  mov     qword ptr [rbx+40h], 0
0x18000b0ed  test    rsi, rsi
0x18000b0f0  jz      short loc_18000B106
0x18000b0f2  call    cs:__imp_GetProcessHeap
0x18000b0f8  mov     rcx, rax; hHeap
0x18000b0fb  mov     r8, rsi; lpMem
0x18000b0fe  xor     edx, edx; dwFlags
0x18000b100  call    cs:__imp_HeapFree
0x18000b106  mov     rcx, rbx; lpCriticalSection
0x18000b109  call    cs:__imp_DeleteCriticalSection
0x18000b10f  lea     rcx, [rdi+90h]
0x18000b116  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000b11b  mov     rsi, [rdi+88h]
0x18000b122  mov     qword ptr [rdi+88h], 0
0x18000b12d  test    rsi, rsi
0x18000b130  jz      short loc_18000B146
0x18000b132  call    cs:__imp_GetProcessHeap
0x18000b138  mov     rcx, rax; hHeap
0x18000b13b  mov     r8, rsi; lpMem
0x18000b13e  xor     edx, edx; dwFlags
0x18000b140  call    cs:__imp_HeapFree
0x18000b146  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000b14a  call    cs:__imp_DeleteCriticalSection
0x18000b150  mov     rbx, [rdi+38h]
0x18000b154  test    rbx, rbx
0x18000b157  jz      short loc_18000B181
0x18000b159  xor     r9d, r9d; msWindowLength
0x18000b15c  xor     r8d, r8d; msPeriod
0x18000b15f  xor     edx, edx; pftDueTime
0x18000b161  mov     rcx, rbx; pti
0x18000b164  call    cs:__imp_SetThreadpoolTimer
0x18000b16a  mov     edx, 1; fCancelPendingCallbacks
0x18000b16f  mov     rcx, rbx; pti
0x18000b172  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b178  mov     rcx, rbx; pti
0x18000b17b  call    cs:__imp_CloseThreadpoolTimer
0x18000b181  mov     rbx, [rdi+30h]
0x18000b185  test    rbx, rbx
0x18000b188  jz      short loc_18000B1B3
0x18000b18a  xor     r9d, r9d; msWindowLength
0x18000b18d  xor     r8d, r8d; msPeriod
0x18000b190  xor     edx, edx; pftDueTime
0x18000b192  mov     rcx, rbx; pti
0x18000b195  call    cs:__imp_SetThreadpoolTimer
0x18000b19b  mov     edx, 1; fCancelPendingCallbacks
0x18000b1a0  mov     rcx, rbx; pti
0x18000b1a3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b1a9  mov     rcx, rbx; pti
0x18000b1ac  call    cs:__imp_CloseThreadpoolTimer
0x18000b1b2  nop
0x18000b1b3  mov     rcx, [rdi+10h]; lpMem
0x18000b1b7  test    rcx, rcx
0x18000b1ba  jz      short loc_18000B1C2
0x18000b1bc  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18000b1c1  nop
0x18000b1c2  mov     rbx, [rsp+28h+arg_0]
0x18000b1c7  mov     rsi, [rsp+28h+arg_8]
0x18000b1cc  add     rsp, 20h
0x18000b1d0  pop     rdi
0x18000b1d1  retn
```
