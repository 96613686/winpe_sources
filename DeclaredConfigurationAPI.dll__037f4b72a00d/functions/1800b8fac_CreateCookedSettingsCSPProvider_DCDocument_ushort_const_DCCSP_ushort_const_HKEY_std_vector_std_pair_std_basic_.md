# CreateCookedSettingsCSPProvider(DCDocument &,ushort const *,DCCSP *,ushort const *,HKEY__ *,std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> *)

- ea: `0x1800b8fac`
- end: `0x1800bac9e`
- name: `?CreateCookedSettingsCSPProvider@@YAJAEAVDCDocument@@PEBGPEAVDCCSP@@1PEAUHKEY__@@PEAV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z`
- size: `7410`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, HKEY hKey, __int64)`
- caller_count: `1`
- callee_count: `53`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800882a0`

## callees

- `0x18000b9e0`
- `0x18000bebc`
- `0x1800117dc`
- `0x180014348`
- `0x18001438c`
- `0x1800143c8`
- `0x180018ac0`
- `0x180018b30`
- `0x180018cc4`
- `0x180019208`
- `0x180019270`
- `0x1800192b4`
- `0x180019d38`
- `0x18001aaec`
- `0x18001bc98`
- `0x18001c300`
- `0x18001ce5c`
- `0x18001d0b0`
- `0x18001d198`
- `0x18001db48`
- `0x18001dea8`
- `0x18001def8`
- `0x180048fe8`
- `0x18004a974`
- `0x18004bc88`
- `0x18004dc70`
- `0x18004ec50`
- `0x1800546f0`
- `0x180054b28`
- `0x180056c10`
- `0x18005ec48`
- `0x18009c3e4`
- `0x1800a01b0`
- `0x1800a01ec`
- `0x1800a0de4`
- `0x1800ad900`
- `0x1800adcb0`
- `0x1800addc4`
- `0x1800adee0`
- `0x1800b8fac`
- `0x1800bfff8`
- `0x1800c41a8`
- `0x1800c4320`
- `0x1800c445c`
- `0x1800c4640`
- `0x1800f5c8c`
- `0x1800f9d70`
- `0x1800f9e64`
- `0x180100e3c`
- `0x18010136c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b92c3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b92ea`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b930f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b95b1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b9756`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b9ada`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b9bab`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b92c3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b92ea`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b930f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b95b1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b9756`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b9ada`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b9bab`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800b956b`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800b9a94`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ba7df`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ba883`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ba7df`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ba883`
- `DeclaredConfiguration!DMOrchestratorRefreshPerDocument` at `0x1800ba161`
- `DeclaredConfiguration!DMOrchestratorRefreshPerDocument` at `0x1800ba161`

## string_xrefs

- `0x1800b9c6e`: `registry`
- `0x1800b9fb1`: `registry`
- `0x1800ba61d`: `UriCount`
- `0x1800ba939`: `ResourceSuccessUri`
- `0x1800ba9f7`: `ResourceFailureUri`
- `0x1800baab5`: `ResourceInProgressUri`
- `0x1800ba428`: `DeclaredConfiguration_CreateCookedSettings`
- `0x1800ba421`: `WriteCookedURI`
- `0x1800b9816`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800b9d8c`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800ba5d5`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800ba810`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800ba8b4`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800bab6e`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800b9c02`: `CreateCookedSettingsCSPProvider`
- `0x1800b9d46`: `CreateCookedSettingsCSPProvider`
- `0x1800ba06a`: `CreateCookedSettingsCSPProvider`
- `0x1800ba0ff`: `CreateCookedSettingsCSPProvider`
- `0x1800ba182`: `CreateCookedSettingsCSPProvider`
- `0x1800ba1b3`: `CreateCookedSettingsCSPProvider`
- `0x1800b9bfb`: `uriMap - conflict detected`
- `0x1800b9ef5`: `IsUriConflicted - conflict detected`

## pseudocode

```c
// Hidden C++ exception states: #wind=39 #try_helpers=1
__int64 __fastcall CreateCookedSettingsCSPProvider(
        unsigned __int16 *a1,
        OLECHAR *a2,
        __int64 a3,
        __int64 a4,
        HKEY hKey,
        __int64 a6)
{
  __int64 v6; // r13
  HKEY v7; // rdi
  HKEY v8; // r12
  __int64 last_of; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  const unsigned __int16 *v13; // rdx
  _QWORD *v14; // rax
  HKEY v15; // rsi
  HKEY v16; // rax
  _QWORD *v17; // rbx
  HKEY v18; // rcx
  __int64 v19; // rcx
  int v20; // eax
  _QWORD *v21; // rax
  _WORD *v22; // rdx
  __int64 v23; // r8
  const unsigned __int16 *v24; // rcx
  int v25; // eax
  __int64 v26; // rsi
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  _BYTE *v30; // rcx
  unsigned __int16 **v31; // rbx
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // r8
  _QWORD *v38; // r9
  _QWORD *v39; // rax
  int v40; // r9d
  _QWORD *v41; // rdx
  _QWORD *v42; // rcx
  char *v43; // r9
  __int64 v44; // rsi
  _QWORD *v45; // rbx
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  char *v51; // r9
  unsigned __int16 **v52; // rcx
  _QWORD *v54; // rax
  _WORD *v55; // rdx
  __int64 v56; // r8
  const unsigned __int16 *v57; // rcx
  int v58; // eax
  __int64 v59; // rsi
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rax
  _BYTE *v63; // rcx
  unsigned __int16 **v64; // rbx
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // r8
  _QWORD *v71; // r9
  _QWORD *v72; // rax
  int v73; // r9d
  _QWORD *v74; // rdx
  _QWORD *v75; // rcx
  char *v76; // r9
  __int64 v77; // rdx
  const unsigned __int16 **v78; // rsi
  const unsigned __int16 *v79; // rdx
  __int64 v80; // rbx
  __int64 v81; // rcx
  CDeclaredConfigurationLogger *Logger; // rax
  const unsigned __int16 *v83; // r9
  const unsigned __int16 *v84; // rcx
  int v85; // eax
  const unsigned __int16 *v86; // rcx
  const unsigned __int16 *v87; // rdx
  int v88; // ebx
  const unsigned __int16 *v89; // rdx
  CDeclaredConfigurationLogger *v90; // rax
  const unsigned __int16 *v91; // r9
  int v92; // ecx
  const unsigned __int16 **v93; // rbx
  const unsigned __int16 *v94; // r9
  const void **v95; // rsi
  const unsigned __int16 *v96; // r8
  const unsigned __int16 *v97; // rcx
  _WORD *v98; // rdx
  HKEY v99; // rbx
  __int64 v100; // r8
  __int64 v101; // r8
  __int64 v102; // rax
  int v103; // ebx
  CDeclaredConfigurationLogger *v104; // rax
  const unsigned __int16 *v105; // r9
  const unsigned __int16 *v106; // r8
  const unsigned __int16 *v107; // r8
  const unsigned __int16 *v108; // r9
  OLECHAR *v109; // rbx
  __int64 v110; // rdx
  int v111; // eax
  const unsigned __int16 *v112; // r9
  const unsigned __int16 *v113; // rcx
  const unsigned __int16 *v114; // rdx
  bool v115; // bl
  const unsigned __int16 *v116; // r9
  const unsigned __int16 *v117; // rdx
  CDeclaredConfigurationLogger *v118; // rax
  const unsigned __int16 *v119; // r9
  int v120; // ecx
  char v121; // al
  const unsigned __int16 *v122; // r9
  HKEY v123; // rbx
  __int64 v124; // rax
  _QWORD *v125; // r8
  _QWORD *v126; // rdx
  unsigned __int16 **v127; // rcx
  CDeclaredConfigurationLogger *v128; // rax
  const unsigned __int16 *v129; // r9
  unsigned __int16 *v130; // rbx
  _QWORD *v131; // rsi
  char IsEnabled; // al
  int v133; // ebx
  char *v134; // rcx
  HKEY v135; // rsi
  __int64 v136; // r8
  int v137; // r9d
  int v138; // ebx
  CDeclaredConfigurationLogger *v139; // rax
  const unsigned __int16 *v140; // r9
  const char *v141; // r9
  __int64 v142; // rax
  __int64 v143; // rax
  char v144; // al
  const unsigned __int16 *v145; // rdx
  unsigned int v146; // r9d
  signed int v147; // esi
  const unsigned __int16 *v148; // r9
  const unsigned __int16 *v149; // rdx
  int v150; // eax
  __int64 v151; // rdx
  const unsigned __int16 *v152; // rdx
  const unsigned __int16 *v153; // rdx
  const unsigned __int16 *v154; // rdx
  const unsigned __int16 *v155; // rdx
  const unsigned __int16 *v156; // rdx
  const WCHAR *v157; // rdx
  LSTATUS v158; // eax
  LSTATUS v159; // eax
  _QWORD *v160; // rdi
  _QWORD *j; // rbx
  const unsigned __int16 *v162; // r9
  const unsigned __int16 *v163; // rdx
  int v164; // eax
  const unsigned __int16 *v165; // r9
  const unsigned __int16 *v166; // rdx
  const unsigned __int16 *v167; // r9
  const unsigned __int16 *v168; // rdx
  const unsigned __int16 *v169; // r9
  const unsigned __int16 *v170; // rdx
  const unsigned __int16 *v171; // r9
  const unsigned __int16 *v172; // rdx
  const unsigned __int16 *v173; // r9
  const unsigned __int16 *v174; // rdx
  __int64 v175; // rdx
  int dwOptions; // [rsp+20h] [rbp-688h]
  int dwOptionsa; // [rsp+20h] [rbp-688h]
  int dwOptionsb; // [rsp+20h] [rbp-688h]
  int dwOptionsc; // [rsp+20h] [rbp-688h]
  const unsigned __int16 *dwOptionsd; // [rsp+20h] [rbp-688h]
  const unsigned __int16 *dwOptionse; // [rsp+20h] [rbp-688h]
  const unsigned __int16 *dwOptionsf; // [rsp+20h] [rbp-688h]
  int dwOptionsg; // [rsp+20h] [rbp-688h]
  int dwOptionsh; // [rsp+20h] [rbp-688h]
  int dwOptionsi; // [rsp+20h] [rbp-688h]
  int dwOptionsj; // [rsp+20h] [rbp-688h]
  const unsigned __int16 *samDesired; // [rsp+28h] [rbp-680h]
  __int64 *lpSecurityAttributes; // [rsp+30h] [rbp-678h]
  __int64 v189; // [rsp+50h] [rbp-658h]
  int v190; // [rsp+70h] [rbp-638h]
  __int16 v191; // [rsp+80h] [rbp-628h] BYREF
  char v192; // [rsp+82h] [rbp-626h] BYREF
  HKEY v193; // [rsp+88h] [rbp-620h] BYREF
  HKEY v194[2]; // [rsp+90h] [rbp-618h] BYREF
  int v195[2]; // [rsp+A0h] [rbp-608h] BYREF
  unsigned int v196[2]; // [rsp+A8h] [rbp-600h]
  OLECHAR *psz; // [rsp+B0h] [rbp-5F8h]
  __int64 v198; // [rsp+B8h] [rbp-5F0h]
  HKEY v199; // [rsp+C0h] [rbp-5E8h]
  __int64 v200; // [rsp+C8h] [rbp-5E0h]
  unsigned __int16 *v201; // [rsp+D0h] [rbp-5D8h]
  HKEY i; // [rsp+D8h] [rbp-5D0h]
  __int64 v203; // [rsp+E0h] [rbp-5C8h] BYREF
  HKEY *v204; // [rsp+E8h] [rbp-5C0h] BYREF
  HKEY phkResult; // [rsp+F0h] [rbp-5B8h] BYREF
  char v206; // [rsp+F8h] [rbp-5B0h]
  int v207; // [rsp+100h] [rbp-5A8h] BYREF
  _QWORD *v208; // [rsp+108h] [rbp-5A0h]
  __int64 v209; // [rsp+110h] [rbp-598h]
  __int64 v210; // [rsp+118h] [rbp-590h] BYREF
  __int128 v211; // [rsp+120h] [rbp-588h]
  __int64 v212; // [rsp+130h] [rbp-578h]
  __int64 v213; // [rsp+138h] [rbp-570h]
  OLECHAR *v214; // [rsp+140h] [rbp-568h]
  __int64 v215; // [rsp+148h] [rbp-560h] BYREF
  char v216; // [rsp+150h] [rbp-558h]
  char v217; // [rsp+158h] [rbp-550h] BYREF
  char v218; // [rsp+160h] [rbp-548h] BYREF
  __int64 v219; // [rsp+170h] [rbp-538h] BYREF
  char v220; // [rsp+180h] [rbp-528h] BYREF
  char v221; // [rsp+190h] [rbp-518h] BYREF
  _BYTE v222[8]; // [rsp+198h] [rbp-510h] BYREF
  _BYTE v223[16]; // [rsp+1A0h] [rbp-508h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+1B0h] [rbp-4F8h] BYREF
  unsigned __int64 v225; // [rsp+1C8h] [rbp-4E0h]
  _QWORD Src[3]; // [rsp+1D0h] [rbp-4D8h] BYREF
  unsigned __int64 v227; // [rsp+1E8h] [rbp-4C0h]
  _QWORD v228[3]; // [rsp+1F0h] [rbp-4B8h] BYREF
  unsigned __int64 v229; // [rsp+208h] [rbp-4A0h]
  unsigned __int16 *v230[3]; // [rsp+210h] [rbp-498h] BYREF
  unsigned __int64 v231; // [rsp+228h] [rbp-480h]
  unsigned __int16 *v232[4]; // [rsp+230h] [rbp-478h] BYREF
  unsigned __int16 *v233[3]; // [rsp+250h] [rbp-458h] BYREF
  unsigned __int64 v234; // [rsp+268h] [rbp-440h]
  __int64 v235[4]; // [rsp+270h] [rbp-438h] BYREF
  _BYTE v236[32]; // [rsp+290h] [rbp-418h] BYREF
  _BYTE v237[32]; // [rsp+2B0h] [rbp-3F8h] BYREF
  _BYTE v238[32]; // [rsp+2D0h] [rbp-3D8h] BYREF
  unsigned __int16 *v239[3]; // [rsp+2F0h] [rbp-3B8h] BYREF
  unsigned __int64 v240; // [rsp+308h] [rbp-3A0h]
  _QWORD v241[4]; // [rsp+310h] [rbp-398h] BYREF
  _QWORD v242[4]; // [rsp+330h] [rbp-378h] BYREF
  _BYTE v243[32]; // [rsp+350h] [rbp-358h] BYREF
  _BYTE v244[32]; // [rsp+370h] [rbp-338h] BYREF
  unsigned __int16 *v245[3]; // [rsp+390h] [rbp-318h] BYREF
  unsigned __int64 v246; // [rsp+3A8h] [rbp-300h]
  unsigned __int16 *v247[4]; // [rsp+3B0h] [rbp-2F8h] BYREF
  unsigned __int16 *v248[4]; // [rsp+3D0h] [rbp-2D8h] BYREF
  unsigned __int16 *v249[4]; // [rsp+3F0h] [rbp-2B8h] BYREF
  unsigned __int16 *v250[4]; // [rsp+410h] [rbp-298h] BYREF
  unsigned __int16 *v251[4]; // [rsp+430h] [rbp-278h] BYREF
  unsigned __int16 *v252[4]; // [rsp+450h] [rbp-258h] BYREF
  __int64 v253[24]; // [rsp+470h] [rbp-238h] BYREF
  __int64 v254[38]; // [rsp+530h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6A8h] [rbp+0h]

  v198 = a4;
  v6 = a3;
  psz = a2;
  v199 = (HKEY)a1;
  v214 = a2;
  v193 = (HKEY)a1;
  v7 = (HKEY)a1;
  v201 = a1;
  *(_QWORD *)v195 = a2;
  *(_QWORD *)v196 = a3;
  v203 = a4;
  v8 = hKey;
  i = hKey;
  v200 = a6;
  std::wstring::wstring((__int64)v232, (__int64)&word_180142E98);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
  {
    if ( *(_DWORD *)(v6 + 128) == 1 )
    {
      last_of = std::wstring::find_last_of(v6 + 88, L"/");
      try
      {
        v10 = std::wstring::substr(v6 + 88, v235, last_of + 1, -1);
        std::wstring::operator=(v232, v10);
        std::wstring::_Tidy_deallocate(v235);
      }
      catch ( ... )
      {
        v199 = v193;
        v7 = v193;
        psz = *(OLECHAR **)v195;
        goto LABEL_6;
      }
    }
    else
    {
      std::wstring::_Assign<unsigned short>((char **)v232, L"___reservedNeverUsed___", (char *)0x17);
    }
  }
  else
  {
    v11 = std::wstring::find_last_of(v6 + 88, L"/");
    try
    {
      v12 = std::wstring::substr(v6 + 88, v235, v11 + 1, -1);
      std::wstring::operator=(v232, v12);
      std::wstring::_Tidy_deallocate(v235);
    }
    catch ( ... )
    {
      v199 = v193;
      v7 = v193;
      psz = *(OLECHAR **)v195;
LABEL_6:
      v8 = i;
      v198 = v203;
      v6 = *(_QWORD *)v196;
    }
  }
  v13 = (const unsigned __int16 *)v232;
  if ( v232[3] > (unsigned __int16 *)7 )
    v13 = v232[0];
  CspSchema::CspSchema((CspSchema *)v254, v13);
  LODWORD(v194[0]) = CspSchema::InitializeFromSchemaStore((CspSchema *)v254);
  v196[0] = 0;
  v191 = 0;
  v192 = 0;
  v209 = 0;
  v14 = operator new(0xF0u);
  *v14 = v14;
  v14[1] = v14;
  v208 = v14;
  v210 = 0;
  v211 = 0;
  v212 = 7;
  v213 = 8;
  v207 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<HierarchyObjectItem>>>>>>>::_Assign_grow(
    &v210,
    16,
    v14);
  v15 = *(HKEY *)(v6 + 16);
  v16 = *(HKEY *)(v6 + 24);
  for ( i = v16; ; v16 = i )
  {
    v193 = v15;
    if ( v15 == v16 )
      break;
    ResourceValidationUrisAndValues::ResourceValidationUrisAndValues((ResourceValidationUrisAndValues *)v253);
    v17 = v7 + 128;
    if ( *((_QWORD *)v7 + 67) <= 7u )
      v18 = v7 + 128;
    else
      v18 = (HKEY)*v17;
    if ( (unsigned int)_o__wcsicmp(v18, L"msftinventory") )
    {
      v19 = *((_QWORD *)v7 + 67) <= 7u ? (__int64)(v7 + 128) : *v17;
      if ( (unsigned int)_o__wcsicmp(v19, L"msftextensibilitymiproviderinventory") )
      {
        if ( *((_QWORD *)v7 + 67) > 7u )
          v17 = (_QWORD *)*v17;
        if ( (unsigned int)_o__wcsicmp(v17, L"msftonetime") && !*(_BYTE *)(v6 + 81) )
        {
          std::wstring::wstring((__int64)v228);
          std::wstring::wstring((__int64)Src);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
          {
            std::wstring::wstring((__int64)v233);
            v20 = *(_DWORD *)(v6 + 128);
            if ( v20 == 1 )
            {
              v21 = (_QWORD *)(v6 + 88);
              if ( *(_QWORD *)(v6 + 112) > 7u )
                v21 = (_QWORD *)*v21;
              v22 = (_WORD *)v21 + 2;
              v23 = -1;
              do
                ++v23;
              while ( v22[v23] );
              std::wstring::_Assign<unsigned short>((char **)v233, v22, (char *)v23);
              v24 = (const unsigned __int16 *)v233;
              if ( v234 > 7 )
                v24 = v233[0];
              v25 = DCDoesCspNeedPrefix(v24);
              try
              {
                v26 = *(_QWORD *)v15;
                if ( v25 )
                {
                  v31 = v233;
                  if ( v234 > 7 )
                    v31 = (unsigned __int16 **)v233[0];
                  v32 = std::operator+<unsigned short>(v237, L"./", v7 + 8);
                  v33 = std::operator+<unsigned short>(v244, v32, L"/");
                  v34 = std::operator+<unsigned short>(v230, v33, v31);
                  v35 = std::operator+<unsigned short>(v243, v34, L"/");
                  v36 = std::operator+<unsigned short>(v236, v35, v26);
                  std::wstring::operator=(v228, v36);
                  std::wstring::_Tidy_deallocate(v236);
                  std::wstring::_Tidy_deallocate(v243);
                  std::wstring::_Tidy_deallocate(v230);
                  std::wstring::_Tidy_deallocate(v244);
                  v30 = v237;
                }
                else
                {
                  v27 = std::operator+<unsigned short>(v236, L"./", v233);
                  v28 = std::operator+<unsigned short>(v243, v27, L"/");
                  v29 = std::operator+<unsigned short>(v230, v28, v26);
                  std::wstring::operator=(v228, v29);
                  std::wstring::_Tidy_deallocate(v230);
                  std::wstring::_Tidy_deallocate(v243);
                  v30 = v236;
                }
                std::wstring::_Tidy_deallocate(v30);
                v38 = v228;
                if ( v229 > 7 )
                  v38 = (_QWORD *)v228[0];
                v39 = (_QWORD *)std::wstring::end(v228, &v203, v37, v38);
                v41 = v228;
                if ( v229 > 7 )
                  LODWORD(v41) = v228[0];
                std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
                  (unsigned int)&v221,
                  (_DWORD)v41,
                  *v39,
                  v40,
                  *(__int64 *)&_o_towlower);
                std::wstring::operator=(Src, v228);
                v42 = v7 + 8;
                if ( *((_QWORD *)v7 + 7) > 7u )
                  v42 = (_QWORD *)*v42;
                if ( !(unsigned int)_o__wcsicmp(v42, L"user") )
                {
                  v43 = (char *)(v7 + 16);
                  if ( *((_QWORD *)v7 + 11) > 7u )
                    v43 = *(char **)v43;
                  std::wstring::_Replace<unsigned short>(Src, 2, 4u, v43, *((_QWORD *)v7 + 10));
                }
              }
              catch ( std::bad_alloc )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xBC1,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
                  (const char *)0x8007000ELL,
                  dwOptionsc);
                std::wstring::_Tidy_deallocate(v233);
                std::wstring::_Tidy_deallocate(Src);
                std::wstring::_Tidy_deallocate(v228);
                ResourceValidationUrisAndValues::~ResourceValidationUrisAndValues((ResourceValidationUrisAndValues *)v253);
                std::_Hash<std::_Umap_traits<std::wstring,ResourceValidationUrisAndValues,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ResourceValidationUrisAndValues>>,0>>::~_Hash<std::_Umap_traits<std::wstring,ResourceValidationUrisAndValues,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ResourceValidationUrisAndValues>>,0>>(&v207);
                CspSchema::~CspSchema((CspSchema *)v254);
                std::wstring::_Tidy_deallocate(v232);
                return 2147942414LL;
              }
            }
            else
            {
              if ( v20 != 3 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xBD6,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
                  (const char *)0x8000FFFFLL,
                  (int)dwOptionsd);
                std::wstring::_Tidy_deallocate(v233);
                std::wstring::_Tidy_deallocate(Src);
                std::wstring::_Tidy_deallocate(v228);
                ResourceValidationUrisAndValues::~ResourceValidationUrisAndValues((ResourceValidationUrisAndValues *)v253);
                std::_Hash<std::_Umap_traits<std::wstring,ResourceValidationUrisAndValues,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ResourceValidationUrisAndValues>>,0>>::~_Hash<std::_Umap_traits<std::wstring,ResourceValidationUrisAndValues,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ResourceValidationUrisAndValues>>,0>>(&v207);
                CspSchema::~CspSchema((CspSchema *)v254);
                std::wstring::_Tidy_deallocate(v232);
                return 2147549183LL;
              }
              try
              {
                v44 = *(_QWORD *)v15;
                v45 = v7 + 8;
                v46 = std::operator+<unsigned short>(v230, L"./", v7 + 8);
                v47 = std::operator+<unsigned short>(v243, v46, L"/");
                v48 = std::operator+<unsigned short>(v236, v47, v6 + 88);
                v49 = std::operator+<unsigned short>(v244, v48, L"/");
                v50 = std::operator+<unsigned short>(v237, v49, v44);
                std::wstring::operator=(v228, v50);
                std::wstring::_Tidy_deallocate(v237);
                std::wstring::_Tidy_deallocate(v244);
                std::wstring::_Tidy_deallocate(v236);
                std::wstring::_Tidy_deallocate(v243);
                std::wstring::_Tidy_deallocate(v230);
                std::wstring::operator=(Src, v228);
                if ( *((_QWORD *)v7 + 7) > 7u )
                  v45 = (_QWORD *)*v45;
                if ( !(unsigned int)_o__wcsicmp(v45, L"user") )
                {
                  v51 = (char *)(v7 + 16);
                  if ( *((_QWORD *)v7 + 11) > 7u )
                    v51 = *(char **)v51;
                  std::wstring::_Replace<unsigned short>(Src, 2, 4u, v51, *((_QWORD *)v7 + 10));
                }
              }
              catch ( std::bad_alloc )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xBD1,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
                  (const char *)0x8007000ELL,
                  dwOptionsb);
                std::wstring::_Tidy_deallocate(v233);
                std::wstring::_Tidy_deallocate(Src);
                std::wstring::_Tidy_deallocate(v228);
                ResourceValidationUrisAndValues::~ResourceValidationUrisAndValues((ResourceValidationUrisAndValues *)v253);
                std::_Hash<std::_Umap_traits<std::wstring,ResourceValidationUrisAndValues,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ResourceValidationUrisAndValues>>,0>>::~_Hash<std::_Umap_traits<std::wstring,ResourceValidationUrisAndValues,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ResourceValidationUrisAndValues>>,0>>(&v207);
                CspSchema::~CspSchema((CspSchema *)v254);
                std::wstring::_Tidy_deallocate(v232);
                return 2147942414LL;
              }
            }
            v52 = v233;
          }
          else
          {
            std::wstring::wstring((__int64)v230);
            v54 = (_QWORD *)(v6 + 88);
            if ( *(_QWORD *)(v6 + 112) > 7u )
              v54 = (_QWORD *)*v54;
            v55 = (_WORD *)v54 + 2;
            v56 = -1;
            do
              ++v56;
            while ( v55[v56] );
            std::wstring::_Assign<unsigned short>((char **)v230, v55, (char *)v56);
            v57 = (const unsigned __int16 *)v230;
            if ( v231 > 7 )
              v57 = v230[0];
            v58 = DCDoesCspNeedPrefix(v57);
            try
            {
              v59 = *(_QWORD *)v15;
              if ( v58 )
              {
                v64 = v230;
                if ( v231 > 7 )
                  v64 = (unsigned __int16 **)v230[0];
                v65 = std::operator+<unsigned short>(v238, L"./", v7 + 8);
                v66 = std::operator+<unsigned short>(v243, v65, L"/");
                v67 = std::operator+<unsigned short>(v236, v66, v64);
                v68 = std::operator+<unsigned short>(v244, v67, L"/");
                v69 = std::operator+<unsigned short>(v237, v68, v59);
                std::wstring::operator=(v228, v69);
                std::wstring::_Tidy_deallocate(v237);
                std::wstring::_Tidy_deallocate(v244);
                std::wstring::_Tidy_deallocate(v236);
                std::wstring::_Tidy_deallocate(v243);
                v63 = v238;
              }
              else
              {
                v60 = std::operator+<unsigned short>(v236, L"./", v230);
                v61 = std::operator+<unsigned short>(v244, v60, L"/");
                v62 = std::operator+<unsigned short>(v237, v61, v59);
                std::wstring::operator=(v228, v62);
                std::wstring::_Tidy_deallocate(v237);
                std::wstring::_Tidy_deallocate(v244);
                v63 = v236;
              }
              std::wstring::_Tidy_deallocate(v63);
              v71 = v228;
              if ( v229 > 7 )
                v71 = (_QWORD *)v228[0];
              v72 = (_QWORD *)std::wstring::end(v228, v222, v70, v71);
              v74 = v228;
              if ( v229 > 7 )
                LODWORD(v74) = v228[0];
              std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
                (unsigned int)&v217,
                (_DWORD)v74,
                *v72,
                v73,
                *(__int64 *)&_o_towlower);
              std::wstring::operator=(Src, v228);
              v75 = v7 + 8;
              if ( *((_QWORD *)v7 + 7) > 7u )
                v75 = (_QWORD *)*v75;
              if ( !(unsigned int)_o__wcsicmp(v75, L"user") )
              {
                v76 = (char *)(v7 + 16);
                if ( *((_QWORD *)v7 + 11) > 7u )
                  v76 = *(char **)v76;
                std::wstring::_Replace<unsigned short>(Src, 2, 4u, v76, *((_QWORD *)v7 + 10));
              }
            }
            catch ( std::bad_alloc )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xBF1,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
                (const char *)0x8007000ELL,
                dwOptionsa);
              std::wstring::_Tidy_deallocate(v230);
              std::wstring::_Tidy_deallocate(Src);
              std::wstring::_Tidy_deallocate(v228);
              ResourceValidationUrisAndValues::~ResourceValidationUrisAndValues((ResourceValidationUrisAndValues *)v253);
              std::_Hash<std::_Umap_traits<std::wstring,ResourceValidationUrisAndValues,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ResourceValidationUrisAndValues>>,0>>::~_Hash<std::_Umap_traits<std::wstring,ResourceValidationUrisAndValues,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ResourceValidationUrisAndValues>>,0>>(&v207);
              CspSchema::~CspSchema((CspSchema *)v254);
              std::wstring::_Tidy_deallocate(v232);
              return 2147942414LL;
            }
            v52 = v230;
          }
          std::wstring::_Tidy_deallocate(v52);
          LOBYTE(v77) = 1;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority>::ReportUsage(
            `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority>::GetImpl'::`2'::impl,
            v77);
          if ( *((_DWORD *)v7 + 69) != 2
            && !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority_ForAll>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority_ForAll>::GetImpl'::`2'::impl) )
          {
            std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<std::wstring &,std::wstring &>(
              uriMap,
              (__int64)&v215,
              v228,
              (__int64)v7);
            if ( v216
              || ((v78 = (const unsigned __int16 **)v199, *((_QWORD *)v7 + 3) <= 7u)
                ? (v79 = (const unsigned __int16 *)v7)
                : (v79 = *(const unsigned __int16 **)v199),
                  (v80 = v215, *(_QWORD *)(v215 + 72) <= 7u) ? (v81 = v215 + 48) : (v81 = *(_QWORD *)(v215 + 48)),
                  !(unsigned int)_o__wcsicmp(v81, v79)) )
            {
              std::wstring::_Assign<unsigned short>((char **)(*(_QWORD *)v193 + 96LL), &word_180142E98, 0);
            }
            else
            {
              std::wstring::operator=(*(_QWORD *)v193 + 96LL, v80 + 48);
              *(_DWORD *)(*(_QWORD *)v193 + 160LL) = -2100297719;
              Logger = CDeclaredConfigurationLogger::GetLogger();
              if ( *((_QWORD *)v7 + 3) <= 7u )
                v83 = (const unsigned __int16 *)v7;
              else
                v83 = *v78;
              CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                Logger,
                L"CreateCookedSettingsCSPProvider",
                L"uriMap - conflict detected",
                v83,
                -2100297719);
            }
            goto LABEL_183;
          }
          DCAuthorityInfo::DCAuthorityInfo((DCAuthorityInfo *)v239);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
          {
            v85 = *(_DWORD *)(v6 + 128);
            if ( v85 == 1 )
            {
              v86 = L"csp";
              goto LABEL_100;
            }
            if ( v85 == 3 )
            {
              v86 = L"registry";
LABEL_100:
              v87 = (const unsigned __int16 *)Src;
              if ( v227 > 7 )
                v87 = (const unsigned __int16 *)Src[0];
              v88 = GetCurrentAuthorityAndCheckDocumentSanity(v86, v87, psz, (struct DCAuthorityInfo *)v239);
            }
            else
            {
              v88 = -2147418113;
            }
          }
          else
          {
            v89 = (const unsigned __int16 *)Src;
            if ( v227 > 7 )
              v89 = (const unsigned __int16 *)Src[0];
            v88 = GetCurrentAuthorityAndCheckDocumentSanity(0, v89, 0, (struct DCAuthorityInfo *)v239);
          }
          if ( v88 == -2147024894 )
          {
            std::wstring::_Assign<unsigned short>((char **)(*(_QWORD *)v193 + 96LL), &word_180142E98, 0);
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OsConfigDeletionCorruptedState>::GetImpl'::`2'::impl) )
            {
              v90 = CDeclaredConfigurationLogger::GetLogger();
              v91 = (const unsigned __int16 *)Src;
              if ( v227 > 7 )
                v91 = (const unsigned __int16 *)Src[0];
              CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                v90,
                L"CreateCookedSettingsCSPProvider",
                L"GetCurrentAuthorityAndCheckDocumentSanity",
                v91,
                -2147024894);
              if ( byte_180189FC1 < 0 )
                McTemplateU0zzd_EventWriteTransfer(
                  v92,
                  (unsigned int)OrchestratorGenericFailure,
                  (unsigned int)L"CreateCookedSettingsCSPProvider",
                  (unsigned int)L"GetCurrentAuthorityAndCheckDocumentSanity",
                  2);
            }
            goto LABEL_182;
          }
          if ( v88 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xC45,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
              (const char *)(unsigned int)v88,
              (int)dwOptionsd);
            DCAuthorityInfo::~DCAuthorityInfo((DCAuthorityInfo *)v239);
            std::wstring::_Tidy_deallocate(Src);
            std::wstring::_Tidy_deallocate(v228);
            ResourceValidationUrisAndValues::~ResourceValidationUrisAndValues((ResourceValidationUrisAndValues *)v253);
            std::_Hash<std::_Umap_traits<std::wstring,ResourceValidationUrisAndValues,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ResourceValidationUrisAndValues>>,0>>::~_Hash<std::_Umap_traits<std::wstring,ResourceValidationUrisAndValues,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ResourceValidationUrisAndValues>>,0>>(&v207);
            CspSchema::~CspSchema((CspSchema *)v254);
            std::wstring::_Tidy_deallocate(v232);
            return (unsigned int)v88;
          }
          v195[0] = 0;
          v93 = (const unsigned __int16 **)(v7 + 8);
          if ( *((_QWORD *)v7 + 7) <= 7u )
            v94 = (const unsigned __int16 *)(v7 + 8);
          else
            v94 = *v93;
          v95 = (const void **)v199;
          if ( *((_QWORD *)v7 + 3) <= 7u )
            v96 = (const unsigned __int16 *)v7;
          else
            v96 = *(const unsigned __int16 **)v199;
          if ( !IsUriConflicted(v84, psz, v96, v94, dwOptionsd, (struct DCAuthorityInfo *)v239, v195) )
            goto LABEL_182;
          if ( v195[0] == -2100297718 )
          {
            if ( *((_QWORD *)v7 + 3) <= 7u )
              v98 = v7;
            else
              v98 = *v95;
            v99 = v193;
            v100 = -1;
            do
              ++v100;
            while ( v98[v100] );
            std::wstring::_Assign<unsigned short>((char **)(*(_QWORD *)v193 + 96LL), v98, (char *)v100);
            v101 = -1;
            do
              ++v101;
            while ( v214[v101] );
            std::wstring::_Assign<unsigned short>((char **)(*(_QWORD *)v99 + 128LL), psz, (char *)v101);
            v102 = *(_QWORD *)v99;
            v103 = -2100297718;
            *(_DWORD *)(v102 + 160) = -2100297718;
            v104 = CDeclaredConfigurationLogger::GetLogger();
            if ( *((_QWORD *)v7 + 3) <= 7u )
              v105 = (const unsigned __int16 *)v7;
            else
              v105 = (const unsigned __int16 *)*v95;
            v106 = L"IsUriConflicted - conflict detected";
            goto LABEL_169;
          }
          v195[0] = 0;
          if ( *((_QWORD *)v7 + 7) > 7u )
            v93 = (const unsigned __int16 **)*v93;
          if ( *((_QWORD *)v7 + 3) <= 7u )
            v107 = (const unsigned __int16 *)v7;
          else
            v107 = (const unsigned __int16 *)*v95;
          v108 = (const unsigned __int16 *)v93;
          v109 = psz;
          if ( IsAllowedByPrecedenceOrder(v97, psz, v107, v108, dwOptionse, (struct DCAuthorityInfo *)v239, v195) )
          {
            v125 = v242;
            if ( v242[3] > 7u )
              v125 = (_QWORD *)v242[0];
            v126 = v241;
            if ( v241[3] > 7u )
              v126 = (_QWORD *)v241[0];
            v127 = v239;
            if ( v240 > 7 )
              v127 = (unsigned __int16 **)v239[0];
            DMOrchestratorRefreshPerDocument(v127, v126, v125);
            v128 = CDeclaredConfigurationLogger::GetLogger();
            if ( *((_QWORD *)v7 + 3) <= 7u )
              v129 = (const unsigned __int16 *)v7;
            else
              v129 = (const unsigned __int16 *)*v95;
            CDeclaredConfigurationLogger::LogOrchestratorGenericInfo(
              v128,
              L"CreateCookedSettingsCSPProvider",
              L"IsAllowedByPrecedenceOrder - not allowed",
              v129);
            if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) == 0 )
              goto LABEL_182;
            v121 = v195[0];
            v122 = L"IsAllowedByPrecedenceOrder - not allowed";
