# CreateActionListInternal

- ea: `0x180069378`
- end: `0x18006cdfe`
- name: `CreateActionListInternal`
- size: `14982`
- prototype: ``
- caller_count: `1`
- callee_count: `78`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x18006ce04`

## callees

- `0x1800031d0`
- `0x180004c70`
- `0x180006198`
- `0x1800062b8`
- `0x180007f68`
- `0x180008b78`
- `0x180009660`
- `0x180009750`
- `0x18000ba40`
- `0x18000ccb8`
- `0x18000f614`
- `0x18000f874`
- `0x18001268c`
- `0x1800172bc`
- `0x18001a810`
- `0x18001b9e4`
- `0x18001ba4c`
- `0x18001c608`
- `0x18001d650`
- `0x18002aa74`
- `0x18002c7e8`
- `0x18002d214`
- `0x18002d610`
- `0x1800369c0`
- `0x18003d278`
- `0x18003ddc8`
- `0x18003e9cc`
- `0x180042764`
- `0x180042f28`
- `0x180044f38`
- `0x180045908`
- `0x180056b28`
- `0x1800662cc`
- `0x180066804`
- `0x180067094`
- `0x180067464`
- `0x18006757c`
- `0x1800676bc`
- `0x180067794`
- `0x180067b1c`
- `0x180067e38`
- `0x180067fcc`
- `0x1800684dc`
- `0x180068610`
- `0x1800686ec`
- `0x1800688b8`
- `0x180068a6c`
- `0x180068cd8`
- `0x180069378`
- `0x18006d7e0`

## string_xrefs

- `0x18006cd15`: `onecore\internal\sdk\inc\wil\opensource\wil\stl.h`
- `0x180069bb8`: `Some Device state will come from input file for this scenario`
- `0x180069913`: `arbiter: --- CreateActionList begin: Sandbox: {0} ---`
- `0x18006970b`: `*DB*.xml.cab`
- `0x180069727`: `*DB*.xml.cab`
- `0x180069818`: `Failed while trying to find compDB cabs in sandbox: {0}`
- `0x180069ab7`: `  Scenario: Upgrade or update`
- `0x180069eb6`: `No action list or device info path specified`
- `0x180069fbd`: `Failed to configurate scenario behavior`
- `0x18006a7d8`: `Failed to create the device gather instance`
- `0x18006a90c`: `Servicing stack state needed repair and can't continue`
- `0x18006b2a5`: `Failed to populate composition database.`
- `0x18006b3bd`: `Failed to populate composition database alternate payload sources`
- `0x18006b531`: `Failed getting the final path to the loaded CompDB folder`
- `0x18006c13c`: `Failed initializing update evaluator from device info`
- `0x18006bf26`: `DeviceInventory.xml`
- `0x18006c515`: `Failed to convert device installed SSU version:{0}`
- `0x18006c62e`: `Disabling scavenge because the required SSU version is not installed, installed SSU version: {1}`
- `0x18006c3d2`: `Failed to get installed servicing stack version`
- `0x18006c791`: `arbiter: ActionList created: {0}`
- `0x18006c7e9`: `  Feature Installs: {0}`
- `0x18006c825`: `  Package Installations: {0}`
- `0x18006c84e`: `  Product Updates: {0}`
- `0x18006ca10`: `PlannedDeviceInventory.PBR.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=43
__int64 __fastcall CreateActionListInternal(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        wchar_t *a5,
        int a6,
        int a7,
        __int64 a8,
        int a9,
        wchar_t *a10,
        wchar_t *a11,
        struct ActionList **a12)
{
  __int64 v12; // r12
  int v14; // r13d
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rax
  _QWORD *v18; // rax
  __int64 v19; // rdi
  _QWORD *v20; // rax
  int v21; // edx
  int v22; // r8d
  int v23; // r9d
  int *v24; // rax
  struct IDeviceInfoGather *v25; // r14
  __int16 *trivial_2; // rax
  const char *v27; // r9
  __int64 v28; // rax
  __int64 v29; // r8
  __int128 *v30; // rax
  unsigned int AllFilesAndDirectories; // ebx
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int128 v34; // xmm0
  const wchar_t *v35; // xmm1_8
  const wchar_t *v36; // rdx
  HKEY v37; // rcx
  unsigned int v38; // r8d
  const wchar_t *v39; // r9
  __int64 v40; // rsi
  __int64 v41; // rbx
  int v42; // ecx
  int v43; // ecx
  int v44; // ecx
  int v45; // ecx
  const wchar_t *v46; // rax
  int v47; // eax
  bool v48; // zf
  __int64 v49; // rdx
  const char *v50; // r9
  __int64 result; // rax
  unsigned int v52; // eax
  wchar_t *v53; // rbx
  __int64 v54; // rdx
  int v55; // eax
  wchar_t *v56; // r12
  __int64 v57; // rdx
  int v58; // eax
  const char *v59; // r9
  __int64 v60; // rdx
  int v61; // edx
  struct ActionList **v62; // rsi
  __int64 v63; // r8
  struct ActionList *v64; // rcx
  int ActionList; // eax
  __int64 v66; // rdx
  const wchar_t *v67; // rax
  int v68; // eax
  __int64 v69; // rdx
  __int32 *v70; // rax
  __int64 v71; // r8
  __int64 v72; // rdx
  unsigned int v73; // esi
  int SessionCompDBs; // eax
  const char *v75; // r9
  __int64 v76; // r13
  __int64 v77; // rcx
  __int64 v78; // rdx
  _QWORD *v79; // r8
  __int32 *v80; // rax
  char v81; // si
  int v82; // eax
  __int64 v83; // rdx
  __int64 v84; // rax
  int v85; // eax
  __int64 v86; // rdx
  __int64 v87; // rax
  int v88; // eax
  __int64 v89; // rax
  int NameValuePairValue; // eax
  __int64 v91; // rdx
  __int64 BuildLayers; // rax
  int v93; // eax
  __int64 v94; // rdx
  int v95; // eax
  unsigned int v96; // ebx
  __int64 v97; // rdx
  __int64 *v98; // rcx
  __int64 v99; // rbx
  __int64 v100; // rdx
  int v101; // eax
  __int64 v102; // rdx
  int v103; // eax
  __int64 v104; // rdx
  int v105; // eax
  __int64 v106; // rdx
  __int64 v107; // rcx
  __int64 v108; // rax
  int FinalPath; // eax
  __int64 v110; // rdx
  __int128 *v111; // rax
  __int64 Directory; // rax
  int v113; // eax
  __int64 v114; // rdx
  unsigned int v115; // r13d
  int v116; // eax
  const char *v117; // r9
  __int64 v118; // rdx
  char IsSatelliteValueInstalled; // bl
  __int64 v120; // rax
  int v121; // eax
  __int64 v122; // rdx
  __int64 v123; // rax
  int v124; // eax
  __int64 v125; // rdx
  _QWORD *v126; // rbx
  __int64 v127; // rsi
  __int64 v128; // rdx
  __int64 v129; // r13
  __int64 v130; // rax
  struct ActionList **v131; // rsi
  int v132; // eax
  int v133; // eax
  int v134; // eax
  int v135; // eax
  __int64 v136; // rdx
  __int64 v137; // rdx
  int v138; // eax
  __int64 v139; // rdx
  __int64 v140; // r8
  __int64 v141; // rdx
  __int64 v142; // rdx
  int v143; // eax
  __int64 v144; // rdx
  int v145; // eax
  __int64 v146; // rdx
  const wchar_t *v147; // rcx
  int v148; // eax
  int v149; // eax
  int v150; // eax
  struct ActionList **v151; // rbx
  int v152; // eax
  int v153; // eax
  unsigned int v154; // ebx
  __int64 v155; // rdx
  int *v156; // [rsp+20h] [rbp-6E8h]
  int *v157; // [rsp+20h] [rbp-6E8h]
  int *v158; // [rsp+20h] [rbp-6E8h]
  int *v159; // [rsp+20h] [rbp-6E8h]
  int *v160; // [rsp+20h] [rbp-6E8h]
  int *v161; // [rsp+20h] [rbp-6E8h]
  int *v162; // [rsp+20h] [rbp-6E8h]
  int *v163; // [rsp+20h] [rbp-6E8h]
  int v164[2]; // [rsp+40h] [rbp-6C8h] BYREF
  __int64 v165; // [rsp+48h] [rbp-6C0h]
  char v166; // [rsp+50h] [rbp-6B8h]
  struct ActionList **v167; // [rsp+58h] [rbp-6B0h] BYREF
  __int64 v168[2]; // [rsp+60h] [rbp-6A8h] BYREF
  struct IDeviceInfoGather *v169; // [rsp+70h] [rbp-698h] BYREF
  __int64 v170; // [rsp+78h] [rbp-690h] BYREF
  __int128 v171; // [rsp+80h] [rbp-688h] BYREF
  __int64 v172; // [rsp+90h] [rbp-678h]
  unsigned __int64 v173; // [rsp+98h] [rbp-670h]
  wchar_t *v174; // [rsp+A0h] [rbp-668h]
  int v175[2]; // [rsp+A8h] [rbp-660h] BYREF
  __int64 v176; // [rsp+B0h] [rbp-658h]
  __int64 v177; // [rsp+B8h] [rbp-650h]
  int v178[2]; // [rsp+C0h] [rbp-648h] BYREF
  _QWORD v179[3]; // [rsp+C8h] [rbp-640h] BYREF
  wchar_t *v180; // [rsp+E0h] [rbp-628h] BYREF
  wchar_t *v181; // [rsp+E8h] [rbp-620h] BYREF
  wchar_t *v182; // [rsp+F0h] [rbp-618h] BYREF
  wchar_t *v183; // [rsp+F8h] [rbp-610h] BYREF
  wchar_t *v184[2]; // [rsp+100h] [rbp-608h] BYREF
  _QWORD v185[2]; // [rsp+110h] [rbp-5F8h] BYREF
  __int64 v186; // [rsp+120h] [rbp-5E8h] BYREF
  __int64 v187; // [rsp+128h] [rbp-5E0h] BYREF
  wchar_t *v188[2]; // [rsp+130h] [rbp-5D8h] BYREF
  __int64 v189; // [rsp+140h] [rbp-5C8h] BYREF
  wchar_t *v190; // [rsp+150h] [rbp-5B8h] BYREF
  int v191[2]; // [rsp+160h] [rbp-5A8h] BYREF
  int v192; // [rsp+168h] [rbp-5A0h] BYREF
  unsigned int v193; // [rsp+16Ch] [rbp-59Ch] BYREF
  __int64 v194[2]; // [rsp+170h] [rbp-598h] BYREF
  __int128 v195; // [rsp+180h] [rbp-588h] BYREF
  const wchar_t *v196; // [rsp+190h] [rbp-578h]
  unsigned __int64 v197; // [rsp+198h] [rbp-570h]
  _BYTE v198[80]; // [rsp+1A0h] [rbp-568h] BYREF
  int v199; // [rsp+1F0h] [rbp-518h] BYREF
  void **v200; // [rsp+1F8h] [rbp-510h]
  __int64 v201; // [rsp+200h] [rbp-508h]
  __int64 v202; // [rsp+208h] [rbp-500h]
  _QWORD *v203; // [rsp+210h] [rbp-4F8h]
  __int64 v204; // [rsp+218h] [rbp-4F0h]
  unsigned int v205; // [rsp+220h] [rbp-4E8h]
  __int64 v206; // [rsp+228h] [rbp-4E0h]
  _QWORD *v207; // [rsp+230h] [rbp-4D8h]
  __int64 v208; // [rsp+238h] [rbp-4D0h]
  _QWORD *v209; // [rsp+240h] [rbp-4C8h]
  __int64 v210; // [rsp+248h] [rbp-4C0h]
  __int128 v211; // [rsp+250h] [rbp-4B8h]
  __int64 v212; // [rsp+260h] [rbp-4A8h]
  __int16 v213; // [rsp+268h] [rbp-4A0h]
  char v214; // [rsp+26Ah] [rbp-49Eh]
  __int128 v215; // [rsp+270h] [rbp-498h]
  __int64 v216; // [rsp+280h] [rbp-488h]
  __int64 v217; // [rsp+288h] [rbp-480h]
  __int64 v218; // [rsp+290h] [rbp-478h]
  __int64 v219; // [rsp+298h] [rbp-470h]
  char v220; // [rsp+2A0h] [rbp-468h]
  __m128i si128; // [rsp+2B0h] [rbp-458h] BYREF
  __m128i v222; // [rsp+2C0h] [rbp-448h] BYREF
  __m128i v223; // [rsp+2D0h] [rbp-438h]
  __m128i v224; // [rsp+2E0h] [rbp-428h]
  __m128i v225; // [rsp+2F0h] [rbp-418h]
  __m128i v226; // [rsp+300h] [rbp-408h]
  __m128i v227; // [rsp+310h] [rbp-3F8h]
  __m128i v228; // [rsp+320h] [rbp-3E8h]
  int v229; // [rsp+330h] [rbp-3D8h]
  _DWORD v230[3]; // [rsp+334h] [rbp-3D4h] BYREF
  __int64 v231[46]; // [rsp+340h] [rbp-3C8h] BYREF
  int v232[108]; // [rsp+4B0h] [rbp-258h] BYREF
  char v233; // [rsp+660h] [rbp-A8h]
  wil::details::in1diag3 *retaddr; // [rsp+708h] [rbp+0h]

  v179[1] = -2;
  v12 = a3;
  v186 = a3;
  v193 = a2;
  v177 = a8;
  v183 = a5;
  v187 = a8;
  v184[0] = a10;
  v174 = a11;
  v167 = a12;
  v14 = 0;
  v185[0] = 0;
  v189 = 0;
  v190 = 0;
  if ( a12 )
    *a12 = 0;
  try
  {
    CCompositionDatabase::CCompositionDatabase((CCompositionDatabase *)v232);
    CDeviceInfo::CDeviceInfo((CDeviceInfo *)v231);
    CActionListCreator::CActionListCreator(v198);
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffff00000000);
    v222 = _mm_load_si128((const __m128i *)&_xmm_ffffffff0000000000000000ffffffff);
    v223 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    v224 = v223;
    v225 = v223;
    v226 = v223;
    v227 = v223;
    v228 = v223;
    v229 = -1;
    v230[0] = 0;
    v194[1] = 0;
    v15 = operator new(0x40u);
    *v15 = v15;
    v15[1] = v15;
    v15[2] = v15;
    *((_WORD *)v15 + 12) = 257;
    v194[0] = (__int64)v15;
    v199 = 0;
    v201 = 0;
    v200 = &Windows::Rtl::PrivateHeapPool::`vftable';
    v202 = 0;
    v203 = 0;
    v204 = 0;
    v16 = operator new(0x28u);
    *v16 = v16;
    v16[1] = v16;
    v16[2] = v16;
    *((_WORD *)v16 + 12) = 257;
    v203 = v16;
    v205 = 0;
    v206 = 0;
    v207 = 0;
    v208 = 0;
    v17 = operator new(0x40u);
    *v17 = v17;
    v17[1] = v17;
    v17[2] = v17;
    *((_WORD *)v17 + 12) = 257;
    v207 = v17;
    v209 = 0;
    v210 = 0;
    v18 = operator new(0x40u);
    *v18 = v18;
    v18[1] = v18;
    v18[2] = v18;
    *((_WORD *)v18 + 12) = 257;
    v209 = v18;
    v211 = 0;
    v212 = 0;
    v213 = 0;
    v214 = 0;
    v215 = 0;
    v216 = 0;
    v217 = 0;
    v218 = 0;
    v219 = 0;
    v220 = 0;
    v179[2] = 0;
    v19 = 0;
    v170 = 0;
    *(_QWORD *)v191 = 0;
    v188[0] = 0;
    v168[1] = 0;
    v20 = operator new(0x88u);
    *v20 = v20;
    v20[1] = v20;
    v20[2] = v20;
    *((_WORD *)v20 + 12) = 257;
    v168[0] = (__int64)v20;
    if ( a8 )
    {
      *(_QWORD *)v175 = "offline";
      v176 = 7;
    }
    else
    {
      *(_QWORD *)v164 = "online";
      v165 = 6;
    }
    v24 = v164;
    if ( a8 )
      v24 = v175;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
      LogAdapter::Logger::LogNumObjects<std::string_view>(LogAdapter::g_Logger, v21, v22, v23, (__int64)v24);
    v25 = 0;
    v169 = 0;
    LOBYTE(v14) = v177 != 0;
    if ( !a2 )
    {
      v195 = 0;
      v196 = 0;
      trivial_2 = (__int16 *)_std_find_trivial_2(L"*DB*.xml.cab", word_1801DA40A, 0);
      if ( trivial_2 == word_1801DA40A || (v28 = ((char *)trivial_2 - (char *)L"*DB*.xml.cab") >> 1, v28 == -1) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xEB,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\stl.h",
          v27);
      *(_QWORD *)v164 = L"*DB*.xml.cab";
      v165 = v28;
      v171 = 0;
      v172 = 0;
      v173 = 0;
      v29 = -1;
      do
        ++v29;
      while ( v183[v29] );
      std::wstring::_Construct<1,wchar_t const *>(&v171);
      v30 = &v171;
      if ( v173 > 7 )
        v30 = (__int128 *)v171;
      *(_QWORD *)v175 = v30;
      v176 = v172;
      AllFilesAndDirectories = GetAllFilesAndDirectories(
                                 (unsigned int)v175,
                                 (unsigned int)v164,
                                 0,
                                 (unsigned int)&v195,
                                 0);
      std::wstring::~wstring(&v171);
      if ( (AllFilesAndDirectories & 0x80000000) != 0 )
      {
        v192 = AllFilesAndDirectories;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed while trying to find compDB cabs in sandbox: {0}",
            &v183);
          v174 = (wchar_t *)&v192;
          LOBYTE(v32) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v32,
            3,
            ": {}");
        }
        std::vector<std::wstring>::_Tidy(&v195);
        std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
        if ( !*(_QWORD *)v191 )
          goto LABEL_380;
        goto LABEL_209;
      }
      if ( (_QWORD)v195 == *((_QWORD *)&v195 + 1) )
        v14 |= 2u;
      std::vector<std::wstring>::_Tidy(&v195);
    }
    LogAdapter::TraceInfo<wchar_t const *>("arbiter: --- CreateActionList begin: Sandbox: {0} ---", &v183);
    if ( a2 )
    {
      if ( a2 == 1 )
      {
        v34 = ___LiteralObject__2U__BaseLiteralBuffer__07U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0EE__0GF__0HD__0GL__0HE__0GP__0HA__0A_____0A__00_01_02_03_04_05_06_Details_RtlStringLiterals__3U_LUNICODE_STRING__B;
        v35 = L"Desktop";
      }
      else
      {
        v34 = ___LiteralObject__2U__BaseLiteralBuffer__0BE_U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0FF__0GO__0GL__0GO__0GP__0HH__0GO__0CA__0GE__0GF__0HG__0GJ__0GD__0GF__0CA__0HE__0HJ__0HA__0GF__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__0M__0N__0O__0P__0BA__0BB__0BC__0BD__Details_RtlStringLiterals__3U_LUNICODE_STRING__B;
        v35 = L"Unknown device type";
      }
    }
    else
    {
      v34 = ___LiteralObject__2U__BaseLiteralBuffer__06U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0EN__0GP__0GC__0GJ__0GM__0GF__0A_____0A__00_01_02_03_04_05_Details_RtlStringLiterals__3U_LUNICODE_STRING__B;
      v35 = L"Mobile";
    }
    v195 = v34;
    v196 = v35;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LOBYTE(v33) = 1;
      LogAdapter::Logger::LogNumObjects<_LUNICODE_STRING>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v33,
        1,
        "  Device type: {0}",
        &v195);
    }
    v195 = 0;
    v196 = 0;
    v197 = 7;
    LOWORD(v195) = 0;
    v171 = 0;
    v172 = 0;
    v173 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v171);
    std::wstring::~wstring(&v195);
    LogAdapter::TraceInfo<std::wstring>("  Using flags: {0}", &v171);
    std::wstring::~wstring(&v171);
    LogAdapter::TraceInfo<wchar_t const *>("  Stack: {0}", &v189);
    LogAdapter::TraceInfo<wchar_t const *>("  Windir: {0}", &v187);
    LogAdapter::TraceInfo<wchar_t const *>("  DeviceInfo: {0}", v185);
    LogAdapter::TraceInfo<wchar_t const *>("  ActionList: {0}", v184);
    LogAdapter::TraceInfo<wchar_t const *>("  Country Code: {0}", &v190);
    if ( v12 )
    {
      v179[0] = ModuleIDToString(*(unsigned int *)(v12 + 8));
      LogAdapter::TraceInfo<wchar_t const *>("  Scenario: {0}", v179);
    }
    else
    {
      LogAdapter::TraceInfo<>("  Scenario: Upgrade or update");
    }
    if ( !v12 )
      goto LABEL_74;
    v40 = v187;
    v41 = v185[0];
    v37 = (HKEY)*(unsigned int *)(v12 + 56);
    if ( (_DWORD)v37 )
    {
      v42 = (_DWORD)v37 - 1;
      if ( v42 )
      {
        v43 = v42 - 1;
        if ( v43 )
        {
          v44 = v43 - 1;
          if ( v44 )
          {
            v45 = v44 - 1;
            if ( v45 )
            {
              if ( v45 == 1 )
                v46 = L"UpgradeCloudRecoveryInventory";
              else
                v46 = L"ModuleOperation is not specified";
            }
            else
            {
              v46 = L"ExecuteCloudBMR";
            }
          }
          else
          {
            v46 = L"ExecuteOfflineCloudPBR";
          }
        }
        else
        {
          v46 = L"ExecuteOnlineCloudPBR";
        }
      }
      else
      {
        v46 = L"CollectCloudRecoveryInventory";
      }
      *(_QWORD *)v178 = v46;
      LogAdapter::TraceInfo<wchar_t const *>("  Module operation: {0}", v178);
    }
    if ( *(_DWORD *)(v12 + 8) != 15 )
      goto LABEL_74;
    v47 = *(_DWORD *)(v12 + 56);
    switch ( v47 )
    {
      case 1:
        if ( !a12 )
          goto LABEL_74;
        goto LABEL_69;
      case 3:
        if ( !v40 )
          goto LABEL_69;
        break;
      case 2:
        if ( v40 )
          goto LABEL_69;
        break;
      case 4:
        if ( !v41 )
          goto LABEL_69;
LABEL_56:
        v48 = v167 == 0;
LABEL_68:
        if ( !v48 )
        {
LABEL_74:
          v52 = v193;
          if ( v193 == 1 )
          {
            v53 = 0;
            v182 = 0;
            v181 = v190;
            if ( !v177 )
            {
              if ( v190 )
              {
                v192 = CbsRegSetStringValue(v37, v36, v38, v39, v190);
                if ( v192 < 0 && *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    0,
                    1,
                    "Failed to set current country code:{0}",
                    &v181);
                  *(_QWORD *)v164 = &v192;
                  v156 = v164;
                  LOBYTE(v54) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    v54,
                    1,
                    ": {0}");
                }
              }
              else
              {
                v55 = CbsRegQueryStringValue(
                        HKEY_LOCAL_MACHINE,
                        L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Servicing",
                        v38,
                        L"CountryCode",
                        &v182);
                v53 = v182;
                if ( v55 >= 0 && v182 )
                  v181 = v182;
              }
            }
            if ( !v181 )
              v181 = L"Unknown";
            v56 = v181;
            v171 = 0;
            v172 = 0;
            v173 = 0;
            std::wstring::_Construct<1,wchar_t const *>(&v171);
            CDeviceInfo::AddValuePair(v231, &v171, v56);
            std::wstring::~wstring(&v171);
            if ( v53 )
              operator delete(v53 - 4);
            v12 = v186;
            v52 = v193;
          }
          if ( !v167 && !v185[0] )
          {
            v192 = -2147024809;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                *(_QWORD *)&LogAdapter::g_Logger,
                0,
                3,
                "No action list or device info path specified");
              *(_QWORD *)v164 = &v192;
              v156 = v164;
              LOBYTE(v57) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v57,
                3,
                ": {}");
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x554,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
              (const char *)0x80070057LL,
              (int)v156);
            std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
            if ( !*(_QWORD *)v191 )
              goto LABEL_73;
            goto LABEL_72;
          }
          v58 = ConfigureScenarioBehaviors(v52, 0, v12, &si128);
          AllFilesAndDirectories = v58;
          if ( v58 < 0 )
          {
            LODWORD(v180) = v58;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                *(_QWORD *)&LogAdapter::g_Logger,
                0,
                3,
                "Failed to configurate scenario behavior");
              *(_QWORD *)v164 = &v180;
              v156 = v164;
              LOBYTE(v60) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v60,
                3,
                ": {}");
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x56D,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
              (const char *)AllFilesAndDirectories,
              (int)v156);
            std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
            if ( !*(_QWORD *)v191 )
              goto LABEL_380;
            goto LABEL_209;
          }
          if ( v223.m128i_i32[3] == -1 )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x45,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\inc\\CDeviceInfo.h",
              v59);
          if ( v223.m128i_i32[3] != 1 )
            goto LABEL_103;
          if ( v224.m128i_i32[0] == -1 )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x48,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\inc\\CDeviceInfo.h",
              v59);
          v61 = 0;
          v192 = 0;
          if ( v224.m128i_i32[0] == 1 )
          {
LABEL_103:
            v61 = 2;
            v192 = 2;
          }
          if ( si128.m128i_i32[3] == -1 )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x1E6,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
              v59);
          if ( si128.m128i_i32[3] == 1 )
          {
            v61 |= 1u;
            v192 = v61;
          }
          if ( v222.m128i_i32[0] == -1 )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x1E8,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
              v59);
          if ( v222.m128i_i32[0] == 1 )
            v192 = v61 | 4;
          v62 = v167;
          if ( v184[0] && v167 && (unsigned int)DoesFileExist(v184[0]) )
          {
            v64 = *v62;
            *v62 = 0;
            if ( v64 )
              (**(void (__fastcall ***)(struct ActionList *))v64)(v64);
            ActionList = LoadActionList(v64, v184[0], v63, v62);
            AllFilesAndDirectories = ActionList;
            if ( ActionList < 0 )
            {
              LODWORD(v180) = ActionList;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed to load action list: {0}",
                  v184);
                *(_QWORD *)v164 = &v180;
                v156 = v164;
                LOBYTE(v66) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v66,
                  3,
                  ": {}");
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x58C,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
                (const char *)AllFilesAndDirectories,
                (int)v156);
              std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
              if ( !*(_QWORD *)v191 )
                goto LABEL_380;
              goto LABEL_209;
            }
            LogAdapter::TraceInfo<wchar_t const *>("arbiter: actionlist loaded: {0}", v184);
            if ( si128.m128i_i32[1] == -1 )
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x1E2,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
                v59);
            if ( si128.m128i_i32[1] == 1 )
            {
              v67 = v12 ? *(const wchar_t **)(v12 + 16) : 0LL;
              v68 = CActionListCreator::ExpressDownloadResumed((CActionListCreator *)v198, v62, v183, v184[0], v67);
              AllFilesAndDirectories = v68;
              if ( v68 < 0 )
              {
                LODWORD(v180) = v68;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed resuming actionlist creation for express download");
                  *(_QWORD *)v164 = &v180;
                  v156 = v164;
                  LOBYTE(v69) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    v69,
                    3,
                    ": {}");
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x595,
                  (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
                  (const char *)AllFilesAndDirectories,
                  (int)v156);
                std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
                if ( !*(_QWORD *)v191 )
                  goto LABEL_380;
                goto LABEL_209;
              }
            }
            if ( si128.m128i_i32[2] == -1 )
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x1E4,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
                v59);
            if ( si128.m128i_i32[2] == 1 )
            {
              std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
              if ( *(_QWORD *)v191 )
              {
                (***(void (__fastcall ****)(_QWORD))v191)(*(_QWORD *)v191);
                *(_QWORD *)v191 = 0;
              }
LABEL_134:
              CUpdateEvaluator::~CUpdateEvaluator((CUpdateEvaluator *)&v199);
              std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(v194);
              CActionListCreator::~CActionListCreator((CActionListCreator *)v198);
              CDeviceInfo::~CDeviceInfo((CDeviceInfo *)v231);
              CCompositionDatabase::~CCompositionDatabase((CCompositionDatabase *)v232);
              return 0;
            }
          }
          if ( v185[0] && v62 )
          {
            v70 = &v222.m128i_i32[2];
            while ( *v70 != 1 )
            {
              if ( ++v70 >= v230 )
                goto LABEL_151;
            }
            if ( !v12 || *(_DWORD *)(v12 + 8) != 15 || (v71 = 1, *(_DWORD *)(v12 + 56) != 4) )
              v71 = 0;
            AllFilesAndDirectories = CDeviceInfo::Load(v231, v185[0], v71);
            if ( (int)(AllFilesAndDirectories + 0x80000000) >= 0 && AllFilesAndDirectories != -2147024894 )
            {
              LODWORD(v180) = AllFilesAndDirectories;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed to load device information file: {0}",
                  v185);
                *(_QWORD *)v164 = &v180;
                v156 = v164;
                LOBYTE(v72) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v72,
                  3,
                  ": {}");
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x5AC,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
                (const char *)AllFilesAndDirectories,
                (int)v156);
              std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
              if ( !*(_QWORD *)v191 )
                goto LABEL_380;
              goto LABEL_209;
            }
          }
