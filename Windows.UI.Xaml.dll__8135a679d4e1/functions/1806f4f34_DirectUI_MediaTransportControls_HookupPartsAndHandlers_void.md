# DirectUI::MediaTransportControls::HookupPartsAndHandlers(void)

- ea: `0x1806f4f34`
- end: `0x1806f6a6d`
- name: `?HookupPartsAndHandlers@MediaTransportControls@DirectUI@@AEAAJXZ`
- size: `6969`
- prototype: `HRESULT __fastcall(DirectUI::MediaTransportControls *this)`
- caller_count: `1`
- callee_count: `69`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180b90a50`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x18000616c`
- `0x18000f730`
- `0x180017ba0`
- `0x18005626c`
- `0x18005b234`
- `0x18005e96c`
- `0x1800f2084`
- `0x1800f4510`
- `0x18011f390`
- `0x18011f3c0`
- `0x18011f5d0`
- `0x180131190`
- `0x1801d6730`
- `0x1801d94c0`
- `0x1801dce8c`
- `0x1801dcfa4`
- `0x1801df610`
- `0x1801dfeb0`
- `0x1801e5458`
- `0x18021e4e0`
- `0x1802e04dc`
- `0x1802fc1bc`
- `0x1802fc2cc`
- `0x1803002b4`
- `0x180303850`
- `0x180304c94`
- `0x180305124`
- `0x1803162a4`
- `0x1803839c0`
- `0x18038a9e4`
- `0x1803d81d8`
- `0x18042b550`
- `0x180453a04`
- `0x180456b20`
- `0x180544a7c`
- `0x1805b4bdc`
- `0x1805e7868`
- `0x1805f7e2c`
- `0x1805f8cd4`
- `0x1805ff204`
- `0x18064e57c`
- `0x180653fd8`
- `0x180661594`
- `0x1806615e0`
- `0x1806627bc`
- `0x18066dd50`
- `0x1806731cc`
- `0x1806cc604`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1806f6376`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1806f6376`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806f50c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806f5102`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806f512d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806f5296`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806f52d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806f543b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806f553d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806f563f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806f5742`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806f5858`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806f5892`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806f59db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806f50c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806f5102`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806f512d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806f5296`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806f52d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806f543b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806f553d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806f563f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806f5742`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806f5858`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806f5892`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806f59db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1806f635d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1806f635d`

## string_xrefs

- `0x1806f5a56`: `MediaControlsCommandBar`

## pseudocode

```c
__int64 __fastcall DirectUI::MediaTransportControls::HookupPartsAndHandlers(DirectUI::MediaTransportControls *this)
{
  Windows::UI::Xaml::Controls::IControlProtected *v1; // r13
  Windows::UI::Xaml::Controls::IControlProtected_vtbl *v2; // rax
  HSTRING__ *hstring; // rbx
  HSTRING__ *v5; // r14
  HRESULT (__fastcall *GetTemplateChild)(Windows::UI::Xaml::Controls::IControlProtected *, HSTRING__ *, Windows::UI::Xaml::IDependencyObject **); // rdi
  HSTRING__ **v7; // rax
  HRESULT DesiredBoundsMode; // eax
  HRESULT v9; // edi
  DesignerMode v10; // ecx
  DirectUI::MediaTransportControls *v11; // rcx
  HRESULT (__fastcall *v12)(Windows::UI::Xaml::Controls::IControlProtected *, HSTRING__ *, Windows::UI::Xaml::IDependencyObject **); // rdi
  HSTRING__ **v13; // rax
  DirectUI::TrackerPtr<Windows::UI::Xaml::IFrameworkElement,1,0> *p_m_tpTimeElapsedElement; // r15
  DirectUI::DXamlCore *Current; // rdi
  DirectUI::MediaTransportControls *v16; // rcx
  DirectUI::DXamlCore *v17; // rbx
  DirectUI::DXamlCore *v18; // rbx
  HRESULT (__fastcall *v19)(Windows::UI::Xaml::Controls::IControlProtected *, HSTRING__ *, Windows::UI::Xaml::IDependencyObject **); // rdi
  HSTRING__ **v20; // rax
  DirectUI::TrackerPtr<Windows::UI::Xaml::IFrameworkElement,1,0> *p_m_tpTimeRemainingElement; // r15
  DirectUI::DXamlCore *v22; // rdi
  DirectUI::MediaTransportControls *v23; // rcx
  DirectUI::DXamlCore *v24; // rdi
  HRESULT (__fastcall *v25)(Windows::UI::Xaml::Controls::IControlProtected *, HSTRING__ *, Windows::UI::Xaml::IDependencyObject **); // rbx
  HSTRING__ **v26; // rax
  DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::ISlider,1,0> *p_m_tpMediaPositionSlider; // r15
  DirectUI::DXamlCore *v28; // rbx
  HRESULT (__fastcall *v29)(Windows::UI::Xaml::Controls::IControlProtected *, HSTRING__ *, Windows::UI::Xaml::IDependencyObject **); // rbx
  HSTRING__ **v30; // rax
  DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::Primitives::IButtonBase,1,0> *p_m_tpPlayPauseButton; // r15
  DirectUI::DXamlCore *v32; // rbx
  HRESULT (__fastcall *v33)(Windows::UI::Xaml::Controls::IControlProtected *, HSTRING__ *, Windows::UI::Xaml::IDependencyObject **); // rbx
  HSTRING__ **v34; // rax
  DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::Primitives::IButtonBase,1,0> *p_m_tpTHLeftSidePlayPauseButton; // r15
  DirectUI::DXamlCore *v36; // rbx
  HRESULT (__fastcall *v37)(Windows::UI::Xaml::Controls::IControlProtected *, HSTRING__ *, Windows::UI::Xaml::IDependencyObject **); // rbx
  HSTRING__ **v38; // rax
  DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::Primitives::IButtonBase,1,0> *p_m_tpFullWindowButton; // r13
  DirectUI::DXamlCore *v40; // rbx
  HRESULT (__fastcall *v41)(Windows::UI::Xaml::Controls::IControlProtected *, HSTRING__ *, Windows::UI::Xaml::IDependencyObject **); // rbx
  HSTRING__ **v42; // rax
  DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::Primitives::IButtonBase,1,0> *p_m_tpZoomButton; // r12
  DirectUI::MediaTransportControls *v44; // rcx
  DirectUI::DXamlCore *v45; // rbx
  DirectUI::DXamlCore *v46; // rbx
  HRESULT (__fastcall *v47)(Windows::UI::Xaml::Controls::IControlProtected *, HSTRING__ *, Windows::UI::Xaml::IDependencyObject **); // rbx
  HSTRING__ **v48; // rax
  Windows::UI::Xaml::IDependencyObject *ptr; // rbx
  DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::ITextBlock,1,0> *p_m_tpErrorTextBlock; // r15
  int v51; // eax
  Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *> *v52; // rbx
  DirectUI::DXamlCore *v53; // rbx
  HRESULT (__fastcall *v54)(Windows::UI::Xaml::Controls::IControlProtected *, HSTRING__ *, Windows::UI::Xaml::IDependencyObject **); // rbx
  HSTRING__ **v55; // rax
  Windows::UI::Xaml::IDependencyObject *v56; // rbx
  ctl::WeakReferenceSourceNoThreadId *v57; // r15
  Windows::UI::Xaml::IFrameworkElement *v58; // rbx
  HRESULT (__fastcall *v59)(Windows::UI::Xaml::Controls::IControlProtected *, HSTRING__ *, Windows::UI::Xaml::IDependencyObject **); // rbx
  HSTRING__ **v60; // rax
  Windows::UI::Xaml::IDependencyObject *v61; // rbx
  Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *> *v62; // rbx
  IUnknown *m_value; // rcx
  IUnknown *v64; // rcx
  IUnknown *v65; // rcx
  IUnknown *v66; // rcx
  DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::ISlider,1,0> *v67; // r14
  IUnknown *v68; // rcx
  Windows::UI::Xaml::Controls::Primitives::IRangeBase *v69; // rdx
  Windows::UI::Xaml::Controls::Primitives::IRangeBase *v70; // rdx
  DirectUI::ClassMemberEventHandler<DirectUI::MediaTransportControls,Windows::UI::Xaml::Controls::IMediaTransportControls,Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs> *FailFast; // rax
  bool v72; // r9
  Windows::UI::Xaml::Input::IPointerEventHandler *v73; // rax
  Windows::UI::Xaml::Input::IPointerEventHandler *v74; // rbx
  DirectUI::ClassMemberEventHandler<DirectUI::MediaTransportControls,Windows::UI::Xaml::Controls::IMediaTransportControls,Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs> *v75; // rax
  bool v76; // r9
  Windows::UI::Xaml::Input::IPointerEventHandler *v77; // rax
  Windows::UI::Xaml::Input::IPointerEventHandler *v78; // rbx
  __int64 v79; // rcx
  __int64 v80; // rdx
  Windows::UI::Xaml::IDispatcherTimer *v81; // rdx
  DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::IGrid,1,0> *p_m_tpControlPanelGrid; // r14
  IUnknown *v83; // rcx
  __int64 v84; // rdx
  Windows::UI::Xaml::IUIElement *v85; // rdx
  __int64 v86; // rdx
  Windows::UI::Xaml::IUIElement *v87; // rdx
  __int64 v88; // rdx
  Windows::UI::Xaml::IUIElement *v89; // rdx
  __int64 v90; // rdx
  Windows::UI::Xaml::IUIElement *v91; // rdx
  __int64 v92; // rcx
  __int64 v93; // rdx
  Windows::UI::Xaml::IDispatcherTimer *v94; // rdx
  HRESULT v95; // eax
  Windows::UI::Xaml::IFrameworkElement *v96; // rdi
  HRESULT (__fastcall *FindName)(Windows::UI::Xaml::IFrameworkElement *, HSTRING__ *, IInspectable **); // rbx
  HSTRING__ **v98; // rax
  HRESULT (__fastcall *v99)(Windows::UI::Xaml::Controls::IControlProtected *, HSTRING__ *, Windows::UI::Xaml::IDependencyObject **); // rbx
  IUnknown *v100; // rcx
  IUnknown *v101; // rcx
  DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::Primitives::IFlyoutBase,1,0> *p_m_tpVolumeFlyout; // rbx
  IUnknown *v103; // rcx
  __int64 v104; // rdx
  Windows::UI::Xaml::Controls::Primitives::IFlyoutBase *v105; // rdx
  __int64 v106; // rcx
  __int64 v107; // rdx
  Windows::UI::Xaml::IDispatcherTimer *v108; // rdx
  ctl::ComPtr<Windows::UI::Xaml::IDependencyObject> spComponentAsDO; // [rsp+20h] [rbp-E0h] BYREF
  Windows::Internal::String strAutomationName; // [rsp+28h] [rbp-D8h] BYREF
  std::function<long __cdecl(IInspectable *,IInspectable *)> v112; // [rsp+30h] [rbp-D0h] BYREF
  ctl::ComPtr<IInspectable> spTranformAsII; // [rsp+70h] [rbp-90h] BYREF
  Windows::Internal::String strSkipString; // [rsp+78h] [rbp-88h] BYREF
  Windows::Internal::String strSeparator; // [rsp+80h] [rbp-80h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Input::IPointerEventHandler> spPositionSliderReleasedHandler; // [rsp+88h] [rbp-78h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Input::IPointerEventHandler> spPositionSliderPressedHandler; // [rsp+90h] [rbp-70h] BYREF
  ctl::ComPtr<DirectUI::DispatcherTimer> spPointerMoveEndTimer; // [rsp+98h] [rbp-68h] BYREF
  ctl::ComPtr<DirectUI::DispatcherTimer> spHideControlPanelTimer; // [rsp+A0h] [rbp-60h] BYREF
  ctl::ComPtr<DirectUI::DispatcherTimer> spPositionUpdateTimer; // [rsp+A8h] [rbp-58h] BYREF
  DirectUI::CRoutedEventSource<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs> *pPositionSliderReleasedEventSource; // [rsp+B0h] [rbp-50h] BYREF
  Windows::UI::Xaml::IFrameworkElement *v122; // [rsp+B8h] [rbp-48h]
  ctl::ComPtr<Windows::UI::Xaml::Input::IKeyEventHandler> spPositionSliderKeyUpHandler; // [rsp+C0h] [rbp-40h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Input::IKeyEventHandler> spPositionSliderKeyDownHandler; // [rsp+C8h] [rbp-38h] BYREF
  Windows::Internal::String strDefaultError; // [rsp+D0h] [rbp-30h] BYREF
  int v126; // [rsp+DCh] [rbp-24h]
  ctl::ComPtr<Windows::UI::Xaml::IFrameworkElement> spControlPanelGridAsIFE; // [rsp+E0h] [rbp-20h] BYREF
  DirectUI::MediaTransportControls *v128; // [rsp+E8h] [rbp-18h]
  ctl::ComPtr<Windows::UI::Xaml::IFrameworkElement> *p_spControlPanelGridAsIFE; // [rsp+118h] [rbp+18h]
  DirectUI::CRoutedEventSource<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs> *pPositionSliderPressedEventSource; // [rsp+120h] [rbp+20h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+128h] [rbp+28h] BYREF

  v1 = &this->Windows::UI::Xaml::Controls::IControlProtected;
  v2 = this->DirectUI::MediaTransportControlsGenerated::DirectUI::Control::DirectUI::ControlGenerated::Windows::UI::Xaml::Controls::IControlProtected::IInspectable::IUnknown::__vftable;
  hstring = 0;
  spComponentAsDO.ptr_ = 0;
  strDefaultError._hstring = 0;
  v5 = 0;
  strAutomationName._hstring = 0;
  GetTemplateChild = v2->GetTemplateChild;
  strSeparator._hstring = 0;
  strSkipString._hstring = 0;
  spPositionUpdateTimer.ptr_ = 0;
  spHideControlPanelTimer.ptr_ = 0;
  spPointerMoveEndTimer.ptr_ = 0;
  spPositionSliderPressedHandler.ptr_ = 0;
  pPositionSliderPressedEventSource = 0;
  spPositionSliderReleasedHandler.ptr_ = 0;
  pPositionSliderReleasedEventSource = 0;
  spPositionSliderKeyDownHandler.ptr_ = 0;
  spPositionSliderKeyUpHandler.ptr_ = 0;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spComponentAsDO);
  Windows::Internal::StringReference::StringReference(
    (Windows::Internal::StringReference *)&spControlPanelGridAsIFE,
    (const wchar_t (*)[17])L"ControlPanelGrid");
  DesiredBoundsMode = GetTemplateChild(v1, *v7, &spComponentAsDO.ptr_);
  v9 = DesiredBoundsMode;
  if ( DesiredBoundsMode < 0 )
    goto LABEL_246;
  ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::IGrid,Windows::UI::Xaml::IDependencyObject>(
    &this->ctl::WeakReferenceSourceNoThreadId,
    &this->m_tpControlPanelGrid,
    spComponentAsDO.ptr_);
  if ( this->m_tpControlPanelGrid.m_trackerReference.m_value )
  {
    if ( XboxUtility::IsOnXbox() )
    {
      LOBYTE(v10) = 1;
      if ( !DesignerInterop::GetDesignerMode(v10) )
      {
        LODWORD(spTranformAsII.ptr_) = 0;
        DesiredBoundsMode = DirectUI::MediaTransportControls::GetDesiredBoundsMode(
                              v11,
                              (Windows::UI::ViewManagement::ApplicationViewBoundsMode *)&spTranformAsII);
        v9 = DesiredBoundsMode;
        if ( DesiredBoundsMode < 0 )
          goto LABEL_246;
        if ( LODWORD(spTranformAsII.ptr_) == 1 )
        {
          DesiredBoundsMode = DirectUI::MediaTransportControls::UpdateSafeMargins(this, 1);
          v9 = DesiredBoundsMode;
          if ( DesiredBoundsMode < 0 )
            goto LABEL_246;
        }
      }
    }
  }
  v12 = v1->GetTemplateChild;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spComponentAsDO);
  Windows::Internal::StringReference::StringReference(
    (Windows::Internal::StringReference *)&spControlPanelGridAsIFE,
    (const wchar_t (*)[19])L"TimeElapsedElement");
  DesiredBoundsMode = v12(v1, *v13, &spComponentAsDO.ptr_);
  v9 = DesiredBoundsMode;
  if ( DesiredBoundsMode < 0 )
    goto LABEL_246;
  p_m_tpTimeElapsedElement = &this->m_tpTimeElapsedElement;
  ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::IFrameworkElement,Windows::UI::Xaml::IDependencyObject>(
    &this->ctl::WeakReferenceSourceNoThreadId,
    &this->m_tpTimeElapsedElement,
    spComponentAsDO.ptr_);
  if ( this->m_tpTimeElapsedElement.m_trackerReference.m_value )
  {
    Current = DirectUI::DXamlCore::GetCurrent();
    WindowsDeleteString(0);
    DesiredBoundsMode = DirectUI::DXamlCore::GetLocalizedResourceString(Current, 0x1486u, &strAutomationName._hstring);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    if ( DirectUI::MediaTransportControls::IsWindowsBlue(v16) )
    {
      v17 = DirectUI::DXamlCore::GetCurrent();
      WindowsDeleteString(0);
      DesiredBoundsMode = DirectUI::DXamlCore::GetLocalizedResourceString(v17, 0x148Au, &strSeparator._hstring);
      v9 = DesiredBoundsMode;
      if ( DesiredBoundsMode < 0 )
        goto LABEL_246;
      v18 = DirectUI::DXamlCore::GetCurrent();
      WindowsDeleteString(0);
      DesiredBoundsMode = DirectUI::DXamlCore::GetLocalizedResourceString(v18, 0x1487u, &strSkipString._hstring);
      v9 = DesiredBoundsMode;
      if ( DesiredBoundsMode < 0 )
        goto LABEL_246;
      DesiredBoundsMode = Windows::Internal::String::Concat(&strAutomationName, &strSeparator, &strAutomationName);
      v9 = DesiredBoundsMode;
      if ( DesiredBoundsMode < 0 )
        goto LABEL_246;
      DesiredBoundsMode = Windows::Internal::String::Concat(&strAutomationName, &strSkipString, &strAutomationName);
      v9 = DesiredBoundsMode;
      if ( DesiredBoundsMode < 0 )
        goto LABEL_246;
      hstring = strSkipString._hstring;
    }
    v5 = strAutomationName._hstring;
    DesiredBoundsMode = DirectUI::DependencyObject::SetValueByKnownIndex(
                          (DirectUI::DependencyObject *)((__int64)&p_m_tpTimeElapsedElement->m_trackerReference.m_value[-44]
                                                       & -(__int64)(p_m_tpTimeElapsedElement->m_trackerReference.m_value != 0)),
                          AutomationProperties_Name,
                          strAutomationName._hstring);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0
      || (DesiredBoundsMode = DirectUI::MediaTransportControls::AddTooltip(
                                (DirectUI::MediaTransportControls *)&p_m_tpTimeElapsedElement->m_trackerReference.m_value[-44],
                                (Windows::UI::Xaml::IDependencyObject *)((unsigned __int128)&p_m_tpTimeElapsedElement->m_trackerReference.m_value[-44]
                                                                       & ((unsigned __int128)-(__int128)(unsigned __int64)p_m_tpTimeElapsedElement->m_trackerReference.m_value >> 64)),
                                v5),
          v9 = DesiredBoundsMode,
          DesiredBoundsMode < 0) )
    {
LABEL_246:
      OnFailure_2990_(DesiredBoundsMode);
      goto $Cleanup_6469;
    }
  }
  v19 = v1->GetTemplateChild;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spComponentAsDO);
  Windows::Internal::StringReference::StringReference(
    (Windows::Internal::StringReference *)&spControlPanelGridAsIFE,
    (const wchar_t (*)[21])L"TimeRemainingElement");
  DesiredBoundsMode = v19(v1, *v20, &spComponentAsDO.ptr_);
  v9 = DesiredBoundsMode;
  if ( DesiredBoundsMode < 0 )
    goto LABEL_246;
  p_m_tpTimeRemainingElement = &this->m_tpTimeRemainingElement;
  ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::IFrameworkElement,Windows::UI::Xaml::IDependencyObject>(
    &this->ctl::WeakReferenceSourceNoThreadId,
    &this->m_tpTimeRemainingElement,
    spComponentAsDO.ptr_);
  if ( this->m_tpTimeRemainingElement.m_trackerReference.m_value )
  {
    v22 = DirectUI::DXamlCore::GetCurrent();
    WindowsDeleteString(v5);
    strAutomationName._hstring = 0;
    DesiredBoundsMode = DirectUI::DXamlCore::GetLocalizedResourceString(v22, 0x1488u, &strAutomationName._hstring);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    if ( DirectUI::MediaTransportControls::IsWindowsBlue(v23) )
    {
      v24 = DirectUI::DXamlCore::GetCurrent();
      WindowsDeleteString(hstring);
      strSkipString._hstring = 0;
      DesiredBoundsMode = DirectUI::DXamlCore::GetLocalizedResourceString(v24, 0x1489u, &strSkipString._hstring);
      v9 = DesiredBoundsMode;
      if ( DesiredBoundsMode < 0 )
        goto LABEL_246;
      DesiredBoundsMode = Windows::Internal::String::Concat(&strAutomationName, &strSeparator, &strAutomationName);
      v9 = DesiredBoundsMode;
      if ( DesiredBoundsMode < 0 )
        goto LABEL_246;
      DesiredBoundsMode = Windows::Internal::String::Concat(&strAutomationName, &strSkipString, &strAutomationName);
      v9 = DesiredBoundsMode;
      if ( DesiredBoundsMode < 0 )
        goto LABEL_246;
    }
    v5 = strAutomationName._hstring;
    DesiredBoundsMode = DirectUI::DependencyObject::SetValueByKnownIndex(
                          (DirectUI::DependencyObject *)((__int64)&p_m_tpTimeRemainingElement->m_trackerReference.m_value[-44]
                                                       & -(__int64)(p_m_tpTimeRemainingElement->m_trackerReference.m_value != 0)),
                          AutomationProperties_Name,
                          strAutomationName._hstring);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    DesiredBoundsMode = DirectUI::MediaTransportControls::AddTooltip(
                          (DirectUI::MediaTransportControls *)&p_m_tpTimeRemainingElement->m_trackerReference.m_value[-44],
                          (Windows::UI::Xaml::IDependencyObject *)((unsigned __int128)&p_m_tpTimeRemainingElement->m_trackerReference.m_value[-44]
                                                                 & ((unsigned __int128)-(__int128)(unsigned __int64)p_m_tpTimeRemainingElement->m_trackerReference.m_value >> 64)),
                          v5);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
  }
  v25 = v1->GetTemplateChild;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spComponentAsDO);
  Windows::Internal::StringReference::StringReference(
    (Windows::Internal::StringReference *)&spControlPanelGridAsIFE,
    (const wchar_t (*)[15])L"ProgressSlider");
  DesiredBoundsMode = v25(v1, *v26, &spComponentAsDO.ptr_);
  v9 = DesiredBoundsMode;
  if ( DesiredBoundsMode < 0 )
    goto LABEL_246;
  p_m_tpMediaPositionSlider = &this->m_tpMediaPositionSlider;
  ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::ISlider,Windows::UI::Xaml::IDependencyObject>(
    &this->ctl::WeakReferenceSourceNoThreadId,
    &this->m_tpMediaPositionSlider,
    spComponentAsDO.ptr_);
  if ( this->m_tpMediaPositionSlider.m_trackerReference.m_value )
  {
    BYTE1(this->m_tpMediaPositionSlider.m_trackerReference.m_value[65].__vftable) = 1;
    v28 = DirectUI::DXamlCore::GetCurrent();
    WindowsDeleteString(v5);
    strAutomationName._hstring = 0;
    DesiredBoundsMode = DirectUI::DXamlCore::GetLocalizedResourceString(v28, 0x148Du, &strAutomationName._hstring);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    v5 = strAutomationName._hstring;
    DesiredBoundsMode = DirectUI::DependencyObject::SetValueByKnownIndex(
                          (DirectUI::DependencyObject *)((__int64)&p_m_tpMediaPositionSlider->m_trackerReference.m_value[-74]
                                                       & -(__int64)(p_m_tpMediaPositionSlider->m_trackerReference.m_value != 0)),
                          AutomationProperties_Name,
                          strAutomationName._hstring);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    DesiredBoundsMode = DirectUI::MediaTransportControls::AddTooltip(
                          (DirectUI::MediaTransportControls *)&p_m_tpMediaPositionSlider->m_trackerReference.m_value[-74],
                          (Windows::UI::Xaml::IDependencyObject *)((unsigned __int128)&p_m_tpMediaPositionSlider->m_trackerReference.m_value[-74]
                                                                 & ((unsigned __int128)-(__int128)(unsigned __int64)p_m_tpMediaPositionSlider->m_trackerReference.m_value >> 64)),
                          v5);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
  }
  v29 = v1->GetTemplateChild;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spComponentAsDO);
  Windows::Internal::StringReference::StringReference(
    (Windows::Internal::StringReference *)&spControlPanelGridAsIFE,
    (const wchar_t (*)[16])L"PlayPauseButton");
  DesiredBoundsMode = v29(v1, *v30, &spComponentAsDO.ptr_);
  v9 = DesiredBoundsMode;
  if ( DesiredBoundsMode < 0 )
    goto LABEL_246;
  p_m_tpPlayPauseButton = &this->m_tpPlayPauseButton;
  ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::Primitives::IButtonBase,Windows::UI::Xaml::IDependencyObject>(
    &this->ctl::WeakReferenceSourceNoThreadId,
    &this->m_tpPlayPauseButton,
    spComponentAsDO.ptr_);
  if ( this->m_tpPlayPauseButton.m_trackerReference.m_value )
  {
    v32 = DirectUI::DXamlCore::GetCurrent();
    WindowsDeleteString(v5);
    strAutomationName._hstring = 0;
    DesiredBoundsMode = DirectUI::DXamlCore::GetLocalizedResourceString(v32, 0x1484u, &strAutomationName._hstring);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    v5 = strAutomationName._hstring;
    DesiredBoundsMode = DirectUI::DependencyObject::SetValueByKnownIndex(
                          (DirectUI::DependencyObject *)((__int64)&p_m_tpPlayPauseButton->m_trackerReference.m_value[-71]
                                                       & -(__int64)(p_m_tpPlayPauseButton->m_trackerReference.m_value != 0)),
                          AutomationProperties_Name,
                          strAutomationName._hstring);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    DesiredBoundsMode = DirectUI::MediaTransportControls::AddTooltip(
                          (DirectUI::MediaTransportControls *)&p_m_tpPlayPauseButton->m_trackerReference.m_value[-71],
                          (Windows::UI::Xaml::IDependencyObject *)((unsigned __int128)&p_m_tpPlayPauseButton->m_trackerReference.m_value[-71]
                                                                 & ((unsigned __int128)-(__int128)(unsigned __int64)p_m_tpPlayPauseButton->m_trackerReference.m_value >> 64)),
                          v5);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
  }
  v33 = v1->GetTemplateChild;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spComponentAsDO);
  Windows::Internal::StringReference::StringReference(
    (Windows::Internal::StringReference *)&spControlPanelGridAsIFE,
    (const wchar_t (*)[22])L"PlayPauseButtonOnLeft");
  DesiredBoundsMode = v33(v1, *v34, &spComponentAsDO.ptr_);
  v9 = DesiredBoundsMode;
  if ( DesiredBoundsMode < 0 )
    goto LABEL_246;
  p_m_tpTHLeftSidePlayPauseButton = &this->m_tpTHLeftSidePlayPauseButton;
  ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::Primitives::IButtonBase,Windows::UI::Xaml::IDependencyObject>(
    &this->ctl::WeakReferenceSourceNoThreadId,
    &this->m_tpTHLeftSidePlayPauseButton,
    spComponentAsDO.ptr_);
  if ( this->m_tpTHLeftSidePlayPauseButton.m_trackerReference.m_value )
  {
    v36 = DirectUI::DXamlCore::GetCurrent();
    WindowsDeleteString(v5);
    strAutomationName._hstring = 0;
    DesiredBoundsMode = DirectUI::DXamlCore::GetLocalizedResourceString(v36, 0x1484u, &strAutomationName._hstring);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    v5 = strAutomationName._hstring;
    DesiredBoundsMode = DirectUI::DependencyObject::SetValueByKnownIndex(
                          (DirectUI::DependencyObject *)((__int64)&p_m_tpTHLeftSidePlayPauseButton->m_trackerReference.m_value[-71]
                                                       & -(__int64)(p_m_tpTHLeftSidePlayPauseButton->m_trackerReference.m_value != 0)),
                          AutomationProperties_Name,
                          strAutomationName._hstring);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    DesiredBoundsMode = DirectUI::MediaTransportControls::AddTooltip(
                          (DirectUI::MediaTransportControls *)&p_m_tpTHLeftSidePlayPauseButton->m_trackerReference.m_value[-71],
                          (Windows::UI::Xaml::IDependencyObject *)((unsigned __int128)&p_m_tpTHLeftSidePlayPauseButton->m_trackerReference.m_value[-71]
                                                                 & ((unsigned __int128)-(__int128)(unsigned __int64)p_m_tpTHLeftSidePlayPauseButton->m_trackerReference.m_value >> 64)),
                          v5);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
  }
  v37 = v1->GetTemplateChild;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spComponentAsDO);
  Windows::Internal::StringReference::StringReference(
    (Windows::Internal::StringReference *)&spControlPanelGridAsIFE,
    (const wchar_t (*)[17])L"FullWindowButton");
  DesiredBoundsMode = v37(v1, *v38, &spComponentAsDO.ptr_);
  v9 = DesiredBoundsMode;
  if ( DesiredBoundsMode < 0 )
    goto LABEL_246;
  p_m_tpFullWindowButton = &this->m_tpFullWindowButton;
  ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::Primitives::IButtonBase,Windows::UI::Xaml::IDependencyObject>(
    &this->ctl::WeakReferenceSourceNoThreadId,
    &this->m_tpFullWindowButton,
    spComponentAsDO.ptr_);
  if ( this->m_tpFullWindowButton.m_trackerReference.m_value )
  {
    v40 = DirectUI::DXamlCore::GetCurrent();
    WindowsDeleteString(v5);
    strAutomationName._hstring = 0;
    DesiredBoundsMode = DirectUI::DXamlCore::GetLocalizedResourceString(v40, 0x149Bu, &strAutomationName._hstring);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    v5 = strAutomationName._hstring;
    DesiredBoundsMode = DirectUI::DependencyObject::SetValueByKnownIndex(
                          (DirectUI::DependencyObject *)((__int64)&p_m_tpFullWindowButton->m_trackerReference.m_value[-71]
                                                       & -(__int64)(p_m_tpFullWindowButton->m_trackerReference.m_value != 0)),
                          AutomationProperties_Name,
                          strAutomationName._hstring);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    DesiredBoundsMode = DirectUI::MediaTransportControls::AddTooltip(
                          (DirectUI::MediaTransportControls *)&p_m_tpFullWindowButton->m_trackerReference.m_value[-71],
                          (Windows::UI::Xaml::IDependencyObject *)((unsigned __int128)&p_m_tpFullWindowButton->m_trackerReference.m_value[-71]
                                                                 & ((unsigned __int128)-(__int128)(unsigned __int64)p_m_tpFullWindowButton->m_trackerReference.m_value >> 64)),
                          v5);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
  }
  v41 = this->GetTemplateChild;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spComponentAsDO);
  Windows::Internal::StringReference::StringReference(
    (Windows::Internal::StringReference *)&spControlPanelGridAsIFE,
    (const wchar_t (*)[11])L"ZoomButton");
  DesiredBoundsMode = v41(&this->Windows::UI::Xaml::Controls::IControlProtected, *v42, &spComponentAsDO.ptr_);
  v9 = DesiredBoundsMode;
  if ( DesiredBoundsMode < 0 )
    goto LABEL_246;
  p_m_tpZoomButton = &this->m_tpZoomButton;
  ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::Primitives::IButtonBase,Windows::UI::Xaml::IDependencyObject>(
    &this->ctl::WeakReferenceSourceNoThreadId,
    &this->m_tpZoomButton,
    spComponentAsDO.ptr_);
  if ( this->m_tpZoomButton.m_trackerReference.m_value )
  {
    if ( DirectUI::MediaTransportControls::IsThreshold(v44) )
    {
      v45 = DirectUI::DXamlCore::GetCurrent();
      WindowsDeleteString(v5);
      strAutomationName._hstring = 0;
      DesiredBoundsMode = DirectUI::DXamlCore::GetLocalizedResourceString(v45, 0x14BAu, &strAutomationName._hstring);
      v9 = DesiredBoundsMode;
      if ( DesiredBoundsMode < 0 )
        goto LABEL_246;
    }
    else
    {
      v46 = DirectUI::DXamlCore::GetCurrent();
      WindowsDeleteString(v5);
      strAutomationName._hstring = 0;
      DesiredBoundsMode = DirectUI::DXamlCore::GetLocalizedResourceString(v46, 0x149Fu, &strAutomationName._hstring);
      v9 = DesiredBoundsMode;
      if ( DesiredBoundsMode < 0 )
        goto LABEL_246;
    }
    v5 = strAutomationName._hstring;
    DesiredBoundsMode = DirectUI::DependencyObject::SetValueByKnownIndex(
                          (DirectUI::DependencyObject *)((__int64)&p_m_tpZoomButton->m_trackerReference.m_value[-71]
                                                       & -(__int64)(p_m_tpZoomButton->m_trackerReference.m_value != 0)),
                          AutomationProperties_Name,
                          strAutomationName._hstring);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    DesiredBoundsMode = DirectUI::MediaTransportControls::AddTooltip(
                          (DirectUI::MediaTransportControls *)&p_m_tpZoomButton->m_trackerReference.m_value[-71],
                          (Windows::UI::Xaml::IDependencyObject *)((unsigned __int128)&p_m_tpZoomButton->m_trackerReference.m_value[-71]
                                                                 & ((unsigned __int128)-(__int128)(unsigned __int64)p_m_tpZoomButton->m_trackerReference.m_value >> 64)),
                          v5);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
  }
  v47 = this->GetTemplateChild;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spComponentAsDO);
  Windows::Internal::StringReference::StringReference(
    (Windows::Internal::StringReference *)&spControlPanelGridAsIFE,
    (const wchar_t (*)[15])L"ErrorTextBlock");
  DesiredBoundsMode = v47(&this->Windows::UI::Xaml::Controls::IControlProtected, *v48, &spComponentAsDO.ptr_);
  v9 = DesiredBoundsMode;
  if ( DesiredBoundsMode < 0 )
    goto LABEL_246;
  ptr = spComponentAsDO.ptr_;
  p_m_tpErrorTextBlock = &this->m_tpErrorTextBlock;
  ctl::WeakReferenceSourceNoThreadId::RegisterPtr(
    &this->ctl::WeakReferenceSourceNoThreadId,
    &this->m_tpErrorTextBlock.m_trackerReference);
  spControlPanelGridAsIFE.ptr_ = 0;
  if ( !ptr
    || (v51 = ptr->QueryInterface(
                ptr,
                &GUID_ae2d9271_3b4a_45fc_8468_f7949548f4d5,
                (void **)&spControlPanelGridAsIFE.ptr_),
        v52 = (Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *> *)spControlPanelGridAsIFE.ptr_,
        v51 < 0) )
  {
    v52 = 0;
  }
  DirectUI::TrackerPtr<Windows::UI::Xaml::Interop::IBindableVector,1,0>::Set<Windows::UI::Xaml::Interop::IBindableVector>(
    (DirectUI::TrackerPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,1,0> *)&this->m_tpErrorTextBlock,
    v52);
  if ( v52 )
    v52->Release(v52);
  if ( p_m_tpErrorTextBlock->m_trackerReference.m_value )
  {
    v53 = DirectUI::DXamlCore::GetCurrent();
    WindowsDeleteString(v5);
    strAutomationName._hstring = 0;
    DesiredBoundsMode = DirectUI::DXamlCore::GetLocalizedResourceString(v53, 0x1490u, &strAutomationName._hstring);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    DesiredBoundsMode = DirectUI::DependencyObject::SetValueByKnownIndex(
                          (DirectUI::DependencyObject *)((__int64)&p_m_tpErrorTextBlock->m_trackerReference.m_value[-56]
                                                       & -(__int64)(p_m_tpErrorTextBlock->m_trackerReference.m_value != 0)),
                          AutomationProperties_Name,
                          strAutomationName._hstring);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
  }
  v54 = this->GetTemplateChild;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spComponentAsDO);
  Windows::Internal::StringReference::StringReference(
    (Windows::Internal::StringReference *)&spControlPanelGridAsIFE,
    (const wchar_t (*)[24])L"MediaControlsCommandBar");
  DesiredBoundsMode = v54(&this->Windows::UI::Xaml::Controls::IControlProtected, *v55, &spComponentAsDO.ptr_);
  v9 = DesiredBoundsMode;
  if ( DesiredBoundsMode < 0 )
    goto LABEL_246;
  v56 = spComponentAsDO.ptr_;
  v57 = &this->ctl::WeakReferenceSourceNoThreadId;
  ctl::WeakReferenceSourceNoThreadId::RegisterPtr(
    &this->ctl::WeakReferenceSourceNoThreadId,
    &this->m_tpCommandBar.m_trackerReference);
  spControlPanelGridAsIFE.ptr_ = 0;
  if ( v56
    && v56->QueryInterface(v56, &GUID_98bc4280_4a3d_4cee_bd07_22ce94c5af76, (void **)&spControlPanelGridAsIFE.ptr_) >= 0
    && (v58 = spControlPanelGridAsIFE.ptr_) != 0 )
  {
    DirectUI::TrackerTargetReference::Set(&this->m_tpCommandBar.m_trackerReference, spControlPanelGridAsIFE.ptr_, 1u, 0);
    v58->Release(v58);
  }
  else
  {
    DirectUI::TrackerTargetReference::Clear(&this->m_tpCommandBar.m_trackerReference, 1u, 0);
  }
  v59 = this->GetTemplateChild;
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spComponentAsDO);
  Windows::Internal::StringReference::StringReference(
    (Windows::Internal::StringReference *)&spControlPanelGridAsIFE,
    (const wchar_t (*)[13])L"VolumeFlyout");
  DesiredBoundsMode = v59(&this->Windows::UI::Xaml::Controls::IControlProtected, *v60, &spComponentAsDO.ptr_);
  v9 = DesiredBoundsMode;
  if ( DesiredBoundsMode < 0 )
    goto LABEL_246;
  v61 = spComponentAsDO.ptr_;
  ctl::WeakReferenceSourceNoThreadId::RegisterPtr(
    &this->ctl::WeakReferenceSourceNoThreadId,
    &this->m_tpVolumeFlyout.m_trackerReference);
  spControlPanelGridAsIFE.ptr_ = 0;
  if ( v61
    && v61->QueryInterface(v61, &GUID_723eea0b_d12e_430d_a9f0_9bb32bbf9913, (void **)&spControlPanelGridAsIFE.ptr_) >= 0 )
  {
    v62 = (Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *> *)spControlPanelGridAsIFE.ptr_;
  }
  else
  {
    v62 = 0;
  }
  DirectUI::TrackerPtr<Windows::UI::Xaml::Interop::IBindableVector,1,0>::Set<Windows::UI::Xaml::Interop::IBindableVector>(
    (DirectUI::TrackerPtr<Windows::Foundation::ITypedEventHandler<IInspectable *,IInspectable *>,1,0> *)&this->m_tpVolumeFlyout,
    v62);
  if ( v62 )
    v62->Release(v62);
  v128 = this;
  spControlPanelGridAsIFE.ptr_ = (Windows::UI::Xaml::IFrameworkElement *)std::_Func_impl_no_alloc__lambda_a1bf92ad3f80051babfb0a1761b009b0__long_IInspectable___Windows::UI::Xaml::IRoutedEventArgs___::_vftable_;
  p_spControlPanelGridAsIFE = &spControlPanelGridAsIFE;
  v122 = (Windows::UI::Xaml::IFrameworkElement *)((unsigned __int64)&this->Windows::UI::Xaml::IFrameworkElement
                                                & -(__int64)(this != 0));
  DesiredBoundsMode = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::FrameworkElementLoadedTraits>>::AttachEventHandler(
                        &this->m_epRootUserControlLoadedHandler,
                        v122,
                        (std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *)> *)&spControlPanelGridAsIFE);
  v9 = DesiredBoundsMode;
  if ( DesiredBoundsMode < 0 )
    goto LABEL_246;
  m_value = this->m_tpPlayPauseButton.m_trackerReference.m_value;
  if ( m_value )
  {
    v128 = this;
    spControlPanelGridAsIFE.ptr_ = (Windows::UI::Xaml::IFrameworkElement *)std::_Func_impl_no_alloc__lambda_7b29e144506b0e678042d20afcfe2ebf__long_IInspectable___Windows::UI::Xaml::IRoutedEventArgs___::_vftable_;
    p_spControlPanelGridAsIFE = &spControlPanelGridAsIFE;
    DesiredBoundsMode = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::ButtonBaseClickTraits>>::AttachEventHandler(
                          &this->m_epPlayPauseButtonClickHandler,
                          (Windows::UI::Xaml::Controls::Primitives::IButtonBase *)((unsigned __int64)m_value
                                                                                 & ((unsigned __int128)-(__int128)(unsigned __int64)&m_value[-71] >> 64)),
                          (std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *)> *)&spControlPanelGridAsIFE);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
  }
  v64 = this->m_tpTHLeftSidePlayPauseButton.m_trackerReference.m_value;
  if ( v64 )
  {
    v128 = this;
    spControlPanelGridAsIFE.ptr_ = (Windows::UI::Xaml::IFrameworkElement *)std::_Func_impl_no_alloc__lambda_98c4ab0136a4d44385ddb0b4b58ccb85__long_IInspectable___Windows::UI::Xaml::IRoutedEventArgs___::_vftable_;
    p_spControlPanelGridAsIFE = &spControlPanelGridAsIFE;
    DesiredBoundsMode = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::ButtonBaseClickTraits>>::AttachEventHandler(
                          &this->m_epLeftsidePlayPauseButtonClickHandler,
                          (Windows::UI::Xaml::Controls::Primitives::IButtonBase *)((unsigned __int64)v64
                                                                                 & ((unsigned __int128)-(__int128)(unsigned __int64)&v64[-71] >> 64)),
                          (std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *)> *)&spControlPanelGridAsIFE);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
  }
  v65 = p_m_tpFullWindowButton->m_trackerReference.m_value;
  if ( p_m_tpFullWindowButton->m_trackerReference.m_value )
  {
    v128 = this;
    spControlPanelGridAsIFE.ptr_ = (Windows::UI::Xaml::IFrameworkElement *)std::_Func_impl_no_alloc__lambda_48e1e189615d607a0a002e6c440a6416__long_IInspectable___Windows::UI::Xaml::IRoutedEventArgs___::_vftable_;
    p_spControlPanelGridAsIFE = &spControlPanelGridAsIFE;
    DesiredBoundsMode = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::ButtonBaseClickTraits>>::AttachEventHandler(
                          &this->m_epFullWindowButtonClickHandler,
                          (Windows::UI::Xaml::Controls::Primitives::IButtonBase *)((unsigned __int64)v65
                                                                                 & ((unsigned __int128)-(__int128)(unsigned __int64)&v65[-71] >> 64)),
                          (std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *)> *)&spControlPanelGridAsIFE);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
  }
  v66 = p_m_tpZoomButton->m_trackerReference.m_value;
  if ( p_m_tpZoomButton->m_trackerReference.m_value )
  {
    v128 = this;
    spControlPanelGridAsIFE.ptr_ = (Windows::UI::Xaml::IFrameworkElement *)std::_Func_impl_no_alloc__lambda_0c224af64d4b961deadf0b38024b8610__long_IInspectable___Windows::UI::Xaml::IRoutedEventArgs___::_vftable_;
    p_spControlPanelGridAsIFE = &spControlPanelGridAsIFE;
    DesiredBoundsMode = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::ButtonBaseClickTraits>>::AttachEventHandler(
                          &this->m_epZoomButtonClickHandler,
                          (Windows::UI::Xaml::Controls::Primitives::IButtonBase *)((unsigned __int64)v66
                                                                                 & ((unsigned __int128)-(__int128)(unsigned __int64)&v66[-71] >> 64)),
                          (std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *)> *)&spControlPanelGridAsIFE);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
  }
  v67 = &this->m_tpMediaPositionSlider;
  v68 = this->m_tpMediaPositionSlider.m_trackerReference.m_value;
  if ( v68 )
  {
    v128 = this;
    spControlPanelGridAsIFE.ptr_ = (Windows::UI::Xaml::IFrameworkElement *)std::_Func_impl_no_alloc__lambda_37a41a575a9453541d65a81f1c42b2d1__long_IInspectable___Windows::UI::Xaml::ISizeChangedEventArgs___::_vftable_;
    p_spControlPanelGridAsIFE = &spControlPanelGridAsIFE;
    DesiredBoundsMode = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::ISizeChangedEventHandler,IInspectable,Windows::UI::Xaml::ISizeChangedEventArgs,DirectUI::FrameworkElementSizeChangedTraits>>::AttachEventHandler(
                          &this->m_epProgressSliderSizeChangedHandler,
                          (Windows::UI::Xaml::IFrameworkElement *)((unsigned __int64)&v68[-30]
                                                                 & ((unsigned __int128)-(__int128)(unsigned __int64)&v68[-74] >> 64)),
                          (std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::ISizeChangedEventArgs *)> *)&spControlPanelGridAsIFE);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    v112._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,IInspectable *> *)this;
    v112._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,IInspectable *> *)std::_Func_impl_no_alloc__lambda_d0633b999a419ba1e76d6c2edfb445d6__long_Windows::UI::Xaml::Controls::IControl___Windows::UI::Xaml::Controls::IFocusDisengagedEventArgs___::_vftable_;
    spControlPanelGridAsIFE.ptr_ = 0;
    v112._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,IInspectable *> *)&v112;
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spControlPanelGridAsIFE);
    if ( v67->m_trackerReference.m_value )
      v67->m_trackerReference.m_value->QueryInterface(
        v67->m_trackerReference.m_value,
        &GUID_0e18aeee_5f2e_44ea_8513_d3875c0a7513,
        (void **)&spControlPanelGridAsIFE.ptr_);
    v9 = ctl::EventPtr<ctl::event_handler<Windows::Foundation::ITypedEventHandler<Windows::UI::Xaml::Controls::Control *,Windows::UI::Xaml::Controls::FocusDisengagedEventArgs *>,Windows::UI::Xaml::Controls::IControl,Windows::UI::Xaml::Controls::IFocusDisengagedEventArgs,DirectUI::Control4FocusDisengagedTraits>>::AttachEventHandler(
           &this->m_epProgressSliderFocusDisengagedHandler,
           (Windows::UI::Xaml::Controls::IControl4 *)spControlPanelGridAsIFE.ptr_,
           (std::function<long __cdecl(Windows::UI::Xaml::Controls::IControl *,Windows::UI::Xaml::Controls::IFocusDisengagedEventArgs *)> *)&v112);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spControlPanelGridAsIFE);
    if ( v9 < 0 )
    {
      OnFailure_2990_(v9);
      goto $Cleanup_6469;
    }
    v112._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,IInspectable *> *)this;
    v112._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,IInspectable *> *)std::_Func_impl_no_alloc__lambda_4dac570a38b8e6531ecece23f97d3a73__long_IInspectable___Windows::UI::Xaml::Controls::Primitives::IRangeBaseValueChangedEventArgs___::_vftable_;
    v112._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,IInspectable *> *)&v112;
    v69 = (Windows::UI::Xaml::Controls::Primitives::IRangeBase *)((unsigned __int128)&v67->m_trackerReference.m_value[-74]
                                                                & ((unsigned __int128)-(__int128)(unsigned __int64)v67->m_trackerReference.m_value >> 64));
    if ( v69 )
      v70 = v69 + 67;
    else
      v70 = 0;
    DesiredBoundsMode = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Controls::Primitives::IRangeBaseValueChangedEventHandler,IInspectable,Windows::UI::Xaml::Controls::Primitives::IRangeBaseValueChangedEventArgs,DirectUI::RangeBaseValueChangedTraits>>::AttachEventHandler(
                          &this->m_epPositionChangedHandler,
                          v70,
                          (std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::Controls::Primitives::IRangeBaseValueChangedEventArgs *)> *)&v112);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    FailFast = (DirectUI::ClassMemberEventHandler<DirectUI::MediaTransportControls,Windows::UI::Xaml::Controls::IMediaTransportControls,Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs> *)XcpAllocation::OSMemoryAllocateFailFast(0x28u);
    if ( FailFast )
    {
      LODWORD(v128) = 0;
      spControlPanelGridAsIFE.ptr_ = (Windows::UI::Xaml::IFrameworkElement *)DirectUI::MediaTransportControls::OnPositionSliderPressed;
      HIDWORD(v128) = v126;
      DirectUI::ClassMemberEventHandler<DirectUI::MediaTransportControls,Windows::UI::Xaml::Controls::IMediaTransportControls,Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs>::ClassMemberEventHandler<DirectUI::MediaTransportControls,Windows::UI::Xaml::Controls::IMediaTransportControls,Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs>(
        FailFast,
        (ctl::WeakReferenceSourceNoThreadId *)((unsigned __int64)v57 & -(__int64)(this != 0)),
        (__int128 *)&spControlPanelGridAsIFE,
        v72);
    }
    else
    {
      v73 = 0;
    }
    ctl::ComPtr<Windows::UI::Xaml::Input::IPointerEventHandler>::Attach(&spPositionSliderPressedHandler, v73);
    DesiredBoundsMode = DirectUI::UIElementGenerated::GetPointerPressedEventSourceNoRef(
                          (DirectUI::UIElementGenerated *)(-(__int64)(v67->m_trackerReference.m_value != 0)
                                                         & (__int64)&v67->m_trackerReference.m_value[-74]),
                          &pPositionSliderPressedEventSource);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    v74 = spPositionSliderPressedHandler.ptr_;
    DesiredBoundsMode = DirectUI::CRoutedEventSource<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs>::AddHandler(
                          pPositionSliderPressedEventSource,
                          spPositionSliderPressedHandler.ptr_,
                          1u);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    this->m_positionSliderPressedEventToken.value = (__int64)v74;
    v75 = (DirectUI::ClassMemberEventHandler<DirectUI::MediaTransportControls,Windows::UI::Xaml::Controls::IMediaTransportControls,Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs> *)XcpAllocation::OSMemoryAllocateFailFast(0x28u);
    if ( v75 )
    {
      LODWORD(hstringHeader.Reserved.Reserved1) = 0;
      pPositionSliderPressedEventSource = (DirectUI::CRoutedEventSource<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs> *)DirectUI::MediaTransportControls::OnPositionSliderReleased;
      *(_DWORD *)&hstringHeader.Reserved.Reserved2[4] = v126;
      DirectUI::ClassMemberEventHandler<DirectUI::MediaTransportControls,Windows::UI::Xaml::Controls::IMediaTransportControls,Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs>::ClassMemberEventHandler<DirectUI::MediaTransportControls,Windows::UI::Xaml::Controls::IMediaTransportControls,Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs>(
        v75,
        (ctl::WeakReferenceSourceNoThreadId *)((unsigned __int64)v57 & -(__int64)(this != 0)),
        (__int128 *)&pPositionSliderPressedEventSource,
        v76);
    }
    else
    {
      v77 = 0;
    }
    ctl::ComPtr<Windows::UI::Xaml::Input::IPointerEventHandler>::Attach(&spPositionSliderReleasedHandler, v77);
    DesiredBoundsMode = DirectUI::UIElementGenerated::GetPointerReleasedEventSourceNoRef(
                          (DirectUI::UIElementGenerated *)(-(__int64)(v67->m_trackerReference.m_value != 0)
                                                         & (__int64)&v67->m_trackerReference.m_value[-74]),
                          &pPositionSliderReleasedEventSource);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    v78 = spPositionSliderReleasedHandler.ptr_;
    DesiredBoundsMode = DirectUI::CRoutedEventSource<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs>::AddHandler(
                          pPositionSliderReleasedEventSource,
                          spPositionSliderReleasedHandler.ptr_,
                          1u);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    this->m_positionSliderReleasedEventToken.value = (__int64)v78;
    DesiredBoundsMode = ctl::make<DirectUI::DispatcherTimer>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::DispatcherTimer> >)&spPositionUpdateTimer);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::IDispatcherTimer,DirectUI::DispatcherTimer>(
      &this->ctl::WeakReferenceSourceNoThreadId,
      &this->m_tpPositionUpdateTimer,
      spPositionUpdateTimer.ptr_);
    v79 = (__int64)this->m_tpPositionUpdateTimer.m_trackerReference.m_value;
    if ( !v79 )
      v79 = 192;
    DesiredBoundsMode = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v79 + 56LL))(v79, 2500000);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    v112._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,IInspectable *> *)this;
    v112._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,IInspectable *> *)std::_Func_impl_no_alloc__lambda_d8cd5f29bee0daec97b1aae051dd4ad4__long_IInspectable___IInspectable___::_vftable_;
    v112._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,IInspectable *> *)&v112;
    v80 = (unsigned __int128)&this->m_tpPositionUpdateTimer.m_trackerReference.m_value[-24]
        & ((unsigned __int128)-(__int128)(unsigned __int64)this->m_tpPositionUpdateTimer.m_trackerReference.m_value >> 64);
    v81 = v80 ? (Windows::UI::Xaml::IDispatcherTimer *)(v80 + 192) : 0LL;
    DesiredBoundsMode = ctl::EventPtr<ctl::event_handler<Windows::Foundation::IEventHandler<IInspectable *>,IInspectable,IInspectable,DirectUI::DispatcherTimerTickTraits>>::AttachEventHandler(
                          &this->m_epPositionUpdateTimerTickHandler,
                          v81,
                          &v112);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    DesiredBoundsMode = DirectUI::MediaTransportControls::EnableValueChangedEventThrottlingOnSliderAutomation(this, 1);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
  }
  p_m_tpControlPanelGrid = &this->m_tpControlPanelGrid;
  v83 = this->m_tpControlPanelGrid.m_trackerReference.m_value;
  if ( v83 )
  {
    v112._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,IInspectable *> *)this;
    v112._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,IInspectable *> *)std::_Func_impl_no_alloc__lambda_9eb1329a4ba7fb2fd52593212a484aaf__long_IInspectable___Windows::UI::Xaml::Input::IPointerRoutedEventArgs___::_vftable_;
    v112._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,IInspectable *> *)&v112;
    DesiredBoundsMode = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs,DirectUI::UIElementPointerEnteredTraits>>::AttachEventHandler(
                          &this->m_epControlPanelEnteredHandler,
                          (Windows::UI::Xaml::IUIElement *)((unsigned __int64)&v83[-39]
                                                          & ((unsigned __int128)-(__int128)(unsigned __int64)&v83[-62] >> 64)),
                          (std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::Input::IPointerRoutedEventArgs *)> *)&v112);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    v112._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,IInspectable *> *)this;
    v112._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,IInspectable *> *)std::_Func_impl_no_alloc__lambda_5edadcef3daeea300f76bc5572ec1488__long_IInspectable___Windows::UI::Xaml::Input::IPointerRoutedEventArgs___::_vftable_;
    v112._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,IInspectable *> *)&v112;
    v84 = (unsigned __int128)&p_m_tpControlPanelGrid->m_trackerReference.m_value[-62]
        & ((unsigned __int128)-(__int128)(unsigned __int64)p_m_tpControlPanelGrid->m_trackerReference.m_value >> 64);
    v85 = v84 ? (Windows::UI::Xaml::IUIElement *)(v84 + 184) : 0LL;
    DesiredBoundsMode = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs,DirectUI::UIElementPointerExitedTraits>>::AttachEventHandler(
                          &this->m_epControlPanelExitedHandler,
                          v85,
                          (std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::Input::IPointerRoutedEventArgs *)> *)&v112);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    v112._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,IInspectable *> *)this;
    v112._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,IInspectable *> *)std::_Func_impl_no_alloc__lambda_cbf7d23ce404580807d603ca39e492a2__long_IInspectable___Windows::UI::Xaml::Input::IPointerRoutedEventArgs___::_vftable_;
    v112._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,IInspectable *> *)&v112;
    v86 = (unsigned __int128)&p_m_tpControlPanelGrid->m_trackerReference.m_value[-62]
        & ((unsigned __int128)-(__int128)(unsigned __int64)p_m_tpControlPanelGrid->m_trackerReference.m_value >> 64);
    v87 = v86 ? (Windows::UI::Xaml::IUIElement *)(v86 + 184) : 0LL;
    DesiredBoundsMode = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs,DirectUI::UIElementPointerCaptureLostTraits>>::AttachEventHandler(
                          &this->m_epControlPanelCaptureLostHandler,
                          v87,
                          (std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::Input::IPointerRoutedEventArgs *)> *)&v112);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    v112._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,IInspectable *> *)this;
    v112._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,IInspectable *> *)std::_Func_impl_no_alloc__lambda_d3d91112ce5301b6e18a4702c7038cda__long_IInspectable___Windows::UI::Xaml::IRoutedEventArgs___::_vftable_;
    v112._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,IInspectable *> *)&v112;
    v88 = (unsigned __int128)&p_m_tpControlPanelGrid->m_trackerReference.m_value[-62]
        & ((unsigned __int128)-(__int128)(unsigned __int64)p_m_tpControlPanelGrid->m_trackerReference.m_value >> 64);
    v89 = v88 ? (Windows::UI::Xaml::IUIElement *)(v88 + 184) : 0LL;
    DesiredBoundsMode = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::UIElementGotFocusTraits>>::AttachEventHandler(
                          &this->m_epControlPanelGotFocusHandler,
                          v89,
                          (std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *)> *)&v112);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    v112._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,IInspectable *> *)this;
    v112._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,IInspectable *> *)std::_Func_impl_no_alloc__lambda_c78735944a7f11a41a93b528da098a59__long_IInspectable___Windows::UI::Xaml::IRoutedEventArgs___::_vftable_;
    v112._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,IInspectable *> *)&v112;
    v90 = (unsigned __int128)&p_m_tpControlPanelGrid->m_trackerReference.m_value[-62]
        & ((unsigned __int128)-(__int128)(unsigned __int64)p_m_tpControlPanelGrid->m_trackerReference.m_value >> 64);
    v91 = v90 ? (Windows::UI::Xaml::IUIElement *)(v90 + 184) : 0LL;
    DesiredBoundsMode = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::UIElementLostFocusTraits>>::AttachEventHandler(
                          &this->m_epControlPanelLostFocusHandler,
                          v91,
                          (std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *)> *)&v112);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    DesiredBoundsMode = ctl::make<DirectUI::DispatcherTimer>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::DispatcherTimer> >)&spHideControlPanelTimer);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::IDispatcherTimer,DirectUI::DispatcherTimer>(
      &this->ctl::WeakReferenceSourceNoThreadId,
      &this->m_tpHideControlPanelTimer,
      spHideControlPanelTimer.ptr_);
    v92 = (__int64)this->m_tpHideControlPanelTimer.m_trackerReference.m_value;
    if ( !v92 )
      v92 = 192;
    DesiredBoundsMode = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v92 + 56LL))(v92, 30000000);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    v112._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,IInspectable *> *)this;
    v112._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,IInspectable *> *)std::_Func_impl_no_alloc__lambda_2304ce46684ef7bc7c548feaf8c7a9c5__long_IInspectable___IInspectable___::_vftable_;
    v112._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,IInspectable *> *)&v112;
    v93 = (unsigned __int128)&this->m_tpHideControlPanelTimer.m_trackerReference.m_value[-24]
        & ((unsigned __int128)-(__int128)(unsigned __int64)this->m_tpHideControlPanelTimer.m_trackerReference.m_value >> 64);
    v94 = v93 ? (Windows::UI::Xaml::IDispatcherTimer *)(v93 + 192) : 0LL;
    DesiredBoundsMode = ctl::EventPtr<ctl::event_handler<Windows::Foundation::IEventHandler<IInspectable *>,IInspectable,IInspectable,DirectUI::DispatcherTimerTickTraits>>::AttachEventHandler(
                          &this->m_epHideControlPanelTimerTickHandler,
                          v94,
                          &v112);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    spTranformAsII.ptr_ = 0;
    spControlPanelGridAsIFE.ptr_ = 0;
    v95 = DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::IGrid,1,0>::As<Windows::UI::Xaml::IFrameworkElement>(
            (ctl::ComPtr<Windows::UI::Xaml::Controls::IButton> *)&this->m_tpControlPanelGrid,
            (ctl::Internal::ComPtrRef<ctl::ComPtr<Windows::UI::Xaml::IFrameworkElement> >)&spControlPanelGridAsIFE);
    v9 = v95;
    if ( v95 < 0 )
      goto LABEL_228;
    v96 = spControlPanelGridAsIFE.ptr_;
    FindName = spControlPanelGridAsIFE.ptr_->FindName;
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spTranformAsII);
    Windows::Internal::StringReference::StringReference(
      (Windows::Internal::StringReference *)&pPositionSliderPressedEventSource,
      L"TranslateVertical",
      0x11u);
    v95 = FindName(v96, *v98, &spTranformAsII.ptr_);
    v9 = v95;
    if ( v95 < 0 )
      goto LABEL_228;
    if ( spTranformAsII.ptr_ )
    {
      v99 = this->GetTemplateChild;
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spComponentAsDO);
      if ( WindowsCreateStringReference(
             L"ControlPanel_ControlPanelVisibilityStates_Border",
             0x30u,
             &hstringHeader,
             (HSTRING *)&pPositionSliderPressedEventSource) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v95 = v99(
              &this->Windows::UI::Xaml::Controls::IControlProtected,
              (HSTRING__ *)pPositionSliderPressedEventSource,
              &spComponentAsDO.ptr_);
      v9 = v95;
      if ( v95 < 0
        || (ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::IBorder,Windows::UI::Xaml::IDependencyObject>(
              &this->ctl::WeakReferenceSourceNoThreadId,
              &this->m_tpControlPanelVisibilityBorder,
              spComponentAsDO.ptr_),
            (v100 = this->m_tpControlPanelVisibilityBorder.m_trackerReference.m_value) != 0)
        && (v112._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,IInspectable *> *)this,
            v112._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,IInspectable *> *)std::_Func_impl_no_alloc__lambda_21dd8af7e5d06b58c8424e0e3437bc33__long_IInspectable___Windows::UI::Xaml::ISizeChangedEventArgs___::_vftable_,
            v112._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,IInspectable *> *)&v112,
            v95 = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::ISizeChangedEventHandler,IInspectable,Windows::UI::Xaml::ISizeChangedEventArgs,DirectUI::FrameworkElementSizeChangedTraits>>::AttachEventHandler(
                    &this->m_epBorderSizeChangedHandler,
                    (Windows::UI::Xaml::IFrameworkElement *)((unsigned __int64)&v100[-12]
                                                           & ((unsigned __int128)-(__int128)(unsigned __int64)&v100[-56] >> 64)),
                    (std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::ISizeChangedEventArgs *)> *)&v112),
            v9 = v95,
            v95 < 0) )
      {
LABEL_228:
        OnFailure_2990_(v95);
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spControlPanelGridAsIFE);
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spTranformAsII);
        goto $Cleanup_6469;
      }
    }
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spControlPanelGridAsIFE);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spTranformAsII);
  }
  v112._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,IInspectable *> *)this;
  v112._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,IInspectable *> *)std::_Func_impl_no_alloc__lambda_cafafff281050f8426ca61d36d5179ab__long_IInspectable___Windows::UI::Xaml::Input::IPointerRoutedEventArgs___::_vftable_;
  v112._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,IInspectable *> *)&v112;
  DesiredBoundsMode = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs,DirectUI::UIElementPointerExitedTraits>>::AttachEventHandler(
                        &this->m_epRootExitedHandler,
                        (Windows::UI::Xaml::IUIElement *)((unsigned __int64)&this->Windows::UI::Xaml::IUIElement
                                                        & -(__int64)(this != 0)),
                        (std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::Input::IPointerRoutedEventArgs *)> *)&v112);
  v9 = DesiredBoundsMode;
  if ( DesiredBoundsMode < 0 )
    goto LABEL_246;
  v112._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,IInspectable *> *)this;
  v112._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,IInspectable *> *)std::_Func_impl_no_alloc__lambda_a6e7d01725350ea4d2c47d1a863df7ae__long_IInspectable___Windows::UI::Xaml::Input::IPointerRoutedEventArgs___::_vftable_;
  v112._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,IInspectable *> *)&v112;
  DesiredBoundsMode = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs,DirectUI::UIElementPointerPressedTraits>>::AttachEventHandler(
                        &this->m_epRootPressedHandler,
                        (Windows::UI::Xaml::IUIElement *)((unsigned __int64)&this->Windows::UI::Xaml::IUIElement
                                                        & -(__int64)(this != 0)),
                        (std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::Input::IPointerRoutedEventArgs *)> *)&v112);
  v9 = DesiredBoundsMode;
  if ( DesiredBoundsMode < 0 )
    goto LABEL_246;
  v112._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,IInspectable *> *)this;
  v112._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,IInspectable *> *)std::_Func_impl_no_alloc__lambda_f9f5222b625c7a5e883ae612fd770913__long_IInspectable___Windows::UI::Xaml::Input::IPointerRoutedEventArgs___::_vftable_;
  v112._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,IInspectable *> *)&v112;
  DesiredBoundsMode = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs,DirectUI::UIElementPointerReleasedTraits>>::AttachEventHandler(
                        &this->m_epRootReleasedHandler,
                        (Windows::UI::Xaml::IUIElement *)((unsigned __int64)&this->Windows::UI::Xaml::IUIElement
                                                        & -(__int64)(this != 0)),
                        (std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::Input::IPointerRoutedEventArgs *)> *)&v112);
  v9 = DesiredBoundsMode;
  if ( DesiredBoundsMode < 0 )
    goto LABEL_246;
  v112._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,IInspectable *> *)this;
  v112._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,IInspectable *> *)std::_Func_impl_no_alloc__lambda_d840104acbb4c1cbcdcca0f1695b7b89__long_IInspectable___Windows::UI::Xaml::Input::IPointerRoutedEventArgs___::_vftable_;
  v112._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,IInspectable *> *)&v112;
  DesiredBoundsMode = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs,DirectUI::UIElementPointerCaptureLostTraits>>::AttachEventHandler(
                        &this->m_epRootCaptureLostHandler,
                        (Windows::UI::Xaml::IUIElement *)((unsigned __int64)&this->Windows::UI::Xaml::IUIElement
                                                        & -(__int64)(this != 0)),
                        (std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::Input::IPointerRoutedEventArgs *)> *)&v112);
  v9 = DesiredBoundsMode;
  if ( DesiredBoundsMode < 0 )
    goto LABEL_246;
  v112._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,IInspectable *> *)this;
  v112._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,IInspectable *> *)std::_Func_impl_no_alloc__lambda_a816895badf39d8baed325f399823beb__long_IInspectable___Windows::UI::Xaml::Input::IPointerRoutedEventArgs___::_vftable_;
  v112._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,IInspectable *> *)&v112;
  DesiredBoundsMode = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::Input::IPointerEventHandler,IInspectable,Windows::UI::Xaml::Input::IPointerRoutedEventArgs,DirectUI::UIElementPointerMovedTraits>>::AttachEventHandler(
                        &this->m_epRootMovedHandler,
                        (Windows::UI::Xaml::IUIElement *)((unsigned __int64)&this->Windows::UI::Xaml::IUIElement
                                                        & -(__int64)(this != 0)),
                        (std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::Input::IPointerRoutedEventArgs *)> *)&v112);
  v9 = DesiredBoundsMode;
  if ( DesiredBoundsMode < 0 )
    goto LABEL_246;
  v112._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,IInspectable *> *)std::_Func_impl_no_alloc__lambda_b4624b47684fc8b31ac6cf8ec3820e98__long_IInspectable___Windows::UI::Xaml::ISizeChangedEventArgs___::_vftable_;
  v112._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,IInspectable *> *)this;
  v112._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,IInspectable *> *)&v112;
  DesiredBoundsMode = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::ISizeChangedEventHandler,IInspectable,Windows::UI::Xaml::ISizeChangedEventArgs,DirectUI::FrameworkElementSizeChangedTraits>>::AttachEventHandler(
                        &this->m_epSizeChangedHandler,
                        v122,
                        (std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::ISizeChangedEventArgs *)> *)&v112);
  v9 = DesiredBoundsMode;
  if ( DesiredBoundsMode < 0 )
    goto LABEL_246;
  v101 = this->m_tpCommandBar.m_trackerReference.m_value;
  if ( v101 )
  {
    v112._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,IInspectable *> *)this;
    v112._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,IInspectable *> *)std::_Func_impl_no_alloc__lambda_ad3d48317529fc6182db9d8d0c917299__long_IInspectable___Windows::UI::Xaml::IRoutedEventArgs___::_vftable_;
    v112._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,IInspectable *> *)&v112;
    DesiredBoundsMode = ctl::EventPtr<ctl::event_handler<Windows::UI::Xaml::IRoutedEventHandler,IInspectable,Windows::UI::Xaml::IRoutedEventArgs,DirectUI::FrameworkElementLoadedTraits>>::AttachEventHandler(
                          &this->m_epCommandBarLoadedHandler,
                          (Windows::UI::Xaml::IFrameworkElement *)((unsigned __int64)&v101[-78]
                                                                 & ((unsigned __int128)-(__int128)(unsigned __int64)&v101[-122] >> 64)),
                          (std::function<long __cdecl(IInspectable *,Windows::UI::Xaml::IRoutedEventArgs *)> *)&v112);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
  }
  p_m_tpVolumeFlyout = &this->m_tpVolumeFlyout;
  v103 = this->m_tpVolumeFlyout.m_trackerReference.m_value;
  if ( v103 )
  {
    v112._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,IInspectable *> *)this;
    v112._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,IInspectable *> *)std::_Func_impl_no_alloc__lambda_54b6c95f4385ac5f6f4e87297b877a6e__long_IInspectable___IInspectable___::_vftable_;
    v112._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,IInspectable *> *)&v112;
    DesiredBoundsMode = ctl::EventPtr<ctl::event_handler<Windows::Foundation::IEventHandler<IInspectable *>,IInspectable,IInspectable,DirectUI::FlyoutBaseOpenedTraits>>::AttachEventHandler(
                          &this->m_epFlyoutOpenedHandler,
                          (Windows::UI::Xaml::Controls::Primitives::IFlyoutBase *)((unsigned __int64)v103
                                                                                 & ((unsigned __int128)-(__int128)(unsigned __int64)&v103[-23] >> 64)),
                          &v112);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    v112._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,IInspectable *> *)this;
    v112._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,IInspectable *> *)std::_Func_impl_no_alloc__lambda_0f7918c1fd504fda0df4a3b83f8b6caf__long_IInspectable___IInspectable___::_vftable_;
    v112._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,IInspectable *> *)&v112;
    v104 = (unsigned __int128)&p_m_tpVolumeFlyout->m_trackerReference.m_value[-23]
         & ((unsigned __int128)-(__int128)(unsigned __int64)p_m_tpVolumeFlyout->m_trackerReference.m_value >> 64);
    v105 = v104 ? (Windows::UI::Xaml::Controls::Primitives::IFlyoutBase *)(v104 + 184) : 0LL;
    DesiredBoundsMode = ctl::EventPtr<ctl::event_handler<Windows::Foundation::IEventHandler<IInspectable *>,IInspectable,IInspectable,DirectUI::FlyoutBaseClosedTraits>>::AttachEventHandler(
                          &this->m_epFlyoutClosedHandler,
                          v105,
                          &v112);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
    DesiredBoundsMode = DirectUI::FlyoutBaseGenerated::put_ShouldConstrainToRootBounds(
                          (DirectUI::FlyoutBaseGenerated *)(-(__int64)(p_m_tpVolumeFlyout->m_trackerReference.m_value != 0)
                                                          & (__int64)&p_m_tpVolumeFlyout->m_trackerReference.m_value[-23]),
                          1u);
    v9 = DesiredBoundsMode;
    if ( DesiredBoundsMode < 0 )
      goto LABEL_246;
  }
  DesiredBoundsMode = ctl::make<DirectUI::DispatcherTimer>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::DispatcherTimer> >)&spPointerMoveEndTimer);
  v9 = DesiredBoundsMode;
  if ( DesiredBoundsMode < 0 )
    goto LABEL_246;
  ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::IDispatcherTimer,DirectUI::DispatcherTimer>(
    &this->ctl::WeakReferenceSourceNoThreadId,
    &this->m_tpPointerMoveEndTimer,
    spPointerMoveEndTimer.ptr_);
  v106 = (__int64)this->m_tpPointerMoveEndTimer.m_trackerReference.m_value;
  if ( !v106 )
    v106 = 192;
  DesiredBoundsMode = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v106 + 56LL))(v106, 0);
  v9 = DesiredBoundsMode;
  if ( DesiredBoundsMode < 0 )
    goto LABEL_246;
  v112._Mystorage._Ptrs[1] = (std::_Func_base<long,IInspectable *,IInspectable *> *)this;
  v112._Mystorage._Ptrs[0] = (std::_Func_base<long,IInspectable *,IInspectable *> *)std::_Func_impl_no_alloc__lambda_9a46584c2c996001200c7f6dc624c33b__long_IInspectable___IInspectable___::_vftable_;
  v112._Mystorage._Ptrs[7] = (std::_Func_base<long,IInspectable *,IInspectable *> *)&v112;
  v107 = (unsigned __int128)&this->m_tpPointerMoveEndTimer.m_trackerReference.m_value[-24]
       & ((unsigned __int128)-(__int128)(unsigned __int64)this->m_tpPointerMoveEndTimer.m_trackerReference.m_value >> 64);
  v108 = v107 ? (Windows::UI::Xaml::IDispatcherTimer *)(v107 + 192) : 0LL;
  DesiredBoundsMode = ctl::EventPtr<ctl::event_handler<Windows::Foundation::IEventHandler<IInspectable *>,IInspectable,IInspectable,DirectUI::DispatcherTimerTickTraits>>::AttachEventHandler(
                        &this->m_epPointerMoveEndTimerTickHandler,
                        v108,
                        &v112);
  v9 = DesiredBoundsMode;
  if ( DesiredBoundsMode < 0 )
    goto LABEL_246;
  DesiredBoundsMode = DirectUI::MediaTransportControls::HookupVolumeAndProgressPartsAndHandlers(this);
  v9 = DesiredBoundsMode;
  if ( DesiredBoundsMode < 0 )
    goto LABEL_246;
  DesiredBoundsMode = DirectUI::MediaTransportControls::HookupPhoneSpecificPartsAndHandlers(this);
  v9 = DesiredBoundsMode;
  if ( DesiredBoundsMode < 0 )
    goto LABEL_246;
  DesiredBoundsMode = DirectUI::MediaTransportControls::GetComponentSizeConstants(this);
  v9 = DesiredBoundsMode;
  if ( DesiredBoundsMode < 0 )
    goto LABEL_246;
  DesiredBoundsMode = DirectUI::MediaTransportControls::MoreControls(this);
  v9 = DesiredBoundsMode;
  if ( DesiredBoundsMode < 0 )
    goto LABEL_246;
  DesiredBoundsMode = DirectUI::MediaTransportControls::SetTabIndex(this);
  v9 = DesiredBoundsMode;
  if ( DesiredBoundsMode < 0 )
    goto LABEL_246;
