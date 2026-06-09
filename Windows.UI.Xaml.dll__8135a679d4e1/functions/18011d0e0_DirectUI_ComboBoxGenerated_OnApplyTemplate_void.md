# DirectUI::ComboBoxGenerated::OnApplyTemplate(void)

- ea: `0x18011d0e0`
- end: `0x18011d7b9`
- name: `?OnApplyTemplate@ComboBoxGenerated@DirectUI@@UEAAJXZ`
- size: `1753`
- prototype: `HRESULT __fastcall(DirectUI::ComboBoxGenerated *this)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18011c930`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x18005b234`
- `0x1800f2084`
- `0x1800f4510`
- `0x18011d0e0`
- `0x18011f3c0`
- `0x1801dfeb0`
- `0x1803024a0`
- `0x180303850`
- `0x1806567c4`
- `0x1806f112c`
- `0x1806fb364`
- `0x18076e110`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18011d189`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18011d1e6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18011d243`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18011d2a4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18011d2ff`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18011d35c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18011d3b9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18011d416`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18011d473`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18011d189`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18011d1e6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18011d243`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18011d2a4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18011d2ff`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18011d35c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18011d3b9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18011d416`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18011d473`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011d168`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011d1d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011d22d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011d28e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011d2e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011d346`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011d3a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011d400`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011d45d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011d168`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011d1d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011d22d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011d28e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011d2e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011d346`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011d3a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011d400`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18011d45d`

## pseudocode

