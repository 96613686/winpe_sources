# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180005c3c`
- end: `0x180005dd7`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180008230`

## callees

- `0x18000207a`
- `0x1800020e4`
- `0x180005c3c`
- `0x18000885c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005cd3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005cfd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005cd3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005cfd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005c8c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005c8c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005dc3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005dc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005d7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005d8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005d7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005d8b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005d76`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005d76`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005d5f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005db1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005d5f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005db1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005d3a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005d3a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005d6d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005d6d`

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
0x180005c3c  push    rbx
0x180005c3e  push    rbp
0x180005c3f  push    rsi
0x180005c40  push    rdi
0x180005c41  push    r14
0x180005c43  push    r15
0x180005c45  sub     rsp, 38h
0x180005c49  mov     ebp, r9d
0x180005c4c  movzx   ebx, r8w
0x180005c50  mov     r14d, edx
0x180005c53  mov     rdi, rcx
0x180005c56  cmp     byte ptr [rcx], 0
0x180005c59  jz      loc_180005DCA
0x180005c5f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180005c66  jnz     loc_180005DCA
0x180005c6c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180005c73  test    rax, rax
0x180005c76  jz      short loc_180005C85
0x180005c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c7d  test    al, al
0x180005c7f  jnz     loc_180005DCA
0x180005c85  lea     rsi, [rdi+28h]
0x180005c89  mov     rcx, rsi; SRWLock
0x180005c8c  call    cs:__imp_AcquireSRWLockExclusive
0x180005c92  xor     eax, eax
0x180005c94  mov     word ptr [rsp+68h+var_48+6], ax
0x180005c99  mov     dword ptr [rsp+68h+var_48], r14d
0x180005c9e  mov     word ptr [rsp+68h+var_48+4], bx
0x180005ca3  lea     rbx, [rdi+0E8h]
0x180005caa  lea     edx, [rax+0Ch]; unsigned __int64
0x180005cad  mov     rcx, rbx; this
0x180005cb0  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180005cb5  test    al, al
0x180005cb7  jz      short loc_180005D13
0x180005cb9  mov     rcx, [rbx+8]; void *
0x180005cbd  mov     rax, [rbx+10h]
0x180005cc1  sub     rax, rcx
0x180005cc4  cmp     rcx, [rbx+10h]
0x180005cc8  sbb     r8, r8
0x180005ccb  and     r8, rax; Size
0x180005cce  test    rcx, rcx
0x180005cd1  jnz     short loc_180005CE1
0x180005cd3  call    cs:__imp__o__errno
0x180005cd9  mov     dword ptr [rax], 16h
0x180005cdf  jmp     short loc_180005D09
0x180005ce1  cmp     r8, 0Ch
0x180005ce5  jb      short loc_180005CF6
0x180005ce7  movsd   xmm0, [rsp+68h+var_48]
0x180005ced  movsd   qword ptr [rcx], xmm0
0x180005cf1  mov     [rcx+8], ebp
0x180005cf4  jmp     short loc_180005D0E
0x180005cf6  xor     edx, edx; Val
0x180005cf8  call    memset_0
0x180005cfd  call    cs:__imp__o__errno
0x180005d03  mov     dword ptr [rax], 22h ; '"'
0x180005d09  call    _invalid_parameter_noinfo
0x180005d0e  add     qword ptr [rbx+8], 0Ch
0x180005d13  cmp     byte ptr [rdi+40h], 0
0x180005d17  jnz     loc_180005DBB
0x180005d1d  cmp     qword ptr [rdi+38h], 0
0x180005d22  jnz     short loc_180005D91
0x180005d24  call    cs:__imp_GetLastError
0x180005d2a  mov     r14d, eax
0x180005d2d  xor     r8d, r8d; pcbe
0x180005d30  mov     rdx, rdi; pv
0x180005d33  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180005d3a  call    cs:__imp_CreateThreadpoolTimer
0x180005d40  mov     r15, rax
0x180005d43  mov     rbp, [rdi+38h]
0x180005d47  test    rbp, rbp
0x180005d4a  jz      short loc_180005D84
0x180005d4c  call    cs:__imp_GetLastError
0x180005d52  mov     ebx, eax
0x180005d54  xor     r9d, r9d; msWindowLength
0x180005d57  xor     r8d, r8d; msPeriod
0x180005d5a  xor     edx, edx; pftDueTime
0x180005d5c  mov     rcx, rbp; pti
0x180005d5f  call    cs:__imp_SetThreadpoolTimer
0x180005d65  mov     edx, 1; fCancelPendingCallbacks
0x180005d6a  mov     rcx, rbp; pti
0x180005d6d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005d73  mov     rcx, rbp; pti
0x180005d76  call    cs:__imp_CloseThreadpoolTimer
0x180005d7c  mov     ecx, ebx; dwErrCode
0x180005d7e  call    cs:__imp_SetLastError
0x180005d84  mov     [rdi+38h], r15
0x180005d88  mov     ecx, r14d; dwErrCode
0x180005d8b  call    cs:__imp_SetLastError
0x180005d91  mov     rcx, [rdi+38h]; pti
0x180005d95  test    rcx, rcx
0x180005d98  jz      short loc_180005DBB
0x180005d9a  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180005da3  mov     r9d, 4E2h; msWindowLength
0x180005da9  xor     r8d, r8d; msPeriod
0x180005dac  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180005db1  call    cs:__imp_SetThreadpoolTimer
0x180005db7  mov     byte ptr [rdi+40h], 1
0x180005dbb  test    rsi, rsi
0x180005dbe  jz      short loc_180005DCA
0x180005dc0  mov     rcx, rsi; SRWLock
0x180005dc3  call    cs:__imp_ReleaseSRWLockExclusive
0x180005dc9  nop
0x180005dca  add     rsp, 38h
0x180005dce  pop     r15
0x180005dd0  pop     r14
0x180005dd2  pop     rdi
0x180005dd3  pop     rsi
0x180005dd4  pop     rbp
0x180005dd5  pop     rbx
0x180005dd6  retn
```
