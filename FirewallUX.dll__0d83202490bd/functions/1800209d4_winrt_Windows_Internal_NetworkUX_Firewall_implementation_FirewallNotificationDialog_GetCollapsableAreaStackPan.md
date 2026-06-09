# winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::_GetCollapsableAreaStackPanel(void)

- ea: `0x1800209d4`
- end: `0x180021d5f`
- name: `?_GetCollapsableAreaStackPanel@FirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@AEAA?AUStackPanel@Controls@Xaml@UI@67@XZ`
- size: `5003`
- prototype: `winrt::Windows::UI::Xaml::Controls::StackPanel *__fastcall(__int64, winrt::Windows::UI::Xaml::Controls::StackPanel *)`
- caller_count: `1`
- callee_count: `45`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e0b0`

## callees

- `0x1800019dc`
- `0x1800021c0`
- `0x1800021e4`
- `0x180002d55`
- `0x180002d91`
- `0x180004c90`
- `0x1800056ec`
- `0x180006b20`
- `0x180007940`
- `0x180008820`
- `0x18000b5d0`
- `0x18000c4f0`
- `0x18000ea58`
- `0x18000ed88`
- `0x18000ee78`
- `0x18000ff68`
- `0x18000ffac`
- `0x180010464`
- `0x180011b80`
- `0x180012b2c`
- `0x180012df8`
- `0x180013488`
- `0x180013818`
- `0x180013860`
- `0x1800138a8`
- `0x18001abf0`
- `0x18001aea4`
- `0x18001afd8`
- `0x18001b7e4`
- `0x18001c758`
- `0x18001c978`
- `0x18001db2c`
- `0x18001dcfc`
- `0x18001de64`
- `0x18001e740`
- `0x18001ef60`
- `0x18001f00c`
- `0x18001f0cc`
- `0x18001f1cc`
- `0x18002028c`
- `0x1800208c8`
- `0x1800209d4`
- `0x180023264`
- `0x180029734`
- `0x18002d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180020ba7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180020d82`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180020e69`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800212ad`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800213ff`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800218a4`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002198e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180020ba7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180020d82`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180020e69`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800212ad`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800213ff`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800218a4`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002198e`

## string_xrefs

- `0x180020a1a`: `ConfigureCheckboxes`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
winrt::Windows::UI::Xaml::Controls::StackPanel *__fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::_GetCollapsableAreaStackPanel(
        __int64 a1,
        winrt::Windows::UI::Xaml::Controls::StackPanel *a2)
{
  winrt::Windows::UI::Xaml::Controls::StackPanel *v2; // r15
  int v4; // r13d
  _QWORD *v5; // rbx
  _QWORD *v6; // rsi
  void *v7; // rbx
  int v8; // eax
  HANDLE ProcessHeap; // rax
  __int64 v10; // rbx
  void **weak; // rax
  void *v12; // r12
  void **v13; // rax
  void *v14; // r15
  void *v15; // rbx
  int v16; // eax
  HANDLE v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  char v20; // bl
  char v21; // si
  __int64 IsChecked; // rax
  _QWORD *v23; // rcx
  LPVOID v24; // rax
  _QWORD *v25; // rcx
  LPVOID v26; // rax
  __int64 v27; // rbx
  _QWORD *v28; // rdx
  void (__fastcall ***v29)(_QWORD, _QWORD, _QWORD); // rcx
  LPVOID v30; // rcx
  _QWORD *v31; // rdx
  LPVOID v32; // rax
  const struct _tlgProvider_t *v33; // rcx
  void **v34; // rax
  void *v35; // r12
  void **v36; // rax
  void *v37; // r15
  void *v38; // rbx
  int v39; // eax
  HANDLE v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rcx
  char v43; // bl
  char v44; // si
  __int64 v45; // rax
  _QWORD *v46; // rcx
  LPVOID v47; // rax
  int v48; // r13d
  _QWORD *v49; // rcx
  LPVOID v50; // rax
  __int64 v51; // rbx
  _QWORD *v52; // rdx
  void (__fastcall ***v53)(_QWORD, _QWORD, _QWORD); // rcx
  LPVOID v54; // rcx
  _QWORD *v55; // rdx
  LPVOID v56; // rax
  const struct _tlgProvider_t *v57; // rcx
  void **v58; // rax
  void *v59; // r12
  void **v60; // rax
  void *v61; // r15
  void *v62; // rbx
  int v63; // eax
  HANDLE v64; // rax
  __int64 v65; // rdx
  __int64 v66; // rcx
  char v67; // bl
  char v68; // si
  __int64 v69; // rax
  _QWORD *v70; // rcx
  LPVOID v71; // rax
  int v72; // r13d
  _QWORD *v73; // rcx
  LPVOID v74; // rax
  __int64 v75; // rbx
  _QWORD *v76; // rdx
  void (__fastcall ***v77)(_QWORD, _QWORD, _QWORD); // rcx
  LPVOID v78; // rcx
  _QWORD *v79; // rdx
  LPVOID v80; // rax
  __int64 v81; // rbx
  __int64 ExternalLinkControl; // rax
  LPVOID v84; // [rsp+30h] [rbp-D0h] BYREF
  char v85[8]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v86; // [rsp+40h] [rbp-C0h] BYREF
  void (__fastcall ***v87)(_QWORD, _QWORD, _QWORD); // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v89; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v90; // [rsp+60h] [rbp-A0h] BYREF
  int v91; // [rsp+68h] [rbp-98h]
  LPVOID v92; // [rsp+70h] [rbp-90h] BYREF
  void (__fastcall ***v93)(_QWORD, void *, _QWORD **); // [rsp+78h] [rbp-88h] BYREF
  winrt::Windows::UI::Xaml::Controls::StackPanel *v94; // [rsp+80h] [rbp-80h] BYREF
  void *v95; // [rsp+88h] [rbp-78h]
  winrt::Windows::UI::Xaml::Controls::StackPanel *v96; // [rsp+90h] [rbp-70h]
  _QWORD v97[42]; // [rsp+A0h] [rbp-60h] BYREF
  __m128i v98; // [rsp+1F0h] [rbp+F0h] BYREF
  __m128i si128; // [rsp+200h] [rbp+100h]

  v2 = a2;
  v94 = a2;
  v96 = a2;
  wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v97,
    "ConfigureCheckboxes");
  v97[0] = &FirewallUxTelemetry::ConfigureCheckboxes::`vftable';
  FirewallUxTelemetry::ConfigureCheckboxes::StartActivity((FirewallUxTelemetry::ConfigureCheckboxes *)v97);
  winrt::Windows::UI::Xaml::Controls::StackPanel::StackPanel(v2);
  v4 = 1;
  v91 = 1;
  v98 = 0;
  si128 = 0;
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::StackPanel>::Margin(
    v2,
    &v98);
  v5 = *(_QWORD **)(a1 + 528);
  v6 = *(_QWORD **)(a1 + 536);
  if ( v5 != v6 )
  {
    do
    {
      if ( *v5 )
        winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v5);
      ++v5;
    }
    while ( v5 != v6 );
    *(_QWORD *)(a1 + 536) = *(_QWORD *)(a1 + 528);
  }
  winrt::Windows::UI::Xaml::Controls::TextBlock::TextBlock((winrt::Windows::UI::Xaml::Controls::TextBlock *)&v93);
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::FontSize(&v93);
  LODWORD(v84) = 0;
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::HorizontalAlignment(
    &v93,
    &v84);
  LODWORD(v84) = 0;
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::VerticalAlignment(
    &v93,
    &v84);
  LODWORD(v84) = 2;
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::TextWrapping(
    &v93,
    &v84);
  v98.m128i_i64[0] = *(_QWORD *)GetResourceString(&lpMem, 250);
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::Text(
    &v93,
    &v98);
  v7 = lpMem;
  if ( lpMem )
  {
    v8 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v8 )
    {
      if ( v8 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v7);
    }
  }
  v98 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::StackPanel>::Margin(
    &v93,
    &v98);
  v10 = winrt::impl::consume_Windows_UI_Xaml_Controls_IPanel<winrt::Windows::UI::Xaml::Controls::Grid>::Children(
          v2,
          &v87);
  if ( v93 )
  {
    v86 = 0;
    (**v93)(v93, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IUIElement>, &v86);
    v89 = v86;
  }
  else
  {
    v89 = 0;
  }
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Xaml::Controls::ColumnDefinition>,winrt::Windows::UI::Xaml::Controls::ColumnDefinition>::Append(
    v10,
    &v89);
  if ( v89 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v89);
  if ( v87 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v87);
  if ( (*(_BYTE *)(a1 + 504) & 4) != 0 )
  {
    weak = (void **)winrt::implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::IFirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase>::get_weak(
                      a1,
                      &v86);
    v12 = *weak;
    *weak = 0;
    v95 = v12;
    if ( v86 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v86);
    v13 = (void **)winrt::implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::IFirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase>::get_weak(
                     a1,
                     &v84);
    v14 = *v13;
    *v13 = 0;
    v92 = v14;
    if ( v84 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v84);
    winrt::Windows::UI::Xaml::Controls::TextBlock::TextBlock((winrt::Windows::UI::Xaml::Controls::TextBlock *)&v89);
    winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::FontSize(&v89);
    LODWORD(v84) = 0;
    winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::HorizontalAlignment(
      &v89,
      &v84);
    LODWORD(v84) = 0;
    winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::VerticalAlignment(
      &v89,
      &v84);
    LODWORD(v84) = 2;
    winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::TextWrapping(
      &v89,
      &v84);
    v98.m128i_i64[0] = *(_QWORD *)GetResourceString(&lpMem, 254);
    winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::Text(
      &v89,
      &v98);
    v15 = lpMem;
    if ( lpMem )
    {
      v16 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v16 )
      {
        if ( v16 < 0 )
          abort();
      }
      else
      {
        v17 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v17, 0, v15);
      }
    }
    winrt::Windows::UI::Xaml::Controls::CheckBox::CheckBox((winrt::Windows::UI::Xaml::Controls::CheckBox *)&v87);
    v85[0] = (*(_DWORD *)(a1 + 600) & 4) != 0;
    winrt::Windows::Foundation::IReference<bool>::IReference<bool>(&v84, v85);
    winrt::impl::consume_Windows_UI_Xaml_Controls_Primitives_IToggleButton<winrt::Windows::UI::Xaml::Controls::CheckBox>::IsChecked(
      &v87,
      &v84);
    if ( v84 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v84);
    LOBYTE(v18) = 1;
    v20 = 0;
    if ( *(_BYTE *)(a1 + 526) )
    {
      if ( (*(_BYTE *)(a1 + 516) & 4) != 0 )
      {
LABEL_30:
        LOBYTE(v19) = 1;
LABEL_35:
        v20 = 1;
        LOBYTE(v18) = 0;
LABEL_38:
        if ( (*(_BYTE *)(a1 + 512) & 4) != 0 )
        {
          if ( v20 )
            MicrosoftTelemetryAssertTriggeredNoArgs(v19, v18);
          LOBYTE(v19) = 0;
          v20 = 1;
          LOBYTE(v18) = 0;
        }
        v21 = *(_BYTE *)(a1 + 525) != 0 ? v18 : 0;
        LOBYTE(v84) = v21;
        BYTE1(v84) = v19;
        BYTE2(v84) = v20;
        LOBYTE(v18) = v21;
        winrt::impl::consume_Windows_UI_Xaml_Controls_IControl<winrt::Windows::UI::Xaml::Controls::CheckBox>::IsEnabled(
          &v87,
          v18);
        if ( v20 )
        {
          winrt::Windows::Foundation::IReference<bool>::IReference<bool>(&v86, (char *)&v84 + 1);
          winrt::impl::consume_Windows_UI_Xaml_Controls_Primitives_IToggleButton<winrt::Windows::UI::Xaml::Controls::CheckBox>::IsChecked(
            &v87,
            &v86);
          if ( v86 )
            winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v86);
        }
        IsChecked = winrt::impl::consume_Windows_UI_Xaml_Controls_Primitives_IToggleButton<winrt::Windows::UI::Xaml::Controls::CheckBox>::IsChecked(
                      &v87,
                      &v86);
        *(_BYTE *)(a1 + 592) = winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IReference<bool>>::GetBoolean(IsChecked);
        if ( v86 )
          winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v86);
        FirewallUxTelemetry::ConfigureCheckboxes::PublicNetworks<bool &,bool &>((char *)&v84, (char *)(a1 + 592));
        if ( aPubliccheckbox[14] )
          abort();
        v98.m128i_i64[1] = 0xE00000001LL;
        si128.m128i_i64[1] = (__int64)L"PublicCheckBox";
        v98.m128i_i64[0] = (__int64)&v98.m128i_i64[1];
        winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::CheckBox>::Name(
          &v87,
          &v98);
        winrt::impl::consume_Windows_UI_Xaml_Controls_IContentControl<winrt::Windows::UI::Xaml::Controls::CheckBox>::Content(
          &v87,
          &v89);
        v98 = _mm_load_si128((const __m128i *)&_xmm);
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::StackPanel>::Margin(
          &v87,
          &v98);
        v95 = 0;
        v84 = v12;
        v90 = &v84;
        v23 = operator new(0x18u);
        v90 = v23;
        *((_DWORD *)v23 + 2) = 1;
        v24 = v84;
        v84 = 0;
        v23[2] = v24;
        _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
        *v23 = off_18002E9C0;
        v86 = v23;
        v91 = 3;
        if ( v84 )
          winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v84);
        winrt::impl::consume_Windows_UI_Xaml_Controls_Primitives_IToggleButton<winrt::Windows::UI::Xaml::Controls::CheckBox>::Checked(
          &v87,
          &lpMem,
          &v86);
        winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v86);
        v92 = 0;
        v84 = v14;
        v90 = &v84;
        v25 = operator new(0x18u);
        v90 = v25;
        *((_DWORD *)v25 + 2) = 1;
        v26 = v84;
        v84 = 0;
        v25[2] = v26;
        _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
        *v25 = off_18002E9A0;
        v86 = v25;
        v4 = 7;
        v91 = 7;
        if ( v84 )
          winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v84);
        winrt::impl::consume_Windows_UI_Xaml_Controls_Primitives_IToggleButton<winrt::Windows::UI::Xaml::Controls::CheckBox>::Unchecked(
          &v87,
          &lpMem,
          &v86);
        winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v86);
        v2 = v94;
        v27 = winrt::impl::consume_Windows_UI_Xaml_Controls_IPanel<winrt::Windows::UI::Xaml::Controls::Grid>::Children(
                v94,
                &lpMem);
        if ( v87 )
        {
          v86 = 0;
          (**v87)(v87, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IUIElement>, &v86);
          v84 = v86;
        }
        else
        {
          v84 = 0;
        }
        winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Xaml::Controls::ColumnDefinition>,winrt::Windows::UI::Xaml::Controls::ColumnDefinition>::Append(
          v27,
          &v84);
        if ( v84 )
          winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v84);
        if ( lpMem )
          winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&lpMem);
        v28 = *(_QWORD **)(a1 + 536);
        if ( v28 == *(_QWORD **)(a1 + 544) )
        {
          std::vector<winrt::Windows::UI::Xaml::Controls::CheckBox>::_Emplace_reallocate<winrt::Windows::UI::Xaml::Controls::CheckBox const &>(
            a1 + 528,
            v28,
            &v87);
        }
        else
        {
          v29 = v87;
          *v28 = v87;
          if ( v29 )
            ((void (__fastcall *)(void (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v29)[1])(v29);
          *(_QWORD *)(a1 + 536) += 8LL;
        }
        if ( v21 )
        {
          if ( v87 )
          {
            lpMem = 0;
            (**v87)(v87, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IControl>, &lpMem);
            v30 = lpMem;
            v84 = lpMem;
          }
          else
          {
            v84 = 0;
            v30 = 0;
          }
          v31 = *(_QWORD **)(a1 + 480);
          if ( v31 == *(_QWORD **)(a1 + 488) )
          {
            std::vector<winrt::Windows::UI::Xaml::Controls::Control>::_Emplace_reallocate<winrt::Windows::UI::Xaml::Controls::Control>(
              a1 + 472,
              v31,
              &v84);
            v32 = v84;
          }
          else
          {
            v32 = 0;
            v84 = 0;
            *v31 = v30;
            *(_QWORD *)(a1 + 480) += 8LL;
          }
          if ( v32 )
            winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v84);
        }
        if ( v87 )
          winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v87);
        if ( v89 )
          winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v89);
        goto LABEL_81;
      }
      if ( (*(_BYTE *)(a1 + 508) & 4) != 0 )
      {
        LOBYTE(v19) = 0;
        goto LABEL_35;
      }
    }
    else if ( (*(_BYTE *)(a1 + 508) & 4) != 0 )
    {
      goto LABEL_30;
    }
    LOBYTE(v19) = v85[0];
    goto LABEL_38;
  }
  v33 = FirewallUxTraceLoggingProvider::Provider();
  if ( *(_DWORD *)v33 > 5u )
    tlgWriteTransfer_EventWriteTransfer(v33, &unk_180033905, 0, 0, 2, &v98);
