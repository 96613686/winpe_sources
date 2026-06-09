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
  __int64 v10; // rdx
  volatile signed __int32 *v11; // rbx
  volatile signed __int32 *v12; // rbx
  char v13; // al
  _QWORD *v14; // rax
  __int64 v15; // rax
  _QWORD *i; // rbx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // r14
  void (__fastcall *v21)(__int64, __int128 *, __int128 *); // r12
  __int64 v22; // rax
  const char *v23; // r9
  __int64 v24; // r11
  __int64 v25; // rax
  __int128 *v26; // rdx
  __int64 v27; // rdx
  volatile signed __int32 *v28; // r14
  volatile signed __int32 *v29; // r14
  __int64 *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rax
  __int64 v35; // r14
  void (__fastcall *v36)(__int64, __int128 *); // r12
  __int128 *v37; // rdx
  __int64 v38; // rdx
  const char *v39; // r9
  volatile signed __int32 *v40; // r14
  volatile signed __int32 *v41; // r14
  _QWORD *v42; // rax
  _QWORD *v43; // rax
  __int64 v44; // rdx
  __int64 v45; // rdx
  _QWORD *v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rax
  __int64 v49; // rcx
  __int64 v50; // rax
  __int64 v51; // r14
  __int64 (__fastcall *v52)(__int64, __int128 *, __int128 *); // r12
  __int64 v53; // rax
  __int64 v54; // rax
  __int128 *v55; // rax
  __int64 v56; // rdx
  char v57; // r12
  __int64 v58; // rdx
  __int64 v59; // rdx
  __int64 v60; // rdx
  volatile signed __int32 *v61; // r14
  volatile signed __int32 *v62; // r14
  __int64 v63; // rax
  __int64 v64; // rcx
  __int64 v65; // rax
  __int64 v66; // r14
  void (__fastcall *v67)(__int64, _QWORD *, __int128 *, __int128 *, __int128 *); // r12
  __int128 v68; // xmm6
  __int64 v69; // rax
  _QWORD *v70; // rax
  __int64 v71; // rcx
  __int64 v72; // rax
  __int64 v73; // rdx
  __int64 v74; // rdx
  __int64 v75; // rdx
  __int64 v76; // rdx
  __int64 v77; // rdx
  _QWORD *v78; // rax
  __int64 v79; // r9
  __int64 v80; // rax
  __int64 v81; // rcx
  __int64 v82; // rax
  __int64 v83; // rcx
  void (__fastcall *v84)(__int64, __int128 *, __int128 *); // r9
  _QWORD *v85; // rax
  _QWORD *v86; // rdx
  __int64 v87; // rax
  __int64 v88; // rcx
  __int64 v89; // rax
  __int64 v90; // r14
  void (__fastcall *v91)(__int64, __int128 *, __int128 *, __int128 *, _QWORD *); // r12
  __int128 v92; // xmm6
  __int64 v93; // rax
  _QWORD *v94; // rax
  __int64 v95; // rcx
  __int64 v96; // rax
  __int64 v97; // rdx
  __int64 v98; // rdx
  __int64 v99; // rdx
  __int64 v100; // rdx
  __int64 v101; // rax
  __int64 v102; // rdx
  _QWORD *v103; // rax
  __int64 v104; // rdx
  __int64 v105; // rdx
  const char *v106; // r9
  int v107; // r15d
  __int64 v108; // rdx
  struct std::error_code *v109; // r8
  bool v110; // al
  const struct std::filesystem::path *v111; // rdx
  const struct std::filesystem::path *v112; // r9
  __int64 v113; // rax
  __int128 v114; // xmm1
  __int64 v115; // rdx
  _QWORD *v116; // rbx
  __int64 v117; // rdx
  int *v118; // rax
  const char *v119; // r9
  __int64 v120; // rax
  _QWORD *v121; // rcx
  __int128 *v122; // rax
  char v123; // r14
  _QWORD *v124; // r12
  __int64 v125; // rax
  __int64 v126; // rcx
  __int64 v127; // rax
  __int64 v128; // rbx
  void (__fastcall *v129)(__int64, __int128 *, __int128 *); // r14
  wchar_t *v130; // rax
  const char *v131; // r9
  __int64 v132; // r11
  __int64 v133; // rax
  __int128 *v134; // rdx
  __int64 v135; // rdx
  volatile signed __int32 *v136; // rbx
  volatile signed __int32 *v137; // rbx
  __int64 v138; // rax
  __int64 v139; // rdx
  __int64 v140; // rax
  __int64 v141; // rcx
  __int64 v142; // rax
  __int64 v143; // rbx
  void (__fastcall *v144)(__int64, __int128 *, __int128 *); // r14
  __int128 v145; // xmm6
  _QWORD *v146; // rax
  __int64 v147; // rcx
  __int64 v148; // rdx
  __int64 *v149; // rax
  __int64 v150; // rdx
  int v151; // r15d
  __int64 v152; // rdx
  __int64 v153; // rdx
  __int64 v154; // rax
  __int64 v155; // rcx
  __int64 v156; // rax
  __int64 v157; // rbx
  void (__fastcall *v158)(__int64, __int128 *); // r14
  __int128 *v159; // rdx
  __int64 v160; // rdx
  _QWORD *v161; // rax
  _QWORD *v162; // rax
  __int64 v163; // rdx
  __int64 v164; // rdx
  __int64 v165; // rax
  __int64 v166; // rcx
  __int64 v167; // rax
  __int64 v168; // rbx
  __int64 (__fastcall *v169)(__int64, __int128 *, __int128 *); // r14
  __int64 v170; // rax
  _QWORD *v171; // rax
  __int64 v172; // rcx
  __int64 v173; // rdx
  char v174; // bl
  __int64 v175; // rdx
  __int64 v176; // rdx
  __int64 v177; // rdx
  __int64 v178; // rdx
  __int128 *v179; // rax
  Windows::UO::LegacyUOProvider *v180; // rbx
  __int64 v181; // rax
  __int64 v182; // rcx
  __int64 v183; // rax
  __int64 v184; // rcx
  void (__fastcall *v185)(__int64, __int128 *, __int128 *); // r9
  _QWORD *v186; // rax
  __int128 *v187; // rdx
  _QWORD *v188; // rax
  int v189; // ebx
  __int64 v190; // rdx
  __int64 v191; // rax
  __int64 v192; // rcx
  __int64 v193; // rax
  __int64 v194; // r14
  void (__fastcall *v195)(__int64, __int128 *, __int128 *, __int128 *, __int128 *); // r12
  __int128 v196; // xmm6
  __int64 v197; // rax
  _QWORD *v198; // rax
  __int64 v199; // rcx
  __int64 v200; // rax
  __int64 v201; // rdx
  __int64 v202; // rdx
  __int64 v203; // rdx
  __int64 v204; // rdx
  __int64 v205; // rax
  __int64 v206; // rdx
  __int128 *v207; // rax
  __int64 v208; // rdx
  unsigned int v209; // eax
  volatile signed __int32 *v210; // rbx
  volatile signed __int32 *v211; // rbx
  volatile signed __int32 *v212; // rbx
  __int64 v213; // rax
  __int64 v214; // rax
  __int64 v215; // rbx
  void (__fastcall *v216)(__int64, __int128 *, __int128 *); // rdi
  _QWORD *ExceptionMessage; // rax
  __int64 v218; // rcx
  _QWORD *v219; // rax
  __int64 v220; // rcx
  __int64 v221; // rdx
  __int64 v222; // rdx
  __int64 v223; // rax
  __int64 v224; // rax
  __int64 v225; // rbx
  void (__fastcall *v226)(__int64, __int128 *, __int128 *); // rdi
  _QWORD *v227; // rax
  __int64 v228; // rcx
  __int128 *v229; // rdx
  __int64 v230; // rdx
  int v231; // [rsp+30h] [rbp-728h]
  __int128 v232; // [rsp+40h] [rbp-718h] BYREF
  Windows::UO::LegacyUOProvider *v233; // [rsp+50h] [rbp-708h]
  __int64 v234; // [rsp+58h] [rbp-700h] BYREF
  __int128 v235; // [rsp+60h] [rbp-6F8h] BYREF
  __int64 v236; // [rsp+70h] [rbp-6E8h]
  __int64 v237; // [rsp+78h] [rbp-6E0h]
  __int128 v238; // [rsp+80h] [rbp-6D8h] BYREF
  __int128 v239; // [rsp+90h] [rbp-6C8h] BYREF
  __int128 v240; // [rsp+A0h] [rbp-6B8h]
  __int128 v241; // [rsp+B0h] [rbp-6A8h] BYREF
  Windows::UO::LegacyUOProvider *v242; // [rsp+C0h] [rbp-698h]
  __int128 v243; // [rsp+D0h] [rbp-688h] BYREF
  char v244[8]; // [rsp+E0h] [rbp-678h] BYREF
  void ***v245; // [rsp+E8h] [rbp-670h]
  __int128 v246; // [rsp+F0h] [rbp-668h] BYREF
  __int64 v247; // [rsp+100h] [rbp-658h]
  unsigned __int64 v248; // [rsp+108h] [rbp-650h]
  __int128 v249; // [rsp+110h] [rbp-648h] BYREF
  __int64 v250; // [rsp+120h] [rbp-638h]
  __int64 v251; // [rsp+128h] [rbp-630h]
  __int128 v252; // [rsp+130h] [rbp-628h] BYREF
  __int128 v253; // [rsp+140h] [rbp-618h] BYREF
  __int128 v254; // [rsp+150h] [rbp-608h] BYREF
  __int64 v255; // [rsp+160h] [rbp-5F8h]
  unsigned __int64 v256; // [rsp+168h] [rbp-5F0h]
  __int128 v257; // [rsp+170h] [rbp-5E8h] BYREF
  __int128 v258; // [rsp+180h] [rbp-5D8h]
  __int64 v259; // [rsp+190h] [rbp-5C8h] BYREF
  unsigned int v260; // [rsp+198h] [rbp-5C0h]
  __int128 v261; // [rsp+1A0h] [rbp-5B8h] BYREF
  __int64 v262; // [rsp+1B0h] [rbp-5A8h]
  __int64 v263; // [rsp+1B8h] [rbp-5A0h]
  char v264; // [rsp+1C0h] [rbp-598h]
  __int128 v265; // [rsp+1D0h] [rbp-588h] BYREF
  _BYTE v266[8]; // [rsp+1E0h] [rbp-578h] BYREF
  volatile signed __int32 *v267; // [rsp+1E8h] [rbp-570h]
  __int128 v268; // [rsp+1F0h] [rbp-568h]
  __int128 v269; // [rsp+200h] [rbp-558h]
  __int128 v270; // [rsp+210h] [rbp-548h]
  __int128 v271; // [rsp+220h] [rbp-538h]
  __int128 v272; // [rsp+230h] [rbp-528h]
  __int128 v273; // [rsp+240h] [rbp-518h]
  __int128 v274; // [rsp+250h] [rbp-508h]
  __int128 v275; // [rsp+260h] [rbp-4F8h]
  __int128 v276; // [rsp+270h] [rbp-4E8h]
  __int128 v277; // [rsp+280h] [rbp-4D8h]
  __int128 v278; // [rsp+290h] [rbp-4C8h]
  _BYTE v279[8]; // [rsp+2A0h] [rbp-4B8h] BYREF
  volatile signed __int32 *v280; // [rsp+2A8h] [rbp-4B0h]
  __int128 v281; // [rsp+2B0h] [rbp-4A8h]
  __int128 v282; // [rsp+2C0h] [rbp-498h] BYREF
  __int128 v283; // [rsp+2D0h] [rbp-488h]
  __int128 v284; // [rsp+2E0h] [rbp-478h] BYREF
  __int128 v285; // [rsp+2F0h] [rbp-468h] BYREF
  __int128 v286; // [rsp+300h] [rbp-458h] BYREF
  __int128 Src; // [rsp+310h] [rbp-448h] BYREF
  __int128 v288; // [rsp+320h] [rbp-438h]
  _BYTE v289[16]; // [rsp+330h] [rbp-428h] BYREF
  _BYTE v290[16]; // [rsp+340h] [rbp-418h] BYREF
  _BYTE v291[16]; // [rsp+350h] [rbp-408h] BYREF
  __int128 v292; // [rsp+360h] [rbp-3F8h] BYREF
  __int64 v293; // [rsp+370h] [rbp-3E8h]
  __int64 v294; // [rsp+378h] [rbp-3E0h]
  __int128 v295; // [rsp+380h] [rbp-3D8h] BYREF
  __int64 v296; // [rsp+390h] [rbp-3C8h]
  __int64 v297; // [rsp+398h] [rbp-3C0h]
  _BYTE v298[8]; // [rsp+3A0h] [rbp-3B8h] BYREF
  volatile signed __int32 *v299; // [rsp+3A8h] [rbp-3B0h]
  _BYTE v300[8]; // [rsp+3B0h] [rbp-3A8h] BYREF
  volatile signed __int32 *v301; // [rsp+3B8h] [rbp-3A0h]
  _BYTE v302[16]; // [rsp+3C0h] [rbp-398h] BYREF
  _BYTE v303[24]; // [rsp+3D0h] [rbp-388h] BYREF
  const std::exception *v304; // [rsp+3E8h] [rbp-370h] BYREF
  const std::exception *v305; // [rsp+3F0h] [rbp-368h] BYREF
  _QWORD v306[34]; // [rsp+400h] [rbp-358h] BYREF
  __int64 v307; // [rsp+510h] [rbp-248h] BYREF
  __int64 v308; // [rsp+518h] [rbp-240h] BYREF
  __int128 v309; // [rsp+520h] [rbp-238h] BYREF
  __int64 v310; // [rsp+530h] [rbp-228h]
  unsigned __int64 v311; // [rsp+538h] [rbp-220h]
  _QWORD v312[2]; // [rsp+540h] [rbp-218h] BYREF
  __int64 v313; // [rsp+550h] [rbp-208h]
  unsigned __int64 v314; // [rsp+558h] [rbp-200h]
  _QWORD v315[4]; // [rsp+560h] [rbp-1F8h] BYREF
  char v316; // [rsp+580h] [rbp-1D8h]
  char v317; // [rsp+588h] [rbp-1D0h]
  _QWORD v318[4]; // [rsp+590h] [rbp-1C8h] BYREF
  char v319; // [rsp+5B0h] [rbp-1A8h]
  __int128 v320; // [rsp+5B8h] [rbp-1A0h] BYREF
  __int64 v321; // [rsp+5C8h] [rbp-190h]
  _BYTE v322[32]; // [rsp+5D0h] [rbp-188h] BYREF
  _BYTE v323[32]; // [rsp+5F0h] [rbp-168h] BYREF
  char v324; // [rsp+610h] [rbp-148h]
  char v325; // [rsp+618h] [rbp-140h]
  _QWORD v326[32]; // [rsp+620h] [rbp-138h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+758h] [rbp+0h]

  v1 = this;
  v233 = this;
  v242 = this;
  v2 = 0;
  v231 = 0;
  System = SystemInterface::Providers::GetSystem(&v265);
  v4 = *(_QWORD *)System + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL);
  v5 = *(void (__fastcall **)(__int64, _BYTE *, __int128 *))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v4 + 40LL))(
                                                                            v4,
                                                                            &v243)
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
  *(_QWORD *)&v253 = L"UOExpeditedAppRegistrations";
  *((_QWORD *)&v253 + 1) = v9;
  v238 = v253;
  v5(v8, v323, &v238);
  v11 = (volatile signed __int32 *)*((_QWORD *)&v243 + 1);
  if ( *((_QWORD *)&v243 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v243 + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( !_InterlockedDecrement(v11 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  v12 = (volatile signed __int32 *)*((_QWORD *)&v265 + 1);
  if ( *((_QWORD *)&v265 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v265 + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( !_InterlockedDecrement(v12 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  v13 = v325;
  if ( v325 )
  {
    try
    {
      v309 = 0;
      v310 = 0;
      v311 = 7;
      LOWORD(v309) = 0;
      if ( v324 != 2 )
        std::_Throw_bad_variant_access();
      std::wstring::operator=(&v309);
      v320 = 0;
      v321 = 0;
      v14 = (_QWORD *)web::json::value::parse(&v259, &v309);
      v15 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 152LL))(*v14);
      std::vector<web::json::value>::vector<web::json::value>(&v320, v15);
      if ( v259 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v259 + 192LL))(v259, 1);
      *(_QWORD *)&v254 = *((_QWORD *)&v320 + 1);
      for ( i = (_QWORD *)v320; ; ++i )
      {
        *(_QWORD *)&v252 = i;
        if ( i == (_QWORD *)v254 )
        {
          std::vector<web::json::value>::_Tidy(&v320);
          goto LABEL_247;
        }
        try
        {
          v307 = 0;
          web::json::value::value((web::json::value *)&v307);
          if ( (unsigned __int8)Windows::Json::has_duplicates_or_unknowns(i) )
          {
            v17 = SystemInterface::Providers::GetSystem(&v285);
            v18 = *(_QWORD *)v17 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v17 + 8LL) + 4LL);
            v19 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v18 + 104LL))(v18, &v265);
            v20 = *(_QWORD *)v19;
            v21 = *(void (__fastcall **)(__int64, __int128 *, __int128 *))(**(_QWORD **)v19 + 176LL);
            v22 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                    L"Found duplicate/unknown keys in Expedited JSON",
                    &word_14047F67E,
                    0);
            if ( v22 == v24
              || (v25 = (v22 - (__int64)L"Found duplicate/unknown keys in Expedited JSON") >> 1, v25 == -1) )
            {
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0xC9,
                (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
                v23);
            }
            *(_QWORD *)&v253 = L"Found duplicate/unknown keys in Expedited JSON";
            *((_QWORD *)&v253 + 1) = v25;
            (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*i + 80LL))(*i, &v239);
            v2 |= 0x400u;
            v26 = &v239;
            if ( *((_QWORD *)&v240 + 1) > 7u )
              v26 = (__int128 *)v239;
            *(_QWORD *)&v257 = v26;
            *((_QWORD *)&v257 + 1) = v240;
            v238 = v253;
            v243 = v257;
            v21(v20, &v243, &v238);
            std::wstring::~wstring(&v239, v27);
            v28 = (volatile signed __int32 *)*((_QWORD *)&v265 + 1);
            if ( *((_QWORD *)&v265 + 1) )
            {
              if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v265 + 1) + 8LL)) )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
                if ( !_InterlockedDecrement(v28 + 3) )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
              }
            }
            v29 = (volatile signed __int32 *)*((_QWORD *)&v285 + 1);
            if ( *((_QWORD *)&v285 + 1) )
            {
              if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v285 + 1) + 8LL)) )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
                if ( !_InterlockedDecrement(v29 + 3) )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
              }
            }
            v1 = v233;
          }
          v30 = (__int64 *)Windows::Json::normalize_keys(v244, i);
          if ( &v307 != v30 )
          {
            v31 = v307;
            v307 = *v30;
            *v30 = v31;
          }
          if ( *(_QWORD *)v244 )
            (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v244 + 192LL))(*(_QWORD *)v244, 1);
          if ( !Windows::UO::LegacyUOProvider::ValidateExpeditedJson(v1, (const struct web::json::value *)&v307) )
          {
            v32 = SystemInterface::Providers::GetSystem(&v286);
            v33 = *(_QWORD *)v32 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v32 + 8LL) + 4LL);
            v34 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v33 + 104LL))(v33, &v284);
            v35 = *(_QWORD *)v34;
            v36 = *(void (__fastcall **)(__int64, __int128 *))(**(_QWORD **)v34 + 152LL);
            (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v307 + 80LL))(v307, &v239);
            v2 |= 0x200u;
            v231 = v2;
            v37 = &v239;
            if ( *((_QWORD *)&v240 + 1) > 7u )
              v37 = (__int128 *)v239;
            *(_QWORD *)&v268 = v37;
            *((_QWORD *)&v268 + 1) = v240;
            v238 = v268;
            v36(v35, &v238);
            std::wstring::~wstring(&v239, v38);
            v40 = (volatile signed __int32 *)*((_QWORD *)&v284 + 1);
            if ( *((_QWORD *)&v284 + 1) )
            {
              if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v284 + 1) + 8LL)) )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v40)(v40);
                if ( !_InterlockedDecrement(v40 + 3) )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
              }
            }
            v41 = (volatile signed __int32 *)*((_QWORD *)&v286 + 1);
            if ( *((_QWORD *)&v286 + 1) )
            {
              if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v286 + 1) + 8LL)) )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v41)(v41);
                if ( !_InterlockedDecrement(v41 + 3) )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v41 + 8LL))(v41);
              }
            }
            if ( v307 )
              goto LABEL_49;
