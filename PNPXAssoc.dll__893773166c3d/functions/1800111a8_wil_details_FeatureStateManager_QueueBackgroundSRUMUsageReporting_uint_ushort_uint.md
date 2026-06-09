# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800111a8`
- end: `0x180011330`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `392`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180012600`

## callees

- `0x1800111a8`
- `0x1800129e4`
- `0x180012e00`
- `0x180014010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180011256`
- `msvcrt!memcpy_s` at `0x180011256`
- `KERNEL32!SetLastError` at `0x1800112cb`
- `KERNEL32!SetLastError` at `0x1800112d8`
- `KERNEL32!SetLastError` at `0x1800112cb`
- `KERNEL32!SetLastError` at `0x1800112d8`
- `KERNEL32!GetLastError` at `0x180011271`
- `KERNEL32!GetLastError` at `0x180011299`
- `KERNEL32!GetLastError` at `0x180011271`
- `KERNEL32!GetLastError` at `0x180011299`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800112c3`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800112c3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180011310`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180011310`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800112ba`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800112ba`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180011206`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180011206`
- `KERNEL32!SetThreadpoolTimer` at `0x1800112ac`
- `KERNEL32!SetThreadpoolTimer` at `0x1800112fe`
- `KERNEL32!SetThreadpoolTimer` at `0x1800112ac`
- `KERNEL32!SetThreadpoolTimer` at `0x1800112fe`
- `KERNEL32!CreateThreadpoolTimer` at `0x180011287`
- `KERNEL32!CreateThreadpoolTimer` at `0x180011287`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        __int16 a3,
        int a4)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *Ptr; // rbp
  PTP_TIMER v11; // r15
  DWORD v12; // ebx
  struct _TP_TIMER *v13; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-58h] BYREF
  int Source; // [rsp+28h] [rbp-50h] BYREF
  __int16 v16; // [rsp+2Ch] [rbp-4Ch]
  __int16 v17; // [rsp+2Eh] [rbp-4Ah]
  int v18; // [rsp+30h] [rbp-48h]

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 5);
    Source = a2;
    v16 = a3;
    v17 = 0;
    v18 = a4;
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
        v11 = ThreadpoolTimer;
        if ( Ptr )
        {
          v12 = GetLastError();
          SetThreadpoolTimer(Ptr, 0, 0, 0);
          WaitForThreadpoolTimerCallbacks(Ptr, 1);
          CloseThreadpoolTimer(Ptr);
          SetLastError(v12);
        }
        pv[7].Ptr = v11;
        SetLastError(LastError);
      }
      v13 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v13 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v13, &pftDueTime, 0, 0x4E2u);
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
0x1800111a8  push    rbx
0x1800111aa  push    rbp
0x1800111ab  push    rsi
0x1800111ac  push    rdi
0x1800111ad  push    r14
0x1800111af  push    r15
0x1800111b1  sub     rsp, 48h
0x1800111b5  mov     rax, cs:__security_cookie
0x1800111bc  xor     rax, rsp
0x1800111bf  mov     [rsp+78h+var_40], rax
0x1800111c4  cmp     byte ptr [rcx], 0
0x1800111c7  mov     r14d, r9d
0x1800111ca  movzx   ebp, r8w
0x1800111ce  mov     ebx, edx
0x1800111d0  mov     rdi, rcx
0x1800111d3  jz      loc_180011316
0x1800111d9  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800111e0  jnz     loc_180011316
0x1800111e6  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800111ed  test    rax, rax
0x1800111f0  jz      short loc_1800111FF
0x1800111f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111f7  test    al, al
0x1800111f9  jnz     loc_180011316
0x1800111ff  lea     rsi, [rdi+28h]
0x180011203  mov     rcx, rsi; SRWLock
0x180011206  call    cs:__imp_AcquireSRWLockExclusive
0x18001120c  xor     eax, eax
0x18001120e  mov     [rsp+78h+Source], ebx
0x180011212  mov     [rsp+78h+var_4C], bp
0x180011217  lea     rbx, [rdi+0E8h]
0x18001121e  mov     rcx, rbx; this
0x180011221  mov     [rsp+78h+var_4A], ax
0x180011226  mov     [rsp+78h+var_48], r14d
0x18001122b  lea     ebp, [rax+0Ch]
0x18001122e  mov     edx, ebp; unsigned __int64
0x180011230  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180011235  test    al, al
0x180011237  jz      short loc_180011260
0x180011239  mov     rcx, [rbx+8]; Destination
0x18001123d  lea     r8, [rsp+78h+Source]; Source
0x180011242  mov     rax, [rbx+10h]
0x180011246  mov     r9d, ebp; SourceSize
0x180011249  sub     rax, rcx
0x18001124c  cmp     rcx, [rbx+10h]
0x180011250  sbb     rdx, rdx
0x180011253  and     rdx, rax; DestinationSize
0x180011256  call    cs:__imp_memcpy_s
0x18001125c  add     [rbx+8], rbp
0x180011260  cmp     byte ptr [rdi+40h], 0
0x180011264  jnz     loc_180011308
0x18001126a  cmp     qword ptr [rdi+38h], 0
0x18001126f  jnz     short loc_1800112DE
0x180011271  call    cs:__imp_GetLastError
0x180011277  xor     r8d, r8d; pcbe
0x18001127a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180011281  mov     rdx, rdi; pv
0x180011284  mov     r14d, eax
0x180011287  call    cs:__imp_CreateThreadpoolTimer
0x18001128d  mov     rbp, [rdi+38h]
0x180011291  mov     r15, rax
0x180011294  test    rbp, rbp
0x180011297  jz      short loc_1800112D1
0x180011299  call    cs:__imp_GetLastError
0x18001129f  xor     r9d, r9d; msWindowLength
0x1800112a2  xor     r8d, r8d; msPeriod
0x1800112a5  xor     edx, edx; pftDueTime
0x1800112a7  mov     rcx, rbp; pti
0x1800112aa  mov     ebx, eax
0x1800112ac  call    cs:__imp_SetThreadpoolTimer
0x1800112b2  mov     edx, 1; fCancelPendingCallbacks
0x1800112b7  mov     rcx, rbp; pti
0x1800112ba  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800112c0  mov     rcx, rbp; pti
0x1800112c3  call    cs:__imp_CloseThreadpoolTimer
0x1800112c9  mov     ecx, ebx; dwErrCode
0x1800112cb  call    cs:__imp_SetLastError
0x1800112d1  mov     ecx, r14d; dwErrCode
0x1800112d4  mov     [rdi+38h], r15
0x1800112d8  call    cs:__imp_SetLastError
0x1800112de  mov     rcx, [rdi+38h]; pti
0x1800112e2  test    rcx, rcx
0x1800112e5  jz      short loc_180011308
0x1800112e7  mov     r9d, 4E2h; msWindowLength
0x1800112ed  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800112f6  xor     r8d, r8d; msPeriod
0x1800112f9  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x1800112fe  call    cs:__imp_SetThreadpoolTimer
0x180011304  mov     byte ptr [rdi+40h], 1
0x180011308  test    rsi, rsi
0x18001130b  jz      short loc_180011316
0x18001130d  mov     rcx, rsi; SRWLock
0x180011310  call    cs:__imp_ReleaseSRWLockExclusive
0x180011316  mov     rcx, [rsp+78h+var_40]
0x18001131b  xor     rcx, rsp; StackCookie
0x18001131e  call    __security_check_cookie
0x180011323  add     rsp, 48h
0x180011327  pop     r15
0x180011329  pop     r14
0x18001132b  pop     rdi
0x18001132c  pop     rsi
0x18001132d  pop     rbp
0x18001132e  pop     rbx
0x18001132f  retn
```
