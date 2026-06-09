# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180005c04`
- end: `0x180005df2`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800149e0`

## callees

- `0x1800058c0`
- `0x180005c04`
- `0x18000da94`
- `0x180010d68`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180005d29`
- `KERNEL32!DeleteCriticalSection` at `0x180005d6a`
- `KERNEL32!DeleteCriticalSection` at `0x180005d29`
- `KERNEL32!DeleteCriticalSection` at `0x180005d6a`
- `KERNEL32!GetLastError` at `0x180005c22`
- `KERNEL32!GetLastError` at `0x180005c6b`
- `KERNEL32!GetLastError` at `0x180005c22`
- `KERNEL32!GetLastError` at `0x180005c6b`
- `KERNEL32!GetProcessHeap` at `0x180005cc2`
- `KERNEL32!GetProcessHeap` at `0x180005d12`
- `KERNEL32!GetProcessHeap` at `0x180005d52`
- `KERNEL32!GetProcessHeap` at `0x180005cc2`
- `KERNEL32!GetProcessHeap` at `0x180005d12`
- `KERNEL32!GetProcessHeap` at `0x180005d52`
- `KERNEL32!SetThreadpoolTimer` at `0x180005c35`
- `KERNEL32!SetThreadpoolTimer` at `0x180005c7e`
- `KERNEL32!SetThreadpoolTimer` at `0x180005d84`
- `KERNEL32!SetThreadpoolTimer` at `0x180005db5`
- `KERNEL32!SetThreadpoolTimer` at `0x180005c35`
- `KERNEL32!SetThreadpoolTimer` at `0x180005c7e`
- `KERNEL32!SetThreadpoolTimer` at `0x180005d84`
- `KERNEL32!SetThreadpoolTimer` at `0x180005db5`
- `KERNEL32!CloseThreadpoolTimer` at `0x180005c4c`
- `KERNEL32!CloseThreadpoolTimer` at `0x180005c95`
- `KERNEL32!CloseThreadpoolTimer` at `0x180005d9b`
- `KERNEL32!CloseThreadpoolTimer` at `0x180005dcc`
- `KERNEL32!CloseThreadpoolTimer` at `0x180005c4c`
- `KERNEL32!CloseThreadpoolTimer` at `0x180005c95`
- `KERNEL32!CloseThreadpoolTimer` at `0x180005d9b`
- `KERNEL32!CloseThreadpoolTimer` at `0x180005dcc`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180005c43`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180005c8c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180005d92`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180005dc3`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180005c43`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180005c8c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180005d92`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180005dc3`
- `KERNEL32!HeapFree` at `0x180005cd0`
- `KERNEL32!HeapFree` at `0x180005d20`
- `KERNEL32!HeapFree` at `0x180005d60`
- `KERNEL32!HeapFree` at `0x180005cd0`
- `KERNEL32!HeapFree` at `0x180005d20`
- `KERNEL32!HeapFree` at `0x180005d60`
- `KERNEL32!SetLastError` at `0x180005c54`
- `KERNEL32!SetLastError` at `0x180005c9d`
- `KERNEL32!SetLastError` at `0x180005c54`
- `KERNEL32!SetLastError` at `0x180005c9d`

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
  if ( v8 && qword_180023110 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180023110[25], qword_180023110, v8);
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
0x180005c04  mov     [rsp+arg_0], rbx
0x180005c09  mov     [rsp+arg_8], rsi
0x180005c0e  push    rdi
0x180005c0f  sub     rsp, 20h
0x180005c13  mov     rdi, rcx
0x180005c16  mov     byte ptr [rcx], 0
0x180005c19  mov     rsi, [rcx+30h]
0x180005c1d  test    rsi, rsi
0x180005c20  jz      short loc_180005C5A
0x180005c22  call    cs:__imp_GetLastError
0x180005c28  mov     ebx, eax
0x180005c2a  xor     r9d, r9d; msWindowLength
0x180005c2d  xor     r8d, r8d; msPeriod
0x180005c30  xor     edx, edx; pftDueTime
0x180005c32  mov     rcx, rsi; pti
0x180005c35  call    cs:__imp_SetThreadpoolTimer
0x180005c3b  mov     edx, 1; fCancelPendingCallbacks
0x180005c40  mov     rcx, rsi; pti
0x180005c43  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005c49  mov     rcx, rsi; pti
0x180005c4c  call    cs:__imp_CloseThreadpoolTimer
0x180005c52  mov     ecx, ebx; dwErrCode
0x180005c54  call    cs:__imp_SetLastError
0x180005c5a  mov     qword ptr [rdi+30h], 0
0x180005c62  mov     rsi, [rdi+38h]
0x180005c66  test    rsi, rsi
0x180005c69  jz      short loc_180005CA3
0x180005c6b  call    cs:__imp_GetLastError
0x180005c71  mov     ebx, eax
0x180005c73  xor     r9d, r9d; msWindowLength
0x180005c76  xor     r8d, r8d; msPeriod
0x180005c79  xor     edx, edx; pftDueTime
0x180005c7b  mov     rcx, rsi; pti
0x180005c7e  call    cs:__imp_SetThreadpoolTimer
0x180005c84  mov     edx, 1; fCancelPendingCallbacks
0x180005c89  mov     rcx, rsi; pti
0x180005c8c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005c92  mov     rcx, rsi; pti
0x180005c95  call    cs:__imp_CloseThreadpoolTimer
0x180005c9b  mov     ecx, ebx; dwErrCode
0x180005c9d  call    cs:__imp_SetLastError
0x180005ca3  mov     qword ptr [rdi+38h], 0
0x180005cab  mov     rbx, [rdi+100h]
0x180005cb2  mov     qword ptr [rdi+100h], 0
0x180005cbd  test    rbx, rbx
0x180005cc0  jz      short loc_180005CD6
0x180005cc2  call    cs:__imp_GetProcessHeap
0x180005cc8  mov     rcx, rax; hHeap
0x180005ccb  mov     r8, rbx; lpMem
0x180005cce  xor     edx, edx; dwFlags
0x180005cd0  call    cs:__imp_HeapFree
0x180005cd6  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180005cdd  test    r8, r8
0x180005ce0  jz      short loc_180005CFA
0x180005ce2  mov     rdx, cs:qword_180023110; SRWLock
0x180005ce9  test    rdx, rdx
0x180005cec  jz      short loc_180005CFA
0x180005cee  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180005cf5  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180005cfa  lea     rbx, [rdi+98h]
0x180005d01  mov     rsi, [rbx+40h]
0x180005d05  mov     qword ptr [rbx+40h], 0
0x180005d0d  test    rsi, rsi
0x180005d10  jz      short loc_180005D26
0x180005d12  call    cs:__imp_GetProcessHeap
0x180005d18  mov     rcx, rax; hHeap
0x180005d1b  mov     r8, rsi; lpMem
0x180005d1e  xor     edx, edx; dwFlags
0x180005d20  call    cs:__imp_HeapFree
0x180005d26  mov     rcx, rbx; lpCriticalSection
0x180005d29  call    cs:__imp_DeleteCriticalSection
0x180005d2f  lea     rcx, [rdi+90h]
0x180005d36  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180005d3b  mov     rsi, [rdi+88h]
0x180005d42  mov     qword ptr [rdi+88h], 0
0x180005d4d  test    rsi, rsi
0x180005d50  jz      short loc_180005D66
0x180005d52  call    cs:__imp_GetProcessHeap
0x180005d58  mov     rcx, rax; hHeap
0x180005d5b  mov     r8, rsi; lpMem
0x180005d5e  xor     edx, edx; dwFlags
0x180005d60  call    cs:__imp_HeapFree
0x180005d66  lea     rcx, [rdi+48h]; lpCriticalSection
0x180005d6a  call    cs:__imp_DeleteCriticalSection
0x180005d70  mov     rbx, [rdi+38h]
0x180005d74  test    rbx, rbx
0x180005d77  jz      short loc_180005DA1
0x180005d79  xor     r9d, r9d; msWindowLength
0x180005d7c  xor     r8d, r8d; msPeriod
0x180005d7f  xor     edx, edx; pftDueTime
0x180005d81  mov     rcx, rbx; pti
0x180005d84  call    cs:__imp_SetThreadpoolTimer
0x180005d8a  mov     edx, 1; fCancelPendingCallbacks
0x180005d8f  mov     rcx, rbx; pti
0x180005d92  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005d98  mov     rcx, rbx; pti
0x180005d9b  call    cs:__imp_CloseThreadpoolTimer
0x180005da1  mov     rbx, [rdi+30h]
0x180005da5  test    rbx, rbx
0x180005da8  jz      short loc_180005DD3
0x180005daa  xor     r9d, r9d; msWindowLength
0x180005dad  xor     r8d, r8d; msPeriod
0x180005db0  xor     edx, edx; pftDueTime
0x180005db2  mov     rcx, rbx; pti
0x180005db5  call    cs:__imp_SetThreadpoolTimer
0x180005dbb  mov     edx, 1; fCancelPendingCallbacks
0x180005dc0  mov     rcx, rbx; pti
0x180005dc3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005dc9  mov     rcx, rbx; pti
0x180005dcc  call    cs:__imp_CloseThreadpoolTimer
0x180005dd2  nop
0x180005dd3  mov     rcx, [rdi+10h]; lpMem
0x180005dd7  test    rcx, rcx
0x180005dda  jz      short loc_180005DE2
0x180005ddc  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180005de1  nop
0x180005de2  mov     rbx, [rsp+28h+arg_0]
0x180005de7  mov     rsi, [rsp+28h+arg_8]
0x180005dec  add     rsp, 20h
0x180005df0  pop     rdi
0x180005df1  retn
```
