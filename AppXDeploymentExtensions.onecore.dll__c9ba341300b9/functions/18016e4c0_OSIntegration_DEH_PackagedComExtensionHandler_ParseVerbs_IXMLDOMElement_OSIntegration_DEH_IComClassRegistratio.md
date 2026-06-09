# OSIntegration::DEH::PackagedComExtensionHandler::ParseVerbs(IXMLDOMElement *,OSIntegration::DEH::IComClassRegistration *)

- ea: `0x18016e4c0`
- end: `0x18016e98b`
- name: `?ParseVerbs@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEAUIComClassRegistration@23@@Z`
- size: `1227`
- prototype: `__int64 __fastcall(OSIntegration::DEH::PackagedComExtensionHandler *__hidden this, struct IXMLDOMElement *, struct OSIntegration::DEH::IComClassRegistration *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180078b84`

## callees

- `0x18000b3bc`
- `0x18000b9e0`
- `0x180037da4`
- `0x18003f7e0`
- `0x180083aa4`
- `0x18009aff4`
- `0x1801656c4`
- `0x18016e4c0`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e601`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e632`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e684`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e6d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e722`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e77b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e789`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e797`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e7a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e7b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e8e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e8f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e904`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e912`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e920`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e601`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e632`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e684`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e6d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e722`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e77b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e789`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e797`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e7a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e7b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e8e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e8f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e904`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e912`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016e920`

## string_xrefs

- `0x18016e54e`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016e885`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016e8c8`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016e947`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016e80d`: `ParseAndRetrieveAttribute( verbElement.Get(), Internal::PackagedComConstants::oleVerbFlagAttribute, oleVerbFlag.GetAddressOf())`
- `0x18016e7e6`: `GetCommaSeparatedValue(verbValues.Get(), verb.GetAddressOf())`
- `0x18016e555`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseVerbs`
- `0x18016e88c`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseVerbs`
- `0x18016e8c1`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseVerbs`
- `0x18016e940`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseVerbs`
- `0x18016e867`: `ParseAndRetrieveAttribute( verbElement.Get(), Internal::PackagedComConstants::idAttribute, id.GetAddressOf())`
- `0x18016e855`: `ParseAndRetrieveLocalizableAttribute( verbElement.Get(), Internal::PackagedComConstants::displayNameAttribute, displayName.GetAddressOf())`
- `0x18016e831`: `ParseAndRetrieveAttribute( verbElement.Get(), Internal::PackagedComConstants::appendMenuFlagAttribute, appendMenuFlag.GetAddressOf())`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall OSIntegration::DEH::PackagedComExtensionHandler::ParseVerbs(
        OSIntegration::DEH::PackagedComExtensionHandler *this,
        struct IXMLDOMElement *a2,
        struct OSIntegration::DEH::IComClassRegistration *a3)
{
  HRESULT (__stdcall *get_childNodes)(IXMLDOMElement *, IXMLDOMNodeList **); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  const char *v9; // rax
  __int64 v10; // rdx
  int v11; // eax
  unsigned int i; // esi
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, _QWORD); // rbx
  int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  int v18; // eax
  OSIntegration::DEH::PackagedComExtensionHandler *v19; // rcx
  int v20; // eax
  int v21; // eax
  int v22; // eax
  OSIntegration::DEH::PackagedComExtensionHandler *v23; // rcx
  int v24; // eax
  int v25; // eax
  OSIntegration::DEH::PackagedComExtensionHandler *v26; // rcx
  int v27; // eax
  int v28; // eax
  __int64 v29; // rcx
  int CommaSeparatedValue; // eax
  int v31; // eax
  const char *v32; // rax
  __int64 v33; // rdx
  char *v35; // [rsp+28h] [rbp-48h]
  HSTRING v36; // [rsp+30h] [rbp-40h] BYREF
  HSTRING v37; // [rsp+38h] [rbp-38h] BYREF
  HSTRING v38; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-28h] BYREF
  __int64 v40; // [rsp+50h] [rbp-20h] BYREF
  struct IXMLDOMElement *v41; // [rsp+58h] [rbp-18h] BYREF
  __int64 (__fastcall ***v42)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-10h] BYREF
  __int64 v43; // [rsp+68h] [rbp-8h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+98h] [rbp+28h]
  int v45; // [rsp+A8h] [rbp+38h] BYREF
  HSTRING v46; // [rsp+B8h] [rbp+48h] BYREF

  v43 = 0;
  v45 = 0;
  get_childNodes = a2->lpVtbl->get_childNodes;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  v7 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64 *))get_childNodes)(a2, &v43);
  v8 = v7;
  if ( v7 < 0 )
  {
    LODWORD(v35) = v7;
    v9 = "root->get_childNodes(&verbs)";
    v10 = 2997;
LABEL_5:
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::ParseVerbs",
      v9,
      v35,
      (int)v36);
    goto LABEL_37;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v43 + 64LL))(v43, &v45);
  v8 = v11;
  if ( v11 < 0 )
  {
    LODWORD(v35) = v11;
    v9 = "verbs->get_length(&listLength)";
    v10 = 2998;
    goto LABEL_5;
  }
  for ( i = 0; (int)i < v45; ++i )
  {
    v42 = 0;
    v13 = v43;
    v14 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v43 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    v15 = v14(v13, i, &v42);
    v8 = v15;
    if ( v15 < 0 )
    {
      LODWORD(v35) = v15;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0xBBB,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::ParseVerbs",
        "verbs->get_item(nodeIndex, &node)",
        v35,
        (int)v36);
      goto LABEL_35;
    }
    string = 0;
    v38 = 0;
    v37 = 0;
    v36 = 0;
    v46 = 0;
    v40 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
    v17 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(
            v16,
            &v40);
    v8 = v17;
    if ( v17 < 0 )
    {
      LODWORD(v35) = v17;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0xBC4,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::ParseVerbs",
        "Vector<HSTRING>::Make(&verbValues)",
        v35,
        (int)v36);
      goto LABEL_33;
    }
    v41 = 0;
    v18 = Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(&v42, (__int64 *)&v41);
    v8 = v18;
    if ( v18 < 0 )
    {
      LODWORD(v35) = v18;
      v32 = "node.As(&verbElement)";
      v33 = 3015;
LABEL_31:
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)v33,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::ParseVerbs",
        v32,
        v35,
        (int)v36);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
