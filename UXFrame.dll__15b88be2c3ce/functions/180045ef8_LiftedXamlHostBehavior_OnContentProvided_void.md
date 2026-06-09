# LiftedXamlHostBehavior::OnContentProvided(void)

- ea: `0x180045ef8`
- end: `0x1800462d4`
- name: `?OnContentProvided@LiftedXamlHostBehavior@@AEAAXXZ`
- size: `988`
- prototype: `void __fastcall(LiftedXamlHostBehavior *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800406a0`

## callees

- `0x180002b20`
- `0x180002b88`
- `0x1800041c4`
- `0x180004240`
- `0x1800043a0`
- `0x1800049ac`
- `0x1800076a4`
- `0x180007c58`
- `0x18001049c`
- `0x1800371d8`
- `0x180039ffc`
- `0x18003cf98`
- `0x18003e2b8`
- `0x18003e6cc`
- `0x18003e70c`
- `0x18003e87c`
- `0x180040620`
- `0x180045804`
- `0x180045ef8`
- `0x180049314`
- `0x18005a010`

## import_xrefs

- `USER32!SetFocus` at `0x180046269`
- `USER32!SetFocus` at `0x180046269`
- `USER32!GetActiveWindow` at `0x18004625a`
- `USER32!GetActiveWindow` at `0x18004625a`

## string_xrefs

