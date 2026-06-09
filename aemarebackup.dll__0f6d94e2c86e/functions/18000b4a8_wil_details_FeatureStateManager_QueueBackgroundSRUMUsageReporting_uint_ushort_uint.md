# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000b4a8`
- end: `0x18000b643`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000e000`

## callees

- `0x18000584a`
- `0x180005914`
- `0x18000b4a8`
- `0x18000e69c`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b53f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b569`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b53f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b569`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b4f8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b4f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b62f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b62f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b5ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b5f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b5ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b5f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b590`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b590`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5b8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b5cb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b61d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b5cb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b61d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b5e2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b5e2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b5a6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b5a6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b5d9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b5d9`

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
0x18000b4a8  push    rbx
0x18000b4aa  push    rbp
0x18000b4ab  push    rsi
0x18000b4ac  push    rdi
0x18000b4ad  push    r14
0x18000b4af  push    r15
0x18000b4b1  sub     rsp, 38h
0x18000b4b5  mov     ebp, r9d
0x18000b4b8  movzx   ebx, r8w
0x18000b4bc  mov     r14d, edx
0x18000b4bf  mov     rdi, rcx
0x18000b4c2  cmp     byte ptr [rcx], 0
0x18000b4c5  jz      loc_18000B636
0x18000b4cb  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000b4d2  jnz     loc_18000B636
0x18000b4d8  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000b4df  test    rax, rax
0x18000b4e2  jz      short loc_18000B4F1
0x18000b4e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4e9  test    al, al
0x18000b4eb  jnz     loc_18000B636
0x18000b4f1  lea     rsi, [rdi+28h]
0x18000b4f5  mov     rcx, rsi; SRWLock
0x18000b4f8  call    cs:__imp_AcquireSRWLockExclusive
0x18000b4fe  xor     eax, eax
0x18000b500  mov     word ptr [rsp+68h+var_48+6], ax
0x18000b505  mov     dword ptr [rsp+68h+var_48], r14d
0x18000b50a  mov     word ptr [rsp+68h+var_48+4], bx
0x18000b50f  lea     rbx, [rdi+0E8h]
0x18000b516  lea     edx, [rax+0Ch]; unsigned __int64
0x18000b519  mov     rcx, rbx; this
0x18000b51c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000b521  test    al, al
0x18000b523  jz      short loc_18000B57F
0x18000b525  mov     rcx, [rbx+8]; void *
0x18000b529  mov     rax, [rbx+10h]
0x18000b52d  sub     rax, rcx
0x18000b530  cmp     rcx, [rbx+10h]
0x18000b534  sbb     r8, r8
0x18000b537  and     r8, rax; Size
0x18000b53a  test    rcx, rcx
0x18000b53d  jnz     short loc_18000B54D
0x18000b53f  call    cs:__imp__o__errno
0x18000b545  mov     dword ptr [rax], 16h
0x18000b54b  jmp     short loc_18000B575
0x18000b54d  cmp     r8, 0Ch
0x18000b551  jb      short loc_18000B562
0x18000b553  movsd   xmm0, [rsp+68h+var_48]
0x18000b559  movsd   qword ptr [rcx], xmm0
0x18000b55d  mov     [rcx+8], ebp
0x18000b560  jmp     short loc_18000B57A
0x18000b562  xor     edx, edx; Val
0x18000b564  call    memset_0
0x18000b569  call    cs:__imp__o__errno
0x18000b56f  mov     dword ptr [rax], 22h ; '"'
0x18000b575  call    _invalid_parameter_noinfo
0x18000b57a  add     qword ptr [rbx+8], 0Ch
0x18000b57f  cmp     byte ptr [rdi+40h], 0
0x18000b583  jnz     loc_18000B627
0x18000b589  cmp     qword ptr [rdi+38h], 0
0x18000b58e  jnz     short loc_18000B5FD
0x18000b590  call    cs:__imp_GetLastError
0x18000b596  mov     r14d, eax
0x18000b599  xor     r8d, r8d; pcbe
0x18000b59c  mov     rdx, rdi; pv
0x18000b59f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000b5a6  call    cs:__imp_CreateThreadpoolTimer
0x18000b5ac  mov     r15, rax
0x18000b5af  mov     rbp, [rdi+38h]
0x18000b5b3  test    rbp, rbp
0x18000b5b6  jz      short loc_18000B5F0
0x18000b5b8  call    cs:__imp_GetLastError
0x18000b5be  mov     ebx, eax
0x18000b5c0  xor     r9d, r9d; msWindowLength
0x18000b5c3  xor     r8d, r8d; msPeriod
0x18000b5c6  xor     edx, edx; pftDueTime
0x18000b5c8  mov     rcx, rbp; pti
0x18000b5cb  call    cs:__imp_SetThreadpoolTimer
0x18000b5d1  mov     edx, 1; fCancelPendingCallbacks
0x18000b5d6  mov     rcx, rbp; pti
0x18000b5d9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b5df  mov     rcx, rbp; pti
0x18000b5e2  call    cs:__imp_CloseThreadpoolTimer
0x18000b5e8  mov     ecx, ebx; dwErrCode
0x18000b5ea  call    cs:__imp_SetLastError
0x18000b5f0  mov     [rdi+38h], r15
0x18000b5f4  mov     ecx, r14d; dwErrCode
0x18000b5f7  call    cs:__imp_SetLastError
0x18000b5fd  mov     rcx, [rdi+38h]; pti
0x18000b601  test    rcx, rcx
0x18000b604  jz      short loc_18000B627
0x18000b606  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000b60f  mov     r9d, 4E2h; msWindowLength
0x18000b615  xor     r8d, r8d; msPeriod
0x18000b618  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000b61d  call    cs:__imp_SetThreadpoolTimer
0x18000b623  mov     byte ptr [rdi+40h], 1
0x18000b627  test    rsi, rsi
0x18000b62a  jz      short loc_18000B636
0x18000b62c  mov     rcx, rsi; SRWLock
0x18000b62f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b635  nop
0x18000b636  add     rsp, 38h
0x18000b63a  pop     r15
0x18000b63c  pop     r14
0x18000b63e  pop     rdi
0x18000b63f  pop     rsi
0x18000b640  pop     rbp
0x18000b641  pop     rbx
0x18000b642  retn
```