LABEL_151:
          if ( v228.m128i_i32[1] == -1 )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x70,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\inc\\CDeviceInfo.h",
              v59);
          if ( v228.m128i_i32[1] != 1 )
            v14 |= 0x40u;
          v73 = v193;
          SessionCompDBs = LoadSessionCompDBs(v12, v14, v193, (_DWORD)v183, (__int64)v191);
          AllFilesAndDirectories = SessionCompDBs;
          if ( SessionCompDBs < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x5B8,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
              (const char *)(unsigned int)SessionCompDBs,
              (int)v157);
            std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
            if ( !*(_QWORD *)v191 )
            {
LABEL_380:
              CUpdateEvaluator::~CUpdateEvaluator((CUpdateEvaluator *)&v199);
              std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(v194);
              CActionListCreator::~CActionListCreator((CActionListCreator *)v198);
              CDeviceInfo::~CDeviceInfo((CDeviceInfo *)v231);
              CCompositionDatabase::~CCompositionDatabase((CCompositionDatabase *)v232);
              return AllFilesAndDirectories;
            }
LABEL_209:
            (***(void (__fastcall ****)(_QWORD))v191)(*(_QWORD *)v191);
            *(_QWORD *)v191 = 0;
            goto LABEL_380;
          }
          v166 = 0;
          v76 = *(_QWORD *)v191;
          v77 = *(_QWORD *)(*(_QWORD *)v191 + 8LL);
          v78 = v77 + 56LL * *(unsigned int *)(*(_QWORD *)v191 + 16LL);
          while ( v77 != v78 )
          {
            v79 = *(_QWORD **)(*(_QWORD *)(v77 + 24) + 656LL);
            if ( v79 && *v79 )
            {
              v166 = 1;
              break;
            }
            v77 += 56;
          }
          if ( !v187 && v185[0] )
          {
LABEL_169:
            v81 = 0;
          }
          else
          {
            v80 = &v222.m128i_i32[2];
            while ( *v80 != 1 )
            {
              if ( ++v80 >= v230 )
                goto LABEL_169;
            }
            v82 = DeviceInfoGatherFactory::CreateInstance(v73, v189, v187, &v169);
            AllFilesAndDirectories = v82;
            if ( v82 < 0 )
            {
              LODWORD(v180) = v82;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed to create the device gather instance");
                *(_QWORD *)v164 = &v180;
                v157 = v164;
                LOBYTE(v83) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v83,
                  3,
                  ": {}");
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x5D6,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
                (const char *)AllFilesAndDirectories,
                (int)v157);
              if ( v169 )
                (*(void (__fastcall **)(struct IDeviceInfoGather *, __int64))(*(_QWORD *)v169 + 64LL))(v169, 1);
              std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
              if ( !*(_QWORD *)v191 )
                goto LABEL_380;
              goto LABEL_209;
            }
            v25 = v169;
            if ( v73 == 1 )
            {
              v84 = (*(__int64 (__fastcall **)(struct IDeviceInfoGather *))(*(_QWORD *)v169 + 56LL))(v169);
              v85 = RepairServicingStackStateIfNeeded(v84);
              AllFilesAndDirectories = v85;
              if ( v85 < 0 )
              {
                LODWORD(v180) = v85;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    0,
                    3,
                    "Servicing stack state needed repair and can't continue");
                  *(_QWORD *)v164 = &v180;
                  v157 = v164;
                  LOBYTE(v86) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    v86,
                    3,
                    ": {}");
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x5DE,
                  (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
                  (const char *)AllFilesAndDirectories,
                  (int)v157);
                if ( v25 )
                  (*(void (__fastcall **)(struct IDeviceInfoGather *, __int64))(*(_QWORD *)v25 + 64LL))(v25, 1);
                std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
                if ( !*(_QWORD *)v191 )
                  goto LABEL_380;
                goto LABEL_209;
              }
            }
            v87 = (*(__int64 (__fastcall **)(struct IDeviceInfoGather *))(*(_QWORD *)v25 + 56LL))(v25);
            StoreDeviceInfoGatherStatus(v73, v87, 0);
            v88 = CDeviceInfo::PopulateDeviceInformation(
                    (CDeviceInfo *)v231,
                    0,
                    v25,
                    (const struct CDeviceInfo::CollectionBehavior *)&v222.m128i_u64[1],
                    v174);
            AllFilesAndDirectories = v88;
            if ( v88 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x5EE,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
                (const char *)(unsigned int)v88,
                (int)v157);
              if ( v25 )
                (*(void (__fastcall **)(struct IDeviceInfoGather *, __int64))(*(_QWORD *)v25 + 64LL))(v25, 1);
              std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
              if ( !*(_QWORD *)v191 )
                goto LABEL_380;
              goto LABEL_209;
            }
            v81 = 1;
            v89 = (*(__int64 (__fastcall **)(struct IDeviceInfoGather *))(*(_QWORD *)v25 + 56LL))(v25);
            StoreDeviceInfoGatherStatus(v193, v89, 1);
          }
          if ( v224.m128i_i32[2] == -1 )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x4D,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\inc\\CDeviceInfo.h",
              v75);
          if ( v224.m128i_i32[2] == 1 )
          {
            NameValuePairValue = CDeviceInfo::GetNameValuePairValue(
                                   (CDeviceInfo *)v231,
                                   L"BuildBranch",
                                   (const wchar_t **)v188,
                                   1);
            AllFilesAndDirectories = NameValuePairValue;
            if ( NameValuePairValue < 0 )
            {
              LODWORD(v180) = NameValuePairValue;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed to get device OS Branch.");
                *(_QWORD *)v164 = &v180;
                v157 = v164;
                LOBYTE(v91) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v91,
                  3,
                  ": {}");
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x602,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
                (const char *)AllFilesAndDirectories,
                (int)v157);
              if ( v25 )
                (*(void (__fastcall **)(struct IDeviceInfoGather *, __int64))(*(_QWORD *)v25 + 64LL))(v25, 1);
              std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
              if ( !*(_QWORD *)v191 )
                goto LABEL_380;
              goto LABEL_209;
            }
            LogAdapter::TraceInfo<wchar_t const *>("Device: BuildBranch {0}", v188);
            BuildLayers = CDeviceInfo::GetBuildLayers(v231, v164);
            std::map<std::wstring,CDeviceInfo::BuildLayer>::operator=(v168, BuildLayers);
            std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v164);
          }
          if ( v223.m128i_i32[1] == -1 )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x40,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\inc\\CDeviceInfo.h",
              v75);
          if ( v223.m128i_i32[1] == 1 )
          {
            v182 = 0;
            v93 = CDeviceInfo::GetNameValuePairValue((CDeviceInfo *)v231, L"OSVersion", (const wchar_t **)&v182, 1);
            AllFilesAndDirectories = v93;
            if ( v93 < 0 )
            {
              LODWORD(v180) = v93;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed to get device OS version");
                *(_QWORD *)v164 = &v180;
                v157 = v164;
                LOBYTE(v94) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v94,
                  3,
                  ": {}");
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x611,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
                (const char *)AllFilesAndDirectories,
                (int)v157);
              if ( v25 )
                (*(void (__fastcall **)(struct IDeviceInfoGather *, __int64))(*(_QWORD *)v25 + 64LL))(v25, 1);
              std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
              if ( !*(_QWORD *)v191 )
                goto LABEL_380;
              goto LABEL_209;
            }
            LogAdapter::TraceInfo<wchar_t const *>("Device: OS version {0}", &v182);
            std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::emplace<wchar_t * const &>(
              v194,
              v164,
              &v182);
          }
          if ( v223.m128i_i32[3] == -1 )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x45,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\inc\\CDeviceInfo.h",
              v75);
          if ( v223.m128i_i32[3] == 1 )
          {
            v182 = 0;
            v181 = 0;
            if ( v224.m128i_i32[0] == -1 )
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x48,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\inc\\CDeviceInfo.h",
                v75);
            if ( v224.m128i_i32[0] == 1 && CDeviceInfo::IsNameValuePairEmpty((CDeviceInfo *)v231, L"EditionVersion") )
            {
              CBSWdsLog(
                0x4000000,
                0,
                0,
                "Device: Edition is not present in device information. Continuing because best effort flag is set.");
            }
            else
            {
              v95 = CDeviceInfo::GetNameValuePairValue(
                      (CDeviceInfo *)v231,
                      L"EditionVersion",
                      (const wchar_t **)&v182,
                      1);
              v96 = v95;
              if ( v95 < 0 )
              {
                LODWORD(v180) = v95;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed to get device Edition version");
                  *(_QWORD *)v164 = &v180;
                  v157 = v164;
                  LOBYTE(v97) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    v97,
                    3,
                    ": {}");
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x630,
                  (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
                  (const char *)v96,
                  (int)v157);
                if ( !v25 )
                  goto LABEL_286;
LABEL_285:
                (*(void (__fastcall **)(struct IDeviceInfoGather *, __int64))(*(_QWORD *)v25 + 64LL))(v25, 1);
LABEL_286:
                std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
                Windows::AutoReleasePtr<ActionList>::~AutoReleasePtr<ActionList>(v191);
                CUpdateEvaluator::~CUpdateEvaluator((CUpdateEvaluator *)&v199);
                std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(v194);
                CActionListCreator::~CActionListCreator((CActionListCreator *)v198);
                CDeviceInfo::~CDeviceInfo((CDeviceInfo *)v231);
                CCompositionDatabase::~CCompositionDatabase((CCompositionDatabase *)v232);
                return v96;
              }
              LogAdapter::TraceInfo<wchar_t const *>("Device: Edition version {0}", &v182);
            }
            CDeviceInfo::GetNameValuePairValue((CDeviceInfo *)v231, L"OSBaseVersion", (const wchar_t **)&v181, 0);
            LogAdapter::TraceInfo<wchar_t const *>("Device: Base version {0} (think RTM version)", &v181);
            if ( (v181 || (v181 = v182) != 0)
              && !std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::count<wchar_t *,WstringCaseInsensitiveCompare,0>(
                    v194,
                    &v181) )
            {
              std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::emplace<wchar_t * const &>(
                v194,
                v164,
                &v181);
            }
          }
          if ( v12 )
          {
            if ( *(_DWORD *)(v12 + 8) == 8 && *(_DWORD *)(v12 + 32) == 1 )
            {
              *(_QWORD *)v164 = 0;
              v98 = *(__int64 **)(v12 + 24);
              v186 = *v98;
              v99 = v98[1];
              std::wstring::wstring(&v171, L"SystemLanguage");
              CDeviceInfo::AddValuePair(v231, &v171, v99);
              std::wstring::~wstring(&v171);
              v158 = (int *)L"Microsoft";
              LOBYTE(v100) = 2;
              v101 = CDeviceInfo::AddInstalledFeature(v231, v100, v186, 0);
              v96 = v101;
              if ( v101 < 0 )
              {
                LODWORD(v180) = v101;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed adding feature: {0}",
                    &v186);
                  *(_QWORD *)v164 = &v180;
                  v158 = v164;
                  LOBYTE(v102) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    v102,
                    3,
                    ": {}");
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x65C,
                  (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
                  (const char *)v96,
                  (int)v158);
                if ( !v25 )
                  goto LABEL_286;
                goto LABEL_285;
              }
            }
          }
          v103 = CCompositionDatabase::PopulateCompositionDatabase(
                   (CCompositionDatabase *)v232,
                   (__int64)v194,
                   (__int64)v231,
                   (__int64)v188[0],
                   (__int64)v168);
          v96 = v103;
          if ( v103 < 0 )
          {
            LODWORD(v180) = v103;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                *(_QWORD *)&LogAdapter::g_Logger,
                0,
                3,
                "Failed to populate composition database.");
              *(_QWORD *)v164 = &v180;
              v159 = v164;
              LOBYTE(v104) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v104,
                3,
                ": {}");
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x669,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
              (const char *)v96,
              (int)v159);
            if ( !v25 )
              goto LABEL_286;
            goto LABEL_285;
          }
          v105 = CActionListCreator::AddAlternateSources(
                   (CActionListCreator *)v198,
                   (const struct CCompositionDatabase *)v232,
                   v183);
          v96 = v105;
          if ( v105 < 0 )
          {
            LODWORD(v180) = v105;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                *(_QWORD *)&LogAdapter::g_Logger,
                0,
                3,
                "Failed to populate composition database alternate payload sources");
              *(_QWORD *)v164 = &v180;
              v159 = v164;
              LOBYTE(v106) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v106,
                3,
                ": {}");
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x66D,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
              (const char *)v96,
              (int)v159);
            if ( !v25 )
              goto LABEL_286;
            goto LABEL_285;
          }
          if ( v81 )
          {
            v195 = 0;
            v196 = 0;
            v197 = 7;
            LOWORD(v195) = 0;
            if ( *(_DWORD *)(v76 + 16) )
            {
              v107 = *(_QWORD *)(*(_QWORD *)(v76 + 8) + 16LL);
              *(_QWORD *)v164 = v107;
              v108 = -1;
              do
                ++v108;
              while ( *(_WORD *)(v107 + 2 * v108) );
              v165 = v108;
              LOBYTE(v159) = 0;
              FinalPath = GetFinalPath(v164, &v195, 0, 1);
              v96 = FinalPath;
              if ( FinalPath < 0 )
              {
                LODWORD(v180) = FinalPath;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed getting the final path to the loaded CompDB folder");
                  *(_QWORD *)v164 = &v180;
                  v159 = v164;
                  LOBYTE(v110) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    v110,
                    3,
                    ": {}");
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x677,
                  (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
                  (const char *)v96,
                  (int)v159);
                std::wstring::~wstring(&v195);
                if ( !v25 )
                  goto LABEL_286;
                goto LABEL_285;
              }
              v111 = &v195;
              if ( v197 > 7 )
                v111 = (__int128 *)v195;
              *(_QWORD *)v164 = v111;
              v165 = (__int64)v196;
              Directory = GetDirectory(&v171, v164);
              std::wstring::operator=(&v195, Directory);
              std::wstring::~wstring(&v171);
            }
            v113 = CDeviceInfo::PopulateDeviceFeatureInformation(
                     (struct CDeviceInfo *)v231,
                     (struct CCompositionDatabase *)v232);
            v96 = v113;
            if ( v113 < 0 )
            {
              LODWORD(v180) = v113;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed to populate device feature information");
                *(_QWORD *)v164 = &v180;
                v159 = v164;
                LOBYTE(v114) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v114,
                  3,
                  ": {}");
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x684,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
                (const char *)v96,
                (int)v159);
              std::wstring::~wstring(&v195);
              if ( !v25 )
                goto LABEL_286;
              goto LABEL_285;
            }
            std::wstring::~wstring(&v195);
          }
          v115 = v193;
          v116 = CCompositionDatabase::MergeDeviceFeatureInformation(v232, v193, v231, v12);
          v96 = v116;
          if ( v116 < 0 )
          {
            LODWORD(v180) = v116;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                *(_QWORD *)&LogAdapter::g_Logger,
                0,
                3,
                "Failed to merge device feature information");
              *(_QWORD *)v164 = &v180;
              v159 = v164;
              LOBYTE(v118) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v118,
                3,
                ": {}");
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x688,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
              (const char *)v96,
              (int)v159);
            if ( !v25 )
              goto LABEL_286;
            goto LABEL_285;
          }
          if ( !v115 )
          {
            std::wstring::wstring(&v171, L"en-US");
            IsSatelliteValueInstalled = CDeviceInfo::IsSatelliteValueInstalled(v231, 0, &v171);
            std::wstring::~wstring(&v171);
            if ( !IsSatelliteValueInstalled )
            {
              LogAdapter::TraceInfo<>("Language 'en-US' not specified in device information; adding as a required system fallback language.");
              std::wstring::wstring(&v195, L"en-US");
              CDeviceInfo::AddSatelliteValue(v231, 0, &v195);
              std::wstring::~wstring(&v195);
            }
          }
          if ( v81 )
          {
            if ( v231[11] == v231[12] )
            {
              if ( v225.m128i_i32[0] == -1 )
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  (void *)0x52,
                  (unsigned int)"onecore\\base\\servicing\\arbiter\\inc\\CDeviceInfo.h",
                  v117);
              if ( v225.m128i_i32[0] == 1 )
              {
                v120 = (*(__int64 (__fastcall **)(struct IDeviceInfoGather *, _QWORD))(*(_QWORD *)v25 + 56LL))(v25, 0);
                v121 = PopulateDeviceRegistryConditionInformation(v120, v232, v231);
                v96 = v121;
                if ( v121 < 0 )
                {
                  v192 = v121;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      0,
                      3,
                      "Failed to populate device conditional information");
                    *(_QWORD *)v175 = &v192;
                    v159 = v175;
                    LOBYTE(v122) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      v122,
                      3,
                      ": {}");
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x6AC,
                    (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
                    (const char *)v96,
                    (int)v159);
                  if ( !v25 )
                    goto LABEL_286;
                  goto LABEL_285;
                }
              }
            }
            if ( v231[42] == v231[43] )
            {
              v123 = (*(__int64 (__fastcall **)(struct IDeviceInfoGather *, _QWORD))(*(_QWORD *)v25 + 56LL))(v25, 0);
              v124 = PopulateVelocityConditions(v123, v232, v231);
              v96 = v124;
              if ( v124 < 0 )
              {
                v193 = v124;
                if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed to populate device velocity information");
                  *(_QWORD *)v178 = &v193;
                  v159 = v178;
                  LOBYTE(v125) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    v125,
                    3,
                    ": {}");
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x6B4,
                  (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
                  (const char *)v96,
                  (int)v159);
                if ( !v25 )
                  goto LABEL_286;
                goto LABEL_285;
              }
            }
          }
          if ( !v115 && (v233 & 4) != 0 )
          {
            v126 = (_QWORD *)v231[8];
            v127 = v231[9];
            while ( v126 != (_QWORD *)v127 )
            {
              if ( (unsigned __int8)rtlex::strings_equal_i<wchar_t *,wchar_t [4]>(*v126 + 16LL, 0) )
                goto LABEL_298;
              ++v126;
            }
            LODWORD(v181) = -2147418113;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                *(_QWORD *)&LogAdapter::g_Logger,
                0,
                3,
                "DeviceDB does not contain OEM entries");
              *(_QWORD *)v164 = &v181;
              v159 = v164;
              LOBYTE(v128) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v128,
                3,
                ": {}");
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x6C7,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
              (const char *)0x8000FFFFLL,
              (int)v159);
            if ( v25 )
              (*(void (__fastcall **)(struct IDeviceInfoGather *, __int64))(*(_QWORD *)v25 + 64LL))(v25, 1);
            std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
            Windows::AutoReleasePtr<ActionList>::~AutoReleasePtr<ActionList>(v191);
            CUpdateEvaluator::~CUpdateEvaluator((CUpdateEvaluator *)&v199);
            std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(v194);
            CActionListCreator::~CActionListCreator((CActionListCreator *)v198);
            CDeviceInfo::~CDeviceInfo((CDeviceInfo *)v231);
            CCompositionDatabase::~CCompositionDatabase((CCompositionDatabase *)v232);
            return 2147549183LL;
          }
