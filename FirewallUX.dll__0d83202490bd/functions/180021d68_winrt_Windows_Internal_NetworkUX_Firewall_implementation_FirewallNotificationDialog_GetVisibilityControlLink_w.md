# winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::_GetVisibilityControlLink(winrt::hstring const &)

- ea: `0x180021d68`
- end: `0x18002269f`
- name: `?_GetVisibilityControlLink@FirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@AEAA?AUButton@Controls@Xaml@UI@67@AEBUhstring@7@@Z`
- size: `2359`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, double *)`
- caller_count: `1`
- callee_count: `25`
- tags: `broker_com_uri`

## callers

- `0x18001e0b0`

## callees

- `0x1800021e4`
- `0x180002d55`
- `0x180002d91`
- `0x18000b058`
- `0x18000b24c`
- `0x18000b5d0`
- `0x18000bbe8`
- `0x18000ee78`
- `0x18000f3bc`
- `0x1800101bc`
- `0x180010464`
- `0x180012a74`
- `0x180012b2c`
- `0x180012d04`
- `0x180013128`
- `0x180013188`
- `0x180013818`
- `0x180013860`
- `0x1800138a8`
- `0x180014980`
- `0x18001bb50`
- `0x18001dda8`
- `0x180021d68`
- `0x180023264`
- `0x18002d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002260a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002260a`

## string_xrefs

- `0x180021e08`: `VisibilityLink`

## pseudocode

```c
_QWORD *__fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::_GetVisibilityControlLink(
        __int64 a1,
        _QWORD *a2,
        double *a3)
{
  _QWORD *weak; // rax
  __int64 *v7; // rcx
  void (__fastcall ***v8)(_QWORD, void *, _QWORD *); // rsi
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 (__fastcall ***v11)(_QWORD, void *, _QWORD *); // rcx
  int v12; // eax
  void (__fastcall ***v13)(_QWORD, void *, _QWORD *); // rbx
  int v14; // eax
  __int64 (__fastcall ***v15)(_QWORD, void *, _QWORD *); // rcx
  int v16; // eax
  void (__fastcall ***v17)(_QWORD, void *, _QWORD *); // rbx
  int v18; // eax
  __int64 (__fastcall ***v19)(_QWORD, void *, _QWORD *); // rcx
  int v20; // eax
  void (__fastcall ***v21)(_QWORD, void *, _QWORD *); // rbx
  int v22; // eax
  _DWORD *v23; // rbx
  void (__fastcall ***v24)(_QWORD, void *, _QWORD *); // rcx
  __int64 (__fastcall ***v25)(_QWORD, void *, _QWORD *); // rcx
  int v26; // eax
  void (__fastcall ***v27)(_QWORD, void *, _QWORD *); // rsi
  int v28; // eax
  unsigned int v29; // edx
  volatile signed __int32 *v30; // rbx
  __int64 v31; // rax
  __int64 v32; // rax
  unsigned int v33; // edx
  char HasKey; // si
  __int64 v35; // rax
  __int64 v36; // rax
  int v37; // eax
  HANDLE ProcessHeap; // rax
  __int64 (__fastcall ***v39)(_QWORD, void *, _QWORD *); // rcx
  int v40; // eax
  void (__fastcall ***v41)(_QWORD, void *, _QWORD *); // rbx
  int v42; // eax
  volatile signed __int32 *v43; // rbx
  __int64 v44; // rax
  __int64 v45; // rax
  char v46; // si
  __int64 v47; // rax
  __int64 v48; // rax
  int v49; // eax
  int v50; // r14d
  HANDLE v51; // rax
  void (__fastcall ***v53)(_QWORD, void *, __int64 **); // [rsp+20h] [rbp-99h] BYREF
  __int64 *v54; // [rsp+28h] [rbp-91h] BYREF
  __int64 v55; // [rsp+30h] [rbp-89h] BYREF
  volatile signed __int32 *v56; // [rsp+38h] [rbp-81h] BYREF
  __int128 v57; // [rsp+40h] [rbp-79h]
  int v58; // [rsp+50h] [rbp-69h]
  __int64 *v59; // [rsp+58h] [rbp-61h] BYREF
  _QWORD v60[2]; // [rsp+60h] [rbp-59h] BYREF
  __m128d si128; // [rsp+70h] [rbp-49h] BYREF
  __m128d v62; // [rsp+80h] [rbp-39h]
  __int64 *v63; // [rsp+90h] [rbp-29h] BYREF
  char v64; // [rsp+98h] [rbp-21h]
  __int128 *v65; // [rsp+A0h] [rbp-19h] BYREF
  __int128 v66; // [rsp+A8h] [rbp-11h] BYREF
  const wchar_t *v67; // [rsp+B8h] [rbp-1h]
  void (__fastcall ***v68)(_QWORD, void *, _QWORD *); // [rsp+C0h] [rbp+7h]
  _QWORD v69[4]; // [rsp+C8h] [rbp+Fh] BYREF
  char v70; // [rsp+E8h] [rbp+2Fh]
  void (__fastcall ***v71)(_QWORD, void *, _QWORD *); // [rsp+130h] [rbp+77h] BYREF
  void (__fastcall ***v72)(_QWORD, void *, _QWORD); // [rsp+138h] [rbp+7Fh] BYREF

  v58 = 0;
  winrt::Windows::UI::Xaml::Controls::TextBlock::TextBlock((winrt::Windows::UI::Xaml::Controls::TextBlock *)&v72);
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::FontSize(&v72);
  LODWORD(v71) = 0;
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::HorizontalAlignment(
    &v72,
    &v71);
  LODWORD(v71) = 0;
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::VerticalAlignment(
    &v72,
    &v71);
  LODWORD(v71) = 2;
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::TextWrapping(
    &v72,
    &v71);
  si128.m128d_f64[0] = *a3;
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::Text(
    &v72,
    &si128);
  *(_QWORD *)&v66 = 0xE00000001LL;
  v67 = L"VisibilityLink";
  v65 = &v66;
  if ( v72 )
  {
    v53 = 0;
    (**v72)(v72, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IDependencyObject>, &v53);
    v71 = (void (__fastcall ***)(_QWORD, void *, _QWORD *))v53;
  }
  else
  {
    v71 = 0;
  }
  winrt::Windows::UI::Xaml::Automation::AutomationProperties::SetAutomationId(
    (const struct winrt::Windows::UI::Xaml::DependencyObject *)&v71,
    (const struct winrt::param::hstring *)&v65);
  if ( v71 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v71);
  weak = (_QWORD *)winrt::implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::IFirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase>::get_weak(
                     a1,
                     &v55);
  v8 = (void (__fastcall ***)(_QWORD, void *, _QWORD *))*weak;
  *weak = 0;
  v68 = v8;
  if ( v55 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v55);
  *a2 = 0;
  v53 = 0;
  v71 = 0;
  v56 = (volatile signed __int32 *)&v53;
  *(_QWORD *)&v57 = &v71;
  v59 = &qword_18003C0F8;
  _InterlockedIncrement64(&qword_18003C0F8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::Button,winrt::Windows::UI::Xaml::Controls::IButtonFactory> )
  {
    `winrt::Windows::UI::Xaml::Controls::HyperlinkButton::HyperlinkButton'::`2'::_lambda_1_::operator()(
      &v56,
      v60,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::Button,winrt::Windows::UI::Xaml::Controls::IButtonFactory>);
    _InterlockedAdd64(&qword_18003C0F8, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_18003C0F8, 0xFFFFFFFFFFFFFFFFuLL);
    ___call_AEAV_lambda_1___1___0Button_Controls_Xaml_UI_Windows_winrt__QEAA_XZ____factory_cache_entry_UButton_Controls_Xaml_UI_Windows_winrt__UIButtonFactory_23456__impl_winrt__QEAA_A_PAEAV_lambda_1___1___0Button_Controls_Xaml_UI_Windows_2_QEAA_XZ__Z(
      v7,
      (__int64)v60,
      (__int64)&v56);
  }
  if ( a2 == v60 )
  {
    v10 = v60[0];
  }
  else
  {
    if ( *a2 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(a2);
    v9 = v60[0];
    v10 = 0;
    v60[0] = 0;
    *a2 = v9;
  }
  if ( v10 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v60);
  if ( v71 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v71);
  if ( v53 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v53);
  v58 = 3;
  v11 = (__int64 (__fastcall ***)(_QWORD, void *, _QWORD *))*a2;
  v71 = 0;
  if ( v11 )
  {
    v12 = (**v11)(v11, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IControl>, &v71);
    v13 = v71;
  }
  else
  {
    v12 = 0;
    v13 = 0;
  }
  LODWORD(v56) = 0;
  v57 = 0;
  if ( v12 < 0 )
    winrt::throw_hresult((unsigned int)v12, &v56);
  LODWORD(v56) = 0;
  v57 = 0;
  si128 = (__m128d)_mm_load_si128((const __m128i *)&_xmm);
  v62 = 0;
  v14 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, void *, _QWORD *), __m128d *))(*v13)[31])(v13, &si128);
  if ( v14 < 0 )
    winrt::throw_hresult((unsigned int)v14, &v56);
  if ( v13 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v71);
  v15 = (__int64 (__fastcall ***)(_QWORD, void *, _QWORD *))*a2;
  v71 = 0;
  if ( v15 )
  {
    v16 = (**v15)(v15, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IFrameworkElement>, &v71);
    v17 = v71;
  }
  else
  {
    v16 = 0;
    v17 = 0;
  }
  LODWORD(v56) = 0;
  v57 = 0;
  if ( v16 < 0 )
    winrt::throw_hresult((unsigned int)v16, &v56);
  LODWORD(v56) = 0;
  v57 = 0;
  si128 = 0;
  v62 = 0;
  v18 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, void *, _QWORD *), __m128d *))(*v17)[32])(v17, &si128);
  if ( v18 < 0 )
    winrt::throw_hresult((unsigned int)v18, &v56);
  if ( v17 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v71);
  v19 = (__int64 (__fastcall ***)(_QWORD, void *, _QWORD *))*a2;
  v71 = 0;
  if ( v19 )
  {
    v20 = (**v19)(v19, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IContentControl>, &v71);
    v21 = v71;
  }
  else
  {
    v20 = 0;
    v21 = 0;
  }
  LODWORD(v56) = 0;
  v57 = 0;
  if ( v20 < 0 )
    winrt::throw_hresult((unsigned int)v20, &v56);
  LODWORD(v56) = 0;
  v57 = 0;
  v22 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, void *, _QWORD *), void (__fastcall ***)(_QWORD, void *, _QWORD)))(*v21)[7])(
          v21,
          v72);
  if ( v22 < 0 )
    winrt::throw_hresult((unsigned int)v22, &v56);
  if ( v21 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v71);
  v68 = 0;
  v71 = v8;
  v59 = (__int64 *)&v71;
  v23 = operator new(0x18u);
  v23[2] = 1;
  v24 = v71;
  v71 = 0;
  *((_QWORD *)v23 + 2) = v24;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v23 = off_18002E900;
  v59 = (__int64 *)v23;
  v58 = 7;
  if ( v71 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v71);
  v54 = 0;
  v25 = (__int64 (__fastcall ***)(_QWORD, void *, _QWORD *))*a2;
  v53 = 0;
  if ( v25 )
  {
    v26 = (**v25)(v25, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::Primitives::IButtonBase>, &v53);
    v27 = (void (__fastcall ***)(_QWORD, void *, _QWORD *))v53;
  }
  else
  {
    v26 = 0;
    v27 = 0;
  }
  LODWORD(v56) = 0;
  v57 = 0;
  if ( v26 < 0 )
    winrt::throw_hresult((unsigned int)v26, &v56);
  LODWORD(v56) = 0;
  v57 = 0;
  v28 = ((__int64 (__fastcall *)(_QWORD, _DWORD *, __int64 **))(*v27)[14])(v27, v23, &v54);
  if ( v28 < 0 )
    winrt::throw_hresult((unsigned int)v28, &v56);
  if ( v27 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v53);
  winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v59);
  v30 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x14, v29);
  memcpy_s((void *const)(v30 + 7), 0x28u, L"TextBlockButtonStyle", 0x28u);
  v59 = (__int64 *)v30;
  *(_QWORD *)&si128.m128d_f64[0] = v30;
  winrt::box_value((winrt *)&v71, (const struct winrt::param::hstring *)&si128);
  v31 = winrt::Windows::UI::Xaml::Application::Current();
  v32 = winrt::impl::consume_Windows_UI_Xaml_Controls_IGrid<winrt::Windows::UI::Xaml::Controls::IGrid>::RowDefinitions(
          v31,
          &v55);
  HasKey = winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::UI::Xaml::ResourceDictionary,winrt::Windows::Foundation::IInspectable,winrt::Windows::Foundation::IInspectable>::HasKey(
             v32,
             &v71);
  if ( v55 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v55);
  if ( v53 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v53);
  if ( !HasKey )
    goto LABEL_64;
  v35 = winrt::Windows::UI::Xaml::Application::Current();
  v36 = winrt::impl::consume_Windows_UI_Xaml_Controls_IGrid<winrt::Windows::UI::Xaml::Controls::IGrid>::RowDefinitions(
          v35,
          &v55);
  winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::UI::Xaml::ResourceDictionary,winrt::Windows::Foundation::IInspectable,winrt::Windows::Foundation::IInspectable>::Lookup(
    v36,
    &v53,
    &v71);
  if ( v55 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v55);
  if ( v54 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v54);
  if ( v53 )
  {
    v54 = 0;
    (**v53)(v53, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IStyle>, &v54);
    v63 = v54;
    v64 = 1;
    v58 = 15;
    if ( v53 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v53);
  }
  else
  {
LABEL_64:
    v64 = 0;
    v58 = 15;
  }
  if ( v71 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v71);
  if ( v30 )
  {
    v37 = _InterlockedDecrement(v30 + 6);
    if ( v37 )
    {
      if ( v37 < 0 )
        goto LABEL_110;
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v30);
    }
  }
  if ( v64 )
  {
    v39 = (__int64 (__fastcall ***)(_QWORD, void *, _QWORD *))*a2;
    v71 = 0;
    if ( v39 )
    {
      v40 = (**v39)(v39, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IFrameworkElement>, &v71);
      v41 = v71;
    }
    else
    {
      v40 = 0;
      v41 = 0;
    }
    LODWORD(v56) = 0;
    v57 = 0;
    if ( v40 < 0 )
      winrt::throw_hresult((unsigned int)v40, &v56);
    LODWORD(v56) = 0;
    v57 = 0;
    v42 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, void *, _QWORD *), __int64 *))(*v41)[39])(v41, v63);
    if ( v42 < 0 )
      winrt::throw_hresult((unsigned int)v42, &v56);
    if ( v41 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v71);
  }
  v43 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x13, v33);
  memcpy_s((void *const)(v43 + 7), 0x26u, L"ControlCornerRadius", 0x26u);
  v56 = v43;
  *(_QWORD *)&si128.m128d_f64[0] = v43;
  winrt::box_value((winrt *)&v71, (const struct winrt::param::hstring *)&si128);
  v44 = winrt::Windows::UI::Xaml::Application::Current();
  v45 = winrt::impl::consume_Windows_UI_Xaml_Controls_IGrid<winrt::Windows::UI::Xaml::Controls::IGrid>::RowDefinitions(
          v44,
          &v54);
  v46 = winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::UI::Xaml::ResourceDictionary,winrt::Windows::Foundation::IInspectable,winrt::Windows::Foundation::IInspectable>::HasKey(
          v45,
          &v71);
  if ( v54 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v54);
  if ( v55 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v55);
  if ( !v46 )
    goto LABEL_95;
  v47 = winrt::Windows::UI::Xaml::Application::Current();
  v48 = winrt::impl::consume_Windows_UI_Xaml_Controls_IGrid<winrt::Windows::UI::Xaml::Controls::IGrid>::RowDefinitions(
          v47,
          &v54);
  winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::UI::Xaml::ResourceDictionary,winrt::Windows::Foundation::IInspectable,winrt::Windows::Foundation::IInspectable>::Lookup(
    v48,
    &v53,
    &v71);
  if ( v54 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v54);
  if ( v55 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v55);
  if ( v53 )
  {
    v54 = 0;
    (**v53)(
      v53,
      &winrt::impl::guid_v<winrt::Windows::Foundation::IReference<winrt::Windows::UI::Xaml::CornerRadius>>,
      &v54);
    v59 = v54;
    if ( v54 )
    {
      si128 = 0;
      v62 = 0;
      LODWORD(v65) = 0;
      v66 = 0;
      v49 = (*(__int64 (__fastcall **)(__int64 *, __m128d *))(*v54 + 48))(v54, &si128);
      if ( v49 < 0 )
        winrt::throw_hresult((unsigned int)v49, &v65);
      v69[0] = *(_QWORD *)&si128.m128d_f64[0];
      v69[1] = *(_OWORD *)&_mm_unpackhi_pd(si128, si128);
      v69[2] = *(_QWORD *)&v62.m128d_f64[0];
      v69[3] = *(_OWORD *)&_mm_unpackhi_pd(v62, v62);
      v70 = 1;
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v59);
    }
    else
    {
      v70 = 0;
    }
    if ( v53 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v53);
  }
  else
  {
LABEL_95:
    v70 = 0;
  }
  if ( v71 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v71);
  if ( v43 )
  {
    v50 = _InterlockedDecrement(v43 + 6);
    if ( !v50 )
    {
      v51 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v51, 0, (LPVOID)v43);
      goto LABEL_101;
    }
    if ( v50 < 0 )
