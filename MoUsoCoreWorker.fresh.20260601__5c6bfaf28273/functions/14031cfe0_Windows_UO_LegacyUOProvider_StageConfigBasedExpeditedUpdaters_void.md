# Windows::UO::LegacyUOProvider::StageConfigBasedExpeditedUpdaters(void)

- ea: `0x14031cfe0`
- end: `0x14031f668`
- name: `?StageConfigBasedExpeditedUpdaters@LegacyUOProvider@UO@Windows@@AEAAXXZ`
- size: `9864`
- prototype: `void __fastcall(Windows::UO::LegacyUOProvider *__hidden this)`
- caller_count: `1`
- callee_count: `56`
- tags: `reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140318e30`

## callees

- `0x140024de0`
- `0x140028c4c`
- `0x140036d60`
- `0x140040184`
- `0x140041b3c`
- `0x14004296c`
- `0x140042d04`
- `0x140043284`
- `0x140043354`
- `0x140043814`
- `0x1400447ac`
- `0x140044b18`
- `0x140045404`
- `0x140045700`
- `0x14004616c`
- `0x140047670`
- `0x140048fc4`
- `0x140049be0`
- `0x14004afa0`
- `0x14004f25c`
- `0x140057a20`
- `0x1400a3d80`
- `0x1400a3f0c`
- `0x1400a52e4`
- `0x1400a5368`
- `0x1400a6784`
- `0x1400a778c`
- `0x1400c75e4`
- `0x1400fcc10`
- `0x140117ae0`
- `0x140117b78`
- `0x14011850c`
- `0x140118c84`
- `0x14012a810`
- `0x14012d7d8`
- `0x140150d4c`
- `0x140150f10`
- `0x140150f78`
- `0x14018c370`
- `0x1401a6414`
- `0x1401a6588`
- `0x140313168`
- `0x1403140f4`
- `0x140318858`
- `0x14031cd6c`
- `0x14031cfe0`
- `0x14031f670`
- `0x140321d30`
- `0x140323228`
- `0x140324948`

## string_xrefs

- `0x14031f5b9`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14031f5d3`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14031f627`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14031f641`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14031f612`: `directory_entry::status`
- `0x14031d649`: `UpdaterName`
- `0x14031eb5f`: `UpdaterName`
- `0x14031d2d2`: `Found duplicate/unknown keys in Expedited JSON`
- `0x14031d2e7`: `Found duplicate/unknown keys in Expedited JSON`
- `0x14031e825`: `Found duplicate/unknown keys in Expedited JSON`
- `0x14031da99`: `updaterRegistrationVersion`
- `0x14031ded9`: `updaterRegistrationVersion`
- `0x14031f0c9`: `updaterRegistrationVersion`
- `0x14031dc2f`: `Registration version for updater {} is less than or equal to the existing registration version. Skipping registration.`
- `0x14031e22c`: `Searching for Config-based expedited updaters from: {}`
- `0x14031f576`: `Config-based expedited updaters registration path does not exist or is not a directory`
- `0x14031e353`: `.json`
- `0x14031e740`: `.json`
- `0x14031eb2b`: `.json`
- `0x14031ee99`: `.json`
- `0x14031f31a`: `.json`
- `0x14031f452`: `.json`
- `0x14031e5c4`: `Failed to open file`
- `0x14031edc1`: `Updater already exists: {}`
- `0x14031f65b`: `recursive_directory_iterator::operator++`

## pseudocode

