# DirectUI::CCueStyler::CreateRun(Windows::Media::Core::ITimedTextLine *,Windows::Media::Core::ITimedTextStyle *,int,int,bool,Windows::UI::Xaml::Documents::IRun * *)

- ea: `0x1806e9a88`
- end: `0x1806ea4d5`
- name: `?CreateRun@CCueStyler@DirectUI@@AEAAJPEAUITimedTextLine@Core@Media@Windows@@PEAUITimedTextStyle@456@HH_NPEAPEAUIRun@Documents@Xaml@UI@6@@Z`
- size: `2637`
- prototype: `HRESULT __fastcall(DirectUI::CCueStyler *this, Windows::Media::Core::ITimedTextLine *pLine, Windows::Media::Core::ITimedTextStyle *pStyle, int start, int length, bool isOutline, Windows::UI::Xaml::Documents::IRun **ppRun)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1804d2294`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x18000616c`
- `0x180015ad4`
- `0x180021970`
- `0x1800d497c`
- `0x1801e5458`
- `0x1801f1530`
- `0x180317204`
- `0x180453c30`
- `0x180572ce0`
- `0x180613b44`
- `0x1806877a8`
- `0x180687890`
- `0x180688828`
- `0x1806b63f0`
- `0x1806e9a88`
- `0x1807046a8`
- `0x18076e110`
- `0x1808fc24c`
- `0x180bedf90`
- `0x180bedfe4`
- `0x180bef4e8`
- `0x180bef654`
- `0x180bef768`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1806e9d48`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1806e9d48`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1806ea255`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1806ea255`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806e9bb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806e9c24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806e9cb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806e9d0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806e9bb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806e9c24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806e9cb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806e9d0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1806e9d38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1806e9d98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1806e9d38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1806e9d98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1806e9d1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1806e9d1f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1806e9df8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1806e9df8`

## pseudocode

