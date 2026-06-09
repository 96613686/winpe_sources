# OSIntegration::DEH::PackagedComExtensionHandler::VerifyInterface(IXMLDOMElement *,bool)

- ea: `0x1800d90e8`
- end: `0x1800d94c3`
- name: `?VerifyInterface@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@_N@Z`
- size: `987`
- prototype: `int(OSIntegration::DEH::PackagedComExtensionHandler *__hidden this, struct IXMLDOMElement *, bool)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007762c`

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
- `0x1800d90e8`
- `0x18013ced4`
- `0x18013d6f8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d9209`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d9218`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d9227`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d92cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d92db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d92ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d9209`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d9218`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d9227`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d92cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d92db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d92ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d9132`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d9170`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d91c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d948e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d949c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d94aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d9132`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d9170`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d91c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d948e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d949c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d94aa`

## string_xrefs

- `0x1800d91b4`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800d929b`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800d9330`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800d93d1`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800d9464`: `APPX_E_INVALID_MANIFEST`
- `0x1800d928f`: `xpath`
- `0x1800d91ad`: `OSIntegration::DEH::PackagedComExtensionHandler::VerifyInterface`
- `0x1800d92a2`: `OSIntegration::DEH::PackagedComExtensionHandler::VerifyInterface`
- `0x1800d9337`: `OSIntegration::DEH::PackagedComExtensionHandler::VerifyInterface`
- `0x1800d93ca`: `OSIntegration::DEH::PackagedComExtensionHandler::VerifyInterface`
- `0x1800d9302`: `//*[local-name()='Extension' and @Category='windows.comInterface']/*[local-name()='ComInterface']/*[local-name()='Interface' and @Id='%ls' and @%ls='%ls' and @ProxyStubClsid='%ls']`
- `0x1800d915e`: `ParseAndRetrieveAttribute( element, Internal::PackagedComConstants::idAttribute, interfaceId.GetAddressOf())`
- `0x1800d91f5`: `ParseAndRetrieveAttribute( element, Internal::PackagedComConstants::proxyStubClsidAttribute, proxyStub.GetAddressOf())`
- `0x1800d9320`: `StringCchPrintf( xpath.get(), cchxpath, Internal::PackagedComConstants::interfaceFormat, interfaceToBeVerified.GetRawBuffer(nullptr), formatHelper, interfaceId.GetRawBuffer(nullptr), proxyStub.GetRawBuffer(nullptr))`
- `0x1800d937f`: `GetXMLElementFromQuery(xpath.get(), element, &interfaceObtained)`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall OSIntegration::DEH::PackagedComExtensionHandler::VerifyInterface(
        OSIntegration::Package **this,
        struct IXMLDOMElement *a2,
        char a3)
{
  const unsigned __int16 *v5; // r12
  struct IXMLDOMElement *v6; // rdi
  OSIntegration::DEH::PackagedComExtensionHandler *v7; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  const char *v10; // rax
  __int64 v11; // rdx
  OSIntegration::DEH::PackagedComExtensionHandler *v12; // rcx
  int v13; // eax
  OSIntegration::DEH::PackagedComExtensionHandler *v14; // rcx
  int v15; // eax
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v17; // rdi
  PCWSTR v18; // rax
  __int64 v19; // rcx
  __int64 v20; // r9
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // r15
  wchar_t *v24; // rbx
  const char *v25; // rax
  __int64 v26; // rdx
  int v27; // esi
  PCWSTR v28; // rdi
  PCWSTR v29; // rax
  int v30; // edi
  const char *v31; // rax
  __int64 v32; // rdx
  struct IXMLDOMElement **v33; // r9
  int XMLElementFromQuery; // eax
  OSIntegration::Package *v35; // rcx
  __int64 v36; // rbx
  unsigned int v37; // eax
  const unsigned __int16 *v38; // rax
  __int64 v39; // rdx
  char *v41; // [rsp+28h] [rbp-50h]
  int v42; // [rsp+30h] [rbp-48h]
  HSTRING string; // [rsp+40h] [rbp-38h] BYREF
  wchar_t *Buffer; // [rsp+48h] [rbp-30h] BYREF
  __int64 v45; // [rsp+50h] [rbp-28h] BYREF
  HSTRING v46; // [rsp+58h] [rbp-20h] BYREF
  struct IXMLDOMElement v47; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+B8h] [rbp+40h]
  HSTRING v49; // [rsp+D8h] [rbp+60h] BYREF

  v46 = 0;
  string = 0;
  v49 = 0;
  v47.lpVtbl = 0;
  v5 = L"SynchronousInterface";
  v6 = (struct IXMLDOMElement *)&stru_18023F1B8;
  if ( !a3 )
  {
    v6 = (struct IXMLDOMElement *)L"SynchronousInterface";
    v5 = (const unsigned __int16 *)&stru_18023F1B8;
  }
  WindowsDeleteString(0);
  v46 = 0;
  v8 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(
         v7,
         a2,
         (struct IXMLDOMElement *)&stru_180231B98,
         &v46,
         0);
  v9 = v8;
  if ( v8 >= 0 )
  {
    WindowsDeleteString(string);
    string = 0;
    v13 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(v12, a2, v6, &string, 0);
    v9 = v13;
    if ( v13 < 0 )
    {
      LODWORD(v41) = v13;
      v10 = "ParseAndRetrieveAttribute( element, attributeHelper, interfaceToBeVerified.GetAddressOf())";
      v11 = 3812;
      goto LABEL_7;
    }
    WindowsDeleteString(v49);
    v49 = 0;
    v15 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(
            v14,
            a2,
            (struct IXMLDOMElement *)&stru_18023F118,
            &v49,
            0);
    v9 = v15;
    if ( v15 < 0 )
    {
      LODWORD(v41) = v15;
      v10 = "ParseAndRetrieveAttribute( element, Internal::PackagedComConstants::proxyStubClsidAttribute, proxyStub.GetAddressOf())";
      v11 = 3819;
      goto LABEL_7;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v17 = WindowsGetStringRawBuffer(v46, 0);
    v18 = WindowsGetStringRawBuffer(v49, 0);
    v19 = -1;
    v20 = -1;
    do
      ++v20;
    while ( v5[v20] );
    v21 = -1;
    do
      ++v21;
    while ( StringRawBuffer[v21] );
    v22 = -1;
    do
      ++v22;
    while ( v17[v22] );
    do
      ++v19;
    while ( v18[v19] );
    v23 = v21 + v22 + v20 + v19;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &Buffer,
      0,
      v23 + 173);
    v24 = Buffer;
    if ( !Buffer )
    {
      v9 = -2147024882;
      LODWORD(v41) = -2147024882;
      v25 = "xpath";
      v26 = 3831;
LABEL_19:
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)v26,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::VerifyInterface",
        v25,
        v41,
        v42);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Buffer);
      goto LABEL_30;
    }
    v27 = (unsigned int)WindowsGetStringRawBuffer(v49, 0);
    v28 = WindowsGetStringRawBuffer(v46, 0);
    v29 = WindowsGetStringRawBuffer(string, 0);
    v42 = v27;
    v30 = StringCchPrintfW(
            v24,
            v23 + 173,
            L"//*[local-name()='Extension' and @Category='windows.comInterface']/*[local-name()='ComInterface']/*[local-na"
             "me()='Interface' and @Id='%ls' and @%ls='%ls' and @ProxyStubClsid='%ls']",
            v29,
            v5,
            v28);
    if ( v30 >= 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
      XMLElementFromQuery = Common::Xml::GetXMLElementFromQuery(v24, (const unsigned __int16 *)a2, &v47, v33);
      v9 = XMLElementFromQuery;
      if ( XMLElementFromQuery < 0 )
      {
        LODWORD(v41) = XMLElementFromQuery;
        v25 = "GetXMLElementFromQuery(xpath.get(), element, &interfaceObtained)";
        v26 = 3844;
        goto LABEL_19;
      }
      if ( v47.lpVtbl )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Buffer);
        v9 = 0;
        goto LABEL_30;
      }
      v45 = 0;
      OSIntegration::Package::GetXmlLineInformation(
        this[5],
        (const struct IXMLDOMNode *)a2,
        0,
        (struct APPX_XML_LINE_INFORMATION *)&v45);
      v30 = -2146958844;
      LODWORD(v41) = -2146958844;
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0xF13,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::VerifyInterface",
        "((HRESULT)0x80080204L)",
        v41,
        v27);
      if ( (byte_1802E21CA & 4) != 0 )
      {
        v35 = this[5];
        v36 = *((_QWORD *)v35 + 28);
        v37 = (unsigned int)RemovePIIfromFilePath(*((const unsigned __int16 **)v35 + 34));
        McTemplateU0zqqdz_EventWriteTransfer(
          HIDWORD(v45),
          (unsigned int)PackagedComInvalidInterfaces,
          v37,
          v45,
          SBYTE4(v45),
          4,
          v36);
      }
      v38 = RemovePIIfromFilePath(*((const unsigned __int16 **)this[5] + 34));
      v42 = -2146958844;
      details::appxLog<unsigned short const *,unsigned int,unsigned int,long,unsigned short *>(
        2148008452LL,
        v39,
        PackagedComInvalidInterfaces,
        v38,
        v45,
        HIDWORD(v45));
      v31 = "APPX_E_INVALID_MANIFEST";
      v32 = 3861;
    }
    else
    {
      v31 = "StringCchPrintf( xpath.get(), cchxpath, Internal::PackagedComConstants::interfaceFormat, interfaceToBeVerifi"
            "ed.GetRawBuffer(nullptr), formatHelper, interfaceId.GetRawBuffer(nullptr), proxyStub.GetRawBuffer(nullptr))";
      v32 = 3840;
    }
    LODWORD(v41) = v30;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v32,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::VerifyInterface",
      v31,
      v41,
      v42);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Buffer);
    v9 = v30;
    goto LABEL_30;
  }
  LODWORD(v41) = v8;
  v10 = "ParseAndRetrieveAttribute( element, Internal::PackagedComConstants::idAttribute, interfaceId.GetAddressOf())";
  v11 = 3806;
