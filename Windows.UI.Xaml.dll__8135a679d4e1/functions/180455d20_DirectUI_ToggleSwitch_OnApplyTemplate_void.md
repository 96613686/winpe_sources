# DirectUI::ToggleSwitch::OnApplyTemplate(void)

- ea: `0x180455d20`
- end: `0x180456b17`
- name: `?OnApplyTemplate@ToggleSwitch@DirectUI@@UEAAJXZ`
- size: `3575`
- prototype: `HRESULT __fastcall(DirectUI::ToggleSwitch *this)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x180062620`
- `0x1800f4510`
- `0x180119c30`
- `0x180126058`
- `0x180131190`
- `0x180248fa8`
- `0x1802490f0`
- `0x18024e464`
- `0x180455d20`
- `0x180456b20`
- `0x180456bf8`
- `0x180456c8c`
- `0x180456cdc`
- `0x1806e03a0`
- `0x18076e110`
- `0x180b839e4`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18045689b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1804568b5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1804568cf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1804568e9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180456903`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18045691d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18045689b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1804568b5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1804568cf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1804568e9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180456903`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18045691d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180455e6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180455ebd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180455f0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180455f5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180455faf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180455fff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180455e6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180455ebd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180455f0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180455f5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180455faf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180455fff`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__int64 __fastcall DirectUI::ToggleSwitch::OnApplyTemplate(DirectUI::ToggleSwitch *this)
{
  DirectUI::ToggleSwitch *v1; // r12
  __int64 *v3; // rcx
  Windows::UI::Xaml::Controls::Primitives::IThumb **v4; // rdi
  ctl::interface_forwarder<Windows::UI::Xaml::IUIElement9,DirectUI::UIElementGenerated>_vtbl *v5; // rcx
  ctl::interface_forwarder<Windows::UI::Composition::IVisualElement2,DirectUI::UIElement>_vtbl *v6; // rcx
  HRESULT v7; // eax
  unsigned int v8; // r15d
  ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject> *v9; // rbx
  unsigned int (__fastcall *AddRef)(IUnknown *); // rsi
  unsigned int (__fastcall *v11)(IUnknown *); // rsi
  unsigned int (__fastcall *v12)(IUnknown *); // rsi
  unsigned int (__fastcall *v13)(IUnknown *); // rsi
  unsigned int (__fastcall *v14)(IUnknown *); // rsi
  unsigned int (__fastcall *v15)(IUnknown *); // rsi
  Windows::UI::Core::ICoreWindow5 *ptr; // r14
  Windows::UI::Core::ICoreWindow5 *v17; // rsi
  Windows::UI::Core::ICoreWindow5 *v18; // rdi
  void *v19; // rbx
  void *Reserved1; // r15
  void *v21; // r12
  ctl::implements<Windows::UI::Xaml::Data::ISupportIncrementalLoading> *FailFast; // rax
  ctl::implements<Windows::UI::Xaml::Data::ISupportIncrementalLoading> *v23; // rax
  __int128 v24; // xmm0
  __int64 v25; // r8
  IInspectable *v26; // rdx
  ctl::implements<Windows::UI::Xaml::Data::ISupportIncrementalLoading> *v27; // rax
  ctl::implements<Windows::UI::Xaml::Data::ISupportIncrementalLoading> *v28; // rax
  HRESULT v29; // eax
  HRESULT v30; // eax
  ctl::implements<Windows::UI::Xaml::Data::ISupportIncrementalLoading> *v31; // rbx
  ctl::implements<Windows::UI::Xaml::Data::ISupportIncrementalLoading> *v32; // rax
  ctl::implements<Windows::UI::Xaml::Data::ISupportIncrementalLoading> *v33; // r15
  __int128 v34; // xmm0
  IInspectable *v35; // rdx
  ctl::interface_forwarder<Windows::UI::Xaml::IUIElement9,DirectUI::UIElementGenerated>_vtbl *v36; // rcx
  HRESULT v37; // eax
  ctl::implements<Windows::UI::Xaml::Data::ISupportIncrementalLoading>_vtbl *v38; // rax
  ctl::implements<Windows::UI::Xaml::Data::ISupportIncrementalLoading> *v39; // rcx
  Windows::UI::Xaml::IDependencyObject *v40; // rcx
  Windows::UI::Xaml::IDependencyObject *v41; // rcx
  Windows::UI::Xaml::IDependencyObject *v42; // rcx
  Windows::UI::Xaml::IDependencyObject *v43; // rcx
  Windows::UI::Xaml::IDependencyObject *v44; // rcx
  Windows::UI::Xaml::IDependencyObject *v45; // rcx
  ctl::interface_forwarder<Windows::UI::Composition::IVisualElement2,DirectUI::UIElement>_vtbl *v47; // rcx
  HRESULT updated; // eax
  Windows::UI::Core::ICoreWindow5_vtbl *v49; // rax
  HRESULT (__fastcall *GetTrustLevel)(IInspectable *, TrustLevel *); // rbx
  HRESULT v51; // eax
  ctl::interface_forwarder<Windows::UI::Xaml::IFrameworkElement6,DirectUI::FrameworkElementGenerated>_vtbl *v52; // rax
  ctl::interface_forwarder<Windows::UI::Xaml::IFrameworkElement6,DirectUI::FrameworkElementGenerated>_vtbl *v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // rcx
  Windows::UI::Core::ICoreWindow5_vtbl *v56; // rax
  HRESULT (__fastcall *v57)(IInspectable *, TrustLevel *); // rbx
  HRESULT v58; // eax
  __int64 v59; // rcx
  __int128 v60; // xmm0
  __int64 v61; // r8
  IInspectable *v62; // rdx
  __int64 v63; // rax
  ctl::interface_forwarder<Windows::UI::Xaml::IFrameworkElementProtected7,DirectUI::FrameworkElementGenerated>_vtbl *v64; // rdx
  HRESULT v65; // eax
  HRESULT v66; // eax
  __int128 v67; // xmm0
  __int64 v68; // r8
  IInspectable *v69; // rdx
  __int128 v70; // xmm0
  __int64 v71; // r8
  IInspectable *v72; // rdx
  __int128 spIDragDeltaEventHandler; // [rsp+20h] [rbp-A9h] OVERLAPPED BYREF
  __int128 spIDragStartedEventHandler; // [rsp+30h] [rbp-99h] OVERLAPPED BYREF
  ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> spKnobIDependencyObject; // [rsp+40h] [rbp-89h] BYREF
  __int128 spIDragCompletedEventHandler; // [rsp+50h] [rbp-79h] OVERLAPPED BYREF
  ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> spThumbIDependencyObject; // [rsp+60h] [rbp-69h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> spKnobBoundsIDependencyObject; // [rsp+68h] [rbp-61h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> spCurtainClipIDependencyObject; // [rsp+70h] [rbp-59h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> spCurtainBoundsIDependencyObject; // [rsp+78h] [rbp-51h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> spCurtainIDependencyObject; // [rsp+80h] [rbp-49h] BYREF
  ctl::ComPtr<Windows::UI::Core::ICoreWindow5> v82; // [rsp+88h] [rbp-41h] BYREF
  ctl::ComPtr<Windows::UI::Core::ICoreWindow5> v83; // [rsp+90h] [rbp-39h] BYREF
  ctl::ComPtr<Windows::UI::Core::ICoreWindow5> v84; // [rsp+98h] [rbp-31h] BYREF
  __int128 spITappedEventHandler; // [rsp+A0h] [rbp-29h] OVERLAPPED BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-19h] BYREF

  v1 = (DirectUI::ToggleSwitch *)((char *)this - 360);
  spCurtainIDependencyObject.ptr_ = 0;
  spCurtainBoundsIDependencyObject.ptr_ = 0;
  v3 = (__int64 *)*((_QWORD *)&this[-1].Windows::UI::Xaml::Controls::IControlOverrides + 89);
  spCurtainClipIDependencyObject.ptr_ = 0;
  spKnobIDependencyObject.ptr_ = 0;
  spKnobBoundsIDependencyObject.ptr_ = 0;
  spThumbIDependencyObject.ptr_ = 0;
  if ( v3 )
  {
    v63 = *v3;
    v64 = this->DirectUI::ToggleSwitchGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElementProtected7,DirectUI::FrameworkElementGenerated>::m_forwarder.DirectUI::ToggleSwitchGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElementProtected7,DirectUI::FrameworkElementGenerated>::__vftable;
    *(_QWORD *)&spIDragDeltaEventHandler = 0;
    v65 = (*(__int64 (__fastcall **)(__int64 *, ctl::interface_forwarder<Windows::UI::Xaml::IFrameworkElementProtected7,DirectUI::FrameworkElementGenerated>_vtbl *))(v63 + 64))(
            v3,
            v64);
    v8 = v65;
    if ( v65 < 0
      || (v4 = (Windows::UI::Xaml::Controls::Primitives::IThumb **)&this->Windows::UI::Xaml::IFrameworkElement,
          v65 = (*((__int64 (__fastcall **)(Windows::UI::Xaml::IFrameworkElement_vtbl *, DirectUI::CFrameworkEventSource<DirectUI::IDataContextChangedEventSource,DirectUI::IDataContextChangedHandler,DirectUI::DependencyObject,DirectUI::DataContextChangedParams const > *))this->QueryInterface
                 + 10))(
                  this->DirectUI::ToggleSwitchGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::Windows::UI::Xaml::IFrameworkElement::IInspectable::IUnknown::__vftable,
                  this->m_pDataContextChangedSource),
          v8 = v65,
          v65 < 0)
      || (v65 = ((__int64 (__fastcall *)(Windows::UI::Xaml::Controls::Primitives::IThumb *, _QWORD))(*v4)->remove_DragCompleted)(
                  *v4,
                  *((_QWORD *)&this->DirectUI::FrameworkElement + 54)),
          v8 = v65,
          v65 < 0) )
    {
      OnFailure_2990_(v65);
    }
    else
    {
      if ( ctl::do_query_interface<Windows::UI::Xaml::IUIElement,Windows::UI::Xaml::Controls::Primitives::IThumb>(
             (ctl::ComPtr<Windows::UI::Xaml::IUIElement> *)&spIDragDeltaEventHandler,
             *v4) < 0
        || (v66 = (*(__int64 (__fastcall **)(_QWORD, std::vector<Windows::UI::Xaml::Controls::IControl *> *))(*(_QWORD *)spIDragDeltaEventHandler + 592LL))(
                    spIDragDeltaEventHandler,
                    this->m_pChainedGoToElementStateSourceControls),
            v8 = v66,
            v66 >= 0) )
      {
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spIDragDeltaEventHandler);
        goto LABEL_3;
      }
      OnFailure_2990_(v66);
    }
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spIDragDeltaEventHandler);
    goto LABEL_66;
  }
  v4 = (Windows::UI::Xaml::Controls::Primitives::IThumb **)&this->Windows::UI::Xaml::IFrameworkElement;
LABEL_3:
  v5 = this->DirectUI::ToggleSwitchGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IUIElement9,DirectUI::UIElementGenerated>::m_forwarder.DirectUI::ToggleSwitchGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IUIElement9,DirectUI::UIElementGenerated>::__vftable;
  if ( v5 )
  {
    v7 = (*((__int64 (__fastcall **)(ctl::interface_forwarder<Windows::UI::Xaml::IUIElement9,DirectUI::UIElementGenerated>_vtbl *, Windows::UI::Xaml::Controls::IControl_vtbl *))v5->QueryInterface
          + 48))(
           v5,
           this->DirectUI::ToggleSwitchGenerated::DirectUI::Control::DirectUI::ControlGenerated::Windows::UI::Xaml::Controls::IControl::IInspectable::IUnknown::__vftable);
    v8 = v7;
    if ( v7 < 0 )
      goto LABEL_120;
  }
  v6 = this->DirectUI::ToggleSwitchGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::ctl::forwarder_holder<Windows::UI::Composition::IVisualElement2,DirectUI::UIElement>::m_forwarder.DirectUI::ToggleSwitchGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::ctl::forwarder_holder<Windows::UI::Composition::IVisualElement2,DirectUI::UIElement>::__vftable;
  if ( v6 )
  {
    v7 = (*((__int64 (__fastcall **)(ctl::interface_forwarder<Windows::UI::Composition::IVisualElement2,DirectUI::UIElement>_vtbl *, Windows::UI::Xaml::Controls::IControlProtected_vtbl *))v6->QueryInterface
          + 48))(
           v6,
           this->DirectUI::ToggleSwitchGenerated::DirectUI::Control::DirectUI::ControlGenerated::Windows::UI::Xaml::Controls::IControlProtected::IInspectable::IUnknown::__vftable);
    v8 = v7;
    if ( v7 < 0 )
      goto LABEL_120;
  }
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)((char *)&this->m_tpAP.m_trackerReference + 16),
    1u,
    0);
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IUIElementOverrides7,DirectUI::UIElementGenerated>,
    1u,
    0);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement7,DirectUI::FrameworkElementGenerated>);
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IUIElement9,DirectUI::UIElementGenerated>,
    1u,
    0);
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->ctl::forwarder_holder<Windows::UI::Composition::IVisualElement2,DirectUI::UIElement>,
    1u,
    0);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement6,DirectUI::FrameworkElementGenerated>);
  DirectUI::TrackerTargetReference::Clear((DirectUI::TrackerTargetReference *)v4, 1u, 0);
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElementOverrides2,DirectUI::FrameworkElementGenerated>,
    1u,
    0);
  v7 = DirectUI::Control::OnApplyTemplate(this);
  v8 = v7;
  if ( v7 < 0 )
    goto LABEL_120;
  v9 = &this->ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject>;
  AddRef = this->DirectUI::ToggleSwitchGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::DirectUI::DependencyObject::ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject>::m_forwarder.DirectUI::ToggleSwitchGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::DirectUI::DependencyObject::ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject>::__vftable[1].AddRef;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spCurtainIDependencyObject);
  if ( WindowsCreateStringReference(
         L"SwitchCurtain",
         0xDu,
         (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
         (HSTRING *)&hstringHeader) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v7 = ((__int64 (__fastcall *)(ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject> *, void *, ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> *))AddRef)(
         &this->ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject>,
         hstringHeader.Reserved.Reserved1,
         &spCurtainIDependencyObject);
  v8 = v7;
  if ( v7 < 0 )
    goto LABEL_120;
  v11 = v9->m_forwarder.__vftable[1].AddRef;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spCurtainBoundsIDependencyObject);
  if ( WindowsCreateStringReference(
         L"SwitchCurtainBounds",
         0x13u,
         (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
         (HSTRING *)&hstringHeader) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v7 = ((__int64 (__fastcall *)(ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject> *, void *, ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> *))v11)(
         &this->ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject>,
         hstringHeader.Reserved.Reserved1,
         &spCurtainBoundsIDependencyObject);
  v8 = v7;
  if ( v7 < 0 )
    goto LABEL_120;
  v12 = v9->m_forwarder.__vftable[1].AddRef;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spCurtainClipIDependencyObject);
  if ( WindowsCreateStringReference(
         L"SwitchCurtainClip",
         0x11u,
         (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
         (HSTRING *)&hstringHeader) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v7 = ((__int64 (__fastcall *)(ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject> *, void *, ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> *))v12)(
         &this->ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject>,
         hstringHeader.Reserved.Reserved1,
         &spCurtainClipIDependencyObject);
  v8 = v7;
  if ( v7 < 0 )
    goto LABEL_120;
  v13 = v9->m_forwarder.__vftable[1].AddRef;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spKnobIDependencyObject);
  if ( WindowsCreateStringReference(
         L"SwitchKnob",
         0xAu,
         (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
         (HSTRING *)&hstringHeader) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v7 = ((__int64 (__fastcall *)(ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject> *, void *, ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> *))v13)(
         &this->ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject>,
         hstringHeader.Reserved.Reserved1,
         &spKnobIDependencyObject);
  v8 = v7;
  if ( v7 < 0 )
    goto LABEL_120;
  v14 = v9->m_forwarder.__vftable[1].AddRef;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spKnobBoundsIDependencyObject);
  if ( WindowsCreateStringReference(
         L"SwitchKnobBounds",
         0x10u,
         (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
         (HSTRING *)&hstringHeader) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v7 = ((__int64 (__fastcall *)(ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject> *, void *, ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> *))v14)(
         &this->ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject>,
         hstringHeader.Reserved.Reserved1,
         &spKnobBoundsIDependencyObject);
  v8 = v7;
  if ( v7 < 0 )
    goto LABEL_120;
  v15 = v9->m_forwarder.__vftable[1].AddRef;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spThumbIDependencyObject);
  if ( WindowsCreateStringReference(
         L"SwitchThumb",
         0xBu,
         (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
         (HSTRING *)&hstringHeader) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v7 = ((__int64 (__fastcall *)(ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject> *, void *, ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> *))v15)(
         &this->ctl::forwarder_holder<ITrackerOwner,DirectUI::DependencyObject>,
         hstringHeader.Reserved.Reserved1,
         &spThumbIDependencyObject);
  v8 = v7;
  if ( v7 < 0 )
  {
LABEL_120:
    OnFailure_2990_(v7);
    goto LABEL_66;
  }
  ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::IFrameworkElement,Windows::UI::Xaml::IDependencyObject>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].ctl::forwarder_holder<Windows::UI::Xaml::Controls::IControl2,DirectUI::ControlGenerated>,
    (DirectUI::TrackerPtr<Windows::UI::Xaml::IFrameworkElement,1,0> *)((char *)&this->m_tpAP.m_trackerReference + 16),
    spCurtainBoundsIDependencyObject.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::IUIElement,Windows::UI::Xaml::IDependencyObject>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].ctl::forwarder_holder<Windows::UI::Xaml::Controls::IControl2,DirectUI::ControlGenerated>,
    (DirectUI::TrackerPtr<Windows::UI::Xaml::IUIElement,1,0> *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IUIElementOverrides7,DirectUI::UIElementGenerated>,
    spCurtainClipIDependencyObject.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::IFrameworkElement,Windows::UI::Xaml::IDependencyObject>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].ctl::forwarder_holder<Windows::UI::Xaml::Controls::IControl2,DirectUI::ControlGenerated>,
    (DirectUI::TrackerPtr<Windows::UI::Xaml::IFrameworkElement,1,0> *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IUIElement9,DirectUI::UIElementGenerated>,
    spKnobIDependencyObject.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::IFrameworkElement,Windows::UI::Xaml::IDependencyObject>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].ctl::forwarder_holder<Windows::UI::Xaml::Controls::IControl2,DirectUI::ControlGenerated>,
    (DirectUI::TrackerPtr<Windows::UI::Xaml::IFrameworkElement,1,0> *)&this->ctl::forwarder_holder<Windows::UI::Composition::IVisualElement2,DirectUI::UIElement>,
    spKnobBoundsIDependencyObject.ptr_);
  ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::Primitives::IThumb,Windows::UI::Xaml::IDependencyObject>(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].ctl::forwarder_holder<Windows::UI::Xaml::Controls::IControl2,DirectUI::ControlGenerated>,
    (DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::Primitives::IThumb,1,0> *)v4,
    spThumbIDependencyObject.ptr_);
  v82.ptr_ = 0;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(&v82);
  ctl::do_query_interface<Windows::UI::Xaml::IUIElement,Windows::UI::Xaml::IFrameworkElement>(
    (Windows::UI::Xaml::IUIElement **)&v82,
    (Windows::UI::Xaml::Controls::ISlider *)*v4);
  ptr = v82.ptr_;
  v82.ptr_ = 0;
  v83.ptr_ = 0;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(&v83);
  if ( spCurtainIDependencyObject.ptr_ )
    spCurtainIDependencyObject.ptr_->QueryInterface(
      spCurtainIDependencyObject.ptr_,
      &GUID_676d0be9_b65c_41c6_ba40_58cf87f201c1,
      (void **)&v83);
  v17 = v83.ptr_;
  v83.ptr_ = 0;
  if ( !v17 )
  {
LABEL_27:
    v84.ptr_ = 0;
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(&v84);
    if ( spKnobIDependencyObject.ptr_ )
      spKnobIDependencyObject.ptr_->QueryInterface(
        spKnobIDependencyObject.ptr_,
        &GUID_676d0be9_b65c_41c6_ba40_58cf87f201c1,
        (void **)&v84);
    v18 = v84.ptr_;
    v84.ptr_ = 0;
    if ( v18 )
    {
      v49 = v18->__vftable;
      *(_QWORD *)&spIDragStartedEventHandler = 0;
      GetTrustLevel = v49[1].GetTrustLevel;
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spIDragStartedEventHandler);
      v51 = GetTrustLevel(v18, (TrustLevel *)&spIDragStartedEventHandler);
      v8 = v51;
      if ( v51 < 0 )
      {
        OnFailure_2990_(v51);
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spIDragStartedEventHandler);
LABEL_61:
        v18->Release(v18);
LABEL_62:
        if ( !v17 )
          goto LABEL_64;
        goto LABEL_63;
      }
      *(_QWORD *)&spIDragDeltaEventHandler = 0;
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spIDragDeltaEventHandler);
      if ( (_QWORD)spIDragStartedEventHandler )
        (**(void (__fastcall ***)(_QWORD, GUID *, __int128 *))spIDragStartedEventHandler)(
          spIDragStartedEventHandler,
          &GUID_c975905c_3c36_4229_817b_178f64c0e113,
          &spIDragDeltaEventHandler);
      v52 = (ctl::interface_forwarder<Windows::UI::Xaml::IFrameworkElement6,DirectUI::FrameworkElementGenerated>_vtbl *)spIDragDeltaEventHandler;
      v53 = this->DirectUI::ToggleSwitchGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement6,DirectUI::FrameworkElementGenerated>::m_forwarder.DirectUI::ToggleSwitchGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement6,DirectUI::FrameworkElementGenerated>::__vftable;
      v54 = 0;
      *(_QWORD *)&spIDragDeltaEventHandler = 0;
      this->DirectUI::ToggleSwitchGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement6,DirectUI::FrameworkElementGenerated>::m_forwarder.DirectUI::ToggleSwitchGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement6,DirectUI::FrameworkElementGenerated>::__vftable = v52;
      if ( v53 )
      {
        (*((void (__fastcall **)(ctl::interface_forwarder<Windows::UI::Xaml::IFrameworkElement6,DirectUI::FrameworkElementGenerated>_vtbl *))v53->QueryInterface
         + 2))(v53);
        v54 = spIDragDeltaEventHandler;
      }
      if ( v54 )
      {
        *(_QWORD *)&spIDragDeltaEventHandler = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      }
      v55 = spIDragStartedEventHandler;
      if ( (_QWORD)spIDragStartedEventHandler )
      {
        *(_QWORD *)&spIDragStartedEventHandler = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
      }
    }
    if ( ptr )
    {
      v19 = 0;
      Reserved1 = 0;
      v21 = 0;
      *(_QWORD *)&spIDragStartedEventHandler = 0;
      *(_QWORD *)&spIDragDeltaEventHandler = 0;
      *(_QWORD *)&spIDragCompletedEventHandler = 0;
      *(_QWORD *)&spITappedEventHandler = 0;
      FailFast = (ctl::implements<Windows::UI::Xaml::Data::ISupportIncrementalLoading> *)XcpAllocation::OSMemoryAllocateFailFast(0x28u);
      hstringHeader.Reserved.Reserved1 = FailFast;
      if ( FailFast )
      {
        DWORD2(spIDragStartedEventHandler) = 0;
        HIDWORD(spIDragStartedEventHandler) = *(_DWORD *)&hstringHeader.Reserved.Reserved2[12];
        *(_QWORD *)&spIDragStartedEventHandler = DirectUI::ToggleSwitch::DragStartedHandler;
        ctl::implements<Windows::ApplicationModel::ISuspendingEventArgs>::implements<Windows::ApplicationModel::ISuspendingEventArgs>(FailFast);
        v67 = spIDragStartedEventHandler;
        *(_QWORD *)v68 = DirectUI::ClassMemberEventHandler<DirectUI::ToggleSwitch,Windows::UI::Xaml::Controls::IToggleSwitch,Windows::UI::Xaml::Controls::Primitives::IDragStartedEventHandler,IInspectable,Windows::UI::Xaml::Controls::Primitives::IDragStartedEventArgs>::`vftable';
        *(_OWORD *)(v68 + 24) = v67;
        ctl::as_weakref((IWeakReference **)(v68 + 16), v69);
        Reserved1 = hstringHeader.Reserved.Reserved1;
        *(_QWORD *)&spIDragStartedEventHandler = hstringHeader.Reserved.Reserved1;
      }
      v23 = (ctl::implements<Windows::UI::Xaml::Data::ISupportIncrementalLoading> *)XcpAllocation::OSMemoryAllocateFailFast(0x28u);
      hstringHeader.Reserved.Reserved1 = v23;
      if ( v23 )
      {
        DWORD2(spIDragDeltaEventHandler) = 0;
        HIDWORD(spIDragDeltaEventHandler) = *(_DWORD *)&hstringHeader.Reserved.Reserved2[12];
        *(_QWORD *)&spIDragDeltaEventHandler = DirectUI::ToggleSwitch::DragDeltaHandler;
        ctl::implements<Windows::ApplicationModel::ISuspendingEventArgs>::implements<Windows::ApplicationModel::ISuspendingEventArgs>(v23);
        v24 = spIDragDeltaEventHandler;
        *(_QWORD *)v25 = DirectUI::ClassMemberEventHandler<DirectUI::ToggleSwitch,Windows::UI::Xaml::Controls::IToggleSwitch,Windows::UI::Xaml::Controls::Primitives::IDragDeltaEventHandler,IInspectable,Windows::UI::Xaml::Controls::Primitives::IDragDeltaEventArgs>::`vftable';
        *(_OWORD *)(v25 + 24) = v24;
        ctl::as_weakref((IWeakReference **)(v25 + 16), v26);
        *(_QWORD *)&spIDragDeltaEventHandler = hstringHeader.Reserved.Reserved1;
      }
      v27 = (ctl::implements<Windows::UI::Xaml::Data::ISupportIncrementalLoading> *)XcpAllocation::OSMemoryAllocateFailFast(0x28u);
      hstringHeader.Reserved.Reserved1 = v27;
      if ( v27 )
      {
        DWORD2(spIDragCompletedEventHandler) = 0;
        HIDWORD(spIDragCompletedEventHandler) = *(_DWORD *)&hstringHeader.Reserved.Reserved2[12];
        *(_QWORD *)&spIDragCompletedEventHandler = DirectUI::ToggleSwitch::DragCompletedHandler;
        ctl::implements<Windows::ApplicationModel::ISuspendingEventArgs>::implements<Windows::ApplicationModel::ISuspendingEventArgs>(v27);
        v70 = spIDragCompletedEventHandler;
        *(_QWORD *)v71 = DirectUI::ClassMemberEventHandler<DirectUI::ToggleSwitch,Windows::UI::Xaml::Controls::IToggleSwitch,Windows::UI::Xaml::Controls::Primitives::IDragCompletedEventHandler,IInspectable,Windows::UI::Xaml::Controls::Primitives::IDragCompletedEventArgs>::`vftable';
        *(_OWORD *)(v71 + 24) = v70;
        ctl::as_weakref((IWeakReference **)(v71 + 16), v72);
        v21 = hstringHeader.Reserved.Reserved1;
        *(_QWORD *)&spIDragCompletedEventHandler = hstringHeader.Reserved.Reserved1;
      }
      v28 = (ctl::implements<Windows::UI::Xaml::Data::ISupportIncrementalLoading> *)XcpAllocation::OSMemoryAllocateFailFast(0x28u);
      hstringHeader.Reserved.Reserved1 = v28;
      if ( v28 )
      {
        DWORD2(spITappedEventHandler) = 0;
        HIDWORD(spITappedEventHandler) = *(_DWORD *)&hstringHeader.Reserved.Reserved2[12];
        *(_QWORD *)&spITappedEventHandler = DirectUI::ToggleSwitch::TapHandler;
        ctl::implements<Windows::ApplicationModel::ISuspendingEventArgs>::implements<Windows::ApplicationModel::ISuspendingEventArgs>(v28);
        v60 = spITappedEventHandler;
        *(_QWORD *)v61 = DirectUI::ClassMemberEventHandler<DirectUI::ToggleSwitch,Windows::UI::Xaml::Controls::IToggleSwitch,Windows::UI::Xaml::Input::ITappedEventHandler,IInspectable,Windows::UI::Xaml::Input::ITappedRoutedEventArgs>::`vftable';
        *(_OWORD *)(v61 + 24) = v60;
        ctl::as_weakref((IWeakReference **)(v61 + 16), v62);
        v19 = hstringHeader.Reserved.Reserved1;
        *(_QWORD *)&spITappedEventHandler = hstringHeader.Reserved.Reserved1;
      }
      v29 = (*((__int64 (__fastcall **)(Windows::UI::Xaml::IFrameworkElement_vtbl *, void *, ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElementProtected7,DirectUI::FrameworkElementGenerated> *))this->QueryInterface
             + 7))(
              this->DirectUI::ToggleSwitchGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::Windows::UI::Xaml::IFrameworkElement::IInspectable::IUnknown::__vftable,
              Reserved1,
              &this->ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElementProtected7,DirectUI::FrameworkElementGenerated>);
      v8 = v29;
      if ( v29 < 0 )
      {
        OnFailure_2990_(v29);
        if ( v19 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v19 + 16LL))(v19);
        if ( v21 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v21 + 16LL))(v21);
        if ( (_QWORD)spIDragDeltaEventHandler )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)spIDragDeltaEventHandler + 16LL))(spIDragDeltaEventHandler);
        v39 = (ctl::implements<Windows::UI::Xaml::Data::ISupportIncrementalLoading> *)spIDragStartedEventHandler;
        if ( (_QWORD)spIDragStartedEventHandler )
        {
          v38 = *(ctl::implements<Windows::UI::Xaml::Data::ISupportIncrementalLoading>_vtbl **)spIDragStartedEventHandler;
LABEL_59:
          v38->Release(v39);
        }
$Cleanup_3099:
        if ( !v18 )
          goto LABEL_62;
        goto LABEL_61;
      }
      v30 = (*((__int64 (__fastcall **)(Windows::UI::Xaml::IFrameworkElement_vtbl *, _QWORD, DirectUI::CFrameworkEventSource<DirectUI::IDataContextChangedEventSource,DirectUI::IDataContextChangedHandler,DirectUI::DependencyObject,DirectUI::DataContextChangedParams const > **))this->QueryInterface
             + 9))(
              this->DirectUI::ToggleSwitchGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::Windows::UI::Xaml::IFrameworkElement::IInspectable::IUnknown::__vftable,
              spIDragDeltaEventHandler,
              &this->m_pDataContextChangedSource);
      v8 = v30;
      if ( v30 < 0
        || (v30 = (*((__int64 (__fastcall **)(Windows::UI::Xaml::IFrameworkElement_vtbl *, void *, char *))this->QueryInterface
                   + 11))(
                    this->DirectUI::ToggleSwitchGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::Windows::UI::Xaml::IFrameworkElement::IInspectable::IUnknown::__vftable,
                    v21,
                    (char *)&this->DirectUI::FrameworkElement + 432),
            v8 = v30,
            v30 < 0)
        || (v30 = ((__int64 (__fastcall *)(Windows::UI::Core::ICoreWindow5 *, void *, std::vector<Windows::UI::Xaml::Controls::IControl *> **))ptr->__vftable[9].AddRef)(
                    ptr,
                    v19,
                    &this->m_pChainedGoToElementStateSourceControls),
            v8 = v30,
            v30 < 0) )
      {
        OnFailure_2990_(v30);
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spITappedEventHandler);
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spIDragCompletedEventHandler);
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spIDragDeltaEventHandler);
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spIDragStartedEventHandler);
        goto $Cleanup_3099;
      }
      if ( v19 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v19 + 16LL))(v19);
      if ( v21 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v21 + 16LL))(v21);
      if ( (_QWORD)spIDragDeltaEventHandler )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)spIDragDeltaEventHandler + 16LL))(spIDragDeltaEventHandler);
      if ( (_QWORD)spIDragStartedEventHandler )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)spIDragStartedEventHandler + 16LL))(spIDragStartedEventHandler);
      v1 = (DirectUI::ToggleSwitch *)((char *)this - 360);
    }
    if ( this->DirectUI::ToggleSwitchGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IUIElement9,DirectUI::UIElementGenerated>::m_forwarder.DirectUI::ToggleSwitchGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IUIElement9,DirectUI::UIElementGenerated>::__vftable
      || this->DirectUI::ToggleSwitchGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::ctl::forwarder_holder<Windows::UI::Composition::IVisualElement2,DirectUI::UIElement>::m_forwarder.DirectUI::ToggleSwitchGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::ctl::forwarder_holder<Windows::UI::Composition::IVisualElement2,DirectUI::UIElement>::__vftable )
    {
      v31 = 0;
      v32 = (ctl::implements<Windows::UI::Xaml::Data::ISupportIncrementalLoading> *)XcpAllocation::OSMemoryAllocateFailFast(0x28u);
      v33 = v32;
      if ( v32 )
      {
        *(_DWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
        hstringHeader.Reserved.Reserved1 = DirectUI::ToggleSwitch::SizeChangedHandler;
        ctl::implements<Windows::ApplicationModel::ISuspendingEventArgs>::implements<Windows::ApplicationModel::ISuspendingEventArgs>(v32);
        v34 = *(_OWORD *)&hstringHeader.Reserved.Reserved1;
        v33->__vftable = (ctl::implements<Windows::UI::Xaml::Data::ISupportIncrementalLoading>_vtbl *)DirectUI::ClassMemberEventHandler<DirectUI::ToggleSwitch,Windows::UI::Xaml::Controls::IToggleSwitch,Windows::UI::Xaml::ISizeChangedEventHandler,IInspectable,Windows::UI::Xaml::ISizeChangedEventArgs>::`vftable';
        *(_OWORD *)&v33[1].m_cRef = v34;
        ctl::as_weakref((IWeakReference **)&v33[1], v35);
        v31 = v33;
      }
      v36 = this->DirectUI::ToggleSwitchGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IUIElement9,DirectUI::UIElementGenerated>::m_forwarder.DirectUI::ToggleSwitchGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IUIElement9,DirectUI::UIElementGenerated>::__vftable;
      if ( v36
        && (v37 = (*((__int64 (__fastcall **)(ctl::interface_forwarder<Windows::UI::Xaml::IUIElement9,DirectUI::UIElementGenerated>_vtbl *, ctl::implements<Windows::UI::Xaml::Data::ISupportIncrementalLoading> *, Windows::UI::Xaml::Controls::IControl *))v36->QueryInterface
                   + 47))(
                    v36,
                    v31,
                    &this->Windows::UI::Xaml::Controls::IControl),
            v8 = v37,
            v37 < 0)
        || (v47 = this->DirectUI::ToggleSwitchGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::ctl::forwarder_holder<Windows::UI::Composition::IVisualElement2,DirectUI::UIElement>::m_forwarder.DirectUI::ToggleSwitchGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::ctl::forwarder_holder<Windows::UI::Composition::IVisualElement2,DirectUI::UIElement>::__vftable) != 0
        && (v37 = (*((__int64 (__fastcall **)(ctl::interface_forwarder<Windows::UI::Composition::IVisualElement2,DirectUI::UIElement>_vtbl *, ctl::implements<Windows::UI::Xaml::Data::ISupportIncrementalLoading> *, Windows::UI::Xaml::Controls::IControlProtected *))v47->QueryInterface
                   + 47))(
                    v47,
                    v31,
                    &this->Windows::UI::Xaml::Controls::IControlProtected),
            v8 = v37,
            v37 < 0) )
      {
        OnFailure_2990_(v37);
        if ( !v31 )
          goto $Cleanup_3099;
        v38 = v31->__vftable;
        v39 = v31;
        goto LABEL_59;
      }
      if ( v31 )
        v31->Release(v31);
    }
    updated = DirectUI::ToggleSwitch::UpdateHeaderPresenterVisibility(v1);
    v8 = updated;
    if ( updated < 0 || (updated = DirectUI::Control::UpdateVisualState(v1, 0), v8 = updated, updated < 0) )
      OnFailure_2990_(updated);
    goto $Cleanup_3099;
  }
  v56 = v17->__vftable;
  *(_QWORD *)&spIDragDeltaEventHandler = 0;
  v57 = v56[1].GetTrustLevel;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spIDragDeltaEventHandler);
  v58 = v57(v17, (TrustLevel *)&spIDragDeltaEventHandler);
  v8 = v58;
  if ( v58 >= 0 )
  {
    *(_QWORD *)&spIDragCompletedEventHandler = 0;
    ctl::ComPtr<Windows::UI::Xaml::Media::ITransform>::As<Windows::UI::Xaml::Media::ITranslateTransform>(
      (ctl::ComPtr<Windows::UI::Xaml::Media::ITransform> *)&spIDragDeltaEventHandler,
      (ctl::Internal::ComPtrRef<ctl::ComPtr<Windows::UI::Xaml::Media::ITranslateTransform> >)&spIDragCompletedEventHandler);
    ctl::ComPtr<Windows::UI::Xaml::Controls::IScrollContentPresenter>::operator=(
      (Microsoft::WRL::ComPtr<DirectUI::FocusAsyncActionBase<Microsoft::WRL::AsyncCausalityOptions<&DirectUI::FocusManagerTryMoveFocusAsyncOperationName,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > > *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement7,DirectUI::FrameworkElementGenerated>,
      (Microsoft::WRL::ComPtr<DirectUI::FocusAsyncActionBase<Microsoft::WRL::AsyncCausalityOptions<&DirectUI::FocusManagerTryMoveFocusAsyncOperationName,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > > *)&spIDragCompletedEventHandler);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spIDragCompletedEventHandler);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spIDragDeltaEventHandler);
    goto LABEL_27;
  }
  OnFailure_2990_(v58);
  v59 = spIDragDeltaEventHandler;
  if ( (_QWORD)spIDragDeltaEventHandler )
  {
    *(_QWORD *)&spIDragDeltaEventHandler = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
  }
