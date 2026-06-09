# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180002f20`
- end: `0x1800030e2`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `450`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180009aa0`

## callees

- `0x180002f20`
- `0x180006658`
- `0x180007394`
- `0x180007408`
- `0x18000897c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180002f5f`
- `KERNEL32!GetProcessHeap` at `0x180002fbb`
- `KERNEL32!GetProcessHeap` at `0x180003012`
- `KERNEL32!GetProcessHeap` at `0x180002f5f`
- `KERNEL32!GetProcessHeap` at `0x180002fbb`
- `KERNEL32!GetProcessHeap` at `0x180003012`
- `KERNEL32!HeapFree` at `0x180002f73`
- `KERNEL32!HeapFree` at `0x180002fcf`
- `KERNEL32!HeapFree` at `0x180003026`
- `KERNEL32!HeapFree` at `0x180002f73`
- `KERNEL32!HeapFree` at `0x180002fcf`
- `KERNEL32!HeapFree` at `0x180003026`
- `KERNEL32!SetThreadpoolTimer` at `0x18000305b`
- `KERNEL32!SetThreadpoolTimer` at `0x18000309b`
- `KERNEL32!SetThreadpoolTimer` at `0x18000305b`
- `KERNEL32!SetThreadpoolTimer` at `0x18000309b`
- `KERNEL32!DeleteCriticalSection` at `0x180002fde`
- `KERNEL32!DeleteCriticalSection` at `0x180003036`
- `KERNEL32!DeleteCriticalSection` at `0x180002fde`
- `KERNEL32!DeleteCriticalSection` at `0x180003036`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000306c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800030ac`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000306c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800030ac`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000307b`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800030bb`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000307b`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800030bb`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(wil::details::FeatureStateManager *this)
{
  void *v2; // rdi
  HANDLE ProcessHeap; // rax
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v4; // r8
  void *v5; // rsi
  HANDLE v6; // rax
  void *v7; // rdx
  wil::details *v8; // rcx
  void *v9; // rsi
  HANDLE v10; // rax
  struct _TP_TIMER *v11; // rdi
  struct _TP_TIMER *v12; // rdi
  void *v13; // rcx

  *(_BYTE *)this = 0;
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (char *)this + 48,
    0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (char *)this + 56,
    0);
  v2 = (void *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  v4 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)*((_QWORD *)this + 28);
  if ( v4 && SRWLock )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&SRWLock[25], SRWLock, v4);
  v5 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v5 )
  {
    v6 = GetProcessHeap();
    HeapFree(v6, 0, v5);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  v8 = (wil::details *)*((_QWORD *)this + 18);
  if ( v8 )
    wil::details::UnregisterWilFeatureConfigurationChange(v8, v7);
  v9 = (void *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v9 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v9);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v11 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v11 )
  {
    SetThreadpoolTimer(v11, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v11, 1);
    CloseThreadpoolTimer(v11);
  }
  v12 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v12 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 6), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v12, 1);
    CloseThreadpoolTimer(v12);
  }
  v13 = (void *)*((_QWORD *)this + 2);
  if ( v13 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v13);
}

```

## disassembly

