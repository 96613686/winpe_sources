# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180014e58`
- end: `0x180014f31`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180015394`

## callees

- `0x18000b810`
- `0x18000bc80`
- `0x18000c020`
- `0x18000d6d0`
- `0x180014d2c`
- `0x180014e58`
- `0x180018d34`
- `0x180018f10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014e8a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014e8a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180014eec`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180014eec`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v8[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-20h]
  char v10; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v11; // [rsp+68h] [rbp+20h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    v11 = pv + 1;
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
            wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3], 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x180014e58  mov     [rsp+arg_8], rbx
0x180014e5d  push    rbp
0x180014e5e  push    rsi
0x180014e5f  push    rdi
0x180014e60  sub     rsp, 30h
0x180014e64  mov     rsi, r8
0x180014e67  mov     ebp, edx
0x180014e69  mov     rdi, rcx
0x180014e6c  mov     eax, [rcx]
0x180014e6e  test    eax, eax
0x180014e70  jz      loc_180014F24
0x180014e76  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180014e7b  test    al, al
0x180014e7d  jnz     loc_180014F24
0x180014e83  lea     rbx, [rdi+8]
0x180014e87  mov     rcx, rbx; SRWLock
0x180014e8a  call    cs:__imp_AcquireSRWLockExclusive
0x180014e90  mov     [rsp+48h+arg_18], rbx
0x180014e95  mov     eax, [rdi]
0x180014e97  test    eax, eax
0x180014e99  jz      short loc_180014F19
0x180014e9b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180014ea0  test    al, al
0x180014ea2  jnz     short loc_180014F19
0x180014ea4  mov     [rsp+48h+var_28], ebp
0x180014ea8  xor     eax, eax
0x180014eaa  mov     [rsp+48h+var_24], eax
0x180014eae  mov     [rsp+48h+var_20], rsi
0x180014eb3  lea     rcx, [rdi+20h]; this
0x180014eb7  lea     r8d, [rax+10h]; unsigned __int64
0x180014ebb  lea     rdx, [rsp+48h+var_28]; void *
0x180014ec0  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180014ec5  cmp     byte ptr [rdi+18h], 0
0x180014ec9  jnz     short loc_180014F19
0x180014ecb  lea     rbx, [rdi+10h]
0x180014ecf  cmp     qword ptr [rbx], 0
0x180014ed3  jnz     short loc_180014F07
0x180014ed5  lea     rcx, [rsp+48h+arg_0]; this
0x180014eda  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180014edf  xor     r8d, r8d; pcbe
0x180014ee2  mov     rdx, rdi; pv
0x180014ee5  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180014eec  call    cs:__imp_CreateThreadpoolTimer
0x180014ef2  mov     rdx, rax
0x180014ef5  mov     rcx, rbx
0x180014ef8  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180014efd  lea     rcx, [rsp+48h+arg_0]; this
0x180014f02  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180014f07  mov     r8d, 493E0h
0x180014f0d  lea     rdx, [rdi+18h]
0x180014f11  mov     rcx, rbx
0x180014f14  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180014f19  lea     rcx, [rsp+48h+arg_18]
0x180014f1e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180014f23  nop
0x180014f24  mov     rbx, [rsp+48h+arg_8]
0x180014f29  add     rsp, 30h
0x180014f2d  pop     rdi
0x180014f2e  pop     rsi
0x180014f2f  pop     rbp
0x180014f30  retn
```
