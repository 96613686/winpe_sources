# OSIntegration::DEH::PackagedComExtensionHandler::ParseMiscStatus(IXMLDOMElement *,OSIntegration::DEH::IComClassRegistration *)

- ea: `0x18016ae84`
- end: `0x18016b21d`
- name: `?ParseMiscStatus@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEAUIComClassRegistration@23@@Z`
- size: `921`
- prototype: `int(OSIntegration::DEH::PackagedComExtensionHandler *__hidden this, struct IXMLDOMElement *, struct OSIntegration::DEH::IComClassRegistration *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180078b84`

## callees

- `0x18000b3bc`
- `0x18000b9e0`
- `0x18003f7e0`
- `0x18009aff4`
- `0x180166a68`
- `0x18016ae84`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016b04b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016b04b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016aeb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b00a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b03b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b07d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b0d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b0e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b0f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b18d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b19b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b1a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b1f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016aeb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b00a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b03b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b07d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b0d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b0e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b0f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b18d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b19b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b1a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016b1f4`

## string_xrefs

- `0x18016af19`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016b172`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016b1d0`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016aedf`: `ParseAndRetrieveAttribute( root, Internal::PackagedComConstants::oleMiscFlagAttribute, oleMiscFlag.GetAddressOf())`
- `0x18016af20`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseMiscStatus`
- `0x18016b16b`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseMiscStatus`
- `0x18016b1c9`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseMiscStatus`
- `0x18016b144`: `ParseAndRetrieveAttribute( aspect.Get(), Internal::PackagedComConstants::typeAttribute, aspectType.GetAddressOf())`
- `0x18016b132`: `MapEnumStringToHstringValue( Internal::PackagedComConstants::aspectMap, ARRAYSIZE(Internal::PackagedComConstants::aspectMap), aspectType.GetRawBuffer(nullptr), aspectTypeValue.GetAddressOf())`
- `0x18016b120`: `ParseAndRetrieveAttribute( aspect.Get(), Internal::PackagedComConstants::oleMiscFlagAttribute, aspectOleMiscFlag.GetAddressOf())`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall OSIntegration::DEH::PackagedComExtensionHandler::ParseMiscStatus(
        OSIntegration::DEH::PackagedComExtensionHandler *this,
        struct IXMLDOMElement *a2,
        struct OSIntegration::DEH::IComClassRegistration *a3)
{
  OSIntegration::DEH::PackagedComExtensionHandler *v5; // rcx
  int v6; // eax
  unsigned int v7; // ebx
  const char *v8; // rax
  __int64 v9; // rdx
  int v10; // eax
  HRESULT (__stdcall *get_childNodes)(IXMLDOMElement *, IXMLDOMNodeList **); // rbx
  int v12; // eax
  int v13; // eax
  unsigned int i; // esi
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD, _QWORD); // rbx
  int v17; // eax
  int v18; // eax
  OSIntegration::DEH::PackagedComExtensionHandler *v19; // rcx
  int v20; // eax
  int StringRawBuffer; // eax
  int v22; // eax
  OSIntegration::DEH::PackagedComExtensionHandler *v23; // rcx
  int v24; // eax
  int v25; // eax
  const char *v26; // rax
  __int64 v27; // rdx
  char *v29; // [rsp+28h] [rbp-38h]
  HSTRING v30; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  __int64 (__fastcall ***v32)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-20h] BYREF
  struct IXMLDOMElement *v33; // [rsp+48h] [rbp-18h] BYREF
  HSTRING v34; // [rsp+50h] [rbp-10h] BYREF
  __int64 v35; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+88h] [rbp+28h]
  int v37; // [rsp+90h] [rbp+30h] BYREF
  int v38; // [rsp+94h] [rbp+34h]
  HSTRING v39; // [rsp+A8h] [rbp+48h] BYREF

  v38 = HIDWORD(this);
  v35 = 0;
  v37 = 0;
  WindowsDeleteString(0);
  v34 = 0;
  v6 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(v5, a2, L"OleMiscFlag", &v34, 0);
  v7 = v6;
  if ( v6 < 0 )
  {
    LODWORD(v29) = v6;
    v8 = "ParseAndRetrieveAttribute( root, Internal::PackagedComConstants::oleMiscFlagAttribute, oleMiscFlag.GetAddressOf())";
    v9 = 3064;
LABEL_5:
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::ParseMiscStatus",
      v8,
      v29,
      (int)v30);
    goto LABEL_28;
  }
  v10 = (*(__int64 (__fastcall **)(struct OSIntegration::DEH::IComClassRegistration *, HSTRING))(*(_QWORD *)a3 + 168LL))(
          a3,
          v34);
  v7 = v10;
  if ( v10 < 0 )
  {
    LODWORD(v29) = v10;
    v8 = "classReg->SetMiscStatusDefault(oleMiscFlag.Get())";
    v9 = 3066;
    goto LABEL_5;
  }
  get_childNodes = a2->lpVtbl->get_childNodes;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  v12 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64 *))get_childNodes)(a2, &v35);
  v7 = v12;
  if ( v12 < 0 )
  {
    LODWORD(v29) = v12;
    v8 = "root->get_childNodes(&aspects)";
    v9 = 3068;
    goto LABEL_5;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v35 + 64LL))(v35, &v37);
  v7 = v13;
  if ( v13 < 0 )
  {
    LODWORD(v29) = v13;
    v8 = "aspects->get_length(&listLength)";
    v9 = 3069;
    goto LABEL_5;
  }
  for ( i = 0; (int)i < v37; ++i )
  {
    v32 = 0;
    v15 = v35;
    v16 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v35 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    v17 = v16(v15, i, &v32);
    v7 = v17;
    if ( v17 < 0 )
    {
      LODWORD(v29) = v17;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0xC02,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::ParseMiscStatus",
        "aspects->get_item(nodeIndex, &node)",
        v29,
        (int)v30);
      goto LABEL_26;
    }
    string = 0;
    v30 = 0;
    v39 = 0;
    v33 = 0;
    v18 = Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(&v32, (__int64 *)&v33);
    v7 = v18;
    if ( v18 < 0 )
    {
      LODWORD(v29) = v18;
      v26 = "node.As(&aspect)";
      v27 = 3081;
LABEL_24:
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)v27,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::ParseMiscStatus",
        v26,
        v29,
        (int)v30);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
      WindowsDeleteString(v39);
      v39 = 0;
      WindowsDeleteString(v30);
      v30 = 0;
      WindowsDeleteString(string);
      string = 0;
LABEL_26:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
      goto LABEL_28;
    }
    WindowsDeleteString(string);
    string = 0;
    v20 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(v19, v33, L"Type", &string, 0);
    v7 = v20;
    if ( v20 < 0 )
    {
      LODWORD(v29) = v20;
      v26 = "ParseAndRetrieveAttribute( aspect.Get(), Internal::PackagedComConstants::typeAttribute, aspectType.GetAddressOf())";
      v27 = 3086;
      goto LABEL_24;
    }
    WindowsDeleteString(v30);
    v30 = 0;
    StringRawBuffer = (unsigned int)WindowsGetStringRawBuffer(string, 0);
    v22 = OSIntegration::DEH::PackagedComExtensionHandler::MapEnumStringToHstringValue(
            (int)&v30,
            (int)&off_1802E0A00,
            4,
            StringRawBuffer,
            &v30);
    v7 = v22;
    if ( v22 < 0 )
    {
      LODWORD(v29) = v22;
      v26 = "MapEnumStringToHstringValue( Internal::PackagedComConstants::aspectMap, ARRAYSIZE(Internal::PackagedComConst"
            "ants::aspectMap), aspectType.GetRawBuffer(nullptr), aspectTypeValue.GetAddressOf())";
      v27 = 3092;
      goto LABEL_24;
    }
    WindowsDeleteString(v39);
    v39 = 0;
    v24 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(v23, v33, L"OleMiscFlag", &v39, 0);
    v7 = v24;
    if ( v24 < 0 )
    {
      LODWORD(v29) = v24;
      v26 = "ParseAndRetrieveAttribute( aspect.Get(), Internal::PackagedComConstants::oleMiscFlagAttribute, aspectOleMisc"
            "Flag.GetAddressOf())";
      v27 = 3097;
      goto LABEL_24;
    }
    v25 = (*(__int64 (__fastcall **)(struct OSIntegration::DEH::IComClassRegistration *, HSTRING, HSTRING))(*(_QWORD *)a3 + 176LL))(
            a3,
            v30,
            v39);
    v7 = v25;
    if ( v25 < 0 )
    {
      LODWORD(v29) = v25;
      v26 = "classReg->AddMiscStatusAspect(aspectTypeValue.Get(), aspectOleMiscFlag.Get())";
      v27 = 3099;
      goto LABEL_24;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    WindowsDeleteString(v39);
    v39 = 0;
    WindowsDeleteString(v30);
    v30 = 0;
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  }
  v7 = 0;
LABEL_28:
  WindowsDeleteString(v34);
  v34 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  return v7;
}

```