$Cleanup_6469:
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spPositionSliderKeyUpHandler);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spPositionSliderKeyDownHandler);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spPositionSliderReleasedHandler);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spPositionSliderPressedHandler);
  ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spPointerMoveEndTimer);
  ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spHideControlPanelTimer);
  ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spPositionUpdateTimer);
  Windows::Internal::String::~String(&strSkipString);
  Windows::Internal::String::~String(&strSeparator);
  Windows::Internal::String::~String(&strAutomationName);
  Windows::Internal::String::~String(&strDefaultError);
  ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spComponentAsDO);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1806f4f34  push    rbp
0x1806f4f36  push    rbx
0x1806f4f37  push    rsi
0x1806f4f38  push    rdi
0x1806f4f39  push    r12
0x1806f4f3b  push    r13
0x1806f4f3d  push    r14
0x1806f4f3f  push    r15
0x1806f4f41  lea     rbp, [rsp-58h]
0x1806f4f46  sub     rsp, 158h
0x1806f4f4d  mov     rax, cs:__security_cookie
0x1806f4f54  xor     rax, rsp
0x1806f4f57  mov     [rbp+90h+var_50], rax
0x1806f4f5b  xor     r15d, r15d
0x1806f4f5e  lea     r13, [this+1C8h]
0x1806f4f65  mov     rax, [r13+0]
0x1806f4f69  mov     rsi, this
0x1806f4f6c  mov     ebx, r15d
0x1806f4f6f  mov     [rsp+190h+spComponentAsDO.ptr_], r15
0x1806f4f74  lea     this, [rsp+190h+spComponentAsDO]; this
0x1806f4f79  mov     [rbp+90h+strDefaultError._hstring], r15
0x1806f4f7d  mov     r14d, r15d
0x1806f4f80  mov     [rsp+190h+strAutomationName._hstring], r15
0x1806f4f85  mov     rdi, [rax+40h]
0x1806f4f89  mov     [rbp+90h+strSeparator._hstring], r15
0x1806f4f8d  mov     [rsp+190h+strSkipString._hstring], rbx
0x1806f4f92  mov     [rbp+90h+spPositionUpdateTimer.ptr_], r15
0x1806f4f96  mov     [rbp+90h+spHideControlPanelTimer.ptr_], r15
0x1806f4f9a  mov     [rbp+90h+spPointerMoveEndTimer.ptr_], r15
0x1806f4f9e  mov     [rbp+90h+spPositionSliderPressedHandler.ptr_], r15
0x1806f4fa2  mov     [rbp+90h+pPositionSliderPressedEventSource], r15
0x1806f4fa6  mov     [rbp+90h+spPositionSliderReleasedHandler.ptr_], r15
0x1806f4faa  mov     [rbp+90h+pPositionSliderReleasedEventSource], r15
0x1806f4fae  mov     [rbp+90h+spPositionSliderKeyDownHandler.ptr_], r15
0x1806f4fb2  mov     [rbp+90h+spPositionSliderKeyUpHandler.ptr_], r15
0x1806f4fb6  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1806f4fbb  lea     rdx, aControlpanelgr; "ControlPanelGrid"
0x1806f4fc2  lea     this, [rbp+90h+spControlPanelGridAsIFE]; this
0x1806f4fc6  call    ??$?0$0BB@@StringReference@Internal@Windows@@QEAA@AEAY0BB@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[17])
0x1806f4fcb  lea     r8, [rsp+190h+spComponentAsDO]
0x1806f4fd0  mov     this, r13
0x1806f4fd3  mov     rdx, [rax]
0x1806f4fd6  mov     rax, rdi
0x1806f4fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806f4fde  mov     edi, eax
0x1806f4fe0  test    eax, eax
0x1806f4fe2  js      loc_1806F69D5
0x1806f4fe8  mov     r8, [rsp+190h+spComponentAsDO.ptr_]; value
0x1806f4fed  lea     rdi, [rsi+368h]
0x1806f4ff4  lea     r12, [rsi+8]
0x1806f4ff8  mov     rdx, rdi; ptr
0x1806f4ffb  mov     this, r12; this
0x1806f4ffe  call    ??$SetPtrValueWithQIOrNull@UIGrid@Controls@Xaml@UI@Windows@@UIDependencyObject@345@@WeakReferenceSourceNoThreadId@ctl@@IEAAXAEAV?$TrackerPtr@UIGrid@Controls@Xaml@UI@Windows@@$00$0A@@DirectUI@@PEAUIDependencyObject@Xaml@UI@Windows@@@Z; ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::Controls::IGrid,Windows::UI::Xaml::IDependencyObject>(DirectUI::TrackerPtr<Windows::UI::Xaml::Controls::IGrid,1,0> &,Windows::UI::Xaml::IDependencyObject *)
0x1806f5003  cmp     [rdi], r15
0x1806f5006  jz      short loc_1806F5060
0x1806f5008  call    ?IsOnXbox@XboxUtility@@YA_NXZ; XboxUtility::IsOnXbox(void)
0x1806f500d  test    al, al
0x1806f500f  jz      short loc_1806F5060
0x1806f5011  mov     cl, 1; mode
0x1806f5013  call    ?GetDesignerMode@DesignerInterop@@SA_NW4DesignerMode@@@Z; DesignerInterop::GetDesignerMode(DesignerMode)
0x1806f5018  test    al, al
0x1806f501a  jnz     short loc_1806F5060
0x1806f501c  lea     rdx, [rsp+190h+spTranformAsII]; boundsMode
0x1806f5021  mov     dword ptr [rsp+190h+spTranformAsII.ptr_], r15d
0x1806f5026  call    ?GetDesiredBoundsMode@MediaTransportControls@DirectUI@@AEBAJPEAW4ApplicationViewBoundsMode@ViewManagement@UI@Windows@@@Z; DirectUI::MediaTransportControls::GetDesiredBoundsMode(Windows::UI::ViewManagement::ApplicationViewBoundsMode *)
0x1806f502b  mov     edi, eax
0x1806f502d  test    eax, eax
0x1806f502f  js      short loc_1806F5054
0x1806f5031  cmp     dword ptr [rsp+190h+spTranformAsII.ptr_], 1
0x1806f5036  jnz     short loc_1806F5060
0x1806f5038  mov     dl, 1; applySafeMargin
0x1806f503a  mov     this, rsi; this
0x1806f503d  call    ?UpdateSafeMargins@MediaTransportControls@DirectUI@@AEAAJ_N@Z; DirectUI::MediaTransportControls::UpdateSafeMargins(bool)
0x1806f5042  mov     edi, eax
0x1806f5044  test    eax, eax
0x1806f5046  jns     short loc_1806F5060
0x1806f5048  mov     ecx, eax; failedFrameHR
0x1806f504a  call    OnFailure_2990_
0x1806f504f  jmp     $Cleanup_6469
0x1806f5054  mov     ecx, eax; failedFrameHR
0x1806f5056  call    OnFailure_2990_
0x1806f505b  jmp     $Cleanup_6469
0x1806f5060  mov     rax, [r13+0]
0x1806f5064  lea     this, [rsp+190h+spComponentAsDO]; this
0x1806f5069  mov     rdi, [rax+40h]
0x1806f506d  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1806f5072  lea     rdx, aTimeelapsedele; "TimeElapsedElement"
0x1806f5079  lea     this, [rbp+90h+spControlPanelGridAsIFE]; this
0x1806f507d  call    ??$?0$0BD@@StringReference@Internal@Windows@@QEAA@AEAY0BD@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[19])
0x1806f5082  lea     r8, [rsp+190h+spComponentAsDO]
0x1806f5087  mov     this, r13
0x1806f508a  mov     rdx, [rax]
0x1806f508d  mov     rax, rdi
0x1806f5090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806f5095  mov     edi, eax
0x1806f5097  test    eax, eax
0x1806f5099  js      loc_1806F69CC
0x1806f509f  mov     r8, [rsp+190h+spComponentAsDO.ptr_]; value
0x1806f50a4  lea     r15, [rsi+5C0h]
0x1806f50ab  mov     rdx, r15; ptr
0x1806f50ae  mov     this, r12; this
0x1806f50b1  call    ??$SetPtrValueWithQIOrNull@UIFrameworkElement@Xaml@UI@Windows@@UIDependencyObject@234@@WeakReferenceSourceNoThreadId@ctl@@IEAAXAEAV?$TrackerPtr@UIFrameworkElement@Xaml@UI@Windows@@$00$0A@@DirectUI@@PEAUIDependencyObject@Xaml@UI@Windows@@@Z; ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::IFrameworkElement,Windows::UI::Xaml::IDependencyObject>(DirectUI::TrackerPtr<Windows::UI::Xaml::IFrameworkElement,1,0> &,Windows::UI::Xaml::IDependencyObject *)
0x1806f50b6  cmp     [r15], rbx
0x1806f50b9  jz      loc_1806F522B
0x1806f50bf  call    ?GetCurrent@DXamlCore@DirectUI@@SAPEAV12@XZ; DirectUI::DXamlCore::GetCurrent(void)
0x1806f50c4  xor     ecx, ecx; string
0x1806f50c6  mov     rdi, rax
0x1806f50c9  call    cs:__imp_WindowsDeleteString
0x1806f50cf  lea     r8, [rsp+190h+strAutomationName]; resourceString
0x1806f50d4  mov     edx, 1486h; resourceStringID
0x1806f50d9  mov     this, rdi; this
0x1806f50dc  call    ?GetLocalizedResourceString@DXamlCore@DirectUI@@QEAAJIPEAPEAUHSTRING__@@@Z; DirectUI::DXamlCore::GetLocalizedResourceString(uint,HSTRING__ * *)
0x1806f50e1  mov     edi, eax
0x1806f50e3  test    eax, eax
0x1806f50e5  js      loc_1806F521F
0x1806f50eb  call    ?IsWindowsBlue@MediaTransportControls@DirectUI@@AEAA_NXZ; DirectUI::MediaTransportControls::IsWindowsBlue(void)
0x1806f50f0  test    al, al
0x1806f50f2  jz      loc_1806F5197
0x1806f50f8  call    ?GetCurrent@DXamlCore@DirectUI@@SAPEAV12@XZ; DirectUI::DXamlCore::GetCurrent(void)
0x1806f50fd  xor     ecx, ecx; string
0x1806f50ff  mov     rbx, rax
0x1806f5102  call    cs:__imp_WindowsDeleteString
0x1806f5108  lea     r8, [rbp+90h+strSeparator]; resourceString
0x1806f510c  mov     edx, 148Ah; resourceStringID
0x1806f5111  mov     this, rbx; this
0x1806f5114  call    ?GetLocalizedResourceString@DXamlCore@DirectUI@@QEAAJIPEAPEAUHSTRING__@@@Z; DirectUI::DXamlCore::GetLocalizedResourceString(uint,HSTRING__ * *)
0x1806f5119  mov     edi, eax
0x1806f511b  test    eax, eax
0x1806f511d  js      loc_1806F5207
0x1806f5123  call    ?GetCurrent@DXamlCore@DirectUI@@SAPEAV12@XZ; DirectUI::DXamlCore::GetCurrent(void)
0x1806f5128  xor     ecx, ecx; string
0x1806f512a  mov     rbx, rax
0x1806f512d  call    cs:__imp_WindowsDeleteString
0x1806f5133  lea     r8, [rsp+190h+strSkipString]; resourceString
0x1806f5138  mov     edx, 1487h; resourceStringID
0x1806f513d  mov     this, rbx; this
0x1806f5140  call    ?GetLocalizedResourceString@DXamlCore@DirectUI@@QEAAJIPEAPEAUHSTRING__@@@Z; DirectUI::DXamlCore::GetLocalizedResourceString(uint,HSTRING__ * *)
0x1806f5145  mov     edi, eax
0x1806f5147  test    eax, eax
0x1806f5149  js      loc_1806F51FB
0x1806f514f  lea     r8, [rsp+190h+strAutomationName]; newString
0x1806f5154  lea     rdx, [rbp+90h+strSeparator]; string
0x1806f5158  lea     this, [rsp+190h+strAutomationName]; this
0x1806f515d  call    ?Concat@String@Internal@Windows@@QEBAJAEBV123@PEAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x1806f5162  mov     edi, eax
0x1806f5164  test    eax, eax
0x1806f5166  js      loc_1806F51EF
0x1806f516c  lea     r8, [rsp+190h+strAutomationName]; newString
0x1806f5171  lea     rdx, [rsp+190h+strSkipString]; string
0x1806f5176  lea     this, [rsp+190h+strAutomationName]; this
0x1806f517b  call    ?Concat@String@Internal@Windows@@QEBAJAEBV123@PEAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x1806f5180  mov     edi, eax
0x1806f5182  test    eax, eax
0x1806f5184  jns     short loc_1806F5192
0x1806f5186  mov     ecx, eax; failedFrameHR
0x1806f5188  call    OnFailure_2990_
0x1806f518d  jmp     $Cleanup_6469
0x1806f5192  mov     rbx, [rsp+190h+strSkipString._hstring]
0x1806f5197  mov     this, [r15]
0x1806f519a  mov     edx, 22h ; '"'; nPropertyIndex
0x1806f519f  mov     r14, [rsp+190h+strAutomationName._hstring]
0x1806f51a4  mov     r8, r14; value
0x1806f51a7  lea     rax, [this-160h]
0x1806f51ae  neg     this
0x1806f51b1  sbb     this, this
0x1806f51b4  and     this, rax; this
0x1806f51b7  call    ?SetValueByKnownIndex@DependencyObject@DirectUI@@QEAAJW4KnownPropertyIndex@@PEAUHSTRING__@@@Z; DirectUI::DependencyObject::SetValueByKnownIndex(KnownPropertyIndex,HSTRING__ *)
0x1806f51bc  mov     edi, eax
0x1806f51be  test    eax, eax
0x1806f51c0  js      short loc_1806F5213
0x1806f51c2  mov     rax, [r15]
0x1806f51c5  mov     r8, r14; hstrTooltipText
0x1806f51c8  lea     this, [rax-160h]; this
0x1806f51cf  neg     rax
0x1806f51d2  sbb     rdx, rdx
0x1806f51d5  and     rdx, this; pTooltipTarget
0x1806f51d8  call    ?AddTooltip@MediaTransportControls@DirectUI@@AEAAJPEAUIDependencyObject@Xaml@UI@Windows@@PEAUHSTRING__@@@Z; DirectUI::MediaTransportControls::AddTooltip(Windows::UI::Xaml::IDependencyObject *,HSTRING__ *)
0x1806f51dd  mov     edi, eax
0x1806f51df  test    eax, eax
0x1806f51e1  jns     short loc_1806F522B
0x1806f51e3  mov     ecx, eax; failedFrameHR
0x1806f51e5  call    OnFailure_2990_
0x1806f51ea  jmp     $Cleanup_6469
0x1806f51ef  mov     ecx, eax; failedFrameHR
0x1806f51f1  call    OnFailure_2990_
0x1806f51f6  jmp     $Cleanup_6469
0x1806f51fb  mov     ecx, eax; failedFrameHR
0x1806f51fd  call    OnFailure_2990_
0x1806f5202  jmp     $Cleanup_6469
0x1806f5207  mov     ecx, eax; failedFrameHR
0x1806f5209  call    OnFailure_2990_
0x1806f520e  jmp     $Cleanup_6469
0x1806f5213  mov     ecx, eax; failedFrameHR
0x1806f5215  call    OnFailure_2990_
0x1806f521a  jmp     $Cleanup_6469
0x1806f521f  mov     ecx, eax; failedFrameHR
0x1806f5221  call    OnFailure_2990_
0x1806f5226  jmp     $Cleanup_6469
0x1806f522b  mov     rax, [r13+0]
0x1806f522f  lea     this, [rsp+190h+spComponentAsDO]; this
0x1806f5234  mov     rdi, [rax+40h]
0x1806f5238  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1806f523d  lea     rdx, aTimeremaininge; "TimeRemainingElement"
0x1806f5244  lea     this, [rbp+90h+spControlPanelGridAsIFE]; this
0x1806f5248  call    ??$?0$0BF@@StringReference@Internal@Windows@@QEAA@AEAY0BF@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[21])
0x1806f524d  lea     r8, [rsp+190h+spComponentAsDO]
0x1806f5252  mov     this, r13
0x1806f5255  mov     rdx, [rax]
0x1806f5258  mov     rax, rdi
0x1806f525b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806f5260  mov     edi, eax
0x1806f5262  test    eax, eax
0x1806f5264  js      loc_1806F69C3
0x1806f526a  mov     r8, [rsp+190h+spComponentAsDO.ptr_]; value
0x1806f526f  lea     r15, [rsi+5D8h]
0x1806f5276  mov     rdx, r15; ptr
0x1806f5279  mov     this, r12; this
0x1806f527c  call    ??$SetPtrValueWithQIOrNull@UIFrameworkElement@Xaml@UI@Windows@@UIDependencyObject@234@@WeakReferenceSourceNoThreadId@ctl@@IEAAXAEAV?$TrackerPtr@UIFrameworkElement@Xaml@UI@Windows@@$00$0A@@DirectUI@@PEAUIDependencyObject@Xaml@UI@Windows@@@Z; ctl::WeakReferenceSourceNoThreadId::SetPtrValueWithQIOrNull<Windows::UI::Xaml::IFrameworkElement,Windows::UI::Xaml::IDependencyObject>(DirectUI::TrackerPtr<Windows::UI::Xaml::IFrameworkElement,1,0> &,Windows::UI::Xaml::IDependencyObject *)
0x1806f5281  cmp     qword ptr [r15], 0
0x1806f5285  jz      loc_1806F53C7
0x1806f528b  call    ?GetCurrent@DXamlCore@DirectUI@@SAPEAV12@XZ; DirectUI::DXamlCore::GetCurrent(void)
0x1806f5290  mov     this, r14; string
0x1806f5293  mov     rdi, rax
0x1806f5296  call    cs:__imp_WindowsDeleteString
0x1806f529c  lea     r8, [rsp+190h+strAutomationName]; resourceString
0x1806f52a1  mov     [rsp+190h+strAutomationName._hstring], 0
0x1806f52aa  mov     edx, 1488h; resourceStringID
0x1806f52af  mov     this, rdi; this
0x1806f52b2  call    ?GetLocalizedResourceString@DXamlCore@DirectUI@@QEAAJIPEAPEAUHSTRING__@@@Z; DirectUI::DXamlCore::GetLocalizedResourceString(uint,HSTRING__ * *)
0x1806f52b7  mov     edi, eax
0x1806f52b9  test    eax, eax
0x1806f52bb  js      loc_1806F53BB
0x1806f52c1  call    ?IsWindowsBlue@MediaTransportControls@DirectUI@@AEAA_NXZ; DirectUI::MediaTransportControls::IsWindowsBlue(void)
0x1806f52c6  test    al, al
0x1806f52c8  jz      loc_1806F5357
0x1806f52ce  call    ?GetCurrent@DXamlCore@DirectUI@@SAPEAV12@XZ; DirectUI::DXamlCore::GetCurrent(void)
0x1806f52d3  mov     this, rbx; string
0x1806f52d6  mov     rdi, rax
0x1806f52d9  call    cs:__imp_WindowsDeleteString
0x1806f52df  lea     r8, [rsp+190h+strSkipString]; resourceString
0x1806f52e4  mov     [rsp+190h+strSkipString._hstring], 0
0x1806f52ed  mov     edx, 1489h; resourceStringID
0x1806f52f2  mov     this, rdi; this
0x1806f52f5  call    ?GetLocalizedResourceString@DXamlCore@DirectUI@@QEAAJIPEAPEAUHSTRING__@@@Z; DirectUI::DXamlCore::GetLocalizedResourceString(uint,HSTRING__ * *)
0x1806f52fa  mov     edi, eax
0x1806f52fc  test    eax, eax
0x1806f52fe  js      short loc_1806F534B
0x1806f5300  lea     r8, [rsp+190h+strAutomationName]; newString
0x1806f5305  lea     rdx, [rbp+90h+strSeparator]; string
0x1806f5309  lea     this, [rsp+190h+strAutomationName]; this
0x1806f530e  call    ?Concat@String@Internal@Windows@@QEBAJAEBV123@PEAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x1806f5313  mov     edi, eax
0x1806f5315  test    eax, eax
0x1806f5317  js      short loc_1806F533F
0x1806f5319  lea     r8, [rsp+190h+strAutomationName]; newString
0x1806f531e  lea     rdx, [rsp+190h+strSkipString]; string
0x1806f5323  lea     this, [rsp+190h+strAutomationName]; this
0x1806f5328  call    ?Concat@String@Internal@Windows@@QEBAJAEBV123@PEAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x1806f532d  mov     edi, eax
0x1806f532f  test    eax, eax
0x1806f5331  jns     short loc_1806F5357
0x1806f5333  mov     ecx, eax; failedFrameHR
0x1806f5335  call    OnFailure_2990_
0x1806f533a  jmp     $Cleanup_6469
0x1806f533f  mov     ecx, eax; failedFrameHR
0x1806f5341  call    OnFailure_2990_
0x1806f5346  jmp     $Cleanup_6469
0x1806f534b  mov     ecx, eax; failedFrameHR
0x1806f534d  call    OnFailure_2990_
0x1806f5352  jmp     $Cleanup_6469
0x1806f5357  mov     this, [r15]
0x1806f535a  mov     edx, 22h ; '"'; nPropertyIndex
0x1806f535f  mov     r14, [rsp+190h+strAutomationName._hstring]
0x1806f5364  mov     r8, r14; value
0x1806f5367  lea     rax, [this-160h]
0x1806f536e  neg     this
0x1806f5371  sbb     this, this
0x1806f5374  and     this, rax; this
0x1806f5377  call    ?SetValueByKnownIndex@DependencyObject@DirectUI@@QEAAJW4KnownPropertyIndex@@PEAUHSTRING__@@@Z; DirectUI::DependencyObject::SetValueByKnownIndex(KnownPropertyIndex,HSTRING__ *)
0x1806f537c  mov     edi, eax
0x1806f537e  test    eax, eax
0x1806f5380  js      short loc_1806F53AF
0x1806f5382  mov     rax, [r15]
0x1806f5385  mov     r8, r14; hstrTooltipText
0x1806f5388  lea     this, [rax-160h]; this
0x1806f538f  neg     rax
0x1806f5392  sbb     rdx, rdx
0x1806f5395  and     rdx, this; pTooltipTarget
0x1806f5398  call    ?AddTooltip@MediaTransportControls@DirectUI@@AEAAJPEAUIDependencyObject@Xaml@UI@Windows@@PEAUHSTRING__@@@Z; DirectUI::MediaTransportControls::AddTooltip(Windows::UI::Xaml::IDependencyObject *,HSTRING__ *)
0x1806f539d  mov     edi, eax
0x1806f539f  test    eax, eax
0x1806f53a1  jns     short loc_1806F53C7
0x1806f53a3  mov     ecx, eax; failedFrameHR
0x1806f53a5  call    OnFailure_2990_
0x1806f53aa  jmp     $Cleanup_6469
0x1806f53af  mov     ecx, eax; failedFrameHR
0x1806f53b1  call    OnFailure_2990_
0x1806f53b6  jmp     $Cleanup_6469
0x1806f53bb  mov     ecx, eax; failedFrameHR
0x1806f53bd  call    OnFailure_2990_
  ... truncated ...
```
