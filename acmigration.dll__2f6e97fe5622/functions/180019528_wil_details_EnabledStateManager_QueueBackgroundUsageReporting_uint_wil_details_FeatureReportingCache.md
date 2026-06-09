# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180019528`
- end: `0x1800196e9`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `449`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800197cc`

## callees

- `0x18000273e`
- `0x180002874`
- `0x180009e2c`
- `0x180019528`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800195e2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001960a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800195e2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001960a`
- `KERNEL32!CreateThreadpoolTimer` at `0x180019646`
- `KERNEL32!CreateThreadpoolTimer` at `0x180019646`
- `KERNEL32!SetThreadpoolTimer` at `0x18001966b`
- `KERNEL32!SetThreadpoolTimer` at `0x1800196c3`
- `KERNEL32!SetThreadpoolTimer` at `0x18001966b`
- `KERNEL32!SetThreadpoolTimer` at `0x1800196c3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001957e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001957e`
- `KERNEL32!CloseThreadpoolTimer` at `0x180019682`
- `KERNEL32!CloseThreadpoolTimer` at `0x180019682`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800196d5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800196d5`
- `KERNEL32!GetLastError` at `0x180019630`
- `KERNEL32!GetLastError` at `0x180019658`
- `KERNEL32!GetLastError` at `0x180019630`
- `KERNEL32!GetLastError` at `0x180019658`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180019679`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180019679`
- `KERNEL32!SetLastError` at `0x18001968a`
- `KERNEL32!SetLastError` at `0x180019697`
- `KERNEL32!SetLastError` at `0x18001968a`
- `KERNEL32!SetLastError` at `0x180019697`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  __int64 v6; // rcx
  _DWORD *v7; // rcx
  size_t v8; // r8
  __int64 v9; // rcx
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v13; // ebx
  struct _TP_TIMER *v14; // rcx
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress(pv)) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( !LODWORD(pv->Ptr)
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress(v6) )
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
          if ( Ptr )
          {
            v13 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v13);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v14 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v14 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v14, &pftDueTime, 0, 0x124F8u);
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
      *(_DWORD *)_o__errno(v9) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x180019528  push    rbx
0x18001952a  push    rbp
0x18001952b  push    rsi
0x18001952c  push    rdi
0x18001952d  push    r14
0x18001952f  push    r15
0x180019531  sub     rsp, 38h
0x180019535  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x18001953e  mov     rbp, r8
0x180019541  mov     r14d, edx
0x180019544  mov     rdi, rcx
0x180019547  mov     eax, [rcx]
0x180019549  test    eax, eax
0x18001954b  jz      loc_1800196DC
0x180019551  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180019558  jnz     loc_1800196DC
0x18001955e  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180019565  test    rax, rax
0x180019568  jz      short loc_180019577
0x18001956a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001956f  test    al, al
0x180019571  jnz     loc_1800196DC
0x180019577  lea     rsi, [rdi+8]
0x18001957b  mov     rcx, rsi; SRWLock
0x18001957e  call    cs:__imp_AcquireSRWLockExclusive
0x180019584  mov     eax, [rdi]
0x180019586  test    eax, eax
0x180019588  jz      loc_1800196CD
0x18001958e  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180019595  jnz     loc_1800196CD
0x18001959b  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800195a2  test    rax, rax
0x1800195a5  jz      short loc_1800195B4
0x1800195a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195ac  test    al, al
0x1800195ae  jnz     loc_1800196CD
0x1800195b4  xor     r15d, r15d
0x1800195b7  lea     edx, [r15+10h]; unsigned __int64
0x1800195bb  lea     rcx, [rdi+20h]; this
0x1800195bf  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800195c4  test    al, al
0x1800195c6  jz      short loc_180019620
0x1800195c8  mov     rcx, [rdi+28h]; void *
0x1800195cc  mov     rax, [rdi+30h]
0x1800195d0  sub     rax, rcx
0x1800195d3  cmp     rcx, [rdi+30h]
0x1800195d7  sbb     r8, r8
0x1800195da  and     r8, rax; Size
0x1800195dd  test    rcx, rcx
0x1800195e0  jnz     short loc_1800195F0
0x1800195e2  call    cs:__imp__o__errno
0x1800195e8  mov     dword ptr [rax], 16h
0x1800195ee  jmp     short loc_180019616
0x1800195f0  cmp     r8, 10h
0x1800195f4  jb      short loc_180019603
0x1800195f6  mov     [rcx], r14d
0x1800195f9  mov     [rcx+4], r15d
0x1800195fd  mov     [rcx+8], rbp
0x180019601  jmp     short loc_18001961B
0x180019603  xor     edx, edx; Val
0x180019605  call    memset_0
0x18001960a  call    cs:__imp__o__errno
0x180019610  mov     dword ptr [rax], 22h ; '"'
0x180019616  call    _invalid_parameter_noinfo
0x18001961b  add     qword ptr [rdi+28h], 10h
0x180019620  cmp     [rdi+18h], r15b
0x180019624  jnz     loc_1800196CD
0x18001962a  cmp     [rdi+10h], r15
0x18001962e  jnz     short loc_18001969D
0x180019630  call    cs:__imp_GetLastError
0x180019636  mov     r14d, eax
0x180019639  xor     r8d, r8d; pcbe
0x18001963c  mov     rdx, rdi; pv
0x18001963f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180019646  call    cs:__imp_CreateThreadpoolTimer
0x18001964c  mov     r15, rax
0x18001964f  mov     rbp, [rdi+10h]
0x180019653  test    rbp, rbp
0x180019656  jz      short loc_180019690
0x180019658  call    cs:__imp_GetLastError
0x18001965e  mov     ebx, eax
0x180019660  xor     r9d, r9d; msWindowLength
0x180019663  xor     r8d, r8d; msPeriod
0x180019666  xor     edx, edx; pftDueTime
0x180019668  mov     rcx, rbp; pti
0x18001966b  call    cs:__imp_SetThreadpoolTimer
0x180019671  mov     edx, 1; fCancelPendingCallbacks
0x180019676  mov     rcx, rbp; pti
0x180019679  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001967f  mov     rcx, rbp; pti
0x180019682  call    cs:__imp_CloseThreadpoolTimer
0x180019688  mov     ecx, ebx; dwErrCode
0x18001968a  call    cs:__imp_SetLastError
0x180019690  mov     [rdi+10h], r15
0x180019694  mov     ecx, r14d; dwErrCode
0x180019697  call    cs:__imp_SetLastError
0x18001969d  mov     rcx, [rdi+10h]; pti
0x1800196a1  test    rcx, rcx
0x1800196a4  jz      short loc_1800196CD
0x1800196a6  mov     rax, 0FFFFFFFF4D2FA200h
0x1800196b0  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x1800196b5  mov     r9d, 124F8h; msWindowLength
0x1800196bb  xor     r8d, r8d; msPeriod
0x1800196be  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x1800196c3  call    cs:__imp_SetThreadpoolTimer
0x1800196c9  mov     byte ptr [rdi+18h], 1
0x1800196cd  test    rsi, rsi
0x1800196d0  jz      short loc_1800196DC
0x1800196d2  mov     rcx, rsi; SRWLock
0x1800196d5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800196db  nop
0x1800196dc  add     rsp, 38h
0x1800196e0  pop     r15
0x1800196e2  pop     r14
0x1800196e4  pop     rdi
0x1800196e5  pop     rsi
0x1800196e6  pop     rbp
0x1800196e7  pop     rbx
0x1800196e8  retn
```
