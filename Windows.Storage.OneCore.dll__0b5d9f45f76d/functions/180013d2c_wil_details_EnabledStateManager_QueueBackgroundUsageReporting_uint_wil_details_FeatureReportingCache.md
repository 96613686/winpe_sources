# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180013d2c`
- end: `0x180013e0a`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `222`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180013f44`

## callees

- `0x1800047c4`
- `0x180004b18`
- `0x180004e40`
- `0x1800054f4`
- `0x180007258`
- `0x18000974c`
- `0x180009854`
- `0x180013d2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013d5f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013d5f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180013dc2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180013dc2`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v5; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _QWORD v7[3]; // [rsp+20h] [rbp-18h] BYREF
  char v8; // [rsp+40h] [rbp+8h] BYREF
  RTL_SRWLOCK *v9; // [rsp+58h] [rbp+20h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    v9 = pv + 1;
    if ( LODWORD(pv->Ptr) )
    {
      if ( !wil::ProcessShutdownInProgress(v5) )
      {
        v7[0] = 13848133;
        v7[1] = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v7, 0x10u);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v8);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v8);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3], 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  }
}

```

## disassembly

```asm
0x180013d2c  mov     [rsp+arg_8], rbx
0x180013d31  mov     [rsp+arg_10], rsi
0x180013d36  push    rdi
0x180013d37  sub     rsp, 30h
0x180013d3b  mov     rsi, r8
0x180013d3e  mov     rdi, rcx
0x180013d41  mov     eax, [rcx]
0x180013d43  test    eax, eax
0x180013d45  jz      loc_180013DFA
0x180013d4b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180013d50  test    al, al
0x180013d52  jnz     loc_180013DFA
0x180013d58  lea     rbx, [rdi+8]
0x180013d5c  mov     rcx, rbx; SRWLock
0x180013d5f  call    cs:__imp_AcquireSRWLockExclusive
0x180013d65  mov     [rsp+38h+arg_18], rbx
0x180013d6a  mov     eax, [rdi]
0x180013d6c  test    eax, eax
0x180013d6e  jz      short loc_180013DEF
0x180013d70  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180013d75  test    al, al
0x180013d77  jnz     short loc_180013DEF
0x180013d79  mov     [rsp+38h+var_18], 0D34E45h
0x180013d82  mov     [rsp+38h+var_10], rsi
0x180013d87  lea     rcx, [rdi+20h]; this
0x180013d8b  mov     r8d, 10h; unsigned __int64
0x180013d91  lea     rdx, [rsp+38h+var_18]; void *
0x180013d96  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180013d9b  cmp     byte ptr [rdi+18h], 0
0x180013d9f  jnz     short loc_180013DEF
0x180013da1  lea     rbx, [rdi+10h]
0x180013da5  cmp     qword ptr [rbx], 0
0x180013da9  jnz     short loc_180013DDD
0x180013dab  lea     rcx, [rsp+38h+arg_0]; this
0x180013db0  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180013db5  xor     r8d, r8d; pcbe
0x180013db8  mov     rdx, rdi; pv
0x180013dbb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180013dc2  call    cs:__imp_CreateThreadpoolTimer
0x180013dc8  mov     rdx, rax
0x180013dcb  mov     rcx, rbx
0x180013dce  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180013dd3  lea     rcx, [rsp+38h+arg_0]; this
0x180013dd8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180013ddd  mov     r8d, 493E0h
0x180013de3  lea     rdx, [rdi+18h]
0x180013de7  mov     rcx, rbx
0x180013dea  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180013def  lea     rcx, [rsp+38h+arg_18]
0x180013df4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180013df9  nop
0x180013dfa  mov     rbx, [rsp+38h+arg_8]
0x180013dff  mov     rsi, [rsp+38h+arg_10]
0x180013e04  add     rsp, 30h
0x180013e08  pop     rdi
0x180013e09  retn
```
