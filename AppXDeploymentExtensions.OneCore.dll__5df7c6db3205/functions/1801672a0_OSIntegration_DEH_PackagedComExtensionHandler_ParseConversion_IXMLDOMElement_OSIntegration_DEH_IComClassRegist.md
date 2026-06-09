# OSIntegration::DEH::PackagedComExtensionHandler::ParseConversion(IXMLDOMElement *,OSIntegration::DEH::IComClassRegistration *)

- ea: `0x1801672a0`
- end: `0x1801676e5`
- name: `?ParseConversion@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEAUIComClassRegistration@23@@Z`
- size: `1093`
- prototype: `int(OSIntegration::DEH::PackagedComExtensionHandler *__hidden this, struct IXMLDOMElement *, struct OSIntegration::DEH::IComClassRegistration *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180078b84`

## callees

- `0x18000b3bc`
- `0x180037da4`
- `0x18003f7e0`
- `0x1800550f4`
- `0x18007d350`
- `0x180098ed0`
- `0x18009aff4`
- `0x18013ced4`
- `0x18013d6f8`
- `0x1801656c4`
- `0x1801672a0`
- `0x1801676ec`
- `0x1802086d0`
- `0x180211010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1801675c9`
- `OLEAUT32!__imp_SysFreeString` at `0x1801676a2`
- `OLEAUT32!__imp_SysFreeString` at `0x1801675c9`
- `OLEAUT32!__imp_SysFreeString` at `0x1801676a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180167517`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801675bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180167694`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180167517`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801675bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180167694`

## string_xrefs

- `0x18016732e`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x180167391`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016743f`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x180167669`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016742c`: `APPX_E_INVALID_MANIFEST`
- `0x18016753c`: `Readable`
- `0x180167581`: `ReadWritable`
- `0x180167335`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseConversion`
- `0x18016738a`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseConversion`
- `0x180167438`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseConversion`
- `0x180167670`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseConversion`
- `0x180167603`: `GetCommaSeparatedValue(conversionValues.Get(), conversion.GetAddressOf())`
- `0x18016756c`: `classReg->SetConversionReadable(conversion.Get())`
- `0x1801675f1`: `classReg->SetConversionReadWritable(conversion.Get())`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall OSIntegration::DEH::PackagedComExtensionHandler::ParseConversion(
        OSIntegration::Package **this,
        const struct IXMLDOMNode *a2,
        struct OSIntegration::DEH::IComClassRegistration *a3)
{
  HRESULT (__stdcall *get_childNodes)(IXMLDOMElement *, IXMLDOMNodeList **); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  const char *v9; // rax
  __int64 v10; // rdx
  int v11; // eax
  int v12; // eax
  OSIntegration::Package *v13; // rcx
  __int64 v14; // rbx
  unsigned int v15; // eax
  const unsigned __int16 *v16; // rax
  __int64 v17; // rdx
  unsigned int i; // esi
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, _QWORD, __int64 *); // rbx
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  __int64 v27; // rcx
  int CommaSeparatedValue; // eax
  int v29; // eax
  const char *v30; // rax
  __int64 v31; // rdx
  int v32; // eax
  char *v34; // [rsp+28h] [rbp-48h]
  char *v35; // [rsp+28h] [rbp-48h]
  int v36; // [rsp+30h] [rbp-40h]
  __int64 v37; // [rsp+40h] [rbp-30h] BYREF
  __int64 v38; // [rsp+48h] [rbp-28h] BYREF
  wchar_t *String2; // [rsp+50h] [rbp-20h] BYREF
  const struct IXMLDOMNode *v40; // [rsp+58h] [rbp-18h] BYREF
  __int64 v41; // [rsp+60h] [rbp-10h] BYREF
  __int64 v42; // [rsp+68h] [rbp-8h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+98h] [rbp+28h]
  int v44; // [rsp+A8h] [rbp+38h] BYREF
  HSTRING string; // [rsp+B8h] [rbp+48h] BYREF

  v42 = 0;
  v44 = 0;
  get_childNodes = (HRESULT (__stdcall *)(IXMLDOMElement *, IXMLDOMNodeList **))a2->lpVtbl->get_childNodes;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  v7 = ((__int64 (__fastcall *)(const struct IXMLDOMNode *, __int64 *))get_childNodes)(a2, &v42);
  v8 = v7;
  if ( v7 < 0 )
  {
    LODWORD(v34) = v7;
    v9 = "root->get_childNodes(&conversionNodes)";
    v10 = 2697;
LABEL_5:
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::ParseConversion",
      v9,
      v34,
      v36);
    goto LABEL_33;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v42 + 64LL))(v42, &v44);
  v8 = v11;
  if ( v11 < 0 )
  {
    LODWORD(v34) = v11;
    v9 = "conversionNodes->get_length(&listLength)";
    v10 = 2698;
    goto LABEL_5;
  }
  v12 = v44;
  if ( v44 )
  {
    for ( i = 0; (int)i < v12; ++i )
    {
      v38 = 0;
      v40 = 0;
      String2 = 0;
      string = 0;
      v37 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
      v20 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(
              v19,
              &v37);
      v8 = v20;
      if ( v20 < 0 )
      {
        LODWORD(v34) = v20;
        v30 = "Vector<HSTRING>::Make(&conversionValues)";
        v31 = 2726;
        goto LABEL_31;
      }
      v21 = v42;
      v22 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v42 + 56LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
      v23 = v22(v21, i, &v38);
      v8 = v23;
      if ( v23 < 0 )
      {
        LODWORD(v34) = v23;
        v30 = "conversionNodes->get_item(nodeIndex, &node)";
        v31 = 2728;
        goto LABEL_31;
      }
      v24 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v38 + 328LL))(v38, &String2);
      v8 = v24;
      if ( v24 < 0 )
      {
        LODWORD(v34) = v24;
        v30 = "node->get_baseName(bstrNodeName.AddressOf())";
        v31 = 2729;
        goto LABEL_31;
      }
      v25 = Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(&v38, &v40);
      v8 = v25;
      if ( v25 < 0 )
      {
        LODWORD(v34) = v25;
        v30 = "node.As(&conversionFormat)";
        v31 = 2731;
        goto LABEL_31;
      }
      v26 = OSIntegration::DEH::PackagedComExtensionHandler::ParseConversionFormats((__int64)this, v40, v37);
      v8 = v26;
      if ( v26 < 0 )
      {
        LODWORD(v34) = v26;
        v30 = "ParseConversionFormats(conversionFormat.Get(), conversionValues.Get())";
        v31 = 2733;
        goto LABEL_31;
      }
      WindowsDeleteString(string);
      string = 0;
      CommaSeparatedValue = OSIntegration::DEH::PackagedComExtensionHandler::GetCommaSeparatedValue(v27, v37, &string);
      v8 = CommaSeparatedValue;
      if ( CommaSeparatedValue < 0 )
      {
        LODWORD(v34) = CommaSeparatedValue;
        v30 = "GetCommaSeparatedValue(conversionValues.Get(), conversion.GetAddressOf())";
        v31 = 2735;
        goto LABEL_31;
      }
      if ( !wcscmp_0(L"Readable", String2) )
      {
        v29 = (*(__int64 (__fastcall **)(struct OSIntegration::DEH::IComClassRegistration *, HSTRING))(*(_QWORD *)a3 + 128LL))(
                a3,
                string);
        v8 = v29;
        if ( v29 < 0 )
        {
          LODWORD(v34) = v29;
          v30 = "classReg->SetConversionReadable(conversion.Get())";
          v31 = 2739;
LABEL_31:
          wil::details::in1diag5::Return_Hr(
            retaddr,
            (void *)v31,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
            "OSIntegration::DEH::PackagedComExtensionHandler::ParseConversion",
            v30,
            v34,
            v36);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
          WindowsDeleteString(string);
          string = 0;
          SysFreeString(String2);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
          goto LABEL_33;
        }
      }
      else if ( !wcscmp_0(L"ReadWritable", String2) )
      {
        v32 = (*(__int64 (__fastcall **)(struct OSIntegration::DEH::IComClassRegistration *, HSTRING))(*(_QWORD *)a3 + 136LL))(
                a3,
                string);
        v8 = v32;
        if ( v32 < 0 )
        {
          LODWORD(v34) = v32;
          v30 = "classReg->SetConversionReadWritable(conversion.Get())";
          v31 = 2743;
          goto LABEL_31;
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
      WindowsDeleteString(string);
      string = 0;
      SysFreeString(String2);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
      v12 = v44;
    }
    v8 = 0;
  }
  else
  {
    v41 = 0;
    OSIntegration::Package::GetXmlLineInformation(this[5], a2, 0, (struct APPX_XML_LINE_INFORMATION *)&v41);
    LODWORD(v34) = -2146958844;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0xA9A,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::ParseConversion",
      "((HRESULT)0x80080204L)",
      v34,
      v36);
    if ( (byte_1802E21CA & 4) != 0 )
    {
      v13 = this[5];
      v14 = *((_QWORD *)v13 + 28);
      v15 = (unsigned int)RemovePIIfromFilePath(*((const unsigned __int16 **)v13 + 34));
      McTemplateU0zqqdz_EventWriteTransfer(
        HIDWORD(v41),
        (unsigned int)PackagedComInvalidConversion,
        v15,
        v41,
        SBYTE4(v41),
        4,
        v14);
    }
    v16 = RemovePIIfromFilePath(*((const unsigned __int16 **)this[5] + 34));
    details::appxLog<unsigned short const *,unsigned int,unsigned int,long,unsigned short *>(
      2148008452LL,
      v17,
      PackagedComInvalidConversion,
      v16);
    LODWORD(v35) = -2146958844;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xA9C,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::ParseConversion",
      "APPX_E_INVALID_MANIFEST",
      v35,
      -2146958844);
    v8 = -2146958844;
  }
LABEL_33:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  return v8;
}

```

