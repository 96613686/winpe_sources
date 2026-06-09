# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180013924`
- end: `0x180013adc`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180014d8c`

## callees

- `0x1800030ee`
- `0x18000316c`
- `0x180013924`
- `0x1800159cc`
- `0x18004f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800139d5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800139fd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800139d5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800139fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013ac8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013ac8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013971`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013971`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013a7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013a8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013a7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013a8a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180013a75`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180013a75`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013a6c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013a6c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180013a39`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180013a39`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013a5e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013ab6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013a5e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013ab6`

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
0x180013924  push    rbx
0x180013926  push    rbp
0x180013927  push    rsi
0x180013928  push    rdi
0x180013929  push    r14
0x18001392b  push    r15
0x18001392d  sub     rsp, 28h
0x180013931  mov     rbp, r8
0x180013934  mov     r14d, edx
0x180013937  mov     rdi, rcx
0x18001393a  mov     eax, [rcx]
0x18001393c  test    eax, eax
0x18001393e  jz      loc_180013ACF
0x180013944  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001394b  jnz     loc_180013ACF
0x180013951  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180013958  test    rax, rax
0x18001395b  jz      short loc_18001396A
0x18001395d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013962  test    al, al
0x180013964  jnz     loc_180013ACF
0x18001396a  lea     rsi, [rdi+8]
0x18001396e  mov     rcx, rsi; SRWLock
0x180013971  call    cs:__imp_AcquireSRWLockExclusive
0x180013977  mov     eax, [rdi]
0x180013979  test    eax, eax
0x18001397b  jz      loc_180013AC0
0x180013981  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180013988  jnz     loc_180013AC0
0x18001398e  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180013995  test    rax, rax
0x180013998  jz      short loc_1800139A7
0x18001399a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001399f  test    al, al
0x1800139a1  jnz     loc_180013AC0
0x1800139a7  xor     r15d, r15d
0x1800139aa  lea     edx, [r15+10h]; unsigned __int64
0x1800139ae  lea     rcx, [rdi+20h]; this
0x1800139b2  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800139b7  test    al, al
0x1800139b9  jz      short loc_180013A13
0x1800139bb  mov     rcx, [rdi+28h]; void *
0x1800139bf  mov     rax, [rdi+30h]
0x1800139c3  sub     rax, rcx
0x1800139c6  cmp     rcx, [rdi+30h]
0x1800139ca  sbb     r8, r8
0x1800139cd  and     r8, rax; Size
0x1800139d0  test    rcx, rcx
0x1800139d3  jnz     short loc_1800139E3
0x1800139d5  call    cs:__imp__o__errno
0x1800139db  mov     dword ptr [rax], 16h
0x1800139e1  jmp     short loc_180013A09
0x1800139e3  cmp     r8, 10h
0x1800139e7  jb      short loc_1800139F6
0x1800139e9  mov     [rcx], r14d
0x1800139ec  mov     [rcx+4], r15d
0x1800139f0  mov     [rcx+8], rbp
0x1800139f4  jmp     short loc_180013A0E
0x1800139f6  xor     edx, edx; Val
0x1800139f8  call    memset_0
0x1800139fd  call    cs:__imp__o__errno
0x180013a03  mov     dword ptr [rax], 22h ; '"'
0x180013a09  call    _invalid_parameter_noinfo
0x180013a0e  add     qword ptr [rdi+28h], 10h
0x180013a13  cmp     [rdi+18h], r15b
0x180013a17  jnz     loc_180013AC0
0x180013a1d  cmp     [rdi+10h], r15
0x180013a21  jnz     short loc_180013A90
0x180013a23  call    cs:__imp_GetLastError
0x180013a29  mov     r14d, eax
0x180013a2c  xor     r8d, r8d; pcbe
0x180013a2f  mov     rdx, rdi; pv
0x180013a32  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180013a39  call    cs:__imp_CreateThreadpoolTimer
0x180013a3f  mov     r15, rax
0x180013a42  mov     rbp, [rdi+10h]
0x180013a46  test    rbp, rbp
0x180013a49  jz      short loc_180013A83
0x180013a4b  call    cs:__imp_GetLastError
0x180013a51  mov     ebx, eax
0x180013a53  xor     r9d, r9d; msWindowLength
0x180013a56  xor     r8d, r8d; msPeriod
0x180013a59  xor     edx, edx; pftDueTime
0x180013a5b  mov     rcx, rbp; pti
0x180013a5e  call    cs:__imp_SetThreadpoolTimer
0x180013a64  mov     edx, 1; fCancelPendingCallbacks
0x180013a69  mov     rcx, rbp; pti
0x180013a6c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180013a72  mov     rcx, rbp; pti
0x180013a75  call    cs:__imp_CloseThreadpoolTimer
0x180013a7b  mov     ecx, ebx; dwErrCode
0x180013a7d  call    cs:__imp_SetLastError
0x180013a83  mov     [rdi+10h], r15
0x180013a87  mov     ecx, r14d; dwErrCode
0x180013a8a  call    cs:__imp_SetLastError
0x180013a90  mov     rcx, [rdi+10h]; pti
0x180013a94  test    rcx, rcx
0x180013a97  jz      short loc_180013AC0
0x180013a99  mov     rax, 0FFFFFFFF4D2FA200h
0x180013aa3  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x180013aa8  mov     r9d, 124F8h; msWindowLength
0x180013aae  xor     r8d, r8d; msPeriod
0x180013ab1  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180013ab6  call    cs:__imp_SetThreadpoolTimer
0x180013abc  mov     byte ptr [rdi+18h], 1
0x180013ac0  test    rsi, rsi
0x180013ac3  jz      short loc_180013ACF
0x180013ac5  mov     rcx, rsi; SRWLock
0x180013ac8  call    cs:__imp_ReleaseSRWLockExclusive
0x180013ace  nop
0x180013acf  add     rsp, 28h
0x180013ad3  pop     r15
0x180013ad5  pop     r14
0x180013ad7  pop     rdi
0x180013ad8  pop     rsi
0x180013ad9  pop     rbp
0x180013ada  pop     rbx
0x180013adb  retn
```
