# CRichEditBox::HandleLinkNavigation(uint,uint,void *)

- ea: `0x18082bb48`
- end: `0x18082c09c`
- name: `?HandleLinkNavigation@CRichEditBox@@AEAAJIIPEAX@Z`
- size: `1364`
- prototype: `HRESULT __fastcall(CRichEditBox *this, unsigned int linkType, unsigned int msg, void *pData)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1802a4240`
- `0x18082b720`

## callees

- `0x180001398`
- `0x180004bc0`
- `0x1800053b0`
- `0x180008428`
- `0x1801451c0`
- `0x1801d1a98`
- `0x18020ca40`
- `0x1804cab60`
- `0x1805313a4`
- `0x180607320`
- `0x1806832c8`
- `0x1807540ac`
- `0x1807b7568`
- `0x18082bb48`
- `0x18082c138`
- `0x180973cb4`
- `0x180973d84`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18082bd82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18082bdb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18082be57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18082be65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18082bf42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18082bf50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18082bd82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18082bdb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18082be57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18082be65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18082bf42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18082bf50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18082be0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18082be28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18082be0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18082be28`
- `OLEAUT32!__imp_SysStringLen` at `0x18082bc68`
- `OLEAUT32!__imp_SysStringLen` at `0x18082bc68`

## pseudocode

```c
__int64 __fastcall CRichEditBox::HandleLinkNavigation(
        CRichEditBox *this,
        unsigned int linkType,
        unsigned int msg,
        unsigned int *pData)
{
  bool v7; // al
  HRESULT Document; // eax
  unsigned int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // rdx
  HRESULT v12; // eax
  ITextRange *ptr; // rdi
  HRESULT (__fastcall *GetText)(ITextRange *, wchar_t **); // rbx
  HRESULT v15; // eax
  unsigned int v16; // edx
  HRESULT v18; // eax
  unsigned int v19; // edi
  int v20; // edx
  HRESULT ContentLinkInfo; // eax
  Windows::UI::Text::IContentLinkInfo *v22; // rbx
  HRESULT (__fastcall *get_DisplayText)(Windows::UI::Text::IContentLinkInfo *, HSTRING__ **); // rdi
  HRESULT v24; // eax
  Windows::UI::Text::IContentLinkInfo *v25; // rdi
  HRESULT (__fastcall *get_LinkContentKind)(Windows::UI::Text::IContentLinkInfo *, HSTRING__ **); // rbx
  const _GUID *v27; // r8
  const _GUID *v28; // r9
  const wchar_t *v29; // rbx
  wchar_t *StringRawBuffer; // rax
  Windows::Foundation::IUriRuntimeClass *v31; // rcx
  CContentLinkInvokedEventArgs *m_ptr; // rbx
  HRESULT v33; // eax
  Windows::UI::Text::IContentLinkInfo *v34; // rcx
  Windows::UI::Text::IContentLinkInfo *v35; // rcx
  Windows::UI::Text::IContentLinkInfo *v36; // rcx
  CTextBoxView *m_pView; // rdi
  MouseCursor v38; // r14
  HRESULT ShouldNavigateLinkOnMouseClick; // eax
  Microsoft::WRL::ComPtr<Windows::UI::Text::IContentLinkInfo> spContentLinkInfo; // [rsp+50h] [rbp-30h] BYREF
  Microsoft::WRL::ComPtr<ITextRange> spTextRange; // [rsp+58h] [rbp-28h] BYREF
  ctl::ComPtr<Windows::Foundation::IUriRuntimeClass> spUri; // [rsp+60h] [rbp-20h] BYREF
  xref_ptr<CContentLinkInvokedEventArgs> eventArgs; // [rsp+68h] [rbp-18h] BYREF
  _tlgWrapSz<unsigned short> pEventMetadata; // [rsp+70h] [rbp-10h] BYREF
  bool fNavigate; // [rsp+C0h] [rbp+40h] BYREF

  fNavigate = 0;
  if ( msg == 512 )
  {
    m_pView = this->m_pView;
    if ( !m_pView )
      return 0;
    if ( this->m_linkHoverTarget == None )
      this->m_eNonHyperlinkCursor = m_pView->m_eMouseCursor;
    v38 = MouseCursorArrow;
    if ( linkType == 1803 )
    {
      this->m_linkHoverTarget = PerThread;
      ShouldNavigateLinkOnMouseClick = CRichEditBox::ShouldNavigateLinkOnMouseClick(this, &fNavigate);
      v9 = ShouldNavigateLinkOnMouseClick;
      if ( ShouldNavigateLinkOnMouseClick < 0 )
      {
LABEL_75:
        OnFailure_2990_(ShouldNavigateLinkOnMouseClick);
        return v9;
      }
      v38 = fNavigate ? MouseCursorArrow : MouseCursorIBeam;
    }
    else if ( linkType == 1822 )
    {
      this->m_linkHoverTarget = 2;
      if ( pData[15] == 1 )
      {
        v38 = MouseCursorPerson;
      }
      else if ( pData[15] == 2 )
      {
        v38 = MouseCursorPin;
      }
    }
    else
    {
      this->m_linkHoverTarget = None;
    }
    if ( m_pView->m_eMouseCursor == v38 )
      return 0;
    ShouldNavigateLinkOnMouseClick = CFrameworkElement::SetCursor(this->m_pView, v38);
    v9 = ShouldNavigateLinkOnMouseClick;
    if ( ShouldNavigateLinkOnMouseClick >= 0 )
      return 0;
    goto LABEL_75;
  }
  if ( msg != 514 && msg != 583 && msg != 1278 )
    return 0;
  if ( msg != 514 )
  {
    if ( msg != 583 )
    {
LABEL_8:
      if ( msg != 1278 )
        goto LABEL_30;
      goto LABEL_9;
    }
    if ( this->m_lastMessage != 583 )
      goto LABEL_30;
LABEL_20:
    v18 = CRichEditBox::ShouldNavigateLinkOnMouseClick(this, &fNavigate);
    v19 = v18;
    if ( v18 < 0 )
    {
      OnFailure_2990_(v18);
      return v19;
    }
    v7 = fNavigate;
    goto LABEL_10;
  }
  if ( this->m_lastMessage == 514 )
    goto LABEL_20;
  if ( this->m_lastMessage - 256 > 1 )
    goto LABEL_8;
LABEL_9:
  v7 = 1;
LABEL_10:
  if ( v7 && linkType == 1803 )
  {
    spContentLinkInfo.ptr_ = 0;
    Document = CTextBoxBase::GetDocument(this, (ITextDocument2 **)&spContentLinkInfo);
    v9 = Document;
    if ( Document < 0 )
    {
      OnFailure_2990_(Document);
    }
    else
    {
      v10 = pData[12];
      v11 = pData[11];
      spTextRange.ptr_ = 0;
      v12 = ((__int64 (__fastcall *)(Windows::UI::Text::IContentLinkInfo *, __int64, __int64, Microsoft::WRL::ComPtr<ITextRange> *))spContentLinkInfo.ptr_->__vftable[1].get_DisplayText)(
              spContentLinkInfo.ptr_,
              v11,
              v10,
              &spTextRange);
      v9 = v12;
      if ( v12 < 0 )
      {
        OnFailure_2990_(v12);
      }
      else
      {
        ptr = spTextRange.ptr_;
        spUri.ptr_ = 0;
        GetText = spTextRange.ptr_->GetText;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          (wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(unsigned short *),&SysFreeString,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > *)&spUri,
          0);
        v15 = GetText(ptr, (wchar_t **)&spUri);
        v9 = v15;
        if ( v15 >= 0 )
        {
          SysStringLen((BSTR)spUri.ptr_);
          v15 = DirectUI::RichEditBox::HandleHyperlinkNavigation((wchar_t *)spUri.ptr_, v16);
          v9 = v15;
          if ( v15 >= 0 )
          {
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(unsigned short *),&SysFreeString,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > *)&spUri);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&spTextRange);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&spContentLinkInfo);
            return 0;
          }
        }
        OnFailure_2990_(v15);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(unsigned short *),&SysFreeString,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > *)&spUri);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&spTextRange);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&spContentLinkInfo);
    return v9;
  }
