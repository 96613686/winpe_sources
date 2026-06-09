# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000624c`
- end: `0x180006400`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `436`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, __int64, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180007788`

## callees

- `0x180001fca`
- `0x180002034`
- `0x18000624c`
- `0x18000d5fc`
- `0x180014010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800062f8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006320`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800062f8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006347`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000636f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006347`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000636f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800063a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800063ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800063a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800063ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800063ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800063ec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006296`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006296`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006399`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006399`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006390`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006390`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006382`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800063da`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006382`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800063da`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000635d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000635d`

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
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v14; // ebx
  struct _TP_TIMER *v15; // rcx
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
                              (PTP_TIMER_CALLBACK)`wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          Ptr = (struct _TP_TIMER *)pv[2].Ptr;
          if ( Ptr )
          {
            v14 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v14);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v15 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v15 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v15, &pftDueTime, 0, 0x124F8u);
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
        *v6 = 60900037;
        v6[1] = a3;
LABEL_16:
        pv[5].Ptr = (char *)pv[5].Ptr + 16;
        goto LABEL_17;
      }
      memset_0(v6, 0, v7);
      *(_DWORD *)_o__errno(v9, v8, v10) = 34;
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
0x18000624c  push    rbx
0x18000624e  push    rbp
0x18000624f  push    rsi
0x180006250  push    rdi
0x180006251  push    r14
0x180006253  push    r15
0x180006255  sub     rsp, 28h
0x180006259  mov     rbp, r8
0x18000625c  mov     rdi, rcx
0x18000625f  mov     eax, [rcx]
0x180006261  test    eax, eax
0x180006263  jz      loc_1800063F3
0x180006269  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180006270  jnz     loc_1800063F3
0x180006276  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000627d  test    rax, rax
0x180006280  jz      short loc_18000628F
0x180006282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006287  test    al, al
0x180006289  jnz     loc_1800063F3
0x18000628f  lea     rsi, [rdi+8]
0x180006293  mov     rcx, rsi; SRWLock
0x180006296  call    cs:__imp_AcquireSRWLockExclusive
0x18000629c  mov     eax, [rdi]
0x18000629e  test    eax, eax
0x1800062a0  jz      loc_1800063E4
0x1800062a6  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800062ad  jnz     loc_1800063E4
0x1800062b3  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800062ba  test    rax, rax
0x1800062bd  jz      short loc_1800062CC
0x1800062bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062c4  test    al, al
0x1800062c6  jnz     loc_1800063E4
0x1800062cc  mov     edx, 10h; unsigned __int64
0x1800062d1  lea     rcx, [rdi+20h]; this
0x1800062d5  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800062da  test    al, al
0x1800062dc  jz      short loc_180006336
0x1800062de  mov     rcx, [rdi+28h]; void *
0x1800062e2  mov     rax, [rdi+30h]
0x1800062e6  sub     rax, rcx
0x1800062e9  cmp     rcx, [rdi+30h]
0x1800062ed  sbb     r8, r8
0x1800062f0  and     r8, rax; Size
0x1800062f3  test    rcx, rcx
0x1800062f6  jnz     short loc_180006306
0x1800062f8  call    cs:__imp__o__errno
0x1800062fe  mov     dword ptr [rax], 16h
0x180006304  jmp     short loc_18000632C
0x180006306  cmp     r8, 10h
0x18000630a  jb      short loc_180006319
0x18000630c  mov     qword ptr [rcx], 3A142C5h
0x180006313  mov     [rcx+8], rbp
0x180006317  jmp     short loc_180006331
0x180006319  xor     edx, edx; Val
0x18000631b  call    memset_0
0x180006320  call    cs:__imp__o__errno
0x180006326  mov     dword ptr [rax], 22h ; '"'
0x18000632c  call    _invalid_parameter_noinfo
0x180006331  add     qword ptr [rdi+28h], 10h
0x180006336  cmp     byte ptr [rdi+18h], 0
0x18000633a  jnz     loc_1800063E4
0x180006340  cmp     qword ptr [rdi+10h], 0
0x180006345  jnz     short loc_1800063B4
0x180006347  call    cs:__imp_GetLastError
0x18000634d  mov     r14d, eax
0x180006350  xor     r8d, r8d; pcbe
0x180006353  mov     rdx, rdi; pv
0x180006356  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000635d  call    cs:__imp_CreateThreadpoolTimer
0x180006363  mov     r15, rax
0x180006366  mov     rbp, [rdi+10h]
0x18000636a  test    rbp, rbp
0x18000636d  jz      short loc_1800063A7
0x18000636f  call    cs:__imp_GetLastError
0x180006375  mov     ebx, eax
0x180006377  xor     r9d, r9d; msWindowLength
0x18000637a  xor     r8d, r8d; msPeriod
0x18000637d  xor     edx, edx; pftDueTime
0x18000637f  mov     rcx, rbp; pti
0x180006382  call    cs:__imp_SetThreadpoolTimer
0x180006388  mov     edx, 1; fCancelPendingCallbacks
0x18000638d  mov     rcx, rbp; pti
0x180006390  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006396  mov     rcx, rbp; pti
0x180006399  call    cs:__imp_CloseThreadpoolTimer
0x18000639f  mov     ecx, ebx; dwErrCode
0x1800063a1  call    cs:__imp_SetLastError
0x1800063a7  mov     [rdi+10h], r15
0x1800063ab  mov     ecx, r14d; dwErrCode
0x1800063ae  call    cs:__imp_SetLastError
0x1800063b4  mov     rcx, [rdi+10h]; pti
0x1800063b8  test    rcx, rcx
0x1800063bb  jz      short loc_1800063E4
0x1800063bd  mov     rax, 0FFFFFFFF4D2FA200h
0x1800063c7  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x1800063cc  mov     r9d, 124F8h; msWindowLength
0x1800063d2  xor     r8d, r8d; msPeriod
0x1800063d5  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x1800063da  call    cs:__imp_SetThreadpoolTimer
0x1800063e0  mov     byte ptr [rdi+18h], 1
0x1800063e4  test    rsi, rsi
0x1800063e7  jz      short loc_1800063F3
0x1800063e9  mov     rcx, rsi; SRWLock
0x1800063ec  call    cs:__imp_ReleaseSRWLockExclusive
0x1800063f2  nop
0x1800063f3  add     rsp, 28h
0x1800063f7  pop     r15
0x1800063f9  pop     r14
0x1800063fb  pop     rdi
0x1800063fc  pop     rsi
0x1800063fd  pop     rbp
0x1800063fe  pop     rbx
0x1800063ff  retn
```
