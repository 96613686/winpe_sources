# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000fd7c`
- end: `0x18000ff34`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001056c`

## callees

- `0x180003f02`
- `0x180003fb8`
- `0x18000c38c`
- `0x18000fd7c`
- `0x180108010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000fe2d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000fe55`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000fe2d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000fe55`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fdc9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fdc9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ff20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ff20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fea3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fea3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fed5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fee2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fed5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fee2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000fecd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000fecd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000feb6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ff0e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000feb6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ff0e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000fe91`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000fe91`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000fec4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000fec4`

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
                              `wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
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
0x18000fd7c  push    rbx
0x18000fd7e  push    rbp
0x18000fd7f  push    rsi
0x18000fd80  push    rdi
0x18000fd81  push    r14
0x18000fd83  push    r15
0x18000fd85  sub     rsp, 28h
0x18000fd89  mov     rbp, r8
0x18000fd8c  mov     r14d, edx
0x18000fd8f  mov     rdi, rcx
0x18000fd92  mov     eax, [rcx]
0x18000fd94  test    eax, eax
0x18000fd96  jz      loc_18000FF27
0x18000fd9c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000fda3  jnz     loc_18000FF27
0x18000fda9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000fdb0  test    rax, rax
0x18000fdb3  jz      short loc_18000FDC2
0x18000fdb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdba  test    al, al
0x18000fdbc  jnz     loc_18000FF27
0x18000fdc2  lea     rsi, [rdi+8]
0x18000fdc6  mov     rcx, rsi; SRWLock
0x18000fdc9  call    cs:__imp_AcquireSRWLockExclusive
0x18000fdcf  mov     eax, [rdi]
0x18000fdd1  test    eax, eax
0x18000fdd3  jz      loc_18000FF18
0x18000fdd9  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000fde0  jnz     loc_18000FF18
0x18000fde6  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000fded  test    rax, rax
0x18000fdf0  jz      short loc_18000FDFF
0x18000fdf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdf7  test    al, al
0x18000fdf9  jnz     loc_18000FF18
0x18000fdff  xor     r15d, r15d
0x18000fe02  lea     edx, [r15+10h]; unsigned __int64
0x18000fe06  lea     rcx, [rdi+20h]; this
0x18000fe0a  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000fe0f  test    al, al
0x18000fe11  jz      short loc_18000FE6B
0x18000fe13  mov     rcx, [rdi+28h]; void *
0x18000fe17  mov     rax, [rdi+30h]
0x18000fe1b  sub     rax, rcx
0x18000fe1e  cmp     rcx, [rdi+30h]
0x18000fe22  sbb     r8, r8
0x18000fe25  and     r8, rax; Size
0x18000fe28  test    rcx, rcx
0x18000fe2b  jnz     short loc_18000FE3B
0x18000fe2d  call    cs:__imp__o__errno
0x18000fe33  mov     dword ptr [rax], 16h
0x18000fe39  jmp     short loc_18000FE61
0x18000fe3b  cmp     r8, 10h
0x18000fe3f  jb      short loc_18000FE4E
0x18000fe41  mov     [rcx], r14d
0x18000fe44  mov     [rcx+4], r15d
0x18000fe48  mov     [rcx+8], rbp
0x18000fe4c  jmp     short loc_18000FE66
0x18000fe4e  xor     edx, edx; Val
0x18000fe50  call    memset_0
0x18000fe55  call    cs:__imp__o__errno
0x18000fe5b  mov     dword ptr [rax], 22h ; '"'
0x18000fe61  call    _invalid_parameter_noinfo
0x18000fe66  add     qword ptr [rdi+28h], 10h
0x18000fe6b  cmp     [rdi+18h], r15b
0x18000fe6f  jnz     loc_18000FF18
0x18000fe75  cmp     [rdi+10h], r15
0x18000fe79  jnz     short loc_18000FEE8
0x18000fe7b  call    cs:__imp_GetLastError
0x18000fe81  mov     r14d, eax
0x18000fe84  xor     r8d, r8d; pcbe
0x18000fe87  mov     rdx, rdi; pv
0x18000fe8a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000fe91  call    cs:__imp_CreateThreadpoolTimer
0x18000fe97  mov     r15, rax
0x18000fe9a  mov     rbp, [rdi+10h]
0x18000fe9e  test    rbp, rbp
0x18000fea1  jz      short loc_18000FEDB
0x18000fea3  call    cs:__imp_GetLastError
0x18000fea9  mov     ebx, eax
0x18000feab  xor     r9d, r9d; msWindowLength
0x18000feae  xor     r8d, r8d; msPeriod
0x18000feb1  xor     edx, edx; pftDueTime
0x18000feb3  mov     rcx, rbp; pti
0x18000feb6  call    cs:__imp_SetThreadpoolTimer
0x18000febc  mov     edx, 1; fCancelPendingCallbacks
0x18000fec1  mov     rcx, rbp; pti
0x18000fec4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000feca  mov     rcx, rbp; pti
0x18000fecd  call    cs:__imp_CloseThreadpoolTimer
0x18000fed3  mov     ecx, ebx; dwErrCode
0x18000fed5  call    cs:__imp_SetLastError
0x18000fedb  mov     [rdi+10h], r15
0x18000fedf  mov     ecx, r14d; dwErrCode
0x18000fee2  call    cs:__imp_SetLastError
0x18000fee8  mov     rcx, [rdi+10h]; pti
0x18000feec  test    rcx, rcx
0x18000feef  jz      short loc_18000FF18
0x18000fef1  mov     rax, 0FFFFFFFF4D2FA200h
0x18000fefb  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18000ff00  mov     r9d, 124F8h; msWindowLength
0x18000ff06  xor     r8d, r8d; msPeriod
0x18000ff09  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18000ff0e  call    cs:__imp_SetThreadpoolTimer
0x18000ff14  mov     byte ptr [rdi+18h], 1
0x18000ff18  test    rsi, rsi
0x18000ff1b  jz      short loc_18000FF27
0x18000ff1d  mov     rcx, rsi; SRWLock
0x18000ff20  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ff26  nop
0x18000ff27  add     rsp, 28h
0x18000ff2b  pop     r15
0x18000ff2d  pop     r14
0x18000ff2f  pop     rdi
0x18000ff30  pop     rsi
0x18000ff31  pop     rbp
0x18000ff32  pop     rbx
0x18000ff33  retn
```
