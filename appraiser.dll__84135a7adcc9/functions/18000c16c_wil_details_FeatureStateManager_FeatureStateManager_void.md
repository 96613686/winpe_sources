# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000c16c`
- end: `0x18000c364`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `504`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18021bbd0`

## callees

- `0x18000bee8`
- `0x18000c16c`
- `0x180010a2c`
- `0x1800124bc`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000c234`
- `KERNEL32!GetProcessHeap` at `0x18000c284`
- `KERNEL32!GetProcessHeap` at `0x18000c2c4`
- `KERNEL32!GetProcessHeap` at `0x18000c234`
- `KERNEL32!GetProcessHeap` at `0x18000c284`
- `KERNEL32!GetProcessHeap` at `0x18000c2c4`
- `KERNEL32!DeleteCriticalSection` at `0x18000c29b`
- `KERNEL32!DeleteCriticalSection` at `0x18000c2dc`
- `KERNEL32!DeleteCriticalSection` at `0x18000c29b`
- `KERNEL32!DeleteCriticalSection` at `0x18000c2dc`
- `KERNEL32!SetThreadpoolTimer` at `0x18000c1a7`
- `KERNEL32!SetThreadpoolTimer` at `0x18000c1f0`
- `KERNEL32!SetThreadpoolTimer` at `0x18000c2f6`
- `KERNEL32!SetThreadpoolTimer` at `0x18000c327`
- `KERNEL32!SetThreadpoolTimer` at `0x18000c1a7`
- `KERNEL32!SetThreadpoolTimer` at `0x18000c1f0`
- `KERNEL32!SetThreadpoolTimer` at `0x18000c2f6`
- `KERNEL32!SetThreadpoolTimer` at `0x18000c327`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000c1be`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000c207`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000c30d`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000c33e`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000c1be`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000c207`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000c30d`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000c33e`
- `KERNEL32!GetLastError` at `0x18000c194`
- `KERNEL32!GetLastError` at `0x18000c1dd`
- `KERNEL32!GetLastError` at `0x18000c194`
- `KERNEL32!GetLastError` at `0x18000c1dd`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000c1b5`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000c1fe`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000c304`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000c335`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000c1b5`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000c1fe`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000c304`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000c335`
- `KERNEL32!SetLastError` at `0x18000c1c6`
- `KERNEL32!SetLastError` at `0x18000c20f`
- `KERNEL32!SetLastError` at `0x18000c1c6`
- `KERNEL32!SetLastError` at `0x18000c20f`
- `KERNEL32!HeapFree` at `0x18000c242`
- `KERNEL32!HeapFree` at `0x18000c292`
- `KERNEL32!HeapFree` at `0x18000c2d2`
- `KERNEL32!HeapFree` at `0x18000c242`
- `KERNEL32!HeapFree` at `0x18000c292`
- `KERNEL32!HeapFree` at `0x18000c2d2`

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
  if ( v8 && qword_1802C9438 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1802C9438[25], qword_1802C9438, v8);
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
0x18000c16c  push    rdi
0x18000c16e  sub     rsp, 30h
0x18000c172  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000c17b  mov     [rsp+38h+arg_0], rbx
0x18000c180  mov     [rsp+38h+arg_8], rsi
0x18000c185  mov     rdi, rcx
0x18000c188  mov     byte ptr [rcx], 0
0x18000c18b  mov     rsi, [rcx+30h]
0x18000c18f  test    rsi, rsi
0x18000c192  jz      short loc_18000C1CC
0x18000c194  call    cs:__imp_GetLastError
0x18000c19a  mov     ebx, eax
0x18000c19c  xor     r9d, r9d; msWindowLength
0x18000c19f  xor     r8d, r8d; msPeriod
0x18000c1a2  xor     edx, edx; pftDueTime
0x18000c1a4  mov     rcx, rsi; pti
0x18000c1a7  call    cs:__imp_SetThreadpoolTimer
0x18000c1ad  mov     edx, 1; fCancelPendingCallbacks
0x18000c1b2  mov     rcx, rsi; pti
0x18000c1b5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c1bb  mov     rcx, rsi; pti
0x18000c1be  call    cs:__imp_CloseThreadpoolTimer
0x18000c1c4  mov     ecx, ebx; dwErrCode
0x18000c1c6  call    cs:__imp_SetLastError
0x18000c1cc  mov     qword ptr [rdi+30h], 0
0x18000c1d4  mov     rsi, [rdi+38h]
0x18000c1d8  test    rsi, rsi
0x18000c1db  jz      short loc_18000C215
0x18000c1dd  call    cs:__imp_GetLastError
0x18000c1e3  mov     ebx, eax
0x18000c1e5  xor     r9d, r9d; msWindowLength
0x18000c1e8  xor     r8d, r8d; msPeriod
0x18000c1eb  xor     edx, edx; pftDueTime
0x18000c1ed  mov     rcx, rsi; pti
0x18000c1f0  call    cs:__imp_SetThreadpoolTimer
0x18000c1f6  mov     edx, 1; fCancelPendingCallbacks
0x18000c1fb  mov     rcx, rsi; pti
0x18000c1fe  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c204  mov     rcx, rsi; pti
0x18000c207  call    cs:__imp_CloseThreadpoolTimer
0x18000c20d  mov     ecx, ebx; dwErrCode
0x18000c20f  call    cs:__imp_SetLastError
0x18000c215  mov     qword ptr [rdi+38h], 0
0x18000c21d  mov     rbx, [rdi+100h]
0x18000c224  mov     qword ptr [rdi+100h], 0
0x18000c22f  test    rbx, rbx
0x18000c232  jz      short loc_18000C248
0x18000c234  call    cs:__imp_GetProcessHeap
0x18000c23a  mov     rcx, rax; hHeap
0x18000c23d  mov     r8, rbx; lpMem
0x18000c240  xor     edx, edx; dwFlags
0x18000c242  call    cs:__imp_HeapFree
0x18000c248  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18000c24f  test    r8, r8
0x18000c252  jz      short loc_18000C26C
0x18000c254  mov     rdx, cs:qword_1802C9438; SRWLock
0x18000c25b  test    rdx, rdx
0x18000c25e  jz      short loc_18000C26C
0x18000c260  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000c267  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000c26c  lea     rbx, [rdi+98h]
0x18000c273  mov     rsi, [rbx+40h]
0x18000c277  mov     qword ptr [rbx+40h], 0
0x18000c27f  test    rsi, rsi
0x18000c282  jz      short loc_18000C298
0x18000c284  call    cs:__imp_GetProcessHeap
0x18000c28a  mov     rcx, rax; hHeap
0x18000c28d  mov     r8, rsi; lpMem
0x18000c290  xor     edx, edx; dwFlags
0x18000c292  call    cs:__imp_HeapFree
0x18000c298  mov     rcx, rbx; lpCriticalSection
0x18000c29b  call    cs:__imp_DeleteCriticalSection
0x18000c2a1  lea     rcx, [rdi+90h]
0x18000c2a8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000c2ad  mov     rsi, [rdi+88h]
0x18000c2b4  mov     qword ptr [rdi+88h], 0
0x18000c2bf  test    rsi, rsi
0x18000c2c2  jz      short loc_18000C2D8
0x18000c2c4  call    cs:__imp_GetProcessHeap
0x18000c2ca  mov     rcx, rax; hHeap
0x18000c2cd  mov     r8, rsi; lpMem
0x18000c2d0  xor     edx, edx; dwFlags
0x18000c2d2  call    cs:__imp_HeapFree
0x18000c2d8  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000c2dc  call    cs:__imp_DeleteCriticalSection
0x18000c2e2  mov     rbx, [rdi+38h]
0x18000c2e6  test    rbx, rbx
0x18000c2e9  jz      short loc_18000C313
0x18000c2eb  xor     r9d, r9d; msWindowLength
0x18000c2ee  xor     r8d, r8d; msPeriod
0x18000c2f1  xor     edx, edx; pftDueTime
0x18000c2f3  mov     rcx, rbx; pti
0x18000c2f6  call    cs:__imp_SetThreadpoolTimer
0x18000c2fc  mov     edx, 1; fCancelPendingCallbacks
0x18000c301  mov     rcx, rbx; pti
0x18000c304  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c30a  mov     rcx, rbx; pti
0x18000c30d  call    cs:__imp_CloseThreadpoolTimer
0x18000c313  mov     rbx, [rdi+30h]
0x18000c317  test    rbx, rbx
0x18000c31a  jz      short loc_18000C345
0x18000c31c  xor     r9d, r9d; msWindowLength
0x18000c31f  xor     r8d, r8d; msPeriod
0x18000c322  xor     edx, edx; pftDueTime
0x18000c324  mov     rcx, rbx; pti
0x18000c327  call    cs:__imp_SetThreadpoolTimer
0x18000c32d  mov     edx, 1; fCancelPendingCallbacks
0x18000c332  mov     rcx, rbx; pti
0x18000c335  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c33b  mov     rcx, rbx; pti
0x18000c33e  call    cs:__imp_CloseThreadpoolTimer
0x18000c344  nop
0x18000c345  mov     rcx, [rdi+10h]; lpMem
0x18000c349  test    rcx, rcx
0x18000c34c  jz      short loc_18000C354
0x18000c34e  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18000c353  nop
0x18000c354  mov     rbx, [rsp+38h+arg_0]
0x18000c359  mov     rsi, [rsp+38h+arg_8]
0x18000c35e  add     rsp, 30h
0x18000c362  pop     rdi
0x18000c363  retn
```
