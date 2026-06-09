# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x14000aba0`
- end: `0x14000ad29`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `393`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14000d080`

## callees

- `0x14000aba0`
- `0x14000d7d4`
- `0x14000e1c0`
- `0x14000f010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000acc3`
- `KERNEL32!SetLastError` at `0x14000acd0`
- `KERNEL32!SetLastError` at `0x14000acc3`
- `KERNEL32!SetLastError` at `0x14000acd0`
- `KERNEL32!GetLastError` at `0x14000ac69`
- `KERNEL32!GetLastError` at `0x14000ac91`
- `KERNEL32!GetLastError` at `0x14000ac69`
- `KERNEL32!GetLastError` at `0x14000ac91`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000abfe`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000abfe`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000ad08`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000ad08`
- `KERNEL32!SetThreadpoolTimer` at `0x14000aca4`
- `KERNEL32!SetThreadpoolTimer` at `0x14000acf6`
- `KERNEL32!SetThreadpoolTimer` at `0x14000aca4`
- `KERNEL32!SetThreadpoolTimer` at `0x14000acf6`
- `KERNEL32!CreateThreadpoolTimer` at `0x14000ac7f`
- `KERNEL32!CreateThreadpoolTimer` at `0x14000ac7f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000acb2`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000acb2`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000acbb`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000acbb`
- `msvcrt!memcpy_s` at `0x14000ac4e`
- `msvcrt!memcpy_s` at `0x14000ac4e`

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
0x14000aba0  push    rbx
0x14000aba2  push    rbp
0x14000aba3  push    rsi
0x14000aba4  push    rdi
0x14000aba5  push    r14
0x14000aba7  push    r15
0x14000aba9  sub     rsp, 48h
0x14000abad  mov     rax, cs:__security_cookie
0x14000abb4  xor     rax, rsp
0x14000abb7  mov     [rsp+78h+var_40], rax
0x14000abbc  mov     r14d, r9d
0x14000abbf  movzx   ebp, r8w
0x14000abc3  mov     ebx, edx
0x14000abc5  mov     rdi, rcx
0x14000abc8  cmp     byte ptr [rcx], 0
0x14000abcb  jz      loc_14000AD0F
0x14000abd1  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000abd8  jnz     loc_14000AD0F
0x14000abde  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000abe5  test    rax, rax
0x14000abe8  jz      short loc_14000ABF7
0x14000abea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000abef  test    al, al
0x14000abf1  jnz     loc_14000AD0F
0x14000abf7  lea     rsi, [rdi+28h]
0x14000abfb  mov     rcx, rsi; SRWLock
0x14000abfe  call    cs:__imp_AcquireSRWLockExclusive
0x14000ac04  xor     eax, eax
0x14000ac06  mov     [rsp+78h+var_4A], ax
0x14000ac0b  mov     [rsp+78h+Source], ebx
0x14000ac0f  mov     [rsp+78h+var_4C], bp
0x14000ac14  mov     [rsp+78h+var_48], r14d
0x14000ac19  lea     rbx, [rdi+0E8h]
0x14000ac20  lea     ebp, [rax+0Ch]
0x14000ac23  mov     edx, ebp; unsigned __int64
0x14000ac25  mov     rcx, rbx; this
0x14000ac28  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000ac2d  test    al, al
0x14000ac2f  jz      short loc_14000AC58
0x14000ac31  mov     rcx, [rbx+8]; Destination
0x14000ac35  mov     rax, [rbx+10h]
0x14000ac39  sub     rax, rcx
0x14000ac3c  cmp     rcx, [rbx+10h]
0x14000ac40  sbb     rdx, rdx
0x14000ac43  and     rdx, rax; DestinationSize
0x14000ac46  mov     r9d, ebp; SourceSize
0x14000ac49  lea     r8, [rsp+78h+Source]; Source
0x14000ac4e  call    cs:__imp_memcpy_s
0x14000ac54  add     [rbx+8], rbp
0x14000ac58  cmp     byte ptr [rdi+40h], 0
0x14000ac5c  jnz     loc_14000AD00
0x14000ac62  cmp     qword ptr [rdi+38h], 0
0x14000ac67  jnz     short loc_14000ACD6
0x14000ac69  call    cs:__imp_GetLastError
0x14000ac6f  mov     r14d, eax
0x14000ac72  xor     r8d, r8d; pcbe
0x14000ac75  mov     rdx, rdi; pv
0x14000ac78  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000ac7f  call    cs:__imp_CreateThreadpoolTimer
0x14000ac85  mov     r15, rax
0x14000ac88  mov     rbp, [rdi+38h]
0x14000ac8c  test    rbp, rbp
0x14000ac8f  jz      short loc_14000ACC9
0x14000ac91  call    cs:__imp_GetLastError
0x14000ac97  mov     ebx, eax
0x14000ac99  xor     r9d, r9d; msWindowLength
0x14000ac9c  xor     r8d, r8d; msPeriod
0x14000ac9f  xor     edx, edx; pftDueTime
0x14000aca1  mov     rcx, rbp; pti
0x14000aca4  call    cs:__imp_SetThreadpoolTimer
0x14000acaa  mov     edx, 1; fCancelPendingCallbacks
0x14000acaf  mov     rcx, rbp; pti
0x14000acb2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000acb8  mov     rcx, rbp; pti
0x14000acbb  call    cs:__imp_CloseThreadpoolTimer
0x14000acc1  mov     ecx, ebx; dwErrCode
0x14000acc3  call    cs:__imp_SetLastError
0x14000acc9  mov     [rdi+38h], r15
0x14000accd  mov     ecx, r14d; dwErrCode
0x14000acd0  call    cs:__imp_SetLastError
0x14000acd6  mov     rcx, [rdi+38h]; pti
0x14000acda  test    rcx, rcx
0x14000acdd  jz      short loc_14000AD00
0x14000acdf  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x14000ace8  mov     r9d, 4E2h; msWindowLength
0x14000acee  xor     r8d, r8d; msPeriod
0x14000acf1  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x14000acf6  call    cs:__imp_SetThreadpoolTimer
0x14000acfc  mov     byte ptr [rdi+40h], 1
0x14000ad00  test    rsi, rsi
0x14000ad03  jz      short loc_14000AD0F
0x14000ad05  mov     rcx, rsi; SRWLock
0x14000ad08  call    cs:__imp_ReleaseSRWLockExclusive
0x14000ad0e  nop
0x14000ad0f  mov     rcx, [rsp+78h+var_40]
0x14000ad14  xor     rcx, rsp; StackCookie
0x14000ad17  call    __security_check_cookie
0x14000ad1c  add     rsp, 48h
0x14000ad20  pop     r15
0x14000ad22  pop     r14
0x14000ad24  pop     rdi
0x14000ad25  pop     rsi
0x14000ad26  pop     rbp
0x14000ad27  pop     rbx
0x14000ad28  retn
```
