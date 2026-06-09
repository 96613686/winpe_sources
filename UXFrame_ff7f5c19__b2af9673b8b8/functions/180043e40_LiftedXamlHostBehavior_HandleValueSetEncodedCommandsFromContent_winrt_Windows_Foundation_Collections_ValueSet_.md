# LiftedXamlHostBehavior::HandleValueSetEncodedCommandsFromContent(winrt::Windows::Foundation::Collections::ValueSet const &)

- ea: `0x180043e40`
- end: `0x1800444eb`
- name: `?HandleValueSetEncodedCommandsFromContent@LiftedXamlHostBehavior@@UEAAXAEBUValueSet@Collections@Foundation@Windows@winrt@@@Z`
- size: `1707`
- prototype: `void __fastcall(LiftedXamlHostBehavior *__hidden this, const struct winrt::Windows::Foundation::Collections::ValueSet *)`
- caller_count: `0`
- callee_count: `37`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002b20`
- `0x1800041c4`
- `0x180004240`
- `0x1800043a0`
- `0x1800043f4`
- `0x1800049ac`
- `0x180006698`
- `0x180006d08`
- `0x180007794`
- `0x1800088ac`
- `0x1800089c0`
- `0x18000d0f0`
- `0x18000d810`
- `0x18000eba0`
- `0x18001047c`
- `0x18001049c`
- `0x180013460`
- `0x180017124`
- `0x180017514`
- `0x180020cac`
- `0x18003739c`
- `0x1800376fc`
- `0x180037740`
- `0x1800377a4`
- `0x180037da8`
- `0x18003c2bc`
- `0x18003c6cc`
- `0x18003cf98`
- `0x18003d190`
- `0x18003d5e0`
- `0x18003dc04`
- `0x18003e764`
- `0x180040414`
- `0x180041bc4`
- `0x180043e40`
- `0x1800450d8`
- `0x18005a010`

## import_xrefs

- `dwmapi!DwmSetWindowAttribute` at `0x180044051`
- `dwmapi!DwmSetWindowAttribute` at `0x180044051`

## string_xrefs

- `0x180044418`: `CustomAnimationHideCompleted`
- `0x1800443bb`: `CustomAnimationShowCompleted`
- `0x1800444a0`: `pcshell\shell\uxframe\dll\LiftedXamlHostBehavior.h`
- `0x1800444c3`: `pcshell\shell\uxframe\dll\LiftedXamlHostBehavior.h`
- `0x1800444d9`: `pcshell\shell\uxframe\dll\LiftedXamlHostBehavior.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall LiftedXamlHostBehavior::HandleValueSetEncodedCommandsFromContent(
        LiftedXamlHostBehavior *this,
        const struct winrt::Windows::Foundation::Collections::ValueSet *a2)
{
  void (__fastcall ***v4)(_QWORD, __int64 *, LiftedXamlHostBehavior **); // rcx
  unsigned int v5; // eax
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *v6; // rcx
  void (__fastcall ***v7)(_QWORD, __int64 *, LiftedXamlHostBehavior **); // rcx
  __int64 v8; // rcx
  LiftedXamlHostBehavior *v9; // rbx
  unsigned int v10; // eax
  void (__fastcall ***v11)(_QWORD, __int64 *, LiftedXamlHostBehavior **); // rcx
  LiftedXamlHostBehavior *v12; // rbx
  LiftedXamlHostBehavior *v13; // rsi
  __int64 v14; // r8
  LiftedXamlHostBehavior **v15; // rax
  LiftedXamlHostBehavior *v16; // rcx
  LiftedXamlHostBehavior *v17; // rcx
  void (__fastcall ***v18)(_QWORD, __int64 *, LiftedXamlHostBehavior **); // rcx
  LiftedXamlHostBehavior *v19; // rsi
  __int64 v20; // rax
  LiftedXamlAcrylicBackground *v21; // rbx
  double v22; // xmm0_8
  __int64 v23; // rax
  const char *v24; // r9
  const char *v25; // r9
  unsigned int v26; // eax
  const wchar_t *v27; // [rsp+28h] [rbp-49h] BYREF
  int v28; // [rsp+30h] [rbp-41h] BYREF
  std::_Ref_count_base *v29[2]; // [rsp+38h] [rbp-39h]
  LiftedXamlHostBehavior *v30; // [rsp+50h] [rbp-21h] BYREF
  LiftedXamlHostBehavior *v31; // [rsp+58h] [rbp-19h] BYREF
  LiftedXamlHostBehavior *v32; // [rsp+60h] [rbp-11h] BYREF
  LiftedXamlHostBehavior *v33; // [rsp+68h] [rbp-9h] BYREF
  LiftedXamlHostBehavior *v34; // [rsp+70h] [rbp-1h] BYREF
  LiftedXamlHostBehavior *pvAttribute; // [rsp+78h] [rbp+7h] BYREF
  LiftedXamlHostBehavior *v36; // [rsp+80h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]

  winrt::hstring::hstring((winrt::hstring *)&v32, L"SetSystemBackdrop");
  try_get_enum_from_valueset<enum UXFrameHelpers::PropertyKeys::SystemBackdropType>(&v33, &v32, a2);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v32);
  if ( BYTE4(v33) )
  {
    v34 = 0;
    if ( (_DWORD)v33 )
    {
      switch ( (_DWORD)v33 )
      {
        case 1:
          v7 = *(void (__fastcall ****)(_QWORD, __int64 *, LiftedXamlHostBehavior **))winrt::Microsoft::UI::Xaml::Media::MicaBackdrop::MicaBackdrop((winrt::Microsoft::UI::Xaml::Media::MicaBackdrop *)&v27);
          v32 = 0;
          if ( v7 )
            (**v7)(v7, winrt::impl::guid_v<winrt::Microsoft::UI::Xaml::Media::ISystemBackdrop>, &v32);
          winrt::Windows::Foundation::IUnknown::operator=(&v34, &v32);
          winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v32);
          v6 = (winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v27;
          break;
        case 2:
          winrt::Microsoft::UI::Xaml::Media::MicaBackdrop::MicaBackdrop((winrt::Microsoft::UI::Xaml::Media::MicaBackdrop *)&v32);
          v28 = 0;
          *(_OWORD *)v29 = 0;
          v5 = (*(__int64 (__fastcall **)(LiftedXamlHostBehavior *, __int64))(*(_QWORD *)v32 + 56LL))(v32, 1);
          winrt::check_hresult(&v33, v5, &v28);
          v33 = 0;
          if ( v32 )
            (**(void (__fastcall ***)(LiftedXamlHostBehavior *, __int64 *, LiftedXamlHostBehavior **))v32)(
              v32,
              winrt::impl::guid_v<winrt::Microsoft::UI::Xaml::Media::ISystemBackdrop>,
              &v33);
          winrt::Windows::Foundation::IUnknown::operator=(&v34, &v33);
          winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v33);
          v6 = (winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v32;
          break;
        case 3:
          v4 = *(void (__fastcall ****)(_QWORD, __int64 *, LiftedXamlHostBehavior **))winrt::Microsoft::UI::Xaml::Media::DesktopAcrylicBackdrop::DesktopAcrylicBackdrop((winrt::Microsoft::UI::Xaml::Media::DesktopAcrylicBackdrop *)&v27);
          if ( v4 )
          {
            v32 = 0;
            (**v4)(v4, winrt::impl::guid_v<winrt::Microsoft::UI::Xaml::Media::ISystemBackdrop>, &v32);
            v33 = v32;
          }
          else
          {
            v33 = 0;
          }
          winrt::Windows::Foundation::IUnknown::operator=(&v34, &v33);
          winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v33);
          winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v27);
          goto LABEL_17;
        default:
          v26 = wil::verify_hresult<long>(2147942487LL);
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            (void *)0xDC,
            (unsigned int)"pcshell\\shell\\uxframe\\dll\\LiftedXamlHostBehavior.h",
            (const char *)v26,
            (int)v27);
      }
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(v6);
    }
