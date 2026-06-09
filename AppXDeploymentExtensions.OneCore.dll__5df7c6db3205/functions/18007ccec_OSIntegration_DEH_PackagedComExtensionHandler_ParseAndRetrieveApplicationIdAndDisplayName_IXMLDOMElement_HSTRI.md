# OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveApplicationIdAndDisplayName(IXMLDOMElement *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x18007ccec`
- end: `0x18007d034`
- name: `?ParseAndRetrieveApplicationIdAndDisplayName@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEAPEAUHSTRING__@@1@Z`
- size: `840`
- prototype: `__int64 __fastcall(OSIntegration::DEH::PackagedComExtensionHandler *__hidden this, struct IXMLDOMElement *, HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18016b770`

## callees

- `0x18000bd80`
- `0x18000e6e0`
- `0x180077608`
- `0x18007ccec`
- `0x18007d03c`
- `0x180099aa4`
- `0x18009aff4`
- `0x1800f0700`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007cebd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007cef9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007cebd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007cef9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007cea8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007cee6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007cf35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007cf43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007cf8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007cf98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007cea8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007cee6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007cf35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007cf43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007cf8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007cf98`

## string_xrefs

- `0x18007cd3d`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18007cdb5`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18007ce2c`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18007cf21`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18007cff1`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18007cfde`: `APPX_E_INVALID_MANIFEST`
- `0x18007cd36`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveApplicationIdAndDisplayName`
- `0x18007cdae`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveApplicationIdAndDisplayName`
- `0x18007ce25`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveApplicationIdAndDisplayName`
- `0x18007cf1a`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveApplicationIdAndDisplayName`
- `0x18007cfea`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveApplicationIdAndDisplayName`
- `0x18007ce19`: `Tools::GetLocalizedStringAttributeValueStringFromQuery( _sourcePackage, Internal::PackagedComConstants::applicationVisualElementsChildXPath, applicationElement.get(), Internal::PackagedComConstants::displayNameAttribute, &displayNameBuffer, &displayNameAttributeFound)`
- `0x18007cd2a`: `GetXMLApplicationNode(element, &applicationElement)`
- `0x18007cda2`: `GetAttributeValueStringFromElement( applicationElement.get(), Internal::PackagedComConstants::idAttribute, idBuffer, &idAttributeFound)`
- `0x18007cecd`: `tempApplicationId.Set( idBuffer.GetChars(), idBuffer.GetLength())`
- `0x18007cf09`: `tempApplicationDisplayName.Set( displayNameBuffer.GetChars(), displayNameBuffer.GetLength())`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveApplicationIdAndDisplayName(
        OSIntegration::Tools **this,
        struct IXMLDOMElement *a2,
        HSTRING *a3,
        HSTRING *a4)
{
  int XMLApplicationNode; // eax
  unsigned int v8; // ebx
  struct IXMLDOMElement *v9; // rbx
  int AttributeValueStringFromElement; // eax
  unsigned int v11; // edi
  int LocalizedStringAttributeValueStringFromQuery; // eax
  unsigned __int64 v13; // rdx
  HRESULT v14; // eax
  const char *v15; // rax
  __int64 v16; // rdx
  UINT32 v17; // edi
  const WCHAR *v18; // rsi
  HRESULT v19; // eax
  HSTRING v21; // rax
  HSTRING v22; // rax
  unsigned __int64 v23; // rdx
  int *v24; // [rsp+20h] [rbp-49h]
  struct Common::StringBuffer *v25; // [rsp+28h] [rbp-41h]
  struct Common::StringBuffer *v26; // [rsp+28h] [rbp-41h]
  int v27; // [rsp+30h] [rbp-39h]
  int v28; // [rsp+30h] [rbp-39h]
  int *v29; // [rsp+38h] [rbp-31h]
  HSTRING v30; // [rsp+40h] [rbp-29h] BYREF
  HSTRING string; // [rsp+48h] [rbp-21h] BYREF
  int v32; // [rsp+50h] [rbp-19h] BYREF
  struct IXMLDOMElement *v33; // [rsp+58h] [rbp-11h] BYREF
  PCNZWCH v34[2]; // [rsp+60h] [rbp-9h] BYREF
  int v35; // [rsp+70h] [rbp+7h]
  PCNZWCH sourceString[2]; // [rsp+78h] [rbp+Fh] BYREF
  int v37; // [rsp+88h] [rbp+1Fh]
  wil::details::in1diag5 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v33 = 0;
  XMLApplicationNode = OSIntegration::DEH::PackagedComExtensionHandler::GetXMLApplicationNode(
                         (OSIntegration::DEH::PackagedComExtensionHandler *)this,
                         a2,
                         &v33);
  v8 = XMLApplicationNode;
  if ( XMLApplicationNode < 0 )
  {
    LODWORD(v25) = XMLApplicationNode;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xD38,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveApplicationIdAndDisplayName",
      "GetXMLApplicationNode(element, &applicationElement)",
      (const char *)v25,
      v27);
    if ( v33 )
      ((void (__fastcall *)(struct IXMLDOMElement *))v33->lpVtbl->Release)(v33);
    return v8;
  }
  *(_OWORD *)sourceString = 0;
  v37 = 0;
  LODWORD(v30) = 0;
  v9 = v33;
  AttributeValueStringFromElement = Common::Xml::GetAttributeValueStringFromElement(
                                      (Common::Xml *)v33,
                                      (struct IXMLDOMElement *)&stru_180231B98,
                                      (const unsigned __int16 *)sourceString,
                                      (struct Common::StringBuffer *)&v30,
                                      v24);
  v11 = AttributeValueStringFromElement;
  if ( AttributeValueStringFromElement < 0 )
  {
    LODWORD(v25) = AttributeValueStringFromElement;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xD41,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveApplicationIdAndDisplayName",
      "GetAttributeValueStringFromElement( applicationElement.get(), Internal::PackagedComConstants::idAttribute, idBuffe"
      "r, &idAttributeFound)",
      (const char *)v25,
      v27);
LABEL_24:
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)sourceString);
    wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v33);
    return v11;
  }
  *(_OWORD *)v34 = 0;
  v35 = 0;
  v32 = 0;
  LocalizedStringAttributeValueStringFromQuery = OSIntegration::Tools::GetLocalizedStringAttributeValueStringFromQuery(
                                                   this[5],
                                                   (const struct OSIntegration::Package *)L"*[local-name()='VisualElements']",
                                                   (const unsigned __int16 *)v9,
                                                   (struct IXMLDOMElement *)L"DisplayName",
                                                   (const unsigned __int16 *)v34,
                                                   (struct Common::StringBuffer *)&v32,
                                                   0,
                                                   v29);
  v11 = LocalizedStringAttributeValueStringFromQuery;
  if ( LocalizedStringAttributeValueStringFromQuery < 0 )
  {
    LODWORD(v26) = LocalizedStringAttributeValueStringFromQuery;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xD4C,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveApplicationIdAndDisplayName",
      "Tools::GetLocalizedStringAttributeValueStringFromQuery( _sourcePackage, Internal::PackagedComConstants::applicatio"
      "nVisualElementsChildXPath, applicationElement.get(), Internal::PackagedComConstants::displayNameAttribute, &displa"
      "yNameBuffer, &displayNameAttributeFound)",
      (const char *)v26,
      v28);
    if ( v34[1] )
      operator delete((void *)v34[1], v13);
    if ( sourceString[1] )
      operator delete((void *)sourceString[1], v13);
    if ( v9 )
      ((void (__fastcall *)(struct IXMLDOMElement *))v9->lpVtbl->Release)(v9);
    return v11;
  }
  if ( !(_DWORD)v30 || !v32 || !sourceString[1] || !v34[1] )
  {
    v8 = -2146958844;
    LODWORD(v26) = -2146958844;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xD63,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveApplicationIdAndDisplayName",
      "APPX_E_INVALID_MANIFEST",
      (const char *)v26,
      v28);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v34);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)sourceString);
    wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v33);
    return v8;
  }
  string = 0;
  v30 = 0;
  WindowsDeleteString(0);
  string = 0;
  v14 = WindowsCreateString(sourceString[1], (UINT32)sourceString[0], &string);
  v11 = v14;
  if ( v14 < 0 )
  {
    LODWORD(v26) = v14;
    v15 = "tempApplicationId.Set( idBuffer.GetChars(), idBuffer.GetLength())";
    v16 = 3416;
LABEL_23:
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveApplicationIdAndDisplayName",
      v15,
      (const char *)v26,
      v28);
    WindowsDeleteString(v30);
    v30 = 0;
    WindowsDeleteString(string);
    string = 0;
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v34);
    goto LABEL_24;
  }
  v17 = (UINT32)v34[0];
  v18 = v34[1];
  WindowsDeleteString(v30);
  v30 = 0;
  v19 = WindowsCreateString(v18, v17, &v30);
  v11 = v19;
  if ( v19 < 0 )
  {
    LODWORD(v26) = v19;
    v15 = "tempApplicationDisplayName.Set( displayNameBuffer.GetChars(), displayNameBuffer.GetLength())";
    v16 = 3420;
    goto LABEL_23;
  }
  v21 = string;
  string = 0;
  *a3 = v21;
  v22 = v30;
  v30 = 0;
  *a4 = v22;
  WindowsDeleteString(0);
  v30 = 0;
  WindowsDeleteString(string);
  if ( v34[1] )
    operator delete((void *)v34[1], v23);
  operator delete((void *)sourceString[1], v23);
  if ( v9 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v9->lpVtbl->Release)(v9);
  return 0;
}

```

