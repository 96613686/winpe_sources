# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180039970`
- end: `0x180039b32`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `450`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1801b8300`

## callees

- `0x180039970`
- `0x18003bb0c`
- `0x18003c348`
- `0x18003c3bc`
- `0x18003c954`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180039a2e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180039a86`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180039a2e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180039a86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800399c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039a1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039a76`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800399c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039a1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039a76`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800399af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039a0b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039a62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800399af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039a0b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039a62`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180039aab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180039aeb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180039aab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180039aeb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180039abc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180039afc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180039abc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180039afc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180039acb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180039b0b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180039acb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180039b0b`

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
  if ( v4 && qword_18023D368 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18023D368[25], qword_18023D368, v4);
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
0x180039970  push    rbx
0x180039972  push    rsi
0x180039973  push    rdi
0x180039974  push    r14
0x180039976  push    r15
0x180039978  sub     rsp, 20h
0x18003997c  mov     rbx, rcx
0x18003997f  mov     byte ptr [rcx], 0
0x180039982  add     rcx, 30h ; '0'
0x180039986  xor     edx, edx
0x180039988  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18003998d  xor     edx, edx
0x18003998f  lea     rcx, [rbx+38h]
0x180039993  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180039998  mov     rdi, [rbx+100h]
0x18003999f  mov     qword ptr [rbx+100h], 0
0x1800399aa  test    rdi, rdi
0x1800399ad  jz      short loc_1800399CF
0x1800399af  call    cs:__imp_GetProcessHeap
0x1800399b6  nop     dword ptr [rax+rax+00h]
0x1800399bb  mov     r8, rdi; lpMem
0x1800399be  xor     edx, edx; dwFlags
0x1800399c0  mov     rcx, rax; hHeap
0x1800399c3  call    cs:__imp_HeapFree
0x1800399ca  nop     dword ptr [rax+rax+00h]
0x1800399cf  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800399d6  test    r8, r8
0x1800399d9  jz      short loc_1800399F3
0x1800399db  mov     rdx, cs:qword_18023D368; SRWLock
0x1800399e2  test    rdx, rdx
0x1800399e5  jz      short loc_1800399F3
0x1800399e7  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800399ee  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800399f3  lea     rdi, [rbx+98h]
0x1800399fa  mov     rsi, [rdi+40h]
0x1800399fe  mov     qword ptr [rdi+40h], 0
0x180039a06  test    rsi, rsi
0x180039a09  jz      short loc_180039A2B
0x180039a0b  call    cs:__imp_GetProcessHeap
0x180039a12  nop     dword ptr [rax+rax+00h]
0x180039a17  mov     r8, rsi; lpMem
0x180039a1a  xor     edx, edx; dwFlags
0x180039a1c  mov     rcx, rax; hHeap
0x180039a1f  call    cs:__imp_HeapFree
0x180039a26  nop     dword ptr [rax+rax+00h]
0x180039a2b  mov     rcx, rdi; lpCriticalSection
0x180039a2e  call    cs:__imp_DeleteCriticalSection
0x180039a35  nop     dword ptr [rax+rax+00h]
0x180039a3a  mov     rcx, [rbx+90h]; this
0x180039a41  test    rcx, rcx
0x180039a44  jz      short loc_180039A4B
0x180039a46  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x180039a4b  mov     rsi, [rbx+88h]
0x180039a52  mov     qword ptr [rbx+88h], 0
0x180039a5d  test    rsi, rsi
0x180039a60  jz      short loc_180039A82
0x180039a62  call    cs:__imp_GetProcessHeap
0x180039a69  nop     dword ptr [rax+rax+00h]
0x180039a6e  mov     r8, rsi; lpMem
0x180039a71  xor     edx, edx; dwFlags
0x180039a73  mov     rcx, rax; hHeap
0x180039a76  call    cs:__imp_HeapFree
0x180039a7d  nop     dword ptr [rax+rax+00h]
0x180039a82  lea     rcx, [rbx+48h]; lpCriticalSection
0x180039a86  call    cs:__imp_DeleteCriticalSection
0x180039a8d  nop     dword ptr [rax+rax+00h]
0x180039a92  mov     rdi, [rbx+38h]
0x180039a96  mov     esi, 1
0x180039a9b  test    rdi, rdi
0x180039a9e  jz      short loc_180039AD7
0x180039aa0  xor     r9d, r9d; msWindowLength
0x180039aa3  xor     r8d, r8d; msPeriod
0x180039aa6  xor     edx, edx; pftDueTime
0x180039aa8  mov     rcx, rdi; pti
0x180039aab  call    cs:__imp_SetThreadpoolTimer
0x180039ab2  nop     dword ptr [rax+rax+00h]
0x180039ab7  mov     edx, esi; fCancelPendingCallbacks
0x180039ab9  mov     rcx, rdi; pti
0x180039abc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180039ac3  nop     dword ptr [rax+rax+00h]
0x180039ac8  mov     rcx, rdi; pti
0x180039acb  call    cs:__imp_CloseThreadpoolTimer
0x180039ad2  nop     dword ptr [rax+rax+00h]
0x180039ad7  mov     rdi, [rbx+30h]
0x180039adb  test    rdi, rdi
0x180039ade  jz      short loc_180039B17
0x180039ae0  xor     r9d, r9d; msWindowLength
0x180039ae3  xor     r8d, r8d; msPeriod
0x180039ae6  xor     edx, edx; pftDueTime
0x180039ae8  mov     rcx, rdi; pti
0x180039aeb  call    cs:__imp_SetThreadpoolTimer
0x180039af2  nop     dword ptr [rax+rax+00h]
0x180039af7  mov     edx, esi; fCancelPendingCallbacks
0x180039af9  mov     rcx, rdi; pti
0x180039afc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180039b03  nop     dword ptr [rax+rax+00h]
0x180039b08  mov     rcx, rdi; pti
0x180039b0b  call    cs:__imp_CloseThreadpoolTimer
0x180039b12  nop     dword ptr [rax+rax+00h]
0x180039b17  mov     rcx, [rbx+10h]; lpMem
0x180039b1b  test    rcx, rcx
0x180039b1e  jz      short loc_180039B25
0x180039b20  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180039b25  add     rsp, 20h
0x180039b29  pop     r15
0x180039b2b  pop     r14
0x180039b2d  pop     rdi
0x180039b2e  pop     rsi
0x180039b2f  pop     rbx
0x180039b30  retn
```
