# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x140003b94`
- end: `0x140003d80`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140016140`

## callees

- `0x1400038d8`
- `0x140003b94`
- `0x140008bb4`
- `0x14000a11c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140003c60`
- `KERNEL32!HeapFree` at `0x140003cb0`
- `KERNEL32!HeapFree` at `0x140003cf0`
- `KERNEL32!HeapFree` at `0x140003c60`
- `KERNEL32!HeapFree` at `0x140003cb0`
- `KERNEL32!HeapFree` at `0x140003cf0`
- `KERNEL32!SetLastError` at `0x140003be4`
- `KERNEL32!SetLastError` at `0x140003c2d`
- `KERNEL32!SetLastError` at `0x140003be4`
- `KERNEL32!SetLastError` at `0x140003c2d`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140003bd3`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140003c1c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140003d22`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140003d53`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140003bd3`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140003c1c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140003d22`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140003d53`
- `KERNEL32!GetLastError` at `0x140003bb2`
- `KERNEL32!GetLastError` at `0x140003bfb`
- `KERNEL32!GetLastError` at `0x140003bb2`
- `KERNEL32!GetLastError` at `0x140003bfb`
- `KERNEL32!CloseThreadpoolTimer` at `0x140003bdc`
- `KERNEL32!CloseThreadpoolTimer` at `0x140003c25`
- `KERNEL32!CloseThreadpoolTimer` at `0x140003d2b`
- `KERNEL32!CloseThreadpoolTimer` at `0x140003d5c`
- `KERNEL32!CloseThreadpoolTimer` at `0x140003bdc`
- `KERNEL32!CloseThreadpoolTimer` at `0x140003c25`
- `KERNEL32!CloseThreadpoolTimer` at `0x140003d2b`
- `KERNEL32!CloseThreadpoolTimer` at `0x140003d5c`
- `KERNEL32!SetThreadpoolTimer` at `0x140003bc5`
- `KERNEL32!SetThreadpoolTimer` at `0x140003c0e`
- `KERNEL32!SetThreadpoolTimer` at `0x140003d14`
- `KERNEL32!SetThreadpoolTimer` at `0x140003d45`
- `KERNEL32!SetThreadpoolTimer` at `0x140003bc5`
- `KERNEL32!SetThreadpoolTimer` at `0x140003c0e`
- `KERNEL32!SetThreadpoolTimer` at `0x140003d14`
- `KERNEL32!SetThreadpoolTimer` at `0x140003d45`
- `KERNEL32!DeleteCriticalSection` at `0x140003cb9`
- `KERNEL32!DeleteCriticalSection` at `0x140003cfa`
- `KERNEL32!DeleteCriticalSection` at `0x140003cb9`
- `KERNEL32!DeleteCriticalSection` at `0x140003cfa`
- `KERNEL32!GetProcessHeap` at `0x140003c52`
- `KERNEL32!GetProcessHeap` at `0x140003ca2`
- `KERNEL32!GetProcessHeap` at `0x140003ce2`
- `KERNEL32!GetProcessHeap` at `0x140003c52`
- `KERNEL32!GetProcessHeap` at `0x140003ca2`
- `KERNEL32!GetProcessHeap` at `0x140003ce2`

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
  if ( v8 && qword_1400203C8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1400203C8[25], qword_1400203C8, v8);
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
0x140003b94  mov     [rsp+arg_0], rbx
0x140003b99  mov     [rsp+arg_8], rsi
0x140003b9e  push    rdi
0x140003b9f  sub     rsp, 20h
0x140003ba3  mov     byte ptr [rcx], 0
0x140003ba6  mov     rdi, rcx
0x140003ba9  mov     rsi, [rcx+30h]
0x140003bad  test    rsi, rsi
0x140003bb0  jz      short loc_140003BEA
0x140003bb2  call    cs:__imp_GetLastError
0x140003bb8  xor     r9d, r9d; msWindowLength
0x140003bbb  xor     r8d, r8d; msPeriod
0x140003bbe  xor     edx, edx; pftDueTime
0x140003bc0  mov     rcx, rsi; pti
0x140003bc3  mov     ebx, eax
0x140003bc5  call    cs:__imp_SetThreadpoolTimer
0x140003bcb  mov     edx, 1; fCancelPendingCallbacks
0x140003bd0  mov     rcx, rsi; pti
0x140003bd3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140003bd9  mov     rcx, rsi; pti
0x140003bdc  call    cs:__imp_CloseThreadpoolTimer
0x140003be2  mov     ecx, ebx; dwErrCode
0x140003be4  call    cs:__imp_SetLastError
0x140003bea  mov     qword ptr [rdi+30h], 0
0x140003bf2  mov     rsi, [rdi+38h]
0x140003bf6  test    rsi, rsi
0x140003bf9  jz      short loc_140003C33
0x140003bfb  call    cs:__imp_GetLastError
0x140003c01  xor     r9d, r9d; msWindowLength
0x140003c04  xor     r8d, r8d; msPeriod
0x140003c07  xor     edx, edx; pftDueTime
0x140003c09  mov     rcx, rsi; pti
0x140003c0c  mov     ebx, eax
0x140003c0e  call    cs:__imp_SetThreadpoolTimer
0x140003c14  mov     edx, 1; fCancelPendingCallbacks
0x140003c19  mov     rcx, rsi; pti
0x140003c1c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140003c22  mov     rcx, rsi; pti
0x140003c25  call    cs:__imp_CloseThreadpoolTimer
0x140003c2b  mov     ecx, ebx; dwErrCode
0x140003c2d  call    cs:__imp_SetLastError
0x140003c33  mov     qword ptr [rdi+38h], 0
0x140003c3b  mov     rbx, [rdi+100h]
0x140003c42  mov     qword ptr [rdi+100h], 0
0x140003c4d  test    rbx, rbx
0x140003c50  jz      short loc_140003C66
0x140003c52  call    cs:__imp_GetProcessHeap
0x140003c58  mov     r8, rbx; lpMem
0x140003c5b  xor     edx, edx; dwFlags
0x140003c5d  mov     rcx, rax; hHeap
0x140003c60  call    cs:__imp_HeapFree
0x140003c66  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x140003c6d  test    r8, r8
0x140003c70  jz      short loc_140003C8A
0x140003c72  mov     rdx, cs:qword_1400203C8; SRWLock
0x140003c79  test    rdx, rdx
0x140003c7c  jz      short loc_140003C8A
0x140003c7e  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140003c85  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x140003c8a  lea     rbx, [rdi+98h]
0x140003c91  mov     rsi, [rbx+40h]
0x140003c95  mov     qword ptr [rbx+40h], 0
0x140003c9d  test    rsi, rsi
0x140003ca0  jz      short loc_140003CB6
0x140003ca2  call    cs:__imp_GetProcessHeap
0x140003ca8  mov     r8, rsi; lpMem
0x140003cab  xor     edx, edx; dwFlags
0x140003cad  mov     rcx, rax; hHeap
0x140003cb0  call    cs:__imp_HeapFree
0x140003cb6  mov     rcx, rbx; lpCriticalSection
0x140003cb9  call    cs:__imp_DeleteCriticalSection
0x140003cbf  lea     rcx, [rdi+90h]
0x140003cc6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140003ccb  mov     rsi, [rdi+88h]
0x140003cd2  mov     qword ptr [rdi+88h], 0
0x140003cdd  test    rsi, rsi
0x140003ce0  jz      short loc_140003CF6
0x140003ce2  call    cs:__imp_GetProcessHeap
0x140003ce8  mov     r8, rsi; lpMem
0x140003ceb  xor     edx, edx; dwFlags
0x140003ced  mov     rcx, rax; hHeap
0x140003cf0  call    cs:__imp_HeapFree
0x140003cf6  lea     rcx, [rdi+48h]; lpCriticalSection
0x140003cfa  call    cs:__imp_DeleteCriticalSection
0x140003d00  mov     rbx, [rdi+38h]
0x140003d04  test    rbx, rbx
0x140003d07  jz      short loc_140003D31
0x140003d09  xor     r9d, r9d; msWindowLength
0x140003d0c  xor     r8d, r8d; msPeriod
0x140003d0f  xor     edx, edx; pftDueTime
0x140003d11  mov     rcx, rbx; pti
0x140003d14  call    cs:__imp_SetThreadpoolTimer
0x140003d1a  mov     edx, 1; fCancelPendingCallbacks
0x140003d1f  mov     rcx, rbx; pti
0x140003d22  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140003d28  mov     rcx, rbx; pti
0x140003d2b  call    cs:__imp_CloseThreadpoolTimer
0x140003d31  mov     rbx, [rdi+30h]
0x140003d35  test    rbx, rbx
0x140003d38  jz      short loc_140003D62
0x140003d3a  xor     r9d, r9d; msWindowLength
0x140003d3d  xor     r8d, r8d; msPeriod
0x140003d40  xor     edx, edx; pftDueTime
0x140003d42  mov     rcx, rbx; pti
0x140003d45  call    cs:__imp_SetThreadpoolTimer
0x140003d4b  mov     edx, 1; fCancelPendingCallbacks
0x140003d50  mov     rcx, rbx; pti
0x140003d53  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140003d59  mov     rcx, rbx; pti
0x140003d5c  call    cs:__imp_CloseThreadpoolTimer
0x140003d62  mov     rcx, [rdi+10h]; lpMem
0x140003d66  test    rcx, rcx
0x140003d69  jz      short loc_140003D70
0x140003d6b  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140003d70  mov     rbx, [rsp+28h+arg_0]
0x140003d75  mov     rsi, [rsp+28h+arg_8]
0x140003d7a  add     rsp, 20h
0x140003d7e  pop     rdi
0x140003d7f  retn
```
