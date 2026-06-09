# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180025c1c`
- end: `0x180025db6`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `410`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800278c0`

## callees

- `0x1800027d6`
- `0x1800028d8`
- `0x180025c1c`
- `0x180027e3c`
- `0x18005d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180025cb3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180025cdd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180025cb3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180025cdd`
- `KERNEL32!CreateThreadpoolTimer` at `0x180025d1a`
- `KERNEL32!CreateThreadpoolTimer` at `0x180025d1a`
- `KERNEL32!SetThreadpoolTimer` at `0x180025d3f`
- `KERNEL32!SetThreadpoolTimer` at `0x180025d91`
- `KERNEL32!SetThreadpoolTimer` at `0x180025d3f`
- `KERNEL32!SetThreadpoolTimer` at `0x180025d91`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180025c6c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180025c6c`
- `KERNEL32!CloseThreadpoolTimer` at `0x180025d56`
- `KERNEL32!CloseThreadpoolTimer` at `0x180025d56`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180025da3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180025da3`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180025d4d`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180025d4d`
- `KERNEL32!SetLastError` at `0x180025d5e`
- `KERNEL32!SetLastError` at `0x180025d6b`
- `KERNEL32!SetLastError` at `0x180025d5e`
- `KERNEL32!SetLastError` at `0x180025d6b`
- `KERNEL32!GetLastError` at `0x180025d04`
- `KERNEL32!GetLastError` at `0x180025d2c`
- `KERNEL32!GetLastError` at `0x180025d04`
- `KERNEL32!GetLastError` at `0x180025d2c`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        unsigned __int16 a3,
        int a4)
{
  __int64 v8; // rdx
  _DWORD *Ptr; // rcx
  size_t v10; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v13; // rbp
  PTP_TIMER v14; // r15
  DWORD v15; // ebx
  struct _TP_TIMER *v16; // rcx
  __int64 v17; // [rsp+20h] [rbp-48h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  HIDWORD(v17) = a3;
  LODWORD(v17) = a2;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v10 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v10 >= 0xC )
      {
        *(_QWORD *)Ptr = v17;
        Ptr[2] = a4;
LABEL_12:
        pv[30].Ptr = (char *)pv[30].Ptr + 12;
        goto LABEL_13;
      }
      memset_0(Ptr, 0, v10);
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0, v8, v10) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_12;
  }
LABEL_13:
  if ( !LOBYTE(pv[8].Ptr) )
  {
    if ( !pv[7].Ptr )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_, pv, 0);
      v13 = (struct _TP_TIMER *)pv[7].Ptr;
      v14 = ThreadpoolTimer;
      if ( v13 )
      {
        v15 = GetLastError();
        SetThreadpoolTimer(v13, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v13, 1);
        CloseThreadpoolTimer(v13);
        SetLastError(v15);
      }
      pv[7].Ptr = v14;
      SetLastError(LastError);
    }
    v16 = (struct _TP_TIMER *)pv[7].Ptr;
    if ( v16 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v16, &pftDueTime, 0, 0x4E2u);
      LOBYTE(pv[8].Ptr) = 1;
    }
  }
  if ( pv != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(pv + 5);
}

```

## disassembly

