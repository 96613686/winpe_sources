# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000d45c`
- end: `0x18000d614`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000ea6c`

## callees

- `0x1800037d2`
- `0x1800038b8`
- `0x18000d45c`
- `0x18001125c`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d50d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d535`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d50d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d535`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d4a9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d4a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d600`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d600`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d5b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d5c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d5b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d5c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d55b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d583`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d55b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d583`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d596`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d5ee`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d596`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d5ee`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000d571`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000d571`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d5ad`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d5ad`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d5a4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d5a4`

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
0x18000d45c  push    rbx
0x18000d45e  push    rbp
0x18000d45f  push    rsi
0x18000d460  push    rdi
0x18000d461  push    r14
0x18000d463  push    r15
0x18000d465  sub     rsp, 28h
0x18000d469  mov     rbp, r8
0x18000d46c  mov     r14d, edx
0x18000d46f  mov     rdi, rcx
0x18000d472  mov     eax, [rcx]
0x18000d474  test    eax, eax
0x18000d476  jz      loc_18000D607
0x18000d47c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000d483  jnz     loc_18000D607
0x18000d489  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000d490  test    rax, rax
0x18000d493  jz      short loc_18000D4A2
0x18000d495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d49a  test    al, al
0x18000d49c  jnz     loc_18000D607
0x18000d4a2  lea     rsi, [rdi+8]
0x18000d4a6  mov     rcx, rsi; SRWLock
0x18000d4a9  call    cs:__imp_AcquireSRWLockExclusive
0x18000d4af  mov     eax, [rdi]
0x18000d4b1  test    eax, eax
0x18000d4b3  jz      loc_18000D5F8
0x18000d4b9  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000d4c0  jnz     loc_18000D5F8
0x18000d4c6  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000d4cd  test    rax, rax
0x18000d4d0  jz      short loc_18000D4DF
0x18000d4d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4d7  test    al, al
0x18000d4d9  jnz     loc_18000D5F8
0x18000d4df  xor     r15d, r15d
0x18000d4e2  lea     edx, [r15+10h]; unsigned __int64
0x18000d4e6  lea     rcx, [rdi+20h]; this
0x18000d4ea  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000d4ef  test    al, al
0x18000d4f1  jz      short loc_18000D54B
0x18000d4f3  mov     rcx, [rdi+28h]; void *
0x18000d4f7  mov     rax, [rdi+30h]
0x18000d4fb  sub     rax, rcx
0x18000d4fe  cmp     rcx, [rdi+30h]
0x18000d502  sbb     r8, r8
0x18000d505  and     r8, rax; Size
0x18000d508  test    rcx, rcx
0x18000d50b  jnz     short loc_18000D51B
0x18000d50d  call    cs:__imp__o__errno
0x18000d513  mov     dword ptr [rax], 16h
0x18000d519  jmp     short loc_18000D541
0x18000d51b  cmp     r8, 10h
0x18000d51f  jb      short loc_18000D52E
0x18000d521  mov     [rcx], r14d
0x18000d524  mov     [rcx+4], r15d
0x18000d528  mov     [rcx+8], rbp
0x18000d52c  jmp     short loc_18000D546
0x18000d52e  xor     edx, edx; Val
0x18000d530  call    memset_0
0x18000d535  call    cs:__imp__o__errno
0x18000d53b  mov     dword ptr [rax], 22h ; '"'
0x18000d541  call    _invalid_parameter_noinfo
0x18000d546  add     qword ptr [rdi+28h], 10h
0x18000d54b  cmp     [rdi+18h], r15b
0x18000d54f  jnz     loc_18000D5F8
0x18000d555  cmp     [rdi+10h], r15
0x18000d559  jnz     short loc_18000D5C8
0x18000d55b  call    cs:__imp_GetLastError
0x18000d561  mov     r14d, eax
0x18000d564  xor     r8d, r8d; pcbe
0x18000d567  mov     rdx, rdi; pv
0x18000d56a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000d571  call    cs:__imp_CreateThreadpoolTimer
0x18000d577  mov     r15, rax
0x18000d57a  mov     rbp, [rdi+10h]
0x18000d57e  test    rbp, rbp
0x18000d581  jz      short loc_18000D5BB
0x18000d583  call    cs:__imp_GetLastError
0x18000d589  mov     ebx, eax
0x18000d58b  xor     r9d, r9d; msWindowLength
0x18000d58e  xor     r8d, r8d; msPeriod
0x18000d591  xor     edx, edx; pftDueTime
0x18000d593  mov     rcx, rbp; pti
0x18000d596  call    cs:__imp_SetThreadpoolTimer
0x18000d59c  mov     edx, 1; fCancelPendingCallbacks
0x18000d5a1  mov     rcx, rbp; pti
0x18000d5a4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d5aa  mov     rcx, rbp; pti
0x18000d5ad  call    cs:__imp_CloseThreadpoolTimer
0x18000d5b3  mov     ecx, ebx; dwErrCode
0x18000d5b5  call    cs:__imp_SetLastError
0x18000d5bb  mov     [rdi+10h], r15
0x18000d5bf  mov     ecx, r14d; dwErrCode
0x18000d5c2  call    cs:__imp_SetLastError
0x18000d5c8  mov     rcx, [rdi+10h]; pti
0x18000d5cc  test    rcx, rcx
0x18000d5cf  jz      short loc_18000D5F8
0x18000d5d1  mov     rax, 0FFFFFFFF4D2FA200h
0x18000d5db  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18000d5e0  mov     r9d, 124F8h; msWindowLength
0x18000d5e6  xor     r8d, r8d; msPeriod
0x18000d5e9  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18000d5ee  call    cs:__imp_SetThreadpoolTimer
0x18000d5f4  mov     byte ptr [rdi+18h], 1
0x18000d5f8  test    rsi, rsi
0x18000d5fb  jz      short loc_18000D607
0x18000d5fd  mov     rcx, rsi; SRWLock
0x18000d600  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d606  nop
0x18000d607  add     rsp, 28h
0x18000d60b  pop     r15
0x18000d60d  pop     r14
0x18000d60f  pop     rdi
0x18000d610  pop     rsi
0x18000d611  pop     rbp
0x18000d612  pop     rbx
0x18000d613  retn
```
