# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180006338`
- end: `0x1800064d3`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180008a90`

## callees

- `0x180002766`
- `0x1800027c8`
- `0x180006338`
- `0x18000911c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800063cf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800063f9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800063cf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800063f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800064bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800064bf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006388`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006388`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000647a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006487`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000647a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006487`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006420`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006420`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006448`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000645b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800064ad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000645b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800064ad`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006472`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006472`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006469`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006469`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006436`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006436`

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
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *v13; // rbp
  DWORD v14; // ebx
  struct _TP_TIMER *v15; // rcx
  __int64 v16; // [rsp+20h] [rbp-48h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  LODWORD(v16) = a2;
  HIDWORD(v16) = a3;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v10 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v10 >= 0xC )
      {
        *(_QWORD *)Ptr = v16;
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
0x180006338  push    rbx
0x18000633a  push    rbp
0x18000633b  push    rsi
0x18000633c  push    rdi
0x18000633d  push    r14
0x18000633f  push    r15
0x180006341  sub     rsp, 38h
0x180006345  mov     ebp, r9d
0x180006348  movzx   ebx, r8w
0x18000634c  mov     r14d, edx
0x18000634f  mov     rdi, rcx
0x180006352  cmp     byte ptr [rcx], 0
0x180006355  jz      loc_1800064C6
0x18000635b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180006362  jnz     loc_1800064C6
0x180006368  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000636f  test    rax, rax
0x180006372  jz      short loc_180006381
0x180006374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006379  test    al, al
0x18000637b  jnz     loc_1800064C6
0x180006381  lea     rsi, [rdi+28h]
0x180006385  mov     rcx, rsi; SRWLock
0x180006388  call    cs:__imp_AcquireSRWLockExclusive
0x18000638e  xor     eax, eax
0x180006390  mov     word ptr [rsp+68h+var_48+6], ax
0x180006395  mov     dword ptr [rsp+68h+var_48], r14d
0x18000639a  mov     word ptr [rsp+68h+var_48+4], bx
0x18000639f  lea     rbx, [rdi+0E8h]
0x1800063a6  lea     edx, [rax+0Ch]; unsigned __int64
0x1800063a9  mov     rcx, rbx; this
0x1800063ac  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800063b1  test    al, al
0x1800063b3  jz      short loc_18000640F
0x1800063b5  mov     rcx, [rbx+8]; void *
0x1800063b9  mov     rax, [rbx+10h]
0x1800063bd  sub     rax, rcx
0x1800063c0  cmp     rcx, [rbx+10h]
0x1800063c4  sbb     r8, r8
0x1800063c7  and     r8, rax; Size
0x1800063ca  test    rcx, rcx
0x1800063cd  jnz     short loc_1800063DD
0x1800063cf  call    cs:__imp__o__errno
0x1800063d5  mov     dword ptr [rax], 16h
0x1800063db  jmp     short loc_180006405
0x1800063dd  cmp     r8, 0Ch
0x1800063e1  jb      short loc_1800063F2
0x1800063e3  movsd   xmm0, [rsp+68h+var_48]
0x1800063e9  movsd   qword ptr [rcx], xmm0
0x1800063ed  mov     [rcx+8], ebp
0x1800063f0  jmp     short loc_18000640A
0x1800063f2  xor     edx, edx; Val
0x1800063f4  call    memset_0
0x1800063f9  call    cs:__imp__o__errno
0x1800063ff  mov     dword ptr [rax], 22h ; '"'
0x180006405  call    _invalid_parameter_noinfo
0x18000640a  add     qword ptr [rbx+8], 0Ch
0x18000640f  cmp     byte ptr [rdi+40h], 0
0x180006413  jnz     loc_1800064B7
0x180006419  cmp     qword ptr [rdi+38h], 0
0x18000641e  jnz     short loc_18000648D
0x180006420  call    cs:__imp_GetLastError
0x180006426  mov     r14d, eax
0x180006429  xor     r8d, r8d; pcbe
0x18000642c  mov     rdx, rdi; pv
0x18000642f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180006436  call    cs:__imp_CreateThreadpoolTimer
0x18000643c  mov     r15, rax
0x18000643f  mov     rbp, [rdi+38h]
0x180006443  test    rbp, rbp
0x180006446  jz      short loc_180006480
0x180006448  call    cs:__imp_GetLastError
0x18000644e  mov     ebx, eax
0x180006450  xor     r9d, r9d; msWindowLength
0x180006453  xor     r8d, r8d; msPeriod
0x180006456  xor     edx, edx; pftDueTime
0x180006458  mov     rcx, rbp; pti
0x18000645b  call    cs:__imp_SetThreadpoolTimer
0x180006461  mov     edx, 1; fCancelPendingCallbacks
0x180006466  mov     rcx, rbp; pti
0x180006469  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000646f  mov     rcx, rbp; pti
0x180006472  call    cs:__imp_CloseThreadpoolTimer
0x180006478  mov     ecx, ebx; dwErrCode
0x18000647a  call    cs:__imp_SetLastError
0x180006480  mov     [rdi+38h], r15
0x180006484  mov     ecx, r14d; dwErrCode
0x180006487  call    cs:__imp_SetLastError
0x18000648d  mov     rcx, [rdi+38h]; pti
0x180006491  test    rcx, rcx
0x180006494  jz      short loc_1800064B7
0x180006496  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000649f  mov     r9d, 4E2h; msWindowLength
0x1800064a5  xor     r8d, r8d; msPeriod
0x1800064a8  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x1800064ad  call    cs:__imp_SetThreadpoolTimer
0x1800064b3  mov     byte ptr [rdi+40h], 1
0x1800064b7  test    rsi, rsi
0x1800064ba  jz      short loc_1800064C6
0x1800064bc  mov     rcx, rsi; SRWLock
0x1800064bf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800064c5  nop
0x1800064c6  add     rsp, 38h
0x1800064ca  pop     r15
0x1800064cc  pop     r14
0x1800064ce  pop     rdi
0x1800064cf  pop     rsi
0x1800064d0  pop     rbp
0x1800064d1  pop     rbx
0x1800064d2  retn
```
