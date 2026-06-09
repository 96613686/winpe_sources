# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18001c074`
- end: `0x18001c22c`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001c6ec`

## callees

- `0x180005306`
- `0x180005374`
- `0x1800122d4`
- `0x18001c074`
- `0x18002e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001c125`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001c14d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001c125`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001c14d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c218`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c218`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c0c1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c0c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c173`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c19b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c173`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c19b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c1cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c1da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c1cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c1da`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001c189`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001c189`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001c1bc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001c1bc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001c1c5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001c1c5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c1ae`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c206`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c1ae`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c206`

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
0x18001c074  push    rbx
0x18001c076  push    rbp
0x18001c077  push    rsi
0x18001c078  push    rdi
0x18001c079  push    r14
0x18001c07b  push    r15
0x18001c07d  sub     rsp, 28h
0x18001c081  mov     rbp, r8
0x18001c084  mov     r14d, edx
0x18001c087  mov     rdi, rcx
0x18001c08a  mov     eax, [rcx]
0x18001c08c  test    eax, eax
0x18001c08e  jz      loc_18001C21F
0x18001c094  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001c09b  jnz     loc_18001C21F
0x18001c0a1  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001c0a8  test    rax, rax
0x18001c0ab  jz      short loc_18001C0BA
0x18001c0ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0b2  test    al, al
0x18001c0b4  jnz     loc_18001C21F
0x18001c0ba  lea     rsi, [rdi+8]
0x18001c0be  mov     rcx, rsi; SRWLock
0x18001c0c1  call    cs:__imp_AcquireSRWLockExclusive
0x18001c0c7  mov     eax, [rdi]
0x18001c0c9  test    eax, eax
0x18001c0cb  jz      loc_18001C210
0x18001c0d1  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001c0d8  jnz     loc_18001C210
0x18001c0de  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001c0e5  test    rax, rax
0x18001c0e8  jz      short loc_18001C0F7
0x18001c0ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0ef  test    al, al
0x18001c0f1  jnz     loc_18001C210
0x18001c0f7  xor     r15d, r15d
0x18001c0fa  lea     edx, [r15+10h]; unsigned __int64
0x18001c0fe  lea     rcx, [rdi+20h]; this
0x18001c102  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001c107  test    al, al
0x18001c109  jz      short loc_18001C163
0x18001c10b  mov     rcx, [rdi+28h]; void *
0x18001c10f  mov     rax, [rdi+30h]
0x18001c113  sub     rax, rcx
0x18001c116  cmp     rcx, [rdi+30h]
0x18001c11a  sbb     r8, r8
0x18001c11d  and     r8, rax; Size
0x18001c120  test    rcx, rcx
0x18001c123  jnz     short loc_18001C133
0x18001c125  call    cs:__imp__o__errno
0x18001c12b  mov     dword ptr [rax], 16h
0x18001c131  jmp     short loc_18001C159
0x18001c133  cmp     r8, 10h
0x18001c137  jb      short loc_18001C146
0x18001c139  mov     [rcx], r14d
0x18001c13c  mov     [rcx+4], r15d
0x18001c140  mov     [rcx+8], rbp
0x18001c144  jmp     short loc_18001C15E
0x18001c146  xor     edx, edx; Val
0x18001c148  call    memset_0
0x18001c14d  call    cs:__imp__o__errno
0x18001c153  mov     dword ptr [rax], 22h ; '"'
0x18001c159  call    _invalid_parameter_noinfo
0x18001c15e  add     qword ptr [rdi+28h], 10h
0x18001c163  cmp     [rdi+18h], r15b
0x18001c167  jnz     loc_18001C210
0x18001c16d  cmp     [rdi+10h], r15
0x18001c171  jnz     short loc_18001C1E0
0x18001c173  call    cs:__imp_GetLastError
0x18001c179  mov     r14d, eax
0x18001c17c  xor     r8d, r8d; pcbe
0x18001c17f  mov     rdx, rdi; pv
0x18001c182  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001c189  call    cs:__imp_CreateThreadpoolTimer
0x18001c18f  mov     r15, rax
0x18001c192  mov     rbp, [rdi+10h]
0x18001c196  test    rbp, rbp
0x18001c199  jz      short loc_18001C1D3
0x18001c19b  call    cs:__imp_GetLastError
0x18001c1a1  mov     ebx, eax
0x18001c1a3  xor     r9d, r9d; msWindowLength
0x18001c1a6  xor     r8d, r8d; msPeriod
0x18001c1a9  xor     edx, edx; pftDueTime
0x18001c1ab  mov     rcx, rbp; pti
0x18001c1ae  call    cs:__imp_SetThreadpoolTimer
0x18001c1b4  mov     edx, 1; fCancelPendingCallbacks
0x18001c1b9  mov     rcx, rbp; pti
0x18001c1bc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001c1c2  mov     rcx, rbp; pti
0x18001c1c5  call    cs:__imp_CloseThreadpoolTimer
0x18001c1cb  mov     ecx, ebx; dwErrCode
0x18001c1cd  call    cs:__imp_SetLastError
0x18001c1d3  mov     [rdi+10h], r15
0x18001c1d7  mov     ecx, r14d; dwErrCode
0x18001c1da  call    cs:__imp_SetLastError
0x18001c1e0  mov     rcx, [rdi+10h]; pti
0x18001c1e4  test    rcx, rcx
0x18001c1e7  jz      short loc_18001C210
0x18001c1e9  mov     rax, 0FFFFFFFF4D2FA200h
0x18001c1f3  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18001c1f8  mov     r9d, 124F8h; msWindowLength
0x18001c1fe  xor     r8d, r8d; msPeriod
0x18001c201  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18001c206  call    cs:__imp_SetThreadpoolTimer
0x18001c20c  mov     byte ptr [rdi+18h], 1
0x18001c210  test    rsi, rsi
0x18001c213  jz      short loc_18001C21F
0x18001c215  mov     rcx, rsi; SRWLock
0x18001c218  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c21e  nop
0x18001c21f  add     rsp, 28h
0x18001c223  pop     r15
0x18001c225  pop     r14
0x18001c227  pop     rdi
0x18001c228  pop     rsi
0x18001c229  pop     rbp
0x18001c22a  pop     rbx
0x18001c22b  retn
```
