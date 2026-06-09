# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1400089f8`
- end: `0x140008be6`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140011670`

## callees

- `0x1400088b4`
- `0x1400089f8`
- `0x14000bcf8`
- `0x14000cab4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008ab6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008b06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008b46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008ab6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008b06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008b46`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008ac4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008b14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008b54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008ac4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008b14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008b54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008a16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008a5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008a16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008a5f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008a48`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008a91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008a48`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008a91`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140008b1d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140008b5e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140008b1d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140008b5e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008a37`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008a80`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008b86`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008bb7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008a37`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008a80`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008b86`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008bb7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008a40`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008a89`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008b8f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008bc0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008a40`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008a89`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008b8f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008bc0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008a29`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008a72`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008b78`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008ba9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008a29`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008a72`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008b78`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008ba9`

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
  if ( v8 && qword_14001A0D8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_14001A0D8[25], qword_14001A0D8, v8);
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
0x1400089f8  mov     [rsp+arg_0], rbx
0x1400089fd  mov     [rsp+arg_8], rsi
0x140008a02  push    rdi
0x140008a03  sub     rsp, 20h
0x140008a07  mov     rdi, rcx
0x140008a0a  mov     byte ptr [rcx], 0
0x140008a0d  mov     rsi, [rcx+30h]
0x140008a11  test    rsi, rsi
0x140008a14  jz      short loc_140008A4E
0x140008a16  call    cs:__imp_GetLastError
0x140008a1c  mov     ebx, eax
0x140008a1e  xor     r9d, r9d; msWindowLength
0x140008a21  xor     r8d, r8d; msPeriod
0x140008a24  xor     edx, edx; pftDueTime
0x140008a26  mov     rcx, rsi; pti
0x140008a29  call    cs:__imp_SetThreadpoolTimer
0x140008a2f  mov     edx, 1; fCancelPendingCallbacks
0x140008a34  mov     rcx, rsi; pti
0x140008a37  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008a3d  mov     rcx, rsi; pti
0x140008a40  call    cs:__imp_CloseThreadpoolTimer
0x140008a46  mov     ecx, ebx; dwErrCode
0x140008a48  call    cs:__imp_SetLastError
0x140008a4e  mov     qword ptr [rdi+30h], 0
0x140008a56  mov     rsi, [rdi+38h]
0x140008a5a  test    rsi, rsi
0x140008a5d  jz      short loc_140008A97
0x140008a5f  call    cs:__imp_GetLastError
0x140008a65  mov     ebx, eax
0x140008a67  xor     r9d, r9d; msWindowLength
0x140008a6a  xor     r8d, r8d; msPeriod
0x140008a6d  xor     edx, edx; pftDueTime
0x140008a6f  mov     rcx, rsi; pti
0x140008a72  call    cs:__imp_SetThreadpoolTimer
0x140008a78  mov     edx, 1; fCancelPendingCallbacks
0x140008a7d  mov     rcx, rsi; pti
0x140008a80  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008a86  mov     rcx, rsi; pti
0x140008a89  call    cs:__imp_CloseThreadpoolTimer
0x140008a8f  mov     ecx, ebx; dwErrCode
0x140008a91  call    cs:__imp_SetLastError
0x140008a97  mov     qword ptr [rdi+38h], 0
0x140008a9f  mov     rbx, [rdi+100h]
0x140008aa6  mov     qword ptr [rdi+100h], 0
0x140008ab1  test    rbx, rbx
0x140008ab4  jz      short loc_140008ACA
0x140008ab6  call    cs:__imp_GetProcessHeap
0x140008abc  mov     rcx, rax; hHeap
0x140008abf  mov     r8, rbx; lpMem
0x140008ac2  xor     edx, edx; dwFlags
0x140008ac4  call    cs:__imp_HeapFree
0x140008aca  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x140008ad1  test    r8, r8
0x140008ad4  jz      short loc_140008AEE
0x140008ad6  mov     rdx, cs:qword_14001A0D8; SRWLock
0x140008add  test    rdx, rdx
0x140008ae0  jz      short loc_140008AEE
0x140008ae2  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140008ae9  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x140008aee  lea     rbx, [rdi+98h]
0x140008af5  mov     rsi, [rbx+40h]
0x140008af9  mov     qword ptr [rbx+40h], 0
0x140008b01  test    rsi, rsi
0x140008b04  jz      short loc_140008B1A
0x140008b06  call    cs:__imp_GetProcessHeap
0x140008b0c  mov     rcx, rax; hHeap
0x140008b0f  mov     r8, rsi; lpMem
0x140008b12  xor     edx, edx; dwFlags
0x140008b14  call    cs:__imp_HeapFree
0x140008b1a  mov     rcx, rbx; lpCriticalSection
0x140008b1d  call    cs:__imp_DeleteCriticalSection
0x140008b23  lea     rcx, [rdi+90h]
0x140008b2a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140008b2f  mov     rsi, [rdi+88h]
0x140008b36  mov     qword ptr [rdi+88h], 0
0x140008b41  test    rsi, rsi
0x140008b44  jz      short loc_140008B5A
0x140008b46  call    cs:__imp_GetProcessHeap
0x140008b4c  mov     rcx, rax; hHeap
0x140008b4f  mov     r8, rsi; lpMem
0x140008b52  xor     edx, edx; dwFlags
0x140008b54  call    cs:__imp_HeapFree
0x140008b5a  lea     rcx, [rdi+48h]; lpCriticalSection
0x140008b5e  call    cs:__imp_DeleteCriticalSection
0x140008b64  mov     rbx, [rdi+38h]
0x140008b68  test    rbx, rbx
0x140008b6b  jz      short loc_140008B95
0x140008b6d  xor     r9d, r9d; msWindowLength
0x140008b70  xor     r8d, r8d; msPeriod
0x140008b73  xor     edx, edx; pftDueTime
0x140008b75  mov     rcx, rbx; pti
0x140008b78  call    cs:__imp_SetThreadpoolTimer
0x140008b7e  mov     edx, 1; fCancelPendingCallbacks
0x140008b83  mov     rcx, rbx; pti
0x140008b86  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008b8c  mov     rcx, rbx; pti
0x140008b8f  call    cs:__imp_CloseThreadpoolTimer
0x140008b95  mov     rbx, [rdi+30h]
0x140008b99  test    rbx, rbx
0x140008b9c  jz      short loc_140008BC7
0x140008b9e  xor     r9d, r9d; msWindowLength
0x140008ba1  xor     r8d, r8d; msPeriod
0x140008ba4  xor     edx, edx; pftDueTime
0x140008ba6  mov     rcx, rbx; pti
0x140008ba9  call    cs:__imp_SetThreadpoolTimer
0x140008baf  mov     edx, 1; fCancelPendingCallbacks
0x140008bb4  mov     rcx, rbx; pti
0x140008bb7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008bbd  mov     rcx, rbx; pti
0x140008bc0  call    cs:__imp_CloseThreadpoolTimer
0x140008bc6  nop
0x140008bc7  mov     rcx, [rdi+10h]; lpMem
0x140008bcb  test    rcx, rcx
0x140008bce  jz      short loc_140008BD6
0x140008bd0  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140008bd5  nop
0x140008bd6  mov     rbx, [rsp+28h+arg_0]
0x140008bdb  mov     rsi, [rsp+28h+arg_8]
0x140008be0  add     rsp, 20h
0x140008be4  pop     rdi
0x140008be5  retn
```
