# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18007c57c`
- end: `0x18007c734`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18007c930`

## callees

- `0x18005ff2a`
- `0x18005ffc4`
- `0x180077a8c`
- `0x18007c57c`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007c62d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007c655`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007c62d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007c655`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007c720`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007c720`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007c5c9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007c5c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007c6d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007c6e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007c6d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007c6e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c67b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c6a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c67b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c6a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18007c6cd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18007c6cd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18007c6c4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18007c6c4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007c6b6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007c70e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007c6b6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007c70e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18007c691`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18007c691`

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
0x18007c57c  push    rbx
0x18007c57e  push    rbp
0x18007c57f  push    rsi
0x18007c580  push    rdi
0x18007c581  push    r14
0x18007c583  push    r15
0x18007c585  sub     rsp, 28h
0x18007c589  mov     rbp, r8
0x18007c58c  mov     r14d, edx
0x18007c58f  mov     rdi, rcx
0x18007c592  mov     eax, [rcx]
0x18007c594  test    eax, eax
0x18007c596  jz      loc_18007C727
0x18007c59c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18007c5a3  jnz     loc_18007C727
0x18007c5a9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18007c5b0  test    rax, rax
0x18007c5b3  jz      short loc_18007C5C2
0x18007c5b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c5ba  test    al, al
0x18007c5bc  jnz     loc_18007C727
0x18007c5c2  lea     rsi, [rdi+8]
0x18007c5c6  mov     rcx, rsi; SRWLock
0x18007c5c9  call    cs:__imp_AcquireSRWLockExclusive
0x18007c5cf  mov     eax, [rdi]
0x18007c5d1  test    eax, eax
0x18007c5d3  jz      loc_18007C718
0x18007c5d9  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18007c5e0  jnz     loc_18007C718
0x18007c5e6  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18007c5ed  test    rax, rax
0x18007c5f0  jz      short loc_18007C5FF
0x18007c5f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c5f7  test    al, al
0x18007c5f9  jnz     loc_18007C718
0x18007c5ff  xor     r15d, r15d
0x18007c602  lea     edx, [r15+10h]; unsigned __int64
0x18007c606  lea     rcx, [rdi+20h]; this
0x18007c60a  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18007c60f  test    al, al
0x18007c611  jz      short loc_18007C66B
0x18007c613  mov     rcx, [rdi+28h]; void *
0x18007c617  mov     rax, [rdi+30h]
0x18007c61b  sub     rax, rcx
0x18007c61e  cmp     rcx, [rdi+30h]
0x18007c622  sbb     r8, r8
0x18007c625  and     r8, rax; Size
0x18007c628  test    rcx, rcx
0x18007c62b  jnz     short loc_18007C63B
0x18007c62d  call    cs:__imp__o__errno
0x18007c633  mov     dword ptr [rax], 16h
0x18007c639  jmp     short loc_18007C661
0x18007c63b  cmp     r8, 10h
0x18007c63f  jb      short loc_18007C64E
0x18007c641  mov     [rcx], r14d
0x18007c644  mov     [rcx+4], r15d
0x18007c648  mov     [rcx+8], rbp
0x18007c64c  jmp     short loc_18007C666
0x18007c64e  xor     edx, edx; Val
0x18007c650  call    memset_0
0x18007c655  call    cs:__imp__o__errno
0x18007c65b  mov     dword ptr [rax], 22h ; '"'
0x18007c661  call    _invalid_parameter_noinfo
0x18007c666  add     qword ptr [rdi+28h], 10h
0x18007c66b  cmp     [rdi+18h], r15b
0x18007c66f  jnz     loc_18007C718
0x18007c675  cmp     [rdi+10h], r15
0x18007c679  jnz     short loc_18007C6E8
0x18007c67b  call    cs:__imp_GetLastError
0x18007c681  mov     r14d, eax
0x18007c684  xor     r8d, r8d; pcbe
0x18007c687  mov     rdx, rdi; pv
0x18007c68a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18007c691  call    cs:__imp_CreateThreadpoolTimer
0x18007c697  mov     r15, rax
0x18007c69a  mov     rbp, [rdi+10h]
0x18007c69e  test    rbp, rbp
0x18007c6a1  jz      short loc_18007C6DB
0x18007c6a3  call    cs:__imp_GetLastError
0x18007c6a9  mov     ebx, eax
0x18007c6ab  xor     r9d, r9d; msWindowLength
0x18007c6ae  xor     r8d, r8d; msPeriod
0x18007c6b1  xor     edx, edx; pftDueTime
0x18007c6b3  mov     rcx, rbp; pti
0x18007c6b6  call    cs:__imp_SetThreadpoolTimer
0x18007c6bc  mov     edx, 1; fCancelPendingCallbacks
0x18007c6c1  mov     rcx, rbp; pti
0x18007c6c4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18007c6ca  mov     rcx, rbp; pti
0x18007c6cd  call    cs:__imp_CloseThreadpoolTimer
0x18007c6d3  mov     ecx, ebx; dwErrCode
0x18007c6d5  call    cs:__imp_SetLastError
0x18007c6db  mov     [rdi+10h], r15
0x18007c6df  mov     ecx, r14d; dwErrCode
0x18007c6e2  call    cs:__imp_SetLastError
0x18007c6e8  mov     rcx, [rdi+10h]; pti
0x18007c6ec  test    rcx, rcx
0x18007c6ef  jz      short loc_18007C718
0x18007c6f1  mov     rax, 0FFFFFFFF4D2FA200h
0x18007c6fb  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18007c700  mov     r9d, 124F8h; msWindowLength
0x18007c706  xor     r8d, r8d; msPeriod
0x18007c709  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18007c70e  call    cs:__imp_SetThreadpoolTimer
0x18007c714  mov     byte ptr [rdi+18h], 1
0x18007c718  test    rsi, rsi
0x18007c71b  jz      short loc_18007C727
0x18007c71d  mov     rcx, rsi; SRWLock
0x18007c720  call    cs:__imp_ReleaseSRWLockExclusive
0x18007c726  nop
0x18007c727  add     rsp, 28h
0x18007c72b  pop     r15
0x18007c72d  pop     r14
0x18007c72f  pop     rdi
0x18007c730  pop     rsi
0x18007c731  pop     rbp
0x18007c732  pop     rbx
0x18007c733  retn
```
