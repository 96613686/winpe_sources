# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000aabc`
- end: `0x18000ac74`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000ae4c`

## callees

- `0x1800029ca`
- `0x180002a28`
- `0x180009d1c`
- `0x18000aabc`
- `0x180019010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ab6d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ab95`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ab6d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ab95`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ac15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ac22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ac15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ac22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000abbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000abe3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000abbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000abe3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ab09`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ab09`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ac60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ac60`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ac04`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ac04`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ac0d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ac0d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000abf6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ac4e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000abf6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ac4e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000abd1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000abd1`

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
0x18000aabc  push    rbx
0x18000aabe  push    rbp
0x18000aabf  push    rsi
0x18000aac0  push    rdi
0x18000aac1  push    r14
0x18000aac3  push    r15
0x18000aac5  sub     rsp, 28h
0x18000aac9  mov     rbp, r8
0x18000aacc  mov     r14d, edx
0x18000aacf  mov     rdi, rcx
0x18000aad2  mov     eax, [rcx]
0x18000aad4  test    eax, eax
0x18000aad6  jz      loc_18000AC67
0x18000aadc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000aae3  jnz     loc_18000AC67
0x18000aae9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000aaf0  test    rax, rax
0x18000aaf3  jz      short loc_18000AB02
0x18000aaf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aafa  test    al, al
0x18000aafc  jnz     loc_18000AC67
0x18000ab02  lea     rsi, [rdi+8]
0x18000ab06  mov     rcx, rsi; SRWLock
0x18000ab09  call    cs:__imp_AcquireSRWLockExclusive
0x18000ab0f  mov     eax, [rdi]
0x18000ab11  test    eax, eax
0x18000ab13  jz      loc_18000AC58
0x18000ab19  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000ab20  jnz     loc_18000AC58
0x18000ab26  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ab2d  test    rax, rax
0x18000ab30  jz      short loc_18000AB3F
0x18000ab32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab37  test    al, al
0x18000ab39  jnz     loc_18000AC58
0x18000ab3f  xor     r15d, r15d
0x18000ab42  lea     edx, [r15+10h]; unsigned __int64
0x18000ab46  lea     rcx, [rdi+20h]; this
0x18000ab4a  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000ab4f  test    al, al
0x18000ab51  jz      short loc_18000ABAB
0x18000ab53  mov     rcx, [rdi+28h]; void *
0x18000ab57  mov     rax, [rdi+30h]
0x18000ab5b  sub     rax, rcx
0x18000ab5e  cmp     rcx, [rdi+30h]
0x18000ab62  sbb     r8, r8
0x18000ab65  and     r8, rax; Size
0x18000ab68  test    rcx, rcx
0x18000ab6b  jnz     short loc_18000AB7B
0x18000ab6d  call    cs:__imp__o__errno
0x18000ab73  mov     dword ptr [rax], 16h
0x18000ab79  jmp     short loc_18000ABA1
0x18000ab7b  cmp     r8, 10h
0x18000ab7f  jb      short loc_18000AB8E
0x18000ab81  mov     [rcx], r14d
0x18000ab84  mov     [rcx+4], r15d
0x18000ab88  mov     [rcx+8], rbp
0x18000ab8c  jmp     short loc_18000ABA6
0x18000ab8e  xor     edx, edx; Val
0x18000ab90  call    memset_0
0x18000ab95  call    cs:__imp__o__errno
0x18000ab9b  mov     dword ptr [rax], 22h ; '"'
0x18000aba1  call    _invalid_parameter_noinfo
0x18000aba6  add     qword ptr [rdi+28h], 10h
0x18000abab  cmp     [rdi+18h], r15b
0x18000abaf  jnz     loc_18000AC58
0x18000abb5  cmp     [rdi+10h], r15
0x18000abb9  jnz     short loc_18000AC28
0x18000abbb  call    cs:__imp_GetLastError
0x18000abc1  mov     r14d, eax
0x18000abc4  xor     r8d, r8d; pcbe
0x18000abc7  mov     rdx, rdi; pv
0x18000abca  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000abd1  call    cs:__imp_CreateThreadpoolTimer
0x18000abd7  mov     r15, rax
0x18000abda  mov     rbp, [rdi+10h]
0x18000abde  test    rbp, rbp
0x18000abe1  jz      short loc_18000AC1B
0x18000abe3  call    cs:__imp_GetLastError
0x18000abe9  mov     ebx, eax
0x18000abeb  xor     r9d, r9d; msWindowLength
0x18000abee  xor     r8d, r8d; msPeriod
0x18000abf1  xor     edx, edx; pftDueTime
0x18000abf3  mov     rcx, rbp; pti
0x18000abf6  call    cs:__imp_SetThreadpoolTimer
0x18000abfc  mov     edx, 1; fCancelPendingCallbacks
0x18000ac01  mov     rcx, rbp; pti
0x18000ac04  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ac0a  mov     rcx, rbp; pti
0x18000ac0d  call    cs:__imp_CloseThreadpoolTimer
0x18000ac13  mov     ecx, ebx; dwErrCode
0x18000ac15  call    cs:__imp_SetLastError
0x18000ac1b  mov     [rdi+10h], r15
0x18000ac1f  mov     ecx, r14d; dwErrCode
0x18000ac22  call    cs:__imp_SetLastError
0x18000ac28  mov     rcx, [rdi+10h]; pti
0x18000ac2c  test    rcx, rcx
0x18000ac2f  jz      short loc_18000AC58
0x18000ac31  mov     rax, 0FFFFFFFF4D2FA200h
0x18000ac3b  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18000ac40  mov     r9d, 124F8h; msWindowLength
0x18000ac46  xor     r8d, r8d; msPeriod
0x18000ac49  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18000ac4e  call    cs:__imp_SetThreadpoolTimer
0x18000ac54  mov     byte ptr [rdi+18h], 1
0x18000ac58  test    rsi, rsi
0x18000ac5b  jz      short loc_18000AC67
0x18000ac5d  mov     rcx, rsi; SRWLock
0x18000ac60  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ac66  nop
0x18000ac67  add     rsp, 28h
0x18000ac6b  pop     r15
0x18000ac6d  pop     r14
0x18000ac6f  pop     rdi
0x18000ac70  pop     rsi
0x18000ac71  pop     rbp
0x18000ac72  pop     rbx
0x18000ac73  retn
```
