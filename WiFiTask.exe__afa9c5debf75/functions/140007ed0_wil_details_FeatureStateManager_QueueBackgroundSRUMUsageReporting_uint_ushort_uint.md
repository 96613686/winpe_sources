# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x140007ed0`
- end: `0x14000806b`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14000afe0`

## callees

- `0x1400020b2`
- `0x140002168`
- `0x140007ed0`
- `0x14000b92c`
- `0x140012010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007f67`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007f91`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007f67`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007f91`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008001`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008001`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140007fce`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140007fce`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140007ff3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008045`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140007ff3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008045`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000800a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000800a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140007f20`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140007f20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008057`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008057`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008012`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000801f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008012`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000801f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007fb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007fe0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007fb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007fe0`

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
0x140007ed0  push    rbx
0x140007ed2  push    rbp
0x140007ed3  push    rsi
0x140007ed4  push    rdi
0x140007ed5  push    r14
0x140007ed7  push    r15
0x140007ed9  sub     rsp, 38h
0x140007edd  mov     ebp, r9d
0x140007ee0  movzx   ebx, r8w
0x140007ee4  mov     r14d, edx
0x140007ee7  mov     rdi, rcx
0x140007eea  cmp     byte ptr [rcx], 0
0x140007eed  jz      loc_14000805E
0x140007ef3  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140007efa  jnz     loc_14000805E
0x140007f00  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140007f07  test    rax, rax
0x140007f0a  jz      short loc_140007F19
0x140007f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007f11  test    al, al
0x140007f13  jnz     loc_14000805E
0x140007f19  lea     rsi, [rdi+28h]
0x140007f1d  mov     rcx, rsi; SRWLock
0x140007f20  call    cs:__imp_AcquireSRWLockExclusive
0x140007f26  xor     eax, eax
0x140007f28  mov     word ptr [rsp+68h+var_48+6], ax
0x140007f2d  mov     dword ptr [rsp+68h+var_48], r14d
0x140007f32  mov     word ptr [rsp+68h+var_48+4], bx
0x140007f37  lea     rbx, [rdi+0E8h]
0x140007f3e  lea     edx, [rax+0Ch]; unsigned __int64
0x140007f41  mov     rcx, rbx; this
0x140007f44  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140007f49  test    al, al
0x140007f4b  jz      short loc_140007FA7
0x140007f4d  mov     rcx, [rbx+8]; void *
0x140007f51  mov     rax, [rbx+10h]
0x140007f55  sub     rax, rcx
0x140007f58  cmp     rcx, [rbx+10h]
0x140007f5c  sbb     r8, r8
0x140007f5f  and     r8, rax; Size
0x140007f62  test    rcx, rcx
0x140007f65  jnz     short loc_140007F75
0x140007f67  call    cs:__imp__o__errno
0x140007f6d  mov     dword ptr [rax], 16h
0x140007f73  jmp     short loc_140007F9D
0x140007f75  cmp     r8, 0Ch
0x140007f79  jb      short loc_140007F8A
0x140007f7b  movsd   xmm0, [rsp+68h+var_48]
0x140007f81  movsd   qword ptr [rcx], xmm0
0x140007f85  mov     [rcx+8], ebp
0x140007f88  jmp     short loc_140007FA2
0x140007f8a  xor     edx, edx; Val
0x140007f8c  call    memset_0
0x140007f91  call    cs:__imp__o__errno
0x140007f97  mov     dword ptr [rax], 22h ; '"'
0x140007f9d  call    _invalid_parameter_noinfo
0x140007fa2  add     qword ptr [rbx+8], 0Ch
0x140007fa7  cmp     byte ptr [rdi+40h], 0
0x140007fab  jnz     loc_14000804F
0x140007fb1  cmp     qword ptr [rdi+38h], 0
0x140007fb6  jnz     short loc_140008025
0x140007fb8  call    cs:__imp_GetLastError
0x140007fbe  mov     r14d, eax
0x140007fc1  xor     r8d, r8d; pcbe
0x140007fc4  mov     rdx, rdi; pv
0x140007fc7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140007fce  call    cs:__imp_CreateThreadpoolTimer
0x140007fd4  mov     r15, rax
0x140007fd7  mov     rbp, [rdi+38h]
0x140007fdb  test    rbp, rbp
0x140007fde  jz      short loc_140008018
0x140007fe0  call    cs:__imp_GetLastError
0x140007fe6  mov     ebx, eax
0x140007fe8  xor     r9d, r9d; msWindowLength
0x140007feb  xor     r8d, r8d; msPeriod
0x140007fee  xor     edx, edx; pftDueTime
0x140007ff0  mov     rcx, rbp; pti
0x140007ff3  call    cs:__imp_SetThreadpoolTimer
0x140007ff9  mov     edx, 1; fCancelPendingCallbacks
0x140007ffe  mov     rcx, rbp; pti
0x140008001  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008007  mov     rcx, rbp; pti
0x14000800a  call    cs:__imp_CloseThreadpoolTimer
0x140008010  mov     ecx, ebx; dwErrCode
0x140008012  call    cs:__imp_SetLastError
0x140008018  mov     [rdi+38h], r15
0x14000801c  mov     ecx, r14d; dwErrCode
0x14000801f  call    cs:__imp_SetLastError
0x140008025  mov     rcx, [rdi+38h]; pti
0x140008029  test    rcx, rcx
0x14000802c  jz      short loc_14000804F
0x14000802e  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x140008037  mov     r9d, 4E2h; msWindowLength
0x14000803d  xor     r8d, r8d; msPeriod
0x140008040  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x140008045  call    cs:__imp_SetThreadpoolTimer
0x14000804b  mov     byte ptr [rdi+40h], 1
0x14000804f  test    rsi, rsi
0x140008052  jz      short loc_14000805E
0x140008054  mov     rcx, rsi; SRWLock
0x140008057  call    cs:__imp_ReleaseSRWLockExclusive
0x14000805d  nop
0x14000805e  add     rsp, 38h
0x140008062  pop     r15
0x140008064  pop     r14
0x140008066  pop     rdi
0x140008067  pop     rsi
0x140008068  pop     rbp
0x140008069  pop     rbx
0x14000806a  retn
```
