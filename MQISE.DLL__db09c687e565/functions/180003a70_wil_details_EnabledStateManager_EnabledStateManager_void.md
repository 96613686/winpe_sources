# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180003a70`
- end: `0x180003bd0`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `352`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010010`

## callees

- `0x180003a70`
- `0x180007ea4`
- `0x180011010`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x180003abd`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003bb9`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003abd`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003bb9`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003ab3`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003baf`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003ab3`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003baf`
- `KERNEL32!SetThreadpoolTimer` at `0x180003aa4`
- `KERNEL32!SetThreadpoolTimer` at `0x180003ba0`
- `KERNEL32!SetThreadpoolTimer` at `0x180003aa4`
- `KERNEL32!SetThreadpoolTimer` at `0x180003ba0`
- `KERNEL32!SetLastError` at `0x180003ac6`
- `KERNEL32!SetLastError` at `0x180003ac6`
- `KERNEL32!GetProcessHeap` at `0x180003b51`
- `KERNEL32!GetProcessHeap` at `0x180003b77`
- `KERNEL32!GetProcessHeap` at `0x180003b51`
- `KERNEL32!GetProcessHeap` at `0x180003b77`
- `KERNEL32!HeapFree` at `0x180003b5f`
- `KERNEL32!HeapFree` at `0x180003b85`
- `KERNEL32!HeapFree` at `0x180003b5f`
- `KERNEL32!HeapFree` at `0x180003b85`
- `KERNEL32!GetLastError` at `0x180003a91`
- `KERNEL32!GetLastError` at `0x180003a91`

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
0x180003a70  mov     [rsp+arg_0], rbx
0x180003a75  mov     [rsp+arg_8], rsi
0x180003a7a  push    rdi
0x180003a7b  sub     rsp, 20h
0x180003a7f  mov     rdi, rcx
0x180003a82  mov     dword ptr [rcx], 0
0x180003a88  mov     rsi, [rcx+10h]
0x180003a8c  test    rsi, rsi
0x180003a8f  jz      short loc_180003ACD
0x180003a91  call    cs:__imp_GetLastError
0x180003a97  mov     ebx, eax
0x180003a99  xor     r9d, r9d; msWindowLength
0x180003a9c  xor     r8d, r8d; msPeriod
0x180003a9f  xor     edx, edx; pftDueTime
0x180003aa1  mov     rcx, rsi; pti
0x180003aa4  call    cs:__imp_SetThreadpoolTimer
0x180003aaa  nop
0x180003aab  mov     edx, 1; fCancelPendingCallbacks
0x180003ab0  mov     rcx, rsi; pti
0x180003ab3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003ab9  nop
0x180003aba  mov     rcx, rsi; pti
0x180003abd  call    cs:__imp_CloseThreadpoolTimer
0x180003ac3  nop
0x180003ac4  mov     ecx, ebx; dwErrCode
0x180003ac6  call    cs:__imp_SetLastError
0x180003acc  nop
0x180003acd  mov     qword ptr [rdi+10h], 0
0x180003ad5  mov     rcx, rdi; this
0x180003ad8  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180003add  mov     rcx, [rdi+68h]
0x180003ae1  test    rcx, rcx
0x180003ae4  jz      short loc_180003B16
0x180003ae6  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003aed  test    rax, rax
0x180003af0  jnz     short loc_180003B01
0x180003af2  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003af9  test    rdx, rdx
0x180003afc  jz      short loc_180003B14
0x180003afe  mov     rax, rdx
0x180003b01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b06  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003b0d  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003b14  jmp     short loc_180003B24
0x180003b16  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003b1d  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003b24  mov     rcx, [rdi+60h]
0x180003b28  test    rcx, rcx
0x180003b2b  jz      short loc_180003B40
0x180003b2d  test    rax, rax
0x180003b30  jnz     short loc_180003B3A
0x180003b32  test    rdx, rdx
0x180003b35  jz      short loc_180003B40
0x180003b37  mov     rax, rdx
0x180003b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b3f  nop
0x180003b40  mov     rbx, [rdi+58h]
0x180003b44  mov     qword ptr [rdi+58h], 0
0x180003b4c  test    rbx, rbx
0x180003b4f  jz      short loc_180003B66
0x180003b51  call    cs:__imp_GetProcessHeap
0x180003b57  mov     rcx, rax; hHeap
0x180003b5a  mov     r8, rbx; lpMem
0x180003b5d  xor     edx, edx; dwFlags
0x180003b5f  call    cs:__imp_HeapFree
0x180003b65  nop
0x180003b66  mov     rbx, [rdi+38h]
0x180003b6a  mov     qword ptr [rdi+38h], 0
0x180003b72  test    rbx, rbx
0x180003b75  jz      short loc_180003B8C
0x180003b77  call    cs:__imp_GetProcessHeap
0x180003b7d  mov     rcx, rax; hHeap
0x180003b80  mov     r8, rbx; lpMem
0x180003b83  xor     edx, edx; dwFlags
0x180003b85  call    cs:__imp_HeapFree
0x180003b8b  nop
0x180003b8c  mov     rbx, [rdi+10h]
0x180003b90  test    rbx, rbx
0x180003b93  jz      short loc_180003BC0
0x180003b95  xor     r9d, r9d; msWindowLength
0x180003b98  xor     r8d, r8d; msPeriod
0x180003b9b  xor     edx, edx; pftDueTime
0x180003b9d  mov     rcx, rbx; pti
0x180003ba0  call    cs:__imp_SetThreadpoolTimer
0x180003ba6  nop
0x180003ba7  mov     edx, 1; fCancelPendingCallbacks
0x180003bac  mov     rcx, rbx; pti
0x180003baf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003bb5  nop
0x180003bb6  mov     rcx, rbx; pti
0x180003bb9  call    cs:__imp_CloseThreadpoolTimer
0x180003bbf  nop
0x180003bc0  mov     rbx, [rsp+28h+arg_0]
0x180003bc5  mov     rsi, [rsp+28h+arg_8]
0x180003bca  add     rsp, 20h
0x180003bce  pop     rdi
0x180003bcf  retn
```