```c
// Hidden C++ exception states: #wind=100 #try_helpers=1
void __fastcall Windows::UO::LegacyUOProvider::StageConfigBasedExpeditedUpdaters(Windows::UO::LegacyUOProvider *this)
{
  Windows::UO::LegacyUOProvider *v1; // r14
  int v2; // r15d
  __int64 System; // rax
  __int64 v4; // rcx
  void (__fastcall *v5)(__int64, _BYTE *, __int128 *); // rbx
  __int64 *traits_2_unsigned_short; // rax
  const char *v7; // r9
  __int64 v8; // r11
  __int64 v9; // rax
  volatile signed __int32 *v10; // rbx
  volatile signed __int32 *v11; // rbx
  char v12; // al
  _QWORD *v13; // rax
  __int64 v14; // rax
  _QWORD *i; // rbx
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // r14
  void (__fastcall *v20)(__int64, __int128 *, __int128 *); // r12
  __int64 v21; // rax
  const char *v22; // r9
  __int64 v23; // r11
  __int64 v24; // rax
  __int128 *v25; // rdx
  volatile signed __int32 *v26; // r14
  volatile signed __int32 *v27; // r14
  __int64 *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // r14
  void (__fastcall *v34)(__int64, __int128 *); // r12
  __int128 *v35; // rdx
  const char *v36; // r9
  volatile signed __int32 *v37; // r14
  volatile signed __int32 *v38; // r14
  _QWORD *v39; // rax
  _QWORD *v40; // rax
  _QWORD *v41; // rax
  __int64 v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rax
  __int64 v45; // r14
  __int64 (__fastcall *v46)(__int64, __int128 *, __int128 *); // r12
  __int64 v47; // rax
  __int64 v48; // rax
  __int128 *v49; // rax
  __int64 v50; // rdx
  char v51; // r12
  volatile signed __int32 *v52; // r14
  volatile signed __int32 *v53; // r14
  __int64 v54; // rax
  __int64 v55; // rcx
  __int64 v56; // rax
  __int64 v57; // r14
  void (__fastcall *v58)(__int64, _QWORD *, __int128 *, __int128 *, __int128 *); // r12
  __int128 v59; // xmm6
  __int64 v60; // rax
  _QWORD *v61; // rax
  __int64 v62; // rcx
  __int64 v63; // rax
  _QWORD *v64; // rax
  __int64 v65; // r9
  __int64 v66; // rax
  __int64 v67; // rcx
  __int64 v68; // rax
  __int64 v69; // rcx
  void (__fastcall *v70)(__int64, __int128 *, __int128 *); // r9
  _QWORD *v71; // rax
  _QWORD *v72; // rdx
  __int64 v73; // rax
  __int64 v74; // rcx
  __int64 v75; // rax
  __int64 v76; // r14
  void (__fastcall *v77)(__int64, __int128 *, __int128 *, __int128 *, _QWORD *); // r12
  __int128 v78; // xmm6
  __int64 v79; // rax
  _QWORD *v80; // rax
  __int64 v81; // rcx
  __int64 v82; // rax
  __int64 v83; // rax
  _QWORD *v84; // rax
  const char *v85; // r9
  int v86; // r15d
  struct std::error_code *v87; // r8
  bool v88; // al
  const struct std::filesystem::path *v89; // rdx
  const struct std::filesystem::path *v90; // r9
  __int64 v91; // rax
  __int128 v92; // xmm1
  _QWORD *v93; // rbx
  int *v94; // rax
  const char *v95; // r9
  __int64 v96; // rax
  _QWORD *v97; // rcx
  __int128 *v98; // rax
  char v99; // r14
  _QWORD *v100; // r12
  __int64 v101; // rax
  __int64 v102; // rcx
  __int64 v103; // rax
  __int64 v104; // rbx
  void (__fastcall *v105)(__int64, __int128 *, __int128 *); // r14
  wchar_t *v106; // rax
  const char *v107; // r9
  __int64 v108; // r11
  __int64 v109; // rax
  __int128 *v110; // rdx
  volatile signed __int32 *v111; // rbx
  volatile signed __int32 *v112; // rbx
  __int64 v113; // rax
  __int64 v114; // rax
  __int64 v115; // rcx
  __int64 v116; // rax
  __int64 v117; // rbx
  void (__fastcall *v118)(__int64, __int128 *, __int128 *); // r14
  __int128 v119; // xmm6
  _QWORD *v120; // rax
  __int64 v121; // rcx
  __int64 *v122; // rax
  __int64 v123; // rdx
  int v124; // r15d
  __int64 v125; // rax
  __int64 v126; // rcx
  __int64 v127; // rax
  __int64 v128; // rbx
  void (__fastcall *v129)(__int64, __int128 *); // r14
  __int128 *v130; // rdx
  _QWORD *v131; // rax
  _QWORD *v132; // rax
  __int64 v133; // rax
  __int64 v134; // rcx
  __int64 v135; // rax
  __int64 v136; // rbx
  __int64 (__fastcall *v137)(__int64, __int128 *, __int128 *); // r14
  __int64 v138; // rax
  _QWORD *v139; // rax
  __int64 v140; // rcx
  __int64 v141; // rdx
  char v142; // bl
  __int128 *v143; // rax
  Windows::UO::LegacyUOProvider *v144; // rbx
  __int64 v145; // rax
  __int64 v146; // rcx
  __int64 v147; // rax
  __int64 v148; // rcx
  void (__fastcall *v149)(__int64, __int128 *, __int128 *); // r9
  _QWORD *v150; // rax
  __int128 *v151; // rdx
  _QWORD *v152; // rax
  int v153; // ebx
  __int64 v154; // rax
  __int64 v155; // rcx
  __int64 v156; // rax
  __int64 v157; // r14
  void (__fastcall *v158)(__int64, __int128 *, __int128 *, __int128 *, __int128 *); // r12
  __int128 v159; // xmm6
  __int64 v160; // rax
  _QWORD *v161; // rax
  __int64 v162; // rcx
  __int64 v163; // rax
  __int64 v164; // rax
  __int128 *v165; // rax
  unsigned int v166; // eax
  volatile signed __int32 *v167; // rbx
  volatile signed __int32 *v168; // rbx
  volatile signed __int32 *v169; // rbx
  __int64 v170; // rax
  __int64 v171; // rax
  __int64 v172; // rbx
  void (__fastcall *v173)(__int64, __int128 *, __int128 *); // rdi
  _QWORD *ExceptionMessage; // rax
  __int64 v175; // rcx
  _QWORD *v176; // rax
  __int64 v177; // rcx
  __int64 v178; // rax
  __int64 v179; // rax
  __int64 v180; // rbx
  void (__fastcall *v181)(__int64, __int128 *, __int128 *); // rdi
  _QWORD *v182; // rax
  __int64 v183; // rcx
  __int128 *v184; // rdx
  int v185; // [rsp+30h] [rbp-728h]
  __int128 v186; // [rsp+40h] [rbp-718h] BYREF
  Windows::UO::LegacyUOProvider *v187; // [rsp+50h] [rbp-708h]
  __int64 v188; // [rsp+58h] [rbp-700h] BYREF
  __int128 v189; // [rsp+60h] [rbp-6F8h] BYREF
  __int64 v190; // [rsp+70h] [rbp-6E8h]
  __int64 v191; // [rsp+78h] [rbp-6E0h]
  __int128 v192; // [rsp+80h] [rbp-6D8h] BYREF
  __int128 v193; // [rsp+90h] [rbp-6C8h] BYREF
  __int128 v194; // [rsp+A0h] [rbp-6B8h]
  __int128 v195; // [rsp+B0h] [rbp-6A8h] BYREF
  Windows::UO::LegacyUOProvider *v196; // [rsp+C0h] [rbp-698h]
  __int128 v197; // [rsp+D0h] [rbp-688h] BYREF
  char v198[8]; // [rsp+E0h] [rbp-678h] BYREF
  void ***v199; // [rsp+E8h] [rbp-670h]
  __int128 v200; // [rsp+F0h] [rbp-668h] BYREF
  __int64 v201; // [rsp+100h] [rbp-658h]
  unsigned __int64 v202; // [rsp+108h] [rbp-650h]
  __int128 v203; // [rsp+110h] [rbp-648h] BYREF
  __int64 v204; // [rsp+120h] [rbp-638h]
  __int64 v205; // [rsp+128h] [rbp-630h]
  __int128 v206; // [rsp+130h] [rbp-628h] BYREF
  __int128 v207; // [rsp+140h] [rbp-618h] BYREF
  __int128 v208; // [rsp+150h] [rbp-608h] BYREF
  __int64 v209; // [rsp+160h] [rbp-5F8h]
  unsigned __int64 v210; // [rsp+168h] [rbp-5F0h]
  __int128 v211; // [rsp+170h] [rbp-5E8h] BYREF
  __int128 v212; // [rsp+180h] [rbp-5D8h]
  __int64 v213; // [rsp+190h] [rbp-5C8h] BYREF
  unsigned int v214; // [rsp+198h] [rbp-5C0h]
  __int128 v215; // [rsp+1A0h] [rbp-5B8h] BYREF
  __int64 v216; // [rsp+1B0h] [rbp-5A8h]
  __int64 v217; // [rsp+1B8h] [rbp-5A0h]
  char v218; // [rsp+1C0h] [rbp-598h]
  __int128 v219; // [rsp+1D0h] [rbp-588h] BYREF
  _BYTE v220[8]; // [rsp+1E0h] [rbp-578h] BYREF
  volatile signed __int32 *v221; // [rsp+1E8h] [rbp-570h]
  __int128 v222; // [rsp+1F0h] [rbp-568h]
  __int128 v223; // [rsp+200h] [rbp-558h]
  __int128 v224; // [rsp+210h] [rbp-548h]
  __int128 v225; // [rsp+220h] [rbp-538h]
  __int128 v226; // [rsp+230h] [rbp-528h]
  __int128 v227; // [rsp+240h] [rbp-518h]
  __int128 v228; // [rsp+250h] [rbp-508h]
  __int128 v229; // [rsp+260h] [rbp-4F8h]
  __int128 v230; // [rsp+270h] [rbp-4E8h]
  __int128 v231; // [rsp+280h] [rbp-4D8h]
  __int128 v232; // [rsp+290h] [rbp-4C8h]
  _BYTE v233[8]; // [rsp+2A0h] [rbp-4B8h] BYREF
  volatile signed __int32 *v234; // [rsp+2A8h] [rbp-4B0h]
  __int128 v235; // [rsp+2B0h] [rbp-4A8h]
  __int128 v236; // [rsp+2C0h] [rbp-498h] BYREF
  __int128 v237; // [rsp+2D0h] [rbp-488h]
  __int128 v238; // [rsp+2E0h] [rbp-478h] BYREF
  __int128 v239; // [rsp+2F0h] [rbp-468h] BYREF
  __int128 v240; // [rsp+300h] [rbp-458h] BYREF
  __int128 Src; // [rsp+310h] [rbp-448h] BYREF
  __int128 v242; // [rsp+320h] [rbp-438h]
  _BYTE v243[16]; // [rsp+330h] [rbp-428h] BYREF
  _BYTE v244[16]; // [rsp+340h] [rbp-418h] BYREF
  _BYTE v245[16]; // [rsp+350h] [rbp-408h] BYREF
  __int128 v246; // [rsp+360h] [rbp-3F8h] BYREF
  __int64 v247; // [rsp+370h] [rbp-3E8h]
  __int64 v248; // [rsp+378h] [rbp-3E0h]
  __int128 v249; // [rsp+380h] [rbp-3D8h] BYREF
  __int64 v250; // [rsp+390h] [rbp-3C8h]
  __int64 v251; // [rsp+398h] [rbp-3C0h]
  _BYTE v252[8]; // [rsp+3A0h] [rbp-3B8h] BYREF
  volatile signed __int32 *v253; // [rsp+3A8h] [rbp-3B0h]
  _BYTE v254[8]; // [rsp+3B0h] [rbp-3A8h] BYREF
  volatile signed __int32 *v255; // [rsp+3B8h] [rbp-3A0h]
  _BYTE v256[16]; // [rsp+3C0h] [rbp-398h] BYREF
  _BYTE v257[24]; // [rsp+3D0h] [rbp-388h] BYREF
  const std::exception *v258; // [rsp+3E8h] [rbp-370h] BYREF
  const std::exception *v259; // [rsp+3F0h] [rbp-368h] BYREF
  _QWORD v260[34]; // [rsp+400h] [rbp-358h] BYREF
  __int64 v261; // [rsp+510h] [rbp-248h] BYREF
  __int64 v262; // [rsp+518h] [rbp-240h] BYREF
  __int128 v263; // [rsp+520h] [rbp-238h] BYREF
  __int64 v264; // [rsp+530h] [rbp-228h]
  unsigned __int64 v265; // [rsp+538h] [rbp-220h]
  _QWORD v266[2]; // [rsp+540h] [rbp-218h] BYREF
  __int64 v267; // [rsp+550h] [rbp-208h]
  unsigned __int64 v268; // [rsp+558h] [rbp-200h]
  _QWORD v269[4]; // [rsp+560h] [rbp-1F8h] BYREF
  char v270; // [rsp+580h] [rbp-1D8h]
  char v271; // [rsp+588h] [rbp-1D0h]
  _QWORD v272[4]; // [rsp+590h] [rbp-1C8h] BYREF
  char v273; // [rsp+5B0h] [rbp-1A8h]
  __int128 v274; // [rsp+5B8h] [rbp-1A0h] BYREF
  __int64 v275; // [rsp+5C8h] [rbp-190h]
  _BYTE v276[32]; // [rsp+5D0h] [rbp-188h] BYREF
  _BYTE v277[32]; // [rsp+5F0h] [rbp-168h] BYREF
  char v278; // [rsp+610h] [rbp-148h]
  char v279; // [rsp+618h] [rbp-140h]
  _QWORD v280[32]; // [rsp+620h] [rbp-138h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+758h] [rbp+0h]

  v1 = this;
  v187 = this;
  v196 = this;
  v2 = 0;
  v185 = 0;
  System = SystemInterface::Providers::GetSystem(&v219);
  v4 = *(_QWORD *)System + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL);
  v5 = *(void (__fastcall **)(__int64, _BYTE *, __int128 *))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v4 + 40LL))(
                                                                            v4,
                                                                            &v197)
                                                           + 32LL);
  traits_2_unsigned_short = (__int64 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                         L"UOExpeditedAppRegistrations",
                                         &qword_14047F618,
                                         0);
  if ( traits_2_unsigned_short == &qword_14047F618
    || (v9 = ((char *)traits_2_unsigned_short - (char *)L"UOExpeditedAppRegistrations") >> 1, v9 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v7);
  }
  *(_QWORD *)&v207 = L"UOExpeditedAppRegistrations";
  *((_QWORD *)&v207 + 1) = v9;
  v192 = v207;
  v5(v8, v277, &v192);
  v10 = (volatile signed __int32 *)*((_QWORD *)&v197 + 1);
  if ( *((_QWORD *)&v197 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v197 + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( !_InterlockedDecrement(v10 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  v11 = (volatile signed __int32 *)*((_QWORD *)&v219 + 1);
  if ( *((_QWORD *)&v219 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v219 + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( !_InterlockedDecrement(v11 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  v12 = v279;
  if ( v279 )
  {
    try
    {
      v263 = 0;
      v264 = 0;
      v265 = 7;
      LOWORD(v263) = 0;
      if ( v278 != 2 )
        std::_Throw_bad_variant_access();
      std::wstring::operator=(&v263);
      v274 = 0;
      v275 = 0;
      v13 = (_QWORD *)web::json::value::parse(&v213, &v263);
      v14 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 152LL))(*v13);
      std::vector<web::json::value>::vector<web::json::value>(&v274, v14);
      if ( v213 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v213 + 192LL))(v213, 1);
      *(_QWORD *)&v208 = *((_QWORD *)&v274 + 1);
      for ( i = (_QWORD *)v274; ; ++i )
      {
        *(_QWORD *)&v206 = i;
        if ( i == (_QWORD *)v208 )
        {
          std::vector<web::json::value>::_Tidy(&v274);
          goto LABEL_247;
        }
        try
        {
          v261 = 0;
          web::json::value::value((web::json::value *)&v261);
          if ( (unsigned __int8)Windows::Json::has_duplicates_or_unknowns(i) )
          {
            v16 = SystemInterface::Providers::GetSystem(&v239);
            v17 = *(_QWORD *)v16 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v16 + 8LL) + 4LL);
            v18 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v17 + 104LL))(v17, &v219);
            v19 = *(_QWORD *)v18;
            v20 = *(void (__fastcall **)(__int64, __int128 *, __int128 *))(**(_QWORD **)v18 + 176LL);
            v21 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                    L"Found duplicate/unknown keys in Expedited JSON",
                    &word_14047F67E,
                    0);
            if ( v21 == v23
              || (v24 = (v21 - (__int64)L"Found duplicate/unknown keys in Expedited JSON") >> 1, v24 == -1) )
            {
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0xC9,
                (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
                v22);
            }
            *(_QWORD *)&v207 = L"Found duplicate/unknown keys in Expedited JSON";
            *((_QWORD *)&v207 + 1) = v24;
            (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*i + 80LL))(*i, &v193);
            v2 |= 0x400u;
            v25 = &v193;
            if ( *((_QWORD *)&v194 + 1) > 7u )
              v25 = (__int128 *)v193;
            *(_QWORD *)&v211 = v25;
            *((_QWORD *)&v211 + 1) = v194;
            v192 = v207;
            v197 = v211;
            v20(v19, &v197, &v192);
            std::wstring::~wstring(&v193);
            v26 = (volatile signed __int32 *)*((_QWORD *)&v219 + 1);
            if ( *((_QWORD *)&v219 + 1) )
            {
              if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v219 + 1) + 8LL)) )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
                if ( !_InterlockedDecrement(v26 + 3) )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
              }
            }
            v27 = (volatile signed __int32 *)*((_QWORD *)&v239 + 1);
            if ( *((_QWORD *)&v239 + 1) )
            {
              if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v239 + 1) + 8LL)) )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
                if ( !_InterlockedDecrement(v27 + 3) )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
              }
            }
            v1 = v187;
          }
          v28 = (__int64 *)Windows::Json::normalize_keys(v198, i);
          if ( &v261 != v28 )
          {
            v29 = v261;
            v261 = *v28;
            *v28 = v29;
          }
          if ( *(_QWORD *)v198 )
            (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v198 + 192LL))(*(_QWORD *)v198, 1);
          if ( !Windows::UO::LegacyUOProvider::ValidateExpeditedJson(v1, (const struct web::json::value *)&v261) )
          {
            v30 = SystemInterface::Providers::GetSystem(&v240);
            v31 = *(_QWORD *)v30 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v30 + 8LL) + 4LL);
            v32 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v31 + 104LL))(v31, &v238);
            v33 = *(_QWORD *)v32;
            v34 = *(void (__fastcall **)(__int64, __int128 *))(**(_QWORD **)v32 + 152LL);
            (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v261 + 80LL))(v261, &v193);
            v2 |= 0x200u;
            v185 = v2;
            v35 = &v193;
            if ( *((_QWORD *)&v194 + 1) > 7u )
              v35 = (__int128 *)v193;
            *(_QWORD *)&v222 = v35;
            *((_QWORD *)&v222 + 1) = v194;
            v192 = v222;
            v34(v33, &v192);
            std::wstring::~wstring(&v193);
            v37 = (volatile signed __int32 *)*((_QWORD *)&v238 + 1);
            if ( *((_QWORD *)&v238 + 1) )
            {
              if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v238 + 1) + 8LL)) )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
                if ( !_InterlockedDecrement(v37 + 3) )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
              }
            }
            v38 = (volatile signed __int32 *)*((_QWORD *)&v240 + 1);
            if ( *((_QWORD *)&v240 + 1) )
            {
              if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v240 + 1) + 8LL)) )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
                if ( !_InterlockedDecrement(v38 + 3) )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
              }
            }
            if ( v261 )
              goto LABEL_49;
LABEL_50:
            v1 = v187;
            continue;
          }
          v246 = 0;
          v247 = 0;
          v248 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v246, L"UpdaterName", 11);
          v39 = (_QWORD *)web::json::value::at(&v261, &v246);
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v39 + 176LL))(*v39);
          v249 = 0;
          v250 = 0;
          v251 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v249, L"OEMName", 7);
          v40 = (_QWORD *)web::json::value::at(&v261, &v249);
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v40 + 176LL))(*v40);
          *(_QWORD *)&v223 = L"{}_{}";
          *((_QWORD *)&v223 + 1) = 5;
          v192 = v223;
          std::format<std::wstring const &,std::wstring const &>(v266);
          std::wstring::~wstring(&v249);
          std::wstring::~wstring(&v246);
          v193 = 0;
          v194 = 0u;
          std::wstring::_Construct<1,wchar_t const *>(&v193, L"RegistrationVersion", 19);
          v41 = (_QWORD *)web::json::value::at(&v261, &v193);
          LODWORD(v188) = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v41 + 128LL))(*v41);
          std::wstring::~wstring(&v193);
          v42 = SystemInterface::Providers::GetSystem(v254);
          v43 = *(_QWORD *)v42 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v42 + 8LL) + 4LL);
          v44 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v43 + 32LL))(v43, v252);
          v45 = *(_QWORD *)v44;
          v46 = *(__int64 (__fastcall **)(__int64, __int128 *, __int128 *))(**(_QWORD **)v44 + 8LL);
          v203 = 0;
          v204 = 0;
          v205 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v203, L"\\", 1);
          v47 = std::wstring::insert(&v203, 0, L"\\UScheduler", 11);
          Src = 0;
          v242 = 0u;
          Src = *(_OWORD *)v47;
          v242 = *(_OWORD *)(v47 + 16);
          *(_QWORD *)(v47 + 16) = 0;
          *(_QWORD *)(v47 + 24) = 7;
          *(_WORD *)v47 = 0;
          v48 = std::wstring::append(&Src);
          v193 = 0;
          v194 = 0u;
          v193 = *(_OWORD *)v48;
          v194 = *(_OWORD *)(v48 + 16);
          *(_QWORD *)(v48 + 16) = 0;
          *(_QWORD *)(v48 + 24) = 7;
          *(_WORD *)v48 = 0;
          v2 |= 0x1C0u;
          v185 = v2;
          v49 = &v193;
          if ( *((_QWORD *)&v194 + 1) > 7u )
            v49 = (__int128 *)v193;
          *(_QWORD *)&v235 = v49;
          *((_QWORD *)&v235 + 1) = v194;
          *(_QWORD *)&v237 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
          v50 = -1;
          do
            ++v50;
          while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v50] );
          *((_QWORD *)&v237 + 1) = v50;
          v192 = v235;
          v197 = v237;
          v51 = v46(v45, &v197, &v192);
          std::wstring::~wstring(&v193);
          std::wstring::~wstring(&Src);
          std::wstring::~wstring(&v203);
          v52 = v253;
          if ( v253 )
          {
            if ( _InterlockedExchangeAdd(v253 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v52)(v52);
              if ( _InterlockedExchangeAdd(v52 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v52 + 8LL))(v52);
            }
          }
          v53 = v255;
          if ( v255 )
          {
            if ( _InterlockedExchangeAdd(v255 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v53)(v53);
              if ( _InterlockedExchangeAdd(v53 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v53 + 8LL))(v53);
            }
          }
          if ( v51 )
          {
            v54 = SystemInterface::Providers::GetSystem(v243);
            v55 = *(_QWORD *)v54 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v54 + 8LL) + 4LL);
            v56 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v55 + 32LL))(v55, v256);
            v57 = *(_QWORD *)v56;
            v58 = *(void (__fastcall **)(__int64, _QWORD *, __int128 *, __int128 *, __int128 *))(**(_QWORD **)v56 + 56LL);
            v59 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                               &v236,
                               L"updaterRegistrationVersion");
            v193 = 0;
            v194 = 0u;
            std::wstring::_Construct<1,wchar_t const *>(&v193, L"\\", 1);
            v2 |= 0x4000u;
            v185 = v2;
            v60 = std::operator+<wchar_t>(&v215, L"\\UScheduler", &v193);
            v61 = (_QWORD *)std::operator+<wchar_t>(&v189, v60, v266);
            v62 = v61[2];
            if ( v61[3] > 7u )
              v61 = (_QWORD *)*v61;
            *(_QWORD *)&v224 = v61;
            *((_QWORD *)&v224 + 1) = v62;
            *(_QWORD *)&v225 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
            v63 = -1;
            do
              ++v63;
            while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v63] );
            *((_QWORD *)&v225 + 1) = v63;
            v192 = v59;
            v197 = v224;
            v203 = v225;
            v58(v57, v269, &v203, &v197, &v192);
            std::wstring::~wstring(&v189);
            std::wstring::~wstring(&v215);
            std::wstring::~wstring(&v193);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v256);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v243);
            if ( v271 && !v270 && (unsigned int)v188 <= LODWORD(v269[0]) )
            {
              *(_QWORD *)&v226 = L"Registration version for updater {} is less than or equal to the existing registration "
                                  "version. Skipping registration.";
              *((_QWORD *)&v226 + 1) = 118;
              v203 = v226;
              SystemInterface::Log<std::wstring>(&v203, v266);
              if ( v271 && v270 != -1 && v270 && v270 != 1 )
                std::wstring::~wstring(v269);
              std::wstring::~wstring(v266);
              if ( !v261 )
                goto LABEL_50;
              goto LABEL_49;
            }
            if ( v271 && v270 != -1 && v270 && v270 != 1 )
              std::wstring::~wstring(v269);
          }
          v64 = v266;
          if ( v268 > 7 )
            v64 = (_QWORD *)v266[0];
          *(_QWORD *)&v227 = v64;
          *((_QWORD *)&v227 + 1) = v267;
          v203 = v227;
          v1 = v187;
          Windows::UO::LegacyUOProvider::PerformApplicabilityChecks(v187, v272, &v203, &v261);
          if ( v273 )
          {
            v66 = SystemInterface::Providers::GetSystem(v245);
            v67 = *(_QWORD *)v66 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v66 + 8LL) + 4LL);
            v68 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v67 + 104LL))(v67, v244);
            v69 = *(_QWORD *)v68;
            v70 = *(void (__fastcall **)(__int64, __int128 *, __int128 *))(**(_QWORD **)v68 + 144LL);
            if ( !v273 )
              std::_Throw_bad_optional_access();
            v71 = v272;
            if ( v272[3] > 7u )
              v71 = (_QWORD *)v272[0];
            *(_QWORD *)&v228 = v71;
            *((_QWORD *)&v228 + 1) = v272[2];
            v72 = v266;
            if ( v268 > 7 )
              v72 = (_QWORD *)v266[0];
            *(_QWORD *)&v229 = v72;
            *((_QWORD *)&v229 + 1) = v267;
            v203 = v228;
            v192 = v229;
            v70(v69, &v192, &v203);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v244);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v245);
            v73 = SystemInterface::Providers::GetSystem(v233);
            v74 = *(_QWORD *)v73 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v73 + 8LL) + 4LL);
            v75 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v74 + 32LL))(v74, v220);
            v76 = *(_QWORD *)v75;
            v77 = *(void (__fastcall **)(__int64, __int128 *, __int128 *, __int128 *, _QWORD *))(**(_QWORD **)v75 + 64LL);
            LODWORD(v269[0]) = v188;
            v270 = 0;
            v78 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                               v257,
                               L"updaterRegistrationVersion");
            v193 = 0;
            v194 = 0u;
            std::wstring::_Construct<1,wchar_t const *>(&v193, L"\\", 1);
            v2 |= 0x8000u;
            v185 = v2;
            v79 = std::operator+<wchar_t>(&v215, L"\\UScheduler", &v193);
            v80 = (_QWORD *)std::operator+<wchar_t>(&v189, v79, v266);
            v81 = v80[2];
            if ( v80[3] > 7u )
              v80 = (_QWORD *)*v80;
            *(_QWORD *)&v230 = v80;
            *((_QWORD *)&v230 + 1) = v81;
            *(_QWORD *)&v231 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
            v82 = -1;
            do
              ++v82;
            while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v82] );
            *((_QWORD *)&v231 + 1) = v82;
            v203 = v78;
            v192 = v230;
            v197 = v231;
            v77(v76, &v197, &v192, &v203, v269);
            std::wstring::~wstring(&v189);
            std::wstring::~wstring(&v215);
            std::wstring::~wstring(&v193);
            if ( v270 != -1 && v270 && v270 != 1 )
              std::wstring::~wstring(v269);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v220);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v233);
            v83 = std::wstring::wstring(&v189, v266);
            Windows::UO::ReportUOWorkCompleted(v83);
            if ( v273 )
              std::wstring::~wstring(v272);
            std::wstring::~wstring(v266);
            if ( !v261 )
              goto LABEL_50;
LABEL_49:
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v261 + 192LL))(v261, 1);
            goto LABEL_50;
          }
          v84 = v266;
          if ( v268 > 7 )
            v84 = (_QWORD *)v266[0];
          *(_QWORD *)&v232 = v84;
          *((_QWORD *)&v232 + 1) = v267;
          v203 = v232;
          LOBYTE(v65) = 1;
          Windows::UO::LegacyUOProvider::RegisterConfigBasedExpeditedApp(v1, &v203, &v261, v65);
          std::wstring::~wstring(v266);
          if ( v261 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v261 + 192LL))(v261, 1);
        }
        catch ( const std::exception *v259 )
        {
          v170 = SystemInterface::Providers::GetSystem(&v186);
          v171 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)(*(int *)(*(_QWORD *)(*(_QWORD *)v170 + 8LL)
                                                                                     + 4LL)
                                                                            + *(_QWORD *)v170
                                                                            + 8LL)
                                                                + 104LL))(
                   *(_QWORD *)v170 + *(int *)(*(_QWORD *)(*(_QWORD *)v170 + 8LL) + 4LL) + 8LL,
                   &v200);
          v172 = *(_QWORD *)v171;
          v173 = *(void (__fastcall **)(__int64, __int128 *, __int128 *))(**(_QWORD **)v171 + 168LL);
          ExceptionMessage = (_QWORD *)Windows::UO::GetExceptionMessage(&v215, v259);
          v175 = ExceptionMessage[2];
          if ( ExceptionMessage[3] > 7u )
            ExceptionMessage = (_QWORD *)*ExceptionMessage;
          *(_QWORD *)&v212 = ExceptionMessage;
          *((_QWORD *)&v212 + 1) = v175;
          v176 = (_QWORD *)web::json::value::serialize(v206, &v189);
          v177 = v176[2];
          if ( v176[3] > 7u )
            v176 = (_QWORD *)*v176;
          *(_QWORD *)&v195 = v176;
          *((_QWORD *)&v195 + 1) = v177;
          v203 = v212;
          v192 = v195;
          v173(v172, &v192, &v203);
          std::wstring::~wstring(&v189);
          std::wstring::~wstring(&v215);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v200);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v186);
          v1 = v196;
          v187 = v196;
          v2 = v185;
          i = (_QWORD *)v206;
          continue;
        }
        catch ( ... )
        {
          wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x290,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\LegacyUOProvider.cpp",
            v36);
          v1 = v196;
          v187 = v196;
          v2 = v185;
          i = (_QWORD *)v206;
          continue;
        }
      }
    }
    catch ( const std::exception *v258 )
    {
      v178 = SystemInterface::Providers::GetSystem(v220);
      v179 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)(*(int *)(*(_QWORD *)(*(_QWORD *)v178 + 8LL) + 4LL)
                                                                     + *(_QWORD *)v178
                                                                     + 8LL)
                                                         + 104LL))(
               *(_QWORD *)v178 + *(int *)(*(_QWORD *)(*(_QWORD *)v178 + 8LL) + 4LL) + 8LL,
               v233);
      v180 = *(_QWORD *)v179;
      v181 = *(void (__fastcall **)(__int64, __int128 *, __int128 *))(**(_QWORD **)v179 + 160LL);
      v182 = (_QWORD *)Windows::UO::GetExceptionMessage(&v189, v258);
      v183 = v182[2];
      if ( v182[3] > 7u )
        v182 = (_QWORD *)*v182;
      *(_QWORD *)&v195 = v182;
      *((_QWORD *)&v195 + 1) = v183;
      v184 = &v263;
      if ( v265 > 7 )
        v184 = (__int128 *)v263;
      *(_QWORD *)&v212 = v184;
      *((_QWORD *)&v212 + 1) = v264;
      v186 = v195;
      v200 = v212;
      v181(v180, &v200, &v186);
      std::wstring::~wstring(&v189);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v233);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v220);
      v187 = v196;
      goto LABEL_109;
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x29B,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\LegacyUOProvider.cpp",
        v85);
      v187 = v196;
LABEL_109:
      v2 = v185;
    }
LABEL_247:
    std::wstring::~wstring(&v263);
    v12 = v279;
  }
  if ( v12 && v278 != -1 && v278 && v278 != 1 )
    std::wstring::~wstring(v277);
  Windows::UO::GetConfigBasedRegistrationPath(v276);
  std::wstring::wstring(&v189, v276);
  v86 = v2 | 4;
  *(_QWORD *)&v195 = L"Searching for Config-based expedited updaters from: {}";
  *((_QWORD *)&v195 + 1) = 54;
  v186 = v195;
  SystemInterface::Log<std::wstring>(&v186, &v189);
  std::wstring::~wstring(&v189);
  *(_QWORD *)v198 = 0;
  v199 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  v88 = std::filesystem::exists((std::filesystem *)v276, (const struct std::filesystem::path *)v198, v87);
  if ( *(_DWORD *)v198 )
    std::filesystem::_Throw_fs_error((std::filesystem *)"exists", v198, (const struct std::error_code *)v276, v90);
  if ( !v88 || !std::filesystem::is_directory((std::filesystem *)v276, v89) )
  {
    *(_QWORD *)&v192 = L"Config-based expedited updaters registration path does not exist or is not a directory";
    *((_QWORD *)&v192 + 1) = 86;
    v236 = v192;
    SystemInterface::Log<>(&v236);
    goto LABEL_223;
  }
  std::filesystem::recursive_directory_iterator::recursive_directory_iterator(
    (std::filesystem::recursive_directory_iterator *)&v211,
    (const struct std::filesystem::path *)v276);
  v206 = 0;
  v91 = *((_QWORD *)&v211 + 1);
  if ( *((_QWORD *)&v211 + 1) )
  {
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v211 + 1) + 8LL));
    v91 = *((_QWORD *)&v211 + 1);
  }
  v92 = v211;
  v206 = v211;
  v207 = 0;
  if ( v91 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v91 + 8));
    v92 = v211;
  }
  v195 = v92;
  std::filesystem::end(&v207, &v195);
  while ( 1 )
  {
    v93 = (_QWORD *)v206;
    if ( (_QWORD)v206 == (_QWORD)v207 )
      break;
    std::filesystem::directory_entry::_Get_any_status((_DWORD *)v206, (unsigned int *)&v213, 3);
    if ( v214 && (((_DWORD)v213 - 1) & 0xFFFFFFF7) != 0 )
      std::filesystem::_Throw_fs_error("directory_entry::status", v214, v93 + 4);
    if ( (_DWORD)v213 != 2 )
      goto LABEL_136;
    v94 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                   L".json",
                   &dword_14047FD1C,
                   0);
    if ( v94 == &dword_14047FD1C || (v96 = ((char *)v94 - (char *)L".json") >> 1, v96 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v95);
    *(_QWORD *)&v232 = L".json";
    *((_QWORD *)&v232 + 1) = v96;
    v97 = v93 + 4;
    if ( v93[7] > 7u )
      v97 = (_QWORD *)v93[4];
    *(_QWORD *)&v195 = v97;
    *((_QWORD *)&v195 + 1) = v93[6];
    v186 = v195;
    v212 = *(_OWORD *)std::filesystem::_Parse_extension(&v193, &v186);
    v186 = v212;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(&v189, &v186);
    std::wstring::wstring(&v263, &v189);
    v86 |= 0x3Bu;
    v98 = &v263;
    if ( v265 > 7 )
      v98 = (__int128 *)v263;
    *(_QWORD *)&v231 = v98;
    *((_QWORD *)&v231 + 1) = v264;
    v186 = v232;
    v200 = v231;
    if ( (unsigned __int8)Strings::iequals(&v200, &v186) )
      v99 = 1;
    else
LABEL_136:
      v99 = 0;
    if ( (v86 & 2) != 0 )
    {
      v86 &= ~2u;
      std::wstring::~wstring(&v263);
    }
    if ( (v86 & 1) != 0 )
    {
      v86 &= ~1u;
      std::wstring::~wstring(&v189);
    }
    if ( v99 )
    {
      memset(v260, 0, sizeof(v260));
      v100 = v93 + 4;
      std::wifstream::wifstream(v260, v93 + 4);
      if ( (*((_BYTE *)&v260[2] + *(int *)(v260[0] + 4LL)) & 6) == 0 )
      {
        memset(v280, 0, 0xF8u);
        std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v280);
        std::wostream::operator<<(&v280[2], &v260[2]);
        v188 = 0;
        v113 = std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(v280, &v189);
        web::json::value::parse(&v188, v113);
        std::wstring::~wstring(&v189);
        v262 = 0;
        web::json::value::value((web::json::value *)&v262);
        if ( (unsigned __int8)Windows::Json::has_duplicates_or_unknowns(&v188) )
        {
          v114 = SystemInterface::Providers::GetSystem(v244);
          v115 = *(_QWORD *)v114 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v114 + 8LL) + 4LL);
          v116 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v115 + 104LL))(v115, v245);
          v117 = *(_QWORD *)v116;
          v118 = *(void (__fastcall **)(__int64, __int128 *, __int128 *))(**(_QWORD **)v116 + 176LL);
          v119 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                              v266,
                              L"Found duplicate/unknown keys in Expedited JSON");
          v120 = (_QWORD *)web::json::value::serialize(&v188, &v189);
          v121 = v120[2];
          if ( v120[3] > 7u )
            v120 = (_QWORD *)*v120;
          *(_QWORD *)&v228 = v120;
          *((_QWORD *)&v228 + 1) = v121;
          v186 = v119;
          v200 = v228;
          v118(v117, &v200, &v186);
          std::wstring::~wstring(&v189);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v245);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v244);
        }
        v122 = (__int64 *)Windows::Json::normalize_keys(v198, &v188);
        if ( &v262 != v122 )
        {
          v123 = v262;
          v262 = *v122;
          *v122 = v123;
        }
        if ( *(_QWORD *)v198 )
          (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v198 + 192LL))(*(_QWORD *)v198, 1);
        (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v262 + 80LL))(v262, &v215);
        std::wstring::wstring(&v189, v100);
        v124 = v86 | 0x3000;
        *(_QWORD *)&v227 = L"Filename: {}, Content: {}";
        *((_QWORD *)&v227 + 1) = 25;
        v186 = v227;
        SystemInterface::Log<std::wstring,std::wstring>(&v186, &v189, &v215);
        std::wstring::~wstring(&v189);
        std::wstring::~wstring(&v215);
        if ( Windows::UO::LegacyUOProvider::ValidateExpeditedJson(v187, (const struct web::json::value *)&v262) )
        {
          v215 = 0;
          v216 = 0;
          v217 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v215, L"UpdaterName", 11);
          v131 = (_QWORD *)web::json::value::at(&v262, &v215);
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v131 + 176LL))(*v131);
          v208 = 0;
          v209 = 0;
          v210 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v208, L"OEMName", 7);
          v132 = (_QWORD *)web::json::value::at(&v262, &v208);
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v132 + 176LL))(*v132);
          *(_QWORD *)&v225 = L"{}_{}";
          *((_QWORD *)&v225 + 1) = 5;
          v186 = v225;
          std::format<std::wstring const &,std::wstring const &>(&v263);
          std::wstring::~wstring(&v208);
          std::wstring::~wstring(&v215);
          v133 = SystemInterface::Providers::GetSystem(v254);
          v134 = *(_QWORD *)v133 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v133 + 8LL) + 4LL);
          v135 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v134 + 32LL))(v134, &v203);
          v136 = *(_QWORD *)v135;
          v137 = *(__int64 (__fastcall **)(__int64, __int128 *, __int128 *))(**(_QWORD **)v135 + 8LL);
          v189 = 0;
          v190 = 0;
          v191 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v189, L"\\", 1);
          v86 = v124 | 0x10000;
          v138 = std::operator+<wchar_t>(v272, L"\\UScheduler", &v189);
          v139 = (_QWORD *)std::operator+<wchar_t>(v277, v138, &v263);
          v140 = v139[2];
          if ( v139[3] > 7u )
            v139 = (_QWORD *)*v139;
          *(_QWORD *)&v224 = v139;
          *((_QWORD *)&v224 + 1) = v140;
          *(_QWORD *)&v237 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
          v141 = -1;
          do
            ++v141;
          while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v141] );
          *((_QWORD *)&v237 + 1) = v141;
          v186 = v224;
          v200 = v237;
          v142 = v137(v136, &v200, &v186);
          std::wstring::~wstring(v277);
          std::wstring::~wstring(v272);
          std::wstring::~wstring(&v189);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v203);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v254);
          if ( v142 )
          {
            *(_QWORD *)&v235 = L"Updater already exists: {}";
            *((_QWORD *)&v235 + 1) = 26;
            v186 = v235;
            SystemInterface::Log<std::wstring>(&v186, &v263);
            std::wstring::~wstring(&v263);
            if ( v262 )
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v262 + 192LL))(v262, 1);
            if ( !v188 )
              goto LABEL_208;
          }
          else
          {
            v143 = &v263;
            if ( v265 > 7 )
              v143 = (__int128 *)v263;
            *(_QWORD *)&v223 = v143;
            *((_QWORD *)&v223 + 1) = v264;
            v186 = v223;
            v144 = v187;
            Windows::UO::LegacyUOProvider::PerformApplicabilityChecks(v187, v269, &v186, &v262);
            if ( v270 )
            {
              v145 = SystemInterface::Providers::GetSystem(&v246);
              v146 = *(_QWORD *)v145 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v145 + 8LL) + 4LL);
              v147 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v146 + 104LL))(v146, v252);
              v148 = *(_QWORD *)v147;
              v149 = *(void (__fastcall **)(__int64, __int128 *, __int128 *))(**(_QWORD **)v147 + 144LL);
              if ( !v270 )
                std::_Throw_bad_optional_access();
              v150 = v269;
              if ( v269[3] > 7u )
                v150 = (_QWORD *)v269[0];
              *(_QWORD *)&v222 = v150;
              *((_QWORD *)&v222 + 1) = v269[2];
              v151 = &v263;
              if ( v265 > 7 )
                v151 = (__int128 *)v263;
              *(_QWORD *)&v240 = v151;
              *((_QWORD *)&v240 + 1) = v264;
              v186 = v222;
              v200 = v240;
              v149(v148, &v200, &v186);
              std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v252);
              std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v246);
              v189 = 0;
              v190 = 0;
              v191 = 0;
              std::wstring::_Construct<1,wchar_t const *>(&v189, L"RegistrationVersion", 19);
              v152 = (_QWORD *)web::json::value::at(&v262, &v189);
              v153 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v152 + 128LL))(*v152);
              std::wstring::~wstring(&v189);
              v154 = SystemInterface::Providers::GetSystem(&Src);
              v155 = *(_QWORD *)v154 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v154 + 8LL) + 4LL);
              v156 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v155 + 32LL))(v155, &v249);
              v157 = *(_QWORD *)v156;
              v158 = *(void (__fastcall **)(__int64, __int128 *, __int128 *, __int128 *, __int128 *))(**(_QWORD **)v156 + 64LL);
              LODWORD(v215) = v153;
              v218 = 0;
              v159 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                                  &v274,
                                  L"updaterRegistrationVersion");
              v189 = 0;
              v190 = 0;
              v191 = 0;
              std::wstring::_Construct<1,wchar_t const *>(&v189, L"\\", 1);
              v86 |= 0x40000u;
              v160 = std::operator+<wchar_t>(v277, L"\\UScheduler", &v189);
              v161 = (_QWORD *)std::operator+<wchar_t>(v272, v160, &v263);
              v162 = v161[2];
              if ( v161[3] > 7u )
                v161 = (_QWORD *)*v161;
              *(_QWORD *)&v238 = v161;
              *((_QWORD *)&v238 + 1) = v162;
              *(_QWORD *)&v239 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
              v163 = -1;
              do
                ++v163;
              while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v163] );
              *((_QWORD *)&v239 + 1) = v163;
              v186 = v159;
              v200 = v238;
              v208 = v239;
              v158(v157, &v208, &v200, &v186, &v215);
              std::wstring::~wstring(v272);
              std::wstring::~wstring(v277);
              std::wstring::~wstring(&v189);
              if ( v218 != -1 && v218 && v218 != 1 )
                std::wstring::~wstring(&v215);
              std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v249);
              std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&Src);
              v164 = std::wstring::wstring(v272, &v263);
              Windows::UO::ReportUOWorkCompleted(v164);
              if ( v270 )
                std::wstring::~wstring(v269);
              std::wstring::~wstring(&v263);
              if ( v262 )
                (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v262 + 192LL))(v262, 1);
              if ( !v188 )
                goto LABEL_208;
            }
            else
            {
              v165 = &v263;
              if ( v265 > 7 )
                v165 = (__int128 *)v263;
              *(_QWORD *)&v219 = v165;
              *((_QWORD *)&v219 + 1) = v264;
              v186 = v219;
              Windows::UO::LegacyUOProvider::RegisterConfigBasedExpeditedApp(v144, &v186, &v262, 0);
              std::wstring::~wstring(&v263);
              if ( v262 )
                (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v262 + 192LL))(v262, 1);
              if ( !v188 )
                goto LABEL_208;
            }
          }
LABEL_207:
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v188 + 192LL))(v188, 1);
        }
        else
        {
          v125 = SystemInterface::Providers::GetSystem(v256);
          v126 = *(_QWORD *)v125 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v125 + 8LL) + 4LL);
          v127 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v126 + 104LL))(v126, v243);
          v128 = *(_QWORD *)v127;
          v129 = *(void (__fastcall **)(__int64, __int128 *))(**(_QWORD **)v127 + 152LL);
          std::wstring::wstring(&v200, v100);
          v86 = v124 | 0x20000;
          v130 = &v200;
          if ( v202 > 7 )
            v130 = (__int128 *)v200;
          *(_QWORD *)&v226 = v130;
          *((_QWORD *)&v226 + 1) = v201;
          v186 = v226;
          v129(v128, &v186);
          std::wstring::~wstring(&v200);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v243);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v256);
          if ( v262 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v262 + 192LL))(v262, 1);
          if ( v188 )
            goto LABEL_207;
        }
LABEL_208:
        std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(&v280[19]);
        v280[19] = &std::wios::`vftable';
        std::ios_base::~ios_base((std::ios_base *)&v280[19]);
        std::wifstream::~wifstream<wchar_t,std::char_traits<wchar_t>>(&v260[22]);
        v260[22] = &std::wios::`vftable';
        std::ios_base::~ios_base((std::ios_base *)&v260[22]);
        goto LABEL_209;
      }
      v101 = SystemInterface::Providers::GetSystem(v220);
      v102 = *(_QWORD *)v101 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v101 + 8LL) + 4LL);
      v103 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v102 + 104LL))(v102, v233);
      v104 = *(_QWORD *)v103;
      v105 = *(void (__fastcall **)(__int64, __int128 *, __int128 *))(**(_QWORD **)v103 + 168LL);
      v106 = (wchar_t *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                          L"Failed to open file",
                          L"Filename: {}, Content: {}",
                          0);
      if ( v106 == L"Filename: {}, Content: {}" || (v109 = ((__int64)v106 - v108) >> 1, v109 == -1) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v107);
      *(_QWORD *)&v230 = v108;
      *((_QWORD *)&v230 + 1) = v109;
      std::wstring::wstring(&v208, v100);
      v86 |= 0x800u;
      v110 = &v208;
      if ( v210 > 7 )
        v110 = (__int128 *)v208;
      *(_QWORD *)&v229 = v110;
      *((_QWORD *)&v229 + 1) = v209;
      v186 = v230;
      v200 = v229;
      v105(v104, &v200, &v186);
      std::wstring::~wstring(&v208);
      v111 = v234;
      if ( v234 )
      {
        if ( !_InterlockedDecrement(v234 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v111)(v111);
          if ( !_InterlockedDecrement(v111 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v111 + 8LL))(v111);
        }
      }
      v112 = v221;
      if ( v221 )
      {
        if ( !_InterlockedDecrement(v221 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v112)(v112);
          if ( !_InterlockedDecrement(v112 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v112 + 8LL))(v112);
        }
      }
      std::wifstream::~wifstream<wchar_t,std::char_traits<wchar_t>>(&v260[22]);
      v260[22] = &std::wios::`vftable';
      std::ios_base::~ios_base((std::ios_base *)&v260[22]);
    }
