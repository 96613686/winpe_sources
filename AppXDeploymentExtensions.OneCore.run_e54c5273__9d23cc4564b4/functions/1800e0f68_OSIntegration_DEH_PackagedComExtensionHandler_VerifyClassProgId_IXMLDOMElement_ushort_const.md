# OSIntegration::DEH::PackagedComExtensionHandler::VerifyClassProgId(IXMLDOMElement *,ushort const *)

- ea: `0x1800e0f68`
- end: `0x1800e1237`
- name: `?VerifyClassProgId@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBG@Z`
- size: `719`
- prototype: `int(OSIntegration::DEH::PackagedComExtensionHandler *__hidden this, struct IXMLDOMElement *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
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
- `0x1800e0f68`
- `0x18013ced4`
- `0x18013d6f8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e0ff6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e107d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e0ff6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e107d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e0f97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e1216`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e0f97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e1216`

## string_xrefs

- `0x1800e0fda`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800e104c`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800e10b7`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800e1158`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800e11eb`: `APPX_E_INVALID_MANIFEST`
- `0x1800e1040`: `xpath`
- `0x1800e0fd3`: `OSIntegration::DEH::PackagedComExtensionHandler::VerifyClassProgId`
- `0x1800e1053`: `OSIntegration::DEH::PackagedComExtensionHandler::VerifyClassProgId`
- `0x1800e10be`: `OSIntegration::DEH::PackagedComExtensionHandler::VerifyClassProgId`
- `0x1800e1151`: `OSIntegration::DEH::PackagedComExtensionHandler::VerifyClassProgId`
- `0x1800e108b`: `//*[local-name()='Extension' and @Category='windows.comServer']/*[local-name()='ComServer']/*[local-name()='ProgId' and @Clsid='%ls' and @Id='%ls']`
- `0x1800e1106`: `GetXMLElementFromQuery(xpath.get(), element, &progId)`
- `0x1800e0fc7`: `ParseAndRetrieveAttribute( element, Internal::PackagedComConstants::idAttribute, classId.GetAddressOf())`
- `0x1800e10a7`: `StringCchPrintf( xpath.get(), cchxpath, Internal::PackagedComConstants::progIdWithClsidAndIdFormat, classId.GetRawBuffer(nullptr), classProgId)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall OSIntegration::DEH::PackagedComExtensionHandler::VerifyClassProgId(
        OSIntegration::Package **this,
        struct IXMLDOMElement *a2,
        const unsigned __int16 *a3)
{
  OSIntegration::DEH::PackagedComExtensionHandler *v6; // rcx
  int v7; // eax
  unsigned int v8; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rdi
  wchar_t *v13; // rbx
  const char *v14; // rax
  __int64 v15; // rdx
  PCWSTR v16; // rax
  int v17; // edi
  const char *v18; // rax
  __int64 v19; // rdx
  struct IXMLDOMElement **v20; // r9
  int XMLElementFromQuery; // eax
  OSIntegration::Package *v22; // rcx
  __int64 v23; // rbx
  unsigned int v24; // eax
  const unsigned __int16 *v25; // rax
  __int64 v26; // rdx
  char *v28; // [rsp+28h] [rbp-38h]
  int v29; // [rsp+30h] [rbp-30h]
  __int64 v30; // [rsp+40h] [rbp-20h] BYREF
  HSTRING string; // [rsp+48h] [rbp-18h] BYREF
  struct IXMLDOMElement v32; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+88h] [rbp+28h]
  wchar_t *Buffer; // [rsp+A8h] [rbp+48h] BYREF

  v32.lpVtbl = 0;
  WindowsDeleteString(0);
  string = 0;
  v7 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(
         v6,
         a2,
         (struct IXMLDOMElement *)&stru_180231B98,
         &string,
         0);
  v8 = v7;
  if ( v7 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v10 = -1;
    v11 = -1;
    do
      ++v11;
    while ( a3[v11] );
    do
      ++v10;
    while ( StringRawBuffer[v10] );
    v12 = v10 + v11;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &Buffer,
      0,
      v10 + v11 + 144);
    v13 = Buffer;
    if ( !Buffer )
    {
      v8 = -2147024882;
      LODWORD(v28) = -2147024882;
      v14 = "xpath";
      v15 = 3660;
LABEL_8:
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::VerifyClassProgId",
        v14,
        v28,
        v29);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Buffer);
      goto LABEL_19;
    }
    v16 = WindowsGetStringRawBuffer(string, 0);
    v17 = StringCchPrintfW(
            v13,
            v12 + 144,
            L"//*[local-name()='Extension' and @Category='windows.comServer']/*[local-name()='ComServer']/*[local-name()='"
             "ProgId' and @Clsid='%ls' and @Id='%ls']",
            v16,
            a3);
    if ( v17 >= 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
      XMLElementFromQuery = Common::Xml::GetXMLElementFromQuery(v13, (const unsigned __int16 *)a2, &v32, v20);
      v8 = XMLElementFromQuery;
      if ( XMLElementFromQuery < 0 )
      {
        LODWORD(v28) = XMLElementFromQuery;
        v14 = "GetXMLElementFromQuery(xpath.get(), element, &progId)";
        v15 = 3670;
        goto LABEL_8;
      }
      if ( v32.lpVtbl )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Buffer);
        v8 = 0;
        goto LABEL_19;
      }
      v30 = 0;
      OSIntegration::Package::GetXmlLineInformation(
        this[5],
        (const struct IXMLDOMNode *)a2,
        0,
        (struct APPX_XML_LINE_INFORMATION *)&v30);
      v17 = -2146958844;
      LODWORD(v28) = -2146958844;
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0xE65,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::VerifyClassProgId",
        "((HRESULT)0x80080204L)",
        v28,
        v29);
      if ( (byte_1802E21CA & 4) != 0 )
      {
        v22 = this[5];
        v23 = *((_QWORD *)v22 + 28);
        v24 = (unsigned int)RemovePIIfromFilePath(*((const unsigned __int16 **)v22 + 34));
        McTemplateU0zqqdz_EventWriteTransfer(
          HIDWORD(v30),
          (unsigned int)PackagedComInvalidClassProgId,
          v24,
          v30,
          SBYTE4(v30),
          4,
          v23);
      }
      v25 = RemovePIIfromFilePath(*((const unsigned __int16 **)this[5] + 34));
      v29 = -2146958844;
      details::appxLog<unsigned short const *,unsigned int,unsigned int,long,unsigned short *>(
        2148008452LL,
        v26,
        PackagedComInvalidClassProgId,
        v25,
        v30,
        HIDWORD(v30));
      v18 = "APPX_E_INVALID_MANIFEST";
      v19 = 3687;
    }
    else
    {
      v18 = "StringCchPrintf( xpath.get(), cchxpath, Internal::PackagedComConstants::progIdWithClsidAndIdFormat, classId."
            "GetRawBuffer(nullptr), classProgId)";
      v19 = 3667;
    }
    LODWORD(v28) = v17;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::VerifyClassProgId",
      v18,
      v28,
      v29);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Buffer);
    v8 = v17;
    goto LABEL_19;
  }
  LODWORD(v28) = v7;
  wil::details::in1diag5::Return_Hr(
    retaddr,
    (void *)0xE42,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
    "OSIntegration::DEH::PackagedComExtensionHandler::VerifyClassProgId",
    "ParseAndRetrieveAttribute( element, Internal::PackagedComConstants::idAttribute, classId.GetAddressOf())",
    v28,
    v29);
LABEL_19:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  WindowsDeleteString(string);
  return v8;
}

```