LABEL_298:
          if ( v12 && *(_DWORD *)(v12 + 8) == 15 && *(_DWORD *)(v12 + 56) == 5 )
          {
            v129 = -1;
            v130 = -1;
            do
              ++v130;
            while ( *(_WORD *)(*(_QWORD *)(v12 + 64) + 2 * v130) );
            *(_QWORD *)v164 = *(_QWORD *)(v12 + 64);
            v165 = v130;
            CDeviceInfo::MergeWithPrimaryInventory((CDeviceInfo *)v231);
          }
          else
          {
            v129 = -1;
          }
          v131 = v167;
          if ( !v167 )
          {
            if ( !v12 || *(_DWORD *)(v12 + 8) != 15 || (v152 = 1, *(_DWORD *)(v12 + 56) != 1) )
              v152 = 0;
            LODWORD(v163) = v152;
            v153 = CDeviceInfo::Save(v231, 0, &v222.m128i_u64[1], v185[0]);
            v154 = v153;
            if ( v153 < 0 )
            {
              LODWORD(v181) = v153;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed persisting CloudRecovery deviceInfo");
                *(_QWORD *)v164 = &v181;
                v163 = v164;
                LOBYTE(v155) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v155,
                  3,
                  ": {}");
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x769,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
                (const char *)v154,
                (int)v163);
              Windows::AutoNewPtr<IDeviceInfoGather>::~AutoNewPtr<IDeviceInfoGather>(&v169);
              std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
              Windows::AutoReleasePtr<ActionList>::~AutoReleasePtr<ActionList>(v191);
              CUpdateEvaluator::~CUpdateEvaluator((CUpdateEvaluator *)&v199);
              std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(v194);
              CActionListCreator::~CActionListCreator((CActionListCreator *)v198);
              CDeviceInfo::~CDeviceInfo((CDeviceInfo *)v231);
              CCompositionDatabase::~CCompositionDatabase((CCompositionDatabase *)v232);
              return v154;
            }
            goto LABEL_393;
          }
          v132 = SczAllocFromSz(&v170);
          AllFilesAndDirectories = v132;
          if ( v132 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x6D7,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
              (const char *)(unsigned int)v132,
              (int)v159);
            if ( v25 )
              (*(void (__fastcall **)(struct IDeviceInfoGather *, __int64))(*(_QWORD *)v25 + 64LL))(v25, 1);
            std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
            Windows::AutoReleasePtr<ActionList>::~AutoReleasePtr<ActionList>(v191);
            if ( !v170 )
              goto LABEL_380;
            goto LABEL_316;
          }
          v133 = SczEnsureBackslashTerminated(&v170);
          AllFilesAndDirectories = v133;
          if ( v133 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x6D8,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
              (const char *)(unsigned int)v133,
              (int)v159);
            Windows::AutoNewPtr<IDeviceInfoGather>::~AutoNewPtr<IDeviceInfoGather>(&v169);
            std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
            Windows::AutoReleasePtr<ActionList>::~AutoReleasePtr<ActionList>(v191);
            if ( !v170 )
              goto LABEL_380;
