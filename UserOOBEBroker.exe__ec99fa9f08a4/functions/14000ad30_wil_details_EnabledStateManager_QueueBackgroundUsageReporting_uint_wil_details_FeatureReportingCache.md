# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x14000ad30`
- end: `0x14000aec3`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `403`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000c778`

## callees

- `0x14000ad30`
- `0x14000d7d4`
- `0x14000f010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000ae64`
- `KERNEL32!SetLastError` at `0x14000ae71`
- `KERNEL32!SetLastError` at `0x14000ae64`
- `KERNEL32!SetLastError` at `0x14000ae71`
- `KERNEL32!GetLastError` at `0x14000ae0a`
- `KERNEL32!GetLastError` at `0x14000ae32`
- `KERNEL32!GetLastError` at `0x14000ae0a`
- `KERNEL32!GetLastError` at `0x14000ae32`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000ad7a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000ad7a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000aeaf`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000aeaf`
- `KERNEL32!SetThreadpoolTimer` at `0x14000ae45`
- `KERNEL32!SetThreadpoolTimer` at `0x14000ae9d`
- `KERNEL32!SetThreadpoolTimer` at `0x14000ae45`
- `KERNEL32!SetThreadpoolTimer` at `0x14000ae9d`
- `KERNEL32!CreateThreadpoolTimer` at `0x14000ae20`
- `KERNEL32!CreateThreadpoolTimer` at `0x14000ae20`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000ae53`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000ae53`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000ae5c`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000ae5c`
- `msvcrt!memcpy_s` at `0x14000adef`
- `msvcrt!memcpy_s` at `0x14000adef`

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
      Source[0] = 43788167;
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
0x14000ad30  push    rbx
0x14000ad32  push    rbp
0x14000ad33  push    rsi
0x14000ad34  push    rdi
0x14000ad35  push    r14
0x14000ad37  push    r15
0x14000ad39  sub     rsp, 38h
0x14000ad3d  mov     rbx, r8
0x14000ad40  mov     rdi, rcx
0x14000ad43  mov     eax, [rcx]
0x14000ad45  test    eax, eax
0x14000ad47  jz      loc_14000AEB6
0x14000ad4d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000ad54  jnz     loc_14000AEB6
0x14000ad5a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000ad61  test    rax, rax
0x14000ad64  jz      short loc_14000AD73
0x14000ad66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ad6b  test    al, al
0x14000ad6d  jnz     loc_14000AEB6
0x14000ad73  lea     rsi, [rdi+8]
0x14000ad77  mov     rcx, rsi; SRWLock
0x14000ad7a  call    cs:__imp_AcquireSRWLockExclusive
0x14000ad80  mov     eax, [rdi]
0x14000ad82  test    eax, eax
0x14000ad84  jz      loc_14000AEA7
0x14000ad8a  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000ad91  jnz     loc_14000AEA7
0x14000ad97  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000ad9e  test    rax, rax
0x14000ada1  jz      short loc_14000ADB0
0x14000ada3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ada8  test    al, al
0x14000adaa  jnz     loc_14000AEA7
0x14000adb0  mov     [rsp+68h+Source], 29C2787h
0x14000adb9  mov     [rsp+68h+var_40], rbx
0x14000adbe  mov     ebp, 10h
0x14000adc3  mov     edx, ebp; unsigned __int64
0x14000adc5  lea     rcx, [rdi+20h]; this
0x14000adc9  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000adce  test    al, al
0x14000add0  jz      short loc_14000ADF9
0x14000add2  mov     rcx, [rdi+28h]; Destination
0x14000add6  mov     rax, [rdi+30h]
0x14000adda  sub     rax, rcx
0x14000addd  cmp     rcx, [rdi+30h]
0x14000ade1  sbb     rdx, rdx
0x14000ade4  and     rdx, rax; DestinationSize
0x14000ade7  mov     r9d, ebp; SourceSize
0x14000adea  lea     r8, [rsp+68h+Source]; Source
0x14000adef  call    cs:__imp_memcpy_s
0x14000adf5  add     [rdi+28h], rbp
0x14000adf9  cmp     byte ptr [rdi+18h], 0
0x14000adfd  jnz     loc_14000AEA7
0x14000ae03  cmp     qword ptr [rdi+10h], 0
0x14000ae08  jnz     short loc_14000AE77
0x14000ae0a  call    cs:__imp_GetLastError
0x14000ae10  mov     r14d, eax
0x14000ae13  xor     r8d, r8d; pcbe
0x14000ae16  mov     rdx, rdi; pv
0x14000ae19  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000ae20  call    cs:__imp_CreateThreadpoolTimer
0x14000ae26  mov     r15, rax
0x14000ae29  mov     rbp, [rdi+10h]
0x14000ae2d  test    rbp, rbp
0x14000ae30  jz      short loc_14000AE6A
0x14000ae32  call    cs:__imp_GetLastError
0x14000ae38  mov     ebx, eax
0x14000ae3a  xor     r9d, r9d; msWindowLength
0x14000ae3d  xor     r8d, r8d; msPeriod
0x14000ae40  xor     edx, edx; pftDueTime
0x14000ae42  mov     rcx, rbp; pti
0x14000ae45  call    cs:__imp_SetThreadpoolTimer
0x14000ae4b  mov     edx, 1; fCancelPendingCallbacks
0x14000ae50  mov     rcx, rbp; pti
0x14000ae53  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000ae59  mov     rcx, rbp; pti
0x14000ae5c  call    cs:__imp_CloseThreadpoolTimer
0x14000ae62  mov     ecx, ebx; dwErrCode
0x14000ae64  call    cs:__imp_SetLastError
0x14000ae6a  mov     [rdi+10h], r15
0x14000ae6e  mov     ecx, r14d; dwErrCode
0x14000ae71  call    cs:__imp_SetLastError
0x14000ae77  mov     rcx, [rdi+10h]; pti
0x14000ae7b  test    rcx, rcx
0x14000ae7e  jz      short loc_14000AEA7
0x14000ae80  mov     rax, 0FFFFFFFF4D2FA200h
0x14000ae8a  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x14000ae8f  mov     r9d, 124F8h; msWindowLength
0x14000ae95  xor     r8d, r8d; msPeriod
0x14000ae98  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x14000ae9d  call    cs:__imp_SetThreadpoolTimer
0x14000aea3  mov     byte ptr [rdi+18h], 1
0x14000aea7  test    rsi, rsi
0x14000aeaa  jz      short loc_14000AEB6
0x14000aeac  mov     rcx, rsi; SRWLock
0x14000aeaf  call    cs:__imp_ReleaseSRWLockExclusive
0x14000aeb5  nop
0x14000aeb6  add     rsp, 38h
0x14000aeba  pop     r15
0x14000aebc  pop     r14
0x14000aebe  pop     rdi
0x14000aebf  pop     rsi
0x14000aec0  pop     rbp
0x14000aec1  pop     rbx
0x14000aec2  retn
```
