# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x14000d158`
- end: `0x14000d302`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `426`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14000e600`

## callees

- `0x1400035ea`
- `0x14000369c`
- `0x14000d158`
- `0x14000ea94`
- `0x140013010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000d1f8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000d222`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000d1f8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000d222`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000d2ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000d2ee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000d1b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000d1b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d249`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d271`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d249`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d271`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d2a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d2b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d2a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d2b0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000d284`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000d2dc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000d284`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000d2dc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000d25f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000d25f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000d292`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000d292`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000d29b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000d29b`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        unsigned __int16 a3,
        int a4)
{
  _DWORD *Ptr; // rcx
  size_t v9; // r8
  __int64 v10; // rcx
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *v13; // rbp
  DWORD v14; // ebx
  struct _TP_TIMER *v15; // rcx
  __int64 v16; // [rsp+28h] [rbp-50h]
  struct _FILETIME pftDueTime; // [rsp+80h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress(pv) )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  LODWORD(v16) = a2;
  HIDWORD(v16) = a3;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v9 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v9 >= 0xC )
      {
        *(_QWORD *)Ptr = v16;
        Ptr[2] = a4;
LABEL_12:
        pv[30].Ptr = (char *)pv[30].Ptr + 12;
        goto LABEL_13;
      }
      memset_0(Ptr, 0, v9);
      *(_DWORD *)_o__errno(v10) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0) = 22;
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
0x14000d158  push    rbx
0x14000d15a  push    rbp
0x14000d15b  push    rsi
0x14000d15c  push    rdi
0x14000d15d  push    r14
0x14000d15f  push    r15
0x14000d161  sub     rsp, 48h
0x14000d165  mov     [rsp+78h+var_58], 0FFFFFFFFFFFFFFFEh
0x14000d16e  mov     ebp, r9d
0x14000d171  movzx   ebx, r8w
0x14000d175  mov     r14d, edx
0x14000d178  mov     rdi, rcx
0x14000d17b  cmp     byte ptr [rcx], 0
0x14000d17e  jz      loc_14000D2F5
0x14000d184  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000d18b  jnz     loc_14000D2F5
0x14000d191  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000d198  test    rax, rax
0x14000d19b  jz      short loc_14000D1AA
0x14000d19d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d1a2  test    al, al
0x14000d1a4  jnz     loc_14000D2F5
0x14000d1aa  lea     rsi, [rdi+28h]
0x14000d1ae  mov     rcx, rsi; SRWLock
0x14000d1b1  call    cs:__imp_AcquireSRWLockExclusive
0x14000d1b7  xor     eax, eax
0x14000d1b9  mov     word ptr [rsp+78h+var_50+6], ax
0x14000d1be  mov     dword ptr [rsp+78h+var_50], r14d
0x14000d1c3  mov     word ptr [rsp+78h+var_50+4], bx
0x14000d1c8  lea     rbx, [rdi+0E8h]
0x14000d1cf  lea     edx, [rax+0Ch]; unsigned __int64
0x14000d1d2  mov     rcx, rbx; this
0x14000d1d5  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000d1da  test    al, al
0x14000d1dc  jz      short loc_14000D238
0x14000d1de  mov     rcx, [rbx+8]; void *
0x14000d1e2  mov     rax, [rbx+10h]
0x14000d1e6  sub     rax, rcx
0x14000d1e9  cmp     rcx, [rbx+10h]
0x14000d1ed  sbb     r8, r8
0x14000d1f0  and     r8, rax; Size
0x14000d1f3  test    rcx, rcx
0x14000d1f6  jnz     short loc_14000D206
0x14000d1f8  call    cs:__imp__o__errno
0x14000d1fe  mov     dword ptr [rax], 16h
0x14000d204  jmp     short loc_14000D22E
0x14000d206  cmp     r8, 0Ch
0x14000d20a  jb      short loc_14000D21B
0x14000d20c  movsd   xmm0, [rsp+78h+var_50]
0x14000d212  movsd   qword ptr [rcx], xmm0
0x14000d216  mov     [rcx+8], ebp
0x14000d219  jmp     short loc_14000D233
0x14000d21b  xor     edx, edx; Val
0x14000d21d  call    memset_0
0x14000d222  call    cs:__imp__o__errno
0x14000d228  mov     dword ptr [rax], 22h ; '"'
0x14000d22e  call    _invalid_parameter_noinfo
0x14000d233  add     qword ptr [rbx+8], 0Ch
0x14000d238  cmp     byte ptr [rdi+40h], 0
0x14000d23c  jnz     loc_14000D2E6
0x14000d242  cmp     qword ptr [rdi+38h], 0
0x14000d247  jnz     short loc_14000D2B6
0x14000d249  call    cs:__imp_GetLastError
0x14000d24f  mov     r14d, eax
0x14000d252  xor     r8d, r8d; pcbe
0x14000d255  mov     rdx, rdi; pv
0x14000d258  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000d25f  call    cs:__imp_CreateThreadpoolTimer
0x14000d265  mov     r15, rax
0x14000d268  mov     rbp, [rdi+38h]
0x14000d26c  test    rbp, rbp
0x14000d26f  jz      short loc_14000D2A9
0x14000d271  call    cs:__imp_GetLastError
0x14000d277  mov     ebx, eax
0x14000d279  xor     r9d, r9d; msWindowLength
0x14000d27c  xor     r8d, r8d; msPeriod
0x14000d27f  xor     edx, edx; pftDueTime
0x14000d281  mov     rcx, rbp; pti
0x14000d284  call    cs:__imp_SetThreadpoolTimer
0x14000d28a  mov     edx, 1; fCancelPendingCallbacks
0x14000d28f  mov     rcx, rbp; pti
0x14000d292  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000d298  mov     rcx, rbp; pti
0x14000d29b  call    cs:__imp_CloseThreadpoolTimer
0x14000d2a1  mov     ecx, ebx; dwErrCode
0x14000d2a3  call    cs:__imp_SetLastError
0x14000d2a9  mov     [rdi+38h], r15
0x14000d2ad  mov     ecx, r14d; dwErrCode
0x14000d2b0  call    cs:__imp_SetLastError
0x14000d2b6  mov     rcx, [rdi+38h]; pti
0x14000d2ba  test    rcx, rcx
0x14000d2bd  jz      short loc_14000D2E6
0x14000d2bf  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x14000d2cb  mov     r9d, 4E2h; msWindowLength
0x14000d2d1  xor     r8d, r8d; msPeriod
0x14000d2d4  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x14000d2dc  call    cs:__imp_SetThreadpoolTimer
0x14000d2e2  mov     byte ptr [rdi+40h], 1
0x14000d2e6  test    rsi, rsi
0x14000d2e9  jz      short loc_14000D2F5
0x14000d2eb  mov     rcx, rsi; SRWLock
0x14000d2ee  call    cs:__imp_ReleaseSRWLockExclusive
0x14000d2f4  nop
0x14000d2f5  add     rsp, 48h
0x14000d2f9  pop     r15
0x14000d2fb  pop     r14
0x14000d2fd  pop     rdi
0x14000d2fe  pop     rsi
0x14000d2ff  pop     rbp
0x14000d300  pop     rbx
0x14000d301  retn
```
