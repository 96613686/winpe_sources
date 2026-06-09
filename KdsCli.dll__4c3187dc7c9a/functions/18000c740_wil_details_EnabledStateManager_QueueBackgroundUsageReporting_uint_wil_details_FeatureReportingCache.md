# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000c740`
- end: `0x18000c8d1`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `401`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000cb6c`

## callees

- `0x180001f4c`
- `0x18000c740`
- `0x18000d284`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c873`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c880`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c873`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c880`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c819`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c841`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c819`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c841`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c78a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c78a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c8be`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c8be`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c854`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c8ac`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c854`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c8ac`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c862`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c862`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c82f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c82f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c86b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c86b`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *Ptr; // rbp
  PTP_TIMER v8; // r15
  DWORD v9; // ebx
  struct _TP_TIMER *v10; // rcx
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
      Source[0] = 22235952;
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
          v8 = ThreadpoolTimer;
          if ( Ptr )
          {
            v9 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v9);
          }
          pv[2].Ptr = v8;
          SetLastError(LastError);
        }
        v10 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v10 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v10, &pftDueTime, 0, 0x124F8u);
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
0x18000c740  push    rbx
0x18000c742  push    rbp
0x18000c743  push    rsi
0x18000c744  push    rdi
0x18000c745  push    r14
0x18000c747  push    r15
0x18000c749  sub     rsp, 38h
0x18000c74d  mov     eax, [rcx]
0x18000c74f  mov     rbx, r8
0x18000c752  mov     rdi, rcx
0x18000c755  test    eax, eax
0x18000c757  jz      loc_18000C8C4
0x18000c75d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000c764  jnz     loc_18000C8C4
0x18000c76a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000c771  test    rax, rax
0x18000c774  jz      short loc_18000C783
0x18000c776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c77b  test    al, al
0x18000c77d  jnz     loc_18000C8C4
0x18000c783  lea     rsi, [rdi+8]
0x18000c787  mov     rcx, rsi; SRWLock
0x18000c78a  call    cs:__imp_AcquireSRWLockExclusive
0x18000c790  mov     eax, [rdi]
0x18000c792  test    eax, eax
0x18000c794  jz      loc_18000C8B6
0x18000c79a  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000c7a1  jnz     loc_18000C8B6
0x18000c7a7  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000c7ae  test    rax, rax
0x18000c7b1  jz      short loc_18000C7C0
0x18000c7b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7b8  test    al, al
0x18000c7ba  jnz     loc_18000C8B6
0x18000c7c0  mov     ebp, 10h
0x18000c7c5  mov     [rsp+68h+Source], 1534B30h
0x18000c7ce  mov     edx, ebp; unsigned __int64
0x18000c7d0  mov     [rsp+68h+var_40], rbx
0x18000c7d5  lea     rcx, [rdi+20h]; this
0x18000c7d9  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000c7de  test    al, al
0x18000c7e0  jz      short loc_18000C808
0x18000c7e2  mov     rcx, [rdi+28h]; Destination
0x18000c7e6  lea     r8, [rsp+68h+Source]; Source
0x18000c7eb  mov     rax, [rdi+30h]
0x18000c7ef  mov     r9d, ebp; SourceSize
0x18000c7f2  sub     rax, rcx
0x18000c7f5  cmp     rcx, [rdi+30h]
0x18000c7f9  sbb     rdx, rdx
0x18000c7fc  and     rdx, rax; DestinationSize
0x18000c7ff  call    memcpy_s
0x18000c804  add     [rdi+28h], rbp
0x18000c808  cmp     byte ptr [rdi+18h], 0
0x18000c80c  jnz     loc_18000C8B6
0x18000c812  cmp     qword ptr [rdi+10h], 0
0x18000c817  jnz     short loc_18000C886
0x18000c819  call    cs:__imp_GetLastError
0x18000c81f  xor     r8d, r8d; pcbe
0x18000c822  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000c829  mov     rdx, rdi; pv
0x18000c82c  mov     r14d, eax
0x18000c82f  call    cs:__imp_CreateThreadpoolTimer
0x18000c835  mov     rbp, [rdi+10h]
0x18000c839  mov     r15, rax
0x18000c83c  test    rbp, rbp
0x18000c83f  jz      short loc_18000C879
0x18000c841  call    cs:__imp_GetLastError
0x18000c847  xor     r9d, r9d; msWindowLength
0x18000c84a  xor     r8d, r8d; msPeriod
0x18000c84d  xor     edx, edx; pftDueTime
0x18000c84f  mov     rcx, rbp; pti
0x18000c852  mov     ebx, eax
0x18000c854  call    cs:__imp_SetThreadpoolTimer
0x18000c85a  mov     edx, 1; fCancelPendingCallbacks
0x18000c85f  mov     rcx, rbp; pti
0x18000c862  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c868  mov     rcx, rbp; pti
0x18000c86b  call    cs:__imp_CloseThreadpoolTimer
0x18000c871  mov     ecx, ebx; dwErrCode
0x18000c873  call    cs:__imp_SetLastError
0x18000c879  mov     ecx, r14d; dwErrCode
0x18000c87c  mov     [rdi+10h], r15
0x18000c880  call    cs:__imp_SetLastError
0x18000c886  mov     rcx, [rdi+10h]; pti
0x18000c88a  test    rcx, rcx
0x18000c88d  jz      short loc_18000C8B6
0x18000c88f  mov     rax, 0FFFFFFFF4D2FA200h
0x18000c899  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000c89e  mov     r9d, 124F8h; msWindowLength
0x18000c8a4  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x18000c8a9  xor     r8d, r8d; msPeriod
0x18000c8ac  call    cs:__imp_SetThreadpoolTimer
0x18000c8b2  mov     byte ptr [rdi+18h], 1
0x18000c8b6  test    rsi, rsi
0x18000c8b9  jz      short loc_18000C8C4
0x18000c8bb  mov     rcx, rsi; SRWLock
0x18000c8be  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c8c4  add     rsp, 38h
0x18000c8c8  pop     r15
0x18000c8ca  pop     r14
0x18000c8cc  pop     rdi
0x18000c8cd  pop     rsi
0x18000c8ce  pop     rbp
0x18000c8cf  pop     rbx
0x18000c8d0  retn
```
