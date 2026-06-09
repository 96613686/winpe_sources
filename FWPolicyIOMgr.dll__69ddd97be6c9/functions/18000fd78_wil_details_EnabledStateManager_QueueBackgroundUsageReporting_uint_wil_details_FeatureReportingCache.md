# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000fd78`
- end: `0x18000fe51`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(char *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000f998`

## callees

- `0x18000fd78`
- `0x1800133f8`
- `0x1800135d4`
- `0x1800135f4`
- `0x180013654`
- `0x180013678`
- `0x180013738`
- `0x18001dd88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fdaa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fdaa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000fe0c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000fe0c`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v8[2]; // [rsp+20h] [rbp-38h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-30h]
  RTL_SRWLOCK *v10; // [rsp+30h] [rbp-28h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    v10 = (RTL_SRWLOCK *)(pv + 8);
    if ( *(_DWORD *)pv )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v8[0] = a2;
        v8[1] = 0;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 32), v8, 0x10u);
        if ( !pv[24] )
        {
          if ( !*((_QWORD *)pv + 2) )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)v8);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              pv + 16,
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)v8);
          }
          wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 2, pv + 24, 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x18000fd78  mov     [rsp+arg_18], rbx
0x18000fd7d  push    rbp
0x18000fd7e  push    rsi
0x18000fd7f  push    rdi
0x18000fd80  sub     rsp, 40h
0x18000fd84  mov     rbp, r8
0x18000fd87  mov     esi, edx
0x18000fd89  mov     rdi, rcx
0x18000fd8c  mov     eax, [rcx]
0x18000fd8e  test    eax, eax
0x18000fd90  jz      loc_18000FE44
0x18000fd96  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000fd9b  test    al, al
0x18000fd9d  jnz     loc_18000FE44
0x18000fda3  lea     rbx, [rdi+8]
0x18000fda7  mov     rcx, rbx; SRWLock
0x18000fdaa  call    cs:__imp_AcquireSRWLockExclusive
0x18000fdb0  mov     [rsp+58h+var_28], rbx
0x18000fdb5  mov     eax, [rdi]
0x18000fdb7  test    eax, eax
0x18000fdb9  jz      short loc_18000FE39
0x18000fdbb  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000fdc0  test    al, al
0x18000fdc2  jnz     short loc_18000FE39
0x18000fdc4  mov     [rsp+58h+var_38], esi
0x18000fdc8  xor     eax, eax
0x18000fdca  mov     [rsp+58h+var_34], eax
0x18000fdce  mov     [rsp+58h+var_30], rbp
0x18000fdd3  lea     rcx, [rdi+20h]; this
0x18000fdd7  lea     r8d, [rax+10h]; unsigned __int64
0x18000fddb  lea     rdx, [rsp+58h+var_38]; void *
0x18000fde0  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000fde5  cmp     byte ptr [rdi+18h], 0
0x18000fde9  jnz     short loc_18000FE39
0x18000fdeb  lea     rbx, [rdi+10h]
0x18000fdef  cmp     qword ptr [rbx], 0
0x18000fdf3  jnz     short loc_18000FE27
0x18000fdf5  lea     rcx, [rsp+58h+var_38]; this
0x18000fdfa  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000fdff  xor     r8d, r8d; pcbe
0x18000fe02  mov     rdx, rdi; pv
0x18000fe05  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000fe0c  call    cs:__imp_CreateThreadpoolTimer
0x18000fe12  mov     rdx, rax
0x18000fe15  mov     rcx, rbx
0x18000fe18  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000fe1d  lea     rcx, [rsp+58h+var_38]; this
0x18000fe22  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000fe27  mov     r8d, 493E0h
0x18000fe2d  lea     rdx, [rdi+18h]
0x18000fe31  mov     rcx, rbx
0x18000fe34  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000fe39  lea     rcx, [rsp+58h+var_28]
0x18000fe3e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000fe43  nop
0x18000fe44  mov     rbx, [rsp+58h+arg_18]
0x18000fe49  add     rsp, 40h
0x18000fe4d  pop     rdi
0x18000fe4e  pop     rsi
0x18000fe4f  pop     rbp
0x18000fe50  retn
```
