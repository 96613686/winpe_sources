# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x14003cd94`
- end: `0x14003ce7e`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `234`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14003d054`

## callees

- `0x14000bd48`
- `0x14000c604`
- `0x14000c628`
- `0x14000c670`
- `0x14000c69c`
- `0x140013958`
- `0x140029808`
- `0x14003cd94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14003cdc6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14003cdc6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14003ce32`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14003ce32`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v8[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-20h]
  char v10; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v11; // [rsp+68h] [rbp+20h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    v11 = (RTL_SRWLOCK *)(pv + 8);
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
          wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 2, pv + 24, 300000);
        }
      }
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v11);
  }
}

```

## disassembly

```asm
0x14003cd94  mov     [rsp+arg_8], rbx
0x14003cd99  push    rbp
0x14003cd9a  push    rsi
0x14003cd9b  push    rdi
0x14003cd9c  sub     rsp, 30h
0x14003cda0  mov     rsi, r8
0x14003cda3  mov     ebp, edx
0x14003cda5  mov     rdi, rcx
0x14003cda8  mov     eax, [rcx]
0x14003cdaa  test    eax, eax
0x14003cdac  jz      loc_14003CE70
0x14003cdb2  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14003cdb7  test    al, al
0x14003cdb9  jnz     loc_14003CE70
0x14003cdbf  lea     rbx, [rdi+8]
0x14003cdc3  mov     rcx, rbx; SRWLock
0x14003cdc6  call    cs:__imp_AcquireSRWLockExclusive
0x14003cdcd  nop     dword ptr [rax+rax+00h]
0x14003cdd2  mov     [rsp+48h+arg_18], rbx
0x14003cdd7  mov     eax, [rdi]
0x14003cdd9  test    eax, eax
0x14003cddb  jz      loc_14003CE65
0x14003cde1  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14003cde6  test    al, al
0x14003cde8  jnz     short loc_14003CE65
0x14003cdea  mov     [rsp+48h+var_28], ebp
0x14003cdee  xor     eax, eax
0x14003cdf0  mov     [rsp+48h+var_24], eax
0x14003cdf4  mov     [rsp+48h+var_20], rsi
0x14003cdf9  lea     rcx, [rdi+20h]; this
0x14003cdfd  lea     r8d, [rax+10h]; unsigned __int64
0x14003ce01  lea     rdx, [rsp+48h+var_28]; void *
0x14003ce06  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14003ce0b  cmp     byte ptr [rdi+18h], 0
0x14003ce0f  jnz     short loc_14003CE65
0x14003ce11  lea     rbx, [rdi+10h]
0x14003ce15  cmp     qword ptr [rbx], 0
0x14003ce19  jnz     short loc_14003CE53
0x14003ce1b  lea     rcx, [rsp+48h+arg_0]; this
0x14003ce20  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14003ce25  xor     r8d, r8d; pcbe
0x14003ce28  mov     rdx, rdi; pv
0x14003ce2b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14003ce32  call    cs:__imp_CreateThreadpoolTimer
0x14003ce39  nop     dword ptr [rax+rax+00h]
0x14003ce3e  mov     rdx, rax
0x14003ce41  mov     rcx, rbx
0x14003ce44  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14003ce49  lea     rcx, [rsp+48h+arg_0]; this
0x14003ce4e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14003ce53  mov     r8d, 493E0h
0x14003ce59  lea     rdx, [rdi+18h]
0x14003ce5d  mov     rcx, rbx
0x14003ce60  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x14003ce65  lea     rcx, [rsp+48h+arg_18]
0x14003ce6a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14003ce6f  nop
0x14003ce70  mov     rbx, [rsp+48h+arg_8]
0x14003ce75  add     rsp, 30h
0x14003ce79  pop     rdi
0x14003ce7a  pop     rsi
0x14003ce7b  pop     rbp
0x14003ce7c  retn
```
