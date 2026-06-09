# OSIntegration::DEH::PackagedComExtensionHandler::ParseConversionFormats(IXMLDOMElement *,Windows::Foundation::Collections::IVector<HSTRING__ *> *)

- ea: `0x1801676ec`
- end: `0x180167b19`
- name: `?ParseConversionFormats@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@Z`
- size: `1069`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801672a0`

## callees

- `0x18000b3bc`
- `0x18000b9e0`
- `0x18003f7e0`
- `0x1800550f4`
- `0x18007d350`
- `0x180098ed0`
- `0x18009aff4`
- `0x18013ced4`
- `0x18013d6f8`
- `0x1801676ec`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180167807`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016783c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801678d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801678e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180167a1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180167a28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180167aa1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180167aaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180167807`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016783c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801678d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801678e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180167a1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180167a28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180167aa1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180167aaf`

## string_xrefs

- `0x180167778`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016794c`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1801679fa`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x180167a86`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x180167ad6`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1801679e7`: `APPX_E_INVALID_MANIFEST`
- `0x18016777f`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseConversionFormats`
- `0x180167945`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseConversionFormats`
- `0x1801679f3`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseConversionFormats`
- `0x180167a7f`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseConversionFormats`
- `0x180167acf`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseConversionFormats`
- `0x180167a58`: `ParseAndRetrieveAttribute( format.Get(), Internal::PackagedComConstants::formatNameAttribute, formatName.GetAddressOf(), &formatNameFound)`
- `0x180167a46`: `ParseAndRetrieveAttribute( format.Get(), Internal::PackagedComConstants::standardFormatAttribute, standardFormat.GetAddressOf(), &standardFormatFound)`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall OSIntegration::DEH::PackagedComExtensionHandler::ParseConversionFormats(
        __int64 a1,
        const struct IXMLDOMNode *a2,
        __int64 a3)
{
  HRESULT (__stdcall *get_childNodes)(IXMLDOMNode *, IXMLDOMNodeList **); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  const char *v9; // rax
  __int64 v10; // rdx
  int v11; // eax
  unsigned int i; // esi
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, _QWORD); // rbx
  int v15; // eax
  int v16; // eax
  OSIntegration::DEH::PackagedComExtensionHandler *v17; // rcx
  int v18; // eax
  OSIntegration::DEH::PackagedComExtensionHandler *v19; // rcx
  int v20; // eax
  int v21; // eax
  const char *v22; // rax
  __int64 v23; // rdx
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rbx
  unsigned int v27; // eax
  const unsigned __int16 *v28; // rax
  __int64 v29; // rdx
  bool *v31; // [rsp+20h] [rbp-50h]
  char *v32; // [rsp+28h] [rbp-48h]
  char *v33; // [rsp+28h] [rbp-48h]
  char *v34; // [rsp+28h] [rbp-48h]
  int v35; // [rsp+30h] [rbp-40h]
  int v36; // [rsp+40h] [rbp-30h] BYREF
  HSTRING v37; // [rsp+48h] [rbp-28h] BYREF
  HSTRING string; // [rsp+50h] [rbp-20h] BYREF
  __int64 (__fastcall ***v39)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-18h] BYREF
  struct IXMLDOMElement *v40; // [rsp+60h] [rbp-10h] BYREF
  __int64 v41; // [rsp+68h] [rbp-8h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+A8h] [rbp+38h]
  __int64 v43; // [rsp+B8h] [rbp+48h] BYREF
  bool v44; // [rsp+C8h] [rbp+58h] BYREF

  v41 = 0;
  v36 = 0;
  get_childNodes = a2->lpVtbl->get_childNodes;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
  v7 = ((__int64 (__fastcall *)(const struct IXMLDOMNode *, __int64 *))get_childNodes)(a2, &v41);
  v8 = v7;
  if ( v7 < 0 )
  {
    LODWORD(v32) = v7;
    v9 = "root->get_childNodes(&formatsNodes)";
    v10 = 2757;
LABEL_5:
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::ParseConversionFormats",
      v9,
      v32,
      v35);
    goto LABEL_30;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v41 + 64LL))(v41, &v36);
  v8 = v11;
  if ( v11 < 0 )
  {
    LODWORD(v32) = v11;
    v9 = "formatsNodes->get_length(&listLength)";
    v10 = 2758;
    goto LABEL_5;
  }
  for ( i = 0; ; ++i )
  {
    if ( (int)i >= v36 )
    {
      v8 = 0;
      goto LABEL_30;
    }
    v39 = 0;
    v13 = v41;
    v14 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v41 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
    v15 = v14(v13, i, &v39);
    v8 = v15;
    if ( v15 < 0 )
    {
      LODWORD(v32) = v15;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0xACB,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::ParseConversionFormats",
        "formatsNodes->get_item(nodeIndex, &node)",
        v32,
        v35);
      goto LABEL_28;
    }
    string = 0;
    v37 = 0;
    v44 = 0;
    LOBYTE(v43) = 0;
    v40 = 0;
    v16 = Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(&v39, (__int64 *)&v40);
    v8 = v16;
    if ( v16 < 0 )
    {
      LODWORD(v32) = v16;
      v22 = "node.As(&format)";
      v23 = 2772;
      goto LABEL_26;
    }
    WindowsDeleteString(string);
    string = 0;
    v18 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(
            v17,
            v40,
            L"FormatName",
            &string,
            &v44);
    v8 = v18;
    if ( v18 < 0 )
    {
      LODWORD(v32) = v18;
      v22 = "ParseAndRetrieveAttribute( format.Get(), Internal::PackagedComConstants::formatNameAttribute, formatName.Get"
            "AddressOf(), &formatNameFound)";
      v23 = 2778;
      goto LABEL_26;
    }
    WindowsDeleteString(v37);
    v37 = 0;
    v20 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(
            v19,
            v40,
            L"StandardFormat",
            &v37,
            (bool *)&v43);
    v8 = v20;
    if ( v20 < 0 )
    {
      LODWORD(v32) = v20;
      v22 = "ParseAndRetrieveAttribute( format.Get(), Internal::PackagedComConstants::standardFormatAttribute, standardFo"
            "rmat.GetAddressOf(), &standardFormatFound)";
      v23 = 2784;
LABEL_26:
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::ParseConversionFormats",
        v22,
        v32,
        v35);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
      WindowsDeleteString(v37);
      v37 = 0;
      WindowsDeleteString(string);
      string = 0;
