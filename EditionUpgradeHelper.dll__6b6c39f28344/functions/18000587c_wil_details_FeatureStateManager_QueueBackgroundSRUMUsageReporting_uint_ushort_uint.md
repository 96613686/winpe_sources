# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000587c`
- end: `0x180005a16`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `410`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180007640`

## callees

- `0x180002472`
- `0x1800024d4`
- `0x18000587c`
- `0x180007bbc`
- `0x180027010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005913`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000593d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005913`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000593d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800058cc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800058cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005a03`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005a03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005964`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000598c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005964`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000598c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800059be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800059cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800059be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800059cb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000599f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800059f1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000599f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800059f1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800059b6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800059b6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000597a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000597a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800059ad`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800059ad`

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
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v13; // rbp
  PTP_TIMER v14; // r15
  DWORD v15; // ebx
  struct _TP_TIMER *v16; // rcx
  __int64 v17; // [rsp+20h] [rbp-48h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  HIDWORD(v17) = a3;
  LODWORD(v17) = a2;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v10 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v10 >= 0xC )
      {
        *(_QWORD *)Ptr = v17;
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
      v14 = ThreadpoolTimer;
      if ( v13 )
      {
        v15 = GetLastError();
        SetThreadpoolTimer(v13, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v13, 1);
        CloseThreadpoolTimer(v13);
        SetLastError(v15);
      }
      pv[7].Ptr = v14;
      SetLastError(LastError);
    }
    v16 = (struct _TP_TIMER *)pv[7].Ptr;
    if ( v16 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v16, &pftDueTime, 0, 0x4E2u);
      LOBYTE(pv[8].Ptr) = 1;
    }
  }
  if ( pv != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(pv + 5);
}

```

## disassembly

```asm
0x18000587c  push    rbx
0x18000587e  push    rbp
0x18000587f  push    rsi
0x180005880  push    rdi
0x180005881  push    r14
0x180005883  push    r15
0x180005885  sub     rsp, 38h
0x180005889  cmp     byte ptr [rcx], 0
0x18000588c  mov     ebp, r9d
0x18000588f  movzx   ebx, r8w
0x180005893  mov     r14d, edx
0x180005896  mov     rdi, rcx
0x180005899  jz      loc_180005A09
0x18000589f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800058a6  jnz     loc_180005A09
0x1800058ac  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800058b3  test    rax, rax
0x1800058b6  jz      short loc_1800058C5
0x1800058b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058bd  test    al, al
0x1800058bf  jnz     loc_180005A09
0x1800058c5  lea     rsi, [rdi+28h]
0x1800058c9  mov     rcx, rsi; SRWLock
0x1800058cc  call    cs:__imp_AcquireSRWLockExclusive
0x1800058d2  xor     eax, eax
0x1800058d4  mov     word ptr [rsp+68h+var_48+4], bx
0x1800058d9  lea     rbx, [rdi+0E8h]
0x1800058e0  mov     word ptr [rsp+68h+var_48+6], ax
0x1800058e5  mov     rcx, rbx; this
0x1800058e8  mov     dword ptr [rsp+68h+var_48], r14d
0x1800058ed  lea     edx, [rax+0Ch]; unsigned __int64
0x1800058f0  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800058f5  test    al, al
0x1800058f7  jz      short loc_180005953
0x1800058f9  mov     rcx, [rbx+8]; void *
0x1800058fd  mov     rax, [rbx+10h]
0x180005901  sub     rax, rcx
0x180005904  cmp     rcx, [rbx+10h]
0x180005908  sbb     r8, r8
0x18000590b  and     r8, rax; Size
0x18000590e  test    rcx, rcx
0x180005911  jnz     short loc_180005921
0x180005913  call    cs:__imp__o__errno
0x180005919  mov     dword ptr [rax], 16h
0x18000591f  jmp     short loc_180005949
0x180005921  cmp     r8, 0Ch
0x180005925  jb      short loc_180005936
0x180005927  movsd   xmm0, [rsp+68h+var_48]
0x18000592d  movsd   qword ptr [rcx], xmm0
0x180005931  mov     [rcx+8], ebp
0x180005934  jmp     short loc_18000594E
0x180005936  xor     edx, edx; Val
0x180005938  call    memset_0
0x18000593d  call    cs:__imp__o__errno
0x180005943  mov     dword ptr [rax], 22h ; '"'
0x180005949  call    _invalid_parameter_noinfo
0x18000594e  add     qword ptr [rbx+8], 0Ch
0x180005953  cmp     byte ptr [rdi+40h], 0
0x180005957  jnz     loc_1800059FB
0x18000595d  cmp     qword ptr [rdi+38h], 0
0x180005962  jnz     short loc_1800059D1
0x180005964  call    cs:__imp_GetLastError
0x18000596a  xor     r8d, r8d; pcbe
0x18000596d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180005974  mov     rdx, rdi; pv
0x180005977  mov     r14d, eax
0x18000597a  call    cs:__imp_CreateThreadpoolTimer
0x180005980  mov     rbp, [rdi+38h]
0x180005984  mov     r15, rax
0x180005987  test    rbp, rbp
0x18000598a  jz      short loc_1800059C4
0x18000598c  call    cs:__imp_GetLastError
0x180005992  xor     r9d, r9d; msWindowLength
0x180005995  xor     r8d, r8d; msPeriod
0x180005998  xor     edx, edx; pftDueTime
0x18000599a  mov     rcx, rbp; pti
0x18000599d  mov     ebx, eax
0x18000599f  call    cs:__imp_SetThreadpoolTimer
0x1800059a5  mov     edx, 1; fCancelPendingCallbacks
0x1800059aa  mov     rcx, rbp; pti
0x1800059ad  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800059b3  mov     rcx, rbp; pti
0x1800059b6  call    cs:__imp_CloseThreadpoolTimer
0x1800059bc  mov     ecx, ebx; dwErrCode
0x1800059be  call    cs:__imp_SetLastError
0x1800059c4  mov     ecx, r14d; dwErrCode
0x1800059c7  mov     [rdi+38h], r15
0x1800059cb  call    cs:__imp_SetLastError
0x1800059d1  mov     rcx, [rdi+38h]; pti
0x1800059d5  test    rcx, rcx
0x1800059d8  jz      short loc_1800059FB
0x1800059da  mov     r9d, 4E2h; msWindowLength
0x1800059e0  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800059e9  xor     r8d, r8d; msPeriod
0x1800059ec  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x1800059f1  call    cs:__imp_SetThreadpoolTimer
0x1800059f7  mov     byte ptr [rdi+40h], 1
0x1800059fb  test    rsi, rsi
0x1800059fe  jz      short loc_180005A09
0x180005a00  mov     rcx, rsi; SRWLock
0x180005a03  call    cs:__imp_ReleaseSRWLockExclusive
0x180005a09  add     rsp, 38h
0x180005a0d  pop     r15
0x180005a0f  pop     r14
0x180005a11  pop     rdi
0x180005a12  pop     rsi
0x180005a13  pop     rbp
0x180005a14  pop     rbx
0x180005a15  retn
```
