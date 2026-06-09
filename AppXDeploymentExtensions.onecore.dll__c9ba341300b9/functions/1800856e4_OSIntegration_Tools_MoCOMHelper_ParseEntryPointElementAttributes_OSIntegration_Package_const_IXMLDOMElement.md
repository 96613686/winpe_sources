# OSIntegration::Tools::MoCOMHelper::ParseEntryPointElementAttributes(OSIntegration::Package const *,IXMLDOMElement *)

- ea: `0x1800856e4`
- end: `0x180085d5b`
- name: `?ParseEntryPointElementAttributes@MoCOMHelper@Tools@OSIntegration@@IEAAJPEBVPackage@3@PEAUIXMLDOMElement@@@Z`
- size: `1655`
- prototype: `__int64 __fastcall(OSIntegration::Tools::MoCOMHelper *__hidden this, const struct OSIntegration::Package *, struct IXMLDOMElement *)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b3e44`
- `0x180151034`
- `0x18015110c`

## callees

- `0x18000bd80`
- `0x18000e6e0`
- `0x18000fed0`
- `0x18002e1cc`
- `0x180041948`
- `0x18007fdec`
- `0x1800856e4`
- `0x180098bf4`
- `0x18009bdbc`
- `0x1800a6244`
- `0x18015131c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800858c5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180085931`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180085a04`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180085a62`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180085a8b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180085abb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800858c5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180085931`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180085a04`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180085a62`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180085a8b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180085abb`

## string_xrefs

- `0x180085751`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x1800857ff`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180085855`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180085906`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180085999`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180085b27`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180085b9f`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180085cf8`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall OSIntegration::Tools::MoCOMHelper::ParseEntryPointElementAttributes(
        OSIntegration::Tools::MoCOMHelper *this,
        const struct OSIntegration::Package *a2,
        struct IXMLDOMElement *a3)
{
  int v6; // r12d
  int AttributeValueStringFromElement; // edi
  __int64 v8; // rdx
  int v10; // r13d
  int AttributeValueStringFromQuery; // eax
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // rdx
  Common::StringBuffer *v15; // rcx
  int v16; // edi
  int v17; // eax
  __int64 v18; // rdx
  unsigned int v19; // r8d
  int v20; // eax
  __int64 v21; // rdx
  const WCHAR *v22; // rdi
  __int64 v23; // rdx
  unsigned int v24; // r8d
  int v25; // eax
  __int64 v26; // rdx
  int v27; // r15d
  unsigned int *v28; // r13
  Common::StringBuffer *v29; // rcx
  int v30; // edi
  int v31; // eax
  int v32; // eax
  __int64 v33; // rdx
  int v34; // eax
  int *bIgnoreCase; // [rsp+20h] [rbp-59h]
  int *bIgnoreCasea; // [rsp+20h] [rbp-59h]
  int *bIgnoreCaseb; // [rsp+20h] [rbp-59h]
  int *bIgnoreCasec; // [rsp+20h] [rbp-59h]
  int *bIgnoreCased; // [rsp+20h] [rbp-59h]
  int *bIgnoreCasee; // [rsp+20h] [rbp-59h]
  int v41; // [rsp+30h] [rbp-49h] BYREF
  int v42; // [rsp+34h] [rbp-45h] BYREF
  struct IXMLDOMElement v43[2]; // [rsp+38h] [rbp-41h] BYREF
  int v44; // [rsp+48h] [rbp-31h]
  int v45; // [rsp+50h] [rbp-29h] BYREF
  struct IXMLDOMElement v46[2]; // [rsp+58h] [rbp-21h] BYREF
  int v47; // [rsp+68h] [rbp-11h]
  LPCWCH v48[2]; // [rsp+70h] [rbp-9h] BYREF
  int v49; // [rsp+80h] [rbp+7h]
  LPCWCH lpString1[2]; // [rsp+88h] [rbp+Fh] BYREF
  int v51; // [rsp+98h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  int v53; // [rsp+E0h] [rbp+67h] BYREF
  int v54; // [rsp+F8h] [rbp+7Fh] BYREF

  v6 = 0;
  v53 = 0;
  *((_QWORD *)this + 76) = 0;
  *((_DWORD *)this + 154) = 0;
  if ( *((_DWORD *)this + 3) )
    return 0;
  AttributeValueStringFromElement = Common::Xml::GetAttributeValueStringFromElement(
                                      (Common::Xml *)a3,
                                      (struct IXMLDOMElement *)&Appx::Packaging::Manifest::AttributeNameWithoutPrefix::StartPage,
                                      (const unsigned __int16 *)this + 36,
                                      (struct Common::StringBuffer *)&v53,
                                      bIgnoreCase);
  if ( AttributeValueStringFromElement < 0 )
  {
    v8 = 2009;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
      (const char *)(unsigned int)AttributeValueStringFromElement,
      (int)bIgnoreCasea);
    return (unsigned int)AttributeValueStringFromElement;
  }
  if ( !v53 )
  {
    v54 = 0;
    v41 = 0;
    v42 = 0;
    v45 = 0;
    AttributeValueStringFromElement = OSIntegration::Tools::MoCOMHelper::ParseHostId(this, a3, &v54);
    if ( AttributeValueStringFromElement < 0 )
    {
      v8 = 2023;
      goto LABEL_4;
    }
    v10 = 3;
    if ( v54 )
    {
      AttributeValueStringFromElement = OSIntegration::Tools::MoCOMHelper::ResolveHostRuntimeAttributes(this, a2);
      if ( AttributeValueStringFromElement < 0 )
      {
        v8 = 2027;
        goto LABEL_4;
      }
      goto LABEL_80;
    }
    *(_OWORD *)lpString1 = 0;
    v51 = 0;
    AttributeValueStringFromQuery = Common::Xml::GetAttributeValueStringFromQuery(
                                      (OLECHAR *)L"@*[local-name()='TrustLevel']",
                                      (const unsigned __int16 *)a3,
                                      (const struct IXMLDOMElement *)lpString1,
                                      (struct Common::StringBuffer *)&v41,
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
LABEL_65:
      v29 = (Common::StringBuffer *)lpString1;
      goto LABEL_66;
    }
    LOBYTE(v12) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloActivationOverride>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_AppSiloActivationOverride>::GetImpl'::`2'::impl,
      v12);
    *(_OWORD *)&v43[0].lpVtbl = 0;
    v44 = 0;
    v53 = 0;
    v13 = Common::Xml::GetAttributeValueStringFromQuery(
            (OLECHAR *)L"@uap18:TrustLevel",
            (const unsigned __int16 *)a3,
            v43,
            (struct Common::StringBuffer *)&v53,
            bIgnoreCaseb);
    AttributeValueStringFromElement = v13;
    if ( v13 < 0 )
    {
      v14 = 2049;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)(unsigned int)v13,
        (int)bIgnoreCasec);
      v15 = (Common::StringBuffer *)v43;
