# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180007518`
- end: `0x1800076b3`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180009f50`

## callees

- `0x180002e3a`
- `0x180002ed4`
- `0x180007518`
- `0x18000a5e0`
- `0x18002b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800075af`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800075d9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800075af`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800075d9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007568`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007568`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000769f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000769f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000765a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007667`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000765a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007667`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007628`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007628`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007652`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007652`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007616`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007616`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000763b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000768d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000763b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000768d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007649`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007649`

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
0x180007518  push    rbx
0x18000751a  push    rbp
0x18000751b  push    rsi
0x18000751c  push    rdi
0x18000751d  push    r14
0x18000751f  push    r15
0x180007521  sub     rsp, 38h
0x180007525  mov     ebp, r9d
0x180007528  movzx   ebx, r8w
0x18000752c  mov     r14d, edx
0x18000752f  mov     rdi, rcx
0x180007532  cmp     byte ptr [rcx], 0
0x180007535  jz      loc_1800076A6
0x18000753b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180007542  jnz     loc_1800076A6
0x180007548  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000754f  test    rax, rax
0x180007552  jz      short loc_180007561
0x180007554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007559  test    al, al
0x18000755b  jnz     loc_1800076A6
0x180007561  lea     rsi, [rdi+28h]
0x180007565  mov     rcx, rsi; SRWLock
0x180007568  call    cs:__imp_AcquireSRWLockExclusive
0x18000756e  xor     eax, eax
0x180007570  mov     word ptr [rsp+68h+var_48+6], ax
0x180007575  mov     dword ptr [rsp+68h+var_48], r14d
0x18000757a  mov     word ptr [rsp+68h+var_48+4], bx
0x18000757f  lea     rbx, [rdi+0E8h]
0x180007586  lea     edx, [rax+0Ch]; unsigned __int64
0x180007589  mov     rcx, rbx; this
0x18000758c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180007591  test    al, al
0x180007593  jz      short loc_1800075EF
0x180007595  mov     rcx, [rbx+8]; void *
0x180007599  mov     rax, [rbx+10h]
0x18000759d  sub     rax, rcx
0x1800075a0  cmp     rcx, [rbx+10h]
0x1800075a4  sbb     r8, r8
0x1800075a7  and     r8, rax; Size
0x1800075aa  test    rcx, rcx
0x1800075ad  jnz     short loc_1800075BD
0x1800075af  call    cs:__imp__o__errno
0x1800075b5  mov     dword ptr [rax], 16h
0x1800075bb  jmp     short loc_1800075E5
0x1800075bd  cmp     r8, 0Ch
0x1800075c1  jb      short loc_1800075D2
0x1800075c3  movsd   xmm0, [rsp+68h+var_48]
0x1800075c9  movsd   qword ptr [rcx], xmm0
0x1800075cd  mov     [rcx+8], ebp
0x1800075d0  jmp     short loc_1800075EA
0x1800075d2  xor     edx, edx; Val
0x1800075d4  call    memset_0
0x1800075d9  call    cs:__imp__o__errno
0x1800075df  mov     dword ptr [rax], 22h ; '"'
0x1800075e5  call    _invalid_parameter_noinfo
0x1800075ea  add     qword ptr [rbx+8], 0Ch
0x1800075ef  cmp     byte ptr [rdi+40h], 0
0x1800075f3  jnz     loc_180007697
0x1800075f9  cmp     qword ptr [rdi+38h], 0
0x1800075fe  jnz     short loc_18000766D
0x180007600  call    cs:__imp_GetLastError
0x180007606  mov     r14d, eax
0x180007609  xor     r8d, r8d; pcbe
0x18000760c  mov     rdx, rdi; pv
0x18000760f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180007616  call    cs:__imp_CreateThreadpoolTimer
0x18000761c  mov     r15, rax
0x18000761f  mov     rbp, [rdi+38h]
0x180007623  test    rbp, rbp
0x180007626  jz      short loc_180007660
0x180007628  call    cs:__imp_GetLastError
0x18000762e  mov     ebx, eax
0x180007630  xor     r9d, r9d; msWindowLength
0x180007633  xor     r8d, r8d; msPeriod
0x180007636  xor     edx, edx; pftDueTime
0x180007638  mov     rcx, rbp; pti
0x18000763b  call    cs:__imp_SetThreadpoolTimer
0x180007641  mov     edx, 1; fCancelPendingCallbacks
0x180007646  mov     rcx, rbp; pti
0x180007649  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000764f  mov     rcx, rbp; pti
0x180007652  call    cs:__imp_CloseThreadpoolTimer
0x180007658  mov     ecx, ebx; dwErrCode
0x18000765a  call    cs:__imp_SetLastError
0x180007660  mov     [rdi+38h], r15
0x180007664  mov     ecx, r14d; dwErrCode
0x180007667  call    cs:__imp_SetLastError
0x18000766d  mov     rcx, [rdi+38h]; pti
0x180007671  test    rcx, rcx
0x180007674  jz      short loc_180007697
0x180007676  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000767f  mov     r9d, 4E2h; msWindowLength
0x180007685  xor     r8d, r8d; msPeriod
0x180007688  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000768d  call    cs:__imp_SetThreadpoolTimer
0x180007693  mov     byte ptr [rdi+40h], 1
0x180007697  test    rsi, rsi
0x18000769a  jz      short loc_1800076A6
0x18000769c  mov     rcx, rsi; SRWLock
0x18000769f  call    cs:__imp_ReleaseSRWLockExclusive
0x1800076a5  nop
0x1800076a6  add     rsp, 38h
0x1800076aa  pop     r15
0x1800076ac  pop     r14
0x1800076ae  pop     rdi
0x1800076af  pop     rsi
0x1800076b0  pop     rbp
0x1800076b1  pop     rbx
0x1800076b2  retn
```
