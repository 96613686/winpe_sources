# ShellPluginQuota::InitializePluginQuota(_FWXML_ELEMENT *,IRequestContext &)

- ea: `0x18000c530`
- end: `0x18000d24b`
- name: `?InitializePluginQuota@ShellPluginQuota@@UEAA_NPEAU_FWXML_ELEMENT@@AEAVIRequestContext@@@Z`
- size: `3355`
- prototype: `bool __fastcall(ShellPluginQuota *__hidden this, struct _FWXML_ELEMENT *, struct IRequestContext *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005d10`
- `0x18000c530`
- `0x18000d780`
- `0x18003a610`
- `0x18003c640`
- `0x180112380`
- `0x1801123a8`
- `0x1801ba182`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_wtoi64` at `0x18000c689`
- `msvcrt!_wtoi64` at `0x18000c801`
- `msvcrt!_wtoi64` at `0x18000c974`
- `msvcrt!_wtoi64` at `0x18000cae7`
- `msvcrt!_wtoi64` at `0x18000cc5a`
- `msvcrt!_wtoi64` at `0x18000cdcd`
- `msvcrt!_wtoi64` at `0x18000cf3e`
- `msvcrt!_wtoi64` at `0x18000d0ad`
- `msvcrt!_wtoi64` at `0x18000c689`
- `msvcrt!_wtoi64` at `0x18000c801`
- `msvcrt!_wtoi64` at `0x18000c974`
- `msvcrt!_wtoi64` at `0x18000cae7`
- `msvcrt!_wtoi64` at `0x18000cc5a`
- `msvcrt!_wtoi64` at `0x18000cdcd`
- `msvcrt!_wtoi64` at `0x18000cf3e`
- `msvcrt!_wtoi64` at `0x18000d0ad`
- `msvcrt!_wcsnicmp` at `0x18000c5fe`
- `msvcrt!_wcsnicmp` at `0x18000c772`
- `msvcrt!_wcsnicmp` at `0x18000c8e8`
- `msvcrt!_wcsnicmp` at `0x18000ca5b`
- `msvcrt!_wcsnicmp` at `0x18000cbce`
- `msvcrt!_wcsnicmp` at `0x18000cd41`
- `msvcrt!_wcsnicmp` at `0x18000ceb2`
- `msvcrt!_wcsnicmp` at `0x18000d025`
- `msvcrt!_wcsnicmp` at `0x18000c5fe`
- `msvcrt!_wcsnicmp` at `0x18000c772`
- `msvcrt!_wcsnicmp` at `0x18000c8e8`
- `msvcrt!_wcsnicmp` at `0x18000ca5b`
- `msvcrt!_wcsnicmp` at `0x18000cbce`
- `msvcrt!_wcsnicmp` at `0x18000cd41`
- `msvcrt!_wcsnicmp` at `0x18000ceb2`
- `msvcrt!_wcsnicmp` at `0x18000d025`

## string_xrefs

- `0x18000cd34`: `MaxConcurrentCommandsPerShell`
- `0x18000c665`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18000c7dd`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18000c93e`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18000cab1`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18000cc24`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18000cd97`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18000cf08`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18000d07b`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`

## pseudocode

```c
char __fastcall ShellPluginQuota::InitializePluginQuota(
        ShellPluginQuota *this,
        struct _FWXML_ELEMENT *a2,
        struct IRequestContext *a3)
{
  __int64 ElementNamespaceUrl; // rax
  __int64 v7; // rbx
  const wchar_t *v8; // rdx
  int i; // edi
  __int64 v10; // r14
  __int64 v11; // rsi
  const wchar_t **v12; // rax
  __int64 v13; // rcx
  const wchar_t *v14; // rcx
  const wchar_t *v15; // rax
  const wchar_t *v16; // rax
  const wchar_t *AttributeValue; // rax
  unsigned int j; // edx
  wchar_t v19; // r8
  __int64 v20; // rax
  const wchar_t *v21; // rdx
  __int64 v22; // rdi
  int v23; // esi
  __int64 v24; // r14
  __int64 v25; // rbx
  const wchar_t **v26; // rax
  __int64 v27; // rcx
  const wchar_t *v28; // rcx
  const wchar_t *v29; // rax
  const wchar_t *v30; // rax
  const wchar_t *v31; // rax
  unsigned int k; // edx
  wchar_t v33; // r8
  __int64 v34; // rax
  const wchar_t *v35; // rdx
  __int64 v36; // rsi
  int v37; // edi
  __int64 v38; // r14
  __int64 v39; // rbx
  const wchar_t **v40; // rax
  __int64 v41; // rcx
  const wchar_t *v42; // rcx
  const wchar_t *v43; // rax
  const wchar_t *v44; // rax
  const wchar_t *v45; // rax
  unsigned int m; // edx
  wchar_t v47; // r8
  __int64 v48; // rax
  const wchar_t *v49; // rdx
  __int64 v50; // rdi
  int v51; // esi
  __int64 v52; // r14
  __int64 v53; // rbx
  const wchar_t **v54; // rax
  __int64 v55; // rcx
  const wchar_t *v56; // rcx
  const wchar_t *v57; // rax
  const wchar_t *v58; // rax
  const wchar_t *v59; // rax
  unsigned int n; // edx
  wchar_t v61; // r8
  __int64 v62; // rax
  const wchar_t *v63; // rdx
  __int64 v64; // rsi
  int v65; // edi
  __int64 v66; // r14
  __int64 v67; // rbx
  const wchar_t **v68; // rax
  __int64 v69; // rcx
  const wchar_t *v70; // rcx
  const wchar_t *v71; // rax
  const wchar_t *v72; // rax
  const wchar_t *v73; // rax
  unsigned int ii; // edx
  wchar_t v75; // r8
  __int64 v76; // rax
  const wchar_t *v77; // rdx
  __int64 v78; // rdi
  int v79; // esi
  __int64 v80; // r14
  __int64 v81; // rbx
  const wchar_t **v82; // rax
  __int64 v83; // rcx
  const wchar_t *v84; // rcx
  const wchar_t *v85; // rax
  const wchar_t *v86; // rax
  const wchar_t *v87; // rax
  unsigned int jj; // edx
  wchar_t v89; // r8
  __int64 v90; // rax
  const wchar_t *v91; // rdx
  __int64 v92; // rsi
  int v93; // edi
  __int64 v94; // r14
  __int64 v95; // rbx
  const wchar_t **v96; // rax
  __int64 v97; // rcx
  const wchar_t *v98; // rcx
  const wchar_t *v99; // rax
  const wchar_t *v100; // rax
  size_t v101; // r8
  const wchar_t *v102; // rax
  unsigned int kk; // edx
  wchar_t v104; // r8
  __int64 v105; // rax
  const wchar_t *v106; // rdx
  __int64 v107; // rsi
  int v108; // edi
  __int64 v109; // r14
  __int64 v110; // rbx
  const wchar_t **v111; // rax
  __int64 v112; // rcx
  const wchar_t *v113; // rcx
  const wchar_t *v114; // rax
  const wchar_t *v115; // rax
  const wchar_t *v116; // rax
  unsigned int mm; // edx
  wchar_t v118; // r8
  __int64 v119; // rax
  _QWORD *v121; // rcx
  __int64 v122; // rdx
  wchar_t *String2; // [rsp+78h] [rbp+10h]

