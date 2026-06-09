# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180008c40`
- end: `0x180008ddb`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000a680`

## callees

- `0x180002c4a`
- `0x180002cb4`
- `0x180008c40`
- `0x18000aa84`
- `0x18000f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008cd7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008d01`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008cd7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008d01`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008dc7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008dc7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008c90`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008c90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008d82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008d8f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008d82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008d8f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008d7a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008d7a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008d71`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008d71`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008d63`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008db5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008d63`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008db5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008d3e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008d3e`

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
0x180008c40  push    rbx
0x180008c42  push    rbp
0x180008c43  push    rsi
0x180008c44  push    rdi
0x180008c45  push    r14
0x180008c47  push    r15
0x180008c49  sub     rsp, 38h
0x180008c4d  mov     ebp, r9d
0x180008c50  movzx   ebx, r8w
0x180008c54  mov     r14d, edx
0x180008c57  mov     rdi, rcx
0x180008c5a  cmp     byte ptr [rcx], 0
0x180008c5d  jz      loc_180008DCE
0x180008c63  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180008c6a  jnz     loc_180008DCE
0x180008c70  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008c77  test    rax, rax
0x180008c7a  jz      short loc_180008C89
0x180008c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c81  test    al, al
0x180008c83  jnz     loc_180008DCE
0x180008c89  lea     rsi, [rdi+28h]
0x180008c8d  mov     rcx, rsi; SRWLock
0x180008c90  call    cs:__imp_AcquireSRWLockExclusive
0x180008c96  xor     eax, eax
0x180008c98  mov     word ptr [rsp+68h+var_48+6], ax
0x180008c9d  mov     dword ptr [rsp+68h+var_48], r14d
0x180008ca2  mov     word ptr [rsp+68h+var_48+4], bx
0x180008ca7  lea     rbx, [rdi+0E8h]
0x180008cae  lea     edx, [rax+0Ch]; unsigned __int64
0x180008cb1  mov     rcx, rbx; this
0x180008cb4  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180008cb9  test    al, al
0x180008cbb  jz      short loc_180008D17
0x180008cbd  mov     rcx, [rbx+8]; void *
0x180008cc1  mov     rax, [rbx+10h]
0x180008cc5  sub     rax, rcx
0x180008cc8  cmp     rcx, [rbx+10h]
0x180008ccc  sbb     r8, r8
0x180008ccf  and     r8, rax; Size
0x180008cd2  test    rcx, rcx
0x180008cd5  jnz     short loc_180008CE5
0x180008cd7  call    cs:__imp__o__errno
0x180008cdd  mov     dword ptr [rax], 16h
0x180008ce3  jmp     short loc_180008D0D
0x180008ce5  cmp     r8, 0Ch
0x180008ce9  jb      short loc_180008CFA
0x180008ceb  movsd   xmm0, [rsp+68h+var_48]
0x180008cf1  movsd   qword ptr [rcx], xmm0
0x180008cf5  mov     [rcx+8], ebp
0x180008cf8  jmp     short loc_180008D12
0x180008cfa  xor     edx, edx; Val
0x180008cfc  call    memset_0
0x180008d01  call    cs:__imp__o__errno
0x180008d07  mov     dword ptr [rax], 22h ; '"'
0x180008d0d  call    _invalid_parameter_noinfo
0x180008d12  add     qword ptr [rbx+8], 0Ch
0x180008d17  cmp     byte ptr [rdi+40h], 0
0x180008d1b  jnz     loc_180008DBF
0x180008d21  cmp     qword ptr [rdi+38h], 0
0x180008d26  jnz     short loc_180008D95
0x180008d28  call    cs:__imp_GetLastError
0x180008d2e  mov     r14d, eax
0x180008d31  xor     r8d, r8d; pcbe
0x180008d34  mov     rdx, rdi; pv
0x180008d37  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180008d3e  call    cs:__imp_CreateThreadpoolTimer
0x180008d44  mov     r15, rax
0x180008d47  mov     rbp, [rdi+38h]
0x180008d4b  test    rbp, rbp
0x180008d4e  jz      short loc_180008D88
0x180008d50  call    cs:__imp_GetLastError
0x180008d56  mov     ebx, eax
0x180008d58  xor     r9d, r9d; msWindowLength
0x180008d5b  xor     r8d, r8d; msPeriod
0x180008d5e  xor     edx, edx; pftDueTime
0x180008d60  mov     rcx, rbp; pti
0x180008d63  call    cs:__imp_SetThreadpoolTimer
0x180008d69  mov     edx, 1; fCancelPendingCallbacks
0x180008d6e  mov     rcx, rbp; pti
0x180008d71  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008d77  mov     rcx, rbp; pti
0x180008d7a  call    cs:__imp_CloseThreadpoolTimer
0x180008d80  mov     ecx, ebx; dwErrCode
0x180008d82  call    cs:__imp_SetLastError
0x180008d88  mov     [rdi+38h], r15
0x180008d8c  mov     ecx, r14d; dwErrCode
0x180008d8f  call    cs:__imp_SetLastError
0x180008d95  mov     rcx, [rdi+38h]; pti
0x180008d99  test    rcx, rcx
0x180008d9c  jz      short loc_180008DBF
0x180008d9e  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180008da7  mov     r9d, 4E2h; msWindowLength
0x180008dad  xor     r8d, r8d; msPeriod
0x180008db0  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180008db5  call    cs:__imp_SetThreadpoolTimer
0x180008dbb  mov     byte ptr [rdi+40h], 1
0x180008dbf  test    rsi, rsi
0x180008dc2  jz      short loc_180008DCE
0x180008dc4  mov     rcx, rsi; SRWLock
0x180008dc7  call    cs:__imp_ReleaseSRWLockExclusive
0x180008dcd  nop
0x180008dce  add     rsp, 38h
0x180008dd2  pop     r15
0x180008dd4  pop     r14
0x180008dd6  pop     rdi
0x180008dd7  pop     rsi
0x180008dd8  pop     rbp
0x180008dd9  pop     rbx
0x180008dda  retn
```
