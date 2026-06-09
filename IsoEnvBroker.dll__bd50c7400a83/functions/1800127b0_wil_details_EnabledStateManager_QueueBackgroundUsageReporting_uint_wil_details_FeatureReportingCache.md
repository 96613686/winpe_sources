# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1800127b0`
- end: `0x180012968`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180013024`

## callees

- `0x18000302e`
- `0x1800030d0`
- `0x18000bebc`
- `0x1800127b0`
- `0x180068010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180012861`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180012889`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180012861`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180012889`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012954`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012954`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800127fd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800127fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800128af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800128d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800128af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800128d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012909`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012916`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012909`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012916`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800128ea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012942`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800128ea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012942`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012901`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012901`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800128f8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800128f8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800128c5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800128c5`

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
  __int64 v9; // rdx
  __int64 v10; // rcx
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v14; // ebx
  struct _TP_TIMER *v15; // rcx
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
                              (PTP_TIMER_CALLBACK)`wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          Ptr = (struct _TP_TIMER *)pv[2].Ptr;
          if ( Ptr )
          {
            v14 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v14);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v15 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v15 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v15, &pftDueTime, 0, 0x124F8u);
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
      *(_DWORD *)_o__errno(v10, v9) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0, v6) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x1800127b0  push    rbx
0x1800127b2  push    rbp
0x1800127b3  push    rsi
0x1800127b4  push    rdi
0x1800127b5  push    r14
0x1800127b7  push    r15
0x1800127b9  sub     rsp, 28h
0x1800127bd  mov     rbp, r8
0x1800127c0  mov     r14d, edx
0x1800127c3  mov     rdi, rcx
0x1800127c6  mov     eax, [rcx]
0x1800127c8  test    eax, eax
0x1800127ca  jz      loc_18001295B
0x1800127d0  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800127d7  jnz     loc_18001295B
0x1800127dd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800127e4  test    rax, rax
0x1800127e7  jz      short loc_1800127F6
0x1800127e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127ee  test    al, al
0x1800127f0  jnz     loc_18001295B
0x1800127f6  lea     rsi, [rdi+8]
0x1800127fa  mov     rcx, rsi; SRWLock
0x1800127fd  call    cs:__imp_AcquireSRWLockExclusive
0x180012803  mov     eax, [rdi]
0x180012805  test    eax, eax
0x180012807  jz      loc_18001294C
0x18001280d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180012814  jnz     loc_18001294C
0x18001281a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180012821  test    rax, rax
0x180012824  jz      short loc_180012833
0x180012826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001282b  test    al, al
0x18001282d  jnz     loc_18001294C
0x180012833  xor     r15d, r15d
0x180012836  lea     edx, [r15+10h]; unsigned __int64
0x18001283a  lea     rcx, [rdi+20h]; this
0x18001283e  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180012843  test    al, al
0x180012845  jz      short loc_18001289F
0x180012847  mov     rcx, [rdi+28h]; void *
0x18001284b  mov     rax, [rdi+30h]
0x18001284f  sub     rax, rcx
0x180012852  cmp     rcx, [rdi+30h]
0x180012856  sbb     r8, r8
0x180012859  and     r8, rax; Size
0x18001285c  test    rcx, rcx
0x18001285f  jnz     short loc_18001286F
0x180012861  call    cs:__imp__o__errno
0x180012867  mov     dword ptr [rax], 16h
0x18001286d  jmp     short loc_180012895
0x18001286f  cmp     r8, 10h
0x180012873  jb      short loc_180012882
0x180012875  mov     [rcx], r14d
0x180012878  mov     [rcx+4], r15d
0x18001287c  mov     [rcx+8], rbp
0x180012880  jmp     short loc_18001289A
0x180012882  xor     edx, edx; Val
0x180012884  call    memset_0
0x180012889  call    cs:__imp__o__errno
0x18001288f  mov     dword ptr [rax], 22h ; '"'
0x180012895  call    _invalid_parameter_noinfo
0x18001289a  add     qword ptr [rdi+28h], 10h
0x18001289f  cmp     [rdi+18h], r15b
0x1800128a3  jnz     loc_18001294C
0x1800128a9  cmp     [rdi+10h], r15
0x1800128ad  jnz     short loc_18001291C
0x1800128af  call    cs:__imp_GetLastError
0x1800128b5  mov     r14d, eax
0x1800128b8  xor     r8d, r8d; pcbe
0x1800128bb  mov     rdx, rdi; pv
0x1800128be  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800128c5  call    cs:__imp_CreateThreadpoolTimer
0x1800128cb  mov     r15, rax
0x1800128ce  mov     rbp, [rdi+10h]
0x1800128d2  test    rbp, rbp
0x1800128d5  jz      short loc_18001290F
0x1800128d7  call    cs:__imp_GetLastError
0x1800128dd  mov     ebx, eax
0x1800128df  xor     r9d, r9d; msWindowLength
0x1800128e2  xor     r8d, r8d; msPeriod
0x1800128e5  xor     edx, edx; pftDueTime
0x1800128e7  mov     rcx, rbp; pti
0x1800128ea  call    cs:__imp_SetThreadpoolTimer
0x1800128f0  mov     edx, 1; fCancelPendingCallbacks
0x1800128f5  mov     rcx, rbp; pti
0x1800128f8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800128fe  mov     rcx, rbp; pti
0x180012901  call    cs:__imp_CloseThreadpoolTimer
0x180012907  mov     ecx, ebx; dwErrCode
0x180012909  call    cs:__imp_SetLastError
0x18001290f  mov     [rdi+10h], r15
0x180012913  mov     ecx, r14d; dwErrCode
0x180012916  call    cs:__imp_SetLastError
0x18001291c  mov     rcx, [rdi+10h]; pti
0x180012920  test    rcx, rcx
0x180012923  jz      short loc_18001294C
0x180012925  mov     rax, 0FFFFFFFF4D2FA200h
0x18001292f  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x180012934  mov     r9d, 124F8h; msWindowLength
0x18001293a  xor     r8d, r8d; msPeriod
0x18001293d  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180012942  call    cs:__imp_SetThreadpoolTimer
0x180012948  mov     byte ptr [rdi+18h], 1
0x18001294c  test    rsi, rsi
0x18001294f  jz      short loc_18001295B
0x180012951  mov     rcx, rsi; SRWLock
0x180012954  call    cs:__imp_ReleaseSRWLockExclusive
0x18001295a  nop
0x18001295b  add     rsp, 28h
0x18001295f  pop     r15
0x180012961  pop     r14
0x180012963  pop     rdi
0x180012964  pop     rsi
0x180012965  pop     rbp
0x180012966  pop     rbx
0x180012967  retn
```
