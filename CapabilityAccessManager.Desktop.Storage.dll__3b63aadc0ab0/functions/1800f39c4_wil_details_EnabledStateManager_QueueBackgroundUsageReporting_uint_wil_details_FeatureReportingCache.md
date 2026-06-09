# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1800f39c4`
- end: `0x1800f3b7c`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800f3d54`

## callees

- `0x1800039c6`
- `0x180003a40`
- `0x1800ec730`
- `0x1800f39c4`
- `0x18010d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f3a75`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f3a9d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f3a75`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800f3a9d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f3a11`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f3a11`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f3b68`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f3b68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f3b1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f3b2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f3b1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f3b2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f3ac3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f3aeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f3ac3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f3aeb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800f3ad9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800f3ad9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800f3b0c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800f3b0c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800f3b15`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800f3b15`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800f3afe`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800f3b56`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800f3afe`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800f3b56`

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
0x1800f39c4  push    rbx
0x1800f39c6  push    rbp
0x1800f39c7  push    rsi
0x1800f39c8  push    rdi
0x1800f39c9  push    r14
0x1800f39cb  push    r15
0x1800f39cd  sub     rsp, 28h
0x1800f39d1  mov     rbp, r8
0x1800f39d4  mov     r14d, edx
0x1800f39d7  mov     rdi, rcx
0x1800f39da  mov     eax, [rcx]
0x1800f39dc  test    eax, eax
0x1800f39de  jz      loc_1800F3B6F
0x1800f39e4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800f39eb  jnz     loc_1800F3B6F
0x1800f39f1  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800f39f8  test    rax, rax
0x1800f39fb  jz      short loc_1800F3A0A
0x1800f39fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3a02  test    al, al
0x1800f3a04  jnz     loc_1800F3B6F
0x1800f3a0a  lea     rsi, [rdi+8]
0x1800f3a0e  mov     rcx, rsi; SRWLock
0x1800f3a11  call    cs:__imp_AcquireSRWLockExclusive
0x1800f3a17  mov     eax, [rdi]
0x1800f3a19  test    eax, eax
0x1800f3a1b  jz      loc_1800F3B60
0x1800f3a21  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800f3a28  jnz     loc_1800F3B60
0x1800f3a2e  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800f3a35  test    rax, rax
0x1800f3a38  jz      short loc_1800F3A47
0x1800f3a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3a3f  test    al, al
0x1800f3a41  jnz     loc_1800F3B60
0x1800f3a47  xor     r15d, r15d
0x1800f3a4a  lea     edx, [r15+10h]; unsigned __int64
0x1800f3a4e  lea     rcx, [rdi+20h]; this
0x1800f3a52  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800f3a57  test    al, al
0x1800f3a59  jz      short loc_1800F3AB3
0x1800f3a5b  mov     rcx, [rdi+28h]; void *
0x1800f3a5f  mov     rax, [rdi+30h]
0x1800f3a63  sub     rax, rcx
0x1800f3a66  cmp     rcx, [rdi+30h]
0x1800f3a6a  sbb     r8, r8
0x1800f3a6d  and     r8, rax; Size
0x1800f3a70  test    rcx, rcx
0x1800f3a73  jnz     short loc_1800F3A83
0x1800f3a75  call    cs:__imp__o__errno
0x1800f3a7b  mov     dword ptr [rax], 16h
0x1800f3a81  jmp     short loc_1800F3AA9
0x1800f3a83  cmp     r8, 10h
0x1800f3a87  jb      short loc_1800F3A96
0x1800f3a89  mov     [rcx], r14d
0x1800f3a8c  mov     [rcx+4], r15d
0x1800f3a90  mov     [rcx+8], rbp
0x1800f3a94  jmp     short loc_1800F3AAE
0x1800f3a96  xor     edx, edx; Val
0x1800f3a98  call    memset_0
0x1800f3a9d  call    cs:__imp__o__errno
0x1800f3aa3  mov     dword ptr [rax], 22h ; '"'
0x1800f3aa9  call    _invalid_parameter_noinfo
0x1800f3aae  add     qword ptr [rdi+28h], 10h
0x1800f3ab3  cmp     [rdi+18h], r15b
0x1800f3ab7  jnz     loc_1800F3B60
0x1800f3abd  cmp     [rdi+10h], r15
0x1800f3ac1  jnz     short loc_1800F3B30
0x1800f3ac3  call    cs:__imp_GetLastError
0x1800f3ac9  mov     r14d, eax
0x1800f3acc  xor     r8d, r8d; pcbe
0x1800f3acf  mov     rdx, rdi; pv
0x1800f3ad2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800f3ad9  call    cs:__imp_CreateThreadpoolTimer
0x1800f3adf  mov     r15, rax
0x1800f3ae2  mov     rbp, [rdi+10h]
0x1800f3ae6  test    rbp, rbp
0x1800f3ae9  jz      short loc_1800F3B23
0x1800f3aeb  call    cs:__imp_GetLastError
0x1800f3af1  mov     ebx, eax
0x1800f3af3  xor     r9d, r9d; msWindowLength
0x1800f3af6  xor     r8d, r8d; msPeriod
0x1800f3af9  xor     edx, edx; pftDueTime
0x1800f3afb  mov     rcx, rbp; pti
0x1800f3afe  call    cs:__imp_SetThreadpoolTimer
0x1800f3b04  mov     edx, 1; fCancelPendingCallbacks
0x1800f3b09  mov     rcx, rbp; pti
0x1800f3b0c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800f3b12  mov     rcx, rbp; pti
0x1800f3b15  call    cs:__imp_CloseThreadpoolTimer
0x1800f3b1b  mov     ecx, ebx; dwErrCode
0x1800f3b1d  call    cs:__imp_SetLastError
0x1800f3b23  mov     [rdi+10h], r15
0x1800f3b27  mov     ecx, r14d; dwErrCode
0x1800f3b2a  call    cs:__imp_SetLastError
0x1800f3b30  mov     rcx, [rdi+10h]; pti
0x1800f3b34  test    rcx, rcx
0x1800f3b37  jz      short loc_1800F3B60
0x1800f3b39  mov     rax, 0FFFFFFFF4D2FA200h
0x1800f3b43  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x1800f3b48  mov     r9d, 124F8h; msWindowLength
0x1800f3b4e  xor     r8d, r8d; msPeriod
0x1800f3b51  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x1800f3b56  call    cs:__imp_SetThreadpoolTimer
0x1800f3b5c  mov     byte ptr [rdi+18h], 1
0x1800f3b60  test    rsi, rsi
0x1800f3b63  jz      short loc_1800F3B6F
0x1800f3b65  mov     rcx, rsi; SRWLock
0x1800f3b68  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f3b6e  nop
0x1800f3b6f  add     rsp, 28h
0x1800f3b73  pop     r15
0x1800f3b75  pop     r14
0x1800f3b77  pop     rdi
0x1800f3b78  pop     rsi
0x1800f3b79  pop     rbp
0x1800f3b7a  pop     rbx
0x1800f3b7b  retn
```