LABEL_64:
      Common::StringBuffer::~StringBuffer(v15);
      goto LABEL_65;
    }
    if ( v53 )
    {
      v13 = Common::StringBuffer::SetValueFromString(
              (Common::StringBuffer *)lpString1,
              (const unsigned __int16 *)v43[1].lpVtbl);
      AttributeValueStringFromElement = v13;
      if ( v13 < 0 )
      {
        v14 = 2053;
        goto LABEL_17;
      }
      v16 = 1;
      v53 = 1;
    }
    else
    {
      v16 = v41;
      v53 = v41;
    }
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v43);
    if ( v16 )
    {
      if ( CompareStringOrdinal(lpString1[1], -1, L"appContainer", -1, 1) == 2 )
      {
        *((_DWORD *)this + 153) = 0;
      }
      else
      {
        if ( CompareStringOrdinal(lpString1[1], -1, L"mediumIL", -1, 1) != 2 )
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            (void *)0x819,
            v19,
            (const char *)0x8000FFFFLL,
            (int)bIgnoreCasec);
        *((_DWORD *)this + 153) = 1;
      }
    }
    *(_OWORD *)v48 = 0;
    v49 = 0;
    v17 = Common::Xml::GetAttributeValueStringFromQuery(
            (OLECHAR *)L"@*[local-name()='RuntimeBehavior']",
            (const unsigned __int16 *)a3,
            (const struct IXMLDOMElement *)v48,
            (struct Common::StringBuffer *)&v42,
            bIgnoreCasec);
    AttributeValueStringFromElement = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x824,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)(unsigned int)v17,
        (int)bIgnoreCased);
