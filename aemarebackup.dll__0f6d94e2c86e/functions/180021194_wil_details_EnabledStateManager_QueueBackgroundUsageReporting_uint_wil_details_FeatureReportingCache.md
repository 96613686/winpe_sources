# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180021194`
- end: `0x18002134c`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180021b8c`

## callees

- `0x18000584a`
- `0x180005914`
- `0x18000e69c`
- `0x180021194`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180021245`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002126d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180021245`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002126d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800211e1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800211e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021338`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021338`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800212ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800212fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800212ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800212fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021293`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021293`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212bb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800212ce`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180021326`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800212ce`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180021326`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800212e5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800212e5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800212a9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800212a9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800212dc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800212dc`

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
0x180021194  push    rbx
0x180021196  push    rbp
0x180021197  push    rsi
0x180021198  push    rdi
0x180021199  push    r14
0x18002119b  push    r15
0x18002119d  sub     rsp, 28h
0x1800211a1  mov     rbp, r8
0x1800211a4  mov     r14d, edx
0x1800211a7  mov     rdi, rcx
0x1800211aa  mov     eax, [rcx]
0x1800211ac  test    eax, eax
0x1800211ae  jz      loc_18002133F
0x1800211b4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800211bb  jnz     loc_18002133F
0x1800211c1  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800211c8  test    rax, rax
0x1800211cb  jz      short loc_1800211DA
0x1800211cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211d2  test    al, al
0x1800211d4  jnz     loc_18002133F
0x1800211da  lea     rsi, [rdi+8]
0x1800211de  mov     rcx, rsi; SRWLock
0x1800211e1  call    cs:__imp_AcquireSRWLockExclusive
0x1800211e7  mov     eax, [rdi]
0x1800211e9  test    eax, eax
0x1800211eb  jz      loc_180021330
0x1800211f1  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800211f8  jnz     loc_180021330
0x1800211fe  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180021205  test    rax, rax
0x180021208  jz      short loc_180021217
0x18002120a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002120f  test    al, al
0x180021211  jnz     loc_180021330
0x180021217  xor     r15d, r15d
0x18002121a  lea     edx, [r15+10h]; unsigned __int64
0x18002121e  lea     rcx, [rdi+20h]; this
0x180021222  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180021227  test    al, al
0x180021229  jz      short loc_180021283
0x18002122b  mov     rcx, [rdi+28h]; void *
0x18002122f  mov     rax, [rdi+30h]
0x180021233  sub     rax, rcx
0x180021236  cmp     rcx, [rdi+30h]
0x18002123a  sbb     r8, r8
0x18002123d  and     r8, rax; Size
0x180021240  test    rcx, rcx
0x180021243  jnz     short loc_180021253
0x180021245  call    cs:__imp__o__errno
0x18002124b  mov     dword ptr [rax], 16h
0x180021251  jmp     short loc_180021279
0x180021253  cmp     r8, 10h
0x180021257  jb      short loc_180021266
0x180021259  mov     [rcx], r14d
0x18002125c  mov     [rcx+4], r15d
0x180021260  mov     [rcx+8], rbp
0x180021264  jmp     short loc_18002127E
0x180021266  xor     edx, edx; Val
0x180021268  call    memset_0
0x18002126d  call    cs:__imp__o__errno
0x180021273  mov     dword ptr [rax], 22h ; '"'
0x180021279  call    _invalid_parameter_noinfo
0x18002127e  add     qword ptr [rdi+28h], 10h
0x180021283  cmp     [rdi+18h], r15b
0x180021287  jnz     loc_180021330
0x18002128d  cmp     [rdi+10h], r15
0x180021291  jnz     short loc_180021300
0x180021293  call    cs:__imp_GetLastError
0x180021299  mov     r14d, eax
0x18002129c  xor     r8d, r8d; pcbe
0x18002129f  mov     rdx, rdi; pv
0x1800212a2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800212a9  call    cs:__imp_CreateThreadpoolTimer
0x1800212af  mov     r15, rax
0x1800212b2  mov     rbp, [rdi+10h]
0x1800212b6  test    rbp, rbp
0x1800212b9  jz      short loc_1800212F3
0x1800212bb  call    cs:__imp_GetLastError
0x1800212c1  mov     ebx, eax
0x1800212c3  xor     r9d, r9d; msWindowLength
0x1800212c6  xor     r8d, r8d; msPeriod
0x1800212c9  xor     edx, edx; pftDueTime
0x1800212cb  mov     rcx, rbp; pti
0x1800212ce  call    cs:__imp_SetThreadpoolTimer
0x1800212d4  mov     edx, 1; fCancelPendingCallbacks
0x1800212d9  mov     rcx, rbp; pti
0x1800212dc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800212e2  mov     rcx, rbp; pti
0x1800212e5  call    cs:__imp_CloseThreadpoolTimer
0x1800212eb  mov     ecx, ebx; dwErrCode
0x1800212ed  call    cs:__imp_SetLastError
0x1800212f3  mov     [rdi+10h], r15
0x1800212f7  mov     ecx, r14d; dwErrCode
0x1800212fa  call    cs:__imp_SetLastError
0x180021300  mov     rcx, [rdi+10h]; pti
0x180021304  test    rcx, rcx
0x180021307  jz      short loc_180021330
0x180021309  mov     rax, 0FFFFFFFF4D2FA200h
0x180021313  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x180021318  mov     r9d, 124F8h; msWindowLength
0x18002131e  xor     r8d, r8d; msPeriod
0x180021321  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180021326  call    cs:__imp_SetThreadpoolTimer
0x18002132c  mov     byte ptr [rdi+18h], 1
0x180021330  test    rsi, rsi
0x180021333  jz      short loc_18002133F
0x180021335  mov     rcx, rsi; SRWLock
0x180021338  call    cs:__imp_ReleaseSRWLockExclusive
0x18002133e  nop
0x18002133f  add     rsp, 28h
0x180021343  pop     r15
0x180021345  pop     r14
0x180021347  pop     rdi
0x180021348  pop     rsi
0x180021349  pop     rbp
0x18002134a  pop     rbx
0x18002134b  retn
```
