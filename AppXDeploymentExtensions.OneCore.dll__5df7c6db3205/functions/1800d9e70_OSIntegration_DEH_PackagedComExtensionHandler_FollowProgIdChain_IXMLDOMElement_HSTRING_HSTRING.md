# OSIntegration::DEH::PackagedComExtensionHandler::FollowProgIdChain(IXMLDOMElement *,HSTRING__ *,HSTRING__ * *)

- ea: `0x1800d9e70`
- end: `0x1800da30e`
- name: `?FollowProgIdChain@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEAUHSTRING__@@PEAPEAU5@@Z`
- size: `1182`
- prototype: `__int64 __fastcall(OSIntegration::DEH::PackagedComExtensionHandler *__hidden this, struct IXMLDOMElement *, HSTRING, HSTRING *)`
- caller_count: `3`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d9e70`
- `0x18016b224`
- `0x18016faf4`

## callees

- `0x18000b3bc`
- `0x18000b7d0`
- `0x18000b9e0`
- `0x180012964`
- `0x18003f850`
- `0x1800550f4`
- `0x18007d350`
- `0x180098ed0`
- `0x18009aff4`
- `0x18009b1b8`
- `0x1800d9e70`
- `0x18013ced4`
- `0x18013d6f8`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800da004`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800da004`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800da06e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800da06e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800da109`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800da176`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800da2da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800da2e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800da109`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800da176`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800da2da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800da2e8`

## string_xrefs

