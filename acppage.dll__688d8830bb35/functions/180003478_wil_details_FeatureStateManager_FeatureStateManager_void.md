# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180003478`
- end: `0x180003664`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180016840`

## callees

- `0x18000313c`
- `0x180003478`
- `0x1800070b4`
- `0x180007c74`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180003544`
- `KERNEL32!HeapFree` at `0x180003594`
- `KERNEL32!HeapFree` at `0x1800035d4`
- `KERNEL32!HeapFree` at `0x180003544`
- `KERNEL32!HeapFree` at `0x180003594`
- `KERNEL32!HeapFree` at `0x1800035d4`
- `KERNEL32!SetLastError` at `0x1800034c8`
- `KERNEL32!SetLastError` at `0x180003511`
- `KERNEL32!SetLastError` at `0x1800034c8`
- `KERNEL32!SetLastError` at `0x180003511`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800034b7`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003500`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003606`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003637`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800034b7`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003500`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003606`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003637`
- `KERNEL32!GetLastError` at `0x180003496`
- `KERNEL32!GetLastError` at `0x1800034df`
- `KERNEL32!GetLastError` at `0x180003496`
- `KERNEL32!GetLastError` at `0x1800034df`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800034c0`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003509`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000360f`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003640`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800034c0`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003509`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000360f`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003640`
- `KERNEL32!SetThreadpoolTimer` at `0x1800034a9`
- `KERNEL32!SetThreadpoolTimer` at `0x1800034f2`
- `KERNEL32!SetThreadpoolTimer` at `0x1800035f8`
- `KERNEL32!SetThreadpoolTimer` at `0x180003629`
- `KERNEL32!SetThreadpoolTimer` at `0x1800034a9`
- `KERNEL32!SetThreadpoolTimer` at `0x1800034f2`
- `KERNEL32!SetThreadpoolTimer` at `0x1800035f8`
- `KERNEL32!SetThreadpoolTimer` at `0x180003629`
- `KERNEL32!DeleteCriticalSection` at `0x18000359d`
- `KERNEL32!DeleteCriticalSection` at `0x1800035de`
- `KERNEL32!DeleteCriticalSection` at `0x18000359d`
- `KERNEL32!DeleteCriticalSection` at `0x1800035de`
- `KERNEL32!GetProcessHeap` at `0x180003536`
- `KERNEL32!GetProcessHeap` at `0x180003586`
- `KERNEL32!GetProcessHeap` at `0x1800035c6`
- `KERNEL32!GetProcessHeap` at `0x180003536`
- `KERNEL32!GetProcessHeap` at `0x180003586`
- `KERNEL32!GetProcessHeap` at `0x1800035c6`

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
  if ( v8 && qword_1800201C8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800201C8[25], qword_1800201C8, v8);
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
0x180003478  mov     [rsp+arg_0], rbx
0x18000347d  mov     [rsp+arg_8], rsi
0x180003482  push    rdi
0x180003483  sub     rsp, 20h
0x180003487  mov     byte ptr [rcx], 0
0x18000348a  mov     rdi, rcx
0x18000348d  mov     rsi, [rcx+30h]
0x180003491  test    rsi, rsi
0x180003494  jz      short loc_1800034CE
0x180003496  call    cs:__imp_GetLastError
0x18000349c  xor     r9d, r9d; msWindowLength
0x18000349f  xor     r8d, r8d; msPeriod
0x1800034a2  xor     edx, edx; pftDueTime
0x1800034a4  mov     rcx, rsi; pti
0x1800034a7  mov     ebx, eax
0x1800034a9  call    cs:__imp_SetThreadpoolTimer
0x1800034af  mov     edx, 1; fCancelPendingCallbacks
0x1800034b4  mov     rcx, rsi; pti
0x1800034b7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800034bd  mov     rcx, rsi; pti
0x1800034c0  call    cs:__imp_CloseThreadpoolTimer
0x1800034c6  mov     ecx, ebx; dwErrCode
0x1800034c8  call    cs:__imp_SetLastError
0x1800034ce  mov     qword ptr [rdi+30h], 0
0x1800034d6  mov     rsi, [rdi+38h]
0x1800034da  test    rsi, rsi
0x1800034dd  jz      short loc_180003517
0x1800034df  call    cs:__imp_GetLastError
0x1800034e5  xor     r9d, r9d; msWindowLength
0x1800034e8  xor     r8d, r8d; msPeriod
0x1800034eb  xor     edx, edx; pftDueTime
0x1800034ed  mov     rcx, rsi; pti
0x1800034f0  mov     ebx, eax
0x1800034f2  call    cs:__imp_SetThreadpoolTimer
0x1800034f8  mov     edx, 1; fCancelPendingCallbacks
0x1800034fd  mov     rcx, rsi; pti
0x180003500  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003506  mov     rcx, rsi; pti
0x180003509  call    cs:__imp_CloseThreadpoolTimer
0x18000350f  mov     ecx, ebx; dwErrCode
0x180003511  call    cs:__imp_SetLastError
0x180003517  mov     qword ptr [rdi+38h], 0
0x18000351f  mov     rbx, [rdi+100h]
0x180003526  mov     qword ptr [rdi+100h], 0
0x180003531  test    rbx, rbx
0x180003534  jz      short loc_18000354A
0x180003536  call    cs:__imp_GetProcessHeap
0x18000353c  mov     r8, rbx; lpMem
0x18000353f  xor     edx, edx; dwFlags
0x180003541  mov     rcx, rax; hHeap
0x180003544  call    cs:__imp_HeapFree
0x18000354a  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180003551  test    r8, r8
0x180003554  jz      short loc_18000356E
0x180003556  mov     rdx, cs:qword_1800201C8; SRWLock
0x18000355d  test    rdx, rdx
0x180003560  jz      short loc_18000356E
0x180003562  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180003569  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000356e  lea     rbx, [rdi+98h]
0x180003575  mov     rsi, [rbx+40h]
0x180003579  mov     qword ptr [rbx+40h], 0
0x180003581  test    rsi, rsi
0x180003584  jz      short loc_18000359A
0x180003586  call    cs:__imp_GetProcessHeap
0x18000358c  mov     r8, rsi; lpMem
0x18000358f  xor     edx, edx; dwFlags
0x180003591  mov     rcx, rax; hHeap
0x180003594  call    cs:__imp_HeapFree
0x18000359a  mov     rcx, rbx; lpCriticalSection
0x18000359d  call    cs:__imp_DeleteCriticalSection
0x1800035a3  lea     rcx, [rdi+90h]
0x1800035aa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800035af  mov     rsi, [rdi+88h]
0x1800035b6  mov     qword ptr [rdi+88h], 0
0x1800035c1  test    rsi, rsi
0x1800035c4  jz      short loc_1800035DA
0x1800035c6  call    cs:__imp_GetProcessHeap
0x1800035cc  mov     r8, rsi; lpMem
0x1800035cf  xor     edx, edx; dwFlags
0x1800035d1  mov     rcx, rax; hHeap
0x1800035d4  call    cs:__imp_HeapFree
0x1800035da  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800035de  call    cs:__imp_DeleteCriticalSection
0x1800035e4  mov     rbx, [rdi+38h]
0x1800035e8  test    rbx, rbx
0x1800035eb  jz      short loc_180003615
0x1800035ed  xor     r9d, r9d; msWindowLength
0x1800035f0  xor     r8d, r8d; msPeriod
0x1800035f3  xor     edx, edx; pftDueTime
0x1800035f5  mov     rcx, rbx; pti
0x1800035f8  call    cs:__imp_SetThreadpoolTimer
0x1800035fe  mov     edx, 1; fCancelPendingCallbacks
0x180003603  mov     rcx, rbx; pti
0x180003606  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000360c  mov     rcx, rbx; pti
0x18000360f  call    cs:__imp_CloseThreadpoolTimer
0x180003615  mov     rbx, [rdi+30h]
0x180003619  test    rbx, rbx
0x18000361c  jz      short loc_180003646
0x18000361e  xor     r9d, r9d; msWindowLength
0x180003621  xor     r8d, r8d; msPeriod
0x180003624  xor     edx, edx; pftDueTime
0x180003626  mov     rcx, rbx; pti
0x180003629  call    cs:__imp_SetThreadpoolTimer
0x18000362f  mov     edx, 1; fCancelPendingCallbacks
0x180003634  mov     rcx, rbx; pti
0x180003637  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000363d  mov     rcx, rbx; pti
0x180003640  call    cs:__imp_CloseThreadpoolTimer
0x180003646  mov     rcx, [rdi+10h]; lpMem
0x18000364a  test    rcx, rcx
0x18000364d  jz      short loc_180003654
0x18000364f  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180003654  mov     rbx, [rsp+28h+arg_0]
0x180003659  mov     rsi, [rsp+28h+arg_8]
0x18000365e  add     rsp, 20h
0x180003662  pop     rdi
0x180003663  retn
```
