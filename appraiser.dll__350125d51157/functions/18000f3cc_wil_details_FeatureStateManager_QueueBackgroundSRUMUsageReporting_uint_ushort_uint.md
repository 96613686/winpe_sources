# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000f3cc`
- end: `0x18000f576`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `426`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180012690`

## callees

- `0x18000916e`
- `0x1800092dc`
- `0x18000f3cc`
- `0x180012e6c`
- `0x18021f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f46c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f496`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f46c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f496`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000f4d3`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000f4d3`
- `KERNEL32!SetThreadpoolTimer` at `0x18000f4f8`
- `KERNEL32!SetThreadpoolTimer` at `0x18000f550`
- `KERNEL32!SetThreadpoolTimer` at `0x18000f4f8`
- `KERNEL32!SetThreadpoolTimer` at `0x18000f550`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000f425`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000f425`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000f50f`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000f50f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000f562`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000f562`
- `KERNEL32!GetLastError` at `0x18000f4bd`
- `KERNEL32!GetLastError` at `0x18000f4e5`
- `KERNEL32!GetLastError` at `0x18000f4bd`
- `KERNEL32!GetLastError` at `0x18000f4e5`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000f506`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000f506`
- `KERNEL32!SetLastError` at `0x18000f517`
- `KERNEL32!SetLastError` at `0x18000f524`
- `KERNEL32!SetLastError` at `0x18000f517`
- `KERNEL32!SetLastError` at `0x18000f524`

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
0x18000f3cc  push    rbx
0x18000f3ce  push    rbp
0x18000f3cf  push    rsi
0x18000f3d0  push    rdi
0x18000f3d1  push    r14
0x18000f3d3  push    r15
0x18000f3d5  sub     rsp, 48h
0x18000f3d9  mov     [rsp+78h+var_58], 0FFFFFFFFFFFFFFFEh
0x18000f3e2  mov     ebp, r9d
0x18000f3e5  movzx   ebx, r8w
0x18000f3e9  mov     r14d, edx
0x18000f3ec  mov     rdi, rcx
0x18000f3ef  cmp     byte ptr [rcx], 0
0x18000f3f2  jz      loc_18000F569
0x18000f3f8  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000f3ff  jnz     loc_18000F569
0x18000f405  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000f40c  test    rax, rax
0x18000f40f  jz      short loc_18000F41E
0x18000f411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f416  test    al, al
0x18000f418  jnz     loc_18000F569
0x18000f41e  lea     rsi, [rdi+28h]
0x18000f422  mov     rcx, rsi; SRWLock
0x18000f425  call    cs:__imp_AcquireSRWLockExclusive
0x18000f42b  xor     eax, eax
0x18000f42d  mov     word ptr [rsp+78h+var_50+6], ax
0x18000f432  mov     dword ptr [rsp+78h+var_50], r14d
0x18000f437  mov     word ptr [rsp+78h+var_50+4], bx
0x18000f43c  lea     rbx, [rdi+0E8h]
0x18000f443  lea     edx, [rax+0Ch]; unsigned __int64
0x18000f446  mov     rcx, rbx; this
0x18000f449  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000f44e  test    al, al
0x18000f450  jz      short loc_18000F4AC
0x18000f452  mov     rcx, [rbx+8]; void *
0x18000f456  mov     rax, [rbx+10h]
0x18000f45a  sub     rax, rcx
0x18000f45d  cmp     rcx, [rbx+10h]
0x18000f461  sbb     r8, r8
0x18000f464  and     r8, rax; Size
0x18000f467  test    rcx, rcx
0x18000f46a  jnz     short loc_18000F47A
0x18000f46c  call    cs:__imp__o__errno
0x18000f472  mov     dword ptr [rax], 16h
0x18000f478  jmp     short loc_18000F4A2
0x18000f47a  cmp     r8, 0Ch
0x18000f47e  jb      short loc_18000F48F
0x18000f480  movsd   xmm0, [rsp+78h+var_50]
0x18000f486  movsd   qword ptr [rcx], xmm0
0x18000f48a  mov     [rcx+8], ebp
0x18000f48d  jmp     short loc_18000F4A7
0x18000f48f  xor     edx, edx; Val
0x18000f491  call    memset_0
0x18000f496  call    cs:__imp__o__errno
0x18000f49c  mov     dword ptr [rax], 22h ; '"'
0x18000f4a2  call    _invalid_parameter_noinfo
0x18000f4a7  add     qword ptr [rbx+8], 0Ch
0x18000f4ac  cmp     byte ptr [rdi+40h], 0
0x18000f4b0  jnz     loc_18000F55A
0x18000f4b6  cmp     qword ptr [rdi+38h], 0
0x18000f4bb  jnz     short loc_18000F52A
0x18000f4bd  call    cs:__imp_GetLastError
0x18000f4c3  mov     r14d, eax
0x18000f4c6  xor     r8d, r8d; pcbe
0x18000f4c9  mov     rdx, rdi; pv
0x18000f4cc  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000f4d3  call    cs:__imp_CreateThreadpoolTimer
0x18000f4d9  mov     r15, rax
0x18000f4dc  mov     rbp, [rdi+38h]
0x18000f4e0  test    rbp, rbp
0x18000f4e3  jz      short loc_18000F51D
0x18000f4e5  call    cs:__imp_GetLastError
0x18000f4eb  mov     ebx, eax
0x18000f4ed  xor     r9d, r9d; msWindowLength
0x18000f4f0  xor     r8d, r8d; msPeriod
0x18000f4f3  xor     edx, edx; pftDueTime
0x18000f4f5  mov     rcx, rbp; pti
0x18000f4f8  call    cs:__imp_SetThreadpoolTimer
0x18000f4fe  mov     edx, 1; fCancelPendingCallbacks
0x18000f503  mov     rcx, rbp; pti
0x18000f506  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000f50c  mov     rcx, rbp; pti
0x18000f50f  call    cs:__imp_CloseThreadpoolTimer
0x18000f515  mov     ecx, ebx; dwErrCode
0x18000f517  call    cs:__imp_SetLastError
0x18000f51d  mov     [rdi+38h], r15
0x18000f521  mov     ecx, r14d; dwErrCode
0x18000f524  call    cs:__imp_SetLastError
0x18000f52a  mov     rcx, [rdi+38h]; pti
0x18000f52e  test    rcx, rcx
0x18000f531  jz      short loc_18000F55A
0x18000f533  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000f53f  mov     r9d, 4E2h; msWindowLength
0x18000f545  xor     r8d, r8d; msPeriod
0x18000f548  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18000f550  call    cs:__imp_SetThreadpoolTimer
0x18000f556  mov     byte ptr [rdi+40h], 1
0x18000f55a  test    rsi, rsi
0x18000f55d  jz      short loc_18000F569
0x18000f55f  mov     rcx, rsi; SRWLock
0x18000f562  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f568  nop
0x18000f569  add     rsp, 48h
0x18000f56d  pop     r15
0x18000f56f  pop     r14
0x18000f571  pop     rdi
0x18000f572  pop     rsi
0x18000f573  pop     rbp
0x18000f574  pop     rbx
0x18000f575  retn
```
