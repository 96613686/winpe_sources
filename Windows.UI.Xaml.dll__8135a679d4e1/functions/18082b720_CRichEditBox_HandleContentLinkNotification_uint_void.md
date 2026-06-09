# CRichEditBox::HandleContentLinkNotification(uint,void *)

- ea: `0x18082b720`
- end: `0x18082bb3f`
- name: `?HandleContentLinkNotification@CRichEditBox@@AEAAJIPEAX@Z`
- size: `1055`
- prototype: `HRESULT __fastcall(CRichEditBox *this, unsigned int notification, void *pData)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x1802a4240`

## callees

- `0x180001398`
- `0x180001f5c`
- `0x180004bc0`
- `0x180131190`
- `0x1801451c0`
- `0x18020ca40`
- `0x1806832c8`
- `0x1807540ac`
- `0x18080f1b8`
- `0x18082b3ec`
- `0x18082b564`
- `0x18082b720`
- `0x18082bb48`
- `0x18082c1a8`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18082b883`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18082b8b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18082b9fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18082ba09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18082ba4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18082ba5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18082b883`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18082b8b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18082b9fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18082ba09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18082ba4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18082ba5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18082b931`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18082b94b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18082b9b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18082b9cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18082b931`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18082b94b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18082b9b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18082b9cc`
- `OLEAUT32!__imp_SysFreeString` at `0x18082b76e`
- `OLEAUT32!__imp_SysFreeString` at `0x18082b778`
- `OLEAUT32!__imp_SysFreeString` at `0x18082bad1`
- `OLEAUT32!__imp_SysFreeString` at `0x18082badb`
- `OLEAUT32!__imp_SysFreeString` at `0x18082bb12`
- `OLEAUT32!__imp_SysFreeString` at `0x18082bb1c`
- `OLEAUT32!__imp_SysFreeString` at `0x18082b76e`
- `OLEAUT32!__imp_SysFreeString` at `0x18082b778`
- `OLEAUT32!__imp_SysFreeString` at `0x18082bad1`
- `OLEAUT32!__imp_SysFreeString` at `0x18082badb`
- `OLEAUT32!__imp_SysFreeString` at `0x18082bb12`
- `OLEAUT32!__imp_SysFreeString` at `0x18082bb1c`
- `OLEAUT32!__imp_SysStringLen` at `0x18082b916`
- `OLEAUT32!__imp_SysStringLen` at `0x18082b916`

## pseudocode

```c
__int64 __fastcall CRichEditBox::HandleContentLinkNotification(
        CRichEditBox *this,
        unsigned int notification,
        void *pData)
{
  HRESULT v6; // eax
  unsigned int v7; // esi
  HRESULT v8; // ebx
  int v10; // edx
  HRESULT ContentLinkInfo; // eax
  unsigned int v12; // ebx
  HRESULT ContentLinkTracker; // eax
  Windows::UI::Text::IContentLinkInfo *v14; // rcx
  void (*Release)(void); // rax
  ITextMarkContainer *ptr; // rdi
  HRESULT (__fastcall *RemoveTracker)(ITextMarkContainer *, int); // rbx
  int *v18; // rax
  Windows::UI::Text::IContentLinkInfo *v19; // rdi
  HRESULT (__fastcall *get_DisplayText)(Windows::UI::Text::IContentLinkInfo *, HSTRING__ **); // rbx
  HRESULT v21; // eax
  Windows::UI::Text::IContentLinkInfo *v22; // rdi
  HRESULT (__fastcall *get_LinkContentKind)(Windows::UI::Text::IContentLinkInfo *, HSTRING__ **); // rbx
  const wchar_t *v24; // rbx
  const _GUID *v25; // r8
  const _GUID *v26; // r9
  const wchar_t *StringRawBuffer; // rax
  HSTRING__ *hstr; // rcx
  const _GUID *v29; // r8
  const _GUID *v30; // r9
  const wchar_t *v31; // rbx
  const wchar_t *v32; // rax
  HSTRING__ *v33; // rcx
  CContentLinkChangedEventArgs *FailFast; // rax
  DirectUI::ContentLinkChangeKind v35; // r9d
  CEventArgs *v36; // rax
  CEventArgs *v37; // rbx
  Windows::UI::Text::IContentLinkInfo *v38; // rcx
  Windows::UI::Text::IContentLinkInfo *v39; // rcx
  Microsoft::WRL::ComPtr<Windows::UI::Text::IContentLinkInfo> spContentLinkInfo; // [rsp+50h] [rbp-30h] BYREF
  Microsoft::WRL::Wrappers::HString displayTitle; // [rsp+58h] [rbp-28h] BYREF
  Windows::UI::Xaml::Documents::TextRange textRange; // [rsp+60h] [rbp-20h]
  _tlgWrapSz<unsigned short> pEventMetadata; // [rsp+68h] [rbp-18h] BYREF
  _tlgWrapSz<unsigned short> hProvider; // [rsp+70h] [rbp-10h] BYREF
  int cpMost; // [rsp+C8h] [rbp+48h] BYREF
  _tlgWrapSz<unsigned short> length; // [rsp+D0h] [rbp+50h] BYREF
  Microsoft::WRL::Wrappers::HString linkType; // [rsp+D8h] [rbp+58h] BYREF

  if ( notification == 1822 )
  {
    v6 = CRichEditBox::HandleLinkNavigation(this, 0x71Eu, *((_DWORD *)pData + 6), (unsigned int *)pData);
    v7 = 0;
    v8 = v6;
    if ( v6 < 0 )
    {
      OnFailure_2990_(v6);
      v7 = v8;
    }
    SysFreeString(*((BSTR *)pData + 10));
    SysFreeString(*((BSTR *)pData + 9));
    return v7;
  }
  v10 = *((_DWORD *)pData + 13);
  cpMost = 0;
  LODWORD(length.Psz) = 0;
  spContentLinkInfo.ptr_ = 0;
  ContentLinkInfo = CRichEditBox::GetContentLinkInfo(this, v10, &spContentLinkInfo.ptr_, &cpMost, (int *)&length);
  v12 = ContentLinkInfo;
  if ( ContentLinkInfo < 0 )
    goto LABEL_42;
  if ( notification != 1823 )
  {
    ptr = this->m_spTextMarkContainer.ptr_;
    LODWORD(linkType.hstr_) = *((_DWORD *)pData + 16);
    RemoveTracker = ptr->RemoveTracker;
    v18 = containers::vector_map<unsigned int,int,std::less<void>,std::allocator<std::pair<unsigned int,int>>>::operator[](
            &this->m_contentLinkTrackers,
            (unsigned int *)&linkType);
    ContentLinkInfo = RemoveTracker(ptr, *v18);
    v12 = ContentLinkInfo;
    if ( ContentLinkInfo >= 0 )
    {
      LODWORD(linkType.hstr_) = *((_DWORD *)pData + 16);
      containers::detail::vector_tree<containers::detail::map_traits<unsigned int,int,std::less<void>,std::allocator<std::pair<unsigned int,int>>,0>>::erase(
        &this->m_contentLinkTrackers,
        (const unsigned int *)&linkType);
      goto LABEL_12;
    }
LABEL_42:
    OnFailure_2990_(ContentLinkInfo);
    goto LABEL_43;
  }
  ContentLinkTracker = CRichEditBox::CreateContentLinkTracker(
                         this,
                         *((_DWORD *)pData + 16),
                         *((_DWORD *)pData + 13),
                         cpMost);
  v12 = ContentLinkTracker;
  if ( ContentLinkTracker < 0 )
  {
    OnFailure_2990_(ContentLinkTracker);
    v14 = spContentLinkInfo.ptr_;
    if ( spContentLinkInfo.ptr_ )
    {
      spContentLinkInfo.ptr_ = 0;
      Release = (void (*)(void))v14->Release;
LABEL_45:
      Release();
      goto LABEL_46;
    }
    goto LABEL_46;
  }
LABEL_12:
  v19 = spContentLinkInfo.ptr_;
  textRange.StartIndex = *((_DWORD *)pData + 13);
  textRange.Length = (int)length.Psz;
  if ( spContentLinkInfo.ptr_ )
  {
    displayTitle.hstr_ = 0;
    linkType.hstr_ = 0;
    get_DisplayText = spContentLinkInfo.ptr_->get_DisplayText;
    WindowsDeleteString(0);
    displayTitle.hstr_ = 0;
    v21 = get_DisplayText(v19, &displayTitle.hstr_);
    v12 = v21;
    if ( v21 >= 0 )
    {
      v22 = spContentLinkInfo.ptr_;
      get_LinkContentKind = spContentLinkInfo.ptr_->get_LinkContentKind;
      WindowsDeleteString(linkType.hstr_);
      linkType.hstr_ = 0;
      v21 = get_LinkContentKind(v22, &linkType.hstr_);
      v12 = v21;
      if ( v21 >= 0 )
      {
        if ( notification == 1823 )
        {
          if ( Tlgg_hTraceProviderProv.LevelPlus1 > 5 && tlgKeywordOn(&Tlgg_hTraceProviderProv, 0x400000000000uLL) )
          {
            v24 = &pressedKeys;
            LODWORD(length.Psz) = SysStringLen(*((BSTR *)pData + 9));
            if ( linkType.hstr_ )
              StringRawBuffer = WindowsGetStringRawBuffer(linkType.hstr_, 0);
            else
              StringRawBuffer = &pressedKeys;
            hstr = displayTitle.hstr_;
            pEventMetadata.Psz = StringRawBuffer;
            if ( displayTitle.hstr_ )
              v24 = WindowsGetStringRawBuffer(displayTitle.hstr_, 0);
            hProvider.Psz = v24;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              (const _tlgProvider_t *)hstr,
              &tlgEvent_8._tlgChannel,
              v25,
              v26,
              &hProvider,
              &pEventMetadata,
              (const _tlgWrapperByVal<4> *)&length);
          }
        }
        else if ( Tlgg_hTraceProviderProv.LevelPlus1 > 5 && tlgKeywordOn(&Tlgg_hTraceProviderProv, 0x400000000000uLL) )
        {
          v31 = &pressedKeys;
          if ( linkType.hstr_ )
            v32 = WindowsGetStringRawBuffer(linkType.hstr_, 0);
          else
            v32 = &pressedKeys;
          v33 = displayTitle.hstr_;
          length.Psz = v32;
          if ( displayTitle.hstr_ )
            v31 = WindowsGetStringRawBuffer(displayTitle.hstr_, 0);
          hProvider.Psz = v31;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            (const _tlgProvider_t *)v33,
            &tlgEvent_7._tlgChannel,
            v29,
            v30,
            &hProvider,
            &length);
        }
        WindowsDeleteString(linkType.hstr_);
        linkType.hstr_ = 0;
        WindowsDeleteString(displayTitle.hstr_);
        v19 = spContentLinkInfo.ptr_;
        goto LABEL_33;
      }
    }
    OnFailure_2990_(v21);
    WindowsDeleteString(linkType.hstr_);
    linkType.hstr_ = 0;
    WindowsDeleteString(displayTitle.hstr_);
    displayTitle.hstr_ = 0;
