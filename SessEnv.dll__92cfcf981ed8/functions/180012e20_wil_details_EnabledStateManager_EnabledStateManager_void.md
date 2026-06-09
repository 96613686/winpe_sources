# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180012e20`
- end: `0x180012f4b`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `299`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18005c2a0`

## callees

- `0x1800128a4`
- `0x180012e20`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012e6b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012e6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012eea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012f0b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012eea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012f0b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012edc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012efd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012edc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012efd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012e63`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012f3c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012e63`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012f3c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180012e5a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180012f33`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180012e5a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180012f33`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012e4c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012f25`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012e4c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012f25`

## pseudocode

```c
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
  v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( *((_QWORD *)this + 13) )
  {
    if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
    {
      v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
      if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
        goto LABEL_9;
      v4 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    }
    v4();
    v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  }
  v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
LABEL_9:
  if ( !*((_QWORD *)this + 12) )
    goto LABEL_14;
  if ( !v4 )
  {
    if ( !v5 )
      goto LABEL_14;
    v4 = (void (*)(void))v5;
  }
  v4();
LABEL_14:
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
0x180012e20  push    rbx
0x180012e22  push    rbp
0x180012e23  push    rsi
0x180012e24  push    rdi
0x180012e25  sub     rsp, 28h
0x180012e29  xor     ebp, ebp
0x180012e2b  mov     rdi, rcx
0x180012e2e  mov     [rcx], ebp
0x180012e30  mov     rsi, [rcx+10h]
0x180012e34  test    rsi, rsi
0x180012e37  jz      short loc_180012E71
0x180012e39  call    cs:__imp_GetLastError
0x180012e3f  xor     r9d, r9d; msWindowLength
0x180012e42  xor     r8d, r8d; msPeriod
0x180012e45  xor     edx, edx; pftDueTime
0x180012e47  mov     rcx, rsi; pti
0x180012e4a  mov     ebx, eax
0x180012e4c  call    cs:__imp_SetThreadpoolTimer
0x180012e52  mov     edx, 1; fCancelPendingCallbacks
0x180012e57  mov     rcx, rsi; pti
0x180012e5a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180012e60  mov     rcx, rsi; pti
0x180012e63  call    cs:__imp_CloseThreadpoolTimer
0x180012e69  mov     ecx, ebx; dwErrCode
0x180012e6b  call    cs:__imp_SetLastError
0x180012e71  mov     rcx, rdi; this
0x180012e74  mov     [rdi+10h], rbp
0x180012e78  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180012e7d  mov     rcx, [rdi+68h]
0x180012e81  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180012e88  test    rcx, rcx
0x180012e8b  jz      short loc_180012EAD
0x180012e8d  test    rax, rax
0x180012e90  jnz     short loc_180012EA1
0x180012e92  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180012e99  test    rdx, rdx
0x180012e9c  jz      short loc_180012EB4
0x180012e9e  mov     rax, rdx
0x180012ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ea6  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180012ead  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180012eb4  mov     rcx, [rdi+60h]
0x180012eb8  test    rcx, rcx
0x180012ebb  jz      short loc_180012ECF
0x180012ebd  test    rax, rax
0x180012ec0  jnz     short loc_180012ECA
0x180012ec2  test    rdx, rdx
0x180012ec5  jz      short loc_180012ECF
0x180012ec7  mov     rax, rdx
0x180012eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ecf  mov     rbx, [rdi+58h]
0x180012ed3  mov     [rdi+58h], rbp
0x180012ed7  test    rbx, rbx
0x180012eda  jz      short loc_180012EF0
0x180012edc  call    cs:__imp_GetProcessHeap
0x180012ee2  mov     r8, rbx; lpMem
0x180012ee5  xor     edx, edx; dwFlags
0x180012ee7  mov     rcx, rax; hHeap
0x180012eea  call    cs:__imp_HeapFree
0x180012ef0  mov     rbx, [rdi+38h]
0x180012ef4  mov     [rdi+38h], rbp
0x180012ef8  test    rbx, rbx
0x180012efb  jz      short loc_180012F11
0x180012efd  call    cs:__imp_GetProcessHeap
0x180012f03  mov     r8, rbx; lpMem
0x180012f06  xor     edx, edx; dwFlags
0x180012f08  mov     rcx, rax; hHeap
0x180012f0b  call    cs:__imp_HeapFree
0x180012f11  mov     rbx, [rdi+10h]
0x180012f15  test    rbx, rbx
0x180012f18  jz      short loc_180012F42
0x180012f1a  xor     r9d, r9d; msWindowLength
0x180012f1d  xor     r8d, r8d; msPeriod
0x180012f20  xor     edx, edx; pftDueTime
0x180012f22  mov     rcx, rbx; pti
0x180012f25  call    cs:__imp_SetThreadpoolTimer
0x180012f2b  mov     edx, 1; fCancelPendingCallbacks
0x180012f30  mov     rcx, rbx; pti
0x180012f33  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180012f39  mov     rcx, rbx; pti
0x180012f3c  call    cs:__imp_CloseThreadpoolTimer
0x180012f42  add     rsp, 28h
0x180012f46  pop     rdi
0x180012f47  pop     rsi
0x180012f48  pop     rbp
0x180012f49  pop     rbx
0x180012f4a  retn
```