LABEL_81:
  if ( (*(_BYTE *)(a1 + 504) & 2) != 0 )
  {
    v34 = (void **)winrt::implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::IFirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase>::get_weak(
                     a1,
                     &lpMem);
    v35 = *v34;
    *v34 = 0;
    v95 = v35;
    if ( lpMem )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&lpMem);
    v36 = (void **)winrt::implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::IFirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase>::get_weak(
                     a1,
                     &v86);
    v37 = *v36;
    *v36 = 0;
    v90 = v37;
    if ( v86 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v86);
    winrt::Windows::UI::Xaml::Controls::TextBlock::TextBlock((winrt::Windows::UI::Xaml::Controls::TextBlock *)&v89);
    winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::FontSize(&v89);
    LODWORD(v84) = 0;
    winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::HorizontalAlignment(
      &v89,
      &v84);
    LODWORD(v84) = 0;
    winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::VerticalAlignment(
      &v89,
      &v84);
    LODWORD(v84) = 2;
    winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::TextWrapping(
      &v89,
      &v84);
    v98.m128i_i64[0] = *(_QWORD *)GetResourceString(&v92, 252);
    winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::Text(
      &v89,
      &v98);
    v38 = v92;
    if ( v92 )
    {
      v39 = _InterlockedDecrement((volatile signed __int32 *)v92 + 6);
      if ( v39 )
      {
        if ( v39 < 0 )
          abort();
      }
      else
      {
        v40 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v40, 0, v38);
      }
    }
    winrt::Windows::UI::Xaml::Controls::CheckBox::CheckBox((winrt::Windows::UI::Xaml::Controls::CheckBox *)&v87);
    v85[0] = (*(_DWORD *)(a1 + 600) & 2) != 0;
    winrt::Windows::Foundation::IReference<bool>::IReference<bool>(&v86, v85);
    winrt::impl::consume_Windows_UI_Xaml_Controls_Primitives_IToggleButton<winrt::Windows::UI::Xaml::Controls::CheckBox>::IsChecked(
      &v87,
      &v86);
    if ( v86 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v86);
    LOBYTE(v41) = 1;
    v43 = 0;
    if ( *(_BYTE *)(a1 + 526) )
    {
      if ( (*(_BYTE *)(a1 + 516) & 2) != 0 )
      {
LABEL_95:
        LOBYTE(v42) = 1;
LABEL_98:
        v43 = 1;
        LOBYTE(v41) = 0;
LABEL_101:
        if ( (*(_BYTE *)(a1 + 512) & 2) != 0 )
        {
          if ( v43 )
            MicrosoftTelemetryAssertTriggeredNoArgs(v42, v41);
          LOBYTE(v42) = 0;
          v43 = 1;
          LOBYTE(v41) = 0;
        }
        v44 = *(_BYTE *)(a1 + 525) != 0 ? v41 : 0;
        LOBYTE(v84) = v44;
        BYTE1(v84) = v42;
        BYTE2(v84) = v43;
        LOBYTE(v41) = v44;
        winrt::impl::consume_Windows_UI_Xaml_Controls_IControl<winrt::Windows::UI::Xaml::Controls::CheckBox>::IsEnabled(
          &v87,
          v41);
        if ( v43 )
        {
          winrt::Windows::Foundation::IReference<bool>::IReference<bool>(&v86, (char *)&v84 + 1);
          winrt::impl::consume_Windows_UI_Xaml_Controls_Primitives_IToggleButton<winrt::Windows::UI::Xaml::Controls::CheckBox>::IsChecked(
            &v87,
            &v86);
          if ( v86 )
            winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v86);
        }
        v45 = winrt::impl::consume_Windows_UI_Xaml_Controls_Primitives_IToggleButton<winrt::Windows::UI::Xaml::Controls::CheckBox>::IsChecked(
                &v87,
                &lpMem);
        *(_BYTE *)(a1 + 593) = winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IReference<bool>>::GetBoolean(v45);
        if ( lpMem )
          winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&lpMem);
        FirewallUxTelemetry::ConfigureCheckboxes::PrivateNetworks<bool &,bool &>((char *)&v84, (char *)(a1 + 593));
        if ( aPrivatecheckbo[15] )
          abort();
        v98.m128i_i64[1] = 0xF00000001LL;
        si128.m128i_i64[1] = (__int64)L"PrivateCheckBox";
        v98.m128i_i64[0] = (__int64)&v98.m128i_i64[1];
        winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::CheckBox>::Name(
          &v87,
          &v98);
        winrt::impl::consume_Windows_UI_Xaml_Controls_IContentControl<winrt::Windows::UI::Xaml::Controls::CheckBox>::Content(
          &v87,
          &v89);
        v98 = _mm_load_si128((const __m128i *)&_xmm);
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::StackPanel>::Margin(
          &v87,
          &v98);
        v95 = 0;
        v84 = v35;
        v92 = &v84;
        v46 = operator new(0x18u);
        v92 = v46;
        *((_DWORD *)v46 + 2) = 1;
        v47 = v84;
        v84 = 0;
        v46[2] = v47;
        _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
        *v46 = off_18002E980;
        lpMem = v46;
        v48 = v4 | 8;
        v91 = v48;
        if ( v84 )
          winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v84);
        winrt::impl::consume_Windows_UI_Xaml_Controls_Primitives_IToggleButton<winrt::Windows::UI::Xaml::Controls::CheckBox>::Checked(
          &v87,
          &v86,
          &lpMem);
        winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&lpMem);
        v90 = 0;
        v84 = v37;
        v92 = &v84;
        v49 = operator new(0x18u);
        v92 = v49;
        *((_DWORD *)v49 + 2) = 1;
        v50 = v84;
        v84 = 0;
        v49[2] = v50;
        _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
        *v49 = off_18002E960;
        lpMem = v49;
        v4 = v48 | 0x10;
        v91 = v4;
        if ( v84 )
          winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v84);
        winrt::impl::consume_Windows_UI_Xaml_Controls_Primitives_IToggleButton<winrt::Windows::UI::Xaml::Controls::CheckBox>::Unchecked(
          &v87,
          &v86,
          &lpMem);
        winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&lpMem);
        v2 = v94;
        v51 = winrt::impl::consume_Windows_UI_Xaml_Controls_IPanel<winrt::Windows::UI::Xaml::Controls::Grid>::Children(
                v94,
                &v86);
        if ( v87 )
        {
          lpMem = 0;
          (**v87)(v87, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IUIElement>, &lpMem);
          v84 = lpMem;
        }
        else
        {
          v84 = 0;
        }
        winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Xaml::Controls::ColumnDefinition>,winrt::Windows::UI::Xaml::Controls::ColumnDefinition>::Append(
          v51,
          &v84);
        if ( v84 )
          winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v84);
        if ( v86 )
          winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v86);
        v52 = *(_QWORD **)(a1 + 536);
        if ( v52 == *(_QWORD **)(a1 + 544) )
        {
          std::vector<winrt::Windows::UI::Xaml::Controls::CheckBox>::_Emplace_reallocate<winrt::Windows::UI::Xaml::Controls::CheckBox const &>(
            a1 + 528,
            v52,
            &v87);
        }
        else
        {
          v53 = v87;
          *v52 = v87;
          if ( v53 )
            ((void (__fastcall *)(void (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v53)[1])(v53);
          *(_QWORD *)(a1 + 536) += 8LL;
        }
        if ( v44 )
        {
          if ( v87 )
          {
            lpMem = 0;
            (**v87)(v87, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IControl>, &lpMem);
            v54 = lpMem;
            v84 = lpMem;
          }
          else
          {
            v84 = 0;
            v54 = 0;
          }
          v55 = *(_QWORD **)(a1 + 480);
          if ( v55 == *(_QWORD **)(a1 + 488) )
          {
            std::vector<winrt::Windows::UI::Xaml::Controls::Control>::_Emplace_reallocate<winrt::Windows::UI::Xaml::Controls::Control>(
              a1 + 472,
              v55,
              &v84);
            v56 = v84;
          }
          else
          {
            v56 = 0;
            v84 = 0;
            *v55 = v54;
            *(_QWORD *)(a1 + 480) += 8LL;
          }
          if ( v56 )
            winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v84);
        }
        if ( v87 )
          winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v87);
        if ( v89 )
          winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v89);
        goto LABEL_144;
      }
      if ( (*(_BYTE *)(a1 + 508) & 2) != 0 )
      {
        LOBYTE(v42) = 0;
        goto LABEL_98;
      }
    }
    else if ( (*(_BYTE *)(a1 + 508) & 2) != 0 )
    {
      goto LABEL_95;
    }
    LOBYTE(v42) = v85[0];
    goto LABEL_101;
  }
  v57 = FirewallUxTraceLoggingProvider::Provider();
  if ( *(_DWORD *)v57 > 5u )
    tlgWriteTransfer_EventWriteTransfer(v57, &unk_1800338E0, 0, 0, 2, &v98);
