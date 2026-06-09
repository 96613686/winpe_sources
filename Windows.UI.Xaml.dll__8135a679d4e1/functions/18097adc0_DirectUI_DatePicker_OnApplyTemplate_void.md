# DirectUI::DatePicker::OnApplyTemplate(void)

- ea: `0x18097adc0`
- end: `0x18097beed`
- name: `?OnApplyTemplate@DatePicker@DirectUI@@MEAAJXZ`
- size: `4397`
- prototype: `HRESULT __fastcall(DirectUI::DatePicker *this)`
- caller_count: `0`
- callee_count: `36`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x180059c30`
- `0x18005bcac`
- `0x18005e96c`
- `0x18009a16c`
- `0x18009ab94`
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
- `0x18037f708`
- `0x1803805dc`
- `0x1803839c0`
- `0x180383ffc`
- `0x180384f48`
- `0x180429a2c`
- `0x18066dd50`
- `0x1806e18f0`
- `0x1806e7e00`
- `0x180772d6c`
- `0x180965c94`
- `0x180965d9c`
- `0x18097adc0`
- `0x18097d150`
- `0x18097d3dc`
- `0x18097e1dc`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18097b530`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18097b5bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18097b698`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18097b6ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18097b831`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18097b88b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18097b9e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18097ba3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18097b530`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18097b5bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18097b698`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18097b6ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18097b831`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18097b88b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18097b9e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18097ba3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18097b562`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18097b562`

## pseudocode

```c
__int64 __fastcall DirectUI::DatePicker::OnApplyTemplate(DirectUI::DatePicker *this)
{
  DirectUI::DatePicker *v1; // r14
  IInspectable *v2; // rdx
  HSTRING__ *hstring; // rbx
  HRESULT v5; // eax
  unsigned int v6; // edi
  ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement4,DirectUI::FrameworkElementGenerated> *v7; // r12
  IInspectable *v8; // rdx
  ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElementProtected7,DirectUI::FrameworkElementGenerated> *v9; // r13
  IInspectable *v10; // rdx
  HRESULT v11; // eax
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
  HRESULT updated; // eax
  ctl::WeakReferenceSourceNoThreadId *v23; // rsi
  const std::_Ph<1> *v24; // r9
  std::_List_node<CDependencyObject *,void *> *Myhead; // rdi
  HRESULT StringFromObject; // eax
  std::_Binder<std::_Unforced,long (__cdecl DirectUI::AutoSuggestBox::*)(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *),DirectUI::AutoSuggestBox *,std::_Ph<1> const &,std::_Ph<2> const &> *v27; // rax
  Windows::UI::Xaml::Controls::Primitives::ISelector **v28; // r10
  Windows::UI::Xaml::Controls::Primitives::ISelector *v29; // rdx
  std::_Func_base<long,IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *> *v30; // r11
  HRESULT ValueByKnownIndex; // eax
  DirectUI::DXamlCore *Current; // rbx
  std::_Binder<std::_Unforced,long (__cdecl DirectUI::AutoSuggestBox::*)(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *),DirectUI::AutoSuggestBox *,std::_Ph<1> const &,std::_Ph<2> const &> *v33; // rax
  Windows::UI::Xaml::Controls::Primitives::ISelector *v34; // rdx
  std::_Func_base<long,IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *> *v35; // r11
  ctl::interface_forwarder<Windows::UI::Xaml::IFrameworkElement4,DirectUI::FrameworkElementGenerated>_vtbl *v36; // rcx
  DirectUI::DXamlCore *v37; // rbx
  std::_Binder<std::_Unforced,long (__cdecl DirectUI::AutoSuggestBox::*)(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *),DirectUI::AutoSuggestBox *,std::_Ph<1> const &,std::_Ph<2> const &> *v38; // rax
  Windows::UI::Xaml::Controls::Primitives::ISelector *v39; // rdx
  ctl::interface_forwarder<Windows::UI::Xaml::IFrameworkElementProtected7,DirectUI::FrameworkElementGenerated>_vtbl *v40; // rcx
  DirectUI::DXamlCore *v41; // rbx
  const std::_Ph<1> *v42; // r8
  const std::_Ph<2> *v43; // r9
  Windows::UI::Composition::IAnimationObject_vtbl *v44; // rdx
  HRESULT refreshed; // eax
  const std::_Ph<2> *v47; // [rsp+20h] [rbp-E0h]
  ctl::ComPtr<DirectUI::TrackerCollection<IInspectable *> > spCollection; // [rsp+30h] [rbp-D0h] BYREF
  __int128 _Func; // [rsp+38h] [rbp-C8h] BYREF
  std::tuple<DirectUI::SplitView *,std::_Ph<1>,std::_Ph<2> > v50; // [rsp+48h] [rbp-B8h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::IGrid> spFlyoutButtonContentGrid; // [rsp+58h] [rbp-A8h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::IColumnDefinition> spSecondSpacerColumn; // [rsp+60h] [rbp-A0h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::IColumnDefinition> spFirstSpacerColumn; // [rsp+68h] [rbp-98h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::IColumnDefinition> spYearColumn; // [rsp+70h] [rbp-90h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::IColumnDefinition> spMonthColumn; // [rsp+78h] [rbp-88h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::IColumnDefinition> spDayColumn; // [rsp+80h] [rbp-80h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::ITextBlock> spDayTextBlock; // [rsp+88h] [rbp-78h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::ITextBlock> spMonthTextBlock; // [rsp+90h] [rbp-70h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::ITextBlock> spYearTextBlock; // [rsp+98h] [rbp-68h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::IButtonBase> spFlyoutButton; // [rsp+A0h] [rbp-60h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IUIElement> spSpacingHolderTwo; // [rsp+A8h] [rbp-58h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IUIElement> spSpacingHolderOne; // [rsp+B0h] [rbp-50h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IFrameworkElement> spLayoutRoot; // [rsp+B8h] [rbp-48h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::IBorder> spThirdPickerHost; // [rsp+C0h] [rbp-40h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::IBorder> spSecondPickerHost; // [rsp+C8h] [rbp-38h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::IBorder> spFirstPickerHost; // [rsp+D0h] [rbp-30h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::ISelector> spYearPicker; // [rsp+D8h] [rbp-28h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::ISelector> spMonthPicker; // [rsp+E0h] [rbp-20h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::ISelector> spDayPicker; // [rsp+E8h] [rbp-18h] BYREF
  std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *)> v70; // [rsp+F0h] [rbp-10h] BYREF
  std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *)> result[2]; // [rsp+130h] [rbp+30h] BYREF
  Windows::Internal::String strAutomationName; // [rsp+1C0h] [rbp+C0h] BYREF
  Windows::Internal::String strParentAutomationName; // [rsp+1C8h] [rbp+C8h] BYREF
  ctl::ComPtr<IInspectable> spHeaderAsInspectable; // [rsp+1D0h] [rbp+D0h] BYREF
  Windows::Internal::String strComboAutomationName; // [rsp+1D8h] [rbp+D8h] BYREF

  v1 = (DirectUI::DatePicker *)((char *)this - 360);
  v2 = (IInspectable *)this->DirectUI::DatePickerGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement2,DirectUI::FrameworkElementGenerated>::m_forwarder.DirectUI::DatePickerGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement2,DirectUI::FrameworkElementGenerated>::__vftable;
  hstring = 0;
  spDayPicker.ptr_ = 0;
  spMonthPicker.ptr_ = 0;
  spYearPicker.ptr_ = 0;
  spFirstPickerHost.ptr_ = 0;
  spSecondPickerHost.ptr_ = 0;
  spThirdPickerHost.ptr_ = 0;
  spLayoutRoot.ptr_ = 0;
  spSpacingHolderOne.ptr_ = 0;
  spSpacingHolderTwo.ptr_ = 0;
  spFlyoutButton.ptr_ = 0;
  spYearTextBlock.ptr_ = 0;
  spMonthTextBlock.ptr_ = 0;
  spDayTextBlock.ptr_ = 0;
  spDayColumn.ptr_ = 0;
  spMonthColumn.ptr_ = 0;
  spYearColumn.ptr_ = 0;
  spFirstSpacerColumn.ptr_ = 0;
  spSecondSpacerColumn.ptr_ = 0;
  spFlyoutButtonContentGrid.ptr_ = 0;
  spCollection.ptr_ = 0;
  strAutomationName._hstring = 0;
  strParentAutomationName._hstring = 0;
  strComboAutomationName._hstring = 0;
  if ( v2 )
  {
    v5 = ctl::EventPtrBase<ctl::event_handler<Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::HandwritingView *,Windows::UI::Xaml::Controls::HandwritingPanelClosedEventArgs *>,Windows::UI::Xaml::Controls::IHandwritingView,Windows::UI::Xaml::Controls::IHandwritingPanelClosedEventArgs,DirectUI::HandwritingViewClosedTraits>>::DetachEventHandler(
           (ctl::EventPtrBase<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::UIElementGotFocusTraits> > *)&this->m_tpFirstSpacerColumn,
           v2);
    v6 = v5;
    if ( v5 < 0 )
      goto LABEL_116;
  }
  v7 = &this->ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement4,DirectUI::FrameworkElementGenerated>;
  v8 = (IInspectable *)this->DirectUI::DatePickerGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement4,DirectUI::FrameworkElementGenerated>::m_forwarder.DirectUI::DatePickerGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement4,DirectUI::FrameworkElementGenerated>::__vftable;
  if ( v8 )
  {
    v5 = ctl::EventPtrBase<ctl::event_handler<Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::HandwritingView *,Windows::UI::Xaml::Controls::HandwritingPanelClosedEventArgs *>,Windows::UI::Xaml::Controls::IHandwritingView,Windows::UI::Xaml::Controls::IHandwritingPanelClosedEventArgs,DirectUI::HandwritingViewClosedTraits>>::DetachEventHandler(
           (ctl::EventPtrBase<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::UIElementGotFocusTraits> > *)&this->m_tpFirstSpacerColumn.m_trackerReference.8,
           v8);
    v6 = v5;
    if ( v5 < 0 )
      goto LABEL_116;
  }
  v9 = &this->ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElementProtected7,DirectUI::FrameworkElementGenerated>;
  v10 = (IInspectable *)this->DirectUI::DatePickerGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElementProtected7,DirectUI::FrameworkElementGenerated>::m_forwarder.DirectUI::DatePickerGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElementProtected7,DirectUI::FrameworkElementGenerated>::__vftable;
  if ( v10 )
  {
    v5 = ctl::EventPtrBase<ctl::event_handler<Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::HandwritingView *,Windows::UI::Xaml::Controls::HandwritingPanelClosedEventArgs *>,Windows::UI::Xaml::Controls::IHandwritingView,Windows::UI::Xaml::Controls::IHandwritingPanelClosedEventArgs,DirectUI::HandwritingViewClosedTraits>>::DetachEventHandler(
           (ctl::EventPtrBase<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::UIElementGotFocusTraits> > *)&this->m_tpFirstSpacerColumn.m_trackerReference
         + 2,
           v10);
    v6 = v5;
    if ( v5 < 0 )
      goto LABEL_116;
  }
  if ( this->DirectUI::DatePickerGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::Windows::UI::Composition::IAnimationObject::IInspectable::IUnknown::__vftable )
  {
    if ( !CQuirksMode2::XamlQuirkIsEnabled(0x200F2u) )
    {
      if ( IsXamlControlsCalculateFlyoutPlacementPresent() )
      {
        v5 = ctl::EventPtrBase<ctl::event_handler<Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::HandwritingView *,Windows::UI::Xaml::Controls::HandwritingPanelClosedEventArgs *>,Windows::UI::Xaml::Controls::IHandwritingView,Windows::UI::Xaml::Controls::IHandwritingPanelClosedEventArgs,DirectUI::HandwritingViewClosedTraits>>::DetachEventHandler(
               (ctl::EventPtrBase<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::UIElementGotFocusTraits> > *)&this->m_tpSecondSpacerColumn,
               (IInspectable *)this->DirectUI::DatePickerGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::Windows::UI::Composition::IAnimationObject::IInspectable::IUnknown::__vftable);
        v6 = v5;
        if ( v5 < 0 )
          goto LABEL_116;
      }
    }
  }
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement2,DirectUI::FrameworkElementGenerated>,
    1u,
    0);
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement4,DirectUI::FrameworkElementGenerated>,
    1u,
    0);
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElementProtected7,DirectUI::FrameworkElementGenerated>,
    1u,
    0);
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->Windows::UI::Xaml::Controls::IControlOverrides,
    1u,
    0);
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->ctl::forwarder_holder<Windows::UI::Xaml::Controls::IControl4,DirectUI::ControlGenerated>,
    1u,
    0);
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->ctl::forwarder_holder<Windows::UI::Xaml::Controls::IControl7,DirectUI::ControlGenerated>,
    1u,
    0);
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->Windows::UI::Xaml::Controls::IDatePicker,
    1u,
    0);
  DirectUI::TrackerTargetReference::Clear(&this->m_tpFlyoutButton.m_trackerReference, 1u, 0);
  DirectUI::TrackerTargetReference::Clear(&this->m_tpYearTextBlock.m_trackerReference, 1u, 0);
  DirectUI::TrackerTargetReference::Clear(&this->m_tpMonthTextBlock.m_trackerReference, 1u, 0);
  DirectUI::TrackerTargetReference::Clear(&this->m_tpDayTextBlock.m_trackerReference, 1u, 0);
  DirectUI::TrackerTargetReference::Clear(&this->m_tpMonthSource.m_trackerReference, 1u, 0);
  DirectUI::TrackerTargetReference::Clear(&this->m_tpYearSource.m_trackerReference, 1u, 0);
  DirectUI::TrackerTargetReference::Clear(&this->m_tpDayPicker.m_trackerReference, 1u, 0);
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->m_pChainedGoToElementStateSourceControls,
    1u,
    0);
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->Windows::UI::Composition::IAnimationObject,
    1u,
    0);
  DirectUI::TrackerTargetReference::Clear(&this->m_tpDaySource.m_trackerReference, 1u, 0);
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IUIElement3,DirectUI::UIElementGenerated>,
    1u,
    0);
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IUIElement7,DirectUI::UIElementGenerated>,
    1u,
    0);
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IUIElementOverrides8,DirectUI::UIElementGenerated>,
    1u,
    0);
  v5 = DirectUI::Control::OnApplyTemplate(this);
  v6 = v5;
  if ( v5 < 0 )
  {
LABEL_116:
    OnFailure_2990_(v5);
    goto $Cleanup_9112;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDayPicker);
  v11 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::Primitives::ISelector,Windows::UI::Xaml::Controls::Primitives::ISelector>(
          v1,
          (wchar_t *)L"DayPicker",
          9u,
          &spDayPicker.ptr_);
  v6 = v11;
  if ( v11 < 0 )
  {
    OnFailure_2990_(v11);
    goto $Cleanup_9112;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spMonthPicker);
  v12 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::Primitives::ISelector,Windows::UI::Xaml::Controls::Primitives::ISelector>(
          v1,
          (wchar_t *)L"MonthPicker",
          0xBu,
          &spMonthPicker.ptr_);
  v6 = v12;
  if ( v12 < 0 )
  {
    OnFailure_2990_(v12);
    goto $Cleanup_9112;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spYearPicker);
  v13 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::Primitives::ISelector,Windows::UI::Xaml::Controls::Primitives::ISelector>(
          v1,
          (wchar_t *)L"YearPicker",
          0xAu,
          &spYearPicker.ptr_);
  v6 = v13;
  if ( v13 < 0 )
  {
    OnFailure_2990_(v13);
    goto $Cleanup_9112;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spFirstPickerHost);
  v14 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IBorder,Windows::UI::Xaml::Controls::IBorder>(
          v1,
          (wchar_t *)L"FirstPickerHost",
          0xFu,
          &spFirstPickerHost.ptr_);
  v6 = v14;
  if ( v14 < 0 )
  {
    OnFailure_2990_(v14);
    goto $Cleanup_9112;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spSecondPickerHost);
  v15 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IBorder,Windows::UI::Xaml::Controls::IBorder>(
          v1,
          (wchar_t *)L"SecondPickerHost",
          0x10u,
          &spSecondPickerHost.ptr_);
  v6 = v15;
  if ( v15 < 0 )
  {
    OnFailure_2990_(v15);
    goto $Cleanup_9112;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spThirdPickerHost);
  v16 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IBorder,Windows::UI::Xaml::Controls::IBorder>(
          v1,
          (wchar_t *)L"ThirdPickerHost",
          0xFu,
          &spThirdPickerHost.ptr_);
  v6 = v16;
  if ( v16 < 0 )
  {
    OnFailure_2990_(v16);
    goto $Cleanup_9112;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDayColumn);
  v17 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IColumnDefinition,Windows::UI::Xaml::Controls::IColumnDefinition>(
          v1,
          (wchar_t *)L"DayColumn",
          9u,
          &spDayColumn.ptr_);
  v6 = v17;
  if ( v17 < 0 )
  {
    OnFailure_2990_(v17);
    goto $Cleanup_9112;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spMonthColumn);
  v18 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IColumnDefinition,Windows::UI::Xaml::Controls::IColumnDefinition>(
          v1,
          (wchar_t *)L"MonthColumn",
          0xBu,
          &spMonthColumn.ptr_);
  v6 = v18;
  if ( v18 < 0 )
  {
    OnFailure_2990_(v18);
    goto $Cleanup_9112;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spYearColumn);
  v19 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IColumnDefinition,Windows::UI::Xaml::Controls::IColumnDefinition>(
          v1,
          (wchar_t *)L"YearColumn",
          0xAu,
          &spYearColumn.ptr_);
  v6 = v19;
  if ( v19 < 0 )
  {
    OnFailure_2990_(v19);
    goto $Cleanup_9112;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spFirstSpacerColumn);
  v20 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IColumnDefinition,Windows::UI::Xaml::Controls::IColumnDefinition>(
          v1,
          (wchar_t *)L"FirstSpacerColumn",
          0x11u,
          &spFirstSpacerColumn.ptr_);
  v6 = v20;
  if ( v20 < 0 )
  {
    OnFailure_2990_(v20);
    goto $Cleanup_9112;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spSecondSpacerColumn);
  v21 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IColumnDefinition,Windows::UI::Xaml::Controls::IColumnDefinition>(
          v1,
          (wchar_t *)L"SecondSpacerColumn",
          0x12u,
          &spSecondSpacerColumn.ptr_);
  v6 = v21;
  if ( v21 < 0 )
    goto LABEL_104;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spYearTextBlock);
  v21 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::ITextBlock,Windows::UI::Xaml::Controls::ITextBlock>(
          v1,
          (wchar_t *)L"YearTextBlock",
          0xDu,
          &spYearTextBlock.ptr_);
  v6 = v21;
  if ( v21 < 0
    || (ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spMonthTextBlock),
        v21 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::ITextBlock,Windows::UI::Xaml::Controls::ITextBlock>(
                v1,
                (wchar_t *)L"MonthTextBlock",
                0xEu,
                &spMonthTextBlock.ptr_),
        v6 = v21,
        v21 < 0)
    || (ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDayTextBlock),
        v21 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::ITextBlock,Windows::UI::Xaml::Controls::ITextBlock>(
                v1,
                (wchar_t *)L"DayTextBlock",
                0xCu,
                &spDayTextBlock.ptr_),
        v6 = v21,
        v21 < 0) )
  {
LABEL_104:
    OnFailure_2990_(v21);
    goto $Cleanup_9112;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spFlyoutButtonContentGrid);
  updated = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IGrid,Windows::UI::Xaml::Controls::IGrid>(
              v1,
              (wchar_t *)L"FlyoutButtonContentGrid",
              0x17u,
              &spFlyoutButtonContentGrid.ptr_);
  v6 = updated;
  if ( updated < 0 )
    goto LABEL_99;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spSpacingHolderOne);
  updated = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::IUIElement,Windows::UI::Xaml::IUIElement>(
              v1,
              (wchar_t *)L"FirstPickerSpacing",
              0x12u,
              &spSpacingHolderOne.ptr_);
  v6 = updated;
  if ( updated < 0 )
    goto LABEL_99;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spSpacingHolderTwo);
  updated = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::IUIElement,Windows::UI::Xaml::IUIElement>(
              v1,
              (wchar_t *)L"SecondPickerSpacing",
              0x13u,
              &spSpacingHolderTwo.ptr_);
  v6 = updated;
  if ( updated < 0 )
    goto LABEL_99;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spLayoutRoot);
  updated = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::IFrameworkElement,Windows::UI::Xaml::IFrameworkElement>(
              v1,
              (wchar_t *)L"LayoutRoot",
              0xAu,
              &spLayoutRoot.ptr_);
  v6 = updated;
  if ( updated < 0 )
    goto LABEL_99;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spFlyoutButton);
  updated = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::Primitives::IButtonBase,Windows::UI::Xaml::Controls::Primitives::IButtonBase>(
              v1,
              (wchar_t *)L"FlyoutButton",
              0xCu,
              &spFlyoutButton.ptr_);
  v6 = updated;
  if ( updated < 0 )
    goto LABEL_99;
  v23 = (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpSecondPickerSpacing.m_trackerReference.8;
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpSecondPickerSpacing.m_trackerReference.8,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement2,DirectUI::FrameworkElementGenerated>,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spDayPicker.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpSecondPickerSpacing.m_trackerReference.8,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement4,DirectUI::FrameworkElementGenerated>,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spMonthPicker.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpSecondPickerSpacing.m_trackerReference.8,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElementProtected7,DirectUI::FrameworkElementGenerated>,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spYearPicker.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpSecondPickerSpacing.m_trackerReference.8,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->m_tpMonthSource,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spSpacingHolderOne.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpSecondPickerSpacing.m_trackerReference.8,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->m_tpYearSource,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spSpacingHolderTwo.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpSecondPickerSpacing.m_trackerReference.8,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->Windows::UI::Xaml::Controls::IControlOverrides,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spFirstPickerHost.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpSecondPickerSpacing.m_trackerReference.8,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->ctl::forwarder_holder<Windows::UI::Xaml::Controls::IControl4,DirectUI::ControlGenerated>,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spSecondPickerHost.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpSecondPickerSpacing.m_trackerReference.8,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->ctl::forwarder_holder<Windows::UI::Xaml::Controls::IControl7,DirectUI::ControlGenerated>,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spThirdPickerHost.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpSecondPickerSpacing.m_trackerReference.8,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->Windows::UI::Xaml::Controls::IDatePicker,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spDayColumn.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpSecondPickerSpacing.m_trackerReference.8,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->m_tpFlyoutButton,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spMonthColumn.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpSecondPickerSpacing.m_trackerReference.8,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->m_tpYearTextBlock,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spYearColumn.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpSecondPickerSpacing.m_trackerReference.8,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->m_tpMonthTextBlock,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spFirstSpacerColumn.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpSecondPickerSpacing.m_trackerReference.8,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->m_tpDayTextBlock,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spSecondSpacerColumn.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpSecondPickerSpacing.m_trackerReference.8,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->m_tpDayPicker,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spLayoutRoot.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpSecondPickerSpacing.m_trackerReference.8,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IUIElement3,DirectUI::UIElementGenerated>,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spYearTextBlock.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpSecondPickerSpacing.m_trackerReference.8,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IUIElement7,DirectUI::UIElementGenerated>,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spMonthTextBlock.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpSecondPickerSpacing.m_trackerReference.8,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IUIElementOverrides8,DirectUI::UIElementGenerated>,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spDayTextBlock.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpSecondPickerSpacing.m_trackerReference.8,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->Windows::UI::Composition::IAnimationObject,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spFlyoutButton.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpSecondPickerSpacing.m_trackerReference.8,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->m_tpDaySource,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spFlyoutButtonContentGrid.ptr_);
  updated = DirectUI::DatePicker::UpdateHeaderPresenterVisibility(v1);
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
LABEL_99:
    OnFailure_2990_(updated);
    goto $Cleanup_9112;
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
      goto $Cleanup_9112;
    }
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spHeaderAsInspectable);
    v23 = (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpSecondPickerSpacing.m_trackerReference.8;
  }
  if ( this->DirectUI::DatePickerGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement2,DirectUI::FrameworkElementGenerated>::m_forwarder.DirectUI::DatePickerGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement2,DirectUI::FrameworkElementGenerated>::__vftable )
  {
    *(_QWORD *)&_Func = DirectUI::DatePicker::OnSelectorSelectionChanged;
    spHeaderAsInspectable.ptr_ = v1;
    DWORD2(_Func) = 0;
    v27 = std::bind<long (DirectUI::TimePicker::*)(IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *),DirectUI::TimePicker *,std::_Ph<1> const &,std::_Ph<2> const &>(
            (std::_Binder<std::_Unforced,long (__cdecl DirectUI::AutoSuggestBox::*)(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *),DirectUI::AutoSuggestBox *,std::_Ph<1> const &,std::_Ph<2> const &> *)result,
            &_Func,
            (DirectUI::AutoSuggestBox **)&spHeaderAsInspectable,
            v24,
            v47);
    v29 = *v28;
    v70._Mystorage._Ptrs[7] = 0;
    v70._Mystorage._Ptrs[0] = v30;
    *(_OWORD *)&v70._Mystorage._Ptrs[1] = v27->_Mypair._Myval1;
    LOWORD(v70._Mystorage._Ptrs[3]) = v27->_Mypair._Myval2.std::tuple<std::_Ph<1>,std::_Ph<2> >;
    v70._Mystorage._Ptrs[4] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *> *)v27->_Mypair._Myval2._Myfirst._Val;
    v70._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *> *)&v70;
    ValueByKnownIndex = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Controls::ISelectionChangedEventHandler,IInspectable,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs,DirectUI::SelectionChangedTraits>>::AttachEventHandler(
                          (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Controls::ISelectionChangedEventHandler,IInspectable,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs,DirectUI::SelectionChangedTraits> > *)&this->m_tpFirstSpacerColumn,
                          v29,
                          &v70);
    v6 = ValueByKnownIndex;
    if ( ValueByKnownIndex < 0 )
      goto LABEL_84;
    WindowsDeleteString(0);
    ValueByKnownIndex = DirectUI::DependencyObject::GetValueByKnownIndex(
                          (DirectUI::DependencyObject *)((__int64)&this->DirectUI::DatePickerGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement2,DirectUI::FrameworkElementGenerated>::m_forwarder.DirectUI::DatePickerGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement2,DirectUI::FrameworkElementGenerated>::__vftable[-11].GetRuntimeClassName
                                                       & -(__int64)(this->DirectUI::DatePickerGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement2,DirectUI::FrameworkElementGenerated>::m_forwarder.DirectUI::DatePickerGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement2,DirectUI::FrameworkElementGenerated>::__vftable != 0)),
                          AutomationProperties_Name,
                          &strAutomationName._hstring);
    v6 = ValueByKnownIndex;
    if ( ValueByKnownIndex < 0 )
      goto LABEL_84;
    hstring = strAutomationName._hstring;
    if ( !strAutomationName._hstring )
    {
      Current = DirectUI::DXamlCore::GetCurrent();
      WindowsDeleteString(0);
      strAutomationName._hstring = 0;
      ValueByKnownIndex = DirectUI::DXamlCore::GetLocalizedResourceString(Current, 0x1491u, &strAutomationName._hstring);
      v6 = ValueByKnownIndex;
      if ( ValueByKnownIndex < 0 )
        goto LABEL_84;
      ValueByKnownIndex = Windows::Internal::String::Concat(
                            &strAutomationName,
                            &strParentAutomationName,
                            &strComboAutomationName);
      v6 = ValueByKnownIndex;
      if ( ValueByKnownIndex < 0 )
        goto LABEL_84;
      ValueByKnownIndex = DirectUI::DependencyObject::SetValueByKnownIndex(
                            (DirectUI::DependencyObject *)((__int64)&this->DirectUI::DatePickerGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement2,DirectUI::FrameworkElementGenerated>::m_forwarder.DirectUI::DatePickerGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement2,DirectUI::FrameworkElementGenerated>::__vftable[-11].GetRuntimeClassName
                                                         & -(__int64)(this->DirectUI::DatePickerGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement2,DirectUI::FrameworkElementGenerated>::m_forwarder.DirectUI::DatePickerGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement2,DirectUI::FrameworkElementGenerated>::__vftable != 0)),
                            AutomationProperties_Name,
                            strComboAutomationName._hstring);
      v6 = ValueByKnownIndex;
      if ( ValueByKnownIndex < 0 )
        goto LABEL_84;
      hstring = strAutomationName._hstring;
    }
  }
  if ( v7->m_forwarder.__vftable )
  {
    *(_QWORD *)&_Func = DirectUI::DatePicker::OnSelectorSelectionChanged;
    spHeaderAsInspectable.ptr_ = v1;
    DWORD2(_Func) = 0;
    v33 = std::bind<long (DirectUI::TimePicker::*)(IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *),DirectUI::TimePicker *,std::_Ph<1> const &,std::_Ph<2> const &>(
            (std::_Binder<std::_Unforced,long (__cdecl DirectUI::AutoSuggestBox::*)(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *),DirectUI::AutoSuggestBox *,std::_Ph<1> const &,std::_Ph<2> const &> *)result,
            &_Func,
            (DirectUI::AutoSuggestBox **)&spHeaderAsInspectable,
            v24,
            v47);
    v34 = (Windows::UI::Xaml::Controls::Primitives::ISelector *)v7->m_forwarder.__vftable;
    v70._Mystorage._Ptrs[7] = 0;
    v70._Mystorage._Ptrs[0] = v35;
    *(_OWORD *)&v70._Mystorage._Ptrs[1] = v33->_Mypair._Myval1;
    LOWORD(v70._Mystorage._Ptrs[3]) = v33->_Mypair._Myval2.std::tuple<std::_Ph<1>,std::_Ph<2> >;
    v70._Mystorage._Ptrs[4] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *> *)v33->_Mypair._Myval2._Myfirst._Val;
    v70._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *> *)&v70;
    ValueByKnownIndex = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Controls::ISelectionChangedEventHandler,IInspectable,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs,DirectUI::SelectionChangedTraits>>::AttachEventHandler(
                          (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Controls::ISelectionChangedEventHandler,IInspectable,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs,DirectUI::SelectionChangedTraits> > *)&this->m_tpFirstSpacerColumn.m_trackerReference.8,
                          v34,
                          &v70);
    v6 = ValueByKnownIndex;
    if ( ValueByKnownIndex < 0 )
      goto LABEL_84;
    WindowsDeleteString(hstring);
    v36 = v7->m_forwarder.__vftable;
    strAutomationName._hstring = 0;
    ValueByKnownIndex = DirectUI::DependencyObject::GetValueByKnownIndex(
                          (DirectUI::DependencyObject *)((unsigned __int64)&v36[-6].GetIids & -(__int64)(v36 != 0)),
                          AutomationProperties_Name,
                          &strAutomationName._hstring);
    v6 = ValueByKnownIndex;
    if ( ValueByKnownIndex < 0 )
      goto LABEL_84;
    hstring = strAutomationName._hstring;
    if ( !strAutomationName._hstring )
    {
      v37 = DirectUI::DXamlCore::GetCurrent();
      WindowsDeleteString(0);
      strAutomationName._hstring = 0;
      ValueByKnownIndex = DirectUI::DXamlCore::GetLocalizedResourceString(v37, 0x1492u, &strAutomationName._hstring);
      v6 = ValueByKnownIndex;
      if ( ValueByKnownIndex < 0
        || (ValueByKnownIndex = Windows::Internal::String::Concat(
                                  &strAutomationName,
                                  &strParentAutomationName,
                                  &strComboAutomationName),
            v6 = ValueByKnownIndex,
            ValueByKnownIndex < 0)
        || (ValueByKnownIndex = DirectUI::DependencyObject::SetValueByKnownIndex(
                                  (DirectUI::DependencyObject *)((__int64)&v7->m_forwarder.__vftable[-6].GetIids
                                                               & -(__int64)(v7->m_forwarder.__vftable != 0)),
                                  AutomationProperties_Name,
                                  strComboAutomationName._hstring),
            v6 = ValueByKnownIndex,
            ValueByKnownIndex < 0) )
      {
LABEL_84:
        OnFailure_2990_(ValueByKnownIndex);
        goto $Cleanup_9112;
      }
      hstring = strAutomationName._hstring;
    }
  }
  if ( v9->m_forwarder.__vftable )
  {
    spHeaderAsInspectable.ptr_ = v1;
    *(_QWORD *)&_Func = DirectUI::DatePicker::OnSelectorSelectionChanged;
    DWORD2(_Func) = 0;
    v38 = std::bind<long (DirectUI::TimePicker::*)(IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *),DirectUI::TimePicker *,std::_Ph<1> const &,std::_Ph<2> const &>(
            (std::_Binder<std::_Unforced,long (__cdecl DirectUI::AutoSuggestBox::*)(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *),DirectUI::AutoSuggestBox *,std::_Ph<1> const &,std::_Ph<2> const &> *)result,
            &_Func,
            (DirectUI::AutoSuggestBox **)&spHeaderAsInspectable,
            v24,
            v47);
    v39 = (Windows::UI::Xaml::Controls::Primitives::ISelector *)v9->m_forwarder.__vftable;
    v70._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *> *)std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (DirectUI::DatePicker::*)(IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *),DirectUI::DatePicker *,std::_Ph<1> const &,std::_Ph<2> const &>,long,IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *>::`vftable';
    v70._Mystorage._Ptrs[7] = 0;
    *(_OWORD *)&v70._Mystorage._Ptrs[1] = v38->_Mypair._Myval1;
    LOWORD(v70._Mystorage._Ptrs[3]) = v38->_Mypair._Myval2.std::tuple<std::_Ph<1>,std::_Ph<2> >;
    v70._Mystorage._Ptrs[4] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *> *)v38->_Mypair._Myval2._Myfirst._Val;
    v70._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs *> *)&v70;
    ValueByKnownIndex = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Controls::ISelectionChangedEventHandler,IInspectable,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs,DirectUI::SelectionChangedTraits>>::AttachEventHandler(
                          (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Controls::ISelectionChangedEventHandler,IInspectable,Windows::UI::Xaml::Controls::ISelectionChangedEventArgs,DirectUI::SelectionChangedTraits> > *)&this->m_tpFirstSpacerColumn.m_trackerReference
                        + 2,
                          v39,
                          &v70);
    v6 = ValueByKnownIndex;
    if ( ValueByKnownIndex < 0 )
      goto LABEL_84;
    WindowsDeleteString(hstring);
    v40 = v9->m_forwarder.__vftable;
    strAutomationName._hstring = 0;
    ValueByKnownIndex = DirectUI::DependencyObject::GetValueByKnownIndex(
                          (DirectUI::DependencyObject *)((unsigned __int64)&v40[-17].Release & -(__int64)(v40 != 0)),
                          AutomationProperties_Name,
                          &strAutomationName._hstring);
    v6 = ValueByKnownIndex;
    if ( ValueByKnownIndex < 0 )
      goto LABEL_84;
    if ( !strAutomationName._hstring )
    {
      v41 = DirectUI::DXamlCore::GetCurrent();
      WindowsDeleteString(0);
      strAutomationName._hstring = 0;
      ValueByKnownIndex = DirectUI::DXamlCore::GetLocalizedResourceString(v41, 0x1493u, &strAutomationName._hstring);
      v6 = ValueByKnownIndex;
      if ( ValueByKnownIndex < 0 )
        goto LABEL_84;
      ValueByKnownIndex = Windows::Internal::String::Concat(
                            &strAutomationName,
                            &strParentAutomationName,
                            &strComboAutomationName);
      v6 = ValueByKnownIndex;
      if ( ValueByKnownIndex < 0 )
        goto LABEL_84;
      ValueByKnownIndex = DirectUI::DependencyObject::SetValueByKnownIndex(
                            (DirectUI::DependencyObject *)((__int64)&v9->m_forwarder.__vftable[-17].Release
                                                         & -(__int64)(v9->m_forwarder.__vftable != 0)),
                            AutomationProperties_Name,
                            strComboAutomationName._hstring);
      v6 = ValueByKnownIndex;
      if ( ValueByKnownIndex < 0 )
        goto LABEL_84;
    }
  }
  if ( this->DirectUI::DatePickerGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::Windows::UI::Composition::IAnimationObject::IInspectable::IUnknown::__vftable )
  {
    if ( !CQuirksMode2::XamlQuirkIsEnabled(0x200F2u) )
    {
      if ( IsXamlControlsCalculateFlyoutPlacementPresent() )
      {
        spHeaderAsInspectable.ptr_ = v1;
        *(_QWORD *)&_Func = DirectUI::DatePicker::OnFlyoutButtonClick;
        DWORD2(_Func) = 0;
        std::tuple<DirectUI::SplitView *,std::_Ph<1>,std::_Ph<2>>::tuple<DirectUI::SplitView *,std::_Ph<1>,std::_Ph<2>>(
          &v50,
          (DirectUI::SplitView **)&spHeaderAsInspectable,
          v42,
          v43);
        v44 = this->DirectUI::DatePickerGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::Windows::UI::Composition::IAnimationObject::IInspectable::IUnknown::__vftable;
        *(_OWORD *)&result[0]._Mystorage._Ptrs[1] = _Func;
        LOWORD(result[0]._Mystorage._Ptrs[3]) = v50.std::tuple<std::_Ph<1>,std::_Ph<2> >;
        result[0]._Mystorage._Ptrs[4] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)v50._Myfirst._Val;
        result[0]._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (DirectUI::DatePicker::*)(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *),DirectUI::DatePicker *,std::_Ph<1> const &,std::_Ph<2> const &>,long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *>::`vftable';
        result[0]._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)result;
        ValueByKnownIndex = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::ButtonBaseClickTraits>>::AttachEventHandler(
                              (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::ButtonBaseClickTraits> > *)&this->m_tpSecondSpacerColumn,
                              (Windows::UI::Xaml::Controls::Primitives::IButtonBase *)v44,
                              result);
        v6 = ValueByKnownIndex;
        if ( ValueByKnownIndex < 0 )
          goto LABEL_84;
      }
    }
    ValueByKnownIndex = DirectUI::DatePicker::RefreshFlyoutButtonAutomationName(v1);
    v6 = ValueByKnownIndex;
    if ( ValueByKnownIndex < 0 )
      goto LABEL_84;
  }
  if ( (-(__int64)(this->m_pVirtualizationInformation._Mypair._Myval2 != 0)
      & ((__int64)&this->m_pVirtualizationInformation._Mypair._Myval2[-1].m_tpBuildTreeArgs.m_trackerReference + 16)) == 0
    || (-(__int64)(this->m_tpAP.m_trackerReference.m_trackerData != 0)
      & (__int64)&this->m_tpAP.m_trackerReference.m_trackerData[-2].TrackerTarget) == 0
    || (-(__int64)(this->DirectUI::DatePickerGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IUIElement10,DirectUI::UIElementGenerated>::m_forwarder.DirectUI::DatePickerGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IUIElement10,DirectUI::UIElementGenerated>::__vftable != 0)
      & (__int64)&this->DirectUI::DatePickerGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IUIElement10,DirectUI::UIElementGenerated>::m_forwarder.DirectUI::DatePickerGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IUIElement10,DirectUI::UIElementGenerated>::__vftable[-1].get_UIContext) == 0 )
  {
    refreshed = ctl::make<DirectUI::TrackerCollection<IInspectable *>>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::TrackerCollection<IInspectable *> > >)&spCollection);
    v6 = refreshed;
    if ( refreshed < 0 )
      goto LABEL_94;
    ctl::WeakReferenceSourceNoThreadId::SetPtrValue<DirectUI::IterableWrappedObservableCollection<Windows::UI::Xaml::Controls::ICommandBarElement>,DirectUI::IterableWrappedObservableCollection<Windows::UI::Xaml::Controls::ICommandBarElement>>(
      v23,
      (DirectUI::TrackerPtr<DirectUI::TrackerCollection<IInspectable *>,1,0> *)&this->m_pVirtualizationInformation,
      spCollection.ptr_);
    refreshed = ctl::make<DirectUI::TrackerCollection<IInspectable *>>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::TrackerCollection<IInspectable *> > >)&spCollection);
    v6 = refreshed;
    if ( refreshed < 0 )
      goto LABEL_94;
    ctl::WeakReferenceSourceNoThreadId::SetPtrValue<DirectUI::IterableWrappedObservableCollection<Windows::UI::Xaml::Controls::ICommandBarElement>,DirectUI::IterableWrappedObservableCollection<Windows::UI::Xaml::Controls::ICommandBarElement>>(
      v23,
      (DirectUI::TrackerPtr<DirectUI::TrackerCollection<IInspectable *>,1,0> *)&this->m_tpAP.m_trackerReference.8,
      spCollection.ptr_);
    refreshed = ctl::make<DirectUI::TrackerCollection<IInspectable *>>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::TrackerCollection<IInspectable *> > >)&spCollection);
    v6 = refreshed;
    if ( refreshed < 0 )
      goto LABEL_94;
    ctl::WeakReferenceSourceNoThreadId::SetPtrValue<DirectUI::IterableWrappedObservableCollection<Windows::UI::Xaml::Controls::ICommandBarElement>,DirectUI::IterableWrappedObservableCollection<Windows::UI::Xaml::Controls::ICommandBarElement>>(
      v23,
      (DirectUI::TrackerPtr<DirectUI::TrackerCollection<IInspectable *>,1,0> *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IUIElement10,DirectUI::UIElementGenerated>,
      spCollection.ptr_);
  }
  refreshed = DirectUI::DatePicker::RefreshSetup(v1);
  v6 = refreshed;
  if ( refreshed < 0 || (refreshed = DirectUI::Control::UpdateVisualState(v1, 0), v6 = refreshed, refreshed < 0) )