LABEL_17:
    v8 = *((_QWORD *)this + 9);
    v28 = 0;
    *(_OWORD *)v29 = 0;
    v9 = v34;
    v10 = (*(__int64 (__fastcall **)(__int64, LiftedXamlHostBehavior *))(*(_QWORD *)v8 + 80LL))(v8, v34);
    winrt::check_hresult(&v33, v10, &v28);
    LODWORD(pvAttribute) = v9 != 0;
    DwmSetWindowAttribute(*((HWND *)this + 7), 0x11u, &pvAttribute, 4u);
    winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v34);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl) )
  {
    winrt::hstring::hstring((winrt::hstring *)&v32, L"SetClippingElementName");
    ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(&v33, &v32, a2);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v32);
    if ( v33 )
    {
      v27 = winrt::hstring::c_str((winrt::hstring *)&v33);
      v32 = this;
      XamlHostTelemetry::DynamicClippingControl<LiftedXamlHostBehavior *,wchar_t const *>(&v32, &v27);
      v11 = *(void (__fastcall ****)(_QWORD, __int64 *, LiftedXamlHostBehavior **))LiftedXamlHostBehavior::FindElementByName(
                                                                                     this,
                                                                                     &v27,
                                                                                     &v33);
      if ( v11 )
      {
        v32 = 0;
        (**v11)(v11, winrt::impl::guid_v<winrt::Microsoft::UI::Xaml::IFrameworkElement>, &v32);
        v12 = v32;
        v13 = v32;
      }
      else
      {
        v12 = 0;
        v13 = 0;
      }
      v34 = v12;
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v27);
      if ( v13 )
      {
        v30 = this;
        v31 = v12;
        winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)&v31);
        winrt::Windows::Foundation::EventHandler<winrt::Windows::Foundation::IInspectable>::EventHandler<winrt::Windows::Foundation::IInspectable>(
          &v32,
          &v30);
        v15 = (LiftedXamlHostBehavior **)winrt::impl::consume_Microsoft_UI_Xaml_IFrameworkElement<winrt::Microsoft::UI::Xaml::IFrameworkElement>::LayoutUpdated(
                                           &v34,
                                           &v28,
                                           v14,
                                           &v32);
        v16 = *v15;
        *v15 = 0;
        pvAttribute = v16;
        v36 = v15[1];
        std::swap<winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement>,0>(&pvAttribute, (char *)this + 208);
        v17 = v36;
        v36 = (LiftedXamlHostBehavior *)*((_QWORD *)this + 27);
        *((_QWORD *)this + 27) = v17;
        __1__event_revoker_UIFrameworkElement_Xaml_UI_Microsoft_winrt___MP8type___abi_UIFrameworkElement_Xaml_UI_Microsoft_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BCDA_AA_impl_winrt__QEAA_XZ(&pvAttribute);
        __1__event_revoker_UIFrameworkElement_Xaml_UI_Microsoft_winrt___MP8type___abi_UIFrameworkElement_Xaml_UI_Microsoft_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BCDA_AA_impl_winrt__QEAA_XZ(&v28);
        if ( v32 )
          winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v32);
        LiftedXamlHostBehavior::ComputeElementClip(
          this,
          (const struct winrt::Microsoft::UI::Xaml::FrameworkElement *)&v34);
      }
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v34);
    }
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v33);
    winrt::hstring::hstring((winrt::hstring *)&v32, L"SetAcrylicElementName");
    ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(&v34, &v32, a2);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v32);
    if ( v34 )
    {
      v27 = winrt::hstring::c_str((winrt::hstring *)&v34);
      v32 = this;
      XamlHostTelemetry::AcrylicHostControl<LiftedXamlHostBehavior *,wchar_t const *>(&v32, &v27);
      v18 = *(void (__fastcall ****)(_QWORD, __int64 *, LiftedXamlHostBehavior **))LiftedXamlHostBehavior::FindElementByName(
                                                                                     this,
                                                                                     &v27,
                                                                                     &v34);
      if ( v18 )
      {
        v32 = 0;
        (**v18)(v18, winrt::impl::guid_v<winrt::Microsoft::UI::Xaml::IFrameworkElement>, &v32);
        v19 = v32;
        pvAttribute = v32;
      }
      else
      {
        pvAttribute = 0;
        v19 = 0;
      }
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v27);
      if ( v19 )
      {
        if ( !*((_QWORD *)this + 28) )
        {
          v20 = std::make_shared<LiftedXamlAcrylicBackground,winrt::Windows::System::DispatcherQueue &>(
                  &v28,
                  (char *)this + 48);
          __4__shared_ptr_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___std__QEAAAEAV01___QEAV01__Z(
            (char *)this + 224,
            v20);
          if ( v29[0] )
            std::_Ref_count_base::_Decref(v29[0]);
        }
        v21 = (LiftedXamlAcrylicBackground *)*((_QWORD *)this + 28);
        v32 = 0;
        (**(void (__fastcall ***)(LiftedXamlHostBehavior *, __int64 *, LiftedXamlHostBehavior **))v19)(
          v19,
          winrt::impl::guid_v<winrt::Microsoft::UI::Xaml::IUIElement>,
          &v32);
        v33 = v32;
        LiftedXamlAcrylicBackground::AttachToElement(v21, (const struct winrt::Microsoft::UI::Xaml::UIElement *)&v33);
        winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v33);
        v27 = (const wchar_t *)this;
        XamlHostTelemetry::AcrylicAttached<LiftedXamlHostBehavior *>(&v27);
      }
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&pvAttribute);
    }
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v34);
    winrt::param::hstring::hstring((winrt::param::hstring *)&v28, L"SetAcrylicCornerRadius");
    if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::HasKey(
                            a2,
                            &v28) )
    {
      winrt::hstring::hstring((winrt::hstring *)&v32, L"SetAcrylicCornerRadius");
      v22 = ValueSetUtils::get_value_or<float,winrt::Windows::Foundation::Collections::ValueSet>(&v32, a2);
      LODWORD(pvAttribute) = LODWORD(v22);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v32);
      v27 = (const wchar_t *)this;
      XamlHostTelemetry::AcrylicCornerRadius<LiftedXamlHostBehavior *,float &>(&v27, &pvAttribute);
      if ( !*((_QWORD *)this + 28) )
      {
        v23 = std::make_shared<LiftedXamlAcrylicBackground,winrt::Windows::System::DispatcherQueue &>(
                &v28,
                (char *)this + 48);
        __4__shared_ptr_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___std__QEAAAEAV01___QEAV01__Z(
          (char *)this + 224,
          v23);
        if ( v29[0] )
          std::_Ref_count_base::_Decref(v29[0]);
      }
      LiftedXamlAcrylicBackground::CornerRadius(*((LiftedXamlAcrylicBackground **)this + 28), *(float *)&v22);
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl)
    && *((_DWORD *)this + 32) == 3 )
  {
    winrt::param::hstring::hstring((winrt::param::hstring *)&v28, L"CustomAnimationShowCompleted");
    if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::HasKey(
                            a2,
                            &v28) )
    {
      if ( *((_BYTE *)this + 192) && *((_DWORD *)this + 47) != 2 )
      {
        if ( *((_DWORD *)this + 46) != 2 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x121,
            (unsigned int)"pcshell\\shell\\uxframe\\dll\\LiftedXamlHostBehavior.h",
            v24);
        *((_DWORD *)this + 46) = 0;
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 24LL))(*((_QWORD *)this + 5));
      }
      *((_BYTE *)this + 192) = 0;
    }
    winrt::param::hstring::hstring((winrt::param::hstring *)&v28, L"CustomAnimationHideCompleted");
    if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::HasKey(
                            a2,
                            &v28) )
    {
      if ( *((_BYTE *)this + 192) && *((_DWORD *)this + 47) != 3 )
      {
        if ( *((_DWORD *)this + 46) != 3 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x12C,
            (unsigned int)"pcshell\\shell\\uxframe\\dll\\LiftedXamlHostBehavior.h",
            v25);
        *((_DWORD *)this + 46) = 1;
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 32LL))(*((_QWORD *)this + 5));
      }
      *((_BYTE *)this + 192) = 0;
    }
  }
}

