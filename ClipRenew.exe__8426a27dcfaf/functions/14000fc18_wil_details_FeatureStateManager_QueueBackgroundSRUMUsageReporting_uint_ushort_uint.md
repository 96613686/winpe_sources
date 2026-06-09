# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x14000fc18`
- end: `0x14000fda0`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `392`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140011920`

## callees

- `0x14000fc18`
- `0x140011fcc`
- `0x1400134a0`
- `0x140014010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000fcc6`
- `msvcrt!memcpy_s` at `0x14000fcc6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000fd80`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000fd80`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000fc76`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000fc76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000fd3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000fd48`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000fd3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000fd48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fd09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fd09`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000fd2a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000fd2a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000fd33`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000fd33`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000fd1c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000fd6e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000fd1c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000fd6e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000fcf7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000fcf7`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        __int16 a3,
        int a4)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *Ptr; // rbp
  PTP_TIMER v11; // r15
  DWORD v12; // ebx
  struct _TP_TIMER *v13; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-58h] BYREF
  int Source; // [rsp+28h] [rbp-50h] BYREF
  __int16 v16; // [rsp+2Ch] [rbp-4Ch]
  __int16 v17; // [rsp+2Eh] [rbp-4Ah]
  int v18; // [rsp+30h] [rbp-48h]

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 5);
    Source = a2;
    v16 = a3;
    v17 = 0;
    v18 = a4;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
    {
      memcpy_s(
        pv[30].Ptr,
        ((char *)pv[31].Ptr - (char *)pv[30].Ptr) & -(__int64)(pv[30].Ptr < pv[31].Ptr),
        &Source,
        0xCu);
      pv[30].Ptr = (char *)pv[30].Ptr + 12;
    }
    if ( !LOBYTE(pv[8].Ptr) )
    {
      if ( !pv[7].Ptr )
      {
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        Ptr = (struct _TP_TIMER *)pv[7].Ptr;
        v11 = ThreadpoolTimer;
        if ( Ptr )
        {
          v12 = GetLastError();
          SetThreadpoolTimer(Ptr, 0, 0, 0);
          WaitForThreadpoolTimerCallbacks(Ptr, 1);
          CloseThreadpoolTimer(Ptr);
          SetLastError(v12);
        }
        pv[7].Ptr = v11;
        SetLastError(LastError);
      }
      v13 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v13 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v13, &pftDueTime, 0, 0x4E2u);
        LOBYTE(pv[8].Ptr) = 1;
      }
    }
    if ( pv != (RTL_SRWLOCK *)-40LL )
      ReleaseSRWLockExclusive(pv + 5);
  }
}