  ElementNamespaceUrl = FwXmlGetElementNamespaceUrl(a2);
  v7 = -1;
  String2 = (wchar_t *)ElementNamespaceUrl;
  v8 = (const wchar_t *)ElementNamespaceUrl;
  do
    ++v7;
  while ( *(_WORD *)(ElementNamespaceUrl + 2 * v7) );
  for ( i = 0; ; ++i )
  {
    if ( i == *((_DWORD *)a2 + 28) )
      goto LABEL_255;
    v10 = 104LL * i;
    v11 = v10 + *((_QWORD *)a2 + 15);
    v12 = (const wchar_t **)(v11 + 48);
    if ( v11 == -48 )
      goto LABEL_22;
    if ( *(_DWORD *)(v11 + 64) != (_DWORD)v7 )
      continue;
    v13 = *(_QWORD *)(v11 + 56);
    if ( v13 == -1 )
    {
      v14 = *v12;
    }
    else
    {
      v15 = *v12;
      v14 = v15 ? (const wchar_t *)(*(_QWORD *)v15 + 2 * v13) : 0LL;
    }
    if ( !wcsncmp_0(v14, v8, (unsigned int)v7) )
      break;
LABEL_23:
    v8 = String2;
  }
  if ( !v11 )
  {
LABEL_22:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 522, L"522", 0x54Fu, 0);
    goto LABEL_23;
  }
  if ( *(_DWORD *)(v11 + 16) != 16 )
    goto LABEL_23;
  v16 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v11);
  if ( _wcsnicmp(v16, L"MaxIdleTimeoutms", 0x10u) )
    goto LABEL_23;
  AttributeValue = (const wchar_t *)FwXmlGetAttributeValue(v10 + *((_QWORD *)a2 + 15));
  if ( !AttributeValue )
    goto LABEL_255;
  for ( j = 0; ; ++j )
  {
    v19 = AttributeValue[j];
    if ( !v19 )
      break;
    if ( j > 0xA || (unsigned __int16)(v19 - 48) > 9u )
      goto LABEL_255;
  }
  if ( j > 0xA || (v20 = _wtoi64(AttributeValue), v20 > 0xFFFFFFFFLL) )
  {
LABEL_255:
    v121 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
      goto LABEL_259;
    v122 = 10;
    goto LABEL_258;
  }
  *((_DWORD *)this + 5) = v20;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_b96a2b66f0f03e66f566abfd93da5cbb_Traceguids,
      (unsigned int)v20);
  v21 = String2;
  v22 = -1;
  do
    ++v22;
  while ( String2[v22] );
  v23 = 0;
  while ( 2 )
  {
    if ( v23 == *((_DWORD *)a2 + 28) )
      goto LABEL_252;
    v24 = 104LL * v23;
    v25 = v24 + *((_QWORD *)a2 + 15);
    v26 = (const wchar_t **)(v25 + 48);
    if ( v25 == -48 )
      goto LABEL_51;
    if ( *(_DWORD *)(v25 + 64) != (_DWORD)v22 )
    {
LABEL_53:
      ++v23;
      continue;
    }
    break;
  }
  v27 = *(_QWORD *)(v25 + 56);
  if ( v27 == -1 )
  {
    v28 = *v26;
  }
  else
  {
    v29 = *v26;
    if ( v29 )
      v28 = (const wchar_t *)(*(_QWORD *)v29 + 2 * v27);
    else
      v28 = 0;
  }
  if ( wcsncmp_0(v28, v21, (unsigned int)v22) )
  {
LABEL_52:
    v21 = String2;
    goto LABEL_53;
  }
  if ( !v25 )
  {
LABEL_51:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 522, L"522", 0x54Fu, 0);
    goto LABEL_52;
  }
  if ( *(_DWORD *)(v25 + 16) != 18 )
    goto LABEL_52;
  v30 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v25);
  if ( _wcsnicmp(v30, L"MaxConcurrentUsers", 0x12u) )
    goto LABEL_52;
  v31 = (const wchar_t *)FwXmlGetAttributeValue(v24 + *((_QWORD *)a2 + 15));
  if ( !v31 )
    goto LABEL_252;
  for ( k = 0; ; ++k )
  {
    v33 = v31[k];
    if ( !v33 )
      break;
    if ( k > 0xA || (unsigned __int16)(v33 - 48) > 9u )
      goto LABEL_252;
  }
  if ( k > 0xA || (v34 = _wtoi64(v31), v34 > 0xFFFFFFFFLL) )
  {
LABEL_252:
    v121 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
      goto LABEL_259;
    v122 = 12;
    goto LABEL_258;
  }
  *((_DWORD *)this + 2) = v34;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_b96a2b66f0f03e66f566abfd93da5cbb_Traceguids,
      (unsigned int)v34);
  v35 = String2;
  v36 = -1;
  do
    ++v36;
  while ( String2[v36] );
  v37 = 0;
  while ( 2 )
  {
    if ( v37 == *((_DWORD *)a2 + 28) )
      goto LABEL_249;
    v38 = 104LL * v37;
    v39 = v38 + *((_QWORD *)a2 + 15);
    v40 = (const wchar_t **)(v39 + 48);
    if ( v39 == -48 )
      goto LABEL_80;
    if ( *(_DWORD *)(v39 + 64) != (_DWORD)v36 )
    {
LABEL_82:
      ++v37;
      continue;
    }
    break;
  }
  v41 = *(_QWORD *)(v39 + 56);
  if ( v41 == -1 )
  {
    v42 = *v40;
  }
  else
  {
    v43 = *v40;
    if ( v43 )
      v42 = (const wchar_t *)(*(_QWORD *)v43 + 2 * v41);
    else
      v42 = 0;
  }
  if ( wcsncmp_0(v42, v35, (unsigned int)v36) )
  {
LABEL_81:
    v35 = String2;
    goto LABEL_82;
  }
  if ( !v39 )
  {
LABEL_80:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 522, L"522", 0x54Fu, 0);
    goto LABEL_81;
  }
  if ( *(_DWORD *)(v39 + 16) != 13 )
    goto LABEL_81;
  v44 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v39);
  if ( _wcsnicmp(v44, L"IdleTimeoutms", 0xDu) )
    goto LABEL_81;
  v45 = (const wchar_t *)FwXmlGetAttributeValue(v38 + *((_QWORD *)a2 + 15));
  if ( !v45 )
    goto LABEL_249;
  for ( m = 0; ; ++m )
  {
    v47 = v45[m];
    if ( !v47 )
      break;
    if ( m > 0xA || (unsigned __int16)(v47 - 48) > 9u )
      goto LABEL_249;
  }
  if ( m > 0xA || (v48 = _wtoi64(v45), v48 > 0xFFFFFFFFLL) )
  {
LABEL_249:
    v121 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
      goto LABEL_259;
    v122 = 14;
    goto LABEL_258;
  }
  *((_DWORD *)this + 4) = v48;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      WPP_b96a2b66f0f03e66f566abfd93da5cbb_Traceguids,
      (unsigned int)v48);
  v49 = String2;
  v50 = -1;
  do
    ++v50;
  while ( String2[v50] );
  v51 = 0;
  while ( 2 )
  {
    if ( v51 == *((_DWORD *)a2 + 28) )
      goto LABEL_246;
    v52 = 104LL * v51;
    v53 = v52 + *((_QWORD *)a2 + 15);
    v54 = (const wchar_t **)(v53 + 48);
    if ( v53 == -48 )
      goto LABEL_109;
    if ( *(_DWORD *)(v53 + 64) != (_DWORD)v50 )
    {
LABEL_111:
      ++v51;
      continue;
    }
    break;
  }
  v55 = *(_QWORD *)(v53 + 56);
  if ( v55 == -1 )
  {
    v56 = *v54;
  }
  else
  {
    v57 = *v54;
    if ( v57 )
      v56 = (const wchar_t *)(*(_QWORD *)v57 + 2 * v55);
    else
      v56 = 0;
  }
  if ( wcsncmp_0(v56, v49, (unsigned int)v50) )
  {
LABEL_110:
    v49 = String2;
    goto LABEL_111;
  }
  if ( !v53 )
  {
LABEL_109:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 522, L"522", 0x54Fu, 0);
    goto LABEL_110;
  }
  if ( *(_DWORD *)(v53 + 16) != 20 )
    goto LABEL_110;
  v58 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v53);
  if ( _wcsnicmp(v58, L"MaxProcessesPerShell", 0x14u) )
    goto LABEL_110;
  v59 = (const wchar_t *)FwXmlGetAttributeValue(v52 + *((_QWORD *)a2 + 15));
  if ( !v59 )
    goto LABEL_246;
  for ( n = 0; ; ++n )
  {
    v61 = v59[n];
    if ( !v61 )
      break;
    if ( n > 0xA || (unsigned __int16)(v61 - 48) > 9u )
      goto LABEL_246;
  }
  if ( n > 0xA || (v62 = _wtoi64(v59), v62 > 0xFFFFFFFFLL) )
  {
LABEL_246:
    v121 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
      goto LABEL_259;
    v122 = 16;
    goto LABEL_258;
  }
  *((_DWORD *)this + 6) = v62;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      WPP_b96a2b66f0f03e66f566abfd93da5cbb_Traceguids,
      (unsigned int)v62);
  v63 = String2;
  v64 = -1;
  do
    ++v64;
  while ( String2[v64] );
  v65 = 0;
  while ( 2 )
  {
    if ( v65 == *((_DWORD *)a2 + 28) )
      goto LABEL_243;
    v66 = 104LL * v65;
    v67 = v66 + *((_QWORD *)a2 + 15);
    v68 = (const wchar_t **)(v67 + 48);
    if ( v67 == -48 )
      goto LABEL_138;
    if ( *(_DWORD *)(v67 + 64) != (_DWORD)v64 )
    {
LABEL_140:
      ++v65;
      continue;
    }
    break;
  }
  v69 = *(_QWORD *)(v67 + 56);
  if ( v69 == -1 )
  {
    v70 = *v68;
  }
  else
  {
    v71 = *v68;
    if ( v71 )
      v70 = (const wchar_t *)(*(_QWORD *)v71 + 2 * v69);
    else
      v70 = 0;
  }
  if ( wcsncmp_0(v70, v63, (unsigned int)v64) )
  {
LABEL_139:
    v63 = String2;
    goto LABEL_140;
  }
  if ( !v67 )
  {
LABEL_138:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 522, L"522", 0x54Fu, 0);
    goto LABEL_139;
  }
  if ( *(_DWORD *)(v67 + 16) != 19 )
    goto LABEL_139;
  v72 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v67);
  if ( _wcsnicmp(v72, L"MaxMemoryPerShellMB", 0x13u) )
    goto LABEL_139;
  v73 = (const wchar_t *)FwXmlGetAttributeValue(v66 + *((_QWORD *)a2 + 15));
  if ( !v73 )
    goto LABEL_243;
  for ( ii = 0; ; ++ii )
  {
    v75 = v73[ii];
    if ( !v75 )
      break;
    if ( ii > 0xA || (unsigned __int16)(v75 - 48) > 9u )
      goto LABEL_243;
  }
  if ( ii > 0xA || (v76 = _wtoi64(v73), v76 > 0xFFFFFFFFLL) )
  {
LABEL_243:
    v121 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
      goto LABEL_259;
    v122 = 18;
    goto LABEL_258;
  }
  *((_DWORD *)this + 7) = v76;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      WPP_b96a2b66f0f03e66f566abfd93da5cbb_Traceguids,
      (unsigned int)v76);
  v77 = String2;
  v78 = -1;
  do
    ++v78;
  while ( String2[v78] );
  v79 = 0;
  while ( 2 )
  {
    if ( v79 == *((_DWORD *)a2 + 28) )
      goto LABEL_240;
    v80 = 104LL * v79;
    v81 = v80 + *((_QWORD *)a2 + 15);
    v82 = (const wchar_t **)(v81 + 48);
    if ( v81 == -48 )
      goto LABEL_167;
    if ( *(_DWORD *)(v81 + 64) != (_DWORD)v78 )
    {
LABEL_169:
      ++v79;
      continue;
    }
    break;
  }
  v83 = *(_QWORD *)(v81 + 56);
  if ( v83 == -1 )
  {
    v84 = *v82;
  }
  else
  {
    v85 = *v82;
    if ( v85 )
      v84 = (const wchar_t *)(*(_QWORD *)v85 + 2 * v83);
    else
      v84 = 0;
  }
  if ( wcsncmp_0(v84, v77, (unsigned int)v78) )
  {
LABEL_168:
    v77 = String2;
    goto LABEL_169;
  }
  if ( !v81 )
  {
LABEL_167:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 522, L"522", 0x54Fu, 0);
    goto LABEL_168;
  }
  if ( *(_DWORD *)(v81 + 16) != 29 )
    goto LABEL_168;
  v86 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v81);
  if ( _wcsnicmp(v86, L"MaxConcurrentCommandsPerShell", 0x1Du) )
    goto LABEL_168;
  v87 = (const wchar_t *)FwXmlGetAttributeValue(v80 + *((_QWORD *)a2 + 15));
  if ( !v87 )
    goto LABEL_240;
  for ( jj = 0; ; ++jj )
  {
    v89 = v87[jj];
    if ( !v89 )
      break;
    if ( jj > 0xA || (unsigned __int16)(v89 - 48) > 9u )
      goto LABEL_240;
  }
  if ( jj > 0xA || (v90 = _wtoi64(v87), v90 > 0xFFFFFFFFLL) )
  {
LABEL_240:
    v121 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
      goto LABEL_259;
    v122 = 20;
LABEL_258:
    WPP_SF_(v121[2], v122, WPP_b96a2b66f0f03e66f566abfd93da5cbb_Traceguids);
    goto LABEL_259;
  }
  *((_DWORD *)this + 9) = v90;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      WPP_b96a2b66f0f03e66f566abfd93da5cbb_Traceguids,
      (unsigned int)v90);
  v91 = String2;
  v92 = -1;
  do
    ++v92;
  while ( String2[v92] );
  v93 = 0;
  while ( 2 )
  {
    if ( v93 == *((_DWORD *)a2 + 28) )
      goto LABEL_237;
    v94 = 104LL * v93;
    v95 = v94 + *((_QWORD *)a2 + 15);
    v96 = (const wchar_t **)(v95 + 48);
    if ( v95 == -48 )
      goto LABEL_196;
    if ( *(_DWORD *)(v95 + 64) != (_DWORD)v92 )
    {
LABEL_198:
      ++v93;
      continue;
    }
    break;
  }
  v97 = *(_QWORD *)(v95 + 56);
  if ( v97 == -1 )
  {
    v98 = *v96;
  }
  else
  {
    v99 = *v96;
    if ( v99 )
      v98 = (const wchar_t *)(*(_QWORD *)v99 + 2 * v97);
    else
      v98 = 0;
  }
  if ( wcsncmp_0(v98, v91, (unsigned int)v92) )
  {
LABEL_197:
    v91 = String2;
    goto LABEL_198;
  }
  if ( !v95 )
  {
LABEL_196:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 522, L"522", 0x54Fu, 0);
    goto LABEL_197;
  }
  if ( *(_DWORD *)(v95 + 16) != 9 )
    goto LABEL_197;
  v100 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v95);
  if ( _wcsnicmp(v100, L"MaxShells", v101) )
    goto LABEL_197;
  v102 = (const wchar_t *)FwXmlGetAttributeValue(v94 + *((_QWORD *)a2 + 15));
  if ( v102 )
  {
    for ( kk = 0; ; ++kk )
    {
      v104 = v102[kk];
      if ( !v104 )
        break;
      if ( kk > 0xA || (unsigned __int16)(v104 - 48) > 9u )
        goto LABEL_237;
    }
    if ( kk <= 0xA )
    {
      v105 = _wtoi64(v102);
      if ( v105 <= 0xFFFFFFFFLL )
      {
        *((_DWORD *)this + 10) = v105;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            WPP_b96a2b66f0f03e66f566abfd93da5cbb_Traceguids,
            (unsigned int)v105);
        v106 = String2;
        v107 = -1;
        do
          ++v107;
        while ( String2[v107] );
        v108 = 0;
        while ( 2 )
        {
          if ( v108 == *((_DWORD *)a2 + 28) )
          {
LABEL_234:
            v121 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
            {
              v122 = 24;
              goto LABEL_258;
            }
            goto LABEL_259;
          }
          v109 = 104LL * v108;
          v110 = v109 + *((_QWORD *)a2 + 15);
          v111 = (const wchar_t **)(v110 + 48);
          if ( v110 != -48 )
          {
            if ( *(_DWORD *)(v110 + 64) != (_DWORD)v107 )
              goto LABEL_227;
            v112 = *(_QWORD *)(v110 + 56);
            if ( v112 == -1 )
            {
              v113 = *v111;
            }
            else
            {
              v114 = *v111;
              if ( v114 )
                v113 = (const wchar_t *)(*(_QWORD *)v114 + 2 * v112);
              else
                v113 = 0;
            }
            if ( wcsncmp_0(v113, v106, (unsigned int)v107) )
              goto LABEL_226;
            if ( v110 )
            {
              if ( *(_DWORD *)(v110 + 16) == 16 )
              {
                v115 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v110);
                if ( !_wcsnicmp(v115, L"MaxShellsPerUser", 0x10u) )
                {
                  v116 = (const wchar_t *)FwXmlGetAttributeValue(v109 + *((_QWORD *)a2 + 15));
                  if ( v116 )
                  {
                    for ( mm = 0; ; ++mm )
                    {
                      v118 = v116[mm];
                      if ( !v118 )
                        break;
                      if ( mm > 0xA || (unsigned __int16)(v118 - 48) > 9u )
                        goto LABEL_234;
                    }
                    if ( mm <= 0xA )
                    {
                      v119 = _wtoi64(v116);
                      if ( v119 <= 0xFFFFFFFFLL )
                      {
                        *((_DWORD *)this + 8) = v119;
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
                        {
                          WPP_SF_d(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            25,
                            WPP_b96a2b66f0f03e66f566abfd93da5cbb_Traceguids,
                            (unsigned int)v119);
                        }
                        return 1;
                      }
                    }
                  }
                  goto LABEL_234;
                }
              }
LABEL_226:
              v106 = String2;
LABEL_227:
              ++v108;
              continue;
            }
          }
          break;
        }
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 522, L"522", 0x54Fu, 0);
        goto LABEL_226;
      }
    }
  }