```

## disassembly

```asm
0x180043e40  mov     rax, rsp
0x180043e43  mov     [rax+18h], rbx
0x180043e47  push    rbp
0x180043e48  push    rsi
0x180043e49  push    rdi
0x180043e4a  push    r14
0x180043e4c  push    r15
0x180043e4e  lea     rbp, [rax-5Fh]
0x180043e52  sub     rsp, 0A0h
0x180043e59  movaps  xmmword ptr [rax-38h], xmm6
0x180043e5d  mov     rax, cs:__security_cookie
0x180043e64  xor     rax, rsp
0x180043e67  mov     [rbp+57h+var_40], rax
0x180043e6b  mov     r14, rdx
0x180043e6e  mov     rdi, rcx
0x180043e71  lea     rdx, aSetsystembackd; "SetSystemBackdrop"
0x180043e78  lea     rcx, [rbp+57h+var_68]; this
0x180043e7c  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x180043e81  nop
0x180043e82  mov     r8, r14
0x180043e85  lea     rdx, [rbp+57h+var_68]
0x180043e89  lea     rcx, [rbp+57h+var_60]
0x180043e8d  call    ??$try_get_enum_from_valueset@W4SystemBackdropType@PropertyKeys@UXFrameHelpers@@@@YA?AV?$optional@W4SystemBackdropType@PropertyKeys@UXFrameHelpers@@@std@@AEBUhstring@winrt@@AEBUValueSet@Collections@Foundation@Windows@3@@Z; try_get_enum_from_valueset<UXFrameHelpers::PropertyKeys::SystemBackdropType>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x180043e92  nop
0x180043e93  lea     rcx, [rbp+57h+var_68]
0x180043e97  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180043e9c  xor     r15d, r15d
0x180043e9f  cmp     byte ptr [rbp+57h+var_60+4], r15b
0x180043ea3  jz      loc_180044061
0x180043ea9  mov     [rbp+57h+var_58], r15
0x180043ead  mov     rax, [rbp+57h+var_60]
0x180043eb1  test    eax, eax
0x180043eb3  jz      loc_180044001
0x180043eb9  sub     eax, 1
0x180043ebc  jz      loc_180043FAF
0x180043ec2  sub     eax, 1
0x180043ec5  jz      short loc_180043F2D
0x180043ec7  cmp     eax, 1
0x180043eca  jnz     loc_1800444B2
0x180043ed0  lea     rcx, [rbp+57h+var_A0]; this
0x180043ed4  call    ??0DesktopAcrylicBackdrop@Media@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::Media::DesktopAcrylicBackdrop::DesktopAcrylicBackdrop(void)
0x180043ed9  mov     rcx, [rax]
0x180043edc  test    rcx, rcx
0x180043edf  jnz     short loc_180043EE7
0x180043ee1  mov     [rbp+57h+var_60], r15
0x180043ee5  jmp     short loc_180043F09
0x180043ee7  mov     [rbp+57h+var_68], r15
0x180043eeb  mov     rax, [rcx]
0x180043eee  lea     r8, [rbp+57h+var_68]
0x180043ef2  lea     rdx, ??$guid_v@UISystemBackdrop@Media@Xaml@UI@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::UI::Xaml::Media::ISystemBackdrop>
0x180043ef9  mov     rax, [rax]
0x180043efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f01  mov     rax, [rbp+57h+var_68]
0x180043f05  mov     [rbp+57h+var_60], rax
0x180043f09  lea     rdx, [rbp+57h+var_60]
0x180043f0d  lea     rcx, [rbp+57h+var_58]
0x180043f11  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x180043f16  lea     rcx, [rbp+57h+var_60]; this
0x180043f1a  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180043f1f  lea     rcx, [rbp+57h+var_A0]; this
0x180043f23  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180043f28  jmp     loc_180044001
0x180043f2d  lea     rcx, [rbp+57h+var_68]; this
0x180043f31  call    ??0MicaBackdrop@Media@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::Media::MicaBackdrop::MicaBackdrop(void)
0x180043f36  nop
0x180043f37  mov     rcx, [rbp+57h+var_68]
0x180043f3b  mov     [rbp+57h+var_98], r15d
0x180043f3f  xorps   xmm0, xmm0
0x180043f42  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x180043f47  mov     rax, [rcx]
0x180043f4a  mov     edx, 1
0x180043f4f  mov     rax, [rax+38h]
0x180043f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f58  lea     r8, [rbp+57h+var_98]
0x180043f5c  mov     edx, eax
0x180043f5e  lea     rcx, [rbp+57h+var_60]
0x180043f62  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180043f67  mov     rcx, [rbp+57h+var_68]
0x180043f6b  mov     [rbp+57h+var_60], r15
0x180043f6f  test    rcx, rcx
0x180043f72  jz      short loc_180043F92
0x180043f74  mov     rax, [rcx]
0x180043f77  lea     r8, [rbp+57h+var_60]
0x180043f7b  lea     rdx, ??$guid_v@UISystemBackdrop@Media@Xaml@UI@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::UI::Xaml::Media::ISystemBackdrop>
0x180043f82  mov     rax, [rax]
0x180043f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f8a  mov     rax, [rbp+57h+var_60]
0x180043f8e  mov     [rbp+57h+var_60], rax
0x180043f92  lea     rdx, [rbp+57h+var_60]
0x180043f96  lea     rcx, [rbp+57h+var_58]
0x180043f9a  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x180043f9f  lea     rcx, [rbp+57h+var_60]; this
0x180043fa3  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180043fa8  nop
0x180043fa9  lea     rcx, [rbp+57h+var_68]
0x180043fad  jmp     short loc_180043FFC
0x180043faf  lea     rcx, [rbp+57h+var_A0]; this
0x180043fb3  call    ??0MicaBackdrop@Media@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::Media::MicaBackdrop::MicaBackdrop(void)
0x180043fb8  mov     rcx, [rax]
0x180043fbb  mov     [rbp+57h+var_68], r15
0x180043fbf  test    rcx, rcx
0x180043fc2  jz      short loc_180043FE2
0x180043fc4  mov     rax, [rcx]
0x180043fc7  lea     r8, [rbp+57h+var_68]
0x180043fcb  lea     rdx, ??$guid_v@UISystemBackdrop@Media@Xaml@UI@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::UI::Xaml::Media::ISystemBackdrop>
0x180043fd2  mov     rax, [rax]
0x180043fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043fda  mov     rax, [rbp+57h+var_68]
0x180043fde  mov     [rbp+57h+var_68], rax
0x180043fe2  lea     rdx, [rbp+57h+var_68]
0x180043fe6  lea     rcx, [rbp+57h+var_58]
0x180043fea  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x180043fef  lea     rcx, [rbp+57h+var_68]; this
0x180043ff3  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180043ff8  lea     rcx, [rbp+57h+var_A0]; this
0x180043ffc  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180044001  mov     rcx, [rdi+48h]
0x180044005  mov     [rbp+57h+var_98], r15d
0x180044009  xorps   xmm0, xmm0
0x18004400c  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x180044011  mov     rax, [rcx]
0x180044014  mov     rbx, [rbp+57h+var_58]
0x180044018  mov     rdx, rbx
0x18004401b  mov     rax, [rax+50h]
0x18004401f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044024  lea     r8, [rbp+57h+var_98]
0x180044028  mov     edx, eax
0x18004402a  lea     rcx, [rbp+57h+var_60]
0x18004402e  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180044033  mov     eax, r15d
0x180044036  test    rbx, rbx
0x180044039  setnz   al
0x18004403c  mov     dword ptr [rbp+57h+pvAttribute], eax
0x18004403f  mov     r9d, 4; cbAttribute
0x180044045  lea     r8, [rbp+57h+pvAttribute]; pvAttribute
0x180044049  lea     edx, [r9+0Dh]; dwAttribute
0x18004404d  mov     rcx, [rdi+38h]; hwnd
0x180044051  call    cs:__imp_DwmSetWindowAttribute
0x180044057  nop
0x180044058  lea     rcx, [rbp+57h+var_58]; this
0x18004405c  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180044061  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x180044068  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x18004406d  test    al, al
0x18004406f  jz      loc_18004439A
0x180044075  lea     rdx, aSetclippingele; "SetClippingElementName"
0x18004407c  lea     rcx, [rbp+57h+var_68]; this
0x180044080  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x180044085  nop
0x180044086  mov     r8, r14
0x180044089  lea     rdx, [rbp+57h+var_68]
0x18004408d  lea     rcx, [rbp+57h+var_60]
0x180044091  call    ??$try_get_value@Uhstring@winrt@@UValueSet@Collections@Foundation@Windows@2@@ValueSetUtils@@YA?AUhstring@winrt@@AEBU12@AEBUValueSet@Collections@Foundation@Windows@2@@Z; ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x180044096  nop
0x180044097  lea     rcx, [rbp+57h+var_68]
0x18004409b  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800440a0  cmp     [rbp+57h+var_60], r15
0x1800440a4  jz      loc_1800441BD
0x1800440aa  lea     rcx, [rbp+57h+var_60]; this
0x1800440ae  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1800440b3  mov     [rbp+57h+var_A0], rax
0x1800440b7  mov     [rbp+57h+var_68], rdi
0x1800440bb  lea     rdx, [rbp+57h+var_A0]
0x1800440bf  lea     rcx, [rbp+57h+var_68]
0x1800440c3  call    ??$DynamicClippingControl@PEAVLiftedXamlHostBehavior@@PEB_W@XamlHostTelemetry@@SAX$$QEAPEAVLiftedXamlHostBehavior@@$$QEAPEB_W@Z; XamlHostTelemetry::DynamicClippingControl<LiftedXamlHostBehavior *,wchar_t const *>(LiftedXamlHostBehavior * &&,wchar_t const * &&)
0x1800440c8  lea     r8, [rbp+57h+var_60]
0x1800440cc  lea     rdx, [rbp+57h+var_A0]
0x1800440d0  mov     rcx, rdi
0x1800440d3  call    ?FindElementByName@LiftedXamlHostBehavior@@AEAA?AUUIElement@Xaml@UI@Microsoft@winrt@@AEBUhstring@6@@Z; LiftedXamlHostBehavior::FindElementByName(winrt::hstring const &)
0x1800440d8  mov     rcx, [rax]
0x1800440db  test    rcx, rcx
0x1800440de  jnz     short loc_1800440E8
0x1800440e0  mov     rbx, r15
0x1800440e3  mov     rsi, r15
0x1800440e6  jmp     short loc_180044109
0x1800440e8  mov     [rbp+57h+var_68], r15
0x1800440ec  mov     rax, [rcx]
0x1800440ef  lea     r8, [rbp+57h+var_68]
0x1800440f3  lea     rdx, ??$guid_v@UIFrameworkElement@Xaml@UI@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::UI::Xaml::IFrameworkElement>
0x1800440fa  mov     rax, [rax]
0x1800440fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044102  mov     rbx, [rbp+57h+var_68]
0x180044106  mov     rsi, rbx
0x180044109  mov     [rbp+57h+var_58], rbx
0x18004410d  lea     rcx, [rbp+57h+var_A0]; this
0x180044111  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180044116  test    rsi, rsi
0x180044119  jz      loc_1800441B3
0x18004411f  mov     [rbp+57h+var_78], rdi
0x180044123  mov     [rbp+57h+var_70], rbx
0x180044127  lea     rcx, [rbp+57h+var_70]; this
0x18004412b  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x180044130  lea     rdx, [rbp+57h+var_78]
0x180044134  lea     rcx, [rbp+57h+var_68]
0x180044138  call    ??$?0V_lambda_d4c1e087e80a002cbe08f58e257b35fb_@@@?$EventHandler@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@QEAA@V_lambda_d4c1e087e80a002cbe08f58e257b35fb_@@@Z; winrt::Windows::Foundation::EventHandler<winrt::Windows::Foundation::IInspectable>::EventHandler<winrt::Windows::Foundation::IInspectable>(_lambda_d4c1e087e80a002cbe08f58e257b35fb_)
0x18004413d  nop
0x18004413e  lea     r9, [rbp+57h+var_68]
0x180044142  lea     rdx, [rbp+57h+var_98]
0x180044146  lea     rcx, [rbp+57h+var_58]
0x18004414a  call    ?LayoutUpdated@?$consume_Microsoft_UI_Xaml_IFrameworkElement@UIFrameworkElement@Xaml@UI@Microsoft@winrt@@@impl@winrt@@QEBA@Uauto_revoke_t@3@AEBU?$EventHandler@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@3@@Z; winrt::impl::consume_Microsoft_UI_Xaml_IFrameworkElement<winrt::Microsoft::UI::Xaml::IFrameworkElement>::LayoutUpdated(winrt::auto_revoke_t,winrt::Windows::Foundation::EventHandler<winrt::Windows::Foundation::IInspectable> const &)
0x18004414f  lea     rbx, [rdi+0D0h]
0x180044156  mov     rcx, [rax]
0x180044159  mov     [rax], r15
0x18004415c  mov     [rbp+57h+pvAttribute], rcx
0x180044160  mov     rax, [rax+8]
0x180044164  mov     [rbp+57h+var_48], rax
0x180044168  mov     rdx, rbx
0x18004416b  lea     rcx, [rbp+57h+pvAttribute]
0x18004416f  call    ??$swap@U?$weak_ref@UIFrameworkElement@Xaml@UI@Windows@winrt@@@winrt@@$0A@@std@@YAXAEAU?$weak_ref@UIFrameworkElement@Xaml@UI@Windows@winrt@@@winrt@@0@Z; std::swap<winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement>,0>(winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement> &,winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement> &)
0x180044174  mov     rcx, [rbp+57h+var_48]
0x180044178  mov     rax, [rbx+8]
0x18004417c  mov     [rbp+57h+var_48], rax
0x180044180  mov     [rbx+8], rcx
0x180044184  lea     rcx, [rbp+57h+pvAttribute]
0x180044188  call    ??1?$event_revoker@UIFrameworkElement@Xaml@UI@Microsoft@winrt@@$MP8type@?$abi@UIFrameworkElement@Xaml@UI@Microsoft@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BCDA@AA@impl@winrt@@QEAA@XZ
0x18004418d  lea     rcx, [rbp+57h+var_98]
0x180044191  call    ??1?$event_revoker@UIFrameworkElement@Xaml@UI@Microsoft@winrt@@$MP8type@?$abi@UIFrameworkElement@Xaml@UI@Microsoft@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BCDA@AA@impl@winrt@@QEAA@XZ
0x180044196  nop
0x180044197  cmp     [rbp+57h+var_68], r15
0x18004419b  jz      short loc_1800441A6
0x18004419d  lea     rcx, [rbp+57h+var_68]
0x1800441a1  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x1800441a6  lea     rdx, [rbp+57h+var_58]; struct winrt::Microsoft::UI::Xaml::FrameworkElement *
0x1800441aa  mov     rcx, rdi; this
0x1800441ad  call    ?ComputeElementClip@LiftedXamlHostBehavior@@AEAAXAEBUFrameworkElement@Xaml@UI@Microsoft@winrt@@@Z; LiftedXamlHostBehavior::ComputeElementClip(winrt::Microsoft::UI::Xaml::FrameworkElement const &)
0x1800441b2  nop
0x1800441b3  lea     rcx, [rbp+57h+var_58]; this
0x1800441b7  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x1800441bc  nop
0x1800441bd  lea     rcx, [rbp+57h+var_60]
0x1800441c1  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800441c6  lea     rdx, aSetacrylicelem; "SetAcrylicElementName"
0x1800441cd  lea     rcx, [rbp+57h+var_68]; this
0x1800441d1  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x1800441d6  nop
0x1800441d7  mov     r8, r14
0x1800441da  lea     rdx, [rbp+57h+var_68]
0x1800441de  lea     rcx, [rbp+57h+var_58]
0x1800441e2  call    ??$try_get_value@Uhstring@winrt@@UValueSet@Collections@Foundation@Windows@2@@ValueSetUtils@@YA?AUhstring@winrt@@AEBU12@AEBUValueSet@Collections@Foundation@Windows@2@@Z; ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x1800441e7  nop
0x1800441e8  lea     rcx, [rbp+57h+var_68]
0x1800441ec  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800441f1  cmp     [rbp+57h+var_58], r15
0x1800441f5  jz      loc_1800442F2
0x1800441fb  lea     rcx, [rbp+57h+var_58]; this
0x1800441ff  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x180044204  mov     [rbp+57h+var_A0], rax
0x180044208  mov     [rbp+57h+var_68], rdi
0x18004420c  lea     rdx, [rbp+57h+var_A0]
0x180044210  lea     rcx, [rbp+57h+var_68]
0x180044214  call    ??$AcrylicHostControl@PEAVLiftedXamlHostBehavior@@PEB_W@XamlHostTelemetry@@SAX$$QEAPEAVLiftedXamlHostBehavior@@$$QEAPEB_W@Z; XamlHostTelemetry::AcrylicHostControl<LiftedXamlHostBehavior *,wchar_t const *>(LiftedXamlHostBehavior * &&,wchar_t const * &&)
0x180044219  lea     r8, [rbp+57h+var_58]
0x18004421d  lea     rdx, [rbp+57h+var_A0]
0x180044221  mov     rcx, rdi
0x180044224  call    ?FindElementByName@LiftedXamlHostBehavior@@AEAA?AUUIElement@Xaml@UI@Microsoft@winrt@@AEBUhstring@6@@Z; LiftedXamlHostBehavior::FindElementByName(winrt::hstring const &)
0x180044229  mov     rcx, [rax]
0x18004422c  test    rcx, rcx
0x18004422f  jnz     short loc_18004423A
0x180044231  mov     [rbp+57h+pvAttribute], r15
0x180044235  mov     rsi, r15
0x180044238  jmp     short loc_18004425C
0x18004423a  mov     [rbp+57h+var_68], r15
0x18004423e  mov     rax, [rcx]
0x180044241  lea     r8, [rbp+57h+var_68]
0x180044245  lea     rdx, ??$guid_v@UIFrameworkElement@Xaml@UI@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::UI::Xaml::IFrameworkElement>
0x18004424c  mov     rax, [rax]
0x18004424f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044254  mov     rsi, [rbp+57h+var_68]
0x180044258  mov     [rbp+57h+pvAttribute], rsi
0x18004425c  lea     rcx, [rbp+57h+var_A0]; this
0x180044260  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180044265  test    rsi, rsi
0x180044268  jz      short loc_1800442E8
0x18004426a  lea     rbx, [rdi+0E0h]
0x180044271  cmp     [rbx], r15
0x180044274  jnz     short loc_18004429C
0x180044276  lea     rdx, [rdi+30h]
0x18004427a  lea     rcx, [rbp+57h+var_98]
0x18004427e  call    ??$make_shared@VLiftedXamlAcrylicBackground@@AEAUDispatcherQueue@System@Windows@winrt@@@std@@YA?AV?$shared_ptr@VLiftedXamlAcrylicBackground@@@0@AEAUDispatcherQueue@System@Windows@winrt@@@Z; std::make_shared<LiftedXamlAcrylicBackground,winrt::Windows::System::DispatcherQueue &>(winrt::Windows::System::DispatcherQueue &)
0x180044283  mov     rdx, rax
0x180044286  mov     rcx, rbx
0x180044289  call    ??4?$shared_ptr@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z
0x18004428e  mov     rcx, [rbp+57h+var_90]; this
0x180044292  test    rcx, rcx
0x180044295  jz      short loc_18004429C
0x180044297  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004429c  mov     rbx, [rbx]
0x18004429f  mov     [rbp+57h+var_68], r15
0x1800442a3  mov     rax, [rsi]
0x1800442a6  lea     r8, [rbp+57h+var_68]
0x1800442aa  lea     rdx, ??$guid_v@UIUIElement@Xaml@UI@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::UI::Xaml::IUIElement>
0x1800442b1  mov     rcx, rsi
0x1800442b4  mov     rax, [rax]
0x1800442b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800442bc  mov     rax, [rbp+57h+var_68]
0x1800442c0  mov     [rbp+57h+var_60], rax
0x1800442c4  lea     rdx, [rbp+57h+var_60]; struct winrt::Microsoft::UI::Xaml::UIElement *
0x1800442c8  mov     rcx, rbx; this
0x1800442cb  call    ?AttachToElement@LiftedXamlAcrylicBackground@@QEAAXAEBUUIElement@Xaml@UI@Microsoft@winrt@@@Z; LiftedXamlAcrylicBackground::AttachToElement(winrt::Microsoft::UI::Xaml::UIElement const &)
0x1800442d0  nop
  ... truncated ...
```