LABEL_28:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
      goto LABEL_30;
    }
    if ( v44 )
    {
      if ( (_BYTE)v43 )
        break;
      v21 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)a3 + 104LL))(a3, string);
      v8 = v21;
      if ( v21 < 0 )
      {
        LODWORD(v32) = v21;
        v22 = "formatsValues->Append(formatName.Get())";
        v23 = 2788;
        goto LABEL_26;
      }
      goto LABEL_18;
    }
    if ( !(_BYTE)v43 )
      break;
    v24 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)a3 + 104LL))(a3, v37);
    v8 = v24;
    if ( v24 < 0 )
    {
      LODWORD(v32) = v24;
      v22 = "formatsValues->Append(standardFormat.Get())";
      v23 = 2792;
      goto LABEL_26;
    }
LABEL_18:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
    WindowsDeleteString(v37);
    v37 = 0;
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
  }
  v43 = 0;
  OSIntegration::Package::GetXmlLineInformation(
    *(OSIntegration::Package **)(a1 + 40),
    a2,
    0,
    (struct APPX_XML_LINE_INFORMATION *)&v43);
  LODWORD(v32) = -2146958844;
  wil::details::in1diag5::_Log_Hr(
    retaddr,
    (void *)0xAF7,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
    "OSIntegration::DEH::PackagedComExtensionHandler::ParseConversionFormats",
    "((HRESULT)0x80080204L)",
    v32,
    v35);
  if ( (byte_1802E21CA & 4) != 0 )
  {
    v25 = *(_QWORD *)(a1 + 40);
    v26 = *(_QWORD *)(v25 + 224);
    v27 = (unsigned int)RemovePIIfromFilePath(*(const unsigned __int16 **)(v25 + 272));
    McTemplateU0zqqdz_EventWriteTransfer(
      HIDWORD(v43),
      (unsigned int)PackagedComInvalidConversionFormat,
      v27,
      v43,
      SBYTE4(v43),
      4,
      v26);
  }
  v28 = RemovePIIfromFilePath(*(const unsigned __int16 **)(*(_QWORD *)(a1 + 40) + 272LL));
  LODWORD(v33) = HIDWORD(v43);
  LODWORD(v31) = v43;
  details::appxLog<unsigned short const *,unsigned int,unsigned int,long,unsigned short *>(
    -2146958844,
    v29,
    (const struct _EVENT_DESCRIPTOR *)PackagedComInvalidConversionFormat,
    v28,
    v31,
    v33);
  LODWORD(v34) = -2146958844;
  wil::details::in1diag5::Return_Hr(
    retaddr,
    (void *)0xAF9,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
    "OSIntegration::DEH::PackagedComExtensionHandler::ParseConversionFormats",
    "APPX_E_INVALID_MANIFEST",
    v34,
    -2146958844);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
  WindowsDeleteString(v37);
  v37 = 0;
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
  v8 = -2146958844;
