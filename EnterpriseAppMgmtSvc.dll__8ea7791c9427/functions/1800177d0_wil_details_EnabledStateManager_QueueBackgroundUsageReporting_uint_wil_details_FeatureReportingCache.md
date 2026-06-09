# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1800177d0`
- end: `0x180017964`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `404`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180017fa8`

## callees

- `0x18000e2cc`
- `0x1800177d0`
- `0x18006a010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180017890`
- `msvcrt!memcpy_s` at `0x180017890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800178ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800178d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800178ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800178d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017905`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017912`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017905`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017912`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017950`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017950`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001781c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001781c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800178fd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800178fd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800178c1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800178c1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800178e6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001793e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800178e6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001793e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800178f4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800178f4`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v9; // ebx
  struct _TP_TIMER *v10; // rcx
  _DWORD Source[2]; // [rsp+20h] [rbp-48h] BYREF
  struct wil_details_FeatureReportingCache *v12; // [rsp+28h] [rbp-40h]
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
      v12 = a3;
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
            v9 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v9);
          }
          pv[2].Ptr = ThreadpoolTimer;
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
0x1800177d0  push    rbx
0x1800177d2  push    rbp
0x1800177d3  push    rsi
0x1800177d4  push    rdi
0x1800177d5  push    r14
0x1800177d7  push    r15
0x1800177d9  sub     rsp, 38h
0x1800177dd  mov     rbx, r8
0x1800177e0  mov     ebp, edx
0x1800177e2  mov     rdi, rcx
0x1800177e5  mov     eax, [rcx]
0x1800177e7  test    eax, eax
0x1800177e9  jz      loc_180017957
0x1800177ef  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800177f6  jnz     loc_180017957
0x1800177fc  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180017803  test    rax, rax
0x180017806  jz      short loc_180017815
0x180017808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001780d  test    al, al
0x18001780f  jnz     loc_180017957
0x180017815  lea     rsi, [rdi+8]
0x180017819  mov     rcx, rsi; SRWLock
0x18001781c  call    cs:__imp_AcquireSRWLockExclusive
0x180017822  mov     eax, [rdi]
0x180017824  test    eax, eax
0x180017826  jz      loc_180017948
0x18001782c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180017833  jnz     loc_180017948
0x180017839  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180017840  test    rax, rax
0x180017843  jz      short loc_180017852
0x180017845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001784a  test    al, al
0x18001784c  jnz     loc_180017948
0x180017852  mov     [rsp+68h+Source], ebp
0x180017856  xor     eax, eax
0x180017858  mov     [rsp+68h+var_44], eax
0x18001785c  mov     [rsp+68h+var_40], rbx
0x180017861  lea     ebp, [rax+10h]
0x180017864  mov     edx, ebp; unsigned __int64
0x180017866  lea     rcx, [rdi+20h]; this
0x18001786a  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001786f  test    al, al
0x180017871  jz      short loc_18001789A
0x180017873  mov     rcx, [rdi+28h]; Destination
0x180017877  mov     rax, [rdi+30h]
0x18001787b  sub     rax, rcx
0x18001787e  cmp     rcx, [rdi+30h]
0x180017882  sbb     rdx, rdx
0x180017885  and     rdx, rax; DestinationSize
0x180017888  mov     r9d, ebp; SourceSize
0x18001788b  lea     r8, [rsp+68h+Source]; Source
0x180017890  call    cs:__imp_memcpy_s
0x180017896  add     [rdi+28h], rbp
0x18001789a  cmp     byte ptr [rdi+18h], 0
0x18001789e  jnz     loc_180017948
0x1800178a4  cmp     qword ptr [rdi+10h], 0
0x1800178a9  jnz     short loc_180017918
0x1800178ab  call    cs:__imp_GetLastError
0x1800178b1  mov     r14d, eax
0x1800178b4  xor     r8d, r8d; pcbe
0x1800178b7  mov     rdx, rdi; pv
0x1800178ba  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800178c1  call    cs:__imp_CreateThreadpoolTimer
0x1800178c7  mov     r15, rax
0x1800178ca  mov     rbp, [rdi+10h]
0x1800178ce  test    rbp, rbp
0x1800178d1  jz      short loc_18001790B
0x1800178d3  call    cs:__imp_GetLastError
0x1800178d9  mov     ebx, eax
0x1800178db  xor     r9d, r9d; msWindowLength
0x1800178de  xor     r8d, r8d; msPeriod
0x1800178e1  xor     edx, edx; pftDueTime
0x1800178e3  mov     rcx, rbp; pti
0x1800178e6  call    cs:__imp_SetThreadpoolTimer
0x1800178ec  mov     edx, 1; fCancelPendingCallbacks
0x1800178f1  mov     rcx, rbp; pti
0x1800178f4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800178fa  mov     rcx, rbp; pti
0x1800178fd  call    cs:__imp_CloseThreadpoolTimer
0x180017903  mov     ecx, ebx; dwErrCode
0x180017905  call    cs:__imp_SetLastError
0x18001790b  mov     [rdi+10h], r15
0x18001790f  mov     ecx, r14d; dwErrCode
0x180017912  call    cs:__imp_SetLastError
0x180017918  mov     rcx, [rdi+10h]; pti
0x18001791c  test    rcx, rcx
0x18001791f  jz      short loc_180017948
0x180017921  mov     rax, 0FFFFFFFF4D2FA200h
0x18001792b  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x180017930  mov     r9d, 124F8h; msWindowLength
0x180017936  xor     r8d, r8d; msPeriod
0x180017939  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18001793e  call    cs:__imp_SetThreadpoolTimer
0x180017944  mov     byte ptr [rdi+18h], 1
0x180017948  test    rsi, rsi
0x18001794b  jz      short loc_180017957
0x18001794d  mov     rcx, rsi; SRWLock
0x180017950  call    cs:__imp_ReleaseSRWLockExclusive
0x180017956  nop
0x180017957  add     rsp, 38h
0x18001795b  pop     r15
0x18001795d  pop     r14
0x18001795f  pop     rdi
0x180017960  pop     rsi
0x180017961  pop     rbp
0x180017962  pop     rbx
0x180017963  retn
```
