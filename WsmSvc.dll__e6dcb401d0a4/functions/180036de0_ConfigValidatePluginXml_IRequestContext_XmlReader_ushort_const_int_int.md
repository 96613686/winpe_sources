# ConfigValidatePluginXml(IRequestContext *,XmlReader *,ushort const *,int *,int)

- ea: `0x180036de0`
- end: `0x180037947`
- name: `?ConfigValidatePluginXml@@YAHPEAVIRequestContext@@PEAVXmlReader@@PEBGPEAHH@Z`
- size: `2919`
- prototype: `__int64 __fastcall(struct IRequestContext *, struct XmlReader *, wchar_t *, XmlReader *, int)`
- caller_count: `2`
- callee_count: `29`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180048db0`
- `0x180199c88`

## callees

- `0x180005d10`
- `0x180010030`
- `0x180022c00`
- `0x180023920`
- `0x180025d90`
- `0x180026310`
- `0x180035ee0`
- `0x180036038`
- `0x180036de0`
- `0x180037950`
- `0x180037d30`
- `0x180038050`
- `0x18003a610`
- `0x18003c640`
- `0x1800405d0`
- `0x180048db0`
- `0x1800a0380`
- `0x1800c1a2c`
- `0x1800c7ca0`
- `0x1800d42a8`
- `0x1800de510`
- `0x1800e5510`
- `0x180112380`
- `0x1801123a8`
- `0x180121d38`
- `0x1801222cc`
- `0x1801a7b54`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180036ec6`
- `msvcrt!_wcsnicmp` at `0x180036f47`
- `msvcrt!_wcsnicmp` at `0x180037053`
- `msvcrt!_wcsnicmp` at `0x180036ec6`
- `msvcrt!_wcsnicmp` at `0x180036f47`
- `msvcrt!_wcsnicmp` at `0x180037053`
- `msvcrt!_wcsicmp` at `0x180036f71`
- `msvcrt!_wcsicmp` at `0x180036f71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800374f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800377e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800374f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800377e4`

## string_xrefs

