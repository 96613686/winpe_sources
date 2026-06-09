# OSIntegration::DEH::PackagedComExtensionHandler::VerifyInterfaceTypeLib(IXMLDOMElement *,ushort const *)

- ea: `0x180077320`
- end: `0x180077601`
- name: `?VerifyInterfaceTypeLib@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBG@Z`
- size: `737`
- prototype: `int(OSIntegration::DEH::PackagedComExtensionHandler *__hidden this, struct IXMLDOMElement *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007762c`

## callees

- `0x18000b3bc`
- `0x18000b7d0`
- `0x18000b9e0`
- `0x180012964`
- `0x18003f850`
- `0x1800411e0`
- `0x1800550f4`
- `0x180077320`
- `0x18007d350`
- `0x180098ed0`
- `0x18009aff4`
- `0x18009d1b8`
- `0x18013ced4`
- `0x18013d6f8`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800773ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077435`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800773ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077435`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007734f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800775e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007734f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800775e0`

## string_xrefs

- `0x180077392`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18007740f`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800774e0`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18007758f`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x180077573`: `APPX_E_INVALID_MANIFEST`
- `0x180077443`: `//*[local-name()='Extension' and @Category='windows.comInterface']/*[local-name()='ComInterface']/*[local-name()='TypeLib' and @Id='%ls']/*[local-name()='Version' and @VersionNumber='%ls']`
- `0x18007738b`: `OSIntegration::DEH::PackagedComExtensionHandler::VerifyInterfaceTypeLib`
- `0x180077408`: `OSIntegration::DEH::PackagedComExtensionHandler::VerifyInterfaceTypeLib`
- `0x1800774d9`: `OSIntegration::DEH::PackagedComExtensionHandler::VerifyInterfaceTypeLib`
- `0x180077588`: `OSIntegration::DEH::PackagedComExtensionHandler::VerifyInterfaceTypeLib`
- `0x1800773fc`: `xpath`
- `0x18007737f`: `ParseAndRetrieveAttribute( element, Internal::PackagedComConstants::idAttribute, typeLibId.GetAddressOf())`
- `0x18007745f`: `StringCchPrintf( xpath.get(), cchxpath, Internal::PackagedComConstants::typeLibWithVersionNumberFormat, typeLibId.GetRawBuffer(nullptr), versionNumber)`
- `0x18007748e`: `GetXMLElementFromQuery(xpath.get(), element, &typeLib)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OSIntegration::DEH::PackagedComExtensionHandler::VerifyInterfaceTypeLib(
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
  PCWSTR v14; // rax
  int XMLElementFromQuery; // edi
  const char *v16; // rax
  __int64 v17; // rdx
  struct IXMLDOMElement **v18; // r9
  OSIntegration::Package *v19; // rcx
  __int64 v20; // rbx
  unsigned int v21; // eax
  const unsigned __int16 *v22; // rax
  __int64 v23; // rdx
  struct IXMLDOMElementVtbl *lpVtbl; // rcx
  bool *v26; // [rsp+20h] [rbp-40h]
  char *v27; // [rsp+28h] [rbp-38h]
  char *v28; // [rsp+28h] [rbp-38h]
  int v29; // [rsp+30h] [rbp-30h]
  __int64 v30; // [rsp+40h] [rbp-20h] BYREF
  wchar_t *Buffer; // [rsp+48h] [rbp-18h] BYREF
  HSTRING string; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+88h] [rbp+28h]
  struct IXMLDOMElement v34; // [rsp+A8h] [rbp+48h] BYREF

  v34.lpVtbl = 0;
  WindowsDeleteString(0);
  string = 0;
  v7 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(
         v6,
         a2,
         (const unsigned __int16 *)&stru_180231B98,
         &string,
         0);
  v8 = v7;
  if ( v7 < 0 )
  {
    LODWORD(v27) = v7;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xE78,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::VerifyInterfaceTypeLib",
      "ParseAndRetrieveAttribute( element, Internal::PackagedComConstants::idAttribute, typeLibId.GetAddressOf())",
      v27,
      v29);
LABEL_17:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    goto LABEL_21;
  }
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
  wil::make_process_heap_string_nothrow((wil *)&Buffer, 0, v10 + v11 + 185);
  v13 = Buffer;
  if ( !Buffer )
  {
    v8 = -2147024882;
    LODWORD(v27) = -2147024882;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xE82,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::VerifyInterfaceTypeLib",
      "xpath",
      v27,
      v29);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Buffer);
    goto LABEL_17;
  }
  v14 = WindowsGetStringRawBuffer(string, 0);
  XMLElementFromQuery = StringCchPrintfW(
                          v13,
                          v12 + 185,
                          L"//*[local-name()='Extension' and @Category='windows.comInterface']/*[local-name()='ComInterfac"
                           "e']/*[local-name()='TypeLib' and @Id='%ls']/*[local-name()='Version' and @VersionNumber='%ls']",
                          v14,
                          a3);
  if ( XMLElementFromQuery < 0 )
  {
    v16 = "StringCchPrintf( xpath.get(), cchxpath, Internal::PackagedComConstants::typeLibWithVersionNumberFormat, typeLi"
          "bId.GetRawBuffer(nullptr), versionNumber)";
    v17 = 3721;
LABEL_16:
    LODWORD(v27) = XMLElementFromQuery;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::VerifyInterfaceTypeLib",
      v16,
      v27,
      v29);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Buffer);
    v8 = XMLElementFromQuery;
    goto LABEL_17;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
  XMLElementFromQuery = Common::Xml::GetXMLElementFromQuery(v13, (const unsigned __int16 *)a2, &v34, v18);
  if ( XMLElementFromQuery < 0 )
  {
    v16 = "GetXMLElementFromQuery(xpath.get(), element, &typeLib)";
    v17 = 3723;
    goto LABEL_16;
  }
  if ( !v34.lpVtbl )
  {
    v30 = 0;
    OSIntegration::Package::GetXmlLineInformation(
      this[5],
      (const struct IXMLDOMNode *)a2,
      0,
      (struct APPX_XML_LINE_INFORMATION *)&v30);
    XMLElementFromQuery = -2146958844;
    LODWORD(v27) = -2146958844;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0xE9A,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::VerifyInterfaceTypeLib",
      "((HRESULT)0x80080204L)",
      v27,
      v29);
    if ( (byte_1802E21CA & 4) != 0 )
    {
      v19 = this[5];
      v20 = *((_QWORD *)v19 + 28);
      v21 = (unsigned int)RemovePIIfromFilePath(*((const unsigned __int16 **)v19 + 34));
      McTemplateU0zqqdz_EventWriteTransfer(
        HIDWORD(v30),
        (unsigned int)PackagedComInvalidInterfaceTypeLib,
        v21,
        v30,
        SBYTE4(v30),
        4,
        v20);
    }
    v22 = RemovePIIfromFilePath(*((const unsigned __int16 **)this[5] + 34));
    v29 = -2146958844;
    LODWORD(v28) = HIDWORD(v30);
    LODWORD(v26) = v30;
    details::appxLog<unsigned short const *,unsigned int,unsigned int,long,unsigned short *>(
      -2146958844,
      v23,
      (const struct _EVENT_DESCRIPTOR *)PackagedComInvalidInterfaceTypeLib,
      v22,
      v26,
      v28);
    v16 = "APPX_E_INVALID_MANIFEST";
    v17 = 3740;
    goto LABEL_16;
  }
  MemoryFree(v13);
  lpVtbl = v34.lpVtbl;
  if ( v34.lpVtbl )
  {
    v34.lpVtbl = 0;
    (*((void (__fastcall **)(struct IXMLDOMElementVtbl *))lpVtbl->QueryInterface + 2))(lpVtbl);
  }
  v8 = 0;
LABEL_21:
  WindowsDeleteString(string);
  return v8;
}

```