LABEL_43:
    v39 = spContentLinkInfo.ptr_;
    if ( spContentLinkInfo.ptr_ )
    {
      spContentLinkInfo.ptr_ = 0;
      Release = (void (*)(void))v39->Release;
      goto LABEL_45;
    }
LABEL_46:
    SysFreeString(*((BSTR *)pData + 10));
    SysFreeString(*((BSTR *)pData + 9));
    return v12;
  }
LABEL_33:
  FailFast = (CContentLinkChangedEventArgs *)XcpAllocation::OSMemoryAllocateFailFast(0x28u);
  if ( FailFast )
  {
    LOBYTE(v35) = notification != 1823;
    CContentLinkChangedEventArgs::CContentLinkChangedEventArgs(FailFast, v19, textRange, v35);
    v37 = v36;
  }
  else
  {
    v37 = 0;
  }
  CEventManager::Raise(
    this->m_sharedState.m_ptr->m_value.m_coreServices->m_pEventManager,
    (EventHandle)221,
    1,
    this,
    v37,
    1,
    0,
    1,
    0);
  if ( v37 )
    CEventArgs::Release(v37);
  v38 = spContentLinkInfo.ptr_;
  if ( spContentLinkInfo.ptr_ )
  {
    spContentLinkInfo.ptr_ = 0;
    v38->Release(v38);
  }
  SysFreeString(*((BSTR *)pData + 10));
  SysFreeString(*((BSTR *)pData + 9));
  return 0;
}

