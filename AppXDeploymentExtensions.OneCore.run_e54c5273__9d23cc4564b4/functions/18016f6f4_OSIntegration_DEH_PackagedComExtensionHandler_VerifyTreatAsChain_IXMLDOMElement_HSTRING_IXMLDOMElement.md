# OSIntegration::DEH::PackagedComExtensionHandler::VerifyTreatAsChain(IXMLDOMElement *,HSTRING__ * *,IXMLDOMElement * *)

- ea: `0x18016f6f4`
- end: `0x18016faec`
- name: `?VerifyTreatAsChain@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEAPEAUHSTRING__@@PEAPEAU4@@Z`
- size: `1016`
- prototype: `int(OSIntegration::DEH::PackagedComExtensionHandler *__hidden this, struct IXMLDOMElement *, HSTRING *, struct IXMLDOMElement **)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801650d8`
- `0x18016cf84`

## callees

- `0x18000b3bc`
- `0x18000b9e0`
- `0x180036090`
- `0x1800550f4`
- `0x180077608`
- `0x18007d350`
- `0x18008d84c`
- `0x180098ed0`
- `0x18009aff4`
- `0x18009cfac`
- `0x18009d0b4`
- `0x1800bc470`
- `0x18013ced4`
- `0x18013d6f8`
- `0x18016f6f4`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18016f9f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18016f9f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016f781`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016f818`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016f781`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016f818`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016f742`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016f883`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016fab5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016f742`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016f883`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016fab5`

## string_xrefs

- `0x18016f8c4`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016f932`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016fa1f`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016fa6f`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016fa9f`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016f9c9`: `APPX_E_INVALID_MANIFEST`
- `0x18016fa0c`: `WindowsDuplicateString(currentTreatAsValue.Get(), terminalClsid)`
- `0x18016f9de`: `treatAsList->Insert(currentTreatAsValue.Get(), nullptr, &replaced)`
- `0x18016fa8c`: `ParseAndRetrieveAttribute( currentTreatAsClassElement.get(), Internal::PackagedComConstants::treatAsAttribute, currentTreatAsValue.GetAddressOf())`
- `0x18016f8bd`: `OSIntegration::DEH::PackagedComExtensionHandler::VerifyTreatAsChain`
- `0x18016f92b`: `OSIntegration::DEH::PackagedComExtensionHandler::VerifyTreatAsChain`
- `0x18016fa18`: `OSIntegration::DEH::PackagedComExtensionHandler::VerifyTreatAsChain`
- `0x18016fa68`: `OSIntegration::DEH::PackagedComExtensionHandler::VerifyTreatAsChain`
- `0x18016fa98`: `OSIntegration::DEH::PackagedComExtensionHandler::VerifyTreatAsChain`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall OSIntegration::DEH::PackagedComExtensionHandler::VerifyTreatAsChain(
        OSIntegration::Package **this,
        struct IXMLDOMElement *a2,
        HSTRING *a3,
        struct IXMLDOMElement **a4)
{
  struct IXMLDOMElement *v8; // rbx
  OSIntegration::DEH::PackagedComExtensionHandler *v9; // rcx
  int v10; // eax
  unsigned int v11; // edi
  const unsigned __int16 *StringRawBuffer; // rax
  OSIntegration::DEH::PackagedComExtensionHandler *v13; // rcx
  int ReferencedClassElementById; // eax
  struct IXMLDOMElement *v15; // r15
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  int v19; // eax
  int v20; // eax
  const unsigned __int16 *v21; // rax
  OSIntegration::DEH::PackagedComExtensionHandler *v22; // rcx
  int TreatAsClassElementById; // eax
  struct IXMLDOMElement *v24; // rdi
  const char *v25; // rax
  __int64 v26; // rdx
  const char *v27; // rax
  __int64 v28; // rdx
  OSIntegration::Package *v29; // rcx
  __int64 v30; // rbx
  unsigned int v31; // eax
  const unsigned __int16 *v32; // rax
  __int64 v33; // rdx
  HRESULT v34; // eax
  char *v36; // [rsp+28h] [rbp-38h]
  int v37; // [rsp+30h] [rbp-30h]
  struct IXMLDOMElement *v38; // [rsp+40h] [rbp-20h] BYREF
  __int64 v39; // [rsp+48h] [rbp-18h] BYREF
  struct IXMLDOMElement *v40; // [rsp+50h] [rbp-10h] BYREF
  struct IXMLDOMElement *v41; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+98h] [rbp+38h]
  char v43; // [rsp+B0h] [rbp+50h] BYREF
  HSTRING string; // [rsp+B8h] [rbp+58h] BYREF

  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v39 = 0;
  wil::com_ptr_t<IXMLDOMElement,wil::err_returncode_policy>::com_ptr_t<IXMLDOMElement,wil::err_returncode_policy>(&v41);
  v8 = v41;
  while ( 1 )
  {
    string = 0;
    WindowsDeleteString(0);
    string = 0;
    v10 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(
            v9,
            v8,
            (struct IXMLDOMElement *)L"TreatAs",
            &string,
            0);
    v11 = v10;
    if ( v10 < 0 )
      break;
    v38 = 0;
    wil::com_ptr_t<IXMLDOMElement,wil::err_returncode_policy>::reset(&v38);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    ReferencedClassElementById = OSIntegration::DEH::PackagedComExtensionHandler::FindReferencedClassElementById(
                                   v13,
                                   a2,
                                   StringRawBuffer,
                                   &v38);
    v11 = ReferencedClassElementById;
    if ( ReferencedClassElementById < 0 )
    {
      LODWORD(v36) = ReferencedClassElementById;
      v25 = "FindReferencedClassElementById(treatAsClassElement, currentTreatAsValue.GetRawBuffer(nullptr), &nextClassElement)";
      v26 = 4157;
      goto LABEL_35;
    }
    v15 = v38;
    if ( v38 )
    {
      if ( a3 && (v34 = WindowsDuplicateString(string, a3), v11 = v34, v34 < 0) )
      {
        LODWORD(v36) = v34;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x1043,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::VerifyTreatAsChain",
          "WindowsDuplicateString(currentTreatAsValue.Get(), terminalClsid)",
          v36,
          v37);
      }
      else
      {
        if ( a4 )
        {
          v38 = 0;
          *a4 = v15;
        }
        v11 = 0;
      }
      goto LABEL_22;
    }
    v16 = v39;
    if ( !v39 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
      v19 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Make(
              v18,
              v17,
              &v39);
      v11 = v19;
      if ( v19 < 0 )
      {
        LODWORD(v36) = v19;
        v25 = "(HashMap<HSTRING, IInspectable*>::Make(&treatAsList))";
        v26 = 4178;
LABEL_35:
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)v26,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::VerifyTreatAsChain",
          v25,
          v36,
          v37);
        goto LABEL_22;
      }
      v16 = v39;
    }
    v43 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, HSTRING, _QWORD, char *))(*(_QWORD *)v16 + 80LL))(v16, string, 0, &v43);
    v11 = v20;
    if ( v20 < 0 )
    {
      LODWORD(v36) = v20;
      v25 = "treatAsList->Insert(currentTreatAsValue.Get(), nullptr, &replaced)";
      v26 = 4182;
      goto LABEL_35;
    }
    v40 = 0;
    if ( v43 )
    {
      OSIntegration::Package::GetXmlLineInformation(
        this[5],
        (const struct IXMLDOMNode *)a2,
        0,
        (struct APPX_XML_LINE_INFORMATION *)&v40);
      v11 = -2146958844;
      LODWORD(v36) = -2146958844;
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0x1064,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::VerifyTreatAsChain",
        "((HRESULT)0x80080204L)",
        v36,
        v37);
      if ( (byte_1802E21CA & 4) != 0 )
      {
        v29 = this[5];
        v30 = *((_QWORD *)v29 + 28);
        v31 = (unsigned int)RemovePIIfromFilePath(*((const unsigned __int16 **)v29 + 34));
        McTemplateU0zqqdz_EventWriteTransfer(
          HIDWORD(v40),
          (unsigned int)PackagedComInvalidTreatAs,
          v31,
          (_DWORD)v40,
          SBYTE4(v40),
          4,
          v30);
      }
      v32 = RemovePIIfromFilePath(*((const unsigned __int16 **)this[5] + 34));
      v37 = -2146958844;
      details::appxLog<unsigned short const *,unsigned int,unsigned int,long,unsigned short *>(
        2148008452LL,
        v33,
        PackagedComInvalidTreatAs,
        v32,
        (_DWORD)v40,
        HIDWORD(v40));
      LODWORD(v36) = -2146958844;
      v25 = "APPX_E_INVALID_MANIFEST";
      v26 = 4198;
      goto LABEL_35;
    }
    wil::com_ptr_t<IXMLDOMElement,wil::err_returncode_policy>::reset(&v40);
    v21 = WindowsGetStringRawBuffer(string, 0);
    TreatAsClassElementById = OSIntegration::DEH::PackagedComExtensionHandler::FindTreatAsClassElementById(
                                v22,
                                v8,
                                v21,
                                &v40);
    v11 = TreatAsClassElementById;
    if ( TreatAsClassElementById < 0 )
    {
      LODWORD(v36) = TreatAsClassElementById;
      v27 = "FindTreatAsClassElementById(currentTreatAsClassElement.get(), currentTreatAsValue.GetRawBuffer(nullptr), &ne"
            "xtTreatAsClassElement)";
      v28 = 4204;
LABEL_21:
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::VerifyTreatAsChain",
        v27,
        v36,
        v37);
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v40);
LABEL_22:
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v38);
      goto LABEL_37;
    }
    if ( !v40 )
    {
      v11 = -2146958844;
      LODWORD(v36) = -2146958844;
      v27 = "nextTreatAsClassElement";
      v28 = 4206;
      goto LABEL_21;
    }
    v24 = v8;
    v8 = v40;
    v41 = v40;
    ((void (__fastcall *)(struct IXMLDOMElement *))v40->lpVtbl->AddRef)(v40);
    if ( v24 )
      ((void (__fastcall *)(struct IXMLDOMElement *))v24->lpVtbl->Release)(v24);
    wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v40);
    wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v38);
    WindowsDeleteString(string);
  }
  LODWORD(v36) = v10;
  wil::details::in1diag5::Return_Hr(
    retaddr,
    (void *)0x1037,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
    "OSIntegration::DEH::PackagedComExtensionHandler::VerifyTreatAsChain",
    "ParseAndRetrieveAttribute( currentTreatAsClassElement.get(), Internal::PackagedComConstants::treatAsAttribute, curre"
    "ntTreatAsValue.GetAddressOf())",
    v36,
    v37);
