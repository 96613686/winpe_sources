# DirectUI::PasswordBox::OnApplyTemplateHandler(CPasswordBox *)

- ea: `0x1803038d0`
- end: `0x1803042e7`
- name: `?OnApplyTemplateHandler@PasswordBox@DirectUI@@SAJPEAVCPasswordBox@@@Z`
- size: `2583`
- prototype: `HRESULT __fastcall(CPasswordBox *pNativePasswordBox)`
- caller_count: `1`
- callee_count: `45`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180266130`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x18000616c`
- `0x180011458`
- `0x18004bfd0`
- `0x18005bcac`
- `0x18005e96c`
- `0x18007d590`
- `0x18009ba40`
- `0x1800f2084`
- `0x1800f3fb4`
- `0x1800f4510`
- `0x180101870`
- `0x180131190`
- `0x1801d1a98`
- `0x1801df610`
- `0x1801dfeb0`
- `0x1801e5458`
- `0x180302ed4`
- `0x1803030f8`
- `0x180303738`
- `0x1803038d0`
- `0x1803042f0`
- `0x180304448`
- `0x180305124`
- `0x1803839c0`
- `0x180383ffc`
- `0x180385e2c`
- `0x180453a04`
- `0x1804572ec`
- `0x180471944`
- `0x180592024`
- `0x18059c4c0`
- `0x180613b44`
- `0x1806eca0c`
- `0x1806fc57c`
- `0x1807018d4`
- `0x1807077b0`
- `0x180708adc`
- `0x180744ddc`
- `0x18076e110`
- `0x180974c9c`
- `0x180974cf4`
- `0x180974d4c`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180303fe0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180303fe0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180303ba1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180303d9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180303ded`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180303e4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180303e97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803041a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180303ba1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180303d9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180303ded`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180303e4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180303e97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803041a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1803039a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1803039a7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18030418e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18030418e`

## pseudocode

```c
__int64 __fastcall DirectUI::PasswordBox::OnApplyTemplateHandler(CPasswordBox *pNativePasswordBox)
{
  Windows::Foundation::IPropertyValue *v1; // r13
  DirectUI::DXamlCore *Current; // rbx
  HRESULT PeerPrivate; // eax
  HSTRING__ *hstring; // rsi
  HRESULT v6; // ebx
  HRESULT v7; // eax
  __int64 (__fastcall *v8)(HSTRING__ *, std::_Func_base<long,IInspectable *,Windows::UI::Xaml::Input::IPointerRoutedEventArgs *> *, ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> *); // rdi
  HRESULT v9; // eax
  CFrameworkElement *Handle; // rax
  unsigned int v11; // ebx
  char v12; // r14
  IWeakReference *v13; // r15
  HSTRING__ *v14; // r14
  DirectUI::PasswordBox::RevealButtonPropertyChangedHandler *FailFast; // rax
  IUnknown *v16; // rdi
  HSTRING__ *v17; // rax
  HSTRING__ *v18; // rbx
  DirectUI::TrackerTargetReference *v19; // rcx
  Windows::UI::Xaml::Controls::Primitives::IButtonBase *v20; // rbx
  HRESULT DPChangedEventSource; // eax
  HRESULT v22; // eax
  IWeakReference_vtbl *v23; // rax
  IWeakReference *ptr; // rcx
  Windows::UI::Xaml::Controls::Primitives::IButtonBase *v25; // rcx
  Windows::UI::Xaml::IDependencyObject *v26; // rcx
  Windows::UI::Xaml::IUIElement *v28; // rdx
  HRESULT updated; // eax
  std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::ISizeChangedEventArgs *)> *v30; // rax
  Windows::UI::Xaml::IFrameworkElement *v31; // rdx
  std::_Func_base<long,IInspectable *,Windows::UI::Xaml::Input::IPointerRoutedEventArgs *> *v32; // rax
  __int64 v33; // rdx
  HRESULT ValueByKnownIndex; // eax
  Windows::Foundation::IPropertyValueStatics *v35; // rdi
  DirectUI::DXamlCore *v36; // rbx
  HRESULT v37; // eax
  char *v38; // rcx
  HRESULT v39; // eax
  std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *)> *v40; // rax
  Windows::UI::Xaml::Controls::Primitives::IToggleButton *v41; // rdx
  std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *)> *v42; // rax
  Windows::UI::Xaml::Controls::Primitives::IToggleButton *v43; // rdx
  Windows::UI::Xaml::Controls::Primitives::IToggleButton *v44; // rcx
  const CDependencyProperty *DependencyPropertyByIndex; // rax
  HRESULT IsPropertyLocal; // eax
  _QWORD *v47; // rax
  HRESULT ActivationFactory; // eax
  DirectUI::DXamlCore *v49; // rbx
  Windows::Foundation::IPropertyValueStatics *v50; // rdi
  HRESULT (__fastcall *CreateString)(Windows::Foundation::IPropertyValueStatics *, HSTRING__ *, IInspectable **); // rbx
  __int64 v52; // rcx
  unsigned __int8 fIsPropertyLocal[8]; // [rsp+40h] [rbp-89h] BYREF
  ctl::WeakRefPtr wrWeakThis; // [rsp+48h] [rbp-81h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::IToggleButton> spToggleButton; // [rsp+50h] [rbp-79h] BYREF
  ctl::ComPtr<Windows::Foundation::IPropertyValueStatics> spPropertyValueFactory; // [rsp+58h] [rbp-71h] BYREF
  Windows::Internal::String strShowPasswordText; // [rsp+60h] [rbp-69h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::IButtonBase> spButton; // [rsp+68h] [rbp-61h] BYREF
  ctl::ComPtr<Windows::Foundation::IPropertyValue> spContentAsPV; // [rsp+70h] [rbp-59h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> spObject; // [rsp+78h] [rbp-51h] BYREF
  HSTRING__ *pPasswordBoxText; // [rsp+80h] [rbp-49h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IUIElement> spPlaceholderTextPresenter; // [rsp+88h] [rbp-41h] BYREF
  CPasswordBox *v63; // [rsp+90h] [rbp-39h]
  std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::Input::IPointerRoutedEventArgs *)> string; // [rsp+98h] [rbp-31h] BYREF

  v1 = 0;
  v63 = pNativePasswordBox;
  spContentAsPV.ptr_ = 0;
  spPlaceholderTextPresenter.ptr_ = 0;
  pPasswordBoxText = 0;
  strShowPasswordText._hstring = 0;
  spObject.ptr_ = 0;
  spButton.ptr_ = 0;
  Current = DirectUI::DXamlCore::GetCurrent();
  ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&strShowPasswordText);
  PeerPrivate = DirectUI::DXamlCore::GetPeerPrivate(
                  Current,
                  0,
                  pNativePasswordBox,
                  CreateIfNecessary,
                  0,
                  0,
                  (DirectUI::DependencyObject **)&strShowPasswordText);
  hstring = strShowPasswordText._hstring;
  v6 = PeerPrivate;
  if ( PeerPrivate < 0 )
  {
    OnFailure_2990_(PeerPrivate);
    goto LABEL_29;
  }
  v7 = DirectUI::PasswordBox::ReleaseTemplateParts((DirectUI::PasswordBox *)strShowPasswordText._hstring);
  v6 = v7;
  if ( v7 < 0 )
    goto LABEL_82;
  v8 = *(__int64 (__fastcall **)(HSTRING__ *, std::_Func_base<long,IInspectable *,Windows::UI::Xaml::Input::IPointerRoutedEventArgs *> *, ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> *))(*((_QWORD *)hstring + 57) + 64LL);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spObject);
  if ( WindowsCreateStringReference(
         L"RevealButton",
         0xCu,
         (HSTRING_HEADER *)&string._Mystorage._Ptrs[1],
         (HSTRING *)&string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v7 = v8(hstring + 114, string._Mystorage._Ptrs[0], &spObject);
  v6 = v7;
  if ( v7 < 0
    || (v7 = DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::IUIElement,Windows::UI::Xaml::IUIElement>(
               (DirectUI::Control *)hstring,
               (wchar_t *)L"PlaceholderTextContentPresenter",
               0x1Fu,
               &spPlaceholderTextPresenter.ptr_),
        v6 = v7,
        v7 < 0)
    || (ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spButton),
        spObject.ptr_)
    && (v7 = spObject.ptr_->QueryInterface(
               spObject.ptr_,
               &GUID_fa002c1a_494e_46cf_91d4_e14a8d798674,
               (void **)&spButton),
        v6 = v7,
        v7 < 0) )
  {
LABEL_82:
    OnFailure_2990_(v7);
    goto $Cleanup_2037;
  }
  ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(
    (ctl::WeakReferenceSourceNoThreadId *)(hstring + 2),
    (DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *>,1,0> *)(hstring + 160),
    (Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Automation::Provider::IRawElementProviderSimple *> *)spButton.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::IUIElement,Windows::UI::Xaml::IUIElement>(
    (ctl::WeakReferenceSourceNoThreadId *)(hstring + 2),
    (DirectUI::TrackerPtr<Windows::UI::Xaml::IUIElement,1,0> *)(hstring + 152),
    spPlaceholderTextPresenter.ptr_);
  if ( !spButton.ptr_ )
  {
LABEL_46:
    updated = DirectUI::PasswordBox::UpdateHeaderPresenterVisibility((DirectUI::PasswordBox *)hstring);
    v6 = updated;
    if ( updated < 0
      || (updated = (*(__int64 (__fastcall **)(HSTRING__ *, HSTRING__ **))(*((_QWORD *)hstring + 67) + 48LL))(
                      hstring + 134,
                      &pPasswordBoxText),
          v6 = updated,
          updated < 0)
      || (updated = DirectUI::PasswordBox::UpdatePlaceholderTextPresenterVisibility(
                      (DirectUI::PasswordBox *)hstring,
                      pPasswordBoxText == 0),
          v6 = updated,
          updated < 0) )
    {
      OnFailure_2990_(updated);
    }
    goto $Cleanup_2037;
  }
  wrWeakThis.ptr_ = 0;
  v9 = ctl::AsWeak<DirectUI::PasswordBox>((DirectUI::PasswordBox *)hstring, &wrWeakThis);
  v6 = v9;
  if ( v9 < 0 )
  {
    OnFailure_2990_(v9);
LABEL_64:
    ptr = wrWeakThis.ptr_;
    if ( !wrWeakThis.ptr_ )
      goto $Cleanup_2037;
    v23 = wrWeakThis.ptr_->__vftable;
LABEL_26:
    v23->Release(ptr);
    goto $Cleanup_2037;
  }
  Handle = (CFrameworkElement *)DirectUI::DependencyObject::GetHandle((DirectUI::DependencyObject *)((__int64)&spButton.ptr_[-71] & -(__int64)(spButton.ptr_ != 0)));
  CFrameworkElement::SetCursor(Handle, MouseCursorArrow);
  v11 = ctl::is<Windows::UI::Xaml::Controls::Primitives::IToggleButton,Windows::UI::Xaml::Controls::Primitives::IButtonBase>(&spButton);
  if ( ctl::is<Windows::UI::Xaml::Controls::ICheckBox,Windows::UI::Xaml::Controls::Primitives::IButtonBase>(&spButton) )
  {
    v12 = 1;
    *((_BYTE *)hstring + 729) = 1;
  }
  else
  {
    v12 = 0;
  }
  if ( !v11 )
    goto LABEL_13;
  if ( !v12 )
  {
    WindowsDeleteString(0);
    spPropertyValueFactory.ptr_ = 0;
    ValueByKnownIndex = DirectUI::DependencyObject::GetValueByKnownIndex(
                          (DirectUI::DependencyObject *)((__int64)&spButton.ptr_[-71] & -(__int64)(spButton.ptr_ != 0)),
                          AutomationProperties_Name,
                          (HSTRING__ **)&spPropertyValueFactory);
    v6 = ValueByKnownIndex;
    if ( ValueByKnownIndex < 0 )
      goto LABEL_84;
    v35 = spPropertyValueFactory.ptr_;
    if ( spPropertyValueFactory.ptr_ )
    {
LABEL_67:
      WindowsDeleteString((HSTRING)v35);
      goto LABEL_68;
    }
    v36 = DirectUI::DXamlCore::GetCurrent();
    WindowsDeleteString(0);
    spPropertyValueFactory.ptr_ = 0;
    ValueByKnownIndex = DirectUI::DXamlCore::GetLocalizedResourceString(
                          v36,
                          0x14D5u,
                          (HSTRING__ **)&spPropertyValueFactory);
    v6 = ValueByKnownIndex;
    if ( ValueByKnownIndex < 0 )
    {
LABEL_84:
      OnFailure_2990_(ValueByKnownIndex);
      Windows::Internal::String::~String((Windows::Internal::String *)&spPropertyValueFactory);
LABEL_86:
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&wrWeakThis);
      goto $Cleanup_2037;
    }
    v35 = spPropertyValueFactory.ptr_;
    v37 = DirectUI::DependencyObject::SetValueByKnownIndex(
            (DirectUI::DependencyObject *)((__int64)&spButton.ptr_[-71] & -(__int64)(spButton.ptr_ != 0)),
            AutomationProperties_Name,
            (HSTRING__ *)spPropertyValueFactory.ptr_);
    v6 = v37;
    if ( v37 < 0 )
    {
      OnFailure_2990_(v37);
      if ( v35 )
        WindowsDeleteString((HSTRING)v35);
      goto LABEL_64;
    }
    if ( v35 )
      goto LABEL_67;
  }
LABEL_68:
  spToggleButton.ptr_ = 0;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spToggleButton);
  if ( spButton.ptr_
    && (v39 = spButton.ptr_->QueryInterface(
                spButton.ptr_,
                &GUID_589877fb_0fc7_4036_9d8b_127dfa75c16d,
                (void **)&spToggleButton),
        v6 = v39,
        v39 < 0)
    || (v39 = spToggleButton.ptr_->put_IsChecked(spToggleButton.ptr_, 0), v6 = v39, v39 < 0) )
  {
LABEL_110:
    OnFailure_2990_(v39);
    goto LABEL_89;
  }
  lambda_f1802912b035dcb592eb4204d4dbbee4_::_lambda_f1802912b035dcb592eb4204d4dbbee4_((const ctl::WeakRefPtr *)&strShowPasswordText);
  std::function_long___cdecl_IInspectable___Windows::UI::Xaml::IRoutedEventArgs____::function_long___cdecl_IInspectable___Windows::UI::Xaml::IRoutedEventArgs______lambda_8207be50e93a4cf12fbddd49503f4516__0_((DirectUI::PasswordBox::OnApplyTemplateHandler::__l47::<lambda_8207be50e93a4cf12fbddd49503f4516> *)&string);
  if ( ((__int64)&spToggleButton.ptr_[-79] & -(__int64)(spToggleButton.ptr_ != 0)) != 0 )
    v41 = (Windows::UI::Xaml::Controls::Primitives::IToggleButton *)(((__int64)&spToggleButton.ptr_[-79]
                                                                    & -(__int64)(spToggleButton.ptr_ != 0))
                                                                   + 632);
  else
    v41 = 0;
  v6 = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::ToggleButtonCheckedTraits>>::AttachEventHandler(
         (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::ToggleButtonCheckedTraits> > *)hstring
       + 87,
         v41,
         v40);
  ctl::ComPtr<Windows::Foundation::IReference<Windows::Foundation::Numerics::Vector2>>::~ComPtr<Windows::Foundation::IReference<Windows::Foundation::Numerics::Vector2>>((ctl::ComPtr<Windows::Foundation::Metadata::IApiInformationStatics> *)&strShowPasswordText);
  if ( v6 < 0
    || ((lambda_f1802912b035dcb592eb4204d4dbbee4_::_lambda_f1802912b035dcb592eb4204d4dbbee4_((const ctl::WeakRefPtr *)&strShowPasswordText),
         std::function_long___cdecl_IInspectable___Windows::UI::Xaml::IRoutedEventArgs____::function_long___cdecl_IInspectable___Windows::UI::Xaml::IRoutedEventArgs______lambda_2098f9520344841e41557f3a1ddb12ae__0_((DirectUI::PasswordBox::OnApplyTemplateHandler::__l47::<lambda_2098f9520344841e41557f3a1ddb12ae> *)&string),
         ((__int64)&spToggleButton.ptr_[-79] & -(__int64)(spToggleButton.ptr_ != 0)) == 0)
      ? (v43 = 0)
      : (v43 = (Windows::UI::Xaml::Controls::Primitives::IToggleButton *)(((__int64)&spToggleButton.ptr_[-79]
                                                                         & -(__int64)(spToggleButton.ptr_ != 0))
                                                                        + 632)),
        v6 = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::ToggleButtonUncheckedTraits>>::AttachEventHandler(
               (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::ToggleButtonUncheckedTraits> > *)hstring
             + 88,
               v43,
               v42),
        ctl::ComPtr<Windows::Foundation::IReference<Windows::Foundation::Numerics::Vector2>>::~ComPtr<Windows::Foundation::IReference<Windows::Foundation::Numerics::Vector2>>((ctl::ComPtr<Windows::Foundation::Metadata::IApiInformationStatics> *)&strShowPasswordText),
        v6 < 0) )
  {
    OnFailure_2990_(v6);
LABEL_89:
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spToggleButton);
    goto LABEL_86;
  }
  v44 = spToggleButton.ptr_;
  if ( spToggleButton.ptr_ )
  {
    spToggleButton.ptr_ = 0;
    v44->Release(v44);
  }
