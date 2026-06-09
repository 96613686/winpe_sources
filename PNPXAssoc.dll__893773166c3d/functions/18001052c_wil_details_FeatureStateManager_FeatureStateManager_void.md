# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18001052c`
- end: `0x180010718`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180013320`

## callees

- `0x1800103e8`
- `0x18001052c`
- `0x180012054`
- `0x180012574`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800105f8`
- `KERNEL32!HeapFree` at `0x180010648`
- `KERNEL32!HeapFree` at `0x180010688`
- `KERNEL32!HeapFree` at `0x1800105f8`
- `KERNEL32!HeapFree` at `0x180010648`
- `KERNEL32!HeapFree` at `0x180010688`
- `KERNEL32!SetLastError` at `0x18001057c`
- `KERNEL32!SetLastError` at `0x1800105c5`
- `KERNEL32!SetLastError` at `0x18001057c`
- `KERNEL32!SetLastError` at `0x1800105c5`
- `KERNEL32!GetLastError` at `0x18001054a`
- `KERNEL32!GetLastError` at `0x180010593`
- `KERNEL32!GetLastError` at `0x18001054a`
- `KERNEL32!GetLastError` at `0x180010593`
- `KERNEL32!GetProcessHeap` at `0x1800105ea`
- `KERNEL32!GetProcessHeap` at `0x18001063a`
- `KERNEL32!GetProcessHeap` at `0x18001067a`
- `KERNEL32!GetProcessHeap` at `0x1800105ea`
- `KERNEL32!GetProcessHeap` at `0x18001063a`
- `KERNEL32!GetProcessHeap` at `0x18001067a`
- `KERNEL32!CloseThreadpoolTimer` at `0x180010574`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800105bd`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800106c3`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800106f4`
- `KERNEL32!CloseThreadpoolTimer` at `0x180010574`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800105bd`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800106c3`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800106f4`
- `KERNEL32!DeleteCriticalSection` at `0x180010651`
- `KERNEL32!DeleteCriticalSection` at `0x180010692`
- `KERNEL32!DeleteCriticalSection` at `0x180010651`
- `KERNEL32!DeleteCriticalSection` at `0x180010692`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18001056b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800105b4`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800106ba`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800106eb`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18001056b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800105b4`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800106ba`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800106eb`
- `KERNEL32!SetThreadpoolTimer` at `0x18001055d`
- `KERNEL32!SetThreadpoolTimer` at `0x1800105a6`
- `KERNEL32!SetThreadpoolTimer` at `0x1800106ac`
- `KERNEL32!SetThreadpoolTimer` at `0x1800106dd`
- `KERNEL32!SetThreadpoolTimer` at `0x18001055d`
- `KERNEL32!SetThreadpoolTimer` at `0x1800105a6`
- `KERNEL32!SetThreadpoolTimer` at `0x1800106ac`
- `KERNEL32!SetThreadpoolTimer` at `0x1800106dd`

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
  if ( v8 && qword_18001A250 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18001A250[25], qword_18001A250, v8);
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
0x18001052c  mov     [rsp+arg_0], rbx
0x180010531  mov     [rsp+arg_8], rsi
0x180010536  push    rdi
0x180010537  sub     rsp, 20h
0x18001053b  mov     byte ptr [rcx], 0
0x18001053e  mov     rdi, rcx
0x180010541  mov     rsi, [rcx+30h]
0x180010545  test    rsi, rsi
0x180010548  jz      short loc_180010582
0x18001054a  call    cs:__imp_GetLastError
0x180010550  xor     r9d, r9d; msWindowLength
0x180010553  xor     r8d, r8d; msPeriod
0x180010556  xor     edx, edx; pftDueTime
0x180010558  mov     rcx, rsi; pti
0x18001055b  mov     ebx, eax
0x18001055d  call    cs:__imp_SetThreadpoolTimer
0x180010563  mov     edx, 1; fCancelPendingCallbacks
0x180010568  mov     rcx, rsi; pti
0x18001056b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010571  mov     rcx, rsi; pti
0x180010574  call    cs:__imp_CloseThreadpoolTimer
0x18001057a  mov     ecx, ebx; dwErrCode
0x18001057c  call    cs:__imp_SetLastError
0x180010582  mov     qword ptr [rdi+30h], 0
0x18001058a  mov     rsi, [rdi+38h]
0x18001058e  test    rsi, rsi
0x180010591  jz      short loc_1800105CB
0x180010593  call    cs:__imp_GetLastError
0x180010599  xor     r9d, r9d; msWindowLength
0x18001059c  xor     r8d, r8d; msPeriod
0x18001059f  xor     edx, edx; pftDueTime
0x1800105a1  mov     rcx, rsi; pti
0x1800105a4  mov     ebx, eax
0x1800105a6  call    cs:__imp_SetThreadpoolTimer
0x1800105ac  mov     edx, 1; fCancelPendingCallbacks
0x1800105b1  mov     rcx, rsi; pti
0x1800105b4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800105ba  mov     rcx, rsi; pti
0x1800105bd  call    cs:__imp_CloseThreadpoolTimer
0x1800105c3  mov     ecx, ebx; dwErrCode
0x1800105c5  call    cs:__imp_SetLastError
0x1800105cb  mov     qword ptr [rdi+38h], 0
0x1800105d3  mov     rbx, [rdi+100h]
0x1800105da  mov     qword ptr [rdi+100h], 0
0x1800105e5  test    rbx, rbx
0x1800105e8  jz      short loc_1800105FE
0x1800105ea  call    cs:__imp_GetProcessHeap
0x1800105f0  mov     r8, rbx; lpMem
0x1800105f3  xor     edx, edx; dwFlags
0x1800105f5  mov     rcx, rax; hHeap
0x1800105f8  call    cs:__imp_HeapFree
0x1800105fe  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180010605  test    r8, r8
0x180010608  jz      short loc_180010622
0x18001060a  mov     rdx, cs:qword_18001A250; SRWLock
0x180010611  test    rdx, rdx
0x180010614  jz      short loc_180010622
0x180010616  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18001061d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180010622  lea     rbx, [rdi+98h]
0x180010629  mov     rsi, [rbx+40h]
0x18001062d  mov     qword ptr [rbx+40h], 0
0x180010635  test    rsi, rsi
0x180010638  jz      short loc_18001064E
0x18001063a  call    cs:__imp_GetProcessHeap
0x180010640  mov     r8, rsi; lpMem
0x180010643  xor     edx, edx; dwFlags
0x180010645  mov     rcx, rax; hHeap
0x180010648  call    cs:__imp_HeapFree
0x18001064e  mov     rcx, rbx; lpCriticalSection
0x180010651  call    cs:__imp_DeleteCriticalSection
0x180010657  lea     rcx, [rdi+90h]
0x18001065e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180010663  mov     rsi, [rdi+88h]
0x18001066a  mov     qword ptr [rdi+88h], 0
0x180010675  test    rsi, rsi
0x180010678  jz      short loc_18001068E
0x18001067a  call    cs:__imp_GetProcessHeap
0x180010680  mov     r8, rsi; lpMem
0x180010683  xor     edx, edx; dwFlags
0x180010685  mov     rcx, rax; hHeap
0x180010688  call    cs:__imp_HeapFree
0x18001068e  lea     rcx, [rdi+48h]; lpCriticalSection
0x180010692  call    cs:__imp_DeleteCriticalSection
0x180010698  mov     rbx, [rdi+38h]
0x18001069c  test    rbx, rbx
0x18001069f  jz      short loc_1800106C9
0x1800106a1  xor     r9d, r9d; msWindowLength
0x1800106a4  xor     r8d, r8d; msPeriod
0x1800106a7  xor     edx, edx; pftDueTime
0x1800106a9  mov     rcx, rbx; pti
0x1800106ac  call    cs:__imp_SetThreadpoolTimer
0x1800106b2  mov     edx, 1; fCancelPendingCallbacks
0x1800106b7  mov     rcx, rbx; pti
0x1800106ba  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800106c0  mov     rcx, rbx; pti
0x1800106c3  call    cs:__imp_CloseThreadpoolTimer
0x1800106c9  mov     rbx, [rdi+30h]
0x1800106cd  test    rbx, rbx
0x1800106d0  jz      short loc_1800106FA
0x1800106d2  xor     r9d, r9d; msWindowLength
0x1800106d5  xor     r8d, r8d; msPeriod
0x1800106d8  xor     edx, edx; pftDueTime
0x1800106da  mov     rcx, rbx; pti
0x1800106dd  call    cs:__imp_SetThreadpoolTimer
0x1800106e3  mov     edx, 1; fCancelPendingCallbacks
0x1800106e8  mov     rcx, rbx; pti
0x1800106eb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800106f1  mov     rcx, rbx; pti
0x1800106f4  call    cs:__imp_CloseThreadpoolTimer
0x1800106fa  mov     rcx, [rdi+10h]; lpMem
0x1800106fe  test    rcx, rcx
0x180010701  jz      short loc_180010708
0x180010703  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180010708  mov     rbx, [rsp+28h+arg_0]
0x18001070d  mov     rsi, [rsp+28h+arg_8]
0x180010712  add     rsp, 20h
0x180010716  pop     rdi
0x180010717  retn
```
