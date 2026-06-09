# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000a018`
- end: `0x18000a1b3`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000dae0`

## callees

- `0x180002d6a`
- `0x180002de0`
- `0x18000a018`
- `0x18000eb4c`
- `0x180012010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a0af`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a0d9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a0af`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a0d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a19f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a19f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a068`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a068`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a15a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a167`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a15a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a167`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a100`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a128`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a100`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a128`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a152`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a152`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a13b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a18d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a13b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a18d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a116`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a116`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a149`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a149`

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
0x18000a018  push    rbx
0x18000a01a  push    rbp
0x18000a01b  push    rsi
0x18000a01c  push    rdi
0x18000a01d  push    r14
0x18000a01f  push    r15
0x18000a021  sub     rsp, 38h
0x18000a025  mov     ebp, r9d
0x18000a028  movzx   ebx, r8w
0x18000a02c  mov     r14d, edx
0x18000a02f  mov     rdi, rcx
0x18000a032  cmp     byte ptr [rcx], 0
0x18000a035  jz      loc_18000A1A6
0x18000a03b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000a042  jnz     loc_18000A1A6
0x18000a048  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a04f  test    rax, rax
0x18000a052  jz      short loc_18000A061
0x18000a054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a059  test    al, al
0x18000a05b  jnz     loc_18000A1A6
0x18000a061  lea     rsi, [rdi+28h]
0x18000a065  mov     rcx, rsi; SRWLock
0x18000a068  call    cs:__imp_AcquireSRWLockExclusive
0x18000a06e  xor     eax, eax
0x18000a070  mov     word ptr [rsp+68h+var_48+6], ax
0x18000a075  mov     dword ptr [rsp+68h+var_48], r14d
0x18000a07a  mov     word ptr [rsp+68h+var_48+4], bx
0x18000a07f  lea     rbx, [rdi+0E8h]
0x18000a086  lea     edx, [rax+0Ch]; unsigned __int64
0x18000a089  mov     rcx, rbx; this
0x18000a08c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000a091  test    al, al
0x18000a093  jz      short loc_18000A0EF
0x18000a095  mov     rcx, [rbx+8]; void *
0x18000a099  mov     rax, [rbx+10h]
0x18000a09d  sub     rax, rcx
0x18000a0a0  cmp     rcx, [rbx+10h]
0x18000a0a4  sbb     r8, r8
0x18000a0a7  and     r8, rax; Size
0x18000a0aa  test    rcx, rcx
0x18000a0ad  jnz     short loc_18000A0BD
0x18000a0af  call    cs:__imp__o__errno
0x18000a0b5  mov     dword ptr [rax], 16h
0x18000a0bb  jmp     short loc_18000A0E5
0x18000a0bd  cmp     r8, 0Ch
0x18000a0c1  jb      short loc_18000A0D2
0x18000a0c3  movsd   xmm0, [rsp+68h+var_48]
0x18000a0c9  movsd   qword ptr [rcx], xmm0
0x18000a0cd  mov     [rcx+8], ebp
0x18000a0d0  jmp     short loc_18000A0EA
0x18000a0d2  xor     edx, edx; Val
0x18000a0d4  call    memset_0
0x18000a0d9  call    cs:__imp__o__errno
0x18000a0df  mov     dword ptr [rax], 22h ; '"'
0x18000a0e5  call    _invalid_parameter_noinfo
0x18000a0ea  add     qword ptr [rbx+8], 0Ch
0x18000a0ef  cmp     byte ptr [rdi+40h], 0
0x18000a0f3  jnz     loc_18000A197
0x18000a0f9  cmp     qword ptr [rdi+38h], 0
0x18000a0fe  jnz     short loc_18000A16D
0x18000a100  call    cs:__imp_GetLastError
0x18000a106  mov     r14d, eax
0x18000a109  xor     r8d, r8d; pcbe
0x18000a10c  mov     rdx, rdi; pv
0x18000a10f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000a116  call    cs:__imp_CreateThreadpoolTimer
0x18000a11c  mov     r15, rax
0x18000a11f  mov     rbp, [rdi+38h]
0x18000a123  test    rbp, rbp
0x18000a126  jz      short loc_18000A160
0x18000a128  call    cs:__imp_GetLastError
0x18000a12e  mov     ebx, eax
0x18000a130  xor     r9d, r9d; msWindowLength
0x18000a133  xor     r8d, r8d; msPeriod
0x18000a136  xor     edx, edx; pftDueTime
0x18000a138  mov     rcx, rbp; pti
0x18000a13b  call    cs:__imp_SetThreadpoolTimer
0x18000a141  mov     edx, 1; fCancelPendingCallbacks
0x18000a146  mov     rcx, rbp; pti
0x18000a149  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a14f  mov     rcx, rbp; pti
0x18000a152  call    cs:__imp_CloseThreadpoolTimer
0x18000a158  mov     ecx, ebx; dwErrCode
0x18000a15a  call    cs:__imp_SetLastError
0x18000a160  mov     [rdi+38h], r15
0x18000a164  mov     ecx, r14d; dwErrCode
0x18000a167  call    cs:__imp_SetLastError
0x18000a16d  mov     rcx, [rdi+38h]; pti
0x18000a171  test    rcx, rcx
0x18000a174  jz      short loc_18000A197
0x18000a176  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000a17f  mov     r9d, 4E2h; msWindowLength
0x18000a185  xor     r8d, r8d; msPeriod
0x18000a188  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000a18d  call    cs:__imp_SetThreadpoolTimer
0x18000a193  mov     byte ptr [rdi+40h], 1
0x18000a197  test    rsi, rsi
0x18000a19a  jz      short loc_18000A1A6
0x18000a19c  mov     rcx, rsi; SRWLock
0x18000a19f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a1a5  nop
0x18000a1a6  add     rsp, 38h
0x18000a1aa  pop     r15
0x18000a1ac  pop     r14
0x18000a1ae  pop     rdi
0x18000a1af  pop     rsi
0x18000a1b0  pop     rbp
0x18000a1b1  pop     rbx
0x18000a1b2  retn
```