LABEL_30:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
  return v8;
}

```

## disassembly

```asm
0x1801676ec  mov     [rsp-38h+arg_0], rbx
0x1801676f1  push    rbp
0x1801676f2  push    rsi
0x1801676f3  push    rdi
0x1801676f4  push    r12
0x1801676f6  push    r13
0x1801676f8  push    r14
0x1801676fa  push    r15
0x1801676fc  mov     rbp, rsp
0x1801676ff  sub     rsp, 70h
0x180167703  mov     r14, r8
0x180167706  mov     r15, rdx
0x180167709  mov     r13, rcx
0x18016770c  xor     r12d, r12d
0x18016770f  mov     [rbp+var_8], r12
0x180167713  mov     [rbp+var_30], r12d
0x180167717  mov     rax, [rdx]
0x18016771a  mov     rbx, [rax+60h]
0x18016771e  lea     rcx, [rbp+var_8]
0x180167722  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180167727  lea     rdx, [rbp+var_8]
0x18016772b  mov     rcx, r15
0x18016772e  mov     rax, rbx
0x180167731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167736  mov     ebx, eax
0x180167738  test    eax, eax
0x18016773a  jns     short loc_18016774E
0x18016773c  mov     dword ptr [rsp+70h+var_48], eax
0x180167740  lea     rax, aRootGetChildno_10; "root->get_childNodes(&formatsNodes)"
0x180167747  mov     edx, 0AC5h
0x18016774c  jmp     short loc_180167778
0x18016774e  mov     rcx, [rbp+var_8]
0x180167752  mov     rax, [rcx]
0x180167755  lea     rdx, [rbp+var_30]
0x180167759  mov     rax, [rax+40h]
0x18016775d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167762  mov     ebx, eax
0x180167764  test    eax, eax
0x180167766  jns     short loc_180167799
0x180167768  mov     dword ptr [rsp+70h+var_48], eax; char *
0x18016776c  lea     rax, aFormatsnodesGe_0; "formatsNodes->get_length(&listLength)"
0x180167773  mov     edx, 0AC6h; void *
0x180167778  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016777f  lea     r9, aOsintegrationD_76; "OSIntegration::DEH::PackagedComExtensio"...
0x180167786  mov     [rsp+70h+var_50], rax; char *
0x18016778b  mov     rcx, [rbp+38h]; this
0x18016778f  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180167794  jmp     loc_180167AF6
0x180167799  mov     esi, r12d
0x18016779c  cmp     esi, [rbp+var_30]
0x18016779f  jge     loc_180167AF3
0x1801677a5  mov     [rbp+var_18], r12
0x1801677a9  mov     rdi, [rbp+var_8]
0x1801677ad  mov     rax, [rdi]
0x1801677b0  mov     rbx, [rax+38h]
0x1801677b4  lea     rcx, [rbp+var_18]
0x1801677b8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801677bd  lea     r8, [rbp+var_18]
0x1801677c1  mov     edx, esi
0x1801677c3  mov     rcx, rdi
0x1801677c6  mov     rax, rbx
0x1801677c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801677ce  mov     ebx, eax
0x1801677d0  test    eax, eax
0x1801677d2  js      loc_180167ABB
0x1801677d8  mov     [rbp+string], r12
0x1801677dc  mov     [rbp+var_28], r12
0x1801677e0  mov     [rbp+arg_18], r12b
0x1801677e4  mov     byte ptr [rbp+arg_8], r12b
0x1801677e8  mov     [rbp+var_10], r12
0x1801677ec  lea     rdx, [rbp+var_10]
0x1801677f0  lea     rcx, [rbp+var_18]
0x1801677f4  call    ??$As@UIXMLDOMElement@@@?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIXMLDOMElement@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IXMLDOMElement>>)
0x1801677f9  mov     ebx, eax
0x1801677fb  test    eax, eax
0x1801677fd  js      loc_180167A66
0x180167803  mov     rcx, [rbp+string]; string
0x180167807  call    cs:__imp_WindowsDeleteString
0x18016780d  mov     [rbp+string], r12
0x180167811  lea     rax, [rbp+arg_18]
0x180167815  mov     [rsp+70h+var_50], rax; bool *
0x18016781a  lea     r9, [rbp+string]; HSTRING *
0x18016781e  lea     r8, aFormatname; "FormatName"
0x180167825  mov     rdx, [rbp+var_10]; struct IXMLDOMElement *
0x180167829  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x18016782e  mov     ebx, eax
0x180167830  test    eax, eax
0x180167832  js      loc_180167A54
0x180167838  mov     rcx, [rbp+var_28]; string
0x18016783c  call    cs:__imp_WindowsDeleteString
0x180167842  mov     [rbp+var_28], r12
0x180167846  lea     rax, [rbp+arg_8]
0x18016784a  mov     [rsp+70h+var_50], rax; bool *
0x18016784f  lea     r9, [rbp+var_28]; HSTRING *
0x180167853  lea     r8, aStandardformat; "StandardFormat"
0x18016785a  mov     rdx, [rbp+var_10]; struct IXMLDOMElement *
0x18016785e  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x180167863  mov     ebx, eax
0x180167865  test    eax, eax
0x180167867  js      loc_180167A42
0x18016786d  cmp     [rbp+arg_18], r12b
0x180167871  jz      short loc_1801678AB
0x180167873  cmp     byte ptr [rbp+arg_8], r12b
0x180167877  jnz     loc_180167915
0x18016787d  mov     rax, [r14]
0x180167880  mov     rdx, [rbp+string]
0x180167884  mov     rcx, r14
0x180167887  mov     rax, [rax+68h]
0x18016788b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167890  mov     ebx, eax
0x180167892  test    eax, eax
0x180167894  jns     short loc_1801678CA
0x180167896  mov     dword ptr [rsp+70h+var_48], eax
0x18016789a  lea     rax, aFormatsvaluesA_0; "formatsValues->Append(formatName.Get())"
0x1801678a1  mov     edx, 0AE4h
0x1801678a6  jmp     loc_180167A76
0x1801678ab  cmp     byte ptr [rbp+arg_8], r12b
0x1801678af  jz      short loc_180167915
0x1801678b1  mov     rax, [r14]
0x1801678b4  mov     rdx, [rbp+var_28]
0x1801678b8  mov     rcx, r14
0x1801678bb  mov     rax, [rax+68h]
0x1801678bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801678c4  mov     ebx, eax
0x1801678c6  test    eax, eax
0x1801678c8  js      short loc_180167900
0x1801678ca  lea     rcx, [rbp+var_10]
0x1801678ce  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801678d3  nop
0x1801678d4  mov     rcx, [rbp+var_28]; string
0x1801678d8  call    cs:__imp_WindowsDeleteString
0x1801678de  mov     [rbp+var_28], r12
0x1801678e2  mov     rcx, [rbp+string]; string
0x1801678e6  call    cs:__imp_WindowsDeleteString
0x1801678ec  mov     [rbp+string], r12
0x1801678f0  lea     rcx, [rbp+var_18]
0x1801678f4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801678f9  inc     esi
0x1801678fb  jmp     loc_18016779C
0x180167900  mov     dword ptr [rsp+70h+var_48], eax
0x180167904  lea     rax, aFormatsvaluesA; "formatsValues->Append(standardFormat.Ge"...
0x18016790b  mov     edx, 0AE8h
0x180167910  jmp     loc_180167A76
0x180167915  mov     [rbp+arg_8], r12
0x180167919  lea     r9, [rbp+arg_8]; struct APPX_XML_LINE_INFORMATION *
0x18016791d  xor     r8d, r8d; unsigned __int16 *
0x180167920  mov     rdx, r15; struct IXMLDOMNode *
0x180167923  mov     rcx, [r13+28h]; this
0x180167927  call    ?GetXmlLineInformation@Package@OSIntegration@@QEBAJPEBUIXMLDOMNode@@PEBGPEAUAPPX_XML_LINE_INFORMATION@@@Z; OSIntegration::Package::GetXmlLineInformation(IXMLDOMNode const *,ushort const *,APPX_XML_LINE_INFORMATION *)
0x18016792c  mov     rcx, [rbp+38h]; this
0x180167930  mov     edi, 80080204h
0x180167935  mov     dword ptr [rsp+70h+var_48], edi; char *
0x180167939  lea     rax, aHresult0x80080; "((HRESULT)0x80080204L)"
0x180167940  mov     [rsp+70h+var_50], rax; char *
0x180167945  lea     r9, aOsintegrationD_76; "OSIntegration::DEH::PackagedComExtensio"...
0x18016794c  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180167953  mov     edx, 0AF7h; void *
0x180167958  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016795d  test    cs:byte_1802E21CA, 4
0x180167964  jz      short loc_1801679A0
0x180167966  mov     rcx, [r13+28h]
0x18016796a  mov     rbx, [rcx+0E0h]
0x180167971  mov     rcx, [rcx+110h]; unsigned __int16 *
0x180167978  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x18016797d  mov     qword ptr [rsp+70h+var_40], rbx
0x180167982  mov     dword ptr [rsp+70h+var_48], edi
0x180167986  mov     ecx, dword ptr [rbp+arg_8+4]
0x180167989  mov     dword ptr [rsp+70h+var_50], ecx
0x18016798d  mov     r9d, dword ptr [rbp+arg_8]
0x180167991  mov     r8, rax
0x180167994  lea     rdx, PackagedComInvalidConversionFormat
0x18016799b  call    McTemplateU0zqqdz_EventWriteTransfer
0x1801679a0  mov     rcx, [r13+28h]
0x1801679a4  mov     rbx, [rcx+0E0h]
0x1801679ab  mov     rcx, [rcx+110h]; unsigned __int16 *
0x1801679b2  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x1801679b7  mov     [rsp+70h+var_38], rbx
0x1801679bc  mov     [rsp+70h+var_40], edi; int
0x1801679c0  mov     ecx, dword ptr [rbp+arg_8+4]
0x1801679c3  mov     dword ptr [rsp+70h+var_48], ecx
0x1801679c7  mov     ecx, dword ptr [rbp+arg_8]
0x1801679ca  mov     dword ptr [rsp+70h+var_50], ecx
0x1801679ce  mov     r9, rax
0x1801679d1  lea     r8, PackagedComInvalidConversionFormat
0x1801679d8  mov     ecx, edi
0x1801679da  call    ??$appxLog@PEBGIIJPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEBGIIJPEAG@Z; details::appxLog<ushort const *,uint,uint,long,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort const *,uint,uint,long,ushort *)
0x1801679df  mov     rcx, [rbp+38h]; this
0x1801679e3  mov     dword ptr [rsp+70h+var_48], edi; char *
0x1801679e7  lea     rax, aAppxEInvalidMa; "APPX_E_INVALID_MANIFEST"
0x1801679ee  mov     [rsp+70h+var_50], rax; char *
0x1801679f3  lea     r9, aOsintegrationD_76; "OSIntegration::DEH::PackagedComExtensio"...
0x1801679fa  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180167a01  mov     edx, 0AF9h; void *
0x180167a06  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180167a0b  nop
0x180167a0c  lea     rcx, [rbp+var_10]
0x180167a10  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180167a15  nop
0x180167a16  mov     rcx, [rbp+var_28]; string
0x180167a1a  call    cs:__imp_WindowsDeleteString
0x180167a20  mov     [rbp+var_28], r12
0x180167a24  mov     rcx, [rbp+string]; string
0x180167a28  call    cs:__imp_WindowsDeleteString
0x180167a2e  mov     [rbp+string], r12
0x180167a32  lea     rcx, [rbp+var_18]
0x180167a36  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180167a3b  mov     ebx, edi
0x180167a3d  jmp     loc_180167AF6
0x180167a42  mov     dword ptr [rsp+70h+var_48], eax
0x180167a46  lea     rax, aParseandretrie_11; "ParseAndRetrieveAttribute( format.Get()"...
0x180167a4d  mov     edx, 0AE0h
0x180167a52  jmp     short loc_180167A76
0x180167a54  mov     dword ptr [rsp+70h+var_48], eax
0x180167a58  lea     rax, aParseandretrie_34; "ParseAndRetrieveAttribute( format.Get()"...
0x180167a5f  mov     edx, 0ADAh
0x180167a64  jmp     short loc_180167A76
0x180167a66  mov     dword ptr [rsp+70h+var_48], eax; char *
0x180167a6a  lea     rax, aNodeAsFormat; "node.As(&format)"
0x180167a71  mov     edx, 0AD4h; void *
0x180167a76  mov     rcx, [rbp+38h]; this
0x180167a7a  mov     [rsp+70h+var_50], rax; char *
0x180167a7f  lea     r9, aOsintegrationD_76; "OSIntegration::DEH::PackagedComExtensio"...
0x180167a86  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180167a8d  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180167a92  nop
0x180167a93  lea     rcx, [rbp+var_10]
0x180167a97  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180167a9c  nop
0x180167a9d  mov     rcx, [rbp+var_28]; string
0x180167aa1  call    cs:__imp_WindowsDeleteString
0x180167aa7  mov     [rbp+var_28], r12
0x180167aab  mov     rcx, [rbp+string]; string
0x180167aaf  call    cs:__imp_WindowsDeleteString
0x180167ab5  mov     [rbp+string], r12
0x180167ab9  jmp     short loc_180167AE8
0x180167abb  mov     rcx, [rbp+38h]; this
0x180167abf  mov     dword ptr [rsp+70h+var_48], eax; char *
0x180167ac3  lea     rax, aFormatsnodesGe; "formatsNodes->get_item(nodeIndex, &node"...
0x180167aca  mov     [rsp+70h+var_50], rax; char *
0x180167acf  lea     r9, aOsintegrationD_76; "OSIntegration::DEH::PackagedComExtensio"...
0x180167ad6  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180167add  mov     edx, 0ACBh; void *
0x180167ae2  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180167ae7  nop
0x180167ae8  lea     rcx, [rbp+var_18]
0x180167aec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180167af1  jmp     short loc_180167AF6
0x180167af3  mov     ebx, r12d
0x180167af6  lea     rcx, [rbp+var_8]
0x180167afa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180167aff  mov     eax, ebx
0x180167b01  mov     rbx, [rsp+70h+arg_0]
0x180167b09  add     rsp, 70h
0x180167b0d  pop     r15
0x180167b0f  pop     r14
0x180167b11  pop     r13
0x180167b13  pop     r12
0x180167b15  pop     rdi
0x180167b16  pop     rsi
0x180167b17  pop     rbp
0x180167b18  retn
```
