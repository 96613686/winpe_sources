# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x140013b5c`
- end: `0x140013c3f`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `227`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14001512c`

## callees

- `0x140006418`
- `0x1400067e4`
- `0x140006b80`
- `0x140007254`
- `0x140009044`
- `0x14000bb00`
- `0x14000bc08`
- `0x140013b5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140013b98`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140013b98`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140013bfa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140013bfa`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v8[2]; // [rsp+28h] [rbp-30h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+30h] [rbp-28h]
  char v10; // [rsp+60h] [rbp+8h] BYREF
  RTL_SRWLOCK *v11; // [rsp+78h] [rbp+20h] BYREF

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
0x140013b5c  push    rbp
0x140013b5e  push    rsi
0x140013b5f  push    rdi
0x140013b60  sub     rsp, 40h
0x140013b64  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x140013b6d  mov     [rsp+58h+arg_8], rbx
0x140013b72  mov     rsi, r8
0x140013b75  mov     ebp, edx
0x140013b77  mov     rdi, rcx
0x140013b7a  mov     eax, [rcx]
0x140013b7c  test    eax, eax
0x140013b7e  jz      loc_140013C32
0x140013b84  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x140013b89  test    al, al
0x140013b8b  jnz     loc_140013C32
0x140013b91  lea     rbx, [rdi+8]
0x140013b95  mov     rcx, rbx; SRWLock
0x140013b98  call    cs:__imp_AcquireSRWLockExclusive
0x140013b9e  mov     [rsp+58h+arg_18], rbx
0x140013ba3  mov     eax, [rdi]
0x140013ba5  test    eax, eax
0x140013ba7  jz      short loc_140013C27
0x140013ba9  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x140013bae  test    al, al
0x140013bb0  jnz     short loc_140013C27
0x140013bb2  mov     [rsp+58h+var_30], ebp
0x140013bb6  xor     eax, eax
0x140013bb8  mov     [rsp+58h+var_2C], eax
0x140013bbc  mov     [rsp+58h+var_28], rsi
0x140013bc1  lea     rcx, [rdi+20h]; this
0x140013bc5  lea     r8d, [rax+10h]; unsigned __int64
0x140013bc9  lea     rdx, [rsp+58h+var_30]; void *
0x140013bce  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140013bd3  cmp     byte ptr [rdi+18h], 0
0x140013bd7  jnz     short loc_140013C27
0x140013bd9  lea     rbx, [rdi+10h]
0x140013bdd  cmp     qword ptr [rbx], 0
0x140013be1  jnz     short loc_140013C15
0x140013be3  lea     rcx, [rsp+58h+arg_0]; this
0x140013be8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140013bed  xor     r8d, r8d; pcbe
0x140013bf0  mov     rdx, rdi; pv
0x140013bf3  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140013bfa  call    cs:__imp_CreateThreadpoolTimer
0x140013c00  mov     rdx, rax
0x140013c03  mov     rcx, rbx
0x140013c06  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140013c0b  lea     rcx, [rsp+58h+arg_0]; this
0x140013c10  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140013c15  mov     r8d, 493E0h
0x140013c1b  lea     rdx, [rdi+18h]
0x140013c1f  mov     rcx, rbx
0x140013c22  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x140013c27  lea     rcx, [rsp+58h+arg_18]
0x140013c2c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140013c31  nop
0x140013c32  mov     rbx, [rsp+58h+arg_8]
0x140013c37  add     rsp, 40h
0x140013c3b  pop     rdi
0x140013c3c  pop     rsi
0x140013c3d  pop     rbp
0x140013c3e  retn
```
