# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180010968`
- end: `0x180010b56`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18006e8a0`

## callees

- `0x180010570`
- `0x180010968`
- `0x1800175d8`
- `0x18001c624`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010a8d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010ace`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010a8d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010ace`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010a26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010a76`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010ab6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010a26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010a76`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010ab6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010a34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010a84`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010ac4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010a34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010a84`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010ac4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010986`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010986`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800109b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010a01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800109b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010a01`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800109b0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800109f9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010aff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010b30`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800109b0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800109f9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010aff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010b30`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010999`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800109e2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010ae8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010b19`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010999`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800109e2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010ae8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010b19`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800109a7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800109f0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010af6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010b27`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800109a7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800109f0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010af6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010b27`

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
  if ( v8 && qword_1800A42C8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800A42C8[25], qword_1800A42C8, v8);
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
0x180010968  mov     [rsp+arg_0], rbx
0x18001096d  mov     [rsp+arg_8], rsi
0x180010972  push    rdi
0x180010973  sub     rsp, 20h
0x180010977  mov     rdi, rcx
0x18001097a  mov     byte ptr [rcx], 0
0x18001097d  mov     rsi, [rcx+30h]
0x180010981  test    rsi, rsi
0x180010984  jz      short loc_1800109BE
0x180010986  call    cs:__imp_GetLastError
0x18001098c  mov     ebx, eax
0x18001098e  xor     r9d, r9d; msWindowLength
0x180010991  xor     r8d, r8d; msPeriod
0x180010994  xor     edx, edx; pftDueTime
0x180010996  mov     rcx, rsi; pti
0x180010999  call    cs:__imp_SetThreadpoolTimer
0x18001099f  mov     edx, 1; fCancelPendingCallbacks
0x1800109a4  mov     rcx, rsi; pti
0x1800109a7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800109ad  mov     rcx, rsi; pti
0x1800109b0  call    cs:__imp_CloseThreadpoolTimer
0x1800109b6  mov     ecx, ebx; dwErrCode
0x1800109b8  call    cs:__imp_SetLastError
0x1800109be  mov     qword ptr [rdi+30h], 0
0x1800109c6  mov     rsi, [rdi+38h]
0x1800109ca  test    rsi, rsi
0x1800109cd  jz      short loc_180010A07
0x1800109cf  call    cs:__imp_GetLastError
0x1800109d5  mov     ebx, eax
0x1800109d7  xor     r9d, r9d; msWindowLength
0x1800109da  xor     r8d, r8d; msPeriod
0x1800109dd  xor     edx, edx; pftDueTime
0x1800109df  mov     rcx, rsi; pti
0x1800109e2  call    cs:__imp_SetThreadpoolTimer
0x1800109e8  mov     edx, 1; fCancelPendingCallbacks
0x1800109ed  mov     rcx, rsi; pti
0x1800109f0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800109f6  mov     rcx, rsi; pti
0x1800109f9  call    cs:__imp_CloseThreadpoolTimer
0x1800109ff  mov     ecx, ebx; dwErrCode
0x180010a01  call    cs:__imp_SetLastError
0x180010a07  mov     qword ptr [rdi+38h], 0
0x180010a0f  mov     rbx, [rdi+100h]
0x180010a16  mov     qword ptr [rdi+100h], 0
0x180010a21  test    rbx, rbx
0x180010a24  jz      short loc_180010A3A
0x180010a26  call    cs:__imp_GetProcessHeap
0x180010a2c  mov     rcx, rax; hHeap
0x180010a2f  mov     r8, rbx; lpMem
0x180010a32  xor     edx, edx; dwFlags
0x180010a34  call    cs:__imp_HeapFree
0x180010a3a  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180010a41  test    r8, r8
0x180010a44  jz      short loc_180010A5E
0x180010a46  mov     rdx, cs:qword_1800A42C8; SRWLock
0x180010a4d  test    rdx, rdx
0x180010a50  jz      short loc_180010A5E
0x180010a52  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180010a59  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180010a5e  lea     rbx, [rdi+98h]
0x180010a65  mov     rsi, [rbx+40h]
0x180010a69  mov     qword ptr [rbx+40h], 0
0x180010a71  test    rsi, rsi
0x180010a74  jz      short loc_180010A8A
0x180010a76  call    cs:__imp_GetProcessHeap
0x180010a7c  mov     rcx, rax; hHeap
0x180010a7f  mov     r8, rsi; lpMem
0x180010a82  xor     edx, edx; dwFlags
0x180010a84  call    cs:__imp_HeapFree
0x180010a8a  mov     rcx, rbx; lpCriticalSection
0x180010a8d  call    cs:__imp_DeleteCriticalSection
0x180010a93  lea     rcx, [rdi+90h]
0x180010a9a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180010a9f  mov     rsi, [rdi+88h]
0x180010aa6  mov     qword ptr [rdi+88h], 0
0x180010ab1  test    rsi, rsi
0x180010ab4  jz      short loc_180010ACA
0x180010ab6  call    cs:__imp_GetProcessHeap
0x180010abc  mov     rcx, rax; hHeap
0x180010abf  mov     r8, rsi; lpMem
0x180010ac2  xor     edx, edx; dwFlags
0x180010ac4  call    cs:__imp_HeapFree
0x180010aca  lea     rcx, [rdi+48h]; lpCriticalSection
0x180010ace  call    cs:__imp_DeleteCriticalSection
0x180010ad4  mov     rbx, [rdi+38h]
0x180010ad8  test    rbx, rbx
0x180010adb  jz      short loc_180010B05
0x180010add  xor     r9d, r9d; msWindowLength
0x180010ae0  xor     r8d, r8d; msPeriod
0x180010ae3  xor     edx, edx; pftDueTime
0x180010ae5  mov     rcx, rbx; pti
0x180010ae8  call    cs:__imp_SetThreadpoolTimer
0x180010aee  mov     edx, 1; fCancelPendingCallbacks
0x180010af3  mov     rcx, rbx; pti
0x180010af6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010afc  mov     rcx, rbx; pti
0x180010aff  call    cs:__imp_CloseThreadpoolTimer
0x180010b05  mov     rbx, [rdi+30h]
0x180010b09  test    rbx, rbx
0x180010b0c  jz      short loc_180010B37
0x180010b0e  xor     r9d, r9d; msWindowLength
0x180010b11  xor     r8d, r8d; msPeriod
0x180010b14  xor     edx, edx; pftDueTime
0x180010b16  mov     rcx, rbx; pti
0x180010b19  call    cs:__imp_SetThreadpoolTimer
0x180010b1f  mov     edx, 1; fCancelPendingCallbacks
0x180010b24  mov     rcx, rbx; pti
0x180010b27  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010b2d  mov     rcx, rbx; pti
0x180010b30  call    cs:__imp_CloseThreadpoolTimer
0x180010b36  nop
0x180010b37  mov     rcx, [rdi+10h]; lpMem
0x180010b3b  test    rcx, rcx
0x180010b3e  jz      short loc_180010B46
0x180010b40  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180010b45  nop
0x180010b46  mov     rbx, [rsp+28h+arg_0]
0x180010b4b  mov     rsi, [rsp+28h+arg_8]
0x180010b50  add     rsp, 20h
0x180010b54  pop     rdi
0x180010b55  retn
```
