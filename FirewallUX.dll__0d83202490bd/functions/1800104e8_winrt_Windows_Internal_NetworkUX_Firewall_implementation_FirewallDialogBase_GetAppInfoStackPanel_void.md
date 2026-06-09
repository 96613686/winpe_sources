# winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::GetAppInfoStackPanel(void)

- ea: `0x1800104e8`
- end: `0x180011a6a`
- name: `?GetAppInfoStackPanel@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@IEAA?AUStackPanel@Controls@Xaml@UI@67@XZ`
- size: `5506`
- prototype: `winrt::Windows::UI::Xaml::Controls::StackPanel *__fastcall(_QWORD *, winrt::Windows::UI::Xaml::Controls::StackPanel *)`
- caller_count: `2`
- callee_count: `41`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180017a90`
- `0x18001e0b0`

## callees

- `0x1800021c0`
- `0x180002d55`
- `0x180002d91`
- `0x180002d9d`
- `0x1800058b0`
- `0x180007940`
- `0x18000b24c`
- `0x18000b5d0`
- `0x18000b5f0`
- `0x18000db2c`
- `0x18000dd74`
- `0x18000de98`
- `0x18000ea58`
- `0x18000ec0c`
- `0x18000ec84`
- `0x18000ed88`
- `0x18000ee78`
- `0x18000efbc`
- `0x18000f660`
- `0x18000f7b0`
- `0x18000f858`
- `0x18000ff68`
- `0x18000ffac`
- `0x18001006c`
- `0x180010464`
- `0x1800104a4`
- `0x1800104e8`
- `0x1800121ac`
- `0x180012b2c`
- `0x180012df8`
- `0x180013128`
- `0x180013188`
- `0x180013214`
- `0x1800132ac`
- `0x180013818`
- `0x180013860`
- `0x1800138a8`
- `0x180013954`
- `0x1800148d0`
- `0x180014b14`
- `0x18002d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800111c0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800115c4`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800111c0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800115c4`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOverStream` at `0x18001080f`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOverStream` at `0x18001080f`

## string_xrefs

- `0x1800119ac`: `shellcommon\shell\networkux\firewallux\lib\firewalldialogbase.cpp`
- `0x1800119c1`: `shellcommon\shell\networkux\firewallux\lib\firewalldialogbase.cpp`
- `0x1800119d6`: `shellcommon\shell\networkux\firewallux\lib\firewalldialogbase.cpp`

## pseudocode