LABEL_94:
    OnFailure_2990_(refreshed);
$Cleanup_9112:
  *((_BYTE *)&this->m_tpSecondSpacerColumn.m_trackerReference + 17) = 0;
  Windows::Internal::String::~String(&strComboAutomationName);
  Windows::Internal::String::~String(&strParentAutomationName);
  Windows::Internal::String::~String(&strAutomationName);
  ctl::ComPtr<DirectUI::TrackerCollection<Windows::UI::Xaml::Controls::CalendarViewDayItem *>>::InternalRelease((ctl::ComPtr<DirectUI::TrackerCollection<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> > *)&spCollection);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spFlyoutButtonContentGrid);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spSecondSpacerColumn);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spFirstSpacerColumn);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spYearColumn);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spMonthColumn);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDayColumn);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDayTextBlock);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spMonthTextBlock);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spYearTextBlock);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spFlyoutButton);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spSpacingHolderTwo);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spSpacingHolderOne);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spLayoutRoot);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spThirdPickerHost);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spSecondPickerHost);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spFirstPickerHost);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spYearPicker);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spMonthPicker);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spDayPicker);
  return v6;
}

```

## disassembly

```asm
0x18097adc0  push    rbp
0x18097adc2  push    rbx
0x18097adc3  push    rsi
0x18097adc4  push    rdi
0x18097adc5  push    r12
0x18097adc7  push    r13
0x18097adc9  push    r14
0x18097adcb  push    r15
0x18097adcd  lea     rbp, [rsp-78h]
0x18097add2  sub     rsp, 178h
0x18097add9  xor     edi, edi
0x18097addb  lea     r14, [this-168h]
0x18097ade2  mov     rdx, [r14+2D8h]; pSource
0x18097ade9  mov     ebx, edi
0x18097adeb  mov     [rbp+0B0h+spDayPicker.ptr_], rdi
0x18097adef  mov     r15, this
0x18097adf2  mov     [rbp+0B0h+spMonthPicker.ptr_], rdi
0x18097adf6  mov     [rbp+0B0h+spYearPicker.ptr_], rdi
0x18097adfa  mov     [rbp+0B0h+spFirstPickerHost.ptr_], rdi
0x18097adfe  mov     [rbp+0B0h+spSecondPickerHost.ptr_], rdi
0x18097ae02  mov     [rbp+0B0h+spThirdPickerHost.ptr_], rdi
0x18097ae06  mov     [rbp+0B0h+spLayoutRoot.ptr_], rdi
0x18097ae0a  mov     [rbp+0B0h+spSpacingHolderOne.ptr_], rdi
0x18097ae0e  mov     [rbp+0B0h+spSpacingHolderTwo.ptr_], rdi
0x18097ae12  mov     [rbp+0B0h+spFlyoutButton.ptr_], rdi
0x18097ae16  mov     [rbp+0B0h+spYearTextBlock.ptr_], rdi
0x18097ae1a  mov     [rbp+0B0h+spMonthTextBlock.ptr_], rdi
0x18097ae1e  mov     [rbp+0B0h+spDayTextBlock.ptr_], rdi
0x18097ae22  mov     [rbp+0B0h+spDayColumn.ptr_], rdi
0x18097ae26  mov     [rsp+1B0h+spMonthColumn.ptr_], rdi
0x18097ae2b  mov     [rsp+1B0h+spYearColumn.ptr_], rdi
0x18097ae30  mov     [rsp+1B0h+spFirstSpacerColumn.ptr_], rdi
0x18097ae35  mov     [rsp+1B0h+spSecondSpacerColumn.ptr_], rdi
0x18097ae3a  mov     [rsp+1B0h+spFlyoutButtonContentGrid.ptr_], rdi
0x18097ae3f  mov     [rsp+1B0h+spCollection.ptr_], rdi
0x18097ae44  mov     [rbp+0B0h+strAutomationName._hstring], rbx
0x18097ae4b  mov     [rbp+0B0h+strParentAutomationName._hstring], rdi
0x18097ae52  mov     [rbp+0B0h+strComboAutomationName._hstring], rdi
0x18097ae59  test    rdx, rdx
0x18097ae5c  jz      short loc_18097AE7E
0x18097ae5e  add     this, 3C8h; this
0x18097ae65  call    ?DetachEventHandler@?$EventPtrBase@V?$event_handler@U?$ITypedEventHandler@PEAVHandwritingView@Controls@Xaml@UI@Windows@@PEAVHandwritingPanelClosedEventArgs@2345@@Foundation@Windows@@UIHandwritingView@Controls@Xaml@UI@3@UIHandwritingPanelClosedEventArgs@5673@UHandwritingViewClosedTraits@DirectUI@@@ctl@@@ctl@@QEAAJPEAUIInspectable@@@Z; ctl::EventPtrBase<ctl::event_handler<Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::HandwritingView *,Windows::UI::Xaml::Controls::HandwritingPanelClosedEventArgs *>,Windows::UI::Xaml::Controls::IHandwritingView,Windows::UI::Xaml::Controls::IHandwritingPanelClosedEventArgs,DirectUI::HandwritingViewClosedTraits>>::DetachEventHandler(IInspectable *)
0x18097ae6a  mov     edi, eax
0x18097ae6c  test    eax, eax
0x18097ae6e  jns     short loc_18097AE7C
0x18097ae70  mov     ecx, eax; failedFrameHR
0x18097ae72  call    OnFailure_2990_
0x18097ae77  jmp     $Cleanup_9112
0x18097ae7c  xor     edi, edi
0x18097ae7e  lea     r12, [r15+188h]
0x18097ae85  mov     rdx, [r12]; pSource
0x18097ae89  test    rdx, rdx
0x18097ae8c  jz      short loc_18097AEAE
0x18097ae8e  lea     this, [r15+3D0h]; this
0x18097ae95  call    ?DetachEventHandler@?$EventPtrBase@V?$event_handler@U?$ITypedEventHandler@PEAVHandwritingView@Controls@Xaml@UI@Windows@@PEAVHandwritingPanelClosedEventArgs@2345@@Foundation@Windows@@UIHandwritingView@Controls@Xaml@UI@3@UIHandwritingPanelClosedEventArgs@5673@UHandwritingViewClosedTraits@DirectUI@@@ctl@@@ctl@@QEAAJPEAUIInspectable@@@Z; ctl::EventPtrBase<ctl::event_handler<Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::HandwritingView *,Windows::UI::Xaml::Controls::HandwritingPanelClosedEventArgs *>,Windows::UI::Xaml::Controls::IHandwritingView,Windows::UI::Xaml::Controls::IHandwritingPanelClosedEventArgs,DirectUI::HandwritingViewClosedTraits>>::DetachEventHandler(IInspectable *)
0x18097ae9a  mov     edi, eax
0x18097ae9c  test    eax, eax
0x18097ae9e  jns     short loc_18097AEAC
0x18097aea0  mov     ecx, eax; failedFrameHR
0x18097aea2  call    OnFailure_2990_
0x18097aea7  jmp     $Cleanup_9112
0x18097aeac  xor     edi, edi
0x18097aeae  lea     r13, [r15+1A0h]
0x18097aeb5  mov     rdx, [r13+0]; pSource
0x18097aeb9  test    rdx, rdx
0x18097aebc  jz      short loc_18097AEDE
0x18097aebe  lea     this, [r15+3D8h]; this
0x18097aec5  call    ?DetachEventHandler@?$EventPtrBase@V?$event_handler@U?$ITypedEventHandler@PEAVHandwritingView@Controls@Xaml@UI@Windows@@PEAVHandwritingPanelClosedEventArgs@2345@@Foundation@Windows@@UIHandwritingView@Controls@Xaml@UI@3@UIHandwritingPanelClosedEventArgs@5673@UHandwritingViewClosedTraits@DirectUI@@@ctl@@@ctl@@QEAAJPEAUIInspectable@@@Z; ctl::EventPtrBase<ctl::event_handler<Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::HandwritingView *,Windows::UI::Xaml::Controls::HandwritingPanelClosedEventArgs *>,Windows::UI::Xaml::Controls::IHandwritingView,Windows::UI::Xaml::Controls::IHandwritingPanelClosedEventArgs,DirectUI::HandwritingViewClosedTraits>>::DetachEventHandler(IInspectable *)
0x18097aeca  mov     edi, eax
0x18097aecc  test    eax, eax
0x18097aece  jns     short loc_18097AEDC
0x18097aed0  mov     ecx, eax; failedFrameHR
0x18097aed2  call    OnFailure_2990_
0x18097aed7  jmp     $Cleanup_9112
0x18097aedc  xor     edi, edi
0x18097aede  lea     rsi, [r15+0C8h]
0x18097aee5  cmp     [rsi], rdi
0x18097aee8  jz      short loc_18097AF22
0x18097aeea  mov     ecx, 200F2h; quirk
0x18097aeef  call    ?XamlQuirkIsEnabled@CQuirksMode2@@SA_NK@Z; CQuirksMode2::XamlQuirkIsEnabled(ulong)
0x18097aef4  test    al, al
0x18097aef6  jnz     short loc_18097AF22
0x18097aef8  call    IsXamlControlsCalculateFlyoutPlacementPresent
0x18097aefd  test    al, al
0x18097aeff  jz      short loc_18097AF22
0x18097af01  mov     rdx, [rsi]; pSource
0x18097af04  lea     this, [r15+3E0h]; this
0x18097af0b  call    ?DetachEventHandler@?$EventPtrBase@V?$event_handler@U?$ITypedEventHandler@PEAVHandwritingView@Controls@Xaml@UI@Windows@@PEAVHandwritingPanelClosedEventArgs@2345@@Foundation@Windows@@UIHandwritingView@Controls@Xaml@UI@3@UIHandwritingPanelClosedEventArgs@5673@UHandwritingViewClosedTraits@DirectUI@@@ctl@@@ctl@@QEAAJPEAUIInspectable@@@Z; ctl::EventPtrBase<ctl::event_handler<Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::HandwritingView *,Windows::UI::Xaml::Controls::HandwritingPanelClosedEventArgs *>,Windows::UI::Xaml::Controls::IHandwritingView,Windows::UI::Xaml::Controls::IHandwritingPanelClosedEventArgs,DirectUI::HandwritingViewClosedTraits>>::DetachEventHandler(IInspectable *)
0x18097af10  mov     edi, eax
0x18097af12  test    eax, eax
0x18097af14  jns     short loc_18097AF22
0x18097af16  mov     ecx, eax; failedFrameHR
0x18097af18  call    OnFailure_2990_
0x18097af1d  jmp     $Cleanup_9112
0x18097af22  lea     this, [r15+170h]; this
0x18097af29  xor     r8d, r8d; bForceLoopback
0x18097af2c  mov     dl, 1; bEnsureTrackerTarget
0x18097af2e  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18097af33  xor     r8d, r8d; bForceLoopback
0x18097af36  mov     dl, 1; bEnsureTrackerTarget
0x18097af38  mov     this, r12; this
0x18097af3b  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18097af40  xor     r8d, r8d; bForceLoopback
0x18097af43  mov     dl, 1; bEnsureTrackerTarget
0x18097af45  mov     this, r13; this
0x18097af48  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18097af4d  lea     this, [r15+1D0h]; this
0x18097af54  xor     r8d, r8d; bForceLoopback
0x18097af57  mov     dl, 1; bEnsureTrackerTarget
0x18097af59  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18097af5e  lea     this, [r15+1E8h]; this
0x18097af65  xor     r8d, r8d; bForceLoopback
0x18097af68  mov     dl, 1; bEnsureTrackerTarget
0x18097af6a  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18097af6f  lea     this, [r15+200h]; this
0x18097af76  xor     r8d, r8d; bForceLoopback
0x18097af79  mov     dl, 1; bEnsureTrackerTarget
0x18097af7b  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18097af80  lea     this, [r15+218h]; this
0x18097af87  xor     r8d, r8d; bForceLoopback
0x18097af8a  mov     dl, 1; bEnsureTrackerTarget
0x18097af8c  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18097af91  lea     this, [r15+230h]; this
0x18097af98  xor     r8d, r8d; bForceLoopback
0x18097af9b  mov     dl, 1; bEnsureTrackerTarget
0x18097af9d  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18097afa2  lea     this, [r15+248h]; this
0x18097afa9  xor     r8d, r8d; bForceLoopback
0x18097afac  mov     dl, 1; bEnsureTrackerTarget
0x18097afae  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18097afb3  lea     this, [r15+260h]; this
0x18097afba  xor     r8d, r8d; bForceLoopback
0x18097afbd  mov     dl, 1; bEnsureTrackerTarget
0x18097afbf  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18097afc4  lea     this, [r15+278h]; this
0x18097afcb  xor     r8d, r8d; bForceLoopback
0x18097afce  mov     dl, 1; bEnsureTrackerTarget
0x18097afd0  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18097afd5  lea     this, [r15+2A8h]; this
0x18097afdc  xor     r8d, r8d; bForceLoopback
0x18097afdf  mov     dl, 1; bEnsureTrackerTarget
0x18097afe1  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18097afe6  lea     this, [r15+2C0h]; this
0x18097afed  xor     r8d, r8d; bForceLoopback
0x18097aff0  mov     dl, 1; bEnsureTrackerTarget
0x18097aff2  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18097aff7  lea     this, [r15+2D8h]; this
0x18097affe  xor     r8d, r8d; bForceLoopback
0x18097b001  mov     dl, 1; bEnsureTrackerTarget
0x18097b003  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18097b008  lea     this, [r15+1B8h]; this
0x18097b00f  xor     r8d, r8d; bForceLoopback
0x18097b012  mov     dl, 1; bEnsureTrackerTarget
0x18097b014  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18097b019  xor     r8d, r8d; bForceLoopback
0x18097b01c  mov     dl, 1; bEnsureTrackerTarget
0x18097b01e  mov     this, rsi; this
0x18097b021  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18097b026  lea     this, [r15+290h]; this
0x18097b02d  xor     r8d, r8d; bForceLoopback
0x18097b030  mov     dl, 1; bEnsureTrackerTarget
0x18097b032  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18097b037  lea     this, [r15+0E0h]; this
0x18097b03e  xor     r8d, r8d; bForceLoopback
0x18097b041  mov     dl, 1; bEnsureTrackerTarget
0x18097b043  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18097b048  lea     this, [r15+0F8h]; this
0x18097b04f  xor     r8d, r8d; bForceLoopback
0x18097b052  mov     dl, 1; bEnsureTrackerTarget
0x18097b054  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18097b059  lea     this, [r15+110h]; this
0x18097b060  xor     r8d, r8d; bForceLoopback
0x18097b063  mov     dl, 1; bEnsureTrackerTarget
0x18097b065  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18097b06a  mov     this, r15; this
0x18097b06d  call    ?OnApplyTemplate@Control@DirectUI@@UEAAJXZ; DirectUI::Control::OnApplyTemplate(void)
0x18097b072  mov     edi, eax
0x18097b074  test    eax, eax
0x18097b076  js      loc_18097BDEA
0x18097b07c  lea     this, [rbp+0B0h+spDayPicker]; this
0x18097b080  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18097b085  lea     r9, [rbp+0B0h+spDayPicker]; ppReference
0x18097b089  mov     r8d, 9; cName
0x18097b08f  lea     rdx, aDaypicker; "DayPicker"
0x18097b096  mov     this, r14; this
0x18097b099  call    ??$GetTemplatePart@UISelector@Primitives@Controls@Xaml@UI@Windows@@U123456@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUISelector@Primitives@Controls@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::Primitives::ISelector,Windows::UI::Xaml::Controls::Primitives::ISelector>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::Primitives::ISelector * *)
0x18097b09e  mov     edi, eax
0x18097b0a0  test    eax, eax
0x18097b0a2  js      loc_18097BDE1
0x18097b0a8  lea     this, [rbp+0B0h+spMonthPicker]; this
0x18097b0ac  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18097b0b1  lea     r9, [rbp+0B0h+spMonthPicker]; ppReference
0x18097b0b5  mov     r8d, 0Bh; cName
0x18097b0bb  lea     rdx, aMonthpicker; "MonthPicker"
0x18097b0c2  mov     this, r14; this
0x18097b0c5  call    ??$GetTemplatePart@UISelector@Primitives@Controls@Xaml@UI@Windows@@U123456@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUISelector@Primitives@Controls@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::Primitives::ISelector,Windows::UI::Xaml::Controls::Primitives::ISelector>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::Primitives::ISelector * *)
0x18097b0ca  mov     edi, eax
0x18097b0cc  test    eax, eax
0x18097b0ce  js      loc_18097BDD8
0x18097b0d4  lea     this, [rbp+0B0h+spYearPicker]; this
0x18097b0d8  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18097b0dd  mov     esi, 0Ah
0x18097b0e2  lea     r9, [rbp+0B0h+spYearPicker]; ppReference
0x18097b0e6  mov     r8d, esi; cName
0x18097b0e9  lea     rdx, aYearpicker; "YearPicker"
0x18097b0f0  mov     this, r14; this
0x18097b0f3  call    ??$GetTemplatePart@UISelector@Primitives@Controls@Xaml@UI@Windows@@U123456@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUISelector@Primitives@Controls@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::Primitives::ISelector,Windows::UI::Xaml::Controls::Primitives::ISelector>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::Primitives::ISelector * *)
0x18097b0f8  mov     edi, eax
0x18097b0fa  test    eax, eax
0x18097b0fc  js      loc_18097BDCF
0x18097b102  lea     this, [rbp+0B0h+spFirstPickerHost]; this
0x18097b106  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18097b10b  lea     r9, [rbp+0B0h+spFirstPickerHost]; ppReference
0x18097b10f  mov     this, r14; this
0x18097b112  lea     r8d, [rsi+5]; cName
0x18097b116  lea     rdx, aFirstpickerhos; "FirstPickerHost"
0x18097b11d  call    ??$GetTemplatePart@UIBorder@Controls@Xaml@UI@Windows@@U12345@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUIBorder@Controls@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IBorder,Windows::UI::Xaml::Controls::IBorder>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::IBorder * *)
0x18097b122  mov     edi, eax
0x18097b124  test    eax, eax
0x18097b126  js      loc_18097BDC6
0x18097b12c  lea     this, [rbp+0B0h+spSecondPickerHost]; this
0x18097b130  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18097b135  lea     r9, [rbp+0B0h+spSecondPickerHost]; ppReference
0x18097b139  mov     this, r14; this
0x18097b13c  lea     r8d, [rsi+6]; cName
0x18097b140  lea     rdx, aSecondpickerho; "SecondPickerHost"
0x18097b147  call    ??$GetTemplatePart@UIBorder@Controls@Xaml@UI@Windows@@U12345@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUIBorder@Controls@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IBorder,Windows::UI::Xaml::Controls::IBorder>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::IBorder * *)
0x18097b14c  mov     edi, eax
0x18097b14e  test    eax, eax
0x18097b150  js      loc_18097BDBD
0x18097b156  lea     this, [rbp+0B0h+spThirdPickerHost]; this
0x18097b15a  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18097b15f  lea     r9, [rbp+0B0h+spThirdPickerHost]; ppReference
0x18097b163  mov     this, r14; this
0x18097b166  lea     r8d, [rsi+5]; cName
0x18097b16a  lea     rdx, aThirdpickerhos; "ThirdPickerHost"
0x18097b171  call    ??$GetTemplatePart@UIBorder@Controls@Xaml@UI@Windows@@U12345@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUIBorder@Controls@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IBorder,Windows::UI::Xaml::Controls::IBorder>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::IBorder * *)
0x18097b176  mov     edi, eax
0x18097b178  test    eax, eax
0x18097b17a  js      loc_18097BDB4
0x18097b180  lea     this, [rbp+0B0h+spDayColumn]; this
0x18097b184  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18097b189  lea     r9, [rbp+0B0h+spDayColumn]; ppReference
0x18097b18d  mov     this, r14; this
0x18097b190  lea     r8d, [rsi-1]; cName
0x18097b194  lea     rdx, aDaycolumn; "DayColumn"
0x18097b19b  call    ??$GetTemplatePart@UIColumnDefinition@Controls@Xaml@UI@Windows@@U12345@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUIColumnDefinition@Controls@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IColumnDefinition,Windows::UI::Xaml::Controls::IColumnDefinition>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::IColumnDefinition * *)
0x18097b1a0  mov     edi, eax
0x18097b1a2  test    eax, eax
0x18097b1a4  js      loc_18097BDAB
0x18097b1aa  lea     this, [rsp+1B0h+spMonthColumn]; this
0x18097b1af  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18097b1b4  lea     r9, [rsp+1B0h+spMonthColumn]; ppReference
0x18097b1b9  mov     this, r14; this
0x18097b1bc  lea     r8d, [rsi+1]; cName
0x18097b1c0  lea     rdx, aMonthcolumn; "MonthColumn"
0x18097b1c7  call    ??$GetTemplatePart@UIColumnDefinition@Controls@Xaml@UI@Windows@@U12345@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUIColumnDefinition@Controls@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IColumnDefinition,Windows::UI::Xaml::Controls::IColumnDefinition>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::IColumnDefinition * *)
0x18097b1cc  mov     edi, eax
0x18097b1ce  test    eax, eax
0x18097b1d0  js      loc_18097BDA2
0x18097b1d6  lea     this, [rsp+1B0h+spYearColumn]; this
0x18097b1db  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18097b1e0  lea     r9, [rsp+1B0h+spYearColumn]; ppReference
0x18097b1e5  mov     r8d, esi; cName
0x18097b1e8  lea     rdx, aYearcolumn; "YearColumn"
0x18097b1ef  mov     this, r14; this
0x18097b1f2  call    ??$GetTemplatePart@UIColumnDefinition@Controls@Xaml@UI@Windows@@U12345@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUIColumnDefinition@Controls@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IColumnDefinition,Windows::UI::Xaml::Controls::IColumnDefinition>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::IColumnDefinition * *)
0x18097b1f7  mov     edi, eax
0x18097b1f9  test    eax, eax
0x18097b1fb  js      loc_18097BD99
0x18097b201  lea     this, [rsp+1B0h+spFirstSpacerColumn]; this
0x18097b206  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18097b20b  lea     r9, [rsp+1B0h+spFirstSpacerColumn]; ppReference
0x18097b210  mov     this, r14; this
0x18097b213  lea     r8d, [rsi+7]; cName
0x18097b217  lea     rdx, aFirstspacercol; "FirstSpacerColumn"
0x18097b21e  call    ??$GetTemplatePart@UIColumnDefinition@Controls@Xaml@UI@Windows@@U12345@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUIColumnDefinition@Controls@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IColumnDefinition,Windows::UI::Xaml::Controls::IColumnDefinition>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::IColumnDefinition * *)
0x18097b223  mov     edi, eax
0x18097b225  test    eax, eax
0x18097b227  js      loc_18097BD90
0x18097b22d  lea     this, [rsp+1B0h+spSecondSpacerColumn]; this
0x18097b232  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18097b237  lea     r9, [rsp+1B0h+spSecondSpacerColumn]; ppReference
0x18097b23c  mov     this, r14; this
0x18097b23f  lea     r8d, [rsi+8]; cName
0x18097b243  lea     rdx, aSecondspacerco; "SecondSpacerColumn"
0x18097b24a  call    ??$GetTemplatePart@UIColumnDefinition@Controls@Xaml@UI@Windows@@U12345@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUIColumnDefinition@Controls@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IColumnDefinition,Windows::UI::Xaml::Controls::IColumnDefinition>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::IColumnDefinition * *)
0x18097b24f  mov     edi, eax
0x18097b251  test    eax, eax
0x18097b253  js      loc_18097BD87
0x18097b259  lea     this, [rbp+0B0h+spYearTextBlock]; this
0x18097b25d  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18097b262  lea     r9, [rbp+0B0h+spYearTextBlock]; ppReference
0x18097b266  mov     this, r14; this
0x18097b269  lea     r8d, [rsi+3]; cName
0x18097b26d  lea     rdx, aYeartextblock; "YearTextBlock"
0x18097b274  call    ??$GetTemplatePart@UITextBlock@Controls@Xaml@UI@Windows@@U12345@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUITextBlock@Controls@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::ITextBlock,Windows::UI::Xaml::Controls::ITextBlock>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::ITextBlock * *)
0x18097b279  mov     edi, eax
0x18097b27b  test    eax, eax
0x18097b27d  js      loc_18097BD7E
  ... truncated ...
```
