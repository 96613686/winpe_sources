# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800162e8`
- end: `0x180016483`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001c8d0`

## callees

- `0x180005b3e`
- `0x180005bbc`
- `0x1800162e8`
- `0x18001d754`
- `0x18006f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001637f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800163a9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001637f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800163a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001646f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001646f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016338`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016338`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800163d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800163f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800163d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800163f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001642a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016437`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001642a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016437`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800163e6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800163e6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180016422`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180016422`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001640b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001645d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001640b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001645d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016419`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016419`

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
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *v16; // rbp
  DWORD v17; // ebx
  struct _TP_TIMER *v18; // rcx
  __int64 v19; // [rsp+20h] [rbp-48h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  LODWORD(v19) = a2;
  HIDWORD(v19) = a3;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v10 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v10 >= 0xC )
      {
        *(_QWORD *)Ptr = v19;
        Ptr[2] = a4;
LABEL_12:
        pv[30].Ptr = (char *)pv[30].Ptr + 12;
        goto LABEL_13;
      }
      memset_0(Ptr, 0, v10);
      *(_DWORD *)_o__errno(v12, v11, v13) = 34;
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
      v16 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v16 )
      {
        v17 = GetLastError();
        SetThreadpoolTimer(v16, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v16, 1);
        CloseThreadpoolTimer(v16);
        SetLastError(v17);
      }
      pv[7].Ptr = ThreadpoolTimer;
      SetLastError(LastError);
    }
    v18 = (struct _TP_TIMER *)pv[7].Ptr;
    if ( v18 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v18, &pftDueTime, 0, 0x4E2u);
      LOBYTE(pv[8].Ptr) = 1;
    }
  }
  if ( pv != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(pv + 5);
}

```

## disassembly

```asm
0x1800162e8  push    rbx
0x1800162ea  push    rbp
0x1800162eb  push    rsi
0x1800162ec  push    rdi
0x1800162ed  push    r14
0x1800162ef  push    r15
0x1800162f1  sub     rsp, 38h
0x1800162f5  mov     ebp, r9d
0x1800162f8  movzx   ebx, r8w
0x1800162fc  mov     r14d, edx
0x1800162ff  mov     rdi, rcx
0x180016302  cmp     byte ptr [rcx], 0
0x180016305  jz      loc_180016476
0x18001630b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180016312  jnz     loc_180016476
0x180016318  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001631f  test    rax, rax
0x180016322  jz      short loc_180016331
0x180016324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016329  test    al, al
0x18001632b  jnz     loc_180016476
0x180016331  lea     rsi, [rdi+28h]
0x180016335  mov     rcx, rsi; SRWLock
0x180016338  call    cs:__imp_AcquireSRWLockExclusive
0x18001633e  xor     eax, eax
0x180016340  mov     word ptr [rsp+68h+var_48+6], ax
0x180016345  mov     dword ptr [rsp+68h+var_48], r14d
0x18001634a  mov     word ptr [rsp+68h+var_48+4], bx
0x18001634f  lea     rbx, [rdi+0E8h]
0x180016356  lea     edx, [rax+0Ch]; unsigned __int64
0x180016359  mov     rcx, rbx; this
0x18001635c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180016361  test    al, al
0x180016363  jz      short loc_1800163BF
0x180016365  mov     rcx, [rbx+8]; void *
0x180016369  mov     rax, [rbx+10h]
0x18001636d  sub     rax, rcx
0x180016370  cmp     rcx, [rbx+10h]
0x180016374  sbb     r8, r8
0x180016377  and     r8, rax; Size
0x18001637a  test    rcx, rcx
0x18001637d  jnz     short loc_18001638D
0x18001637f  call    cs:__imp__o__errno
0x180016385  mov     dword ptr [rax], 16h
0x18001638b  jmp     short loc_1800163B5
0x18001638d  cmp     r8, 0Ch
0x180016391  jb      short loc_1800163A2
0x180016393  movsd   xmm0, [rsp+68h+var_48]
0x180016399  movsd   qword ptr [rcx], xmm0
0x18001639d  mov     [rcx+8], ebp
0x1800163a0  jmp     short loc_1800163BA
0x1800163a2  xor     edx, edx; Val
0x1800163a4  call    memset_0
0x1800163a9  call    cs:__imp__o__errno
0x1800163af  mov     dword ptr [rax], 22h ; '"'
0x1800163b5  call    _invalid_parameter_noinfo
0x1800163ba  add     qword ptr [rbx+8], 0Ch
0x1800163bf  cmp     byte ptr [rdi+40h], 0
0x1800163c3  jnz     loc_180016467
0x1800163c9  cmp     qword ptr [rdi+38h], 0
0x1800163ce  jnz     short loc_18001643D
0x1800163d0  call    cs:__imp_GetLastError
0x1800163d6  mov     r14d, eax
0x1800163d9  xor     r8d, r8d; pcbe
0x1800163dc  mov     rdx, rdi; pv
0x1800163df  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800163e6  call    cs:__imp_CreateThreadpoolTimer
0x1800163ec  mov     r15, rax
0x1800163ef  mov     rbp, [rdi+38h]
0x1800163f3  test    rbp, rbp
0x1800163f6  jz      short loc_180016430
0x1800163f8  call    cs:__imp_GetLastError
0x1800163fe  mov     ebx, eax
0x180016400  xor     r9d, r9d; msWindowLength
0x180016403  xor     r8d, r8d; msPeriod
0x180016406  xor     edx, edx; pftDueTime
0x180016408  mov     rcx, rbp; pti
0x18001640b  call    cs:__imp_SetThreadpoolTimer
0x180016411  mov     edx, 1; fCancelPendingCallbacks
0x180016416  mov     rcx, rbp; pti
0x180016419  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001641f  mov     rcx, rbp; pti
0x180016422  call    cs:__imp_CloseThreadpoolTimer
0x180016428  mov     ecx, ebx; dwErrCode
0x18001642a  call    cs:__imp_SetLastError
0x180016430  mov     [rdi+38h], r15
0x180016434  mov     ecx, r14d; dwErrCode
0x180016437  call    cs:__imp_SetLastError
0x18001643d  mov     rcx, [rdi+38h]; pti
0x180016441  test    rcx, rcx
0x180016444  jz      short loc_180016467
0x180016446  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18001644f  mov     r9d, 4E2h; msWindowLength
0x180016455  xor     r8d, r8d; msPeriod
0x180016458  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18001645d  call    cs:__imp_SetThreadpoolTimer
0x180016463  mov     byte ptr [rdi+40h], 1
0x180016467  test    rsi, rsi
0x18001646a  jz      short loc_180016476
0x18001646c  mov     rcx, rsi; SRWLock
0x18001646f  call    cs:__imp_ReleaseSRWLockExclusive
0x180016475  nop
0x180016476  add     rsp, 38h
0x18001647a  pop     r15
0x18001647c  pop     r14
0x18001647e  pop     rdi
0x18001647f  pop     rsi
0x180016480  pop     rbp
0x180016481  pop     rbx
0x180016482  retn
```
