# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x14005ef9c`
- end: `0x14005f18a`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140069870`

## callees

- `0x14005ee48`
- `0x14005ef9c`
- `0x140062534`
- `0x140062e78`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x14005f05a`
- `KERNEL32!GetProcessHeap` at `0x14005f0aa`
- `KERNEL32!GetProcessHeap` at `0x14005f0ea`
- `KERNEL32!GetProcessHeap` at `0x14005f05a`
- `KERNEL32!GetProcessHeap` at `0x14005f0aa`
- `KERNEL32!GetProcessHeap` at `0x14005f0ea`
- `KERNEL32!DeleteCriticalSection` at `0x14005f0c1`
- `KERNEL32!DeleteCriticalSection` at `0x14005f102`
- `KERNEL32!DeleteCriticalSection` at `0x14005f0c1`
- `KERNEL32!DeleteCriticalSection` at `0x14005f102`
- `KERNEL32!SetThreadpoolTimer` at `0x14005efcd`
- `KERNEL32!SetThreadpoolTimer` at `0x14005f016`
- `KERNEL32!SetThreadpoolTimer` at `0x14005f11c`
- `KERNEL32!SetThreadpoolTimer` at `0x14005f14d`
- `KERNEL32!SetThreadpoolTimer` at `0x14005efcd`
- `KERNEL32!SetThreadpoolTimer` at `0x14005f016`
- `KERNEL32!SetThreadpoolTimer` at `0x14005f11c`
- `KERNEL32!SetThreadpoolTimer` at `0x14005f14d`
- `KERNEL32!CloseThreadpoolTimer` at `0x14005efe4`
- `KERNEL32!CloseThreadpoolTimer` at `0x14005f02d`
- `KERNEL32!CloseThreadpoolTimer` at `0x14005f133`
- `KERNEL32!CloseThreadpoolTimer` at `0x14005f164`
- `KERNEL32!CloseThreadpoolTimer` at `0x14005efe4`
- `KERNEL32!CloseThreadpoolTimer` at `0x14005f02d`
- `KERNEL32!CloseThreadpoolTimer` at `0x14005f133`
- `KERNEL32!CloseThreadpoolTimer` at `0x14005f164`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14005efdb`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14005f024`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14005f12a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14005f15b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14005efdb`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14005f024`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14005f12a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14005f15b`
- `KERNEL32!GetLastError` at `0x14005efba`
- `KERNEL32!GetLastError` at `0x14005f003`
- `KERNEL32!GetLastError` at `0x14005efba`
- `KERNEL32!GetLastError` at `0x14005f003`
- `KERNEL32!SetLastError` at `0x14005efec`
- `KERNEL32!SetLastError` at `0x14005f035`
- `KERNEL32!SetLastError` at `0x14005efec`
- `KERNEL32!SetLastError` at `0x14005f035`
- `KERNEL32!HeapFree` at `0x14005f068`
- `KERNEL32!HeapFree` at `0x14005f0b8`
- `KERNEL32!HeapFree` at `0x14005f0f8`
- `KERNEL32!HeapFree` at `0x14005f068`
- `KERNEL32!HeapFree` at `0x14005f0b8`
- `KERNEL32!HeapFree` at `0x14005f0f8`

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
  if ( v8 && qword_1400AA430 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1400AA430[25], qword_1400AA430, v8);
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
0x14005ef9c  mov     [rsp+arg_0], rbx
0x14005efa1  mov     [rsp+arg_8], rsi
0x14005efa6  push    rdi
0x14005efa7  sub     rsp, 20h
0x14005efab  mov     rdi, rcx
0x14005efae  mov     byte ptr [rcx], 0
0x14005efb1  mov     rsi, [rcx+30h]
0x14005efb5  test    rsi, rsi
0x14005efb8  jz      short loc_14005EFF2
0x14005efba  call    cs:__imp_GetLastError
0x14005efc0  mov     ebx, eax
0x14005efc2  xor     r9d, r9d; msWindowLength
0x14005efc5  xor     r8d, r8d; msPeriod
0x14005efc8  xor     edx, edx; pftDueTime
0x14005efca  mov     rcx, rsi; pti
0x14005efcd  call    cs:__imp_SetThreadpoolTimer
0x14005efd3  mov     edx, 1; fCancelPendingCallbacks
0x14005efd8  mov     rcx, rsi; pti
0x14005efdb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14005efe1  mov     rcx, rsi; pti
0x14005efe4  call    cs:__imp_CloseThreadpoolTimer
0x14005efea  mov     ecx, ebx; dwErrCode
0x14005efec  call    cs:__imp_SetLastError
0x14005eff2  mov     qword ptr [rdi+30h], 0
0x14005effa  mov     rsi, [rdi+38h]
0x14005effe  test    rsi, rsi
0x14005f001  jz      short loc_14005F03B
0x14005f003  call    cs:__imp_GetLastError
0x14005f009  mov     ebx, eax
0x14005f00b  xor     r9d, r9d; msWindowLength
0x14005f00e  xor     r8d, r8d; msPeriod
0x14005f011  xor     edx, edx; pftDueTime
0x14005f013  mov     rcx, rsi; pti
0x14005f016  call    cs:__imp_SetThreadpoolTimer
0x14005f01c  mov     edx, 1; fCancelPendingCallbacks
0x14005f021  mov     rcx, rsi; pti
0x14005f024  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14005f02a  mov     rcx, rsi; pti
0x14005f02d  call    cs:__imp_CloseThreadpoolTimer
0x14005f033  mov     ecx, ebx; dwErrCode
0x14005f035  call    cs:__imp_SetLastError
0x14005f03b  mov     qword ptr [rdi+38h], 0
0x14005f043  mov     rbx, [rdi+100h]
0x14005f04a  mov     qword ptr [rdi+100h], 0
0x14005f055  test    rbx, rbx
0x14005f058  jz      short loc_14005F06E
0x14005f05a  call    cs:__imp_GetProcessHeap
0x14005f060  mov     rcx, rax; hHeap
0x14005f063  mov     r8, rbx; lpMem
0x14005f066  xor     edx, edx; dwFlags
0x14005f068  call    cs:__imp_HeapFree
0x14005f06e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x14005f075  test    r8, r8
0x14005f078  jz      short loc_14005F092
0x14005f07a  mov     rdx, cs:qword_1400AA430; SRWLock
0x14005f081  test    rdx, rdx
0x14005f084  jz      short loc_14005F092
0x14005f086  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14005f08d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x14005f092  lea     rbx, [rdi+98h]
0x14005f099  mov     rsi, [rbx+40h]
0x14005f09d  mov     qword ptr [rbx+40h], 0
0x14005f0a5  test    rsi, rsi
0x14005f0a8  jz      short loc_14005F0BE
0x14005f0aa  call    cs:__imp_GetProcessHeap
0x14005f0b0  mov     rcx, rax; hHeap
0x14005f0b3  mov     r8, rsi; lpMem
0x14005f0b6  xor     edx, edx; dwFlags
0x14005f0b8  call    cs:__imp_HeapFree
0x14005f0be  mov     rcx, rbx; lpCriticalSection
0x14005f0c1  call    cs:__imp_DeleteCriticalSection
0x14005f0c7  lea     rcx, [rdi+90h]
0x14005f0ce  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14005f0d3  mov     rsi, [rdi+88h]
0x14005f0da  mov     qword ptr [rdi+88h], 0
0x14005f0e5  test    rsi, rsi
0x14005f0e8  jz      short loc_14005F0FE
0x14005f0ea  call    cs:__imp_GetProcessHeap
0x14005f0f0  mov     rcx, rax; hHeap
0x14005f0f3  mov     r8, rsi; lpMem
0x14005f0f6  xor     edx, edx; dwFlags
0x14005f0f8  call    cs:__imp_HeapFree
0x14005f0fe  lea     rcx, [rdi+48h]; lpCriticalSection
0x14005f102  call    cs:__imp_DeleteCriticalSection
0x14005f108  mov     rbx, [rdi+38h]
0x14005f10c  test    rbx, rbx
0x14005f10f  jz      short loc_14005F139
0x14005f111  xor     r9d, r9d; msWindowLength
0x14005f114  xor     r8d, r8d; msPeriod
0x14005f117  xor     edx, edx; pftDueTime
0x14005f119  mov     rcx, rbx; pti
0x14005f11c  call    cs:__imp_SetThreadpoolTimer
0x14005f122  mov     edx, 1; fCancelPendingCallbacks
0x14005f127  mov     rcx, rbx; pti
0x14005f12a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14005f130  mov     rcx, rbx; pti
0x14005f133  call    cs:__imp_CloseThreadpoolTimer
0x14005f139  mov     rbx, [rdi+30h]
0x14005f13d  test    rbx, rbx
0x14005f140  jz      short loc_14005F16B
0x14005f142  xor     r9d, r9d; msWindowLength
0x14005f145  xor     r8d, r8d; msPeriod
0x14005f148  xor     edx, edx; pftDueTime
0x14005f14a  mov     rcx, rbx; pti
0x14005f14d  call    cs:__imp_SetThreadpoolTimer
0x14005f153  mov     edx, 1; fCancelPendingCallbacks
0x14005f158  mov     rcx, rbx; pti
0x14005f15b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14005f161  mov     rcx, rbx; pti
0x14005f164  call    cs:__imp_CloseThreadpoolTimer
0x14005f16a  nop
0x14005f16b  mov     rcx, [rdi+10h]; lpMem
0x14005f16f  test    rcx, rcx
0x14005f172  jz      short loc_14005F17A
0x14005f174  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x14005f179  nop
0x14005f17a  mov     rbx, [rsp+28h+arg_0]
0x14005f17f  mov     rsi, [rsp+28h+arg_8]
0x14005f184  add     rsp, 20h
0x14005f188  pop     rdi
0x14005f189  retn
```