LABEL_13:
  v13 = wrWeakThis.ptr_;
  if ( v12 )
  {
    spToggleButton.ptr_ = 0;
    fIsPropertyLocal[0] = 0;
    v39 = DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::Primitives::IButtonBase,1,0>::As<Windows::UI::Xaml::Controls::Primitives::IToggleButton>(
            (DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::Primitives::IButtonBase,1,0> *)&spButton,
            (ctl::Internal::ComPtrRef<ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::IToggleButton> >)&spToggleButton);
    v6 = v39;
    if ( v39 >= 0 )
    {
      DependencyPropertyByIndex = DirectUI::MetadataAPI::GetDependencyPropertyByIndex(ContentControl_Content);
      IsPropertyLocal = DirectUI::DependencyObject::IsPropertyLocal(
                          (DirectUI::DependencyObject *)((__int64)&spToggleButton.ptr_[-79]
                                                       & -(__int64)(spToggleButton.ptr_ != 0)),
                          DependencyPropertyByIndex,
                          fIsPropertyLocal);
      v6 = IsPropertyLocal;
      if ( IsPropertyLocal < 0 )
      {
        OnFailure_2990_(IsPropertyLocal);
      }
      else
      {
        if ( fIsPropertyLocal[0] )
        {
LABEL_105:
          v63->m_fAlwaysShowRevealButton = 1;
          ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spToggleButton);
LABEL_44:
          if ( v13 )
            v13->Release(v13);
          goto LABEL_46;
        }
        spPropertyValueFactory.ptr_ = 0;
        spContentAsPV.ptr_ = 0;
        strShowPasswordText._hstring = 0;
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spPropertyValueFactory);
        Windows::Internal::StringReference::StringReference(
          (Windows::Internal::StringReference *)&string,
          (const wchar_t (*)[33])RuntimeClass_Windows_Foundation_PropertyValue);
        ActivationFactory = RoGetActivationFactory(
                              *v47,
                              &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858,
                              &spPropertyValueFactory);
        v6 = ActivationFactory;
        if ( ActivationFactory >= 0 )
        {
          v49 = DirectUI::DXamlCore::GetCurrent();
          WindowsDeleteString(0);
          ActivationFactory = DirectUI::DXamlCore::GetLocalizedResourceString(
                                v49,
                                0x13E0u,
                                &strShowPasswordText._hstring);
          v6 = ActivationFactory;
          if ( ActivationFactory >= 0 )
          {
            v50 = spPropertyValueFactory.ptr_;
            CreateString = spPropertyValueFactory.ptr_->CreateString;
            ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spContentAsPV);
            ActivationFactory = CreateString(v50, strShowPasswordText._hstring, &spContentAsPV.ptr_);
            v6 = ActivationFactory;
            if ( ActivationFactory >= 0 )
            {
              v52 = (__int64)&spToggleButton.ptr_[-12];
              if ( !spToggleButton.ptr_ )
                v52 = 536;
              ActivationFactory = (*(__int64 (__fastcall **)(__int64, Windows::Foundation::IPropertyValue *))(*(_QWORD *)v52 + 56LL))(
                                    v52,
                                    spContentAsPV.ptr_);
              v6 = ActivationFactory;
              if ( ActivationFactory >= 0 )
              {
                Windows::Internal::String::~String(&strShowPasswordText);
                ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spContentAsPV);
                ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spPropertyValueFactory);
                goto LABEL_105;
              }
            }
          }
        }
        OnFailure_2990_(ActivationFactory);
        Windows::Internal::String::~String(&strShowPasswordText);
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spContentAsPV);
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spPropertyValueFactory);
      }
      goto LABEL_89;
    }
    goto LABEL_110;
  }
  v14 = 0;
  strShowPasswordText._hstring = 0;
  FailFast = (DirectUI::PasswordBox::RevealButtonPropertyChangedHandler *)XcpAllocation::OSMemoryAllocateFailFast(0x18u);
  if ( FailFast )
  {
    DirectUI::PasswordBox::RevealButtonPropertyChangedHandler::RevealButtonPropertyChangedHandler(
      FailFast,
      (DirectUI::PasswordBox *)hstring);
    v16 = 0;
    v18 = v17;
    if ( v17 )
    {
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&strShowPasswordText);
      v14 = v18;
      strShowPasswordText._hstring = v18;
      v16 = (IUnknown *)v18;
    }
  }
  else
  {
    v16 = 0;
  }
  ctl::WeakReferenceSourceNoThreadId::RegisterPtr(
    (ctl::WeakReferenceSourceNoThreadId *)(hstring + 2),
    (DirectUI::TrackerTargetReference *const)(hstring + 166));
  v19 = (DirectUI::TrackerTargetReference *)(hstring + 166);
  if ( v16 )
    DirectUI::TrackerTargetReference::Set(v19, v16, 1u, 0);
  else
    DirectUI::TrackerTargetReference::Clear(v19, 1u, 0);
  v20 = spButton.ptr_;
  ctl::ComPtr<DirectUI::IDPChangedEventSource>::InternalRelease((ctl::ComPtr<DirectUI::IDPChangedEventSource> *)&spContentAsPV);
  DPChangedEventSource = DirectUI::DependencyObject::GetDPChangedEventSource(
                           (DirectUI::DependencyObject *)((unsigned __int64)&v20[-71] & -(__int64)(v20 != 0)),
                           (DirectUI::IDPChangedEventSource **)&spContentAsPV);
  v6 = DPChangedEventSource;
  if ( DPChangedEventSource >= 0 )
  {
    v1 = spContentAsPV.ptr_;
    v22 = ((__int64 (__fastcall *)(Windows::Foundation::IPropertyValue *, HSTRING__ *))spContentAsPV.ptr_->QueryInterface)(
            spContentAsPV.ptr_,
            v14);
    v6 = v22;
    if ( v22 < 0 )
    {
      OnFailure_2990_(v22);
      if ( v16 )
        v16->Release(v16);
      if ( !v13 )
        goto $Cleanup_2037;
      v23 = v13->__vftable;
      ptr = v13;
      goto LABEL_26;
    }
    lambda_f1802912b035dcb592eb4204d4dbbee4_::_lambda_f1802912b035dcb592eb4204d4dbbee4_((const ctl::WeakRefPtr *)&spPropertyValueFactory);
    std::function_long___cdecl_IInspectable___Windows::UI::Xaml::ISizeChangedEventArgs____::function_long___cdecl_IInspectable___Windows::UI::Xaml::ISizeChangedEventArgs______lambda_92dabb9d7f125d744a2349985f1e17b4__0_((DirectUI::PasswordBox::OnApplyTemplateHandler::__l98::<lambda_92dabb9d7f125d744a2349985f1e17b4> *)&string);
    v31 = (Windows::UI::Xaml::IFrameworkElement *)(((__int64)&spButton.ptr_[-71] & -(__int64)(spButton.ptr_ != 0)) + 352);
    if ( ((__int64)&spButton.ptr_[-71] & -(__int64)(spButton.ptr_ != 0)) == 0 )
      v31 = 0;
    v6 = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::ISizeChangedEventHandler,IInspectable,Windows::UI::Xaml::ISizeChangedEventArgs,DirectUI::FrameworkElementSizeChangedTraits>>::AttachEventHandler(
           (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::ISizeChangedEventHandler,IInspectable,Windows::UI::Xaml::ISizeChangedEventArgs,DirectUI::FrameworkElementSizeChangedTraits> > *)hstring
         + 86,
           v31,
           v30);
    ctl::ComPtr<Windows::Foundation::IReference<Windows::Foundation::Numerics::Vector2>>::~ComPtr<Windows::Foundation::IReference<Windows::Foundation::Numerics::Vector2>>((ctl::ComPtr<Windows::Foundation::Metadata::IApiInformationStatics> *)&spPropertyValueFactory);
    if ( v6 >= 0 )
    {
      spPropertyValueFactory.ptr_ = (Windows::Foundation::IPropertyValueStatics *)v13;
      Microsoft::WRL::ComPtr<ICastingEventHandler>::InternalAddRef((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo> *)&spPropertyValueFactory);
      string._Mystorage._Ptrs[7] = 0;
      std::_Func_impl_no_alloc__lambda_f35245ce803cd00a1837c2470ccb7751__long_IInspectable___Windows::UI::Xaml::Input::IPointerRoutedEventArgs___::_Func_impl_no_alloc__lambda_f35245ce803cd00a1837c2470ccb7751__long_IInspectable___Windows::UI::Xaml::Input::IPointerRoutedEventArgs_____lambda_f35245ce803cd00a1837c2470ccb7751__0_((DirectUI::PasswordBox::OnApplyTemplateHandler::__l98::<lambda_f35245ce803cd00a1837c2470ccb7751> *)&string);
      string._Mystorage._Ptrs[7] = v32;
      v33 = (unsigned __int128)&spButton.ptr_[-71]
          & ((unsigned __int128)-(__int128)(unsigned __int64)spButton.ptr_ >> 64);
      v28 = v33 ? (Windows::UI::Xaml::IUIElement *)(v33 + 184) : 0LL;
      v6 = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs,DirectUI::UIElementPointerReleasedTraits>>::AttachEventHandler(
             (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs,DirectUI::UIElementPointerReleasedTraits> > *)hstring
           + 89,
             v28,
             &string);
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spPropertyValueFactory);
      if ( v6 >= 0 )
      {
        if ( v14 )
          (*(void (__fastcall **)(HSTRING__ *))(*(_QWORD *)v14 + 16LL))(v14);
        goto LABEL_44;
      }
    }
    OnFailure_2990_(v6);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&strShowPasswordText);
    goto LABEL_86;
  }
  OnFailure_2990_(DPChangedEventSource);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&strShowPasswordText);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&wrWeakThis);
  v1 = spContentAsPV.ptr_;
