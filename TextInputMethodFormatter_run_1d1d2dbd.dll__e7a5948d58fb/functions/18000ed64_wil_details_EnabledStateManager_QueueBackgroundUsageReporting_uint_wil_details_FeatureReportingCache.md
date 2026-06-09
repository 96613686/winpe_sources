# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000ed64`
- end: `0x18000ef1d`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `441`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180010678`

## callees

- `0x180002db8`
- `0x18000ed64`
- `0x18001268c`
- `0x180058010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x18000ee49`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x18000ee49`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ee15`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ee3d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ee15`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ee3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ef09`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ef09`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000edb1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000edb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eebe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eecb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eebe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eecb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ee7a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ee7a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ee9f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000eef7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ee9f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000eef7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000eeb6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000eeb6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000eead`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000eead`

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
    _invalid_parameter_noinfo();
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x18000ed64  push    rbx
0x18000ed66  push    rbp
0x18000ed67  push    rsi
0x18000ed68  push    rdi
0x18000ed69  push    r14
0x18000ed6b  push    r15
0x18000ed6d  sub     rsp, 28h
0x18000ed71  mov     rbp, r8
0x18000ed74  mov     r14d, edx
0x18000ed77  mov     rdi, rcx
0x18000ed7a  mov     eax, [rcx]
0x18000ed7c  test    eax, eax
0x18000ed7e  jz      loc_18000EF10
0x18000ed84  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000ed8b  jnz     loc_18000EF10
0x18000ed91  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ed98  test    rax, rax
0x18000ed9b  jz      short loc_18000EDAA
0x18000ed9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eda2  test    al, al
0x18000eda4  jnz     loc_18000EF10
0x18000edaa  lea     rsi, [rdi+8]
0x18000edae  mov     rcx, rsi; SRWLock
0x18000edb1  call    cs:__imp_AcquireSRWLockExclusive
0x18000edb7  mov     eax, [rdi]
0x18000edb9  test    eax, eax
0x18000edbb  jz      loc_18000EF01
0x18000edc1  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000edc8  jnz     loc_18000EF01
0x18000edce  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000edd5  test    rax, rax
0x18000edd8  jz      short loc_18000EDE7
0x18000edda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eddf  test    al, al
0x18000ede1  jnz     loc_18000EF01
0x18000ede7  xor     r15d, r15d
0x18000edea  lea     edx, [r15+10h]; unsigned __int64
0x18000edee  lea     rcx, [rdi+20h]; this
0x18000edf2  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000edf7  test    al, al
0x18000edf9  jz      short loc_18000EE54
0x18000edfb  mov     rcx, [rdi+28h]; void *
0x18000edff  mov     rax, [rdi+30h]
0x18000ee03  sub     rax, rcx
0x18000ee06  cmp     rcx, [rdi+30h]
0x18000ee0a  sbb     r8, r8
0x18000ee0d  and     r8, rax; Size
0x18000ee10  test    rcx, rcx
0x18000ee13  jnz     short loc_18000EE23
0x18000ee15  call    cs:__imp__o__errno
0x18000ee1b  mov     dword ptr [rax], 16h
0x18000ee21  jmp     short loc_18000EE49
0x18000ee23  cmp     r8, 10h
0x18000ee27  jb      short loc_18000EE36
0x18000ee29  mov     [rcx], r14d
0x18000ee2c  mov     [rcx+4], r15d
0x18000ee30  mov     [rcx+8], rbp
0x18000ee34  jmp     short loc_18000EE4F
0x18000ee36  xor     edx, edx; Val
0x18000ee38  call    memset_0
0x18000ee3d  call    cs:__imp__o__errno
0x18000ee43  mov     dword ptr [rax], 22h ; '"'
0x18000ee49  call    cs:__imp__invalid_parameter_noinfo
0x18000ee4f  add     qword ptr [rdi+28h], 10h
0x18000ee54  cmp     [rdi+18h], r15b
0x18000ee58  jnz     loc_18000EF01
0x18000ee5e  cmp     [rdi+10h], r15
0x18000ee62  jnz     short loc_18000EED1
0x18000ee64  call    cs:__imp_GetLastError
0x18000ee6a  mov     r14d, eax
0x18000ee6d  xor     r8d, r8d; pcbe
0x18000ee70  mov     rdx, rdi; pv
0x18000ee73  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000ee7a  call    cs:__imp_CreateThreadpoolTimer
0x18000ee80  mov     r15, rax
0x18000ee83  mov     rbp, [rdi+10h]
0x18000ee87  test    rbp, rbp
0x18000ee8a  jz      short loc_18000EEC4
0x18000ee8c  call    cs:__imp_GetLastError
0x18000ee92  mov     ebx, eax
0x18000ee94  xor     r9d, r9d; msWindowLength
0x18000ee97  xor     r8d, r8d; msPeriod
0x18000ee9a  xor     edx, edx; pftDueTime
0x18000ee9c  mov     rcx, rbp; pti
0x18000ee9f  call    cs:__imp_SetThreadpoolTimer
0x18000eea5  mov     edx, 1; fCancelPendingCallbacks
0x18000eeaa  mov     rcx, rbp; pti
0x18000eead  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000eeb3  mov     rcx, rbp; pti
0x18000eeb6  call    cs:__imp_CloseThreadpoolTimer
0x18000eebc  mov     ecx, ebx; dwErrCode
0x18000eebe  call    cs:__imp_SetLastError
0x18000eec4  mov     [rdi+10h], r15
0x18000eec8  mov     ecx, r14d; dwErrCode
0x18000eecb  call    cs:__imp_SetLastError
0x18000eed1  mov     rcx, [rdi+10h]; pti
0x18000eed5  test    rcx, rcx
0x18000eed8  jz      short loc_18000EF01
0x18000eeda  mov     rax, 0FFFFFFFF4D2FA200h
0x18000eee4  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18000eee9  mov     r9d, 124F8h; msWindowLength
0x18000eeef  xor     r8d, r8d; msPeriod
0x18000eef2  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18000eef7  call    cs:__imp_SetThreadpoolTimer
0x18000eefd  mov     byte ptr [rdi+18h], 1
0x18000ef01  test    rsi, rsi
0x18000ef04  jz      short loc_18000EF10
0x18000ef06  mov     rcx, rsi; SRWLock
0x18000ef09  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ef0f  nop
0x18000ef10  add     rsp, 28h
0x18000ef14  pop     r15
0x18000ef16  pop     r14
0x18000ef18  pop     rdi
0x18000ef19  pop     rsi
0x18000ef1a  pop     rbp
0x18000ef1b  pop     rbx
0x18000ef1c  retn
```