LABEL_50:
            v1 = v233;
            continue;
          }
          v292 = 0;
          v293 = 0;
          v294 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v292, L"UpdaterName", 11);
          v42 = (_QWORD *)web::json::value::at(&v307, &v292);
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v42 + 176LL))(*v42);
          v295 = 0;
          v296 = 0;
          v297 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v295, L"OEMName", 7);
          v43 = (_QWORD *)web::json::value::at(&v307, &v295);
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v43 + 176LL))(*v43);
          *(_QWORD *)&v269 = L"{}_{}";
          *((_QWORD *)&v269 + 1) = 5;
          v238 = v269;
          std::format<std::wstring const &,std::wstring const &>(v312);
          std::wstring::~wstring(&v295, v44);
          std::wstring::~wstring(&v292, v45);
          v239 = 0;
          v240 = 0u;
          std::wstring::_Construct<1,wchar_t const *>(&v239, L"RegistrationVersion", 19);
          v46 = (_QWORD *)web::json::value::at(&v307, &v239);
          LODWORD(v234) = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v46 + 128LL))(*v46);
          std::wstring::~wstring(&v239, v47);
          v48 = SystemInterface::Providers::GetSystem(v300);
          v49 = *(_QWORD *)v48 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v48 + 8LL) + 4LL);
          v50 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v49 + 32LL))(v49, v298);
          v51 = *(_QWORD *)v50;
          v52 = *(__int64 (__fastcall **)(__int64, __int128 *, __int128 *))(**(_QWORD **)v50 + 8LL);
          v249 = 0;
          v250 = 0;
          v251 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v249, L"\\", 1);
          v53 = std::wstring::insert(&v249, 0, L"\\UScheduler", 11);
          Src = 0;
          v288 = 0u;
          Src = *(_OWORD *)v53;
          v288 = *(_OWORD *)(v53 + 16);
          *(_QWORD *)(v53 + 16) = 0;
          *(_QWORD *)(v53 + 24) = 7;
          *(_WORD *)v53 = 0;
          v54 = std::wstring::append(&Src);
          v239 = 0;
          v240 = 0u;
          v239 = *(_OWORD *)v54;
          v240 = *(_OWORD *)(v54 + 16);
          *(_QWORD *)(v54 + 16) = 0;
          *(_QWORD *)(v54 + 24) = 7;
          *(_WORD *)v54 = 0;
          v2 |= 0x1C0u;
          v231 = v2;
          v55 = &v239;
          if ( *((_QWORD *)&v240 + 1) > 7u )
            v55 = (__int128 *)v239;
          *(_QWORD *)&v281 = v55;
          *((_QWORD *)&v281 + 1) = v240;
          *(_QWORD *)&v283 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
          v56 = -1;
          do
            ++v56;
          while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v56] );
          *((_QWORD *)&v283 + 1) = v56;
          v238 = v281;
          v243 = v283;
          v57 = v52(v51, &v243, &v238);
          std::wstring::~wstring(&v239, v58);
          std::wstring::~wstring(&Src, v59);
          std::wstring::~wstring(&v249, v60);
          v61 = v299;
          if ( v299 )
          {
            if ( _InterlockedExchangeAdd(v299 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v61)(v61);
              if ( _InterlockedExchangeAdd(v61 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v61 + 8LL))(v61);
            }
          }
          v62 = v301;
          if ( v301 )
          {
            if ( _InterlockedExchangeAdd(v301 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v62)(v62);
              if ( _InterlockedExchangeAdd(v62 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 8LL))(v62);
            }
          }
          if ( v57 )
          {
            v63 = SystemInterface::Providers::GetSystem(v289);
            v64 = *(_QWORD *)v63 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v63 + 8LL) + 4LL);
            v65 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v64 + 32LL))(v64, v302);
            v66 = *(_QWORD *)v65;
            v67 = *(void (__fastcall **)(__int64, _QWORD *, __int128 *, __int128 *, __int128 *))(**(_QWORD **)v65 + 56LL);
            v68 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                               &v282,
                               L"updaterRegistrationVersion");
            v239 = 0;
            v240 = 0u;
            std::wstring::_Construct<1,wchar_t const *>(&v239, L"\\", 1);
            v2 |= 0x4000u;
            v231 = v2;
            v69 = std::operator+<wchar_t>(&v261, L"\\UScheduler", &v239);
            v70 = (_QWORD *)std::operator+<wchar_t>(&v235, v69, v312);
            v71 = v70[2];
            if ( v70[3] > 7u )
              v70 = (_QWORD *)*v70;
            *(_QWORD *)&v270 = v70;
            *((_QWORD *)&v270 + 1) = v71;
            *(_QWORD *)&v271 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
            v72 = -1;
            do
              ++v72;
            while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v72] );
            *((_QWORD *)&v271 + 1) = v72;
            v238 = v68;
            v243 = v270;
            v249 = v271;
            v67(v66, v315, &v249, &v243, &v238);
            std::wstring::~wstring(&v235, v73);
            std::wstring::~wstring(&v261, v74);
            std::wstring::~wstring(&v239, v75);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v302);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v289);
            if ( v317 && !v316 && (unsigned int)v234 <= LODWORD(v315[0]) )
            {
              *(_QWORD *)&v272 = L"Registration version for updater {} is less than or equal to the existing registration "
                                  "version. Skipping registration.";
              *((_QWORD *)&v272 + 1) = 118;
              v249 = v272;
              SystemInterface::Log<std::wstring>(&v249, v312);
              if ( v317 && v316 != -1 && v316 && v316 != 1 )
                std::wstring::~wstring(v315, v77);
              std::wstring::~wstring(v312, v77);
              if ( !v307 )
                goto LABEL_50;
              goto LABEL_49;
            }
            if ( v317 && v316 != -1 && v316 && v316 != 1 )
              std::wstring::~wstring(v315, v76);
          }
          v78 = v312;
          if ( v314 > 7 )
            v78 = (_QWORD *)v312[0];
          *(_QWORD *)&v273 = v78;
          *((_QWORD *)&v273 + 1) = v313;
          v249 = v273;
          v1 = v233;
          Windows::UO::LegacyUOProvider::PerformApplicabilityChecks(v233, v318, &v249, &v307);
          if ( v319 )
          {
            v80 = SystemInterface::Providers::GetSystem(v291);
            v81 = *(_QWORD *)v80 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v80 + 8LL) + 4LL);
            v82 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v81 + 104LL))(v81, v290);
            v83 = *(_QWORD *)v82;
            v84 = *(void (__fastcall **)(__int64, __int128 *, __int128 *))(**(_QWORD **)v82 + 144LL);
            if ( !v319 )
              std::_Throw_bad_optional_access();
            v85 = v318;
            if ( v318[3] > 7u )
              v85 = (_QWORD *)v318[0];
            *(_QWORD *)&v274 = v85;
            *((_QWORD *)&v274 + 1) = v318[2];
            v86 = v312;
            if ( v314 > 7 )
              v86 = (_QWORD *)v312[0];
            *(_QWORD *)&v275 = v86;
            *((_QWORD *)&v275 + 1) = v313;
            v249 = v274;
            v238 = v275;
            v84(v83, &v238, &v249);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v290);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v291);
            v87 = SystemInterface::Providers::GetSystem(v279);
            v88 = *(_QWORD *)v87 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v87 + 8LL) + 4LL);
            v89 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v88 + 32LL))(v88, v266);
            v90 = *(_QWORD *)v89;
            v91 = *(void (__fastcall **)(__int64, __int128 *, __int128 *, __int128 *, _QWORD *))(**(_QWORD **)v89 + 64LL);
            LODWORD(v315[0]) = v234;
            v316 = 0;
            v92 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                               v303,
                               L"updaterRegistrationVersion");
            v239 = 0;
            v240 = 0u;
            std::wstring::_Construct<1,wchar_t const *>(&v239, L"\\", 1);
            v2 |= 0x8000u;
            v231 = v2;
            v93 = std::operator+<wchar_t>(&v261, L"\\UScheduler", &v239);
            v94 = (_QWORD *)std::operator+<wchar_t>(&v235, v93, v312);
            v95 = v94[2];
            if ( v94[3] > 7u )
              v94 = (_QWORD *)*v94;
            *(_QWORD *)&v276 = v94;
            *((_QWORD *)&v276 + 1) = v95;
            *(_QWORD *)&v277 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
            v96 = -1;
            do
              ++v96;
            while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v96] );
            *((_QWORD *)&v277 + 1) = v96;
            v249 = v92;
            v238 = v276;
            v243 = v277;
            v91(v90, &v243, &v238, &v249, v315);
            std::wstring::~wstring(&v235, v97);
            std::wstring::~wstring(&v261, v98);
            std::wstring::~wstring(&v239, v99);
            if ( v316 != -1 && v316 && v316 != 1 )
              std::wstring::~wstring(v315, v100);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v266);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v279);
            v101 = std::wstring::wstring(&v235, v312);
            Windows::UO::ReportUOWorkCompleted(v101);
            if ( v319 )
              std::wstring::~wstring(v318, v102);
            std::wstring::~wstring(v312, v102);
            if ( !v307 )
              goto LABEL_50;
