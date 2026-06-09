# ValidateSecurityAndCapabilities(IRequestContext *,_FWXML_ELEMENT *,int *)

- ea: `0x180038050`
- end: `0x180038e1c`
- name: `?ValidateSecurityAndCapabilities@@YAHPEAVIRequestContext@@PEAU_FWXML_ELEMENT@@PEAH@Z`
- size: `3532`
- prototype: `__int64 __fastcall(struct IRequestContext *, struct _FWXML_ELEMENT *, int *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180036de0`
- `0x1801a6268`

## callees

- `0x180005d10`
- `0x18000f700`
- `0x180036864`
- `0x180036d00`
- `0x180038050`
- `0x18003a610`
- `0x18003c640`
- `0x18003c670`
- `0x180064250`
- `0x1800ac320`
- `0x180112380`
- `0x1801133b0`
- `0x1801ba182`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18003818f`
- `msvcrt!_wcsnicmp` at `0x180038233`
- `msvcrt!_wcsnicmp` at `0x18003825b`
- `msvcrt!_wcsnicmp` at `0x1800382d7`
- `msvcrt!_wcsnicmp` at `0x180038334`
- `msvcrt!_wcsnicmp` at `0x1800386b4`
- `msvcrt!_wcsnicmp` at `0x18003895f`
- `msvcrt!_wcsnicmp` at `0x18003818f`
- `msvcrt!_wcsnicmp` at `0x180038233`
- `msvcrt!_wcsnicmp` at `0x18003825b`
- `msvcrt!_wcsnicmp` at `0x1800382d7`
- `msvcrt!_wcsnicmp` at `0x180038334`
- `msvcrt!_wcsnicmp` at `0x1800386b4`
- `msvcrt!_wcsnicmp` at `0x18003895f`
- `msvcrt!_wcsicmp` at `0x180038363`
- `msvcrt!_wcsicmp` at `0x180038462`
- `msvcrt!_wcsicmp` at `0x1800386e7`
- `msvcrt!_wcsicmp` at `0x18003871b`
- `msvcrt!_wcsicmp` at `0x18003873c`
- `msvcrt!_wcsicmp` at `0x18003875d`
- `msvcrt!_wcsicmp` at `0x18003877e`
- `msvcrt!_wcsicmp` at `0x18003879f`
- `msvcrt!_wcsicmp` at `0x1800387bc`
- `msvcrt!_wcsicmp` at `0x1800387dd`
- `msvcrt!_wcsicmp` at `0x1800387fe`
- `msvcrt!_wcsicmp` at `0x180038837`
- `msvcrt!_wcsicmp` at `0x180038363`
- `msvcrt!_wcsicmp` at `0x180038462`
- `msvcrt!_wcsicmp` at `0x1800386e7`
- `msvcrt!_wcsicmp` at `0x18003871b`
- `msvcrt!_wcsicmp` at `0x18003873c`
- `msvcrt!_wcsicmp` at `0x18003875d`
- `msvcrt!_wcsicmp` at `0x18003877e`
- `msvcrt!_wcsicmp` at `0x18003879f`
- `msvcrt!_wcsicmp` at `0x1800387bc`
- `msvcrt!_wcsicmp` at `0x1800387dd`
- `msvcrt!_wcsicmp` at `0x1800387fe`
- `msvcrt!_wcsicmp` at `0x180038837`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18003847d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18003847d`

## string_xrefs

