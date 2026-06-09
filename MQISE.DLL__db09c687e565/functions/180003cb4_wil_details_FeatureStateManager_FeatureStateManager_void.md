# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180003cb4`
- end: `0x180003eb5`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `513`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180010060`

## callees

- `0x180003870`
- `0x180003cb4`
- `0x1800093d8`
- `0x18000a7b8`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x180003cfe`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003d4b`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003e5b`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003e8f`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003cfe`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003d4b`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003e5b`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003e8f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003cf4`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003d41`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003e51`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003e85`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003cf4`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003d41`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003e51`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003e85`
- `KERNEL32!SetThreadpoolTimer` at `0x180003ce5`
- `KERNEL32!SetThreadpoolTimer` at `0x180003d32`
- `KERNEL32!SetThreadpoolTimer` at `0x180003e42`
- `KERNEL32!SetThreadpoolTimer` at `0x180003e76`
- `KERNEL32!SetThreadpoolTimer` at `0x180003ce5`
- `KERNEL32!SetThreadpoolTimer` at `0x180003d32`
- `KERNEL32!SetThreadpoolTimer` at `0x180003e42`
- `KERNEL32!SetThreadpoolTimer` at `0x180003e76`
- `KERNEL32!SetLastError` at `0x180003d07`
- `KERNEL32!SetLastError` at `0x180003d54`
- `KERNEL32!SetLastError` at `0x180003d07`
- `KERNEL32!SetLastError` at `0x180003d54`
- `KERNEL32!GetProcessHeap` at `0x180003d7a`
- `KERNEL32!GetProcessHeap` at `0x180003dcb`
- `KERNEL32!GetProcessHeap` at `0x180003e0e`
- `KERNEL32!GetProcessHeap` at `0x180003d7a`
- `KERNEL32!GetProcessHeap` at `0x180003dcb`
- `KERNEL32!GetProcessHeap` at `0x180003e0e`
- `KERNEL32!HeapFree` at `0x180003d88`
- `KERNEL32!HeapFree` at `0x180003dd9`
- `KERNEL32!HeapFree` at `0x180003e1c`
- `KERNEL32!HeapFree` at `0x180003d88`
- `KERNEL32!HeapFree` at `0x180003dd9`
- `KERNEL32!HeapFree` at `0x180003e1c`
- `KERNEL32!DeleteCriticalSection` at `0x180003de3`
- `KERNEL32!DeleteCriticalSection` at `0x180003e27`
- `KERNEL32!DeleteCriticalSection` at `0x180003de3`
- `KERNEL32!DeleteCriticalSection` at `0x180003e27`
- `KERNEL32!GetLastError` at `0x180003cd2`
- `KERNEL32!GetLastError` at `0x180003d1f`
- `KERNEL32!GetLastError` at `0x180003cd2`
- `KERNEL32!GetLastError` at `0x180003d1f`

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
  if ( v8 && qword_180017038 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180017038[25], qword_180017038, v8);
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
0x180003cb4  mov     [rsp+arg_0], rbx
0x180003cb9  mov     [rsp+arg_8], rsi
0x180003cbe  push    rdi
0x180003cbf  sub     rsp, 20h
0x180003cc3  mov     rdi, rcx
0x180003cc6  mov     byte ptr [rcx], 0
0x180003cc9  mov     rsi, [rcx+30h]
0x180003ccd  test    rsi, rsi
0x180003cd0  jz      short loc_180003D0E
0x180003cd2  call    cs:__imp_GetLastError
0x180003cd8  mov     ebx, eax
0x180003cda  xor     r9d, r9d; msWindowLength
0x180003cdd  xor     r8d, r8d; msPeriod
0x180003ce0  xor     edx, edx; pftDueTime
0x180003ce2  mov     rcx, rsi; pti
0x180003ce5  call    cs:__imp_SetThreadpoolTimer
0x180003ceb  nop
0x180003cec  mov     edx, 1; fCancelPendingCallbacks
0x180003cf1  mov     rcx, rsi; pti
0x180003cf4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003cfa  nop
0x180003cfb  mov     rcx, rsi; pti
0x180003cfe  call    cs:__imp_CloseThreadpoolTimer
0x180003d04  nop
0x180003d05  mov     ecx, ebx; dwErrCode
0x180003d07  call    cs:__imp_SetLastError
0x180003d0d  nop
0x180003d0e  mov     qword ptr [rdi+30h], 0
0x180003d16  mov     rsi, [rdi+38h]
0x180003d1a  test    rsi, rsi
0x180003d1d  jz      short loc_180003D5B
0x180003d1f  call    cs:__imp_GetLastError
0x180003d25  mov     ebx, eax
0x180003d27  xor     r9d, r9d; msWindowLength
0x180003d2a  xor     r8d, r8d; msPeriod
0x180003d2d  xor     edx, edx; pftDueTime
0x180003d2f  mov     rcx, rsi; pti
0x180003d32  call    cs:__imp_SetThreadpoolTimer
0x180003d38  nop
0x180003d39  mov     edx, 1; fCancelPendingCallbacks
0x180003d3e  mov     rcx, rsi; pti
0x180003d41  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003d47  nop
0x180003d48  mov     rcx, rsi; pti
0x180003d4b  call    cs:__imp_CloseThreadpoolTimer
0x180003d51  nop
0x180003d52  mov     ecx, ebx; dwErrCode
0x180003d54  call    cs:__imp_SetLastError
0x180003d5a  nop
0x180003d5b  mov     qword ptr [rdi+38h], 0
0x180003d63  mov     rbx, [rdi+100h]
0x180003d6a  mov     qword ptr [rdi+100h], 0
0x180003d75  test    rbx, rbx
0x180003d78  jz      short loc_180003D8F
0x180003d7a  call    cs:__imp_GetProcessHeap
0x180003d80  mov     rcx, rax; hHeap
0x180003d83  mov     r8, rbx; lpMem
0x180003d86  xor     edx, edx; dwFlags
0x180003d88  call    cs:__imp_HeapFree
0x180003d8e  nop
0x180003d8f  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180003d96  test    r8, r8
0x180003d99  jz      short loc_180003DB3
0x180003d9b  mov     rdx, cs:qword_180017038; SRWLock
0x180003da2  test    rdx, rdx
0x180003da5  jz      short loc_180003DB3
0x180003da7  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180003dae  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180003db3  lea     rbx, [rdi+98h]
0x180003dba  mov     rsi, [rbx+40h]
0x180003dbe  mov     qword ptr [rbx+40h], 0
0x180003dc6  test    rsi, rsi
0x180003dc9  jz      short loc_180003DE0
0x180003dcb  call    cs:__imp_GetProcessHeap
0x180003dd1  mov     rcx, rax; hHeap
0x180003dd4  mov     r8, rsi; lpMem
0x180003dd7  xor     edx, edx; dwFlags
0x180003dd9  call    cs:__imp_HeapFree
0x180003ddf  nop
0x180003de0  mov     rcx, rbx; lpCriticalSection
0x180003de3  call    cs:__imp_DeleteCriticalSection
0x180003de9  nop
0x180003dea  lea     rcx, [rdi+90h]
0x180003df1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180003df6  nop
0x180003df7  mov     rsi, [rdi+88h]
0x180003dfe  mov     qword ptr [rdi+88h], 0
0x180003e09  test    rsi, rsi
0x180003e0c  jz      short loc_180003E23
0x180003e0e  call    cs:__imp_GetProcessHeap
0x180003e14  mov     rcx, rax; hHeap
0x180003e17  mov     r8, rsi; lpMem
0x180003e1a  xor     edx, edx; dwFlags
0x180003e1c  call    cs:__imp_HeapFree
0x180003e22  nop
0x180003e23  lea     rcx, [rdi+48h]; lpCriticalSection
0x180003e27  call    cs:__imp_DeleteCriticalSection
0x180003e2d  nop
0x180003e2e  mov     rbx, [rdi+38h]
0x180003e32  test    rbx, rbx
0x180003e35  jz      short loc_180003E62
0x180003e37  xor     r9d, r9d; msWindowLength
0x180003e3a  xor     r8d, r8d; msPeriod
0x180003e3d  xor     edx, edx; pftDueTime
0x180003e3f  mov     rcx, rbx; pti
0x180003e42  call    cs:__imp_SetThreadpoolTimer
0x180003e48  nop
0x180003e49  mov     edx, 1; fCancelPendingCallbacks
0x180003e4e  mov     rcx, rbx; pti
0x180003e51  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003e57  nop
0x180003e58  mov     rcx, rbx; pti
0x180003e5b  call    cs:__imp_CloseThreadpoolTimer
0x180003e61  nop
0x180003e62  mov     rbx, [rdi+30h]
0x180003e66  test    rbx, rbx
0x180003e69  jz      short loc_180003E96
0x180003e6b  xor     r9d, r9d; msWindowLength
0x180003e6e  xor     r8d, r8d; msPeriod
0x180003e71  xor     edx, edx; pftDueTime
0x180003e73  mov     rcx, rbx; pti
0x180003e76  call    cs:__imp_SetThreadpoolTimer
0x180003e7c  nop
0x180003e7d  mov     edx, 1; fCancelPendingCallbacks
0x180003e82  mov     rcx, rbx; pti
0x180003e85  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003e8b  nop
0x180003e8c  mov     rcx, rbx; pti
0x180003e8f  call    cs:__imp_CloseThreadpoolTimer
0x180003e95  nop
0x180003e96  mov     rcx, [rdi+10h]; lpMem
0x180003e9a  test    rcx, rcx
0x180003e9d  jz      short loc_180003EA5
0x180003e9f  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180003ea4  nop
0x180003ea5  mov     rbx, [rsp+28h+arg_0]
0x180003eaa  mov     rsi, [rsp+28h+arg_8]
0x180003eaf  add     rsp, 20h
0x180003eb3  pop     rdi
0x180003eb4  retn
```
