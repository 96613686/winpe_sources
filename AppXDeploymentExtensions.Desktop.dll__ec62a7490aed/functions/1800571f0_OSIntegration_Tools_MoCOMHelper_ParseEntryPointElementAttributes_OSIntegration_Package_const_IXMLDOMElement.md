# OSIntegration::Tools::MoCOMHelper::ParseEntryPointElementAttributes(OSIntegration::Package const *,IXMLDOMElement *)

- ea: `0x1800571f0`
- end: `0x180057a32`
- name: `?ParseEntryPointElementAttributes@MoCOMHelper@Tools@OSIntegration@@IEAAJPEBVPackage@3@PEAUIXMLDOMElement@@@Z`
- size: `2114`
- prototype: `int(OSIntegration::Tools::MoCOMHelper *__hidden this, const struct OSIntegration::Package *, struct IXMLDOMElement *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800dd2dc`

## callees

- `0x180009dc0`
- `0x180011020`
- `0x180012710`
- `0x18001adb4`
- `0x18004c55c`
- `0x1800571f0`
- `0x180057b60`
- `0x1800af1bc`
- `0x1800ddcb4`
- `0x1800de064`
- `0x1800de0b4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180057427`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800574b9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800575fe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180057691`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800576c3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800576f8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180057427`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800574b9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800575fe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180057691`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800576c3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800576f8`

## string_xrefs

- `0x18005725d`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180057305`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180057370`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x1800573b5`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180057472`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x18005752d`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x18005757a`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x18005764a`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180057770`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x1800577bd`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180057854`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180057967`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x1800579a3`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall OSIntegration::Tools::MoCOMHelper::ParseEntryPointElementAttributes(
        OSIntegration::Tools::MoCOMHelper *this,
        const struct OSIntegration::Package *a2,
        struct IXMLDOMElement *a3)
{
  int AttributeValueStringFromElement; // edi
  __int64 v7; // rdx
  int AttributeValueStringFromQuery; // eax
  __int64 v10; // rdx
  const struct std::nothrow_t *v11; // rdx
  struct IXMLDOMElementVtbl *v12; // rcx
  int v13; // eax
  const struct std::nothrow_t *v14; // rdx
  struct IXMLDOMElementVtbl *lpVtbl; // rdi
  int v16; // eax
  int v17; // esi
  const struct std::nothrow_t *v18; // rdx
  WCHAR *v19; // rcx
  int v20; // esi
  WCHAR *v21; // rdi
  int v22; // eax
  __int64 v23; // rdx
  unsigned int v24; // r8d
  int v25; // eax
  const struct std::nothrow_t *v26; // rdx
  struct IXMLDOMElementVtbl *v27; // rsi
  int v28; // eax
  unsigned int v29; // r15d
  const struct std::nothrow_t *v30; // rdx
  WCHAR *v31; // rcx
  int v32; // r15d
  WCHAR *v33; // rsi
  int v34; // eax
  __int64 v35; // rdx
  unsigned int v36; // r8d
  int v37; // eax
  const struct std::nothrow_t *v38; // rdx
  struct IXMLDOMElementVtbl *v39; // r15
  int v40; // eax
  unsigned int v41; // r12d
  const struct std::nothrow_t *v42; // rdx
  struct IXMLDOMElementVtbl *v43; // rcx
  int v44; // r12d
  struct IXMLDOMElementVtbl *v45; // r15
  int v46; // eax
  int v47; // ecx
  int v48; // eax
  int v49; // eax
  __int64 v50; // rdx
  const struct std::nothrow_t *v51; // rdx
  int v52; // eax
  bool v53; // zf
  int v54; // eax
  int *bIgnoreCase; // [rsp+20h] [rbp-59h]
  int *bIgnoreCasea; // [rsp+20h] [rbp-59h]
  int *bIgnoreCaseb; // [rsp+20h] [rbp-59h]
  int *bIgnoreCasec; // [rsp+20h] [rbp-59h]
  int *bIgnoreCased; // [rsp+20h] [rbp-59h]
  int *bIgnoreCasee; // [rsp+20h] [rbp-59h]
  int *bIgnoreCasef; // [rsp+20h] [rbp-59h]
  int *bIgnoreCaseg; // [rsp+20h] [rbp-59h]
  int v63; // [rsp+30h] [rbp-49h] BYREF
  int v64; // [rsp+34h] [rbp-45h] BYREF
  int v65; // [rsp+38h] [rbp-41h] BYREF
  struct IXMLDOMElement v66[2]; // [rsp+40h] [rbp-39h] BYREF
  int v67; // [rsp+50h] [rbp-29h]
  struct IXMLDOMElement v68[2]; // [rsp+58h] [rbp-21h] BYREF
  int v69; // [rsp+68h] [rbp-11h]
  LPCWCH lpString1[2]; // [rsp+70h] [rbp-9h] BYREF
  int v71; // [rsp+80h] [rbp+7h]
  LPCWCH v72[2]; // [rsp+88h] [rbp+Fh] BYREF
  int v73; // [rsp+98h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  int v75; // [rsp+E0h] [rbp+67h] BYREF
  int v76; // [rsp+F8h] [rbp+7Fh] BYREF

