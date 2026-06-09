# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1800676b4`
- end: `0x1800677a0`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `236`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800682f4`

## callees

- `0x1800413c0`
- `0x1800418a0`
- `0x18004b084`
- `0x180065988`
- `0x180066510`
- `0x1800676b4`
- `0x18006924c`
- `0x1800692a8`
- `0x1800693b8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180067756`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180067756`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v5; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _QWORD v7[4]; // [rsp+28h] [rbp-20h] BYREF
  char v8; // [rsp+50h] [rbp+8h] BYREF
  char v9; // [rsp+68h] [rbp+20h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    wil::srwlock::lock_exclusive(pv + 8, &v9);
    if ( *(_DWORD *)pv )
    {
      if ( !wil::ProcessShutdownInProgress(v5) )
      {
        v7[0] = 42911515;
        v7[1] = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 32), v7, 0x10u);
        if ( !pv[24] )
        {
          if ( !*((_QWORD *)pv + 2) )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v8);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              pv + 16,
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v8);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(pv + 16, pv + 24, 300000);
        }
      }
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>();
  }
}

```

## disassembly

```asm
0x1800676b4  push    rdi
0x1800676b6  sub     rsp, 40h
0x1800676ba  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x1800676c3  mov     [rsp+48h+arg_8], rbx
0x1800676c8  mov     [rsp+48h+arg_10], rsi
0x1800676cd  mov     rdi, r8
0x1800676d0  mov     rbx, rcx
0x1800676d3  mov     eax, [rcx]
0x1800676d5  test    eax, eax
0x1800676d7  jz      loc_180067790
0x1800676dd  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800676e2  test    al, al
0x1800676e4  jnz     loc_180067790
0x1800676ea  lea     rcx, [rbx+8]
0x1800676ee  lea     rdx, [rsp+48h+arg_18]
0x1800676f3  call    ?lock_exclusive@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_exclusive(void)
0x1800676f8  nop
0x1800676f9  mov     eax, [rbx]
0x1800676fb  test    eax, eax
0x1800676fd  jz      loc_180067785
0x180067703  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180067708  test    al, al
0x18006770a  jnz     short loc_180067785
0x18006770c  mov     [rsp+48h+var_20], 28EC71Bh
0x180067715  mov     [rsp+48h+var_18], rdi
0x18006771a  lea     rcx, [rbx+20h]; this
0x18006771e  mov     r8d, 10h; unsigned __int64
0x180067724  lea     rdx, [rsp+48h+var_20]; void *
0x180067729  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18006772e  cmp     byte ptr [rbx+18h], 0
0x180067732  jnz     short loc_180067785
0x180067734  lea     rdi, [rbx+10h]
0x180067738  cmp     qword ptr [rdi], 0
0x18006773c  jnz     short loc_180067772
0x18006773e  lea     rcx, [rsp+48h+arg_0]; this
0x180067743  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180067748  nop
0x180067749  xor     r8d, r8d; pcbe
0x18006774c  mov     rdx, rbx; pv
0x18006774f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180067756  call    cs:__imp_CreateThreadpoolTimer
0x18006775c  mov     rdx, rax
0x18006775f  mov     rcx, rdi
0x180067762  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180067767  nop
0x180067768  lea     rcx, [rsp+48h+arg_0]; this
0x18006776d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180067772  mov     r8d, 493E0h
0x180067778  lea     rdx, [rbx+18h]
0x18006777c  mov     rcx, rdi
0x18006777f  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180067784  nop
0x180067785  lea     rcx, [rsp+48h+arg_18]
0x18006778a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18006778f  nop
0x180067790  mov     rbx, [rsp+48h+arg_8]
0x180067795  mov     rsi, [rsp+48h+arg_10]
0x18006779a  add     rsp, 40h
0x18006779e  pop     rdi
0x18006779f  retn
```
