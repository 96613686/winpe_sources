# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000a9a8`
- end: `0x18000ab60`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000aca0`

## callees

- `0x180002766`
- `0x1800027c8`
- `0x18000911c`
- `0x18000a9a8`
- `0x18002a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000aa59`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000aa81`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000aa59`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000aa81`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ab4c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ab4c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a9f5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a9f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ab01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ab0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ab01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ab0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aaa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aacf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aaa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aacf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000aae2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ab3a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000aae2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ab3a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000aaf9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000aaf9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000aaf0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000aaf0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000aabd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000aabd`

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
0x18000a9a8  push    rbx
0x18000a9aa  push    rbp
0x18000a9ab  push    rsi
0x18000a9ac  push    rdi
0x18000a9ad  push    r14
0x18000a9af  push    r15
0x18000a9b1  sub     rsp, 28h
0x18000a9b5  mov     rbp, r8
0x18000a9b8  mov     r14d, edx
0x18000a9bb  mov     rdi, rcx
0x18000a9be  mov     eax, [rcx]
0x18000a9c0  test    eax, eax
0x18000a9c2  jz      loc_18000AB53
0x18000a9c8  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000a9cf  jnz     loc_18000AB53
0x18000a9d5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a9dc  test    rax, rax
0x18000a9df  jz      short loc_18000A9EE
0x18000a9e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9e6  test    al, al
0x18000a9e8  jnz     loc_18000AB53
0x18000a9ee  lea     rsi, [rdi+8]
0x18000a9f2  mov     rcx, rsi; SRWLock
0x18000a9f5  call    cs:__imp_AcquireSRWLockExclusive
0x18000a9fb  mov     eax, [rdi]
0x18000a9fd  test    eax, eax
0x18000a9ff  jz      loc_18000AB44
0x18000aa05  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000aa0c  jnz     loc_18000AB44
0x18000aa12  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000aa19  test    rax, rax
0x18000aa1c  jz      short loc_18000AA2B
0x18000aa1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa23  test    al, al
0x18000aa25  jnz     loc_18000AB44
0x18000aa2b  xor     r15d, r15d
0x18000aa2e  lea     edx, [r15+10h]; unsigned __int64
0x18000aa32  lea     rcx, [rdi+20h]; this
0x18000aa36  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000aa3b  test    al, al
0x18000aa3d  jz      short loc_18000AA97
0x18000aa3f  mov     rcx, [rdi+28h]; void *
0x18000aa43  mov     rax, [rdi+30h]
0x18000aa47  sub     rax, rcx
0x18000aa4a  cmp     rcx, [rdi+30h]
0x18000aa4e  sbb     r8, r8
0x18000aa51  and     r8, rax; Size
0x18000aa54  test    rcx, rcx
0x18000aa57  jnz     short loc_18000AA67
0x18000aa59  call    cs:__imp__o__errno
0x18000aa5f  mov     dword ptr [rax], 16h
0x18000aa65  jmp     short loc_18000AA8D
0x18000aa67  cmp     r8, 10h
0x18000aa6b  jb      short loc_18000AA7A
0x18000aa6d  mov     [rcx], r14d
0x18000aa70  mov     [rcx+4], r15d
0x18000aa74  mov     [rcx+8], rbp
0x18000aa78  jmp     short loc_18000AA92
0x18000aa7a  xor     edx, edx; Val
0x18000aa7c  call    memset_0
0x18000aa81  call    cs:__imp__o__errno
0x18000aa87  mov     dword ptr [rax], 22h ; '"'
0x18000aa8d  call    _invalid_parameter_noinfo
0x18000aa92  add     qword ptr [rdi+28h], 10h
0x18000aa97  cmp     [rdi+18h], r15b
0x18000aa9b  jnz     loc_18000AB44
0x18000aaa1  cmp     [rdi+10h], r15
0x18000aaa5  jnz     short loc_18000AB14
0x18000aaa7  call    cs:__imp_GetLastError
0x18000aaad  mov     r14d, eax
0x18000aab0  xor     r8d, r8d; pcbe
0x18000aab3  mov     rdx, rdi; pv
0x18000aab6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000aabd  call    cs:__imp_CreateThreadpoolTimer
0x18000aac3  mov     r15, rax
0x18000aac6  mov     rbp, [rdi+10h]
0x18000aaca  test    rbp, rbp
0x18000aacd  jz      short loc_18000AB07
0x18000aacf  call    cs:__imp_GetLastError
0x18000aad5  mov     ebx, eax
0x18000aad7  xor     r9d, r9d; msWindowLength
0x18000aada  xor     r8d, r8d; msPeriod
0x18000aadd  xor     edx, edx; pftDueTime
0x18000aadf  mov     rcx, rbp; pti
0x18000aae2  call    cs:__imp_SetThreadpoolTimer
0x18000aae8  mov     edx, 1; fCancelPendingCallbacks
0x18000aaed  mov     rcx, rbp; pti
0x18000aaf0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000aaf6  mov     rcx, rbp; pti
0x18000aaf9  call    cs:__imp_CloseThreadpoolTimer
0x18000aaff  mov     ecx, ebx; dwErrCode
0x18000ab01  call    cs:__imp_SetLastError
0x18000ab07  mov     [rdi+10h], r15
0x18000ab0b  mov     ecx, r14d; dwErrCode
0x18000ab0e  call    cs:__imp_SetLastError
0x18000ab14  mov     rcx, [rdi+10h]; pti
0x18000ab18  test    rcx, rcx
0x18000ab1b  jz      short loc_18000AB44
0x18000ab1d  mov     rax, 0FFFFFFFF4D2FA200h
0x18000ab27  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18000ab2c  mov     r9d, 124F8h; msWindowLength
0x18000ab32  xor     r8d, r8d; msPeriod
0x18000ab35  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18000ab3a  call    cs:__imp_SetThreadpoolTimer
0x18000ab40  mov     byte ptr [rdi+18h], 1
0x18000ab44  test    rsi, rsi
0x18000ab47  jz      short loc_18000AB53
0x18000ab49  mov     rcx, rsi; SRWLock
0x18000ab4c  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ab52  nop
0x18000ab53  add     rsp, 28h
0x18000ab57  pop     r15
0x18000ab59  pop     r14
0x18000ab5b  pop     rdi
0x18000ab5c  pop     rsi
0x18000ab5d  pop     rbp
0x18000ab5e  pop     rbx
0x18000ab5f  retn
```
