# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000824c`
- end: `0x1800083e7`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000a620`

## callees

- `0x1800020d0`
- `0x180002134`
- `0x18000824c`
- `0x18000ac4c`
- `0x18000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800082e3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000830d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800082e3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000830d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000835c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000835c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000838e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000839b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000838e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000839b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800083d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800083d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000829c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000829c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000836f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800083c1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000836f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800083c1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000837d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000837d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000834a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000834a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008386`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008386`

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
0x18000824c  push    rbx
0x18000824e  push    rbp
0x18000824f  push    rsi
0x180008250  push    rdi
0x180008251  push    r14
0x180008253  push    r15
0x180008255  sub     rsp, 38h
0x180008259  mov     ebp, r9d
0x18000825c  movzx   ebx, r8w
0x180008260  mov     r14d, edx
0x180008263  mov     rdi, rcx
0x180008266  cmp     byte ptr [rcx], 0
0x180008269  jz      loc_1800083DA
0x18000826f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180008276  jnz     loc_1800083DA
0x18000827c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008283  test    rax, rax
0x180008286  jz      short loc_180008295
0x180008288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000828d  test    al, al
0x18000828f  jnz     loc_1800083DA
0x180008295  lea     rsi, [rdi+28h]
0x180008299  mov     rcx, rsi; SRWLock
0x18000829c  call    cs:__imp_AcquireSRWLockExclusive
0x1800082a2  xor     eax, eax
0x1800082a4  mov     word ptr [rsp+68h+var_48+6], ax
0x1800082a9  mov     dword ptr [rsp+68h+var_48], r14d
0x1800082ae  mov     word ptr [rsp+68h+var_48+4], bx
0x1800082b3  lea     rbx, [rdi+0E8h]
0x1800082ba  lea     edx, [rax+0Ch]; unsigned __int64
0x1800082bd  mov     rcx, rbx; this
0x1800082c0  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800082c5  test    al, al
0x1800082c7  jz      short loc_180008323
0x1800082c9  mov     rcx, [rbx+8]; void *
0x1800082cd  mov     rax, [rbx+10h]
0x1800082d1  sub     rax, rcx
0x1800082d4  cmp     rcx, [rbx+10h]
0x1800082d8  sbb     r8, r8
0x1800082db  and     r8, rax; Size
0x1800082de  test    rcx, rcx
0x1800082e1  jnz     short loc_1800082F1
0x1800082e3  call    cs:__imp__o__errno
0x1800082e9  mov     dword ptr [rax], 16h
0x1800082ef  jmp     short loc_180008319
0x1800082f1  cmp     r8, 0Ch
0x1800082f5  jb      short loc_180008306
0x1800082f7  movsd   xmm0, [rsp+68h+var_48]
0x1800082fd  movsd   qword ptr [rcx], xmm0
0x180008301  mov     [rcx+8], ebp
0x180008304  jmp     short loc_18000831E
0x180008306  xor     edx, edx; Val
0x180008308  call    memset_0
0x18000830d  call    cs:__imp__o__errno
0x180008313  mov     dword ptr [rax], 22h ; '"'
0x180008319  call    _invalid_parameter_noinfo
0x18000831e  add     qword ptr [rbx+8], 0Ch
0x180008323  cmp     byte ptr [rdi+40h], 0
0x180008327  jnz     loc_1800083CB
0x18000832d  cmp     qword ptr [rdi+38h], 0
0x180008332  jnz     short loc_1800083A1
0x180008334  call    cs:__imp_GetLastError
0x18000833a  mov     r14d, eax
0x18000833d  xor     r8d, r8d; pcbe
0x180008340  mov     rdx, rdi; pv
0x180008343  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000834a  call    cs:__imp_CreateThreadpoolTimer
0x180008350  mov     r15, rax
0x180008353  mov     rbp, [rdi+38h]
0x180008357  test    rbp, rbp
0x18000835a  jz      short loc_180008394
0x18000835c  call    cs:__imp_GetLastError
0x180008362  mov     ebx, eax
0x180008364  xor     r9d, r9d; msWindowLength
0x180008367  xor     r8d, r8d; msPeriod
0x18000836a  xor     edx, edx; pftDueTime
0x18000836c  mov     rcx, rbp; pti
0x18000836f  call    cs:__imp_SetThreadpoolTimer
0x180008375  mov     edx, 1; fCancelPendingCallbacks
0x18000837a  mov     rcx, rbp; pti
0x18000837d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008383  mov     rcx, rbp; pti
0x180008386  call    cs:__imp_CloseThreadpoolTimer
0x18000838c  mov     ecx, ebx; dwErrCode
0x18000838e  call    cs:__imp_SetLastError
0x180008394  mov     [rdi+38h], r15
0x180008398  mov     ecx, r14d; dwErrCode
0x18000839b  call    cs:__imp_SetLastError
0x1800083a1  mov     rcx, [rdi+38h]; pti
0x1800083a5  test    rcx, rcx
0x1800083a8  jz      short loc_1800083CB
0x1800083aa  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800083b3  mov     r9d, 4E2h; msWindowLength
0x1800083b9  xor     r8d, r8d; msPeriod
0x1800083bc  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x1800083c1  call    cs:__imp_SetThreadpoolTimer
0x1800083c7  mov     byte ptr [rdi+40h], 1
0x1800083cb  test    rsi, rsi
0x1800083ce  jz      short loc_1800083DA
0x1800083d0  mov     rcx, rsi; SRWLock
0x1800083d3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800083d9  nop
0x1800083da  add     rsp, 38h
0x1800083de  pop     r15
0x1800083e0  pop     r14
0x1800083e2  pop     rdi
0x1800083e3  pop     rsi
0x1800083e4  pop     rbp
0x1800083e5  pop     rbx
0x1800083e6  retn
```
