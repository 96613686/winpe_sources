# CParser::BuildTenantFeedInfoList(void)

- ea: `0x1800635a0`
- end: `0x180063e84`
- name: `?BuildTenantFeedInfoList@CParser@@IEAAJXZ`
- size: `2276`
- prototype: `__int64 __fastcall(CParser *__hidden this)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180065568`
- `0x180065990`

## callees

- `0x1800054c4`
- `0x180005500`
- `0x180005524`
- `0x180007598`
- `0x18000b1d8`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x180010ba4`
- `0x180027914`
- `0x1800635a0`
- `0x1800651b0`
- `0x18006b928`
- `0x18006bef8`
- `0x18006c3b8`
- `0x1800a3010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18006368f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800637a1`
- `OLEAUT32!__imp_SysAllocString` at `0x18006368f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800637a1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800638c5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800639c5`
- `OLEAUT32!__imp_SysFreeString` at `0x180063e53`
- `OLEAUT32!__imp_SysFreeString` at `0x1800638c5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800639c5`
- `OLEAUT32!__imp_SysFreeString` at `0x180063e53`
- `OLEAUT32!__imp_VariantClear` at `0x180063676`
- `OLEAUT32!__imp_VariantClear` at `0x180063717`
- `OLEAUT32!__imp_VariantClear` at `0x18006378e`
- `OLEAUT32!__imp_VariantClear` at `0x18006382a`
- `OLEAUT32!__imp_VariantClear` at `0x180063676`
- `OLEAUT32!__imp_VariantClear` at `0x180063717`
- `OLEAUT32!__imp_VariantClear` at `0x18006378e`
- `OLEAUT32!__imp_VariantClear` at `0x18006382a`

## string_xrefs

- `0x180063688`: `XPath`
- `0x18006374e`: `IXmlDOMDocument::setproperty failed`
- `0x180063861`: `IXmlDOMDocument::setproperty failed`
- `0x18006379a`: `xmlns:ns='http://schemas.microsoft.com/ts/2014/03/tswfdiscovery'`
- `0x1800639f5`: `IXMLDOMNode::SelectNodes failed for all resources.`
- `0x180063abe`: `IXMLDOMNodeList::get_length failed for numFeeds nodes`
- `0x180063c31`: `IXMLDomNodeList::item failed.`
- `0x180063d35`: `RadcXmlTenantFeedInfo::CreateInstance failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall CParser::BuildTenantFeedInfoList(CParser *this)
{
  _BYTE *v2; // r12
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int NamedAttributeValue; // ebx
  __int64 *v5; // rbx
  __int64 v6; // rdi
  unsigned int v7; // eax
  __int64 *v8; // rbx
  __int64 v9; // rdi
  unsigned int v10; // eax
  unsigned __int16 **v11; // rax
  unsigned int v12; // eax
  unsigned int v13; // eax
  struct IXMLDOMNode *v14; // rdi
  HRESULT (__stdcall *selectNodes)(IXMLDOMNode *, BSTR, IXMLDOMNodeList **); // rbx
  _QWORD *v16; // rax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  PVOID *v20; // rax
  int v21; // ebx
  unsigned int v22; // eax
  int v23; // ebx
  unsigned int v24; // eax
  unsigned int v25; // edi
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  __int64 v32; // [rsp+30h] [rbp-118h] BYREF
  __int64 v33; // [rsp+38h] [rbp-110h] BYREF
  struct IXMLDOMNode *v34; // [rsp+40h] [rbp-108h] BYREF
  int v35; // [rsp+48h] [rbp-100h]
  VARIANTARG pvarg; // [rsp+50h] [rbp-F8h] BYREF
  VARIANTARG v37; // [rsp+68h] [rbp-E0h] BYREF
  BSTR v38[2]; // [rsp+80h] [rbp-C8h] BYREF
  VARIANTARG v39; // [rsp+90h] [rbp-B8h] BYREF
  VARIANTARG v40[6]; // [rsp+B0h] [rbp-98h] BYREF
  BSTR bstrString; // [rsp+158h] [rbp+10h] BYREF
  struct IXMLDOMNode *v42; // [rsp+160h] [rbp+18h] BYREF
  char *v43; // [rsp+168h] [rbp+20h]

  v38[1] = (BSTR)-2LL;
  v34 = 0;
  v33 = 0;
  HIDWORD(v32) = 0;
  v38[0] = 0;
  v2 = (char *)this + 80;
  v43 = (char *)this + 80;
  *((_BYTE *)this + 80) = 0;
  LODWORD(v32) = (*(__int64 (__fastcall **)(_QWORD, struct IXMLDOMNode **))(**((_QWORD **)this + 21) + 360LL))(
                   *((_QWORD *)this + 21),
                   &v34);
  if ( (_DWORD)v32 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        147,
        &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
    NamedAttributeValue = -2147220988;
    LODWORD(v32) = -2147220988;
LABEL_87:
    std::vector<ComPlainSmartPtr<CTenantFeedInfo>>::clear((char *)this + 176);
    *v2 = 0;
    goto LABEL_88;
  }
  v5 = (__int64 *)*((_QWORD *)this + 21);
  v6 = *v5;
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
  *(VARIANTARG *)((char *)&v40[1] + 8) = pvarg;
  v39 = pvarg;
  NamedAttributeValue = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v6 + 640))(
                          v5,
                          L"SelectionLanguage",
                          &v39);
  LODWORD(v32) = NamedAttributeValue;
  VariantClear(&pvarg);
  if ( NamedAttributeValue < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        148,
        (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
        v7,
        (__int64)"IXmlDOMDocument::setproperty failed",
        NamedAttributeValue,
        v32);
    }
    goto LABEL_87;
  }
  v8 = (__int64 *)*((_QWORD *)this + 21);
  v9 = *v8;
  v37.vt = 0;
  VariantClear(&v37);
  v37.vt = 8;
  v37.llVal = (LONGLONG)SysAllocString(L"xmlns:ns='http://schemas.microsoft.com/ts/2014/03/tswfdiscovery'");
  if ( !v37.llVal )
  {
    v37.vt = 10;
    v37.lVal = -2147024882;
    ATL::AtlThrowImpl(-2147024882);
  }
  *(VARIANTARG *)((char *)&v40[2] + 8) = v37;
  v40[0] = v37;
  NamedAttributeValue = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v9 + 640))(
                          v8,
                          L"SelectionNamespaces",
                          v40);
  LODWORD(v32) = NamedAttributeValue;
  VariantClear(&v37);
  if ( NamedAttributeValue < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        149,
        (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
        v10,
        (__int64)"IXmlDOMDocument::setproperty failed",
        NamedAttributeValue,
        v32);
    }
    goto LABEL_87;
  }
  v11 = (unsigned __int16 **)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"UserIdType");
  NamedAttributeValue = GetNamedAttributeValue(v34, *v11, v38);
  LODWORD(v32) = NamedAttributeValue;
  SysFreeString(bstrString);
  if ( NamedAttributeValue == -2147023728 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids, v12);
    }
    LODWORD(v32) = 0;
  }
  else if ( NamedAttributeValue < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        151,
        (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
        v13,
        (__int64)"GetNamedAttributeValue for UserIdType failed",
        NamedAttributeValue,
        v32);
    }
    goto LABEL_87;
  }
  v14 = v34;
  selectNodes = v34->lpVtbl->selectNodes;
  v16 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"//ns:TenantFeedURL");
  NamedAttributeValue = ((__int64 (__fastcall *)(struct IXMLDOMNode *, _QWORD, __int64 *))selectNodes)(v14, *v16, &v33);
  LODWORD(v32) = NamedAttributeValue;
  SysFreeString(bstrString);
  if ( NamedAttributeValue < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        152,
        (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
        v17,
        (__int64)"IXMLDOMNode::SelectNodes failed for all resources.",
        NamedAttributeValue,
        v32);
    }
    goto LABEL_87;
  }
  if ( !v33 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        153,
        &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
        v18,
        -2147418113);
    }
    NamedAttributeValue = -2147418113;
    LODWORD(v32) = -2147418113;
    goto LABEL_87;
  }
  NamedAttributeValue = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v33 + 64LL))(v33, (char *)&v32 + 4);
  LODWORD(v32) = NamedAttributeValue;
  if ( NamedAttributeValue < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        154,
        (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
        v19,
        (__int64)"IXMLDOMNodeList::get_length failed for numFeeds nodes",
        NamedAttributeValue,
        v32);
    }
    goto LABEL_87;
  }
  v20 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v21 = HIDWORD(v32);
    v22 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids, v22, v21);
    v20 = (PVOID *)WPP_GLOBAL_Control;
  }
  v23 = HIDWORD(v32);
  if ( SHIDWORD(v32) <= 0 )
  {
    if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 8) != 0 && *((_BYTE *)v20 + 25) >= 2u )
    {
      v24 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        156,
        &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
        v24,
        -2147220966);
    }
    NamedAttributeValue = -2147220966;
    LODWORD(v32) = -2147220966;
    goto LABEL_87;
  }
  v25 = 0;
  v35 = 0;
  while ( (int)v25 < v23 )
  {
    v42 = 0;
    bstrString = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v26 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 157, &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids, v26, v25);
    }
    NamedAttributeValue = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IXMLDOMNode **))(*(_QWORD *)v33 + 56LL))(
                            v33,
                            v25,
                            &v42);
    LODWORD(v32) = NamedAttributeValue;
    if ( NamedAttributeValue < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v27 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          158,
          (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
          v27,
          (__int64)"IXMLDomNodeList::item failed.",
          NamedAttributeValue,
          v32);
      }
