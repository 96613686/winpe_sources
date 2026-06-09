# DirectUI::MediaTransportControls::MoreControls(void)

- ea: `0x18042b550`
- end: `0x18042c079`
- name: `?MoreControls@MediaTransportControls@DirectUI@@AEAAJXZ`
- size: `2857`
- prototype: `HRESULT __fastcall(DirectUI::MediaTransportControls *this)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1806f4f34`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x18005e96c`
- `0x18009ba40`
- `0x1801df610`
- `0x1802e04dc`
- `0x180304c94`
- `0x1803839c0`
- `0x18042b550`
- `0x180501d9c`
- `0x180539834`
- `0x1806cfac4`
- `0x1806d83e0`
- `0x1806f9bac`
- `0x1807045e8`
- `0x18076e110`
- `0x180b8c4cc`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18042b5ce`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18042b74d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18042b8ce`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18042ba4f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18042bbd0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18042bd51`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18042b5ce`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18042b74d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18042b8ce`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18042ba4f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18042bbd0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18042bd51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042b61e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042b79b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042b91c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042ba9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042bc1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042bd9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042c034`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042b61e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042b79b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042b91c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042ba9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042bc1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042bd9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042c034`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18042b5b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18042b734`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18042b8b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18042ba36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18042bbb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18042bd38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18042b5b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18042b734`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18042b8b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18042ba36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18042bbb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18042bd38`

## string_xrefs

- `0x18042bd31`: `CompactOverlayButton`

## pseudocode

```c
__int64 __fastcall DirectUI::MediaTransportControls::MoreControls(DirectUI::MediaTransportControls *this)
{
  Windows::UI::Xaml::Controls::IControlProtected *v1; // r12
  Windows::UI::Xaml::Controls::IControlProtected_vtbl *v2; // rax
  HSTRING__ *hstring; // rsi
  HRESULT (__fastcall *GetTemplateChild)(Windows::UI::Xaml::Controls::IControlProtected *, HSTRING__ *, Windows::UI::Xaml::IDependencyObject **); // rbx
  HRESULT v6; // eax
  unsigned int v7; // edi
  DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::IButton,1,0> *p_m_tpSkipForwardButton; // r15
  DirectUI::DXamlCore *Current; // rbx
  HRESULT LocalizedResourceString; // eax
  __int64 v11; // rdx
  Windows::UI::Xaml::Controls::Primitives::IButtonBase *v12; // rdx
  HRESULT (__fastcall *v13)(Windows::UI::Xaml::Controls::IControlProtected *, HSTRING__ *, Windows::UI::Xaml::IDependencyObject **); // rbx
  DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::IButton,1,0> *p_m_tpSkipBackwardButton; // r15
  DirectUI::DXamlCore *v15; // rbx
  __int64 v16; // rdx
  Windows::UI::Xaml::Controls::Primitives::IButtonBase *v17; // rdx
  HRESULT (__fastcall *v18)(Windows::UI::Xaml::Controls::IControlProtected *, HSTRING__ *, Windows::UI::Xaml::IDependencyObject **); // rbx
  DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::IButton,1,0> *p_m_tpNextTrackButton; // r15
  DirectUI::DXamlCore *v20; // rbx
  __int64 v21; // rdx
  Windows::UI::Xaml::Controls::Primitives::IButtonBase *v22; // rdx
  HRESULT (__fastcall *v23)(Windows::UI::Xaml::Controls::IControlProtected *, HSTRING__ *, Windows::UI::Xaml::IDependencyObject **); // rbx
  DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::IButton,1,0> *p_m_tpPreviousTrackButton; // r15
  DirectUI::DXamlCore *v25; // rbx
  __int64 v26; // rdx
  Windows::UI::Xaml::Controls::Primitives::IButtonBase *v27; // rdx
  HRESULT (__fastcall *v28)(Windows::UI::Xaml::Controls::IControlProtected *, HSTRING__ *, Windows::UI::Xaml::IDependencyObject **); // rbx
  DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::Primitives::IToggleButton,1,0> *p_m_tpRepeatButton; // r15
  DirectUI::DXamlCore *v30; // rbx
  __int64 v31; // rdx
  Windows::UI::Xaml::Controls::Primitives::IButtonBase *v32; // rdx
  HRESULT (__fastcall *v33)(Windows::UI::Xaml::Controls::IControlProtected *, HSTRING__ *, Windows::UI::Xaml::IDependencyObject **); // rbx
  DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::IButton,1,0> *p_m_tpCompactOverlayButton; // r15
  DirectUI::DXamlCore *v35; // rbx
  __int64 v36; // rdx
  Windows::UI::Xaml::Controls::Primitives::IButtonBase *v37; // rdx
  HRESULT (__fastcall *v38)(Windows::UI::Xaml::Controls::IControlProtected *, HSTRING__ *, Windows::UI::Xaml::IDependencyObject **); // rbx
  HSTRING__ **v39; // rax
  HRESULT (__fastcall *v40)(Windows::UI::Xaml::Controls::IControlProtected *, HSTRING__ *, Windows::UI::Xaml::IDependencyObject **); // rbx
  HSTRING__ **v41; // rax
  HRESULT v42; // eax
  Windows::UI::Xaml::IVisualStateGroup *ptr; // r15
  Windows::UI::Xaml::IVisualStateGroup *m_value; // rdx
  HRESULT v45; // eax
  Windows::UI::Xaml::IDependencyObject *v46; // rcx
  ctl::ComPtr<Windows::UI::Xaml::IVisualStateGroup> spVisibilityStatesGroup; // [rsp+20h] [rbp-49h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> spComponentAsDO; // [rsp+28h] [rbp-41h] BYREF
  Windows::Internal::String strAutomationName; // [rsp+30h] [rbp-39h] BYREF
  std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *)> string; // [rsp+38h] [rbp-31h] BYREF

  v1 = &this->Windows::UI::Xaml::Controls::IControlProtected;
  spComponentAsDO.ptr_ = 0;
  v2 = this->DirectUI::MediaTransportControlsGenerated::DirectUI::Control::DirectUI::ControlGenerated::Windows::UI::Xaml::Controls::IControlProtected::IInspectable::IUnknown::__vftable;
  hstring = 0;
  strAutomationName._hstring = 0;
  spVisibilityStatesGroup.ptr_ = 0;
  GetTemplateChild = v2->GetTemplateChild;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spComponentAsDO);
  if ( WindowsCreateStringReference(
         L"SkipForwardButton",
         0x11u,
         (HSTRING_HEADER *)&string._Mystorage._Ptrs[1],
         (HSTRING *)&string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v6 = GetTemplateChild(v1, (HSTRING__ *)string._Mystorage._Ptrs[0], &spComponentAsDO.ptr_);
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_99;
  p_m_tpSkipForwardButton = &this->m_tpSkipForwardButton;
  ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::IButton,Windows::UI::Xaml::IDependencyObject>(
    &this->ctl::WeakReferenceSourceNoThreadId,
    &this->m_tpSkipForwardButton,
    spComponentAsDO.ptr_);
  if ( this->m_tpSkipForwardButton.m_trackerReference.m_value )
  {
    Current = DirectUI::DXamlCore::GetCurrent();
    WindowsDeleteString(0);
    LocalizedResourceString = DirectUI::DXamlCore::GetLocalizedResourceString(
                                Current,
                                0x14C8u,
                                &strAutomationName._hstring);
    v7 = LocalizedResourceString;
    if ( LocalizedResourceString < 0 )
      goto LABEL_15;
    hstring = strAutomationName._hstring;
    v6 = DirectUI::DependencyObject::SetValueByKnownIndex(
           (DirectUI::DependencyObject *)((__int64)&p_m_tpSkipForwardButton->m_trackerReference.m_value[-79]
                                        & -(__int64)(p_m_tpSkipForwardButton->m_trackerReference.m_value != 0)),
           AutomationProperties_Name,
           strAutomationName._hstring);
    v7 = v6;
    if ( v6 < 0 )
      goto LABEL_99;
    v6 = DirectUI::MediaTransportControls::AddTooltip(
           (DirectUI::MediaTransportControls *)&p_m_tpSkipForwardButton->m_trackerReference.m_value[-79],
           (Windows::UI::Xaml::IDependencyObject *)((unsigned __int128)&p_m_tpSkipForwardButton->m_trackerReference.m_value[-79]
                                                  & ((unsigned __int128)-(__int128)(unsigned __int64)p_m_tpSkipForwardButton->m_trackerReference.m_value >> 64)),
           hstring);
    v7 = v6;
    if ( v6 < 0 )
      goto LABEL_99;
    string._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)this;
    string._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)std::_Func_impl_no_alloc__lambda_a093af20e0133ec21989a1cdec032b04__long_IInspectable___Windows::UI::Xaml::IRoutedEventArgs___::_vftable_;
    string._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)&string;
    v11 = (unsigned __int128)&p_m_tpSkipForwardButton->m_trackerReference.m_value[-79]
        & ((unsigned __int128)-(__int128)(unsigned __int64)p_m_tpSkipForwardButton->m_trackerReference.m_value >> 64);
    v12 = v11 ? (Windows::UI::Xaml::Controls::Primitives::IButtonBase *)(v11 + 568) : 0LL;
    v6 = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::ButtonBaseClickTraits>>::AttachEventHandler(
           &this->m_epSkipForwardButtonClickHandler,
           v12,
           &string);
    v7 = v6;
    if ( v6 < 0 )
      goto LABEL_99;
  }
  v13 = v1->GetTemplateChild;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spComponentAsDO);
  if ( WindowsCreateStringReference(
         L"SkipBackwardButton",
         0x12u,
         (HSTRING_HEADER *)&string._Mystorage._Ptrs[1],
         (HSTRING *)&string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v6 = v13(v1, (HSTRING__ *)string._Mystorage._Ptrs[0], &spComponentAsDO.ptr_);
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_99;
  p_m_tpSkipBackwardButton = &this->m_tpSkipBackwardButton;
  ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::IButton,Windows::UI::Xaml::IDependencyObject>(
    &this->ctl::WeakReferenceSourceNoThreadId,
    &this->m_tpSkipBackwardButton,
    spComponentAsDO.ptr_);
  if ( this->m_tpSkipBackwardButton.m_trackerReference.m_value )
  {
    v15 = DirectUI::DXamlCore::GetCurrent();
    WindowsDeleteString(hstring);
    strAutomationName._hstring = 0;
    LocalizedResourceString = DirectUI::DXamlCore::GetLocalizedResourceString(v15, 0x14BEu, &strAutomationName._hstring);
    v7 = LocalizedResourceString;
    if ( LocalizedResourceString < 0 )
      goto LABEL_15;
    hstring = strAutomationName._hstring;
    v6 = DirectUI::DependencyObject::SetValueByKnownIndex(
           (DirectUI::DependencyObject *)((__int64)&p_m_tpSkipBackwardButton->m_trackerReference.m_value[-79]
                                        & -(__int64)(p_m_tpSkipBackwardButton->m_trackerReference.m_value != 0)),
           AutomationProperties_Name,
           strAutomationName._hstring);
    v7 = v6;
    if ( v6 < 0 )
      goto LABEL_99;
    v6 = DirectUI::MediaTransportControls::AddTooltip(
           (DirectUI::MediaTransportControls *)&p_m_tpSkipBackwardButton->m_trackerReference.m_value[-79],
           (Windows::UI::Xaml::IDependencyObject *)((unsigned __int128)&p_m_tpSkipBackwardButton->m_trackerReference.m_value[-79]
                                                  & ((unsigned __int128)-(__int128)(unsigned __int64)p_m_tpSkipBackwardButton->m_trackerReference.m_value >> 64)),
           hstring);
    v7 = v6;
    if ( v6 < 0 )
      goto LABEL_99;
    string._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)this;
    string._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)std::_Func_impl_no_alloc__lambda_577b008a973ec84d50da5506fc8ebbfa__long_IInspectable___Windows::UI::Xaml::IRoutedEventArgs___::_vftable_;
    string._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)&string;
    v16 = (unsigned __int128)&p_m_tpSkipBackwardButton->m_trackerReference.m_value[-79]
        & ((unsigned __int128)-(__int128)(unsigned __int64)p_m_tpSkipBackwardButton->m_trackerReference.m_value >> 64);
    v17 = v16 ? (Windows::UI::Xaml::Controls::Primitives::IButtonBase *)(v16 + 568) : 0LL;
    v6 = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::ButtonBaseClickTraits>>::AttachEventHandler(
           &this->m_epSkipBackwardButtonClickHandler,
           v17,
           &string);
    v7 = v6;
    if ( v6 < 0 )
      goto LABEL_99;
  }
  v18 = v1->GetTemplateChild;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spComponentAsDO);
  if ( WindowsCreateStringReference(
         L"NextTrackButton",
         0xFu,
         (HSTRING_HEADER *)&string._Mystorage._Ptrs[1],
         (HSTRING *)&string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v6 = v18(v1, (HSTRING__ *)string._Mystorage._Ptrs[0], &spComponentAsDO.ptr_);
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_99;
  p_m_tpNextTrackButton = &this->m_tpNextTrackButton;
  ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::IButton,Windows::UI::Xaml::IDependencyObject>(
    &this->ctl::WeakReferenceSourceNoThreadId,
    &this->m_tpNextTrackButton,
    spComponentAsDO.ptr_);
  if ( this->m_tpNextTrackButton.m_trackerReference.m_value )
  {
    v20 = DirectUI::DXamlCore::GetCurrent();
    WindowsDeleteString(hstring);
    strAutomationName._hstring = 0;
    LocalizedResourceString = DirectUI::DXamlCore::GetLocalizedResourceString(v20, 0x14C9u, &strAutomationName._hstring);
    v7 = LocalizedResourceString;
    if ( LocalizedResourceString < 0 )
      goto LABEL_15;
    hstring = strAutomationName._hstring;
    v6 = DirectUI::DependencyObject::SetValueByKnownIndex(
           (DirectUI::DependencyObject *)((__int64)&p_m_tpNextTrackButton->m_trackerReference.m_value[-79]
                                        & -(__int64)(p_m_tpNextTrackButton->m_trackerReference.m_value != 0)),
           AutomationProperties_Name,
           strAutomationName._hstring);
    v7 = v6;
    if ( v6 < 0 )
      goto LABEL_99;
    v6 = DirectUI::MediaTransportControls::AddTooltip(
           (DirectUI::MediaTransportControls *)&p_m_tpNextTrackButton->m_trackerReference.m_value[-79],
           (Windows::UI::Xaml::IDependencyObject *)((unsigned __int128)&p_m_tpNextTrackButton->m_trackerReference.m_value[-79]
                                                  & ((unsigned __int128)-(__int128)(unsigned __int64)p_m_tpNextTrackButton->m_trackerReference.m_value >> 64)),
           hstring);
    v7 = v6;
    if ( v6 < 0 )
      goto LABEL_99;
    string._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)this;
    string._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)std::_Func_impl_no_alloc__lambda_caf5661827116b15caebce571d244fb7__long_IInspectable___Windows::UI::Xaml::IRoutedEventArgs___::_vftable_;
    string._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)&string;
    v21 = (unsigned __int128)&p_m_tpNextTrackButton->m_trackerReference.m_value[-79]
        & ((unsigned __int128)-(__int128)(unsigned __int64)p_m_tpNextTrackButton->m_trackerReference.m_value >> 64);
    v22 = v21 ? (Windows::UI::Xaml::Controls::Primitives::IButtonBase *)(v21 + 568) : 0LL;
    v6 = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::ButtonBaseClickTraits>>::AttachEventHandler(
           &this->m_epNextTrackButtonClickHandler,
           v22,
           &string);
    v7 = v6;
    if ( v6 < 0 )
      goto LABEL_99;
  }
  v23 = v1->GetTemplateChild;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spComponentAsDO);
  if ( WindowsCreateStringReference(
         L"PreviousTrackButton",
         0x13u,
         (HSTRING_HEADER *)&string._Mystorage._Ptrs[1],
         (HSTRING *)&string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v6 = v23(v1, (HSTRING__ *)string._Mystorage._Ptrs[0], &spComponentAsDO.ptr_);
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_99;
  p_m_tpPreviousTrackButton = &this->m_tpPreviousTrackButton;
  ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::IButton,Windows::UI::Xaml::IDependencyObject>(
    &this->ctl::WeakReferenceSourceNoThreadId,
    &this->m_tpPreviousTrackButton,
    spComponentAsDO.ptr_);
  if ( this->m_tpPreviousTrackButton.m_trackerReference.m_value )
  {
    v25 = DirectUI::DXamlCore::GetCurrent();
    WindowsDeleteString(hstring);
    strAutomationName._hstring = 0;
    LocalizedResourceString = DirectUI::DXamlCore::GetLocalizedResourceString(v25, 0x14CAu, &strAutomationName._hstring);
    v7 = LocalizedResourceString;
    if ( LocalizedResourceString < 0 )
      goto LABEL_15;
    hstring = strAutomationName._hstring;
    v6 = DirectUI::DependencyObject::SetValueByKnownIndex(
           (DirectUI::DependencyObject *)((__int64)&p_m_tpPreviousTrackButton->m_trackerReference.m_value[-79]
                                        & -(__int64)(p_m_tpPreviousTrackButton->m_trackerReference.m_value != 0)),
           AutomationProperties_Name,
           strAutomationName._hstring);
    v7 = v6;
    if ( v6 < 0 )
      goto LABEL_99;
    v6 = DirectUI::MediaTransportControls::AddTooltip(
           (DirectUI::MediaTransportControls *)&p_m_tpPreviousTrackButton->m_trackerReference.m_value[-79],
           (Windows::UI::Xaml::IDependencyObject *)((unsigned __int128)&p_m_tpPreviousTrackButton->m_trackerReference.m_value[-79]
                                                  & ((unsigned __int128)-(__int128)(unsigned __int64)p_m_tpPreviousTrackButton->m_trackerReference.m_value >> 64)),
           hstring);
    v7 = v6;
    if ( v6 < 0 )
      goto LABEL_99;
    string._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)this;
    string._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)std::_Func_impl_no_alloc__lambda_bd04cf2fdc496b76bb6d3fdd8d10d3d1__long_IInspectable___Windows::UI::Xaml::IRoutedEventArgs___::_vftable_;
    string._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)&string;
    v26 = (unsigned __int128)&p_m_tpPreviousTrackButton->m_trackerReference.m_value[-79]
        & ((unsigned __int128)-(__int128)(unsigned __int64)p_m_tpPreviousTrackButton->m_trackerReference.m_value >> 64);
    v27 = v26 ? (Windows::UI::Xaml::Controls::Primitives::IButtonBase *)(v26 + 568) : 0LL;
    v6 = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::ButtonBaseClickTraits>>::AttachEventHandler(
           &this->m_epPreviousTrackButtonClickHandler,
           v27,
           &string);
    v7 = v6;
    if ( v6 < 0 )
      goto LABEL_99;
  }
  v28 = v1->GetTemplateChild;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spComponentAsDO);
  if ( WindowsCreateStringReference(
         L"RepeatButton",
         0xCu,
         (HSTRING_HEADER *)&string._Mystorage._Ptrs[1],
         (HSTRING *)&string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v6 = v28(v1, (HSTRING__ *)string._Mystorage._Ptrs[0], &spComponentAsDO.ptr_);
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_99;
  p_m_tpRepeatButton = &this->m_tpRepeatButton;
  ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::Primitives::IToggleButton,Windows::UI::Xaml::IDependencyObject>(
    &this->ctl::WeakReferenceSourceNoThreadId,
    &this->m_tpRepeatButton,
    spComponentAsDO.ptr_);
  if ( this->m_tpRepeatButton.m_trackerReference.m_value )
  {
    v30 = DirectUI::DXamlCore::GetCurrent();
    WindowsDeleteString(hstring);
    strAutomationName._hstring = 0;
    LocalizedResourceString = DirectUI::DXamlCore::GetLocalizedResourceString(v30, 0x14DBu, &strAutomationName._hstring);
    v7 = LocalizedResourceString;
    if ( LocalizedResourceString < 0 )
      goto LABEL_15;
    hstring = strAutomationName._hstring;
    v6 = DirectUI::DependencyObject::SetValueByKnownIndex(
           (DirectUI::DependencyObject *)((__int64)&p_m_tpRepeatButton->m_trackerReference.m_value[-79]
                                        & -(__int64)(p_m_tpRepeatButton->m_trackerReference.m_value != 0)),
           AutomationProperties_Name,
           strAutomationName._hstring);
    v7 = v6;
    if ( v6 < 0 )
      goto LABEL_99;
    v6 = DirectUI::MediaTransportControls::AddTooltip(
           (DirectUI::MediaTransportControls *)&p_m_tpRepeatButton->m_trackerReference.m_value[-79],
           (Windows::UI::Xaml::IDependencyObject *)((unsigned __int128)&p_m_tpRepeatButton->m_trackerReference.m_value[-79]
                                                  & ((unsigned __int128)-(__int128)(unsigned __int64)p_m_tpRepeatButton->m_trackerReference.m_value >> 64)),
           hstring);
    v7 = v6;
    if ( v6 < 0 )
      goto LABEL_99;
    string._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)this;
    string._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)std::_Func_impl_no_alloc__lambda_13d95a5040e4ac57437640b360cd9873__long_IInspectable___Windows::UI::Xaml::IRoutedEventArgs___::_vftable_;
    string._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)&string;
    v31 = (unsigned __int128)&p_m_tpRepeatButton->m_trackerReference.m_value[-79]
        & ((unsigned __int128)-(__int128)(unsigned __int64)p_m_tpRepeatButton->m_trackerReference.m_value >> 64);
    v32 = v31 ? (Windows::UI::Xaml::Controls::Primitives::IButtonBase *)(v31 + 568) : 0LL;
    v6 = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::ButtonBaseClickTraits>>::AttachEventHandler(
           &this->m_epRepeatButtonClickHandler,
           v32,
           &string);
    v7 = v6;
    if ( v6 < 0 )
      goto LABEL_99;
  }
  v33 = v1->GetTemplateChild;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spComponentAsDO);
  if ( WindowsCreateStringReference(
         L"CompactOverlayButton",
         0x14u,
         (HSTRING_HEADER *)&string._Mystorage._Ptrs[1],
         (HSTRING *)&string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v6 = v33(v1, (HSTRING__ *)string._Mystorage._Ptrs[0], &spComponentAsDO.ptr_);
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_99;
  p_m_tpCompactOverlayButton = &this->m_tpCompactOverlayButton;
  ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::IButton,Windows::UI::Xaml::IDependencyObject>(
    &this->ctl::WeakReferenceSourceNoThreadId,
    &this->m_tpCompactOverlayButton,
    spComponentAsDO.ptr_);
  if ( !this->m_tpCompactOverlayButton.m_trackerReference.m_value )
    goto LABEL_91;
  v35 = DirectUI::DXamlCore::GetCurrent();
  WindowsDeleteString(hstring);
  strAutomationName._hstring = 0;
  LocalizedResourceString = DirectUI::DXamlCore::GetLocalizedResourceString(v35, 0x1596u, &strAutomationName._hstring);
  v7 = LocalizedResourceString;
  if ( LocalizedResourceString < 0 )
  {
LABEL_15:
    OnFailure_2990_(LocalizedResourceString);
    hstring = strAutomationName._hstring;
    goto LABEL_100;
  }
  hstring = strAutomationName._hstring;
  v6 = DirectUI::DependencyObject::SetValueByKnownIndex(
         (DirectUI::DependencyObject *)((__int64)&p_m_tpCompactOverlayButton->m_trackerReference.m_value[-79]
                                      & -(__int64)(p_m_tpCompactOverlayButton->m_trackerReference.m_value != 0)),
         AutomationProperties_Name,
         strAutomationName._hstring);
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_99;
  v6 = DirectUI::MediaTransportControls::AddTooltip(
         (DirectUI::MediaTransportControls *)&p_m_tpCompactOverlayButton->m_trackerReference.m_value[-79],
         (Windows::UI::Xaml::IDependencyObject *)((unsigned __int128)&p_m_tpCompactOverlayButton->m_trackerReference.m_value[-79]
                                                & ((unsigned __int128)-(__int128)(unsigned __int64)p_m_tpCompactOverlayButton->m_trackerReference.m_value >> 64)),
         hstring);
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_99;
  string._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)this;
  string._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)std::_Func_impl_no_alloc__lambda_909e20c958de1ad7293ffe73b717b9bb__long_IInspectable___Windows::UI::Xaml::IRoutedEventArgs___::_vftable_;
  string._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)&string;
  v36 = (unsigned __int128)&p_m_tpCompactOverlayButton->m_trackerReference.m_value[-79]
      & ((unsigned __int128)-(__int128)(unsigned __int64)p_m_tpCompactOverlayButton->m_trackerReference.m_value >> 64);
  v37 = v36 ? (Windows::UI::Xaml::Controls::Primitives::IButtonBase *)(v36 + 568) : 0LL;
  v6 = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::ButtonBaseClickTraits>>::AttachEventHandler(
         &this->m_epCompactOverlayButtonClickHandler,
         v37,
         &string);
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_99;
LABEL_91:
  v38 = v1->GetTemplateChild;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spComponentAsDO);
  Windows::Internal::StringReference::StringReference(
    (Windows::Internal::StringReference *)&string,
    (const wchar_t (*)[14])L"LeftSeparator");
  v6 = v38(v1, *v39, &spComponentAsDO.ptr_);
  v7 = v6;
  if ( v6 < 0
    || (ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::IAppBarSeparator,Windows::UI::Xaml::IDependencyObject>(
          &this->ctl::WeakReferenceSourceNoThreadId,
          &this->m_tpLeftAppBarSeparator,
          spComponentAsDO.ptr_),
        v40 = v1->GetTemplateChild,
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spComponentAsDO),
        Windows::Internal::StringReference::StringReference(
          (Windows::Internal::StringReference *)&string,
          (const wchar_t (*)[15])L"RightSeparator"),
        v6 = v40(v1, *v41, &spComponentAsDO.ptr_),
        v7 = v6,
        v6 < 0) )
  {
LABEL_99:
    OnFailure_2990_(v6);
    goto LABEL_100;
  }
  ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::IAppBarSeparator,Windows::UI::Xaml::IDependencyObject>(
    &this->ctl::WeakReferenceSourceNoThreadId,
    &this->m_tpRightAppBarSeparator,
    spComponentAsDO.ptr_);
  if ( this->m_tpCommandBar.m_trackerReference.m_value )
  {
LABEL_100:
    ptr = spVisibilityStatesGroup.ptr_;
    goto $Cleanup_2980;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spVisibilityStatesGroup);
  v42 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::IVisualStateGroup,Windows::UI::Xaml::IVisualStateGroup>(
          this,
          (wchar_t *)L"ControlPanelVisibilityStates",
          0x1Cu,
          &spVisibilityStatesGroup.ptr_);
  v7 = v42;
  if ( v42 < 0 )
  {
    OnFailure_2990_(v42);
    goto LABEL_100;
  }
  ptr = spVisibilityStatesGroup.ptr_;
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    &this->ctl::WeakReferenceSourceNoThreadId,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->m_tpVisibilityStatesGroup,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spVisibilityStatesGroup.ptr_);
  m_value = (Windows::UI::Xaml::IVisualStateGroup *)this->m_tpVisibilityStatesGroup.m_trackerReference.m_value;
  if ( m_value )
  {
    string._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)this;
    string._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)std::_Func_impl_no_alloc__lambda_ff6bdd296eaeb6231688c7a85a21cc1b__long_IInspectable___Windows::UI::Xaml::IVisualStateChangedEventArgs___::_vftable_;
    string._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *> *)&string;
    v45 = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IVisualStateChangedEventHandler,IInspectable,Windows::UI::Xaml::IVisualStateChangedEventArgs,DirectUI::VisualStateGroupCurrentStateChangedTraits>>::AttachEventHandler(
            &this->m_visibilityStateChangedEventHandler,
            m_value,
            (std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::IVisualStateChangedEventArgs *)> *)&string);
    v7 = v45;
    if ( v45 < 0 )
      OnFailure_2990_(v45);
  }
