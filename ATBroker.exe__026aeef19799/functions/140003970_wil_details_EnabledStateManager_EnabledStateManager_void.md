# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x140003970`
- end: `0x140003ab6`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `326`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400160f0`

## callees

- `0x140003970`
- `0x14000766c`
- `0x140017010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140003a4a`
- `KERNEL32!HeapFree` at `0x140003a6f`
- `KERNEL32!HeapFree` at `0x140003a4a`
- `KERNEL32!HeapFree` at `0x140003a6f`
- `KERNEL32!SetLastError` at `0x1400039c3`
- `KERNEL32!SetLastError` at `0x1400039c3`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400039b2`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140003a97`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400039b2`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140003a97`
- `KERNEL32!GetLastError` at `0x140003991`
- `KERNEL32!GetLastError` at `0x140003991`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400039bb`
- `KERNEL32!CloseThreadpoolTimer` at `0x140003aa0`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400039bb`
- `KERNEL32!CloseThreadpoolTimer` at `0x140003aa0`
- `KERNEL32!SetThreadpoolTimer` at `0x1400039a4`
- `KERNEL32!SetThreadpoolTimer` at `0x140003a89`
- `KERNEL32!SetThreadpoolTimer` at `0x1400039a4`
- `KERNEL32!SetThreadpoolTimer` at `0x140003a89`
- `KERNEL32!GetProcessHeap` at `0x140003a3c`
- `KERNEL32!GetProcessHeap` at `0x140003a61`
- `KERNEL32!GetProcessHeap` at `0x140003a3c`
- `KERNEL32!GetProcessHeap` at `0x140003a61`

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
0x140003970  mov     [rsp+arg_0], rbx
0x140003975  mov     [rsp+arg_8], rsi
0x14000397a  push    rdi
0x14000397b  sub     rsp, 20h
0x14000397f  mov     dword ptr [rcx], 0
0x140003985  mov     rdi, rcx
0x140003988  mov     rsi, [rcx+10h]
0x14000398c  test    rsi, rsi
0x14000398f  jz      short loc_1400039C9
0x140003991  call    cs:__imp_GetLastError
0x140003997  xor     r9d, r9d; msWindowLength
0x14000399a  xor     r8d, r8d; msPeriod
0x14000399d  xor     edx, edx; pftDueTime
0x14000399f  mov     rcx, rsi; pti
0x1400039a2  mov     ebx, eax
0x1400039a4  call    cs:__imp_SetThreadpoolTimer
0x1400039aa  mov     edx, 1; fCancelPendingCallbacks
0x1400039af  mov     rcx, rsi; pti
0x1400039b2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400039b8  mov     rcx, rsi; pti
0x1400039bb  call    cs:__imp_CloseThreadpoolTimer
0x1400039c1  mov     ecx, ebx; dwErrCode
0x1400039c3  call    cs:__imp_SetLastError
0x1400039c9  mov     rcx, rdi; this
0x1400039cc  mov     qword ptr [rdi+10h], 0
0x1400039d4  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1400039d9  mov     rcx, [rdi+68h]
0x1400039dd  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1400039e4  test    rcx, rcx
0x1400039e7  jz      short loc_140003A09
0x1400039e9  test    rax, rax
0x1400039ec  jnz     short loc_1400039FD
0x1400039ee  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1400039f5  test    rdx, rdx
0x1400039f8  jz      short loc_140003A10
0x1400039fa  mov     rax, rdx
0x1400039fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003a02  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140003a09  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140003a10  mov     rcx, [rdi+60h]
0x140003a14  test    rcx, rcx
0x140003a17  jz      short loc_140003A2B
0x140003a19  test    rax, rax
0x140003a1c  jnz     short loc_140003A26
0x140003a1e  test    rdx, rdx
0x140003a21  jz      short loc_140003A2B
0x140003a23  mov     rax, rdx
0x140003a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003a2b  mov     rbx, [rdi+58h]
0x140003a2f  mov     qword ptr [rdi+58h], 0
0x140003a37  test    rbx, rbx
0x140003a3a  jz      short loc_140003A50
0x140003a3c  call    cs:__imp_GetProcessHeap
0x140003a42  mov     r8, rbx; lpMem
0x140003a45  xor     edx, edx; dwFlags
0x140003a47  mov     rcx, rax; hHeap
0x140003a4a  call    cs:__imp_HeapFree
0x140003a50  mov     rbx, [rdi+38h]
0x140003a54  mov     qword ptr [rdi+38h], 0
0x140003a5c  test    rbx, rbx
0x140003a5f  jz      short loc_140003A75
0x140003a61  call    cs:__imp_GetProcessHeap
0x140003a67  mov     r8, rbx; lpMem
0x140003a6a  xor     edx, edx; dwFlags
0x140003a6c  mov     rcx, rax; hHeap
0x140003a6f  call    cs:__imp_HeapFree
0x140003a75  mov     rbx, [rdi+10h]
0x140003a79  test    rbx, rbx
0x140003a7c  jz      short loc_140003AA6
0x140003a7e  xor     r9d, r9d; msWindowLength
0x140003a81  xor     r8d, r8d; msPeriod
0x140003a84  xor     edx, edx; pftDueTime
0x140003a86  mov     rcx, rbx; pti
0x140003a89  call    cs:__imp_SetThreadpoolTimer
0x140003a8f  mov     edx, 1; fCancelPendingCallbacks
0x140003a94  mov     rcx, rbx; pti
0x140003a97  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140003a9d  mov     rcx, rbx; pti
0x140003aa0  call    cs:__imp_CloseThreadpoolTimer
0x140003aa6  mov     rbx, [rsp+28h+arg_0]
0x140003aab  mov     rsi, [rsp+28h+arg_8]
0x140003ab0  add     rsp, 20h
0x140003ab4  pop     rdi
0x140003ab5  retn
```
