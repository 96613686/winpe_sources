# winrt::Windows::UI::Accessibility::implementation::ScreenReaderService::ScreenReaderService(void)

- ea: `0x1800259f0`
- end: `0x180025b04`
- name: `??0ScreenReaderService@implementation@Accessibility@UI@Windows@winrt@@QEAA@XZ`
- size: `276`
- prototype: `__int64 __fastcall(winrt::Windows::UI::Accessibility::implementation::ScreenReaderService *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180025318`

## callees

- `0x180003980`
- `0x1800072d8`
- `0x180008ee0`
- `0x18000dd40`
- `0x18001eca0`
- `0x180020410`
- `0x1800205a4`
- `0x180020834`
- `0x18002550c`
- `0x1800259d8`
- `0x1800259f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
winrt::Windows::UI::Accessibility::implementation::ScreenReaderService *__fastcall winrt::Windows::UI::Accessibility::implementation::ScreenReaderService::ScreenReaderService(
        winrt::Windows::UI::Accessibility::implementation::ScreenReaderService *this)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rax
  __int64 v6; // [rsp+20h] [rbp-49h] BYREF
  __int64 v7; // [rsp+28h] [rbp-41h] BYREF
  _BYTE v8[8]; // [rsp+30h] [rbp-39h] BYREF
  winrt::Windows::UI::Accessibility::implementation::ScreenReaderService *v9; // [rsp+38h] [rbp-31h]
  _BYTE v10[8]; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v11[14]; // [rsp+48h] [rbp-21h] BYREF

  v9 = this;
  winrt::impl::producers_base<winrt::Windows::UI::Accessibility::implementation::ScreenReaderService,std::tuple<winrt::Windows::UI::Accessibility::ScreenReaderService>>::producers_base<winrt::Windows::UI::Accessibility::implementation::ScreenReaderService,std::tuple<winrt::Windows::UI::Accessibility::ScreenReaderService>>((char *)this + 16);
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  std::atomic<unsigned __int64>::atomic<unsigned __int64>((char *)this + 8);
  *(_QWORD *)this = &winrt::impl::heap_implements<winrt::Windows::UI::Accessibility::implementation::ScreenReaderService>::`vftable';
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  winrt::impl::root_implements<winrt::Windows::UI::Shell::implementation::FocusSessionManager,winrt::Windows::UI::Shell::FocusSessionManager>::get_weak<winrt::Windows::UI::Shell::implementation::FocusSessionManager>(
    this,
    &v6);
  v2 = v6;
  v6 = 0;
  v11[0] = &off_180036EB0;
  v7 = 0;
  v11[1] = v2;
  v11[13] = v11;
  lambda_a5002306207cfcb53d179eafdcf275e5_::__lambda_a5002306207cfcb53d179eafdcf275e5_(&v7);
  v4 = wil::make_wnf_subscription<winrt::Windows::UI::Accessibility::implementation::ScreenReaderService::ScreenReaderPositionChangedEventPayload>(
         v8,
         v3,
         v10);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
    (char *)this + 24,
    v4);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(v8);
  wistd::function<void (winrt::Windows::UI::Accessibility::implementation::ScreenReaderService::ScreenReaderPositionChangedEventPayload const &)>::~function<void (winrt::Windows::UI::Accessibility::implementation::ScreenReaderService::ScreenReaderPositionChangedEventPayload const &)>(v10);
  if ( v6 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v6);
  return this;
}