$Cleanup_2037:
  if ( hstring )
    *((_BYTE *)hstring + 632) = 0;
LABEL_29:
  WindowsDeleteString(pPasswordBoxText);
  if ( spPlaceholderTextPresenter.ptr_ )
    spPlaceholderTextPresenter.ptr_->Release(spPlaceholderTextPresenter.ptr_);
  if ( v1 )
  {
    v38 = (char *)&v1[1] + SHIDWORD(v1[1].QueryInterface);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v38 + 16LL))(v38);
  }
  v25 = spButton.ptr_;
  if ( spButton.ptr_ )
  {
    spButton.ptr_ = 0;
    v25->Release(v25);
  }
  v26 = spObject.ptr_;
  if ( spObject.ptr_ )
  {
    spObject.ptr_ = 0;
    v26->Release(v26);
  }
  if ( hstring )
    (*(void (__fastcall **)(HSTRING__ *))(*((_QWORD *)hstring + 1) + 16LL))(hstring + 2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1803038d0  push    rbp
0x1803038d2  push    rbx
0x1803038d3  push    rsi
0x1803038d4  push    rdi
0x1803038d5  push    r12
0x1803038d7  push    r13
0x1803038d9  push    r14
0x1803038db  push    r15
0x1803038dd  lea     rbp, [rsp-1Fh]
0x1803038e2  sub     rsp, 0E8h
0x1803038e9  mov     rax, cs:__security_cookie
0x1803038f0  xor     rax, rsp
0x1803038f3  mov     [rbp+57h+var_48], rax
0x1803038f7  xor     r13d, r13d
0x1803038fa  mov     [rbp+57h+var_90], pNativePasswordBox
0x1803038fe  mov     [rbp+57h+spContentAsPV.ptr_], r13
0x180303902  mov     rdi, pNativePasswordBox
0x180303905  mov     [rbp+57h+spPlaceholderTextPresenter.ptr_], r13
0x180303909  mov     [rbp+57h+pPasswordBoxText], r13
0x18030390d  mov     [rbp+57h+strShowPasswordText._hstring], 0
0x180303915  mov     [rbp+57h+spObject.ptr_], 0
0x18030391d  mov     [rbp+57h+spButton.ptr_], 0
0x180303925  call    ?GetCurrent@DXamlCore@DirectUI@@SAPEAV12@XZ; DirectUI::DXamlCore::GetCurrent(void)
0x18030392a  lea     pNativePasswordBox, [rbp+57h+strShowPasswordText]; this
0x18030392e  mov     rbx, rax
0x180303931  call    ?InternalRelease@?$ComPtr@VStoryboard@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::Storyboard>::InternalRelease(void)
0x180303936  lea     rax, [rbp+57h+strShowPasswordText]
0x18030393a  mov     r8, rdi; pDO
0x18030393d  mov     [rsp+120h+ppObject], rax; ppObject
0x180303942  lea     r15d, [r13+1]
0x180303946  mov     [rsp+120h+pIsPendingDelete], r13; pIsPendingDelete
0x18030394b  mov     r9d, r15d; createMode
0x18030394e  xor     edx, edx; pOuter
0x180303950  mov     [rsp+120h+bInternalRef], r13d; bInternalRef
0x180303955  mov     pNativePasswordBox, rbx; this
0x180303958  call    ?GetPeerPrivate@DXamlCore@DirectUI@@AEAAJPEAUIInspectable@@PEAVCDependencyObject@@W4GetPeerPrivateCreateMode@12@IPEAIPEAPEAVDependencyObject@2@@Z; DirectUI::DXamlCore::GetPeerPrivate(IInspectable *,CDependencyObject *,DirectUI::DXamlCore::GetPeerPrivateCreateMode,uint,uint *,DirectUI::DependencyObject * *)
0x18030395d  mov     rsi, [rbp+57h+strShowPasswordText._hstring]
0x180303961  mov     ebx, eax
0x180303963  test    eax, eax
0x180303965  js      loc_1803042DB
0x18030396b  mov     pNativePasswordBox, rsi; this
0x18030396e  call    ?ReleaseTemplateParts@PasswordBox@DirectUI@@AEAAJXZ; DirectUI::PasswordBox::ReleaseTemplateParts(void)
0x180303973  mov     ebx, eax
0x180303975  test    eax, eax
0x180303977  js      loc_1803042C3
0x18030397d  lea     rbx, [rsi+1C8h]
0x180303984  mov     rax, [rbx]
0x180303987  lea     pNativePasswordBox, [rbp+57h+spObject]; this
0x18030398b  mov     rdi, [rax+40h]
0x18030398f  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180303994  lea     r9, [rbp+57h+string]; string
0x180303998  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18030399c  lea     edx, [r13+0Ch]; length
0x1803039a0  lea     pNativePasswordBox, aRevealbutton; "RevealButton"
0x1803039a7  call    cs:__imp_WindowsCreateStringReference
0x1803039ad  test    eax, eax
0x1803039af  js      loc_180303FD2
0x1803039b5  mov     rdx, [rbp+57h+string]
0x1803039b9  lea     r8, [rbp+57h+spObject]
0x1803039bd  mov     pNativePasswordBox, rbx
0x1803039c0  mov     rax, rdi
0x1803039c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803039c8  mov     ebx, eax
0x1803039ca  test    eax, eax
0x1803039cc  js      loc_1803042B7
0x1803039d2  lea     r9, [rbp+57h+spPlaceholderTextPresenter]; ppReference
0x1803039d6  mov     r8d, 1Fh; cName
0x1803039dc  lea     rdx, aPlaceholdertex_0; "PlaceholderTextContentPresenter"
0x1803039e3  mov     pNativePasswordBox, rsi; this
0x1803039e6  call    ??$GetTemplatePart@UIUIElement@Xaml@UI@Windows@@U1234@@Control@DirectUI@@QEAAJPEAG_KPEAPEAUIUIElement@Xaml@UI@Windows@@@Z; DirectUI::Control::GetTemplatePart<Windows::UI::Xaml::IUIElement,Windows::UI::Xaml::IUIElement>(ushort *,unsigned __int64,Windows::UI::Xaml::IUIElement * *)
0x1803039eb  mov     ebx, eax
0x1803039ed  test    eax, eax
0x1803039ef  js      loc_1803042AB
0x1803039f5  lea     pNativePasswordBox, [rbp+57h+spButton]; this
0x1803039f9  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1803039fe  mov     pNativePasswordBox, [rbp+57h+spObject.ptr_]
0x180303a02  test    pNativePasswordBox, pNativePasswordBox
0x180303a05  jnz     loc_180303FEB
0x180303a0b  mov     r8, [rbp+57h+spButton.ptr_]; value
0x180303a0f  lea     r12, [rsi+8]
0x180303a13  mov     pNativePasswordBox, r12; this
0x180303a16  lea     rdx, [rsi+280h]; ptr
0x180303a1d  call    ??$SetPtrValue@U?$IVector@PEAVWebViewDeferredPermissionRequest@Controls@Xaml@UI@Windows@@@Collections@Foundation@Windows@@U1234@@WeakReferenceSourceNoThreadId@ctl@@QEAAXAEAV?$TrackerPtr@U?$IVector@PEAVWebViewDeferredPermissionRequest@Controls@Xaml@UI@Windows@@@Collections@Foundation@Windows@@$00$0A@@DirectUI@@PEAU?$IVector@PEAVWebViewDeferredPermissionRequest@Controls@Xaml@UI@Windows@@@Collections@Foundation@Windows@@@Z; ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>>(DirectUI::TrackerPtr<Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *>,1,0> &,Windows::Foundation::Collections::IVector<Windows::UI::Xaml::Controls::WebViewDeferredPermissionRequest *> *)
0x180303a22  mov     r8, [rbp+57h+spPlaceholderTextPresenter.ptr_]; value
0x180303a26  lea     rdx, [rsi+260h]; ptr
0x180303a2d  mov     pNativePasswordBox, r12; this
0x180303a30  call    ??$SetPtrValueWithQIOrNull@UIUIElement@Xaml@UI@Windows@@U1234@@WeakReferenceSourceNoThreadId@ctl@@IEAAXAEAV?$TrackerPtr@UIUIElement@Xaml@UI@Windows@@$00$0A@@DirectUI@@PEAUIUIElement@Xaml@UI@Windows@@@Z; ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::IUIElement,Windows::UI::Xaml::IUIElement>(DirectUI::TrackerPtr<Windows::UI::Xaml::IUIElement,1,0> &,Windows::UI::Xaml::IUIElement *)
0x180303a35  cmp     [rbp+57h+spButton.ptr_], r13
0x180303a39  jz      loc_180303C88
0x180303a3f  lea     rdx, [rsp+120h+wrWeakThis]; pWeak
0x180303a44  mov     [rsp+120h+wrWeakThis.ptr_], r13
0x180303a49  mov     pNativePasswordBox, rsi; p
0x180303a4c  call    ??$AsWeak@VPasswordBox@DirectUI@@@ctl@@YAJPEAVPasswordBox@DirectUI@@PEAVWeakRefPtr@0@@Z; ctl::AsWeak<DirectUI::PasswordBox>(DirectUI::PasswordBox *,ctl::WeakRefPtr *)
0x180303a51  mov     ebx, eax
0x180303a53  test    eax, eax
0x180303a55  js      loc_180303E52
0x180303a5b  mov     rax, [rbp+57h+spButton.ptr_]
0x180303a5f  lea     rdx, [rax-238h]
0x180303a66  neg     rax
0x180303a69  sbb     pNativePasswordBox, pNativePasswordBox
0x180303a6c  and     pNativePasswordBox, rdx; this
0x180303a6f  call    ?GetHandle@DependencyObject@DirectUI@@QEBAPEAVCDependencyObject@@XZ; DirectUI::DependencyObject::GetHandle(void)
0x180303a74  mov     pNativePasswordBox, rax; this
0x180303a77  mov     dl, r15b; cursor
0x180303a7a  call    ?SetCursor@CFrameworkElement@@QEAAJW4MouseCursor@@@Z; CFrameworkElement::SetCursor(MouseCursor)
0x180303a7f  lea     pNativePasswordBox, [rbp+57h+spButton]; spInterface
0x180303a83  call    ??$is@UIToggleButton@Primitives@Controls@Xaml@UI@Windows@@UIButtonBase@23456@@ctl@@YAIAEAV?$ComPtr@UIButtonBase@Primitives@Controls@Xaml@UI@Windows@@@0@@Z; ctl::is<Windows::UI::Xaml::Controls::Primitives::IToggleButton,Windows::UI::Xaml::Controls::Primitives::IButtonBase>(ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::IButtonBase> &)
0x180303a88  lea     pNativePasswordBox, [rbp+57h+spButton]; spInterface
0x180303a8c  mov     ebx, eax
0x180303a8e  call    ??$is@UICheckBox@Controls@Xaml@UI@Windows@@UIButtonBase@Primitives@2345@@ctl@@YAIAEAV?$ComPtr@UIButtonBase@Primitives@Controls@Xaml@UI@Windows@@@0@@Z; ctl::is<Windows::UI::Xaml::Controls::ICheckBox,Windows::UI::Xaml::Controls::Primitives::IButtonBase>(ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::IButtonBase> &)
0x180303a93  test    eax, eax
0x180303a95  jnz     loc_180304017
0x180303a9b  xor     r14b, r14b
0x180303a9e  test    ebx, ebx
0x180303aa0  jnz     loc_180303D91
0x180303aa6  mov     r15, [rsp+120h+wrWeakThis.ptr_]
0x180303aab  test    r14b, r14b
0x180303aae  jnz     loc_1803040F8
0x180303ab4  xor     r14d, r14d
0x180303ab7  mov     [rbp+57h+strShowPasswordText._hstring], r14
0x180303abb  lea     ecx, [r14+18h]; cSize
0x180303abf  call    ?OSMemoryAllocateFailFast@XcpAllocation@@YAPEAX_K@Z; XcpAllocation::OSMemoryAllocateFailFast(unsigned __int64)
0x180303ac4  test    rax, rax
0x180303ac7  jnz     short loc_180303ACD
0x180303ac9  xor     edi, edi
0x180303acb  jmp     short loc_180303AE6
0x180303acd  mov     rdx, rsi; pPasswordBox
0x180303ad0  mov     pNativePasswordBox, rax; this
0x180303ad3  call    ??0RevealButtonPropertyChangedHandler@PasswordBox@DirectUI@@QEAA@PEAV12@@Z; DirectUI::PasswordBox::RevealButtonPropertyChangedHandler::RevealButtonPropertyChangedHandler(DirectUI::PasswordBox *)
0x180303ad8  xor     edi, edi
0x180303ada  mov     rbx, rax
0x180303add  test    rax, rax
0x180303ae0  jnz     loc_1803040B1
0x180303ae6  lea     rbx, [rsi+298h]
0x180303aed  mov     pNativePasswordBox, r12; this
0x180303af0  mov     rdx, rbx; pTrackerPtr
0x180303af3  call    ?RegisterPtr@WeakReferenceSourceNoThreadId@ctl@@AEAAXQEAVTrackerTargetReference@DirectUI@@@Z; ctl::WeakReferenceSourceNoThreadId::RegisterPtr(DirectUI::TrackerTargetReference * const)
0x180303af8  xor     r12d, r12d
0x180303afb  mov     pNativePasswordBox, rbx; this
0x180303afe  test    rdi, rdi
0x180303b01  jz      loc_180303CE2
0x180303b07  xor     r9d, r9d; bForceLoopback
0x180303b0a  mov     r8b, 1; bEnsureTrackerTarget
0x180303b0d  mov     rdx, rdi; pValue
0x180303b10  call    ?Set@TrackerTargetReference@DirectUI@@IEAAXQEAUIUnknown@@EE@Z; DirectUI::TrackerTargetReference::Set(IUnknown * const,uchar,uchar)
0x180303b15  mov     rbx, [rbp+57h+spButton.ptr_]
0x180303b19  lea     pNativePasswordBox, [rbp+57h+spContentAsPV]; this
0x180303b1d  call    ?InternalRelease@?$ComPtr@UIDPChangedEventSource@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::IDPChangedEventSource>::InternalRelease(void)
0x180303b22  lea     rax, [rbx-238h]
0x180303b29  neg     rbx
0x180303b2c  lea     rdx, [rbp+57h+spContentAsPV]; ppEventSource
0x180303b30  sbb     pNativePasswordBox, pNativePasswordBox
0x180303b33  and     pNativePasswordBox, rax; this
0x180303b36  call    ?GetDPChangedEventSource@DependencyObject@DirectUI@@QEAAJPEAPEAUIDPChangedEventSource@2@@Z; DirectUI::DependencyObject::GetDPChangedEventSource(DirectUI::IDPChangedEventSource * *)
0x180303b3b  mov     ebx, eax
0x180303b3d  test    eax, eax
0x180303b3f  js      loc_1803040D5
0x180303b45  mov     r13, [rbp+57h+spContentAsPV.ptr_]
0x180303b49  mov     rdx, r14
0x180303b4c  mov     pNativePasswordBox, r13
0x180303b4f  mov     rax, [r13+0]
0x180303b53  mov     rax, [rax]
0x180303b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180303b5b  mov     ebx, eax
0x180303b5d  test    eax, eax
0x180303b5f  jns     loc_180303CF1
0x180303b65  mov     ecx, eax; failedFrameHR
0x180303b67  call    OnFailure_2990_
0x180303b6c  test    rdi, rdi
0x180303b6f  jz      short loc_180303B80
0x180303b71  mov     rax, [rdi]
0x180303b74  mov     pNativePasswordBox, rdi
0x180303b77  mov     rax, [rax+10h]
0x180303b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180303b80  test    r15, r15
0x180303b83  jz      short $Cleanup_2037
0x180303b85  mov     rax, [r15]
0x180303b88  mov     pNativePasswordBox, r15
0x180303b8b  mov     rax, [rax+10h]
0x180303b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180303b94  test    rsi, rsi
0x180303b97  jnz     loc_1803042CF
0x180303b9d  mov     pNativePasswordBox, [rbp+57h+pPasswordBoxText]; string
0x180303ba1  call    cs:__imp_WindowsDeleteString
0x180303ba7  mov     pNativePasswordBox, [rbp+57h+spPlaceholderTextPresenter.ptr_]
0x180303bab  test    pNativePasswordBox, pNativePasswordBox
0x180303bae  jz      short loc_180303BBC
0x180303bb0  mov     rax, [pNativePasswordBox]
0x180303bb3  mov     rax, [rax+10h]
0x180303bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180303bbc  test    r13, r13
0x180303bbf  jnz     loc_180303E6F
0x180303bc5  mov     pNativePasswordBox, [rbp+57h+spButton.ptr_]
0x180303bc9  test    pNativePasswordBox, pNativePasswordBox
0x180303bcc  jz      short loc_180303BE2
0x180303bce  mov     [rbp+57h+spButton.ptr_], 0
0x180303bd6  mov     rax, [pNativePasswordBox]
0x180303bd9  mov     rax, [rax+10h]
0x180303bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180303be2  mov     pNativePasswordBox, [rbp+57h+spObject.ptr_]
0x180303be6  test    pNativePasswordBox, pNativePasswordBox
0x180303be9  jz      short loc_180303BFF
0x180303beb  mov     [rbp+57h+spObject.ptr_], 0
0x180303bf3  mov     rax, [pNativePasswordBox]
0x180303bf6  mov     rax, [rax+10h]
0x180303bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180303bff  test    rsi, rsi
0x180303c02  jz      short loc_180303C14
0x180303c04  lea     pNativePasswordBox, [rsi+8]
0x180303c08  mov     rax, [pNativePasswordBox]
0x180303c0b  mov     rax, [rax+10h]
0x180303c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180303c14  mov     eax, ebx
0x180303c16  mov     pNativePasswordBox, [rbp+57h+var_48]
0x180303c1a  xor     pNativePasswordBox, rsp; StackCookie
0x180303c1d  call    __security_check_cookie
0x180303c22  add     rsp, 0E8h
0x180303c29  pop     r15
0x180303c2b  pop     r14
0x180303c2d  pop     r13
0x180303c2f  pop     r12
0x180303c31  pop     rdi
0x180303c32  pop     rsi
0x180303c33  pop     rbx
0x180303c34  pop     rbp
0x180303c35  retn
0x180303c36  add     rdx, 0B8h
0x180303c3d  lea     pNativePasswordBox, [rsi+2C8h]
0x180303c44  lea     r8, [rbp+57h+string]
0x180303c48  call    ?AttachEventHandler@?$EventPtr@V?$event_handler@UIPointerEventHandler@Input@Xaml@UI@Windows@@UIInspectable@@UIPointerRoutedEventArgs@2345@UUIElementPointerReleasedTraits@DirectUI@@@ctl@@@ctl@@QEAAJPEAUIUIElement@Xaml@UI@Windows@@V?$function@$$A6AJPEAUIInspectable@@PEAUIPointerRoutedEventArgs@Input@Xaml@UI@Windows@@@Z@std@@@Z; ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs,DirectUI::UIElementPointerReleasedTraits>>::AttachEventHandler(Windows::UI::Xaml::IUIElement *,std::function<long (IInspectable *,Windows::UI::Xaml::Input::IPointerRoutedEventArgs *)>)
0x180303c4d  lea     pNativePasswordBox, [rbp+57h+spPropertyValueFactory]; this
0x180303c51  mov     ebx, eax
0x180303c53  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180303c58  test    ebx, ebx
0x180303c5a  js      loc_1803040C9
0x180303c60  test    r14, r14
0x180303c63  jz      short loc_180303C74
0x180303c65  mov     rax, [r14]
0x180303c68  mov     pNativePasswordBox, r14
0x180303c6b  mov     rax, [rax+10h]
0x180303c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180303c74  test    r15, r15
0x180303c77  jz      short loc_180303C88
0x180303c79  mov     rax, [r15]
0x180303c7c  mov     pNativePasswordBox, r15
0x180303c7f  mov     rax, [rax+10h]
0x180303c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180303c88  mov     pNativePasswordBox, rsi; this
0x180303c8b  call    ?UpdateHeaderPresenterVisibility@PasswordBox@DirectUI@@AEAAJXZ; DirectUI::PasswordBox::UpdateHeaderPresenterVisibility(void)
0x180303c90  mov     ebx, eax
0x180303c92  test    eax, eax
0x180303c94  js      loc_18030429F
0x180303c9a  lea     pNativePasswordBox, [rsi+218h]
0x180303ca1  mov     rax, [pNativePasswordBox]
0x180303ca4  lea     rdx, [rbp+57h+pPasswordBoxText]
0x180303ca8  mov     rax, [rax+30h]
0x180303cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180303cb1  mov     ebx, eax
0x180303cb3  test    eax, eax
0x180303cb5  js      loc_180304293
0x180303cbb  xor     edx, edx
0x180303cbd  mov     pNativePasswordBox, rsi; this
0x180303cc0  cmp     [rbp+57h+pPasswordBoxText], rdx
0x180303cc4  setz    dl; isEnabled
0x180303cc7  call    ?UpdatePlaceholderTextPresenterVisibility@PasswordBox@DirectUI@@AEAAJI@Z; DirectUI::PasswordBox::UpdatePlaceholderTextPresenterVisibility(uint)
0x180303ccc  mov     ebx, eax
0x180303cce  test    eax, eax
0x180303cd0  jns     $Cleanup_2037
0x180303cd6  mov     ecx, eax; failedFrameHR
0x180303cd8  call    OnFailure_2990_
0x180303cdd  jmp     $Cleanup_2037
0x180303ce2  xor     r8d, r8d; bForceLoopback
0x180303ce5  mov     dl, 1; bEnsureTrackerTarget
0x180303ce7  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x180303cec  jmp     loc_180303B15
0x180303cf1  lea     rdx, [rsp+120h+wrWeakThis]
0x180303cf6  lea     pNativePasswordBox, [rbp+57h+spPropertyValueFactory]; <wrThis>
0x180303cfa  call    _lambda_f1802912b035dcb592eb4204d4dbbee4____lambda_f1802912b035dcb592eb4204d4dbbee4_
0x180303cff  mov     rdx, rax
0x180303d02  lea     pNativePasswordBox, [rbp+57h+string]; _Func
0x180303d06  call    std__function_long___cdecl_IInspectable___Windows__UI__Xaml__ISizeChangedEventArgs______function_long___cdecl_IInspectable___Windows__UI__Xaml__ISizeChangedEventArgs______lambda_92dabb9d7f125d744a2349985f1e17b4__0_
0x180303d0b  mov     pNativePasswordBox, [rbp+57h+spButton.ptr_]
0x180303d0f  lea     rdx, [pNativePasswordBox-238h]
0x180303d16  neg     pNativePasswordBox
0x180303d19  sbb     r8, r8
0x180303d1c  and     r8, rdx
0x180303d1f  lea     rdx, [r8+160h]
0x180303d26  jnz     short loc_180303D2B
0x180303d28  mov     rdx, r12
0x180303d2b  lea     pNativePasswordBox, [rsi+2B0h]
0x180303d32  mov     r8, rax
0x180303d35  call    ?AttachEventHandler@?$EventPtr@V?$event_handler@UISizeChangedEventHandler@Xaml@UI@Windows@@UIInspectable@@UISizeChangedEventArgs@234@UFrameworkElementSizeChangedTraits@DirectUI@@@ctl@@@ctl@@QEAAJPEAUIFrameworkElement@Xaml@UI@Windows@@V?$function@$$A6AJPEAUIInspectable@@PEAUISizeChangedEventArgs@Xaml@UI@Windows@@@Z@std@@@Z; ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::ISizeChangedEventHandler,IInspectable,Windows::UI::Xaml::ISizeChangedEventArgs,DirectUI::FrameworkElementSizeChangedTraits>>::AttachEventHandler(Windows::UI::Xaml::IFrameworkElement *,std::function<long (IInspectable *,Windows::UI::Xaml::ISizeChangedEventArgs *)>)
0x180303d3a  lea     pNativePasswordBox, [rbp+57h+spPropertyValueFactory]; this
0x180303d3e  mov     ebx, eax
0x180303d40  call    ??1?$ComPtr@U?$IReference@UVector2@Numerics@Foundation@Windows@@@Foundation@Windows@@@ctl@@QEAA@XZ; ctl::ComPtr<Windows::Foundation::IReference<Windows::Foundation::Numerics::Vector2>>::~ComPtr<Windows::Foundation::IReference<Windows::Foundation::Numerics::Vector2>>(void)
0x180303d45  test    ebx, ebx
0x180303d47  js      loc_180304041
0x180303d4d  lea     pNativePasswordBox, [rbp+57h+spPropertyValueFactory]; this
0x180303d51  mov     [rbp+57h+spPropertyValueFactory.ptr_], r15
0x180303d55  call    ?InternalAddRef@?$ComPtr@UICastingEventHandler@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ICastingEventHandler>::InternalAddRef(void)
  ... truncated ...
```
