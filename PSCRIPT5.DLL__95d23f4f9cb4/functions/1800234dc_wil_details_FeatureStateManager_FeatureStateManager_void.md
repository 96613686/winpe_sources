# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800234dc`
- end: `0x1800236c8`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18005c5a0`

## callees

- `0x180023398`
- `0x1800234dc`
- `0x180026cc0`
- `0x180027838`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18002359a`
- `KERNEL32!GetProcessHeap` at `0x1800235ea`
- `KERNEL32!GetProcessHeap` at `0x18002362a`
- `KERNEL32!GetProcessHeap` at `0x18002359a`
- `KERNEL32!GetProcessHeap` at `0x1800235ea`
- `KERNEL32!GetProcessHeap` at `0x18002362a`
- `KERNEL32!SetThreadpoolTimer` at `0x18002350d`
- `KERNEL32!SetThreadpoolTimer` at `0x180023556`
- `KERNEL32!SetThreadpoolTimer` at `0x18002365c`
- `KERNEL32!SetThreadpoolTimer` at `0x18002368d`
- `KERNEL32!SetThreadpoolTimer` at `0x18002350d`
- `KERNEL32!SetThreadpoolTimer` at `0x180023556`
- `KERNEL32!SetThreadpoolTimer` at `0x18002365c`
- `KERNEL32!SetThreadpoolTimer` at `0x18002368d`
- `KERNEL32!CloseThreadpoolTimer` at `0x180023524`
- `KERNEL32!CloseThreadpoolTimer` at `0x18002356d`
- `KERNEL32!CloseThreadpoolTimer` at `0x180023673`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800236a4`
- `KERNEL32!CloseThreadpoolTimer` at `0x180023524`
- `KERNEL32!CloseThreadpoolTimer` at `0x18002356d`
- `KERNEL32!CloseThreadpoolTimer` at `0x180023673`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800236a4`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18002351b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180023564`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18002366a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18002369b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18002351b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180023564`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18002366a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18002369b`
- `KERNEL32!HeapFree` at `0x1800235a8`
- `KERNEL32!HeapFree` at `0x1800235f8`
- `KERNEL32!HeapFree` at `0x180023638`
- `KERNEL32!HeapFree` at `0x1800235a8`
- `KERNEL32!HeapFree` at `0x1800235f8`
- `KERNEL32!HeapFree` at `0x180023638`
- `KERNEL32!DeleteCriticalSection` at `0x180023601`
- `KERNEL32!DeleteCriticalSection` at `0x180023642`
- `KERNEL32!DeleteCriticalSection` at `0x180023601`
- `KERNEL32!DeleteCriticalSection` at `0x180023642`
- `KERNEL32!SetLastError` at `0x18002352c`
- `KERNEL32!SetLastError` at `0x180023575`
- `KERNEL32!SetLastError` at `0x18002352c`
- `KERNEL32!SetLastError` at `0x180023575`
- `KERNEL32!GetLastError` at `0x1800234fa`
- `KERNEL32!GetLastError` at `0x180023543`
- `KERNEL32!GetLastError` at `0x1800234fa`
- `KERNEL32!GetLastError` at `0x180023543`

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
  if ( v8 && qword_180072198 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180072198[25], qword_180072198, v8);
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
0x1800234dc  mov     [rsp+arg_0], rbx
0x1800234e1  mov     [rsp+arg_8], rsi
0x1800234e6  push    rdi
0x1800234e7  sub     rsp, 20h
0x1800234eb  mov     byte ptr [rcx], 0
0x1800234ee  mov     rdi, rcx
0x1800234f1  mov     rsi, [rcx+30h]
0x1800234f5  test    rsi, rsi
0x1800234f8  jz      short loc_180023532
0x1800234fa  call    cs:__imp_GetLastError
0x180023500  xor     r9d, r9d; msWindowLength
0x180023503  xor     r8d, r8d; msPeriod
0x180023506  xor     edx, edx; pftDueTime
0x180023508  mov     rcx, rsi; pti
0x18002350b  mov     ebx, eax
0x18002350d  call    cs:__imp_SetThreadpoolTimer
0x180023513  mov     edx, 1; fCancelPendingCallbacks
0x180023518  mov     rcx, rsi; pti
0x18002351b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180023521  mov     rcx, rsi; pti
0x180023524  call    cs:__imp_CloseThreadpoolTimer
0x18002352a  mov     ecx, ebx; dwErrCode
0x18002352c  call    cs:__imp_SetLastError
0x180023532  mov     qword ptr [rdi+30h], 0
0x18002353a  mov     rsi, [rdi+38h]
0x18002353e  test    rsi, rsi
0x180023541  jz      short loc_18002357B
0x180023543  call    cs:__imp_GetLastError
0x180023549  xor     r9d, r9d; msWindowLength
0x18002354c  xor     r8d, r8d; msPeriod
0x18002354f  xor     edx, edx; pftDueTime
0x180023551  mov     rcx, rsi; pti
0x180023554  mov     ebx, eax
0x180023556  call    cs:__imp_SetThreadpoolTimer
0x18002355c  mov     edx, 1; fCancelPendingCallbacks
0x180023561  mov     rcx, rsi; pti
0x180023564  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002356a  mov     rcx, rsi; pti
0x18002356d  call    cs:__imp_CloseThreadpoolTimer
0x180023573  mov     ecx, ebx; dwErrCode
0x180023575  call    cs:__imp_SetLastError
0x18002357b  mov     qword ptr [rdi+38h], 0
0x180023583  mov     rbx, [rdi+100h]
0x18002358a  mov     qword ptr [rdi+100h], 0
0x180023595  test    rbx, rbx
0x180023598  jz      short loc_1800235AE
0x18002359a  call    cs:__imp_GetProcessHeap
0x1800235a0  mov     r8, rbx; lpMem
0x1800235a3  xor     edx, edx; dwFlags
0x1800235a5  mov     rcx, rax; hHeap
0x1800235a8  call    cs:__imp_HeapFree
0x1800235ae  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800235b5  test    r8, r8
0x1800235b8  jz      short loc_1800235D2
0x1800235ba  mov     rdx, cs:qword_180072198; SRWLock
0x1800235c1  test    rdx, rdx
0x1800235c4  jz      short loc_1800235D2
0x1800235c6  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800235cd  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800235d2  lea     rbx, [rdi+98h]
0x1800235d9  mov     rsi, [rbx+40h]
0x1800235dd  mov     qword ptr [rbx+40h], 0
0x1800235e5  test    rsi, rsi
0x1800235e8  jz      short loc_1800235FE
0x1800235ea  call    cs:__imp_GetProcessHeap
0x1800235f0  mov     r8, rsi; lpMem
0x1800235f3  xor     edx, edx; dwFlags
0x1800235f5  mov     rcx, rax; hHeap
0x1800235f8  call    cs:__imp_HeapFree
0x1800235fe  mov     rcx, rbx; lpCriticalSection
0x180023601  call    cs:__imp_DeleteCriticalSection
0x180023607  lea     rcx, [rdi+90h]
0x18002360e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180023613  mov     rsi, [rdi+88h]
0x18002361a  mov     qword ptr [rdi+88h], 0
0x180023625  test    rsi, rsi
0x180023628  jz      short loc_18002363E
0x18002362a  call    cs:__imp_GetProcessHeap
0x180023630  mov     r8, rsi; lpMem
0x180023633  xor     edx, edx; dwFlags
0x180023635  mov     rcx, rax; hHeap
0x180023638  call    cs:__imp_HeapFree
0x18002363e  lea     rcx, [rdi+48h]; lpCriticalSection
0x180023642  call    cs:__imp_DeleteCriticalSection
0x180023648  mov     rbx, [rdi+38h]
0x18002364c  test    rbx, rbx
0x18002364f  jz      short loc_180023679
0x180023651  xor     r9d, r9d; msWindowLength
0x180023654  xor     r8d, r8d; msPeriod
0x180023657  xor     edx, edx; pftDueTime
0x180023659  mov     rcx, rbx; pti
0x18002365c  call    cs:__imp_SetThreadpoolTimer
0x180023662  mov     edx, 1; fCancelPendingCallbacks
0x180023667  mov     rcx, rbx; pti
0x18002366a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180023670  mov     rcx, rbx; pti
0x180023673  call    cs:__imp_CloseThreadpoolTimer
0x180023679  mov     rbx, [rdi+30h]
0x18002367d  test    rbx, rbx
0x180023680  jz      short loc_1800236AA
0x180023682  xor     r9d, r9d; msWindowLength
0x180023685  xor     r8d, r8d; msPeriod
0x180023688  xor     edx, edx; pftDueTime
0x18002368a  mov     rcx, rbx; pti
0x18002368d  call    cs:__imp_SetThreadpoolTimer
0x180023693  mov     edx, 1; fCancelPendingCallbacks
0x180023698  mov     rcx, rbx; pti
0x18002369b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800236a1  mov     rcx, rbx; pti
0x1800236a4  call    cs:__imp_CloseThreadpoolTimer
0x1800236aa  mov     rcx, [rdi+10h]; lpMem
0x1800236ae  test    rcx, rcx
0x1800236b1  jz      short loc_1800236B8
0x1800236b3  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800236b8  mov     rbx, [rsp+28h+arg_0]
0x1800236bd  mov     rsi, [rsp+28h+arg_8]
0x1800236c2  add     rsp, 20h
0x1800236c6  pop     rdi
0x1800236c7  retn
```