LABEL_49:
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v307 + 192LL))(v307, 1);
            goto LABEL_50;
          }
          v103 = v312;
          if ( v314 > 7 )
            v103 = (_QWORD *)v312[0];
          *(_QWORD *)&v278 = v103;
          *((_QWORD *)&v278 + 1) = v313;
          v249 = v278;
          LOBYTE(v79) = 1;
          Windows::UO::LegacyUOProvider::RegisterConfigBasedExpeditedApp(v1, &v249, &v307, v79);
          std::wstring::~wstring(v312, v104);
          if ( v307 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v307 + 192LL))(v307, 1);
        }
        catch ( const std::exception *v305 )
        {
          v213 = SystemInterface::Providers::GetSystem(&v232);
          v214 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)(*(int *)(*(_QWORD *)(*(_QWORD *)v213 + 8LL)
                                                                                     + 4LL)
                                                                            + *(_QWORD *)v213
                                                                            + 8LL)
                                                                + 104LL))(
                   *(_QWORD *)v213 + *(int *)(*(_QWORD *)(*(_QWORD *)v213 + 8LL) + 4LL) + 8LL,
                   &v246);
          v215 = *(_QWORD *)v214;
          v216 = *(void (__fastcall **)(__int64, __int128 *, __int128 *))(**(_QWORD **)v214 + 168LL);
          ExceptionMessage = (_QWORD *)Windows::UO::GetExceptionMessage(&v261, v305);
          v218 = ExceptionMessage[2];
          if ( ExceptionMessage[3] > 7u )
            ExceptionMessage = (_QWORD *)*ExceptionMessage;
          *(_QWORD *)&v258 = ExceptionMessage;
          *((_QWORD *)&v258 + 1) = v218;
          v219 = (_QWORD *)web::json::value::serialize(v252, &v235);
          v220 = v219[2];
          if ( v219[3] > 7u )
            v219 = (_QWORD *)*v219;
          *(_QWORD *)&v241 = v219;
          *((_QWORD *)&v241 + 1) = v220;
          v249 = v258;
          v238 = v241;
          v216(v215, &v238, &v249);
          std::wstring::~wstring(&v235, v221);
          std::wstring::~wstring(&v261, v222);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v246);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v232);
          v1 = v242;
          v233 = v242;
          v2 = v231;
          i = (_QWORD *)v252;
          continue;
        }
        catch ( ... )
        {
          wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x290,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\LegacyUOProvider.cpp",
            v39);
          v1 = v242;
          v233 = v242;
          v2 = v231;
          i = (_QWORD *)v252;
          continue;
        }
      }
    }
    catch ( const std::exception *v304 )
    {
      v223 = SystemInterface::Providers::GetSystem(v266);
      v224 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)(*(int *)(*(_QWORD *)(*(_QWORD *)v223 + 8LL) + 4LL)
                                                                     + *(_QWORD *)v223
                                                                     + 8LL)
                                                         + 104LL))(
               *(_QWORD *)v223 + *(int *)(*(_QWORD *)(*(_QWORD *)v223 + 8LL) + 4LL) + 8LL,
               v279);
      v225 = *(_QWORD *)v224;
      v226 = *(void (__fastcall **)(__int64, __int128 *, __int128 *))(**(_QWORD **)v224 + 160LL);
      v227 = (_QWORD *)Windows::UO::GetExceptionMessage(&v235, v304);
      v228 = v227[2];
      if ( v227[3] > 7u )
        v227 = (_QWORD *)*v227;
      *(_QWORD *)&v241 = v227;
      *((_QWORD *)&v241 + 1) = v228;
      v229 = &v309;
      if ( v311 > 7 )
        v229 = (__int128 *)v309;
      *(_QWORD *)&v258 = v229;
      *((_QWORD *)&v258 + 1) = v310;
      v232 = v241;
      v246 = v258;
      v226(v225, &v246, &v232);
      std::wstring::~wstring(&v235, v230);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v279);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v266);
      v233 = v242;
      goto LABEL_109;
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x29B,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\LegacyUOProvider.cpp",
        v106);
      v233 = v242;
