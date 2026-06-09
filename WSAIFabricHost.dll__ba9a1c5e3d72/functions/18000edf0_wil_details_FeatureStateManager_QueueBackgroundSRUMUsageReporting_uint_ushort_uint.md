# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000edf0`
- end: `0x18000ef8b`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180010c40`

## callees

- `0x1800056d2`
- `0x180005758`
- `0x18000edf0`
- `0x1800111dc`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ee87`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000eeb1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ee87`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000eeb1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ee40`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ee40`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ef77`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ef77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eed8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eed8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef00`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ef32`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ef3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ef32`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ef3f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ef21`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ef21`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ef2a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ef2a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000eeee`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000eeee`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ef13`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ef65`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ef13`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ef65`

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
0x18000edf0  push    rbx
0x18000edf2  push    rbp
0x18000edf3  push    rsi
0x18000edf4  push    rdi
0x18000edf5  push    r14
0x18000edf7  push    r15
0x18000edf9  sub     rsp, 38h
0x18000edfd  mov     ebp, r9d
0x18000ee00  movzx   ebx, r8w
0x18000ee04  mov     r14d, edx
0x18000ee07  mov     rdi, rcx
0x18000ee0a  cmp     byte ptr [rcx], 0
0x18000ee0d  jz      loc_18000EF7E
0x18000ee13  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000ee1a  jnz     loc_18000EF7E
0x18000ee20  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ee27  test    rax, rax
0x18000ee2a  jz      short loc_18000EE39
0x18000ee2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee31  test    al, al
0x18000ee33  jnz     loc_18000EF7E
0x18000ee39  lea     rsi, [rdi+28h]
0x18000ee3d  mov     rcx, rsi; SRWLock
0x18000ee40  call    cs:__imp_AcquireSRWLockExclusive
0x18000ee46  xor     eax, eax
0x18000ee48  mov     word ptr [rsp+68h+var_48+6], ax
0x18000ee4d  mov     dword ptr [rsp+68h+var_48], r14d
0x18000ee52  mov     word ptr [rsp+68h+var_48+4], bx
0x18000ee57  lea     rbx, [rdi+0E8h]
0x18000ee5e  lea     edx, [rax+0Ch]; unsigned __int64
0x18000ee61  mov     rcx, rbx; this
0x18000ee64  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000ee69  test    al, al
0x18000ee6b  jz      short loc_18000EEC7
0x18000ee6d  mov     rcx, [rbx+8]; void *
0x18000ee71  mov     rax, [rbx+10h]
0x18000ee75  sub     rax, rcx
0x18000ee78  cmp     rcx, [rbx+10h]
0x18000ee7c  sbb     r8, r8
0x18000ee7f  and     r8, rax; Size
0x18000ee82  test    rcx, rcx
0x18000ee85  jnz     short loc_18000EE95
0x18000ee87  call    cs:__imp__o__errno
0x18000ee8d  mov     dword ptr [rax], 16h
0x18000ee93  jmp     short loc_18000EEBD
0x18000ee95  cmp     r8, 0Ch
0x18000ee99  jb      short loc_18000EEAA
0x18000ee9b  movsd   xmm0, [rsp+68h+var_48]
0x18000eea1  movsd   qword ptr [rcx], xmm0
0x18000eea5  mov     [rcx+8], ebp
0x18000eea8  jmp     short loc_18000EEC2
0x18000eeaa  xor     edx, edx; Val
0x18000eeac  call    memset_0
0x18000eeb1  call    cs:__imp__o__errno
0x18000eeb7  mov     dword ptr [rax], 22h ; '"'
0x18000eebd  call    _invalid_parameter_noinfo
0x18000eec2  add     qword ptr [rbx+8], 0Ch
0x18000eec7  cmp     byte ptr [rdi+40h], 0
0x18000eecb  jnz     loc_18000EF6F
0x18000eed1  cmp     qword ptr [rdi+38h], 0
0x18000eed6  jnz     short loc_18000EF45
0x18000eed8  call    cs:__imp_GetLastError
0x18000eede  mov     r14d, eax
0x18000eee1  xor     r8d, r8d; pcbe
0x18000eee4  mov     rdx, rdi; pv
0x18000eee7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000eeee  call    cs:__imp_CreateThreadpoolTimer
0x18000eef4  mov     r15, rax
0x18000eef7  mov     rbp, [rdi+38h]
0x18000eefb  test    rbp, rbp
0x18000eefe  jz      short loc_18000EF38
0x18000ef00  call    cs:__imp_GetLastError
0x18000ef06  mov     ebx, eax
0x18000ef08  xor     r9d, r9d; msWindowLength
0x18000ef0b  xor     r8d, r8d; msPeriod
0x18000ef0e  xor     edx, edx; pftDueTime
0x18000ef10  mov     rcx, rbp; pti
0x18000ef13  call    cs:__imp_SetThreadpoolTimer
0x18000ef19  mov     edx, 1; fCancelPendingCallbacks
0x18000ef1e  mov     rcx, rbp; pti
0x18000ef21  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ef27  mov     rcx, rbp; pti
0x18000ef2a  call    cs:__imp_CloseThreadpoolTimer
0x18000ef30  mov     ecx, ebx; dwErrCode
0x18000ef32  call    cs:__imp_SetLastError
0x18000ef38  mov     [rdi+38h], r15
0x18000ef3c  mov     ecx, r14d; dwErrCode
0x18000ef3f  call    cs:__imp_SetLastError
0x18000ef45  mov     rcx, [rdi+38h]; pti
0x18000ef49  test    rcx, rcx
0x18000ef4c  jz      short loc_18000EF6F
0x18000ef4e  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000ef57  mov     r9d, 4E2h; msWindowLength
0x18000ef5d  xor     r8d, r8d; msPeriod
0x18000ef60  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000ef65  call    cs:__imp_SetThreadpoolTimer
0x18000ef6b  mov     byte ptr [rdi+40h], 1
0x18000ef6f  test    rsi, rsi
0x18000ef72  jz      short loc_18000EF7E
0x18000ef74  mov     rcx, rsi; SRWLock
0x18000ef77  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ef7d  nop
0x18000ef7e  add     rsp, 38h
0x18000ef82  pop     r15
0x18000ef84  pop     r14
0x18000ef86  pop     rdi
0x18000ef87  pop     rsi
0x18000ef88  pop     rbp
0x18000ef89  pop     rbx
0x18000ef8a  retn
```
