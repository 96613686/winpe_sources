# ProcessDocDiffsForDelete(DeclaredConfigurationScopeData *,DCDocument &,DCDocument &,HKEY__ *,int *,bool)

- ea: `0x180091eec`
- end: `0x18009339a`
- name: `?ProcessDocDiffsForDelete@@YAJPEAUDeclaredConfigurationScopeData@@AEAVDCDocument@@1PEAUHKEY__@@PEAH_N@Z`
- size: `5294`
- prototype: `__int64 __fastcall(struct DeclaredConfigurationScopeData *, struct DCDocument *, struct DCDocument *, HKEY, int *, bool)`
- caller_count: `1`
- callee_count: `39`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009468c`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180011fe0`
- `0x180014348`
- `0x18001438c`
- `0x1800143c8`
- `0x180018ac0`
- `0x180018b30`
- `0x180019208`
- `0x180019270`
- `0x1800192b4`
- `0x180019d38`
- `0x18001a2cc`
- `0x18001bc98`
- `0x18001dea8`
- `0x180048fe8`
- `0x18004b7f4`
- `0x18004bc88`
- `0x18004cb4c`
- `0x18004dc70`
- `0x18004e188`
- `0x18004ec50`
- `0x18005ec48`
- `0x18005feac`
- `0x180091eec`
- `0x18009c3e4`
- `0x1800a0174`
- `0x1800a01b0`
- `0x1800a0de4`
- `0x1800a69a0`
- `0x1800f5c8c`
- `0x1800f9d70`
- `0x180100e3c`
- `0x18010136c`
- `0x18010381c`
- `0x180103b58`
- `0x1801051d4`
- `0x18012d59c`
- `0x180139010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009229e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800922ce`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180092318`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180092342`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180092420`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180092462`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009229e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800922ce`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180092318`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180092342`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180092420`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180092462`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800920e8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800920e8`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180092b7d`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180092d08`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180092f7f`
- `OLEAUT32!__imp_VariantInit` at `0x18009251e`
- `OLEAUT32!__imp_VariantInit` at `0x18009252d`
- `OLEAUT32!__imp_VariantInit` at `0x18009251e`
- `OLEAUT32!__imp_VariantInit` at `0x18009252d`
- `OLEAUT32!__imp_VariantClear` at `0x1800925e6`
- `OLEAUT32!__imp_VariantClear` at `0x1800925f5`
- `OLEAUT32!__imp_VariantClear` at `0x1800925e6`
- `OLEAUT32!__imp_VariantClear` at `0x1800925f5`

## string_xrefs

- `0x1800931a0`: `UriCount`
- `0x180092d53`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180093216`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180092870`: `DeclaredConfiguration_CreateCookedSettings`
- `0x1800930fb`: `DeclaredConfiguration_CreateCookedSettings`
- `0x180092869`: `WriteCookedURI::SetValueChanged`
- `0x1800930f4`: `WriteCookedURI`

## pseudocode

```c
// Hidden C++ exception states: #wind=32
__int64 __fastcall ProcessDocDiffsForDelete(
        struct DeclaredConfigurationScopeData *a1,
        struct DCDocument *a2,
        struct DCDocument *a3,
        HKEY a4,
        int *a5)
{
  struct DCDocument *v5; // r12
  int *v6; // rbx
  _QWORD *v7; // r14
  __int64 v8; // r15
  __int64 v9; // rax
  __int64 v10; // rax
  unsigned __int16 **v11; // rcx
  __int64 last_of; // rax
  __int64 v13; // rax
  const unsigned __int16 *v14; // rdx
  _QWORD *v15; // r14
  _QWORD *v16; // rax
  __int64 v17; // rdx
  unsigned int v18; // r15d
  _QWORD *v19; // rbx
  _QWORD *v20; // r12
  _QWORD *v21; // r14
  _QWORD *v22; // r13
  _QWORD *v23; // r15
  char *v24; // rdx
  _QWORD *v25; // rcx
  _QWORD *v26; // rdx
  _QWORD *v27; // rcx
  unsigned __int16 **v28; // rcx
  unsigned __int16 **v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  const char *v33; // r9
  __int64 v34; // rax
  _QWORD *v35; // rdx
  _QWORD *v36; // rcx
  int v37; // eax
  const char *v38; // r9
  char v39; // cl
  _QWORD *v40; // rdx
  _QWORD *v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // r8
  int v44; // ecx
  bool v45; // bl
  int v46; // ecx
  int v47; // ecx
  int v48; // ecx
  int v49; // ecx
  bool v50; // zf
  int v51; // ecx
  int v52; // ecx
  int v53; // ecx
  int v54; // ecx
  char *v55; // rcx
  char *v56; // rax
  signed __int64 v57; // rcx
  int v58; // edx
  int v59; // r8d
  bool v60; // zf
  char *v61; // rcx
  char *v62; // rax
  signed __int64 v63; // rcx
  int v64; // edx
  int v65; // r8d
  __int64 v66; // rax
  __int64 v67; // rdx
  size_t v68; // r8
  const wchar_t *v69; // r9
  const wchar_t *v70; // rcx
  int v71; // ebx
  int v72; // ebx
  unsigned __int16 **v73; // rax
  _QWORD *v74; // r9
  unsigned int v75; // r10d
  CDeclaredConfigurationLogger *v76; // rax
  const unsigned __int16 *v77; // r9
  __int64 *v78; // rcx
  __int64 *v79; // rcx
  __int64 v80; // r15
  int v81; // eax
  _QWORD *v82; // rax
  _WORD *v83; // rdx
  __int64 v84; // r8
  const unsigned __int16 *v85; // rcx
  int v86; // eax
  __int64 v87; // r14
  __int64 v88; // rax
  __int64 v89; // rax
  __int64 v90; // rax
  VARIANTARG *p_pvarg; // rcx
  unsigned __int16 **v92; // rbx
  __int64 v93; // rax
  __int64 v94; // rax
  __int64 v95; // rax
  __int64 v96; // rax
  __int64 v97; // rax
  __int64 v98; // r8
  _QWORD *v99; // r9
  _QWORD *v100; // rax
  int v101; // r9d
  _QWORD *v102; // rdx
  const char *v103; // r9
  unsigned __int16 **v104; // rcx
  unsigned __int16 **v105; // rcx
  __int64 v106; // r14
  _QWORD *v107; // rbx
  __int64 v108; // rax
  __int64 v109; // rax
  __int64 v110; // rax
  __int64 v111; // rax
  __int64 v112; // rax
  __int64 v113; // r8
  _QWORD *v114; // r9
  _QWORD *v115; // rax
  int v116; // r9d
  _QWORD *v117; // rdx
  const char *v118; // r9
  _QWORD *v119; // rax
  _WORD *v120; // rdx
  __int64 v121; // r8
  const unsigned __int16 *v122; // rcx
  int v123; // eax
  __int64 v124; // r14
  __int64 v125; // rax
  __int64 v126; // rax
  __int64 v127; // rax
  VARIANTARG *v128; // rcx
  unsigned __int16 **v129; // rbx
  __int64 v130; // rax
  __int64 v131; // rax
  __int64 v132; // rax
  __int64 v133; // rax
  __int64 v134; // rax
  __int64 v135; // r8
  _QWORD *v136; // r9
  _QWORD *v137; // rax
  int v138; // r9d
  _QWORD *v139; // rdx
  const char *v140; // r9
  int v141; // eax
  int v142; // ebx
  unsigned __int16 **v143; // rax
  _QWORD *v144; // r8
  CDeclaredConfigurationLogger *Logger; // rax
  const unsigned __int16 *v146; // r9
  __int64 v147; // rax
  __int64 v148; // rax
  const unsigned __int16 *v149; // rdx
  int v150; // eax
  const unsigned __int16 *v151; // r9
  const unsigned __int16 *v152; // rdx
  int v153; // eax
  __int64 v154; // rdx
  const unsigned __int16 *v155; // rdx
  int v157; // [rsp+20h] [rbp-478h]
  int v158; // [rsp+20h] [rbp-478h]
  int v159; // [rsp+80h] [rbp-418h]
  int v160; // [rsp+80h] [rbp-418h]
  _QWORD *v161; // [rsp+88h] [rbp-410h]
  unsigned int v162; // [rsp+90h] [rbp-408h]
  char v163; // [rsp+94h] [rbp-404h]
  unsigned int v164; // [rsp+98h] [rbp-400h]
  unsigned int v165; // [rsp+9Ch] [rbp-3FCh]
  __int64 v166; // [rsp+A0h] [rbp-3F8h]
  HKEY hKey; // [rsp+A8h] [rbp-3F0h]
  struct DCDocument *v168; // [rsp+B0h] [rbp-3E8h]
  _QWORD *v169; // [rsp+C0h] [rbp-3D8h]
  struct DCDocument *v170; // [rsp+C8h] [rbp-3D0h]
  _QWORD *v175; // [rsp+100h] [rbp-398h]
  _QWORD *v176; // [rsp+108h] [rbp-390h]
  char v177[8]; // [rsp+110h] [rbp-388h] BYREF
  char v178; // [rsp+118h] [rbp-380h] BYREF
  char v179[8]; // [rsp+120h] [rbp-378h] BYREF
  char v180; // [rsp+128h] [rbp-370h] BYREF
  char v181[8]; // [rsp+130h] [rbp-368h] BYREF
  char v182; // [rsp+138h] [rbp-360h] BYREF
  __int64 v183; // [rsp+140h] [rbp-358h] BYREF
  __int64 v184; // [rsp+150h] [rbp-348h] BYREF
  _QWORD v185[3]; // [rsp+160h] [rbp-338h] BYREF
  unsigned __int64 v186; // [rsp+178h] [rbp-320h]
  struct tagVARIANT v187; // [rsp+180h] [rbp-318h] BYREF
  unsigned __int16 *v188[3]; // [rsp+1A0h] [rbp-2F8h] BYREF
  unsigned __int64 v189; // [rsp+1B8h] [rbp-2E0h]
  unsigned __int16 *v190[3]; // [rsp+1C0h] [rbp-2D8h] BYREF
  unsigned __int64 v191; // [rsp+1D8h] [rbp-2C0h]
  VARIANTARG pvarg; // [rsp+1E0h] [rbp-2B8h] BYREF
  struct tagVARIANT v193; // [rsp+200h] [rbp-298h] BYREF
  _BYTE v194[32]; // [rsp+220h] [rbp-278h] BYREF
  VARIANTARG v195; // [rsp+240h] [rbp-258h] BYREF
  unsigned __int16 *v196[3]; // [rsp+260h] [rbp-238h] BYREF
  unsigned __int64 v197; // [rsp+278h] [rbp-220h]
  unsigned __int16 *v198[3]; // [rsp+280h] [rbp-218h] BYREF
  unsigned __int64 v199; // [rsp+298h] [rbp-200h]
  __int64 v200[4]; // [rsp+2A0h] [rbp-1F8h] BYREF
  _QWORD v201[4]; // [rsp+2C0h] [rbp-1D8h] BYREF
  _QWORD v202[4]; // [rsp+2E0h] [rbp-1B8h] BYREF
  __int64 v203[38]; // [rsp+300h] [rbp-198h] BYREF
  unsigned __int16 v204[16]; // [rsp+430h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+498h] [rbp+0h]

  hKey = a4;
  v5 = a3;
  v168 = a3;
  v170 = a2;
  v6 = a5;
  v204[0] = 0;
  v7 = (_QWORD *)*((_QWORD *)a2 + 20);
  v175 = (_QWORD *)*((_QWORD *)a2 + 21);
  while ( 1 )
  {
    v169 = v7;
    if ( v7 == v175 )
      return 0;
    v8 = _RTDynamicCast_0(*v7, 0, &DCProvider `RTTI Type Descriptor', &DCCSP `RTTI Type Descriptor', 0);
    v166 = v8;
    if ( v8 )
      break;
LABEL_215:
    v7 += 2;
  }
  ++*v6;
  std::wstring::wstring((__int64)v188, (__int64)&word_180142E98);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
  {
    last_of = std::wstring::find_last_of(v8 + 88, L"/");
    try
    {
      v13 = std::wstring::substr(v8 + 88, &v187, last_of + 1, -1);
      std::wstring::operator=(v188, v13);
      std::wstring::_Tidy_deallocate(&v187);
    }
    catch ( ... )
    {
      v170 = a2;
      v5 = a3;
      hKey = a4;
      v168 = a3;
      goto LABEL_7;
    }
    goto LABEL_7;
  }
  if ( (**(unsigned int (__fastcall ***)(_QWORD))*v7)(*v7) == 1 )
  {
    try
    {
      v9 = std::wstring::find_last_of(v8 + 88, L"/");
      v10 = std::wstring::substr(v8 + 88, &v187, v9 + 1, -1);
      std::wstring::operator=(v188, v10);
      std::wstring::_Tidy_deallocate(&v187);
    }
    catch ( ... )
    {
      v170 = a2;
      v5 = a3;
      hKey = a4;
      v168 = a3;
    }
LABEL_7:
    v6 = a5;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_EnterpriseDesktopAppManagementCsp_Support>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_EnterpriseDesktopAppManagementCsp_Support>::GetImpl'::`2'::impl) )
  {
    v11 = v188;
    if ( v189 > 7 )
      v11 = (unsigned __int16 **)v188[0];
    if ( !(unsigned int)_o__wcsnicmp(v11, L"EnterpriseDesktopAppManagement", 260) )
    {
      --*v6;
      std::wstring::_Tidy_deallocate(v188);
      goto LABEL_215;
    }
  }
  v162 = 0;
  v159 = 0;
  v14 = (const unsigned __int16 *)v188;
  if ( v189 > 7 )
    v14 = v188[0];
  CspSchema::CspSchema((CspSchema *)v203, v14);
  CspSchema::InitializeFromSchemaStore((CspSchema *)v203);
  v163 = 0;
  v15 = *(_QWORD **)(v8 + 16);
  v16 = *(_QWORD **)(v8 + 24);
  v176 = v16;
  while ( 2 )
  {
    v161 = v15;
    if ( v15 == v16 )
    {
      if ( !v159 )
        --*a5;
LABEL_214:
      CspSchema::~CspSchema((CspSchema *)v203);
      std::wstring::_Tidy_deallocate(v188);
      v6 = a5;
      v7 = v169;
      goto LABEL_215;
    }
    if ( *(_DWORD *)(*v15 + 184LL) == 2 )
    {
LABEL_210:
      v15 += 2;
      v16 = v176;
      continue;
    }
    break;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl'::`2'::impl) )
    v204[0] = 0;
  v18 = 0;
  v165 = 0;
  v19 = (_QWORD *)*((_QWORD *)v5 + 20);
  v20 = (_QWORD *)*((_QWORD *)v5 + 21);
  while ( 2 )
  {
    if ( v19 == v20 )
    {
      LOBYTE(v17) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority>::GetImpl'::`2'::impl,
        v17);
      v5 = v168;
      if ( *((_DWORD *)v168 + 69) == 2
        || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority_ForAll>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority_ForAll>::GetImpl'::`2'::impl) )
      {
        v80 = v166;
        goto LABEL_180;
      }
      std::wstring::wstring((__int64)v185);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
      {
        v80 = v166;
        v81 = *(_DWORD *)(v166 + 128);
        if ( v81 != 1 )
        {
          if ( v81 != 3 )
          {
            v71 = -2147418113;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x718A,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
              (const char *)0x8000FFFFLL,
              v158);
            v79 = v185;
            goto LABEL_159;
          }
          v106 = *v15;
          v107 = (_QWORD *)(v166 + 88);
          if ( *(_QWORD *)(v166 + 112) > 7u )
            v107 = (_QWORD *)*v107;
          try
          {
            v108 = std::operator+<unsigned short>(&v195, L"./", (char *)v168 + 32);
            v109 = std::operator+<unsigned short>(&pvarg, v108, L"/");
            v110 = std::operator+<unsigned short>(&v193, v109, v107);
            v111 = std::operator+<unsigned short>(&v187, v110, L"/");
            v112 = std::operator+<unsigned short>(v194, v111, v106);
            std::wstring::operator=(v185, v112);
            std::wstring::_Tidy_deallocate(v194);
            std::wstring::_Tidy_deallocate(&v187);
            std::wstring::_Tidy_deallocate(&v193);
            std::wstring::_Tidy_deallocate(&pvarg);
            std::wstring::_Tidy_deallocate(&v195);
            v114 = v185;
            if ( v186 > 7 )
              v114 = (_QWORD *)v185[0];
            v115 = (_QWORD *)std::wstring::end(v185, v179, v113, v114);
            v117 = v185;
            if ( v186 > 7 )
              LODWORD(v117) = v185[0];
            std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
              (unsigned int)&v180,
              (_DWORD)v117,
              *v115,
              v116,
              *(__int64 *)&_o_towlower);
            std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase<std::wstring>(
              uriMap,
              (__int64)v185);
          }
          catch ( ... )
          {
            v160 = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x7186,
                     (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredc"
                                   "onfigurationapi.cpp",
                     v118);
            goto LABEL_149;
          }
          goto LABEL_178;
        }
        std::wstring::wstring((__int64)v196);
        v82 = (_QWORD *)(v166 + 88);
        if ( *(_QWORD *)(v166 + 112) > 7u )
          v82 = (_QWORD *)*v82;
        v83 = (_WORD *)v82 + 2;
        v84 = -1;
        do
          ++v84;
        while ( v83[v84] );
        std::wstring::_Assign<unsigned short>((char **)v196, v83, (char *)v84);
        try
        {
          v85 = (const unsigned __int16 *)v196;
          if ( v197 > 7 )
            v85 = v196[0];
          v86 = DCDoesCspNeedPrefix(v85);
          v87 = *v15;
          if ( v86 )
          {
            v92 = v196;
            if ( v197 > 7 )
              v92 = (unsigned __int16 **)v196[0];
            v93 = std::operator+<unsigned short>(v194, L"./", (char *)v168 + 32);
            v94 = std::operator+<unsigned short>(&v195, v93, L"/");
            v95 = std::operator+<unsigned short>(&pvarg, v94, v92);
            v96 = std::operator+<unsigned short>(&v193, v95, L"/");
            v97 = std::operator+<unsigned short>(&v187, v96, v87);
            std::wstring::operator=(v185, v97);
            std::wstring::_Tidy_deallocate(&v187);
            std::wstring::_Tidy_deallocate(&v193);
            std::wstring::_Tidy_deallocate(&pvarg);
            std::wstring::_Tidy_deallocate(&v195);
            p_pvarg = (VARIANTARG *)v194;
          }
          else
          {
            v88 = std::operator+<unsigned short>(&pvarg, L"./", v196);
            v89 = std::operator+<unsigned short>(&v193, v88, L"/");
            v90 = std::operator+<unsigned short>(&v187, v89, v87);
            std::wstring::operator=(v185, v90);
            std::wstring::_Tidy_deallocate(&v187);
            std::wstring::_Tidy_deallocate(&v193);
            p_pvarg = &pvarg;
          }
          std::wstring::_Tidy_deallocate(p_pvarg);
          v99 = v185;
          if ( v186 > 7 )
            v99 = (_QWORD *)v185[0];
          v100 = (_QWORD *)std::wstring::end(v185, v177, v98, v99);
          v102 = v185;
          if ( v186 > 7 )
            LODWORD(v102) = v185[0];
          std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
            (unsigned int)&v178,
            (_DWORD)v102,
            *v100,
            v101,
            *(__int64 *)&_o_towlower);
          std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase<std::wstring>(
            uriMap,
            (__int64)v185);
          v104 = v196;
        }
        catch ( ... )
        {
          v160 = wil::details::in1diag3::Return_CaughtException(
                   retaddr,
                   (void *)0x717D,
                   (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredcon"
                                 "figurationapi.cpp",
                   v103);
          v105 = v196;
          goto LABEL_148;
        }
      }
      else
      {
        std::wstring::wstring((__int64)v198);
        v80 = v166;
        v119 = (_QWORD *)(v166 + 88);
        if ( *(_QWORD *)(v166 + 112) > 7u )
          v119 = (_QWORD *)*v119;
        v120 = (_WORD *)v119 + 2;
        v121 = -1;
        do
          ++v121;
        while ( v120[v121] );
        std::wstring::_Assign<unsigned short>((char **)v198, v120, (char *)v121);
        v122 = (const unsigned __int16 *)v198;
        if ( v199 > 7 )
          v122 = v198[0];
        v123 = DCDoesCspNeedPrefix(v122);
        try
        {
          v124 = *v15;
          if ( v123 )
          {
            v129 = v198;
            if ( v199 > 7 )
              v129 = (unsigned __int16 **)v198[0];
            v130 = std::operator+<unsigned short>(&v195, L"./", (char *)v168 + 32);
            v131 = std::operator+<unsigned short>(&pvarg, v130, L"/");
            v132 = std::operator+<unsigned short>(&v193, v131, v129);
            v133 = std::operator+<unsigned short>(&v187, v132, L"/");
            v134 = std::operator+<unsigned short>(v194, v133, v124);
            std::wstring::operator=(v185, v134);
            std::wstring::_Tidy_deallocate(v194);
            std::wstring::_Tidy_deallocate(&v187);
            std::wstring::_Tidy_deallocate(&v193);
            std::wstring::_Tidy_deallocate(&pvarg);
            v128 = &v195;
          }
          else
          {
            v125 = std::operator+<unsigned short>(&v193, L"./", v198);
            v126 = std::operator+<unsigned short>(&v187, v125, L"/");
            v127 = std::operator+<unsigned short>(v194, v126, v124);
            std::wstring::operator=(v185, v127);
            std::wstring::_Tidy_deallocate(v194);
            std::wstring::_Tidy_deallocate(&v187);
            v128 = &v193;
          }
          std::wstring::_Tidy_deallocate(v128);
          v136 = v185;
          if ( v186 > 7 )
            v136 = (_QWORD *)v185[0];
          v137 = (_QWORD *)std::wstring::end(v185, v181, v135, v136);
          v139 = v185;
          if ( v186 > 7 )
            LODWORD(v139) = v185[0];
          std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
            (unsigned int)&v182,
            (_DWORD)v139,
            *v137,
            v138,
            *(__int64 *)&_o_towlower);
          std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase<std::wstring>(
            uriMap,
            (__int64)v185);
          v104 = v198;
        }
        catch ( ... )
        {
          v160 = wil::details::in1diag3::Return_CaughtException(
                   retaddr,
                   (void *)0x719D,
                   (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredcon"
                                 "figurationapi.cpp",
                   v140);
          v105 = v198;
LABEL_148:
          std::wstring::_Tidy_deallocate(v105);
LABEL_149:
          std::wstring::_Tidy_deallocate(v185);
          v71 = v160;
          goto LABEL_211;
        }
      }
      std::wstring::_Tidy_deallocate(v104);
