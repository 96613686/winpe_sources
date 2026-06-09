# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18002c22c`
- end: `0x18002c3bf`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `403`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, __int64, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002db04`

## callees

- `0x18002c22c`
- `0x1800302f4`
- `0x180037010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18002c2eb`
- `msvcrt!memcpy_s` at `0x18002c2eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c306`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c32e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c306`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c32e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c360`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c36d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c360`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c36d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c3ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c3ab`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c276`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c276`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002c34f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002c34f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002c358`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002c358`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002c341`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002c399`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002c341`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002c399`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002c31c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002c31c`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v8; // ebx
  struct _TP_TIMER *v9; // rcx
  _QWORD Source[9]; // [rsp+20h] [rbp-48h] BYREF
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
      Source[0] = 45690917;
      Source[1] = a3;
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
          if ( Ptr )
          {
            v8 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v8);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v9 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v9 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v9, &pftDueTime, 0, 0x124F8u);
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
0x18002c22c  push    rbx
0x18002c22e  push    rbp
0x18002c22f  push    rsi
0x18002c230  push    rdi
0x18002c231  push    r14
0x18002c233  push    r15
0x18002c235  sub     rsp, 38h
0x18002c239  mov     rbx, r8
0x18002c23c  mov     rdi, rcx
0x18002c23f  mov     eax, [rcx]
0x18002c241  test    eax, eax
0x18002c243  jz      loc_18002C3B2
0x18002c249  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18002c250  jnz     loc_18002C3B2
0x18002c256  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18002c25d  test    rax, rax
0x18002c260  jz      short loc_18002C26F
0x18002c262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c267  test    al, al
0x18002c269  jnz     loc_18002C3B2
0x18002c26f  lea     rsi, [rdi+8]
0x18002c273  mov     rcx, rsi; SRWLock
0x18002c276  call    cs:__imp_AcquireSRWLockExclusive
0x18002c27c  mov     eax, [rdi]
0x18002c27e  test    eax, eax
0x18002c280  jz      loc_18002C3A3
0x18002c286  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18002c28d  jnz     loc_18002C3A3
0x18002c293  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18002c29a  test    rax, rax
0x18002c29d  jz      short loc_18002C2AC
0x18002c29f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2a4  test    al, al
0x18002c2a6  jnz     loc_18002C3A3
0x18002c2ac  mov     [rsp+68h+Source], 2B93025h
0x18002c2b5  mov     [rsp+68h+var_40], rbx
0x18002c2ba  mov     ebp, 10h
0x18002c2bf  mov     edx, ebp; unsigned __int64
0x18002c2c1  lea     rcx, [rdi+20h]; this
0x18002c2c5  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18002c2ca  test    al, al
0x18002c2cc  jz      short loc_18002C2F5
0x18002c2ce  mov     rcx, [rdi+28h]; Destination
0x18002c2d2  mov     rax, [rdi+30h]
0x18002c2d6  sub     rax, rcx
0x18002c2d9  cmp     rcx, [rdi+30h]
0x18002c2dd  sbb     rdx, rdx
0x18002c2e0  and     rdx, rax; DestinationSize
0x18002c2e3  mov     r9d, ebp; SourceSize
0x18002c2e6  lea     r8, [rsp+68h+Source]; Source
0x18002c2eb  call    cs:__imp_memcpy_s
0x18002c2f1  add     [rdi+28h], rbp
0x18002c2f5  cmp     byte ptr [rdi+18h], 0
0x18002c2f9  jnz     loc_18002C3A3
0x18002c2ff  cmp     qword ptr [rdi+10h], 0
0x18002c304  jnz     short loc_18002C373
0x18002c306  call    cs:__imp_GetLastError
0x18002c30c  mov     r14d, eax
0x18002c30f  xor     r8d, r8d; pcbe
0x18002c312  mov     rdx, rdi; pv
0x18002c315  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002c31c  call    cs:__imp_CreateThreadpoolTimer
0x18002c322  mov     r15, rax
0x18002c325  mov     rbp, [rdi+10h]
0x18002c329  test    rbp, rbp
0x18002c32c  jz      short loc_18002C366
0x18002c32e  call    cs:__imp_GetLastError
0x18002c334  mov     ebx, eax
0x18002c336  xor     r9d, r9d; msWindowLength
0x18002c339  xor     r8d, r8d; msPeriod
0x18002c33c  xor     edx, edx; pftDueTime
0x18002c33e  mov     rcx, rbp; pti
0x18002c341  call    cs:__imp_SetThreadpoolTimer
0x18002c347  mov     edx, 1; fCancelPendingCallbacks
0x18002c34c  mov     rcx, rbp; pti
0x18002c34f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002c355  mov     rcx, rbp; pti
0x18002c358  call    cs:__imp_CloseThreadpoolTimer
0x18002c35e  mov     ecx, ebx; dwErrCode
0x18002c360  call    cs:__imp_SetLastError
0x18002c366  mov     [rdi+10h], r15
0x18002c36a  mov     ecx, r14d; dwErrCode
0x18002c36d  call    cs:__imp_SetLastError
0x18002c373  mov     rcx, [rdi+10h]; pti
0x18002c377  test    rcx, rcx
0x18002c37a  jz      short loc_18002C3A3
0x18002c37c  mov     rax, 0FFFFFFFF4D2FA200h
0x18002c386  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x18002c38b  mov     r9d, 124F8h; msWindowLength
0x18002c391  xor     r8d, r8d; msPeriod
0x18002c394  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18002c399  call    cs:__imp_SetThreadpoolTimer
0x18002c39f  mov     byte ptr [rdi+18h], 1
0x18002c3a3  test    rsi, rsi
0x18002c3a6  jz      short loc_18002C3B2
0x18002c3a8  mov     rcx, rsi; SRWLock
0x18002c3ab  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c3b1  nop
0x18002c3b2  add     rsp, 38h
0x18002c3b6  pop     r15
0x18002c3b8  pop     r14
0x18002c3ba  pop     rdi
0x18002c3bb  pop     rsi
0x18002c3bc  pop     rbp
0x18002c3bd  pop     rbx
0x18002c3be  retn
```
