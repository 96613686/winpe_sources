# OSIntegration::DEH::Internal::PackagedServiceExtensionHelper::HelpParse(OSIntegration::Package const *,IXMLDOMElement const *,IXMLDOMElement *)

- ea: `0x18001db48`
- end: `0x18001e3eb`
- name: `?HelpParse@PackagedServiceExtensionHelper@Internal@DEH@OSIntegration@@AEAAXPEBVPackage@4@PEBUIXMLDOMElement@@PEAU6@@Z`
- size: `2211`
- prototype: `void __fastcall(OSIntegration::DEH::Internal::PackagedServiceExtensionHelper *__hidden this, const struct OSIntegration::Package *, const struct IXMLDOMElement *, struct IXMLDOMElement *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001da0c`

## callees

- `0x180006970`
- `0x180009dc0`
- `0x180011020`
- `0x180012da0`
- `0x180014260`
- `0x180014860`
- `0x18001d7f0`
- `0x18001db48`
- `0x18001e3f4`
- `0x18001e42c`
- `0x18001e6f0`
- `0x180064a88`
- `0x180085454`
- `0x1800af1bc`
- `0x1801ac010`

## string_xrefs

- `0x18001df0b`: `networkService`
- `0x18001df1e`: `NT AUTHORITY\NetworkService`
- `0x18001df27`: `localService`
- `0x18001dc33`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x18001dc60`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x18001dc9a`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x18001dcc7`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x18001dd27`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x18001dd7e`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x18001ddaa`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x18001dde4`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x18001de11`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x18001dec8`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x18001def5`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x18001dfa0`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x18001dfec`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x18001e019`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x18001e064`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x18001e0a0`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x18001e0ef`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x18001e12b`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x18001e17a`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x18001e1ad`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x18001e1e0`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x18001e227`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x18001e254`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x18001e3ba`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x18001e3d9`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x18001df3a`: `NT AUTHORITY\LocalService`

## pseudocode

```c
void __fastcall OSIntegration::DEH::Internal::PackagedServiceExtensionHelper::HelpParse(
        OSIntegration::DEH::Internal::PackagedServiceExtensionHelper *this,
        const struct OSIntegration::Package *a2,
        struct IXMLDOMElement *a3,
        struct IXMLDOMElement *a4)
{
  __int64 v8; // rdi
  int AttributeValueStringFromElement; // eax
  int v10; // eax
  struct Common::StringBuffer *v11; // r9
  __int64 v12; // rax
  int v13; // eax
  int inserted; // eax
  int appended; // eax
  int v16; // eax
  unsigned __int16 *v17; // r14
  int v18; // eax
  unsigned __int16 *v19; // r15
  const unsigned __int16 *v20; // rdx
  const struct std::nothrow_t *v21; // rdx
  int v22; // eax
  int v23; // eax
  int v24; // eax
  struct IXMLDOMElement **v25; // r9
  int XMLElementFromQuery; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int AttributeValueStringFromQuery; // eax
  const struct std::nothrow_t *v34; // rdx
  const struct std::nothrow_t *v35; // rdx
  struct IXMLDOMElementVtbl *lpVtbl; // rcx
  void *v37; // rcx
  int *v38; // [rsp+20h] [rbp-E0h]
  int *v39; // [rsp+20h] [rbp-E0h]
  int *v40; // [rsp+20h] [rbp-E0h]
  int *v41; // [rsp+20h] [rbp-E0h]
  int *v42; // [rsp+20h] [rbp-E0h]
  int *v43; // [rsp+20h] [rbp-E0h]
  int *v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  int *v47; // [rsp+28h] [rbp-D8h]
  struct IXMLDOMElement v48; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v49[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v50; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v51; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v52; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v53[3]; // [rsp+60h] [rbp-A0h] BYREF
  void *v54[2]; // [rsp+78h] [rbp-88h] BYREF
  int v55; // [rsp+88h] [rbp-78h]
  void *v56[2]; // [rsp+90h] [rbp-70h] BYREF
  int v57; // [rsp+A0h] [rbp-60h]
  void *v58[2]; // [rsp+A8h] [rbp-58h] BYREF
  int v59; // [rsp+B8h] [rbp-48h]
  _QWORD v60[3]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v61[2]; // [rsp+D8h] [rbp-28h] BYREF
  int v62; // [rsp+E8h] [rbp-18h]
  unsigned __int16 *v63[2]; // [rsp+F0h] [rbp-10h] BYREF
  int v64; // [rsp+100h] [rbp+0h]
  _QWORD v65[4]; // [rsp+108h] [rbp+8h] BYREF
  __int128 v66; // [rsp+128h] [rbp+28h]
  int v67; // [rsp+138h] [rbp+38h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]
  unsigned __int16 v69; // [rsp+190h] [rbp+90h] BYREF
  int v70; // [rsp+198h] [rbp+98h] BYREF
  unsigned __int16 *v71; // [rsp+1A0h] [rbp+A0h]

  v71 = (unsigned __int16 *)a3;
  *(_OWORD *)v58 = 0;
  v59 = 0;
  v66 = 0;
  v67 = 0;
  *(_OWORD *)v61 = 0;
  v62 = 0;
  *(_OWORD *)v63 = 0;
  v64 = 0;
  *(_OWORD *)v56 = 0;
  v57 = 0;
  *(_OWORD *)v54 = 0;
  v55 = 0;
  *(_OWORD *)v49 = 0;
  v50 = 0;
  v53[1] = v49;
  v53[0] = &Common::StringBufferBuilder::`vftable';
  v53[2] = v49;
  v51 = 0;
  v52 = 0;
  v70 = 0;
  v8 = *((_QWORD *)a2 + 3);
  v65[3] = v8;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  AttributeValueStringFromElement = Common::Xml::GetAttributeValueStringFromElement(
                                      (Common::Xml *)a4,
                                      (struct IXMLDOMElement *)&Appx::Packaging::Manifest::AttributeNameWithoutPrefix::Name,
                                      (const unsigned __int16 *)this,
                                      (struct Common::StringBuffer *)&v70,
                                      v38);
  if ( AttributeValueStringFromElement < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD4,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)(unsigned int)AttributeValueStringFromElement,
      (int)v39);
  if ( !v70 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD5,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)0x80080204LL,
      (int)v39);
  v10 = Common::Xml::GetAttributeValueStringFromElement(
          (Common::Xml *)a3,
          (struct IXMLDOMElement *)&Appx::Packaging::Manifest::AttributeNameWithoutPrefix::Executable,
          (const unsigned __int16 *)v58,
          (struct Common::StringBuffer *)&v70,
          v39);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)(unsigned int)v10,
      (int)v40);
  if ( !v70 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)0x80080204LL,
      (int)v40);
  if ( *((_QWORD *)a2 + 24) )
  {
    v12 = 184;
  }
  else if ( !*((_BYTE *)a2 + 408) || (v12 = 136, !*((_BYTE *)a2 + 415)) )
  {
    v12 = 88;
  }
  v13 = OSIntegration::Tools::ConcatenatePaths(
          (const struct OSIntegration::Package *)((char *)a2 + v12),
          (const struct Common::COMMON_STRING *)v58,
          (OSIntegration::DEH::Internal::PackagedServiceExtensionHelper *)((char *)this + 24),
          v11);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE2,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)(unsigned int)v13,
      (int)v40);
  v60[1] = (char *)this + 24;
  v60[0] = &Common::StringBufferBuilder::`vftable';
  v60[2] = (char *)this + 24;
  v69 = 34;
  inserted = Common::StringBuilder::InsertChars((Common::StringBuilder *)v60, 0, &v69, 1u);
  if ( inserted < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE6,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)(unsigned int)inserted,
      (int)v40);
  appended = Common::StringBuilder::AppendChar((Common::StringBuilder *)v60, 0x22u);
  if ( appended < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE7,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)(unsigned int)appended,
      (int)v40);
  v16 = Common::Xml::GetAttributeValueStringFromElement(
          (Common::Xml *)a4,
          (struct IXMLDOMElement *)&Appx::Packaging::Manifest::AttributeNameWithoutPrefix::StartupType,
          (const unsigned __int16 *)v61,
          (struct Common::StringBuffer *)&v70,
          v40);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEE,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)(unsigned int)v16,
      (int)v41);
  if ( !v70 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEF,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)0x80080204LL,
      (int)v41);
  v17 = v61[1];
  if ( Common::String::Equals(v61[1], L"manual") )
  {
    *((_DWORD *)this + 42) = 3;
    goto LABEL_34;
  }
  if ( !Common::String::Equals(v17, L"auto") )
  {
    if ( Common::String::Equals(v17, L"disabled") )
    {
      *((_DWORD *)this + 42) = 4;
      goto LABEL_34;
    }
    if ( !Common::String::Equals(v17, L"delayedStart") )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x104,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
        (const char *)0x80080204LL,
        (int)v41);
    *((_BYTE *)this + 172) = 1;
  }
  *((_DWORD *)this + 42) = 2;
