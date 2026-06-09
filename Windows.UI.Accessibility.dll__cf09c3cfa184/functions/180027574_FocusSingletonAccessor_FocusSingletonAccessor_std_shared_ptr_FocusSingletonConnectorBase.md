# FocusSingletonAccessor::FocusSingletonAccessor(std::shared_ptr<FocusSingletonConnectorBase>)

- ea: `0x180027574`
- end: `0x180027658`
- name: `??0FocusSingletonAccessor@@QEAA@V?$shared_ptr@VFocusSingletonConnectorBase@@@std@@@Z`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180027428`

## callees

- `0x180003980`
- `0x18000840c`
- `0x180008ee0`
- `0x180012904`
- `0x180016584`
- `0x1800205a4`
- `0x180020834`
- `0x1800270f8`
- `0x180027574`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall FocusSingletonAccessor::FocusSingletonAccessor(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 wnf; // rax
  std::_Ref_count_base *v7; // rcx
  _BYTE v9[8]; // [rsp+20h] [rbp-A8h] BYREF
  __int64 v10; // [rsp+28h] [rbp-A0h]
  __int64 v11; // [rsp+30h] [rbp-98h]
  _BYTE v12[8]; // [rsp+38h] [rbp-90h] BYREF
  _BYTE v13[8]; // [rsp+40h] [rbp-88h] BYREF
  _QWORD v14[14]; // [rsp+48h] [rbp-80h] BYREF

  v10 = a1;
  v11 = a2;
  std::shared_ptr<FocusSingletonConnectorBase>::shared_ptr<FocusSingletonConnectorBase>(a1, a2);
  v4[2] = 0;
  v4[3] = 0;
  v4[4] = 0;
  v5 = *(_QWORD *)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(v12, v4);
  v14[0] = off_180037148;
  v14[1] = v5;
  v14[13] = v14;
  wnf = wil::make_wnf_subscription<unsigned int>(v9, &WNF_EOA_FOCUS_SESSION_SINGLETON_INITIALIZED, v13);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
    a1 + 32,
    wnf);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(v9);
  wistd::function<void (winrt::Windows::UI::Accessibility::implementation::ScreenReaderService::ScreenReaderPositionChangedEventPayload const &)>::~function<void (winrt::Windows::UI::Accessibility::implementation::ScreenReaderService::ScreenReaderPositionChangedEventPayload const &)>((__int64)v13);
  v7 = *(std::_Ref_count_base **)(a2 + 8);
  if ( v7 )
    std::_Ref_count_base::_Decref(v7);
  return a1;
}

```

## disassembly

```asm
0x180027574  mov     [rsp+arg_10], rbx
0x180027579  mov     [rsp+arg_18], rsi
0x18002757e  push    rdi
0x18002757f  sub     rsp, 0C0h
0x180027586  mov     rax, cs:__security_cookie
0x18002758d  xor     rax, rsp
0x180027590  mov     [rsp+0C8h+var_10], rax
0x180027598  mov     rdi, rdx
0x18002759b  mov     rsi, rcx
0x18002759e  mov     [rsp+0C8h+var_A0], rcx
0x1800275a3  mov     [rsp+0C8h+var_98], rdx
0x1800275a8  call    ??0?$shared_ptr@VFocusSingletonConnectorBase@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<FocusSingletonConnectorBase>::shared_ptr<FocusSingletonConnectorBase>(std::shared_ptr<FocusSingletonConnectorBase> const &)
0x1800275ad  nop
0x1800275ae  xor     eax, eax
0x1800275b0  mov     [rcx+10h], rax
0x1800275b4  mov     [rcx+18h], rax
0x1800275b8  mov     [rcx+20h], rax
0x1800275bc  mov     rdx, rcx
0x1800275bf  lea     rcx, [rsp+0C8h+var_90]
0x1800275c4  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800275c9  mov     rdx, [rax]
0x1800275cc  lea     rax, off_180037148
0x1800275d3  mov     [rsp+0C8h+var_80], rax
0x1800275d8  mov     [rsp+0C8h+var_78], rdx
0x1800275dd  lea     rax, [rsp+0C8h+var_80]
0x1800275e2  mov     [rsp+0C8h+var_18], rax
0x1800275ea  lea     r8, [rsp+0C8h+var_88]
0x1800275ef  lea     rdx, WNF_EOA_FOCUS_SESSION_SINGLETON_INITIALIZED
0x1800275f6  lea     rcx, [rsp+0C8h+var_A8]
0x1800275fb  call    ??$make_wnf_subscription@I@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXAEBI@Z@wistd@@K@Z; wil::make_wnf_subscription<uint>(_WNF_STATE_NAME const &,wistd::function<void (uint const &)> &&,ulong)
0x180027600  mov     rdx, rax
0x180027603  lea     rcx, [rsi+20h]
0x180027607  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x18002760c  lea     rcx, [rsp+0C8h+var_A8]
0x180027611  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x180027616  nop
0x180027617  lea     rcx, [rsp+0C8h+var_88]
0x18002761c  call    ??1?$function@$$A6AXAEBUScreenReaderPositionChangedEventPayload@ScreenReaderService@implementation@Accessibility@UI@Windows@winrt@@@Z@wistd@@QEAA@XZ; wistd::function<void (winrt::Windows::UI::Accessibility::implementation::ScreenReaderService::ScreenReaderPositionChangedEventPayload const &)>::~function<void (winrt::Windows::UI::Accessibility::implementation::ScreenReaderService::ScreenReaderPositionChangedEventPayload const &)>(void)
0x180027621  nop
0x180027622  mov     rcx, [rdi+8]; this
0x180027626  test    rcx, rcx
0x180027629  jz      short loc_180027630
0x18002762b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180027630  mov     rax, rsi
0x180027633  mov     rcx, [rsp+0C8h+var_10]
0x18002763b  xor     rcx, rsp; StackCookie
0x18002763e  call    __security_check_cookie
0x180027643  lea     r11, [rsp+0C8h+var_8]
0x18002764b  mov     rbx, [r11+20h]
0x18002764f  mov     rsi, [r11+28h]
0x180027653  mov     rsp, r11
0x180027656  pop     rdi
0x180027657  retn
```
