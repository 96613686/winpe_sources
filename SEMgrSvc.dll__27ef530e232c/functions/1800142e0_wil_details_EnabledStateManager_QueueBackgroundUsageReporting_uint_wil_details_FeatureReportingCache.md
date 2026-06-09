# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1800142e0`
- end: `0x180014498`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800145d8`

## callees

- `0x1800057c6`
- `0x180005858`
- `0x18000e60c`
- `0x1800142e0`
- `0x18009d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180014391`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800143b9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180014391`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800143b9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001432d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001432d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014484`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014484`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800143df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014407`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800143df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014407`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014439`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014446`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014439`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014446`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014428`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014428`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800143f5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800143f5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001441a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014472`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001441a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014472`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014431`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014431`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  __int64 v6; // rdx
  _DWORD *v7; // rcx
  size_t v8; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
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
                              `wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          Ptr = (struct _TP_TIMER *)pv[2].Ptr;
          if ( Ptr )
          {
            v12 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v12);
          }
          pv[2].Ptr = ThreadpoolTimer;
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
    v7 = pv[5].Ptr;
    v8 = ((char *)pv[6].Ptr - (char *)v7) & -(__int64)(v7 < pv[6].Ptr);
    if ( v7 )
    {
      if ( v8 >= 0x10 )
      {
        *v7 = a2;
        v7[1] = 0;
        *((_QWORD *)v7 + 1) = a3;
LABEL_16:
        pv[5].Ptr = (char *)pv[5].Ptr + 16;
        goto LABEL_17;
      }
      memset_0(v7, 0, v8);
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0, v6, v8) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x1800142e0  push    rbx
0x1800142e2  push    rbp
0x1800142e3  push    rsi
0x1800142e4  push    rdi
0x1800142e5  push    r14
0x1800142e7  push    r15
0x1800142e9  sub     rsp, 28h
0x1800142ed  mov     rbp, r8
0x1800142f0  mov     r14d, edx
0x1800142f3  mov     rdi, rcx
0x1800142f6  mov     eax, [rcx]
0x1800142f8  test    eax, eax
0x1800142fa  jz      loc_18001448B
0x180014300  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180014307  jnz     loc_18001448B
0x18001430d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180014314  test    rax, rax
0x180014317  jz      short loc_180014326
0x180014319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001431e  test    al, al
0x180014320  jnz     loc_18001448B
0x180014326  lea     rsi, [rdi+8]
0x18001432a  mov     rcx, rsi; SRWLock
0x18001432d  call    cs:__imp_AcquireSRWLockExclusive
0x180014333  mov     eax, [rdi]
0x180014335  test    eax, eax
0x180014337  jz      loc_18001447C
0x18001433d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180014344  jnz     loc_18001447C
0x18001434a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180014351  test    rax, rax
0x180014354  jz      short loc_180014363
0x180014356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001435b  test    al, al
0x18001435d  jnz     loc_18001447C
0x180014363  xor     r15d, r15d
0x180014366  lea     edx, [r15+10h]; unsigned __int64
0x18001436a  lea     rcx, [rdi+20h]; this
0x18001436e  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180014373  test    al, al
0x180014375  jz      short loc_1800143CF
0x180014377  mov     rcx, [rdi+28h]; void *
0x18001437b  mov     rax, [rdi+30h]
0x18001437f  sub     rax, rcx
0x180014382  cmp     rcx, [rdi+30h]
0x180014386  sbb     r8, r8
0x180014389  and     r8, rax; Size
0x18001438c  test    rcx, rcx
0x18001438f  jnz     short loc_18001439F
0x180014391  call    cs:__imp__o__errno
0x180014397  mov     dword ptr [rax], 16h
0x18001439d  jmp     short loc_1800143C5
0x18001439f  cmp     r8, 10h
0x1800143a3  jb      short loc_1800143B2
0x1800143a5  mov     [rcx], r14d
0x1800143a8  mov     [rcx+4], r15d
0x1800143ac  mov     [rcx+8], rbp
0x1800143b0  jmp     short loc_1800143CA
0x1800143b2  xor     edx, edx; Val
0x1800143b4  call    memset_0
0x1800143b9  call    cs:__imp__o__errno
0x1800143bf  mov     dword ptr [rax], 22h ; '"'
0x1800143c5  call    _invalid_parameter_noinfo
0x1800143ca  add     qword ptr [rdi+28h], 10h
0x1800143cf  cmp     [rdi+18h], r15b
0x1800143d3  jnz     loc_18001447C
0x1800143d9  cmp     [rdi+10h], r15
0x1800143dd  jnz     short loc_18001444C
0x1800143df  call    cs:__imp_GetLastError
0x1800143e5  mov     r14d, eax
0x1800143e8  xor     r8d, r8d; pcbe
0x1800143eb  mov     rdx, rdi; pv
0x1800143ee  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800143f5  call    cs:__imp_CreateThreadpoolTimer
0x1800143fb  mov     r15, rax
0x1800143fe  mov     rbp, [rdi+10h]
0x180014402  test    rbp, rbp
0x180014405  jz      short loc_18001443F
0x180014407  call    cs:__imp_GetLastError
0x18001440d  mov     ebx, eax
0x18001440f  xor     r9d, r9d; msWindowLength
0x180014412  xor     r8d, r8d; msPeriod
0x180014415  xor     edx, edx; pftDueTime
0x180014417  mov     rcx, rbp; pti
0x18001441a  call    cs:__imp_SetThreadpoolTimer
0x180014420  mov     edx, 1; fCancelPendingCallbacks
0x180014425  mov     rcx, rbp; pti
0x180014428  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001442e  mov     rcx, rbp; pti
0x180014431  call    cs:__imp_CloseThreadpoolTimer
0x180014437  mov     ecx, ebx; dwErrCode
0x180014439  call    cs:__imp_SetLastError
0x18001443f  mov     [rdi+10h], r15
0x180014443  mov     ecx, r14d; dwErrCode
0x180014446  call    cs:__imp_SetLastError
0x18001444c  mov     rcx, [rdi+10h]; pti
0x180014450  test    rcx, rcx
0x180014453  jz      short loc_18001447C
0x180014455  mov     rax, 0FFFFFFFF4D2FA200h
0x18001445f  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x180014464  mov     r9d, 124F8h; msWindowLength
0x18001446a  xor     r8d, r8d; msPeriod
0x18001446d  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180014472  call    cs:__imp_SetThreadpoolTimer
0x180014478  mov     byte ptr [rdi+18h], 1
0x18001447c  test    rsi, rsi
0x18001447f  jz      short loc_18001448B
0x180014481  mov     rcx, rsi; SRWLock
0x180014484  call    cs:__imp_ReleaseSRWLockExclusive
0x18001448a  nop
0x18001448b  add     rsp, 28h
0x18001448f  pop     r15
0x180014491  pop     r14
0x180014493  pop     rdi
0x180014494  pop     rsi
0x180014495  pop     rbp
0x180014496  pop     rbx
0x180014497  retn
```