LABEL_316:
            operator delete((void *)(v170 - 8));
            goto LABEL_380;
          }
          v134 = SczAllocConcatSz(&v170, L"DeviceInventory.xml");
          AllFilesAndDirectories = v134;
          if ( v134 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x6D9,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
              (const char *)(unsigned int)v134,
              (int)v159);
            Windows::AutoNewPtr<IDeviceInfoGather>::~AutoNewPtr<IDeviceInfoGather>(&v169);
            std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
            Windows::AutoReleasePtr<ActionList>::~AutoReleasePtr<ActionList>(v191);
            if ( !v170 )
              goto LABEL_380;
            goto LABEL_316;
          }
          LODWORD(v160) = 0;
          v19 = v170;
          v135 = CDeviceInfo::Save(v231, 0, &v222.m128i_u64[1], v170);
          AllFilesAndDirectories = v135;
          if ( v135 < 0 )
          {
            LODWORD(v181) = v135;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                *(_QWORD *)&LogAdapter::g_Logger,
                0,
                3,
                "Failed persisting deviceInfo");
              *(_QWORD *)v164 = &v181;
              v160 = v164;
              LOBYTE(v136) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v136,
                3,
                ": {}");
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x6DC,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
              (const char *)AllFilesAndDirectories,
              (int)v160);
            Windows::AutoNewPtr<IDeviceInfoGather>::~AutoNewPtr<IDeviceInfoGather>(&v169);
            std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
            Windows::AutoReleasePtr<ActionList>::~AutoReleasePtr<ActionList>(v191);
            if ( !v19 )
              goto LABEL_380;
            goto LABEL_379;
          }
          AllFilesAndDirectories = CUpdateEvaluator::Initialize(&v199, v193, v12, v231);
          if ( (AllFilesAndDirectories & 0x80000000) != 0 )
          {
            LODWORD(v181) = AllFilesAndDirectories;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                *(_QWORD *)&LogAdapter::g_Logger,
                0,
                3,
                "Failed initializing update evaluator from device info");
              *(_QWORD *)v164 = &v181;
              v160 = v164;
              LOBYTE(v137) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v137,
                3,
                ": {}");
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x6DF,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
              (const char *)AllFilesAndDirectories,
              (int)v160);
            Windows::AutoNewPtr<IDeviceInfoGather>::~AutoNewPtr<IDeviceInfoGather>(&v169);
            std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
            Windows::AutoReleasePtr<ActionList>::~AutoReleasePtr<ActionList>(v191);
            if ( !v19 )
              goto LABEL_380;
            goto LABEL_379;
          }
          LODWORD(v161) = (_DWORD)v183;
          v138 = CUpdateEvaluator::PlanOperation(&v199, v12, v232, v198);
          AllFilesAndDirectories = v138;
          if ( v138 < 0 )
          {
            LODWORD(v181) = v138;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to plan operation");
              *(_QWORD *)v164 = &v181;
              v161 = v164;
              LOBYTE(v139) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v139,
                3,
                ": {}");
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x6F6,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
              (const char *)AllFilesAndDirectories,
              (int)v161);
            Windows::AutoNewPtr<IDeviceInfoGather>::~AutoNewPtr<IDeviceInfoGather>(&v169);
            std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
            Windows::AutoReleasePtr<ActionList>::~AutoReleasePtr<ActionList>(v191);
            if ( !v19 )
              goto LABEL_380;
            goto LABEL_379;
          }
          if ( BYTE3(v212) )
          {
            v140 = v205;
            if ( (v205 - 1 <= 1 || v205 - 22 <= 1) && v25 && !v177 )
            {
              if ( v205 == 1 )
              {
                v180 = 0;
                LODWORD(v181) = CDeviceInfo::GetNameValuePairValue(
                                  (CDeviceInfo *)v231,
                                  L"ServicingStackVersion",
                                  (const wchar_t **)&v180,
                                  0);
                if ( (int)v181 >= 0 )
                {
                  if ( v180 )
                  {
                    v167 = 0;
                    v143 = FileVersionFromString(v180, (char *)&v167 + 4, &v167);
                    AllFilesAndDirectories = v143;
                    if ( v143 < 0 )
                    {
                      LODWORD(v181) = v143;
                      if ( *(_QWORD *)&LogAdapter::g_Logger )
                      {
                        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                          *(_QWORD *)&LogAdapter::g_Logger,
                          0,
                          3,
                          "Failed to convert device installed SSU version:{0}",
                          &v180);
                        *(_QWORD *)v164 = &v181;
                        v161 = v164;
                        LOBYTE(v144) = 1;
                        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                          *(_QWORD *)&LogAdapter::g_Logger,
                          v144,
                          3,
                          ": {}");
                      }
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x71D,
                        (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
                        (const char *)AllFilesAndDirectories,
                        (int)v161);
                      Windows::AutoNewPtr<IDeviceInfoGather>::~AutoNewPtr<IDeviceInfoGather>(&v169);
                      std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
                      Windows::AutoReleasePtr<ActionList>::~AutoReleasePtr<ActionList>(v191);
                      if ( !v19 )
                        goto LABEL_380;
LABEL_379:
                      operator delete((void *)(v19 - 8));
                      goto LABEL_380;
                    }
                    if ( HIDWORD(v167) == 655360 && WORD1(v167) == 22621 && (unsigned __int16)v167 <= 0x1095u )
                    {
                      LogAdapter::TraceInfo<wchar_t const *>(
                        "Disabling scavenge because the required SSU version is not installed, installed SSU version: {1}",
                        &v180);
                      goto LABEL_355;
                    }
                  }
                }
                else if ( *(_QWORD *)&LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    0,
                    1,
                    "Failed to get installed servicing stack version");
                  *(_QWORD *)v164 = &v181;
                  LOBYTE(v141) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    *(_QWORD *)&LogAdapter::g_Logger,
                    v141,
                    1,
                    ": {0}");
                }
                v140 = v205;
              }
              v169 = 0;
              (*(void (__fastcall **)(struct IDeviceInfoGather *, __int64, __int64))(*(_QWORD *)v25 + 64LL))(
                v25,
                1,
                v140);
              LODWORD(v181) = PrepareDesktopUpdateOperation(v189, v187, v205);
              if ( (int)v181 < 0 && *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  1,
                  "Not able to ask servicing stack to clean up disk space, ignore");
                *(_QWORD *)v164 = &v181;
                LOBYTE(v142) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v142,
                  1,
                  ": {0}");
              }
            }
          }
