# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1400092cc`
- end: `0x140009468`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `412`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14000b650`

## callees

- `0x1400022ec`
- `0x1400092cc`
- `0x14000bb9c`
- `0x140011010`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x140009399`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x140009399`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140009363`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14000938d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140009363`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14000938d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400093b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400093dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400093b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400093dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000940f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000941c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000940f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000941c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009454`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009454`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000931c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000931c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140009407`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140009407`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400093cb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400093cb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400093f0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140009442`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400093f0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140009442`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400093fe`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400093fe`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        unsigned __int16 a3,
        int a4)
{
  _DWORD *Ptr; // rcx
  size_t v9; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *v12; // rbp
  DWORD v13; // ebx
  struct _TP_TIMER *v14; // rcx
  __int64 v15; // [rsp+20h] [rbp-48h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  LODWORD(v15) = a2;
  HIDWORD(v15) = a3;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v9 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v9 >= 0xC )
      {
        *(_QWORD *)Ptr = v15;
        Ptr[2] = a4;
LABEL_12:
        pv[30].Ptr = (char *)pv[30].Ptr + 12;
        goto LABEL_13;
      }
      memset_0(Ptr, 0, v9);
      *_errno() = 34;
    }
    else
    {
      *_errno() = 22;
    }
    _invalid_parameter_noinfo();
    goto LABEL_12;
  }
LABEL_13:
  if ( !LOBYTE(pv[8].Ptr) )
  {
    if ( !pv[7].Ptr )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_, pv, 0);
      v12 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v12 )
      {
        v13 = GetLastError();
        SetThreadpoolTimer(v12, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v12, 1);
        CloseThreadpoolTimer(v12);
        SetLastError(v13);
      }
      pv[7].Ptr = ThreadpoolTimer;
      SetLastError(LastError);
    }
    v14 = (struct _TP_TIMER *)pv[7].Ptr;
    if ( v14 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v14, &pftDueTime, 0, 0x4E2u);
      LOBYTE(pv[8].Ptr) = 1;
    }
  }
  if ( pv != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(pv + 5);
}

```

## disassembly

```asm
0x1400092cc  push    rbx
0x1400092ce  push    rbp
0x1400092cf  push    rsi
0x1400092d0  push    rdi
0x1400092d1  push    r14
0x1400092d3  push    r15
0x1400092d5  sub     rsp, 38h
0x1400092d9  mov     ebp, r9d
0x1400092dc  movzx   ebx, r8w
0x1400092e0  mov     r14d, edx
0x1400092e3  mov     rdi, rcx
0x1400092e6  cmp     byte ptr [rcx], 0
0x1400092e9  jz      loc_14000945B
0x1400092ef  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1400092f6  jnz     loc_14000945B
0x1400092fc  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140009303  test    rax, rax
0x140009306  jz      short loc_140009315
0x140009308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000930d  test    al, al
0x14000930f  jnz     loc_14000945B
0x140009315  lea     rsi, [rdi+28h]
0x140009319  mov     rcx, rsi; SRWLock
0x14000931c  call    cs:__imp_AcquireSRWLockExclusive
0x140009322  xor     eax, eax
0x140009324  mov     word ptr [rsp+68h+var_48+6], ax
0x140009329  mov     dword ptr [rsp+68h+var_48], r14d
0x14000932e  mov     word ptr [rsp+68h+var_48+4], bx
0x140009333  lea     rbx, [rdi+0E8h]
0x14000933a  lea     edx, [rax+0Ch]; unsigned __int64
0x14000933d  mov     rcx, rbx; this
0x140009340  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140009345  test    al, al
0x140009347  jz      short loc_1400093A4
0x140009349  mov     rcx, [rbx+8]; void *
0x14000934d  mov     rax, [rbx+10h]
0x140009351  sub     rax, rcx
0x140009354  cmp     rcx, [rbx+10h]
0x140009358  sbb     r8, r8
0x14000935b  and     r8, rax; Size
0x14000935e  test    rcx, rcx
0x140009361  jnz     short loc_140009371
0x140009363  call    cs:__imp__errno
0x140009369  mov     dword ptr [rax], 16h
0x14000936f  jmp     short loc_140009399
0x140009371  cmp     r8, 0Ch
0x140009375  jb      short loc_140009386
0x140009377  movsd   xmm0, [rsp+68h+var_48]
0x14000937d  movsd   qword ptr [rcx], xmm0
0x140009381  mov     [rcx+8], ebp
0x140009384  jmp     short loc_14000939F
0x140009386  xor     edx, edx; Val
0x140009388  call    memset_0
0x14000938d  call    cs:__imp__errno
0x140009393  mov     dword ptr [rax], 22h ; '"'
0x140009399  call    cs:__imp__invalid_parameter_noinfo
0x14000939f  add     qword ptr [rbx+8], 0Ch
0x1400093a4  cmp     byte ptr [rdi+40h], 0
0x1400093a8  jnz     loc_14000944C
0x1400093ae  cmp     qword ptr [rdi+38h], 0
0x1400093b3  jnz     short loc_140009422
0x1400093b5  call    cs:__imp_GetLastError
0x1400093bb  mov     r14d, eax
0x1400093be  xor     r8d, r8d; pcbe
0x1400093c1  mov     rdx, rdi; pv
0x1400093c4  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400093cb  call    cs:__imp_CreateThreadpoolTimer
0x1400093d1  mov     r15, rax
0x1400093d4  mov     rbp, [rdi+38h]
0x1400093d8  test    rbp, rbp
0x1400093db  jz      short loc_140009415
0x1400093dd  call    cs:__imp_GetLastError
0x1400093e3  mov     ebx, eax
0x1400093e5  xor     r9d, r9d; msWindowLength
0x1400093e8  xor     r8d, r8d; msPeriod
0x1400093eb  xor     edx, edx; pftDueTime
0x1400093ed  mov     rcx, rbp; pti
0x1400093f0  call    cs:__imp_SetThreadpoolTimer
0x1400093f6  mov     edx, 1; fCancelPendingCallbacks
0x1400093fb  mov     rcx, rbp; pti
0x1400093fe  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140009404  mov     rcx, rbp; pti
0x140009407  call    cs:__imp_CloseThreadpoolTimer
0x14000940d  mov     ecx, ebx; dwErrCode
0x14000940f  call    cs:__imp_SetLastError
0x140009415  mov     [rdi+38h], r15
0x140009419  mov     ecx, r14d; dwErrCode
0x14000941c  call    cs:__imp_SetLastError
0x140009422  mov     rcx, [rdi+38h]; pti
0x140009426  test    rcx, rcx
0x140009429  jz      short loc_14000944C
0x14000942b  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x140009434  mov     r9d, 4E2h; msWindowLength
0x14000943a  xor     r8d, r8d; msPeriod
0x14000943d  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x140009442  call    cs:__imp_SetThreadpoolTimer
0x140009448  mov     byte ptr [rdi+40h], 1
0x14000944c  test    rsi, rsi
0x14000944f  jz      short loc_14000945B
0x140009451  mov     rcx, rsi; SRWLock
0x140009454  call    cs:__imp_ReleaseSRWLockExclusive
0x14000945a  nop
0x14000945b  add     rsp, 38h
0x14000945f  pop     r15
0x140009461  pop     r14
0x140009463  pop     rdi
0x140009464  pop     rsi
0x140009465  pop     rbp
0x140009466  pop     rbx
0x140009467  retn
```
