# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800109f8`
- end: `0x180010bea`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `498`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800180e0`

## callees

- `0x180010754`
- `0x1800109f8`
- `0x180014484`
- `0x1800155a0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180010ac8`
- `KERNEL32!HeapFree` at `0x180010b18`
- `KERNEL32!HeapFree` at `0x180010b58`
- `KERNEL32!HeapFree` at `0x180010ac8`
- `KERNEL32!HeapFree` at `0x180010b18`
- `KERNEL32!HeapFree` at `0x180010b58`
- `KERNEL32!GetProcessHeap` at `0x180010aba`
- `KERNEL32!GetProcessHeap` at `0x180010b0a`
- `KERNEL32!GetProcessHeap` at `0x180010b4a`
- `KERNEL32!GetProcessHeap` at `0x180010aba`
- `KERNEL32!GetProcessHeap` at `0x180010b0a`
- `KERNEL32!GetProcessHeap` at `0x180010b4a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180010a37`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180010a82`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180010b8a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180010bbb`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180010a37`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180010a82`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180010b8a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180010bbb`
- `KERNEL32!CloseThreadpoolTimer` at `0x180010a40`
- `KERNEL32!CloseThreadpoolTimer` at `0x180010a8b`
- `KERNEL32!CloseThreadpoolTimer` at `0x180010b93`
- `KERNEL32!CloseThreadpoolTimer` at `0x180010bc4`
- `KERNEL32!CloseThreadpoolTimer` at `0x180010a40`
- `KERNEL32!CloseThreadpoolTimer` at `0x180010a8b`
- `KERNEL32!CloseThreadpoolTimer` at `0x180010b93`
- `KERNEL32!CloseThreadpoolTimer` at `0x180010bc4`
- `KERNEL32!SetThreadpoolTimer` at `0x180010a29`
- `KERNEL32!SetThreadpoolTimer` at `0x180010a74`
- `KERNEL32!SetThreadpoolTimer` at `0x180010b7c`
- `KERNEL32!SetThreadpoolTimer` at `0x180010bad`
- `KERNEL32!SetThreadpoolTimer` at `0x180010a29`
- `KERNEL32!SetThreadpoolTimer` at `0x180010a74`
- `KERNEL32!SetThreadpoolTimer` at `0x180010b7c`
- `KERNEL32!SetThreadpoolTimer` at `0x180010bad`
- `KERNEL32!DeleteCriticalSection` at `0x180010b21`
- `KERNEL32!DeleteCriticalSection` at `0x180010b62`
- `KERNEL32!DeleteCriticalSection` at `0x180010b21`
- `KERNEL32!DeleteCriticalSection` at `0x180010b62`
- `KERNEL32!GetLastError` at `0x180010a16`
- `KERNEL32!GetLastError` at `0x180010a61`
- `KERNEL32!GetLastError` at `0x180010a16`
- `KERNEL32!GetLastError` at `0x180010a61`
- `KERNEL32!SetLastError` at `0x180010a49`
- `KERNEL32!SetLastError` at `0x180010a94`
- `KERNEL32!SetLastError` at `0x180010a49`
- `KERNEL32!SetLastError` at `0x180010a94`

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
  if ( v8 && qword_180070028 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180070028[25], qword_180070028, v8);
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
0x1800109f8  mov     [rsp+arg_0], rbx
0x1800109fd  mov     [rsp+arg_8], rsi
0x180010a02  push    rdi
0x180010a03  sub     rsp, 20h
0x180010a07  mov     rdi, rcx
0x180010a0a  mov     byte ptr [rcx], 0
0x180010a0d  mov     rsi, [rcx+30h]
0x180010a11  test    rsi, rsi
0x180010a14  jz      short loc_180010A50
0x180010a16  call    cs:__imp_GetLastError
0x180010a1c  mov     ebx, eax
0x180010a1e  xor     r9d, r9d; msWindowLength
0x180010a21  xor     r8d, r8d; msPeriod
0x180010a24  xor     edx, edx; pftDueTime
0x180010a26  mov     rcx, rsi; pti
0x180010a29  call    cs:__imp_SetThreadpoolTimer
0x180010a2f  mov     edx, 1; fCancelPendingCallbacks
0x180010a34  mov     rcx, rsi; pti
0x180010a37  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010a3d  mov     rcx, rsi; pti
0x180010a40  call    cs:__imp_CloseThreadpoolTimer
0x180010a46  nop
0x180010a47  mov     ecx, ebx; dwErrCode
0x180010a49  call    cs:__imp_SetLastError
0x180010a4f  nop
0x180010a50  mov     qword ptr [rdi+30h], 0
0x180010a58  mov     rsi, [rdi+38h]
0x180010a5c  test    rsi, rsi
0x180010a5f  jz      short loc_180010A9B
0x180010a61  call    cs:__imp_GetLastError
0x180010a67  mov     ebx, eax
0x180010a69  xor     r9d, r9d; msWindowLength
0x180010a6c  xor     r8d, r8d; msPeriod
0x180010a6f  xor     edx, edx; pftDueTime
0x180010a71  mov     rcx, rsi; pti
0x180010a74  call    cs:__imp_SetThreadpoolTimer
0x180010a7a  mov     edx, 1; fCancelPendingCallbacks
0x180010a7f  mov     rcx, rsi; pti
0x180010a82  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010a88  mov     rcx, rsi; pti
0x180010a8b  call    cs:__imp_CloseThreadpoolTimer
0x180010a91  nop
0x180010a92  mov     ecx, ebx; dwErrCode
0x180010a94  call    cs:__imp_SetLastError
0x180010a9a  nop
0x180010a9b  mov     qword ptr [rdi+38h], 0
0x180010aa3  mov     rbx, [rdi+100h]
0x180010aaa  mov     qword ptr [rdi+100h], 0
0x180010ab5  test    rbx, rbx
0x180010ab8  jz      short loc_180010ACE
0x180010aba  call    cs:__imp_GetProcessHeap
0x180010ac0  mov     rcx, rax; hHeap
0x180010ac3  mov     r8, rbx; lpMem
0x180010ac6  xor     edx, edx; dwFlags
0x180010ac8  call    cs:__imp_HeapFree
0x180010ace  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180010ad5  test    r8, r8
0x180010ad8  jz      short loc_180010AF2
0x180010ada  mov     rdx, cs:qword_180070028; SRWLock
0x180010ae1  test    rdx, rdx
0x180010ae4  jz      short loc_180010AF2
0x180010ae6  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180010aed  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180010af2  lea     rbx, [rdi+98h]
0x180010af9  mov     rsi, [rbx+40h]
0x180010afd  mov     qword ptr [rbx+40h], 0
0x180010b05  test    rsi, rsi
0x180010b08  jz      short loc_180010B1E
0x180010b0a  call    cs:__imp_GetProcessHeap
0x180010b10  mov     rcx, rax; hHeap
0x180010b13  mov     r8, rsi; lpMem
0x180010b16  xor     edx, edx; dwFlags
0x180010b18  call    cs:__imp_HeapFree
0x180010b1e  mov     rcx, rbx; lpCriticalSection
0x180010b21  call    cs:__imp_DeleteCriticalSection
0x180010b27  lea     rcx, [rdi+90h]
0x180010b2e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180010b33  mov     rsi, [rdi+88h]
0x180010b3a  mov     qword ptr [rdi+88h], 0
0x180010b45  test    rsi, rsi
0x180010b48  jz      short loc_180010B5E
0x180010b4a  call    cs:__imp_GetProcessHeap
0x180010b50  mov     rcx, rax; hHeap
0x180010b53  mov     r8, rsi; lpMem
0x180010b56  xor     edx, edx; dwFlags
0x180010b58  call    cs:__imp_HeapFree
0x180010b5e  lea     rcx, [rdi+48h]; lpCriticalSection
0x180010b62  call    cs:__imp_DeleteCriticalSection
0x180010b68  mov     rbx, [rdi+38h]
0x180010b6c  test    rbx, rbx
0x180010b6f  jz      short loc_180010B99
0x180010b71  xor     r9d, r9d; msWindowLength
0x180010b74  xor     r8d, r8d; msPeriod
0x180010b77  xor     edx, edx; pftDueTime
0x180010b79  mov     rcx, rbx; pti
0x180010b7c  call    cs:__imp_SetThreadpoolTimer
0x180010b82  mov     edx, 1; fCancelPendingCallbacks
0x180010b87  mov     rcx, rbx; pti
0x180010b8a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010b90  mov     rcx, rbx; pti
0x180010b93  call    cs:__imp_CloseThreadpoolTimer
0x180010b99  mov     rbx, [rdi+30h]
0x180010b9d  test    rbx, rbx
0x180010ba0  jz      short loc_180010BCB
0x180010ba2  xor     r9d, r9d; msWindowLength
0x180010ba5  xor     r8d, r8d; msPeriod
0x180010ba8  xor     edx, edx; pftDueTime
0x180010baa  mov     rcx, rbx; pti
0x180010bad  call    cs:__imp_SetThreadpoolTimer
0x180010bb3  mov     edx, 1; fCancelPendingCallbacks
0x180010bb8  mov     rcx, rbx; pti
0x180010bbb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010bc1  mov     rcx, rbx; pti
0x180010bc4  call    cs:__imp_CloseThreadpoolTimer
0x180010bca  nop
0x180010bcb  mov     rcx, [rdi+10h]; lpMem
0x180010bcf  test    rcx, rcx
0x180010bd2  jz      short loc_180010BDA
0x180010bd4  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180010bd9  nop
0x180010bda  mov     rbx, [rsp+28h+arg_0]
0x180010bdf  mov     rsi, [rsp+28h+arg_8]
0x180010be4  add     rsp, 20h
0x180010be8  pop     rdi
0x180010be9  retn
```