LABEL_181:
            McTemplateU0zzd_EventWriteTransfer(
              v120,
              (unsigned int)OrchestratorGenericInformation,
              (unsigned int)L"CreateCookedSettingsCSPProvider",
              (_DWORD)v122,
              v121);
          }
          else
          {
            LOBYTE(v110) = 1;
            wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority_DriftControl>::ReportUsage(
              `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_MultipleAuthority_DriftControl>::GetImpl'::`2'::impl,
              v110);
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
            {
              if ( *((_QWORD *)v7 + 3) <= 7u )
                v116 = (const unsigned __int16 *)v7;
              else
                v116 = (const unsigned __int16 *)*v95;
              v117 = (const unsigned __int16 *)Src;
              if ( v227 > 7 )
                v117 = (const unsigned __int16 *)Src[0];
              v115 = IsUnblockedBecauseOfRefreshByPrecedenceOrder(
                       0,
                       v117,
                       v109,
                       v116,
                       dwOptionsf,
                       samDesired,
                       (struct DCAuthorityInfo *)v239);
              goto LABEL_160;
            }
            v111 = *(_DWORD *)(v6 + 128);
            if ( v111 == 1 )
            {
              if ( *((_QWORD *)v7 + 3) <= 7u )
                v112 = (const unsigned __int16 *)v7;
              else
                v112 = (const unsigned __int16 *)*v95;
              v113 = L"csp";
              goto LABEL_151;
            }
            if ( v111 != 3 )
              goto LABEL_166;
            v112 = *((_QWORD *)v7 + 3) <= 7u ? (const unsigned __int16 *)v7 : (const unsigned __int16 *)*v95;
            v113 = L"registry";
LABEL_151:
            v114 = (const unsigned __int16 *)Src;
            if ( v227 > 7 )
              v114 = (const unsigned __int16 *)Src[0];
            v115 = IsUnblockedBecauseOfRefreshByPrecedenceOrder(
                     v113,
                     v114,
                     v109,
                     v112,
                     dwOptionsf,
                     samDesired,
                     (struct DCAuthorityInfo *)v239);
LABEL_160:
            if ( v115 )
            {
              std::wstring::_Assign<unsigned short>((char **)(*(_QWORD *)v193 + 96LL), &word_180142E98, 0);
              v118 = CDeclaredConfigurationLogger::GetLogger();
              if ( *((_QWORD *)v7 + 3) <= 7u )
                v119 = (const unsigned __int16 *)v7;
              else
                v119 = (const unsigned __int16 *)*v95;
              CDeclaredConfigurationLogger::LogOrchestratorGenericInfo(
                v118,
                L"CreateCookedSettingsCSPProvider",
                L"IsUnblockedBecauseOfRefreshByPrecedenceOrder - unblocked",
                v119);
              if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
              {
                v121 = v115;
                v122 = L"IsUnblockedBecauseOfRefreshByPrecedenceOrder - unblocked";
                goto LABEL_181;
              }
            }
            else
            {
LABEL_166:
              v123 = v193;
              std::wstring::operator=(*(_QWORD *)v193 + 128LL, v239);
              std::wstring::operator=(*(_QWORD *)v123 + 96LL, v241);
              v124 = *(_QWORD *)v123;
              v103 = v195[0];
              *(_DWORD *)(v124 + 160) = v195[0];
              v104 = CDeclaredConfigurationLogger::GetLogger();
              v105 = (const unsigned __int16 *)v239;
              if ( v240 > 7 )
                v105 = v239[0];
              v106 = L"IsAllowedByPrecedenceOrder - not allowed";
LABEL_169:
              CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                v104,
                L"CreateCookedSettingsCSPProvider",
                v106,
                v105,
                v103);
            }
          }