LABEL_63:
  v17->Release(v17);
LABEL_64:
  if ( ptr )
    ptr->Release(ptr);
LABEL_66:
  v40 = spThumbIDependencyObject.ptr_;
  if ( spThumbIDependencyObject.ptr_ )
  {
    spThumbIDependencyObject.ptr_ = 0;
    v40->Release(v40);
  }
  v41 = spKnobBoundsIDependencyObject.ptr_;
  if ( spKnobBoundsIDependencyObject.ptr_ )
  {
    spKnobBoundsIDependencyObject.ptr_ = 0;
    v41->Release(v41);
  }
  v42 = spKnobIDependencyObject.ptr_;
  if ( spKnobIDependencyObject.ptr_ )
  {
    spKnobIDependencyObject.ptr_ = 0;
    v42->Release(v42);
  }
  v43 = spCurtainClipIDependencyObject.ptr_;
  if ( spCurtainClipIDependencyObject.ptr_ )
  {
    spCurtainClipIDependencyObject.ptr_ = 0;
    v43->Release(v43);
  }
  v44 = spCurtainBoundsIDependencyObject.ptr_;
  if ( spCurtainBoundsIDependencyObject.ptr_ )
  {
    spCurtainBoundsIDependencyObject.ptr_ = 0;
    v44->Release(v44);
  }
  v45 = spCurtainIDependencyObject.ptr_;
  if ( spCurtainIDependencyObject.ptr_ )
  {
    spCurtainIDependencyObject.ptr_ = 0;
    v45->Release(v45);
  }
  return v8;
}