## disassembly

```asm
0x180077320  mov     [rsp-28h+arg_0], rbx
0x180077325  mov     [rsp-28h+arg_8], rsi
0x18007732a  push    rbp
0x18007732b  push    rdi
0x18007732c  push    r12
0x18007732e  push    r14
0x180077330  push    r15
0x180077332  mov     rbp, rsp
0x180077335  sub     rsp, 60h
0x180077339  mov     r14, r8
0x18007733c  mov     rsi, rdx
0x18007733f  mov     r15, rcx
0x180077342  xor     r12d, r12d
0x180077345  mov     [rbp+string], r12
0x180077349  mov     [rbp+arg_18.lpVtbl], r12
0x18007734d  xor     ecx, ecx; string
0x18007734f  call    cs:__imp_WindowsDeleteString
0x180077355  mov     [rbp+string], r12
0x180077359  mov     [rsp+60h+var_40], r12; bool *
0x18007735e  lea     r9, [rbp+string]; HSTRING *
0x180077362  lea     r8, stru_180231B98; unsigned __int16 *
0x180077369  mov     rdx, rsi; struct IXMLDOMElement *
0x18007736c  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x180077371  mov     ebx, eax
0x180077373  test    eax, eax
0x180077375  jns     short loc_1800773A8
0x180077377  mov     rcx, [rbp+28h]; this
0x18007737b  mov     dword ptr [rsp+60h+var_38], eax; char *
0x18007737f  lea     rax, aParseandretrie_13; "ParseAndRetrieveAttribute( element, Int"...
0x180077386  mov     [rsp+60h+var_40], rax; char *
0x18007738b  lea     r9, aOsintegrationD_368; "OSIntegration::DEH::PackagedComExtensio"...
0x180077392  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180077399  mov     edx, 0E78h; void *
0x18007739e  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800773a3  jmp     loc_1800775AB
0x1800773a8  xor     edx, edx; length
0x1800773aa  mov     rcx, [rbp+string]; string
0x1800773ae  call    cs:__imp_WindowsGetStringRawBuffer
0x1800773b4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800773b8  mov     rdx, rcx
0x1800773bb  inc     rdx
0x1800773be  cmp     [r14+rdx*2], r12w
0x1800773c3  jnz     short loc_1800773BB
0x1800773c5  inc     rcx
0x1800773c8  cmp     [rax+rcx*2], r12w
0x1800773cd  jnz     short loc_1800773C5
0x1800773cf  lea     rdi, [rcx+rdx]
0x1800773d3  lea     r8, [rdi+0B9h]; unsigned __int64
0x1800773da  xor     edx, edx; unsigned __int16 *
0x1800773dc  lea     rcx, [rbp+Buffer]; this
0x1800773e0  call    ?make_process_heap_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_process_heap_string_nothrow(ushort const *,unsigned __int64)
0x1800773e5  nop
0x1800773e6  mov     rbx, [rbp+Buffer]
0x1800773ea  test    rbx, rbx
0x1800773ed  jnz     short loc_18007742F
0x1800773ef  mov     rcx, [rbp+28h]; this
0x1800773f3  mov     ebx, 8007000Eh
0x1800773f8  mov     dword ptr [rsp+60h+var_38], ebx; char *
0x1800773fc  lea     rax, aXpath_0; "xpath"
0x180077403  mov     [rsp+60h+var_40], rax; char *
0x180077408  lea     r9, aOsintegrationD_368; "OSIntegration::DEH::PackagedComExtensio"...
0x18007740f  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180077416  mov     edx, 0E82h; void *
0x18007741b  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180077420  nop
0x180077421  lea     rcx, [rbp+Buffer]
0x180077425  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007742a  jmp     loc_1800775AB
0x18007742f  xor     edx, edx; length
0x180077431  mov     rcx, [rbp+string]; string
0x180077435  call    cs:__imp_WindowsGetStringRawBuffer
0x18007743b  mov     [rsp+60h+var_40], r14
0x180077440  mov     r9, rax
0x180077443  lea     r8, aLocalNameExten_7; "//*[local-name()='Extension' and @Categ"...
0x18007744a  lea     rdx, [rdi+0B9h]; unsigned __int64
0x180077451  mov     rcx, rbx; Buffer
0x180077454  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180077459  mov     edi, eax
0x18007745b  test    eax, eax
0x18007745d  jns     short loc_180077470
0x18007745f  lea     rax, aStringcchprint_29; "StringCchPrintf( xpath.get(), cchxpath,"...
0x180077466  mov     edx, 0E89h
0x18007746b  jmp     loc_18007757F
0x180077470  lea     rcx, [rbp+arg_18]
0x180077474  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180077479  lea     r8, [rbp+arg_18]; struct IXMLDOMElement *
0x18007747d  mov     rdx, rsi; unsigned __int16 *
0x180077480  mov     rcx, rbx; strIn
0x180077483  call    ?GetXMLElementFromQuery@Xml@Common@@YAJPEBGPEAUIXMLDOMElement@@PEAPEAU3@@Z; Common::Xml::GetXMLElementFromQuery(ushort const *,IXMLDOMElement *,IXMLDOMElement * *)
0x180077488  mov     edi, eax
0x18007748a  test    eax, eax
0x18007748c  jns     short loc_18007749F
0x18007748e  lea     rax, aGetxmlelementf_8; "GetXMLElementFromQuery(xpath.get(), ele"...
0x180077495  mov     edx, 0E8Bh
0x18007749a  jmp     loc_18007757F
0x18007749f  cmp     [rbp+arg_18.lpVtbl], r12
0x1800774a3  jnz     loc_1800775B6
0x1800774a9  mov     [rbp+var_20], r12
0x1800774ad  lea     r9, [rbp+var_20]; struct APPX_XML_LINE_INFORMATION *
0x1800774b1  xor     r8d, r8d; unsigned __int16 *
0x1800774b4  mov     rdx, rsi; struct IXMLDOMNode *
0x1800774b7  mov     rcx, [r15+28h]; this
0x1800774bb  call    ?GetXmlLineInformation@Package@OSIntegration@@QEBAJPEBUIXMLDOMNode@@PEBGPEAUAPPX_XML_LINE_INFORMATION@@@Z; OSIntegration::Package::GetXmlLineInformation(IXMLDOMNode const *,ushort const *,APPX_XML_LINE_INFORMATION *)
0x1800774c0  mov     rcx, [rbp+28h]; this
0x1800774c4  mov     edi, 80080204h
0x1800774c9  mov     dword ptr [rsp+60h+var_38], edi; char *
0x1800774cd  lea     rax, aHresult0x80080; "((HRESULT)0x80080204L)"
0x1800774d4  mov     [rsp+60h+var_40], rax; char *
0x1800774d9  lea     r9, aOsintegrationD_368; "OSIntegration::DEH::PackagedComExtensio"...
0x1800774e0  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800774e7  mov     edx, 0E9Ah; void *
0x1800774ec  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800774f1  test    cs:byte_1802E21CA, 4
0x1800774f8  jz      short loc_180077534
0x1800774fa  mov     rcx, [r15+28h]
0x1800774fe  mov     rbx, [rcx+0E0h]
0x180077505  mov     rcx, [rcx+110h]; unsigned __int16 *
0x18007750c  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x180077511  mov     qword ptr [rsp+60h+var_30], rbx
0x180077516  mov     dword ptr [rsp+60h+var_38], edi
0x18007751a  mov     ecx, dword ptr [rbp+var_20+4]
0x18007751d  mov     dword ptr [rsp+60h+var_40], ecx
0x180077521  mov     r9d, dword ptr [rbp+var_20]
0x180077525  mov     r8, rax
0x180077528  lea     rdx, PackagedComInvalidInterfaceTypeLib
0x18007752f  call    McTemplateU0zqqdz_EventWriteTransfer
0x180077534  mov     rcx, [r15+28h]
0x180077538  mov     rbx, [rcx+0E0h]
0x18007753f  mov     rcx, [rcx+110h]; unsigned __int16 *
0x180077546  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x18007754b  mov     [rsp+60h+var_28], rbx
0x180077550  mov     [rsp+60h+var_30], edi; int
0x180077554  mov     ecx, dword ptr [rbp+var_20+4]
0x180077557  mov     dword ptr [rsp+60h+var_38], ecx
0x18007755b  mov     ecx, dword ptr [rbp+var_20]
0x18007755e  mov     dword ptr [rsp+60h+var_40], ecx
0x180077562  mov     r9, rax
0x180077565  lea     r8, PackagedComInvalidInterfaceTypeLib
0x18007756c  mov     ecx, edi
0x18007756e  call    ??$appxLog@PEBGIIJPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEBGIIJPEAG@Z; details::appxLog<ushort const *,uint,uint,long,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort const *,uint,uint,long,ushort *)
0x180077573  lea     rax, aAppxEInvalidMa; "APPX_E_INVALID_MANIFEST"
0x18007757a  mov     edx, 0E9Ch; void *
0x18007757f  mov     dword ptr [rsp+60h+var_38], edi; char *
0x180077583  mov     [rsp+60h+var_40], rax; char *
0x180077588  lea     r9, aOsintegrationD_368; "OSIntegration::DEH::PackagedComExtensio"...
0x18007758f  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180077596  mov     rcx, [rbp+28h]; this
0x18007759a  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18007759f  nop
0x1800775a0  lea     rcx, [rbp+Buffer]
0x1800775a4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800775a9  mov     ebx, edi
0x1800775ab  lea     rcx, [rbp+arg_18]
0x1800775af  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800775b4  jmp     short loc_1800775DC
0x1800775b6  mov     rcx, rbx; void *
0x1800775b9  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1800775be  nop
0x1800775bf  mov     rcx, [rbp+arg_18.lpVtbl]
0x1800775c3  test    rcx, rcx
0x1800775c6  jz      short loc_1800775D9
0x1800775c8  mov     [rbp+arg_18.lpVtbl], r12
0x1800775cc  mov     rax, [rcx]
0x1800775cf  mov     rax, [rax+10h]
0x1800775d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800775d8  nop
0x1800775d9  mov     ebx, r12d
0x1800775dc  mov     rcx, [rbp+string]; string
0x1800775e0  call    cs:__imp_WindowsDeleteString
0x1800775e6  mov     eax, ebx
0x1800775e8  lea     r11, [rsp+60h+var_s0]
0x1800775ed  mov     rbx, [r11+30h]
0x1800775f1  mov     rsi, [r11+38h]
0x1800775f5  mov     rsp, r11
0x1800775f8  pop     r15
0x1800775fa  pop     r14
0x1800775fc  pop     r12
0x1800775fe  pop     rdi
0x1800775ff  pop     rbp
0x180077600  retn
```