- `0x1800462c2`: `pcshell\shell\uxframe\dll\LiftedXamlHostBehavior.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall LiftedXamlHostBehavior::OnContentProvided(LiftedXamlHostBehavior *this)
{
  char *v2; // r14
  const char *v3; // r9
  _QWORD *v4; // rax
  _DWORD *v5; // rax
  unsigned int v6; // eax
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  _QWORD *v10; // rax
  _DWORD *v11; // rax
  unsigned int v12; // eax
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rax
  _DWORD *v16; // rax
  __int64 *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 ElementVisual; // rax
  __int64 v21; // rax
  HWND v22; // rbx
  __int64 v23; // rax
  __int64 v24; // [rsp+20h] [rbp-49h] BYREF
  __int64 v25; // [rsp+28h] [rbp-41h]
  _DWORD *v26; // [rsp+30h] [rbp-39h] BYREF
  int v27; // [rsp+38h] [rbp-31h] BYREF
  _DWORD *v28; // [rsp+40h] [rbp-29h] BYREF
  _DWORD *v29; // [rsp+48h] [rbp-21h] BYREF
  __int64 v30; // [rsp+50h] [rbp-19h]
  __int64 v31; // [rsp+58h] [rbp-11h] BYREF
  __int64 v32; // [rsp+60h] [rbp-9h]
  int v33; // [rsp+68h] [rbp-1h] BYREF
  __int128 v34; // [rsp+70h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v2 = (char *)this + 72;
  if ( !*(_QWORD *)winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::Content(
                     (char *)this + 72,
                     &v24) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x190,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\LiftedXamlHostBehavior.h",
      v3);
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v24);
  v4 = (_QWORD *)winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::Content(
                   v2,
                   &v29);
  winrt::impl::as<winrt::Microsoft::UI::Xaml::FrameworkElement,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(
    &v26,
    *v4);
  v5 = operator new(0x18u);
  v5[2] = 1;
  *((_QWORD *)v5 + 2) = this;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v5 = &winrt::impl::delegate<winrt::Microsoft::UI::Xaml::SizeChangedEventHandler,_lambda_5ee6b1c6ade97d2c875d91efe52c50a9_>::`vftable';
  v28 = v5;
  v24 = 0;
  v33 = 0;
  v34 = 0;
  v6 = (*(__int64 (__fastcall **)(_DWORD *, _DWORD *, __int64 *))(*(_QWORD *)v26 + 536LL))(v26, v5, &v24);
  winrt::check_hresult(&v27, v6, &v33);
  v7 = v24;
  winrt::weak_ref<winrt::Microsoft::UI::Xaml::IFrameworkElement>::weak_ref<winrt::Microsoft::UI::Xaml::IFrameworkElement>(
    &v31,
    &v26);
  v32 = v7;
  v8 = v31;
  v31 = 0;
  v24 = v8;
  v25 = v7;
  std::swap<winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement>,0>(&v24, (char *)this + 88);
  v9 = v25;
  v25 = *((_QWORD *)this + 12);
  *((_QWORD *)this + 12) = v9;
  __1__event_revoker_UIFrameworkElement_Xaml_UI_Microsoft_winrt___MP8type___abi_UIFrameworkElement_Xaml_UI_Microsoft_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BCCA_AA_impl_winrt__QEAA_XZ(&v24);
  __1__event_revoker_UIFrameworkElement_Xaml_UI_Microsoft_winrt___MP8type___abi_UIFrameworkElement_Xaml_UI_Microsoft_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BCCA_AA_impl_winrt__QEAA_XZ(&v31);
  winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v28);
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v26);
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v29);
  v10 = (_QWORD *)winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::Content(
                    v2,
                    &v28);
  winrt::impl::as<winrt::Microsoft::UI::Xaml::FrameworkElement,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(
    &v26,
    *v10);
  v11 = operator new(0x18u);
  v11[2] = 1;
  *((_QWORD *)v11 + 2) = this;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v11 = &winrt::impl::delegate<winrt::Microsoft::UI::Xaml::RoutedEventHandler,_lambda_e9b4dd055e021ee68947adf49169062e_>::`vftable';
  v29 = v11;
  v24 = 0;
  v33 = 0;
  v34 = 0;
  v12 = (*(__int64 (__fastcall **)(_DWORD *, _DWORD *, __int64 *))(*(_QWORD *)v26 + 488LL))(v26, v11, &v24);
  winrt::check_hresult(&v27, v12, &v33);
  v13 = v24;
  winrt::weak_ref<winrt::Microsoft::UI::Xaml::IFrameworkElement>::weak_ref<winrt::Microsoft::UI::Xaml::IFrameworkElement>(
    &v31,
    &v26);
  v32 = v13;
  v14 = v31;
  v31 = 0;
  v24 = v14;
  v25 = v13;
  std::swap<winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement>,0>(&v24, (char *)this + 104);
  v15 = v25;
  v25 = *((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = v15;
  __1__event_revoker_UIFrameworkElement_Xaml_UI_Microsoft_winrt___MP8type___abi_UIFrameworkElement_Xaml_UI_Microsoft_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BBPA_AA_impl_winrt__QEAA_XZ(&v24);
  __1__event_revoker_UIFrameworkElement_Xaml_UI_Microsoft_winrt___MP8type___abi_UIFrameworkElement_Xaml_UI_Microsoft_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BBPA_AA_impl_winrt__QEAA_XZ(&v31);
  winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v29);
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v26);
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v28);
  v16 = operator new(0x18u);
  v29 = v16;
  v16[2] = 1;
  *((_QWORD *)v16 + 2) = this;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v16 = &winrt::impl::delegate<winrt::Windows::Foundation::EventHandler<winrt::Microsoft::UI::Xaml::Media::RenderedEventArgs>,_lambda_22b692447b334b456ecfdac45b0a1d9e_>::`vftable';
  v26 = v16;
  v17 = (__int64 *)winrt::Microsoft::UI::Xaml::Media::CompositionTarget::Rendered((winrt::Windows::Foundation::IUnknown *)&v31);
  v18 = *v17;
  *v17 = 0;
  v30 = v17[1];
  v29 = 0;
  v24 = v18;
  winrt::Windows::Foundation::IUnknown::operator=(&v29, (char *)this + 144);
  winrt::Windows::Foundation::IUnknown::operator=((char *)this + 144, &v24);
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v24);
  v19 = v30;
  v30 = *((_QWORD *)this + 19);
  *((_QWORD *)this + 19) = v19;
  __1__factory_event_revoker_UICompositionTargetStatics_Media_Xaml_UI_Microsoft_winrt___MP8type___abi_UICompositionTargetStatics_Media_Xaml_UI_Microsoft_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BEI_AA_impl_winrt__QEAA_XZ((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v29);
  __1__factory_event_revoker_UICompositionTargetStatics_Media_Xaml_UI_Microsoft_winrt___MP8type___abi_UICompositionTargetStatics_Media_Xaml_UI_Microsoft_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BEI_AA_impl_winrt__QEAA_XZ((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v31);
  if ( v26 )
    winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v26);
  winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::Content(
    v2,
    &v24);
  ElementVisual = winrt::Microsoft::UI::Xaml::Hosting::ElementCompositionPreview::GetElementVisual((const struct winrt::Microsoft::UI::Xaml::UIElement *)&v28);
  v21 = winrt::impl::consume_Microsoft_UI_Composition_ICompositionObject<winrt::Microsoft::UI::Composition::Visual>::Compositor(
          ElementVisual,
          &v29);
  winrt::Windows::Foundation::IUnknown::operator=((char *)this + 200, v21);
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v29);
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v28);
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v24);
  *((_DWORD *)this + 49) = 5;
  v22 = (HWND)*((_QWORD *)this + 7);
  if ( GetActiveWindow() == v22 )
  {
    SetFocus(*((HWND *)this + 8));
    v27 = 1;
    v23 = winrt::Microsoft::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest::XamlSourceFocusNavigationRequest(
            (winrt::Microsoft::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest *)&v28,
            (const enum winrt::Microsoft::UI::Xaml::Hosting::XamlSourceFocusNavigationReason *)&v27);
    winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::NavigateFocus(
      v2,
      &v29,
      v23);
    winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v29);
    winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v28);
  }
}

