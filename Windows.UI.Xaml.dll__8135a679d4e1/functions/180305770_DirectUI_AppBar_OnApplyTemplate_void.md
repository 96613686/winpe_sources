# DirectUI::AppBar::OnApplyTemplate(void)

- ea: `0x180305770`
- end: `0x180306845`
- name: `?OnApplyTemplate@AppBar@DirectUI@@UEAAJXZ`
- size: `4309`
- prototype: `HRESULT __fastcall(DirectUI::AppBar *this)`
- caller_count: `1`
- callee_count: `28`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1803d82c4`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x18005bcac`
- `0x18005e96c`
- `0x18009a16c`
- `0x18009ba40`
- `0x1800c41e0`
- `0x1800d4a38`
- `0x1800f4510`
- `0x180101870`
- `0x1801df610`
- `0x1801e5458`
- `0x1802490f0`
- `0x180304634`
- `0x180304c94`
- `0x180305124`
- `0x180305770`
- `0x18037f708`
- `0x1803805dc`
- `0x1803839c0`
- `0x18049b4e8`
- `0x18064b94c`
- `0x180688828`
- `0x1806b9b44`
- `0x1806cdd00`
- `0x180704588`
- `0x18076e110`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180306617`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1803066bf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180306753`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18030677b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180306617`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1803066bf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180306753`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18030677b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180305992`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180305a16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180305a6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180305a92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803060f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18030611d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180306503`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180305992`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180305a16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180305a6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180305a92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803060f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18030611d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180306503`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180305b31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180305ba5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180305d02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180305e4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180305b31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180305ba5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180305d02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180305e4d`

## string_xrefs

- `0x180305cfb`: `OverlayOpeningAnimation`
- `0x180305b2a`: `AppBarThemeCompactHeight`

## pseudocode

```c
__int64 __fastcall DirectUI::AppBar::OnApplyTemplate(DirectUI::AppBar *this)
{
  ctl::forwarder_holder<Windows::UI::Xaml::IUIElementOverrides9,DirectUI::UIElementGenerated> *v1; // rbx
  DirectUI::TrackerPtr<Windows::UI::Xaml::Automation::Peers::IAutomationPeer,0,0> *p_m_tpAP; // rdi
  HRESULT v4; // eax
  unsigned int v5; // esi
  HRESULT v6; // eax
  HRESULT v7; // esi
  Windows::UI::Xaml::Controls::IGrid *ptr; // r15
  HRESULT v9; // eax
  Windows::UI::Xaml::IFrameworkElement *v10; // r12
  const std::_Ph<1> *v11; // r8
  const std::_Ph<2> *v12; // r9
  HRESULT v13; // eax
  unsigned int v14; // ebx
  Windows::UI::Xaml::Controls::Primitives::IButtonBase *v15; // r14
  Windows::UI::Xaml::Media::Animation::IStoryboard *v16; // rsi
  const std::_Ph<1> *v17; // r8
  const std::_Ph<2> *v18; // r9
  Windows::UI::Xaml::Controls::Primitives::IButtonBase *m_value; // rdx
  HRESULT v20; // eax
  DirectUI::DXamlCore *Current; // rbx
  HRESULT LocalizedResourceString; // eax
  HSTRING__ *hstring; // rbx
  HRESULT v24; // eax
  IUnknown *v25; // rdi
  IInspectable *v26; // rsi
  const CDependencyProperty *DependencyPropertyByIndex; // rax
  HRESULT v28; // eax
  HRESULT v29; // edi
  HRESULT ValueByKnownIndex; // eax
  unsigned int v31; // edi
  HSTRING__ *v32; // rdi
  IInspectable *v33; // rcx
  __int64 v34; // rax
  __int64 (__fastcall *v35)(char *, ctl::ComPtr<Windows::UI::Xaml::IResourceDictionary> *); // rbx
  HRESULT v36; // eax
  HRESULT v37; // eax
  HRESULT v38; // eax
  IInspectable *v39; // rcx
  IInspectable *v40; // rcx
  Windows::Foundation::Collections::IMap<IInspectable *,IInspectable *> *v41; // rcx
  Windows::UI::Xaml::IResourceDictionary *v42; // rcx
  ctl::interface_forwarder<Windows::UI::Xaml::IUIElement8,DirectUI::UIElementGenerated>_vtbl *v43; // rdi
  __int64 (__fastcall *v44)(_QWORD, ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *); // rbx
  HRESULT v45; // eax
  HRESULT v46; // eax
  HRESULT v47; // eax
  Windows::UI::Core::ICoreWindow5 *v48; // rdi
  HRESULT (__fastcall *get_DispatcherQueue)(Windows::UI::Core::ICoreWindow5 *, Windows::System::IDispatcherQueue **); // rbx
  HRESULT v50; // eax
  HRESULT v51; // eax
  ctl::WeakReferenceSourceNoThreadId *p_m_tpLayoutRoot; // rsi
  Windows::UI::Xaml::Media::Animation::IStoryboard *v53; // rcx
  Windows::UI::Core::ICoreWindow5 *v54; // rcx
  IInspectable *v55; // rcx
  HRESULT v56; // eax
  HRESULT v57; // eax
  Windows::UI::Core::ICoreWindow5 *v58; // rdi
  HRESULT (__fastcall *v59)(Windows::UI::Core::ICoreWindow5 *, Windows::System::IDispatcherQueue **); // rbx
  HRESULT v60; // eax
  HRESULT v61; // eax
  HSTRING__ *v62; // rcx
  HSTRING__ *v63; // rcx
  IInspectable *v64; // rcx
  Windows::UI::Core::ICoreWindow5 *v65; // rcx
  Windows::UI::Core::ICoreWindow5 *v66; // rcx
  HRESULT IsOverlayVisible; // eax
  Windows::UI::Core::ICoreWindow5 *v69; // rcx
  IInspectable *v70; // rcx
  Windows::UI::Core::ICoreWindow5 *v71; // rcx
  void *v72; // rcx
  IInspectable *v73; // rcx
  HSTRING__ *v74; // rcx
  HSTRING__ *v75; // rcx
  IInspectable *v76; // rcx
  Windows::UI::Core::ICoreWindow5 *v77; // rcx
  Windows::Foundation::Collections::IMap<IInspectable *,IInspectable *> *v78; // rdi
  HRESULT (__fastcall *v79)(Windows::Foundation::Collections::IMap_impl<IInspectable *,IInspectable *> *, IInspectable *, IInspectable **); // rbx
  HRESULT v80; // ecx
  Windows::UI::Xaml::Media::Animation::IStoryboard *v81; // rbx
  HRESULT v82; // eax
  Windows::UI::Xaml::IFrameworkElement *v83; // rdx
  HRESULT v84; // eax
  IInspectable *v85; // rcx
  IInspectable *v86; // rcx
  Windows::Foundation::Collections::IMap<IInspectable *,IInspectable *> *v87; // rcx
  HRESULT v88; // eax
  DirectUI::DXamlCore *v89; // rdi
  HRESULT v90; // eax
  HRESULT v91; // eax
  ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *p_resources; // rcx
  Windows::Foundation::Collections::IMap<IInspectable *,IInspectable *> *v93; // rdi
  HRESULT (__fastcall *Lookup)(Windows::Foundation::Collections::IMap_impl<IInspectable *,IInspectable *> *, IInspectable *, IInspectable **); // rbx
  HRESULT v95; // eax
  ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *p_automationName; // rcx
  unsigned __int8 doesResourceExist; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int8 hasKey[7]; // [rsp+21h] [rbp-DFh] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::IButtonBase> expandButton; // [rsp+28h] [rbp-D8h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IFrameworkElement> contentRoot; // [rsp+30h] [rbp-D0h] BYREF
  IInspectable *ppValue; // [rsp+38h] [rbp-C8h] BYREF
  ctl::ComPtr<IInspectable> boxedResourceKey; // [rsp+40h] [rbp-C0h] BYREF
  ctl::ComPtr<Windows::UI::Core::ICoreWindow5> v103; // [rsp+48h] [rbp-B8h] BYREF
  ctl::ComPtr<IInspectable> boxedResource; // [rsp+50h] [rbp-B0h] BYREF
  ctl::ComPtr<Windows::Foundation::Collections::IMap<IInspectable *,IInspectable *> > resourcesMap; // [rsp+58h] [rbp-A8h] BYREF
  ctl::ComPtr<Windows::UI::Core::ICoreWindow5> v106; // [rsp+60h] [rbp-A0h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IResourceDictionary> resources; // [rsp+68h] [rbp-98h] BYREF
  Windows::Internal::String automationName; // [rsp+70h] [rbp-90h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Media::Animation::IStoryboard> windowOverlayOpeningStoryboard; // [rsp+78h] [rbp-88h] BYREF
  Windows::Internal::String toolTipText; // [rsp+80h] [rbp-80h] BYREF
  ctl::ComPtr<IInspectable> boxedToolTipText; // [rsp+88h] [rbp-78h] BYREF
  ctl::ComPtr<Windows::UI::Core::ICoreWindow5> v112; // [rsp+90h] [rbp-70h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::IGrid> layoutRoot; // [rsp+98h] [rbp-68h] BYREF
  int v114; // [rsp+A4h] [rbp-5Ch]
  std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::ISizeChangedEventArgs *)> v115; // [rsp+A8h] [rbp-58h] BYREF
  __int128 string; // [rsp+E8h] [rbp-18h] BYREF
  std::tuple<DirectUI::SplitView *,std::_Ph<1>,std::_Ph<2> > hstringHeader_8; // [rsp+F8h] [rbp-8h] BYREF

  v1 = &this->ctl::forwarder_holder<Windows::UI::Xaml::IUIElementOverrides9,DirectUI::UIElementGenerated>;
  if ( this->DirectUI::AppBarGenerated::DirectUI::ContentControl::DirectUI::ContentControlGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IUIElementOverrides9,DirectUI::UIElementGenerated>::m_forwarder.DirectUI::AppBarGenerated::DirectUI::ContentControl::DirectUI::ContentControlGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IUIElementOverrides9,DirectUI::UIElementGenerated>::__vftable )
  {
    v88 = DirectUI::DetachHandler_ctl::event_handler_Windows::UI::Xaml::IRoutedEventHandler_IInspectable_Windows::UI::Xaml::IRoutedEventArgs_DirectUI::ButtonBaseClickTraits__Windows::UI::Xaml::IFrameworkElement_(
            (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::ButtonBaseClickTraits> > *)&this->DirectUI::FrameworkElement
          + 54,
            (DirectUI::TrackerPtr<Windows::UI::Xaml::IFrameworkElement,1,0> *)v1);
    v31 = v88;
    if ( v88 < 0 )
    {
      OnFailure_2990_(v88);
      return v31;
    }
  }
  p_m_tpAP = &this->m_tpAP;
  if ( this->m_tpAP.m_trackerReference.m_value )
  {
    v4 = DirectUI::DetachHandler_ctl::event_handler_Windows::UI::Xaml::IRoutedEventHandler_IInspectable_Windows::UI::Xaml::IRoutedEventArgs_DirectUI::ButtonBaseClickTraits__Windows::UI::Xaml::Controls::Primitives::IButtonBase__1(
           (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::ButtonBaseClickTraits> > *)&this->Windows::UI::Xaml::Controls::IControl,
           (DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::Primitives::IButtonBase,1,0> *)&this->m_tpAP);
    v5 = v4;
    if ( v4 < 0 )
      goto LABEL_204;
  }
  if ( *(_QWORD *)&this->m_IsLocationValid )
  {
    v4 = DirectUI::DetachHandler_ctl::event_handler_Windows::UI::Xaml::IVisualStateChangedEventHandler_IInspectable_Windows::UI::Xaml::IVisualStateChangedEventArgs_DirectUI::VisualStateGroupCurrentStateChangedTraits__Windows::UI::Xaml::IVisualStateGroup_(
           (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IVisualStateChangedEventHandler,IInspectable,Windows::UI::Xaml::IVisualStateChangedEventArgs,DirectUI::VisualStateGroupCurrentStateChangedTraits> > *)&this->Windows::UI::Xaml::Controls::IControlProtected,
           (DirectUI::TrackerPtr<Windows::UI::Xaml::IVisualStateGroup,1,0> *)&this->m_IsLocationValid);
    v5 = v4;
    if ( v4 < 0 )
      goto LABEL_204;
  }
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IUIElement8,DirectUI::UIElementGenerated>,
    1u,
    0);
  DirectUI::TrackerTargetReference::Clear((DirectUI::TrackerTargetReference *)v1, 1u, 0);
  DirectUI::TrackerTargetReference::Clear(&this->m_tpAP.m_trackerReference, 1u, 0);
  DirectUI::TrackerTargetReference::Clear((DirectUI::TrackerTargetReference *)&this->m_IsLocationValid, 1u, 0);
  v4 = DirectUI::Control::OnApplyTemplate(this);
  v5 = v4;
  if ( v4 < 0 )
  {
LABEL_204:
    OnFailure_2990_(v4);
    return v5;
  }
  layoutRoot.ptr_ = 0;
  v6 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IGrid,Windows::UI::Xaml::Controls::IGrid>(
         (DirectUI::AppBar *)((char *)this - 360),
         (wchar_t *)L"LayoutRoot",
         0xAu,
         &layoutRoot.ptr_);
  v7 = v6;
  if ( v6 < 0 )
  {
    OnFailure_2990_(v6);
    goto LABEL_203;
  }
  ptr = layoutRoot.ptr_;
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpLayoutRoot,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IUIElement8,DirectUI::UIElementGenerated>,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)layoutRoot.ptr_);
  contentRoot.ptr_ = 0;
  v9 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::IFrameworkElement,Windows::UI::Xaml::IFrameworkElement>(
         (DirectUI::AppBar *)((char *)this - 360),
         (wchar_t *)L"ContentRoot",
         0xBu,
         &contentRoot.ptr_);
  v7 = v9;
  if ( v9 < 0 )
  {
    OnFailure_2990_(v9);
    goto LABEL_170;
  }
  v10 = contentRoot.ptr_;
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpLayoutRoot,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)v1,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)contentRoot.ptr_);
  if ( v1->m_forwarder.__vftable )
  {
    windowOverlayOpeningStoryboard.ptr_ = (Windows::UI::Xaml::Media::Animation::IStoryboard *)&this[-1].DirectUI::IBackButtonPressedListener;
    *(_QWORD *)&string =  DirectUI::AppBar::`vcall'{800,{flat}};
    HIDWORD(string) = v114;
    DWORD2(string) = 0;
    std::tuple<DirectUI::SplitView *,std::_Ph<1>,std::_Ph<2>>::tuple<DirectUI::SplitView *,std::_Ph<1>,std::_Ph<2>>(
      &hstringHeader_8,
      (DirectUI::SplitView **)&windowOverlayOpeningStoryboard,
      v11,
      v12);
    v83 = (Windows::UI::Xaml::IFrameworkElement *)v1->m_forwarder.__vftable;
    *(_OWORD *)&v115._Mystorage._Ptrs[1] = string;
    LOWORD(v115._Mystorage._Ptrs[3]) = hstringHeader_8.std::tuple<std::_Ph<1>,std::_Ph<2> >;
    v115._Mystorage._Ptrs[4] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::ISizeChangedEventArgs *> *)hstringHeader_8._Myfirst._Val;
    v115._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::ISizeChangedEventArgs *> *)std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (DirectUI::AppBar::*)(IInspectable *,Windows::UI::Xaml::ISizeChangedEventArgs *),DirectUI::AppBar *,std::_Ph<1> const &,std::_Ph<2> const &>,long,IInspectable *,Windows::UI::Xaml::ISizeChangedEventArgs *>::`vftable';
    v115._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::ISizeChangedEventArgs *> *)&v115;
    v84 = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::ISizeChangedEventHandler,IInspectable,Windows::UI::Xaml::ISizeChangedEventArgs,DirectUI::FrameworkElementSizeChangedTraits>>::AttachEventHandler(
            (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::ISizeChangedEventHandler,IInspectable,Windows::UI::Xaml::ISizeChangedEventArgs,DirectUI::FrameworkElementSizeChangedTraits> > *)&this->DirectUI::FrameworkElement
          + 54,
            v83,
            &v115);
    v14 = v84;
    if ( v84 < 0 )
    {
      OnFailure_2990_(v84);
LABEL_161:
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&contentRoot);
      goto LABEL_139;
    }
  }
  expandButton.ptr_ = 0;
  v13 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::Primitives::IButtonBase,Windows::UI::Xaml::Controls::Primitives::IButtonBase>(
          (DirectUI::AppBar *)((char *)this - 360),
          (wchar_t *)L"ExpandButton",
          0xCu,
          &expandButton.ptr_);
  v14 = v13;
  if ( v13 < 0 )
    goto LABEL_159;
  v15 = expandButton.ptr_;
  if ( expandButton.ptr_ )
  {
    v16 = (Windows::UI::Xaml::Media::Animation::IStoryboard *)&this[-1].DirectUI::IBackButtonPressedListener;
    goto LABEL_11;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&expandButton);
  v16 = (Windows::UI::Xaml::Media::Animation::IStoryboard *)&this[-1].DirectUI::IBackButtonPressedListener;
  v13 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::Primitives::IButtonBase,Windows::UI::Xaml::Controls::Primitives::IButtonBase>(
          (DirectUI::AppBar *)((char *)this - 360),
          (wchar_t *)L"MoreButton",
          0xAu,
          &expandButton.ptr_);
  v14 = v13;
  if ( v13 < 0 )
  {
LABEL_159:
    OnFailure_2990_(v13);
LABEL_160:
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&expandButton);
    goto LABEL_161;
  }
  v15 = expandButton.ptr_;