```

## disassembly

```asm
0x1800259f0  mov     [rsp-8+arg_8], rbx
0x1800259f5  mov     [rsp-8+arg_10], rdi
0x1800259fa  push    rbp
0x1800259fb  lea     rbp, [rsp-57h]
0x180025a00  sub     rsp, 0C0h
0x180025a07  mov     rax, cs:__security_cookie
0x180025a0e  xor     rax, rsp
0x180025a11  mov     [rbp+57h+var_8], rax
0x180025a15  mov     rdi, rcx
0x180025a18  mov     [rbp+57h+var_88], rcx
0x180025a1c  add     rcx, 10h
0x180025a20  call    ??0?$producers_base@UScreenReaderService@implementation@Accessibility@UI@Windows@winrt@@V?$tuple@UScreenReaderService@Accessibility@UI@Windows@winrt@@@std@@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<winrt::Windows::UI::Accessibility::implementation::ScreenReaderService,std::tuple<winrt::Windows::UI::Accessibility::ScreenReaderService>>::producers_base<winrt::Windows::UI::Accessibility::implementation::ScreenReaderService,std::tuple<winrt::Windows::UI::Accessibility::ScreenReaderService>>(void)
0x180025a25  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180025a2c  lea     rcx, [rdi+8]
0x180025a30  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x180025a35  nop
0x180025a36  lea     rax, ??_7?$heap_implements@UScreenReaderService@implementation@Accessibility@UI@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::UI::Accessibility::implementation::ScreenReaderService>::`vftable'
0x180025a3d  mov     [rdi], rax
0x180025a40  mov     qword ptr [rdi+18h], 0
0x180025a48  mov     qword ptr [rdi+20h], 0
0x180025a50  mov     qword ptr [rdi+28h], 0
0x180025a58  mov     qword ptr [rdi+30h], 0
0x180025a60  lea     rdx, [rbp+57h+var_A0]
0x180025a64  mov     rcx, rdi
0x180025a67  call    ??$get_weak@UFocusSessionManager@implementation@Shell@UI@Windows@winrt@@@?$root_implements@UFocusSessionManager@implementation@Shell@UI@Windows@winrt@@U13456@@impl@winrt@@IEAA?AU?$weak_ref@UFocusSessionManager@implementation@Shell@UI@Windows@winrt@@@2@XZ; winrt::impl::root_implements<winrt::Windows::UI::Shell::implementation::FocusSessionManager,winrt::Windows::UI::Shell::FocusSessionManager>::get_weak<winrt::Windows::UI::Shell::implementation::FocusSessionManager>(void)
0x180025a6c  nop
0x180025a6d  mov     rax, [rbp+57h+var_A0]
0x180025a71  mov     [rbp+57h+var_A0], 0
0x180025a79  lea     rcx, off_180036EB0
0x180025a80  mov     [rbp+57h+var_78], rcx
0x180025a84  mov     [rbp+57h+var_98], 0
0x180025a8c  mov     [rbp+57h+var_70], rax
0x180025a90  lea     rax, [rbp+57h+var_78]
0x180025a94  mov     [rbp+57h+var_10], rax
0x180025a98  lea     rcx, [rbp+57h+var_98]
0x180025a9c  call    _lambda_a5002306207cfcb53d179eafdcf275e5_____lambda_a5002306207cfcb53d179eafdcf275e5_
0x180025aa1  nop
0x180025aa2  lea     r8, [rbp+57h+var_80]
0x180025aa6  lea     rcx, [rbp+57h+var_90]
0x180025aaa  call    ??$make_wnf_subscription@UScreenReaderPositionChangedEventPayload@ScreenReaderService@implementation@Accessibility@UI@Windows@winrt@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXAEBUScreenReaderPositionChangedEventPayload@ScreenReaderService@implementation@Accessibility@UI@Windows@winrt@@@Z@wistd@@K@Z; wil::make_wnf_subscription<winrt::Windows::UI::Accessibility::implementation::ScreenReaderService::ScreenReaderPositionChangedEventPayload>(_WNF_STATE_NAME const &,wistd::function<void (winrt::Windows::UI::Accessibility::implementation::ScreenReaderService::ScreenReaderPositionChangedEventPayload const &)> &&,ulong)
0x180025aaf  mov     rdx, rax
0x180025ab2  lea     rcx, [rdi+18h]
0x180025ab6  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x180025abb  lea     rcx, [rbp+57h+var_90]
0x180025abf  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x180025ac4  nop
0x180025ac5  lea     rcx, [rbp+57h+var_80]
0x180025ac9  call    ??1?$function@$$A6AXAEBUScreenReaderPositionChangedEventPayload@ScreenReaderService@implementation@Accessibility@UI@Windows@winrt@@@Z@wistd@@QEAA@XZ; wistd::function<void (winrt::Windows::UI::Accessibility::implementation::ScreenReaderService::ScreenReaderPositionChangedEventPayload const &)>::~function<void (winrt::Windows::UI::Accessibility::implementation::ScreenReaderService::ScreenReaderPositionChangedEventPayload const &)>(void)
0x180025ace  nop
0x180025acf  cmp     [rbp+57h+var_A0], 0
0x180025ad4  jz      short loc_180025AE0
0x180025ad6  lea     rcx, [rbp+57h+var_A0]
0x180025ada  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180025adf  nop
0x180025ae0  mov     rax, rdi
0x180025ae3  mov     rcx, [rbp+57h+var_8]
0x180025ae7  xor     rcx, rsp; StackCookie
0x180025aea  call    __security_check_cookie
0x180025aef  lea     r11, [rsp+0C0h+var_s0]
0x180025af7  mov     rbx, [r11+18h]
0x180025afb  mov     rdi, [r11+20h]
0x180025aff  mov     rsp, r11
0x180025b02  pop     rbp
0x180025b03  retn
```
