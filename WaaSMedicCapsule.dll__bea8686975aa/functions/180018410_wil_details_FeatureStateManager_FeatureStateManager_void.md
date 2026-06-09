# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180018410`
- end: `0x1800185fe`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180063680`

## callees

- `0x1800182cc`
- `0x180018410`
- `0x18001a740`
- `0x18001ac48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018535`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018576`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018535`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018576`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800184dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001852c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001856c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800184dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001852c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001856c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800184ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001851e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001855e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800184ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001851e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001855e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001842e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018477`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001842e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018477`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018460`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800184a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018460`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800184a9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180018458`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800184a1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800185a7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800185d8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180018458`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800184a1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800185a7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800185d8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180018441`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001848a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180018590`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800185c1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180018441`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001848a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180018590`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800185c1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001844f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180018498`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001859e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800185cf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001844f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180018498`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001859e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800185cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  if ( v8 && qword_180097878 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180097878[25], qword_180097878, v8);
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
0x180018410  mov     [rsp+arg_0], rbx
0x180018415  mov     [rsp+arg_8], rsi
0x18001841a  push    rdi
0x18001841b  sub     rsp, 20h
0x18001841f  mov     rdi, rcx
0x180018422  mov     byte ptr [rcx], 0
0x180018425  mov     rsi, [rcx+30h]
0x180018429  test    rsi, rsi
0x18001842c  jz      short loc_180018466
0x18001842e  call    cs:__imp_GetLastError
0x180018434  mov     ebx, eax
0x180018436  xor     r9d, r9d; msWindowLength
0x180018439  xor     r8d, r8d; msPeriod
0x18001843c  xor     edx, edx; pftDueTime
0x18001843e  mov     rcx, rsi; pti
0x180018441  call    cs:__imp_SetThreadpoolTimer
0x180018447  mov     edx, 1; fCancelPendingCallbacks
0x18001844c  mov     rcx, rsi; pti
0x18001844f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180018455  mov     rcx, rsi; pti
0x180018458  call    cs:__imp_CloseThreadpoolTimer
0x18001845e  mov     ecx, ebx; dwErrCode
0x180018460  call    cs:__imp_SetLastError
0x180018466  mov     qword ptr [rdi+30h], 0
0x18001846e  mov     rsi, [rdi+38h]
0x180018472  test    rsi, rsi
0x180018475  jz      short loc_1800184AF
0x180018477  call    cs:__imp_GetLastError
0x18001847d  mov     ebx, eax
0x18001847f  xor     r9d, r9d; msWindowLength
0x180018482  xor     r8d, r8d; msPeriod
0x180018485  xor     edx, edx; pftDueTime
0x180018487  mov     rcx, rsi; pti
0x18001848a  call    cs:__imp_SetThreadpoolTimer
0x180018490  mov     edx, 1; fCancelPendingCallbacks
0x180018495  mov     rcx, rsi; pti
0x180018498  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001849e  mov     rcx, rsi; pti
0x1800184a1  call    cs:__imp_CloseThreadpoolTimer
0x1800184a7  mov     ecx, ebx; dwErrCode
0x1800184a9  call    cs:__imp_SetLastError
0x1800184af  mov     qword ptr [rdi+38h], 0
0x1800184b7  mov     rbx, [rdi+100h]
0x1800184be  mov     qword ptr [rdi+100h], 0
0x1800184c9  test    rbx, rbx
0x1800184cc  jz      short loc_1800184E2
0x1800184ce  call    cs:__imp_GetProcessHeap
0x1800184d4  mov     rcx, rax; hHeap
0x1800184d7  mov     r8, rbx; lpMem
0x1800184da  xor     edx, edx; dwFlags
0x1800184dc  call    cs:__imp_HeapFree
0x1800184e2  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800184e9  test    r8, r8
0x1800184ec  jz      short loc_180018506
0x1800184ee  mov     rdx, cs:qword_180097878; SRWLock
0x1800184f5  test    rdx, rdx
0x1800184f8  jz      short loc_180018506
0x1800184fa  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180018501  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180018506  lea     rbx, [rdi+98h]
0x18001850d  mov     rsi, [rbx+40h]
0x180018511  mov     qword ptr [rbx+40h], 0
0x180018519  test    rsi, rsi
0x18001851c  jz      short loc_180018532
0x18001851e  call    cs:__imp_GetProcessHeap
0x180018524  mov     rcx, rax; hHeap
0x180018527  mov     r8, rsi; lpMem
0x18001852a  xor     edx, edx; dwFlags
0x18001852c  call    cs:__imp_HeapFree
0x180018532  mov     rcx, rbx; lpCriticalSection
0x180018535  call    cs:__imp_DeleteCriticalSection
0x18001853b  lea     rcx, [rdi+90h]
0x180018542  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180018547  mov     rsi, [rdi+88h]
0x18001854e  mov     qword ptr [rdi+88h], 0
0x180018559  test    rsi, rsi
0x18001855c  jz      short loc_180018572
0x18001855e  call    cs:__imp_GetProcessHeap
0x180018564  mov     rcx, rax; hHeap
0x180018567  mov     r8, rsi; lpMem
0x18001856a  xor     edx, edx; dwFlags
0x18001856c  call    cs:__imp_HeapFree
0x180018572  lea     rcx, [rdi+48h]; lpCriticalSection
0x180018576  call    cs:__imp_DeleteCriticalSection
0x18001857c  mov     rbx, [rdi+38h]
0x180018580  test    rbx, rbx
0x180018583  jz      short loc_1800185AD
0x180018585  xor     r9d, r9d; msWindowLength
0x180018588  xor     r8d, r8d; msPeriod
0x18001858b  xor     edx, edx; pftDueTime
0x18001858d  mov     rcx, rbx; pti
0x180018590  call    cs:__imp_SetThreadpoolTimer
0x180018596  mov     edx, 1; fCancelPendingCallbacks
0x18001859b  mov     rcx, rbx; pti
0x18001859e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800185a4  mov     rcx, rbx; pti
0x1800185a7  call    cs:__imp_CloseThreadpoolTimer
0x1800185ad  mov     rbx, [rdi+30h]
0x1800185b1  test    rbx, rbx
0x1800185b4  jz      short loc_1800185DF
0x1800185b6  xor     r9d, r9d; msWindowLength
0x1800185b9  xor     r8d, r8d; msPeriod
0x1800185bc  xor     edx, edx; pftDueTime
0x1800185be  mov     rcx, rbx; pti
0x1800185c1  call    cs:__imp_SetThreadpoolTimer
0x1800185c7  mov     edx, 1; fCancelPendingCallbacks
0x1800185cc  mov     rcx, rbx; pti
0x1800185cf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800185d5  mov     rcx, rbx; pti
0x1800185d8  call    cs:__imp_CloseThreadpoolTimer
0x1800185de  nop
0x1800185df  mov     rcx, [rdi+10h]; lpMem
0x1800185e3  test    rcx, rcx
0x1800185e6  jz      short loc_1800185EE
0x1800185e8  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800185ed  nop
0x1800185ee  mov     rbx, [rsp+28h+arg_0]
0x1800185f3  mov     rsi, [rsp+28h+arg_8]
0x1800185f8  add     rsp, 20h
0x1800185fc  pop     rdi
0x1800185fd  retn
```
