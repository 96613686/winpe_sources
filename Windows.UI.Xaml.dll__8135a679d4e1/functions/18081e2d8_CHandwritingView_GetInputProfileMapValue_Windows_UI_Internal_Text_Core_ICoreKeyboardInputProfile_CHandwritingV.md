# CHandwritingView::GetInputProfileMapValue(Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfile *,CHandwritingView::InputProfileMapValue &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18081e2d8`
- end: `0x18081e617`
- name: `?GetInputProfileMapValue@CHandwritingView@@AEAAJPEAUICoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@AEAUInputProfileMapValue@1@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `831`
- prototype: `HRESULT __fastcall(CHandwritingView *this, Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfile *pProfile, CHandwritingView::InputProfileMapValue *result, std::wstring *pMapKey)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1807214b8`
- `0x180821450`

## callees

- `0x180004bc0`
- `0x180008428`
- `0x1800fe130`
- `0x1801c3490`
- `0x18030bcd4`
- `0x180511238`
- `0x180688828`
- `0x18076e110`
- `0x180817394`
- `0x18081e2d8`
- `0x180822a80`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18081e32b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18081e392`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18081e3bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18081e3e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18081e50e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18081e524`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18081e534`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18081e544`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18081e591`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18081e5a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18081e5b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18081e5cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18081e5e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18081e32b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18081e392`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18081e3bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18081e3e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18081e50e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18081e524`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18081e534`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18081e544`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18081e591`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18081e5a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18081e5b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18081e5cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18081e5e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18081e465`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18081e475`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18081e465`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18081e475`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18081e355`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18081e355`
- `Bcp47Langs!Bcp47FromLcid` at `0x18081e3a6`
- `Bcp47Langs!Bcp47FromLcid` at `0x18081e3a6`
- `Bcp47Langs!Bcp47GetLanguageName` at `0x18081e3d0`
- `Bcp47Langs!Bcp47GetLanguageName` at `0x18081e3d0`
- `Bcp47Langs!Bcp47GetAbbreviation` at `0x18081e3fa`
- `Bcp47Langs!Bcp47GetAbbreviation` at `0x18081e3fa`

## pseudocode

```c
__int64 __fastcall CHandwritingView::GetInputProfileMapValue(
        CHandwritingView *this,
        Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfile *pProfile,
        CHandwritingView::InputProfileMapValue *result,
        std::wstring *pMapKey)
{
  Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfile_vtbl *v8; // rax
  HRESULT (__fastcall *get_DisplayDescription)(Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfile *, HSTRING__ **); // rbx
  HRESULT v10; // eax
  unsigned int v11; // ebx
  HRESULT LanguageName; // eax
  HRESULT v13; // eax
  IXcpBrowserHost *m_pBrowserHost; // rcx
  HRESULT v15; // eax
  wil::ReportingKind v16; // r8d
  unsigned __int64 v17; // r9
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v19; // rax
  unsigned __int64 v20; // r8
  std::wstring *v21; // rax
  Microsoft::WRL::Wrappers::HString abbreviation; // [rsp+30h] [rbp-D0h] BYREF
  Microsoft::WRL::Wrappers::HString bcp47Tag; // [rsp+38h] [rbp-C8h] BYREF
  Microsoft::WRL::Wrappers::HString fullLangName; // [rsp+40h] [rbp-C0h] BYREF
  Microsoft::WRL::Wrappers::HString hstrProfile; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int langId; // [rsp+50h] [rbp-B0h] BYREF
  xstring_ptr jointStr; // [rsp+58h] [rbp-A8h] BYREF
  Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> v29; // [rsp+60h] [rbp-A0h] BYREF
  Diagnostics::ElementStateChangedContext v30; // [rsp+68h] [rbp-98h] BYREF
  wchar_t formattedString[88]; // [rsp+90h] [rbp-70h] BYREF

  if ( pProfile )
  {
    v8 = pProfile->__vftable;
    hstrProfile.hstr_ = 0;
    langId = 0;
    get_DisplayDescription = v8->get_DisplayDescription;
    WindowsDeleteString(0);
    hstrProfile.hstr_ = 0;
    v10 = get_DisplayDescription(pProfile, &hstrProfile.hstr_);
    v11 = v10;
    if ( v10 < 0 )
      goto LABEL_23;
    if ( WindowsIsStringEmpty(hstrProfile.hstr_) )
    {
      WindowsDeleteString(hstrProfile.hstr_);
      return 2147943568LL;
    }
    v10 = pProfile->get_Langid(pProfile, &langId);
    v11 = v10;
    if ( v10 < 0 )
    {
LABEL_23:
      OnFailure_2990_(v10);
    }
    else
    {
      fullLangName.hstr_ = 0;
      abbreviation.hstr_ = 0;
      WindowsDeleteString(0);
      bcp47Tag.hstr_ = 0;
      LanguageName = Bcp47FromLcid(langId, &bcp47Tag);
      v11 = LanguageName;
      if ( LanguageName < 0
        || (WindowsDeleteString(fullLangName.hstr_),
            fullLangName.hstr_ = 0,
            LanguageName = Bcp47GetLanguageName(bcp47Tag.hstr_, &fullLangName),
            v11 = LanguageName,
            LanguageName < 0) )
      {
        OnFailure_2990_(LanguageName);
      }
      else
      {
        WindowsDeleteString(abbreviation.hstr_);
        abbreviation.hstr_ = 0;
        v13 = Bcp47GetAbbreviation(bcp47Tag.hstr_, &abbreviation);
        v11 = v13;
        if ( v13 < 0 )
        {
          OnFailure_2990_(v13);
        }
        else
        {
          if ( !pMapKey )
            goto LABEL_14;
          jointStr.m_encodedStorage.Storage = xstring_ptr_constants::c_xencoded_string_ptr_null.Storage;
          m_pBrowserHost = this->m_sharedState.m_ptr->m_value.m_coreServices->m_pBrowserHost;
          v15 = m_pBrowserHost->GetLocalizedResourceString(m_pBrowserHost, 5569u, &jointStr);
          v11 = v15;
          if ( v15 >= 0 )
          {
            wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExpandedEIC>::ReportUsage(
              &`wil::Feature<__WilFeatureTraits_Feature_ExpandedEIC>::GetImpl'::`2'::impl,
              1,
              v16,
              v17);
            StringRawBuffer = WindowsGetStringRawBuffer(hstrProfile.hstr_, 0);
            v19 = WindowsGetStringRawBuffer(fullLangName.hstr_, 0);
            v15 = StringCchPrintfW(formattedString, 0x55u, L"%s\n%s", v19, StringRawBuffer);
            v11 = v15;
            if ( v15 >= 0 )
            {
              v20 = -1;
              do
                ++v20;
              while ( formattedString[v20] );
              std::wstring::wstring(&v30.PathToError, formattedString, v20);
              std::wstring::operator=(pMapKey, v21);
              Diagnostics::ElementStateChangedContext::~ElementStateChangedContext(&v30);
              xstring_ptr::~xstring_ptr(&jointStr);
LABEL_14:
              if ( result->m_pCoreKeyboardInputProfile.ptr_ != pProfile )
              {
                pProfile->AddRef(pProfile);
                v29.ptr_ = (Windows::System::Internal::IUserManagerStatics *)result->m_pCoreKeyboardInputProfile.ptr_;
                result->m_pCoreKeyboardInputProfile.ptr_ = pProfile;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
              }
              WindowsDeleteString(result->abbreviation.hstr_);
              result->abbreviation = abbreviation;
              abbreviation.hstr_ = 0;
              WindowsDeleteString(0);
              abbreviation.hstr_ = 0;
              WindowsDeleteString(bcp47Tag.hstr_);
              bcp47Tag.hstr_ = 0;
              WindowsDeleteString(fullLangName.hstr_);
              fullLangName.hstr_ = 0;
              v11 = 0;
              goto LABEL_24;
            }
          }
          OnFailure_2990_(v15);
          xstring_ptr::~xstring_ptr(&jointStr);
        }
      }
      WindowsDeleteString(abbreviation.hstr_);
      abbreviation.hstr_ = 0;
      WindowsDeleteString(bcp47Tag.hstr_);
      bcp47Tag.hstr_ = 0;
      WindowsDeleteString(fullLangName.hstr_);
      fullLangName.hstr_ = 0;
    }
LABEL_24:
    WindowsDeleteString(hstrProfile.hstr_);
    return v11;
  }
  OnNewFailure_1172_((HRESULT)this);
  return 2147500035LL;
}