LABEL_178:
      std::wstring::_Tidy_deallocate(v185);
      v15 = v161;
LABEL_180:
      v204[0] = 0;
      v141 = StringCchPrintfW(v204, 0xFu, L"CSP%d", (unsigned int)*a5);
      if ( v141 < 0 )
      {
        v71 = v141;
        goto LABEL_211;
      }
      ++v162;
      std::wstring::wstring((__int64)v200);
      v142 = *((_DWORD *)v168 + 69);
      std::wstring::wstring((__int64)v194, (_QWORD *)a3 + 4);
      v143 = (unsigned __int16 **)std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(&v184, v15);
      v71 = WriteCookedURI(
              hKey,
              (__int64)v204,
              v162,
              v143,
              2u,
              v144,
              (__int64)v203,
              0,
              0,
              0,
              0,
              (unsigned __int16 *)v200,
              0,
              v163,
              v142);
      if ( v71 < 0 )
      {
        Logger = CDeclaredConfigurationLogger::GetLogger();
        v146 = (const unsigned __int16 *)*v15;
        if ( *(_QWORD *)(*v15 + 24LL) > 7u )
          v146 = *(const unsigned __int16 **)v146;
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          Logger,
          L"DeclaredConfiguration_CreateCookedSettings",
          L"WriteCookedURI",
          v146,
          v71);
        goto LABEL_186;
      }
      std::wstring::wstring((__int64)v190);
      try
      {
        v147 = std::wstring::wstring((__int64)&v187, (__int64)L"cooked\\");
        v148 = std::operator+<unsigned short>(v194, v147, v204);
        std::wstring::operator=(v190, v148);
        std::wstring::_Tidy_deallocate(v194);
        std::wstring::_Tidy_deallocate(&v187);
        v149 = (const unsigned __int16 *)v190;
        if ( v191 > 7 )
          v149 = v190[0];
        v150 = DCCDNUtil_SetRegistryDWORD(hKey, v149, L"UriCount", v162);
      }
      catch ( std::bad_alloc )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x71E3,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)0x8007000ELL,
          v157);
        std::wstring::_Tidy_deallocate(v190);
        std::wstring::_Tidy_deallocate(v200);
        v71 = -2147024882;
        goto LABEL_211;
      }
      v71 = v150;
      if ( v150 < 0 )
        goto LABEL_192;
      v151 = (const unsigned __int16 *)(v80 + 88);
      if ( *(_QWORD *)(v80 + 112) > 7u )
        v151 = *(const unsigned __int16 **)v151;
      v152 = (const unsigned __int16 *)v190;
      if ( v191 > 7 )
        v152 = v190[0];
      v153 = DCCDNUtil_SetRegistryString(hKey, v152, L"csp", v151, 0);
      v71 = v153;
      if ( v153 < 0 )
      {
        v154 = 29167;
LABEL_199:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v154,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)(unsigned int)v153,
          v158);
