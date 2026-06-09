# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180005fe8`
- end: `0x180006182`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `410`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800081a0`

## callees

- `0x180002652`
- `0x1800026b4`
- `0x180005fe8`
- `0x18000877c`
- `0x180023010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000607f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800060a9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000607f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800060a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000616f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000616f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006038`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006038`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000612a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006137`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000612a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006137`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060f8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006119`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006119`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006122`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006122`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800060e6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800060e6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000610b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000615d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000610b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000615d`

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
0x180005fe8  push    rbx
0x180005fea  push    rbp
0x180005feb  push    rsi
0x180005fec  push    rdi
0x180005fed  push    r14
0x180005fef  push    r15
0x180005ff1  sub     rsp, 38h
0x180005ff5  cmp     byte ptr [rcx], 0
0x180005ff8  mov     ebp, r9d
0x180005ffb  movzx   ebx, r8w
0x180005fff  mov     r14d, edx
0x180006002  mov     rdi, rcx
0x180006005  jz      loc_180006175
0x18000600b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180006012  jnz     loc_180006175
0x180006018  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000601f  test    rax, rax
0x180006022  jz      short loc_180006031
0x180006024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006029  test    al, al
0x18000602b  jnz     loc_180006175
0x180006031  lea     rsi, [rdi+28h]
0x180006035  mov     rcx, rsi; SRWLock
0x180006038  call    cs:__imp_AcquireSRWLockExclusive
0x18000603e  xor     eax, eax
0x180006040  mov     word ptr [rsp+68h+var_48+4], bx
0x180006045  lea     rbx, [rdi+0E8h]
0x18000604c  mov     word ptr [rsp+68h+var_48+6], ax
0x180006051  mov     rcx, rbx; this
0x180006054  mov     dword ptr [rsp+68h+var_48], r14d
0x180006059  lea     edx, [rax+0Ch]; unsigned __int64
0x18000605c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180006061  test    al, al
0x180006063  jz      short loc_1800060BF
0x180006065  mov     rcx, [rbx+8]; void *
0x180006069  mov     rax, [rbx+10h]
0x18000606d  sub     rax, rcx
0x180006070  cmp     rcx, [rbx+10h]
0x180006074  sbb     r8, r8
0x180006077  and     r8, rax; Size
0x18000607a  test    rcx, rcx
0x18000607d  jnz     short loc_18000608D
0x18000607f  call    cs:__imp__o__errno
0x180006085  mov     dword ptr [rax], 16h
0x18000608b  jmp     short loc_1800060B5
0x18000608d  cmp     r8, 0Ch
0x180006091  jb      short loc_1800060A2
0x180006093  movsd   xmm0, [rsp+68h+var_48]
0x180006099  movsd   qword ptr [rcx], xmm0
0x18000609d  mov     [rcx+8], ebp
0x1800060a0  jmp     short loc_1800060BA
0x1800060a2  xor     edx, edx; Val
0x1800060a4  call    memset_0
0x1800060a9  call    cs:__imp__o__errno
0x1800060af  mov     dword ptr [rax], 22h ; '"'
0x1800060b5  call    _invalid_parameter_noinfo
0x1800060ba  add     qword ptr [rbx+8], 0Ch
0x1800060bf  cmp     byte ptr [rdi+40h], 0
0x1800060c3  jnz     loc_180006167
0x1800060c9  cmp     qword ptr [rdi+38h], 0
0x1800060ce  jnz     short loc_18000613D
0x1800060d0  call    cs:__imp_GetLastError
0x1800060d6  xor     r8d, r8d; pcbe
0x1800060d9  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800060e0  mov     rdx, rdi; pv
0x1800060e3  mov     r14d, eax
0x1800060e6  call    cs:__imp_CreateThreadpoolTimer
0x1800060ec  mov     rbp, [rdi+38h]
0x1800060f0  mov     r15, rax
0x1800060f3  test    rbp, rbp
0x1800060f6  jz      short loc_180006130
0x1800060f8  call    cs:__imp_GetLastError
0x1800060fe  xor     r9d, r9d; msWindowLength
0x180006101  xor     r8d, r8d; msPeriod
0x180006104  xor     edx, edx; pftDueTime
0x180006106  mov     rcx, rbp; pti
0x180006109  mov     ebx, eax
0x18000610b  call    cs:__imp_SetThreadpoolTimer
0x180006111  mov     edx, 1; fCancelPendingCallbacks
0x180006116  mov     rcx, rbp; pti
0x180006119  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000611f  mov     rcx, rbp; pti
0x180006122  call    cs:__imp_CloseThreadpoolTimer
0x180006128  mov     ecx, ebx; dwErrCode
0x18000612a  call    cs:__imp_SetLastError
0x180006130  mov     ecx, r14d; dwErrCode
0x180006133  mov     [rdi+38h], r15
0x180006137  call    cs:__imp_SetLastError
0x18000613d  mov     rcx, [rdi+38h]; pti
0x180006141  test    rcx, rcx
0x180006144  jz      short loc_180006167
0x180006146  mov     r9d, 4E2h; msWindowLength
0x18000614c  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180006155  xor     r8d, r8d; msPeriod
0x180006158  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000615d  call    cs:__imp_SetThreadpoolTimer
0x180006163  mov     byte ptr [rdi+40h], 1
0x180006167  test    rsi, rsi
0x18000616a  jz      short loc_180006175
0x18000616c  mov     rcx, rsi; SRWLock
0x18000616f  call    cs:__imp_ReleaseSRWLockExclusive
0x180006175  add     rsp, 38h
0x180006179  pop     r15
0x18000617b  pop     r14
0x18000617d  pop     rdi
0x18000617e  pop     rsi
0x18000617f  pop     rbp
0x180006180  pop     rbx
0x180006181  retn
```