- `0x180038188`: `ResourceUri`
- `0x180038958`: `ResourceUri`
- `0x180038150`: `http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration`
- `0x180038600`: `http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration`
- `0x1800389d1`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x180038a01`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x180038a32`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x180038a50`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x180038a75`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x180038aba`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x180038ae2`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x180038b4b`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x180038dd0`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18003822c`: `Security`
- `0x180038254`: `Security`
- `0x180038753`: `Create`
- `0x180038774`: `Delete`
- `0x180038859`: `onecore\admin\wmi\wmx\config\configxmladditionalvalidation.cpp`
- `0x1800388aa`: `onecore\admin\wmi\wmx\config\configxmladditionalvalidation.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ValidateSecurityAndCapabilities(struct IRequestContext *a1, struct _FWXML_ELEMENT *a2, int *a3)
{
  unsigned int v4; // ecx
  __int64 v5; // rax
  __int64 v6; // rcx
  int v7; // esi
  _QWORD *v8; // r13
  _QWORD *v9; // r12
  __int64 v10; // r15
  __int64 v11; // rbx
  const wchar_t **v12; // rax
  __int64 v13; // rcx
  const wchar_t *v14; // rax
  const wchar_t *v15; // rcx
  const wchar_t *v16; // rax
  wchar_t *AttributeValue; // r15
  struct _FWXML_ELEMENT *v18; // rdx
  unsigned int v19; // ecx
  __int64 v20; // rax
  __int64 v21; // rbx
  const wchar_t *v22; // rax
  const wchar_t *v23; // rax
  int v24; // eax
  BOOL v25; // ecx
  int j; // esi
  __int64 v27; // r15
  __int64 v28; // rcx
  const wchar_t *v29; // rax
  const wchar_t *v30; // rsi
  int k; // r15d
  __int64 v32; // r12
  __int64 v33; // rcx
  const wchar_t *v34; // rax
  const wchar_t *v35; // r15
  int v36; // r13d
  int m; // r15d
  __int64 v38; // r12
  __int64 v39; // rcx
  wchar_t *Attribute; // rsi
  const unsigned __int16 *v42; // rax
  BOOL v43; // r9d
  struct IRequestContext *v44; // rcx
  HLOCAL v45; // rcx
  unsigned int v46; // ecx
  void (__fastcall *v47)(struct IRequestContext *, __int64, __int64, const unsigned __int16 *); // rbx
  const unsigned __int16 *ResourceUriAttributeValue; // rax
  _QWORD *v49; // rcx
  __int64 v50; // rdx
  _QWORD *v51; // rcx
  __int64 v52; // rdx
  __int64 v53; // rdx
  const wchar_t *v54; // rax
  const wchar_t *v55; // rax
  const wchar_t *v56; // rbx
  const unsigned __int16 *v57; // r8
  unsigned int v58; // edx
  unsigned int v59; // edx
  const unsigned __int16 *v60; // r8
  __int64 v61; // rbx
  const wchar_t **v62; // rax
  __int64 v63; // rcx
  const wchar_t *v64; // rax
  const wchar_t *v65; // rcx
  int i; // esi
  const wchar_t *v67; // rax
  void (__fastcall *v68)(struct IRequestContext *, __int64, __int64, const wchar_t *, const unsigned __int16 *); // rbx
  const unsigned __int16 *v69; // rax
  struct IRequestContext *v70; // [rsp+20h] [rbp-79h]
  struct _FWXML_ELEMENT *v71; // [rsp+30h] [rbp-69h]
  HLOCAL hMem; // [rsp+38h] [rbp-61h] BYREF
  int v73; // [rsp+40h] [rbp-59h]
  int v74; // [rsp+44h] [rbp-55h]
  unsigned int v75; // [rsp+48h] [rbp-51h]
  unsigned int v76; // [rsp+4Ch] [rbp-4Dh]
  wchar_t *v77; // [rsp+50h] [rbp-49h]
  struct _FWXML_ELEMENT *v78; // [rsp+58h] [rbp-41h]
  __int128 v79; // [rsp+60h] [rbp-39h]
  __int128 v80; // [rsp+70h] [rbp-29h]
  int v81; // [rsp+80h] [rbp-19h]
  __int128 v82; // [rsp+88h] [rbp-11h]
  __int128 v83; // [rsp+98h] [rbp-1h]
  int *v84; // [rsp+B0h] [rbp+17h]

  v84 = a3;
  v78 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids);
    a2 = v78;
  }
  if ( !a1 )
  {
    v70 = 0;
    v57 = L"607";
    v58 = 607;
LABEL_138:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmladditionalvalidation.cpp", v58, v57, 0x54Fu, v70);
    return 0;
  }
  if ( !a2 )
  {
    v70 = a1;
    v57 = L"608";
    v58 = 608;
    goto LABEL_138;
  }
  v4 = *((_DWORD *)a2 + 32);
  v76 = v4;
  if ( !v4 )
  {
    v70 = a1;
    v57 = L"614";
    v58 = 614;
    goto LABEL_138;
  }
  v82 = 0;
  v83 = 0;
  v5 = 0;
  while ( 1 )
  {
    v74 = v5;
    if ( (unsigned int)v5 >= v4 )
    {
      if ( !HIDWORD(v83)
        || !(_DWORD)v82
        && __PAIR64__(DWORD1(v82), 0) == DWORD2(v82)
        && __PAIR64__(HIDWORD(v82), 0) == (unsigned int)v83
        && __PAIR64__(DWORD1(v83), 0) == DWORD2(v83) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids);
        return 1;
      }
      (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64))(*(_QWORD *)a1 + 64LL))(
        a1,
        2150858819LL,
        1077134585);
      v49 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) == 0 )
        return 0;
      v50 = 57;
