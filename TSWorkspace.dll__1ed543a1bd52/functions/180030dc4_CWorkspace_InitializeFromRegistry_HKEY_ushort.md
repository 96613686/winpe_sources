# CWorkspace::InitializeFromRegistry(HKEY__ *,ushort *)

- ea: `0x180030dc4`
- end: `0x18003191b`
- name: `?InitializeFromRegistry@CWorkspace@@QEAAJPEAUHKEY__@@PEAG@Z`
- size: `2903`
- prototype: `__int64 __fastcall(GUID *this, HKEY, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800294b4`

## callees

- `0x1800044bf`
- `0x1800055d0`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000dbdc`
- `0x18000ec94`
- `0x18000ece0`
- `0x18001e41c`
- `0x18001e610`
- `0x18001e92c`
- `0x180020bf0`
- `0x18003091c`
- `0x180030dc4`
- `0x180031924`
- `0x180031e20`
- `0x180031f10`
- `0x18009a520`
- `0x18009a5e0`

## import_xrefs

- `ole32!IIDFromString` at `0x18003175c`
- `ole32!IIDFromString` at `0x18003175c`
- `ADVAPI32!RegGetValueW` at `0x1800315ee`
- `ADVAPI32!RegGetValueW` at `0x1800315ee`

## string_xrefs

- `0x180030fd6`: `EnableAutoUpdate`
- `0x1800311df`: `NumStartMenuComputers`
- `0x18003120f`: `LastSuccessfulUpdateTimeHigh`
- `0x180031243`: `LastSuccessfulUpdateTimeLow`
- `0x18003126c`: `LastAttemptTimeHigh`
- `0x1800312a0`: `LastAttemptTimeLow`
- `0x180031326`: `CreatedTimeHigh`
- `0x18003135a`: `CreatedTimeLow`
- `0x180031383`: `LastAttemptStatus`
- `0x1800313b3`: `LastAttemptTitle`
- `0x1800313ed`: `LastAttemptDetail`
- `0x18003149e`: `RDWebServiceURL`
- `0x1800314dc`: `CreatedThroughSSP`
- `0x18003180f`: `InitializeFtaAppRegistrationsFromRegistry failed`
- `0x18003185b`: `InitializeFileAssocFromRegistry failed`
- `0x18003189e`: `InitializeResourceMapFromRegistry failed`
- `0x1800318e1`: `InitializeSSPInstalledAppsFromRegistry failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWorkspace::InitializeFromRegistry(GUID *this, HKEY a2, unsigned __int16 *a3)
{
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rbx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int i; // r14d
  LSTATUS ValueW; // ebx
  __int64 v13; // r8
  __int64 v14; // rcx
  unsigned int v15; // edi
  unsigned int v16; // eax
  LPCWSTR v17; // rbx
  unsigned int v18; // eax
  const OLECHAR *v19; // rax
  unsigned int v20; // eax
  int v21; // edx
  const char *v22; // rcx
  PVOID pvData; // [rsp+28h] [rbp-D8h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+48h] [rbp-B8h]
  _BYTE v27[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v28[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v29[32]; // [rsp+90h] [rbp-70h] BYREF
  _DWORD v30[2564]; // [rsp+B0h] [rbp-50h] BYREF
  LPCWSTR lpValue; // [rsp+28C0h] [rbp+27C0h]
  int v32; // [rsp+28C8h] [rbp+27C8h]
  int v33; // [rsp+28CCh] [rbp+27CCh]
  __int64 v34; // [rsp+28D0h] [rbp+27D0h]
  GUID *v35; // [rsp+28D8h] [rbp+27D8h]
  _QWORD v36[2]; // [rsp+28E0h] [rbp+27E0h] BYREF
  int v37; // [rsp+28F0h] [rbp+27F0h]
  int v38; // [rsp+28F4h] [rbp+27F4h]
  __int64 v39; // [rsp+28F8h] [rbp+27F8h]
  unsigned __int8 *Data4; // [rsp+2900h] [rbp+2800h]
  __int64 v41; // [rsp+2908h] [rbp+2808h]
  const wchar_t *v42; // [rsp+2910h] [rbp+2810h]
  int v43; // [rsp+2918h] [rbp+2818h]
  int v44; // [rsp+291Ch] [rbp+281Ch]
  __int64 v45; // [rsp+2920h] [rbp+2820h]
  unsigned __int8 *v46; // [rsp+2928h] [rbp+2828h]
  __int64 v47; // [rsp+2930h] [rbp+2830h]
  const wchar_t *v48; // [rsp+2938h] [rbp+2838h]
  int v49; // [rsp+2940h] [rbp+2840h]
  int v50; // [rsp+2944h] [rbp+2844h]
  GUID *v51; // [rsp+2948h] [rbp+2848h]
  __int128 v52; // [rsp+2950h] [rbp+2850h]
  const wchar_t *v53; // [rsp+2960h] [rbp+2860h]
  int v54; // [rsp+2968h] [rbp+2868h]
  int v55; // [rsp+296Ch] [rbp+286Ch]
  unsigned __int8 *v56; // [rsp+2970h] [rbp+2870h]
  __int128 v57; // [rsp+2978h] [rbp+2878h]
  const wchar_t *v58; // [rsp+2988h] [rbp+2888h]
  int v59; // [rsp+2990h] [rbp+2890h]
  int v60; // [rsp+2994h] [rbp+2894h]
  unsigned __int8 *v61; // [rsp+2998h] [rbp+2898h]
  __int128 v62; // [rsp+29A0h] [rbp+28A0h]
  const unsigned __int16 *v63; // [rsp+29B0h] [rbp+28B0h]
  int v64; // [rsp+29B8h] [rbp+28B8h]
  int v65; // [rsp+29BCh] [rbp+28BCh]
  __int64 v66; // [rsp+29C0h] [rbp+28C0h]
  unsigned __int8 *v67; // [rsp+29C8h] [rbp+28C8h]
  __int64 v68; // [rsp+29D0h] [rbp+28D0h]
  const wchar_t *v69; // [rsp+29D8h] [rbp+28D8h]
  int v70; // [rsp+29E0h] [rbp+28E0h]
  int v71; // [rsp+29E4h] [rbp+28E4h]
  __int64 v72; // [rsp+29E8h] [rbp+28E8h]
  unsigned __int8 *v73; // [rsp+29F0h] [rbp+28F0h]
  __int64 v74; // [rsp+29F8h] [rbp+28F8h]
  const wchar_t *v75; // [rsp+2A00h] [rbp+2900h]
  int v76; // [rsp+2A08h] [rbp+2908h]
  int v77; // [rsp+2A0Ch] [rbp+290Ch]
  __int64 v78; // [rsp+2A10h] [rbp+2910h]
  unsigned __int8 *v79; // [rsp+2A18h] [rbp+2918h]
  __int64 v80; // [rsp+2A20h] [rbp+2920h]
  const wchar_t *v81; // [rsp+2A28h] [rbp+2928h]
  int v82; // [rsp+2A30h] [rbp+2930h]
  int v83; // [rsp+2A34h] [rbp+2934h]
  __int64 v84; // [rsp+2A38h] [rbp+2938h]
  unsigned __int8 *v85; // [rsp+2A40h] [rbp+2940h]
  __int64 v86; // [rsp+2A48h] [rbp+2948h]
  const wchar_t *v87; // [rsp+2A50h] [rbp+2950h]
  int v88; // [rsp+2A58h] [rbp+2958h]
  int v89; // [rsp+2A5Ch] [rbp+295Ch]
  unsigned __int8 *v90; // [rsp+2A60h] [rbp+2960h]
  __int128 v91; // [rsp+2A68h] [rbp+2968h]
  const wchar_t *v92; // [rsp+2A78h] [rbp+2978h]
  int v93; // [rsp+2A80h] [rbp+2980h]
  int v94; // [rsp+2A84h] [rbp+2984h]
  unsigned __int8 *v95; // [rsp+2A88h] [rbp+2988h]
  __int128 v96; // [rsp+2A90h] [rbp+2990h]
  const wchar_t *v97; // [rsp+2AA0h] [rbp+29A0h]
  int v98; // [rsp+2AA8h] [rbp+29A8h]
  int v99; // [rsp+2AACh] [rbp+29ACh]
  GUID *v100; // [rsp+2AB0h] [rbp+29B0h]
  __int128 v101; // [rsp+2AB8h] [rbp+29B8h]
  const wchar_t *v102; // [rsp+2AC8h] [rbp+29C8h]
  int v103; // [rsp+2AD0h] [rbp+29D0h]
  int v104; // [rsp+2AD4h] [rbp+29D4h]
  unsigned __int8 *v105; // [rsp+2AD8h] [rbp+29D8h]
  __int128 v106; // [rsp+2AE0h] [rbp+29E0h]
  const wchar_t *v107; // [rsp+2AF0h] [rbp+29F0h]
  int v108; // [rsp+2AF8h] [rbp+29F8h]
  int v109; // [rsp+2AFCh] [rbp+29FCh]
  unsigned __int8 *v110; // [rsp+2B00h] [rbp+2A00h]
  __int128 v111; // [rsp+2B08h] [rbp+2A08h]
  const wchar_t *v112; // [rsp+2B18h] [rbp+2A18h]
  int v113; // [rsp+2B20h] [rbp+2A20h]
  int v114; // [rsp+2B24h] [rbp+2A24h]
  unsigned __int8 *v115; // [rsp+2B28h] [rbp+2A28h]
  __int128 v116; // [rsp+2B30h] [rbp+2A30h]
  const wchar_t *v117; // [rsp+2B40h] [rbp+2A40h]
  int v118; // [rsp+2B48h] [rbp+2A48h]
  int v119; // [rsp+2B4Ch] [rbp+2A4Ch]
  unsigned __int8 *v120; // [rsp+2B50h] [rbp+2A50h]
  __int128 v121; // [rsp+2B58h] [rbp+2A58h]
  const wchar_t *v122; // [rsp+2B68h] [rbp+2A68h]
  int v123; // [rsp+2B70h] [rbp+2A70h]
  int v124; // [rsp+2B74h] [rbp+2A74h]
  unsigned __int16 *p_Data2; // [rsp+2B78h] [rbp+2A78h]
  __int128 v126; // [rsp+2B80h] [rbp+2A80h]
  const wchar_t *v127; // [rsp+2B90h] [rbp+2A90h]
  int v128; // [rsp+2B98h] [rbp+2A98h]
  int v129; // [rsp+2B9Ch] [rbp+2A9Ch]
  GUID *v130; // [rsp+2BA0h] [rbp+2AA0h]
  __int128 v131; // [rsp+2BA8h] [rbp+2AA8h]
  const wchar_t *v132; // [rsp+2BB8h] [rbp+2AB8h]
  int v133; // [rsp+2BC0h] [rbp+2AC0h]
  int v134; // [rsp+2BC4h] [rbp+2AC4h]
  unsigned __int8 *v135; // [rsp+2BC8h] [rbp+2AC8h]
  __int128 v136; // [rsp+2BD0h] [rbp+2AD0h]
  const wchar_t *v137; // [rsp+2BE0h] [rbp+2AE0h]
  int v138; // [rsp+2BE8h] [rbp+2AE8h]
  int v139; // [rsp+2BECh] [rbp+2AECh]
  unsigned __int8 *v140; // [rsp+2BF0h] [rbp+2AF0h]
  __int128 v141; // [rsp+2BF8h] [rbp+2AF8h]
  const wchar_t *v142; // [rsp+2C08h] [rbp+2B08h]
  int v143; // [rsp+2C10h] [rbp+2B10h]
  int v144; // [rsp+2C14h] [rbp+2B14h]
  unsigned __int16 *v145; // [rsp+2C18h] [rbp+2B18h]
  __int128 v146; // [rsp+2C20h] [rbp+2B20h]
  const wchar_t *v147; // [rsp+2C30h] [rbp+2B30h]
  int v148; // [rsp+2C38h] [rbp+2B38h]
  int v149; // [rsp+2C3Ch] [rbp+2B3Ch]
  GUID *v150; // [rsp+2C40h] [rbp+2B40h]
  __int128 v151; // [rsp+2C48h] [rbp+2B48h]
  const wchar_t *v152; // [rsp+2C58h] [rbp+2B58h]
  int v153; // [rsp+2C60h] [rbp+2B60h]
  int v154; // [rsp+2C64h] [rbp+2B64h]
  GUID *v155; // [rsp+2C68h] [rbp+2B68h]
  __int128 v156; // [rsp+2C70h] [rbp+2B70h]
  const wchar_t *v157; // [rsp+2C80h] [rbp+2B80h]
  int v158; // [rsp+2C88h] [rbp+2B88h]
  int v159; // [rsp+2C8Ch] [rbp+2B8Ch]
  __int64 v160; // [rsp+2C90h] [rbp+2B90h]
  unsigned __int8 *v161; // [rsp+2C98h] [rbp+2B98h]
  __int64 v162; // [rsp+2CA0h] [rbp+2BA0h]
  const wchar_t *v163; // [rsp+2CA8h] [rbp+2BA8h]
  int v164; // [rsp+2CB0h] [rbp+2BB0h]
  int v165; // [rsp+2CB4h] [rbp+2BB4h]
  __int64 v166; // [rsp+2CB8h] [rbp+2BB8h]
  unsigned __int8 *v167; // [rsp+2CC0h] [rbp+2BC0h]
  __int64 v168; // [rsp+2CC8h] [rbp+2BC8h]
  const wchar_t *v169; // [rsp+2CD0h] [rbp+2BD0h]
  int v170; // [rsp+2CD8h] [rbp+2BD8h]
  int v171; // [rsp+2CDCh] [rbp+2BDCh]
  __int64 v172; // [rsp+2CE0h] [rbp+2BE0h]
  unsigned __int8 *v173; // [rsp+2CE8h] [rbp+2BE8h]
  __int64 v174; // [rsp+2CF0h] [rbp+2BF0h]
  const wchar_t *v175; // [rsp+2CF8h] [rbp+2BF8h]
  int v176; // [rsp+2D00h] [rbp+2C00h]
  int v177; // [rsp+2D04h] [rbp+2C04h]
  GUID *v178; // [rsp+2D08h] [rbp+2C08h]
  __int64 v179; // [rsp+2D10h] [rbp+2C10h]
  int v180; // [rsp+2D18h] [rbp+2C18h]
  int v181; // [rsp+2D1Ch] [rbp+2C1Ch]
  const wchar_t *v182; // [rsp+2D20h] [rbp+2C20h]
  int v183; // [rsp+2D28h] [rbp+2C28h]
  int v184; // [rsp+2D2Ch] [rbp+2C2Ch]
  __int64 v185; // [rsp+2D30h] [rbp+2C30h]
  unsigned __int8 *v186; // [rsp+2D38h] [rbp+2C38h]
  int v187; // [rsp+2D40h] [rbp+2C40h]
  int v188; // [rsp+2D44h] [rbp+2C44h]
  const WCHAR *v189; // [rsp+2D48h] [rbp+2C48h]
  int v190; // [rsp+2D50h] [rbp+2C50h]
  int v191; // [rsp+2D54h] [rbp+2C54h]
  unsigned __int8 *v192; // [rsp+2D58h] [rbp+2C58h]
  __int64 v193; // [rsp+2D60h] [rbp+2C60h]
  int v194; // [rsp+2D68h] [rbp+2C68h]
  int v195; // [rsp+2D6Ch] [rbp+2C6Ch]
  const wchar_t *v196; // [rsp+2D70h] [rbp+2C70h]
  int v197; // [rsp+2D78h] [rbp+2C78h]
  int v198; // [rsp+2D7Ch] [rbp+2C7Ch]
  unsigned __int8 *v199; // [rsp+2D80h] [rbp+2C80h]
  __int64 v200; // [rsp+2D88h] [rbp+2C88h]
  int v201; // [rsp+2D90h] [rbp+2C90h]
  int v202; // [rsp+2D94h] [rbp+2C94h]
  const wchar_t *v203; // [rsp+2D98h] [rbp+2C98h]
  int v204; // [rsp+2DA0h] [rbp+2CA0h]
  int v205; // [rsp+2DA4h] [rbp+2CA4h]
  __int64 v206; // [rsp+2DA8h] [rbp+2CA8h]
  unsigned __int8 *v207; // [rsp+2DB0h] [rbp+2CB0h]
  int v208; // [rsp+2DB8h] [rbp+2CB8h]
  int v209; // [rsp+2DBCh] [rbp+2CBCh]

  v26 = -2;
  pcbData = 0;
  memset_0(v30, 0, 0x2804u);
  v6 = std::wstring::wstring(v29, L"Software\\Microsoft\\Workspaces\\Feeds");
  v7 = std::operator+<unsigned short>(v28, v6, L"\\");
  v8 = std::operator+<unsigned short>(v27, v7, a3);
  std::wstring::operator=(this[30].Data4, v8);
  std::wstring::~wstring(v27);
  std::wstring::~wstring(v28);
  std::wstring::~wstring(v29);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this[30].Data4);
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      91,
      (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
      CurrentThreadActivityIdPrefix,
      v9);
  }
  lpValue = L"Id";
  v32 = 2;
  v33 = 1;
  v34 = 0;
  v35 = this + 4;
  v36[0] = 0;
  v36[1] = L"Publisher";
  v37 = 2;
  v38 = 1;
  v39 = 0;
  Data4 = this[6].Data4;
  v41 = 0;
  v42 = L"WorkspaceId";
  v43 = 2;
  v44 = 1;
  v45 = 0;
  v46 = this[8].Data4;
  v47 = 0;
  v48 = L"PublisherNameSuffix";
  v49 = 16;
  v50 = 4;
  v51 = this + 18;
  v52 = 0;
  v53 = L"EnableAutoUpdate";
  v54 = 16;
  v55 = 4;
  v56 = this[10].Data4;
  v57 = 0;
  v58 = L"UseClaimsAuth";
  v59 = 16;
  v60 = 4;
  v61 = &this[10].Data4[4];
  v62 = 0;
  v63 = L"URL";
  v64 = 2;
  v65 = 1;
  v66 = 0;
  v67 = this[18].Data4;
  v68 = 0;
  v69 = L"ClaimsHint";
  v70 = 2;
  v71 = 1;
  v72 = 0;
  v73 = this[22].Data4;
  v74 = 0;
  v75 = L"WorkspaceFolder";
  v76 = 6;
  v77 = 1;
  v78 = 0;
  v79 = this[26].Data4;
  v80 = 0;
  v81 = L"StartMenuRoot";
  v82 = 6;
  v83 = 1;
  v84 = 0;
  v85 = this[28].Data4;
  v86 = 0;
  v87 = L"NumPublishedResources";
  v88 = 16;
  v89 = 4;
  v90 = this[36].Data4;
  v91 = 0;
  v92 = L"NumDownloadedResourceFiles";
  v93 = 16;
  v94 = 4;
  v95 = &this[36].Data4[4];
  v96 = 0;
  v97 = L"NumDownloadedIcons";
  v98 = 16;
  v99 = 4;
  v100 = this + 37;
  v101 = 0;
  v102 = L"NumStartMenuPrograms";
  v103 = 16;
  v104 = 4;
  v105 = this[37].Data4;
  v106 = 0;
  v107 = L"NumStartMenuComputers";
  v108 = 16;
  v109 = 4;
  v110 = &this[37].Data4[4];
  v111 = 0;
  v112 = L"LastSuccessfulUpdateTimeHigh";
  v113 = 16;
  v114 = 4;
  v115 = &this[38].Data4[4];
  v116 = 0;
  v117 = L"LastSuccessfulUpdateTimeLow";
  v118 = 16;
  v119 = 4;
  v120 = this[38].Data4;
  v121 = 0;
  v122 = L"LastAttemptTimeHigh";
  v123 = 16;
  v124 = 4;
  p_Data2 = &this[39].Data2;
  v126 = 0;
  v127 = L"LastAttemptTimeLow";
  v128 = 16;
  v129 = 4;
  v130 = this + 39;
  v131 = 0;
  v132 = L"FirstFailureTimeHigh";
  v133 = 16;
  v134 = 4;
  v135 = &this[39].Data4[4];
  v136 = 0;
  v137 = L"FirstFailureTimeLow";
  v138 = 16;
  v139 = 4;
  v140 = this[39].Data4;
  v141 = 0;
  v142 = L"CreatedTimeHigh";
  v143 = 16;
  v144 = 4;
  v145 = &this[38].Data2;
  v146 = 0;
  v147 = L"CreatedTimeLow";
  v148 = 16;
  v149 = 4;
  v150 = this + 38;
  v151 = 0;
  v152 = L"LastAttemptStatus";
  v153 = 16;
  v154 = 4;
  v155 = this + 40;
  v156 = 0;
  v157 = L"LastAttemptTitle";
  v158 = 2;
  v159 = 1;
  v160 = 0;
  v161 = this[40].Data4;
  v162 = 0;
  v163 = L"LastAttemptDetail";
  v164 = 2;
  v165 = 1;
  v166 = 0;
  v167 = this[42].Data4;
  v168 = 0;
  v169 = L"LoginCookie";
  v170 = 2;
  v171 = 1;
  v172 = 0;
  v173 = this[44].Data4;
  v174 = 0;
  v175 = L"EnableFileAssociations";
  v176 = 16;
  v177 = 4;
  v178 = this + 54;
  v179 = 0;
  v180 = 0;
  v181 = 1;
  v182 = L"RDWebServiceURL";
  v183 = 2;
  v184 = 1;
  v185 = 0;
  v186 = this[24].Data4;
  v187 = 0;
  v188 = 1;
  v189 = L"CreatedThroughSSP";
  v190 = 16;
  v191 = 4;
  v192 = this[16].Data4;
  v193 = 0;
  v194 = 0;
  v195 = 2;
  v196 = L"SuppressReconnect";
  v197 = 16;
  v198 = 4;
  v199 = this[11].Data4;
  v200 = 0;
  v201 = 0;
  v202 = 2;
  v203 = L"FeedDiscoveryURL";
  v204 = 2;
  v205 = 1;
  v206 = 0;
  v207 = this[20].Data4;
  v208 = 0;
  v209 = 2;
  for ( i = 0; i < 0x20; ++i )
  {
    pcbData = 10244;
    ValueW = RegGetValueW(a2, a3, (&lpValue)[5 * i], *(&v32 + 10 * i) | 0x10000000, (LPDWORD)&v36[5 * i], v30, &pcbData);
    if ( ValueW && SHIDWORD(v36[5 * i]) < 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( ValueW > 0 )
          v15 = (unsigned __int16)ValueW | 0x80070000;
        else
          v15 = ValueW;
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v16, v15);
      }
      if ( ValueW > 0 )
        return (unsigned __int16)ValueW | 0x80070000;
      return (unsigned int)ValueW;
    }
    if ( *(&v33 + 10 * i) == 4 )
    {
      if ( ValueW )
      {
        *(_DWORD *)*(&v34 + 5 * i) = 0;
      }
      else
      {
        if ( pcbData != 4 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v17 = (&lpValue)[5 * i];
            v18 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              93,
              (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
              v18,
              (__int64)v17);
          }
          return (unsigned int)-2147467259;
        }
        *(_DWORD *)*(&v34 + 5 * i) = v30[0];
      }
    }
    if ( *(&v33 + 10 * i) == 1 )
    {
      v14 = v36[5 * i - 1];
      if ( ValueW )
        std::wstring::assign(v14, &LocaleName, v13, 1);
      else
        std::wstring::assign(v14, v30, v13, 1);
    }
  }
  if ( *(_QWORD *)&this[5].Data1 )
  {
    v19 = (const OLECHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&this[4]);
    ValueW = IIDFromString(v19, this + 3);
    if ( ValueW < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)ValueW;
      }
      v20 = RdpWppGetCurrentThreadActivityIdPrefix();
      v21 = 94;
      v22 = "IIDFromString failed";
      goto LABEL_39;
    }
  }
  ValueW = CWorkspace::InitializeFtaAppRegistrationsFromRegistry((CWorkspace *)this);
  if ( ValueW < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)ValueW;
    }
    v20 = RdpWppGetCurrentThreadActivityIdPrefix();
    v21 = 95;
    v22 = "InitializeFtaAppRegistrationsFromRegistry failed";
    goto LABEL_39;
  }
  ValueW = CWorkspace::InitializeFileAssocFromRegistry((CWorkspace *)this);
  if ( ValueW < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)ValueW;
    }
    v20 = RdpWppGetCurrentThreadActivityIdPrefix();
    v21 = 96;
    v22 = "InitializeFileAssocFromRegistry failed";
    goto LABEL_39;
  }
  ValueW = CWorkspace::InitializeResourceMapFromRegistry((CWorkspace *)this);
  if ( ValueW < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)ValueW;
    }
    v20 = RdpWppGetCurrentThreadActivityIdPrefix();
    v21 = 97;
    v22 = "InitializeResourceMapFromRegistry failed";