LABEL_192:
        std::wstring::_Tidy_deallocate(v190);
LABEL_186:
        v79 = v200;
        goto LABEL_159;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
      {
        v155 = (const unsigned __int16 *)v190;
        if ( v191 > 7 )
          v155 = v190[0];
        v153 = DCCDNUtil_SetRegistryDWORD(hKey, v155, L"ProviderType", *(_DWORD *)(v80 + 128));
        v71 = v153;
        if ( v153 < 0 )
        {
          v154 = 29175;
          goto LABEL_199;
        }
      }
      if ( v200[2] && !v163 )
      {
        std::wstring::_Tidy_deallocate(v190);
        std::wstring::_Tidy_deallocate(v200);
        goto LABEL_214;
      }
      v159 = 1;
      std::wstring::_Tidy_deallocate(v190);
      v78 = v200;
LABEL_209:
      std::wstring::_Tidy_deallocate(v78);
      goto LABEL_210;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl'::`2'::impl) )
      v165 = v18 + 1;
    v21 = (_QWORD *)_RTDynamicCast_0(*v19, 0, &DCProvider `RTTI Type Descriptor', &DCCSP `RTTI Type Descriptor', 0);
    v164 = 0;
    v22 = (_QWORD *)v21[2];
    v23 = (_QWORD *)v21[3];
LABEL_26:
    if ( v22 == v23 )
    {
      v19 += 2;
      v15 = v161;
      v18 = v165;
      continue;
    }
    break;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl'::`2'::impl) )
    ++v164;
  if ( *((_QWORD *)v168 + 7) <= 7u )
    v24 = (char *)v168 + 32;
  else
    v24 = (char *)*((_QWORD *)v168 + 4);
  v25 = (_QWORD *)((char *)v170 + 32);
  if ( *((_QWORD *)v170 + 7) > 7u )
    v25 = (_QWORD *)*v25;
  if ( (unsigned int)_o__wcsicmp(v25, v24) )
    goto LABEL_124;
  v26 = v21 + 11;
  if ( v21[14] > 7u )
    v26 = (_QWORD *)*v26;
  v27 = (_QWORD *)(v166 + 88);
  if ( *(_QWORD *)(v166 + 112) > 7u )
    v27 = (_QWORD *)*v27;
  if ( (unsigned int)_o__wcsicmp(v27, v26) )
  {
LABEL_124:
    v22 += 2;
    goto LABEL_26;
  }
  std::wstring::wstring((__int64)v202);
  std::wstring::wstring((__int64)v201);
  v28 = v188;
  if ( v189 > 7 )
    v28 = (unsigned __int16 **)v188[0];
  if ( !(unsigned int)_o__wcsicmp(v28, L"vpnv2") )
    goto LABEL_46;
  v29 = v188;
  if ( v189 > 7 )
    v29 = (unsigned __int16 **)v188[0];
  if ( !(unsigned int)_o__wcsicmp(v29, L"wifi") )
  {
LABEL_46:
    v30 = std::wstring::find(*v161, L"/", 0);
    try
    {
      v31 = std::wstring::substr(*v161, &v187, 0, v30);
      std::wstring::operator=(v201, v31);
      std::wstring::_Tidy_deallocate(&v187);
      v32 = std::wstring::find(*v22, L"/", 0);
    }
    catch ( ... )
    {
      v71 = wil::details::in1diag3::Return_CaughtException(
              retaddr,
              (void *)0x70AA,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
              v33);
      goto LABEL_125;
    }
    try
    {
      v34 = std::wstring::substr(*v22, &v187, 0, v32);
      std::wstring::operator=(v202, v34);
      std::wstring::_Tidy_deallocate(&v187);
      v35 = v202;
      if ( v202[3] > 7u )
        v35 = (_QWORD *)v202[0];
      v36 = v201;
      if ( v201[3] > 7u )
        v36 = (_QWORD *)v201[0];
      v37 = _o__wcsicmp(v36, v35);
      v39 = v163;
      if ( !v37 )
        v39 = 1;
      v163 = v39;
    }
    catch ( ... )
    {
      v71 = wil::details::in1diag3::Return_CaughtException(
              retaddr,
              (void *)0x70B0,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
              v38);
      goto LABEL_125;
    }
  }
  v40 = (_QWORD *)*v22;
  if ( *(_QWORD *)(*v22 + 24LL) > 7u )
    v40 = (_QWORD *)*v40;
  v41 = (_QWORD *)*v161;
  if ( *(_QWORD *)(*v161 + 24LL) > 7u )
    v41 = (_QWORD *)*v41;
  if ( (unsigned int)_o__wcsicmp(v41, v40) )
  {
    std::wstring::_Tidy_deallocate(v201);
    std::wstring::_Tidy_deallocate(v202);
    goto LABEL_124;
  }
  v5 = v168;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl'::`2'::impl)
    || *((_DWORD *)v168 + 69) != 2 )
  {
    v15 = v161;
    goto LABEL_122;
  }
  v15 = v161;
  if ( (*((_DWORD *)v168 + 169) & 0x400) == 0 )
    goto LABEL_122;
  v42 = *v22;
  v43 = *v161;
  v44 = *(_DWORD *)(*v161 + 164LL);
  if ( v44 != *(_DWORD *)(*v22 + 164LL) )
    goto LABEL_116;
  v45 = 0;
  if ( v44 > 7 )
  {
    v51 = v44 - 8;
    if ( !v51 )
      goto LABEL_84;
    v52 = v51 - 1;
    if ( !v52 )
      goto LABEL_75;
    v53 = v52 - 2;
    if ( v53 )
    {
      v54 = v53 - 1;
      if ( v54 )
      {
        if ( v54 != 1 )
          goto LABEL_75;
        goto LABEL_84;
      }
LABEL_100:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
      {
        v61 = (char *)(*v22 + 32LL);
        if ( *(_QWORD *)(*v22 + 56LL) > 7u )
          v61 = *(char **)v61;
        v62 = (char *)(*v161 + 32LL);
        if ( *(_QWORD *)(*v161 + 56LL) > 7u )
          v62 = *(char **)v62;
        v63 = v61 - v62;
        do
        {
          v64 = *(unsigned __int16 *)&v62[v63];
          v65 = *(unsigned __int16 *)v62 - v64;
          if ( v65 )
            break;
          v62 += 2;
        }
        while ( v64 );
        v50 = v65 == 0;
        goto LABEL_78;
      }
      goto LABEL_109;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
    {
      v50 = *(_QWORD *)(*v161 + 392LL) == *(_QWORD *)(*v22 + 392LL);
      goto LABEL_78;
    }
LABEL_96:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
    {
      v60 = *(double *)(*v161 + 392LL) == *(double *)(*v22 + 392LL);
      goto LABEL_98;
    }
    goto LABEL_100;
  }
  if ( v44 == 7 )
  {
LABEL_109:
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
      goto LABEL_75;
    v66 = *v22;
    v67 = *v161;
    v68 = *(_QWORD *)(*v161 + 48LL);
    if ( v68 != *(_QWORD *)(*v22 + 48LL) )
    {
LABEL_99:
      v45 = 1;
      goto LABEL_75;
    }
    v69 = (const wchar_t *)(v66 + 32);
    if ( *(_QWORD *)(v66 + 56) > 7u )
      v69 = *(const wchar_t **)v69;
    v70 = (const wchar_t *)(v67 + 32);
    if ( *(_QWORD *)(v67 + 56) > 7u )
      v70 = *(const wchar_t **)v70;
    v60 = wmemcmp(v70, v69, v68) == 0;
LABEL_98:
    if ( v60 )
      goto LABEL_75;
    goto LABEL_99;
  }
  if ( !v44 )
    goto LABEL_77;
  v46 = v44 - 1;
  if ( !v46 )
    goto LABEL_84;
  v47 = v46 - 1;
  if ( !v47 )
    goto LABEL_96;
  v48 = v47 - 2;
  if ( v48 )
  {
    v49 = v48 - 1;
    if ( v49 )
    {
      if ( v49 == 1 )
      {
        VariantInit(&pvarg);
        VariantInit(&v195);
        if ( (int)DCSetBinaryToVariant(*(unsigned __int8 **)(*v161 + 392LL), *(unsigned int *)(*v161 + 400LL), &pvarg) >= 0
          && (int)DCSetBinaryToVariant(*(unsigned __int8 **)(*v22 + 392LL), *(unsigned int *)(*v22 + 400LL), &v195) >= 0 )
        {
          v193 = v195;
          v187 = pvarg;
          v45 = IsDiffVariants(&v187, &v193) != 0;
        }
        VariantClear(&v195);
        VariantClear(&pvarg);
      }
      goto LABEL_75;
    }
LABEL_77:
    v50 = *(_DWORD *)(v43 + 392) == *(_DWORD *)(v42 + 392);
LABEL_78:
    v45 = !v50;
    goto LABEL_75;
  }
LABEL_84:
  v55 = (char *)(v42 + 32);
  if ( *(_QWORD *)(v42 + 56) > 7u )
    v55 = *(char **)v55;
  v56 = (char *)(v43 + 32);
  if ( *(_QWORD *)(v43 + 56) > 7u )
    v56 = *(char **)v56;
  v57 = v55 - v56;
  do
  {
    v58 = *(unsigned __int16 *)&v56[v57];
    v59 = *(unsigned __int16 *)v56 - v58;
    if ( v59 )
      break;
    v56 += 2;
  }
  while ( v58 );
  if ( v59 )
    v45 = 1;
LABEL_75:
  if ( !v45 )
    goto LABEL_122;
LABEL_116:
  *(_BYTE *)(*v22 + 409LL) = 1;
  v71 = StringCchPrintfW(v204, 0xFu, L"CSP%d", v165);
  if ( v71 < 0 )
    goto LABEL_125;
  v72 = *((_DWORD *)v168 + 69);
  std::wstring::wstring((__int64)&v187, (_QWORD *)v168 + 4);
  v73 = (unsigned __int16 **)std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(&v183, v22);
  v71 = WriteCookedURI(hKey, (__int64)v204, v164, v73, v75, v74, (__int64)v203, 0, 0, 0, 0, 0, 0, 0, v72);
  if ( v71 >= 0 )
  {
LABEL_122:
    std::wstring::_Tidy_deallocate(v201);
    v78 = v202;
    goto LABEL_209;
  }
  v76 = CDeclaredConfigurationLogger::GetLogger();
  v77 = (const unsigned __int16 *)*v161;
  if ( *(_QWORD *)(*v161 + 24LL) > 7u )
    v77 = *(const unsigned __int16 **)v77;
  CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
    v76,
    L"DeclaredConfiguration_CreateCookedSettings",
    L"WriteCookedURI::SetValueChanged",
    v77,
    v71);
