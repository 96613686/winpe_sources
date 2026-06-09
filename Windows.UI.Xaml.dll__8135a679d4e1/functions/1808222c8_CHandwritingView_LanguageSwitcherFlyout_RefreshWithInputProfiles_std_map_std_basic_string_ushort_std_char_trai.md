# CHandwritingView::LanguageSwitcherFlyout::RefreshWithInputProfiles(std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,CHandwritingView::InputProfileMapValue,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CHandwritingView::InputProfileMapValue>>> const &)

- ea: `0x1808222c8`
- end: `0x180822940`
- name: `?RefreshWithInputProfiles@LanguageSwitcherFlyout@CHandwritingView@@QEAAJAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UInputProfileMapValue@CHandwritingView@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UInputProfileMapValue@CHandwritingView@@@std@@@2@@std@@@Z`
- size: `1656`
- prototype: `HRESULT __fastcall(CHandwritingView::LanguageSwitcherFlyout *this, const std::map<std::wstring,CHandwritingView::InputProfileMapValue> *profileMap)`
- caller_count: `1`
- callee_count: `32`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1807214b8`

## callees

- `0x180004bc0`
- `0x18000b6c0`
- `0x180021970`
- `0x18004486c`
- `0x180045d64`
- `0x18006cfd0`
- `0x1800c6d60`
- `0x1800e8b00`
- `0x1800eb360`
- `0x1800f85d0`
- `0x1800fe130`
- `0x180100ca0`
- `0x1801376ac`
- `0x1801bcad8`
- `0x1801eb6f4`
- `0x180200ea8`
- `0x180202ac4`
- `0x180254ef4`
- `0x18027eaa0`
- `0x18028b1c0`
- `0x1802b42f4`
- `0x1802eb450`
- `0x1802f2850`
- `0x18034045c`
- `0x1804de0e8`
- `0x180688828`
- `0x1807558f0`
- `0x18076e110`
- `0x18081a0f4`
- `0x1808222c8`
- `0x18096272c`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180822556`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180822583`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18082261c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1808226de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1808226f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180822706`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1808227a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1808227bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1808227cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180822815`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180822829`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180822556`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180822583`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18082261c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1808226de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1808226f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180822706`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1808227a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1808227bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1808227cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180822815`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180822829`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1808225bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18082263f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1808225bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18082263f`
- `Bcp47Langs!Bcp47FromLcid` at `0x18082256d`
- `Bcp47Langs!Bcp47FromLcid` at `0x18082256d`
- `Bcp47Langs!Bcp47GetLanguageName` at `0x18082259c`
- `Bcp47Langs!Bcp47GetLanguageName` at `0x18082259c`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__int64 __fastcall CHandwritingView::LanguageSwitcherFlyout::RefreshWithInputProfiles(
        CHandwritingView::LanguageSwitcherFlyout *this,
        const std::map<std::wstring,CHandwritingView::InputProfileMapValue> *profileMap)
{
  Flyweight::ValueObjectWrapper<CDOSharedState> *m_ptr; // rax
  CCoreServices *m_coreServices; // rdi
  HRESULT ValueByIndex; // eax
  unsigned int v7; // ebx
  CDependencyObject *v8; // rax
  const xstring_ptr_view *v9; // rax
  HRESULT v10; // ecx
  float RasterizationScaleForElement; // xmm0_4
  std::_Tree_node<std::pair<std::wstring const ,CHandwritingView::InputProfileMapValue>,void *> *Left; // rbx
  CHandwritingView::InputProfileMapValue *p_second; // r15
  HRESULT IconContentFromInputProfile; // eax
  HRESULT v15; // ecx
  HRESULT v16; // r14d
  CPointKeyFrameCollection *v17; // rdi
  CImage *v18; // rdi
  HRESULT v19; // eax
  CDependencyObject *v20; // rax
  bool v21; // r9
  Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfile *ptr; // rcx
  HRESULT LanguageName; // eax
  const wchar_t *StringRawBuffer; // rax
  HRESULT v25; // eax
  Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfile *v26; // r15
  HRESULT (__fastcall *get_DisplayDescription)(Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfile *, HSTRING__ **); // r14
  const wchar_t *v28; // rax
  HRESULT v29; // eax
  std::_Tree_node<std::pair<std::wstring const ,CHandwritingView::InputProfileMapValue>,void *> *Right; // rcx
  std::_Tree_node<std::pair<std::wstring const ,CHandwritingView::InputProfileMapValue>,void *> *i; // rax
  std::_Tree_node<std::pair<std::wstring const ,CHandwritingView::InputProfileMapValue>,void *> *j; // rcx
  Microsoft::WRL::Wrappers::HString fullLangName; // [rsp+38h] [rbp-89h] BYREF
  xref_ptr<CHandwritingView::LanguageSwitcherMenuItem> newLangItem; // [rsp+40h] [rbp-81h] BYREF
  xref_ptr<CPointKeyFrameCollection> isIconContentIcon; // [rsp+48h] [rbp-79h] BYREF
  xref_ptr<CUIElement> pIconContent; // [rsp+50h] [rbp-71h] BYREF
  xref_ptr<CImage> pImage; // [rsp+58h] [rbp-69h] BYREF
  Microsoft::WRL::Wrappers::HString hstrProfileDesc; // [rsp+60h] [rbp-61h] BYREF
  xref_ptr<CStyle> pLangMenuItemStyle; // [rsp+68h] [rbp-59h] BYREF
  xref_ptr<CBinding> langId; // [rsp+70h] [rbp-51h] BYREF
  _BYTE cp[48]; // [rsp+78h] [rbp-49h] OVERLAPPED BYREF
  CDependencyObjectCollection *v43; // [rsp+A8h] [rbp-19h]
  xephemeral_string_ptr v44; // [rsp+B0h] [rbp-11h] BYREF
  CValue value; // [rsp+C8h] [rbp+7h] BYREF

  m_ptr = this->m_sharedState.m_ptr;
  value = 0;
  m_coreServices = m_ptr->m_value.m_coreServices;
  *(_QWORD *)&cp[24] = m_ptr->m_value.m_coreServices;
  *(_QWORD *)&cp[8] = 0;
  *(_QWORD *)&cp[16] = 0;
  *(_OWORD *)&cp[32] = 0;
  ValueByIndex = CDependencyObject::GetValueByIndex(this, MenuFlyout_Items, &value);
  v7 = ValueByIndex;
  if ( ValueByIndex < 0 )
  {
    OnFailure_2990_(ValueByIndex);
    CREATEPARAMETERS::~CREATEPARAMETERS((CREATEPARAMETERS *)&cp[8]);
    CValue::ReleaseAndReset(&value);
    return v7;
  }
  else
  {
    v8 = CValue::As<24>(&value);
    v43 = do_pointer_cast<CMenuFlyoutItemBaseCollection>(v8);
    CCollection::Clear(v43);
    langId.m_ptr = 0;
    xref_ptr<CUIElement>::~xref_ptr<CUIElement>(&langId);
    xephemeral_string_ptr::xephemeral_string_ptr(&v44, L"LanguageSwitcherMenuFlyoutItemStyle", 0x23u);
    CCoreServices::LookupThemeResource(m_coreServices, v9, &langId.m_ptr);
    if ( langId.m_ptr )
    {
      RasterizationScaleForElement = RootScale::GetRasterizationScaleForElement(this);
      Left = profileMap->_Mypair._Myval2._Myval2._Myhead->_Left;
      while ( Left != profileMap->_Mypair._Myval2._Myval2._Myhead )
      {
        isIconContentIcon.m_ptr = 0;
        pImage.m_ptr = 0;
        LOBYTE(pIconContent.m_ptr) = 0;
        xref_ptr<CUIElement>::~xref_ptr<CUIElement>((xref_ptr<CBinding> *)&pImage);
        p_second = &Left->_Myval.second;
        IconContentFromInputProfile = CHandwritingView::LanguageSwitcherFlyout::CreateIconContentFromInputProfile(
                                        this,
                                        &Left->_Myval.second,
                                        (int)(float)(RasterizationScaleForElement * 32.0),
                                        &pImage.m_ptr,
                                        (bool *)&pIconContent);
        v16 = IconContentFromInputProfile;
        if ( IconContentFromInputProfile < 0 )
          goto LABEL_45;
        if ( LOBYTE(pIconContent.m_ptr) )
        {
          xref_ptr<CTranslateTransform>::DecrementRefCount(&isIconContentIcon);
          IconContentFromInputProfile = CHandwritingView::LanguageSwitcherMenuItem::Create(
                                          &isIconContentIcon.m_ptr,
                                          (CREATEPARAMETERS *)&cp[8],
                                          &Left->_Myval.first,
                                          0);
          v16 = IconContentFromInputProfile;
          if ( IconContentFromInputProfile < 0
            || (CValue::SetAddRef<24>(&value, pImage.m_ptr),
                v17 = isIconContentIcon.m_ptr,
                IconContentFromInputProfile = CDependencyObject::SetValueByKnownIndex(
                                                isIconContentIcon.m_ptr,
                                                MenuFlyoutItem_Icon,
                                                &value),
                v16 = IconContentFromInputProfile,
                IconContentFromInputProfile < 0) )
          {
LABEL_45:
            OnFailure_2990_(IconContentFromInputProfile);
            goto LABEL_46;
          }
        }
        else
        {
          v18 = pImage.m_ptr;
          if ( !pImage.m_ptr || !CDependencyObject::OfTypeByIndex<599>(pImage.m_ptr) )
          {
            hstrProfileDesc.hstr_ = 0;
            OnNewFailure_1172_(v15);
            xref_ptr<CTranslateTransform>::DecrementRefCount((xref_ptr<CPointKeyFrameCollection> *)&hstrProfileDesc);
            xref_ptr<CUIElement>::~xref_ptr<CUIElement>((xref_ptr<CBinding> *)&pImage);
            xref_ptr<CTranslateTransform>::DecrementRefCount(&isIconContentIcon);
            goto LABEL_49;
          }
          hstrProfileDesc.hstr_ = (HSTRING__ *)v18;
          CDependencyObject::AddRef(v18);
          xref_ptr<CTranslateTransform>::DecrementRefCount(&isIconContentIcon);
          v19 = CHandwritingView::LanguageSwitcherMenuItem::Create(
                  &isIconContentIcon.m_ptr,
                  (CREATEPARAMETERS *)&cp[8],
                  &Left->_Myval.first,
                  v18);
          v16 = v19;
          if ( v19 < 0 )
          {
            OnFailure_2990_(v19);
            xref_ptr<CTranslateTransform>::DecrementRefCount((xref_ptr<CPointKeyFrameCollection> *)&hstrProfileDesc);
            goto LABEL_46;
          }
          xref_ptr<CTranslateTransform>::DecrementRefCount((xref_ptr<CPointKeyFrameCollection> *)&hstrProfileDesc);
          v17 = isIconContentIcon.m_ptr;
        }
        IconContentFromInputProfile = CDependencyObject::GetValueByIndex(this, HandwritingView_AttachedView, &value);
        v16 = IconContentFromInputProfile;
        if ( IconContentFromInputProfile < 0 )
          goto LABEL_45;
        v20 = CValue::As<24>(&value);
        do_pointer_cast<CHandwritingView>(v20);
        IconContentFromInputProfile = CDependencyObject::PrivateEnsurePeerAndTryPeg(v17, 1, 0, v21, 0);
        v16 = IconContentFromInputProfile;
        if ( IconContentFromInputProfile < 0 )
          goto LABEL_45;
        v16 = CDependencyObject::SetValueByIndex(v17, HandwritingView_AttachedView, &value);
        if ( v16 < 0 )
        {
          OnFailure_2990_(v16);
          goto LABEL_46;
        }
        ptr = p_second->m_pCoreKeyboardInputProfile.ptr_;
        *(_DWORD *)cp = 0;
        newLangItem.m_ptr = 0;
        fullLangName.hstr_ = 0;
        LanguageName = ptr->get_Langid(ptr, (unsigned int *)cp);
        v16 = LanguageName;
        if ( LanguageName < 0 )
          goto LABEL_38;
        WindowsDeleteString(fullLangName.hstr_);
        fullLangName.hstr_ = 0;
        LanguageName = Bcp47FromLcid(*(unsigned int *)cp, &fullLangName);
        v16 = LanguageName;
        if ( LanguageName < 0
          || (WindowsDeleteString((HSTRING)newLangItem.m_ptr),
              newLangItem.m_ptr = 0,
              LanguageName = Bcp47GetLanguageName(fullLangName.hstr_, &newLangItem),
              v16 = LanguageName,
              LanguageName < 0) )
        {
LABEL_38:
          OnFailure_2990_(LanguageName);
LABEL_39:
          WindowsDeleteString(fullLangName.hstr_);
          fullLangName.hstr_ = 0;
          WindowsDeleteString((HSTRING)newLangItem.m_ptr);
          newLangItem.m_ptr = 0;
LABEL_46:
          xref_ptr<CUIElement>::~xref_ptr<CUIElement>((xref_ptr<CBinding> *)&pImage);
          xref_ptr<CTranslateTransform>::DecrementRefCount(&isIconContentIcon);
          goto LABEL_50;
        }
        hstrProfileDesc.hstr_ = (HSTRING__ *)&xstring_ptr_constants::c_xstring_ptr_storage_null;
        StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)newLangItem.m_ptr, 0);
        v25 = xstring_ptr::CloneBuffer(StringRawBuffer, (xstring_ptr *)&hstrProfileDesc);
        v16 = v25;
        if ( v25 < 0
          || (CValue::SetString(&value, (const xstring_ptr *)&hstrProfileDesc),
              v25 = CDependencyObject::SetValueByIndex(v17, MenuFlyoutItem_Text, &value),
              v16 = v25,
              v25 < 0) )
        {
          OnFailure_2990_(v25);
          xstring_ptr::~xstring_ptr((xstring_ptr *)&hstrProfileDesc);
          goto LABEL_39;
        }
        v26 = p_second->m_pCoreKeyboardInputProfile.ptr_;
        pLangMenuItemStyle.m_ptr = 0;
        get_DisplayDescription = v26->get_DisplayDescription;
        WindowsDeleteString(0);
        pLangMenuItemStyle.m_ptr = 0;
        get_DisplayDescription(v26, (HSTRING__ **)&pLangMenuItemStyle);
        v28 = WindowsGetStringRawBuffer((HSTRING)pLangMenuItemStyle.m_ptr, 0);
        v29 = xstring_ptr::CloneBuffer(v28, (xstring_ptr *)&hstrProfileDesc);
        v16 = v29;
        if ( v29 < 0 )
          goto LABEL_36;
        CValue::SetString(&value, (const xstring_ptr *)&hstrProfileDesc);
        v29 = CDependencyObject::SetValueByIndex(v17, MenuFlyoutItem_KeyboardAcceleratorTextOverride, &value);
        v16 = v29;
        if ( v29 < 0
          || (DirectUI::MenuFlyoutItem::AddProofingItemHandlerStatic(v17, CHandwritingView::OnLanguageSelected),
              CValue::Wrap<24>(&value, v17),
              v29 = CDependencyObjectCollection::Append(v43, &value, 0),
              v16 = v29,
              v29 < 0)
          || (v29 = CDependencyObject::SetValueByKnownIndex(v17, FrameworkElement_Style, langId.m_ptr),
              v16 = v29,
              v29 < 0) )
        {
LABEL_36:
          OnFailure_2990_(v29);
          WindowsDeleteString((HSTRING)pLangMenuItemStyle.m_ptr);
          pLangMenuItemStyle.m_ptr = 0;
          xstring_ptr::~xstring_ptr((xstring_ptr *)&hstrProfileDesc);
          WindowsDeleteString(fullLangName.hstr_);
          fullLangName.hstr_ = 0;
          WindowsDeleteString((HSTRING)newLangItem.m_ptr);
          newLangItem.m_ptr = 0;
          goto LABEL_46;
        }
        WindowsDeleteString((HSTRING)pLangMenuItemStyle.m_ptr);
        pLangMenuItemStyle.m_ptr = 0;
        xstring_ptr::~xstring_ptr((xstring_ptr *)&hstrProfileDesc);
        WindowsDeleteString(fullLangName.hstr_);
        fullLangName.hstr_ = 0;
        WindowsDeleteString((HSTRING)newLangItem.m_ptr);
        newLangItem.m_ptr = 0;
        xref_ptr<CUIElement>::~xref_ptr<CUIElement>((xref_ptr<CBinding> *)&pImage);
        xref_ptr<CTranslateTransform>::DecrementRefCount(&isIconContentIcon);
        Right = Left->_Right;
        if ( Right->_Isnil )
        {
          for ( i = Left->_Parent; !i->_Isnil && Left == i->_Right; i = i->_Parent )
            Left = i;
          Left = i;
        }
        else
        {
          Left = Left->_Right;
          for ( j = Right->_Left; !j->_Isnil; j = j->_Left )
            Left = j;
        }
      }
      xref_ptr<CUIElement>::~xref_ptr<CUIElement>(&langId);
      CREATEPARAMETERS::~CREATEPARAMETERS((CREATEPARAMETERS *)&cp[8]);
      CValue::ReleaseAndReset(&value);
      return 0;
    }
    else
    {
      OnNewFailure_1172_(v10);
LABEL_49:
      v16 = -2147467261;
LABEL_50:
      xref_ptr<CUIElement>::~xref_ptr<CUIElement>(&langId);
      CREATEPARAMETERS::~CREATEPARAMETERS((CREATEPARAMETERS *)&cp[8]);
      CValue::ReleaseAndReset(&value);
      return (unsigned int)v16;
    }
  }
}

