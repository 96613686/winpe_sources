# OSIntegration::DEH::PackagedComExtensionHandler::VerifyVersionIndependentProgIdHelper(IXMLDOMElement *,HSTRING__ *,HSTRING__ *,HSTRING__ *)

- ea: `0x18016faf4`
- end: `0x18016fe3b`
- name: `?VerifyVersionIndependentProgIdHelper@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEAUHSTRING__@@11@Z`
- size: `839`
- prototype: `__int64 __fastcall(OSIntegration::DEH::PackagedComExtensionHandler *__hidden this, struct IXMLDOMElement *, HSTRING, HSTRING, HSTRING)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d70e0`

## callees

- `0x18000b3bc`
- `0x18000b9e0`
- `0x1800550f4`
- `0x18007d350`
- `0x180098ed0`
- `0x18009aff4`
- `0x18009cfac`
- `0x1800ccb88`
- `0x1800d9e70`
- `0x18013ced4`
- `0x18013d6f8`
- `0x18016faf4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016fb92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016fb92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016fb34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016fbe2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016fe16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016fe28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016fb34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016fbe2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016fe16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016fe28`

## string_xrefs

- `0x18016fbcd`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016fc77`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016fd47`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016fdf6`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016fde3`: `APPX_E_INVALID_MANIFEST`
- `0x18016fb5e`: `FollowProgIdChain( progId, currentVersion, progIdClsid.GetAddressOf())`
- `0x18016fbc6`: `OSIntegration::DEH::PackagedComExtensionHandler::VerifyVersionIndependentProgIdHelper`
- `0x18016fc70`: `OSIntegration::DEH::PackagedComExtensionHandler::VerifyVersionIndependentProgIdHelper`
- `0x18016fd40`: `OSIntegration::DEH::PackagedComExtensionHandler::VerifyVersionIndependentProgIdHelper`
- `0x18016fdef`: `OSIntegration::DEH::PackagedComExtensionHandler::VerifyVersionIndependentProgIdHelper`
- `0x18016fbb1`: `FindReferencedClassElementById(progId, progIdClsid.GetRawBuffer(nullptr), &classElementToCompare)`
- `0x18016fc17`: `ParseAndRetrieveAttribute( classElementToCompare.Get(), Internal::PackagedComConstants::versionIndependentProgIdAttribute, versionIndependentProgIdToCompare.GetAddressOf(), &versionIndependentProgIdToCompareFound)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall OSIntegration::DEH::PackagedComExtensionHandler::VerifyVersionIndependentProgIdHelper(
        OSIntegration::Package **this,
        struct IXMLDOMNode *a2,
        HSTRING a3,
        HSTRING a4,
        HSTRING a5)
{
  int v9; // eax
  HSTRING v10; // r8
  unsigned int v11; // ebx
  const char *v12; // rax
  __int64 v13; // rdx
  const unsigned __int16 *StringRawBuffer; // rax
  OSIntegration::DEH::PackagedComExtensionHandler *v15; // rcx
  int ReferencedClassElementById; // eax
  OSIntegration::DEH::PackagedComExtensionHandler *v17; // rcx
  int v18; // eax
  HSTRING v19; // r8
  OSIntegration::Package *v20; // rcx
  __int64 v21; // rbx
  unsigned int v22; // eax
  const unsigned __int16 *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rdx
  OSIntegration::Package *v26; // rcx
  __int64 v27; // rbx
  unsigned int v28; // eax
  const unsigned __int16 *v29; // rax
  __int64 v30; // rdx
  char *v32; // [rsp+28h] [rbp-48h]
  char *v33; // [rsp+28h] [rbp-48h]
  int v34; // [rsp+30h] [rbp-40h]
  bool v35; // [rsp+40h] [rbp-30h] BYREF
  __int64 v36; // [rsp+48h] [rbp-28h] BYREF
  HSTRING v37; // [rsp+50h] [rbp-20h] BYREF
  HSTRING string; // [rsp+58h] [rbp-18h] BYREF
  struct IXMLDOMElement *v39[2]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+98h] [rbp+28h]

  v37 = 0;
  v39[0] = 0;
  v35 = 0;
  v36 = 0;
  WindowsDeleteString(0);
  string = 0;
  v9 = OSIntegration::DEH::PackagedComExtensionHandler::FollowProgIdChain(
         (OSIntegration::DEH::PackagedComExtensionHandler *)this,
         a2,
         a3,
         &string);
  v11 = v9;
  if ( v9 < 0 )
  {
    LODWORD(v32) = v9;
    v12 = "FollowProgIdChain( progId, currentVersion, progIdClsid.GetAddressOf())";
    v13 = 3960;
LABEL_7:
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::VerifyVersionIndependentProgIdHelper",
      v12,
      v32,
      v34);
    goto LABEL_19;
  }
  if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                       (Microsoft::WRL::Wrappers::Details *)string,
                       a4,
                       v10) )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v39);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    ReferencedClassElementById = OSIntegration::DEH::PackagedComExtensionHandler::FindReferencedClassElementById(
                                   v15,
                                   (struct IXMLDOMElement *)a2,
                                   StringRawBuffer,
                                   v39);
    v11 = ReferencedClassElementById;
    if ( ReferencedClassElementById < 0 )
    {
      LODWORD(v32) = ReferencedClassElementById;
      v12 = "FindReferencedClassElementById(progId, progIdClsid.GetRawBuffer(nullptr), &classElementToCompare)";
      v13 = 3970;
      goto LABEL_7;
    }
    WindowsDeleteString(v37);
    v37 = 0;
    v18 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(
            v17,
            v39[0],
            L"VersionIndependentProgId",
            &v37,
            &v35);
    v11 = v18;
    if ( v18 < 0 )
    {
      LODWORD(v32) = v18;
      v12 = "ParseAndRetrieveAttribute( classElementToCompare.Get(), Internal::PackagedComConstants::versionIndependentPr"
            "ogIdAttribute, versionIndependentProgIdToCompare.GetAddressOf(), &versionIndependentProgIdToCompareFound)";
      v13 = 3976;
      goto LABEL_7;
    }
    if ( v35 )
    {
      if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                            (Microsoft::WRL::Wrappers::Details *)v37,
                            a5,
                            v19) )
        goto LABEL_4;
      OSIntegration::Package::GetXmlLineInformation(this[5], a2, 0, (struct APPX_XML_LINE_INFORMATION *)&v36);
      LODWORD(v32) = -2146958844;
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0xF9D,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::VerifyVersionIndependentProgIdHelper",
        "((HRESULT)0x80080204L)",
        v32,
        v34);
      if ( (byte_1802E21CA & 4) != 0 )
      {
        v20 = this[5];
        v21 = *((_QWORD *)v20 + 28);
        v22 = (unsigned int)RemovePIIfromFilePath(*((const unsigned __int16 **)v20 + 34));
        McTemplateU0zqqdz_EventWriteTransfer(
          HIDWORD(v36),
          (unsigned int)PackagedComInvalidClassVersionIndependentProgIdWrongClassVersionIndependentProgId,
          v22,
          v36,
          SBYTE4(v36),
          4,
          v21);
      }
      v23 = RemovePIIfromFilePath(*((const unsigned __int16 **)this[5] + 34));
      details::appxLog<unsigned short const *,unsigned int,unsigned int,long,unsigned short *>(
        2148008452LL,
        v24,
        PackagedComInvalidClassVersionIndependentProgIdWrongClassVersionIndependentProgId,
        v23);
      v25 = 3999;
    }
    else
    {
      OSIntegration::Package::GetXmlLineInformation(this[5], a2, 0, (struct APPX_XML_LINE_INFORMATION *)&v36);
      LODWORD(v32) = -2146958844;
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0xFAE,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::VerifyVersionIndependentProgIdHelper",
        "((HRESULT)0x80080204L)",
        v32,
        v34);
      if ( (byte_1802E21CA & 4) != 0 )
      {
        v26 = this[5];
        v27 = *((_QWORD *)v26 + 28);
        v28 = (unsigned int)RemovePIIfromFilePath(*((const unsigned __int16 **)v26 + 34));
        McTemplateU0zqqdz_EventWriteTransfer(
          HIDWORD(v36),
          (unsigned int)PackagedComInvalidClassVersionIndependentProgIdNoClassVersionIndependentProgId,
          v28,
          v36,
          SBYTE4(v36),
          4,
          v27);
      }
      v29 = RemovePIIfromFilePath(*((const unsigned __int16 **)this[5] + 34));
      details::appxLog<unsigned short const *,unsigned int,unsigned int,long,unsigned short *>(
        2148008452LL,
        v30,
        PackagedComInvalidClassVersionIndependentProgIdNoClassVersionIndependentProgId,
        v29);
      v25 = 4016;
    }
    LODWORD(v33) = -2146958844;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::VerifyVersionIndependentProgIdHelper",
      "APPX_E_INVALID_MANIFEST",
      v33,
      -2146958844);
    v11 = -2146958844;
    goto LABEL_19;
  }
LABEL_4:
  v11 = 0;
LABEL_19:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v39);
  WindowsDeleteString(v37);
  v37 = 0;
  WindowsDeleteString(string);
  return v11;
}

```

