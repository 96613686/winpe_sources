# _lambda_a8c7a4f4c07832cacff1022654013f1b_::operator()

- ea: `0x180097ba0`
- end: `0x180098bed`
- name: `_lambda_a8c7a4f4c07832cacff1022654013f1b_::operator()`
- size: `4173`
- prototype: ``
- caller_count: `2`
- callee_count: `31`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800095a0`
- `0x18007d8e0`

## callees

- `0x18000a974`
- `0x18000b3bc`
- `0x18000b7d0`
- `0x18000bd80`
- `0x18000e6e0`
- `0x18000e700`
- `0x18000fed0`
- `0x180013044`
- `0x1800135d8`
- `0x1800138e0`
- `0x18001423c`
- `0x180014468`
- `0x180018a54`
- `0x18002e1cc`
- `0x18002ece0`
- `0x18003bfc0`
- `0x1800415c0`
- `0x180041948`
- `0x18005d5e8`
- `0x18007c814`
- `0x18007fdec`
- `0x180097ba0`
- `0x180098bf4`
- `0x18009bdbc`
- `0x1800a55b0`
- `0x1800f0700`
- `0x18014d9e4`
- `0x180151240`
- `0x1801512a0`
- `0x18015131c`
- `0x180211010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180098904`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800989a5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180098904`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800989a5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180097fff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009802a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800980ff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180098130`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009815a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180098188`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800983c0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180098569`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180098596`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180097fff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009802a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800980ff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180098130`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009815a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180098188`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800983c0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180098569`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180098596`

## string_xrefs