LABEL_37:
  WindowsDeleteString(string);
  string = 0;
  wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v41);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
  return v11;
}

```

## disassembly

```asm
0x18016f6f4  mov     [rsp-38h+arg_0], rbx
0x18016f6f9  push    rbp
0x18016f6fa  push    rsi
0x18016f6fb  push    rdi
0x18016f6fc  push    r12
0x18016f6fe  push    r13
0x18016f700  push    r14
0x18016f702  push    r15
0x18016f704  mov     rbp, rsp
0x18016f707  sub     rsp, 60h
0x18016f70b  mov     rsi, r9
0x18016f70e  mov     r14, r8
0x18016f711  mov     r12, rdx
0x18016f714  mov     r13, rcx
0x18016f717  xor     r15d, r15d
0x18016f71a  test    r8, r8
0x18016f71d  jz      short loc_18016F722
0x18016f71f  mov     [r8], r15
0x18016f722  test    rsi, rsi
0x18016f725  jz      short loc_18016F72A
0x18016f727  mov     [r9], r15
0x18016f72a  mov     [rbp+var_18], r15
0x18016f72e  lea     rcx, [rbp+var_8]
0x18016f732  call    ??0?$com_ptr_t@UIXMLDOMElement@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAUIXMLDOMElement@@@Z; wil::com_ptr_t<IXMLDOMElement,wil::err_returncode_policy>::com_ptr_t<IXMLDOMElement,wil::err_returncode_policy>(IXMLDOMElement *)
0x18016f737  nop
0x18016f738  mov     rbx, [rbp+var_8]
0x18016f73c  mov     [rbp+string], r15
0x18016f740  xor     ecx, ecx; string
0x18016f742  call    cs:__imp_WindowsDeleteString
0x18016f748  mov     [rbp+string], r15
0x18016f74c  mov     [rsp+60h+var_40], r15; bool *
0x18016f751  lea     r9, [rbp+string]; HSTRING *
0x18016f755  lea     r8, aTreatas; "TreatAs"
0x18016f75c  mov     rdx, rbx; struct IXMLDOMElement *
0x18016f75f  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x18016f764  mov     edi, eax
0x18016f766  test    eax, eax
0x18016f768  js      loc_18016FA84
0x18016f76e  mov     [rbp+var_20], r15
0x18016f772  lea     rcx, [rbp+var_20]
0x18016f776  call    ?reset@?$com_ptr_t@UIXMLDOMElement@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IXMLDOMElement,wil::err_returncode_policy>::reset(void)
0x18016f77b  xor     edx, edx; length
0x18016f77d  mov     rcx, [rbp+string]; string
0x18016f781  call    cs:__imp_WindowsGetStringRawBuffer
0x18016f787  lea     r9, [rbp+var_20]; struct IXMLDOMElement **
0x18016f78b  mov     r8, rax; unsigned __int16 *
0x18016f78e  mov     rdx, r12; struct IXMLDOMElement *
0x18016f791  call    ?FindReferencedClassElementById@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAU4@@Z; OSIntegration::DEH::PackagedComExtensionHandler::FindReferencedClassElementById(IXMLDOMElement *,ushort const *,IXMLDOMElement * *)
0x18016f796  mov     edi, eax
0x18016f798  test    eax, eax
0x18016f79a  js      loc_18016FA53
0x18016f7a0  mov     r15, [rbp+var_20]
0x18016f7a4  test    r15, r15
0x18016f7a7  jnz     loc_18016F9EC
0x18016f7ad  mov     rcx, [rbp+var_18]
0x18016f7b1  test    rcx, rcx
0x18016f7b4  jnz     short loc_18016F7D6
0x18016f7b6  lea     rcx, [rbp+var_18]
0x18016f7ba  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016f7bf  lea     r8, [rbp+var_18]
0x18016f7c3  call    ?Make@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@SAJAEBU?$DefaultHash@PEAUHSTRING__@@@2345@AEBU?$DefaultEqualityPredicate@PEAUHSTRING__@@@2345@PEAPEAV12345@@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Make(Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>> * *)
0x18016f7c8  mov     edi, eax
0x18016f7ca  test    eax, eax
0x18016f7cc  js      loc_18016F88E
0x18016f7d2  mov     rcx, [rbp+var_18]
0x18016f7d6  mov     [rbp+arg_10], r15b
0x18016f7da  mov     rax, [rcx]
0x18016f7dd  lea     r9, [rbp+arg_10]
0x18016f7e1  xor     r8d, r8d
0x18016f7e4  mov     rdx, [rbp+string]
0x18016f7e8  mov     rax, [rax+50h]
0x18016f7ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016f7f1  mov     edi, eax
0x18016f7f3  test    eax, eax
0x18016f7f5  js      loc_18016F9DA
0x18016f7fb  mov     [rbp+var_10], r15
0x18016f7ff  cmp     [rbp+arg_10], r15b
0x18016f803  jnz     loc_18016F8FF
0x18016f809  lea     rcx, [rbp+var_10]
0x18016f80d  call    ?reset@?$com_ptr_t@UIXMLDOMElement@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IXMLDOMElement,wil::err_returncode_policy>::reset(void)
0x18016f812  xor     edx, edx; length
0x18016f814  mov     rcx, [rbp+string]; string
0x18016f818  call    cs:__imp_WindowsGetStringRawBuffer
0x18016f81e  lea     r9, [rbp+var_10]; struct IXMLDOMElement **
0x18016f822  mov     r8, rax; unsigned __int16 *
0x18016f825  mov     rdx, rbx; struct IXMLDOMElement *
0x18016f828  call    ?FindTreatAsClassElementById@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAU4@@Z; OSIntegration::DEH::PackagedComExtensionHandler::FindTreatAsClassElementById(IXMLDOMElement *,ushort const *,IXMLDOMElement * *)
0x18016f82d  mov     edi, eax
0x18016f82f  test    eax, eax
0x18016f831  js      loc_18016F8ED
0x18016f837  mov     rcx, [rbp+var_10]
0x18016f83b  test    rcx, rcx
0x18016f83e  jz      short loc_18016F8A3
0x18016f840  mov     rdi, rbx
0x18016f843  mov     rbx, rcx
0x18016f846  mov     [rbp+var_8], rcx
0x18016f84a  mov     rax, [rcx]
0x18016f84d  mov     rax, [rax+8]
0x18016f851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016f856  test    rdi, rdi
0x18016f859  jz      short loc_18016F86B
0x18016f85b  mov     rax, [rdi]
0x18016f85e  mov     rcx, rdi
0x18016f861  mov     rax, [rax+10h]
0x18016f865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016f86a  nop
0x18016f86b  lea     rcx, [rbp+var_10]
0x18016f86f  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x18016f874  nop
0x18016f875  lea     rcx, [rbp+var_20]
0x18016f879  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x18016f87e  nop
0x18016f87f  mov     rcx, [rbp+string]; string
0x18016f883  call    cs:__imp_WindowsDeleteString
0x18016f889  jmp     loc_18016F73C
0x18016f88e  mov     dword ptr [rsp+60h+var_38], eax
0x18016f892  lea     rax, aHashmapHstring_0; "(HashMap<HSTRING, IInspectable*>::Make("...
0x18016f899  mov     edx, 1052h
0x18016f89e  jmp     loc_18016FA63
0x18016f8a3  mov     edi, 80080204h
0x18016f8a8  mov     dword ptr [rsp+60h+var_38], edi; char *
0x18016f8ac  lea     rax, aNexttreatascla; "nextTreatAsClassElement"
0x18016f8b3  mov     edx, 106Eh; void *
0x18016f8b8  mov     [rsp+60h+var_40], rax; char *
0x18016f8bd  lea     r9, aOsintegrationD_370; "OSIntegration::DEH::PackagedComExtensio"...
0x18016f8c4  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016f8cb  mov     rcx, [rbp+38h]; this
0x18016f8cf  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016f8d4  nop
0x18016f8d5  lea     rcx, [rbp+var_10]
0x18016f8d9  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x18016f8de  nop
0x18016f8df  lea     rcx, [rbp+var_20]
0x18016f8e3  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x18016f8e8  jmp     loc_18016FAB1
0x18016f8ed  mov     dword ptr [rsp+60h+var_38], eax
0x18016f8f1  lea     rax, aFindtreatascla; "FindTreatAsClassElementById(currentTrea"...
0x18016f8f8  mov     edx, 106Ch
0x18016f8fd  jmp     short loc_18016F8B8
0x18016f8ff  lea     r9, [rbp+var_10]; struct APPX_XML_LINE_INFORMATION *
0x18016f903  xor     r8d, r8d; unsigned __int16 *
0x18016f906  mov     rdx, r12; struct IXMLDOMNode *
0x18016f909  mov     rcx, [r13+28h]; this
0x18016f90d  call    ?GetXmlLineInformation@Package@OSIntegration@@QEBAJPEBUIXMLDOMNode@@PEBGPEAUAPPX_XML_LINE_INFORMATION@@@Z; OSIntegration::Package::GetXmlLineInformation(IXMLDOMNode const *,ushort const *,APPX_XML_LINE_INFORMATION *)
0x18016f912  mov     rcx, [rbp+38h]; this
0x18016f916  mov     edi, 80080204h
0x18016f91b  mov     dword ptr [rsp+60h+var_38], edi; char *
0x18016f91f  lea     rax, aHresult0x80080; "((HRESULT)0x80080204L)"
0x18016f926  mov     [rsp+60h+var_40], rax; char *
0x18016f92b  lea     r9, aOsintegrationD_370; "OSIntegration::DEH::PackagedComExtensio"...
0x18016f932  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016f939  mov     edx, 1064h; void *
0x18016f93e  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016f943  test    cs:byte_1802E21CA, 4
0x18016f94a  jz      short loc_18016F986
0x18016f94c  mov     rcx, [r13+28h]
0x18016f950  mov     rbx, [rcx+0E0h]
0x18016f957  mov     rcx, [rcx+110h]; unsigned __int16 *
0x18016f95e  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x18016f963  mov     [rsp+60h+var_30], rbx
0x18016f968  mov     dword ptr [rsp+60h+var_38], edi
0x18016f96c  mov     ecx, dword ptr [rbp+var_10+4]
0x18016f96f  mov     dword ptr [rsp+60h+var_40], ecx
0x18016f973  mov     r9d, dword ptr [rbp+var_10]
0x18016f977  mov     r8, rax
0x18016f97a  lea     rdx, PackagedComInvalidTreatAs
0x18016f981  call    McTemplateU0zqqdz_EventWriteTransfer
0x18016f986  mov     rcx, [r13+28h]
0x18016f98a  mov     rbx, [rcx+0E0h]
0x18016f991  mov     rcx, [rcx+110h]; unsigned __int16 *
0x18016f998  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x18016f99d  mov     [rsp+60h+var_28], rbx
0x18016f9a2  mov     dword ptr [rsp+60h+var_30], edi
0x18016f9a6  mov     ecx, dword ptr [rbp+var_10+4]
0x18016f9a9  mov     dword ptr [rsp+60h+var_38], ecx
0x18016f9ad  mov     ecx, dword ptr [rbp+var_10]
0x18016f9b0  mov     dword ptr [rsp+60h+var_40], ecx
0x18016f9b4  mov     r9, rax
0x18016f9b7  lea     r8, PackagedComInvalidTreatAs
0x18016f9be  mov     ecx, edi
0x18016f9c0  call    ??$appxLog@PEBGIIJPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEBGIIJPEAG@Z; details::appxLog<ushort const *,uint,uint,long,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort const *,uint,uint,long,ushort *)
0x18016f9c5  mov     dword ptr [rsp+60h+var_38], edi
0x18016f9c9  lea     rax, aAppxEInvalidMa; "APPX_E_INVALID_MANIFEST"
0x18016f9d0  mov     edx, 1066h
0x18016f9d5  jmp     loc_18016FA63
0x18016f9da  mov     dword ptr [rsp+60h+var_38], eax
0x18016f9de  lea     rax, aTreataslistIns; "treatAsList->Insert(currentTreatAsValue"...
0x18016f9e5  mov     edx, 1056h
0x18016f9ea  jmp     short loc_18016FA63
0x18016f9ec  test    r14, r14
0x18016f9ef  jz      short loc_18016FA38
0x18016f9f1  mov     rdx, r14; newString
0x18016f9f4  mov     rcx, [rbp+string]; string
0x18016f9f8  call    cs:__imp_WindowsDuplicateString
0x18016f9fe  mov     edi, eax
0x18016fa00  test    eax, eax
0x18016fa02  jns     short loc_18016FA38
0x18016fa04  mov     rcx, [rbp+38h]; this
0x18016fa08  mov     dword ptr [rsp+60h+var_38], eax; char *
0x18016fa0c  lea     rax, aWindowsduplica; "WindowsDuplicateString(currentTreatAsVa"...
0x18016fa13  mov     [rsp+60h+var_40], rax; char *
0x18016fa18  lea     r9, aOsintegrationD_370; "OSIntegration::DEH::PackagedComExtensio"...
0x18016fa1f  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016fa26  mov     edx, 1043h; void *
0x18016fa2b  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016fa30  xor     r15d, r15d
0x18016fa33  jmp     loc_18016F8DF
0x18016fa38  test    rsi, rsi
0x18016fa3b  jz      short loc_18016FA48
0x18016fa3d  mov     [rbp+var_20], 0
0x18016fa45  mov     [rsi], r15
0x18016fa48  xor     r15d, r15d
0x18016fa4b  mov     edi, r15d
0x18016fa4e  jmp     loc_18016F8DF
0x18016fa53  mov     dword ptr [rsp+60h+var_38], eax; char *
0x18016fa57  lea     rax, aFindreferenced_0; "FindReferencedClassElementById(treatAsC"...
0x18016fa5e  mov     edx, 103Dh; void *
0x18016fa63  mov     [rsp+60h+var_40], rax; char *
0x18016fa68  lea     r9, aOsintegrationD_370; "OSIntegration::DEH::PackagedComExtensio"...
0x18016fa6f  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016fa76  mov     rcx, [rbp+38h]; this
0x18016fa7a  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016fa7f  jmp     loc_18016F8DF
0x18016fa84  mov     rcx, [rbp+38h]; this
0x18016fa88  mov     dword ptr [rsp+60h+var_38], edi; char *
0x18016fa8c  lea     rax, aParseandretrie_26; "ParseAndRetrieveAttribute( currentTreat"...
0x18016fa93  mov     [rsp+60h+var_40], rax; char *
0x18016fa98  lea     r9, aOsintegrationD_370; "OSIntegration::DEH::PackagedComExtensio"...
0x18016fa9f  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016faa6  mov     edx, 1037h; void *
0x18016faab  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016fab0  nop
0x18016fab1  mov     rcx, [rbp+string]; string
0x18016fab5  call    cs:__imp_WindowsDeleteString
0x18016fabb  mov     [rbp+string], r15
0x18016fabf  lea     rcx, [rbp+var_8]
0x18016fac3  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x18016fac8  nop
0x18016fac9  lea     rcx, [rbp+var_18]
0x18016facd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016fad2  mov     eax, edi
0x18016fad4  mov     rbx, [rsp+60h+arg_0]
0x18016fadc  add     rsp, 60h
0x18016fae0  pop     r15
0x18016fae2  pop     r14
0x18016fae4  pop     r13
0x18016fae6  pop     r12
0x18016fae8  pop     rdi
0x18016fae9  pop     rsi
0x18016faea  pop     rbp
0x18016faeb  retn
```
