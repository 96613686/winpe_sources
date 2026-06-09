# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000f57c`
- end: `0x18000f73d`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `449`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180010c84`

## callees

- `0x18000916e`
- `0x1800092dc`
- `0x18000f57c`
- `0x180012e6c`
- `0x18021f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f636`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f65e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f636`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f65e`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000f69a`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000f69a`
- `KERNEL32!SetThreadpoolTimer` at `0x18000f6bf`
- `KERNEL32!SetThreadpoolTimer` at `0x18000f717`
- `KERNEL32!SetThreadpoolTimer` at `0x18000f6bf`
- `KERNEL32!SetThreadpoolTimer` at `0x18000f717`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000f5d2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000f5d2`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000f6d6`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000f6d6`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000f729`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000f729`
- `KERNEL32!GetLastError` at `0x18000f684`
- `KERNEL32!GetLastError` at `0x18000f6ac`
- `KERNEL32!GetLastError` at `0x18000f684`
- `KERNEL32!GetLastError` at `0x18000f6ac`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000f6cd`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000f6cd`
- `KERNEL32!SetLastError` at `0x18000f6de`
- `KERNEL32!SetLastError` at `0x18000f6eb`
- `KERNEL32!SetLastError` at `0x18000f6de`
- `KERNEL32!SetLastError` at `0x18000f6eb`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  __int64 v6; // rcx
  _DWORD *v7; // rcx
  size_t v8; // r8
  __int64 v9; // rcx
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v13; // ebx
  struct _TP_TIMER *v14; // rcx
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress(pv)) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( !LODWORD(pv->Ptr)
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress(v6) )
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
            v13 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v13);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v14 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v14 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v14, &pftDueTime, 0, 0x124F8u);
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
      *(_DWORD *)_o__errno(v9) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x18000f57c  push    rbx
0x18000f57e  push    rbp
0x18000f57f  push    rsi
0x18000f580  push    rdi
0x18000f581  push    r14
0x18000f583  push    r15
0x18000f585  sub     rsp, 38h
0x18000f589  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x18000f592  mov     rbp, r8
0x18000f595  mov     r14d, edx
0x18000f598  mov     rdi, rcx
0x18000f59b  mov     eax, [rcx]
0x18000f59d  test    eax, eax
0x18000f59f  jz      loc_18000F730
0x18000f5a5  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000f5ac  jnz     loc_18000F730
0x18000f5b2  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000f5b9  test    rax, rax
0x18000f5bc  jz      short loc_18000F5CB
0x18000f5be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5c3  test    al, al
0x18000f5c5  jnz     loc_18000F730
0x18000f5cb  lea     rsi, [rdi+8]
0x18000f5cf  mov     rcx, rsi; SRWLock
0x18000f5d2  call    cs:__imp_AcquireSRWLockExclusive
0x18000f5d8  mov     eax, [rdi]
0x18000f5da  test    eax, eax
0x18000f5dc  jz      loc_18000F721
0x18000f5e2  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000f5e9  jnz     loc_18000F721
0x18000f5ef  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000f5f6  test    rax, rax
0x18000f5f9  jz      short loc_18000F608
0x18000f5fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f600  test    al, al
0x18000f602  jnz     loc_18000F721
0x18000f608  xor     r15d, r15d
0x18000f60b  lea     edx, [r15+10h]; unsigned __int64
0x18000f60f  lea     rcx, [rdi+20h]; this
0x18000f613  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000f618  test    al, al
0x18000f61a  jz      short loc_18000F674
0x18000f61c  mov     rcx, [rdi+28h]; void *
0x18000f620  mov     rax, [rdi+30h]
0x18000f624  sub     rax, rcx
0x18000f627  cmp     rcx, [rdi+30h]
0x18000f62b  sbb     r8, r8
0x18000f62e  and     r8, rax; Size
0x18000f631  test    rcx, rcx
0x18000f634  jnz     short loc_18000F644
0x18000f636  call    cs:__imp__o__errno
0x18000f63c  mov     dword ptr [rax], 16h
0x18000f642  jmp     short loc_18000F66A
0x18000f644  cmp     r8, 10h
0x18000f648  jb      short loc_18000F657
0x18000f64a  mov     [rcx], r14d
0x18000f64d  mov     [rcx+4], r15d
0x18000f651  mov     [rcx+8], rbp
0x18000f655  jmp     short loc_18000F66F
0x18000f657  xor     edx, edx; Val
0x18000f659  call    memset_0
0x18000f65e  call    cs:__imp__o__errno
0x18000f664  mov     dword ptr [rax], 22h ; '"'
0x18000f66a  call    _invalid_parameter_noinfo
0x18000f66f  add     qword ptr [rdi+28h], 10h
0x18000f674  cmp     [rdi+18h], r15b
0x18000f678  jnz     loc_18000F721
0x18000f67e  cmp     [rdi+10h], r15
0x18000f682  jnz     short loc_18000F6F1
0x18000f684  call    cs:__imp_GetLastError
0x18000f68a  mov     r14d, eax
0x18000f68d  xor     r8d, r8d; pcbe
0x18000f690  mov     rdx, rdi; pv
0x18000f693  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000f69a  call    cs:__imp_CreateThreadpoolTimer
0x18000f6a0  mov     r15, rax
0x18000f6a3  mov     rbp, [rdi+10h]
0x18000f6a7  test    rbp, rbp
0x18000f6aa  jz      short loc_18000F6E4
0x18000f6ac  call    cs:__imp_GetLastError
0x18000f6b2  mov     ebx, eax
0x18000f6b4  xor     r9d, r9d; msWindowLength
0x18000f6b7  xor     r8d, r8d; msPeriod
0x18000f6ba  xor     edx, edx; pftDueTime
0x18000f6bc  mov     rcx, rbp; pti
0x18000f6bf  call    cs:__imp_SetThreadpoolTimer
0x18000f6c5  mov     edx, 1; fCancelPendingCallbacks
0x18000f6ca  mov     rcx, rbp; pti
0x18000f6cd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000f6d3  mov     rcx, rbp; pti
0x18000f6d6  call    cs:__imp_CloseThreadpoolTimer
0x18000f6dc  mov     ecx, ebx; dwErrCode
0x18000f6de  call    cs:__imp_SetLastError
0x18000f6e4  mov     [rdi+10h], r15
0x18000f6e8  mov     ecx, r14d; dwErrCode
0x18000f6eb  call    cs:__imp_SetLastError
0x18000f6f1  mov     rcx, [rdi+10h]; pti
0x18000f6f5  test    rcx, rcx
0x18000f6f8  jz      short loc_18000F721
0x18000f6fa  mov     rax, 0FFFFFFFF4D2FA200h
0x18000f704  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x18000f709  mov     r9d, 124F8h; msWindowLength
0x18000f70f  xor     r8d, r8d; msPeriod
0x18000f712  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000f717  call    cs:__imp_SetThreadpoolTimer
0x18000f71d  mov     byte ptr [rdi+18h], 1
0x18000f721  test    rsi, rsi
0x18000f724  jz      short loc_18000F730
0x18000f726  mov     rcx, rsi; SRWLock
0x18000f729  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f72f  nop
0x18000f730  add     rsp, 38h
0x18000f734  pop     r15
0x18000f736  pop     r14
0x18000f738  pop     rdi
0x18000f739  pop     rsi
0x18000f73a  pop     rbp
0x18000f73b  pop     rbx
0x18000f73c  retn
```
