# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180007d50`
- end: `0x180007e2b`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `219`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180009208`

## callees

- `0x180003a24`
- `0x180003d78`
- `0x180004128`
- `0x180004650`
- `0x180004884`
- `0x180007c98`
- `0x180007d50`
- `0x18000ad18`
- `0x18000ae20`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007de3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007de3`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v8[2]; // [rsp+20h] [rbp-18h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-10h]
  char v10; // [rsp+40h] [rbp+8h] BYREF
  char v11; // [rsp+58h] [rbp+20h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    wil::AcquireSRWLockExclusive(&v11, pv + 8);
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
            wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              pv + 16,
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(pv + 16, pv + 24, 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x180007d50  mov     [rsp+arg_8], rbx
0x180007d55  mov     [rsp+arg_10], rsi
0x180007d5a  push    rdi
0x180007d5b  sub     rsp, 30h
0x180007d5f  mov     rdi, r8
0x180007d62  mov     esi, edx
0x180007d64  mov     rbx, rcx
0x180007d67  mov     eax, [rcx]
0x180007d69  test    eax, eax
0x180007d6b  jz      loc_180007E1B
0x180007d71  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180007d76  test    al, al
0x180007d78  jnz     loc_180007E1B
0x180007d7e  lea     rdx, [rbx+8]
0x180007d82  lea     rcx, [rsp+38h+arg_18]
0x180007d87  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180007d8c  mov     eax, [rbx]
0x180007d8e  test    eax, eax
0x180007d90  jz      short loc_180007E10
0x180007d92  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180007d97  test    al, al
0x180007d99  jnz     short loc_180007E10
0x180007d9b  mov     [rsp+38h+var_18], esi
0x180007d9f  xor     eax, eax
0x180007da1  mov     [rsp+38h+var_14], eax
0x180007da5  mov     [rsp+38h+var_10], rdi
0x180007daa  lea     rcx, [rbx+20h]; this
0x180007dae  lea     r8d, [rax+10h]; unsigned __int64
0x180007db2  lea     rdx, [rsp+38h+var_18]; void *
0x180007db7  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180007dbc  cmp     byte ptr [rbx+18h], 0
0x180007dc0  jnz     short loc_180007E10
0x180007dc2  lea     rdi, [rbx+10h]
0x180007dc6  cmp     qword ptr [rdi], 0
0x180007dca  jnz     short loc_180007DFE
0x180007dcc  lea     rcx, [rsp+38h+arg_0]; this
0x180007dd1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180007dd6  xor     r8d, r8d; pcbe
0x180007dd9  mov     rdx, rbx; pv
0x180007ddc  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180007de3  call    cs:__imp_CreateThreadpoolTimer
0x180007de9  mov     rdx, rax
0x180007dec  mov     rcx, rdi
0x180007def  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180007df4  lea     rcx, [rsp+38h+arg_0]; this
0x180007df9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180007dfe  mov     r8d, 493E0h
0x180007e04  lea     rdx, [rbx+18h]
0x180007e08  mov     rcx, rdi
0x180007e0b  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180007e10  lea     rcx, [rsp+38h+arg_18]
0x180007e15  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180007e1a  nop
0x180007e1b  mov     rbx, [rsp+38h+arg_8]
0x180007e20  mov     rsi, [rsp+38h+arg_10]
0x180007e25  add     rsp, 30h
0x180007e29  pop     rdi
0x180007e2a  retn
```
