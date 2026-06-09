# DirectUI::TimePicker::OnApplyTemplate(void)

- ea: `0x1809685f0`
- end: `0x180969513`
- name: `?OnApplyTemplate@TimePicker@DirectUI@@MEAAJXZ`
- size: `3875`
- prototype: `HRESULT __fastcall(DirectUI::TimePicker *this)`
- caller_count: `0`
- callee_count: `33`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x18005bcac`
- `0x18005e96c`
- `0x18009a16c`
- `0x18009ba40`
- `0x18009d4f4`
- `0x1800f4510`
- `0x18018fa54`
- `0x1801df610`
- `0x1801e5458`
- `0x180248fa8`
- `0x1802490f0`
- `0x180304634`
- `0x180304c94`
- `0x18034d3ec`
- `0x18037f18c`
- `0x1803805dc`
- `0x1803839c0`
- `0x180383ffc`
- `0x180384f48`
- `0x18066dd50`
- `0x1806b6b8c`
- `0x1806e18f0`
- `0x1806e7e00`
- `0x180772d6c`
- `0x180965c94`
- `0x180965d9c`
- `0x1809685f0`
- `0x18096a430`
- `0x18096ae44`
- `0x18096b4c0`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180968c79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180968d06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180968de1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180968e33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180968f7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180968fd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18096915c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1809691af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180968c79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180968d06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180968de1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180968e33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180968f7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180968fd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18096915c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1809691af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180968cab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180968cab`

## pseudocode

