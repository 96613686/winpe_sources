# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800086fc`
- end: `0x1800088c0`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `452`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1801b1920`

## callees

- `0x1800086fc`
- `0x18000d588`
- `0x180015b8c`
- `0x180015c00`
- `0x180016b7c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008837`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008877`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008837`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008877`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008857`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008897`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008857`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008897`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008848`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008888`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008848`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008888`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800087ba`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008812`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800087ba`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008812`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000873b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008797`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800087ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000873b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008797`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800087ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000874f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800087ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008802`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000874f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800087ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008802`

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
  if ( v4 && qword_18021E370 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18021E370[25], qword_18021E370, v4);
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
0x1800086fc  push    rbx
0x1800086fe  push    rsi
0x1800086ff  push    rdi
0x180008700  push    r14
0x180008702  push    r15
0x180008704  sub     rsp, 20h
0x180008708  mov     rbx, rcx
0x18000870b  mov     byte ptr [rcx], 0
0x18000870e  xor     edx, edx
0x180008710  add     rcx, 30h ; '0'
0x180008714  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180008719  xor     edx, edx
0x18000871b  lea     rcx, [rbx+38h]
0x18000871f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180008724  mov     rdi, [rbx+100h]
0x18000872b  mov     qword ptr [rbx+100h], 0
0x180008736  test    rdi, rdi
0x180008739  jz      short loc_18000875B
0x18000873b  call    cs:__imp_GetProcessHeap
0x180008742  nop     dword ptr [rax+rax+00h]
0x180008747  mov     rcx, rax; hHeap
0x18000874a  mov     r8, rdi; lpMem
0x18000874d  xor     edx, edx; dwFlags
0x18000874f  call    cs:__imp_HeapFree
0x180008756  nop     dword ptr [rax+rax+00h]
0x18000875b  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180008762  test    r8, r8
0x180008765  jz      short loc_18000877F
0x180008767  mov     rdx, cs:qword_18021E370; SRWLock
0x18000876e  test    rdx, rdx
0x180008771  jz      short loc_18000877F
0x180008773  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000877a  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000877f  lea     rdi, [rbx+98h]
0x180008786  mov     rsi, [rdi+40h]
0x18000878a  mov     qword ptr [rdi+40h], 0
0x180008792  test    rsi, rsi
0x180008795  jz      short loc_1800087B7
0x180008797  call    cs:__imp_GetProcessHeap
0x18000879e  nop     dword ptr [rax+rax+00h]
0x1800087a3  mov     rcx, rax; hHeap
0x1800087a6  mov     r8, rsi; lpMem
0x1800087a9  xor     edx, edx; dwFlags
0x1800087ab  call    cs:__imp_HeapFree
0x1800087b2  nop     dword ptr [rax+rax+00h]
0x1800087b7  mov     rcx, rdi; lpCriticalSection
0x1800087ba  call    cs:__imp_DeleteCriticalSection
0x1800087c1  nop     dword ptr [rax+rax+00h]
0x1800087c6  mov     rcx, [rbx+90h]; this
0x1800087cd  test    rcx, rcx
0x1800087d0  jz      short loc_1800087D7
0x1800087d2  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x1800087d7  mov     rsi, [rbx+88h]
0x1800087de  mov     qword ptr [rbx+88h], 0
0x1800087e9  test    rsi, rsi
0x1800087ec  jz      short loc_18000880E
0x1800087ee  call    cs:__imp_GetProcessHeap
0x1800087f5  nop     dword ptr [rax+rax+00h]
0x1800087fa  mov     rcx, rax; hHeap
0x1800087fd  mov     r8, rsi; lpMem
0x180008800  xor     edx, edx; dwFlags
0x180008802  call    cs:__imp_HeapFree
0x180008809  nop     dword ptr [rax+rax+00h]
0x18000880e  lea     rcx, [rbx+48h]; lpCriticalSection
0x180008812  call    cs:__imp_DeleteCriticalSection
0x180008819  nop     dword ptr [rax+rax+00h]
0x18000881e  mov     rdi, [rbx+38h]
0x180008822  mov     esi, 1
0x180008827  test    rdi, rdi
0x18000882a  jz      short loc_180008863
0x18000882c  xor     r9d, r9d; msWindowLength
0x18000882f  xor     r8d, r8d; msPeriod
0x180008832  xor     edx, edx; pftDueTime
0x180008834  mov     rcx, rdi; pti
0x180008837  call    cs:__imp_SetThreadpoolTimer
0x18000883e  nop     dword ptr [rax+rax+00h]
0x180008843  mov     edx, esi; fCancelPendingCallbacks
0x180008845  mov     rcx, rdi; pti
0x180008848  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000884f  nop     dword ptr [rax+rax+00h]
0x180008854  mov     rcx, rdi; pti
0x180008857  call    cs:__imp_CloseThreadpoolTimer
0x18000885e  nop     dword ptr [rax+rax+00h]
0x180008863  mov     rdi, [rbx+30h]
0x180008867  test    rdi, rdi
0x18000886a  jz      short loc_1800088A4
0x18000886c  xor     r9d, r9d; msWindowLength
0x18000886f  xor     r8d, r8d; msPeriod
0x180008872  xor     edx, edx; pftDueTime
0x180008874  mov     rcx, rdi; pti
0x180008877  call    cs:__imp_SetThreadpoolTimer
0x18000887e  nop     dword ptr [rax+rax+00h]
0x180008883  mov     edx, esi; fCancelPendingCallbacks
0x180008885  mov     rcx, rdi; pti
0x180008888  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000888f  nop     dword ptr [rax+rax+00h]
0x180008894  mov     rcx, rdi; pti
0x180008897  call    cs:__imp_CloseThreadpoolTimer
0x18000889e  nop     dword ptr [rax+rax+00h]
0x1800088a3  nop
0x1800088a4  mov     rcx, [rbx+10h]; lpMem
0x1800088a8  test    rcx, rcx
0x1800088ab  jz      short loc_1800088B3
0x1800088ad  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800088b2  nop
0x1800088b3  add     rsp, 20h
0x1800088b7  pop     r15
0x1800088b9  pop     r14
0x1800088bb  pop     rdi
0x1800088bc  pop     rsi
0x1800088bd  pop     rbx
0x1800088be  retn
```
