# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000c84c`
- end: `0x18000c9e0`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `404`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000dda0`

## callees

- `0x18000c84c`
- `0x180011eec`
- `0x180015010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000c90c`
- `msvcrt!memcpy_s` at `0x18000c90c`
- `KERNEL32!GetLastError` at `0x18000c927`
- `KERNEL32!GetLastError` at `0x18000c94f`
- `KERNEL32!GetLastError` at `0x18000c927`
- `KERNEL32!GetLastError` at `0x18000c94f`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000c93d`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000c93d`
- `KERNEL32!SetThreadpoolTimer` at `0x18000c962`
- `KERNEL32!SetThreadpoolTimer` at `0x18000c9ba`
- `KERNEL32!SetThreadpoolTimer` at `0x18000c962`
- `KERNEL32!SetThreadpoolTimer` at `0x18000c9ba`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000c898`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000c898`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000c979`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000c979`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c9cc`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c9cc`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000c970`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000c970`
- `KERNEL32!SetLastError` at `0x18000c981`
- `KERNEL32!SetLastError` at `0x18000c98e`
- `KERNEL32!SetLastError` at `0x18000c981`
- `KERNEL32!SetLastError` at `0x18000c98e`

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
0x18000c84c  push    rbx
0x18000c84e  push    rbp
0x18000c84f  push    rsi
0x18000c850  push    rdi
0x18000c851  push    r14
0x18000c853  push    r15
0x18000c855  sub     rsp, 38h
0x18000c859  mov     rbx, r8
0x18000c85c  mov     ebp, edx
0x18000c85e  mov     rdi, rcx
0x18000c861  mov     eax, [rcx]
0x18000c863  test    eax, eax
0x18000c865  jz      loc_18000C9D3
0x18000c86b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000c872  jnz     loc_18000C9D3
0x18000c878  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000c87f  test    rax, rax
0x18000c882  jz      short loc_18000C891
0x18000c884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c889  test    al, al
0x18000c88b  jnz     loc_18000C9D3
0x18000c891  lea     rsi, [rdi+8]
0x18000c895  mov     rcx, rsi; SRWLock
0x18000c898  call    cs:__imp_AcquireSRWLockExclusive
0x18000c89e  mov     eax, [rdi]
0x18000c8a0  test    eax, eax
0x18000c8a2  jz      loc_18000C9C4
0x18000c8a8  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000c8af  jnz     loc_18000C9C4
0x18000c8b5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000c8bc  test    rax, rax
0x18000c8bf  jz      short loc_18000C8CE
0x18000c8c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8c6  test    al, al
0x18000c8c8  jnz     loc_18000C9C4
0x18000c8ce  mov     [rsp+68h+Source], ebp
0x18000c8d2  xor     eax, eax
0x18000c8d4  mov     [rsp+68h+var_44], eax
0x18000c8d8  mov     [rsp+68h+var_40], rbx
0x18000c8dd  lea     ebp, [rax+10h]
0x18000c8e0  mov     edx, ebp; unsigned __int64
0x18000c8e2  lea     rcx, [rdi+20h]; this
0x18000c8e6  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000c8eb  test    al, al
0x18000c8ed  jz      short loc_18000C916
0x18000c8ef  mov     rcx, [rdi+28h]; Destination
0x18000c8f3  mov     rax, [rdi+30h]
0x18000c8f7  sub     rax, rcx
0x18000c8fa  cmp     rcx, [rdi+30h]
0x18000c8fe  sbb     rdx, rdx
0x18000c901  and     rdx, rax; DestinationSize
0x18000c904  mov     r9d, ebp; SourceSize
0x18000c907  lea     r8, [rsp+68h+Source]; Source
0x18000c90c  call    cs:__imp_memcpy_s
0x18000c912  add     [rdi+28h], rbp
0x18000c916  cmp     byte ptr [rdi+18h], 0
0x18000c91a  jnz     loc_18000C9C4
0x18000c920  cmp     qword ptr [rdi+10h], 0
0x18000c925  jnz     short loc_18000C994
0x18000c927  call    cs:__imp_GetLastError
0x18000c92d  mov     r14d, eax
0x18000c930  xor     r8d, r8d; pcbe
0x18000c933  mov     rdx, rdi; pv
0x18000c936  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000c93d  call    cs:__imp_CreateThreadpoolTimer
0x18000c943  mov     r15, rax
0x18000c946  mov     rbp, [rdi+10h]
0x18000c94a  test    rbp, rbp
0x18000c94d  jz      short loc_18000C987
0x18000c94f  call    cs:__imp_GetLastError
0x18000c955  mov     ebx, eax
0x18000c957  xor     r9d, r9d; msWindowLength
0x18000c95a  xor     r8d, r8d; msPeriod
0x18000c95d  xor     edx, edx; pftDueTime
0x18000c95f  mov     rcx, rbp; pti
0x18000c962  call    cs:__imp_SetThreadpoolTimer
0x18000c968  mov     edx, 1; fCancelPendingCallbacks
0x18000c96d  mov     rcx, rbp; pti
0x18000c970  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c976  mov     rcx, rbp; pti
0x18000c979  call    cs:__imp_CloseThreadpoolTimer
0x18000c97f  mov     ecx, ebx; dwErrCode
0x18000c981  call    cs:__imp_SetLastError
0x18000c987  mov     [rdi+10h], r15
0x18000c98b  mov     ecx, r14d; dwErrCode
0x18000c98e  call    cs:__imp_SetLastError
0x18000c994  mov     rcx, [rdi+10h]; pti
0x18000c998  test    rcx, rcx
0x18000c99b  jz      short loc_18000C9C4
0x18000c99d  mov     rax, 0FFFFFFFF4D2FA200h
0x18000c9a7  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x18000c9ac  mov     r9d, 124F8h; msWindowLength
0x18000c9b2  xor     r8d, r8d; msPeriod
0x18000c9b5  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000c9ba  call    cs:__imp_SetThreadpoolTimer
0x18000c9c0  mov     byte ptr [rdi+18h], 1
0x18000c9c4  test    rsi, rsi
0x18000c9c7  jz      short loc_18000C9D3
0x18000c9c9  mov     rcx, rsi; SRWLock
0x18000c9cc  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c9d2  nop
0x18000c9d3  add     rsp, 38h
0x18000c9d7  pop     r15
0x18000c9d9  pop     r14
0x18000c9db  pop     rdi
0x18000c9dc  pop     rsi
0x18000c9dd  pop     rbp
0x18000c9de  pop     rbx
0x18000c9df  retn
```
