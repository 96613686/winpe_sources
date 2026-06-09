# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800094b0`
- end: `0x180009639`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `393`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000abf0`

## callees

- `0x1800094b0`
- `0x18000afc4`
- `0x18000b640`
- `0x18000c010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000955e`
- `msvcrt!memcpy_s` at `0x18000955e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009579`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009579`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800095d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800095e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800095d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800095e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009618`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009618`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000950e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000950e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000958f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000958f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800095c2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800095c2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800095cb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800095cb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800095b4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009606`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800095b4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009606`

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
0x1800094b0  push    rbx
0x1800094b2  push    rbp
0x1800094b3  push    rsi
0x1800094b4  push    rdi
0x1800094b5  push    r14
0x1800094b7  push    r15
0x1800094b9  sub     rsp, 48h
0x1800094bd  mov     rax, cs:__security_cookie
0x1800094c4  xor     rax, rsp
0x1800094c7  mov     [rsp+78h+var_40], rax
0x1800094cc  mov     r14d, r9d
0x1800094cf  movzx   ebp, r8w
0x1800094d3  mov     ebx, edx
0x1800094d5  mov     rdi, rcx
0x1800094d8  cmp     byte ptr [rcx], 0
0x1800094db  jz      loc_18000961F
0x1800094e1  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800094e8  jnz     loc_18000961F
0x1800094ee  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800094f5  test    rax, rax
0x1800094f8  jz      short loc_180009507
0x1800094fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094ff  test    al, al
0x180009501  jnz     loc_18000961F
0x180009507  lea     rsi, [rdi+28h]
0x18000950b  mov     rcx, rsi; SRWLock
0x18000950e  call    cs:__imp_AcquireSRWLockExclusive
0x180009514  xor     eax, eax
0x180009516  mov     [rsp+78h+var_4A], ax
0x18000951b  mov     [rsp+78h+Source], ebx
0x18000951f  mov     [rsp+78h+var_4C], bp
0x180009524  mov     [rsp+78h+var_48], r14d
0x180009529  lea     rbx, [rdi+0E8h]
0x180009530  lea     ebp, [rax+0Ch]
0x180009533  mov     edx, ebp; unsigned __int64
0x180009535  mov     rcx, rbx; this
0x180009538  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000953d  test    al, al
0x18000953f  jz      short loc_180009568
0x180009541  mov     rcx, [rbx+8]; Destination
0x180009545  mov     rax, [rbx+10h]
0x180009549  sub     rax, rcx
0x18000954c  cmp     rcx, [rbx+10h]
0x180009550  sbb     rdx, rdx
0x180009553  and     rdx, rax; DestinationSize
0x180009556  mov     r9d, ebp; SourceSize
0x180009559  lea     r8, [rsp+78h+Source]; Source
0x18000955e  call    cs:__imp_memcpy_s
0x180009564  add     [rbx+8], rbp
0x180009568  cmp     byte ptr [rdi+40h], 0
0x18000956c  jnz     loc_180009610
0x180009572  cmp     qword ptr [rdi+38h], 0
0x180009577  jnz     short loc_1800095E6
0x180009579  call    cs:__imp_GetLastError
0x18000957f  mov     r14d, eax
0x180009582  xor     r8d, r8d; pcbe
0x180009585  mov     rdx, rdi; pv
0x180009588  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000958f  call    cs:__imp_CreateThreadpoolTimer
0x180009595  mov     r15, rax
0x180009598  mov     rbp, [rdi+38h]
0x18000959c  test    rbp, rbp
0x18000959f  jz      short loc_1800095D9
0x1800095a1  call    cs:__imp_GetLastError
0x1800095a7  mov     ebx, eax
0x1800095a9  xor     r9d, r9d; msWindowLength
0x1800095ac  xor     r8d, r8d; msPeriod
0x1800095af  xor     edx, edx; pftDueTime
0x1800095b1  mov     rcx, rbp; pti
0x1800095b4  call    cs:__imp_SetThreadpoolTimer
0x1800095ba  mov     edx, 1; fCancelPendingCallbacks
0x1800095bf  mov     rcx, rbp; pti
0x1800095c2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800095c8  mov     rcx, rbp; pti
0x1800095cb  call    cs:__imp_CloseThreadpoolTimer
0x1800095d1  mov     ecx, ebx; dwErrCode
0x1800095d3  call    cs:__imp_SetLastError
0x1800095d9  mov     [rdi+38h], r15
0x1800095dd  mov     ecx, r14d; dwErrCode
0x1800095e0  call    cs:__imp_SetLastError
0x1800095e6  mov     rcx, [rdi+38h]; pti
0x1800095ea  test    rcx, rcx
0x1800095ed  jz      short loc_180009610
0x1800095ef  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800095f8  mov     r9d, 4E2h; msWindowLength
0x1800095fe  xor     r8d, r8d; msPeriod
0x180009601  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x180009606  call    cs:__imp_SetThreadpoolTimer
0x18000960c  mov     byte ptr [rdi+40h], 1
0x180009610  test    rsi, rsi
0x180009613  jz      short loc_18000961F
0x180009615  mov     rcx, rsi; SRWLock
0x180009618  call    cs:__imp_ReleaseSRWLockExclusive
0x18000961e  nop
0x18000961f  mov     rcx, [rsp+78h+var_40]
0x180009624  xor     rcx, rsp; StackCookie
0x180009627  call    __security_check_cookie
0x18000962c  add     rsp, 48h
0x180009630  pop     r15
0x180009632  pop     r14
0x180009634  pop     rdi
0x180009635  pop     rsi
0x180009636  pop     rbp
0x180009637  pop     rbx
0x180009638  retn
```
