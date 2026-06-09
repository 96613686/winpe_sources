# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800043f8`
- end: `0x1800045f0`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `504`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180069010`

## callees

- `0x1800041a8`
- `0x1800043f8`
- `0x18000827c`
- `0x180009698`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800044c0`
- `KERNEL32!GetProcessHeap` at `0x180004510`
- `KERNEL32!GetProcessHeap` at `0x180004550`
- `KERNEL32!GetProcessHeap` at `0x1800044c0`
- `KERNEL32!GetProcessHeap` at `0x180004510`
- `KERNEL32!GetProcessHeap` at `0x180004550`
- `KERNEL32!DeleteCriticalSection` at `0x180004527`
- `KERNEL32!DeleteCriticalSection` at `0x180004568`
- `KERNEL32!DeleteCriticalSection` at `0x180004527`
- `KERNEL32!DeleteCriticalSection` at `0x180004568`
- `KERNEL32!SetThreadpoolTimer` at `0x180004433`
- `KERNEL32!SetThreadpoolTimer` at `0x18000447c`
- `KERNEL32!SetThreadpoolTimer` at `0x180004582`
- `KERNEL32!SetThreadpoolTimer` at `0x1800045b3`
- `KERNEL32!SetThreadpoolTimer` at `0x180004433`
- `KERNEL32!SetThreadpoolTimer` at `0x18000447c`
- `KERNEL32!SetThreadpoolTimer` at `0x180004582`
- `KERNEL32!SetThreadpoolTimer` at `0x1800045b3`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000444a`
- `KERNEL32!CloseThreadpoolTimer` at `0x180004493`
- `KERNEL32!CloseThreadpoolTimer` at `0x180004599`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800045ca`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000444a`
- `KERNEL32!CloseThreadpoolTimer` at `0x180004493`
- `KERNEL32!CloseThreadpoolTimer` at `0x180004599`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800045ca`
- `KERNEL32!GetLastError` at `0x180004420`
- `KERNEL32!GetLastError` at `0x180004469`
- `KERNEL32!GetLastError` at `0x180004420`
- `KERNEL32!GetLastError` at `0x180004469`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180004441`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000448a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180004590`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800045c1`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180004441`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000448a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180004590`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800045c1`
- `KERNEL32!SetLastError` at `0x180004452`
- `KERNEL32!SetLastError` at `0x18000449b`
- `KERNEL32!SetLastError` at `0x180004452`
- `KERNEL32!SetLastError` at `0x18000449b`
- `KERNEL32!HeapFree` at `0x1800044ce`
- `KERNEL32!HeapFree` at `0x18000451e`
- `KERNEL32!HeapFree` at `0x18000455e`
- `KERNEL32!HeapFree` at `0x1800044ce`
- `KERNEL32!HeapFree` at `0x18000451e`
- `KERNEL32!HeapFree` at `0x18000455e`

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
  if ( v8 && qword_180096AA8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180096AA8[25], qword_180096AA8, v8);
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
0x1800043f8  push    rdi
0x1800043fa  sub     rsp, 30h
0x1800043fe  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180004407  mov     [rsp+38h+arg_0], rbx
0x18000440c  mov     [rsp+38h+arg_8], rsi
0x180004411  mov     rdi, rcx
0x180004414  mov     byte ptr [rcx], 0
0x180004417  mov     rsi, [rcx+30h]
0x18000441b  test    rsi, rsi
0x18000441e  jz      short loc_180004458
0x180004420  call    cs:__imp_GetLastError
0x180004426  mov     ebx, eax
0x180004428  xor     r9d, r9d; msWindowLength
0x18000442b  xor     r8d, r8d; msPeriod
0x18000442e  xor     edx, edx; pftDueTime
0x180004430  mov     rcx, rsi; pti
0x180004433  call    cs:__imp_SetThreadpoolTimer
0x180004439  mov     edx, 1; fCancelPendingCallbacks
0x18000443e  mov     rcx, rsi; pti
0x180004441  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004447  mov     rcx, rsi; pti
0x18000444a  call    cs:__imp_CloseThreadpoolTimer
0x180004450  mov     ecx, ebx; dwErrCode
0x180004452  call    cs:__imp_SetLastError
0x180004458  mov     qword ptr [rdi+30h], 0
0x180004460  mov     rsi, [rdi+38h]
0x180004464  test    rsi, rsi
0x180004467  jz      short loc_1800044A1
0x180004469  call    cs:__imp_GetLastError
0x18000446f  mov     ebx, eax
0x180004471  xor     r9d, r9d; msWindowLength
0x180004474  xor     r8d, r8d; msPeriod
0x180004477  xor     edx, edx; pftDueTime
0x180004479  mov     rcx, rsi; pti
0x18000447c  call    cs:__imp_SetThreadpoolTimer
0x180004482  mov     edx, 1; fCancelPendingCallbacks
0x180004487  mov     rcx, rsi; pti
0x18000448a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004490  mov     rcx, rsi; pti
0x180004493  call    cs:__imp_CloseThreadpoolTimer
0x180004499  mov     ecx, ebx; dwErrCode
0x18000449b  call    cs:__imp_SetLastError
0x1800044a1  mov     qword ptr [rdi+38h], 0
0x1800044a9  mov     rbx, [rdi+100h]
0x1800044b0  mov     qword ptr [rdi+100h], 0
0x1800044bb  test    rbx, rbx
0x1800044be  jz      short loc_1800044D4
0x1800044c0  call    cs:__imp_GetProcessHeap
0x1800044c6  mov     rcx, rax; hHeap
0x1800044c9  mov     r8, rbx; lpMem
0x1800044cc  xor     edx, edx; dwFlags
0x1800044ce  call    cs:__imp_HeapFree
0x1800044d4  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800044db  test    r8, r8
0x1800044de  jz      short loc_1800044F8
0x1800044e0  mov     rdx, cs:qword_180096AA8; SRWLock
0x1800044e7  test    rdx, rdx
0x1800044ea  jz      short loc_1800044F8
0x1800044ec  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800044f3  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800044f8  lea     rbx, [rdi+98h]
0x1800044ff  mov     rsi, [rbx+40h]
0x180004503  mov     qword ptr [rbx+40h], 0
0x18000450b  test    rsi, rsi
0x18000450e  jz      short loc_180004524
0x180004510  call    cs:__imp_GetProcessHeap
0x180004516  mov     rcx, rax; hHeap
0x180004519  mov     r8, rsi; lpMem
0x18000451c  xor     edx, edx; dwFlags
0x18000451e  call    cs:__imp_HeapFree
0x180004524  mov     rcx, rbx; lpCriticalSection
0x180004527  call    cs:__imp_DeleteCriticalSection
0x18000452d  lea     rcx, [rdi+90h]
0x180004534  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180004539  mov     rsi, [rdi+88h]
0x180004540  mov     qword ptr [rdi+88h], 0
0x18000454b  test    rsi, rsi
0x18000454e  jz      short loc_180004564
0x180004550  call    cs:__imp_GetProcessHeap
0x180004556  mov     rcx, rax; hHeap
0x180004559  mov     r8, rsi; lpMem
0x18000455c  xor     edx, edx; dwFlags
0x18000455e  call    cs:__imp_HeapFree
0x180004564  lea     rcx, [rdi+48h]; lpCriticalSection
0x180004568  call    cs:__imp_DeleteCriticalSection
0x18000456e  mov     rbx, [rdi+38h]
0x180004572  test    rbx, rbx
0x180004575  jz      short loc_18000459F
0x180004577  xor     r9d, r9d; msWindowLength
0x18000457a  xor     r8d, r8d; msPeriod
0x18000457d  xor     edx, edx; pftDueTime
0x18000457f  mov     rcx, rbx; pti
0x180004582  call    cs:__imp_SetThreadpoolTimer
0x180004588  mov     edx, 1; fCancelPendingCallbacks
0x18000458d  mov     rcx, rbx; pti
0x180004590  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004596  mov     rcx, rbx; pti
0x180004599  call    cs:__imp_CloseThreadpoolTimer
0x18000459f  mov     rbx, [rdi+30h]
0x1800045a3  test    rbx, rbx
0x1800045a6  jz      short loc_1800045D1
0x1800045a8  xor     r9d, r9d; msWindowLength
0x1800045ab  xor     r8d, r8d; msPeriod
0x1800045ae  xor     edx, edx; pftDueTime
0x1800045b0  mov     rcx, rbx; pti
0x1800045b3  call    cs:__imp_SetThreadpoolTimer
0x1800045b9  mov     edx, 1; fCancelPendingCallbacks
0x1800045be  mov     rcx, rbx; pti
0x1800045c1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800045c7  mov     rcx, rbx; pti
0x1800045ca  call    cs:__imp_CloseThreadpoolTimer
0x1800045d0  nop
0x1800045d1  mov     rcx, [rdi+10h]; lpMem
0x1800045d5  test    rcx, rcx
0x1800045d8  jz      short loc_1800045E0
0x1800045da  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800045df  nop
0x1800045e0  mov     rbx, [rsp+38h+arg_0]
0x1800045e5  mov     rsi, [rsp+38h+arg_8]
0x1800045ea  add     rsp, 30h
0x1800045ee  pop     rdi
0x1800045ef  retn
```