```c
__int64 __fastcall DirectUI::ComboBoxGenerated::OnApplyTemplate(DirectUI::ComboBoxGenerated *this)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject> *v4; // rdi
  unsigned int (__fastcall *AddRef)(IUnknown *); // rbx
  HRESULT v6; // eax
  unsigned int (__fastcall *v7)(IUnknown *); // rbx
  HRESULT v8; // eax
  unsigned int (__fastcall *v9)(IUnknown *); // rbx
  HRESULT v10; // eax
  unsigned int (__fastcall *v11)(IUnknown *); // rbx
  HRESULT v12; // eax
  unsigned int (__fastcall *v13)(IUnknown *); // rbx
  HRESULT v14; // eax
  unsigned int (__fastcall *v15)(IUnknown *); // rbx
  HRESULT v16; // eax
  unsigned int (__fastcall *v17)(IUnknown *); // rbx
  HRESULT v18; // eax
  unsigned int (__fastcall *v19)(IUnknown *); // rbx
  HRESULT v20; // eax
  unsigned int (__fastcall *v21)(IUnknown *); // rbx
  HRESULT v22; // eax
  Windows::UI::Xaml::IDependencyObject *ptr; // rdi
  IUnknown *v24; // rdi
  Windows::UI::Xaml::IDependencyObject *v25; // rdi
  IUnknown *v26; // rdi
  Windows::UI::Xaml::IDependencyObject *v27; // rdi
  int v28; // eax
  Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *> *v29; // rdi
  Windows::UI::Xaml::IDependencyObject *v30; // rcx
  Windows::UI::Xaml::IDependencyObject *v31; // rcx
  Windows::UI::Xaml::IDependencyObject *v32; // rcx
  Windows::UI::Xaml::IDependencyObject *v33; // rcx
  Windows::UI::Xaml::IDependencyObject *v34; // rcx
  Windows::UI::Xaml::IDependencyObject *v35; // rcx
  Windows::UI::Xaml::IDependencyObject *v36; // rcx
  Windows::UI::Xaml::IDependencyObject *v37; // rcx
  Windows::UI::Xaml::IDependencyObject *v38; // rcx
  IUnknown *pValue; // [rsp+20h] [rbp-69h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> pPopupPart; // [rsp+28h] [rbp-61h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> pItemsPresenterTranslateTransformPart; // [rsp+30h] [rbp-59h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> pItemsPresenterPart; // [rsp+38h] [rbp-51h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> pItemsPresenterHostPart; // [rsp+40h] [rbp-49h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> pFlyoutButtonPart; // [rsp+48h] [rbp-41h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> pEditableTextPart; // [rsp+50h] [rbp-39h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> pDropDownOverlayPart; // [rsp+58h] [rbp-31h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> pContentPresenterPart; // [rsp+60h] [rbp-29h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> pBackgroundPart; // [rsp+68h] [rbp-21h] BYREF
  HSTRING string; // [rsp+70h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-11h] BYREF

  pBackgroundPart.ptr_ = 0;
  pContentPresenterPart.ptr_ = 0;
  pDropDownOverlayPart.ptr_ = 0;
  pEditableTextPart.ptr_ = 0;
  pFlyoutButtonPart.ptr_ = 0;
  pItemsPresenterHostPart.ptr_ = 0;
  pItemsPresenterPart.ptr_ = 0;
  pItemsPresenterTranslateTransformPart.ptr_ = 0;
  pPopupPart.ptr_ = 0;
  v2 = DirectUI::Selector::OnApplyTemplate(this);
  v3 = v2;
  if ( v2 < 0 )
  {
    OnFailure_2990_(v2);
  }
  else
  {
    v4 = &this->ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject>;
    AddRef = this->DirectUI::Selector::DirectUI::SelectorGenerated::DirectUI::ItemsControl::DirectUI::ItemsControlGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::DirectUI::DependencyObject::ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject>::m_forwarder.DirectUI::Selector::DirectUI::SelectorGenerated::DirectUI::ItemsControl::DirectUI::ItemsControlGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::DirectUI::DependencyObject::ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject>::__vftable[1].AddRef;
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&pBackgroundPart);
    if ( WindowsCreateStringReference(L"Background", 0xAu, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v6 = ((__int64 (__fastcall *)(ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject> *, HSTRING, ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> *))AddRef)(
           &this->ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject>,
           string,
           &pBackgroundPart);
    v3 = v6;
    if ( v6 < 0 )
    {
      OnFailure_2990_(v6);
    }
    else
    {
      v7 = v4->m_forwarder.__vftable[1].AddRef;
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&pContentPresenterPart);
      if ( WindowsCreateStringReference(L"ContentPresenter", 0x10u, &hstringHeader, &string) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v8 = ((__int64 (__fastcall *)(ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject> *, HSTRING, ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> *))v7)(
             &this->ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject>,
             string,
             &pContentPresenterPart);
      v3 = v8;
      if ( v8 < 0 )
      {
        OnFailure_2990_(v8);
      }
      else
      {
        v9 = v4->m_forwarder.__vftable[1].AddRef;
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&pDropDownOverlayPart);
        if ( WindowsCreateStringReference(L"DropDownOverlay", 0xFu, &hstringHeader, &string) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v10 = ((__int64 (__fastcall *)(ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject> *, HSTRING, ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> *))v9)(
                &this->ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject>,
                string,
                &pDropDownOverlayPart);
        v3 = v10;
        if ( v10 < 0 )
        {
          OnFailure_2990_(v10);
        }
        else
        {
          v11 = v4->m_forwarder.__vftable[1].AddRef;
          ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&pEditableTextPart);
          if ( WindowsCreateStringReference(L"EditableText", 0xCu, &hstringHeader, &string) < 0 )
            RaiseException(0xC000000D, 1u, 0, 0);
          v12 = ((__int64 (__fastcall *)(ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject> *, HSTRING, ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> *))v11)(
                  &this->ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject>,
                  string,
                  &pEditableTextPart);
          v3 = v12;
          if ( v12 < 0 )
          {
            OnFailure_2990_(v12);
          }
          else
          {
            v13 = v4->m_forwarder.__vftable[1].AddRef;
            ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&pFlyoutButtonPart);
            if ( WindowsCreateStringReference(L"FlyoutButton", 0xCu, &hstringHeader, &string) < 0 )
              RaiseException(0xC000000D, 1u, 0, 0);
            v14 = ((__int64 (__fastcall *)(ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject> *, HSTRING, ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> *))v13)(
                    &this->ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject>,
                    string,
                    &pFlyoutButtonPart);
            v3 = v14;
            if ( v14 < 0 )
            {
              OnFailure_2990_(v14);
            }
            else
            {
              v15 = v4->m_forwarder.__vftable[1].AddRef;
              ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&pItemsPresenterHostPart);
              if ( WindowsCreateStringReference(L"ItemsPresenterHost", 0x12u, &hstringHeader, &string) < 0 )
                RaiseException(0xC000000D, 1u, 0, 0);
              v16 = ((__int64 (__fastcall *)(ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject> *, HSTRING, ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> *))v15)(
                      &this->ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject>,
                      string,
                      &pItemsPresenterHostPart);
              v3 = v16;
              if ( v16 < 0 )
              {
                OnFailure_2990_(v16);
              }
              else
              {
                v17 = v4->m_forwarder.__vftable[1].AddRef;
                ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&pItemsPresenterPart);
                if ( WindowsCreateStringReference(L"ItemsPresenter", 0xEu, &hstringHeader, &string) < 0 )
                  RaiseException(0xC000000D, 1u, 0, 0);
                v18 = ((__int64 (__fastcall *)(ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject> *, HSTRING, ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> *))v17)(
                        &this->ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject>,
                        string,
                        &pItemsPresenterPart);
                v3 = v18;
                if ( v18 < 0 )
                {
                  OnFailure_2990_(v18);
                }
                else
                {
                  v19 = v4->m_forwarder.__vftable[1].AddRef;
                  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&pItemsPresenterTranslateTransformPart);
                  if ( WindowsCreateStringReference(L"ItemsPresenterTranslateTransform", 0x20u, &hstringHeader, &string) < 0 )
                    RaiseException(0xC000000D, 1u, 0, 0);
                  v20 = ((__int64 (__fastcall *)(ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject> *, HSTRING, ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> *))v19)(
                          &this->ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject>,
                          string,
                          &pItemsPresenterTranslateTransformPart);
                  v3 = v20;
                  if ( v20 < 0 )
                  {
                    OnFailure_2990_(v20);
                  }
                  else
                  {
                    v21 = v4->m_forwarder.__vftable[1].AddRef;
                    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&pPopupPart);
                    if ( WindowsCreateStringReference(L"Popup", 5u, &hstringHeader, &string) < 0 )
                      RaiseException(0xC000000D, 1u, 0, 0);
                    v22 = ((__int64 (__fastcall *)(ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject> *, HSTRING, ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> *))v21)(
                            &this->ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject>,
                            string,
                            &pPopupPart);
                    v3 = v22;
                    if ( v22 < 0 )
                    {
                      OnFailure_2990_(v22);
                    }
                    else
                    {
                      ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::IBorder,Windows::UI::Xaml::IDependencyObject>(
                        (ctl::WeakReferenceSourceNoThreadId *)((char *)&this[-1].m_tpMonitoredCV.m_trackerReference + 16),
                        (DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::IBorder,1,0> *)&this->m_selectedIndexValueSetBeforeItemsAvailable,
                        pBackgroundPart.ptr_);
                      ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::IContentPresenter,Windows::UI::Xaml::Controls::IContentPresenter>(
                        (ctl::WeakReferenceSourceNoThreadId *)((char *)&this[-1].m_tpMonitoredCV.m_trackerReference + 16),
                        (DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::IContentPresenter,1,0> *)((char *)&this->m_tpDataSourceAsSelectionInfo.m_trackerReference + 16),
                        pContentPresenterPart.ptr_);
                      ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::IBorder,Windows::UI::Xaml::IDependencyObject>(
                        (ctl::WeakReferenceSourceNoThreadId *)((char *)&this[-1].m_tpMonitoredCV.m_trackerReference + 16),
                        (DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::IBorder,1,0> *)&this->m_selection.m_selectionChanger.m_pOwnerNoRef,
                        pDropDownOverlayPart.ptr_);
                      ptr = pEditableTextPart.ptr_;
                      ctl::WeakReferenceSourceNoThreadId::RegisterPtr(
                        (ctl::WeakReferenceSourceNoThreadId *)((char *)&this[-1].m_tpMonitoredCV.m_trackerReference + 16),
                        (DirectUI::TrackerTargetReference *const)&this->m_selection.m_selectionChanger.m_bIsActive);
                      pValue = 0;
                      if ( ptr
                        && ptr->QueryInterface(ptr, &GUID_e48f5a8b_1dff_4352_a1f4_e516514ec882, (void **)&pValue) >= 0
                        && (v24 = pValue) != 0 )
                      {
                        DirectUI::TrackerTargetReference::Set(
                          (DirectUI::TrackerTargetReference *)&this->m_selection.m_selectionChanger.m_bIsActive,
                          pValue,
                          1u,
                          0);
                        v24->Release(v24);
                      }
                      else
                      {
                        DirectUI::TrackerTargetReference::Clear(
                          (DirectUI::TrackerTargetReference *)&this->m_selection.m_selectionChanger.m_bIsActive,
                          1u,
                          0);
                      }
                      ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::Primitives::IButtonBase,Windows::UI::Xaml::IDependencyObject>(
                        (ctl::WeakReferenceSourceNoThreadId *)((char *)&this[-1].m_tpMonitoredCV.m_trackerReference + 16),
                        (DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::Primitives::IButtonBase,1,0> *)&this->m_selection.m_spSelectedItems,
                        pFlyoutButtonPart.ptr_);
                      ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::ICanvas,Windows::UI::Xaml::IDependencyObject>(
                        (ctl::WeakReferenceSourceNoThreadId *)((char *)&this[-1].m_tpMonitoredCV.m_trackerReference + 16),
                        (DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::ICanvas,1,0> *)&this->m_tpSelectedItemsImpl,
                        pItemsPresenterHostPart.ptr_);
                      ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::IItemsPresenter,Windows::UI::Xaml::IDependencyObject>(
                        (ctl::WeakReferenceSourceNoThreadId *)((char *)&this[-1].m_tpMonitoredCV.m_trackerReference + 16),
                        (DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::IItemsPresenter,1,0> *)&this->m_SelectedItemsVectorChangedToken,
                        pItemsPresenterPart.ptr_);
                      v25 = pItemsPresenterTranslateTransformPart.ptr_;
                      ctl::WeakReferenceSourceNoThreadId::RegisterPtr(
                        (ctl::WeakReferenceSourceNoThreadId *)((char *)&this[-1].m_tpMonitoredCV.m_trackerReference + 16),
                        (DirectUI::TrackerTargetReference *const)&this->m_tpSelectedRangesImpl.m_trackerReference.8);
                      pValue = 0;
                      if ( v25
                        && v25->QueryInterface(v25, &GUID_c975905c_3c36_4229_817b_178f64c0e113, (void **)&pValue) >= 0
                        && (v26 = pValue) != 0 )
                      {
                        DirectUI::TrackerTargetReference::Set(
                          (DirectUI::TrackerTargetReference *)&this->m_tpSelectedRangesImpl.m_trackerReference.8,
                          pValue,
                          1u,
                          0);
                        v26->Release(v26);
                      }
                      else
                      {
                        DirectUI::TrackerTargetReference::Clear(
                          (DirectUI::TrackerTargetReference *)&this->m_tpSelectedRangesImpl.m_trackerReference.8,
                          1u,
                          0);
                      }
                      v27 = pPopupPart.ptr_;
                      ctl::WeakReferenceSourceNoThreadId::RegisterPtr(
                        (ctl::WeakReferenceSourceNoThreadId *)((char *)&this[-1].m_tpMonitoredCV.m_trackerReference + 16),
                        (DirectUI::TrackerTargetReference *const)&this->m_tpScrollViewer.m_trackerReference.8);
                      pValue = 0;
                      if ( !v27
                        || (v28 = v27->QueryInterface(v27, &GUID_62418240_e6d3_4705_a1dc_39156456ee29, (void **)&pValue),
                            v29 = (Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *> *)pValue,
                            v28 < 0) )
                      {
                        v29 = 0;
                      }
                      DirectUI::TrackerPtr<Windows::UI::Xaml::Interop::IBindableVector,1,0>::Set<Windows::UI::Xaml::Interop::IBindableVector>(
                        (DirectUI::TrackerPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,1,0> *)&this->m_tpScrollViewer.m_trackerReference.8,
                        v29);
                      if ( v29 )
                        v29->Release(v29);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  v30 = pPopupPart.ptr_;
  if ( pPopupPart.ptr_ )
  {
    pPopupPart.ptr_ = 0;
    v30->Release(v30);
  }
  v31 = pItemsPresenterTranslateTransformPart.ptr_;
  if ( pItemsPresenterTranslateTransformPart.ptr_ )
  {
    pItemsPresenterTranslateTransformPart.ptr_ = 0;
    v31->Release(v31);
  }
  v32 = pItemsPresenterPart.ptr_;
  if ( pItemsPresenterPart.ptr_ )
  {
    pItemsPresenterPart.ptr_ = 0;
    v32->Release(v32);
  }
  v33 = pItemsPresenterHostPart.ptr_;
  if ( pItemsPresenterHostPart.ptr_ )
  {
    pItemsPresenterHostPart.ptr_ = 0;
    v33->Release(v33);
  }
  v34 = pFlyoutButtonPart.ptr_;
  if ( pFlyoutButtonPart.ptr_ )
  {
    pFlyoutButtonPart.ptr_ = 0;
    v34->Release(v34);
  }
  v35 = pEditableTextPart.ptr_;
  if ( pEditableTextPart.ptr_ )
  {
    pEditableTextPart.ptr_ = 0;
    v35->Release(v35);
  }
  v36 = pDropDownOverlayPart.ptr_;
  if ( pDropDownOverlayPart.ptr_ )
  {
    pDropDownOverlayPart.ptr_ = 0;
    v36->Release(v36);
  }
  v37 = pContentPresenterPart.ptr_;
  if ( pContentPresenterPart.ptr_ )
  {
    pContentPresenterPart.ptr_ = 0;
    v37->Release(v37);
  }
  v38 = pBackgroundPart.ptr_;
  if ( pBackgroundPart.ptr_ )
  {
    pBackgroundPart.ptr_ = 0;
    v38->Release(v38);
  }
  return v3;
}

```