LABEL_11:
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpLayoutRoot,
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->m_tpAP,
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)v15);
  if ( p_m_tpAP->m_trackerReference.m_value )
  {
    windowOverlayOpeningStoryboard.ptr_ = v16;
    *(_QWORD *)&string = DirectUI::AppBar::OnExpandButtonClick;
    HIDWORD(string) = v114;
    DWORD2(string) = 0;
    std::tuple<DirectUI::SplitView *,std::_Ph<1>,std::_Ph<2>>::tuple<DirectUI::SplitView *,std::_Ph<1>,std::_Ph<2>>(
      &hstringHeader_8,
      (DirectUI::SplitView **)&windowOverlayOpeningStoryboard,
      v17,
      v18);
    m_value = (Windows::UI::Xaml::Controls::Primitives::IButtonBase *)p_m_tpAP->m_trackerReference.m_value;
    *(_OWORD *)&v115._Mystorage._Ptrs[1] = string;
    LOWORD(v115._Mystorage._Ptrs[3]) = hstringHeader_8.std::tuple<std::_Ph<1>,std::_Ph<2> >;
    v115._Mystorage._Ptrs[4] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::ISizeChangedEventArgs *> *)hstringHeader_8._Myfirst._Val;
    v115._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::ISizeChangedEventArgs *> *)std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (DirectUI::AppBar::*)(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *),DirectUI::AppBar *,std::_Ph<1> const &,std::_Ph<2> const &>,long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *>::`vftable';
    v115._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,Windows::UI::Xaml::ISizeChangedEventArgs *> *)&v115;
    v20 = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::ButtonBaseClickTraits>>::AttachEventHandler(
            (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::ButtonBaseClickTraits> > *)&this->Windows::UI::Xaml::Controls::IControl,
            m_value,
            (std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *)> *)&v115);
    v14 = v20;
    if ( v20 < 0 )
    {
      OnFailure_2990_(v20);
      goto LABEL_98;
    }
    Current = DirectUI::DXamlCore::GetCurrent();
    WindowsDeleteString(0);
    toolTipText._hstring = 0;
    LocalizedResourceString = DirectUI::DXamlCore::GetLocalizedResourceString(Current, 0x13EEu, &toolTipText._hstring);
    v14 = LocalizedResourceString;
    if ( LocalizedResourceString < 0 )
    {
      OnFailure_2990_(LocalizedResourceString);
      Windows::Internal::String::~String(&toolTipText);
      goto LABEL_160;
    }
    boxedToolTipText.ptr_ = 0;
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&boxedToolTipText);
    hstring = toolTipText._hstring;
    v24 = DirectUI::PropertyValue::CreateFromString(toolTipText._hstring, &boxedToolTipText.ptr_);
    v7 = v24;
    if ( v24 >= 0 )
    {
      v25 = p_m_tpAP->m_trackerReference.m_value;
      v26 = boxedToolTipText.ptr_;
      DependencyPropertyByIndex = DirectUI::MetadataAPI::GetDependencyPropertyByIndex(ToolTipService_ToolTip);
      v28 = DirectUI::DependencyObject::SetValue(
              (DirectUI::DependencyObject *)((unsigned __int64)&v25[-71] & -(__int64)(v25 != 0)),
              DependencyPropertyByIndex,
              v26);
      v29 = v28;
      if ( v28 < 0 )
      {
        OnFailure_2990_(v28);
      }
      else
      {
        WindowsDeleteString(0);
        automationName._hstring = 0;
        ValueByKnownIndex = DirectUI::DependencyObject::GetValueByKnownIndex(
                              (DirectUI::DependencyObject *)((__int64)&this->m_tpAP.m_trackerReference.m_value[-71]
                                                           & -(__int64)(this->m_tpAP.m_trackerReference.m_value != 0)),
                              AutomationProperties_Name,
                              &automationName._hstring);
        v31 = ValueByKnownIndex;
        if ( ValueByKnownIndex < 0 )
        {
          OnFailure_2990_(ValueByKnownIndex);
          if ( automationName._hstring )
            WindowsDeleteString(automationName._hstring);
          v73 = boxedToolTipText.ptr_;
          if ( boxedToolTipText.ptr_ )
          {
            boxedToolTipText.ptr_ = 0;
            v73->Release(v73);
          }
          if ( hstring )
            WindowsDeleteString(hstring);
          if ( v15 )
            v15->Release(v15);
          if ( v10 )
            v10->Release(v10);
          if ( ptr )
            ptr->Release(ptr);
          return v31;
        }
        v32 = automationName._hstring;
        if ( automationName._hstring )
        {
LABEL_18:
          WindowsDeleteString(v32);
LABEL_19:
          v33 = boxedToolTipText.ptr_;
          if ( boxedToolTipText.ptr_ )
          {
            boxedToolTipText.ptr_ = 0;
            v33->Release(v33);
          }
          if ( hstring )
            WindowsDeleteString(hstring);
          goto LABEL_23;
        }
        v89 = DirectUI::DXamlCore::GetCurrent();
        WindowsDeleteString(0);
        automationName._hstring = 0;
        v90 = DirectUI::DXamlCore::GetLocalizedResourceString(v89, 0x14B9u, &automationName._hstring);
        v29 = v90;
        if ( v90 >= 0 )
        {
          v32 = automationName._hstring;
          v91 = DirectUI::DependencyObject::SetValueByKnownIndex(
                  (DirectUI::DependencyObject *)((__int64)&this->m_tpAP.m_trackerReference.m_value[-71]
                                               & -(__int64)(this->m_tpAP.m_trackerReference.m_value != 0)),
                  AutomationProperties_Name,
                  automationName._hstring);
          v7 = v91;
          if ( v91 >= 0 )
          {
            if ( !v32 )
              goto LABEL_19;
            goto LABEL_18;
          }
          OnFailure_2990_(v91);
          Windows::Internal::String::~String(&automationName);
          goto LABEL_168;
        }
        OnFailure_2990_(v90);
        Windows::Internal::String::~String(&automationName);
      }
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&boxedToolTipText);
      Windows::Internal::String::~String(&toolTipText);
      goto LABEL_200;
    }
    OnFailure_2990_(v24);
LABEL_168:
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&boxedToolTipText);
    Windows::Internal::String::~String(&toolTipText);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&expandButton);
LABEL_170:
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&contentRoot);
LABEL_203:
    v14 = v7;
    goto LABEL_139;
  }
LABEL_23:
  v34 = *((_QWORD *)&this[-1].m_overlayClosingStoryboard.m_trackerReference + 2);
  resources.ptr_ = 0;
  resourcesMap.ptr_ = 0;
  boxedResourceKey.ptr_ = 0;
  v35 = *(__int64 (__fastcall **)(char *, ctl::ComPtr<Windows::UI::Xaml::IResourceDictionary> *))(v34 + 56);
  boxedResource.ptr_ = 0;
  doesResourceExist = 0;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&resources);
  v36 = v35((char *)&this[-1].m_overlayClosingStoryboard.m_trackerReference + 16, &resources);
  v14 = v36;
  if ( v36 < 0 )
  {
    OnFailure_2990_(v36);
    v85 = boxedResource.ptr_;
    if ( boxedResource.ptr_ )
    {
      boxedResource.ptr_ = 0;
      v85->Release(v85);
    }
    v86 = boxedResourceKey.ptr_;
    if ( boxedResourceKey.ptr_ )
    {
      boxedResourceKey.ptr_ = 0;
      v86->Release(v86);
    }
    v87 = resourcesMap.ptr_;
    if ( resourcesMap.ptr_ )
    {
      resourcesMap.ptr_ = 0;
      v87->Release(v87);
    }
    v72 = resources.ptr_;
    if ( !resources.ptr_ )
      goto LABEL_98;
    resources.ptr_ = 0;
    goto LABEL_97;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&resourcesMap);
  if ( resources.ptr_ )
  {
    v37 = resources.ptr_->QueryInterface(
            resources.ptr_,
            &GUID_f5f69427_55ed_5512_8429_d4f6626dfcdd,
            (void **)&resourcesMap);
    v14 = v37;
    if ( v37 < 0 )
      goto LABEL_172;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&boxedResourceKey);
  if ( WindowsCreateStringReference(
         L"AppBarThemeCompactHeight",
         0x18u,
         (HSTRING_HEADER *)((char *)&string + 8),
         (HSTRING *)&string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v37 = DirectUI::PropertyValue::CreateFromString((HSTRING__ *)string, &boxedResourceKey.ptr_);
  v14 = v37;
  if ( v37 < 0 )
  {
LABEL_172:
    OnFailure_2990_(v37);
LABEL_174:
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&boxedResource);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&boxedResourceKey);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&resourcesMap);
    p_resources = (ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&resources;
LABEL_177:
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(p_resources);
    goto LABEL_160;
  }
  v38 = resourcesMap.ptr_->HasKey(resourcesMap.ptr_, boxedResourceKey.ptr_, &doesResourceExist);
  v14 = v38;
  if ( v38 < 0 )
    goto LABEL_173;
  if ( !doesResourceExist )
    goto LABEL_31;
  v93 = resourcesMap.ptr_;
  Lookup = resourcesMap.ptr_->Lookup;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&boxedResource);
  v38 = Lookup(v93, boxedResourceKey.ptr_, &boxedResource.ptr_);
  v14 = v38;
  if ( v38 < 0 )
  {
LABEL_173:
    OnFailure_2990_(v38);
    goto LABEL_174;
  }
  if ( !boxedResource.ptr_ )
    goto LABEL_138;
  ctl::query_interface_cast<Windows::Foundation::IReference<double>,IInspectable>(
    (ctl::ComPtr<Windows::Foundation::IReference<double> > *)&windowOverlayOpeningStoryboard,
    boxedResource.ptr_);
  v95 = windowOverlayOpeningStoryboard.ptr_->get_Children(
          windowOverlayOpeningStoryboard.ptr_,
          (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Media::Animation::Timeline *> **)&this->Windows::UI::Xaml::IFrameworkElementOverrides);
  v14 = v95;
  if ( v95 < 0 )
  {
    OnFailure_2990_(v95);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&windowOverlayOpeningStoryboard);
    goto LABEL_174;
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&windowOverlayOpeningStoryboard);
LABEL_31:
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&boxedResourceKey);
  if ( WindowsCreateStringReference(
         L"AppBarThemeMinimalHeight",
         0x18u,
         (HSTRING_HEADER *)((char *)&string + 8),
         (HSTRING *)&string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v38 = DirectUI::PropertyValue::CreateFromString((HSTRING__ *)string, &boxedResourceKey.ptr_);
  v14 = v38;
  if ( v38 < 0 )
    goto LABEL_173;
  v38 = resourcesMap.ptr_->HasKey(resourcesMap.ptr_, boxedResourceKey.ptr_, &doesResourceExist);
  v14 = v38;
  if ( v38 < 0 )
    goto LABEL_173;
  if ( !doesResourceExist )
    goto LABEL_36;
  v78 = resourcesMap.ptr_;
  v79 = resourcesMap.ptr_->Lookup;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&boxedResource);
  v38 = v79(v78, boxedResourceKey.ptr_, &boxedResource.ptr_);
  v14 = v38;
  if ( v38 < 0 )
    goto LABEL_173;
  if ( !boxedResource.ptr_ )
  {
LABEL_138:
    OnNewFailure_1172_(v80);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&boxedResource);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&boxedResourceKey);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&resourcesMap);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&resources);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&expandButton);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&contentRoot);
    v14 = -2147467261;
LABEL_139:
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&layoutRoot);
    return v14;
  }
  ctl::query_interface_cast<Windows::Foundation::IReference<double>,IInspectable>(
    (ctl::ComPtr<Windows::Foundation::IReference<double> > *)&windowOverlayOpeningStoryboard,
    boxedResource.ptr_);
  v81 = windowOverlayOpeningStoryboard.ptr_;
  v82 = windowOverlayOpeningStoryboard.ptr_->get_Children(
          windowOverlayOpeningStoryboard.ptr_,
          (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Media::Animation::Timeline *> **)&this->ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement2,DirectUI::FrameworkElementGenerated>);
  v29 = v82;
  if ( v82 < 0 )
  {
    OnFailure_2990_(v82);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&windowOverlayOpeningStoryboard);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&boxedResource);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&boxedResourceKey);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&resourcesMap);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&resources);
LABEL_200:
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&expandButton);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&contentRoot);
    v14 = v29;
    goto LABEL_139;
  }
  if ( v81 )
    v81->Release(v81);
LABEL_36:
  v39 = boxedResource.ptr_;
  if ( boxedResource.ptr_ )
  {
    boxedResource.ptr_ = 0;
    v39->Release(v39);
  }
  v40 = boxedResourceKey.ptr_;
  if ( boxedResourceKey.ptr_ )
  {
    boxedResourceKey.ptr_ = 0;
    v40->Release(v40);
  }
  v41 = resourcesMap.ptr_;
  if ( resourcesMap.ptr_ )
  {
    resourcesMap.ptr_ = 0;
    v41->Release(v41);
  }
  v42 = resources.ptr_;
  if ( resources.ptr_ )
  {
    resources.ptr_ = 0;
    v42->Release(v42);
  }
  v43 = this->DirectUI::AppBarGenerated::DirectUI::ContentControl::DirectUI::ContentControlGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IUIElement8,DirectUI::UIElementGenerated>::m_forwarder.DirectUI::AppBarGenerated::DirectUI::ContentControl::DirectUI::ContentControlGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IUIElement8,DirectUI::UIElementGenerated>::__vftable;
  if ( v43 )
  {
    v106.ptr_ = 0;
    v44 = (__int64 (__fastcall *)(_QWORD, ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *))*((_QWORD *)v43[-2].get_KeyboardAcceleratorPlacementMode
                                                                                          + 7);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(&v106);
    v45 = v44(&v43[-2].get_KeyboardAcceleratorPlacementMode, &v106);
    v14 = v45;
    if ( v45 < 0 )
    {
      OnFailure_2990_(v45);
LABEL_176:
      p_resources = &v106;
      goto LABEL_177;
    }
    v103.ptr_ = 0;
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(&v103);
    if ( v106.ptr_ )
    {
      v46 = v106.ptr_->QueryInterface(v106.ptr_, &GUID_f5f69427_55ed_5512_8429_d4f6626dfcdd, (void **)&v103);
      v14 = v46;
      if ( v46 < 0 )
      {
        OnFailure_2990_(v46);
LABEL_188:
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(&v103);
        goto LABEL_176;
      }
    }
    ppValue = 0;
    if ( WindowsCreateStringReference(
           L"OverlayOpeningAnimation",
           0x17u,
           (HSTRING_HEADER *)((char *)&string + 8),
           (HSTRING *)&string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v47 = DirectUI::PropertyValue::CreateFromString((HSTRING__ *)string, &ppValue);
    v14 = v47;
    if ( v47 < 0
      || (hasKey[0] = 0,
          v47 = v103.ptr_->__vftable[1].QueryInterface(v103.ptr_, (const _GUID *)ppValue, (void **)hasKey),
          v14 = v47,
          v47 < 0) )
    {
      OnFailure_2990_(v47);
    }
    else
    {
      if ( !hasKey[0] )
      {
        p_m_tpLayoutRoot = (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpLayoutRoot;
        goto LABEL_60;
      }
      v48 = v103.ptr_;
      v112.ptr_ = 0;
      get_DispatcherQueue = v103.ptr_->get_DispatcherQueue;
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(&v112);
      v50 = ((__int64 (__fastcall *)(Windows::UI::Core::ICoreWindow5 *, IInspectable *, ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *))get_DispatcherQueue)(
              v48,
              ppValue,
              &v112);
      v14 = v50;
      if ( v50 >= 0 )
      {
        windowOverlayOpeningStoryboard.ptr_ = 0;
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&windowOverlayOpeningStoryboard);
        if ( v112.ptr_ )
        {
          v51 = v112.ptr_->QueryInterface(
                  v112.ptr_,
                  &GUID_d45c1e6e_3594_460e_981a_32271bd3aa06,
                  (void **)&windowOverlayOpeningStoryboard);
          v14 = v51;
          if ( v51 < 0 )
          {
            OnFailure_2990_(v51);
            ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&windowOverlayOpeningStoryboard);
            p_automationName = &v112;
            goto LABEL_186;
          }
        }
        p_m_tpLayoutRoot = (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpLayoutRoot;
        ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
          (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpLayoutRoot,
          (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->Windows::UI::Xaml::Controls::IAppBar,
          (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)windowOverlayOpeningStoryboard.ptr_);
        v53 = windowOverlayOpeningStoryboard.ptr_;
        if ( windowOverlayOpeningStoryboard.ptr_ )
        {
          windowOverlayOpeningStoryboard.ptr_ = 0;
          v53->Release(v53);
        }
        v54 = v112.ptr_;
        if ( v112.ptr_ )
        {
          v112.ptr_ = 0;
          v54->Release(v54);
        }
LABEL_60:
        v55 = ppValue;
        if ( ppValue )
        {
          ppValue = 0;
          v55->Release(v55);
        }
        if ( WindowsCreateStringReference(
               L"OverlayClosingAnimation",
               0x17u,
               (HSTRING_HEADER *)((char *)&string + 8),
               (HSTRING *)&string) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v56 = DirectUI::PropertyValue::CreateFromString((HSTRING__ *)string, &ppValue);
        v14 = v56;
        if ( v56 < 0 )
        {
          OnFailure_2990_(v56);
LABEL_123:
          v76 = ppValue;
          if ( ppValue )
          {
            ppValue = 0;
            v76->Release(v76);
          }
          v77 = v103.ptr_;
          if ( v103.ptr_ )
          {
            v103.ptr_ = 0;
            v77->Release(v77);
          }
          v72 = v106.ptr_;
          if ( !v106.ptr_ )
            goto LABEL_98;
          v106.ptr_ = 0;
          goto LABEL_97;
        }
        v57 = v103.ptr_->__vftable[1].QueryInterface(v103.ptr_, (const _GUID *)ppValue, (void **)hasKey);
        v14 = v57;
        if ( v57 < 0 )
        {
          OnFailure_2990_(v57);
          goto LABEL_187;
        }
        if ( !hasKey[0] )
        {
LABEL_74:
          v64 = ppValue;
          if ( ppValue )
          {
            ppValue = 0;
            v64->Release(v64);
          }
          v65 = v103.ptr_;
          if ( v103.ptr_ )
          {
            v103.ptr_ = 0;
            v65->Release(v65);
          }
          v66 = v106.ptr_;
          if ( v106.ptr_ )
          {
            v106.ptr_ = 0;
            v66->Release(v66);
          }
          goto LABEL_80;
        }
        automationName._hstring = 0;
        v58 = v103.ptr_;
        v59 = v103.ptr_->get_DispatcherQueue;
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&automationName);
        v60 = ((__int64 (__fastcall *)(Windows::UI::Core::ICoreWindow5 *, IInspectable *, Windows::Internal::String *))v59)(
                v58,
                ppValue,
                &automationName);
        v14 = v60;
        if ( v60 >= 0 )
        {
          toolTipText._hstring = 0;
          ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&toolTipText);
          if ( !automationName._hstring
            || (v61 = (**(__int64 (__fastcall ***)(HSTRING__ *, GUID *, Windows::Internal::String *))automationName._hstring)(
                        automationName._hstring,
                        &GUID_d45c1e6e_3594_460e_981a_32271bd3aa06,
                        &toolTipText),
                v14 = v61,
                v61 >= 0) )
          {
            ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
              p_m_tpLayoutRoot,
              (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)&this->Windows::UI::Xaml::Controls::IAppBar3,
              (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)toolTipText._hstring);
            v62 = toolTipText._hstring;
            if ( toolTipText._hstring )
            {
              toolTipText._hstring = 0;
              (*(void (__fastcall **)(HSTRING__ *))(*(_QWORD *)v62 + 16LL))(v62);
            }
            v63 = automationName._hstring;
            if ( automationName._hstring )
            {
              automationName._hstring = 0;
              (*(void (__fastcall **)(HSTRING__ *))(*(_QWORD *)v63 + 16LL))(v63);
            }
            goto LABEL_74;
          }
          OnFailure_2990_(v61);
          v74 = toolTipText._hstring;
          if ( toolTipText._hstring )
          {
            toolTipText._hstring = 0;
            (*(void (__fastcall **)(HSTRING__ *))(*(_QWORD *)v74 + 16LL))(v74);
          }
          v75 = automationName._hstring;
          if ( automationName._hstring )
          {
            automationName._hstring = 0;
            (*(void (__fastcall **)(HSTRING__ *))(*(_QWORD *)v75 + 16LL))(v75);
          }
          goto LABEL_123;
        }
        OnFailure_2990_(v60);
        p_automationName = (ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&automationName;
LABEL_186:
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(p_automationName);
LABEL_187:
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&ppValue);
        goto LABEL_188;
      }
      OnFailure_2990_(v50);
      v69 = v112.ptr_;
      if ( v112.ptr_ )
      {
        v112.ptr_ = 0;
        v69->Release(v69);
      }
    }
    v70 = ppValue;
    if ( ppValue )
    {
      ppValue = 0;
      v70->Release(v70);
    }
    v71 = v103.ptr_;
    if ( v103.ptr_ )
    {
      v103.ptr_ = 0;
      v71->Release(v71);
    }
    v72 = v106.ptr_;
    if ( !v106.ptr_ )
      goto LABEL_98;
    v106.ptr_ = 0;
LABEL_97:
    (*(void (__fastcall **)(void *))(*(_QWORD *)v72 + 16LL))(v72);
LABEL_98:
    if ( v15 )
      v15->Release(v15);
    if ( v10 )
      v10->Release(v10);
    if ( ptr )
      ptr->Release(ptr);
    return v14;
  }
LABEL_80:
  IsOverlayVisible = DirectUI::AppBar::ReevaluateIsOverlayVisible((DirectUI::AppBar *)((char *)this - 360));
  v14 = IsOverlayVisible;
  if ( IsOverlayVisible < 0 )
  {
    OnFailure_2990_(IsOverlayVisible);
    goto LABEL_160;
  }
  if ( v15 )
    v15->Release(v15);
  if ( v10 )
    v10->Release(v10);
  if ( ptr )
    ptr->Release(ptr);
  return 0;
}

```

