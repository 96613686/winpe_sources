# DirectUI::ContentDialog::ChangeVisualState(bool)

- ea: `0x18059c7b0`
- end: `0x18059cdbc`
- name: `?ChangeVisualState@ContentDialog@DirectUI@@UEAAJ_N@Z`
- size: `1548`
- prototype: `HRESULT __fastcall(DirectUI::ContentDialog *this, bool useTransitions)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180004bc0`
- `0x1800053b0`
- `0x18000616c`
- `0x180079624`
- `0x1801e5458`
- `0x180243e00`
- `0x1802456ac`
- `0x18059c7b0`
- `0x18059cdc4`
- `0x18063f664`
- `0x18076e110`
- `0x1808eb2c8`
- `0x1808ebaa0`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18059c915`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18059c945`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18059c97c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18059cc3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18059c915`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18059c945`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18059c97c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18059cc3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18059c9a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18059c9af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18059c9bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18059c9a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18059c9af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18059c9bb`
- `ext-ms-win-dwmapi-ext-l1-1-0!DwmpGetColorizationParameters` at `0x18059cd16`
- `ext-ms-win-dwmapi-ext-l1-1-0!DwmpGetColorizationParameters` at `0x18059cd16`

## pseudocode

```c
__int64 __fastcall DirectUI::ContentDialog::ChangeVisualState(DirectUI::ContentDialog *this, bool useTransitions)
{
  Windows::UI::Xaml::Controls::IContentDialog *v5; // r14
  HRESULT v6; // eax
  unsigned int v7; // ebx
  HSTRING__ **v8; // rax
  HRESULT v9; // eax
  HSTRING__ *hstring; // rdi
  __int64 (__fastcall *v11)(HSTRING__ *, ctl::ComPtr<DirectUI::DependencyObject> *); // rbx
  HRESULT v12; // eax
  const wchar_t *v13; // r8
  HRESULT v14; // eax
  Windows::UI::Xaml::Controls::IContentDialog_vtbl *v15; // rax
  HRESULT (__fastcall *get_PrimaryButtonText)(Windows::UI::Xaml::Controls::IContentDialog *, HSTRING__ **); // rbx
  HRESULT v17; // eax
  Windows::UI::Xaml::Controls::IContentDialog_vtbl *v18; // rax
  HRESULT (__fastcall *get_SecondaryButtonText)(Windows::UI::Xaml::Controls::IContentDialog *, HSTRING__ **); // rbx
  HRESULT v20; // eax
  HRESULT (__fastcall *get_CloseButtonText)(Windows::UI::Xaml::Controls::IContentDialog2 *, HSTRING__ **); // rbx
  HRESULT v22; // eax
  BOOL IsStringEmpty; // ebx
  BOOL v24; // edi
  BOOL v25; // eax
  const wchar_t *v26; // r8
  const wchar_t *v27; // rcx
  Windows::UI::Xaml::Controls::IContentDialog2_vtbl *v28; // rax
  HRESULT v29; // eax
  const wchar_t *v30; // r14
  HRESULT IsAncestorOf; // eax
  unsigned int v32; // edi
  IUnknown *m_value; // rax
  DirectUI::DependencyObject *ptr; // rbx
  HRESULT v35; // eax
  DirectUI::ContentDialog::PlacementMode m_placementMode; // eax
  const wchar_t *v37; // r8
  const wchar_t *v38; // r8
  bool v39; // bl
  const wchar_t *v40; // r8
  unsigned __int8 ignored; // [rsp+20h] [rbp-50h] BYREF
  unsigned __int8 isFocusInCommandArea; // [rsp+21h] [rbp-4Fh] BYREF
  unsigned __int8 fullSizeDesired[6]; // [rsp+22h] [rbp-4Eh] BYREF
  ctl::ComPtr<DirectUI::DependencyObject> focusedElement; // [rsp+28h] [rbp-48h] BYREF
  Windows::Internal::String defaultButton; // [rsp+30h] [rbp-40h] BYREF
  Windows::Internal::String secondaryText; // [rsp+38h] [rbp-38h] BYREF
  _DWM_COLORIZATION_PARAMETERS colorizationParameters; // [rsp+40h] [rbp-30h] BYREF

  if ( this->m_templateVersion == Unsupported )
    return 0;
  v5 = &this->Windows::UI::Xaml::Controls::IContentDialog;
  fullSizeDesired[0] = 0;
  v6 = this->get_FullSizeDesired(&this->Windows::UI::Xaml::Controls::IContentDialog, fullSizeDesired);
  v7 = v6;
  if ( v6 < 0 )
  {
    OnFailure_2990_(v6);
    return v7;
  }
  if ( this->m_templateVersion == PhoneBlue )
  {
    secondaryText._hstring = 0;
    Windows::Internal::StringReference::StringReference(
      (Windows::Internal::StringReference *)&colorizationParameters,
      (const wchar_t (*)[44])RuntimeClass_Windows_Graphics_Display_DisplayInformation);
    v9 = ctl::GetActivationFactory<ctl::ComPtr<Windows::Graphics::Display::IDisplayInformationStatics>>(
           *v8,
           (ctl::Internal::ComPtrRef<ctl::ComPtr<Windows::Graphics::Display::IDisplayInformationStatics> >)&secondaryText);
    v7 = v9;
    if ( v9 < 0 )
    {
      OnFailure_2990_(v9);
      goto LABEL_27;
    }
    hstring = secondaryText._hstring;
    focusedElement.ptr_ = 0;
    v11 = *(__int64 (__fastcall **)(HSTRING__ *, ctl::ComPtr<DirectUI::DependencyObject> *))(*(_QWORD *)secondaryText._hstring
                                                                                           + 48LL);
    ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&focusedElement);
    v12 = v11(hstring, &focusedElement);
    v7 = v12;
    if ( v12 < 0
      || (LODWORD(defaultButton._hstring) = 0,
          v12 = ((__int64 (__fastcall *)(DirectUI::DependencyObject *, Windows::Internal::String *))focusedElement.ptr_->GetValue)(
                  focusedElement.ptr_,
                  &defaultButton),
          v7 = v12,
          v12 < 0) )
    {
      OnFailure_2990_(v12);
LABEL_25:
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&focusedElement);
LABEL_27:
      ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&secondaryText);
      return v7;
    }
    v13 = 0;
    if ( LODWORD(defaultButton._hstring) != 1 )
    {
      if ( LODWORD(defaultButton._hstring) == 2 )
        goto LABEL_12;
      if ( LODWORD(defaultButton._hstring) != 4 )
      {
        if ( LODWORD(defaultButton._hstring) != 8 )
        {
LABEL_14:
          isFocusInCommandArea = 0;
          v14 = DirectUI::Control::GoToState(this, useTransitions, v13, &isFocusInCommandArea);
          v7 = v14;
          if ( v14 >= 0 )
          {
            ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&focusedElement);
            ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&secondaryText);
            goto LABEL_16;
          }
          OnFailure_2990_(v14);
          goto LABEL_25;
        }