LABEL_355:
          *(_QWORD *)v164 = *v131;
          *v131 = 0;
          Windows::AutoReleasePtr<ActionList>::~AutoReleasePtr<ActionList>(v164);
          LODWORD(v162) = (_DWORD)v174;
          v145 = CActionListCreator::CreateActionList(v198, v193, v232, v184[0]);
          AllFilesAndDirectories = v145;
          if ( v145 < 0 )
          {
            LODWORD(v181) = v145;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed creating actionlist");
              *(_QWORD *)v164 = &v181;
              v162 = v164;
              LOBYTE(v146) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v146,
                3,
                ": {}");
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x743,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
              (const char *)AllFilesAndDirectories,
              (int)v162);
            Windows::AutoNewPtr<IDeviceInfoGather>::~AutoNewPtr<IDeviceInfoGather>(&v169);
            std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
            Windows::AutoReleasePtr<ActionList>::~AutoReleasePtr<ActionList>(v191);
            if ( !v19 )
              goto LABEL_380;
            goto LABEL_379;
          }
          LogAdapter::TraceInfo<wchar_t const *>("arbiter: ActionList created: {0}", v184);
          v147 = L"true";
          if ( !*((_QWORD *)*v131 + 10) )
            v147 = L"false";
          *(_QWORD *)v164 = v147;
          LogAdapter::TraceInfo<wchar_t const *>("  Media: {0}", v164);
          LogAdapter::TraceInfo<unsigned long>("  Feature Enumerations: {0}", (char *)*v131 + 208);
          LogAdapter::TraceInfo<unsigned long>("  Feature Installs: {0}", (char *)*v131 + 128);
          LogAdapter::TraceInfo<unsigned long>("  Feature Removals: {0}", (char *)*v131 + 144);
          LogAdapter::TraceInfo<unsigned long>("  Downloads: {0}", (char *)*v131 + 72);
          LogAdapter::TraceInfo<unsigned long>("  Package Installations: {0}", (char *)*v131 + 96);
          LogAdapter::TraceInfo<unsigned long>("  Package Removals: {0}", (char *)*v131 + 112);
          LogAdapter::TraceInfo<unsigned long>("  Product Updates: {0}", (char *)*v131 + 224);
          if ( v12 && *(_DWORD *)(v12 + 8) == 15 && *(_DWORD *)(v12 + 56) == 5 )
          {
            v167 = 0;
            v148 = SczAllocFromSz(&v167);
            AllFilesAndDirectories = v148;
            if ( v148 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x752,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
                (const char *)(unsigned int)v148,
                (int)v162);
              if ( v167 )
                operator delete(v167 - 1);
              Windows::AutoNewPtr<IDeviceInfoGather>::~AutoNewPtr<IDeviceInfoGather>(&v169);
              std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
              Windows::AutoReleasePtr<ActionList>::~AutoReleasePtr<ActionList>(v191);
              if ( !v19 )
                goto LABEL_380;
              goto LABEL_379;
            }
            v149 = SczEnsureBackslashTerminated(&v167);
            AllFilesAndDirectories = v149;
            if ( v149 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x753,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
                (const char *)(unsigned int)v149,
                (int)v162);
              if ( v167 )
                operator delete(v167 - 1);
              Windows::AutoNewPtr<IDeviceInfoGather>::~AutoNewPtr<IDeviceInfoGather>(&v169);
              std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
              Windows::AutoReleasePtr<ActionList>::~AutoReleasePtr<ActionList>(v191);
              if ( !v19 )
                goto LABEL_380;
              goto LABEL_379;
            }
            v150 = SczAllocConcatSz(&v167, L"PlannedDeviceInventory.PBR.xml");
            AllFilesAndDirectories = v150;
            if ( v150 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x754,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
                (const char *)(unsigned int)v150,
                (int)v162);
              if ( v167 )
                operator delete(v167 - 1);
              Windows::AutoNewPtr<IDeviceInfoGather>::~AutoNewPtr<IDeviceInfoGather>(&v169);
              std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
              Windows::AutoReleasePtr<ActionList>::~AutoReleasePtr<ActionList>(v191);
              if ( !v19 )
                goto LABEL_380;
              goto LABEL_379;
            }
            v151 = v167;
            do
              ++v129;
            while ( *((_WORD *)v167 + v129) );
            *(_QWORD *)v164 = v167;
            v165 = v129;
            GeneratePlannedCloudRecoveryInventory(
              0,
              (unsigned int)&v222.m128i_u32[2],
              (unsigned int)*v131,
              (unsigned int)v231,
              (__int64)v164);
            if ( v151 )
              operator delete(v151 - 1);
          }