- `0x1800d9eea`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800d9f3d`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800d9feb`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800da03e`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800da0af`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800da20b`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800da2b9`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800d9fd8`: `APPX_E_INVALID_MANIFEST`
- `0x1800da2a6`: `APPX_E_INVALID_MANIFEST`
- `0x1800da032`: `xpath`
- `0x1800d9ee3`: `OSIntegration::DEH::PackagedComExtensionHandler::FollowProgIdChain`
- `0x1800d9f36`: `OSIntegration::DEH::PackagedComExtensionHandler::FollowProgIdChain`
- `0x1800d9fe4`: `OSIntegration::DEH::PackagedComExtensionHandler::FollowProgIdChain`
- `0x1800da045`: `OSIntegration::DEH::PackagedComExtensionHandler::FollowProgIdChain`
- `0x1800da0a8`: `OSIntegration::DEH::PackagedComExtensionHandler::FollowProgIdChain`
- `0x1800da204`: `OSIntegration::DEH::PackagedComExtensionHandler::FollowProgIdChain`
- `0x1800da2b2`: `OSIntegration::DEH::PackagedComExtensionHandler::FollowProgIdChain`
- `0x1800da077`: `//*[local-name()='Extension' and @Category='windows.comServer']/*[local-name()='ComServer']/*[local-name()='ProgId' and @Id='%ls']`
- `0x1800d9ed7`: `_progIdHelperList->Insert(currentVersion, nullptr, &replaced)`
- `0x1800da09c`: `StringCchPrintf( xpath.get(), cchxpath, Internal::PackagedComConstants::progIdWithIdFormat, ::WindowsGetStringRawBuffer(currentVersion, nullptr))`
- `0x1800da0f4`: `GetXMLElementFromQuery(xpath.get(), previousProgId, &progId)`
- `0x1800da13a`: `ParseAndRetrieveAttribute( progId.Get(), Internal::PackagedComConstants::clsidAttribute, clsidProgId.GetAddressOf(), &clsidFound)`
- `0x1800da1a7`: `ParseAndRetrieveAttribute( progId.Get(), Internal::PackagedComConstants::currentVersionAttribute, currentVersionProgId.GetAddressOf(), &currentVersionFound)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OSIntegration::DEH::PackagedComExtensionHandler::FollowProgIdChain(
        OSIntegration::DEH::PackagedComExtensionHandler *this,
        const struct IXMLDOMNode *a2,
        HSTRING a3,
        HSTRING *a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // rbx
  unsigned int v12; // eax
  const unsigned __int16 *v13; // rax
  __int64 v14; // rdx
  __int64 StringLen; // r15
  wchar_t *v16; // rbx
  const char *v17; // rax
  __int64 v18; // rdx
  PCWSTR StringRawBuffer; // rax
  int v20; // eax
  unsigned int v21; // r14d
  struct IXMLDOMElement **v22; // r9
  int XMLElementFromQuery; // eax
  OSIntegration::DEH::PackagedComExtensionHandler *v24; // rcx
  int v25; // eax
  HSTRING v26; // rax
  OSIntegration::DEH::PackagedComExtensionHandler *v27; // rcx
  int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rbx
  unsigned int v31; // eax
  const unsigned __int16 *v32; // rax
  __int64 v33; // rdx
  char *v35; // [rsp+28h] [rbp-50h]
  char *v36; // [rsp+28h] [rbp-50h]
  char *v37; // [rsp+28h] [rbp-50h]
  int v38; // [rsp+30h] [rbp-48h]
  bool v39; // [rsp+40h] [rbp-38h] BYREF
  bool v40; // [rsp+41h] [rbp-37h] BYREF
  __int64 v41; // [rsp+48h] [rbp-30h] BYREF
  wchar_t *Buffer; // [rsp+50h] [rbp-28h] BYREF
  HSTRING v43; // [rsp+58h] [rbp-20h] BYREF
  HSTRING string; // [rsp+60h] [rbp-18h] BYREF
  struct IXMLDOMElement v45; // [rsp+68h] [rbp-10h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+B8h] [rbp+40h]
  char v47; // [rsp+C0h] [rbp+48h] BYREF

  v45.lpVtbl = 0;
  v43 = 0;
  string = 0;
  v40 = 0;
  v39 = 0;
  v47 = 0;
  v41 = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, _QWORD, char *))(**((_QWORD **)this + 7) + 80LL))(
         *((_QWORD *)this + 7),
         a3,
         0,
         &v47);
  v9 = v8;
  if ( v8 < 0 )
  {
    LODWORD(v35) = v8;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xFC3,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::FollowProgIdChain",
      "_progIdHelperList->Insert(currentVersion, nullptr, &replaced)",
      v35,
      v38);
    goto LABEL_29;
  }
  if ( v47 )
  {
    OSIntegration::Package::GetXmlLineInformation(
      *((OSIntegration::Package **)this + 5),
      a2,
      0,
      (struct APPX_XML_LINE_INFORMATION *)&v41);
    LODWORD(v35) = -2146958844;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0xFD5,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::FollowProgIdChain",
      "((HRESULT)0x80080204L)",
      v35,
      v38);
    if ( (byte_1802E21CA & 4) != 0 )
    {
      v10 = *((_QWORD *)this + 5);
      v11 = *(_QWORD *)(v10 + 224);
      v12 = (unsigned int)RemovePIIfromFilePath(*(const unsigned __int16 **)(v10 + 272));
      McTemplateU0zqqdz_EventWriteTransfer(
        HIDWORD(v41),
        (unsigned int)PackagedComInvalidProgId,
        v12,
        v41,
        SBYTE4(v41),
        4,
        v11);
    }
    v13 = RemovePIIfromFilePath(*(const unsigned __int16 **)(*((_QWORD *)this + 5) + 272LL));
    details::appxLog<unsigned short const *,unsigned int,unsigned int,long,unsigned short *>(
      2148008452LL,
      v14,
      PackagedComInvalidProgId,
      v13);
    LODWORD(v36) = -2146958844;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xFD7,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::FollowProgIdChain",
      "APPX_E_INVALID_MANIFEST",
      v36,
      -2146958844);
LABEL_28:
    v9 = -2146958844;
    goto LABEL_29;
  }
  StringLen = WindowsGetStringLen(a3);
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &Buffer,
    0,
    StringLen + 129);
  v16 = Buffer;
  if ( !Buffer )
  {
    v9 = -2147024882;
    LODWORD(v35) = -2147024882;
    v17 = "xpath";
    v18 = 4065;
    goto LABEL_9;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
  v20 = StringCchPrintfW(
          v16,
          StringLen + 129,
          L"//*[local-name()='Extension' and @Category='windows.comServer']/*[local-name()='ComServer']/*[local-name()='Pr"
           "ogId' and @Id='%ls']",
          StringRawBuffer);
  v21 = v20;
  if ( v20 < 0 )
  {
    LODWORD(v35) = v20;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xFE7,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::FollowProgIdChain",
      "StringCchPrintf( xpath.get(), cchxpath, Internal::PackagedComConstants::progIdWithIdFormat, ::WindowsGetStringRawB"
      "uffer(currentVersion, nullptr))",
      v35,
      v38);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Buffer);
    v9 = v21;
    goto LABEL_29;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
  XMLElementFromQuery = Common::Xml::GetXMLElementFromQuery(v16, (const unsigned __int16 *)a2, &v45, v22);
  v9 = XMLElementFromQuery;
  if ( XMLElementFromQuery < 0 )
  {
    LODWORD(v35) = XMLElementFromQuery;
    v17 = "GetXMLElementFromQuery(xpath.get(), previousProgId, &progId)";
    v18 = 4075;
    goto LABEL_9;
  }
  WindowsDeleteString(v43);
  v43 = 0;
  v25 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(
          v24,
          (struct IXMLDOMElement *)v45.lpVtbl,
          (const unsigned __int16 *)&stru_180255228,
          &v43,
          &v39);
  v9 = v25;
  if ( v25 < 0 )
  {
    LODWORD(v35) = v25;
    v17 = "ParseAndRetrieveAttribute( progId.Get(), Internal::PackagedComConstants::clsidAttribute, clsidProgId.GetAddres"
          "sOf(), &clsidFound)";
    v18 = 4082;
    goto LABEL_9;
  }
  if ( !v39 )
  {
    WindowsDeleteString(string);
    string = 0;
    v28 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(
            v27,
            (struct IXMLDOMElement *)v45.lpVtbl,
            L"CurrentVersion",
            &string,
            &v40);
    v9 = v28;
    if ( v28 >= 0 )
    {
      if ( !v40 )
      {
        OSIntegration::Package::GetXmlLineInformation(
          *((OSIntegration::Package **)this + 5),
          a2,
          0,
          (struct APPX_XML_LINE_INFORMATION *)&v41);
        LODWORD(v35) = -2146958844;
        wil::details::in1diag5::_Log_Hr(
          retaddr,
          (void *)0x1019,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::FollowProgIdChain",
          "((HRESULT)0x80080204L)",
          v35,
          v38);
        if ( (byte_1802E21CA & 4) != 0 )
        {
          v29 = *((_QWORD *)this + 5);
          v30 = *(_QWORD *)(v29 + 224);
          v31 = (unsigned int)RemovePIIfromFilePath(*(const unsigned __int16 **)(v29 + 272));
          McTemplateU0zqqdz_EventWriteTransfer(
            HIDWORD(v41),
            (unsigned int)PackagedComInvalidCurrentVersion,
            v31,
            v41,
            SBYTE4(v41),
            4,
            v30);
        }
        v32 = RemovePIIfromFilePath(*(const unsigned __int16 **)(*((_QWORD *)this + 5) + 272LL));
        details::appxLog<unsigned short const *,unsigned int,unsigned int,long,unsigned short *>(
          2148008452LL,
          v33,
          PackagedComInvalidCurrentVersion,
          v32);
        LODWORD(v37) = -2146958844;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x101B,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::FollowProgIdChain",
          "APPX_E_INVALID_MANIFEST",
          v37,
          -2146958844);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Buffer);
        goto LABEL_28;
      }
      v9 = OSIntegration::DEH::PackagedComExtensionHandler::FollowProgIdChain(
             this,
             (struct IXMLDOMElement *)v45.lpVtbl,
             string,
             a4);
LABEL_10:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Buffer);
      goto LABEL_29;
    }
    LODWORD(v35) = v28;
    v17 = "ParseAndRetrieveAttribute( progId.Get(), Internal::PackagedComConstants::currentVersionAttribute, currentVersi"
          "onProgId.GetAddressOf(), &currentVersionFound)";
    v18 = 4100;
LABEL_9:
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::FollowProgIdChain",
      v17,
      v35,
      v38);
    goto LABEL_10;
  }
  if ( a4 )
  {
    v26 = v43;
    v43 = 0;
    *a4 = v26;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Buffer);
  v9 = 0;
LABEL_29:
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v43);
  v43 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
  return v9;
}

```

