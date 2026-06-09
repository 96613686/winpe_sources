# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000599c`
- end: `0x180005b37`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180007f20`

## callees

- `0x18000212a`
- `0x180002194`
- `0x18000599c`
- `0x18000854c`
- `0x180011010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005a33`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005a5d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005a33`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005a5d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800059ec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800059ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005b23`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005b23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005aac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005aac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005ade`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005aeb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005ade`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005aeb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005ad6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005ad6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005abf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005b11`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005abf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005b11`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005a9a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005a9a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005acd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005acd`

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
0x18000599c  push    rbx
0x18000599e  push    rbp
0x18000599f  push    rsi
0x1800059a0  push    rdi
0x1800059a1  push    r14
0x1800059a3  push    r15
0x1800059a5  sub     rsp, 38h
0x1800059a9  mov     ebp, r9d
0x1800059ac  movzx   ebx, r8w
0x1800059b0  mov     r14d, edx
0x1800059b3  mov     rdi, rcx
0x1800059b6  cmp     byte ptr [rcx], 0
0x1800059b9  jz      loc_180005B2A
0x1800059bf  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800059c6  jnz     loc_180005B2A
0x1800059cc  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800059d3  test    rax, rax
0x1800059d6  jz      short loc_1800059E5
0x1800059d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059dd  test    al, al
0x1800059df  jnz     loc_180005B2A
0x1800059e5  lea     rsi, [rdi+28h]
0x1800059e9  mov     rcx, rsi; SRWLock
0x1800059ec  call    cs:__imp_AcquireSRWLockExclusive
0x1800059f2  xor     eax, eax
0x1800059f4  mov     word ptr [rsp+68h+var_48+6], ax
0x1800059f9  mov     dword ptr [rsp+68h+var_48], r14d
0x1800059fe  mov     word ptr [rsp+68h+var_48+4], bx
0x180005a03  lea     rbx, [rdi+0E8h]
0x180005a0a  lea     edx, [rax+0Ch]; unsigned __int64
0x180005a0d  mov     rcx, rbx; this
0x180005a10  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180005a15  test    al, al
0x180005a17  jz      short loc_180005A73
0x180005a19  mov     rcx, [rbx+8]; void *
0x180005a1d  mov     rax, [rbx+10h]
0x180005a21  sub     rax, rcx
0x180005a24  cmp     rcx, [rbx+10h]
0x180005a28  sbb     r8, r8
0x180005a2b  and     r8, rax; Size
0x180005a2e  test    rcx, rcx
0x180005a31  jnz     short loc_180005A41
0x180005a33  call    cs:__imp__o__errno
0x180005a39  mov     dword ptr [rax], 16h
0x180005a3f  jmp     short loc_180005A69
0x180005a41  cmp     r8, 0Ch
0x180005a45  jb      short loc_180005A56
0x180005a47  movsd   xmm0, [rsp+68h+var_48]
0x180005a4d  movsd   qword ptr [rcx], xmm0
0x180005a51  mov     [rcx+8], ebp
0x180005a54  jmp     short loc_180005A6E
0x180005a56  xor     edx, edx; Val
0x180005a58  call    memset_0
0x180005a5d  call    cs:__imp__o__errno
0x180005a63  mov     dword ptr [rax], 22h ; '"'
0x180005a69  call    _invalid_parameter_noinfo
0x180005a6e  add     qword ptr [rbx+8], 0Ch
0x180005a73  cmp     byte ptr [rdi+40h], 0
0x180005a77  jnz     loc_180005B1B
0x180005a7d  cmp     qword ptr [rdi+38h], 0
0x180005a82  jnz     short loc_180005AF1
0x180005a84  call    cs:__imp_GetLastError
0x180005a8a  mov     r14d, eax
0x180005a8d  xor     r8d, r8d; pcbe
0x180005a90  mov     rdx, rdi; pv
0x180005a93  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180005a9a  call    cs:__imp_CreateThreadpoolTimer
0x180005aa0  mov     r15, rax
0x180005aa3  mov     rbp, [rdi+38h]
0x180005aa7  test    rbp, rbp
0x180005aaa  jz      short loc_180005AE4
0x180005aac  call    cs:__imp_GetLastError
0x180005ab2  mov     ebx, eax
0x180005ab4  xor     r9d, r9d; msWindowLength
0x180005ab7  xor     r8d, r8d; msPeriod
0x180005aba  xor     edx, edx; pftDueTime
0x180005abc  mov     rcx, rbp; pti
0x180005abf  call    cs:__imp_SetThreadpoolTimer
0x180005ac5  mov     edx, 1; fCancelPendingCallbacks
0x180005aca  mov     rcx, rbp; pti
0x180005acd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005ad3  mov     rcx, rbp; pti
0x180005ad6  call    cs:__imp_CloseThreadpoolTimer
0x180005adc  mov     ecx, ebx; dwErrCode
0x180005ade  call    cs:__imp_SetLastError
0x180005ae4  mov     [rdi+38h], r15
0x180005ae8  mov     ecx, r14d; dwErrCode
0x180005aeb  call    cs:__imp_SetLastError
0x180005af1  mov     rcx, [rdi+38h]; pti
0x180005af5  test    rcx, rcx
0x180005af8  jz      short loc_180005B1B
0x180005afa  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180005b03  mov     r9d, 4E2h; msWindowLength
0x180005b09  xor     r8d, r8d; msPeriod
0x180005b0c  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180005b11  call    cs:__imp_SetThreadpoolTimer
0x180005b17  mov     byte ptr [rdi+40h], 1
0x180005b1b  test    rsi, rsi
0x180005b1e  jz      short loc_180005B2A
0x180005b20  mov     rcx, rsi; SRWLock
0x180005b23  call    cs:__imp_ReleaseSRWLockExclusive
0x180005b29  nop
0x180005b2a  add     rsp, 38h
0x180005b2e  pop     r15
0x180005b30  pop     r14
0x180005b32  pop     rdi
0x180005b33  pop     rsi
0x180005b34  pop     rbp
0x180005b35  pop     rbx
0x180005b36  retn
```