LABEL_63:
      v15 = (Common::StringBuffer *)v48;
      goto LABEL_64;
    }
    LOBYTE(v18) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloActivationOverride>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_AppSiloActivationOverride>::GetImpl'::`2'::impl,
      v18);
    *(_OWORD *)&v43[0].lpVtbl = 0;
    v44 = 0;
    v41 = 0;
    v20 = Common::Xml::GetAttributeValueStringFromQuery(
            (OLECHAR *)L"@uap18:RuntimeBehavior",
            (const unsigned __int16 *)a3,
            v43,
            (struct Common::StringBuffer *)&v41,
            bIgnoreCased);
    AttributeValueStringFromElement = v20;
    if ( v20 < 0 )
    {
      v21 = 2095;
LABEL_61:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)(unsigned int)v20,
        (int)bIgnoreCasea);
      goto LABEL_62;
    }
    if ( v41 )
    {
      v20 = Common::StringBuffer::SetValueFromString(
              (Common::StringBuffer *)v48,
              (const unsigned __int16 *)v43[1].lpVtbl);
      AttributeValueStringFromElement = v20;
      if ( v20 < 0 )
      {
        v21 = 2099;
        goto LABEL_61;
      }
      v6 = 1;
    }
    else
    {
      v6 = v42;
    }
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v43);
    if ( v6 )
    {
      v22 = v48[1];
      if ( CompareStringOrdinal(v48[1], -1, L"windowsApp", -1, 1) == 2 )
      {
        *((_DWORD *)this + 152) = 0;
      }
      else if ( CompareStringOrdinal(v22, -1, L"packagedClassicApp", -1, 1) == 2 )
      {
        *((_DWORD *)this + 152) = 1;
      }
      else if ( CompareStringOrdinal(v22, -1, L"win32App", -1, 1) == 2 )
      {
        *((_DWORD *)this + 152) = 2;
      }
      else
      {
        if ( CompareStringOrdinal(v22, -1, L"appSilo", -1, 1) != 2 )
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            (void *)0x84D,
            v24,
            (const char *)0x8000FFFFLL,
            (int)bIgnoreCasea);
        *((_DWORD *)this + 152) = 3;
      }
    }
    *(_OWORD *)&v43[0].lpVtbl = 0;
    v44 = 0;
    v20 = Common::Xml::GetAttributeValueStringFromElement(
            (Common::Xml *)a3,
            (struct IXMLDOMElement *)&Appx::Packaging::Manifest::AttributeNameWithoutPrefix::EntryPoint,
            (const unsigned __int16 *)v43,
            (struct Common::StringBuffer *)&v45,
            bIgnoreCasea);
    AttributeValueStringFromElement = v20;
    if ( v20 < 0 )
    {
      v21 = 2137;
      goto LABEL_61;
    }
    LOBYTE(v23) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloActivationOverride>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_AppSiloActivationOverride>::GetImpl'::`2'::impl,
      v23);
    *(_OWORD *)&v46[0].lpVtbl = 0;
    v47 = 0;
    v42 = 0;
    v25 = Common::Xml::GetAttributeValueStringFromQuery(
            (OLECHAR *)L"uap18:EntryPoint",
            (const unsigned __int16 *)a3,
            v46,
            (struct Common::StringBuffer *)&v42,
            bIgnoreCasea);
    AttributeValueStringFromElement = v25;
    if ( v25 < 0 )
    {
      v26 = 2148;
LABEL_52:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v26,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)(unsigned int)v25,
        (int)bIgnoreCasea);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v46);