## disassembly

```asm
0x18007ccec  push    rbp
0x18007ccee  push    rbx
0x18007ccef  push    rsi
0x18007ccf0  push    rdi
0x18007ccf1  push    r12
0x18007ccf3  push    r13
0x18007ccf5  push    r15
0x18007ccf7  lea     rbp, [rsp-27h]
0x18007ccfc  sub     rsp, 90h
0x18007cd03  mov     r15, r9
0x18007cd06  mov     r12, r8
0x18007cd09  mov     rsi, rcx
0x18007cd0c  xor     r13d, r13d
0x18007cd0f  mov     [rbp+57h+var_68], r13
0x18007cd13  lea     r8, [rbp+57h+var_68]; struct IXMLDOMElement **
0x18007cd17  call    ?GetXMLApplicationNode@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEAPEAU4@@Z; OSIntegration::DEH::PackagedComExtensionHandler::GetXMLApplicationNode(IXMLDOMElement *,IXMLDOMElement * *)
0x18007cd1c  mov     ebx, eax
0x18007cd1e  test    eax, eax
0x18007cd20  jns     short loc_18007CD6A
0x18007cd22  mov     rcx, [rbp+5Fh]; this
0x18007cd26  mov     dword ptr [rsp+0C0h+var_98], eax; char *
0x18007cd2a  lea     rax, aGetxmlapplicat; "GetXMLApplicationNode(element, &applica"...
0x18007cd31  mov     [rsp+0C0h+var_A0], rax; char *
0x18007cd36  lea     r9, aOsintegrationD_233; "OSIntegration::DEH::PackagedComExtensio"...
0x18007cd3d  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18007cd44  mov     edx, 0D38h; void *
0x18007cd49  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18007cd4e  nop
0x18007cd4f  mov     rcx, [rbp+57h+var_68]
0x18007cd53  test    rcx, rcx
0x18007cd56  jz      short loc_18007CD65
0x18007cd58  mov     rax, [rcx]
0x18007cd5b  mov     rax, [rax+10h]
0x18007cd5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cd64  nop
0x18007cd65  jmp     loc_18007D020
0x18007cd6a  xorps   xmm0, xmm0
0x18007cd6d  movups  xmmword ptr [rbp+57h+sourceString], xmm0
0x18007cd71  mov     [rbp+57h+var_38], r13d
0x18007cd75  mov     dword ptr [rbp+57h+var_80], r13d
0x18007cd79  lea     r9, [rbp+57h+var_80]; struct Common::StringBuffer *
0x18007cd7d  lea     r8, [rbp+57h+sourceString]; unsigned __int16 *
0x18007cd81  lea     rdx, stru_180231B98; struct IXMLDOMElement *
0x18007cd88  mov     rbx, [rbp+57h+var_68]
0x18007cd8c  mov     rcx, rbx; this
0x18007cd8f  call    ?GetAttributeValueStringFromElement@Xml@Common@@YAJPEAUIXMLDOMElement@@PEBGAEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromElement(IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)
0x18007cd94  mov     edi, eax
0x18007cd96  test    eax, eax
0x18007cd98  jns     short loc_18007CDCB
0x18007cd9a  mov     rcx, [rbp+5Fh]; this
0x18007cd9e  mov     dword ptr [rsp+0C0h+var_98], eax; char *
0x18007cda2  lea     rax, aGetattributeva_1; "GetAttributeValueStringFromElement( app"...
0x18007cda9  mov     [rsp+0C0h+var_A0], rax; char *
0x18007cdae  lea     r9, aOsintegrationD_233; "OSIntegration::DEH::PackagedComExtensio"...
0x18007cdb5  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18007cdbc  mov     edx, 0D41h; void *
0x18007cdc1  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18007cdc6  jmp     loc_18007CF57
0x18007cdcb  xorps   xmm0, xmm0
0x18007cdce  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x18007cdd2  mov     [rbp+57h+var_50], r13d
0x18007cdd6  mov     [rbp+57h+var_70], r13d
0x18007cdda  mov     [rsp+0C0h+var_90], r13; int
0x18007cddf  lea     rax, [rbp+57h+var_70]
0x18007cde3  mov     [rsp+0C0h+var_98], rax; struct Common::StringBuffer *
0x18007cde8  lea     rax, [rbp+57h+var_60]
0x18007cdec  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 *
0x18007cdf1  lea     r9, aDisplayname; "DisplayName"
0x18007cdf8  mov     r8, rbx; unsigned __int16 *
0x18007cdfb  lea     rdx, aLocalNameVisua; "*[local-name()='VisualElements']"
0x18007ce02  mov     rcx, [rsi+28h]; this
0x18007ce06  call    ?GetLocalizedStringAttributeValueStringFromQuery@Tools@OSIntegration@@YAJPEBVPackage@2@PEBGPEAUIXMLDOMElement@@1PEAVStringBuffer@Common@@PEAH4@Z; OSIntegration::Tools::GetLocalizedStringAttributeValueStringFromQuery(OSIntegration::Package const *,ushort const *,IXMLDOMElement *,ushort const *,Common::StringBuffer *,int *,int *)
0x18007ce0b  mov     edi, eax
0x18007ce0d  test    eax, eax
0x18007ce0f  jns     short loc_18007CE76
0x18007ce11  mov     rcx, [rbp+5Fh]; this
0x18007ce15  mov     dword ptr [rsp+0C0h+var_98], eax; char *
0x18007ce19  lea     rax, aToolsGetlocali; "Tools::GetLocalizedStringAttributeValue"...
0x18007ce20  mov     [rsp+0C0h+var_A0], rax; char *
0x18007ce25  lea     r9, aOsintegrationD_233; "OSIntegration::DEH::PackagedComExtensio"...
0x18007ce2c  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18007ce33  mov     edx, 0D4Ch; void *
0x18007ce38  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18007ce3d  nop
0x18007ce3e  mov     rcx, [rbp+57h+var_60+8]; void *
0x18007ce42  test    rcx, rcx
0x18007ce45  jz      short loc_18007CE4D
0x18007ce47  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18007ce4c  nop
0x18007ce4d  mov     rcx, [rbp+57h+sourceString+8]; void *
0x18007ce51  test    rcx, rcx
0x18007ce54  jz      short loc_18007CE5C
0x18007ce56  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18007ce5b  nop
0x18007ce5c  test    rbx, rbx
0x18007ce5f  jz      short loc_18007CE71
0x18007ce61  mov     rax, [rbx]
0x18007ce64  mov     rcx, rbx
0x18007ce67  mov     rax, [rax+10h]
0x18007ce6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ce70  nop
0x18007ce71  jmp     loc_18007CF6A
0x18007ce76  cmp     dword ptr [rbp+57h+var_80], r13d
0x18007ce7a  jz      loc_18007CFD1
0x18007ce80  cmp     [rbp+57h+var_70], r13d
0x18007ce84  jz      loc_18007CFD1
0x18007ce8a  cmp     [rbp+57h+sourceString+8], r13
0x18007ce8e  jz      loc_18007CFD1
0x18007ce94  cmp     [rbp+57h+var_60+8], r13
0x18007ce98  jz      loc_18007CFD1
0x18007ce9e  mov     [rbp+57h+string], r13
0x18007cea2  mov     [rbp+57h+var_80], r13
0x18007cea6  xor     ecx, ecx; string
0x18007cea8  call    cs:__imp_WindowsDeleteString
0x18007ceae  mov     [rbp+57h+string], r13
0x18007ceb2  lea     r8, [rbp+57h+string]; string
0x18007ceb6  mov     edx, dword ptr [rbp+57h+sourceString]; length
0x18007ceb9  mov     rcx, [rbp+57h+sourceString+8]; sourceString
0x18007cebd  call    cs:__imp_WindowsCreateString
0x18007cec3  mov     edi, eax
0x18007cec5  test    eax, eax
0x18007cec7  jns     short loc_18007CEDB
0x18007cec9  mov     dword ptr [rsp+0C0h+var_98], eax
0x18007cecd  lea     rax, aTempapplicatio_0; "tempApplicationId.Set( idBuffer.GetChar"...
0x18007ced4  mov     edx, 0D58h
0x18007ced9  jmp     short loc_18007CF15
0x18007cedb  mov     edi, dword ptr [rbp+57h+var_60]
0x18007cede  mov     rsi, [rbp+57h+var_60+8]
0x18007cee2  mov     rcx, [rbp+57h+var_80]; string
0x18007cee6  call    cs:__imp_WindowsDeleteString
0x18007ceec  mov     [rbp+57h+var_80], r13
0x18007cef0  lea     r8, [rbp+57h+var_80]; string
0x18007cef4  mov     edx, edi; length
0x18007cef6  mov     rcx, rsi; sourceString
0x18007cef9  call    cs:__imp_WindowsCreateString
0x18007ceff  mov     edi, eax
0x18007cf01  test    eax, eax
0x18007cf03  jns     short loc_18007CF71
0x18007cf05  mov     dword ptr [rsp+0C0h+var_98], eax; char *
0x18007cf09  lea     rax, aTempapplicatio; "tempApplicationDisplayName.Set( display"...
0x18007cf10  mov     edx, 0D5Ch; void *
0x18007cf15  mov     [rsp+0C0h+var_A0], rax; char *
0x18007cf1a  lea     r9, aOsintegrationD_233; "OSIntegration::DEH::PackagedComExtensio"...
0x18007cf21  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18007cf28  mov     rcx, [rbp+5Fh]; this
0x18007cf2c  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18007cf31  mov     rcx, [rbp+57h+var_80]; string
0x18007cf35  call    cs:__imp_WindowsDeleteString
0x18007cf3b  mov     [rbp+57h+var_80], r13
0x18007cf3f  mov     rcx, [rbp+57h+string]; string
0x18007cf43  call    cs:__imp_WindowsDeleteString
0x18007cf49  mov     [rbp+57h+string], r13
0x18007cf4d  lea     rcx, [rbp+57h+var_60]; this
0x18007cf51  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18007cf56  nop
0x18007cf57  lea     rcx, [rbp+57h+sourceString]; this
0x18007cf5b  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18007cf60  nop
0x18007cf61  lea     rcx, [rbp+57h+var_68]
0x18007cf65  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x18007cf6a  mov     eax, edi
0x18007cf6c  jmp     loc_18007D022
0x18007cf71  mov     rax, [rbp+57h+string]
0x18007cf75  mov     [rbp+57h+string], r13
0x18007cf79  mov     [r12], rax
0x18007cf7d  mov     rax, [rbp+57h+var_80]
0x18007cf81  mov     [rbp+57h+var_80], r13
0x18007cf85  mov     [r15], rax
0x18007cf88  xor     ecx, ecx; string
0x18007cf8a  call    cs:__imp_WindowsDeleteString
0x18007cf90  mov     [rbp+57h+var_80], r13
0x18007cf94  mov     rcx, [rbp+57h+string]; string
0x18007cf98  call    cs:__imp_WindowsDeleteString
0x18007cf9e  nop
0x18007cf9f  mov     rcx, [rbp+57h+var_60+8]; void *
0x18007cfa3  test    rcx, rcx
0x18007cfa6  jz      short loc_18007CFAE
0x18007cfa8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18007cfad  nop
0x18007cfae  mov     rcx, [rbp+57h+sourceString+8]; void *
0x18007cfb2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18007cfb7  nop
0x18007cfb8  test    rbx, rbx
0x18007cfbb  jz      short loc_18007CFCD
0x18007cfbd  mov     rax, [rbx]
0x18007cfc0  mov     rcx, rbx
0x18007cfc3  mov     rax, [rax+10h]
0x18007cfc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cfcc  nop
0x18007cfcd  xor     eax, eax
0x18007cfcf  jmp     short loc_18007D022
0x18007cfd1  mov     rcx, [rbp+5Fh]; this
0x18007cfd5  mov     ebx, 80080204h
0x18007cfda  mov     dword ptr [rsp+0C0h+var_98], ebx; char *
0x18007cfde  lea     rax, aAppxEInvalidMa; "APPX_E_INVALID_MANIFEST"
0x18007cfe5  mov     [rsp+0C0h+var_A0], rax; char *
0x18007cfea  lea     r9, aOsintegrationD_233; "OSIntegration::DEH::PackagedComExtensio"...
0x18007cff1  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18007cff8  mov     edx, 0D63h; void *
0x18007cffd  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18007d002  nop
0x18007d003  lea     rcx, [rbp+57h+var_60]; this
0x18007d007  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18007d00c  nop
0x18007d00d  lea     rcx, [rbp+57h+sourceString]; this
0x18007d011  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18007d016  nop
0x18007d017  lea     rcx, [rbp+57h+var_68]
0x18007d01b  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x18007d020  mov     eax, ebx
0x18007d022  add     rsp, 90h
0x18007d029  pop     r15
0x18007d02b  pop     r13
0x18007d02d  pop     r12
0x18007d02f  pop     rdi
0x18007d030  pop     rsi
0x18007d031  pop     rbx
0x18007d032  pop     rbp
0x18007d033  retn
```
