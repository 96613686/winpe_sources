# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000c388`
- end: `0x18000c576`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180069810`

## callees

- `0x18000c150`
- `0x18000c388`
- `0x18000ffbc`
- `0x1800113dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c4ad`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c4ee`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c4ad`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c4ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c454`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c4a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c4e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c454`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c4a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c4e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c446`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c496`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c4d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c446`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c496`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c4d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c3a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c3ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c3a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c3ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c3d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c421`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c3d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c421`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c3b9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c402`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c508`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c539`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c3b9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c402`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c508`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c539`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c3d0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c419`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c51f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c550`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c3d0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c419`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c51f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c550`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c3c7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c410`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c516`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c547`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c3c7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c410`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c516`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c547`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
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
  if ( v8 && qword_1800890D0 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800890D0[25], qword_1800890D0, v8);
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
0x18000c388  mov     [rsp+arg_0], rbx
0x18000c38d  mov     [rsp+arg_8], rsi
0x18000c392  push    rdi
0x18000c393  sub     rsp, 20h
0x18000c397  mov     rdi, rcx
0x18000c39a  mov     byte ptr [rcx], 0
0x18000c39d  mov     rsi, [rcx+30h]
0x18000c3a1  test    rsi, rsi
0x18000c3a4  jz      short loc_18000C3DE
0x18000c3a6  call    cs:__imp_GetLastError
0x18000c3ac  mov     ebx, eax
0x18000c3ae  xor     r9d, r9d; msWindowLength
0x18000c3b1  xor     r8d, r8d; msPeriod
0x18000c3b4  xor     edx, edx; pftDueTime
0x18000c3b6  mov     rcx, rsi; pti
0x18000c3b9  call    cs:__imp_SetThreadpoolTimer
0x18000c3bf  mov     edx, 1; fCancelPendingCallbacks
0x18000c3c4  mov     rcx, rsi; pti
0x18000c3c7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c3cd  mov     rcx, rsi; pti
0x18000c3d0  call    cs:__imp_CloseThreadpoolTimer
0x18000c3d6  mov     ecx, ebx; dwErrCode
0x18000c3d8  call    cs:__imp_SetLastError
0x18000c3de  mov     qword ptr [rdi+30h], 0
0x18000c3e6  mov     rsi, [rdi+38h]
0x18000c3ea  test    rsi, rsi
0x18000c3ed  jz      short loc_18000C427
0x18000c3ef  call    cs:__imp_GetLastError
0x18000c3f5  mov     ebx, eax
0x18000c3f7  xor     r9d, r9d; msWindowLength
0x18000c3fa  xor     r8d, r8d; msPeriod
0x18000c3fd  xor     edx, edx; pftDueTime
0x18000c3ff  mov     rcx, rsi; pti
0x18000c402  call    cs:__imp_SetThreadpoolTimer
0x18000c408  mov     edx, 1; fCancelPendingCallbacks
0x18000c40d  mov     rcx, rsi; pti
0x18000c410  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c416  mov     rcx, rsi; pti
0x18000c419  call    cs:__imp_CloseThreadpoolTimer
0x18000c41f  mov     ecx, ebx; dwErrCode
0x18000c421  call    cs:__imp_SetLastError
0x18000c427  mov     qword ptr [rdi+38h], 0
0x18000c42f  mov     rbx, [rdi+100h]
0x18000c436  mov     qword ptr [rdi+100h], 0
0x18000c441  test    rbx, rbx
0x18000c444  jz      short loc_18000C45A
0x18000c446  call    cs:__imp_GetProcessHeap
0x18000c44c  mov     rcx, rax; hHeap
0x18000c44f  mov     r8, rbx; lpMem
0x18000c452  xor     edx, edx; dwFlags
0x18000c454  call    cs:__imp_HeapFree
0x18000c45a  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18000c461  test    r8, r8
0x18000c464  jz      short loc_18000C47E
0x18000c466  mov     rdx, cs:qword_1800890D0; SRWLock
0x18000c46d  test    rdx, rdx
0x18000c470  jz      short loc_18000C47E
0x18000c472  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000c479  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000c47e  lea     rbx, [rdi+98h]
0x18000c485  mov     rsi, [rbx+40h]
0x18000c489  mov     qword ptr [rbx+40h], 0
0x18000c491  test    rsi, rsi
0x18000c494  jz      short loc_18000C4AA
0x18000c496  call    cs:__imp_GetProcessHeap
0x18000c49c  mov     rcx, rax; hHeap
0x18000c49f  mov     r8, rsi; lpMem
0x18000c4a2  xor     edx, edx; dwFlags
0x18000c4a4  call    cs:__imp_HeapFree
0x18000c4aa  mov     rcx, rbx; lpCriticalSection
0x18000c4ad  call    cs:__imp_DeleteCriticalSection
0x18000c4b3  lea     rcx, [rdi+90h]
0x18000c4ba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000c4bf  mov     rsi, [rdi+88h]
0x18000c4c6  mov     qword ptr [rdi+88h], 0
0x18000c4d1  test    rsi, rsi
0x18000c4d4  jz      short loc_18000C4EA
0x18000c4d6  call    cs:__imp_GetProcessHeap
0x18000c4dc  mov     rcx, rax; hHeap
0x18000c4df  mov     r8, rsi; lpMem
0x18000c4e2  xor     edx, edx; dwFlags
0x18000c4e4  call    cs:__imp_HeapFree
0x18000c4ea  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000c4ee  call    cs:__imp_DeleteCriticalSection
0x18000c4f4  mov     rbx, [rdi+38h]
0x18000c4f8  test    rbx, rbx
0x18000c4fb  jz      short loc_18000C525
0x18000c4fd  xor     r9d, r9d; msWindowLength
0x18000c500  xor     r8d, r8d; msPeriod
0x18000c503  xor     edx, edx; pftDueTime
0x18000c505  mov     rcx, rbx; pti
0x18000c508  call    cs:__imp_SetThreadpoolTimer
0x18000c50e  mov     edx, 1; fCancelPendingCallbacks
0x18000c513  mov     rcx, rbx; pti
0x18000c516  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c51c  mov     rcx, rbx; pti
0x18000c51f  call    cs:__imp_CloseThreadpoolTimer
0x18000c525  mov     rbx, [rdi+30h]
0x18000c529  test    rbx, rbx
0x18000c52c  jz      short loc_18000C557
0x18000c52e  xor     r9d, r9d; msWindowLength
0x18000c531  xor     r8d, r8d; msPeriod
0x18000c534  xor     edx, edx; pftDueTime
0x18000c536  mov     rcx, rbx; pti
0x18000c539  call    cs:__imp_SetThreadpoolTimer
0x18000c53f  mov     edx, 1; fCancelPendingCallbacks
0x18000c544  mov     rcx, rbx; pti
0x18000c547  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c54d  mov     rcx, rbx; pti
0x18000c550  call    cs:__imp_CloseThreadpoolTimer
0x18000c556  nop
0x18000c557  mov     rcx, [rdi+10h]; lpMem
0x18000c55b  test    rcx, rcx
0x18000c55e  jz      short loc_18000C566
0x18000c560  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18000c565  nop
0x18000c566  mov     rbx, [rsp+28h+arg_0]
0x18000c56b  mov     rsi, [rsp+28h+arg_8]
0x18000c570  add     rsp, 20h
0x18000c574  pop     rdi
0x18000c575  retn
```
