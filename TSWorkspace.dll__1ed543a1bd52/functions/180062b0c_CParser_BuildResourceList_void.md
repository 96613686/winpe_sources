# CParser::BuildResourceList(void)

- ea: `0x180062b0c`
- end: `0x180063597`
- name: `?BuildResourceList@CParser@@IEAAJXZ`
- size: `2699`
- prototype: `__int64 __fastcall(CParser *__hidden this)`
- caller_count: `6`
- callee_count: `24`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800644bc`
- `0x1800654c4`
- `0x18006566c`
- `0x180065710`
- `0x1800658f4`
- `0x180065c20`

## callees

- `0x1800054c4`
- `0x180005500`
- `0x180005524`
- `0x180007598`
- `0x18000b1d8`
- `0x18000c3a0`
- `0x18000c3d0`
- `0x18000dbdc`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x18000fed8`
- `0x180020a68`
- `0x180020a9c`
- `0x180027914`
- `0x18004a694`
- `0x180060dd4`
- `0x180062b0c`
- `0x180063fc4`
- `0x180064d10`
- `0x1800651b0`
- `0x18006b928`
- `0x18006bef8`
- `0x1800a3010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180062c43`
- `OLEAUT32!__imp_SysAllocString` at `0x180062c43`
- `OLEAUT32!__imp_SysFreeString` at `0x180062f24`
- `OLEAUT32!__imp_SysFreeString` at `0x180063037`
- `OLEAUT32!__imp_SysFreeString` at `0x180063147`
- `OLEAUT32!__imp_SysFreeString` at `0x1800631cc`
- `OLEAUT32!__imp_SysFreeString` at `0x180063503`
- `OLEAUT32!__imp_SysFreeString` at `0x18006350f`
- `OLEAUT32!__imp_SysFreeString` at `0x18006351b`
- `OLEAUT32!__imp_SysFreeString` at `0x18006352a`
- `OLEAUT32!__imp_SysFreeString` at `0x180063539`
- `OLEAUT32!__imp_SysFreeString` at `0x180063545`
- `OLEAUT32!__imp_SysFreeString` at `0x180062f24`
- `OLEAUT32!__imp_SysFreeString` at `0x180063037`
- `OLEAUT32!__imp_SysFreeString` at `0x180063147`
- `OLEAUT32!__imp_SysFreeString` at `0x1800631cc`
- `OLEAUT32!__imp_SysFreeString` at `0x180063503`
- `OLEAUT32!__imp_SysFreeString` at `0x18006350f`
- `OLEAUT32!__imp_SysFreeString` at `0x18006351b`
- `OLEAUT32!__imp_SysFreeString` at `0x18006352a`
- `OLEAUT32!__imp_SysFreeString` at `0x180063539`
- `OLEAUT32!__imp_SysFreeString` at `0x180063545`
- `OLEAUT32!__imp_SysStringLen` at `0x180062f8c`
- `OLEAUT32!__imp_SysStringLen` at `0x18006309f`
- `OLEAUT32!__imp_SysStringLen` at `0x180062f8c`
- `OLEAUT32!__imp_SysStringLen` at `0x18006309f`
- `OLEAUT32!__imp_VariantClear` at `0x180062c27`
- `OLEAUT32!__imp_VariantClear` at `0x180062ce0`
- `OLEAUT32!__imp_VariantClear` at `0x180062d5a`
- `OLEAUT32!__imp_VariantClear` at `0x180062e12`
- `OLEAUT32!__imp_VariantClear` at `0x180062c27`
- `OLEAUT32!__imp_VariantClear` at `0x180062ce0`
- `OLEAUT32!__imp_VariantClear` at `0x180062d5a`
- `OLEAUT32!__imp_VariantClear` at `0x180062e12`

## string_xrefs