```c
__int64 __fastcall DirectUI::CCueStyler::CreateRun(
        DirectUI::CCueStyler *this,
        Windows::Media::Core::ITimedTextLine *pLine,
        Windows::Media::Core::ITimedTextStyle *pStyle,
        unsigned int start,
        unsigned int length,
        bool isOutline,
        Windows::UI::Xaml::Documents::IRun **ppRun)
{
  HRESULT v11; // eax
  unsigned int v12; // ebx
  Windows::Media::ClosedCaptioning::IClosedCaptionPropertiesStatics *ptr; // rcx
  Windows::Media::Core::ITimedTextLine_vtbl *v14; // rax
  HRESULT (__fastcall *get_Text)(Windows::Media::Core::ITimedTextLine *, HSTRING__ **); // rbx
  HRESULT v16; // eax
  Windows::Internal::String *v17; // rcx
  Windows::Internal::String *p_hSubText; // rcx
  HRESULT v19; // eax
  HRESULT (__fastcall *get_FontFamily)(Windows::Media::Core::ITimedTextStyle *, HSTRING__ **); // rbx
  HRESULT ActivationFactory; // eax
  HSTRING *v22; // rax
  HSTRING *v23; // rbx
  Windows::Media::ClosedCaptioning::ClosedCaptionStyle v24; // edx
  PCWSTR StringRawBuffer; // rax
  HRESULT v26; // eax
  const wchar_t *v27; // rax
  Windows::Internal::StringReference *v28; // rax
  _QWORD *v29; // rax
  Windows::UI::Xaml::Media::IFontFamilyFactory *v30; // rdi
  HRESULT (__fastcall *CreateInstanceWithName)(Windows::UI::Xaml::Media::IFontFamilyFactory *, HSTRING__ *, IInspectable *, IInspectable **, Windows::UI::Xaml::Media::IFontFamily **); // rbx
  ctl::ComPtr<DirectUI::FontWeightsFactory> *p_m_spFontWeightsFactory; // rdi
  HRESULT v33; // eax
  HRESULT v34; // eax
  unsigned int v35; // eax
  Windows::Media::Core::TimedTextFlowDirection v36; // ecx
  HRESULT v37; // eax
  Windows::Media::Core::ITimedTextStyle_vtbl *v38; // rax
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rbx
  HRESULT v40; // eax
  HRESULT v41; // ebx
  HRESULT v42; // eax
  Windows::UI::Xaml::Controls::Primitives::EdgeTransitionLocation v43; // ebx
  HRESULT v44; // eax
  HRESULT v45; // edi
  Windows::UI::Color color; // [rsp+30h] [rbp-C1h] BYREF
  unsigned __int8 fUnderLine; // [rsp+34h] [rbp-BDh] BYREF
  unsigned __int8 fStrikethrough[3]; // [rsp+35h] [rbp-BCh] BYREF
  ctl::ComPtr<DirectUI::Run> spRun; // [rsp+38h] [rbp-B9h] BYREF
  Windows::Internal::String fontFamilyName; // [rsp+40h] [rbp-B1h] BYREF
  Windows::UI::Text::FontWeight uiFontWeight; // [rsp+48h] [rbp-A9h] BYREF
  ctl::ComPtr<Windows::Media::Core::ITimedTextStyle2> spStyle2; // [rsp+50h] [rbp-A1h] BYREF
  ctl::ComPtr<DirectUI::SolidColorBrush> spSolidColorBrush; // [rsp+58h] [rbp-99h] BYREF
  Windows::Internal::String hSubText; // [rsp+60h] [rbp-91h] BYREF
  Windows::Media::Core::TimedTextWeight fontWeight; // [rsp+68h] [rbp-89h] BYREF
  ctl::ComPtr<Windows::UI::Xaml::Media::IFontFamily> spFontFamily; // [rsp+70h] [rbp-81h] BYREF
  Windows::Media::ClosedCaptioning::ClosedCaptionStyle userFontStyle; // [rsp+78h] [rbp-79h] BYREF
  Windows::Internal::String v59; // [rsp+80h] [rbp-71h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **ppStowedExceptions; // [rsp+88h] [rbp-69h] BYREF
  Windows::Media::ClosedCaptioning::ClosedCaptionColor userForegroundColor; // [rsp+90h] [rbp-61h] BYREF
  Windows::Media::ClosedCaptioning::ClosedCaptionOpacity userForegroundOpacity; // [rsp+94h] [rbp-5Dh] BYREF
  Windows::Media::Core::TimedTextFlowDirection flow; // [rsp+98h] [rbp-59h] BYREF
  unsigned int cStowedExceptions; // [rsp+9Ch] [rbp-55h] BYREF
  Windows::Media::Core::TimedTextFontStyle timedTextFontStyle; // [rsp+A0h] [rbp-51h] BYREF
  CValue value; // [rsp+A8h] [rbp-49h] BYREF
  Windows::Internal::StringReference result; // [rsp+C8h] [rbp-29h] BYREF

  spRun.ptr_ = 0;
  if ( ppRun )
  {
    *ppRun = 0;
    v11 = ctl::make<DirectUI::Run>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::Run> >)&spRun);
    v12 = v11;
    if ( v11 < 0 )
      goto LABEL_114;
    ptr = this->m_pSettingsStatics.ptr_;
    userForegroundOpacity = ClosedCaptionOpacity_Default;
    userForegroundColor = ClosedCaptionColor_Default;
    userFontStyle = ClosedCaptionStyle_Default;
    if ( ptr )
    {
      if ( (v12 = ptr->get_FontColor(ptr, &userForegroundColor), (int)(v12 + 0x80000000) >= 0) && v12 != -2147024891
        || (v12 = this->m_pSettingsStatics.ptr_->get_FontOpacity(this->m_pSettingsStatics.ptr_, &userForegroundOpacity),
            (int)(v12 + 0x80000000) >= 0)
        && v12 != -2147024891
        || (v12 = this->m_pSettingsStatics.ptr_->get_FontStyle(this->m_pSettingsStatics.ptr_, &userFontStyle),
            (int)(v12 + 0x80000000) >= 0)
        && v12 != -2147024891 )
      {
        OnFailure_2990_(v12);
LABEL_115:
        ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spRun);
        return v12;
      }
    }
    v14 = pLine->__vftable;
    hSubText._hstring = 0;
    get_Text = v14->get_Text;
    if ( length == -1 )
    {
      WindowsDeleteString(0);
      hSubText._hstring = 0;
      v16 = get_Text(pLine, &hSubText._hstring);
      v12 = v16;
      if ( v16 < 0
        || (v16 = spRun.ptr_->put_Text(&spRun.ptr_->Windows::UI::Xaml::Documents::IRun, hSubText._hstring),
            v12 = v16,
            v16 < 0) )
      {
        OnFailure_2990_(v16);
        p_hSubText = &hSubText;
LABEL_17:
        Windows::Internal::String::~String(p_hSubText);
        goto LABEL_115;
      }
      v17 = &hSubText;
    }
    else
    {
      v59._hstring = 0;
      WindowsDeleteString(0);
      v59._hstring = 0;
      v19 = get_Text(pLine, &v59._hstring);
      v12 = v19;
      if ( v19 < 0
        || (v19 = Windows::Internal::String::Substring(&v59, start, length, &hSubText), v12 = v19, v19 < 0)
        || (v19 = spRun.ptr_->put_Text(&spRun.ptr_->Windows::UI::Xaml::Documents::IRun, hSubText._hstring),
            v12 = v19,
            v19 < 0) )
      {
        OnFailure_2990_(v19);
        Windows::Internal::String::~String(&hSubText);
        p_hSubText = &v59;
        goto LABEL_17;
      }
      Windows::Internal::String::~String(&hSubText);
      v17 = &v59;
    }
    Windows::Internal::String::~String(v17);
    fontFamilyName._hstring = 0;
    spFontFamily.ptr_ = 0;
    if ( pStyle )
    {
      get_FontFamily = pStyle->get_FontFamily;
      WindowsDeleteString(0);
      fontFamilyName._hstring = 0;
      ActivationFactory = get_FontFamily(pStyle, &fontFamilyName._hstring);
      v12 = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
LABEL_24:
        OnFailure_2990_(ActivationFactory);
LABEL_25:
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spFontFamily);
        p_hSubText = &fontFamilyName;
        goto LABEL_17;
      }
    }
    else
    {
      Windows::Internal::StringReference::StringReference(
        (Windows::Internal::StringReference *)&value,
        (const wchar_t (*)[8])L"default");
      v23 = v22;
      WindowsDeleteString(fontFamilyName._hstring);
      fontFamilyName._hstring = 0;
      WindowsDuplicateString(*v23, &fontFamilyName._hstring);
    }
    v24 = userFontStyle;
    if ( userFontStyle == ClosedCaptionStyle_SmallCapitals )
      goto LABEL_30;
    if ( userFontStyle )
      goto LABEL_34;
    StringRawBuffer = WindowsGetStringRawBuffer(fontFamilyName._hstring, 0);
    if ( !(unsigned int)_o__wcsicmp(StringRawBuffer, L"smallCaps") )
    {
LABEL_30:
      value = 0;
      CValue::SetEnum8(&value, 2u);
      v26 = DirectUI::DependencyObject::SetValueByKnownIndex(spRun.ptr_, Typography_Capitals, &value);
      v12 = v26;
      if ( v26 < 0 )
      {
        OnFailure_2990_(v26);
        CValue::ReleaseAndReset(&value);
        goto LABEL_25;
      }
      CValue::ReleaseAndReset(&value);
    }
    v24 = userFontStyle;
    if ( userFontStyle == ClosedCaptionStyle_Default )
    {
      v27 = WindowsGetStringRawBuffer(fontFamilyName._hstring, 0);
      v28 = DirectUI::CCueStyler::ConvertUserFontStyle(&result, v27);
LABEL_35:
      ppStowedExceptions = (_STOWED_EXCEPTION_INFORMATION_V2 **)v28->_hstring;
      Windows::Internal::String::Initialize(&fontFamilyName, (HSTRING__ *const *)&ppStowedExceptions);
      if ( !this->m_spFontFamilyFactory.ptr_ )
      {
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&this->m_spFontFamilyFactory);
        Windows::Internal::StringReference::StringReference(
          &result,
          (const wchar_t (*)[33])RuntimeClass_Windows_UI_Xaml_Media_FontFamily);
        ActivationFactory = RoGetActivationFactory(
                              *v29,
                              &GUID_d5603377_3dae_4dcd_af09_f9498e9ec659,
                              &this->m_spFontFamilyFactory);
        v12 = ActivationFactory;
        if ( ActivationFactory < 0 )
          goto LABEL_24;
      }
      v30 = this->m_spFontFamilyFactory.ptr_;
      CreateInstanceWithName = v30->CreateInstanceWithName;
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spFontFamily);
      ActivationFactory = CreateInstanceWithName(v30, fontFamilyName._hstring, 0, 0, &spFontFamily.ptr_);
      v12 = ActivationFactory;
      if ( ActivationFactory < 0 )
        goto LABEL_24;
      ActivationFactory = spRun.ptr_->put_FontFamily(
                            &spRun.ptr_->Windows::UI::Xaml::Documents::ITextElement,
                            spFontFamily.ptr_);
      v12 = ActivationFactory;
      if ( ActivationFactory < 0 )
        goto LABEL_24;
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spFontFamily);
      Windows::Internal::String::~String(&fontFamilyName);
      spStyle2.ptr_ = 0;
      if ( !pStyle
        || (v11 = DirectUI::CCueStyler::CalculateFontSize(this, pStyle, (long double *)&spStyle2), v12 = v11, v11 >= 0) )
      {
        v11 = ((__int64 (__fastcall *)(Windows::UI::Xaml::Documents::ITextElement *))spRun.ptr_->put_FontSize)(&spRun.ptr_->Windows::UI::Xaml::Documents::ITextElement);
        v12 = v11;
        if ( v11 >= 0 )
        {
          fontWeight = 0;
          uiFontWeight.Weight = 0;
          if ( pStyle )
          {
            v11 = pStyle->get_FontWeight(pStyle, &fontWeight);
            v12 = v11;
            if ( v11 < 0 )
              goto LABEL_114;
          }
          else
          {
            fontWeight = TimedTextWeight_Normal;
          }
          p_m_spFontWeightsFactory = &this->m_spFontWeightsFactory;
          if ( !this->m_spFontWeightsFactory.ptr_ )
          {
            v11 = ctl::make<DirectUI::FontWeightsFactory>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::FontWeightsFactory> >)&this->m_spFontWeightsFactory);
            v12 = v11;
            if ( v11 < 0 )
              goto LABEL_114;
          }
          if ( fontWeight == TimedTextWeight_Normal )
          {
            v11 = p_m_spFontWeightsFactory->ptr_->get_Normal(
                    &p_m_spFontWeightsFactory->ptr_->Windows::UI::Text::IFontWeightsStatics,
                    &uiFontWeight);
            v12 = v11;
            if ( v11 < 0 )
              goto LABEL_114;
          }
          else if ( fontWeight == TimedTextWeight_Bold )
          {
            v11 = p_m_spFontWeightsFactory->ptr_->get_Bold(
                    &p_m_spFontWeightsFactory->ptr_->Windows::UI::Text::IFontWeightsStatics,
                    &uiFontWeight);
            v12 = v11;
            if ( v11 < 0 )
              goto LABEL_114;
          }
          v11 = ((__int64 (__fastcall *)(Windows::UI::Xaml::Documents::ITextElement *, _QWORD))spRun.ptr_->put_FontWeight)(
                  &spRun.ptr_->Windows::UI::Xaml::Documents::ITextElement,
                  uiFontWeight.Weight);
          v12 = v11;
          if ( v11 >= 0 )
          {
            spSolidColorBrush.ptr_ = 0;
            color = 0;
            v33 = ctl::make<DirectUI::SolidColorBrush>((ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::SolidColorBrush> >)&spSolidColorBrush);
            v12 = v33;
            if ( v33 >= 0 )
            {
              if ( isOutline )
              {
                if ( pStyle )
                {
                  v34 = pStyle->get_OutlineColor(pStyle, &color);
                  v12 = v34;
                  if ( v34 < 0 )
                    goto LABEL_70;
                }
                else
                {
                  *(_WORD *)&color.R = 0;
                  color.B = 0;
                  color.A = -1;
                }
                v34 = ((__int64 (__fastcall *)(Windows::UI::Xaml::Media::ISolidColorBrush *, _QWORD))spSolidColorBrush.ptr_->put_Color)(
                        &spSolidColorBrush.ptr_->Windows::UI::Xaml::Media::ISolidColorBrush,
                        *(unsigned int *)&color);
                v12 = v34;
                if ( v34 < 0 )
                  goto LABEL_70;
                goto LABEL_72;
              }
              if ( userForegroundOpacity == ClosedCaptionOpacity_Default
                && userForegroundColor == ClosedCaptionColor_Default )
              {
                if ( pStyle )
                {
                  v34 = pStyle->get_Foreground(pStyle, &color);
                  v12 = v34;
                  if ( v34 < 0 )
                    goto LABEL_70;
                }
                else
                {
                  *(_WORD *)&color.R = -1;
                  color.B = -1;
                  color.A = -1;
                }
                v34 = ((__int64 (__fastcall *)(Windows::UI::Xaml::Media::ISolidColorBrush *, _QWORD))spSolidColorBrush.ptr_->put_Color)(
                        &spSolidColorBrush.ptr_->Windows::UI::Xaml::Media::ISolidColorBrush,
                        *(unsigned int *)&color);
                v12 = v34;
                if ( v34 < 0 )
                {
LABEL_70:
                  OnFailure_2990_(v34);
LABEL_106:
                  ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spSolidColorBrush);
                  goto LABEL_115;
                }
LABEL_72:
                v34 = spRun.ptr_->put_Foreground(
                        &spRun.ptr_->Windows::UI::Xaml::Documents::ITextElement,
                        (Windows::UI::Xaml::Media::IBrush *)((__int64)&spSolidColorBrush.ptr_->Windows::UI::Xaml::Media::IBrush
                                                           & -(__int64)(spSolidColorBrush.ptr_ != 0)));
                v12 = v34;
                if ( v34 < 0 )
                  goto LABEL_70;
                ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spSolidColorBrush);
                v36 = TimedTextFlowDirection_LeftToRight;
                flow = TimedTextFlowDirection_LeftToRight;
                if ( pStyle )
                {
                  v37 = pStyle->get_FlowDirection(pStyle, &flow);
                  v12 = v37;
                  if ( v37 < 0 )
                  {
LABEL_75:
                    OnFailure_2990_(v37);
                    goto LABEL_115;
                  }
                  v36 = flow;
                }
                if ( v36 )
                {
                  if ( v36 == TimedTextFlowDirection_RightToLeft )
                  {
                    v37 = spRun.ptr_->put_FlowDirection(
                            &spRun.ptr_->Windows::UI::Xaml::Documents::IRun,
                            FlowDirection_RightToLeft);
                    v12 = v37;
                    if ( v37 < 0 )
                      goto LABEL_75;
                  }
                }
                else
                {
                  v37 = spRun.ptr_->put_FlowDirection(
                          &spRun.ptr_->Windows::UI::Xaml::Documents::IRun,
                          FlowDirection_LeftToRight);
                  v12 = v37;
                  if ( v37 < 0 )
                    goto LABEL_75;
                }
                if ( !pStyle )
                {
LABEL_97:
                  v37 = ctl::ComPtr<DirectUI::Run>::CopyTo<Windows::UI::Xaml::Documents::IRun>(&spRun, ppRun);
                  v12 = v37;
                  if ( v37 >= 0 )
                  {
                    ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&spRun);
                    return 0;
                  }
                  goto LABEL_75;
                }
                v38 = pStyle->__vftable;
                spStyle2.ptr_ = 0;
                QueryInterface = v38->QueryInterface;
                ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spStyle2);
                v40 = QueryInterface(pStyle, &GUID_655f492d_6111_4787_89cc_686fece57e14, (void **)&spStyle2.ptr_);
                v41 = v40;
                if ( v40 < 0 )
                {
                  OnFailure_2990_(v40);
                  ppStowedExceptions = 0;
                  cStowedExceptions = 0;
                  TraceForFailFast(v41);
                  GetStowedExceptionsForFailFast(&ppStowedExceptions, &cStowedExceptions);
                  RoFailFastWithErrorContextInternal2(v41, cStowedExceptions, ppStowedExceptions);
                }
                timedTextFontStyle = TimedTextFontStyle_Normal;
                v42 = spStyle2.ptr_->get_FontStyle(spStyle2.ptr_, &timedTextFontStyle);
                v12 = v42;
                if ( v42 < 0 )
                  goto LABEL_101;
                if ( timedTextFontStyle == TimedTextFontStyle_Oblique )
                {
                  v42 = spRun.ptr_->put_FontStyle(
                          &spRun.ptr_->Windows::UI::Xaml::Documents::ITextElement,
                          FontStyle_Oblique);
                  v12 = v42;
                  if ( v42 < 0 )
                    goto LABEL_101;
                }
                else if ( timedTextFontStyle == TimedTextFontStyle_Italic )
                {
                  v42 = spRun.ptr_->put_FontStyle(
                          &spRun.ptr_->Windows::UI::Xaml::Documents::ITextElement,
                          FontStyle_Italic);
                  v12 = v42;
                  if ( v42 < 0 )
                    goto LABEL_101;
                }
                fUnderLine = 0;
                v42 = spStyle2.ptr_->get_IsUnderlineEnabled(spStyle2.ptr_, &fUnderLine);
                v12 = v42;
                if ( v42 >= 0 )
                {
                  fStrikethrough[0] = 0;
                  v43 = fUnderLine != 0;
                  v44 = spStyle2.ptr_->get_IsLineThroughEnabled(spStyle2.ptr_, fStrikethrough);
                  v45 = v44;
                  if ( v44 < 0 )
                  {
                    OnFailure_2990_(v44);
                    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spStyle2);
                    v12 = v45;
                    goto LABEL_115;
                  }
                  if ( fStrikethrough[0] )
                    v43 |= 2u;
                  v42 = DirectUI::DependencyObject::SetValueByKnownIndex<enum Windows::UI::Xaml::Controls::ScrollBarVisibility>(
                          spRun.ptr_,
                          TextElement_TextDecorations,
                          v43);
                  v12 = v42;
                  if ( v42 >= 0 )
                  {
                    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spStyle2);
                    goto LABEL_97;
                  }
                }
LABEL_101:
                OnFailure_2990_(v42);
                ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spStyle2);
                goto LABEL_115;
              }
              v35 = (unsigned int)DirectUI::CCueStyler::ConvertUserColor(
                                    userForegroundColor,
                                    ClosedCaptionOpacity_Default);
              v33 = ((__int64 (__fastcall *)(Windows::UI::Xaml::Media::ISolidColorBrush *, _QWORD))spSolidColorBrush.ptr_->put_Color)(
                      &spSolidColorBrush.ptr_->Windows::UI::Xaml::Media::ISolidColorBrush,
                      v35);
              v12 = v33;
              if ( v33 >= 0 )
                goto LABEL_72;
            }
            OnFailure_2990_(v33);
            goto LABEL_106;
          }
        }
      }
LABEL_114:
      OnFailure_2990_(v11);
      goto LABEL_115;
    }
LABEL_34:
    v28 = DirectUI::CCueStyler::ConvertUserFontStyle(&result, v24);
    goto LABEL_35;
  }
  OnNewFailure_1172_((HRESULT)this);
  return 2147500035LL;
}

```