## disassembly

```asm
0x1801672a0  mov     [rsp-28h+arg_0], rbx
0x1801672a5  mov     [rsp-28h+arg_10], rsi
0x1801672aa  push    rbp
0x1801672ab  push    rdi
0x1801672ac  push    r12
0x1801672ae  push    r14
0x1801672b0  push    r15
0x1801672b2  mov     rbp, rsp
0x1801672b5  sub     rsp, 70h
0x1801672b9  mov     r14, r8
0x1801672bc  mov     rdi, rdx
0x1801672bf  mov     r15, rcx
0x1801672c2  xor     r12d, r12d
0x1801672c5  mov     [rbp+var_8], r12
0x1801672c9  mov     [rbp+arg_8], r12d
0x1801672cd  mov     rax, [rdx]
0x1801672d0  mov     rbx, [rax+60h]
0x1801672d4  lea     rcx, [rbp+var_8]
0x1801672d8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801672dd  lea     rdx, [rbp+var_8]
0x1801672e1  mov     rcx, rdi
0x1801672e4  mov     rax, rbx
0x1801672e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801672ec  mov     ebx, eax
0x1801672ee  test    eax, eax
0x1801672f0  jns     short loc_180167304
0x1801672f2  mov     dword ptr [rsp+70h+var_48], eax
0x1801672f6  lea     rax, aRootGetChildno_6; "root->get_childNodes(&conversionNodes)"
0x1801672fd  mov     edx, 0A89h
0x180167302  jmp     short loc_18016732E
0x180167304  mov     rcx, [rbp+var_8]
0x180167308  mov     rax, [rcx]
0x18016730b  lea     rdx, [rbp+arg_8]
0x18016730f  mov     rax, [rax+40h]
0x180167313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167318  mov     ebx, eax
0x18016731a  test    eax, eax
0x18016731c  jns     short loc_18016734F
0x18016731e  mov     dword ptr [rsp+70h+var_48], eax; char *
0x180167322  lea     rax, aConversionnode_0; "conversionNodes->get_length(&listLength"...
0x180167329  mov     edx, 0A8Ah; void *
0x18016732e  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180167335  lea     r9, aOsintegrationD_9; "OSIntegration::DEH::PackagedComExtensio"...
0x18016733c  mov     [rsp+70h+var_50], rax; char *
0x180167341  mov     rcx, [rbp+28h]; this
0x180167345  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016734a  jmp     loc_1801676C1
0x18016734f  mov     eax, [rbp+arg_8]
0x180167352  test    eax, eax
0x180167354  jnz     loc_180167457
0x18016735a  mov     [rbp+var_10], r12
0x18016735e  lea     r9, [rbp+var_10]; struct APPX_XML_LINE_INFORMATION *
0x180167362  xor     r8d, r8d; unsigned __int16 *
0x180167365  mov     rdx, rdi; struct IXMLDOMNode *
0x180167368  mov     rcx, [r15+28h]; this
0x18016736c  call    ?GetXmlLineInformation@Package@OSIntegration@@QEBAJPEBUIXMLDOMNode@@PEBGPEAUAPPX_XML_LINE_INFORMATION@@@Z; OSIntegration::Package::GetXmlLineInformation(IXMLDOMNode const *,ushort const *,APPX_XML_LINE_INFORMATION *)
0x180167371  mov     rcx, [rbp+28h]; this
0x180167375  mov     edi, 80080204h
0x18016737a  mov     dword ptr [rsp+70h+var_48], edi; char *
0x18016737e  lea     rax, aHresult0x80080; "((HRESULT)0x80080204L)"
0x180167385  mov     [rsp+70h+var_50], rax; char *
0x18016738a  lea     r9, aOsintegrationD_9; "OSIntegration::DEH::PackagedComExtensio"...
0x180167391  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180167398  mov     edx, 0A9Ah; void *
0x18016739d  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x1801673a2  test    cs:byte_1802E21CA, 4
0x1801673a9  jz      short loc_1801673E5
0x1801673ab  mov     rcx, [r15+28h]
0x1801673af  mov     rbx, [rcx+0E0h]
0x1801673b6  mov     rcx, [rcx+110h]; unsigned __int16 *
0x1801673bd  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x1801673c2  mov     qword ptr [rsp+70h+var_40], rbx
0x1801673c7  mov     dword ptr [rsp+70h+var_48], edi
0x1801673cb  mov     ecx, dword ptr [rbp+var_10+4]
0x1801673ce  mov     dword ptr [rsp+70h+var_50], ecx
0x1801673d2  mov     r9d, dword ptr [rbp+var_10]
0x1801673d6  mov     r8, rax
0x1801673d9  lea     rdx, PackagedComInvalidConversion
0x1801673e0  call    McTemplateU0zqqdz_EventWriteTransfer
0x1801673e5  mov     rcx, [r15+28h]
0x1801673e9  mov     rbx, [rcx+0E0h]
0x1801673f0  mov     rcx, [rcx+110h]; unsigned __int16 *
0x1801673f7  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x1801673fc  mov     [rsp+70h+var_38], rbx
0x180167401  mov     [rsp+70h+var_40], edi; int
0x180167405  mov     ecx, dword ptr [rbp+var_10+4]
0x180167408  mov     dword ptr [rsp+70h+var_48], ecx
0x18016740c  mov     ecx, dword ptr [rbp+var_10]
0x18016740f  mov     dword ptr [rsp+70h+var_50], ecx
0x180167413  mov     r9, rax
0x180167416  lea     r8, PackagedComInvalidConversion
0x18016741d  mov     ecx, edi
0x18016741f  call    ??$appxLog@PEBGIIJPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEBGIIJPEAG@Z; details::appxLog<ushort const *,uint,uint,long,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort const *,uint,uint,long,ushort *)
0x180167424  mov     rcx, [rbp+28h]; this
0x180167428  mov     dword ptr [rsp+70h+var_48], edi; char *
0x18016742c  lea     rax, aAppxEInvalidMa; "APPX_E_INVALID_MANIFEST"
0x180167433  mov     [rsp+70h+var_50], rax; char *
0x180167438  lea     r9, aOsintegrationD_9; "OSIntegration::DEH::PackagedComExtensio"...
0x18016743f  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180167446  mov     edx, 0A9Ch; void *
0x18016744b  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180167450  mov     ebx, edi
0x180167452  jmp     loc_1801676C1
0x180167457  mov     esi, r12d
0x18016745a  cmp     esi, eax
0x18016745c  jge     loc_1801676BE
0x180167462  mov     [rbp+var_28], r12
0x180167466  mov     [rbp+var_18], r12
0x18016746a  mov     [rbp+String2], r12
0x18016746e  mov     [rbp+string], r12
0x180167472  mov     [rbp+var_30], r12
0x180167476  lea     rcx, [rbp+var_30]
0x18016747a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016747f  lea     rdx, [rbp+var_30]
0x180167483  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)
0x180167488  mov     ebx, eax
0x18016748a  test    eax, eax
0x18016748c  js      loc_180167659
0x180167492  mov     rdi, [rbp+var_8]
0x180167496  mov     rax, [rdi]
0x180167499  mov     rbx, [rax+38h]
0x18016749d  lea     rcx, [rbp+var_28]
0x1801674a1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801674a6  lea     r8, [rbp+var_28]
0x1801674aa  mov     edx, esi
0x1801674ac  mov     rcx, rdi
0x1801674af  mov     rax, rbx
0x1801674b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801674b7  mov     ebx, eax
0x1801674b9  test    eax, eax
0x1801674bb  js      loc_180167647
0x1801674c1  mov     rcx, [rbp+var_28]
0x1801674c5  mov     rax, [rcx]
0x1801674c8  lea     rdx, [rbp+String2]
0x1801674cc  mov     rax, [rax+148h]
0x1801674d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801674d8  mov     ebx, eax
0x1801674da  test    eax, eax
0x1801674dc  js      loc_180167635
0x1801674e2  lea     rdx, [rbp+var_18]
0x1801674e6  lea     rcx, [rbp+var_28]
0x1801674ea  call    ??$As@UIXMLDOMElement@@@?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIXMLDOMElement@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IXMLDOMElement>>)
0x1801674ef  mov     ebx, eax
0x1801674f1  test    eax, eax
0x1801674f3  js      loc_180167623
0x1801674f9  mov     r8, [rbp+var_30]
0x1801674fd  mov     rdx, [rbp+var_18]
0x180167501  mov     rcx, r15
0x180167504  call    ?ParseConversionFormats@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseConversionFormats(IXMLDOMElement *,Windows::Foundation::Collections::IVector<HSTRING__ *> *)
0x180167509  mov     ebx, eax
0x18016750b  test    eax, eax
0x18016750d  js      loc_180167611
0x180167513  mov     rcx, [rbp+string]; string
0x180167517  call    cs:__imp_WindowsDeleteString
0x18016751d  mov     [rbp+string], r12
0x180167521  lea     r8, [rbp+string]
0x180167525  mov     rdx, [rbp+var_30]
0x180167529  call    ?GetCommaSeparatedValue@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@PEAPEAUHSTRING__@@@Z; OSIntegration::DEH::PackagedComExtensionHandler::GetCommaSeparatedValue(Windows::Foundation::Collections::IVector<HSTRING__ *> *,HSTRING__ * *)
0x18016752e  mov     ebx, eax
0x180167530  test    eax, eax
0x180167532  js      loc_1801675FF
0x180167538  mov     rdx, [rbp+String2]; String2
0x18016753c  lea     rcx, aReadable; "Readable"
0x180167543  call    wcscmp_0
0x180167548  test    eax, eax
0x18016754a  jnz     short loc_18016757D
0x18016754c  mov     rax, [r14]
0x18016754f  mov     rdx, [rbp+string]
0x180167553  mov     rcx, r14
0x180167556  mov     rax, [rax+80h]
0x18016755d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167562  mov     ebx, eax
0x180167564  test    eax, eax
0x180167566  jns     short loc_1801675AD
0x180167568  mov     dword ptr [rsp+70h+var_48], eax
0x18016756c  lea     rax, aClassregSetcon_0; "classReg->SetConversionReadable(convers"...
0x180167573  mov     edx, 0AB3h
0x180167578  jmp     loc_180167669
0x18016757d  mov     rdx, [rbp+String2]; String2
0x180167581  lea     rcx, aReadwritable; "ReadWritable"
0x180167588  call    wcscmp_0
0x18016758d  test    eax, eax
0x18016758f  jnz     short loc_1801675AD
0x180167591  mov     rax, [r14]
0x180167594  mov     rdx, [rbp+string]
0x180167598  mov     rcx, r14
0x18016759b  mov     rax, [rax+88h]
0x1801675a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801675a7  mov     ebx, eax
0x1801675a9  test    eax, eax
0x1801675ab  js      short loc_1801675ED
0x1801675ad  lea     rcx, [rbp+var_30]
0x1801675b1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801675b6  nop
0x1801675b7  mov     rcx, [rbp+string]; string
0x1801675bb  call    cs:__imp_WindowsDeleteString
0x1801675c1  mov     [rbp+string], r12
0x1801675c5  mov     rcx, [rbp+String2]; bstrString
0x1801675c9  call    cs:__imp_SysFreeString
0x1801675cf  nop
0x1801675d0  lea     rcx, [rbp+var_18]
0x1801675d4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801675d9  nop
0x1801675da  lea     rcx, [rbp+var_28]
0x1801675de  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801675e3  inc     esi
0x1801675e5  mov     eax, [rbp+arg_8]
0x1801675e8  jmp     loc_18016745A
0x1801675ed  mov     dword ptr [rsp+70h+var_48], eax
0x1801675f1  lea     rax, aClassregSetcon; "classReg->SetConversionReadWritable(con"...
0x1801675f8  mov     edx, 0AB7h
0x1801675fd  jmp     short loc_180167669
0x1801675ff  mov     dword ptr [rsp+70h+var_48], eax
0x180167603  lea     rax, aGetcommasepara_0; "GetCommaSeparatedValue(conversionValues"...
0x18016760a  mov     edx, 0AAFh
0x18016760f  jmp     short loc_180167669
0x180167611  mov     dword ptr [rsp+70h+var_48], eax
0x180167615  lea     rax, aParseconversio_0; "ParseConversionFormats(conversionFormat"...
0x18016761c  mov     edx, 0AADh
0x180167621  jmp     short loc_180167669
0x180167623  mov     dword ptr [rsp+70h+var_48], eax
0x180167627  lea     rax, aNodeAsConversi; "node.As(&conversionFormat)"
0x18016762e  mov     edx, 0AABh
0x180167633  jmp     short loc_180167669
0x180167635  mov     dword ptr [rsp+70h+var_48], eax
0x180167639  lea     rax, aNodeGetBasenam; "node->get_baseName(bstrNodeName.Address"...
0x180167640  mov     edx, 0AA9h
0x180167645  jmp     short loc_180167669
0x180167647  mov     dword ptr [rsp+70h+var_48], eax
0x18016764b  lea     rax, aConversionnode; "conversionNodes->get_item(nodeIndex, &n"...
0x180167652  mov     edx, 0AA8h
0x180167657  jmp     short loc_180167669
0x180167659  mov     dword ptr [rsp+70h+var_48], eax; char *
0x18016765d  lea     rax, aVectorHstringM_0; "Vector<HSTRING>::Make(&conversionValues"...
0x180167664  mov     edx, 0AA6h; void *
0x180167669  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180167670  lea     r9, aOsintegrationD_9; "OSIntegration::DEH::PackagedComExtensio"...
0x180167677  mov     [rsp+70h+var_50], rax; char *
0x18016767c  mov     rcx, [rbp+28h]; this
0x180167680  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180167685  nop
0x180167686  lea     rcx, [rbp+var_30]
0x18016768a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016768f  nop
0x180167690  mov     rcx, [rbp+string]; string
0x180167694  call    cs:__imp_WindowsDeleteString
0x18016769a  mov     [rbp+string], r12
0x18016769e  mov     rcx, [rbp+String2]; bstrString
0x1801676a2  call    cs:__imp_SysFreeString
0x1801676a8  nop
0x1801676a9  lea     rcx, [rbp+var_18]
0x1801676ad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801676b2  nop
0x1801676b3  lea     rcx, [rbp+var_28]
0x1801676b7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801676bc  jmp     short loc_1801676C1
0x1801676be  mov     ebx, r12d
0x1801676c1  lea     rcx, [rbp+var_8]
0x1801676c5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801676ca  mov     eax, ebx
0x1801676cc  lea     r11, [rsp+70h+var_s0]
0x1801676d1  mov     rbx, [r11+30h]
0x1801676d5  mov     rsi, [r11+40h]
0x1801676d9  mov     rsp, r11
0x1801676dc  pop     r15
0x1801676de  pop     r14
0x1801676e0  pop     r12
0x1801676e2  pop     rdi
0x1801676e3  pop     rbp
0x1801676e4  retn
```
