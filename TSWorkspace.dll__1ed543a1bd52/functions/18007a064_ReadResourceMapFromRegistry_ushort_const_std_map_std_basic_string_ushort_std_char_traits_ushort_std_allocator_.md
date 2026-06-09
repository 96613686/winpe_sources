# ReadResourceMapFromRegistry(ushort const *,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ResourceMapNode,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ResourceMapNode>>> &)

- ea: `0x18007a064`
- end: `0x18007ab37`
- name: `?ReadResourceMapFromRegistry@@YAJPEBGAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceMapNode@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceMapNode@@@std@@@2@@std@@@Z`
- size: `2771`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180031e20`

## callees

- `0x180004970`
- `0x1800055d0`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000dbdc`
- `0x18000ec94`
- `0x18000ece0`
- `0x18001e610`
- `0x18001ead4`
- `0x180020964`
- `0x180020a68`
- `0x180020bf0`
- `0x18002774c`
- `0x180027dc0`
- `0x180028378`
- `0x180028860`
- `0x1800289f0`
- `0x18003aee0`
- `0x18003afdc`
- `0x18003c9a4`
- `0x180077160`
- `0x180079dbc`
- `0x180079eb4`
- `0x18007a064`
- `0x18007ab40`
- `0x18009a520`
- `0x18009a5e0`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x18007a43b`
- `ADVAPI32!RegGetValueW` at `0x18007a4e5`
- `ADVAPI32!RegGetValueW` at `0x18007a5a4`
- `ADVAPI32!RegGetValueW` at `0x18007a663`
- `ADVAPI32!RegGetValueW` at `0x18007a726`
- `ADVAPI32!RegGetValueW` at `0x18007a7e8`
- `ADVAPI32!RegGetValueW` at `0x18007a915`
- `ADVAPI32!RegGetValueW` at `0x18007a43b`
- `ADVAPI32!RegGetValueW` at `0x18007a4e5`
- `ADVAPI32!RegGetValueW` at `0x18007a5a4`
- `ADVAPI32!RegGetValueW` at `0x18007a663`
- `ADVAPI32!RegGetValueW` at `0x18007a726`
- `ADVAPI32!RegGetValueW` at `0x18007a7e8`
- `ADVAPI32!RegGetValueW` at `0x18007a915`
- `ADVAPI32!RegCloseKey` at `0x18007aacd`
- `ADVAPI32!RegCloseKey` at `0x18007aacd`
- `ADVAPI32!RegEnumKeyExW` at `0x18007a378`
- `ADVAPI32!RegEnumKeyExW` at `0x18007a378`
- `ADVAPI32!RegOpenKeyExW` at `0x18007a29a`
- `ADVAPI32!RegOpenKeyExW` at `0x18007a29a`

## string_xrefs

- `0x18007a1a4`: `SSPInstalledApps`
- `0x18007a20c`: `ReadSSPAppMapFromRegistry failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall ReadResourceMapFromRegistry(const WCHAR *a1, __int64 a2)
{
  int WorkspaceSSPInfo; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  const WCHAR *v6; // rax
  unsigned int v7; // eax
  const WCHAR *v8; // rax
  unsigned int v9; // esi
  unsigned int v10; // eax
  int v11; // r12d
  DWORD v12; // r13d
  LSTATUS v13; // eax
  unsigned int v14; // ebx
  unsigned int v15; // eax
  unsigned int v16; // esi
  unsigned int v17; // eax
  unsigned int v18; // esi
  unsigned int v19; // eax
  unsigned int v20; // esi
  unsigned int v21; // eax
  LSTATUS ValueW; // eax
  unsigned int v23; // esi
  unsigned int v24; // eax
  unsigned int v25; // esi
  unsigned int v26; // eax
  unsigned int v27; // esi
  unsigned int v28; // eax
  unsigned int v29; // eax
  LSTATUS v30; // eax
  int v31; // eax
  unsigned int v32; // esi
  unsigned int v33; // eax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // r8
  char v37; // bl
  unsigned int v38; // eax
  __int64 v39; // rax
  LPWSTR lpClass; // [rsp+28h] [rbp-2BD0h]
  DWORD pcbData; // [rsp+40h] [rbp-2BB8h] BYREF
  int v43; // [rsp+44h] [rbp-2BB4h]
  HKEY hKey; // [rsp+48h] [rbp-2BB0h] BYREF
  int v45; // [rsp+50h] [rbp-2BA8h] BYREF
  DWORD cchName; // [rsp+54h] [rbp-2BA4h] BYREF
  DWORD i; // [rsp+58h] [rbp-2BA0h]
  _BYTE v48[16]; // [rsp+60h] [rbp-2B98h] BYREF
  __int64 v49; // [rsp+70h] [rbp-2B88h]
  __int64 v50; // [rsp+78h] [rbp-2B80h]
  _BYTE v51[8]; // [rsp+80h] [rbp-2B78h] BYREF
  _BYTE v52[8]; // [rsp+88h] [rbp-2B70h] BYREF
  _BYTE v53[32]; // [rsp+90h] [rbp-2B68h] BYREF
  _BYTE v54[32]; // [rsp+B0h] [rbp-2B48h] BYREF
  _BYTE pvData[4]; // [rsp+D0h] [rbp-2B28h] BYREF
  int v56; // [rsp+D4h] [rbp-2B24h] BYREF
  BOOL v57; // [rsp+D8h] [rbp-2B20h]
  _BYTE v58[32]; // [rsp+E0h] [rbp-2B18h] BYREF
  _BYTE v59[32]; // [rsp+100h] [rbp-2AF8h] BYREF
  _BYTE v60[32]; // [rsp+120h] [rbp-2AD8h] BYREF
  _BYTE v61[32]; // [rsp+140h] [rbp-2AB8h] BYREF
  _BYTE v62[16]; // [rsp+160h] [rbp-2A98h] BYREF
  _BYTE v63[32]; // [rsp+170h] [rbp-2A88h] BYREF
  _BYTE v64[32]; // [rsp+190h] [rbp-2A68h] BYREF
  WCHAR Name[256]; // [rsp+1B0h] [rbp-2A48h] BYREF
  _BYTE v66[10264]; // [rsp+3B0h] [rbp-2848h] BYREF

  v50 = -2;
  v49 = a2;
  hKey = 0;
  cchName = 256;
  ResourceMapNode::ResourceMapNode((ResourceMapNode *)pvData);
  pcbData = 0;
  std::wstring::wstring(v54);
  std::wstring::wstring(v53);
  std::map<std::wstring,bool,KeyCompareLessIgnoreCase,std::allocator<std::pair<std::wstring const,bool>>>::map<std::wstring,bool,KeyCompareLessIgnoreCase,std::allocator<std::pair<std::wstring const,bool>>>(v48);
  v45 = 0;
  std::_Tree<std::_Tmap_traits<std::wstring,ResourceMapNode,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ResourceMapNode>>,0>>::clear(a2);
  WorkspaceSSPInfo = GetWorkspaceSSPInfo(a1, &v45);
  v43 = WorkspaceSSPInfo;
  if ( WorkspaceSSPInfo < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_9a9b29d69df23d7c330004de722d1721_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"GetWorkspaceSSPInfo failed",
        WorkspaceSSPInfo);
    }
    goto LABEL_134;
  }
  if ( v45 )
  {
    std::wstring::assign(v53, a1);
    std::wstring::append(v53, L"\\");
    std::wstring::append(v53, L"SSPInstalledApps");
    v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v53);
    WorkspaceSSPInfo = ReadSSPAppMapFromRegistry(v6);
    v43 = WorkspaceSSPInfo;
    if ( WorkspaceSSPInfo < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)WPP_9a9b29d69df23d7c330004de722d1721_Traceguids,
          v7,
          (__int64)"ReadSSPAppMapFromRegistry failed",
          WorkspaceSSPInfo);
      }
      goto LABEL_134;
    }
  }
  std::wstring::assign(v54, a1);
  std::wstring::append(v54, L"\\");
  std::wstring::append(v54, L"ResourceMap");
  v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v54);
  WorkspaceSSPInfo = RegOpenKeyExW(HKEY_CURRENT_USER, v8, 0, 0x20019u, &hKey);
  if ( WorkspaceSSPInfo )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( WorkspaceSSPInfo > 0 )
        v9 = (unsigned __int16)WorkspaceSSPInfo | 0x80070000;
      else
        v9 = WorkspaceSSPInfo;
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_9a9b29d69df23d7c330004de722d1721_Traceguids, v10, v9);
    }
    if ( WorkspaceSSPInfo > 0 )
      WorkspaceSSPInfo = (unsigned __int16)WorkspaceSSPInfo | 0x80070000;
    v43 = WorkspaceSSPInfo;
    goto LABEL_134;
  }
  v11 = 0;
  v12 = 0;
  for ( i = 0; ; i = v12 )
  {
    if ( v11 == 259 )
    {
      WorkspaceSSPInfo = 0;
      goto LABEL_134;
    }
    cchName = 256;
    v13 = RegEnumKeyExW(hKey, v12, Name, &cchName, 0, 0, 0, 0);
    v11 = v13;
    if ( !v13 )
      break;
    if ( v13 != 259 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( v13 > 0 )
          v14 = (unsigned __int16)v13 | 0x80070000;
        else
          v14 = v13;
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_9a9b29d69df23d7c330004de722d1721_Traceguids, v15, v14);
      }
      if ( v11 > 0 )
        WorkspaceSSPInfo = (unsigned __int16)v11 | 0x80070000;
      else
        WorkspaceSSPInfo = v11;
      v43 = WorkspaceSSPInfo;
      goto LABEL_134;
    }
