# OSIntegration::DEH::Internal::AppExecutionAliasHelper::Parse(void)

- ea: `0x180007450`
- end: `0x180007ea7`
- name: `?Parse@AppExecutionAliasHelper@Internal@DEH@OSIntegration@@UEAAJXZ`
- size: `2647`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::AppExecutionAliasHelper *__hidden this)`
- caller_count: `0`
- callee_count: `26`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005e10`
- `0x180006e28`
- `0x180007450`
- `0x180009480`
- `0x180009578`
- `0x18000b3bc`
- `0x18000b7d0`
- `0x18000bd80`
- `0x18000e6e0`
- `0x1800138e0`
- `0x18002ece0`
- `0x1800415c0`
- `0x180041948`
- `0x1800434a0`
- `0x18008f690`
- `0x180098bf4`
- `0x1800a2854`
- `0x1800b6ca4`
- `0x1800bea8c`
- `0x1800c8e28`
- `0x1800cc4f4`
- `0x1800f0700`
- `0x18015d56c`
- `0x18015d72c`
- `0x18015dfe0`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007646`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007646`
- `OLEAUT32!__imp_VariantInit` at `0x180007742`
- `OLEAUT32!__imp_VariantInit` at `0x180007742`
- `OLEAUT32!__imp_VariantClear` at `0x1800077e7`
- `OLEAUT32!__imp_VariantClear` at `0x180007820`
- `OLEAUT32!__imp_VariantClear` at `0x1800077e7`
- `OLEAUT32!__imp_VariantClear` at `0x180007820`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800079f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007a45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007a57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007aa9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007ab7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007aeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007afb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800079f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007a45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007a57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007aa9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007ab7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007aeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007afb`
- `profapi!__imp_ExpandEnvStringForUser` at `0x180007c5a`
- `profapi!__imp_ExpandEnvStringForUser` at `0x180007c5a`

## string_xrefs

- `0x18000767f`: `ancestor::*[local-name()='Extension']`
- `0x180007c76`: `/*[local-name()='Package']/*[local-name()='Applications']/*[local-name()='Application']/*[local-name()='Extensions']/*[local-name()='Extension']/*[local-name()='AppExecutionAlias']/*[local-name()='ExecutionAlias' and @Alias='`
- `0x1800078be`: `Windows.CommandLineLaunch`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OSIntegration::DEH::Internal::AppExecutionAliasHelper::Parse(
        OSIntegration::DEH::Internal::AppExecutionAliasHelper *this)
{
  int AttributeValueStringFromElement; // eax
  unsigned int v4; // ebx
  __int64 v5; // r9
  __int64 v6; // rdx
  struct IXMLDOMElement **v7; // r9
  int XMLElementFromQuery; // eax
  __int64 v9; // rdx
  char lpVtbl; // r13
  int AttributeValueStringFromQuery; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  char v14; // si
  __int64 v15; // r12
  void *v16; // r15
  struct IXMLDOMElement **v17; // r9
  int v18; // eax
  unsigned __int64 v19; // rdx
  struct IXMLDOMElementVtbl *v20; // rcx
  struct IXMLDOMElementVtbl *v21; // rcx
  __int64 v22; // rcx
  LONGLONG *bstr; // rax
  LONGLONG v24; // rcx
  struct IXMLDOMElementVtbl *v25; // rdi
  __int64 (__fastcall *v26)(struct IXMLDOMElementVtbl *, _QWORD, __int128 *); // rbx
  __int128 v27; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  _QWORD *v29; // rax
  unsigned __int64 v30; // r9
  __int64 v31; // rdx
  int v32; // eax
  int v33; // eax
  OSIntegration::Tools::MoCOMHelper *v34; // rbx
  int appended; // edi
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rcx
  int v39; // eax
  OSIntegration::Tools::MoCOMHelper *v40; // rdi
  int v41; // eax
  int v42; // esi
  int v43; // eax
  OSIntegration::Tools::MoCOMHelper *v44; // rdi
  unsigned __int16 *v45; // rsi
  int v46; // eax
  unsigned int v47; // r12d
  __int64 v48; // rax
  __int64 v49; // rdx
  unsigned __int64 v50; // rdx
  struct IXMLDOMElementVtbl *v51; // rcx
  struct IXMLDOMElementVtbl *v52; // rcx
  int v53; // eax
  _BYTE *v54; // rsi
  struct Common::StringBuffer *v55; // r9
  unsigned __int64 v56; // rdx
  struct IXMLDOMElementVtbl *v57; // rcx
  struct IXMLDOMElementVtbl *v58; // rcx
  int *bIgnoreCase; // [rsp+28h] [rbp-A9h]
  int *bIgnoreCasea; // [rsp+28h] [rbp-A9h]
  int *bIgnoreCaseb; // [rsp+28h] [rbp-A9h]
  OSIntegration::Tools::MoCOMHelper **bIgnoreCasec; // [rsp+28h] [rbp-A9h]
  struct IXMLDOMElement v63; // [rsp+38h] [rbp-99h] BYREF
  OSIntegration::Tools::MoCOMHelper *pv; // [rsp+40h] [rbp-91h] BYREF
  LPVOID pv_8[2]; // [rsp+48h] [rbp-89h] BYREF
  int v66; // [rsp+58h] [rbp-79h]
  unsigned __int16 *v67; // [rsp+60h] [rbp-71h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-69h] BYREF
  _QWORD v69[3]; // [rsp+80h] [rbp-51h] BYREF
  __int128 v70; // [rsp+98h] [rbp-39h] BYREF
  IRecordInfo *v71; // [rsp+A8h] [rbp-29h]
  _QWORD v72[8]; // [rsp+B8h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+5Fh]
  struct IXMLDOMElement v74; // [rsp+140h] [rbp+6Fh] BYREF
  OSIntegration::Tools::MoCOMHelper *v75; // [rsp+148h] [rbp+77h] BYREF
  struct IXMLDOMElement v76; // [rsp+150h] [rbp+7Fh] BYREF

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA>::GetImpl'::`2'::impl)
    && OSIntegration::Package::IsPackageRootExternalLocation(*((OSIntegration::Package **)this + 3))
    && *(_BYTE *)(*((_QWORD *)this + 3) + 208LL) )
  {
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x47,
             (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
             (const char *)0x32,
             (unsigned int)bIgnoreCase);
  }
  v69[0] = 2;
  v69[1] = L"']";
  v72[1] = (char *)this + 168;
  v72[0] = &Common::StringBufferBuilder::`vftable';
  v72[2] = (char *)this + 168;
  v63.lpVtbl = 0;
  LODWORD(v75) = 0;
  AttributeValueStringFromElement = Common::Xml::GetAttributeValueStringFromElement(
                                      *((Common::Xml **)this + 2),
                                      (struct IXMLDOMElement *)&stru_1802310C0,
                                      (const unsigned __int16 *)this + 68,
                                      (struct Common::StringBuffer *)&v75,
                                      bIgnoreCase);
  v4 = AttributeValueStringFromElement;
  if ( AttributeValueStringFromElement < 0 )
  {
    v5 = (unsigned int)AttributeValueStringFromElement;
    v6 = 90;
LABEL_133:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
      (const char *)v5,
      (int)bIgnoreCasea);
    goto LABEL_134;
  }
  if ( !(_DWORD)v75 || !*((_QWORD *)this + 18) )
  {
    v4 = -2147024883;
    v5 = 2147942413LL;
    v6 = 94;
    goto LABEL_133;
  }
  v76.lpVtbl = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
  XMLElementFromQuery = Common::Xml::GetXMLElementFromQuery(
                          (OLECHAR *)L"ancestor::*[local-name()='Application']",
                          *((const unsigned __int16 **)this + 2),
                          &v76,
                          v7);
  v4 = XMLElementFromQuery;
  if ( XMLElementFromQuery < 0 )
  {
    v9 = 101;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
      (const char *)(unsigned int)XMLElementFromQuery,
      (int)bIgnoreCasea);
LABEL_12:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
LABEL_134:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
    return v4;
  }
  LOBYTE(v74.lpVtbl) = 0;
  XMLElementFromQuery = Common::Xml::GetAttributeValueBooleanFromQuery(
                          (OLECHAR *)L"@*[local-name()='SupportsMultipleInstances']",
                          (const unsigned __int16 *)v76.lpVtbl,
                          &v74,
                          (bool *)&v75,
                          bIgnoreCasea);
  v4 = XMLElementFromQuery;
  if ( XMLElementFromQuery < 0 )
  {
    v9 = 108;
    goto LABEL_11;
  }
  lpVtbl = 0;
  if ( (_DWORD)v75 )
    lpVtbl = (char)v74.lpVtbl;
  LODWORD(v75) = 0;
  *(_OWORD *)pv_8 = 0;
  v66 = 0;
  AttributeValueStringFromQuery = Common::Xml::GetAttributeValueStringFromQuery(
                                    (OLECHAR *)L"@*[local-name()='Subsystem']",
                                    (const unsigned __int16 *)v76.lpVtbl,
                                    (const struct IXMLDOMElement *)pv_8,
                                    (struct Common::StringBuffer *)&v75,
                                    bIgnoreCasea);
  v4 = AttributeValueStringFromQuery;
  if ( AttributeValueStringFromQuery < 0 )
  {
    v12 = 121;
LABEL_19:
    v13 = (unsigned int)AttributeValueStringFromQuery;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
      (const char *)v13,
      (int)bIgnoreCaseb);
LABEL_21:
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)pv_8);
    goto LABEL_12;
  }
  v14 = 0;
  LOBYTE(v74.lpVtbl) = 0;
  v15 = -1;
  v16 = pv_8[1];
  if ( (_DWORD)v75 )
  {
    if ( CompareStringOrdinal((LPCWCH)pv_8[1], -1, L"console", -1, 1) == 2 )
    {
      v14 = 1;
      LOBYTE(v74.lpVtbl) = 1;
      if ( !lpVtbl )
      {
        v4 = -2147024883;
        v13 = 2147942413LL;
        v12 = 130;
        goto LABEL_20;
      }
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
  v18 = Common::Xml::GetXMLElementFromQuery(
          (OLECHAR *)L"ancestor::*[local-name()='Extension']",
          *((const unsigned __int16 **)this + 2),
          &v63,
          v17);
  v4 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8A,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
      (const char *)(unsigned int)v18,
      (int)bIgnoreCaseb);
    if ( v16 )
      operator delete(v16, v19);
    v20 = v76.lpVtbl;
    if ( v76.lpVtbl )
    {
      v76.lpVtbl = 0;
      (*((void (__fastcall **)(struct IXMLDOMElementVtbl *))v20->QueryInterface + 2))(v20);
    }
    v21 = v63.lpVtbl;
    if ( v63.lpVtbl )
    {
      v63.lpVtbl = 0;
      (*((void (__fastcall **)(struct IXMLDOMElementVtbl *))v21->QueryInterface + 2))(v21);
    }
    return v4;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA>::GetImpl'::`2'::impl) )
  {
    LODWORD(v75) = 0;
    AttributeValueStringFromQuery = Common::Xml::GetAttributeValueStringFromQuery(
                                      (OLECHAR *)L"@*[local-name()='HostId']",
                                      (const unsigned __int16 *)v76.lpVtbl,
                                      (const struct IXMLDOMElement *)this + 48,
                                      (struct Common::StringBuffer *)&v75,
                                      bIgnoreCaseb);
    v4 = AttributeValueStringFromQuery;
    if ( AttributeValueStringFromQuery < 0 )
    {
      v12 = 145;
      goto LABEL_19;
    }
    if ( (_DWORD)v75 )
    {
      VariantInit(&pvarg);
      pvarg.vt = 8;
      bstr = (LONGLONG *)wil::make_bstr(&v75, *((_QWORD *)this + 49));
      v24 = *bstr;
      *bstr = 0;
      pvarg.llVal = v24;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v75);
      v25 = v63.lpVtbl;
      v26 = (__int64 (__fastcall *)(struct IXMLDOMElementVtbl *, _QWORD, __int128 *))*((_QWORD *)v63.lpVtbl->QueryInterface
                                                                                     + 45);
      v27 = *(_OWORD *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      v29 = (_QWORD *)wil::make_bstr(&v75, *((_QWORD *)this + 55));
      v70 = v27;
      v71 = pRecInfo;
      v4 = v26(v25, *v29, &v70);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v75);
      if ( (v4 & 0x80000000) != 0 )
      {
        v30 = v4;
        v31 = 153;
LABEL_40:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v31,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
          (const char *)v30,
          (int)bIgnoreCaseb);
        VariantClear(&pvarg);
        goto LABEL_21;
      }
      v32 = Common::Xml::GetAttributeValueStringFromQuery(
              (OLECHAR *)L"@*[local-name()='Parameters']",
              (const unsigned __int16 *)v76.lpVtbl,
              (const struct IXMLDOMElement *)this + 51,
              0,
              bIgnoreCaseb);
      v4 = v32;
      if ( v32 < 0 )
      {
        v30 = (unsigned int)v32;
        v31 = 156;
        goto LABEL_40;
      }
      VariantClear(&pvarg);
    }
  }
  v75 = 0;
  LODWORD(bIgnoreCasec) = 2;
  v33 = OSIntegration::Tools::MoCOMHelper::CreateHelper(v22, v63.lpVtbl, *((_QWORD *)this + 3), &v75);
  v4 = v33;
  if ( v33 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA7,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
      (const char *)(unsigned int)v33,
      2);
    Common::AutoPtrDeallocate<OSIntegration::Tools::MoCOMActionEntityHelper>(v75);
    goto LABEL_21;
  }
  v34 = v75;
  appended = OSIntegration::Tools::MoCOMHelper::Evaluate(v75, *((const struct OSIntegration::Package **)this + 3));
  v36 = 0;
  if ( appended < 0 )
  {
    v37 = 170;
LABEL_123:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v37,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
      (const char *)(unsigned int)appended,
      (int)bIgnoreCasec);
    goto LABEL_124;
  }
  v38 = *((unsigned int *)v34 + 152);
  *((_BYTE *)this + 436) = (_DWORD)v38 == 0;
  if ( (_DWORD)v38 )
  {
    appended = Common::StringBuffer::SetValue(
                 (OSIntegration::DEH::Internal::AppExecutionAliasHelper *)((char *)this + 240),
                 *((const unsigned __int16 **)v34 + 19),
                 *((_DWORD *)v34 + 36));
    if ( appended < 0 )
    {
      v37 = 210;
      goto LABEL_123;
    }
  }
  else
  {
    if ( !v14 )
    {
      *(_QWORD *)&v70 = 25;
      *((_QWORD *)&v70 + 1) = L"Windows.CommandLineLaunch";
      pv = 0;
      bIgnoreCasec = &pv;
      v39 = OSIntegration::Tools::MoCOMHelper::CreateHelper(v38, v63.lpVtbl, &v70, *((_QWORD *)this + 3));
      appended = v39;
      if ( v39 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBD,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
          (const char *)(unsigned int)v39,
          (int)&pv);
        Common::AutoPtrDeallocate<OSIntegration::Tools::MoCOMActionEntityHelper>(pv);
LABEL_124:
        Common::AutoPtrDeallocate<OSIntegration::Tools::MoCOMActionEntityHelper>(v34);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)pv_8);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
        v4 = appended;
        goto LABEL_134;
      }
      v40 = pv;
      v41 = OSIntegration::Tools::MoCOMHelper::Evaluate(pv, *((const struct OSIntegration::Package **)this + 3));
      v42 = v41;
      if ( v41 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBE,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
          (const char *)(unsigned int)v41,
          (int)&pv);
        Common::AutoPtrDeallocate<OSIntegration::Tools::MoCOMActionEntityHelper>(v40);
LABEL_54:
        Common::AutoPtrDeallocate<OSIntegration::Tools::MoCOMActionEntityHelper>(v34);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)pv_8);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
        v4 = v42;
        goto LABEL_134;
      }
      Common::AutoPtrDeallocate<OSIntegration::Tools::MoCOMActionEntityHelper>(v40);
    }
    if ( lpVtbl )
    {
      appended = Common::StringBuffer::SetValue(
                   (OSIntegration::DEH::Internal::AppExecutionAliasHelper *)((char *)this + 240),
                   *((const unsigned __int16 **)v34 + 19),
                   *((_DWORD *)v34 + 36));
      if ( appended < 0 )
      {
        v37 = 196;
        goto LABEL_123;
      }
    }
    else
    {
      pv = 0;
      v67 = 0;
      v43 = wil::GetSystemDirectoryW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
              &pv,
              v36);
      appended = v43;
      if ( v43 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCA,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
          (const char *)(unsigned int)v43,
          (int)bIgnoreCasec);
        if ( pv )
          CoTaskMemFree(pv);
        goto LABEL_124;
      }
      v44 = pv;
      v42 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short *,unsigned short [23]>(
              &v67,
              &pv);
      if ( v42 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCB,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
          (const char *)(unsigned int)v42,
          (int)bIgnoreCasec);
        if ( v67 )
          CoTaskMemFree(v67);
        if ( v44 )
          CoTaskMemFree(v44);
        goto LABEL_54;
      }
      v45 = v67;
      do
        ++v15;
      while ( v67[v15] );
      v46 = Common::StringBuffer::SetValue(
              (OSIntegration::DEH::Internal::AppExecutionAliasHelper *)((char *)this + 240),
              v67,
              v15);
      v47 = v46;
      if ( v46 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCC,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
          (const char *)(unsigned int)v46,
          (int)bIgnoreCasec);
        if ( v45 )
          CoTaskMemFree(v45);
        if ( v44 )
          CoTaskMemFree(v44);
        Common::AutoPtrDeallocate<OSIntegration::Tools::MoCOMActionEntityHelper>(v34);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)pv_8);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
        v4 = v47;
        goto LABEL_134;
      }
      if ( v45 )
        CoTaskMemFree(v45);
      if ( v44 )
        CoTaskMemFree(v44);
    }
  }
  v48 = *((_QWORD *)this + 3);
  if ( (*(_BYTE *)(v48 + 396) & 0x20) != 0 )
  {
    if ( *(_QWORD *)(v48 + 328) != 1 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD8,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
        (const char *)0x8000FFFFLL,
        (int)bIgnoreCasec);
      Common::AutoPtrDeallocate<OSIntegration::Tools::MoCOMActionEntityHelper>(v34);
      if ( v16 )
        operator delete(v16, v50);
      v51 = v76.lpVtbl;
      if ( v76.lpVtbl )
      {
        v76.lpVtbl = 0;
        (*((void (__fastcall **)(struct IXMLDOMElementVtbl *))v51->QueryInterface + 2))(v51);
      }
      v52 = v63.lpVtbl;
      if ( v63.lpVtbl )
      {
        v63.lpVtbl = 0;
        (*((void (__fastcall **)(struct IXMLDOMElementVtbl *))v52->QueryInterface + 2))(v52);
      }
      return 2147549183LL;
    }
    v49 = **(_QWORD **)(v48 + 312);
  }
  else
  {
    v49 = v48 + 240;
  }
  appended = Common::StringBuffer::SetValue(
               (OSIntegration::DEH::Internal::AppExecutionAliasHelper *)((char *)this + 192),
               *(const unsigned __int16 **)(v49 + 8),
               *(_DWORD *)v49);
  if ( appended < 0 )
  {
    v37 = 217;
    goto LABEL_123;
  }
  appended = Common::StringBuffer::SetValue(
               (OSIntegration::DEH::Internal::AppExecutionAliasHelper *)((char *)this + 216),
               *((const unsigned __int16 **)v34 + 34),
               *((_DWORD *)v34 + 66));
  if ( appended < 0 )
  {
    v37 = 219;
    goto LABEL_123;
  }
  appended = Common::StringBuffer::SetCapacity(
               (OSIntegration::DEH::Internal::AppExecutionAliasHelper *)((char *)this + 264),
               0x105u);
  if ( appended < 0 )
  {
    v37 = 222;
    goto LABEL_123;
  }
  appended = ExpandEnvStringForUser(
               *(_QWORD *)(*((_QWORD *)this + 3) + 56LL),
               L"%localappdata%\\Microsoft\\WindowsApps",
               *((_QWORD *)this + 34),
               260);
  if ( appended < 0 )
  {
    v37 = 223;
    goto LABEL_123;
  }
  appended = Common::StringBuffer::SetValue(
               (OSIntegration::DEH::Internal::AppExecutionAliasHelper *)((char *)this + 168),
               L"/*[local-name()='Package']/*[local-name()='Applications']/*[local-name()='Application']/*[local-name()='E"
                "xtensions']/*[local-name()='Extension']/*[local-name()='AppExecutionAlias']/*[local-name()='ExecutionAli"
                "as' and @Alias='",
               0xE1u);
  if ( appended < 0 )
  {
    v37 = 226;
    goto LABEL_123;
  }
  appended = Common::StringBuilder::AppendString(
               (Common::StringBuilder *)v72,
               (OSIntegration::DEH::Internal::AppExecutionAliasHelper *)((char *)this + 136));
  if ( appended < 0 )
  {
    v37 = 227;
    goto LABEL_123;
  }
  appended = Common::StringBuilder::AppendString(
               (Common::StringBuilder *)v72,
               (const struct Common::COMMON_STRING *)v69);
  if ( appended < 0 )
  {
    v37 = 228;
    goto LABEL_123;
  }
  if ( *((_BYTE *)this + 436) )
  {
    if ( LOBYTE(v74.lpVtbl) )
      v53 = 3;
    else
      v53 = (lpVtbl != 0) + 1;
  }
  else
  {
    v53 = 0;
  }
  *((_DWORD *)this + 108) = v53;
  v54 = (char *)this + 437;
  appended = OSIntegration::DEH::Internal::AppExecutionAliasHelper::GetAppExecAliasDirectory(
               this,
               (OSIntegration::DEH::Internal::AppExecutionAliasHelper *)((char *)this + 312),
               (bool *)this + 437);
  if ( appended < 0 )
  {
    v37 = 239;
    goto LABEL_123;
  }
  if ( *v54 )
  {
    appended = OSIntegration::Tools::ConcatenatePaths(
                 (OSIntegration::DEH::Internal::AppExecutionAliasHelper *)((char *)this + 312),
                 (OSIntegration::DEH::Internal::AppExecutionAliasHelper *)((char *)this + 192),
                 (OSIntegration::DEH::Internal::AppExecutionAliasHelper *)((char *)this + 336),
                 v55);
    if ( appended < 0 )
    {
      v37 = 242;
      goto LABEL_123;
    }
  }
  if ( (*(_BYTE *)(*((_QWORD *)this + 3) + 384LL) & 1) != 0 && *v54 )
  {
    appended = OSIntegration::Tools::ConcatenatePaths(
                 (OSIntegration::DEH::Internal::AppExecutionAliasHelper *)((char *)this + 336),
                 (OSIntegration::DEH::Internal::AppExecutionAliasHelper *)((char *)this + 136),
                 (OSIntegration::DEH::Internal::AppExecutionAliasHelper *)((char *)this + 360),
                 v55);
    if ( appended < 0 )
    {
      v37 = 247;
      goto LABEL_123;
    }
  }
  else
  {
    Common::StringBuffer::SetValue(
      (OSIntegration::DEH::Internal::AppExecutionAliasHelper *)((char *)this + 360),
      *((const unsigned __int16 **)this + 31),
      *((_DWORD *)this + 60));
  }
  appended = Common::StringBuffer::SetValue(
               (OSIntegration::DEH::Internal::AppExecutionAliasHelper *)((char *)this + 288),
               *((const unsigned __int16 **)v34 + 19),
               *((_DWORD *)v34 + 36));
  if ( appended < 0 )
  {
    v37 = 254;
    goto LABEL_123;
  }
  Common::AutoPtrDeallocate<OSIntegration::Tools::MoCOMActionEntityHelper>(v34);
  if ( v16 )
    operator delete(v16, v56);
  v57 = v76.lpVtbl;
  if ( v76.lpVtbl )
  {
    v76.lpVtbl = 0;
    (*((void (__fastcall **)(struct IXMLDOMElementVtbl *))v57->QueryInterface + 2))(v57);
  }
  v58 = v63.lpVtbl;
  if ( v63.lpVtbl )
  {
    v63.lpVtbl = 0;
    (*((void (__fastcall **)(struct IXMLDOMElementVtbl *))v58->QueryInterface + 2))(v58);
  }
  return 0;
}

```

## disassembly

```asm
0x180007450  mov     rax, rsp
0x180007453  mov     [rax+8], rbx
0x180007457  push    rbp
0x180007458  push    rsi
0x180007459  push    rdi
0x18000745a  push    r12
0x18000745c  push    r13
0x18000745e  push    r14
0x180007460  push    r15
0x180007462  lea     rbp, [rax-5Fh]
0x180007466  sub     rsp, 0F0h
0x18000746d  movaps  xmmword ptr [rax-48h], xmm6
0x180007471  movaps  xmmword ptr [rax-58h], xmm7
0x180007475  mov     r14, rcx
0x180007478  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA> `wil::Feature<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA>::GetImpl(void)'::`2'::impl
0x18000747f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA>::__private_IsEnabled(void)
0x180007484  xor     edi, edi
0x180007486  test    al, al
0x180007488  jnz     short loc_1800074C0
0x18000748a  mov     rcx, [r14+18h]; this
0x18000748e  call    ?IsPackageRootExternalLocation@Package@OSIntegration@@QEBA_NXZ; OSIntegration::Package::IsPackageRootExternalLocation(void)
0x180007493  test    al, al
0x180007495  jz      short loc_1800074C0
0x180007497  mov     rax, [r14+18h]
0x18000749b  cmp     [rax+0D0h], dil
0x1800074a2  jz      short loc_1800074C0
0x1800074a4  mov     rcx, [rbp+5Fh]; this
0x1800074a8  lea     r9d, [rdi+32h]; char *
0x1800074ac  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800074b3  lea     edx, [rdi+47h]; void *
0x1800074b6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800074bb  jmp     loc_180007E82
0x1800074c0  xor     eax, eax
0x1800074c2  mov     dword ptr [rbp+57h+var_A8+4], eax
0x1800074c5  mov     [rbp+57h+var_A8], 2
0x1800074cd  lea     rax, asc_1802310CC; "']"
0x1800074d4  mov     [rbp+57h+var_A0], rax
0x1800074d8  lea     rax, [r14+0A8h]
0x1800074df  mov     [rbp+57h+var_68], rax
0x1800074e3  lea     rcx, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x1800074ea  mov     [rbp+57h+var_70], rcx
0x1800074ee  mov     [rbp+57h+var_60], rax
0x1800074f2  mov     [rsp+120h+var_F0.lpVtbl], rdi
0x1800074f7  mov     dword ptr [rbp+57h+arg_10], edi
0x1800074fa  lea     r8, [r14+88h]; unsigned __int16 *
0x180007501  lea     r9, [rbp+57h+arg_10]; struct Common::StringBuffer *
0x180007505  lea     rdx, stru_1802310C0; struct IXMLDOMElement *
0x18000750c  mov     rcx, [r14+10h]; this
0x180007510  call    ?GetAttributeValueStringFromElement@Xml@Common@@YAJPEAUIXMLDOMElement@@PEBGAEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromElement(IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)
0x180007515  mov     ebx, eax
0x180007517  test    eax, eax
0x180007519  jns     short loc_180007528
0x18000751b  mov     r9d, eax
0x18000751e  mov     edx, 5Ah ; 'Z'
0x180007523  jmp     loc_180007E65
0x180007528  cmp     dword ptr [rbp+57h+arg_10], edi
0x18000752b  jz      loc_180007E58
0x180007531  cmp     [r14+90h], rdi
0x180007538  jz      loc_180007E58
0x18000753e  mov     [rbp+57h+arg_18.lpVtbl], rdi
0x180007542  lea     rcx, [rbp+57h+arg_18]
0x180007546  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000754b  lea     r8, [rbp+57h+arg_18]; struct IXMLDOMElement *
0x18000754f  mov     rdx, [r14+10h]; unsigned __int16 *
0x180007553  lea     rcx, aAncestorLocalN; "ancestor::*[local-name()='Application']"
0x18000755a  call    ?GetXMLElementFromQuery@Xml@Common@@YAJPEBGPEAUIXMLDOMElement@@PEAPEAU3@@Z; Common::Xml::GetXMLElementFromQuery(ushort const *,IXMLDOMElement *,IXMLDOMElement * *)
0x18000755f  mov     ebx, eax
0x180007561  test    eax, eax
0x180007563  jns     short loc_18000758C
0x180007565  mov     edx, 65h ; 'e'; void *
0x18000756a  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180007571  mov     r9d, eax; char *
0x180007574  mov     rcx, [rbp+5Fh]; this
0x180007578  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000757d  nop
0x18000757e  lea     rcx, [rbp+57h+arg_18]
0x180007582  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180007587  jmp     loc_180007E76
0x18000758c  mov     byte ptr [rbp+57h+arg_8.lpVtbl], dil
0x180007590  lea     r9, [rbp+57h+arg_10]; bool *
0x180007594  lea     r8, [rbp+57h+arg_8]; struct IXMLDOMElement *
0x180007598  mov     rdx, [rbp+57h+arg_18.lpVtbl]; unsigned __int16 *
0x18000759c  lea     rcx, aLocalNameSuppo_1; "@*[local-name()='SupportsMultipleInstan"...
0x1800075a3  call    ?GetAttributeValueBooleanFromQuery@Xml@Common@@YAJPEBGPEAUIXMLDOMElement@@AEA_NPEAH@Z; Common::Xml::GetAttributeValueBooleanFromQuery(ushort const *,IXMLDOMElement *,bool &,int *)
0x1800075a8  mov     ebx, eax
0x1800075aa  test    eax, eax
0x1800075ac  jns     short loc_1800075B5
0x1800075ae  mov     edx, 6Ch ; 'l'
0x1800075b3  jmp     short loc_18000756A
0x1800075b5  movzx   r13d, dil
0x1800075b9  movzx   eax, byte ptr [rbp+57h+arg_8.lpVtbl]
0x1800075bd  cmp     dword ptr [rbp+57h+arg_10], edi
0x1800075c0  cmovnz  r13d, eax
0x1800075c4  mov     dword ptr [rbp+57h+arg_10], edi
0x1800075c7  xorps   xmm0, xmm0
0x1800075ca  movups  xmmword ptr [rsp+120h+pv+8], xmm0
0x1800075cf  mov     [rbp+57h+var_D0], edi
0x1800075d2  lea     r9, [rbp+57h+arg_10]; struct Common::StringBuffer *
0x1800075d6  lea     r8, [rsp+120h+pv+8]; struct IXMLDOMElement *
0x1800075db  mov     rdx, [rbp+57h+arg_18.lpVtbl]; unsigned __int16 *
0x1800075df  lea     rcx, aLocalNameSubsy; "@*[local-name()='Subsystem']"
0x1800075e6  call    ?GetAttributeValueStringFromQuery@Xml@Common@@YAJPEBGPEBUIXMLDOMElement@@AEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromQuery(ushort const *,IXMLDOMElement const *,Common::StringBuffer &,int *)
0x1800075eb  mov     ebx, eax
0x1800075ed  test    eax, eax
0x1800075ef  jns     short loc_180007619
0x1800075f1  mov     edx, 79h ; 'y'; void *
0x1800075f6  mov     r9d, eax; char *
0x1800075f9  mov     rcx, [rbp+5Fh]; this
0x1800075fd  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180007604  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007609  nop
0x18000760a  lea     rcx, [rsp+120h+pv+8]; this
0x18000760f  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180007614  jmp     loc_18000757E
0x180007619  mov     sil, dil
0x18000761c  mov     byte ptr [rbp+57h+arg_8.lpVtbl], dil
0x180007620  or      r12, 0FFFFFFFFFFFFFFFFh
0x180007624  mov     r15, [rsp+120h+lpString1]
0x180007629  cmp     dword ptr [rbp+57h+arg_10], edi
0x18000762c  jz      short loc_18000766C
0x18000762e  mov     dword ptr [rsp+120h+bIgnoreCase], 1; bIgnoreCase
0x180007636  mov     r9d, r12d; cchCount2
0x180007639  lea     r8, ?SubsystemConsole@Value@Packaging@Appx@@3QBGB; "console"
0x180007640  mov     edx, r12d; cchCount1
0x180007643  mov     rcx, r15; lpString1
0x180007646  call    cs:__imp_CompareStringOrdinal
0x18000764c  cmp     eax, 2
0x18000764f  jnz     short loc_18000766C
0x180007651  mov     sil, 1
0x180007654  mov     byte ptr [rbp+57h+arg_8.lpVtbl], sil
0x180007658  test    r13b, r13b
0x18000765b  jnz     short loc_18000766C
0x18000765d  mov     ebx, 8007000Dh
0x180007662  mov     r9d, ebx
0x180007665  mov     edx, 82h
0x18000766a  jmp     short loc_1800075F9
0x18000766c  lea     rcx, [rsp+120h+var_F0]
0x180007671  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180007676  lea     r8, [rsp+120h+var_F0]; struct IXMLDOMElement *
0x18000767b  mov     rdx, [r14+10h]; unsigned __int16 *
0x18000767f  lea     rcx, aAncestorLocalN_1; "ancestor::*[local-name()='Extension']"
0x180007686  call    ?GetXMLElementFromQuery@Xml@Common@@YAJPEBGPEAUIXMLDOMElement@@PEAPEAU3@@Z; Common::Xml::GetXMLElementFromQuery(ushort const *,IXMLDOMElement *,IXMLDOMElement * *)
0x18000768b  mov     ebx, eax
0x18000768d  test    eax, eax
0x18000768f  jns     short loc_1800076F3
0x180007691  mov     rcx, [rbp+5Fh]; this
0x180007695  mov     r9d, eax; char *
0x180007698  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18000769f  mov     edx, 8Ah; void *
0x1800076a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800076a9  nop
0x1800076aa  test    r15, r15
0x1800076ad  jz      short loc_1800076B8
0x1800076af  mov     rcx, r15; void *
0x1800076b2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800076b7  nop
0x1800076b8  mov     rcx, [rbp+57h+arg_18.lpVtbl]
0x1800076bc  test    rcx, rcx
0x1800076bf  jz      short loc_1800076D2
0x1800076c1  mov     [rbp+57h+arg_18.lpVtbl], rdi
0x1800076c5  mov     rax, [rcx]
0x1800076c8  mov     rax, [rax+10h]
0x1800076cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076d1  nop
0x1800076d2  mov     rcx, [rsp+120h+var_F0.lpVtbl]
0x1800076d7  test    rcx, rcx
0x1800076da  jz      short loc_1800076EE
0x1800076dc  mov     [rsp+120h+var_F0.lpVtbl], rdi
0x1800076e1  mov     rax, [rcx]
0x1800076e4  mov     rax, [rax+10h]
0x1800076e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076ed  nop
0x1800076ee  jmp     loc_180007E80
0x1800076f3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA> `wil::Feature<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA>::GetImpl(void)'::`2'::impl
0x1800076fa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableRunningHostedAppsWithAEA>::__private_IsEnabled(void)
0x1800076ff  test    al, al
0x180007701  jz      loc_180007826
0x180007707  mov     dword ptr [rbp+57h+arg_10], edi
0x18000770a  lea     r8, [r14+180h]; struct IXMLDOMElement *
0x180007711  lea     r9, [rbp+57h+arg_10]; struct Common::StringBuffer *
0x180007715  mov     rdx, [rbp+57h+arg_18.lpVtbl]; unsigned __int16 *
0x180007719  lea     rcx, aLocalNameHosti; "@*[local-name()='HostId']"
0x180007720  call    ?GetAttributeValueStringFromQuery@Xml@Common@@YAJPEBGPEBUIXMLDOMElement@@AEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromQuery(ushort const *,IXMLDOMElement const *,Common::StringBuffer &,int *)
0x180007725  mov     ebx, eax
0x180007727  test    eax, eax
0x180007729  jns     short loc_180007735
0x18000772b  mov     edx, 91h
0x180007730  jmp     loc_1800075F6
0x180007735  cmp     dword ptr [rbp+57h+arg_10], edi
0x180007738  jz      loc_180007826
0x18000773e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180007742  call    cs:__imp_VariantInit
0x180007748  nop
0x180007749  mov     eax, 8
0x18000774e  mov     word ptr [rbp+57h+pvarg], ax
0x180007752  mov     rdx, [r14+188h]
0x180007759  lea     rcx, [rbp+57h+arg_10]
0x18000775d  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180007762  mov     rcx, [rax]
0x180007765  mov     [rax], rdi
0x180007768  mov     qword ptr [rbp+57h+pvarg+8], rcx
0x18000776c  lea     rcx, [rbp+57h+arg_10]
0x180007770  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180007775  mov     rdi, [rsp+120h+var_F0.lpVtbl]
0x18000777a  mov     rax, [rdi]
0x18000777d  mov     rbx, [rax+168h]
0x180007784  movups  xmm6, xmmword ptr [rbp+57h+pvarg]
0x180007788  movsd   xmm7, qword ptr [rbp+57h+pvarg+10h]
0x18000778d  mov     rdx, [r14+1B8h]
0x180007794  lea     rcx, [rbp+57h+arg_10]
0x180007798  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18000779d  nop
0x18000779e  movaps  [rbp+57h+var_90], xmm6
0x1800077a2  movsd   [rbp+57h+var_80], xmm7
0x1800077a7  lea     r8, [rbp+57h+var_90]
0x1800077ab  mov     rdx, [rax]
0x1800077ae  mov     rcx, rdi
0x1800077b1  mov     rax, rbx
0x1800077b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077b9  mov     ebx, eax
0x1800077bb  lea     rcx, [rbp+57h+arg_10]
0x1800077bf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800077c4  xor     edi, edi
0x1800077c6  test    ebx, ebx
0x1800077c8  jns     short loc_1800077F2
0x1800077ca  mov     r9d, ebx; char *
0x1800077cd  mov     edx, 99h; void *
0x1800077d2  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800077d9  mov     rcx, [rbp+5Fh]; this
0x1800077dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800077e2  nop
0x1800077e3  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800077e7  call    cs:__imp_VariantClear
0x1800077ed  jmp     loc_18000760A
0x1800077f2  lea     r8, [r14+198h]; struct IXMLDOMElement *
0x1800077f9  xor     r9d, r9d; struct Common::StringBuffer *
0x1800077fc  mov     rdx, [rbp+57h+arg_18.lpVtbl]; unsigned __int16 *
0x180007800  lea     rcx, aLocalNameParam; "@*[local-name()='Parameters']"
0x180007807  call    ?GetAttributeValueStringFromQuery@Xml@Common@@YAJPEBGPEBUIXMLDOMElement@@AEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromQuery(ushort const *,IXMLDOMElement const *,Common::StringBuffer &,int *)
0x18000780c  mov     ebx, eax
0x18000780e  test    eax, eax
0x180007810  jns     short loc_18000781C
0x180007812  mov     r9d, eax
0x180007815  mov     edx, 9Ch
0x18000781a  jmp     short loc_1800077D2
0x18000781c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180007820  call    cs:__imp_VariantClear
0x180007826  mov     [rbp+57h+arg_10], rdi
0x18000782a  mov     dword ptr [rsp+120h+bIgnoreCase], 2; int
0x180007832  lea     r9, [rbp+57h+arg_10]
0x180007836  mov     r8, [r14+18h]
0x18000783a  mov     rdx, [rsp+120h+var_F0.lpVtbl]
0x18000783f  call    ?CreateHelper@MoCOMHelper@Tools@OSIntegration@@SAJPEAXPEAUIXMLDOMElement@@PEBVPackage@3@PEAPEAV123@W4ExtensionActivationRuntimeSupport@23@@Z; OSIntegration::Tools::MoCOMHelper::CreateHelper(void *,IXMLDOMElement *,OSIntegration::Package const *,OSIntegration::Tools::MoCOMHelper * *,OSIntegration::Tools::ExtensionActivationRuntimeSupport)
0x180007844  mov     ebx, eax
0x180007846  test    eax, eax
0x180007848  jns     short loc_180007871
0x18000784a  mov     rcx, [rbp+5Fh]; this
0x18000784e  mov     r9d, eax; char *
0x180007851  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180007858  mov     edx, 0A7h; void *
0x18000785d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007862  nop
0x180007863  mov     rcx, [rbp+57h+arg_10]
0x180007867  call    ??$AutoPtrDeallocate@VMoCOMActionEntityHelper@Tools@OSIntegration@@@Common@@YAXPEAVMoCOMActionEntityHelper@Tools@OSIntegration@@@Z; Common::AutoPtrDeallocate<OSIntegration::Tools::MoCOMActionEntityHelper>(OSIntegration::Tools::MoCOMActionEntityHelper *)
0x18000786c  jmp     loc_18000760A
0x180007871  mov     rdx, [r14+18h]; struct OSIntegration::Package *
0x180007875  mov     rbx, [rbp+57h+arg_10]
0x180007879  mov     rcx, rbx; this
0x18000787c  call    ?Evaluate@MoCOMHelper@Tools@OSIntegration@@QEBAJPEBVPackage@3@@Z; OSIntegration::Tools::MoCOMHelper::Evaluate(OSIntegration::Package const *)
0x180007881  mov     edi, eax
0x180007883  xor     edx, edx
0x180007885  test    eax, eax
0x180007887  jns     short loc_180007893
0x180007889  mov     edx, 0AAh
0x18000788e  jmp     loc_180007DD2
0x180007893  mov     ecx, [rbx+260h]
0x180007899  test    ecx, ecx
0x18000789b  setz    al
0x18000789e  mov     [r14+1B4h], al
0x1800078a5  test    ecx, ecx
0x1800078a7  jnz     loc_180007B2B
0x1800078ad  test    sil, sil
0x1800078b0  jnz     loc_180007985
0x1800078b6  mov     qword ptr [rbp+57h+var_90], 19h
0x1800078be  lea     rax, aWindowsCommand; "Windows.CommandLineLaunch"
0x1800078c5  mov     qword ptr [rbp+57h+var_90+8], rax
0x1800078c9  mov     [rsp+120h+pv], rdx
0x1800078ce  mov     dword ptr [rsp+120h+var_F8], 2
0x1800078d6  lea     rax, [rsp+120h+pv]
0x1800078db  mov     [rsp+120h+bIgnoreCase], rax; int
0x1800078e0  mov     r9, [r14+18h]
0x1800078e4  lea     r8, [rbp+57h+var_90]
0x1800078e8  mov     rdx, [rsp+120h+var_F0.lpVtbl]
0x1800078ed  call    ?CreateHelper@MoCOMHelper@Tools@OSIntegration@@SAJPEAXPEAUIXMLDOMElement@@PEBUCOMMON_STRING@Common@@PEBVPackage@3@PEAPEAV123@W4ExtensionActivationRuntimeSupport@23@@Z; OSIntegration::Tools::MoCOMHelper::CreateHelper(void *,IXMLDOMElement *,Common::COMMON_STRING const *,OSIntegration::Package const *,OSIntegration::Tools::MoCOMHelper * *,OSIntegration::Tools::ExtensionActivationRuntimeSupport)
0x1800078f2  mov     edi, eax
0x1800078f4  test    eax, eax
0x1800078f6  jns     short loc_180007920
0x1800078f8  mov     rcx, [rbp+5Fh]; this
0x1800078fc  mov     r9d, eax; char *
0x1800078ff  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\osim\\src\\de"...
  ... truncated ...
```