LABEL_69:
      ComPlainSmartPtr<CRadcXmlIcon>::~ComPlainSmartPtr<CRadcXmlIcon>(&bstrString);
      ComPlainSmartPtr<IRADCWorkspaceManager>::~ComPlainSmartPtr<IRADCWorkspaceManager>(&v42);
      goto LABEL_87;
    }
    if ( !v42 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v28 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          159,
          (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
          v28,
          (__int64)"spTenantFeedURLNode");
      }
      NamedAttributeValue = -2147467261;
      LODWORD(v32) = -2147467261;
      ComPlainSmartPtr<CRadcXmlIcon>::~ComPlainSmartPtr<CRadcXmlIcon>(&bstrString);
      ComPlainSmartPtr<IRADCWorkspaceManager>::~ComPlainSmartPtr<IRADCWorkspaceManager>(&v42);
      goto LABEL_87;
    }
    NamedAttributeValue = CTenantFeedInfo::CreateInstance(v42, (struct CTenantFeedInfo **)&bstrString);
    LODWORD(v32) = NamedAttributeValue;
    if ( NamedAttributeValue < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v29 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          160,
          (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
          v29,
          (__int64)"RadcXmlTenantFeedInfo::CreateInstance failed",
          NamedAttributeValue,
          v32);
      }
      goto LABEL_69;
    }
    std::vector<ComPlainSmartPtr<CResource>>::push_back((char *)this + 176, &bstrString);
    ComPlainSmartPtr<CRadcXmlIcon>::~ComPlainSmartPtr<CRadcXmlIcon>(&bstrString);
    ComPlainSmartPtr<IRADCWorkspaceManager>::~ComPlainSmartPtr<IRADCWorkspaceManager>(&v42);
    v35 = ++v25;
    v23 = HIDWORD(v32);
    v20 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 1) != 0 && *((_BYTE *)v20 + 25) >= 4u )
  {
    v30 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 161, &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids, v30, v23);
  }
  *v2 = 1;
  NamedAttributeValue = 0;
  LODWORD(v32) = 0;