```

## disassembly

```asm
0x14000fc18  push    rbx
0x14000fc1a  push    rbp
0x14000fc1b  push    rsi
0x14000fc1c  push    rdi
0x14000fc1d  push    r14
0x14000fc1f  push    r15
0x14000fc21  sub     rsp, 48h
0x14000fc25  mov     rax, cs:__security_cookie
0x14000fc2c  xor     rax, rsp
0x14000fc2f  mov     [rsp+78h+var_40], rax
0x14000fc34  cmp     byte ptr [rcx], 0
0x14000fc37  mov     r14d, r9d
0x14000fc3a  movzx   ebp, r8w
0x14000fc3e  mov     ebx, edx
0x14000fc40  mov     rdi, rcx
0x14000fc43  jz      loc_14000FD86
0x14000fc49  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000fc50  jnz     loc_14000FD86
0x14000fc56  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000fc5d  test    rax, rax
0x14000fc60  jz      short loc_14000FC6F
0x14000fc62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fc67  test    al, al
0x14000fc69  jnz     loc_14000FD86
0x14000fc6f  lea     rsi, [rdi+28h]
0x14000fc73  mov     rcx, rsi; SRWLock
0x14000fc76  call    cs:__imp_AcquireSRWLockExclusive
0x14000fc7c  xor     eax, eax
0x14000fc7e  mov     [rsp+78h+Source], ebx
0x14000fc82  mov     [rsp+78h+var_4C], bp
0x14000fc87  lea     rbx, [rdi+0E8h]
0x14000fc8e  mov     rcx, rbx; this
0x14000fc91  mov     [rsp+78h+var_4A], ax
0x14000fc96  mov     [rsp+78h+var_48], r14d
0x14000fc9b  lea     ebp, [rax+0Ch]
0x14000fc9e  mov     edx, ebp; unsigned __int64
0x14000fca0  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000fca5  test    al, al
0x14000fca7  jz      short loc_14000FCD0
0x14000fca9  mov     rcx, [rbx+8]; Destination
0x14000fcad  lea     r8, [rsp+78h+Source]; Source
0x14000fcb2  mov     rax, [rbx+10h]
0x14000fcb6  mov     r9d, ebp; SourceSize
0x14000fcb9  sub     rax, rcx
0x14000fcbc  cmp     rcx, [rbx+10h]
0x14000fcc0  sbb     rdx, rdx
0x14000fcc3  and     rdx, rax; DestinationSize
0x14000fcc6  call    cs:__imp_memcpy_s
0x14000fccc  add     [rbx+8], rbp
0x14000fcd0  cmp     byte ptr [rdi+40h], 0
0x14000fcd4  jnz     loc_14000FD78
0x14000fcda  cmp     qword ptr [rdi+38h], 0
0x14000fcdf  jnz     short loc_14000FD4E
0x14000fce1  call    cs:__imp_GetLastError
0x14000fce7  xor     r8d, r8d; pcbe
0x14000fcea  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000fcf1  mov     rdx, rdi; pv
0x14000fcf4  mov     r14d, eax
0x14000fcf7  call    cs:__imp_CreateThreadpoolTimer
0x14000fcfd  mov     rbp, [rdi+38h]
0x14000fd01  mov     r15, rax
0x14000fd04  test    rbp, rbp
0x14000fd07  jz      short loc_14000FD41
0x14000fd09  call    cs:__imp_GetLastError
0x14000fd0f  xor     r9d, r9d; msWindowLength
0x14000fd12  xor     r8d, r8d; msPeriod
0x14000fd15  xor     edx, edx; pftDueTime
0x14000fd17  mov     rcx, rbp; pti
0x14000fd1a  mov     ebx, eax
0x14000fd1c  call    cs:__imp_SetThreadpoolTimer
0x14000fd22  mov     edx, 1; fCancelPendingCallbacks
0x14000fd27  mov     rcx, rbp; pti
0x14000fd2a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000fd30  mov     rcx, rbp; pti
0x14000fd33  call    cs:__imp_CloseThreadpoolTimer
0x14000fd39  mov     ecx, ebx; dwErrCode
0x14000fd3b  call    cs:__imp_SetLastError
0x14000fd41  mov     ecx, r14d; dwErrCode
0x14000fd44  mov     [rdi+38h], r15
0x14000fd48  call    cs:__imp_SetLastError
0x14000fd4e  mov     rcx, [rdi+38h]; pti
0x14000fd52  test    rcx, rcx
0x14000fd55  jz      short loc_14000FD78
0x14000fd57  mov     r9d, 4E2h; msWindowLength
0x14000fd5d  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x14000fd66  xor     r8d, r8d; msPeriod
0x14000fd69  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x14000fd6e  call    cs:__imp_SetThreadpoolTimer
0x14000fd74  mov     byte ptr [rdi+40h], 1
0x14000fd78  test    rsi, rsi
0x14000fd7b  jz      short loc_14000FD86
0x14000fd7d  mov     rcx, rsi; SRWLock
0x14000fd80  call    cs:__imp_ReleaseSRWLockExclusive
0x14000fd86  mov     rcx, [rsp+78h+var_40]
0x14000fd8b  xor     rcx, rsp; StackCookie
0x14000fd8e  call    __security_check_cookie
0x14000fd93  add     rsp, 48h
0x14000fd97  pop     r15
0x14000fd99  pop     r14
0x14000fd9b  pop     rdi
0x14000fd9c  pop     rsi
0x14000fd9d  pop     rbp
0x14000fd9e  pop     rbx
0x14000fd9f  retn
```