## disassembly

```asm
0x1800d9e70  push    rbp
0x1800d9e72  push    rbx
0x1800d9e73  push    rsi
0x1800d9e74  push    rdi
0x1800d9e75  push    r12
0x1800d9e77  push    r13
0x1800d9e79  push    r14
0x1800d9e7b  push    r15
0x1800d9e7d  mov     rbp, rsp
0x1800d9e80  sub     rsp, 78h
0x1800d9e84  mov     rdi, r9
0x1800d9e87  mov     r14, r8
0x1800d9e8a  mov     r12, rdx
0x1800d9e8d  mov     rsi, rcx
0x1800d9e90  xor     r13d, r13d
0x1800d9e93  mov     [rbp+var_10.lpVtbl], r13
0x1800d9e97  mov     [rbp+var_20], r13
0x1800d9e9b  mov     [rbp+string], r13
0x1800d9e9f  mov     [rbp+var_37], r13b
0x1800d9ea3  mov     [rbp+var_38], r13b
0x1800d9ea7  mov     [rbp+arg_0], r13b
0x1800d9eab  mov     [rbp+var_30], r13
0x1800d9eaf  mov     rcx, [rcx+38h]
0x1800d9eb3  mov     rax, [rcx]
0x1800d9eb6  lea     r9, [rbp+arg_0]
0x1800d9eba  xor     r8d, r8d
0x1800d9ebd  mov     rdx, r14
0x1800d9ec0  mov     rax, [rax+50h]
0x1800d9ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9ec9  mov     ebx, eax
0x1800d9ecb  test    eax, eax
0x1800d9ecd  jns     short loc_1800D9F00
0x1800d9ecf  mov     rcx, [rbp+40h]; this
0x1800d9ed3  mov     dword ptr [rsp+78h+var_50], eax; char *
0x1800d9ed7  lea     rax, aProgidhelperli_1; "_progIdHelperList->Insert(currentVersio"...
0x1800d9ede  mov     [rsp+78h+var_58], rax; char *
0x1800d9ee3  lea     r9, aOsintegrationD_514; "OSIntegration::DEH::PackagedComExtensio"...
0x1800d9eea  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d9ef1  mov     edx, 0FC3h; void *
0x1800d9ef6  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d9efb  jmp     loc_1800DA2D6
0x1800d9f00  cmp     [rbp+arg_0], r13b
0x1800d9f04  jz      loc_1800DA001
0x1800d9f0a  lea     r9, [rbp+var_30]; struct APPX_XML_LINE_INFORMATION *
0x1800d9f0e  xor     r8d, r8d; unsigned __int16 *
0x1800d9f11  mov     rdx, r12; struct IXMLDOMNode *
0x1800d9f14  mov     rcx, [rsi+28h]; this
0x1800d9f18  call    ?GetXmlLineInformation@Package@OSIntegration@@QEBAJPEBUIXMLDOMNode@@PEBGPEAUAPPX_XML_LINE_INFORMATION@@@Z; OSIntegration::Package::GetXmlLineInformation(IXMLDOMNode const *,ushort const *,APPX_XML_LINE_INFORMATION *)
0x1800d9f1d  mov     rcx, [rbp+40h]; this
0x1800d9f21  mov     edi, 80080204h
0x1800d9f26  mov     dword ptr [rsp+78h+var_50], edi; char *
0x1800d9f2a  lea     rax, aHresult0x80080; "((HRESULT)0x80080204L)"
0x1800d9f31  mov     [rsp+78h+var_58], rax; char *
0x1800d9f36  lea     r9, aOsintegrationD_514; "OSIntegration::DEH::PackagedComExtensio"...
0x1800d9f3d  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d9f44  mov     edx, 0FD5h; void *
0x1800d9f49  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d9f4e  test    cs:byte_1802E21CA, 4
0x1800d9f55  jz      short loc_1800D9F91
0x1800d9f57  mov     rcx, [rsi+28h]
0x1800d9f5b  mov     rbx, [rcx+0E0h]
0x1800d9f62  mov     rcx, [rcx+110h]; unsigned __int16 *
0x1800d9f69  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x1800d9f6e  mov     qword ptr [rsp+78h+var_48], rbx
0x1800d9f73  mov     dword ptr [rsp+78h+var_50], edi
0x1800d9f77  mov     ecx, dword ptr [rbp+var_30+4]
0x1800d9f7a  mov     dword ptr [rsp+78h+var_58], ecx
0x1800d9f7e  mov     r9d, dword ptr [rbp+var_30]
0x1800d9f82  mov     r8, rax
0x1800d9f85  lea     rdx, PackagedComInvalidProgId
0x1800d9f8c  call    McTemplateU0zqqdz_EventWriteTransfer
0x1800d9f91  mov     rcx, [rsi+28h]
0x1800d9f95  mov     rbx, [rcx+0E0h]
0x1800d9f9c  mov     rcx, [rcx+110h]; unsigned __int16 *
0x1800d9fa3  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x1800d9fa8  mov     [rsp+78h+var_40], rbx
0x1800d9fad  mov     [rsp+78h+var_48], edi; int
0x1800d9fb1  mov     ecx, dword ptr [rbp+var_30+4]
0x1800d9fb4  mov     dword ptr [rsp+78h+var_50], ecx
0x1800d9fb8  mov     ecx, dword ptr [rbp+var_30]
0x1800d9fbb  mov     dword ptr [rsp+78h+var_58], ecx
0x1800d9fbf  mov     r9, rax
0x1800d9fc2  lea     r8, PackagedComInvalidProgId
0x1800d9fc9  mov     ecx, edi
0x1800d9fcb  call    ??$appxLog@PEBGIIJPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEBGIIJPEAG@Z; details::appxLog<ushort const *,uint,uint,long,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort const *,uint,uint,long,ushort *)
0x1800d9fd0  mov     rcx, [rbp+40h]; this
0x1800d9fd4  mov     dword ptr [rsp+78h+var_50], edi; char *
0x1800d9fd8  lea     rax, aAppxEInvalidMa; "APPX_E_INVALID_MANIFEST"
0x1800d9fdf  mov     [rsp+78h+var_58], rax; char *
0x1800d9fe4  lea     r9, aOsintegrationD_514; "OSIntegration::DEH::PackagedComExtensio"...
0x1800d9feb  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d9ff2  mov     edx, 0FD7h; void *
0x1800d9ff7  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d9ffc  jmp     loc_1800DA2D4
0x1800da001  mov     rcx, r14; string
0x1800da004  call    cs:__imp_WindowsGetStringLen
0x1800da00a  mov     r15d, eax
0x1800da00d  lea     r8, [r15+81h]
0x1800da014  xor     edx, edx
0x1800da016  lea     rcx, [rbp+Buffer]
0x1800da01a  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800da01f  nop
0x1800da020  mov     rbx, [rbp+Buffer]
0x1800da024  test    rbx, rbx
0x1800da027  jnz     short loc_1800DA069
0x1800da029  mov     ebx, 8007000Eh
0x1800da02e  mov     dword ptr [rsp+78h+var_50], ebx; char *
0x1800da032  lea     rax, aXpath_0; "xpath"
0x1800da039  mov     edx, 0FE1h; void *
0x1800da03e  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800da045  lea     r9, aOsintegrationD_514; "OSIntegration::DEH::PackagedComExtensio"...
0x1800da04c  mov     [rsp+78h+var_58], rax; char *
0x1800da051  mov     rcx, [rbp+40h]; this
0x1800da055  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800da05a  nop
0x1800da05b  lea     rcx, [rbp+Buffer]
0x1800da05f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800da064  jmp     loc_1800DA2D6
0x1800da069  xor     edx, edx; length
0x1800da06b  mov     rcx, r14; string
0x1800da06e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800da074  mov     r9, rax
0x1800da077  lea     r8, aLocalNameExten_3; "//*[local-name()='Extension' and @Categ"...
0x1800da07e  lea     rdx, [r15+81h]; unsigned __int64
0x1800da085  mov     rcx, rbx; Buffer
0x1800da088  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800da08d  mov     r14d, eax
0x1800da090  test    eax, eax
0x1800da092  jns     short loc_1800DA0D2
0x1800da094  mov     rcx, [rbp+40h]; this
0x1800da098  mov     dword ptr [rsp+78h+var_50], eax; char *
0x1800da09c  lea     rax, aStringcchprint_27; "StringCchPrintf( xpath.get(), cchxpath,"...
0x1800da0a3  mov     [rsp+78h+var_58], rax; char *
0x1800da0a8  lea     r9, aOsintegrationD_514; "OSIntegration::DEH::PackagedComExtensio"...
0x1800da0af  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800da0b6  mov     edx, 0FE7h; void *
0x1800da0bb  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800da0c0  nop
0x1800da0c1  lea     rcx, [rbp+Buffer]
0x1800da0c5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800da0ca  mov     ebx, r14d
0x1800da0cd  jmp     loc_1800DA2D6
0x1800da0d2  lea     rcx, [rbp+var_10]
0x1800da0d6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800da0db  lea     r8, [rbp+var_10]; struct IXMLDOMElement *
0x1800da0df  mov     rdx, r12; unsigned __int16 *
0x1800da0e2  mov     rcx, rbx; strIn
0x1800da0e5  call    ?GetXMLElementFromQuery@Xml@Common@@YAJPEBGPEAUIXMLDOMElement@@PEAPEAU3@@Z; Common::Xml::GetXMLElementFromQuery(ushort const *,IXMLDOMElement *,IXMLDOMElement * *)
0x1800da0ea  mov     ebx, eax
0x1800da0ec  test    eax, eax
0x1800da0ee  jns     short loc_1800DA105
0x1800da0f0  mov     dword ptr [rsp+78h+var_50], eax
0x1800da0f4  lea     rax, aGetxmlelementf_10; "GetXMLElementFromQuery(xpath.get(), pre"...
0x1800da0fb  mov     edx, 0FEBh
0x1800da100  jmp     loc_1800DA03E
0x1800da105  mov     rcx, [rbp+var_20]; string
0x1800da109  call    cs:__imp_WindowsDeleteString
0x1800da10f  mov     [rbp+var_20], r13
0x1800da113  lea     rax, [rbp+var_38]
0x1800da117  mov     [rsp+78h+var_58], rax; bool *
0x1800da11c  lea     r9, [rbp+var_20]; HSTRING *
0x1800da120  lea     r8, stru_180255228; unsigned __int16 *
0x1800da127  mov     rdx, [rbp+var_10.lpVtbl]; struct IXMLDOMElement *
0x1800da12b  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x1800da130  mov     ebx, eax
0x1800da132  test    eax, eax
0x1800da134  jns     short loc_1800DA14B
0x1800da136  mov     dword ptr [rsp+78h+var_50], eax
0x1800da13a  lea     rax, aParseandretrie_29; "ParseAndRetrieveAttribute( progId.Get()"...
0x1800da141  mov     edx, 0FF2h
0x1800da146  jmp     loc_1800DA03E
0x1800da14b  cmp     [rbp+var_38], r13b
0x1800da14f  jz      short loc_1800DA172
0x1800da151  test    rdi, rdi
0x1800da154  jz      short loc_1800DA161
0x1800da156  mov     rax, [rbp+var_20]
0x1800da15a  mov     [rbp+var_20], r13
0x1800da15e  mov     [rdi], rax
0x1800da161  lea     rcx, [rbp+Buffer]
0x1800da165  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800da16a  mov     ebx, r13d
0x1800da16d  jmp     loc_1800DA2D6
0x1800da172  mov     rcx, [rbp+string]; string
0x1800da176  call    cs:__imp_WindowsDeleteString
0x1800da17c  mov     [rbp+string], r13
0x1800da180  lea     rax, [rbp+var_37]
0x1800da184  mov     [rsp+78h+var_58], rax; bool *
0x1800da189  lea     r9, [rbp+string]; HSTRING *
0x1800da18d  lea     r8, aCurrentversion; "CurrentVersion"
0x1800da194  mov     rdx, [rbp+var_10.lpVtbl]; struct IXMLDOMElement *
0x1800da198  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x1800da19d  mov     ebx, eax
0x1800da19f  test    eax, eax
0x1800da1a1  jns     short loc_1800DA1B8
0x1800da1a3  mov     dword ptr [rsp+78h+var_50], eax
0x1800da1a7  lea     rax, aParseandretrie_60; "ParseAndRetrieveAttribute( progId.Get()"...
0x1800da1ae  mov     edx, 1004h
0x1800da1b3  jmp     loc_1800DA03E
0x1800da1b8  cmp     [rbp+var_37], r13b
0x1800da1bc  jz      short loc_1800DA1D8
0x1800da1be  mov     r9, rdi; HSTRING *
0x1800da1c1  mov     r8, [rbp+string]; HSTRING
0x1800da1c5  mov     rdx, [rbp+var_10.lpVtbl]; struct IXMLDOMElement *
0x1800da1c9  mov     rcx, rsi; this
0x1800da1cc  call    ?FollowProgIdChain@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEAUHSTRING__@@PEAPEAU5@@Z; OSIntegration::DEH::PackagedComExtensionHandler::FollowProgIdChain(IXMLDOMElement *,HSTRING__ *,HSTRING__ * *)
0x1800da1d1  mov     ebx, eax
0x1800da1d3  jmp     loc_1800DA05B
0x1800da1d8  lea     r9, [rbp+var_30]; struct APPX_XML_LINE_INFORMATION *
0x1800da1dc  xor     r8d, r8d; unsigned __int16 *
0x1800da1df  mov     rdx, r12; struct IXMLDOMNode *
0x1800da1e2  mov     rcx, [rsi+28h]; this
0x1800da1e6  call    ?GetXmlLineInformation@Package@OSIntegration@@QEBAJPEBUIXMLDOMNode@@PEBGPEAUAPPX_XML_LINE_INFORMATION@@@Z; OSIntegration::Package::GetXmlLineInformation(IXMLDOMNode const *,ushort const *,APPX_XML_LINE_INFORMATION *)
0x1800da1eb  mov     rcx, [rbp+40h]; this
0x1800da1ef  mov     edi, 80080204h
0x1800da1f4  mov     dword ptr [rsp+78h+var_50], edi; char *
0x1800da1f8  lea     rax, aHresult0x80080; "((HRESULT)0x80080204L)"
0x1800da1ff  mov     [rsp+78h+var_58], rax; char *
0x1800da204  lea     r9, aOsintegrationD_514; "OSIntegration::DEH::PackagedComExtensio"...
0x1800da20b  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800da212  mov     edx, 1019h; void *
0x1800da217  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800da21c  test    cs:byte_1802E21CA, 4
0x1800da223  jz      short loc_1800DA25F
0x1800da225  mov     rcx, [rsi+28h]
0x1800da229  mov     rbx, [rcx+0E0h]
0x1800da230  mov     rcx, [rcx+110h]; unsigned __int16 *
0x1800da237  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x1800da23c  mov     qword ptr [rsp+78h+var_48], rbx
0x1800da241  mov     dword ptr [rsp+78h+var_50], edi
0x1800da245  mov     ecx, dword ptr [rbp+var_30+4]
0x1800da248  mov     dword ptr [rsp+78h+var_58], ecx
0x1800da24c  mov     r9d, dword ptr [rbp+var_30]
0x1800da250  mov     r8, rax
0x1800da253  lea     rdx, PackagedComInvalidCurrentVersion
0x1800da25a  call    McTemplateU0zqqdz_EventWriteTransfer
0x1800da25f  mov     rcx, [rsi+28h]
0x1800da263  mov     rbx, [rcx+0E0h]
0x1800da26a  mov     rcx, [rcx+110h]; unsigned __int16 *
0x1800da271  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x1800da276  mov     [rsp+78h+var_40], rbx
0x1800da27b  mov     [rsp+78h+var_48], edi; int
0x1800da27f  mov     ecx, dword ptr [rbp+var_30+4]
0x1800da282  mov     dword ptr [rsp+78h+var_50], ecx
0x1800da286  mov     ecx, dword ptr [rbp+var_30]
0x1800da289  mov     dword ptr [rsp+78h+var_58], ecx
0x1800da28d  mov     r9, rax
0x1800da290  lea     r8, PackagedComInvalidCurrentVersion
0x1800da297  mov     ecx, edi
0x1800da299  call    ??$appxLog@PEBGIIJPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEBGIIJPEAG@Z; details::appxLog<ushort const *,uint,uint,long,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort const *,uint,uint,long,ushort *)
0x1800da29e  mov     rcx, [rbp+40h]; this
0x1800da2a2  mov     dword ptr [rsp+78h+var_50], edi; char *
0x1800da2a6  lea     rax, aAppxEInvalidMa; "APPX_E_INVALID_MANIFEST"
0x1800da2ad  mov     [rsp+78h+var_58], rax; char *
0x1800da2b2  lea     r9, aOsintegrationD_514; "OSIntegration::DEH::PackagedComExtensio"...
0x1800da2b9  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800da2c0  mov     edx, 101Bh; void *
0x1800da2c5  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800da2ca  nop
0x1800da2cb  lea     rcx, [rbp+Buffer]
0x1800da2cf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800da2d4  mov     ebx, edi
0x1800da2d6  mov     rcx, [rbp+string]; string
0x1800da2da  call    cs:__imp_WindowsDeleteString
0x1800da2e0  mov     [rbp+string], r13
0x1800da2e4  mov     rcx, [rbp+var_20]; string
0x1800da2e8  call    cs:__imp_WindowsDeleteString
0x1800da2ee  mov     [rbp+var_20], r13
0x1800da2f2  lea     rcx, [rbp+var_10]
0x1800da2f6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800da2fb  mov     eax, ebx
0x1800da2fd  add     rsp, 78h
0x1800da301  pop     r15
0x1800da303  pop     r14
0x1800da305  pop     r13
0x1800da307  pop     r12
0x1800da309  pop     rdi
0x1800da30a  pop     rsi
0x1800da30b  pop     rbx
0x1800da30c  pop     rbp
0x1800da30d  retn
```
