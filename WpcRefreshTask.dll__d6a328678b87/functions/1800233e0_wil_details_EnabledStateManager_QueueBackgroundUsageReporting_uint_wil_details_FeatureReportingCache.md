# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1800233e0`
- end: `0x180023598`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180023770`

## callees

- `0x180006e3e`
- `0x180006ed4`
- `0x180013a84`
- `0x1800233e0`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180023491`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800234b9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180023491`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800234b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023539`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023546`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023539`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800234df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023507`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800234df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023507`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002342d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002342d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023584`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023584`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180023531`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180023531`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180023528`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180023528`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002351a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180023572`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002351a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180023572`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800234f5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800234f5`

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
0x1800233e0  push    rbx
0x1800233e2  push    rbp
0x1800233e3  push    rsi
0x1800233e4  push    rdi
0x1800233e5  push    r14
0x1800233e7  push    r15
0x1800233e9  sub     rsp, 28h
0x1800233ed  mov     rbp, r8
0x1800233f0  mov     r14d, edx
0x1800233f3  mov     rdi, rcx
0x1800233f6  mov     eax, [rcx]
0x1800233f8  test    eax, eax
0x1800233fa  jz      loc_18002358B
0x180023400  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180023407  jnz     loc_18002358B
0x18002340d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180023414  test    rax, rax
0x180023417  jz      short loc_180023426
0x180023419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002341e  test    al, al
0x180023420  jnz     loc_18002358B
0x180023426  lea     rsi, [rdi+8]
0x18002342a  mov     rcx, rsi; SRWLock
0x18002342d  call    cs:__imp_AcquireSRWLockExclusive
0x180023433  mov     eax, [rdi]
0x180023435  test    eax, eax
0x180023437  jz      loc_18002357C
0x18002343d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180023444  jnz     loc_18002357C
0x18002344a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180023451  test    rax, rax
0x180023454  jz      short loc_180023463
0x180023456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002345b  test    al, al
0x18002345d  jnz     loc_18002357C
0x180023463  xor     r15d, r15d
0x180023466  lea     edx, [r15+10h]; unsigned __int64
0x18002346a  lea     rcx, [rdi+20h]; this
0x18002346e  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180023473  test    al, al
0x180023475  jz      short loc_1800234CF
0x180023477  mov     rcx, [rdi+28h]; void *
0x18002347b  mov     rax, [rdi+30h]
0x18002347f  sub     rax, rcx
0x180023482  cmp     rcx, [rdi+30h]
0x180023486  sbb     r8, r8
0x180023489  and     r8, rax; Size
0x18002348c  test    rcx, rcx
0x18002348f  jnz     short loc_18002349F
0x180023491  call    cs:__imp__o__errno
0x180023497  mov     dword ptr [rax], 16h
0x18002349d  jmp     short loc_1800234C5
0x18002349f  cmp     r8, 10h
0x1800234a3  jb      short loc_1800234B2
0x1800234a5  mov     [rcx], r14d
0x1800234a8  mov     [rcx+4], r15d
0x1800234ac  mov     [rcx+8], rbp
0x1800234b0  jmp     short loc_1800234CA
0x1800234b2  xor     edx, edx; Val
0x1800234b4  call    memset_0
0x1800234b9  call    cs:__imp__o__errno
0x1800234bf  mov     dword ptr [rax], 22h ; '"'
0x1800234c5  call    _invalid_parameter_noinfo
0x1800234ca  add     qword ptr [rdi+28h], 10h
0x1800234cf  cmp     [rdi+18h], r15b
0x1800234d3  jnz     loc_18002357C
0x1800234d9  cmp     [rdi+10h], r15
0x1800234dd  jnz     short loc_18002354C
0x1800234df  call    cs:__imp_GetLastError
0x1800234e5  mov     r14d, eax
0x1800234e8  xor     r8d, r8d; pcbe
0x1800234eb  mov     rdx, rdi; pv
0x1800234ee  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800234f5  call    cs:__imp_CreateThreadpoolTimer
0x1800234fb  mov     r15, rax
0x1800234fe  mov     rbp, [rdi+10h]
0x180023502  test    rbp, rbp
0x180023505  jz      short loc_18002353F
0x180023507  call    cs:__imp_GetLastError
0x18002350d  mov     ebx, eax
0x18002350f  xor     r9d, r9d; msWindowLength
0x180023512  xor     r8d, r8d; msPeriod
0x180023515  xor     edx, edx; pftDueTime
0x180023517  mov     rcx, rbp; pti
0x18002351a  call    cs:__imp_SetThreadpoolTimer
0x180023520  mov     edx, 1; fCancelPendingCallbacks
0x180023525  mov     rcx, rbp; pti
0x180023528  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002352e  mov     rcx, rbp; pti
0x180023531  call    cs:__imp_CloseThreadpoolTimer
0x180023537  mov     ecx, ebx; dwErrCode
0x180023539  call    cs:__imp_SetLastError
0x18002353f  mov     [rdi+10h], r15
0x180023543  mov     ecx, r14d; dwErrCode
0x180023546  call    cs:__imp_SetLastError
0x18002354c  mov     rcx, [rdi+10h]; pti
0x180023550  test    rcx, rcx
0x180023553  jz      short loc_18002357C
0x180023555  mov     rax, 0FFFFFFFF4D2FA200h
0x18002355f  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x180023564  mov     r9d, 124F8h; msWindowLength
0x18002356a  xor     r8d, r8d; msPeriod
0x18002356d  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180023572  call    cs:__imp_SetThreadpoolTimer
0x180023578  mov     byte ptr [rdi+18h], 1
0x18002357c  test    rsi, rsi
0x18002357f  jz      short loc_18002358B
0x180023581  mov     rcx, rsi; SRWLock
0x180023584  call    cs:__imp_ReleaseSRWLockExclusive
0x18002358a  nop
0x18002358b  add     rsp, 28h
0x18002358f  pop     r15
0x180023591  pop     r14
0x180023593  pop     rdi
0x180023594  pop     rsi
0x180023595  pop     rbp
0x180023596  pop     rbx
0x180023597  retn
```