LABEL_109:
      v2 = v231;
    }
LABEL_247:
    std::wstring::~wstring(&v309, v105);
    v13 = v325;
  }
  if ( v13 && v324 != -1 && v324 && v324 != 1 )
    std::wstring::~wstring(v323, v10);
  Windows::UO::GetConfigBasedRegistrationPath(v322);
  std::wstring::wstring(&v235, v322);
  v107 = v2 | 4;
  *(_QWORD *)&v241 = L"Searching for Config-based expedited updaters from: {}";
  *((_QWORD *)&v241 + 1) = 54;
  v232 = v241;
  SystemInterface::Log<std::wstring>(&v232, &v235);
  std::wstring::~wstring(&v235, v108);
  *(_QWORD *)v244 = 0;
  v245 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  v110 = std::filesystem::exists((std::filesystem *)v322, (const struct std::filesystem::path *)v244, v109);
  if ( *(_DWORD *)v244 )
    std::filesystem::_Throw_fs_error((std::filesystem *)"exists", v244, (const struct std::error_code *)v322, v112);
  if ( !v110 || !std::filesystem::is_directory((std::filesystem *)v322, v111) )
  {
    *(_QWORD *)&v238 = L"Config-based expedited updaters registration path does not exist or is not a directory";
    *((_QWORD *)&v238 + 1) = 86;
    v282 = v238;
    SystemInterface::Log<>(&v282);
    goto LABEL_223;
  }
  std::filesystem::recursive_directory_iterator::recursive_directory_iterator(
    (std::filesystem::recursive_directory_iterator *)&v257,
    (const struct std::filesystem::path *)v322);
  v252 = 0;
  v113 = *((_QWORD *)&v257 + 1);
  if ( *((_QWORD *)&v257 + 1) )
  {
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v257 + 1) + 8LL));
    v113 = *((_QWORD *)&v257 + 1);
  }
  v114 = v257;
  v252 = v257;
  v253 = 0;
  if ( v113 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v113 + 8));
    v114 = v257;
  }
  v241 = v114;
  std::filesystem::end(&v253, &v241);
  while ( 1 )
  {
    v116 = (_QWORD *)v252;
    if ( (_QWORD)v252 == (_QWORD)v253 )
      break;
    std::filesystem::directory_entry::_Get_any_status(v252, &v259, 3);
    v117 = v260;
    if ( v260 && (((_DWORD)v259 - 1) & 0xFFFFFFF7) != 0 )
      std::filesystem::_Throw_fs_error("directory_entry::status", v260, v116 + 4);
    if ( (_DWORD)v259 != 2 )
      goto LABEL_136;
    v118 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                    L".json",
                    &dword_14047FD1C,
                    0);
    if ( v118 == &dword_14047FD1C || (v120 = ((char *)v118 - (char *)L".json") >> 1, v120 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v119);
    *(_QWORD *)&v278 = L".json";
    *((_QWORD *)&v278 + 1) = v120;
    v121 = v116 + 4;
    if ( v116[7] > 7u )
      v121 = (_QWORD *)v116[4];
    *(_QWORD *)&v241 = v121;
    *((_QWORD *)&v241 + 1) = v116[6];
    v232 = v241;
    v258 = *(_OWORD *)std::filesystem::_Parse_extension(&v239, &v232);
    v232 = v258;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(&v235, &v232);
    std::wstring::wstring(&v309, &v235);
    v107 |= 0x3Bu;
    v122 = &v309;
    if ( v311 > 7 )
      v122 = (__int128 *)v309;
    *(_QWORD *)&v277 = v122;
    *((_QWORD *)&v277 + 1) = v310;
    v232 = v278;
    v246 = v277;
    if ( (unsigned __int8)Strings::iequals(&v246, &v232) )
      v123 = 1;
    else
LABEL_136:
      v123 = 0;
    if ( (v107 & 2) != 0 )
    {
      v107 &= ~2u;
      std::wstring::~wstring(&v309, v117);
    }
    if ( (v107 & 1) != 0 )
    {
      v107 &= ~1u;
      std::wstring::~wstring(&v235, v117);
    }
    if ( v123 )
    {
      memset(v306, 0, sizeof(v306));
      v124 = v116 + 4;
      std::wifstream::wifstream(v306, v116 + 4);
      if ( (*((_BYTE *)&v306[2] + *(int *)(v306[0] + 4LL)) & 6) == 0 )
      {
        memset(v326, 0, 0xF8u);
        std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v326);
        std::wostream::operator<<(&v326[2], &v306[2]);
        v234 = 0;
        v138 = std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(v326, &v235);
        web::json::value::parse(&v234, v138);
        std::wstring::~wstring(&v235, v139);
        v308 = 0;
        web::json::value::value((web::json::value *)&v308);
        if ( (unsigned __int8)Windows::Json::has_duplicates_or_unknowns(&v234) )
        {
          v140 = SystemInterface::Providers::GetSystem(v290);
          v141 = *(_QWORD *)v140 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v140 + 8LL) + 4LL);
          v142 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v141 + 104LL))(v141, v291);
          v143 = *(_QWORD *)v142;
          v144 = *(void (__fastcall **)(__int64, __int128 *, __int128 *))(**(_QWORD **)v142 + 176LL);
          v145 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                              v312,
                              L"Found duplicate/unknown keys in Expedited JSON");
          v146 = (_QWORD *)web::json::value::serialize(&v234, &v235);
          v147 = v146[2];
          if ( v146[3] > 7u )
            v146 = (_QWORD *)*v146;
          *(_QWORD *)&v274 = v146;
          *((_QWORD *)&v274 + 1) = v147;
          v232 = v145;
          v246 = v274;
          v144(v143, &v246, &v232);
          std::wstring::~wstring(&v235, v148);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v291);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v290);
        }
        v149 = (__int64 *)Windows::Json::normalize_keys(v244, &v234);
        if ( &v308 != v149 )
        {
          v150 = v308;
          v308 = *v149;
          *v149 = v150;
        }
        if ( *(_QWORD *)v244 )
          (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v244 + 192LL))(*(_QWORD *)v244, 1);
        (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v308 + 80LL))(v308, &v261);
        std::wstring::wstring(&v235, v124);
        v151 = v107 | 0x3000;
        *(_QWORD *)&v273 = L"Filename: {}, Content: {}";
        *((_QWORD *)&v273 + 1) = 25;
        v232 = v273;
        SystemInterface::Log<std::wstring,std::wstring>(&v232, &v235, &v261);
        std::wstring::~wstring(&v235, v152);
        std::wstring::~wstring(&v261, v153);
        if ( Windows::UO::LegacyUOProvider::ValidateExpeditedJson(v233, (const struct web::json::value *)&v308) )
        {
          v261 = 0;
          v262 = 0;
          v263 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v261, L"UpdaterName", 11);
          v161 = (_QWORD *)web::json::value::at(&v308, &v261);
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v161 + 176LL))(*v161);
          v254 = 0;
          v255 = 0;
          v256 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v254, L"OEMName", 7);
          v162 = (_QWORD *)web::json::value::at(&v308, &v254);
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v162 + 176LL))(*v162);
          *(_QWORD *)&v271 = L"{}_{}";
          *((_QWORD *)&v271 + 1) = 5;
          v232 = v271;
          std::format<std::wstring const &,std::wstring const &>(&v309);
          std::wstring::~wstring(&v254, v163);
          std::wstring::~wstring(&v261, v164);
          v165 = SystemInterface::Providers::GetSystem(v300);
          v166 = *(_QWORD *)v165 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v165 + 8LL) + 4LL);
          v167 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v166 + 32LL))(v166, &v249);
          v168 = *(_QWORD *)v167;
          v169 = *(__int64 (__fastcall **)(__int64, __int128 *, __int128 *))(**(_QWORD **)v167 + 8LL);
          v235 = 0;
          v236 = 0;
          v237 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v235, L"\\", 1);
          v107 = v151 | 0x10000;
          v170 = std::operator+<wchar_t>(v318, L"\\UScheduler", &v235);
          v171 = (_QWORD *)std::operator+<wchar_t>(v323, v170, &v309);
          v172 = v171[2];
          if ( v171[3] > 7u )
            v171 = (_QWORD *)*v171;
          *(_QWORD *)&v270 = v171;
          *((_QWORD *)&v270 + 1) = v172;
          *(_QWORD *)&v283 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
          v173 = -1;
          do
            ++v173;
          while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v173] );
          *((_QWORD *)&v283 + 1) = v173;
          v232 = v270;
          v246 = v283;
          v174 = v169(v168, &v246, &v232);
          std::wstring::~wstring(v323, v175);
          std::wstring::~wstring(v318, v176);
          std::wstring::~wstring(&v235, v177);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v249);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v300);
          if ( v174 )
          {
            *(_QWORD *)&v281 = L"Updater already exists: {}";
            *((_QWORD *)&v281 + 1) = 26;
            v232 = v281;
            SystemInterface::Log<std::wstring>(&v232, &v309);
            std::wstring::~wstring(&v309, v178);
            if ( v308 )
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v308 + 192LL))(v308, 1);
            if ( !v234 )
              goto LABEL_208;
          }
          else
          {
            v179 = &v309;
            if ( v311 > 7 )
              v179 = (__int128 *)v309;
            *(_QWORD *)&v269 = v179;
            *((_QWORD *)&v269 + 1) = v310;
            v232 = v269;
            v180 = v233;
            Windows::UO::LegacyUOProvider::PerformApplicabilityChecks(v233, v315, &v232, &v308);
            if ( v316 )
            {
              v181 = SystemInterface::Providers::GetSystem(&v292);
              v182 = *(_QWORD *)v181 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v181 + 8LL) + 4LL);
              v183 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v182 + 104LL))(v182, v298);
              v184 = *(_QWORD *)v183;
              v185 = *(void (__fastcall **)(__int64, __int128 *, __int128 *))(**(_QWORD **)v183 + 144LL);
              if ( !v316 )
                std::_Throw_bad_optional_access();
              v186 = v315;
              if ( v315[3] > 7u )
                v186 = (_QWORD *)v315[0];
              *(_QWORD *)&v268 = v186;
              *((_QWORD *)&v268 + 1) = v315[2];
              v187 = &v309;
              if ( v311 > 7 )
                v187 = (__int128 *)v309;
              *(_QWORD *)&v286 = v187;
              *((_QWORD *)&v286 + 1) = v310;
              v232 = v268;
              v246 = v286;
              v185(v184, &v246, &v232);
              std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v298);
              std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v292);
              v235 = 0;
              v236 = 0;
              v237 = 0;
              std::wstring::_Construct<1,wchar_t const *>(&v235, L"RegistrationVersion", 19);
              v188 = (_QWORD *)web::json::value::at(&v308, &v235);
              v189 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v188 + 128LL))(*v188);
              std::wstring::~wstring(&v235, v190);
              v191 = SystemInterface::Providers::GetSystem(&Src);
              v192 = *(_QWORD *)v191 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v191 + 8LL) + 4LL);
              v193 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v192 + 32LL))(v192, &v295);
              v194 = *(_QWORD *)v193;
              v195 = *(void (__fastcall **)(__int64, __int128 *, __int128 *, __int128 *, __int128 *))(**(_QWORD **)v193 + 64LL);
              LODWORD(v261) = v189;
              v264 = 0;
              v196 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                                  &v320,
                                  L"updaterRegistrationVersion");
              v235 = 0;
              v236 = 0;
              v237 = 0;
              std::wstring::_Construct<1,wchar_t const *>(&v235, L"\\", 1);
              v107 |= 0x40000u;
              v197 = std::operator+<wchar_t>(v323, L"\\UScheduler", &v235);
              v198 = (_QWORD *)std::operator+<wchar_t>(v318, v197, &v309);
              v199 = v198[2];
              if ( v198[3] > 7u )
                v198 = (_QWORD *)*v198;
              *(_QWORD *)&v284 = v198;
              *((_QWORD *)&v284 + 1) = v199;
              *(_QWORD *)&v285 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
              v200 = -1;
              do
                ++v200;
              while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v200] );
              *((_QWORD *)&v285 + 1) = v200;
              v232 = v196;
              v246 = v284;
              v254 = v285;
              v195(v194, &v254, &v246, &v232, &v261);
              std::wstring::~wstring(v318, v201);
              std::wstring::~wstring(v323, v202);
              std::wstring::~wstring(&v235, v203);
              if ( v264 != -1 && v264 && v264 != 1 )
                std::wstring::~wstring(&v261, v204);
              std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v295);
              std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&Src);
              v205 = std::wstring::wstring(v318, &v309);
              Windows::UO::ReportUOWorkCompleted(v205);
              if ( v316 )
                std::wstring::~wstring(v315, v206);
              std::wstring::~wstring(&v309, v206);
              if ( v308 )
                (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v308 + 192LL))(v308, 1);
              if ( !v234 )
                goto LABEL_208;
            }
            else
            {
              v207 = &v309;
              if ( v311 > 7 )
                v207 = (__int128 *)v309;
              *(_QWORD *)&v265 = v207;
              *((_QWORD *)&v265 + 1) = v310;
              v232 = v265;
              Windows::UO::LegacyUOProvider::RegisterConfigBasedExpeditedApp(v180, &v232, &v308, 0);
              std::wstring::~wstring(&v309, v208);
              if ( v308 )
                (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v308 + 192LL))(v308, 1);
              if ( !v234 )
                goto LABEL_208;
            }
          }
