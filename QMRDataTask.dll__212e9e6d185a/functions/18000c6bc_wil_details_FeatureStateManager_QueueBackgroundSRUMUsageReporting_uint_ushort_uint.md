# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000c6bc`
- end: `0x18000c845`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `393`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180010e60`

## callees

- `0x18000c6bc`
- `0x180011eec`
- `0x180014310`
- `0x180015010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000c76a`
- `msvcrt!memcpy_s` at `0x18000c76a`
- `KERNEL32!GetLastError` at `0x18000c785`
- `KERNEL32!GetLastError` at `0x18000c7ad`
- `KERNEL32!GetLastError` at `0x18000c785`
- `KERNEL32!GetLastError` at `0x18000c7ad`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000c79b`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000c79b`
- `KERNEL32!SetThreadpoolTimer` at `0x18000c7c0`
- `KERNEL32!SetThreadpoolTimer` at `0x18000c812`
- `KERNEL32!SetThreadpoolTimer` at `0x18000c7c0`
- `KERNEL32!SetThreadpoolTimer` at `0x18000c812`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000c71a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000c71a`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000c7d7`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000c7d7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c824`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c824`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000c7ce`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000c7ce`
- `KERNEL32!SetLastError` at `0x18000c7df`
- `KERNEL32!SetLastError` at `0x18000c7ec`
- `KERNEL32!SetLastError` at `0x18000c7df`
- `KERNEL32!SetLastError` at `0x18000c7ec`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        __int16 a3,
        int a4)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v11; // ebx
  struct _TP_TIMER *v12; // rcx
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
      if ( !pv[7].Ptr )
      {
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        Ptr = (struct _TP_TIMER *)pv[7].Ptr;
        if ( Ptr )
        {
          v11 = GetLastError();
          SetThreadpoolTimer(Ptr, 0, 0, 0);
          WaitForThreadpoolTimerCallbacks(Ptr, 1);
          CloseThreadpoolTimer(Ptr);
          SetLastError(v11);
        }
        pv[7].Ptr = ThreadpoolTimer;
        SetLastError(LastError);
      }
      v12 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v12 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v12, &pftDueTime, 0, 0x4E2u);
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
0x18000c6bc  push    rbx
0x18000c6be  push    rbp
0x18000c6bf  push    rsi
0x18000c6c0  push    rdi
0x18000c6c1  push    r14
0x18000c6c3  push    r15
0x18000c6c5  sub     rsp, 48h
0x18000c6c9  mov     rax, cs:__security_cookie
0x18000c6d0  xor     rax, rsp
0x18000c6d3  mov     [rsp+78h+var_40], rax
0x18000c6d8  mov     r14d, r9d
0x18000c6db  movzx   ebp, r8w
0x18000c6df  mov     ebx, edx
0x18000c6e1  mov     rdi, rcx
0x18000c6e4  cmp     byte ptr [rcx], 0
0x18000c6e7  jz      loc_18000C82B
0x18000c6ed  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000c6f4  jnz     loc_18000C82B
0x18000c6fa  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000c701  test    rax, rax
0x18000c704  jz      short loc_18000C713
0x18000c706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c70b  test    al, al
0x18000c70d  jnz     loc_18000C82B
0x18000c713  lea     rsi, [rdi+28h]
0x18000c717  mov     rcx, rsi; SRWLock
0x18000c71a  call    cs:__imp_AcquireSRWLockExclusive
0x18000c720  xor     eax, eax
0x18000c722  mov     [rsp+78h+var_4A], ax
0x18000c727  mov     [rsp+78h+Source], ebx
0x18000c72b  mov     [rsp+78h+var_4C], bp
0x18000c730  mov     [rsp+78h+var_48], r14d
0x18000c735  lea     rbx, [rdi+0E8h]
0x18000c73c  lea     ebp, [rax+0Ch]
0x18000c73f  mov     edx, ebp; unsigned __int64
0x18000c741  mov     rcx, rbx; this
0x18000c744  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000c749  test    al, al
0x18000c74b  jz      short loc_18000C774
0x18000c74d  mov     rcx, [rbx+8]; Destination
0x18000c751  mov     rax, [rbx+10h]
0x18000c755  sub     rax, rcx
0x18000c758  cmp     rcx, [rbx+10h]
0x18000c75c  sbb     rdx, rdx
0x18000c75f  and     rdx, rax; DestinationSize
0x18000c762  mov     r9d, ebp; SourceSize
0x18000c765  lea     r8, [rsp+78h+Source]; Source
0x18000c76a  call    cs:__imp_memcpy_s
0x18000c770  add     [rbx+8], rbp
0x18000c774  cmp     byte ptr [rdi+40h], 0
0x18000c778  jnz     loc_18000C81C
0x18000c77e  cmp     qword ptr [rdi+38h], 0
0x18000c783  jnz     short loc_18000C7F2
0x18000c785  call    cs:__imp_GetLastError
0x18000c78b  mov     r14d, eax
0x18000c78e  xor     r8d, r8d; pcbe
0x18000c791  mov     rdx, rdi; pv
0x18000c794  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000c79b  call    cs:__imp_CreateThreadpoolTimer
0x18000c7a1  mov     r15, rax
0x18000c7a4  mov     rbp, [rdi+38h]
0x18000c7a8  test    rbp, rbp
0x18000c7ab  jz      short loc_18000C7E5
0x18000c7ad  call    cs:__imp_GetLastError
0x18000c7b3  mov     ebx, eax
0x18000c7b5  xor     r9d, r9d; msWindowLength
0x18000c7b8  xor     r8d, r8d; msPeriod
0x18000c7bb  xor     edx, edx; pftDueTime
0x18000c7bd  mov     rcx, rbp; pti
0x18000c7c0  call    cs:__imp_SetThreadpoolTimer
0x18000c7c6  mov     edx, 1; fCancelPendingCallbacks
0x18000c7cb  mov     rcx, rbp; pti
0x18000c7ce  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c7d4  mov     rcx, rbp; pti
0x18000c7d7  call    cs:__imp_CloseThreadpoolTimer
0x18000c7dd  mov     ecx, ebx; dwErrCode
0x18000c7df  call    cs:__imp_SetLastError
0x18000c7e5  mov     [rdi+38h], r15
0x18000c7e9  mov     ecx, r14d; dwErrCode
0x18000c7ec  call    cs:__imp_SetLastError
0x18000c7f2  mov     rcx, [rdi+38h]; pti
0x18000c7f6  test    rcx, rcx
0x18000c7f9  jz      short loc_18000C81C
0x18000c7fb  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000c804  mov     r9d, 4E2h; msWindowLength
0x18000c80a  xor     r8d, r8d; msPeriod
0x18000c80d  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18000c812  call    cs:__imp_SetThreadpoolTimer
0x18000c818  mov     byte ptr [rdi+40h], 1
0x18000c81c  test    rsi, rsi
0x18000c81f  jz      short loc_18000C82B
0x18000c821  mov     rcx, rsi; SRWLock
0x18000c824  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c82a  nop
0x18000c82b  mov     rcx, [rsp+78h+var_40]
0x18000c830  xor     rcx, rsp; StackCookie
0x18000c833  call    __security_check_cookie
0x18000c838  add     rsp, 48h
0x18000c83c  pop     r15
0x18000c83e  pop     r14
0x18000c840  pop     rdi
0x18000c841  pop     rsi
0x18000c842  pop     rbp
0x18000c843  pop     rbx
0x18000c844  retn
```