LABEL_30:
  if ( linkType == 1822 )
  {
    v20 = pData[13];
    spContentLinkInfo.ptr_ = 0;
    ContentLinkInfo = CRichEditBox::GetContentLinkInfo(this, v20, &spContentLinkInfo.ptr_, 0, 0);
    v9 = ContentLinkInfo;
    if ( ContentLinkInfo < 0 )
    {
      OnFailure_2990_(ContentLinkInfo);
    }
    else
    {
      v22 = spContentLinkInfo.ptr_;
      if ( !spContentLinkInfo.ptr_ )
      {
LABEL_44:
        pEventMetadata.Psz = (const wchar_t *const)v22;
        make_xref<CContentLinkInvokedEventArgs,Windows::UI::Text::IContentLinkInfo *>(
          &eventArgs,
          (Windows::UI::Text::IContentLinkInfo **)&pEventMetadata);
        m_ptr = eventArgs.m_ptr;
        CEventManager::Raise(
          this->m_sharedState.m_ptr->m_value.m_coreServices->m_pEventManager,
          (EventHandle)222,
          1,
          this,
          eventArgs.m_ptr,
          1,
          0,
          1,
          0);
        if ( m_ptr->m_handled )
        {
LABEL_48:
          if ( m_ptr )
            CEventArgs::Release(m_ptr);
          v34 = spContentLinkInfo.ptr_;
          if ( spContentLinkInfo.ptr_ )
          {
            spContentLinkInfo.ptr_ = 0;
            v34->Release(v34);
          }
          return 0;
        }
        spUri.ptr_ = 0;
        v33 = spContentLinkInfo.ptr_->get_Uri(spContentLinkInfo.ptr_, (Windows::Foundation::IUriRuntimeClass **)&spUri);
        v19 = v33;
        if ( v33 >= 0 )
        {
          v33 = DirectUI::RichEditBox::HandleContentLinkNavigation(spUri.ptr_, pData[15]);
          v19 = v33;
          if ( v33 >= 0 )
          {
            ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spUri);
            goto LABEL_48;
          }
        }
        OnFailure_2990_(v33);
        ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease((ctl::ComPtr<Windows::UI::Core::ICoreWindow5> *)&spUri);
        if ( m_ptr )
          CEventArgs::Release(m_ptr);
        v35 = spContentLinkInfo.ptr_;
        if ( spContentLinkInfo.ptr_ )
        {
          spContentLinkInfo.ptr_ = 0;
          v35->Release(v35);
        }
        return v19;
      }
      spUri.ptr_ = 0;
      spTextRange.ptr_ = 0;
      get_DisplayText = spContentLinkInfo.ptr_->get_DisplayText;
      WindowsDeleteString(0);
      spUri.ptr_ = 0;
      v24 = get_DisplayText(v22, (HSTRING__ **)&spUri);
      v9 = v24;
      if ( v24 >= 0 )
      {
        v25 = spContentLinkInfo.ptr_;
        get_LinkContentKind = spContentLinkInfo.ptr_->get_LinkContentKind;
        WindowsDeleteString((HSTRING)spTextRange.ptr_);
        spTextRange.ptr_ = 0;
        v24 = get_LinkContentKind(v25, (HSTRING__ **)&spTextRange);
        v9 = v24;
        if ( v24 >= 0 )
        {
          if ( Tlgg_hTraceProviderProv.LevelPlus1 > 5 && tlgKeywordOn(&Tlgg_hTraceProviderProv, 0x400000000000uLL) )
          {
            v29 = &pressedKeys;
            if ( spTextRange.ptr_ )
              StringRawBuffer = (wchar_t *)WindowsGetStringRawBuffer((HSTRING)spTextRange.ptr_, 0);
            else
              StringRawBuffer = (wchar_t *)&pressedKeys;
            v31 = spUri.ptr_;
            eventArgs.m_ptr = (CContentLinkInvokedEventArgs *)StringRawBuffer;
            if ( spUri.ptr_ )
              v29 = WindowsGetStringRawBuffer((HSTRING)spUri.ptr_, 0);
            pEventMetadata.Psz = v29;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              (const _tlgProvider_t *)v31,
              &tlgEvent_9._tlgChannel,
              v27,
              v28,
              &pEventMetadata,
              (const _tlgWrapSz<unsigned short> *)&eventArgs);
          }
          WindowsDeleteString((HSTRING)spTextRange.ptr_);
          spTextRange.ptr_ = 0;
          WindowsDeleteString((HSTRING)spUri.ptr_);
          v22 = spContentLinkInfo.ptr_;
          goto LABEL_44;
        }
      }
      OnFailure_2990_(v24);
      WindowsDeleteString((HSTRING)spTextRange.ptr_);
      spTextRange.ptr_ = 0;
      WindowsDeleteString((HSTRING)spUri.ptr_);
      spUri.ptr_ = 0;
    }
    v36 = spContentLinkInfo.ptr_;
    if ( spContentLinkInfo.ptr_ )
    {
      spContentLinkInfo.ptr_ = 0;
      v36->Release(v36);
    }
    return v9;
  }
  return 4474182;
}