LABEL_62:
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v43);
      goto LABEL_63;
    }
    if ( v42 )
    {
      v25 = Common::StringBuffer::SetValueFromString(
              (Common::StringBuffer *)v43,
              (const unsigned __int16 *)v46[1].lpVtbl);
      AttributeValueStringFromElement = v25;
      if ( v25 < 0 )
      {
        v26 = 2152;
        goto LABEL_52;
      }
      v27 = 1;
    }
    else
    {
      v27 = v45;
    }
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v46);
    if ( v27 )
    {
      v28 = (unsigned int *)((char *)this + 96);
      v20 = Common::StringBuffer::SetValueFromString(
              (OSIntegration::Tools::MoCOMHelper *)((char *)this + 96),
              (const unsigned __int16 *)v43[1].lpVtbl);
      AttributeValueStringFromElement = v20;
      if ( v20 < 0 )
      {
        v21 = 2159;
        goto LABEL_61;
      }
      v30 = Common::String::Equals(
              *((const unsigned __int16 **)this + 13),
              *v28,
              off_1802E07C0,
              `OSIntegration::Tools::MoCOMHelper::CentennialEntryPointValue'::`2'::result);
      v31 = Common::String::Equals(
              *((const unsigned __int16 **)this + 13),
              *v28,
              off_1802E07B0,
              `OSIntegration::Tools::MoCOMHelper::CentennialInAppcontainerEntryPointValue'::`2'::result);
      if ( !v53 )
      {
        if ( v30 )
        {
          *((_DWORD *)this + 153) = 1;
        }
        else if ( v31 )
        {
          *((_DWORD *)this + 153) = 0;
        }
      }
      if ( !v6 && (v30 || v31) )
        *((_DWORD *)this + 152) = 1;
      v10 = 3;
    }
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v43);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v48);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpString1);
    if ( v27 || v53 || v6 )
    {
      v6 = 0;
LABEL_83:
      v53 = v6;
      *(_OWORD *)&v46[0].lpVtbl = 0;
      v47 = v6;
      v32 = Common::Xml::GetAttributeValueStringFromElement(
              (Common::Xml *)a3,
              (struct IXMLDOMElement *)&Appx::Packaging::Manifest::AttributeNameWithoutPrefix::Executable,
              (const unsigned __int16 *)v46,
              (struct Common::StringBuffer *)&v53,
              bIgnoreCasea);
      AttributeValueStringFromElement = v32;
      if ( v32 >= 0 )
      {
        if ( v53 == v6
          || (v32 = Common::StringBuffer::SetValueFromString(
                      (OSIntegration::Tools::MoCOMHelper *)((char *)this + 120),
                      (const unsigned __int16 *)v46[1].lpVtbl),
              AttributeValueStringFromElement = v32,
              v32 >= 0) )
        {
          v32 = Common::Xml::GetAttributeValueStringFromElement(
                  (Common::Xml *)a3,
                  (struct IXMLDOMElement *)&Appx::Packaging::Manifest::AttributeNameWithoutPrefix::RuntimeType,
                  (const unsigned __int16 *)this + 184,
                  0,
                  bIgnoreCasee);
          AttributeValueStringFromElement = v32;
          if ( v32 >= 0 )
          {
            v34 = *((_DWORD *)this + 152);
            if ( v34 == 1 )
            {
              *((_DWORD *)this + 3) = 9;
            }
            else
            {
              if ( v34 == 2 )
                v10 = 12;
              *((_DWORD *)this + 3) = v10;
            }
            Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v46);
            return 0;
          }
          v33 = 2208;
        }
        else
        {
          v33 = 2199;
        }
      }
      else
      {
        v33 = 2196;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v33,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)(unsigned int)v32,
        (int)bIgnoreCasee);
      v29 = (Common::StringBuffer *)v46;
LABEL_66:
      Common::StringBuffer::~StringBuffer(v29);
      return (unsigned int)AttributeValueStringFromElement;
    }
LABEL_80:
    if ( v54 == v6 )
      return 0;
    goto LABEL_83;
  }
  *((_DWORD *)this + 3) = 1;
  return 0;
}