LABEL_102:
      WPP_SF_(v49[2], v50, WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids);
      return 0;
    }
    v6 = (unsigned int)v5 >= *((_DWORD *)a2 + 32) ? 0LL : *((_QWORD *)a2 + 17) + 152 * v5;
    v71 = (struct _FWXML_ELEMENT *)v6;
    v7 = 0;
    v8 = (_QWORD *)(v6 + 120);
    v9 = (_QWORD *)(v6 + 120);
    while ( 1 )
    {
      if ( v7 == *(_DWORD *)(v6 + 112) )
      {
        for ( i = 0; ; ++i )
        {
          if ( i == *(_DWORD *)(v6 + 112) )
            goto LABEL_141;
          v10 = 104LL * i;
          v61 = v10 + *v9;
          v62 = (const wchar_t **)(v61 + 48);
          if ( v61 == -48 )
            goto LABEL_166;
          if ( *(_DWORD *)(v61 + 64) )
            goto LABEL_156;
          v63 = *(_QWORD *)(v61 + 56);
          if ( v63 == -1 )
          {
            v65 = *v62;
          }
          else
          {
            v64 = *v62;
            v65 = v64 ? (const wchar_t *)(*(_QWORD *)v64 + 2 * v63) : 0LL;
          }
          if ( !wcsncmp_0(v65, &Class, 0) )
            break;
LABEL_155:
          v6 = (__int64)v71;
LABEL_156:
          v9 = v8;
        }
        if ( v61 )
        {
          if ( *(_DWORD *)(v61 + 16) == 11 )
          {
            v67 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v61);
            if ( !_wcsnicmp(v67, L"ResourceUri", 0xBu) )
              goto LABEL_22;
          }
          goto LABEL_155;
        }
LABEL_166:
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
        goto LABEL_155;
      }
      v10 = 104LL * v7;
      v9 = (_QWORD *)(v6 + 120);
      v11 = v10 + *(_QWORD *)(v6 + 120);
      v12 = (const wchar_t **)(v11 + 48);
      if ( v11 == -48 )
        goto LABEL_164;
      if ( *(_DWORD *)(v11 + 64) != 68 )
        goto LABEL_20;
      v13 = *(_QWORD *)(v11 + 56);
      if ( v13 == -1 )
      {
        v15 = *v12;
      }
      else
      {
        v14 = *v12;
        v15 = v14 ? (const wchar_t *)(*(_QWORD *)v14 + 2 * v13) : 0LL;
      }
      if ( !wcsncmp_0(v15, L"http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration", 0x44u) )
        break;
LABEL_19:
      v6 = (__int64)v71;
LABEL_20:
      ++v7;
    }
    if ( !v11 )
    {
LABEL_164:
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
      goto LABEL_19;
    }
    if ( *(_DWORD *)(v11 + 16) != 11 )
      goto LABEL_19;
    v16 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v11);
    if ( _wcsnicmp(v16, L"ResourceUri", 0xBu) )
      goto LABEL_19;
LABEL_22:
    AttributeValue = (wchar_t *)FwXmlGetAttributeValue(v10 + *v9);
    v77 = AttributeValue;
    if ( !AttributeValue )
    {
LABEL_141:
      (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a1 + 72LL))(a1, 2150858819LL);
      return 0;
    }
    v79 = 0;
    v80 = 0;
    v81 = 0;
    v18 = v71;
    if ( !v71 )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x49Bu, L"1179", 0x54Fu, 0);
LABEL_194:
      WSManError(
        (wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmladditionalvalidation.cpp",
        0x28Eu,
        L"654",
        0x54Fu,
        a1);
      return 0;
    }
    v19 = *((_DWORD *)v71 + 32);
    v75 = v19;
    if ( !v19 )
      goto LABEL_194;
    v20 = 0;
LABEL_26:
    v73 = v20;
    if ( (unsigned int)v20 < v19 )
      break;
    if ( HIDWORD(v80)
      && ((_DWORD)v79
       || __PAIR64__(DWORD1(v79), 0) != DWORD2(v79)
       || __PAIR64__(HIDWORD(v79), 0) != (unsigned int)v80
       || __PAIR64__(DWORD1(v80), 0) != DWORD2(v80)) )
    {
      v47 = *(void (__fastcall **)(struct IRequestContext *, __int64, __int64, const unsigned __int16 *))(*(_QWORD *)a1 + 64LL);
      ResourceUriAttributeValue = GetResourceUriAttributeValue(v18);
      v47(a1, 2150858819LL, 1077134538, ResourceUriAttributeValue);
      v49 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) == 0 )
        return 0;
      v50 = 56;
      goto LABEL_102;
    }
    v5 = (unsigned int)(v74 + 1);
    a2 = v78;
    v4 = v76;
  }
  if ( (unsigned int)v20 < *((_DWORD *)v18 + 32) )
  {
    v21 = *((_QWORD *)v18 + 17) + 152 * v20;
    if ( !v21 )
      goto LABEL_168;
    if ( *(_DWORD *)(v21 + 16) != 8 )
      goto LABEL_38;
    v22 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(*((_QWORD *)v18 + 17) + 152 * v20);
    if ( _wcsnicmp(v22, L"Security", 8u) )
    {
      if ( *(_DWORD *)(v21 + 16) != 8 )
        goto LABEL_38;
      v23 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v21);
      v24 = _wcsnicmp(v23, L"Security", 8u);
      v25 = v24 == 0;
      if ( !v24 )
      {
        if ( v21 == -48 )
        {
          WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
LABEL_35:
          v25 = 0;
        }
        else
        {
          if ( *(_DWORD *)(v21 + 64) != 68 )
            goto LABEL_35;
          v54 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v21 + 48);
          v25 = wcsncmp_0(v54, L"http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration", 0x44u) == 0;
        }
      }
      if ( !v25 )
        goto LABEL_37;
    }
    hMem = 0;
    Attribute = (wchar_t *)GetAttribute(v21, L"Uri");
    if ( !Attribute )
    {
      v44 = a1;
LABEL_90:
      v53 = 2150858819LL;
      goto LABEL_91;
    }
    v42 = (const unsigned __int16 *)GetAttribute(v21, L"Sddl");
    v44 = a1;
    if ( !v42 )
      goto LABEL_90;
    if ( !(unsigned int)SDDLToSecurityDescriptor(a1, v42, &hMem, v43) )
      goto LABEL_92;
    if ( _wcsicmp(Attribute, &Class) && !(unsigned int)StringCchStartsWithCI(Attribute, AttributeValue) )
    {
      v53 = 2150859183LL;
      v44 = a1;
LABEL_91:
      (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a1 + 72LL))(v44, v53);
