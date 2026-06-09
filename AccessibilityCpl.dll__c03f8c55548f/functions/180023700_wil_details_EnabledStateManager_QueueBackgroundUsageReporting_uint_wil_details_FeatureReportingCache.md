# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180023700`
- end: `0x1800237df`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `223`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800239e0`

## callees

- `0x180004610`
- `0x1800049d0`
- `0x180004dc8`
- `0x180005e58`
- `0x180014a40`
- `0x18001b77c`
- `0x18001b888`
- `0x180023700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023732`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023732`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180023799`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180023799`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v8[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-20h]
  RTL_SRWLOCK *v10; // [rsp+50h] [rbp+8h] BYREF
  char v11; // [rsp+68h] [rbp+20h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    v10 = pv + 1;
    if ( LODWORD(pv->Ptr) )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v8[0] = a2;
        v8[1] = 0;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v8, 0x10u);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3], 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x180023700  mov     [rsp+arg_8], rbx
0x180023705  push    rbp
0x180023706  push    rsi
0x180023707  push    rdi
0x180023708  sub     rsp, 30h
0x18002370c  mov     rsi, r8
0x18002370f  mov     ebp, edx
0x180023711  mov     rdi, rcx
0x180023714  mov     eax, [rcx]
0x180023716  test    eax, eax
0x180023718  jz      loc_1800237D2
0x18002371e  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180023723  test    al, al
0x180023725  jnz     loc_1800237D2
0x18002372b  lea     rbx, [rdi+8]
0x18002372f  mov     rcx, rbx; SRWLock
0x180023732  call    cs:__imp_AcquireSRWLockExclusive
0x180023738  mov     [rsp+48h+arg_0], rbx
0x18002373d  mov     eax, [rdi]
0x18002373f  test    eax, eax
0x180023741  jz      loc_1800237C7
0x180023747  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002374c  test    al, al
0x18002374e  jnz     short loc_1800237C7
0x180023750  mov     [rsp+48h+var_28], ebp
0x180023754  xor     eax, eax
0x180023756  mov     [rsp+48h+var_24], eax
0x18002375a  mov     [rsp+48h+var_20], rsi
0x18002375f  lea     rcx, [rdi+20h]; this
0x180023763  lea     r8d, [rax+10h]; unsigned __int64
0x180023767  lea     rdx, [rsp+48h+var_28]; void *
0x18002376c  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180023771  nop
0x180023772  cmp     byte ptr [rdi+18h], 0
0x180023776  jnz     short loc_1800237C7
0x180023778  lea     rbx, [rdi+10h]
0x18002377c  cmp     qword ptr [rbx], 0
0x180023780  jnz     short loc_1800237B4
0x180023782  lea     rcx, [rsp+48h+arg_18]; this
0x180023787  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002378c  xor     r8d, r8d; pcbe
0x18002378f  mov     rdx, rdi; pv
0x180023792  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180023799  call    cs:__imp_CreateThreadpoolTimer
0x18002379f  mov     rdx, rax
0x1800237a2  mov     rcx, rbx
0x1800237a5  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800237aa  lea     rcx, [rsp+48h+arg_18]; this
0x1800237af  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800237b4  mov     r8d, 493E0h
0x1800237ba  lea     rdx, [rdi+18h]
0x1800237be  mov     rcx, rbx
0x1800237c1  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800237c6  nop
0x1800237c7  lea     rcx, [rsp+48h+arg_0]
0x1800237cc  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800237d1  nop
0x1800237d2  mov     rbx, [rsp+48h+arg_8]
0x1800237d7  add     rsp, 30h
0x1800237db  pop     rdi
0x1800237dc  pop     rsi
0x1800237dd  pop     rbp
0x1800237de  retn
```