```c
__int64 __fastcall DirectUI::TimePicker::OnApplyTemplate(DirectUI::TimePicker *this)
{
  DirectUI::TimePicker *v1; // r14
  IInspectable *m_value; // rdx
  HSTRING__ *hstring; // rbx
  HRESULT v5; // eax
  unsigned int v6; // edi
  DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::ITextBlock,1,0> *p_m_tpPeriodTextBlock; // r12
  IInspectable *v8; // rdx
  DirectUI::TrackerPtr<DirectUI::TrackerCollection<IInspectable *>,1,0> *p_m_tpHourSource; // r13
  IInspectable *v10; // rdx
  IInspectable **v11; // rsi
  HRESULT v12; // eax
  HRESULT v13; // eax
  HRESULT v14; // eax
  HRESULT v15; // eax
  HRESULT v16; // eax
  HRESULT v17; // eax
  HRESULT v18; // eax
  HRESULT v19; // eax
  HRESULT v20; // eax
  HRESULT v21; // eax
  HRESULT v22; // eax
  HRESULT v23; // eax
  HRESULT v24; // eax
  HRESULT updated; // eax
  const std::_Ph<1> *v26; // r9
  std::_List_node<CDependencyObject *,void *> *Myhead; // rdi
  HRESULT StringFromObject; // eax
  std::_Binder<std::_Unforced,long (__cdecl DirectUI::AutoSuggestBox::*)(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *),DirectUI::AutoSuggestBox *,std::_Ph<1> const &,std::_Ph<2> const &> *v29; // rax
  Windows::UI::Xaml::Controls::Primitives::ISelector **v30; // r10
  Windows::UI::Xaml::Controls::Primitives::ISelector *v31; // rdx
  std::_Func_base<long,IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *> *v32; // r11
  HRESULT ValueByKnownIndex; // eax
  DirectUI::DXamlCore *Current; // rbx
  std::_Binder<std::_Unforced,long (__cdecl DirectUI::AutoSuggestBox::*)(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *),DirectUI::AutoSuggestBox *,std::_Ph<1> const &,std::_Ph<2> const &> *v35; // rax
  Windows::UI::Xaml::Controls::Primitives::ISelector *v36; // rdx
  std::_Func_base<long,IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *> *v37; // r11
  IUnknown *v38; // rcx
  DirectUI::DXamlCore *v39; // rbx
  std::_Binder<std::_Unforced,long (__cdecl DirectUI::AutoSuggestBox::*)(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *),DirectUI::AutoSuggestBox *,std::_Ph<1> const &,std::_Ph<2> const &> *v40; // rax
  Windows::UI::Xaml::Controls::Primitives::ISelector *v41; // rdx
  IUnknown *v42; // rcx
  DirectUI::DXamlCore *v43; // rbx
  const std::_Ph<1> *v44; // r8
  const std::_Ph<2> *v45; // r9
  Windows::UI::Xaml::Controls::Primitives::IButtonBase *v46; // rdx
  const std::_Ph<2> *v48; // [rsp+20h] [rbp-E0h]
  __int128 _Func; // [rsp+30h] [rbp-D0h] BYREF
  std::tuple<DirectUI::SplitView *,std::_Ph<1>,std::_Ph<2> > v50; // [rsp+40h] [rbp-C0h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IUIElement> spSecondColumnDivider; // [rsp+50h] [rbp-B0h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IUIElement> spFirstColumnDivider; // [rsp+58h] [rbp-A8h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::IColumnDefinition> spThirdTextBlockColumn; // [rsp+60h] [rbp-A0h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::IColumnDefinition> spSecondTextBlockColumn; // [rsp+68h] [rbp-98h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::IColumnDefinition> spFirstTextBlockColumn; // [rsp+70h] [rbp-90h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::ITextBlock> spPeriodTextBlock; // [rsp+78h] [rbp-88h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::ITextBlock> spMinuteTextBlock; // [rsp+80h] [rbp-80h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::ITextBlock> spHourTextBlock; // [rsp+88h] [rbp-78h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::IButtonBase> spFlyoutButton; // [rsp+90h] [rbp-70h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IFrameworkElement> spLayoutRoot; // [rsp+98h] [rbp-68h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::IBorder> spThirdPickerHost; // [rsp+A0h] [rbp-60h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::IBorder> spSecondPickerHost; // [rsp+A8h] [rbp-58h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::IBorder> spFirstPickerHost; // [rsp+B0h] [rbp-50h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::ISelector> spPeriodPicker; // [rsp+B8h] [rbp-48h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::ISelector> spMinutePicker; // [rsp+C0h] [rbp-40h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::ISelector> spHourPicker; // [rsp+C8h] [rbp-38h] BYREF
  std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *)> v67; // [rsp+D0h] [rbp-30h] BYREF
  std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *)> result[2]; // [rsp+110h] [rbp+10h] BYREF
  Windows::Internal::String strAutomationName; // [rsp+1A0h] [rbp+A0h] BYREF
  Windows::Internal::String strParentAutomationName; // [rsp+1A8h] [rbp+A8h] BYREF
  ctl::ComPtr<IInspectable> spHeaderAsInspectable; // [rsp+1B0h] [rbp+B0h] BYREF
  Windows::Internal::String strComboAutomationName; // [rsp+1B8h] [rbp+B8h] BYREF

  v1 = (DirectUI::TimePicker *)((char *)this - 360);
  m_value = (IInspectable *)this->m_tpMinuteTextBlock.m_trackerReference.m_value;
  hstring = 0;
  spHourPicker.ptr_ = 0;
  spMinutePicker.ptr_ = 0;
  spPeriodPicker.ptr_ = 0;
  spFirstPickerHost.ptr_ = 0;
  spSecondPickerHost.ptr_ = 0;
  spThirdPickerHost.ptr_ = 0;
  spLayoutRoot.ptr_ = 0;
  spFlyoutButton.ptr_ = 0;
  spHourTextBlock.ptr_ = 0;
  spMinuteTextBlock.ptr_ = 0;
  spPeriodTextBlock.ptr_ = 0;
  spFirstTextBlockColumn.ptr_ = 0;
  spSecondTextBlockColumn.ptr_ = 0;
  spThirdTextBlockColumn.ptr_ = 0;
  spFirstColumnDivider.ptr_ = 0;
  spSecondColumnDivider.ptr_ = 0;
  strAutomationName._hstring = 0;
  strParentAutomationName._hstring = 0;
  strComboAutomationName._hstring = 0;
  if ( m_value )
  {
    v5 = ctl::EventPtrBase<ctl::event_handler<Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::HandwritingView *,Windows::UI::Xaml::Controls::HandwritingPanelClosedEventArgs *>,Windows::UI::Xaml::Controls::IHandwritingView,Windows::UI::Xaml::Controls::IHandwritingPanelClosedEventArgs,DirectUI::HandwritingViewClosedTraits>>::DetachEventHandler(
           (ctl::EventPtrBase<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::UIElementGotFocusTraits> > *)&this->m_tpPeriodSource,
           m_value);
    v6 = v5;
    if ( v5 < 0 )
      goto LABEL_104;
  }
  p_m_tpPeriodTextBlock = &this->m_tpPeriodTextBlock;
  v8 = (IInspectable *)this->m_tpPeriodTextBlock.m_trackerReference.m_value;
  if ( v8 )
  {
    v5 = ctl::EventPtrBase<ctl::event_handler<Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::HandwritingView *,Windows::UI::Xaml::Controls::HandwritingPanelClosedEventArgs *>,Windows::UI::Xaml::Controls::IHandwritingView,Windows::UI::Xaml::Controls::IHandwritingPanelClosedEventArgs,DirectUI::HandwritingViewClosedTraits>>::DetachEventHandler(
           (ctl::EventPtrBase<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::UIElementGotFocusTraits> > *)&this->m_tpPeriodSource.m_trackerReference.8,
           v8);
    v6 = v5;
    if ( v5 < 0 )
      goto LABEL_104;
  }
  p_m_tpHourSource = &this->m_tpHourSource;
  v10 = (IInspectable *)this->m_tpHourSource.m_trackerReference.m_value;
  if ( v10 )
  {
    v5 = ctl::EventPtrBase<ctl::event_handler<Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::HandwritingView *,Windows::UI::Xaml::Controls::HandwritingPanelClosedEventArgs *>,Windows::UI::Xaml::Controls::IHandwritingView,Windows::UI::Xaml::Controls::IHandwritingPanelClosedEventArgs,DirectUI::HandwritingViewClosedTraits>>::DetachEventHandler(
           (ctl::EventPtrBase<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::UIElementGotFocusTraits> > *)&this->m_tpPeriodSource.m_trackerReference
         + 2,
           v10);
    v6 = v5;
    if ( v5 < 0 )
      goto LABEL_104;
  }
  v11 = (IInspectable **)&this->Windows::UI::Composition::IVisualElement;
  if ( this->DirectUI::TimePickerGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::Windows::UI::Composition::IVisualElement::IInspectable::IUnknown::__vftable )
  {
    if ( !CQuirksMode2::XamlQuirkIsEnabled(0x200F2u) )
    {
      if ( IsXamlControlsCalculateFlyoutPlacementPresent() )
      {
        v5 = ctl::EventPtrBase<ctl::event_handler<Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::HandwritingView *,Windows::UI::Xaml::Controls::HandwritingPanelClosedEventArgs *>,Windows::UI::Xaml::Controls::IHandwritingView,Windows::UI::Xaml::Controls::IHandwritingPanelClosedEventArgs,DirectUI::HandwritingViewClosedTraits>>::DetachEventHandler(
               (ctl::EventPtrBase<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::UIElementGotFocusTraits> > *)&this->m_tpFirstPickerHost,
               *v11);
        v6 = v5;
        if ( v5 < 0 )
          goto LABEL_104;
      }
    }
  }
  DirectUI::TrackerTargetReference::Clear(&this->m_tpMinuteTextBlock.m_trackerReference, 1u, 0);
  DirectUI::TrackerTargetReference::Clear(&this->m_tpPeriodTextBlock.m_trackerReference, 1u, 0);
  DirectUI::TrackerTargetReference::Clear(&this->m_tpHourSource.m_trackerReference, 1u, 0);
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElementOverrides2,DirectUI::FrameworkElementGenerated>,
    1u,
    0);
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement6,DirectUI::FrameworkElementGenerated>,
    1u,
    0);
  DirectUI::TrackerTargetReference::Clear((DirectUI::TrackerTargetReference *)&this->m_pDataContextChangedSource, 1u, 0);
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->Windows::UI::Xaml::Controls::IControl,
    1u,
    0);
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->ctl::forwarder_holder<Windows::UI::Xaml::Controls::IControl2,DirectUI::ControlGenerated>,
    1u,
    0);
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->ctl::forwarder_holder<Windows::UI::Xaml::Controls::IControl5,DirectUI::ControlGenerated>,
    1u,
    0);
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)((char *)&this->DirectUI::Control + 520),
    1u,
    0);
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->Windows::UI::Xaml::Controls::ITimePicker2,
    1u,
    0);
  DirectUI::TrackerTargetReference::Clear(&this->m_tpFlyoutButton.m_trackerReference, 1u, 0);
  DirectUI::TrackerTargetReference::Clear(&this->m_tpHourTextBlock.m_trackerReference, 1u, 0);
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->Windows::UI::Composition::IVisualElement,
    1u,
    0);
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IUIElement4,DirectUI::UIElementGenerated>,
    1u,
    0);
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IUIElementOverrides7,DirectUI::UIElementGenerated>,
    1u,
    0);
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IUIElement9,DirectUI::UIElementGenerated>,
    1u,
    0);
  v5 = DirectUI::Control::OnApplyTemplate(this);
  v6 = v5;
  if ( v5 < 0 )
  {
LABEL_104:
    OnFailure_2990_(v5);
    goto $Cleanup_9016;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spHourPicker);
  v12 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::Primitives::ISelector,Windows::UI::Xaml::Controls::Primitives::ISelector>(
          v1,
          (wchar_t *)L"HourPicker",
          0xAu,
          &spHourPicker.ptr_);
  v6 = v12;
  if ( v12 < 0 )
  {
    OnFailure_2990_(v12);
    goto $Cleanup_9016;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spMinutePicker);
  v13 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::Primitives::ISelector,Windows::UI::Xaml::Controls::Primitives::ISelector>(
          v1,
          (wchar_t *)L"MinutePicker",
          0xCu,
          &spMinutePicker.ptr_);
  v6 = v13;
  if ( v13 < 0 )
  {
    OnFailure_2990_(v13);
    goto $Cleanup_9016;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spPeriodPicker);
  v14 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::Primitives::ISelector,Windows::UI::Xaml::Controls::Primitives::ISelector>(
          v1,
          (wchar_t *)L"PeriodPicker",
          0xCu,
          &spPeriodPicker.ptr_);
  v6 = v14;
  if ( v14 < 0 )
  {
    OnFailure_2990_(v14);
    goto $Cleanup_9016;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spFirstPickerHost);
  v15 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IBorder,Windows::UI::Xaml::Controls::IBorder>(
          v1,
          (wchar_t *)L"FirstPickerHost",
          0xFu,
          &spFirstPickerHost.ptr_);
  v6 = v15;
  if ( v15 < 0 )
  {
    OnFailure_2990_(v15);
    goto $Cleanup_9016;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spSecondPickerHost);
  v16 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IBorder,Windows::UI::Xaml::Controls::IBorder>(
          v1,
          (wchar_t *)L"SecondPickerHost",
          0x10u,
          &spSecondPickerHost.ptr_);
  v6 = v16;
  if ( v16 < 0 )
  {
    OnFailure_2990_(v16);
    goto $Cleanup_9016;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spThirdPickerHost);
  v17 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IBorder,Windows::UI::Xaml::Controls::IBorder>(
          v1,
          (wchar_t *)L"ThirdPickerHost",
          0xFu,
          &spThirdPickerHost.ptr_);
  v6 = v17;
  if ( v17 < 0 )
  {
    OnFailure_2990_(v17);
    goto $Cleanup_9016;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spHourTextBlock);
  v18 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::ITextBlock,Windows::UI::Xaml::Controls::ITextBlock>(
          v1,
          (wchar_t *)L"HourTextBlock",
          0xDu,
          &spHourTextBlock.ptr_);
  v6 = v18;
  if ( v18 < 0 )
  {
    OnFailure_2990_(v18);
    goto $Cleanup_9016;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spMinuteTextBlock);
  v19 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::ITextBlock,Windows::UI::Xaml::Controls::ITextBlock>(
          v1,
          (wchar_t *)L"MinuteTextBlock",
          0xFu,
          &spMinuteTextBlock.ptr_);
  v6 = v19;
  if ( v19 < 0 )
  {
    OnFailure_2990_(v19);
    goto $Cleanup_9016;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spPeriodTextBlock);
  v20 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::ITextBlock,Windows::UI::Xaml::Controls::ITextBlock>(
          v1,
          (wchar_t *)L"PeriodTextBlock",
          0xFu,
          &spPeriodTextBlock.ptr_);
  v6 = v20;
  if ( v20 < 0 )
  {
    OnFailure_2990_(v20);
    goto $Cleanup_9016;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spFirstTextBlockColumn);
  v21 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IColumnDefinition,Windows::UI::Xaml::Controls::IColumnDefinition>(
          v1,
          (wchar_t *)L"FirstTextBlockColumn",
          0x14u,
          &spFirstTextBlockColumn.ptr_);
  v6 = v21;
  if ( v21 < 0 )
  {
    OnFailure_2990_(v21);
    goto $Cleanup_9016;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spSecondTextBlockColumn);
  v22 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IColumnDefinition,Windows::UI::Xaml::Controls::IColumnDefinition>(
          v1,
          (wchar_t *)L"SecondTextBlockColumn",
          0x15u,
          &spSecondTextBlockColumn.ptr_);
  v6 = v22;
  if ( v22 < 0 )
  {
    OnFailure_2990_(v22);
    goto $Cleanup_9016;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spThirdTextBlockColumn);
  v23 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IColumnDefinition,Windows::UI::Xaml::Controls::IColumnDefinition>(
          v1,
          (wchar_t *)L"ThirdTextBlockColumn",
          0x14u,
          &spThirdTextBlockColumn.ptr_);
  v6 = v23;
  if ( v23 < 0 )
  {
    OnFailure_2990_(v23);
    goto $Cleanup_9016;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spFirstColumnDivider);
  v24 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::IUIElement,Windows::UI::Xaml::IUIElement>(
          v1,
          (wchar_t *)L"FirstColumnDivider",
          0x12u,
          &spFirstColumnDivider.ptr_);
  v6 = v24;
  if ( v24 < 0 )
  {
    OnFailure_2990_(v24);
    goto $Cleanup_9016;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spSecondColumnDivider);
  updated = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::IUIElement,Windows::UI::Xaml::IUIElement>(
              v1,
              (wchar_t *)L"SecondColumnDivider",
              0x13u,
              &spSecondColumnDivider.ptr_);
  v6 = updated;
  if ( updated < 0 )
    goto LABEL_88;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spLayoutRoot);
  updated = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::IFrameworkElement,Windows::UI::Xaml::IFrameworkElement>(
              v1,
              (wchar_t *)L"LayoutRoot",
              0xAu,
              &spLayoutRoot.ptr_);
  v6 = updated;
  if ( updated < 0 )
    goto LABEL_88;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spFlyoutButton);
  updated = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::Primitives::IButtonBase,Windows::UI::Xaml::Controls::Primitives::IButtonBase>(
              v1,
              (wchar_t *)L"FlyoutButton",
              0xCu,
              &spFlyoutButton.ptr_);
  v6 = updated;
  if ( updated < 0 )
    goto LABEL_88;
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpFirstTextBlockColumn,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->m_tpMinuteTextBlock,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spHourPicker.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpFirstTextBlockColumn,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->m_tpPeriodTextBlock,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spMinutePicker.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpFirstTextBlockColumn,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->m_tpHourSource,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spPeriodPicker.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpFirstTextBlockColumn,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElementOverrides2,DirectUI::FrameworkElementGenerated>,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spFirstPickerHost.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpFirstTextBlockColumn,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement6,DirectUI::FrameworkElementGenerated>,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spSecondPickerHost.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpFirstTextBlockColumn,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->m_pDataContextChangedSource,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spThirdPickerHost.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpFirstTextBlockColumn,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->Windows::UI::Xaml::Controls::IControl,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spFirstTextBlockColumn.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpFirstTextBlockColumn,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->ctl::forwarder_holder<Windows::UI::Xaml::Controls::IControl2,DirectUI::ControlGenerated>,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spSecondTextBlockColumn.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpFirstTextBlockColumn,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->ctl::forwarder_holder<Windows::UI::Xaml::Controls::IControl5,DirectUI::ControlGenerated>,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spThirdTextBlockColumn.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpFirstTextBlockColumn,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)((char *)&this->DirectUI::Control + 520),
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spFirstColumnDivider.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpFirstTextBlockColumn,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->Windows::UI::Xaml::Controls::ITimePicker2,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spSecondColumnDivider.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpFirstTextBlockColumn,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IUIElement4,DirectUI::UIElementGenerated>,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spHourTextBlock.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpFirstTextBlockColumn,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IUIElementOverrides7,DirectUI::UIElementGenerated>,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spMinuteTextBlock.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpFirstTextBlockColumn,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IUIElement9,DirectUI::UIElementGenerated>,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spPeriodTextBlock.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpFirstTextBlockColumn,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->m_tpHourTextBlock,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spLayoutRoot.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpFirstTextBlockColumn,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->Windows::UI::Composition::IVisualElement,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spFlyoutButton.ptr_);
  updated = DirectUI::TimePicker::UpdateHeaderPresenterVisibility(v1);
  v6 = updated;
  if ( updated < 0
    || (WindowsDeleteString(strParentAutomationName._hstring),
        strParentAutomationName._hstring = 0,
        updated = DirectUI::DependencyObject::GetValueByKnownIndex(
                    v1,
                    AutomationProperties_Name,
                    &strParentAutomationName._hstring),
        v6 = updated,
        updated < 0) )
  {
LABEL_88:
    OnFailure_2990_(updated);
    goto $Cleanup_9016;
  }
  if ( !WindowsGetStringLen(strParentAutomationName._hstring) )
  {
    spHeaderAsInspectable.ptr_ = 0;
    Myhead = this->m_pM3Parents[3]._Mypair._Myval2._Myhead;
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spHeaderAsInspectable);
    StringFromObject = ((__int64 (__fastcall *)(std::list<CDependencyObject *> **, ctl::ComPtr<IInspectable> *))Myhead)(
                         &this->m_pM3Parents,
                         &spHeaderAsInspectable);
    v6 = StringFromObject;
    if ( StringFromObject < 0
      || spHeaderAsInspectable.ptr_
      && (WindowsDeleteString(strParentAutomationName._hstring),
          strParentAutomationName._hstring = 0,
          StringFromObject = DirectUI::FrameworkElement::GetStringFromObject(
                               spHeaderAsInspectable.ptr_,
                               &strParentAutomationName._hstring),
          v6 = StringFromObject,
          StringFromObject < 0) )
    {
      OnFailure_2990_(StringFromObject);
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spHeaderAsInspectable);
      goto $Cleanup_9016;
    }
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spHeaderAsInspectable);
    v11 = (IInspectable **)&this->Windows::UI::Composition::IVisualElement;
  }
  if ( this->m_tpMinuteTextBlock.m_trackerReference.m_value )
  {
    *(_QWORD *)&_Func = DirectUI::TimePicker::OnSelectorSelectionChanged;
    spHeaderAsInspectable.ptr_ = v1;
    DWORD2(_Func) = 0;
    v29 = std::bind<long (DirectUI::TimePicker::*)(IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *),DirectUI::TimePicker *,std::_Ph<1> const &,std::_Ph<2> const &>(
            (std::_Binder<std::_Unforced,long (__cdecl DirectUI::AutoSuggestBox::*)(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *),DirectUI::AutoSuggestBox *,std::_Ph<1> const &,std::_Ph<2> const &> *)result,
            &_Func,
            (DirectUI::AutoSuggestBox **)&spHeaderAsInspectable,
            v26,
            v48);
    v31 = *v30;
    v67._Mystorage._Ptrs[7] = 0;
    v67._Mystorage._Ptrs[0] = v32;
    *(_OWORD *)&v67._Mystorage._Ptrs[1] = v29->_Mypair._Myval1;
    LOWORD(v67._Mystorage._Ptrs[3]) = v29->_Mypair._Myval2.std::tuple<std::_Ph<1>,std::_Ph<2> >;
    v67._Mystorage._Ptrs[4] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *> *)v29->_Mypair._Myval2._Myfirst._Val;
    v67._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *> *)&v67;
    ValueByKnownIndex = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Controls::ISelectionChangedEventHandler,IInspectable,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs,DirectUI::SelectionChangedTraits>>::AttachEventHandler(
                          (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Controls::ISelectionChangedEventHandler,IInspectable,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs,DirectUI::SelectionChangedTraits> > *)&this->m_tpPeriodSource,
                          v31,
                          &v67);
    v6 = ValueByKnownIndex;
    if ( ValueByKnownIndex < 0 )
      goto LABEL_86;
    WindowsDeleteString(0);
    ValueByKnownIndex = DirectUI::DependencyObject::GetValueByKnownIndex(
                          (DirectUI::DependencyObject *)((__int64)&this->m_tpMinuteTextBlock.m_trackerReference.m_value[-117]
                                                       & -(__int64)(this->m_tpMinuteTextBlock.m_trackerReference.m_value != 0)),
                          AutomationProperties_Name,
                          &strAutomationName._hstring);
    v6 = ValueByKnownIndex;
    if ( ValueByKnownIndex < 0 )
      goto LABEL_86;
    hstring = strAutomationName._hstring;
    if ( !strAutomationName._hstring )
    {
      Current = DirectUI::DXamlCore::GetCurrent();
      WindowsDeleteString(0);
      strAutomationName._hstring = 0;
      ValueByKnownIndex = DirectUI::DXamlCore::GetLocalizedResourceString(Current, 0x1494u, &strAutomationName._hstring);
      v6 = ValueByKnownIndex;
      if ( ValueByKnownIndex < 0 )
        goto LABEL_86;
      ValueByKnownIndex = Windows::Internal::String::Concat(
                            &strAutomationName,
                            &strParentAutomationName,
                            &strComboAutomationName);
      v6 = ValueByKnownIndex;
      if ( ValueByKnownIndex < 0 )
        goto LABEL_86;
      ValueByKnownIndex = DirectUI::DependencyObject::SetValueByKnownIndex(
                            (DirectUI::DependencyObject *)((__int64)&this->m_tpMinuteTextBlock.m_trackerReference.m_value[-117]
                                                         & -(__int64)(this->m_tpMinuteTextBlock.m_trackerReference.m_value != 0)),
                            AutomationProperties_Name,
                            strComboAutomationName._hstring);
      v6 = ValueByKnownIndex;
      if ( ValueByKnownIndex < 0 )
        goto LABEL_86;
      hstring = strAutomationName._hstring;
    }
  }
  if ( p_m_tpPeriodTextBlock->m_trackerReference.m_value )
  {
    *(_QWORD *)&_Func = DirectUI::TimePicker::OnSelectorSelectionChanged;
    spHeaderAsInspectable.ptr_ = v1;
    DWORD2(_Func) = 0;
    v35 = std::bind<long (DirectUI::TimePicker::*)(IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *),DirectUI::TimePicker *,std::_Ph<1> const &,std::_Ph<2> const &>(
            (std::_Binder<std::_Unforced,long (__cdecl DirectUI::AutoSuggestBox::*)(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *),DirectUI::AutoSuggestBox *,std::_Ph<1> const &,std::_Ph<2> const &> *)result,
            &_Func,
            (DirectUI::AutoSuggestBox **)&spHeaderAsInspectable,
            v26,
            v48);
    v36 = (Windows::UI::Xaml::Controls::Primitives::ISelector *)p_m_tpPeriodTextBlock->m_trackerReference.m_value;
    v67._Mystorage._Ptrs[7] = 0;
    v67._Mystorage._Ptrs[0] = v37;
    *(_OWORD *)&v67._Mystorage._Ptrs[1] = v35->_Mypair._Myval1;
    LOWORD(v67._Mystorage._Ptrs[3]) = v35->_Mypair._Myval2.std::tuple<std::_Ph<1>,std::_Ph<2> >;
    v67._Mystorage._Ptrs[4] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *> *)v35->_Mypair._Myval2._Myfirst._Val;
    v67._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *> *)&v67;
    ValueByKnownIndex = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Controls::ISelectionChangedEventHandler,IInspectable,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs,DirectUI::SelectionChangedTraits>>::AttachEventHandler(
                          (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Controls::ISelectionChangedEventHandler,IInspectable,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs,DirectUI::SelectionChangedTraits> > *)&this->m_tpPeriodSource.m_trackerReference.8,
                          v36,
                          &v67);
    v6 = ValueByKnownIndex;
    if ( ValueByKnownIndex < 0 )
      goto LABEL_86;
    WindowsDeleteString(hstring);
    v38 = p_m_tpPeriodTextBlock->m_trackerReference.m_value;
    strAutomationName._hstring = 0;
    ValueByKnownIndex = DirectUI::DependencyObject::GetValueByKnownIndex(
                          (DirectUI::DependencyObject *)((unsigned __int64)&v38[-117] & -(__int64)(v38 != 0)),
                          AutomationProperties_Name,
                          &strAutomationName._hstring);
    v6 = ValueByKnownIndex;
    if ( ValueByKnownIndex < 0 )
      goto LABEL_86;
    hstring = strAutomationName._hstring;
    if ( !strAutomationName._hstring )
    {
      v39 = DirectUI::DXamlCore::GetCurrent();
      WindowsDeleteString(0);
      strAutomationName._hstring = 0;
      ValueByKnownIndex = DirectUI::DXamlCore::GetLocalizedResourceString(v39, 0x1495u, &strAutomationName._hstring);
      v6 = ValueByKnownIndex;
      if ( ValueByKnownIndex < 0
        || (ValueByKnownIndex = Windows::Internal::String::Concat(
                                  &strAutomationName,
                                  &strParentAutomationName,
                                  &strComboAutomationName),
            v6 = ValueByKnownIndex,
            ValueByKnownIndex < 0)
        || (ValueByKnownIndex = DirectUI::DependencyObject::SetValueByKnownIndex(
                                  (DirectUI::DependencyObject *)((__int64)&p_m_tpPeriodTextBlock->m_trackerReference.m_value[-117]
                                                               & -(__int64)(p_m_tpPeriodTextBlock->m_trackerReference.m_value != 0)),
                                  AutomationProperties_Name,
                                  strComboAutomationName._hstring),
            v6 = ValueByKnownIndex,
            ValueByKnownIndex < 0) )
      {
LABEL_86:
        OnFailure_2990_(ValueByKnownIndex);
        goto $Cleanup_9016;
      }
      hstring = strAutomationName._hstring;
    }
  }
  if ( p_m_tpHourSource->m_trackerReference.m_value )
  {
    spHeaderAsInspectable.ptr_ = v1;
    *(_QWORD *)&_Func = DirectUI::TimePicker::OnSelectorSelectionChanged;
    DWORD2(_Func) = 0;
    v40 = std::bind<long (DirectUI::TimePicker::*)(IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *),DirectUI::TimePicker *,std::_Ph<1> const &,std::_Ph<2> const &>(
            (std::_Binder<std::_Unforced,long (__cdecl DirectUI::AutoSuggestBox::*)(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *),DirectUI::AutoSuggestBox *,std::_Ph<1> const &,std::_Ph<2> const &> *)result,
            &_Func,
            (DirectUI::AutoSuggestBox **)&spHeaderAsInspectable,
            v26,
            v48);
    v41 = (Windows::UI::Xaml::Controls::Primitives::ISelector *)p_m_tpHourSource->m_trackerReference.m_value;
    v67._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *> *)std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (DirectUI::TimePicker::*)(IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *),DirectUI::TimePicker *,std::_Ph<1> const &,std::_Ph<2> const &>,long,IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *>::`vftable';
    v67._Mystorage._Ptrs[7] = 0;
    *(_OWORD *)&v67._Mystorage._Ptrs[1] = v40->_Mypair._Myval1;
    LOWORD(v67._Mystorage._Ptrs[3]) = v40->_Mypair._Myval2.std::tuple<std::_Ph<1>,std::_Ph<2> >;
    v67._Mystorage._Ptrs[4] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *> *)v40->_Mypair._Myval2._Myfirst._Val;
    v67._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *> *)&v67;
    ValueByKnownIndex = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Controls::ISelectionChangedEventHandler,IInspectable,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs,DirectUI::SelectionChangedTraits>>::AttachEventHandler(
                          (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Controls::ISelectionChangedEventHandler,IInspectable,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs,DirectUI::SelectionChangedTraits> > *)&this->m_tpPeriodSource.m_trackerReference
                        + 2,
                          v41,
                          &v67);
    v6 = ValueByKnownIndex;
    if ( ValueByKnownIndex < 0 )
      goto LABEL_86;
    WindowsDeleteString(hstring);
    v42 = p_m_tpHourSource->m_trackerReference.m_value;
    strAutomationName._hstring = 0;
    ValueByKnownIndex = DirectUI::DependencyObject::GetValueByKnownIndex(
                          (DirectUI::DependencyObject *)((unsigned __int64)&v42[-117] & -(__int64)(v42 != 0)),
                          AutomationProperties_Name,
                          &strAutomationName._hstring);
    v6 = ValueByKnownIndex;
    if ( ValueByKnownIndex < 0 )
      goto LABEL_86;
    if ( !strAutomationName._hstring )
    {
      v43 = DirectUI::DXamlCore::GetCurrent();
      WindowsDeleteString(0);
      strAutomationName._hstring = 0;
      ValueByKnownIndex = DirectUI::DXamlCore::GetLocalizedResourceString(v43, 0x1496u, &strAutomationName._hstring);
      v6 = ValueByKnownIndex;
      if ( ValueByKnownIndex < 0 )
        goto LABEL_86;
      ValueByKnownIndex = Windows::Internal::String::Concat(
                            &strAutomationName,
                            &strParentAutomationName,
                            &strComboAutomationName);
      v6 = ValueByKnownIndex;
      if ( ValueByKnownIndex < 0 )
        goto LABEL_86;
      ValueByKnownIndex = DirectUI::DependencyObject::SetValueByKnownIndex(
                            (DirectUI::DependencyObject *)((__int64)&p_m_tpHourSource->m_trackerReference.m_value[-117]
                                                         & -(__int64)(p_m_tpHourSource->m_trackerReference.m_value != 0)),
                            AutomationProperties_Name,
                            strComboAutomationName._hstring);
      v6 = ValueByKnownIndex;
      if ( ValueByKnownIndex < 0 )
        goto LABEL_86;
    }
  }
  ValueByKnownIndex = DirectUI::TimePicker::RefreshSetup(v1);
  v6 = ValueByKnownIndex;
  if ( ValueByKnownIndex < 0 )
    goto LABEL_86;
  if ( *v11 )
  {
    if ( !CQuirksMode2::XamlQuirkIsEnabled(0x200F2u) )
    {
      if ( IsXamlControlsCalculateFlyoutPlacementPresent() )
      {
        spHeaderAsInspectable.ptr_ = v1;
        *(_QWORD *)&_Func = DirectUI::TimePicker::OnFlyoutButtonClick;
        DWORD2(_Func) = 0;
        std::tuple<DirectUI::SplitView *,std::_Ph<1>,std::_Ph<2>>::tuple<DirectUI::SplitView *,std::_Ph<1>,std::_Ph<2>>(
          &v50,
          (DirectUI::SplitView **)&spHeaderAsInspectable,
          v44,
          v45);
        v46 = (Windows::UI::Xaml::Controls::Primitives::IButtonBase *)*v11;
        *(_OWORD *)&result[0]._Mystorage._Ptrs[1] = _Func;
        LOWORD(result[0]._Mystorage._Ptrs[3]) = v50.std::tuple<std::_Ph<1>,std::_Ph<2> >;
        result[0]._Mystorage._Ptrs[4] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)v50._Myfirst._Val;
        result[0]._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (DirectUI::TimePicker::*)(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *),DirectUI::TimePicker *,std::_Ph<1> const &,std::_Ph<2> const &>,long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *>::`vftable';
        result[0]._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)result;
        ValueByKnownIndex = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::ButtonBaseClickTraits>>::AttachEventHandler(
                              (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::ButtonBaseClickTraits> > *)&this->m_tpFirstPickerHost,
                              v46,
                              result);
        v6 = ValueByKnownIndex;
        if ( ValueByKnownIndex < 0 )
          goto LABEL_86;
      }
    }
    ValueByKnownIndex = DirectUI::TimePicker::RefreshFlyoutButtonAutomationName(v1);
    v6 = ValueByKnownIndex;
    if ( ValueByKnownIndex < 0 )
      goto LABEL_86;
    ValueByKnownIndex = DirectUI::TimePicker::UpdateFlyoutButtonContent(v1);
    v6 = ValueByKnownIndex;
    if ( ValueByKnownIndex < 0 )
      goto LABEL_86;
  }
  ValueByKnownIndex = DirectUI::Control::UpdateVisualState(v1, 0);
  v6 = ValueByKnownIndex;
  if ( ValueByKnownIndex < 0 )
    goto LABEL_86;
$Cleanup_9016:
  Windows::Internal::String::~String(&strComboAutomationName);
  Windows::Internal::String::~String(&strParentAutomationName);
  Windows::Internal::String::~String(&strAutomationName);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spSecondColumnDivider);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spFirstColumnDivider);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spThirdTextBlockColumn);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spSecondTextBlockColumn);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spFirstTextBlockColumn);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spPeriodTextBlock);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spMinuteTextBlock);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spHourTextBlock);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spFlyoutButton);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spLayoutRoot);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spThirdPickerHost);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spSecondPickerHost);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spFirstPickerHost);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spPeriodPicker);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spMinutePicker);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spHourPicker);
  return v6;
}

```

## disassembly

```asm
0x1809685f0  push    rbp
0x1809685f2  push    rbx
0x1809685f3  push    rsi
0x1809685f4  push    rdi
0x1809685f5  push    r12
0x1809685f7  push    r13
0x1809685f9  push    r14
0x1809685fb  push    r15
0x1809685fd  lea     rbp, [rsp-58h]
0x180968602  sub     rsp, 158h
0x180968609  xor     esi, esi
0x18096860b  lea     r14, [this-168h]
0x180968612  mov     rdx, [r14+3D0h]; pSource
0x180968619  mov     ebx, esi
0x18096861b  mov     [rbp+90h+spHourPicker.ptr_], rsi
0x18096861f  mov     r15, this
0x180968622  mov     [rbp+90h+spMinutePicker.ptr_], rsi
0x180968626  mov     [rbp+90h+spPeriodPicker.ptr_], rsi
0x18096862a  mov     [rbp+90h+spFirstPickerHost.ptr_], rsi
0x18096862e  mov     [rbp+90h+spSecondPickerHost.ptr_], rsi
0x180968632  mov     [rbp+90h+spThirdPickerHost.ptr_], rsi
0x180968636  mov     [rbp+90h+spLayoutRoot.ptr_], rsi
0x18096863a  mov     [rbp+90h+spFlyoutButton.ptr_], rsi
0x18096863e  mov     [rbp+90h+spHourTextBlock.ptr_], rsi
0x180968642  mov     [rbp+90h+spMinuteTextBlock.ptr_], rsi
0x180968646  mov     [rsp+190h+spPeriodTextBlock.ptr_], rsi
0x18096864b  mov     [rsp+190h+spFirstTextBlockColumn.ptr_], rsi
0x180968650  mov     [rsp+190h+spSecondTextBlockColumn.ptr_], rsi
0x180968655  mov     [rsp+190h+spThirdTextBlockColumn.ptr_], rsi
0x18096865a  mov     [rsp+190h+spFirstColumnDivider.ptr_], rsi
0x18096865f  mov     [rsp+190h+spSecondColumnDivider.ptr_], rsi
0x180968664  mov     [rbp+90h+strAutomationName._hstring], rbx
0x18096866b  mov     [rbp+90h+strParentAutomationName._hstring], rsi
0x180968672  mov     [rbp+90h+strComboAutomationName._hstring], rsi
0x180968679  test    rdx, rdx
0x18096867c  jz      short loc_18096869C
0x18096867e  add     this, 2C8h; this
0x180968685  call    ?DetachEventHandler@?$EventPtrBase@V?$event_handler@U?$ITypedEventHandler@PEAVHandwritingView@Controls@Xaml@UI@Windows@@PEAVHandwritingPanelClosedEventArgs@2345@@Foundation@Windows@@UIHandwritingView@Controls@Xaml@UI@3@UIHandwritingPanelClosedEventArgs@5673@UHandwritingViewClosedTraits@DirectUI@@@ctl@@@ctl@@QEAAJPEAUIInspectable@@@Z; ctl::EventPtrBase<ctl::event_handler<Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::HandwritingView *,Windows::UI::Xaml::Controls::HandwritingPanelClosedEventArgs *>,Windows::UI::Xaml::Controls::IHandwritingView,Windows::UI::Xaml::Controls::IHandwritingPanelClosedEventArgs,DirectUI::HandwritingViewClosedTraits>>::DetachEventHandler(IInspectable *)
0x18096868a  mov     edi, eax
0x18096868c  test    eax, eax
0x18096868e  jns     short loc_18096869C
0x180968690  mov     ecx, eax; failedFrameHR
0x180968692  call    OnFailure_2990_
0x180968697  jmp     $Cleanup_9016
0x18096869c  lea     r12, [r15+280h]
0x1809686a3  mov     rdx, [r12]; pSource
0x1809686a7  test    rdx, rdx
0x1809686aa  jz      short loc_1809686CA
0x1809686ac  lea     this, [r15+2D0h]; this
0x1809686b3  call    ?DetachEventHandler@?$EventPtrBase@V?$event_handler@U?$ITypedEventHandler@PEAVHandwritingView@Controls@Xaml@UI@Windows@@PEAVHandwritingPanelClosedEventArgs@2345@@Foundation@Windows@@UIHandwritingView@Controls@Xaml@UI@3@UIHandwritingPanelClosedEventArgs@5673@UHandwritingViewClosedTraits@DirectUI@@@ctl@@@ctl@@QEAAJPEAUIInspectable@@@Z; ctl::EventPtrBase<ctl::event_handler<Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::HandwritingView *,Windows::UI::Xaml::Controls::HandwritingPanelClosedEventArgs *>,Windows::UI::Xaml::Controls::IHandwritingView,Windows::UI::Xaml::Controls::IHandwritingPanelClosedEventArgs,DirectUI::HandwritingViewClosedTraits>>::DetachEventHandler(IInspectable *)
0x1809686b8  mov     edi, eax
0x1809686ba  test    eax, eax
0x1809686bc  jns     short loc_1809686CA
0x1809686be  mov     ecx, eax; failedFrameHR
0x1809686c0  call    OnFailure_2990_
0x1809686c5  jmp     $Cleanup_9016
0x1809686ca  lea     r13, [r15+298h]
0x1809686d1  mov     rdx, [r13+0]; pSource
0x1809686d5  test    rdx, rdx
0x1809686d8  jz      short loc_1809686F8
0x1809686da  lea     this, [r15+2D8h]; this
0x1809686e1  call    ?DetachEventHandler@?$EventPtrBase@V?$event_handler@U?$ITypedEventHandler@PEAVHandwritingView@Controls@Xaml@UI@Windows@@PEAVHandwritingPanelClosedEventArgs@2345@@Foundation@Windows@@UIHandwritingView@Controls@Xaml@UI@3@UIHandwritingPanelClosedEventArgs@5673@UHandwritingViewClosedTraits@DirectUI@@@ctl@@@ctl@@QEAAJPEAUIInspectable@@@Z; ctl::EventPtrBase<ctl::event_handler<Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::HandwritingView *,Windows::UI::Xaml::Controls::HandwritingPanelClosedEventArgs *>,Windows::UI::Xaml::Controls::IHandwritingView,Windows::UI::Xaml::Controls::IHandwritingPanelClosedEventArgs,DirectUI::HandwritingViewClosedTraits>>::DetachEventHandler(IInspectable *)
0x1809686e6  mov     edi, eax
0x1809686e8  test    eax, eax
0x1809686ea  jns     short loc_1809686F8
0x1809686ec  mov     ecx, eax; failedFrameHR
0x1809686ee  call    OnFailure_2990_
0x1809686f3  jmp     $Cleanup_9016
0x1809686f8  lea     rsi, [r15+0D0h]
0x1809686ff  cmp     [rsi], rbx
0x180968702  jz      short loc_18096873C
0x180968704  mov     ecx, 200F2h; quirk
0x180968709  call    ?XamlQuirkIsEnabled@CQuirksMode2@@SA_NK@Z; CQuirksMode2::XamlQuirkIsEnabled(ulong)
0x18096870e  test    al, al
0x180968710  jnz     short loc_18096873C
0x180968712  call    IsXamlControlsCalculateFlyoutPlacementPresent
0x180968717  test    al, al
0x180968719  jz      short loc_18096873C
0x18096871b  mov     rdx, [rsi]; pSource
0x18096871e  lea     this, [r15+2E0h]; this
0x180968725  call    ?DetachEventHandler@?$EventPtrBase@V?$event_handler@U?$ITypedEventHandler@PEAVHandwritingView@Controls@Xaml@UI@Windows@@PEAVHandwritingPanelClosedEventArgs@2345@@Foundation@Windows@@UIHandwritingView@Controls@Xaml@UI@3@UIHandwritingPanelClosedEventArgs@5673@UHandwritingViewClosedTraits@DirectUI@@@ctl@@@ctl@@QEAAJPEAUIInspectable@@@Z; ctl::EventPtrBase<ctl::event_handler<Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::HandwritingView *,Windows::UI::Xaml::Controls::HandwritingPanelClosedEventArgs *>,Windows::UI::Xaml::Controls::IHandwritingView,Windows::UI::Xaml::Controls::IHandwritingPanelClosedEventArgs,DirectUI::HandwritingViewClosedTraits>>::DetachEventHandler(IInspectable *)
0x18096872a  mov     edi, eax
0x18096872c  test    eax, eax
0x18096872e  jns     short loc_18096873C
0x180968730  mov     ecx, eax; failedFrameHR
0x180968732  call    OnFailure_2990_
0x180968737  jmp     $Cleanup_9016
0x18096873c  lea     this, [r15+268h]; this
0x180968743  xor     r8d, r8d; bForceLoopback
0x180968746  mov     dl, 1; bEnsureTrackerTarget
0x180968748  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18096874d  xor     r8d, r8d; bForceLoopback
0x180968750  mov     dl, 1; bEnsureTrackerTarget
0x180968752  mov     this, r12; this
0x180968755  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18096875a  xor     r8d, r8d; bForceLoopback
0x18096875d  mov     dl, 1; bEnsureTrackerTarget
0x18096875f  mov     this, r13; this
0x180968762  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x180968767  lea     this, [r15+178h]; this
0x18096876e  xor     r8d, r8d; bForceLoopback
0x180968771  mov     dl, 1; bEnsureTrackerTarget
0x180968773  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x180968778  lea     this, [r15+190h]; this
0x18096877f  xor     r8d, r8d; bForceLoopback
0x180968782  mov     dl, 1; bEnsureTrackerTarget
0x180968784  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x180968789  lea     this, [r15+1A8h]; this
0x180968790  xor     r8d, r8d; bForceLoopback
0x180968793  mov     dl, 1; bEnsureTrackerTarget
0x180968795  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18096879a  lea     this, [r15+1C0h]; this
0x1809687a1  xor     r8d, r8d; bForceLoopback
0x1809687a4  mov     dl, 1; bEnsureTrackerTarget
0x1809687a6  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x1809687ab  lea     this, [r15+1D8h]; this
0x1809687b2  xor     r8d, r8d; bForceLoopback
0x1809687b5  mov     dl, 1; bEnsureTrackerTarget
0x1809687b7  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x1809687bc  lea     this, [r15+1F0h]; this
0x1809687c3  xor     r8d, r8d; bForceLoopback
0x1809687c6  mov     dl, 1; bEnsureTrackerTarget
0x1809687c8  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x1809687cd  lea     this, [r15+208h]; this
0x1809687d4  xor     r8d, r8d; bForceLoopback
0x1809687d7  mov     dl, 1; bEnsureTrackerTarget
0x1809687d9  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x1809687de  lea     this, [r15+220h]; this
0x1809687e5  xor     r8d, r8d; bForceLoopback
0x1809687e8  mov     dl, 1; bEnsureTrackerTarget
0x1809687ea  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x1809687ef  lea     this, [r15+238h]; this
0x1809687f6  xor     r8d, r8d; bForceLoopback
0x1809687f9  mov     dl, 1; bEnsureTrackerTarget
0x1809687fb  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x180968800  lea     this, [r15+250h]; this
0x180968807  xor     r8d, r8d; bForceLoopback
0x18096880a  mov     dl, 1; bEnsureTrackerTarget
0x18096880c  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x180968811  xor     r8d, r8d; bForceLoopback
0x180968814  mov     dl, 1; bEnsureTrackerTarget
0x180968816  mov     this, rsi; this
0x180968819  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18096881e  lea     this, [r15+0E8h]; this
0x180968825  xor     r8d, r8d; bForceLoopback
0x180968828  mov     dl, 1; bEnsureTrackerTarget
0x18096882a  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18096882f  lea     this, [r15+100h]; this
0x180968836  xor     r8d, r8d; bForceLoopback
0x180968839  mov     dl, 1; bEnsureTrackerTarget
0x18096883b  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x180968840  lea     this, [r15+118h]; this
0x180968847  xor     r8d, r8d; bForceLoopback
0x18096884a  mov     dl, 1; bEnsureTrackerTarget
0x18096884c  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x180968851  mov     this, r15; this
0x180968854  call    ?OnApplyTemplate@Control@DirectUI@@UEAAJXZ; DirectUI::Control::OnApplyTemplate(void)
0x180968859  mov     edi, eax
0x18096885b  test    eax, eax
0x18096885d  js      loc_18096943C
0x180968863  lea     this, [rbp+90h+spHourPicker]; this
0x180968867  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18096886c  lea     r9, [rbp+90h+spHourPicker]; ppReference
0x180968870  mov     r8d, 0Ah; cName
0x180968876  lea     rdx, aHourpicker; "HourPicker"
0x18096887d  mov     this, r14; this
0x180968880  call    ??$GetTemplatePart@UISelector@Primitives@Controls@Xaml@UI@Windows@@U123456@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUISelector@Primitives@Controls@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::Primitives::ISelector,Windows::UI::Xaml::Controls::Primitives::ISelector>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::Primitives::ISelector * *)
0x180968885  mov     edi, eax
0x180968887  test    eax, eax
0x180968889  js      loc_180969433
0x18096888f  lea     this, [rbp+90h+spMinutePicker]; this
0x180968893  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180968898  lea     r9, [rbp+90h+spMinutePicker]; ppReference
0x18096889c  mov     r8d, 0Ch; cName
0x1809688a2  lea     rdx, aMinutepicker; "MinutePicker"
0x1809688a9  mov     this, r14; this
0x1809688ac  call    ??$GetTemplatePart@UISelector@Primitives@Controls@Xaml@UI@Windows@@U123456@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUISelector@Primitives@Controls@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::Primitives::ISelector,Windows::UI::Xaml::Controls::Primitives::ISelector>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::Primitives::ISelector * *)
0x1809688b1  mov     edi, eax
0x1809688b3  test    eax, eax
0x1809688b5  js      loc_18096942A
0x1809688bb  lea     this, [rbp+90h+spPeriodPicker]; this
0x1809688bf  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1809688c4  lea     r9, [rbp+90h+spPeriodPicker]; ppReference
0x1809688c8  mov     r8d, 0Ch; cName
0x1809688ce  lea     rdx, aPeriodpicker; "PeriodPicker"
0x1809688d5  mov     this, r14; this
0x1809688d8  call    ??$GetTemplatePart@UISelector@Primitives@Controls@Xaml@UI@Windows@@U123456@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUISelector@Primitives@Controls@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::Primitives::ISelector,Windows::UI::Xaml::Controls::Primitives::ISelector>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::Primitives::ISelector * *)
0x1809688dd  mov     edi, eax
0x1809688df  test    eax, eax
0x1809688e1  js      loc_180969421
0x1809688e7  lea     this, [rbp+90h+spFirstPickerHost]; this
0x1809688eb  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1809688f0  lea     r9, [rbp+90h+spFirstPickerHost]; ppReference
0x1809688f4  mov     r8d, 0Fh; cName
0x1809688fa  lea     rdx, aFirstpickerhos; "FirstPickerHost"
0x180968901  mov     this, r14; this
0x180968904  call    ??$GetTemplatePart@UIBorder@Controls@Xaml@UI@Windows@@U12345@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUIBorder@Controls@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IBorder,Windows::UI::Xaml::Controls::IBorder>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::IBorder * *)
0x180968909  mov     edi, eax
0x18096890b  test    eax, eax
0x18096890d  js      loc_180969418
0x180968913  lea     this, [rbp+90h+spSecondPickerHost]; this
0x180968917  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18096891c  lea     r9, [rbp+90h+spSecondPickerHost]; ppReference
0x180968920  mov     r8d, 10h; cName
0x180968926  lea     rdx, aSecondpickerho; "SecondPickerHost"
0x18096892d  mov     this, r14; this
0x180968930  call    ??$GetTemplatePart@UIBorder@Controls@Xaml@UI@Windows@@U12345@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUIBorder@Controls@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IBorder,Windows::UI::Xaml::Controls::IBorder>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::IBorder * *)
0x180968935  mov     edi, eax
0x180968937  test    eax, eax
0x180968939  js      loc_18096940F
0x18096893f  lea     this, [rbp+90h+spThirdPickerHost]; this
0x180968943  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180968948  lea     r9, [rbp+90h+spThirdPickerHost]; ppReference
0x18096894c  mov     r8d, 0Fh; cName
0x180968952  lea     rdx, aThirdpickerhos; "ThirdPickerHost"
0x180968959  mov     this, r14; this
0x18096895c  call    ??$GetTemplatePart@UIBorder@Controls@Xaml@UI@Windows@@U12345@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUIBorder@Controls@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IBorder,Windows::UI::Xaml::Controls::IBorder>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::IBorder * *)
0x180968961  mov     edi, eax
0x180968963  test    eax, eax
0x180968965  js      loc_180969406
0x18096896b  lea     this, [rbp+90h+spHourTextBlock]; this
0x18096896f  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180968974  lea     r9, [rbp+90h+spHourTextBlock]; ppReference
0x180968978  mov     r8d, 0Dh; cName
0x18096897e  lea     rdx, aHourtextblock; "HourTextBlock"
0x180968985  mov     this, r14; this
0x180968988  call    ??$GetTemplatePart@UITextBlock@Controls@Xaml@UI@Windows@@U12345@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUITextBlock@Controls@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::ITextBlock,Windows::UI::Xaml::Controls::ITextBlock>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::ITextBlock * *)
0x18096898d  mov     edi, eax
0x18096898f  test    eax, eax
0x180968991  js      loc_1809693FD
0x180968997  lea     this, [rbp+90h+spMinuteTextBlock]; this
0x18096899b  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1809689a0  lea     r9, [rbp+90h+spMinuteTextBlock]; ppReference
0x1809689a4  mov     r8d, 0Fh; cName
0x1809689aa  lea     rdx, aMinutetextbloc; "MinuteTextBlock"
0x1809689b1  mov     this, r14; this
0x1809689b4  call    ??$GetTemplatePart@UITextBlock@Controls@Xaml@UI@Windows@@U12345@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUITextBlock@Controls@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::ITextBlock,Windows::UI::Xaml::Controls::ITextBlock>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::ITextBlock * *)
0x1809689b9  mov     edi, eax
0x1809689bb  test    eax, eax
0x1809689bd  js      loc_1809693F4
0x1809689c3  lea     this, [rsp+190h+spPeriodTextBlock]; this
0x1809689c8  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1809689cd  lea     r9, [rsp+190h+spPeriodTextBlock]; ppReference
0x1809689d2  mov     r8d, 0Fh; cName
0x1809689d8  lea     rdx, aPeriodtextbloc; "PeriodTextBlock"
0x1809689df  mov     this, r14; this
0x1809689e2  call    ??$GetTemplatePart@UITextBlock@Controls@Xaml@UI@Windows@@U12345@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUITextBlock@Controls@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::ITextBlock,Windows::UI::Xaml::Controls::ITextBlock>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::ITextBlock * *)
0x1809689e7  mov     edi, eax
0x1809689e9  test    eax, eax
0x1809689eb  js      loc_1809693EB
0x1809689f1  lea     this, [rsp+190h+spFirstTextBlockColumn]; this
0x1809689f6  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1809689fb  lea     r9, [rsp+190h+spFirstTextBlockColumn]; ppReference
0x180968a00  mov     r8d, 14h; cName
0x180968a06  lea     rdx, aFirsttextblock; "FirstTextBlockColumn"
0x180968a0d  mov     this, r14; this
0x180968a10  call    ??$GetTemplatePart@UIColumnDefinition@Controls@Xaml@UI@Windows@@U12345@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUIColumnDefinition@Controls@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IColumnDefinition,Windows::UI::Xaml::Controls::IColumnDefinition>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::IColumnDefinition * *)
0x180968a15  mov     edi, eax
0x180968a17  test    eax, eax
0x180968a19  js      loc_1809693E2
0x180968a1f  lea     this, [rsp+190h+spSecondTextBlockColumn]; this
0x180968a24  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180968a29  lea     r9, [rsp+190h+spSecondTextBlockColumn]; ppReference
0x180968a2e  mov     r8d, 15h; cName
0x180968a34  lea     rdx, aSecondtextbloc; "SecondTextBlockColumn"
0x180968a3b  mov     this, r14; this
0x180968a3e  call    ??$GetTemplatePart@UIColumnDefinition@Controls@Xaml@UI@Windows@@U12345@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUIColumnDefinition@Controls@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IColumnDefinition,Windows::UI::Xaml::Controls::IColumnDefinition>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::IColumnDefinition * *)
0x180968a43  mov     edi, eax
0x180968a45  test    eax, eax
0x180968a47  js      loc_1809693D9
0x180968a4d  lea     this, [rsp+190h+spThirdTextBlockColumn]; this
0x180968a52  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180968a57  lea     r9, [rsp+190h+spThirdTextBlockColumn]; ppReference
0x180968a5c  mov     r8d, 14h; cName
0x180968a62  lea     rdx, aThirdtextblock; "ThirdTextBlockColumn"
0x180968a69  mov     this, r14; this
0x180968a6c  call    ??$GetTemplatePart@UIColumnDefinition@Controls@Xaml@UI@Windows@@U12345@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUIColumnDefinition@Controls@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IColumnDefinition,Windows::UI::Xaml::Controls::IColumnDefinition>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::IColumnDefinition * *)
0x180968a71  mov     edi, eax
0x180968a73  test    eax, eax
0x180968a75  js      loc_1809693D0
0x180968a7b  lea     this, [rsp+190h+spFirstColumnDivider]; this
0x180968a80  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180968a85  lea     r9, [rsp+190h+spFirstColumnDivider]; ppReference
0x180968a8a  mov     r8d, 12h; cName
0x180968a90  lea     rdx, aFirstcolumndiv; "FirstColumnDivider"
0x180968a97  mov     this, r14; this
0x180968a9a  call    ??$GetTemplatePart@UIUIElement@Xaml@UI@Windows@@U1234@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUIUIElement@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::IUIElement,Windows::UI::Xaml::IUIElement>(ushort *,unsigned __int64,Windows::UI::Xaml::IUIElement * *)
0x180968a9f  mov     edi, eax
0x180968aa1  test    eax, eax
0x180968aa3  js      loc_1809693C7
0x180968aa9  lea     this, [rsp+190h+spSecondColumnDivider]; this
0x180968aae  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180968ab3  lea     r9, [rsp+190h+spSecondColumnDivider]; ppReference
0x180968ab8  mov     r8d, 13h; cName
0x180968abe  lea     rdx, aSecondcolumndi; "SecondColumnDivider"
0x180968ac5  mov     this, r14; this
0x180968ac8  call    ??$GetTemplatePart@UIUIElement@Xaml@UI@Windows@@U1234@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUIUIElement@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::IUIElement,Windows::UI::Xaml::IUIElement>(ushort *,unsigned __int64,Windows::UI::Xaml::IUIElement * *)
0x180968acd  mov     edi, eax
0x180968acf  test    eax, eax
0x180968ad1  js      loc_1809693BE
  ... truncated ...
```
