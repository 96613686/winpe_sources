# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000f830`
- end: `0x18000f9e8`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000fb28`

## callees

- `0x180002432`
- `0x1800024ac`
- `0x18000959c`
- `0x18000f830`
- `0x180037010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f8e1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f909`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f8e1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f909`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f9d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f9d4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f87d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f87d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f92f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f957`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f92f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f957`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f989`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f996`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f989`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f996`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f96a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f9c2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f96a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f9c2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000f945`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000f945`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f981`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f981`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f978`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f978`

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
0x18000f830  push    rbx
0x18000f832  push    rbp
0x18000f833  push    rsi
0x18000f834  push    rdi
0x18000f835  push    r14
0x18000f837  push    r15
0x18000f839  sub     rsp, 28h
0x18000f83d  mov     rbp, r8
0x18000f840  mov     r14d, edx
0x18000f843  mov     rdi, rcx
0x18000f846  mov     eax, [rcx]
0x18000f848  test    eax, eax
0x18000f84a  jz      loc_18000F9DB
0x18000f850  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000f857  jnz     loc_18000F9DB
0x18000f85d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000f864  test    rax, rax
0x18000f867  jz      short loc_18000F876
0x18000f869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f86e  test    al, al
0x18000f870  jnz     loc_18000F9DB
0x18000f876  lea     rsi, [rdi+8]
0x18000f87a  mov     rcx, rsi; SRWLock
0x18000f87d  call    cs:__imp_AcquireSRWLockExclusive
0x18000f883  mov     eax, [rdi]
0x18000f885  test    eax, eax
0x18000f887  jz      loc_18000F9CC
0x18000f88d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000f894  jnz     loc_18000F9CC
0x18000f89a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000f8a1  test    rax, rax
0x18000f8a4  jz      short loc_18000F8B3
0x18000f8a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8ab  test    al, al
0x18000f8ad  jnz     loc_18000F9CC
0x18000f8b3  xor     r15d, r15d
0x18000f8b6  lea     edx, [r15+10h]; unsigned __int64
0x18000f8ba  lea     rcx, [rdi+20h]; this
0x18000f8be  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000f8c3  test    al, al
0x18000f8c5  jz      short loc_18000F91F
0x18000f8c7  mov     rcx, [rdi+28h]; void *
0x18000f8cb  mov     rax, [rdi+30h]
0x18000f8cf  sub     rax, rcx
0x18000f8d2  cmp     rcx, [rdi+30h]
0x18000f8d6  sbb     r8, r8
0x18000f8d9  and     r8, rax; Size
0x18000f8dc  test    rcx, rcx
0x18000f8df  jnz     short loc_18000F8EF
0x18000f8e1  call    cs:__imp__o__errno
0x18000f8e7  mov     dword ptr [rax], 16h
0x18000f8ed  jmp     short loc_18000F915
0x18000f8ef  cmp     r8, 10h
0x18000f8f3  jb      short loc_18000F902
0x18000f8f5  mov     [rcx], r14d
0x18000f8f8  mov     [rcx+4], r15d
0x18000f8fc  mov     [rcx+8], rbp
0x18000f900  jmp     short loc_18000F91A
0x18000f902  xor     edx, edx; Val
0x18000f904  call    memset_0
0x18000f909  call    cs:__imp__o__errno
0x18000f90f  mov     dword ptr [rax], 22h ; '"'
0x18000f915  call    _invalid_parameter_noinfo
0x18000f91a  add     qword ptr [rdi+28h], 10h
0x18000f91f  cmp     [rdi+18h], r15b
0x18000f923  jnz     loc_18000F9CC
0x18000f929  cmp     [rdi+10h], r15
0x18000f92d  jnz     short loc_18000F99C
0x18000f92f  call    cs:__imp_GetLastError
0x18000f935  mov     r14d, eax
0x18000f938  xor     r8d, r8d; pcbe
0x18000f93b  mov     rdx, rdi; pv
0x18000f93e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000f945  call    cs:__imp_CreateThreadpoolTimer
0x18000f94b  mov     r15, rax
0x18000f94e  mov     rbp, [rdi+10h]
0x18000f952  test    rbp, rbp
0x18000f955  jz      short loc_18000F98F
0x18000f957  call    cs:__imp_GetLastError
0x18000f95d  mov     ebx, eax
0x18000f95f  xor     r9d, r9d; msWindowLength
0x18000f962  xor     r8d, r8d; msPeriod
0x18000f965  xor     edx, edx; pftDueTime
0x18000f967  mov     rcx, rbp; pti
0x18000f96a  call    cs:__imp_SetThreadpoolTimer
0x18000f970  mov     edx, 1; fCancelPendingCallbacks
0x18000f975  mov     rcx, rbp; pti
0x18000f978  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000f97e  mov     rcx, rbp; pti
0x18000f981  call    cs:__imp_CloseThreadpoolTimer
0x18000f987  mov     ecx, ebx; dwErrCode
0x18000f989  call    cs:__imp_SetLastError
0x18000f98f  mov     [rdi+10h], r15
0x18000f993  mov     ecx, r14d; dwErrCode
0x18000f996  call    cs:__imp_SetLastError
0x18000f99c  mov     rcx, [rdi+10h]; pti
0x18000f9a0  test    rcx, rcx
0x18000f9a3  jz      short loc_18000F9CC
0x18000f9a5  mov     rax, 0FFFFFFFF4D2FA200h
0x18000f9af  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18000f9b4  mov     r9d, 124F8h; msWindowLength
0x18000f9ba  xor     r8d, r8d; msPeriod
0x18000f9bd  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18000f9c2  call    cs:__imp_SetThreadpoolTimer
0x18000f9c8  mov     byte ptr [rdi+18h], 1
0x18000f9cc  test    rsi, rsi
0x18000f9cf  jz      short loc_18000F9DB
0x18000f9d1  mov     rcx, rsi; SRWLock
0x18000f9d4  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f9da  nop
0x18000f9db  add     rsp, 28h
0x18000f9df  pop     r15
0x18000f9e1  pop     r14
0x18000f9e3  pop     rdi
0x18000f9e4  pop     rsi
0x18000f9e5  pop     rbp
0x18000f9e6  pop     rbx
0x18000f9e7  retn
```
