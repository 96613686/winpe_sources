# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18001307c`
- end: `0x180013257`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `475`
- prototype: `void __fastcall(wil::details::FeatureStateManager *this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800299a0`

## callees

- `0x180012b00`
- `0x18001307c`
- `0x18001aac8`
- `0x18001cc80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001318e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800131cf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001318e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800131cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013148`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013185`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800131c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013148`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013185`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800131c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001313a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013177`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800131b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001313a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013177`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800131b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800130cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013115`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800130cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001309a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800130e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001309a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800130e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800130c4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001310d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180013200`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180013231`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800130c4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001310d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180013200`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180013231`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800130ad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800130f6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800131e9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001321a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800130ad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800130f6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800131e9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001321a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800130bb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013104`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800131f7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013228`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800130bb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013104`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800131f7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013228`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(
        wil::details::FeatureStateManager *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *a2)
{
  struct _TP_TIMER *v3; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *v5; // rsi
  DWORD v6; // ebx
  void *v7; // rbx
  HANDLE ProcessHeap; // rax
  wil::details *v9; // rcx
  void *v10; // rsi
  HANDLE v11; // rax
  void *v12; // rsi
  HANDLE v13; // rax
  struct _TP_TIMER *v14; // rbx
  struct _TP_TIMER *v15; // rbx
  void *v16; // rcx

  *(_BYTE *)this = 0;
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v3 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v3, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v3, 1);
    CloseThreadpoolTimer(v3);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 6) = 0;
  v5 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v5 )
  {
    v6 = GetLastError();
    SetThreadpoolTimer(v5, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v5, 1);
    CloseThreadpoolTimer(v5);
    SetLastError(v6);
  }
  *((_QWORD *)this + 7) = 0;
  v7 = (void *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
  }
  v9 = (wil::details *)*((_QWORD *)this + 28);
  if ( v9 )
    wil::details::UnsubscribeProcessWideUsageFlush(v9, a2);
  v10 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v10 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v10);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((__int64 *)this + 18);
  v12 = (void *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v12 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v12);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v14 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v14 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 7), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v14, 1);
    CloseThreadpoolTimer(v14);
  }
  v15 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v15 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 6), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v15, 1);
    CloseThreadpoolTimer(v15);
  }
  v16 = (void *)*((_QWORD *)this + 2);
  if ( v16 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v16);
}

