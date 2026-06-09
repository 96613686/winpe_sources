# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000521c`
- end: `0x18000540a`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180032080`

## callees

- `0x180004f10`
- `0x18000521c`
- `0x18000a118`
- `0x18000be7c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005338`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005378`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005338`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005378`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000532a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000536a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000532a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000536a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000526c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800052b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000526c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800052b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000523a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005283`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000523a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005283`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005341`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005382`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005341`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005382`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000525b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800052a4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800053aa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800053db`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000525b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800052a4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800053aa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800053db`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005264`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800052ad`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800053b3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800053e4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005264`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800052ad`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800053b3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800053e4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000524d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005296`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000539c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800053cd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000524d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005296`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000539c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800053cd`

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
  if ( v8 && qword_1800410B8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800410B8[25], qword_1800410B8, v8);
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
0x18000521c  mov     [rsp+arg_0], rbx
0x180005221  mov     [rsp+arg_8], rsi
0x180005226  push    rdi
0x180005227  sub     rsp, 20h
0x18000522b  mov     rdi, rcx
0x18000522e  mov     byte ptr [rcx], 0
0x180005231  mov     rsi, [rcx+30h]
0x180005235  test    rsi, rsi
0x180005238  jz      short loc_180005272
0x18000523a  call    cs:__imp_GetLastError
0x180005240  mov     ebx, eax
0x180005242  xor     r9d, r9d; msWindowLength
0x180005245  xor     r8d, r8d; msPeriod
0x180005248  xor     edx, edx; pftDueTime
0x18000524a  mov     rcx, rsi; pti
0x18000524d  call    cs:__imp_SetThreadpoolTimer
0x180005253  mov     edx, 1; fCancelPendingCallbacks
0x180005258  mov     rcx, rsi; pti
0x18000525b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005261  mov     rcx, rsi; pti
0x180005264  call    cs:__imp_CloseThreadpoolTimer
0x18000526a  mov     ecx, ebx; dwErrCode
0x18000526c  call    cs:__imp_SetLastError
0x180005272  mov     qword ptr [rdi+30h], 0
0x18000527a  mov     rsi, [rdi+38h]
0x18000527e  test    rsi, rsi
0x180005281  jz      short loc_1800052BB
0x180005283  call    cs:__imp_GetLastError
0x180005289  mov     ebx, eax
0x18000528b  xor     r9d, r9d; msWindowLength
0x18000528e  xor     r8d, r8d; msPeriod
0x180005291  xor     edx, edx; pftDueTime
0x180005293  mov     rcx, rsi; pti
0x180005296  call    cs:__imp_SetThreadpoolTimer
0x18000529c  mov     edx, 1; fCancelPendingCallbacks
0x1800052a1  mov     rcx, rsi; pti
0x1800052a4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800052aa  mov     rcx, rsi; pti
0x1800052ad  call    cs:__imp_CloseThreadpoolTimer
0x1800052b3  mov     ecx, ebx; dwErrCode
0x1800052b5  call    cs:__imp_SetLastError
0x1800052bb  mov     qword ptr [rdi+38h], 0
0x1800052c3  mov     rbx, [rdi+100h]
0x1800052ca  mov     qword ptr [rdi+100h], 0
0x1800052d5  test    rbx, rbx
0x1800052d8  jz      short loc_1800052EE
0x1800052da  call    cs:__imp_GetProcessHeap
0x1800052e0  mov     rcx, rax; hHeap
0x1800052e3  mov     r8, rbx; lpMem
0x1800052e6  xor     edx, edx; dwFlags
0x1800052e8  call    cs:__imp_HeapFree
0x1800052ee  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800052f5  test    r8, r8
0x1800052f8  jz      short loc_180005312
0x1800052fa  mov     rdx, cs:qword_1800410B8; SRWLock
0x180005301  test    rdx, rdx
0x180005304  jz      short loc_180005312
0x180005306  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000530d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180005312  lea     rbx, [rdi+98h]
0x180005319  mov     rsi, [rbx+40h]
0x18000531d  mov     qword ptr [rbx+40h], 0
0x180005325  test    rsi, rsi
0x180005328  jz      short loc_18000533E
0x18000532a  call    cs:__imp_GetProcessHeap
0x180005330  mov     rcx, rax; hHeap
0x180005333  mov     r8, rsi; lpMem
0x180005336  xor     edx, edx; dwFlags
0x180005338  call    cs:__imp_HeapFree
0x18000533e  mov     rcx, rbx; lpCriticalSection
0x180005341  call    cs:__imp_DeleteCriticalSection
0x180005347  lea     rcx, [rdi+90h]
0x18000534e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180005353  mov     rsi, [rdi+88h]
0x18000535a  mov     qword ptr [rdi+88h], 0
0x180005365  test    rsi, rsi
0x180005368  jz      short loc_18000537E
0x18000536a  call    cs:__imp_GetProcessHeap
0x180005370  mov     rcx, rax; hHeap
0x180005373  mov     r8, rsi; lpMem
0x180005376  xor     edx, edx; dwFlags
0x180005378  call    cs:__imp_HeapFree
0x18000537e  lea     rcx, [rdi+48h]; lpCriticalSection
0x180005382  call    cs:__imp_DeleteCriticalSection
0x180005388  mov     rbx, [rdi+38h]
0x18000538c  test    rbx, rbx
0x18000538f  jz      short loc_1800053B9
0x180005391  xor     r9d, r9d; msWindowLength
0x180005394  xor     r8d, r8d; msPeriod
0x180005397  xor     edx, edx; pftDueTime
0x180005399  mov     rcx, rbx; pti
0x18000539c  call    cs:__imp_SetThreadpoolTimer
0x1800053a2  mov     edx, 1; fCancelPendingCallbacks
0x1800053a7  mov     rcx, rbx; pti
0x1800053aa  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800053b0  mov     rcx, rbx; pti
0x1800053b3  call    cs:__imp_CloseThreadpoolTimer
0x1800053b9  mov     rbx, [rdi+30h]
0x1800053bd  test    rbx, rbx
0x1800053c0  jz      short loc_1800053EB
0x1800053c2  xor     r9d, r9d; msWindowLength
0x1800053c5  xor     r8d, r8d; msPeriod
0x1800053c8  xor     edx, edx; pftDueTime
0x1800053ca  mov     rcx, rbx; pti
0x1800053cd  call    cs:__imp_SetThreadpoolTimer
0x1800053d3  mov     edx, 1; fCancelPendingCallbacks
0x1800053d8  mov     rcx, rbx; pti
0x1800053db  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800053e1  mov     rcx, rbx; pti
0x1800053e4  call    cs:__imp_CloseThreadpoolTimer
0x1800053ea  nop
0x1800053eb  mov     rcx, [rdi+10h]; lpMem
0x1800053ef  test    rcx, rcx
0x1800053f2  jz      short loc_1800053FA
0x1800053f4  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800053f9  nop
0x1800053fa  mov     rbx, [rsp+28h+arg_0]
0x1800053ff  mov     rsi, [rsp+28h+arg_8]
0x180005404  add     rsp, 20h
0x180005408  pop     rdi
0x180005409  retn
```
