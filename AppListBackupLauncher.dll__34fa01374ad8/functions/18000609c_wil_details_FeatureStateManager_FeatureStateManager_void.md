# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000609c`
- end: `0x18000628a`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800111b0`

## callees

- `0x180005b90`
- `0x18000609c`
- `0x18000b50c`
- `0x18000d9c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800061c1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006202`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800061c1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006202`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006168`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800061b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800061f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006168`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800061b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800061f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000615a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800061aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800061ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000615a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800061aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800061ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800060ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006135`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800060ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006135`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006103`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800060e4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000612d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006233`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006264`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800060e4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000612d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006233`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006264`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800060cd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006116`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000621c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000624d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800060cd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006116`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000621c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000624d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800060db`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006124`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000622a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000625b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800060db`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006124`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000622a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000625b`

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
  if ( v8 && qword_180019050 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180019050[25], qword_180019050, v8);
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
0x18000609c  mov     [rsp+arg_0], rbx
0x1800060a1  mov     [rsp+arg_8], rsi
0x1800060a6  push    rdi
0x1800060a7  sub     rsp, 20h
0x1800060ab  mov     rdi, rcx
0x1800060ae  mov     byte ptr [rcx], 0
0x1800060b1  mov     rsi, [rcx+30h]
0x1800060b5  test    rsi, rsi
0x1800060b8  jz      short loc_1800060F2
0x1800060ba  call    cs:__imp_GetLastError
0x1800060c0  mov     ebx, eax
0x1800060c2  xor     r9d, r9d; msWindowLength
0x1800060c5  xor     r8d, r8d; msPeriod
0x1800060c8  xor     edx, edx; pftDueTime
0x1800060ca  mov     rcx, rsi; pti
0x1800060cd  call    cs:__imp_SetThreadpoolTimer
0x1800060d3  mov     edx, 1; fCancelPendingCallbacks
0x1800060d8  mov     rcx, rsi; pti
0x1800060db  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800060e1  mov     rcx, rsi; pti
0x1800060e4  call    cs:__imp_CloseThreadpoolTimer
0x1800060ea  mov     ecx, ebx; dwErrCode
0x1800060ec  call    cs:__imp_SetLastError
0x1800060f2  mov     qword ptr [rdi+30h], 0
0x1800060fa  mov     rsi, [rdi+38h]
0x1800060fe  test    rsi, rsi
0x180006101  jz      short loc_18000613B
0x180006103  call    cs:__imp_GetLastError
0x180006109  mov     ebx, eax
0x18000610b  xor     r9d, r9d; msWindowLength
0x18000610e  xor     r8d, r8d; msPeriod
0x180006111  xor     edx, edx; pftDueTime
0x180006113  mov     rcx, rsi; pti
0x180006116  call    cs:__imp_SetThreadpoolTimer
0x18000611c  mov     edx, 1; fCancelPendingCallbacks
0x180006121  mov     rcx, rsi; pti
0x180006124  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000612a  mov     rcx, rsi; pti
0x18000612d  call    cs:__imp_CloseThreadpoolTimer
0x180006133  mov     ecx, ebx; dwErrCode
0x180006135  call    cs:__imp_SetLastError
0x18000613b  mov     qword ptr [rdi+38h], 0
0x180006143  mov     rbx, [rdi+100h]
0x18000614a  mov     qword ptr [rdi+100h], 0
0x180006155  test    rbx, rbx
0x180006158  jz      short loc_18000616E
0x18000615a  call    cs:__imp_GetProcessHeap
0x180006160  mov     rcx, rax; hHeap
0x180006163  mov     r8, rbx; lpMem
0x180006166  xor     edx, edx; dwFlags
0x180006168  call    cs:__imp_HeapFree
0x18000616e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180006175  test    r8, r8
0x180006178  jz      short loc_180006192
0x18000617a  mov     rdx, cs:qword_180019050; SRWLock
0x180006181  test    rdx, rdx
0x180006184  jz      short loc_180006192
0x180006186  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000618d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180006192  lea     rbx, [rdi+98h]
0x180006199  mov     rsi, [rbx+40h]
0x18000619d  mov     qword ptr [rbx+40h], 0
0x1800061a5  test    rsi, rsi
0x1800061a8  jz      short loc_1800061BE
0x1800061aa  call    cs:__imp_GetProcessHeap
0x1800061b0  mov     rcx, rax; hHeap
0x1800061b3  mov     r8, rsi; lpMem
0x1800061b6  xor     edx, edx; dwFlags
0x1800061b8  call    cs:__imp_HeapFree
0x1800061be  mov     rcx, rbx; lpCriticalSection
0x1800061c1  call    cs:__imp_DeleteCriticalSection
0x1800061c7  lea     rcx, [rdi+90h]
0x1800061ce  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800061d3  mov     rsi, [rdi+88h]
0x1800061da  mov     qword ptr [rdi+88h], 0
0x1800061e5  test    rsi, rsi
0x1800061e8  jz      short loc_1800061FE
0x1800061ea  call    cs:__imp_GetProcessHeap
0x1800061f0  mov     rcx, rax; hHeap
0x1800061f3  mov     r8, rsi; lpMem
0x1800061f6  xor     edx, edx; dwFlags
0x1800061f8  call    cs:__imp_HeapFree
0x1800061fe  lea     rcx, [rdi+48h]; lpCriticalSection
0x180006202  call    cs:__imp_DeleteCriticalSection
0x180006208  mov     rbx, [rdi+38h]
0x18000620c  test    rbx, rbx
0x18000620f  jz      short loc_180006239
0x180006211  xor     r9d, r9d; msWindowLength
0x180006214  xor     r8d, r8d; msPeriod
0x180006217  xor     edx, edx; pftDueTime
0x180006219  mov     rcx, rbx; pti
0x18000621c  call    cs:__imp_SetThreadpoolTimer
0x180006222  mov     edx, 1; fCancelPendingCallbacks
0x180006227  mov     rcx, rbx; pti
0x18000622a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006230  mov     rcx, rbx; pti
0x180006233  call    cs:__imp_CloseThreadpoolTimer
0x180006239  mov     rbx, [rdi+30h]
0x18000623d  test    rbx, rbx
0x180006240  jz      short loc_18000626B
0x180006242  xor     r9d, r9d; msWindowLength
0x180006245  xor     r8d, r8d; msPeriod
0x180006248  xor     edx, edx; pftDueTime
0x18000624a  mov     rcx, rbx; pti
0x18000624d  call    cs:__imp_SetThreadpoolTimer
0x180006253  mov     edx, 1; fCancelPendingCallbacks
0x180006258  mov     rcx, rbx; pti
0x18000625b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006261  mov     rcx, rbx; pti
0x180006264  call    cs:__imp_CloseThreadpoolTimer
0x18000626a  nop
0x18000626b  mov     rcx, [rdi+10h]; lpMem
0x18000626f  test    rcx, rcx
0x180006272  jz      short loc_18000627A
0x180006274  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180006279  nop
0x18000627a  mov     rbx, [rsp+28h+arg_0]
0x18000627f  mov     rsi, [rsp+28h+arg_8]
0x180006284  add     rsp, 20h
0x180006288  pop     rdi
0x180006289  retn
```
