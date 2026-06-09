# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x140005cc0`
- end: `0x140005eae`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140008ba0`

## callees

- `0x140005b7c`
- `0x140005cc0`
- `0x140007910`
- `0x140007e50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005de5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005e26`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005de5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005e26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005d7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005dce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005e0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005d7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005dce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005e0e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005d8c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005ddc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005e1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005d8c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005ddc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005e1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005cde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005d27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005cde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005d27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005d10`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005d59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005d10`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005d59`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005d08`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005d51`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005e57`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005e88`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005d08`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005d51`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005e57`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005e88`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005cf1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005d3a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005e40`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005e71`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005cf1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005d3a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005e40`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005e71`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005cff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005d48`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005e4e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005e7f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005cff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005d48`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005e4e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005e7f`

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
  if ( v8 && qword_14000D028 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_14000D028[25], qword_14000D028, v8);
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
0x140005cc0  mov     [rsp+arg_0], rbx
0x140005cc5  mov     [rsp+arg_8], rsi
0x140005cca  push    rdi
0x140005ccb  sub     rsp, 20h
0x140005ccf  mov     rdi, rcx
0x140005cd2  mov     byte ptr [rcx], 0
0x140005cd5  mov     rsi, [rcx+30h]
0x140005cd9  test    rsi, rsi
0x140005cdc  jz      short loc_140005D16
0x140005cde  call    cs:__imp_GetLastError
0x140005ce4  mov     ebx, eax
0x140005ce6  xor     r9d, r9d; msWindowLength
0x140005ce9  xor     r8d, r8d; msPeriod
0x140005cec  xor     edx, edx; pftDueTime
0x140005cee  mov     rcx, rsi; pti
0x140005cf1  call    cs:__imp_SetThreadpoolTimer
0x140005cf7  mov     edx, 1; fCancelPendingCallbacks
0x140005cfc  mov     rcx, rsi; pti
0x140005cff  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005d05  mov     rcx, rsi; pti
0x140005d08  call    cs:__imp_CloseThreadpoolTimer
0x140005d0e  mov     ecx, ebx; dwErrCode
0x140005d10  call    cs:__imp_SetLastError
0x140005d16  mov     qword ptr [rdi+30h], 0
0x140005d1e  mov     rsi, [rdi+38h]
0x140005d22  test    rsi, rsi
0x140005d25  jz      short loc_140005D5F
0x140005d27  call    cs:__imp_GetLastError
0x140005d2d  mov     ebx, eax
0x140005d2f  xor     r9d, r9d; msWindowLength
0x140005d32  xor     r8d, r8d; msPeriod
0x140005d35  xor     edx, edx; pftDueTime
0x140005d37  mov     rcx, rsi; pti
0x140005d3a  call    cs:__imp_SetThreadpoolTimer
0x140005d40  mov     edx, 1; fCancelPendingCallbacks
0x140005d45  mov     rcx, rsi; pti
0x140005d48  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005d4e  mov     rcx, rsi; pti
0x140005d51  call    cs:__imp_CloseThreadpoolTimer
0x140005d57  mov     ecx, ebx; dwErrCode
0x140005d59  call    cs:__imp_SetLastError
0x140005d5f  mov     qword ptr [rdi+38h], 0
0x140005d67  mov     rbx, [rdi+100h]
0x140005d6e  mov     qword ptr [rdi+100h], 0
0x140005d79  test    rbx, rbx
0x140005d7c  jz      short loc_140005D92
0x140005d7e  call    cs:__imp_GetProcessHeap
0x140005d84  mov     rcx, rax; hHeap
0x140005d87  mov     r8, rbx; lpMem
0x140005d8a  xor     edx, edx; dwFlags
0x140005d8c  call    cs:__imp_HeapFree
0x140005d92  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x140005d99  test    r8, r8
0x140005d9c  jz      short loc_140005DB6
0x140005d9e  mov     rdx, cs:qword_14000D028; SRWLock
0x140005da5  test    rdx, rdx
0x140005da8  jz      short loc_140005DB6
0x140005daa  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140005db1  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x140005db6  lea     rbx, [rdi+98h]
0x140005dbd  mov     rsi, [rbx+40h]
0x140005dc1  mov     qword ptr [rbx+40h], 0
0x140005dc9  test    rsi, rsi
0x140005dcc  jz      short loc_140005DE2
0x140005dce  call    cs:__imp_GetProcessHeap
0x140005dd4  mov     rcx, rax; hHeap
0x140005dd7  mov     r8, rsi; lpMem
0x140005dda  xor     edx, edx; dwFlags
0x140005ddc  call    cs:__imp_HeapFree
0x140005de2  mov     rcx, rbx; lpCriticalSection
0x140005de5  call    cs:__imp_DeleteCriticalSection
0x140005deb  lea     rcx, [rdi+90h]
0x140005df2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140005df7  mov     rsi, [rdi+88h]
0x140005dfe  mov     qword ptr [rdi+88h], 0
0x140005e09  test    rsi, rsi
0x140005e0c  jz      short loc_140005E22
0x140005e0e  call    cs:__imp_GetProcessHeap
0x140005e14  mov     rcx, rax; hHeap
0x140005e17  mov     r8, rsi; lpMem
0x140005e1a  xor     edx, edx; dwFlags
0x140005e1c  call    cs:__imp_HeapFree
0x140005e22  lea     rcx, [rdi+48h]; lpCriticalSection
0x140005e26  call    cs:__imp_DeleteCriticalSection
0x140005e2c  mov     rbx, [rdi+38h]
0x140005e30  test    rbx, rbx
0x140005e33  jz      short loc_140005E5D
0x140005e35  xor     r9d, r9d; msWindowLength
0x140005e38  xor     r8d, r8d; msPeriod
0x140005e3b  xor     edx, edx; pftDueTime
0x140005e3d  mov     rcx, rbx; pti
0x140005e40  call    cs:__imp_SetThreadpoolTimer
0x140005e46  mov     edx, 1; fCancelPendingCallbacks
0x140005e4b  mov     rcx, rbx; pti
0x140005e4e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005e54  mov     rcx, rbx; pti
0x140005e57  call    cs:__imp_CloseThreadpoolTimer
0x140005e5d  mov     rbx, [rdi+30h]
0x140005e61  test    rbx, rbx
0x140005e64  jz      short loc_140005E8F
0x140005e66  xor     r9d, r9d; msWindowLength
0x140005e69  xor     r8d, r8d; msPeriod
0x140005e6c  xor     edx, edx; pftDueTime
0x140005e6e  mov     rcx, rbx; pti
0x140005e71  call    cs:__imp_SetThreadpoolTimer
0x140005e77  mov     edx, 1; fCancelPendingCallbacks
0x140005e7c  mov     rcx, rbx; pti
0x140005e7f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005e85  mov     rcx, rbx; pti
0x140005e88  call    cs:__imp_CloseThreadpoolTimer
0x140005e8e  nop
0x140005e8f  mov     rcx, [rdi+10h]; lpMem
0x140005e93  test    rcx, rcx
0x140005e96  jz      short loc_140005E9E
0x140005e98  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140005e9d  nop
0x140005e9e  mov     rbx, [rsp+28h+arg_0]
0x140005ea3  mov     rsi, [rsp+28h+arg_8]
0x140005ea8  add     rsp, 20h
0x140005eac  pop     rdi
0x140005ead  retn
```
