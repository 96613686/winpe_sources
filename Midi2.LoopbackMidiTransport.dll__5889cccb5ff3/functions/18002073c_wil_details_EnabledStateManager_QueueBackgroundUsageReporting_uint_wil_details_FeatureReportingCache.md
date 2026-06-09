# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18002073c`
- end: `0x1800208a5`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `361`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180020bdc`

## callees

- `0x18002073c`
- `0x180021770`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020891`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020891`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020788`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020788`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020846`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020853`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020846`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800207ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800207ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020814`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002083e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002083e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180020835`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180020835`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180020827`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002087f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180020827`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002087f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180020802`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180020802`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  unsigned __int64 v6; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v10; // ebx
  struct _TP_TIMER *v11; // rcx
  _DWORD v12[2]; // [rsp+20h] [rbp-48h] BYREF
  struct wil_details_FeatureReportingCache *v13; // [rsp+28h] [rbp-40h]
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
      v12[0] = a2;
      v12[1] = 0;
      v13 = a3;
      wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v12, v6);
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
            v10 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v10);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v11 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v11 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v11, &pftDueTime, 0, 0x124F8u);
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
0x18002073c  push    rbx
0x18002073e  push    rbp
0x18002073f  push    rsi
0x180020740  push    rdi
0x180020741  push    r14
0x180020743  push    r15
0x180020745  sub     rsp, 38h
0x180020749  mov     rbx, r8
0x18002074c  mov     ebp, edx
0x18002074e  mov     rdi, rcx
0x180020751  mov     eax, [rcx]
0x180020753  test    eax, eax
0x180020755  jz      loc_180020898
0x18002075b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180020762  jnz     loc_180020898
0x180020768  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18002076f  test    rax, rax
0x180020772  jz      short loc_180020781
0x180020774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020779  test    al, al
0x18002077b  jnz     loc_180020898
0x180020781  lea     rsi, [rdi+8]
0x180020785  mov     rcx, rsi; SRWLock
0x180020788  call    cs:__imp_AcquireSRWLockExclusive
0x18002078e  mov     eax, [rdi]
0x180020790  test    eax, eax
0x180020792  jz      loc_180020889
0x180020798  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18002079f  jnz     loc_180020889
0x1800207a5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800207ac  test    rax, rax
0x1800207af  jz      short loc_1800207BE
0x1800207b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207b6  test    al, al
0x1800207b8  jnz     loc_180020889
0x1800207be  mov     [rsp+68h+var_48], ebp
0x1800207c2  xor     eax, eax
0x1800207c4  mov     [rsp+68h+var_44], eax
0x1800207c8  mov     [rsp+68h+var_40], rbx
0x1800207cd  lea     rcx, [rdi+20h]; this
0x1800207d1  lea     rdx, [rsp+68h+var_48]; void *
0x1800207d6  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800207db  cmp     byte ptr [rdi+18h], 0
0x1800207df  jnz     loc_180020889
0x1800207e5  cmp     qword ptr [rdi+10h], 0
0x1800207ea  jnz     short loc_180020859
0x1800207ec  call    cs:__imp_GetLastError
0x1800207f2  mov     r14d, eax
0x1800207f5  xor     r8d, r8d; pcbe
0x1800207f8  mov     rdx, rdi; pv
0x1800207fb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180020802  call    cs:__imp_CreateThreadpoolTimer
0x180020808  mov     r15, rax
0x18002080b  mov     rbp, [rdi+10h]
0x18002080f  test    rbp, rbp
0x180020812  jz      short loc_18002084C
0x180020814  call    cs:__imp_GetLastError
0x18002081a  mov     ebx, eax
0x18002081c  xor     r9d, r9d; msWindowLength
0x18002081f  xor     r8d, r8d; msPeriod
0x180020822  xor     edx, edx; pftDueTime
0x180020824  mov     rcx, rbp; pti
0x180020827  call    cs:__imp_SetThreadpoolTimer
0x18002082d  mov     edx, 1; fCancelPendingCallbacks
0x180020832  mov     rcx, rbp; pti
0x180020835  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002083b  mov     rcx, rbp; pti
0x18002083e  call    cs:__imp_CloseThreadpoolTimer
0x180020844  mov     ecx, ebx; dwErrCode
0x180020846  call    cs:__imp_SetLastError
0x18002084c  mov     [rdi+10h], r15
0x180020850  mov     ecx, r14d; dwErrCode
0x180020853  call    cs:__imp_SetLastError
0x180020859  mov     rcx, [rdi+10h]; pti
0x18002085d  test    rcx, rcx
0x180020860  jz      short loc_180020889
0x180020862  mov     rax, 0FFFFFFFF4D2FA200h
0x18002086c  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x180020871  mov     r9d, 124F8h; msWindowLength
0x180020877  xor     r8d, r8d; msPeriod
0x18002087a  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18002087f  call    cs:__imp_SetThreadpoolTimer
0x180020885  mov     byte ptr [rdi+18h], 1
0x180020889  test    rsi, rsi
0x18002088c  jz      short loc_180020898
0x18002088e  mov     rcx, rsi; SRWLock
0x180020891  call    cs:__imp_ReleaseSRWLockExclusive
0x180020897  nop
0x180020898  add     rsp, 38h
0x18002089c  pop     r15
0x18002089e  pop     r14
0x1800208a0  pop     rdi
0x1800208a1  pop     rsi
0x1800208a2  pop     rbp
0x1800208a3  pop     rbx
0x1800208a4  retn
```
