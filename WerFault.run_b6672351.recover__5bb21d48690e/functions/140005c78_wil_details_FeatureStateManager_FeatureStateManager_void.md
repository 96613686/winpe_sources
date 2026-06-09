# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x140005c78`
- end: `0x140005e3c`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `452`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400605a0`

## callees

- `0x140005c78`
- `0x14000a2e4`
- `0x14000bda4`
- `0x14000be18`
- `0x14000cec8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005d36`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005d8e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005d36`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005d8e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005ccb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005d27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005d7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005ccb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005d27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005d7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005cb7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005d13`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005d6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005cb7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005d13`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005d6a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005dd3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005e13`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005dd3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005e13`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005dc4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005e04`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005dc4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005e04`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005db3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005df3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005db3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005df3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  if ( v4 && qword_14007E608 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_14007E608[25], qword_14007E608, v4);
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
0x140005c78  push    rbx
0x140005c7a  push    rsi
0x140005c7b  push    rdi
0x140005c7c  push    r14
0x140005c7e  push    r15
0x140005c80  sub     rsp, 20h
0x140005c84  mov     rbx, rcx
0x140005c87  mov     byte ptr [rcx], 0
0x140005c8a  xor     edx, edx
0x140005c8c  add     rcx, 30h ; '0'
0x140005c90  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140005c95  xor     edx, edx
0x140005c97  lea     rcx, [rbx+38h]
0x140005c9b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140005ca0  mov     rdi, [rbx+100h]
0x140005ca7  mov     qword ptr [rbx+100h], 0
0x140005cb2  test    rdi, rdi
0x140005cb5  jz      short loc_140005CD7
0x140005cb7  call    cs:__imp_GetProcessHeap
0x140005cbe  nop     dword ptr [rax+rax+00h]
0x140005cc3  mov     rcx, rax; hHeap
0x140005cc6  mov     r8, rdi; lpMem
0x140005cc9  xor     edx, edx; dwFlags
0x140005ccb  call    cs:__imp_HeapFree
0x140005cd2  nop     dword ptr [rax+rax+00h]
0x140005cd7  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x140005cde  test    r8, r8
0x140005ce1  jz      short loc_140005CFB
0x140005ce3  mov     rdx, cs:qword_14007E608; SRWLock
0x140005cea  test    rdx, rdx
0x140005ced  jz      short loc_140005CFB
0x140005cef  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140005cf6  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x140005cfb  lea     rdi, [rbx+98h]
0x140005d02  mov     rsi, [rdi+40h]
0x140005d06  mov     qword ptr [rdi+40h], 0
0x140005d0e  test    rsi, rsi
0x140005d11  jz      short loc_140005D33
0x140005d13  call    cs:__imp_GetProcessHeap
0x140005d1a  nop     dword ptr [rax+rax+00h]
0x140005d1f  mov     rcx, rax; hHeap
0x140005d22  mov     r8, rsi; lpMem
0x140005d25  xor     edx, edx; dwFlags
0x140005d27  call    cs:__imp_HeapFree
0x140005d2e  nop     dword ptr [rax+rax+00h]
0x140005d33  mov     rcx, rdi; lpCriticalSection
0x140005d36  call    cs:__imp_DeleteCriticalSection
0x140005d3d  nop     dword ptr [rax+rax+00h]
0x140005d42  mov     rcx, [rbx+90h]; this
0x140005d49  test    rcx, rcx
0x140005d4c  jz      short loc_140005D53
0x140005d4e  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x140005d53  mov     rsi, [rbx+88h]
0x140005d5a  mov     qword ptr [rbx+88h], 0
0x140005d65  test    rsi, rsi
0x140005d68  jz      short loc_140005D8A
0x140005d6a  call    cs:__imp_GetProcessHeap
0x140005d71  nop     dword ptr [rax+rax+00h]
0x140005d76  mov     rcx, rax; hHeap
0x140005d79  mov     r8, rsi; lpMem
0x140005d7c  xor     edx, edx; dwFlags
0x140005d7e  call    cs:__imp_HeapFree
0x140005d85  nop     dword ptr [rax+rax+00h]
0x140005d8a  lea     rcx, [rbx+48h]; lpCriticalSection
0x140005d8e  call    cs:__imp_DeleteCriticalSection
0x140005d95  nop     dword ptr [rax+rax+00h]
0x140005d9a  mov     rdi, [rbx+38h]
0x140005d9e  mov     esi, 1
0x140005da3  test    rdi, rdi
0x140005da6  jz      short loc_140005DDF
0x140005da8  xor     r9d, r9d; msWindowLength
0x140005dab  xor     r8d, r8d; msPeriod
0x140005dae  xor     edx, edx; pftDueTime
0x140005db0  mov     rcx, rdi; pti
0x140005db3  call    cs:__imp_SetThreadpoolTimer
0x140005dba  nop     dword ptr [rax+rax+00h]
0x140005dbf  mov     edx, esi; fCancelPendingCallbacks
0x140005dc1  mov     rcx, rdi; pti
0x140005dc4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005dcb  nop     dword ptr [rax+rax+00h]
0x140005dd0  mov     rcx, rdi; pti
0x140005dd3  call    cs:__imp_CloseThreadpoolTimer
0x140005dda  nop     dword ptr [rax+rax+00h]
0x140005ddf  mov     rdi, [rbx+30h]
0x140005de3  test    rdi, rdi
0x140005de6  jz      short loc_140005E20
0x140005de8  xor     r9d, r9d; msWindowLength
0x140005deb  xor     r8d, r8d; msPeriod
0x140005dee  xor     edx, edx; pftDueTime
0x140005df0  mov     rcx, rdi; pti
0x140005df3  call    cs:__imp_SetThreadpoolTimer
0x140005dfa  nop     dword ptr [rax+rax+00h]
0x140005dff  mov     edx, esi; fCancelPendingCallbacks
0x140005e01  mov     rcx, rdi; pti
0x140005e04  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005e0b  nop     dword ptr [rax+rax+00h]
0x140005e10  mov     rcx, rdi; pti
0x140005e13  call    cs:__imp_CloseThreadpoolTimer
0x140005e1a  nop     dword ptr [rax+rax+00h]
0x140005e1f  nop
0x140005e20  mov     rcx, [rbx+10h]; lpMem
0x140005e24  test    rcx, rcx
0x140005e27  jz      short loc_140005E2F
0x140005e29  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140005e2e  nop
0x140005e2f  add     rsp, 20h
0x140005e33  pop     r15
0x140005e35  pop     r14
0x140005e37  pop     rdi
0x140005e38  pop     rsi
0x140005e39  pop     rbx
0x140005e3a  retn
```