LABEL_182:
          DCAuthorityInfo::~DCAuthorityInfo((DCAuthorityInfo *)v239);
LABEL_183:
          std::wstring::_Tidy_deallocate(Src);
          std::wstring::_Tidy_deallocate(v228);
        }
      }
    }
    std::wstring::wstring((__int64)v235);
    v130 = v201;
    v131 = v201 + 16;
    ++v196[0];
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl);
    v133 = *((_DWORD *)v130 + 69);
    if ( IsEnabled )
    {
      if ( *(_DWORD *)(v6 + 128) != 1 )
      {
        std::wstring::wstring((__int64)v238, v131);
        v135 = v193;
        std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(&v219, v193);
        v190 = v133;
        v189 = v200;
        lpSecurityAttributes = 0;
        goto LABEL_190;
      }
      std::wstring::wstring((__int64)v238, v131);
      v134 = &v218;
    }
    else
    {
      std::wstring::wstring((__int64)v238, v131);
      v134 = &v220;
    }
    v135 = v193;
    std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(v134, v193);
    v190 = v133;
    v189 = v200;
    lpSecurityAttributes = v254;
LABEL_190:
    v138 = WriteCookedURI(
             v8,
             v137,
             v136,
             (__int64)lpSecurityAttributes,
             (__int64)&v191,
             (__int64)&v191 + 1,
             (__int64)&v192,
             v189,
             (__int64)v235,
             (__int64)v253,
             0,
             v190);
    if ( v138 >= 0 )
    {
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
        v6 + 64,
        v223,
        v235);
      try
      {
        if ( v253[2] )
          std::_Hash<std::_Umap_traits<std::wstring,ResourceValidationUrisAndValues,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ResourceValidationUrisAndValues>>,0>>::emplace<std::wstring &,ResourceValidationUrisAndValues &>(
            (float *)&v207,
            (__int64)&v204,
            v253,
            (const struct ResourceValidationUrisAndValues *)v253);
      }
      catch ( ... )
      {
        v195[0] = wil::details::in1diag3::Return_CaughtException(
                    retaddr,
                    (void *)0xD6B,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
                    v141);
        std::wstring::_Tidy_deallocate(v235);
        v147 = v195[0];
        ResourceValidationUrisAndValues::~ResourceValidationUrisAndValues((ResourceValidationUrisAndValues *)v253);
        goto LABEL_295;
      }
    }
    else
    {
      v139 = CDeclaredConfigurationLogger::GetLogger();
      v140 = *(const unsigned __int16 **)v135;
      if ( *(_QWORD *)(*(_QWORD *)v135 + 24LL) > 7u )
        v140 = *(const unsigned __int16 **)v140;
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v139,
        L"DeclaredConfiguration_CreateCookedSettings",
        L"WriteCookedURI",
        v140,
        v138);
    }
    std::wstring::_Tidy_deallocate(v235);
    ResourceValidationUrisAndValues::~ResourceValidationUrisAndValues((ResourceValidationUrisAndValues *)v253);
    v15 = v135 + 4;
  }
  std::wstring::wstring((__int64)lpSubKey);
  try
  {
    v142 = std::wstring::wstring((__int64)v237, (__int64)L"cooked\\");
    v143 = std::operator+<unsigned short>(v238, v142, v198);
    std::wstring::operator=(lpSubKey, v143);
    std::wstring::_Tidy_deallocate(v238);
    std::wstring::_Tidy_deallocate(v237);
  }
  catch ( std::bad_alloc )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD75,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
      (const char *)0x8007000ELL,
      dwOptions);
    std::wstring::_Tidy_deallocate(lpSubKey);
    std::_Hash<std::_Umap_traits<std::wstring,ResourceValidationUrisAndValues,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ResourceValidationUrisAndValues>>,0>>::~_Hash<std::_Umap_traits<std::wstring,ResourceValidationUrisAndValues,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ResourceValidationUrisAndValues>>,0>>(&v207);
    CspSchema::~CspSchema((CspSchema *)v254);
    std::wstring::_Tidy_deallocate(v232);
    return 2147942414LL;
  }
  v144 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl);
  v145 = (const unsigned __int16 *)lpSubKey;
  if ( v144 )
    v146 = *(_DWORD *)(v6 + 128);
  else
    v146 = 1;
  if ( v225 > 7 )
    v145 = lpSubKey[0];
  v147 = DCCDNUtil_SetRegistryDWORD(v8, v145, L"ProviderType", v146);
  if ( v147 < 0 )
    goto LABEL_294;
  v148 = (const unsigned __int16 *)(v6 + 88);
  if ( *(_QWORD *)(v6 + 112) > 7u )
    v148 = *(const unsigned __int16 **)v148;
  v149 = (const unsigned __int16 *)lpSubKey;
  if ( v225 > 7 )
    v149 = lpSubKey[0];
  v150 = DCCDNUtil_SetRegistryString(v8, v149, L"csp", v148, 0);
  v147 = v150;
  if ( v150 < 0 )
  {
    v151 = 3468;
LABEL_210:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v151,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
      (const char *)(unsigned int)v150,
      dwOptionsg);
    goto LABEL_294;
  }
  v152 = (const unsigned __int16 *)lpSubKey;
  if ( v225 > 7 )
    v152 = lpSubKey[0];
  v150 = DCCDNUtil_SetRegistryDWORD(v8, v152, L"UriCount", v196[0]);
  v147 = v150;
  if ( v150 < 0 )
  {
    v151 = 3474;
    goto LABEL_210;
  }
  if ( SLODWORD(v194[0]) >= 0 )
  {
    v153 = (const unsigned __int16 *)lpSubKey;
    if ( v225 > 7 )
      v153 = lpSubKey[0];
    v150 = DCCDNUtil_SetRegistryDWORD(v8, v153, L"cspSchemaFound", 1u);
    v147 = v150;
    if ( v150 < 0 )
    {
      v151 = 3482;
      goto LABEL_210;
    }
    if ( (_BYTE)v191 )
    {
      v154 = (const unsigned __int16 *)lpSubKey;
      if ( v225 > 7 )
        v154 = lpSubKey[0];
      v150 = DCCDNUtil_SetRegistryDWORD(v8, v154, L"atomicFlagNecessary", 1u);
      v147 = v150;
      if ( v150 < 0 )
      {
        v151 = 3490;
        goto LABEL_210;
      }
    }
    if ( HIBYTE(v191) )
    {
      v155 = (const unsigned __int16 *)lpSubKey;
      if ( v225 > 7 )
        v155 = lpSubKey[0];
      v150 = DCCDNUtil_SetRegistryDWORD(v8, v155, L"oneTimeExecutionNodeNecessary", 1u);
      v147 = v150;
      if ( v150 < 0 )
      {
        v151 = 3499;
        goto LABEL_210;
      }
    }
    if ( v192 )
    {
      v156 = (const unsigned __int16 *)lpSubKey;
      if ( v225 > 7 )
        v156 = lpSubKey[0];
      v150 = DCCDNUtil_SetRegistryDWORD(v8, v156, L"checkValueNodeNecessary", 1u);
      v147 = v150;
      if ( v150 < 0 )
      {
        v151 = 3508;
        goto LABEL_210;
      }
    }
    if ( v209 )
    {
      v193 = 0;
      v204 = &v193;
      phkResult = 0;
      v206 = 1;
      v157 = (const WCHAR *)lpSubKey;
      if ( v225 > 7 )
        v157 = lpSubKey[0];
      v158 = RegCreateKeyExW(v8, v157, 0, 0, 0, 0x20106u, 0, &phkResult, 0);
      v147 = v158;
      if ( v158 > 0 )
        v147 = (unsigned __int16)v158 | 0x80070000;
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v204);
      if ( v147 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDC5,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
          (const char *)(unsigned int)v147,
          dwOptionsh);
        goto LABEL_293;
      }
      v194[0] = 0;
      v204 = v194;
      phkResult = 0;
      v206 = 1;
      v159 = RegCreateKeyExW(v193, L"resourceTracking", 0, 0, 0, 0x20106u, 0, &phkResult, 0);
      v147 = v159;
      if ( v159 > 0 )
        v147 = (unsigned __int16)v159 | 0x80070000;
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v204);
      if ( v147 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDD1,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
          (const char *)(unsigned int)v147,
          dwOptionsi);
        goto LABEL_292;
      }
      v160 = v208;
      for ( j = (_QWORD *)*v208; j != v160; j = (_QWORD *)*j )
      {
        std::wstring::wstring((__int64)v245, j + 2);
        ResourceValidationUrisAndValues::ResourceValidationUrisAndValues(
          (ResourceValidationUrisAndValues *)v247,
          (const struct ResourceValidationUrisAndValues *)(j + 6));
        v162 = (const unsigned __int16 *)v247;
        if ( v247[3] > (unsigned __int16 *)7 )
          v162 = v247[0];
        v163 = (const unsigned __int16 *)v245;
        if ( v246 > 7 )
          v163 = v245[0];
        v164 = DCCDNUtil_SetRegistryString(v194[0], v163, L"ResourceSuccessUri", v162, 0);
        v147 = v164;
        if ( v164 < 0 )
        {
          v175 = 3544;
LABEL_291:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v175,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
            (const char *)(unsigned int)v164,
            dwOptionsj);
          std::pair<std::wstring,ResourceValidationUrisAndValues>::~pair<std::wstring,ResourceValidationUrisAndValues>(v245);
LABEL_292:
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v194);
LABEL_293:
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v193);
LABEL_294:
          std::wstring::_Tidy_deallocate(lpSubKey);