```

## disassembly

```asm
0x180455d20  push    rbp
0x180455d22  push    rbx
0x180455d23  push    rsi
0x180455d24  push    rdi
0x180455d25  push    r12
0x180455d27  push    r13
0x180455d29  push    r14
0x180455d2b  push    r15
0x180455d2d  lea     rbp, [rsp-1Fh]
0x180455d32  sub     rsp, 0E8h
0x180455d39  mov     rax, cs:__security_cookie
0x180455d40  xor     rax, rsp
0x180455d43  mov     [rbp+57h+var_50], rax
0x180455d47  lea     r12, [this-168h]
0x180455d4e  mov     [rbp+57h+spCurtainIDependencyObject.ptr_], 0
0x180455d56  mov     r13, this
0x180455d59  mov     [rbp+57h+spCurtainBoundsIDependencyObject.ptr_], 0
0x180455d61  mov     this, [r12+2C8h]
0x180455d69  mov     [rbp+57h+spCurtainClipIDependencyObject.ptr_], 0
0x180455d71  mov     [rsp+120h+spKnobIDependencyObject.ptr_], 0
0x180455d7a  mov     [rbp+57h+spKnobBoundsIDependencyObject.ptr_], 0
0x180455d82  mov     [rbp+57h+spThumbIDependencyObject.ptr_], 0
0x180455d8a  test    this, this
0x180455d8d  jnz     loc_180456774
0x180455d93  lea     rdi, [r13+160h]
0x180455d9a  lea     r14, [r13+118h]
0x180455da1  mov     this, [r14]
0x180455da4  test    this, this
0x180455da7  jnz     loc_180456832
0x180455dad  lea     rbx, [r13+130h]
0x180455db4  mov     this, [rbx]
0x180455db7  test    this, this
0x180455dba  jnz     loc_18045685F
0x180455dc0  lea     this, [r13+148h]; this
0x180455dc7  xor     r8d, r8d; bForceLoopback
0x180455dca  mov     dl, 1; bEnsureTrackerTarget
0x180455dcc  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x180455dd1  lea     this, [r13+100h]; this
0x180455dd8  xor     r8d, r8d; bForceLoopback
0x180455ddb  mov     dl, 1; bEnsureTrackerTarget
0x180455ddd  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x180455de2  lea     this, [r13+198h]; this
0x180455de9  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180455dee  xor     r8d, r8d; bForceLoopback
0x180455df1  mov     dl, 1; bEnsureTrackerTarget
0x180455df3  mov     this, r14; this
0x180455df6  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x180455dfb  xor     r8d, r8d; bForceLoopback
0x180455dfe  mov     dl, 1; bEnsureTrackerTarget
0x180455e00  mov     this, rbx; this
0x180455e03  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x180455e08  lea     this, [r13+190h]; this
0x180455e0f  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180455e14  xor     r8d, r8d; bForceLoopback
0x180455e17  mov     dl, 1; bEnsureTrackerTarget
0x180455e19  mov     this, rdi; this
0x180455e1c  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x180455e21  lea     this, [r13+178h]; this
0x180455e28  xor     r8d, r8d; bForceLoopback
0x180455e2b  mov     dl, 1; bEnsureTrackerTarget
0x180455e2d  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x180455e32  mov     this, r13; this
0x180455e35  call    ?OnApplyTemplate@Control@DirectUI@@UEAAJXZ; DirectUI::Control::OnApplyTemplate(void)
0x180455e3a  mov     r15d, eax
0x180455e3d  test    eax, eax
0x180455e3f  js      loc_180456AE3
0x180455e45  lea     rbx, [r13+60h]
0x180455e49  mov     rax, [rbx]
0x180455e4c  lea     this, [rbp+57h+spCurtainIDependencyObject]; this
0x180455e50  mov     rsi, [rax+40h]
0x180455e54  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180455e59  lea     r9, [rbp+57h+hstringHeader]; string
0x180455e5d  mov     edx, 0Dh; length
0x180455e62  lea     r8, [rbp+57h+hstringHeader.Reserved+8]; hstringHeader
0x180455e66  lea     this, aSwitchcurtain; "SwitchCurtain"
0x180455e6d  call    cs:__imp_WindowsCreateStringReference
0x180455e73  test    eax, eax
0x180455e75  js      loc_18045688C
0x180455e7b  mov     rdx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x180455e7f  lea     r8, [rbp+57h+spCurtainIDependencyObject]
0x180455e83  mov     this, rbx
0x180455e86  mov     rax, rsi
0x180455e89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180455e8e  mov     r15d, eax
0x180455e91  test    eax, eax
0x180455e93  js      loc_180456AD7
0x180455e99  mov     rax, [rbx]
0x180455e9c  lea     this, [rbp+57h+spCurtainBoundsIDependencyObject]; this
0x180455ea0  mov     rsi, [rax+40h]
0x180455ea4  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180455ea9  lea     r9, [rbp+57h+hstringHeader]; string
0x180455ead  mov     edx, 13h; length
0x180455eb2  lea     r8, [rbp+57h+hstringHeader.Reserved+8]; hstringHeader
0x180455eb6  lea     this, aSwitchcurtainb; "SwitchCurtainBounds"
0x180455ebd  call    cs:__imp_WindowsCreateStringReference
0x180455ec3  test    eax, eax
0x180455ec5  js      loc_1804568A6
0x180455ecb  mov     rdx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x180455ecf  lea     r8, [rbp+57h+spCurtainBoundsIDependencyObject]
0x180455ed3  mov     this, rbx
0x180455ed6  mov     rax, rsi
0x180455ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180455ede  mov     r15d, eax
0x180455ee1  test    eax, eax
0x180455ee3  js      loc_180456ACB
0x180455ee9  mov     rax, [rbx]
0x180455eec  lea     this, [rbp+57h+spCurtainClipIDependencyObject]; this
0x180455ef0  mov     rsi, [rax+40h]
0x180455ef4  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180455ef9  lea     r9, [rbp+57h+hstringHeader]; string
0x180455efd  mov     edx, 11h; length
0x180455f02  lea     r8, [rbp+57h+hstringHeader.Reserved+8]; hstringHeader
0x180455f06  lea     this, aSwitchcurtainc; "SwitchCurtainClip"
0x180455f0d  call    cs:__imp_WindowsCreateStringReference
0x180455f13  test    eax, eax
0x180455f15  js      loc_1804568C0
0x180455f1b  mov     rdx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x180455f1f  lea     r8, [rbp+57h+spCurtainClipIDependencyObject]
0x180455f23  mov     this, rbx
0x180455f26  mov     rax, rsi
0x180455f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180455f2e  mov     r15d, eax
0x180455f31  test    eax, eax
0x180455f33  js      loc_18045661B
0x180455f39  mov     rax, [rbx]
0x180455f3c  lea     this, [rsp+120h+spKnobIDependencyObject]; this
0x180455f41  mov     rsi, [rax+40h]
0x180455f45  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180455f4a  lea     r9, [rbp+57h+hstringHeader]; string
0x180455f4e  mov     edx, 0Ah; length
0x180455f53  lea     r8, [rbp+57h+hstringHeader.Reserved+8]; hstringHeader
0x180455f57  lea     this, aSwitchknob; "SwitchKnob"
0x180455f5e  call    cs:__imp_WindowsCreateStringReference
0x180455f64  test    eax, eax
0x180455f66  js      loc_1804568DA
0x180455f6c  mov     rdx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x180455f70  lea     r8, [rsp+120h+spKnobIDependencyObject]
0x180455f75  mov     this, rbx
0x180455f78  mov     rax, rsi
0x180455f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180455f80  mov     r15d, eax
0x180455f83  test    eax, eax
0x180455f85  js      loc_180456ABF
0x180455f8b  mov     rax, [rbx]
0x180455f8e  lea     this, [rbp+57h+spKnobBoundsIDependencyObject]; this
0x180455f92  mov     rsi, [rax+40h]
0x180455f96  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180455f9b  lea     r9, [rbp+57h+hstringHeader]; string
0x180455f9f  mov     edx, 10h; length
0x180455fa4  lea     r8, [rbp+57h+hstringHeader.Reserved+8]; hstringHeader
0x180455fa8  lea     this, aSwitchknobboun; "SwitchKnobBounds"
0x180455faf  call    cs:__imp_WindowsCreateStringReference
0x180455fb5  test    eax, eax
0x180455fb7  js      loc_1804568F4
0x180455fbd  mov     rdx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x180455fc1  lea     r8, [rbp+57h+spKnobBoundsIDependencyObject]
0x180455fc5  mov     this, rbx
0x180455fc8  mov     rax, rsi
0x180455fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180455fd0  mov     r15d, eax
0x180455fd3  test    eax, eax
0x180455fd5  js      loc_180456AB3
0x180455fdb  mov     rax, [rbx]
0x180455fde  lea     this, [rbp+57h+spThumbIDependencyObject]; this
0x180455fe2  mov     rsi, [rax+40h]
0x180455fe6  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180455feb  lea     r9, [rbp+57h+hstringHeader]; string
0x180455fef  mov     edx, 0Bh; length
0x180455ff4  lea     r8, [rbp+57h+hstringHeader.Reserved+8]; hstringHeader
0x180455ff8  lea     this, aSwitchthumb; "SwitchThumb"
0x180455fff  call    cs:__imp_WindowsCreateStringReference
0x180456005  test    eax, eax
0x180456007  js      loc_18045690E
0x18045600d  mov     rdx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x180456011  lea     r8, [rbp+57h+spThumbIDependencyObject]
0x180456015  mov     this, rbx
0x180456018  mov     rax, rsi
0x18045601b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180456020  mov     r15d, eax
0x180456023  test    eax, eax
0x180456025  js      loc_180456AA7
0x18045602b  mov     r8, [rbp+57h+spCurtainBoundsIDependencyObject.ptr_]; value
0x18045602f  lea     rbx, [r13-160h]
0x180456036  mov     this, rbx; this
0x180456039  lea     rdx, [r13+148h]; ptr
0x180456040  call    ??$SetPtrValueWithQIOrNull@UIFrameworkElement@Xaml@UI@Windows@@UIDependencyObject@234@@WeakReferenceSourceNoThreadId@ctl@@IEAAXAEAV?$TrackerPtr@UIFrameworkElement@Xaml@UI@Windows@@$00$0A@@DirectUI@@PEAUIDependencyObject@Xaml@UI@Windows@@@Z; ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::IFrameworkElement,Windows::UI::Xaml::IDependencyObject>(DirectUI::TrackerPtr<Windows::UI::Xaml::IFrameworkElement,1,0> &,Windows::UI::Xaml::IDependencyObject *)
0x180456045  mov     r8, [rbp+57h+spCurtainClipIDependencyObject.ptr_]; value
0x180456049  lea     rdx, [r13+100h]; ptr
0x180456050  mov     this, rbx; this
0x180456053  call    ??$SetPtrValueWithQIOrNull@UIUIElement@Xaml@UI@Windows@@UIDependencyObject@234@@WeakReferenceSourceNoThreadId@ctl@@IEAAXAEAV?$TrackerPtr@UIUIElement@Xaml@UI@Windows@@$00$0A@@DirectUI@@PEAUIDependencyObject@Xaml@UI@Windows@@@Z; ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::IUIElement,Windows::UI::Xaml::IDependencyObject>(DirectUI::TrackerPtr<Windows::UI::Xaml::IUIElement,1,0> &,Windows::UI::Xaml::IDependencyObject *)
0x180456058  mov     r8, [rsp+120h+spKnobIDependencyObject.ptr_]; value
0x18045605d  mov     rdx, r14; ptr
0x180456060  mov     this, rbx; this
0x180456063  call    ??$SetPtrValueWithQIOrNull@UIFrameworkElement@Xaml@UI@Windows@@UIDependencyObject@234@@WeakReferenceSourceNoThreadId@ctl@@IEAAXAEAV?$TrackerPtr@UIFrameworkElement@Xaml@UI@Windows@@$00$0A@@DirectUI@@PEAUIDependencyObject@Xaml@UI@Windows@@@Z; ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::IFrameworkElement,Windows::UI::Xaml::IDependencyObject>(DirectUI::TrackerPtr<Windows::UI::Xaml::IFrameworkElement,1,0> &,Windows::UI::Xaml::IDependencyObject *)
0x180456068  mov     r8, [rbp+57h+spKnobBoundsIDependencyObject.ptr_]; value
0x18045606c  lea     rdx, [r13+130h]; ptr
0x180456073  mov     this, rbx; this
0x180456076  call    ??$SetPtrValueWithQIOrNull@UIFrameworkElement@Xaml@UI@Windows@@UIDependencyObject@234@@WeakReferenceSourceNoThreadId@ctl@@IEAAXAEAV?$TrackerPtr@UIFrameworkElement@Xaml@UI@Windows@@$00$0A@@DirectUI@@PEAUIDependencyObject@Xaml@UI@Windows@@@Z; ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::IFrameworkElement,Windows::UI::Xaml::IDependencyObject>(DirectUI::TrackerPtr<Windows::UI::Xaml::IFrameworkElement,1,0> &,Windows::UI::Xaml::IDependencyObject *)
0x18045607b  mov     r8, [rbp+57h+spThumbIDependencyObject.ptr_]; value
0x18045607f  mov     rdx, rdi; ptr
0x180456082  mov     this, rbx; this
0x180456085  call    ??$SetPtrValueWithQIOrNull@UIThumb@Primitives@Controls@Xaml@UI@Windows@@UIDependencyObject@456@@WeakReferenceSourceNoThreadId@ctl@@IEAAXAEAV?$TrackerPtr@UIThumb@Primitives@Controls@Xaml@UI@Windows@@$00$0A@@DirectUI@@PEAUIDependencyObject@Xaml@UI@Windows@@@Z; ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::Primitives::IThumb,Windows::UI::Xaml::IDependencyObject>(DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::Primitives::IThumb,1,0> &,Windows::UI::Xaml::IDependencyObject *)
0x18045608a  lea     this, [rbp+57h+var_98]; this
0x18045608e  mov     [rbp+57h+var_98.ptr_], 0
0x180456096  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18045609b  mov     rdx, [rdi]; pIn
0x18045609e  lea     this, [rbp+57h+var_98]; pOut
0x1804560a2  call    ??$do_query_interface@UIUIElement@Xaml@UI@Windows@@UIFrameworkElement@234@@ctl@@YAJAEAPEAUIUIElement@Xaml@UI@Windows@@PEAUIFrameworkElement@234@@Z; ctl::do_query_interface<Windows::UI::Xaml::IUIElement,Windows::UI::Xaml::IFrameworkElement>(Windows::UI::Xaml::IUIElement * &,Windows::UI::Xaml::IFrameworkElement *)
0x1804560a7  mov     r14, [rbp+57h+var_98.ptr_]
0x1804560ab  lea     this, [rbp+57h+var_90]; this
0x1804560af  mov     [rbp+57h+var_98.ptr_], 0
0x1804560b7  mov     [rbp+57h+var_90.ptr_], 0
0x1804560bf  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1804560c4  mov     this, [rbp+57h+spCurtainIDependencyObject.ptr_]
0x1804560c8  test    this, this
0x1804560cb  jz      short loc_1804560E3
0x1804560cd  mov     rax, [this]
0x1804560d0  lea     r8, [rbp+57h+var_90]
0x1804560d4  lea     rdx, _GUID_676d0be9_b65c_41c6_ba40_58cf87f201c1
0x1804560db  mov     rax, [rax]
0x1804560de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804560e3  mov     rsi, [rbp+57h+var_90.ptr_]
0x1804560e7  mov     [rbp+57h+var_90.ptr_], 0
0x1804560ef  test    rsi, rsi
0x1804560f2  jnz     loc_1804566B3
0x1804560f8  lea     this, [rbp+57h+var_88]; this
0x1804560fc  mov     [rbp+57h+var_88.ptr_], 0
0x180456104  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180456109  mov     this, [rsp+120h+spKnobIDependencyObject.ptr_]
0x18045610e  test    this, this
0x180456111  jz      short loc_180456129
0x180456113  mov     rax, [this]
0x180456116  lea     r8, [rbp+57h+var_88]
0x18045611a  lea     rdx, _GUID_676d0be9_b65c_41c6_ba40_58cf87f201c1
0x180456121  mov     rax, [rax]
0x180456124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180456129  mov     rdi, [rbp+57h+var_88.ptr_]
0x18045612d  mov     [rbp+57h+var_88.ptr_], 0
0x180456135  test    rdi, rdi
0x180456138  jnz     loc_180456551
0x18045613e  test    r14, r14
0x180456141  jz      loc_18045631D
0x180456147  xor     ebx, ebx
0x180456149  xor     r15d, r15d
0x18045614c  xor     r12d, r12d
0x18045614f  mov     [rsp+120h+spIDragStartedEventHandler.ptr_], r15
0x180456154  mov     [rsp+120h+spIDragDeltaEventHandler.ptr_], r15
0x180456159  mov     [rbp+57h+spIDragCompletedEventHandler.ptr_], r12
0x18045615d  lea     ecx, [rbx+28h]; cSize
0x180456160  mov     [rbp+57h+spITappedEventHandler.ptr_], rbx
0x180456164  call    ?OSMemoryAllocateFailFast@XcpAllocation@@YAPEAX_K@Z; XcpAllocation::OSMemoryAllocateFailFast(unsigned __int64)
0x180456169  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x18045616d  mov     r8, rax
0x180456170  test    rax, rax
0x180456173  jnz     loc_180456998
0x180456179  mov     ecx, 28h ; '('; cSize
0x18045617e  call    ?OSMemoryAllocateFailFast@XcpAllocation@@YAPEAX_K@Z; XcpAllocation::OSMemoryAllocateFailFast(unsigned __int64)
0x180456183  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x180456187  mov     r8, rax
0x18045618a  test    rax, rax
0x18045618d  jz      short loc_1804561EC
0x18045618f  lea     rax, [r13-160h]
0x180456196  mov     [rsp+120h+var_F8], ebx
0x18045619a  lea     this, [r13-168h]
0x1804561a1  neg     this
0x1804561a4  mov     ecx, dword ptr [rbp+57h+hstringHeader.Reserved+0Ch]
0x1804561a7  sbb     rdx, rdx
0x1804561aa  mov     [rsp+120h+var_F4], ecx
0x1804561ae  and     rdx, rax
0x1804561b1  mov     this, r8; this
0x1804561b4  lea     rax, ?DragDeltaHandler@ToggleSwitch@DirectUI@@AEAAJPEAUIInspectable@@PEAUIDragDeltaEventArgs@Primitives@Controls@Xaml@UI@Windows@@@Z; DirectUI::ToggleSwitch::DragDeltaHandler(IInspectable *,Windows::UI::Xaml::Controls::Primitives::IDragDeltaEventArgs *)
0x1804561bb  mov     [rsp+120h+spIDragDeltaEventHandler.ptr_], rax
0x1804561c0  call    ??0?$implements@UISuspendingEventArgs@ApplicationModel@Windows@@@ctl@@IEAA@XZ; ctl::implements<Windows::ApplicationModel::ISuspendingEventArgs>::implements<Windows::ApplicationModel::ISuspendingEventArgs>(void)
0x1804561c5  movaps  xmm0, xmmword ptr [rsp+120h+spIDragDeltaEventHandler.ptr_]
0x1804561ca  lea     this, ??_7?$ClassMemberEventHandler@VToggleSwitch@DirectUI@@UIToggleSwitch@Controls@Xaml@UI@Windows@@UIDragDeltaEventHandler@Primitives@4567@UIInspectable@@UIDragDeltaEventArgs@94567@@DirectUI@@6B@; const DirectUI::ClassMemberEventHandler<DirectUI::ToggleSwitch,Windows::UI::Xaml::Controls::IToggleSwitch,Windows::UI::Xaml::Controls::Primitives::IDragDeltaEventHandler,IInspectable,Windows::UI::Xaml::Controls::Primitives::IDragDeltaEventArgs>::`vftable'
0x1804561d1  mov     [r8], this
0x1804561d4  lea     this, [r8+10h]; pWeakRef
0x1804561d8  movdqu  xmmword ptr [r8+18h], xmm0
0x1804561de  call    ?as_weakref@ctl@@YAJAEAPEAUIWeakReference@@PEAUIInspectable@@@Z; ctl::as_weakref(IWeakReference * &,IInspectable *)
0x1804561e3  mov     rax, qword ptr [rbp+57h+hstringHeader.Reserved]
0x1804561e7  mov     [rsp+120h+spIDragDeltaEventHandler.ptr_], rax
0x1804561ec  mov     ecx, 28h ; '('; cSize
0x1804561f1  call    ?OSMemoryAllocateFailFast@XcpAllocation@@YAPEAX_K@Z; XcpAllocation::OSMemoryAllocateFailFast(unsigned __int64)
0x1804561f6  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x1804561fa  mov     r8, rax
0x1804561fd  test    rax, rax
0x180456200  jnz     loc_1804569FA
0x180456206  mov     ecx, 28h ; '('; cSize
0x18045620b  call    ?OSMemoryAllocateFailFast@XcpAllocation@@YAPEAX_K@Z; XcpAllocation::OSMemoryAllocateFailFast(unsigned __int64)
0x180456210  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x180456214  mov     r8, rax
0x180456217  test    rax, rax
0x18045621a  jnz     loc_180456717
0x180456220  mov     this, [r13+160h]
0x180456227  lea     r8, [r13+1A0h]
0x18045622e  mov     rdx, r15
0x180456231  mov     rax, [this]
0x180456234  mov     rax, [rax+38h]
0x180456238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18045623d  mov     r15d, eax
  ... truncated ...
```
