# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180010fd0`
- end: `0x18001116b`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180013f20`

## callees

- `0x180003ca6`
- `0x180003d14`
- `0x180010fd0`
- `0x180014824`
- `0x18002c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180011067`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180011091`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180011067`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180011091`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011157`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011157`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011020`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011020`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011112`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001111f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011112`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001111f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800110b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800110e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800110b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800110e0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800110ce`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800110ce`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011101`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011101`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800110f3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011145`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800110f3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011145`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001110a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001110a`

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
0x180010fd0  push    rbx
0x180010fd2  push    rbp
0x180010fd3  push    rsi
0x180010fd4  push    rdi
0x180010fd5  push    r14
0x180010fd7  push    r15
0x180010fd9  sub     rsp, 38h
0x180010fdd  mov     ebp, r9d
0x180010fe0  movzx   ebx, r8w
0x180010fe4  mov     r14d, edx
0x180010fe7  mov     rdi, rcx
0x180010fea  cmp     byte ptr [rcx], 0
0x180010fed  jz      loc_18001115E
0x180010ff3  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180010ffa  jnz     loc_18001115E
0x180011000  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180011007  test    rax, rax
0x18001100a  jz      short loc_180011019
0x18001100c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011011  test    al, al
0x180011013  jnz     loc_18001115E
0x180011019  lea     rsi, [rdi+28h]
0x18001101d  mov     rcx, rsi; SRWLock
0x180011020  call    cs:__imp_AcquireSRWLockExclusive
0x180011026  xor     eax, eax
0x180011028  mov     word ptr [rsp+68h+var_48+6], ax
0x18001102d  mov     dword ptr [rsp+68h+var_48], r14d
0x180011032  mov     word ptr [rsp+68h+var_48+4], bx
0x180011037  lea     rbx, [rdi+0E8h]
0x18001103e  lea     edx, [rax+0Ch]; unsigned __int64
0x180011041  mov     rcx, rbx; this
0x180011044  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180011049  test    al, al
0x18001104b  jz      short loc_1800110A7
0x18001104d  mov     rcx, [rbx+8]; void *
0x180011051  mov     rax, [rbx+10h]
0x180011055  sub     rax, rcx
0x180011058  cmp     rcx, [rbx+10h]
0x18001105c  sbb     r8, r8
0x18001105f  and     r8, rax; Size
0x180011062  test    rcx, rcx
0x180011065  jnz     short loc_180011075
0x180011067  call    cs:__imp__o__errno
0x18001106d  mov     dword ptr [rax], 16h
0x180011073  jmp     short loc_18001109D
0x180011075  cmp     r8, 0Ch
0x180011079  jb      short loc_18001108A
0x18001107b  movsd   xmm0, [rsp+68h+var_48]
0x180011081  movsd   qword ptr [rcx], xmm0
0x180011085  mov     [rcx+8], ebp
0x180011088  jmp     short loc_1800110A2
0x18001108a  xor     edx, edx; Val
0x18001108c  call    memset_0
0x180011091  call    cs:__imp__o__errno
0x180011097  mov     dword ptr [rax], 22h ; '"'
0x18001109d  call    _invalid_parameter_noinfo
0x1800110a2  add     qword ptr [rbx+8], 0Ch
0x1800110a7  cmp     byte ptr [rdi+40h], 0
0x1800110ab  jnz     loc_18001114F
0x1800110b1  cmp     qword ptr [rdi+38h], 0
0x1800110b6  jnz     short loc_180011125
0x1800110b8  call    cs:__imp_GetLastError
0x1800110be  mov     r14d, eax
0x1800110c1  xor     r8d, r8d; pcbe
0x1800110c4  mov     rdx, rdi; pv
0x1800110c7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800110ce  call    cs:__imp_CreateThreadpoolTimer
0x1800110d4  mov     r15, rax
0x1800110d7  mov     rbp, [rdi+38h]
0x1800110db  test    rbp, rbp
0x1800110de  jz      short loc_180011118
0x1800110e0  call    cs:__imp_GetLastError
0x1800110e6  mov     ebx, eax
0x1800110e8  xor     r9d, r9d; msWindowLength
0x1800110eb  xor     r8d, r8d; msPeriod
0x1800110ee  xor     edx, edx; pftDueTime
0x1800110f0  mov     rcx, rbp; pti
0x1800110f3  call    cs:__imp_SetThreadpoolTimer
0x1800110f9  mov     edx, 1; fCancelPendingCallbacks
0x1800110fe  mov     rcx, rbp; pti
0x180011101  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180011107  mov     rcx, rbp; pti
0x18001110a  call    cs:__imp_CloseThreadpoolTimer
0x180011110  mov     ecx, ebx; dwErrCode
0x180011112  call    cs:__imp_SetLastError
0x180011118  mov     [rdi+38h], r15
0x18001111c  mov     ecx, r14d; dwErrCode
0x18001111f  call    cs:__imp_SetLastError
0x180011125  mov     rcx, [rdi+38h]; pti
0x180011129  test    rcx, rcx
0x18001112c  jz      short loc_18001114F
0x18001112e  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180011137  mov     r9d, 4E2h; msWindowLength
0x18001113d  xor     r8d, r8d; msPeriod
0x180011140  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180011145  call    cs:__imp_SetThreadpoolTimer
0x18001114b  mov     byte ptr [rdi+40h], 1
0x18001114f  test    rsi, rsi
0x180011152  jz      short loc_18001115E
0x180011154  mov     rcx, rsi; SRWLock
0x180011157  call    cs:__imp_ReleaseSRWLockExclusive
0x18001115d  nop
0x18001115e  add     rsp, 38h
0x180011162  pop     r15
0x180011164  pop     r14
0x180011166  pop     rdi
0x180011167  pop     rsi
0x180011168  pop     rbp
0x180011169  pop     rbx
0x18001116a  retn
```
