# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180006488`
- end: `0x18000663b`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `435`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180007a1c`

## callees

- `0x180001f32`
- `0x180001f88`
- `0x180006488`
- `0x180008f3c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006534`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000655c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006534`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000655c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800064d2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800064d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006628`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006628`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006583`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006583`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800065dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800065ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800065dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800065ea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800065be`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006616`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800065be`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006616`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800065d5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800065d5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800065cc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800065cc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006599`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006599`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  __int64 v5; // rdx
  _QWORD *v6; // rcx
  size_t v7; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *Ptr; // rbp
  PTP_TIMER v11; // r15
  DWORD v12; // ebx
  struct _TP_TIMER *v13; // rcx
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( !LODWORD(pv->Ptr)
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
LABEL_24:
      if ( pv != (RTL_SRWLOCK *)-8LL )
        ReleaseSRWLockExclusive(pv + 1);
      return;
    }
    if ( !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[4], 0x10u) )
    {
LABEL_17:
      if ( !LOBYTE(pv[3].Ptr) )
      {
        if ( !pv[2].Ptr )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          Ptr = (struct _TP_TIMER *)pv[2].Ptr;
          v11 = ThreadpoolTimer;
          if ( Ptr )
          {
            v12 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v12);
          }
          pv[2].Ptr = v11;
          SetLastError(LastError);
        }
        v13 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v13 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v13, &pftDueTime, 0, 0x124F8u);
          LOBYTE(pv[3].Ptr) = 1;
        }
      }
      goto LABEL_24;
    }
    v6 = pv[5].Ptr;
    v7 = ((char *)pv[6].Ptr - (char *)v6) & -(__int64)(v6 < pv[6].Ptr);
    if ( v6 )
    {
      if ( v7 >= 0x10 )
      {
        *v6 = 47350999;
        v6[1] = a3;
LABEL_16:
        pv[5].Ptr = (char *)pv[5].Ptr + 16;
        goto LABEL_17;
      }
      memset_0(v6, 0, v7);
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0, v5, v7) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x180006488  push    rbx
0x18000648a  push    rbp
0x18000648b  push    rsi
0x18000648c  push    rdi
0x18000648d  push    r14
0x18000648f  push    r15
0x180006491  sub     rsp, 28h
0x180006495  mov     eax, [rcx]
0x180006497  mov     rbp, r8
0x18000649a  mov     rdi, rcx
0x18000649d  test    eax, eax
0x18000649f  jz      loc_18000662E
0x1800064a5  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800064ac  jnz     loc_18000662E
0x1800064b2  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800064b9  test    rax, rax
0x1800064bc  jz      short loc_1800064CB
0x1800064be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064c3  test    al, al
0x1800064c5  jnz     loc_18000662E
0x1800064cb  lea     rsi, [rdi+8]
0x1800064cf  mov     rcx, rsi; SRWLock
0x1800064d2  call    cs:__imp_AcquireSRWLockExclusive
0x1800064d8  mov     eax, [rdi]
0x1800064da  test    eax, eax
0x1800064dc  jz      loc_180006620
0x1800064e2  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800064e9  jnz     loc_180006620
0x1800064ef  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800064f6  test    rax, rax
0x1800064f9  jz      short loc_180006508
0x1800064fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006500  test    al, al
0x180006502  jnz     loc_180006620
0x180006508  mov     edx, 10h; unsigned __int64
0x18000650d  lea     rcx, [rdi+20h]; this
0x180006511  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180006516  test    al, al
0x180006518  jz      short loc_180006572
0x18000651a  mov     rcx, [rdi+28h]; void *
0x18000651e  mov     rax, [rdi+30h]
0x180006522  sub     rax, rcx
0x180006525  cmp     rcx, [rdi+30h]
0x180006529  sbb     r8, r8
0x18000652c  and     r8, rax; Size
0x18000652f  test    rcx, rcx
0x180006532  jnz     short loc_180006542
0x180006534  call    cs:__imp__o__errno
0x18000653a  mov     dword ptr [rax], 16h
0x180006540  jmp     short loc_180006568
0x180006542  cmp     r8, 10h
0x180006546  jb      short loc_180006555
0x180006548  mov     qword ptr [rcx], 2D284D7h
0x18000654f  mov     [rcx+8], rbp
0x180006553  jmp     short loc_18000656D
0x180006555  xor     edx, edx; Val
0x180006557  call    memset_0
0x18000655c  call    cs:__imp__o__errno
0x180006562  mov     dword ptr [rax], 22h ; '"'
0x180006568  call    _invalid_parameter_noinfo
0x18000656d  add     qword ptr [rdi+28h], 10h
0x180006572  cmp     byte ptr [rdi+18h], 0
0x180006576  jnz     loc_180006620
0x18000657c  cmp     qword ptr [rdi+10h], 0
0x180006581  jnz     short loc_1800065F0
0x180006583  call    cs:__imp_GetLastError
0x180006589  xor     r8d, r8d; pcbe
0x18000658c  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180006593  mov     rdx, rdi; pv
0x180006596  mov     r14d, eax
0x180006599  call    cs:__imp_CreateThreadpoolTimer
0x18000659f  mov     rbp, [rdi+10h]
0x1800065a3  mov     r15, rax
0x1800065a6  test    rbp, rbp
0x1800065a9  jz      short loc_1800065E3
0x1800065ab  call    cs:__imp_GetLastError
0x1800065b1  xor     r9d, r9d; msWindowLength
0x1800065b4  xor     r8d, r8d; msPeriod
0x1800065b7  xor     edx, edx; pftDueTime
0x1800065b9  mov     rcx, rbp; pti
0x1800065bc  mov     ebx, eax
0x1800065be  call    cs:__imp_SetThreadpoolTimer
0x1800065c4  mov     edx, 1; fCancelPendingCallbacks
0x1800065c9  mov     rcx, rbp; pti
0x1800065cc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800065d2  mov     rcx, rbp; pti
0x1800065d5  call    cs:__imp_CloseThreadpoolTimer
0x1800065db  mov     ecx, ebx; dwErrCode
0x1800065dd  call    cs:__imp_SetLastError
0x1800065e3  mov     ecx, r14d; dwErrCode
0x1800065e6  mov     [rdi+10h], r15
0x1800065ea  call    cs:__imp_SetLastError
0x1800065f0  mov     rcx, [rdi+10h]; pti
0x1800065f4  test    rcx, rcx
0x1800065f7  jz      short loc_180006620
0x1800065f9  mov     rax, 0FFFFFFFF4D2FA200h
0x180006603  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180006608  mov     r9d, 124F8h; msWindowLength
0x18000660e  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x180006613  xor     r8d, r8d; msPeriod
0x180006616  call    cs:__imp_SetThreadpoolTimer
0x18000661c  mov     byte ptr [rdi+18h], 1
0x180006620  test    rsi, rsi
0x180006623  jz      short loc_18000662E
0x180006625  mov     rcx, rsi; SRWLock
0x180006628  call    cs:__imp_ReleaseSRWLockExclusive
0x18000662e  add     rsp, 28h
0x180006632  pop     r15
0x180006634  pop     r14
0x180006636  pop     rdi
0x180006637  pop     rsi
0x180006638  pop     rbp
0x180006639  pop     rbx
0x18000663a  retn
```