LABEL_144:
  if ( (*(_BYTE *)(a1 + 504) & 1) == 0 )
  {
    FirewallUxTelemetry::ConfigureCheckboxes::DomainNetworksHidden();
    goto LABEL_206;
  }
  v58 = (void **)winrt::implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::IFirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase>::get_weak(
                   a1,
                   &lpMem);
  v59 = *v58;
  *v58 = 0;
  v92 = v59;
  if ( lpMem )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&lpMem);
  v60 = (void **)winrt::implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::IFirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase>::get_weak(
                   a1,
                   &v86);
  v61 = *v60;
  *v60 = 0;
  v95 = v61;
  if ( v86 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v86);
  winrt::Windows::UI::Xaml::Controls::TextBlock::TextBlock((winrt::Windows::UI::Xaml::Controls::TextBlock *)&v89);
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::FontSize(&v89);
  LODWORD(v84) = 0;
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::HorizontalAlignment(
    &v89,
    &v84);
  LODWORD(v84) = 0;
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::VerticalAlignment(
    &v89,
    &v84);
  LODWORD(v84) = 2;
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::TextWrapping(
    &v89,
    &v84);
  v98.m128i_i64[0] = *(_QWORD *)GetResourceString(&v90, 251);
  winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::Text(
    &v89,
    &v98);
  v62 = v90;
  if ( v90 )
  {
    v63 = _InterlockedDecrement((volatile signed __int32 *)v90 + 6);
    if ( v63 )
    {
      if ( v63 < 0 )
        abort();
    }
    else
    {
      v64 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v64, 0, v62);
    }
  }
  winrt::Windows::UI::Xaml::Controls::CheckBox::CheckBox((winrt::Windows::UI::Xaml::Controls::CheckBox *)&v87);
  v85[0] = *(_BYTE *)(a1 + 600) & 1;
  winrt::Windows::Foundation::IReference<bool>::IReference<bool>(&v86, v85);
  winrt::impl::consume_Windows_UI_Xaml_Controls_Primitives_IToggleButton<winrt::Windows::UI::Xaml::Controls::CheckBox>::IsChecked(
    &v87,
    &v86);
  if ( v86 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v86);
  LOBYTE(v65) = 1;
  v67 = 0;
  if ( !*(_BYTE *)(a1 + 526) )
  {
    if ( (*(_BYTE *)(a1 + 508) & 4) != 0 )
      goto LABEL_156;
LABEL_163:
    LOBYTE(v66) = v85[0];
    goto LABEL_164;
  }
  if ( (*(_BYTE *)(a1 + 516) & 4) == 0 )
  {
    if ( (*(_BYTE *)(a1 + 508) & 4) != 0 )
    {
      LOBYTE(v66) = 0;
      goto LABEL_161;
    }
    goto LABEL_163;
  }