- `0x180097eef`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180097f7e`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180098082`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x1800981e5`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180098380`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x18009852f`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180098943`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180098a48`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180098ab7`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180098b96`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall lambda_a8c7a4f4c07832cacff1022654013f1b_::operator()(OSIntegration::Tools::MoCOMHelper **a1)
{
  _QWORD *v2; // rcx
  int v3; // eax
  int v4; // ebx
  unsigned __int64 v5; // r9
  __int64 v6; // rdx
  struct IXMLDOMElement **v7; // r9
  int XMLElementFromQuery; // eax
  struct IXMLDOMElement **v9; // r9
  int v10; // eax
  int AttributeValueStringFromElement; // eax
  int LocalizedPathAttributeValueStringFromElement; // eax
  int v13; // eax
  int LocalizedStringAttributeValueStringFromElement; // eax
  int v15; // eax
  int v16; // eax
  OSIntegration::Tools::MoCOMHelper *v17; // rdx
  OSIntegration::Tools::MoCOMHelper *v18; // r8
  int v19; // r13d
  int v20; // r15d
  int v21; // esi
  char v22; // r12
  int v23; // eax
  __int64 v24; // rdx
  int v25; // eax
  int AttributeValueStringFromQuery; // eax
  __int64 v27; // rdx
  LPCWCH *v28; // rcx
  __int64 v29; // rdx
  const WCHAR *v30; // rbx
  unsigned int v31; // r8d
  int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rdx
  WCHAR *v35; // r14
  unsigned int v36; // r8d
  int HasGameOSPackageDependency; // eax
  __int64 v38; // rdx
  unsigned __int64 v39; // rdx
  WCHAR *v40; // r12
  OSIntegration::Tools::MoCOMHelper *v41; // rbx
  int v42; // ecx
  int v43; // eax
  int v44; // eax
  BOOL v45; // ebx
  WCHAR *v46; // r14
  int v47; // ecx
  struct IXMLDOMElementVtbl *lpVtbl; // rcx
  struct IXMLDOMElementVtbl *v49; // rcx
  void *v50; // rcx
  WCHAR *v52; // rsi
  OSIntegration::Tools::MoCOMHelper *v53; // rcx
  unsigned int v54; // r8d
  OSIntegration::Tools::MoCOMHelper *v55; // rcx
  OSIntegration::Tools::MoCOMHelper *v56; // rcx
  OSIntegration::Package **v57; // rax
  OSIntegration::Package *v58; // rcx
  int v59; // edx
  OSIntegration::Tools *PackageRootAsCommonString; // rax
  __int64 v61; // r9
  OSIntegration::Tools::MoCOMHelper *v62; // rcx
  unsigned __int16 *v63; // rdx
  int v64; // edx
  int v65; // eax
  __int64 v66; // rdx
  int v67; // eax
  unsigned __int64 v68; // rdx
  struct IXMLDOMElementVtbl *v69; // rcx
  struct IXMLDOMElementVtbl *v70; // rcx
  void *v71; // rcx
  int *v72; // [rsp+28h] [rbp-A9h]
  int *v73; // [rsp+28h] [rbp-A9h]
  int *v74; // [rsp+28h] [rbp-A9h]
  int *v75; // [rsp+30h] [rbp-A1h]
  int *v76; // [rsp+30h] [rbp-A1h]
  int *v77; // [rsp+30h] [rbp-A1h]
  struct IXMLDOMElement v78; // [rsp+38h] [rbp-99h] BYREF
  struct IXMLDOMElement v79[2]; // [rsp+40h] [rbp-91h] BYREF
  int v80; // [rsp+50h] [rbp-81h]
  struct IXMLDOMElement v81; // [rsp+58h] [rbp-79h] BYREF
  LPCWCH v82[2]; // [rsp+60h] [rbp-71h] BYREF
  int v83; // [rsp+70h] [rbp-61h]
  int v84; // [rsp+78h] [rbp-59h] BYREF
  int v85; // [rsp+7Ch] [rbp-55h] BYREF
  int v86; // [rsp+80h] [rbp-51h] BYREF
  unsigned __int16 *v87[2]; // [rsp+88h] [rbp-49h] BYREF
  int v88; // [rsp+98h] [rbp-39h]
  LPCWCH v89[2]; // [rsp+A0h] [rbp-31h] BYREF
  int v90; // [rsp+B0h] [rbp-21h]
  __int128 v91; // [rsp+B8h] [rbp-19h] BYREF
  int v92; // [rsp+C8h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+5Fh]
  struct IXMLDOMElement v94; // [rsp+138h] [rbp+67h] BYREF
  int v95; // [rsp+140h] [rbp+6Fh] BYREF
  int v96; // [rsp+148h] [rbp+77h] BYREF
  int v97; // [rsp+150h] [rbp+7Fh] BYREF

  v96 = 0;
  v91 = 0;
  v92 = 0;
  *(_OWORD *)v87 = 0;
  v88 = 0;
  v78.lpVtbl = 0;
  v81.lpVtbl = 0;
  v2 = (_QWORD *)((char *)*a1 + 592);
  if ( !*v2 )
    Microsoft::WRL::ComPtr<IXMLDOMElement>::operator=(v2, *(_QWORD *)a1[1]);
  v3 = Common::StringBuffer::SetValue(
         (OSIntegration::Tools::MoCOMHelper *)((char *)*a1 + 240),
         *((const unsigned __int16 **)*a1 + 4),
         *((_DWORD *)*a1 + 6));
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = (unsigned int)v3;
    v6 = 1379;
LABEL_229:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
      (const char *)v5,
      (int)v72);
    goto LABEL_230;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
  XMLElementFromQuery = Common::Xml::GetXMLElementFromQuery(
                          (OLECHAR *)L"./*[local-name()='VisualElements']",
                          *(const unsigned __int16 **)a1[1],
                          &v78,
                          v7);
  v4 = XMLElementFromQuery;
  if ( XMLElementFromQuery < 0 )
  {
    v5 = (unsigned int)XMLElementFromQuery;
    v6 = 1386;
    goto LABEL_229;
  }
  if ( !v78.lpVtbl )
  {
    v4 = -2146958844;
    v6 = 1388;
LABEL_228:
    v5 = (unsigned int)v4;
    goto LABEL_229;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
  v10 = Common::Xml::GetXMLElementFromQuery((OLECHAR *)L"../..", (const unsigned __int16 *)v78.lpVtbl, &v81, v9);
  v4 = v10;
  if ( v10 < 0 )
  {
    v5 = (unsigned int)v10;
    v6 = 1395;
    goto LABEL_229;
  }
  if ( !v81.lpVtbl )
  {
    v4 = -2146958844;
    v6 = 1397;
    goto LABEL_228;
  }
  AttributeValueStringFromElement = Common::Xml::GetAttributeValueStringFromElement(
                                      *(Common::Xml **)a1[1],
                                      (struct IXMLDOMElement *)&Appx::Packaging::Manifest::AttributeNameWithoutPrefix::Id,
                                      (const unsigned __int16 *)*a1 + 96,
                                      (struct Common::StringBuffer *)&v96,
                                      v72);
  v4 = AttributeValueStringFromElement;
  if ( AttributeValueStringFromElement < 0 )
  {
    v5 = (unsigned int)AttributeValueStringFromElement;
    v6 = 1405;
    goto LABEL_229;
  }
  LocalizedPathAttributeValueStringFromElement = OSIntegration::Tools::GetLocalizedPathAttributeValueStringFromElement(
                                                   *(OSIntegration::Tools **)a1[2],
                                                   (const struct OSIntegration::Package *)v78.lpVtbl,
                                                   (struct IXMLDOMElement *)&Appx::Packaging::Manifest::AttributeNameWithoutPrefix::Square150x150Logo,
                                                   (const unsigned __int16 *)v87,
                                                   (struct Common::StringBuffer *)&v96,
                                                   v75,
                                                   (int *)v78.lpVtbl);
  v4 = LocalizedPathAttributeValueStringFromElement;
  if ( LocalizedPathAttributeValueStringFromElement < 0 )
  {
    v5 = (unsigned int)LocalizedPathAttributeValueStringFromElement;
    v6 = 1415;
    goto LABEL_229;
  }
  if ( !v96 )
  {
    v13 = OSIntegration::Tools::GetLocalizedPathAttributeValueStringFromElement(
            *(OSIntegration::Tools **)a1[2],
            (const struct OSIntegration::Package *)v78.lpVtbl,
            (struct IXMLDOMElement *)&Appx::Packaging::Manifest::AttributeNameWithoutPrefix::Logo,
            (const unsigned __int16 *)v87,
            (struct Common::StringBuffer *)&v96,
            v76,
            (int *)v78.lpVtbl);
    v4 = v13;
    if ( v13 < 0 )
    {
      v5 = (unsigned int)v13;
      v6 = 1426;
      goto LABEL_229;
    }
  }
  if ( !v87[1] )
  {
    v4 = -2147467261;
    goto LABEL_227;
  }
  v4 = Windows::Internal::String::_InitializeHelper((OSIntegration::Tools::MoCOMHelper *)((char *)*a1 + 352), v87[1]);
  if ( v4 < 0 )
  {
LABEL_227:
    v6 = 1429;
    goto LABEL_228;
  }
  LocalizedStringAttributeValueStringFromElement = OSIntegration::Tools::GetLocalizedStringAttributeValueStringFromElement(
                                                     *(OSIntegration::Tools **)a1[2],
                                                     (const struct OSIntegration::Package *)v78.lpVtbl,
                                                     (struct IXMLDOMElement *)&Appx::Packaging::Manifest::AttributeNameWithoutPrefix::DisplayName,
                                                     (const unsigned __int16 *)v87,
                                                     (struct Common::StringBuffer *)&v96,
                                                     v76,
                                                     (int *)v78.lpVtbl);
  v4 = LocalizedStringAttributeValueStringFromElement;
  if ( LocalizedStringAttributeValueStringFromElement < 0 )
  {
    v5 = (unsigned int)LocalizedStringAttributeValueStringFromElement;
    v6 = 1438;
    goto LABEL_229;
  }
  if ( !v87[1] )
  {
    v4 = -2147467261;
    goto LABEL_225;
  }
  v4 = Windows::Internal::String::_InitializeHelper((OSIntegration::Tools::MoCOMHelper *)((char *)*a1 + 360), v87[1]);
  if ( v4 < 0 )
  {
LABEL_225:
    v6 = 1440;
    goto LABEL_228;
  }
  v15 = OSIntegration::Tools::GetLocalizedStringAttributeValueStringFromElement(
          *(OSIntegration::Tools **)a1[2],
          (const struct OSIntegration::Package *)v78.lpVtbl,
          (struct IXMLDOMElement *)&Appx::Packaging::Manifest::AttributeNameWithoutPrefix::Description,
          (const unsigned __int16 *)v87,
          (struct Common::StringBuffer *)&v96,
          v77,
          (int *)v78.lpVtbl);
  v4 = v15;
  if ( v15 < 0 )
  {
    v5 = (unsigned int)v15;
    v6 = 1449;
    goto LABEL_229;
  }
  if ( !v87[1] )
  {
    v4 = -2147467261;
    goto LABEL_223;
  }
  v4 = Windows::Internal::String::_InitializeHelper((OSIntegration::Tools::MoCOMHelper *)((char *)*a1 + 336), v87[1]);
  if ( v4 < 0 )
  {
LABEL_223:
    v6 = 1451;
    goto LABEL_228;
  }
  if ( *((_DWORD *)*a1 + 3) )
    goto LABEL_129;
  v16 = Common::Xml::GetAttributeValueStringFromElement(
          *(Common::Xml **)a1[1],
          (struct IXMLDOMElement *)&Appx::Packaging::Manifest::AttributeNameWithoutPrefix::StartPage,
          (const unsigned __int16 *)*a1 + 36,
          (struct Common::StringBuffer *)&v96,
          v72);
  v4 = v16;
  if ( v16 < 0 )
  {
    v5 = (unsigned int)v16;
    v6 = 1461;
    goto LABEL_229;
  }
  v18 = *a1;
  if ( v96 )
  {
    *((_DWORD *)v18 + 3) = 2;
LABEL_117:
    if ( !*((_DWORD *)*a1 + 3) )
    {
      **(_BYTE **)a1[3] = 0;
      lpVtbl = v81.lpVtbl;
      if ( v81.lpVtbl )
      {
        v81.lpVtbl = 0;
        (*((void (__fastcall **)(struct IXMLDOMElementVtbl *))lpVtbl->QueryInterface + 2))(lpVtbl);
      }
      v49 = v78.lpVtbl;
      if ( v78.lpVtbl )
      {
        v78.lpVtbl = 0;
        (*((void (__fastcall **)(struct IXMLDOMElementVtbl *))v49->QueryInterface + 2))(v49);
      }
      if ( v87[1] )
        operator delete(v87[1], (unsigned __int64)v17);
      v50 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      if ( v50 )
        operator delete(v50, (unsigned __int64)v17);
      return 0;
    }
LABEL_129:
    *(_OWORD *)&v79[0].lpVtbl = 0;
    v80 = 0;
    LODWORD(v94.lpVtbl) = 0;
    AttributeValueStringFromQuery = Common::Xml::GetAttributeValueStringFromQuery(
                                      (OLECHAR *)L"@*[local-name()='AppLifecycleBehavior']",
                                      *(const unsigned __int16 **)a1[1],
                                      v79,
                                      (struct Common::StringBuffer *)&v94,
                                      v72);
    v4 = AttributeValueStringFromQuery;
    if ( AttributeValueStringFromQuery < 0 )
    {
      v27 = 1731;
      goto LABEL_42;
    }
    v52 = (WCHAR *)v79[1].lpVtbl;
    if ( LODWORD(v94.lpVtbl) )
    {
      if ( CompareStringOrdinal((LPCWCH)v79[1].lpVtbl, -1, L"unmanaged", -1, 1) == 2 )
      {
        v53 = *a1;
        *((_DWORD *)*a1 + 155) = 0;
      }
      else
      {
        if ( CompareStringOrdinal(v52, -1, L"systemManaged", -1, 1) != 2 )
          wil::details::in1diag3::FailFast_Hr(retaddr, (void *)0x6D1, v54, (const char *)0x8000FFFFLL, (int)v73);
        v53 = *a1;
        *((_DWORD *)*a1 + 155) = 1;
      }
      *((_BYTE *)v53 + 624) = 1;
      *(_WORD *)((char *)v53 + 625) = *(_WORD *)((char *)&v94.lpVtbl + 5);
      *((_BYTE *)v53 + 627) = HIBYTE(v94.lpVtbl);
    }
    LOBYTE(v94.lpVtbl) = 0;
    v95 = 0;
    AttributeValueStringFromQuery = Common::Xml::GetAttributeValueBooleanFromQuery(
                                      (OLECHAR *)L"@*[local-name()='SupportsMultipleInstances']",
                                      *(const unsigned __int16 **)a1[1],
                                      &v94,
                                      (bool *)&v95,
                                      v73);
    v4 = AttributeValueStringFromQuery;
    if ( AttributeValueStringFromQuery < 0 )
    {
      v27 = 1755;
      goto LABEL_42;
    }
    if ( v95 )
    {
      v55 = *a1;
      *((_BYTE *)v55 + 628) = v94.lpVtbl;
      *((_BYTE *)v55 + 629) = 1;
    }
    v56 = *a1;
    if ( (unsigned int)(*((_DWORD *)*a1 + 3) - 3) > 9 )
    {
LABEL_176:
      if ( (unsigned int)(*((_DWORD *)*a1 + 3) - 1) <= 1 )
      {
        AttributeValueStringFromQuery = OSIntegration::Tools::MoCOMHelper::ConfigureWWAHostAsExeServer(
                                          *a1,
                                          *(const struct OSIntegration::Package **)a1[2]);
        v4 = AttributeValueStringFromQuery;
        if ( AttributeValueStringFromQuery < 0 )
        {
          v27 = 1856;
          goto LABEL_42;
        }
        AttributeValueStringFromQuery = OSIntegration::Tools::AddStringPropertyToContainer(
                                          L"NavigateTo",
                                          *((unsigned __int16 **)*a1 + 10),
                                          (__int64)*a1 + 520);
        v4 = AttributeValueStringFromQuery;
        if ( AttributeValueStringFromQuery < 0 )
        {
          v27 = 1861;
          goto LABEL_42;
        }
        AttributeValueStringFromQuery = OSIntegration::Tools::AddStringPropertyToContainer(
                                          L"ExeHost",
                                          L"wwahost.exe",
                                          (__int64)*a1 + 520);
        v4 = AttributeValueStringFromQuery;
        if ( AttributeValueStringFromQuery < 0 )
        {
          v27 = 1866;
          goto LABEL_42;
        }
        AttributeValueStringFromQuery = OSIntegration::Tools::AddDwordPropertyToContainer(L"AppObject.Aliased");
        v4 = AttributeValueStringFromQuery;
        if ( AttributeValueStringFromQuery < 0 )
        {
          v27 = 1872;
          goto LABEL_42;
        }
        AttributeValueStringFromQuery = OSIntegration::Tools::AddStringPropertyToContainer(
                                          L"AppObject.EntryPoint",
                                          *((unsigned __int16 **)*a1 + 10),
                                          (__int64)*a1 + 520);
        v4 = AttributeValueStringFromQuery;
        if ( AttributeValueStringFromQuery < 0 )
        {
          v27 = 1878;
          goto LABEL_42;
        }
      }
      v64 = *((_DWORD *)*a1 + 3);
      if ( ((v64 - 2) & 0xFFFFFFFC) == 0
        && v64 != 3
        && !(unsigned int)_o__wcsicmp(*((_QWORD *)*a1 + 4), L"Windows.Launch") )
      {
        *(_OWORD *)v82 = 0;
        v83 = 0;
        v65 = Common::Xml::GetAttributeValueStringFromElement(
                *(Common::Xml **)a1[1],
                (struct IXMLDOMElement *)&stru_180241938,
                (const unsigned __int16 *)v82,
                (struct Common::StringBuffer *)&v96,
                v73);
        v4 = v65;
        if ( v65 < 0 )
        {
          v66 = 1892;
LABEL_192:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v66,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
            (const char *)(unsigned int)v65,
            (int)v73);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v82);
          goto LABEL_43;
        }
        if ( v96 )
        {
          v65 = OSIntegration::Tools::AddStringPropertyToContainer(
                  (unsigned __int16 *)&stru_180241938,
                  (unsigned __int16 *)v82[1],
                  (__int64)*a1 + 488);
          v4 = v65;
          if ( v65 < 0 )
          {
            v66 = 1899;
            goto LABEL_192;
          }
        }
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v82);
      }
      if ( !(unsigned int)_o__wcsicmp(*((_QWORD *)*a1 + 4), L"Windows.Launch") )
      {
        LOBYTE(v94.lpVtbl) = 0;
        AttributeValueStringFromQuery = Common::Xml::GetAttributeValueBooleanFromQuery(
                                          (OLECHAR *)L"@*[local-name()='SupportsMultipleInstances']",
                                          *(const unsigned __int16 **)a1[1],
                                          &v94,
                                          (bool *)&v96,
                                          v73);
        v4 = AttributeValueStringFromQuery;
        if ( AttributeValueStringFromQuery < 0 )
        {
          v27 = 1910;
          goto LABEL_42;
        }
        if ( v96 )
        {
          if ( LOBYTE(v94.lpVtbl) )
          {
            AttributeValueStringFromQuery = OSIntegration::Tools::AddDwordPropertyToContainer(L"SupportsMultipleInstances");
            v4 = AttributeValueStringFromQuery;
            if ( AttributeValueStringFromQuery < 0 )
            {
              v27 = 1915;
              goto LABEL_42;
            }
          }
        }
        *(_OWORD *)v82 = 0;
        v83 = 0;
        v65 = Common::Xml::GetAttributeValueStringFromQuery(
                (OLECHAR *)L"@*[local-name()='Subsystem']",
                *(const unsigned __int16 **)a1[1],
                (const struct IXMLDOMElement *)v82,
                (struct Common::StringBuffer *)&v96,
                v73);
        v4 = v65;
        if ( v65 < 0 )
        {
          v66 = 1923;
          goto LABEL_192;
        }
        if ( v96 )
        {
          v65 = OSIntegration::Tools::AddStringPropertyToContainer(
                  L"Subsystem",
                  (unsigned __int16 *)v82[1],
                  (__int64)*a1 + 488);
          v4 = v65;
          if ( v65 < 0 )
          {
            v66 = 1928;
            goto LABEL_192;
          }
        }
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v82);
      }
      v67 = OSIntegration::Tools::MoCOMHelper::ParsePackage(
              *a1,
              *(const struct OSIntegration::Package **)a1[2],
              (struct IXMLDOMElement *)v81.lpVtbl);
      v4 = v67;
      if ( v67 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x78F,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
          (const char *)(unsigned int)v67,
          (int)v73);
        if ( v52 )
          operator delete(v52, v68);
        v69 = v81.lpVtbl;
        if ( v81.lpVtbl )
        {
          v81.lpVtbl = 0;
          (*((void (__fastcall **)(struct IXMLDOMElementVtbl *))v69->QueryInterface + 2))(v69);
        }
        v70 = v78.lpVtbl;
        if ( v78.lpVtbl )
        {
          v78.lpVtbl = 0;
          (*((void (__fastcall **)(struct IXMLDOMElementVtbl *))v70->QueryInterface + 2))(v70);
        }
        if ( v87[1] )
          operator delete(v87[1], v68);
        v71 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        if ( v71 )
          operator delete(v71, v68);
        return (unsigned int)v4;
      }
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v79);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v87);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v91);
      return 0;
    }
    if ( !*((_QWORD *)v56 + 37) )
    {
      if ( !*((_QWORD *)v56 + 16) )
      {
        AttributeValueStringFromQuery = Common::Xml::GetAttributeValueStringFromElement(
                                          *(Common::Xml **)a1[1],
                                          (struct IXMLDOMElement *)&Appx::Packaging::Manifest::AttributeNameWithoutPrefix::Executable,
                                          (const unsigned __int16 *)v56 + 60,
                                          (struct Common::StringBuffer *)&v96,
                                          v73);
        v4 = AttributeValueStringFromQuery;
        if ( AttributeValueStringFromQuery < 0 )
        {
          v27 = 1784;
          goto LABEL_42;
        }
      }
      if ( *((_QWORD *)*a1 + 16) )
      {
        v57 = (OSIntegration::Package **)a1[2];
        v58 = *v57;
        if ( !*((_BYTE *)*v57 + 400) || *((_BYTE *)v58 + 368) )
        {
          if ( Common::Deployment::Platform::g_platform != 5 )
            goto LABEL_157;
          v59 = *((_DWORD *)*a1 + 3);
          if ( (unsigned int)(v59 - 6) <= 1 )
          {
            AttributeValueStringFromQuery = OSIntegration::Tools::MoCOMHelper::ConfigureXboxEraProxyAppAsExeServer(*a1);
            v4 = AttributeValueStringFromQuery;
            if ( AttributeValueStringFromQuery < 0 )
            {
              v27 = 1796;
              goto LABEL_42;
            }
            goto LABEL_160;
          }
          if ( v59 == 10 )
          {
            AttributeValueStringFromQuery = OSIntegration::Tools::MoCOMHelper::ConfigureGameCoreProxyAppAsExeServer(*a1);
            v4 = AttributeValueStringFromQuery;
            if ( AttributeValueStringFromQuery < 0 )
            {
              v27 = 1800;
              goto LABEL_42;
            }
          }
          else
          {
LABEL_157:
            PackageRootAsCommonString = OSIntegration::Package::GetPackageRootAsCommonString(v58);
            AttributeValueStringFromQuery = OSIntegration::Tools::ConcatenatePaths(
                                              PackageRootAsCommonString,
                                              (const struct Common::COMMON_STRING *)(v61 + 120),
                                              (const struct Common::COMMON_STRING *)(v61 + 144),
                                              (struct Common::StringBuffer *)v61);
            v4 = AttributeValueStringFromQuery;
            if ( AttributeValueStringFromQuery < 0 )
            {
              v27 = 1807;
              goto LABEL_42;
            }
            *((_BYTE *)*a1 + 630) = 1;
          }
        }
      }
    }
LABEL_160:
    v62 = *a1;
    if ( *((_DWORD *)*a1 + 3) <= 7u || *((_DWORD *)v62 + 3) == 10 )
    {
      if ( *((_QWORD *)v62 + 37) || *((_QWORD *)v62 + 16) )
      {
        AttributeValueStringFromQuery = OSIntegration::Tools::MoCOMHelper::ConfigureMCAExeServer(
                                          v62,
                                          *(const struct OSIntegration::Package **)a1[2]);
        v4 = AttributeValueStringFromQuery;
        if ( AttributeValueStringFromQuery < 0 )
        {
          v27 = 1820;
          goto LABEL_42;
        }
      }
      if ( *((_DWORD *)*a1 + 3) == 5 )
      {
        AttributeValueStringFromQuery = OSIntegration::Tools::MoCOMHelper::ConfigureAGHostAsExeServer(*a1);
        v4 = AttributeValueStringFromQuery;
        if ( AttributeValueStringFromQuery < 0 )
        {
          v27 = 1827;
          goto LABEL_42;
        }
      }
      AttributeValueStringFromQuery = OSIntegration::Tools::AddDwordPropertyToContainer(L"AppObject.Aliased");
      v4 = AttributeValueStringFromQuery;
      if ( AttributeValueStringFromQuery < 0 )
      {
        v27 = 1834;
        goto LABEL_42;
      }
      AttributeValueStringFromQuery = OSIntegration::Tools::AddStringPropertyToContainer(
                                        L"AppObject.EntryPoint",
                                        *((unsigned __int16 **)*a1 + 13),
                                        (__int64)*a1 + 520);
      v4 = AttributeValueStringFromQuery;
      if ( AttributeValueStringFromQuery < 0 )
      {
        v27 = 1840;
        goto LABEL_42;
      }
      v63 = (unsigned __int16 *)*((_QWORD *)*a1 + 47);
      if ( v63 )
      {
        AttributeValueStringFromQuery = OSIntegration::Tools::AddStringPropertyToContainer(
                                          L"AppObject.RuntimeType",
                                          v63,
                                          (__int64)*a1 + 520);
        v4 = AttributeValueStringFromQuery;
        if ( AttributeValueStringFromQuery < 0 )
        {
          v27 = 1849;
          goto LABEL_42;
        }
      }
    }
    goto LABEL_176;
  }
  v86 = 0;
  v19 = 0;
  v97 = 0;
  v20 = 0;
  v84 = 0;
  v21 = 0;
  v85 = 0;
  v22 = 0;
  LOBYTE(v94.lpVtbl) = 0;
  LOBYTE(v95) = 0;
  v23 = Common::Xml::GetAttributeValueStringFromQuery(
          (OLECHAR *)L"@*[local-name()='HostId']",
          *(const unsigned __int16 **)a1[1],
          (const struct IXMLDOMElement *)v18 + 36,
          (struct Common::StringBuffer *)&v86,
          v72);
  v4 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB05,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
      (const char *)(unsigned int)v23,
      (int)v72);
    v6 = 1476;
    goto LABEL_228;
  }
  if ( v86 )
  {
    v25 = OSIntegration::Tools::MoCOMHelper::ResolveHostRuntimeAttributes(
            *a1,
            *(const struct OSIntegration::Package **)a1[2]);
    v4 = v25;
    if ( v25 < 0 )
    {
      v5 = (unsigned int)v25;
      v6 = 1480;
      goto LABEL_229;
    }
    goto LABEL_100;
  }
  *(_OWORD *)&v79[0].lpVtbl = 0;
  v80 = 0;
  LOBYTE(v24) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloActivationOverride>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_AppSiloActivationOverride>::GetImpl'::`2'::impl,
    v24);
  AttributeValueStringFromQuery = Common::Xml::GetAttributeValueStringFromQuery(
                                    (OLECHAR *)L"@uap18:TrustLevel",
                                    *(const unsigned __int16 **)a1[1],
                                    v79,
                                    (struct Common::StringBuffer *)&v97,
                                    v72);
  v4 = AttributeValueStringFromQuery;
  if ( AttributeValueStringFromQuery >= 0 )
  {
    v19 = v97;
    if ( v97 )
      goto LABEL_49;
    AttributeValueStringFromQuery = Common::Xml::GetAttributeValueStringFromQuery(
                                      (OLECHAR *)L"@*[local-name()='TrustLevel']",
                                      *(const unsigned __int16 **)a1[1],
                                      v79,
                                      (struct Common::StringBuffer *)&v97,
                                      v73);
    v4 = AttributeValueStringFromQuery;
    if ( AttributeValueStringFromQuery < 0 )
    {
      v27 = 1502;
      goto LABEL_42;
    }
    v19 = v97;
    if ( v97 )
    {
LABEL_49:
      v30 = (const WCHAR *)v79[1].lpVtbl;
      if ( CompareStringOrdinal((LPCWCH)v79[1].lpVtbl, -1, L"appContainer", -1, 1) == 2 )
      {
        *((_DWORD *)*a1 + 153) = 0;
      }
      else
      {
        if ( CompareStringOrdinal(v30, -1, L"mediumIL", -1, 1) != 2 )
          wil::details::in1diag3::FailFast_Hr(retaddr, (void *)0x5F8, v31, (const char *)0x8000FFFFLL, (int)v73);
        *((_DWORD *)*a1 + 153) = 1;
      }
    }
    *(_OWORD *)v89 = 0;
    v90 = 0;
    LOBYTE(v29) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloActivationOverride>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_AppSiloActivationOverride>::GetImpl'::`2'::impl,
      v29);
    v32 = Common::Xml::GetAttributeValueStringFromQuery(
            (OLECHAR *)L"@uap18:RuntimeBehavior",
            *(const unsigned __int16 **)a1[1],
            (const struct IXMLDOMElement *)v89,
            (struct Common::StringBuffer *)&v84,
            v73);
    v4 = v32;
    if ( v32 < 0 )
    {
      v33 = 1541;
LABEL_55:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v33,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)(unsigned int)v32,
        (int)v74);
