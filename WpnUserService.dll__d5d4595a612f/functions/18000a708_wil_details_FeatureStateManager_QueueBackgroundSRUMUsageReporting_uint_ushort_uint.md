# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000a708`
- end: `0x18000a8a3`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000c740`

## callees

- `0x1800034fe`
- `0x18000354c`
- `0x18000a708`
- `0x18000cef4`
- `0x180012010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a79f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a7c9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a79f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a7c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a88f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a88f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a758`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a758`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a84a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a857`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a84a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a857`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a7f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a818`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a7f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a818`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a842`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a842`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a82b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a87d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a82b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a87d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a806`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a806`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a839`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a839`

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
0x18000a708  push    rbx
0x18000a70a  push    rbp
0x18000a70b  push    rsi
0x18000a70c  push    rdi
0x18000a70d  push    r14
0x18000a70f  push    r15
0x18000a711  sub     rsp, 38h
0x18000a715  mov     ebp, r9d
0x18000a718  movzx   ebx, r8w
0x18000a71c  mov     r14d, edx
0x18000a71f  mov     rdi, rcx
0x18000a722  cmp     byte ptr [rcx], 0
0x18000a725  jz      loc_18000A896
0x18000a72b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000a732  jnz     loc_18000A896
0x18000a738  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a73f  test    rax, rax
0x18000a742  jz      short loc_18000A751
0x18000a744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a749  test    al, al
0x18000a74b  jnz     loc_18000A896
0x18000a751  lea     rsi, [rdi+28h]
0x18000a755  mov     rcx, rsi; SRWLock
0x18000a758  call    cs:__imp_AcquireSRWLockExclusive
0x18000a75e  xor     eax, eax
0x18000a760  mov     word ptr [rsp+68h+var_48+6], ax
0x18000a765  mov     dword ptr [rsp+68h+var_48], r14d
0x18000a76a  mov     word ptr [rsp+68h+var_48+4], bx
0x18000a76f  lea     rbx, [rdi+0E8h]
0x18000a776  lea     edx, [rax+0Ch]; unsigned __int64
0x18000a779  mov     rcx, rbx; this
0x18000a77c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000a781  test    al, al
0x18000a783  jz      short loc_18000A7DF
0x18000a785  mov     rcx, [rbx+8]; void *
0x18000a789  mov     rax, [rbx+10h]
0x18000a78d  sub     rax, rcx
0x18000a790  cmp     rcx, [rbx+10h]
0x18000a794  sbb     r8, r8
0x18000a797  and     r8, rax; Size
0x18000a79a  test    rcx, rcx
0x18000a79d  jnz     short loc_18000A7AD
0x18000a79f  call    cs:__imp__o__errno
0x18000a7a5  mov     dword ptr [rax], 16h
0x18000a7ab  jmp     short loc_18000A7D5
0x18000a7ad  cmp     r8, 0Ch
0x18000a7b1  jb      short loc_18000A7C2
0x18000a7b3  movsd   xmm0, [rsp+68h+var_48]
0x18000a7b9  movsd   qword ptr [rcx], xmm0
0x18000a7bd  mov     [rcx+8], ebp
0x18000a7c0  jmp     short loc_18000A7DA
0x18000a7c2  xor     edx, edx; Val
0x18000a7c4  call    memset_0
0x18000a7c9  call    cs:__imp__o__errno
0x18000a7cf  mov     dword ptr [rax], 22h ; '"'
0x18000a7d5  call    _invalid_parameter_noinfo
0x18000a7da  add     qword ptr [rbx+8], 0Ch
0x18000a7df  cmp     byte ptr [rdi+40h], 0
0x18000a7e3  jnz     loc_18000A887
0x18000a7e9  cmp     qword ptr [rdi+38h], 0
0x18000a7ee  jnz     short loc_18000A85D
0x18000a7f0  call    cs:__imp_GetLastError
0x18000a7f6  mov     r14d, eax
0x18000a7f9  xor     r8d, r8d; pcbe
0x18000a7fc  mov     rdx, rdi; pv
0x18000a7ff  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000a806  call    cs:__imp_CreateThreadpoolTimer
0x18000a80c  mov     r15, rax
0x18000a80f  mov     rbp, [rdi+38h]
0x18000a813  test    rbp, rbp
0x18000a816  jz      short loc_18000A850
0x18000a818  call    cs:__imp_GetLastError
0x18000a81e  mov     ebx, eax
0x18000a820  xor     r9d, r9d; msWindowLength
0x18000a823  xor     r8d, r8d; msPeriod
0x18000a826  xor     edx, edx; pftDueTime
0x18000a828  mov     rcx, rbp; pti
0x18000a82b  call    cs:__imp_SetThreadpoolTimer
0x18000a831  mov     edx, 1; fCancelPendingCallbacks
0x18000a836  mov     rcx, rbp; pti
0x18000a839  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a83f  mov     rcx, rbp; pti
0x18000a842  call    cs:__imp_CloseThreadpoolTimer
0x18000a848  mov     ecx, ebx; dwErrCode
0x18000a84a  call    cs:__imp_SetLastError
0x18000a850  mov     [rdi+38h], r15
0x18000a854  mov     ecx, r14d; dwErrCode
0x18000a857  call    cs:__imp_SetLastError
0x18000a85d  mov     rcx, [rdi+38h]; pti
0x18000a861  test    rcx, rcx
0x18000a864  jz      short loc_18000A887
0x18000a866  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000a86f  mov     r9d, 4E2h; msWindowLength
0x18000a875  xor     r8d, r8d; msPeriod
0x18000a878  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000a87d  call    cs:__imp_SetThreadpoolTimer
0x18000a883  mov     byte ptr [rdi+40h], 1
0x18000a887  test    rsi, rsi
0x18000a88a  jz      short loc_18000A896
0x18000a88c  mov     rcx, rsi; SRWLock
0x18000a88f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a895  nop
0x18000a896  add     rsp, 38h
0x18000a89a  pop     r15
0x18000a89c  pop     r14
0x18000a89e  pop     rdi
0x18000a89f  pop     rsi
0x18000a8a0  pop     rbp
0x18000a8a1  pop     rbx
0x18000a8a2  retn
```
