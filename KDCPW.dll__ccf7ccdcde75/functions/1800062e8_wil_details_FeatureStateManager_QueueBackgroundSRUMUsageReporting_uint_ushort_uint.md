# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800062e8`
- end: `0x180006482`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `410`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180008960`

## callees

- `0x180001f32`
- `0x180001f88`
- `0x1800062e8`
- `0x180008f3c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000637f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800063a9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000637f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800063a9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006338`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006338`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000646f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000646f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000642a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006437`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000642a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006437`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000640b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000645d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000640b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000645d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006422`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006422`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006419`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006419`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800063e6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800063e6`

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
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v16; // rbp
  PTP_TIMER v17; // r15
  DWORD v18; // ebx
  struct _TP_TIMER *v19; // rcx
  __int64 v20; // [rsp+20h] [rbp-48h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  HIDWORD(v20) = a3;
  LODWORD(v20) = a2;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v10 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v10 >= 0xC )
      {
        *(_QWORD *)Ptr = v20;
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
      v17 = ThreadpoolTimer;
      if ( v16 )
      {
        v18 = GetLastError();
        SetThreadpoolTimer(v16, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v16, 1);
        CloseThreadpoolTimer(v16);
        SetLastError(v18);
      }
      pv[7].Ptr = v17;
      SetLastError(LastError);
    }
    v19 = (struct _TP_TIMER *)pv[7].Ptr;
    if ( v19 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v19, &pftDueTime, 0, 0x4E2u);
      LOBYTE(pv[8].Ptr) = 1;
    }
  }
  if ( pv != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(pv + 5);
}

```

## disassembly

```asm
0x1800062e8  push    rbx
0x1800062ea  push    rbp
0x1800062eb  push    rsi
0x1800062ec  push    rdi
0x1800062ed  push    r14
0x1800062ef  push    r15
0x1800062f1  sub     rsp, 38h
0x1800062f5  cmp     byte ptr [rcx], 0
0x1800062f8  mov     ebp, r9d
0x1800062fb  movzx   ebx, r8w
0x1800062ff  mov     r14d, edx
0x180006302  mov     rdi, rcx
0x180006305  jz      loc_180006475
0x18000630b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180006312  jnz     loc_180006475
0x180006318  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000631f  test    rax, rax
0x180006322  jz      short loc_180006331
0x180006324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006329  test    al, al
0x18000632b  jnz     loc_180006475
0x180006331  lea     rsi, [rdi+28h]
0x180006335  mov     rcx, rsi; SRWLock
0x180006338  call    cs:__imp_AcquireSRWLockExclusive
0x18000633e  xor     eax, eax
0x180006340  mov     word ptr [rsp+68h+var_48+4], bx
0x180006345  lea     rbx, [rdi+0E8h]
0x18000634c  mov     word ptr [rsp+68h+var_48+6], ax
0x180006351  mov     rcx, rbx; this
0x180006354  mov     dword ptr [rsp+68h+var_48], r14d
0x180006359  lea     edx, [rax+0Ch]; unsigned __int64
0x18000635c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180006361  test    al, al
0x180006363  jz      short loc_1800063BF
0x180006365  mov     rcx, [rbx+8]; void *
0x180006369  mov     rax, [rbx+10h]
0x18000636d  sub     rax, rcx
0x180006370  cmp     rcx, [rbx+10h]
0x180006374  sbb     r8, r8
0x180006377  and     r8, rax; Size
0x18000637a  test    rcx, rcx
0x18000637d  jnz     short loc_18000638D
0x18000637f  call    cs:__imp__o__errno
0x180006385  mov     dword ptr [rax], 16h
0x18000638b  jmp     short loc_1800063B5
0x18000638d  cmp     r8, 0Ch
0x180006391  jb      short loc_1800063A2
0x180006393  movsd   xmm0, [rsp+68h+var_48]
0x180006399  movsd   qword ptr [rcx], xmm0
0x18000639d  mov     [rcx+8], ebp
0x1800063a0  jmp     short loc_1800063BA
0x1800063a2  xor     edx, edx; Val
0x1800063a4  call    memset_0
0x1800063a9  call    cs:__imp__o__errno
0x1800063af  mov     dword ptr [rax], 22h ; '"'
0x1800063b5  call    _invalid_parameter_noinfo
0x1800063ba  add     qword ptr [rbx+8], 0Ch
0x1800063bf  cmp     byte ptr [rdi+40h], 0
0x1800063c3  jnz     loc_180006467
0x1800063c9  cmp     qword ptr [rdi+38h], 0
0x1800063ce  jnz     short loc_18000643D
0x1800063d0  call    cs:__imp_GetLastError
0x1800063d6  xor     r8d, r8d; pcbe
0x1800063d9  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800063e0  mov     rdx, rdi; pv
0x1800063e3  mov     r14d, eax
0x1800063e6  call    cs:__imp_CreateThreadpoolTimer
0x1800063ec  mov     rbp, [rdi+38h]
0x1800063f0  mov     r15, rax
0x1800063f3  test    rbp, rbp
0x1800063f6  jz      short loc_180006430
0x1800063f8  call    cs:__imp_GetLastError
0x1800063fe  xor     r9d, r9d; msWindowLength
0x180006401  xor     r8d, r8d; msPeriod
0x180006404  xor     edx, edx; pftDueTime
0x180006406  mov     rcx, rbp; pti
0x180006409  mov     ebx, eax
0x18000640b  call    cs:__imp_SetThreadpoolTimer
0x180006411  mov     edx, 1; fCancelPendingCallbacks
0x180006416  mov     rcx, rbp; pti
0x180006419  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000641f  mov     rcx, rbp; pti
0x180006422  call    cs:__imp_CloseThreadpoolTimer
0x180006428  mov     ecx, ebx; dwErrCode
0x18000642a  call    cs:__imp_SetLastError
0x180006430  mov     ecx, r14d; dwErrCode
0x180006433  mov     [rdi+38h], r15
0x180006437  call    cs:__imp_SetLastError
0x18000643d  mov     rcx, [rdi+38h]; pti
0x180006441  test    rcx, rcx
0x180006444  jz      short loc_180006467
0x180006446  mov     r9d, 4E2h; msWindowLength
0x18000644c  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180006455  xor     r8d, r8d; msPeriod
0x180006458  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000645d  call    cs:__imp_SetThreadpoolTimer
0x180006463  mov     byte ptr [rdi+40h], 1
0x180006467  test    rsi, rsi
0x18000646a  jz      short loc_180006475
0x18000646c  mov     rcx, rsi; SRWLock
0x18000646f  call    cs:__imp_ReleaseSRWLockExclusive
0x180006475  add     rsp, 38h
0x180006479  pop     r15
0x18000647b  pop     r14
0x18000647d  pop     rdi
0x18000647e  pop     rsi
0x18000647f  pop     rbp
0x180006480  pop     rbx
0x180006481  retn
```
