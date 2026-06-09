# TrackerEventHandler(CTextTracker *,RichEditEvent::EVENTID)

- ea: `0x180813bd0`
- end: `0x180813e6d`
- name: `?TrackerEventHandler@@YAJPEAVCTextTracker@@W4EVENTID@RichEditEvent@@@Z`
- size: `669`
- prototype: `HRESULT __fastcall(CTextTracker *pTextTracker, RichEditEvent::EVENTID id)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001398`
- `0x180004bc0`
- `0x180131190`
- `0x1801451c0`
- `0x18020ca40`
- `0x180272e94`
- `0x1806832c8`
- `0x1807540ac`
- `0x18080f0b4`
- `0x18080f1b8`
- `0x180813bd0`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180813c87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180813cb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180813dde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180813dec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180813e2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180813e3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180813c87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180813cb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180813dde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180813dec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180813e2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180813e3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180813d13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180813d2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180813d13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180813d2d`

## pseudocode

```c
__int64 __fastcall TrackerEventHandler(CTextTracker *pTextTracker, RichEditEvent::EVENTID id)
{
  xref::details::control_block *m_ref_count; // rax
  CTextBoxBase *m_ptr; // rsi
  int m_cpChangeMin; // edi
  CRichEditBox *v6; // rax
  HRESULT ContentLinkInfo; // eax
  unsigned int v8; // ebx
  Windows::UI::Text::IContentLinkInfo *ptr; // rdi
  HRESULT (__fastcall *get_DisplayText)(Windows::UI::Text::IContentLinkInfo *, HSTRING__ **); // rbx
  HRESULT v11; // eax
  Windows::UI::Text::IContentLinkInfo *v12; // rdi
  HRESULT (__fastcall *get_LinkContentKind)(Windows::UI::Text::IContentLinkInfo *, HSTRING__ **); // rbx
  const _GUID *v14; // r8
  const _GUID *v15; // r9
  const wchar_t *v16; // rbx
  const wchar_t *StringRawBuffer; // rax
  HSTRING__ *hstr; // rcx
  Windows::UI::Text::IContentLinkInfo *v19; // rbx
  CContentLinkChangedEventArgs *FailFast; // rax
  DirectUI::ContentLinkChangeKind v21; // r9d
  CEventArgs *v22; // rax
  CEventArgs *v23; // rbx
  Windows::UI::Text::IContentLinkInfo *v24; // rdi
  Windows::UI::Text::IContentLinkInfo *v26; // rcx
  Microsoft::WRL::Wrappers::HString displayTitle; // [rsp+50h] [rbp-20h] BYREF
  _tlgWrapSz<unsigned short> v28; // [rsp+58h] [rbp-18h] BYREF
  _tlgWrapSz<unsigned short> pEventMetadata; // [rsp+60h] [rbp-10h] BYREF
  Windows::UI::Xaml::Documents::TextRange textRange; // [rsp+A0h] [rbp+30h] BYREF
  int cpNewMost; // [rsp+A8h] [rbp+38h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Text::IContentLinkInfo> spContentLinkInfo; // [rsp+B0h] [rbp+40h] BYREF
  Microsoft::WRL::Wrappers::HString linkType; // [rsp+B8h] [rbp+48h] BYREF

  m_ref_count = pTextTracker->m_spOwnerWeakRef.m_ref_count;
  if ( m_ref_count && (m_ref_count->m_destroying || m_ref_count->m_strong._Storage._Value) )
    m_ptr = pTextTracker->m_spOwnerWeakRef.m_ptr;
  else
    m_ptr = 0;
  if ( id != EVENTID_TRACKER_CPCHANGE || !CDependencyObject::OfTypeByIndex<778>(m_ptr) )
    return 0;
  m_cpChangeMin = pTextTracker->m_cpChangeMin;
  cpNewMost = 0;
  textRange.StartIndex = 0;
  spContentLinkInfo.ptr_ = 0;
  if ( m_cpChangeMin <= -1 )
    m_cpChangeMin = pTextTracker->m_cpMin;
  else
    pTextTracker->m_cpChangeMin = -1;
  v6 = do_pointer_cast<CRichEditBox>(m_ptr);
  ContentLinkInfo = CRichEditBox::GetContentLinkInfo(
                      v6,
                      m_cpChangeMin,
                      &spContentLinkInfo.ptr_,
                      &cpNewMost,
                      (int *)&textRange);
  v8 = ContentLinkInfo;
  if ( ContentLinkInfo < 0 )
  {
    OnFailure_2990_(ContentLinkInfo);
    goto LABEL_33;
  }
  ptr = spContentLinkInfo.ptr_;
  if ( !spContentLinkInfo.ptr_ )
    return 0;
  displayTitle.hstr_ = 0;
  linkType.hstr_ = 0;
  get_DisplayText = spContentLinkInfo.ptr_->get_DisplayText;
  WindowsDeleteString(0);
  displayTitle.hstr_ = 0;
  v11 = get_DisplayText(ptr, &displayTitle.hstr_);
  v8 = v11;
  if ( v11 >= 0 )
  {
    v12 = spContentLinkInfo.ptr_;
    get_LinkContentKind = spContentLinkInfo.ptr_->get_LinkContentKind;
    WindowsDeleteString(linkType.hstr_);
    linkType.hstr_ = 0;
    v11 = get_LinkContentKind(v12, &linkType.hstr_);
    v8 = v11;
    if ( v11 >= 0 )
    {
      if ( Tlgg_hTraceProviderProv.LevelPlus1 > 5 && tlgKeywordOn(&Tlgg_hTraceProviderProv, 0x400000000000uLL) )
      {
        v16 = &pressedKeys;
        if ( linkType.hstr_ )
          StringRawBuffer = WindowsGetStringRawBuffer(linkType.hstr_, 0);
        else
          StringRawBuffer = &pressedKeys;
        hstr = displayTitle.hstr_;
        v28.Psz = StringRawBuffer;
        if ( displayTitle.hstr_ )
          v16 = WindowsGetStringRawBuffer(displayTitle.hstr_, 0);
        pEventMetadata.Psz = v16;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (const _tlgProvider_t *)hstr,
          &tlgEvent_6._tlgChannel,
          v14,
          v15,
          &pEventMetadata,
          &v28);
      }
      v19 = spContentLinkInfo.ptr_;
      textRange.Length = textRange.StartIndex;
      textRange.StartIndex = cpNewMost - textRange.StartIndex;
      FailFast = (CContentLinkChangedEventArgs *)XcpAllocation::OSMemoryAllocateFailFast(0x28u);
      if ( FailFast )
      {
        LOBYTE(v21) = 2;
        CContentLinkChangedEventArgs::CContentLinkChangedEventArgs(FailFast, v19, textRange, v21);
        v23 = v22;
      }
      else
      {
        v23 = 0;
      }
      CEventManager::Raise(
        m_ptr->m_sharedState.m_ptr->m_value.m_coreServices->m_pEventManager,
        (EventHandle)221,
        1,
        m_ptr,
        v23,
        1,
        0,
        1,
        0);
      if ( v23 )
        CEventArgs::Release(v23);
      WindowsDeleteString(linkType.hstr_);
      linkType.hstr_ = 0;
      WindowsDeleteString(displayTitle.hstr_);
      v24 = spContentLinkInfo.ptr_;
      if ( spContentLinkInfo.ptr_ )
      {
        spContentLinkInfo.ptr_ = 0;
        v24->Release(v24);
      }
      return 0;
    }
  }
  OnFailure_2990_(v11);
  WindowsDeleteString(linkType.hstr_);
  linkType.hstr_ = 0;
  WindowsDeleteString(displayTitle.hstr_);
  displayTitle.hstr_ = 0;