```asm
0x180002f20  push    rbx
0x180002f22  push    rsi
0x180002f23  push    rdi
0x180002f24  push    r14
0x180002f26  push    r15
0x180002f28  sub     rsp, 20h
0x180002f2c  mov     rbx, rcx
0x180002f2f  mov     byte ptr [rcx], 0
0x180002f32  add     rcx, 30h ; '0'
0x180002f36  xor     edx, edx
0x180002f38  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180002f3d  xor     edx, edx
0x180002f3f  lea     rcx, [rbx+38h]
0x180002f43  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180002f48  mov     rdi, [rbx+100h]
0x180002f4f  mov     qword ptr [rbx+100h], 0
0x180002f5a  test    rdi, rdi
0x180002f5d  jz      short loc_180002F7F
0x180002f5f  call    cs:__imp_GetProcessHeap
0x180002f66  nop     dword ptr [rax+rax+00h]
0x180002f6b  mov     r8, rdi; lpMem
0x180002f6e  xor     edx, edx; dwFlags
0x180002f70  mov     rcx, rax; hHeap
0x180002f73  call    cs:__imp_HeapFree
0x180002f7a  nop     dword ptr [rax+rax+00h]
0x180002f7f  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180002f86  test    r8, r8
0x180002f89  jz      short loc_180002FA3
0x180002f8b  mov     rdx, cs:SRWLock; SRWLock
0x180002f92  test    rdx, rdx
0x180002f95  jz      short loc_180002FA3
0x180002f97  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180002f9e  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180002fa3  lea     rdi, [rbx+98h]
0x180002faa  mov     rsi, [rdi+40h]
0x180002fae  mov     qword ptr [rdi+40h], 0
0x180002fb6  test    rsi, rsi
0x180002fb9  jz      short loc_180002FDB
0x180002fbb  call    cs:__imp_GetProcessHeap
0x180002fc2  nop     dword ptr [rax+rax+00h]
0x180002fc7  mov     r8, rsi; lpMem
0x180002fca  xor     edx, edx; dwFlags
0x180002fcc  mov     rcx, rax; hHeap
0x180002fcf  call    cs:__imp_HeapFree
0x180002fd6  nop     dword ptr [rax+rax+00h]
0x180002fdb  mov     rcx, rdi; lpCriticalSection
0x180002fde  call    cs:__imp_DeleteCriticalSection
0x180002fe5  nop     dword ptr [rax+rax+00h]
0x180002fea  mov     rcx, [rbx+90h]; this
0x180002ff1  test    rcx, rcx
0x180002ff4  jz      short loc_180002FFB
0x180002ff6  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x180002ffb  mov     rsi, [rbx+88h]
0x180003002  mov     qword ptr [rbx+88h], 0
0x18000300d  test    rsi, rsi
0x180003010  jz      short loc_180003032
0x180003012  call    cs:__imp_GetProcessHeap
0x180003019  nop     dword ptr [rax+rax+00h]
0x18000301e  mov     r8, rsi; lpMem
0x180003021  xor     edx, edx; dwFlags
0x180003023  mov     rcx, rax; hHeap
0x180003026  call    cs:__imp_HeapFree
0x18000302d  nop     dword ptr [rax+rax+00h]
0x180003032  lea     rcx, [rbx+48h]; lpCriticalSection
0x180003036  call    cs:__imp_DeleteCriticalSection
0x18000303d  nop     dword ptr [rax+rax+00h]
0x180003042  mov     rdi, [rbx+38h]
0x180003046  mov     esi, 1
0x18000304b  test    rdi, rdi
0x18000304e  jz      short loc_180003087
0x180003050  xor     r9d, r9d; msWindowLength
0x180003053  xor     r8d, r8d; msPeriod
0x180003056  xor     edx, edx; pftDueTime
0x180003058  mov     rcx, rdi; pti
0x18000305b  call    cs:__imp_SetThreadpoolTimer
0x180003062  nop     dword ptr [rax+rax+00h]
0x180003067  mov     edx, esi; fCancelPendingCallbacks
0x180003069  mov     rcx, rdi; pti
0x18000306c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003073  nop     dword ptr [rax+rax+00h]
0x180003078  mov     rcx, rdi; pti
0x18000307b  call    cs:__imp_CloseThreadpoolTimer
0x180003082  nop     dword ptr [rax+rax+00h]
0x180003087  mov     rdi, [rbx+30h]
0x18000308b  test    rdi, rdi
0x18000308e  jz      short loc_1800030C7
0x180003090  xor     r9d, r9d; msWindowLength
0x180003093  xor     r8d, r8d; msPeriod
0x180003096  xor     edx, edx; pftDueTime
0x180003098  mov     rcx, rdi; pti
0x18000309b  call    cs:__imp_SetThreadpoolTimer
0x1800030a2  nop     dword ptr [rax+rax+00h]
0x1800030a7  mov     edx, esi; fCancelPendingCallbacks
0x1800030a9  mov     rcx, rdi; pti
0x1800030ac  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800030b3  nop     dword ptr [rax+rax+00h]
0x1800030b8  mov     rcx, rdi; pti
0x1800030bb  call    cs:__imp_CloseThreadpoolTimer
0x1800030c2  nop     dword ptr [rax+rax+00h]
0x1800030c7  mov     rcx, [rbx+10h]; lpMem
0x1800030cb  test    rcx, rcx
0x1800030ce  jz      short loc_1800030D5
0x1800030d0  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800030d5  add     rsp, 20h
0x1800030d9  pop     r15
0x1800030db  pop     r14
0x1800030dd  pop     rdi
0x1800030de  pop     rsi
0x1800030df  pop     rbx
0x1800030e0  retn
```