LABEL_12:
        v13 = L"Portrait";
        goto LABEL_14;
      }
    }
    v13 = L"Landscape";
    goto LABEL_14;
  }
LABEL_16:
  if ( this->m_templateVersion < Redstone2 )
    goto LABEL_65;
  v15 = v5->__vftable;
  defaultButton._hstring = 0;
  get_PrimaryButtonText = v15->get_PrimaryButtonText;
  WindowsDeleteString(0);
  defaultButton._hstring = 0;
  v17 = get_PrimaryButtonText(v5, &defaultButton._hstring);
  v7 = v17;
  if ( v17 < 0 )
  {
    OnFailure_2990_(v17);
    if ( defaultButton._hstring )
      WindowsDeleteString(defaultButton._hstring);
    return v7;
  }
  v18 = v5->__vftable;
  secondaryText._hstring = 0;
  get_SecondaryButtonText = v18->get_SecondaryButtonText;
  WindowsDeleteString(0);
  secondaryText._hstring = 0;
  v20 = get_SecondaryButtonText(v5, &secondaryText._hstring);
  v7 = v20;
  if ( v20 < 0 )
  {
    OnFailure_2990_(v20);
    goto LABEL_62;
  }
  focusedElement.ptr_ = 0;
  get_CloseButtonText = this->get_CloseButtonText;
  WindowsDeleteString(0);
  focusedElement.ptr_ = 0;
  v22 = get_CloseButtonText(&this->Windows::UI::Xaml::Controls::IContentDialog2, (HSTRING__ **)&focusedElement);
  v7 = v22;
  if ( v22 < 0 )
  {
LABEL_60:
    OnFailure_2990_(v22);
    Windows::Internal::String::~String((Windows::Internal::String *)&focusedElement);
LABEL_62:
    Windows::Internal::String::~String(&secondaryText);
    Windows::Internal::String::~String(&defaultButton);
    return v7;
  }
  IsStringEmpty = WindowsIsStringEmpty(defaultButton._hstring);
  v24 = WindowsIsStringEmpty(secondaryText._hstring);
  v25 = WindowsIsStringEmpty((HSTRING)focusedElement.ptr_);
  if ( IsStringEmpty )
  {
    if ( !v24 )
    {
      if ( v25 )
        v26 = L"SecondaryVisible";
      else
        v26 = L"SecondaryAndCloseVisible";
      goto LABEL_38;
    }
    v26 = L"CloseVisible";
    v27 = L"NoneVisible";
  }
  else
  {
    if ( v24 )
    {
      if ( v25 )
        v26 = L"PrimaryVisible";
      else
        v26 = L"PrimaryAndCloseVisible";
      goto LABEL_38;
    }
    v26 = L"AllVisible";
    v27 = L"PrimaryAndSecondaryVisible";
  }
  if ( v25 )
    v26 = v27;
