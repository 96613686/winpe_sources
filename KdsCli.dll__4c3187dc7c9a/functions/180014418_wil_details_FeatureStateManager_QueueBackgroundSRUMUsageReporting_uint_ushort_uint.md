# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180014418`
- end: `0x18001459f`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `391`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800160e0`

## callees

- `0x180001630`
- `0x180001f4c`
- `0x18000d284`
- `0x180014418`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001453a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014547`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001453a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014547`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800144e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014508`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800144e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014508`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014476`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014476`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001457f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001457f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001451b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001456d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001451b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001456d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014529`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014529`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800144f6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800144f6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014532`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014532`

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
0x180014418  push    rbx
0x18001441a  push    rbp
0x18001441b  push    rsi
0x18001441c  push    rdi
0x18001441d  push    r14
0x18001441f  push    r15
0x180014421  sub     rsp, 48h
0x180014425  mov     rax, cs:__security_cookie
0x18001442c  xor     rax, rsp
0x18001442f  mov     [rsp+78h+var_40], rax
0x180014434  cmp     byte ptr [rcx], 0
0x180014437  mov     r14d, r9d
0x18001443a  movzx   ebp, r8w
0x18001443e  mov     ebx, edx
0x180014440  mov     rdi, rcx
0x180014443  jz      loc_180014585
0x180014449  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180014450  jnz     loc_180014585
0x180014456  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001445d  test    rax, rax
0x180014460  jz      short loc_18001446F
0x180014462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014467  test    al, al
0x180014469  jnz     loc_180014585
0x18001446f  lea     rsi, [rdi+28h]
0x180014473  mov     rcx, rsi; SRWLock
0x180014476  call    cs:__imp_AcquireSRWLockExclusive
0x18001447c  xor     eax, eax
0x18001447e  mov     [rsp+78h+Source], ebx
0x180014482  mov     [rsp+78h+var_4C], bp
0x180014487  lea     rbx, [rdi+0E8h]
0x18001448e  mov     rcx, rbx; this
0x180014491  mov     [rsp+78h+var_4A], ax
0x180014496  mov     [rsp+78h+var_48], r14d
0x18001449b  lea     ebp, [rax+0Ch]
0x18001449e  mov     edx, ebp; unsigned __int64
0x1800144a0  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800144a5  test    al, al
0x1800144a7  jz      short loc_1800144CF
0x1800144a9  mov     rcx, [rbx+8]; Destination
0x1800144ad  lea     r8, [rsp+78h+Source]; Source
0x1800144b2  mov     rax, [rbx+10h]
0x1800144b6  mov     r9d, ebp; SourceSize
0x1800144b9  sub     rax, rcx
0x1800144bc  cmp     rcx, [rbx+10h]
0x1800144c0  sbb     rdx, rdx
0x1800144c3  and     rdx, rax; DestinationSize
0x1800144c6  call    memcpy_s
0x1800144cb  add     [rbx+8], rbp
0x1800144cf  cmp     byte ptr [rdi+40h], 0
0x1800144d3  jnz     loc_180014577
0x1800144d9  cmp     qword ptr [rdi+38h], 0
0x1800144de  jnz     short loc_18001454D
0x1800144e0  call    cs:__imp_GetLastError
0x1800144e6  xor     r8d, r8d; pcbe
0x1800144e9  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800144f0  mov     rdx, rdi; pv
0x1800144f3  mov     r14d, eax
0x1800144f6  call    cs:__imp_CreateThreadpoolTimer
0x1800144fc  mov     rbp, [rdi+38h]
0x180014500  mov     r15, rax
0x180014503  test    rbp, rbp
0x180014506  jz      short loc_180014540
0x180014508  call    cs:__imp_GetLastError
0x18001450e  xor     r9d, r9d; msWindowLength
0x180014511  xor     r8d, r8d; msPeriod
0x180014514  xor     edx, edx; pftDueTime
0x180014516  mov     rcx, rbp; pti
0x180014519  mov     ebx, eax
0x18001451b  call    cs:__imp_SetThreadpoolTimer
0x180014521  mov     edx, 1; fCancelPendingCallbacks
0x180014526  mov     rcx, rbp; pti
0x180014529  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001452f  mov     rcx, rbp; pti
0x180014532  call    cs:__imp_CloseThreadpoolTimer
0x180014538  mov     ecx, ebx; dwErrCode
0x18001453a  call    cs:__imp_SetLastError
0x180014540  mov     ecx, r14d; dwErrCode
0x180014543  mov     [rdi+38h], r15
0x180014547  call    cs:__imp_SetLastError
0x18001454d  mov     rcx, [rdi+38h]; pti
0x180014551  test    rcx, rcx
0x180014554  jz      short loc_180014577
0x180014556  mov     r9d, 4E2h; msWindowLength
0x18001455c  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180014565  xor     r8d, r8d; msPeriod
0x180014568  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18001456d  call    cs:__imp_SetThreadpoolTimer
0x180014573  mov     byte ptr [rdi+40h], 1
0x180014577  test    rsi, rsi
0x18001457a  jz      short loc_180014585
0x18001457c  mov     rcx, rsi; SRWLock
0x18001457f  call    cs:__imp_ReleaseSRWLockExclusive
0x180014585  mov     rcx, [rsp+78h+var_40]
0x18001458a  xor     rcx, rsp; StackCookie
0x18001458d  call    __security_check_cookie
0x180014592  add     rsp, 48h
0x180014596  pop     r15
0x180014598  pop     r14
0x18001459a  pop     rdi
0x18001459b  pop     rsi
0x18001459c  pop     rbp
0x18001459d  pop     rbx
0x18001459e  retn
```
