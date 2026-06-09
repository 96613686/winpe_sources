# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180007a20`
- end: `0x180007c0e`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000be70`

## callees

- `0x1800078dc`
- `0x180007a20`
- `0x18000a370`
- `0x18000ab60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007a70`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007ab9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007a70`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007ab9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007b45`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007b86`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007b45`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007b86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ade`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b6e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ade`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007aec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007b3c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007b7c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007aec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007b3c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007b7c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007a5f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007aa8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007bae`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007bdf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007a5f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007aa8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007bae`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007bdf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007a68`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007ab1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007bb7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007be8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007a68`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007ab1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007bb7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007be8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007a51`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007a9a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007ba0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007bd1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007a51`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007a9a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007ba0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007bd1`

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
  if ( v8 && qword_180012130 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180012130[25], qword_180012130, v8);
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
0x180007a20  mov     [rsp+arg_0], rbx
0x180007a25  mov     [rsp+arg_8], rsi
0x180007a2a  push    rdi
0x180007a2b  sub     rsp, 20h
0x180007a2f  mov     rdi, rcx
0x180007a32  mov     byte ptr [rcx], 0
0x180007a35  mov     rsi, [rcx+30h]
0x180007a39  test    rsi, rsi
0x180007a3c  jz      short loc_180007A76
0x180007a3e  call    cs:__imp_GetLastError
0x180007a44  mov     ebx, eax
0x180007a46  xor     r9d, r9d; msWindowLength
0x180007a49  xor     r8d, r8d; msPeriod
0x180007a4c  xor     edx, edx; pftDueTime
0x180007a4e  mov     rcx, rsi; pti
0x180007a51  call    cs:__imp_SetThreadpoolTimer
0x180007a57  mov     edx, 1; fCancelPendingCallbacks
0x180007a5c  mov     rcx, rsi; pti
0x180007a5f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007a65  mov     rcx, rsi; pti
0x180007a68  call    cs:__imp_CloseThreadpoolTimer
0x180007a6e  mov     ecx, ebx; dwErrCode
0x180007a70  call    cs:__imp_SetLastError
0x180007a76  mov     qword ptr [rdi+30h], 0
0x180007a7e  mov     rsi, [rdi+38h]
0x180007a82  test    rsi, rsi
0x180007a85  jz      short loc_180007ABF
0x180007a87  call    cs:__imp_GetLastError
0x180007a8d  mov     ebx, eax
0x180007a8f  xor     r9d, r9d; msWindowLength
0x180007a92  xor     r8d, r8d; msPeriod
0x180007a95  xor     edx, edx; pftDueTime
0x180007a97  mov     rcx, rsi; pti
0x180007a9a  call    cs:__imp_SetThreadpoolTimer
0x180007aa0  mov     edx, 1; fCancelPendingCallbacks
0x180007aa5  mov     rcx, rsi; pti
0x180007aa8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007aae  mov     rcx, rsi; pti
0x180007ab1  call    cs:__imp_CloseThreadpoolTimer
0x180007ab7  mov     ecx, ebx; dwErrCode
0x180007ab9  call    cs:__imp_SetLastError
0x180007abf  mov     qword ptr [rdi+38h], 0
0x180007ac7  mov     rbx, [rdi+100h]
0x180007ace  mov     qword ptr [rdi+100h], 0
0x180007ad9  test    rbx, rbx
0x180007adc  jz      short loc_180007AF2
0x180007ade  call    cs:__imp_GetProcessHeap
0x180007ae4  mov     rcx, rax; hHeap
0x180007ae7  mov     r8, rbx; lpMem
0x180007aea  xor     edx, edx; dwFlags
0x180007aec  call    cs:__imp_HeapFree
0x180007af2  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180007af9  test    r8, r8
0x180007afc  jz      short loc_180007B16
0x180007afe  mov     rdx, cs:qword_180012130; SRWLock
0x180007b05  test    rdx, rdx
0x180007b08  jz      short loc_180007B16
0x180007b0a  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180007b11  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180007b16  lea     rbx, [rdi+98h]
0x180007b1d  mov     rsi, [rbx+40h]
0x180007b21  mov     qword ptr [rbx+40h], 0
0x180007b29  test    rsi, rsi
0x180007b2c  jz      short loc_180007B42
0x180007b2e  call    cs:__imp_GetProcessHeap
0x180007b34  mov     rcx, rax; hHeap
0x180007b37  mov     r8, rsi; lpMem
0x180007b3a  xor     edx, edx; dwFlags
0x180007b3c  call    cs:__imp_HeapFree
0x180007b42  mov     rcx, rbx; lpCriticalSection
0x180007b45  call    cs:__imp_DeleteCriticalSection
0x180007b4b  lea     rcx, [rdi+90h]
0x180007b52  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180007b57  mov     rsi, [rdi+88h]
0x180007b5e  mov     qword ptr [rdi+88h], 0
0x180007b69  test    rsi, rsi
0x180007b6c  jz      short loc_180007B82
0x180007b6e  call    cs:__imp_GetProcessHeap
0x180007b74  mov     rcx, rax; hHeap
0x180007b77  mov     r8, rsi; lpMem
0x180007b7a  xor     edx, edx; dwFlags
0x180007b7c  call    cs:__imp_HeapFree
0x180007b82  lea     rcx, [rdi+48h]; lpCriticalSection
0x180007b86  call    cs:__imp_DeleteCriticalSection
0x180007b8c  mov     rbx, [rdi+38h]
0x180007b90  test    rbx, rbx
0x180007b93  jz      short loc_180007BBD
0x180007b95  xor     r9d, r9d; msWindowLength
0x180007b98  xor     r8d, r8d; msPeriod
0x180007b9b  xor     edx, edx; pftDueTime
0x180007b9d  mov     rcx, rbx; pti
0x180007ba0  call    cs:__imp_SetThreadpoolTimer
0x180007ba6  mov     edx, 1; fCancelPendingCallbacks
0x180007bab  mov     rcx, rbx; pti
0x180007bae  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007bb4  mov     rcx, rbx; pti
0x180007bb7  call    cs:__imp_CloseThreadpoolTimer
0x180007bbd  mov     rbx, [rdi+30h]
0x180007bc1  test    rbx, rbx
0x180007bc4  jz      short loc_180007BEF
0x180007bc6  xor     r9d, r9d; msWindowLength
0x180007bc9  xor     r8d, r8d; msPeriod
0x180007bcc  xor     edx, edx; pftDueTime
0x180007bce  mov     rcx, rbx; pti
0x180007bd1  call    cs:__imp_SetThreadpoolTimer
0x180007bd7  mov     edx, 1; fCancelPendingCallbacks
0x180007bdc  mov     rcx, rbx; pti
0x180007bdf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007be5  mov     rcx, rbx; pti
0x180007be8  call    cs:__imp_CloseThreadpoolTimer
0x180007bee  nop
0x180007bef  mov     rcx, [rdi+10h]; lpMem
0x180007bf3  test    rcx, rcx
0x180007bf6  jz      short loc_180007BFE
0x180007bf8  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180007bfd  nop
0x180007bfe  mov     rbx, [rsp+28h+arg_0]
0x180007c03  mov     rsi, [rsp+28h+arg_8]
0x180007c08  add     rsp, 20h
0x180007c0c  pop     rdi
0x180007c0d  retn
```
