# OSIntegration::DEH::PackagedComExtensionHandler::VerifyVersionIndependentProgId(IXMLDOMElement *,HSTRING__ *)

- ea: `0x1800d70e0`
- end: `0x1800d740f`
- name: `?VerifyVersionIndependentProgId@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEAUHSTRING__@@@Z`
- size: `815`
- prototype: `int(OSIntegration::DEH::PackagedComExtensionHandler *__hidden this, struct IXMLDOMElement *, HSTRING)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180078b84`

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
- `0x1800d70e0`
- `0x18013ced4`
- `0x18013d6f8`
- `0x18016faf4`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800d7118`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800d7118`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d7157`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d7157`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d71c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d721c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d73e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d73fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d71c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d721c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d73e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d73fa`

## string_xrefs

- `0x1800d7310`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800d73bf`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800d73a3`: `APPX_E_INVALID_MANIFEST`
- `0x1800d7141`: `xpath`
- `0x1800d7309`: `OSIntegration::DEH::PackagedComExtensionHandler::VerifyVersionIndependentProgId`
- `0x1800d73b8`: `OSIntegration::DEH::PackagedComExtensionHandler::VerifyVersionIndependentProgId`
- `0x1800d7160`: `//*[local-name()='Extension' and @Category='windows.comServer']/*[local-name()='ComServer']/*[local-name()='ProgId' and @Id='%ls']`
- `0x1800d71b3`: `GetXMLElementFromQuery(xpath.get(), element, &progId)`
- `0x1800d7250`: `ParseAndRetrieveAttribute( element, Internal::PackagedComConstants::idAttribute, classId.GetAddressOf())`
- `0x1800d7180`: `StringCchPrintf( xpath.get(), cchxpath, Internal::PackagedComConstants::progIdWithIdFormat, ::WindowsGetStringRawBuffer(versionIndependentProgId, nullptr))`
- `0x1800d71fd`: `ParseAndRetrieveAttribute( progId.Get(), Internal::PackagedComConstants::currentVersionAttribute, currentVersion.GetAddressOf(), &currentVersionFound)`
- `0x1800d7289`: `_progIdHelperList->Insert(versionIndependentProgId, nullptr, &replaced)`
- `0x1800d72bd`: `VerifyVersionIndependentProgIdHelper( progId.Get(), currentVersion.Get(), classId.Get(), versionIndependentProgId)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OSIntegration::DEH::PackagedComExtensionHandler::VerifyVersionIndependentProgId(
        OSIntegration::Package **this,
        struct IXMLDOMElement *a2,
        HSTRING a3)
{
  __int64 StringLen; // rdi
  wchar_t *v7; // rbx
  unsigned int v8; // edi
  const char *v9; // rax
  __int64 v10; // rdx
  PCWSTR StringRawBuffer; // rax
  int v12; // eax
  struct IXMLDOMElement **v13; // r9
  int XMLElementFromQuery; // eax
  OSIntegration::DEH::PackagedComExtensionHandler *v15; // rcx
  int v16; // eax
  OSIntegration::DEH::PackagedComExtensionHandler *v17; // rcx
  int v18; // eax
  int v19; // eax
  int v20; // eax
  OSIntegration::Package *v21; // rcx
  __int64 v22; // rbx
  unsigned int v23; // eax
  const unsigned __int16 *v24; // rax
  __int64 v25; // rdx
  char *v27; // [rsp+28h] [rbp-50h]
  int v28; // [rsp+30h] [rbp-48h]
  HSTRING string; // [rsp+40h] [rbp-38h] BYREF
  __int64 v30; // [rsp+48h] [rbp-30h] BYREF
  struct IXMLDOMElement v31; // [rsp+50h] [rbp-28h] BYREF
  HSTRING v32; // [rsp+58h] [rbp-20h] BYREF
  wchar_t *Buffer[3]; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+A8h] [rbp+30h]
  bool v35; // [rsp+C8h] [rbp+50h] BYREF

  v32 = 0;
  string = 0;
  v31.lpVtbl = 0;
  v35 = 0;
  StringLen = WindowsGetStringLen(a3);
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    Buffer,
    0,
    StringLen + 129);
  v7 = Buffer[0];
  if ( !Buffer[0] )
  {
    v8 = -2147024882;
    v9 = "xpath";
    v10 = 3884;
LABEL_20:
    LODWORD(v27) = v8;
    goto LABEL_21;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
  v12 = StringCchPrintfW(
          v7,
          StringLen + 129,
          L"//*[local-name()='Extension' and @Category='windows.comServer']/*[local-name()='ComServer']/*[local-name()='Pr"
           "ogId' and @Id='%ls']",
          StringRawBuffer);
  v8 = v12;
  if ( v12 < 0 )
  {
    LODWORD(v27) = v12;
    v9 = "StringCchPrintf( xpath.get(), cchxpath, Internal::PackagedComConstants::progIdWithIdFormat, ::WindowsGetStringR"
         "awBuffer(versionIndependentProgId, nullptr))";
    v10 = 3890;
LABEL_21:
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::VerifyVersionIndependentProgId",
      v9,
      v27,
      v28);
    goto LABEL_22;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  XMLElementFromQuery = Common::Xml::GetXMLElementFromQuery(v7, (const unsigned __int16 *)a2, &v31, v13);
  v8 = XMLElementFromQuery;
  if ( XMLElementFromQuery < 0 )
  {
    LODWORD(v27) = XMLElementFromQuery;
    v9 = "GetXMLElementFromQuery(xpath.get(), element, &progId)";
    v10 = 3894;
    goto LABEL_21;
  }
  WindowsDeleteString(string);
  string = 0;
  v16 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(
          v15,
          (struct IXMLDOMElement *)v31.lpVtbl,
          (struct IXMLDOMElement *)L"CurrentVersion",
          &string,
          &v35);
  v8 = v16;
  if ( v16 < 0 )
  {
    LODWORD(v27) = v16;
    v9 = "ParseAndRetrieveAttribute( progId.Get(), Internal::PackagedComConstants::currentVersionAttribute, currentVersio"
         "n.GetAddressOf(), &currentVersionFound)";
    v10 = 3901;
    goto LABEL_21;
  }
  if ( !v35 )
  {
    v30 = 0;
    OSIntegration::Package::GetXmlLineInformation(
      this[5],
      (const struct IXMLDOMNode *)a2,
      0,
      (struct APPX_XML_LINE_INFORMATION *)&v30);
    v8 = -2146958844;
    LODWORD(v27) = -2146958844;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0xF60,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::VerifyVersionIndependentProgId",
      "((HRESULT)0x80080204L)",
      v27,
      v28);
    if ( (byte_1802E21CA & 4) != 0 )
    {
      v21 = this[5];
      v22 = *((_QWORD *)v21 + 28);
      v23 = (unsigned int)RemovePIIfromFilePath(*((const unsigned __int16 **)v21 + 34));
      McTemplateU0zqqdz_EventWriteTransfer(
        HIDWORD(v30),
        (unsigned int)PackagedComInvalidClassVersionIndependentProgIdCurrentVersion,
        v23,
        v30,
        SBYTE4(v30),
        4,
        v22);
    }
    v24 = RemovePIIfromFilePath(*((const unsigned __int16 **)this[5] + 34));
    v28 = -2146958844;
    details::appxLog<unsigned short const *,unsigned int,unsigned int,long,unsigned short *>(
      2148008452LL,
      v25,
      PackagedComInvalidClassVersionIndependentProgIdCurrentVersion,
      v24,
      v30,
      HIDWORD(v30));
    v9 = "APPX_E_INVALID_MANIFEST";
    v10 = 3938;
    goto LABEL_20;
  }
  WindowsDeleteString(v32);
  v32 = 0;
  v18 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(
          v17,
          a2,
          (struct IXMLDOMElement *)&stru_180231B98,
          &v32,
          0);
  v8 = v18;
  if ( v18 < 0 )
  {
    LODWORD(v27) = v18;
    v9 = "ParseAndRetrieveAttribute( element, Internal::PackagedComConstants::idAttribute, classId.GetAddressOf())";
    v10 = 3909;
    goto LABEL_21;
  }
  v35 = 0;
  v19 = (*(__int64 (__fastcall **)(OSIntegration::Package *, HSTRING, _QWORD, bool *))(*(_QWORD *)this[7] + 80LL))(
          this[7],
          a3,
          0,
          &v35);
  v8 = v19;
  if ( v19 < 0 )
  {
    LODWORD(v27) = v19;
    v9 = "_progIdHelperList->Insert(versionIndependentProgId, nullptr, &replaced)";
    v10 = 3913;
    goto LABEL_21;
  }
  v20 = OSIntegration::DEH::PackagedComExtensionHandler::VerifyVersionIndependentProgIdHelper(
          (OSIntegration::DEH::PackagedComExtensionHandler *)this,
          (struct IXMLDOMElement *)v31.lpVtbl,
          string,
          v32,
          a3);
  v8 = v20;
  if ( v20 < 0 )
  {
    LODWORD(v27) = v20;
    v9 = "VerifyVersionIndependentProgIdHelper( progId.Get(), currentVersion.Get(), classId.Get(), versionIndependentProgId)";
    v10 = 3919;
    goto LABEL_21;
  }
  v8 = 0;
LABEL_22:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(Buffer);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v32);
  return v8;
}

```