LABEL_133:
    ++v12;
  }
  pcbData = 4;
  WorkspaceSSPInfo = RegGetValueW(hKey, Name, L"IsRDP", 0x10u, 0, pvData, &pcbData);
  if ( WorkspaceSSPInfo )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( WorkspaceSSPInfo > 0 )
        v16 = (unsigned __int16)WorkspaceSSPInfo | 0x80070000;
      else
        v16 = WorkspaceSSPInfo;
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_9a9b29d69df23d7c330004de722d1721_Traceguids, v17, v16);
    }
    if ( WorkspaceSSPInfo > 0 )
      WorkspaceSSPInfo = (unsigned __int16)WorkspaceSSPInfo | 0x80070000;
    v43 = WorkspaceSSPInfo;
    goto LABEL_134;
  }
  pcbData = 10242;
  WorkspaceSSPInfo = RegGetValueW(hKey, Name, L"ResourceFileExt", 2u, 0, v66, &pcbData);
  if ( WorkspaceSSPInfo )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( WorkspaceSSPInfo > 0 )
        v18 = (unsigned __int16)WorkspaceSSPInfo | 0x80070000;
      else
        v18 = WorkspaceSSPInfo;
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_9a9b29d69df23d7c330004de722d1721_Traceguids, v19, v18);
    }
    if ( WorkspaceSSPInfo > 0 )
      WorkspaceSSPInfo = (unsigned __int16)WorkspaceSSPInfo | 0x80070000;
    v43 = WorkspaceSSPInfo;
    goto LABEL_134;
  }
  std::wstring::assign(v58, v66);
  pcbData = 10242;
  WorkspaceSSPInfo = RegGetValueW(hKey, Name, L"ResourceFile", 2u, 0, v66, &pcbData);
  if ( WorkspaceSSPInfo )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( WorkspaceSSPInfo > 0 )
        v20 = (unsigned __int16)WorkspaceSSPInfo | 0x80070000;
      else
        v20 = WorkspaceSSPInfo;
      v21 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_9a9b29d69df23d7c330004de722d1721_Traceguids, v21, v20);
    }
    if ( WorkspaceSSPInfo > 0 )
      WorkspaceSSPInfo = (unsigned __int16)WorkspaceSSPInfo | 0x80070000;
    v43 = WorkspaceSSPInfo;
    goto LABEL_134;
  }
  std::wstring::assign(v59, v66);
  pcbData = 10242;
  ValueW = RegGetValueW(hKey, Name, L"Alias", 2u, 0, v66, &pcbData);
  WorkspaceSSPInfo = ValueW;
  if ( ValueW )
  {
    if ( ValueW != 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( ValueW > 0 )
          v23 = (unsigned __int16)ValueW | 0x80070000;
        else
          v23 = ValueW;
        v24 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_9a9b29d69df23d7c330004de722d1721_Traceguids, v24, v23);
      }
      if ( WorkspaceSSPInfo > 0 )
        WorkspaceSSPInfo = (unsigned __int16)WorkspaceSSPInfo | 0x80070000;
      v43 = WorkspaceSSPInfo;
      goto LABEL_134;
    }
  }
  else
  {
    std::wstring::assign(v61, v66);
  }
  pcbData = 10242;
  WorkspaceSSPInfo = RegGetValueW(hKey, Name, L"IconFile", 2u, 0, v66, &pcbData);
  if ( WorkspaceSSPInfo )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( WorkspaceSSPInfo > 0 )
        v25 = (unsigned __int16)WorkspaceSSPInfo | 0x80070000;
      else
        v25 = WorkspaceSSPInfo;
      v26 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_9a9b29d69df23d7c330004de722d1721_Traceguids, v26, v25);
    }
    if ( WorkspaceSSPInfo > 0 )
      WorkspaceSSPInfo = (unsigned __int16)WorkspaceSSPInfo | 0x80070000;
    v43 = WorkspaceSSPInfo;
    goto LABEL_134;
  }
  std::wstring::assign(v60, v66);
  pcbData = 10242;
  WorkspaceSSPInfo = RegGetValueW(hKey, Name, L"Folders", 0x20u, 0, v66, &pcbData);
  if ( WorkspaceSSPInfo )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( WorkspaceSSPInfo > 0 )
        v27 = (unsigned __int16)WorkspaceSSPInfo | 0x80070000;
      else
        v27 = WorkspaceSSPInfo;
      v28 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_9a9b29d69df23d7c330004de722d1721_Traceguids, v28, v27);
    }
    if ( WorkspaceSSPInfo > 0 )
      WorkspaceSSPInfo = (unsigned __int16)WorkspaceSSPInfo | 0x80070000;
    v43 = WorkspaceSSPInfo;
    goto LABEL_134;
  }
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::clear(v62);
  WorkspaceSSPInfo = MultiSzToStrings<std::set<std::wstring>>(v66, pcbData >> 1, v62);
  v43 = WorkspaceSSPInfo;
  if ( WorkspaceSSPInfo < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v29 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(lpClass) = WorkspaceSSPInfo;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)WPP_9a9b29d69df23d7c330004de722d1721_Traceguids,
        v29,
        (__int64)"MultiSzToStrings failed",
        lpClass);
    }
    goto LABEL_134;
  }
  pcbData = 4;
  v30 = RegGetValueW(hKey, Name, L"ShowByDefault", 0x10u, 0, &v56, &pcbData);
  WorkspaceSSPInfo = v30;
  if ( !v30 )
  {
    v31 = v56;
    goto LABEL_125;
  }
  if ( v30 == 2 )
  {
    v31 = 1;
    v56 = 1;
LABEL_125:
    if ( v45 )
    {
      v34 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v61);
      std::wstring::wstring(v63, v34);
      std::_Tree<std::_Tmap_traits<std::wstring,bool,KeyCompareLessIgnoreCase,std::allocator<std::pair<std::wstring const,bool>>,0>>::find(
        v48,
        v51,
        v63);
      v35 = std::vector<unsigned int>::begin(v48, v52);
      v37 = std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,bool>>>>::operator!=(
              v36,
              v35);
      std::wstring::~wstring(v63);
      v57 = v37 != 0;
    }
    else
    {
      v57 = v31;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v38 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        (unsigned int)WPP_9a9b29d69df23d7c330004de722d1721_Traceguids,
        v38,
        (__int64)Name);
    }
    std::wstring::wstring(v64, Name);
    v39 = std::map<std::wstring,ResourceMapNode>::operator[](v49, v64);
    ResourceMapNode::operator=(v39, pvData);
    std::wstring::~wstring(v64);
    goto LABEL_133;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    if ( v30 > 0 )
      v32 = (unsigned __int16)v30 | 0x80070000;
    else
      v32 = v30;
    v33 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_9a9b29d69df23d7c330004de722d1721_Traceguids, v33, v32);
  }
  if ( WorkspaceSSPInfo > 0 )
    WorkspaceSSPInfo = (unsigned __int16)WorkspaceSSPInfo | 0x80070000;
  v43 = WorkspaceSSPInfo;