$Cleanup_2980:
  if ( ptr )
    ptr->Release(ptr);
  if ( hstring )
    WindowsDeleteString(hstring);
  v46 = spComponentAsDO.ptr_;
  if ( spComponentAsDO.ptr_ )
  {
    spComponentAsDO.ptr_ = 0;
    v46->Release(v46);
  }
  return v7;
}

```

## disassembly

```asm
0x18042b550  push    rbp
0x18042b552  push    rbx
0x18042b553  push    rsi
0x18042b554  push    rdi
0x18042b555  push    r12
0x18042b557  push    r13
0x18042b559  push    r14
0x18042b55b  push    r15
0x18042b55d  lea     rbp, [rsp-1Fh]
0x18042b562  sub     rsp, 88h
0x18042b569  mov     rax, cs:__security_cookie
0x18042b570  xor     rax, rsp
0x18042b573  mov     [rbp+57h+var_48], rax
0x18042b577  lea     r12, [this+1C8h]
0x18042b57e  mov     [rbp+57h+spComponentAsDO.ptr_], 0
0x18042b586  mov     rax, [r12]
0x18042b58a  mov     r14, this
0x18042b58d  xor     esi, esi
0x18042b58f  lea     this, [rbp+57h+spComponentAsDO]; this
0x18042b593  mov     [rbp+57h+strAutomationName._hstring], rsi
0x18042b597  mov     [rbp+57h+spVisibilityStatesGroup.ptr_], rsi
0x18042b59b  mov     rbx, [rax+40h]
0x18042b59f  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18042b5a4  lea     r9, [rbp+57h+string]; string
0x18042b5a8  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18042b5ac  lea     edx, [rsi+11h]; length
0x18042b5af  lea     this, aSkipforwardbut; "SkipForwardButton"
0x18042b5b6  call    cs:__imp_WindowsCreateStringReference
0x18042b5bc  test    eax, eax
0x18042b5be  jns     short loc_18042B5D4
0x18042b5c0  xor     r9d, r9d; lpArguments
0x18042b5c3  lea     edx, [rsi+1]; dwExceptionFlags
0x18042b5c6  xor     r8d, r8d; nNumberOfArguments
0x18042b5c9  mov     ecx, 0C000000Dh; dwExceptionCode
0x18042b5ce  call    cs:__imp_RaiseException
0x18042b5d4  mov     rdx, [rbp+57h+string]
0x18042b5d8  lea     r8, [rbp+57h+spComponentAsDO]
0x18042b5dc  mov     this, r12
0x18042b5df  mov     rax, rbx
0x18042b5e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042b5e7  mov     edi, eax
0x18042b5e9  test    eax, eax
0x18042b5eb  js      loc_18042C00D
0x18042b5f1  mov     r8, [rbp+57h+spComponentAsDO.ptr_]; value
0x18042b5f5  lea     r13, [r14+8]
0x18042b5f9  lea     r15, [r14+650h]
0x18042b600  mov     this, r13; this
0x18042b603  mov     rdx, r15; ptr
0x18042b606  call    ??$SetPtrValueWithQIOrNull@UIButton@Controls@Xaml@UI@Windows@@UIDependencyObject@345@@WeakReferenceSourceNoThreadId@ctl@@IEAAXAEAV?$TrackerPtr@UIButton@Controls@Xaml@UI@Windows@@$00$0A@@DirectUI@@PEAUIDependencyObject@Xaml@UI@Windows@@@Z; ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::IButton,Windows::UI::Xaml::IDependencyObject>(DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::IButton,1,0> &,Windows::UI::Xaml::IDependencyObject *)
0x18042b60b  cmp     [r15], rsi
0x18042b60e  jz      loc_18042B70F
0x18042b614  call    ?GetCurrent@DXamlCore@DirectUI@@SAPEAV12@XZ; DirectUI::DXamlCore::GetCurrent(void)
0x18042b619  xor     ecx, ecx; string
0x18042b61b  mov     rbx, rax
0x18042b61e  call    cs:__imp_WindowsDeleteString
0x18042b624  lea     r8, [rbp+57h+strAutomationName]; resourceString
0x18042b628  mov     edx, 14C8h; resourceStringID
0x18042b62d  mov     this, rbx; this
0x18042b630  call    ?GetLocalizedResourceString@DXamlCore@DirectUI@@QEAAJIPEAPEAUHSTRING__@@@Z; DirectUI::DXamlCore::GetLocalizedResourceString(uint,HSTRING__ * *)
0x18042b635  mov     edi, eax
0x18042b637  test    eax, eax
0x18042b639  js      loc_18042B6FF
0x18042b63f  mov     this, [r15]
0x18042b642  mov     edx, 22h ; '"'; nPropertyIndex
0x18042b647  mov     rsi, [rbp+57h+strAutomationName._hstring]
0x18042b64b  mov     r8, rsi; value
0x18042b64e  lea     rax, [this-278h]
0x18042b655  neg     this
0x18042b658  sbb     this, this
0x18042b65b  and     this, rax; this
0x18042b65e  call    ?SetValueByKnownIndex@DependencyObject@DirectUI@@QEAAJW4KnownPropertyIndex@@PEAUHSTRING__@@@Z; DirectUI::DependencyObject::SetValueByKnownIndex(KnownPropertyIndex,HSTRING__ *)
0x18042b663  mov     edi, eax
0x18042b665  test    eax, eax
0x18042b667  js      loc_18042B6F3
0x18042b66d  mov     rax, [r15]
0x18042b670  mov     r8, rsi; hstrTooltipText
0x18042b673  lea     this, [rax-278h]; this
0x18042b67a  neg     rax
0x18042b67d  sbb     rdx, rdx
0x18042b680  and     rdx, this; pTooltipTarget
0x18042b683  call    ?AddTooltip@MediaTransportControls@DirectUI@@AEAAJPEAUIDependencyObject@Xaml@UI@Windows@@PEAUHSTRING__@@@Z; DirectUI::MediaTransportControls::AddTooltip(Windows::UI::Xaml::IDependencyObject *,HSTRING__ *)
0x18042b688  mov     edi, eax
0x18042b68a  test    eax, eax
0x18042b68c  js      short loc_18042B6E7
0x18042b68e  lea     rax, std___Func_impl_no_alloc__lambda_a093af20e0133ec21989a1cdec032b04__long_IInspectable___Windows__UI__Xaml__IRoutedEventArgs______vftable_
0x18042b695  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r14
0x18042b699  mov     [rbp+57h+string], rax
0x18042b69d  lea     rax, [rbp+57h+string]
0x18042b6a1  mov     [rbp+57h+var_50], rax
0x18042b6a5  mov     rax, [r15]
0x18042b6a8  lea     this, [rax-278h]
0x18042b6af  neg     rax
0x18042b6b2  sbb     rdx, rdx
0x18042b6b5  and     rdx, this
0x18042b6b8  jz      short loc_18042B6C3
0x18042b6ba  add     rdx, 238h
0x18042b6c1  jmp     short loc_18042B6C5
0x18042b6c3  xor     edx, edx
0x18042b6c5  lea     this, [r14+8F8h]
0x18042b6cc  lea     r8, [rbp+57h+string]
0x18042b6d0  call    ?AttachEventHandler@?$EventPtr@V?$event_handler@UIRoutedEventHandler@Xaml@UI@Windows@@UIInspectable@@UIRoutedEventArgs@234@UButtonBaseClickTraits@DirectUI@@@ctl@@@ctl@@QEAAJPEAUIButtonBase@Primitives@Controls@Xaml@UI@Windows@@V?$function@$$A6AJPEAUIInspectable@@PEAUIRoutedEventArgs@Xaml@UI@Windows@@@Z@std@@@Z; ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::ButtonBaseClickTraits>>::AttachEventHandler(Windows::UI::Xaml::Controls::Primitives::IButtonBase *,std::function<long (IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *)>)
0x18042b6d5  mov     edi, eax
0x18042b6d7  test    eax, eax
0x18042b6d9  jns     short loc_18042B70F
0x18042b6db  mov     ecx, eax; failedFrameHR
0x18042b6dd  call    OnFailure_2990_
0x18042b6e2  jmp     loc_18042C014
0x18042b6e7  mov     ecx, eax; failedFrameHR
0x18042b6e9  call    OnFailure_2990_
0x18042b6ee  jmp     loc_18042C014
0x18042b6f3  mov     ecx, eax; failedFrameHR
0x18042b6f5  call    OnFailure_2990_
0x18042b6fa  jmp     loc_18042C014
0x18042b6ff  mov     ecx, eax; failedFrameHR
0x18042b701  call    OnFailure_2990_
0x18042b706  mov     rsi, [rbp+57h+strAutomationName._hstring]
0x18042b70a  jmp     loc_18042C014
0x18042b70f  mov     rax, [r12]
0x18042b713  lea     this, [rbp+57h+spComponentAsDO]; this
0x18042b717  mov     rbx, [rax+40h]
0x18042b71b  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18042b720  lea     r9, [rbp+57h+string]; string
0x18042b724  mov     edx, 12h; length
0x18042b729  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18042b72d  lea     this, aSkipbackwardbu; "SkipBackwardButton"
0x18042b734  call    cs:__imp_WindowsCreateStringReference
0x18042b73a  test    eax, eax
0x18042b73c  jns     short loc_18042B753
0x18042b73e  xor     r9d, r9d; lpArguments
0x18042b741  xor     r8d, r8d; nNumberOfArguments
0x18042b744  mov     ecx, 0C000000Dh; dwExceptionCode
0x18042b749  lea     edx, [r9+1]; dwExceptionFlags
0x18042b74d  call    cs:__imp_RaiseException
0x18042b753  mov     rdx, [rbp+57h+string]
0x18042b757  lea     r8, [rbp+57h+spComponentAsDO]
0x18042b75b  mov     this, r12
0x18042b75e  mov     rax, rbx
0x18042b761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042b766  mov     edi, eax
0x18042b768  test    eax, eax
0x18042b76a  js      loc_18042C004
0x18042b770  mov     r8, [rbp+57h+spComponentAsDO.ptr_]; value
0x18042b774  lea     r15, [r14+668h]
0x18042b77b  mov     rdx, r15; ptr
0x18042b77e  mov     this, r13; this
0x18042b781  call    ??$SetPtrValueWithQIOrNull@UIButton@Controls@Xaml@UI@Windows@@UIDependencyObject@345@@WeakReferenceSourceNoThreadId@ctl@@IEAAXAEAV?$TrackerPtr@UIButton@Controls@Xaml@UI@Windows@@$00$0A@@DirectUI@@PEAUIDependencyObject@Xaml@UI@Windows@@@Z; ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::IButton,Windows::UI::Xaml::IDependencyObject>(DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::IButton,1,0> &,Windows::UI::Xaml::IDependencyObject *)
0x18042b786  cmp     qword ptr [r15], 0
0x18042b78a  jz      loc_18042B890
0x18042b790  call    ?GetCurrent@DXamlCore@DirectUI@@SAPEAV12@XZ; DirectUI::DXamlCore::GetCurrent(void)
0x18042b795  mov     this, rsi; string
0x18042b798  mov     rbx, rax
0x18042b79b  call    cs:__imp_WindowsDeleteString
0x18042b7a1  lea     r8, [rbp+57h+strAutomationName]; resourceString
0x18042b7a5  mov     [rbp+57h+strAutomationName._hstring], 0
0x18042b7ad  mov     edx, 14BEh; resourceStringID
0x18042b7b2  mov     this, rbx; this
0x18042b7b5  call    ?GetLocalizedResourceString@DXamlCore@DirectUI@@QEAAJIPEAPEAUHSTRING__@@@Z; DirectUI::DXamlCore::GetLocalizedResourceString(uint,HSTRING__ * *)
0x18042b7ba  mov     edi, eax
0x18042b7bc  test    eax, eax
0x18042b7be  js      loc_18042B884
0x18042b7c4  mov     this, [r15]
0x18042b7c7  mov     edx, 22h ; '"'; nPropertyIndex
0x18042b7cc  mov     rsi, [rbp+57h+strAutomationName._hstring]
0x18042b7d0  mov     r8, rsi; value
0x18042b7d3  lea     rax, [this-278h]
0x18042b7da  neg     this
0x18042b7dd  sbb     this, this
0x18042b7e0  and     this, rax; this
0x18042b7e3  call    ?SetValueByKnownIndex@DependencyObject@DirectUI@@QEAAJW4KnownPropertyIndex@@PEAUHSTRING__@@@Z; DirectUI::DependencyObject::SetValueByKnownIndex(KnownPropertyIndex,HSTRING__ *)
0x18042b7e8  mov     edi, eax
0x18042b7ea  test    eax, eax
0x18042b7ec  js      loc_18042B878
0x18042b7f2  mov     rax, [r15]
0x18042b7f5  mov     r8, rsi; hstrTooltipText
0x18042b7f8  lea     this, [rax-278h]; this
0x18042b7ff  neg     rax
0x18042b802  sbb     rdx, rdx
0x18042b805  and     rdx, this; pTooltipTarget
0x18042b808  call    ?AddTooltip@MediaTransportControls@DirectUI@@AEAAJPEAUIDependencyObject@Xaml@UI@Windows@@PEAUHSTRING__@@@Z; DirectUI::MediaTransportControls::AddTooltip(Windows::UI::Xaml::IDependencyObject *,HSTRING__ *)
0x18042b80d  mov     edi, eax
0x18042b80f  test    eax, eax
0x18042b811  js      short loc_18042B86C
0x18042b813  lea     rax, std___Func_impl_no_alloc__lambda_577b008a973ec84d50da5506fc8ebbfa__long_IInspectable___Windows__UI__Xaml__IRoutedEventArgs______vftable_
0x18042b81a  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r14
0x18042b81e  mov     [rbp+57h+string], rax
0x18042b822  lea     rax, [rbp+57h+string]
0x18042b826  mov     [rbp+57h+var_50], rax
0x18042b82a  mov     rax, [r15]
0x18042b82d  lea     this, [rax-278h]
0x18042b834  neg     rax
0x18042b837  sbb     rdx, rdx
0x18042b83a  and     rdx, this
0x18042b83d  jz      short loc_18042B848
0x18042b83f  add     rdx, 238h
0x18042b846  jmp     short loc_18042B84A
0x18042b848  xor     edx, edx
0x18042b84a  lea     this, [r14+900h]
0x18042b851  lea     r8, [rbp+57h+string]
0x18042b855  call    ?AttachEventHandler@?$EventPtr@V?$event_handler@UIRoutedEventHandler@Xaml@UI@Windows@@UIInspectable@@UIRoutedEventArgs@234@UButtonBaseClickTraits@DirectUI@@@ctl@@@ctl@@QEAAJPEAUIButtonBase@Primitives@Controls@Xaml@UI@Windows@@V?$function@$$A6AJPEAUIInspectable@@PEAUIRoutedEventArgs@Xaml@UI@Windows@@@Z@std@@@Z; ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::ButtonBaseClickTraits>>::AttachEventHandler(Windows::UI::Xaml::Controls::Primitives::IButtonBase *,std::function<long (IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *)>)
0x18042b85a  mov     edi, eax
0x18042b85c  test    eax, eax
0x18042b85e  jns     short loc_18042B890
0x18042b860  mov     ecx, eax; failedFrameHR
0x18042b862  call    OnFailure_2990_
0x18042b867  jmp     loc_18042C014
0x18042b86c  mov     ecx, eax; failedFrameHR
0x18042b86e  call    OnFailure_2990_
0x18042b873  jmp     loc_18042C014
0x18042b878  mov     ecx, eax; failedFrameHR
0x18042b87a  call    OnFailure_2990_
0x18042b87f  jmp     loc_18042C014
0x18042b884  mov     ecx, eax; failedFrameHR
0x18042b886  call    OnFailure_2990_
0x18042b88b  jmp     loc_18042B706
0x18042b890  mov     rax, [r12]
0x18042b894  lea     this, [rbp+57h+spComponentAsDO]; this
0x18042b898  mov     rbx, [rax+40h]
0x18042b89c  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18042b8a1  lea     r9, [rbp+57h+string]; string
0x18042b8a5  mov     edx, 0Fh; length
0x18042b8aa  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18042b8ae  lea     this, aNexttrackbutto; "NextTrackButton"
0x18042b8b5  call    cs:__imp_WindowsCreateStringReference
0x18042b8bb  test    eax, eax
0x18042b8bd  jns     short loc_18042B8D4
0x18042b8bf  xor     r9d, r9d; lpArguments
0x18042b8c2  xor     r8d, r8d; nNumberOfArguments
0x18042b8c5  mov     ecx, 0C000000Dh; dwExceptionCode
0x18042b8ca  lea     edx, [r9+1]; dwExceptionFlags
0x18042b8ce  call    cs:__imp_RaiseException
0x18042b8d4  mov     rdx, [rbp+57h+string]
0x18042b8d8  lea     r8, [rbp+57h+spComponentAsDO]
0x18042b8dc  mov     this, r12
0x18042b8df  mov     rax, rbx
0x18042b8e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042b8e7  mov     edi, eax
0x18042b8e9  test    eax, eax
0x18042b8eb  js      loc_18042BFFB
0x18042b8f1  mov     r8, [rbp+57h+spComponentAsDO.ptr_]; value
0x18042b8f5  lea     r15, [r14+680h]
0x18042b8fc  mov     rdx, r15; ptr
0x18042b8ff  mov     this, r13; this
0x18042b902  call    ??$SetPtrValueWithQIOrNull@UIButton@Controls@Xaml@UI@Windows@@UIDependencyObject@345@@WeakReferenceSourceNoThreadId@ctl@@IEAAXAEAV?$TrackerPtr@UIButton@Controls@Xaml@UI@Windows@@$00$0A@@DirectUI@@PEAUIDependencyObject@Xaml@UI@Windows@@@Z; ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::IButton,Windows::UI::Xaml::IDependencyObject>(DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::IButton,1,0> &,Windows::UI::Xaml::IDependencyObject *)
0x18042b907  cmp     qword ptr [r15], 0
0x18042b90b  jz      loc_18042BA11
0x18042b911  call    ?GetCurrent@DXamlCore@DirectUI@@SAPEAV12@XZ; DirectUI::DXamlCore::GetCurrent(void)
0x18042b916  mov     this, rsi; string
0x18042b919  mov     rbx, rax
0x18042b91c  call    cs:__imp_WindowsDeleteString
0x18042b922  lea     r8, [rbp+57h+strAutomationName]; resourceString
0x18042b926  mov     [rbp+57h+strAutomationName._hstring], 0
0x18042b92e  mov     edx, 14C9h; resourceStringID
0x18042b933  mov     this, rbx; this
0x18042b936  call    ?GetLocalizedResourceString@DXamlCore@DirectUI@@QEAAJIPEAPEAUHSTRING__@@@Z; DirectUI::DXamlCore::GetLocalizedResourceString(uint,HSTRING__ * *)
0x18042b93b  mov     edi, eax
0x18042b93d  test    eax, eax
0x18042b93f  js      loc_18042BA05
0x18042b945  mov     this, [r15]
0x18042b948  mov     edx, 22h ; '"'; nPropertyIndex
0x18042b94d  mov     rsi, [rbp+57h+strAutomationName._hstring]
0x18042b951  mov     r8, rsi; value
0x18042b954  lea     rax, [this-278h]
0x18042b95b  neg     this
0x18042b95e  sbb     this, this
0x18042b961  and     this, rax; this
0x18042b964  call    ?SetValueByKnownIndex@DependencyObject@DirectUI@@QEAAJW4KnownPropertyIndex@@PEAUHSTRING__@@@Z; DirectUI::DependencyObject::SetValueByKnownIndex(KnownPropertyIndex,HSTRING__ *)
0x18042b969  mov     edi, eax
0x18042b96b  test    eax, eax
0x18042b96d  js      loc_18042B9F9
0x18042b973  mov     rax, [r15]
0x18042b976  mov     r8, rsi; hstrTooltipText
0x18042b979  lea     this, [rax-278h]; this
0x18042b980  neg     rax
0x18042b983  sbb     rdx, rdx
0x18042b986  and     rdx, this; pTooltipTarget
0x18042b989  call    ?AddTooltip@MediaTransportControls@DirectUI@@AEAAJPEAUIDependencyObject@Xaml@UI@Windows@@PEAUHSTRING__@@@Z; DirectUI::MediaTransportControls::AddTooltip(Windows::UI::Xaml::IDependencyObject *,HSTRING__ *)
0x18042b98e  mov     edi, eax
0x18042b990  test    eax, eax
0x18042b992  js      short loc_18042B9ED
0x18042b994  lea     rax, std___Func_impl_no_alloc__lambda_caf5661827116b15caebce571d244fb7__long_IInspectable___Windows__UI__Xaml__IRoutedEventArgs______vftable_
0x18042b99b  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r14
0x18042b99f  mov     [rbp+57h+string], rax
0x18042b9a3  lea     rax, [rbp+57h+string]
0x18042b9a7  mov     [rbp+57h+var_50], rax
0x18042b9ab  mov     rax, [r15]
0x18042b9ae  lea     this, [rax-278h]
0x18042b9b5  neg     rax
0x18042b9b8  sbb     rdx, rdx
0x18042b9bb  and     rdx, this
0x18042b9be  jz      short loc_18042B9C9
0x18042b9c0  add     rdx, 238h
0x18042b9c7  jmp     short loc_18042B9CB
0x18042b9c9  xor     edx, edx
0x18042b9cb  lea     this, [r14+908h]
0x18042b9d2  lea     r8, [rbp+57h+string]
0x18042b9d6  call    ?AttachEventHandler@?$EventPtr@V?$event_handler@UIRoutedEventHandler@Xaml@UI@Windows@@UIInspectable@@UIRoutedEventArgs@234@UButtonBaseClickTraits@DirectUI@@@ctl@@@ctl@@QEAAJPEAUIButtonBase@Primitives@Controls@Xaml@UI@Windows@@V?$function@$$A6AJPEAUIInspectable@@PEAUIRoutedEventArgs@Xaml@UI@Windows@@@Z@std@@@Z; ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::ButtonBaseClickTraits>>::AttachEventHandler(Windows::UI::Xaml::Controls::Primitives::IButtonBase *,std::function<long (IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *)>)
0x18042b9db  mov     edi, eax
0x18042b9dd  test    eax, eax
0x18042b9df  jns     short loc_18042BA11
0x18042b9e1  mov     ecx, eax; failedFrameHR
  ... truncated ...
```
