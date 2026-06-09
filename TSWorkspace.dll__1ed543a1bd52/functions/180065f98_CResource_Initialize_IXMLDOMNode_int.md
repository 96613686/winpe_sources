# CResource::Initialize(IXMLDOMNode *,int)

- ea: `0x180065f98`
- end: `0x180067070`
- name: `?Initialize@CResource@@QEAAJPEAUIXMLDOMNode@@H@Z`
- size: `4312`
- prototype: `__int64 __fastcall(CResource *__hidden this, struct IXMLDOMNode *, int)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180063fc4`

## callees

- `0x180003108`
- `0x1800054c4`
- `0x180005524`
- `0x18000b1d8`
- `0x18000c3d0`
- `0x18000d948`
- `0x18000dbdc`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x18001e610`
- `0x180020bf0`
- `0x180027914`
- `0x18003cb1c`
- `0x180060cf8`
- `0x180061488`
- `0x180061d5c`
- `0x180064a64`
- `0x1800651b0`
- `0x180065cc4`
- `0x180065f98`
- `0x1800681b8`
- `0x18009a520`
- `0x1800a3010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180066127`
- `msvcrt!_wcsicmp` at `0x1800664f0`
- `msvcrt!_wcsicmp` at `0x180066127`
- `msvcrt!_wcsicmp` at `0x1800664f0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180066ff6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180066ff6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800660a3`
- `OLEAUT32!__imp_SysFreeString` at `0x180066198`
- `OLEAUT32!__imp_SysFreeString` at `0x1800661d2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800662b6`
- `OLEAUT32!__imp_SysFreeString` at `0x18006639d`
- `OLEAUT32!__imp_SysFreeString` at `0x180066484`
- `OLEAUT32!__imp_SysFreeString` at `0x180066604`
- `OLEAUT32!__imp_SysFreeString` at `0x180066790`
- `OLEAUT32!__imp_SysFreeString` at `0x180066960`
- `OLEAUT32!__imp_SysFreeString` at `0x180066a9a`
- `OLEAUT32!__imp_SysFreeString` at `0x180066b21`
- `OLEAUT32!__imp_SysFreeString` at `0x180066c2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180066cb2`
- `OLEAUT32!__imp_SysFreeString` at `0x180066d96`
- `OLEAUT32!__imp_SysFreeString` at `0x180067010`
- `OLEAUT32!__imp_SysFreeString` at `0x1800660a3`
- `OLEAUT32!__imp_SysFreeString` at `0x180066198`
- `OLEAUT32!__imp_SysFreeString` at `0x1800661d2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800662b6`
- `OLEAUT32!__imp_SysFreeString` at `0x18006639d`
- `OLEAUT32!__imp_SysFreeString` at `0x180066484`
- `OLEAUT32!__imp_SysFreeString` at `0x180066604`
- `OLEAUT32!__imp_SysFreeString` at `0x180066790`
- `OLEAUT32!__imp_SysFreeString` at `0x180066960`
- `OLEAUT32!__imp_SysFreeString` at `0x180066a9a`
- `OLEAUT32!__imp_SysFreeString` at `0x180066b21`
- `OLEAUT32!__imp_SysFreeString` at `0x180066c2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180066cb2`
- `OLEAUT32!__imp_SysFreeString` at `0x180066d96`
- `OLEAUT32!__imp_SysFreeString` at `0x180067010`
- `OLEAUT32!__imp_SysStringLen` at `0x180066df3`
- `OLEAUT32!__imp_SysStringLen` at `0x180066e7e`
- `OLEAUT32!__imp_SysStringLen` at `0x180066e89`
- `OLEAUT32!__imp_SysStringLen` at `0x180066df3`
- `OLEAUT32!__imp_SysStringLen` at `0x180066e7e`
- `OLEAUT32!__imp_SysStringLen` at `0x180066e89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066ed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066f0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066ed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066f0c`
- `KERNEL32!LCMapStringW` at `0x180066eb1`
- `KERNEL32!LCMapStringW` at `0x180066eb1`

## string_xrefs

- `0x1800665d0`: `ns:FileExtensions/ns:FileExtension`
- `0x1800666a6`: `IXMLDOMNodeList::get_length failed`
- `0x18006682e`: `IXMLDOMNodeList::get_length(Folders) failed`
- `0x180066909`: `IXMLDOMNodeList::item(Folders) failed`
- `0x180066aca`: `GetIndexedNodeFromXPath failed`
- `0x180066c5b`: `GetIndexedNodeFromXPath failed`
- `0x180066d67`: `FileExtension`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall CResource::Initialize(CResource *this, struct IXMLDOMNode *a2, int a3)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int NamedAttributeValue; // ebx
  unsigned __int16 **v7; // rax
  unsigned int v8; // eax
  unsigned int i; // ebx
  int v10; // ebx
  unsigned int v11; // eax
  unsigned __int16 **v12; // rax
  unsigned int v13; // eax
  wchar_t *v14; // rdx
  _QWORD *v15; // rbx
  unsigned int v16; // eax
  unsigned __int16 **v17; // rax
  unsigned int v18; // eax
  wchar_t *v19; // rdx
  _QWORD *v20; // rbx
  unsigned int v21; // eax
  unsigned __int16 **v22; // rax
  unsigned int v23; // eax
  wchar_t *v24; // rdx
  _QWORD *v25; // rbx
  unsigned int v26; // eax
  unsigned __int16 **v27; // rax
  unsigned int v28; // eax
  int v29; // ebx
  unsigned int v30; // eax
  unsigned int v31; // eax
  HRESULT (__stdcall *selectNodes)(IXMLDOMNode *, BSTR, IXMLDOMNodeList **); // rbx
  _QWORD *v33; // rax
  unsigned int v34; // eax
  unsigned int v35; // eax
  int v36; // ebx
  unsigned int v37; // eax
  unsigned int v38; // eax
  struct IXMLDOMNode *v39; // rdi
  HRESULT (__stdcall *v40)(IXMLDOMNode *, BSTR, IXMLDOMNodeList **); // rbx
  _QWORD *v41; // rax
  unsigned int v42; // eax
  unsigned int v43; // eax
  int v44; // ebx
  unsigned int v45; // eax
  unsigned int v46; // edi
  unsigned int v47; // eax
  unsigned __int16 **v48; // rax
  unsigned int v49; // eax
  wchar_t *v50; // rbx
  __int64 v51; // rdx
  unsigned int v52; // eax
  unsigned __int16 **v53; // rax
  unsigned int v54; // r8d
  unsigned int v55; // eax
  unsigned __int16 **v56; // rax
  unsigned int v57; // eax
  wchar_t *v58; // rdx
  CResource *v59; // rdi
  _QWORD *v60; // rbx
  unsigned int v61; // eax
  struct IXMLDOMNode *v62; // rcx
  unsigned __int16 **v63; // rax
  unsigned int v64; // r8d
  unsigned int v65; // eax
  unsigned __int16 **v66; // rax
  unsigned int v67; // eax
  wchar_t *v68; // rdx
  _QWORD *v69; // rbx
  unsigned int v70; // eax
  unsigned __int16 **v71; // rax
  unsigned int v72; // eax
  unsigned __int64 v73; // rax
  unsigned __int64 v74; // kr10_8
  unsigned int v75; // eax
  wchar_t *v76; // rbx
  UINT v77; // edi
  UINT v78; // eax
  signed int LastError; // eax
  unsigned int v80; // ebx
  unsigned int v81; // eax
  signed int v82; // eax
  CResource *v83; // rdi
  _QWORD *v84; // rbx
  unsigned int v85; // eax
  int inited; // ebx
  unsigned int v87; // eax
  wchar_t *String1; // [rsp+38h] [rbp-E0h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-D8h] BYREF
  struct IXMLDOMNode *v91; // [rsp+48h] [rbp-D0h]
  struct IXMLDOMNode *v92; // [rsp+50h] [rbp-C8h] BYREF
  int v93; // [rsp+58h] [rbp-C0h] BYREF
  struct IXMLDOMNode *v94; // [rsp+60h] [rbp-B8h] BYREF
  LPWSTR lpDestStr; // [rsp+68h] [rbp-B0h]
  __int64 v96; // [rsp+70h] [rbp-A8h] BYREF
  unsigned int v97; // [rsp+78h] [rbp-A0h]
  int v98; // [rsp+7Ch] [rbp-9Ch]
  int v99; // [rsp+80h] [rbp-98h]
  CResource *v100; // [rsp+88h] [rbp-90h]
  _QWORD v101[2]; // [rsp+90h] [rbp-88h] BYREF
  _BYTE v102[32]; // [rsp+A0h] [rbp-78h] BYREF
  _BYTE v103[16]; // [rsp+C0h] [rbp-58h] BYREF
  _BYTE v104[40]; // [rsp+D0h] [rbp-48h] BYREF

  v101[1] = -2;
  v98 = a3;
  v91 = a2;
  v100 = this;
  v92 = 0;
  v101[0] = 0;
  v94 = 0;
  v96 = 0;
  String1 = 0;
  lpDestStr = 0;
  std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(
    v102,
    L"^/([^<>:\"/\\\\|?*\\x01-\\x1F]+)?$");
  v93 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
        CurrentThreadActivityIdPrefix,
        -2147024809);
    }
    NamedAttributeValue = -2147024809;
    goto LABEL_196;
  }
  v7 = (unsigned __int16 **)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"Type");
  NamedAttributeValue = GetNamedAttributeValue(a2, *v7, &String1);
  SysFreeString(bstrString);
  if ( NamedAttributeValue < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        36,
        (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
        v8,
        (__int64)"GetNamedAttributeValue for Resource type failed",
        NamedAttributeValue,
        NamedAttributeValue,
        String1);
    }
    goto LABEL_196;
  }
  for ( i = 0; ; ++i )
  {
    v97 = i;
    if ( i >= 2 )
      break;
    if ( !_wcsicmp(String1, (&off_1800AB7E0)[2 * i]) )
    {
      *((_DWORD *)this + 20) = *((_DWORD *)&off_1800AB7E0 + 4 * i + 2);
      break;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v10 = *((_DWORD *)this + 20);
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids, v11, v10);
  }
  SysFreeString(String1);
  String1 = 0;
  v12 = (unsigned __int16 **)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"Title");
  NamedAttributeValue = GetNamedAttributeValue(v91, *v12, &String1);
  SysFreeString(bstrString);
  if ( NamedAttributeValue < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
        v13,
        (__int64)"GetNamedAttributeValue for Resource type failed",
        NamedAttributeValue,
        NamedAttributeValue);
    }
    goto LABEL_194;
  }
  v14 = String1;
  String1 = 0;
  v15 = (_QWORD *)((char *)this + 48);
  std::wstring::assign((char *)this + 48, v14);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    if ( *((_QWORD *)this + 9) >= 8u )
      v15 = (_QWORD *)*v15;
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
      v16,
      (__int64)v15);
  }
  v17 = (unsigned __int16 **)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"Alias");
  NamedAttributeValue = GetNamedAttributeValue(v91, *v17, &String1);
  SysFreeString(bstrString);
  if ( NamedAttributeValue < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
        v18,
        (__int64)"GetNamedAttributeValue for Resource type failed",
        NamedAttributeValue,
        NamedAttributeValue);
    }
    goto LABEL_194;
  }
  v19 = String1;
  String1 = 0;
  v20 = (_QWORD *)((char *)this + 216);
  std::wstring::assign((char *)this + 216, v19);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    if ( *((_QWORD *)this + 30) >= 8u )
      v20 = (_QWORD *)*v20;
    v21 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
      v21,
      (__int64)v20);
  }
  v22 = (unsigned __int16 **)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"ID");
  NamedAttributeValue = GetNamedAttributeValue(v91, *v22, &String1);
  SysFreeString(bstrString);
  if ( NamedAttributeValue < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v23 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
        v23,
        (__int64)"GetNamedAttributeValue for Resource ID failed",
        NamedAttributeValue,
        NamedAttributeValue);
    }
    goto LABEL_194;
  }
  v24 = String1;
  String1 = 0;
  v25 = (_QWORD *)((char *)this + 248);
  std::wstring::assign((char *)this + 248, v24);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    if ( *((_QWORD *)this + 34) >= 8u )
      v25 = (_QWORD *)*v25;
    v26 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      43,
      (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
      v26,
      (__int64)v25);
  }
  v27 = (unsigned __int16 **)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"ShowByDefault");
  NamedAttributeValue = GetNamedAttributeValue(v91, *v27, &String1);
  SysFreeString(bstrString);
  if ( NamedAttributeValue < 0 )
  {
    if ( NamedAttributeValue != -2147023728 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v28 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          44,
          (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
          v28,
          (__int64)"GetNamedAttributeValue for ShowByDefault failed",
          NamedAttributeValue,
          NamedAttributeValue);
      }
      goto LABEL_194;
    }
    goto LABEL_61;
  }
  if ( !_wcsicmp(String1, L"true") )
  {
LABEL_61:
    *((_DWORD *)this + 86) = 1;
    v29 = 1;
    goto LABEL_63;
  }
  *((_DWORD *)this + 86) = 0;
  v29 = 0;
LABEL_63:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v30 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids, v30, v29);
  }
  NamedAttributeValue = CResource::PopulateIconFiles(this, v91);
  if ( NamedAttributeValue >= 0 )
  {
    if ( v98 )
    {
      selectNodes = v91->lpVtbl->selectNodes;
      v33 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"ns:FileExtensions/ns:FileExtension");
      NamedAttributeValue = ((__int64 (__fastcall *)(struct IXMLDOMNode *, _QWORD, char *))selectNodes)(
                              v91,
                              *v33,
                              (char *)this + 352);
      SysFreeString(bstrString);
      if ( NamedAttributeValue < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v34 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            47,
            (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
            v34,
            (__int64)"selectNodes failed",
            NamedAttributeValue,
            NamedAttributeValue);
        }
        goto LABEL_194;
      }
      NamedAttributeValue = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 44) + 64LL))(
                              *((_QWORD *)this + 44),
                              (char *)this + 360);
      if ( NamedAttributeValue < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v35 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            48,
            (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
            v35,
            (__int64)"IXMLDOMNodeList::get_length failed",
            NamedAttributeValue,
            NamedAttributeValue);
        }
        goto LABEL_194;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v36 = *((_DWORD *)this + 90);
        v37 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids, v37, v36);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v38 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids, v38);
      }
      *((_DWORD *)this + 90) = 0;
    }
    v39 = v91;
    v40 = v91->lpVtbl->selectNodes;
    v41 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"ns:Folders/ns:Folder");
    NamedAttributeValue = ((__int64 (__fastcall *)(struct IXMLDOMNode *, _QWORD, __int64 *))v40)(v39, *v41, &v96);
    SysFreeString(bstrString);
    if ( NamedAttributeValue >= 0 )
    {
      NamedAttributeValue = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v96 + 64LL))(v96, &v93);
      if ( NamedAttributeValue >= 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v44 = v93;
          v45 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids, v45, v44);
        }
        v46 = 0;
        v99 = 0;
        while ( (int)v46 < v93 )
        {
          if ( v94 )
          {
            TCntPtr<ITSThread>::SafeRelease(&v94);
            v94 = 0;
          }
          NamedAttributeValue = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IXMLDOMNode **))(*(_QWORD *)v96 + 56LL))(
                                  v96,
                                  v46,
                                  &v94);
          if ( NamedAttributeValue < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v47 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                54,
                (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
                v47,
                (__int64)"IXMLDOMNodeList::item(Folders) failed",
                NamedAttributeValue,
                NamedAttributeValue);
            }
            goto LABEL_194;
          }
          v48 = (unsigned __int16 **)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"Name");
          NamedAttributeValue = GetNamedAttributeValue(v94, *v48, &String1);
          SysFreeString(bstrString);
          if ( NamedAttributeValue < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v49 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                55,
                (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
                v49,
                (__int64)"GetNamedAttributeValue(Folder:Name) failed",
                NamedAttributeValue,
                NamedAttributeValue);
            }
            goto LABEL_194;
          }
          v50 = String1;
          if ( (unsigned __int8)std::regex_match<unsigned short,std::regex_traits<unsigned short>>(String1, v102) )
          {
            std::wstring::wstring(v104, v50);
            std::set<std::wstring>::insert((char *)v100 + 368, v103, v104);
            LOBYTE(v51) = 1;
            std::wstring::_Tidy(v104, v51, 0);
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v52 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              56,
              (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
              v52,
              (__int64)String1);
          }
          v99 = ++v46;
        }
        v53 = (unsigned __int16 **)ATL::CComBSTR::CComBSTR(
                                     (ATL::CComBSTR *)&bstrString,
                                     L"ns:HostingTerminalServers/ns:HostingTerminalServer/ns:TerminalServerRef");
        NamedAttributeValue = GetIndexedNodeFromXPath(v91, *v53, v54, &v92);
        SysFreeString(bstrString);
        if ( NamedAttributeValue >= 0 )
        {
          v56 = (unsigned __int16 **)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"Ref");
          NamedAttributeValue = GetNamedAttributeValue(v92, *v56, &String1);
          SysFreeString(bstrString);
          if ( NamedAttributeValue >= 0 )
          {
            v58 = String1;
            String1 = 0;
            v59 = v100;
            v60 = (_QWORD *)((char *)v100 + 184);
            std::wstring::assign((char *)v100 + 184, v58);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              if ( v60[3] >= 8u )
                v60 = (_QWORD *)*v60;
              v61 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                59,
                (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
                v61,
                (__int64)v60);
            }
            v62 = v92;
            if ( v92 )
            {
              v92 = 0;
              ((void (__fastcall *)(struct IXMLDOMNode *))v62->lpVtbl->Release)(v62);
            }
            v63 = (unsigned __int16 **)ATL::CComBSTR::CComBSTR(
                                         (ATL::CComBSTR *)&bstrString,
                                         L"ns:HostingTerminalServers/ns:HostingTerminalServer/ns:ResourceFile");
            NamedAttributeValue = GetIndexedNodeFromXPath(v91, *v63, v64, &v92);
            SysFreeString(bstrString);
            if ( NamedAttributeValue >= 0 )
            {
              v66 = (unsigned __int16 **)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"URL");
              NamedAttributeValue = GetNamedAttributeValue(v92, *v66, &String1);
              SysFreeString(bstrString);
              if ( NamedAttributeValue >= 0 )
              {
                v68 = String1;
                String1 = 0;
                v69 = (_QWORD *)((char *)v59 + 120);
                std::wstring::assign((char *)v59 + 120, v68);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                {
                  if ( *((_QWORD *)v59 + 18) >= 8u )
                    v69 = (_QWORD *)*v69;
                  v70 = RdpWppGetCurrentThreadActivityIdPrefix();
                  WPP_SF_DS(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    62,
                    (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
                    v70,
                    (__int64)v69);
                }
                v71 = (unsigned __int16 **)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"FileExtension");
                NamedAttributeValue = GetNamedAttributeValue(v92, *v71, &String1);
                SysFreeString(bstrString);
                if ( NamedAttributeValue >= 0 )
                {
                  v74 = SysStringLen(String1) + 1;
                  v73 = 2 * v74;
                  if ( !is_mul_ok(v74, 2u) )
                    v73 = -1;
                  lpDestStr = (LPWSTR)operator new[](v73, (const struct std::nothrow_t *)&std::nothrow);
                  if ( lpDestStr )
                  {
                    v76 = String1;
                    v77 = SysStringLen(String1);
                    v78 = SysStringLen(v76);
                    if ( LCMapStringW(0x7Fu, 0x100u, v76, v78 + 1, lpDestStr, v77 + 1) )
                    {
                      v83 = v100;
                      v84 = (_QWORD *)((char *)v100 + 152);
                      std::wstring::assign((char *)v100 + 152, lpDestStr);
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                      {
                        if ( v84[3] >= 8u )
                          v84 = (_QWORD *)*v84;
                        v85 = RdpWppGetCurrentThreadActivityIdPrefix();
                        WPP_SF_DS(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          66,
                          (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
                          v85,
                          (__int64)v84);
                      }
                      inited = CResource::InitLaunchDataFromResourceNode(v83, v91);
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                      {
                        v87 = RdpWppGetCurrentThreadActivityIdPrefix();
                        WPP_SF_Dd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          67,
                          &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
                          v87,
                          inited);
                      }
                      NamedAttributeValue = 0;
                    }
                    else
                    {
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        LastError = GetLastError();
                        v80 = LastError;
                        if ( LastError > 0 )
                          v80 = (unsigned __int16)LastError | 0x80070000;
                        v81 = RdpWppGetCurrentThreadActivityIdPrefix();
                        WPP_SF_Dd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          65,
                          &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
                          v81,
                          v80);
                      }
                      v82 = GetLastError();
                      NamedAttributeValue = v82;
                      if ( v82 > 0 )
                        NamedAttributeValue = (unsigned __int16)v82 | 0x80070000;
                    }
                  }
                  else
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v75 = RdpWppGetCurrentThreadActivityIdPrefix();
                      WPP_SF_Dd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        64,
                        &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
                        v75,
                        -2147024882);
                    }
                    NamedAttributeValue = -2147024882;
                  }
                }
                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v72 = RdpWppGetCurrentThreadActivityIdPrefix();
                  WPP_SF_DsD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    63,
                    (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
                    v72,
                    (__int64)"GetNamedAttributeValue for IconRaw::FileURL failed",
                    NamedAttributeValue,
                    NamedAttributeValue);
                }
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v67 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_DsD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  61,
                  (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
                  v67,
                  (__int64)"GetNamedAttributeValue for IconRaw::FileURL failed",
                  NamedAttributeValue,
                  NamedAttributeValue);
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v65 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                60,
                (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
                v65,
                (__int64)"GetIndexedNodeFromXPath failed",
                NamedAttributeValue,
                NamedAttributeValue);
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v57 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              58,
              (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
              v57,
              (__int64)"GetNamedAttributeValue failed",
              NamedAttributeValue,
              NamedAttributeValue);
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v55 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            57,
            (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
            v55,
            (__int64)"GetIndexedNodeFromXPath failed",
            NamedAttributeValue,
            NamedAttributeValue);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v43 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52,
          (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
          v43,
          (__int64)"IXMLDOMNodeList::get_length(Folders) failed",
          NamedAttributeValue,
          NamedAttributeValue);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v42 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        51,
        (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
        v42,
        (__int64)"selectNodes(Folders) failed",
        NamedAttributeValue,
        NamedAttributeValue);
    }
    goto LABEL_194;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v31 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      46,
      (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
      v31,
      (__int64)"PopulateIconFiles failed",
      NamedAttributeValue,
      NamedAttributeValue);
  }
LABEL_194:
  if ( lpDestStr )
    operator delete[](lpDestStr);
LABEL_196:
  std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v102);
  SysFreeString(String1);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v96);
  ComPlainSmartPtr<IRADCWorkspaceManager>::~ComPlainSmartPtr<IRADCWorkspaceManager>(&v94);
  ComPlainSmartPtr<IRADCWorkspaceManager>::~ComPlainSmartPtr<IRADCWorkspaceManager>(v101);
  ComPlainSmartPtr<IRADCWorkspaceManager>::~ComPlainSmartPtr<IRADCWorkspaceManager>(&v92);
  return (unsigned int)NamedAttributeValue;
}

```

