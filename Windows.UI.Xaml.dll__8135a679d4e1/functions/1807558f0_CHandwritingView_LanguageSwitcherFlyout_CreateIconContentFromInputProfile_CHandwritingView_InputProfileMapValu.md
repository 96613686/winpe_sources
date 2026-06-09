# CHandwritingView::LanguageSwitcherFlyout::CreateIconContentFromInputProfile(CHandwritingView::InputProfileMapValue const &,uint,CUIElement * *,bool &)

- ea: `0x1807558f0`
- end: `0x180755d5f`
- name: `?CreateIconContentFromInputProfile@LanguageSwitcherFlyout@CHandwritingView@@QEAAJAEBUInputProfileMapValue@2@IPEAPEAVCUIElement@@AEA_N@Z`
- size: `1135`
- prototype: `HRESULT __fastcall(CHandwritingView::LanguageSwitcherFlyout *this, const CHandwritingView::InputProfileMapValue *inputProfileData, unsigned int iconSize, CUIElement **ppResult, bool *isIcon)`
- caller_count: `2`
- callee_count: `24`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1808222c8`
- `0x180824bd8`

## callees

- `0x180004bc0`
- `0x18000b6c0`
- `0x18001a464`
- `0x18001f3c0`
- `0x180021970`
- `0x18004486c`
- `0x180045d64`
- `0x18006cfd0`
- `0x1800f85d0`
- `0x1800fe130`
- `0x180108820`
- `0x1801f1cd8`
- `0x180202ac4`
- `0x1802eb450`
- `0x180343084`
- `0x180532530`
- `0x180583d7c`
- `0x180688828`
- `0x1807558f0`
- `0x180755d68`
- `0x18076e110`
- `0x18081a3c0`
- `0x18081e1f8`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18075594e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180755c41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180755d2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18075594e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180755c41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180755d2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180755998`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180755ae9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180755998`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180755ae9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180755980`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180755980`
- `ext-ms-win-shell-shell32-l1-2-1!SHDefExtractIconW` at `0x1807559e2`
- `ext-ms-win-shell-shell32-l1-2-1!SHDefExtractIconW` at `0x1807559e2`

## pseudocode

```c
__int64 __fastcall CHandwritingView::LanguageSwitcherFlyout::CreateIconContentFromInputProfile(
        CHandwritingView::LanguageSwitcherFlyout *this,
        const CHandwritingView::InputProfileMapValue *inputProfileData,
        UINT iconSize,
        CFontIcon **ppResult,
        bool *isIcon)
{
  Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfile *ptr; // rdi
  HRESULT (__fastcall *get_IconFile)(Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfile *, HSTRING__ **); // rbx
  HRESULT v11; // eax
  unsigned int v12; // ebx
  PCWSTR StringRawBuffer; // rax
  Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfile *v14; // r8
  const WCHAR *v15; // rdi
  HRESULT v16; // eax
  CFontIcon *m_ptr; // rbx
  HRESULT BitmapImageFromHICON; // eax
  Flyweight::ValueObjectWrapper<CDOSharedState> *v19; // rax
  HRESULT v20; // eax
  HSTRING__ *hstr; // rcx
  const wchar_t *v22; // rax
  HRESULT HandwritingView; // eax
  HRESULT v24; // edi
  HRESULT v25; // ecx
  Flyweight::ValueObjectWrapper<CDOSharedState> *v26; // rax
  HRESULT v27; // eax
  HRESULT v28; // ecx
  CVisualState *v29; // rdx
  HRESULT v30; // eax
  xref_ptr<CFontIcon> pAbbreviationIcon; // [rsp+30h] [rbp-91h] BYREF
  xref_ptr<CUIElement> itemInLeftColumn; // [rsp+38h] [rbp-89h] BYREF
  CDependencyObject *pFontFamily; // [rsp+40h] [rbp-81h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (__cdecl*)(HICON__ *),&DestroyIcon,wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t> > > icon; // [rsp+48h] [rbp-79h] BYREF
  Microsoft::WRL::Wrappers::HString iconFile; // [rsp+50h] [rbp-71h] BYREF
  unsigned int iconIndex; // [rsp+58h] [rbp-69h] BYREF
  xstring_ptr fontIconFont; // [rsp+60h] [rbp-61h] BYREF
  CREATEPARAMETERS cp; // [rsp+68h] [rbp-59h] BYREF
  CValue value; // [rsp+90h] [rbp-31h] BYREF
  CREATEPARAMETERS fontCP; // [rsp+A0h] [rbp-21h] BYREF

  if ( ppResult )
  {
    *ppResult = 0;
    ptr = inputProfileData->m_pCoreKeyboardInputProfile.ptr_;
    iconFile.hstr_ = 0;
    get_IconFile = ptr->get_IconFile;
    WindowsDeleteString(0);
    iconFile.hstr_ = 0;
    v11 = get_IconFile(ptr, &iconFile.hstr_);
    v12 = v11;
    if ( v11 < 0 )
    {
      OnFailure_2990_(v11);
      goto LABEL_34;
    }
    itemInLeftColumn.m_ptr = 0;
    if ( WindowsIsStringEmpty(iconFile.hstr_) )
      goto LABEL_15;
    icon.m_ptr = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(iconFile.hstr_, 0);
    v14 = inputProfileData->m_pCoreKeyboardInputProfile.ptr_;
    iconIndex = 0;
    v15 = StringRawBuffer;
    v16 = v14->get_IconIndex(v14, &iconIndex);
    v12 = v16;
    if ( v16 < 0 )
    {
      OnFailure_2990_(v16);
    }
    else
    {
      SHDefExtractIconW(v15, iconIndex, 0, &icon.m_ptr, 0, iconSize);
      if ( !icon.m_ptr )
      {
        m_ptr = 0;
        goto LABEL_9;
      }
      pAbbreviationIcon.m_ptr = 0;
      xref_ptr<CTranslateTransform>::DecrementRefCount((xref_ptr<CPointKeyFrameCollection> *)&pAbbreviationIcon);
      pFontFamily = (CDependencyObject *)icon.m_ptr;
      icon.m_ptr = 0;
      BitmapImageFromHICON = CHandwritingView::LanguageSwitcherFlyout::CreateBitmapImageFromHICON(
                               this,
                               (wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (__cdecl*)(HICON__ *),&DestroyIcon,wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t> > >)&pFontFamily,
                               (CImage **)&pAbbreviationIcon);
      v12 = BitmapImageFromHICON;
      if ( BitmapImageFromHICON >= 0 )
      {
        m_ptr = pAbbreviationIcon.m_ptr;
        itemInLeftColumn.m_ptr = pAbbreviationIcon.m_ptr;
        xref_ptr<CSolidColorBrush>::IncrementRefCount((xref_ptr<CSetter> *)&itemInLeftColumn);
        *isIcon = 0;
        xref_ptr<CTranslateTransform>::DecrementRefCount((xref_ptr<CPointKeyFrameCollection> *)&pAbbreviationIcon);
LABEL_9:
        wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&int DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&int DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>(&icon);
        if ( m_ptr )
          goto LABEL_23;
LABEL_15:
        v19 = this->m_sharedState.m_ptr;
        pAbbreviationIcon.m_ptr = 0;
        cp.m_value.m_value = 0;
        cp.m_value.m_flags = 0;
        cp.m_pCore = v19->m_value.m_coreServices;
        cp.m_spServiceProviderContext = 0;
        xref_ptr<CTranslateTransform>::DecrementRefCount((xref_ptr<CPointKeyFrameCollection> *)&pAbbreviationIcon);
        v20 = CFontIcon::Create(&pAbbreviationIcon.m_ptr, &cp);
        v12 = v20;
        if ( v20 >= 0 )
        {
          hstr = inputProfileData->abbreviation.hstr_;
          value = 0;
          v22 = WindowsGetStringRawBuffer(hstr, 0);
          Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)&fontCP, v22);
          CValue::SetString(&value, *(HSTRING__ **)&fontCP.m_value.m_value);
          m_ptr = pAbbreviationIcon.m_ptr;
          HandwritingView = CDependencyObject::SetValueByKnownIndex(pAbbreviationIcon.m_ptr, FontIcon_Glyph, &value);
          v24 = HandwritingView;
          if ( HandwritingView < 0
            || (pFontFamily = 0,
                HandwritingView = CHandwritingView::GetHandwritingView(this, (CHandwritingView **)&pFontFamily),
                v24 = HandwritingView,
                HandwritingView < 0) )
          {
            OnFailure_2990_(HandwritingView);
            goto LABEL_31;
          }
          if ( pFontFamily )
          {
            v26 = this->m_sharedState.m_ptr;
            fontCP.m_value.m_value = 0;
            fontCP.m_value.m_flags = 0;
            fontCP.m_spServiceProviderContext = 0;
            fontCP.m_pCore = v26->m_value.m_coreServices;
            fontIconFont.m_encodedStorage.Storage = &c_strLanguageSwitcherFontIconFontStorage;
            CValue::SetString(&fontCP.m_value, &fontIconFont);
            pFontFamily = 0;
            v27 = CFontFamily::Create(&pFontFamily, &fontCP);
            v24 = v27;
            if ( v27 < 0 )
            {
              OnFailure_2990_(v27);
LABEL_27:
              xstring_ptr::~xstring_ptr(&fontIconFont);
              CREATEPARAMETERS::~CREATEPARAMETERS(&fontCP);
LABEL_31:
              CValue::ReleaseAndReset(&value);
              CREATEPARAMETERS::~CREATEPARAMETERS(&cp);
              xref_ptr<CTranslateTransform>::DecrementRefCount((xref_ptr<CPointKeyFrameCollection> *)&pAbbreviationIcon);
              xref_ptr<CUIElement>::~xref_ptr<CUIElement>((xref_ptr<CBinding> *)&itemInLeftColumn);
              v12 = v24;
              goto LABEL_34;
            }
            v29 = (CVisualState *)pFontFamily;
            if ( pFontFamily )
            {
              pFontFamily = 0;
              xref_ptr<CMediaPlayerPresenter>::attach<CMediaPlayerPresenter>(
                (xref_ptr<CVisualState> *)&pFontFamily,
                v29);
              v30 = CDependencyObject::SetValueByKnownIndex(m_ptr, FontIcon_FontFamily, pFontFamily);
              v24 = v30;
              if ( v30 >= 0 )
              {
                itemInLeftColumn.m_ptr = m_ptr;
                xref_ptr<CSolidColorBrush>::IncrementRefCount((xref_ptr<CSetter> *)&itemInLeftColumn);
                *isIcon = 1;
                xref_ptr<CDependencyObject>::DecrementRefCount((xref_ptr<CDependencyObject> *)&pFontFamily);
                xstring_ptr::~xstring_ptr(&fontIconFont);
                CREATEPARAMETERS::~CREATEPARAMETERS(&fontCP);
                CValue::ReleaseAndReset(&value);
                CREATEPARAMETERS::~CREATEPARAMETERS(&cp);
                xref_ptr<CTranslateTransform>::DecrementRefCount((xref_ptr<CPointKeyFrameCollection> *)&pAbbreviationIcon);
LABEL_23:
                *ppResult = m_ptr;
                CDependencyObject::AddRef(m_ptr);
                xref_ptr<CUIElement>::~xref_ptr<CUIElement>((xref_ptr<CBinding> *)&itemInLeftColumn);
                WindowsDeleteString(iconFile.hstr_);
                return 0;
              }
              OnFailure_2990_(v30);
              xref_ptr<CDependencyObject>::DecrementRefCount((xref_ptr<CDependencyObject> *)&pFontFamily);
              goto LABEL_27;
            }
            OnNewFailure_1172_(v28);
            xstring_ptr::~xstring_ptr(&fontIconFont);
            CREATEPARAMETERS::~CREATEPARAMETERS(&fontCP);
          }
          else
          {
            OnNewFailure_1172_(v25);
          }
          CValue::ReleaseAndReset(&value);
          CREATEPARAMETERS::~CREATEPARAMETERS(&cp);
          xref_ptr<CTranslateTransform>::DecrementRefCount((xref_ptr<CPointKeyFrameCollection> *)&pAbbreviationIcon);
          xref_ptr<CUIElement>::~xref_ptr<CUIElement>((xref_ptr<CBinding> *)&itemInLeftColumn);
          v12 = -2147467261;
LABEL_34:
          WindowsDeleteString(iconFile.hstr_);
          return v12;
        }
        OnFailure_2990_(v20);
        CREATEPARAMETERS::~CREATEPARAMETERS(&cp);
        xref_ptr<CTranslateTransform>::DecrementRefCount((xref_ptr<CPointKeyFrameCollection> *)&pAbbreviationIcon);
LABEL_14:
        xref_ptr<CUIElement>::~xref_ptr<CUIElement>((xref_ptr<CBinding> *)&itemInLeftColumn);
        goto LABEL_34;
      }
      OnFailure_2990_(BitmapImageFromHICON);
      xref_ptr<CTranslateTransform>::DecrementRefCount((xref_ptr<CPointKeyFrameCollection> *)&pAbbreviationIcon);
    }
    wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&int DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&int DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>(&icon);
    goto LABEL_14;
  }
  OnNewFailure_1172_((HRESULT)this);
  return 2147500035LL;
}

