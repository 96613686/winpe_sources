# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180038bb4`
- end: `0x180038d0c`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18006eca0`

## callees

- `0x180038bb4`
- `0x18003a274`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038c91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038cb6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038c91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038cb6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038c9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038cc4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038c9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038cc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038bd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038bd5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038c07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038c07`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180038be8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180038cde`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180038be8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180038cde`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180038bf6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180038cec`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180038bf6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180038cec`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180038bff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180038cf5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180038bff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180038cf5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180038bb4  mov     [rsp+arg_0], rbx
0x180038bb9  mov     [rsp+arg_8], rsi
0x180038bbe  push    rdi
0x180038bbf  sub     rsp, 20h
0x180038bc3  mov     rdi, rcx
0x180038bc6  mov     dword ptr [rcx], 0
0x180038bcc  mov     rsi, [rcx+10h]
0x180038bd0  test    rsi, rsi
0x180038bd3  jz      short loc_180038C0D
0x180038bd5  call    cs:__imp_GetLastError
0x180038bdb  mov     ebx, eax
0x180038bdd  xor     r9d, r9d; msWindowLength
0x180038be0  xor     r8d, r8d; msPeriod
0x180038be3  xor     edx, edx; pftDueTime
0x180038be5  mov     rcx, rsi; pti
0x180038be8  call    cs:__imp_SetThreadpoolTimer
0x180038bee  mov     edx, 1; fCancelPendingCallbacks
0x180038bf3  mov     rcx, rsi; pti
0x180038bf6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180038bfc  mov     rcx, rsi; pti
0x180038bff  call    cs:__imp_CloseThreadpoolTimer
0x180038c05  mov     ecx, ebx; dwErrCode
0x180038c07  call    cs:__imp_SetLastError
0x180038c0d  mov     qword ptr [rdi+10h], 0
0x180038c15  mov     rcx, rdi; this
0x180038c18  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180038c1d  mov     rcx, [rdi+68h]
0x180038c21  test    rcx, rcx
0x180038c24  jz      short loc_180038C56
0x180038c26  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180038c2d  test    rax, rax
0x180038c30  jnz     short loc_180038C41
0x180038c32  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180038c39  test    rdx, rdx
0x180038c3c  jz      short loc_180038C54
0x180038c3e  mov     rax, rdx
0x180038c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c46  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180038c4d  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180038c54  jmp     short loc_180038C64
0x180038c56  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180038c5d  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180038c64  mov     rcx, [rdi+60h]
0x180038c68  test    rcx, rcx
0x180038c6b  jz      short loc_180038C80
0x180038c6d  test    rax, rax
0x180038c70  jnz     short loc_180038C7A
0x180038c72  test    rdx, rdx
0x180038c75  jz      short loc_180038C80
0x180038c77  mov     rax, rdx
0x180038c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c7f  nop
0x180038c80  mov     rbx, [rdi+58h]
0x180038c84  mov     qword ptr [rdi+58h], 0
0x180038c8c  test    rbx, rbx
0x180038c8f  jz      short loc_180038CA5
0x180038c91  call    cs:__imp_GetProcessHeap
0x180038c97  mov     rcx, rax; hHeap
0x180038c9a  mov     r8, rbx; lpMem
0x180038c9d  xor     edx, edx; dwFlags
0x180038c9f  call    cs:__imp_HeapFree
0x180038ca5  mov     rbx, [rdi+38h]
0x180038ca9  mov     qword ptr [rdi+38h], 0
0x180038cb1  test    rbx, rbx
0x180038cb4  jz      short loc_180038CCA
0x180038cb6  call    cs:__imp_GetProcessHeap
0x180038cbc  mov     rcx, rax; hHeap
0x180038cbf  mov     r8, rbx; lpMem
0x180038cc2  xor     edx, edx; dwFlags
0x180038cc4  call    cs:__imp_HeapFree
0x180038cca  mov     rbx, [rdi+10h]
0x180038cce  test    rbx, rbx
0x180038cd1  jz      short loc_180038CFC
0x180038cd3  xor     r9d, r9d; msWindowLength
0x180038cd6  xor     r8d, r8d; msPeriod
0x180038cd9  xor     edx, edx; pftDueTime
0x180038cdb  mov     rcx, rbx; pti
0x180038cde  call    cs:__imp_SetThreadpoolTimer
0x180038ce4  mov     edx, 1; fCancelPendingCallbacks
0x180038ce9  mov     rcx, rbx; pti
0x180038cec  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180038cf2  mov     rcx, rbx; pti
0x180038cf5  call    cs:__imp_CloseThreadpoolTimer
0x180038cfb  nop
0x180038cfc  mov     rbx, [rsp+28h+arg_0]
0x180038d01  mov     rsi, [rsp+28h+arg_8]
0x180038d06  add     rsp, 20h
0x180038d0a  pop     rdi
0x180038d0b  retn
```