LABEL_110:
      abort();
  }
LABEL_101:
  if ( v70 )
    winrt::impl::consume_Windows_UI_Xaml_Controls_IControl7<winrt::Windows::UI::Xaml::Controls::Button>::CornerRadius(
      a2,
      v69);
  if ( v64 && v63 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v63);
  if ( v72 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v72);
  return a2;
}

```

## disassembly

```asm
0x180021d68  mov     [rsp-8+arg_0], rbx
0x180021d6d  mov     [rsp-8+arg_8], rdx
0x180021d72  push    rbp
0x180021d73  push    rsi
0x180021d74  push    rdi
0x180021d75  push    r14
0x180021d77  push    r15
0x180021d79  lea     rbp, [rsp-37h]
0x180021d7e  sub     rsp, 0F0h
0x180021d85  mov     rbx, r8
0x180021d88  mov     rdi, rdx
0x180021d8b  mov     rsi, rcx
0x180021d8e  xor     r15d, r15d
0x180021d91  mov     [rbp+57h+var_C0], r15d
0x180021d95  lea     rcx, [rbp+57h+arg_18]; this
0x180021d99  call    ??0TextBlock@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ; winrt::Windows::UI::Xaml::Controls::TextBlock::TextBlock(void)
0x180021d9e  nop
0x180021d9f  movsd   xmm1, cs:__real@402c000000000000
0x180021da7  lea     rcx, [rbp+57h+arg_18]
0x180021dab  call    ?FontSize@?$consume_Windows_UI_Xaml_Controls_ITextBlock@UITextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@N@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::FontSize(double)
0x180021db0  mov     dword ptr [rbp+57h+arg_10], r15d
0x180021db4  lea     rdx, [rbp+57h+arg_10]
0x180021db8  lea     rcx, [rbp+57h+arg_18]
0x180021dbc  call    ?HorizontalAlignment@?$consume_Windows_UI_Xaml_IFrameworkElement@UTextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBW40Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::HorizontalAlignment(winrt::Windows::UI::Xaml::HorizontalAlignment const &)
0x180021dc1  mov     dword ptr [rbp+57h+arg_10], r15d
0x180021dc5  lea     rdx, [rbp+57h+arg_10]
0x180021dc9  lea     rcx, [rbp+57h+arg_18]
0x180021dcd  call    ?VerticalAlignment@?$consume_Windows_UI_Xaml_IFrameworkElement@UTextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBW40Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::VerticalAlignment(winrt::Windows::UI::Xaml::VerticalAlignment const &)
0x180021dd2  mov     dword ptr [rbp+57h+arg_10], 2
0x180021dd9  lea     rdx, [rbp+57h+arg_10]
0x180021ddd  lea     rcx, [rbp+57h+arg_18]
0x180021de1  call    ?TextWrapping@?$consume_Windows_UI_Xaml_Controls_ITextBlock@UITextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBW40Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::TextWrapping(winrt::Windows::UI::Xaml::TextWrapping const &)
0x180021de6  mov     rax, [rbx]
0x180021de9  mov     qword ptr [rbp+57h+var_A0], rax
0x180021ded  lea     rdx, [rbp+57h+var_A0]
0x180021df1  lea     rcx, [rbp+57h+arg_18]
0x180021df5  call    ?Text@?$consume_Windows_UI_Xaml_Controls_ITextBlock@UITextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::Text(winrt::param::hstring const &)
0x180021dfa  mov     dword ptr [rbp+57h+var_68], 1
0x180021e01  mov     dword ptr [rbp+57h+var_68+4], 0Eh
0x180021e08  lea     rax, aVisibilitylink; "VisibilityLink"
0x180021e0f  mov     [rbp+57h+var_58], rax
0x180021e13  lea     rax, [rbp+57h+var_68]
0x180021e17  mov     [rbp+57h+var_70], rax
0x180021e1b  mov     rcx, [rbp+57h+arg_18]
0x180021e1f  test    rcx, rcx
0x180021e22  jnz     short loc_180021E2A
0x180021e24  mov     [rbp+57h+arg_10], r15
0x180021e28  jmp     short loc_180021E4F
0x180021e2a  mov     [rsp+110h+var_F0], r15
0x180021e2f  mov     rax, [rcx]
0x180021e32  lea     r8, [rsp+110h+var_F0]
0x180021e37  lea     rdx, ??$guid_v@UIDependencyObject@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::IDependencyObject>
0x180021e3e  mov     rax, [rax]
0x180021e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e46  mov     rax, [rsp+110h+var_F0]
0x180021e4b  mov     [rbp+57h+arg_10], rax
0x180021e4f  lea     rdx, [rbp+57h+var_70]; struct winrt::param::hstring *
0x180021e53  lea     rcx, [rbp+57h+arg_10]; struct winrt::Windows::UI::Xaml::DependencyObject *
0x180021e57  call    ?SetAutomationId@AutomationProperties@Automation@Xaml@UI@Windows@winrt@@SA@AEBUDependencyObject@3456@AEBUhstring@param@6@@Z; winrt::Windows::UI::Xaml::Automation::AutomationProperties::SetAutomationId(winrt::Windows::UI::Xaml::DependencyObject const &,winrt::param::hstring const &)
0x180021e5c  nop
0x180021e5d  cmp     [rbp+57h+arg_10], r15
0x180021e61  jz      short loc_180021E6C
0x180021e63  lea     rcx, [rbp+57h+arg_10]
0x180021e67  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180021e6c  lea     rdx, [rsp+110h+var_E0]
0x180021e71  mov     rcx, rsi
0x180021e74  call    ?get_weak@?$implements@UFirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UIFirewallNotificationDialog@34567@UFirewallDialogBase@234567@@winrt@@QEAA?AU?$weak_ref@UFirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@2@XZ; winrt::implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::IFirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase>::get_weak(void)
0x180021e79  mov     rsi, [rax]
0x180021e7c  mov     [rax], r15
0x180021e7f  mov     [rbp+57h+var_50], rsi
0x180021e83  cmp     [rsp+110h+var_E0], r15
0x180021e88  jz      short loc_180021E94
0x180021e8a  lea     rcx, [rsp+110h+var_E0]
0x180021e8f  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180021e94  mov     [rdi], r15
0x180021e97  mov     [rsp+110h+var_F0], r15
0x180021e9c  mov     [rbp+57h+arg_10], r15
0x180021ea0  lea     rax, [rsp+110h+var_F0]
0x180021ea5  mov     [rsp+110h+var_D8], rax
0x180021eaa  lea     rax, [rbp+57h+arg_10]
0x180021eae  mov     qword ptr [rbp+57h+var_D0], rax
0x180021eb2  lea     rax, qword_18003C0F8
0x180021eb9  mov     [rbp+57h+var_B8], rax
0x180021ebd  lock inc cs:qword_18003C0F8
0x180021ec5  cmp     cs:??$factory_cache_entry_v@UButton@Controls@Xaml@UI@Windows@winrt@@UIButtonFactory@23456@@impl@winrt@@3U?$factory_cache_entry@UButton@Controls@Xaml@UI@Windows@winrt@@UIButtonFactory@23456@@12@A, r15; factory_cache_entry<winrt::Windows::UI::Xaml::Controls::Button,winrt::Windows::UI::Xaml::Controls::IButtonFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Controls::Button,winrt::Windows::UI::Xaml::Controls::IButtonFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::Button,winrt::Windows::UI::Xaml::Controls::IButtonFactory>
0x180021ecc  jz      short loc_180021EF2
0x180021ece  lea     r8, ??$factory_cache_entry_v@UButton@Controls@Xaml@UI@Windows@winrt@@UIButtonFactory@23456@@impl@winrt@@3U?$factory_cache_entry@UButton@Controls@Xaml@UI@Windows@winrt@@UIButtonFactory@23456@@12@A; factory_cache_entry<winrt::Windows::UI::Xaml::Controls::Button,winrt::Windows::UI::Xaml::Controls::IButtonFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Controls::Button,winrt::Windows::UI::Xaml::Controls::IButtonFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::Button,winrt::Windows::UI::Xaml::Controls::IButtonFactory>
0x180021ed5  lea     rdx, [rbp+57h+var_B0]
0x180021ed9  lea     rcx, [rsp+110h+var_D8]
0x180021ede  call    ??R_lambda_1_@?1???0HyperlinkButton@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ@QEBA@AEBUIHyperlinkButtonFactory@23456@@Z; `winrt::Windows::UI::Xaml::Controls::HyperlinkButton::HyperlinkButton(void)'::`2'::_lambda_1_::operator()(winrt::Windows::UI::Xaml::Controls::IHyperlinkButtonFactory const &)
0x180021ee3  nop
0x180021ee4  or      r14, 0FFFFFFFFFFFFFFFFh
0x180021ee8  lock add cs:qword_18003C0F8, r14
0x180021ef0  jmp     short loc_180021F0C
0x180021ef2  or      r14, 0FFFFFFFFFFFFFFFFh
0x180021ef6  lock add cs:qword_18003C0F8, r14
0x180021efe  lea     r8, [rsp+110h+var_D8]
0x180021f03  lea     rdx, [rbp+57h+var_B0]
0x180021f07  call    ??$call@AEAV_lambda_1_@?1???0Button@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ@@?$factory_cache_entry@UButton@Controls@Xaml@UI@Windows@winrt@@UIButtonFactory@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1???0Button@Controls@Xaml@UI@Windows@2@QEAA@XZ@@Z
0x180021f0c  lea     rax, [rbp+57h+var_B0]
0x180021f10  cmp     rdi, rax
0x180021f13  jz      short loc_180021F32
0x180021f15  cmp     [rdi], r15
0x180021f18  jz      short loc_180021F22
0x180021f1a  mov     rcx, rdi
0x180021f1d  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180021f22  mov     rcx, [rbp+57h+var_B0]
0x180021f26  mov     rax, r15
0x180021f29  mov     [rbp+57h+var_B0], rax
0x180021f2d  mov     [rdi], rcx
0x180021f30  jmp     short loc_180021F36
0x180021f32  mov     rax, [rbp+57h+var_B0]
0x180021f36  test    rax, rax
0x180021f39  jz      short loc_180021F45
0x180021f3b  lea     rcx, [rbp+57h+var_B0]
0x180021f3f  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180021f44  nop
0x180021f45  cmp     [rbp+57h+arg_10], r15
0x180021f49  jz      short loc_180021F55
0x180021f4b  lea     rcx, [rbp+57h+arg_10]
0x180021f4f  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180021f54  nop
0x180021f55  cmp     [rsp+110h+var_F0], r15
0x180021f5a  jz      short loc_180021F67
0x180021f5c  lea     rcx, [rsp+110h+var_F0]
0x180021f61  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180021f66  nop
0x180021f67  mov     [rbp+57h+var_C0], 3
0x180021f6e  mov     rcx, [rdi]
0x180021f71  mov     [rbp+57h+arg_10], r15
0x180021f75  test    rcx, rcx
0x180021f78  jnz     short loc_180021F82
0x180021f7a  mov     eax, r15d
0x180021f7d  mov     rbx, r15
0x180021f80  jmp     short loc_180021FA0
0x180021f82  mov     rax, [rcx]
0x180021f85  lea     r8, [rbp+57h+arg_10]
0x180021f89  lea     rdx, ??$guid_v@UIControl@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IControl>
0x180021f90  mov     rax, [rax]
0x180021f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f98  mov     rbx, [rbp+57h+arg_10]
0x180021f9c  mov     [rbp+57h+arg_10], rbx
0x180021fa0  mov     dword ptr [rsp+110h+var_D8], r15d
0x180021fa5  xorps   xmm0, xmm0
0x180021fa8  movdqu  [rbp+57h+var_D0], xmm0
0x180021fad  test    eax, eax
0x180021faf  js      loc_18002261D
0x180021fb5  mov     dword ptr [rsp+110h+var_D8], r15d
0x180021fba  movdqu  [rbp+57h+var_D0], xmm0
0x180021fbf  movdqa  xmm1, cs:__xmm@00000000000000003ff0000000000000
0x180021fc7  movaps  [rbp+57h+var_A0], xmm1
0x180021fcb  movaps  [rbp+57h+var_90], xmm0
0x180021fcf  mov     rax, [rbx]
0x180021fd2  lea     rdx, [rbp+57h+var_A0]
0x180021fd6  mov     rcx, rbx
0x180021fd9  mov     rax, [rax+0F8h]
0x180021fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fe5  test    eax, eax
0x180021fe7  js      loc_18002262A
0x180021fed  test    rbx, rbx
0x180021ff0  jz      short loc_180021FFB
0x180021ff2  lea     rcx, [rbp+57h+arg_10]
0x180021ff6  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180021ffb  mov     rcx, [rdi]
0x180021ffe  mov     [rbp+57h+arg_10], r15
0x180022002  test    rcx, rcx
0x180022005  jnz     short loc_18002200F
0x180022007  mov     eax, r15d
0x18002200a  mov     rbx, r15
0x18002200d  jmp     short loc_18002202D
0x18002200f  mov     rax, [rcx]
0x180022012  lea     r8, [rbp+57h+arg_10]
0x180022016  lea     rdx, ??$guid_v@UIFrameworkElement@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::IFrameworkElement>
0x18002201d  mov     rax, [rax]
0x180022020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022025  mov     rbx, [rbp+57h+arg_10]
0x180022029  mov     [rbp+57h+arg_10], rbx
0x18002202d  mov     dword ptr [rsp+110h+var_D8], r15d
0x180022032  xorps   xmm0, xmm0
0x180022035  movdqu  [rbp+57h+var_D0], xmm0
0x18002203a  test    eax, eax
0x18002203c  js      loc_180022637
0x180022042  mov     dword ptr [rsp+110h+var_D8], r15d
0x180022047  movdqu  [rbp+57h+var_D0], xmm0
0x18002204c  movaps  [rbp+57h+var_A0], xmm0
0x180022050  xorps   xmm1, xmm1
0x180022053  movaps  [rbp+57h+var_90], xmm1
0x180022057  mov     rax, [rbx]
0x18002205a  lea     rdx, [rbp+57h+var_A0]
0x18002205e  mov     rcx, rbx
0x180022061  mov     rax, [rax+100h]
0x180022068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002206d  test    eax, eax
0x18002206f  js      loc_180022644
0x180022075  test    rbx, rbx
0x180022078  jz      short loc_180022083
0x18002207a  lea     rcx, [rbp+57h+arg_10]
0x18002207e  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180022083  mov     rcx, [rdi]
0x180022086  mov     [rbp+57h+arg_10], r15
0x18002208a  test    rcx, rcx
0x18002208d  jnz     short loc_180022097
0x18002208f  mov     eax, r15d
0x180022092  mov     rbx, r15
0x180022095  jmp     short loc_1800220B5
0x180022097  mov     rax, [rcx]
0x18002209a  lea     r8, [rbp+57h+arg_10]
0x18002209e  lea     rdx, ??$guid_v@UIContentControl@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IContentControl>
0x1800220a5  mov     rax, [rax]
0x1800220a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220ad  mov     rbx, [rbp+57h+arg_10]
0x1800220b1  mov     [rbp+57h+arg_10], rbx
0x1800220b5  mov     dword ptr [rsp+110h+var_D8], r15d
0x1800220ba  xorps   xmm0, xmm0
0x1800220bd  movdqu  [rbp+57h+var_D0], xmm0
0x1800220c2  test    eax, eax
0x1800220c4  js      loc_180022651
0x1800220ca  mov     dword ptr [rsp+110h+var_D8], r15d
0x1800220cf  movdqu  [rbp+57h+var_D0], xmm0
0x1800220d4  mov     rax, [rbx]
0x1800220d7  mov     rdx, [rbp+57h+arg_18]
0x1800220db  mov     rcx, rbx
0x1800220de  mov     rax, [rax+38h]
0x1800220e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220e7  test    eax, eax
0x1800220e9  js      loc_18002265E
0x1800220ef  test    rbx, rbx
0x1800220f2  jz      short loc_1800220FD
0x1800220f4  lea     rcx, [rbp+57h+arg_10]
0x1800220f8  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x1800220fd  mov     [rbp+57h+var_50], r15
0x180022101  mov     [rbp+57h+arg_10], rsi
0x180022105  lea     rax, [rbp+57h+arg_10]
0x180022109  mov     [rbp+57h+var_B8], rax
0x18002210d  mov     ecx, 18h; Size
0x180022112  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022117  mov     rbx, rax
0x18002211a  mov     [rbp+57h+var_B8], rax
0x18002211e  mov     dword ptr [rax+8], 1
0x180022125  mov     rcx, [rbp+57h+arg_10]
0x180022129  mov     [rbp+57h+arg_10], r15
0x18002212d  mov     [rax+10h], rcx
0x180022131  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180022138  lea     rax, off_18002E900
0x18002213f  mov     [rbx], rax
0x180022142  mov     [rbp+57h+var_B8], rbx
0x180022146  mov     [rbp+57h+var_C0], 7
0x18002214d  cmp     [rbp+57h+arg_10], r15
0x180022151  jz      short loc_18002215D
0x180022153  lea     rcx, [rbp+57h+arg_10]
0x180022157  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18002215c  nop
0x18002215d  mov     [rsp+110h+var_E8], r15
0x180022162  mov     rcx, [rdi]
0x180022165  mov     [rsp+110h+var_F0], r15
0x18002216a  test    rcx, rcx
0x18002216d  jnz     short loc_180022177
0x18002216f  mov     eax, r15d
0x180022172  mov     rsi, r15
0x180022175  jmp     short loc_180022198
0x180022177  mov     rax, [rcx]
0x18002217a  lea     r8, [rsp+110h+var_F0]
0x18002217f  lea     rdx, ??$guid_v@UIButtonBase@Primitives@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::Primitives::IButtonBase>
0x180022186  mov     rax, [rax]
0x180022189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002218e  mov     rsi, [rsp+110h+var_F0]
0x180022193  mov     [rsp+110h+var_F0], rsi
0x180022198  mov     dword ptr [rsp+110h+var_D8], r15d
0x18002219d  xorps   xmm0, xmm0
0x1800221a0  movdqu  [rbp+57h+var_D0], xmm0
0x1800221a5  test    eax, eax
0x1800221a7  js      loc_18002266B
0x1800221ad  mov     dword ptr [rsp+110h+var_D8], r15d
0x1800221b2  movdqu  [rbp+57h+var_D0], xmm0
0x1800221b7  mov     rax, [rsi]
0x1800221ba  lea     r8, [rsp+110h+var_E8]
0x1800221bf  mov     rdx, rbx
0x1800221c2  mov     rcx, rsi
0x1800221c5  mov     rax, [rax+70h]
0x1800221c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221ce  test    eax, eax
0x1800221d0  js      loc_180022678
0x1800221d6  test    rsi, rsi
0x1800221d9  jz      short loc_1800221E6
0x1800221db  lea     rcx, [rsp+110h+var_F0]
0x1800221e0  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x1800221e5  nop
0x1800221e6  lea     rcx, [rbp+57h+var_B8]
0x1800221ea  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x1800221ef  mov     ecx, 14h; this
0x1800221f4  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1800221f9  mov     rbx, rax
0x1800221fc  lea     rcx, [rax+1Ch]; Destination
0x180022200  mov     edx, 28h ; '('; DestinationSize
0x180022205  mov     r9d, edx; SourceSize
0x180022208  lea     r8, aTextblockbutto; "TextBlockButtonStyle"
0x18002220f  call    memcpy_s
0x180022214  mov     [rbp+57h+var_B8], rbx
0x180022218  mov     qword ptr [rbp+57h+var_A0], rbx
0x18002221c  lea     rdx, [rbp+57h+var_A0]; struct winrt::param::hstring *
  ... truncated ...
```