```

## disassembly

```asm
0x1807558f0  push    rbp
0x1807558f2  push    rbx
0x1807558f3  push    rsi
0x1807558f4  push    rdi
0x1807558f5  push    r12
0x1807558f7  push    r13
0x1807558f9  push    r14
0x1807558fb  push    r15
0x1807558fd  lea     rbp, [rsp-17h]
0x180755902  sub     rsp, 0D8h
0x180755909  mov     rax, cs:__security_cookie
0x180755910  xor     rax, rsp
0x180755913  mov     [rbp+4Fh+var_48], rax
0x180755917  mov     r13, [rbp+4Fh+arg_20]
0x18075591b  mov     r14, ppResult
0x18075591e  mov     r15d, iconSize
0x180755921  mov     r12, inputProfileData
0x180755924  mov     rsi, this
0x180755927  test    ppResult, ppResult
0x18075592a  jz      loc_180755D35
0x180755930  mov     qword ptr [ppResult], 0
0x180755937  xor     ecx, ecx; string
0x180755939  mov     rdi, [inputProfileData]
0x18075593c  mov     [rbp+4Fh+iconFile.hstr_], 0
0x180755944  mov     rax, [rdi]
0x180755947  mov     rbx, [rax+90h]
0x18075594e  call    cs:__imp_WindowsDeleteString
0x180755954  lea     inputProfileData, [rbp+4Fh+iconFile]
0x180755958  mov     [rbp+4Fh+iconFile.hstr_], 0
0x180755960  mov     this, rdi
0x180755963  mov     rax, rbx
0x180755966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18075596b  mov     ebx, eax
0x18075596d  test    eax, eax
0x18075596f  js      loc_180755D20
0x180755975  mov     this, [rbp+4Fh+iconFile.hstr_]; string
0x180755979  xor     ebx, ebx
0x18075597b  mov     [rsp+110h+itemInLeftColumn.m_ptr], rbx
0x180755980  call    cs:__imp_WindowsIsStringEmpty
0x180755986  test    eax, eax
0x180755988  jnz     loc_180755A8E
0x18075598e  mov     this, [rbp+4Fh+iconFile.hstr_]; string
0x180755992  xor     edx, edx; length
0x180755994  mov     [rbp+4Fh+icon.m_ptr], rbx
0x180755998  call    cs:__imp_WindowsGetStringRawBuffer
0x18075599e  mov     r8, [r12]
0x1807559a2  lea     inputProfileData, [rbp+4Fh+iconIndex]
0x1807559a6  mov     [rbp+4Fh+iconIndex], ebx
0x1807559a9  mov     rdi, rax
0x1807559ac  mov     this, [r8]
0x1807559af  mov     rax, [this+98h]
0x1807559b6  mov     this, r8
0x1807559b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1807559be  mov     ebx, eax
0x1807559c0  test    eax, eax
0x1807559c2  js      loc_180755A6F
0x1807559c8  mov     edx, [rbp+4Fh+iconIndex]; iIndex
0x1807559cb  lea     ppResult, [rbp+4Fh+icon]; phiconLarge
0x1807559cf  mov     [rsp+110h+nIconSize], r15d; nIconSize
0x1807559d4  xor     iconSize, iconSize; uFlags
0x1807559d7  xor     r15d, r15d
0x1807559da  mov     this, rdi; pszIconFile
0x1807559dd  mov     [rsp+110h+phiconSmall], r15; phiconSmall
0x1807559e2  call    cs:__imp_SHDefExtractIconW
0x1807559e8  cmp     [rbp+4Fh+icon.m_ptr], r15
0x1807559ec  jnz     short loc_1807559F3
0x1807559ee  mov     ebx, r15d
0x1807559f1  jmp     short loc_180755A49
0x1807559f3  lea     this, [rsp+110h+pAbbreviationIcon]; this
0x1807559f8  mov     [rsp+110h+pAbbreviationIcon.m_ptr], r15
0x1807559fd  call    ?DecrementRefCount@?$xref_ptr@VCTranslateTransform@@@@AEAAXXZ; xref_ptr<CTranslateTransform>::DecrementRefCount(void)
0x180755a02  mov     rax, [rbp+4Fh+icon.m_ptr]
0x180755a06  lea     r8, [rsp+110h+pAbbreviationIcon]; ppResult
0x180755a0b  lea     inputProfileData, [rsp+110h+pFontFamily]; hIcon
0x180755a10  mov     [rsp+110h+pFontFamily], rax
0x180755a15  mov     this, rsi; this
0x180755a18  mov     [rbp+4Fh+icon.m_ptr], r15
0x180755a1c  call    ?CreateBitmapImageFromHICON@LanguageSwitcherFlyout@CHandwritingView@@AEAAJV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHICON__@@P6AHPEAU1@@Z$1?DestroyIcon@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAPEAVCImage@@@Z; CHandwritingView::LanguageSwitcherFlyout::CreateBitmapImageFromHICON(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>>,CImage * *)
0x180755a21  mov     ebx, eax
0x180755a23  test    eax, eax
0x180755a25  js      short loc_180755A5C
0x180755a27  mov     rbx, [rsp+110h+pAbbreviationIcon.m_ptr]
0x180755a2c  lea     this, [rsp+110h+itemInLeftColumn]; this
0x180755a31  mov     [rsp+110h+itemInLeftColumn.m_ptr], rbx
0x180755a36  call    ?IncrementRefCount@?$xref_ptr@VCSolidColorBrush@@@@AEAAXXZ; xref_ptr<CSolidColorBrush>::IncrementRefCount(void)
0x180755a3b  lea     this, [rsp+110h+pAbbreviationIcon]; this
0x180755a40  mov     [r13+0], r15b
0x180755a44  call    ?DecrementRefCount@?$xref_ptr@VCTranslateTransform@@@@AEAAXXZ; xref_ptr<CTranslateTransform>::DecrementRefCount(void)
0x180755a49  lea     this, [rbp+4Fh+icon]; this
0x180755a4d  call    ??1?$unique_storage@U?$resource_policy@PEAUHICON__@@P6AHPEAU1@@Z$1?DestroyIcon@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>(void)
0x180755a52  test    rbx, rbx
0x180755a55  jz      short loc_180755A91
0x180755a57  jmp     loc_180755C28
0x180755a5c  mov     ecx, eax; failedFrameHR
0x180755a5e  call    OnFailure_2990_
0x180755a63  lea     this, [rsp+110h+pAbbreviationIcon]; this
0x180755a68  call    ?DecrementRefCount@?$xref_ptr@VCTranslateTransform@@@@AEAAXXZ; xref_ptr<CTranslateTransform>::DecrementRefCount(void)
0x180755a6d  jmp     short loc_180755A76
0x180755a6f  mov     ecx, eax; failedFrameHR
0x180755a71  call    OnFailure_2990_
0x180755a76  lea     this, [rbp+4Fh+icon]; this
0x180755a7a  call    ??1?$unique_storage@U?$resource_policy@PEAUHICON__@@P6AHPEAU1@@Z$1?DestroyIcon@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>(void)
0x180755a7f  lea     this, [rsp+110h+itemInLeftColumn]; this
0x180755a84  call    ??1?$xref_ptr@VCUIElement@@@@QEAA@XZ; xref_ptr<CUIElement>::~xref_ptr<CUIElement>(void)
0x180755a89  jmp     loc_180755D27
0x180755a8e  xor     r15d, r15d
0x180755a91  mov     rax, [rsi+10h]
0x180755a95  lea     this, [rsp+110h+pAbbreviationIcon]; this
0x180755a9a  xorps   xmm0, xmm0
0x180755a9d  mov     [rsp+110h+pAbbreviationIcon.m_ptr], r15
0x180755aa2  mov     qword ptr [rbp+4Fh+cp.m_value.m_value], 0
0x180755aaa  mov     qword ptr [rbp+4Fh+cp.m_value.m_flags], 0
0x180755ab2  mov     inputProfileData, [rax]
0x180755ab5  mov     [rbp+4Fh+cp.m_pCore], inputProfileData
0x180755ab9  movdqu  xmmword ptr [rbp+4Fh+cp.m_spServiceProviderContext._Ptr], xmm0
0x180755abe  call    ?DecrementRefCount@?$xref_ptr@VCTranslateTransform@@@@AEAAXXZ; xref_ptr<CTranslateTransform>::DecrementRefCount(void)
0x180755ac3  lea     inputProfileData, [rbp+4Fh+cp]; pCreate
0x180755ac7  lea     this, [rsp+110h+pAbbreviationIcon]; ppObject
0x180755acc  call    ?Create@CFontIcon@@SAJPEAPEAVCDependencyObject@@PEAVCREATEPARAMETERS@@@Z; CFontIcon::Create(CDependencyObject * *,CREATEPARAMETERS *)
0x180755ad1  mov     ebx, eax
0x180755ad3  test    eax, eax
0x180755ad5  js      loc_180755D01
0x180755adb  mov     this, [r12+8]; string
0x180755ae0  xorps   xmm0, xmm0
0x180755ae3  xor     edx, edx; length
0x180755ae5  movups  xmmword ptr [rbp+4Fh+value.m_value], xmm0
0x180755ae9  call    cs:__imp_WindowsGetStringRawBuffer
0x180755aef  mov     inputProfileData, rax; stringRef
0x180755af2  lea     this, [rbp+4Fh+fontCP]; this
0x180755af6  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180755afb  mov     inputProfileData, qword ptr [rbp+4Fh+fontCP.m_value.m_value]; value
0x180755aff  lea     this, [rbp+4Fh+value]; this
0x180755b03  call    ?SetString@CValue@@QEAAJPEAUHSTRING__@@@Z; CValue::SetString(HSTRING__ *)
0x180755b08  mov     rbx, [rsp+110h+pAbbreviationIcon.m_ptr]
0x180755b0d  lea     r8, [rbp+4Fh+value]; value
0x180755b11  mov     this, rbx; this
0x180755b14  mov     edx, 563h; index
0x180755b19  call    ?SetValueByKnownIndex@CDependencyObject@@QEAAJW4KnownPropertyIndex@@AEBVCValue@@@Z; CDependencyObject::SetValueByKnownIndex(KnownPropertyIndex,CValue const &)
0x180755b1e  mov     edi, eax
0x180755b20  test    eax, eax
0x180755b22  js      loc_180755CD0
0x180755b28  lea     inputProfileData, [rsp+110h+pFontFamily]; ppHandwritingView
0x180755b2d  mov     [rsp+110h+pFontFamily], r15
0x180755b32  mov     this, rsi; pSender
0x180755b35  call    ?GetHandwritingView@CHandwritingView@@SAJPEAVCDependencyObject@@PEAPEAV1@@Z; CHandwritingView::GetHandwritingView(CDependencyObject *,CHandwritingView * *)
0x180755b3a  mov     edi, eax
0x180755b3c  test    eax, eax
0x180755b3e  js      loc_180755CC7
0x180755b44  cmp     [rsp+110h+pFontFamily], r15
0x180755b49  jz      loc_180755C95
0x180755b4f  mov     rax, [rsi+10h]
0x180755b53  lea     inputProfileData, [rbp+4Fh+fontIconFont]; value
0x180755b57  xorps   xmm0, xmm0
0x180755b5a  mov     qword ptr [rbp+4Fh+fontCP.m_value.m_value], 0
0x180755b62  mov     qword ptr [rbp+4Fh+fontCP.m_value.m_flags], 0
0x180755b6a  movdqu  xmmword ptr [rbp+4Fh+fontCP.m_spServiceProviderContext._Ptr], xmm0
0x180755b6f  mov     this, [rax]
0x180755b72  lea     rax, c_strLanguageSwitcherFontIconFontStorage
0x180755b79  mov     [rbp+4Fh+fontCP.m_pCore], this
0x180755b7d  lea     this, [rbp+4Fh+fontCP]; this
0x180755b81  mov     qword ptr [rbp+4Fh+fontIconFont.m_encodedStorage.___u0], rax
0x180755b85  call    ?SetString@CValue@@QEAAXAEBVxstring_ptr@@@Z; CValue::SetString(xstring_ptr const &)
0x180755b8a  lea     inputProfileData, [rbp+4Fh+fontCP]; pCreate
0x180755b8e  mov     [rsp+110h+pFontFamily], r15
0x180755b93  lea     this, [rsp+110h+pFontFamily]; ppObject
0x180755b98  call    ?Create@CFontFamily@@SAJPEAPEAVCDependencyObject@@PEAVCREATEPARAMETERS@@@Z; CFontFamily::Create(CDependencyObject * *,CREATEPARAMETERS *)
0x180755b9d  mov     edi, eax
0x180755b9f  test    eax, eax
0x180755ba1  js      loc_180755C7A
0x180755ba7  mov     inputProfileData, [rsp+110h+pFontFamily]; ptr
0x180755bac  test    inputProfileData, inputProfileData
0x180755baf  jz      loc_180755C61
0x180755bb5  lea     this, [rsp+110h+pFontFamily]; this
0x180755bba  mov     [rsp+110h+pFontFamily], r15
0x180755bbf  call    ??$attach@VCMediaPlayerPresenter@@@?$xref_ptr@VCMediaPlayerPresenter@@@@QEAAXPEAVCMediaPlayerPresenter@@@Z; xref_ptr<CMediaPlayerPresenter>::attach<CMediaPlayerPresenter>(CMediaPlayerPresenter *)
0x180755bc4  mov     r8, [rsp+110h+pFontFamily]; value
0x180755bc9  mov     edx, 55Fh; index
0x180755bce  mov     this, rbx; this
0x180755bd1  call    ?SetValueByKnownIndex@CDependencyObject@@QEAAJW4KnownPropertyIndex@@PEAV1@@Z; CDependencyObject::SetValueByKnownIndex(KnownPropertyIndex,CDependencyObject *)
0x180755bd6  mov     edi, eax
0x180755bd8  test    eax, eax
0x180755bda  js      short loc_180755C4E
0x180755bdc  lea     this, [rsp+110h+itemInLeftColumn]; this
0x180755be1  mov     [rsp+110h+itemInLeftColumn.m_ptr], rbx
0x180755be6  call    ?IncrementRefCount@?$xref_ptr@VCSolidColorBrush@@@@AEAAXXZ; xref_ptr<CSolidColorBrush>::IncrementRefCount(void)
0x180755beb  lea     this, [rsp+110h+pFontFamily]; this
0x180755bf0  mov     byte ptr [r13+0], 1
0x180755bf5  call    ?DecrementRefCount@?$xref_ptr@VCDependencyObject@@@@AEAAXXZ; xref_ptr<CDependencyObject>::DecrementRefCount(void)
0x180755bfa  lea     this, [rbp+4Fh+fontIconFont]; this
0x180755bfe  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x180755c03  lea     this, [rbp+4Fh+fontCP]; this
0x180755c07  call    ??1CREATEPARAMETERS@@QEAA@XZ; CREATEPARAMETERS::~CREATEPARAMETERS(void)
0x180755c0c  lea     this, [rbp+4Fh+value]; this
0x180755c10  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x180755c15  lea     this, [rbp+4Fh+cp]; this
0x180755c19  call    ??1CREATEPARAMETERS@@QEAA@XZ; CREATEPARAMETERS::~CREATEPARAMETERS(void)
0x180755c1e  lea     this, [rsp+110h+pAbbreviationIcon]; this
0x180755c23  call    ?DecrementRefCount@?$xref_ptr@VCTranslateTransform@@@@AEAAXXZ; xref_ptr<CTranslateTransform>::DecrementRefCount(void)
0x180755c28  mov     this, rbx; this
0x180755c2b  mov     [r14], rbx
0x180755c2e  call    ?AddRef@CDependencyObject@@QEAAXXZ; CDependencyObject::AddRef(void)
0x180755c33  lea     this, [rsp+110h+itemInLeftColumn]; this
0x180755c38  call    ??1?$xref_ptr@VCUIElement@@@@QEAA@XZ; xref_ptr<CUIElement>::~xref_ptr<CUIElement>(void)
0x180755c3d  mov     this, [rbp+4Fh+iconFile.hstr_]; string
0x180755c41  call    cs:__imp_WindowsDeleteString
0x180755c47  xor     eax, eax
0x180755c49  jmp     loc_180755D3F
0x180755c4e  mov     ecx, edi; failedFrameHR
0x180755c50  call    OnFailure_2990_
0x180755c55  lea     this, [rsp+110h+pFontFamily]; this
0x180755c5a  call    ?DecrementRefCount@?$xref_ptr@VCDependencyObject@@@@AEAAXXZ; xref_ptr<CDependencyObject>::DecrementRefCount(void)
0x180755c5f  jmp     short loc_180755C81
0x180755c61  call    OnNewFailure_1172_
0x180755c66  lea     this, [rbp+4Fh+fontIconFont]; this
0x180755c6a  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x180755c6f  lea     this, [rbp+4Fh+fontCP]; this
0x180755c73  call    ??1CREATEPARAMETERS@@QEAA@XZ; CREATEPARAMETERS::~CREATEPARAMETERS(void)
0x180755c78  jmp     short loc_180755C9A
0x180755c7a  mov     ecx, edi; failedFrameHR
0x180755c7c  call    OnFailure_2990_
0x180755c81  lea     this, [rbp+4Fh+fontIconFont]; this
0x180755c85  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x180755c8a  lea     this, [rbp+4Fh+fontCP]; this
0x180755c8e  call    ??1CREATEPARAMETERS@@QEAA@XZ; CREATEPARAMETERS::~CREATEPARAMETERS(void)
0x180755c93  jmp     short loc_180755CD7
0x180755c95  call    OnNewFailure_1172_
0x180755c9a  lea     this, [rbp+4Fh+value]; this
0x180755c9e  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x180755ca3  lea     this, [rbp+4Fh+cp]; this
0x180755ca7  call    ??1CREATEPARAMETERS@@QEAA@XZ; CREATEPARAMETERS::~CREATEPARAMETERS(void)
0x180755cac  lea     this, [rsp+110h+pAbbreviationIcon]; this
0x180755cb1  call    ?DecrementRefCount@?$xref_ptr@VCTranslateTransform@@@@AEAAXXZ; xref_ptr<CTranslateTransform>::DecrementRefCount(void)
0x180755cb6  lea     this, [rsp+110h+itemInLeftColumn]; this
0x180755cbb  call    ??1?$xref_ptr@VCUIElement@@@@QEAA@XZ; xref_ptr<CUIElement>::~xref_ptr<CUIElement>(void)
0x180755cc0  mov     ebx, 80004003h
0x180755cc5  jmp     short loc_180755D27
0x180755cc7  mov     ecx, edi; failedFrameHR
0x180755cc9  call    OnFailure_2990_
0x180755cce  jmp     short loc_180755CD7
0x180755cd0  mov     ecx, edi; failedFrameHR
0x180755cd2  call    OnFailure_2990_
0x180755cd7  lea     this, [rbp+4Fh+value]; this
0x180755cdb  call    ?ReleaseAndReset@CValue@@QEAAXXZ; CValue::ReleaseAndReset(void)
0x180755ce0  lea     this, [rbp+4Fh+cp]; this
0x180755ce4  call    ??1CREATEPARAMETERS@@QEAA@XZ; CREATEPARAMETERS::~CREATEPARAMETERS(void)
0x180755ce9  lea     this, [rsp+110h+pAbbreviationIcon]; this
0x180755cee  call    ?DecrementRefCount@?$xref_ptr@VCTranslateTransform@@@@AEAAXXZ; xref_ptr<CTranslateTransform>::DecrementRefCount(void)
0x180755cf3  lea     this, [rsp+110h+itemInLeftColumn]; this
0x180755cf8  call    ??1?$xref_ptr@VCUIElement@@@@QEAA@XZ; xref_ptr<CUIElement>::~xref_ptr<CUIElement>(void)
0x180755cfd  mov     ebx, edi
0x180755cff  jmp     short loc_180755D27
0x180755d01  mov     ecx, eax; failedFrameHR
0x180755d03  call    OnFailure_2990_
0x180755d08  lea     this, [rbp+4Fh+cp]; this
0x180755d0c  call    ??1CREATEPARAMETERS@@QEAA@XZ; CREATEPARAMETERS::~CREATEPARAMETERS(void)
0x180755d11  lea     this, [rsp+110h+pAbbreviationIcon]; this
0x180755d16  call    ?DecrementRefCount@?$xref_ptr@VCTranslateTransform@@@@AEAAXXZ; xref_ptr<CTranslateTransform>::DecrementRefCount(void)
0x180755d1b  jmp     loc_180755A7F
0x180755d20  mov     ecx, eax; failedFrameHR
0x180755d22  call    OnFailure_2990_
0x180755d27  mov     this, [rbp+4Fh+iconFile.hstr_]; string
0x180755d2b  call    cs:__imp_WindowsDeleteString
0x180755d31  mov     eax, ebx
0x180755d33  jmp     short loc_180755D3F
0x180755d35  call    OnNewFailure_1172_
0x180755d3a  mov     eax, 80004003h
0x180755d3f  mov     this, [rbp+4Fh+var_48]
0x180755d43  xor     this, rsp; StackCookie
0x180755d46  call    __security_check_cookie
0x180755d4b  add     rsp, 0D8h
0x180755d52  pop     r15
0x180755d54  pop     r14
0x180755d56  pop     r13
0x180755d58  pop     r12
0x180755d5a  pop     rdi
0x180755d5b  pop     rsi
0x180755d5c  pop     rbx
0x180755d5d  pop     rbp
0x180755d5e  retn
```