## disassembly

```asm
0x1800e0f68  mov     [rsp-28h+arg_0], rbx
0x1800e0f6d  mov     [rsp-28h+arg_8], rsi
0x1800e0f72  push    rbp
0x1800e0f73  push    rdi
0x1800e0f74  push    r12
0x1800e0f76  push    r14
0x1800e0f78  push    r15
0x1800e0f7a  mov     rbp, rsp
0x1800e0f7d  sub     rsp, 60h
0x1800e0f81  mov     r14, r8
0x1800e0f84  mov     rsi, rdx
0x1800e0f87  mov     r15, rcx
0x1800e0f8a  xor     r12d, r12d
0x1800e0f8d  mov     [rbp+string], r12
0x1800e0f91  mov     [rbp+var_10.lpVtbl], r12
0x1800e0f95  xor     ecx, ecx; string
0x1800e0f97  call    cs:__imp_WindowsDeleteString
0x1800e0f9d  mov     [rbp+string], r12
0x1800e0fa1  mov     [rsp+60h+var_40], r12; bool *
0x1800e0fa6  lea     r9, [rbp+string]; HSTRING *
0x1800e0faa  lea     r8, stru_180231B98; unsigned __int16 *
0x1800e0fb1  mov     rdx, rsi; struct IXMLDOMElement *
0x1800e0fb4  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x1800e0fb9  mov     ebx, eax
0x1800e0fbb  test    eax, eax
0x1800e0fbd  jns     short loc_1800E0FF0
0x1800e0fbf  mov     rcx, [rbp+28h]; this
0x1800e0fc3  mov     dword ptr [rsp+60h+var_38], eax; char *
0x1800e0fc7  lea     rax, aParseandretrie_78; "ParseAndRetrieveAttribute( element, Int"...
0x1800e0fce  mov     [rsp+60h+var_40], rax; char *
0x1800e0fd3  lea     r9, aOsintegrationD_341; "OSIntegration::DEH::PackagedComExtensio"...
0x1800e0fda  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800e0fe1  mov     edx, 0E42h; void *
0x1800e0fe6  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800e0feb  jmp     loc_1800E1208
0x1800e0ff0  xor     edx, edx; length
0x1800e0ff2  mov     rcx, [rbp+string]; string
0x1800e0ff6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e0ffc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800e1000  mov     rdx, rcx
0x1800e1003  inc     rdx
0x1800e1006  cmp     [r14+rdx*2], r12w
0x1800e100b  jnz     short loc_1800E1003
0x1800e100d  inc     rcx
0x1800e1010  cmp     [rax+rcx*2], r12w
0x1800e1015  jnz     short loc_1800E100D
0x1800e1017  lea     rdi, [rcx+rdx]
0x1800e101b  lea     r8, [rdi+90h]
0x1800e1022  xor     edx, edx
0x1800e1024  lea     rcx, [rbp+Buffer]
0x1800e1028  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800e102d  nop
0x1800e102e  mov     rbx, [rbp+Buffer]
0x1800e1032  test    rbx, rbx
0x1800e1035  jnz     short loc_1800E1077
0x1800e1037  mov     ebx, 8007000Eh
0x1800e103c  mov     dword ptr [rsp+60h+var_38], ebx; char *
0x1800e1040  lea     rax, aXpath_0; "xpath"
0x1800e1047  mov     edx, 0E4Ch; void *
0x1800e104c  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800e1053  lea     r9, aOsintegrationD_341; "OSIntegration::DEH::PackagedComExtensio"...
0x1800e105a  mov     [rsp+60h+var_40], rax; char *
0x1800e105f  mov     rcx, [rbp+28h]; this
0x1800e1063  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800e1068  nop
0x1800e1069  lea     rcx, [rbp+Buffer]
0x1800e106d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800e1072  jmp     loc_1800E1208
0x1800e1077  xor     edx, edx; length
0x1800e1079  mov     rcx, [rbp+string]; string
0x1800e107d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e1083  mov     [rsp+60h+var_40], r14
0x1800e1088  mov     r9, rax
0x1800e108b  lea     r8, aLocalNameExten_4; "//*[local-name()='Extension' and @Categ"...
0x1800e1092  lea     rdx, [rdi+90h]; unsigned __int64
0x1800e1099  mov     rcx, rbx; Buffer
0x1800e109c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800e10a1  mov     edi, eax
0x1800e10a3  test    eax, eax
0x1800e10a5  jns     short loc_1800E10E4
0x1800e10a7  lea     rax, aStringcchprint_8; "StringCchPrintf( xpath.get(), cchxpath,"...
0x1800e10ae  mov     edx, 0E53h; void *
0x1800e10b3  mov     dword ptr [rsp+60h+var_38], edi; char *
0x1800e10b7  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800e10be  lea     r9, aOsintegrationD_341; "OSIntegration::DEH::PackagedComExtensio"...
0x1800e10c5  mov     [rsp+60h+var_40], rax; char *
0x1800e10ca  mov     rcx, [rbp+28h]; this
0x1800e10ce  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800e10d3  nop
0x1800e10d4  lea     rcx, [rbp+Buffer]
0x1800e10d8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800e10dd  mov     ebx, edi
0x1800e10df  jmp     loc_1800E1208
0x1800e10e4  lea     rcx, [rbp+var_10]
0x1800e10e8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e10ed  lea     r8, [rbp+var_10]; struct IXMLDOMElement *
0x1800e10f1  mov     rdx, rsi; unsigned __int16 *
0x1800e10f4  mov     rcx, rbx; strIn
0x1800e10f7  call    ?GetXMLElementFromQuery@Xml@Common@@YAJPEBGPEAUIXMLDOMElement@@PEAPEAU3@@Z; Common::Xml::GetXMLElementFromQuery(ushort const *,IXMLDOMElement *,IXMLDOMElement * *)
0x1800e10fc  mov     ebx, eax
0x1800e10fe  test    eax, eax
0x1800e1100  jns     short loc_1800E1117
0x1800e1102  mov     dword ptr [rsp+60h+var_38], eax
0x1800e1106  lea     rax, aGetxmlelementf_6; "GetXMLElementFromQuery(xpath.get(), ele"...
0x1800e110d  mov     edx, 0E56h
0x1800e1112  jmp     loc_1800E104C
0x1800e1117  cmp     [rbp+var_10.lpVtbl], r12
0x1800e111b  jnz     loc_1800E11FC
0x1800e1121  mov     [rbp+var_20], r12
0x1800e1125  lea     r9, [rbp+var_20]; struct APPX_XML_LINE_INFORMATION *
0x1800e1129  xor     r8d, r8d; unsigned __int16 *
0x1800e112c  mov     rdx, rsi; struct IXMLDOMNode *
0x1800e112f  mov     rcx, [r15+28h]; this
0x1800e1133  call    ?GetXmlLineInformation@Package@OSIntegration@@QEBAJPEBUIXMLDOMNode@@PEBGPEAUAPPX_XML_LINE_INFORMATION@@@Z; OSIntegration::Package::GetXmlLineInformation(IXMLDOMNode const *,ushort const *,APPX_XML_LINE_INFORMATION *)
0x1800e1138  mov     rcx, [rbp+28h]; this
0x1800e113c  mov     edi, 80080204h
0x1800e1141  mov     dword ptr [rsp+60h+var_38], edi; char *
0x1800e1145  lea     rax, aHresult0x80080; "((HRESULT)0x80080204L)"
0x1800e114c  mov     [rsp+60h+var_40], rax; char *
0x1800e1151  lea     r9, aOsintegrationD_341; "OSIntegration::DEH::PackagedComExtensio"...
0x1800e1158  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800e115f  mov     edx, 0E65h; void *
0x1800e1164  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800e1169  test    cs:byte_1802E21CA, 4
0x1800e1170  jz      short loc_1800E11AC
0x1800e1172  mov     rcx, [r15+28h]
0x1800e1176  mov     rbx, [rcx+0E0h]
0x1800e117d  mov     rcx, [rcx+110h]; unsigned __int16 *
0x1800e1184  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x1800e1189  mov     [rsp+60h+var_30], rbx
0x1800e118e  mov     dword ptr [rsp+60h+var_38], edi
0x1800e1192  mov     ecx, dword ptr [rbp+var_20+4]
0x1800e1195  mov     dword ptr [rsp+60h+var_40], ecx
0x1800e1199  mov     r9d, dword ptr [rbp+var_20]
0x1800e119d  mov     r8, rax
0x1800e11a0  lea     rdx, PackagedComInvalidClassProgId
0x1800e11a7  call    McTemplateU0zqqdz_EventWriteTransfer
0x1800e11ac  mov     rcx, [r15+28h]
0x1800e11b0  mov     rbx, [rcx+0E0h]
0x1800e11b7  mov     rcx, [rcx+110h]; unsigned __int16 *
0x1800e11be  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x1800e11c3  mov     [rsp+60h+var_28], rbx
0x1800e11c8  mov     dword ptr [rsp+60h+var_30], edi
0x1800e11cc  mov     ecx, dword ptr [rbp+var_20+4]
0x1800e11cf  mov     dword ptr [rsp+60h+var_38], ecx
0x1800e11d3  mov     ecx, dword ptr [rbp+var_20]
0x1800e11d6  mov     dword ptr [rsp+60h+var_40], ecx
0x1800e11da  mov     r9, rax
0x1800e11dd  lea     r8, PackagedComInvalidClassProgId
0x1800e11e4  mov     ecx, edi
0x1800e11e6  call    ??$appxLog@PEBGIIJPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEBGIIJPEAG@Z; details::appxLog<ushort const *,uint,uint,long,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort const *,uint,uint,long,ushort *)
0x1800e11eb  lea     rax, aAppxEInvalidMa; "APPX_E_INVALID_MANIFEST"
0x1800e11f2  mov     edx, 0E67h
0x1800e11f7  jmp     loc_1800E10B3
0x1800e11fc  lea     rcx, [rbp+Buffer]
0x1800e1200  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800e1205  mov     ebx, r12d
0x1800e1208  lea     rcx, [rbp+var_10]
0x1800e120c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e1211  nop
0x1800e1212  mov     rcx, [rbp+string]; string
0x1800e1216  call    cs:__imp_WindowsDeleteString
0x1800e121c  mov     eax, ebx
0x1800e121e  lea     r11, [rsp+60h+var_s0]
0x1800e1223  mov     rbx, [r11+30h]
0x1800e1227  mov     rsi, [r11+38h]
0x1800e122b  mov     rsp, r11
0x1800e122e  pop     r15
0x1800e1230  pop     r14
0x1800e1232  pop     r12
0x1800e1234  pop     rdi
0x1800e1235  pop     rbp
0x1800e1236  retn
```