LABEL_237:
  v121 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
  {
    v122 = 22;
    goto LABEL_258;
  }
LABEL_259:
  (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a3 + 88LL))(a3, 1359);
  return 0;
}

```

## disassembly

```asm
0x18000c530  mov     [rsp+arg_10], rbx
0x18000c535  mov     [rsp+arg_0], rcx
0x18000c53a  push    rbp
0x18000c53b  push    rsi
0x18000c53c  push    rdi
0x18000c53d  push    r12
0x18000c53f  push    r13
0x18000c541  push    r14
0x18000c543  push    r15
0x18000c545  sub     rsp, 30h
0x18000c549  mov     rbp, rcx
0x18000c54c  mov     r15, r8
0x18000c54f  mov     rcx, rdx; struct IRequestContext *
0x18000c552  mov     r13, rdx
0x18000c555  call    FwXmlGetElementNamespaceUrl
0x18000c55a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000c55e  mov     [rsp+68h+String2], rax
0x18000c563  xor     r12d, r12d
0x18000c566  mov     rdx, rax; String2
0x18000c569  inc     rbx
0x18000c56c  cmp     [rax+rbx*2], r12w
0x18000c571  jnz     short loc_18000C569
0x18000c573  mov     edi, r12d
0x18000c576  cmp     edi, [r13+70h]
0x18000c57a  jz      loc_18000D1EC
0x18000c580  mov     rsi, [r13+78h]
0x18000c584  movsxd  rax, edi
0x18000c587  imul    r14, rax, 68h ; 'h'
0x18000c58b  add     rsi, r14
0x18000c58e  lea     rax, [rsi+30h]
0x18000c592  test    rax, rax
0x18000c595  jz      loc_18000C64E
0x18000c59b  cmp     [rax+10h], ebx
0x18000c59e  jnz     loc_18000C676
0x18000c5a4  mov     rcx, [rax+8]
0x18000c5a8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c5ac  jnz     short loc_18000C5B3
0x18000c5ae  mov     rcx, [rax]
0x18000c5b1  jmp     short loc_18000C5C7
0x18000c5b3  mov     rax, [rax]
0x18000c5b6  test    rax, rax
0x18000c5b9  jnz     short loc_18000C5C0
0x18000c5bb  mov     rcx, r12
0x18000c5be  jmp     short loc_18000C5C7
0x18000c5c0  mov     rax, [rax]
0x18000c5c3  lea     rcx, [rax+rcx*2]; String1
0x18000c5c7  mov     r8d, ebx; MaxCount
0x18000c5ca  call    wcsncmp_0
0x18000c5cf  test    eax, eax
0x18000c5d1  jnz     loc_18000C671
0x18000c5d7  test    rsi, rsi
0x18000c5da  jz      short loc_18000C64E
0x18000c5dc  cmp     dword ptr [rsi+10h], 10h
0x18000c5e0  jnz     loc_18000C671
0x18000c5e6  mov     rcx, rsi
0x18000c5e9  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x18000c5ee  mov     rcx, rax; String1
0x18000c5f1  lea     rdx, aMaxidletimeout_0; "MaxIdleTimeoutms"
0x18000c5f8  mov     r8d, 10h; MaxCount
0x18000c5fe  call    cs:__imp__wcsnicmp
0x18000c604  test    eax, eax
0x18000c606  jnz     short loc_18000C671
0x18000c608  mov     rcx, [r13+78h]
0x18000c60c  add     rcx, r14
0x18000c60f  call    FwXmlGetAttributeValue
0x18000c614  xor     ebx, ebx
0x18000c616  test    rax, rax
0x18000c619  jz      loc_18000D1EC
0x18000c61f  mov     edx, ebx
0x18000c621  lea     r9d, [rbx+9]
0x18000c625  mov     ecx, edx
0x18000c627  movzx   r8d, word ptr [rax+rcx*2]
0x18000c62c  test    r8w, r8w
0x18000c630  jz      short loc_18000C67D
0x18000c632  cmp     edx, 0Ah
0x18000c635  ja      loc_18000D1EC
0x18000c63b  sub     r8w, 30h ; '0'
0x18000c640  cmp     r8w, r9w
0x18000c644  ja      loc_18000D1EC
0x18000c64a  inc     edx
0x18000c64c  jmp     short loc_18000C625
0x18000c64e  mov     r9d, 54Fh; unsigned int
0x18000c654  mov     [rsp+68h+var_48], r12; struct IRequestContext *
0x18000c659  lea     r8, a522; "522"
0x18000c660  mov     edx, 20Ah; unsigned int
0x18000c665  lea     rcx, aOnecoreAdminWm_5; "onecore\\admin\\wmi\\wmx\\fwxml\\fwxml."...
0x18000c66c  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18000c671  mov     rdx, [rsp+68h+String2]
0x18000c676  inc     edi
0x18000c678  jmp     loc_18000C576
0x18000c67d  cmp     edx, 0Ah
0x18000c680  ja      loc_18000D1EC
0x18000c686  mov     rcx, rax; String
0x18000c689  call    cs:__imp__wtoi64
0x18000c68f  mov     ecx, 0FFFFFFFFh
0x18000c694  cmp     rax, rcx
0x18000c697  jg      loc_18000D1EC
0x18000c69d  mov     [rbp+14h], eax
0x18000c6a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6a7  lea     rbp, WPP_GLOBAL_Control
0x18000c6ae  lea     r12, WPP_b96a2b66f0f03e66f566abfd93da5cbb_Traceguids
0x18000c6b5  cmp     rcx, rbp
0x18000c6b8  jz      short loc_18000C6D7
0x18000c6ba  test    dword ptr [rcx+1Ch], 200000h
0x18000c6c1  jz      short loc_18000C6D7
0x18000c6c3  mov     rcx, [rcx+10h]
0x18000c6c7  mov     edx, 0Bh
0x18000c6cc  mov     r9d, eax
0x18000c6cf  mov     r8, r12
0x18000c6d2  call    WPP_SF_d
0x18000c6d7  mov     rdx, [rsp+68h+String2]; String2
0x18000c6dc  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000c6e0  inc     rdi
0x18000c6e3  cmp     [rdx+rdi*2], bx
0x18000c6e7  jnz     short loc_18000C6E0
0x18000c6e9  mov     esi, ebx
0x18000c6eb  cmp     esi, [r13+70h]
0x18000c6ef  jz      loc_18000D1CD
0x18000c6f5  mov     rbx, [r13+78h]
0x18000c6f9  movsxd  rax, esi
0x18000c6fc  imul    r14, rax, 68h ; 'h'
0x18000c700  add     rbx, r14
0x18000c703  lea     rax, [rbx+30h]
0x18000c707  test    rax, rax
0x18000c70a  jz      loc_18000C7C2
0x18000c710  cmp     [rax+10h], edi
0x18000c713  jnz     loc_18000C7EE
0x18000c719  mov     rcx, [rax+8]
0x18000c71d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c721  jnz     short loc_18000C728
0x18000c723  mov     rcx, [rax]
0x18000c726  jmp     short loc_18000C73B
0x18000c728  mov     rax, [rax]
0x18000c72b  test    rax, rax
0x18000c72e  jnz     short loc_18000C734
0x18000c730  xor     ecx, ecx
0x18000c732  jmp     short loc_18000C73B
0x18000c734  mov     rax, [rax]
0x18000c737  lea     rcx, [rax+rcx*2]; String1
0x18000c73b  mov     r8d, edi; MaxCount
0x18000c73e  call    wcsncmp_0
0x18000c743  test    eax, eax
0x18000c745  jnz     loc_18000C7E9
0x18000c74b  test    rbx, rbx
0x18000c74e  jz      short loc_18000C7C2
0x18000c750  cmp     dword ptr [rbx+10h], 12h
0x18000c754  jnz     loc_18000C7E9
0x18000c75a  mov     rcx, rbx
0x18000c75d  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x18000c762  mov     rcx, rax; String1
0x18000c765  lea     rdx, aMaxconcurrentu; "MaxConcurrentUsers"
0x18000c76c  mov     r8d, 12h; MaxCount
0x18000c772  call    cs:__imp__wcsnicmp
0x18000c778  xor     ebx, ebx
0x18000c77a  test    eax, eax
0x18000c77c  jnz     short loc_18000C7E9
0x18000c77e  mov     rcx, [r13+78h]
0x18000c782  add     rcx, r14
0x18000c785  call    FwXmlGetAttributeValue
0x18000c78a  test    rax, rax
0x18000c78d  jz      loc_18000D1CD
0x18000c793  mov     edx, ebx
0x18000c795  lea     r9d, [rbx+9]
0x18000c799  mov     ecx, edx
0x18000c79b  movzx   r8d, word ptr [rax+rcx*2]
0x18000c7a0  test    r8w, r8w
0x18000c7a4  jz      short loc_18000C7F5
0x18000c7a6  cmp     edx, 0Ah
0x18000c7a9  ja      loc_18000D1CD
0x18000c7af  sub     r8w, 30h ; '0'
0x18000c7b4  cmp     r8w, r9w
0x18000c7b8  ja      loc_18000D1CD
0x18000c7be  inc     edx
0x18000c7c0  jmp     short loc_18000C799
0x18000c7c2  mov     r9d, 54Fh; unsigned int
0x18000c7c8  mov     [rsp+68h+var_48], 0; struct IRequestContext *
0x18000c7d1  lea     r8, a522; "522"
0x18000c7d8  mov     edx, 20Ah; unsigned int
0x18000c7dd  lea     rcx, aOnecoreAdminWm_5; "onecore\\admin\\wmi\\wmx\\fwxml\\fwxml."...
0x18000c7e4  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18000c7e9  mov     rdx, [rsp+68h+String2]
0x18000c7ee  inc     esi
0x18000c7f0  jmp     loc_18000C6EB
0x18000c7f5  cmp     edx, 0Ah
0x18000c7f8  ja      loc_18000D1CD
0x18000c7fe  mov     rcx, rax; String
0x18000c801  call    cs:__imp__wtoi64
0x18000c807  mov     ecx, 0FFFFFFFFh
0x18000c80c  cmp     rax, rcx
0x18000c80f  jg      loc_18000D1CD
0x18000c815  mov     rcx, [rsp+68h+arg_0]
0x18000c81a  mov     [rcx+8], eax
0x18000c81d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c824  cmp     rcx, rbp
0x18000c827  jz      short loc_18000C846
0x18000c829  test    dword ptr [rcx+1Ch], 200000h
0x18000c830  jz      short loc_18000C846
0x18000c832  mov     rcx, [rcx+10h]
0x18000c836  mov     edx, 0Dh
0x18000c83b  mov     r9d, eax
0x18000c83e  mov     r8, r12
0x18000c841  call    WPP_SF_d
0x18000c846  mov     rdx, [rsp+68h+String2]; String2
0x18000c84b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000c84f  inc     rsi
0x18000c852  cmp     [rdx+rsi*2], bx
0x18000c856  jnz     short loc_18000C84F
0x18000c858  mov     edi, ebx
0x18000c85a  cmp     edi, [r13+70h]
0x18000c85e  jz      loc_18000D1AE
0x18000c864  mov     rbx, [r13+78h]
0x18000c868  xor     r8d, r8d
0x18000c86b  movsxd  rax, edi
0x18000c86e  imul    r14, rax, 68h ; 'h'
0x18000c872  add     rbx, r14
0x18000c875  lea     rax, [rbx+30h]
0x18000c879  test    rax, rax
0x18000c87c  jz      loc_18000C939
0x18000c882  cmp     [rax+10h], esi
0x18000c885  jnz     loc_18000C961
0x18000c88b  mov     rcx, [rax+8]
0x18000c88f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c893  jnz     short loc_18000C89A
0x18000c895  mov     rcx, [rax]
0x18000c898  jmp     short loc_18000C8AE
0x18000c89a  mov     rax, [rax]
0x18000c89d  test    rax, rax
0x18000c8a0  jnz     short loc_18000C8A7
0x18000c8a2  mov     rcx, r8
0x18000c8a5  jmp     short loc_18000C8AE
0x18000c8a7  mov     rax, [rax]
0x18000c8aa  lea     rcx, [rax+rcx*2]; String1
0x18000c8ae  mov     r8d, esi; MaxCount
0x18000c8b1  call    wcsncmp_0
0x18000c8b6  xor     r8d, r8d
0x18000c8b9  test    eax, eax
0x18000c8bb  jnz     loc_18000C95C
0x18000c8c1  test    rbx, rbx
0x18000c8c4  jz      short loc_18000C939
0x18000c8c6  cmp     dword ptr [rbx+10h], 0Dh
0x18000c8ca  jnz     loc_18000C95C
0x18000c8d0  mov     rcx, rbx
0x18000c8d3  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x18000c8d8  mov     rcx, rax; String1
0x18000c8db  lea     rdx, aIdletimeoutms; "IdleTimeoutms"
0x18000c8e2  mov     r8d, 0Dh; MaxCount
0x18000c8e8  call    cs:__imp__wcsnicmp
0x18000c8ee  xor     ebx, ebx
0x18000c8f0  test    eax, eax
0x18000c8f2  jnz     short loc_18000C95C
0x18000c8f4  mov     rcx, [r13+78h]
0x18000c8f8  add     rcx, r14
0x18000c8fb  call    FwXmlGetAttributeValue
0x18000c900  test    rax, rax
0x18000c903  jz      loc_18000D1AE
0x18000c909  mov     edx, ebx
0x18000c90b  mov     ecx, edx
0x18000c90d  movzx   r8d, word ptr [rax+rcx*2]
0x18000c912  test    r8w, r8w
0x18000c916  jz      short loc_18000C968
0x18000c918  cmp     edx, 0Ah
0x18000c91b  ja      loc_18000D1AE
0x18000c921  sub     r8w, 30h ; '0'
0x18000c926  mov     ecx, 9
0x18000c92b  cmp     r8w, cx
0x18000c92f  ja      loc_18000D1AE
0x18000c935  inc     edx
0x18000c937  jmp     short loc_18000C90B
0x18000c939  mov     [rsp+68h+var_48], r8; struct IRequestContext *
0x18000c93e  lea     rcx, aOnecoreAdminWm_5; "onecore\\admin\\wmi\\wmx\\fwxml\\fwxml."...
0x18000c945  lea     r8, a522; "522"
0x18000c94c  mov     r9d, 54Fh; unsigned int
0x18000c952  mov     edx, 20Ah; unsigned int
0x18000c957  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18000c95c  mov     rdx, [rsp+68h+String2]
0x18000c961  inc     edi
0x18000c963  jmp     loc_18000C85A
0x18000c968  cmp     edx, 0Ah
0x18000c96b  ja      loc_18000D1AE
0x18000c971  mov     rcx, rax; String
0x18000c974  call    cs:__imp__wtoi64
0x18000c97a  mov     ecx, 0FFFFFFFFh
0x18000c97f  cmp     rax, rcx
0x18000c982  jg      loc_18000D1AE
0x18000c988  mov     rcx, [rsp+68h+arg_0]
0x18000c98d  mov     [rcx+10h], eax
0x18000c990  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c997  cmp     rcx, rbp
0x18000c99a  jz      short loc_18000C9B9
0x18000c99c  test    dword ptr [rcx+1Ch], 200000h
0x18000c9a3  jz      short loc_18000C9B9
0x18000c9a5  mov     rcx, [rcx+10h]
0x18000c9a9  mov     edx, 0Fh
0x18000c9ae  mov     r9d, eax
0x18000c9b1  mov     r8, r12
0x18000c9b4  call    WPP_SF_d
0x18000c9b9  mov     rdx, [rsp+68h+String2]; String2
0x18000c9be  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000c9c2  inc     rdi
0x18000c9c5  cmp     [rdx+rdi*2], bx
  ... truncated ...
```
