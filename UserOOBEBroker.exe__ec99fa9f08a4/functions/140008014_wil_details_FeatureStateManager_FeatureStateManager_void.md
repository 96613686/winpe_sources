# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x140008014`
- end: `0x140008202`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000e9f0`

## callees

- `0x140007d70`
- `0x140008014`
- `0x14000c13c`
- `0x14000cf8c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400080e0`
- `KERNEL32!HeapFree` at `0x140008130`
- `KERNEL32!HeapFree` at `0x140008170`
- `KERNEL32!HeapFree` at `0x1400080e0`
- `KERNEL32!HeapFree` at `0x140008130`
- `KERNEL32!HeapFree` at `0x140008170`
- `KERNEL32!SetLastError` at `0x140008064`
- `KERNEL32!SetLastError` at `0x1400080ad`
- `KERNEL32!SetLastError` at `0x140008064`
- `KERNEL32!SetLastError` at `0x1400080ad`
- `KERNEL32!GetLastError` at `0x140008032`
- `KERNEL32!GetLastError` at `0x14000807b`
- `KERNEL32!GetLastError` at `0x140008032`
- `KERNEL32!GetLastError` at `0x14000807b`
- `KERNEL32!GetProcessHeap` at `0x1400080d2`
- `KERNEL32!GetProcessHeap` at `0x140008122`
- `KERNEL32!GetProcessHeap` at `0x140008162`
- `KERNEL32!GetProcessHeap` at `0x1400080d2`
- `KERNEL32!GetProcessHeap` at `0x140008122`
- `KERNEL32!GetProcessHeap` at `0x140008162`
- `KERNEL32!SetThreadpoolTimer` at `0x140008045`
- `KERNEL32!SetThreadpoolTimer` at `0x14000808e`
- `KERNEL32!SetThreadpoolTimer` at `0x140008194`
- `KERNEL32!SetThreadpoolTimer` at `0x1400081c5`
- `KERNEL32!SetThreadpoolTimer` at `0x140008045`
- `KERNEL32!SetThreadpoolTimer` at `0x14000808e`
- `KERNEL32!SetThreadpoolTimer` at `0x140008194`
- `KERNEL32!SetThreadpoolTimer` at `0x1400081c5`
- `KERNEL32!DeleteCriticalSection` at `0x140008139`
- `KERNEL32!DeleteCriticalSection` at `0x14000817a`
- `KERNEL32!DeleteCriticalSection` at `0x140008139`
- `KERNEL32!DeleteCriticalSection` at `0x14000817a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140008053`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000809c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400081a2`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400081d3`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140008053`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000809c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400081a2`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400081d3`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000805c`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400080a5`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400081ab`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400081dc`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000805c`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400080a5`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400081ab`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400081dc`

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
  if ( v8 && qword_1400170B0 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1400170B0[25], qword_1400170B0, v8);
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
0x140008014  mov     [rsp+arg_0], rbx
0x140008019  mov     [rsp+arg_8], rsi
0x14000801e  push    rdi
0x14000801f  sub     rsp, 20h
0x140008023  mov     rdi, rcx
0x140008026  mov     byte ptr [rcx], 0
0x140008029  mov     rsi, [rcx+30h]
0x14000802d  test    rsi, rsi
0x140008030  jz      short loc_14000806A
0x140008032  call    cs:__imp_GetLastError
0x140008038  mov     ebx, eax
0x14000803a  xor     r9d, r9d; msWindowLength
0x14000803d  xor     r8d, r8d; msPeriod
0x140008040  xor     edx, edx; pftDueTime
0x140008042  mov     rcx, rsi; pti
0x140008045  call    cs:__imp_SetThreadpoolTimer
0x14000804b  mov     edx, 1; fCancelPendingCallbacks
0x140008050  mov     rcx, rsi; pti
0x140008053  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008059  mov     rcx, rsi; pti
0x14000805c  call    cs:__imp_CloseThreadpoolTimer
0x140008062  mov     ecx, ebx; dwErrCode
0x140008064  call    cs:__imp_SetLastError
0x14000806a  mov     qword ptr [rdi+30h], 0
0x140008072  mov     rsi, [rdi+38h]
0x140008076  test    rsi, rsi
0x140008079  jz      short loc_1400080B3
0x14000807b  call    cs:__imp_GetLastError
0x140008081  mov     ebx, eax
0x140008083  xor     r9d, r9d; msWindowLength
0x140008086  xor     r8d, r8d; msPeriod
0x140008089  xor     edx, edx; pftDueTime
0x14000808b  mov     rcx, rsi; pti
0x14000808e  call    cs:__imp_SetThreadpoolTimer
0x140008094  mov     edx, 1; fCancelPendingCallbacks
0x140008099  mov     rcx, rsi; pti
0x14000809c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400080a2  mov     rcx, rsi; pti
0x1400080a5  call    cs:__imp_CloseThreadpoolTimer
0x1400080ab  mov     ecx, ebx; dwErrCode
0x1400080ad  call    cs:__imp_SetLastError
0x1400080b3  mov     qword ptr [rdi+38h], 0
0x1400080bb  mov     rbx, [rdi+100h]
0x1400080c2  mov     qword ptr [rdi+100h], 0
0x1400080cd  test    rbx, rbx
0x1400080d0  jz      short loc_1400080E6
0x1400080d2  call    cs:__imp_GetProcessHeap
0x1400080d8  mov     rcx, rax; hHeap
0x1400080db  mov     r8, rbx; lpMem
0x1400080de  xor     edx, edx; dwFlags
0x1400080e0  call    cs:__imp_HeapFree
0x1400080e6  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1400080ed  test    r8, r8
0x1400080f0  jz      short loc_14000810A
0x1400080f2  mov     rdx, cs:qword_1400170B0; SRWLock
0x1400080f9  test    rdx, rdx
0x1400080fc  jz      short loc_14000810A
0x1400080fe  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140008105  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x14000810a  lea     rbx, [rdi+98h]
0x140008111  mov     rsi, [rbx+40h]
0x140008115  mov     qword ptr [rbx+40h], 0
0x14000811d  test    rsi, rsi
0x140008120  jz      short loc_140008136
0x140008122  call    cs:__imp_GetProcessHeap
0x140008128  mov     rcx, rax; hHeap
0x14000812b  mov     r8, rsi; lpMem
0x14000812e  xor     edx, edx; dwFlags
0x140008130  call    cs:__imp_HeapFree
0x140008136  mov     rcx, rbx; lpCriticalSection
0x140008139  call    cs:__imp_DeleteCriticalSection
0x14000813f  lea     rcx, [rdi+90h]
0x140008146  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14000814b  mov     rsi, [rdi+88h]
0x140008152  mov     qword ptr [rdi+88h], 0
0x14000815d  test    rsi, rsi
0x140008160  jz      short loc_140008176
0x140008162  call    cs:__imp_GetProcessHeap
0x140008168  mov     rcx, rax; hHeap
0x14000816b  mov     r8, rsi; lpMem
0x14000816e  xor     edx, edx; dwFlags
0x140008170  call    cs:__imp_HeapFree
0x140008176  lea     rcx, [rdi+48h]; lpCriticalSection
0x14000817a  call    cs:__imp_DeleteCriticalSection
0x140008180  mov     rbx, [rdi+38h]
0x140008184  test    rbx, rbx
0x140008187  jz      short loc_1400081B1
0x140008189  xor     r9d, r9d; msWindowLength
0x14000818c  xor     r8d, r8d; msPeriod
0x14000818f  xor     edx, edx; pftDueTime
0x140008191  mov     rcx, rbx; pti
0x140008194  call    cs:__imp_SetThreadpoolTimer
0x14000819a  mov     edx, 1; fCancelPendingCallbacks
0x14000819f  mov     rcx, rbx; pti
0x1400081a2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400081a8  mov     rcx, rbx; pti
0x1400081ab  call    cs:__imp_CloseThreadpoolTimer
0x1400081b1  mov     rbx, [rdi+30h]
0x1400081b5  test    rbx, rbx
0x1400081b8  jz      short loc_1400081E3
0x1400081ba  xor     r9d, r9d; msWindowLength
0x1400081bd  xor     r8d, r8d; msPeriod
0x1400081c0  xor     edx, edx; pftDueTime
0x1400081c2  mov     rcx, rbx; pti
0x1400081c5  call    cs:__imp_SetThreadpoolTimer
0x1400081cb  mov     edx, 1; fCancelPendingCallbacks
0x1400081d0  mov     rcx, rbx; pti
0x1400081d3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400081d9  mov     rcx, rbx; pti
0x1400081dc  call    cs:__imp_CloseThreadpoolTimer
0x1400081e2  nop
0x1400081e3  mov     rcx, [rdi+10h]; lpMem
0x1400081e7  test    rcx, rcx
0x1400081ea  jz      short loc_1400081F2
0x1400081ec  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1400081f1  nop
0x1400081f2  mov     rbx, [rsp+28h+arg_0]
0x1400081f7  mov     rsi, [rsp+28h+arg_8]
0x1400081fc  add     rsp, 20h
0x140008200  pop     rdi
0x140008201  retn
```