  v75 = 0;
  *((_QWORD *)this + 76) = 0;
  *((_DWORD *)this + 154) = 0;
  if ( *((_DWORD *)this + 3) )
    return 0;
  AttributeValueStringFromElement = Common::Xml::GetAttributeValueStringFromElement(
                                      (Common::Xml *)a3,
                                      (struct IXMLDOMElement *)&Appx::Packaging::Manifest::AttributeNameWithoutPrefix::StartPage,
                                      (const unsigned __int16 *)this + 36,
                                      (struct Common::StringBuffer *)&v75,
                                      bIgnoreCase);
  if ( AttributeValueStringFromElement < 0 )
  {
    v7 = 2009;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
      (const char *)(unsigned int)AttributeValueStringFromElement,
      (int)bIgnoreCasea);
    return (unsigned int)AttributeValueStringFromElement;
  }
  if ( v75 )
  {
    *((_DWORD *)this + 3) = 1;
    return 0;
  }
  v65 = 0;
  v76 = 0;
  v63 = 0;
  v64 = 0;
  AttributeValueStringFromElement = OSIntegration::Tools::MoCOMHelper::ParseHostId(this, a3, &v65);
  if ( AttributeValueStringFromElement < 0 )
  {
    v7 = 2023;
    goto LABEL_4;
  }
  if ( v65 )
  {
    AttributeValueStringFromElement = OSIntegration::Tools::MoCOMHelper::ResolveHostRuntimeAttributes(this, a2);
    if ( AttributeValueStringFromElement < 0 )
    {
      v7 = 2027;
      goto LABEL_4;
    }
    goto LABEL_117;
  }
  *(_OWORD *)lpString1 = 0;
  v71 = 0;
  AttributeValueStringFromQuery = Common::Xml::GetAttributeValueStringFromQuery(
                                    (OLECHAR *)L"@*[local-name()='TrustLevel']",
                                    (const unsigned __int16 *)a3,
                                    (const struct IXMLDOMElement *)lpString1,
                                    (struct Common::StringBuffer *)&v76,
                                    bIgnoreCasea);
  AttributeValueStringFromElement = AttributeValueStringFromQuery;
  if ( AttributeValueStringFromQuery < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F6,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
      (const char *)(unsigned int)AttributeValueStringFromQuery,
      (int)bIgnoreCaseb);
LABEL_15:
    v12 = (struct IXMLDOMElementVtbl *)lpString1[1];
    goto LABEL_16;
  }
  LOBYTE(v10) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloActivationOverride>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_AppSiloActivationOverride>::GetImpl'::`2'::impl,
    v10);
  *(_OWORD *)&v66[0].lpVtbl = 0;
  v67 = 0;
  v75 = 0;
  v13 = Common::Xml::GetAttributeValueStringFromQuery(
          (OLECHAR *)L"@uap18:TrustLevel",
          (const unsigned __int16 *)a3,
          v66,
          (struct Common::StringBuffer *)&v75,
          bIgnoreCaseb);
  AttributeValueStringFromElement = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x801,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
      (const char *)(unsigned int)v13,
      (int)bIgnoreCasec);
    if ( v66[1].lpVtbl )
      operator delete(v66[1].lpVtbl, v11);
    goto LABEL_15;
  }
  lpVtbl = v66[1].lpVtbl;
  if ( v75 )
  {
    v16 = Common::StringBuffer::SetValueFromString(
            (Common::StringBuffer *)lpString1,
            (const unsigned __int16 *)v66[1].lpVtbl);
    v17 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x805,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)(unsigned int)v16,
        (int)bIgnoreCasec);
      if ( lpVtbl )
        operator delete(lpVtbl, v18);
      v19 = (WCHAR *)lpString1[1];
      if ( !lpString1[1] )
        return (unsigned int)v17;
      goto LABEL_26;
    }
    v20 = 1;
    v76 = 1;
  }
  else
  {
    v20 = v76;
  }
  if ( lpVtbl )
    operator delete(lpVtbl, v14);
  v21 = (WCHAR *)lpString1[1];
  if ( v20 )
  {
    if ( CompareStringOrdinal(lpString1[1], -1, L"appContainer", -1, 1) == 2 )
    {
      *((_DWORD *)this + 153) = 0;
    }
    else
    {
      if ( CompareStringOrdinal(v21, -1, L"mediumIL", -1, 1) != 2 )
        wil::details::in1diag3::FailFast_Hr(retaddr, (void *)0x819, v24, (const char *)0x8000FFFFLL, (int)bIgnoreCasec);
      *((_DWORD *)this + 153) = 1;
    }
  }
  *(_OWORD *)v72 = 0;
  v73 = 0;
  v22 = Common::Xml::GetAttributeValueStringFromQuery(
          (OLECHAR *)L"@*[local-name()='RuntimeBehavior']",
          (const unsigned __int16 *)a3,
          (const struct IXMLDOMElement *)v72,
          (struct Common::StringBuffer *)&v63,
          bIgnoreCasec);
  v17 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x824,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
      (const char *)(unsigned int)v22,
      (int)bIgnoreCased);
