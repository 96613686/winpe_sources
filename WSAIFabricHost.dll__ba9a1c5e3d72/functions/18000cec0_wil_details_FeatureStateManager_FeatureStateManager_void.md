# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000cec0`
- end: `0x18000d0ae`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800884a0`

## callees

- `0x18000cc1c`
- `0x18000cec0`
- `0x1800100dc`
- `0x180010b48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cfe5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d026`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cfe5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d026`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cf7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cfce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d00e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cf7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cfce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d00e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cf8c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cfdc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d01c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cf8c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cfdc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d01c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cf10`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cf59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cf10`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cf59`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ceff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cf48`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d04e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d07f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ceff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cf48`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d04e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d07f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cf08`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cf51`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d057`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d088`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cf08`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cf51`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d057`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d088`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cef1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cf3a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d040`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d071`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cef1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cf3a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d040`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d071`

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
  if ( v8 && qword_1800AE1F8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800AE1F8[25], qword_1800AE1F8, v8);
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
0x18000cec0  mov     [rsp+arg_0], rbx
0x18000cec5  mov     [rsp+arg_8], rsi
0x18000ceca  push    rdi
0x18000cecb  sub     rsp, 20h
0x18000cecf  mov     rdi, rcx
0x18000ced2  mov     byte ptr [rcx], 0
0x18000ced5  mov     rsi, [rcx+30h]
0x18000ced9  test    rsi, rsi
0x18000cedc  jz      short loc_18000CF16
0x18000cede  call    cs:__imp_GetLastError
0x18000cee4  mov     ebx, eax
0x18000cee6  xor     r9d, r9d; msWindowLength
0x18000cee9  xor     r8d, r8d; msPeriod
0x18000ceec  xor     edx, edx; pftDueTime
0x18000ceee  mov     rcx, rsi; pti
0x18000cef1  call    cs:__imp_SetThreadpoolTimer
0x18000cef7  mov     edx, 1; fCancelPendingCallbacks
0x18000cefc  mov     rcx, rsi; pti
0x18000ceff  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000cf05  mov     rcx, rsi; pti
0x18000cf08  call    cs:__imp_CloseThreadpoolTimer
0x18000cf0e  mov     ecx, ebx; dwErrCode
0x18000cf10  call    cs:__imp_SetLastError
0x18000cf16  mov     qword ptr [rdi+30h], 0
0x18000cf1e  mov     rsi, [rdi+38h]
0x18000cf22  test    rsi, rsi
0x18000cf25  jz      short loc_18000CF5F
0x18000cf27  call    cs:__imp_GetLastError
0x18000cf2d  mov     ebx, eax
0x18000cf2f  xor     r9d, r9d; msWindowLength
0x18000cf32  xor     r8d, r8d; msPeriod
0x18000cf35  xor     edx, edx; pftDueTime
0x18000cf37  mov     rcx, rsi; pti
0x18000cf3a  call    cs:__imp_SetThreadpoolTimer
0x18000cf40  mov     edx, 1; fCancelPendingCallbacks
0x18000cf45  mov     rcx, rsi; pti
0x18000cf48  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000cf4e  mov     rcx, rsi; pti
0x18000cf51  call    cs:__imp_CloseThreadpoolTimer
0x18000cf57  mov     ecx, ebx; dwErrCode
0x18000cf59  call    cs:__imp_SetLastError
0x18000cf5f  mov     qword ptr [rdi+38h], 0
0x18000cf67  mov     rbx, [rdi+100h]
0x18000cf6e  mov     qword ptr [rdi+100h], 0
0x18000cf79  test    rbx, rbx
0x18000cf7c  jz      short loc_18000CF92
0x18000cf7e  call    cs:__imp_GetProcessHeap
0x18000cf84  mov     rcx, rax; hHeap
0x18000cf87  mov     r8, rbx; lpMem
0x18000cf8a  xor     edx, edx; dwFlags
0x18000cf8c  call    cs:__imp_HeapFree
0x18000cf92  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18000cf99  test    r8, r8
0x18000cf9c  jz      short loc_18000CFB6
0x18000cf9e  mov     rdx, cs:qword_1800AE1F8; SRWLock
0x18000cfa5  test    rdx, rdx
0x18000cfa8  jz      short loc_18000CFB6
0x18000cfaa  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000cfb1  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000cfb6  lea     rbx, [rdi+98h]
0x18000cfbd  mov     rsi, [rbx+40h]
0x18000cfc1  mov     qword ptr [rbx+40h], 0
0x18000cfc9  test    rsi, rsi
0x18000cfcc  jz      short loc_18000CFE2
0x18000cfce  call    cs:__imp_GetProcessHeap
0x18000cfd4  mov     rcx, rax; hHeap
0x18000cfd7  mov     r8, rsi; lpMem
0x18000cfda  xor     edx, edx; dwFlags
0x18000cfdc  call    cs:__imp_HeapFree
0x18000cfe2  mov     rcx, rbx; lpCriticalSection
0x18000cfe5  call    cs:__imp_DeleteCriticalSection
0x18000cfeb  lea     rcx, [rdi+90h]
0x18000cff2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000cff7  mov     rsi, [rdi+88h]
0x18000cffe  mov     qword ptr [rdi+88h], 0
0x18000d009  test    rsi, rsi
0x18000d00c  jz      short loc_18000D022
0x18000d00e  call    cs:__imp_GetProcessHeap
0x18000d014  mov     rcx, rax; hHeap
0x18000d017  mov     r8, rsi; lpMem
0x18000d01a  xor     edx, edx; dwFlags
0x18000d01c  call    cs:__imp_HeapFree
0x18000d022  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000d026  call    cs:__imp_DeleteCriticalSection
0x18000d02c  mov     rbx, [rdi+38h]
0x18000d030  test    rbx, rbx
0x18000d033  jz      short loc_18000D05D
0x18000d035  xor     r9d, r9d; msWindowLength
0x18000d038  xor     r8d, r8d; msPeriod
0x18000d03b  xor     edx, edx; pftDueTime
0x18000d03d  mov     rcx, rbx; pti
0x18000d040  call    cs:__imp_SetThreadpoolTimer
0x18000d046  mov     edx, 1; fCancelPendingCallbacks
0x18000d04b  mov     rcx, rbx; pti
0x18000d04e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d054  mov     rcx, rbx; pti
0x18000d057  call    cs:__imp_CloseThreadpoolTimer
0x18000d05d  mov     rbx, [rdi+30h]
0x18000d061  test    rbx, rbx
0x18000d064  jz      short loc_18000D08F
0x18000d066  xor     r9d, r9d; msWindowLength
0x18000d069  xor     r8d, r8d; msPeriod
0x18000d06c  xor     edx, edx; pftDueTime
0x18000d06e  mov     rcx, rbx; pti
0x18000d071  call    cs:__imp_SetThreadpoolTimer
0x18000d077  mov     edx, 1; fCancelPendingCallbacks
0x18000d07c  mov     rcx, rbx; pti
0x18000d07f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d085  mov     rcx, rbx; pti
0x18000d088  call    cs:__imp_CloseThreadpoolTimer
0x18000d08e  nop
0x18000d08f  mov     rcx, [rdi+10h]; lpMem
0x18000d093  test    rcx, rcx
0x18000d096  jz      short loc_18000D09E
0x18000d098  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18000d09d  nop
0x18000d09e  mov     rbx, [rsp+28h+arg_0]
0x18000d0a3  mov     rsi, [rsp+28h+arg_8]
0x18000d0a8  add     rsp, 20h
0x18000d0ac  pop     rdi
0x18000d0ad  retn
```