LABEL_38:
  isFocusInCommandArea = 0;
  v22 = DirectUI::Control::GoToState(this, useTransitions, v26, &isFocusInCommandArea);
  v7 = v22;
  if ( v22 < 0 )
    goto LABEL_60;
  Windows::Internal::String::~String((Windows::Internal::String *)&focusedElement);
  Windows::Internal::String::~String(&secondaryText);
  Windows::Internal::String::~String(&defaultButton);
  v28 = this->DirectUI::ContentDialogGenerated::Windows::UI::Xaml::Controls::IContentDialog2::IInspectable::IUnknown::__vftable;
  LODWORD(defaultButton._hstring) = 0;
  v29 = v28->get_DefaultButton(
          &this->Windows::UI::Xaml::Controls::IContentDialog2,
          (Windows::UI::Xaml::Controls::ContentDialogButton *)&defaultButton);
  v7 = v29;
  if ( v29 >= 0 )
  {
    v30 = L"NoDefaultButton";
    if ( LODWORD(defaultButton._hstring) )
    {
      focusedElement.ptr_ = 0;
      ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&focusedElement);
      IsAncestorOf = DirectUI::DependencyObject::GetFocusedElement(this, &focusedElement.ptr_);
      v32 = IsAncestorOf;
      if ( IsAncestorOf < 0
        || (m_value = this->m_tpCommandSpacePart.m_trackerReference.m_value,
            ptr = focusedElement.ptr_,
            isFocusInCommandArea = 0,
            IsAncestorOf = DirectUI::DependencyObject::IsAncestorOf(
                             (DirectUI::DependencyObject *)(-(__int64)(m_value != 0) & (unsigned __int64)&m_value[-62]),
                             focusedElement.ptr_,
                             &isFocusInCommandArea),
            v32 = IsAncestorOf,
            IsAncestorOf < 0) )
      {
        OnFailure_2990_(IsAncestorOf);
        ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&focusedElement);
        return v32;
      }
      if ( LODWORD(defaultButton._hstring) == 1 )
      {
        if ( !isFocusInCommandArea
          || ctl::are_equal<Windows::UI::Xaml::Controls::Primitives::IButtonBase,DirectUI::DependencyObject>(
               (Windows::UI::Xaml::Controls::Primitives::IButtonBase *)this->m_tpPrimaryButtonPart.m_trackerReference.m_value,
               ptr) )
        {
          v30 = L"PrimaryAsDefaultButton";
        }
      }
      else if ( LODWORD(defaultButton._hstring) == 2 )
      {
        if ( !isFocusInCommandArea
          || ctl::are_equal<Windows::UI::Xaml::Controls::Primitives::IButtonBase,DirectUI::DependencyObject>(
               (Windows::UI::Xaml::Controls::Primitives::IButtonBase *)this->m_tpSecondaryButtonPart.m_trackerReference.m_value,
               ptr) )
        {
          v30 = L"SecondaryAsDefaultButton";
        }
      }
      else if ( LODWORD(defaultButton._hstring) == 3
             && (!isFocusInCommandArea
              || ctl::are_equal<Windows::UI::Xaml::Controls::Primitives::IButtonBase,DirectUI::DependencyObject>(
                   (Windows::UI::Xaml::Controls::Primitives::IButtonBase *)this->m_tpCloseButtonPart.m_trackerReference.m_value,
                   ptr)) )
      {
        v30 = L"CloseAsDefaultButton";
      }
      ctl::ComPtr<DirectUI::Storyboard>::InternalRelease((ctl::ComPtr<DirectUI::SoftwareBitmapSource> *)&focusedElement);
    }
    ignored = 0;
    v35 = DirectUI::Control::GoToState(this, useTransitions, v30, &ignored);
    v7 = v35;
    if ( v35 < 0 )
      goto LABEL_86;