- `0x180037282`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x1800372ea`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x180037413`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x1800370c3`: `onecore\admin\wmi\wmx\config\configxmladditionalvalidation.cpp`
- `0x18003715a`: `onecore\admin\wmi\wmx\config\configxmladditionalvalidation.cpp`
- `0x180037259`: `onecore\admin\wmi\wmx\config\configxmladditionalvalidation.cpp`
- `0x180037745`: `onecore\admin\wmi\wmx\config\configxmladditionalvalidation.cpp`
- `0x1800378a8`: `onecore\admin\wmi\wmx\config\configxmladditionalvalidation.cpp`
- `0x1800378fd`: `onecore\admin\wmi\wmx\config\configxmladditionalvalidation.cpp`

## pseudocode

```c
__int64 __fastcall ConfigValidatePluginXml(
        struct IRequestContext *a1,
        struct XmlReader *a2,
        wchar_t *a3,
        XmlReader *a4,
        int a5)
{
  wchar_t *v5; // rax
  __int64 v8; // rax
  __int64 v9; // r15
  __int64 v10; // r14
  int i; // ebx
  __int64 v12; // rcx
  const wchar_t *v13; // rax
  __int64 v14; // rcx
  int j; // ebx
  __int64 v16; // r12
  __int64 v17; // rcx
  const wchar_t *v18; // rax
  const wchar_t *AttributeValue; // rbx
  struct FWXML_ATTRIBUTE *v20; // rbx
  struct FWXML_ATTRIBUTE_LIST *v21; // r8
  wchar_t *v22; // r15
  struct _FWXML_ELEMENT *v23; // r12
  int v24; // r9d
  int k; // ebx
  __int64 v26; // r15
  __int64 v27; // rcx
  const wchar_t *v28; // rax
  struct XmlReader *v29; // rcx
  PVOID *v30; // rcx
  const unsigned __int16 *v32; // r8
  __int64 v33; // rdx
  __int64 v34; // rdx
  const unsigned __int16 *v35; // rax
  wchar_t *FirstConfigManagerForTable; // rbx
  DWORD v37; // ebx
  struct _FWXML_ELEMENT *Root; // rax
  DWORD LastError; // eax
  wchar_t *String2; // [rsp+30h] [rbp-D0h] BYREF
  XmlReader *v41; // [rsp+38h] [rbp-C8h] BYREF
  struct FWXML_ATTRIBUTE *v42; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v43; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *String1[2]; // [rsp+58h] [rbp-A8h]
  int v45; // [rsp+68h] [rbp-98h]
  __int64 v46; // [rsp+70h] [rbp-90h]
  __int64 v47; // [rsp+78h] [rbp-88h]
  _BYTE v48[672]; // [rsp+80h] [rbp-80h] BYREF

  v41 = a4;
  v5 = a3;
  String2 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids);
    a4 = v41;
    v5 = String2;
  }
  if ( !a1 )
  {
    WSManError(
      (wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmladditionalvalidation.cpp",
      223,
      L"223",
      0x54Fu,
      0);
    return 0;
  }
  if ( !a2 )
  {
    v32 = L"224";
    v33 = 224;
    goto LABEL_46;
  }
  if ( !v5 )
  {
    v32 = L"225";
    v33 = 225;
    goto LABEL_46;
  }
  v8 = *((_QWORD *)a2 + 1);
  if ( !v8 )
  {
    v9 = 0;
    *(_DWORD *)a4 = 0;
    v10 = 128;
    goto LABEL_7;
  }
  v9 = *(_QWORD *)(v8 + 16);
  *(_DWORD *)a4 = 0;
  v10 = v9 + 128;
  if ( v9 == -128 )
  {
    WSManError(
      (wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmladditionalvalidation.cpp",
      859,
      L"859",
      0x54Fu,
      0);
LABEL_45:
    v32 = L"239";
    v33 = 239;
LABEL_46:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmladditionalvalidation.cpp", v33, v32, 0x54Fu, a1);
    return 0;
  }
LABEL_7:
  for ( i = 0; ; ++i )
  {
    if ( i == *(_DWORD *)v10 )
      goto LABEL_45;
    v46 = 152LL * i;
    v12 = *(_QWORD *)(v10 + 8) + v46;
    if ( !v12 )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 522, L"522", 0x54Fu, 0);
      continue;
    }
    if ( *(_DWORD *)(v12 + 16) == 9 )
    {
      v13 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v12);
      if ( !_wcsnicmp(v13, L"Resources", 9u) )
        break;
    }
  }
  v47 = *(_QWORD *)(v10 + 8);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids);
  if ( v9 )
  {
    v14 = v9 + 112;
    v42 = (struct FWXML_ATTRIBUTE *)(v9 + 112);
    for ( j = 0; ; ++j )
    {
      if ( j == *(_DWORD *)v14 )
      {
        WSManError(
          (wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmladditionalvalidation.cpp",
          406,
          L"406",
          0x54Fu,
          0);
        goto LABEL_124;
      }
      v16 = 104LL * j;
      v17 = v16 + *(_QWORD *)(v14 + 8);
      if ( v17 )
      {
        if ( *(_DWORD *)(v17 + 16) == 4 )
        {
          v18 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v17);
          if ( !_wcsnicmp(v18, L"Name", 4u) )
          {
            AttributeValue = (const wchar_t *)FwXmlGetAttributeValue(v16 + *(_QWORD *)(v9 + 120));
            if ( !AttributeValue )
              WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 139, L"139", 0x54Fu, 0);
            if ( !_wcsicmp(AttributeValue, String2) )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids);
              if ( !(unsigned int)ValidatePluginFilePath(a1, (struct _FWXML_ELEMENT *)v9, 1) )
              {
                v30 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
                {
                  v34 = 26;
                  goto LABEL_128;
                }
                return 0;
              }
              v20 = (struct FWXML_ATTRIBUTE *)(v9 + 112);
              v21 = (struct FWXML_ATTRIBUTE_LIST *)(v9 + 112);
              v22 = String2;
              if ( !(unsigned int)ValidatePluginAttributesCombination(a1, (struct IRequestContext *)String2, v21) )
              {
                v30 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
                {
                  v34 = 27;
                  goto LABEL_128;
                }
                return 0;
              }
              v23 = (struct _FWXML_ELEMENT *)(v46 + v47);
              if ( !(unsigned int)ValidateResourceUris(a1, (struct _FWXML_ELEMENT *)(v46 + v47)) )
              {
                v30 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
                {
                  v34 = 28;
                  goto LABEL_128;
                }
                return 0;
              }
              if ( !(unsigned int)ValidateSecurityAndCapabilities(a1, v23, (int *)v41) )
              {
                v30 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
                {
                  v34 = 29;
                  goto LABEL_128;
                }
                return 0;
              }
              if ( v10 )
              {
                for ( k = 0; ; ++k )
                {
                  if ( k == *(_DWORD *)v10 )
                    goto LABEL_42;
                  v26 = 152LL * k;
                  v27 = v26 + *(_QWORD *)(v10 + 8);
                  if ( v27 )
                  {
                    if ( *(_DWORD *)(v27 + 16) == 6 )
                    {
                      v28 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v27);
                      if ( !_wcsnicmp(v28, L"Quotas", 6u) )
                      {
                        if ( ValidateQuotas(
                               v29,
                               a1,
                               (struct _FWXML_ELEMENT *)(v26 + *(_QWORD *)(v10 + 8)),
                               *(_DWORD *)v41) )
                        {
LABEL_42:
                          v22 = String2;
                          v20 = v42;
                          goto LABEL_39;
                        }
                        v30 = (PVOID *)WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
                        {
                          v34 = 30;
                          goto LABEL_128;
                        }
                        return 0;
                      }
                    }
                  }
                  else
                  {
                    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 522, L"522", 0x54Fu, 0);
                  }
                }
              }
              WSManError(
                (wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmladditionalvalidation.cpp",
                859,
                L"859",
                0x54Fu,
                0);
LABEL_39:
              if ( a5 )
              {
                v42 = 0;
                if ( FindAttribute(v20, L"RunAsVirtualAccountGroups", &v42, v24) )
                {
                  v35 = (const unsigned __int16 *)FwXmlGetAttributeValue((__int64)v42);
                  v43 = 0;
                  *(_OWORD *)String1 = 0;
                  v45 = 0;
                  if ( !(unsigned int)VirtualAccountGroupsListParser::ProcessList(
                                        (VirtualAccountGroupsListParser *)&v43,
                                        v35,
                                        a1) )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
                    {
                      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids);
                    }
                    VirtualAccountGroupsListParser::Reset((VirtualAccountGroupsListParser *)&v43);
                    return 0;
                  }
                  VirtualAccountGroupsListParser::Reset((VirtualAccountGroupsListParser *)&v43);
                }
                FirstConfigManagerForTable = (wchar_t *)CConfigManager::GetFirstConfigManagerForTable(4, 0);
                String2 = FirstConfigManagerForTable;
                if ( FirstConfigManagerForTable )
                {
                  while ( 1 )
                  {
                    CRequestContext::CRequestContext((CRequestContext *)v48);
                    v41 = 0;
                    *(_QWORD *)&v43 = &PLUGIN_IDENTITY::`vftable';
                    String1[0] = 0;
                    LODWORD(String1[1]) = 0;
                    DWORD2(v43) = 4;
                    if ( !CConfigManager::GetCurrentTableIdentity(
                            (CConfigManager *)FirstConfigManagerForTable,
                            (struct WSMANCONFIGTABLE_IDENTITY *)&v43,
                            0) )
                    {
                      WSManError(
                        (wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmladditionalvalidation.cpp",
                        331,
                        L"331",
                        0x54Fu,
                        a1);
                      PLUGIN_IDENTITY::~PLUGIN_IDENTITY((PLUGIN_IDENTITY *)&v43);
                      AutoCleanup<AutoDelete<XmlReader>,XmlReader *>::ReleasePtr(&v41);
                      CRequestContext::~CRequestContext((CRequestContext *)v48);
                      AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&String2);
                      return 0;
                    }
                    if ( !(unsigned int)StringCchEqualsCI(String1[0], v22) )
                    {
                      if ( (unsigned int)CConfigManager::GetConfigXml(
                                           (CConfigManager *)FirstConfigManagerForTable,
                                           a1,
                                           0,
                                           &v41,
                                           0) )
                      {
                        Root = XmlReader::GetRoot(v41);
                        v42 = 0;
                        if ( !FindChildElement((struct _FWXML_ELEMENT *)((char *)Root + 128), L"Resources", &v42, 1) )
                        {
                          WSManError(
                            (wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmladditionalvalidation.cpp",
                            351,
                            L"351",
                            0x54Fu,
                            a1);
                          PLUGIN_IDENTITY::~PLUGIN_IDENTITY((PLUGIN_IDENTITY *)&v43);
                          AutoCleanup<AutoDelete<XmlReader>,XmlReader *>::ReleasePtr(&v41);
                          CRequestContext::~CRequestContext((CRequestContext *)v48);
                          AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&String2);
                          return 0;
                        }
                        if ( !ValidateResourceUris(a1, v23, v42) )
                        {
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
                          {
                            WPP_SF_(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              34,
                              WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids);
                          }
LABEL_120:
                          PLUGIN_IDENTITY::~PLUGIN_IDENTITY((PLUGIN_IDENTITY *)&v43);
                          AutoCleanup<AutoDelete<XmlReader>,XmlReader *>::ReleasePtr(&v41);
                          CRequestContext::~CRequestContext((CRequestContext *)v48);
                          AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&String2);
                          return 0;
                        }
                      }
                      else
                      {
                        if ( (*(unsigned int (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a1 + 152LL))(a1) != -2144108144 )
                        {
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
                          {
                            WPP_SF_(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              35,
                              WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids);
                          }
                          goto LABEL_120;
                        }
                        (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a1 + 200LL))(a1, 1);
                      }
                    }
                    if ( !(unsigned int)CConfigManager::NextRow((CConfigManager *)FirstConfigManagerForTable) )
                      break;
                    PLUGIN_IDENTITY::~PLUGIN_IDENTITY((PLUGIN_IDENTITY *)&v43);
                    AutoCleanup<AutoDelete<XmlReader>,XmlReader *>::ReleasePtr(&v41);
                    CRequestContext::~CRequestContext((CRequestContext *)v48);
                  }
                  LastError = GetLastError();
                  if ( LastError != 259 )
                  {
                    (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a1 + 72LL))(a1, LastError);
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
                    {
                      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids);
                    }
                    goto LABEL_120;
                  }
                  PLUGIN_IDENTITY::~PLUGIN_IDENTITY((PLUGIN_IDENTITY *)&v43);
                  AutoCleanup<AutoDelete<XmlReader>,XmlReader *>::ReleasePtr(&v41);
                  CRequestContext::~CRequestContext((CRequestContext *)v48);
                  AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&String2);
                  goto LABEL_40;
                }
                v37 = GetLastError();
                if ( v37 != 259 )
                {
                  (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a1 + 72LL))(a1, v37);
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      32,
                      WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids,
                      v37);
                  }
                  AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&String2);
                  return 0;
                }
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids);
                AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&String2);
              }
              else
              {
LABEL_40:
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids);
              }
              return 1;
            }
            (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64))(*(_QWORD *)a1 + 64LL))(
              a1,
              2150858819LL,
              1077134539);
            v30 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              return 0;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids);
              goto LABEL_124;
            }
            goto LABEL_125;
          }
        }
      }
      else
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 522, L"522", 0x54Fu, 0);
      }
      v14 = v9 + 112;
    }
  }
  WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmladditionalvalidation.cpp", 399, L"399", 0x54Fu, a1);
LABEL_124:
  v30 = (PVOID *)WPP_GLOBAL_Control;
LABEL_125:
  if ( v30 != &WPP_GLOBAL_Control && (*((_DWORD *)v30 + 7) & 0x200000) != 0 )
  {
    v34 = 25;
LABEL_128:
    WPP_SF_(v30[2], v34, WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180036de0  push    rbp
0x180036de2  push    rbx
0x180036de3  push    rsi
0x180036de4  push    rdi
0x180036de5  push    r12
0x180036de7  push    r13
0x180036de9  push    r14
0x180036deb  push    r15
0x180036ded  lea     rbp, [rsp-238h]
0x180036df5  sub     rsp, 338h
0x180036dfc  mov     rax, cs:__security_cookie
0x180036e03  xor     rax, rsp
0x180036e06  mov     [rbp+270h+var_50], rax
0x180036e0d  mov     [rsp+370h+var_338], r9
0x180036e12  mov     rax, r8
0x180036e15  mov     [rsp+370h+String2], rax
0x180036e1a  mov     rbx, rdx
0x180036e1d  mov     rdi, rcx
0x180036e20  lea     rdx, WPP_GLOBAL_Control
0x180036e27  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e2e  cmp     rcx, rdx
0x180036e31  jnz     loc_1800371D4
0x180036e37  test    rdi, rdi
0x180036e3a  jz      loc_180037205
0x180036e40  test    rbx, rbx
0x180036e43  jz      loc_180037225
0x180036e49  test    rax, rax
0x180036e4c  jz      loc_18003716B
0x180036e52  mov     rax, [rbx+8]
0x180036e56  test    rax, rax
0x180036e59  jz      loc_18003709E
0x180036e5f  mov     r15, [rax+10h]
0x180036e63  mov     dword ptr [r9], 0
0x180036e6a  lea     r14, [r15+80h]
0x180036e71  test    r14, r14
0x180036e74  jz      loc_18003723C
0x180036e7a  mov     r13, r14
0x180036e7d  xor     ebx, ebx
0x180036e7f  mov     esi, 54Fh
0x180036e84  cmp     ebx, [r13+0]
0x180036e88  jz      loc_180037146
0x180036e8e  movsxd  rax, ebx
0x180036e91  imul    rcx, rax, 98h
0x180036e98  mov     [rsp+370h+var_300], rcx
0x180036e9d  add     rcx, [r13+8]
0x180036ea1  jz      loc_18003726A
0x180036ea7  cmp     dword ptr [rcx+10h], 9
0x180036eab  jnz     loc_18003728E
0x180036eb1  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x180036eb6  mov     rcx, rax; String1
0x180036eb9  mov     r8d, 9; MaxCount
0x180036ebf  lea     rdx, aResources; "Resources"
0x180036ec6  call    cs:__imp__wcsnicmp
0x180036ecc  test    eax, eax
0x180036ece  jnz     loc_18003728E
0x180036ed4  mov     rax, [r13+8]
0x180036ed8  mov     [rsp+370h+var_2F8], rax
0x180036edd  mov     rcx, cs:WPP_GLOBAL_Control
0x180036ee4  lea     rax, WPP_GLOBAL_Control
0x180036eeb  cmp     rcx, rax
0x180036eee  jnz     loc_180037295
0x180036ef4  test    r15, r15
0x180036ef7  jz      loc_1800372BC
0x180036efd  lea     rcx, [r15+70h]
0x180036f01  mov     [rsp+370h+var_330], rcx
0x180036f06  xor     ebx, ebx
0x180036f08  cmp     ebx, [rcx]
0x180036f0a  jz      loc_1800378E5
0x180036f10  movsxd  rax, ebx
0x180036f13  imul    r12, rax, 68h ; 'h'
0x180036f17  mov     rcx, [rcx+8]
0x180036f1b  add     rcx, r12
0x180036f1e  jz      loc_1800372D2
0x180036f24  cmp     dword ptr [rcx+10h], 4
0x180036f28  jz      short loc_180036F32
0x180036f2a  inc     ebx
0x180036f2c  lea     rcx, [r15+70h]
0x180036f30  jmp     short loc_180036F08
0x180036f32  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x180036f37  mov     rcx, rax; String1
0x180036f3a  mov     r8d, 4; MaxCount
0x180036f40  lea     rdx, aName; "Name"
0x180036f47  call    cs:__imp__wcsnicmp
0x180036f4d  test    eax, eax
0x180036f4f  jnz     short loc_180036F2A
0x180036f51  mov     rcx, [r15+78h]
0x180036f55  add     rcx, r12
0x180036f58  call    FwXmlGetAttributeValue
0x180036f5d  mov     rbx, rax
0x180036f60  test    rax, rax
0x180036f63  jz      loc_1800372FB
0x180036f69  mov     rdx, [rsp+370h+String2]; String2
0x180036f6e  mov     rcx, rbx; String1
0x180036f71  call    cs:__imp__wcsicmp
0x180036f77  test    eax, eax
0x180036f79  jnz     loc_180037324
0x180036f7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036f86  lea     rbx, WPP_GLOBAL_Control
0x180036f8d  mov     r12d, 200000h
0x180036f93  cmp     rcx, rbx
0x180036f96  jnz     loc_18003735A
0x180036f9c  mov     r8d, 1; int
0x180036fa2  mov     rdx, r15; struct _FWXML_ELEMENT *
0x180036fa5  mov     rcx, rdi; struct IRequestContext *
0x180036fa8  call    ?ValidatePluginFilePath@@YAHPEAVIRequestContext@@PEAU_FWXML_ELEMENT@@H@Z; ValidatePluginFilePath(IRequestContext *,_FWXML_ELEMENT *,int)
0x180036fad  test    eax, eax
0x180036faf  jz      loc_18003737E
0x180036fb5  lea     rbx, [r15+70h]
0x180036fb9  mov     r8, rbx; struct FWXML_ATTRIBUTE_LIST *
0x180036fbc  mov     r15, [rsp+370h+String2]
0x180036fc1  mov     rdx, r15; struct IRequestContext *
0x180036fc4  mov     rcx, rdi; struct IRequestContext *
0x180036fc7  call    ?ValidatePluginAttributesCombination@@YAHPEAVIRequestContext@@PEBGPEAUFWXML_ATTRIBUTE_LIST@@@Z; ValidatePluginAttributesCombination(IRequestContext *,ushort const *,FWXML_ATTRIBUTE_LIST *)
0x180036fcc  test    eax, eax
0x180036fce  jz      loc_1800373A2
0x180036fd4  mov     r12, [rsp+370h+var_2F8]
0x180036fd9  add     r12, [rsp+370h+var_300]
0x180036fde  mov     rdx, r12; struct _FWXML_ELEMENT *
0x180036fe1  mov     rcx, rdi; struct IRequestContext *
0x180036fe4  call    ?ValidateResourceUris@@YAHPEAVIRequestContext@@PEAU_FWXML_ELEMENT@@@Z; ValidateResourceUris(IRequestContext *,_FWXML_ELEMENT *)
0x180036fe9  test    eax, eax
0x180036feb  jz      loc_1800373CD
0x180036ff1  mov     r8, [rsp+370h+var_338]; int *
0x180036ff6  mov     rdx, r12; struct _FWXML_ELEMENT *
0x180036ff9  mov     rcx, rdi; struct IRequestContext *
0x180036ffc  call    ?ValidateSecurityAndCapabilities@@YAHPEAVIRequestContext@@PEAU_FWXML_ELEMENT@@PEAH@Z; ValidateSecurityAndCapabilities(IRequestContext *,_FWXML_ELEMENT *,int *)
0x180037001  test    eax, eax
0x180037003  jz      loc_18003717F
0x180037009  test    r14, r14
0x18003700c  jz      loc_1800370AF
0x180037012  xor     ebx, ebx
0x180037014  cmp     ebx, [r14]
0x180037017  jz      loc_180037117
0x18003701d  movsxd  rax, ebx
0x180037020  imul    r15, rax, 98h
0x180037027  mov     rcx, [r13+8]
0x18003702b  add     rcx, r15
0x18003702e  jz      loc_1800373FB
0x180037034  cmp     dword ptr [rcx+10h], 6
0x180037038  jnz     loc_18003741F
0x18003703e  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x180037043  mov     rcx, rax; String1
0x180037046  mov     r8d, 6; MaxCount
0x18003704c  lea     rdx, aQuotas; "Quotas"
0x180037053  call    cs:__imp__wcsnicmp
0x180037059  test    eax, eax
0x18003705b  jnz     loc_18003741F
0x180037061  mov     r8, [r13+8]
0x180037065  add     r8, r15; struct _FWXML_ELEMENT *
0x180037068  mov     rax, [rsp+370h+var_338]
0x18003706d  mov     r9d, [rax]; int
0x180037070  mov     rdx, rdi; struct IRequestContext *
0x180037073  call    ?ValidateQuotas@@YA_NPEAVXmlReader@@PEAVIRequestContext@@PEAU_FWXML_ELEMENT@@H@Z; ValidateQuotas(XmlReader *,IRequestContext *,_FWXML_ELEMENT *,int)
0x180037078  xor     r14d, r14d
0x18003707b  test    al, al
0x18003707d  jnz     loc_18003711A
0x180037083  mov     rcx, cs:WPP_GLOBAL_Control
0x18003708a  lea     rax, WPP_GLOBAL_Control
0x180037091  cmp     rcx, rax
0x180037094  jnz     loc_180037426
0x18003709a  xor     eax, eax
0x18003709c  jmp     short loc_1800370F4
0x18003709e  xor     r15d, r15d
0x1800370a1  mov     [r9], r15d
0x1800370a4  mov     r14d, 80h
0x1800370aa  jmp     loc_180036E7A
0x1800370af  mov     [rsp+370h+var_350], r14; struct IRequestContext *
0x1800370b4  mov     r9d, esi; unsigned int
0x1800370b7  lea     r8, a859; "859"
0x1800370be  mov     edx, 35Bh; unsigned int
0x1800370c3  lea     rcx, aOnecoreAdminWm_160; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x1800370ca  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800370cf  cmp     [rbp+270h+arg_20], r14d
0x1800370d6  jnz     loc_18003743D
0x1800370dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800370e3  lea     rax, WPP_GLOBAL_Control
0x1800370ea  cmp     rcx, rax
0x1800370ed  jnz     short loc_180037126
0x1800370ef  mov     eax, 1
0x1800370f4  mov     rcx, [rbp+270h+var_50]
0x1800370fb  xor     rcx, rsp; StackCookie
0x1800370fe  call    __security_check_cookie
0x180037103  add     rsp, 338h
0x18003710a  pop     r15
0x18003710c  pop     r14
0x18003710e  pop     r13
0x180037110  pop     r12
0x180037112  pop     rdi
0x180037113  pop     rsi
0x180037114  pop     rbx
0x180037115  pop     rbp
0x180037116  retn
0x180037117  xor     r14d, r14d
0x18003711a  mov     r15, [rsp+370h+String2]
0x18003711f  mov     rbx, [rsp+370h+var_330]
0x180037124  jmp     short loc_1800370CF
0x180037126  test    dword ptr [rcx+1Ch], 200000h
0x18003712d  jz      short loc_1800370EF
0x18003712f  mov     edx, 25h ; '%'
0x180037134  lea     r8, WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids
0x18003713b  mov     rcx, [rcx+10h]
0x18003713f  call    WPP_SF_
0x180037144  jmp     short loc_1800370EF
0x180037146  mov     r9d, esi; unsigned int
0x180037149  lea     r8, a239; "239"
0x180037150  mov     edx, 0EFh; unsigned int
0x180037155  mov     [rsp+370h+var_350], rdi; struct IRequestContext *
0x18003715a  lea     rcx, aOnecoreAdminWm_160; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x180037161  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180037166  jmp     loc_18003709A
0x18003716b  mov     r9d, 54Fh
0x180037171  lea     r8, a225; "225"
0x180037178  mov     edx, 0E1h
0x18003717d  jmp     short loc_180037155
0x18003717f  mov     rcx, cs:WPP_GLOBAL_Control
0x180037186  lea     rax, WPP_GLOBAL_Control
0x18003718d  cmp     rcx, rax
0x180037190  jz      loc_18003709A
0x180037196  test    dword ptr [rcx+1Ch], 200000h
0x18003719d  jz      loc_18003709A
0x1800371a3  mov     edx, 1Dh
0x1800371a8  jmp     loc_180037932
0x1800371ad  test    dword ptr [rcx+1Ch], 200000h
0x1800371b4  jz      loc_180037917
0x1800371ba  mov     edx, 27h ; '''
0x1800371bf  lea     r8, WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids
0x1800371c6  mov     rcx, [rcx+10h]
0x1800371ca  call    WPP_SF_
0x1800371cf  jmp     loc_180037910
0x1800371d4  test    dword ptr [rcx+1Ch], 200000h
0x1800371db  jz      loc_180036E37
0x1800371e1  mov     edx, 18h
0x1800371e6  lea     r8, WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids
0x1800371ed  mov     rcx, [rcx+10h]
0x1800371f1  call    WPP_SF_
0x1800371f6  mov     r9, [rsp+370h+var_338]
0x1800371fb  mov     rax, [rsp+370h+String2]
0x180037200  jmp     loc_180036E37
0x180037205  mov     [rsp+370h+var_350], 0
0x18003720e  mov     r9d, 54Fh
0x180037214  lea     r8, a223; "223"
0x18003721b  mov     edx, 0DFh
0x180037220  jmp     loc_18003715A
0x180037225  mov     r9d, 54Fh
0x18003722b  lea     r8, a224; "224"
0x180037232  mov     edx, 0E0h
0x180037237  jmp     loc_180037155
0x18003723c  mov     [rsp+370h+var_350], 0; struct IRequestContext *
0x180037245  mov     esi, 54Fh
0x18003724a  mov     r9d, esi; unsigned int
0x18003724d  lea     r8, a859; "859"
0x180037254  mov     edx, 35Bh; unsigned int
0x180037259  lea     rcx, aOnecoreAdminWm_160; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x180037260  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180037265  jmp     loc_180037146
0x18003726a  mov     [rsp+370h+var_350], 0; struct IRequestContext *
0x180037273  mov     r9d, esi; unsigned int
0x180037276  lea     r8, a522; "522"
0x18003727d  mov     edx, 20Ah; unsigned int
0x180037282  lea     rcx, aOnecoreAdminWm_5; "onecore\\admin\\wmi\\wmx\\fwxml\\fwxml."...
0x180037289  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18003728e  inc     ebx
0x180037290  jmp     loc_180036E84
0x180037295  test    dword ptr [rcx+1Ch], 200000h
0x18003729c  jz      loc_180036EF4
0x1800372a2  mov     edx, 26h ; '&'
0x1800372a7  lea     r8, WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids
0x1800372ae  mov     rcx, [rcx+10h]
0x1800372b2  call    WPP_SF_
0x1800372b7  jmp     loc_180036EF4
0x1800372bc  mov     [rsp+370h+var_350], rdi
0x1800372c1  lea     r8, a399; "399"
0x1800372c8  mov     edx, 18Fh
0x1800372cd  jmp     loc_1800378FA
0x1800372d2  mov     [rsp+370h+var_350], 0; struct IRequestContext *
0x1800372db  mov     r9d, esi; unsigned int
0x1800372de  lea     r8, a522; "522"
0x1800372e5  mov     edx, 20Ah; unsigned int
0x1800372ea  lea     rcx, aOnecoreAdminWm_5; "onecore\\admin\\wmi\\wmx\\fwxml\\fwxml."...
0x1800372f1  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800372f6  jmp     loc_180036F2A
0x1800372fb  mov     [rsp+370h+var_350], 0; struct IRequestContext *
0x180037304  mov     r9d, esi; unsigned int
0x180037307  lea     r8, a139; "139"
0x18003730e  mov     edx, 8Bh; unsigned int
0x180037313  lea     rcx, aOnecoreAdminWm_90; "onecore\\admin\\wmi\\wmx\\stdlib\\wsman"...
0x18003731a  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18003731f  jmp     loc_180036F69
0x180037324  mov     rax, [rdi]
0x180037327  mov     edx, 80338043h
0x18003732c  mov     r8d, 4033C4CBh
0x180037332  mov     rcx, rdi
0x180037335  mov     rax, [rax+40h]
0x180037339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003733e  mov     rcx, cs:WPP_GLOBAL_Control
0x180037345  lea     rbx, WPP_GLOBAL_Control
0x18003734c  cmp     rcx, rbx
0x18003734f  jz      loc_18003709A
0x180037355  jmp     loc_1800371AD
0x18003735a  test    [rcx+1Ch], r12d
  ... truncated ...
```
