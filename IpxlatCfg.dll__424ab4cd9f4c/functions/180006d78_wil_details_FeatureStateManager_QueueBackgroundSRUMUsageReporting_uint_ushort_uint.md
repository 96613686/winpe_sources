# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180006d78`
- end: `0x180006f13`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180009680`

## callees

- `0x1800029ca`
- `0x180002a28`
- `0x180006d78`
- `0x180009d1c`
- `0x180019010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006e0f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006e39`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006e0f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006e39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006eba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006ec7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006eba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006ec7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e88`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006dc8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006dc8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006eff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006eff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006ea9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006ea9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006eb2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006eb2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006e9b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006eed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006e9b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006eed`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006e76`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006e76`

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
0x180006d78  push    rbx
0x180006d7a  push    rbp
0x180006d7b  push    rsi
0x180006d7c  push    rdi
0x180006d7d  push    r14
0x180006d7f  push    r15
0x180006d81  sub     rsp, 38h
0x180006d85  mov     ebp, r9d
0x180006d88  movzx   ebx, r8w
0x180006d8c  mov     r14d, edx
0x180006d8f  mov     rdi, rcx
0x180006d92  cmp     byte ptr [rcx], 0
0x180006d95  jz      loc_180006F06
0x180006d9b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180006da2  jnz     loc_180006F06
0x180006da8  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180006daf  test    rax, rax
0x180006db2  jz      short loc_180006DC1
0x180006db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006db9  test    al, al
0x180006dbb  jnz     loc_180006F06
0x180006dc1  lea     rsi, [rdi+28h]
0x180006dc5  mov     rcx, rsi; SRWLock
0x180006dc8  call    cs:__imp_AcquireSRWLockExclusive
0x180006dce  xor     eax, eax
0x180006dd0  mov     word ptr [rsp+68h+var_48+6], ax
0x180006dd5  mov     dword ptr [rsp+68h+var_48], r14d
0x180006dda  mov     word ptr [rsp+68h+var_48+4], bx
0x180006ddf  lea     rbx, [rdi+0E8h]
0x180006de6  lea     edx, [rax+0Ch]; unsigned __int64
0x180006de9  mov     rcx, rbx; this
0x180006dec  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180006df1  test    al, al
0x180006df3  jz      short loc_180006E4F
0x180006df5  mov     rcx, [rbx+8]; void *
0x180006df9  mov     rax, [rbx+10h]
0x180006dfd  sub     rax, rcx
0x180006e00  cmp     rcx, [rbx+10h]
0x180006e04  sbb     r8, r8
0x180006e07  and     r8, rax; Size
0x180006e0a  test    rcx, rcx
0x180006e0d  jnz     short loc_180006E1D
0x180006e0f  call    cs:__imp__o__errno
0x180006e15  mov     dword ptr [rax], 16h
0x180006e1b  jmp     short loc_180006E45
0x180006e1d  cmp     r8, 0Ch
0x180006e21  jb      short loc_180006E32
0x180006e23  movsd   xmm0, [rsp+68h+var_48]
0x180006e29  movsd   qword ptr [rcx], xmm0
0x180006e2d  mov     [rcx+8], ebp
0x180006e30  jmp     short loc_180006E4A
0x180006e32  xor     edx, edx; Val
0x180006e34  call    memset_0
0x180006e39  call    cs:__imp__o__errno
0x180006e3f  mov     dword ptr [rax], 22h ; '"'
0x180006e45  call    _invalid_parameter_noinfo
0x180006e4a  add     qword ptr [rbx+8], 0Ch
0x180006e4f  cmp     byte ptr [rdi+40h], 0
0x180006e53  jnz     loc_180006EF7
0x180006e59  cmp     qword ptr [rdi+38h], 0
0x180006e5e  jnz     short loc_180006ECD
0x180006e60  call    cs:__imp_GetLastError
0x180006e66  mov     r14d, eax
0x180006e69  xor     r8d, r8d; pcbe
0x180006e6c  mov     rdx, rdi; pv
0x180006e6f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180006e76  call    cs:__imp_CreateThreadpoolTimer
0x180006e7c  mov     r15, rax
0x180006e7f  mov     rbp, [rdi+38h]
0x180006e83  test    rbp, rbp
0x180006e86  jz      short loc_180006EC0
0x180006e88  call    cs:__imp_GetLastError
0x180006e8e  mov     ebx, eax
0x180006e90  xor     r9d, r9d; msWindowLength
0x180006e93  xor     r8d, r8d; msPeriod
0x180006e96  xor     edx, edx; pftDueTime
0x180006e98  mov     rcx, rbp; pti
0x180006e9b  call    cs:__imp_SetThreadpoolTimer
0x180006ea1  mov     edx, 1; fCancelPendingCallbacks
0x180006ea6  mov     rcx, rbp; pti
0x180006ea9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006eaf  mov     rcx, rbp; pti
0x180006eb2  call    cs:__imp_CloseThreadpoolTimer
0x180006eb8  mov     ecx, ebx; dwErrCode
0x180006eba  call    cs:__imp_SetLastError
0x180006ec0  mov     [rdi+38h], r15
0x180006ec4  mov     ecx, r14d; dwErrCode
0x180006ec7  call    cs:__imp_SetLastError
0x180006ecd  mov     rcx, [rdi+38h]; pti
0x180006ed1  test    rcx, rcx
0x180006ed4  jz      short loc_180006EF7
0x180006ed6  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180006edf  mov     r9d, 4E2h; msWindowLength
0x180006ee5  xor     r8d, r8d; msPeriod
0x180006ee8  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180006eed  call    cs:__imp_SetThreadpoolTimer
0x180006ef3  mov     byte ptr [rdi+40h], 1
0x180006ef7  test    rsi, rsi
0x180006efa  jz      short loc_180006F06
0x180006efc  mov     rcx, rsi; SRWLock
0x180006eff  call    cs:__imp_ReleaseSRWLockExclusive
0x180006f05  nop
0x180006f06  add     rsp, 38h
0x180006f0a  pop     r15
0x180006f0c  pop     r14
0x180006f0e  pop     rdi
0x180006f0f  pop     rsi
0x180006f10  pop     rbp
0x180006f11  pop     rbx
0x180006f12  retn
```