```

## disassembly

```asm
0x18082b720  mov     [rsp-38h+arg_0], rbx
0x18082b725  push    rbp
0x18082b726  push    rsi
0x18082b727  push    rdi
0x18082b728  push    r12
0x18082b72a  push    r13
0x18082b72c  push    r14
0x18082b72e  push    r15
0x18082b730  mov     rbp, rsp
0x18082b733  sub     rsp, 80h
0x18082b73a  mov     r15d, notification
0x18082b73d  mov     r14, pData
0x18082b740  mov     notification, 71Eh; linkType
0x18082b745  mov     r13, this
0x18082b748  cmp     r15d, notification
0x18082b74b  jnz     short loc_18082B785
0x18082b74d  mov     r9, pData; pData
0x18082b750  mov     r8d, [pData+18h]; msg
0x18082b754  call    ?HandleLinkNavigation@CRichEditBox@@AEAAJIIPEAX@Z; CRichEditBox::HandleLinkNavigation(uint,uint,void *)
0x18082b759  xor     esi, esi
0x18082b75b  mov     ebx, eax
0x18082b75d  test    eax, eax
0x18082b75f  jns     short loc_18082B76A
0x18082b761  mov     ecx, eax; failedFrameHR
0x18082b763  call    OnFailure_2990_
0x18082b768  mov     esi, ebx
0x18082b76a  mov     this, [r14+50h]; bstrString
0x18082b76e  call    cs:__imp_SysFreeString
0x18082b774  mov     this, [r14+48h]; bstrString
0x18082b778  call    cs:__imp_SysFreeString
0x18082b77e  mov     eax, esi
0x18082b780  jmp     loc_18082BB24
0x18082b785  mov     notification, [r14+34h]; cpMin
0x18082b789  lea     rax, [rbp+length]
0x18082b78d  xor     esi, esi
0x18082b78f  mov     [rsp+80h+pNewLength], rax; pNewLength
0x18082b794  lea     r9, [rbp+cpMost]; pNewMax
0x18082b798  mov     [rbp+cpMost], esi
0x18082b79b  lea     pData, [rbp+spContentLinkInfo]; ppContentLinkInfo
0x18082b79f  mov     dword ptr [rbp+length], esi
0x18082b7a2  mov     [rbp+spContentLinkInfo.ptr_], rsi
0x18082b7a6  call    ?GetContentLinkInfo@CRichEditBox@@QEAAJJPEAPEAUIContentLinkInfo@Text@UI@Windows@@PEAH1@Z; CRichEditBox::GetContentLinkInfo(long,Windows::UI::Text::IContentLinkInfo * *,int *,int *)
0x18082b7ab  mov     ebx, eax
0x18082b7ad  test    eax, eax
0x18082b7af  js      loc_18082BAEE
0x18082b7b5  mov     notification, [r14+40h]; contentLinkId
0x18082b7b9  cmp     r15d, 71Fh
0x18082b7c0  jnz     short loc_18082B7FC
0x18082b7c2  mov     r9d, [rbp+cpMost]; cpMax
0x18082b7c6  mov     this, r13; this
0x18082b7c9  mov     r8d, [r14+34h]; cpMin
0x18082b7cd  call    ?CreateContentLinkTracker@CRichEditBox@@AEAAJIII@Z; CRichEditBox::CreateContentLinkTracker(uint,uint,uint)
0x18082b7d2  mov     ebx, eax
0x18082b7d4  test    eax, eax
0x18082b7d6  jns     short loc_18082B84D
0x18082b7d8  mov     ecx, eax; failedFrameHR
0x18082b7da  call    OnFailure_2990_
0x18082b7df  mov     this, [rbp+spContentLinkInfo.ptr_]
0x18082b7e3  test    this, this
0x18082b7e6  jz      loc_18082BB0E
0x18082b7ec  mov     [rbp+spContentLinkInfo.ptr_], rsi
0x18082b7f0  mov     rdx, [this]
0x18082b7f3  mov     rax, [rdx+10h]
0x18082b7f7  jmp     loc_18082BB09
0x18082b7fc  mov     rdi, [r13+2A8h]
0x18082b803  lea     r12, [r13+430h]
0x18082b80a  mov     dword ptr [rbp+linkType.hstr_], notification
0x18082b80d  mov     this, r12; this
0x18082b810  lea     rdx, [rbp+linkType]; key
0x18082b814  mov     rax, [rdi]
0x18082b817  mov     rbx, [rax+0A8h]
0x18082b81e  call    ??A?$vector_map@IHU?$less@X@std@@V?$allocator@U?$pair@IH@std@@@2@@containers@@QEAAAEAH$$QEAI@Z; containers::vector_map<uint,int,std::less<void>,std::allocator<std::pair<uint,int>>>::operator[](uint &&)
0x18082b823  mov     this, rdi
0x18082b826  mov     notification, [rax]
0x18082b828  mov     rax, rbx
0x18082b82b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18082b830  mov     ebx, eax
0x18082b832  test    eax, eax
0x18082b834  js      loc_18082BAE5
0x18082b83a  mov     eax, [r14+40h]
0x18082b83e  lea     rdx, [rbp+linkType]; key
0x18082b842  mov     this, r12; this
0x18082b845  mov     dword ptr [rbp+linkType.hstr_], eax
0x18082b848  call    ?erase@?$vector_tree@U?$map_traits@IHU?$less@X@std@@V?$allocator@U?$pair@IH@std@@@2@$0A@@detail@containers@@@detail@containers@@QEAA_KAEBI@Z; containers::detail::vector_tree<containers::detail::map_traits<uint,int,std::less<void>,std::allocator<std::pair<uint,int>>,0>>::erase(uint const &)
0x18082b84d  mov     eax, [r14+34h]
0x18082b851  cmp     r15d, 71Fh
0x18082b858  mov     rdi, [rbp+spContentLinkInfo.ptr_]
0x18082b85c  setnz   r12b
0x18082b860  mov     [rbp+textRange.StartIndex], eax
0x18082b863  mov     eax, dword ptr [rbp+length]
0x18082b866  mov     [rbp+textRange.Length], eax
0x18082b869  test    rdi, rdi
0x18082b86c  jz      loc_18082BA13
0x18082b872  mov     [rbp+displayTitle.hstr_], rsi
0x18082b876  xor     ecx, ecx; string
0x18082b878  mov     [rbp+linkType.hstr_], rsi
0x18082b87c  mov     rax, [rdi]
0x18082b87f  mov     rbx, [rax+40h]
0x18082b883  call    cs:__imp_WindowsDeleteString
0x18082b889  lea     rdx, [rbp+displayTitle]
0x18082b88d  mov     [rbp+displayTitle.hstr_], rsi
0x18082b891  mov     this, rdi
0x18082b894  mov     rax, rbx
0x18082b897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18082b89c  mov     ebx, eax
0x18082b89e  test    eax, eax
0x18082b8a0  js      loc_18082BA42
0x18082b8a6  mov     rdi, [rbp+spContentLinkInfo.ptr_]
0x18082b8aa  mov     this, [rbp+linkType.hstr_]; string
0x18082b8ae  mov     rax, [rdi]
0x18082b8b1  mov     rbx, [rax+70h]
0x18082b8b5  call    cs:__imp_WindowsDeleteString
0x18082b8bb  lea     rdx, [rbp+linkType]
0x18082b8bf  mov     [rbp+linkType.hstr_], rsi
0x18082b8c3  mov     this, rdi
0x18082b8c6  mov     rax, rbx
0x18082b8c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18082b8ce  mov     ebx, eax
0x18082b8d0  test    eax, eax
0x18082b8d2  js      loc_18082BA39
0x18082b8d8  mov     eax, cs:_Tlgg_hTraceProviderProv.LevelPlus1
0x18082b8de  cmp     r15d, 71Fh
0x18082b8e5  jnz     loc_18082B981
0x18082b8eb  cmp     eax, 5
0x18082b8ee  jbe     loc_18082B9F7
0x18082b8f4  mov     rdx, 400000000000h; keyword
0x18082b8fe  lea     this, _Tlgg_hTraceProviderProv; hProvider
0x18082b905  call    _tlgKeywordOn
0x18082b90a  test    al, al
0x18082b90c  jz      loc_18082B9F7
0x18082b912  mov     this, [r14+48h]; __annotation("_TlgWrite:|704|g_hTraceProvider|"SmartLinkCreated"=|"DisplayTitle"=|"LinkType"=|"LinkLength"=")
0x18082b916  call    cs:__imp_SysStringLen
0x18082b91c  mov     this, [rbp+linkType.hstr_]; string
0x18082b920  lea     rbx, pressedKeys
0x18082b927  mov     dword ptr [rbp+length], eax
0x18082b92a  test    this, this
0x18082b92d  jz      short loc_18082B939
0x18082b92f  xor     notification, notification; length
0x18082b931  call    cs:__imp_WindowsGetStringRawBuffer
0x18082b937  jmp     short loc_18082B93C
0x18082b939  mov     rax, rbx
0x18082b93c  mov     this, [rbp+displayTitle.hstr_]; string
0x18082b940  mov     [rbp+var_18.Psz], rax
0x18082b944  test    this, this
0x18082b947  jz      short loc_18082B954
0x18082b949  xor     notification, notification; length
0x18082b94b  call    cs:__imp_WindowsGetStringRawBuffer
0x18082b951  mov     rbx, rax
0x18082b954  lea     rax, [rbp+length]
0x18082b958  mov     [rbp+hProvider.Psz], rbx
0x18082b95c  mov     [rsp+80h+var_50], rax; <writerArgs_0>
0x18082b961  lea     rdx, _tlgEvent_8._tlgChannel; <wrappedArgs_0>
0x18082b968  lea     rax, [rbp+var_18]
0x18082b96c  mov     [rsp+80h+pEventMetadata], rax; pEventMetadata
0x18082b971  lea     rax, [rbp+hProvider]
0x18082b975  mov     [rsp+80h+pNewLength], rax; hProvider
0x18082b97a  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18082b97f  jmp     short loc_18082B9F7
0x18082b981  cmp     eax, 5
0x18082b984  jbe     short loc_18082B9F7
0x18082b986  mov     rdx, 400000000000h; keyword
0x18082b990  lea     this, _Tlgg_hTraceProviderProv; hProvider
0x18082b997  call    _tlgKeywordOn
0x18082b99c  test    al, al
0x18082b99e  jz      short loc_18082B9F7
0x18082b9a0  mov     this, [rbp+linkType.hstr_]; __annotation("_TlgWrite:|712|g_hTraceProvider|"SmartLinkDeleted"=|"DisplayTitle"=|"LinkType"=")
0x18082b9a4  lea     rbx, pressedKeys
0x18082b9ab  test    this, this
0x18082b9ae  jz      short loc_18082B9BA
0x18082b9b0  xor     notification, notification; length
0x18082b9b2  call    cs:__imp_WindowsGetStringRawBuffer
0x18082b9b8  jmp     short loc_18082B9BD
0x18082b9ba  mov     rax, rbx
0x18082b9bd  mov     this, [rbp+displayTitle.hstr_]; string
0x18082b9c1  mov     [rbp+length], rax
0x18082b9c5  test    this, this
0x18082b9c8  jz      short loc_18082B9D5
0x18082b9ca  xor     notification, notification; length
0x18082b9cc  call    cs:__imp_WindowsGetStringRawBuffer
0x18082b9d2  mov     rbx, rax
0x18082b9d5  lea     rax, [rbp+length]
0x18082b9d9  mov     [rbp+hProvider.Psz], rbx
0x18082b9dd  mov     [rsp+80h+pEventMetadata], rax; <writerArgs_0>
0x18082b9e2  lea     rdx, _tlgEvent_7._tlgChannel; <wrappedArgs_0>
0x18082b9e9  lea     rax, [rbp+hProvider]
0x18082b9ed  mov     [rsp+80h+pNewLength], rax; pEventMetadata
0x18082b9f2  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18082b9f7  mov     this, [rbp+linkType.hstr_]; string
0x18082b9fb  call    cs:__imp_WindowsDeleteString
0x18082ba01  mov     this, [rbp+displayTitle.hstr_]; string
0x18082ba05  mov     [rbp+linkType.hstr_], rsi
0x18082ba09  call    cs:__imp_WindowsDeleteString
0x18082ba0f  mov     rdi, [rbp+spContentLinkInfo.ptr_]
0x18082ba13  mov     ecx, 28h ; '('; cSize
0x18082ba18  call    ?OSMemoryAllocateFailFast@XcpAllocation@@YAPEAX_K@Z; XcpAllocation::OSMemoryAllocateFailFast(unsigned __int64)
0x18082ba1d  test    rax, rax
0x18082ba20  jz      short loc_18082BA6A
0x18082ba22  mov     pData, qword ptr [rbp+textRange.StartIndex]; textRange
0x18082ba26  mov     r9b, r12b; changeKind
0x18082ba29  mov     rdx, rdi; contentLinkInfo
0x18082ba2c  mov     this, rax; this
0x18082ba2f  call    ??0CContentLinkChangedEventArgs@@QEAA@PEAUIContentLinkInfo@Text@UI@Windows@@UTextRange@Documents@Xaml@34@W4ContentLinkChangeKind@DirectUI@@@Z; CContentLinkChangedEventArgs::CContentLinkChangedEventArgs(Windows::UI::Text::IContentLinkInfo *,Windows::UI::Xaml::Documents::TextRange,DirectUI::ContentLinkChangeKind)
0x18082ba34  mov     rbx, rax
0x18082ba37  jmp     short loc_18082BA6D
0x18082ba39  mov     ecx, eax; failedFrameHR
0x18082ba3b  call    OnFailure_2990_
0x18082ba40  jmp     short loc_18082BA49
0x18082ba42  mov     ecx, eax; failedFrameHR
0x18082ba44  call    OnFailure_2990_
0x18082ba49  mov     this, [rbp+linkType.hstr_]; string
0x18082ba4d  call    cs:__imp_WindowsDeleteString
0x18082ba53  mov     this, [rbp+displayTitle.hstr_]; string
0x18082ba57  mov     [rbp+linkType.hstr_], rsi
0x18082ba5b  call    cs:__imp_WindowsDeleteString
0x18082ba61  mov     [rbp+displayTitle.hstr_], rsi
0x18082ba65  jmp     loc_18082BAF5
0x18082ba6a  mov     rbx, rsi
0x18082ba6d  mov     rax, [r13+10h]
0x18082ba71  mov     notification, 0DDh; hEvent
0x18082ba76  mov     [rsp+80h+pSenderOverride], rsi; pSenderOverride
0x18082ba7b  mov     r9, r13; pSender
0x18082ba7e  mov     [rsp+80h+bAllowErrorFallback], 1; bAllowErrorFallback
0x18082ba83  mov     r8d, 1; bRefire
0x18082ba89  mov     byte ptr [rsp+80h+var_50], sil; fInputEvent
0x18082ba8e  mov     this, [rax]
0x18082ba91  mov     byte ptr [rsp+80h+pEventMetadata], 1; fRaiseSync
0x18082ba96  mov     [rsp+80h+pNewLength], rbx; pArgs
0x18082ba9b  mov     this, [this+0E8h]; this
0x18082baa2  call    ?Raise@CEventManager@@QEAAXUEventHandle@@HPEAVCDependencyObject@@PEAVCEventArgs@@_N331@Z; CEventManager::Raise(EventHandle,int,CDependencyObject *,CEventArgs *,bool,bool,bool,CDependencyObject *)
0x18082baa7  test    rbx, rbx
0x18082baaa  jz      short loc_18082BAB4
0x18082baac  mov     this, rbx; this
0x18082baaf  call    ?Release@CEventArgs@@UEAAKXZ; CEventArgs::Release(void)
0x18082bab4  mov     this, [rbp+spContentLinkInfo.ptr_]
0x18082bab8  test    this, this
0x18082babb  jz      short loc_18082BACD
0x18082babd  mov     [rbp+spContentLinkInfo.ptr_], rsi
0x18082bac1  mov     rax, [this]
0x18082bac4  mov     rax, [rax+10h]
0x18082bac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18082bacd  mov     this, [r14+50h]; bstrString
0x18082bad1  call    cs:__imp_SysFreeString
0x18082bad7  mov     this, [r14+48h]; bstrString
0x18082badb  call    cs:__imp_SysFreeString
0x18082bae1  xor     eax, eax
0x18082bae3  jmp     short loc_18082BB24
0x18082bae5  mov     ecx, eax; failedFrameHR
0x18082bae7  call    OnFailure_2990_
0x18082baec  jmp     short loc_18082BAF5
0x18082baee  mov     ecx, ebx; failedFrameHR
0x18082baf0  call    OnFailure_2990_
0x18082baf5  mov     this, [rbp+spContentLinkInfo.ptr_]
0x18082baf9  test    this, this
0x18082bafc  jz      short loc_18082BB0E
0x18082bafe  mov     [rbp+spContentLinkInfo.ptr_], rsi
0x18082bb02  mov     rax, [this]
0x18082bb05  mov     rax, [rax+10h]
0x18082bb09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18082bb0e  mov     this, [r14+50h]; bstrString
0x18082bb12  call    cs:__imp_SysFreeString
0x18082bb18  mov     this, [r14+48h]; bstrString
0x18082bb1c  call    cs:__imp_SysFreeString
0x18082bb22  mov     eax, ebx
0x18082bb24  mov     rbx, [rsp+80h+arg_0]
0x18082bb2c  add     rsp, 80h
0x18082bb33  pop     r15
0x18082bb35  pop     r14
0x18082bb37  pop     r13
0x18082bb39  pop     r12
0x18082bb3b  pop     rdi
0x18082bb3c  pop     rsi
0x18082bb3d  pop     rbp
0x18082bb3e  retn
```
