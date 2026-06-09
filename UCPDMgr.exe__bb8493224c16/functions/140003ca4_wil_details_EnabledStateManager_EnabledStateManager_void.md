# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x140003ca4`
- end: `0x140003dfc`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400102c0`

## callees

- `0x140003ca4`
- `0x140003e98`
- `0x14000f4d0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140003d2c`
- `KERNEL32!HeapFree` at `0x140003d51`
- `KERNEL32!HeapFree` at `0x140003d2c`
- `KERNEL32!HeapFree` at `0x140003d51`
- `KERNEL32!SetLastError` at `0x140003cf4`
- `KERNEL32!SetLastError` at `0x140003cf4`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140003ce3`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140003ddc`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140003ce3`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140003ddc`
- `KERNEL32!GetLastError` at `0x140003cc2`
- `KERNEL32!GetLastError` at `0x140003cc2`
- `KERNEL32!CloseThreadpoolTimer` at `0x140003cec`
- `KERNEL32!CloseThreadpoolTimer` at `0x140003de5`
- `KERNEL32!CloseThreadpoolTimer` at `0x140003cec`
- `KERNEL32!CloseThreadpoolTimer` at `0x140003de5`
- `KERNEL32!SetThreadpoolTimer` at `0x140003cd5`
- `KERNEL32!SetThreadpoolTimer` at `0x140003dce`
- `KERNEL32!SetThreadpoolTimer` at `0x140003cd5`
- `KERNEL32!SetThreadpoolTimer` at `0x140003dce`
- `KERNEL32!GetProcessHeap` at `0x140003d1e`
- `KERNEL32!GetProcessHeap` at `0x140003d43`
- `KERNEL32!GetProcessHeap` at `0x140003d1e`
- `KERNEL32!GetProcessHeap` at `0x140003d43`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::~EnabledStateManager(wil::details::EnabledStateManager *this)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  void *v6; // rbx
  HANDLE v7; // rax
  void (*v8)(void); // rax
  __int64 v9; // rdx
  struct _TP_TIMER *v10; // rbx

  *(_BYTE *)this = 0;
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
  *(_BYTE *)this = 0;
  wil::details::EnabledStateManager::RecordCachedUsageUnderLock(this);
  v4 = (void *)*((_QWORD *)this + 13);
  *((_QWORD *)this + 13) = 0;
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  v6 = (void *)*((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
  }
  if ( !*((_QWORD *)this + 5) )
  {
    v8 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v9 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_14;
  }
  v8 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v9 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_14;
    v8 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  }
  v8();
  v9 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v8 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_14:
  if ( !*((_QWORD *)this + 4) )
    goto LABEL_19;
  if ( !v8 )
  {
    if ( !v9 )
      goto LABEL_19;
    v8 = (void (*)(void))v9;
  }
  v8();
LABEL_19:
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
0x140003ca4  mov     [rsp+arg_0], rbx
0x140003ca9  mov     [rsp+arg_8], rsi
0x140003cae  push    rdi
0x140003caf  sub     rsp, 20h
0x140003cb3  mov     rdi, rcx
0x140003cb6  mov     byte ptr [rcx], 0
0x140003cb9  mov     rsi, [rcx+10h]
0x140003cbd  test    rsi, rsi
0x140003cc0  jz      short loc_140003CFA
0x140003cc2  call    cs:__imp_GetLastError
0x140003cc8  mov     ebx, eax
0x140003cca  xor     r9d, r9d; msWindowLength
0x140003ccd  xor     r8d, r8d; msPeriod
0x140003cd0  xor     edx, edx; pftDueTime
0x140003cd2  mov     rcx, rsi; pti
0x140003cd5  call    cs:__imp_SetThreadpoolTimer
0x140003cdb  mov     edx, 1; fCancelPendingCallbacks
0x140003ce0  mov     rcx, rsi; pti
0x140003ce3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140003ce9  mov     rcx, rsi; pti
0x140003cec  call    cs:__imp_CloseThreadpoolTimer
0x140003cf2  mov     ecx, ebx; dwErrCode
0x140003cf4  call    cs:__imp_SetLastError
0x140003cfa  mov     qword ptr [rdi+10h], 0
0x140003d02  mov     byte ptr [rdi], 0
0x140003d05  mov     rcx, rdi; this
0x140003d08  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)
0x140003d0d  mov     rbx, [rdi+68h]
0x140003d11  mov     qword ptr [rdi+68h], 0
0x140003d19  test    rbx, rbx
0x140003d1c  jz      short loc_140003D32
0x140003d1e  call    cs:__imp_GetProcessHeap
0x140003d24  mov     rcx, rax; hHeap
0x140003d27  mov     r8, rbx; lpMem
0x140003d2a  xor     edx, edx; dwFlags
0x140003d2c  call    cs:__imp_HeapFree
0x140003d32  mov     rbx, [rdi+48h]
0x140003d36  mov     qword ptr [rdi+48h], 0
0x140003d3e  test    rbx, rbx
0x140003d41  jz      short loc_140003D57
0x140003d43  call    cs:__imp_GetProcessHeap
0x140003d49  mov     rcx, rax; hHeap
0x140003d4c  mov     r8, rbx; lpMem
0x140003d4f  xor     edx, edx; dwFlags
0x140003d51  call    cs:__imp_HeapFree
0x140003d57  mov     rcx, [rdi+28h]
0x140003d5b  test    rcx, rcx
0x140003d5e  jz      short loc_140003D90
0x140003d60  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140003d67  test    rax, rax
0x140003d6a  jnz     short loc_140003D7B
0x140003d6c  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140003d73  test    rdx, rdx
0x140003d76  jz      short loc_140003D8E
0x140003d78  mov     rax, rdx
0x140003d7b  call    _guard_dispatch_icall
0x140003d80  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140003d87  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140003d8e  jmp     short loc_140003D9E
0x140003d90  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140003d97  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140003d9e  mov     rcx, [rdi+20h]
0x140003da2  test    rcx, rcx
0x140003da5  jz      short loc_140003DBA
0x140003da7  test    rax, rax
0x140003daa  jnz     short loc_140003DB4
0x140003dac  test    rdx, rdx
0x140003daf  jz      short loc_140003DBA
0x140003db1  mov     rax, rdx
0x140003db4  call    _guard_dispatch_icall
0x140003db9  nop
0x140003dba  mov     rbx, [rdi+10h]
0x140003dbe  test    rbx, rbx
0x140003dc1  jz      short loc_140003DEC
0x140003dc3  xor     r9d, r9d; msWindowLength
0x140003dc6  xor     r8d, r8d; msPeriod
0x140003dc9  xor     edx, edx; pftDueTime
0x140003dcb  mov     rcx, rbx; pti
0x140003dce  call    cs:__imp_SetThreadpoolTimer
0x140003dd4  mov     edx, 1; fCancelPendingCallbacks
0x140003dd9  mov     rcx, rbx; pti
0x140003ddc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140003de2  mov     rcx, rbx; pti
0x140003de5  call    cs:__imp_CloseThreadpoolTimer
0x140003deb  nop
0x140003dec  mov     rbx, [rsp+28h+arg_0]
0x140003df1  mov     rsi, [rsp+28h+arg_8]
0x140003df6  add     rsp, 20h
0x140003dfa  pop     rdi
0x140003dfb  retn
```
