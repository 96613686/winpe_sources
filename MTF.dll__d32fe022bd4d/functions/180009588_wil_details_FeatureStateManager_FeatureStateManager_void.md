# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180009588`
- end: `0x180009776`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002e150`

## callees

- `0x180009370`
- `0x180009588`
- `0x18000bd50`
- `0x18000c794`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800096ad`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800096ee`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800096ad`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800096ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009646`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009696`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800096d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009646`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009696`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800096d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009654`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800096a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800096e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009654`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800096a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800096e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800095d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009621`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800095d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009621`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800095c7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009610`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009716`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009747`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800095c7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009610`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009716`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009747`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800095b9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009602`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009708`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009739`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800095b9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009602`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009708`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009739`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800095d0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009619`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000971f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009750`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800095d0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009619`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000971f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009750`

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
  if ( v8 && qword_18003E140 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18003E140[25], qword_18003E140, v8);
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
0x180009588  mov     [rsp+arg_0], rbx
0x18000958d  mov     [rsp+arg_8], rsi
0x180009592  push    rdi
0x180009593  sub     rsp, 20h
0x180009597  mov     rdi, rcx
0x18000959a  mov     byte ptr [rcx], 0
0x18000959d  mov     rsi, [rcx+30h]
0x1800095a1  test    rsi, rsi
0x1800095a4  jz      short loc_1800095DE
0x1800095a6  call    cs:__imp_GetLastError
0x1800095ac  mov     ebx, eax
0x1800095ae  xor     r9d, r9d; msWindowLength
0x1800095b1  xor     r8d, r8d; msPeriod
0x1800095b4  xor     edx, edx; pftDueTime
0x1800095b6  mov     rcx, rsi; pti
0x1800095b9  call    cs:__imp_SetThreadpoolTimer
0x1800095bf  mov     edx, 1; fCancelPendingCallbacks
0x1800095c4  mov     rcx, rsi; pti
0x1800095c7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800095cd  mov     rcx, rsi; pti
0x1800095d0  call    cs:__imp_CloseThreadpoolTimer
0x1800095d6  mov     ecx, ebx; dwErrCode
0x1800095d8  call    cs:__imp_SetLastError
0x1800095de  mov     qword ptr [rdi+30h], 0
0x1800095e6  mov     rsi, [rdi+38h]
0x1800095ea  test    rsi, rsi
0x1800095ed  jz      short loc_180009627
0x1800095ef  call    cs:__imp_GetLastError
0x1800095f5  mov     ebx, eax
0x1800095f7  xor     r9d, r9d; msWindowLength
0x1800095fa  xor     r8d, r8d; msPeriod
0x1800095fd  xor     edx, edx; pftDueTime
0x1800095ff  mov     rcx, rsi; pti
0x180009602  call    cs:__imp_SetThreadpoolTimer
0x180009608  mov     edx, 1; fCancelPendingCallbacks
0x18000960d  mov     rcx, rsi; pti
0x180009610  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009616  mov     rcx, rsi; pti
0x180009619  call    cs:__imp_CloseThreadpoolTimer
0x18000961f  mov     ecx, ebx; dwErrCode
0x180009621  call    cs:__imp_SetLastError
0x180009627  mov     qword ptr [rdi+38h], 0
0x18000962f  mov     rbx, [rdi+100h]
0x180009636  mov     qword ptr [rdi+100h], 0
0x180009641  test    rbx, rbx
0x180009644  jz      short loc_18000965A
0x180009646  call    cs:__imp_GetProcessHeap
0x18000964c  mov     rcx, rax; hHeap
0x18000964f  mov     r8, rbx; lpMem
0x180009652  xor     edx, edx; dwFlags
0x180009654  call    cs:__imp_HeapFree
0x18000965a  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180009661  test    r8, r8
0x180009664  jz      short loc_18000967E
0x180009666  mov     rdx, cs:qword_18003E140; SRWLock
0x18000966d  test    rdx, rdx
0x180009670  jz      short loc_18000967E
0x180009672  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180009679  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000967e  lea     rbx, [rdi+98h]
0x180009685  mov     rsi, [rbx+40h]
0x180009689  mov     qword ptr [rbx+40h], 0
0x180009691  test    rsi, rsi
0x180009694  jz      short loc_1800096AA
0x180009696  call    cs:__imp_GetProcessHeap
0x18000969c  mov     rcx, rax; hHeap
0x18000969f  mov     r8, rsi; lpMem
0x1800096a2  xor     edx, edx; dwFlags
0x1800096a4  call    cs:__imp_HeapFree
0x1800096aa  mov     rcx, rbx; lpCriticalSection
0x1800096ad  call    cs:__imp_DeleteCriticalSection
0x1800096b3  lea     rcx, [rdi+90h]
0x1800096ba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800096bf  mov     rsi, [rdi+88h]
0x1800096c6  mov     qword ptr [rdi+88h], 0
0x1800096d1  test    rsi, rsi
0x1800096d4  jz      short loc_1800096EA
0x1800096d6  call    cs:__imp_GetProcessHeap
0x1800096dc  mov     rcx, rax; hHeap
0x1800096df  mov     r8, rsi; lpMem
0x1800096e2  xor     edx, edx; dwFlags
0x1800096e4  call    cs:__imp_HeapFree
0x1800096ea  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800096ee  call    cs:__imp_DeleteCriticalSection
0x1800096f4  mov     rbx, [rdi+38h]
0x1800096f8  test    rbx, rbx
0x1800096fb  jz      short loc_180009725
0x1800096fd  xor     r9d, r9d; msWindowLength
0x180009700  xor     r8d, r8d; msPeriod
0x180009703  xor     edx, edx; pftDueTime
0x180009705  mov     rcx, rbx; pti
0x180009708  call    cs:__imp_SetThreadpoolTimer
0x18000970e  mov     edx, 1; fCancelPendingCallbacks
0x180009713  mov     rcx, rbx; pti
0x180009716  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000971c  mov     rcx, rbx; pti
0x18000971f  call    cs:__imp_CloseThreadpoolTimer
0x180009725  mov     rbx, [rdi+30h]
0x180009729  test    rbx, rbx
0x18000972c  jz      short loc_180009757
0x18000972e  xor     r9d, r9d; msWindowLength
0x180009731  xor     r8d, r8d; msPeriod
0x180009734  xor     edx, edx; pftDueTime
0x180009736  mov     rcx, rbx; pti
0x180009739  call    cs:__imp_SetThreadpoolTimer
0x18000973f  mov     edx, 1; fCancelPendingCallbacks
0x180009744  mov     rcx, rbx; pti
0x180009747  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000974d  mov     rcx, rbx; pti
0x180009750  call    cs:__imp_CloseThreadpoolTimer
0x180009756  nop
0x180009757  mov     rcx, [rdi+10h]; lpMem
0x18000975b  test    rcx, rcx
0x18000975e  jz      short loc_180009766
0x180009760  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180009765  nop
0x180009766  mov     rbx, [rsp+28h+arg_0]
0x18000976b  mov     rsi, [rsp+28h+arg_8]
0x180009770  add     rsp, 20h
0x180009774  pop     rdi
0x180009775  retn
```
