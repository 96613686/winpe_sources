# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180014f74`
- end: `0x18001512b`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `439`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180016424`

## callees

- `0x1800028c8`
- `0x180002928`
- `0x180014f74`
- `0x180018294`
- `0x18001e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180015025`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001504d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180015025`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001504d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014fc1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014fc1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015118`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015118`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800150cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800150da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800150cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800150da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015073`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001509b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015073`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001509b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800150c5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800150c5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800150bc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800150bc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800150ae`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015106`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800150ae`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015106`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180015089`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180015089`

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
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *Ptr; // rbp
  PTP_TIMER v12; // r15
  DWORD v13; // ebx
  struct _TP_TIMER *v14; // rcx
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
          v12 = ThreadpoolTimer;
          if ( Ptr )
          {
            v13 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v13);
          }
          pv[2].Ptr = v12;
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
0x180014f74  push    rbx
0x180014f76  push    rbp
0x180014f77  push    rsi
0x180014f78  push    rdi
0x180014f79  push    r14
0x180014f7b  push    r15
0x180014f7d  sub     rsp, 28h
0x180014f81  mov     eax, [rcx]
0x180014f83  mov     rbp, r8
0x180014f86  mov     r14d, edx
0x180014f89  mov     rdi, rcx
0x180014f8c  test    eax, eax
0x180014f8e  jz      loc_18001511E
0x180014f94  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180014f9b  jnz     loc_18001511E
0x180014fa1  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180014fa8  test    rax, rax
0x180014fab  jz      short loc_180014FBA
0x180014fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fb2  test    al, al
0x180014fb4  jnz     loc_18001511E
0x180014fba  lea     rsi, [rdi+8]
0x180014fbe  mov     rcx, rsi; SRWLock
0x180014fc1  call    cs:__imp_AcquireSRWLockExclusive
0x180014fc7  mov     eax, [rdi]
0x180014fc9  test    eax, eax
0x180014fcb  jz      loc_180015110
0x180014fd1  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180014fd8  jnz     loc_180015110
0x180014fde  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180014fe5  test    rax, rax
0x180014fe8  jz      short loc_180014FF7
0x180014fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fef  test    al, al
0x180014ff1  jnz     loc_180015110
0x180014ff7  xor     r15d, r15d
0x180014ffa  lea     rcx, [rdi+20h]; this
0x180014ffe  lea     edx, [r15+10h]; unsigned __int64
0x180015002  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180015007  test    al, al
0x180015009  jz      short loc_180015063
0x18001500b  mov     rcx, [rdi+28h]; void *
0x18001500f  mov     rax, [rdi+30h]
0x180015013  sub     rax, rcx
0x180015016  cmp     rcx, [rdi+30h]
0x18001501a  sbb     r8, r8
0x18001501d  and     r8, rax; Size
0x180015020  test    rcx, rcx
0x180015023  jnz     short loc_180015033
0x180015025  call    cs:__imp__o__errno
0x18001502b  mov     dword ptr [rax], 16h
0x180015031  jmp     short loc_180015059
0x180015033  cmp     r8, 10h
0x180015037  jb      short loc_180015046
0x180015039  mov     [rcx], r14d
0x18001503c  mov     [rcx+4], r15d
0x180015040  mov     [rcx+8], rbp
0x180015044  jmp     short loc_18001505E
0x180015046  xor     edx, edx; Val
0x180015048  call    memset_0
0x18001504d  call    cs:__imp__o__errno
0x180015053  mov     dword ptr [rax], 22h ; '"'
0x180015059  call    _invalid_parameter_noinfo
0x18001505e  add     qword ptr [rdi+28h], 10h
0x180015063  cmp     [rdi+18h], r15b
0x180015067  jnz     loc_180015110
0x18001506d  cmp     [rdi+10h], r15
0x180015071  jnz     short loc_1800150E0
0x180015073  call    cs:__imp_GetLastError
0x180015079  xor     r8d, r8d; pcbe
0x18001507c  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180015083  mov     rdx, rdi; pv
0x180015086  mov     r14d, eax
0x180015089  call    cs:__imp_CreateThreadpoolTimer
0x18001508f  mov     rbp, [rdi+10h]
0x180015093  mov     r15, rax
0x180015096  test    rbp, rbp
0x180015099  jz      short loc_1800150D3
0x18001509b  call    cs:__imp_GetLastError
0x1800150a1  xor     r9d, r9d; msWindowLength
0x1800150a4  xor     r8d, r8d; msPeriod
0x1800150a7  xor     edx, edx; pftDueTime
0x1800150a9  mov     rcx, rbp; pti
0x1800150ac  mov     ebx, eax
0x1800150ae  call    cs:__imp_SetThreadpoolTimer
0x1800150b4  mov     edx, 1; fCancelPendingCallbacks
0x1800150b9  mov     rcx, rbp; pti
0x1800150bc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800150c2  mov     rcx, rbp; pti
0x1800150c5  call    cs:__imp_CloseThreadpoolTimer
0x1800150cb  mov     ecx, ebx; dwErrCode
0x1800150cd  call    cs:__imp_SetLastError
0x1800150d3  mov     ecx, r14d; dwErrCode
0x1800150d6  mov     [rdi+10h], r15
0x1800150da  call    cs:__imp_SetLastError
0x1800150e0  mov     rcx, [rdi+10h]; pti
0x1800150e4  test    rcx, rcx
0x1800150e7  jz      short loc_180015110
0x1800150e9  mov     rax, 0FFFFFFFF4D2FA200h
0x1800150f3  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x1800150f8  mov     r9d, 124F8h; msWindowLength
0x1800150fe  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x180015103  xor     r8d, r8d; msPeriod
0x180015106  call    cs:__imp_SetThreadpoolTimer
0x18001510c  mov     byte ptr [rdi+18h], 1
0x180015110  test    rsi, rsi
0x180015113  jz      short loc_18001511E
0x180015115  mov     rcx, rsi; SRWLock
0x180015118  call    cs:__imp_ReleaseSRWLockExclusive
0x18001511e  add     rsp, 28h
0x180015122  pop     r15
0x180015124  pop     r14
0x180015126  pop     rdi
0x180015127  pop     rsi
0x180015128  pop     rbp
0x180015129  pop     rbx
0x18001512a  retn
```
