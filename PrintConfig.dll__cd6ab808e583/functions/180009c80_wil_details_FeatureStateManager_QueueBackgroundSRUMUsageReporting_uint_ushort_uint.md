# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180009c80`
- end: `0x180009e2a`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `426`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000c6f0`

## callees

- `0x18000425e`
- `0x180004418`
- `0x180009c80`
- `0x18000ce3c`
- `0x1801c3010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009d20`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009d4a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009d20`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009d4a`
- `KERNEL32!CreateThreadpoolTimer` at `0x180009d87`
- `KERNEL32!CreateThreadpoolTimer` at `0x180009d87`
- `KERNEL32!CloseThreadpoolTimer` at `0x180009dc3`
- `KERNEL32!CloseThreadpoolTimer` at `0x180009dc3`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180009dba`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180009dba`
- `KERNEL32!SetThreadpoolTimer` at `0x180009dac`
- `KERNEL32!SetThreadpoolTimer` at `0x180009e04`
- `KERNEL32!SetThreadpoolTimer` at `0x180009dac`
- `KERNEL32!SetThreadpoolTimer` at `0x180009e04`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180009cd9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180009cd9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180009e16`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180009e16`
- `KERNEL32!SetLastError` at `0x180009dcb`
- `KERNEL32!SetLastError` at `0x180009dd8`
- `KERNEL32!SetLastError` at `0x180009dcb`
- `KERNEL32!SetLastError` at `0x180009dd8`
- `KERNEL32!GetLastError` at `0x180009d71`
- `KERNEL32!GetLastError` at `0x180009d99`
- `KERNEL32!GetLastError` at `0x180009d71`
- `KERNEL32!GetLastError` at `0x180009d99`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        unsigned __int16 a3,
        int a4)
{
  _DWORD *Ptr; // rcx
  size_t v9; // r8
  __int64 v10; // rcx
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *v13; // rbp
  DWORD v14; // ebx
  struct _TP_TIMER *v15; // rcx
  __int64 v16; // [rsp+28h] [rbp-50h]
  struct _FILETIME pftDueTime; // [rsp+80h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress(pv) )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  LODWORD(v16) = a2;
  HIDWORD(v16) = a3;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v9 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v9 >= 0xC )
      {
        *(_QWORD *)Ptr = v16;
        Ptr[2] = a4;
LABEL_12:
        pv[30].Ptr = (char *)pv[30].Ptr + 12;
        goto LABEL_13;
      }
      memset_0(Ptr, 0, v9);
      *(_DWORD *)_o__errno(v10) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0) = 22;
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
      if ( v13 )
      {
        v14 = GetLastError();
        SetThreadpoolTimer(v13, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v13, 1);
        CloseThreadpoolTimer(v13);
        SetLastError(v14);
      }
      pv[7].Ptr = ThreadpoolTimer;
      SetLastError(LastError);
    }
    v15 = (struct _TP_TIMER *)pv[7].Ptr;
    if ( v15 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v15, &pftDueTime, 0, 0x4E2u);
      LOBYTE(pv[8].Ptr) = 1;
    }
  }
  if ( pv != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(pv + 5);
}

```

## disassembly

