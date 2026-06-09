# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x140008f8c`
- end: `0x140009144`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14000a518`

## callees

- `0x140002ff2`
- `0x1400030a8`
- `0x140008f8c`
- `0x14000ca4c`
- `0x14005d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000903d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140009065`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000903d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140009065`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008fd9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008fd9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009130`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009130`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000908b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400090b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000908b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400090b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400090e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400090f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400090e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400090f2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400090dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400090dd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400090d4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400090d4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400090a1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400090a1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400090c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000911e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400090c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000911e`

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
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
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
0x140008f8c  push    rbx
0x140008f8e  push    rbp
0x140008f8f  push    rsi
0x140008f90  push    rdi
0x140008f91  push    r14
0x140008f93  push    r15
0x140008f95  sub     rsp, 28h
0x140008f99  mov     rbp, r8
0x140008f9c  mov     r14d, edx
0x140008f9f  mov     rdi, rcx
0x140008fa2  mov     eax, [rcx]
0x140008fa4  test    eax, eax
0x140008fa6  jz      loc_140009137
0x140008fac  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140008fb3  jnz     loc_140009137
0x140008fb9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140008fc0  test    rax, rax
0x140008fc3  jz      short loc_140008FD2
0x140008fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008fca  test    al, al
0x140008fcc  jnz     loc_140009137
0x140008fd2  lea     rsi, [rdi+8]
0x140008fd6  mov     rcx, rsi; SRWLock
0x140008fd9  call    cs:__imp_AcquireSRWLockExclusive
0x140008fdf  mov     eax, [rdi]
0x140008fe1  test    eax, eax
0x140008fe3  jz      loc_140009128
0x140008fe9  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140008ff0  jnz     loc_140009128
0x140008ff6  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140008ffd  test    rax, rax
0x140009000  jz      short loc_14000900F
0x140009002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009007  test    al, al
0x140009009  jnz     loc_140009128
0x14000900f  xor     r15d, r15d
0x140009012  lea     edx, [r15+10h]; unsigned __int64
0x140009016  lea     rcx, [rdi+20h]; this
0x14000901a  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000901f  test    al, al
0x140009021  jz      short loc_14000907B
0x140009023  mov     rcx, [rdi+28h]; void *
0x140009027  mov     rax, [rdi+30h]
0x14000902b  sub     rax, rcx
0x14000902e  cmp     rcx, [rdi+30h]
0x140009032  sbb     r8, r8
0x140009035  and     r8, rax; Size
0x140009038  test    rcx, rcx
0x14000903b  jnz     short loc_14000904B
0x14000903d  call    cs:__imp__o__errno
0x140009043  mov     dword ptr [rax], 16h
0x140009049  jmp     short loc_140009071
0x14000904b  cmp     r8, 10h
0x14000904f  jb      short loc_14000905E
0x140009051  mov     [rcx], r14d
0x140009054  mov     [rcx+4], r15d
0x140009058  mov     [rcx+8], rbp
0x14000905c  jmp     short loc_140009076
0x14000905e  xor     edx, edx; Val
0x140009060  call    memset_0
0x140009065  call    cs:__imp__o__errno
0x14000906b  mov     dword ptr [rax], 22h ; '"'
0x140009071  call    _invalid_parameter_noinfo
0x140009076  add     qword ptr [rdi+28h], 10h
0x14000907b  cmp     [rdi+18h], r15b
0x14000907f  jnz     loc_140009128
0x140009085  cmp     [rdi+10h], r15
0x140009089  jnz     short loc_1400090F8
0x14000908b  call    cs:__imp_GetLastError
0x140009091  mov     r14d, eax
0x140009094  xor     r8d, r8d; pcbe
0x140009097  mov     rdx, rdi; pv
0x14000909a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400090a1  call    cs:__imp_CreateThreadpoolTimer
0x1400090a7  mov     r15, rax
0x1400090aa  mov     rbp, [rdi+10h]
0x1400090ae  test    rbp, rbp
0x1400090b1  jz      short loc_1400090EB
0x1400090b3  call    cs:__imp_GetLastError
0x1400090b9  mov     ebx, eax
0x1400090bb  xor     r9d, r9d; msWindowLength
0x1400090be  xor     r8d, r8d; msPeriod
0x1400090c1  xor     edx, edx; pftDueTime
0x1400090c3  mov     rcx, rbp; pti
0x1400090c6  call    cs:__imp_SetThreadpoolTimer
0x1400090cc  mov     edx, 1; fCancelPendingCallbacks
0x1400090d1  mov     rcx, rbp; pti
0x1400090d4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400090da  mov     rcx, rbp; pti
0x1400090dd  call    cs:__imp_CloseThreadpoolTimer
0x1400090e3  mov     ecx, ebx; dwErrCode
0x1400090e5  call    cs:__imp_SetLastError
0x1400090eb  mov     [rdi+10h], r15
0x1400090ef  mov     ecx, r14d; dwErrCode
0x1400090f2  call    cs:__imp_SetLastError
0x1400090f8  mov     rcx, [rdi+10h]; pti
0x1400090fc  test    rcx, rcx
0x1400090ff  jz      short loc_140009128
0x140009101  mov     rax, 0FFFFFFFF4D2FA200h
0x14000910b  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x140009110  mov     r9d, 124F8h; msWindowLength
0x140009116  xor     r8d, r8d; msPeriod
0x140009119  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x14000911e  call    cs:__imp_SetThreadpoolTimer
0x140009124  mov     byte ptr [rdi+18h], 1
0x140009128  test    rsi, rsi
0x14000912b  jz      short loc_140009137
0x14000912d  mov     rcx, rsi; SRWLock
0x140009130  call    cs:__imp_ReleaseSRWLockExclusive
0x140009136  nop
0x140009137  add     rsp, 28h
0x14000913b  pop     r15
0x14000913d  pop     r14
0x14000913f  pop     rdi
0x140009140  pop     rsi
0x140009141  pop     rbp
0x140009142  pop     rbx
0x140009143  retn
```
