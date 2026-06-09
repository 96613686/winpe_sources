# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18000ba88`
- end: `0x18000bbe0`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180063630`

## callees

- `0x18000ba88`
- `0x180016c00`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bb98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bb65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bb8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bb65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bb8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000baa9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000baa9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000badb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000badb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000bad3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000bbc9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000bad3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000bbc9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000babc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bbb2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000babc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bbb2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000baca`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000bbc0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000baca`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000bbc0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnabledStateManager::~EnabledStateManager(wil::details::EnabledStateManager *this)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx
  void (*v4)(void); // rax
  __int64 v5; // rdx
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  void *v8; // rbx
  HANDLE v9; // rax
  struct _TP_TIMER *v10; // rbx

  *(_DWORD *)this = 0;
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 2) = 0;
  wil::details::EnabledStateManager::ProcessShutdown(this);
  if ( !*((_QWORD *)this + 13) )
  {
    v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_10;
  }
  v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_10;
    v4 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  }
  v4();
  v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_10:
  if ( !*((_QWORD *)this + 12) )
    goto LABEL_15;
  if ( !v4 )
  {
    if ( !v5 )
      goto LABEL_15;
    v4 = (void (*)(void))v5;
  }
  v4();
LABEL_15:
  v6 = (void *)*((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  v8 = (void *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v8 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v8);
  }
  v10 = (struct _TP_TIMER *)*((_QWORD *)this + 2);
  if ( v10 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 2), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v10, 1);
    CloseThreadpoolTimer(v10);
  }
}

```

## disassembly

```asm
0x18000ba88  mov     [rsp+arg_0], rbx
0x18000ba8d  mov     [rsp+arg_8], rsi
0x18000ba92  push    rdi
0x18000ba93  sub     rsp, 20h
0x18000ba97  mov     rdi, rcx
0x18000ba9a  mov     dword ptr [rcx], 0
0x18000baa0  mov     rsi, [rcx+10h]
0x18000baa4  test    rsi, rsi
0x18000baa7  jz      short loc_18000BAE1
0x18000baa9  call    cs:__imp_GetLastError
0x18000baaf  mov     ebx, eax
0x18000bab1  xor     r9d, r9d; msWindowLength
0x18000bab4  xor     r8d, r8d; msPeriod
0x18000bab7  xor     edx, edx; pftDueTime
0x18000bab9  mov     rcx, rsi; pti
0x18000babc  call    cs:__imp_SetThreadpoolTimer
0x18000bac2  mov     edx, 1; fCancelPendingCallbacks
0x18000bac7  mov     rcx, rsi; pti
0x18000baca  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000bad0  mov     rcx, rsi; pti
0x18000bad3  call    cs:__imp_CloseThreadpoolTimer
0x18000bad9  mov     ecx, ebx; dwErrCode
0x18000badb  call    cs:__imp_SetLastError
0x18000bae1  mov     qword ptr [rdi+10h], 0
0x18000bae9  mov     rcx, rdi; this
0x18000baec  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000baf1  mov     rcx, [rdi+68h]
0x18000baf5  test    rcx, rcx
0x18000baf8  jz      short loc_18000BB2A
0x18000bafa  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000bb01  test    rax, rax
0x18000bb04  jnz     short loc_18000BB15
0x18000bb06  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000bb0d  test    rdx, rdx
0x18000bb10  jz      short loc_18000BB28
0x18000bb12  mov     rax, rdx
0x18000bb15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb1a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000bb21  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000bb28  jmp     short loc_18000BB38
0x18000bb2a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000bb31  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000bb38  mov     rcx, [rdi+60h]
0x18000bb3c  test    rcx, rcx
0x18000bb3f  jz      short loc_18000BB54
0x18000bb41  test    rax, rax
0x18000bb44  jnz     short loc_18000BB4E
0x18000bb46  test    rdx, rdx
0x18000bb49  jz      short loc_18000BB54
0x18000bb4b  mov     rax, rdx
0x18000bb4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb53  nop
0x18000bb54  mov     rbx, [rdi+58h]
0x18000bb58  mov     qword ptr [rdi+58h], 0
0x18000bb60  test    rbx, rbx
0x18000bb63  jz      short loc_18000BB79
0x18000bb65  call    cs:__imp_GetProcessHeap
0x18000bb6b  mov     rcx, rax; hHeap
0x18000bb6e  mov     r8, rbx; lpMem
0x18000bb71  xor     edx, edx; dwFlags
0x18000bb73  call    cs:__imp_HeapFree
0x18000bb79  mov     rbx, [rdi+38h]
0x18000bb7d  mov     qword ptr [rdi+38h], 0
0x18000bb85  test    rbx, rbx
0x18000bb88  jz      short loc_18000BB9E
0x18000bb8a  call    cs:__imp_GetProcessHeap
0x18000bb90  mov     rcx, rax; hHeap
0x18000bb93  mov     r8, rbx; lpMem
0x18000bb96  xor     edx, edx; dwFlags
0x18000bb98  call    cs:__imp_HeapFree
0x18000bb9e  mov     rbx, [rdi+10h]
0x18000bba2  test    rbx, rbx
0x18000bba5  jz      short loc_18000BBD0
0x18000bba7  xor     r9d, r9d; msWindowLength
0x18000bbaa  xor     r8d, r8d; msPeriod
0x18000bbad  xor     edx, edx; pftDueTime
0x18000bbaf  mov     rcx, rbx; pti
0x18000bbb2  call    cs:__imp_SetThreadpoolTimer
0x18000bbb8  mov     edx, 1; fCancelPendingCallbacks
0x18000bbbd  mov     rcx, rbx; pti
0x18000bbc0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000bbc6  mov     rcx, rbx; pti
0x18000bbc9  call    cs:__imp_CloseThreadpoolTimer
0x18000bbcf  nop
0x18000bbd0  mov     rbx, [rsp+28h+arg_0]
0x18000bbd5  mov     rsi, [rsp+28h+arg_8]
0x18000bbda  add     rsp, 20h
0x18000bbde  pop     rdi
0x18000bbdf  retn
```