## disassembly

```asm
0x18011d0e0  push    rbp
0x18011d0e2  push    rbx
0x18011d0e3  push    rsi
0x18011d0e4  push    rdi
0x18011d0e5  push    r12
0x18011d0e7  push    r13
0x18011d0e9  push    r14
0x18011d0eb  push    r15
0x18011d0ed  lea     rbp, [rsp-1Fh]
0x18011d0f2  sub     rsp, 0A8h
0x18011d0f9  mov     rax, cs:__security_cookie
0x18011d100  xor     rax, rsp
0x18011d103  mov     [rbp+57h+var_50], rax
0x18011d107  xor     r12d, r12d
0x18011d10a  mov     rsi, this
0x18011d10d  mov     [rbp+57h+pBackgroundPart.ptr_], r12
0x18011d111  mov     [rbp+57h+pContentPresenterPart.ptr_], r12
0x18011d115  mov     [rbp+57h+pDropDownOverlayPart.ptr_], r12
0x18011d119  mov     [rbp+57h+pEditableTextPart.ptr_], r12
0x18011d11d  mov     [rbp+57h+pFlyoutButtonPart.ptr_], r12
0x18011d121  mov     [rbp+57h+pItemsPresenterHostPart.ptr_], r12
0x18011d125  mov     [rbp+57h+pItemsPresenterPart.ptr_], r12
0x18011d129  mov     [rbp+57h+pItemsPresenterTranslateTransformPart.ptr_], r12
0x18011d12d  mov     [rbp+57h+pPopupPart.ptr_], r12
0x18011d131  call    ?OnApplyTemplate@Selector@DirectUI@@UEAAJXZ; DirectUI::Selector::OnApplyTemplate(void)
0x18011d136  mov     ebx, eax
0x18011d138  test    eax, eax
0x18011d13a  js      loc_18011D6AF
0x18011d140  lea     rdi, [rsi+60h]
0x18011d144  mov     rax, [rdi]
0x18011d147  lea     this, [rbp+57h+pBackgroundPart]; this
0x18011d14b  mov     rbx, [rax+40h]
0x18011d14f  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18011d154  lea     r9, [rbp+57h+string]; string
0x18011d158  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18011d15c  lea     edx, [r12+0Ah]; length
0x18011d161  lea     this, aBackground; "Background"
0x18011d168  call    cs:__imp_WindowsCreateStringReference
0x18011d16e  lea     r13d, [r12+1]
0x18011d173  mov     r14d, 0C000000Dh
0x18011d179  test    eax, eax
0x18011d17b  jns     short loc_18011D18F
0x18011d17d  xor     r9d, r9d; lpArguments
0x18011d180  xor     r8d, r8d; nNumberOfArguments
0x18011d183  mov     edx, r13d; dwExceptionFlags
0x18011d186  mov     ecx, r14d; dwExceptionCode
0x18011d189  call    cs:__imp_RaiseException
0x18011d18f  mov     rdx, [rbp+57h+string]
0x18011d193  lea     r8, [rbp+57h+pBackgroundPart]
0x18011d197  mov     this, rdi
0x18011d19a  mov     rax, rbx
0x18011d19d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011d1a2  mov     ebx, eax
0x18011d1a4  test    eax, eax
0x18011d1a6  js      loc_18011D6A6
0x18011d1ac  mov     rax, [rdi]
0x18011d1af  lea     this, [rbp+57h+pContentPresenterPart]; this
0x18011d1b3  mov     rbx, [rax+40h]
0x18011d1b7  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18011d1bc  lea     r9, [rbp+57h+string]; string
0x18011d1c0  mov     edx, 10h; length
0x18011d1c5  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18011d1c9  lea     this, aContentpresent; "ContentPresenter"
0x18011d1d0  call    cs:__imp_WindowsCreateStringReference
0x18011d1d6  test    eax, eax
0x18011d1d8  jns     short loc_18011D1EC
0x18011d1da  xor     r9d, r9d; lpArguments
0x18011d1dd  xor     r8d, r8d; nNumberOfArguments
0x18011d1e0  mov     edx, r13d; dwExceptionFlags
0x18011d1e3  mov     ecx, r14d; dwExceptionCode
0x18011d1e6  call    cs:__imp_RaiseException
0x18011d1ec  mov     rdx, [rbp+57h+string]
0x18011d1f0  lea     r8, [rbp+57h+pContentPresenterPart]
0x18011d1f4  mov     this, rdi
0x18011d1f7  mov     rax, rbx
0x18011d1fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011d1ff  mov     ebx, eax
0x18011d201  test    eax, eax
0x18011d203  js      loc_18011D69D
0x18011d209  mov     rax, [rdi]
0x18011d20c  lea     this, [rbp+57h+pDropDownOverlayPart]; this
0x18011d210  mov     rbx, [rax+40h]
0x18011d214  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18011d219  lea     r9, [rbp+57h+string]; string
0x18011d21d  mov     edx, 0Fh; length
0x18011d222  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18011d226  lea     this, aDropdownoverla; "DropDownOverlay"
0x18011d22d  call    cs:__imp_WindowsCreateStringReference
0x18011d233  test    eax, eax
0x18011d235  jns     short loc_18011D249
0x18011d237  xor     r9d, r9d; lpArguments
0x18011d23a  xor     r8d, r8d; nNumberOfArguments
0x18011d23d  mov     edx, r13d; dwExceptionFlags
0x18011d240  mov     ecx, r14d; dwExceptionCode
0x18011d243  call    cs:__imp_RaiseException
0x18011d249  mov     rdx, [rbp+57h+string]
0x18011d24d  lea     r8, [rbp+57h+pDropDownOverlayPart]
0x18011d251  mov     this, rdi
0x18011d254  mov     rax, rbx
0x18011d257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011d25c  mov     ebx, eax
0x18011d25e  test    eax, eax
0x18011d260  js      loc_18011D694
0x18011d266  mov     rax, [rdi]
0x18011d269  lea     this, [rbp+57h+pEditableTextPart]; this
0x18011d26d  mov     rbx, [rax+40h]
0x18011d271  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18011d276  mov     r15d, 0Ch
0x18011d27c  lea     r9, [rbp+57h+string]; string
0x18011d280  mov     edx, r15d; length
0x18011d283  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18011d287  lea     this, aEditabletext; "EditableText"
0x18011d28e  call    cs:__imp_WindowsCreateStringReference
0x18011d294  test    eax, eax
0x18011d296  jns     short loc_18011D2AA
0x18011d298  xor     r9d, r9d; lpArguments
0x18011d29b  xor     r8d, r8d; nNumberOfArguments
0x18011d29e  mov     edx, r13d; dwExceptionFlags
0x18011d2a1  mov     ecx, r14d; dwExceptionCode
0x18011d2a4  call    cs:__imp_RaiseException
0x18011d2aa  mov     rdx, [rbp+57h+string]
0x18011d2ae  lea     r8, [rbp+57h+pEditableTextPart]
0x18011d2b2  mov     this, rdi
0x18011d2b5  mov     rax, rbx
0x18011d2b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011d2bd  mov     ebx, eax
0x18011d2bf  test    eax, eax
0x18011d2c1  js      loc_18011D68B
0x18011d2c7  mov     rax, [rdi]
0x18011d2ca  lea     this, [rbp+57h+pFlyoutButtonPart]; this
0x18011d2ce  mov     rbx, [rax+40h]
0x18011d2d2  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18011d2d7  lea     r9, [rbp+57h+string]; string
0x18011d2db  mov     edx, r15d; length
0x18011d2de  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18011d2e2  lea     this, aFlyoutbutton; "FlyoutButton"
0x18011d2e9  call    cs:__imp_WindowsCreateStringReference
0x18011d2ef  test    eax, eax
0x18011d2f1  jns     short loc_18011D305
0x18011d2f3  xor     r9d, r9d; lpArguments
0x18011d2f6  xor     r8d, r8d; nNumberOfArguments
0x18011d2f9  mov     edx, r13d; dwExceptionFlags
0x18011d2fc  mov     ecx, r14d; dwExceptionCode
0x18011d2ff  call    cs:__imp_RaiseException
0x18011d305  mov     rdx, [rbp+57h+string]
0x18011d309  lea     r8, [rbp+57h+pFlyoutButtonPart]
0x18011d30d  mov     this, rdi
0x18011d310  mov     rax, rbx
0x18011d313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011d318  mov     ebx, eax
0x18011d31a  test    eax, eax
0x18011d31c  js      loc_18011D682
0x18011d322  mov     rax, [rdi]
0x18011d325  lea     this, [rbp+57h+pItemsPresenterHostPart]; this
0x18011d329  mov     rbx, [rax+40h]
0x18011d32d  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18011d332  lea     r9, [rbp+57h+string]; string
0x18011d336  mov     edx, 12h; length
0x18011d33b  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18011d33f  lea     this, aItemspresenter; "ItemsPresenterHost"
0x18011d346  call    cs:__imp_WindowsCreateStringReference
0x18011d34c  test    eax, eax
0x18011d34e  jns     short loc_18011D362
0x18011d350  xor     r9d, r9d; lpArguments
0x18011d353  xor     r8d, r8d; nNumberOfArguments
0x18011d356  mov     edx, r13d; dwExceptionFlags
0x18011d359  mov     ecx, r14d; dwExceptionCode
0x18011d35c  call    cs:__imp_RaiseException
0x18011d362  mov     rdx, [rbp+57h+string]
0x18011d366  lea     r8, [rbp+57h+pItemsPresenterHostPart]
0x18011d36a  mov     this, rdi
0x18011d36d  mov     rax, rbx
0x18011d370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011d375  mov     ebx, eax
0x18011d377  test    eax, eax
0x18011d379  js      loc_18011D679
0x18011d37f  mov     rax, [rdi]
0x18011d382  lea     this, [rbp+57h+pItemsPresenterPart]; this
0x18011d386  mov     rbx, [rax+40h]
0x18011d38a  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18011d38f  lea     r9, [rbp+57h+string]; string
0x18011d393  mov     edx, 0Eh; length
0x18011d398  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18011d39c  lea     this, aItemspresenter_1; "ItemsPresenter"
0x18011d3a3  call    cs:__imp_WindowsCreateStringReference
0x18011d3a9  test    eax, eax
0x18011d3ab  jns     short loc_18011D3BF
0x18011d3ad  xor     r9d, r9d; lpArguments
0x18011d3b0  xor     r8d, r8d; nNumberOfArguments
0x18011d3b3  mov     edx, r13d; dwExceptionFlags
0x18011d3b6  mov     ecx, r14d; dwExceptionCode
0x18011d3b9  call    cs:__imp_RaiseException
0x18011d3bf  mov     rdx, [rbp+57h+string]
0x18011d3c3  lea     r8, [rbp+57h+pItemsPresenterPart]
0x18011d3c7  mov     this, rdi
0x18011d3ca  mov     rax, rbx
0x18011d3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011d3d2  mov     ebx, eax
0x18011d3d4  test    eax, eax
0x18011d3d6  js      loc_18011D670
0x18011d3dc  mov     rax, [rdi]
0x18011d3df  lea     this, [rbp+57h+pItemsPresenterTranslateTransformPart]; this
0x18011d3e3  mov     rbx, [rax+40h]
0x18011d3e7  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18011d3ec  lea     r9, [rbp+57h+string]; string
0x18011d3f0  mov     edx, 20h ; ' '; length
0x18011d3f5  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18011d3f9  lea     this, aItemspresenter_0; "ItemsPresenterTranslateTransform"
0x18011d400  call    cs:__imp_WindowsCreateStringReference
0x18011d406  test    eax, eax
0x18011d408  jns     short loc_18011D41C
0x18011d40a  xor     r9d, r9d; lpArguments
0x18011d40d  xor     r8d, r8d; nNumberOfArguments
0x18011d410  mov     edx, r13d; dwExceptionFlags
0x18011d413  mov     ecx, r14d; dwExceptionCode
0x18011d416  call    cs:__imp_RaiseException
0x18011d41c  mov     rdx, [rbp+57h+string]
0x18011d420  lea     r8, [rbp+57h+pItemsPresenterTranslateTransformPart]
0x18011d424  mov     this, rdi
0x18011d427  mov     rax, rbx
0x18011d42a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011d42f  mov     ebx, eax
0x18011d431  test    eax, eax
0x18011d433  js      loc_18011D667
0x18011d439  mov     rax, [rdi]
0x18011d43c  lea     this, [rbp+57h+pPopupPart]; this
0x18011d440  mov     rbx, [rax+40h]
0x18011d444  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18011d449  lea     r9, [rbp+57h+string]; string
0x18011d44d  mov     edx, 5; length
0x18011d452  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18011d456  lea     this, aPopup; "Popup"
0x18011d45d  call    cs:__imp_WindowsCreateStringReference
0x18011d463  test    eax, eax
0x18011d465  jns     short loc_18011D479
0x18011d467  xor     r9d, r9d; lpArguments
0x18011d46a  xor     r8d, r8d; nNumberOfArguments
0x18011d46d  mov     edx, r13d; dwExceptionFlags
0x18011d470  mov     ecx, r14d; dwExceptionCode
0x18011d473  call    cs:__imp_RaiseException
0x18011d479  mov     rdx, [rbp+57h+string]
0x18011d47d  lea     r8, [rbp+57h+pPopupPart]
0x18011d481  mov     this, rdi
0x18011d484  mov     rax, rbx
0x18011d487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011d48c  mov     ebx, eax
0x18011d48e  test    eax, eax
0x18011d490  js      loc_18011D65E
0x18011d496  mov     r8, [rbp+57h+pBackgroundPart.ptr_]; value
0x18011d49a  lea     r14, [rsi-160h]
0x18011d4a1  mov     this, r14; this
0x18011d4a4  lea     rdx, [rsi+3C8h]; ptr
0x18011d4ab  call    ??$SetPtrValueWithQIOrNull@UIBorder@Controls@Xaml@UI@Windows@@UIDependencyObject@345@@WeakReferenceSourceNoThreadId@ctl@@IEAAXAEAV?$TrackerPtr@UIBorder@Controls@Xaml@UI@Windows@@$00$0A@@DirectUI@@PEAUIDependencyObject@Xaml@UI@Windows@@@Z; ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::IBorder,Windows::UI::Xaml::IDependencyObject>(DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::IBorder,1,0> &,Windows::UI::Xaml::IDependencyObject *)
0x18011d4b0  mov     r8, [rbp+57h+pContentPresenterPart.ptr_]; value
0x18011d4b4  lea     rdx, [rsi+3E0h]; ptr
0x18011d4bb  mov     this, r14; this
0x18011d4be  call    ??$SetPtrValueWithQIOrNull@UIContentPresenter@Controls@Xaml@UI@Windows@@U12345@@WeakReferenceSourceNoThreadId@ctl@@IEAAXAEAV?$TrackerPtr@UIContentPresenter@Controls@Xaml@UI@Windows@@$00$0A@@DirectUI@@PEAUIContentPresenter@Controls@Xaml@UI@Windows@@@Z; ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::IContentPresenter,Windows::UI::Xaml::Controls::IContentPresenter>(DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::IContentPresenter,1,0> &,Windows::UI::Xaml::Controls::IContentPresenter *)
0x18011d4c3  mov     r8, [rbp+57h+pDropDownOverlayPart.ptr_]; value
0x18011d4c7  lea     rdx, [rsi+3F8h]; ptr
0x18011d4ce  mov     this, r14; this
0x18011d4d1  call    ??$SetPtrValueWithQIOrNull@UIBorder@Controls@Xaml@UI@Windows@@UIDependencyObject@345@@WeakReferenceSourceNoThreadId@ctl@@IEAAXAEAV?$TrackerPtr@UIBorder@Controls@Xaml@UI@Windows@@$00$0A@@DirectUI@@PEAUIDependencyObject@Xaml@UI@Windows@@@Z; ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::IBorder,Windows::UI::Xaml::IDependencyObject>(DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::IBorder,1,0> &,Windows::UI::Xaml::IDependencyObject *)
0x18011d4d6  mov     rdi, [rbp+57h+pEditableTextPart.ptr_]
0x18011d4da  lea     r15, [rsi+410h]
0x18011d4e1  mov     rdx, r15; pTrackerPtr
0x18011d4e4  mov     this, r14; this
0x18011d4e7  call    ?RegisterPtr@WeakReferenceSourceNoThreadId@ctl@@AEAAXQEAVTrackerTargetReference@DirectUI@@@Z; ctl::WeakReferenceSourceNoThreadId::RegisterPtr(DirectUI::TrackerTargetReference * const)
0x18011d4ec  mov     [rbp+57h+pValue], r12
0x18011d4f0  test    rdi, rdi
0x18011d4f3  jz      short loc_18011D53D
0x18011d4f5  mov     rax, [rdi]
0x18011d4f8  lea     r8, [rbp+57h+pValue]
0x18011d4fc  lea     rdx, _GUID_e48f5a8b_1dff_4352_a1f4_e516514ec882
0x18011d503  mov     this, rdi
0x18011d506  mov     rax, [rax]
0x18011d509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011d50e  test    eax, eax
0x18011d510  js      short loc_18011D53D
0x18011d512  mov     rdi, [rbp+57h+pValue]
0x18011d516  test    rdi, rdi
0x18011d519  jz      short loc_18011D53D
0x18011d51b  xor     r9d, r9d; bForceLoopback
0x18011d51e  mov     r8b, r13b; bEnsureTrackerTarget
0x18011d521  mov     rdx, rdi; pValue
0x18011d524  mov     this, r15; this
0x18011d527  call    ?Set@TrackerTargetReference@DirectUI@@IEAAXQEAUIUnknown@@EE@Z; DirectUI::TrackerTargetReference::Set(IUnknown * const,uchar,uchar)
0x18011d52c  mov     rax, [rdi]
0x18011d52f  mov     this, rdi
0x18011d532  mov     rax, [rax+10h]
0x18011d536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011d53b  jmp     short loc_18011D54B
0x18011d53d  xor     r8d, r8d; bForceLoopback
0x18011d540  mov     dl, r13b; bEnsureTrackerTarget
0x18011d543  mov     this, r15; this
0x18011d546  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18011d54b  mov     r8, [rbp+57h+pFlyoutButtonPart.ptr_]; value
0x18011d54f  lea     rdx, [rsi+428h]; ptr
0x18011d556  mov     this, r14; this
0x18011d559  call    ??$SetPtrValueWithQIOrNull@UIButtonBase@Primitives@Controls@Xaml@UI@Windows@@UIDependencyObject@456@@WeakReferenceSourceNoThreadId@ctl@@IEAAXAEAV?$TrackerPtr@UIButtonBase@Primitives@Controls@Xaml@UI@Windows@@$00$0A@@DirectUI@@PEAUIDependencyObject@Xaml@UI@Windows@@@Z; ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::Primitives::IButtonBase,Windows::UI::Xaml::IDependencyObject>(DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::Primitives::IButtonBase,1,0> &,Windows::UI::Xaml::IDependencyObject *)
0x18011d55e  mov     r8, [rbp+57h+pItemsPresenterHostPart.ptr_]; value
0x18011d562  lea     rdx, [rsi+440h]; ptr
  ... truncated ...
```