```

## disassembly

```asm
0x18081e2d8  push    rbp
0x18081e2da  push    rbx
0x18081e2db  push    rsi
0x18081e2dc  push    rdi
0x18081e2dd  push    r12
0x18081e2df  push    r14
0x18081e2e1  push    r15
0x18081e2e3  lea     rbp, [rsp-50h]
0x18081e2e8  sub     rsp, 150h
0x18081e2ef  mov     rax, cs:__security_cookie
0x18081e2f6  xor     rax, rsp
0x18081e2f9  mov     [rbp+80h+var_40], rax
0x18081e2fd  xor     r12d, r12d
0x18081e300  mov     r14, pMapKey
0x18081e303  mov     rsi, result
0x18081e306  mov     rdi, pProfile
0x18081e309  mov     r15, this
0x18081e30c  test    pProfile, pProfile
0x18081e30f  jz      loc_18081E5EF
0x18081e315  mov     rax, [pProfile]
0x18081e318  xor     ecx, ecx; string
0x18081e31a  mov     [rsp+180h+hstrProfile.hstr_], r12
0x18081e31f  mov     [rsp+180h+langId], r12d
0x18081e324  mov     rbx, [rax+80h]
0x18081e32b  call    cs:__imp_WindowsDeleteString
0x18081e331  lea     pProfile, [rsp+180h+hstrProfile]
0x18081e336  mov     [rsp+180h+hstrProfile.hstr_], r12
0x18081e33b  mov     this, rdi
0x18081e33e  mov     rax, rbx
0x18081e341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18081e346  mov     ebx, eax
0x18081e348  test    eax, eax
0x18081e34a  js      loc_18081E5D9
0x18081e350  mov     this, [rsp+180h+hstrProfile.hstr_]; string
0x18081e355  call    cs:__imp_WindowsIsStringEmpty
0x18081e35b  test    eax, eax
0x18081e35d  jnz     loc_18081E5C7
0x18081e363  mov     rax, [rdi]
0x18081e366  lea     pProfile, [rsp+180h+langId]
0x18081e36b  mov     this, rdi
0x18081e36e  mov     rax, [rax+40h]
0x18081e372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18081e377  mov     ebx, eax
0x18081e379  test    eax, eax
0x18081e37b  js      loc_18081E5BE
0x18081e381  xor     ecx, ecx; string
0x18081e383  mov     [rsp+180h+fullLangName.hstr_], r12
0x18081e388  mov     [rsp+180h+bcp47Tag.hstr_], r12
0x18081e38d  mov     [rsp+180h+abbreviation.hstr_], r12
0x18081e392  call    cs:__imp_WindowsDeleteString
0x18081e398  mov     ecx, [rsp+180h+langId]
0x18081e39c  lea     pProfile, [rsp+180h+bcp47Tag]
0x18081e3a1  mov     [rsp+180h+bcp47Tag.hstr_], r12
0x18081e3a6  call    cs:__imp_Bcp47FromLcid
0x18081e3ac  mov     ebx, eax
0x18081e3ae  test    eax, eax
0x18081e3b0  js      loc_18081E585
0x18081e3b6  mov     this, [rsp+180h+fullLangName.hstr_]; string
0x18081e3bb  call    cs:__imp_WindowsDeleteString
0x18081e3c1  mov     this, [rsp+180h+bcp47Tag.hstr_]
0x18081e3c6  lea     pProfile, [rsp+180h+fullLangName]
0x18081e3cb  mov     [rsp+180h+fullLangName.hstr_], r12
0x18081e3d0  call    cs:__imp_Bcp47GetLanguageName
0x18081e3d6  mov     ebx, eax
0x18081e3d8  test    eax, eax
0x18081e3da  js      loc_18081E57C
0x18081e3e0  mov     this, [rsp+180h+abbreviation.hstr_]; string
0x18081e3e5  call    cs:__imp_WindowsDeleteString
0x18081e3eb  mov     this, [rsp+180h+bcp47Tag.hstr_]
0x18081e3f0  lea     pProfile, [rsp+180h+abbreviation]
0x18081e3f5  mov     [rsp+180h+abbreviation.hstr_], r12
0x18081e3fa  call    cs:__imp_Bcp47GetAbbreviation
0x18081e400  mov     ebx, eax
0x18081e402  test    eax, eax
0x18081e404  js      loc_18081E573
0x18081e40a  test    r14, r14
0x18081e40d  jz      loc_18081E4E1
0x18081e413  mov     rax, qword ptr cs:?c_xencoded_string_ptr_null@xstring_ptr_constants@@2Uxencoded_string_ptr@@B.___u0; xencoded_string_ptr const xstring_ptr_constants::c_xencoded_string_ptr_null ...
0x18081e41a  lea     result, [rsp+180h+jointStr]
0x18081e41f  mov     qword ptr [rsp+180h+jointStr.m_encodedStorage.___u0], rax
0x18081e424  mov     edx, 15C1h
0x18081e429  mov     rax, [r15+10h]
0x18081e42d  mov     this, [rax]
0x18081e430  mov     this, [this+108h]
0x18081e437  mov     rax, [this]
0x18081e43a  mov     rax, [rax+188h]
0x18081e441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18081e446  mov     ebx, eax
0x18081e448  test    eax, eax
0x18081e44a  js      loc_18081E560
0x18081e450  mov     dl, 1; __annotation("WILSTG:|18675136|Feature_ExpandedEIC|AlwaysEnabled")
0x18081e452  lea     this, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ExpandedEIC@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ExpandedEIC@@@details@3@XZ@4V453@A; this
0x18081e459  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ExpandedEIC@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExpandedEIC>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18081e45e  mov     this, [rsp+180h+hstrProfile.hstr_]; string
0x18081e463  xor     edx, edx; length
0x18081e465  call    cs:__imp_WindowsGetStringRawBuffer
0x18081e46b  mov     this, [rsp+180h+fullLangName.hstr_]; string
0x18081e470  xor     edx, edx; length
0x18081e472  mov     rbx, rax
0x18081e475  call    cs:__imp_WindowsGetStringRawBuffer
0x18081e47b  lea     result, aSS_0; "%s\n%s"
0x18081e482  mov     [rsp+180h+var_160], rbx
0x18081e487  mov     pMapKey, rax
0x18081e48a  lea     edx, [r12+55h]; cchDest
0x18081e48f  lea     this, [rbp+80h+formattedString]; pszDest
0x18081e493  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18081e498  mov     ebx, eax
0x18081e49a  test    eax, eax
0x18081e49c  js      loc_18081E557
0x18081e4a2  lea     rax, [rbp+80h+formattedString]
0x18081e4a6  or      result, 0FFFFFFFFFFFFFFFFh
0x18081e4aa  inc     result; _Count
0x18081e4ad  cmp     [rax+result*2], r12w
0x18081e4b2  jnz     short loc_18081E4AA
0x18081e4b4  lea     pProfile, [rbp+80h+formattedString]; _Ptr
0x18081e4b8  lea     this, [rsp+180h+var_118]; this
0x18081e4bd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x18081e4c2  mov     pProfile, rax; _Right
0x18081e4c5  mov     this, r14; this
0x18081e4c8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18081e4cd  lea     this, [rsp+180h+var_118]; this
0x18081e4d2  call    ??1ElementStateChangedContext@Diagnostics@@QEAA@XZ; Diagnostics::ElementStateChangedContext::~ElementStateChangedContext(void)
0x18081e4d7  lea     this, [rsp+180h+jointStr]; this
0x18081e4dc  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x18081e4e1  cmp     [rsi], rdi
0x18081e4e4  jz      short loc_18081E50A
0x18081e4e6  mov     rax, [rdi]
0x18081e4e9  mov     this, rdi
0x18081e4ec  mov     rax, [rax+8]
0x18081e4f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18081e4f5  mov     rax, [rsi]
0x18081e4f8  lea     this, [rsp+180h+var_120]; this
0x18081e4fd  mov     [rsp+180h+var_120.ptr_], rax
0x18081e502  mov     [rsi], rdi
0x18081e505  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18081e50a  mov     this, [rsi+8]; string
0x18081e50e  call    cs:__imp_WindowsDeleteString
0x18081e514  mov     rax, [rsp+180h+abbreviation.hstr_]
0x18081e519  xor     ecx, ecx; string
0x18081e51b  mov     [rsi+8], rax
0x18081e51f  mov     [rsp+180h+abbreviation.hstr_], r12
0x18081e524  call    cs:__imp_WindowsDeleteString
0x18081e52a  mov     this, [rsp+180h+bcp47Tag.hstr_]; string
0x18081e52f  mov     [rsp+180h+abbreviation.hstr_], r12
0x18081e534  call    cs:__imp_WindowsDeleteString
0x18081e53a  mov     this, [rsp+180h+fullLangName.hstr_]; string
0x18081e53f  mov     [rsp+180h+bcp47Tag.hstr_], r12
0x18081e544  call    cs:__imp_WindowsDeleteString
0x18081e54a  mov     [rsp+180h+fullLangName.hstr_], r12
0x18081e54f  mov     ebx, r12d
0x18081e552  jmp     loc_18081E5E0
0x18081e557  mov     ecx, eax; failedFrameHR
0x18081e559  call    OnFailure_2990_
0x18081e55e  jmp     short loc_18081E567
0x18081e560  mov     ecx, eax; failedFrameHR
0x18081e562  call    OnFailure_2990_
0x18081e567  lea     this, [rsp+180h+jointStr]; this
0x18081e56c  call    ??1xstring_ptr@@QEAA@XZ; xstring_ptr::~xstring_ptr(void)
0x18081e571  jmp     short loc_18081E58C
0x18081e573  mov     ecx, eax; failedFrameHR
0x18081e575  call    OnFailure_2990_
0x18081e57a  jmp     short loc_18081E58C
0x18081e57c  mov     ecx, eax; failedFrameHR
0x18081e57e  call    OnFailure_2990_
0x18081e583  jmp     short loc_18081E58C
0x18081e585  mov     ecx, eax; failedFrameHR
0x18081e587  call    OnFailure_2990_
0x18081e58c  mov     this, [rsp+180h+abbreviation.hstr_]; string
0x18081e591  call    cs:__imp_WindowsDeleteString
0x18081e597  mov     this, [rsp+180h+bcp47Tag.hstr_]; string
0x18081e59c  mov     [rsp+180h+abbreviation.hstr_], r12
0x18081e5a1  call    cs:__imp_WindowsDeleteString
0x18081e5a7  mov     this, [rsp+180h+fullLangName.hstr_]; string
0x18081e5ac  mov     [rsp+180h+bcp47Tag.hstr_], r12
0x18081e5b1  call    cs:__imp_WindowsDeleteString
0x18081e5b7  mov     [rsp+180h+fullLangName.hstr_], r12
0x18081e5bc  jmp     short loc_18081E5E0
0x18081e5be  mov     ecx, eax; failedFrameHR
0x18081e5c0  call    OnFailure_2990_
0x18081e5c5  jmp     short loc_18081E5E0
0x18081e5c7  mov     this, [rsp+180h+hstrProfile.hstr_]; string
0x18081e5cc  call    cs:__imp_WindowsDeleteString
0x18081e5d2  mov     eax, 80070490h
0x18081e5d7  jmp     short loc_18081E5F9
0x18081e5d9  mov     ecx, eax; failedFrameHR
0x18081e5db  call    OnFailure_2990_
0x18081e5e0  mov     this, [rsp+180h+hstrProfile.hstr_]; string
0x18081e5e5  call    cs:__imp_WindowsDeleteString
0x18081e5eb  mov     eax, ebx
0x18081e5ed  jmp     short loc_18081E5F9
0x18081e5ef  call    OnNewFailure_1172_
0x18081e5f4  mov     eax, 80004003h
0x18081e5f9  mov     this, [rbp+80h+var_40]
0x18081e5fd  xor     this, rsp; StackCookie
0x18081e600  call    __security_check_cookie
0x18081e605  add     rsp, 150h
0x18081e60c  pop     r15
0x18081e60e  pop     r14
0x18081e610  pop     r12
0x18081e612  pop     rdi
0x18081e613  pop     rsi
0x18081e614  pop     rbx
0x18081e615  pop     rbp
0x18081e616  retn
```
