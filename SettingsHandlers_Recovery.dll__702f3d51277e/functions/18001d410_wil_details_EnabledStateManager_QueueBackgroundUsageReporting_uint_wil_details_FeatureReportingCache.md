# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18001d410`
- end: `0x18001d5c8`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001ea10`

## callees

- `0x180002e3a`
- `0x180002ed4`
- `0x18000a5e0`
- `0x18001d410`
- `0x18002b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d4c1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d4e9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d4c1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d4e9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d45d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d45d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d5b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d5b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d569`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d576`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d569`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d576`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d50f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d537`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d50f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d537`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001d561`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001d561`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d525`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d525`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d54a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d5a2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d54a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d5a2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001d558`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001d558`

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
0x18001d410  push    rbx
0x18001d412  push    rbp
0x18001d413  push    rsi
0x18001d414  push    rdi
0x18001d415  push    r14
0x18001d417  push    r15
0x18001d419  sub     rsp, 28h
0x18001d41d  mov     rbp, r8
0x18001d420  mov     r14d, edx
0x18001d423  mov     rdi, rcx
0x18001d426  mov     eax, [rcx]
0x18001d428  test    eax, eax
0x18001d42a  jz      loc_18001D5BB
0x18001d430  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001d437  jnz     loc_18001D5BB
0x18001d43d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001d444  test    rax, rax
0x18001d447  jz      short loc_18001D456
0x18001d449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d44e  test    al, al
0x18001d450  jnz     loc_18001D5BB
0x18001d456  lea     rsi, [rdi+8]
0x18001d45a  mov     rcx, rsi; SRWLock
0x18001d45d  call    cs:__imp_AcquireSRWLockExclusive
0x18001d463  mov     eax, [rdi]
0x18001d465  test    eax, eax
0x18001d467  jz      loc_18001D5AC
0x18001d46d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001d474  jnz     loc_18001D5AC
0x18001d47a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001d481  test    rax, rax
0x18001d484  jz      short loc_18001D493
0x18001d486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d48b  test    al, al
0x18001d48d  jnz     loc_18001D5AC
0x18001d493  xor     r15d, r15d
0x18001d496  lea     edx, [r15+10h]; unsigned __int64
0x18001d49a  lea     rcx, [rdi+20h]; this
0x18001d49e  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001d4a3  test    al, al
0x18001d4a5  jz      short loc_18001D4FF
0x18001d4a7  mov     rcx, [rdi+28h]; void *
0x18001d4ab  mov     rax, [rdi+30h]
0x18001d4af  sub     rax, rcx
0x18001d4b2  cmp     rcx, [rdi+30h]
0x18001d4b6  sbb     r8, r8
0x18001d4b9  and     r8, rax; Size
0x18001d4bc  test    rcx, rcx
0x18001d4bf  jnz     short loc_18001D4CF
0x18001d4c1  call    cs:__imp__o__errno
0x18001d4c7  mov     dword ptr [rax], 16h
0x18001d4cd  jmp     short loc_18001D4F5
0x18001d4cf  cmp     r8, 10h
0x18001d4d3  jb      short loc_18001D4E2
0x18001d4d5  mov     [rcx], r14d
0x18001d4d8  mov     [rcx+4], r15d
0x18001d4dc  mov     [rcx+8], rbp
0x18001d4e0  jmp     short loc_18001D4FA
0x18001d4e2  xor     edx, edx; Val
0x18001d4e4  call    memset_0
0x18001d4e9  call    cs:__imp__o__errno
0x18001d4ef  mov     dword ptr [rax], 22h ; '"'
0x18001d4f5  call    _invalid_parameter_noinfo
0x18001d4fa  add     qword ptr [rdi+28h], 10h
0x18001d4ff  cmp     [rdi+18h], r15b
0x18001d503  jnz     loc_18001D5AC
0x18001d509  cmp     [rdi+10h], r15
0x18001d50d  jnz     short loc_18001D57C
0x18001d50f  call    cs:__imp_GetLastError
0x18001d515  mov     r14d, eax
0x18001d518  xor     r8d, r8d; pcbe
0x18001d51b  mov     rdx, rdi; pv
0x18001d51e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001d525  call    cs:__imp_CreateThreadpoolTimer
0x18001d52b  mov     r15, rax
0x18001d52e  mov     rbp, [rdi+10h]
0x18001d532  test    rbp, rbp
0x18001d535  jz      short loc_18001D56F
0x18001d537  call    cs:__imp_GetLastError
0x18001d53d  mov     ebx, eax
0x18001d53f  xor     r9d, r9d; msWindowLength
0x18001d542  xor     r8d, r8d; msPeriod
0x18001d545  xor     edx, edx; pftDueTime
0x18001d547  mov     rcx, rbp; pti
0x18001d54a  call    cs:__imp_SetThreadpoolTimer
0x18001d550  mov     edx, 1; fCancelPendingCallbacks
0x18001d555  mov     rcx, rbp; pti
0x18001d558  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001d55e  mov     rcx, rbp; pti
0x18001d561  call    cs:__imp_CloseThreadpoolTimer
0x18001d567  mov     ecx, ebx; dwErrCode
0x18001d569  call    cs:__imp_SetLastError
0x18001d56f  mov     [rdi+10h], r15
0x18001d573  mov     ecx, r14d; dwErrCode
0x18001d576  call    cs:__imp_SetLastError
0x18001d57c  mov     rcx, [rdi+10h]; pti
0x18001d580  test    rcx, rcx
0x18001d583  jz      short loc_18001D5AC
0x18001d585  mov     rax, 0FFFFFFFF4D2FA200h
0x18001d58f  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18001d594  mov     r9d, 124F8h; msWindowLength
0x18001d59a  xor     r8d, r8d; msPeriod
0x18001d59d  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18001d5a2  call    cs:__imp_SetThreadpoolTimer
0x18001d5a8  mov     byte ptr [rdi+18h], 1
0x18001d5ac  test    rsi, rsi
0x18001d5af  jz      short loc_18001D5BB
0x18001d5b1  mov     rcx, rsi; SRWLock
0x18001d5b4  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d5ba  nop
0x18001d5bb  add     rsp, 28h
0x18001d5bf  pop     r15
0x18001d5c1  pop     r14
0x18001d5c3  pop     rdi
0x18001d5c4  pop     rsi
0x18001d5c5  pop     rbp
0x18001d5c6  pop     rbx
0x18001d5c7  retn
```