LABEL_207:
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v234 + 192LL))(v234, 1);
        }
        else
        {
          v154 = SystemInterface::Providers::GetSystem(v302);
          v155 = *(_QWORD *)v154 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v154 + 8LL) + 4LL);
          v156 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v155 + 104LL))(v155, v289);
          v157 = *(_QWORD *)v156;
          v158 = *(void (__fastcall **)(__int64, __int128 *))(**(_QWORD **)v156 + 152LL);
          std::wstring::wstring(&v246, v124);
          v107 = v151 | 0x20000;
          v159 = &v246;
          if ( v248 > 7 )
            v159 = (__int128 *)v246;
          *(_QWORD *)&v272 = v159;
          *((_QWORD *)&v272 + 1) = v247;
          v232 = v272;
          v158(v157, &v232);
          std::wstring::~wstring(&v246, v160);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v289);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v302);
          if ( v308 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v308 + 192LL))(v308, 1);
          if ( v234 )
            goto LABEL_207;
        }
LABEL_208:
        std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(&v326[19]);
        v326[19] = &std::wios::`vftable';
        std::ios_base::~ios_base((std::ios_base *)&v326[19]);
        std::wifstream::~wifstream<wchar_t,std::char_traits<wchar_t>>(&v306[22]);
        v306[22] = &std::wios::`vftable';
        std::ios_base::~ios_base((std::ios_base *)&v306[22]);
        goto LABEL_209;
      }
      v125 = SystemInterface::Providers::GetSystem(v266);
      v126 = *(_QWORD *)v125 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v125 + 8LL) + 4LL);
      v127 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v126 + 104LL))(v126, v279);
      v128 = *(_QWORD *)v127;
      v129 = *(void (__fastcall **)(__int64, __int128 *, __int128 *))(**(_QWORD **)v127 + 168LL);
      v130 = (wchar_t *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                          L"Failed to open file",
                          L"Filename: {}, Content: {}",
                          0);
      if ( v130 == L"Filename: {}, Content: {}" || (v133 = ((__int64)v130 - v132) >> 1, v133 == -1) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v131);
      *(_QWORD *)&v276 = v132;
      *((_QWORD *)&v276 + 1) = v133;
      std::wstring::wstring(&v254, v124);
      v107 |= 0x800u;
      v134 = &v254;
      if ( v256 > 7 )
        v134 = (__int128 *)v254;
      *(_QWORD *)&v275 = v134;
      *((_QWORD *)&v275 + 1) = v255;
      v232 = v276;
      v246 = v275;
      v129(v128, &v246, &v232);
      std::wstring::~wstring(&v254, v135);
      v136 = v280;
      if ( v280 )
      {
        if ( _InterlockedExchangeAdd(v280 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v136)(v136);
          if ( _InterlockedExchangeAdd(v136 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v136 + 8LL))(v136);
        }
      }
      v137 = v267;
      if ( v267 )
      {
        if ( _InterlockedExchangeAdd(v267 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v137)(v137);
          if ( _InterlockedExchangeAdd(v137 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v137 + 8LL))(v137);
        }
      }
      std::wifstream::~wifstream<wchar_t,std::char_traits<wchar_t>>(&v306[22]);
      v306[22] = &std::wios::`vftable';
      std::ios_base::~ios_base((std::ios_base *)&v306[22]);
    }
LABEL_209:
    v209 = std::filesystem::_Recursive_dir_enum_impl::_Advance_and_reset_if_no_more_files(&v252);
    if ( v209 )
      std::filesystem::_Throw_fs_error("recursive_directory_iterator::operator++", v209);
  }
  v210 = (volatile signed __int32 *)*((_QWORD *)&v253 + 1);
  if ( *((_QWORD *)&v253 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v253 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v210)(v210);
      if ( _InterlockedExchangeAdd(v210 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v210 + 8LL))(v210);
    }
  }
  v211 = (volatile signed __int32 *)*((_QWORD *)&v252 + 1);
  if ( *((_QWORD *)&v252 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v252 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v211)(v211);
      if ( _InterlockedExchangeAdd(v211 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v211 + 8LL))(v211);
    }
  }
  v212 = (volatile signed __int32 *)*((_QWORD *)&v257 + 1);
  if ( *((_QWORD *)&v257 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v257 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v212)(v212);
      if ( _InterlockedExchangeAdd(v212 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v212 + 8LL))(v212);
    }
  }
LABEL_223:
  std::wstring::~wstring(v322, v115);
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
