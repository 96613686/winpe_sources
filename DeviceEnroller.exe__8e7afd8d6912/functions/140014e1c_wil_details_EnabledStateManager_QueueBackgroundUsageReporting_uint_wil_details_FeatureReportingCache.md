# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x140014e1c`
- end: `0x140014fd4`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140017828`

## callees

- `0x140004d6e`
- `0x140004e28`
- `0x140014e1c`
- `0x14001d160`
- `0x14005d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014ecd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014ef5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014ecd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014ef5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014fc0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014fc0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014e69`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014e69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014f1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014f43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014f1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014f43`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140014f75`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140014f82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140014f75`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140014f82`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140014f31`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140014f31`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140014f6d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140014f6d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140014f56`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140014fae`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140014f56`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140014fae`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140014f64`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140014f64`

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
0x140014e1c  push    rbx
0x140014e1e  push    rbp
0x140014e1f  push    rsi
0x140014e20  push    rdi
0x140014e21  push    r14
0x140014e23  push    r15
0x140014e25  sub     rsp, 28h
0x140014e29  mov     rbp, r8
0x140014e2c  mov     r14d, edx
0x140014e2f  mov     rdi, rcx
0x140014e32  mov     eax, [rcx]
0x140014e34  test    eax, eax
0x140014e36  jz      loc_140014FC7
0x140014e3c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140014e43  jnz     loc_140014FC7
0x140014e49  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140014e50  test    rax, rax
0x140014e53  jz      short loc_140014E62
0x140014e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014e5a  test    al, al
0x140014e5c  jnz     loc_140014FC7
0x140014e62  lea     rsi, [rdi+8]
0x140014e66  mov     rcx, rsi; SRWLock
0x140014e69  call    cs:__imp_AcquireSRWLockExclusive
0x140014e6f  mov     eax, [rdi]
0x140014e71  test    eax, eax
0x140014e73  jz      loc_140014FB8
0x140014e79  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140014e80  jnz     loc_140014FB8
0x140014e86  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140014e8d  test    rax, rax
0x140014e90  jz      short loc_140014E9F
0x140014e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014e97  test    al, al
0x140014e99  jnz     loc_140014FB8
0x140014e9f  xor     r15d, r15d
0x140014ea2  lea     edx, [r15+10h]; unsigned __int64
0x140014ea6  lea     rcx, [rdi+20h]; this
0x140014eaa  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140014eaf  test    al, al
0x140014eb1  jz      short loc_140014F0B
0x140014eb3  mov     rcx, [rdi+28h]; void *
0x140014eb7  mov     rax, [rdi+30h]
0x140014ebb  sub     rax, rcx
0x140014ebe  cmp     rcx, [rdi+30h]
0x140014ec2  sbb     r8, r8
0x140014ec5  and     r8, rax; Size
0x140014ec8  test    rcx, rcx
0x140014ecb  jnz     short loc_140014EDB
0x140014ecd  call    cs:__imp__o__errno
0x140014ed3  mov     dword ptr [rax], 16h
0x140014ed9  jmp     short loc_140014F01
0x140014edb  cmp     r8, 10h
0x140014edf  jb      short loc_140014EEE
0x140014ee1  mov     [rcx], r14d
0x140014ee4  mov     [rcx+4], r15d
0x140014ee8  mov     [rcx+8], rbp
0x140014eec  jmp     short loc_140014F06
0x140014eee  xor     edx, edx; Val
0x140014ef0  call    memset_0
0x140014ef5  call    cs:__imp__o__errno
0x140014efb  mov     dword ptr [rax], 22h ; '"'
0x140014f01  call    _invalid_parameter_noinfo
0x140014f06  add     qword ptr [rdi+28h], 10h
0x140014f0b  cmp     [rdi+18h], r15b
0x140014f0f  jnz     loc_140014FB8
0x140014f15  cmp     [rdi+10h], r15
0x140014f19  jnz     short loc_140014F88
0x140014f1b  call    cs:__imp_GetLastError
0x140014f21  mov     r14d, eax
0x140014f24  xor     r8d, r8d; pcbe
0x140014f27  mov     rdx, rdi; pv
0x140014f2a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140014f31  call    cs:__imp_CreateThreadpoolTimer
0x140014f37  mov     r15, rax
0x140014f3a  mov     rbp, [rdi+10h]
0x140014f3e  test    rbp, rbp
0x140014f41  jz      short loc_140014F7B
0x140014f43  call    cs:__imp_GetLastError
0x140014f49  mov     ebx, eax
0x140014f4b  xor     r9d, r9d; msWindowLength
0x140014f4e  xor     r8d, r8d; msPeriod
0x140014f51  xor     edx, edx; pftDueTime
0x140014f53  mov     rcx, rbp; pti
0x140014f56  call    cs:__imp_SetThreadpoolTimer
0x140014f5c  mov     edx, 1; fCancelPendingCallbacks
0x140014f61  mov     rcx, rbp; pti
0x140014f64  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140014f6a  mov     rcx, rbp; pti
0x140014f6d  call    cs:__imp_CloseThreadpoolTimer
0x140014f73  mov     ecx, ebx; dwErrCode
0x140014f75  call    cs:__imp_SetLastError
0x140014f7b  mov     [rdi+10h], r15
0x140014f7f  mov     ecx, r14d; dwErrCode
0x140014f82  call    cs:__imp_SetLastError
0x140014f88  mov     rcx, [rdi+10h]; pti
0x140014f8c  test    rcx, rcx
0x140014f8f  jz      short loc_140014FB8
0x140014f91  mov     rax, 0FFFFFFFF4D2FA200h
0x140014f9b  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x140014fa0  mov     r9d, 124F8h; msWindowLength
0x140014fa6  xor     r8d, r8d; msPeriod
0x140014fa9  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x140014fae  call    cs:__imp_SetThreadpoolTimer
0x140014fb4  mov     byte ptr [rdi+18h], 1
0x140014fb8  test    rsi, rsi
0x140014fbb  jz      short loc_140014FC7
0x140014fbd  mov     rcx, rsi; SRWLock
0x140014fc0  call    cs:__imp_ReleaseSRWLockExclusive
0x140014fc6  nop
0x140014fc7  add     rsp, 28h
0x140014fcb  pop     r15
0x140014fcd  pop     r14
0x140014fcf  pop     rdi
0x140014fd0  pop     rsi
0x140014fd1  pop     rbp
0x140014fd2  pop     rbx
0x140014fd3  retn
```