LABEL_156:
  LOBYTE(v66) = 1;
LABEL_161:
  v67 = 1;
  LOBYTE(v65) = 0;
LABEL_164:
  if ( (*(_BYTE *)(a1 + 512) & 4) != 0 )
  {
    if ( v67 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v66, v65);
    LOBYTE(v66) = 0;
    v67 = 1;
    LOBYTE(v65) = 0;
  }
  v68 = *(_BYTE *)(a1 + 525) != 0 ? v65 : 0;
  LOBYTE(v84) = v68;
  BYTE1(v84) = v66;
  BYTE2(v84) = v67;
  LOBYTE(v65) = v68;
  winrt::impl::consume_Windows_UI_Xaml_Controls_IControl<winrt::Windows::UI::Xaml::Controls::CheckBox>::IsEnabled(
    &v87,
    v65);
  if ( v67 )
  {
    winrt::Windows::Foundation::IReference<bool>::IReference<bool>(&v86, (char *)&v84 + 1);
    winrt::impl::consume_Windows_UI_Xaml_Controls_Primitives_IToggleButton<winrt::Windows::UI::Xaml::Controls::CheckBox>::IsChecked(
      &v87,
      &v86);
    if ( v86 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v86);
  }
  v69 = winrt::impl::consume_Windows_UI_Xaml_Controls_Primitives_IToggleButton<winrt::Windows::UI::Xaml::Controls::CheckBox>::IsChecked(
          &v87,
          &lpMem);
  *(_BYTE *)(a1 + 594) = winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IReference<bool>>::GetBoolean(v69);
  if ( lpMem )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&lpMem);
  FirewallUxTelemetry::ConfigureCheckboxes::DomainNetworks<bool &,bool &>((char *)&v84, (char *)(a1 + 594));
  if ( aDomaincheckbox[14] )
    abort();
  v98.m128i_i64[1] = 0xE00000001LL;
  si128.m128i_i64[1] = (__int64)L"DomainCheckBox";
  v98.m128i_i64[0] = (__int64)&v98.m128i_i64[1];
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::CheckBox>::Name(&v87, &v98);
  winrt::impl::consume_Windows_UI_Xaml_Controls_IContentControl<winrt::Windows::UI::Xaml::Controls::CheckBox>::Content(
    &v87,
    &v89);
  v98 = _mm_load_si128((const __m128i *)&_xmm);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::StackPanel>::Margin(
    &v87,
    &v98);
  v92 = 0;
  v84 = v59;
  v90 = &v84;
  v70 = operator new(0x18u);
  v90 = v70;
  *((_DWORD *)v70 + 2) = 1;
  v71 = v84;
  v84 = 0;
  v70[2] = v71;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *v70 = off_18002E940;
  lpMem = v70;
  v72 = v4 | 0x20;
  v91 = v72;
  if ( v84 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v84);
  winrt::impl::consume_Windows_UI_Xaml_Controls_Primitives_IToggleButton<winrt::Windows::UI::Xaml::Controls::CheckBox>::Checked(
    &v87,
    &v86,
    &lpMem);
  winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&lpMem);
  v95 = 0;
  v84 = v61;
  v90 = &v84;
  v73 = operator new(0x18u);
  v90 = v73;
  *((_DWORD *)v73 + 2) = 1;
  v74 = v84;
  v84 = 0;
  v73[2] = v74;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *v73 = off_18002E920;
  lpMem = v73;
  v91 = v72 | 0x40;
  if ( v84 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v84);
  winrt::impl::consume_Windows_UI_Xaml_Controls_Primitives_IToggleButton<winrt::Windows::UI::Xaml::Controls::CheckBox>::Unchecked(
    &v87,
    &v86,
    &lpMem);
  winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&lpMem);
  v2 = v94;
  v75 = winrt::impl::consume_Windows_UI_Xaml_Controls_IPanel<winrt::Windows::UI::Xaml::Controls::Grid>::Children(
          v94,
          &v86);
  if ( v87 )
  {
    lpMem = 0;
    (**v87)(v87, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::IUIElement>, &lpMem);
    v84 = lpMem;
  }
  else
  {
    v84 = 0;
  }
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Xaml::Controls::ColumnDefinition>,winrt::Windows::UI::Xaml::Controls::ColumnDefinition>::Append(
    v75,
    &v84);
  if ( v84 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v84);
  if ( v86 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v86);
  v76 = *(_QWORD **)(a1 + 536);
  if ( v76 == *(_QWORD **)(a1 + 544) )
  {
    std::vector<winrt::Windows::UI::Xaml::Controls::CheckBox>::_Emplace_reallocate<winrt::Windows::UI::Xaml::Controls::CheckBox const &>(
      a1 + 528,
      v76,
      &v87);
  }
  else
  {
    v77 = v87;
    *v76 = v87;
    if ( v77 )
      ((void (__fastcall *)(void (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v77)[1])(v77);
    *(_QWORD *)(a1 + 536) += 8LL;
  }
  if ( v68 )
  {
    if ( v87 )
    {
      lpMem = 0;
      (**v87)(v87, &winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IControl>, &lpMem);
      v78 = lpMem;
      v84 = lpMem;
    }
    else
    {
      v84 = 0;
      v78 = 0;
    }
    v79 = *(_QWORD **)(a1 + 480);
    if ( v79 == *(_QWORD **)(a1 + 488) )
    {
      std::vector<winrt::Windows::UI::Xaml::Controls::Control>::_Emplace_reallocate<winrt::Windows::UI::Xaml::Controls::Control>(
        a1 + 472,
        v79,
        &v84);
      v80 = v84;
    }
    else
    {
      v80 = 0;
      v84 = 0;
      *v79 = v78;
      *(_QWORD *)(a1 + 480) += 8LL;
    }
    if ( v80 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v84);
  }
  if ( v87 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v87);
  if ( v89 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v89);
LABEL_206:
  wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v97, 0);
  v81 = winrt::impl::consume_Windows_UI_Xaml_Controls_IPanel<winrt::Windows::UI::Xaml::Controls::Grid>::Children(
          v2,
          &v86);
  ExternalLinkControl = winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::GetExternalLinkControl(
                          a1,
                          &lpMem);
  winrt::impl::base_one<winrt::Windows::UI::Xaml::Controls::TextBlock,winrt::Windows::UI::Xaml::UIElement>::operator winrt::Windows::UI::Xaml::UIElement(
    ExternalLinkControl,
    &v94);
  winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Xaml::Controls::ColumnDefinition>,winrt::Windows::UI::Xaml::Controls::ColumnDefinition>::Append(
    v81,
    &v94);
  if ( v94 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v94);
  if ( lpMem )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&lpMem);
  if ( v86 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v86);
  if ( v93 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v93);
  v97[0] = &FirewallUxTelemetry::ConfigureCheckboxes::`vftable';
  wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v97);
  wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v97);
  return v2;
}

```

