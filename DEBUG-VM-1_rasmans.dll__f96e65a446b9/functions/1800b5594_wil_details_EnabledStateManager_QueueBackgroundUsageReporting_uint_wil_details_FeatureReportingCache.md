# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1800b5594`
- end: `0x1800b5727`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `403`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800b6cac`

## callees

- `0x1800b5594`
- `0x1800b829c`
- `0x1800e9010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800b5654`
- `msvcrt!memcpy_s` at `0x1800b5654`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b56c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b56d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b56c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b56d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b566f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5697`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b566f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5697`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b5714`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b5714`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b55e0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b55e0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800b56b8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800b56b8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800b56c1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800b56c1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800b5685`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800b5685`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b56aa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b5702`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b56aa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b5702`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *Ptr; // rbp
  PTP_TIMER v9; // r15
  DWORD v10; // ebx
  struct _TP_TIMER *v11; // rcx
  _DWORD Source[2]; // [rsp+20h] [rbp-48h] BYREF
  struct wil_details_FeatureReportingCache *v13; // [rsp+28h] [rbp-40h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( LODWORD(pv->Ptr)
      && !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      Source[0] = a2;
      Source[1] = 0;
      v13 = a3;
      if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[4], 0x10u) )
      {
        memcpy_s(pv[5].Ptr, ((char *)pv[6].Ptr - (char *)pv[5].Ptr) & -(__int64)(pv[5].Ptr < pv[6].Ptr), Source, 0x10u);
        pv[5].Ptr = (char *)pv[5].Ptr + 16;
      }
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
          v9 = ThreadpoolTimer;
          if ( Ptr )
          {
            v10 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v10);
          }
          pv[2].Ptr = v9;
          SetLastError(LastError);
        }
        v11 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v11 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v11, &pftDueTime, 0, 0x124F8u);
          LOBYTE(pv[3].Ptr) = 1;
        }
      }
    }
    if ( pv != (RTL_SRWLOCK *)-8LL )
      ReleaseSRWLockExclusive(pv + 1);
  }
}

```

## disassembly

```asm
0x1800b5594  push    rbx
0x1800b5596  push    rbp
0x1800b5597  push    rsi
0x1800b5598  push    rdi
0x1800b5599  push    r14
0x1800b559b  push    r15
0x1800b559d  sub     rsp, 38h
0x1800b55a1  mov     eax, [rcx]
0x1800b55a3  mov     rbx, r8
0x1800b55a6  mov     ebp, edx
0x1800b55a8  mov     rdi, rcx
0x1800b55ab  test    eax, eax
0x1800b55ad  jz      loc_1800B571A
0x1800b55b3  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800b55ba  jnz     loc_1800B571A
0x1800b55c0  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800b55c7  test    rax, rax
0x1800b55ca  jz      short loc_1800B55D9
0x1800b55cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b55d1  test    al, al
0x1800b55d3  jnz     loc_1800B571A
0x1800b55d9  lea     rsi, [rdi+8]
0x1800b55dd  mov     rcx, rsi; SRWLock
0x1800b55e0  call    cs:__imp_AcquireSRWLockExclusive
0x1800b55e6  mov     eax, [rdi]
0x1800b55e8  test    eax, eax
0x1800b55ea  jz      loc_1800B570C
0x1800b55f0  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800b55f7  jnz     loc_1800B570C
0x1800b55fd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800b5604  test    rax, rax
0x1800b5607  jz      short loc_1800B5616
0x1800b5609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b560e  test    al, al
0x1800b5610  jnz     loc_1800B570C
0x1800b5616  xor     eax, eax
0x1800b5618  mov     [rsp+68h+Source], ebp
0x1800b561c  lea     rcx, [rdi+20h]; this
0x1800b5620  mov     [rsp+68h+var_44], eax
0x1800b5624  mov     [rsp+68h+var_40], rbx
0x1800b5629  lea     ebp, [rax+10h]
0x1800b562c  mov     edx, ebp; unsigned __int64
0x1800b562e  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800b5633  test    al, al
0x1800b5635  jz      short loc_1800B565E
0x1800b5637  mov     rcx, [rdi+28h]; Destination
0x1800b563b  lea     r8, [rsp+68h+Source]; Source
0x1800b5640  mov     rax, [rdi+30h]
0x1800b5644  mov     r9d, ebp; SourceSize
0x1800b5647  sub     rax, rcx
0x1800b564a  cmp     rcx, [rdi+30h]
0x1800b564e  sbb     rdx, rdx
0x1800b5651  and     rdx, rax; DestinationSize
0x1800b5654  call    cs:__imp_memcpy_s
0x1800b565a  add     [rdi+28h], rbp
0x1800b565e  cmp     byte ptr [rdi+18h], 0
0x1800b5662  jnz     loc_1800B570C
0x1800b5668  cmp     qword ptr [rdi+10h], 0
0x1800b566d  jnz     short loc_1800B56DC
0x1800b566f  call    cs:__imp_GetLastError
0x1800b5675  xor     r8d, r8d; pcbe
0x1800b5678  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800b567f  mov     rdx, rdi; pv
0x1800b5682  mov     r14d, eax
0x1800b5685  call    cs:__imp_CreateThreadpoolTimer
0x1800b568b  mov     rbp, [rdi+10h]
0x1800b568f  mov     r15, rax
0x1800b5692  test    rbp, rbp
0x1800b5695  jz      short loc_1800B56CF
0x1800b5697  call    cs:__imp_GetLastError
0x1800b569d  xor     r9d, r9d; msWindowLength
0x1800b56a0  xor     r8d, r8d; msPeriod
0x1800b56a3  xor     edx, edx; pftDueTime
0x1800b56a5  mov     rcx, rbp; pti
0x1800b56a8  mov     ebx, eax
0x1800b56aa  call    cs:__imp_SetThreadpoolTimer
0x1800b56b0  mov     edx, 1; fCancelPendingCallbacks
0x1800b56b5  mov     rcx, rbp; pti
0x1800b56b8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800b56be  mov     rcx, rbp; pti
0x1800b56c1  call    cs:__imp_CloseThreadpoolTimer
0x1800b56c7  mov     ecx, ebx; dwErrCode
0x1800b56c9  call    cs:__imp_SetLastError
0x1800b56cf  mov     ecx, r14d; dwErrCode
0x1800b56d2  mov     [rdi+10h], r15
0x1800b56d6  call    cs:__imp_SetLastError
0x1800b56dc  mov     rcx, [rdi+10h]; pti
0x1800b56e0  test    rcx, rcx
0x1800b56e3  jz      short loc_1800B570C
0x1800b56e5  mov     rax, 0FFFFFFFF4D2FA200h
0x1800b56ef  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x1800b56f4  mov     r9d, 124F8h; msWindowLength
0x1800b56fa  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x1800b56ff  xor     r8d, r8d; msPeriod
0x1800b5702  call    cs:__imp_SetThreadpoolTimer
0x1800b5708  mov     byte ptr [rdi+18h], 1
0x1800b570c  test    rsi, rsi
0x1800b570f  jz      short loc_1800B571A
0x1800b5711  mov     rcx, rsi; SRWLock
0x1800b5714  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b571a  add     rsp, 38h
0x1800b571e  pop     r15
0x1800b5720  pop     r14
0x1800b5722  pop     rdi
0x1800b5723  pop     rsi
0x1800b5724  pop     rbp
0x1800b5725  pop     rbx
0x1800b5726  retn
```