LABEL_92:
      AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(&hMem);
      return 0;
    }
    v45 = hMem;
    hMem = 0;
    if ( v45 )
      LocalFree(v45);
LABEL_75:
    v20 = (unsigned int)(v73 + 1);
    v18 = v71;
    v19 = v75;
    goto LABEL_26;
  }
  v21 = 0;
LABEL_168:
  WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x80Cu, L"2060", 0x80070057, 0);
  WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x80Cu, L"2060", 0x80070057, 0);
LABEL_37:
  if ( v21 )
  {
LABEL_38:
    for ( j = 0; ; ++j )
    {
      if ( j == *(_DWORD *)(v21 + 112) )
      {
        v59 = 808;
        v60 = L"808";
        goto LABEL_143;
      }
      v27 = 104LL * j;
      v28 = v27 + *(_QWORD *)(v21 + 120);
      if ( v28 )
      {
        if ( *(_DWORD *)(v28 + 16) == 4 )
        {
          v29 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v28);
          if ( !_wcsnicmp(v29, L"Type", 4u) )
          {
            v30 = (const wchar_t *)FwXmlGetAttributeValue(v27 + *(_QWORD *)(v21 + 120));
            LODWORD(hMem) = 0;
            for ( k = 0; k != *(_DWORD *)(v21 + 112); ++k )
            {
              v32 = 104LL * k;
              v33 = v32 + *(_QWORD *)(v21 + 120);
              if ( v33 )
              {
                if ( *(_DWORD *)(v33 + 16) == 16 )
                {
                  v34 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v33);
                  if ( !_wcsnicmp(v34, L"SupportsFragment", 0x10u) )
                  {
                    v35 = (const wchar_t *)FwXmlGetAttributeValue(v32 + *(_QWORD *)(v21 + 120));
                    if ( !v35 )
                      WSManError(
                        (wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp",
                        0x8Bu,
                        L"139",
                        0x54Fu,
                        0);
                    if ( !_wcsicmp(v35, L"true") || (unsigned int)StringCchEquals(v35, L"1") )
                      LODWORD(hMem) = 1;
                    break;
                  }
                }
              }
              else
              {
                WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
              }
            }
            v36 = 0;
            for ( m = 0; m != *(_DWORD *)(v21 + 112); ++m )
            {
              v38 = 104LL * m;
              v39 = v38 + *(_QWORD *)(v21 + 120);
              if ( v39 )
              {
                if ( *(_DWORD *)(v39 + 16) == 17 )
                {
                  v55 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v39);
                  if ( !_wcsnicmp(v55, L"SupportsFiltering", 0x11u) )
                  {
                    v56 = (const wchar_t *)FwXmlGetAttributeValue(v38 + *(_QWORD *)(v21 + 120));
                    if ( !v56 )
                      WSManError(
                        (wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp",
                        0x8Bu,
                        L"139",
                        0x54Fu,
                        0);
                    if ( !_wcsicmp(v56, L"true") || (unsigned int)StringCchEquals(v56, L"1") )
                      v36 = 1;
                    break;
                  }
                }
              }
              else
              {
                WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
              }
            }
            if ( !v30 )
              WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 0x8Bu, L"139", 0x54Fu, 0);
            if ( _wcsicmp(v30, L"Get") )
            {
              if ( !v30 )
                WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 0x8Bu, L"139", 0x54Fu, 0);
              if ( _wcsicmp(v30, L"Put") )
              {
                if ( !v30 )
                  WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 0x8Bu, L"139", 0x54Fu, 0);
                if ( _wcsicmp(v30, L"Create") )
                {
                  if ( !v30 )
                    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 0x8Bu, L"139", 0x54Fu, 0);
                  if ( _wcsicmp(v30, L"Delete") )
                  {
                    if ( !v30 )
                      WSManError(
                        (wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp",
                        0x8Bu,
                        L"139",
                        0x54Fu,
                        0);
                    if ( _wcsicmp(v30, L"Invoke") )
                    {
                      if ( !v30 )
                        WSManError(
                          (wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp",
                          0x8Bu,
                          L"139",
                          0x54Fu,
                          0);
                      if ( _wcsicmp(v30, L"Enumerate") )
                      {
                        if ( !v30 )
                          WSManError(
                            (wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp",
                            0x8Bu,
                            L"139",
                            0x54Fu,
                            0);
                        if ( _wcsicmp(v30, L"Subscribe") )
                        {
                          if ( !v30 )
                            WSManError(
                              (wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp",
                              0x8Bu,
                              L"139",
                              0x54Fu,
                              0);
                          if ( _wcsicmp(v30, L"Shell") )
                          {
                            if ( !v30 )
                              WSManError(
                                (wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp",
                                0x8Bu,
                                L"139",
                                0x54Fu,
                                0);
                            if ( _wcsicmp(v30, L"Identify") )
                            {
                              v70 = a1;
                              v57 = L"737";
                              v58 = 737;
                              goto LABEL_138;
                            }
                            v46 = 8;
                          }
                          else
                          {
                            v46 = 7;
                            *v84 = 1;
                          }
                        }
                        else
                        {
                          v46 = 6;
                        }
                      }
                      else
                      {
                        v46 = 5;
                      }
                    }
                    else
                    {
                      v46 = 4;
                    }
                  }
                  else
                  {
                    v46 = 3;
                  }
                }
                else
                {
                  v46 = 2;
                }
              }
              else
              {
                v46 = 1;
              }
            }
            else
            {
              v46 = 0;
            }
            if ( *((_DWORD *)&v79 + v46) )
            {
              v68 = *(void (__fastcall **)(struct IRequestContext *, __int64, __int64, const wchar_t *, const unsigned __int16 *))(*(_QWORD *)a1 + 64LL);
              v69 = GetResourceUriAttributeValue(v71);
              v68(a1, 2150858819LL, 1077134535, v30, v69);
              v51 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
              {
                v52 = 53;
                goto LABEL_188;
              }
            }
            else
            {
              *((_DWORD *)&v79 + v46) = 1;
              *((_DWORD *)&v82 + v46) = 1;
              if ( (_DWORD)hMem && v46 - 4 <= 3 )
              {
                (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, const wchar_t *))(*(_QWORD *)a1 + 64LL))(
                  a1,
                  2150858819LL,
                  1077134536,
                  v30);
                v51 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
                {
                  v52 = 54;
                  goto LABEL_188;
                }
              }
              else
              {
                if ( !v36 || v46 - 5 <= 1 )
                {
                  AttributeValue = v77;
                  goto LABEL_75;
                }
                (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, const wchar_t *))(*(_QWORD *)a1 + 64LL))(
                  a1,
                  2150858819LL,
                  1077134537,
                  v30);
                v51 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
                {
                  v52 = 55;
LABEL_188:
                  WPP_SF_S(v51[2], v52, WPP_41b7160f62713ab8e9a46e145cc9941b_Traceguids, v30);
                  return 0;
                }
              }
            }
            return 0;
          }
        }
      }
      else
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
      }
    }
  }
  v59 = 802;
  v60 = L"802";