```

## disassembly

```asm
0x1808222c8  mov     rax, rsp
0x1808222cb  mov     [rax+10h], rbx
0x1808222cf  mov     [rax+18h], rdi
0x1808222d3  push    rbp
0x1808222d4  push    r12
0x1808222d6  push    r13
0x1808222d8  push    r14
0x1808222da  push    r15
0x1808222dc  lea     rbp, [rax-5Fh]
0x1808222e0  sub     rsp, 0F0h
0x1808222e7  movaps  xmmword ptr [rax-38h], xmm6
0x1808222eb  mov     rax, cs:__security_cookie
0x1808222f2  xor     rax, rsp
0x1808222f5  mov     [rbp+57h+var_40], rax
0x1808222f9  mov     rax, [this+10h]
0x1808222fd  lea     r8, [rbp+57h+value]; value
0x180822301  xorps   xmm0, xmm0
0x180822304  mov     r12, profileMap
0x180822307  movups  xmmword ptr [rbp+57h+value.m_value], xmm0
0x18082230b  xor     r15d, r15d
0x18082230e  mov     edx, 28Dh; index
0x180822313  mov     rdi, [rax]
0x180822316  mov     r13, this
0x180822319  mov     [rbp+57h+cp.m_spServiceProviderContext._Ptr], rdi
0x18082231d  mov     qword ptr [rbp+57h+cp.m_value.m_flags], r15
0x180822321  mov     [rbp+57h+cp.m_pCore], r15
0x180822325  movdqu  xmmword ptr [rbp+57h+cp.m_spServiceProviderContext._Rep], xmm0
0x18082232a  call    ?GetValueByIndex@CDependencyObject@@QEBAJW4KnownPropertyIndex@@PEAVCValue@@@Z; CDependencyObject::GetValueByIndex(KnownPropertyIndex,CValue *)
0x18082232f  mov     ebx, eax
0x180822331  test    eax, eax
0x180822333  js      loc_1808228F7
0x180822339  lea     this, [rbp+57h+value]; this
0x18082233d  call    ??$As@$0BI@@CValue@@QEAAPEAVCDependencyObject@@XZ; CValue::As<24>(void)
0x180822342  mov     this, rax; pDO
0x180822345  call    ??$do_pointer_cast@VCMenuFlyoutItemBaseCollection@@@@YAPEAVCMenuFlyoutItemBaseCollection@@PEAVCDependencyObject@@@Z; do_pointer_cast<CMenuFlyoutItemBaseCollection>(CDependencyObject *)
0x18082234a  mov     this, rax; this
0x18082234d  mov     [rbp+57h+var_70], rax
0x180822351  call    ?Clear@CCollection@@UEAAJXZ; CCollection::Clear(void)
0x180822356  lea     this, [rbp+57h+langId]; this
0x18082235a  mov     [rbp+57h+langId], r15
0x18082235e  call    ??1?$xref_ptr@VCUIElement@@@@QEAA@XZ; xref_ptr<CUIElement>::~xref_ptr<CUIElement>(void)
0x180822363  lea     r8d, [r15+23h]; count
0x180822367  lea     profileMap, aLanguageswitch_0; "LanguageSwitcherMenuFlyoutItemStyle"
0x18082236e  lea     this, [rbp+57h+var_68]; this
0x180822372  call    ??0xephemeral_string_ptr@@QEAA@PEBGI@Z; xephemeral_string_ptr::xephemeral_string_ptr(ushort const *,uint)
0x180822377  lea     r8, [rbp+57h+langId]; ppValue
0x18082237b  mov     profileMap, rax; strKey
0x18082237e  mov     this, rdi; this
0x180822381  call    ?LookupThemeResource@CCoreServices@@QEAAJAEBVxstring_ptr_view@@PEAPEAVCDependencyObject@@@Z; CCoreServices::LookupThemeResource(xstring_ptr_view const &,CDependencyObject * *)
0x180822386  cmp     [rbp+57h+langId], r15
0x18082238a  jz      loc_1808228CC
0x180822390  mov     this, r13; pDO
0x180822393  call    ?GetRasterizationScaleForElement@RootScale@@SAMPEAVCDependencyObject@@@Z; RootScale::GetRasterizationScaleForElement(CDependencyObject *)
0x180822398  mov     rbx, [r12]
0x18082239c  movaps  xmm6, xmm0
0x18082239f  mov     rbx, [rbx]
0x1808223a2  cmp     rbx, [r12]
0x1808223a6  jz      loc_1808228AD
0x1808223ac  lea     this, [rbp+57h+pImage]; this
0x1808223b0  mov     [rbp+57h+isIconContentIcon], r15
0x1808223b4  mov     [rbp+57h+pImage.m_ptr], r15
0x1808223b8  mov     byte ptr [rbp+57h+pIconContent.m_ptr], r15b
0x1808223bc  call    ??1?$xref_ptr@VCUIElement@@@@QEAA@XZ; xref_ptr<CUIElement>::~xref_ptr<CUIElement>(void)
0x1808223c1  movaps  xmm0, xmm6
0x1808223c4  lea     rax, [rbp+57h+pIconContent]
0x1808223c8  mulss   xmm0, cs:__real@42000000
0x1808223d0  lea     r15, [rbx+40h]
0x1808223d4  lea     r9, [rbp+57h+pImage]; ppResult
0x1808223d8  mov     [rsp+110h+isIcon], rax; isIcon
0x1808223dd  mov     profileMap, r15; inputProfileData
0x1808223e0  mov     this, r13; this
0x1808223e3  cvttss2si r8, xmm0; iconSize
0x1808223e8  call    ?CreateIconContentFromInputProfile@LanguageSwitcherFlyout@CHandwritingView@@QEAAJAEBUInputProfileMapValue@2@IPEAPEAVCUIElement@@AEA_N@Z; CHandwritingView::LanguageSwitcherFlyout::CreateIconContentFromInputProfile(CHandwritingView::InputProfileMapValue const &,uint,CUIElement * *,bool &)
0x1808223ed  mov     r14d, eax
0x1808223f0  test    eax, eax
0x1808223f2  js      loc_180822892
0x1808223f8  cmp     byte ptr [rbp+57h+pIconContent.m_ptr], 0
0x1808223fc  jz      short loc_18082245B
0x1808223fe  lea     this, [rbp+57h+isIconContentIcon]; this
0x180822402  call    ?DecrementRefCount@?$xref_ptr@VCTranslateTransform@@@@AEAAXXZ; xref_ptr<CTranslateTransform>::DecrementRefCount(void)
0x180822407  lea     r8, [rbx+20h]; inputProfileKey
0x18082240b  xor     r9d, r9d; pIconImage
0x18082240e  lea     profileMap, [rbp+57h+cp.m_value.m_flags]; pCreate
0x180822412  lea     this, [rbp+57h+isIconContentIcon]; ppObject
0x180822416  call    ?Create@LanguageSwitcherMenuItem@CHandwritingView@@SAJPEAPEAVCDependencyObject@@PEAVCREATEPARAMETERS@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCImage@@@Z; CHandwritingView::LanguageSwitcherMenuItem::Create(CDependencyObject * *,CREATEPARAMETERS *,std::wstring const &,CImage *)
0x18082241b  mov     r14d, eax
0x18082241e  test    eax, eax
0x180822420  js      loc_180822772
0x180822426  mov     profileMap, [rbp+57h+pImage.m_ptr]; value
0x18082242a  lea     this, [rbp+57h+value]; this
0x18082242e  call    ??$SetAddRef@$0BI@@CValue@@QEAAXPEAVCDependencyObject@@@Z; CValue::SetAddRef<24>(CDependencyObject *)
0x180822433  mov     rdi, [rbp+57h+isIconContentIcon]
0x180822437  lea     r8, [rbp+57h+value]; value
0x18082243b  mov     this, rdi; this
0x18082243e  mov     edx, 750h; index
0x180822443  call    ?SetValueByKnownIndex@CDependencyObject@@QEAAJW4KnownPropertyIndex@@AEBVCValue@@@Z; CDependencyObject::SetValueByKnownIndex(KnownPropertyIndex,CValue const &)
0x180822448  mov     r14d, eax
0x18082244b  test    eax, eax
0x18082244d  jns     short loc_1808224B9
0x18082244f  mov     ecx, eax; failedFrameHR
0x180822451  call    OnFailure_2990_
0x180822456  jmp     loc_180822899
0x18082245b  mov     rdi, [rbp+57h+pImage.m_ptr]
0x18082245f  test    rdi, rdi
0x180822462  jz      loc_180822868
0x180822468  mov     this, rdi; this
0x18082246b  call    ??$OfTypeByIndex@$0CFH@@CDependencyObject@@QEBA_NXZ; CDependencyObject::OfTypeByIndex<599>(void)
0x180822470  test    al, al
0x180822472  jz      loc_180822868
0x180822478  mov     this, rdi; this
0x18082247b  mov     [rbp+57h+hstrProfileDesc.hstr_], rdi
0x18082247f  call    ?AddRef@CDependencyObject@@QEAAXXZ; CDependencyObject::AddRef(void)
0x180822484  lea     this, [rbp+57h+isIconContentIcon]; this
0x180822488  call    ?DecrementRefCount@?$xref_ptr@VCTranslateTransform@@@@AEAAXXZ; xref_ptr<CTranslateTransform>::DecrementRefCount(void)
0x18082248d  lea     r8, [rbx+20h]; inputProfileKey
0x180822491  mov     r9, rdi; pIconImage
0x180822494  lea     profileMap, [rbp+57h+cp.m_value.m_flags]; pCreate
0x180822498  lea     this, [rbp+57h+isIconContentIcon]; ppObject
0x18082249c  call    ?Create@LanguageSwitcherMenuItem@CHandwritingView@@SAJPEAPEAVCDependencyObject@@PEAVCREATEPARAMETERS@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCImage@@@Z; CHandwritingView::LanguageSwitcherMenuItem::Create(CDependencyObject * *,CREATEPARAMETERS *,std::wstring const &,CImage *)
0x1808224a1  mov     r14d, eax
0x1808224a4  test    eax, eax
0x1808224a6  js      loc_180822856
0x1808224ac  lea     this, [rbp+57h+hstrProfileDesc]; this
0x1808224b0  call    ?DecrementRefCount@?$xref_ptr@VCTranslateTransform@@@@AEAAXXZ; xref_ptr<CTranslateTransform>::DecrementRefCount(void)
0x1808224b5  mov     rdi, [rbp+57h+isIconContentIcon]
0x1808224b9  mov     edx, 574h; index
0x1808224be  lea     r8, [rbp+57h+value]; value
0x1808224c2  mov     this, r13; this
0x1808224c5  call    ?GetValueByIndex@CDependencyObject@@QEBAJW4KnownPropertyIndex@@PEAVCValue@@@Z; CDependencyObject::GetValueByIndex(KnownPropertyIndex,CValue *)
0x1808224ca  mov     r14d, eax
0x1808224cd  test    eax, eax
0x1808224cf  js      loc_18082284D
0x1808224d5  lea     this, [rbp+57h+value]; this
0x1808224d9  call    ??$As@$0BI@@CValue@@QEAAPEAVCDependencyObject@@XZ; CValue::As<24>(void)
0x1808224de  mov     this, rax; pDO
0x1808224e1  call    ??$do_pointer_cast@VCHandwritingView@@@@YAPEAVCHandwritingView@@PEAVCDependencyObject@@@Z; do_pointer_cast<CHandwritingView>(CDependencyObject *)
0x1808224e6  xor     r8d, r8d; fPegRef
0x1808224e9  mov     [rsp+110h+isIcon], 0; fPegNoRef
0x1808224f2  mov     dl, 1; fPegNoRef
0x1808224f4  mov     this, rdi; this
0x1808224f7  call    ?PrivateEnsurePeerAndTryPeg@CDependencyObject@@AEAAJ_N00PEA_N@Z; CDependencyObject::PrivateEnsurePeerAndTryPeg(bool,bool,bool,bool *)
0x1808224fc  mov     r14d, eax
0x1808224ff  test    eax, eax
0x180822501  js      loc_180822844
0x180822507  mov     edx, 574h; index
0x18082250c  lea     r8, [rbp+57h+value]; value
0x180822510  mov     this, rdi; this
0x180822513  call    ?SetValueByIndex@CDependencyObject@@QEAAJW4KnownPropertyIndex@@AEBVCValue@@@Z; CDependencyObject::SetValueByIndex(KnownPropertyIndex,CValue const &)
0x180822518  mov     r14d, eax
0x18082251b  xor     eax, eax
0x18082251d  test    r14d, r14d
0x180822520  js      loc_18082283A
0x180822526  mov     this, [r15]
0x180822529  lea     profileMap, [rbp+57h+cp]
0x18082252d  mov     dword ptr [rbp+57h+cp.m_value.m_value], eax
0x180822530  mov     [rsp+110h+newLangItem.m_ptr], rax
0x180822535  mov     [rsp+110h+fullLangName.hstr_], rax
0x18082253a  mov     rax, [this]
0x18082253d  mov     rax, [rax+40h]
0x180822541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180822546  mov     r14d, eax
0x180822549  test    eax, eax
0x18082254b  js      loc_180822809
0x180822551  mov     this, [rsp+110h+fullLangName.hstr_]; string
0x180822556  call    cs:__imp_WindowsDeleteString
0x18082255c  mov     ecx, dword ptr [rbp+57h+cp.m_value.m_value]
0x18082255f  lea     profileMap, [rsp+110h+fullLangName]
0x180822564  mov     [rsp+110h+fullLangName.hstr_], 0
0x18082256d  call    cs:__imp_Bcp47FromLcid
0x180822573  mov     r14d, eax
0x180822576  test    eax, eax
0x180822578  js      loc_180822800
0x18082257e  mov     this, [rsp+110h+newLangItem.m_ptr]; string
0x180822583  call    cs:__imp_WindowsDeleteString
0x180822589  mov     this, [rsp+110h+fullLangName.hstr_]
0x18082258e  lea     profileMap, [rsp+110h+newLangItem]
0x180822593  mov     [rsp+110h+newLangItem.m_ptr], 0
0x18082259c  call    cs:__imp_Bcp47GetLanguageName
0x1808225a2  mov     r14d, eax
0x1808225a5  test    eax, eax
0x1808225a7  js      loc_1808227F7
0x1808225ad  mov     this, [rsp+110h+newLangItem.m_ptr]; string
0x1808225b2  lea     rax, ?c_xstring_ptr_storage_null@xstring_ptr_constants@@2Uxstring_ptr_storage@@B; xstring_ptr_storage const xstring_ptr_constants::c_xstring_ptr_storage_null
0x1808225b9  xor     edx, edx; length
0x1808225bb  mov     [rbp+57h+hstrProfileDesc.hstr_], rax
0x1808225bf  call    cs:__imp_WindowsGetStringRawBuffer
0x1808225c5  mov     this, rax; buffer
0x1808225c8  lea     profileMap, [rbp+57h+hstrProfileDesc]; pstrCloned
0x1808225cc  call    ?CloneBuffer@xstring_ptr@@SAJPEBGPEAV1@@Z; xstring_ptr::CloneBuffer(ushort const *,xstring_ptr *)
0x1808225d1  mov     r14d, eax
0x1808225d4  test    eax, eax
0x1808225d6  js      loc_1808227E5
0x1808225dc  lea     profileMap, [rbp+57h+hstrProfileDesc]; value
0x1808225e0  lea     this, [rbp+57h+value]; this
0x1808225e4  call    ?SetString@CValue@@QEAAXAEBVxstring_ptr@@@Z; CValue::SetString(xstring_ptr const &)
0x1808225e9  mov     edx, 754h; index
0x1808225ee  lea     r8, [rbp+57h+value]; value
0x1808225f2  mov     this, rdi; this
0x1808225f5  call    ?SetValueByIndex@CDependencyObject@@QEAAJW4KnownPropertyIndex@@AEBVCValue@@@Z; CDependencyObject::SetValueByIndex(KnownPropertyIndex,CValue const &)
0x1808225fa  mov     r14d, eax
0x1808225fd  test    eax, eax
0x1808225ff  js      loc_1808227DC
0x180822605  mov     r15, [r15]
0x180822608  xor     ecx, ecx; string
0x18082260a  mov     [rbp+57h+pLangMenuItemStyle.m_ptr], 0
0x180822612  mov     rax, [r15]
0x180822615  mov     r14, [rax+80h]
0x18082261c  call    cs:__imp_WindowsDeleteString
0x180822622  lea     profileMap, [rbp+57h+pLangMenuItemStyle]
0x180822626  mov     [rbp+57h+pLangMenuItemStyle.m_ptr], 0
0x18082262e  mov     this, r15
0x180822631  mov     rax, r14
0x180822634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180822639  mov     this, [rbp+57h+pLangMenuItemStyle.m_ptr]; string
0x18082263d  xor     edx, edx; length
0x18082263f  call    cs:__imp_WindowsGetStringRawBuffer
0x180822645  mov     this, rax; buffer
0x180822648  lea     profileMap, [rbp+57h+hstrProfileDesc]; pstrCloned
0x18082264c  call    ?CloneBuffer@xstring_ptr@@SAJPEBGPEAV1@@Z; xstring_ptr::CloneBuffer(ushort const *,xstring_ptr *)
0x180822651  xor     r15d, r15d
0x180822654  mov     r14d, eax
0x180822657  test    eax, eax
0x180822659  js      loc_180822799
0x18082265f  lea     profileMap, [rbp+57h+hstrProfileDesc]; value
0x180822663  lea     this, [rbp+57h+value]; this
0x180822667  call    ?SetString@CValue@@QEAAXAEBVxstring_ptr@@@Z; CValue::SetString(xstring_ptr const &)
0x18082266c  mov     edx, 751h; index
0x180822671  lea     r8, [rbp+57h+value]; value
0x180822675  mov     this, rdi; this
0x180822678  call    ?SetValueByIndex@CDependencyObject@@QEAAJW4KnownPropertyIndex@@AEBVCValue@@@Z; CDependencyObject::SetValueByIndex(KnownPropertyIndex,CValue const &)
0x18082267d  mov     r14d, eax
0x180822680  test    eax, eax
0x180822682  js      loc_180822790
0x180822688  lea     profileMap, ?OnLanguageSelected@CHandwritingView@@CAJPEAVCDependencyObject@@PEAVCEventArgs@@@Z; eventHandler
0x18082268f  mov     this, rdi; pMenuFlyoutItem
0x180822692  call    ?AddProofingItemHandlerStatic@MenuFlyoutItem@DirectUI@@SAJPEAVCDependencyObject@@P6AJ0PEAVCEventArgs@@@Z@Z; DirectUI::MenuFlyoutItem::AddProofingItemHandlerStatic(CDependencyObject *,long (*)(CDependencyObject *,CEventArgs *))
0x180822697  mov     profileMap, rdi; value
0x18082269a  lea     this, [rbp+57h+value]; this
0x18082269e  call    ??$Wrap@$0BI@@CValue@@QEAAXPEAVCDependencyObject@@@Z; CValue::Wrap<24>(CDependencyObject *)
0x1808226a3  mov     this, [rbp+57h+var_70]; this
0x1808226a7  lea     profileMap, [rbp+57h+value]; value
0x1808226ab  xor     r8d, r8d; pnIndex
0x1808226ae  call    ?Append@CDependencyObjectCollection@@UEAAJAEAVCValue@@PEAI@Z; CDependencyObjectCollection::Append(CValue &,uint *)
0x1808226b3  mov     r14d, eax
0x1808226b6  test    eax, eax
0x1808226b8  js      loc_180822787
0x1808226be  mov     r8, [rbp+57h+langId]; value
0x1808226c2  mov     edx, 26Ch; index
0x1808226c7  mov     this, rdi; this
0x1808226ca  call    ?SetValueByKnownIndex@CDependencyObject@@QEAAJW4KnownPropertyIndex@@PEAV1@@Z; CDependencyObject::SetValueByKnownIndex(KnownPropertyIndex,CDependencyObject *)
0x1808226cf  mov     r14d, eax
0x1808226d2  test    eax, eax
0x1808226d4  js      loc_18082277E
0x1808226da  mov     this, [rbp+57h+pLangMenuItemStyle.m_ptr]; string
0x1808226de  call    cs:__imp_WindowsDeleteString
0x1808226e4  lea     this, [rbp+57h+hstrProfileDesc]; this
0x1808226e8  mov     [rbp+57h+pLangMenuItemStyle.m_ptr], r15
0x1808226ec  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x1808226f1  mov     this, [rsp+110h+fullLangName.hstr_]; string
0x1808226f6  call    cs:__imp_WindowsDeleteString
0x1808226fc  mov     this, [rsp+110h+newLangItem.m_ptr]; string
0x180822701  mov     [rsp+110h+fullLangName.hstr_], r15
0x180822706  call    cs:__imp_WindowsDeleteString
0x18082270c  lea     this, [rbp+57h+pImage]; this
0x180822710  mov     [rsp+110h+newLangItem.m_ptr], r15
0x180822715  call    ??1?$xref_ptr@VCUIElement@@@@QEAA@XZ; xref_ptr<CUIElement>::~xref_ptr<CUIElement>(void)
0x18082271a  lea     this, [rbp+57h+isIconContentIcon]; this
0x18082271e  call    ?DecrementRefCount@?$xref_ptr@VCTranslateTransform@@@@AEAAXXZ; xref_ptr<CTranslateTransform>::DecrementRefCount(void)
0x180822723  mov     this, [rbx+10h]
0x180822727  cmp     [this+19h], r15b
0x18082272b  jz      short loc_18082274E
0x18082272d  mov     rax, [rbx+8]
0x180822731  jmp     short loc_180822740
0x180822733  cmp     rbx, [rax+10h]
0x180822737  jnz     short loc_180822746
0x180822739  mov     rbx, rax
0x18082273c  mov     rax, [rax+8]
0x180822740  cmp     [rax+19h], r15b
0x180822744  jz      short loc_180822733
0x180822746  mov     rbx, rax
0x180822749  jmp     loc_1808223A2
0x18082274e  mov     rbx, this
0x180822751  mov     this, [this]
0x180822754  cmp     [this+19h], r15b
0x180822758  jnz     loc_1808223A2
0x18082275e  mov     rax, [this]
0x180822761  mov     rbx, this
0x180822764  mov     this, rax
0x180822767  cmp     [rax+19h], r15b
0x18082276b  jz      short loc_18082275E
0x18082276d  jmp     loc_1808223A2
0x180822772  mov     ecx, eax; failedFrameHR
0x180822774  call    OnFailure_2990_
0x180822779  jmp     loc_180822899
0x18082277e  mov     ecx, eax; failedFrameHR
0x180822780  call    OnFailure_2990_
0x180822785  jmp     short loc_1808227A0
0x180822787  mov     ecx, eax; failedFrameHR
0x180822789  call    OnFailure_2990_
0x18082278e  jmp     short loc_1808227A0
  ... truncated ...
```