LABEL_88:
  SysFreeString(v38[0]);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v33);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v34);
  return (unsigned int)NamedAttributeValue;
}

```

## disassembly

```asm
0x1800635a0  mov     [rsp+arg_0], rcx
0x1800635a5  push    rbx
0x1800635a6  push    rsi
0x1800635a7  push    rdi
0x1800635a8  push    r12
0x1800635aa  push    r13
0x1800635ac  push    r14
0x1800635ae  push    r15
0x1800635b0  sub     rsp, 110h
0x1800635b7  mov     [rsp+148h+var_C0], 0FFFFFFFFFFFFFFFEh
0x1800635c3  mov     r15, rcx
0x1800635c6  xor     esi, esi
0x1800635c8  mov     [rsp+148h+var_108], rsi
0x1800635cd  mov     [rsp+148h+var_110], rsi
0x1800635d2  mov     [rsp+148h+var_114], esi
0x1800635d6  mov     [rsp+148h+var_C8], rsi
0x1800635de  lea     r12, [rcx+50h]
0x1800635e2  mov     [rsp+148h+arg_18], r12
0x1800635ea  mov     [r12], sil
0x1800635ee  mov     rcx, [rcx+0A8h]
0x1800635f5  mov     rax, [rcx]
0x1800635f8  lea     rdx, [rsp+148h+var_108]
0x1800635fd  mov     rax, [rax+168h]
0x180063604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063609  mov     [rsp+148h+var_118], eax
0x18006360d  test    eax, eax
0x18006360f  jz      short loc_180063662
0x180063611  lea     r14, WPP_GLOBAL_Control
0x180063618  mov     rax, cs:WPP_GLOBAL_Control
0x18006361f  cmp     rax, r14
0x180063622  jz      short loc_180063654
0x180063624  test    byte ptr [rax+1Ch], 1
0x180063628  jz      short loc_180063654
0x18006362a  cmp     byte ptr [rax+19h], 2
0x18006362e  jb      short loc_180063654
0x180063630  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180063635  mov     edx, 93h
0x18006363a  mov     r9d, eax
0x18006363d  lea     r8, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x180063644  mov     rcx, cs:WPP_GLOBAL_Control
0x18006364b  mov     rcx, [rcx+10h]
0x18006364f  call    WPP_SF_D
0x180063654  mov     ebx, 80040204h
0x180063659  mov     [rsp+148h+var_118], ebx
0x18006365d  jmp     loc_180063E3B
0x180063662  mov     rbx, [r15+0A8h]
0x180063669  mov     rdi, [rbx]
0x18006366c  mov     word ptr [rsp+148h+pvarg], si
0x180063671  lea     rcx, [rsp+148h+pvarg]; pvarg
0x180063676  call    cs:__imp_VariantClear
0x18006367c  mov     r13d, 8
0x180063682  mov     word ptr [rsp+148h+pvarg], r13w
0x180063688  lea     rcx, psz; "XPath"
0x18006368f  call    cs:__imp_SysAllocString
0x180063695  mov     dword ptr [rsp+148h+pvarg+8], eax
0x180063699  mov     rcx, rax
0x18006369c  sar     rcx, 20h
0x1800636a0  mov     dword ptr [rsp+148h+pvarg+0Ch], ecx
0x1800636a4  test    rax, rax
0x1800636a7  jnz     short loc_1800636C1
0x1800636a9  lea     eax, [r13+2]
0x1800636ad  mov     word ptr [rsp+148h+pvarg], ax
0x1800636b2  mov     ecx, 8007000Eh; int
0x1800636b7  mov     dword ptr [rsp+148h+pvarg+8], ecx
0x1800636bb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800636c1  movups  xmm1, xmmword ptr [rsp+148h+pvarg]
0x1800636c6  movups  [rsp+148h+var_78], xmm1
0x1800636ce  movsd   xmm0, qword ptr [rsp+148h+pvarg+10h]
0x1800636d4  movsd   [rsp+148h+var_68], xmm0
0x1800636dd  movaps  [rsp+148h+var_B8], xmm1
0x1800636e5  movsd   [rsp+148h+var_A8], xmm0
0x1800636ee  lea     r8, [rsp+148h+var_B8]
0x1800636f6  lea     rdx, aSelectionlangu; "SelectionLanguage"
0x1800636fd  mov     rcx, rbx
0x180063700  mov     rax, [rdi+280h]
0x180063707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006370c  mov     ebx, eax
0x18006370e  mov     [rsp+148h+var_118], eax
0x180063712  lea     rcx, [rsp+148h+pvarg]; pvarg
0x180063717  call    cs:__imp_VariantClear
0x18006371d  test    ebx, ebx
0x18006371f  jns     short loc_18006377A
0x180063721  lea     r14, WPP_GLOBAL_Control
0x180063728  mov     rax, cs:WPP_GLOBAL_Control
0x18006372f  cmp     rax, r14
0x180063732  jz      short loc_180063775
0x180063734  test    [rax+1Ch], r13b
0x180063738  jz      short loc_180063775
0x18006373a  cmp     byte ptr [rax+19h], 2
0x18006373e  jb      short loc_180063775
0x180063740  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180063745  mov     edx, 94h
0x18006374a  mov     [rsp+148h+var_120], ebx
0x18006374e  lea     rcx, aIxmldomdocumen_7; "IXmlDOMDocument::setproperty failed"
0x180063755  mov     [rsp+148h+var_128], rcx
0x18006375a  mov     r9d, eax
0x18006375d  lea     r8, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x180063764  mov     rcx, cs:WPP_GLOBAL_Control
0x18006376b  mov     rcx, [rcx+10h]
0x18006376f  call    WPP_SF_DsD
0x180063774  nop
0x180063775  jmp     loc_180063E37
0x18006377a  mov     rbx, [r15+0A8h]
0x180063781  mov     rdi, [rbx]
0x180063784  mov     word ptr [rsp+148h+var_E0], si
0x180063789  lea     rcx, [rsp+148h+var_E0]; pvarg
0x18006378e  call    cs:__imp_VariantClear
0x180063794  mov     word ptr [rsp+148h+var_E0], r13w
0x18006379a  lea     rcx, aXmlnsNsHttpSch_0; "xmlns:ns='http://schemas.microsoft.com/"...
0x1800637a1  call    cs:__imp_SysAllocString
0x1800637a7  mov     dword ptr [rsp+148h+var_E0+8], eax
0x1800637ab  mov     rcx, rax
0x1800637ae  sar     rcx, 20h
0x1800637b2  mov     dword ptr [rsp+148h+var_E0+0Ch], ecx
0x1800637b6  test    rax, rax
0x1800637b9  jnz     short loc_1800637D4
0x1800637bb  mov     eax, 0Ah
0x1800637c0  mov     word ptr [rsp+148h+var_E0], ax
0x1800637c5  mov     ecx, 8007000Eh; int
0x1800637ca  mov     dword ptr [rsp+148h+var_E0+8], ecx
0x1800637ce  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800637d4  movups  xmm1, xmmword ptr [rsp+148h+var_E0]
0x1800637d9  movups  [rsp+148h+var_60], xmm1
0x1800637e1  movsd   xmm0, qword ptr [rsp+148h+var_E0+10h]
0x1800637e7  movsd   [rsp+148h+var_50], xmm0
0x1800637f0  movaps  [rsp+148h+var_98], xmm1
0x1800637f8  movsd   [rsp+148h+var_88], xmm0
0x180063801  lea     r8, [rsp+148h+var_98]
0x180063809  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x180063810  mov     rcx, rbx
0x180063813  mov     rax, [rdi+280h]
0x18006381a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006381f  mov     ebx, eax
0x180063821  mov     [rsp+148h+var_118], eax
0x180063825  lea     rcx, [rsp+148h+var_E0]; pvarg
0x18006382a  call    cs:__imp_VariantClear
0x180063830  test    ebx, ebx
0x180063832  jns     short loc_18006388D
0x180063834  lea     r14, WPP_GLOBAL_Control
0x18006383b  mov     rax, cs:WPP_GLOBAL_Control
0x180063842  cmp     rax, r14
0x180063845  jz      short loc_180063888
0x180063847  test    [rax+1Ch], r13b
0x18006384b  jz      short loc_180063888
0x18006384d  cmp     byte ptr [rax+19h], 2
0x180063851  jb      short loc_180063888
0x180063853  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180063858  mov     edx, 95h
0x18006385d  mov     [rsp+148h+var_120], ebx
0x180063861  lea     rcx, aIxmldomdocumen_7; "IXmlDOMDocument::setproperty failed"
0x180063868  mov     [rsp+148h+var_128], rcx
0x18006386d  mov     r9d, eax
0x180063870  lea     r8, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x180063877  mov     rcx, cs:WPP_GLOBAL_Control
0x18006387e  mov     rcx, [rcx+10h]
0x180063882  call    WPP_SF_DsD
0x180063887  nop
0x180063888  jmp     loc_180063E37
0x18006388d  lea     rdx, aUseridtype; "UserIdType"
0x180063894  lea     rcx, [rsp+148h+bstrString]; this
0x18006389c  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800638a1  nop
0x1800638a2  lea     r8, [rsp+148h+var_C8]; unsigned __int16 **
0x1800638aa  mov     rdx, [rax]; unsigned __int16 *
0x1800638ad  mov     rcx, [rsp+148h+var_108]; struct IXMLDOMNode *
0x1800638b2  call    ?GetNamedAttributeValue@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z; GetNamedAttributeValue(IXMLDOMNode *,ushort *,ushort * *)
0x1800638b7  mov     ebx, eax
0x1800638b9  mov     [rsp+148h+var_118], eax
0x1800638bd  mov     rcx, [rsp+148h+bstrString]; bstrString
0x1800638c5  call    cs:__imp_SysFreeString
0x1800638cb  cmp     ebx, 80070490h
0x1800638d1  jnz     short loc_18006391C
0x1800638d3  lea     r14, WPP_GLOBAL_Control
0x1800638da  mov     rax, cs:WPP_GLOBAL_Control
0x1800638e1  cmp     rax, r14
0x1800638e4  jz      short loc_180063916
0x1800638e6  test    byte ptr [rax+1Ch], 1
0x1800638ea  jz      short loc_180063916
0x1800638ec  cmp     byte ptr [rax+19h], 4
0x1800638f0  jb      short loc_180063916
0x1800638f2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800638f7  mov     edx, 96h
0x1800638fc  mov     r9d, eax
0x1800638ff  lea     r8, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x180063906  mov     rcx, cs:WPP_GLOBAL_Control
0x18006390d  mov     rcx, [rcx+10h]
0x180063911  call    WPP_SF_D
0x180063916  mov     [rsp+148h+var_118], esi
0x18006391a  jmp     short loc_180063980
0x18006391c  test    ebx, ebx
0x18006391e  jns     short loc_180063979
0x180063920  lea     r14, WPP_GLOBAL_Control
0x180063927  mov     rax, cs:WPP_GLOBAL_Control
0x18006392e  cmp     rax, r14
0x180063931  jz      short loc_180063974
0x180063933  test    [rax+1Ch], r13b
0x180063937  jz      short loc_180063974
0x180063939  cmp     byte ptr [rax+19h], 2
0x18006393d  jb      short loc_180063974
0x18006393f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180063944  mov     edx, 97h
0x180063949  mov     [rsp+148h+var_120], ebx
0x18006394d  lea     rcx, aGetnamedattrib_13; "GetNamedAttributeValue for UserIdType f"...
0x180063954  mov     [rsp+148h+var_128], rcx
0x180063959  mov     r9d, eax
0x18006395c  lea     r8, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x180063963  mov     rcx, cs:WPP_GLOBAL_Control
0x18006396a  mov     rcx, [rcx+10h]
0x18006396e  call    WPP_SF_DsD
0x180063973  nop
0x180063974  jmp     loc_180063E37
0x180063979  lea     r14, WPP_GLOBAL_Control
0x180063980  mov     rdi, [rsp+148h+var_108]
0x180063985  mov     rax, [rdi]
0x180063988  mov     rbx, [rax+120h]
0x18006398f  lea     rdx, aNsTenantfeedur; "//ns:TenantFeedURL"
0x180063996  lea     rcx, [rsp+148h+bstrString]; this
0x18006399e  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800639a3  nop
0x1800639a4  lea     r8, [rsp+148h+var_110]
0x1800639a9  mov     rdx, [rax]
0x1800639ac  mov     rcx, rdi
0x1800639af  mov     rax, rbx
0x1800639b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800639b7  mov     ebx, eax
0x1800639b9  mov     [rsp+148h+var_118], eax
0x1800639bd  mov     rcx, [rsp+148h+bstrString]; bstrString
0x1800639c5  call    cs:__imp_SysFreeString
0x1800639cb  test    ebx, ebx
0x1800639cd  jns     short loc_180063A21
0x1800639cf  mov     rax, cs:WPP_GLOBAL_Control
0x1800639d6  cmp     rax, r14
0x1800639d9  jz      short loc_180063A1C
0x1800639db  test    [rax+1Ch], r13b
0x1800639df  jz      short loc_180063A1C
0x1800639e1  cmp     byte ptr [rax+19h], 2
0x1800639e5  jb      short loc_180063A1C
0x1800639e7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800639ec  mov     edx, 98h
0x1800639f1  mov     [rsp+148h+var_120], ebx
0x1800639f5  lea     rcx, aIxmldomnodeSel; "IXMLDOMNode::SelectNodes failed for all"...
0x1800639fc  mov     [rsp+148h+var_128], rcx
0x180063a01  mov     r9d, eax
0x180063a04  lea     r8, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x180063a0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180063a12  mov     rcx, [rcx+10h]
0x180063a16  call    WPP_SF_DsD
0x180063a1b  nop
0x180063a1c  jmp     loc_180063E37
0x180063a21  mov     rcx, [rsp+148h+var_110]
0x180063a26  test    rcx, rcx
0x180063a29  jnz     short loc_180063A7D
0x180063a2b  mov     rax, cs:WPP_GLOBAL_Control
0x180063a32  cmp     rax, r14
0x180063a35  jz      short loc_180063A6F
0x180063a37  test    [rax+1Ch], r13b
0x180063a3b  jz      short loc_180063A6F
0x180063a3d  cmp     byte ptr [rax+19h], 2
0x180063a41  jb      short loc_180063A6F
0x180063a43  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180063a48  mov     edx, 99h
0x180063a4d  mov     dword ptr [rsp+148h+var_128], 8000FFFFh
0x180063a55  mov     r9d, eax
0x180063a58  lea     r8, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x180063a5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180063a66  mov     rcx, [rcx+10h]
0x180063a6a  call    WPP_SF_Dd
0x180063a6f  mov     ebx, 8000FFFFh
0x180063a74  mov     [rsp+148h+var_118], ebx
0x180063a78  jmp     loc_180063E3B
0x180063a7d  mov     rax, [rcx]
0x180063a80  lea     rdx, [rsp+148h+var_114]
0x180063a85  mov     rax, [rax+40h]
0x180063a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063a8e  mov     ebx, eax
0x180063a90  mov     [rsp+148h+var_118], eax
0x180063a94  test    eax, eax
0x180063a96  jns     short loc_180063AEA
0x180063a98  mov     rax, cs:WPP_GLOBAL_Control
0x180063a9f  cmp     rax, r14
0x180063aa2  jz      short loc_180063AE5
0x180063aa4  test    [rax+1Ch], r13b
0x180063aa8  jz      short loc_180063AE5
0x180063aaa  cmp     byte ptr [rax+19h], 2
0x180063aae  jb      short loc_180063AE5
0x180063ab0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180063ab5  mov     edx, 9Ah
0x180063aba  mov     [rsp+148h+var_120], ebx
0x180063abe  lea     rcx, aIxmldomnodelis_2; "IXMLDOMNodeList::get_length failed for "...
0x180063ac5  mov     [rsp+148h+var_128], rcx
0x180063aca  mov     r9d, eax
0x180063acd  lea     r8, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x180063ad4  mov     rcx, cs:WPP_GLOBAL_Control
0x180063adb  mov     rcx, [rcx+10h]
0x180063adf  call    WPP_SF_DsD
0x180063ae4  nop
0x180063ae5  jmp     loc_180063E37
0x180063aea  mov     rax, cs:WPP_GLOBAL_Control
0x180063af1  cmp     rax, r14
0x180063af4  jz      short loc_180063B35
  ... truncated ...
```