LABEL_56:
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v89);
      goto LABEL_43;
    }
    v20 = v84;
    if ( v84 )
      goto LABEL_62;
    v32 = Common::Xml::GetAttributeValueStringFromQuery(
            (OLECHAR *)L"@*[local-name()='RuntimeBehavior']",
            *(const unsigned __int16 **)a1[1],
            (const struct IXMLDOMElement *)v89,
            (struct Common::StringBuffer *)&v84,
            v74);
    v4 = v32;
    if ( v32 < 0 )
    {
      v33 = 1550;
      goto LABEL_55;
    }
    v20 = v84;
    if ( v84 )
    {
LABEL_62:
      v35 = (WCHAR *)v89[1];
      if ( CompareStringOrdinal(v89[1], -1, L"windowsApp", -1, 1) == 2 )
      {
        *((_DWORD *)*a1 + 152) = 0;
      }
      else if ( CompareStringOrdinal(v35, -1, L"packagedClassicApp", -1, 1) == 2 )
      {
        *((_DWORD *)*a1 + 152) = 1;
      }
      else if ( CompareStringOrdinal(v35, -1, L"win32App", -1, 1) == 2 )
      {
        *((_DWORD *)*a1 + 152) = 2;
      }
      else
      {
        if ( CompareStringOrdinal(v35, -1, L"appSilo", -1, 1) != 2 )
          wil::details::in1diag3::FailFast_Hr(retaddr, (void *)0x634, v36, (const char *)0x8000FFFFLL, (int)v74);
        *((_DWORD *)*a1 + 152) = 3;
      }
    }
    else
    {
      v35 = (WCHAR *)v89[1];
    }
    *(_OWORD *)v82 = 0;
    v83 = 0;
    LOBYTE(v34) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloActivationOverride>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_AppSiloActivationOverride>::GetImpl'::`2'::impl,
      v34);
    HasGameOSPackageDependency = Common::Xml::GetAttributeValueStringFromQuery(
                                   (OLECHAR *)L"@uap18:EntryPoint",
                                   *(const unsigned __int16 **)a1[1],
                                   (const struct IXMLDOMElement *)v82,
                                   (struct Common::StringBuffer *)&v85,
                                   v74);
    v4 = HasGameOSPackageDependency;
    if ( HasGameOSPackageDependency < 0 )
    {
      v38 = 1600;
LABEL_72:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v38,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)(unsigned int)HasGameOSPackageDependency,
        (int)v72);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v82);
      goto LABEL_56;
    }
    v21 = v85;
    if ( v85 )
      goto LABEL_78;
    HasGameOSPackageDependency = Common::Xml::GetAttributeValueStringFromElement(
                                   *(Common::Xml **)a1[1],
                                   (struct IXMLDOMElement *)&Appx::Packaging::Manifest::AttributeNameWithoutPrefix::EntryPoint,
                                   (const unsigned __int16 *)v82,
                                   (struct Common::StringBuffer *)&v85,
                                   v72);
    v4 = HasGameOSPackageDependency;
    if ( HasGameOSPackageDependency < 0 )
    {
      v38 = 1609;
      goto LABEL_72;
    }
    v21 = v85;
    if ( v85 )
    {
LABEL_78:
      v40 = (WCHAR *)v82[1];
      HasGameOSPackageDependency = Common::StringBuffer::SetValueFromString(
                                     (OSIntegration::Tools::MoCOMHelper *)((char *)*a1 + 96),
                                     v82[1]);
      v4 = HasGameOSPackageDependency;
      if ( HasGameOSPackageDependency < 0 )
      {
        v38 = 1624;
        goto LABEL_72;
      }
      if ( Common::Deployment::Platform::g_platform == 5 )
      {
        HasGameOSPackageDependency = OSIntegration::Package::GetHasGameOSPackageDependency(
                                       *(OSIntegration::Package **)a1[2],
                                       (bool *)&v95);
        v4 = HasGameOSPackageDependency;
        if ( HasGameOSPackageDependency < 0 )
        {
          v38 = 1629;
          goto LABEL_72;
        }
        LOBYTE(v94.lpVtbl) = v95;
      }
      v41 = *a1;
      v95 = Common::String::Equals(
              *((const unsigned __int16 **)*a1 + 13),
              *((_DWORD *)*a1 + 24),
              off_1802E07C0,
              `OSIntegration::Tools::MoCOMHelper::CentennialEntryPointValue'::`2'::result);
      v42 = Common::String::Equals(
              *((const unsigned __int16 **)v41 + 13),
              *((_DWORD *)v41 + 24),
              off_1802E07B0,
              `OSIntegration::Tools::MoCOMHelper::CentennialInAppcontainerEntryPointValue'::`2'::result);
      v43 = v95;
      if ( !v19 )
      {
        if ( v95 )
        {
          *((_DWORD *)v41 + 153) = 1;
        }
        else if ( v42 )
        {
          *((_DWORD *)v41 + 153) = 0;
        }
      }
      if ( !v20 && (v43 || v42) )
        *((_DWORD *)*a1 + 152) = 1;
    }
    else
    {
      v40 = (WCHAR *)v82[1];
    }
    if ( v40 )
      operator delete(v40, v39);
    if ( v35 )
      operator delete(v35, v39);
    if ( v79[1].lpVtbl )
      operator delete(v79[1].lpVtbl, v39);
    v22 = (char)v94.lpVtbl;
LABEL_100:
    *(_OWORD *)v82 = 0;
    v83 = 0;
    LODWORD(v94.lpVtbl) = 0;
    v44 = Common::Xml::GetAttributeValueStringFromQuery(
            (OLECHAR *)L"@*[local-name()='BaseNamedObjectsIsolation']",
            *(const unsigned __int16 **)a1[1],
            (const struct IXMLDOMElement *)v82,
            (struct Common::StringBuffer *)&v94,
            v72);
    v4 = v44;
    if ( v44 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x681,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
        (const char *)(unsigned int)v44,
        (int)v72);
      v28 = v82;
      goto LABEL_44;
    }
    v45 = 0;
    v46 = (WCHAR *)v82[1];
    if ( LODWORD(v94.lpVtbl) )
      v45 = CompareStringOrdinal(v82[1], -1, L"package", -1, 1) == 2;
    *((_DWORD *)*a1 + 154) = v45;
    if ( v21 || v19 || v20 || v86 )
    {
      v17 = *a1;
      if ( *(_QWORD *)(*(_QWORD *)a1[2] + 432LL) == 12 )
      {
        *((_DWORD *)v17 + 3) = 7;
      }
      else
      {
        v47 = *((_DWORD *)v17 + 152);
        if ( ((v47 - 1) & 0xFFFFFFFD) != 0 )
        {
          if ( v47 == 2 )
            *((_DWORD *)v17 + 3) = 11;
          else
            *((_DWORD *)v17 + 3) = v22 != 0 ? 10 : 4;
        }
        else
        {
          *((_DWORD *)v17 + 3) = 8;
        }
      }
    }
    if ( v46 )
      operator delete(v46, (unsigned __int64)v17);
    goto LABEL_117;
  }
  v27 = 1493;