LABEL_33:
  v26 = spContentLinkInfo.ptr_;
  if ( spContentLinkInfo.ptr_ )
  {
    spContentLinkInfo.ptr_ = 0;
    v26->Release(v26);
  }
  return v8;
}

```

## disassembly

```asm
0x180813bd0  push    rbp
0x180813bd2  push    rbx
0x180813bd3  push    rsi
0x180813bd4  push    rdi
0x180813bd5  push    r14
0x180813bd7  mov     rbp, rsp
0x180813bda  sub     rsp, 70h
0x180813bde  mov     rax, [pTextTracker+28h]
0x180813be2  xor     r14d, r14d
0x180813be5  mov     rbx, pTextTracker
0x180813be8  test    rax, rax
0x180813beb  jz      short loc_180813C00
0x180813bed  cmp     [rax+8], r14b
0x180813bf1  jnz     short loc_180813BFA
0x180813bf3  mov     eax, [rax]
0x180813bf5  nop
0x180813bf6  test    eax, eax
0x180813bf8  jz      short loc_180813C00
0x180813bfa  mov     rsi, [pTextTracker+20h]
0x180813bfe  jmp     short loc_180813C03
0x180813c00  mov     rsi, r14
0x180813c03  cmp     id, 4
0x180813c06  jnz     loc_180813E0E
0x180813c0c  mov     pTextTracker, rsi; this
0x180813c0f  call    ??$OfTypeByIndex@$0DAK@@CDependencyObject@@QEBA_NXZ; CDependencyObject::OfTypeByIndex<778>(void)
0x180813c14  test    al, al
0x180813c16  jz      loc_180813E0E
0x180813c1c  mov     edi, [rbx+3Ch]
0x180813c1f  mov     [rbp+cpNewMost], r14d
0x180813c23  mov     [rbp+textRange.StartIndex], r14d
0x180813c27  mov     [rbp+spContentLinkInfo.ptr_], r14
0x180813c2b  cmp     edi, 0FFFFFFFFh
0x180813c2e  jle     short loc_180813C39
0x180813c30  mov     dword ptr [rbx+3Ch], 0FFFFFFFFh
0x180813c37  jmp     short loc_180813C3C
0x180813c39  mov     edi, [rbx+34h]
0x180813c3c  mov     pTextTracker, rsi; pDO
0x180813c3f  call    ??$do_pointer_cast@VCRichEditBox@@@@YAPEAVCRichEditBox@@PEAVCDependencyObject@@@Z; do_pointer_cast<CRichEditBox>(CDependencyObject *)
0x180813c44  lea     pTextTracker, [rbp+textRange]
0x180813c48  mov     id, edi; cpMin
0x180813c4a  mov     [rsp+70h+pNewLength], pTextTracker; pNewLength
0x180813c4f  lea     r9, [rbp+cpNewMost]; pNewMax
0x180813c53  mov     pTextTracker, rax; this
0x180813c56  lea     r8, [rbp+spContentLinkInfo]; ppContentLinkInfo
0x180813c5a  call    ?GetContentLinkInfo@CRichEditBox@@QEAAJJPEAPEAUIContentLinkInfo@Text@UI@Windows@@PEAH1@Z; CRichEditBox::GetContentLinkInfo(long,Windows::UI::Text::IContentLinkInfo * *,int *,int *)
0x180813c5f  mov     ebx, eax
0x180813c61  test    eax, eax
0x180813c63  js      loc_180813E49
0x180813c69  mov     rdi, [rbp+spContentLinkInfo.ptr_]
0x180813c6d  test    rdi, rdi
0x180813c70  jz      loc_180813E0E
0x180813c76  mov     [rbp+displayTitle.hstr_], r14
0x180813c7a  xor     ecx, ecx; string
0x180813c7c  mov     [rbp+linkType.hstr_], r14
0x180813c80  mov     rax, [rdi]
0x180813c83  mov     rbx, [rax+40h]
0x180813c87  call    cs:__imp_WindowsDeleteString
0x180813c8d  lea     rdx, [rbp+displayTitle]
0x180813c91  mov     [rbp+displayTitle.hstr_], r14
0x180813c95  mov     pTextTracker, rdi
0x180813c98  mov     rax, rbx
0x180813c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180813ca0  mov     ebx, eax
0x180813ca2  test    eax, eax
0x180813ca4  js      loc_180813E24
0x180813caa  mov     rdi, [rbp+spContentLinkInfo.ptr_]
0x180813cae  mov     pTextTracker, [rbp+linkType.hstr_]; string
0x180813cb2  mov     rax, [rdi]
0x180813cb5  mov     rbx, [rax+70h]
0x180813cb9  call    cs:__imp_WindowsDeleteString
0x180813cbf  lea     rdx, [rbp+linkType]
0x180813cc3  mov     [rbp+linkType.hstr_], r14
0x180813cc7  mov     pTextTracker, rdi
0x180813cca  mov     rax, rbx
0x180813ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180813cd2  mov     ebx, eax
0x180813cd4  test    eax, eax
0x180813cd6  js      loc_180813E1B
0x180813cdc  mov     eax, cs:_Tlgg_hTraceProviderProv.LevelPlus1
0x180813ce2  cmp     eax, 5
0x180813ce5  jbe     short loc_180813D58
0x180813ce7  mov     rdx, 400000000000h; keyword
0x180813cf1  lea     pTextTracker, _Tlgg_hTraceProviderProv; hProvider
0x180813cf8  call    _tlgKeywordOn
0x180813cfd  test    al, al
0x180813cff  jz      short loc_180813D58
0x180813d01  mov     pTextTracker, [rbp+linkType.hstr_]; __annotation("_TlgWrite:|5709|g_hTraceProvider|"SmartLinkEdited"=|"DisplayTitle"=|"LinkType"=")
0x180813d05  lea     rbx, pressedKeys
0x180813d0c  test    pTextTracker, pTextTracker
0x180813d0f  jz      short loc_180813D1B
0x180813d11  xor     id, id; length
0x180813d13  call    cs:__imp_WindowsGetStringRawBuffer
0x180813d19  jmp     short loc_180813D1E
0x180813d1b  mov     rax, rbx
0x180813d1e  mov     pTextTracker, [rbp+displayTitle.hstr_]; string
0x180813d22  mov     [rbp+var_18.Psz], rax
0x180813d26  test    pTextTracker, pTextTracker
0x180813d29  jz      short loc_180813D36
0x180813d2b  xor     id, id; length
0x180813d2d  call    cs:__imp_WindowsGetStringRawBuffer
0x180813d33  mov     rbx, rax
0x180813d36  lea     rax, [rbp+var_18]
0x180813d3a  mov     [rbp+pEventMetadata.Psz], rbx
0x180813d3e  mov     [rsp+70h+var_48], rax; <writerArgs_0>
0x180813d43  lea     rdx, _tlgEvent_6._tlgChannel; <wrappedArgs_0>
0x180813d4a  lea     rax, [rbp+pEventMetadata]
0x180813d4e  mov     [rsp+70h+pNewLength], rax; pEventMetadata
0x180813d53  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180813d58  mov     ecx, [rbp+textRange.StartIndex]
0x180813d5b  mov     eax, [rbp+cpNewMost]
0x180813d5e  mov     rbx, [rbp+spContentLinkInfo.ptr_]
0x180813d62  sub     eax, ecx
0x180813d64  mov     [rbp+textRange.Length], ecx
0x180813d67  mov     ecx, 28h ; '('; cSize
0x180813d6c  mov     [rbp+textRange.StartIndex], eax
0x180813d6f  call    ?OSMemoryAllocateFailFast@XcpAllocation@@YAPEAX_K@Z; XcpAllocation::OSMemoryAllocateFailFast(unsigned __int64)
0x180813d74  test    rax, rax
0x180813d77  jz      short loc_180813D90
0x180813d79  mov     r8, qword ptr [rbp+textRange.StartIndex]; textRange
0x180813d7d  mov     r9b, 2; changeKind
0x180813d80  mov     rdx, rbx; contentLinkInfo
0x180813d83  mov     pTextTracker, rax; this
0x180813d86  call    ??0CContentLinkChangedEventArgs@@QEAA@PEAUIContentLinkInfo@Text@UI@Windows@@UTextRange@Documents@Xaml@34@W4ContentLinkChangeKind@DirectUI@@@Z; CContentLinkChangedEventArgs::CContentLinkChangedEventArgs(Windows::UI::Text::IContentLinkInfo *,Windows::UI::Xaml::Documents::TextRange,DirectUI::ContentLinkChangeKind)
0x180813d8b  mov     rbx, rax
0x180813d8e  jmp     short loc_180813D93
0x180813d90  mov     rbx, r14
0x180813d93  mov     rax, [rsi+10h]
0x180813d97  mov     id, 0DDh; hEvent
0x180813d9c  mov     [rsp+70h+pSenderOverride], r14; pSenderOverride
0x180813da1  mov     r9, rsi; pSender
0x180813da4  mov     [rsp+70h+bAllowErrorFallback], 1; bAllowErrorFallback
0x180813da9  mov     r8d, 1; bRefire
0x180813daf  mov     [rsp+70h+fInputEvent], r14b; fInputEvent
0x180813db4  mov     pTextTracker, [rax]
0x180813db7  mov     byte ptr [rsp+70h+var_48], 1; fRaiseSync
0x180813dbc  mov     [rsp+70h+pNewLength], rbx; pArgs
0x180813dc1  mov     pTextTracker, [pTextTracker+0E8h]; this
0x180813dc8  call    ?Raise@CEventManager@@QEAAXUEventHandle@@HPEAVCDependencyObject@@PEAVCEventArgs@@_N331@Z; CEventManager::Raise(EventHandle,int,CDependencyObject *,CEventArgs *,bool,bool,bool,CDependencyObject *)
0x180813dcd  test    rbx, rbx
0x180813dd0  jz      short loc_180813DDA
0x180813dd2  mov     pTextTracker, rbx; this
0x180813dd5  call    ?Release@CEventArgs@@UEAAKXZ; CEventArgs::Release(void)
0x180813dda  mov     pTextTracker, [rbp+linkType.hstr_]; string
0x180813dde  call    cs:__imp_WindowsDeleteString
0x180813de4  mov     pTextTracker, [rbp+displayTitle.hstr_]; string
0x180813de8  mov     [rbp+linkType.hstr_], r14
0x180813dec  call    cs:__imp_WindowsDeleteString
0x180813df2  mov     rdi, [rbp+spContentLinkInfo.ptr_]
0x180813df6  test    rdi, rdi
0x180813df9  jz      short loc_180813E0E
0x180813dfb  mov     [rbp+spContentLinkInfo.ptr_], r14
0x180813dff  mov     pTextTracker, rdi
0x180813e02  mov     rax, [rdi]
0x180813e05  mov     rax, [rax+10h]
0x180813e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180813e0e  xor     eax, eax
0x180813e10  add     rsp, 70h
0x180813e14  pop     r14
0x180813e16  pop     rdi
0x180813e17  pop     rsi
0x180813e18  pop     rbx
0x180813e19  pop     rbp
0x180813e1a  retn
0x180813e1b  mov     ecx, ebx; failedFrameHR
0x180813e1d  call    OnFailure_2990_
0x180813e22  jmp     short loc_180813E2B
0x180813e24  mov     ecx, ebx; failedFrameHR
0x180813e26  call    OnFailure_2990_
0x180813e2b  mov     pTextTracker, [rbp+linkType.hstr_]; string
0x180813e2f  call    cs:__imp_WindowsDeleteString
0x180813e35  mov     pTextTracker, [rbp+displayTitle.hstr_]; string
0x180813e39  mov     [rbp+linkType.hstr_], r14
0x180813e3d  call    cs:__imp_WindowsDeleteString
0x180813e43  mov     [rbp+displayTitle.hstr_], r14
0x180813e47  jmp     short loc_180813E50
0x180813e49  mov     ecx, ebx; failedFrameHR
0x180813e4b  call    OnFailure_2990_
0x180813e50  mov     pTextTracker, [rbp+spContentLinkInfo.ptr_]
0x180813e54  test    pTextTracker, pTextTracker
0x180813e57  jz      short loc_180813E69
0x180813e59  mov     [rbp+spContentLinkInfo.ptr_], r14
0x180813e5d  mov     rax, [pTextTracker]
0x180813e60  mov     rax, [rax+10h]
0x180813e64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180813e69  mov     eax, ebx
0x180813e6b  jmp     short loc_180813E10
```