LABEL_65:
    if ( this->m_templateVersion >= Redstone3 )
    {
      m_placementMode = this->m_placementMode;
      if ( m_placementMode == InPlace )
      {
        ignored = 0;
        if ( !this->m_isShowing || (v37 = L"DialogShowing", this->m_hideInProgress) )
          v37 = L"DialogHidden";
        v35 = DirectUI::Control::GoToState(this, 1, v37, &ignored);
        v7 = v35;
        if ( v35 < 0 )
          goto LABEL_86;
      }
      else if ( m_placementMode )
      {
        ignored = 0;
        v35 = DirectUI::Control::GoToState(this, 0, L"DialogShowingWithoutSmokeLayer", &ignored);
        v7 = v35;
        if ( v35 < 0 )
        {
LABEL_86:
          OnFailure_2990_(v35);
          return v7;
        }
      }
      v38 = L"FullDialogSizing";
      ignored = 0;
      if ( !fullSizeDesired[0] )
        v38 = L"DefaultDialogSizing";
      v35 = DirectUI::Control::GoToState(this, useTransitions, v38, &ignored);
      v7 = v35;
      if ( v35 < 0 )
        goto LABEL_86;
      memset(&colorizationParameters, 0, sizeof(colorizationParameters));
      v39 = 0;
      if ( (int)DwmpGetColorizationParameters(&colorizationParameters) >= 0 )
        v39 = colorizationParameters.enableWindowColorization != 0;
      ignored = 0;
      v40 = L"AccentColorBorder";
      if ( !v39 )
        v40 = L"NoBorder";
      v35 = DirectUI::Control::GoToState(this, useTransitions, v40, &ignored);
      v7 = v35;
      if ( v35 < 0 )
        goto LABEL_86;
    }
    if ( this->m_templateVersion <= PhoneBlue )
      return 0;
    v35 = DirectUI::ContentDialog::AdjustVisualStateForInputPane(this);
    v7 = v35;
    if ( v35 >= 0 )
      return 0;
    goto LABEL_86;
  }
  OnFailure_2990_(v29);
  return v7;
}

