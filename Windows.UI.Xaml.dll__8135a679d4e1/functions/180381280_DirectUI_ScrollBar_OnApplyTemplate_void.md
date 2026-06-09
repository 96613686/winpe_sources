# DirectUI::ScrollBar::OnApplyTemplate(void)

- ea: `0x180381280`
- end: `0x180383696`
- name: `?OnApplyTemplate@ScrollBar@DirectUI@@MEAAJXZ`
- size: `9238`
- prototype: `HRESULT __fastcall(DirectUI::ScrollBar *this)`
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004bc0`
- `0x18005b234`
- `0x18005bcac`
- `0x18005e96c`
- `0x180062620`
- `0x1800f2084`
- `0x1800f4510`
- `0x180131190`
- `0x1801df610`
- `0x1801dfeb0`
- `0x1802490f0`
- `0x18024e464`
- `0x18038114c`
- `0x180381280`
- `0x18038369c`
- `0x1803837f0`
- `0x1803839c0`
- `0x1805aff58`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038164c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803816a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038178c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803817e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803819d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180381a2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180381b75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038244c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803824ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038254a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803825a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803826da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180382739`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180382b56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180382b8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180382bee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180382d2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180382d8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180382e0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180382e69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180383450`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038164c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803816a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038178c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803817e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803819d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180381a2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180381b75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038244c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803824ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18038254a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803825a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803826da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180382739`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180382b56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180382b8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180382bee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180382d2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180382d8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180382e0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180382e69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180383450`

## pseudocode

```c
__int64 __fastcall DirectUI::ScrollBar::OnApplyTemplate(DirectUI::ScrollBar *this)
{
  DirectUI::DXamlCore *v1; // rbx
  DirectUI::ScrollBar *v2; // rdx
  DirectUI::DXamlCore *v3; // r14
  ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElementOverrides2,DirectUI::FrameworkElementGenerated> *v4; // rax
  ctl::interface_forwarder<Windows::UI::Xaml::IFrameworkElementOverrides2,DirectUI::FrameworkElementGenerated>_vtbl *v5; // rcx
  DirectUI::DXamlCore *v6; // r12
  DirectUI::DXamlCore *v7; // r13
  DirectUI::DXamlCore *v8; // rsi
  DirectUI::DXamlCore *v9; // r15
  DirectUI::DXamlCore *v10; // rdi
  ctl::interface_forwarder<Windows::UI::Composition::IVisualElement2,DirectUI::UIElement>_vtbl *v11; // rcx
  ctl::interface_forwarder<Windows::UI::Xaml::IUIElement9,DirectUI::UIElementGenerated>_vtbl *v12; // rcx
  Windows::UI::Xaml::IFrameworkElement_vtbl *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  Windows::UI::Xaml::Controls::IControl_vtbl *v16; // rcx
  DirectUI::CFrameworkEventSource<DirectUI::IDataContextChangedEventSource,DirectUI::IDataContextChangedHandler,DirectUI::DependencyObject,DirectUI::DataContextChangedParams const > *m_pDataContextChangedSource; // rcx
  ctl::interface_forwarder<Windows::UI::Xaml::Controls::IControl5,DirectUI::ControlGenerated>_vtbl *v18; // rcx
  ctl::interface_forwarder<Windows::UI::Xaml::Controls::IControl2,DirectUI::ControlGenerated>_vtbl *v19; // rcx
  HRESULT v20; // eax
  Windows::UI::Xaml::IFrameworkElement *ptr; // rcx
  HRESULT ValueByKnownIndex; // eax
  HRESULT LocalizedResourceString; // eax
  Windows::UI::Xaml::Controls::Primitives::IRepeatButton *v24; // rcx
  HRESULT v25; // eax
  HRESULT updated; // eax
  Windows::UI::Xaml::IFrameworkElement *v27; // rcx
  Windows::UI::Xaml::Controls::Primitives::IRepeatButton *v28; // rcx
  Windows::UI::Xaml::Controls::Primitives::IRepeatButton *v29; // rcx
  Windows::UI::Xaml::Controls::Primitives::IRepeatButton *v30; // rcx
  Windows::UI::Xaml::Controls::Primitives::IRepeatButton *v31; // rcx
  Windows::UI::Xaml::Controls::Primitives::IThumb *v32; // rcx
  Windows::UI::Xaml::IFrameworkElement *v33; // rcx
  Windows::UI::Xaml::IFrameworkElement *v34; // rcx
  Windows::UI::Xaml::IFrameworkElement *v35; // rcx
  Windows::UI::Xaml::IFrameworkElement *v36; // rcx
  DirectUI::ScrollBar *v37; // kr00_8
  __int64 v38; // r8
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // r8
  DirectUI::ScrollBar *v43; // kr08_8
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // r8
  DirectUI::ScrollBar *v48; // kr10_8
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  DirectUI::ScrollBar *v52; // kr18_8
  __int64 v53; // r8
  __int64 v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rcx
  Windows::UI::Xaml::Controls::Primitives::IThumb *v57; // rcx
  Windows::UI::Xaml::Controls::Primitives::IThumb *v58; // rcx
  Windows::UI::Xaml::Controls::Primitives::IRepeatButton *v59; // rcx
  Windows::UI::Xaml::Controls::Primitives::IRepeatButton *v60; // rcx
  Windows::UI::Xaml::Controls::Primitives::IRepeatButton *v61; // rcx
  Windows::UI::Xaml::Controls::Primitives::IRepeatButton *v62; // rcx
  Windows::UI::Xaml::Controls::Primitives::IRepeatButton *v63; // rcx
  Windows::UI::Xaml::Controls::Primitives::IRepeatButton *v64; // rcx
  Windows::UI::Xaml::Controls::Primitives::IRepeatButton *v65; // rcx
  Windows::UI::Xaml::Controls::Primitives::IRepeatButton *v66; // rcx
  Windows::UI::Xaml::IFrameworkElement *v67; // rcx
  Windows::UI::Xaml::IFrameworkElement *v68; // rcx
  Windows::UI::Xaml::IFrameworkElement *v69; // rcx
  Windows::UI::Xaml::IFrameworkElement *v70; // rcx
  Windows::UI::Xaml::IFrameworkElement *v71; // rcx
  Windows::UI::Xaml::IFrameworkElement *v72; // rcx
  DirectUI::ScrollBar *v74; // kr20_8
  __int64 v75; // r8
  __int64 v76; // r8
  DirectUI::ScrollBar *v77; // kr28_8
  __int64 v78; // rcx
  __int64 v79; // rcx
  __int64 v80; // r8
  DirectUI::ScrollBar *v81; // kr30_8
  __int64 m_value; // rcx
  __int64 v83; // rcx
  __int64 v84; // rcx
  __int64 v85; // rcx
  ctl::WeakReferenceSourceNoThreadId *v86; // [rsp+20h] [rbp-E0h]
  DirectUI::TrackerTargetReference *v87[2]; // [rsp+30h] [rbp-D0h]
  DirectUI::TrackerPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,1,0> *p_m_tpElementHorizontalTemplate; // [rsp+30h] [rbp-D0h]
  DirectUI::TrackerTargetReference *v89; // [rsp+40h] [rbp-C0h]
  DirectUI::TrackerTargetReference *v90; // [rsp+48h] [rbp-B8h]
  DirectUI::TrackerTargetReference *v91; // [rsp+50h] [rbp-B0h]
  DirectUI::TrackerTargetReference *v92; // [rsp+58h] [rbp-A8h]
  DirectUI::TrackerTargetReference *v93; // [rsp+60h] [rbp-A0h]
  DirectUI::TrackerTargetReference *p_m_pDataContextChangedSource; // [rsp+68h] [rbp-98h]
  DirectUI::TrackerTargetReference *v95; // [rsp+70h] [rbp-90h]
  DirectUI::TrackerTargetReference *v96; // [rsp+78h] [rbp-88h]
  DirectUI::TrackerTargetReference *v97; // [rsp+80h] [rbp-80h]
  DirectUI::TrackerTargetReference *v98; // [rsp+88h] [rbp-78h]
  ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::IThumb> spElementHorizontalThumb; // [rsp+90h] [rbp-70h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::IThumb> spElementVerticalThumb; // [rsp+98h] [rbp-68h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::IRepeatButton> spElementVerticalSmallDecrease; // [rsp+A0h] [rbp-60h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::IRepeatButton> spElementVerticalSmallIncrease; // [rsp+A8h] [rbp-58h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::IRepeatButton> spElementVerticalLargeDecrease; // [rsp+B0h] [rbp-50h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::IRepeatButton> spElementHorizontalSmallDecrease; // [rsp+B8h] [rbp-48h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::IRepeatButton> spElementHorizontalSmallIncrease; // [rsp+C0h] [rbp-40h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::IRepeatButton> spElementHorizontalLargeDecrease; // [rsp+C8h] [rbp-38h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::IRepeatButton> spElementHorizontalLargeIncrease; // [rsp+D0h] [rbp-30h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IFrameworkElement> spElementVerticalPanningThumb; // [rsp+D8h] [rbp-28h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IFrameworkElement> spElementVerticalPanningRoot; // [rsp+E0h] [rbp-20h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IFrameworkElement> spElementHorizontalPanningThumb; // [rsp+E8h] [rbp-18h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IFrameworkElement> spElementHorizontalPanningRoot; // [rsp+F0h] [rbp-10h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IFrameworkElement> spElementVerticalTemplate; // [rsp+F8h] [rbp-8h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::IFrameworkElement> spElementHorizontalTemplate; // [rsp+100h] [rbp+0h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::IRepeatButton> spElementVerticalLargeIncrease; // [rsp+108h] [rbp+8h] BYREF
  DirectUI::TrackerTargetReference *pTrackerPtr; // [rsp+110h] [rbp+10h]
  DirectUI::TrackerTargetReference *v116; // [rsp+118h] [rbp+18h]
  DirectUI::TrackerTargetReference *v117; // [rsp+120h] [rbp+20h]
  DirectUI::TrackerTargetReference *p_m_initialVal; // [rsp+128h] [rbp+28h]
  DirectUI::TrackerTargetReference *v119; // [rsp+130h] [rbp+30h]
  unsigned int v121; // [rsp+198h] [rbp+98h]
  DirectUI::DXamlCore *Current; // [rsp+198h] [rbp+98h]
  DirectUI::DXamlCore *v123; // [rsp+198h] [rbp+98h]
  DirectUI::DXamlCore *v124; // [rsp+198h] [rbp+98h]
  DirectUI::DXamlCore *FailFast; // [rsp+198h] [rbp+98h]
  DirectUI::DXamlCore *v126; // [rsp+198h] [rbp+98h]
  DirectUI::DXamlCore *v127; // [rsp+198h] [rbp+98h]
  DirectUI::DXamlCore *v128; // [rsp+198h] [rbp+98h]
  DirectUI::DXamlCore *v129; // [rsp+198h] [rbp+98h]
  DirectUI::DXamlCore *v130; // [rsp+198h] [rbp+98h]
  DirectUI::DXamlCore *v131; // [rsp+198h] [rbp+98h]
  DirectUI::DXamlCore *v132; // [rsp+198h] [rbp+98h]
  DirectUI::DXamlCore *v133; // [rsp+198h] [rbp+98h]
  DirectUI::DXamlCore *v134; // [rsp+198h] [rbp+98h]
  DirectUI::DXamlCore *v135; // [rsp+198h] [rbp+98h]
  DirectUI::DXamlCore *v136; // [rsp+198h] [rbp+98h]
  DirectUI::DXamlCore *v137; // [rsp+198h] [rbp+98h]
  DirectUI::DXamlCore *v138; // [rsp+198h] [rbp+98h]
  Windows::Internal::String strAutomationName; // [rsp+1A0h] [rbp+A0h] BYREF
  DirectUI::ScrollBar *v140; // [rsp+1A8h] [rbp+A8h]

  v1 = 0;
  strAutomationName._hstring = 0;
  spElementHorizontalTemplate.ptr_ = 0;
  v140 = (DirectUI::ScrollBar *)((char *)this - 360);
  v2 = this;
  BYTE2(this->DirectUI::ScrollBarGenerated::DirectUI::RangeBase::DirectUI::RangeBaseGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IUIElement5,DirectUI::UIElementGenerated>::m_forwarder.DirectUI::ScrollBarGenerated::DirectUI::RangeBase::DirectUI::RangeBaseGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IUIElement5,DirectUI::UIElementGenerated>::__vftable) = 1;
  v3 = 0;
  v4 = &this->ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElementOverrides2,DirectUI::FrameworkElementGenerated>;
  spElementVerticalTemplate.ptr_ = 0;
  v5 = this->DirectUI::ScrollBarGenerated::DirectUI::RangeBase::DirectUI::RangeBaseGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElementOverrides2,DirectUI::FrameworkElementGenerated>::m_forwarder.DirectUI::ScrollBarGenerated::DirectUI::RangeBase::DirectUI::RangeBaseGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElementOverrides2,DirectUI::FrameworkElementGenerated>::__vftable;
  v6 = 0;
  v7 = 0;
  spElementHorizontalPanningRoot.ptr_ = 0;
  v8 = 0;
  spElementHorizontalPanningThumb.ptr_ = 0;
  v9 = 0;
  spElementVerticalPanningRoot.ptr_ = 0;
  v10 = 0;
  spElementVerticalPanningThumb.ptr_ = 0;
  spElementHorizontalLargeIncrease.ptr_ = 0;
  spElementHorizontalLargeDecrease.ptr_ = 0;
  spElementHorizontalSmallIncrease.ptr_ = 0;
  spElementHorizontalSmallDecrease.ptr_ = 0;
  spElementVerticalLargeIncrease.ptr_ = 0;
  spElementVerticalLargeDecrease.ptr_ = 0;
  spElementVerticalSmallIncrease.ptr_ = 0;
  spElementVerticalSmallDecrease.ptr_ = 0;
  spElementVerticalThumb.ptr_ = 0;
  spElementHorizontalThumb.ptr_ = 0;
  v89 = (DirectUI::TrackerTargetReference *)v4;
  if ( v5 )
  {
    v20 = (*((__int64 (__fastcall **)(ctl::interface_forwarder<Windows::UI::Xaml::IFrameworkElementOverrides2,DirectUI::FrameworkElementGenerated>_vtbl *, IUnknown *))v5->QueryInterface
           + 8))(
            v5,
            v2->m_tpElementHorizontalLargeIncrease.m_trackerReference.m_value);
    v121 = v20;
    if ( v20 < 0 )
      goto LABEL_322;
    m_value = (__int64)v89->m_value;
    if ( !v89->m_value )
      m_value = 536;
    v20 = (*(__int64 (__fastcall **)(__int64, DirectUI::TrackerTargetReference::ReferenceTrackerTargetData *))(*(_QWORD *)m_value + 80LL))(
            m_value,
            this->m_tpElementHorizontalLargeIncrease.m_trackerReference.m_trackerData);
    v121 = v20;
    if ( v20 < 0 )
      goto LABEL_322;
    v83 = (__int64)v89->m_value;
    if ( !v89->m_value )
      v83 = 536;
    v20 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v83 + 96LL))(
            v83,
            *((_QWORD *)&this->m_tpElementHorizontalLargeIncrease.m_trackerReference + 2));
    v121 = v20;
    if ( v20 < 0 )
      goto LABEL_322;
    v2 = this;
  }
  v11 = v2->DirectUI::ScrollBarGenerated::DirectUI::RangeBase::DirectUI::RangeBaseGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::ctl::forwarder_holder<Windows::UI::Composition::IVisualElement2,DirectUI::UIElement>::m_forwarder.DirectUI::ScrollBarGenerated::DirectUI::RangeBase::DirectUI::RangeBaseGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::ctl::forwarder_holder<Windows::UI::Composition::IVisualElement2,DirectUI::UIElement>::__vftable;
  v91 = (DirectUI::TrackerTargetReference *)&v2->ctl::forwarder_holder<Windows::UI::Composition::IVisualElement2,DirectUI::UIElement>;
  if ( v11 )
  {
    v20 = (*((__int64 (__fastcall **)(__int64, IUnknown *))v11[-2].GetVisualInternal + 15))(
            (__int64)&v11[-2].GetVisualInternal,
            v2->m_tpElementHorizontalLargeDecrease.m_trackerReference.m_value);
    v121 = v20;
    if ( v20 < 0 )
      goto LABEL_322;
    v2 = this;
  }
  v12 = v2->DirectUI::ScrollBarGenerated::DirectUI::RangeBase::DirectUI::RangeBaseGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IUIElement9,DirectUI::UIElementGenerated>::m_forwarder.DirectUI::ScrollBarGenerated::DirectUI::RangeBase::DirectUI::RangeBaseGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IUIElement9,DirectUI::UIElementGenerated>::__vftable;
  v93 = (DirectUI::TrackerTargetReference *)&v2->ctl::forwarder_holder<Windows::UI::Xaml::IUIElement9,DirectUI::UIElementGenerated>;
  if ( v12 )
  {
    v20 = (*((__int64 (__fastcall **)(__int64, DirectUI::TrackerTargetReference::ReferenceTrackerTargetData *))v12[-1].get_TransformMatrix
           + 15))(
            (__int64)&v12[-1].get_TransformMatrix,
            v2->m_tpElementHorizontalLargeDecrease.m_trackerReference.m_trackerData);
    v121 = v20;
    if ( v20 < 0 )
      goto LABEL_322;
    v2 = this;
  }
  v13 = v2->DirectUI::ScrollBarGenerated::DirectUI::RangeBase::DirectUI::RangeBaseGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::Windows::UI::Xaml::IFrameworkElement::IInspectable::IUnknown::__vftable;
  v95 = (DirectUI::TrackerTargetReference *)&v2->Windows::UI::Xaml::IFrameworkElement;
  if ( v13 )
  {
    v20 = (*((__int64 (__fastcall **)(HRESULT (__fastcall **)(Windows::UI::Xaml::IFrameworkElement *, Windows::UI::Xaml::IRoutedEventHandler *, EventRegistrationToken *), _QWORD))v13[-1].add_Unloaded
           + 15))(
            &v13[-1].add_Unloaded,
            *((_QWORD *)&v2->m_tpElementHorizontalLargeDecrease.m_trackerReference + 2));
    v121 = v20;
    if ( v20 < 0 )
      goto LABEL_322;
    v2 = this;
  }
  v14 = *((_QWORD *)&v2->m_tpAP.m_trackerReference + 2);
  v97 = (DirectUI::TrackerTargetReference *)((char *)&v2->m_tpAP.m_trackerReference + 16);
  if ( v14 )
  {
    v20 = (*(__int64 (__fastcall **)(__int64, IUnknown *))(*(_QWORD *)(v14 - 64) + 120LL))(
            v14 - 64,
            v2->m_tpElementHorizontalSmallIncrease.m_trackerReference.m_value);
    v121 = v20;
    if ( v20 < 0 )
      goto LABEL_322;
    v2 = this;
  }
  v15 = *((_QWORD *)&v2->DirectUI::Control + 65);
  v90 = (DirectUI::TrackerTargetReference *)((char *)&v2->DirectUI::Control + 520);
  if ( v15 )
  {
    v20 = (*(__int64 (__fastcall **)(__int64, DirectUI::TrackerTargetReference::ReferenceTrackerTargetData *))(*(_QWORD *)v15 + 64LL))(
            v15,
            v2->m_tpElementHorizontalSmallIncrease.m_trackerReference.m_trackerData);
    v121 = v20;
    if ( v20 < 0 )
      goto LABEL_322;
    v84 = (__int64)v90->m_value;
    if ( !v90->m_value )
      v84 = 536;
    v20 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v84 + 80LL))(
            v84,
            *((_QWORD *)&this->m_tpElementHorizontalSmallIncrease.m_trackerReference + 2));
    v121 = v20;
    if ( v20 < 0 )
      goto LABEL_322;
    v85 = (__int64)v90->m_value;
    if ( !v90->m_value )
      v85 = 536;
    v20 = (*(__int64 (__fastcall **)(__int64, IUnknown *))(*(_QWORD *)v85 + 96LL))(
            v85,
            this->m_tpElementHorizontalSmallDecrease.m_trackerReference.m_value);
    v121 = v20;
    if ( v20 < 0 )
      goto LABEL_322;
    v2 = this;
  }
  v16 = v2->DirectUI::ScrollBarGenerated::DirectUI::RangeBase::DirectUI::RangeBaseGenerated::DirectUI::Control::DirectUI::ControlGenerated::Windows::UI::Xaml::Controls::IControl::IInspectable::IUnknown::__vftable;
  v92 = (DirectUI::TrackerTargetReference *)&v2->Windows::UI::Xaml::Controls::IControl;
  if ( v16 )
  {
    v20 = (*((__int64 (__fastcall **)(HRESULT (__fastcall **)(Windows::UI::Xaml::Controls::IControl *, Windows::UI::Xaml::Thickness *__struct_ptr), DirectUI::TrackerTargetReference::ReferenceTrackerTargetData *))v16[-1].put_BorderThickness
           + 15))(
            &v16[-1].put_BorderThickness,
            v2->m_tpElementHorizontalSmallDecrease.m_trackerReference.m_trackerData);
    v121 = v20;
    if ( v20 < 0 )
      goto LABEL_322;
    v2 = this;
  }
  m_pDataContextChangedSource = v2->m_pDataContextChangedSource;
  p_m_pDataContextChangedSource = (DirectUI::TrackerTargetReference *)&v2->m_pDataContextChangedSource;
  if ( m_pDataContextChangedSource )
  {
    v20 = ((__int64 (__fastcall *)(DirectUI::CFrameworkEventSource<DirectUI::IDataContextChangedEventSource,DirectUI::IDataContextChangedHandler,DirectUI::DependencyObject,DirectUI::DataContextChangedParams const > *, _QWORD))m_pDataContextChangedSource[-1].DirectUI::CEventSourceBase<DirectUI::IDataContextChangedEventSource,DirectUI::IDataContextChangedHandler,DirectUI::DependencyObject,DirectUI::DataContextChangedParams const >::DirectUI::IDataContextChangedEventSource::IUnknown::__vftable[2].AddRef)(
            &m_pDataContextChangedSource[-1],
            *((_QWORD *)&v2->m_tpElementHorizontalSmallDecrease.m_trackerReference + 2));
    v121 = v20;
    if ( v20 < 0 )
      goto LABEL_322;
    v2 = this;
  }
  v18 = v2->DirectUI::ScrollBarGenerated::DirectUI::RangeBase::DirectUI::RangeBaseGenerated::DirectUI::Control::DirectUI::ControlGenerated::ctl::forwarder_holder<Windows::UI::Xaml::Controls::IControl5,DirectUI::ControlGenerated>::m_forwarder.DirectUI::ScrollBarGenerated::DirectUI::RangeBase::DirectUI::RangeBaseGenerated::DirectUI::Control::DirectUI::ControlGenerated::ctl::forwarder_holder<Windows::UI::Xaml::Controls::IControl5,DirectUI::ControlGenerated>::__vftable;
  v96 = (DirectUI::TrackerTargetReference *)&v2->ctl::forwarder_holder<Windows::UI::Xaml::Controls::IControl5,DirectUI::ControlGenerated>;
  if ( v18 )
  {
    v20 = (*((__int64 (__fastcall **)(ctl::interface_forwarder<Windows::UI::Xaml::Controls::IControl5,DirectUI::ControlGenerated>_vtbl *, IUnknown *))v18[-1].QueryInterface
           + 15))(
            v18 - 1,
            v2->m_tpElementHorizontalThumb.m_trackerReference.m_value);
    v121 = v20;
    if ( v20 < 0 )
      goto LABEL_322;
    v2 = this;
  }
  v19 = v2->DirectUI::ScrollBarGenerated::DirectUI::RangeBase::DirectUI::RangeBaseGenerated::DirectUI::Control::DirectUI::ControlGenerated::ctl::forwarder_holder<Windows::UI::Xaml::Controls::IControl2,DirectUI::ControlGenerated>::m_forwarder.DirectUI::ScrollBarGenerated::DirectUI::RangeBase::DirectUI::RangeBaseGenerated::DirectUI::Control::DirectUI::ControlGenerated::ctl::forwarder_holder<Windows::UI::Xaml::Controls::IControl2,DirectUI::ControlGenerated>::__vftable;
  v98 = (DirectUI::TrackerTargetReference *)&v2->ctl::forwarder_holder<Windows::UI::Xaml::Controls::IControl2,DirectUI::ControlGenerated>;
  if ( v19 )
  {
    v20 = (*((__int64 (__fastcall **)(ctl::interface_forwarder<Windows::UI::Xaml::Controls::IControl2,DirectUI::ControlGenerated>_vtbl *, DirectUI::TrackerTargetReference::ReferenceTrackerTargetData *))v19[-1].QueryInterface
           + 15))(
            v19 - 1,
            v2->m_tpElementHorizontalThumb.m_trackerReference.m_trackerData);
    v121 = v20;
    if ( v20 >= 0 )
    {
      v2 = this;
      goto LABEL_11;
    }
LABEL_322:
    OnFailure_2990_(v20);
    goto $Cleanup_2541;
  }