```

## disassembly

```asm
0x180045ef8  push    rbp
0x180045efa  push    rbx
0x180045efb  push    rsi
0x180045efc  push    rdi
0x180045efd  push    r14
0x180045eff  push    r15
0x180045f01  lea     rbp, [rsp-2Fh]
0x180045f06  sub     rsp, 98h
0x180045f0d  mov     rax, cs:__security_cookie
0x180045f14  xor     rax, rsp
0x180045f17  mov     [rbp+57h+var_40], rax
0x180045f1b  mov     rsi, rcx
0x180045f1e  lea     r14, [rcx+48h]
0x180045f22  lea     rdx, [rbp+57h+var_A0]
0x180045f26  mov     rcx, r14
0x180045f29  call    ?Content@?$consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource@UIDesktopWindowXamlSource@Hosting@Xaml@UI@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::Content(void)
0x180045f2e  cmp     qword ptr [rax], 0
0x180045f32  setz    al
0x180045f35  mov     rcx, [rbp+5Fh]; this
0x180045f39  test    al, al
0x180045f3b  jnz     loc_1800462C2
0x180045f41  lea     rcx, [rbp+57h+var_A0]; this
0x180045f45  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180045f4a  lea     rdx, [rbp+57h+var_78]
0x180045f4e  mov     rcx, r14
0x180045f51  call    ?Content@?$consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource@UIDesktopWindowXamlSource@Hosting@Xaml@UI@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::Content(void)
0x180045f56  nop
0x180045f57  mov     rdx, [rax]
0x180045f5a  lea     rcx, [rbp+57h+var_90]
0x180045f5e  call    ??$as@UFrameworkElement@Xaml@UI@Microsoft@winrt@@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@5@$0A@@impl@winrt@@YA?AUFrameworkElement@Xaml@UI@Microsoft@1@PEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@01@@Z; winrt::impl::as<winrt::Microsoft::UI::Xaml::FrameworkElement,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x180045f63  nop
0x180045f64  mov     r15d, 18h
0x180045f6a  mov     ecx, r15d; Size
0x180045f6d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045f72  mov     rdx, rax
0x180045f75  mov     [rbp+57h+var_80], rax
0x180045f79  mov     dword ptr [rax+8], 1
0x180045f80  mov     [rax+10h], rsi
0x180045f84  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180045f8b  lea     rax, ??_7?$delegate@USizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@V_lambda_5ee6b1c6ade97d2c875d91efe52c50a9_@@@impl@winrt@@6B@; const winrt::impl::delegate<winrt::Microsoft::UI::Xaml::SizeChangedEventHandler,_lambda_5ee6b1c6ade97d2c875d91efe52c50a9_>::`vftable'
0x180045f92  mov     [rdx], rax
0x180045f95  mov     [rbp+57h+var_80], rdx
0x180045f99  mov     [rbp+57h+var_A0], 0
0x180045fa1  mov     rcx, [rbp+57h+var_90]
0x180045fa5  mov     [rbp+57h+var_58], 0
0x180045fac  xorps   xmm0, xmm0
0x180045faf  movdqu  [rbp+57h+var_50], xmm0
0x180045fb4  mov     rax, [rcx]
0x180045fb7  lea     r8, [rbp+57h+var_A0]
0x180045fbb  mov     rax, [rax+218h]
0x180045fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045fc7  lea     r8, [rbp+57h+var_58]
0x180045fcb  mov     edx, eax
0x180045fcd  lea     rcx, [rbp+57h+var_88]
0x180045fd1  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180045fd6  mov     rbx, [rbp+57h+var_A0]
0x180045fda  lea     rdx, [rbp+57h+var_90]
0x180045fde  lea     rcx, [rbp+57h+var_68]
0x180045fe2  call    ??$?0AEBUIFrameworkElement@Xaml@UI@Microsoft@winrt@@X@?$weak_ref@UIFrameworkElement@Xaml@UI@Microsoft@winrt@@@winrt@@QEAA@AEBUIFrameworkElement@Xaml@UI@Microsoft@1@@Z; winrt::weak_ref<winrt::Microsoft::UI::Xaml::IFrameworkElement>::weak_ref<winrt::Microsoft::UI::Xaml::IFrameworkElement>(winrt::Microsoft::UI::Xaml::IFrameworkElement const &)
0x180045fe7  mov     [rbp+57h+var_60], rbx
0x180045feb  mov     rax, [rbp+57h+var_68]
0x180045fef  mov     [rbp+57h+var_68], 0
0x180045ff7  mov     [rbp+57h+var_A0], rax
0x180045ffb  mov     [rbp+57h+var_98], rbx
0x180045fff  lea     rdx, [rsi+58h]
0x180046003  lea     rcx, [rbp+57h+var_A0]
0x180046007  call    ??$swap@U?$weak_ref@UIFrameworkElement@Xaml@UI@Windows@winrt@@@winrt@@$0A@@std@@YAXAEAU?$weak_ref@UIFrameworkElement@Xaml@UI@Windows@winrt@@@winrt@@0@Z; std::swap<winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement>,0>(winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement> &,winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement> &)
0x18004600c  mov     rax, [rbp+57h+var_98]
0x180046010  mov     rcx, [rsi+60h]
0x180046014  mov     [rbp+57h+var_98], rcx
0x180046018  mov     [rsi+60h], rax
0x18004601c  lea     rcx, [rbp+57h+var_A0]
0x180046020  call    ??1?$event_revoker@UIFrameworkElement@Xaml@UI@Microsoft@winrt@@$MP8type@?$abi@UIFrameworkElement@Xaml@UI@Microsoft@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BCCA@AA@impl@winrt@@QEAA@XZ
0x180046025  lea     rcx, [rbp+57h+var_68]
0x180046029  call    ??1?$event_revoker@UIFrameworkElement@Xaml@UI@Microsoft@winrt@@$MP8type@?$abi@UIFrameworkElement@Xaml@UI@Microsoft@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BCCA@AA@impl@winrt@@QEAA@XZ
0x18004602e  nop
0x18004602f  lea     rcx, [rbp+57h+var_80]
0x180046033  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x180046038  nop
0x180046039  lea     rcx, [rbp+57h+var_90]; this
0x18004603d  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180046042  nop
0x180046043  lea     rcx, [rbp+57h+var_78]; this
0x180046047  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18004604c  lea     rdx, [rbp+57h+var_80]
0x180046050  mov     rcx, r14
0x180046053  call    ?Content@?$consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource@UIDesktopWindowXamlSource@Hosting@Xaml@UI@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::Content(void)
0x180046058  nop
0x180046059  mov     rdx, [rax]
0x18004605c  lea     rcx, [rbp+57h+var_90]
0x180046060  call    ??$as@UFrameworkElement@Xaml@UI@Microsoft@winrt@@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@5@$0A@@impl@winrt@@YA?AUFrameworkElement@Xaml@UI@Microsoft@1@PEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@01@@Z; winrt::impl::as<winrt::Microsoft::UI::Xaml::FrameworkElement,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x180046065  nop
0x180046066  mov     ecx, r15d; Size
0x180046069  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004606e  mov     rdx, rax
0x180046071  mov     [rbp+57h+var_78], rax
0x180046075  mov     dword ptr [rax+8], 1
0x18004607c  mov     [rax+10h], rsi
0x180046080  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180046087  lea     rax, ??_7?$delegate@URoutedEventHandler@Xaml@UI@Microsoft@winrt@@V_lambda_e9b4dd055e021ee68947adf49169062e_@@@impl@winrt@@6B@; const winrt::impl::delegate<winrt::Microsoft::UI::Xaml::RoutedEventHandler,_lambda_e9b4dd055e021ee68947adf49169062e_>::`vftable'
0x18004608e  mov     [rdx], rax
0x180046091  mov     [rbp+57h+var_78], rdx
0x180046095  mov     [rbp+57h+var_A0], 0
0x18004609d  mov     rcx, [rbp+57h+var_90]
0x1800460a1  mov     [rbp+57h+var_58], 0
0x1800460a8  xorps   xmm0, xmm0
0x1800460ab  movdqu  [rbp+57h+var_50], xmm0
0x1800460b0  mov     rax, [rcx]
0x1800460b3  lea     r8, [rbp+57h+var_A0]
0x1800460b7  mov     rax, [rax+1E8h]
0x1800460be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800460c3  lea     r8, [rbp+57h+var_58]
0x1800460c7  mov     edx, eax
0x1800460c9  lea     rcx, [rbp+57h+var_88]
0x1800460cd  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800460d2  mov     rbx, [rbp+57h+var_A0]
0x1800460d6  lea     rdx, [rbp+57h+var_90]
0x1800460da  lea     rcx, [rbp+57h+var_68]
0x1800460de  call    ??$?0AEBUIFrameworkElement@Xaml@UI@Microsoft@winrt@@X@?$weak_ref@UIFrameworkElement@Xaml@UI@Microsoft@winrt@@@winrt@@QEAA@AEBUIFrameworkElement@Xaml@UI@Microsoft@1@@Z; winrt::weak_ref<winrt::Microsoft::UI::Xaml::IFrameworkElement>::weak_ref<winrt::Microsoft::UI::Xaml::IFrameworkElement>(winrt::Microsoft::UI::Xaml::IFrameworkElement const &)
0x1800460e3  mov     [rbp+57h+var_60], rbx
0x1800460e7  mov     rax, [rbp+57h+var_68]
0x1800460eb  mov     [rbp+57h+var_68], 0
0x1800460f3  mov     [rbp+57h+var_A0], rax
0x1800460f7  mov     [rbp+57h+var_98], rbx
0x1800460fb  lea     rdx, [rsi+68h]
0x1800460ff  lea     rcx, [rbp+57h+var_A0]
0x180046103  call    ??$swap@U?$weak_ref@UIFrameworkElement@Xaml@UI@Windows@winrt@@@winrt@@$0A@@std@@YAXAEAU?$weak_ref@UIFrameworkElement@Xaml@UI@Windows@winrt@@@winrt@@0@Z; std::swap<winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement>,0>(winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement> &,winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement> &)
0x180046108  mov     rax, [rbp+57h+var_98]
0x18004610c  mov     rcx, [rsi+70h]
0x180046110  mov     [rbp+57h+var_98], rcx
0x180046114  mov     [rsi+70h], rax
0x180046118  lea     rcx, [rbp+57h+var_A0]
0x18004611c  call    ??1?$event_revoker@UIFrameworkElement@Xaml@UI@Microsoft@winrt@@$MP8type@?$abi@UIFrameworkElement@Xaml@UI@Microsoft@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BBPA@AA@impl@winrt@@QEAA@XZ
0x180046121  lea     rcx, [rbp+57h+var_68]
0x180046125  call    ??1?$event_revoker@UIFrameworkElement@Xaml@UI@Microsoft@winrt@@$MP8type@?$abi@UIFrameworkElement@Xaml@UI@Microsoft@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BBPA@AA@impl@winrt@@QEAA@XZ
0x18004612a  nop
0x18004612b  lea     rcx, [rbp+57h+var_78]
0x18004612f  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x180046134  nop
0x180046135  lea     rcx, [rbp+57h+var_90]; this
0x180046139  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18004613e  nop
0x18004613f  lea     rcx, [rbp+57h+var_80]; this
0x180046143  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180046148  mov     ecx, r15d; Size
0x18004614b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180046150  mov     [rbp+57h+var_78], rax
0x180046154  mov     dword ptr [rax+8], 1
0x18004615b  mov     [rax+10h], rsi
0x18004615f  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180046166  lea     rcx, ??_7?$delegate@U?$EventHandler@URenderedEventArgs@Media@Xaml@UI@Microsoft@winrt@@@Foundation@Windows@winrt@@V_lambda_22b692447b334b456ecfdac45b0a1d9e_@@@impl@winrt@@6B@; const winrt::impl::delegate<winrt::Windows::Foundation::EventHandler<winrt::Microsoft::UI::Xaml::Media::RenderedEventArgs>,_lambda_22b692447b334b456ecfdac45b0a1d9e_>::`vftable'
0x18004616d  mov     [rax], rcx
0x180046170  mov     [rbp+57h+var_90], rax
0x180046174  lea     r8, [rbp+57h+var_90]
0x180046178  lea     rcx, [rbp+57h+var_68]; this
0x18004617c  call    ?Rendered@CompositionTarget@Media@Xaml@UI@Microsoft@winrt@@SA@Uauto_revoke_t@6@AEBU?$EventHandler@URenderedEventArgs@Media@Xaml@UI@Microsoft@winrt@@@Foundation@Windows@6@@Z; winrt::Microsoft::UI::Xaml::Media::CompositionTarget::Rendered(winrt::auto_revoke_t,winrt::Windows::Foundation::EventHandler<winrt::Microsoft::UI::Xaml::Media::RenderedEventArgs> const &)
0x180046181  lea     rbx, [rsi+90h]
0x180046188  mov     rcx, [rax]
0x18004618b  mov     qword ptr [rax], 0
0x180046192  mov     rax, [rax+8]
0x180046196  mov     [rbp+57h+var_70], rax
0x18004619a  mov     [rbp+57h+var_78], 0
0x1800461a2  mov     [rbp+57h+var_A0], rcx
0x1800461a6  mov     rdx, rbx
0x1800461a9  lea     rcx, [rbp+57h+var_78]
0x1800461ad  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x1800461b2  lea     rdx, [rbp+57h+var_A0]
0x1800461b6  mov     rcx, rbx
0x1800461b9  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x1800461be  lea     rcx, [rbp+57h+var_A0]; this
0x1800461c2  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x1800461c7  mov     rax, [rbp+57h+var_70]
0x1800461cb  mov     rcx, [rbx+8]
0x1800461cf  mov     [rbp+57h+var_70], rcx
0x1800461d3  mov     [rbx+8], rax
0x1800461d7  lea     rcx, [rbp+57h+var_78]; this
0x1800461db  call    ??1?$factory_event_revoker@UICompositionTargetStatics@Media@Xaml@UI@Microsoft@winrt@@$MP8type@?$abi@UICompositionTargetStatics@Media@Xaml@UI@Microsoft@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BEI@AA@impl@winrt@@QEAA@XZ
0x1800461e0  lea     rcx, [rbp+57h+var_68]; this
0x1800461e4  call    ??1?$factory_event_revoker@UICompositionTargetStatics@Media@Xaml@UI@Microsoft@winrt@@$MP8type@?$abi@UICompositionTargetStatics@Media@Xaml@UI@Microsoft@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BEI@AA@impl@winrt@@QEAA@XZ
0x1800461e9  nop
0x1800461ea  cmp     [rbp+57h+var_90], 0
0x1800461ef  jz      short loc_1800461FA
0x1800461f1  lea     rcx, [rbp+57h+var_90]
0x1800461f5  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x1800461fa  lea     rdx, [rbp+57h+var_A0]
0x1800461fe  mov     rcx, r14
0x180046201  call    ?Content@?$consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource@UIDesktopWindowXamlSource@Hosting@Xaml@UI@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::Content(void)
0x180046206  nop
0x180046207  mov     rdx, rax
0x18004620a  lea     rcx, [rbp+57h+var_80]; struct winrt::Microsoft::UI::Xaml::UIElement *
0x18004620e  call    ?GetElementVisual@ElementCompositionPreview@Hosting@Xaml@UI@Microsoft@winrt@@SA@AEBUUIElement@3456@@Z; winrt::Microsoft::UI::Xaml::Hosting::ElementCompositionPreview::GetElementVisual(winrt::Microsoft::UI::Xaml::UIElement const &)
0x180046213  nop
0x180046214  lea     rdx, [rbp+57h+var_78]
0x180046218  mov     rcx, rax
0x18004621b  call    ?Compositor@?$consume_Microsoft_UI_Composition_ICompositionObject@UVisual@Composition@UI@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_UI_Composition_ICompositionObject<winrt::Microsoft::UI::Composition::Visual>::Compositor(void)
0x180046220  lea     rcx, [rsi+0C8h]
0x180046227  mov     rdx, rax
0x18004622a  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18004622f  lea     rcx, [rbp+57h+var_78]; this
0x180046233  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180046238  nop
0x180046239  lea     rcx, [rbp+57h+var_80]; this
0x18004623d  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180046242  nop
0x180046243  lea     rcx, [rbp+57h+var_A0]; this
0x180046247  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18004624c  mov     dword ptr [rsi+0C4h], 5
0x180046256  mov     rbx, [rsi+38h]
0x18004625a  call    cs:__imp_GetActiveWindow
0x180046260  cmp     rax, rbx
0x180046263  jnz     short loc_1800462A6
0x180046265  mov     rcx, [rsi+40h]; hWnd
0x180046269  call    cs:__imp_SetFocus
0x18004626f  mov     [rbp+57h+var_88], 1
0x180046276  lea     rdx, [rbp+57h+var_88]; enum winrt::Microsoft::UI::Xaml::Hosting::XamlSourceFocusNavigationReason *
0x18004627a  lea     rcx, [rbp+57h+var_80]; this
0x18004627e  call    ??0XamlSourceFocusNavigationRequest@Hosting@Xaml@UI@Microsoft@winrt@@QEAA@AEBW4XamlSourceFocusNavigationReason@12345@@Z; winrt::Microsoft::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest::XamlSourceFocusNavigationRequest(winrt::Microsoft::UI::Xaml::Hosting::XamlSourceFocusNavigationReason const &)
0x180046283  nop
0x180046284  mov     r8, rax
0x180046287  lea     rdx, [rbp+57h+var_78]
0x18004628b  mov     rcx, r14
0x18004628e  call    ?NavigateFocus@?$consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource@UIDesktopWindowXamlSource@Hosting@Xaml@UI@Microsoft@winrt@@@impl@winrt@@QEBA@AEBUXamlSourceFocusNavigationRequest@Hosting@Xaml@UI@Microsoft@3@@Z; winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::NavigateFocus(winrt::Microsoft::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest const &)
0x180046293  lea     rcx, [rbp+57h+var_78]; this
0x180046297  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18004629c  nop
0x18004629d  lea     rcx, [rbp+57h+var_80]; this
0x1800462a1  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x1800462a6  mov     rcx, [rbp+57h+var_40]
0x1800462aa  xor     rcx, rsp; StackCookie
0x1800462ad  call    __security_check_cookie
0x1800462b2  add     rsp, 98h
0x1800462b9  pop     r15
0x1800462bb  pop     r14
0x1800462bd  pop     rdi
0x1800462be  pop     rsi
0x1800462bf  pop     rbx
0x1800462c0  pop     rbp
0x1800462c1  retn
0x1800462c2  lea     r8, aPcshellShellUx_8; "pcshell\\shell\\uxframe\\dll\\LiftedXam"...
0x1800462c9  mov     edx, 190h; void *
0x1800462ce  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