LABEL_37:
    if ( v72[1] )
      operator delete((void *)v72[1], v18);
LABEL_39:
    if ( !v21 )
      return (unsigned int)v17;
    v19 = v21;
LABEL_26:
    operator delete(v19, v18);
    return (unsigned int)v17;
  }
  LOBYTE(v23) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloActivationOverride>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_AppSiloActivationOverride>::GetImpl'::`2'::impl,
    v23);
  *(_OWORD *)&v66[0].lpVtbl = 0;
  v67 = 0;
  v75 = 0;
  v25 = Common::Xml::GetAttributeValueStringFromQuery(
          (OLECHAR *)L"@uap18:RuntimeBehavior",
          (const unsigned __int16 *)a3,
          v66,
          (struct Common::StringBuffer *)&v75,
          bIgnoreCased);
  v17 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x82F,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
      (const char *)(unsigned int)v25,
      (int)bIgnoreCasee);
    if ( v66[1].lpVtbl )
      operator delete(v66[1].lpVtbl, v18);
    goto LABEL_37;
  }
  v27 = v66[1].lpVtbl;
  if ( v75 )
  {
    v28 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v72, (const unsigned __int16 *)v66[1].lpVtbl);
    v29 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x833,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)(unsigned int)v28,
        (int)bIgnoreCasee);
      if ( v27 )
        operator delete(v27, v30);
      v31 = (WCHAR *)v72[1];
      if ( !v72[1] )
        goto LABEL_53;
      goto LABEL_52;
    }
    v32 = 1;
    v63 = 1;
  }
  else
  {
    v32 = v63;
  }
  if ( v27 )
    operator delete(v27, v26);
  v33 = (WCHAR *)v72[1];
  if ( v32 )
  {
    if ( CompareStringOrdinal(v72[1], -1, L"windowsApp", -1, 1) == 2 )
    {
      *((_DWORD *)this + 152) = 0;
    }
    else if ( CompareStringOrdinal(v33, -1, L"packagedClassicApp", -1, 1) == 2 )
    {
      *((_DWORD *)this + 152) = 1;
    }
    else if ( CompareStringOrdinal(v33, -1, L"win32App", -1, 1) == 2 )
    {
      *((_DWORD *)this + 152) = 2;
    }
    else
    {
      if ( CompareStringOrdinal(v33, -1, L"appSilo", -1, 1) != 2 )
        wil::details::in1diag3::FailFast_Hr(retaddr, (void *)0x84D, v36, (const char *)0x8000FFFFLL, (int)bIgnoreCasee);
      *((_DWORD *)this + 152) = 3;
    }
  }
  *(_OWORD *)&v66[0].lpVtbl = 0;
  v67 = 0;
  v34 = Common::Xml::GetAttributeValueStringFromElement(
          (Common::Xml *)a3,
          (struct IXMLDOMElement *)&Appx::Packaging::Manifest::AttributeNameWithoutPrefix::EntryPoint,
          (const unsigned __int16 *)v66,
          (struct Common::StringBuffer *)&v64,
          bIgnoreCasee);
  v29 = v34;
  if ( v34 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x859,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
      (const char *)(unsigned int)v34,
      (int)bIgnoreCasef);
LABEL_65:
    if ( v66[1].lpVtbl )
      operator delete(v66[1].lpVtbl, v30);
    if ( !v33 )
      goto LABEL_53;
    v31 = v33;
LABEL_52:
    operator delete(v31, v30);