## disassembly

```asm
0x1800209d4  mov     [rsp-8+arg_10], rbx
0x1800209d9  push    rbp
0x1800209da  push    rsi
0x1800209db  push    rdi
0x1800209dc  push    r12
0x1800209de  push    r13
0x1800209e0  push    r14
0x1800209e2  push    r15
0x1800209e4  lea     rbp, [rsp-120h]
0x1800209ec  sub     rsp, 220h
0x1800209f3  mov     rax, cs:__security_cookie
0x1800209fa  xor     rax, rsp
0x1800209fd  mov     [rbp+150h+var_40], rax
0x180020a04  mov     r15, rdx
0x180020a07  mov     [rbp+150h+var_1D0], rdx
0x180020a0b  mov     rdi, rcx
0x180020a0e  mov     [rbp+150h+var_1C0], rdx
0x180020a12  xor     r12d, r12d
0x180020a15  mov     [rsp+250h+var_1E8], r12d
0x180020a1a  lea     rdx, aConfigurecheck; "ConfigureCheckboxes"
0x180020a21  lea     rcx, [rbp+150h+var_1B0]
0x180020a25  call    ??0?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180020a2a  lea     rax, ??_7ConfigureCheckboxes@FirewallUxTelemetry@@6B@; const FirewallUxTelemetry::ConfigureCheckboxes::`vftable'
0x180020a31  mov     [rbp+150h+var_1B0], rax
0x180020a35  lea     rcx, [rbp+150h+var_1B0]; this
0x180020a39  call    ?StartActivity@ConfigureCheckboxes@FirewallUxTelemetry@@QEAAXXZ; FirewallUxTelemetry::ConfigureCheckboxes::StartActivity(void)
0x180020a3e  nop
0x180020a3f  mov     rcx, r15; this
0x180020a42  call    ??0StackPanel@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ; winrt::Windows::UI::Xaml::Controls::StackPanel::StackPanel(void)
0x180020a47  lea     r13d, [r12+1]
0x180020a4c  mov     [rsp+250h+var_1E8], r13d
0x180020a51  xorps   xmm0, xmm0
0x180020a54  movups  [rbp+150h+var_60], xmm0
0x180020a5b  xorps   xmm1, xmm1
0x180020a5e  movups  [rbp+150h+var_50], xmm1
0x180020a65  lea     rdx, [rbp+150h+var_60]
0x180020a6c  mov     rcx, r15
0x180020a6f  call    ?Margin@?$consume_Windows_UI_Xaml_IFrameworkElement@UStackPanel@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUThickness@Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::StackPanel>::Margin(winrt::Windows::UI::Xaml::Thickness const &)
0x180020a74  lea     r14, [rdi+210h]
0x180020a7b  mov     rbx, [r14]
0x180020a7e  mov     rsi, [r14+8]
0x180020a82  cmp     rbx, rsi
0x180020a85  jz      short loc_180020AA4
0x180020a87  cmp     [rbx], r12
0x180020a8a  jz      short loc_180020A94
0x180020a8c  mov     rcx, rbx
0x180020a8f  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180020a94  add     rbx, 8
0x180020a98  cmp     rbx, rsi
0x180020a9b  jnz     short loc_180020A87
0x180020a9d  mov     rax, [r14]
0x180020aa0  mov     [r14+8], rax
0x180020aa4  lea     rcx, [rsp+250h+var_1D8]; this
0x180020aa9  call    ??0TextBlock@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ; winrt::Windows::UI::Xaml::Controls::TextBlock::TextBlock(void)
0x180020aae  nop
0x180020aaf  movsd   xmm1, cs:__real@402c000000000000
0x180020ab7  lea     rcx, [rsp+250h+var_1D8]
0x180020abc  call    ?FontSize@?$consume_Windows_UI_Xaml_Controls_ITextBlock@UITextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@N@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::FontSize(double)
0x180020ac1  mov     dword ptr [rsp+250h+var_220], r12d
0x180020ac6  lea     rdx, [rsp+250h+var_220]
0x180020acb  lea     rcx, [rsp+250h+var_1D8]
0x180020ad0  call    ?HorizontalAlignment@?$consume_Windows_UI_Xaml_IFrameworkElement@UTextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBW40Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::HorizontalAlignment(winrt::Windows::UI::Xaml::HorizontalAlignment const &)
0x180020ad5  mov     dword ptr [rsp+250h+var_220], r12d
0x180020ada  lea     rdx, [rsp+250h+var_220]
0x180020adf  lea     rcx, [rsp+250h+var_1D8]
0x180020ae4  call    ?VerticalAlignment@?$consume_Windows_UI_Xaml_IFrameworkElement@UTextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBW40Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::VerticalAlignment(winrt::Windows::UI::Xaml::VerticalAlignment const &)
0x180020ae9  mov     dword ptr [rsp+250h+var_220], 2
0x180020af1  lea     rdx, [rsp+250h+var_220]
0x180020af6  lea     rcx, [rsp+250h+var_1D8]
0x180020afb  call    ?TextWrapping@?$consume_Windows_UI_Xaml_Controls_ITextBlock@UITextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBW40Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::TextWrapping(winrt::Windows::UI::Xaml::TextWrapping const &)
0x180020b00  mov     edx, 0FAh
0x180020b05  lea     rcx, [rsp+250h+lpMem]
0x180020b0a  call    ?GetResourceString@@YA?AUhstring@winrt@@I@Z; GetResourceString(uint)
0x180020b0f  nop
0x180020b10  mov     rax, [rax]
0x180020b13  mov     qword ptr [rbp+150h+var_60], rax
0x180020b1a  lea     rdx, [rbp+150h+var_60]
0x180020b21  lea     rcx, [rsp+250h+var_1D8]
0x180020b26  call    ?Text@?$consume_Windows_UI_Xaml_Controls_ITextBlock@UITextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::Text(winrt::param::hstring const &)
0x180020b2b  nop
0x180020b2c  or      esi, 0FFFFFFFFh
0x180020b2f  mov     rbx, [rsp+250h+lpMem]
0x180020b34  test    rbx, rbx
0x180020b37  jz      short loc_180020B58
0x180020b39  mov     eax, esi
0x180020b3b  lock xadd [rbx+18h], eax
0x180020b40  sub     eax, 1
0x180020b43  jnz     short loc_180020BA3
0x180020b45  nop
0x180020b46  call    WINRT_IMPL_GetProcessHeap
0x180020b4b  mov     rcx, rax; hHeap
0x180020b4e  mov     r8, rbx; lpMem
0x180020b51  xor     edx, edx; dwFlags
0x180020b53  call    WINRT_IMPL_HeapFree
0x180020b58  xorps   xmm0, xmm0
0x180020b5b  movups  [rbp+150h+var_60], xmm0
0x180020b62  movdqa  xmm1, cs:__xmm@40240000000000000000000000000000
0x180020b6a  movups  [rbp+150h+var_50], xmm1
0x180020b71  lea     rdx, [rbp+150h+var_60]
0x180020b78  lea     rcx, [rsp+250h+var_1D8]
0x180020b7d  call    ?Margin@?$consume_Windows_UI_Xaml_IFrameworkElement@UStackPanel@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUThickness@Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::StackPanel>::Margin(winrt::Windows::UI::Xaml::Thickness const &)
0x180020b82  lea     rdx, [rsp+250h+var_208]
0x180020b87  mov     rcx, r15
0x180020b8a  call    ?Children@?$consume_Windows_UI_Xaml_Controls_IPanel@UGrid@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Xaml_Controls_IPanel<winrt::Windows::UI::Xaml::Controls::Grid>::Children(void)
0x180020b8f  mov     rbx, rax
0x180020b92  mov     rcx, [rsp+250h+var_1D8]
0x180020b97  test    rcx, rcx
0x180020b9a  jnz     short loc_180020BAE
0x180020b9c  mov     [rsp+250h+var_1F8], r12
0x180020ba1  jmp     short loc_180020BD4
0x180020ba3  test    eax, eax
0x180020ba5  jns     short loc_180020B58
0x180020ba7  call    cs:__imp_abort
0x180020bae  mov     [rsp+250h+var_210], r12
0x180020bb3  mov     rax, [rcx]
0x180020bb6  lea     r8, [rsp+250h+var_210]
0x180020bbb  lea     rdx, ??$guid_v@UIUIElement@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::IUIElement>
0x180020bc2  mov     rax, [rax]
0x180020bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bca  mov     rax, [rsp+250h+var_210]
0x180020bcf  mov     [rsp+250h+var_1F8], rax
0x180020bd4  lea     rdx, [rsp+250h+var_1F8]
0x180020bd9  mov     rcx, rbx
0x180020bdc  call    ?Append@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@UColumnDefinition@Controls@Xaml@UI@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UColumnDefinition@Controls@Xaml@UI@45@@impl@winrt@@QEBA@AEBUColumnDefinition@Controls@Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::UI::Xaml::Controls::ColumnDefinition>,winrt::Windows::UI::Xaml::Controls::ColumnDefinition>::Append(winrt::Windows::UI::Xaml::Controls::ColumnDefinition const &)
0x180020be1  nop
0x180020be2  cmp     [rsp+250h+var_1F8], r12
0x180020be7  jz      short loc_180020BF4
0x180020be9  lea     rcx, [rsp+250h+var_1F8]
0x180020bee  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180020bf3  nop
0x180020bf4  cmp     [rsp+250h+var_208], r12
0x180020bf9  jz      short loc_180020C05
0x180020bfb  lea     rcx, [rsp+250h+var_208]
0x180020c00  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180020c05  test    byte ptr [rdi+1F8h], 4
0x180020c0c  jz      loc_180021161
0x180020c12  lea     rdx, [rsp+250h+var_210]
0x180020c17  mov     rcx, rdi
0x180020c1a  call    ?get_weak@?$implements@UFirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UIFirewallNotificationDialog@34567@UFirewallDialogBase@234567@@winrt@@QEAA?AU?$weak_ref@UFirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@2@XZ; winrt::implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::IFirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase>::get_weak(void)
0x180020c1f  mov     r12, [rax]
0x180020c22  xor     r13d, r13d
0x180020c25  mov     [rax], r13
0x180020c28  mov     [rbp+150h+var_1C8], r12
0x180020c2c  cmp     [rsp+250h+var_210], r13
0x180020c31  jz      short loc_180020C3D
0x180020c33  lea     rcx, [rsp+250h+var_210]
0x180020c38  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180020c3d  lea     rdx, [rsp+250h+var_220]
0x180020c42  mov     rcx, rdi
0x180020c45  call    ?get_weak@?$implements@UFirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UIFirewallNotificationDialog@34567@UFirewallDialogBase@234567@@winrt@@QEAA?AU?$weak_ref@UFirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@2@XZ; winrt::implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::IFirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase>::get_weak(void)
0x180020c4a  mov     r15, [rax]
0x180020c4d  mov     [rax], r13
0x180020c50  mov     [rsp+250h+var_1E0], r15
0x180020c55  cmp     [rsp+250h+var_220], r13
0x180020c5a  jz      short loc_180020C66
0x180020c5c  lea     rcx, [rsp+250h+var_220]
0x180020c61  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180020c66  lea     rcx, [rsp+250h+var_1F8]; this
0x180020c6b  call    ??0TextBlock@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ; winrt::Windows::UI::Xaml::Controls::TextBlock::TextBlock(void)
0x180020c70  nop
0x180020c71  movsd   xmm1, cs:__real@402c000000000000
0x180020c79  lea     rcx, [rsp+250h+var_1F8]
0x180020c7e  call    ?FontSize@?$consume_Windows_UI_Xaml_Controls_ITextBlock@UITextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@N@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::FontSize(double)
0x180020c83  mov     dword ptr [rsp+250h+var_220], r13d
0x180020c88  lea     rdx, [rsp+250h+var_220]
0x180020c8d  lea     rcx, [rsp+250h+var_1F8]
0x180020c92  call    ?HorizontalAlignment@?$consume_Windows_UI_Xaml_IFrameworkElement@UTextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBW40Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::HorizontalAlignment(winrt::Windows::UI::Xaml::HorizontalAlignment const &)
0x180020c97  mov     dword ptr [rsp+250h+var_220], r13d
0x180020c9c  lea     rdx, [rsp+250h+var_220]
0x180020ca1  lea     rcx, [rsp+250h+var_1F8]
0x180020ca6  call    ?VerticalAlignment@?$consume_Windows_UI_Xaml_IFrameworkElement@UTextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBW40Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::TextBlock>::VerticalAlignment(winrt::Windows::UI::Xaml::VerticalAlignment const &)
0x180020cab  mov     dword ptr [rsp+250h+var_220], 2
0x180020cb3  lea     rdx, [rsp+250h+var_220]
0x180020cb8  lea     rcx, [rsp+250h+var_1F8]
0x180020cbd  call    ?TextWrapping@?$consume_Windows_UI_Xaml_Controls_ITextBlock@UITextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBW40Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::TextWrapping(winrt::Windows::UI::Xaml::TextWrapping const &)
0x180020cc2  mov     edx, 0FEh
0x180020cc7  lea     rcx, [rsp+250h+lpMem]
0x180020ccc  call    ?GetResourceString@@YA?AUhstring@winrt@@I@Z; GetResourceString(uint)
0x180020cd1  nop
0x180020cd2  mov     rax, [rax]
0x180020cd5  mov     qword ptr [rbp+150h+var_60], rax
0x180020cdc  lea     rdx, [rbp+150h+var_60]
0x180020ce3  lea     rcx, [rsp+250h+var_1F8]
0x180020ce8  call    ?Text@?$consume_Windows_UI_Xaml_Controls_ITextBlock@UITextBlock@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_ITextBlock<winrt::Windows::UI::Xaml::Controls::ITextBlock>::Text(winrt::param::hstring const &)
0x180020ced  nop
0x180020cee  mov     rbx, [rsp+250h+lpMem]
0x180020cf3  test    rbx, rbx
0x180020cf6  jz      short loc_180020D17
0x180020cf8  mov     eax, esi
0x180020cfa  lock xadd [rbx+18h], eax
0x180020cff  sub     eax, 1
0x180020d02  jnz     short loc_180020D7E
0x180020d04  nop
0x180020d05  call    WINRT_IMPL_GetProcessHeap
0x180020d0a  mov     rcx, rax; hHeap
0x180020d0d  mov     r8, rbx; lpMem
0x180020d10  xor     edx, edx; dwFlags
0x180020d12  call    WINRT_IMPL_HeapFree
0x180020d17  lea     rcx, [rsp+250h+var_208]; this
0x180020d1c  call    ??0CheckBox@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ; winrt::Windows::UI::Xaml::Controls::CheckBox::CheckBox(void)
0x180020d21  nop
0x180020d22  mov     eax, [rdi+258h]
0x180020d28  shr     eax, 2
0x180020d2b  and     al, 1
0x180020d2d  mov     [rsp+250h+var_218], al
0x180020d31  lea     rdx, [rsp+250h+var_218]
0x180020d36  lea     rcx, [rsp+250h+var_220]
0x180020d3b  call    ??0?$IReference@_N@Foundation@Windows@winrt@@QEAA@AEB_N@Z; winrt::Windows::Foundation::IReference<bool>::IReference<bool>(bool const &)
0x180020d40  nop
0x180020d41  lea     rdx, [rsp+250h+var_220]
0x180020d46  lea     rcx, [rsp+250h+var_208]
0x180020d4b  call    ?IsChecked@?$consume_Windows_UI_Xaml_Controls_Primitives_IToggleButton@UCheckBox@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBU?$IReference@_N@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_Primitives_IToggleButton<winrt::Windows::UI::Xaml::Controls::CheckBox>::IsChecked(winrt::Windows::Foundation::IReference<bool> const &)
0x180020d50  nop
0x180020d51  cmp     [rsp+250h+var_220], r13
0x180020d56  jz      short loc_180020D63
0x180020d58  lea     rcx, [rsp+250h+var_220]
0x180020d5d  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180020d62  nop
0x180020d63  mov     dl, 1
0x180020d65  mov     bl, r13b
0x180020d68  cmp     [rdi+20Eh], r13b
0x180020d6f  jz      short loc_180020D9C
0x180020d71  test    byte ptr [rdi+204h], 4
0x180020d78  jz      short loc_180020D89
0x180020d7a  mov     cl, dl
0x180020d7c  jmp     short loc_180020D95
0x180020d7e  test    eax, eax
0x180020d80  jns     short loc_180020D17
0x180020d82  call    cs:__imp_abort
0x180020d89  test    byte ptr [rdi+1FCh], 4
0x180020d90  jz      short loc_180020DA5
0x180020d92  mov     cl, r13b
0x180020d95  mov     bl, dl
0x180020d97  mov     dl, r13b
0x180020d9a  jmp     short loc_180020DA9
0x180020d9c  test    byte ptr [rdi+1FCh], 4
0x180020da3  jnz     short loc_180020D7A
0x180020da5  mov     cl, [rsp+250h+var_218]
0x180020da9  test    byte ptr [rdi+200h], 4
0x180020db0  jz      short loc_180020DC3
0x180020db2  test    bl, bl
0x180020db4  jz      short loc_180020DBB
0x180020db6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180020dbb  mov     cl, r13b
0x180020dbe  mov     bl, 1
0x180020dc0  mov     dl, r13b
0x180020dc3  mov     al, [rdi+20Dh]
0x180020dc9  neg     al
0x180020dcb  sbb     sil, sil
0x180020dce  and     sil, dl
0x180020dd1  mov     byte ptr [rsp+250h+var_220], sil
0x180020dd6  mov     byte ptr [rsp+250h+var_220+1], cl
0x180020dda  mov     byte ptr [rsp+250h+var_220+2], bl
0x180020dde  mov     dl, sil
0x180020de1  lea     rcx, [rsp+250h+var_208]
0x180020de6  call    ?IsEnabled@?$consume_Windows_UI_Xaml_Controls_IControl@UCheckBox@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@_N@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_IControl<winrt::Windows::UI::Xaml::Controls::CheckBox>::IsEnabled(bool)
0x180020deb  test    bl, bl
0x180020ded  jz      short loc_180020E20
0x180020def  lea     rdx, [rsp+250h+var_220+1]
0x180020df4  lea     rcx, [rsp+250h+var_210]
0x180020df9  call    ??0?$IReference@_N@Foundation@Windows@winrt@@QEAA@AEB_N@Z; winrt::Windows::Foundation::IReference<bool>::IReference<bool>(bool const &)
0x180020dfe  nop
0x180020dff  lea     rdx, [rsp+250h+var_210]
0x180020e04  lea     rcx, [rsp+250h+var_208]
0x180020e09  call    ?IsChecked@?$consume_Windows_UI_Xaml_Controls_Primitives_IToggleButton@UCheckBox@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBU?$IReference@_N@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_Primitives_IToggleButton<winrt::Windows::UI::Xaml::Controls::CheckBox>::IsChecked(winrt::Windows::Foundation::IReference<bool> const &)
0x180020e0e  nop
0x180020e0f  cmp     [rsp+250h+var_210], r13
0x180020e14  jz      short loc_180020E20
0x180020e16  lea     rcx, [rsp+250h+var_210]
0x180020e1b  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180020e20  lea     rdx, [rsp+250h+var_210]
0x180020e25  lea     rcx, [rsp+250h+var_208]
0x180020e2a  call    ?IsChecked@?$consume_Windows_UI_Xaml_Controls_Primitives_IToggleButton@UCheckBox@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Xaml_Controls_Primitives_IToggleButton<winrt::Windows::UI::Xaml::Controls::CheckBox>::IsChecked(void)
0x180020e2f  nop
0x180020e30  lea     rbx, [rdi+250h]
0x180020e37  mov     rcx, rax
0x180020e3a  call    ?GetBoolean@?$consume_Windows_Foundation_IPropertyValue@U?$IReference@_N@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IReference<bool>>::GetBoolean(void)
0x180020e3f  mov     [rbx], al
0x180020e41  cmp     [rsp+250h+var_210], r13
0x180020e46  jz      short loc_180020E52
0x180020e48  lea     rcx, [rsp+250h+var_210]
0x180020e4d  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180020e52  mov     rdx, rbx
0x180020e55  lea     rcx, [rsp+250h+var_220]
0x180020e5a  call    ??$PublicNetworks@AEA_NAEA_N@ConfigureCheckboxes@FirewallUxTelemetry@@SAXAEA_N0@Z; FirewallUxTelemetry::ConfigureCheckboxes::PublicNetworks<bool &,bool &>(bool &,bool &)
0x180020e5f  cmp     word ptr cs:aPubliccheckbox+1Ch, r13w; ""
0x180020e67  jz      short loc_180020E70
0x180020e69  call    cs:__imp_abort
0x180020e70  mov     ebx, 1
0x180020e75  mov     dword ptr [rbp+150h+var_60+8], ebx
0x180020e7b  mov     dword ptr [rbp+150h+var_60+0Ch], 0Eh
0x180020e85  lea     rax, aPubliccheckbox; "PublicCheckBox"
0x180020e8c  mov     qword ptr [rbp+150h+var_50+8], rax
0x180020e93  lea     rax, [rbp+150h+var_60+8]
0x180020e9a  mov     qword ptr [rbp+150h+var_60], rax
0x180020ea1  lea     rdx, [rbp+150h+var_60]
0x180020ea8  lea     rcx, [rsp+250h+var_208]
0x180020ead  call    ?Name@?$consume_Windows_UI_Xaml_IFrameworkElement@UCheckBox@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::CheckBox>::Name(winrt::param::hstring const &)
0x180020eb2  lea     rdx, [rsp+250h+var_1F8]
0x180020eb7  lea     rcx, [rsp+250h+var_208]
  ... truncated ...
```