## disassembly

```asm
0x1800d70e0  push    rbp
0x1800d70e2  push    rbx
0x1800d70e3  push    rsi
0x1800d70e4  push    rdi
0x1800d70e5  push    r14
0x1800d70e7  push    r15
0x1800d70e9  mov     rbp, rsp
0x1800d70ec  sub     rsp, 78h
0x1800d70f0  mov     rsi, r8
0x1800d70f3  mov     r15, rdx
0x1800d70f6  mov     r14, rcx
0x1800d70f9  mov     [rbp+var_20], 0
0x1800d7101  mov     [rbp+string], 0
0x1800d7109  mov     [rbp+var_28.lpVtbl], 0
0x1800d7111  mov     [rbp+arg_18], 0
0x1800d7115  mov     rcx, r8; string
0x1800d7118  call    cs:__imp_WindowsGetStringLen
0x1800d711e  mov     edi, eax
0x1800d7120  lea     r8, [rdi+81h]
0x1800d7127  xor     edx, edx
0x1800d7129  lea     rcx, [rbp+Buffer]
0x1800d712d  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800d7132  nop
0x1800d7133  mov     rbx, [rbp+Buffer]
0x1800d7137  test    rbx, rbx
0x1800d713a  jnz     short loc_1800D7152
0x1800d713c  mov     edi, 8007000Eh
0x1800d7141  lea     rax, aXpath_0; "xpath"
0x1800d7148  mov     edx, 0F2Ch
0x1800d714d  jmp     loc_1800D73AF
0x1800d7152  xor     edx, edx; length
0x1800d7154  mov     rcx, rsi; string
0x1800d7157  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d715d  mov     r9, rax
0x1800d7160  lea     r8, aLocalNameExten_3; "//*[local-name()='Extension' and @Categ"...
0x1800d7167  lea     rdx, [rdi+81h]; unsigned __int64
0x1800d716e  mov     rcx, rbx; Buffer
0x1800d7171  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800d7176  mov     edi, eax
0x1800d7178  test    eax, eax
0x1800d717a  jns     short loc_1800D7191
0x1800d717c  mov     dword ptr [rsp+78h+var_50], eax
0x1800d7180  lea     rax, aStringcchprint_11; "StringCchPrintf( xpath.get(), cchxpath,"...
0x1800d7187  mov     edx, 0F32h
0x1800d718c  jmp     loc_1800D73B3
0x1800d7191  lea     rcx, [rbp+var_28]
0x1800d7195  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d719a  lea     r8, [rbp+var_28]; struct IXMLDOMElement *
0x1800d719e  mov     rdx, r15; unsigned __int16 *
0x1800d71a1  mov     rcx, rbx; strIn
0x1800d71a4  call    ?GetXMLElementFromQuery@Xml@Common@@YAJPEBGPEAUIXMLDOMElement@@PEAPEAU3@@Z; Common::Xml::GetXMLElementFromQuery(ushort const *,IXMLDOMElement *,IXMLDOMElement * *)
0x1800d71a9  mov     edi, eax
0x1800d71ab  test    eax, eax
0x1800d71ad  jns     short loc_1800D71C4
0x1800d71af  mov     dword ptr [rsp+78h+var_50], eax
0x1800d71b3  lea     rax, aGetxmlelementf_6; "GetXMLElementFromQuery(xpath.get(), ele"...
0x1800d71ba  mov     edx, 0F36h
0x1800d71bf  jmp     loc_1800D73B3
0x1800d71c4  mov     rcx, [rbp+string]; string
0x1800d71c8  call    cs:__imp_WindowsDeleteString
0x1800d71ce  mov     [rbp+string], 0
0x1800d71d6  lea     rax, [rbp+arg_18]
0x1800d71da  mov     [rsp+78h+var_58], rax; bool *
0x1800d71df  lea     r9, [rbp+string]; HSTRING *
0x1800d71e3  lea     r8, aCurrentversion; "CurrentVersion"
0x1800d71ea  mov     rdx, [rbp+var_28.lpVtbl]; struct IXMLDOMElement *
0x1800d71ee  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x1800d71f3  mov     edi, eax
0x1800d71f5  test    eax, eax
0x1800d71f7  jns     short loc_1800D720E
0x1800d71f9  mov     dword ptr [rsp+78h+var_50], eax
0x1800d71fd  lea     rax, aParseandretrie_46; "ParseAndRetrieveAttribute( progId.Get()"...
0x1800d7204  mov     edx, 0F3Dh
0x1800d7209  jmp     loc_1800D73B3
0x1800d720e  cmp     [rbp+arg_18], 0
0x1800d7212  jz      loc_1800D72D5
0x1800d7218  mov     rcx, [rbp+var_20]; string
0x1800d721c  call    cs:__imp_WindowsDeleteString
0x1800d7222  mov     [rbp+var_20], 0
0x1800d722a  mov     [rsp+78h+var_58], 0; bool *
0x1800d7233  lea     r9, [rbp+var_20]; HSTRING *
0x1800d7237  lea     r8, stru_180231B98; unsigned __int16 *
0x1800d723e  mov     rdx, r15; struct IXMLDOMElement *
0x1800d7241  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x1800d7246  mov     edi, eax
0x1800d7248  test    eax, eax
0x1800d724a  jns     short loc_1800D7261
0x1800d724c  mov     dword ptr [rsp+78h+var_50], eax
0x1800d7250  lea     rax, aParseandretrie_78; "ParseAndRetrieveAttribute( element, Int"...
0x1800d7257  mov     edx, 0F45h
0x1800d725c  jmp     loc_1800D73B3
0x1800d7261  mov     [rbp+arg_18], 0
0x1800d7265  mov     rcx, [r14+38h]
0x1800d7269  mov     rax, [rcx]
0x1800d726c  lea     r9, [rbp+arg_18]
0x1800d7270  xor     r8d, r8d
0x1800d7273  mov     rdx, rsi
0x1800d7276  mov     rax, [rax+50h]
0x1800d727a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d727f  mov     edi, eax
0x1800d7281  test    eax, eax
0x1800d7283  jns     short loc_1800D729A
0x1800d7285  mov     dword ptr [rsp+78h+var_50], eax
0x1800d7289  lea     rax, aProgidhelperli_2; "_progIdHelperList->Insert(versionIndepe"...
0x1800d7290  mov     edx, 0F49h
0x1800d7295  jmp     loc_1800D73B3
0x1800d729a  mov     [rsp+78h+var_58], rsi; HSTRING
0x1800d729f  mov     r9, [rbp+var_20]; HSTRING
0x1800d72a3  mov     r8, [rbp+string]; HSTRING
0x1800d72a7  mov     rdx, [rbp+var_28.lpVtbl]; struct IXMLDOMElement *
0x1800d72ab  mov     rcx, r14; this
0x1800d72ae  call    ?VerifyVersionIndependentProgIdHelper@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEAUHSTRING__@@11@Z; OSIntegration::DEH::PackagedComExtensionHandler::VerifyVersionIndependentProgIdHelper(IXMLDOMElement *,HSTRING__ *,HSTRING__ *,HSTRING__ *)
0x1800d72b3  mov     edi, eax
0x1800d72b5  test    eax, eax
0x1800d72b7  jns     short loc_1800D72CE
0x1800d72b9  mov     dword ptr [rsp+78h+var_50], eax
0x1800d72bd  lea     rax, aVerifyversioni; "VerifyVersionIndependentProgIdHelper( p"...
0x1800d72c4  mov     edx, 0F4Fh
0x1800d72c9  jmp     loc_1800D73B3
0x1800d72ce  xor     edi, edi
0x1800d72d0  jmp     loc_1800D73D0
0x1800d72d5  mov     [rbp+var_30], 0
0x1800d72dd  lea     r9, [rbp+var_30]; struct APPX_XML_LINE_INFORMATION *
0x1800d72e1  xor     r8d, r8d; unsigned __int16 *
0x1800d72e4  mov     rdx, r15; struct IXMLDOMNode *
0x1800d72e7  mov     rcx, [r14+28h]; this
0x1800d72eb  call    ?GetXmlLineInformation@Package@OSIntegration@@QEBAJPEBUIXMLDOMNode@@PEBGPEAUAPPX_XML_LINE_INFORMATION@@@Z; OSIntegration::Package::GetXmlLineInformation(IXMLDOMNode const *,ushort const *,APPX_XML_LINE_INFORMATION *)
0x1800d72f0  mov     rcx, [rbp+30h]; this
0x1800d72f4  mov     edi, 80080204h
0x1800d72f9  mov     dword ptr [rsp+78h+var_50], edi; char *
0x1800d72fd  lea     rax, aHresult0x80080; "((HRESULT)0x80080204L)"
0x1800d7304  mov     [rsp+78h+var_58], rax; char *
0x1800d7309  lea     r9, aOsintegrationD_358; "OSIntegration::DEH::PackagedComExtensio"...
0x1800d7310  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d7317  mov     edx, 0F60h; void *
0x1800d731c  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d7321  test    cs:byte_1802E21CA, 4
0x1800d7328  jz      short loc_1800D7364
0x1800d732a  mov     rcx, [r14+28h]
0x1800d732e  mov     rbx, [rcx+0E0h]
0x1800d7335  mov     rcx, [rcx+110h]; unsigned __int16 *
0x1800d733c  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x1800d7341  mov     qword ptr [rsp+78h+var_48], rbx
0x1800d7346  mov     dword ptr [rsp+78h+var_50], edi
0x1800d734a  mov     ecx, dword ptr [rbp+var_30+4]
0x1800d734d  mov     dword ptr [rsp+78h+var_58], ecx
0x1800d7351  mov     r9d, dword ptr [rbp+var_30]
0x1800d7355  mov     r8, rax
0x1800d7358  lea     rdx, PackagedComInvalidClassVersionIndependentProgIdCurrentVersion
0x1800d735f  call    McTemplateU0zqqdz_EventWriteTransfer
0x1800d7364  mov     rcx, [r14+28h]
0x1800d7368  mov     rbx, [rcx+0E0h]
0x1800d736f  mov     rcx, [rcx+110h]; unsigned __int16 *
0x1800d7376  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x1800d737b  mov     [rsp+78h+var_40], rbx
0x1800d7380  mov     [rsp+78h+var_48], edi; int
0x1800d7384  mov     ecx, dword ptr [rbp+var_30+4]
0x1800d7387  mov     dword ptr [rsp+78h+var_50], ecx
0x1800d738b  mov     ecx, dword ptr [rbp+var_30]
0x1800d738e  mov     dword ptr [rsp+78h+var_58], ecx
0x1800d7392  mov     r9, rax
0x1800d7395  lea     r8, PackagedComInvalidClassVersionIndependentProgIdCurrentVersion
0x1800d739c  mov     ecx, edi
0x1800d739e  call    ??$appxLog@PEBGIIJPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEBGIIJPEAG@Z; details::appxLog<ushort const *,uint,uint,long,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort const *,uint,uint,long,ushort *)
0x1800d73a3  lea     rax, aAppxEInvalidMa; "APPX_E_INVALID_MANIFEST"
0x1800d73aa  mov     edx, 0F62h; void *
0x1800d73af  mov     dword ptr [rsp+78h+var_50], edi; char *
0x1800d73b3  mov     [rsp+78h+var_58], rax; char *
0x1800d73b8  lea     r9, aOsintegrationD_358; "OSIntegration::DEH::PackagedComExtensio"...
0x1800d73bf  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d73c6  mov     rcx, [rbp+30h]; this
0x1800d73ca  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d73cf  nop
0x1800d73d0  lea     rcx, [rbp+Buffer]
0x1800d73d4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d73d9  nop
0x1800d73da  lea     rcx, [rbp+var_28]
0x1800d73de  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d73e3  nop
0x1800d73e4  mov     rcx, [rbp+string]; string
0x1800d73e8  call    cs:__imp_WindowsDeleteString
0x1800d73ee  mov     [rbp+string], 0
0x1800d73f6  mov     rcx, [rbp+var_20]; string
0x1800d73fa  call    cs:__imp_WindowsDeleteString
0x1800d7400  mov     eax, edi
0x1800d7402  add     rsp, 78h
0x1800d7406  pop     r15
0x1800d7408  pop     r14
0x1800d740a  pop     rdi
0x1800d740b  pop     rsi
0x1800d740c  pop     rbx
0x1800d740d  pop     rbp
0x1800d740e  retn
```