LABEL_34:
  v18 = Common::Xml::GetAttributeValueStringFromElement(
          (Common::Xml *)a4,
          (struct IXMLDOMElement *)&Appx::Packaging::Manifest::AttributeNameWithoutPrefix::StartAccount,
          (const unsigned __int16 *)v63,
          (struct Common::StringBuffer *)&v70,
          v41);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10C,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)(unsigned int)v18,
      (int)v42);
  if ( !v70 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10D,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)0x80080204LL,
      (int)v42);
  v19 = v63[1];
  if ( Common::String::Equals(v63[1], L"networkService") )
  {
    v20 = L"NT AUTHORITY\\NetworkService";
LABEL_42:
    Common::StringBuffer::SetValueFromString(
      (OSIntegration::DEH::Internal::PackagedServiceExtensionHelper *)((char *)this + 72),
      v20);
    goto LABEL_45;
  }
  if ( Common::String::Equals(v19, L"localService") )
  {
    v20 = L"NT AUTHORITY\\LocalService";
    goto LABEL_42;
  }
  if ( !Common::String::Equals(v19, L"localSystem") )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x11F,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)0x80080204LL,
      (int)v42);
  operator delete(*((void **)this + 10), v21);
  *((_QWORD *)this + 10) = 0;
  *((_DWORD *)this + 18) = 0;
  *((_DWORD *)this + 22) = 0;