LABEL_393:
          Windows::AutoNewPtr<IDeviceInfoGather>::~AutoNewPtr<IDeviceInfoGather>(&v169);
          std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
          Windows::AutoReleasePtr<ActionList>::~AutoReleasePtr<ActionList>(v191);
          if ( v19 )
            operator delete((void *)(v19 - 8));
          goto LABEL_134;
        }
LABEL_69:
        LODWORD(v180) = -2147024809;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Invalid module operation");
          *(_QWORD *)v175 = &v180;
          v156 = v175;
          LOBYTE(v49) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v49,
            3,
            ": {}");
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x52E,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
          (const char *)0x80070057LL,
          (int)v156);
        std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(v168);
        if ( !*(_QWORD *)v191 )
          goto LABEL_73;
LABEL_72:
        (***(void (__fastcall ****)(_QWORD))v191)(*(_QWORD *)v191);
        *(_QWORD *)v191 = 0;
LABEL_73:
        CUpdateEvaluator::~CUpdateEvaluator((CUpdateEvaluator *)&v199);
        std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(v194);
        CActionListCreator::~CActionListCreator((CActionListCreator *)v198);
        CDeviceInfo::~CDeviceInfo((CDeviceInfo *)v231);
        CCompositionDatabase::~CCompositionDatabase((CCompositionDatabase *)v232);
        return 2147942487LL;
      case 5:
        if ( v41 )
          LogAdapter::TraceInfo<>("Some Device state will come from input file for this scenario");
        else
          LogAdapter::TraceInfo<>("Some device state will be collected and used from current device for this scenario");
        v48 = *(_QWORD *)(v12 + 64) == 0;
        goto LABEL_68;
      default:
        goto LABEL_69;
    }
    if ( v41 )
      goto LABEL_69;
    goto LABEL_56;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x76E,
                           (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
                           v50);
  }
  return result;
}