LABEL_11:
  pTrackerPtr = (DirectUI::TrackerTargetReference *)&v2->ctl::forwarder_holder<Windows::UI::Xaml::IUIElementOverrides7,DirectUI::UIElementGenerated>;
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&v2->ctl::forwarder_holder<Windows::UI::Xaml::IUIElementOverrides7,DirectUI::UIElementGenerated>,
    1u,
    0);
  DirectUI::TrackerTargetReference::Clear(v93, 1u, 0);
  DirectUI::TrackerTargetReference::Clear(v91, 1u, 0);
  DirectUI::TrackerTargetReference::Clear(v97, 1u, 0);
  DirectUI::TrackerTargetReference::Clear(v95, 1u, 0);
  DirectUI::TrackerTargetReference::Clear(v89, 1u, 0);
  v116 = (DirectUI::TrackerTargetReference *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement6,DirectUI::FrameworkElementGenerated>;
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->ctl::forwarder_holder<Windows::UI::Xaml::IFrameworkElement6,DirectUI::FrameworkElementGenerated>,
    1u,
    0);
  DirectUI::TrackerTargetReference::Clear(p_m_pDataContextChangedSource, 1u, 0);
  DirectUI::TrackerTargetReference::Clear(v92, 1u, 0);
  DirectUI::TrackerTargetReference::Clear(v98, 1u, 0);
  DirectUI::TrackerTargetReference::Clear(v90, 1u, 0);
  DirectUI::TrackerTargetReference::Clear(v96, 1u, 0);
  v117 = (DirectUI::TrackerTargetReference *)&this->Windows::UI::Xaml::Controls::Primitives::IRangeBaseOverrides;
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->Windows::UI::Xaml::Controls::Primitives::IRangeBaseOverrides,
    1u,
    0);
  p_m_initialVal = (DirectUI::TrackerTargetReference *)&this->m_initialVal;
  DirectUI::TrackerTargetReference::Clear((DirectUI::TrackerTargetReference *)&this->m_initialVal, 1u, 0);
  v119 = (DirectUI::TrackerTargetReference *)&this->Windows::UI::Xaml::Controls::Primitives::IScrollBar;
  DirectUI::TrackerTargetReference::Clear(
    (DirectUI::TrackerTargetReference *)&this->Windows::UI::Xaml::Controls::Primitives::IScrollBar,
    1u,
    0);
  p_m_tpElementHorizontalTemplate = (DirectUI::TrackerPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,1,0> *)&this->m_tpElementHorizontalTemplate;
  DirectUI::TrackerTargetReference::Clear(&this->m_tpElementHorizontalTemplate.m_trackerReference, 1u, 0);
  v20 = DirectUI::Control::OnApplyTemplate(this);
  v121 = v20;
  if ( v20 < 0 )
    goto LABEL_322;
  ptr = spElementHorizontalTemplate.ptr_;
  if ( spElementHorizontalTemplate.ptr_ )
  {
    spElementHorizontalTemplate.ptr_ = 0;
    ptr->Release(ptr);
  }
  v20 = DirectUI::ScrollBar::GetTemplateChildHelper<Windows::UI::Xaml::IFrameworkElement,Windows::UI::Xaml::IFrameworkElement>(
          v140,
          (wchar_t *)L"HorizontalRoot",
          0xEu,
          &spElementHorizontalTemplate.ptr_);
  v121 = v20;
  if ( v20 < 0 )
    goto LABEL_322;
  v86 = (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpElementVerticalTemplate.m_trackerReference.8;
  ctl::WeakReferenceSourceNoThreadId::RegisterPtr(
    (ctl::WeakReferenceSourceNoThreadId *)&this[-1].m_tpElementVerticalTemplate.m_trackerReference.8,
    pTrackerPtr);
  DirectUI::TrackerPtr<Windows::UI::Xaml::Interop::IBindableVector,1,0>::Set<Windows::UI::Xaml::Interop::IBindableVector>(
    (DirectUI::TrackerPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,1,0> *)pTrackerPtr,
    (Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *> *)spElementHorizontalTemplate.ptr_);
  ValueByKnownIndex = DirectUI::ScrollBar::GetTemplateChildHelper<Windows::UI::Xaml::Controls::Primitives::IRepeatButton,Windows::UI::Xaml::Controls::Primitives::IRepeatButton>(
                        v140,
                        (wchar_t *)L"HorizontalLargeIncrease",
                        0x17u,
                        &spElementHorizontalLargeIncrease.ptr_);
  v121 = ValueByKnownIndex;
  if ( ValueByKnownIndex < 0 )
    goto LABEL_324;
  ctl::WeakReferenceSourceNoThreadId::RegisterPtr(v86, v93);
  if ( spElementHorizontalLargeIncrease.ptr_ )
    DirectUI::TrackerTargetReference::Set(v93, spElementHorizontalLargeIncrease.ptr_, 1u, 0);
  else
    DirectUI::TrackerTargetReference::Clear(v93, 1u, 0);
  if ( v93->m_value )
  {
    WindowsDeleteString(0);
    ValueByKnownIndex = DirectUI::DependencyObject::GetValueByKnownIndex(
                          (DirectUI::DependencyObject *)((__int64)&v93->m_value[-79] & -(__int64)(v93->m_value != 0)),
                          AutomationProperties_Name,
                          &strAutomationName._hstring);
    v121 = ValueByKnownIndex;
    if ( ValueByKnownIndex < 0
      || !strAutomationName._hstring
      && ((Current = DirectUI::DXamlCore::GetCurrent(),
           WindowsDeleteString(0),
           strAutomationName._hstring = 0,
           ValueByKnownIndex = DirectUI::DXamlCore::GetLocalizedResourceString(
                                 Current,
                                 0x14ADu,
                                 &strAutomationName._hstring),
           v121 = ValueByKnownIndex,
           ValueByKnownIndex < 0)
       || (ValueByKnownIndex = DirectUI::DependencyObject::SetValueByKnownIndex(
                                 (DirectUI::DependencyObject *)((__int64)&v93->m_value[-79]
                                                              & -(__int64)(v93->m_value != 0)),
                                 AutomationProperties_Name,
                                 strAutomationName._hstring),
           v121 = ValueByKnownIndex,
           ValueByKnownIndex < 0)) )
    {
LABEL_324:
      OnFailure_2990_(ValueByKnownIndex);
      goto $Cleanup_2541;
    }
  }
  LocalizedResourceString = DirectUI::ScrollBar::GetTemplateChildHelper<Windows::UI::Xaml::Controls::Primitives::IRepeatButton,Windows::UI::Xaml::Controls::Primitives::IRepeatButton>(
                              v140,
                              (wchar_t *)L"HorizontalSmallIncrease",
                              0x17u,
                              &spElementHorizontalSmallIncrease.ptr_);
  v121 = LocalizedResourceString;
  if ( LocalizedResourceString < 0 )
    goto LABEL_252;
  ctl::WeakReferenceSourceNoThreadId::RegisterPtr(v86, v97);
  if ( spElementHorizontalSmallIncrease.ptr_ )
    DirectUI::TrackerTargetReference::Set(v97, spElementHorizontalSmallIncrease.ptr_, 1u, 0);
  else
    DirectUI::TrackerTargetReference::Clear(v97, 1u, 0);
  if ( v97->m_value )
  {
    WindowsDeleteString(strAutomationName._hstring);
    strAutomationName._hstring = 0;
    LocalizedResourceString = DirectUI::DependencyObject::GetValueByKnownIndex(
                                (DirectUI::DependencyObject *)((__int64)&v97->m_value[-79]
                                                             & -(__int64)(v97->m_value != 0)),
                                AutomationProperties_Name,
                                &strAutomationName._hstring);
    v121 = LocalizedResourceString;
    if ( LocalizedResourceString < 0 )
      goto LABEL_252;
    if ( !strAutomationName._hstring )
    {
      v123 = DirectUI::DXamlCore::GetCurrent();
      WindowsDeleteString(0);
      strAutomationName._hstring = 0;
      LocalizedResourceString = DirectUI::DXamlCore::GetLocalizedResourceString(
                                  v123,
                                  0x14AEu,
                                  &strAutomationName._hstring);
      v121 = LocalizedResourceString;
      if ( LocalizedResourceString < 0 )
        goto LABEL_252;
      LocalizedResourceString = DirectUI::DependencyObject::SetValueByKnownIndex(
                                  (DirectUI::DependencyObject *)((__int64)&v97->m_value[-79]
                                                               & -(__int64)(v97->m_value != 0)),
                                  AutomationProperties_Name,
                                  strAutomationName._hstring);
      v121 = LocalizedResourceString;
      if ( LocalizedResourceString < 0 )
        goto LABEL_252;
    }
  }
  v24 = spElementHorizontalLargeDecrease.ptr_;
  if ( spElementHorizontalLargeDecrease.ptr_ )
  {
    spElementHorizontalLargeDecrease.ptr_ = 0;
    v24->Release(v24);
  }
  LocalizedResourceString = DirectUI::ScrollBar::GetTemplateChildHelper<Windows::UI::Xaml::Controls::Primitives::IRepeatButton,Windows::UI::Xaml::Controls::Primitives::IRepeatButton>(
                              v140,
                              (wchar_t *)L"HorizontalLargeDecrease",
                              0x17u,
                              &spElementHorizontalLargeDecrease.ptr_);
  v121 = LocalizedResourceString;
  if ( LocalizedResourceString < 0 )
    goto LABEL_252;
  ctl::WeakReferenceSourceNoThreadId::RegisterPtr(v86, v91);
  if ( spElementHorizontalLargeDecrease.ptr_ )
    DirectUI::TrackerTargetReference::Set(v91, spElementHorizontalLargeDecrease.ptr_, 1u, 0);
  else
    DirectUI::TrackerTargetReference::Clear(v91, 1u, 0);
  if ( v91->m_value )
  {
    WindowsDeleteString(strAutomationName._hstring);
    strAutomationName._hstring = 0;
    LocalizedResourceString = DirectUI::DependencyObject::GetValueByKnownIndex(
                                (DirectUI::DependencyObject *)((__int64)&v91->m_value[-79]
                                                             & -(__int64)(v91->m_value != 0)),
                                AutomationProperties_Name,
                                &strAutomationName._hstring);
    v121 = LocalizedResourceString;
    if ( LocalizedResourceString < 0
      || !strAutomationName._hstring
      && ((v135 = DirectUI::DXamlCore::GetCurrent(),
           WindowsDeleteString(0),
           strAutomationName._hstring = 0,
           LocalizedResourceString = DirectUI::DXamlCore::GetLocalizedResourceString(
                                       v135,
                                       0x14AFu,
                                       &strAutomationName._hstring),
           v121 = LocalizedResourceString,
           LocalizedResourceString < 0)
       || (LocalizedResourceString = DirectUI::DependencyObject::SetValueByKnownIndex(
                                       (DirectUI::DependencyObject *)((__int64)&v91->m_value[-79]
                                                                    & -(__int64)(v91->m_value != 0)),
                                       AutomationProperties_Name,
                                       strAutomationName._hstring),
           v121 = LocalizedResourceString,
           LocalizedResourceString < 0)) )
    {
LABEL_252:
      OnFailure_2990_(LocalizedResourceString);
      goto $Cleanup_2541;
    }
  }
  v25 = DirectUI::ScrollBar::GetTemplateChildHelper<Windows::UI::Xaml::Controls::Primitives::IRepeatButton,Windows::UI::Xaml::Controls::Primitives::IRepeatButton>(
          v140,
          (wchar_t *)L"HorizontalSmallDecrease",
          0x17u,
          &spElementHorizontalSmallDecrease.ptr_);
  v121 = v25;
  if ( v25 < 0 )
    goto LABEL_160;
  ctl::WeakReferenceSourceNoThreadId::RegisterPtr(v86, v95);
  if ( spElementHorizontalSmallDecrease.ptr_ )
    DirectUI::TrackerTargetReference::Set(v95, spElementHorizontalSmallDecrease.ptr_, 1u, 0);
  else
    DirectUI::TrackerTargetReference::Clear(v95, 1u, 0);
  if ( v95->m_value )
  {
    WindowsDeleteString(strAutomationName._hstring);
    strAutomationName._hstring = 0;
    v25 = DirectUI::DependencyObject::GetValueByKnownIndex(
            (DirectUI::DependencyObject *)((__int64)&v95->m_value[-79] & -(__int64)(v95->m_value != 0)),
            AutomationProperties_Name,
            &strAutomationName._hstring);
    v121 = v25;
    if ( v25 < 0
      || !strAutomationName._hstring
      && ((v131 = DirectUI::DXamlCore::GetCurrent(),
           WindowsDeleteString(0),
           strAutomationName._hstring = 0,
           v25 = DirectUI::DXamlCore::GetLocalizedResourceString(v131, 0x14B0u, &strAutomationName._hstring),
           v121 = v25,
           v25 < 0)
       || (v25 = DirectUI::DependencyObject::SetValueByKnownIndex(
                   (DirectUI::DependencyObject *)((__int64)&v95->m_value[-79] & -(__int64)(v95->m_value != 0)),
                   AutomationProperties_Name,
                   strAutomationName._hstring),
           v121 = v25,
           v25 < 0)) )
    {
LABEL_160:
      OnFailure_2990_(v25);
      goto $Cleanup_2541;
    }
  }
  updated = DirectUI::ScrollBar::GetTemplateChildHelper<Windows::UI::Xaml::Controls::Primitives::IThumb,Windows::UI::Xaml::Controls::Primitives::IThumb>(
              v140,
              (wchar_t *)L"HorizontalThumb",
              0xFu,
              &spElementHorizontalThumb.ptr_);
  v121 = updated;
  if ( updated < 0 )
    goto LABEL_196;
  ctl::WeakReferenceSourceNoThreadId::RegisterPtr(v86, v89);
  if ( spElementHorizontalThumb.ptr_ )
    DirectUI::TrackerTargetReference::Set(v89, spElementHorizontalThumb.ptr_, 1u, 0);
  else
    DirectUI::TrackerTargetReference::Clear(v89, 1u, 0);
  if ( v89->m_value )
  {
    WindowsDeleteString(strAutomationName._hstring);
    strAutomationName._hstring = 0;
    updated = DirectUI::DependencyObject::GetValueByKnownIndex(
                (DirectUI::DependencyObject *)((__int64)&v89->m_value[-67] & -(__int64)(v89->m_value != 0)),
                AutomationProperties_Name,
                &strAutomationName._hstring);
    v121 = updated;
    if ( updated < 0 )
      goto LABEL_196;
    if ( !strAutomationName._hstring )
    {
      v124 = DirectUI::DXamlCore::GetCurrent();
      WindowsDeleteString(0);
      strAutomationName._hstring = 0;
      updated = DirectUI::DXamlCore::GetLocalizedResourceString(v124, 0x14B1u, &strAutomationName._hstring);
      v121 = updated;
      if ( updated < 0 )
        goto LABEL_196;
      updated = DirectUI::DependencyObject::SetValueByKnownIndex(
                  (DirectUI::DependencyObject *)((__int64)&v89->m_value[-67] & -(__int64)(v89->m_value != 0)),
                  AutomationProperties_Name,
                  strAutomationName._hstring);
      v121 = updated;
      if ( updated < 0 )
        goto LABEL_196;
    }
  }
  v27 = spElementVerticalTemplate.ptr_;
  if ( spElementVerticalTemplate.ptr_ )
  {
    spElementVerticalTemplate.ptr_ = 0;
    v27->Release(v27);
  }
  updated = DirectUI::ScrollBar::GetTemplateChildHelper<Windows::UI::Xaml::IFrameworkElement,Windows::UI::Xaml::IFrameworkElement>(
              v140,
              (wchar_t *)L"VerticalRoot",
              0xCu,
              &spElementVerticalTemplate.ptr_);
  v121 = updated;
  if ( updated < 0 )
    goto LABEL_196;
  ctl::WeakReferenceSourceNoThreadId::RegisterPtr(v86, v116);
  DirectUI::TrackerPtr<Windows::UI::Xaml::Interop::IBindableVector,1,0>::Set<Windows::UI::Xaml::Interop::IBindableVector>(
    (DirectUI::TrackerPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,1,0> *)v116,
    (Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *> *)spElementVerticalTemplate.ptr_);
  v28 = spElementVerticalLargeIncrease.ptr_;
  if ( spElementVerticalLargeIncrease.ptr_ )
  {
    spElementVerticalLargeIncrease.ptr_ = 0;
    v28->Release(v28);
  }
  updated = DirectUI::ScrollBar::GetTemplateChildHelper<Windows::UI::Xaml::Controls::Primitives::IRepeatButton,Windows::UI::Xaml::Controls::Primitives::IRepeatButton>(
              v140,
              (wchar_t *)L"VerticalLargeIncrease",
              0x15u,
              &spElementVerticalLargeIncrease.ptr_);
  v121 = updated;
  if ( updated < 0 )
    goto LABEL_196;
  ctl::WeakReferenceSourceNoThreadId::RegisterPtr(v86, p_m_pDataContextChangedSource);
  if ( spElementVerticalLargeIncrease.ptr_ )
    DirectUI::TrackerTargetReference::Set(p_m_pDataContextChangedSource, spElementVerticalLargeIncrease.ptr_, 1u, 0);
  else
    DirectUI::TrackerTargetReference::Clear(p_m_pDataContextChangedSource, 1u, 0);
  if ( p_m_pDataContextChangedSource->m_value )
  {
    WindowsDeleteString(strAutomationName._hstring);
    strAutomationName._hstring = 0;
    updated = DirectUI::DependencyObject::GetValueByKnownIndex(
                (DirectUI::DependencyObject *)((__int64)&p_m_pDataContextChangedSource->m_value[-79]
                                             & -(__int64)(p_m_pDataContextChangedSource->m_value != 0)),
                AutomationProperties_Name,
                &strAutomationName._hstring);
    v121 = updated;
    if ( updated < 0 )
      goto LABEL_196;
    if ( !strAutomationName._hstring )
    {
      v138 = DirectUI::DXamlCore::GetCurrent();
      WindowsDeleteString(0);
      strAutomationName._hstring = 0;
      updated = DirectUI::DXamlCore::GetLocalizedResourceString(v138, 0x14B2u, &strAutomationName._hstring);
      v121 = updated;
      if ( updated < 0 )
        goto LABEL_196;
      updated = DirectUI::DependencyObject::SetValueByKnownIndex(
                  (DirectUI::DependencyObject *)((__int64)&p_m_pDataContextChangedSource->m_value[-79]
                                               & -(__int64)(p_m_pDataContextChangedSource->m_value != 0)),
                  AutomationProperties_Name,
                  strAutomationName._hstring);
      v121 = updated;
      if ( updated < 0 )
        goto LABEL_196;
    }
  }
  v29 = spElementVerticalSmallIncrease.ptr_;
  if ( spElementVerticalSmallIncrease.ptr_ )
  {
    spElementVerticalSmallIncrease.ptr_ = 0;
    v29->Release(v29);
  }
  updated = DirectUI::ScrollBar::GetTemplateChildHelper<Windows::UI::Xaml::Controls::Primitives::IRepeatButton,Windows::UI::Xaml::Controls::Primitives::IRepeatButton>(
              v140,
              (wchar_t *)L"VerticalSmallIncrease",
              0x15u,
              &spElementVerticalSmallIncrease.ptr_);
  v121 = updated;
  if ( updated < 0 )
    goto LABEL_196;
  ctl::WeakReferenceSourceNoThreadId::RegisterPtr(v86, v98);
  if ( spElementVerticalSmallIncrease.ptr_ )
    DirectUI::TrackerTargetReference::Set(v98, spElementVerticalSmallIncrease.ptr_, 1u, 0);
  else
    DirectUI::TrackerTargetReference::Clear(v98, 1u, 0);
  if ( v98->m_value )
  {
    WindowsDeleteString(strAutomationName._hstring);
    strAutomationName._hstring = 0;
    updated = DirectUI::DependencyObject::GetValueByKnownIndex(
                (DirectUI::DependencyObject *)((__int64)&v98->m_value[-79] & -(__int64)(v98->m_value != 0)),
                AutomationProperties_Name,
                &strAutomationName._hstring);
    v121 = updated;
    if ( updated < 0 )
      goto LABEL_196;
    if ( !strAutomationName._hstring )
    {
      v137 = DirectUI::DXamlCore::GetCurrent();
      WindowsDeleteString(0);
      strAutomationName._hstring = 0;
      updated = DirectUI::DXamlCore::GetLocalizedResourceString(v137, 0x14B3u, &strAutomationName._hstring);
      v121 = updated;
      if ( updated < 0 )
        goto LABEL_196;
      updated = DirectUI::DependencyObject::SetValueByKnownIndex(
                  (DirectUI::DependencyObject *)((__int64)&v98->m_value[-79] & -(__int64)(v98->m_value != 0)),
                  AutomationProperties_Name,
                  strAutomationName._hstring);
      v121 = updated;
      if ( updated < 0 )
        goto LABEL_196;
    }
  }
  v30 = spElementVerticalLargeDecrease.ptr_;
  if ( spElementVerticalLargeDecrease.ptr_ )
  {
    spElementVerticalLargeDecrease.ptr_ = 0;
    v30->Release(v30);
  }
  updated = DirectUI::ScrollBar::GetTemplateChildHelper<Windows::UI::Xaml::Controls::Primitives::IRepeatButton,Windows::UI::Xaml::Controls::Primitives::IRepeatButton>(
              v140,
              (wchar_t *)L"VerticalLargeDecrease",
              0x15u,
              &spElementVerticalLargeDecrease.ptr_);
  v121 = updated;
  if ( updated < 0 )
    goto LABEL_196;
  ctl::WeakReferenceSourceNoThreadId::RegisterPtr(v86, v92);
  if ( spElementVerticalLargeDecrease.ptr_ )
    DirectUI::TrackerTargetReference::Set(v92, spElementVerticalLargeDecrease.ptr_, 1u, 0);
  else
    DirectUI::TrackerTargetReference::Clear(v92, 1u, 0);
  if ( v92->m_value )
  {
    WindowsDeleteString(strAutomationName._hstring);
    strAutomationName._hstring = 0;
    updated = DirectUI::DependencyObject::GetValueByKnownIndex(
                (DirectUI::DependencyObject *)((__int64)&v92->m_value[-79] & -(__int64)(v92->m_value != 0)),
                AutomationProperties_Name,
                &strAutomationName._hstring);
    v121 = updated;
    if ( updated < 0 )
      goto LABEL_196;
    if ( !strAutomationName._hstring )
    {
      v134 = DirectUI::DXamlCore::GetCurrent();
      WindowsDeleteString(0);
      strAutomationName._hstring = 0;
      updated = DirectUI::DXamlCore::GetLocalizedResourceString(v134, 0x14B4u, &strAutomationName._hstring);
      v121 = updated;
      if ( updated < 0 )
        goto LABEL_196;
      updated = DirectUI::DependencyObject::SetValueByKnownIndex(
                  (DirectUI::DependencyObject *)((__int64)&v92->m_value[-79] & -(__int64)(v92->m_value != 0)),
                  AutomationProperties_Name,
                  strAutomationName._hstring);
      v121 = updated;
      if ( updated < 0 )
        goto LABEL_196;
    }
  }
  v31 = spElementVerticalSmallDecrease.ptr_;
  if ( spElementVerticalSmallDecrease.ptr_ )
  {
    spElementVerticalSmallDecrease.ptr_ = 0;
    v31->Release(v31);
  }
  updated = DirectUI::ScrollBar::GetTemplateChildHelper<Windows::UI::Xaml::Controls::Primitives::IRepeatButton,Windows::UI::Xaml::Controls::Primitives::IRepeatButton>(
              v140,
              (wchar_t *)L"VerticalSmallDecrease",
              0x15u,
              &spElementVerticalSmallDecrease.ptr_);
  v121 = updated;
  if ( updated < 0 )
    goto LABEL_196;
  ctl::WeakReferenceSourceNoThreadId::RegisterPtr(v86, v96);
  if ( spElementVerticalSmallDecrease.ptr_ )
    DirectUI::TrackerTargetReference::Set(v96, spElementVerticalSmallDecrease.ptr_, 1u, 0);
  else
    DirectUI::TrackerTargetReference::Clear(v96, 1u, 0);
  if ( v96->m_value )
  {
    WindowsDeleteString(strAutomationName._hstring);
    strAutomationName._hstring = 0;
    updated = DirectUI::DependencyObject::GetValueByKnownIndex(
                (DirectUI::DependencyObject *)((__int64)&v96->m_value[-79] & -(__int64)(v96->m_value != 0)),
                AutomationProperties_Name,
                &strAutomationName._hstring);
    v121 = updated;
    if ( updated < 0 )
      goto LABEL_196;
    if ( !strAutomationName._hstring )
    {
      v132 = DirectUI::DXamlCore::GetCurrent();
      WindowsDeleteString(0);
      strAutomationName._hstring = 0;
      updated = DirectUI::DXamlCore::GetLocalizedResourceString(v132, 0x14B5u, &strAutomationName._hstring);
      v121 = updated;
      if ( updated < 0 )
        goto LABEL_196;
      updated = DirectUI::DependencyObject::SetValueByKnownIndex(
                  (DirectUI::DependencyObject *)((__int64)&v96->m_value[-79] & -(__int64)(v96->m_value != 0)),
                  AutomationProperties_Name,
                  strAutomationName._hstring);
      v121 = updated;
      if ( updated < 0 )
        goto LABEL_196;
    }
  }
  v32 = spElementVerticalThumb.ptr_;
  if ( spElementVerticalThumb.ptr_ )
  {
    spElementVerticalThumb.ptr_ = 0;
    v32->Release(v32);
  }
  updated = DirectUI::ScrollBar::GetTemplateChildHelper<Windows::UI::Xaml::Controls::Primitives::IThumb,Windows::UI::Xaml::Controls::Primitives::IThumb>(
              v140,
              (wchar_t *)L"VerticalThumb",
              0xDu,
              &spElementVerticalThumb.ptr_);
  v121 = updated;
  if ( updated < 0 )
    goto LABEL_196;
  ctl::WeakReferenceSourceNoThreadId::RegisterPtr(v86, v90);
  if ( spElementVerticalThumb.ptr_ )
    DirectUI::TrackerTargetReference::Set(v90, spElementVerticalThumb.ptr_, 1u, 0);
  else
    DirectUI::TrackerTargetReference::Clear(v90, 1u, 0);
  if ( v90->m_value )
  {
    WindowsDeleteString(strAutomationName._hstring);
    strAutomationName._hstring = 0;
    updated = DirectUI::DependencyObject::GetValueByKnownIndex(
                (DirectUI::DependencyObject *)((__int64)&v90->m_value[-67] & -(__int64)(v90->m_value != 0)),
                AutomationProperties_Name,
                &strAutomationName._hstring);
    v121 = updated;
    if ( updated < 0 )
      goto LABEL_196;
    if ( !strAutomationName._hstring )
    {
      v136 = DirectUI::DXamlCore::GetCurrent();
      WindowsDeleteString(0);
      strAutomationName._hstring = 0;
      updated = DirectUI::DXamlCore::GetLocalizedResourceString(v136, 0x14B6u, &strAutomationName._hstring);
      v121 = updated;
      if ( updated < 0 )
        goto LABEL_196;
      updated = DirectUI::DependencyObject::SetValueByKnownIndex(
                  (DirectUI::DependencyObject *)((__int64)&v90->m_value[-67] & -(__int64)(v90->m_value != 0)),
                  AutomationProperties_Name,
                  strAutomationName._hstring);
      v121 = updated;
      if ( updated < 0 )
        goto LABEL_196;
    }
  }
  v33 = spElementHorizontalPanningRoot.ptr_;
  if ( spElementHorizontalPanningRoot.ptr_ )
  {
    spElementHorizontalPanningRoot.ptr_ = 0;
    v33->Release(v33);
  }
  updated = DirectUI::ScrollBar::GetTemplateChildHelper<Windows::UI::Xaml::IFrameworkElement,Windows::UI::Xaml::IFrameworkElement>(
              v140,
              (wchar_t *)L"HorizontalPanningRoot",
              0x15u,
              &spElementHorizontalPanningRoot.ptr_);
  v121 = updated;
  if ( updated < 0 )
    goto LABEL_196;
  ctl::WeakReferenceSourceNoThreadId::RegisterPtr(v86, v117);
  DirectUI::TrackerPtr<Windows::UI::Xaml::Interop::IBindableVector,1,0>::Set<Windows::UI::Xaml::Interop::IBindableVector>(
    (DirectUI::TrackerPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,1,0> *)v117,
    (Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *> *)spElementHorizontalPanningRoot.ptr_);
  v34 = spElementHorizontalPanningThumb.ptr_;
  if ( spElementHorizontalPanningThumb.ptr_ )
  {
    spElementHorizontalPanningThumb.ptr_ = 0;
    v34->Release(v34);
  }
  updated = DirectUI::ScrollBar::GetTemplateChildHelper<Windows::UI::Xaml::IFrameworkElement,Windows::UI::Xaml::IFrameworkElement>(
              v140,
              (wchar_t *)L"HorizontalPanningThumb",
              0x16u,
              &spElementHorizontalPanningThumb.ptr_);
  v121 = updated;
  if ( updated < 0 )
    goto LABEL_196;
  ctl::WeakReferenceSourceNoThreadId::RegisterPtr(v86, p_m_initialVal);
  DirectUI::TrackerPtr<Windows::UI::Xaml::Interop::IBindableVector,1,0>::Set<Windows::UI::Xaml::Interop::IBindableVector>(
    (DirectUI::TrackerPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,1,0> *)p_m_initialVal,
    (Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *> *)spElementHorizontalPanningThumb.ptr_);
  v35 = spElementVerticalPanningRoot.ptr_;
  if ( spElementVerticalPanningRoot.ptr_ )
  {
    spElementVerticalPanningRoot.ptr_ = 0;
    v35->Release(v35);
  }
  updated = DirectUI::ScrollBar::GetTemplateChildHelper<Windows::UI::Xaml::IFrameworkElement,Windows::UI::Xaml::IFrameworkElement>(
              v140,
              (wchar_t *)L"VerticalPanningRoot",
              0x13u,
              &spElementVerticalPanningRoot.ptr_);
  v121 = updated;
  if ( updated < 0 )
    goto LABEL_196;
  ctl::WeakReferenceSourceNoThreadId::RegisterPtr(v86, v119);
  DirectUI::TrackerPtr<Windows::UI::Xaml::Interop::IBindableVector,1,0>::Set<Windows::UI::Xaml::Interop::IBindableVector>(
    (DirectUI::TrackerPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,1,0> *)v119,
    (Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *> *)spElementVerticalPanningRoot.ptr_);
  v36 = spElementVerticalPanningThumb.ptr_;
  if ( spElementVerticalPanningThumb.ptr_ )
  {
    spElementVerticalPanningThumb.ptr_ = 0;
    v36->Release(v36);
  }
  updated = DirectUI::ScrollBar::GetTemplateChildHelper<Windows::UI::Xaml::IFrameworkElement,Windows::UI::Xaml::IFrameworkElement>(
              v140,
              (wchar_t *)L"VerticalPanningThumb",
              0x14u,
              &spElementVerticalPanningThumb.ptr_);
  v121 = updated;
  if ( updated < 0 )
    goto LABEL_196;
  ctl::WeakReferenceSourceNoThreadId::RegisterPtr(v86, &p_m_tpElementHorizontalTemplate->m_trackerReference);
  DirectUI::TrackerPtr<Windows::UI::Xaml::Interop::IBindableVector,1,0>::Set<Windows::UI::Xaml::Interop::IBindableVector>(
    p_m_tpElementHorizontalTemplate,
    (Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *> *)spElementVerticalPanningThumb.ptr_);
  if ( v89->m_value || v90->m_value )
  {
    FailFast = (DirectUI::DXamlCore *)XcpAllocation::OSMemoryAllocateFailFast(0x28u);
    if ( FailFast )
    {
      v87[0] = (DirectUI::TrackerTargetReference *)DirectUI::ScrollBar::OnThumbDragStarted;
      LODWORD(v87[1]) = 0;
      ctl::implements<Windows::ApplicationModel::ISuspendingEventArgs>::implements<Windows::ApplicationModel::ISuspendingEventArgs>((ctl::implements<Windows::UI::Xaml::Data::ISupportIncrementalLoading> *)FailFast);
      v37 = v140;
      *(_QWORD *)v38 = DirectUI::ClassMemberEventHandler<DirectUI::ScrollBar,Windows::UI::Xaml::Controls::Primitives::IScrollBar,Windows::UI::Xaml::Controls::Primitives::IDragStartedEventHandler,IInspectable,Windows::UI::Xaml::Controls::Primitives::IDragStartedEventArgs>::`vftable';
      *(_OWORD *)(v38 + 24) = *(_OWORD *)v87;
      ctl::as_weakref(
        (IWeakReference **)(v38 + 16),
        (IInspectable *)((unsigned __int64)v86 & ((unsigned __int128)-(__int128)(unsigned __int64)v37 >> 64)));
      v3 = FailFast;
    }
    v126 = (DirectUI::DXamlCore *)XcpAllocation::OSMemoryAllocateFailFast(0x28u);
    if ( v126 )
    {
      v87[0] = (DirectUI::TrackerTargetReference *)DirectUI::ScrollBar::OnThumbDragDelta;
      LODWORD(v87[1]) = 0;
      ctl::implements<Windows::ApplicationModel::ISuspendingEventArgs>::implements<Windows::ApplicationModel::ISuspendingEventArgs>((ctl::implements<Windows::UI::Xaml::Data::ISupportIncrementalLoading> *)v126);
      v74 = v140;
      *(_QWORD *)v75 = DirectUI::ClassMemberEventHandler<DirectUI::ScrollBar,Windows::UI::Xaml::Controls::Primitives::IScrollBar,Windows::UI::Xaml::Controls::Primitives::IDragDeltaEventHandler,IInspectable,Windows::UI::Xaml::Controls::Primitives::IDragDeltaEventArgs>::`vftable';
      *(_OWORD *)(v75 + 24) = *(_OWORD *)v87;
      ctl::as_weakref(
        (IWeakReference **)(v75 + 16),
        (IInspectable *)((unsigned __int64)v86 & ((unsigned __int128)-(__int128)(unsigned __int64)v74 >> 64)));
      v6 = v126;
    }
    v127 = (DirectUI::DXamlCore *)XcpAllocation::OSMemoryAllocateFailFast(0x28u);
    if ( v127 )
    {
      v87[0] = (DirectUI::TrackerTargetReference *)DirectUI::ScrollBar::OnThumbDragCompleted;
      LODWORD(v87[1]) = 0;
      ctl::implements<Windows::ApplicationModel::ISuspendingEventArgs>::implements<Windows::ApplicationModel::ISuspendingEventArgs>((ctl::implements<Windows::UI::Xaml::Data::ISupportIncrementalLoading> *)v127);
      v52 = v140;
      *(_QWORD *)v53 = DirectUI::ClassMemberEventHandler<DirectUI::ScrollBar,Windows::UI::Xaml::Controls::Primitives::IScrollBar,Windows::UI::Xaml::Controls::Primitives::IDragCompletedEventHandler,IInspectable,Windows::UI::Xaml::Controls::Primitives::IDragCompletedEventArgs>::`vftable';
      *(_OWORD *)(v53 + 24) = *(_OWORD *)v87;
      ctl::as_weakref(
        (IWeakReference **)(v53 + 16),
        (IInspectable *)((unsigned __int64)v86 & ((unsigned __int128)-(__int128)(unsigned __int64)v52 >> 64)));
      v7 = v127;
    }
    if ( v89->m_value )
    {
      updated = ((__int64 (__fastcall *)(IUnknown *, DirectUI::DXamlCore *, DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::Primitives::IRepeatButton,1,0> *))v89->m_value->__vftable[2].AddRef)(
                  v89->m_value,
                  v3,
                  &this->m_tpElementHorizontalLargeIncrease);
      v121 = updated;
      if ( updated < 0 )
        goto LABEL_196;
      v54 = (__int64)v89->m_value;
      if ( !v89->m_value )
        v54 = 536;
      updated = (*(__int64 (__fastcall **)(__int64, DirectUI::DXamlCore *, $5B200F22DE067370BF14E8C6BF81764F *))(*(_QWORD *)v54 + 72LL))(
                  v54,
                  v6,
                  &this->m_tpElementHorizontalLargeIncrease.m_trackerReference.8);
      v121 = updated;
      if ( updated < 0 )
        goto LABEL_196;
      v55 = (__int64)v89->m_value;
      if ( !v89->m_value )
        v55 = 536;
      updated = (*(__int64 (__fastcall **)(__int64, DirectUI::DXamlCore *, char *))(*(_QWORD *)v55 + 88LL))(
                  v55,
                  v7,
                  (char *)&this->m_tpElementHorizontalLargeIncrease.m_trackerReference + 16);
      v121 = updated;
      if ( updated < 0 )
        goto LABEL_196;
      v56 = (__int64)&v89->m_value[8];
      if ( !v89->m_value )
        v56 = 600;
      *(_BYTE *)v56 = 1;
    }
    if ( v90->m_value )
    {
      updated = ((__int64 (__fastcall *)(IUnknown *, DirectUI::DXamlCore *, $5B200F22DE067370BF14E8C6BF81764F *))v90->m_value->__vftable[2].AddRef)(
                  v90->m_value,
                  v3,
                  &this->m_tpElementHorizontalSmallIncrease.m_trackerReference.8);
      v121 = updated;
      if ( updated < 0 )
        goto LABEL_196;
      v39 = (__int64)v90->m_value;
      if ( !v90->m_value )
        v39 = 536;
      updated = (*(__int64 (__fastcall **)(__int64, DirectUI::DXamlCore *, char *))(*(_QWORD *)v39 + 72LL))(
                  v39,
                  v6,
                  (char *)&this->m_tpElementHorizontalSmallIncrease.m_trackerReference + 16);
      v121 = updated;
      if ( updated < 0 )
        goto LABEL_196;
      v40 = (__int64)v90->m_value;
      if ( !v90->m_value )
        v40 = 536;
      updated = (*(__int64 (__fastcall **)(__int64, DirectUI::DXamlCore *, DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::Primitives::IRepeatButton,1,0> *))(*(_QWORD *)v40 + 88LL))(
                  v40,
                  v7,
                  &this->m_tpElementHorizontalSmallDecrease);
      v121 = updated;
      if ( updated < 0 )
        goto LABEL_196;
      v41 = (__int64)&v90->m_value[8];
      if ( !v90->m_value )
        v41 = 600;
      *(_BYTE *)v41 = 1;
    }
  }
  if ( v91->m_value || v92->m_value )
  {
    v128 = (DirectUI::DXamlCore *)XcpAllocation::OSMemoryAllocateFailFast(0x28u);
    if ( v128 )
    {
      v87[0] = (DirectUI::TrackerTargetReference *)DirectUI::ScrollBar::LargeDecrement;
      LODWORD(v87[1]) = 0;
      ctl::implements<Windows::ApplicationModel::ISuspendingEventArgs>::implements<Windows::ApplicationModel::ISuspendingEventArgs>((ctl::implements<Windows::UI::Xaml::Data::ISupportIncrementalLoading> *)v128);
      *(_QWORD *)v42 = DirectUI::ClassMemberEventHandler<DirectUI::ScrollBar,Windows::UI::Xaml::Controls::Primitives::IScrollBar,Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs>::`vftable';
      v43 = v140;
      *(_OWORD *)(v42 + 24) = *(_OWORD *)v87;
      ctl::as_weakref(
        (IWeakReference **)(v42 + 16),
        (IInspectable *)((unsigned __int64)v86 & ((unsigned __int128)-(__int128)(unsigned __int64)v43 >> 64)));
      v9 = v128;
    }
    if ( v91->m_value )
    {
      updated = ((__int64 (__fastcall *)(IUnknown *, DirectUI::DXamlCore *, DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::Primitives::IRepeatButton,1,0> *))v91->m_value[-8].__vftable[4].Release)(
                  &v91->m_value[-8],
                  v9,
                  &this->m_tpElementHorizontalLargeDecrease);
      v121 = updated;
      if ( updated < 0 )
        goto LABEL_196;
      v79 = (__int64)&v91->m_value[1].__vftable + 2;
      if ( !v91->m_value )
        v79 = 642;
      *(_BYTE *)v79 = 1;
    }
    if ( v92->m_value )
    {
      updated = ((__int64 (__fastcall *)(IUnknown *, DirectUI::DXamlCore *, $5B200F22DE067370BF14E8C6BF81764F *))v92->m_value[-8].__vftable[4].Release)(
                  &v92->m_value[-8],
                  v9,
                  &this->m_tpElementHorizontalSmallDecrease.m_trackerReference.8);
      v121 = updated;
      if ( updated < 0 )
        goto LABEL_196;
      v44 = (__int64)&v92->m_value[1].__vftable + 2;
      if ( !v92->m_value )
        v44 = 642;
      *(_BYTE *)v44 = 1;
    }
  }
  if ( v93->m_value || p_m_pDataContextChangedSource->m_value )
  {
    v129 = (DirectUI::DXamlCore *)XcpAllocation::OSMemoryAllocateFailFast(0x28u);
    if ( v129 )
    {
      v87[0] = (DirectUI::TrackerTargetReference *)DirectUI::ScrollBar::LargeIncrement;
      LODWORD(v87[1]) = 0;
      ctl::implements<Windows::ApplicationModel::ISuspendingEventArgs>::implements<Windows::ApplicationModel::ISuspendingEventArgs>((ctl::implements<Windows::UI::Xaml::Data::ISupportIncrementalLoading> *)v129);
      *(_QWORD *)v80 = DirectUI::ClassMemberEventHandler<DirectUI::ScrollBar,Windows::UI::Xaml::Controls::Primitives::IScrollBar,Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs>::`vftable';
      v81 = v140;
      *(_OWORD *)(v80 + 24) = *(_OWORD *)v87;
      ctl::as_weakref(
        (IWeakReference **)(v80 + 16),
        (IInspectable *)((unsigned __int64)v86 & ((unsigned __int128)-(__int128)(unsigned __int64)v81 >> 64)));
      v8 = v129;
    }
    if ( v93->m_value )
    {
      updated = ((__int64 (__fastcall *)(IUnknown *, DirectUI::DXamlCore *, $5B200F22DE067370BF14E8C6BF81764F *))v93->m_value[-8].__vftable[4].Release)(
                  &v93->m_value[-8],
                  v8,
                  &this->m_tpElementHorizontalLargeDecrease.m_trackerReference.8);
      v121 = updated;
      if ( updated < 0 )
        goto LABEL_196;
      v45 = (__int64)&v93->m_value[1].__vftable + 2;
      if ( !v93->m_value )
        v45 = 642;
      *(_BYTE *)v45 = 1;
    }
    if ( p_m_pDataContextChangedSource->m_value )
    {
      updated = ((__int64 (__fastcall *)(IUnknown *, DirectUI::DXamlCore *, char *))p_m_pDataContextChangedSource->m_value[-8].__vftable[4].Release)(
                  &p_m_pDataContextChangedSource->m_value[-8],
                  v8,
                  (char *)&this->m_tpElementHorizontalSmallDecrease.m_trackerReference + 16);
      v121 = updated;
      if ( updated < 0 )
        goto LABEL_196;
      v46 = (__int64)&p_m_pDataContextChangedSource->m_value[1].__vftable + 2;
      if ( !p_m_pDataContextChangedSource->m_value )
        v46 = 642;
      *(_BYTE *)v46 = 1;
    }
  }
  if ( v95->m_value || v96->m_value )
  {
    v133 = (DirectUI::DXamlCore *)XcpAllocation::OSMemoryAllocateFailFast(0x28u);
    if ( v133 )
    {
      v87[0] = (DirectUI::TrackerTargetReference *)DirectUI::ScrollBar::SmallDecrement;
      LODWORD(v87[1]) = 0;
      ctl::implements<Windows::ApplicationModel::ISuspendingEventArgs>::implements<Windows::ApplicationModel::ISuspendingEventArgs>((ctl::implements<Windows::UI::Xaml::Data::ISupportIncrementalLoading> *)v133);
      *(_QWORD *)v76 = DirectUI::ClassMemberEventHandler<DirectUI::ScrollBar,Windows::UI::Xaml::Controls::Primitives::IScrollBar,Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs>::`vftable';
      v77 = v140;
      *(_OWORD *)(v76 + 24) = *(_OWORD *)v87;
      ctl::as_weakref(
        (IWeakReference **)(v76 + 16),
        (IInspectable *)((unsigned __int64)v86 & ((unsigned __int128)-(__int128)(unsigned __int64)v77 >> 64)));
      v10 = v133;
    }
    if ( v95->m_value )
    {
      updated = ((__int64 (__fastcall *)(IUnknown *, DirectUI::DXamlCore *, char *))v95->m_value[-8].__vftable[4].Release)(
                  &v95->m_value[-8],
                  v10,
                  (char *)&this->m_tpElementHorizontalLargeDecrease.m_trackerReference + 16);
      v121 = updated;
      if ( updated < 0 )
        goto LABEL_196;
      v78 = (__int64)&v95->m_value[1].__vftable + 2;
      if ( !v95->m_value )
        v78 = 642;
      *(_BYTE *)v78 = 1;
    }
    if ( v96->m_value )
    {
      updated = ((__int64 (__fastcall *)(IUnknown *, DirectUI::DXamlCore *, DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::Primitives::IThumb,1,0> *))v96->m_value[-8].__vftable[4].Release)(
                  &v96->m_value[-8],
                  v10,
                  &this->m_tpElementHorizontalThumb);
      v121 = updated;
      if ( updated < 0 )
        goto LABEL_196;
      v51 = (__int64)&v96->m_value[1].__vftable + 2;
      if ( !v96->m_value )
        v51 = 642;
      *(_BYTE *)v51 = 1;
    }
  }
  if ( !v97->m_value && !v98->m_value )
    goto LABEL_152;
  v130 = (DirectUI::DXamlCore *)XcpAllocation::OSMemoryAllocateFailFast(0x28u);
  if ( v130 )
  {
    v87[0] = (DirectUI::TrackerTargetReference *)DirectUI::ScrollBar::SmallIncrement;
    LODWORD(v87[1]) = 0;
    ctl::implements<Windows::ApplicationModel::ISuspendingEventArgs>::implements<Windows::ApplicationModel::ISuspendingEventArgs>((ctl::implements<Windows::UI::Xaml::Data::ISupportIncrementalLoading> *)v130);
    *(_QWORD *)v47 = DirectUI::ClassMemberEventHandler<DirectUI::ScrollBar,Windows::UI::Xaml::Controls::Primitives::IScrollBar,Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs>::`vftable';
    v48 = v140;
    *(_OWORD *)(v47 + 24) = *(_OWORD *)v87;
    ctl::as_weakref(
      (IWeakReference **)(v47 + 16),
      (IInspectable *)((unsigned __int64)v86 & ((unsigned __int128)-(__int128)(unsigned __int64)v48 >> 64)));
    v1 = v130;
  }
  if ( v97->m_value )
  {
    updated = ((__int64 (__fastcall *)(IUnknown *, DirectUI::DXamlCore *, DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::Primitives::IRepeatButton,1,0> *))v97->m_value[-8].__vftable[4].Release)(
                &v97->m_value[-8],
                v1,
                &this->m_tpElementHorizontalSmallIncrease);
    v121 = updated;
    if ( updated < 0 )
      goto LABEL_196;
    v49 = (__int64)&v97->m_value[1].__vftable + 2;
    if ( !v97->m_value )
      v49 = 642;
    *(_BYTE *)v49 = 1;
  }
  if ( !v98->m_value )
    goto LABEL_152;
  updated = ((__int64 (__fastcall *)(IUnknown *, DirectUI::DXamlCore *, $5B200F22DE067370BF14E8C6BF81764F *))v98->m_value[-8].__vftable[4].Release)(
              &v98->m_value[-8],
              v1,
              &this->m_tpElementHorizontalThumb.m_trackerReference.8);
  v121 = updated;
  if ( updated < 0 )
  {
LABEL_196:
    OnFailure_2990_(updated);
    goto $Cleanup_2541;
  }
  v50 = (__int64)&v98->m_value[1].__vftable + 2;
  if ( !v98->m_value )
    v50 = 642;
  *(_BYTE *)v50 = 1;
LABEL_152:
  updated = DirectUI::ScrollBar::UpdateScrollBarVisibility(v140);
  v121 = updated;
  if ( updated < 0 )
    goto LABEL_196;
  BYTE2(this->DirectUI::ScrollBarGenerated::DirectUI::RangeBase::DirectUI::RangeBaseGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IUIElement5,DirectUI::UIElementGenerated>::m_forwarder.DirectUI::ScrollBarGenerated::DirectUI::RangeBase::DirectUI::RangeBaseGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IUIElement5,DirectUI::UIElementGenerated>::__vftable) = 0;
  updated = ((__int64 (__fastcall *)(DirectUI::TrackerPtr<Windows::UI::Xaml::IFrameworkElement,1,0> *, _QWORD))this[-1].m_tpElementVerticalTemplate.m_trackerReference.m_value[94].__vftable)(
              &this[-1].m_tpElementVerticalTemplate,
              0);
  v121 = updated;
  if ( updated < 0 )
    goto LABEL_196;
$Cleanup_2541:
  v57 = spElementHorizontalThumb.ptr_;
  BYTE2(this->DirectUI::ScrollBarGenerated::DirectUI::RangeBase::DirectUI::RangeBaseGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IUIElement5,DirectUI::UIElementGenerated>::m_forwarder.DirectUI::ScrollBarGenerated::DirectUI::RangeBase::DirectUI::RangeBaseGenerated::DirectUI::Control::DirectUI::ControlGenerated::DirectUI::FrameworkElement::DirectUI::FrameworkElementGenerated::DirectUI::UIElement::DirectUI::UIElementGenerated::ctl::forwarder_holder<Windows::UI::Xaml::IUIElement5,DirectUI::UIElementGenerated>::__vftable) = 0;
  if ( v57 )
  {
    spElementHorizontalThumb.ptr_ = 0;
    v57->Release(v57);
  }
  v58 = spElementVerticalThumb.ptr_;
  if ( spElementVerticalThumb.ptr_ )
  {
    spElementVerticalThumb.ptr_ = 0;
    v58->Release(v58);
  }
  v59 = spElementVerticalSmallDecrease.ptr_;
  if ( spElementVerticalSmallDecrease.ptr_ )
  {
    spElementVerticalSmallDecrease.ptr_ = 0;
    v59->Release(v59);
  }
  v60 = spElementVerticalSmallIncrease.ptr_;
  if ( spElementVerticalSmallIncrease.ptr_ )
  {
    spElementVerticalSmallIncrease.ptr_ = 0;
    v60->Release(v60);
  }
  v61 = spElementVerticalLargeDecrease.ptr_;
  if ( spElementVerticalLargeDecrease.ptr_ )
  {
    spElementVerticalLargeDecrease.ptr_ = 0;
    v61->Release(v61);
  }
  v62 = spElementVerticalLargeIncrease.ptr_;
  if ( spElementVerticalLargeIncrease.ptr_ )
  {
    spElementVerticalLargeIncrease.ptr_ = 0;
    v62->Release(v62);
  }
  v63 = spElementHorizontalSmallDecrease.ptr_;
  if ( spElementHorizontalSmallDecrease.ptr_ )
  {
    spElementHorizontalSmallDecrease.ptr_ = 0;
    v63->Release(v63);
  }
  v64 = spElementHorizontalSmallIncrease.ptr_;
  if ( spElementHorizontalSmallIncrease.ptr_ )
  {
    spElementHorizontalSmallIncrease.ptr_ = 0;
    v64->Release(v64);
  }
  v65 = spElementHorizontalLargeDecrease.ptr_;
  if ( spElementHorizontalLargeDecrease.ptr_ )
  {
    spElementHorizontalLargeDecrease.ptr_ = 0;
    v65->Release(v65);
  }
  v66 = spElementHorizontalLargeIncrease.ptr_;
  if ( spElementHorizontalLargeIncrease.ptr_ )
  {
    spElementHorizontalLargeIncrease.ptr_ = 0;
    v66->Release(v66);
  }
  v67 = spElementVerticalPanningThumb.ptr_;
  if ( spElementVerticalPanningThumb.ptr_ )
  {
    spElementVerticalPanningThumb.ptr_ = 0;
    v67->Release(v67);
  }
  v68 = spElementVerticalPanningRoot.ptr_;
  if ( spElementVerticalPanningRoot.ptr_ )
  {
    spElementVerticalPanningRoot.ptr_ = 0;
    v68->Release(v68);
  }
  v69 = spElementHorizontalPanningThumb.ptr_;
  if ( spElementHorizontalPanningThumb.ptr_ )
  {
    spElementHorizontalPanningThumb.ptr_ = 0;
    v69->Release(v69);
  }
  v70 = spElementHorizontalPanningRoot.ptr_;
  if ( spElementHorizontalPanningRoot.ptr_ )
  {
    spElementHorizontalPanningRoot.ptr_ = 0;
    v70->Release(v70);
  }
  v71 = spElementVerticalTemplate.ptr_;
  if ( spElementVerticalTemplate.ptr_ )
  {
    spElementVerticalTemplate.ptr_ = 0;
    v71->Release(v71);
  }
  v72 = spElementHorizontalTemplate.ptr_;
  if ( spElementHorizontalTemplate.ptr_ )
  {
    spElementHorizontalTemplate.ptr_ = 0;
    v72->Release(v72);
  }
  if ( v10 )
    ((void (__fastcall *)(DirectUI::DXamlCore *))v10->AddToReferenceTrackingList)(v10);
  if ( v1 )
    ((void (__fastcall *)(DirectUI::DXamlCore *))v1->AddToReferenceTrackingList)(v1);
  if ( v9 )
    ((void (__fastcall *)(DirectUI::DXamlCore *))v9->AddToReferenceTrackingList)(v9);
  if ( v8 )
    ((void (__fastcall *)(DirectUI::DXamlCore *))v8->AddToReferenceTrackingList)(v8);
  if ( v7 )
    ((void (__fastcall *)(DirectUI::DXamlCore *))v7->AddToReferenceTrackingList)(v7);
  if ( v6 )
    ((void (__fastcall *)(DirectUI::DXamlCore *))v6->AddToReferenceTrackingList)(v6);
  if ( v3 )
    ((void (__fastcall *)(DirectUI::DXamlCore *))v3->AddToReferenceTrackingList)(v3);
  if ( strAutomationName._hstring )
    WindowsDeleteString(strAutomationName._hstring);
  return v121;
}

```

## disassembly

```asm
0x180381280  mov     [rsp-8+arg_0], this
0x180381285  push    rbp
0x180381286  push    rbx
0x180381287  push    rsi
0x180381288  push    rdi
0x180381289  push    r12
0x18038128b  push    r13
0x18038128d  push    r14
0x18038128f  push    r15
0x180381291  lea     rbp, [rsp-48h]
0x180381296  sub     rsp, 148h
0x18038129d  xor     ebx, ebx
0x18038129f  mov     [rbp+80h+strAutomationName._hstring], 0
0x1803812aa  lea     rax, [this-168h]
0x1803812b1  mov     [rbp+80h+spElementHorizontalTemplate.ptr_], rbx
0x1803812b5  mov     [rbp+80h+arg_18], rax
0x1803812bc  mov     rdx, this
0x1803812bf  mov     byte ptr [rax+25Ah], 1
0x1803812c6  xor     r14d, r14d
0x1803812c9  lea     rax, [this+178h]
0x1803812d0  mov     [rbp+80h+spElementVerticalTemplate.ptr_], rbx
0x1803812d4  mov     this, [rax]
0x1803812d7  xor     r12d, r12d
0x1803812da  xor     r13d, r13d
0x1803812dd  mov     [rbp+80h+spElementHorizontalPanningRoot.ptr_], rbx
0x1803812e1  xor     esi, esi
0x1803812e3  mov     [rbp+80h+spElementHorizontalPanningThumb.ptr_], rbx
0x1803812e7  xor     r15d, r15d
0x1803812ea  mov     [rbp+80h+spElementVerticalPanningRoot.ptr_], rbx
0x1803812ee  xor     edi, edi
0x1803812f0  mov     [rbp+80h+spElementVerticalPanningThumb.ptr_], rbx
0x1803812f4  mov     [rbp+80h+spElementHorizontalLargeIncrease.ptr_], rbx
0x1803812f8  mov     [rbp+80h+spElementHorizontalLargeDecrease.ptr_], rbx
0x1803812fc  mov     [rbp+80h+spElementHorizontalSmallIncrease.ptr_], rbx
0x180381300  mov     [rbp+80h+spElementHorizontalSmallDecrease.ptr_], rbx
0x180381304  mov     [rbp+80h+spElementVerticalLargeIncrease.ptr_], rbx
0x180381308  mov     [rbp+80h+spElementVerticalLargeDecrease.ptr_], rbx
0x18038130c  mov     [rbp+80h+spElementVerticalSmallIncrease.ptr_], rbx
0x180381310  mov     [rbp+80h+spElementVerticalSmallDecrease.ptr_], rbx
0x180381314  mov     [rbp+80h+spElementVerticalThumb.ptr_], rbx
0x180381318  mov     [rbp+80h+spElementHorizontalThumb.ptr_], rbx
0x18038131c  mov     [rsp+180h+var_140], rax
0x180381321  test    this, this
0x180381324  jnz     loc_180382F88
0x18038132a  lea     rax, [rdx+130h]
0x180381331  mov     this, [rax]
0x180381334  mov     [rsp+180h+var_130], rax
0x180381339  test    this, this
0x18038133c  jnz     loc_180383129
0x180381342  lea     rax, [rdx+118h]
0x180381349  mov     this, [rax]
0x18038134c  mov     [rsp+180h+var_120], rax
0x180381351  test    this, this
0x180381354  jnz     loc_180383162
0x18038135a  lea     rax, [rdx+160h]
0x180381361  mov     this, [rax]
0x180381364  mov     [rsp+180h+var_110], rax
0x180381369  test    this, this
0x18038136c  jnz     loc_18038319B
0x180381372  lea     rax, [rdx+148h]
0x180381379  mov     this, [rax]
0x18038137c  mov     [rbp+80h+var_100], rax
0x180381380  test    this, this
0x180381383  jnz     loc_1803831D4
0x180381389  lea     rax, [rdx+208h]
0x180381390  mov     this, [rax]
0x180381393  mov     [rsp+180h+var_138], rax
0x180381398  test    this, this
0x18038139b  jnz     loc_18038320D
0x1803813a1  lea     rax, [rdx+1C0h]
0x1803813a8  mov     this, [rax]
0x1803813ab  mov     [rsp+180h+var_128], rax
0x1803813b0  test    this, this
0x1803813b3  jnz     loc_1803832CE
0x1803813b9  lea     rax, [rdx+1A8h]
0x1803813c0  mov     this, [rax]
0x1803813c3  mov     [rsp+180h+var_118], rax
0x1803813c8  test    this, this
0x1803813cb  jnz     loc_180383307
0x1803813d1  lea     rax, [rdx+1F0h]
0x1803813d8  mov     this, [rax]
0x1803813db  mov     [rsp+180h+var_108], rax
0x1803813e0  test    this, this
0x1803813e3  jnz     loc_180383340
0x1803813e9  lea     rax, [rdx+1D8h]
0x1803813f0  mov     this, [rax]
0x1803813f3  mov     [rbp+80h+var_F8], rax
0x1803813f7  test    this, this
0x1803813fa  jnz     loc_180383379
0x180381400  lea     rax, [rdx+100h]
0x180381407  xor     r8d, r8d; bForceLoopback
0x18038140a  mov     this, rax; this
0x18038140d  mov     [rbp+80h+pTrackerPtr], rax
0x180381411  mov     dl, 1; bEnsureTrackerTarget
0x180381413  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x180381418  mov     this, [rsp+180h+var_120]; this
0x18038141d  xor     r8d, r8d; bForceLoopback
0x180381420  mov     dl, 1; bEnsureTrackerTarget
0x180381422  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x180381427  mov     this, [rsp+180h+var_130]; this
0x18038142c  xor     r8d, r8d; bForceLoopback
0x18038142f  mov     dl, 1; bEnsureTrackerTarget
0x180381431  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x180381436  mov     this, [rbp+80h+var_100]; this
0x18038143a  xor     r8d, r8d; bForceLoopback
0x18038143d  mov     dl, 1; bEnsureTrackerTarget
0x18038143f  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x180381444  mov     this, [rsp+180h+var_110]; this
0x180381449  xor     r8d, r8d; bForceLoopback
0x18038144c  mov     dl, 1; bEnsureTrackerTarget
0x18038144e  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x180381453  mov     this, [rsp+180h+var_140]; this
0x180381458  xor     r8d, r8d; bForceLoopback
0x18038145b  mov     dl, 1; bEnsureTrackerTarget
0x18038145d  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x180381462  mov     rax, [rbp+80h+arg_0]
0x180381469  xor     r8d, r8d; bForceLoopback
0x18038146c  add     rax, 190h
0x180381472  mov     dl, 1; bEnsureTrackerTarget
0x180381474  mov     this, rax; this
0x180381477  mov     [rbp+80h+var_68], rax
0x18038147b  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x180381480  mov     this, [rsp+180h+var_118]; this
0x180381485  xor     r8d, r8d; bForceLoopback
0x180381488  mov     dl, 1; bEnsureTrackerTarget
0x18038148a  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18038148f  mov     this, [rsp+180h+var_128]; this
0x180381494  xor     r8d, r8d; bForceLoopback
0x180381497  mov     dl, 1; bEnsureTrackerTarget
0x180381499  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x18038149e  mov     this, [rbp+80h+var_F8]; this
0x1803814a2  xor     r8d, r8d; bForceLoopback
0x1803814a5  mov     dl, 1; bEnsureTrackerTarget
0x1803814a7  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x1803814ac  mov     this, [rsp+180h+var_138]; this
0x1803814b1  xor     r8d, r8d; bForceLoopback
0x1803814b4  mov     dl, 1; bEnsureTrackerTarget
0x1803814b6  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x1803814bb  mov     this, [rsp+180h+var_108]; this
0x1803814c0  xor     r8d, r8d; bForceLoopback
0x1803814c3  mov     dl, 1; bEnsureTrackerTarget
0x1803814c5  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x1803814ca  mov     rax, [rbp+80h+arg_0]
0x1803814d1  xor     r8d, r8d; bForceLoopback
0x1803814d4  add     rax, 220h
0x1803814da  mov     dl, 1; bEnsureTrackerTarget
0x1803814dc  mov     this, rax; this
0x1803814df  mov     [rbp+80h+var_60], rax
0x1803814e3  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x1803814e8  mov     rax, [rbp+80h+arg_0]
0x1803814ef  xor     r8d, r8d; bForceLoopback
0x1803814f2  add     rax, 238h
0x1803814f8  mov     dl, 1; bEnsureTrackerTarget
0x1803814fa  mov     this, rax; this
0x1803814fd  mov     [rbp+80h+var_58], rax
0x180381501  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x180381506  mov     rax, [rbp+80h+arg_0]
0x18038150d  xor     r8d, r8d; bForceLoopback
0x180381510  add     rax, 250h
0x180381516  mov     dl, 1; bEnsureTrackerTarget
0x180381518  mov     this, rax; this
0x18038151b  mov     [rbp+80h+var_50], rax
0x18038151f  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x180381524  mov     rax, [rbp+80h+arg_0]
0x18038152b  xor     r8d, r8d; bForceLoopback
0x18038152e  add     rax, 268h
0x180381534  mov     dl, 1; bEnsureTrackerTarget
0x180381536  mov     this, rax; this
0x180381539  mov     [rsp+180h+var_150], rax
0x18038153e  call    ?Clear@TrackerTargetReference@DirectUI@@IEAAKEE@Z; DirectUI::TrackerTargetReference::Clear(uchar,uchar)
0x180381543  mov     this, [rbp+80h+arg_0]; this
0x18038154a  call    ?OnApplyTemplate@Control@DirectUI@@UEAAJXZ; DirectUI::Control::OnApplyTemplate(void)
0x18038154f  mov     dword ptr [rbp+80h+arg_8], eax
0x180381555  test    eax, eax
0x180381557  js      loc_18038368A
0x18038155d  mov     this, [rbp+80h+spElementHorizontalTemplate.ptr_]
0x180381561  test    this, this
0x180381564  jz      short loc_180381576
0x180381566  mov     [rbp+80h+spElementHorizontalTemplate.ptr_], rbx
0x18038156a  mov     rax, [this]
0x18038156d  mov     rax, [rax+10h]
0x180381571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180381576  mov     this, [rbp+80h+arg_18]; this
0x18038157d  lea     r9, [rbp+80h+spElementHorizontalTemplate]; ppReference
0x180381581  mov     r8d, 0Eh; cName
0x180381587  lea     rdx, aHorizontalroot; "HorizontalRoot"
0x18038158e  call    ??$GetTemplateChildHelper@UIFrameworkElement@Xaml@UI@Windows@@U1234@@ScrollBar@DirectUI@@AEAAJPEAG_KPEAPEAUIFrameworkElement@Xaml@UI@Windows@@@Z; DirectUI::ScrollBar::GetTemplateChildHelper<Windows::UI::Xaml::IFrameworkElement,Windows::UI::Xaml::IFrameworkElement>(ushort *,unsigned __int64,Windows::UI::Xaml::IFrameworkElement * *)
0x180381593  mov     dword ptr [rbp+80h+arg_8], eax
0x180381599  test    eax, eax
0x18038159b  js      loc_18038367E
0x1803815a1  mov     rax, [rbp+80h+arg_0]
0x1803815a8  mov     rdx, [rbp+80h+pTrackerPtr]; pTrackerPtr
0x1803815ac  add     rax, 0FFFFFFFFFFFFFEA0h
0x1803815b2  mov     this, rax; this
0x1803815b5  mov     [rsp+180h+var_160], rax
0x1803815ba  call    ?RegisterPtr@WeakReferenceSourceNoThreadId@ctl@@AEAAXQEAVTrackerTargetReference@DirectUI@@@Z; ctl::WeakReferenceSourceNoThreadId::RegisterPtr(DirectUI::TrackerTargetReference * const)
0x1803815bf  mov     rdx, [rbp+80h+spElementHorizontalTemplate.ptr_]; ptr
0x1803815c3  mov     this, [rbp+80h+pTrackerPtr]; this
0x1803815c7  call    ??$Set@UIBindableVector@Interop@Xaml@UI@Windows@@@?$TrackerPtr@UIBindableVector@Interop@Xaml@UI@Windows@@$00$0A@@DirectUI@@AEAAXPEAUIBindableVector@Interop@Xaml@UI@Windows@@@Z; DirectUI::TrackerPtr<Windows::UI::Xaml::Interop::IBindableVector,1,0>::Set<Windows::UI::Xaml::Interop::IBindableVector>(Windows::UI::Xaml::Interop::IBindableVector *)
0x1803815cc  mov     this, [rbp+80h+spElementHorizontalLargeIncrease.ptr_]
0x1803815d0  test    this, this
0x1803815d3  jz      short loc_1803815E5
0x1803815d5  mov     [rbp+80h+spElementHorizontalLargeIncrease.ptr_], rbx
0x1803815d9  mov     rax, [this]
0x1803815dc  mov     rax, [rax+10h]
0x1803815e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803815e5  mov     this, [rbp+80h+arg_18]; this
0x1803815ec  lea     r9, [rbp+80h+spElementHorizontalLargeIncrease]; ppReference
0x1803815f0  mov     r8d, 17h; cName
0x1803815f6  lea     rdx, aHorizontallarg; "HorizontalLargeIncrease"
0x1803815fd  call    ??$GetTemplateChildHelper@UIRepeatButton@Primitives@Controls@Xaml@UI@Windows@@U123456@@ScrollBar@DirectUI@@AEAAJPEAG_KPEAPEAUIRepeatButton@Primitives@Controls@Xaml@UI@Windows@@@Z; DirectUI::ScrollBar::GetTemplateChildHelper<Windows::UI::Xaml::Controls::Primitives::IRepeatButton,Windows::UI::Xaml::Controls::Primitives::IRepeatButton>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::Primitives::IRepeatButton * *)
0x180381602  mov     dword ptr [rbp+80h+arg_8], eax
0x180381608  test    eax, eax
0x18038160a  js      loc_180383672
0x180381610  mov     rdx, [rsp+180h+var_120]; pTrackerPtr
0x180381615  mov     this, [rsp+180h+var_160]; this
0x18038161a  call    ?RegisterPtr@WeakReferenceSourceNoThreadId@ctl@@AEAAXQEAVTrackerTargetReference@DirectUI@@@Z; ctl::WeakReferenceSourceNoThreadId::RegisterPtr(DirectUI::TrackerTargetReference * const)
0x18038161f  mov     rdx, [rbp+80h+spElementHorizontalLargeIncrease.ptr_]; pValue
0x180381623  mov     this, [rsp+180h+var_120]; this
0x180381628  test    rdx, rdx
0x18038162b  jz      loc_18038301D
0x180381631  xor     r9d, r9d; bForceLoopback
0x180381634  mov     r8b, 1; bEnsureTrackerTarget
0x180381637  call    ?Set@TrackerTargetReference@DirectUI@@IEAAXQEAUIUnknown@@EE@Z; DirectUI::TrackerTargetReference::Set(IUnknown * const,uchar,uchar)
0x18038163c  mov     rax, [rsp+180h+var_120]
0x180381641  cmp     [rax], rbx
0x180381644  jz      loc_18038170A
0x18038164a  xor     ecx, ecx; string
0x18038164c  call    cs:__imp_WindowsDeleteString
0x180381652  mov     rax, [rsp+180h+var_120]
0x180381657  lea     r8, [rbp+80h+strAutomationName]; pValue
0x18038165e  mov     edx, 22h ; '"'; nPropertyIndex
0x180381663  mov     this, [rax]
0x180381666  lea     rax, [this-278h]
0x18038166d  neg     this
0x180381670  sbb     this, this
0x180381673  and     this, rax; this
0x180381676  call    ?GetValueByKnownIndex@DependencyObject@DirectUI@@QEAAJW4KnownPropertyIndex@@PEAPEAUHSTRING__@@@Z; DirectUI::DependencyObject::GetValueByKnownIndex(KnownPropertyIndex,HSTRING__ * *)
0x18038167b  mov     dword ptr [rbp+80h+arg_8], eax
0x180381681  test    eax, eax
0x180381683  js      loc_1803833CA
0x180381689  cmp     [rbp+80h+strAutomationName._hstring], rbx
0x180381690  jnz     short loc_18038170A
0x180381692  call    ?GetCurrent@DXamlCore@DirectUI@@SAPEAV12@XZ; DirectUI::DXamlCore::GetCurrent(void)
0x180381697  xor     ecx, ecx; string
0x180381699  mov     [rbp+80h+arg_8], rax
0x1803816a0  call    cs:__imp_WindowsDeleteString
0x1803816a6  mov     this, [rbp+80h+arg_8]; this
0x1803816ad  lea     r8, [rbp+80h+strAutomationName]; resourceString
0x1803816b4  mov     edx, 14ADh; resourceStringID
0x1803816b9  mov     [rbp+80h+strAutomationName._hstring], rbx
0x1803816c0  call    ?GetLocalizedResourceString@DXamlCore@DirectUI@@QEAAJIPEAPEAUHSTRING__@@@Z; DirectUI::DXamlCore::GetLocalizedResourceString(uint,HSTRING__ * *)
0x1803816c5  mov     dword ptr [rbp+80h+arg_8], eax
0x1803816cb  test    eax, eax
0x1803816cd  js      loc_1803833BE
0x1803816d3  mov     rax, [rsp+180h+var_120]
0x1803816d8  mov     edx, 22h ; '"'; nPropertyIndex
0x1803816dd  mov     r8, [rbp+80h+strAutomationName._hstring]; value
0x1803816e4  mov     this, [rax]
0x1803816e7  lea     rax, [this-278h]
0x1803816ee  neg     this
0x1803816f1  sbb     this, this
0x1803816f4  and     this, rax; this
0x1803816f7  call    ?SetValueByKnownIndex@DependencyObject@DirectUI@@QEAAJW4KnownPropertyIndex@@PEAUHSTRING__@@@Z; DirectUI::DependencyObject::SetValueByKnownIndex(KnownPropertyIndex,HSTRING__ *)
0x1803816fc  mov     dword ptr [rbp+80h+arg_8], eax
0x180381702  test    eax, eax
0x180381704  js      loc_1803833B2
0x18038170a  mov     this, [rbp+80h+spElementHorizontalSmallIncrease.ptr_]
0x18038170e  test    this, this
0x180381711  jz      short loc_180381723
0x180381713  mov     [rbp+80h+spElementHorizontalSmallIncrease.ptr_], rbx
0x180381717  mov     rax, [this]
0x18038171a  mov     rax, [rax+10h]
0x18038171e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180381723  mov     this, [rbp+80h+arg_18]; this
0x18038172a  lea     r9, [rbp+80h+spElementHorizontalSmallIncrease]; ppReference
0x18038172e  mov     r8d, 17h; cName
0x180381734  lea     rdx, aHorizontalsmal_0; "HorizontalSmallIncrease"
0x18038173b  call    ??$GetTemplateChildHelper@UIRepeatButton@Primitives@Controls@Xaml@UI@Windows@@U123456@@ScrollBar@DirectUI@@AEAAJPEAG_KPEAPEAUIRepeatButton@Primitives@Controls@Xaml@UI@Windows@@@Z; DirectUI::ScrollBar::GetTemplateChildHelper<Windows::UI::Xaml::Controls::Primitives::IRepeatButton,Windows::UI::Xaml::Controls::Primitives::IRepeatButton>(ushort *,unsigned __int64,Windows::UI::Xaml::Controls::Primitives::IRepeatButton * *)
0x180381740  mov     dword ptr [rbp+80h+arg_8], eax
0x180381746  test    eax, eax
0x180381748  js      loc_180383666
0x18038174e  mov     rdx, [rbp+80h+var_100]; pTrackerPtr
0x180381752  mov     this, [rsp+180h+var_160]; this
0x180381757  call    ?RegisterPtr@WeakReferenceSourceNoThreadId@ctl@@AEAAXQEAVTrackerTargetReference@DirectUI@@@Z; ctl::WeakReferenceSourceNoThreadId::RegisterPtr(DirectUI::TrackerTargetReference * const)
0x18038175c  mov     rdx, [rbp+80h+spElementHorizontalSmallIncrease.ptr_]; pValue
0x180381760  mov     this, [rbp+80h+var_100]; this
0x180381764  test    rdx, rdx
0x180381767  jz      loc_18038302C
0x18038176d  xor     r9d, r9d; bForceLoopback
0x180381770  mov     r8b, 1; bEnsureTrackerTarget
0x180381773  call    ?Set@TrackerTargetReference@DirectUI@@IEAAXQEAUIUnknown@@EE@Z; DirectUI::TrackerTargetReference::Set(IUnknown * const,uchar,uchar)
0x180381778  mov     rax, [rbp+80h+var_100]
0x18038177c  cmp     [rax], rbx
0x18038177f  jz      loc_18038184F
0x180381785  mov     this, [rbp+80h+strAutomationName._hstring]; string
0x18038178c  call    cs:__imp_WindowsDeleteString
0x180381792  mov     rax, [rbp+80h+var_100]
0x180381796  lea     r8, [rbp+80h+strAutomationName]; pValue
0x18038179d  mov     edx, 22h ; '"'; nPropertyIndex
  ... truncated ...
```