LABEL_295:
          std::_Hash<std::_Umap_traits<std::wstring,ResourceValidationUrisAndValues,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ResourceValidationUrisAndValues>>,0>>::~_Hash<std::_Umap_traits<std::wstring,ResourceValidationUrisAndValues,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ResourceValidationUrisAndValues>>,0>>(&v207);
          CspSchema::~CspSchema((CspSchema *)v254);
          std::wstring::_Tidy_deallocate(v232);
          return (unsigned int)v147;
        }
        if ( v248[2] )
        {
          v165 = (const unsigned __int16 *)v248;
          if ( v248[3] > (unsigned __int16 *)7 )
            v165 = v248[0];
          v166 = (const unsigned __int16 *)v245;
          if ( v246 > 7 )
            v166 = v245[0];
          v164 = DCCDNUtil_SetRegistryString(v194[0], v166, L"ResourceSuccessValues", v165, 0);
          v147 = v164;
          if ( v164 < 0 )
          {
            v175 = 3552;
            goto LABEL_291;
          }
        }
        if ( v249[2] )
        {
          v167 = (const unsigned __int16 *)v249;
          if ( v249[3] > (unsigned __int16 *)7 )
            v167 = v249[0];
          v168 = (const unsigned __int16 *)v245;
          if ( v246 > 7 )
            v168 = v245[0];
          v164 = DCCDNUtil_SetRegistryString(v194[0], v168, L"ResourceFailureUri", v167, 0);
          v147 = v164;
          if ( v164 < 0 )
          {
            v175 = 3561;
            goto LABEL_291;
          }
        }
        if ( v250[2] )
        {
          v169 = (const unsigned __int16 *)v250;
          if ( v250[3] > (unsigned __int16 *)7 )
            v169 = v250[0];
          v170 = (const unsigned __int16 *)v245;
          if ( v246 > 7 )
            v170 = v245[0];
          v164 = DCCDNUtil_SetRegistryString(v194[0], v170, L"ResourceFailureValues", v169, 0);
          v147 = v164;
          if ( v164 < 0 )
          {
            v175 = 3570;
            goto LABEL_291;
          }
        }
        if ( v251[2] )
        {
          v171 = (const unsigned __int16 *)v251;
          if ( v251[3] > (unsigned __int16 *)7 )
            v171 = v251[0];
          v172 = (const unsigned __int16 *)v245;
          if ( v246 > 7 )
            v172 = v245[0];
          v164 = DCCDNUtil_SetRegistryString(v194[0], v172, L"ResourceInProgressUri", v171, 0);
          v147 = v164;
          if ( v164 < 0 )
          {
            v175 = 3579;
            goto LABEL_291;
          }
        }
        if ( v252[2] )
        {
          v173 = (const unsigned __int16 *)v252;
          if ( v252[3] > (unsigned __int16 *)7 )
            v173 = v252[0];
          v174 = (const unsigned __int16 *)v245;
          if ( v246 > 7 )
            v174 = v245[0];
          v164 = DCCDNUtil_SetRegistryString(v194[0], v174, L"ResourceInProgressValues", v173, 0);
          v147 = v164;
          if ( v164 < 0 )
          {
            v175 = 3588;
            goto LABEL_291;
          }
        }
        std::pair<std::wstring,ResourceValidationUrisAndValues>::~pair<std::wstring,ResourceValidationUrisAndValues>(v245);
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v194);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v193);
    }
  }
  std::wstring::_Tidy_deallocate(lpSubKey);
  std::_Hash<std::_Umap_traits<std::wstring,ResourceValidationUrisAndValues,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ResourceValidationUrisAndValues>>,0>>::~_Hash<std::_Umap_traits<std::wstring,ResourceValidationUrisAndValues,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ResourceValidationUrisAndValues>>,0>>(&v207);
  CspSchema::~CspSchema((CspSchema *)v254);
  std::wstring::_Tidy_deallocate(v232);
  return 0;
}

