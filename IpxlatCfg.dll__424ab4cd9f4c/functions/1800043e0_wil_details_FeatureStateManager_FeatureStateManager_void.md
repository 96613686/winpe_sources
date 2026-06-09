# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800043e0`
- end: `0x1800045ce`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180018930`

## callees

- `0x18000413c`
- `0x1800043e0`
- `0x18000807c`
- `0x180009580`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004430`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004479`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004430`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004479`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004447`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800044ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800044fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000453c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800044ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800044fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000453c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000449e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800044ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000452e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000449e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800044ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000452e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004505`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004546`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004505`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004546`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000441f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004468`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000456e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000459f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000441f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004468`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000456e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000459f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004428`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004471`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004577`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800045a8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004428`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004471`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004577`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800045a8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004411`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000445a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004560`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004591`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004411`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000445a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004560`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004591`

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
  if ( v8 && qword_1800230B8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800230B8[25], qword_1800230B8, v8);
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
0x1800043e0  mov     [rsp+arg_0], rbx
0x1800043e5  mov     [rsp+arg_8], rsi
0x1800043ea  push    rdi
0x1800043eb  sub     rsp, 20h
0x1800043ef  mov     rdi, rcx
0x1800043f2  mov     byte ptr [rcx], 0
0x1800043f5  mov     rsi, [rcx+30h]
0x1800043f9  test    rsi, rsi
0x1800043fc  jz      short loc_180004436
0x1800043fe  call    cs:__imp_GetLastError
0x180004404  mov     ebx, eax
0x180004406  xor     r9d, r9d; msWindowLength
0x180004409  xor     r8d, r8d; msPeriod
0x18000440c  xor     edx, edx; pftDueTime
0x18000440e  mov     rcx, rsi; pti
0x180004411  call    cs:__imp_SetThreadpoolTimer
0x180004417  mov     edx, 1; fCancelPendingCallbacks
0x18000441c  mov     rcx, rsi; pti
0x18000441f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004425  mov     rcx, rsi; pti
0x180004428  call    cs:__imp_CloseThreadpoolTimer
0x18000442e  mov     ecx, ebx; dwErrCode
0x180004430  call    cs:__imp_SetLastError
0x180004436  mov     qword ptr [rdi+30h], 0
0x18000443e  mov     rsi, [rdi+38h]
0x180004442  test    rsi, rsi
0x180004445  jz      short loc_18000447F
0x180004447  call    cs:__imp_GetLastError
0x18000444d  mov     ebx, eax
0x18000444f  xor     r9d, r9d; msWindowLength
0x180004452  xor     r8d, r8d; msPeriod
0x180004455  xor     edx, edx; pftDueTime
0x180004457  mov     rcx, rsi; pti
0x18000445a  call    cs:__imp_SetThreadpoolTimer
0x180004460  mov     edx, 1; fCancelPendingCallbacks
0x180004465  mov     rcx, rsi; pti
0x180004468  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000446e  mov     rcx, rsi; pti
0x180004471  call    cs:__imp_CloseThreadpoolTimer
0x180004477  mov     ecx, ebx; dwErrCode
0x180004479  call    cs:__imp_SetLastError
0x18000447f  mov     qword ptr [rdi+38h], 0
0x180004487  mov     rbx, [rdi+100h]
0x18000448e  mov     qword ptr [rdi+100h], 0
0x180004499  test    rbx, rbx
0x18000449c  jz      short loc_1800044B2
0x18000449e  call    cs:__imp_GetProcessHeap
0x1800044a4  mov     rcx, rax; hHeap
0x1800044a7  mov     r8, rbx; lpMem
0x1800044aa  xor     edx, edx; dwFlags
0x1800044ac  call    cs:__imp_HeapFree
0x1800044b2  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800044b9  test    r8, r8
0x1800044bc  jz      short loc_1800044D6
0x1800044be  mov     rdx, cs:qword_1800230B8; SRWLock
0x1800044c5  test    rdx, rdx
0x1800044c8  jz      short loc_1800044D6
0x1800044ca  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800044d1  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800044d6  lea     rbx, [rdi+98h]
0x1800044dd  mov     rsi, [rbx+40h]
0x1800044e1  mov     qword ptr [rbx+40h], 0
0x1800044e9  test    rsi, rsi
0x1800044ec  jz      short loc_180004502
0x1800044ee  call    cs:__imp_GetProcessHeap
0x1800044f4  mov     rcx, rax; hHeap
0x1800044f7  mov     r8, rsi; lpMem
0x1800044fa  xor     edx, edx; dwFlags
0x1800044fc  call    cs:__imp_HeapFree
0x180004502  mov     rcx, rbx; lpCriticalSection
0x180004505  call    cs:__imp_DeleteCriticalSection
0x18000450b  lea     rcx, [rdi+90h]
0x180004512  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180004517  mov     rsi, [rdi+88h]
0x18000451e  mov     qword ptr [rdi+88h], 0
0x180004529  test    rsi, rsi
0x18000452c  jz      short loc_180004542
0x18000452e  call    cs:__imp_GetProcessHeap
0x180004534  mov     rcx, rax; hHeap
0x180004537  mov     r8, rsi; lpMem
0x18000453a  xor     edx, edx; dwFlags
0x18000453c  call    cs:__imp_HeapFree
0x180004542  lea     rcx, [rdi+48h]; lpCriticalSection
0x180004546  call    cs:__imp_DeleteCriticalSection
0x18000454c  mov     rbx, [rdi+38h]
0x180004550  test    rbx, rbx
0x180004553  jz      short loc_18000457D
0x180004555  xor     r9d, r9d; msWindowLength
0x180004558  xor     r8d, r8d; msPeriod
0x18000455b  xor     edx, edx; pftDueTime
0x18000455d  mov     rcx, rbx; pti
0x180004560  call    cs:__imp_SetThreadpoolTimer
0x180004566  mov     edx, 1; fCancelPendingCallbacks
0x18000456b  mov     rcx, rbx; pti
0x18000456e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004574  mov     rcx, rbx; pti
0x180004577  call    cs:__imp_CloseThreadpoolTimer
0x18000457d  mov     rbx, [rdi+30h]
0x180004581  test    rbx, rbx
0x180004584  jz      short loc_1800045AF
0x180004586  xor     r9d, r9d; msWindowLength
0x180004589  xor     r8d, r8d; msPeriod
0x18000458c  xor     edx, edx; pftDueTime
0x18000458e  mov     rcx, rbx; pti
0x180004591  call    cs:__imp_SetThreadpoolTimer
0x180004597  mov     edx, 1; fCancelPendingCallbacks
0x18000459c  mov     rcx, rbx; pti
0x18000459f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800045a5  mov     rcx, rbx; pti
0x1800045a8  call    cs:__imp_CloseThreadpoolTimer
0x1800045ae  nop
0x1800045af  mov     rcx, [rdi+10h]; lpMem
0x1800045b3  test    rcx, rcx
0x1800045b6  jz      short loc_1800045BE
0x1800045b8  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800045bd  nop
0x1800045be  mov     rbx, [rsp+28h+arg_0]
0x1800045c3  mov     rsi, [rsp+28h+arg_8]
0x1800045c8  add     rsp, 20h
0x1800045cc  pop     rdi
0x1800045cd  retn
```