LABEL_209:
    v166 = std::filesystem::_Recursive_dir_enum_impl::_Advance_and_reset_if_no_more_files(&v206);
    if ( v166 )
      std::filesystem::_Throw_fs_error("recursive_directory_iterator::operator++", v166);
  }
  v167 = (volatile signed __int32 *)*((_QWORD *)&v207 + 1);
  if ( *((_QWORD *)&v207 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v207 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v167)(v167);
      if ( _InterlockedExchangeAdd(v167 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v167 + 8LL))(v167);
    }
  }
  v168 = (volatile signed __int32 *)*((_QWORD *)&v206 + 1);
  if ( *((_QWORD *)&v206 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v206 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v168)(v168);
      if ( _InterlockedExchangeAdd(v168 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v168 + 8LL))(v168);
    }
  }
  v169 = (volatile signed __int32 *)*((_QWORD *)&v211 + 1);
  if ( *((_QWORD *)&v211 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v211 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v169)(v169);
      if ( _InterlockedExchangeAdd(v169 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v169 + 8LL))(v169);
    }
  }
LABEL_223:
  std::wstring::~wstring(v276);
}

```

## disassembly

```asm
0x14031cfe0  mov     rax, rsp
0x14031cfe3  mov     [rax+10h], rbx
0x14031cfe7  mov     [rax+18h], rsi
0x14031cfeb  mov     [rax+20h], rdi
0x14031cfef  push    r12
0x14031cff1  push    r14
0x14031cff3  push    r15
0x14031cff5  sub     rsp, 740h
0x14031cffc  movaps  xmmword ptr [rax-28h], xmm6
0x14031d000  mov     rax, cs:__security_cookie
0x14031d007  xor     rax, rsp
0x14031d00a  mov     [rsp+758h+var_38], rax
0x14031d012  mov     r14, rcx
0x14031d015  mov     [rsp+758h+var_708], rcx
0x14031d01a  mov     [rsp+758h+var_698], rcx
0x14031d022  xor     edi, edi
0x14031d024  mov     r15d, edi
0x14031d027  mov     [rsp+758h+var_728], edi
0x14031d02b  lea     rcx, [rsp+758h+var_588]
0x14031d033  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x14031d038  nop
0x14031d039  mov     rdx, [rax]
0x14031d03c  mov     rax, [rdx+8]
0x14031d040  movsxd  rcx, dword ptr [rax+4]
0x14031d044  add     rdx, 8
0x14031d048  add     rcx, rdx
0x14031d04b  mov     rax, [rcx]
0x14031d04e  lea     rdx, [rsp+758h+var_688]
0x14031d056  mov     rax, [rax+28h]
0x14031d05a  call    _guard_dispatch_icall
0x14031d05f  nop
0x14031d060  mov     r11, [rax]
0x14031d063  mov     rax, [r11]
0x14031d066  mov     rbx, [rax+20h]
0x14031d06a  xor     r8d, r8d
0x14031d06d  lea     rsi, qword_14047F618
0x14031d074  mov     rdx, rsi
0x14031d077  lea     r12, aUoexpeditedapp; "UOExpeditedAppRegistrations"
0x14031d07e  mov     rcx, r12
0x14031d081  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x14031d086  cmp     rax, rsi
0x14031d089  jz      loc_14031F5B1
0x14031d08f  sub     rax, r12
0x14031d092  sar     rax, 1
0x14031d095  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14031d099  cmp     rax, rsi
0x14031d09c  jz      loc_14031F5B1
0x14031d0a2  mov     qword ptr [rsp+758h+var_618], r12
0x14031d0aa  mov     qword ptr [rsp+758h+var_618+8], rax
0x14031d0b2  movaps  xmm0, [rsp+758h+var_618]
0x14031d0ba  movdqa  [rsp+758h+var_6D8], xmm0
0x14031d0c3  lea     r8, [rsp+758h+var_6D8]
0x14031d0cb  lea     rdx, [rsp+758h+var_168]
0x14031d0d3  mov     rcx, r11
0x14031d0d6  mov     rax, rbx
0x14031d0d9  call    _guard_dispatch_icall
0x14031d0de  nop
0x14031d0df  mov     rbx, qword ptr [rsp+758h+var_688+8]
0x14031d0e7  test    rbx, rbx
0x14031d0ea  jz      short loc_14031D120
0x14031d0ec  mov     eax, esi
0x14031d0ee  lock xadd [rbx+8], eax
0x14031d0f3  add     eax, esi
0x14031d0f5  jnz     short loc_14031D120
0x14031d0f7  mov     rax, [rbx]
0x14031d0fa  mov     rcx, rbx
0x14031d0fd  mov     rax, [rax]
0x14031d100  call    _guard_dispatch_icall
0x14031d105  mov     eax, esi
0x14031d107  lock xadd [rbx+0Ch], eax
0x14031d10c  add     eax, esi
0x14031d10e  jnz     short loc_14031D120
0x14031d110  mov     rax, [rbx]
0x14031d113  mov     rcx, rbx
0x14031d116  mov     rax, [rax+8]
0x14031d11a  call    _guard_dispatch_icall
0x14031d11f  nop
0x14031d120  mov     rbx, qword ptr [rsp+758h+var_588+8]
0x14031d128  test    rbx, rbx
0x14031d12b  jz      short loc_14031D160
0x14031d12d  mov     eax, esi
0x14031d12f  lock xadd [rbx+8], eax
0x14031d134  add     eax, esi
0x14031d136  jnz     short loc_14031D160
0x14031d138  mov     rax, [rbx]
0x14031d13b  mov     rcx, rbx
0x14031d13e  mov     rax, [rax]
0x14031d141  call    _guard_dispatch_icall
0x14031d146  mov     eax, esi
0x14031d148  lock xadd [rbx+0Ch], eax
0x14031d14d  add     eax, esi
0x14031d14f  jnz     short loc_14031D160
0x14031d151  mov     rax, [rbx]
0x14031d154  mov     rcx, rbx
0x14031d157  mov     rax, [rax+8]
0x14031d15b  call    _guard_dispatch_icall
0x14031d160  mov     al, [rsp+758h+var_140]
0x14031d167  test    al, al
0x14031d169  jz      loc_14031E1D7
0x14031d16f  xorps   xmm0, xmm0
0x14031d172  movups  [rsp+758h+var_238], xmm0
0x14031d17a  mov     [rsp+758h+var_228], rdi
0x14031d182  mov     [rsp+758h+var_220], 7
0x14031d18e  mov     word ptr [rsp+758h+var_238], di
0x14031d196  cmp     [rsp+758h+var_148], 2
0x14031d19e  jnz     loc_14031F5EB
0x14031d1a4  lea     rdx, [rsp+758h+var_168]
0x14031d1ac  lea     rcx, [rsp+758h+var_238]; void *
0x14031d1b4  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14031d1b9  xorps   xmm0, xmm0
0x14031d1bc  xor     eax, eax
0x14031d1be  movups  [rsp+758h+var_1A0], xmm0
0x14031d1c6  mov     [rsp+758h+var_190], rax
0x14031d1ce  lea     rdx, [rsp+758h+var_238]
0x14031d1d6  lea     rcx, [rsp+758h+var_5C8]
0x14031d1de  call    ?parse@value@json@web@@SA?AV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::parse(std::wstring const &)
0x14031d1e3  nop
0x14031d1e4  mov     rcx, [rax]
0x14031d1e7  mov     rax, [rcx]
0x14031d1ea  mov     rax, [rax+98h]
0x14031d1f1  call    _guard_dispatch_icall
0x14031d1f6  mov     rdx, rax
0x14031d1f9  lea     rcx, [rsp+758h+var_1A0]
0x14031d201  call    ??0?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<web::json::value>::vector<web::json::value>(std::vector<web::json::value> const &)
0x14031d206  nop
0x14031d207  mov     rcx, [rsp+758h+var_5C8]
0x14031d20f  test    rcx, rcx
0x14031d212  jz      short loc_14031D228
0x14031d214  mov     rax, [rcx]
0x14031d217  mov     edx, 1
0x14031d21c  mov     rax, [rax+0C0h]
0x14031d223  call    _guard_dispatch_icall
0x14031d228  mov     rbx, qword ptr [rsp+758h+var_1A0]
0x14031d230  mov     rax, qword ptr [rsp+758h+var_1A0+8]
0x14031d238  mov     qword ptr [rsp+758h+var_608], rax
0x14031d240  lea     r12, asc_140415FC0; "{}_{}"
0x14031d247  mov     qword ptr [rsp+758h+var_628], rbx
0x14031d24f  cmp     rbx, qword ptr [rsp+758h+var_608]
0x14031d257  jz      loc_14031E18C
0x14031d25d  mov     [rsp+758h+var_248], rdi
0x14031d265  lea     rcx, [rsp+758h+var_248]; this
0x14031d26d  call    ??0value@json@web@@QEAA@XZ; web::json::value::value(void)
0x14031d272  nop
0x14031d273  mov     rcx, rbx
0x14031d276  call    ?has_duplicates_or_unknowns@Json@Windows@@YA_NAEBVvalue@json@web@@AEBV?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Ucase_insensitive_less@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@Z; Windows::Json::has_duplicates_or_unknowns(web::json::value const &,std::set<std::wstring,case_insensitive_less,std::allocator<std::wstring>> const &)
0x14031d27b  test    al, al
0x14031d27d  jz      loc_14031D43D
0x14031d283  lea     rcx, [rsp+758h+var_468]
0x14031d28b  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x14031d290  nop
0x14031d291  mov     rdx, [rax]
0x14031d294  mov     rax, [rdx+8]
0x14031d298  movsxd  rcx, dword ptr [rax+4]
0x14031d29c  add     rdx, 8
0x14031d2a0  add     rcx, rdx
0x14031d2a3  mov     rax, [rcx]
0x14031d2a6  lea     rdx, [rsp+758h+var_588]
0x14031d2ae  mov     rax, [rax+68h]
0x14031d2b2  call    _guard_dispatch_icall
0x14031d2b7  nop
0x14031d2b8  mov     r14, [rax]
0x14031d2bb  mov     rax, [r14]
0x14031d2be  mov     r12, [rax+0B0h]
0x14031d2c5  xor     r8d, r8d
0x14031d2c8  lea     r11, word_14047F67E
0x14031d2cf  mov     rdx, r11
0x14031d2d2  lea     rcx, aFoundDuplicate; "Found duplicate/unknown keys in Expedit"...
0x14031d2d9  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x14031d2de  cmp     rax, r11
0x14031d2e1  jz      loc_14031F5CB
0x14031d2e7  lea     rcx, aFoundDuplicate; "Found duplicate/unknown keys in Expedit"...
0x14031d2ee  sub     rax, rcx
0x14031d2f1  sar     rax, 1
0x14031d2f4  cmp     rax, rsi
0x14031d2f7  jz      loc_14031F5CB
0x14031d2fd  mov     qword ptr [rsp+758h+var_618], rcx
0x14031d305  mov     qword ptr [rsp+758h+var_618+8], rax
0x14031d30d  mov     rcx, [rbx]
0x14031d310  mov     rax, [rcx]
0x14031d313  lea     rdx, [rsp+758h+var_6C8]
0x14031d31b  mov     rax, [rax+50h]
0x14031d31f  call    _guard_dispatch_icall
0x14031d324  bts     r15d, 0Ah
0x14031d329  mov     [rsp+758h+var_728], r15d
0x14031d32e  lea     rdx, [rsp+758h+var_6C8]
0x14031d336  cmp     qword ptr [rsp+758h+var_6B8+8], 7
0x14031d33f  cmova   rdx, qword ptr [rsp+758h+var_6C8]
0x14031d348  mov     qword ptr [rsp+758h+var_5E8], rdx
0x14031d350  mov     rdx, qword ptr [rsp+758h+var_6B8]
0x14031d358  mov     qword ptr [rsp+758h+var_5E8+8], rdx
0x14031d360  movups  xmm0, [rsp+758h+var_618]
0x14031d368  movdqu  [rsp+758h+var_6D8], xmm0
0x14031d371  movaps  xmm1, [rsp+758h+var_5E8]
0x14031d379  movdqa  [rsp+758h+var_688], xmm1
0x14031d382  lea     r8, [rsp+758h+var_6D8]
0x14031d38a  lea     rdx, [rsp+758h+var_688]
0x14031d392  mov     rcx, r14
0x14031d395  mov     rax, r12
0x14031d398  call    _guard_dispatch_icall
0x14031d39d  nop
0x14031d39e  lea     rcx, [rsp+758h+var_6C8]
0x14031d3a6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14031d3ab  nop
0x14031d3ac  mov     r14, qword ptr [rsp+758h+var_588+8]
0x14031d3b4  test    r14, r14
0x14031d3b7  jz      short loc_14031D3EF
0x14031d3b9  mov     eax, esi
0x14031d3bb  lock xadd [r14+8], eax
0x14031d3c1  add     eax, esi
0x14031d3c3  jnz     short loc_14031D3EF
0x14031d3c5  mov     rax, [r14]
0x14031d3c8  mov     rcx, r14
0x14031d3cb  mov     rax, [rax]
0x14031d3ce  call    _guard_dispatch_icall
0x14031d3d3  mov     eax, esi
0x14031d3d5  lock xadd [r14+0Ch], eax
0x14031d3db  add     eax, esi
0x14031d3dd  jnz     short loc_14031D3EF
0x14031d3df  mov     rax, [r14]
0x14031d3e2  mov     rcx, r14
0x14031d3e5  mov     rax, [rax+8]
0x14031d3e9  call    _guard_dispatch_icall
0x14031d3ee  nop
0x14031d3ef  mov     r14, qword ptr [rsp+758h+var_468+8]
0x14031d3f7  test    r14, r14
0x14031d3fa  jz      short loc_14031D431
0x14031d3fc  mov     eax, esi
0x14031d3fe  lock xadd [r14+8], eax
0x14031d404  add     eax, esi
0x14031d406  jnz     short loc_14031D431
0x14031d408  mov     rax, [r14]
0x14031d40b  mov     rcx, r14
0x14031d40e  mov     rax, [rax]
0x14031d411  call    _guard_dispatch_icall
0x14031d416  mov     eax, esi
0x14031d418  lock xadd [r14+0Ch], eax
0x14031d41e  add     eax, esi
0x14031d420  jnz     short loc_14031D431
0x14031d422  mov     rax, [r14]
0x14031d425  mov     rcx, r14
0x14031d428  mov     rax, [rax+8]
0x14031d42c  call    _guard_dispatch_icall
0x14031d431  lea     r12, asc_140415FC0; "{}_{}"
0x14031d438  mov     r14, [rsp+758h+var_708]
0x14031d43d  mov     rdx, rbx
0x14031d440  lea     rcx, [rsp+758h+var_678]
0x14031d448  call    ?normalize_keys@Json@Windows@@YA?AVvalue@json@web@@AEBV345@AEBV?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Ucase_insensitive_less@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@Z; Windows::Json::normalize_keys(web::json::value const &,std::set<std::wstring,case_insensitive_less,std::allocator<std::wstring>> const &)
0x14031d44d  lea     rcx, [rsp+758h+var_248]
0x14031d455  cmp     rcx, rax
0x14031d458  jz      short loc_14031D470
0x14031d45a  mov     rdx, [rsp+758h+var_248]
0x14031d462  mov     rcx, [rax]
0x14031d465  mov     [rsp+758h+var_248], rcx
0x14031d46d  mov     [rax], rdx
0x14031d470  mov     rcx, qword ptr [rsp+758h+var_678]
0x14031d478  test    rcx, rcx
0x14031d47b  jz      short loc_14031D491
0x14031d47d  mov     rax, [rcx]
0x14031d480  mov     edx, 1
0x14031d485  mov     rax, [rax+0C0h]
0x14031d48c  call    _guard_dispatch_icall
0x14031d491  lea     rdx, [rsp+758h+var_248]; struct web::json::value *
0x14031d499  mov     rcx, r14; this
0x14031d49c  call    ?ValidateExpeditedJson@LegacyUOProvider@UO@Windows@@AEAA_NAEBVvalue@json@web@@@Z; Windows::UO::LegacyUOProvider::ValidateExpeditedJson(web::json::value const &)
0x14031d4a1  test    al, al
0x14031d4a3  jnz     loc_14031D628
0x14031d4a9  lea     rcx, [rsp+758h+var_458]
0x14031d4b1  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x14031d4b6  nop
0x14031d4b7  mov     rdx, [rax]
0x14031d4ba  mov     rax, [rdx+8]
0x14031d4be  movsxd  rcx, dword ptr [rax+4]
0x14031d4c2  add     rdx, 8
0x14031d4c6  add     rcx, rdx
0x14031d4c9  mov     rax, [rcx]
0x14031d4cc  lea     rdx, [rsp+758h+var_478]
0x14031d4d4  mov     rax, [rax+68h]
0x14031d4d8  call    _guard_dispatch_icall
0x14031d4dd  nop
0x14031d4de  mov     r14, [rax]
0x14031d4e1  mov     rax, [r14]
0x14031d4e4  mov     r12, [rax+98h]
0x14031d4eb  mov     rcx, [rsp+758h+var_248]
0x14031d4f3  mov     rax, [rcx]
0x14031d4f6  lea     rdx, [rsp+758h+var_6C8]
0x14031d4fe  mov     rax, [rax+50h]
0x14031d502  call    _guard_dispatch_icall
0x14031d507  bts     r15d, 9
0x14031d50c  mov     [rsp+758h+var_728], r15d
0x14031d511  lea     rdx, [rsp+758h+var_6C8]
0x14031d519  cmp     qword ptr [rsp+758h+var_6B8+8], 7
0x14031d522  cmova   rdx, qword ptr [rsp+758h+var_6C8]
0x14031d52b  mov     qword ptr [rsp+758h+var_568], rdx
0x14031d533  mov     rdx, qword ptr [rsp+758h+var_6B8]
0x14031d53b  mov     qword ptr [rsp+758h+var_568+8], rdx
0x14031d543  movaps  xmm0, [rsp+758h+var_568]
0x14031d54b  movdqa  [rsp+758h+var_6D8], xmm0
0x14031d554  lea     rdx, [rsp+758h+var_6D8]
0x14031d55c  mov     rcx, r14
0x14031d55f  mov     rax, r12
  ... truncated ...
```