LABEL_33:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
      WindowsDeleteString(v46);
      v46 = 0;
      WindowsDeleteString(v36);
      v36 = 0;
      WindowsDeleteString(v37);
      v37 = 0;
      WindowsDeleteString(v38);
      v38 = 0;
      WindowsDeleteString(string);
      string = 0;
LABEL_35:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      goto LABEL_37;
    }
    WindowsDeleteString(string);
    string = 0;
    v20 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(
            v19,
            v41,
            (const unsigned __int16 *)&stru_180231B98,
            &string,
            0);
    v8 = v20;
    if ( v20 < 0 )
    {
      LODWORD(v35) = v20;
      v32 = "ParseAndRetrieveAttribute( verbElement.Get(), Internal::PackagedComConstants::idAttribute, id.GetAddressOf())";
      v33 = 3021;
      goto LABEL_31;
    }
    WindowsDeleteString(v38);
    v38 = 0;
    v21 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveLocalizableAttribute(
            this,
            v41,
            L"DisplayName",
            &v38,
            0);
    v8 = v21;
    if ( v21 < 0 )
    {
      LODWORD(v35) = v21;
      v32 = "ParseAndRetrieveLocalizableAttribute( verbElement.Get(), Internal::PackagedComConstants::displayNameAttribut"
            "e, displayName.GetAddressOf())";
      v33 = 3026;
      goto LABEL_31;
    }
    v22 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v40 + 104LL))(v40, v38);
    v8 = v22;
    if ( v22 < 0 )
    {
      LODWORD(v35) = v22;
      v32 = "verbValues->Append(displayName.Get())";
      v33 = 3028;
      goto LABEL_31;
    }
    WindowsDeleteString(v37);
    v37 = 0;
    v24 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(
            v23,
            v41,
            L"AppendMenuFlag",
            &v37,
            0);
    v8 = v24;
    if ( v24 < 0 )
    {
      LODWORD(v35) = v24;
      v32 = "ParseAndRetrieveAttribute( verbElement.Get(), Internal::PackagedComConstants::appendMenuFlagAttribute, appen"
            "dMenuFlag.GetAddressOf())";
      v33 = 3033;
      goto LABEL_31;
    }
    v25 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v40 + 104LL))(v40, v37);
    v8 = v25;
    if ( v25 < 0 )
    {
      LODWORD(v35) = v25;
      v32 = "verbValues->Append(appendMenuFlag.Get())";
      v33 = 3035;
      goto LABEL_31;
    }
    WindowsDeleteString(v36);
    v36 = 0;
    v27 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(v26, v41, L"OleVerbFlag", &v36, 0);
    v8 = v27;
    if ( v27 < 0 )
    {
      LODWORD(v35) = v27;
      v32 = "ParseAndRetrieveAttribute( verbElement.Get(), Internal::PackagedComConstants::oleVerbFlagAttribute, oleVerbF"
            "lag.GetAddressOf())";
      v33 = 3040;
      goto LABEL_31;
    }
    v28 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v40 + 104LL))(v40, v36);
    v8 = v28;
    if ( v28 < 0 )
    {
      LODWORD(v35) = v28;
      v32 = "verbValues->Append(oleVerbFlag.Get())";
      v33 = 3042;
      goto LABEL_31;
    }
    WindowsDeleteString(v46);
    v46 = 0;
    CommaSeparatedValue = OSIntegration::DEH::PackagedComExtensionHandler::GetCommaSeparatedValue(v29, v40, &v46);
    v8 = CommaSeparatedValue;
    if ( CommaSeparatedValue < 0 )
    {
      LODWORD(v35) = CommaSeparatedValue;
      v32 = "GetCommaSeparatedValue(verbValues.Get(), verb.GetAddressOf())";
      v33 = 3044;
      goto LABEL_31;
    }
    v31 = (*(__int64 (__fastcall **)(struct OSIntegration::DEH::IComClassRegistration *, HSTRING, HSTRING))(*(_QWORD *)a3 + 160LL))(
            a3,
            string,
            v46);
    v8 = v31;
    if ( v31 < 0 )
    {
      LODWORD(v35) = v31;
      v32 = "classReg->AddVerb(id.Get(), verb.Get())";
      v33 = 3046;
      goto LABEL_31;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
    WindowsDeleteString(v46);
    v46 = 0;
    WindowsDeleteString(v36);
    v36 = 0;
    WindowsDeleteString(v37);
    v37 = 0;
    WindowsDeleteString(v38);
    v38 = 0;
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  }
  v8 = 0;