```

## disassembly

```asm
0x1800b8fac  push    rbx
0x1800b8fae  push    rsi
0x1800b8faf  push    rdi
0x1800b8fb0  push    r12
0x1800b8fb2  push    r13
0x1800b8fb4  push    r14
0x1800b8fb6  sub     rsp, 678h
0x1800b8fbd  mov     rax, cs:__security_cookie
0x1800b8fc4  xor     rax, rsp
0x1800b8fc7  mov     [rsp+6A8h+var_48], rax
0x1800b8fcf  mov     [rsp+6A8h+var_5F0], r9
0x1800b8fd7  mov     r13, r8
0x1800b8fda  mov     [rsp+6A8h+psz], rdx
0x1800b8fe2  mov     [rsp+6A8h+var_5E8], rcx
0x1800b8fea  mov     [rsp+6A8h+var_568], rdx
0x1800b8ff2  mov     [rsp+6A8h+var_620], rcx
0x1800b8ffa  mov     rdi, rcx
0x1800b8ffd  mov     [rsp+6A8h+var_5D8], rcx
0x1800b9005  mov     qword ptr [rsp+6A8h+var_608], rdx
0x1800b900d  mov     qword ptr [rsp+6A8h+var_600], r8
0x1800b9015  mov     rbx, r9
0x1800b9018  mov     [rsp+6A8h+var_5C8], rbx
0x1800b9020  mov     r12, [rsp+6A8h+hKey]
0x1800b9028  mov     [rsp+6A8h+var_5D0], r12
0x1800b9030  mov     rbx, [rsp+6A8h+arg_28]
0x1800b9038  mov     [rsp+6A8h+var_5E0], rbx
0x1800b9040  lea     rdx, word_180142E98
0x1800b9047  lea     rcx, [rsp+6A8h+var_478]
0x1800b904f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b9054  nop
0x1800b9055  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x1800b905c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800b9061  xor     r14d, r14d
0x1800b9064  test    al, al
0x1800b9066  jz      loc_1800B9108
0x1800b906c  cmp     dword ptr [r13+80h], 1
0x1800b9074  jnz     short loc_1800B90E9
0x1800b9076  lea     rdx, asc_18013EB9C; "/"
0x1800b907d  lea     rcx, [r13+58h]
0x1800b9081  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_last_of(ushort const * const,unsigned __int64)
0x1800b9086  lea     r8, [rax+1]
0x1800b908a  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800b908e  lea     rdx, [rsp+6A8h+var_438]
0x1800b9096  lea     rcx, [r13+58h]
0x1800b909a  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800b909f  mov     rdx, rax
0x1800b90a2  lea     rcx, [rsp+6A8h+var_478]
0x1800b90aa  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800b90af  lea     rcx, [rsp+6A8h+var_438]
0x1800b90b7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b90bc  jmp     loc_1800B914F
0x1800b90c1  mov     rbx, [rsp+6A8h+var_620]
0x1800b90c9  mov     [rsp+6A8h+var_5E8], rbx
0x1800b90d1  mov     rdi, rbx
0x1800b90d4  mov     rbx, qword ptr [rsp+6A8h+var_608]
0x1800b90dc  mov     [rsp+6A8h+psz], rbx
0x1800b90e4  jmp     loc_1800B9174
0x1800b90e9  mov     r8d, 17h
0x1800b90ef  lea     rdx, aReservedneveru; "___reservedNeverUsed___"
0x1800b90f6  lea     rcx, [rsp+6A8h+var_478]
0x1800b90fe  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800b9103  jmp     loc_1800B9197
0x1800b9108  lea     rdx, asc_18013EB9C; "/"
0x1800b910f  lea     rcx, [r13+58h]
0x1800b9113  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_last_of(ushort const * const,unsigned __int64)
0x1800b9118  lea     r8, [rax+1]
0x1800b911c  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800b9120  lea     rdx, [rsp+6A8h+var_438]
0x1800b9128  lea     rcx, [r13+58h]
0x1800b912c  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800b9131  mov     rdx, rax
0x1800b9134  lea     rcx, [rsp+6A8h+var_478]
0x1800b913c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800b9141  lea     rcx, [rsp+6A8h+var_438]
0x1800b9149  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b914e  nop
0x1800b914f  jmp     short loc_1800B9197
0x1800b9151  mov     rax, [rsp+6A8h+var_620]
0x1800b9159  mov     [rsp+6A8h+var_5E8], rax
0x1800b9161  mov     rdi, rax
0x1800b9164  mov     rax, qword ptr [rsp+6A8h+var_608]
0x1800b916c  mov     [rsp+6A8h+psz], rax
0x1800b9174  mov     rbx, [rsp+6A8h+var_5C8]
0x1800b917c  mov     r12, [rsp+6A8h+var_5D0]
0x1800b9184  mov     [rsp+6A8h+var_5F0], rbx
0x1800b918c  mov     r13, qword ptr [rsp+6A8h+var_600]
0x1800b9194  xor     r14d, r14d
0x1800b9197  lea     rdx, [rsp+6A8h+var_478]
0x1800b919f  cmp     [rsp+6A8h+var_460], 7
0x1800b91a8  cmova   rdx, [rsp+6A8h+var_478]; unsigned __int16 *
0x1800b91b1  lea     rcx, [rsp+6A8h+var_178]; this
0x1800b91b9  call    ??0CspSchema@@QEAA@PEBG@Z; CspSchema::CspSchema(ushort const *)
0x1800b91be  nop
0x1800b91bf  lea     rcx, [rsp+6A8h+var_178]; this
0x1800b91c7  call    ?InitializeFromSchemaStore@CspSchema@@QEAAJXZ; CspSchema::InitializeFromSchemaStore(void)
0x1800b91cc  mov     dword ptr [rsp+6A8h+var_618], eax
0x1800b91d3  mov     [rsp+6A8h+var_600], r14d
0x1800b91db  mov     byte ptr [rsp+6A8h+var_628], r14b
0x1800b91e3  mov     byte ptr [rsp+6A8h+var_628+1], r14b
0x1800b91eb  mov     byte ptr [rsp+6A8h+var_628+2], r14b
0x1800b91f3  mov     [rsp+6A8h+var_5A8], 0
0x1800b91fe  mov     [rsp+6A8h+var_5A0], r14
0x1800b9206  mov     [rsp+6A8h+var_598], r14
0x1800b920e  mov     ecx, 0F0h; Size
0x1800b9213  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b9218  mov     [rax], rax
0x1800b921b  mov     [rax+8], rax
0x1800b921f  mov     [rsp+6A8h+var_5A0], rax
0x1800b9227  mov     [rsp+6A8h+var_590], r14
0x1800b922f  xorps   xmm0, xmm0
0x1800b9232  movdqa  [rsp+6A8h+var_588], xmm0
0x1800b923b  mov     [rsp+6A8h+var_578], 7
0x1800b9247  mov     [rsp+6A8h+var_570], 8
0x1800b9253  mov     [rsp+6A8h+var_5A8], 3F800000h
0x1800b925e  mov     r8, rax
0x1800b9261  mov     edx, 10h
0x1800b9266  lea     rcx, [rsp+6A8h+var_590]
0x1800b926e  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VHierarchyObjectItem@@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VHierarchyObjectItem@@@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<HierarchyObjectItem>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<HierarchyObjectItem>>>>>)
0x1800b9273  nop
0x1800b9274  mov     rsi, [r13+10h]
0x1800b9278  mov     rax, [r13+18h]
0x1800b927c  mov     [rsp+6A8h+var_5D0], rax
0x1800b9284  mov     [rsp+6A8h+var_620], rsi
0x1800b928c  cmp     rsi, rax
0x1800b928f  jz      loc_1800BA4D5
0x1800b9295  lea     rcx, [rsp+6A8h+var_238]; this
0x1800b929d  call    ??0ResourceValidationUrisAndValues@@QEAA@XZ; ResourceValidationUrisAndValues::ResourceValidationUrisAndValues(void)
0x1800b92a2  nop
0x1800b92a3  lea     rbx, [rdi+200h]
0x1800b92aa  cmp     qword ptr [rdi+218h], 7
0x1800b92b2  jbe     short loc_1800B92B9
0x1800b92b4  mov     rcx, [rbx]
0x1800b92b7  jmp     short loc_1800B92BC
0x1800b92b9  mov     rcx, rbx
0x1800b92bc  lea     rdx, aMsftinventory; "msftinventory"
0x1800b92c3  call    cs:__imp__o__wcsicmp
0x1800b92c9  test    eax, eax
0x1800b92cb  jz      loc_1800BA25B
0x1800b92d1  cmp     qword ptr [rdi+218h], 7
0x1800b92d9  jbe     short loc_1800B92E0
0x1800b92db  mov     rcx, [rbx]
0x1800b92de  jmp     short loc_1800B92E3
0x1800b92e0  mov     rcx, rbx
0x1800b92e3  lea     rdx, aMsftextensibil_1; "msftextensibilitymiproviderinventory"
0x1800b92ea  call    cs:__imp__o__wcsicmp
0x1800b92f0  test    eax, eax
0x1800b92f2  jz      loc_1800BA25B
0x1800b92f8  cmp     qword ptr [rdi+218h], 7
0x1800b9300  jbe     short loc_1800B9305
0x1800b9302  mov     rbx, [rbx]
0x1800b9305  lea     rdx, aMsftonetime; "msftonetime"
0x1800b930c  mov     rcx, rbx
0x1800b930f  call    cs:__imp__o__wcsicmp
0x1800b9315  test    eax, eax
0x1800b9317  jz      loc_1800BA25B
0x1800b931d  cmp     [r13+51h], r14b
0x1800b9321  jnz     loc_1800BA25B
0x1800b9327  lea     rcx, [rsp+6A8h+var_4B8]
0x1800b932f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800b9334  nop
0x1800b9335  lea     rcx, [rsp+6A8h+Src]
0x1800b933d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800b9342  nop
0x1800b9343  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x1800b934a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800b934f  test    al, al
0x1800b9351  jz      loc_1800B9890
0x1800b9357  lea     rcx, [rsp+6A8h+var_458]
0x1800b935f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800b9364  nop
0x1800b9365  mov     eax, [r13+80h]
0x1800b936c  cmp     eax, 1
0x1800b936f  jnz     loc_1800B9658
0x1800b9375  lea     rax, [r13+58h]
0x1800b9379  cmp     qword ptr [r13+70h], 7
0x1800b937e  jbe     short loc_1800B9383
0x1800b9380  mov     rax, [rax]
0x1800b9383  lea     rdx, [rax+4]
0x1800b9387  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800b938b  inc     r8
0x1800b938e  cmp     [rdx+r8*2], r14w
0x1800b9393  jnz     short loc_1800B938B
0x1800b9395  lea     rcx, [rsp+6A8h+var_458]
0x1800b939d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800b93a2  nop
0x1800b93a3  lea     rcx, [rsp+6A8h+var_458]
0x1800b93ab  cmp     [rsp+6A8h+var_440], 7
0x1800b93b4  cmova   rcx, [rsp+6A8h+var_458]; unsigned __int16 *
0x1800b93bd  call    ?DCDoesCspNeedPrefix@@YAHPEBG@Z; DCDoesCspNeedPrefix(ushort const *)
0x1800b93c2  mov     rsi, [rsi]
0x1800b93c5  lea     rdx, asc_180142BE8; "./"
0x1800b93cc  test    eax, eax
0x1800b93ce  jnz     short loc_1800B944A
0x1800b93d0  lea     r8, [rsp+6A8h+var_458]
0x1800b93d8  lea     rcx, [rsp+6A8h+var_418]
0x1800b93e0  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x1800b93e5  nop
0x1800b93e6  lea     r8, asc_18013EB9C; "/"
0x1800b93ed  mov     rdx, rax
0x1800b93f0  lea     rcx, [rsp+6A8h+var_358]
0x1800b93f8  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800b93fd  nop
0x1800b93fe  mov     r8, rsi
0x1800b9401  mov     rdx, rax
0x1800b9404  lea     rcx, [rsp+6A8h+var_498]
0x1800b940c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800b9411  mov     rdx, rax
0x1800b9414  lea     rcx, [rsp+6A8h+var_4B8]
0x1800b941c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800b9421  lea     rcx, [rsp+6A8h+var_498]
0x1800b9429  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b942e  nop
0x1800b942f  lea     rcx, [rsp+6A8h+var_358]
0x1800b9437  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b943c  nop
0x1800b943d  lea     rcx, [rsp+6A8h+var_418]
0x1800b9445  jmp     loc_1800B951D
0x1800b944a  lea     rbx, [rsp+6A8h+var_458]
0x1800b9452  cmp     [rsp+6A8h+var_440], 7
0x1800b945b  cmova   rbx, [rsp+6A8h+var_458]
0x1800b9464  lea     r8, [rdi+20h]
0x1800b9468  lea     rcx, [rsp+6A8h+var_3F8]
0x1800b9470  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x1800b9475  nop
0x1800b9476  lea     r8, asc_18013EB9C; "/"
0x1800b947d  mov     rdx, rax
0x1800b9480  lea     rcx, [rsp+6A8h+var_338]
0x1800b9488  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800b948d  nop
0x1800b948e  mov     r8, rbx
0x1800b9491  mov     rdx, rax
0x1800b9494  lea     rcx, [rsp+6A8h+var_498]
0x1800b949c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800b94a1  nop
0x1800b94a2  lea     r8, asc_18013EB9C; "/"
0x1800b94a9  mov     rdx, rax
0x1800b94ac  lea     rcx, [rsp+6A8h+var_358]
0x1800b94b4  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800b94b9  nop
0x1800b94ba  mov     r8, rsi
0x1800b94bd  mov     rdx, rax
0x1800b94c0  lea     rcx, [rsp+6A8h+var_418]
0x1800b94c8  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800b94cd  mov     rdx, rax
0x1800b94d0  lea     rcx, [rsp+6A8h+var_4B8]
0x1800b94d8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800b94dd  lea     rcx, [rsp+6A8h+var_418]
0x1800b94e5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b94ea  nop
0x1800b94eb  lea     rcx, [rsp+6A8h+var_358]
0x1800b94f3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b94f8  nop
0x1800b94f9  lea     rcx, [rsp+6A8h+var_498]
0x1800b9501  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b9506  nop
0x1800b9507  lea     rcx, [rsp+6A8h+var_338]
0x1800b950f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b9514  nop
0x1800b9515  lea     rcx, [rsp+6A8h+var_3F8]
0x1800b951d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b9522  lea     r9, [rsp+6A8h+var_4B8]
0x1800b952a  cmp     [rsp+6A8h+var_4A0], 7
0x1800b9533  cmova   r9, [rsp+6A8h+var_4B8]
0x1800b953c  lea     rdx, [rsp+6A8h+var_5C8]
0x1800b9544  lea     rcx, [rsp+6A8h+var_4B8]
0x1800b954c  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x1800b9551  lea     rdx, [rsp+6A8h+var_4B8]
0x1800b9559  cmp     [rsp+6A8h+var_4A0], 7
0x1800b9562  cmova   rdx, [rsp+6A8h+var_4B8]
0x1800b956b  mov     rcx, cs:__imp__o_towlower
0x1800b9572  mov     qword ptr [rsp+6A8h+dwOptions], rcx
0x1800b9577  mov     r8, [rax]
0x1800b957a  lea     rcx, [rsp+6A8h+var_518]
0x1800b9582  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x1800b9587  lea     rdx, [rsp+6A8h+var_4B8]
0x1800b958f  lea     rcx, [rsp+6A8h+Src]
0x1800b9597  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800b959c  lea     rcx, [rdi+20h]
0x1800b95a0  cmp     qword ptr [rdi+38h], 7
0x1800b95a5  jbe     short loc_1800B95AA
0x1800b95a7  mov     rcx, [rcx]
0x1800b95aa  lea     rdx, aUser_0; "user"
0x1800b95b1  call    cs:__imp__o__wcsicmp
0x1800b95b7  test    eax, eax
0x1800b95b9  jnz     short loc_1800B95E8
0x1800b95bb  lea     r9, [rdi+40h]
0x1800b95bf  mov     rax, [rdi+50h]
0x1800b95c3  cmp     qword ptr [rdi+58h], 7
0x1800b95c8  jbe     short loc_1800B95CD
0x1800b95ca  mov     r9, [r9]
0x1800b95cd  mov     qword ptr [rsp+6A8h+dwOptions], rax; void *
0x1800b95d2  mov     edx, 2
0x1800b95d7  lea     r8d, [rdx+2]
0x1800b95db  lea     rcx, [rsp+6A8h+Src]; Src
0x1800b95e3  call    ??$_Replace@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_K_KQEBG0@Z; std::wstring::_Replace<ushort>(unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x1800b95e8  jmp     loc_1800B978E
0x1800b95ed  lea     rcx, [rsp+6A8h+var_458]
0x1800b95f5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b95fa  nop
0x1800b95fb  lea     rcx, [rsp+6A8h+Src]
  ... truncated ...
```