```asm
0x180009c80  push    rbx
0x180009c82  push    rbp
0x180009c83  push    rsi
0x180009c84  push    rdi
0x180009c85  push    r14
0x180009c87  push    r15
0x180009c89  sub     rsp, 48h
0x180009c8d  mov     [rsp+78h+var_58], 0FFFFFFFFFFFFFFFEh
0x180009c96  mov     ebp, r9d
0x180009c99  movzx   ebx, r8w
0x180009c9d  mov     r14d, edx
0x180009ca0  mov     rdi, rcx
0x180009ca3  cmp     byte ptr [rcx], 0
0x180009ca6  jz      loc_180009E1D
0x180009cac  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180009cb3  jnz     loc_180009E1D
0x180009cb9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180009cc0  test    rax, rax
0x180009cc3  jz      short loc_180009CD2
0x180009cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cca  test    al, al
0x180009ccc  jnz     loc_180009E1D
0x180009cd2  lea     rsi, [rdi+28h]
0x180009cd6  mov     rcx, rsi; SRWLock
0x180009cd9  call    cs:__imp_AcquireSRWLockExclusive
0x180009cdf  xor     eax, eax
0x180009ce1  mov     word ptr [rsp+78h+var_50+6], ax
0x180009ce6  mov     dword ptr [rsp+78h+var_50], r14d
0x180009ceb  mov     word ptr [rsp+78h+var_50+4], bx
0x180009cf0  lea     rbx, [rdi+0E8h]
0x180009cf7  lea     edx, [rax+0Ch]; unsigned __int64
0x180009cfa  mov     rcx, rbx; this
0x180009cfd  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180009d02  test    al, al
0x180009d04  jz      short loc_180009D60
0x180009d06  mov     rcx, [rbx+8]; void *
0x180009d0a  mov     rax, [rbx+10h]
0x180009d0e  sub     rax, rcx
0x180009d11  cmp     rcx, [rbx+10h]
0x180009d15  sbb     r8, r8
0x180009d18  and     r8, rax; Size
0x180009d1b  test    rcx, rcx
0x180009d1e  jnz     short loc_180009D2E
0x180009d20  call    cs:__imp__o__errno
0x180009d26  mov     dword ptr [rax], 16h
0x180009d2c  jmp     short loc_180009D56
0x180009d2e  cmp     r8, 0Ch
0x180009d32  jb      short loc_180009D43
0x180009d34  movsd   xmm0, [rsp+78h+var_50]
0x180009d3a  movsd   qword ptr [rcx], xmm0
0x180009d3e  mov     [rcx+8], ebp
0x180009d41  jmp     short loc_180009D5B
0x180009d43  xor     edx, edx; Val
0x180009d45  call    memset_0
0x180009d4a  call    cs:__imp__o__errno
0x180009d50  mov     dword ptr [rax], 22h ; '"'
0x180009d56  call    _invalid_parameter_noinfo
0x180009d5b  add     qword ptr [rbx+8], 0Ch
0x180009d60  cmp     byte ptr [rdi+40h], 0
0x180009d64  jnz     loc_180009E0E
0x180009d6a  cmp     qword ptr [rdi+38h], 0
0x180009d6f  jnz     short loc_180009DDE
0x180009d71  call    cs:__imp_GetLastError
0x180009d77  mov     r14d, eax
0x180009d7a  xor     r8d, r8d; pcbe
0x180009d7d  mov     rdx, rdi; pv
0x180009d80  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180009d87  call    cs:__imp_CreateThreadpoolTimer
0x180009d8d  mov     r15, rax
0x180009d90  mov     rbp, [rdi+38h]
0x180009d94  test    rbp, rbp
0x180009d97  jz      short loc_180009DD1
0x180009d99  call    cs:__imp_GetLastError
0x180009d9f  mov     ebx, eax
0x180009da1  xor     r9d, r9d; msWindowLength
0x180009da4  xor     r8d, r8d; msPeriod
0x180009da7  xor     edx, edx; pftDueTime
0x180009da9  mov     rcx, rbp; pti
0x180009dac  call    cs:__imp_SetThreadpoolTimer
0x180009db2  mov     edx, 1; fCancelPendingCallbacks
0x180009db7  mov     rcx, rbp; pti
0x180009dba  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009dc0  mov     rcx, rbp; pti
0x180009dc3  call    cs:__imp_CloseThreadpoolTimer
0x180009dc9  mov     ecx, ebx; dwErrCode
0x180009dcb  call    cs:__imp_SetLastError
0x180009dd1  mov     [rdi+38h], r15
0x180009dd5  mov     ecx, r14d; dwErrCode
0x180009dd8  call    cs:__imp_SetLastError
0x180009dde  mov     rcx, [rdi+38h]; pti
0x180009de2  test    rcx, rcx
0x180009de5  jz      short loc_180009E0E
0x180009de7  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180009df3  mov     r9d, 4E2h; msWindowLength
0x180009df9  xor     r8d, r8d; msPeriod
0x180009dfc  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x180009e04  call    cs:__imp_SetThreadpoolTimer
0x180009e0a  mov     byte ptr [rdi+40h], 1
0x180009e0e  test    rsi, rsi
0x180009e11  jz      short loc_180009E1D
0x180009e13  mov     rcx, rsi; SRWLock
0x180009e16  call    cs:__imp_ReleaseSRWLockExclusive
0x180009e1c  nop
0x180009e1d  add     rsp, 48h
0x180009e21  pop     r15
0x180009e23  pop     r14
0x180009e25  pop     rdi
0x180009e26  pop     rsi
0x180009e27  pop     rbp
0x180009e28  pop     rbx
0x180009e29  retn
```
