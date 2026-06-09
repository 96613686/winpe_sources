# OSIntegration::DEH::PackagedComExtensionHandler::ParseExtensions(IXMLDOMElement * *,unsigned __int64)

- ea: `0x180168c58`
- end: `0x18016921e`
- name: `?ParseExtensions@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAPEAUIXMLDOMElement@@_K@Z`
- size: `1478`
- prototype: `__int64 __fastcall(OSIntegration::DEH::PackagedComExtensionHandler *__hidden this, struct IXMLDOMElement **, unsigned __int64)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800b9ec4`
- `0x180164880`

## callees

- `0x18000b3bc`
- `0x18000b9e0`
- `0x18003d928`
- `0x18003f7e0`
- `0x1800550f4`
- `0x18007d350`
- `0x180091b90`
- `0x180098ed0`
- `0x180099988`
- `0x18009aff4`
- `0x18009ba14`
- `0x18009be48`
- `0x18013ced4`
- `0x18013d6f8`
- `0x180166d20`
- `0x180168c58`
- `0x18016f4e0`
- `0x1802086d0`
- `0x180211010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180168ec1`
- `OLEAUT32!__imp_SysFreeString` at `0x18016902c`
- `OLEAUT32!__imp_SysFreeString` at `0x1801691bf`
- `OLEAUT32!__imp_SysFreeString` at `0x180168ec1`
- `OLEAUT32!__imp_SysFreeString` at `0x18016902c`
- `OLEAUT32!__imp_SysFreeString` at `0x1801691bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180168d6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180168e4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180168d6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180168e4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180168ce2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180168eb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016901e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801691b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180168ce2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180168eb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016901e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801691b1`

## string_xrefs