```c
winrt::Windows::UI::Xaml::Controls::StackPanel *__fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::GetAppInfoStackPanel(
        _QWORD *a1,
        winrt::Windows::UI::Xaml::Controls::StackPanel *a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rbx
  void (__fastcall ***v7)(_QWORD, __int64 *, __int64 **); // rcx
  int v8; // edi
  HRESULT v9; // eax
  LPVOID v10; // rbx
  int v11; // eax
  __int64 v12; // r8
  int StreamOfWICBitmapSourceWithOptions; // eax
  __int64 v14; // rbx
  int v15; // eax
  int v16; // eax
  LPVOID v17; // rcx
  int v18; // eax
  void *v19; // rdx
  LPVOID v20; // r14
  int v21; // eax
  int v22; // eax
  LPVOID v23; // rcx
  int v24; // eax
  int v25; // eax
  LPVOID v26; // rcx
  int v27; // eax
  int v28; // eax
  LPVOID v29; // rcx
  int v30; // eax
  __int64 v31; // rbx
  __int64 v32; // rbx
  void (__fastcall ***v33)(_QWORD, __int64 *, __int64 **); // rcx
  __int64 *v34; // rbx
  int v35; // edi
  __int64 v36; // rcx
  int v37; // eax
  void (__fastcall ***v38)(_QWORD, __int64 *, __int64 **); // rcx
  __int64 *v39; // rbx
  int v40; // edi
  __int64 v41; // rcx
  int v42; // eax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rbx
  void *v46; // rbx
  int v47; // eax
  HANDLE ProcessHeap; // rax
  __int64 v49; // rbx
  __int64 v50; // rbx
  void *v51; // rbx
  int v52; // esi
  HANDLE v53; // rax
  __int64 v54; // rbx
  __int64 v55; // rbx
  __int64 v56; // rax
  __int64 v57; // rax
  int ppv; // [rsp+20h] [rbp-E0h]
  LPVOID v60; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v61; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v62[2]; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v63[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v64; // [rsp+70h] [rbp-90h]
  _OWORD v65[2]; // [rsp+78h] [rbp-88h] BYREF
  __int16 v66; // [rsp+98h] [rbp-68h] BYREF
  __int64 (__fastcall ***v67)(LPVOID, void *, LPVOID *); // [rsp+A0h] [rbp-60h] BYREF
  void (__fastcall ***v68)(_QWORD, void *, LPVOID *); // [rsp+A8h] [rbp-58h] BYREF
  void (__fastcall ***v69)(_QWORD, void *, LPVOID *); // [rsp+B0h] [rbp-50h] BYREF
  void (__fastcall ***v70)(_QWORD, void *, LPVOID *); // [rsp+B8h] [rbp-48h] BYREF
  void (__fastcall ***v71)(_QWORD, void *, LPVOID *); // [rsp+C0h] [rbp-40h] BYREF
  void (__fastcall ***v72)(_QWORD, void *, LPVOID *); // [rsp+C8h] [rbp-38h] BYREF
  void (__fastcall ***v73)(_QWORD, void *, LPVOID *); // [rsp+D0h] [rbp-30h] BYREF
  __int64 v74; // [rsp+D8h] [rbp-28h] BYREF
  void (__fastcall ***v75)(_QWORD, void *, LPVOID *); // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v76[3]; // [rsp+E8h] [rbp-18h] BYREF
  IID rclsid; // [rsp+100h] [rbp+0h] BYREF
  __m128i si128; // [rsp+110h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v76[1] = a2;
  winrt::Windows::UI::Xaml::Controls::StackPanel::StackPanel(a2);
  v64 = 1;
  v65[0] = 0;
  v65[1] = _mm_load_si128((const __m128i *)&_xmm);
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::StackPanel>::Margin(
    a2,
    v65);
  winrt::Windows::UI::Xaml::Controls::Grid::Grid((winrt::Windows::UI::Xaml::Controls::Grid *)&v75);
  winrt::Windows::UI::Xaml::Controls::ColumnDefinition::ColumnDefinition((winrt::Windows::UI::Xaml::Controls::ColumnDefinition *)&v60);
  winrt::Windows::UI::Xaml::Controls::ColumnDefinition::ColumnDefinition((winrt::Windows::UI::Xaml::Controls::ColumnDefinition *)&v61);
  *(double *)&rclsid.Data1 = DOUBLE_1_0;
  *(_QWORD *)rclsid.Data4 = 0;
  winrt::impl::consume_Windows_UI_Xaml_Controls_IColumnDefinition<winrt::Windows::UI::Xaml::Controls::IColumnDefinition>::Width(
    &v60,
    &rclsid);
  *(double *)&rclsid.Data1 = DOUBLE_1_0;
  *(_QWORD *)rclsid.Data4 = 2;
  winrt::impl::consume_Windows_UI_Xaml_Controls_IColumnDefinition<winrt::Windows::UI::Xaml::Controls::IColumnDefinition>::Width(
    &v61,
    &rclsid);
  v4 = winrt::impl::consume_Windows_UI_Xaml_Controls_IGrid<winrt::Windows::UI::Xaml::Controls::IGrid>::ColumnDefinitions(
         &v75,
         v62);
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Xaml::Controls::ColumnDefinition>,winrt::Windows::UI::Xaml::Controls::ColumnDefinition>::Append(
    v4,
    &v60);
  if ( v62[0] )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v62);
  v5 = winrt::impl::consume_Windows_UI_Xaml_Controls_IGrid<winrt::Windows::UI::Xaml::Controls::IGrid>::ColumnDefinitions(
         &v75,
         v62);
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Xaml::Controls::ColumnDefinition>,winrt::Windows::UI::Xaml::Controls::ColumnDefinition>::Append(
    v5,
    &v61);
  if ( v62[0] )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v62);
  v6 = winrt::impl::consume_Windows_UI_Xaml_Controls_IPanel<winrt::Windows::UI::Xaml::Controls::Grid>::Children(a2, v76);
  if ( v75 )
  {
    v62[0] = 0;
    (**v75)(v75, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IUIElement>, v62);
    v67 = (__int64 (__fastcall ***)(LPVOID, void *, LPVOID *))v62[0];
  }
  else
  {
    v67 = 0;
  }
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Xaml::Controls::ColumnDefinition>,winrt::Windows::UI::Xaml::Controls::ColumnDefinition>::Append(
    v6,
    &v67);
  if ( v67 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v67);
  if ( v76[0] )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v76);
  if ( v61 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v61);
  if ( v60 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v60);
  *(_QWORD *)&rclsid.Data1 = &qword_18003C1B8;
  _InterlockedIncrement64(&qword_18003C1B8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::Image,winrt::Windows::Foundation::IActivationFactory> )
  {
    `winrt::Windows::UI::Xaml::Controls::Image::Image'::`1'::_lambda_52__::operator()(
      v7,
      &v74,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::Image,winrt::Windows::Foundation::IActivationFactory>);
    v8 = 3;
    v64 = 3;
    _InterlockedAdd64(&qword_18003C1B8, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_18003C1B8, 0xFFFFFFFFFFFFFFFFuLL);
    v63[0] = `winrt::Windows::UI::Xaml::Controls::Image::Image'::`1'::_lambda_52__::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::UI::Xaml::Controls::Image,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::UI::Xaml::Controls::Image (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      v7,
      (__int64)&v74,
      (void (__fastcall **)(__int64, __int64 *))v63);
    v8 = 3;
    v64 = 3;
  }
  if ( a1[6] )
  {
    rclsid = CLSID_WICImagingFactory2;
    v62[0] = 0;
    LODWORD(v63[0]) = 0;
    *(_OWORD *)&v63[1] = 0;
    v9 = CoCreateInstance_0(&rclsid, 0, 1u, &winrt::impl::guid_v<IWICImagingFactory>, v62);
    if ( v9 < 0 )
      winrt::throw_hresult((unsigned int)v9, v63);
    v10 = v62[0];
    *(LPVOID *)&rclsid.Data1 = v62[0];
    v64 = 15;
    v60 = 0;
    v11 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, LPVOID *))(*(_QWORD *)v62[0] + 176LL))(v62[0], a1[6], &v60);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xD1,
        (int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewalldialogbase.cpp",
        (const char *)(unsigned int)v11,
        ppv);
    v76[0] = 0;
    v61 = 0;
    *(GUID *)v63 = GUID_WICPixelFormat32bppBGRA;
    StreamOfWICBitmapSourceWithOptions = GetStreamOfWICBitmapSourceWithOptions(v10, v60, v12, v63);
    if ( StreamOfWICBitmapSourceWithOptions < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xDB,
        (int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewalldialogbase.cpp",
        (const char *)(unsigned int)StreamOfWICBitmapSourceWithOptions,
        ppv);
    if ( v61 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v61);
    v14 = v76[0];
    v15 = CreateRandomAccessStreamOverStream(
            v76[0],
            0,
            &winrt::impl::guid_v<winrt::Windows::Storage::Streams::IRandomAccessStream>,
            &v61);
    if ( v15 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xDD,
        (int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewalldialogbase.cpp",
        (const char *)(unsigned int)v15,
        ppv);
    v63[0] = &qword_18003C1F8;
    _InterlockedIncrement64(&qword_18003C1F8);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Media::Imaging::BitmapImage,winrt::Windows::Foundation::IActivationFactory> )
    {
      `winrt::Windows::UI::Xaml::Media::Imaging::BitmapImage::BitmapImage'::`1'::_lambda_202__::operator()(
        retaddr,
        &v67,
        &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Media::Imaging::BitmapImage,winrt::Windows::Foundation::IActivationFactory>);
      v8 = 31;
      v64 = 31;
      _InterlockedAdd64(&qword_18003C1F8, 0xFFFFFFFFFFFFFFFFuLL);
    }
    else
    {
      _InterlockedAdd64(&qword_18003C1F8, 0xFFFFFFFFFFFFFFFFuLL);
      v63[0] = `winrt::Windows::UI::Xaml::Media::Imaging::BitmapImage::BitmapImage'::`1'::_lambda_202__::_lambda_invoker_cdecl_;
      winrt::impl::factory_cache_entry<winrt::Windows::UI::Xaml::Media::Imaging::BitmapImage,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::UI::Xaml::Media::Imaging::BitmapImage (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        (void (__fastcall ***)(_QWORD, __int64 *, __int64 **))retaddr,
        (__int64)&v67,
        (void (__fastcall **)(__int64, __int64 *))v63);
      v8 = 31;
      v64 = 31;
    }
    v63[0] = 0;
    if ( v67 )
    {
      v16 = (**v67)(v67, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::Media::Imaging::IBitmapSource>, v63);
      v17 = v63[0];
    }
    else
    {
      v16 = 0;
      v17 = 0;
    }
    LODWORD(v65[0]) = 0;
    *(_OWORD *)((char *)v65 + 8) = 0;
    if ( v16 < 0 )
      winrt::throw_hresult((unsigned int)v16, v65);
    LODWORD(v65[0]) = 0;
    *(_OWORD *)((char *)v65 + 8) = 0;
    v18 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v17 + 64LL))(v17, v61);
    if ( v18 < 0 )
      winrt::throw_hresult((unsigned int)v18, v65);
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v63);
    if ( v67 )
    {
      v63[0] = 0;
      (**v67)(v67, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::Media::IImageSource>, v63);
      v19 = v63[0];
      v20 = v63[0];
    }
    else
    {
      v19 = 0;
      v20 = 0;
    }
    v63[0] = v19;
    LODWORD(v65[0]) = 0;
    *(_OWORD *)((char *)v65 + 8) = 0;
    v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v74 + 56LL))(v74);
    if ( v21 < 0 )
      winrt::throw_hresult((unsigned int)v21, v65);
    if ( v20 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v63);
    if ( v67 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v67);
    if ( v61 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v61);
    if ( v14 )
      winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(v76);
    if ( v60 )
      winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&v60);
    if ( v62[0] )
      winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&rclsid);
  }
  v63[0] = 0;
  if ( v74 )
  {
    v22 = (**(__int64 (__fastcall ***)(__int64, void *, LPVOID *))v74)(
            v74,
            &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IFrameworkElement>,
            v63);
    v23 = v63[0];
  }
  else
  {
    v22 = 0;
    v23 = 0;
  }
  LODWORD(v65[0]) = 0;
  *(_OWORD *)((char *)v65 + 8) = 0;
  if ( v22 < 0 )
    winrt::throw_hresult((unsigned int)v22, v65);
  LODWORD(v65[0]) = 0;
  *(_OWORD *)((char *)v65 + 8) = 0;
  v24 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v23 + 128LL))(v23);
  if ( v24 < 0 )
    winrt::throw_hresult((unsigned int)v24, v65);
  winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v63);
  v63[0] = 0;
  if ( v74 )
  {
    v25 = (**(__int64 (__fastcall ***)(__int64, void *, LPVOID *))v74)(
            v74,
            &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IFrameworkElement>,
            v63);
    v26 = v63[0];
  }
  else
  {
    v25 = 0;
    v26 = 0;
  }
  LODWORD(v65[0]) = 0;
  *(_OWORD *)((char *)v65 + 8) = 0;
  if ( v25 < 0 )
    winrt::throw_hresult((unsigned int)v25, v65);
  LODWORD(v65[0]) = 0;
  *(_OWORD *)((char *)v65 + 8) = 0;
  rclsid = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v27 = (*(__int64 (__fastcall **)(LPVOID, IID *))(*(_QWORD *)v26 + 256LL))(v26, &rclsid);
  if ( v27 < 0 )
    winrt::throw_hresult((unsigned int)v27, v65);
  winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v63);
  v63[0] = 0;
  if ( v74 )
  {
    v28 = (**(__int64 (__fastcall ***)(__int64, void *, LPVOID *))v74)(
            v74,
            &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IFrameworkElement>,
            v63);
    v29 = v63[0];
  }
  else
  {
    v28 = 0;
    v29 = 0;
  }
  LODWORD(v65[0]) = 0;
  *(_OWORD *)((char *)v65 + 8) = 0;
  if ( v28 < 0 )
    winrt::throw_hresult((unsigned int)v28, v65);
  LODWORD(v65[0]) = 0;
  *(_OWORD *)((char *)v65 + 8) = 0;
  v30 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v29 + 144LL))(v29);
  if ( v30 < 0 )
    winrt::throw_hresult((unsigned int)v30, v65);
  winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v63);
  v31 = winrt::impl::consume_Windows_UI_Xaml_Controls_IPanel<winrt::Windows::UI::Xaml::Controls::Grid>::Children(
          &v75,
          v62);
  if ( v74 )
  {
    v63[0] = 0;
    (**(void (__fastcall ***)(__int64, void *, LPVOID *))v74)(
      v74,
      &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IUIElement>,
      v63);
    v60 = v63[0];
  }
  else
  {
    v60 = 0;
  }
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Xaml::Controls::ColumnDefinition>,winrt::Windows::UI::Xaml::Controls::ColumnDefinition>::Append(
    v31,
    &v60);
  if ( v60 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v60);
  if ( v62[0] )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v62);
  if ( v74 )
  {
    v63[0] = 0;
    (**(void (__fastcall ***)(__int64, void *, LPVOID *))v74)(
      v74,
      &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IFrameworkElement>,
      v63);
    v60 = v63[0];
  }
  else
  {
    v60 = 0;
  }
  winrt::Windows::UI::Xaml::Controls::Grid::SetColumn(
    (const struct winrt::Windows::UI::Xaml::FrameworkElement *)&v60,
    0);
  if ( v60 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v60);
  v66 = 600;
  winrt::Windows::UI::Xaml::Controls::TextBlock::TextBlock((winrt::Windows::UI::Xaml::Controls::TextBlock *)&v72);
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::FontSize(&v72);
  LODWORD(v61) = 0;
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::HorizontalAlignment(
    &v72,
    &v61);
  LODWORD(v61) = 1;
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::VerticalAlignment(
    &v72,
    &v61);
  LODWORD(v61) = 2;
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::TextWrapping(
    &v72,
    &v61);
  *(_QWORD *)&v65[0] = a1[4];
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::Text(
    &v72,
    v65);
  v65[0] = 0;
  v65[1] = _mm_load_si128((const __m128i *)&_xmm);
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::StackPanel>::Margin(
    &v72,
    v65);
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::FontWeight(
    &v72,
    &v66);
  v32 = winrt::impl::consume_Windows_UI_Xaml_Controls_IPanel<winrt::Windows::UI::Xaml::Controls::Grid>::Children(
          &v75,
          v62);
  if ( v72 )
  {
    v63[0] = 0;
    (**v72)(v72, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IUIElement>, v63);
    v60 = v63[0];
  }
  else
  {
    v60 = 0;
  }
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Xaml::Controls::ColumnDefinition>,winrt::Windows::UI::Xaml::Controls::ColumnDefinition>::Append(
    v32,
    &v60);
  if ( v60 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v60);
  if ( v62[0] )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v62);
  if ( v72 )
  {
    v63[0] = 0;
    (**v72)(v72, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IFrameworkElement>, v63);
    v60 = v63[0];
  }
  else
  {
    v60 = 0;
  }
  winrt::Windows::UI::Xaml::Controls::Grid::SetColumn(
    (const struct winrt::Windows::UI::Xaml::FrameworkElement *)&v60,
    1);
  if ( v60 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v60);
  *((_QWORD *)&v65[0] + 1) = 0xB00000001LL;
  *((_QWORD *)&v65[1] + 1) = L"DisplayName";
  *(_QWORD *)&v65[0] = (char *)v65 + 8;
  if ( v72 )
  {
    v63[0] = 0;
    (**v72)(v72, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IDependencyObject>, v63);
    v60 = v63[0];
  }
  else
  {
    v60 = 0;
  }
  winrt::Windows::UI::Xaml::Automation::AutomationProperties::SetAutomationId(
    (const struct winrt::Windows::UI::Xaml::DependencyObject *)&v60,
    (const struct winrt::param::hstring *)v65);
  if ( v60 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v60);
  winrt::Windows::UI::Xaml::Controls::Grid::Grid((winrt::Windows::UI::Xaml::Controls::Grid *)&v73);
  winrt::Windows::UI::Xaml::Controls::ColumnDefinition::ColumnDefinition((winrt::Windows::UI::Xaml::Controls::ColumnDefinition *)&v61);
  winrt::Windows::UI::Xaml::Controls::ColumnDefinition::ColumnDefinition((winrt::Windows::UI::Xaml::Controls::ColumnDefinition *)&v67);
  *(double *)&rclsid.Data1 = DOUBLE_1_0;
  *(_QWORD *)rclsid.Data4 = 0;
  winrt::impl::consume_Windows_UI_Xaml_Controls_IColumnDefinition<winrt::Windows::UI::Xaml::Controls::IColumnDefinition>::Width(
    &v61,
    &rclsid);
  *(double *)&rclsid.Data1 = DOUBLE_1_0;
  *(_QWORD *)rclsid.Data4 = 2;
  winrt::impl::consume_Windows_UI_Xaml_Controls_IColumnDefinition<winrt::Windows::UI::Xaml::Controls::IColumnDefinition>::Width(
    &v67,
    &rclsid);
  v34 = (__int64 *)winrt::impl::consume_Windows_UI_Xaml_Controls_IGrid<winrt::Windows::UI::Xaml::Controls::IGrid>::RowDefinitions(
                     &v73,
                     v63);
  *(_QWORD *)&rclsid.Data1 = &qword_18003BDE8;
  _InterlockedIncrement64(&qword_18003BDE8);
  v35 = v8 | 0x20;
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::RowDefinition,winrt::Windows::Foundation::IActivationFactory> )
  {
    `winrt::Windows::UI::Xaml::Controls::RowDefinition::RowDefinition'::`1'::_lambda_72__::operator()(
      v33,
      &v60,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::RowDefinition,winrt::Windows::Foundation::IActivationFactory>);
    v64 = v35;
    _InterlockedAdd64(&qword_18003BDE8, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_18003BDE8, 0xFFFFFFFFFFFFFFFFuLL);
    *(_QWORD *)&rclsid.Data1 = `winrt::Windows::UI::Xaml::Controls::RowDefinition::RowDefinition'::`1'::_lambda_72__::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::UI::Xaml::Controls::RowDefinition,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::UI::Xaml::Controls::RowDefinition (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      v33,
      (__int64)&v60,
      (void (__fastcall **)(__int64, __int64 *))&rclsid);
    v64 = v35;
  }
  v36 = *v34;
  LODWORD(v65[0]) = 0;
  *(_OWORD *)((char *)v65 + 8) = 0;
  v37 = (*(__int64 (__fastcall **)(__int64, LPVOID))(*(_QWORD *)v36 + 104LL))(v36, v60);
  if ( v37 < 0 )
    winrt::throw_hresult((unsigned int)v37, v65);
  if ( v60 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v60);
  if ( v63[0] )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v63);
  v39 = (__int64 *)winrt::impl::consume_Windows_UI_Xaml_Controls_IGrid<winrt::Windows::UI::Xaml::Controls::IGrid>::RowDefinitions(
                     &v73,
                     v63);
  *(_QWORD *)&rclsid.Data1 = &qword_18003BDE8;
  _InterlockedIncrement64(&qword_18003BDE8);
  v40 = v35 | 0x40;
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::RowDefinition,winrt::Windows::Foundation::IActivationFactory> )
  {
    `winrt::Windows::UI::Xaml::Controls::RowDefinition::RowDefinition'::`1'::_lambda_72__::operator()(
      v38,
      &v60,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::RowDefinition,winrt::Windows::Foundation::IActivationFactory>);
    v64 = v40;
    _InterlockedAdd64(&qword_18003BDE8, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_18003BDE8, 0xFFFFFFFFFFFFFFFFuLL);
    *(_QWORD *)&rclsid.Data1 = `winrt::Windows::UI::Xaml::Controls::RowDefinition::RowDefinition'::`1'::_lambda_72__::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::UI::Xaml::Controls::RowDefinition,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::UI::Xaml::Controls::RowDefinition (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      v38,
      (__int64)&v60,
      (void (__fastcall **)(__int64, __int64 *))&rclsid);
    v64 = v40;
  }
  v41 = *v39;
  LODWORD(v65[0]) = 0;
  *(_OWORD *)((char *)v65 + 8) = 0;
  v42 = (*(__int64 (__fastcall **)(__int64, LPVOID))(*(_QWORD *)v41 + 104LL))(v41, v60);
  if ( v42 < 0 )
    winrt::throw_hresult((unsigned int)v42, v65);
  if ( v60 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v60);
  if ( v63[0] )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v63);
  v43 = winrt::impl::consume_Windows_UI_Xaml_Controls_IGrid<winrt::Windows::UI::Xaml::Controls::IGrid>::ColumnDefinitions(
          &v73,
          v63);
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Xaml::Controls::ColumnDefinition>,winrt::Windows::UI::Xaml::Controls::ColumnDefinition>::Append(
    v43,
    &v61);
  if ( v63[0] )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v63);
  v44 = winrt::impl::consume_Windows_UI_Xaml_Controls_IGrid<winrt::Windows::UI::Xaml::Controls::IGrid>::ColumnDefinitions(
          &v73,
          v63);
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Xaml::Controls::ColumnDefinition>,winrt::Windows::UI::Xaml::Controls::ColumnDefinition>::Append(
    v44,
    &v67);
  if ( v63[0] )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v63);
  v45 = winrt::impl::consume_Windows_UI_Xaml_Controls_IPanel<winrt::Windows::UI::Xaml::Controls::Grid>::Children(
          a2,
          v62);
  if ( v73 )
  {
    v63[0] = 0;
    (**v73)(v73, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IUIElement>, v63);
    v60 = v63[0];
  }
  else
  {
    v60 = 0;
  }
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Xaml::Controls::ColumnDefinition>,winrt::Windows::UI::Xaml::Controls::ColumnDefinition>::Append(
    v45,
    &v60);
  if ( v60 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v60);
  if ( v62[0] )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v62);
  if ( v67 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v67);
  if ( v61 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v61);
  winrt::Windows::UI::Xaml::Controls::TextBlock::TextBlock((winrt::Windows::UI::Xaml::Controls::TextBlock *)&v71);
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::FontSize(&v71);
  LODWORD(v61) = 0;
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::HorizontalAlignment(
    &v71,
    &v61);
  LODWORD(v61) = 0;
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::VerticalAlignment(
    &v71,
    &v61);
  LODWORD(v61) = 2;
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::TextWrapping(
    &v71,
    &v61);
  *(_QWORD *)&v65[0] = *(_QWORD *)GetResourceString(&rclsid, 100);
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::Text(
    &v71,
    v65);
  v46 = *(void **)&rclsid.Data1;
  if ( *(_QWORD *)&rclsid.Data1 )
  {
    v47 = _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)&rclsid.Data1 + 24LL));
    if ( v47 )
    {
      if ( v47 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v46);
    }
  }
  v65[0] = 0;
  v65[1] = _mm_load_si128((const __m128i *)&_xmm);
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::StackPanel>::Margin(
    &v71,
    v65);
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::FontWeight(
    &v71,
    &v66);
  v49 = winrt::impl::consume_Windows_UI_Xaml_Controls_IPanel<winrt::Windows::UI::Xaml::Controls::Grid>::Children(
          &v73,
          v62);
  if ( v71 )
  {
    v63[0] = 0;
    (**v71)(v71, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IUIElement>, v63);
    v60 = v63[0];
  }
  else
  {
    v60 = 0;
  }
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Xaml::Controls::ColumnDefinition>,winrt::Windows::UI::Xaml::Controls::ColumnDefinition>::Append(
    v49,
    &v60);
  if ( v60 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v60);
  if ( v62[0] )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v62);
  if ( v71 )
  {
    v63[0] = 0;
    (**v71)(v71, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IFrameworkElement>, v63);
    v60 = v63[0];
  }
  else
  {
    v60 = 0;
  }
  winrt::Windows::UI::Xaml::Controls::Grid::SetRow((const struct winrt::Windows::UI::Xaml::FrameworkElement *)&v60, 0);
  if ( v60 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v60);
  if ( v71 )
  {
    v63[0] = 0;
    (**v71)(v71, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IFrameworkElement>, v63);
    v60 = v63[0];
  }
  else
  {
    v60 = 0;
  }
  winrt::Windows::UI::Xaml::Controls::Grid::SetColumn(
    (const struct winrt::Windows::UI::Xaml::FrameworkElement *)&v60,
    0);
  if ( v60 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v60);
  winrt::Windows::UI::Xaml::Controls::TextBlock::TextBlock((winrt::Windows::UI::Xaml::Controls::TextBlock *)&v70);
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::FontSize(&v70);
  LODWORD(v61) = 0;
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::HorizontalAlignment(
    &v70,
    &v61);
  LODWORD(v61) = 0;
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::VerticalAlignment(
    &v70,
    &v61);
  LODWORD(v61) = 2;
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::TextWrapping(
    &v70,
    &v61);
  *(_QWORD *)&v65[0] = a1[5];
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::Text(
    &v70,
    v65);
  memset(v65, 0, sizeof(v65));
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::StackPanel>::Margin(
    &v70,
    v65);
  v50 = winrt::impl::consume_Windows_UI_Xaml_Controls_IPanel<winrt::Windows::UI::Xaml::Controls::Grid>::Children(
          &v73,
          v62);
  if ( v70 )
  {
    v63[0] = 0;
    (**v70)(v70, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IUIElement>, v63);
    v60 = v63[0];
  }
  else
  {
    v60 = 0;
  }
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Xaml::Controls::ColumnDefinition>,winrt::Windows::UI::Xaml::Controls::ColumnDefinition>::Append(
    v50,
    &v60);
  if ( v60 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v60);
  if ( v62[0] )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v62);
  if ( v70 )
  {
    v63[0] = 0;
    (**v70)(v70, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IFrameworkElement>, v63);
    v60 = v63[0];
  }
  else
  {
    v60 = 0;
  }
  winrt::Windows::UI::Xaml::Controls::Grid::SetRow((const struct winrt::Windows::UI::Xaml::FrameworkElement *)&v60, 0);
  if ( v60 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v60);
  if ( v70 )
  {
    v63[0] = 0;
    (**v70)(v70, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IFrameworkElement>, v63);
    v60 = v63[0];
  }
  else
  {
    v60 = 0;
  }
  winrt::Windows::UI::Xaml::Controls::Grid::SetColumn(
    (const struct winrt::Windows::UI::Xaml::FrameworkElement *)&v60,
    1);
  if ( v60 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v60);
  *((_QWORD *)&v65[0] + 1) = 0x900000001LL;
  *((_QWORD *)&v65[1] + 1) = L"Publisher";
  *(_QWORD *)&v65[0] = (char *)v65 + 8;
  if ( v70 )
  {
    v63[0] = 0;
    (**v70)(v70, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IDependencyObject>, v63);
    v60 = v63[0];
  }
  else
  {
    v60 = 0;
  }
  winrt::Windows::UI::Xaml::Automation::AutomationProperties::SetAutomationId(
    (const struct winrt::Windows::UI::Xaml::DependencyObject *)&v60,
    (const struct winrt::param::hstring *)v65);
  if ( v60 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v60);
  winrt::Windows::UI::Xaml::Controls::TextBlock::TextBlock((winrt::Windows::UI::Xaml::Controls::TextBlock *)&v69);
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::FontSize(&v69);
  LODWORD(v61) = 0;
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::HorizontalAlignment(
    &v69,
    &v61);
  LODWORD(v61) = 0;
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::VerticalAlignment(
    &v69,
    &v61);
  LODWORD(v61) = 2;
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::TextWrapping(
    &v69,
    &v61);
  *(_QWORD *)&v65[0] = *(_QWORD *)GetResourceString(&rclsid, 101);
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::Text(
    &v69,
    v65);
  v51 = *(void **)&rclsid.Data1;
  if ( *(_QWORD *)&rclsid.Data1 )
  {
    v52 = _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)&rclsid.Data1 + 24LL));
    if ( v52 )
    {
      if ( v52 < 0 )
        abort();
    }
    else
    {
      v53 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v53, 0, v51);
    }
  }
  v65[0] = 0;
  v65[1] = _mm_load_si128((const __m128i *)&_xmm);
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::StackPanel>::Margin(
    &v69,
    v65);
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::FontWeight(
    &v69,
    &v66);
  v54 = winrt::impl::consume_Windows_UI_Xaml_Controls_IPanel<winrt::Windows::UI::Xaml::Controls::Grid>::Children(
          &v73,
          v62);
  if ( v69 )
  {
    v63[0] = 0;
    (**v69)(v69, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IUIElement>, v63);
    v60 = v63[0];
  }
  else
  {
    v60 = 0;
  }
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Xaml::Controls::ColumnDefinition>,winrt::Windows::UI::Xaml::Controls::ColumnDefinition>::Append(
    v54,
    &v60);
  if ( v60 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v60);
  if ( v62[0] )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v62);
  if ( v69 )
  {
    v63[0] = 0;
    (**v69)(v69, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IFrameworkElement>, v63);
    v60 = v63[0];
  }
  else
  {
    v60 = 0;
  }
  winrt::Windows::UI::Xaml::Controls::Grid::SetRow((const struct winrt::Windows::UI::Xaml::FrameworkElement *)&v60, 1);
  if ( v60 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v60);
  if ( v69 )
  {
    v63[0] = 0;
    (**v69)(v69, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IFrameworkElement>, v63);
    v60 = v63[0];
  }
  else
  {
    v60 = 0;
  }
  winrt::Windows::UI::Xaml::Controls::Grid::SetColumn(
    (const struct winrt::Windows::UI::Xaml::FrameworkElement *)&v60,
    0);
  if ( v60 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v60);
  winrt::Windows::UI::Xaml::Controls::TextBlock::TextBlock((winrt::Windows::UI::Xaml::Controls::TextBlock *)&v68);
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::FontSize(&v68);
  LODWORD(v61) = 0;
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::HorizontalAlignment(
    &v68,
    &v61);
  LODWORD(v61) = 0;
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::VerticalAlignment(
    &v68,
    &v61);
  LODWORD(v61) = 2;
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::TextWrapping(
    &v68,
    &v61);
  *(_QWORD *)&v65[0] = a1[3];
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::Text(
    &v68,
    v65);
  memset(v65, 0, sizeof(v65));
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::StackPanel>::Margin(
    &v68,
    v65);
  v55 = winrt::impl::consume_Windows_UI_Xaml_Controls_IPanel<winrt::Windows::UI::Xaml::Controls::Grid>::Children(
          &v73,
          v62);
  if ( v68 )
  {
    v63[0] = 0;
    (**v68)(v68, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IUIElement>, v63);
    v60 = v63[0];
  }
  else
  {
    v60 = 0;
  }
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Xaml::Controls::ColumnDefinition>,winrt::Windows::UI::Xaml::Controls::ColumnDefinition>::Append(
    v55,
    &v60);
  if ( v60 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v60);
  if ( v62[0] )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v62);
  if ( v68 )
  {
    v63[0] = 0;
    (**v68)(v68, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IFrameworkElement>, v63);
    v60 = v63[0];
  }
  else
  {
    v60 = 0;
  }
  winrt::Windows::UI::Xaml::Controls::Grid::SetRow((const struct winrt::Windows::UI::Xaml::FrameworkElement *)&v60, 1);
  if ( v60 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v60);
  if ( v68 )
  {
    v63[0] = 0;
    (**v68)(v68, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IFrameworkElement>, v63);
    v60 = v63[0];
  }
  else
  {
    v60 = 0;
  }
  winrt::Windows::UI::Xaml::Controls::Grid::SetColumn(
    (const struct winrt::Windows::UI::Xaml::FrameworkElement *)&v60,
    1);
  if ( v60 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v60);
  winrt::param::hstring::hstring((winrt::param::hstring *)v65, L"Path");
  if ( v68 )
  {
    v63[0] = 0;
    (**v68)(v68, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IDependencyObject>, v63);
    v62[0] = v63[0];
  }
  else
  {
    v62[0] = 0;
  }
  winrt::Windows::UI::Xaml::Automation::AutomationProperties::SetAutomationId(
    (const struct winrt::Windows::UI::Xaml::DependencyObject *)v62,
    (const struct winrt::param::hstring *)v65);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v62);
  v56 = winrt::impl::base_one<winrt::Windows::UI::Xaml::Controls::TextBlock,winrt::Windows::UI::Xaml::UIElement>::operator winrt::Windows::UI::Xaml::UIElement(
          &v69,
          &rclsid);
  std::vector<winrt::Windows::UI::Xaml::UIElement>::push_back(a1 + 7, v56);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&rclsid);
  v57 = winrt::impl::base_one<winrt::Windows::UI::Xaml::Controls::TextBlock,winrt::Windows::UI::Xaml::UIElement>::operator winrt::Windows::UI::Xaml::UIElement(
          &v68,
          v63);
  std::vector<winrt::Windows::UI::Xaml::UIElement>::push_back(a1 + 7, v57);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v63);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v68);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v69);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v70);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v71);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v73);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v72);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v74);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v75);
  return a2;
}

