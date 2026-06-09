# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180019520`
- end: `0x180019658`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `312`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180062664`

## callees

- `0x18000d1d0`
- `0x18000f640`
- `0x180019520`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001963e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001963e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019571`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019571`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019600`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800195d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800195d7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800195ec`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800195ec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001962c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001962c`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  DWORD LastError; // ebx
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *Ptr; // rcx
  _DWORD v9[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v10; // [rsp+28h] [rbp-20h]
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( LODWORD(pv->Ptr)
      && !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      v9[0] = a2;
      v9[1] = 0;
      v10 = a3;
      wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v9, 0x10u);
      if ( !LOBYTE(pv[3].Ptr) )
      {
        if ( !pv[2].Ptr )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              `wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            &pv[2],
            ThreadpoolTimer);
          SetLastError(LastError);
        }
        Ptr = (struct _TP_TIMER *)pv[2].Ptr;
        if ( Ptr )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(Ptr, &pftDueTime, 0, 0x124F8u);
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
0x180019520  mov     [rsp+arg_8], rbx
0x180019525  mov     [rsp+arg_10], rbp
0x18001952a  push    rsi
0x18001952b  push    rdi
0x18001952c  push    r14
0x18001952e  sub     rsp, 30h
0x180019532  mov     rbx, r8
0x180019535  mov     ebp, edx
0x180019537  mov     rdi, rcx
0x18001953a  mov     eax, [rcx]
0x18001953c  test    eax, eax
0x18001953e  jz      loc_180019645
0x180019544  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001954b  jnz     loc_180019645
0x180019551  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180019558  test    rax, rax
0x18001955b  jz      short loc_18001956A
0x18001955d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019562  test    al, al
0x180019564  jnz     loc_180019645
0x18001956a  lea     rsi, [rdi+8]
0x18001956e  mov     rcx, rsi; SRWLock
0x180019571  call    cs:__imp_AcquireSRWLockExclusive
0x180019577  mov     eax, [rdi]
0x180019579  test    eax, eax
0x18001957b  jz      loc_180019636
0x180019581  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180019588  jnz     loc_180019636
0x18001958e  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180019595  test    rax, rax
0x180019598  jz      short loc_1800195A7
0x18001959a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001959f  test    al, al
0x1800195a1  jnz     loc_180019636
0x1800195a7  mov     [rsp+48h+var_28], ebp
0x1800195ab  xor     eax, eax
0x1800195ad  mov     [rsp+48h+var_24], eax
0x1800195b1  mov     [rsp+48h+var_20], rbx
0x1800195b6  lea     rcx, [rdi+20h]; this
0x1800195ba  mov     r8d, 10h; unsigned __int64
0x1800195c0  lea     rdx, [rsp+48h+var_28]; void *
0x1800195c5  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800195ca  cmp     byte ptr [rdi+18h], 0
0x1800195ce  jnz     short loc_180019636
0x1800195d0  cmp     qword ptr [rdi+10h], 0
0x1800195d5  jnz     short loc_180019606
0x1800195d7  call    cs:__imp_GetLastError
0x1800195dd  mov     ebx, eax
0x1800195df  xor     r8d, r8d; pcbe
0x1800195e2  mov     rdx, rdi; pv
0x1800195e5  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800195ec  call    cs:__imp_CreateThreadpoolTimer
0x1800195f2  mov     rdx, rax
0x1800195f5  lea     rcx, [rdi+10h]
0x1800195f9  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800195fe  mov     ecx, ebx; dwErrCode
0x180019600  call    cs:__imp_SetLastError
0x180019606  mov     rcx, [rdi+10h]; pti
0x18001960a  test    rcx, rcx
0x18001960d  jz      short loc_180019636
0x18001960f  mov     rax, 0FFFFFFFF4D2FA200h
0x180019619  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x18001961e  mov     r9d, 124F8h; msWindowLength
0x180019624  xor     r8d, r8d; msPeriod
0x180019627  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18001962c  call    cs:__imp_SetThreadpoolTimer
0x180019632  mov     byte ptr [rdi+18h], 1
0x180019636  test    rsi, rsi
0x180019639  jz      short loc_180019645
0x18001963b  mov     rcx, rsi; SRWLock
0x18001963e  call    cs:__imp_ReleaseSRWLockExclusive
0x180019644  nop
0x180019645  mov     rbx, [rsp+48h+arg_8]
0x18001964a  mov     rbp, [rsp+48h+arg_10]
0x18001964f  add     rsp, 30h
0x180019653  pop     r14
0x180019655  pop     rdi
0x180019656  pop     rsi
0x180019657  retn
```