```asm
0x180025c1c  push    rbx
0x180025c1e  push    rbp
0x180025c1f  push    rsi
0x180025c20  push    rdi
0x180025c21  push    r14
0x180025c23  push    r15
0x180025c25  sub     rsp, 38h
0x180025c29  cmp     byte ptr [rcx], 0
0x180025c2c  mov     ebp, r9d
0x180025c2f  movzx   ebx, r8w
0x180025c33  mov     r14d, edx
0x180025c36  mov     rdi, rcx
0x180025c39  jz      loc_180025DA9
0x180025c3f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180025c46  jnz     loc_180025DA9
0x180025c4c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180025c53  test    rax, rax
0x180025c56  jz      short loc_180025C65
0x180025c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c5d  test    al, al
0x180025c5f  jnz     loc_180025DA9
0x180025c65  lea     rsi, [rdi+28h]
0x180025c69  mov     rcx, rsi; SRWLock
0x180025c6c  call    cs:__imp_AcquireSRWLockExclusive
0x180025c72  xor     eax, eax
0x180025c74  mov     word ptr [rsp+68h+var_48+4], bx
0x180025c79  lea     rbx, [rdi+0E8h]
0x180025c80  mov     word ptr [rsp+68h+var_48+6], ax
0x180025c85  mov     rcx, rbx; this
0x180025c88  mov     dword ptr [rsp+68h+var_48], r14d
0x180025c8d  lea     edx, [rax+0Ch]; unsigned __int64
0x180025c90  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180025c95  test    al, al
0x180025c97  jz      short loc_180025CF3
0x180025c99  mov     rcx, [rbx+8]; void *
0x180025c9d  mov     rax, [rbx+10h]
0x180025ca1  sub     rax, rcx
0x180025ca4  cmp     rcx, [rbx+10h]
0x180025ca8  sbb     r8, r8
0x180025cab  and     r8, rax; Size
0x180025cae  test    rcx, rcx
0x180025cb1  jnz     short loc_180025CC1
0x180025cb3  call    cs:__imp__o__errno
0x180025cb9  mov     dword ptr [rax], 16h
0x180025cbf  jmp     short loc_180025CE9
0x180025cc1  cmp     r8, 0Ch
0x180025cc5  jb      short loc_180025CD6
0x180025cc7  movsd   xmm0, [rsp+68h+var_48]
0x180025ccd  movsd   qword ptr [rcx], xmm0
0x180025cd1  mov     [rcx+8], ebp
0x180025cd4  jmp     short loc_180025CEE
0x180025cd6  xor     edx, edx; Val
0x180025cd8  call    memset_0
0x180025cdd  call    cs:__imp__o__errno
0x180025ce3  mov     dword ptr [rax], 22h ; '"'
0x180025ce9  call    _invalid_parameter_noinfo
0x180025cee  add     qword ptr [rbx+8], 0Ch
0x180025cf3  cmp     byte ptr [rdi+40h], 0
0x180025cf7  jnz     loc_180025D9B
0x180025cfd  cmp     qword ptr [rdi+38h], 0
0x180025d02  jnz     short loc_180025D71
0x180025d04  call    cs:__imp_GetLastError
0x180025d0a  xor     r8d, r8d; pcbe
0x180025d0d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180025d14  mov     rdx, rdi; pv
0x180025d17  mov     r14d, eax
0x180025d1a  call    cs:__imp_CreateThreadpoolTimer
0x180025d20  mov     rbp, [rdi+38h]
0x180025d24  mov     r15, rax
0x180025d27  test    rbp, rbp
0x180025d2a  jz      short loc_180025D64
0x180025d2c  call    cs:__imp_GetLastError
0x180025d32  xor     r9d, r9d; msWindowLength
0x180025d35  xor     r8d, r8d; msPeriod
0x180025d38  xor     edx, edx; pftDueTime
0x180025d3a  mov     rcx, rbp; pti
0x180025d3d  mov     ebx, eax
0x180025d3f  call    cs:__imp_SetThreadpoolTimer
0x180025d45  mov     edx, 1; fCancelPendingCallbacks
0x180025d4a  mov     rcx, rbp; pti
0x180025d4d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180025d53  mov     rcx, rbp; pti
0x180025d56  call    cs:__imp_CloseThreadpoolTimer
0x180025d5c  mov     ecx, ebx; dwErrCode
0x180025d5e  call    cs:__imp_SetLastError
0x180025d64  mov     ecx, r14d; dwErrCode
0x180025d67  mov     [rdi+38h], r15
0x180025d6b  call    cs:__imp_SetLastError
0x180025d71  mov     rcx, [rdi+38h]; pti
0x180025d75  test    rcx, rcx
0x180025d78  jz      short loc_180025D9B
0x180025d7a  mov     r9d, 4E2h; msWindowLength
0x180025d80  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180025d89  xor     r8d, r8d; msPeriod
0x180025d8c  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180025d91  call    cs:__imp_SetThreadpoolTimer
0x180025d97  mov     byte ptr [rdi+40h], 1
0x180025d9b  test    rsi, rsi
0x180025d9e  jz      short loc_180025DA9
0x180025da0  mov     rcx, rsi; SRWLock
0x180025da3  call    cs:__imp_ReleaseSRWLockExclusive
0x180025da9  add     rsp, 38h
0x180025dad  pop     r15
0x180025daf  pop     r14
0x180025db1  pop     rdi
0x180025db2  pop     rsi
0x180025db3  pop     rbp
0x180025db4  pop     rbx
0x180025db5  retn
```
