# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180008cb0`
- end: `0x180008e68`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000a7e0`

## callees

- `0x180002f3a`
- `0x180002f98`
- `0x180008cb0`
- `0x18000c6e0`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008d61`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008d89`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008d61`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008d89`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008e09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008e16`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008e09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008e16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008daf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008dd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008daf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008dd7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008cfd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008cfd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008e54`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008e54`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008df8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008df8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008e01`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008e01`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008dc5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008dc5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008dea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008e42`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008dea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008e42`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  __int64 v6; // rdx
  _DWORD *v7; // rcx
  size_t v8; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v12; // ebx
  struct _TP_TIMER *v13; // rcx
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( !LODWORD(pv->Ptr)
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
LABEL_24:
      if ( pv != (RTL_SRWLOCK *)-8LL )
        ReleaseSRWLockExclusive(pv + 1);
      return;
    }
    if ( !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[4], 0x10u) )
    {
LABEL_17:
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
            v12 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v12);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v13 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v13 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v13, &pftDueTime, 0, 0x124F8u);
          LOBYTE(pv[3].Ptr) = 1;
        }
      }
      goto LABEL_24;
    }
    v7 = pv[5].Ptr;
    v8 = ((char *)pv[6].Ptr - (char *)v7) & -(__int64)(v7 < pv[6].Ptr);
    if ( v7 )
    {
      if ( v8 >= 0x10 )
      {
        *v7 = a2;
        v7[1] = 0;
        *((_QWORD *)v7 + 1) = a3;
LABEL_16:
        pv[5].Ptr = (char *)pv[5].Ptr + 16;
        goto LABEL_17;
      }
      memset_0(v7, 0, v8);
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0, v6, v8) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x180008cb0  push    rbx
0x180008cb2  push    rbp
0x180008cb3  push    rsi
0x180008cb4  push    rdi
0x180008cb5  push    r14
0x180008cb7  push    r15
0x180008cb9  sub     rsp, 28h
0x180008cbd  mov     rbp, r8
0x180008cc0  mov     r14d, edx
0x180008cc3  mov     rdi, rcx
0x180008cc6  mov     eax, [rcx]
0x180008cc8  test    eax, eax
0x180008cca  jz      loc_180008E5B
0x180008cd0  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180008cd7  jnz     loc_180008E5B
0x180008cdd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008ce4  test    rax, rax
0x180008ce7  jz      short loc_180008CF6
0x180008ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cee  test    al, al
0x180008cf0  jnz     loc_180008E5B
0x180008cf6  lea     rsi, [rdi+8]
0x180008cfa  mov     rcx, rsi; SRWLock
0x180008cfd  call    cs:__imp_AcquireSRWLockExclusive
0x180008d03  mov     eax, [rdi]
0x180008d05  test    eax, eax
0x180008d07  jz      loc_180008E4C
0x180008d0d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180008d14  jnz     loc_180008E4C
0x180008d1a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008d21  test    rax, rax
0x180008d24  jz      short loc_180008D33
0x180008d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d2b  test    al, al
0x180008d2d  jnz     loc_180008E4C
0x180008d33  xor     r15d, r15d
0x180008d36  lea     edx, [r15+10h]; unsigned __int64
0x180008d3a  lea     rcx, [rdi+20h]; this
0x180008d3e  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180008d43  test    al, al
0x180008d45  jz      short loc_180008D9F
0x180008d47  mov     rcx, [rdi+28h]; void *
0x180008d4b  mov     rax, [rdi+30h]
0x180008d4f  sub     rax, rcx
0x180008d52  cmp     rcx, [rdi+30h]
0x180008d56  sbb     r8, r8
0x180008d59  and     r8, rax; Size
0x180008d5c  test    rcx, rcx
0x180008d5f  jnz     short loc_180008D6F
0x180008d61  call    cs:__imp__o__errno
0x180008d67  mov     dword ptr [rax], 16h
0x180008d6d  jmp     short loc_180008D95
0x180008d6f  cmp     r8, 10h
0x180008d73  jb      short loc_180008D82
0x180008d75  mov     [rcx], r14d
0x180008d78  mov     [rcx+4], r15d
0x180008d7c  mov     [rcx+8], rbp
0x180008d80  jmp     short loc_180008D9A
0x180008d82  xor     edx, edx; Val
0x180008d84  call    memset_0
0x180008d89  call    cs:__imp__o__errno
0x180008d8f  mov     dword ptr [rax], 22h ; '"'
0x180008d95  call    _invalid_parameter_noinfo
0x180008d9a  add     qword ptr [rdi+28h], 10h
0x180008d9f  cmp     [rdi+18h], r15b
0x180008da3  jnz     loc_180008E4C
0x180008da9  cmp     [rdi+10h], r15
0x180008dad  jnz     short loc_180008E1C
0x180008daf  call    cs:__imp_GetLastError
0x180008db5  mov     r14d, eax
0x180008db8  xor     r8d, r8d; pcbe
0x180008dbb  mov     rdx, rdi; pv
0x180008dbe  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180008dc5  call    cs:__imp_CreateThreadpoolTimer
0x180008dcb  mov     r15, rax
0x180008dce  mov     rbp, [rdi+10h]
0x180008dd2  test    rbp, rbp
0x180008dd5  jz      short loc_180008E0F
0x180008dd7  call    cs:__imp_GetLastError
0x180008ddd  mov     ebx, eax
0x180008ddf  xor     r9d, r9d; msWindowLength
0x180008de2  xor     r8d, r8d; msPeriod
0x180008de5  xor     edx, edx; pftDueTime
0x180008de7  mov     rcx, rbp; pti
0x180008dea  call    cs:__imp_SetThreadpoolTimer
0x180008df0  mov     edx, 1; fCancelPendingCallbacks
0x180008df5  mov     rcx, rbp; pti
0x180008df8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008dfe  mov     rcx, rbp; pti
0x180008e01  call    cs:__imp_CloseThreadpoolTimer
0x180008e07  mov     ecx, ebx; dwErrCode
0x180008e09  call    cs:__imp_SetLastError
0x180008e0f  mov     [rdi+10h], r15
0x180008e13  mov     ecx, r14d; dwErrCode
0x180008e16  call    cs:__imp_SetLastError
0x180008e1c  mov     rcx, [rdi+10h]; pti
0x180008e20  test    rcx, rcx
0x180008e23  jz      short loc_180008E4C
0x180008e25  mov     rax, 0FFFFFFFF4D2FA200h
0x180008e2f  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x180008e34  mov     r9d, 124F8h; msWindowLength
0x180008e3a  xor     r8d, r8d; msPeriod
0x180008e3d  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180008e42  call    cs:__imp_SetThreadpoolTimer
0x180008e48  mov     byte ptr [rdi+18h], 1
0x180008e4c  test    rsi, rsi
0x180008e4f  jz      short loc_180008E5B
0x180008e51  mov     rcx, rsi; SRWLock
0x180008e54  call    cs:__imp_ReleaseSRWLockExclusive
0x180008e5a  nop
0x180008e5b  add     rsp, 28h
0x180008e5f  pop     r15
0x180008e61  pop     r14
0x180008e63  pop     rdi
0x180008e64  pop     rsi
0x180008e65  pop     rbp
0x180008e66  pop     rbx
0x180008e67  retn
```
