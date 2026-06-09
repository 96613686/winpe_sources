# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x140007930`
- end: `0x140007ac3`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `403`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400090c0`

## callees

- `0x140007930`
- `0x14000a87c`
- `0x140017010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140007a65`
- `KERNEL32!SetLastError` at `0x140007a72`
- `KERNEL32!SetLastError` at `0x140007a65`
- `KERNEL32!SetLastError` at `0x140007a72`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140007a54`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140007a54`
- `KERNEL32!GetLastError` at `0x140007a0b`
- `KERNEL32!GetLastError` at `0x140007a33`
- `KERNEL32!GetLastError` at `0x140007a0b`
- `KERNEL32!GetLastError` at `0x140007a33`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140007ab0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140007ab0`
- `KERNEL32!CloseThreadpoolTimer` at `0x140007a5d`
- `KERNEL32!CloseThreadpoolTimer` at `0x140007a5d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000797c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000797c`
- `KERNEL32!SetThreadpoolTimer` at `0x140007a46`
- `KERNEL32!SetThreadpoolTimer` at `0x140007a9e`
- `KERNEL32!SetThreadpoolTimer` at `0x140007a46`
- `KERNEL32!SetThreadpoolTimer` at `0x140007a9e`
- `KERNEL32!CreateThreadpoolTimer` at `0x140007a21`
- `KERNEL32!CreateThreadpoolTimer` at `0x140007a21`
- `msvcrt!memcpy_s` at `0x1400079f0`
- `msvcrt!memcpy_s` at `0x1400079f0`

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
0x140007930  push    rbx
0x140007932  push    rbp
0x140007933  push    rsi
0x140007934  push    rdi
0x140007935  push    r14
0x140007937  push    r15
0x140007939  sub     rsp, 38h
0x14000793d  mov     eax, [rcx]
0x14000793f  mov     rbx, r8
0x140007942  mov     ebp, edx
0x140007944  mov     rdi, rcx
0x140007947  test    eax, eax
0x140007949  jz      loc_140007AB6
0x14000794f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140007956  jnz     loc_140007AB6
0x14000795c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140007963  test    rax, rax
0x140007966  jz      short loc_140007975
0x140007968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000796d  test    al, al
0x14000796f  jnz     loc_140007AB6
0x140007975  lea     rsi, [rdi+8]
0x140007979  mov     rcx, rsi; SRWLock
0x14000797c  call    cs:__imp_AcquireSRWLockExclusive
0x140007982  mov     eax, [rdi]
0x140007984  test    eax, eax
0x140007986  jz      loc_140007AA8
0x14000798c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140007993  jnz     loc_140007AA8
0x140007999  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1400079a0  test    rax, rax
0x1400079a3  jz      short loc_1400079B2
0x1400079a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400079aa  test    al, al
0x1400079ac  jnz     loc_140007AA8
0x1400079b2  xor     eax, eax
0x1400079b4  mov     [rsp+68h+Source], ebp
0x1400079b8  lea     rcx, [rdi+20h]; this
0x1400079bc  mov     [rsp+68h+var_44], eax
0x1400079c0  mov     [rsp+68h+var_40], rbx
0x1400079c5  lea     ebp, [rax+10h]
0x1400079c8  mov     edx, ebp; unsigned __int64
0x1400079ca  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1400079cf  test    al, al
0x1400079d1  jz      short loc_1400079FA
0x1400079d3  mov     rcx, [rdi+28h]; Destination
0x1400079d7  lea     r8, [rsp+68h+Source]; Source
0x1400079dc  mov     rax, [rdi+30h]
0x1400079e0  mov     r9d, ebp; SourceSize
0x1400079e3  sub     rax, rcx
0x1400079e6  cmp     rcx, [rdi+30h]
0x1400079ea  sbb     rdx, rdx
0x1400079ed  and     rdx, rax; DestinationSize
0x1400079f0  call    cs:__imp_memcpy_s
0x1400079f6  add     [rdi+28h], rbp
0x1400079fa  cmp     byte ptr [rdi+18h], 0
0x1400079fe  jnz     loc_140007AA8
0x140007a04  cmp     qword ptr [rdi+10h], 0
0x140007a09  jnz     short loc_140007A78
0x140007a0b  call    cs:__imp_GetLastError
0x140007a11  xor     r8d, r8d; pcbe
0x140007a14  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140007a1b  mov     rdx, rdi; pv
0x140007a1e  mov     r14d, eax
0x140007a21  call    cs:__imp_CreateThreadpoolTimer
0x140007a27  mov     rbp, [rdi+10h]
0x140007a2b  mov     r15, rax
0x140007a2e  test    rbp, rbp
0x140007a31  jz      short loc_140007A6B
0x140007a33  call    cs:__imp_GetLastError
0x140007a39  xor     r9d, r9d; msWindowLength
0x140007a3c  xor     r8d, r8d; msPeriod
0x140007a3f  xor     edx, edx; pftDueTime
0x140007a41  mov     rcx, rbp; pti
0x140007a44  mov     ebx, eax
0x140007a46  call    cs:__imp_SetThreadpoolTimer
0x140007a4c  mov     edx, 1; fCancelPendingCallbacks
0x140007a51  mov     rcx, rbp; pti
0x140007a54  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140007a5a  mov     rcx, rbp; pti
0x140007a5d  call    cs:__imp_CloseThreadpoolTimer
0x140007a63  mov     ecx, ebx; dwErrCode
0x140007a65  call    cs:__imp_SetLastError
0x140007a6b  mov     ecx, r14d; dwErrCode
0x140007a6e  mov     [rdi+10h], r15
0x140007a72  call    cs:__imp_SetLastError
0x140007a78  mov     rcx, [rdi+10h]; pti
0x140007a7c  test    rcx, rcx
0x140007a7f  jz      short loc_140007AA8
0x140007a81  mov     rax, 0FFFFFFFF4D2FA200h
0x140007a8b  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x140007a90  mov     r9d, 124F8h; msWindowLength
0x140007a96  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x140007a9b  xor     r8d, r8d; msPeriod
0x140007a9e  call    cs:__imp_SetThreadpoolTimer
0x140007aa4  mov     byte ptr [rdi+18h], 1
0x140007aa8  test    rsi, rsi
0x140007aab  jz      short loc_140007AB6
0x140007aad  mov     rcx, rsi; SRWLock
0x140007ab0  call    cs:__imp_ReleaseSRWLockExclusive
0x140007ab6  add     rsp, 38h
0x140007aba  pop     r15
0x140007abc  pop     r14
0x140007abe  pop     rdi
0x140007abf  pop     rsi
0x140007ac0  pop     rbp
0x140007ac1  pop     rbx
0x140007ac2  retn
```