- `0x1800632a3`: `IXMLDOMNodeList::get_length failed`
- `0x180063364`: `IXMLDomNodeList::item failed`
- `0x180062b4d`: `xmlns:ns='http://schemas.microsoft.com/ts/2007/05/tswf'`
- `0x180062c3c`: `XPath`
- `0x180062d17`: `IXmlDOMDocument::setproperty failed`
- `0x180062e49`: `IXmlDOMDocument::setproperty failed`
- `0x1800633db`: `CResource::CreateInstance failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=22 #try_helpers=2
__int64 __fastcall CParser::BuildResourceList(CParser *this)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int NamedAttributeValue; // ebx
  __int64 *v4; // rbx
  __int64 v5; // rsi
  unsigned int v6; // eax
  __int64 *v7; // rbx
  __int64 v8; // rsi
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned __int16 **v11; // rax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned __int16 **v14; // rax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned __int16 **v17; // rax
  int NamedAttributeBoolValue; // ebx
  unsigned int v19; // eax
  unsigned __int16 **v20; // rax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  int v25; // r15d
  _QWORD *v26; // rax
  __int64 v27; // r8
  __int64 v28; // r9
  int v29; // ebx
  unsigned int v30; // eax
  __int64 v32; // [rsp+30h] [rbp-158h] BYREF
  struct CResource *v33; // [rsp+38h] [rbp-150h] BYREF
  struct IXMLDOMNode *v34; // [rsp+40h] [rbp-148h] BYREF
  struct IXMLDOMNode *v35; // [rsp+48h] [rbp-140h] BYREF
  BSTR v36; // [rsp+50h] [rbp-138h] BYREF
  BSTR pbstr; // [rsp+58h] [rbp-130h] BYREF
  __int64 v38; // [rsp+60h] [rbp-128h] BYREF
  int v39; // [rsp+68h] [rbp-120h]
  BSTR v40; // [rsp+70h] [rbp-118h] BYREF
  __int64 v41; // [rsp+78h] [rbp-110h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-108h] BYREF
  VARIANTARG v43; // [rsp+98h] [rbp-F0h] BYREF
  BSTR v44; // [rsp+B0h] [rbp-D8h] BYREF
  BSTR v45; // [rsp+B8h] [rbp-D0h] BYREF
  BSTR v46[2]; // [rsp+C0h] [rbp-C8h] BYREF
  VARIANTARG v47; // [rsp+D0h] [rbp-B8h] BYREF
  VARIANTARG v48[6]; // [rsp+F0h] [rbp-98h] BYREF
  BSTR bstrString; // [rsp+198h] [rbp+10h] BYREF
  char v50; // [rsp+1A0h] [rbp+18h] BYREF

  v46[1] = (BSTR)-2LL;
  v41 = 0;
  v34 = 0;
  v38 = 0;
  v35 = 0;
  v33 = 0;
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v40, L"xmlns:ns='http://schemas.microsoft.com/ts/2007/05/tswf'");
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)v46, L"//ns:Publisher");
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v45, L"ns:Resources/ns:Resource");
  pbstr = 0;
  v36 = 0;
  v44 = 0;
  HIDWORD(v32) = 0;
  LODWORD(v32) = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 6) + 360LL))(
                   *((_QWORD *)this + 6),
                   &v41);
  if ( (_DWORD)v32 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        133,
        &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
    NamedAttributeValue = -2147220988;
    LODWORD(v32) = -2147220988;
LABEL_85:
    std::vector<ComPlainSmartPtr<CTenantFeedInfo>>::clear((char *)this + 56);
    *((_BYTE *)this + 81) = 0;
    goto LABEL_86;
  }
  v4 = (__int64 *)*((_QWORD *)this + 6);
  v5 = *v4;
  pvarg.vt = 0;
  VariantClear(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(L"XPath");
  if ( !pvarg.llVal )
  {
    pvarg.vt = 10;
    pvarg.lVal = -2147024882;
    ATL::AtlThrowImpl(-2147024882);
  }
  *(VARIANTARG *)((char *)&v48[1] + 8) = pvarg;
  v47 = pvarg;
  NamedAttributeValue = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v5 + 640))(
                          v4,
                          L"SelectionLanguage",
                          &v47);
  LODWORD(v32) = NamedAttributeValue;
  VariantClear(&pvarg);
  if ( NamedAttributeValue < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        134,
        (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
        v6,
        (__int64)"IXmlDOMDocument::setproperty failed",
        NamedAttributeValue,
        v32);
    }
    goto LABEL_85;
  }
  v7 = (__int64 *)*((_QWORD *)this + 6);
  v8 = *v7;
  v43.vt = 0;
  VariantClear(&v43);
  v43.vt = 8;
  v43.llVal = (LONGLONG)ATL::CComBSTR::Copy((ATL::CComBSTR *)&v40);
  if ( !v43.llVal && v40 )
  {
    v43.vt = 10;
    v43.lVal = -2147024882;
    ATL::AtlThrowImpl(-2147024882);
  }
  *(VARIANTARG *)((char *)&v48[2] + 8) = v43;
  v48[0] = v43;
  NamedAttributeValue = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v8 + 640))(
                          v7,
                          L"SelectionNamespaces",
                          v48);
  LODWORD(v32) = NamedAttributeValue;
  VariantClear(&v43);
  if ( NamedAttributeValue < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        135,
        (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
        v9,
        (__int64)"IXmlDOMDocument::setproperty failed",
        NamedAttributeValue,
        v32);
    }
    goto LABEL_85;
  }
  LODWORD(v32) = (*(__int64 (__fastcall **)(__int64, BSTR, struct IXMLDOMNode **))(*(_QWORD *)v41 + 296LL))(
                   v41,
                   v46[0],
                   &v34);
  if ( (_DWORD)v32 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids, v10);
    }
    NamedAttributeValue = -2147220988;
    LODWORD(v32) = -2147220988;
    goto LABEL_85;
  }
  v11 = (unsigned __int16 **)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"Name");
  NamedAttributeValue = GetNamedAttributeValue(v34, *v11, &pbstr);
  LODWORD(v32) = NamedAttributeValue;
  SysFreeString(bstrString);
  if ( NamedAttributeValue < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        137,
        (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
        v12,
        (__int64)"GetNamedAttributeValue for Publisher Name failed",
        NamedAttributeValue,
        v32);
    }
    goto LABEL_85;
  }
  if ( SysStringLen(pbstr) >= 0x1401 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        138,
        &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
        v13,
        -2147220988);
    }
    NamedAttributeValue = -2147220988;
    LODWORD(v32) = -2147220988;
    goto LABEL_85;
  }
  std::wstring::assign((char *)this + 88, pbstr);
  v14 = (unsigned __int16 **)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"ID");
  NamedAttributeValue = GetNamedAttributeValue(v34, *v14, &v36);
  LODWORD(v32) = NamedAttributeValue;
  SysFreeString(bstrString);
  if ( NamedAttributeValue < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        139,
        (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
        v15,
        (__int64)"GetNamedAttributeValue for Workspace ID failed",
        NamedAttributeValue,
        v32);
    }
    goto LABEL_85;
  }
  if ( SysStringLen(v36) >= 0x1401 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        140,
        &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
        v16,
        -2147220988);
    }
    NamedAttributeValue = -2147220988;
    LODWORD(v32) = -2147220988;
    goto LABEL_85;
  }
  std::wstring::assign((char *)this + 120, v36);
  v17 = (unsigned __int16 **)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"SupportsReconnect");
  NamedAttributeBoolValue = GetNamedAttributeBoolValue(v34, *v17, (int *)this + 38);
  LODWORD(v32) = NamedAttributeBoolValue;
  SysFreeString(bstrString);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v19 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      141,
      &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
      v19,
      NamedAttributeBoolValue);
  }
  v20 = (unsigned __int16 **)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"DisplayFolder");
  LODWORD(v32) = GetNamedAttributeValue(v34, *v20, &v44);
  SysFreeString(bstrString);
  *((_DWORD *)this + 40) = (int)v32 >= 0;
  NamedAttributeValue = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR, __int64 *))v34->lpVtbl->selectNodes)(
                          v34,
                          v45,
                          &v38);
  LODWORD(v32) = NamedAttributeValue;
  if ( NamedAttributeValue < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v21 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        142,
        (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
        v21,
        (__int64)"selectnodes failed",
        NamedAttributeValue,
        v32);
    }
    goto LABEL_85;
  }
  NamedAttributeValue = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v38 + 64LL))(v38, (char *)&v32 + 4);
  LODWORD(v32) = NamedAttributeValue;
  if ( NamedAttributeValue < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v22 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        143,
        (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
        v22,
        (__int64)"IXMLDOMNodeList::get_length failed",
        NamedAttributeValue,
        v32);
    }
    goto LABEL_85;
  }
  v25 = 0;
  v39 = 0;
  while ( v25 < SHIDWORD(v32) )
  {
    if ( v35 )
    {
      TCntPtr<ITSThread>::SafeRelease(&v35);
      v35 = 0;
    }
    if ( v33 )
    {
      TCntPtr<CConfigManager>::SafeRelease(&v33);
      v33 = 0;
      TCntPtr<CConfigManager>::SafeAddRef(&v33);
    }
    NamedAttributeValue = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IXMLDOMNode **))(*(_QWORD *)v38 + 56LL))(
                            v38,
                            (unsigned int)v25,
                            &v35);
    LODWORD(v32) = NamedAttributeValue;
    if ( NamedAttributeValue < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v23 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          144,
          (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
          v23,
          (__int64)"IXMLDomNodeList::item failed",
          NamedAttributeValue,
          v32);
      }
      goto LABEL_85;
    }
    NamedAttributeValue = CResource::CreateInstance(v35, *((_DWORD *)this + 39), &v33);
    LODWORD(v32) = NamedAttributeValue;
    if ( NamedAttributeValue < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v24 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          145,
          (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
          v24,
          (__int64)"CResource::CreateInstance failed",
          NamedAttributeValue,
          v32);
      }
      goto LABEL_85;
    }
    std::vector<ComPlainSmartPtr<CResource>>::push_back((char *)this + 56, &v33);
    v39 = ++v25;
  }
  std::vector<std::wstring>::end((char *)this + 56, &bstrString);
  v26 = (_QWORD *)std::vector<unsigned int>::begin((char *)this + 56, &v50);
  LOBYTE(v27) = (_BYTE)bstrString;
  std::sort<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ComPlainSmartPtr<CResource>>>>,ResourceLessById>(
    *v26,
    v28,
    v27);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v29 = HIDWORD(v32);
    v30 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids, v30, v29);
  }
  *((_BYTE *)this + 81) = 1;
  NamedAttributeValue = 0;
  LODWORD(v32) = 0;
LABEL_86:
  SysFreeString(v44);
  SysFreeString(v36);
  SysFreeString(pbstr);
  SysFreeString(v45);
  SysFreeString(v46[0]);
  SysFreeString(v40);
  ComPlainSmartPtr<CRadcXmlIcon>::~ComPlainSmartPtr<CRadcXmlIcon>(&v33);
  ComPlainSmartPtr<IRADCWorkspaceManager>::~ComPlainSmartPtr<IRADCWorkspaceManager>(&v35);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v38);
  ComPlainSmartPtr<IRADCWorkspaceManager>::~ComPlainSmartPtr<IRADCWorkspaceManager>(&v34);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v41);
  return (unsigned int)NamedAttributeValue;
}

```

