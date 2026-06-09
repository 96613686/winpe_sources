# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000ea9c`
- end: `0x18000ec37`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180011aa0`

## callees

- `0x180005306`
- `0x180005374`
- `0x18000ea9c`
- `0x1800122d4`
- `0x18002e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000eb33`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000eb5d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000eb33`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000eb5d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ec23`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ec23`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000eaec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000eaec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ebac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ebac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ebde`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ebeb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ebde`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ebeb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000eb9a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000eb9a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ebcd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ebcd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ebd6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ebd6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ebbf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ec11`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ebbf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ec11`

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
0x18000ea9c  push    rbx
0x18000ea9e  push    rbp
0x18000ea9f  push    rsi
0x18000eaa0  push    rdi
0x18000eaa1  push    r14
0x18000eaa3  push    r15
0x18000eaa5  sub     rsp, 38h
0x18000eaa9  mov     ebp, r9d
0x18000eaac  movzx   ebx, r8w
0x18000eab0  mov     r14d, edx
0x18000eab3  mov     rdi, rcx
0x18000eab6  cmp     byte ptr [rcx], 0
0x18000eab9  jz      loc_18000EC2A
0x18000eabf  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000eac6  jnz     loc_18000EC2A
0x18000eacc  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ead3  test    rax, rax
0x18000ead6  jz      short loc_18000EAE5
0x18000ead8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eadd  test    al, al
0x18000eadf  jnz     loc_18000EC2A
0x18000eae5  lea     rsi, [rdi+28h]
0x18000eae9  mov     rcx, rsi; SRWLock
0x18000eaec  call    cs:__imp_AcquireSRWLockExclusive
0x18000eaf2  xor     eax, eax
0x18000eaf4  mov     word ptr [rsp+68h+var_48+6], ax
0x18000eaf9  mov     dword ptr [rsp+68h+var_48], r14d
0x18000eafe  mov     word ptr [rsp+68h+var_48+4], bx
0x18000eb03  lea     rbx, [rdi+0E8h]
0x18000eb0a  lea     edx, [rax+0Ch]; unsigned __int64
0x18000eb0d  mov     rcx, rbx; this
0x18000eb10  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000eb15  test    al, al
0x18000eb17  jz      short loc_18000EB73
0x18000eb19  mov     rcx, [rbx+8]; void *
0x18000eb1d  mov     rax, [rbx+10h]
0x18000eb21  sub     rax, rcx
0x18000eb24  cmp     rcx, [rbx+10h]
0x18000eb28  sbb     r8, r8
0x18000eb2b  and     r8, rax; Size
0x18000eb2e  test    rcx, rcx
0x18000eb31  jnz     short loc_18000EB41
0x18000eb33  call    cs:__imp__o__errno
0x18000eb39  mov     dword ptr [rax], 16h
0x18000eb3f  jmp     short loc_18000EB69
0x18000eb41  cmp     r8, 0Ch
0x18000eb45  jb      short loc_18000EB56
0x18000eb47  movsd   xmm0, [rsp+68h+var_48]
0x18000eb4d  movsd   qword ptr [rcx], xmm0
0x18000eb51  mov     [rcx+8], ebp
0x18000eb54  jmp     short loc_18000EB6E
0x18000eb56  xor     edx, edx; Val
0x18000eb58  call    memset_0
0x18000eb5d  call    cs:__imp__o__errno
0x18000eb63  mov     dword ptr [rax], 22h ; '"'
0x18000eb69  call    _invalid_parameter_noinfo
0x18000eb6e  add     qword ptr [rbx+8], 0Ch
0x18000eb73  cmp     byte ptr [rdi+40h], 0
0x18000eb77  jnz     loc_18000EC1B
0x18000eb7d  cmp     qword ptr [rdi+38h], 0
0x18000eb82  jnz     short loc_18000EBF1
0x18000eb84  call    cs:__imp_GetLastError
0x18000eb8a  mov     r14d, eax
0x18000eb8d  xor     r8d, r8d; pcbe
0x18000eb90  mov     rdx, rdi; pv
0x18000eb93  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000eb9a  call    cs:__imp_CreateThreadpoolTimer
0x18000eba0  mov     r15, rax
0x18000eba3  mov     rbp, [rdi+38h]
0x18000eba7  test    rbp, rbp
0x18000ebaa  jz      short loc_18000EBE4
0x18000ebac  call    cs:__imp_GetLastError
0x18000ebb2  mov     ebx, eax
0x18000ebb4  xor     r9d, r9d; msWindowLength
0x18000ebb7  xor     r8d, r8d; msPeriod
0x18000ebba  xor     edx, edx; pftDueTime
0x18000ebbc  mov     rcx, rbp; pti
0x18000ebbf  call    cs:__imp_SetThreadpoolTimer
0x18000ebc5  mov     edx, 1; fCancelPendingCallbacks
0x18000ebca  mov     rcx, rbp; pti
0x18000ebcd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ebd3  mov     rcx, rbp; pti
0x18000ebd6  call    cs:__imp_CloseThreadpoolTimer
0x18000ebdc  mov     ecx, ebx; dwErrCode
0x18000ebde  call    cs:__imp_SetLastError
0x18000ebe4  mov     [rdi+38h], r15
0x18000ebe8  mov     ecx, r14d; dwErrCode
0x18000ebeb  call    cs:__imp_SetLastError
0x18000ebf1  mov     rcx, [rdi+38h]; pti
0x18000ebf5  test    rcx, rcx
0x18000ebf8  jz      short loc_18000EC1B
0x18000ebfa  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000ec03  mov     r9d, 4E2h; msWindowLength
0x18000ec09  xor     r8d, r8d; msPeriod
0x18000ec0c  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000ec11  call    cs:__imp_SetThreadpoolTimer
0x18000ec17  mov     byte ptr [rdi+40h], 1
0x18000ec1b  test    rsi, rsi
0x18000ec1e  jz      short loc_18000EC2A
0x18000ec20  mov     rcx, rsi; SRWLock
0x18000ec23  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ec29  nop
0x18000ec2a  add     rsp, 38h
0x18000ec2e  pop     r15
0x18000ec30  pop     r14
0x18000ec32  pop     rdi
0x18000ec33  pop     rsi
0x18000ec34  pop     rbp
0x18000ec35  pop     rbx
0x18000ec36  retn
```