LABEL_143:
  WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmladditionalvalidation.cpp", v59, v60, 0x54Fu, 0);
  WSManError(
    (wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configxmladditionalvalidation.cpp",
    0x2B2u,
    L"690",
    0x54Fu,
    a1);
  return 0;
}

```

## disassembly

```asm
0x180038050  mov     [rsp-8+arg_18], rbx
0x180038055  push    rbp
0x180038056  push    rsi
0x180038057  push    rdi
0x180038058  push    r12
0x18003805a  push    r13
0x18003805c  push    r14
0x18003805e  push    r15
0x180038060  lea     rbp, [rsp-27h]
0x180038065  sub     rsp, 0C0h
0x18003806c  mov     [rbp+57h+var_40], r8
0x180038070  mov     [rbp+57h+var_98], rdx
0x180038074  mov     rdi, rcx
0x180038077  lea     rbx, WPP_GLOBAL_Control
0x18003807e  mov     rcx, cs:WPP_GLOBAL_Control
0x180038085  cmp     rcx, rbx
0x180038088  jnz     loc_180038553
0x18003808e  xor     r12d, r12d
0x180038091  test    rdi, rdi
0x180038094  jz      loc_180038977
0x18003809a  test    rdx, rdx
0x18003809d  jz      loc_1800389A6
0x1800380a3  mov     ecx, [rdx+80h]
0x1800380a9  mov     [rbp+57h+var_A4], ecx
0x1800380ac  test    ecx, ecx
0x1800380ae  jz      loc_18003898A
0x1800380b4  xorps   xmm0, xmm0
0x1800380b7  movups  [rbp+57h+var_68], xmm0
0x1800380bb  movups  [rbp+57h+var_58], xmm0
0x1800380bf  mov     eax, r12d
0x1800380c2  mov     r14d, 54Fh
0x1800380c8  mov     [rbp+57h+var_AC], eax
0x1800380cb  cmp     eax, ecx
0x1800380cd  jnb     loc_1800383C9
0x1800380d3  cmp     eax, [rdx+80h]
0x1800380d9  jnb     loc_180038872
0x1800380df  imul    rcx, rax, 98h
0x1800380e6  add     rcx, [rdx+88h]
0x1800380ed  mov     [rbp+57h+var_C0], rcx
0x1800380f1  mov     esi, r12d
0x1800380f4  lea     r13, [rcx+78h]
0x1800380f8  mov     r12, r13
0x1800380fb  cmp     esi, [rcx+70h]
0x1800380fe  jz      loc_1800389E2
0x180038104  movsxd  rax, esi
0x180038107  imul    r15, rax, 68h ; 'h'
0x18003810b  lea     r12, [rcx+78h]
0x18003810f  mov     rbx, [r12]
0x180038113  add     rbx, r15
0x180038116  lea     rax, [rbx+30h]
0x18003811a  test    rax, rax
0x18003811d  jz      loc_1800389B9
0x180038123  cmp     dword ptr [rax+10h], 44h ; 'D'
0x180038127  jnz     short loc_180038173
0x180038129  mov     rcx, [rax+8]
0x18003812d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180038131  jz      loc_1800388CC
0x180038137  mov     rax, [rax]
0x18003813a  test    rax, rax
0x18003813d  jz      loc_1800388D4
0x180038143  mov     rax, [rax]
0x180038146  lea     rcx, [rax+rcx*2]; String1
0x18003814a  mov     r8d, 44h ; 'D'; MaxCount
0x180038150  lea     rdx, aHttpSchemasMic_9; "http://schemas.microsoft.com/wbem/wsman"...
0x180038157  call    wcsncmp_0
0x18003815c  test    eax, eax
0x18003815e  jnz     short loc_18003816F
0x180038160  test    rbx, rbx
0x180038163  jz      loc_1800389B9
0x180038169  cmp     dword ptr [rbx+10h], 0Bh
0x18003816d  jz      short loc_180038177
0x18003816f  mov     rcx, [rbp+57h+var_C0]
0x180038173  inc     esi
0x180038175  jmp     short loc_1800380FB
0x180038177  mov     rcx, rbx
0x18003817a  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x18003817f  mov     rcx, rax; String1
0x180038182  mov     r8d, 0Bh; MaxCount
0x180038188  lea     rdx, aResourceuri; "ResourceUri"
0x18003818f  call    cs:__imp__wcsnicmp
0x180038195  test    eax, eax
0x180038197  jnz     short loc_18003816F
0x180038199  mov     rcx, [r12]
0x18003819d  add     rcx, r15
0x1800381a0  call    FwXmlGetAttributeValue
0x1800381a5  mov     r15, rax
0x1800381a8  mov     [rbp+57h+var_A0], rax
0x1800381ac  xor     r12d, r12d
0x1800381af  test    rax, rax
0x1800381b2  jz      loc_18003887A
0x1800381b8  xorps   xmm0, xmm0
0x1800381bb  xor     eax, eax
0x1800381bd  movups  [rbp+57h+var_90], xmm0
0x1800381c1  movups  [rbp+57h+var_80], xmm0
0x1800381c5  mov     [rbp+57h+var_70], eax
0x1800381c8  mov     rdx, [rbp+57h+var_C0]
0x1800381cc  test    rdx, rdx
0x1800381cf  jz      loc_180038DBC
0x1800381d5  mov     ecx, [rdx+80h]
0x1800381db  mov     [rbp+57h+var_A8], ecx
0x1800381de  test    ecx, ecx
0x1800381e0  jz      loc_180038DDC
0x1800381e6  mov     eax, r12d
0x1800381e9  mov     [rbp+57h+var_B0], eax
0x1800381ec  cmp     eax, ecx
0x1800381ee  jnb     loc_1800383AE
0x1800381f4  cmp     eax, [rdx+80h]
0x1800381fa  jnb     loc_180038A12
0x180038200  imul    rbx, rax, 98h
0x180038207  add     rbx, [rdx+88h]
0x18003820e  jz      loc_180038A15
0x180038214  mov     esi, 8
0x180038219  cmp     [rbx+10h], esi
0x18003821c  jnz     short loc_180038298
0x18003821e  mov     rcx, rbx
0x180038221  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x180038226  mov     rcx, rax; String1
0x180038229  mov     r8d, esi; MaxCount
0x18003822c  lea     rdx, aSecurity; "Security"
0x180038233  call    cs:__imp__wcsnicmp
0x180038239  test    eax, eax
0x18003823b  jz      loc_18003840A
0x180038241  cmp     [rbx+10h], esi
0x180038244  jnz     short loc_180038298
0x180038246  mov     rcx, rbx
0x180038249  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x18003824e  mov     rcx, rax; String1
0x180038251  mov     r8d, esi; MaxCount
0x180038254  lea     rdx, aSecurity; "Security"
0x18003825b  call    cs:__imp__wcsnicmp
0x180038261  mov     ecx, r12d
0x180038264  test    eax, eax
0x180038266  setz    cl
0x180038269  test    eax, eax
0x18003826b  jnz     short loc_180038287
0x18003826d  lea     rcx, [rbx+30h]
0x180038271  test    rcx, rcx
0x180038274  jz      loc_180038A61
0x18003827a  cmp     dword ptr [rcx+10h], 44h ; 'D'
0x18003827e  jz      loc_1800385F2
0x180038284  mov     ecx, r12d
0x180038287  test    ecx, ecx
0x180038289  jnz     loc_18003840A
0x18003828f  test    rbx, rbx
0x180038292  jz      loc_180038893
0x180038298  mov     esi, r12d
0x18003829b  cmp     esi, [rbx+70h]
0x18003829e  jz      loc_180038DAB
0x1800382a4  movsxd  rax, esi
0x1800382a7  imul    r15, rax, 68h ; 'h'
0x1800382ab  mov     rcx, [rbx+78h]
0x1800382af  add     rcx, r15
0x1800382b2  jz      loc_180038AA6
0x1800382b8  cmp     dword ptr [rcx+10h], 4
0x1800382bc  jz      short loc_1800382C2
0x1800382be  inc     esi
0x1800382c0  jmp     short loc_18003829B
0x1800382c2  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x1800382c7  mov     rcx, rax; String1
0x1800382ca  mov     r8d, 4; MaxCount
0x1800382d0  lea     rdx, aType_1; "Type"
0x1800382d7  call    cs:__imp__wcsnicmp
0x1800382dd  test    eax, eax
0x1800382df  jnz     short loc_1800382BE
0x1800382e1  mov     rcx, [rbx+78h]
0x1800382e5  add     rcx, r15
0x1800382e8  call    FwXmlGetAttributeValue
0x1800382ed  mov     rsi, rax
0x1800382f0  mov     dword ptr [rbp+57h+hMem], r12d
0x1800382f4  mov     r15d, r12d
0x1800382f7  cmp     r15d, [rbx+70h]
0x1800382fb  jz      short loc_180038378
0x1800382fd  movsxd  rcx, r15d
0x180038300  imul    r12, rcx, 68h ; 'h'
0x180038304  mov     rcx, [rbx+78h]
0x180038308  add     rcx, r12
0x18003830b  jz      loc_180038ACB
0x180038311  cmp     dword ptr [rcx+10h], 10h
0x180038315  jz      short loc_18003831F
0x180038317  xor     r12d, r12d
0x18003831a  inc     r15d
0x18003831d  jmp     short loc_1800382F7
0x18003831f  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x180038324  mov     rcx, rax; String1
0x180038327  mov     r8d, 10h; MaxCount
0x18003832d  lea     rdx, aSupportsfragme; "SupportsFragment"
0x180038334  call    cs:__imp__wcsnicmp
0x18003833a  test    eax, eax
0x18003833c  jnz     short loc_180038317
0x18003833e  mov     rcx, [rbx+78h]
0x180038342  add     rcx, r12
0x180038345  call    FwXmlGetAttributeValue
0x18003834a  mov     r15, rax
0x18003834d  xor     r12d, r12d
0x180038350  test    rax, rax
0x180038353  jz      loc_180038AF3
0x180038359  lea     rdx, aTrue; "true"
0x180038360  mov     rcx, r15; String1
0x180038363  call    cs:__imp__wcsicmp
0x180038369  test    eax, eax
0x18003836b  jnz     loc_180038B18
0x180038371  mov     dword ptr [rbp+57h+hMem], 1
0x180038378  mov     r13d, r12d
0x18003837b  mov     r15d, r12d
0x18003837e  cmp     r15d, [rbx+70h]
0x180038382  jz      loc_1800386FB
0x180038388  movsxd  rax, r15d
0x18003838b  imul    r12, rax, 68h ; 'h'
0x18003838f  mov     rcx, [rbx+78h]
0x180038393  add     rcx, r12
0x180038396  jz      loc_180038B34
0x18003839c  cmp     dword ptr [rcx+10h], 11h
0x1800383a0  jz      loc_18003869F
0x1800383a6  xor     r12d, r12d
0x1800383a9  inc     r15d
0x1800383ac  jmp     short loc_18003837E
0x1800383ae  cmp     dword ptr [rbp+57h+var_80+0Ch], r12d
0x1800383b2  jnz     loc_1800384CF
0x1800383b8  mov     eax, [rbp+57h+var_AC]
0x1800383bb  inc     eax
0x1800383bd  mov     rdx, [rbp+57h+var_98]
0x1800383c1  mov     ecx, [rbp+57h+var_A4]
0x1800383c4  jmp     loc_1800380C8
0x1800383c9  cmp     dword ptr [rbp+57h+var_58+0Ch], r12d
0x1800383cd  jnz     loc_180038619
0x1800383d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800383da  lea     rax, WPP_GLOBAL_Control
0x1800383e1  cmp     rcx, rax
0x1800383e4  jnz     loc_180038DF5
0x1800383ea  mov     eax, 1
0x1800383ef  mov     rbx, [rsp+0F0h+arg_18]
0x1800383f7  add     rsp, 0C0h
0x1800383fe  pop     r15
0x180038400  pop     r14
0x180038402  pop     r13
0x180038404  pop     r12
0x180038406  pop     rdi
0x180038407  pop     rsi
0x180038408  pop     rbp
0x180038409  retn
0x18003840a  mov     [rbp+57h+hMem], r12
0x18003840e  lea     rdx, aUri_0; "Uri"
0x180038415  mov     rcx, rbx
0x180038418  call    GetAttribute
0x18003841d  mov     rsi, rax
0x180038420  test    rax, rax
0x180038423  jz      loc_1800385CD
0x180038429  lea     rdx, aSddl; "Sddl"
0x180038430  mov     rcx, rbx
0x180038433  call    GetAttribute
0x180038438  mov     rcx, rdi; struct IRequestContext *
0x18003843b  test    rax, rax
0x18003843e  jz      loc_1800385D0
0x180038444  lea     r8, [rbp+57h+hMem]; void **
0x180038448  mov     rdx, rax; unsigned __int16 *
0x18003844b  call    ?SDDLToSecurityDescriptor@@YAHPEAVIRequestContext@@PEBGPEAPEAXH@Z; SDDLToSecurityDescriptor(IRequestContext *,ushort const *,void * *,int)
0x180038450  test    eax, eax
0x180038452  jz      loc_1800385E2
0x180038458  lea     rdx, Class; String2
0x18003845f  mov     rcx, rsi; String1
0x180038462  call    cs:__imp__wcsicmp
0x180038468  test    eax, eax
0x18003846a  jnz     loc_180038A86
0x180038470  mov     rcx, [rbp+57h+hMem]; hMem
0x180038474  mov     [rbp+57h+hMem], r12
0x180038478  test    rcx, rcx
0x18003847b  jz      short loc_1800384BE
0x18003847d  call    cs:__imp_LocalFree
0x180038483  jmp     short loc_1800384BE
0x180038485  mov     ecx, 6
0x18003848a  mov     eax, ecx
0x18003848c  cmp     dword ptr [rbp+rax*4+57h+var_90], r12d
0x180038491  jnz     loc_180038D57
0x180038497  mov     dword ptr [rbp+rax*4+57h+var_90], 1
0x18003849f  mov     dword ptr [rbp+rax*4+57h+var_68], 1
0x1800384a7  cmp     dword ptr [rbp+57h+hMem], r12d
0x1800384ab  jnz     loc_180038CE6
0x1800384b1  test    r13d, r13d
0x1800384b4  jnz     loc_18003857E
0x1800384ba  mov     r15, [rbp+57h+var_A0]
0x1800384be  mov     eax, [rbp+57h+var_B0]
0x1800384c1  inc     eax
0x1800384c3  mov     rdx, [rbp+57h+var_C0]
0x1800384c7  mov     ecx, [rbp+57h+var_A8]
0x1800384ca  jmp     loc_1800381E9
0x1800384cf  cmp     dword ptr [rbp+57h+var_90], r12d
0x1800384d3  jnz     short loc_1800384FD
0x1800384d5  cmp     dword ptr [rbp+57h+var_90+4], r12d
0x1800384d9  jnz     short loc_1800384FD
0x1800384db  cmp     dword ptr [rbp+57h+var_90+8], r12d
0x1800384df  jnz     short loc_1800384FD
0x1800384e1  cmp     dword ptr [rbp+57h+var_90+0Ch], r12d
0x1800384e5  jnz     short loc_1800384FD
0x1800384e7  cmp     dword ptr [rbp+57h+var_80], r12d
0x1800384eb  jnz     short loc_1800384FD
0x1800384ed  cmp     dword ptr [rbp+57h+var_80+4], r12d
0x1800384f1  jnz     short loc_1800384FD
0x1800384f3  cmp     dword ptr [rbp+57h+var_80+8], r12d
0x1800384f7  jz      loc_1800383B8
0x1800384fd  mov     rax, [rdi]
  ... truncated ...
```
