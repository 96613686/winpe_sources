# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x140011e9c`
- end: `0x140011f74`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `216`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140013480`

## callees

- `0x1400085ac`
- `0x140009158`
- `0x1400097ec`
- `0x14000b924`
- `0x140010938`
- `0x140011e9c`
- `0x14001a930`
- `0x14001af30`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x140011ece`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140011ece`
- `KERNEL32!CreateThreadpoolTimer` at `0x140011f30`
- `KERNEL32!CreateThreadpoolTimer` at `0x140011f30`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  int v7; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v9[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v10; // [rsp+28h] [rbp-20h]
  char v11; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v12; // [rsp+68h] [rbp+20h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    v7 = *(_DWORD *)pv;
    v12 = (RTL_SRWLOCK *)(pv + 8);
    if ( v7 )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v9[0] = a2;
        v9[1] = 0;
        v10 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 32), v9, 0x10u);
        if ( !pv[24] )
        {
          if ( !*((_QWORD *)pv + 2) )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              pv + 16,
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
          }
          wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 2, pv + 24, 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  }
}

```

## disassembly

```asm
0x140011e9c  mov     [rsp+arg_8], rbx
0x140011ea1  push    rbp
0x140011ea2  push    rsi
0x140011ea3  push    rdi
0x140011ea4  sub     rsp, 30h
0x140011ea8  mov     eax, [rcx]
0x140011eaa  mov     rsi, r8
0x140011ead  mov     ebp, edx
0x140011eaf  mov     rdi, rcx
0x140011eb2  test    eax, eax
0x140011eb4  jz      loc_140011F67
0x140011eba  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x140011ebf  test    al, al
0x140011ec1  jnz     loc_140011F67
0x140011ec7  lea     rbx, [rdi+8]
0x140011ecb  mov     rcx, rbx; SRWLock
0x140011ece  call    cs:__imp_AcquireSRWLockExclusive
0x140011ed4  mov     eax, [rdi]
0x140011ed6  mov     [rsp+48h+arg_18], rbx
0x140011edb  test    eax, eax
0x140011edd  jz      short loc_140011F5D
0x140011edf  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x140011ee4  test    al, al
0x140011ee6  jnz     short loc_140011F5D
0x140011ee8  xor     eax, eax
0x140011eea  mov     [rsp+48h+var_28], ebp
0x140011eee  lea     rcx, [rdi+20h]; this
0x140011ef2  mov     [rsp+48h+var_24], eax
0x140011ef6  lea     rdx, [rsp+48h+var_28]; void *
0x140011efb  mov     [rsp+48h+var_20], rsi
0x140011f00  lea     r8d, [rax+10h]; unsigned __int64
0x140011f04  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140011f09  cmp     byte ptr [rdi+18h], 0
0x140011f0d  jnz     short loc_140011F5D
0x140011f0f  lea     rbx, [rdi+10h]
0x140011f13  cmp     qword ptr [rbx], 0
0x140011f17  jnz     short loc_140011F4B
0x140011f19  lea     rcx, [rsp+48h+arg_0]; this
0x140011f1e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140011f23  xor     r8d, r8d; pcbe
0x140011f26  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140011f2d  mov     rdx, rdi; pv
0x140011f30  call    cs:__imp_CreateThreadpoolTimer
0x140011f36  mov     rdx, rax
0x140011f39  mov     rcx, rbx
0x140011f3c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140011f41  lea     rcx, [rsp+48h+arg_0]; this
0x140011f46  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140011f4b  mov     r8d, 493E0h
0x140011f51  lea     rdx, [rdi+18h]
0x140011f55  mov     rcx, rbx
0x140011f58  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x140011f5d  lea     rcx, [rsp+48h+arg_18]
0x140011f62  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140011f67  mov     rbx, [rsp+48h+arg_8]
0x140011f6c  add     rsp, 30h
0x140011f70  pop     rdi
0x140011f71  pop     rsi
0x140011f72  pop     rbp
0x140011f73  retn
```
