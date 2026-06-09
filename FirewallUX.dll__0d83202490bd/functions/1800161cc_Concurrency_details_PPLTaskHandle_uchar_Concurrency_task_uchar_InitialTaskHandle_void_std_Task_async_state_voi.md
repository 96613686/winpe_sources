# Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,`std::_Task_async_state<void>::_Task_async_state<void>(std::_Fake_no_copy_callable_adapter<`winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync(bool)'::`2'::_lambda_1_> &&)'::`2'::_lambda_1_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::~_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,`std::_Task_async_state<void>::_Task_async_state<void>(std::_Fake_no_copy_callable_adapter<`winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync(bool)'::`2'::_lambda_1_> &&)'::`2'::_lambda_1_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>(void)

- ea: `0x1800161cc`
- end: `0x180016249`
- name: `??1?$_PPLTaskHandle@EU?$_InitialTaskHandle@XV_lambda_1_@?1???$?0V?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@std@@@?$_Task_async_state@X@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@3@@Z@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_TaskProcHandle@details@3@@details@Concurrency@@UEAA@XZ`
- size: `125`
- prototype: `void **__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800171c0`
- `0x180017210`

## callees

- `0x1800161cc`
- `0x18002d010`

## import_xrefs

- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800161ee`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800161ee`

## pseudocode

```c
void **__fastcall __1___PPLTaskHandle_EU___InitialTaskHandle_XV_lambda_1___1_____0V___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__std______Task_async_state_X_std__QEAA___QEAV___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__3__Z_U_TypeSelectorNoAsync_details_Concurrency_____task_E_Concurrency__U_TaskProcHandle_details_3__details_Concurrency__UEAA_XZ(
        _QWORD *a1)
{
  volatile signed __int32 *v2; // rbx
  void **result; // rax

  *a1 = &___7___PPLTaskHandle_EU___InitialTaskHandle_XV_lambda_1___1_____0V___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__std______Task_async_state_X_std__QEAA___QEAV___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__3__Z_U_TypeSelectorNoAsync_details_Concurrency_____task_E_Concurrency__U_TaskProcHandle_details_3__details_Concurrency__6B_;
  Concurrency::details::_TaskEventLogger::_LogTaskCompleted((Concurrency::details::_TaskEventLogger *)(a1[1] + 352LL));
  v2 = (volatile signed __int32 *)a1[2];
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
      if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
    }
  }
  result = &Concurrency::details::_TaskProcHandle::`vftable';
  *a1 = &Concurrency::details::_TaskProcHandle::`vftable';
  return result;
}

```

## disassembly

```asm
0x1800161cc  mov     [rsp+arg_0], rbx
0x1800161d1  push    rdi
0x1800161d2  sub     rsp, 20h
0x1800161d6  mov     rdi, rcx
0x1800161d9  lea     rax, ??_7?$_PPLTaskHandle@EU?$_InitialTaskHandle@XV_lambda_1_@?1???$?0V?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@std@@@?$_Task_async_state@X@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@3@@Z@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_TaskProcHandle@details@3@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,`std::_Task_async_state<void>::_Task_async_state<void>(std::_Fake_no_copy_callable_adapter<`winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync(bool)'::`2'::_lambda_1_> &&)'::`2'::_lambda_1_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable'
0x1800161e0  mov     [rcx], rax
0x1800161e3  mov     rcx, [rcx+8]
0x1800161e7  add     rcx, 160h
0x1800161ee  call    cs:__imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskCompleted(void)
0x1800161f4  mov     rbx, [rdi+10h]
0x1800161f8  test    rbx, rbx
0x1800161fb  jz      short loc_180016234
0x1800161fd  or      eax, 0FFFFFFFFh
0x180016200  lock xadd [rbx+8], eax
0x180016205  cmp     eax, 1
0x180016208  jnz     short loc_180016234
0x18001620a  mov     rax, [rbx]
0x18001620d  mov     rcx, rbx
0x180016210  mov     rax, [rax]
0x180016213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016218  or      eax, 0FFFFFFFFh
0x18001621b  lock xadd [rbx+0Ch], eax
0x180016220  cmp     eax, 1
0x180016223  jnz     short loc_180016234
0x180016225  mov     rax, [rbx]
0x180016228  mov     rcx, rbx
0x18001622b  mov     rax, [rax+8]
0x18001622f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016234  lea     rax, ??_7_TaskProcHandle@details@Concurrency@@6B@; const Concurrency::details::_TaskProcHandle::`vftable'
0x18001623b  mov     [rdi], rax
0x18001623e  mov     rbx, [rsp+28h+arg_0]
0x180016243  add     rsp, 20h
0x180016247  pop     rdi
0x180016248  retn
```
