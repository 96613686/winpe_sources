# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180003b90`
- end: `0x180003d7e`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180033b90`

## callees

- `0x1800038b8`
- `0x180003b90`
- `0x1800078b4`
- `0x180008e04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003cb5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003cf6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003cb5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003cf6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cde`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003cac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003cec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003cac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003cec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003bae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003bf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003bae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003bf7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003be0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003c29`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003be0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003c29`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003bc1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003c0a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003d10`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003d41`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003bc1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003c0a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003d10`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003d41`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003bd8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003c21`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003d27`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003d58`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003bd8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003c21`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003d27`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003d58`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003bcf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003c18`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003d1e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003d4f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003bcf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003c18`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003d1e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003d4f`

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
  if ( v8 && qword_180044078 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180044078[25], qword_180044078, v8);
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
0x180003b90  mov     [rsp+arg_0], rbx
0x180003b95  mov     [rsp+arg_8], rsi
0x180003b9a  push    rdi
0x180003b9b  sub     rsp, 20h
0x180003b9f  mov     rdi, rcx
0x180003ba2  mov     byte ptr [rcx], 0
0x180003ba5  mov     rsi, [rcx+30h]
0x180003ba9  test    rsi, rsi
0x180003bac  jz      short loc_180003BE6
0x180003bae  call    cs:__imp_GetLastError
0x180003bb4  mov     ebx, eax
0x180003bb6  xor     r9d, r9d; msWindowLength
0x180003bb9  xor     r8d, r8d; msPeriod
0x180003bbc  xor     edx, edx; pftDueTime
0x180003bbe  mov     rcx, rsi; pti
0x180003bc1  call    cs:__imp_SetThreadpoolTimer
0x180003bc7  mov     edx, 1; fCancelPendingCallbacks
0x180003bcc  mov     rcx, rsi; pti
0x180003bcf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003bd5  mov     rcx, rsi; pti
0x180003bd8  call    cs:__imp_CloseThreadpoolTimer
0x180003bde  mov     ecx, ebx; dwErrCode
0x180003be0  call    cs:__imp_SetLastError
0x180003be6  mov     qword ptr [rdi+30h], 0
0x180003bee  mov     rsi, [rdi+38h]
0x180003bf2  test    rsi, rsi
0x180003bf5  jz      short loc_180003C2F
0x180003bf7  call    cs:__imp_GetLastError
0x180003bfd  mov     ebx, eax
0x180003bff  xor     r9d, r9d; msWindowLength
0x180003c02  xor     r8d, r8d; msPeriod
0x180003c05  xor     edx, edx; pftDueTime
0x180003c07  mov     rcx, rsi; pti
0x180003c0a  call    cs:__imp_SetThreadpoolTimer
0x180003c10  mov     edx, 1; fCancelPendingCallbacks
0x180003c15  mov     rcx, rsi; pti
0x180003c18  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003c1e  mov     rcx, rsi; pti
0x180003c21  call    cs:__imp_CloseThreadpoolTimer
0x180003c27  mov     ecx, ebx; dwErrCode
0x180003c29  call    cs:__imp_SetLastError
0x180003c2f  mov     qword ptr [rdi+38h], 0
0x180003c37  mov     rbx, [rdi+100h]
0x180003c3e  mov     qword ptr [rdi+100h], 0
0x180003c49  test    rbx, rbx
0x180003c4c  jz      short loc_180003C62
0x180003c4e  call    cs:__imp_GetProcessHeap
0x180003c54  mov     rcx, rax; hHeap
0x180003c57  mov     r8, rbx; lpMem
0x180003c5a  xor     edx, edx; dwFlags
0x180003c5c  call    cs:__imp_HeapFree
0x180003c62  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180003c69  test    r8, r8
0x180003c6c  jz      short loc_180003C86
0x180003c6e  mov     rdx, cs:qword_180044078; SRWLock
0x180003c75  test    rdx, rdx
0x180003c78  jz      short loc_180003C86
0x180003c7a  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180003c81  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180003c86  lea     rbx, [rdi+98h]
0x180003c8d  mov     rsi, [rbx+40h]
0x180003c91  mov     qword ptr [rbx+40h], 0
0x180003c99  test    rsi, rsi
0x180003c9c  jz      short loc_180003CB2
0x180003c9e  call    cs:__imp_GetProcessHeap
0x180003ca4  mov     rcx, rax; hHeap
0x180003ca7  mov     r8, rsi; lpMem
0x180003caa  xor     edx, edx; dwFlags
0x180003cac  call    cs:__imp_HeapFree
0x180003cb2  mov     rcx, rbx; lpCriticalSection
0x180003cb5  call    cs:__imp_DeleteCriticalSection
0x180003cbb  lea     rcx, [rdi+90h]
0x180003cc2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180003cc7  mov     rsi, [rdi+88h]
0x180003cce  mov     qword ptr [rdi+88h], 0
0x180003cd9  test    rsi, rsi
0x180003cdc  jz      short loc_180003CF2
0x180003cde  call    cs:__imp_GetProcessHeap
0x180003ce4  mov     rcx, rax; hHeap
0x180003ce7  mov     r8, rsi; lpMem
0x180003cea  xor     edx, edx; dwFlags
0x180003cec  call    cs:__imp_HeapFree
0x180003cf2  lea     rcx, [rdi+48h]; lpCriticalSection
0x180003cf6  call    cs:__imp_DeleteCriticalSection
0x180003cfc  mov     rbx, [rdi+38h]
0x180003d00  test    rbx, rbx
0x180003d03  jz      short loc_180003D2D
0x180003d05  xor     r9d, r9d; msWindowLength
0x180003d08  xor     r8d, r8d; msPeriod
0x180003d0b  xor     edx, edx; pftDueTime
0x180003d0d  mov     rcx, rbx; pti
0x180003d10  call    cs:__imp_SetThreadpoolTimer
0x180003d16  mov     edx, 1; fCancelPendingCallbacks
0x180003d1b  mov     rcx, rbx; pti
0x180003d1e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003d24  mov     rcx, rbx; pti
0x180003d27  call    cs:__imp_CloseThreadpoolTimer
0x180003d2d  mov     rbx, [rdi+30h]
0x180003d31  test    rbx, rbx
0x180003d34  jz      short loc_180003D5F
0x180003d36  xor     r9d, r9d; msWindowLength
0x180003d39  xor     r8d, r8d; msPeriod
0x180003d3c  xor     edx, edx; pftDueTime
0x180003d3e  mov     rcx, rbx; pti
0x180003d41  call    cs:__imp_SetThreadpoolTimer
0x180003d47  mov     edx, 1; fCancelPendingCallbacks
0x180003d4c  mov     rcx, rbx; pti
0x180003d4f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003d55  mov     rcx, rbx; pti
0x180003d58  call    cs:__imp_CloseThreadpoolTimer
0x180003d5e  nop
0x180003d5f  mov     rcx, [rdi+10h]; lpMem
0x180003d63  test    rcx, rcx
0x180003d66  jz      short loc_180003D6E
0x180003d68  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180003d6d  nop
0x180003d6e  mov     rbx, [rsp+28h+arg_0]
0x180003d73  mov     rsi, [rsp+28h+arg_8]
0x180003d78  add     rsp, 20h
0x180003d7c  pop     rdi
0x180003d7d  retn
```