LABEL_37:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  return v8;
}

```

## disassembly

```asm
0x18016e4c0  mov     [rsp-28h+arg_0], rbx
0x18016e4c5  mov     [rsp-28h+arg_10], rsi
0x18016e4ca  push    rbp
0x18016e4cb  push    rdi
0x18016e4cc  push    r12
0x18016e4ce  push    r14
0x18016e4d0  push    r15
0x18016e4d2  mov     rbp, rsp
0x18016e4d5  sub     rsp, 70h
0x18016e4d9  mov     r14, r8
0x18016e4dc  mov     rdi, rdx
0x18016e4df  mov     r15, rcx
0x18016e4e2  xor     r12d, r12d
0x18016e4e5  mov     [rbp+var_8], r12
0x18016e4e9  mov     [rbp+arg_8], r12d
0x18016e4ed  mov     rax, [rdx]
0x18016e4f0  mov     rbx, [rax+60h]
0x18016e4f4  lea     rcx, [rbp+var_8]
0x18016e4f8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016e4fd  lea     rdx, [rbp+var_8]
0x18016e501  mov     rcx, rdi
0x18016e504  mov     rax, rbx
0x18016e507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016e50c  mov     ebx, eax
0x18016e50e  test    eax, eax
0x18016e510  jns     short loc_18016E524
0x18016e512  mov     dword ptr [rsp+70h+var_48], eax
0x18016e516  lea     rax, aRootGetChildno_4; "root->get_childNodes(&verbs)"
0x18016e51d  mov     edx, 0BB5h
0x18016e522  jmp     short loc_18016E54E
0x18016e524  mov     rcx, [rbp+var_8]
0x18016e528  mov     rax, [rcx]
0x18016e52b  lea     rdx, [rbp+arg_8]
0x18016e52f  mov     rax, [rax+40h]
0x18016e533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016e538  mov     ebx, eax
0x18016e53a  test    eax, eax
0x18016e53c  jns     short loc_18016E56F
0x18016e53e  mov     dword ptr [rsp+70h+var_48], eax; char *
0x18016e542  lea     rax, aVerbsGetLength; "verbs->get_length(&listLength)"
0x18016e549  mov     edx, 0BB6h; void *
0x18016e54e  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016e555  lea     r9, aOsintegrationD_507; "OSIntegration::DEH::PackagedComExtensio"...
0x18016e55c  mov     [rsp+70h+var_50], rax; char *
0x18016e561  mov     rcx, [rbp+28h]; this
0x18016e565  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016e56a  jmp     loc_18016E967
0x18016e56f  mov     esi, r12d
0x18016e572  cmp     esi, [rbp+arg_8]
0x18016e575  jge     loc_18016E964
0x18016e57b  mov     [rbp+var_10], r12
0x18016e57f  mov     rdi, [rbp+var_8]
0x18016e583  mov     rax, [rdi]
0x18016e586  mov     rbx, [rax+38h]
0x18016e58a  lea     rcx, [rbp+var_10]
0x18016e58e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016e593  lea     r8, [rbp+var_10]
0x18016e597  mov     edx, esi
0x18016e599  mov     rcx, rdi
0x18016e59c  mov     rax, rbx
0x18016e59f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016e5a4  mov     ebx, eax
0x18016e5a6  test    eax, eax
0x18016e5a8  js      loc_18016E92C
0x18016e5ae  mov     [rbp+string], r12
0x18016e5b2  mov     [rbp+var_30], r12
0x18016e5b6  mov     [rbp+var_38], r12
0x18016e5ba  mov     [rbp+var_40], r12
0x18016e5be  mov     [rbp+arg_18], r12
0x18016e5c2  mov     [rbp+var_20], r12
0x18016e5c6  lea     rcx, [rbp+var_20]
0x18016e5ca  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016e5cf  lea     rdx, [rbp+var_20]
0x18016e5d3  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)
0x18016e5d8  mov     ebx, eax
0x18016e5da  test    eax, eax
0x18016e5dc  js      loc_18016E8AD
0x18016e5e2  mov     [rbp+var_18], r12
0x18016e5e6  lea     rdx, [rbp+var_18]
0x18016e5ea  lea     rcx, [rbp+var_10]
0x18016e5ee  call    ??$As@UIXMLDOMElement@@@?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIXMLDOMElement@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IXMLDOMElement>>)
0x18016e5f3  mov     ebx, eax
0x18016e5f5  test    eax, eax
0x18016e5f7  js      loc_18016E875
0x18016e5fd  mov     rcx, [rbp+string]; string
0x18016e601  call    cs:__imp_WindowsDeleteString
0x18016e607  mov     [rbp+string], r12
0x18016e60b  mov     [rsp+70h+var_50], r12; bool *
0x18016e610  lea     r9, [rbp+string]; HSTRING *
0x18016e614  lea     r8, stru_180231B98; unsigned __int16 *
0x18016e61b  mov     rdx, [rbp+var_18]; struct IXMLDOMElement *
0x18016e61f  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x18016e624  mov     ebx, eax
0x18016e626  test    eax, eax
0x18016e628  js      loc_18016E863
0x18016e62e  mov     rcx, [rbp+var_30]; string
0x18016e632  call    cs:__imp_WindowsDeleteString
0x18016e638  mov     [rbp+var_30], r12
0x18016e63c  mov     [rsp+70h+var_50], r12; bool *
0x18016e641  lea     r9, [rbp+var_30]; HSTRING *
0x18016e645  lea     r8, aDisplayname; "DisplayName"
0x18016e64c  mov     rdx, [rbp+var_18]; struct IXMLDOMElement *
0x18016e650  mov     rcx, r15; this
0x18016e653  call    ?ParseAndRetrieveLocalizableAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveLocalizableAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x18016e658  mov     ebx, eax
0x18016e65a  test    eax, eax
0x18016e65c  js      loc_18016E851
0x18016e662  mov     rcx, [rbp+var_20]
0x18016e666  mov     rax, [rcx]
0x18016e669  mov     rdx, [rbp+var_30]
0x18016e66d  mov     rax, [rax+68h]
0x18016e671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016e676  mov     ebx, eax
0x18016e678  test    eax, eax
0x18016e67a  js      loc_18016E83F
0x18016e680  mov     rcx, [rbp+var_38]; string
0x18016e684  call    cs:__imp_WindowsDeleteString
0x18016e68a  mov     [rbp+var_38], r12
0x18016e68e  mov     [rsp+70h+var_50], r12; bool *
0x18016e693  lea     r9, [rbp+var_38]; HSTRING *
0x18016e697  lea     r8, aAppendmenuflag; "AppendMenuFlag"
0x18016e69e  mov     rdx, [rbp+var_18]; struct IXMLDOMElement *
0x18016e6a2  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x18016e6a7  mov     ebx, eax
0x18016e6a9  test    eax, eax
0x18016e6ab  js      loc_18016E82D
0x18016e6b1  mov     rcx, [rbp+var_20]
0x18016e6b5  mov     rax, [rcx]
0x18016e6b8  mov     rdx, [rbp+var_38]
0x18016e6bc  mov     rax, [rax+68h]
0x18016e6c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016e6c5  mov     ebx, eax
0x18016e6c7  test    eax, eax
0x18016e6c9  js      loc_18016E81B
0x18016e6cf  mov     rcx, [rbp+var_40]; string
0x18016e6d3  call    cs:__imp_WindowsDeleteString
0x18016e6d9  mov     [rbp+var_40], r12
0x18016e6dd  mov     [rsp+70h+var_50], r12; bool *
0x18016e6e2  lea     r9, [rbp+var_40]; HSTRING *
0x18016e6e6  lea     r8, aOleverbflag; "OleVerbFlag"
0x18016e6ed  mov     rdx, [rbp+var_18]; struct IXMLDOMElement *
0x18016e6f1  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x18016e6f6  mov     ebx, eax
0x18016e6f8  test    eax, eax
0x18016e6fa  js      loc_18016E809
0x18016e700  mov     rcx, [rbp+var_20]
0x18016e704  mov     rax, [rcx]
0x18016e707  mov     rdx, [rbp+var_40]
0x18016e70b  mov     rax, [rax+68h]
0x18016e70f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016e714  mov     ebx, eax
0x18016e716  test    eax, eax
0x18016e718  js      loc_18016E7F7
0x18016e71e  mov     rcx, [rbp+arg_18]; string
0x18016e722  call    cs:__imp_WindowsDeleteString
0x18016e728  mov     [rbp+arg_18], r12
0x18016e72c  lea     r8, [rbp+arg_18]
0x18016e730  mov     rdx, [rbp+var_20]
0x18016e734  call    ?GetCommaSeparatedValue@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@PEAPEAUHSTRING__@@@Z; OSIntegration::DEH::PackagedComExtensionHandler::GetCommaSeparatedValue(Windows::Foundation::Collections::IVector<HSTRING__ *> *,HSTRING__ * *)
0x18016e739  mov     ebx, eax
0x18016e73b  test    eax, eax
0x18016e73d  js      loc_18016E7E2
0x18016e743  mov     rax, [r14]
0x18016e746  mov     r8, [rbp+arg_18]
0x18016e74a  mov     rdx, [rbp+string]
0x18016e74e  mov     rcx, r14
0x18016e751  mov     rax, [rax+0A0h]
0x18016e758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016e75d  mov     ebx, eax
0x18016e75f  test    eax, eax
0x18016e761  js      short loc_18016E7CD
0x18016e763  lea     rcx, [rbp+var_18]
0x18016e767  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016e76c  nop
0x18016e76d  lea     rcx, [rbp+var_20]
0x18016e771  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016e776  nop
0x18016e777  mov     rcx, [rbp+arg_18]; string
0x18016e77b  call    cs:__imp_WindowsDeleteString
0x18016e781  mov     [rbp+arg_18], r12
0x18016e785  mov     rcx, [rbp+var_40]; string
0x18016e789  call    cs:__imp_WindowsDeleteString
0x18016e78f  mov     [rbp+var_40], r12
0x18016e793  mov     rcx, [rbp+var_38]; string
0x18016e797  call    cs:__imp_WindowsDeleteString
0x18016e79d  mov     [rbp+var_38], r12
0x18016e7a1  mov     rcx, [rbp+var_30]; string
0x18016e7a5  call    cs:__imp_WindowsDeleteString
0x18016e7ab  mov     [rbp+var_30], r12
0x18016e7af  mov     rcx, [rbp+string]; string
0x18016e7b3  call    cs:__imp_WindowsDeleteString
0x18016e7b9  mov     [rbp+string], r12
0x18016e7bd  lea     rcx, [rbp+var_10]
0x18016e7c1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016e7c6  inc     esi
0x18016e7c8  jmp     loc_18016E572
0x18016e7cd  mov     dword ptr [rsp+70h+var_48], eax
0x18016e7d1  lea     rax, aClassregAddver; "classReg->AddVerb(id.Get(), verb.Get())"
0x18016e7d8  mov     edx, 0BE6h
0x18016e7dd  jmp     loc_18016E885
0x18016e7e2  mov     dword ptr [rsp+70h+var_48], eax
0x18016e7e6  lea     rax, aGetcommasepara_2; "GetCommaSeparatedValue(verbValues.Get()"...
0x18016e7ed  mov     edx, 0BE4h
0x18016e7f2  jmp     loc_18016E885
0x18016e7f7  mov     dword ptr [rsp+70h+var_48], eax
0x18016e7fb  lea     rax, aVerbvaluesAppe_0; "verbValues->Append(oleVerbFlag.Get())"
0x18016e802  mov     edx, 0BE2h
0x18016e807  jmp     short loc_18016E885
0x18016e809  mov     dword ptr [rsp+70h+var_48], eax
0x18016e80d  lea     rax, aParseandretrie_12; "ParseAndRetrieveAttribute( verbElement."...
0x18016e814  mov     edx, 0BE0h
0x18016e819  jmp     short loc_18016E885
0x18016e81b  mov     dword ptr [rsp+70h+var_48], eax
0x18016e81f  lea     rax, aVerbvaluesAppe; "verbValues->Append(appendMenuFlag.Get()"...
0x18016e826  mov     edx, 0BDBh
0x18016e82b  jmp     short loc_18016E885
0x18016e82d  mov     dword ptr [rsp+70h+var_48], eax
0x18016e831  lea     rax, aParseandretrie_41; "ParseAndRetrieveAttribute( verbElement."...
0x18016e838  mov     edx, 0BD9h
0x18016e83d  jmp     short loc_18016E885
0x18016e83f  mov     dword ptr [rsp+70h+var_48], eax
0x18016e843  lea     rax, aVerbvaluesAppe_1; "verbValues->Append(displayName.Get())"
0x18016e84a  mov     edx, 0BD4h
0x18016e84f  jmp     short loc_18016E885
0x18016e851  mov     dword ptr [rsp+70h+var_48], eax
0x18016e855  lea     rax, aParseandretrie_76; "ParseAndRetrieveLocalizableAttribute( v"...
0x18016e85c  mov     edx, 0BD2h
0x18016e861  jmp     short loc_18016E885
0x18016e863  mov     dword ptr [rsp+70h+var_48], eax
0x18016e867  lea     rax, aParseandretrie_80; "ParseAndRetrieveAttribute( verbElement."...
0x18016e86e  mov     edx, 0BCDh
0x18016e873  jmp     short loc_18016E885
0x18016e875  mov     dword ptr [rsp+70h+var_48], eax; char *
0x18016e879  lea     rax, aNodeAsVerbelem; "node.As(&verbElement)"
0x18016e880  mov     edx, 0BC7h; void *
0x18016e885  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016e88c  lea     r9, aOsintegrationD_507; "OSIntegration::DEH::PackagedComExtensio"...
0x18016e893  mov     [rsp+70h+var_50], rax; char *
0x18016e898  mov     rcx, [rbp+28h]; this
0x18016e89c  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016e8a1  nop
0x18016e8a2  lea     rcx, [rbp+var_18]
0x18016e8a6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016e8ab  jmp     short loc_18016E8DA
0x18016e8ad  mov     rcx, [rbp+28h]; this
0x18016e8b1  mov     dword ptr [rsp+70h+var_48], eax; char *
0x18016e8b5  lea     rax, aVectorHstringM; "Vector<HSTRING>::Make(&verbValues)"
0x18016e8bc  mov     [rsp+70h+var_50], rax; char *
0x18016e8c1  lea     r9, aOsintegrationD_507; "OSIntegration::DEH::PackagedComExtensio"...
0x18016e8c8  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016e8cf  mov     edx, 0BC4h; void *
0x18016e8d4  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016e8d9  nop
0x18016e8da  lea     rcx, [rbp+var_20]
0x18016e8de  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016e8e3  nop
0x18016e8e4  mov     rcx, [rbp+arg_18]; string
0x18016e8e8  call    cs:__imp_WindowsDeleteString
0x18016e8ee  mov     [rbp+arg_18], r12
0x18016e8f2  mov     rcx, [rbp+var_40]; string
0x18016e8f6  call    cs:__imp_WindowsDeleteString
0x18016e8fc  mov     [rbp+var_40], r12
0x18016e900  mov     rcx, [rbp+var_38]; string
0x18016e904  call    cs:__imp_WindowsDeleteString
0x18016e90a  mov     [rbp+var_38], r12
0x18016e90e  mov     rcx, [rbp+var_30]; string
0x18016e912  call    cs:__imp_WindowsDeleteString
0x18016e918  mov     [rbp+var_30], r12
0x18016e91c  mov     rcx, [rbp+string]; string
0x18016e920  call    cs:__imp_WindowsDeleteString
0x18016e926  mov     [rbp+string], r12
0x18016e92a  jmp     short loc_18016E959
0x18016e92c  mov     rcx, [rbp+28h]; this
0x18016e930  mov     dword ptr [rsp+70h+var_48], eax; char *
0x18016e934  lea     rax, aVerbsGetItemNo; "verbs->get_item(nodeIndex, &node)"
0x18016e93b  mov     [rsp+70h+var_50], rax; char *
0x18016e940  lea     r9, aOsintegrationD_507; "OSIntegration::DEH::PackagedComExtensio"...
0x18016e947  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016e94e  mov     edx, 0BBBh; void *
0x18016e953  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016e958  nop
0x18016e959  lea     rcx, [rbp+var_10]
0x18016e95d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016e962  jmp     short loc_18016E967
0x18016e964  mov     ebx, r12d
0x18016e967  lea     rcx, [rbp+var_8]
0x18016e96b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016e970  mov     eax, ebx
0x18016e972  lea     r11, [rsp+70h+var_s0]
0x18016e977  mov     rbx, [r11+30h]
0x18016e97b  mov     rsi, [r11+40h]
0x18016e97f  mov     rsp, r11
0x18016e982  pop     r15
0x18016e984  pop     r14
0x18016e986  pop     r12
0x18016e988  pop     rdi
0x18016e989  pop     rbp
0x18016e98a  retn
```
