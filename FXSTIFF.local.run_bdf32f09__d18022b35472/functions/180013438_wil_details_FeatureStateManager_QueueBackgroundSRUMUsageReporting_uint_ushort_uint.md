# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180013438`
- end: `0x1800135c5`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `397`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180015630`

## callees

- `0x180013438`
- `0x180015cac`
- `0x180017c00`
- `0x180019010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800134e6`
- `msvcrt!memcpy_s` at `0x1800134e6`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18001354c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18001354c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800135a4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800135a4`
- `KERNEL32!CloseThreadpoolTimer` at `0x180013555`
- `KERNEL32!CloseThreadpoolTimer` at `0x180013555`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180013496`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180013496`
- `KERNEL32!SetThreadpoolTimer` at `0x18001353e`
- `KERNEL32!SetThreadpoolTimer` at `0x180013592`
- `KERNEL32!SetThreadpoolTimer` at `0x18001353e`
- `KERNEL32!SetThreadpoolTimer` at `0x180013592`
- `KERNEL32!CreateThreadpoolTimer` at `0x180013519`
- `KERNEL32!CreateThreadpoolTimer` at `0x180013519`
- `KERNEL32!GetLastError` at `0x180013503`
- `KERNEL32!GetLastError` at `0x18001352b`
- `KERNEL32!GetLastError` at `0x180013503`
- `KERNEL32!GetLastError` at `0x18001352b`
- `KERNEL32!SetLastError` at `0x18001355e`
- `KERNEL32!SetLastError` at `0x18001356c`
- `KERNEL32!SetLastError` at `0x18001355e`
- `KERNEL32!SetLastError` at `0x18001356c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180013438  push    rbx
0x18001343a  push    rbp
0x18001343b  push    rsi
0x18001343c  push    rdi
0x18001343d  push    r14
0x18001343f  push    r15
0x180013441  sub     rsp, 48h
0x180013445  mov     rax, cs:__security_cookie
0x18001344c  xor     rax, rsp
0x18001344f  mov     [rsp+78h+var_40], rax
0x180013454  mov     r14d, r9d
0x180013457  movzx   ebp, r8w
0x18001345b  mov     ebx, edx
0x18001345d  mov     rdi, rcx
0x180013460  cmp     byte ptr [rcx], 0
0x180013463  jz      loc_1800135AB
0x180013469  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180013470  jnz     loc_1800135AB
0x180013476  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001347d  test    rax, rax
0x180013480  jz      short loc_18001348F
0x180013482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013487  test    al, al
0x180013489  jnz     loc_1800135AB
0x18001348f  lea     rsi, [rdi+28h]
0x180013493  mov     rcx, rsi; SRWLock
0x180013496  call    cs:__imp_AcquireSRWLockExclusive
0x18001349c  xor     eax, eax
0x18001349e  mov     [rsp+78h+var_4A], ax
0x1800134a3  mov     [rsp+78h+Source], ebx
0x1800134a7  mov     [rsp+78h+var_4C], bp
0x1800134ac  mov     [rsp+78h+var_48], r14d
0x1800134b1  lea     rbx, [rdi+0E8h]
0x1800134b8  lea     ebp, [rax+0Ch]
0x1800134bb  mov     edx, ebp; unsigned __int64
0x1800134bd  mov     rcx, rbx; this
0x1800134c0  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800134c5  test    al, al
0x1800134c7  jz      short loc_1800134F0
0x1800134c9  mov     rcx, [rbx+8]; Destination
0x1800134cd  mov     rax, [rbx+10h]
0x1800134d1  sub     rax, rcx
0x1800134d4  cmp     rcx, [rbx+10h]
0x1800134d8  sbb     rdx, rdx
0x1800134db  and     rdx, rax; DestinationSize
0x1800134de  mov     r9d, ebp; SourceSize
0x1800134e1  lea     r8, [rsp+78h+Source]; Source
0x1800134e6  call    cs:__imp_memcpy_s
0x1800134ec  add     [rbx+8], rbp
0x1800134f0  cmp     byte ptr [rdi+40h], 0
0x1800134f4  jnz     loc_18001359C
0x1800134fa  mov     rcx, [rdi+38h]
0x1800134fe  test    rcx, rcx
0x180013501  jnz     short loc_18001357B
0x180013503  call    cs:__imp_GetLastError
0x180013509  mov     r14d, eax
0x18001350c  xor     r8d, r8d; pcbe
0x18001350f  mov     rdx, rdi; pv
0x180013512  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180013519  call    cs:__imp_CreateThreadpoolTimer
0x18001351f  mov     r15, rax
0x180013522  mov     rbp, [rdi+38h]
0x180013526  test    rbp, rbp
0x180013529  jz      short loc_180013565
0x18001352b  call    cs:__imp_GetLastError
0x180013531  mov     ebx, eax
0x180013533  xor     r9d, r9d; msWindowLength
0x180013536  xor     r8d, r8d; msPeriod
0x180013539  xor     edx, edx; pftDueTime
0x18001353b  mov     rcx, rbp; pti
0x18001353e  call    cs:__imp_SetThreadpoolTimer
0x180013544  mov     edx, 1; fCancelPendingCallbacks
0x180013549  mov     rcx, rbp; pti
0x18001354c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180013552  mov     rcx, rbp; pti
0x180013555  call    cs:__imp_CloseThreadpoolTimer
0x18001355b  nop
0x18001355c  mov     ecx, ebx; dwErrCode
0x18001355e  call    cs:__imp_SetLastError
0x180013564  nop
0x180013565  mov     [rdi+38h], r15
0x180013569  mov     ecx, r14d; dwErrCode
0x18001356c  call    cs:__imp_SetLastError
0x180013572  mov     rcx, [rdi+38h]; pti
0x180013576  test    rcx, rcx
0x180013579  jz      short loc_18001359C
0x18001357b  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180013584  mov     r9d, 4E2h; msWindowLength
0x18001358a  xor     r8d, r8d; msPeriod
0x18001358d  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x180013592  call    cs:__imp_SetThreadpoolTimer
0x180013598  mov     byte ptr [rdi+40h], 1
0x18001359c  test    rsi, rsi
0x18001359f  jz      short loc_1800135AB
0x1800135a1  mov     rcx, rsi; SRWLock
0x1800135a4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800135aa  nop
0x1800135ab  mov     rcx, [rsp+78h+var_40]
0x1800135b0  xor     rcx, rsp; StackCookie
0x1800135b3  call    __security_check_cookie
0x1800135b8  add     rsp, 48h
0x1800135bc  pop     r15
0x1800135be  pop     r14
0x1800135c0  pop     rdi
0x1800135c1  pop     rsi
0x1800135c2  pop     rbp
0x1800135c3  pop     rbx
0x1800135c4  retn
```