LABEL_7:
  wil::details::in1diag5::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
    "OSIntegration::DEH::PackagedComExtensionHandler::VerifyInterface",
    v10,
    v41,
    v42);
LABEL_30:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
  WindowsDeleteString(v49);
  v49 = 0;
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v46);
  return v9;
}

```

## disassembly

```asm
0x1800d90e8  push    rbp
0x1800d90ea  push    rbx
0x1800d90eb  push    rsi
0x1800d90ec  push    rdi
0x1800d90ed  push    r12
0x1800d90ef  push    r13
0x1800d90f1  push    r14
0x1800d90f3  push    r15
0x1800d90f5  mov     rbp, rsp
0x1800d90f8  sub     rsp, 78h
0x1800d90fc  mov     r14, rdx
0x1800d90ff  mov     r13, rcx
0x1800d9102  xor     esi, esi
0x1800d9104  mov     [rbp+var_20], rsi
0x1800d9108  mov     [rbp+string], rsi
0x1800d910c  mov     [rbp+arg_18], rsi
0x1800d9110  mov     [rbp+var_18.lpVtbl], rsi
0x1800d9114  lea     r12, aSynchronousint; "SynchronousInterface"
0x1800d911b  lea     rax, stru_18023F1B8
0x1800d9122  mov     rdi, rax
0x1800d9125  test    r8b, r8b
0x1800d9128  cmovz   rdi, r12
0x1800d912c  cmovz   r12, rax
0x1800d9130  xor     ecx, ecx; string
0x1800d9132  call    cs:__imp_WindowsDeleteString
0x1800d9138  mov     [rbp+var_20], rsi
0x1800d913c  mov     [rsp+78h+var_58], rsi; bool *
0x1800d9141  lea     r9, [rbp+var_20]; HSTRING *
0x1800d9145  lea     r8, stru_180231B98; unsigned __int16 *
0x1800d914c  mov     rdx, r14; struct IXMLDOMElement *
0x1800d914f  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x1800d9154  mov     ebx, eax
0x1800d9156  test    eax, eax
0x1800d9158  jns     short loc_1800D916C
0x1800d915a  mov     dword ptr [rsp+78h+var_50], eax
0x1800d915e  lea     rax, aParseandretrie_63; "ParseAndRetrieveAttribute( element, Int"...
0x1800d9165  mov     edx, 0EDEh
0x1800d916a  jmp     short loc_1800D91A4
0x1800d916c  mov     rcx, [rbp+string]; string
0x1800d9170  call    cs:__imp_WindowsDeleteString
0x1800d9176  mov     [rbp+string], rsi
0x1800d917a  mov     [rsp+78h+var_58], rsi; bool *
0x1800d917f  lea     r9, [rbp+string]; HSTRING *
0x1800d9183  mov     r8, rdi; unsigned __int16 *
0x1800d9186  mov     rdx, r14; struct IXMLDOMElement *
0x1800d9189  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x1800d918e  mov     ebx, eax
0x1800d9190  test    eax, eax
0x1800d9192  jns     short loc_1800D91C5
0x1800d9194  mov     dword ptr [rsp+78h+var_50], eax; char *
0x1800d9198  lea     rax, aParseandretrie_62; "ParseAndRetrieveAttribute( element, att"...
0x1800d919f  mov     edx, 0EE4h; void *
0x1800d91a4  mov     rcx, [rbp+40h]; this
0x1800d91a8  mov     [rsp+78h+var_58], rax; char *
0x1800d91ad  lea     r9, aOsintegrationD_280; "OSIntegration::DEH::PackagedComExtensio"...
0x1800d91b4  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d91bb  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d91c0  jmp     loc_1800D9480
0x1800d91c5  mov     rcx, [rbp+arg_18]; string
0x1800d91c9  call    cs:__imp_WindowsDeleteString
0x1800d91cf  mov     [rbp+arg_18], rsi
0x1800d91d3  mov     [rsp+78h+var_58], rsi; bool *
0x1800d91d8  lea     r9, [rbp+arg_18]; HSTRING *
0x1800d91dc  lea     r8, stru_18023F118; unsigned __int16 *
0x1800d91e3  mov     rdx, r14; struct IXMLDOMElement *
0x1800d91e6  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x1800d91eb  mov     ebx, eax
0x1800d91ed  test    eax, eax
0x1800d91ef  jns     short loc_1800D9203
0x1800d91f1  mov     dword ptr [rsp+78h+var_50], eax
0x1800d91f5  lea     rax, aParseandretrie_39; "ParseAndRetrieveAttribute( element, Int"...
0x1800d91fc  mov     edx, 0EEBh
0x1800d9201  jmp     short loc_1800D91A4
0x1800d9203  xor     edx, edx; length
0x1800d9205  mov     rcx, [rbp+string]; string
0x1800d9209  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d920f  mov     rbx, rax
0x1800d9212  xor     edx, edx; length
0x1800d9214  mov     rcx, [rbp+var_20]; string
0x1800d9218  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d921e  mov     rdi, rax
0x1800d9221  xor     edx, edx; length
0x1800d9223  mov     rcx, [rbp+arg_18]; string
0x1800d9227  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d922d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800d9231  mov     r9, rcx
0x1800d9234  inc     r9
0x1800d9237  cmp     [r12+r9*2], si
0x1800d923c  jnz     short loc_1800D9234
0x1800d923e  mov     r8, rcx
0x1800d9241  inc     r8
0x1800d9244  cmp     [rbx+r8*2], si
0x1800d9249  jnz     short loc_1800D9241
0x1800d924b  mov     rdx, rcx
0x1800d924e  inc     rdx
0x1800d9251  cmp     [rdi+rdx*2], si
0x1800d9255  jnz     short loc_1800D924E
0x1800d9257  inc     rcx
0x1800d925a  cmp     [rax+rcx*2], si
0x1800d925e  jnz     short loc_1800D9257
0x1800d9260  lea     r15, [r9+rcx]
0x1800d9264  add     r15, rdx
0x1800d9267  add     r15, r8
0x1800d926a  lea     r8, [r15+0ADh]
0x1800d9271  xor     edx, edx
0x1800d9273  lea     rcx, [rbp+Buffer]
0x1800d9277  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800d927c  nop
0x1800d927d  mov     rbx, [rbp+Buffer]
0x1800d9281  test    rbx, rbx
0x1800d9284  jnz     short loc_1800D92C6
0x1800d9286  mov     ebx, 8007000Eh
0x1800d928b  mov     dword ptr [rsp+78h+var_50], ebx; char *
0x1800d928f  lea     rax, aXpath_0; "xpath"
0x1800d9296  mov     edx, 0EF7h; void *
0x1800d929b  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d92a2  lea     r9, aOsintegrationD_280; "OSIntegration::DEH::PackagedComExtensio"...
0x1800d92a9  mov     [rsp+78h+var_58], rax; char *
0x1800d92ae  mov     rcx, [rbp+40h]; this
0x1800d92b2  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d92b7  nop
0x1800d92b8  lea     rcx, [rbp+Buffer]
0x1800d92bc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d92c1  jmp     loc_1800D9480
0x1800d92c6  xor     edx, edx; length
0x1800d92c8  mov     rcx, [rbp+arg_18]; string
0x1800d92cc  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d92d2  mov     rsi, rax
0x1800d92d5  xor     edx, edx; length
0x1800d92d7  mov     rcx, [rbp+var_20]; string
0x1800d92db  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d92e1  mov     rdi, rax
0x1800d92e4  xor     edx, edx; length
0x1800d92e6  mov     rcx, [rbp+string]; string
0x1800d92ea  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d92f0  mov     qword ptr [rsp+78h+var_48], rsi; int
0x1800d92f5  mov     [rsp+78h+var_50], rdi
0x1800d92fa  mov     [rsp+78h+var_58], r12
0x1800d92ff  mov     r9, rax
0x1800d9302  lea     r8, aLocalNameExten_5; "//*[local-name()='Extension' and @Categ"...
0x1800d9309  lea     rdx, [r15+0ADh]; unsigned __int64
0x1800d9310  mov     rcx, rbx; Buffer
0x1800d9313  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800d9318  mov     edi, eax
0x1800d931a  xor     esi, esi
0x1800d931c  test    eax, eax
0x1800d931e  jns     short loc_1800D935D
0x1800d9320  lea     rax, aStringcchprint_35; "StringCchPrintf( xpath.get(), cchxpath,"...
0x1800d9327  mov     edx, 0F00h; void *
0x1800d932c  mov     dword ptr [rsp+78h+var_50], edi; char *
0x1800d9330  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d9337  lea     r9, aOsintegrationD_280; "OSIntegration::DEH::PackagedComExtensio"...
0x1800d933e  mov     [rsp+78h+var_58], rax; char *
0x1800d9343  mov     rcx, [rbp+40h]; this
0x1800d9347  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d934c  nop
0x1800d934d  lea     rcx, [rbp+Buffer]
0x1800d9351  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d9356  mov     ebx, edi
0x1800d9358  jmp     loc_1800D9480
0x1800d935d  lea     rcx, [rbp+var_18]
0x1800d9361  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d9366  lea     r8, [rbp+var_18]; struct IXMLDOMElement *
0x1800d936a  mov     rdx, r14; unsigned __int16 *
0x1800d936d  mov     rcx, rbx; strIn
0x1800d9370  call    ?GetXMLElementFromQuery@Xml@Common@@YAJPEBGPEAUIXMLDOMElement@@PEAPEAU3@@Z; Common::Xml::GetXMLElementFromQuery(ushort const *,IXMLDOMElement *,IXMLDOMElement * *)
0x1800d9375  mov     ebx, eax
0x1800d9377  test    eax, eax
0x1800d9379  jns     short loc_1800D9390
0x1800d937b  mov     dword ptr [rsp+78h+var_50], eax
0x1800d937f  lea     rax, aGetxmlelementf_11; "GetXMLElementFromQuery(xpath.get(), ele"...
0x1800d9386  mov     edx, 0F04h
0x1800d938b  jmp     loc_1800D929B
0x1800d9390  cmp     [rbp+var_18.lpVtbl], rsi
0x1800d9394  jnz     loc_1800D9475
0x1800d939a  mov     [rbp+var_28], rsi
0x1800d939e  lea     r9, [rbp+var_28]; struct APPX_XML_LINE_INFORMATION *
0x1800d93a2  xor     r8d, r8d; unsigned __int16 *
0x1800d93a5  mov     rdx, r14; struct IXMLDOMNode *
0x1800d93a8  mov     rcx, [r13+28h]; this
0x1800d93ac  call    ?GetXmlLineInformation@Package@OSIntegration@@QEBAJPEBUIXMLDOMNode@@PEBGPEAUAPPX_XML_LINE_INFORMATION@@@Z; OSIntegration::Package::GetXmlLineInformation(IXMLDOMNode const *,ushort const *,APPX_XML_LINE_INFORMATION *)
0x1800d93b1  mov     rcx, [rbp+40h]; this
0x1800d93b5  mov     edi, 80080204h
0x1800d93ba  mov     dword ptr [rsp+78h+var_50], edi; char *
0x1800d93be  lea     rax, aHresult0x80080; "((HRESULT)0x80080204L)"
0x1800d93c5  mov     [rsp+78h+var_58], rax; char *
0x1800d93ca  lea     r9, aOsintegrationD_280; "OSIntegration::DEH::PackagedComExtensio"...
0x1800d93d1  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d93d8  mov     edx, 0F13h; void *
0x1800d93dd  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d93e2  test    cs:byte_1802E21CA, 4
0x1800d93e9  jz      short loc_1800D9425
0x1800d93eb  mov     rcx, [r13+28h]
0x1800d93ef  mov     rbx, [rcx+0E0h]
0x1800d93f6  mov     rcx, [rcx+110h]; unsigned __int16 *
0x1800d93fd  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x1800d9402  mov     qword ptr [rsp+78h+var_48], rbx
0x1800d9407  mov     dword ptr [rsp+78h+var_50], edi
0x1800d940b  mov     ecx, dword ptr [rbp+var_28+4]
0x1800d940e  mov     dword ptr [rsp+78h+var_58], ecx
0x1800d9412  mov     r9d, dword ptr [rbp+var_28]
0x1800d9416  mov     r8, rax
0x1800d9419  lea     rdx, PackagedComInvalidInterfaces
0x1800d9420  call    McTemplateU0zqqdz_EventWriteTransfer
0x1800d9425  mov     rcx, [r13+28h]
0x1800d9429  mov     rbx, [rcx+0E0h]
0x1800d9430  mov     rcx, [rcx+110h]; unsigned __int16 *
0x1800d9437  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x1800d943c  mov     [rsp+78h+var_40], rbx
0x1800d9441  mov     [rsp+78h+var_48], edi
0x1800d9445  mov     ecx, dword ptr [rbp+var_28+4]
0x1800d9448  mov     dword ptr [rsp+78h+var_50], ecx
0x1800d944c  mov     ecx, dword ptr [rbp+var_28]
0x1800d944f  mov     dword ptr [rsp+78h+var_58], ecx
0x1800d9453  mov     r9, rax
0x1800d9456  lea     r8, PackagedComInvalidInterfaces
0x1800d945d  mov     ecx, edi
0x1800d945f  call    ??$appxLog@PEBGIIJPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEBGIIJPEAG@Z; details::appxLog<ushort const *,uint,uint,long,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort const *,uint,uint,long,ushort *)
0x1800d9464  lea     rax, aAppxEInvalidMa; "APPX_E_INVALID_MANIFEST"
0x1800d946b  mov     edx, 0F15h
0x1800d9470  jmp     loc_1800D932C
0x1800d9475  lea     rcx, [rbp+Buffer]
0x1800d9479  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800d947e  mov     ebx, esi
0x1800d9480  lea     rcx, [rbp+var_18]
0x1800d9484  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d9489  nop
0x1800d948a  mov     rcx, [rbp+arg_18]; string
0x1800d948e  call    cs:__imp_WindowsDeleteString
0x1800d9494  mov     [rbp+arg_18], rsi
0x1800d9498  mov     rcx, [rbp+string]; string
0x1800d949c  call    cs:__imp_WindowsDeleteString
0x1800d94a2  mov     [rbp+string], rsi
0x1800d94a6  mov     rcx, [rbp+var_20]; string
0x1800d94aa  call    cs:__imp_WindowsDeleteString
0x1800d94b0  mov     eax, ebx
0x1800d94b2  add     rsp, 78h
0x1800d94b6  pop     r15
0x1800d94b8  pop     r14
0x1800d94ba  pop     r13
0x1800d94bc  pop     r12
0x1800d94be  pop     rdi
0x1800d94bf  pop     rsi
0x1800d94c0  pop     rbx
0x1800d94c1  pop     rbp
0x1800d94c2  retn
```