```

## disassembly

```asm
0x18059c7b0  mov     [rsp-28h+arg_10], rbx
0x18059c7b5  mov     [rsp-28h+arg_18], rsi
0x18059c7ba  push    rbp
0x18059c7bb  push    rdi
0x18059c7bc  push    r12
0x18059c7be  push    r14
0x18059c7c0  push    r15
0x18059c7c2  mov     rbp, rsp
0x18059c7c5  sub     rsp, 70h
0x18059c7c9  mov     rax, cs:__security_cookie
0x18059c7d0  xor     rax, rsp
0x18059c7d3  mov     [rbp+var_10], rax
0x18059c7d7  xor     r12d, r12d
0x18059c7da  mov     r15b, useTransitions
0x18059c7dd  mov     rsi, this
0x18059c7e0  cmp     [this+4D0h], r12d
0x18059c7e7  jnz     short loc_18059C7F0
0x18059c7e9  xor     eax, eax
0x18059c7eb  jmp     loc_18059CD97
0x18059c7f0  lea     r14, [this+238h]
0x18059c7f7  mov     [rbp+fullSizeDesired], r12b
0x18059c7fb  mov     rax, [r14]
0x18059c7fe  lea     rdx, [rbp+fullSizeDesired]
0x18059c802  mov     this, r14
0x18059c805  mov     rax, [rax+50h]
0x18059c809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18059c80e  mov     ebx, eax
0x18059c810  test    eax, eax
0x18059c812  js      loc_18059CD8E
0x18059c818  cmp     dword ptr [rsi+4D0h], 1
0x18059c81f  jnz     loc_18059C8FB
0x18059c825  lea     rdx, ?RuntimeClass_Windows_Graphics_Display_DisplayInformation@@3QBGB; stringRef
0x18059c82c  mov     [rbp+secondaryText._hstring], r12
0x18059c830  lea     this, [rbp+colorizationParameters]; this
0x18059c834  call    ??$?0$0CM@@StringReference@Internal@Windows@@QEAA@AEAY0CM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[44])
0x18059c839  lea     rdx, [rbp+secondaryText]; factory
0x18059c83d  mov     this, [rax]; activatableClassId
0x18059c840  call    ??$GetActivationFactory@V?$ComPtr@UIDisplayInformationStatics@Display@Graphics@Windows@@@ctl@@@ctl@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIDisplayInformationStatics@Display@Graphics@Windows@@@ctl@@@Internal@0@@Z; ctl::GetActivationFactory<ctl::ComPtr<Windows::Graphics::Display::IDisplayInformationStatics>>(HSTRING__ *,ctl::Internal::ComPtrRef<ctl::ComPtr<Windows::Graphics::Display::IDisplayInformationStatics>>)
0x18059c845  mov     ebx, eax
0x18059c847  test    eax, eax
0x18059c849  js      loc_18059C9FD
0x18059c84f  mov     rdi, [rbp+secondaryText._hstring]
0x18059c853  lea     this, [rbp+focusedElement]; this
0x18059c857  mov     [rbp+focusedElement.ptr_], r12
0x18059c85b  mov     rax, [rdi]
0x18059c85e  mov     rbx, [rax+30h]
0x18059c862  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18059c867  lea     rdx, [rbp+focusedElement]
0x18059c86b  mov     this, rdi
0x18059c86e  mov     rax, rbx
0x18059c871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18059c876  mov     ebx, eax
0x18059c878  test    eax, eax
0x18059c87a  js      loc_18059C9EB
0x18059c880  mov     this, [rbp+focusedElement.ptr_]
0x18059c884  lea     rdx, [rbp+defaultButton]
0x18059c888  mov     dword ptr [rbp+defaultButton], r12d
0x18059c88c  mov     rax, [this]
0x18059c88f  mov     rax, [rax+30h]
0x18059c893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18059c898  mov     ebx, eax
0x18059c89a  test    eax, eax
0x18059c89c  js      loc_18059C9E2
0x18059c8a2  mov     eax, dword ptr [rbp+defaultButton]
0x18059c8a5  mov     r8, r12
0x18059c8a8  sub     eax, 1
0x18059c8ab  jz      short loc_18059C8C5
0x18059c8ad  sub     eax, 1
0x18059c8b0  jz      short loc_18059C8BC
0x18059c8b2  sub     eax, 2
0x18059c8b5  jz      short loc_18059C8C5
0x18059c8b7  cmp     eax, 4
0x18059c8ba  jnz     short loc_18059C8CC
0x18059c8bc  lea     r8, aPortrait; "Portrait"
0x18059c8c3  jmp     short loc_18059C8CC
0x18059c8c5  lea     r8, aLandscape; "Landscape"
0x18059c8cc  lea     r9, [rbp+isFocusInCommandArea]; pbReturnValue
0x18059c8d0  mov     [rbp+isFocusInCommandArea], r12b
0x18059c8d4  mov     useTransitions, r15b; bUseTransitions
0x18059c8d7  mov     this, rsi; this
0x18059c8da  call    ?GoToState@Control@DirectUI@@IEAAJ_NPEBGPEAE@Z; DirectUI::Control::GoToState(bool,ushort const *,uchar *)
0x18059c8df  mov     ebx, eax
0x18059c8e1  test    eax, eax
0x18059c8e3  js      loc_18059C9D9
0x18059c8e9  lea     this, [rbp+focusedElement]; this
0x18059c8ed  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18059c8f2  lea     this, [rbp+secondaryText]; this
0x18059c8f6  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18059c8fb  cmp     dword ptr [rsi+4D0h], 3
0x18059c902  jl      loc_18059CC4A
0x18059c908  mov     rax, [r14]
0x18059c90b  xor     ecx, ecx; string
0x18059c90d  mov     [rbp+defaultButton], r12
0x18059c911  mov     rbx, [rax+60h]
0x18059c915  call    cs:__imp_WindowsDeleteString
0x18059c91b  lea     rdx, [rbp+defaultButton]
0x18059c91f  mov     [rbp+defaultButton], r12
0x18059c923  mov     this, r14
0x18059c926  mov     rax, rbx
0x18059c929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18059c92e  mov     ebx, eax
0x18059c930  test    eax, eax
0x18059c932  js      loc_18059CC2B
0x18059c938  mov     rax, [r14]
0x18059c93b  xor     ecx, ecx; string
0x18059c93d  mov     [rbp+secondaryText._hstring], r12
0x18059c941  mov     rbx, [rax+70h]
0x18059c945  call    cs:__imp_WindowsDeleteString
0x18059c94b  lea     rdx, [rbp+secondaryText]
0x18059c94f  mov     [rbp+secondaryText._hstring], r12
0x18059c953  mov     this, r14
0x18059c956  mov     rax, rbx
0x18059c959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18059c95e  mov     ebx, eax
0x18059c960  test    eax, eax
0x18059c962  js      loc_18059CC0D
0x18059c968  lea     r14, [rsi+248h]
0x18059c96f  mov     [rbp+focusedElement.ptr_], r12
0x18059c973  mov     rax, [r14]
0x18059c976  xor     ecx, ecx; string
0x18059c978  mov     rbx, [rax+30h]
0x18059c97c  call    cs:__imp_WindowsDeleteString
0x18059c982  lea     rdx, [rbp+focusedElement]
0x18059c986  mov     [rbp+focusedElement.ptr_], r12
0x18059c98a  mov     this, r14
0x18059c98d  mov     rax, rbx
0x18059c990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18059c995  mov     ebx, eax
0x18059c997  test    eax, eax
0x18059c999  js      loc_18059CBFB
0x18059c99f  mov     this, [rbp+defaultButton]; string
0x18059c9a3  call    cs:__imp_WindowsIsStringEmpty
0x18059c9a9  mov     this, [rbp+secondaryText._hstring]; string
0x18059c9ad  mov     ebx, eax
0x18059c9af  call    cs:__imp_WindowsIsStringEmpty
0x18059c9b5  mov     this, [rbp+focusedElement.ptr_]; string
0x18059c9b9  mov     edi, eax
0x18059c9bb  call    cs:__imp_WindowsIsStringEmpty
0x18059c9c1  test    ebx, ebx
0x18059c9c3  jnz     short loc_18059CA28
0x18059c9c5  test    edi, edi
0x18059c9c7  jnz     short loc_18059CA12
0x18059c9c9  lea     r8, aAllvisible; "AllVisible"
0x18059c9d0  lea     this, aPrimaryandseco; "PrimaryAndSecondaryVisible"
0x18059c9d7  jmp     short loc_18059CA50
0x18059c9d9  mov     ecx, eax; failedFrameHR
0x18059c9db  call    OnFailure_2990_
0x18059c9e0  jmp     short loc_18059C9F2
0x18059c9e2  mov     ecx, eax; failedFrameHR
0x18059c9e4  call    OnFailure_2990_
0x18059c9e9  jmp     short loc_18059C9F2
0x18059c9eb  mov     ecx, eax; failedFrameHR
0x18059c9ed  call    OnFailure_2990_
0x18059c9f2  lea     this, [rbp+focusedElement]; this
0x18059c9f6  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18059c9fb  jmp     short loc_18059CA04
0x18059c9fd  mov     ecx, eax; failedFrameHR
0x18059c9ff  call    OnFailure_2990_
0x18059ca04  lea     this, [rbp+secondaryText]; this
0x18059ca08  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18059ca0d  jmp     loc_18059CD95
0x18059ca12  test    eax, eax
0x18059ca14  jnz     short loc_18059CA1F
0x18059ca16  lea     r8, aPrimaryandclos; "PrimaryAndCloseVisible"
0x18059ca1d  jmp     short loc_18059CA56
0x18059ca1f  lea     r8, aPrimaryvisible; "PrimaryVisible"
0x18059ca26  jmp     short loc_18059CA56
0x18059ca28  test    edi, edi
0x18059ca2a  jnz     short loc_18059CA42
0x18059ca2c  test    eax, eax
0x18059ca2e  jnz     short loc_18059CA39
0x18059ca30  lea     r8, aSecondaryandcl; "SecondaryAndCloseVisible"
0x18059ca37  jmp     short loc_18059CA56
0x18059ca39  lea     r8, aSecondaryvisib; "SecondaryVisible"
0x18059ca40  jmp     short loc_18059CA56
0x18059ca42  lea     r8, aClosevisible; "CloseVisible"
0x18059ca49  lea     this, aNonevisible; "NoneVisible"
0x18059ca50  test    eax, eax
0x18059ca52  cmovnz  r8, this; pszState
0x18059ca56  lea     r9, [rbp+isFocusInCommandArea]; pbReturnValue
0x18059ca5a  mov     [rbp+isFocusInCommandArea], r12b
0x18059ca5e  mov     useTransitions, r15b; bUseTransitions
0x18059ca61  mov     this, rsi; this
0x18059ca64  call    ?GoToState@Control@DirectUI@@IEAAJ_NPEBGPEAE@Z; DirectUI::Control::GoToState(bool,ushort const *,uchar *)
0x18059ca69  mov     ebx, eax
0x18059ca6b  test    eax, eax
0x18059ca6d  js      loc_18059CBF2
0x18059ca73  lea     this, [rbp+focusedElement]; this
0x18059ca77  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18059ca7c  lea     this, [rbp+secondaryText]; this
0x18059ca80  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18059ca85  lea     this, [rbp+defaultButton]; this
0x18059ca89  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18059ca8e  mov     rax, [r14]
0x18059ca91  lea     rdx, [rbp+defaultButton]
0x18059ca95  mov     this, r14
0x18059ca98  mov     dword ptr [rbp+defaultButton], r12d
0x18059ca9c  mov     rax, [rax+90h]
0x18059caa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18059caa8  mov     ebx, eax
0x18059caaa  test    eax, eax
0x18059caac  js      loc_18059CBE6
0x18059cab2  lea     r14, aNodefaultbutto; "NoDefaultButton"
0x18059cab9  cmp     dword ptr [rbp+defaultButton], r12d
0x18059cabd  jz      loc_18059CB9A
0x18059cac3  lea     this, [rbp+focusedElement]; this
0x18059cac7  mov     [rbp+focusedElement.ptr_], r12
0x18059cacb  call    ?InternalRelease@?$ComPtr@VStoryboard@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::Storyboard>::InternalRelease(void)
0x18059cad0  lea     rdx, [rbp+focusedElement]; ppFocusedElement
0x18059cad4  mov     this, rsi; this
0x18059cad7  call    ?GetFocusedElement@DependencyObject@DirectUI@@QEAAJPEAPEAV12@@Z; DirectUI::DependencyObject::GetFocusedElement(DirectUI::DependencyObject * *)
0x18059cadc  mov     edi, eax
0x18059cade  test    eax, eax
0x18059cae0  js      loc_18059CBCF
0x18059cae6  mov     rax, [rsi+2B8h]
0x18059caed  lea     r8, [rbp+isFocusInCommandArea]; pIsAncestor
0x18059caf1  mov     rbx, [rbp+focusedElement.ptr_]
0x18059caf5  mov     rdx, rbx; pElement
0x18059caf8  mov     [rbp+isFocusInCommandArea], r12b
0x18059cafc  lea     this, [rax-1F0h]
0x18059cb03  neg     rax
0x18059cb06  sbb     r9, r9
0x18059cb09  and     this, r9; this
0x18059cb0c  call    ?IsAncestorOf@DependencyObject@DirectUI@@QEAAJPEAV12@PEAE@Z; DirectUI::DependencyObject::IsAncestorOf(DirectUI::DependencyObject *,uchar *)
0x18059cb11  mov     edi, eax
0x18059cb13  test    eax, eax
0x18059cb15  js      loc_18059CBC6
0x18059cb1b  mov     eax, dword ptr [rbp+defaultButton]
0x18059cb1e  cmp     eax, 1
0x18059cb21  jnz     short loc_18059CB45
0x18059cb23  cmp     [rbp+isFocusInCommandArea], r12b
0x18059cb27  jz      short loc_18059CB3C
0x18059cb29  mov     this, [rsi+360h]; pFirst
0x18059cb30  mov     rdx, rbx; pSecond
0x18059cb33  call    ??$are_equal@UIButtonBase@Primitives@Controls@Xaml@UI@Windows@@VDependencyObject@DirectUI@@@ctl@@YA_NPEAUIButtonBase@Primitives@Controls@Xaml@UI@Windows@@PEAVDependencyObject@DirectUI@@@Z; ctl::are_equal<Windows::UI::Xaml::Controls::Primitives::IButtonBase,DirectUI::DependencyObject>(Windows::UI::Xaml::Controls::Primitives::IButtonBase *,DirectUI::DependencyObject *)
0x18059cb38  test    al, al
0x18059cb3a  jz      short loc_18059CB91
0x18059cb3c  lea     r14, aPrimaryasdefau; "PrimaryAsDefaultButton"
0x18059cb43  jmp     short loc_18059CB91
0x18059cb45  cmp     eax, 2
0x18059cb48  jnz     short loc_18059CB6C
0x18059cb4a  cmp     [rbp+isFocusInCommandArea], r12b
0x18059cb4e  jz      short loc_18059CB63
0x18059cb50  mov     this, [rsi+390h]; pFirst
0x18059cb57  mov     rdx, rbx; pSecond
0x18059cb5a  call    ??$are_equal@UIButtonBase@Primitives@Controls@Xaml@UI@Windows@@VDependencyObject@DirectUI@@@ctl@@YA_NPEAUIButtonBase@Primitives@Controls@Xaml@UI@Windows@@PEAVDependencyObject@DirectUI@@@Z; ctl::are_equal<Windows::UI::Xaml::Controls::Primitives::IButtonBase,DirectUI::DependencyObject>(Windows::UI::Xaml::Controls::Primitives::IButtonBase *,DirectUI::DependencyObject *)
0x18059cb5f  test    al, al
0x18059cb61  jz      short loc_18059CB91
0x18059cb63  lea     r14, aSecondaryasdef; "SecondaryAsDefaultButton"
0x18059cb6a  jmp     short loc_18059CB91
0x18059cb6c  cmp     eax, 3
0x18059cb6f  jnz     short loc_18059CB91
0x18059cb71  cmp     [rbp+isFocusInCommandArea], r12b
0x18059cb75  jz      short loc_18059CB8A
0x18059cb77  mov     this, [rsi+2A0h]; pFirst
0x18059cb7e  mov     rdx, rbx; pSecond
0x18059cb81  call    ??$are_equal@UIButtonBase@Primitives@Controls@Xaml@UI@Windows@@VDependencyObject@DirectUI@@@ctl@@YA_NPEAUIButtonBase@Primitives@Controls@Xaml@UI@Windows@@PEAVDependencyObject@DirectUI@@@Z; ctl::are_equal<Windows::UI::Xaml::Controls::Primitives::IButtonBase,DirectUI::DependencyObject>(Windows::UI::Xaml::Controls::Primitives::IButtonBase *,DirectUI::DependencyObject *)
0x18059cb86  test    al, al
0x18059cb88  jz      short loc_18059CB91
0x18059cb8a  lea     r14, aCloseasdefault; "CloseAsDefaultButton"
0x18059cb91  lea     this, [rbp+focusedElement]; this
0x18059cb95  call    ?InternalRelease@?$ComPtr@VStoryboard@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::Storyboard>::InternalRelease(void)
0x18059cb9a  lea     r9, [rbp+ignored]; pbReturnValue
0x18059cb9e  mov     [rbp+ignored], r12b
0x18059cba2  mov     r8, r14; pszState
0x18059cba5  mov     useTransitions, r15b; bUseTransitions
0x18059cba8  mov     this, rsi; this
0x18059cbab  call    ?GoToState@Control@DirectUI@@IEAAJ_NPEBGPEAE@Z; DirectUI::Control::GoToState(bool,ushort const *,uchar *)
0x18059cbb0  mov     ebx, eax
0x18059cbb2  test    eax, eax
0x18059cbb4  jns     loc_18059CC4A
0x18059cbba  mov     ecx, eax; failedFrameHR
0x18059cbbc  call    OnFailure_2990_
0x18059cbc1  jmp     loc_18059CD95
0x18059cbc6  mov     ecx, eax; failedFrameHR
0x18059cbc8  call    OnFailure_2990_
0x18059cbcd  jmp     short loc_18059CBD6
0x18059cbcf  mov     ecx, eax; failedFrameHR
0x18059cbd1  call    OnFailure_2990_
0x18059cbd6  lea     this, [rbp+focusedElement]; this
0x18059cbda  call    ?InternalRelease@?$ComPtr@VStoryboard@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::Storyboard>::InternalRelease(void)
0x18059cbdf  mov     eax, edi
0x18059cbe1  jmp     loc_18059CD97
0x18059cbe6  mov     ecx, ebx; failedFrameHR
0x18059cbe8  call    OnFailure_2990_
0x18059cbed  jmp     loc_18059CD95
0x18059cbf2  mov     ecx, eax; failedFrameHR
0x18059cbf4  call    OnFailure_2990_
0x18059cbf9  jmp     short loc_18059CC02
0x18059cbfb  mov     ecx, eax; failedFrameHR
0x18059cbfd  call    OnFailure_2990_
0x18059cc02  lea     this, [rbp+focusedElement]; this
0x18059cc06  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18059cc0b  jmp     short loc_18059CC14
0x18059cc0d  mov     ecx, eax; failedFrameHR
0x18059cc0f  call    OnFailure_2990_
0x18059cc14  lea     this, [rbp+secondaryText]; this
0x18059cc18  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18059cc1d  lea     this, [rbp+defaultButton]; this
0x18059cc21  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
  ... truncated ...
```
