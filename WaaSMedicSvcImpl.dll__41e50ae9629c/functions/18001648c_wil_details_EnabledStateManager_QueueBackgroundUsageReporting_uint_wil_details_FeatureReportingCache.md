# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18001648c`
- end: `0x180016644`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800178b0`

## callees

- `0x180005b3e`
- `0x180005bbc`
- `0x18001648c`
- `0x18001d754`
- `0x18006f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001653d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180016565`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001653d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180016565`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016630`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016630`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800164d9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800164d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001658b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800165b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001658b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800165b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800165e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800165f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800165e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800165f2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800165a1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800165a1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800165dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800165dd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800165c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001661e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800165c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001661e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800165d4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800165d4`

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
0x18001648c  push    rbx
0x18001648e  push    rbp
0x18001648f  push    rsi
0x180016490  push    rdi
0x180016491  push    r14
0x180016493  push    r15
0x180016495  sub     rsp, 28h
0x180016499  mov     rbp, r8
0x18001649c  mov     r14d, edx
0x18001649f  mov     rdi, rcx
0x1800164a2  mov     eax, [rcx]
0x1800164a4  test    eax, eax
0x1800164a6  jz      loc_180016637
0x1800164ac  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800164b3  jnz     loc_180016637
0x1800164b9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800164c0  test    rax, rax
0x1800164c3  jz      short loc_1800164D2
0x1800164c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164ca  test    al, al
0x1800164cc  jnz     loc_180016637
0x1800164d2  lea     rsi, [rdi+8]
0x1800164d6  mov     rcx, rsi; SRWLock
0x1800164d9  call    cs:__imp_AcquireSRWLockExclusive
0x1800164df  mov     eax, [rdi]
0x1800164e1  test    eax, eax
0x1800164e3  jz      loc_180016628
0x1800164e9  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800164f0  jnz     loc_180016628
0x1800164f6  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800164fd  test    rax, rax
0x180016500  jz      short loc_18001650F
0x180016502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016507  test    al, al
0x180016509  jnz     loc_180016628
0x18001650f  xor     r15d, r15d
0x180016512  lea     edx, [r15+10h]; unsigned __int64
0x180016516  lea     rcx, [rdi+20h]; this
0x18001651a  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001651f  test    al, al
0x180016521  jz      short loc_18001657B
0x180016523  mov     rcx, [rdi+28h]; void *
0x180016527  mov     rax, [rdi+30h]
0x18001652b  sub     rax, rcx
0x18001652e  cmp     rcx, [rdi+30h]
0x180016532  sbb     r8, r8
0x180016535  and     r8, rax; Size
0x180016538  test    rcx, rcx
0x18001653b  jnz     short loc_18001654B
0x18001653d  call    cs:__imp__o__errno
0x180016543  mov     dword ptr [rax], 16h
0x180016549  jmp     short loc_180016571
0x18001654b  cmp     r8, 10h
0x18001654f  jb      short loc_18001655E
0x180016551  mov     [rcx], r14d
0x180016554  mov     [rcx+4], r15d
0x180016558  mov     [rcx+8], rbp
0x18001655c  jmp     short loc_180016576
0x18001655e  xor     edx, edx; Val
0x180016560  call    memset_0
0x180016565  call    cs:__imp__o__errno
0x18001656b  mov     dword ptr [rax], 22h ; '"'
0x180016571  call    _invalid_parameter_noinfo
0x180016576  add     qword ptr [rdi+28h], 10h
0x18001657b  cmp     [rdi+18h], r15b
0x18001657f  jnz     loc_180016628
0x180016585  cmp     [rdi+10h], r15
0x180016589  jnz     short loc_1800165F8
0x18001658b  call    cs:__imp_GetLastError
0x180016591  mov     r14d, eax
0x180016594  xor     r8d, r8d; pcbe
0x180016597  mov     rdx, rdi; pv
0x18001659a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800165a1  call    cs:__imp_CreateThreadpoolTimer
0x1800165a7  mov     r15, rax
0x1800165aa  mov     rbp, [rdi+10h]
0x1800165ae  test    rbp, rbp
0x1800165b1  jz      short loc_1800165EB
0x1800165b3  call    cs:__imp_GetLastError
0x1800165b9  mov     ebx, eax
0x1800165bb  xor     r9d, r9d; msWindowLength
0x1800165be  xor     r8d, r8d; msPeriod
0x1800165c1  xor     edx, edx; pftDueTime
0x1800165c3  mov     rcx, rbp; pti
0x1800165c6  call    cs:__imp_SetThreadpoolTimer
0x1800165cc  mov     edx, 1; fCancelPendingCallbacks
0x1800165d1  mov     rcx, rbp; pti
0x1800165d4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800165da  mov     rcx, rbp; pti
0x1800165dd  call    cs:__imp_CloseThreadpoolTimer
0x1800165e3  mov     ecx, ebx; dwErrCode
0x1800165e5  call    cs:__imp_SetLastError
0x1800165eb  mov     [rdi+10h], r15
0x1800165ef  mov     ecx, r14d; dwErrCode
0x1800165f2  call    cs:__imp_SetLastError
0x1800165f8  mov     rcx, [rdi+10h]; pti
0x1800165fc  test    rcx, rcx
0x1800165ff  jz      short loc_180016628
0x180016601  mov     rax, 0FFFFFFFF4D2FA200h
0x18001660b  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x180016610  mov     r9d, 124F8h; msWindowLength
0x180016616  xor     r8d, r8d; msPeriod
0x180016619  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18001661e  call    cs:__imp_SetThreadpoolTimer
0x180016624  mov     byte ptr [rdi+18h], 1
0x180016628  test    rsi, rsi
0x18001662b  jz      short loc_180016637
0x18001662d  mov     rcx, rsi; SRWLock
0x180016630  call    cs:__imp_ReleaseSRWLockExclusive
0x180016636  nop
0x180016637  add     rsp, 28h
0x18001663b  pop     r15
0x18001663d  pop     r14
0x18001663f  pop     rdi
0x180016640  pop     rsi
0x180016641  pop     rbp
0x180016642  pop     rbx
0x180016643  retn
```