- `0x180168f50`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x180169003`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x180169082`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x180169186`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1801691e2`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x180168fec`: `APPX_E_INVALID_MANIFEST`
- `0x180168d75`: `windows.comServer`
- `0x180168e53`: `windows.comInterface`
- `0x180168d8d`: `ComServer`
- `0x180168e6b`: `ComInterface`
- `0x180168ef2`: `TryGetExtensionRuntimeBehavior(extensionElements[extensionIndex], extensionRuntimeBehavior)`
- `0x180168edd`: `TryGetExtensionBnoIsolation(extensionElements[extensionIndex], extensionBnoIsolation)`
- `0x180168e33`: `ParseComServer(extension.Get(), (compatMode == MsixAppCompatSupport::CompatMode::Classic), (scope == MsixAppCompatSupport::Scope::Machine), extensionTrustLevel, extensionRuntimeBehavior, extensionBnoIsolation)`
- `0x18016903d`: `ParseComInterface(extension.Get(), (compatMode == MsixAppCompatSupport::CompatMode::Classic), (scope == MsixAppCompatSupport::Scope::Machine))`
- `0x1801691cf`: `extensionElements[extensionIndex]->get_firstChild(&node)`
- `0x180168f49`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseExtensions`
- `0x180168ffc`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseExtensions`
- `0x18016907b`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseExtensions`
- `0x18016918d`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseExtensions`
- `0x1801691db`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseExtensions`
- `0x18016917a`: `node.As(&extension)`
- `0x180169168`: `ParseAndRetrieveAttribute(extensionElements[extensionIndex], Internal::PackagedComConstants::categoryAttribute, category.GetAddressOf())`
- `0x180169156`: `MsixAppCompatSupport::GetExtensionCompatMode(extensionElements[extensionIndex], &compatMode)`
- `0x180169144`: `MsixAppCompatSupport::GetExtensionScope(extensionElements[extensionIndex], &scope)`
- `0x180169132`: `extension->get_baseName(bstrNodeName.AddressOf())`
- `0x180168f07`: `TryGetExtensionTrustLevel(extensionElements[extensionIndex], extensionTrustLevel)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OSIntegration::DEH::PackagedComExtensionHandler::ParseExtensions(
        OSIntegration::Package **this,
        struct IXMLDOMElement **a2,
        unsigned __int64 a3)
{
  unsigned __int64 i; // rsi
  struct IXMLDOMElement *v7; // rdi
  HRESULT (__stdcall *get_firstChild)(IXMLDOMElement *, IXMLDOMNode **); // rbx
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  OSIntegration::DEH::PackagedComExtensionHandler *v12; // rcx
  int v13; // eax
  enum OSIntegration::DEH::MsixAppCompatSupport::CompatMode *v14; // r8
  int ExtensionCompatMode; // eax
  enum OSIntegration::DEH::MsixAppCompatSupport::Scope *v16; // r8
  int ExtensionScope; // eax
  int v18; // eax
  const wchar_t *StringRawBuffer; // rax
  __int64 v20; // rcx
  int ExtensionTrustLevel; // eax
  __int64 v22; // rcx
  int ExtensionRuntimeBehavior; // eax
  __int64 v24; // rcx
  int ExtensionBnoIsolation; // eax
  int v26; // eax
  const char *v27; // rax
  __int64 v28; // rdx
  const wchar_t *v29; // rax
  int v30; // eax
  OSIntegration::Package *v31; // rcx
  __int64 v32; // rbx
  unsigned int v33; // eax
  const unsigned __int16 *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rdx
  OSIntegration::Package *v37; // rcx
  __int64 v38; // rbx
  unsigned int v39; // eax
  const unsigned __int16 *v40; // rax
  __int64 v41; // rdx
  char *v43; // [rsp+28h] [rbp-58h]
  int v44; // [rsp+30h] [rbp-50h]
  HSTRING string; // [rsp+40h] [rbp-40h] BYREF
  struct IXMLDOMElement *v46; // [rsp+48h] [rbp-38h] BYREF
  wchar_t *String2; // [rsp+50h] [rbp-30h] BYREF
  __int64 v48; // [rsp+58h] [rbp-28h] BYREF
  __int64 v49; // [rsp+60h] [rbp-20h] BYREF
  __int64 v50; // [rsp+68h] [rbp-18h] BYREF
  __int64 v51; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+B8h] [rbp+38h]
  struct IXMLDOMElement v53; // [rsp+D0h] [rbp+50h] BYREF
  struct IXMLDOMElement v54; // [rsp+D8h] [rbp+58h] BYREF

  for ( i = 0; i < a3; ++i )
  {
    v48 = 0;
    v7 = a2[i];
    get_firstChild = v7->lpVtbl->get_firstChild;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    v9 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64 *))get_firstChild)(v7, &v48);
    v10 = v9;
    if ( v9 < 0 )
    {
      LODWORD(v43) = v9;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0xD1,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::ParseExtensions",
        "extensionElements[extensionIndex]->get_firstChild(&node)",
        v43,
        v44);
      goto LABEL_39;
    }
    String2 = 0;
    string = 0;
    v46 = 0;
    v11 = Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(&v48, &v46);
    v10 = v11;
    if ( v11 < 0 )
    {
      LODWORD(v43) = v11;
      v27 = "node.As(&extension)";
      v28 = 215;
LABEL_37:
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::ParseExtensions",
        v27,
        v43,
        v44);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      WindowsDeleteString(string);
      string = 0;
      SysFreeString(String2);
LABEL_39:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
      return v10;
    }
    WindowsDeleteString(string);
    string = 0;
    v13 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(
            v12,
            a2[i],
            L"Category",
            &string,
            0);
    v10 = v13;
    if ( v13 < 0 )
    {
      LODWORD(v43) = v13;
      v27 = "ParseAndRetrieveAttribute(extensionElements[extensionIndex], Internal::PackagedComConstants::categoryAttribu"
            "te, category.GetAddressOf())";
      v28 = 219;
      goto LABEL_37;
    }
    LODWORD(v54.lpVtbl) = 0;
    ExtensionCompatMode = OSIntegration::DEH::MsixAppCompatSupport::GetExtensionCompatMode(
                            (OSIntegration::DEH::MsixAppCompatSupport *)a2[i],
                            &v54,
                            v14);
    v10 = ExtensionCompatMode;
    if ( ExtensionCompatMode < 0 )
    {
      LODWORD(v43) = ExtensionCompatMode;
      v27 = "MsixAppCompatSupport::GetExtensionCompatMode(extensionElements[extensionIndex], &compatMode)";
      v28 = 227;
      goto LABEL_37;
    }
    LODWORD(v53.lpVtbl) = 0;
    ExtensionScope = OSIntegration::DEH::MsixAppCompatSupport::GetExtensionScope(
                       (OSIntegration::DEH::MsixAppCompatSupport *)a2[i],
                       &v53,
                       v16);
    v10 = ExtensionScope;
    if ( ExtensionScope < 0 )
    {
      LODWORD(v43) = ExtensionScope;
      v27 = "MsixAppCompatSupport::GetExtensionScope(extensionElements[extensionIndex], &scope)";
      v28 = 230;
      goto LABEL_37;
    }
    v18 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, wchar_t **))v46->lpVtbl->get_baseName)(v46, &String2);
    v10 = v18;
    if ( v18 < 0 )
    {
      LODWORD(v43) = v18;
      v27 = "extension->get_baseName(bstrNodeName.AddressOf())";
      v28 = 232;
      goto LABEL_37;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( !wcscmp_0(L"windows.comServer", StringRawBuffer) )
    {
      if ( wcscmp_0(L"ComServer", String2) )
      {
        v53.lpVtbl = 0;
        OSIntegration::Package::GetXmlLineInformation(
          this[5],
          (const struct IXMLDOMNode *)v46,
          0,
          (struct APPX_XML_LINE_INFORMATION *)&v53);
        LODWORD(v43) = -2146958844;
        wil::details::in1diag5::_Log_Hr(
          retaddr,
          (void *)0x10C,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::ParseExtensions",
          "((HRESULT)0x80080204L)",
          v43,
          v44);
        if ( (byte_1802E21CA & 4) != 0 )
        {
          v31 = this[5];
          v32 = *((_QWORD *)v31 + 28);
          v33 = (unsigned int)RemovePIIfromFilePath(*((const unsigned __int16 **)v31 + 34));
          McTemplateU0zqqdz_EventWriteTransfer(
            HIDWORD(v53.lpVtbl),
            (unsigned int)PackagedComInvalidComServerCategory,
            v33,
            v53.lpVtbl,
            SBYTE4(v53.lpVtbl),
            4,
            v32);
        }
        v34 = RemovePIIfromFilePath(*((const unsigned __int16 **)this[5] + 34));
        v44 = -2146958844;
        details::appxLog<unsigned short const *,unsigned int,unsigned int,long,unsigned short *>(
          2148008452LL,
          v35,
          PackagedComInvalidComServerCategory,
          v34);
        v36 = 270;
        goto LABEL_26;
      }
      BYTE4(v51) = 0;
      ExtensionTrustLevel = OSIntegration::DEH::PackagedComExtensionHandler::TryGetExtensionTrustLevel(v20, a2[i], &v51);
      v10 = ExtensionTrustLevel;
      if ( ExtensionTrustLevel < 0 )
      {
        LODWORD(v43) = ExtensionTrustLevel;
        v27 = "TryGetExtensionTrustLevel(extensionElements[extensionIndex], extensionTrustLevel)";
        v28 = 239;
        goto LABEL_37;
      }
      BYTE4(v50) = 0;
      ExtensionRuntimeBehavior = OSIntegration::DEH::PackagedComExtensionHandler::TryGetExtensionRuntimeBehavior(
                                   v22,
                                   a2[i],
                                   &v50);
      v10 = ExtensionRuntimeBehavior;
      if ( ExtensionRuntimeBehavior < 0 )
      {
        LODWORD(v43) = ExtensionRuntimeBehavior;
        v27 = "TryGetExtensionRuntimeBehavior(extensionElements[extensionIndex], extensionRuntimeBehavior)";
        v28 = 242;
        goto LABEL_37;
      }
      BYTE4(v49) = 0;
      ExtensionBnoIsolation = OSIntegration::DEH::PackagedComExtensionHandler::TryGetExtensionBnoIsolation(
                                v24,
                                a2[i],
                                &v49);
      v10 = ExtensionBnoIsolation;
      if ( ExtensionBnoIsolation < 0 )
      {
        LODWORD(v43) = ExtensionBnoIsolation;
        v27 = "TryGetExtensionBnoIsolation(extensionElements[extensionIndex], extensionBnoIsolation)";
        v28 = 245;
        goto LABEL_37;
      }
      v26 = OSIntegration::DEH::PackagedComExtensionHandler::ParseComServer(
              (OSIntegration::DEH::PackagedComExtensionHandler *)this,
              (struct IXMLDOMNode *)v46,
              v51,
              v50,
              v49);
      v10 = v26;
      if ( v26 < 0 )
      {
        LODWORD(v43) = v26;
        v27 = "ParseComServer(extension.Get(), (compatMode == MsixAppCompatSupport::CompatMode::Classic), (scope == MsixA"
              "ppCompatSupport::Scope::Machine), extensionTrustLevel, extensionRuntimeBehavior, extensionBnoIsolation)";
        v28 = 250;
        goto LABEL_37;
      }
    }
    else
    {
      v29 = WindowsGetStringRawBuffer(string, 0);
      if ( wcscmp_0(L"windows.comInterface", v29) )
      {
        v36 = 306;
        goto LABEL_26;
      }
      if ( wcscmp_0(L"ComInterface", String2) )
      {
        v54.lpVtbl = 0;
        OSIntegration::Package::GetXmlLineInformation(
          this[5],
          (const struct IXMLDOMNode *)v46,
          0,
          (struct APPX_XML_LINE_INFORMATION *)&v54);
        LODWORD(v43) = -2146958844;
        wil::details::in1diag5::_Log_Hr(
          retaddr,
          (void *)0x129,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::ParseExtensions",
          "((HRESULT)0x80080204L)",
          v43,
          v44);
        if ( (byte_1802E21CA & 4) != 0 )
        {
          v37 = this[5];
          v38 = *((_QWORD *)v37 + 28);
          v39 = (unsigned int)RemovePIIfromFilePath(*((const unsigned __int16 **)v37 + 34));
          McTemplateU0zqqdz_EventWriteTransfer(
            HIDWORD(v54.lpVtbl),
            (unsigned int)PackagedComInvalidComInterfaceCategory,
            v39,
            v54.lpVtbl,
            SBYTE4(v54.lpVtbl),
            4,
            v38);
        }
        v40 = RemovePIIfromFilePath(*((const unsigned __int16 **)this[5] + 34));
        v44 = -2146958844;
        details::appxLog<unsigned short const *,unsigned int,unsigned int,long,unsigned short *>(
          2148008452LL,
          v41,
          PackagedComInvalidComInterfaceCategory,
          v40);
        v36 = 299;
LABEL_26:
        LODWORD(v43) = -2146958844;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)v36,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::ParseExtensions",
          "APPX_E_INVALID_MANIFEST",
          v43,
          v44);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
        WindowsDeleteString(string);
        string = 0;
        SysFreeString(String2);
        v10 = -2146958844;
        goto LABEL_39;
      }
      v30 = OSIntegration::DEH::PackagedComExtensionHandler::ParseComInterface(
              (OSIntegration::DEH::PackagedComExtensionHandler *)this,
              v46,
              LODWORD(v54.lpVtbl) == 1,
              LODWORD(v53.lpVtbl) == 1);
      v10 = v30;
      if ( v30 < 0 )
      {
        LODWORD(v43) = v30;
        v27 = "ParseComInterface(extension.Get(), (compatMode == MsixAppCompatSupport::CompatMode::Classic), (scope == Ms"
              "ixAppCompatSupport::Scope::Machine))";
        v28 = 279;
        goto LABEL_37;
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    WindowsDeleteString(string);
    string = 0;
    SysFreeString(String2);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
  }
  return 0;
}

```