```

## disassembly

```asm
0x18082bb48  mov     [rsp-28h+arg_0], rbx
0x18082bb4d  mov     [rsp-28h+arg_8], rsi
0x18082bb52  push    rbp
0x18082bb53  push    rdi
0x18082bb54  push    r12
0x18082bb56  push    r14
0x18082bb58  push    r15
0x18082bb5a  mov     rbp, rsp
0x18082bb5d  sub     rsp, 80h
0x18082bb64  xor     r12d, r12d
0x18082bb67  mov     eax, msg
0x18082bb6a  mov     [rbp+fNavigate], r12b
0x18082bb6e  mov     r15, pData
0x18082bb71  mov     ebx, linkType
0x18082bb73  mov     rsi, this
0x18082bb76  sub     eax, 200h
0x18082bb7b  jz      loc_18082BFD7
0x18082bb81  sub     eax, 2
0x18082bb84  jz      short loc_18082BB96
0x18082bb86  sub     eax, 45h ; 'E'
0x18082bb89  jz      short loc_18082BB96
0x18082bb8b  cmp     eax, 2B7h
0x18082bb90  jnz     loc_18082BC98
0x18082bb96  mov     eax, 202h
0x18082bb9b  mov     r14d, 1
0x18082bba1  cmp     msg, eax
0x18082bba4  jnz     loc_18082BCB6
0x18082bbaa  cmp     [this+280h], eax
0x18082bbb0  jz      loc_18082BCCC
0x18082bbb6  mov     eax, [this+280h]
0x18082bbbc  sub     eax, 100h
0x18082bbc1  cmp     eax, r14d
0x18082bbc4  jbe     short loc_18082BBD3
0x18082bbc6  cmp     msg, 4FEh
0x18082bbcd  jnz     loc_18082BD32
0x18082bbd3  mov     al, r14b
0x18082bbd6  test    al, al
0x18082bbd8  jz      loc_18082BD32
0x18082bbde  cmp     ebx, 70Bh
0x18082bbe4  jnz     loc_18082BD32
0x18082bbea  lea     rdx, [rbp+spContentLinkInfo]; ppDocument
0x18082bbee  mov     [rbp+spContentLinkInfo.ptr_], r12
0x18082bbf2  mov     this, rsi; this
0x18082bbf5  call    ?GetDocument@CTextBoxBase@@QEBAJPEAPEAUITextDocument2@@@Z; CTextBoxBase::GetDocument(ITextDocument2 * *)
0x18082bbfa  mov     ebx, eax
0x18082bbfc  test    eax, eax
0x18082bbfe  js      loc_18082BD1B
0x18082bc04  mov     this, [rbp+spContentLinkInfo.ptr_]
0x18082bc08  lea     pData, [rbp+spTextRange]
0x18082bc0c  mov     msg, [r15+30h]
0x18082bc10  mov     linkType, [r15+2Ch]
0x18082bc14  mov     [rbp+spTextRange.ptr_], r12
0x18082bc18  mov     rax, [this]
0x18082bc1b  mov     rax, [rax+0C0h]
0x18082bc22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18082bc27  mov     ebx, eax
0x18082bc29  test    eax, eax
0x18082bc2b  js      loc_18082BD09
0x18082bc31  mov     rdi, [rbp+spTextRange.ptr_]
0x18082bc35  lea     this, [rbp+spUri]; this
0x18082bc39  mov     [rbp+spUri.ptr_], r12
0x18082bc3d  xor     linkType, linkType; ptr
0x18082bc3f  mov     rax, [rdi]
0x18082bc42  mov     rbx, [rax+38h]
0x18082bc46  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18082bc4b  lea     rdx, [rbp+spUri]
0x18082bc4f  mov     this, rdi
0x18082bc52  mov     rax, rbx
0x18082bc55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18082bc5a  mov     ebx, eax
0x18082bc5c  test    eax, eax
0x18082bc5e  js      loc_18082BCF7
0x18082bc64  mov     this, [rbp+spUri.ptr_]; pbstr
0x18082bc68  call    cs:__imp_SysStringLen
0x18082bc6e  mov     this, [rbp+spUri.ptr_]; pLinkText
0x18082bc72  call    ?HandleHyperlinkNavigation@RichEditBox@DirectUI@@SAJPEAGI@Z; DirectUI::RichEditBox::HandleHyperlinkNavigation(ushort *,uint)
0x18082bc77  mov     ebx, eax
0x18082bc79  test    eax, eax
0x18082bc7b  js      short loc_18082BCEE
0x18082bc7d  lea     this, [rbp+spUri]; this
0x18082bc81  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18082bc86  lea     this, [rbp+spTextRange]; this
0x18082bc8a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18082bc8f  lea     this, [rbp+spContentLinkInfo]; this
0x18082bc93  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18082bc98  xor     eax, eax
0x18082bc9a  lea     r11, [rsp+80h+var_s0]
0x18082bca2  mov     rbx, [r11+30h]
0x18082bca6  mov     rsi, [r11+38h]
0x18082bcaa  mov     rsp, r11
0x18082bcad  pop     r15
0x18082bcaf  pop     r14
0x18082bcb1  pop     r12
0x18082bcb3  pop     rdi
0x18082bcb4  pop     rbp
0x18082bcb5  retn
0x18082bcb6  mov     eax, 247h
0x18082bcbb  cmp     msg, eax
0x18082bcbe  jnz     loc_18082BBC6
0x18082bcc4  cmp     [this+280h], eax
0x18082bcca  jnz     short loc_18082BD32
0x18082bccc  lea     rdx, [rbp+fNavigate]; pfNavigate
0x18082bcd0  call    ?ShouldNavigateLinkOnMouseClick@CRichEditBox@@AEAAJPEA_N@Z; CRichEditBox::ShouldNavigateLinkOnMouseClick(bool *)
0x18082bcd5  mov     edi, eax
0x18082bcd7  test    eax, eax
0x18082bcd9  jns     short loc_18082BCE6
0x18082bcdb  mov     ecx, eax; failedFrameHR
0x18082bcdd  call    OnFailure_2990_
0x18082bce2  mov     eax, edi
0x18082bce4  jmp     short loc_18082BC9A
0x18082bce6  mov     al, [rbp+fNavigate]
0x18082bce9  jmp     loc_18082BBD6
0x18082bcee  mov     ecx, eax; failedFrameHR
0x18082bcf0  call    OnFailure_2990_
0x18082bcf5  jmp     short loc_18082BCFE
0x18082bcf7  mov     ecx, eax; failedFrameHR
0x18082bcf9  call    OnFailure_2990_
0x18082bcfe  lea     this, [rbp+spUri]; this
0x18082bd02  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18082bd07  jmp     short loc_18082BD10
0x18082bd09  mov     ecx, eax; failedFrameHR
0x18082bd0b  call    OnFailure_2990_
0x18082bd10  lea     this, [rbp+spTextRange]; this
0x18082bd14  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18082bd19  jmp     short loc_18082BD22
0x18082bd1b  mov     ecx, eax; failedFrameHR
0x18082bd1d  call    OnFailure_2990_
0x18082bd22  lea     this, [rbp+spContentLinkInfo]; this
0x18082bd26  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18082bd2b  mov     eax, ebx
0x18082bd2d  jmp     loc_18082BC9A
0x18082bd32  cmp     ebx, 71Eh
0x18082bd38  jnz     loc_18082BFCD
0x18082bd3e  mov     linkType, [r15+34h]; cpMin
0x18082bd42  lea     r8, [rbp+spContentLinkInfo]; ppContentLinkInfo
0x18082bd46  xor     r9d, r9d; pNewMax
0x18082bd49  mov     [rbp+spContentLinkInfo.ptr_], r12
0x18082bd4d  mov     this, rsi; this
0x18082bd50  mov     [rsp+80h+pNewLength], r12; pNewLength
0x18082bd55  call    ?GetContentLinkInfo@CRichEditBox@@QEAAJJPEAPEAUIContentLinkInfo@Text@UI@Windows@@PEAH1@Z; CRichEditBox::GetContentLinkInfo(long,Windows::UI::Text::IContentLinkInfo * *,int *,int *)
0x18082bd5a  mov     ebx, eax
0x18082bd5c  test    eax, eax
0x18082bd5e  js      loc_18082BFA4
0x18082bd64  mov     rbx, [rbp+spContentLinkInfo.ptr_]
0x18082bd68  test    rbx, rbx
0x18082bd6b  jz      loc_18082BE6F
0x18082bd71  mov     [rbp+spUri.ptr_], r12
0x18082bd75  xor     ecx, ecx; string
0x18082bd77  mov     [rbp+spTextRange.ptr_], r12
0x18082bd7b  mov     rax, [rbx]
0x18082bd7e  mov     rdi, [rax+40h]
0x18082bd82  call    cs:__imp_WindowsDeleteString
0x18082bd88  lea     rdx, [rbp+spUri]
0x18082bd8c  mov     [rbp+spUri.ptr_], r12
0x18082bd90  mov     this, rbx
0x18082bd93  mov     rax, rdi
0x18082bd96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18082bd9b  mov     ebx, eax
0x18082bd9d  test    eax, eax
0x18082bd9f  js      loc_18082BF37
0x18082bda5  mov     rdi, [rbp+spContentLinkInfo.ptr_]
0x18082bda9  mov     this, [rbp+spTextRange.ptr_]; string
0x18082bdad  mov     rax, [rdi]
0x18082bdb0  mov     rbx, [rax+70h]
0x18082bdb4  call    cs:__imp_WindowsDeleteString
0x18082bdba  lea     rdx, [rbp+spTextRange]
0x18082bdbe  mov     [rbp+spTextRange.ptr_], r12
0x18082bdc2  mov     this, rdi
0x18082bdc5  mov     rax, rbx
0x18082bdc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18082bdcd  mov     ebx, eax
0x18082bdcf  test    eax, eax
0x18082bdd1  js      loc_18082BF2E
0x18082bdd7  mov     eax, cs:_Tlgg_hTraceProviderProv.LevelPlus1
0x18082bddd  cmp     eax, 5
0x18082bde0  jbe     short loc_18082BE53
0x18082bde2  mov     rdx, 400000000000h; keyword
0x18082bdec  lea     this, _Tlgg_hTraceProviderProv; hProvider
0x18082bdf3  call    _tlgKeywordOn
0x18082bdf8  test    al, al
0x18082bdfa  jz      short loc_18082BE53
0x18082bdfc  mov     this, [rbp+spTextRange.ptr_]; __annotation("_TlgWrite:|557|g_hTraceProvider|"SmartLinkClicked"=|"DisplayTitle"=|"LinkType"=")
0x18082be00  lea     rbx, pressedKeys
0x18082be07  test    this, this
0x18082be0a  jz      short loc_18082BE16
0x18082be0c  xor     linkType, linkType; length
0x18082be0e  call    cs:__imp_WindowsGetStringRawBuffer
0x18082be14  jmp     short loc_18082BE19
0x18082be16  mov     rax, rbx
0x18082be19  mov     this, [rbp+spUri.ptr_]; string
0x18082be1d  mov     [rbp+eventArgs.m_ptr], rax
0x18082be21  test    this, this
0x18082be24  jz      short loc_18082BE31
0x18082be26  xor     linkType, linkType; length
0x18082be28  call    cs:__imp_WindowsGetStringRawBuffer
0x18082be2e  mov     rbx, rax
0x18082be31  lea     rax, [rbp+eventArgs]
0x18082be35  mov     [rbp+pEventMetadata.Psz], rbx
0x18082be39  mov     [rsp+80h+var_58], rax; <writerArgs_0>
0x18082be3e  lea     rdx, _tlgEvent_9._tlgChannel; <wrappedArgs_0>
0x18082be45  lea     rax, [rbp+pEventMetadata]
0x18082be49  mov     [rsp+80h+pNewLength], rax; pEventMetadata
0x18082be4e  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18082be53  mov     this, [rbp+spTextRange.ptr_]; string
0x18082be57  call    cs:__imp_WindowsDeleteString
0x18082be5d  mov     this, [rbp+spUri.ptr_]; string
0x18082be61  mov     [rbp+spTextRange.ptr_], r12
0x18082be65  call    cs:__imp_WindowsDeleteString
0x18082be6b  mov     rbx, [rbp+spContentLinkInfo.ptr_]
0x18082be6f  lea     rdx, [rbp+pEventMetadata]; <Args_0>
0x18082be73  mov     [rbp+pEventMetadata.Psz], rbx
0x18082be77  lea     this, [rbp+eventArgs]; result
0x18082be7b  call    ??$make_xref@VCContentLinkInvokedEventArgs@@PEAUIContentLinkInfo@Text@UI@Windows@@@@YA?AV?$xref_ptr@VCContentLinkInvokedEventArgs@@@@$$QEAPEAUIContentLinkInfo@Text@UI@Windows@@@Z; make_xref<CContentLinkInvokedEventArgs,Windows::UI::Text::IContentLinkInfo *>(Windows::UI::Text::IContentLinkInfo * &&)
0x18082be80  mov     rax, [rsi+10h]
0x18082be84  mov     linkType, 0DEh; hEvent
0x18082be89  mov     rbx, [rbp+eventArgs.m_ptr]
0x18082be8d  mov     pData, rsi; pSender
0x18082be90  mov     [rsp+80h+pSenderOverride], r12; pSenderOverride
0x18082be95  mov     msg, r14d; bRefire
0x18082be98  mov     [rsp+80h+bAllowErrorFallback], r14b; bAllowErrorFallback
0x18082be9d  mov     this, [rax]
0x18082bea0  mov     [rsp+80h+fInputEvent], r12b; fInputEvent
0x18082bea5  mov     byte ptr [rsp+80h+var_58], r14b; fRaiseSync
0x18082beaa  mov     [rsp+80h+pNewLength], rbx; pArgs
0x18082beaf  mov     this, [this+0E8h]; this
0x18082beb6  call    ?Raise@CEventManager@@QEAAXUEventHandle@@HPEAVCDependencyObject@@PEAVCEventArgs@@_N331@Z; CEventManager::Raise(EventHandle,int,CDependencyObject *,CEventArgs *,bool,bool,bool,CDependencyObject *)
0x18082bebb  cmp     [rbx+10h], r12b
0x18082bebf  jnz     short loc_18082BEFF
0x18082bec1  mov     this, [rbp+spContentLinkInfo.ptr_]
0x18082bec5  lea     rdx, [rbp+spUri]
0x18082bec9  mov     [rbp+spUri.ptr_], r12
0x18082becd  mov     rax, [this]
0x18082bed0  mov     rax, [rax+60h]
0x18082bed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18082bed9  mov     edi, eax
0x18082bedb  test    eax, eax
0x18082bedd  js      loc_18082BF65
0x18082bee3  mov     linkType, [r15+3Ch]; linkContentKind
0x18082bee7  mov     this, [rbp+spUri.ptr_]; pUri
0x18082beeb  call    ?HandleContentLinkNavigation@RichEditBox@DirectUI@@SAJPEAUIUriRuntimeClass@Foundation@Windows@@I@Z; DirectUI::RichEditBox::HandleContentLinkNavigation(Windows::Foundation::IUriRuntimeClass *,uint)
0x18082bef0  mov     edi, eax
0x18082bef2  test    eax, eax
0x18082bef4  js      short loc_18082BF5C
0x18082bef6  lea     this, [rbp+spUri]; this
0x18082befa  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18082beff  test    rbx, rbx
0x18082bf02  jz      short loc_18082BF0C
0x18082bf04  mov     this, rbx; this
0x18082bf07  call    ?Release@CEventArgs@@UEAAKXZ; CEventArgs::Release(void)
0x18082bf0c  mov     this, [rbp+spContentLinkInfo.ptr_]
0x18082bf10  test    this, this
0x18082bf13  jz      loc_18082BC98
0x18082bf19  mov     [rbp+spContentLinkInfo.ptr_], r12
0x18082bf1d  mov     rax, [this]
0x18082bf20  mov     rax, [rax+10h]
0x18082bf24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18082bf29  jmp     loc_18082BC98
0x18082bf2e  mov     ecx, ebx; failedFrameHR
0x18082bf30  call    OnFailure_2990_
0x18082bf35  jmp     short loc_18082BF3E
0x18082bf37  mov     ecx, ebx; failedFrameHR
0x18082bf39  call    OnFailure_2990_
0x18082bf3e  mov     this, [rbp+spTextRange.ptr_]; string
0x18082bf42  call    cs:__imp_WindowsDeleteString
0x18082bf48  mov     this, [rbp+spUri.ptr_]; string
0x18082bf4c  mov     [rbp+spTextRange.ptr_], r12
0x18082bf50  call    cs:__imp_WindowsDeleteString
0x18082bf56  mov     [rbp+spUri.ptr_], r12
0x18082bf5a  jmp     short loc_18082BFAB
0x18082bf5c  mov     ecx, edi; failedFrameHR
0x18082bf5e  call    OnFailure_2990_
0x18082bf63  jmp     short loc_18082BF6C
0x18082bf65  mov     ecx, edi; failedFrameHR
0x18082bf67  call    OnFailure_2990_
0x18082bf6c  lea     this, [rbp+spUri]; this
0x18082bf70  call    ?InternalRelease@?$ComPtr@VFlyoutMetadata@DirectUI@@@ctl@@IEAAXXZ; ctl::ComPtr<DirectUI::FlyoutMetadata>::InternalRelease(void)
0x18082bf75  test    rbx, rbx
0x18082bf78  jz      short loc_18082BF82
0x18082bf7a  mov     this, rbx; this
0x18082bf7d  call    ?Release@CEventArgs@@UEAAKXZ; CEventArgs::Release(void)
0x18082bf82  mov     this, [rbp+spContentLinkInfo.ptr_]
0x18082bf86  test    this, this
0x18082bf89  jz      loc_18082BCE2
0x18082bf8f  mov     [rbp+spContentLinkInfo.ptr_], r12
0x18082bf93  mov     rax, [this]
0x18082bf96  mov     rax, [rax+10h]
0x18082bf9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18082bf9f  jmp     loc_18082BCE2
0x18082bfa4  mov     ecx, ebx; failedFrameHR
0x18082bfa6  call    OnFailure_2990_
0x18082bfab  mov     this, [rbp+spContentLinkInfo.ptr_]
0x18082bfaf  test    this, this
0x18082bfb2  jz      loc_18082BD2B
0x18082bfb8  mov     [rbp+spContentLinkInfo.ptr_], r12
0x18082bfbc  mov     rax, [this]
0x18082bfbf  mov     rax, [rax+10h]
0x18082bfc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18082bfc8  jmp     loc_18082BD2B
0x18082bfcd  mov     eax, 444546h
0x18082bfd2  jmp     loc_18082BC9A
  ... truncated ...
```
