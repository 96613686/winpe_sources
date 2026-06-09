# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x140014c78`
- end: `0x140014e13`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140019760`

## callees

- `0x140004d6e`
- `0x140004e28`
- `0x140014c78`
- `0x14001d160`
- `0x14005d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014d0f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014d39`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014d0f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014d39`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014dff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014dff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014cc8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014cc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014d60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014d88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014d60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014d88`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140014dba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140014dc7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140014dba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140014dc7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140014d76`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140014d76`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140014db2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140014db2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140014d9b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140014ded`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140014d9b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140014ded`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140014da9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140014da9`

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
0x140014c78  push    rbx
0x140014c7a  push    rbp
0x140014c7b  push    rsi
0x140014c7c  push    rdi
0x140014c7d  push    r14
0x140014c7f  push    r15
0x140014c81  sub     rsp, 38h
0x140014c85  mov     ebp, r9d
0x140014c88  movzx   ebx, r8w
0x140014c8c  mov     r14d, edx
0x140014c8f  mov     rdi, rcx
0x140014c92  cmp     byte ptr [rcx], 0
0x140014c95  jz      loc_140014E06
0x140014c9b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140014ca2  jnz     loc_140014E06
0x140014ca8  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140014caf  test    rax, rax
0x140014cb2  jz      short loc_140014CC1
0x140014cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014cb9  test    al, al
0x140014cbb  jnz     loc_140014E06
0x140014cc1  lea     rsi, [rdi+28h]
0x140014cc5  mov     rcx, rsi; SRWLock
0x140014cc8  call    cs:__imp_AcquireSRWLockExclusive
0x140014cce  xor     eax, eax
0x140014cd0  mov     word ptr [rsp+68h+var_48+6], ax
0x140014cd5  mov     dword ptr [rsp+68h+var_48], r14d
0x140014cda  mov     word ptr [rsp+68h+var_48+4], bx
0x140014cdf  lea     rbx, [rdi+0E8h]
0x140014ce6  lea     edx, [rax+0Ch]; unsigned __int64
0x140014ce9  mov     rcx, rbx; this
0x140014cec  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140014cf1  test    al, al
0x140014cf3  jz      short loc_140014D4F
0x140014cf5  mov     rcx, [rbx+8]; void *
0x140014cf9  mov     rax, [rbx+10h]
0x140014cfd  sub     rax, rcx
0x140014d00  cmp     rcx, [rbx+10h]
0x140014d04  sbb     r8, r8
0x140014d07  and     r8, rax; Size
0x140014d0a  test    rcx, rcx
0x140014d0d  jnz     short loc_140014D1D
0x140014d0f  call    cs:__imp__o__errno
0x140014d15  mov     dword ptr [rax], 16h
0x140014d1b  jmp     short loc_140014D45
0x140014d1d  cmp     r8, 0Ch
0x140014d21  jb      short loc_140014D32
0x140014d23  movsd   xmm0, [rsp+68h+var_48]
0x140014d29  movsd   qword ptr [rcx], xmm0
0x140014d2d  mov     [rcx+8], ebp
0x140014d30  jmp     short loc_140014D4A
0x140014d32  xor     edx, edx; Val
0x140014d34  call    memset_0
0x140014d39  call    cs:__imp__o__errno
0x140014d3f  mov     dword ptr [rax], 22h ; '"'
0x140014d45  call    _invalid_parameter_noinfo
0x140014d4a  add     qword ptr [rbx+8], 0Ch
0x140014d4f  cmp     byte ptr [rdi+40h], 0
0x140014d53  jnz     loc_140014DF7
0x140014d59  cmp     qword ptr [rdi+38h], 0
0x140014d5e  jnz     short loc_140014DCD
0x140014d60  call    cs:__imp_GetLastError
0x140014d66  mov     r14d, eax
0x140014d69  xor     r8d, r8d; pcbe
0x140014d6c  mov     rdx, rdi; pv
0x140014d6f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140014d76  call    cs:__imp_CreateThreadpoolTimer
0x140014d7c  mov     r15, rax
0x140014d7f  mov     rbp, [rdi+38h]
0x140014d83  test    rbp, rbp
0x140014d86  jz      short loc_140014DC0
0x140014d88  call    cs:__imp_GetLastError
0x140014d8e  mov     ebx, eax
0x140014d90  xor     r9d, r9d; msWindowLength
0x140014d93  xor     r8d, r8d; msPeriod
0x140014d96  xor     edx, edx; pftDueTime
0x140014d98  mov     rcx, rbp; pti
0x140014d9b  call    cs:__imp_SetThreadpoolTimer
0x140014da1  mov     edx, 1; fCancelPendingCallbacks
0x140014da6  mov     rcx, rbp; pti
0x140014da9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140014daf  mov     rcx, rbp; pti
0x140014db2  call    cs:__imp_CloseThreadpoolTimer
0x140014db8  mov     ecx, ebx; dwErrCode
0x140014dba  call    cs:__imp_SetLastError
0x140014dc0  mov     [rdi+38h], r15
0x140014dc4  mov     ecx, r14d; dwErrCode
0x140014dc7  call    cs:__imp_SetLastError
0x140014dcd  mov     rcx, [rdi+38h]; pti
0x140014dd1  test    rcx, rcx
0x140014dd4  jz      short loc_140014DF7
0x140014dd6  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x140014ddf  mov     r9d, 4E2h; msWindowLength
0x140014de5  xor     r8d, r8d; msPeriod
0x140014de8  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x140014ded  call    cs:__imp_SetThreadpoolTimer
0x140014df3  mov     byte ptr [rdi+40h], 1
0x140014df7  test    rsi, rsi
0x140014dfa  jz      short loc_140014E06
0x140014dfc  mov     rcx, rsi; SRWLock
0x140014dff  call    cs:__imp_ReleaseSRWLockExclusive
0x140014e05  nop
0x140014e06  add     rsp, 38h
0x140014e0a  pop     r15
0x140014e0c  pop     r14
0x140014e0e  pop     rdi
0x140014e0f  pop     rsi
0x140014e10  pop     rbp
0x140014e11  pop     rbx
0x140014e12  retn
```
