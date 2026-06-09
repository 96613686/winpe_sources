# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180008184`
- end: `0x18000831f`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800096a0`

## callees

- `0x18000201a`
- `0x180002084`
- `0x180008184`
- `0x180009a7c`
- `0x18000b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000821b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008245`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000821b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008245`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000830b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000830b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800081d4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800081d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000826c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000826c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008294`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082d3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800082b5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800082b5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800082be`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800082be`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008282`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008282`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800082a7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800082f9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800082a7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800082f9`

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
0x180008184  push    rbx
0x180008186  push    rbp
0x180008187  push    rsi
0x180008188  push    rdi
0x180008189  push    r14
0x18000818b  push    r15
0x18000818d  sub     rsp, 38h
0x180008191  mov     ebp, r9d
0x180008194  movzx   ebx, r8w
0x180008198  mov     r14d, edx
0x18000819b  mov     rdi, rcx
0x18000819e  cmp     byte ptr [rcx], 0
0x1800081a1  jz      loc_180008312
0x1800081a7  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800081ae  jnz     loc_180008312
0x1800081b4  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800081bb  test    rax, rax
0x1800081be  jz      short loc_1800081CD
0x1800081c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081c5  test    al, al
0x1800081c7  jnz     loc_180008312
0x1800081cd  lea     rsi, [rdi+28h]
0x1800081d1  mov     rcx, rsi; SRWLock
0x1800081d4  call    cs:__imp_AcquireSRWLockExclusive
0x1800081da  xor     eax, eax
0x1800081dc  mov     word ptr [rsp+68h+var_48+6], ax
0x1800081e1  mov     dword ptr [rsp+68h+var_48], r14d
0x1800081e6  mov     word ptr [rsp+68h+var_48+4], bx
0x1800081eb  lea     rbx, [rdi+0E8h]
0x1800081f2  lea     edx, [rax+0Ch]; unsigned __int64
0x1800081f5  mov     rcx, rbx; this
0x1800081f8  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800081fd  test    al, al
0x1800081ff  jz      short loc_18000825B
0x180008201  mov     rcx, [rbx+8]; void *
0x180008205  mov     rax, [rbx+10h]
0x180008209  sub     rax, rcx
0x18000820c  cmp     rcx, [rbx+10h]
0x180008210  sbb     r8, r8
0x180008213  and     r8, rax; Size
0x180008216  test    rcx, rcx
0x180008219  jnz     short loc_180008229
0x18000821b  call    cs:__imp__o__errno
0x180008221  mov     dword ptr [rax], 16h
0x180008227  jmp     short loc_180008251
0x180008229  cmp     r8, 0Ch
0x18000822d  jb      short loc_18000823E
0x18000822f  movsd   xmm0, [rsp+68h+var_48]
0x180008235  movsd   qword ptr [rcx], xmm0
0x180008239  mov     [rcx+8], ebp
0x18000823c  jmp     short loc_180008256
0x18000823e  xor     edx, edx; Val
0x180008240  call    memset_0
0x180008245  call    cs:__imp__o__errno
0x18000824b  mov     dword ptr [rax], 22h ; '"'
0x180008251  call    _invalid_parameter_noinfo
0x180008256  add     qword ptr [rbx+8], 0Ch
0x18000825b  cmp     byte ptr [rdi+40h], 0
0x18000825f  jnz     loc_180008303
0x180008265  cmp     qword ptr [rdi+38h], 0
0x18000826a  jnz     short loc_1800082D9
0x18000826c  call    cs:__imp_GetLastError
0x180008272  mov     r14d, eax
0x180008275  xor     r8d, r8d; pcbe
0x180008278  mov     rdx, rdi; pv
0x18000827b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180008282  call    cs:__imp_CreateThreadpoolTimer
0x180008288  mov     r15, rax
0x18000828b  mov     rbp, [rdi+38h]
0x18000828f  test    rbp, rbp
0x180008292  jz      short loc_1800082CC
0x180008294  call    cs:__imp_GetLastError
0x18000829a  mov     ebx, eax
0x18000829c  xor     r9d, r9d; msWindowLength
0x18000829f  xor     r8d, r8d; msPeriod
0x1800082a2  xor     edx, edx; pftDueTime
0x1800082a4  mov     rcx, rbp; pti
0x1800082a7  call    cs:__imp_SetThreadpoolTimer
0x1800082ad  mov     edx, 1; fCancelPendingCallbacks
0x1800082b2  mov     rcx, rbp; pti
0x1800082b5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800082bb  mov     rcx, rbp; pti
0x1800082be  call    cs:__imp_CloseThreadpoolTimer
0x1800082c4  mov     ecx, ebx; dwErrCode
0x1800082c6  call    cs:__imp_SetLastError
0x1800082cc  mov     [rdi+38h], r15
0x1800082d0  mov     ecx, r14d; dwErrCode
0x1800082d3  call    cs:__imp_SetLastError
0x1800082d9  mov     rcx, [rdi+38h]; pti
0x1800082dd  test    rcx, rcx
0x1800082e0  jz      short loc_180008303
0x1800082e2  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800082eb  mov     r9d, 4E2h; msWindowLength
0x1800082f1  xor     r8d, r8d; msPeriod
0x1800082f4  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x1800082f9  call    cs:__imp_SetThreadpoolTimer
0x1800082ff  mov     byte ptr [rdi+40h], 1
0x180008303  test    rsi, rsi
0x180008306  jz      short loc_180008312
0x180008308  mov     rcx, rsi; SRWLock
0x18000830b  call    cs:__imp_ReleaseSRWLockExclusive
0x180008311  nop
0x180008312  add     rsp, 38h
0x180008316  pop     r15
0x180008318  pop     r14
0x18000831a  pop     rdi
0x18000831b  pop     rsi
0x18000831c  pop     rbp
0x18000831d  pop     rbx
0x18000831e  retn
```