```

## disassembly

```asm
0x18001307c  mov     [rsp+arg_0], rbx
0x180013081  mov     [rsp+arg_8], rsi
0x180013086  push    rdi
0x180013087  sub     rsp, 20h
0x18001308b  mov     rdi, rcx
0x18001308e  mov     byte ptr [rcx], 0
0x180013091  mov     rsi, [rcx+30h]
0x180013095  test    rsi, rsi
0x180013098  jz      short loc_1800130D2
0x18001309a  call    cs:__imp_GetLastError
0x1800130a0  mov     ebx, eax
0x1800130a2  xor     r9d, r9d; msWindowLength
0x1800130a5  xor     r8d, r8d; msPeriod
0x1800130a8  xor     edx, edx; pftDueTime
0x1800130aa  mov     rcx, rsi; pti
0x1800130ad  call    cs:__imp_SetThreadpoolTimer
0x1800130b3  mov     edx, 1; fCancelPendingCallbacks
0x1800130b8  mov     rcx, rsi; pti
0x1800130bb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800130c1  mov     rcx, rsi; pti
0x1800130c4  call    cs:__imp_CloseThreadpoolTimer
0x1800130ca  mov     ecx, ebx; dwErrCode
0x1800130cc  call    cs:__imp_SetLastError
0x1800130d2  mov     qword ptr [rdi+30h], 0
0x1800130da  mov     rsi, [rdi+38h]
0x1800130de  test    rsi, rsi
0x1800130e1  jz      short loc_18001311B
0x1800130e3  call    cs:__imp_GetLastError
0x1800130e9  mov     ebx, eax
0x1800130eb  xor     r9d, r9d; msWindowLength
0x1800130ee  xor     r8d, r8d; msPeriod
0x1800130f1  xor     edx, edx; pftDueTime
0x1800130f3  mov     rcx, rsi; pti
0x1800130f6  call    cs:__imp_SetThreadpoolTimer
0x1800130fc  mov     edx, 1; fCancelPendingCallbacks
0x180013101  mov     rcx, rsi; pti
0x180013104  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001310a  mov     rcx, rsi; pti
0x18001310d  call    cs:__imp_CloseThreadpoolTimer
0x180013113  mov     ecx, ebx; dwErrCode
0x180013115  call    cs:__imp_SetLastError
0x18001311b  mov     qword ptr [rdi+38h], 0
0x180013123  mov     rbx, [rdi+100h]
0x18001312a  mov     qword ptr [rdi+100h], 0
0x180013135  test    rbx, rbx
0x180013138  jz      short loc_18001314E
0x18001313a  call    cs:__imp_GetProcessHeap
0x180013140  mov     rcx, rax; hHeap
0x180013143  mov     r8, rbx; lpMem
0x180013146  xor     edx, edx; dwFlags
0x180013148  call    cs:__imp_HeapFree
0x18001314e  mov     rcx, [rdi+0E0h]; this
0x180013155  test    rcx, rcx
0x180013158  jz      short loc_18001315F
0x18001315a  call    ?UnsubscribeProcessWideUsageFlush@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::UnsubscribeProcessWideUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18001315f  lea     rbx, [rdi+98h]
0x180013166  mov     rsi, [rbx+40h]
0x18001316a  mov     qword ptr [rbx+40h], 0
0x180013172  test    rsi, rsi
0x180013175  jz      short loc_18001318B
0x180013177  call    cs:__imp_GetProcessHeap
0x18001317d  mov     rcx, rax; hHeap
0x180013180  mov     r8, rsi; lpMem
0x180013183  xor     edx, edx; dwFlags
0x180013185  call    cs:__imp_HeapFree
0x18001318b  mov     rcx, rbx; lpCriticalSection
0x18001318e  call    cs:__imp_DeleteCriticalSection
0x180013194  lea     rcx, [rdi+90h]
0x18001319b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800131a0  mov     rsi, [rdi+88h]
0x1800131a7  mov     qword ptr [rdi+88h], 0
0x1800131b2  test    rsi, rsi
0x1800131b5  jz      short loc_1800131CB
0x1800131b7  call    cs:__imp_GetProcessHeap
0x1800131bd  mov     rcx, rax; hHeap
0x1800131c0  mov     r8, rsi; lpMem
0x1800131c3  xor     edx, edx; dwFlags
0x1800131c5  call    cs:__imp_HeapFree
0x1800131cb  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800131cf  call    cs:__imp_DeleteCriticalSection
0x1800131d5  mov     rbx, [rdi+38h]
0x1800131d9  test    rbx, rbx
0x1800131dc  jz      short loc_180013206
0x1800131de  xor     r9d, r9d; msWindowLength
0x1800131e1  xor     r8d, r8d; msPeriod
0x1800131e4  xor     edx, edx; pftDueTime
0x1800131e6  mov     rcx, rbx; pti
0x1800131e9  call    cs:__imp_SetThreadpoolTimer
0x1800131ef  mov     edx, 1; fCancelPendingCallbacks
0x1800131f4  mov     rcx, rbx; pti
0x1800131f7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800131fd  mov     rcx, rbx; pti
0x180013200  call    cs:__imp_CloseThreadpoolTimer
0x180013206  mov     rbx, [rdi+30h]
0x18001320a  test    rbx, rbx
0x18001320d  jz      short loc_180013238
0x18001320f  xor     r9d, r9d; msWindowLength
0x180013212  xor     r8d, r8d; msPeriod
0x180013215  xor     edx, edx; pftDueTime
0x180013217  mov     rcx, rbx; pti
0x18001321a  call    cs:__imp_SetThreadpoolTimer
0x180013220  mov     edx, 1; fCancelPendingCallbacks
0x180013225  mov     rcx, rbx; pti
0x180013228  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001322e  mov     rcx, rbx; pti
0x180013231  call    cs:__imp_CloseThreadpoolTimer
0x180013237  nop
0x180013238  mov     rcx, [rdi+10h]; lpMem
0x18001323c  test    rcx, rcx
0x18001323f  jz      short loc_180013247
0x180013241  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180013246  nop
0x180013247  mov     rbx, [rsp+28h+arg_0]
0x18001324c  mov     rsi, [rsp+28h+arg_8]
0x180013251  add     rsp, 20h
0x180013255  pop     rdi
0x180013256  retn
```
