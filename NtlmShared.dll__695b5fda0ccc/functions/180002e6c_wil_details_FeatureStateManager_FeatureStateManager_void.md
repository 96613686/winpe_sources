# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180002e6c`
- end: `0x180003058`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000c730`

## callees

- `0x180002bdc`
- `0x180002e6c`
- `0x180006814`
- `0x18000761c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002f91`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002fd2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002f91`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002fd2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002fc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002fc8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002fba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002fba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ed3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002ebc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002f05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002ebc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002f05`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002e9d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002ee6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002fec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000301d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002e9d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002ee6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002fec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000301d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002eab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002ef4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002ffa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000302b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002eab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002ef4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002ffa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000302b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002eb4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002efd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003003`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003034`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002eb4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002efd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003003`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003034`

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
  if ( v8 && qword_180012058 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180012058[25], qword_180012058, v8);
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
0x180002e6c  mov     [rsp+arg_0], rbx
0x180002e71  mov     [rsp+arg_8], rsi
0x180002e76  push    rdi
0x180002e77  sub     rsp, 20h
0x180002e7b  mov     byte ptr [rcx], 0
0x180002e7e  mov     rdi, rcx
0x180002e81  mov     rsi, [rcx+30h]
0x180002e85  test    rsi, rsi
0x180002e88  jz      short loc_180002EC2
0x180002e8a  call    cs:__imp_GetLastError
0x180002e90  xor     r9d, r9d; msWindowLength
0x180002e93  xor     r8d, r8d; msPeriod
0x180002e96  xor     edx, edx; pftDueTime
0x180002e98  mov     rcx, rsi; pti
0x180002e9b  mov     ebx, eax
0x180002e9d  call    cs:__imp_SetThreadpoolTimer
0x180002ea3  mov     edx, 1; fCancelPendingCallbacks
0x180002ea8  mov     rcx, rsi; pti
0x180002eab  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180002eb1  mov     rcx, rsi; pti
0x180002eb4  call    cs:__imp_CloseThreadpoolTimer
0x180002eba  mov     ecx, ebx; dwErrCode
0x180002ebc  call    cs:__imp_SetLastError
0x180002ec2  mov     qword ptr [rdi+30h], 0
0x180002eca  mov     rsi, [rdi+38h]
0x180002ece  test    rsi, rsi
0x180002ed1  jz      short loc_180002F0B
0x180002ed3  call    cs:__imp_GetLastError
0x180002ed9  xor     r9d, r9d; msWindowLength
0x180002edc  xor     r8d, r8d; msPeriod
0x180002edf  xor     edx, edx; pftDueTime
0x180002ee1  mov     rcx, rsi; pti
0x180002ee4  mov     ebx, eax
0x180002ee6  call    cs:__imp_SetThreadpoolTimer
0x180002eec  mov     edx, 1; fCancelPendingCallbacks
0x180002ef1  mov     rcx, rsi; pti
0x180002ef4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180002efa  mov     rcx, rsi; pti
0x180002efd  call    cs:__imp_CloseThreadpoolTimer
0x180002f03  mov     ecx, ebx; dwErrCode
0x180002f05  call    cs:__imp_SetLastError
0x180002f0b  mov     qword ptr [rdi+38h], 0
0x180002f13  mov     rbx, [rdi+100h]
0x180002f1a  mov     qword ptr [rdi+100h], 0
0x180002f25  test    rbx, rbx
0x180002f28  jz      short loc_180002F3E
0x180002f2a  call    cs:__imp_GetProcessHeap
0x180002f30  mov     r8, rbx; lpMem
0x180002f33  xor     edx, edx; dwFlags
0x180002f35  mov     rcx, rax; hHeap
0x180002f38  call    cs:__imp_HeapFree
0x180002f3e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180002f45  test    r8, r8
0x180002f48  jz      short loc_180002F62
0x180002f4a  mov     rdx, cs:qword_180012058; SRWLock
0x180002f51  test    rdx, rdx
0x180002f54  jz      short loc_180002F62
0x180002f56  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180002f5d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180002f62  lea     rbx, [rdi+98h]
0x180002f69  mov     rsi, [rbx+40h]
0x180002f6d  mov     qword ptr [rbx+40h], 0
0x180002f75  test    rsi, rsi
0x180002f78  jz      short loc_180002F8E
0x180002f7a  call    cs:__imp_GetProcessHeap
0x180002f80  mov     r8, rsi; lpMem
0x180002f83  xor     edx, edx; dwFlags
0x180002f85  mov     rcx, rax; hHeap
0x180002f88  call    cs:__imp_HeapFree
0x180002f8e  mov     rcx, rbx; lpCriticalSection
0x180002f91  call    cs:__imp_DeleteCriticalSection
0x180002f97  lea     rcx, [rdi+90h]
0x180002f9e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180002fa3  mov     rsi, [rdi+88h]
0x180002faa  mov     qword ptr [rdi+88h], 0
0x180002fb5  test    rsi, rsi
0x180002fb8  jz      short loc_180002FCE
0x180002fba  call    cs:__imp_GetProcessHeap
0x180002fc0  mov     r8, rsi; lpMem
0x180002fc3  xor     edx, edx; dwFlags
0x180002fc5  mov     rcx, rax; hHeap
0x180002fc8  call    cs:__imp_HeapFree
0x180002fce  lea     rcx, [rdi+48h]; lpCriticalSection
0x180002fd2  call    cs:__imp_DeleteCriticalSection
0x180002fd8  mov     rbx, [rdi+38h]
0x180002fdc  test    rbx, rbx
0x180002fdf  jz      short loc_180003009
0x180002fe1  xor     r9d, r9d; msWindowLength
0x180002fe4  xor     r8d, r8d; msPeriod
0x180002fe7  xor     edx, edx; pftDueTime
0x180002fe9  mov     rcx, rbx; pti
0x180002fec  call    cs:__imp_SetThreadpoolTimer
0x180002ff2  mov     edx, 1; fCancelPendingCallbacks
0x180002ff7  mov     rcx, rbx; pti
0x180002ffa  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003000  mov     rcx, rbx; pti
0x180003003  call    cs:__imp_CloseThreadpoolTimer
0x180003009  mov     rbx, [rdi+30h]
0x18000300d  test    rbx, rbx
0x180003010  jz      short loc_18000303A
0x180003012  xor     r9d, r9d; msWindowLength
0x180003015  xor     r8d, r8d; msPeriod
0x180003018  xor     edx, edx; pftDueTime
0x18000301a  mov     rcx, rbx; pti
0x18000301d  call    cs:__imp_SetThreadpoolTimer
0x180003023  mov     edx, 1; fCancelPendingCallbacks
0x180003028  mov     rcx, rbx; pti
0x18000302b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003031  mov     rcx, rbx; pti
0x180003034  call    cs:__imp_CloseThreadpoolTimer
0x18000303a  mov     rcx, [rdi+10h]; lpMem
0x18000303e  test    rcx, rcx
0x180003041  jz      short loc_180003048
0x180003043  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180003048  mov     rbx, [rsp+28h+arg_0]
0x18000304d  mov     rsi, [rsp+28h+arg_8]
0x180003052  add     rsp, 20h
0x180003056  pop     rdi
0x180003057  retn
```
