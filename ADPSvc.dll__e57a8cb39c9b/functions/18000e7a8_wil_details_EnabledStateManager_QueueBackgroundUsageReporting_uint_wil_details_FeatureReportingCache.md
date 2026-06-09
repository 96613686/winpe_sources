# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000e7a8`
- end: `0x18000e960`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000ef50`

## callees

- `0x180002c6a`
- `0x180002cf8`
- `0x18000b5ac`
- `0x18000e7a8`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e859`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e881`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e859`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e881`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e94c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e94c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e7f5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e7f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e901`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e90e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e901`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e90e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8cf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e8e2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e93a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e8e2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e93a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000e8bd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000e8bd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e8f0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e8f0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e8f9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e8f9`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  _DWORD *v6; // rcx
  size_t v7; // r8
  __int64 v8; // rcx
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
                              (PTP_TIMER_CALLBACK)`wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
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
    v6 = pv[5].Ptr;
    v7 = ((char *)pv[6].Ptr - (char *)v6) & -(__int64)(v6 < pv[6].Ptr);
    if ( v6 )
    {
      if ( v7 >= 0x10 )
      {
        *v6 = a2;
        v6[1] = 0;
        *((_QWORD *)v6 + 1) = a3;
LABEL_16:
        pv[5].Ptr = (char *)pv[5].Ptr + 16;
        goto LABEL_17;
      }
      memset_0(v6, 0, v7);
      *(_DWORD *)_o__errno(v8) = 34;
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
0x18000e7a8  push    rbx
0x18000e7aa  push    rbp
0x18000e7ab  push    rsi
0x18000e7ac  push    rdi
0x18000e7ad  push    r14
0x18000e7af  push    r15
0x18000e7b1  sub     rsp, 28h
0x18000e7b5  mov     rbp, r8
0x18000e7b8  mov     r14d, edx
0x18000e7bb  mov     rdi, rcx
0x18000e7be  mov     eax, [rcx]
0x18000e7c0  test    eax, eax
0x18000e7c2  jz      loc_18000E953
0x18000e7c8  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000e7cf  jnz     loc_18000E953
0x18000e7d5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000e7dc  test    rax, rax
0x18000e7df  jz      short loc_18000E7EE
0x18000e7e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7e6  test    al, al
0x18000e7e8  jnz     loc_18000E953
0x18000e7ee  lea     rsi, [rdi+8]
0x18000e7f2  mov     rcx, rsi; SRWLock
0x18000e7f5  call    cs:__imp_AcquireSRWLockExclusive
0x18000e7fb  mov     eax, [rdi]
0x18000e7fd  test    eax, eax
0x18000e7ff  jz      loc_18000E944
0x18000e805  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000e80c  jnz     loc_18000E944
0x18000e812  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000e819  test    rax, rax
0x18000e81c  jz      short loc_18000E82B
0x18000e81e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e823  test    al, al
0x18000e825  jnz     loc_18000E944
0x18000e82b  xor     r15d, r15d
0x18000e82e  lea     edx, [r15+10h]; unsigned __int64
0x18000e832  lea     rcx, [rdi+20h]; this
0x18000e836  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000e83b  test    al, al
0x18000e83d  jz      short loc_18000E897
0x18000e83f  mov     rcx, [rdi+28h]; void *
0x18000e843  mov     rax, [rdi+30h]
0x18000e847  sub     rax, rcx
0x18000e84a  cmp     rcx, [rdi+30h]
0x18000e84e  sbb     r8, r8
0x18000e851  and     r8, rax; Size
0x18000e854  test    rcx, rcx
0x18000e857  jnz     short loc_18000E867
0x18000e859  call    cs:__imp__o__errno
0x18000e85f  mov     dword ptr [rax], 16h
0x18000e865  jmp     short loc_18000E88D
0x18000e867  cmp     r8, 10h
0x18000e86b  jb      short loc_18000E87A
0x18000e86d  mov     [rcx], r14d
0x18000e870  mov     [rcx+4], r15d
0x18000e874  mov     [rcx+8], rbp
0x18000e878  jmp     short loc_18000E892
0x18000e87a  xor     edx, edx; Val
0x18000e87c  call    memset_0
0x18000e881  call    cs:__imp__o__errno
0x18000e887  mov     dword ptr [rax], 22h ; '"'
0x18000e88d  call    _invalid_parameter_noinfo
0x18000e892  add     qword ptr [rdi+28h], 10h
0x18000e897  cmp     [rdi+18h], r15b
0x18000e89b  jnz     loc_18000E944
0x18000e8a1  cmp     [rdi+10h], r15
0x18000e8a5  jnz     short loc_18000E914
0x18000e8a7  call    cs:__imp_GetLastError
0x18000e8ad  mov     r14d, eax
0x18000e8b0  xor     r8d, r8d; pcbe
0x18000e8b3  mov     rdx, rdi; pv
0x18000e8b6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000e8bd  call    cs:__imp_CreateThreadpoolTimer
0x18000e8c3  mov     r15, rax
0x18000e8c6  mov     rbp, [rdi+10h]
0x18000e8ca  test    rbp, rbp
0x18000e8cd  jz      short loc_18000E907
0x18000e8cf  call    cs:__imp_GetLastError
0x18000e8d5  mov     ebx, eax
0x18000e8d7  xor     r9d, r9d; msWindowLength
0x18000e8da  xor     r8d, r8d; msPeriod
0x18000e8dd  xor     edx, edx; pftDueTime
0x18000e8df  mov     rcx, rbp; pti
0x18000e8e2  call    cs:__imp_SetThreadpoolTimer
0x18000e8e8  mov     edx, 1; fCancelPendingCallbacks
0x18000e8ed  mov     rcx, rbp; pti
0x18000e8f0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000e8f6  mov     rcx, rbp; pti
0x18000e8f9  call    cs:__imp_CloseThreadpoolTimer
0x18000e8ff  mov     ecx, ebx; dwErrCode
0x18000e901  call    cs:__imp_SetLastError
0x18000e907  mov     [rdi+10h], r15
0x18000e90b  mov     ecx, r14d; dwErrCode
0x18000e90e  call    cs:__imp_SetLastError
0x18000e914  mov     rcx, [rdi+10h]; pti
0x18000e918  test    rcx, rcx
0x18000e91b  jz      short loc_18000E944
0x18000e91d  mov     rax, 0FFFFFFFF4D2FA200h
0x18000e927  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18000e92c  mov     r9d, 124F8h; msWindowLength
0x18000e932  xor     r8d, r8d; msPeriod
0x18000e935  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18000e93a  call    cs:__imp_SetThreadpoolTimer
0x18000e940  mov     byte ptr [rdi+18h], 1
0x18000e944  test    rsi, rsi
0x18000e947  jz      short loc_18000E953
0x18000e949  mov     rcx, rsi; SRWLock
0x18000e94c  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e952  nop
0x18000e953  add     rsp, 28h
0x18000e957  pop     r15
0x18000e959  pop     r14
0x18000e95b  pop     rdi
0x18000e95c  pop     rsi
0x18000e95d  pop     rbp
0x18000e95e  pop     rbx
0x18000e95f  retn
```
