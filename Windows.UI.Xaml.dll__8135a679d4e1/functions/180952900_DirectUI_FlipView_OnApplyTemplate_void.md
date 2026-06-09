# DirectUI::FlipView::OnApplyTemplate(void)

- ea: `0x180952900`
- end: `0x180952fc9`
- name: `?OnApplyTemplate@FlipView@DirectUI@@MEAAJXZ`
- size: `1737`
- prototype: `HRESULT __fastcall(DirectUI::FlipView *this)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x18005bcac`
- `0x18005e96c`
- `0x180164e04`
- `0x1801df610`
- `0x1801e5458`
- `0x180248fa8`
- `0x1803024a0`
- `0x1803839c0`
- `0x180951920`
- `0x180951a58`
- `0x180951ac4`
- `0x180952900`
- `0x180953ef0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180952a10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180952a53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180952b89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180952bd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180952d08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180952d50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180952e87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180952eca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180952a10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180952a53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180952b89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180952bd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180952d08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180952d50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180952e87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180952eca`

## pseudocode

```c
__int64 __fastcall DirectUI::FlipView::OnApplyTemplate(DirectUI::FlipView *this)
{
  DirectUI::FlipView *v1; // r14
  HSTRING__ *hstring; // rbx
  HRESULT v4; // eax
  unsigned int v5; // edi
  HRESULT ButtonClickEventHandler; // eax
  Windows::UI::Xaml::Controls::Primitives::IButtonBase **v7; // r15
  DirectUI::DXamlCore *Current; // rbx
  Windows::UI::Xaml::Controls::Primitives::IButtonBase **p_m_tpDataSourceAsSelectionInfo; // r15
  Windows::UI::Xaml::Controls::Primitives::IButtonBase *v10; // rcx
  DirectUI::DXamlCore *v11; // rbx
  bool *p_m_customValuesAllowed; // r15
  Windows::UI::Xaml::Controls::Primitives::IButtonBase *v13; // rcx
  DirectUI::DXamlCore *v14; // rbx
  Windows::UI::Xaml::Controls::Primitives::IButtonBase **p_m_spItemsToSelect; // r15
  Windows::UI::Xaml::Controls::Primitives::IButtonBase *v16; // rcx
  DirectUI::DXamlCore *v17; // rbx
  ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::IButtonBase> spPreviousButtonHorizontalPart; // [rsp+30h] [rbp-28h] BYREF
  HRESULT (__fastcall *v20)(DirectUI::FlipView *, IInspectable *, Windows::UI::Xaml::IRoutedEventArgs *); // [rsp+40h] [rbp-18h] BYREF
  int v21; // [rsp+48h] [rbp-10h]
  Windows::Internal::String strAutomationName; // [rsp+A0h] [rbp+48h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::IButtonBase> spNextButtonVerticalPart; // [rsp+A8h] [rbp+50h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::IButtonBase> spPreviousButtonVerticalPart; // [rsp+B0h] [rbp+58h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Controls::Primitives::IButtonBase> spNextButtonHorizontalPart; // [rsp+B8h] [rbp+60h] BYREF

  v1 = (DirectUI::FlipView *)((char *)this - 360);
  spPreviousButtonHorizontalPart.ptr_ = 0;
  hstring = 0;
  spNextButtonHorizontalPart.ptr_ = 0;
  strAutomationName._hstring = 0;
  spPreviousButtonVerticalPart.ptr_ = 0;
  spNextButtonVerticalPart.ptr_ = 0;
  v4 = DirectUI::FlipView::UnhookTemplate((DirectUI::FlipView *)((char *)this - 360));
  v5 = v4;
  if ( v4 < 0 || (v4 = DirectUI::Selector::OnApplyTemplate(this), v5 = v4, v4 < 0) )
  {
    OnFailure_2990_(v4);
  }
  else
  {
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spPreviousButtonHorizontalPart);
    v21 = 0;
    v20 = DirectUI::FlipView::OnPreviousButtonPartClick;
    ButtonClickEventHandler = DirectUI::FlipView::CreateButtonClickEventHandler(
                                v1,
                                (wchar_t *)L"PreviousButtonHorizontal",
                                0x18u,
                                (HRESULT (__fastcall *)(DirectUI::FlipView *, IInspectable *, Windows::UI::Xaml::IRoutedEventArgs *))&v20,
                                &spPreviousButtonHorizontalPart.ptr_,
                                (EventRegistrationToken *)&this->m_selection.m_selectionChanger.m_pChangeApplier);
    v5 = ButtonClickEventHandler;
    if ( ButtonClickEventHandler < 0 )
      goto LABEL_56;
    v7 = (Windows::UI::Xaml::Controls::Primitives::IButtonBase **)&this->DirectUI::SelectionChangeApplier;
    ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::UI::Xaml::Media::Animation::ITimeline,Windows::UI::Xaml::Media::Animation::ITimeline>(
      (ctl::WeakReferenceSourceNoThreadId *)((char *)&this[-1].m_tpSelectedValuePropertyPathListener.m_trackerReference
                                           + 16),
      (DirectUI::TrackerPtr<Windows::UI::Xaml::Internal::ISecondaryContentRelationship,1,0> *)&this->DirectUI::SelectionChangeApplier,
      (const ctl::ComPtr<Windows::UI::Xaml::Internal::ISecondaryContentRelationship> *)&spPreviousButtonHorizontalPart);
    if ( this->DirectUI::FlipViewGenerated::DirectUI::Selector::DirectUI::SelectionChangeApplier::__vftable )
    {
      ButtonClickEventHandler = DirectUI::FlipView::CreateButtonPointerEnteredEventHandler(
                                  v1,
                                  (Windows::UI::Xaml::Controls::Primitives::IButtonBase *)this->DirectUI::FlipViewGenerated::DirectUI::Selector::DirectUI::SelectionChangeApplier::__vftable,
                                  (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs,DirectUI::UIElementPointerEnteredTraits> > *)&this->m_tpScrollViewer);
      v5 = ButtonClickEventHandler;
      if ( ButtonClickEventHandler < 0 )
        goto LABEL_56;
      ButtonClickEventHandler = DirectUI::FlipView::CreateButtonPointerExitedEventHandler(
                                  v1,
                                  *v7,
                                  (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs,DirectUI::UIElementPointerExitedTraits> > *)&this->m_tpMonitoredCV.m_trackerReference.8);
      v5 = ButtonClickEventHandler;
      if ( ButtonClickEventHandler < 0 )
        goto LABEL_56;
      WindowsDeleteString(0);
      ButtonClickEventHandler = DirectUI::DependencyObject::GetValueByKnownIndex(
                                  (DirectUI::DependencyObject *)((unsigned __int64)&(*v7)[-71] & -(__int64)(*v7 != 0)),
                                  AutomationProperties_Name,
                                  &strAutomationName._hstring);
      v5 = ButtonClickEventHandler;
      if ( ButtonClickEventHandler < 0 )
        goto LABEL_56;
      hstring = strAutomationName._hstring;
      if ( !strAutomationName._hstring )
      {
        Current = DirectUI::DXamlCore::GetCurrent();
        WindowsDeleteString(0);
        strAutomationName._hstring = 0;
        ButtonClickEventHandler = DirectUI::DXamlCore::GetLocalizedResourceString(
                                    Current,
                                    0x1483u,
                                    &strAutomationName._hstring);
        v5 = ButtonClickEventHandler;
        if ( ButtonClickEventHandler < 0 )
          goto LABEL_56;
        hstring = strAutomationName._hstring;
        ButtonClickEventHandler = DirectUI::DependencyObject::SetValueByKnownIndex(
                                    (DirectUI::DependencyObject *)((unsigned __int64)&(*v7)[-71] & -(__int64)(*v7 != 0)),
                                    AutomationProperties_Name,
                                    strAutomationName._hstring);
        v5 = ButtonClickEventHandler;
        if ( ButtonClickEventHandler < 0 )
          goto LABEL_56;
      }
    }
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spNextButtonHorizontalPart);
    v21 = 0;
    v20 = DirectUI::FlipView::OnNextButtonPartClick;
    ButtonClickEventHandler = DirectUI::FlipView::CreateButtonClickEventHandler(
                                v1,
                                (wchar_t *)L"NextButtonHorizontal",
                                0x14u,
                                (HRESULT (__fastcall *)(DirectUI::FlipView *, IInspectable *, Windows::UI::Xaml::IRoutedEventArgs *))&v20,
                                &spNextButtonHorizontalPart.ptr_,
                                (EventRegistrationToken *)&this->m_selection.m_spSelectedItems);
    v5 = ButtonClickEventHandler;
    if ( ButtonClickEventHandler < 0 )
      goto LABEL_56;
    p_m_tpDataSourceAsSelectionInfo = (Windows::UI::Xaml::Controls::Primitives::IButtonBase **)&this->m_tpDataSourceAsSelectionInfo;
    ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::UI::Xaml::Media::Animation::ITimeline,Windows::UI::Xaml::Media::Animation::ITimeline>(
      (ctl::WeakReferenceSourceNoThreadId *)((char *)&this[-1].m_tpSelectedValuePropertyPathListener.m_trackerReference
                                           + 16),
      (DirectUI::TrackerPtr<Windows::UI::Xaml::Internal::ISecondaryContentRelationship,1,0> *)&this->m_tpDataSourceAsSelectionInfo,
      (const ctl::ComPtr<Windows::UI::Xaml::Internal::ISecondaryContentRelationship> *)&spNextButtonHorizontalPart);
    if ( this->m_tpDataSourceAsSelectionInfo.m_trackerReference.m_value )
    {
      ButtonClickEventHandler = DirectUI::FlipView::CreateButtonPointerEnteredEventHandler(
                                  v1,
                                  (Windows::UI::Xaml::Controls::Primitives::IButtonBase *)this->m_tpDataSourceAsSelectionInfo.m_trackerReference.m_value,
                                  (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs,DirectUI::UIElementPointerEnteredTraits> > *)&this->m_tpScrollViewer.m_trackerReference.8);
      v5 = ButtonClickEventHandler;
      if ( ButtonClickEventHandler < 0 )
        goto LABEL_56;
      ButtonClickEventHandler = DirectUI::FlipView::CreateButtonPointerExitedEventHandler(
                                  v1,
                                  *p_m_tpDataSourceAsSelectionInfo,
                                  (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs,DirectUI::UIElementPointerExitedTraits> > *)&this->m_tpMonitoredCV.m_trackerReference
                                + 2);
      v5 = ButtonClickEventHandler;
      if ( ButtonClickEventHandler < 0 )
        goto LABEL_56;
      WindowsDeleteString(hstring);
      v10 = *p_m_tpDataSourceAsSelectionInfo;
      strAutomationName._hstring = 0;
      ButtonClickEventHandler = DirectUI::DependencyObject::GetValueByKnownIndex(
                                  (DirectUI::DependencyObject *)((unsigned __int64)&v10[-71] & -(__int64)(v10 != 0)),
                                  AutomationProperties_Name,
                                  &strAutomationName._hstring);
      v5 = ButtonClickEventHandler;
      if ( ButtonClickEventHandler < 0 )
        goto LABEL_56;
      hstring = strAutomationName._hstring;
      if ( !strAutomationName._hstring )
      {
        v11 = DirectUI::DXamlCore::GetCurrent();
        WindowsDeleteString(0);
        strAutomationName._hstring = 0;
        ButtonClickEventHandler = DirectUI::DXamlCore::GetLocalizedResourceString(
                                    v11,
                                    0x1482u,
                                    &strAutomationName._hstring);
        v5 = ButtonClickEventHandler;
        if ( ButtonClickEventHandler < 0 )
          goto LABEL_56;
        hstring = strAutomationName._hstring;
        ButtonClickEventHandler = DirectUI::DependencyObject::SetValueByKnownIndex(
                                    (DirectUI::DependencyObject *)((unsigned __int64)&(*p_m_tpDataSourceAsSelectionInfo)[-71]
                                                                 & -(__int64)(*p_m_tpDataSourceAsSelectionInfo != 0)),
                                    AutomationProperties_Name,
                                    strAutomationName._hstring);
        v5 = ButtonClickEventHandler;
        if ( ButtonClickEventHandler < 0 )
          goto LABEL_56;
      }
    }
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spPreviousButtonVerticalPart);
    v21 = 0;
    v20 = DirectUI::FlipView::OnPreviousButtonPartClick;
    ButtonClickEventHandler = DirectUI::FlipView::CreateButtonClickEventHandler(
                                v1,
                                (wchar_t *)L"PreviousButtonVertical",
                                0x16u,
                                (HRESULT (__fastcall *)(DirectUI::FlipView *, IInspectable *, Windows::UI::Xaml::IRoutedEventArgs *))&v20,
                                &spPreviousButtonVerticalPart.ptr_,
                                (EventRegistrationToken *)&this->m_iFocusedIndex);
    v5 = ButtonClickEventHandler;
    if ( ButtonClickEventHandler < 0 )
      goto LABEL_56;
    p_m_customValuesAllowed = &this->m_customValuesAllowed;
    ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::UI::Xaml::Media::Animation::ITimeline,Windows::UI::Xaml::Media::Animation::ITimeline>(
      (ctl::WeakReferenceSourceNoThreadId *)((char *)&this[-1].m_tpSelectedValuePropertyPathListener.m_trackerReference
                                           + 16),
      (DirectUI::TrackerPtr<Windows::UI::Xaml::Internal::ISecondaryContentRelationship,1,0> *)&this->m_customValuesAllowed,
      (const ctl::ComPtr<Windows::UI::Xaml::Internal::ISecondaryContentRelationship> *)&spPreviousButtonVerticalPart);
    if ( *(_QWORD *)&this->m_customValuesAllowed )
    {
      ButtonClickEventHandler = DirectUI::FlipView::CreateButtonPointerEnteredEventHandler(
                                  v1,
                                  *(Windows::UI::Xaml::Controls::Primitives::IButtonBase **)&this->m_customValuesAllowed,
                                  (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs,DirectUI::UIElementPointerEnteredTraits> > *)&this->m_tpScrollViewer.m_trackerReference
                                + 2);
      v5 = ButtonClickEventHandler;
      if ( ButtonClickEventHandler < 0 )
        goto LABEL_56;
      ButtonClickEventHandler = DirectUI::FlipView::CreateButtonPointerExitedEventHandler(
                                  v1,
                                  *(Windows::UI::Xaml::Controls::Primitives::IButtonBase **)p_m_customValuesAllowed,
                                  (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs,DirectUI::UIElementPointerExitedTraits> > *)&this->m_epCVCurrentChanged);
      v5 = ButtonClickEventHandler;
      if ( ButtonClickEventHandler < 0 )
        goto LABEL_56;
      WindowsDeleteString(hstring);
      v13 = *(Windows::UI::Xaml::Controls::Primitives::IButtonBase **)p_m_customValuesAllowed;
      strAutomationName._hstring = 0;
      ButtonClickEventHandler = DirectUI::DependencyObject::GetValueByKnownIndex(
                                  (DirectUI::DependencyObject *)((unsigned __int64)&v13[-71] & -(__int64)(v13 != 0)),
                                  AutomationProperties_Name,
                                  &strAutomationName._hstring);
      v5 = ButtonClickEventHandler;
      if ( ButtonClickEventHandler < 0 )
        goto LABEL_56;
      hstring = strAutomationName._hstring;
      if ( !strAutomationName._hstring )
      {
        v14 = DirectUI::DXamlCore::GetCurrent();
        WindowsDeleteString(0);
        strAutomationName._hstring = 0;
        ButtonClickEventHandler = DirectUI::DXamlCore::GetLocalizedResourceString(
                                    v14,
                                    0x1483u,
                                    &strAutomationName._hstring);
        v5 = ButtonClickEventHandler;
        if ( ButtonClickEventHandler < 0 )
          goto LABEL_56;
        hstring = strAutomationName._hstring;
        ButtonClickEventHandler = DirectUI::DependencyObject::SetValueByKnownIndex(
                                    (DirectUI::DependencyObject *)((*(_QWORD *)p_m_customValuesAllowed - 568LL)
                                                                 & -(__int64)(*(_QWORD *)p_m_customValuesAllowed != 0)),
                                    AutomationProperties_Name,
                                    strAutomationName._hstring);
        v5 = ButtonClickEventHandler;
        if ( ButtonClickEventHandler < 0 )
          goto LABEL_56;
      }
    }
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spNextButtonVerticalPart);
    v21 = 0;
    v20 = DirectUI::FlipView::OnNextButtonPartClick;
    ButtonClickEventHandler = DirectUI::FlipView::CreateButtonClickEventHandler(
                                v1,
                                (wchar_t *)L"NextButtonVertical",
                                0x12u,
                                (HRESULT (__fastcall *)(DirectUI::FlipView *, IInspectable *, Windows::UI::Xaml::IRoutedEventArgs *))&v20,
                                &spNextButtonVerticalPart.ptr_,
                                (EventRegistrationToken *)&this->DirectUI::Selector + 135);
    v5 = ButtonClickEventHandler;
    if ( ButtonClickEventHandler < 0 )
      goto LABEL_56;
    p_m_spItemsToSelect = (Windows::UI::Xaml::Controls::Primitives::IButtonBase **)&this->m_selection.m_selectionChanger.m_spItemsToSelect;
    ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::UI::Xaml::Media::Animation::ITimeline,Windows::UI::Xaml::Media::Animation::ITimeline>(
      (ctl::WeakReferenceSourceNoThreadId *)((char *)&this[-1].m_tpSelectedValuePropertyPathListener.m_trackerReference
                                           + 16),
      (DirectUI::TrackerPtr<Windows::UI::Xaml::Internal::ISecondaryContentRelationship,1,0> *)&this->m_selection.m_selectionChanger.m_spItemsToSelect,
      (const ctl::ComPtr<Windows::UI::Xaml::Internal::ISecondaryContentRelationship> *)&spNextButtonVerticalPart);
    if ( this->m_selection.m_selectionChanger.m_spItemsToSelect.ptr_ )
    {
      ButtonClickEventHandler = DirectUI::FlipView::CreateButtonPointerEnteredEventHandler(
                                  v1,
                                  (Windows::UI::Xaml::Controls::Primitives::IButtonBase *)this->m_selection.m_selectionChanger.m_spItemsToSelect.ptr_,
                                  (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs,DirectUI::UIElementPointerEnteredTraits> > *)&this->m_tpMonitoredCV);
      v5 = ButtonClickEventHandler;
      if ( ButtonClickEventHandler < 0 )
        goto LABEL_56;
      ButtonClickEventHandler = DirectUI::FlipView::CreateButtonPointerExitedEventHandler(
                                  v1,
                                  *p_m_spItemsToSelect,
                                  (ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs,DirectUI::UIElementPointerExitedTraits> > *)&this->m_pInitializingData);
      v5 = ButtonClickEventHandler;
      if ( ButtonClickEventHandler < 0 )
        goto LABEL_56;
      WindowsDeleteString(hstring);
      v16 = *p_m_spItemsToSelect;
      strAutomationName._hstring = 0;
      ButtonClickEventHandler = DirectUI::DependencyObject::GetValueByKnownIndex(
                                  (DirectUI::DependencyObject *)((unsigned __int64)&v16[-71] & -(__int64)(v16 != 0)),
                                  AutomationProperties_Name,
                                  &strAutomationName._hstring);
      v5 = ButtonClickEventHandler;
      if ( ButtonClickEventHandler < 0 )
        goto LABEL_56;
      if ( !strAutomationName._hstring )
      {
        v17 = DirectUI::DXamlCore::GetCurrent();
        WindowsDeleteString(0);
        strAutomationName._hstring = 0;
        ButtonClickEventHandler = DirectUI::DXamlCore::GetLocalizedResourceString(
                                    v17,
                                    0x1482u,
                                    &strAutomationName._hstring);
        v5 = ButtonClickEventHandler;
        if ( ButtonClickEventHandler < 0 )
          goto LABEL_56;
        ButtonClickEventHandler = DirectUI::DependencyObject::SetValueByKnownIndex(
                                    (DirectUI::DependencyObject *)((unsigned __int64)&(*p_m_spItemsToSelect)[-71]
                                                                 & -(__int64)(*p_m_spItemsToSelect != 0)),
                                    AutomationProperties_Name,
                                    strAutomationName._hstring);
        v5 = ButtonClickEventHandler;
        if ( ButtonClickEventHandler < 0 )
          goto LABEL_56;
      }
    }
    ButtonClickEventHandler = DirectUI::Control::UpdateVisualState(v1, 0);
    v5 = ButtonClickEventHandler;
    if ( ButtonClickEventHandler < 0 )
LABEL_56:
      OnFailure_2990_(ButtonClickEventHandler);
  }
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spNextButtonVerticalPart);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spPreviousButtonVerticalPart);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spNextButtonHorizontalPart);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spPreviousButtonHorizontalPart);
  Windows::Internal::String::~String(&strAutomationName);
  return v5;
}

```