```

## disassembly

```asm
0x1800104e8  mov     rax, rsp
0x1800104eb  mov     [rax+18h], rbx
0x1800104ef  push    rbp
0x1800104f0  push    rsi
0x1800104f1  push    rdi
0x1800104f2  push    r12
0x1800104f4  push    r13
0x1800104f6  push    r14
0x1800104f8  push    r15
0x1800104fa  lea     rbp, [rsp-50h]
0x1800104ff  sub     rsp, 150h
0x180010506  movaps  xmmword ptr [rax-48h], xmm6
0x18001050a  movaps  xmmword ptr [rax-58h], xmm7
0x18001050e  mov     rax, cs:__security_cookie
0x180010515  xor     rax, rsp
0x180010518  mov     [rbp+80h+var_60], rax
0x18001051c  mov     r15, rdx
0x18001051f  mov     r13, rcx
0x180010522  mov     [rbp+80h+var_90], rdx
0x180010526  xor     r12d, r12d
0x180010529  mov     [rsp+180h+var_110], r12d
0x18001052e  mov     rcx, rdx; this
0x180010531  call    ??0StackPanel@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ; winrt::Windows::UI::Xaml::Controls::StackPanel::StackPanel(void)
0x180010536  mov     [rsp+180h+var_110], 1
0x18001053e  xorps   xmm0, xmm0
0x180010541  movups  [rsp+180h+var_108], xmm0
0x180010546  movdqa  xmm1, cs:__xmm@40280000000000000000000000000000
0x18001054e  movups  [rbp+80h+var_F8], xmm1
0x180010552  lea     rdx, [rsp+180h+var_108]
0x180010557  mov     rcx, r15
0x18001055a  call    ?Margin@?$consume_Windows_UI_Xaml_IFrameworkElement@UStackPanel@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUThickness@Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::StackPanel>::Margin(winrt::Windows::UI::Xaml::Thickness const &)
0x18001055f  lea     rcx, [rbp+80h+var_A0]; this
0x180010563  call    ??0Grid@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ; winrt::Windows::UI::Xaml::Controls::Grid::Grid(void)
0x180010568  nop
0x180010569  lea     rcx, [rsp+180h+var_150]; this
0x18001056e  call    ??0ColumnDefinition@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ; winrt::Windows::UI::Xaml::Controls::ColumnDefinition::ColumnDefinition(void)
0x180010573  nop
0x180010574  lea     rcx, [rsp+180h+var_148]; this
0x180010579  call    ??0ColumnDefinition@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ; winrt::Windows::UI::Xaml::Controls::ColumnDefinition::ColumnDefinition(void)
0x18001057e  nop
0x18001057f  movsd   xmm7, cs:__real@3ff0000000000000
0x180010587  movsd   qword ptr [rbp+80h+rclsid.Data1], xmm7
0x18001058c  mov     qword ptr [rbp+80h+rclsid.Data4], r12
0x180010590  lea     rdx, [rbp+80h+rclsid]
0x180010594  lea     rcx, [rsp+180h+var_150]
0x180010599  call    ?Width@?$consume_Windows_UI_Xaml_Controls_IColumnDefinition@UIColumnDefinition@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUGridLength@Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_IColumnDefinition<winrt::Windows::UI::Xaml::Controls::IColumnDefinition>::Width(winrt::Windows::UI::Xaml::GridLength const &)
0x18001059e  movsd   qword ptr [rbp+80h+rclsid.Data1], xmm7
0x1800105a3  mov     qword ptr [rbp+80h+rclsid.Data4], 2
0x1800105ab  lea     rdx, [rbp+80h+rclsid]
0x1800105af  lea     rcx, [rsp+180h+var_148]
0x1800105b4  call    ?Width@?$consume_Windows_UI_Xaml_Controls_IColumnDefinition@UIColumnDefinition@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUGridLength@Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_IColumnDefinition<winrt::Windows::UI::Xaml::Controls::IColumnDefinition>::Width(winrt::Windows::UI::Xaml::GridLength const &)
0x1800105b9  lea     rdx, [rsp+180h+var_140]
0x1800105be  lea     rcx, [rbp+80h+var_A0]
0x1800105c2  call    ?ColumnDefinitions@?$consume_Windows_UI_Xaml_Controls_IGrid@UIGrid@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Xaml_Controls_IGrid<winrt::Windows::UI::Xaml::Controls::IGrid>::ColumnDefinitions(void)
0x1800105c7  nop
0x1800105c8  lea     rdx, [rsp+180h+var_150]
0x1800105cd  mov     rcx, rax
0x1800105d0  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@UColumnDefinition@Controls@Xaml@UI@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UColumnDefinition@Controls@Xaml@UI@45@@impl@winrt@@QEBA@AEBUColumnDefinition@Controls@Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Xaml::Controls::ColumnDefinition>,winrt::Windows::UI::Xaml::Controls::ColumnDefinition>::Append(winrt::Windows::UI::Xaml::Controls::ColumnDefinition const &)
0x1800105d5  nop
0x1800105d6  cmp     [rsp+180h+var_140], r12
0x1800105db  jz      short loc_1800105E7
0x1800105dd  lea     rcx, [rsp+180h+var_140]
0x1800105e2  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x1800105e7  lea     rdx, [rsp+180h+var_140]
0x1800105ec  lea     rcx, [rbp+80h+var_A0]
0x1800105f0  call    ?ColumnDefinitions@?$consume_Windows_UI_Xaml_Controls_IGrid@UIGrid@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Xaml_Controls_IGrid<winrt::Windows::UI::Xaml::Controls::IGrid>::ColumnDefinitions(void)
0x1800105f5  nop
0x1800105f6  lea     rdx, [rsp+180h+var_148]
0x1800105fb  mov     rcx, rax
0x1800105fe  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@UColumnDefinition@Controls@Xaml@UI@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UColumnDefinition@Controls@Xaml@UI@45@@impl@winrt@@QEBA@AEBUColumnDefinition@Controls@Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Xaml::Controls::ColumnDefinition>,winrt::Windows::UI::Xaml::Controls::ColumnDefinition>::Append(winrt::Windows::UI::Xaml::Controls::ColumnDefinition const &)
0x180010603  nop
0x180010604  cmp     [rsp+180h+var_140], r12
0x180010609  jz      short loc_180010615
0x18001060b  lea     rcx, [rsp+180h+var_140]
0x180010610  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180010615  lea     rdx, [rbp+80h+var_98]
0x180010619  mov     rcx, r15
0x18001061c  call    ?Children@?$consume_Windows_UI_Xaml_Controls_IPanel@UGrid@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Xaml_Controls_IPanel<winrt::Windows::UI::Xaml::Controls::Grid>::Children(void)
0x180010621  mov     rbx, rax
0x180010624  mov     rcx, [rbp+80h+var_A0]
0x180010628  test    rcx, rcx
0x18001062b  jnz     short loc_180010633
0x18001062d  mov     [rbp+80h+var_E0], r12
0x180010631  jmp     short loc_180010658
0x180010633  mov     [rsp+180h+var_140], r12
0x180010638  mov     rax, [rcx]
0x18001063b  lea     r8, [rsp+180h+var_140]
0x180010640  lea     rdx, ??$guid_v@UIUIElement@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::IUIElement>
0x180010647  mov     rax, [rax]
0x18001064a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001064f  mov     rax, [rsp+180h+var_140]
0x180010654  mov     [rbp+80h+var_E0], rax
0x180010658  lea     rdx, [rbp+80h+var_E0]
0x18001065c  mov     rcx, rbx
0x18001065f  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@UColumnDefinition@Controls@Xaml@UI@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UColumnDefinition@Controls@Xaml@UI@45@@impl@winrt@@QEBA@AEBUColumnDefinition@Controls@Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Xaml::Controls::ColumnDefinition>,winrt::Windows::UI::Xaml::Controls::ColumnDefinition>::Append(winrt::Windows::UI::Xaml::Controls::ColumnDefinition const &)
0x180010664  nop
0x180010665  cmp     [rbp+80h+var_E0], r12
0x180010669  jz      short loc_180010675
0x18001066b  lea     rcx, [rbp+80h+var_E0]
0x18001066f  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180010674  nop
0x180010675  cmp     [rbp+80h+var_98], r12
0x180010679  jz      short loc_180010685
0x18001067b  lea     rcx, [rbp+80h+var_98]
0x18001067f  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180010684  nop
0x180010685  cmp     [rsp+180h+var_148], r12
0x18001068a  jz      short loc_180010697
0x18001068c  lea     rcx, [rsp+180h+var_148]
0x180010691  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180010696  nop
0x180010697  cmp     [rsp+180h+var_150], r12
0x18001069c  jz      short loc_1800106A8
0x18001069e  lea     rcx, [rsp+180h+var_150]
0x1800106a3  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x1800106a8  lea     rax, qword_18003C1B8
0x1800106af  mov     qword ptr [rbp+80h+rclsid.Data1], rax
0x1800106b3  lock inc cs:qword_18003C1B8
0x1800106bb  cmp     cs:??$factory_cache_entry_v@UImage@Controls@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@3U?$factory_cache_entry@UImage@Controls@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@56@@12@A, r12; factory_cache_entry<winrt::Windows::UI::Xaml::Controls::Image,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Controls::Image,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::Image,winrt::Windows::Foundation::IActivationFactory>
0x1800106c2  jz      short loc_1800106EB
0x1800106c4  lea     r8, ??$factory_cache_entry_v@UImage@Controls@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@3U?$factory_cache_entry@UImage@Controls@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@56@@12@A; factory_cache_entry<winrt::Windows::UI::Xaml::Controls::Image,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Controls::Image,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::Image,winrt::Windows::Foundation::IActivationFactory>
0x1800106cb  lea     rdx, [rbp+80h+var_A8]
0x1800106cf  call    ??R_lambda_52__@?0???0Image@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ@QEBA@AEBUIActivationFactory@Foundation@56@@Z; `winrt::Windows::UI::Xaml::Controls::Image::Image(void)'::`1'::_lambda_52__::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x1800106d4  mov     edi, 3
0x1800106d9  mov     [rsp+180h+var_110], edi
0x1800106dd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800106e1  lock add cs:qword_18003C1B8, rsi
0x1800106e9  jmp     short loc_180010718
0x1800106eb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800106ef  lock add cs:qword_18003C1B8, rsi
0x1800106f7  lea     rax, ?_lambda_invoker_cdecl_@_lambda_52__@?0???0Image@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ@SA@AEBUIActivationFactory@Foundation@67@@Z; `winrt::Windows::UI::Xaml::Controls::Image::Image(void)'::`1'::_lambda_52__::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x1800106fe  mov     [rsp+180h+var_130], rax
0x180010703  lea     r8, [rsp+180h+var_130]
0x180010708  lea     rdx, [rbp+80h+var_A8]
0x18001070c  call    ??$call@P6A?AUImage@Controls@Xaml@UI@Windows@winrt@@AEBUIActivationFactory@Foundation@56@@Z@?$factory_cache_entry@UImage@Controls@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@QEAA?A_P$$QEAP6A?AUImage@Controls@Xaml@UI@Windows@2@AEBUIActivationFactory@Foundation@72@@Z@Z
0x180010711  lea     edi, [rsi+4]
0x180010714  mov     [rsp+180h+var_110], edi
0x180010718  cmp     [r13+30h], r12
0x18001071c  jz      loc_1800109CA
0x180010722  movups  xmm0, xmmword ptr cs:CLSID_WICImagingFactory2.Data1
0x180010729  movdqu  xmmword ptr [rbp+80h+rclsid.Data1], xmm0
0x18001072e  mov     [rsp+180h+var_140], r12
0x180010733  mov     dword ptr [rsp+180h+var_130], r12d
0x180010738  xorps   xmm0, xmm0
0x18001073b  movdqu  xmmword ptr [rsp+180h+var_130+8], xmm0
0x180010741  lea     rax, [rsp+180h+var_140]
0x180010746  mov     [rsp+180h+ppv], rax; int
0x18001074b  lea     r9, ??$guid_v@UIWICImagingFactory@@@impl@winrt@@3Uguid@2@B; riid
0x180010752  xor     edx, edx; pUnkOuter
0x180010754  lea     r8d, [rdx+1]; dwClsContext
0x180010758  lea     rcx, [rbp+80h+rclsid]; rclsid
0x18001075c  call    CoCreateInstance_0
0x180010761  test    eax, eax
0x180010763  js      loc_18001199C
0x180010769  mov     rbx, [rsp+180h+var_140]
0x18001076e  mov     qword ptr [rbp+80h+rclsid.Data1], rbx
0x180010772  mov     [rsp+180h+var_110], 0Fh
0x18001077a  mov     [rsp+180h+var_150], r12
0x18001077f  mov     rax, [rbx]
0x180010782  lea     r8, [rsp+180h+var_150]
0x180010787  mov     rdx, [r13+30h]
0x18001078b  mov     rcx, rbx
0x18001078e  mov     rax, [rax+0B0h]
0x180010795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001079a  mov     rcx, [rbp+88h]; this
0x1800107a1  test    eax, eax
0x1800107a3  js      loc_1800119A9
0x1800107a9  mov     [rbp+80h+var_98], r12
0x1800107ad  mov     [rsp+180h+var_148], r12
0x1800107b2  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat32bppBGRA.Data1
0x1800107b9  movdqu  xmmword ptr [rsp+180h+var_130], xmm0
0x1800107bf  lea     rax, [rbp+80h+var_98]
0x1800107c3  mov     [rsp+180h+var_158], rax
0x1800107c8  lea     r9, [rsp+180h+var_130]
0x1800107cd  mov     rdx, [rsp+180h+var_150]
0x1800107d2  mov     rcx, rbx
0x1800107d5  call    ?GetStreamOfWICBitmapSourceWithOptions@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@AEBU_GUID@@U3@W4EncodingOptions@@PEAPEAUIStream@@@Z; GetStreamOfWICBitmapSourceWithOptions(IWICImagingFactory *,IWICBitmapSource *,_GUID const &,_GUID,EncodingOptions,IStream * *)
0x1800107da  mov     rcx, [rbp+88h]; this
0x1800107e1  test    eax, eax
0x1800107e3  js      loc_1800119BE
0x1800107e9  cmp     [rsp+180h+var_148], r12
0x1800107ee  jz      short loc_1800107FA
0x1800107f0  lea     rcx, [rsp+180h+var_148]
0x1800107f5  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x1800107fa  lea     r9, [rsp+180h+var_148]
0x1800107ff  lea     r8, ??$guid_v@UIRandomAccessStream@Streams@Storage@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Storage::Streams::IRandomAccessStream>
0x180010806  xor     edx, edx
0x180010808  mov     rbx, [rbp+80h+var_98]
0x18001080c  mov     rcx, rbx
0x18001080f  call    cs:__imp_CreateRandomAccessStreamOverStream
0x180010815  mov     rcx, [rbp+88h]; this
0x18001081c  test    eax, eax
0x18001081e  js      loc_1800119D3
0x180010824  lea     rax, qword_18003C1F8
0x18001082b  mov     [rsp+180h+var_130], rax
0x180010830  lock inc cs:qword_18003C1F8
0x180010838  cmp     cs:??$factory_cache_entry_v@UBitmapImage@Imaging@Media@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@3U?$factory_cache_entry@UBitmapImage@Imaging@Media@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@67@@12@A, r12; factory_cache_entry<winrt::Windows::UI::Xaml::Media::Imaging::BitmapImage,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Media::Imaging::BitmapImage,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Media::Imaging::BitmapImage,winrt::Windows::Foundation::IActivationFactory>
0x18001083f  jz      short loc_180010864
0x180010841  lea     r8, ??$factory_cache_entry_v@UBitmapImage@Imaging@Media@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@3U?$factory_cache_entry@UBitmapImage@Imaging@Media@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@67@@12@A; factory_cache_entry<winrt::Windows::UI::Xaml::Media::Imaging::BitmapImage,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Media::Imaging::BitmapImage,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Media::Imaging::BitmapImage,winrt::Windows::Foundation::IActivationFactory>
0x180010848  lea     rdx, [rbp+80h+var_E0]
0x18001084c  call    ??R_lambda_202__@?0???0BitmapImage@Imaging@Media@Xaml@UI@Windows@winrt@@QEAA@XZ@QEBA@AEBUIActivationFactory@Foundation@67@@Z; `winrt::Windows::UI::Xaml::Media::Imaging::BitmapImage::BitmapImage(void)'::`1'::_lambda_202__::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x180010851  mov     edi, 1Fh
0x180010856  mov     [rsp+180h+var_110], edi
0x18001085a  lock add cs:qword_18003C1F8, rsi
0x180010862  jmp     short loc_18001088F
0x180010864  lock add cs:qword_18003C1F8, rsi
0x18001086c  lea     rax, ?_lambda_invoker_cdecl_@_lambda_202__@?0???0BitmapImage@Imaging@Media@Xaml@UI@Windows@winrt@@QEAA@XZ@SA@AEBUIActivationFactory@Foundation@78@@Z; `winrt::Windows::UI::Xaml::Media::Imaging::BitmapImage::BitmapImage(void)'::`1'::_lambda_202__::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x180010873  mov     [rsp+180h+var_130], rax
0x180010878  lea     r8, [rsp+180h+var_130]
0x18001087d  lea     rdx, [rbp+80h+var_E0]
0x180010881  call    ??$call@P6A?AUBitmapImage@Imaging@Media@Xaml@UI@Windows@winrt@@AEBUIActivationFactory@Foundation@67@@Z@?$factory_cache_entry@UBitmapImage@Imaging@Media@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@QEAA?A_P$$QEAP6A?AUBitmapImage@Imaging@Media@Xaml@UI@Windows@2@AEBUIActivationFactory@Foundation@82@@Z@Z
0x180010886  mov     edi, 1Fh
0x18001088b  mov     [rsp+180h+var_110], edi
0x18001088f  mov     rcx, [rbp+80h+var_E0]
0x180010893  mov     [rsp+180h+var_130], r12
0x180010898  test    rcx, rcx
0x18001089b  jnz     short loc_1800108A5
0x18001089d  mov     eax, r12d
0x1800108a0  mov     rcx, r12
0x1800108a3  jmp     short loc_1800108C6
0x1800108a5  mov     rax, [rcx]
0x1800108a8  lea     r8, [rsp+180h+var_130]
0x1800108ad  lea     rdx, ??$guid_v@UIBitmapSource@Imaging@Media@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::Media::Imaging::IBitmapSource>
0x1800108b4  mov     rax, [rax]
0x1800108b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108bc  mov     rcx, [rsp+180h+var_130]
0x1800108c1  mov     [rsp+180h+var_130], rcx
0x1800108c6  mov     dword ptr [rsp+180h+var_108], r12d
0x1800108cb  xorps   xmm0, xmm0
0x1800108ce  movdqu  [rbp+80h+var_108+8], xmm0
0x1800108d3  test    eax, eax
0x1800108d5  js      loc_1800119E8
0x1800108db  mov     dword ptr [rsp+180h+var_108], r12d
0x1800108e0  movdqu  [rbp+80h+var_108+8], xmm0
0x1800108e5  mov     rax, [rcx]
0x1800108e8  mov     rdx, [rsp+180h+var_148]
0x1800108ed  mov     rax, [rax+40h]
0x1800108f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108f6  test    eax, eax
0x1800108f8  js      loc_1800119F5
0x1800108fe  lea     rcx, [rsp+180h+var_130]
0x180010903  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180010908  mov     rcx, [rbp+80h+var_E0]
0x18001090c  test    rcx, rcx
0x18001090f  jnz     short loc_180010919
0x180010911  mov     rdx, r12
0x180010914  mov     r14, r12
0x180010917  jmp     short loc_18001093D
0x180010919  mov     [rsp+180h+var_130], r12
0x18001091e  mov     rax, [rcx]
0x180010921  lea     r8, [rsp+180h+var_130]
0x180010926  lea     rdx, ??$guid_v@UIImageSource@Media@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::Media::IImageSource>
0x18001092d  mov     rax, [rax]
0x180010930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010935  mov     rdx, [rsp+180h+var_130]
0x18001093a  mov     r14, rdx
0x18001093d  mov     [rsp+180h+var_130], rdx
0x180010942  mov     rcx, [rbp+80h+var_A8]
0x180010946  mov     dword ptr [rsp+180h+var_108], r12d
0x18001094b  xorps   xmm0, xmm0
0x18001094e  movdqu  [rbp+80h+var_108+8], xmm0
0x180010953  mov     rax, [rcx]
0x180010956  mov     rax, [rax+38h]
0x18001095a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001095f  test    eax, eax
0x180010961  js      loc_180011A02
0x180010967  test    r14, r14
0x18001096a  jz      short loc_180010977
0x18001096c  lea     rcx, [rsp+180h+var_130]
0x180010971  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180010976  nop
0x180010977  cmp     [rbp+80h+var_E0], r12
0x18001097b  jz      short loc_180010987
0x18001097d  lea     rcx, [rbp+80h+var_E0]
0x180010981  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180010986  nop
0x180010987  cmp     [rsp+180h+var_148], r12
0x18001098c  jz      short loc_180010999
0x18001098e  lea     rcx, [rsp+180h+var_148]
0x180010993  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180010998  nop
0x180010999  test    rbx, rbx
0x18001099c  jz      short loc_1800109A8
0x18001099e  lea     rcx, [rbp+80h+var_98]
0x1800109a2  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x1800109a7  nop
0x1800109a8  cmp     [rsp+180h+var_150], r12
0x1800109ad  jz      short loc_1800109BA
0x1800109af  lea     rcx, [rsp+180h+var_150]
0x1800109b4  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x1800109b9  nop
0x1800109ba  cmp     [rsp+180h+var_140], r12
0x1800109bf  jz      short loc_1800109CA
0x1800109c1  lea     rcx, [rbp+80h+rclsid]
0x1800109c5  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x1800109ca  mov     rcx, [rbp+80h+var_A8]
0x1800109ce  lea     r14, ??$guid_v@UIFrameworkElement@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::IFrameworkElement>
0x1800109d5  mov     [rsp+180h+var_130], r12
0x1800109da  test    rcx, rcx
0x1800109dd  jnz     short loc_1800109E7
  ... truncated ...
```