## disassembly

```asm
0x180168c58  mov     [rsp-38h+arg_0], rbx
0x180168c5d  push    rbp
0x180168c5e  push    rsi
0x180168c5f  push    rdi
0x180168c60  push    r12
0x180168c62  push    r13
0x180168c64  push    r14
0x180168c66  push    r15
0x180168c68  mov     rbp, rsp
0x180168c6b  sub     rsp, 80h
0x180168c72  mov     r12, r8
0x180168c75  mov     r14, rdx
0x180168c78  mov     r15, rcx
0x180168c7b  xor     r13d, r13d
0x180168c7e  mov     esi, r13d
0x180168c81  cmp     rsi, r12
0x180168c84  jnb     loc_180169201
0x180168c8a  mov     [rbp+var_28], r13
0x180168c8e  mov     rdi, [r14+rsi*8]
0x180168c92  mov     rax, [rdi]
0x180168c95  mov     rbx, [rax+68h]
0x180168c99  lea     rcx, [rbp+var_28]
0x180168c9d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180168ca2  lea     rdx, [rbp+var_28]
0x180168ca6  mov     rcx, rdi
0x180168ca9  mov     rax, rbx
0x180168cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180168cb1  mov     ebx, eax
0x180168cb3  test    eax, eax
0x180168cb5  js      loc_1801691C7
0x180168cbb  mov     [rbp+String2], r13
0x180168cbf  mov     [rbp+string], r13
0x180168cc3  mov     [rbp+var_38], r13
0x180168cc7  lea     rdx, [rbp+var_38]
0x180168ccb  lea     rcx, [rbp+var_28]
0x180168ccf  call    ??$As@UIXMLDOMElement@@@?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIXMLDOMElement@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IXMLDOMElement>>)
0x180168cd4  mov     ebx, eax
0x180168cd6  test    eax, eax
0x180168cd8  js      loc_180169176
0x180168cde  mov     rcx, [rbp+string]; string
0x180168ce2  call    cs:__imp_WindowsDeleteString
0x180168ce8  mov     [rbp+string], r13
0x180168cec  mov     [rsp+80h+var_60], r13; bool *
0x180168cf1  lea     r9, [rbp+string]; HSTRING *
0x180168cf5  lea     r8, aCategory; "Category"
0x180168cfc  mov     rdx, [r14+rsi*8]; struct IXMLDOMElement *
0x180168d00  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x180168d05  mov     ebx, eax
0x180168d07  test    eax, eax
0x180168d09  js      loc_180169164
0x180168d0f  mov     dword ptr [rbp+arg_18.lpVtbl], r13d
0x180168d13  lea     rdx, [rbp+arg_18]; struct IXMLDOMElement *
0x180168d17  mov     rcx, [r14+rsi*8]; this
0x180168d1b  call    ?GetExtensionCompatMode@MsixAppCompatSupport@DEH@OSIntegration@@YAJPEAUIXMLDOMElement@@PEAW4CompatMode@123@@Z; OSIntegration::DEH::MsixAppCompatSupport::GetExtensionCompatMode(IXMLDOMElement *,OSIntegration::DEH::MsixAppCompatSupport::CompatMode *)
0x180168d20  mov     ebx, eax
0x180168d22  test    eax, eax
0x180168d24  js      loc_180169152
0x180168d2a  mov     dword ptr [rbp+arg_10.lpVtbl], r13d
0x180168d2e  lea     rdx, [rbp+arg_10]; struct IXMLDOMElement *
0x180168d32  mov     rcx, [r14+rsi*8]; this
0x180168d36  call    ?GetExtensionScope@MsixAppCompatSupport@DEH@OSIntegration@@YAJPEAUIXMLDOMElement@@PEAW4Scope@123@@Z; OSIntegration::DEH::MsixAppCompatSupport::GetExtensionScope(IXMLDOMElement *,OSIntegration::DEH::MsixAppCompatSupport::Scope *)
0x180168d3b  mov     ebx, eax
0x180168d3d  test    eax, eax
0x180168d3f  js      loc_180169140
0x180168d45  mov     rcx, [rbp+var_38]
0x180168d49  mov     rax, [rcx]
0x180168d4c  lea     rdx, [rbp+String2]
0x180168d50  mov     rax, [rax+148h]
0x180168d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180168d5c  mov     ebx, eax
0x180168d5e  test    eax, eax
0x180168d60  js      loc_18016912E
0x180168d66  xor     edx, edx; length
0x180168d68  mov     rcx, [rbp+string]; string
0x180168d6c  call    cs:__imp_WindowsGetStringRawBuffer
0x180168d72  mov     rdx, rax; String2
0x180168d75  lea     rcx, aWindowsComserv; "windows.comServer"
0x180168d7c  call    wcscmp_0
0x180168d81  test    eax, eax
0x180168d83  jnz     loc_180168E44
0x180168d89  mov     rdx, [rbp+String2]; String2
0x180168d8d  lea     rcx, aComserver; "ComServer"
0x180168d94  call    wcscmp_0
0x180168d99  test    eax, eax
0x180168d9b  jnz     loc_180168F18
0x180168da1  mov     byte ptr [rbp+var_10+4], r13b
0x180168da5  lea     r8, [rbp+var_10]
0x180168da9  mov     rdx, [r14+rsi*8]
0x180168dad  call    ?TryGetExtensionTrustLevel@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@AEAV?$optional@W4TrustLevel@AppModel@@@std@@@Z; OSIntegration::DEH::PackagedComExtensionHandler::TryGetExtensionTrustLevel(IXMLDOMElement *,std::optional<AppModel::TrustLevel> &)
0x180168db2  mov     ebx, eax
0x180168db4  test    eax, eax
0x180168db6  js      loc_180168F03
0x180168dbc  mov     byte ptr [rbp+var_18+4], r13b
0x180168dc0  lea     r8, [rbp+var_18]
0x180168dc4  mov     rdx, [r14+rsi*8]
0x180168dc8  call    ?TryGetExtensionRuntimeBehavior@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@AEAV?$optional@W4RuntimeBehavior@AppModel@@@std@@@Z; OSIntegration::DEH::PackagedComExtensionHandler::TryGetExtensionRuntimeBehavior(IXMLDOMElement *,std::optional<AppModel::RuntimeBehavior> &)
0x180168dcd  mov     ebx, eax
0x180168dcf  test    eax, eax
0x180168dd1  js      loc_180168EEE
0x180168dd7  mov     byte ptr [rbp+var_20+4], r13b
0x180168ddb  lea     r8, [rbp+var_20]
0x180168ddf  mov     rdx, [r14+rsi*8]
0x180168de3  call    ?TryGetExtensionBnoIsolation@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@AEAV?$optional@W4BnoIsolation@AppModel@@@std@@@Z; OSIntegration::DEH::PackagedComExtensionHandler::TryGetExtensionBnoIsolation(IXMLDOMElement *,std::optional<AppModel::BnoIsolation> &)
0x180168de8  mov     ebx, eax
0x180168dea  test    eax, eax
0x180168dec  js      loc_180168ED9
0x180168df2  cmp     dword ptr [rbp+arg_10.lpVtbl], 1
0x180168df6  setz    r9b
0x180168dfa  cmp     dword ptr [rbp+arg_18.lpVtbl], 1
0x180168dfe  setz    r8b
0x180168e02  mov     rax, [rbp+var_20]
0x180168e06  mov     qword ptr [rsp+80h+var_50], rax
0x180168e0b  mov     rax, [rbp+var_18]
0x180168e0f  mov     [rsp+80h+var_58], rax
0x180168e14  mov     rax, [rbp+var_10]
0x180168e18  mov     [rsp+80h+var_60], rax
0x180168e1d  mov     rdx, [rbp+var_38]
0x180168e21  mov     rcx, r15
0x180168e24  call    ?ParseComServer@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@_N1V?$optional@W4TrustLevel@AppModel@@@std@@V?$optional@W4RuntimeBehavior@AppModel@@@6@V?$optional@W4BnoIsolation@AppModel@@@6@@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseComServer(IXMLDOMElement *,bool,bool,std::optional<AppModel::TrustLevel>,std::optional<AppModel::RuntimeBehavior>,std::optional<AppModel::BnoIsolation>)
0x180168e29  mov     ebx, eax
0x180168e2b  test    eax, eax
0x180168e2d  jns     short loc_180168EA5
0x180168e2f  mov     dword ptr [rsp+80h+var_58], eax
0x180168e33  lea     rax, aParsecomserver; "ParseComServer(extension.Get(), (compat"...
0x180168e3a  mov     edx, 0FAh
0x180168e3f  jmp     loc_180169186
0x180168e44  xor     edx, edx; length
0x180168e46  mov     rcx, [rbp+string]; string
0x180168e4a  call    cs:__imp_WindowsGetStringRawBuffer
0x180168e50  mov     rdx, rax; String2
0x180168e53  lea     rcx, aWindowsCominte; "windows.comInterface"
0x180168e5a  call    wcscmp_0
0x180168e5f  test    eax, eax
0x180168e61  jnz     loc_18016911F
0x180168e67  mov     rdx, [rbp+String2]; String2
0x180168e6b  lea     rcx, aCominterface; "ComInterface"
0x180168e72  call    wcscmp_0
0x180168e77  mov     rdx, [rbp+var_38]; struct IXMLDOMNode *
0x180168e7b  test    eax, eax
0x180168e7d  jnz     loc_18016904E
0x180168e83  cmp     dword ptr [rbp+arg_10.lpVtbl], 1
0x180168e87  setz    r9b; bool
0x180168e8b  cmp     dword ptr [rbp+arg_18.lpVtbl], 1
0x180168e8f  setz    r8b; bool
0x180168e93  mov     rcx, r15; this
0x180168e96  call    ?ParseComInterface@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@_N1@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseComInterface(IXMLDOMElement *,bool,bool)
0x180168e9b  mov     ebx, eax
0x180168e9d  test    eax, eax
0x180168e9f  js      loc_180169039
0x180168ea5  lea     rcx, [rbp+var_38]
0x180168ea9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180168eae  nop
0x180168eaf  mov     rcx, [rbp+string]; string
0x180168eb3  call    cs:__imp_WindowsDeleteString
0x180168eb9  mov     [rbp+string], r13
0x180168ebd  mov     rcx, [rbp+String2]; bstrString
0x180168ec1  call    cs:__imp_SysFreeString
0x180168ec7  nop
0x180168ec8  lea     rcx, [rbp+var_28]
0x180168ecc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180168ed1  inc     rsi
0x180168ed4  jmp     loc_180168C81
0x180168ed9  mov     dword ptr [rsp+80h+var_58], eax
0x180168edd  lea     rax, aTrygetextensio_0; "TryGetExtensionBnoIsolation(extensionEl"...
0x180168ee4  mov     edx, 0F5h
0x180168ee9  jmp     loc_180169186
0x180168eee  mov     dword ptr [rsp+80h+var_58], eax
0x180168ef2  lea     rax, aTrygetextensio_1; "TryGetExtensionRuntimeBehavior(extensio"...
0x180168ef9  mov     edx, 0F2h
0x180168efe  jmp     loc_180169186
0x180168f03  mov     dword ptr [rsp+80h+var_58], eax
0x180168f07  lea     rax, aTrygetextensio; "TryGetExtensionTrustLevel(extensionElem"...
0x180168f0e  mov     edx, 0EFh
0x180168f13  jmp     loc_180169186
0x180168f18  mov     [rbp+arg_10.lpVtbl], r13
0x180168f1c  lea     r9, [rbp+arg_10]; struct APPX_XML_LINE_INFORMATION *
0x180168f20  xor     r8d, r8d; unsigned __int16 *
0x180168f23  mov     rdx, [rbp+var_38]; struct IXMLDOMNode *
0x180168f27  mov     rcx, [r15+28h]; this
0x180168f2b  call    ?GetXmlLineInformation@Package@OSIntegration@@QEBAJPEBUIXMLDOMNode@@PEBGPEAUAPPX_XML_LINE_INFORMATION@@@Z; OSIntegration::Package::GetXmlLineInformation(IXMLDOMNode const *,ushort const *,APPX_XML_LINE_INFORMATION *)
0x180168f30  mov     rcx, [rbp+38h]; this
0x180168f34  mov     edi, 80080204h
0x180168f39  mov     dword ptr [rsp+80h+var_58], edi; char *
0x180168f3d  lea     rax, aHresult0x80080; "((HRESULT)0x80080204L)"
0x180168f44  mov     [rsp+80h+var_60], rax; char *
0x180168f49  lea     r9, aOsintegrationD_364; "OSIntegration::DEH::PackagedComExtensio"...
0x180168f50  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180168f57  mov     edx, 10Ch; void *
0x180168f5c  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x180168f61  test    cs:byte_1802E21CA, 4
0x180168f68  jz      short loc_180168FA4
0x180168f6a  mov     rcx, [r15+28h]
0x180168f6e  mov     rbx, [rcx+0E0h]
0x180168f75  mov     rcx, [rcx+110h]; unsigned __int16 *
0x180168f7c  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x180168f81  mov     qword ptr [rsp+80h+var_50], rbx
0x180168f86  mov     dword ptr [rsp+80h+var_58], edi
0x180168f8a  mov     ecx, dword ptr [rbp+arg_10.lpVtbl+4]
0x180168f8d  mov     dword ptr [rsp+80h+var_60], ecx
0x180168f91  mov     r9d, dword ptr [rbp+arg_10.lpVtbl]
0x180168f95  mov     r8, rax
0x180168f98  lea     rdx, PackagedComInvalidComServerCategory
0x180168f9f  call    McTemplateU0zqqdz_EventWriteTransfer
0x180168fa4  mov     rcx, [r15+28h]
0x180168fa8  mov     rbx, [rcx+0E0h]
0x180168faf  mov     rcx, [rcx+110h]; unsigned __int16 *
0x180168fb6  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x180168fbb  mov     [rsp+80h+var_48], rbx
0x180168fc0  mov     [rsp+80h+var_50], edi; int
0x180168fc4  mov     ecx, dword ptr [rbp+arg_10.lpVtbl+4]
0x180168fc7  mov     dword ptr [rsp+80h+var_58], ecx
0x180168fcb  mov     ecx, dword ptr [rbp+arg_10.lpVtbl]
0x180168fce  mov     dword ptr [rsp+80h+var_60], ecx
0x180168fd2  mov     r9, rax
0x180168fd5  lea     r8, PackagedComInvalidComServerCategory
0x180168fdc  mov     ecx, edi
0x180168fde  call    ??$appxLog@PEBGIIJPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEBGIIJPEAG@Z; details::appxLog<ushort const *,uint,uint,long,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort const *,uint,uint,long,ushort *)
0x180168fe3  mov     edx, 10Eh; void *
0x180168fe8  mov     dword ptr [rsp+80h+var_58], edi; char *
0x180168fec  lea     rax, aAppxEInvalidMa; "APPX_E_INVALID_MANIFEST"
0x180168ff3  mov     rcx, [rbp+38h]; this
0x180168ff7  mov     [rsp+80h+var_60], rax; char *
0x180168ffc  lea     r9, aOsintegrationD_364; "OSIntegration::DEH::PackagedComExtensio"...
0x180169003  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016900a  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016900f  nop
0x180169010  lea     rcx, [rbp+var_38]
0x180169014  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180169019  nop
0x18016901a  mov     rcx, [rbp+string]; string
0x18016901e  call    cs:__imp_WindowsDeleteString
0x180169024  mov     [rbp+string], r13
0x180169028  mov     rcx, [rbp+String2]; bstrString
0x18016902c  call    cs:__imp_SysFreeString
0x180169032  mov     ebx, edi
0x180169034  jmp     loc_1801691F4
0x180169039  mov     dword ptr [rsp+80h+var_58], eax
0x18016903d  lea     rax, aParsecominterf; "ParseComInterface(extension.Get(), (com"...
0x180169044  mov     edx, 117h
0x180169049  jmp     loc_180169186
0x18016904e  mov     [rbp+arg_18.lpVtbl], r13
0x180169052  lea     r9, [rbp+arg_18]; struct APPX_XML_LINE_INFORMATION *
0x180169056  xor     r8d, r8d; unsigned __int16 *
0x180169059  mov     rcx, [r15+28h]; this
0x18016905d  call    ?GetXmlLineInformation@Package@OSIntegration@@QEBAJPEBUIXMLDOMNode@@PEBGPEAUAPPX_XML_LINE_INFORMATION@@@Z; OSIntegration::Package::GetXmlLineInformation(IXMLDOMNode const *,ushort const *,APPX_XML_LINE_INFORMATION *)
0x180169062  mov     rcx, [rbp+38h]; this
0x180169066  mov     edi, 80080204h
0x18016906b  mov     dword ptr [rsp+80h+var_58], edi; char *
0x18016906f  lea     rax, aHresult0x80080; "((HRESULT)0x80080204L)"
0x180169076  mov     [rsp+80h+var_60], rax; char *
0x18016907b  lea     r9, aOsintegrationD_364; "OSIntegration::DEH::PackagedComExtensio"...
0x180169082  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180169089  mov     edx, 129h; void *
0x18016908e  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x180169093  test    cs:byte_1802E21CA, 4
0x18016909a  jz      short loc_1801690D6
0x18016909c  mov     rcx, [r15+28h]
0x1801690a0  mov     rbx, [rcx+0E0h]
0x1801690a7  mov     rcx, [rcx+110h]; unsigned __int16 *
0x1801690ae  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x1801690b3  mov     qword ptr [rsp+80h+var_50], rbx
0x1801690b8  mov     dword ptr [rsp+80h+var_58], edi
0x1801690bc  mov     ecx, dword ptr [rbp+arg_18.lpVtbl+4]
0x1801690bf  mov     dword ptr [rsp+80h+var_60], ecx
0x1801690c3  mov     r9d, dword ptr [rbp+arg_18.lpVtbl]
0x1801690c7  mov     r8, rax
0x1801690ca  lea     rdx, PackagedComInvalidComInterfaceCategory
0x1801690d1  call    McTemplateU0zqqdz_EventWriteTransfer
0x1801690d6  mov     rcx, [r15+28h]
0x1801690da  mov     rbx, [rcx+0E0h]
0x1801690e1  mov     rcx, [rcx+110h]; unsigned __int16 *
0x1801690e8  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x1801690ed  mov     [rsp+80h+var_48], rbx
0x1801690f2  mov     [rsp+80h+var_50], edi
0x1801690f6  mov     ecx, dword ptr [rbp+arg_18.lpVtbl+4]
0x1801690f9  mov     dword ptr [rsp+80h+var_58], ecx
0x1801690fd  mov     ecx, dword ptr [rbp+arg_18.lpVtbl]
0x180169100  mov     dword ptr [rsp+80h+var_60], ecx
0x180169104  mov     r9, rax
0x180169107  lea     r8, PackagedComInvalidComInterfaceCategory
0x18016910e  mov     ecx, edi
0x180169110  call    ??$appxLog@PEBGIIJPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEBGIIJPEAG@Z; details::appxLog<ushort const *,uint,uint,long,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort const *,uint,uint,long,ushort *)
0x180169115  mov     edx, 12Bh
0x18016911a  jmp     loc_180168FE8
0x18016911f  mov     edi, 80080204h
0x180169124  mov     edx, 132h
0x180169129  jmp     loc_180168FE8
0x18016912e  mov     dword ptr [rsp+80h+var_58], eax
0x180169132  lea     rax, aExtensionGetBa; "extension->get_baseName(bstrNodeName.Ad"...
0x180169139  mov     edx, 0E8h
0x18016913e  jmp     short loc_180169186
0x180169140  mov     dword ptr [rsp+80h+var_58], eax
0x180169144  lea     rax, aMsixappcompats_1; "MsixAppCompatSupport::GetExtensionScope"...
0x18016914b  mov     edx, 0E6h
0x180169150  jmp     short loc_180169186
0x180169152  mov     dword ptr [rsp+80h+var_58], eax
0x180169156  lea     rax, aMsixappcompats; "MsixAppCompatSupport::GetExtensionCompa"...
0x18016915d  mov     edx, 0E3h
0x180169162  jmp     short loc_180169186
0x180169164  mov     dword ptr [rsp+80h+var_58], eax
  ... truncated ...
```
