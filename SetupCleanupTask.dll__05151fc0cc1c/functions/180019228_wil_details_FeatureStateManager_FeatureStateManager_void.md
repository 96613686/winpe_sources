# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180019228`
- end: `0x180019414`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800354c0`

## callees

- `0x1800190e4`
- `0x180019228`
- `0x180021ab0`
- `0x180023794`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001934d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001938e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001934d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001938e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019278`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800192c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019278`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800192c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019246`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001928f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019246`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001928f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800192e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019336`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019376`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800192e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019336`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019376`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800192f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019344`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019384`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800192f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019344`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019384`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019259`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800192a2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800193a8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800193d9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019259`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800192a2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800193a8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800193d9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180019267`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800192b0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800193b6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800193e7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180019267`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800192b0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800193b6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800193e7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180019270`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800192b9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800193bf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800193f0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180019270`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800192b9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800193bf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800193f0`

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
  if ( v8 && qword_1800510B0 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800510B0[25], qword_1800510B0, v8);
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
0x180019228  mov     [rsp+arg_0], rbx
0x18001922d  mov     [rsp+arg_8], rsi
0x180019232  push    rdi
0x180019233  sub     rsp, 20h
0x180019237  mov     byte ptr [rcx], 0
0x18001923a  mov     rdi, rcx
0x18001923d  mov     rsi, [rcx+30h]
0x180019241  test    rsi, rsi
0x180019244  jz      short loc_18001927E
0x180019246  call    cs:__imp_GetLastError
0x18001924c  xor     r9d, r9d; msWindowLength
0x18001924f  xor     r8d, r8d; msPeriod
0x180019252  xor     edx, edx; pftDueTime
0x180019254  mov     rcx, rsi; pti
0x180019257  mov     ebx, eax
0x180019259  call    cs:__imp_SetThreadpoolTimer
0x18001925f  mov     edx, 1; fCancelPendingCallbacks
0x180019264  mov     rcx, rsi; pti
0x180019267  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001926d  mov     rcx, rsi; pti
0x180019270  call    cs:__imp_CloseThreadpoolTimer
0x180019276  mov     ecx, ebx; dwErrCode
0x180019278  call    cs:__imp_SetLastError
0x18001927e  mov     qword ptr [rdi+30h], 0
0x180019286  mov     rsi, [rdi+38h]
0x18001928a  test    rsi, rsi
0x18001928d  jz      short loc_1800192C7
0x18001928f  call    cs:__imp_GetLastError
0x180019295  xor     r9d, r9d; msWindowLength
0x180019298  xor     r8d, r8d; msPeriod
0x18001929b  xor     edx, edx; pftDueTime
0x18001929d  mov     rcx, rsi; pti
0x1800192a0  mov     ebx, eax
0x1800192a2  call    cs:__imp_SetThreadpoolTimer
0x1800192a8  mov     edx, 1; fCancelPendingCallbacks
0x1800192ad  mov     rcx, rsi; pti
0x1800192b0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800192b6  mov     rcx, rsi; pti
0x1800192b9  call    cs:__imp_CloseThreadpoolTimer
0x1800192bf  mov     ecx, ebx; dwErrCode
0x1800192c1  call    cs:__imp_SetLastError
0x1800192c7  mov     qword ptr [rdi+38h], 0
0x1800192cf  mov     rbx, [rdi+100h]
0x1800192d6  mov     qword ptr [rdi+100h], 0
0x1800192e1  test    rbx, rbx
0x1800192e4  jz      short loc_1800192FA
0x1800192e6  call    cs:__imp_GetProcessHeap
0x1800192ec  mov     r8, rbx; lpMem
0x1800192ef  xor     edx, edx; dwFlags
0x1800192f1  mov     rcx, rax; hHeap
0x1800192f4  call    cs:__imp_HeapFree
0x1800192fa  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180019301  test    r8, r8
0x180019304  jz      short loc_18001931E
0x180019306  mov     rdx, cs:qword_1800510B0; SRWLock
0x18001930d  test    rdx, rdx
0x180019310  jz      short loc_18001931E
0x180019312  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180019319  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18001931e  lea     rbx, [rdi+98h]
0x180019325  mov     rsi, [rbx+40h]
0x180019329  mov     qword ptr [rbx+40h], 0
0x180019331  test    rsi, rsi
0x180019334  jz      short loc_18001934A
0x180019336  call    cs:__imp_GetProcessHeap
0x18001933c  mov     r8, rsi; lpMem
0x18001933f  xor     edx, edx; dwFlags
0x180019341  mov     rcx, rax; hHeap
0x180019344  call    cs:__imp_HeapFree
0x18001934a  mov     rcx, rbx; lpCriticalSection
0x18001934d  call    cs:__imp_DeleteCriticalSection
0x180019353  lea     rcx, [rdi+90h]
0x18001935a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001935f  mov     rsi, [rdi+88h]
0x180019366  mov     qword ptr [rdi+88h], 0
0x180019371  test    rsi, rsi
0x180019374  jz      short loc_18001938A
0x180019376  call    cs:__imp_GetProcessHeap
0x18001937c  mov     r8, rsi; lpMem
0x18001937f  xor     edx, edx; dwFlags
0x180019381  mov     rcx, rax; hHeap
0x180019384  call    cs:__imp_HeapFree
0x18001938a  lea     rcx, [rdi+48h]; lpCriticalSection
0x18001938e  call    cs:__imp_DeleteCriticalSection
0x180019394  mov     rbx, [rdi+38h]
0x180019398  test    rbx, rbx
0x18001939b  jz      short loc_1800193C5
0x18001939d  xor     r9d, r9d; msWindowLength
0x1800193a0  xor     r8d, r8d; msPeriod
0x1800193a3  xor     edx, edx; pftDueTime
0x1800193a5  mov     rcx, rbx; pti
0x1800193a8  call    cs:__imp_SetThreadpoolTimer
0x1800193ae  mov     edx, 1; fCancelPendingCallbacks
0x1800193b3  mov     rcx, rbx; pti
0x1800193b6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800193bc  mov     rcx, rbx; pti
0x1800193bf  call    cs:__imp_CloseThreadpoolTimer
0x1800193c5  mov     rbx, [rdi+30h]
0x1800193c9  test    rbx, rbx
0x1800193cc  jz      short loc_1800193F6
0x1800193ce  xor     r9d, r9d; msWindowLength
0x1800193d1  xor     r8d, r8d; msPeriod
0x1800193d4  xor     edx, edx; pftDueTime
0x1800193d6  mov     rcx, rbx; pti
0x1800193d9  call    cs:__imp_SetThreadpoolTimer
0x1800193df  mov     edx, 1; fCancelPendingCallbacks
0x1800193e4  mov     rcx, rbx; pti
0x1800193e7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800193ed  mov     rcx, rbx; pti
0x1800193f0  call    cs:__imp_CloseThreadpoolTimer
0x1800193f6  mov     rcx, [rdi+10h]; lpMem
0x1800193fa  test    rcx, rcx
0x1800193fd  jz      short loc_180019404
0x1800193ff  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180019404  mov     rbx, [rsp+28h+arg_0]
0x180019409  mov     rsi, [rsp+28h+arg_8]
0x18001940e  add     rsp, 20h
0x180019412  pop     rdi
0x180019413  retn
```