## disassembly

```asm
0x180065f98  mov     r11, rsp
0x180065f9b  push    rdi
0x180065f9c  push    r14
0x180065f9e  push    r15
0x180065fa0  sub     rsp, 100h
0x180065fa7  mov     qword ptr [r11-80h], 0FFFFFFFFFFFFFFFEh
0x180065faf  mov     [r11+18h], rbx
0x180065fb3  mov     [r11+20h], rsi
0x180065fb7  mov     rax, cs:__security_cookie
0x180065fbe  xor     rax, rsp
0x180065fc1  mov     [rsp+118h+var_20], rax
0x180065fc9  mov     [rsp+118h+var_9C], r8d
0x180065fce  mov     rbx, rdx
0x180065fd1  mov     [rsp+118h+var_D0], rdx
0x180065fd6  mov     rdi, rcx
0x180065fd9  mov     [rsp+118h+var_90], rcx
0x180065fe1  xor     r14d, r14d
0x180065fe4  mov     [rsp+118h+var_C8], r14
0x180065fe9  mov     [r11-88h], r14
0x180065ff0  mov     [rsp+118h+var_B8], r14
0x180065ff5  mov     [rsp+118h+var_A8], r14
0x180065ffa  mov     [rsp+118h+String1], r14
0x180065fff  mov     [rsp+118h+var_B0], r14
0x180066004  lea     rdx, aX01X1f; "^/([^<>:\"/\\\\|?*\\x01-\\x1F]+)?$"
0x18006600b  lea     rcx, [r11-78h]
0x18006600f  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@PEBGW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(ushort const *,std::regex_constants::syntax_option_type)
0x180066014  nop
0x180066015  mov     [rsp+118h+var_C0], r14d
0x18006601a  test    rbx, rbx
0x18006601d  jnz     short loc_180066076
0x18006601f  lea     rsi, WPP_GLOBAL_Control
0x180066026  mov     rax, cs:WPP_GLOBAL_Control
0x18006602d  cmp     rax, rsi
0x180066030  jz      short loc_180066068
0x180066032  test    byte ptr [rax+1Ch], 8
0x180066036  jz      short loc_180066068
0x180066038  cmp     byte ptr [rax+19h], 2
0x18006603c  jb      short loc_180066068
0x18006603e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180066043  lea     edx, [rbx+23h]
0x180066046  mov     dword ptr [rsp+118h+lpDestStr], 80070057h
0x18006604e  mov     r9d, eax
0x180066051  lea     r8, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x180066058  mov     rcx, cs:WPP_GLOBAL_Control
0x18006605f  mov     rcx, [rcx+10h]
0x180066063  call    WPP_SF_Dd
0x180066068  mov     ebx, 80070057h
0x18006606d  mov     [rsp+118h+var_E8], ebx
0x180066071  jmp     loc_180066FFD
0x180066076  lea     rdx, aType; "Type"
0x18006607d  lea     rcx, [rsp+118h+bstrString]; this
0x180066082  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180066087  nop
0x180066088  lea     r8, [rsp+118h+String1]; unsigned __int16 **
0x18006608d  mov     rdx, [rax]; unsigned __int16 *
0x180066090  mov     rcx, rbx; struct IXMLDOMNode *
0x180066093  call    ?GetNamedAttributeValue@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z; GetNamedAttributeValue(IXMLDOMNode *,ushort *,ushort * *)
0x180066098  mov     ebx, eax
0x18006609a  mov     [rsp+118h+var_E8], eax
0x18006609e  mov     rcx, [rsp+118h+bstrString]; bstrString
0x1800660a3  call    cs:__imp_SysFreeString
0x1800660a9  test    ebx, ebx
0x1800660ab  jns     short loc_180066106
0x1800660ad  lea     rsi, WPP_GLOBAL_Control
0x1800660b4  mov     rax, cs:WPP_GLOBAL_Control
0x1800660bb  cmp     rax, rsi
0x1800660be  jz      short loc_180066101
0x1800660c0  test    byte ptr [rax+1Ch], 8
0x1800660c4  jz      short loc_180066101
0x1800660c6  cmp     byte ptr [rax+19h], 2
0x1800660ca  jb      short loc_180066101
0x1800660cc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800660d1  mov     edx, 24h ; '$'
0x1800660d6  mov     [rsp+118h+cchDest], ebx
0x1800660da  lea     rcx, aGetnamedattrib; "GetNamedAttributeValue for Resource typ"...
0x1800660e1  mov     [rsp+118h+lpDestStr], rcx
0x1800660e6  mov     r9d, eax
0x1800660e9  lea     r8, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x1800660f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800660f7  mov     rcx, [rcx+10h]
0x1800660fb  call    WPP_SF_DsD
0x180066100  nop
0x180066101  jmp     loc_180066FFD
0x180066106  mov     ebx, r14d
0x180066109  lea     r15, off_1800AB7E0; "RemoteApp"
0x180066110  mov     [rsp+118h+var_A0], ebx
0x180066114  cmp     ebx, 2
0x180066117  jnb     short loc_180066139
0x180066119  mov     esi, ebx
0x18006611b  add     rsi, rsi
0x18006611e  mov     rdx, [r15+rsi*8]; String2
0x180066122  mov     rcx, [rsp+118h+String1]; String1
0x180066127  call    cs:__imp__wcsicmp
0x18006612d  test    eax, eax
0x18006612f  jnz     short loc_180066188
0x180066131  mov     eax, [r15+rsi*8+8]
0x180066136  mov     [rdi+50h], eax
0x180066139  lea     rsi, WPP_GLOBAL_Control
0x180066140  mov     rax, cs:WPP_GLOBAL_Control
0x180066147  cmp     rax, rsi
0x18006614a  jz      short loc_18006618C
0x18006614c  test    byte ptr [rax+1Ch], 1
0x180066150  jz      short loc_18006618C
0x180066152  cmp     byte ptr [rax+19h], 4
0x180066156  jb      short loc_18006618C
0x180066158  mov     ebx, [rdi+50h]
0x18006615b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180066160  mov     edx, 25h ; '%'
0x180066165  mov     dword ptr [rsp+118h+lpDestStr], ebx
0x180066169  mov     r9d, eax
0x18006616c  lea     r15, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x180066173  mov     r8, r15
0x180066176  mov     rcx, cs:WPP_GLOBAL_Control
0x18006617d  mov     rcx, [rcx+10h]
0x180066181  call    WPP_SF_Dd
0x180066186  jmp     short loc_180066193
0x180066188  inc     ebx
0x18006618a  jmp     short loc_180066110
0x18006618c  lea     r15, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x180066193  mov     rcx, [rsp+118h+String1]; bstrString
0x180066198  call    cs:__imp_SysFreeString
0x18006619e  mov     [rsp+118h+String1], r14
0x1800661a3  lea     rdx, aTitle; "Title"
0x1800661aa  lea     rcx, [rsp+118h+bstrString]; this
0x1800661af  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800661b4  nop
0x1800661b5  lea     r8, [rsp+118h+String1]; unsigned __int16 **
0x1800661ba  mov     rdx, [rax]; unsigned __int16 *
0x1800661bd  mov     rcx, [rsp+118h+var_D0]; struct IXMLDOMNode *
0x1800661c2  call    ?GetNamedAttributeValue@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z; GetNamedAttributeValue(IXMLDOMNode *,ushort *,ushort * *)
0x1800661c7  mov     ebx, eax
0x1800661c9  mov     [rsp+118h+var_E8], eax
0x1800661cd  mov     rcx, [rsp+118h+bstrString]; bstrString
0x1800661d2  call    cs:__imp_SysFreeString
0x1800661d8  test    ebx, ebx
0x1800661da  jns     short loc_18006622A
0x1800661dc  mov     rax, cs:WPP_GLOBAL_Control
0x1800661e3  cmp     rax, rsi
0x1800661e6  jz      short loc_180066225
0x1800661e8  test    byte ptr [rax+1Ch], 8
0x1800661ec  jz      short loc_180066225
0x1800661ee  cmp     byte ptr [rax+19h], 2
0x1800661f2  jb      short loc_180066225
0x1800661f4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800661f9  mov     edx, 26h ; '&'
0x1800661fe  mov     [rsp+118h+cchDest], ebx
0x180066202  lea     rcx, aGetnamedattrib; "GetNamedAttributeValue for Resource typ"...
0x180066209  mov     [rsp+118h+lpDestStr], rcx
0x18006620e  mov     r9d, eax
0x180066211  mov     r8, r15
0x180066214  mov     rcx, cs:WPP_GLOBAL_Control
0x18006621b  mov     rcx, [rcx+10h]
0x18006621f  call    WPP_SF_DsD
0x180066224  nop
0x180066225  jmp     loc_180066FE9
0x18006622a  mov     rdx, [rsp+118h+String1]
0x18006622f  mov     [rsp+118h+String1], r14
0x180066234  lea     rbx, [rdi+30h]
0x180066238  mov     rcx, rbx
0x18006623b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180066240  mov     rax, cs:WPP_GLOBAL_Control
0x180066247  cmp     rax, rsi
0x18006624a  jz      short loc_180066287
0x18006624c  test    byte ptr [rax+1Ch], 1
0x180066250  jz      short loc_180066287
0x180066252  cmp     byte ptr [rax+19h], 4
0x180066256  jb      short loc_180066287
0x180066258  cmp     qword ptr [rbx+18h], 8
0x18006625d  jb      short loc_180066262
0x18006625f  mov     rbx, [rbx]
0x180066262  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180066267  mov     edx, 27h ; '''
0x18006626c  mov     [rsp+118h+lpDestStr], rbx
0x180066271  mov     r9d, eax
0x180066274  mov     r8, r15
0x180066277  mov     rcx, cs:WPP_GLOBAL_Control
0x18006627e  mov     rcx, [rcx+10h]
0x180066282  call    WPP_SF_DS
0x180066287  lea     rdx, aAlias; "Alias"
0x18006628e  lea     rcx, [rsp+118h+bstrString]; this
0x180066293  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180066298  nop
0x180066299  lea     r8, [rsp+118h+String1]; unsigned __int16 **
0x18006629e  mov     rdx, [rax]; unsigned __int16 *
0x1800662a1  mov     rcx, [rsp+118h+var_D0]; struct IXMLDOMNode *
0x1800662a6  call    ?GetNamedAttributeValue@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z; GetNamedAttributeValue(IXMLDOMNode *,ushort *,ushort * *)
0x1800662ab  mov     ebx, eax
0x1800662ad  mov     [rsp+118h+var_E8], eax
0x1800662b1  mov     rcx, [rsp+118h+bstrString]; bstrString
0x1800662b6  call    cs:__imp_SysFreeString
0x1800662bc  test    ebx, ebx
0x1800662be  jns     short loc_18006630E
0x1800662c0  mov     rax, cs:WPP_GLOBAL_Control
0x1800662c7  cmp     rax, rsi
0x1800662ca  jz      short loc_180066309
0x1800662cc  test    byte ptr [rax+1Ch], 8
0x1800662d0  jz      short loc_180066309
0x1800662d2  cmp     byte ptr [rax+19h], 2
0x1800662d6  jb      short loc_180066309
0x1800662d8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800662dd  mov     edx, 28h ; '('
0x1800662e2  mov     [rsp+118h+cchDest], ebx
0x1800662e6  lea     rcx, aGetnamedattrib; "GetNamedAttributeValue for Resource typ"...
0x1800662ed  mov     [rsp+118h+lpDestStr], rcx
0x1800662f2  mov     r9d, eax
0x1800662f5  mov     r8, r15
0x1800662f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800662ff  mov     rcx, [rcx+10h]
0x180066303  call    WPP_SF_DsD
0x180066308  nop
0x180066309  jmp     loc_180066FE9
0x18006630e  mov     rdx, [rsp+118h+String1]
0x180066313  mov     [rsp+118h+String1], r14
0x180066318  lea     rbx, [rdi+0D8h]
0x18006631f  mov     rcx, rbx
0x180066322  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180066327  mov     rax, cs:WPP_GLOBAL_Control
0x18006632e  cmp     rax, rsi
0x180066331  jz      short loc_18006636E
0x180066333  test    byte ptr [rax+1Ch], 1
0x180066337  jz      short loc_18006636E
0x180066339  cmp     byte ptr [rax+19h], 4
0x18006633d  jb      short loc_18006636E
0x18006633f  cmp     qword ptr [rbx+18h], 8
0x180066344  jb      short loc_180066349
0x180066346  mov     rbx, [rbx]
0x180066349  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18006634e  mov     edx, 29h ; ')'
0x180066353  mov     [rsp+118h+lpDestStr], rbx
0x180066358  mov     r9d, eax
0x18006635b  mov     r8, r15
0x18006635e  mov     rcx, cs:WPP_GLOBAL_Control
0x180066365  mov     rcx, [rcx+10h]
0x180066369  call    WPP_SF_DS
0x18006636e  lea     rdx, aId_0; "ID"
0x180066375  lea     rcx, [rsp+118h+bstrString]; this
0x18006637a  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18006637f  nop
0x180066380  lea     r8, [rsp+118h+String1]; unsigned __int16 **
0x180066385  mov     rdx, [rax]; unsigned __int16 *
0x180066388  mov     rcx, [rsp+118h+var_D0]; struct IXMLDOMNode *
0x18006638d  call    ?GetNamedAttributeValue@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z; GetNamedAttributeValue(IXMLDOMNode *,ushort *,ushort * *)
0x180066392  mov     ebx, eax
0x180066394  mov     [rsp+118h+var_E8], eax
0x180066398  mov     rcx, [rsp+118h+bstrString]; bstrString
0x18006639d  call    cs:__imp_SysFreeString
0x1800663a3  test    ebx, ebx
0x1800663a5  jns     short loc_1800663F5
0x1800663a7  mov     rax, cs:WPP_GLOBAL_Control
0x1800663ae  cmp     rax, rsi
0x1800663b1  jz      short loc_1800663F0
0x1800663b3  test    byte ptr [rax+1Ch], 8
0x1800663b7  jz      short loc_1800663F0
0x1800663b9  cmp     byte ptr [rax+19h], 2
0x1800663bd  jb      short loc_1800663F0
0x1800663bf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800663c4  mov     edx, 2Ah ; '*'
0x1800663c9  mov     [rsp+118h+cchDest], ebx
0x1800663cd  lea     rcx, aGetnamedattrib_3; "GetNamedAttributeValue for Resource ID "...
0x1800663d4  mov     [rsp+118h+lpDestStr], rcx
0x1800663d9  mov     r9d, eax
0x1800663dc  mov     r8, r15
0x1800663df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800663e6  mov     rcx, [rcx+10h]
0x1800663ea  call    WPP_SF_DsD
0x1800663ef  nop
0x1800663f0  jmp     loc_180066FE9
0x1800663f5  mov     rdx, [rsp+118h+String1]
0x1800663fa  mov     [rsp+118h+String1], r14
0x1800663ff  lea     rbx, [rdi+0F8h]
0x180066406  mov     rcx, rbx
0x180066409  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18006640e  mov     rax, cs:WPP_GLOBAL_Control
0x180066415  cmp     rax, rsi
0x180066418  jz      short loc_180066455
0x18006641a  test    byte ptr [rax+1Ch], 1
0x18006641e  jz      short loc_180066455
0x180066420  cmp     byte ptr [rax+19h], 4
0x180066424  jb      short loc_180066455
0x180066426  cmp     qword ptr [rbx+18h], 8
0x18006642b  jb      short loc_180066430
0x18006642d  mov     rbx, [rbx]
0x180066430  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180066435  mov     edx, 2Bh ; '+'
0x18006643a  mov     [rsp+118h+lpDestStr], rbx
0x18006643f  mov     r9d, eax
0x180066442  mov     r8, r15
0x180066445  mov     rcx, cs:WPP_GLOBAL_Control
0x18006644c  mov     rcx, [rcx+10h]
0x180066450  call    WPP_SF_DS
0x180066455  lea     rdx, aShowbydefault; "ShowByDefault"
0x18006645c  lea     rcx, [rsp+118h+bstrString]; this
0x180066461  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180066466  nop
0x180066467  lea     r8, [rsp+118h+String1]; unsigned __int16 **
0x18006646c  mov     rdx, [rax]; unsigned __int16 *
0x18006646f  mov     rcx, [rsp+118h+var_D0]; struct IXMLDOMNode *
0x180066474  call    ?GetNamedAttributeValue@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z; GetNamedAttributeValue(IXMLDOMNode *,ushort *,ushort * *)
0x180066479  mov     ebx, eax
0x18006647b  mov     [rsp+118h+var_E8], eax
  ... truncated ...
```