LABEL_42:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v27,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
    (const char *)(unsigned int)AttributeValueStringFromQuery,
    (int)v73);
LABEL_43:
  v28 = (LPCWCH *)v79;
LABEL_44:
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v28);
LABEL_230:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v87);
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v91);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180097ba0  mov     rax, rsp
0x180097ba3  push    rbp
0x180097ba4  push    rbx
0x180097ba5  push    rsi
0x180097ba6  push    rdi
0x180097ba7  push    r12
0x180097ba9  push    r13
0x180097bab  push    r14
0x180097bad  push    r15
0x180097baf  lea     rbp, [rax-5Fh]
0x180097bb3  sub     rsp, 0E8h
0x180097bba  movaps  xmmword ptr [rax-58h], xmm6
0x180097bbe  mov     rdi, rcx
0x180097bc1  xor     r14d, r14d
0x180097bc4  mov     [rbp+57h+arg_10], r14d
0x180097bc8  xorps   xmm6, xmm6
0x180097bcb  movups  [rbp+57h+var_70], xmm6
0x180097bcf  mov     [rbp+57h+var_60], r14d
0x180097bd3  xorps   xmm0, xmm0
0x180097bd6  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x180097bda  mov     [rbp+57h+var_90], r14d
0x180097bde  mov     [rsp+120h+var_F0.lpVtbl], r14; int *
0x180097be3  mov     [rbp+57h+var_D0.lpVtbl], r14
0x180097be7  mov     rcx, [rcx]
0x180097bea  add     rcx, 250h
0x180097bf1  cmp     [rcx], r14
0x180097bf4  jnz     short loc_180097C02
0x180097bf6  mov     rdx, [rdi+8]
0x180097bfa  mov     rdx, [rdx]
0x180097bfd  call    ??4?$ComPtr@UIXMLDOMElement@@@WRL@Microsoft@@QEAAAEAV012@PEAUIXMLDOMElement@@@Z; Microsoft::WRL::ComPtr<IXMLDOMElement>::operator=(IXMLDOMElement *)
0x180097c02  mov     rdx, [rdi]
0x180097c05  lea     rcx, [rdx+0F0h]; this
0x180097c0c  mov     r8d, [rdx+18h]; unsigned int
0x180097c10  mov     rdx, [rdx+20h]; unsigned __int16 *
0x180097c14  call    ?SetValue@StringBuffer@Common@@QEAAJPEBGK@Z; Common::StringBuffer::SetValue(ushort const *,ulong)
0x180097c19  mov     ebx, eax
0x180097c1b  test    eax, eax
0x180097c1d  jns     short loc_180097C2C
0x180097c1f  mov     r9d, eax
0x180097c22  mov     edx, 563h
0x180097c27  jmp     loc_180098B96
0x180097c2c  lea     rcx, [rsp+120h+var_F0]
0x180097c31  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180097c36  mov     rdx, [rdi+8]
0x180097c3a  lea     r8, [rsp+120h+var_F0]; struct IXMLDOMElement *
0x180097c3f  mov     rdx, [rdx]; unsigned __int16 *
0x180097c42  lea     rcx, aLocalNameVisua_0; "./*[local-name()='VisualElements']"
0x180097c49  call    ?GetXMLElementFromQuery@Xml@Common@@YAJPEBGPEAUIXMLDOMElement@@PEAPEAU3@@Z; Common::Xml::GetXMLElementFromQuery(ushort const *,IXMLDOMElement *,IXMLDOMElement * *)
0x180097c4e  mov     ebx, eax
0x180097c50  test    eax, eax
0x180097c52  jns     short loc_180097C61
0x180097c54  mov     r9d, eax
0x180097c57  mov     edx, 56Ah
0x180097c5c  jmp     loc_180098B96
0x180097c61  cmp     [rsp+120h+var_F0.lpVtbl], r14
0x180097c66  jnz     short loc_180097C77
0x180097c68  mov     ebx, 80080204h
0x180097c6d  mov     edx, 56Ch
0x180097c72  jmp     loc_180098B93
0x180097c77  lea     rcx, [rbp+57h+var_D0]
0x180097c7b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180097c80  lea     r8, [rbp+57h+var_D0]; struct IXMLDOMElement *
0x180097c84  mov     rdx, [rsp+120h+var_F0.lpVtbl]; unsigned __int16 *
0x180097c89  lea     rcx, asc_18023F560; "../.."
0x180097c90  call    ?GetXMLElementFromQuery@Xml@Common@@YAJPEBGPEAUIXMLDOMElement@@PEAPEAU3@@Z; Common::Xml::GetXMLElementFromQuery(ushort const *,IXMLDOMElement *,IXMLDOMElement * *)
0x180097c95  mov     ebx, eax
0x180097c97  test    eax, eax
0x180097c99  jns     short loc_180097CA8
0x180097c9b  mov     r9d, eax
0x180097c9e  mov     edx, 573h
0x180097ca3  jmp     loc_180098B96
0x180097ca8  cmp     [rbp+57h+var_D0.lpVtbl], r14
0x180097cac  jnz     short loc_180097CBD
0x180097cae  mov     ebx, 80080204h
0x180097cb3  mov     edx, 575h
0x180097cb8  jmp     loc_180098B93
0x180097cbd  mov     r8, [rdi]
0x180097cc0  add     r8, 0C0h; unsigned __int16 *
0x180097cc7  mov     rcx, [rdi+8]
0x180097ccb  lea     r9, [rbp+57h+arg_10]; struct Common::StringBuffer *
0x180097ccf  lea     rdx, ?Id@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; struct IXMLDOMElement *
0x180097cd6  mov     rcx, [rcx]; this
0x180097cd9  call    ?GetAttributeValueStringFromElement@Xml@Common@@YAJPEAUIXMLDOMElement@@PEBGAEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromElement(IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)
0x180097cde  mov     ebx, eax
0x180097ce0  test    eax, eax
0x180097ce2  jns     short loc_180097CF1
0x180097ce4  mov     r9d, eax
0x180097ce7  mov     edx, 57Dh
0x180097cec  jmp     loc_180098B96
0x180097cf1  mov     rcx, [rdi+10h]
0x180097cf5  lea     rax, [rbp+57h+arg_10]
0x180097cf9  mov     [rsp+20h], rax; int
0x180097cfe  lea     r9, [rbp+57h+var_A0]; unsigned __int16 *
0x180097d02  lea     r8, ?Square150x150Logo@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; struct IXMLDOMElement *
0x180097d09  mov     rdx, [rsp+120h+var_F0.lpVtbl]; struct OSIntegration::Package *
0x180097d0e  mov     rcx, [rcx]; this
0x180097d11  call    ?GetLocalizedPathAttributeValueStringFromElement@Tools@OSIntegration@@YAJPEBVPackage@2@PEAUIXMLDOMElement@@PEBGPEAVStringBuffer@Common@@PEAH4@Z; OSIntegration::Tools::GetLocalizedPathAttributeValueStringFromElement(OSIntegration::Package const *,IXMLDOMElement *,ushort const *,Common::StringBuffer *,int *,int *)
0x180097d16  mov     ebx, eax
0x180097d18  test    eax, eax
0x180097d1a  jns     short loc_180097D29
0x180097d1c  mov     r9d, eax
0x180097d1f  mov     edx, 587h
0x180097d24  jmp     loc_180098B96
0x180097d29  cmp     [rbp+57h+arg_10], r14d
0x180097d2d  jnz     short loc_180097D67
0x180097d2f  mov     rcx, [rdi+10h]
0x180097d33  lea     rax, [rbp+57h+arg_10]
0x180097d37  mov     [rsp+20h], rax; struct Common::StringBuffer *
0x180097d3c  lea     r9, [rbp+57h+var_A0]; unsigned __int16 *
0x180097d40  lea     r8, ?Logo@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; struct IXMLDOMElement *
0x180097d47  mov     rdx, [rsp+120h+var_F0.lpVtbl]; struct OSIntegration::Package *
0x180097d4c  mov     rcx, [rcx]; this
0x180097d4f  call    ?GetLocalizedPathAttributeValueStringFromElement@Tools@OSIntegration@@YAJPEBVPackage@2@PEAUIXMLDOMElement@@PEBGPEAVStringBuffer@Common@@PEAH4@Z; OSIntegration::Tools::GetLocalizedPathAttributeValueStringFromElement(OSIntegration::Package const *,IXMLDOMElement *,ushort const *,Common::StringBuffer *,int *,int *)
0x180097d54  mov     ebx, eax
0x180097d56  test    eax, eax
0x180097d58  jns     short loc_180097D67
0x180097d5a  mov     r9d, eax
0x180097d5d  mov     edx, 592h
0x180097d62  jmp     loc_180098B96
0x180097d67  mov     rdx, [rbp+57h+var_A0+8]; unsigned __int16 *
0x180097d6b  test    rdx, rdx
0x180097d6e  jz      loc_180098B89
0x180097d74  mov     rcx, [rdi]
0x180097d77  add     rcx, 160h; this
0x180097d7e  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x180097d83  mov     ebx, eax
0x180097d85  test    eax, eax
0x180097d87  js      loc_180098B8E
0x180097d8d  mov     rcx, [rdi+10h]
0x180097d91  lea     rax, [rbp+57h+arg_10]
0x180097d95  mov     [rsp+20h], rax; struct Common::StringBuffer *
0x180097d9a  lea     r9, [rbp+57h+var_A0]; unsigned __int16 *
0x180097d9e  lea     r8, ?DisplayName@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; struct IXMLDOMElement *
0x180097da5  mov     rdx, [rsp+120h+var_F0.lpVtbl]; struct OSIntegration::Package *
0x180097daa  mov     rcx, [rcx]; this
0x180097dad  call    ?GetLocalizedStringAttributeValueStringFromElement@Tools@OSIntegration@@YAJPEBVPackage@2@PEAUIXMLDOMElement@@PEBGPEAVStringBuffer@Common@@PEAH4@Z; OSIntegration::Tools::GetLocalizedStringAttributeValueStringFromElement(OSIntegration::Package const *,IXMLDOMElement *,ushort const *,Common::StringBuffer *,int *,int *)
0x180097db2  mov     ebx, eax
0x180097db4  test    eax, eax
0x180097db6  jns     short loc_180097DC5
0x180097db8  mov     r9d, eax
0x180097dbb  mov     edx, 59Eh
0x180097dc0  jmp     loc_180098B96
0x180097dc5  mov     rdx, [rbp+57h+var_A0+8]; unsigned __int16 *
0x180097dc9  test    rdx, rdx
0x180097dcc  jz      loc_180098B7D
0x180097dd2  mov     rcx, [rdi]
0x180097dd5  add     rcx, 168h; this
0x180097ddc  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x180097de1  mov     ebx, eax
0x180097de3  test    eax, eax
0x180097de5  js      loc_180098B82
0x180097deb  mov     rcx, [rdi+10h]
0x180097def  lea     rax, [rbp+57h+arg_10]
0x180097df3  mov     [rsp+20h], rax; int
0x180097df8  lea     r9, [rbp+57h+var_A0]; unsigned __int16 *
0x180097dfc  lea     r8, ?Description@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; struct IXMLDOMElement *
0x180097e03  mov     rdx, [rsp+120h+var_F0.lpVtbl]; struct OSIntegration::Package *
0x180097e08  mov     rcx, [rcx]; this
0x180097e0b  call    ?GetLocalizedStringAttributeValueStringFromElement@Tools@OSIntegration@@YAJPEBVPackage@2@PEAUIXMLDOMElement@@PEBGPEAVStringBuffer@Common@@PEAH4@Z; OSIntegration::Tools::GetLocalizedStringAttributeValueStringFromElement(OSIntegration::Package const *,IXMLDOMElement *,ushort const *,Common::StringBuffer *,int *,int *)
0x180097e10  mov     ebx, eax
0x180097e12  test    eax, eax
0x180097e14  jns     short loc_180097E23
0x180097e16  mov     r9d, eax
0x180097e19  mov     edx, 5A9h
0x180097e1e  jmp     loc_180098B96
0x180097e23  mov     rdx, [rbp+57h+var_A0+8]; unsigned __int16 *
0x180097e27  test    rdx, rdx
0x180097e2a  jz      loc_180098B71
0x180097e30  mov     rcx, [rdi]
0x180097e33  add     rcx, 150h; this
0x180097e3a  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x180097e3f  mov     ebx, eax
0x180097e41  test    eax, eax
0x180097e43  js      loc_180098B76
0x180097e49  mov     r8, [rdi]
0x180097e4c  mov     r15d, 1
0x180097e52  cmp     [r8+0Ch], r14d
0x180097e56  jnz     loc_1800984F7
0x180097e5c  add     r8, 48h ; 'H'; unsigned __int16 *
0x180097e60  mov     rcx, [rdi+8]
0x180097e64  lea     r9, [rbp+57h+arg_10]; struct Common::StringBuffer *
0x180097e68  lea     rdx, ?StartPage@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; struct IXMLDOMElement *
0x180097e6f  mov     rcx, [rcx]; this
0x180097e72  call    ?GetAttributeValueStringFromElement@Xml@Common@@YAJPEAUIXMLDOMElement@@PEBGAEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromElement(IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)
0x180097e77  mov     ebx, eax
0x180097e79  test    eax, eax
0x180097e7b  jns     short loc_180097E8A
0x180097e7d  mov     r9d, eax
0x180097e80  mov     edx, 5B5h
0x180097e85  jmp     loc_180098B96
0x180097e8a  mov     r8, [rdi]
0x180097e8d  cmp     [rbp+57h+arg_10], r14d
0x180097e91  jz      short loc_180097EA0
0x180097e93  mov     dword ptr [r8+0Ch], 2
0x180097e9b  jmp     loc_180098456
0x180097ea0  mov     [rbp+57h+var_A8], r14d
0x180097ea4  mov     r13d, r14d
0x180097ea7  mov     [rbp+57h+arg_18], r14d
0x180097eab  mov     r15d, r14d
0x180097eae  mov     [rbp+57h+var_B0], r14d
0x180097eb2  mov     esi, r14d
0x180097eb5  mov     [rbp+57h+var_AC], r14d
0x180097eb9  mov     r12b, r14b
0x180097ebc  mov     byte ptr [rbp+57h+arg_0.lpVtbl], r14b
0x180097ec0  mov     byte ptr [rbp+57h+arg_8], r14b
0x180097ec4  add     r8, 120h; struct IXMLDOMElement *
0x180097ecb  mov     rdx, [rdi+8]
0x180097ecf  lea     r9, [rbp+57h+var_A8]; struct Common::StringBuffer *
0x180097ed3  mov     rdx, [rdx]; unsigned __int16 *
0x180097ed6  lea     rcx, aLocalNameHosti; "@*[local-name()='HostId']"
0x180097edd  call    ?GetAttributeValueStringFromQuery@Xml@Common@@YAJPEBGPEBUIXMLDOMElement@@AEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromQuery(ushort const *,IXMLDOMElement const *,Common::StringBuffer &,int *)
0x180097ee2  mov     ebx, eax
0x180097ee4  test    eax, eax
0x180097ee6  jns     short loc_180097F0A
0x180097ee8  mov     rcx, [rbp+5Fh]; this
0x180097eec  mov     r9d, eax; char *
0x180097eef  lea     r8, aOnecoreAdminAp_122; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180097ef6  mov     edx, 0B05h; void *
0x180097efb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180097f00  mov     edx, 5C4h
0x180097f05  jmp     loc_180098B93
0x180097f0a  cmp     [rbp+57h+var_A8], r14d
0x180097f0e  jz      short loc_180097F36
0x180097f10  mov     rdx, [rdi+10h]
0x180097f14  mov     rdx, [rdx]; struct OSIntegration::Package *
0x180097f17  mov     rcx, [rdi]; this
0x180097f1a  call    ?ResolveHostRuntimeAttributes@MoCOMHelper@Tools@OSIntegration@@AEAAJPEBVPackage@3@@Z; OSIntegration::Tools::MoCOMHelper::ResolveHostRuntimeAttributes(OSIntegration::Package const *)
0x180097f1f  mov     ebx, eax
0x180097f21  test    eax, eax
0x180097f23  jns     loc_180098349
0x180097f29  mov     r9d, eax
0x180097f2c  mov     edx, 5C8h
0x180097f31  jmp     loc_180098B96
0x180097f36  xorps   xmm0, xmm0
0x180097f39  movups  xmmword ptr [rsp+120h+var_F0.lpVtbl+8], xmm0
0x180097f3e  mov     [rsp+120h+var_D8], r14d
0x180097f43  mov     esi, 1
0x180097f48  mov     dl, sil
0x180097f4b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloActivationOverride@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloActivationOverride@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloActivationOverride> `wil::Feature<__WilFeatureTraits_Feature_AppSiloActivationOverride>::GetImpl(void)'::`2'::impl
0x180097f52  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloActivationOverride@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloActivationOverride>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180097f57  mov     rdx, [rdi+8]
0x180097f5b  lea     r9, [rbp+57h+arg_18]; struct Common::StringBuffer *
0x180097f5f  lea     r8, [rsp+120h+var_F0.lpVtbl+8]; struct IXMLDOMElement *
0x180097f64  mov     rdx, [rdx]; unsigned __int16 *
0x180097f67  lea     rcx, aUap18Trustleve; "@uap18:TrustLevel"
0x180097f6e  call    ?GetAttributeValueStringFromQuery@Xml@Common@@YAJPEBGPEBUIXMLDOMElement@@AEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromQuery(ushort const *,IXMLDOMElement const *,Common::StringBuffer &,int *)
0x180097f73  mov     ebx, eax
0x180097f75  test    eax, eax
0x180097f77  jns     short loc_180097FA1
0x180097f79  mov     edx, 5D5h; void *
0x180097f7e  lea     r8, aOnecoreAdminAp_122; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180097f85  mov     r9d, eax; char *
0x180097f88  mov     rcx, [rbp+5Fh]; this
0x180097f8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180097f91  nop
0x180097f92  lea     rcx, [rsp+120h+var_F0.lpVtbl+8]; this
0x180097f97  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180097f9c  jmp     loc_180098BA7
0x180097fa1  mov     r13d, [rbp+57h+arg_18]
0x180097fa5  test    r13d, r13d
0x180097fa8  jnz     short loc_180097FE2
0x180097faa  mov     rdx, [rdi+8]
0x180097fae  lea     r9, [rbp+57h+arg_18]; struct Common::StringBuffer *
0x180097fb2  lea     r8, [rsp+120h+var_F0.lpVtbl+8]; struct IXMLDOMElement *
0x180097fb7  mov     rdx, [rdx]; unsigned __int16 *
0x180097fba  lea     rcx, aLocalNameTrust; "@*[local-name()='TrustLevel']"
0x180097fc1  call    ?GetAttributeValueStringFromQuery@Xml@Common@@YAJPEBGPEBUIXMLDOMElement@@AEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromQuery(ushort const *,IXMLDOMElement const *,Common::StringBuffer &,int *)
0x180097fc6  mov     ebx, eax
0x180097fc8  test    eax, eax
0x180097fca  jns     short loc_180097FD3
0x180097fcc  mov     edx, 5DEh
0x180097fd1  jmp     short loc_180097F7E
0x180097fd3  mov     r13d, [rbp+57h+arg_18]
0x180097fd7  test    r13d, r13d
0x180097fda  jnz     short loc_180097FE2
0x180097fdc  or      r12d, 0FFFFFFFFh
0x180097fe0  jmp     short loc_180098042
0x180097fe2  mov     [rsp+20h], esi; bIgnoreCase
0x180097fe6  or      r12d, 0FFFFFFFFh
0x180097fea  mov     r9d, r12d; cchCount2
0x180097fed  lea     r8, ?TrustLevelAppContainer@Value@Packaging@Appx@@3QBGB; "appContainer"
0x180097ff4  mov     edx, r12d; cchCount1
0x180097ff7  mov     rbx, [rsp+120h+lpString1]
0x180097ffc  mov     rcx, rbx; lpString1
0x180097fff  call    cs:__imp_CompareStringOrdinal
0x180098005  add     eax, 0FFFFFFFEh
0x180098008  jnz     short loc_180098016
0x18009800a  mov     rax, [rdi]
0x18009800d  mov     [rax+264h], r14d
0x180098014  jmp     short loc_180098042
0x180098016  mov     [rsp+20h], esi; int
0x18009801a  mov     r9d, r12d; cchCount2
0x18009801d  lea     r8, ?TrustLevelMediumIL@Value@Packaging@Appx@@3QBGB; "mediumIL"
0x180098024  mov     edx, r12d; cchCount1
0x180098027  mov     rcx, rbx; lpString1
0x18009802a  call    cs:__imp_CompareStringOrdinal
0x180098030  add     eax, 0FFFFFFFEh
0x180098033  jnz     loc_1800984E2
0x180098039  mov     rax, [rdi]
0x18009803c  mov     [rax+264h], esi
  ... truncated ...
```
