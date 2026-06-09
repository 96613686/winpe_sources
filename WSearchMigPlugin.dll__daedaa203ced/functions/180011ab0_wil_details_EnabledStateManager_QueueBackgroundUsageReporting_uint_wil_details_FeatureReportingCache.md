# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180011ab0`
- end: `0x180011c71`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `449`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800121e0`

## callees

- `0x18000321a`
- `0x18000329c`
- `0x18000a05c`
- `0x180011ab0`
- `0x180018010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180011b6a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180011b92`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180011b6a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180011b92`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011b06`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011b06`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011c5d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011c5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011c12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011c1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011c12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011c1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011bb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011be0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011bb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011be0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011bf3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011c4b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011bf3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011c4b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011c0a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011c0a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011c01`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011c01`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180011bce`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180011bce`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  __int64 v6; // rcx
  _DWORD *v7; // rcx
  size_t v8; // r8
  __int64 v9; // rcx
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v13; // ebx
  struct _TP_TIMER *v14; // rcx
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress(pv)) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( !LODWORD(pv->Ptr)
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress(v6) )
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
            v13 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v13);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v14 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v14 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v14, &pftDueTime, 0, 0x124F8u);
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
      *(_DWORD *)_o__errno(v9) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x180011ab0  push    rbx
0x180011ab2  push    rbp
0x180011ab3  push    rsi
0x180011ab4  push    rdi
0x180011ab5  push    r14
0x180011ab7  push    r15
0x180011ab9  sub     rsp, 38h
0x180011abd  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x180011ac6  mov     rbp, r8
0x180011ac9  mov     r14d, edx
0x180011acc  mov     rdi, rcx
0x180011acf  mov     eax, [rcx]
0x180011ad1  test    eax, eax
0x180011ad3  jz      loc_180011C64
0x180011ad9  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180011ae0  jnz     loc_180011C64
0x180011ae6  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180011aed  test    rax, rax
0x180011af0  jz      short loc_180011AFF
0x180011af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011af7  test    al, al
0x180011af9  jnz     loc_180011C64
0x180011aff  lea     rsi, [rdi+8]
0x180011b03  mov     rcx, rsi; SRWLock
0x180011b06  call    cs:__imp_AcquireSRWLockExclusive
0x180011b0c  mov     eax, [rdi]
0x180011b0e  test    eax, eax
0x180011b10  jz      loc_180011C55
0x180011b16  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180011b1d  jnz     loc_180011C55
0x180011b23  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180011b2a  test    rax, rax
0x180011b2d  jz      short loc_180011B3C
0x180011b2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b34  test    al, al
0x180011b36  jnz     loc_180011C55
0x180011b3c  xor     r15d, r15d
0x180011b3f  lea     edx, [r15+10h]; unsigned __int64
0x180011b43  lea     rcx, [rdi+20h]; this
0x180011b47  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180011b4c  test    al, al
0x180011b4e  jz      short loc_180011BA8
0x180011b50  mov     rcx, [rdi+28h]; void *
0x180011b54  mov     rax, [rdi+30h]
0x180011b58  sub     rax, rcx
0x180011b5b  cmp     rcx, [rdi+30h]
0x180011b5f  sbb     r8, r8
0x180011b62  and     r8, rax; Size
0x180011b65  test    rcx, rcx
0x180011b68  jnz     short loc_180011B78
0x180011b6a  call    cs:__imp__o__errno
0x180011b70  mov     dword ptr [rax], 16h
0x180011b76  jmp     short loc_180011B9E
0x180011b78  cmp     r8, 10h
0x180011b7c  jb      short loc_180011B8B
0x180011b7e  mov     [rcx], r14d
0x180011b81  mov     [rcx+4], r15d
0x180011b85  mov     [rcx+8], rbp
0x180011b89  jmp     short loc_180011BA3
0x180011b8b  xor     edx, edx; Val
0x180011b8d  call    memset_0
0x180011b92  call    cs:__imp__o__errno
0x180011b98  mov     dword ptr [rax], 22h ; '"'
0x180011b9e  call    _invalid_parameter_noinfo
0x180011ba3  add     qword ptr [rdi+28h], 10h
0x180011ba8  cmp     [rdi+18h], r15b
0x180011bac  jnz     loc_180011C55
0x180011bb2  cmp     [rdi+10h], r15
0x180011bb6  jnz     short loc_180011C25
0x180011bb8  call    cs:__imp_GetLastError
0x180011bbe  mov     r14d, eax
0x180011bc1  xor     r8d, r8d; pcbe
0x180011bc4  mov     rdx, rdi; pv
0x180011bc7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180011bce  call    cs:__imp_CreateThreadpoolTimer
0x180011bd4  mov     r15, rax
0x180011bd7  mov     rbp, [rdi+10h]
0x180011bdb  test    rbp, rbp
0x180011bde  jz      short loc_180011C18
0x180011be0  call    cs:__imp_GetLastError
0x180011be6  mov     ebx, eax
0x180011be8  xor     r9d, r9d; msWindowLength
0x180011beb  xor     r8d, r8d; msPeriod
0x180011bee  xor     edx, edx; pftDueTime
0x180011bf0  mov     rcx, rbp; pti
0x180011bf3  call    cs:__imp_SetThreadpoolTimer
0x180011bf9  mov     edx, 1; fCancelPendingCallbacks
0x180011bfe  mov     rcx, rbp; pti
0x180011c01  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180011c07  mov     rcx, rbp; pti
0x180011c0a  call    cs:__imp_CloseThreadpoolTimer
0x180011c10  mov     ecx, ebx; dwErrCode
0x180011c12  call    cs:__imp_SetLastError
0x180011c18  mov     [rdi+10h], r15
0x180011c1c  mov     ecx, r14d; dwErrCode
0x180011c1f  call    cs:__imp_SetLastError
0x180011c25  mov     rcx, [rdi+10h]; pti
0x180011c29  test    rcx, rcx
0x180011c2c  jz      short loc_180011C55
0x180011c2e  mov     rax, 0FFFFFFFF4D2FA200h
0x180011c38  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x180011c3d  mov     r9d, 124F8h; msWindowLength
0x180011c43  xor     r8d, r8d; msPeriod
0x180011c46  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180011c4b  call    cs:__imp_SetThreadpoolTimer
0x180011c51  mov     byte ptr [rdi+18h], 1
0x180011c55  test    rsi, rsi
0x180011c58  jz      short loc_180011C64
0x180011c5a  mov     rcx, rsi; SRWLock
0x180011c5d  call    cs:__imp_ReleaseSRWLockExclusive
0x180011c63  nop
0x180011c64  add     rsp, 38h
0x180011c68  pop     r15
0x180011c6a  pop     r14
0x180011c6c  pop     rdi
0x180011c6d  pop     rsi
0x180011c6e  pop     rbp
0x180011c6f  pop     rbx
0x180011c70  retn
```