LABEL_53:
    if ( v21 )
      operator delete(v21, v30);
    return v29;
  }
  LOBYTE(v35) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloActivationOverride>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_AppSiloActivationOverride>::GetImpl'::`2'::impl,
    v35);
  *(_OWORD *)&v68[0].lpVtbl = 0;
  v69 = 0;
  v75 = 0;
  v37 = Common::Xml::GetAttributeValueStringFromQuery(
          (OLECHAR *)L"uap18:EntryPoint",
          (const unsigned __int16 *)a3,
          v68,
          (struct Common::StringBuffer *)&v75,
          bIgnoreCasef);
  v29 = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x864,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
      (const char *)(unsigned int)v37,
      (int)bIgnoreCasea);
    if ( v68[1].lpVtbl )
      operator delete(v68[1].lpVtbl, v30);
    goto LABEL_65;
  }
  v39 = v68[1].lpVtbl;
  if ( v75 )
  {
    v40 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v66, (const unsigned __int16 *)v68[1].lpVtbl);
    v41 = v40;
    if ( v40 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x868,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)(unsigned int)v40,
        (int)bIgnoreCasea);
      if ( v39 )
        operator delete(v39, v42);
      v43 = v66[1].lpVtbl;
      if ( !v66[1].lpVtbl )
        goto LABEL_85;
      goto LABEL_84;
    }
    v44 = 1;
    v75 = 1;
  }
  else
  {
    v44 = v64;
    v75 = v64;
  }
  if ( v39 )
    operator delete(v39, v38);
  v45 = v66[1].lpVtbl;
  if ( !v44 )
  {
LABEL_108:
    if ( v45 )
      operator delete(v45, v38);
    if ( v33 )
      operator delete(v33, v38);
    if ( v21 )
      operator delete(v21, v38);
    if ( v44 || v76 || v63 )
    {
LABEL_118:
      v75 = 0;
      *(_OWORD *)&v68[0].lpVtbl = 0;
      v69 = 0;
      v49 = Common::Xml::GetAttributeValueStringFromElement(
              (Common::Xml *)a3,
              (struct IXMLDOMElement *)&Appx::Packaging::Manifest::AttributeNameWithoutPrefix::Executable,
              (const unsigned __int16 *)v68,
              (struct Common::StringBuffer *)&v75,
              bIgnoreCasea);
      AttributeValueStringFromElement = v49;
      if ( v49 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x894,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
          (const char *)(unsigned int)v49,
          (int)bIgnoreCaseg);
        v12 = v68[1].lpVtbl;
LABEL_16:
        if ( v12 )
          operator delete(v12, v11);
        return (unsigned int)AttributeValueStringFromElement;
      }
      v21 = (WCHAR *)v68[1].lpVtbl;
      if ( v75
        && (v17 = Common::StringBuffer::SetValueFromString(
                    (OSIntegration::Tools::MoCOMHelper *)((char *)this + 120),
                    (const unsigned __int16 *)v68[1].lpVtbl),
            v17 < 0) )
      {
        v50 = 2199;
      }
      else
      {
        v17 = Common::Xml::GetAttributeValueStringFromElement(
                (Common::Xml *)a3,
                (struct IXMLDOMElement *)&Appx::Packaging::Manifest::AttributeNameWithoutPrefix::RuntimeType,
                (const unsigned __int16 *)this + 184,
                0,
                bIgnoreCaseg);
        if ( v17 >= 0 )
        {
          v52 = *((_DWORD *)this + 152);
          if ( v52 == 1 )
          {
            *((_DWORD *)this + 3) = 9;
          }
          else
          {
            v53 = v52 == 2;
            v54 = 3;
            if ( v53 )
              v54 = 12;
            *((_DWORD *)this + 3) = v54;
          }
          if ( v21 )
            operator delete(v21, v51);
          return 0;
        }
        v50 = 2208;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v50,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)(unsigned int)v17,
        (int)bIgnoreCaseg);
      goto LABEL_39;
    }