## disassembly

```asm
0x180062b0c  mov     [rsp+arg_0], rcx
0x180062b11  push    rbx
0x180062b12  push    rsi
0x180062b13  push    rdi
0x180062b14  push    r12
0x180062b16  push    r13
0x180062b18  push    r14
0x180062b1a  push    r15
0x180062b1c  sub     rsp, 150h
0x180062b23  mov     [rsp+188h+var_C0], 0FFFFFFFFFFFFFFFEh
0x180062b2f  mov     r14, rcx
0x180062b32  xor     edi, edi
0x180062b34  mov     [rsp+188h+var_110], rdi
0x180062b39  mov     [rsp+188h+var_148], rdi
0x180062b3e  mov     [rsp+188h+var_128], rdi
0x180062b43  mov     [rsp+188h+var_140], rdi
0x180062b48  mov     [rsp+188h+var_150], rdi
0x180062b4d  lea     rdx, aXmlnsNsHttpSch; "xmlns:ns='http://schemas.microsoft.com/"...
0x180062b54  lea     rcx, [rsp+188h+var_118]; this
0x180062b59  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180062b5e  nop
0x180062b5f  lea     rdx, aNsPublisher; "//ns:Publisher"
0x180062b66  lea     rcx, [rsp+188h+var_C8]; this
0x180062b6e  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180062b73  nop
0x180062b74  lea     rdx, aNsResourcesNsR; "ns:Resources/ns:Resource"
0x180062b7b  lea     rcx, [rsp+188h+var_D0]; this
0x180062b83  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180062b88  nop
0x180062b89  mov     [rsp+188h+pbstr], rdi
0x180062b8e  mov     [rsp+188h+var_138], rdi
0x180062b93  mov     [rsp+188h+var_D8], rdi
0x180062b9b  mov     [rsp+188h+var_154], edi
0x180062b9f  mov     rcx, [r14+30h]
0x180062ba3  mov     rax, [rcx]
0x180062ba6  lea     rdx, [rsp+188h+var_110]
0x180062bab  mov     rax, [rax+168h]
0x180062bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062bb7  mov     [rsp+188h+var_158], eax
0x180062bbb  test    eax, eax
0x180062bbd  jz      short loc_180062C10
0x180062bbf  lea     rsi, WPP_GLOBAL_Control
0x180062bc6  mov     rax, cs:WPP_GLOBAL_Control
0x180062bcd  cmp     rax, rsi
0x180062bd0  jz      short loc_180062C02
0x180062bd2  test    byte ptr [rax+1Ch], 1
0x180062bd6  jz      short loc_180062C02
0x180062bd8  cmp     byte ptr [rax+19h], 2
0x180062bdc  jb      short loc_180062C02
0x180062bde  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180062be3  mov     edx, 85h
0x180062be8  mov     r9d, eax
0x180062beb  lea     r8, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x180062bf2  mov     rcx, cs:WPP_GLOBAL_Control
0x180062bf9  mov     rcx, [rcx+10h]
0x180062bfd  call    WPP_SF_D
0x180062c02  mov     ebx, 80040204h
0x180062c07  mov     [rsp+188h+var_158], ebx
0x180062c0b  jmp     loc_1800634EE
0x180062c10  mov     rbx, [r14+30h]
0x180062c14  mov     rsi, [rbx]
0x180062c17  mov     word ptr [rsp+188h+pvarg], di
0x180062c1f  lea     rcx, [rsp+188h+pvarg]; pvarg
0x180062c27  call    cs:__imp_VariantClear
0x180062c2d  mov     r13d, 8
0x180062c33  mov     word ptr [rsp+188h+pvarg], r13w
0x180062c3c  lea     rcx, psz; "XPath"
0x180062c43  call    cs:__imp_SysAllocString
0x180062c49  mov     dword ptr [rsp+188h+pvarg+8], eax
0x180062c50  mov     rcx, rax
0x180062c53  sar     rcx, 20h
0x180062c57  mov     dword ptr [rsp+188h+pvarg+0Ch], ecx
0x180062c5e  test    rax, rax
0x180062c61  jnz     short loc_180062C81
0x180062c63  lea     eax, [r13+2]
0x180062c67  mov     word ptr [rsp+188h+pvarg], ax
0x180062c6f  mov     ecx, 8007000Eh; int
0x180062c74  mov     dword ptr [rsp+188h+pvarg+8], ecx
0x180062c7b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180062c81  movups  xmm1, xmmword ptr [rsp+188h+pvarg]
0x180062c89  movups  [rsp+188h+var_78], xmm1
0x180062c91  movsd   xmm0, qword ptr [rsp+188h+pvarg+10h]
0x180062c9a  movsd   [rsp+188h+var_68], xmm0
0x180062ca3  movaps  [rsp+188h+var_B8], xmm1
0x180062cab  movsd   [rsp+188h+var_A8], xmm0
0x180062cb4  lea     r8, [rsp+188h+var_B8]
0x180062cbc  lea     rdx, aSelectionlangu; "SelectionLanguage"
0x180062cc3  mov     rcx, rbx
0x180062cc6  mov     rax, [rsi+280h]
0x180062ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062cd2  mov     ebx, eax
0x180062cd4  mov     [rsp+188h+var_158], eax
0x180062cd8  lea     rcx, [rsp+188h+pvarg]; pvarg
0x180062ce0  call    cs:__imp_VariantClear
0x180062ce6  test    ebx, ebx
0x180062ce8  jns     short loc_180062D43
0x180062cea  lea     rsi, WPP_GLOBAL_Control
0x180062cf1  mov     rax, cs:WPP_GLOBAL_Control
0x180062cf8  cmp     rax, rsi
0x180062cfb  jz      short loc_180062D3E
0x180062cfd  test    [rax+1Ch], r13b
0x180062d01  jz      short loc_180062D3E
0x180062d03  cmp     byte ptr [rax+19h], 2
0x180062d07  jb      short loc_180062D3E
0x180062d09  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180062d0e  mov     edx, 86h
0x180062d13  mov     [rsp+188h+var_160], ebx
0x180062d17  lea     rcx, aIxmldomdocumen_7; "IXmlDOMDocument::setproperty failed"
0x180062d1e  mov     [rsp+188h+var_168], rcx
0x180062d23  mov     r9d, eax
0x180062d26  lea     r8, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x180062d2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180062d34  mov     rcx, [rcx+10h]
0x180062d38  call    WPP_SF_DsD
0x180062d3d  nop
0x180062d3e  jmp     loc_1800634EA
0x180062d43  mov     rbx, [r14+30h]
0x180062d47  mov     rsi, [rbx]
0x180062d4a  mov     word ptr [rsp+188h+var_F0], di
0x180062d52  lea     rcx, [rsp+188h+var_F0]; pvarg
0x180062d5a  call    cs:__imp_VariantClear
0x180062d60  mov     word ptr [rsp+188h+var_F0], r13w
0x180062d69  lea     rcx, [rsp+188h+var_118]; this
0x180062d6e  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x180062d73  mov     dword ptr [rsp+188h+var_F0+8], eax
0x180062d7a  mov     rcx, rax
0x180062d7d  sar     rcx, 20h
0x180062d81  mov     dword ptr [rsp+188h+var_F0+0Ch], ecx
0x180062d88  test    rax, rax
0x180062d8b  jnz     short loc_180062DB3
0x180062d8d  cmp     [rsp+188h+var_118], rdi
0x180062d92  jz      short loc_180062DB3
0x180062d94  mov     eax, 0Ah
0x180062d99  mov     word ptr [rsp+188h+var_F0], ax
0x180062da1  mov     ecx, 8007000Eh; int
0x180062da6  mov     dword ptr [rsp+188h+var_F0+8], ecx
0x180062dad  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180062db3  movups  xmm1, xmmword ptr [rsp+188h+var_F0]
0x180062dbb  movups  [rsp+188h+var_60], xmm1
0x180062dc3  movsd   xmm0, qword ptr [rsp+188h+var_F0+10h]
0x180062dcc  movsd   [rsp+188h+var_50], xmm0
0x180062dd5  movaps  [rsp+188h+var_98], xmm1
0x180062ddd  movsd   [rsp+188h+var_88], xmm0
0x180062de6  lea     r8, [rsp+188h+var_98]
0x180062dee  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x180062df5  mov     rcx, rbx
0x180062df8  mov     rax, [rsi+280h]
0x180062dff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062e04  mov     ebx, eax
0x180062e06  mov     [rsp+188h+var_158], eax
0x180062e0a  lea     rcx, [rsp+188h+var_F0]; pvarg
0x180062e12  call    cs:__imp_VariantClear
0x180062e18  test    ebx, ebx
0x180062e1a  jns     short loc_180062E75
0x180062e1c  lea     rsi, WPP_GLOBAL_Control
0x180062e23  mov     rax, cs:WPP_GLOBAL_Control
0x180062e2a  cmp     rax, rsi
0x180062e2d  jz      short loc_180062E70
0x180062e2f  test    [rax+1Ch], r13b
0x180062e33  jz      short loc_180062E70
0x180062e35  cmp     byte ptr [rax+19h], 2
0x180062e39  jb      short loc_180062E70
0x180062e3b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180062e40  mov     edx, 87h
0x180062e45  mov     [rsp+188h+var_160], ebx
0x180062e49  lea     rcx, aIxmldomdocumen_7; "IXmlDOMDocument::setproperty failed"
0x180062e50  mov     [rsp+188h+var_168], rcx
0x180062e55  mov     r9d, eax
0x180062e58  lea     r8, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x180062e5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180062e66  mov     rcx, [rcx+10h]
0x180062e6a  call    WPP_SF_DsD
0x180062e6f  nop
0x180062e70  jmp     loc_1800634EA
0x180062e75  mov     rcx, [rsp+188h+var_110]
0x180062e7a  mov     rax, [rcx]
0x180062e7d  lea     r8, [rsp+188h+var_148]
0x180062e82  mov     rdx, [rsp+188h+var_C8]
0x180062e8a  mov     rax, [rax+128h]
0x180062e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062e96  mov     [rsp+188h+var_158], eax
0x180062e9a  test    eax, eax
0x180062e9c  jz      short loc_180062EEF
0x180062e9e  lea     rsi, WPP_GLOBAL_Control
0x180062ea5  mov     rax, cs:WPP_GLOBAL_Control
0x180062eac  cmp     rax, rsi
0x180062eaf  jz      short loc_180062EE1
0x180062eb1  test    byte ptr [rax+1Ch], 1
0x180062eb5  jz      short loc_180062EE1
0x180062eb7  cmp     byte ptr [rax+19h], 2
0x180062ebb  jb      short loc_180062EE1
0x180062ebd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180062ec2  mov     edx, 88h
0x180062ec7  mov     r9d, eax
0x180062eca  lea     r8, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x180062ed1  mov     rcx, cs:WPP_GLOBAL_Control
0x180062ed8  mov     rcx, [rcx+10h]
0x180062edc  call    WPP_SF_D
0x180062ee1  mov     ebx, 80040204h
0x180062ee6  mov     [rsp+188h+var_158], ebx
0x180062eea  jmp     loc_1800634EE
0x180062eef  lea     rdx, aName; "Name"
0x180062ef6  lea     rcx, [rsp+188h+bstrString]; this
0x180062efe  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180062f03  nop
0x180062f04  lea     r8, [rsp+188h+pbstr]; unsigned __int16 **
0x180062f09  mov     rdx, [rax]; unsigned __int16 *
0x180062f0c  mov     rcx, [rsp+188h+var_148]; struct IXMLDOMNode *
0x180062f11  call    ?GetNamedAttributeValue@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z; GetNamedAttributeValue(IXMLDOMNode *,ushort *,ushort * *)
0x180062f16  mov     ebx, eax
0x180062f18  mov     [rsp+188h+var_158], eax
0x180062f1c  mov     rcx, [rsp+188h+bstrString]; bstrString
0x180062f24  call    cs:__imp_SysFreeString
0x180062f2a  test    ebx, ebx
0x180062f2c  jns     short loc_180062F87
0x180062f2e  lea     rsi, WPP_GLOBAL_Control
0x180062f35  mov     rax, cs:WPP_GLOBAL_Control
0x180062f3c  cmp     rax, rsi
0x180062f3f  jz      short loc_180062F82
0x180062f41  test    [rax+1Ch], r13b
0x180062f45  jz      short loc_180062F82
0x180062f47  cmp     byte ptr [rax+19h], 2
0x180062f4b  jb      short loc_180062F82
0x180062f4d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180062f52  mov     edx, 89h
0x180062f57  mov     [rsp+188h+var_160], ebx
0x180062f5b  lea     rcx, aGetnamedattrib_5; "GetNamedAttributeValue for Publisher Na"...
0x180062f62  mov     [rsp+188h+var_168], rcx
0x180062f67  mov     r9d, eax
0x180062f6a  lea     r8, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x180062f71  mov     rcx, cs:WPP_GLOBAL_Control
0x180062f78  mov     rcx, [rcx+10h]
0x180062f7c  call    WPP_SF_DsD
0x180062f81  nop
0x180062f82  jmp     loc_1800634EA
0x180062f87  mov     rcx, [rsp+188h+pbstr]; pbstr
0x180062f8c  call    cs:__imp_SysStringLen
0x180062f92  mov     esi, 1401h
0x180062f97  cmp     eax, esi
0x180062f99  jb      short loc_180062FF4
0x180062f9b  lea     rsi, WPP_GLOBAL_Control
0x180062fa2  mov     rax, cs:WPP_GLOBAL_Control
0x180062fa9  cmp     rax, rsi
0x180062fac  jz      short loc_180062FE6
0x180062fae  test    [rax+1Ch], r13b
0x180062fb2  jz      short loc_180062FE6
0x180062fb4  cmp     byte ptr [rax+19h], 2
0x180062fb8  jb      short loc_180062FE6
0x180062fba  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180062fbf  mov     edx, 8Ah
0x180062fc4  mov     dword ptr [rsp+188h+var_168], 80040204h
0x180062fcc  mov     r9d, eax
0x180062fcf  lea     r8, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x180062fd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180062fdd  mov     rcx, [rcx+10h]
0x180062fe1  call    WPP_SF_Dd
0x180062fe6  mov     ebx, 80040204h
0x180062feb  mov     [rsp+188h+var_158], ebx
0x180062fef  jmp     loc_1800634EE
0x180062ff4  lea     rcx, [r14+58h]
0x180062ff8  mov     rdx, [rsp+188h+pbstr]
0x180062ffd  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180063002  lea     rdx, aId_0; "ID"
0x180063009  lea     rcx, [rsp+188h+bstrString]; this
0x180063011  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180063016  nop
0x180063017  lea     r8, [rsp+188h+var_138]; unsigned __int16 **
0x18006301c  mov     rdx, [rax]; unsigned __int16 *
0x18006301f  mov     rcx, [rsp+188h+var_148]; struct IXMLDOMNode *
0x180063024  call    ?GetNamedAttributeValue@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z; GetNamedAttributeValue(IXMLDOMNode *,ushort *,ushort * *)
0x180063029  mov     ebx, eax
0x18006302b  mov     [rsp+188h+var_158], eax
0x18006302f  mov     rcx, [rsp+188h+bstrString]; bstrString
0x180063037  call    cs:__imp_SysFreeString
0x18006303d  test    ebx, ebx
0x18006303f  jns     short loc_18006309A
0x180063041  lea     rsi, WPP_GLOBAL_Control
0x180063048  mov     rax, cs:WPP_GLOBAL_Control
0x18006304f  cmp     rax, rsi
0x180063052  jz      short loc_180063095
0x180063054  test    [rax+1Ch], r13b
0x180063058  jz      short loc_180063095
0x18006305a  cmp     byte ptr [rax+19h], 2
0x18006305e  jb      short loc_180063095
0x180063060  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180063065  mov     edx, 8Bh
0x18006306a  mov     [rsp+188h+var_160], ebx
0x18006306e  lea     rcx, aGetnamedattrib_8; "GetNamedAttributeValue for Workspace ID"...
0x180063075  mov     [rsp+188h+var_168], rcx
0x18006307a  mov     r9d, eax
0x18006307d  lea     r8, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x180063084  mov     rcx, cs:WPP_GLOBAL_Control
0x18006308b  mov     rcx, [rcx+10h]
0x18006308f  call    WPP_SF_DsD
0x180063094  nop
0x180063095  jmp     loc_1800634EA
0x18006309a  mov     rcx, [rsp+188h+var_138]; pbstr
0x18006309f  call    cs:__imp_SysStringLen
0x1800630a5  cmp     eax, esi
0x1800630a7  jb      short loc_180063102
  ... truncated ...
```