```

## disassembly

```asm
0x180069378  mov     r11, rsp
0x18006937b  push    rdi
0x18006937c  push    r12
0x18006937e  push    r13
0x180069380  push    r14
0x180069382  push    r15
0x180069384  sub     rsp, 6E0h
0x18006938b  mov     qword ptr [r11-638h], 0FFFFFFFFFFFFFFFEh
0x180069396  mov     [r11+8], rbx
0x18006939a  mov     [r11+20h], rsi
0x18006939e  mov     rax, cs:__security_cookie
0x1800693a5  xor     rax, rsp
0x1800693a8  mov     [rsp+708h+var_38], rax
0x1800693b0  mov     r12, r8
0x1800693b3  mov     [rsp+708h+var_5E8], r8
0x1800693bb  mov     esi, edx
0x1800693bd  mov     [rsp+708h+var_59C], edx
0x1800693c4  mov     r14, [rsp+708h+arg_38]
0x1800693cc  mov     [rsp+708h+var_650], r14
0x1800693d4  mov     rax, [rsp+708h+arg_20]
0x1800693dc  mov     [r11-610h], rax
0x1800693e3  mov     [r11-5E0h], r14
0x1800693ea  mov     rax, [rsp+708h+arg_48]
0x1800693f2  mov     [r11-608h], rax
0x1800693f9  mov     rax, [rsp+708h+arg_50]
0x180069401  mov     [rsp+708h+var_668], rax
0x180069409  mov     r15, [rsp+708h+arg_58]
0x180069411  mov     [rsp+708h+var_6B0], r15
0x180069416  xor     r13d, r13d
0x180069419  mov     [r11-5F8h], r13
0x180069420  mov     [r11-5C8h], r13
0x180069427  mov     [r11-5B8h], r13
0x18006942e  test    r15, r15
0x180069431  jz      short loc_180069436
0x180069433  mov     [r15], r13
0x180069436  lea     rcx, [rsp+708h+var_258]; this
0x18006943e  call    ??0CCompositionDatabase@@QEAA@XZ; CCompositionDatabase::CCompositionDatabase(void)
0x180069443  nop
0x180069444  lea     rcx, [rsp+708h+var_3C8]; this
0x18006944c  call    ??0CDeviceInfo@@QEAA@XZ; CDeviceInfo::CDeviceInfo(void)
0x180069451  nop
0x180069452  lea     rcx, [rsp+708h+var_568]
0x18006945a  call    ??0CActionListCreator@@QEAA@W4CreateActionListFlags@@@Z; CActionListCreator::CActionListCreator(CreateActionListFlags)
0x18006945f  nop
0x180069460  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffff00000000
0x180069468  movdqa  [rsp+708h+var_458], xmm0
0x180069471  movdqa  xmm1, cs:__xmm@ffffffff0000000000000000ffffffff
0x180069479  movdqa  [rsp+708h+var_448], xmm1
0x180069482  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18006948a  movdqa  [rsp+708h+var_438], xmm0
0x180069493  movdqa  [rsp+708h+var_428], xmm0
0x18006949c  movdqa  [rsp+708h+var_418], xmm0
0x1800694a5  movdqa  [rsp+708h+var_408], xmm0
0x1800694ae  movdqa  [rsp+708h+var_3F8], xmm0
0x1800694b7  movdqa  [rsp+708h+var_3E8], xmm0
0x1800694c0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800694c4  mov     [rsp+708h+var_3D8], ebx
0x1800694cb  mov     [rsp+708h+var_3D4], r13d
0x1800694d3  mov     [rsp+708h+var_598], r13
0x1800694db  mov     [rsp+708h+var_590], r13
0x1800694e3  lea     edi, [rbx+41h]
0x1800694e6  mov     ecx, edi; Size
0x1800694e8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800694ed  mov     [rax], rax
0x1800694f0  mov     [rax+8], rax
0x1800694f4  mov     [rax+10h], rax
0x1800694f8  mov     word ptr [rax+18h], 101h
0x1800694fe  mov     [rsp+708h+var_598], rax
0x180069506  mov     [rsp+708h+var_518], r13d
0x18006950e  mov     [rsp+708h+var_508], r13
0x180069516  lea     rax, ??_7PrivateHeapPool@Rtl@Windows@@6B@; const Windows::Rtl::PrivateHeapPool::`vftable'
0x18006951d  mov     [rsp+708h+var_510], rax
0x180069525  mov     [rsp+708h+var_500], r13
0x18006952d  mov     [rsp+708h+var_4F8], r13
0x180069535  mov     [rsp+708h+var_4F0], r13
0x18006953d  lea     ecx, [rbx+29h]; Size
0x180069540  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180069545  mov     [rax], rax
0x180069548  mov     [rax+8], rax
0x18006954c  mov     [rax+10h], rax
0x180069550  mov     word ptr [rax+18h], 101h
0x180069556  mov     [rsp+708h+var_4F8], rax
0x18006955e  mov     [rsp+708h+var_4E8], r13d
0x180069566  mov     [rsp+708h+var_4E0], r13
0x18006956e  mov     [rsp+708h+var_4D8], r13
0x180069576  mov     [rsp+708h+var_4D0], r13
0x18006957e  mov     ecx, edi; Size
0x180069580  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180069585  mov     [rax], rax
0x180069588  mov     [rax+8], rax
0x18006958c  mov     [rax+10h], rax
0x180069590  mov     word ptr [rax+18h], 101h
0x180069596  mov     [rsp+708h+var_4D8], rax
0x18006959e  mov     [rsp+708h+var_4C8], r13
0x1800695a6  mov     [rsp+708h+var_4C0], r13
0x1800695ae  mov     ecx, edi; Size
0x1800695b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800695b5  mov     [rax], rax
0x1800695b8  mov     [rax+8], rax
0x1800695bc  mov     [rax+10h], rax
0x1800695c0  mov     word ptr [rax+18h], 101h
0x1800695c6  mov     [rsp+708h+var_4C8], rax
0x1800695ce  xorps   xmm0, xmm0
0x1800695d1  movdqa  [rsp+708h+var_4B8], xmm0
0x1800695da  mov     [rsp+708h+var_4A8], r13
0x1800695e2  mov     [rsp+708h+var_4A0], r13w
0x1800695eb  mov     [rsp+708h+var_49E], r13b
0x1800695f3  movdqa  [rsp+708h+var_498], xmm0
0x1800695fc  mov     [rsp+708h+var_488], r13
0x180069604  mov     [rsp+708h+var_480], r13
0x18006960c  mov     [rsp+708h+var_478], r13
0x180069614  mov     [rsp+708h+var_470], r13
0x18006961c  mov     [rsp+708h+var_468], r13b
0x180069624  mov     [rsp+708h+var_630], r13
0x18006962c  mov     rdi, r13
0x18006962f  mov     [rsp+708h+var_690], r13
0x180069634  mov     qword ptr [rsp+708h+var_5A8], r13
0x18006963c  mov     [rsp+708h+var_5D8], r13
0x180069644  mov     [rsp+708h+var_6A8], r13
0x180069649  mov     [rsp+708h+var_6A0], r13
0x18006964e  mov     ecx, 88h; Size
0x180069653  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180069658  mov     [rax], rax
0x18006965b  mov     [rax+8], rax
0x18006965f  mov     [rax+10h], rax
0x180069663  mov     word ptr [rax+18h], 101h
0x180069669  mov     [rsp+708h+var_6A8], rax
0x18006966e  test    r14, r14
0x180069671  jz      short loc_180069690
0x180069673  lea     rax, aOffline; "offline"
0x18006967a  mov     qword ptr [rsp+708h+var_660], rax
0x180069682  mov     [rsp+708h+var_658], 7
0x18006968e  jmp     short loc_1800696A5
0x180069690  lea     rax, aOnline; "online"
0x180069697  mov     qword ptr [rsp+708h+var_6C8], rax
0x18006969c  mov     [rsp+708h+var_6C0], 6
0x1800696a5  lea     rax, [rsp+708h+var_6C8]
0x1800696aa  lea     rcx, [rsp+708h+var_660]
0x1800696b2  test    r14, r14
0x1800696b5  cmovnz  rax, rcx
0x1800696b9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800696c0  test    rcx, rcx
0x1800696c3  jz      short loc_1800696CF
0x1800696c5  mov     [rsp+708h+var_6E8], rax
0x1800696ca  call    ??$LogNumObjects@V?$basic_string_view@DU?$char_traits@D@std@@@std@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z; LogAdapter::Logger::LogNumObjects<std::string_view>(bool,LogAdapter::LogLevel,char const * const,std::string_view const &)
0x1800696cf  mov     r14, r13
0x1800696d2  mov     [rsp+708h+var_698], r13
0x1800696d7  xor     eax, eax
0x1800696d9  cmp     [rsp+708h+var_650], rax
0x1800696e1  setnz   r13b
0x1800696e5  test    esi, esi
0x1800696e7  jnz     loc_18006990B
0x1800696ed  xorps   xmm0, xmm0
0x1800696f0  movdqu  [rsp+708h+var_588], xmm0
0x1800696f9  mov     [rsp+708h+var_578], rax
0x180069701  xor     r8d, r8d
0x180069704  lea     rdx, word_1801DA40A
0x18006970b  lea     rcx, aDbXmlCab; "*DB*.xml.cab"
0x180069712  call    __std_find_trivial_2
0x180069717  lea     rcx, word_1801DA40A
0x18006971e  cmp     rax, rcx
0x180069721  jz      loc_18006CD0D
0x180069727  lea     rcx, aDbXmlCab; "*DB*.xml.cab"
0x18006972e  sub     rax, rcx
0x180069731  sar     rax, 1
0x180069734  cmp     rax, rbx
0x180069737  jz      loc_18006CD0D
0x18006973d  mov     qword ptr [rsp+708h+var_6C8], rcx
0x180069742  mov     [rsp+708h+var_6C0], rax
0x180069747  mov     rdx, [rsp+708h+var_610]
0x18006974f  xorps   xmm0, xmm0
0x180069752  movups  [rsp+708h+var_688], xmm0
0x18006975a  xor     eax, eax
0x18006975c  mov     [rsp+708h+var_678], rax
0x180069764  mov     [rsp+708h+var_670], rax
0x18006976c  mov     r8, rbx
0x18006976f  inc     r8
0x180069772  cmp     [rdx+r8*2], ax
0x180069777  jnz     short loc_18006976F
0x180069779  lea     rcx, [rsp+708h+var_688]
0x180069781  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180069786  nop
0x180069787  mov     rcx, [rsp+708h+var_678]
0x18006978f  lea     rax, [rsp+708h+var_688]
0x180069797  cmp     [rsp+708h+var_670], 7
0x1800697a0  cmova   rax, qword ptr [rsp+708h+var_688]
0x1800697a9  mov     qword ptr [rsp+708h+var_660], rax
0x1800697b1  mov     [rsp+708h+var_658], rcx
0x1800697b9  mov     [rsp+708h+var_6E8], 0
0x1800697c2  lea     r9, [rsp+708h+var_588]
0x1800697ca  xor     r8d, r8d
0x1800697cd  lea     rdx, [rsp+708h+var_6C8]
0x1800697d2  lea     rcx, [rsp+708h+var_660]
0x1800697da  call    ?GetAllFilesAndDirectories@@YAJAEBV?$basic_zstring_view@_W@wil@@0HPEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@1@Z; GetAllFilesAndDirectories(wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &,int,std::vector<std::wstring> *,std::vector<std::wstring> *)
0x1800697df  mov     ebx, eax
0x1800697e1  lea     rcx, [rsp+708h+var_688]; void *
0x1800697e9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800697ee  test    ebx, ebx
0x1800697f0  jns     loc_1800698E8
0x1800697f6  mov     [rsp+708h+var_5A0], ebx
0x1800697fd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180069804  xor     edi, edi
0x180069806  test    rcx, rcx
0x180069809  jz      short loc_180069863
0x18006980b  lea     rax, [rsp+708h+var_610]
0x180069813  mov     [rsp+708h+var_6E8], rax
0x180069818  lea     r9, aFailedWhileTry; "Failed while trying to find compDB cabs"...
0x18006981f  lea     r15d, [rdi+3]
0x180069823  mov     r8d, r15d
0x180069826  xor     edx, edx
0x180069828  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18006982d  lea     rax, [rsp+708h+var_5A0]
0x180069835  mov     [rsp+708h+var_668], rax
0x18006983d  lea     rax, [rsp+708h+var_668]
0x180069845  mov     [rsp+708h+var_6E8], rax
0x18006984a  lea     r9, asc_1801CAFB4; ": {}"
0x180069851  mov     r8d, r15d
0x180069854  mov     dl, 1
0x180069856  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18006985d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180069862  nop
0x180069863  lea     rcx, [rsp+708h+var_588]
0x18006986b  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180069870  nop
0x180069871  lea     rcx, [rsp+708h+var_6A8]
0x180069876  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UBuildLayer@CDeviceInfo@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UBuildLayer@CDeviceInfo@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDeviceInfo::BuildLayer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDeviceInfo::BuildLayer>>,0>>(void)
0x18006987b  nop
0x18006987c  mov     rcx, qword ptr [rsp+708h+var_5A8]
0x180069884  test    rcx, rcx
0x180069887  jz      short loc_18006989C
0x180069889  mov     rax, [rcx]
0x18006988c  mov     rax, [rax]
0x18006988f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069894  mov     qword ptr [rsp+708h+var_5A8], rdi
0x18006989c  lea     rcx, [rsp+708h+var_518]; this
0x1800698a4  call    ??1CUpdateEvaluator@@QEAA@XZ; CUpdateEvaluator::~CUpdateEvaluator(void)
0x1800698a9  nop
0x1800698aa  lea     rcx, [rsp+708h+var_598]
0x1800698b2  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UWstringCaseInsensitiveCompare@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(void)
0x1800698b7  nop
0x1800698b8  lea     rcx, [rsp+708h+var_568]; this
0x1800698c0  call    ??1CActionListCreator@@QEAA@XZ; CActionListCreator::~CActionListCreator(void)
0x1800698c5  nop
0x1800698c6  lea     rcx, [rsp+708h+var_3C8]; this
0x1800698ce  call    ??1CDeviceInfo@@QEAA@XZ; CDeviceInfo::~CDeviceInfo(void)
0x1800698d3  nop
0x1800698d4  lea     rcx, [rsp+708h+var_258]; this
0x1800698dc  call    ??1CCompositionDatabase@@QEAA@XZ; CCompositionDatabase::~CCompositionDatabase(void)
0x1800698e1  mov     eax, ebx
0x1800698e3  jmp     loc_18006CCDF
0x1800698e8  mov     rax, qword ptr [rsp+708h+var_588+8]
0x1800698f0  cmp     qword ptr [rsp+708h+var_588], rax
0x1800698f8  jnz     short loc_1800698FE
0x1800698fa  or      r13d, 2
0x1800698fe  lea     rcx, [rsp+708h+var_588]
0x180069906  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18006990b  lea     rdx, [rsp+708h+var_610]
0x180069913  lea     rcx, aArbiterCreatea; "arbiter: --- CreateActionList begin: Sa"...
0x18006991a  call    ??$TraceInfo@PEB_W@LogAdapter@@YAXQEBDAEBQEB_W@Z; LogAdapter::TraceInfo<wchar_t const *>(char const * const,wchar_t const * const &)
0x18006991f  mov     ecx, esi
0x180069921  xor     esi, esi
0x180069923  test    ecx, ecx
0x180069925  jz      short loc_18006994E
0x180069927  cmp     ecx, 1
0x18006992a  jz      short loc_18006993D
0x18006992c  movups  xmm0, cs:??$LiteralObject@$2U?$BaseLiteralBuffer@$0BE@U_LUNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0FF@@0GO@@0GL@@0GO@@0GP@@0HH@@0GO@@0CA@@0GE@@0GF@@0HG@@0GJ@@0GD@@0GF@@0CA@@0HE@@0HJ@@0HA@@0GF@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@$0N@$0O@$0P@$0BA@$0BB@$0BC@$0BD@@Details@RtlStringLiterals@@3U_LUNICODE_STRING@@B
0x180069933  movsd   xmm1, cs:off_1801C42B0; "Unknown device type"
0x18006993b  jmp     short loc_18006995D
0x18006993d  movups  xmm0, cs:??$LiteralObject@$2U?$BaseLiteralBuffer@$07U_LUNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0EE@@0GF@@0HD@@0GL@@0HE@@0GP@@0HA@@0A@@@@$0A@$00$01$02$03$04$05$06@Details@RtlStringLiterals@@3U_LUNICODE_STRING@@B
0x180069944  movsd   xmm1, cs:off_1801C4298; "Desktop"
0x18006994c  jmp     short loc_18006995D
0x18006994e  movups  xmm0, cs:??$LiteralObject@$2U?$BaseLiteralBuffer@$06U_LUNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0EN@@0GP@@0GC@@0GJ@@0GM@@0GF@@0A@@@@$0A@$00$01$02$03$04$05@Details@RtlStringLiterals@@3U_LUNICODE_STRING@@B
0x180069955  movsd   xmm1, cs:off_1801C42C8; "Mobile"
0x18006995d  movups  [rsp+708h+var_588], xmm0
0x180069965  movsd   [rsp+708h+var_578], xmm1
0x18006996e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180069975  test    rcx, rcx
0x180069978  jz      short loc_18006999C
0x18006997a  lea     rax, [rsp+708h+var_588]
0x180069982  mov     [rsp+708h+var_6E8], rax
0x180069987  lea     r9, aDeviceType0; "  Device type: {0}"
0x18006998e  mov     r8d, 1
0x180069994  mov     dl, r8b
0x180069997  call    ??$LogNumObjects@U_LUNICODE_STRING@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU_LUNICODE_STRING@@@Z; LogAdapter::Logger::LogNumObjects<_LUNICODE_STRING>(bool,LogAdapter::LogLevel,char const * const,_LUNICODE_STRING const &)
0x18006999c  xorps   xmm0, xmm0
0x18006999f  movups  [rsp+708h+var_588], xmm0
0x1800699a7  mov     [rsp+708h+var_578], rsi
0x1800699af  mov     [rsp+708h+var_570], 7
0x1800699bb  mov     word ptr [rsp+708h+var_588], si
0x1800699c3  movups  [rsp+708h+var_688], xmm0
0x1800699cb  mov     [rsp+708h+var_678], rsi
0x1800699d3  mov     [rsp+708h+var_670], rsi
0x1800699db  mov     r8d, 4
0x1800699e1  lea     rdx, aNone_0; "None"
0x1800699e8  lea     rcx, [rsp+708h+var_688]
0x1800699f0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800699f5  nop
0x1800699f6  lea     rcx, [rsp+708h+var_588]; void *
0x1800699fe  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180069a03  nop
  ... truncated ...
```