## disassembly

```asm
0x18016faf4  push    rbp
0x18016faf6  push    rbx
0x18016faf7  push    rsi
0x18016faf8  push    rdi
0x18016faf9  push    r14
0x18016fafb  mov     rbp, rsp
0x18016fafe  sub     rsp, 70h
0x18016fb02  mov     r14, r9
0x18016fb05  mov     rbx, r8
0x18016fb08  mov     rdi, rdx
0x18016fb0b  mov     rsi, rcx
0x18016fb0e  mov     [rbp+string], 0
0x18016fb16  mov     [rbp+var_20], 0
0x18016fb1e  mov     [rbp+var_10], 0
0x18016fb26  mov     [rbp+var_30], 0
0x18016fb2a  mov     [rbp+var_28], 0
0x18016fb32  xor     ecx, ecx; string
0x18016fb34  call    cs:__imp_WindowsDeleteString
0x18016fb3a  mov     [rbp+string], 0
0x18016fb42  lea     r9, [rbp+string]; HSTRING *
0x18016fb46  mov     r8, rbx; HSTRING
0x18016fb49  mov     rdx, rdi; struct IXMLDOMElement *
0x18016fb4c  mov     rcx, rsi; this
0x18016fb4f  call    ?FollowProgIdChain@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEAUHSTRING__@@PEAPEAU5@@Z; OSIntegration::DEH::PackagedComExtensionHandler::FollowProgIdChain(IXMLDOMElement *,HSTRING__ *,HSTRING__ * *)
0x18016fb54  mov     ebx, eax
0x18016fb56  test    eax, eax
0x18016fb58  jns     short loc_18016FB6C
0x18016fb5a  mov     dword ptr [rsp+70h+var_48], eax
0x18016fb5e  lea     rax, aFollowprogidch; "FollowProgIdChain( progId, currentVersi"...
0x18016fb65  mov     edx, 0F78h
0x18016fb6a  jmp     short loc_18016FBBD
0x18016fb6c  mov     rdx, r14; HSTRING
0x18016fb6f  mov     rcx, [rbp+string]; this
0x18016fb73  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18016fb78  test    eax, eax
0x18016fb7a  jnz     short loc_18016FB83
0x18016fb7c  xor     ebx, ebx
0x18016fb7e  jmp     loc_18016FE08
0x18016fb83  lea     rcx, [rbp+var_10]
0x18016fb87  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016fb8c  xor     edx, edx; length
0x18016fb8e  mov     rcx, [rbp+string]; string
0x18016fb92  call    cs:__imp_WindowsGetStringRawBuffer
0x18016fb98  lea     r9, [rbp+var_10]; struct IXMLDOMElement **
0x18016fb9c  mov     r8, rax; unsigned __int16 *
0x18016fb9f  mov     rdx, rdi; struct IXMLDOMElement *
0x18016fba2  call    ?FindReferencedClassElementById@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAU4@@Z; OSIntegration::DEH::PackagedComExtensionHandler::FindReferencedClassElementById(IXMLDOMElement *,ushort const *,IXMLDOMElement * *)
0x18016fba7  mov     ebx, eax
0x18016fba9  test    eax, eax
0x18016fbab  jns     short loc_18016FBDE
0x18016fbad  mov     dword ptr [rsp+70h+var_48], eax; char *
0x18016fbb1  lea     rax, aFindreferenced; "FindReferencedClassElementById(progId, "...
0x18016fbb8  mov     edx, 0F82h; void *
0x18016fbbd  mov     rcx, [rbp+28h]; this
0x18016fbc1  mov     [rsp+70h+var_50], rax; char *
0x18016fbc6  lea     r9, aOsintegrationD_470; "OSIntegration::DEH::PackagedComExtensio"...
0x18016fbcd  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016fbd4  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016fbd9  jmp     loc_18016FE08
0x18016fbde  mov     rcx, [rbp+var_20]; string
0x18016fbe2  call    cs:__imp_WindowsDeleteString
0x18016fbe8  mov     [rbp+var_20], 0
0x18016fbf0  lea     rax, [rbp+var_30]
0x18016fbf4  mov     [rsp+70h+var_50], rax; bool *
0x18016fbf9  lea     r9, [rbp+var_20]; HSTRING *
0x18016fbfd  lea     r8, aVersionindepen; "VersionIndependentProgId"
0x18016fc04  mov     rdx, [rbp+var_10]; struct IXMLDOMElement *
0x18016fc08  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x18016fc0d  mov     ebx, eax
0x18016fc0f  test    eax, eax
0x18016fc11  jns     short loc_18016FC25
0x18016fc13  mov     dword ptr [rsp+70h+var_48], eax
0x18016fc17  lea     rax, aParseandretrie_1; "ParseAndRetrieveAttribute( classElement"...
0x18016fc1e  mov     edx, 0F88h
0x18016fc23  jmp     short loc_18016FBBD
0x18016fc25  cmp     [rbp+var_30], 0
0x18016fc29  jz      loc_18016FD14
0x18016fc2f  mov     rdx, [rbp+arg_20]; HSTRING
0x18016fc33  mov     rcx, [rbp+var_20]; this
0x18016fc37  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18016fc3c  test    eax, eax
0x18016fc3e  jz      loc_18016FB7C
0x18016fc44  lea     r9, [rbp+var_28]; struct APPX_XML_LINE_INFORMATION *
0x18016fc48  xor     r8d, r8d; unsigned __int16 *
0x18016fc4b  mov     rdx, rdi; struct IXMLDOMNode *
0x18016fc4e  mov     rcx, [rsi+28h]; this
0x18016fc52  call    ?GetXmlLineInformation@Package@OSIntegration@@QEBAJPEBUIXMLDOMNode@@PEBGPEAUAPPX_XML_LINE_INFORMATION@@@Z; OSIntegration::Package::GetXmlLineInformation(IXMLDOMNode const *,ushort const *,APPX_XML_LINE_INFORMATION *)
0x18016fc57  mov     rcx, [rbp+28h]; this
0x18016fc5b  mov     edi, 80080204h
0x18016fc60  mov     dword ptr [rsp+70h+var_48], edi; char *
0x18016fc64  lea     rax, aHresult0x80080; "((HRESULT)0x80080204L)"
0x18016fc6b  mov     [rsp+70h+var_50], rax; char *
0x18016fc70  lea     r9, aOsintegrationD_470; "OSIntegration::DEH::PackagedComExtensio"...
0x18016fc77  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016fc7e  mov     edx, 0F9Dh; void *
0x18016fc83  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016fc88  test    cs:byte_1802E21CA, 4
0x18016fc8f  jz      short loc_18016FCCB
0x18016fc91  mov     rcx, [rsi+28h]
0x18016fc95  mov     rbx, [rcx+0E0h]
0x18016fc9c  mov     rcx, [rcx+110h]; unsigned __int16 *
0x18016fca3  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x18016fca8  mov     qword ptr [rsp+70h+var_40], rbx
0x18016fcad  mov     dword ptr [rsp+70h+var_48], edi
0x18016fcb1  mov     ecx, dword ptr [rbp+var_28+4]
0x18016fcb4  mov     dword ptr [rsp+70h+var_50], ecx
0x18016fcb8  mov     r9d, dword ptr [rbp+var_28]
0x18016fcbc  mov     r8, rax
0x18016fcbf  lea     rdx, PackagedComInvalidClassVersionIndependentProgIdWrongClassVersionIndependentProgId
0x18016fcc6  call    McTemplateU0zqqdz_EventWriteTransfer
0x18016fccb  mov     rcx, [rsi+28h]
0x18016fccf  mov     rbx, [rcx+0E0h]
0x18016fcd6  mov     rcx, [rcx+110h]; unsigned __int16 *
0x18016fcdd  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x18016fce2  mov     [rsp+70h+var_38], rbx
0x18016fce7  mov     [rsp+70h+var_40], edi
0x18016fceb  mov     ecx, dword ptr [rbp+var_28+4]
0x18016fcee  mov     dword ptr [rsp+70h+var_48], ecx
0x18016fcf2  mov     ecx, dword ptr [rbp+var_28]
0x18016fcf5  mov     dword ptr [rsp+70h+var_50], ecx
0x18016fcf9  mov     r9, rax
0x18016fcfc  lea     r8, PackagedComInvalidClassVersionIndependentProgIdWrongClassVersionIndependentProgId
0x18016fd03  mov     ecx, edi
0x18016fd05  call    ??$appxLog@PEBGIIJPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEBGIIJPEAG@Z; details::appxLog<ushort const *,uint,uint,long,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort const *,uint,uint,long,ushort *)
0x18016fd0a  mov     edx, 0F9Fh
0x18016fd0f  jmp     loc_18016FDDF
0x18016fd14  lea     r9, [rbp+var_28]; struct APPX_XML_LINE_INFORMATION *
0x18016fd18  xor     r8d, r8d; unsigned __int16 *
0x18016fd1b  mov     rdx, rdi; struct IXMLDOMNode *
0x18016fd1e  mov     rcx, [rsi+28h]; this
0x18016fd22  call    ?GetXmlLineInformation@Package@OSIntegration@@QEBAJPEBUIXMLDOMNode@@PEBGPEAUAPPX_XML_LINE_INFORMATION@@@Z; OSIntegration::Package::GetXmlLineInformation(IXMLDOMNode const *,ushort const *,APPX_XML_LINE_INFORMATION *)
0x18016fd27  mov     rcx, [rbp+28h]; this
0x18016fd2b  mov     edi, 80080204h
0x18016fd30  mov     dword ptr [rsp+70h+var_48], edi; char *
0x18016fd34  lea     rax, aHresult0x80080; "((HRESULT)0x80080204L)"
0x18016fd3b  mov     [rsp+70h+var_50], rax; char *
0x18016fd40  lea     r9, aOsintegrationD_470; "OSIntegration::DEH::PackagedComExtensio"...
0x18016fd47  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016fd4e  mov     edx, 0FAEh; void *
0x18016fd53  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016fd58  test    cs:byte_1802E21CA, 4
0x18016fd5f  jz      short loc_18016FD9B
0x18016fd61  mov     rcx, [rsi+28h]
0x18016fd65  mov     rbx, [rcx+0E0h]
0x18016fd6c  mov     rcx, [rcx+110h]; unsigned __int16 *
0x18016fd73  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x18016fd78  mov     qword ptr [rsp+70h+var_40], rbx
0x18016fd7d  mov     dword ptr [rsp+70h+var_48], edi
0x18016fd81  mov     ecx, dword ptr [rbp+var_28+4]
0x18016fd84  mov     dword ptr [rsp+70h+var_50], ecx
0x18016fd88  mov     r9d, dword ptr [rbp+var_28]
0x18016fd8c  mov     r8, rax
0x18016fd8f  lea     rdx, PackagedComInvalidClassVersionIndependentProgIdNoClassVersionIndependentProgId
0x18016fd96  call    McTemplateU0zqqdz_EventWriteTransfer
0x18016fd9b  mov     rcx, [rsi+28h]
0x18016fd9f  mov     rbx, [rcx+0E0h]
0x18016fda6  mov     rcx, [rcx+110h]; unsigned __int16 *
0x18016fdad  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x18016fdb2  mov     [rsp+70h+var_38], rbx
0x18016fdb7  mov     [rsp+70h+var_40], edi; int
0x18016fdbb  mov     ecx, dword ptr [rbp+var_28+4]
0x18016fdbe  mov     dword ptr [rsp+70h+var_48], ecx
0x18016fdc2  mov     ecx, dword ptr [rbp+var_28]
0x18016fdc5  mov     dword ptr [rsp+70h+var_50], ecx
0x18016fdc9  mov     r9, rax
0x18016fdcc  lea     r8, PackagedComInvalidClassVersionIndependentProgIdNoClassVersionIndependentProgId
0x18016fdd3  mov     ecx, edi
0x18016fdd5  call    ??$appxLog@PEBGIIJPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEBGIIJPEAG@Z; details::appxLog<ushort const *,uint,uint,long,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort const *,uint,uint,long,ushort *)
0x18016fdda  mov     edx, 0FB0h; void *
0x18016fddf  mov     dword ptr [rsp+70h+var_48], edi; char *
0x18016fde3  lea     rax, aAppxEInvalidMa; "APPX_E_INVALID_MANIFEST"
0x18016fdea  mov     [rsp+70h+var_50], rax; char *
0x18016fdef  lea     r9, aOsintegrationD_470; "OSIntegration::DEH::PackagedComExtensio"...
0x18016fdf6  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016fdfd  mov     rcx, [rbp+28h]; this
0x18016fe01  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016fe06  mov     ebx, edi
0x18016fe08  lea     rcx, [rbp+var_10]
0x18016fe0c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18016fe11  nop
0x18016fe12  mov     rcx, [rbp+var_20]; string
0x18016fe16  call    cs:__imp_WindowsDeleteString
0x18016fe1c  mov     [rbp+var_20], 0
0x18016fe24  mov     rcx, [rbp+string]; string
0x18016fe28  call    cs:__imp_WindowsDeleteString
0x18016fe2e  mov     eax, ebx
0x18016fe30  add     rsp, 70h
0x18016fe34  pop     r14
0x18016fe36  pop     rdi
0x18016fe37  pop     rsi
0x18016fe38  pop     rbx
0x18016fe39  pop     rbp
0x18016fe3a  retn
```
