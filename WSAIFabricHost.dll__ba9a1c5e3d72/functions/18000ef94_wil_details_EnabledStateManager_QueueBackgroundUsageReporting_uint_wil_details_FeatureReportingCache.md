# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000ef94`
- end: `0x18000f14c`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800103fc`

## callees

- `0x1800056d2`
- `0x180005758`
- `0x18000ef94`
- `0x1800111dc`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f045`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f06d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f045`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f06d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000efe1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000efe1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f138`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f138`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f093`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f0bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f093`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f0bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f0ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f0fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f0ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f0fa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f0dc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f0dc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f0e5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f0e5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000f0a9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000f0a9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f0ce`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f126`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f0ce`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f126`

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
0x18000ef94  push    rbx
0x18000ef96  push    rbp
0x18000ef97  push    rsi
0x18000ef98  push    rdi
0x18000ef99  push    r14
0x18000ef9b  push    r15
0x18000ef9d  sub     rsp, 28h
0x18000efa1  mov     rbp, r8
0x18000efa4  mov     r14d, edx
0x18000efa7  mov     rdi, rcx
0x18000efaa  mov     eax, [rcx]
0x18000efac  test    eax, eax
0x18000efae  jz      loc_18000F13F
0x18000efb4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000efbb  jnz     loc_18000F13F
0x18000efc1  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000efc8  test    rax, rax
0x18000efcb  jz      short loc_18000EFDA
0x18000efcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efd2  test    al, al
0x18000efd4  jnz     loc_18000F13F
0x18000efda  lea     rsi, [rdi+8]
0x18000efde  mov     rcx, rsi; SRWLock
0x18000efe1  call    cs:__imp_AcquireSRWLockExclusive
0x18000efe7  mov     eax, [rdi]
0x18000efe9  test    eax, eax
0x18000efeb  jz      loc_18000F130
0x18000eff1  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000eff8  jnz     loc_18000F130
0x18000effe  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000f005  test    rax, rax
0x18000f008  jz      short loc_18000F017
0x18000f00a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f00f  test    al, al
0x18000f011  jnz     loc_18000F130
0x18000f017  xor     r15d, r15d
0x18000f01a  lea     edx, [r15+10h]; unsigned __int64
0x18000f01e  lea     rcx, [rdi+20h]; this
0x18000f022  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000f027  test    al, al
0x18000f029  jz      short loc_18000F083
0x18000f02b  mov     rcx, [rdi+28h]; void *
0x18000f02f  mov     rax, [rdi+30h]
0x18000f033  sub     rax, rcx
0x18000f036  cmp     rcx, [rdi+30h]
0x18000f03a  sbb     r8, r8
0x18000f03d  and     r8, rax; Size
0x18000f040  test    rcx, rcx
0x18000f043  jnz     short loc_18000F053
0x18000f045  call    cs:__imp__o__errno
0x18000f04b  mov     dword ptr [rax], 16h
0x18000f051  jmp     short loc_18000F079
0x18000f053  cmp     r8, 10h
0x18000f057  jb      short loc_18000F066
0x18000f059  mov     [rcx], r14d
0x18000f05c  mov     [rcx+4], r15d
0x18000f060  mov     [rcx+8], rbp
0x18000f064  jmp     short loc_18000F07E
0x18000f066  xor     edx, edx; Val
0x18000f068  call    memset_0
0x18000f06d  call    cs:__imp__o__errno
0x18000f073  mov     dword ptr [rax], 22h ; '"'
0x18000f079  call    _invalid_parameter_noinfo
0x18000f07e  add     qword ptr [rdi+28h], 10h
0x18000f083  cmp     [rdi+18h], r15b
0x18000f087  jnz     loc_18000F130
0x18000f08d  cmp     [rdi+10h], r15
0x18000f091  jnz     short loc_18000F100
0x18000f093  call    cs:__imp_GetLastError
0x18000f099  mov     r14d, eax
0x18000f09c  xor     r8d, r8d; pcbe
0x18000f09f  mov     rdx, rdi; pv
0x18000f0a2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000f0a9  call    cs:__imp_CreateThreadpoolTimer
0x18000f0af  mov     r15, rax
0x18000f0b2  mov     rbp, [rdi+10h]
0x18000f0b6  test    rbp, rbp
0x18000f0b9  jz      short loc_18000F0F3
0x18000f0bb  call    cs:__imp_GetLastError
0x18000f0c1  mov     ebx, eax
0x18000f0c3  xor     r9d, r9d; msWindowLength
0x18000f0c6  xor     r8d, r8d; msPeriod
0x18000f0c9  xor     edx, edx; pftDueTime
0x18000f0cb  mov     rcx, rbp; pti
0x18000f0ce  call    cs:__imp_SetThreadpoolTimer
0x18000f0d4  mov     edx, 1; fCancelPendingCallbacks
0x18000f0d9  mov     rcx, rbp; pti
0x18000f0dc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000f0e2  mov     rcx, rbp; pti
0x18000f0e5  call    cs:__imp_CloseThreadpoolTimer
0x18000f0eb  mov     ecx, ebx; dwErrCode
0x18000f0ed  call    cs:__imp_SetLastError
0x18000f0f3  mov     [rdi+10h], r15
0x18000f0f7  mov     ecx, r14d; dwErrCode
0x18000f0fa  call    cs:__imp_SetLastError
0x18000f100  mov     rcx, [rdi+10h]; pti
0x18000f104  test    rcx, rcx
0x18000f107  jz      short loc_18000F130
0x18000f109  mov     rax, 0FFFFFFFF4D2FA200h
0x18000f113  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18000f118  mov     r9d, 124F8h; msWindowLength
0x18000f11e  xor     r8d, r8d; msPeriod
0x18000f121  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18000f126  call    cs:__imp_SetThreadpoolTimer
0x18000f12c  mov     byte ptr [rdi+18h], 1
0x18000f130  test    rsi, rsi
0x18000f133  jz      short loc_18000F13F
0x18000f135  mov     rcx, rsi; SRWLock
0x18000f138  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f13e  nop
0x18000f13f  add     rsp, 28h
0x18000f143  pop     r15
0x18000f145  pop     r14
0x18000f147  pop     rdi
0x18000f148  pop     rsi
0x18000f149  pop     rbp
0x18000f14a  pop     rbx
0x18000f14b  retn
```
