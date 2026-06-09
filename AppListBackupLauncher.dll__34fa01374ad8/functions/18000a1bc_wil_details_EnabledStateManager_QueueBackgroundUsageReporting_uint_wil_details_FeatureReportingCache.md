# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000a1bc`
- end: `0x18000a374`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000bc10`

## callees

- `0x180002d6a`
- `0x180002de0`
- `0x18000a1bc`
- `0x18000eb4c`
- `0x180012010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a26d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a295`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a26d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a295`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a360`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a360`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a209`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a209`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a315`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a322`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a315`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a322`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a30d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a30d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a2f6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a34e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a2f6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a34e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a2d1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a2d1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a304`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a304`

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
0x18000a1bc  push    rbx
0x18000a1be  push    rbp
0x18000a1bf  push    rsi
0x18000a1c0  push    rdi
0x18000a1c1  push    r14
0x18000a1c3  push    r15
0x18000a1c5  sub     rsp, 28h
0x18000a1c9  mov     rbp, r8
0x18000a1cc  mov     r14d, edx
0x18000a1cf  mov     rdi, rcx
0x18000a1d2  mov     eax, [rcx]
0x18000a1d4  test    eax, eax
0x18000a1d6  jz      loc_18000A367
0x18000a1dc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000a1e3  jnz     loc_18000A367
0x18000a1e9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a1f0  test    rax, rax
0x18000a1f3  jz      short loc_18000A202
0x18000a1f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1fa  test    al, al
0x18000a1fc  jnz     loc_18000A367
0x18000a202  lea     rsi, [rdi+8]
0x18000a206  mov     rcx, rsi; SRWLock
0x18000a209  call    cs:__imp_AcquireSRWLockExclusive
0x18000a20f  mov     eax, [rdi]
0x18000a211  test    eax, eax
0x18000a213  jz      loc_18000A358
0x18000a219  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000a220  jnz     loc_18000A358
0x18000a226  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a22d  test    rax, rax
0x18000a230  jz      short loc_18000A23F
0x18000a232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a237  test    al, al
0x18000a239  jnz     loc_18000A358
0x18000a23f  xor     r15d, r15d
0x18000a242  lea     edx, [r15+10h]; unsigned __int64
0x18000a246  lea     rcx, [rdi+20h]; this
0x18000a24a  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000a24f  test    al, al
0x18000a251  jz      short loc_18000A2AB
0x18000a253  mov     rcx, [rdi+28h]; void *
0x18000a257  mov     rax, [rdi+30h]
0x18000a25b  sub     rax, rcx
0x18000a25e  cmp     rcx, [rdi+30h]
0x18000a262  sbb     r8, r8
0x18000a265  and     r8, rax; Size
0x18000a268  test    rcx, rcx
0x18000a26b  jnz     short loc_18000A27B
0x18000a26d  call    cs:__imp__o__errno
0x18000a273  mov     dword ptr [rax], 16h
0x18000a279  jmp     short loc_18000A2A1
0x18000a27b  cmp     r8, 10h
0x18000a27f  jb      short loc_18000A28E
0x18000a281  mov     [rcx], r14d
0x18000a284  mov     [rcx+4], r15d
0x18000a288  mov     [rcx+8], rbp
0x18000a28c  jmp     short loc_18000A2A6
0x18000a28e  xor     edx, edx; Val
0x18000a290  call    memset_0
0x18000a295  call    cs:__imp__o__errno
0x18000a29b  mov     dword ptr [rax], 22h ; '"'
0x18000a2a1  call    _invalid_parameter_noinfo
0x18000a2a6  add     qword ptr [rdi+28h], 10h
0x18000a2ab  cmp     [rdi+18h], r15b
0x18000a2af  jnz     loc_18000A358
0x18000a2b5  cmp     [rdi+10h], r15
0x18000a2b9  jnz     short loc_18000A328
0x18000a2bb  call    cs:__imp_GetLastError
0x18000a2c1  mov     r14d, eax
0x18000a2c4  xor     r8d, r8d; pcbe
0x18000a2c7  mov     rdx, rdi; pv
0x18000a2ca  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000a2d1  call    cs:__imp_CreateThreadpoolTimer
0x18000a2d7  mov     r15, rax
0x18000a2da  mov     rbp, [rdi+10h]
0x18000a2de  test    rbp, rbp
0x18000a2e1  jz      short loc_18000A31B
0x18000a2e3  call    cs:__imp_GetLastError
0x18000a2e9  mov     ebx, eax
0x18000a2eb  xor     r9d, r9d; msWindowLength
0x18000a2ee  xor     r8d, r8d; msPeriod
0x18000a2f1  xor     edx, edx; pftDueTime
0x18000a2f3  mov     rcx, rbp; pti
0x18000a2f6  call    cs:__imp_SetThreadpoolTimer
0x18000a2fc  mov     edx, 1; fCancelPendingCallbacks
0x18000a301  mov     rcx, rbp; pti
0x18000a304  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a30a  mov     rcx, rbp; pti
0x18000a30d  call    cs:__imp_CloseThreadpoolTimer
0x18000a313  mov     ecx, ebx; dwErrCode
0x18000a315  call    cs:__imp_SetLastError
0x18000a31b  mov     [rdi+10h], r15
0x18000a31f  mov     ecx, r14d; dwErrCode
0x18000a322  call    cs:__imp_SetLastError
0x18000a328  mov     rcx, [rdi+10h]; pti
0x18000a32c  test    rcx, rcx
0x18000a32f  jz      short loc_18000A358
0x18000a331  mov     rax, 0FFFFFFFF4D2FA200h
0x18000a33b  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18000a340  mov     r9d, 124F8h; msWindowLength
0x18000a346  xor     r8d, r8d; msPeriod
0x18000a349  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18000a34e  call    cs:__imp_SetThreadpoolTimer
0x18000a354  mov     byte ptr [rdi+18h], 1
0x18000a358  test    rsi, rsi
0x18000a35b  jz      short loc_18000A367
0x18000a35d  mov     rcx, rsi; SRWLock
0x18000a360  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a366  nop
0x18000a367  add     rsp, 28h
0x18000a36b  pop     r15
0x18000a36d  pop     r14
0x18000a36f  pop     rdi
0x18000a370  pop     rsi
0x18000a371  pop     rbp
0x18000a372  pop     rbx
0x18000a373  retn
```