## disassembly

```asm
0x180305770  push    rbp
0x180305772  push    rbx
0x180305773  push    rsi
0x180305774  push    rdi
0x180305775  push    r12
0x180305777  push    r13
0x180305779  push    r14
0x18030577b  push    r15
0x18030577d  lea     rbp, [rsp-18h]
0x180305782  sub     rsp, 118h
0x180305789  mov     rax, cs:__security_cookie
0x180305790  xor     rax, rsp
0x180305793  mov     [rbp+50h+var_48], rax
0x180305797  lea     rbx, [this+120h]
0x18030579e  xor     r15d, r15d
0x1803057a1  mov     r13, this
0x1803057a4  cmp     [rbx], r15
0x1803057a7  jnz     loc_180306426
0x1803057ad  lea     rdi, [r13+138h]
0x1803057b4  cmp     [rdi], r15
0x1803057b7  jnz     loc_18030644B
0x1803057bd  lea     r14, [r13+150h]
0x1803057c4  cmp     [r14], r15
0x1803057c7  jnz     loc_180306470
0x1803057cd  lea     r12, [r13+108h]
0x1803057d4  xor     r8d, r8d; bForceLoopback
0x1803057d7  mov     this, r12; this
0x1803057da  mov     dl, 1; bEnsureTrackerTarget
0x1803057dc  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x1803057e1  xor     r8d, r8d; bForceLoopback
0x1803057e4  mov     dl, 1; bEnsureTrackerTarget
0x1803057e6  mov     this, rbx; this
0x1803057e9  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x1803057ee  xor     r8d, r8d; bForceLoopback
0x1803057f1  mov     dl, 1; bEnsureTrackerTarget
0x1803057f3  mov     this, rdi; this
0x1803057f6  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x1803057fb  xor     r8d, r8d; bForceLoopback
0x1803057fe  mov     dl, 1; bEnsureTrackerTarget
0x180305800  mov     this, r14; this
0x180305803  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x180305808  mov     this, r13; this
0x18030580b  call    ?OnApplyTemplate@Control@DirectUI@@UEAAJXZ; DirectUI::Control::OnApplyTemplate(void)
0x180305810  mov     esi, eax
0x180305812  test    eax, eax
0x180305814  js      loc_180306837
0x18030581a  lea     r14, [r13-168h]
0x180305821  mov     [rbp+50h+layoutRoot.ptr_], r15
0x180305825  mov     this, r14; this
0x180305828  lea     r9, [rbp+50h+layoutRoot]; ppReference
0x18030582c  mov     r8d, 0Ah; cName
0x180305832  lea     rdx, pName; "LayoutRoot"
0x180305839  call    ??$GetTemplatePart@UIGrid@Controls@Xaml@UI@Windows@@U12345@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUIGrid@Controls@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::IGrid,Windows::UI::Xaml::Controls::IGrid>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::IGrid * *)
0x18030583e  mov     esi, eax
0x180305840  test    eax, eax
0x180305842  js      loc_180306829
0x180305848  mov     r15, [rbp+50h+layoutRoot.ptr_]
0x18030584c  lea     this, [r13-160h]; this
0x180305853  mov     r8, r15; value
0x180305856  mov     rdx, r12; ptr
0x180305859  call    ??$SetPtrValue@U?$IVector@PEAVWebViewDeferredPermissionRequest@Controls@Xaml@UI@Windows@@@Collections@Foundation@Windows@@U1234@@WeakReferenceSourceNoThreadId@ctl@@QEAAXAEAV?$TrackerPtr@U?$IVector@PEAVWebViewDeferredPermissionRequest@Controls@Xaml@UI@Windows@@@Collections@Foundation@Windows@@$00$0A@@DirectUI@@PEAU?$IVector@PEAVWebViewDeferredPermissionRequest@Controls@Xaml@UI@Windows@@@Collections@Foundation@Windows@@@Z; ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,1,0> &,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *> *)
0x18030585e  lea     r9, [rsp+150h+contentRoot]; ppReference
0x180305863  mov     [rsp+150h+contentRoot.ptr_], 0
0x18030586c  mov     r8d, 0Bh; cName
0x180305872  lea     rdx, aContentroot; "ContentRoot"
0x180305879  mov     this, r14; this
0x18030587c  call    ??$GetTemplatePart@UIFrameworkElement@Xaml@UI@Windows@@U1234@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUIFrameworkElement@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::IFrameworkElement,Windows::UI::Xaml::IFrameworkElement>(ushort *,unsigned __int64,Windows::UI::Xaml::IFrameworkElement * *)
0x180305881  mov     esi, eax
0x180305883  test    eax, eax
0x180305885  js      loc_180306591
0x18030588b  mov     r12, [rsp+150h+contentRoot.ptr_]
0x180305890  lea     this, [r13-160h]; this
0x180305897  mov     r8, r12; value
0x18030589a  mov     rdx, rbx; ptr
0x18030589d  call    ??$SetPtrValue@U?$IVector@PEAVWebViewDeferredPermissionRequest@Controls@Xaml@UI@Windows@@@Collections@Foundation@Windows@@U1234@@WeakReferenceSourceNoThreadId@ctl@@QEAAXAEAV?$TrackerPtr@U?$IVector@PEAVWebViewDeferredPermissionRequest@Controls@Xaml@UI@Windows@@@Collections@Foundation@Windows@@$00$0A@@DirectUI@@PEAU?$IVector@PEAVWebViewDeferredPermissionRequest@Controls@Xaml@UI@Windows@@@Collections@Foundation@Windows@@@Z; ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,1,0> &,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *> *)
0x1803058a2  xor     esi, esi
0x1803058a4  cmp     [rbx], rsi
0x1803058a7  jnz     loc_1803062A3
0x1803058ad  lea     r9, [rsp+150h+expandButton]; ppReference
0x1803058b2  mov     [rsp+150h+expandButton.ptr_], rsi
0x1803058b7  mov     r8d, 0Ch; cName
0x1803058bd  lea     rdx, aExpandbutton; "ExpandButton"
0x1803058c4  mov     this, r14; this
0x1803058c7  call    ??$GetTemplatePart@UIButtonBase@Primitives@Controls@Xaml@UI@Windows@@U123456@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUIButtonBase@Primitives@Controls@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::Controls::Primitives::IButtonBase,Windows::UI::Xaml::Controls::Primitives::IButtonBase>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::Primitives::IButtonBase * *)
0x1803058cc  mov     ebx, eax
0x1803058ce  test    eax, eax
0x1803058d0  js      loc_180306495
0x1803058d6  mov     r14, [rsp+150h+expandButton.ptr_]
0x1803058db  test    r14, r14
0x1803058de  jz      loc_1803064B5
0x1803058e4  lea     rsi, [r13-168h]
0x1803058eb  mov     r8, r14; value
0x1803058ee  lea     this, [r13-160h]; this
0x1803058f5  mov     rdx, rdi; ptr
0x1803058f8  call    ??$SetPtrValue@U?$IVector@PEAVWebViewDeferredPermissionRequest@Controls@Xaml@UI@Windows@@@Collections@Foundation@Windows@@U1234@@WeakReferenceSourceNoThreadId@ctl@@QEAAXAEAV?$TrackerPtr@U?$IVector@PEAVWebViewDeferredPermissionRequest@Controls@Xaml@UI@Windows@@@Collections@Foundation@Windows@@$00$0A@@DirectUI@@PEAU?$IVector@PEAVWebViewDeferredPermissionRequest@Controls@Xaml@UI@Windows@@@Collections@Foundation@Windows@@@Z; ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,1,0> &,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *> *)
0x1803058fd  cmp     qword ptr [rdi], 0
0x180305901  jz      loc_18030600A
0x180305907  lea     rax, ?OnExpandButtonClick@AppBar@DirectUI@@AEAAJPEAUIInspectable@@PEAUIRoutedEventArgs@Xaml@UI@Windows@@@Z; DirectUI::AppBar::OnExpandButtonClick(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *)
0x18030590e  mov     [rsp+150h+windowOverlayOpeningStoryboard.ptr_], rsi
0x180305913  mov     [rbp+50h+string], rax
0x180305917  lea     rdx, [rsp+150h+windowOverlayOpeningStoryboard]; _This_arg
0x18030591c  mov     eax, [rbp+50h+var_AC]
0x18030591f  lea     this, [rbp+50h+hstringHeader.Reserved+8]; this
0x180305923  xor     esi, esi
0x180305925  mov     dword ptr [rbp+50h+hstringHeader.Reserved+4], eax
0x180305928  mov     dword ptr [rbp+50h+hstringHeader.Reserved], esi
0x18030592b  call    ??$?0PEAVSplitView@DirectUI@@AEBU?$_Ph@$00@std@@AEBU?$_Ph@$01@3@$0A@@?$tuple@PEAVSplitView@DirectUI@@U?$_Ph@$00@std@@U?$_Ph@$01@4@@std@@QEAA@$$QEAPEAVSplitView@DirectUI@@AEBU?$_Ph@$00@1@AEBU?$_Ph@$01@1@@Z; std::tuple<DirectUI::SplitView *,std::_Ph<1>,std::_Ph<2>>::tuple<DirectUI::SplitView *,std::_Ph<1>,std::_Ph<2>>(DirectUI::SplitView * &&,std::_Ph<1> const &,std::_Ph<2> const &)
0x180305930  mov     rax, [rbp+50h+string]
0x180305934  lea     this, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8AppBar@DirectUI@@EAAJPEAUIInspectable@@PEAUIRoutedEventArgs@Xaml@UI@Windows@@@ZPEAV34@AEBU?$_Ph@$00@2@AEBU?$_Ph@$01@2@@std@@JPEAUIInspectable@@PEAUIRoutedEventArgs@Xaml@UI@Windows@@@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (DirectUI::AppBar::*)(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *),DirectUI::AppBar *,std::_Ph<1> const &,std::_Ph<2> const &>,long,IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *>::`vftable'
0x18030593b  mov     rdx, [rdi]
0x18030593e  lea     r8, [rbp+50h+var_A8]
0x180305942  mov     [rbp+50h+var_A0], rax
0x180305946  mov     eax, dword ptr [rbp+50h+hstringHeader.Reserved]
0x180305949  mov     dword ptr [rbp+50h+var_98], eax
0x18030594c  mov     eax, dword ptr [rbp+50h+hstringHeader.Reserved+4]
0x18030594f  mov     dword ptr [rbp+50h+var_98+4], eax
0x180305952  mov     al, byte ptr [rbp+50h+hstringHeader.Reserved+8]
0x180305955  mov     byte ptr [rbp+50h+var_90], al
0x180305958  mov     al, byte ptr [rbp+50h+hstringHeader.Reserved+9]
0x18030595b  mov     byte ptr [rbp+50h+var_90+1], al
0x18030595e  mov     rax, qword ptr [rbp+50h+hstringHeader.Reserved+10h]
0x180305962  mov     [rbp+50h+var_88], rax
0x180305966  lea     rax, [rbp+50h+var_A8]
0x18030596a  mov     [rbp+50h+var_A8], this
0x18030596e  lea     this, [r13+1C0h]
0x180305975  mov     [rbp+50h+var_70], rax
0x180305979  call    ?AttachEventHandler@?$EventPtr@V?$event_handler@UIRoutedEventHandler@Xaml@UI@Windows@@UIInspectable@@UIRoutedEventArgs@234@UButtonBaseClickTraits@DirectUI@@@ctl@@@ctl@@QEAAJPEAUIButtonBase@Primitives@Controls@Xaml@UI@Windows@@V?$function@$$A6AJPEAUIInspectable@@PEAUIRoutedEventArgs@Xaml@UI@Windows@@@Z@std@@@Z; ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::ButtonBaseClickTraits>>::AttachEventHandler(Windows::UI::Xaml::Controls::Primitives::IButtonBase *,std::function<long (IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *)>)
0x18030597e  mov     ebx, eax
0x180305980  test    eax, eax
0x180305982  js      loc_1803063F2
0x180305988  call    ?GetCurrent@DXamlCore@DirectUI@@SAPEAV12@XZ; DirectUI::DXamlCore::GetCurrent(void)
0x18030598d  xor     ecx, ecx; string
0x18030598f  mov     rbx, rax
0x180305992  call    cs:__imp_WindowsDeleteString
0x180305998  lea     r8, [rbp+50h+toolTipText]; resourceString
0x18030599c  mov     [rbp+50h+toolTipText._hstring], rsi
0x1803059a0  mov     edx, 13EEh; resourceStringID
0x1803059a5  mov     this, rbx; this
0x1803059a8  call    ?GetLocalizedResourceString@DXamlCore@DirectUI@@QEAAJIPEAPEAUHSTRING__@@@Z; DirectUI::DXamlCore::GetLocalizedResourceString(uint,HSTRING__ * *)
0x1803059ad  mov     ebx, eax
0x1803059af  test    eax, eax
0x1803059b1  js      loc_180306814
0x1803059b7  lea     this, [rbp+50h+boxedToolTipText]; this
0x1803059bb  mov     [rbp+50h+boxedToolTipText.ptr_], rsi
0x1803059bf  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1803059c4  mov     rbx, [rbp+50h+toolTipText._hstring]
0x1803059c8  lea     rdx, [rbp+50h+boxedToolTipText]; ppValue
0x1803059cc  mov     this, rbx; hString
0x1803059cf  call    ?CreateFromString@PropertyValue@DirectUI@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; DirectUI::PropertyValue::CreateFromString(HSTRING__ *,IInspectable * *)
0x1803059d4  mov     esi, eax
0x1803059d6  test    eax, eax
0x1803059d8  js      loc_18030656C
0x1803059de  mov     rdi, [rdi]
0x1803059e1  mov     ecx, 3Bh ; ';'; ePropertyIndex
0x1803059e6  mov     rsi, [rbp+50h+boxedToolTipText.ptr_]
0x1803059ea  call    ?GetDependencyPropertyByIndex@MetadataAPI@DirectUI@@SAPEBVCDependencyProperty@@W4KnownPropertyIndex@@@Z; DirectUI::MetadataAPI::GetDependencyPropertyByIndex(KnownPropertyIndex)
0x1803059ef  lea     rdx, [rdi-238h]
0x1803059f6  mov     r8, rsi; pValue
0x1803059f9  neg     rdi
0x1803059fc  sbb     this, this
0x1803059ff  and     this, rdx; this
0x180305a02  mov     rdx, rax; pDP
0x180305a05  call    ?SetValue@DependencyObject@DirectUI@@QEAAJPEBVCDependencyProperty@@PEAUIInspectable@@@Z; DirectUI::DependencyObject::SetValue(CDependencyProperty const *,IInspectable *)
0x180305a0a  mov     edi, eax
0x180305a0c  test    eax, eax
0x180305a0e  js      loc_1803067E0
0x180305a14  xor     ecx, ecx; string
0x180305a16  call    cs:__imp_WindowsDeleteString
0x180305a1c  lea     rsi, [r13+138h]
0x180305a23  mov     [rsp+150h+automationName._hstring], 0
0x180305a2c  mov     this, [rsi]
0x180305a2f  lea     r8, [rsp+150h+automationName]; pValue
0x180305a34  mov     edx, 22h ; '"'; nPropertyIndex
0x180305a39  lea     rax, [this-238h]
0x180305a40  neg     this
0x180305a43  sbb     this, this
0x180305a46  and     this, rax; this
0x180305a49  call    ?GetValueByKnownIndex@DependencyObject@DirectUI@@QEAAJW4KnownPropertyIndex@@PEAPEAUHSTRING__@@@Z; DirectUI::DependencyObject::GetValueByKnownIndex(KnownPropertyIndex,HSTRING__ * *)
0x180305a4e  mov     edi, eax
0x180305a50  test    eax, eax
0x180305a52  js      loc_1803060E1
0x180305a58  mov     rdi, [rsp+150h+automationName._hstring]
0x180305a5d  test    rdi, rdi
0x180305a60  jz      loc_1803064F9
0x180305a66  xor     esi, esi
0x180305a68  mov     this, rdi; string
0x180305a6b  call    cs:__imp_WindowsDeleteString
0x180305a71  mov     this, [rbp+50h+boxedToolTipText.ptr_]
0x180305a75  test    this, this
0x180305a78  jz      short loc_180305A8A
0x180305a7a  mov     [rbp+50h+boxedToolTipText.ptr_], rsi
0x180305a7e  mov     rax, [this]
0x180305a81  mov     rax, [rax+10h]
0x180305a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180305a8a  test    rbx, rbx
0x180305a8d  jz      short loc_180305A98
0x180305a8f  mov     this, rbx; string
0x180305a92  call    cs:__imp_WindowsDeleteString
0x180305a98  mov     rax, [r13-8]
0x180305a9c  lea     this, [rsp+150h+resources]; this
0x180305aa1  mov     [rsp+150h+resources.ptr_], rsi
0x180305aa6  mov     [rsp+150h+resourcesMap.ptr_], rsi
0x180305aab  mov     [rsp+150h+boxedResourceKey.ptr_], rsi
0x180305ab0  mov     rbx, [rax+38h]
0x180305ab4  mov     [rsp+150h+boxedResource.ptr_], rsi
0x180305ab9  mov     [rsp+150h+doesResourceExist], sil
0x180305abe  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180305ac3  lea     rdx, [rsp+150h+resources]
0x180305ac8  mov     rax, rbx
0x180305acb  lea     this, [r13-8]
0x180305acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180305ad4  mov     ebx, eax
0x180305ad6  test    eax, eax
0x180305ad8  js      loc_180306382
0x180305ade  lea     this, [rsp+150h+resourcesMap]; this
0x180305ae3  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180305ae8  mov     this, [rsp+150h+resources.ptr_]
0x180305aed  test    this, this
0x180305af0  jz      short loc_180305B13
0x180305af2  mov     rax, [this]
0x180305af5  lea     r8, [rsp+150h+resourcesMap]
0x180305afa  lea     rdx, _GUID_f5f69427_55ed_5512_8429_d4f6626dfcdd
0x180305b01  mov     rax, [rax]
0x180305b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180305b09  mov     ebx, eax
0x180305b0b  test    eax, eax
0x180305b0d  js      loc_1803065BD
0x180305b13  lea     this, [rsp+150h+boxedResourceKey]; this
0x180305b18  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180305b1d  lea     r9, [rbp+50h+string]; string
0x180305b21  mov     edx, 18h; length
0x180305b26  lea     r8, [rbp+50h+hstringHeader]; hstringHeader
0x180305b2a  lea     this, aAppbarthemecom; "AppBarThemeCompactHeight"
0x180305b31  call    cs:__imp_WindowsCreateStringReference
0x180305b37  test    eax, eax
0x180305b39  js      loc_180306608
0x180305b3f  mov     this, [rbp+50h+string]; hString
0x180305b43  lea     rdx, [rsp+150h+boxedResourceKey]; ppValue
0x180305b48  call    ?CreateFromString@PropertyValue@DirectUI@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; DirectUI::PropertyValue::CreateFromString(HSTRING__ *,IInspectable * *)
0x180305b4d  mov     ebx, eax
0x180305b4f  test    eax, eax
0x180305b51  js      loc_1803067D4
0x180305b57  mov     this, [rsp+150h+resourcesMap.ptr_]
0x180305b5c  lea     r8, [rsp+150h+doesResourceExist]
0x180305b61  mov     rdx, [rsp+150h+boxedResourceKey.ptr_]
0x180305b66  mov     rax, [this]
0x180305b69  mov     rax, [rax+40h]
0x180305b6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180305b72  mov     ebx, eax
0x180305b74  test    eax, eax
0x180305b76  js      loc_1803067C8
0x180305b7c  cmp     [rsp+150h+doesResourceExist], sil
0x180305b81  jnz     loc_180306622
0x180305b87  lea     this, [rsp+150h+boxedResourceKey]; this
0x180305b8c  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180305b91  lea     r9, [rbp+50h+string]; string
0x180305b95  mov     edx, 18h; length
0x180305b9a  lea     r8, [rbp+50h+hstringHeader]; hstringHeader
0x180305b9e  lea     this, aAppbarthememin; "AppBarThemeMinimalHeight"
0x180305ba5  call    cs:__imp_WindowsCreateStringReference
0x180305bab  test    eax, eax
0x180305bad  js      loc_1803066B0
0x180305bb3  mov     this, [rbp+50h+string]; hString
0x180305bb7  lea     rdx, [rsp+150h+boxedResourceKey]; ppValue
0x180305bbc  call    ?CreateFromString@PropertyValue@DirectUI@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; DirectUI::PropertyValue::CreateFromString(HSTRING__ *,IInspectable * *)
0x180305bc1  mov     ebx, eax
0x180305bc3  test    eax, eax
0x180305bc5  js      loc_1803067BC
0x180305bcb  mov     this, [rsp+150h+resourcesMap.ptr_]
0x180305bd0  lea     r8, [rsp+150h+doesResourceExist]
0x180305bd5  mov     rdx, [rsp+150h+boxedResourceKey.ptr_]
0x180305bda  mov     rax, [this]
0x180305bdd  mov     rax, [rax+40h]
0x180305be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180305be6  mov     ebx, eax
0x180305be8  test    eax, eax
0x180305bea  js      loc_1803067B0
0x180305bf0  cmp     [rsp+150h+doesResourceExist], sil
0x180305bf5  jnz     loc_180306208
0x180305bfb  mov     this, [rsp+150h+boxedResource.ptr_]
0x180305c00  test    this, this
0x180305c03  jz      short loc_180305C16
0x180305c05  mov     [rsp+150h+boxedResource.ptr_], rsi
0x180305c0a  mov     rax, [this]
0x180305c0d  mov     rax, [rax+10h]
0x180305c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180305c16  mov     this, [rsp+150h+boxedResourceKey.ptr_]
0x180305c1b  test    this, this
0x180305c1e  jz      short loc_180305C31
0x180305c20  mov     [rsp+150h+boxedResourceKey.ptr_], rsi
0x180305c25  mov     rax, [this]
0x180305c28  mov     rax, [rax+10h]
0x180305c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180305c31  mov     this, [rsp+150h+resourcesMap.ptr_]
0x180305c36  test    this, this
0x180305c39  jz      short loc_180305C4C
0x180305c3b  mov     [rsp+150h+resourcesMap.ptr_], rsi
0x180305c40  mov     rax, [this]
0x180305c43  mov     rax, [rax+10h]
0x180305c47  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