## disassembly

```asm
0x1806e9a88  push    rbp
0x1806e9a8a  push    rbx
0x1806e9a8b  push    rsi
0x1806e9a8c  push    rdi
0x1806e9a8d  push    r12
0x1806e9a8f  push    r13
0x1806e9a91  push    r14
0x1806e9a93  push    r15
0x1806e9a95  lea     rbp, [rsp-7]
0x1806e9a9a  sub     rsp, 0F8h
0x1806e9aa1  mov     rax, cs:__security_cookie
0x1806e9aa8  xor     rax, rsp
0x1806e9aab  mov     [rbp+3Fh+var_48], rax
0x1806e9aaf  mov     r12, [rbp+3Fh+ptr]
0x1806e9ab3  xor     r13d, r13d
0x1806e9ab6  mov     [rsp+130h+spRun.ptr_], r13
0x1806e9abb  mov     r15d, start
0x1806e9abe  mov     rsi, pStyle
0x1806e9ac1  mov     rdi, pLine
0x1806e9ac4  mov     r14, this
0x1806e9ac7  test    r12, r12
0x1806e9aca  jz      loc_1806EA48C
0x1806e9ad0  lea     this, [rsp+130h+spRun]; ppNewInstance
0x1806e9ad5  mov     [r12], r13
0x1806e9ad9  call    ??$make@VRun@DirectUI@@@ctl@@YAJV?$ComPtrRef@V?$ComPtr@VRun@DirectUI@@@ctl@@@Internal@0@@Z; ctl::make<DirectUI::Run>(ctl::Internal::ComPtrRef<ctl::ComPtr<DirectUI::Run>>)
0x1806e9ade  mov     ebx, eax
0x1806e9ae0  test    eax, eax
0x1806e9ae2  js      loc_1806EA477
0x1806e9ae8  mov     this, [r14+28h]
0x1806e9aec  mov     [rbp+3Fh+userForegroundOpacity], r13d
0x1806e9af0  mov     [rbp+3Fh+userForegroundColor], r13d
0x1806e9af4  mov     [rbp+3Fh+userFontStyle], r13d
0x1806e9af8  test    this, this
0x1806e9afb  jz      loc_1806E9B9F
0x1806e9b01  mov     rax, [this]
0x1806e9b04  lea     pLine, [rbp+3Fh+userForegroundColor]
0x1806e9b08  mov     rax, [rax+30h]
0x1806e9b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806e9b11  mov     ebx, eax
0x1806e9b13  mov     eax, 80000000h
0x1806e9b18  lea     ecx, [rbx+rax]
0x1806e9b1b  test    eax, ecx
0x1806e9b1d  jnz     short loc_1806E9B33
0x1806e9b1f  cmp     ebx, 80070005h
0x1806e9b25  jz      short loc_1806E9B33
0x1806e9b27  mov     ecx, ebx; failedFrameHR
0x1806e9b29  call    OnFailure_2990_
0x1806e9b2e  jmp     loc_1806EA47E
0x1806e9b33  mov     this, [r14+28h]
0x1806e9b37  lea     pLine, [rbp+3Fh+userForegroundOpacity]
0x1806e9b3b  mov     rax, [this]
0x1806e9b3e  mov     rax, [rax+40h]
0x1806e9b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806e9b47  mov     ebx, eax
0x1806e9b49  mov     eax, 80000000h
0x1806e9b4e  lea     ecx, [rbx+rax]
0x1806e9b51  test    eax, ecx
0x1806e9b53  jnz     short loc_1806E9B69
0x1806e9b55  cmp     ebx, 80070005h
0x1806e9b5b  jz      short loc_1806E9B69
0x1806e9b5d  mov     ecx, ebx; failedFrameHR
0x1806e9b5f  call    OnFailure_2990_
0x1806e9b64  jmp     loc_1806EA47E
0x1806e9b69  mov     this, [r14+28h]
0x1806e9b6d  lea     pLine, [rbp+3Fh+userFontStyle]
0x1806e9b71  mov     rax, [this]
0x1806e9b74  mov     rax, [rax+50h]
0x1806e9b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806e9b7d  mov     ebx, eax
0x1806e9b7f  mov     eax, 80000000h
0x1806e9b84  lea     ecx, [rbx+rax]
0x1806e9b87  test    eax, ecx
0x1806e9b89  jnz     short loc_1806E9B9F
0x1806e9b8b  cmp     ebx, 80070005h
0x1806e9b91  jz      short loc_1806E9B9F
0x1806e9b93  mov     ecx, ebx; failedFrameHR
0x1806e9b95  call    OnFailure_2990_
0x1806e9b9a  jmp     loc_1806EA47E
0x1806e9b9f  mov     rax, [rdi]
0x1806e9ba2  xor     ecx, ecx; string
0x1806e9ba4  cmp     [rbp+3Fh+arg_20], 0FFFFFFFFh
0x1806e9ba8  mov     [rsp+130h+hSubText._hstring], r13
0x1806e9bad  mov     rbx, [rax+30h]
0x1806e9bb1  jnz     short loc_1806E9C20
0x1806e9bb3  call    cs:__imp_WindowsDeleteString
0x1806e9bb9  lea     pLine, [rsp+130h+hSubText]
0x1806e9bbe  mov     [rsp+130h+hSubText._hstring], r13
0x1806e9bc3  mov     this, rdi
0x1806e9bc6  mov     rax, rbx
0x1806e9bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806e9bce  mov     ebx, eax
0x1806e9bd0  test    eax, eax
0x1806e9bd2  js      short loc_1806E9C0A
0x1806e9bd4  mov     this, [rsp+130h+spRun.ptr_]
0x1806e9bd9  mov     pLine, [rsp+130h+hSubText._hstring]
0x1806e9bde  add     this, 108h
0x1806e9be5  mov     rax, [this]
0x1806e9be8  mov     rax, [rax+38h]
0x1806e9bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806e9bf1  mov     ebx, eax
0x1806e9bf3  test    eax, eax
0x1806e9bf5  js      short loc_1806E9C01
0x1806e9bf7  lea     this, [rsp+130h+hSubText]
0x1806e9bfc  jmp     loc_1806E9C9B
0x1806e9c01  mov     ecx, eax; failedFrameHR
0x1806e9c03  call    OnFailure_2990_
0x1806e9c08  jmp     short loc_1806E9C11
0x1806e9c0a  mov     ecx, eax; failedFrameHR
0x1806e9c0c  call    OnFailure_2990_
0x1806e9c11  lea     this, [rsp+130h+hSubText]; this
0x1806e9c16  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1806e9c1b  jmp     loc_1806EA47E
0x1806e9c20  mov     [rbp+3Fh+var_B0._hstring], r13
0x1806e9c24  call    cs:__imp_WindowsDeleteString
0x1806e9c2a  lea     pLine, [rbp+3Fh+var_B0]
0x1806e9c2e  mov     [rbp+3Fh+var_B0._hstring], r13
0x1806e9c32  mov     this, rdi
0x1806e9c35  mov     rax, rbx
0x1806e9c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806e9c3d  mov     ebx, eax
0x1806e9c3f  test    eax, eax
0x1806e9c41  js      loc_1806EA45D
0x1806e9c47  mov     r8d, [rbp+3Fh+arg_20]; length
0x1806e9c4b  lea     r9, [rsp+130h+hSubText]; newString
0x1806e9c50  mov     edx, r15d; startIndex
0x1806e9c53  lea     this, [rbp+3Fh+var_B0]; this
0x1806e9c57  call    ?Substring@String@Internal@Windows@@QEBAJIIPEAV123@@Z; Windows::Internal::String::Substring(uint,uint,Windows::Internal::String *)
0x1806e9c5c  mov     ebx, eax
0x1806e9c5e  test    eax, eax
0x1806e9c60  js      loc_1806EA454
0x1806e9c66  mov     this, [rsp+130h+spRun.ptr_]
0x1806e9c6b  mov     pLine, [rsp+130h+hSubText._hstring]
0x1806e9c70  add     this, 108h
0x1806e9c77  mov     rax, [this]
0x1806e9c7a  mov     rax, [rax+38h]
0x1806e9c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806e9c83  mov     ebx, eax
0x1806e9c85  test    eax, eax
0x1806e9c87  js      loc_1806EA44B
0x1806e9c8d  lea     this, [rsp+130h+hSubText]; this
0x1806e9c92  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1806e9c97  lea     this, [rbp+3Fh+var_B0]; this
0x1806e9c9b  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1806e9ca0  mov     [rsp+130h+fontFamilyName._hstring], r13
0x1806e9ca5  mov     [rsp+130h+spFontFamily.ptr_], r13
0x1806e9caa  test    rsi, rsi
0x1806e9cad  jz      short loc_1806E9CF4
0x1806e9caf  mov     rax, [rsi]
0x1806e9cb2  xor     ecx, ecx; string
0x1806e9cb4  mov     rbx, [rax+40h]
0x1806e9cb8  call    cs:__imp_WindowsDeleteString
0x1806e9cbe  lea     pLine, [rsp+130h+fontFamilyName]
0x1806e9cc3  mov     [rsp+130h+fontFamilyName._hstring], r13
0x1806e9cc8  mov     this, rsi
0x1806e9ccb  mov     rax, rbx
0x1806e9cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806e9cd3  mov     ebx, eax
0x1806e9cd5  test    eax, eax
0x1806e9cd7  jns     short loc_1806E9D25
0x1806e9cd9  mov     ecx, eax; failedFrameHR
0x1806e9cdb  call    OnFailure_2990_
0x1806e9ce0  lea     this, [rsp+130h+spFontFamily]; this
0x1806e9ce5  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1806e9cea  lea     this, [rsp+130h+fontFamilyName]
0x1806e9cef  jmp     loc_1806E9C16
0x1806e9cf4  lea     pLine, aDefault; "default"
0x1806e9cfb  lea     this, [rbp+3Fh+value]; this
0x1806e9cff  call    ??$?0$07@StringReference@Internal@Windows@@QEAA@AEAY07$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[8])
0x1806e9d04  mov     this, [rsp+130h+fontFamilyName._hstring]; string
0x1806e9d09  mov     rbx, rax
0x1806e9d0c  call    cs:__imp_WindowsDeleteString
0x1806e9d12  mov     [rsp+130h+fontFamilyName._hstring], r13
0x1806e9d17  lea     pLine, [rsp+130h+fontFamilyName]; newString
0x1806e9d1c  mov     this, [rbx]; string
0x1806e9d1f  call    cs:__imp_WindowsDuplicateString
0x1806e9d25  mov     edx, [rbp+3Fh+userFontStyle]; fontStyle
0x1806e9d28  cmp     edx, 7
0x1806e9d2b  jz      short loc_1806E9D52
0x1806e9d2d  test    edx, edx
0x1806e9d2f  jnz     short loc_1806E9DAC
0x1806e9d31  mov     this, [rsp+130h+fontFamilyName._hstring]; string
0x1806e9d36  xor     edx, edx; length
0x1806e9d38  call    cs:__imp_WindowsGetStringRawBuffer
0x1806e9d3e  mov     this, rax
0x1806e9d41  lea     pLine, aSmallcaps_0; "smallCaps"
0x1806e9d48  call    cs:__imp__o__wcsicmp
0x1806e9d4e  test    eax, eax
0x1806e9d50  jnz     short loc_1806E9D8A
0x1806e9d52  xorps   xmm0, xmm0
0x1806e9d55  lea     this, [rbp+3Fh+value]; this
0x1806e9d59  mov     dl, 2; value
0x1806e9d5b  movups  xmmword ptr [rbp+3Fh+value.m_value], xmm0
0x1806e9d5f  call    ?SetEnum8@CValue@@QEAAXE@Z; CValue::SetEnum8(uchar)
0x1806e9d64  mov     this, [rsp+130h+spRun.ptr_]; this
0x1806e9d69  lea     pStyle, [rbp+3Fh+value]; value
0x1806e9d6d  mov     edx, 3Eh ; '>'; ePropertyIndex
0x1806e9d72  call    ?SetValueByKnownIndex@DependencyObject@DirectUI@@QEAAJW4KnownPropertyIndex@@AEBVCValue@@@Z; DirectUI::DependencyObject::SetValueByKnownIndex(KnownPropertyIndex,CValue const &)
0x1806e9d77  mov     ebx, eax
0x1806e9d79  test    eax, eax
0x1806e9d7b  js      loc_1806EA436
0x1806e9d81  lea     this, [rbp+3Fh+value]; this
0x1806e9d85  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x1806e9d8a  mov     edx, [rbp+3Fh+userFontStyle]
0x1806e9d8d  test    edx, edx
0x1806e9d8f  jnz     short loc_1806E9DAC
0x1806e9d91  mov     this, [rsp+130h+fontFamilyName._hstring]; string
0x1806e9d96  xor     edx, edx; length
0x1806e9d98  call    cs:__imp_WindowsGetStringRawBuffer
0x1806e9d9e  mov     pLine, rax; fontStyle
0x1806e9da1  lea     this, [rbp+3Fh+result]; result
0x1806e9da5  call    ?ConvertUserFontStyle@CCueStyler@DirectUI@@SA?AVStringReference@Internal@Windows@@PEBG@Z; DirectUI::CCueStyler::ConvertUserFontStyle(ushort const *)
0x1806e9daa  jmp     short loc_1806E9DB5
0x1806e9dac  lea     this, [rbp+3Fh+result]; result
0x1806e9db0  call    ?ConvertUserFontStyle@CCueStyler@DirectUI@@SA?AVStringReference@Internal@Windows@@W4ClosedCaptionStyle@ClosedCaptioning@Media@5@@Z; DirectUI::CCueStyler::ConvertUserFontStyle(Windows::Media::ClosedCaptioning::ClosedCaptionStyle)
0x1806e9db5  mov     this, [rax]
0x1806e9db8  lea     pLine, [rbp+3Fh+ppStowedExceptions]; other
0x1806e9dbc  mov     [rbp+3Fh+ppStowedExceptions], this
0x1806e9dc0  lea     this, [rsp+130h+fontFamilyName]; this
0x1806e9dc5  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x1806e9dca  lea     rdi, [r14+30h]
0x1806e9dce  cmp     [rdi], r13
0x1806e9dd1  jnz     short loc_1806E9E10
0x1806e9dd3  mov     this, rdi; this
0x1806e9dd6  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1806e9ddb  lea     pLine, ?RuntimeClass_Windows_UI_Xaml_Media_FontFamily@@3QBGB; stringRef
0x1806e9de2  lea     this, [rbp+3Fh+result]; this
0x1806e9de6  call    ??$?0$0CB@@StringReference@Internal@Windows@@QEAA@AEAY0CB@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[33])
0x1806e9deb  mov     pStyle, rdi
0x1806e9dee  lea     pLine, _GUID_d5603377_3dae_4dcd_af09_f9498e9ec659
0x1806e9df5  mov     this, [rax]
0x1806e9df8  call    cs:__imp_RoGetActivationFactory
0x1806e9dfe  mov     ebx, eax
0x1806e9e00  test    eax, eax
0x1806e9e02  jns     short loc_1806E9E10
0x1806e9e04  mov     ecx, eax; failedFrameHR
0x1806e9e06  call    OnFailure_2990_
0x1806e9e0b  jmp     loc_1806E9CE0
0x1806e9e10  mov     rdi, [rdi]
0x1806e9e13  lea     this, [rsp+130h+spFontFamily]; this
0x1806e9e18  mov     rax, [rdi]
0x1806e9e1b  mov     rbx, [rax+30h]
0x1806e9e1f  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1806e9e24  mov     pLine, [rsp+130h+fontFamilyName._hstring]
0x1806e9e29  lea     rax, [rsp+130h+spFontFamily]
0x1806e9e2e  mov     [rsp+130h+var_110], rax
0x1806e9e33  xor     start, start
0x1806e9e36  mov     rax, rbx
0x1806e9e39  xor     r8d, r8d
0x1806e9e3c  mov     this, rdi
0x1806e9e3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806e9e44  mov     ebx, eax
0x1806e9e46  test    eax, eax
0x1806e9e48  js      loc_1806EA42A
0x1806e9e4e  mov     this, [rsp+130h+spRun.ptr_]
0x1806e9e53  mov     pLine, [rsp+130h+spFontFamily.ptr_]
0x1806e9e58  add     this, 0B8h
0x1806e9e5f  mov     rax, [this]
0x1806e9e62  mov     rax, [rax+50h]
0x1806e9e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806e9e6b  mov     ebx, eax
0x1806e9e6d  test    eax, eax
0x1806e9e6f  js      loc_1806EA41E
0x1806e9e75  lea     this, [rsp+130h+spFontFamily]; this
0x1806e9e7a  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x1806e9e7f  lea     this, [rsp+130h+fontFamilyName]; this
0x1806e9e84  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1806e9e89  xorps   xmm0, xmm0
0x1806e9e8c  movsd   [rsp+130h+spStyle2.ptr_], xmm0
0x1806e9e92  test    rsi, rsi
0x1806e9e95  jz      short loc_1806E9EC1
0x1806e9e97  lea     pStyle, [rsp+130h+spStyle2]; actualSize
0x1806e9e9c  mov     pLine, rsi; pStyle
0x1806e9e9f  mov     this, r14; this
0x1806e9ea2  call    ?CalculateFontSize@CCueStyler@DirectUI@@AEAAJPEAUITimedTextStyle@Core@Media@Windows@@PEAN@Z; DirectUI::CCueStyler::CalculateFontSize(Windows::Media::Core::ITimedTextStyle *,double *)
0x1806e9ea7  mov     ebx, eax
0x1806e9ea9  test    eax, eax
0x1806e9eab  jns     short loc_1806E9EB9
0x1806e9ead  mov     ecx, eax; failedFrameHR
0x1806e9eaf  call    OnFailure_2990_
0x1806e9eb4  jmp     loc_1806EA47E
0x1806e9eb9  movsd   xmm1, [rsp+130h+spStyle2.ptr_]
0x1806e9ebf  jmp     short loc_1806E9ED4
0x1806e9ec1  movsd   xmm1, qword ptr [r14]
0x1806e9ec6  divsd   xmm1, cs:__real@4034000000000000
0x1806e9ece  mulsd   xmm1, qword ptr [r14+10h]
0x1806e9ed4  mov     this, [rsp+130h+spRun.ptr_]
0x1806e9ed9  add     this, 0B8h
0x1806e9ee0  mov     rax, [this]
0x1806e9ee3  mov     rax, [rax+40h]
0x1806e9ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806e9eec  mov     ebx, eax
0x1806e9eee  test    eax, eax
0x1806e9ef0  js      loc_1806EA415
0x1806e9ef6  mov     [rsp+130h+fontWeight], r13d
0x1806e9efb  mov     r15d, 190h
0x1806e9f01  mov     [rsp+130h+uiFontWeight.Weight], r13w
0x1806e9f07  test    rsi, rsi
0x1806e9f0a  jz      short loc_1806E9F32
0x1806e9f0c  mov     rax, [rsi]
0x1806e9f0f  lea     pLine, [rsp+130h+fontWeight]
  ... truncated ...
```
