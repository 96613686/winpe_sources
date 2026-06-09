# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1800162e0`
- end: `0x1800164a1`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `449`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180017760`

## callees

- `0x18000425e`
- `0x180004418`
- `0x18000ce3c`
- `0x1800162e0`
- `0x1801c3010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001639a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800163c2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001639a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800163c2`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800163fe`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800163fe`
- `KERNEL32!CloseThreadpoolTimer` at `0x18001643a`
- `KERNEL32!CloseThreadpoolTimer` at `0x18001643a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180016431`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180016431`
- `KERNEL32!SetThreadpoolTimer` at `0x180016423`
- `KERNEL32!SetThreadpoolTimer` at `0x18001647b`
- `KERNEL32!SetThreadpoolTimer` at `0x180016423`
- `KERNEL32!SetThreadpoolTimer` at `0x18001647b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180016336`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180016336`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001648d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001648d`
- `KERNEL32!SetLastError` at `0x180016442`
- `KERNEL32!SetLastError` at `0x18001644f`
- `KERNEL32!SetLastError` at `0x180016442`
- `KERNEL32!SetLastError` at `0x18001644f`
- `KERNEL32!GetLastError` at `0x1800163e8`
- `KERNEL32!GetLastError` at `0x180016410`
- `KERNEL32!GetLastError` at `0x1800163e8`
- `KERNEL32!GetLastError` at `0x180016410`

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
0x1800162e0  push    rbx
0x1800162e2  push    rbp
0x1800162e3  push    rsi
0x1800162e4  push    rdi
0x1800162e5  push    r14
0x1800162e7  push    r15
0x1800162e9  sub     rsp, 38h
0x1800162ed  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x1800162f6  mov     rbp, r8
0x1800162f9  mov     r14d, edx
0x1800162fc  mov     rdi, rcx
0x1800162ff  mov     eax, [rcx]
0x180016301  test    eax, eax
0x180016303  jz      loc_180016494
0x180016309  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180016310  jnz     loc_180016494
0x180016316  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001631d  test    rax, rax
0x180016320  jz      short loc_18001632F
0x180016322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016327  test    al, al
0x180016329  jnz     loc_180016494
0x18001632f  lea     rsi, [rdi+8]
0x180016333  mov     rcx, rsi; SRWLock
0x180016336  call    cs:__imp_AcquireSRWLockExclusive
0x18001633c  mov     eax, [rdi]
0x18001633e  test    eax, eax
0x180016340  jz      loc_180016485
0x180016346  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001634d  jnz     loc_180016485
0x180016353  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001635a  test    rax, rax
0x18001635d  jz      short loc_18001636C
0x18001635f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016364  test    al, al
0x180016366  jnz     loc_180016485
0x18001636c  xor     r15d, r15d
0x18001636f  lea     edx, [r15+10h]; unsigned __int64
0x180016373  lea     rcx, [rdi+20h]; this
0x180016377  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001637c  test    al, al
0x18001637e  jz      short loc_1800163D8
0x180016380  mov     rcx, [rdi+28h]; void *
0x180016384  mov     rax, [rdi+30h]
0x180016388  sub     rax, rcx
0x18001638b  cmp     rcx, [rdi+30h]
0x18001638f  sbb     r8, r8
0x180016392  and     r8, rax; Size
0x180016395  test    rcx, rcx
0x180016398  jnz     short loc_1800163A8
0x18001639a  call    cs:__imp__o__errno
0x1800163a0  mov     dword ptr [rax], 16h
0x1800163a6  jmp     short loc_1800163CE
0x1800163a8  cmp     r8, 10h
0x1800163ac  jb      short loc_1800163BB
0x1800163ae  mov     [rcx], r14d
0x1800163b1  mov     [rcx+4], r15d
0x1800163b5  mov     [rcx+8], rbp
0x1800163b9  jmp     short loc_1800163D3
0x1800163bb  xor     edx, edx; Val
0x1800163bd  call    memset_0
0x1800163c2  call    cs:__imp__o__errno
0x1800163c8  mov     dword ptr [rax], 22h ; '"'
0x1800163ce  call    _invalid_parameter_noinfo
0x1800163d3  add     qword ptr [rdi+28h], 10h
0x1800163d8  cmp     [rdi+18h], r15b
0x1800163dc  jnz     loc_180016485
0x1800163e2  cmp     [rdi+10h], r15
0x1800163e6  jnz     short loc_180016455
0x1800163e8  call    cs:__imp_GetLastError
0x1800163ee  mov     r14d, eax
0x1800163f1  xor     r8d, r8d; pcbe
0x1800163f4  mov     rdx, rdi; pv
0x1800163f7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800163fe  call    cs:__imp_CreateThreadpoolTimer
0x180016404  mov     r15, rax
0x180016407  mov     rbp, [rdi+10h]
0x18001640b  test    rbp, rbp
0x18001640e  jz      short loc_180016448
0x180016410  call    cs:__imp_GetLastError
0x180016416  mov     ebx, eax
0x180016418  xor     r9d, r9d; msWindowLength
0x18001641b  xor     r8d, r8d; msPeriod
0x18001641e  xor     edx, edx; pftDueTime
0x180016420  mov     rcx, rbp; pti
0x180016423  call    cs:__imp_SetThreadpoolTimer
0x180016429  mov     edx, 1; fCancelPendingCallbacks
0x18001642e  mov     rcx, rbp; pti
0x180016431  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180016437  mov     rcx, rbp; pti
0x18001643a  call    cs:__imp_CloseThreadpoolTimer
0x180016440  mov     ecx, ebx; dwErrCode
0x180016442  call    cs:__imp_SetLastError
0x180016448  mov     [rdi+10h], r15
0x18001644c  mov     ecx, r14d; dwErrCode
0x18001644f  call    cs:__imp_SetLastError
0x180016455  mov     rcx, [rdi+10h]; pti
0x180016459  test    rcx, rcx
0x18001645c  jz      short loc_180016485
0x18001645e  mov     rax, 0FFFFFFFF4D2FA200h
0x180016468  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x18001646d  mov     r9d, 124F8h; msWindowLength
0x180016473  xor     r8d, r8d; msPeriod
0x180016476  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18001647b  call    cs:__imp_SetThreadpoolTimer
0x180016481  mov     byte ptr [rdi+18h], 1
0x180016485  test    rsi, rsi
0x180016488  jz      short loc_180016494
0x18001648a  mov     rcx, rsi; SRWLock
0x18001648d  call    cs:__imp_ReleaseSRWLockExclusive
0x180016493  nop
0x180016494  add     rsp, 38h
0x180016498  pop     r15
0x18001649a  pop     r14
0x18001649c  pop     rdi
0x18001649d  pop     rsi
0x18001649e  pop     rbp
0x18001649f  pop     rbx
0x1800164a0  retn
```
