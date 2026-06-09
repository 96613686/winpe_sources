# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180009988`
- end: `0x180009b1b`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `403`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180009d60`

## callees

- `0x18000835c`
- `0x180009988`
- `0x180017010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180009a48`
- `msvcrt!memcpy_s` at `0x180009a48`
- `KERNEL32!SetLastError` at `0x180009abd`
- `KERNEL32!SetLastError` at `0x180009aca`
- `KERNEL32!SetLastError` at `0x180009abd`
- `KERNEL32!SetLastError` at `0x180009aca`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180009aac`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180009aac`
- `KERNEL32!GetLastError` at `0x180009a63`
- `KERNEL32!GetLastError` at `0x180009a8b`
- `KERNEL32!GetLastError` at `0x180009a63`
- `KERNEL32!GetLastError` at `0x180009a8b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180009b08`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180009b08`
- `KERNEL32!CloseThreadpoolTimer` at `0x180009ab5`
- `KERNEL32!CloseThreadpoolTimer` at `0x180009ab5`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800099d4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800099d4`
- `KERNEL32!SetThreadpoolTimer` at `0x180009a9e`
- `KERNEL32!SetThreadpoolTimer` at `0x180009af6`
- `KERNEL32!SetThreadpoolTimer` at `0x180009a9e`
- `KERNEL32!SetThreadpoolTimer` at `0x180009af6`
- `KERNEL32!CreateThreadpoolTimer` at `0x180009a79`
- `KERNEL32!CreateThreadpoolTimer` at `0x180009a79`

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
0x180009988  push    rbx
0x18000998a  push    rbp
0x18000998b  push    rsi
0x18000998c  push    rdi
0x18000998d  push    r14
0x18000998f  push    r15
0x180009991  sub     rsp, 38h
0x180009995  mov     eax, [rcx]
0x180009997  mov     rbx, r8
0x18000999a  mov     ebp, edx
0x18000999c  mov     rdi, rcx
0x18000999f  test    eax, eax
0x1800099a1  jz      loc_180009B0E
0x1800099a7  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800099ae  jnz     loc_180009B0E
0x1800099b4  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800099bb  test    rax, rax
0x1800099be  jz      short loc_1800099CD
0x1800099c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099c5  test    al, al
0x1800099c7  jnz     loc_180009B0E
0x1800099cd  lea     rsi, [rdi+8]
0x1800099d1  mov     rcx, rsi; SRWLock
0x1800099d4  call    cs:__imp_AcquireSRWLockExclusive
0x1800099da  mov     eax, [rdi]
0x1800099dc  test    eax, eax
0x1800099de  jz      loc_180009B00
0x1800099e4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800099eb  jnz     loc_180009B00
0x1800099f1  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800099f8  test    rax, rax
0x1800099fb  jz      short loc_180009A0A
0x1800099fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a02  test    al, al
0x180009a04  jnz     loc_180009B00
0x180009a0a  xor     eax, eax
0x180009a0c  mov     [rsp+68h+Source], ebp
0x180009a10  lea     rcx, [rdi+20h]; this
0x180009a14  mov     [rsp+68h+var_44], eax
0x180009a18  mov     [rsp+68h+var_40], rbx
0x180009a1d  lea     ebp, [rax+10h]
0x180009a20  mov     edx, ebp; unsigned __int64
0x180009a22  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180009a27  test    al, al
0x180009a29  jz      short loc_180009A52
0x180009a2b  mov     rcx, [rdi+28h]; Destination
0x180009a2f  lea     r8, [rsp+68h+Source]; Source
0x180009a34  mov     rax, [rdi+30h]
0x180009a38  mov     r9d, ebp; SourceSize
0x180009a3b  sub     rax, rcx
0x180009a3e  cmp     rcx, [rdi+30h]
0x180009a42  sbb     rdx, rdx
0x180009a45  and     rdx, rax; DestinationSize
0x180009a48  call    cs:__imp_memcpy_s
0x180009a4e  add     [rdi+28h], rbp
0x180009a52  cmp     byte ptr [rdi+18h], 0
0x180009a56  jnz     loc_180009B00
0x180009a5c  cmp     qword ptr [rdi+10h], 0
0x180009a61  jnz     short loc_180009AD0
0x180009a63  call    cs:__imp_GetLastError
0x180009a69  xor     r8d, r8d; pcbe
0x180009a6c  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180009a73  mov     rdx, rdi; pv
0x180009a76  mov     r14d, eax
0x180009a79  call    cs:__imp_CreateThreadpoolTimer
0x180009a7f  mov     rbp, [rdi+10h]
0x180009a83  mov     r15, rax
0x180009a86  test    rbp, rbp
0x180009a89  jz      short loc_180009AC3
0x180009a8b  call    cs:__imp_GetLastError
0x180009a91  xor     r9d, r9d; msWindowLength
0x180009a94  xor     r8d, r8d; msPeriod
0x180009a97  xor     edx, edx; pftDueTime
0x180009a99  mov     rcx, rbp; pti
0x180009a9c  mov     ebx, eax
0x180009a9e  call    cs:__imp_SetThreadpoolTimer
0x180009aa4  mov     edx, 1; fCancelPendingCallbacks
0x180009aa9  mov     rcx, rbp; pti
0x180009aac  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009ab2  mov     rcx, rbp; pti
0x180009ab5  call    cs:__imp_CloseThreadpoolTimer
0x180009abb  mov     ecx, ebx; dwErrCode
0x180009abd  call    cs:__imp_SetLastError
0x180009ac3  mov     ecx, r14d; dwErrCode
0x180009ac6  mov     [rdi+10h], r15
0x180009aca  call    cs:__imp_SetLastError
0x180009ad0  mov     rcx, [rdi+10h]; pti
0x180009ad4  test    rcx, rcx
0x180009ad7  jz      short loc_180009B00
0x180009ad9  mov     rax, 0FFFFFFFF4D2FA200h
0x180009ae3  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180009ae8  mov     r9d, 124F8h; msWindowLength
0x180009aee  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x180009af3  xor     r8d, r8d; msPeriod
0x180009af6  call    cs:__imp_SetThreadpoolTimer
0x180009afc  mov     byte ptr [rdi+18h], 1
0x180009b00  test    rsi, rsi
0x180009b03  jz      short loc_180009B0E
0x180009b05  mov     rcx, rsi; SRWLock
0x180009b08  call    cs:__imp_ReleaseSRWLockExclusive
0x180009b0e  add     rsp, 38h
0x180009b12  pop     r15
0x180009b14  pop     r14
0x180009b16  pop     rdi
0x180009b17  pop     rsi
0x180009b18  pop     rbp
0x180009b19  pop     rbx
0x180009b1a  retn
```
