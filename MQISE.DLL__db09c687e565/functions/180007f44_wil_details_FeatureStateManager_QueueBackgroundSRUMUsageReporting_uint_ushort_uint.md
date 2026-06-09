# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180007f44`
- end: `0x1800080d4`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `400`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000ab20`

## callees

- `0x180007f44`
- `0x18000c40c`
- `0x18000f5f0`
- `0x180011010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007ff3`
- `msvcrt!memcpy_s` at `0x180007ff3`
- `KERNEL32!CreateThreadpoolTimer` at `0x180008026`
- `KERNEL32!CreateThreadpoolTimer` at `0x180008026`
- `KERNEL32!CloseThreadpoolTimer` at `0x180008064`
- `KERNEL32!CloseThreadpoolTimer` at `0x180008064`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000805a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000805a`
- `KERNEL32!SetThreadpoolTimer` at `0x18000804b`
- `KERNEL32!SetThreadpoolTimer` at `0x1800080a1`
- `KERNEL32!SetThreadpoolTimer` at `0x18000804b`
- `KERNEL32!SetThreadpoolTimer` at `0x1800080a1`
- `KERNEL32!SetLastError` at `0x18000806d`
- `KERNEL32!SetLastError` at `0x18000807b`
- `KERNEL32!SetLastError` at `0x18000806d`
- `KERNEL32!SetLastError` at `0x18000807b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800080b3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800080b3`
- `KERNEL32!GetLastError` at `0x180008010`
- `KERNEL32!GetLastError` at `0x180008038`
- `KERNEL32!GetLastError` at `0x180008010`
- `KERNEL32!GetLastError` at `0x180008038`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180007fa2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180007fa2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        __int16 a3,
        int a4)
{
  struct _TP_TIMER *Ptr; // rcx
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *v11; // rbp
  DWORD v12; // ebx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-58h] BYREF
  int Source; // [rsp+28h] [rbp-50h] BYREF
  __int16 v15; // [rsp+2Ch] [rbp-4Ch]
  __int16 v16; // [rsp+2Eh] [rbp-4Ah]
  int v17; // [rsp+30h] [rbp-48h]

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 5);
    v16 = 0;
    Source = a2;
    v15 = a3;
    v17 = a4;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
    {
      memcpy_s(
        pv[30].Ptr,
        ((char *)pv[31].Ptr - (char *)pv[30].Ptr) & -(__int64)(pv[30].Ptr < pv[31].Ptr),
        &Source,
        0xCu);
      pv[30].Ptr = (char *)pv[30].Ptr + 12;
    }
    if ( !LOBYTE(pv[8].Ptr) )
    {
      Ptr = (struct _TP_TIMER *)pv[7].Ptr;
      if ( Ptr )
        goto LABEL_12;
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_, pv, 0);
      v11 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v11 )
      {
        v12 = GetLastError();
        SetThreadpoolTimer(v11, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v11, 1);
        CloseThreadpoolTimer(v11);
        SetLastError(v12);
      }
      pv[7].Ptr = ThreadpoolTimer;
      SetLastError(LastError);
      Ptr = (struct _TP_TIMER *)pv[7].Ptr;
      if ( Ptr )
      {
LABEL_12:
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(Ptr, &pftDueTime, 0, 0x4E2u);
        LOBYTE(pv[8].Ptr) = 1;
      }
    }
    if ( pv != (RTL_SRWLOCK *)-40LL )
      ReleaseSRWLockExclusive(pv + 5);
  }
}

