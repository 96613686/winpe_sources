# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180023a7c`
- end: `0x180023c6a`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002c1d0`

## callees

- `0x180023938`
- `0x180023a7c`
- `0x180025640`
- `0x180025b8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023ba1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023be2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023ba1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023be2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023b3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023b8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023bca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023b3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023b8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023bca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023b48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023b98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023bd8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023b48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023b98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023bd8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023acc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023b15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023acc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023b15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023a9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023a9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ae3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180023abb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180023b04`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180023c0a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180023c3b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180023abb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180023b04`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180023c0a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180023c3b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180023ac4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180023b0d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180023c13`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180023c44`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180023ac4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180023b0d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180023c13`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180023c44`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180023aad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180023af6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180023bfc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180023c2d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180023aad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180023af6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180023bfc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180023c2d`

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
  if ( v8 && qword_18003B0A8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18003B0A8[25], qword_18003B0A8, v8);
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
0x180023a7c  mov     [rsp+arg_0], rbx
0x180023a81  mov     [rsp+arg_8], rsi
0x180023a86  push    rdi
0x180023a87  sub     rsp, 20h
0x180023a8b  mov     rdi, rcx
0x180023a8e  mov     byte ptr [rcx], 0
0x180023a91  mov     rsi, [rcx+30h]
0x180023a95  test    rsi, rsi
0x180023a98  jz      short loc_180023AD2
0x180023a9a  call    cs:__imp_GetLastError
0x180023aa0  mov     ebx, eax
0x180023aa2  xor     r9d, r9d; msWindowLength
0x180023aa5  xor     r8d, r8d; msPeriod
0x180023aa8  xor     edx, edx; pftDueTime
0x180023aaa  mov     rcx, rsi; pti
0x180023aad  call    cs:__imp_SetThreadpoolTimer
0x180023ab3  mov     edx, 1; fCancelPendingCallbacks
0x180023ab8  mov     rcx, rsi; pti
0x180023abb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180023ac1  mov     rcx, rsi; pti
0x180023ac4  call    cs:__imp_CloseThreadpoolTimer
0x180023aca  mov     ecx, ebx; dwErrCode
0x180023acc  call    cs:__imp_SetLastError
0x180023ad2  mov     qword ptr [rdi+30h], 0
0x180023ada  mov     rsi, [rdi+38h]
0x180023ade  test    rsi, rsi
0x180023ae1  jz      short loc_180023B1B
0x180023ae3  call    cs:__imp_GetLastError
0x180023ae9  mov     ebx, eax
0x180023aeb  xor     r9d, r9d; msWindowLength
0x180023aee  xor     r8d, r8d; msPeriod
0x180023af1  xor     edx, edx; pftDueTime
0x180023af3  mov     rcx, rsi; pti
0x180023af6  call    cs:__imp_SetThreadpoolTimer
0x180023afc  mov     edx, 1; fCancelPendingCallbacks
0x180023b01  mov     rcx, rsi; pti
0x180023b04  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180023b0a  mov     rcx, rsi; pti
0x180023b0d  call    cs:__imp_CloseThreadpoolTimer
0x180023b13  mov     ecx, ebx; dwErrCode
0x180023b15  call    cs:__imp_SetLastError
0x180023b1b  mov     qword ptr [rdi+38h], 0
0x180023b23  mov     rbx, [rdi+100h]
0x180023b2a  mov     qword ptr [rdi+100h], 0
0x180023b35  test    rbx, rbx
0x180023b38  jz      short loc_180023B4E
0x180023b3a  call    cs:__imp_GetProcessHeap
0x180023b40  mov     rcx, rax; hHeap
0x180023b43  mov     r8, rbx; lpMem
0x180023b46  xor     edx, edx; dwFlags
0x180023b48  call    cs:__imp_HeapFree
0x180023b4e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180023b55  test    r8, r8
0x180023b58  jz      short loc_180023B72
0x180023b5a  mov     rdx, cs:qword_18003B0A8; SRWLock
0x180023b61  test    rdx, rdx
0x180023b64  jz      short loc_180023B72
0x180023b66  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180023b6d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180023b72  lea     rbx, [rdi+98h]
0x180023b79  mov     rsi, [rbx+40h]
0x180023b7d  mov     qword ptr [rbx+40h], 0
0x180023b85  test    rsi, rsi
0x180023b88  jz      short loc_180023B9E
0x180023b8a  call    cs:__imp_GetProcessHeap
0x180023b90  mov     rcx, rax; hHeap
0x180023b93  mov     r8, rsi; lpMem
0x180023b96  xor     edx, edx; dwFlags
0x180023b98  call    cs:__imp_HeapFree
0x180023b9e  mov     rcx, rbx; lpCriticalSection
0x180023ba1  call    cs:__imp_DeleteCriticalSection
0x180023ba7  lea     rcx, [rdi+90h]
0x180023bae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180023bb3  mov     rsi, [rdi+88h]
0x180023bba  mov     qword ptr [rdi+88h], 0
0x180023bc5  test    rsi, rsi
0x180023bc8  jz      short loc_180023BDE
0x180023bca  call    cs:__imp_GetProcessHeap
0x180023bd0  mov     rcx, rax; hHeap
0x180023bd3  mov     r8, rsi; lpMem
0x180023bd6  xor     edx, edx; dwFlags
0x180023bd8  call    cs:__imp_HeapFree
0x180023bde  lea     rcx, [rdi+48h]; lpCriticalSection
0x180023be2  call    cs:__imp_DeleteCriticalSection
0x180023be8  mov     rbx, [rdi+38h]
0x180023bec  test    rbx, rbx
0x180023bef  jz      short loc_180023C19
0x180023bf1  xor     r9d, r9d; msWindowLength
0x180023bf4  xor     r8d, r8d; msPeriod
0x180023bf7  xor     edx, edx; pftDueTime
0x180023bf9  mov     rcx, rbx; pti
0x180023bfc  call    cs:__imp_SetThreadpoolTimer
0x180023c02  mov     edx, 1; fCancelPendingCallbacks
0x180023c07  mov     rcx, rbx; pti
0x180023c0a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180023c10  mov     rcx, rbx; pti
0x180023c13  call    cs:__imp_CloseThreadpoolTimer
0x180023c19  mov     rbx, [rdi+30h]
0x180023c1d  test    rbx, rbx
0x180023c20  jz      short loc_180023C4B
0x180023c22  xor     r9d, r9d; msWindowLength
0x180023c25  xor     r8d, r8d; msPeriod
0x180023c28  xor     edx, edx; pftDueTime
0x180023c2a  mov     rcx, rbx; pti
0x180023c2d  call    cs:__imp_SetThreadpoolTimer
0x180023c33  mov     edx, 1; fCancelPendingCallbacks
0x180023c38  mov     rcx, rbx; pti
0x180023c3b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180023c41  mov     rcx, rbx; pti
0x180023c44  call    cs:__imp_CloseThreadpoolTimer
0x180023c4a  nop
0x180023c4b  mov     rcx, [rdi+10h]; lpMem
0x180023c4f  test    rcx, rcx
0x180023c52  jz      short loc_180023C5A
0x180023c54  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180023c59  nop
0x180023c5a  mov     rbx, [rsp+28h+arg_0]
0x180023c5f  mov     rsi, [rsp+28h+arg_8]
0x180023c64  add     rsp, 20h
0x180023c68  pop     rdi
0x180023c69  retn
```
