# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x14000bdac`
- end: `0x14000bfa4`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `504`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140012570`

## callees

- `0x14000bcb8`
- `0x14000bdac`
- `0x14000e0b0`
- `0x14000e570`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000bedb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000bf1c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000bedb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000bf1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000be82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bed2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bf12`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000be82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bed2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bf12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000be74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bec4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bf04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000be74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bec4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bf04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bdd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000be1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bdd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000be1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000be06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000be4f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000be06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000be4f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000bde7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000be30`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000bf36`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000bf67`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000bde7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000be30`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000bf36`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000bf67`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000bdf5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000be3e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000bf44`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000bf75`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000bdf5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000be3e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000bf44`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000bf75`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000bdfe`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000be47`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000bf4d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000bf7e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000bdfe`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000be47`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000bf4d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000bf7e`

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
  if ( v8 && qword_1400200D0 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1400200D0[25], qword_1400200D0, v8);
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
0x14000bdac  push    rdi
0x14000bdae  sub     rsp, 30h
0x14000bdb2  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x14000bdbb  mov     [rsp+38h+arg_0], rbx
0x14000bdc0  mov     [rsp+38h+arg_8], rsi
0x14000bdc5  mov     rdi, rcx
0x14000bdc8  mov     byte ptr [rcx], 0
0x14000bdcb  mov     rsi, [rcx+30h]
0x14000bdcf  test    rsi, rsi
0x14000bdd2  jz      short loc_14000BE0C
0x14000bdd4  call    cs:__imp_GetLastError
0x14000bdda  mov     ebx, eax
0x14000bddc  xor     r9d, r9d; msWindowLength
0x14000bddf  xor     r8d, r8d; msPeriod
0x14000bde2  xor     edx, edx; pftDueTime
0x14000bde4  mov     rcx, rsi; pti
0x14000bde7  call    cs:__imp_SetThreadpoolTimer
0x14000bded  mov     edx, 1; fCancelPendingCallbacks
0x14000bdf2  mov     rcx, rsi; pti
0x14000bdf5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000bdfb  mov     rcx, rsi; pti
0x14000bdfe  call    cs:__imp_CloseThreadpoolTimer
0x14000be04  mov     ecx, ebx; dwErrCode
0x14000be06  call    cs:__imp_SetLastError
0x14000be0c  mov     qword ptr [rdi+30h], 0
0x14000be14  mov     rsi, [rdi+38h]
0x14000be18  test    rsi, rsi
0x14000be1b  jz      short loc_14000BE55
0x14000be1d  call    cs:__imp_GetLastError
0x14000be23  mov     ebx, eax
0x14000be25  xor     r9d, r9d; msWindowLength
0x14000be28  xor     r8d, r8d; msPeriod
0x14000be2b  xor     edx, edx; pftDueTime
0x14000be2d  mov     rcx, rsi; pti
0x14000be30  call    cs:__imp_SetThreadpoolTimer
0x14000be36  mov     edx, 1; fCancelPendingCallbacks
0x14000be3b  mov     rcx, rsi; pti
0x14000be3e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000be44  mov     rcx, rsi; pti
0x14000be47  call    cs:__imp_CloseThreadpoolTimer
0x14000be4d  mov     ecx, ebx; dwErrCode
0x14000be4f  call    cs:__imp_SetLastError
0x14000be55  mov     qword ptr [rdi+38h], 0
0x14000be5d  mov     rbx, [rdi+100h]
0x14000be64  mov     qword ptr [rdi+100h], 0
0x14000be6f  test    rbx, rbx
0x14000be72  jz      short loc_14000BE88
0x14000be74  call    cs:__imp_GetProcessHeap
0x14000be7a  mov     rcx, rax; hHeap
0x14000be7d  mov     r8, rbx; lpMem
0x14000be80  xor     edx, edx; dwFlags
0x14000be82  call    cs:__imp_HeapFree
0x14000be88  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x14000be8f  test    r8, r8
0x14000be92  jz      short loc_14000BEAC
0x14000be94  mov     rdx, cs:qword_1400200D0; SRWLock
0x14000be9b  test    rdx, rdx
0x14000be9e  jz      short loc_14000BEAC
0x14000bea0  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14000bea7  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x14000beac  lea     rbx, [rdi+98h]
0x14000beb3  mov     rsi, [rbx+40h]
0x14000beb7  mov     qword ptr [rbx+40h], 0
0x14000bebf  test    rsi, rsi
0x14000bec2  jz      short loc_14000BED8
0x14000bec4  call    cs:__imp_GetProcessHeap
0x14000beca  mov     rcx, rax; hHeap
0x14000becd  mov     r8, rsi; lpMem
0x14000bed0  xor     edx, edx; dwFlags
0x14000bed2  call    cs:__imp_HeapFree
0x14000bed8  mov     rcx, rbx; lpCriticalSection
0x14000bedb  call    cs:__imp_DeleteCriticalSection
0x14000bee1  lea     rcx, [rdi+90h]
0x14000bee8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14000beed  mov     rsi, [rdi+88h]
0x14000bef4  mov     qword ptr [rdi+88h], 0
0x14000beff  test    rsi, rsi
0x14000bf02  jz      short loc_14000BF18
0x14000bf04  call    cs:__imp_GetProcessHeap
0x14000bf0a  mov     rcx, rax; hHeap
0x14000bf0d  mov     r8, rsi; lpMem
0x14000bf10  xor     edx, edx; dwFlags
0x14000bf12  call    cs:__imp_HeapFree
0x14000bf18  lea     rcx, [rdi+48h]; lpCriticalSection
0x14000bf1c  call    cs:__imp_DeleteCriticalSection
0x14000bf22  mov     rbx, [rdi+38h]
0x14000bf26  test    rbx, rbx
0x14000bf29  jz      short loc_14000BF53
0x14000bf2b  xor     r9d, r9d; msWindowLength
0x14000bf2e  xor     r8d, r8d; msPeriod
0x14000bf31  xor     edx, edx; pftDueTime
0x14000bf33  mov     rcx, rbx; pti
0x14000bf36  call    cs:__imp_SetThreadpoolTimer
0x14000bf3c  mov     edx, 1; fCancelPendingCallbacks
0x14000bf41  mov     rcx, rbx; pti
0x14000bf44  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000bf4a  mov     rcx, rbx; pti
0x14000bf4d  call    cs:__imp_CloseThreadpoolTimer
0x14000bf53  mov     rbx, [rdi+30h]
0x14000bf57  test    rbx, rbx
0x14000bf5a  jz      short loc_14000BF85
0x14000bf5c  xor     r9d, r9d; msWindowLength
0x14000bf5f  xor     r8d, r8d; msPeriod
0x14000bf62  xor     edx, edx; pftDueTime
0x14000bf64  mov     rcx, rbx; pti
0x14000bf67  call    cs:__imp_SetThreadpoolTimer
0x14000bf6d  mov     edx, 1; fCancelPendingCallbacks
0x14000bf72  mov     rcx, rbx; pti
0x14000bf75  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000bf7b  mov     rcx, rbx; pti
0x14000bf7e  call    cs:__imp_CloseThreadpoolTimer
0x14000bf84  nop
0x14000bf85  mov     rcx, [rdi+10h]; lpMem
0x14000bf89  test    rcx, rcx
0x14000bf8c  jz      short loc_14000BF94
0x14000bf8e  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x14000bf93  nop
0x14000bf94  mov     rbx, [rsp+38h+arg_0]
0x14000bf99  mov     rsi, [rsp+38h+arg_8]
0x14000bf9e  add     rsp, 30h
0x14000bfa2  pop     rdi
0x14000bfa3  retn
```
