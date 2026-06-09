# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18001c27c`
- end: `0x18001c434`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001c5d8`

## callees

- `0x180003392`
- `0x1800033e8`
- `0x18000fcc0`
- `0x18001c27c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001c32d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001c355`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001c32d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001c355`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c2c9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c2c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c420`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c420`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c3d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c3e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c3d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c3e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c37b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c3a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c37b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c3a3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c3b6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c40e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c3b6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c40e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001c3cd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001c3cd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001c391`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001c391`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001c3c4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001c3c4`

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
0x18001c27c  push    rbx
0x18001c27e  push    rbp
0x18001c27f  push    rsi
0x18001c280  push    rdi
0x18001c281  push    r14
0x18001c283  push    r15
0x18001c285  sub     rsp, 28h
0x18001c289  mov     rbp, r8
0x18001c28c  mov     r14d, edx
0x18001c28f  mov     rdi, rcx
0x18001c292  mov     eax, [rcx]
0x18001c294  test    eax, eax
0x18001c296  jz      loc_18001C427
0x18001c29c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001c2a3  jnz     loc_18001C427
0x18001c2a9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001c2b0  test    rax, rax
0x18001c2b3  jz      short loc_18001C2C2
0x18001c2b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2ba  test    al, al
0x18001c2bc  jnz     loc_18001C427
0x18001c2c2  lea     rsi, [rdi+8]
0x18001c2c6  mov     rcx, rsi; SRWLock
0x18001c2c9  call    cs:__imp_AcquireSRWLockExclusive
0x18001c2cf  mov     eax, [rdi]
0x18001c2d1  test    eax, eax
0x18001c2d3  jz      loc_18001C418
0x18001c2d9  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001c2e0  jnz     loc_18001C418
0x18001c2e6  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001c2ed  test    rax, rax
0x18001c2f0  jz      short loc_18001C2FF
0x18001c2f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2f7  test    al, al
0x18001c2f9  jnz     loc_18001C418
0x18001c2ff  xor     r15d, r15d
0x18001c302  lea     edx, [r15+10h]; unsigned __int64
0x18001c306  lea     rcx, [rdi+20h]; this
0x18001c30a  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001c30f  test    al, al
0x18001c311  jz      short loc_18001C36B
0x18001c313  mov     rcx, [rdi+28h]; void *
0x18001c317  mov     rax, [rdi+30h]
0x18001c31b  sub     rax, rcx
0x18001c31e  cmp     rcx, [rdi+30h]
0x18001c322  sbb     r8, r8
0x18001c325  and     r8, rax; Size
0x18001c328  test    rcx, rcx
0x18001c32b  jnz     short loc_18001C33B
0x18001c32d  call    cs:__imp__o__errno
0x18001c333  mov     dword ptr [rax], 16h
0x18001c339  jmp     short loc_18001C361
0x18001c33b  cmp     r8, 10h
0x18001c33f  jb      short loc_18001C34E
0x18001c341  mov     [rcx], r14d
0x18001c344  mov     [rcx+4], r15d
0x18001c348  mov     [rcx+8], rbp
0x18001c34c  jmp     short loc_18001C366
0x18001c34e  xor     edx, edx; Val
0x18001c350  call    memset_0
0x18001c355  call    cs:__imp__o__errno
0x18001c35b  mov     dword ptr [rax], 22h ; '"'
0x18001c361  call    _invalid_parameter_noinfo
0x18001c366  add     qword ptr [rdi+28h], 10h
0x18001c36b  cmp     [rdi+18h], r15b
0x18001c36f  jnz     loc_18001C418
0x18001c375  cmp     [rdi+10h], r15
0x18001c379  jnz     short loc_18001C3E8
0x18001c37b  call    cs:__imp_GetLastError
0x18001c381  mov     r14d, eax
0x18001c384  xor     r8d, r8d; pcbe
0x18001c387  mov     rdx, rdi; pv
0x18001c38a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001c391  call    cs:__imp_CreateThreadpoolTimer
0x18001c397  mov     r15, rax
0x18001c39a  mov     rbp, [rdi+10h]
0x18001c39e  test    rbp, rbp
0x18001c3a1  jz      short loc_18001C3DB
0x18001c3a3  call    cs:__imp_GetLastError
0x18001c3a9  mov     ebx, eax
0x18001c3ab  xor     r9d, r9d; msWindowLength
0x18001c3ae  xor     r8d, r8d; msPeriod
0x18001c3b1  xor     edx, edx; pftDueTime
0x18001c3b3  mov     rcx, rbp; pti
0x18001c3b6  call    cs:__imp_SetThreadpoolTimer
0x18001c3bc  mov     edx, 1; fCancelPendingCallbacks
0x18001c3c1  mov     rcx, rbp; pti
0x18001c3c4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001c3ca  mov     rcx, rbp; pti
0x18001c3cd  call    cs:__imp_CloseThreadpoolTimer
0x18001c3d3  mov     ecx, ebx; dwErrCode
0x18001c3d5  call    cs:__imp_SetLastError
0x18001c3db  mov     [rdi+10h], r15
0x18001c3df  mov     ecx, r14d; dwErrCode
0x18001c3e2  call    cs:__imp_SetLastError
0x18001c3e8  mov     rcx, [rdi+10h]; pti
0x18001c3ec  test    rcx, rcx
0x18001c3ef  jz      short loc_18001C418
0x18001c3f1  mov     rax, 0FFFFFFFF4D2FA200h
0x18001c3fb  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18001c400  mov     r9d, 124F8h; msWindowLength
0x18001c406  xor     r8d, r8d; msPeriod
0x18001c409  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18001c40e  call    cs:__imp_SetThreadpoolTimer
0x18001c414  mov     byte ptr [rdi+18h], 1
0x18001c418  test    rsi, rsi
0x18001c41b  jz      short loc_18001C427
0x18001c41d  mov     rcx, rsi; SRWLock
0x18001c420  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c426  nop
0x18001c427  add     rsp, 28h
0x18001c42b  pop     r15
0x18001c42d  pop     r14
0x18001c42f  pop     rdi
0x18001c430  pop     rsi
0x18001c431  pop     rbp
0x18001c432  pop     rbx
0x18001c433  retn
```