LABEL_117:
    if ( !v65 )
      return 0;
    goto LABEL_118;
  }
  v46 = Common::StringBuffer::SetValueFromString(
          (OSIntegration::Tools::MoCOMHelper *)((char *)this + 96),
          (const unsigned __int16 *)v66[1].lpVtbl);
  v41 = v46;
  if ( v46 >= 0 )
  {
    v64 = Common::String::Equals(
            *((const unsigned __int16 **)this + 13),
            *((_DWORD *)this + 24),
            off_1802441D8,
            `OSIntegration::Tools::MoCOMHelper::CentennialEntryPointValue'::`2'::result);
    v47 = Common::String::Equals(
            *((const unsigned __int16 **)this + 13),
            *((_DWORD *)this + 24),
            off_1802441C8,
            `OSIntegration::Tools::MoCOMHelper::CentennialInAppcontainerEntryPointValue'::`2'::result);
    v48 = v64;
    if ( !v76 )
    {
      if ( v64 )
      {
        *((_DWORD *)this + 153) = 1;
      }
      else if ( v47 )
      {
        *((_DWORD *)this + 153) = 0;
      }
    }
    if ( !v63 && (v48 || v47) )
      *((_DWORD *)this + 152) = 1;
    v44 = v75;
    goto LABEL_108;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x86F,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
    (const char *)(unsigned int)v46,
    (int)bIgnoreCasea);
  if ( !v45 )
    goto LABEL_85;
  v43 = v45;
LABEL_84:
  operator delete(v43, v42);
LABEL_85:
  if ( v33 )
    operator delete(v33, v42);
  if ( v21 )
    operator delete(v21, v42);
  return v41;
}

```

## disassembly

```asm
0x1800571f0  mov     [rsp-8+arg_8], rbx
0x1800571f5  push    rbp
0x1800571f6  push    rsi
0x1800571f7  push    rdi
0x1800571f8  push    r12
0x1800571fa  push    r13
0x1800571fc  push    r14
0x1800571fe  push    r15
0x180057200  lea     rbp, [rsp-27h]
0x180057205  sub     rsp, 0A0h
0x18005720c  mov     r13, r8
0x18005720f  mov     rsi, rdx
0x180057212  mov     rbx, rcx
0x180057215  xor     r12d, r12d
0x180057218  mov     [rbp+57h+arg_0], r12d
0x18005721c  mov     [rcx+260h], r12
0x180057223  mov     [rcx+268h], r12d
0x18005722a  cmp     [rcx+0Ch], r12d
0x18005722e  jnz     loc_180057A14
0x180057234  lea     r8, [rcx+48h]; unsigned __int16 *
0x180057238  lea     r9, [rbp+57h+arg_0]; struct Common::StringBuffer *
0x18005723c  lea     rdx, ?StartPage@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; struct IXMLDOMElement *
0x180057243  mov     rcx, r13; this
0x180057246  call    ?GetAttributeValueStringFromElement@Xml@Common@@YAJPEAUIXMLDOMElement@@PEBGAEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromElement(IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)
0x18005724b  mov     edi, eax
0x18005724d  test    eax, eax
0x18005724f  jns     short loc_180057270
0x180057251  mov     edx, 7D9h; void *
0x180057256  mov     rcx, [rbp+5Fh]; this
0x18005725a  mov     r9d, edi; char *
0x18005725d  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180057264  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057269  mov     eax, edi
0x18005726b  jmp     loc_180057A16
0x180057270  cmp     [rbp+57h+arg_0], r12d
0x180057274  jz      short loc_180057282
0x180057276  mov     dword ptr [rbx+0Ch], 1
0x18005727d  jmp     loc_180057A14
0x180057282  mov     [rbp+57h+var_98], r12d
0x180057286  mov     [rbp+57h+arg_18], r12d
0x18005728a  mov     [rbp+57h+var_A0], r12d
0x18005728e  mov     [rbp+57h+var_9C], r12d
0x180057292  lea     r8, [rbp+57h+var_98]; int *
0x180057296  mov     rdx, r13; struct IXMLDOMElement *
0x180057299  mov     rcx, rbx; this
0x18005729c  call    ?ParseHostId@MoCOMHelper@Tools@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEAH@Z; OSIntegration::Tools::MoCOMHelper::ParseHostId(IXMLDOMElement *,int *)
0x1800572a1  mov     edi, eax
0x1800572a3  test    eax, eax
0x1800572a5  jns     short loc_1800572AE
0x1800572a7  mov     edx, 7E7h
0x1800572ac  jmp     short loc_180057256
0x1800572ae  mov     r14d, 1
0x1800572b4  cmp     [rbp+57h+var_98], r12d
0x1800572b8  jz      short loc_1800572D6
0x1800572ba  mov     rdx, rsi; struct OSIntegration::Package *
0x1800572bd  mov     rcx, rbx; this
0x1800572c0  call    ?ResolveHostRuntimeAttributes@MoCOMHelper@Tools@OSIntegration@@AEAAJPEBVPackage@3@@Z; OSIntegration::Tools::MoCOMHelper::ResolveHostRuntimeAttributes(OSIntegration::Package const *)
0x1800572c5  mov     edi, eax
0x1800572c7  test    eax, eax
0x1800572c9  jns     loc_180057926
0x1800572cf  mov     edx, 7EBh
0x1800572d4  jmp     short loc_180057256
0x1800572d6  xorps   xmm0, xmm0
0x1800572d9  movups  xmmword ptr [rbp+57h+lpString1], xmm0
0x1800572dd  mov     [rbp+57h+var_50], r12d
0x1800572e1  lea     r9, [rbp+57h+arg_18]; struct Common::StringBuffer *
0x1800572e5  lea     r8, [rbp+57h+lpString1]; struct IXMLDOMElement *
0x1800572e9  mov     rdx, r13; unsigned __int16 *
0x1800572ec  lea     rcx, aLocalNameTrust; "@*[local-name()='TrustLevel']"
0x1800572f3  call    ?GetAttributeValueStringFromQuery@Xml@Common@@YAJPEBGPEBUIXMLDOMElement@@AEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromQuery(ushort const *,IXMLDOMElement const *,Common::StringBuffer &,int *)
0x1800572f8  mov     edi, eax
0x1800572fa  test    eax, eax
0x1800572fc  jns     short loc_18005732E
0x1800572fe  mov     rcx, [rbp+5Fh]; this
0x180057302  mov     r9d, eax; char *
0x180057305  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18005730c  mov     edx, 7F6h; void *
0x180057311  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057316  nop
0x180057317  mov     rcx, [rbp+57h+lpString1+8]; void *
0x18005731b  test    rcx, rcx
0x18005731e  jz      loc_180057269
0x180057324  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180057329  jmp     loc_180057269
0x18005732e  mov     dl, r14b
0x180057331  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloActivationOverride@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloActivationOverride@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloActivationOverride> `wil::Feature<__WilFeatureTraits_Feature_AppSiloActivationOverride>::GetImpl(void)'::`2'::impl
0x180057338  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloActivationOverride@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloActivationOverride>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18005733d  xorps   xmm0, xmm0
0x180057340  movups  xmmword ptr [rbp+57h+var_90.lpVtbl], xmm0
0x180057344  mov     [rbp+57h+var_80], r12d
0x180057348  mov     [rbp+57h+arg_0], r12d
0x18005734c  lea     r9, [rbp+57h+arg_0]; struct Common::StringBuffer *
0x180057350  lea     r8, [rbp+57h+var_90]; struct IXMLDOMElement *
0x180057354  mov     rdx, r13; unsigned __int16 *
0x180057357  lea     rcx, aUap18Trustleve; "@uap18:TrustLevel"
0x18005735e  call    ?GetAttributeValueStringFromQuery@Xml@Common@@YAJPEBGPEBUIXMLDOMElement@@AEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromQuery(ushort const *,IXMLDOMElement const *,Common::StringBuffer &,int *)
0x180057363  mov     edi, eax
0x180057365  test    eax, eax
0x180057367  jns     short loc_180057392
0x180057369  mov     rcx, [rbp+5Fh]; this
0x18005736d  mov     r9d, eax; char *
0x180057370  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180057377  mov     edx, 801h; void *
0x18005737c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057381  nop
0x180057382  mov     rcx, [rbp+57h+var_90.lpVtbl+8]; void *
0x180057386  test    rcx, rcx
0x180057389  jz      short loc_180057317
0x18005738b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180057390  jmp     short loc_180057317
0x180057392  mov     rdi, [rbp+57h+var_90.lpVtbl+8]
0x180057396  cmp     [rbp+57h+arg_0], r12d
0x18005739a  jz      short loc_1800573F3
0x18005739c  mov     rdx, rdi; unsigned __int16 *
0x18005739f  lea     rcx, [rbp+57h+lpString1]; this
0x1800573a3  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x1800573a8  mov     esi, eax
0x1800573aa  test    eax, eax
0x1800573ac  jns     short loc_1800573EA
0x1800573ae  mov     rcx, [rbp+5Fh]; this
0x1800573b2  mov     r9d, eax; char *
0x1800573b5  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800573bc  mov     edx, 805h; void *
0x1800573c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800573c6  nop
0x1800573c7  test    rdi, rdi
0x1800573ca  jz      short loc_1800573D5
0x1800573cc  mov     rcx, rdi; void *
0x1800573cf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800573d4  nop
0x1800573d5  mov     rcx, [rbp+57h+lpString1+8]; void *
0x1800573d9  test    rcx, rcx
0x1800573dc  jz      short loc_1800573E3
0x1800573de  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800573e3  mov     eax, esi
0x1800573e5  jmp     loc_180057A16
0x1800573ea  mov     esi, r14d
0x1800573ed  mov     [rbp+57h+arg_18], r14d
0x1800573f1  jmp     short loc_1800573F9
0x1800573f3  mov     esi, [rbp+57h+arg_18]
0x1800573f6  mov     [rbp+57h+arg_18], esi
0x1800573f9  test    rdi, rdi
0x1800573fc  jz      short loc_180057406
0x1800573fe  mov     rcx, rdi; void *
0x180057401  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180057406  or      r15d, 0FFFFFFFFh
0x18005740a  mov     rdi, [rbp+57h+lpString1+8]
0x18005740e  test    esi, esi
0x180057410  jz      short loc_18005743F
0x180057412  mov     [rsp+0D0h+bIgnoreCase], r14d; int
0x180057417  mov     r9d, r15d; cchCount2
0x18005741a  lea     r8, ?TrustLevelAppContainer@Value@Packaging@Appx@@3QBGB; "appContainer"
0x180057421  mov     edx, r15d; cchCount1
0x180057424  mov     rcx, rdi; lpString1
0x180057427  call    cs:__imp_CompareStringOrdinal
0x18005742e  nop     dword ptr [rax+rax+00h]
0x180057433  add     eax, 0FFFFFFFEh
0x180057436  jnz     short loc_1800574A4
0x180057438  mov     [rbx+264h], r12d
0x18005743f  xorps   xmm0, xmm0
0x180057442  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x180057446  mov     [rbp+57h+var_38], r12d
0x18005744a  lea     r9, [rbp+57h+var_A0]; struct Common::StringBuffer *
0x18005744e  lea     r8, [rbp+57h+var_48]; struct IXMLDOMElement *
0x180057452  mov     rdx, r13; unsigned __int16 *
0x180057455  lea     rcx, aLocalNameRunti; "@*[local-name()='RuntimeBehavior']"
0x18005745c  call    ?GetAttributeValueStringFromQuery@Xml@Common@@YAJPEBGPEBUIXMLDOMElement@@AEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromQuery(ushort const *,IXMLDOMElement const *,Common::StringBuffer &,int *)
0x180057461  mov     esi, eax
0x180057463  test    eax, eax
0x180057465  jns     loc_1800574EB
0x18005746b  mov     rcx, [rbp+5Fh]; this
0x18005746f  mov     r9d, eax; char *
0x180057472  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180057479  mov     edx, 824h; void *
0x18005747e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057483  nop
0x180057484  mov     rcx, [rbp+57h+var_48+8]; void *
0x180057488  test    rcx, rcx
0x18005748b  jz      short loc_180057493
0x18005748d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180057492  nop
0x180057493  test    rdi, rdi
0x180057496  jz      loc_1800573E3
0x18005749c  mov     rcx, rdi
0x18005749f  jmp     loc_1800573DE
0x1800574a4  mov     [rsp+0D0h+bIgnoreCase], r14d; int
0x1800574a9  mov     r9d, r15d; cchCount2
0x1800574ac  lea     r8, ?TrustLevelMediumIL@Value@Packaging@Appx@@3QBGB; "mediumIL"
0x1800574b3  mov     edx, r15d; cchCount1
0x1800574b6  mov     rcx, rdi; lpString1
0x1800574b9  call    cs:__imp_CompareStringOrdinal
0x1800574c0  nop     dword ptr [rax+rax+00h]
0x1800574c5  add     eax, 0FFFFFFFEh
0x1800574c8  jnz     short loc_1800574D6
0x1800574ca  mov     [rbx+264h], r14d
0x1800574d1  jmp     loc_18005743F
0x1800574d6  mov     rcx, [rbp+5Fh]; this
0x1800574da  mov     edx, 819h; void *
0x1800574df  mov     r9d, 8000FFFFh; char *
0x1800574e5  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800574eb  mov     dl, r14b
0x1800574ee  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloActivationOverride@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloActivationOverride@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloActivationOverride> `wil::Feature<__WilFeatureTraits_Feature_AppSiloActivationOverride>::GetImpl(void)'::`2'::impl
0x1800574f5  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloActivationOverride@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloActivationOverride>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800574fa  xorps   xmm0, xmm0
0x1800574fd  movups  xmmword ptr [rbp+57h+var_90.lpVtbl], xmm0
0x180057501  mov     [rbp+57h+var_80], r12d
0x180057505  mov     [rbp+57h+arg_0], r12d
0x180057509  lea     r9, [rbp+57h+arg_0]; struct Common::StringBuffer *
0x18005750d  lea     r8, [rbp+57h+var_90]; struct IXMLDOMElement *
0x180057511  mov     rdx, r13; unsigned __int16 *
0x180057514  lea     rcx, aUap18Runtimebe; "@uap18:RuntimeBehavior"
0x18005751b  call    ?GetAttributeValueStringFromQuery@Xml@Common@@YAJPEBGPEBUIXMLDOMElement@@AEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromQuery(ushort const *,IXMLDOMElement const *,Common::StringBuffer &,int *)
0x180057520  mov     esi, eax
0x180057522  test    eax, eax
0x180057524  jns     short loc_180057556
0x180057526  mov     rcx, [rbp+5Fh]; this
0x18005752a  mov     r9d, eax; char *
0x18005752d  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180057534  mov     edx, 82Fh; void *
0x180057539  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005753e  nop
0x18005753f  mov     rcx, [rbp+57h+var_90.lpVtbl+8]; void *
0x180057543  test    rcx, rcx
0x180057546  jz      loc_180057484
0x18005754c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180057551  jmp     loc_180057484
0x180057556  mov     rsi, [rbp+57h+var_90.lpVtbl+8]
0x18005755a  cmp     [rbp+57h+arg_0], r12d
0x18005755e  jz      short loc_1800575C7
0x180057560  mov     rdx, rsi; unsigned __int16 *
0x180057563  lea     rcx, [rbp+57h+var_48]; this
0x180057567  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18005756c  mov     r15d, eax
0x18005756f  test    eax, eax
0x180057571  jns     short loc_1800575BE
0x180057573  mov     rcx, [rbp+5Fh]; this
0x180057577  mov     r9d, eax; char *
0x18005757a  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180057581  mov     edx, 833h; void *
0x180057586  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005758b  nop
0x18005758c  test    rsi, rsi
0x18005758f  jz      short loc_18005759A
0x180057591  mov     rcx, rsi; void *
0x180057594  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180057599  nop
0x18005759a  mov     rcx, [rbp+57h+var_48+8]; void *
0x18005759e  test    rcx, rcx
0x1800575a1  jz      short loc_1800575A9
0x1800575a3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800575a8  nop
0x1800575a9  test    rdi, rdi
0x1800575ac  jz      short loc_1800575B6
0x1800575ae  mov     rcx, rdi; void *
0x1800575b1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800575b6  mov     eax, r15d
0x1800575b9  jmp     loc_180057A16
0x1800575be  mov     r15d, r14d
0x1800575c1  mov     [rbp+57h+var_A0], r14d
0x1800575c5  jmp     short loc_1800575CF
0x1800575c7  mov     r15d, [rbp+57h+var_A0]
0x1800575cb  mov     [rbp+57h+var_A0], r15d
0x1800575cf  test    rsi, rsi
0x1800575d2  jz      short loc_1800575DC
0x1800575d4  mov     rcx, rsi; void *
0x1800575d7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800575dc  mov     rsi, [rbp+57h+var_48+8]
0x1800575e0  test    r15d, r15d
0x1800575e3  jz      short loc_180057616
0x1800575e5  mov     [rsp+0D0h+bIgnoreCase], r14d; int *
0x1800575ea  or      r15d, 0FFFFFFFFh
0x1800575ee  mov     r9d, r15d; cchCount2
0x1800575f1  lea     r8, ?RuntimeBehaviorWindowsApp@Value@Packaging@Appx@@3QBGB; "windowsApp"
0x1800575f8  mov     edx, r15d; cchCount1
0x1800575fb  mov     rcx, rsi; lpString1
0x1800575fe  call    cs:__imp_CompareStringOrdinal
0x180057605  nop     dword ptr [rax+rax+00h]
0x18005760a  add     eax, 0FFFFFFFEh
0x18005760d  jnz     short loc_18005767C
0x18005760f  mov     [rbx+260h], r12d
0x180057616  xorps   xmm0, xmm0
0x180057619  movups  xmmword ptr [rbp+57h+var_90.lpVtbl], xmm0
0x18005761d  mov     [rbp+57h+var_80], r12d
0x180057621  lea     r9, [rbp+57h+var_9C]; struct Common::StringBuffer *
0x180057625  lea     r8, [rbp+57h+var_90]; unsigned __int16 *
0x180057629  lea     rdx, ?EntryPoint@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; struct IXMLDOMElement *
0x180057630  mov     rcx, r13; this
0x180057633  call    ?GetAttributeValueStringFromElement@Xml@Common@@YAJPEAUIXMLDOMElement@@PEBGAEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromElement(IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)
0x180057638  mov     r15d, eax
0x18005763b  test    eax, eax
0x18005763d  jns     loc_18005772D
0x180057643  mov     rcx, [rbp+5Fh]; this
0x180057647  mov     r9d, eax; char *
0x18005764a  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180057651  mov     edx, 859h; void *
0x180057656  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005765b  nop
0x18005765c  mov     rcx, [rbp+57h+var_90.lpVtbl+8]; void *
0x180057660  test    rcx, rcx
0x180057663  jz      short loc_18005766B
  ... truncated ...
```