## disassembly

```asm
0x18016ae84  mov     [rsp-28h+arg_8], rbx
0x18016ae89  mov     [rsp-28h+arg_0], rcx
0x18016ae8e  push    rbp
0x18016ae8f  push    rsi
0x18016ae90  push    rdi
0x18016ae91  push    r14
0x18016ae93  push    r15
0x18016ae95  mov     rbp, rsp
0x18016ae98  sub     rsp, 60h
0x18016ae9c  mov     r14, r8
0x18016ae9f  mov     rdi, rdx
0x18016aea2  xor     r15d, r15d
0x18016aea5  mov     [rbp+var_8], r15
0x18016aea9  mov     dword ptr [rbp+arg_0], r15d
0x18016aead  mov     [rbp+var_10], r15
0x18016aeb1  xor     ecx, ecx; string
0x18016aeb3  call    cs:__imp_WindowsDeleteString
0x18016aeb9  mov     [rbp+var_10], r15
0x18016aebd  mov     [rsp+60h+var_40], r15; bool *
0x18016aec2  lea     r9, [rbp+var_10]; HSTRING *
0x18016aec6  lea     r8, aOlemiscflag; "OleMiscFlag"
0x18016aecd  mov     rdx, rdi; struct IXMLDOMElement *
0x18016aed0  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x18016aed5  mov     ebx, eax
0x18016aed7  test    eax, eax
0x18016aed9  jns     short loc_18016AEED
0x18016aedb  mov     dword ptr [rsp+60h+var_38], eax
0x18016aedf  lea     rax, aParseandretrie_33; "ParseAndRetrieveAttribute( root, Intern"...
0x18016aee6  mov     edx, 0BF8h
0x18016aeeb  jmp     short loc_18016AF19
0x18016aeed  mov     rax, [r14]
0x18016aef0  mov     rdx, [rbp+var_10]
0x18016aef4  mov     rcx, r14
0x18016aef7  mov     rax, [rax+0A8h]
0x18016aefe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016af03  mov     ebx, eax
0x18016af05  test    eax, eax
0x18016af07  jns     short loc_18016AF3A
0x18016af09  mov     dword ptr [rsp+60h+var_38], eax; char *
0x18016af0d  lea     rax, aClassregSetmis; "classReg->SetMiscStatusDefault(oleMiscF"...
0x18016af14  mov     edx, 0BFAh; void *
0x18016af19  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016af20  lea     r9, aOsintegrationD_49; "OSIntegration::DEH::PackagedComExtensio"...
0x18016af27  mov     [rsp+60h+var_40], rax; char *
0x18016af2c  mov     rcx, [rbp+28h]; this
0x18016af30  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016af35  jmp     loc_18016B1F0
0x18016af3a  mov     rax, [rdi]
0x18016af3d  mov     rbx, [rax+60h]
0x18016af41  lea     rcx, [rbp+var_8]
0x18016af45  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016af4a  lea     rdx, [rbp+var_8]
0x18016af4e  mov     rcx, rdi
0x18016af51  mov     rax, rbx
0x18016af54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016af59  mov     ebx, eax
0x18016af5b  test    eax, eax
0x18016af5d  jns     short loc_18016AF71
0x18016af5f  mov     dword ptr [rsp+60h+var_38], eax
0x18016af63  lea     rax, aRootGetChildno_1; "root->get_childNodes(&aspects)"
0x18016af6a  mov     edx, 0BFCh
0x18016af6f  jmp     short loc_18016AF19
0x18016af71  mov     rcx, [rbp+var_8]
0x18016af75  mov     rax, [rcx]
0x18016af78  lea     rdx, [rbp+arg_0]
0x18016af7c  mov     rax, [rax+40h]
0x18016af80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016af85  mov     ebx, eax
0x18016af87  test    eax, eax
0x18016af89  jns     short loc_18016AFA0
0x18016af8b  mov     dword ptr [rsp+60h+var_38], eax
0x18016af8f  lea     rax, aAspectsGetLeng; "aspects->get_length(&listLength)"
0x18016af96  mov     edx, 0BFDh
0x18016af9b  jmp     loc_18016AF19
0x18016afa0  mov     esi, r15d
0x18016afa3  cmp     esi, dword ptr [rbp+arg_0]
0x18016afa6  jge     loc_18016B1ED
0x18016afac  mov     [rbp+var_20], r15
0x18016afb0  mov     rdi, [rbp+var_8]
0x18016afb4  mov     rax, [rdi]
0x18016afb7  mov     rbx, [rax+38h]
0x18016afbb  lea     rcx, [rbp+var_20]
0x18016afbf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016afc4  lea     r8, [rbp+var_20]
0x18016afc8  mov     edx, esi
0x18016afca  mov     rcx, rdi
0x18016afcd  mov     rax, rbx
0x18016afd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016afd5  mov     ebx, eax
0x18016afd7  test    eax, eax
0x18016afd9  js      loc_18016B1B5
0x18016afdf  mov     [rbp+string], r15
0x18016afe3  mov     [rbp+var_30], r15
0x18016afe7  mov     [rbp+arg_18], r15
0x18016afeb  mov     [rbp+var_18], r15
0x18016afef  lea     rdx, [rbp+var_18]
0x18016aff3  lea     rcx, [rbp+var_20]
0x18016aff7  call    ??$As@UIXMLDOMElement@@@?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIXMLDOMElement@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IXMLDOMElement>>)
0x18016affc  mov     ebx, eax
0x18016affe  test    eax, eax
0x18016b000  js      loc_18016B152
0x18016b006  mov     rcx, [rbp+string]; string
0x18016b00a  call    cs:__imp_WindowsDeleteString
0x18016b010  mov     [rbp+string], r15
0x18016b014  mov     [rsp+60h+var_40], r15; bool *
0x18016b019  lea     r9, [rbp+string]; HSTRING *
0x18016b01d  lea     r8, aType_0; "Type"
0x18016b024  mov     rdx, [rbp+var_18]; struct IXMLDOMElement *
0x18016b028  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x18016b02d  mov     ebx, eax
0x18016b02f  test    eax, eax
0x18016b031  js      loc_18016B140
0x18016b037  mov     rcx, [rbp+var_30]; string
0x18016b03b  call    cs:__imp_WindowsDeleteString
0x18016b041  mov     [rbp+var_30], r15
0x18016b045  xor     edx, edx; length
0x18016b047  mov     rcx, [rbp+string]; string
0x18016b04b  call    cs:__imp_WindowsGetStringRawBuffer
0x18016b051  lea     rcx, [rbp+var_30]; int
0x18016b055  mov     [rsp+60h+var_40], rcx; string
0x18016b05a  mov     r9, rax; int
0x18016b05d  mov     r8d, 4; int
0x18016b063  lea     rdx, off_1802E0A00; int
0x18016b06a  call    ?MapEnumStringToHstringValue@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJQEBU?$EnumStringMapping@K@23@_KPEBGPEAPEAUHSTRING__@@@Z; OSIntegration::DEH::PackagedComExtensionHandler::MapEnumStringToHstringValue(OSIntegration::DEH::EnumStringMapping<ulong> const * const,unsigned __int64,ushort const *,HSTRING__ * *)
0x18016b06f  mov     ebx, eax
0x18016b071  test    eax, eax
0x18016b073  js      loc_18016B12E
0x18016b079  mov     rcx, [rbp+arg_18]; string
0x18016b07d  call    cs:__imp_WindowsDeleteString
0x18016b083  mov     [rbp+arg_18], r15
0x18016b087  mov     [rsp+60h+var_40], r15; bool *
0x18016b08c  lea     r9, [rbp+arg_18]; HSTRING *
0x18016b090  lea     r8, aOlemiscflag; "OleMiscFlag"
0x18016b097  mov     rdx, [rbp+var_18]; struct IXMLDOMElement *
0x18016b09b  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x18016b0a0  mov     ebx, eax
0x18016b0a2  test    eax, eax
0x18016b0a4  js      short loc_18016B11C
0x18016b0a6  mov     rax, [r14]
0x18016b0a9  mov     r8, [rbp+arg_18]
0x18016b0ad  mov     rdx, [rbp+var_30]
0x18016b0b1  mov     rcx, r14
0x18016b0b4  mov     rax, [rax+0B0h]
0x18016b0bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b0c0  mov     ebx, eax
0x18016b0c2  test    eax, eax
0x18016b0c4  js      short loc_18016B10A
0x18016b0c6  lea     rcx, [rbp+var_18]
0x18016b0ca  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016b0cf  nop
0x18016b0d0  mov     rcx, [rbp+arg_18]; string
0x18016b0d4  call    cs:__imp_WindowsDeleteString
0x18016b0da  mov     [rbp+arg_18], r15
0x18016b0de  mov     rcx, [rbp+var_30]; string
0x18016b0e2  call    cs:__imp_WindowsDeleteString
0x18016b0e8  mov     [rbp+var_30], r15
0x18016b0ec  mov     rcx, [rbp+string]; string
0x18016b0f0  call    cs:__imp_WindowsDeleteString
0x18016b0f6  mov     [rbp+string], r15
0x18016b0fa  lea     rcx, [rbp+var_20]
0x18016b0fe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016b103  inc     esi
0x18016b105  jmp     loc_18016AFA3
0x18016b10a  mov     dword ptr [rsp+60h+var_38], eax
0x18016b10e  lea     rax, aClassregAddmis; "classReg->AddMiscStatusAspect(aspectTyp"...
0x18016b115  mov     edx, 0C1Bh
0x18016b11a  jmp     short loc_18016B162
0x18016b11c  mov     dword ptr [rsp+60h+var_38], eax
0x18016b120  lea     rax, aParseandretrie_19; "ParseAndRetrieveAttribute( aspect.Get()"...
0x18016b127  mov     edx, 0C19h
0x18016b12c  jmp     short loc_18016B162
0x18016b12e  mov     dword ptr [rsp+60h+var_38], eax
0x18016b132  lea     rax, aMapenumstringt_0; "MapEnumStringToHstringValue( Internal::"...
0x18016b139  mov     edx, 0C14h
0x18016b13e  jmp     short loc_18016B162
0x18016b140  mov     dword ptr [rsp+60h+var_38], eax
0x18016b144  lea     rax, aParseandretrie_14; "ParseAndRetrieveAttribute( aspect.Get()"...
0x18016b14b  mov     edx, 0C0Eh
0x18016b150  jmp     short loc_18016B162
0x18016b152  mov     dword ptr [rsp+60h+var_38], eax; char *
0x18016b156  lea     rax, aNodeAsAspect; "node.As(&aspect)"
0x18016b15d  mov     edx, 0C09h; void *
0x18016b162  mov     rcx, [rbp+28h]; this
0x18016b166  mov     [rsp+60h+var_40], rax; char *
0x18016b16b  lea     r9, aOsintegrationD_49; "OSIntegration::DEH::PackagedComExtensio"...
0x18016b172  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016b179  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016b17e  nop
0x18016b17f  lea     rcx, [rbp+var_18]
0x18016b183  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016b188  nop
0x18016b189  mov     rcx, [rbp+arg_18]; string
0x18016b18d  call    cs:__imp_WindowsDeleteString
0x18016b193  mov     [rbp+arg_18], r15
0x18016b197  mov     rcx, [rbp+var_30]; string
0x18016b19b  call    cs:__imp_WindowsDeleteString
0x18016b1a1  mov     [rbp+var_30], r15
0x18016b1a5  mov     rcx, [rbp+string]; string
0x18016b1a9  call    cs:__imp_WindowsDeleteString
0x18016b1af  mov     [rbp+string], r15
0x18016b1b3  jmp     short loc_18016B1E2
0x18016b1b5  mov     rcx, [rbp+28h]; this
0x18016b1b9  mov     dword ptr [rsp+60h+var_38], eax; char *
0x18016b1bd  lea     rax, aAspectsGetItem; "aspects->get_item(nodeIndex, &node)"
0x18016b1c4  mov     [rsp+60h+var_40], rax; char *
0x18016b1c9  lea     r9, aOsintegrationD_49; "OSIntegration::DEH::PackagedComExtensio"...
0x18016b1d0  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016b1d7  mov     edx, 0C02h; void *
0x18016b1dc  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016b1e1  nop
0x18016b1e2  lea     rcx, [rbp+var_20]
0x18016b1e6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016b1eb  jmp     short loc_18016B1F0
0x18016b1ed  mov     ebx, r15d
0x18016b1f0  mov     rcx, [rbp+var_10]; string
0x18016b1f4  call    cs:__imp_WindowsDeleteString
0x18016b1fa  mov     [rbp+var_10], r15
0x18016b1fe  lea     rcx, [rbp+var_8]
0x18016b202  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016b207  mov     eax, ebx
0x18016b209  mov     rbx, [rsp+60h+arg_8]
0x18016b211  add     rsp, 60h
0x18016b215  pop     r15
0x18016b217  pop     r14
0x18016b219  pop     rdi
0x18016b21a  pop     rsi
0x18016b21b  pop     rbp
0x18016b21c  retn
```