LABEL_45:
  v22 = Common::Xml::GetAttributeValueStringFromElement(
          (Common::Xml *)a4,
          (struct IXMLDOMElement *)&Appx::Packaging::Manifest::AttributeNameWithoutPrefix::Arguments,
          (const unsigned __int16 *)v56,
          (struct Common::StringBuffer *)&v70,
          v42);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x129,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)(unsigned int)v22,
      (int)v43);
  if ( v70 )
  {
    v65[1] = (char *)this + 24;
    v65[0] = &Common::StringBufferBuilder::`vftable';
    v65[2] = (char *)this + 24;
    v23 = Common::StringBuilder::AppendString(
            (Common::StringBuilder *)v65,
            (const struct Common::COMMON_STRING *)&unk_1801AD220);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12E,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
        (const char *)(unsigned int)v23,
        (int)v43);
    v24 = Common::StringBuilder::AppendString((Common::StringBuilder *)v65, (const struct Common::COMMON_STRING *)v56);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12F,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
        (const char *)(unsigned int)v24,
        (int)v43);
  }
  v48.lpVtbl = 0;
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v48);
  XMLElementFromQuery = Common::Xml::GetXMLElementFromQuery(
                          (OLECHAR *)L"ancestor::*[local-name()='Application']/*[local-name()='VisualElements']",
                          v71,
                          &v48,
                          v25);
  if ( XMLElementFromQuery < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x136,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)(unsigned int)XMLElementFromQuery,
      (int)v43);
  v27 = Common::Xml::GetAttributeValueStringFromElement(
          (Common::Xml *)v48.lpVtbl,
          (struct IXMLDOMElement *)&Appx::Packaging::Manifest::AttributeNameWithoutPrefix::DisplayName,
          (const unsigned __int16 *)this + 24,
          (struct Common::StringBuffer *)&v70,
          v43);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13D,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)(unsigned int)v27,
      (int)v44);
  if ( v8 )
  {
    if ( (*(int (__fastcall **)(__int64, _QWORD, unsigned __int16 **))(*(_QWORD *)v8 + 40LL))(
           v8,
           *((_QWORD *)this + 7),
           &v51) >= 0 )
    {
      v28 = Common::StringBuffer::SetValueFromString(
              (OSIntegration::DEH::Internal::PackagedServiceExtensionHelper *)((char *)this + 48),
              v51);
      if ( v28 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x144,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
          (const char *)(unsigned int)v28,
          (int)v44);
    }
  }
  v29 = Common::Xml::GetAttributeValueStringFromElement(
          (Common::Xml *)v48.lpVtbl,
          (struct IXMLDOMElement *)&Appx::Packaging::Manifest::AttributeNameWithoutPrefix::Description,
          (const unsigned __int16 *)this + 48,
          (struct Common::StringBuffer *)&v70,
          v44);
  if ( v29 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14D,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)(unsigned int)v29,
      v45);
  if ( v8 )
  {
    if ( (*(int (__fastcall **)(__int64, _QWORD, unsigned __int16 **))(*(_QWORD *)v8 + 40LL))(
           v8,
           *((_QWORD *)this + 13),
           &v52) >= 0 )
    {
      v30 = Common::StringBuffer::SetValueFromString(
              (OSIntegration::DEH::Internal::PackagedServiceExtensionHelper *)((char *)this + 96),
              v52);
      if ( v30 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x154,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
          (const char *)(unsigned int)v30,
          v45);
    }
  }
  v31 = Common::StringBuffer::SetValueFromString(
          (OSIntegration::DEH::Internal::PackagedServiceExtensionHelper *)((char *)this + 176),
          *((const unsigned __int16 **)a2 + 28));
  if ( v31 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x159,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)(unsigned int)v31,
      v45);
  v32 = Common::StringBuffer::SetValueFromString(
          (OSIntegration::DEH::Internal::PackagedServiceExtensionHelper *)((char *)this + 232),
          *((const unsigned __int16 **)a2 + 34));
  if ( v32 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15A,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)(unsigned int)v32,
      v45);
  AttributeValueStringFromQuery = Common::Xml::GetAttributeValueStringFromQuery(
                                    (OLECHAR *)L"ancestor::*[local-name()='Application']",
                                    (const unsigned __int16 *)a4,
                                    (struct IXMLDOMElement *)&Appx::Packaging::Manifest::AttributeNameWithoutPrefix::Id,
                                    (const unsigned __int16 *)v54,
                                    (struct Common::StringBuffer *)&v70,
                                    v47);
  if ( AttributeValueStringFromQuery < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x163,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)(unsigned int)AttributeValueStringFromQuery,
      v46);
  if ( !v70 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x164,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)0x80080204LL,
      v46);
  operator delete(v49[1], v34);
  v49[1] = 0;
  LODWORD(v49[0]) = 0;
  v50 = 0;
  Common::StringBuilder::AppendString(
    (Common::StringBuilder *)v53,
    (const struct OSIntegration::Package *)((char *)a2 + 240));
  Common::StringBuilder::AppendString(
    (Common::StringBuilder *)v53,
    (const struct Common::COMMON_STRING *)&unk_1801AD160);
  Common::StringBuilder::AppendString((Common::StringBuilder *)v53, (const struct Common::COMMON_STRING *)v54);
  Common::StringBuffer::SetValueFromString(
    (OSIntegration::DEH::Internal::PackagedServiceExtensionHelper *)((char *)this + 200),
    v49[1]);
  *((_DWORD *)this + 56) = *((_DWORD *)a2 + 94);
  OSIntegration::DEH::Internal::PackagedServiceTriggerData::ParseFromServiceElement(
    (OSIntegration::DEH::Internal::PackagedServiceExtensionHelper *)((char *)this + 256),
    a4,
    a2);
  lpVtbl = v48.lpVtbl;
  if ( v48.lpVtbl )
  {
    v48.lpVtbl = 0;
    (*((void (__fastcall **)(struct IXMLDOMElementVtbl *))lpVtbl->QueryInterface + 2))(lpVtbl);
  }
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v49[1] )
    operator delete(v49[1], v35);
  if ( v54[1] )
    operator delete(v54[1], v35);
  if ( v56[1] )
    operator delete(v56[1], v35);
  if ( v19 )
    operator delete(v19, v35);
  if ( v17 )
    operator delete(v17, v35);
  v37 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( v37 )
    operator delete(v37, v35);
  if ( v58[1] )
    operator delete(v58[1], v35);
}

```

## disassembly

```asm
0x18001db48  mov     rax, rsp
0x18001db4b  mov     [rax+20h], rbx
0x18001db4f  mov     [rax+18h], r8
0x18001db53  push    rbp
0x18001db54  push    rsi
0x18001db55  push    rdi
0x18001db56  push    r12
0x18001db58  push    r13
0x18001db5a  push    r14
0x18001db5c  push    r15
0x18001db5e  lea     rbp, [rsp-50h]
0x18001db63  sub     rsp, 150h
0x18001db6a  movaps  xmmword ptr [rax-48h], xmm6
0x18001db6e  mov     r13, r9
0x18001db71  mov     r14, r8
0x18001db74  mov     rsi, rdx
0x18001db77  mov     rbx, rcx
0x18001db7a  xorps   xmm0, xmm0
0x18001db7d  movups  xmmword ptr [rbp+80h+var_D8], xmm0
0x18001db81  xor     r15d, r15d
0x18001db84  mov     [rbp+80h+var_C8], r15d
0x18001db88  xorps   xmm6, xmm6
0x18001db8b  movups  [rbp+80h+var_58], xmm6
0x18001db8f  mov     [rbp+80h+var_48], r15d
0x18001db93  movups  xmmword ptr [rbp+80h+var_A8], xmm0
0x18001db97  mov     [rbp+80h+var_98], r15d
0x18001db9b  movups  xmmword ptr [rbp+80h+var_90], xmm0
0x18001db9f  mov     [rbp+80h+var_80], r15d
0x18001dba3  movups  xmmword ptr [rbp+80h+var_F0], xmm0
0x18001dba7  mov     [rbp+80h+var_E0], r15d
0x18001dbab  movups  xmmword ptr [rsp+180h+var_108], xmm0
0x18001dbb0  mov     [rbp+80h+var_F8], r15d
0x18001dbb4  movups  xmmword ptr [rsp+180h+var_148], xmm0
0x18001dbb9  mov     [rsp+180h+var_138], r15d
0x18001dbbe  lea     rax, [rsp+180h+var_148]
0x18001dbc3  mov     [rsp+180h+var_118], rax
0x18001dbc8  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x18001dbcf  mov     [rsp+180h+var_120], rax
0x18001dbd4  lea     rax, [rsp+180h+var_148]
0x18001dbd9  mov     [rsp+180h+var_110], rax
0x18001dbde  mov     [rsp+180h+var_130], r15
0x18001dbe3  mov     [rsp+180h+var_128], r15
0x18001dbe8  mov     [rbp+80h+arg_8], r15d
0x18001dbef  mov     rdi, [rdx+18h]
0x18001dbf3  mov     [rbp+80h+var_60], rdi
0x18001dbf7  test    rdi, rdi
0x18001dbfa  jz      short loc_18001DC0C
0x18001dbfc  mov     rax, [rdi]
0x18001dbff  mov     rcx, rdi
0x18001dc02  mov     rax, [rax+8]
0x18001dc06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc0b  nop
0x18001dc0c  lea     r9, [rbp+80h+arg_8]; struct Common::StringBuffer *
0x18001dc13  mov     r8, rbx; unsigned __int16 *
0x18001dc16  lea     rdx, ?Name@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; struct IXMLDOMElement *
0x18001dc1d  mov     rcx, r13; this
0x18001dc20  call    ?GetAttributeValueStringFromElement@Xml@Common@@YAJPEAUIXMLDOMElement@@PEBGAEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromElement(IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)
0x18001dc25  mov     rcx, [rbp+88h]; this
0x18001dc2c  test    eax, eax
0x18001dc2e  jns     short loc_18001DC45
0x18001dc30  mov     r9d, eax; char *
0x18001dc33  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18001dc3a  mov     edx, 0D4h; void *
0x18001dc3f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001dc45  cmp     [rbp+80h+arg_8], r15d
0x18001dc4c  setnz   al
0x18001dc4f  mov     rcx, [rbp+88h]; this
0x18001dc56  test    al, al
0x18001dc58  jnz     short loc_18001DC72
0x18001dc5a  mov     r9d, 80080204h; char *
0x18001dc60  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18001dc67  mov     edx, 0D5h; void *
0x18001dc6c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001dc72  lea     r9, [rbp+80h+arg_8]; struct Common::StringBuffer *
0x18001dc79  lea     r8, [rbp+80h+var_D8]; unsigned __int16 *
0x18001dc7d  lea     rdx, ?Executable@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; struct IXMLDOMElement *
0x18001dc84  mov     rcx, r14; this
0x18001dc87  call    ?GetAttributeValueStringFromElement@Xml@Common@@YAJPEAUIXMLDOMElement@@PEBGAEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromElement(IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)
0x18001dc8c  mov     rcx, [rbp+88h]; this
0x18001dc93  test    eax, eax
0x18001dc95  jns     short loc_18001DCAC
0x18001dc97  mov     r9d, eax; char *
0x18001dc9a  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18001dca1  mov     edx, 0DCh; void *
0x18001dca6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001dcac  cmp     [rbp+80h+arg_8], r15d
0x18001dcb3  setnz   al
0x18001dcb6  mov     rcx, [rbp+88h]; this
0x18001dcbd  test    al, al
0x18001dcbf  jnz     short loc_18001DCD9
0x18001dcc1  mov     r9d, 80080204h; char *
0x18001dcc7  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18001dcce  mov     edx, 0DDh; void *
0x18001dcd3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001dcd9  cmp     [rsi+0C0h], r15
0x18001dce0  jz      short loc_18001DCE9
0x18001dce2  mov     eax, 0B8h
0x18001dce7  jmp     short loc_18001DD05
0x18001dce9  cmp     [rsi+198h], r15b
0x18001dcf0  jz      short loc_18001DD00
0x18001dcf2  cmp     [rsi+19Fh], r15b
0x18001dcf9  mov     eax, 88h
0x18001dcfe  jnz     short loc_18001DD05
0x18001dd00  mov     eax, 58h ; 'X'
0x18001dd05  lea     r12, [rbx+18h]
0x18001dd09  lea     rcx, [rax+rsi]; this
0x18001dd0d  mov     r8, r12; struct Common::COMMON_STRING *
0x18001dd10  lea     rdx, [rbp+80h+var_D8]; struct Common::COMMON_STRING *
0x18001dd14  call    ?ConcatenatePaths@Tools@OSIntegration@@YAJPEBUCOMMON_STRING@Common@@0AEAVStringBuffer@4@@Z; OSIntegration::Tools::ConcatenatePaths(Common::COMMON_STRING const *,Common::COMMON_STRING const *,Common::StringBuffer &)
0x18001dd19  mov     rcx, [rbp+88h]; this
0x18001dd20  test    eax, eax
0x18001dd22  jns     short loc_18001DD39
0x18001dd24  mov     r9d, eax; char *
0x18001dd27  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18001dd2e  mov     edx, 0E2h; void *
0x18001dd33  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001dd39  mov     [rbp+80h+var_B8], r12
0x18001dd3d  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x18001dd44  mov     [rbp+80h+var_C0], rax
0x18001dd48  mov     [rbp+80h+var_B0], r12
0x18001dd4c  mov     r14d, 22h ; '"'
0x18001dd52  mov     [rbp+80h+arg_0], r14w
0x18001dd5a  lea     r9d, [r14-21h]; unsigned int
0x18001dd5e  lea     r8, [rbp+80h+arg_0]; unsigned __int16 *
0x18001dd65  xor     edx, edx; unsigned int
0x18001dd67  lea     rcx, [rbp+80h+var_C0]; this
0x18001dd6b  call    ?InsertChars@StringBuilder@Common@@QEAAJKPEBGK@Z; Common::StringBuilder::InsertChars(ulong,ushort const *,ulong)
0x18001dd70  mov     rcx, [rbp+88h]; this
0x18001dd77  test    eax, eax
0x18001dd79  jns     short loc_18001DD90
0x18001dd7b  mov     r9d, eax; char *
0x18001dd7e  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18001dd85  mov     edx, 0E6h; void *
0x18001dd8a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001dd90  mov     edx, r14d; unsigned __int16
0x18001dd93  lea     rcx, [rbp+80h+var_C0]; this
0x18001dd97  call    ?AppendChar@StringBuilder@Common@@QEAAJG@Z; Common::StringBuilder::AppendChar(ushort)
0x18001dd9c  mov     rcx, [rbp+88h]; this
0x18001dda3  test    eax, eax
0x18001dda5  jns     short loc_18001DDBC
0x18001dda7  mov     r9d, eax; char *
0x18001ddaa  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18001ddb1  mov     edx, 0E7h; void *
0x18001ddb6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ddbc  lea     r9, [rbp+80h+arg_8]; struct Common::StringBuffer *
0x18001ddc3  lea     r8, [rbp+80h+var_A8]; unsigned __int16 *
0x18001ddc7  lea     rdx, ?StartupType@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; struct IXMLDOMElement *
0x18001ddce  mov     rcx, r13; this
0x18001ddd1  call    ?GetAttributeValueStringFromElement@Xml@Common@@YAJPEAUIXMLDOMElement@@PEBGAEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromElement(IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)
0x18001ddd6  mov     rcx, [rbp+88h]; this
0x18001dddd  test    eax, eax
0x18001dddf  jns     short loc_18001DDF6
0x18001dde1  mov     r9d, eax; char *
0x18001dde4  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18001ddeb  mov     edx, 0EEh; void *
0x18001ddf0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ddf6  cmp     [rbp+80h+arg_8], r15d
0x18001ddfd  setnz   al
0x18001de00  mov     rcx, [rbp+88h]; this
0x18001de07  test    al, al
0x18001de09  jnz     short loc_18001DE23
0x18001de0b  mov     r9d, 80080204h; char *
0x18001de11  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18001de18  mov     edx, 0EFh; void *
0x18001de1d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001de23  mov     r14, [rbp+80h+var_A8+8]
0x18001de27  lea     rdx, ?StartupTypeManual@Value@Packaging@Appx@@3QBGB; "manual"
0x18001de2e  mov     rcx, r14; unsigned __int16 *
0x18001de31  call    ?Equals@String@Common@@SA_NPEBG0@Z; Common::String::Equals(ushort const *,ushort const *)
0x18001de36  test    al, al
0x18001de38  jz      short loc_18001DE46
0x18001de3a  mov     dword ptr [rbx+0A8h], 3
0x18001de44  jmp     short loc_18001DEA0
0x18001de46  lea     rdx, ?StartupTypeAuto@Value@Packaging@Appx@@3QBGB; "auto"
0x18001de4d  mov     rcx, r14; unsigned __int16 *
0x18001de50  call    ?Equals@String@Common@@SA_NPEBG0@Z; Common::String::Equals(ushort const *,ushort const *)
0x18001de55  test    al, al
0x18001de57  jnz     short loc_18001DE96
0x18001de59  lea     rdx, ?StartupTypeDisabled@Value@Packaging@Appx@@3QBGB; "disabled"
0x18001de60  mov     rcx, r14; unsigned __int16 *
0x18001de63  call    ?Equals@String@Common@@SA_NPEBG0@Z; Common::String::Equals(ushort const *,ushort const *)
0x18001de68  test    al, al
0x18001de6a  jz      short loc_18001DE78
0x18001de6c  mov     dword ptr [rbx+0A8h], 4
0x18001de76  jmp     short loc_18001DEA0
0x18001de78  lea     rdx, ?StartupTypeDelayed@Value@Packaging@Appx@@3QBGB; "delayedStart"
0x18001de7f  mov     rcx, r14; unsigned __int16 *
0x18001de82  call    ?Equals@String@Common@@SA_NPEBG0@Z; Common::String::Equals(ushort const *,ushort const *)
0x18001de87  test    al, al
0x18001de89  jz      loc_18001E3CC
0x18001de8f  mov     byte ptr [rbx+0ACh], 1
0x18001de96  mov     dword ptr [rbx+0A8h], 2
0x18001dea0  lea     r9, [rbp+80h+arg_8]; struct Common::StringBuffer *
0x18001dea7  lea     r8, [rbp+80h+var_90]; unsigned __int16 *
0x18001deab  lea     rdx, ?StartAccount@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; struct IXMLDOMElement *
0x18001deb2  mov     rcx, r13; this
0x18001deb5  call    ?GetAttributeValueStringFromElement@Xml@Common@@YAJPEAUIXMLDOMElement@@PEBGAEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromElement(IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)
0x18001deba  mov     rcx, [rbp+88h]; this
0x18001dec1  test    eax, eax
0x18001dec3  jns     short loc_18001DEDA
0x18001dec5  mov     r9d, eax; char *
0x18001dec8  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18001decf  mov     edx, 10Ch; void *
0x18001ded4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001deda  cmp     [rbp+80h+arg_8], r15d
0x18001dee1  setnz   al
0x18001dee4  mov     rcx, [rbp+88h]; this
0x18001deeb  test    al, al
0x18001deed  jnz     short loc_18001DF07
0x18001deef  mov     r9d, 80080204h; char *
0x18001def5  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18001defc  mov     edx, 10Dh; void *
0x18001df01  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001df07  mov     r15, [rbp+80h+var_90+8]
0x18001df0b  lea     rdx, ?StartAccountNetworkService@Value@Packaging@Appx@@3QBGB; "networkService"
0x18001df12  mov     rcx, r15; unsigned __int16 *
0x18001df15  call    ?Equals@String@Common@@SA_NPEBG0@Z; Common::String::Equals(ushort const *,ushort const *)
0x18001df1a  test    al, al
0x18001df1c  jz      short loc_18001DF27
0x18001df1e  lea     rdx, aNtAuthorityNet; "NT AUTHORITY\\NetworkService"
0x18001df25  jmp     short loc_18001DF41
0x18001df27  lea     rdx, ?StartAccountLocalService@Value@Packaging@Appx@@3QBGB; "localService"
0x18001df2e  mov     rcx, r15; unsigned __int16 *
0x18001df31  call    ?Equals@String@Common@@SA_NPEBG0@Z; Common::String::Equals(ushort const *,ushort const *)
0x18001df36  test    al, al
0x18001df38  jz      short loc_18001DF4C
0x18001df3a  lea     rdx, aNtAuthorityLoc; "NT AUTHORITY\\LocalService"
0x18001df41  lea     rcx, [rbx+48h]; this
0x18001df45  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18001df4a  jmp     short loc_18001DF78
0x18001df4c  lea     rdx, ?StartAccountLocalSystem@Value@Packaging@Appx@@3QBGB; "localSystem"
0x18001df53  mov     rcx, r15; unsigned __int16 *
0x18001df56  call    ?Equals@String@Common@@SA_NPEBG0@Z; Common::String::Equals(ushort const *,ushort const *)
0x18001df5b  test    al, al
0x18001df5d  jz      loc_18001E3AD
0x18001df63  mov     rcx, [rbx+50h]; void *
0x18001df67  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001df6c  xor     eax, eax
0x18001df6e  mov     [rbx+50h], rax
0x18001df72  mov     [rbx+48h], eax
0x18001df75  mov     [rbx+58h], eax
0x18001df78  lea     r9, [rbp+80h+arg_8]; struct Common::StringBuffer *
0x18001df7f  lea     r8, [rbp+80h+var_F0]; unsigned __int16 *
0x18001df83  lea     rdx, ?Arguments@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; struct IXMLDOMElement *
0x18001df8a  mov     rcx, r13; this
0x18001df8d  call    ?GetAttributeValueStringFromElement@Xml@Common@@YAJPEAUIXMLDOMElement@@PEBGAEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromElement(IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)
0x18001df92  mov     rcx, [rbp+88h]; this
0x18001df99  test    eax, eax
0x18001df9b  jns     short loc_18001DFB2
0x18001df9d  mov     r9d, eax; char *
0x18001dfa0  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18001dfa7  mov     edx, 129h; void *
0x18001dfac  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001dfb2  cmp     [rbp+80h+arg_8], 0
0x18001dfb9  jz      short loc_18001E02B
0x18001dfbb  mov     [rbp+80h+var_70], r12
0x18001dfbf  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x18001dfc6  mov     [rbp+80h+var_78], rax
0x18001dfca  mov     [rbp+80h+var_68], r12
0x18001dfce  lea     rdx, unk_1801AD220; struct Common::COMMON_STRING *
0x18001dfd5  lea     rcx, [rbp+80h+var_78]; this
0x18001dfd9  call    ?AppendString@StringBuilder@Common@@QEAAJPEBUCOMMON_STRING@2@@Z; Common::StringBuilder::AppendString(Common::COMMON_STRING const *)
0x18001dfde  mov     rcx, [rbp+88h]; this
0x18001dfe5  test    eax, eax
0x18001dfe7  jns     short loc_18001DFFE
0x18001dfe9  mov     r9d, eax; char *
0x18001dfec  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18001dff3  mov     edx, 12Eh; void *
0x18001dff8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001dffe  lea     rdx, [rbp+80h+var_F0]; struct Common::COMMON_STRING *
0x18001e002  lea     rcx, [rbp+80h+var_78]; this
0x18001e006  call    ?AppendString@StringBuilder@Common@@QEAAJPEBUCOMMON_STRING@2@@Z; Common::StringBuilder::AppendString(Common::COMMON_STRING const *)
0x18001e00b  mov     rcx, [rbp+88h]; this
0x18001e012  test    eax, eax
0x18001e014  jns     short loc_18001E02B
0x18001e016  mov     r9d, eax; char *
0x18001e019  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18001e020  mov     edx, 12Fh; void *
0x18001e025  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e02b  mov     [rsp+180h+var_150.lpVtbl], 0
0x18001e034  lea     rcx, [rsp+180h+var_150]
0x18001e039  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x18001e03e  lea     r8, [rsp+180h+var_150]; struct IXMLDOMElement *
0x18001e043  mov     rdx, [rbp+80h+arg_10]; unsigned __int16 *
0x18001e04a  lea     rcx, aAncestorLocalN_5; "ancestor::*[local-name()='Application']"...
0x18001e051  call    ?GetXMLElementFromQuery@Xml@Common@@YAJPEBGPEAUIXMLDOMElement@@PEAPEAU3@@Z; Common::Xml::GetXMLElementFromQuery(ushort const *,IXMLDOMElement *,IXMLDOMElement * *)
0x18001e056  mov     rcx, [rbp+88h]; this
0x18001e05d  test    eax, eax
0x18001e05f  jns     short loc_18001E076
0x18001e061  mov     r9d, eax; char *
0x18001e064  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18001e06b  mov     edx, 136h; void *
0x18001e070  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e076  lea     r9, [rbp+80h+arg_8]; struct Common::StringBuffer *
0x18001e07d  lea     r8, [rbx+30h]; unsigned __int16 *
0x18001e081  lea     rdx, ?DisplayName@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; struct IXMLDOMElement *
0x18001e088  mov     rcx, [rsp+180h+var_150.lpVtbl]; this
0x18001e08d  call    ?GetAttributeValueStringFromElement@Xml@Common@@YAJPEAUIXMLDOMElement@@PEBGAEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromElement(IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)
0x18001e092  mov     rcx, [rbp+88h]; this
0x18001e099  test    eax, eax
  ... truncated ...
```
