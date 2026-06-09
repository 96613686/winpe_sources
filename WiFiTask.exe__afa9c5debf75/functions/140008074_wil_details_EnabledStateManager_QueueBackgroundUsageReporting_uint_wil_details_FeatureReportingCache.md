# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x140008074`
- end: `0x14000822c`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400096c8`

## callees

- `0x1400020b2`
- `0x140002168`
- `0x140008074`
- `0x14000b92c`
- `0x140012010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140008125`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000814d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140008125`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000814d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400081bc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400081bc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140008189`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140008189`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400081ae`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008206`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400081ae`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008206`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400081c5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400081c5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400080c1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400080c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008218`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008218`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400081cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400081da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400081cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400081da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008173`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000819b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008173`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000819b`

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
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v15; // ebx
  struct _TP_TIMER *v16; // rcx
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
            v15 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v15);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v16 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v16 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v16, &pftDueTime, 0, 0x124F8u);
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
      *(_DWORD *)_o__errno(v10, v9, v11) = 34;
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
0x140008074  push    rbx
0x140008076  push    rbp
0x140008077  push    rsi
0x140008078  push    rdi
0x140008079  push    r14
0x14000807b  push    r15
0x14000807d  sub     rsp, 28h
0x140008081  mov     rbp, r8
0x140008084  mov     r14d, edx
0x140008087  mov     rdi, rcx
0x14000808a  mov     eax, [rcx]
0x14000808c  test    eax, eax
0x14000808e  jz      loc_14000821F
0x140008094  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000809b  jnz     loc_14000821F
0x1400080a1  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1400080a8  test    rax, rax
0x1400080ab  jz      short loc_1400080BA
0x1400080ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400080b2  test    al, al
0x1400080b4  jnz     loc_14000821F
0x1400080ba  lea     rsi, [rdi+8]
0x1400080be  mov     rcx, rsi; SRWLock
0x1400080c1  call    cs:__imp_AcquireSRWLockExclusive
0x1400080c7  mov     eax, [rdi]
0x1400080c9  test    eax, eax
0x1400080cb  jz      loc_140008210
0x1400080d1  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1400080d8  jnz     loc_140008210
0x1400080de  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1400080e5  test    rax, rax
0x1400080e8  jz      short loc_1400080F7
0x1400080ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400080ef  test    al, al
0x1400080f1  jnz     loc_140008210
0x1400080f7  xor     r15d, r15d
0x1400080fa  lea     edx, [r15+10h]; unsigned __int64
0x1400080fe  lea     rcx, [rdi+20h]; this
0x140008102  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140008107  test    al, al
0x140008109  jz      short loc_140008163
0x14000810b  mov     rcx, [rdi+28h]; void *
0x14000810f  mov     rax, [rdi+30h]
0x140008113  sub     rax, rcx
0x140008116  cmp     rcx, [rdi+30h]
0x14000811a  sbb     r8, r8
0x14000811d  and     r8, rax; Size
0x140008120  test    rcx, rcx
0x140008123  jnz     short loc_140008133
0x140008125  call    cs:__imp__o__errno
0x14000812b  mov     dword ptr [rax], 16h
0x140008131  jmp     short loc_140008159
0x140008133  cmp     r8, 10h
0x140008137  jb      short loc_140008146
0x140008139  mov     [rcx], r14d
0x14000813c  mov     [rcx+4], r15d
0x140008140  mov     [rcx+8], rbp
0x140008144  jmp     short loc_14000815E
0x140008146  xor     edx, edx; Val
0x140008148  call    memset_0
0x14000814d  call    cs:__imp__o__errno
0x140008153  mov     dword ptr [rax], 22h ; '"'
0x140008159  call    _invalid_parameter_noinfo
0x14000815e  add     qword ptr [rdi+28h], 10h
0x140008163  cmp     [rdi+18h], r15b
0x140008167  jnz     loc_140008210
0x14000816d  cmp     [rdi+10h], r15
0x140008171  jnz     short loc_1400081E0
0x140008173  call    cs:__imp_GetLastError
0x140008179  mov     r14d, eax
0x14000817c  xor     r8d, r8d; pcbe
0x14000817f  mov     rdx, rdi; pv
0x140008182  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140008189  call    cs:__imp_CreateThreadpoolTimer
0x14000818f  mov     r15, rax
0x140008192  mov     rbp, [rdi+10h]
0x140008196  test    rbp, rbp
0x140008199  jz      short loc_1400081D3
0x14000819b  call    cs:__imp_GetLastError
0x1400081a1  mov     ebx, eax
0x1400081a3  xor     r9d, r9d; msWindowLength
0x1400081a6  xor     r8d, r8d; msPeriod
0x1400081a9  xor     edx, edx; pftDueTime
0x1400081ab  mov     rcx, rbp; pti
0x1400081ae  call    cs:__imp_SetThreadpoolTimer
0x1400081b4  mov     edx, 1; fCancelPendingCallbacks
0x1400081b9  mov     rcx, rbp; pti
0x1400081bc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400081c2  mov     rcx, rbp; pti
0x1400081c5  call    cs:__imp_CloseThreadpoolTimer
0x1400081cb  mov     ecx, ebx; dwErrCode
0x1400081cd  call    cs:__imp_SetLastError
0x1400081d3  mov     [rdi+10h], r15
0x1400081d7  mov     ecx, r14d; dwErrCode
0x1400081da  call    cs:__imp_SetLastError
0x1400081e0  mov     rcx, [rdi+10h]; pti
0x1400081e4  test    rcx, rcx
0x1400081e7  jz      short loc_140008210
0x1400081e9  mov     rax, 0FFFFFFFF4D2FA200h
0x1400081f3  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x1400081f8  mov     r9d, 124F8h; msWindowLength
0x1400081fe  xor     r8d, r8d; msPeriod
0x140008201  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x140008206  call    cs:__imp_SetThreadpoolTimer
0x14000820c  mov     byte ptr [rdi+18h], 1
0x140008210  test    rsi, rsi
0x140008213  jz      short loc_14000821F
0x140008215  mov     rcx, rsi; SRWLock
0x140008218  call    cs:__imp_ReleaseSRWLockExclusive
0x14000821e  nop
0x14000821f  add     rsp, 28h
0x140008223  pop     r15
0x140008225  pop     r14
0x140008227  pop     rdi
0x140008228  pop     rsi
0x140008229  pop     rbp
0x14000822a  pop     rbx
0x14000822b  retn
```