LABEL_39:
    LODWORD(pvData) = ValueW;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v21,
      (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
      v20,
      (__int64)v22,
      pvData);
    return (unsigned int)ValueW;
  }
  ValueW = CWorkspace::InitializeSSPInstalledAppsFromRegistry((CWorkspace *)this);
  if ( ValueW >= 0 )
    return 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v20 = RdpWppGetCurrentThreadActivityIdPrefix();
    v21 = 98;
    v22 = "InitializeSSPInstalledAppsFromRegistry failed";
    goto LABEL_39;
  }
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x180030dc4  push    rbp
0x180030dc6  push    rsi
0x180030dc7  push    rdi
0x180030dc8  push    r12
0x180030dca  push    r13
0x180030dcc  push    r14
0x180030dce  push    r15
0x180030dd0  lea     rbp, [rsp-2CD0h]
0x180030dd8  mov     eax, 2DD0h
0x180030ddd  call    _alloca_probe
0x180030de2  sub     rsp, rax
0x180030de5  mov     [rsp+2E00h+var_2DB8], 0FFFFFFFFFFFFFFFEh
0x180030dee  mov     [rsp+2E00h+arg_18], rbx
0x180030df6  mov     rax, cs:__security_cookie
0x180030dfd  xor     rax, rsp
0x180030e00  mov     [rbp+2D00h+var_40], rax
0x180030e07  mov     r15, r8
0x180030e0a  mov     r12, rdx
0x180030e0d  mov     rsi, rcx
0x180030e10  xor     edi, edi
0x180030e12  mov     [rsp+2E00h+var_2DC0], edi
0x180030e16  xor     edx, edx; Val
0x180030e18  mov     r8d, 2804h; Size
0x180030e1e  lea     rcx, [rbp+2D00h+var_2D50]; void *
0x180030e22  call    memset_0
0x180030e27  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Workspaces\\Feeds"
0x180030e2e  lea     rcx, [rbp+2D00h+var_2D70]
0x180030e32  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180030e37  nop
0x180030e38  lea     r8, SubStr; "\\"
0x180030e3f  mov     rdx, rax
0x180030e42  lea     rcx, [rsp+2E00h+var_2D90]
0x180030e47  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180030e4c  nop
0x180030e4d  mov     r8, r15
0x180030e50  mov     rdx, rax
0x180030e53  lea     rcx, [rsp+2E00h+var_2DB0]
0x180030e58  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180030e5d  nop
0x180030e5e  lea     rbx, [rsi+1E8h]
0x180030e65  mov     rdx, rax
0x180030e68  mov     rcx, rbx
0x180030e6b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180030e70  nop
0x180030e71  lea     rcx, [rsp+2E00h+var_2DB0]; void *
0x180030e76  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180030e7b  nop
0x180030e7c  lea     rcx, [rsp+2E00h+var_2D90]; void *
0x180030e81  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180030e86  nop
0x180030e87  lea     rcx, [rbp+2D00h+var_2D70]; void *
0x180030e8b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180030e90  lea     rcx, WPP_GLOBAL_Control
0x180030e97  lea     r10d, [rdi+4]
0x180030e9b  lea     r9d, [rdi+1]
0x180030e9f  mov     rax, cs:WPP_GLOBAL_Control
0x180030ea6  cmp     rax, rcx
0x180030ea9  jz      short loc_180030EF1
0x180030eab  test    [rax+1Ch], r9b
0x180030eaf  jz      short loc_180030EF1
0x180030eb1  cmp     [rax+19h], r10b
0x180030eb5  jb      short loc_180030EF1
0x180030eb7  mov     rcx, rbx
0x180030eba  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180030ebf  mov     rbx, rax
0x180030ec2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180030ec7  lea     edx, [rdi+5Bh]
0x180030eca  mov     [rsp+2E00h+pdwType], rbx
0x180030ecf  mov     r9d, eax
0x180030ed2  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180030ed9  mov     rcx, cs:WPP_GLOBAL_Control
0x180030ee0  mov     rcx, [rcx+10h]
0x180030ee4  call    WPP_SF_DS
0x180030ee9  lea     r9d, [rdi+1]
0x180030eed  lea     r10d, [rdi+4]
0x180030ef1  lea     rax, aId; "Id"
0x180030ef8  mov     [rbp+2D00h+lpValue], rax
0x180030eff  mov     r8d, 2
0x180030f05  mov     [rbp+2D00h+var_538], r8d
0x180030f0c  mov     [rbp+2D00h+var_534], r9d
0x180030f13  mov     [rbp+2D00h+var_530], rdi
0x180030f1a  lea     r13, [rsi+40h]
0x180030f1e  mov     [rbp+2D00h+var_528], r13
0x180030f25  xor     eax, eax
0x180030f27  mov     [rbp+2D00h+var_520], rax
0x180030f2e  lea     rax, aPublisher; "Publisher"
0x180030f35  mov     [rbp+2D00h+var_518], rax
0x180030f3c  mov     [rbp+2D00h+var_510], r8d
0x180030f43  mov     [rbp+2D00h+var_50C], r9d
0x180030f4a  mov     [rbp+2D00h+var_508], rdi
0x180030f51  lea     rax, [rsi+68h]
0x180030f55  mov     [rbp+2D00h+var_500], rax
0x180030f5c  xor     eax, eax
0x180030f5e  mov     [rbp+2D00h+var_4F8], rax
0x180030f65  lea     rax, aWorkspaceid; "WorkspaceId"
0x180030f6c  mov     [rbp+2D00h+var_4F0], rax
0x180030f73  mov     [rbp+2D00h+var_4E8], r8d
0x180030f7a  mov     [rbp+2D00h+var_4E4], r9d
0x180030f81  mov     [rbp+2D00h+var_4E0], rdi
0x180030f88  lea     rax, [rsi+88h]
0x180030f8f  mov     [rbp+2D00h+var_4D8], rax
0x180030f96  xor     eax, eax
0x180030f98  mov     [rbp+2D00h+var_4D0], rax
0x180030f9f  lea     rax, aPublishernames; "PublisherNameSuffix"
0x180030fa6  mov     [rbp+2D00h+var_4C8], rax
0x180030fad  lea     edx, [r8+0Eh]
0x180030fb1  mov     [rbp+2D00h+var_4C0], edx
0x180030fb7  mov     [rbp+2D00h+var_4BC], r10d
0x180030fbe  lea     rax, [rsi+120h]
0x180030fc5  mov     [rbp+2D00h+var_4B8], rax
0x180030fcc  xorps   xmm0, xmm0
0x180030fcf  movups  [rbp+2D00h+var_4B0], xmm0
0x180030fd6  lea     rax, aEnableautoupda; "EnableAutoUpdate"
0x180030fdd  mov     [rbp+2D00h+var_4A0], rax
0x180030fe4  mov     [rbp+2D00h+var_498], edx
0x180030fea  mov     [rbp+2D00h+var_494], r10d
0x180030ff1  lea     rax, [rsi+0A8h]
0x180030ff8  mov     [rbp+2D00h+var_490], rax
0x180030fff  movups  [rbp+2D00h+var_488], xmm0
0x180031006  lea     rax, aUseclaimsauth; "UseClaimsAuth"
0x18003100d  mov     [rbp+2D00h+var_478], rax
0x180031014  mov     [rbp+2D00h+var_470], edx
0x18003101a  mov     [rbp+2D00h+var_46C], r10d
0x180031021  lea     rax, [rsi+0ACh]
0x180031028  mov     [rbp+2D00h+var_468], rax
0x18003102f  movups  [rbp+2D00h+var_460], xmm0
0x180031036  lea     rax, aUrl; "URL"
0x18003103d  mov     [rbp+2D00h+var_450], rax
0x180031044  mov     [rbp+2D00h+var_448], r8d
0x18003104b  mov     [rbp+2D00h+var_444], r9d
0x180031052  mov     [rbp+2D00h+var_440], rdi
0x180031059  lea     rax, [rsi+128h]
0x180031060  mov     [rbp+2D00h+var_438], rax
0x180031067  xor     eax, eax
0x180031069  mov     [rbp+2D00h+var_430], rax
0x180031070  lea     rax, aClaimshint; "ClaimsHint"
0x180031077  mov     [rbp+2D00h+var_428], rax
0x18003107e  mov     [rbp+2D00h+var_420], r8d
0x180031085  mov     [rbp+2D00h+var_41C], r9d
0x18003108c  mov     [rbp+2D00h+var_418], rdi
0x180031093  lea     rax, [rsi+168h]
0x18003109a  mov     [rbp+2D00h+var_410], rax
0x1800310a1  xor     eax, eax
0x1800310a3  mov     [rbp+2D00h+var_408], rax
0x1800310aa  lea     rax, aWorkspacefolde; "WorkspaceFolder"
0x1800310b1  mov     [rbp+2D00h+var_400], rax
0x1800310b8  lea     ecx, [rdx-0Ah]
0x1800310bb  mov     [rbp+2D00h+var_3F8], ecx
0x1800310c1  mov     [rbp+2D00h+var_3F4], r9d
0x1800310c8  mov     [rbp+2D00h+var_3F0], rdi
0x1800310cf  lea     rax, [rsi+1A8h]
0x1800310d6  mov     [rbp+2D00h+var_3E8], rax
0x1800310dd  xor     eax, eax
0x1800310df  mov     [rbp+2D00h+var_3E0], rax
0x1800310e6  lea     rax, aStartmenuroot; "StartMenuRoot"
0x1800310ed  mov     [rbp+2D00h+var_3D8], rax
0x1800310f4  mov     [rbp+2D00h+var_3D0], ecx
0x1800310fa  mov     [rbp+2D00h+var_3CC], r9d
0x180031101  mov     [rbp+2D00h+var_3C8], rdi
0x180031108  lea     rax, [rsi+1C8h]
0x18003110f  mov     [rbp+2D00h+var_3C0], rax
0x180031116  xor     eax, eax
0x180031118  mov     [rbp+2D00h+var_3B8], rax
0x18003111f  lea     rax, aNumpublishedre; "NumPublishedResources"
0x180031126  mov     [rbp+2D00h+var_3B0], rax
0x18003112d  mov     [rbp+2D00h+var_3A8], edx
0x180031133  mov     [rbp+2D00h+var_3A4], r10d
0x18003113a  lea     rax, [rsi+248h]
0x180031141  mov     [rbp+2D00h+var_3A0], rax
0x180031148  movups  [rbp+2D00h+var_398], xmm0
0x18003114f  lea     rax, aNumdownloadedr; "NumDownloadedResourceFiles"
0x180031156  mov     [rbp+2D00h+var_388], rax
0x18003115d  mov     [rbp+2D00h+var_380], edx
0x180031163  mov     [rbp+2D00h+var_37C], r10d
0x18003116a  lea     rax, [rsi+24Ch]
0x180031171  mov     [rbp+2D00h+var_378], rax
0x180031178  movups  [rbp+2D00h+var_370], xmm0
0x18003117f  lea     rax, aNumdownloadedi; "NumDownloadedIcons"
0x180031186  mov     [rbp+2D00h+var_360], rax
0x18003118d  mov     [rbp+2D00h+var_358], edx
0x180031193  mov     [rbp+2D00h+var_354], r10d
0x18003119a  lea     rax, [rsi+250h]
0x1800311a1  mov     [rbp+2D00h+var_350], rax
0x1800311a8  movups  [rbp+2D00h+var_348], xmm0
0x1800311af  lea     rax, aNumstartmenupr; "NumStartMenuPrograms"
0x1800311b6  mov     [rbp+2D00h+var_338], rax
0x1800311bd  mov     [rbp+2D00h+var_330], edx
0x1800311c3  mov     [rbp+2D00h+var_32C], r10d
0x1800311ca  lea     rax, [rsi+258h]
0x1800311d1  mov     [rbp+2D00h+var_328], rax
0x1800311d8  movups  [rbp+2D00h+var_320], xmm0
0x1800311df  lea     rax, aNumstartmenuco; "NumStartMenuComputers"
0x1800311e6  mov     [rbp+2D00h+var_310], rax
0x1800311ed  mov     [rbp+2D00h+var_308], edx
0x1800311f3  mov     [rbp+2D00h+var_304], r10d
0x1800311fa  lea     rax, [rsi+25Ch]
0x180031201  mov     [rbp+2D00h+var_300], rax
0x180031208  movups  [rbp+2D00h+var_2F8], xmm0
0x18003120f  lea     rax, aLastsuccessful_0; "LastSuccessfulUpdateTimeHigh"
0x180031216  mov     [rbp+2D00h+var_2E8], rax
0x18003121d  mov     [rbp+2D00h+var_2E0], edx
0x180031223  mov     [rbp+2D00h+var_2DC], r10d
0x18003122a  lea     rcx, [rsi+268h]
0x180031231  lea     rax, [rcx+4]
0x180031235  mov     [rbp+2D00h+var_2D8], rax
0x18003123c  movups  [rbp+2D00h+var_2D0], xmm0
0x180031243  lea     rax, aLastsuccessful; "LastSuccessfulUpdateTimeLow"
0x18003124a  mov     [rbp+2D00h+var_2C0], rax
0x180031251  mov     [rbp+2D00h+var_2B8], edx
0x180031257  mov     [rbp+2D00h+var_2B4], r10d
0x18003125e  mov     [rbp+2D00h+var_2B0], rcx
0x180031265  movups  [rbp+2D00h+var_2A8], xmm0
0x18003126c  lea     rax, aLastattempttim_0; "LastAttemptTimeHigh"
0x180031273  mov     [rbp+2D00h+var_298], rax
0x18003127a  mov     [rbp+2D00h+var_290], edx
0x180031280  mov     [rbp+2D00h+var_28C], r10d
0x180031287  lea     rcx, [rsi+270h]
0x18003128e  lea     rax, [rcx+4]
0x180031292  mov     [rbp+2D00h+var_288], rax
0x180031299  movups  [rbp+2D00h+var_280], xmm0
0x1800312a0  lea     rax, aLastattempttim; "LastAttemptTimeLow"
0x1800312a7  mov     [rbp+2D00h+var_270], rax
0x1800312ae  mov     [rbp+2D00h+var_268], edx
0x1800312b4  mov     [rbp+2D00h+var_264], r10d
0x1800312bb  mov     [rbp+2D00h+var_260], rcx
0x1800312c2  movups  [rbp+2D00h+var_258], xmm0
0x1800312c9  lea     rax, aFirstfailureti; "FirstFailureTimeHigh"
0x1800312d0  mov     [rbp+2D00h+var_248], rax
0x1800312d7  mov     [rbp+2D00h+var_240], edx
0x1800312dd  mov     [rbp+2D00h+var_23C], r10d
0x1800312e4  lea     rcx, [rsi+278h]
0x1800312eb  lea     rax, [rcx+4]
0x1800312ef  mov     [rbp+2D00h+var_238], rax
0x1800312f6  movups  [rbp+2D00h+var_230], xmm0
0x1800312fd  lea     rax, aFirstfailureti_0; "FirstFailureTimeLow"
0x180031304  mov     [rbp+2D00h+var_220], rax
0x18003130b  mov     [rbp+2D00h+var_218], edx
0x180031311  mov     [rbp+2D00h+var_214], r10d
0x180031318  mov     [rbp+2D00h+var_210], rcx
0x18003131f  movups  [rbp+2D00h+var_208], xmm0
0x180031326  lea     rax, aCreatedtimehig; "CreatedTimeHigh"
0x18003132d  mov     [rbp+2D00h+var_1F8], rax
0x180031334  mov     [rbp+2D00h+var_1F0], edx
0x18003133a  mov     [rbp+2D00h+var_1EC], r10d
0x180031341  lea     rcx, [rsi+260h]
0x180031348  lea     rax, [rcx+4]
0x18003134c  mov     [rbp+2D00h+var_1E8], rax
0x180031353  movups  [rbp+2D00h+var_1E0], xmm0
0x18003135a  lea     rax, aCreatedtimelow; "CreatedTimeLow"
0x180031361  mov     [rbp+2D00h+var_1D0], rax
0x180031368  mov     [rbp+2D00h+var_1C8], edx
0x18003136e  mov     [rbp+2D00h+var_1C4], r10d
0x180031375  mov     [rbp+2D00h+var_1C0], rcx
0x18003137c  movups  [rbp+2D00h+var_1B8], xmm0
0x180031383  lea     rax, aLastattemptsta; "LastAttemptStatus"
0x18003138a  mov     [rbp+2D00h+var_1A8], rax
0x180031391  mov     [rbp+2D00h+var_1A0], edx
0x180031397  mov     [rbp+2D00h+var_19C], r10d
0x18003139e  lea     rax, [rsi+280h]
0x1800313a5  mov     [rbp+2D00h+var_198], rax
0x1800313ac  movups  [rbp+2D00h+var_190], xmm0
0x1800313b3  lea     rax, aLastattempttit; "LastAttemptTitle"
0x1800313ba  mov     [rbp+2D00h+var_180], rax
0x1800313c1  mov     [rbp+2D00h+var_178], r8d
0x1800313c8  mov     [rbp+2D00h+var_174], r9d
0x1800313cf  mov     [rbp+2D00h+var_170], rdi
0x1800313d6  lea     rax, [rsi+288h]
0x1800313dd  mov     [rbp+2D00h+var_168], rax
0x1800313e4  xor     eax, eax
0x1800313e6  mov     [rbp+2D00h+var_160], rax
0x1800313ed  lea     rax, aLastattemptdet; "LastAttemptDetail"
0x1800313f4  mov     [rbp+2D00h+var_158], rax
0x1800313fb  mov     [rbp+2D00h+var_150], r8d
0x180031402  mov     [rbp+2D00h+var_14C], r9d
0x180031409  mov     [rbp+2D00h+var_148], rdi
0x180031410  lea     rax, [rsi+2A8h]
0x180031417  mov     [rbp+2D00h+var_140], rax
0x18003141e  xor     eax, eax
0x180031420  mov     [rbp+2D00h+var_138], rax
0x180031427  lea     rax, aLogincookie; "LoginCookie"
0x18003142e  mov     [rbp+2D00h+var_130], rax
0x180031435  mov     [rbp+2D00h+var_128], r8d
0x18003143c  mov     [rbp+2D00h+var_124], r9d
0x180031443  mov     [rbp+2D00h+var_120], rdi
0x18003144a  lea     rax, [rsi+2C8h]
0x180031451  mov     [rbp+2D00h+var_118], rax
0x180031458  xor     eax, eax
0x18003145a  mov     [rbp+2D00h+var_110], rax
0x180031461  lea     rax, aEnablefileasso; "EnableFileAssociations"
0x180031468  mov     [rbp+2D00h+var_108], rax
0x18003146f  mov     [rbp+2D00h+var_100], edx
0x180031475  mov     [rbp+2D00h+var_FC], r10d
0x18003147c  lea     rax, [rsi+360h]
0x180031483  mov     [rbp+2D00h+var_F8], rax
0x18003148a  mov     [rbp+2D00h+var_F0], rdi
0x180031491  mov     [rbp+2D00h+var_E8], edi
0x180031497  mov     [rbp+2D00h+var_E4], r9d
0x18003149e  lea     rax, aRdwebserviceur; "RDWebServiceURL"
0x1800314a5  mov     [rbp+2D00h+var_E0], rax
0x1800314ac  mov     [rbp+2D00h+var_D8], r8d
  ... truncated ...
```
