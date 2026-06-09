# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18001067c`
- end: `0x180010868`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001d650`

## callees

- `0x1800103ec`
- `0x18001067c`
- `0x180016140`
- `0x1800178b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001073a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001078a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800107ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001073a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001078a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800107ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010748`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010798`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800107d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010748`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010798`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800107d8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800107a1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800107e2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800107a1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800107e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800106cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010715`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800106cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010715`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001069a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800106e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001069a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800106e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800106c4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001070d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010813`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010844`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800106c4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001070d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010813`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010844`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800106bb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010704`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001080a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001083b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800106bb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010704`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001080a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001083b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800106ad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800106f6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800107fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001082d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800106ad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800106f6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800107fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001082d`

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
  if ( v8 && qword_1800292A0 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800292A0[25], qword_1800292A0, v8);
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
0x18001067c  mov     [rsp+arg_0], rbx
0x180010681  mov     [rsp+arg_8], rsi
0x180010686  push    rdi
0x180010687  sub     rsp, 20h
0x18001068b  mov     byte ptr [rcx], 0
0x18001068e  mov     rdi, rcx
0x180010691  mov     rsi, [rcx+30h]
0x180010695  test    rsi, rsi
0x180010698  jz      short loc_1800106D2
0x18001069a  call    cs:__imp_GetLastError
0x1800106a0  xor     r9d, r9d; msWindowLength
0x1800106a3  xor     r8d, r8d; msPeriod
0x1800106a6  xor     edx, edx; pftDueTime
0x1800106a8  mov     rcx, rsi; pti
0x1800106ab  mov     ebx, eax
0x1800106ad  call    cs:__imp_SetThreadpoolTimer
0x1800106b3  mov     edx, 1; fCancelPendingCallbacks
0x1800106b8  mov     rcx, rsi; pti
0x1800106bb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800106c1  mov     rcx, rsi; pti
0x1800106c4  call    cs:__imp_CloseThreadpoolTimer
0x1800106ca  mov     ecx, ebx; dwErrCode
0x1800106cc  call    cs:__imp_SetLastError
0x1800106d2  mov     qword ptr [rdi+30h], 0
0x1800106da  mov     rsi, [rdi+38h]
0x1800106de  test    rsi, rsi
0x1800106e1  jz      short loc_18001071B
0x1800106e3  call    cs:__imp_GetLastError
0x1800106e9  xor     r9d, r9d; msWindowLength
0x1800106ec  xor     r8d, r8d; msPeriod
0x1800106ef  xor     edx, edx; pftDueTime
0x1800106f1  mov     rcx, rsi; pti
0x1800106f4  mov     ebx, eax
0x1800106f6  call    cs:__imp_SetThreadpoolTimer
0x1800106fc  mov     edx, 1; fCancelPendingCallbacks
0x180010701  mov     rcx, rsi; pti
0x180010704  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001070a  mov     rcx, rsi; pti
0x18001070d  call    cs:__imp_CloseThreadpoolTimer
0x180010713  mov     ecx, ebx; dwErrCode
0x180010715  call    cs:__imp_SetLastError
0x18001071b  mov     qword ptr [rdi+38h], 0
0x180010723  mov     rbx, [rdi+100h]
0x18001072a  mov     qword ptr [rdi+100h], 0
0x180010735  test    rbx, rbx
0x180010738  jz      short loc_18001074E
0x18001073a  call    cs:__imp_GetProcessHeap
0x180010740  mov     r8, rbx; lpMem
0x180010743  xor     edx, edx; dwFlags
0x180010745  mov     rcx, rax; hHeap
0x180010748  call    cs:__imp_HeapFree
0x18001074e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180010755  test    r8, r8
0x180010758  jz      short loc_180010772
0x18001075a  mov     rdx, cs:qword_1800292A0; SRWLock
0x180010761  test    rdx, rdx
0x180010764  jz      short loc_180010772
0x180010766  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18001076d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180010772  lea     rbx, [rdi+98h]
0x180010779  mov     rsi, [rbx+40h]
0x18001077d  mov     qword ptr [rbx+40h], 0
0x180010785  test    rsi, rsi
0x180010788  jz      short loc_18001079E
0x18001078a  call    cs:__imp_GetProcessHeap
0x180010790  mov     r8, rsi; lpMem
0x180010793  xor     edx, edx; dwFlags
0x180010795  mov     rcx, rax; hHeap
0x180010798  call    cs:__imp_HeapFree
0x18001079e  mov     rcx, rbx; lpCriticalSection
0x1800107a1  call    cs:__imp_DeleteCriticalSection
0x1800107a7  lea     rcx, [rdi+90h]
0x1800107ae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800107b3  mov     rsi, [rdi+88h]
0x1800107ba  mov     qword ptr [rdi+88h], 0
0x1800107c5  test    rsi, rsi
0x1800107c8  jz      short loc_1800107DE
0x1800107ca  call    cs:__imp_GetProcessHeap
0x1800107d0  mov     r8, rsi; lpMem
0x1800107d3  xor     edx, edx; dwFlags
0x1800107d5  mov     rcx, rax; hHeap
0x1800107d8  call    cs:__imp_HeapFree
0x1800107de  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800107e2  call    cs:__imp_DeleteCriticalSection
0x1800107e8  mov     rbx, [rdi+38h]
0x1800107ec  test    rbx, rbx
0x1800107ef  jz      short loc_180010819
0x1800107f1  xor     r9d, r9d; msWindowLength
0x1800107f4  xor     r8d, r8d; msPeriod
0x1800107f7  xor     edx, edx; pftDueTime
0x1800107f9  mov     rcx, rbx; pti
0x1800107fc  call    cs:__imp_SetThreadpoolTimer
0x180010802  mov     edx, 1; fCancelPendingCallbacks
0x180010807  mov     rcx, rbx; pti
0x18001080a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010810  mov     rcx, rbx; pti
0x180010813  call    cs:__imp_CloseThreadpoolTimer
0x180010819  mov     rbx, [rdi+30h]
0x18001081d  test    rbx, rbx
0x180010820  jz      short loc_18001084A
0x180010822  xor     r9d, r9d; msWindowLength
0x180010825  xor     r8d, r8d; msPeriod
0x180010828  xor     edx, edx; pftDueTime
0x18001082a  mov     rcx, rbx; pti
0x18001082d  call    cs:__imp_SetThreadpoolTimer
0x180010833  mov     edx, 1; fCancelPendingCallbacks
0x180010838  mov     rcx, rbx; pti
0x18001083b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010841  mov     rcx, rbx; pti
0x180010844  call    cs:__imp_CloseThreadpoolTimer
0x18001084a  mov     rcx, [rdi+10h]; lpMem
0x18001084e  test    rcx, rcx
0x180010851  jz      short loc_180010858
0x180010853  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180010858  mov     rbx, [rsp+28h+arg_0]
0x18001085d  mov     rsi, [rsp+28h+arg_8]
0x180010862  add     rsp, 20h
0x180010866  pop     rdi
0x180010867  retn
```
