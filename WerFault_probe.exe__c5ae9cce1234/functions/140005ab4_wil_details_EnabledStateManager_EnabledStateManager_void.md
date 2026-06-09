# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x140005ab4`
- end: `0x140005c0c`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14005c7c0`

## callees

- `0x140005ab4`
- `0x140008d4c`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005b9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005bc4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005b9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005bc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005b91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005bb6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005b91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005bb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005ad5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005ad5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005b07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005b07`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005aff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005bf5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005aff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005bf5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005af6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005bec`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005af6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005bec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005ae8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005bde`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005ae8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005bde`

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
0x140005ab4  mov     [rsp+arg_0], rbx
0x140005ab9  mov     [rsp+arg_8], rsi
0x140005abe  push    rdi
0x140005abf  sub     rsp, 20h
0x140005ac3  mov     rdi, rcx
0x140005ac6  mov     dword ptr [rcx], 0
0x140005acc  mov     rsi, [rcx+10h]
0x140005ad0  test    rsi, rsi
0x140005ad3  jz      short loc_140005B0D
0x140005ad5  call    cs:__imp_GetLastError
0x140005adb  mov     ebx, eax
0x140005add  xor     r9d, r9d; msWindowLength
0x140005ae0  xor     r8d, r8d; msPeriod
0x140005ae3  xor     edx, edx; pftDueTime
0x140005ae5  mov     rcx, rsi; pti
0x140005ae8  call    cs:__imp_SetThreadpoolTimer
0x140005aee  mov     edx, 1; fCancelPendingCallbacks
0x140005af3  mov     rcx, rsi; pti
0x140005af6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005afc  mov     rcx, rsi; pti
0x140005aff  call    cs:__imp_CloseThreadpoolTimer
0x140005b05  mov     ecx, ebx; dwErrCode
0x140005b07  call    cs:__imp_SetLastError
0x140005b0d  mov     qword ptr [rdi+10h], 0
0x140005b15  mov     rcx, rdi; this
0x140005b18  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x140005b1d  mov     rcx, [rdi+68h]
0x140005b21  test    rcx, rcx
0x140005b24  jz      short loc_140005B56
0x140005b26  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140005b2d  test    rax, rax
0x140005b30  jnz     short loc_140005B41
0x140005b32  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140005b39  test    rdx, rdx
0x140005b3c  jz      short loc_140005B54
0x140005b3e  mov     rax, rdx
0x140005b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b46  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140005b4d  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140005b54  jmp     short loc_140005B64
0x140005b56  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140005b5d  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140005b64  mov     rcx, [rdi+60h]
0x140005b68  test    rcx, rcx
0x140005b6b  jz      short loc_140005B80
0x140005b6d  test    rax, rax
0x140005b70  jnz     short loc_140005B7A
0x140005b72  test    rdx, rdx
0x140005b75  jz      short loc_140005B80
0x140005b77  mov     rax, rdx
0x140005b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b7f  nop
0x140005b80  mov     rbx, [rdi+58h]
0x140005b84  mov     qword ptr [rdi+58h], 0
0x140005b8c  test    rbx, rbx
0x140005b8f  jz      short loc_140005BA5
0x140005b91  call    cs:__imp_GetProcessHeap
0x140005b97  mov     rcx, rax; hHeap
0x140005b9a  mov     r8, rbx; lpMem
0x140005b9d  xor     edx, edx; dwFlags
0x140005b9f  call    cs:__imp_HeapFree
0x140005ba5  mov     rbx, [rdi+38h]
0x140005ba9  mov     qword ptr [rdi+38h], 0
0x140005bb1  test    rbx, rbx
0x140005bb4  jz      short loc_140005BCA
0x140005bb6  call    cs:__imp_GetProcessHeap
0x140005bbc  mov     rcx, rax; hHeap
0x140005bbf  mov     r8, rbx; lpMem
0x140005bc2  xor     edx, edx; dwFlags
0x140005bc4  call    cs:__imp_HeapFree
0x140005bca  mov     rbx, [rdi+10h]
0x140005bce  test    rbx, rbx
0x140005bd1  jz      short loc_140005BFC
0x140005bd3  xor     r9d, r9d; msWindowLength
0x140005bd6  xor     r8d, r8d; msPeriod
0x140005bd9  xor     edx, edx; pftDueTime
0x140005bdb  mov     rcx, rbx; pti
0x140005bde  call    cs:__imp_SetThreadpoolTimer
0x140005be4  mov     edx, 1; fCancelPendingCallbacks
0x140005be9  mov     rcx, rbx; pti
0x140005bec  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005bf2  mov     rcx, rbx; pti
0x140005bf5  call    cs:__imp_CloseThreadpoolTimer
0x140005bfb  nop
0x140005bfc  mov     rbx, [rsp+28h+arg_0]
0x140005c01  mov     rsi, [rsp+28h+arg_8]
0x140005c06  add     rsp, 20h
0x140005c0a  pop     rdi
0x140005c0b  retn
```
