# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18001ff58`
- end: `0x180020036`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `222`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002107c`

## callees

- `0x18000a894`
- `0x18000ab7c`
- `0x18000c11c`
- `0x18001da5c`
- `0x18001e628`
- `0x18001ff58`
- `0x180022ea0`
- `0x18002308c`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x18001ffee`
- `KERNEL32!CreateThreadpoolTimer` at `0x18001ffee`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001ff8b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001ff8b`

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
        v7[0] = 60475541;
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
0x18001ff58  mov     [rsp+arg_8], rbx
0x18001ff5d  mov     [rsp+arg_10], rsi
0x18001ff62  push    rdi
0x18001ff63  sub     rsp, 30h
0x18001ff67  mov     rsi, r8
0x18001ff6a  mov     rdi, rcx
0x18001ff6d  mov     eax, [rcx]
0x18001ff6f  test    eax, eax
0x18001ff71  jz      loc_180020026
0x18001ff77  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001ff7c  test    al, al
0x18001ff7e  jnz     loc_180020026
0x18001ff84  lea     rbx, [rdi+8]
0x18001ff88  mov     rcx, rbx; SRWLock
0x18001ff8b  call    cs:__imp_AcquireSRWLockExclusive
0x18001ff91  mov     [rsp+38h+arg_18], rbx
0x18001ff96  mov     eax, [rdi]
0x18001ff98  test    eax, eax
0x18001ff9a  jz      short loc_18002001B
0x18001ff9c  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001ffa1  test    al, al
0x18001ffa3  jnz     short loc_18002001B
0x18001ffa5  mov     [rsp+38h+var_18], 39AC895h
0x18001ffae  mov     [rsp+38h+var_10], rsi
0x18001ffb3  lea     rcx, [rdi+20h]; this
0x18001ffb7  mov     r8d, 10h; unsigned __int64
0x18001ffbd  lea     rdx, [rsp+38h+var_18]; void *
0x18001ffc2  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001ffc7  cmp     byte ptr [rdi+18h], 0
0x18001ffcb  jnz     short loc_18002001B
0x18001ffcd  lea     rbx, [rdi+10h]
0x18001ffd1  cmp     qword ptr [rbx], 0
0x18001ffd5  jnz     short loc_180020009
0x18001ffd7  lea     rcx, [rsp+38h+arg_0]; this
0x18001ffdc  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001ffe1  xor     r8d, r8d; pcbe
0x18001ffe4  mov     rdx, rdi; pv
0x18001ffe7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001ffee  call    cs:__imp_CreateThreadpoolTimer
0x18001fff4  mov     rdx, rax
0x18001fff7  mov     rcx, rbx
0x18001fffa  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001ffff  lea     rcx, [rsp+38h+arg_0]; this
0x180020004  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180020009  mov     r8d, 493E0h
0x18002000f  lea     rdx, [rdi+18h]
0x180020013  mov     rcx, rbx
0x180020016  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18002001b  lea     rcx, [rsp+38h+arg_18]
0x180020020  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180020025  nop
0x180020026  mov     rbx, [rsp+38h+arg_8]
0x18002002b  mov     rsi, [rsp+38h+arg_10]
0x180020030  add     rsp, 30h
0x180020034  pop     rdi
0x180020035  retn
```