```

## disassembly

```asm
0x1800856e4  mov     [rsp-8+arg_8], rbx
0x1800856e9  push    rbp
0x1800856ea  push    rsi
0x1800856eb  push    rdi
0x1800856ec  push    r12
0x1800856ee  push    r13
0x1800856f0  push    r14
0x1800856f2  push    r15
0x1800856f4  lea     rbp, [rsp-27h]
0x1800856f9  sub     rsp, 0A0h
0x180085700  mov     r14, r8
0x180085703  mov     r15, rdx
0x180085706  mov     rbx, rcx
0x180085709  xor     r12d, r12d
0x18008570c  mov     [rbp+57h+arg_0], r12d
0x180085710  mov     [rcx+260h], r12
0x180085717  mov     [rcx+268h], r12d
0x18008571e  cmp     [rcx+0Ch], r12d
0x180085722  jnz     loc_180085D3E
0x180085728  lea     r8, [rcx+48h]; unsigned __int16 *
0x18008572c  lea     r9, [rbp+57h+arg_0]; struct Common::StringBuffer *
0x180085730  lea     rdx, ?StartPage@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; struct IXMLDOMElement *
0x180085737  mov     rcx, r14; this
0x18008573a  call    ?GetAttributeValueStringFromElement@Xml@Common@@YAJPEAUIXMLDOMElement@@PEBGAEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromElement(IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)
0x18008573f  mov     edi, eax
0x180085741  test    eax, eax
0x180085743  jns     short loc_180085764
0x180085745  mov     edx, 7D9h; void *
0x18008574a  mov     rcx, [rbp+5Fh]; this
0x18008574e  mov     r9d, edi; char *
0x180085751  lea     r8, aOnecoreAdminAp_122; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180085758  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008575d  mov     eax, edi
0x18008575f  jmp     loc_180085D40
0x180085764  cmp     [rbp+57h+arg_0], r12d
0x180085768  jz      short loc_180085776
0x18008576a  mov     dword ptr [rbx+0Ch], 1
0x180085771  jmp     loc_180085D3E
0x180085776  mov     [rbp+57h+arg_18], r12d
0x18008577a  mov     [rbp+57h+var_A0], r12d
0x18008577e  mov     [rbp+57h+var_9C], r12d
0x180085782  mov     [rbp+57h+var_80], r12d
0x180085786  lea     r8, [rbp+57h+arg_18]; int *
0x18008578a  mov     rdx, r14; struct IXMLDOMElement *
0x18008578d  mov     rcx, rbx; this
0x180085790  call    ?ParseHostId@MoCOMHelper@Tools@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEAH@Z; OSIntegration::Tools::MoCOMHelper::ParseHostId(IXMLDOMElement *,int *)
0x180085795  mov     edi, eax
0x180085797  test    eax, eax
0x180085799  jns     short loc_1800857A2
0x18008579b  mov     edx, 7E7h
0x1800857a0  jmp     short loc_18008574A
0x1800857a2  mov     esi, 1
0x1800857a7  lea     r13d, [rsi+2]
0x1800857ab  cmp     [rbp+57h+arg_18], r12d
0x1800857af  jz      short loc_1800857D0
0x1800857b1  mov     rdx, r15; struct OSIntegration::Package *
0x1800857b4  mov     rcx, rbx; this
0x1800857b7  call    ?ResolveHostRuntimeAttributes@MoCOMHelper@Tools@OSIntegration@@AEAAJPEBVPackage@3@@Z; OSIntegration::Tools::MoCOMHelper::ResolveHostRuntimeAttributes(OSIntegration::Package const *)
0x1800857bc  mov     edi, eax
0x1800857be  test    eax, eax
0x1800857c0  jns     loc_180085C70
0x1800857c6  mov     edx, 7EBh
0x1800857cb  jmp     loc_18008574A
0x1800857d0  xorps   xmm0, xmm0
0x1800857d3  movups  xmmword ptr [rbp+57h+lpString1], xmm0
0x1800857d7  mov     [rbp+57h+var_38], r12d
0x1800857db  lea     r9, [rbp+57h+var_A0]; struct Common::StringBuffer *
0x1800857df  lea     r8, [rbp+57h+lpString1]; struct IXMLDOMElement *
0x1800857e3  mov     rdx, r14; unsigned __int16 *
0x1800857e6  lea     rcx, aLocalNameTrust; "@*[local-name()='TrustLevel']"
0x1800857ed  call    ?GetAttributeValueStringFromQuery@Xml@Common@@YAJPEBGPEBUIXMLDOMElement@@AEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromQuery(ushort const *,IXMLDOMElement const *,Common::StringBuffer &,int *)
0x1800857f2  mov     edi, eax
0x1800857f4  test    eax, eax
0x1800857f6  jns     short loc_180085815
0x1800857f8  mov     rcx, [rbp+5Fh]; this
0x1800857fc  mov     r9d, eax; char *
0x1800857ff  lea     r8, aOnecoreAdminAp_122; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180085806  mov     edx, 7F6h; void *
0x18008580b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085810  jmp     loc_180085BC4
0x180085815  mov     dl, sil
0x180085818  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloActivationOverride@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloActivationOverride@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloActivationOverride> `wil::Feature<__WilFeatureTraits_Feature_AppSiloActivationOverride>::GetImpl(void)'::`2'::impl
0x18008581f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloActivationOverride@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloActivationOverride>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180085824  xorps   xmm0, xmm0
0x180085827  movups  xmmword ptr [rbp+57h+var_98.lpVtbl], xmm0
0x18008582b  mov     [rbp+57h+var_88], r12d
0x18008582f  mov     [rbp+57h+arg_0], r12d
0x180085833  lea     r9, [rbp+57h+arg_0]; struct Common::StringBuffer *
0x180085837  lea     r8, [rbp+57h+var_98]; struct IXMLDOMElement *
0x18008583b  mov     rdx, r14; unsigned __int16 *
0x18008583e  lea     rcx, aUap18Trustleve; "@uap18:TrustLevel"
0x180085845  call    ?GetAttributeValueStringFromQuery@Xml@Common@@YAJPEBGPEBUIXMLDOMElement@@AEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromQuery(ushort const *,IXMLDOMElement const *,Common::StringBuffer &,int *)
0x18008584a  mov     edi, eax
0x18008584c  test    eax, eax
0x18008584e  jns     short loc_180085872
0x180085850  mov     edx, 801h; void *
0x180085855  lea     r8, aOnecoreAdminAp_122; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18008585c  mov     r9d, eax; char *
0x18008585f  mov     rcx, [rbp+5Fh]; this
0x180085863  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085868  nop
0x180085869  lea     rcx, [rbp+57h+var_98]
0x18008586d  jmp     loc_180085BBE
0x180085872  cmp     [rbp+57h+arg_0], r12d
0x180085876  jz      short loc_180085899
0x180085878  mov     rdx, [rbp+57h+var_98.lpVtbl+8]; unsigned __int16 *
0x18008587c  lea     rcx, [rbp+57h+lpString1]; this
0x180085880  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180085885  mov     edi, eax
0x180085887  test    eax, eax
0x180085889  jns     short loc_180085892
0x18008588b  mov     edx, 805h
0x180085890  jmp     short loc_180085855
0x180085892  mov     edi, esi
0x180085894  mov     [rbp+57h+arg_0], esi
0x180085897  jmp     short loc_18008589F
0x180085899  mov     edi, [rbp+57h+var_A0]
0x18008589c  mov     [rbp+57h+arg_0], edi
0x18008589f  lea     rcx, [rbp+57h+var_98]; this
0x1800858a3  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800858a8  or      r15d, 0FFFFFFFFh
0x1800858ac  test    edi, edi
0x1800858ae  jz      short loc_1800858D7
0x1800858b0  mov     [rsp+0D0h+bIgnoreCase], esi; int
0x1800858b4  mov     r9d, r15d; cchCount2
0x1800858b7  lea     r8, ?TrustLevelAppContainer@Value@Packaging@Appx@@3QBGB; "appContainer"
0x1800858be  mov     edx, r15d; cchCount1
0x1800858c1  mov     rcx, [rbp+57h+lpString1+8]; lpString1
0x1800858c5  call    cs:__imp_CompareStringOrdinal
0x1800858cb  add     eax, 0FFFFFFFEh
0x1800858ce  jnz     short loc_18008591C
0x1800858d0  mov     [rbx+264h], r12d
0x1800858d7  xorps   xmm0, xmm0
0x1800858da  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x1800858de  mov     [rbp+57h+var_50], r12d
0x1800858e2  lea     r9, [rbp+57h+var_9C]; struct Common::StringBuffer *
0x1800858e6  lea     r8, [rbp+57h+var_60]; struct IXMLDOMElement *
0x1800858ea  mov     rdx, r14; unsigned __int16 *
0x1800858ed  lea     rcx, aLocalNameRunti; "@*[local-name()='RuntimeBehavior']"
0x1800858f4  call    ?GetAttributeValueStringFromQuery@Xml@Common@@YAJPEBGPEBUIXMLDOMElement@@AEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromQuery(ushort const *,IXMLDOMElement const *,Common::StringBuffer &,int *)
0x1800858f9  mov     edi, eax
0x1800858fb  test    eax, eax
0x1800858fd  jns     short loc_180085959
0x1800858ff  mov     rcx, [rbp+5Fh]; this
0x180085903  mov     r9d, eax; char *
0x180085906  lea     r8, aOnecoreAdminAp_122; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18008590d  mov     edx, 824h; void *
0x180085912  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085917  jmp     loc_180085BBA
0x18008591c  mov     [rsp+0D0h+bIgnoreCase], esi; int
0x180085920  mov     r9d, r15d; cchCount2
0x180085923  lea     r8, ?TrustLevelMediumIL@Value@Packaging@Appx@@3QBGB; "mediumIL"
0x18008592a  mov     edx, r15d; cchCount1
0x18008592d  mov     rcx, [rbp+57h+lpString1+8]; lpString1
0x180085931  call    cs:__imp_CompareStringOrdinal
0x180085937  add     eax, 0FFFFFFFEh
0x18008593a  jnz     short loc_180085944
0x18008593c  mov     [rbx+264h], esi
0x180085942  jmp     short loc_1800858D7
0x180085944  mov     rcx, [rbp+5Fh]; this
0x180085948  mov     edx, 819h; void *
0x18008594d  mov     r9d, 8000FFFFh; char *
0x180085953  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180085959  mov     dl, sil
0x18008595c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloActivationOverride@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloActivationOverride@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloActivationOverride> `wil::Feature<__WilFeatureTraits_Feature_AppSiloActivationOverride>::GetImpl(void)'::`2'::impl
0x180085963  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloActivationOverride@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloActivationOverride>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180085968  xorps   xmm0, xmm0
0x18008596b  movups  xmmword ptr [rbp+57h+var_98.lpVtbl], xmm0
0x18008596f  mov     [rbp+57h+var_88], r12d
0x180085973  mov     [rbp+57h+var_A0], r12d
0x180085977  lea     r9, [rbp+57h+var_A0]; struct Common::StringBuffer *
0x18008597b  lea     r8, [rbp+57h+var_98]; struct IXMLDOMElement *
0x18008597f  mov     rdx, r14; unsigned __int16 *
0x180085982  lea     rcx, aUap18Runtimebe; "@uap18:RuntimeBehavior"
0x180085989  call    ?GetAttributeValueStringFromQuery@Xml@Common@@YAJPEBGPEBUIXMLDOMElement@@AEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromQuery(ushort const *,IXMLDOMElement const *,Common::StringBuffer &,int *)
0x18008598e  mov     edi, eax
0x180085990  test    eax, eax
0x180085992  jns     short loc_1800859B2
0x180085994  mov     edx, 82Fh; void *
0x180085999  lea     r8, aOnecoreAdminAp_122; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800859a0  mov     r9d, eax; char *
0x1800859a3  mov     rcx, [rbp+5Fh]; this
0x1800859a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800859ac  nop
0x1800859ad  jmp     loc_180085BB0
0x1800859b2  cmp     [rbp+57h+var_A0], r12d
0x1800859b6  jz      short loc_1800859D7
0x1800859b8  mov     rdx, [rbp+57h+var_98.lpVtbl+8]; unsigned __int16 *
0x1800859bc  lea     rcx, [rbp+57h+var_60]; this
0x1800859c0  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x1800859c5  mov     edi, eax
0x1800859c7  test    eax, eax
0x1800859c9  jns     short loc_1800859D2
0x1800859cb  mov     edx, 833h
0x1800859d0  jmp     short loc_180085999
0x1800859d2  mov     r12d, esi
0x1800859d5  jmp     short loc_1800859DB
0x1800859d7  mov     r12d, [rbp+57h+var_9C]
0x1800859db  lea     rcx, [rbp+57h+var_98]; this
0x1800859df  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800859e4  xor     r15d, r15d
0x1800859e7  test    r12d, r12d
0x1800859ea  jz      short loc_180085A16
0x1800859ec  mov     rdi, [rbp+57h+var_60+8]
0x1800859f0  mov     [rsp+0D0h+bIgnoreCase], esi; int
0x1800859f4  or      edx, 0FFFFFFFFh; cchCount1
0x1800859f7  mov     r9d, edx; cchCount2
0x1800859fa  lea     r8, ?RuntimeBehaviorWindowsApp@Value@Packaging@Appx@@3QBGB; "windowsApp"
0x180085a01  mov     rcx, rdi; lpString1
0x180085a04  call    cs:__imp_CompareStringOrdinal
0x180085a0a  add     eax, 0FFFFFFFEh
0x180085a0d  jnz     short loc_180085A4C
0x180085a0f  mov     [rbx+260h], r15d
0x180085a16  xorps   xmm0, xmm0
0x180085a19  movups  xmmword ptr [rbp+57h+var_98.lpVtbl], xmm0
0x180085a1d  mov     [rbp+57h+var_88], r15d
0x180085a21  lea     r9, [rbp+57h+var_80]; struct Common::StringBuffer *
0x180085a25  lea     r8, [rbp+57h+var_98]; unsigned __int16 *
0x180085a29  lea     rdx, ?EntryPoint@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; struct IXMLDOMElement *
0x180085a30  mov     rcx, r14; this
0x180085a33  call    ?GetAttributeValueStringFromElement@Xml@Common@@YAJPEAUIXMLDOMElement@@PEBGAEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromElement(IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)
0x180085a38  mov     edi, eax
0x180085a3a  test    eax, eax
0x180085a3c  jns     loc_180085AE7
0x180085a42  mov     edx, 859h
0x180085a47  jmp     loc_180085B9C
0x180085a4c  mov     [rsp+0D0h+bIgnoreCase], esi; bIgnoreCase
0x180085a50  or      eax, 0FFFFFFFFh
0x180085a53  mov     r9d, eax; cchCount2
0x180085a56  lea     r8, ?RuntimeBehaviorPackagedClassicApp@Value@Packaging@Appx@@3QBGB; "packagedClassicApp"
0x180085a5d  mov     edx, eax; cchCount1
0x180085a5f  mov     rcx, rdi; lpString1
0x180085a62  call    cs:__imp_CompareStringOrdinal
0x180085a68  add     eax, 0FFFFFFFEh
0x180085a6b  jnz     short loc_180085A75
0x180085a6d  mov     [rbx+260h], esi
0x180085a73  jmp     short loc_180085A16
0x180085a75  mov     [rsp+0D0h+bIgnoreCase], esi; bIgnoreCase
0x180085a79  or      eax, 0FFFFFFFFh
0x180085a7c  mov     r9d, eax; cchCount2
0x180085a7f  lea     r8, ?RuntimeBehaviorWin32App@Value@Packaging@Appx@@3QBGB; "win32App"
0x180085a86  mov     edx, eax; cchCount1
0x180085a88  mov     rcx, rdi; lpString1
0x180085a8b  call    cs:__imp_CompareStringOrdinal
0x180085a91  add     eax, 0FFFFFFFEh
0x180085a94  jnz     short loc_180085AA5
0x180085a96  mov     dword ptr [rbx+260h], 2
0x180085aa0  jmp     loc_180085A16
0x180085aa5  mov     [rsp+0D0h+bIgnoreCase], esi; int
0x180085aa9  or      eax, 0FFFFFFFFh
0x180085aac  mov     r9d, eax; cchCount2
0x180085aaf  lea     r8, ?RuntimeBehaviorAppSilo@Value@Packaging@Appx@@3QBGB; "appSilo"
0x180085ab6  mov     edx, eax; cchCount1
0x180085ab8  mov     rcx, rdi; lpString1
0x180085abb  call    cs:__imp_CompareStringOrdinal
0x180085ac1  add     eax, 0FFFFFFFEh
0x180085ac4  jnz     short loc_180085AD2
0x180085ac6  mov     [rbx+260h], r13d
0x180085acd  jmp     loc_180085A16
0x180085ad2  mov     rcx, [rbp+5Fh]; this
0x180085ad6  mov     edx, 84Dh; void *
0x180085adb  mov     r9d, 8000FFFFh; char *
0x180085ae1  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180085ae7  mov     dl, sil
0x180085aea  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloActivationOverride@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloActivationOverride@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloActivationOverride> `wil::Feature<__WilFeatureTraits_Feature_AppSiloActivationOverride>::GetImpl(void)'::`2'::impl
0x180085af1  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloActivationOverride@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloActivationOverride>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180085af6  xorps   xmm0, xmm0
0x180085af9  movups  xmmword ptr [rbp+57h+var_78.lpVtbl], xmm0
0x180085afd  mov     [rbp+57h+var_68], r15d
0x180085b01  mov     [rbp+57h+var_9C], r15d
0x180085b05  lea     r9, [rbp+57h+var_9C]; struct Common::StringBuffer *
0x180085b09  lea     r8, [rbp+57h+var_78]; struct IXMLDOMElement *
0x180085b0d  mov     rdx, r14; unsigned __int16 *
0x180085b10  lea     rcx, aUap18Entrypoin_0; "uap18:EntryPoint"
0x180085b17  call    ?GetAttributeValueStringFromQuery@Xml@Common@@YAJPEBGPEBUIXMLDOMElement@@AEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromQuery(ushort const *,IXMLDOMElement const *,Common::StringBuffer &,int *)
0x180085b1c  mov     edi, eax
0x180085b1e  test    eax, eax
0x180085b20  jns     short loc_180085B46
0x180085b22  mov     edx, 864h; void *
0x180085b27  lea     r8, aOnecoreAdminAp_122; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180085b2e  mov     r9d, eax; char *
0x180085b31  mov     rcx, [rbp+5Fh]; this
0x180085b35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085b3a  nop
0x180085b3b  lea     rcx, [rbp+57h+var_78]; this
0x180085b3f  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180085b44  jmp     short loc_180085BB0
0x180085b46  cmp     [rbp+57h+var_9C], r15d
0x180085b4a  jz      short loc_180085B6B
0x180085b4c  mov     rdx, [rbp+57h+var_78.lpVtbl+8]; unsigned __int16 *
0x180085b50  lea     rcx, [rbp+57h+var_98]; this
0x180085b54  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180085b59  mov     edi, eax
0x180085b5b  test    eax, eax
0x180085b5d  jns     short loc_180085B66
0x180085b5f  mov     edx, 868h
0x180085b64  jmp     short loc_180085B27
0x180085b66  mov     r15d, esi
0x180085b69  jmp     short loc_180085B6F
0x180085b6b  mov     r15d, [rbp+57h+var_80]
  ... truncated ...
```