LABEL_125:
  std::wstring::_Tidy_deallocate(v201);
  v79 = v202;
LABEL_159:
  std::wstring::_Tidy_deallocate(v79);
LABEL_211:
  CspSchema::~CspSchema((CspSchema *)v203);
  std::wstring::_Tidy_deallocate(v188);
  return (unsigned int)v71;
}

```

## disassembly

```asm
0x180091eec  push    rbx
0x180091eee  push    rsi
0x180091eef  push    rdi
0x180091ef0  push    r12
0x180091ef2  push    r13
0x180091ef4  push    r14
0x180091ef6  push    r15
0x180091ef8  sub     rsp, 460h
0x180091eff  mov     rax, cs:__security_cookie
0x180091f06  xor     rax, rsp
0x180091f09  mov     [rsp+498h+var_48], rax
0x180091f11  mov     rax, r9
0x180091f14  mov     [rsp+498h+hKey], rax
0x180091f1c  mov     r12, r8
0x180091f1f  mov     [rsp+498h+var_3E8], r8
0x180091f27  mov     [rsp+498h+var_3D0], rdx
0x180091f2f  mov     [rsp+498h+var_3C8], rdx
0x180091f37  mov     [rsp+498h+var_3B8], r8
0x180091f3f  mov     [rsp+498h+var_3A8], rax
0x180091f47  mov     rbx, [rsp+498h+arg_20]
0x180091f4f  mov     [rsp+498h+var_3E0], rbx
0x180091f57  mov     [rsp+498h+var_3A0], r8
0x180091f5f  xor     edi, edi
0x180091f61  mov     [rsp+498h+var_68], di
0x180091f69  mov     r14, [rdx+0A0h]
0x180091f70  mov     rax, [rdx+0A8h]
0x180091f77  mov     [rsp+498h+var_398], rax
0x180091f7f  lea     esi, [rdi+7]
0x180091f82  lea     r13d, [rdi+1]
0x180091f86  mov     [rsp+498h+var_3D8], r14
0x180091f8e  cmp     r14, [rsp+498h+var_398]
0x180091f96  jz      loc_180093375
0x180091f9c  mov     dword ptr [rsp+498h+var_478], edi
0x180091fa0  lea     r9, ??_R0?AVDCCSP@@@8; DCCSP `RTTI Type Descriptor'
0x180091fa7  lea     r8, ??_R0?AVDCProvider@@@8; DCProvider `RTTI Type Descriptor'
0x180091fae  xor     edx, edx
0x180091fb0  mov     rcx, [r14]
0x180091fb3  call    __RTDynamicCast_0
0x180091fb8  mov     r15, rax
0x180091fbb  mov     [rsp+498h+var_3F8], rax
0x180091fc3  test    rax, rax
0x180091fc6  jz      loc_18009336C
0x180091fcc  add     [rbx], r13d
0x180091fcf  lea     rdx, word_180142E98
0x180091fd6  lea     rcx, [rsp+498h+var_2F8]
0x180091fde  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180091fe3  nop
0x180091fe4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x180091feb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x180091ff0  test    al, al
0x180091ff2  jz      loc_180092106
0x180091ff8  mov     rcx, [r14]
0x180091ffb  mov     rax, [rcx]
0x180091ffe  mov     rax, [rax]
0x180092001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092006  cmp     eax, r13d
0x180092009  jnz     loc_1800920AE
0x18009200f  lea     rdx, asc_18013EB9C; "/"
0x180092016  lea     rcx, [r15+58h]
0x18009201a  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_last_of(ushort const * const,unsigned __int64)
0x18009201f  lea     r8, [rax+1]
0x180092023  or      r9, 0FFFFFFFFFFFFFFFFh
0x180092027  lea     rdx, [rsp+498h+var_318]
0x18009202f  lea     rcx, [r15+58h]
0x180092033  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180092038  mov     rdx, rax
0x18009203b  lea     rcx, [rsp+498h+var_2F8]
0x180092043  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180092048  lea     rcx, [rsp+498h+var_318]
0x180092050  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180092055  jmp     loc_18009214D
0x18009205a  mov     rax, [rsp+498h+var_3C8]
0x180092062  mov     [rsp+498h+var_3D0], rax
0x18009206a  mov     rax, [rsp+498h+var_3A8]
0x180092072  mov     r12, [rsp+498h+var_3B8]
0x18009207a  mov     r15, [rsp+498h+var_3F8]
0x180092082  mov     [rsp+498h+hKey], rax
0x18009208a  mov     [rsp+498h+var_3E8], r12
0x180092092  mov     r14, [rsp+498h+var_3D8]
0x18009209a  mov     r13d, 1
0x1800920a0  lea     esi, [r13+6]
0x1800920a4  xor     edi, edi
0x1800920a6  mov     rbx, [rsp+498h+var_3E0]
0x1800920ae  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_EnterpriseDesktopAppManagementCsp_Support@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_EnterpriseDesktopAppManagementCsp_Support@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_EnterpriseDesktopAppManagementCsp_Support> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_EnterpriseDesktopAppManagementCsp_Support>::GetImpl(void)'::`2'::impl
0x1800920b5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_EnterpriseDesktopAppManagementCsp_Support@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_EnterpriseDesktopAppManagementCsp_Support>::__private_IsEnabled(void)
0x1800920ba  test    al, al
0x1800920bc  jz      loc_180092152
0x1800920c2  lea     rcx, [rsp+498h+var_2F8]
0x1800920ca  cmp     [rsp+498h+var_2E0], rsi
0x1800920d2  cmova   rcx, [rsp+498h+var_2F8]
0x1800920db  mov     r8d, 104h
0x1800920e1  lea     rdx, aEnterprisedesk_0; "EnterpriseDesktopAppManagement"
0x1800920e8  call    cs:__imp__o__wcsnicmp
0x1800920ee  test    eax, eax
0x1800920f0  jnz     short loc_180092152
0x1800920f2  dec     dword ptr [rbx]
0x1800920f4  lea     rcx, [rsp+498h+var_2F8]
0x1800920fc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180092101  jmp     loc_18009336C
0x180092106  lea     rdx, asc_18013EB9C; "/"
0x18009210d  lea     rcx, [r15+58h]
0x180092111  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_last_of(ushort const * const,unsigned __int64)
0x180092116  lea     r8, [rax+1]
0x18009211a  or      r9, 0FFFFFFFFFFFFFFFFh
0x18009211e  lea     rdx, [rsp+498h+var_318]
0x180092126  lea     rcx, [r15+58h]
0x18009212a  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18009212f  mov     rdx, rax
0x180092132  lea     rcx, [rsp+498h+var_2F8]
0x18009213a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18009213f  lea     rcx, [rsp+498h+var_318]
0x180092147  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009214c  nop
0x18009214d  jmp     loc_1800920A6
0x180092152  mov     [rsp+498h+var_408], edi
0x180092159  mov     [rsp+498h+var_418], edi
0x180092160  lea     rdx, [rsp+498h+var_2F8]
0x180092168  cmp     [rsp+498h+var_2E0], rsi
0x180092170  cmova   rdx, [rsp+498h+var_2F8]; unsigned __int16 *
0x180092179  lea     rcx, [rsp+498h+var_198]; this
0x180092181  call    ??0CspSchema@@QEAA@PEBG@Z; CspSchema::CspSchema(ushort const *)
0x180092186  nop
0x180092187  lea     rcx, [rsp+498h+var_198]; this
0x18009218f  call    ?InitializeFromSchemaStore@CspSchema@@QEAAJXZ; CspSchema::InitializeFromSchemaStore(void)
0x180092194  mov     byte ptr [rsp+498h+var_404], dil
0x18009219c  mov     r14, [r15+10h]
0x1800921a0  mov     rax, [r15+18h]
0x1800921a4  mov     [rsp+498h+var_390], rax
0x1800921ac  mov     [rsp+498h+var_410], r14
0x1800921b4  cmp     r14, rax
0x1800921b7  jz      loc_18009332D
0x1800921bd  mov     rax, [r14]
0x1800921c0  cmp     dword ptr [rax+0B8h], 2
0x1800921c7  jz      loc_1800932D7
0x1800921cd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl(void)'::`2'::impl
0x1800921d4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(void)
0x1800921d9  test    al, al
0x1800921db  jz      short loc_1800921E5
0x1800921dd  mov     [rsp+498h+var_68], di
0x1800921e5  mov     r15d, edi
0x1800921e8  mov     [rsp+498h+var_3FC], edi
0x1800921ef  mov     rbx, [r12+0A0h]
0x1800921f7  mov     r12, [r12+0A8h]
0x1800921ff  cmp     rbx, r12
0x180092202  jz      loc_180092909
0x180092208  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl(void)'::`2'::impl
0x18009220f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(void)
0x180092214  test    al, al
0x180092216  jz      short loc_180092223
0x180092218  add     r15d, r13d
0x18009221b  mov     [rsp+498h+var_3FC], r15d
0x180092223  mov     dword ptr [rsp+498h+var_478], edi
0x180092227  lea     r9, ??_R0?AVDCCSP@@@8; DCCSP `RTTI Type Descriptor'
0x18009222e  lea     r8, ??_R0?AVDCProvider@@@8; DCProvider `RTTI Type Descriptor'
0x180092235  xor     edx, edx
0x180092237  mov     rcx, [rbx]
0x18009223a  call    __RTDynamicCast_0
0x18009223f  mov     r14, rax
0x180092242  mov     [rsp+498h+var_400], edi
0x180092249  mov     r13, [rax+10h]
0x18009224d  mov     r15, [rax+18h]
0x180092251  cmp     r13, r15
0x180092254  jz      loc_1800928EA
0x18009225a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl(void)'::`2'::impl
0x180092261  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(void)
0x180092266  test    al, al
0x180092268  jz      short loc_180092271
0x18009226a  inc     [rsp+498h+var_400]
0x180092271  mov     rcx, [rsp+498h+var_3E8]
0x180092279  cmp     [rcx+38h], rsi
0x18009227d  jbe     short loc_180092285
0x18009227f  mov     rdx, [rcx+20h]
0x180092283  jmp     short loc_180092289
0x180092285  lea     rdx, [rcx+20h]
0x180092289  mov     rax, [rsp+498h+var_3D0]
0x180092291  lea     rcx, [rax+20h]
0x180092295  cmp     [rax+38h], rsi
0x180092299  jbe     short loc_18009229E
0x18009229b  mov     rcx, [rcx]
0x18009229e  call    cs:__imp__o__wcsicmp
0x1800922a4  test    eax, eax
0x1800922a6  jnz     loc_1800928BF
0x1800922ac  lea     rdx, [r14+58h]
0x1800922b0  cmp     [r14+70h], rsi
0x1800922b4  jbe     short loc_1800922B9
0x1800922b6  mov     rdx, [rdx]
0x1800922b9  mov     rax, [rsp+498h+var_3F8]
0x1800922c1  lea     rcx, [rax+58h]
0x1800922c5  cmp     [rax+70h], rsi
0x1800922c9  jbe     short loc_1800922CE
0x1800922cb  mov     rcx, [rcx]
0x1800922ce  call    cs:__imp__o__wcsicmp
0x1800922d4  test    eax, eax
0x1800922d6  jnz     loc_1800928BF
0x1800922dc  lea     rcx, [rsp+498h+var_1B8]
0x1800922e4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800922e9  nop
0x1800922ea  lea     rcx, [rsp+498h+var_1D8]
0x1800922f2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800922f7  nop
0x1800922f8  lea     rcx, [rsp+498h+var_2F8]
0x180092300  cmp     [rsp+498h+var_2E0], rsi
0x180092308  cmova   rcx, [rsp+498h+var_2F8]
0x180092311  lea     rdx, aVpnv2; "vpnv2"
0x180092318  call    cs:__imp__o__wcsicmp
0x18009231e  test    eax, eax
0x180092320  jz      short loc_180092350
0x180092322  lea     rcx, [rsp+498h+var_2F8]
0x18009232a  cmp     [rsp+498h+var_2E0], rsi
0x180092332  cmova   rcx, [rsp+498h+var_2F8]
0x18009233b  lea     rdx, aWifi; "wifi"
0x180092342  call    cs:__imp__o__wcsicmp
0x180092348  test    eax, eax
0x18009234a  jnz     loc_180092441
0x180092350  xor     r8d, r8d
0x180092353  lea     rdx, asc_18013EB9C; "/"
0x18009235a  mov     rcx, [rsp+498h+var_410]
0x180092362  mov     rcx, [rcx]
0x180092365  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x18009236a  mov     r9, rax
0x18009236d  xor     r8d, r8d
0x180092370  lea     rdx, [rsp+498h+var_318]
0x180092378  mov     rax, [rsp+498h+var_410]
0x180092380  mov     rcx, [rax]
0x180092383  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180092388  mov     rdx, rax
0x18009238b  lea     rcx, [rsp+498h+var_1D8]
0x180092393  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180092398  lea     rcx, [rsp+498h+var_318]
0x1800923a0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800923a5  nop
0x1800923a6  xor     r8d, r8d
0x1800923a9  lea     rdx, asc_18013EB9C; "/"
0x1800923b0  mov     rcx, [r13+0]
0x1800923b4  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x1800923b9  mov     r9, rax
0x1800923bc  xor     r8d, r8d
0x1800923bf  lea     rdx, [rsp+498h+var_318]
0x1800923c7  mov     rcx, [r13+0]
0x1800923cb  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800923d0  mov     rdx, rax
0x1800923d3  lea     rcx, [rsp+498h+var_1B8]
0x1800923db  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800923e0  lea     rcx, [rsp+498h+var_318]
0x1800923e8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800923ed  nop
0x1800923ee  lea     rdx, [rsp+498h+var_1B8]
0x1800923f6  cmp     [rsp+498h+var_1A0], rsi
0x1800923fe  cmova   rdx, [rsp+498h+var_1B8]
0x180092407  lea     rcx, [rsp+498h+var_1D8]
0x18009240f  cmp     [rsp+498h+var_1C0], rsi
0x180092417  cmova   rcx, [rsp+498h+var_1D8]
0x180092420  call    cs:__imp__o__wcsicmp
0x180092426  mov     ecx, [rsp+498h+var_404]
0x18009242d  movzx   ecx, cl
0x180092430  test    eax, eax
0x180092432  mov     eax, 1
0x180092437  cmovz   ecx, eax
0x18009243a  mov     [rsp+498h+var_404], ecx
0x180092441  mov     rdx, [r13+0]
0x180092445  cmp     [rdx+18h], rsi
0x180092449  jbe     short loc_18009244E
0x18009244b  mov     rdx, [rdx]
0x18009244e  mov     rax, [rsp+498h+var_410]
0x180092456  mov     rcx, [rax]
0x180092459  cmp     [rcx+18h], rsi
0x18009245d  jbe     short loc_180092462
0x18009245f  mov     rcx, [rcx]
0x180092462  call    cs:__imp__o__wcsicmp
0x180092468  test    eax, eax
0x18009246a  jnz     loc_1800928A4
0x180092470  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl(void)'::`2'::impl
0x180092477  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(void)
0x18009247c  mov     r12, [rsp+498h+var_3E8]
0x180092484  test    al, al
0x180092486  jz      loc_180092881
0x18009248c  cmp     dword ptr [r12+114h], 2
0x180092495  jnz     loc_180092881
0x18009249b  mov     r14, [rsp+498h+var_410]
0x1800924a3  test    dword ptr [r12+2A4h], 400h
0x1800924af  jz      loc_180092889
0x1800924b5  mov     rdx, [r13+0]
0x1800924b9  mov     r8, [r14]
0x1800924bc  mov     ecx, [r8+0A4h]
0x1800924c3  cmp     ecx, [rdx+0A4h]
0x1800924c9  jnz     loc_18009277A
0x1800924cf  movzx   ebx, dil
0x1800924d3  cmp     ecx, esi
0x1800924d5  jg      loc_18009261F
0x1800924db  jz      loc_18009272C
0x1800924e1  test    ecx, ecx
0x1800924e3  jz      loc_18009260D
0x1800924e9  sub     ecx, 1
0x1800924ec  jz      loc_18009263C
0x1800924f2  sub     ecx, 1
0x1800924f5  jz      loc_1800926A5
0x1800924fb  sub     ecx, 2
0x1800924fe  jz      loc_18009263C
0x180092504  sub     ecx, 1
0x180092507  jz      loc_18009260D
  ... truncated ...
```