```

## disassembly

```asm
0x180007f44  push    rbx
0x180007f46  push    rbp
0x180007f47  push    rsi
0x180007f48  push    rdi
0x180007f49  push    r14
0x180007f4b  push    r15
0x180007f4d  sub     rsp, 48h
0x180007f51  mov     rax, cs:__security_cookie
0x180007f58  xor     rax, rsp
0x180007f5b  mov     [rsp+78h+var_40], rax
0x180007f60  mov     r14d, r9d
0x180007f63  movzx   ebp, r8w
0x180007f67  mov     ebx, edx
0x180007f69  mov     rdi, rcx
0x180007f6c  cmp     byte ptr [rcx], 0
0x180007f6f  jz      loc_1800080BA
0x180007f75  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180007f7c  jnz     loc_1800080BA
0x180007f82  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180007f89  test    rax, rax
0x180007f8c  jz      short loc_180007F9B
0x180007f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f93  test    al, al
0x180007f95  jnz     loc_1800080BA
0x180007f9b  lea     rsi, [rdi+28h]
0x180007f9f  mov     rcx, rsi; SRWLock
0x180007fa2  call    cs:__imp_AcquireSRWLockExclusive
0x180007fa8  nop
0x180007fa9  xor     eax, eax
0x180007fab  mov     [rsp+78h+var_4A], ax
0x180007fb0  mov     [rsp+78h+Source], ebx
0x180007fb4  mov     [rsp+78h+var_4C], bp
0x180007fb9  mov     [rsp+78h+var_48], r14d
0x180007fbe  lea     rbx, [rdi+0E8h]
0x180007fc5  lea     ebp, [rax+0Ch]
0x180007fc8  mov     edx, ebp; unsigned __int64
0x180007fca  mov     rcx, rbx; this
0x180007fcd  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180007fd2  test    al, al
0x180007fd4  jz      short loc_180007FFD
0x180007fd6  mov     rcx, [rbx+8]; Destination
0x180007fda  mov     rax, [rbx+10h]
0x180007fde  sub     rax, rcx
0x180007fe1  cmp     rcx, [rbx+10h]
0x180007fe5  sbb     rdx, rdx
0x180007fe8  and     rdx, rax; DestinationSize
0x180007feb  mov     r9d, ebp; SourceSize
0x180007fee  lea     r8, [rsp+78h+Source]; Source
0x180007ff3  call    cs:__imp_memcpy_s
0x180007ff9  add     [rbx+8], rbp
0x180007ffd  cmp     byte ptr [rdi+40h], 0
0x180008001  jnz     loc_1800080AB
0x180008007  mov     rcx, [rdi+38h]
0x18000800b  test    rcx, rcx
0x18000800e  jnz     short loc_18000808A
0x180008010  call    cs:__imp_GetLastError
0x180008016  mov     r14d, eax
0x180008019  xor     r8d, r8d; pcbe
0x18000801c  mov     rdx, rdi; pv
0x18000801f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180008026  call    cs:__imp_CreateThreadpoolTimer
0x18000802c  mov     r15, rax
0x18000802f  mov     rbp, [rdi+38h]
0x180008033  test    rbp, rbp
0x180008036  jz      short loc_180008074
0x180008038  call    cs:__imp_GetLastError
0x18000803e  mov     ebx, eax
0x180008040  xor     r9d, r9d; msWindowLength
0x180008043  xor     r8d, r8d; msPeriod
0x180008046  xor     edx, edx; pftDueTime
0x180008048  mov     rcx, rbp; pti
0x18000804b  call    cs:__imp_SetThreadpoolTimer
0x180008051  nop
0x180008052  mov     edx, 1; fCancelPendingCallbacks
0x180008057  mov     rcx, rbp; pti
0x18000805a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008060  nop
0x180008061  mov     rcx, rbp; pti
0x180008064  call    cs:__imp_CloseThreadpoolTimer
0x18000806a  nop
0x18000806b  mov     ecx, ebx; dwErrCode
0x18000806d  call    cs:__imp_SetLastError
0x180008073  nop
0x180008074  mov     [rdi+38h], r15
0x180008078  mov     ecx, r14d; dwErrCode
0x18000807b  call    cs:__imp_SetLastError
0x180008081  mov     rcx, [rdi+38h]; pti
0x180008085  test    rcx, rcx
0x180008088  jz      short loc_1800080AB
0x18000808a  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180008093  mov     r9d, 4E2h; msWindowLength
0x180008099  xor     r8d, r8d; msPeriod
0x18000809c  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x1800080a1  call    cs:__imp_SetThreadpoolTimer
0x1800080a7  mov     byte ptr [rdi+40h], 1
0x1800080ab  test    rsi, rsi
0x1800080ae  jz      short loc_1800080BA
0x1800080b0  mov     rcx, rsi; SRWLock
0x1800080b3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800080b9  nop
0x1800080ba  mov     rcx, [rsp+78h+var_40]
0x1800080bf  xor     rcx, rsp; StackCookie
0x1800080c2  call    __security_check_cookie
0x1800080c7  add     rsp, 48h
0x1800080cb  pop     r15
0x1800080cd  pop     r14
0x1800080cf  pop     rdi
0x1800080d0  pop     rsi
0x1800080d1  pop     rbp
0x1800080d2  pop     rbx
0x1800080d3  retn
```