LABEL_134:
  if ( hKey )
    RegCloseKey(hKey);
  std::map<std::wstring,bool,KeyCompareLessIgnoreCase,std::allocator<std::pair<std::wstring const,bool>>>::~map<std::wstring,bool,KeyCompareLessIgnoreCase,std::allocator<std::pair<std::wstring const,bool>>>(v48);
  std::wstring::~wstring(v53);
  std::wstring::~wstring(v54);
  ResourceMapNode::~ResourceMapNode((ResourceMapNode *)pvData);
  return (unsigned int)WorkspaceSSPInfo;
}

```

## disassembly

```asm
0x18007a064  push    rdi
0x18007a066  push    r12
0x18007a068  push    r13
0x18007a06a  push    r14
0x18007a06c  push    r15
0x18007a06e  mov     eax, 2BD0h
0x18007a073  call    _alloca_probe
0x18007a078  sub     rsp, rax
0x18007a07b  mov     [rsp+2BF8h+var_2B80], 0FFFFFFFFFFFFFFFEh
0x18007a084  mov     [rsp+2BF8h+arg_10], rbx
0x18007a08c  mov     [rsp+2BF8h+arg_18], rsi
0x18007a094  mov     rax, cs:__security_cookie
0x18007a09b  xor     rax, rsp
0x18007a09e  mov     [rsp+2BF8h+var_30], rax
0x18007a0a6  mov     rbx, rdx
0x18007a0a9  mov     [rsp+2BF8h+var_2B88], rdx
0x18007a0ae  mov     rsi, rcx
0x18007a0b1  xor     edi, edi
0x18007a0b3  mov     [rsp+2BF8h+hKey], rdi
0x18007a0b8  mov     [rsp+2BF8h+cchName], 100h
0x18007a0c0  lea     rcx, [rsp+2BF8h+pvData]; this
0x18007a0c8  call    ??0ResourceMapNode@@QEAA@XZ; ResourceMapNode::ResourceMapNode(void)
0x18007a0cd  nop
0x18007a0ce  mov     [rsp+2BF8h+pcbData], edi
0x18007a0d2  lea     rcx, [rsp+2BF8h+var_2B48]
0x18007a0da  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18007a0df  nop
0x18007a0e0  lea     rcx, [rsp+2BF8h+var_2B68]
0x18007a0e8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18007a0ed  nop
0x18007a0ee  lea     rcx, [rsp+2BF8h+var_2B98]
0x18007a0f3  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NUKeyCompareLessIgnoreCase@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,bool,KeyCompareLessIgnoreCase,std::allocator<std::pair<std::wstring const,bool>>>::map<std::wstring,bool,KeyCompareLessIgnoreCase,std::allocator<std::pair<std::wstring const,bool>>>(void)
0x18007a0f8  nop
0x18007a0f9  mov     [rsp+2BF8h+var_2BA8], edi
0x18007a0fd  mov     rcx, rbx
0x18007a100  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceMapNode@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceMapNode@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,ResourceMapNode,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ResourceMapNode>>,0>>::clear(void)
0x18007a105  lea     rdx, [rsp+2BF8h+var_2BA8]; pvData
0x18007a10a  mov     rcx, rsi; lpSubKey
0x18007a10d  call    ?GetWorkspaceSSPInfo@@YAJPEBGAEAH@Z; GetWorkspaceSSPInfo(ushort const *,int &)
0x18007a112  mov     ebx, eax
0x18007a114  mov     [rsp+2BF8h+var_2BB4], eax
0x18007a118  test    eax, eax
0x18007a11a  jns     short loc_18007A176
0x18007a11c  lea     r14, WPP_GLOBAL_Control
0x18007a123  mov     rax, cs:WPP_GLOBAL_Control
0x18007a12a  cmp     rax, r14
0x18007a12d  jz      short loc_18007A171
0x18007a12f  test    byte ptr [rax+1Ch], 8
0x18007a133  jz      short loc_18007A171
0x18007a135  lea     esi, [rdi+2]
0x18007a138  cmp     [rax+19h], sil
0x18007a13c  jb      short loc_18007A171
0x18007a13e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007a143  lea     edx, [rdi+0Ah]
0x18007a146  mov     dword ptr [rsp+2BF8h+lpClass], ebx
0x18007a14a  lea     rcx, aGetworkspacess; "GetWorkspaceSSPInfo failed"
0x18007a151  mov     [rsp+2BF8h+phkResult], rcx
0x18007a156  mov     r9d, eax
0x18007a159  lea     r8, WPP_9a9b29d69df23d7c330004de722d1721_Traceguids
0x18007a160  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a167  mov     rcx, [rcx+10h]
0x18007a16b  call    WPP_SF_DsD
0x18007a170  nop
0x18007a171  jmp     loc_18007AAC3
0x18007a176  cmp     [rsp+2BF8h+var_2BA8], edi
0x18007a17a  jz      loc_18007A238
0x18007a180  mov     rdx, rsi
0x18007a183  lea     rcx, [rsp+2BF8h+var_2B68]
0x18007a18b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18007a190  lea     rdx, SubStr; "\\"
0x18007a197  lea     rcx, [rsp+2BF8h+var_2B68]
0x18007a19f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18007a1a4  lea     rdx, aSspinstalledap; "SSPInstalledApps"
0x18007a1ab  lea     rcx, [rsp+2BF8h+var_2B68]
0x18007a1b3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18007a1b8  lea     rcx, [rsp+2BF8h+var_2B68]
0x18007a1c0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007a1c5  mov     rcx, rax; lpSubKey
0x18007a1c8  lea     rdx, [rsp+2BF8h+var_2B98]
0x18007a1cd  call    ?ReadSSPAppMapFromRegistry@@YAJPEBGAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NUKeyCompareLessIgnoreCase@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@@std@@@Z; ReadSSPAppMapFromRegistry(ushort const *,std::map<std::wstring,bool,KeyCompareLessIgnoreCase,std::allocator<std::pair<std::wstring const,bool>>> &)
0x18007a1d2  mov     ebx, eax
0x18007a1d4  mov     [rsp+2BF8h+var_2BB4], eax
0x18007a1d8  test    eax, eax
0x18007a1da  jns     short loc_18007A238
0x18007a1dc  lea     r14, WPP_GLOBAL_Control
0x18007a1e3  mov     rax, cs:WPP_GLOBAL_Control
0x18007a1ea  cmp     rax, r14
0x18007a1ed  jz      short loc_18007A233
0x18007a1ef  test    byte ptr [rax+1Ch], 8
0x18007a1f3  jz      short loc_18007A233
0x18007a1f5  mov     esi, 2
0x18007a1fa  cmp     [rax+19h], sil
0x18007a1fe  jb      short loc_18007A233
0x18007a200  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007a205  lea     edx, [rsi+9]
0x18007a208  mov     dword ptr [rsp+2BF8h+lpClass], ebx
0x18007a20c  lea     rcx, aReadsspappmapf; "ReadSSPAppMapFromRegistry failed"
0x18007a213  mov     [rsp+2BF8h+phkResult], rcx
0x18007a218  mov     r9d, eax
0x18007a21b  lea     r8, WPP_9a9b29d69df23d7c330004de722d1721_Traceguids
0x18007a222  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a229  mov     rcx, [rcx+10h]
0x18007a22d  call    WPP_SF_DsD
0x18007a232  nop
0x18007a233  jmp     loc_18007AAC3
0x18007a238  mov     rdx, rsi
0x18007a23b  lea     rcx, [rsp+2BF8h+var_2B48]
0x18007a243  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18007a248  lea     rdx, SubStr; "\\"
0x18007a24f  lea     rcx, [rsp+2BF8h+var_2B48]
0x18007a257  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18007a25c  lea     rdx, aResourcemap; "ResourceMap"
0x18007a263  lea     rcx, [rsp+2BF8h+var_2B48]
0x18007a26b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18007a270  lea     rcx, [rsp+2BF8h+var_2B48]
0x18007a278  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007a27d  mov     rdx, rax; lpSubKey
0x18007a280  lea     rax, [rsp+2BF8h+hKey]
0x18007a285  mov     [rsp+2BF8h+phkResult], rax; phkResult
0x18007a28a  mov     r9d, 20019h; samDesired
0x18007a290  xor     r8d, r8d; ulOptions
0x18007a293  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18007a29a  call    cs:__imp_RegOpenKeyExW
0x18007a2a0  mov     ebx, eax
0x18007a2a2  test    eax, eax
0x18007a2a4  jz      short loc_18007A319
0x18007a2a6  lea     r14, WPP_GLOBAL_Control
0x18007a2ad  mov     rax, cs:WPP_GLOBAL_Control
0x18007a2b4  cmp     rax, r14
0x18007a2b7  jz      short loc_18007A303
0x18007a2b9  test    byte ptr [rax+1Ch], 8
0x18007a2bd  jz      short loc_18007A303
0x18007a2bf  mov     esi, 2
0x18007a2c4  cmp     [rax+19h], sil
0x18007a2c8  jb      short loc_18007A303
0x18007a2ca  test    ebx, ebx
0x18007a2cc  jg      short loc_18007A2D2
0x18007a2ce  mov     esi, ebx
0x18007a2d0  jmp     short loc_18007A2DB
0x18007a2d2  movzx   esi, bx
0x18007a2d5  or      esi, 80070000h
0x18007a2db  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007a2e0  mov     edx, 0Ch
0x18007a2e5  mov     dword ptr [rsp+2BF8h+phkResult], esi
0x18007a2e9  mov     r9d, eax
0x18007a2ec  lea     r8, WPP_9a9b29d69df23d7c330004de722d1721_Traceguids
0x18007a2f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a2fa  mov     rcx, [rcx+10h]
0x18007a2fe  call    WPP_SF_Dd
0x18007a303  test    ebx, ebx
0x18007a305  jle     short loc_18007A310
0x18007a307  movzx   ebx, bx
0x18007a30a  or      ebx, 80070000h
0x18007a310  mov     [rsp+2BF8h+var_2BB4], ebx
0x18007a314  jmp     loc_18007AAC3
0x18007a319  mov     [rsp+2BF8h+var_2BA0], edi
0x18007a31d  mov     r12d, edi
0x18007a320  mov     r13d, edi
0x18007a323  mov     [rsp+2BF8h+var_2BA0], edi
0x18007a327  lea     r14, WPP_GLOBAL_Control
0x18007a32e  mov     esi, 2
0x18007a333  lea     r15, WPP_9a9b29d69df23d7c330004de722d1721_Traceguids
0x18007a33a  cmp     r12d, 103h
0x18007a341  jz      loc_18007AAB9
0x18007a347  mov     [rsp+2BF8h+cchName], 100h
0x18007a34f  mov     [rsp+2BF8h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x18007a354  mov     [rsp+2BF8h+lpcchClass], rdi; lpcchClass
0x18007a359  mov     [rsp+2BF8h+lpClass], rdi; lpClass
0x18007a35e  mov     [rsp+2BF8h+phkResult], rdi; lpReserved
0x18007a363  lea     r9, [rsp+2BF8h+cchName]; lpcchName
0x18007a368  lea     r8, [rsp+2BF8h+Name]; lpName
0x18007a370  mov     edx, r13d; dwIndex
0x18007a373  mov     rcx, [rsp+2BF8h+hKey]; hKey
0x18007a378  call    cs:__imp_RegEnumKeyExW
0x18007a37e  mov     r12d, eax
0x18007a381  test    eax, eax
0x18007a383  jz      short loc_18007A3FD
0x18007a385  cmp     eax, 103h
0x18007a38a  jz      loc_18007AAAC
0x18007a390  mov     rax, cs:WPP_GLOBAL_Control
0x18007a397  cmp     rax, r14
0x18007a39a  jz      short loc_18007A3E0
0x18007a39c  test    byte ptr [rax+1Ch], 8
0x18007a3a0  jz      short loc_18007A3E0
0x18007a3a2  cmp     [rax+19h], sil
0x18007a3a6  jb      short loc_18007A3E0
0x18007a3a8  test    r12d, r12d
0x18007a3ab  jg      short loc_18007A3B2
0x18007a3ad  mov     ebx, r12d
0x18007a3b0  jmp     short loc_18007A3BC
0x18007a3b2  movzx   ebx, r12w
0x18007a3b6  or      ebx, 80070000h
0x18007a3bc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007a3c1  mov     edx, 0Dh
0x18007a3c6  mov     dword ptr [rsp+2BF8h+phkResult], ebx
0x18007a3ca  mov     r9d, eax
0x18007a3cd  mov     r8, r15
0x18007a3d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a3d7  mov     rcx, [rcx+10h]
0x18007a3db  call    WPP_SF_Dd
0x18007a3e0  test    r12d, r12d
0x18007a3e3  jg      short loc_18007A3EA
0x18007a3e5  mov     ebx, r12d
0x18007a3e8  jmp     short loc_18007A3F4
0x18007a3ea  movzx   ebx, r12w
0x18007a3ee  or      ebx, 80070000h
0x18007a3f4  mov     [rsp+2BF8h+var_2BB4], ebx
0x18007a3f8  jmp     loc_18007AAC3
0x18007a3fd  mov     [rsp+2BF8h+pcbData], 4
0x18007a405  lea     rax, [rsp+2BF8h+pcbData]
0x18007a40a  mov     [rsp+2BF8h+lpcchClass], rax; pcbData
0x18007a40f  lea     rax, [rsp+2BF8h+pvData]
0x18007a417  mov     [rsp+2BF8h+lpClass], rax; pvData
0x18007a41c  mov     [rsp+2BF8h+phkResult], rdi; pdwType
0x18007a421  mov     r9d, 10h; dwFlags
0x18007a427  lea     r8, ValueName; "IsRDP"
0x18007a42e  lea     rdx, [rsp+2BF8h+Name]; lpSubKey
0x18007a436  mov     rcx, [rsp+2BF8h+hKey]; hkey
0x18007a43b  call    cs:__imp_RegGetValueW
0x18007a441  mov     ebx, eax
0x18007a443  test    eax, eax
0x18007a445  jz      short loc_18007A4AA
0x18007a447  mov     rax, cs:WPP_GLOBAL_Control
0x18007a44e  cmp     rax, r14
0x18007a451  jz      short loc_18007A494
0x18007a453  test    byte ptr [rax+1Ch], 8
0x18007a457  jz      short loc_18007A494
0x18007a459  cmp     [rax+19h], sil
0x18007a45d  jb      short loc_18007A494
0x18007a45f  test    ebx, ebx
0x18007a461  jg      short loc_18007A467
0x18007a463  mov     esi, ebx
0x18007a465  jmp     short loc_18007A470
0x18007a467  movzx   esi, bx
0x18007a46a  or      esi, 80070000h
0x18007a470  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007a475  mov     edx, 0Eh
0x18007a47a  mov     dword ptr [rsp+2BF8h+phkResult], esi
0x18007a47e  mov     r9d, eax
0x18007a481  mov     r8, r15
0x18007a484  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a48b  mov     rcx, [rcx+10h]
0x18007a48f  call    WPP_SF_Dd
0x18007a494  test    ebx, ebx
0x18007a496  jle     short loc_18007A4A1
0x18007a498  movzx   ebx, bx
0x18007a49b  or      ebx, 80070000h
0x18007a4a1  mov     [rsp+2BF8h+var_2BB4], ebx
0x18007a4a5  jmp     loc_18007AAC3
0x18007a4aa  mov     [rsp+2BF8h+pcbData], 2802h
0x18007a4b2  lea     rax, [rsp+2BF8h+pcbData]
0x18007a4b7  mov     [rsp+2BF8h+lpcchClass], rax; pcbData
0x18007a4bc  lea     rax, [rsp+2BF8h+var_2848]
0x18007a4c4  mov     [rsp+2BF8h+lpClass], rax; pvData
0x18007a4c9  mov     [rsp+2BF8h+phkResult], rdi; pdwType
0x18007a4ce  mov     r9d, esi; dwFlags
0x18007a4d1  lea     r8, aResourcefileex; "ResourceFileExt"
0x18007a4d8  lea     rdx, [rsp+2BF8h+Name]; lpSubKey
0x18007a4e0  mov     rcx, [rsp+2BF8h+hKey]; hkey
0x18007a4e5  call    cs:__imp_RegGetValueW
0x18007a4eb  mov     ebx, eax
0x18007a4ed  test    eax, eax
0x18007a4ef  jz      short loc_18007A554
0x18007a4f1  mov     rax, cs:WPP_GLOBAL_Control
0x18007a4f8  cmp     rax, r14
0x18007a4fb  jz      short loc_18007A53E
0x18007a4fd  test    byte ptr [rax+1Ch], 8
0x18007a501  jz      short loc_18007A53E
0x18007a503  cmp     [rax+19h], sil
0x18007a507  jb      short loc_18007A53E
0x18007a509  test    ebx, ebx
0x18007a50b  jg      short loc_18007A511
0x18007a50d  mov     esi, ebx
0x18007a50f  jmp     short loc_18007A51A
0x18007a511  movzx   esi, bx
0x18007a514  or      esi, 80070000h
0x18007a51a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007a51f  mov     edx, 0Fh
0x18007a524  mov     dword ptr [rsp+2BF8h+phkResult], esi
0x18007a528  mov     r9d, eax
0x18007a52b  mov     r8, r15
0x18007a52e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a535  mov     rcx, [rcx+10h]
0x18007a539  call    WPP_SF_Dd
0x18007a53e  test    ebx, ebx
0x18007a540  jle     short loc_18007A54B
0x18007a542  movzx   ebx, bx
0x18007a545  or      ebx, 80070000h
0x18007a54b  mov     [rsp+2BF8h+var_2BB4], ebx
0x18007a54f  jmp     loc_18007AAC3
0x18007a554  lea     rdx, [rsp+2BF8h+var_2848]
0x18007a55c  lea     rcx, [rsp+2BF8h+var_2B18]
0x18007a564  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18007a569  mov     [rsp+2BF8h+pcbData], 2802h
0x18007a571  lea     rax, [rsp+2BF8h+pcbData]
0x18007a576  mov     [rsp+2BF8h+lpcchClass], rax; pcbData
0x18007a57b  lea     rax, [rsp+2BF8h+var_2848]
0x18007a583  mov     [rsp+2BF8h+lpClass], rax; pvData
0x18007a588  mov     [rsp+2BF8h+phkResult], rdi; pdwType
0x18007a58d  mov     r9d, esi; dwFlags
  ... truncated ...
```