## disassembly

```asm
0x180952900  push    rbp
0x180952902  push    rbx
0x180952903  push    rsi
0x180952904  push    rdi
0x180952905  push    r12
0x180952907  push    r13
0x180952909  push    r14
0x18095290b  push    r15
0x18095290d  mov     rbp, rsp
0x180952910  sub     rsp, 58h
0x180952914  xor     r13d, r13d
0x180952917  lea     r14, [this-168h]
0x18095291e  mov     rsi, this
0x180952921  mov     [rbp+spPreviousButtonHorizontalPart.ptr_], r13
0x180952925  mov     ebx, r13d
0x180952928  mov     [rbp+spNextButtonHorizontalPart.ptr_], r13
0x18095292c  mov     this, r14; this
0x18095292f  mov     [rbp+strAutomationName._hstring], rbx
0x180952933  mov     [rbp+spPreviousButtonVerticalPart.ptr_], r13
0x180952937  mov     [rbp+spNextButtonVerticalPart.ptr_], r13
0x18095293b  call    ?UnhookTemplate@FlipView@DirectUI@@AEAAJXZ; DirectUI::FlipView::UnhookTemplate(void)
0x180952940  mov     edi, eax
0x180952942  test    eax, eax
0x180952944  js      loc_180952F82
0x18095294a  mov     this, rsi; this
0x18095294d  call    ?OnApplyTemplate@Selector@DirectUI@@UEAAJXZ; DirectUI::Selector::OnApplyTemplate(void)
0x180952952  mov     edi, eax
0x180952954  test    eax, eax
0x180952956  js      loc_180952F79
0x18095295c  lea     this, [rbp+spPreviousButtonHorizontalPart]; this
0x180952960  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180952965  lea     rax, ?OnPreviousButtonPartClick@FlipView@DirectUI@@AEAAJPEAUIInspectable@@PEAUIRoutedEventArgs@Xaml@UI@Windows@@@Z; DirectUI::FlipView::OnPreviousButtonPartClick(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *)
0x18095296c  mov     [rbp+var_10], r13d
0x180952970  mov     [rbp+var_18], rax
0x180952974  lea     r9, [rbp+var_18]; pfnEventHandler
0x180952978  mov     eax, [rbp+var_C]
0x18095297b  lea     r8d, [r13+18h]; pcButton
0x18095297f  mov     [rbp+var_C], eax
0x180952982  lea     rdx, aPreviousbutton; "PreviousButtonHorizontal"
0x180952989  lea     rax, [rsi+420h]
0x180952990  mov     this, r14; this
0x180952993  mov     [rsp+58h+pEventToken], rax; pEventToken
0x180952998  lea     rax, [rbp+spPreviousButtonHorizontalPart]
0x18095299c  mov     [rsp+58h+ppButton], rax; ppButton
0x1809529a1  call    ?CreateButtonClickEventHandler@FlipView@DirectUI@@AEAAJPEAG_KP812@EAAJPEAUIInspectable@@PEAUIRoutedEventArgs@Xaml@UI@Windows@@@ZPEAPEAUIButtonBase@Primitives@Controls@567@PEAUEventRegistrationToken@@@Z; DirectUI::FlipView::CreateButtonClickEventHandler(ushort *,unsigned __int64,long (DirectUI::FlipView::*)(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *),Windows::UI::Xaml::Controls::Primitives::IButtonBase * *,EventRegistrationToken *)
0x1809529a6  mov     edi, eax
0x1809529a8  test    eax, eax
0x1809529aa  js      loc_180952F70
0x1809529b0  lea     r12, [rsi-160h]
0x1809529b7  lea     r15, [rsi+3B8h]
0x1809529be  mov     this, r12; this
0x1809529c1  mov     rdx, r15; ptr
0x1809529c4  lea     r8, [rbp+spPreviousButtonHorizontalPart]; sp
0x1809529c8  call    ??$SetPtrValue@UITimeline@Animation@Media@Xaml@UI@Windows@@U123456@@WeakReferenceSourceNoThreadId@ctl@@QEAAXAEAV?$TrackerPtr@UITimeline@Animation@Media@Xaml@UI@Windows@@$00$0A@@DirectUI@@AEBV?$ComPtr@UITimeline@Animation@Media@Xaml@UI@Windows@@@1@@Z; ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::UI::Xaml::Media::Animation::ITimeline,Windows::UI::Xaml::Media::Animation::ITimeline>(DirectUI::TrackerPtr<Windows::UI::Xaml::Media::Animation::ITimeline,1,0> &,ctl::ComPtr<Windows::UI::Xaml::Media::Animation::ITimeline> const &)
0x1809529cd  mov     rdx, [r15]; pButton
0x1809529d0  test    rdx, rdx
0x1809529d3  jz      loc_180952AD9
0x1809529d9  lea     r8, [rsi+480h]; eventPtr
0x1809529e0  mov     this, r14; this
0x1809529e3  call    ?CreateButtonPointerEnteredEventHandler@FlipView@DirectUI@@AEAAJPEAUIButtonBase@Primitives@Controls@Xaml@UI@Windows@@AEAV?$EventPtr@V?$event_handler@UIPointerEventHandler@Input@Xaml@UI@Windows@@UIInspectable@@UIPointerRoutedEventArgs@2345@UUIElementPointerEnteredTraits@DirectUI@@@ctl@@@ctl@@@Z; DirectUI::FlipView::CreateButtonPointerEnteredEventHandler(Windows::UI::Xaml::Controls::Primitives::IButtonBase *,ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs,DirectUI::UIElementPointerEnteredTraits>> &)
0x1809529e8  mov     edi, eax
0x1809529ea  test    eax, eax
0x1809529ec  js      loc_180952ACD
0x1809529f2  mov     rdx, [r15]; pButton
0x1809529f5  lea     r8, [rsi+4A0h]; eventPtr
0x1809529fc  mov     this, r14; this
0x1809529ff  call    ?CreateButtonPointerExitedEventHandler@FlipView@DirectUI@@AEAAJPEAUIButtonBase@Primitives@Controls@Xaml@UI@Windows@@AEAV?$EventPtr@V?$event_handler@UIPointerEventHandler@Input@Xaml@UI@Windows@@UIInspectable@@UIPointerRoutedEventArgs@2345@UUIElementPointerExitedTraits@DirectUI@@@ctl@@@ctl@@@Z; DirectUI::FlipView::CreateButtonPointerExitedEventHandler(Windows::UI::Xaml::Controls::Primitives::IButtonBase *,ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs,DirectUI::UIElementPointerExitedTraits>> &)
0x180952a04  mov     edi, eax
0x180952a06  test    eax, eax
0x180952a08  js      loc_180952AC1
0x180952a0e  xor     ecx, ecx; string
0x180952a10  call    cs:__imp_WindowsDeleteString
0x180952a16  mov     this, [r15]
0x180952a19  lea     edx, [r13+22h]; nPropertyIndex
0x180952a1d  lea     r8, [rbp+strAutomationName]; pValue
0x180952a21  lea     rax, [this-238h]
0x180952a28  neg     this
0x180952a2b  sbb     this, this
0x180952a2e  and     this, rax; this
0x180952a31  call    ?GetValueByKnownIndex@DependencyObject@DirectUI@@QEAAJW4KnownPropertyIndex@@PEAPEAUHSTRING__@@@Z; DirectUI::DependencyObject::GetValueByKnownIndex(KnownPropertyIndex,HSTRING__ * *)
0x180952a36  mov     edi, eax
0x180952a38  test    eax, eax
0x180952a3a  js      short loc_180952AB5
0x180952a3c  mov     rbx, [rbp+strAutomationName._hstring]
0x180952a40  test    rbx, rbx
0x180952a43  jnz     loc_180952AD9
0x180952a49  call    ?GetCurrent@DXamlCore@DirectUI@@SAPEAV12@XZ; DirectUI::DXamlCore::GetCurrent(void)
0x180952a4e  xor     ecx, ecx; string
0x180952a50  mov     rbx, rax
0x180952a53  call    cs:__imp_WindowsDeleteString
0x180952a59  lea     r8, [rbp+strAutomationName]; resourceString
0x180952a5d  mov     [rbp+strAutomationName._hstring], r13
0x180952a61  mov     edx, 1483h; resourceStringID
0x180952a66  mov     this, rbx; this
0x180952a69  call    ?GetLocalizedResourceString@DXamlCore@DirectUI@@QEAAJIPEAPEAUHSTRING__@@@Z; DirectUI::DXamlCore::GetLocalizedResourceString(uint,HSTRING__ * *)
0x180952a6e  mov     edi, eax
0x180952a70  test    eax, eax
0x180952a72  js      short loc_180952AA9
0x180952a74  mov     this, [r15]
0x180952a77  lea     edx, [r13+22h]; nPropertyIndex
0x180952a7b  mov     rbx, [rbp+strAutomationName._hstring]
0x180952a7f  mov     r8, rbx; value
0x180952a82  lea     rax, [this-238h]
0x180952a89  neg     this
0x180952a8c  sbb     this, this
0x180952a8f  and     this, rax; this
0x180952a92  call    ?SetValueByKnownIndex@DependencyObject@DirectUI@@QEAAJW4KnownPropertyIndex@@PEAUHSTRING__@@@Z; DirectUI::DependencyObject::SetValueByKnownIndex(KnownPropertyIndex,HSTRING__ *)
0x180952a97  mov     edi, eax
0x180952a99  test    eax, eax
0x180952a9b  jns     short loc_180952AD9
0x180952a9d  mov     ecx, eax; failedFrameHR
0x180952a9f  call    OnFailure_2990_
0x180952aa4  jmp     $Cleanup_8868
0x180952aa9  mov     ecx, eax; failedFrameHR
0x180952aab  call    OnFailure_2990_
0x180952ab0  jmp     $Cleanup_8868
0x180952ab5  mov     ecx, eax; failedFrameHR
0x180952ab7  call    OnFailure_2990_
0x180952abc  jmp     $Cleanup_8868
0x180952ac1  mov     ecx, eax; failedFrameHR
0x180952ac3  call    OnFailure_2990_
0x180952ac8  jmp     $Cleanup_8868
0x180952acd  mov     ecx, eax; failedFrameHR
0x180952acf  call    OnFailure_2990_
0x180952ad4  jmp     $Cleanup_8868
0x180952ad9  lea     this, [rbp+spNextButtonHorizontalPart]; this
0x180952add  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180952ae2  lea     rax, ?OnNextButtonPartClick@FlipView@DirectUI@@AEAAJPEAUIInspectable@@PEAUIRoutedEventArgs@Xaml@UI@Windows@@@Z; DirectUI::FlipView::OnNextButtonPartClick(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *)
0x180952ae9  mov     [rbp+var_10], r13d
0x180952aed  mov     [rbp+var_18], rax
0x180952af1  lea     r9, [rbp+var_18]; pfnEventHandler
0x180952af5  mov     eax, [rbp+var_C]
0x180952af8  lea     rdx, aNextbuttonhori; "NextButtonHorizontal"
0x180952aff  mov     [rbp+var_C], eax
0x180952b02  mov     r8d, 14h; pcButton
0x180952b08  lea     rax, [rsi+428h]
0x180952b0f  mov     this, r14; this
0x180952b12  mov     [rsp+58h+pEventToken], rax; pEventToken
0x180952b17  lea     rax, [rbp+spNextButtonHorizontalPart]
0x180952b1b  mov     [rsp+58h+ppButton], rax; ppButton
0x180952b20  call    ?CreateButtonClickEventHandler@FlipView@DirectUI@@AEAAJPEAG_KP812@EAAJPEAUIInspectable@@PEAUIRoutedEventArgs@Xaml@UI@Windows@@@ZPEAPEAUIButtonBase@Primitives@Controls@567@PEAUEventRegistrationToken@@@Z; DirectUI::FlipView::CreateButtonClickEventHandler(ushort *,unsigned __int64,long (DirectUI::FlipView::*)(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *),Windows::UI::Xaml::Controls::Primitives::IButtonBase * *,EventRegistrationToken *)
0x180952b25  mov     edi, eax
0x180952b27  test    eax, eax
0x180952b29  js      loc_180952F67
0x180952b2f  lea     r15, [rsi+3D0h]
0x180952b36  mov     this, r12; this
0x180952b39  mov     rdx, r15; ptr
0x180952b3c  lea     r8, [rbp+spNextButtonHorizontalPart]; sp
0x180952b40  call    ??$SetPtrValue@UITimeline@Animation@Media@Xaml@UI@Windows@@U123456@@WeakReferenceSourceNoThreadId@ctl@@QEAAXAEAV?$TrackerPtr@UITimeline@Animation@Media@Xaml@UI@Windows@@$00$0A@@DirectUI@@AEBV?$ComPtr@UITimeline@Animation@Media@Xaml@UI@Windows@@@1@@Z; ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::UI::Xaml::Media::Animation::ITimeline,Windows::UI::Xaml::Media::Animation::ITimeline>(DirectUI::TrackerPtr<Windows::UI::Xaml::Media::Animation::ITimeline,1,0> &,ctl::ComPtr<Windows::UI::Xaml::Media::Animation::ITimeline> const &)
0x180952b45  mov     rdx, [r15]; pButton
0x180952b48  test    rdx, rdx
0x180952b4b  jz      loc_180952C58
0x180952b51  lea     r8, [rsi+488h]; eventPtr
0x180952b58  mov     this, r14; this
0x180952b5b  call    ?CreateButtonPointerEnteredEventHandler@FlipView@DirectUI@@AEAAJPEAUIButtonBase@Primitives@Controls@Xaml@UI@Windows@@AEAV?$EventPtr@V?$event_handler@UIPointerEventHandler@Input@Xaml@UI@Windows@@UIInspectable@@UIPointerRoutedEventArgs@2345@UUIElementPointerEnteredTraits@DirectUI@@@ctl@@@ctl@@@Z; DirectUI::FlipView::CreateButtonPointerEnteredEventHandler(Windows::UI::Xaml::Controls::Primitives::IButtonBase *,ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs,DirectUI::UIElementPointerEnteredTraits>> &)
0x180952b60  mov     edi, eax
0x180952b62  test    eax, eax
0x180952b64  js      loc_180952C4C
0x180952b6a  mov     rdx, [r15]; pButton
0x180952b6d  lea     r8, [rsi+4A8h]; eventPtr
0x180952b74  mov     this, r14; this
0x180952b77  call    ?CreateButtonPointerExitedEventHandler@FlipView@DirectUI@@AEAAJPEAUIButtonBase@Primitives@Controls@Xaml@UI@Windows@@AEAV?$EventPtr@V?$event_handler@UIPointerEventHandler@Input@Xaml@UI@Windows@@UIInspectable@@UIPointerRoutedEventArgs@2345@UUIElementPointerExitedTraits@DirectUI@@@ctl@@@ctl@@@Z; DirectUI::FlipView::CreateButtonPointerExitedEventHandler(Windows::UI::Xaml::Controls::Primitives::IButtonBase *,ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs,DirectUI::UIElementPointerExitedTraits>> &)
0x180952b7c  mov     edi, eax
0x180952b7e  test    eax, eax
0x180952b80  js      loc_180952C40
0x180952b86  mov     this, rbx; string
0x180952b89  call    cs:__imp_WindowsDeleteString
0x180952b8f  mov     this, [r15]
0x180952b92  lea     r8, [rbp+strAutomationName]; pValue
0x180952b96  mov     edx, 22h ; '"'; nPropertyIndex
0x180952b9b  mov     [rbp+strAutomationName._hstring], r13
0x180952b9f  lea     rax, [this-238h]
0x180952ba6  neg     this
0x180952ba9  sbb     this, this
0x180952bac  and     this, rax; this
0x180952baf  call    ?GetValueByKnownIndex@DependencyObject@DirectUI@@QEAAJW4KnownPropertyIndex@@PEAPEAUHSTRING__@@@Z; DirectUI::DependencyObject::GetValueByKnownIndex(KnownPropertyIndex,HSTRING__ * *)
0x180952bb4  mov     edi, eax
0x180952bb6  test    eax, eax
0x180952bb8  js      short loc_180952C34
0x180952bba  mov     rbx, [rbp+strAutomationName._hstring]
0x180952bbe  test    rbx, rbx
0x180952bc1  jnz     loc_180952C58
0x180952bc7  call    ?GetCurrent@DXamlCore@DirectUI@@SAPEAV12@XZ; DirectUI::DXamlCore::GetCurrent(void)
0x180952bcc  xor     ecx, ecx; string
0x180952bce  mov     rbx, rax
0x180952bd1  call    cs:__imp_WindowsDeleteString
0x180952bd7  lea     r8, [rbp+strAutomationName]; resourceString
0x180952bdb  mov     [rbp+strAutomationName._hstring], r13
0x180952bdf  mov     edx, 1482h; resourceStringID
0x180952be4  mov     this, rbx; this
0x180952be7  call    ?GetLocalizedResourceString@DXamlCore@DirectUI@@QEAAJIPEAPEAUHSTRING__@@@Z; DirectUI::DXamlCore::GetLocalizedResourceString(uint,HSTRING__ * *)
0x180952bec  mov     edi, eax
0x180952bee  test    eax, eax
0x180952bf0  js      short loc_180952C28
0x180952bf2  mov     this, [r15]
0x180952bf5  mov     edx, 22h ; '"'; nPropertyIndex
0x180952bfa  mov     rbx, [rbp+strAutomationName._hstring]
0x180952bfe  mov     r8, rbx; value
0x180952c01  lea     rax, [this-238h]
0x180952c08  neg     this
0x180952c0b  sbb     this, this
0x180952c0e  and     this, rax; this
0x180952c11  call    ?SetValueByKnownIndex@DependencyObject@DirectUI@@QEAAJW4KnownPropertyIndex@@PEAUHSTRING__@@@Z; DirectUI::DependencyObject::SetValueByKnownIndex(KnownPropertyIndex,HSTRING__ *)
0x180952c16  mov     edi, eax
0x180952c18  test    eax, eax
0x180952c1a  jns     short loc_180952C58
0x180952c1c  mov     ecx, eax; failedFrameHR
0x180952c1e  call    OnFailure_2990_
0x180952c23  jmp     $Cleanup_8868
0x180952c28  mov     ecx, eax; failedFrameHR
0x180952c2a  call    OnFailure_2990_
0x180952c2f  jmp     $Cleanup_8868
0x180952c34  mov     ecx, eax; failedFrameHR
0x180952c36  call    OnFailure_2990_
0x180952c3b  jmp     $Cleanup_8868
0x180952c40  mov     ecx, eax; failedFrameHR
0x180952c42  call    OnFailure_2990_
0x180952c47  jmp     $Cleanup_8868
0x180952c4c  mov     ecx, eax; failedFrameHR
0x180952c4e  call    OnFailure_2990_
0x180952c53  jmp     $Cleanup_8868
0x180952c58  lea     this, [rbp+spPreviousButtonVerticalPart]; this
0x180952c5c  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x180952c61  lea     rax, ?OnPreviousButtonPartClick@FlipView@DirectUI@@AEAAJPEAUIInspectable@@PEAUIRoutedEventArgs@Xaml@UI@Windows@@@Z; DirectUI::FlipView::OnPreviousButtonPartClick(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *)
0x180952c68  mov     [rbp+var_10], r13d
0x180952c6c  mov     [rbp+var_18], rax
0x180952c70  lea     r9, [rbp+var_18]; pfnEventHandler
0x180952c74  mov     eax, [rbp+var_C]
0x180952c77  lea     rdx, aPreviousbutton_1; "PreviousButtonVertical"
0x180952c7e  mov     [rbp+var_C], eax
0x180952c81  mov     r8d, 16h; pcButton
0x180952c87  lea     rax, [rsi+430h]
0x180952c8e  mov     this, r14; this
0x180952c91  mov     [rsp+58h+pEventToken], rax; pEventToken
0x180952c96  lea     rax, [rbp+spPreviousButtonVerticalPart]
0x180952c9a  mov     [rsp+58h+ppButton], rax; ppButton
0x180952c9f  call    ?CreateButtonClickEventHandler@FlipView@DirectUI@@AEAAJPEAG_KP812@EAAJPEAUIInspectable@@PEAUIRoutedEventArgs@Xaml@UI@Windows@@@ZPEAPEAUIButtonBase@Primitives@Controls@567@PEAUEventRegistrationToken@@@Z; DirectUI::FlipView::CreateButtonClickEventHandler(ushort *,unsigned __int64,long (DirectUI::FlipView::*)(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *),Windows::UI::Xaml::Controls::Primitives::IButtonBase * *,EventRegistrationToken *)
0x180952ca4  mov     edi, eax
0x180952ca6  test    eax, eax
0x180952ca8  js      loc_180952F5E
0x180952cae  lea     r15, [rsi+3E8h]
0x180952cb5  mov     this, r12; this
0x180952cb8  mov     rdx, r15; ptr
0x180952cbb  lea     r8, [rbp+spPreviousButtonVerticalPart]; sp
0x180952cbf  call    ??$SetPtrValue@UITimeline@Animation@Media@Xaml@UI@Windows@@U123456@@WeakReferenceSourceNoThreadId@ctl@@QEAAXAEAV?$TrackerPtr@UITimeline@Animation@Media@Xaml@UI@Windows@@$00$0A@@DirectUI@@AEBV?$ComPtr@UITimeline@Animation@Media@Xaml@UI@Windows@@@1@@Z; ctl::WeakReferenceSourceNoThreadId::SetPtrValue<Windows::UI::Xaml::Media::Animation::ITimeline,Windows::UI::Xaml::Media::Animation::ITimeline>(DirectUI::TrackerPtr<Windows::UI::Xaml::Media::Animation::ITimeline,1,0> &,ctl::ComPtr<Windows::UI::Xaml::Media::Animation::ITimeline> const &)
0x180952cc4  mov     rdx, [r15]; pButton
0x180952cc7  test    rdx, rdx
0x180952cca  jz      loc_180952DD7
0x180952cd0  lea     r8, [rsi+490h]; eventPtr
0x180952cd7  mov     this, r14; this
0x180952cda  call    ?CreateButtonPointerEnteredEventHandler@FlipView@DirectUI@@AEAAJPEAUIButtonBase@Primitives@Controls@Xaml@UI@Windows@@AEAV?$EventPtr@V?$event_handler@UIPointerEventHandler@Input@Xaml@UI@Windows@@UIInspectable@@UIPointerRoutedEventArgs@2345@UUIElementPointerEnteredTraits@DirectUI@@@ctl@@@ctl@@@Z; DirectUI::FlipView::CreateButtonPointerEnteredEventHandler(Windows::UI::Xaml::Controls::Primitives::IButtonBase *,ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs,DirectUI::UIElementPointerEnteredTraits>> &)
0x180952cdf  mov     edi, eax
0x180952ce1  test    eax, eax
0x180952ce3  js      loc_180952DCB
0x180952ce9  mov     rdx, [r15]; pButton
0x180952cec  lea     r8, [rsi+4B0h]; eventPtr
0x180952cf3  mov     this, r14; this
0x180952cf6  call    ?CreateButtonPointerExitedEventHandler@FlipView@DirectUI@@AEAAJPEAUIButtonBase@Primitives@Controls@Xaml@UI@Windows@@AEAV?$EventPtr@V?$event_handler@UIPointerEventHandler@Input@Xaml@UI@Windows@@UIInspectable@@UIPointerRoutedEventArgs@2345@UUIElementPointerExitedTraits@DirectUI@@@ctl@@@ctl@@@Z; DirectUI::FlipView::CreateButtonPointerExitedEventHandler(Windows::UI::Xaml::Controls::Primitives::IButtonBase *,ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs,DirectUI::UIElementPointerExitedTraits>> &)
0x180952cfb  mov     edi, eax
0x180952cfd  test    eax, eax
0x180952cff  js      loc_180952DBF
0x180952d05  mov     this, rbx; string
0x180952d08  call    cs:__imp_WindowsDeleteString
0x180952d0e  mov     this, [r15]
0x180952d11  lea     r8, [rbp+strAutomationName]; pValue
0x180952d15  mov     edx, 22h ; '"'; nPropertyIndex
0x180952d1a  mov     [rbp+strAutomationName._hstring], r13
0x180952d1e  lea     rax, [this-238h]
0x180952d25  neg     this
0x180952d28  sbb     this, this
0x180952d2b  and     this, rax; this
0x180952d2e  call    ?GetValueByKnownIndex@DependencyObject@DirectUI@@QEAAJW4KnownPropertyIndex@@PEAPEAUHSTRING__@@@Z; DirectUI::DependencyObject::GetValueByKnownIndex(KnownPropertyIndex,HSTRING__ * *)
0x180952d33  mov     edi, eax
0x180952d35  test    eax, eax
0x180952d37  js      short loc_180952DB3
0x180952d39  mov     rbx, [rbp+strAutomationName._hstring]
0x180952d3d  test    rbx, rbx
0x180952d40  jnz     loc_180952DD7
0x180952d46  call    ?GetCurrent@DXamlCore@DirectUI@@SAPEAV12@XZ; DirectUI::DXamlCore::GetCurrent(void)
0x180952d4b  xor     ecx, ecx; string
0x180952d4d  mov     rbx, rax
0x180952d50  call    cs:__imp_WindowsDeleteString
0x180952d56  lea     r8, [rbp+strAutomationName]; resourceString
0x180952d5a  mov     [rbp+strAutomationName._hstring], r13
0x180952d5e  mov     edx, 1483h; resourceStringID
0x180952d63  mov     this, rbx; this
0x180952d66  call    ?GetLocalizedResourceString@DXamlCore@DirectUI@@QEAAJIPEAPEAUHSTRING__@@@Z; DirectUI::DXamlCore::GetLocalizedResourceString(uint,HSTRING__ * *)
0x180952d6b  mov     edi, eax
0x180952d6d  test    eax, eax
0x180952d6f  js      short loc_180952DA7
0x180952d71  mov     this, [r15]
0x180952d74  mov     edx, 22h ; '"'; nPropertyIndex
0x180952d79  mov     rbx, [rbp+strAutomationName._hstring]
0x180952d7d  mov     r8, rbx; value
0x180952d80  lea     rax, [this-238h]
0x180952d87  neg     this
0x180952d8a  sbb     this, this
0x180952d8d  and     this, rax; this
0x180952d90  call    ?SetValueByKnownIndex@DependencyObject@DirectUI@@QEAAJW4KnownPropertyIndex@@PEAUHSTRING__@@@Z; DirectUI::DependencyObject::SetValueByKnownIndex(KnownPropertyIndex,HSTRING__ *)
0x180952d95  mov     edi, eax
  ... truncated ...
```
