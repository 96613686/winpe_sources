# winrt::Windows::Management::Update::implementation::BuildUpdatePropertiesJsonString(winrt::hstring const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateInstallationType const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::Windows::Foundation::Uri const &,unsigned __int64,unsigned __int64,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateAppPackageInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateExecutionInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateOptionalInfo const &,winrt::Windows::Foundation::IReference<winrt::guid> const &,winrt::hstring const &)

- ea: `0x180019118`
- end: `0x18001cac0`
- name: `?BuildUpdatePropertiesJsonString@implementation@Update@Management@Windows@winrt@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUhstring@5@AEBW4WindowsSoftwareUpdateInstallationType@2345@000AEBUUri@Foundation@45@_K3AEBUWindowsSoftwareUpdateVersion@2345@4AEBUWindowsSoftwareUpdateAppPackageInfo@2345@AEBUWindowsSoftwareUpdateExecutionInfo@2345@AEBUWindowsSoftwareUpdateOptionalInfo@2345@AEBU?$IReference@Uguid@winrt@@@Foundation@45@0@Z`
- size: `14760`
- prototype: ``
- caller_count: `1`
- callee_count: `36`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001d150`

## callees

- `0x180002880`
- `0x1800035f0`
- `0x1800055f0`
- `0x180005610`
- `0x180005890`
- `0x180005930`
- `0x180006230`
- `0x180006aa0`
- `0x180006b10`
- `0x180006b80`
- `0x180006bf0`
- `0x180006fb0`
- `0x1800085f0`
- `0x180008bf4`
- `0x180008c0c`
- `0x180011ffc`
- `0x180012764`
- `0x180015ac0`
- `0x180017c3c`
- `0x1800188d4`
- `0x180018a14`
- `0x180018f10`
- `0x180018fc8`
- `0x180019118`
- `0x18001cac8`
- `0x18001cb24`
- `0x18001cb80`
- `0x18001d3c8`
- `0x18001d414`
- `0x18001d460`
- `0x18001d620`
- `0x18001d99c`
- `0x18001da30`
- `0x18001e7a4`
- `0x18001e9d0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180019ad6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001a4fc`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180019ad6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001a4fc`

## string_xrefs

- `0x18001c952`: `AppPackageInfo cannot be null for AppPackage installation type.`
- `0x18001c9e2`: `ExecutionInfo cannot be null for Executable or Powershell installation type.`
- `0x180019330`: `InstallationType`
- `0x180019403`: `UpdateId`
- `0x1800197cb`: `InstallSizeInBytes`
- `0x18001a880`: `InstallUri`
- `0x18001b01d`: `InstallInfo`
- `0x18001bbe8`: `CloseAndInstallInfo`
- `0x18001ca87`: `ComplianceDeadlineInDays must be a non-negative value less than or equal to 30 days.`
- `0x18001c6a4`: `ComplianceDeadlineInDays`
- `0x18001c90a`: `ComplianceGracePeriodInDays must be a non-negative value less than or equal to 7 days.`
- `0x18001c7e1`: `ComplianceGracePeriodInDays`

## pseudocode

```c
// Hidden C++ exception states: #wind=201
__int64 __fastcall winrt::Windows::Management::Update::implementation::BuildUpdatePropertiesJsonString(
        __int64 a1,
        __int64 a2,
        unsigned int *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7,
        __int64 a8,
        __int64 a9,
        _QWORD *a10,
        _QWORD *a11,
        __int64 *a12,
        _QWORD *a13,
        _QWORD *a14,
        __int64 *a15,
        __int64 a16)
{
  const unsigned __int16 *v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rax
  const unsigned __int16 *v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rbx
  __int64 v27; // rax
  const unsigned __int16 *v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rbx
  __int64 v31; // rax
  const unsigned __int16 *v32; // rdx
  __int64 v33; // r14
  __int64 v34; // r8
  __int64 v35; // rbx
  __int64 v36; // rax
  __int64 v37; // rax
  const unsigned __int16 *v38; // rdx
  __int64 v39; // r8
  __int64 v40; // rbx
  __int64 v41; // rax
  void *v42; // rbx
  int v43; // eax
  HANDLE ProcessHeap; // rax
  __int64 v45; // rbx
  __int64 v46; // rax
  __int64 v47; // rbx
  __int64 v48; // rax
  unsigned int v49; // eax
  __int64 v50; // rbx
  __int64 v51; // rax
  unsigned int v52; // eax
  __int64 v53; // rbx
  __int64 v54; // rax
  unsigned int v55; // eax
  __int64 v56; // rbx
  __int64 v57; // rax
  unsigned int v58; // eax
  __int64 v59; // rbx
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rcx
  __int64 v63; // rbx
  __int64 v64; // rax
  __int64 v65; // rbx
  __int64 v66; // rax
  __int64 v67; // rbx
  __int64 v68; // rax
  __int64 v69; // rbx
  __int64 v70; // rax
  __int64 v71; // rax
  _QWORD *v72; // rdi
  unsigned int v73; // eax
  __int64 v74; // rbx
  __int64 v75; // rax
  unsigned int v76; // eax
  __int64 v77; // rbx
  __int64 v78; // rax
  unsigned int v79; // eax
  __int64 v80; // rbx
  __int64 v81; // rax
  unsigned int v82; // eax
  __int64 v83; // rbx
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // rcx
  __int64 v87; // rbx
  __int64 v88; // rax
  __int64 v89; // rbx
  __int64 v90; // rax
  __int64 v91; // rbx
  __int64 v92; // rax
  __int64 v93; // rbx
  __int64 v94; // rax
  __int64 v95; // rax
  __int64 v96; // rcx
  int v97; // eax
  __int64 v98; // rax
  const unsigned __int16 *v99; // rdx
  __int64 v100; // r8
  __int64 v101; // rbx
  int v102; // esi
  __int64 v103; // rax
  void *v104; // rbx
  int v105; // eax
  HANDLE v106; // rax
  __int64 v107; // rdx
  __int64 v108; // r8
  __int64 v109; // rbx
  int v110; // esi
  __int64 v111; // rax
  __int64 *v112; // rdi
  __int64 v113; // rcx
  int v114; // eax
  const unsigned __int16 *v115; // rdx
  __int64 v116; // r8
  __int64 v117; // rbx
  __int64 v118; // rax
  __int64 v119; // rcx
  int v120; // eax
  __int64 v121; // rbx
  __int64 v122; // rax
  __int64 v123; // rbx
  __int64 v124; // rax
  __int64 v125; // rax
  const unsigned __int16 *v126; // rdx
  __int64 v127; // rbx
  __int64 v128; // rax
  __int64 v129; // rax
  __int64 v130; // rcx
  _QWORD *v131; // rdi
  __int64 v132; // rbx
  __int64 v133; // rax
  __int64 v134; // rax
  const unsigned __int16 *v135; // rdx
  __int64 v136; // r8
  __int64 v137; // rbx
  __int64 v138; // rax
  __int64 v139; // rax
  __int64 v140; // rax
  const unsigned __int16 *v141; // rdx
  __int64 v142; // r8
  __int64 v143; // rbx
  __int64 v144; // rax
  __int64 v145; // rax
  unsigned int v146; // eax
  __int64 v147; // rbx
  __int64 v148; // rax
  __int64 v149; // rax
  __int64 v150; // rbx
  __int64 v151; // rax
  __int64 v152; // rax
  const unsigned __int16 *v153; // rdx
  __int64 v154; // r8
  __int64 v155; // rbx
  __int64 v156; // rax
  __int64 v157; // rax
  __int64 v158; // rax
  const unsigned __int16 *v159; // rdx
  __int64 v160; // r8
  __int64 v161; // rbx
  __int64 v162; // rax
  __int64 v163; // rax
  unsigned int v164; // eax
  __int64 v165; // rbx
  __int64 v166; // rax
  __int64 v167; // rax
  __int64 v168; // rbx
  __int64 v169; // rax
  __int64 v170; // rax
  const unsigned __int16 *v171; // rdx
  __int64 v172; // r8
  __int64 v173; // rbx
  __int64 v174; // rax
  __int64 v175; // rax
  __int64 v176; // rax
  const unsigned __int16 *v177; // rdx
  __int64 v178; // r8
  __int64 v179; // rbx
  __int64 v180; // rax
  __int64 v181; // rax
  unsigned int v182; // eax
  __int64 v183; // rbx
  __int64 v184; // rax
  __int64 v185; // rax
  __int64 v186; // rbx
  __int64 v187; // rax
  __int64 v188; // rbx
  __int64 v189; // rax
  __int64 v190; // rax
  __int64 v191; // rax
  const unsigned __int16 *v192; // rdx
  __int64 v193; // r8
  __int64 v194; // rbx
  __int64 v195; // rax
  __int64 v196; // rax
  __int64 v197; // rax
  __int64 v198; // rax
  const unsigned __int16 *v199; // rdx
  __int64 v200; // r8
  __int64 v201; // rbx
  __int64 v202; // rax
  __int64 v203; // rax
  __int64 v204; // rax
  unsigned int v205; // eax
  __int64 v206; // rbx
  __int64 v207; // rax
  __int64 v208; // rax
  __int64 v209; // rax
  __int64 v210; // rbx
  __int64 v211; // rax
  __int64 v212; // rax
  __int64 v213; // rax
  const unsigned __int16 *v214; // rdx
  __int64 v215; // r8
  __int64 v216; // rbx
  __int64 v217; // rax
  __int64 v218; // rax
  __int64 v219; // rax
  __int64 v220; // rax
  const unsigned __int16 *v221; // rdx
  __int64 v222; // r8
  __int64 v223; // rbx
  __int64 v224; // rax
  __int64 v225; // rax
  __int64 v226; // rax
  unsigned int v227; // eax
  __int64 v228; // rbx
  __int64 v229; // rax
  __int64 v230; // rax
  __int64 v231; // rax
  __int64 v232; // rbx
  __int64 v233; // rax
  __int64 v234; // rax
  __int64 v235; // rax
  const unsigned __int16 *v236; // rdx
  __int64 v237; // r8
  __int64 v238; // rbx
  __int64 v239; // rax
  __int64 v240; // rax
  __int64 v241; // rax
  __int64 v242; // rax
  const unsigned __int16 *v243; // rdx
  __int64 v244; // rbx
  __int64 v245; // rax
  __int64 v246; // rax
  __int64 v247; // rax
  unsigned int v248; // eax
  __int64 v249; // rbx
  __int64 v250; // rax
  __int64 v251; // rax
  __int64 v252; // rax
  _QWORD *v253; // rdi
  int v254; // esi
  __int64 v255; // rax
  char v256; // bl
  __int64 v257; // rax
  unsigned int v258; // eax
  int v259; // r15d
  unsigned int v260; // r14d
  int v261; // r12d
  __int64 v262; // rbx
  int v263; // esi
  int v264; // eax
  unsigned int v265; // esi
  int v266; // eax
  __int64 v267; // rdi
  __int64 v268; // rax
  int v269; // eax
  int v270; // esi
  const unsigned __int16 *v271; // rdx
  __int64 v272; // rax
  __int64 v273; // rdi
  __int64 v274; // rax
  int v275; // eax
  const unsigned __int16 *v276; // rdx
  __int64 v277; // rax
  __int64 v278; // rdi
  __int64 v279; // rax
  __int64 v280; // rdi
  __int64 v281; // rax
  __int64 v282; // rax
  const unsigned __int16 *v283; // rdx
  __int64 v284; // rax
  __int64 v285; // rdi
  __int64 v286; // rax
  __int64 v287; // rax
  __int64 v288; // rax
  __int64 v289; // rbx
  __int64 v290; // rax
  __int64 v291; // rax
  char v292; // bl
  __int64 v293; // rax
  unsigned int v294; // eax
  __int64 v295; // rbx
  __int64 v296; // rax
  __int64 v297; // rbx
  __int64 v298; // rax
  __int16 v299; // si
  __int64 v300; // rax
  char v301; // bl
  __int64 v302; // rax
  unsigned int v303; // eax
  __int64 v304; // rbx
  __int64 v305; // rax
  __int64 v306; // rax
  __int64 v307; // rbx
  const struct winrt::impl::slim_source_location *v309; // rbx
  const struct winrt::impl::slim_source_location *v310; // rbx
  const struct winrt::impl::slim_source_location *v311; // rbx
  const struct winrt::impl::slim_source_location *v312; // rbx
  const struct winrt::impl::slim_source_location *v313; // rbx
  __int128 v314; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v315; // [rsp+38h] [rbp-C8h]
  __int64 v316; // [rsp+40h] [rbp-C0h]
  _QWORD v317[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v318; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v319; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v320; // [rsp+68h] [rbp-98h] BYREF
  int pExceptionObject; // [rsp+70h] [rbp-90h] BYREF
  __int128 v322; // [rsp+78h] [rbp-88h]
  __int64 v323; // [rsp+88h] [rbp-78h] BYREF
  __int64 v324; // [rsp+90h] [rbp-70h] BYREF
  _QWORD *v325; // [rsp+98h] [rbp-68h] BYREF
  __int64 v326; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v327; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v328; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v329; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v330; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v331; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int *v332; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD *v333; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v334; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v335; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v336; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD *v337; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v338; // [rsp+100h] [rbp+0h] BYREF
  __int64 v339; // [rsp+108h] [rbp+8h] BYREF
  __int64 v340; // [rsp+110h] [rbp+10h] BYREF
  __int64 v341; // [rsp+118h] [rbp+18h] BYREF
  __int64 v342; // [rsp+120h] [rbp+20h] BYREF
  __int64 *v343; // [rsp+128h] [rbp+28h] BYREF
  __int64 v344; // [rsp+130h] [rbp+30h] BYREF
  __int64 *v345; // [rsp+138h] [rbp+38h] BYREF
  _QWORD *v346; // [rsp+140h] [rbp+40h] BYREF
  __int64 v347; // [rsp+148h] [rbp+48h] BYREF
  __int64 v348; // [rsp+150h] [rbp+50h] BYREF
  __int64 v349; // [rsp+158h] [rbp+58h] BYREF
  __int64 v350; // [rsp+160h] [rbp+60h] BYREF
  __int64 v351; // [rsp+168h] [rbp+68h] BYREF
  __int64 v352; // [rsp+170h] [rbp+70h] BYREF
  _QWORD *v353; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v354[32]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v355; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v356; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v357; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v358; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v359; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v360; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 v361; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v362; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 v363; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v364; // [rsp+1E8h] [rbp+E8h] BYREF
  __int64 v365; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v366; // [rsp+1F8h] [rbp+F8h] BYREF
  __int64 v367; // [rsp+200h] [rbp+100h] BYREF
  __int64 v368; // [rsp+208h] [rbp+108h] BYREF
  __int64 v369; // [rsp+210h] [rbp+110h] BYREF
  __int64 v370; // [rsp+218h] [rbp+118h] BYREF
  __int64 v371; // [rsp+220h] [rbp+120h] BYREF
  __int64 v372; // [rsp+228h] [rbp+128h] BYREF
  __int64 v373; // [rsp+230h] [rbp+130h] BYREF
  __int64 v374; // [rsp+238h] [rbp+138h] BYREF
  __int64 v375; // [rsp+240h] [rbp+140h] BYREF
  __int64 v376; // [rsp+248h] [rbp+148h] BYREF
  __int64 v377; // [rsp+250h] [rbp+150h] BYREF
  __int64 v378; // [rsp+258h] [rbp+158h] BYREF
  __int64 v379; // [rsp+260h] [rbp+160h] BYREF
  __int64 v380; // [rsp+268h] [rbp+168h] BYREF
  __int64 v381; // [rsp+270h] [rbp+170h] BYREF
  __int64 v382; // [rsp+278h] [rbp+178h] BYREF
  __int64 v383; // [rsp+280h] [rbp+180h] BYREF
  __int64 v384; // [rsp+288h] [rbp+188h] BYREF
  __int64 v385; // [rsp+290h] [rbp+190h] BYREF
  __int64 v386; // [rsp+298h] [rbp+198h] BYREF
  __int64 v387; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int128 v388; // [rsp+2A8h] [rbp+1A8h] BYREF
  __int64 v389; // [rsp+2B8h] [rbp+1B8h]
  __int64 v390; // [rsp+2C0h] [rbp+1C0h]
  __int64 v391; // [rsp+2C8h] [rbp+1C8h] BYREF
  __int64 v392; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int64 v393; // [rsp+2D8h] [rbp+1D8h] BYREF
  __int64 v394; // [rsp+2E0h] [rbp+1E0h] BYREF
  __int64 v395; // [rsp+2E8h] [rbp+1E8h] BYREF
  __int64 v396; // [rsp+2F0h] [rbp+1F0h] BYREF
  __int64 v397; // [rsp+2F8h] [rbp+1F8h] BYREF
  __int64 v398; // [rsp+300h] [rbp+200h] BYREF
  __int64 v399; // [rsp+308h] [rbp+208h] BYREF
  __int64 v400; // [rsp+310h] [rbp+210h] BYREF
  __int64 v401; // [rsp+318h] [rbp+218h] BYREF
  __int64 v402; // [rsp+320h] [rbp+220h] BYREF
  __int64 v403; // [rsp+328h] [rbp+228h] BYREF
  __int64 v404; // [rsp+330h] [rbp+230h] BYREF
  __int64 v405; // [rsp+338h] [rbp+238h] BYREF
  LPVOID v406; // [rsp+340h] [rbp+240h] BYREF
  __int64 v407; // [rsp+348h] [rbp+248h] BYREF
  __int64 v408; // [rsp+350h] [rbp+250h] BYREF
  __int64 v409; // [rsp+358h] [rbp+258h] BYREF
  char v410[8]; // [rsp+360h] [rbp+260h] BYREF
  __int64 v411; // [rsp+368h] [rbp+268h] BYREF
  char v412[8]; // [rsp+370h] [rbp+270h] BYREF
  __int64 v413; // [rsp+378h] [rbp+278h] BYREF
  __int64 v414; // [rsp+380h] [rbp+280h] BYREF
  char v415[8]; // [rsp+388h] [rbp+288h] BYREF
  __int64 v416; // [rsp+390h] [rbp+290h] BYREF
  char v417[8]; // [rsp+398h] [rbp+298h] BYREF
  __int64 v418; // [rsp+3A0h] [rbp+2A0h] BYREF
  __int64 v419; // [rsp+3A8h] [rbp+2A8h] BYREF
  char v420[8]; // [rsp+3B0h] [rbp+2B0h] BYREF
  __int64 v421; // [rsp+3B8h] [rbp+2B8h] BYREF
  char v422[8]; // [rsp+3C0h] [rbp+2C0h] BYREF
  __int64 v423; // [rsp+3C8h] [rbp+2C8h] BYREF
  __int64 v424; // [rsp+3D0h] [rbp+2D0h] BYREF
  char v425[8]; // [rsp+3D8h] [rbp+2D8h] BYREF
  __int64 v426; // [rsp+3E0h] [rbp+2E0h] BYREF
  char v427[8]; // [rsp+3E8h] [rbp+2E8h] BYREF
  __int64 v428; // [rsp+3F0h] [rbp+2F0h] BYREF
  __int64 v429; // [rsp+3F8h] [rbp+2F8h] BYREF
  char v430[8]; // [rsp+400h] [rbp+300h] BYREF
  __int64 v431; // [rsp+408h] [rbp+308h] BYREF
  char v432[8]; // [rsp+410h] [rbp+310h] BYREF
  __int64 v433; // [rsp+418h] [rbp+318h] BYREF
  __int64 v434; // [rsp+420h] [rbp+320h] BYREF
  char v435[8]; // [rsp+428h] [rbp+328h] BYREF
  __int64 v436; // [rsp+430h] [rbp+330h] BYREF
  char v437[8]; // [rsp+438h] [rbp+338h] BYREF
  LPVOID lpMem; // [rsp+440h] [rbp+340h] BYREF
  __int64 v439; // [rsp+448h] [rbp+348h] BYREF
  __int64 v440; // [rsp+450h] [rbp+350h] BYREF
  __int64 v441; // [rsp+458h] [rbp+358h] BYREF
  __int64 v442; // [rsp+460h] [rbp+360h] BYREF
  char v443[8]; // [rsp+468h] [rbp+368h] BYREF
  __int64 v444; // [rsp+470h] [rbp+370h] BYREF
  __int64 v445; // [rsp+478h] [rbp+378h] BYREF
  __int64 v446; // [rsp+480h] [rbp+380h] BYREF
  __int64 v447; // [rsp+488h] [rbp+388h] BYREF
  __int64 v448; // [rsp+490h] [rbp+390h] BYREF
  __int64 v449; // [rsp+498h] [rbp+398h] BYREF
  __int64 v450; // [rsp+4A0h] [rbp+3A0h] BYREF
  __int64 v451; // [rsp+4A8h] [rbp+3A8h]
  _BYTE v452[24]; // [rsp+4B0h] [rbp+3B0h] BYREF
  __int128 v453; // [rsp+4C8h] [rbp+3C8h] BYREF
  __int64 v454; // [rsp+4D8h] [rbp+3D8h]
  __int64 v455; // [rsp+4E0h] [rbp+3E0h]
  __int128 v456; // [rsp+4E8h] [rbp+3E8h] BYREF
  __int64 v457; // [rsp+4F8h] [rbp+3F8h]
  __int64 v458; // [rsp+500h] [rbp+400h]
  __int128 v459; // [rsp+508h] [rbp+408h] BYREF
  __int64 v460; // [rsp+518h] [rbp+418h]
  __int64 v461; // [rsp+520h] [rbp+420h]
  __int128 v462; // [rsp+528h] [rbp+428h] BYREF
  __int64 v463; // [rsp+538h] [rbp+438h]
  __int64 v464; // [rsp+540h] [rbp+440h]
  __int128 v465; // [rsp+548h] [rbp+448h] BYREF
  __int64 v466; // [rsp+558h] [rbp+458h]
  __int64 v467; // [rsp+560h] [rbp+460h]
  int v468; // [rsp+568h] [rbp+468h] BYREF
  __int128 v469; // [rsp+570h] [rbp+470h]
  __int128 v470; // [rsp+580h] [rbp+480h] BYREF
  __int128 v471; // [rsp+590h] [rbp+490h]
  __int128 v472; // [rsp+5A0h] [rbp+4A0h] BYREF
  _OWORD v473[2]; // [rsp+5B0h] [rbp+4B0h] BYREF
  _OWORD v474[2]; // [rsp+5D0h] [rbp+4D0h] BYREF
  _OWORD v475[2]; // [rsp+5F0h] [rbp+4F0h] BYREF
  _OWORD v476[2]; // [rsp+610h] [rbp+510h] BYREF
  _OWORD v477[2]; // [rsp+630h] [rbp+530h] BYREF
  _OWORD v478[2]; // [rsp+650h] [rbp+550h] BYREF
  _OWORD v479[2]; // [rsp+670h] [rbp+570h] BYREF
  _OWORD v480[2]; // [rsp+690h] [rbp+590h] BYREF
  _OWORD v481[2]; // [rsp+6B0h] [rbp+5B0h] BYREF
  _OWORD v482[2]; // [rsp+6D0h] [rbp+5D0h] BYREF
  _OWORD v483[2]; // [rsp+6F0h] [rbp+5F0h] BYREF
  _OWORD v484[2]; // [rsp+710h] [rbp+610h] BYREF
  _OWORD v485[2]; // [rsp+730h] [rbp+630h] BYREF
  _OWORD v486[2]; // [rsp+750h] [rbp+650h] BYREF
  _OWORD v487[2]; // [rsp+770h] [rbp+670h] BYREF
  _OWORD v488[2]; // [rsp+790h] [rbp+690h] BYREF
  _OWORD v489[2]; // [rsp+7B0h] [rbp+6B0h] BYREF
  _OWORD v490[2]; // [rsp+7D0h] [rbp+6D0h] BYREF
  _OWORD v491[2]; // [rsp+7F0h] [rbp+6F0h] BYREF
  _OWORD v492[2]; // [rsp+810h] [rbp+710h] BYREF
  _OWORD v493[2]; // [rsp+830h] [rbp+730h] BYREF
  _OWORD v494[2]; // [rsp+850h] [rbp+750h] BYREF
  _OWORD v495[2]; // [rsp+870h] [rbp+770h] BYREF
  _OWORD v496[2]; // [rsp+890h] [rbp+790h] BYREF
  _OWORD v497[2]; // [rsp+8B0h] [rbp+7B0h] BYREF
  _OWORD v498[2]; // [rsp+8D0h] [rbp+7D0h] BYREF
  _OWORD v499[2]; // [rsp+8F0h] [rbp+7F0h] BYREF
  _OWORD v500[2]; // [rsp+910h] [rbp+810h] BYREF

  v332 = a3;
  v451 = a1;
  v326 = a1;
  v347 = a9;
  v346 = a11;
  v343 = a12;
  v320 = a13;
  v333 = a14;
  v345 = a15;
  v344 = a16;
  if ( !*(_QWORD *)a2 || !*(_QWORD *)a4 || !*(_QWORD *)a5 || !*(_QWORD *)a6 || !*a7 )
  {
    v311 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v452);
    winrt::param::hstring::hstring((winrt::param::hstring *)v354, L"Required parameters cannot be empty.");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)&pExceptionObject,
      (const struct winrt::param::hstring *)v354,
      v311);
    throw (winrt::hresult_invalid_argument *)&pExceptionObject;
  }
  if ( *a3 == 1 )
  {
    if ( !*a12 )
    {
      v310 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v452);
      winrt::param::hstring::hstring(
        (winrt::param::hstring *)v354,
        L"AppPackageInfo cannot be null for AppPackage installation type.");
      winrt::hresult_invalid_argument::hresult_invalid_argument(
        (winrt::hresult_invalid_argument *)&pExceptionObject,
        (const struct winrt::param::hstring *)v354,
        v310);
      throw (winrt::hresult_invalid_argument *)&pExceptionObject;
    }
  }
  else if ( *a3 - 2 <= 1 && !*a13 )
  {
    v312 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v452);
    winrt::param::hstring::hstring(
      (winrt::param::hstring *)v354,
      L"ExecutionInfo cannot be null for Executable or Powershell installation type.");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)&pExceptionObject,
      (const struct winrt::param::hstring *)v354,
      v312);
    throw (winrt::hresult_invalid_argument *)&pExceptionObject;
  }
  web::json::value::object(&v318, 0);
  if ( *(_QWORD *)a2 )
    v18 = *(const unsigned __int16 **)(*(_QWORD *)a2 + 16LL);
  else
    v18 = &dword_180030C44;
  v453 = 0;
  v454 = 0;
  v455 = 0;
  v19 = -1;
  do
    ++v19;
  while ( v18[v19] );
  std::wstring::_Construct<1,unsigned short const *>(&v453, v18, v19);
  v20 = web::json::value::string(&v351, &v453);
  memset(v473, 0, sizeof(v473));
  std::wstring::_Construct<1,unsigned short const *>(v473, L"ProviderId", 10);
  v21 = web::json::value::operator[](&v318, v473);
  web::json::value::operator=(v21, v20);
  std::wstring::_Tidy_deallocate(v473);
  if ( v351 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v351 + 192LL))(v351, 1);
  v22 = web::json::value::number(&v338, *v332);
  memset(v474, 0, sizeof(v474));
  std::wstring::_Construct<1,unsigned short const *>(v474, L"InstallationType", 16);
  v23 = web::json::value::operator[](&v318, v474);
  web::json::value::operator=(v23, v22);
  std::wstring::_Tidy_deallocate(v474);
  if ( v338 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v338 + 192LL))(v338, 1);
  if ( *(_QWORD *)a4 )
    v24 = *(const unsigned __int16 **)(*(_QWORD *)a4 + 16LL);
  else
    v24 = &dword_180030C44;
  v456 = 0;
  v457 = 0;
  v458 = 0;
  v25 = -1;
  do
    ++v25;
  while ( v24[v25] );
  std::wstring::_Construct<1,unsigned short const *>(&v456, v24, v25);
  v26 = web::json::value::string(&v350, &v456);
  memset(v475, 0, sizeof(v475));
  std::wstring::_Construct<1,unsigned short const *>(v475, L"UpdateId", 8);
  v27 = web::json::value::operator[](&v318, v475);
  web::json::value::operator=(v27, v26);
  std::wstring::_Tidy_deallocate(v475);
  if ( v350 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v350 + 192LL))(v350, 1);
  if ( *(_QWORD *)a5 )
    v28 = *(const unsigned __int16 **)(*(_QWORD *)a5 + 16LL);
  else
    v28 = &dword_180030C44;
  v388 = 0;
  v389 = 0;
  v390 = 0;
  v29 = -1;
  do
    ++v29;
  while ( v28[v29] );
  std::wstring::_Construct<1,unsigned short const *>(&v388, v28, v29);
  v30 = web::json::value::string(&v349, &v388);
  memset(v476, 0, sizeof(v476));
  std::wstring::_Construct<1,unsigned short const *>(v476, L"Title", 5);
  v31 = web::json::value::operator[](&v318, v476);
  web::json::value::operator=(v31, v30);
  std::wstring::_Tidy_deallocate(v476);
  if ( v349 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v349 + 192LL))(v349, 1);
  if ( *(_QWORD *)a6 )
    v32 = *(const unsigned __int16 **)(*(_QWORD *)a6 + 16LL);
  else
    v32 = &dword_180030C44;
  v314 = 0;
  v315 = 0;
  v316 = 0;
  v33 = -1;
  v34 = -1;
  do
    ++v34;
  while ( v32[v34] );
  std::wstring::_Construct<1,unsigned short const *>(&v314, v32, v34);
  v35 = web::json::value::string(&v348, &v314);
  v470 = 0;
  v471 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v470, L"Description", 11);
  v36 = web::json::value::operator[](&v318, &v470);
  web::json::value::operator=(v36, v35);
  std::wstring::_Tidy_deallocate(&v470);
  if ( v348 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v348 + 192LL))(v348, 1);
  v37 = winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::RawUri(
          a7,
          &lpMem);
  if ( *(_QWORD *)v37 )
    v38 = *(const unsigned __int16 **)(*(_QWORD *)v37 + 16LL);
  else
    v38 = &dword_180030C44;
  v459 = 0;
  v460 = 0;
  v461 = 0;
  v39 = -1;
  do
    ++v39;
  while ( v38[v39] );
  std::wstring::_Construct<1,unsigned short const *>(&v459, v38, v39);
  v40 = web::json::value::string(&v408, &v459);
  memset(v477, 0, sizeof(v477));
  std::wstring::_Construct<1,unsigned short const *>(v477, L"MoreInfoUrl", 11);
  v41 = web::json::value::operator[](&v318, v477);
  web::json::value::operator=(v41, v40);
  std::wstring::_Tidy_deallocate(v477);
  if ( v408 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v408 + 192LL))(v408, 1);
  v42 = lpMem;
  if ( lpMem )
  {
    v43 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v43 )
    {
      if ( v43 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v42);
    }
  }
  v45 = web::json::value::number(&v445, a8);
  memset(v478, 0, sizeof(v478));
  std::wstring::_Construct<1,unsigned short const *>(v478, L"DownloadSizeInBytes", 19);
  v46 = web::json::value::operator[](&v318, v478);
  web::json::value::operator=(v46, v45);
  std::wstring::_Tidy_deallocate(v478);
  if ( v445 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v445 + 192LL))(v445, 1);
  v47 = web::json::value::number(&v446, v347);
  memset(v479, 0, sizeof(v479));
  std::wstring::_Construct<1,unsigned short const *>(v479, L"InstallSizeInBytes", 18);
  v48 = web::json::value::operator[](&v318, v479);
  web::json::value::operator=(v48, v47);
  std::wstring::_Tidy_deallocate(v479);
  if ( v446 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v446 + 192LL))(v446, 1);
  if ( *a10 )
  {
    web::json::value::object(&v327, 0);
    v49 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(a10);
    v50 = web::json::value::number(&v447, v49);
    memset(v500, 0, sizeof(v500));
    std::wstring::_Construct<1,unsigned short const *>(v500, L"Major", 5);
    v51 = web::json::value::operator[](&v327, v500);
    web::json::value::operator=(v51, v50);
    std::wstring::_Tidy_deallocate(v500);
    if ( v447 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v447 + 192LL))(v447, 1);
    v52 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::Size(a10);
    v53 = web::json::value::number(&v448, v52);
    memset(v480, 0, sizeof(v480));
    std::wstring::_Construct<1,unsigned short const *>(v480, L"Minor", 5);
    v54 = web::json::value::operator[](&v327, v480);
    web::json::value::operator=(v54, v53);
    std::wstring::_Tidy_deallocate(v480);
    if ( v448 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v448 + 192LL))(v448, 1);
    v55 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateActionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateActionInfo>::ActionType(a10);
    v56 = web::json::value::number(&v449, v55);
    memset(v481, 0, sizeof(v481));
    std::wstring::_Construct<1,unsigned short const *>(v481, L"RevisionMajor", 13);
    v57 = web::json::value::operator[](&v327, v481);
    web::json::value::operator=(v57, v56);
    std::wstring::_Tidy_deallocate(v481);
    if ( v449 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v449 + 192LL))(v449, 1);
    v58 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::RevisionMinor(a10);
    v59 = web::json::value::number(&v450, v58);
    memset(v482, 0, sizeof(v482));
    std::wstring::_Construct<1,unsigned short const *>(v482, L"RevisionMinor", 13);
    v60 = web::json::value::operator[](&v327, v482);
    web::json::value::operator=(v60, v59);
    std::wstring::_Tidy_deallocate(v482);
    if ( v450 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v450 + 192LL))(v450, 1);
    memset(v483, 0, sizeof(v483));
    std::wstring::_Construct<1,unsigned short const *>(v483, L"SourceVersion", 13);
    v61 = web::json::value::operator[](&v318, v483);
    web::json::value::operator=(v61, &v327);
    std::wstring::_Tidy_deallocate(v483);
    v62 = v327;
  }
  else
  {
    web::json::value::object(&v328, 0);
    v63 = web::json::value::number(&v392, 0);
    memset(v484, 0, sizeof(v484));
    std::wstring::_Construct<1,unsigned short const *>(v484, L"Major", 5);
    v64 = web::json::value::operator[](&v328, v484);
    web::json::value::operator=(v64, v63);
    std::wstring::_Tidy_deallocate(v484);
    if ( v392 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v392 + 192LL))(v392, 1);
    v65 = web::json::value::number(&v393, 0);
    memset(v485, 0, sizeof(v485));
    std::wstring::_Construct<1,unsigned short const *>(v485, L"Minor", 5);
    v66 = web::json::value::operator[](&v328, v485);
    web::json::value::operator=(v66, v65);
    std::wstring::_Tidy_deallocate(v485);
    if ( v393 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v393 + 192LL))(v393, 1);
    v67 = web::json::value::number(&v394, 0);
    memset(v486, 0, sizeof(v486));
    std::wstring::_Construct<1,unsigned short const *>(v486, L"RevisionMajor", 13);
    v68 = web::json::value::operator[](&v328, v486);
    web::json::value::operator=(v68, v67);
    std::wstring::_Tidy_deallocate(v486);
    if ( v394 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v394 + 192LL))(v394, 1);
    v69 = web::json::value::number(&v395, 0);
    memset(v487, 0, sizeof(v487));
    std::wstring::_Construct<1,unsigned short const *>(v487, L"RevisionMinor", 13);
    v70 = web::json::value::operator[](&v328, v487);
    web::json::value::operator=(v70, v69);
    std::wstring::_Tidy_deallocate(v487);
    if ( v395 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v395 + 192LL))(v395, 1);
    memset(v488, 0, sizeof(v488));
    std::wstring::_Construct<1,unsigned short const *>(v488, L"SourceVersion", 13);
    v71 = web::json::value::operator[](&v318, v488);
    web::json::value::operator=(v71, &v328);
    std::wstring::_Tidy_deallocate(v488);
    v62 = v328;
  }
  if ( v62 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v62 + 192LL))(v62, 1);
  v72 = v346;
  if ( *v346 )
  {
    web::json::value::object(&v329, 0);
    v73 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(v72);
    v74 = web::json::value::number(&v396, v73);
    memset(v489, 0, sizeof(v489));
    std::wstring::_Construct<1,unsigned short const *>(v489, L"Major", 5);
    v75 = web::json::value::operator[](&v329, v489);
    web::json::value::operator=(v75, v74);
    std::wstring::_Tidy_deallocate(v489);
    if ( v396 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v396 + 192LL))(v396, 1);
    v76 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::Size(v72);
    v77 = web::json::value::number(&v397, v76);
    memset(v490, 0, sizeof(v490));
    std::wstring::_Construct<1,unsigned short const *>(v490, L"Minor", 5);
    v78 = web::json::value::operator[](&v329, v490);
    web::json::value::operator=(v78, v77);
    std::wstring::_Tidy_deallocate(v490);
    if ( v397 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v397 + 192LL))(v397, 1);
    v79 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateActionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateActionInfo>::ActionType(v72);
    v80 = web::json::value::number(&v398, v79);
    memset(v491, 0, sizeof(v491));
    std::wstring::_Construct<1,unsigned short const *>(v491, L"RevisionMajor", 13);
    v81 = web::json::value::operator[](&v329, v491);
    web::json::value::operator=(v81, v80);
    std::wstring::_Tidy_deallocate(v491);
    if ( v398 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v398 + 192LL))(v398, 1);
    v82 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::RevisionMinor(v72);
    v83 = web::json::value::number(&v399, v82);
    memset(v492, 0, sizeof(v492));
    std::wstring::_Construct<1,unsigned short const *>(v492, L"RevisionMinor", 13);
    v84 = web::json::value::operator[](&v329, v492);
    web::json::value::operator=(v84, v83);
    std::wstring::_Tidy_deallocate(v492);
    if ( v399 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v399 + 192LL))(v399, 1);
    memset(v493, 0, sizeof(v493));
    std::wstring::_Construct<1,unsigned short const *>(v493, L"TargetVersion", 13);
    v85 = web::json::value::operator[](&v318, v493);
    web::json::value::operator=(v85, &v329);
    std::wstring::_Tidy_deallocate(v493);
    v86 = v329;
  }
  else
  {
    web::json::value::object(&v330, 0);
    v87 = web::json::value::number(&v400, 0);
    memset(v494, 0, sizeof(v494));
    std::wstring::_Construct<1,unsigned short const *>(v494, L"Major", 5);
    v88 = web::json::value::operator[](&v330, v494);
    web::json::value::operator=(v88, v87);
    std::wstring::_Tidy_deallocate(v494);
    if ( v400 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v400 + 192LL))(v400, 1);
    v89 = web::json::value::number(&v401, 0);
    memset(v495, 0, sizeof(v495));
    std::wstring::_Construct<1,unsigned short const *>(v495, L"Minor", 5);
    v90 = web::json::value::operator[](&v330, v495);
    web::json::value::operator=(v90, v89);
    std::wstring::_Tidy_deallocate(v495);
    if ( v401 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v401 + 192LL))(v401, 1);
    v91 = web::json::value::number(&v402, 0);
    memset(v496, 0, sizeof(v496));
    std::wstring::_Construct<1,unsigned short const *>(v496, L"RevisionMajor", 13);
    v92 = web::json::value::operator[](&v330, v496);
    web::json::value::operator=(v92, v91);
    std::wstring::_Tidy_deallocate(v496);
    if ( v402 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v402 + 192LL))(v402, 1);
    v93 = web::json::value::number(&v403, 0);
    memset(v497, 0, sizeof(v497));
    std::wstring::_Construct<1,unsigned short const *>(v497, L"RevisionMinor", 13);
    v94 = web::json::value::operator[](&v330, v497);
    web::json::value::operator=(v94, v93);
    std::wstring::_Tidy_deallocate(v497);
    if ( v403 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v403 + 192LL))(v403, 1);
    memset(v498, 0, sizeof(v498));
    std::wstring::_Construct<1,unsigned short const *>(v498, L"TargetVersion", 13);
    v95 = web::json::value::operator[](&v318, v498);
    web::json::value::operator=(v95, &v330);
    std::wstring::_Tidy_deallocate(v498);
    v86 = v330;
  }
  if ( v86 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v86 + 192LL))(v86, 1);
  v96 = *v345;
  if ( *v345 )
  {
    v472 = 0;
    v468 = 0;
    v469 = 0;
    v97 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v96 + 48LL))(v96, &v472);
    if ( v97 < 0 )
      winrt::throw_hresult((unsigned int)v97, &v468);
    v98 = winrt::to_hstring(&v406, &v472);
    if ( *(_QWORD *)v98 )
      v99 = *(const unsigned __int16 **)(*(_QWORD *)v98 + 16LL);
    else
      v99 = &dword_180030C44;
    v462 = 0;
    v463 = 0;
    v464 = 0;
    v100 = -1;
    do
      ++v100;
    while ( v99[v100] );
    std::wstring::_Construct<1,unsigned short const *>(&v462, v99, v100);
    v101 = web::json::value::string(&v405, &v462);
    v102 = 3;
  }
  else
  {
    v465 = 0;
    v466 = 0;
    v467 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v465, &dword_180030C44, 0);
    v101 = web::json::value::string(&v404, &v465);
    v102 = 4;
  }
  memset(v499, 0, sizeof(v499));
  std::wstring::_Construct<1,unsigned short const *>(v499, L"ProductCode", 11);
  v103 = web::json::value::operator[](&v318, v499);
  web::json::value::operator=(v103, v101);
  std::wstring::_Tidy_deallocate(v499);
  if ( (v102 & 4) != 0 )
  {
    v102 &= ~4u;
    if ( v404 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v404 + 192LL))(v404, 1);
  }
  if ( (v102 & 2) != 0 )
  {
    v102 &= ~2u;
    if ( v405 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v405 + 192LL))(v405, 1);
  }
  if ( (v102 & 1) != 0 )
  {
    v102 &= ~1u;
    v104 = v406;
    if ( v406 )
    {
      v105 = _InterlockedDecrement((volatile signed __int32 *)v406 + 6);
      if ( v105 )
      {
        if ( v105 < 0 )
          abort();
      }
      else
      {
        v106 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v106, 0, v104);
      }
    }
  }
  if ( *(_QWORD *)v344 )
  {
    v107 = *(_QWORD *)(*(_QWORD *)v344 + 16LL);
    v314 = 0;
    v315 = 0;
    v316 = 0;
    v108 = -1;
    do
      ++v108;
    while ( *(_WORD *)(v107 + 2 * v108) );
    std::wstring::_Construct<1,unsigned short const *>(&v314, v107, v108);
    v109 = web::json::value::string(&v353, &v314);
    v110 = v102 | 8;
  }
  else
  {
    v388 = 0;
    v389 = 0;
    v390 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v388, &dword_180030C44, 0);
    v109 = web::json::value::string(&v407, &v388);
    v110 = v102 | 0x10;
  }
  v470 = 0;
  v471 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v470, L"PackageFamilyName", 17);
  v111 = web::json::value::operator[](&v318, &v470);
  web::json::value::operator=(v111, v109);
  std::wstring::_Tidy_deallocate(&v470);
  if ( (v110 & 0x10) != 0 )
  {
    v110 &= ~0x10u;
    if ( v407 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v407 + 192LL))(v407, 1);
  }
  if ( (v110 & 8) != 0 )
  {
    v110 &= ~8u;
    if ( v353 )
      (*(void (__fastcall **)(_QWORD *, __int64))(*v353 + 192LL))(v353, 1);
  }
  if ( *v332 == 1 )
  {
    v112 = v343;
    if ( !*v343 )
      goto LABEL_351;
    web::json::value::object(v317, 0);
    v325 = 0;
    v113 = *v112;
    pExceptionObject = 0;
    v322 = 0;
    v114 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v113 + 48LL))(v113, &v325);
    if ( v114 < 0 )
      winrt::throw_hresult((unsigned int)v114, &pExceptionObject);
    v353 = v325;
    v110 |= 0x1000u;
    if ( v325 )
      v115 = (const unsigned __int16 *)v325[2];
    else
      v115 = &dword_180030C44;
    v314 = 0;
    v315 = 0;
    v316 = 0;
    v116 = -1;
    do
      ++v116;
    while ( v115[v116] );
    std::wstring::_Construct<1,unsigned short const *>(&v314, v115, v116);
    v117 = web::json::value::string(&v342, &v314);
    v470 = 0;
    v471 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v470, L"PackageFamilyName", 17);
    v118 = web::json::value::operator[](v317, &v470);
    web::json::value::operator=(v118, v117);
    std::wstring::_Tidy_deallocate(&v470);
    if ( v342 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v342 + 192LL))(v342, 1);
    winrt::hstring::~hstring((winrt::hstring *)&v353);
    LODWORD(v319) = 0;
    v119 = *v112;
    pExceptionObject = 0;
    v322 = 0;
    v120 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v119 + 56LL))(v119, &v319);
    if ( v120 < 0 )
      winrt::throw_hresult((unsigned int)v120, &pExceptionObject);
    v121 = web::json::value::number(&v341, (unsigned int)v319);
    v470 = 0;
    v471 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v470, L"PackageArchitecture", 19);
    v122 = web::json::value::operator[](v317, &v470);
    web::json::value::operator=(v122, v121);
    std::wstring::_Tidy_deallocate(&v470);
    if ( v341 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v341 + 192LL))(v341, 1);
    v123 = *(_QWORD *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DeployInfo(
                        v112,
                        &v324);
    if ( v324 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v324);
    if ( v123 )
    {
      v124 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DeployInfo(
               v112,
               &v323);
      v125 = winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::RawUri(
               v124,
               &v339);
      if ( *(_QWORD *)v125 )
        v126 = *(const unsigned __int16 **)(*(_QWORD *)v125 + 16LL);
      else
        v126 = &dword_180030C44;
      v314 = 0;
      v315 = 0;
      v316 = 0;
      do
        ++v33;
      while ( v126[v33] );
      std::wstring::_Construct<1,unsigned short const *>(&v314, v126, v33);
      v127 = web::json::value::string(&v340, &v314);
      v470 = 0;
      v471 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v470, L"InstallUri", 10);
      v128 = web::json::value::operator[](v317, &v470);
      web::json::value::operator=(v128, v127);
      std::wstring::_Tidy_deallocate(&v470);
      if ( v340 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v340 + 192LL))(v340, 1);
      winrt::hstring::~hstring((winrt::hstring *)&v339);
      if ( v323 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v323);
    }
    v470 = 0;
    v471 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v470, L"AppPackageInfo", 14);
    v129 = web::json::value::operator[](&v318, &v470);
    web::json::value::operator=(v129, v317);
    std::wstring::_Tidy_deallocate(&v470);
    v130 = v317[0];
  }
  else
  {
    if ( *v332 - 2 > 1 )
      goto LABEL_351;
    v131 = v320;
    if ( !*v320 )
      goto LABEL_351;
    web::json::value::object(&v319, 0);
    v132 = *(_QWORD *)winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
                        v131,
                        &v366);
    if ( v366 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v366);
    if ( v132 )
    {
      web::json::value::object(v317, 0);
      v133 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
               v131,
               &v367);
      v134 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
               v133,
               v410);
      if ( *(_QWORD *)v134 )
        v135 = *(const unsigned __int16 **)(*(_QWORD *)v134 + 16LL);
      else
        v135 = &dword_180030C44;
      v314 = 0;
      v315 = 0;
      v316 = 0;
      v136 = -1;
      do
        ++v136;
      while ( v135[v136] );
      std::wstring::_Construct<1,unsigned short const *>(&v314, v135, v136);
      v137 = web::json::value::string(&v409, &v314);
      v470 = 0;
      v471 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v470, L"FileName", 8);
      v138 = web::json::value::operator[](v317, &v470);
      web::json::value::operator=(v138, v137);
      std::wstring::_Tidy_deallocate(&v470);
      if ( v409 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v409 + 192LL))(v409, 1);
      winrt::hstring::~hstring((winrt::hstring *)v410);
      if ( v367 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v367);
      v139 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
               v131,
               &v368);
      v140 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
               v139,
               v412);
      if ( *(_QWORD *)v140 )
        v141 = *(const unsigned __int16 **)(*(_QWORD *)v140 + 16LL);
      else
        v141 = &dword_180030C44;
      v314 = 0;
      v315 = 0;
      v316 = 0;
      v142 = -1;
      do
        ++v142;
      while ( v141[v142] );
      std::wstring::_Construct<1,unsigned short const *>(&v314, v141, v142);
      v143 = web::json::value::string(&v411, &v314);
      v470 = 0;
      v471 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v470, L"FileArguments", 13);
      v144 = web::json::value::operator[](v317, &v470);
      web::json::value::operator=(v144, v143);
      std::wstring::_Tidy_deallocate(&v470);
      if ( v411 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v411 + 192LL))(v411, 1);
      winrt::hstring::~hstring((winrt::hstring *)v412);
      if ( v368 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v368);
      v145 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
               v131,
               &v369);
      v146 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateActionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateActionInfo>::ActionType(v145);
      v147 = web::json::value::number(&v413, v146);
      v470 = 0;
      v471 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v470, L"ActionType", 10);
      v148 = web::json::value::operator[](v317, &v470);
      web::json::value::operator=(v148, v147);
      std::wstring::_Tidy_deallocate(&v470);
      if ( v413 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v413 + 192LL))(v413, 1);
      if ( v369 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v369);
      v470 = 0;
      v471 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v470, L"DownloadInfo", 12);
      v149 = web::json::value::operator[](&v319, &v470);
      web::json::value::operator=(v149, v317);
      std::wstring::_Tidy_deallocate(&v470);
      if ( v317[0] )
        (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v317[0] + 192LL))(v317[0], 1);
    }
    v150 = *(_QWORD *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
                        v131,
                        &v372);
    if ( v372 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v372);
    if ( v150 )
    {
      web::json::value::object(&v336, 0);
      v151 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
               v131,
               &v364);
      v152 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
               v151,
               v415);
      if ( *(_QWORD *)v152 )
        v153 = *(const unsigned __int16 **)(*(_QWORD *)v152 + 16LL);
      else
        v153 = &dword_180030C44;
      v314 = 0;
      v315 = 0;
      v316 = 0;
      v154 = -1;
      do
        ++v154;
      while ( v153[v154] );
      std::wstring::_Construct<1,unsigned short const *>(&v314, v153, v154);
      v155 = web::json::value::string(&v414, &v314);
      v470 = 0;
      v471 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v470, L"FileName", 8);
      v156 = web::json::value::operator[](&v336, &v470);
      web::json::value::operator=(v156, v155);
      std::wstring::_Tidy_deallocate(&v470);
      if ( v414 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v414 + 192LL))(v414, 1);
      winrt::hstring::~hstring((winrt::hstring *)v415);
      if ( v364 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v364);
      v157 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
               v131,
               &v373);
      v158 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
               v157,
               v417);
      if ( *(_QWORD *)v158 )
        v159 = *(const unsigned __int16 **)(*(_QWORD *)v158 + 16LL);
      else
        v159 = &dword_180030C44;
      v314 = 0;
      v315 = 0;
      v316 = 0;
      v160 = -1;
      do
        ++v160;
      while ( v159[v160] );
      std::wstring::_Construct<1,unsigned short const *>(&v314, v159, v160);
      v161 = web::json::value::string(&v416, &v314);
      v470 = 0;
      v471 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v470, L"FileArguments", 13);
      v162 = web::json::value::operator[](&v336, &v470);
      web::json::value::operator=(v162, v161);
      std::wstring::_Tidy_deallocate(&v470);
      if ( v416 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v416 + 192LL))(v416, 1);
      winrt::hstring::~hstring((winrt::hstring *)v417);
      if ( v373 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v373);
      v163 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
               v131,
               &v374);
      v164 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateActionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateActionInfo>::ActionType(v163);
      v165 = web::json::value::number(&v418, v164);
      v470 = 0;
      v471 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v470, L"ActionType", 10);
      v166 = web::json::value::operator[](&v336, &v470);
      web::json::value::operator=(v166, v165);
      std::wstring::_Tidy_deallocate(&v470);
      if ( v418 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v418 + 192LL))(v418, 1);
      if ( v374 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v374);
      v470 = 0;
      v471 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v470, L"InstallInfo", 11);
      v167 = web::json::value::operator[](&v319, &v470);
      web::json::value::operator=(v167, &v336);
      std::wstring::_Tidy_deallocate(&v470);
      if ( v336 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v336 + 192LL))(v336, 1);
    }
    v168 = *(_QWORD *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DeployInfo(
                        v131,
                        &v375);
    if ( v375 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v375);
    if ( v168 )
    {
      web::json::value::object(&v334, 0);
      v169 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DeployInfo(
               v131,
               &v376);
      v170 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
               v169,
               v420);
      if ( *(_QWORD *)v170 )
        v171 = *(const unsigned __int16 **)(*(_QWORD *)v170 + 16LL);
      else
        v171 = &dword_180030C44;
      v314 = 0;
      v315 = 0;
      v316 = 0;
      v172 = -1;
      do
        ++v172;
      while ( v171[v172] );
      std::wstring::_Construct<1,unsigned short const *>(&v314, v171, v172);
      v173 = web::json::value::string(&v419, &v314);
      v470 = 0;
      v471 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v470, L"FileName", 8);
      v174 = web::json::value::operator[](&v334, &v470);
      web::json::value::operator=(v174, v173);
      std::wstring::_Tidy_deallocate(&v470);
      if ( v419 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v419 + 192LL))(v419, 1);
      winrt::hstring::~hstring((winrt::hstring *)v420);
      if ( v376 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v376);
      v175 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DeployInfo(
               v131,
               &v377);
      v176 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
               v175,
               v422);
      if ( *(_QWORD *)v176 )
        v177 = *(const unsigned __int16 **)(*(_QWORD *)v176 + 16LL);
      else
        v177 = &dword_180030C44;
      v314 = 0;
      v315 = 0;
      v316 = 0;
      v178 = -1;
      do
        ++v178;
      while ( v177[v178] );
      std::wstring::_Construct<1,unsigned short const *>(&v314, v177, v178);
      v179 = web::json::value::string(&v421, &v314);
      v470 = 0;
      v471 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v470, L"FileArguments", 13);
      v180 = web::json::value::operator[](&v334, &v470);
      web::json::value::operator=(v180, v179);
      std::wstring::_Tidy_deallocate(&v470);
      if ( v421 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v421 + 192LL))(v421, 1);
      winrt::hstring::~hstring((winrt::hstring *)v422);
      if ( v377 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v377);
      v181 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DeployInfo(
               v131,
               &v378);
      v182 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateActionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateActionInfo>::ActionType(v181);
      v183 = web::json::value::number(&v423, v182);
      v470 = 0;
      v471 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v470, L"ActionType", 10);
      v184 = web::json::value::operator[](&v334, &v470);
      web::json::value::operator=(v184, v183);
      std::wstring::_Tidy_deallocate(&v470);
      if ( v423 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v423 + 192LL))(v423, 1);
      if ( v378 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v378);
      v470 = 0;
      v471 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v470, L"DeployInfo", 10);
      v185 = web::json::value::operator[](&v319, &v470);
      web::json::value::operator=(v185, &v334);
      std::wstring::_Tidy_deallocate(&v470);
      if ( v334 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v334 + 192LL))(v334, 1);
    }
    v186 = *(_QWORD *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
                        v131,
                        &v379);
    if ( v379 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v379);
    if ( v186 )
    {
      v187 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
               v131,
               &v382);
      v188 = *(_QWORD *)winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
                          v187,
                          &v381);
      if ( v381 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v381);
      if ( v382 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v382);
      if ( v188 )
      {
        web::json::value::object(&v323, 0);
        v189 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
                 v131,
                 &v386);
        v190 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
                 v189,
                 &v387);
        v191 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
                 v190,
                 v425);
        if ( *(_QWORD *)v191 )
          v192 = *(const unsigned __int16 **)(*(_QWORD *)v191 + 16LL);
        else
          v192 = &dword_180030C44;
        v314 = 0;
        v315 = 0;
        v316 = 0;
        v193 = -1;
        do
          ++v193;
        while ( v192[v193] );
        std::wstring::_Construct<1,unsigned short const *>(&v314, v192, v193);
        v194 = web::json::value::string(&v424, &v314);
        v470 = 0;
        v471 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v470, L"FileName", 8);
        v195 = web::json::value::operator[](&v323, &v470);
        web::json::value::operator=(v195, v194);
        std::wstring::_Tidy_deallocate(&v470);
        if ( v424 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v424 + 192LL))(v424, 1);
        winrt::hstring::~hstring((winrt::hstring *)v425);
        if ( v387 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v387);
        if ( v386 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v386);
        v196 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
                 v131,
                 &v371);
        v197 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
                 v196,
                 &v384);
        v198 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
                 v197,
                 v427);
        if ( *(_QWORD *)v198 )
          v199 = *(const unsigned __int16 **)(*(_QWORD *)v198 + 16LL);
        else
          v199 = &dword_180030C44;
        v314 = 0;
        v315 = 0;
        v316 = 0;
        v200 = -1;
        do
          ++v200;
        while ( v199[v200] );
        std::wstring::_Construct<1,unsigned short const *>(&v314, v199, v200);
        v201 = web::json::value::string(&v426, &v314);
        v470 = 0;
        v471 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v470, L"FileArguments", 13);
        v202 = web::json::value::operator[](&v323, &v470);
        web::json::value::operator=(v202, v201);
        std::wstring::_Tidy_deallocate(&v470);
        if ( v426 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v426 + 192LL))(v426, 1);
        winrt::hstring::~hstring((winrt::hstring *)v427);
        if ( v384 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v384);
        if ( v371 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v371);
        v203 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
                 v131,
                 &v391);
        v204 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
                 v203,
                 &v380);
        v205 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateActionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateActionInfo>::ActionType(v204);
        v206 = web::json::value::number(&v428, v205);
        v470 = 0;
        v471 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v470, L"ActionType", 10);
        v207 = web::json::value::operator[](&v323, &v470);
        web::json::value::operator=(v207, v206);
        std::wstring::_Tidy_deallocate(&v470);
        if ( v428 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v428 + 192LL))(v428, 1);
        if ( v380 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v380);
        if ( v391 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v391);
        v470 = 0;
        v471 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v470, L"CloseAndDeployInfo", 18);
        v208 = web::json::value::operator[](&v319, &v470);
        web::json::value::operator=(v208, &v323);
        std::wstring::_Tidy_deallocate(&v470);
        if ( v323 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v323 + 192LL))(v323, 1);
      }
      v209 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
               v131,
               &v355);
      v210 = *(_QWORD *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
                          v209,
                          &v385);
      if ( v385 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v385);
      if ( v355 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v355);
      if ( v210 )
      {
        web::json::value::object(&v324, 0);
        v211 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
                 v131,
                 &v357);
        v212 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
                 v211,
                 &v356);
        v213 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
                 v212,
                 v430);
        if ( *(_QWORD *)v213 )
          v214 = *(const unsigned __int16 **)(*(_QWORD *)v213 + 16LL);
        else
          v214 = &dword_180030C44;
        v314 = 0;
        v315 = 0;
        v316 = 0;
        v215 = -1;
        do
          ++v215;
        while ( v214[v215] );
        std::wstring::_Construct<1,unsigned short const *>(&v314, v214, v215);
        v216 = web::json::value::string(&v429, &v314);
        v470 = 0;
        v471 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v470, L"FileName", 8);
        v217 = web::json::value::operator[](&v324, &v470);
        web::json::value::operator=(v217, v216);
        std::wstring::_Tidy_deallocate(&v470);
        if ( v429 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v429 + 192LL))(v429, 1);
        winrt::hstring::~hstring((winrt::hstring *)v430);
        if ( v356 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v356);
        if ( v357 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v357);
        v218 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
                 v131,
                 &v359);
        v219 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
                 v218,
                 &v358);
        v220 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
                 v219,
                 v432);
        if ( *(_QWORD *)v220 )
          v221 = *(const unsigned __int16 **)(*(_QWORD *)v220 + 16LL);
        else
          v221 = &dword_180030C44;
        v314 = 0;
        v315 = 0;
        v316 = 0;
        v222 = -1;
        do
          ++v222;
        while ( v221[v222] );
        std::wstring::_Construct<1,unsigned short const *>(&v314, v221, v222);
        v223 = web::json::value::string(&v431, &v314);
        v470 = 0;
        v471 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v470, L"FileArguments", 13);
        v224 = web::json::value::operator[](&v324, &v470);
        web::json::value::operator=(v224, v223);
        std::wstring::_Tidy_deallocate(&v470);
        if ( v431 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v431 + 192LL))(v431, 1);
        winrt::hstring::~hstring((winrt::hstring *)v432);
        if ( v358 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v358);
        if ( v359 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v359);
        v225 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
                 v131,
                 &v361);
        v226 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
                 v225,
                 &v360);
        v227 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateActionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateActionInfo>::ActionType(v226);
        v228 = web::json::value::number(&v433, v227);
        v470 = 0;
        v471 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v470, L"ActionType", 10);
        v229 = web::json::value::operator[](&v324, &v470);
        web::json::value::operator=(v229, v228);
        std::wstring::_Tidy_deallocate(&v470);
        if ( v433 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v433 + 192LL))(v433, 1);
        if ( v360 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v360);
        if ( v361 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v361);
        v470 = 0;
        v471 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v470, L"CloseAndInstallInfo", 19);
        v230 = web::json::value::operator[](&v319, &v470);
        web::json::value::operator=(v230, &v324);
        std::wstring::_Tidy_deallocate(&v470);
        if ( v324 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v324 + 192LL))(v324, 1);
      }
      v231 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
               v131,
               &v363);
      v232 = *(_QWORD *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DeployInfo(
                          v231,
                          &v362);
      if ( v362 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v362);
      if ( v363 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v363);
      if ( v232 )
      {
        web::json::value::object(&v325, 0);
        v233 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
                 v131,
                 &v365);
        v234 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DeployInfo(
                 v233,
                 &v383);
        v235 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
                 v234,
                 v435);
        if ( *(_QWORD *)v235 )
          v236 = *(const unsigned __int16 **)(*(_QWORD *)v235 + 16LL);
        else
          v236 = &dword_180030C44;
        v314 = 0;
        v315 = 0;
        v316 = 0;
        v237 = -1;
        do
          ++v237;
        while ( v236[v237] );
        std::wstring::_Construct<1,unsigned short const *>(&v314, v236, v237);
        v238 = web::json::value::string(&v434, &v314);
        v470 = 0;
        v471 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v470, L"FileName", 8);
        v239 = web::json::value::operator[](&v325, &v470);
        web::json::value::operator=(v239, v238);
        std::wstring::_Tidy_deallocate(&v470);
        if ( v434 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v434 + 192LL))(v434, 1);
        winrt::hstring::~hstring((winrt::hstring *)v435);
        if ( v383 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v383);
        if ( v365 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v365);
        v240 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
                 v131,
                 &v340);
        v241 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DeployInfo(
                 v240,
                 &v339);
        v242 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
                 v241,
                 v437);
        if ( *(_QWORD *)v242 )
          v243 = *(const unsigned __int16 **)(*(_QWORD *)v242 + 16LL);
        else
          v243 = &dword_180030C44;
        v314 = 0;
        v315 = 0;
        v316 = 0;
        do
          ++v33;
        while ( v243[v33] );
        std::wstring::_Construct<1,unsigned short const *>(&v314, v243, v33);
        v244 = web::json::value::string(&v436, &v314);
        v470 = 0;
        v471 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v470, L"FileArguments", 13);
        v245 = web::json::value::operator[](&v325, &v470);
        web::json::value::operator=(v245, v244);
        std::wstring::_Tidy_deallocate(&v470);
        if ( v436 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v436 + 192LL))(v436, 1);
        winrt::hstring::~hstring((winrt::hstring *)v437);
        if ( v339 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v339);
        if ( v340 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v340);
        v246 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
                 v131,
                 &v342);
        v247 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DeployInfo(
                 v246,
                 &v341);
        v248 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateActionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateActionInfo>::ActionType(v247);
        v249 = web::json::value::number(&v337, v248);
        v470 = 0;
        v471 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v470, L"ActionType", 10);
        v250 = web::json::value::operator[](&v325, &v470);
        web::json::value::operator=(v250, v249);
        std::wstring::_Tidy_deallocate(&v470);
        if ( v337 )
          (*(void (__fastcall **)(_QWORD *, __int64))(*v337 + 192LL))(v337, 1);
        if ( v341 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v341);
        if ( v342 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v342);
        v470 = 0;
        v471 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v470, L"CloseAndRestartInfo", 19);
        v251 = web::json::value::operator[](&v319, &v470);
        web::json::value::operator=(v251, &v325);
        std::wstring::_Tidy_deallocate(&v470);
        if ( v325 )
          (*(void (__fastcall **)(_QWORD *, __int64))(*v325 + 192LL))(v325, 1);
      }
    }
    std::wstring::wstring(&v470, L"ExecutionInfo");
    v252 = web::json::value::operator[](&v318, &v470);
    web::json::value::operator=(v252, &v319);
    std::wstring::_Tidy_deallocate(&v470);
    v130 = v319;
  }
  if ( v130 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v130 + 192LL))(v130, 1);
LABEL_351:
  v253 = v333;
  if ( *v333 )
  {
    web::json::value::object(&v335, 0);
    v254 = v110 | 0x20;
    if ( !*(_QWORD *)winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
                       v253,
                       &v320)
      || (v255 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
                   v253,
                   &v370),
          v254 |= 0x40u,
          v256 = 1,
          !(unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::Size(v255)) )
    {
      v256 = 0;
    }
    if ( (v254 & 0x40) != 0 )
    {
      v254 &= ~0x40u;
      if ( v370 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v370);
    }
    if ( (v254 & 0x20) != 0 )
    {
      v254 &= ~0x20u;
      if ( v320 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v320);
    }
    if ( v256 )
    {
      v257 = winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
               v253,
               &v343);
      v258 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::Size(v257);
      web::json::value::array(&v332, v258);
      if ( v343 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v343);
      v259 = 0;
      winrt::impl::consume_Windows_Management_Update_IWindowsUpdateRestartRequestOptions<winrt::Windows::Management::Update::IWindowsUpdateRestartRequestOptions>::Title(
        v253,
        &v352);
      v260 = 0;
      v261 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>,winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::Size(&v352);
      v262 = v352;
      while ( v260 != v261 )
      {
        v317[0] = 0;
        v263 = v254 | 0x4000;
        pExceptionObject = 0;
        v322 = 0;
        v264 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v262 + 48LL))(v262, v260, v317);
        if ( v264 < 0 )
          winrt::throw_hresult((unsigned int)v264, &pExceptionObject);
        v265 = v263 & 0xFFFF9FFF | 0x2000;
        web::json::value::object(&v331, 0);
        LODWORD(v319) = 0;
        pExceptionObject = 0;
        v322 = 0;
        v266 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v317[0] + 48LL))(v317[0], &v319);
        if ( v266 < 0 )
          winrt::throw_hresult((unsigned int)v266, &pExceptionObject);
        v267 = web::json::value::number(&v439, (unsigned int)v319);
        std::wstring::wstring(&v470, L"LanguageId");
        v268 = web::json::value::operator[](&v331, &v470);
        web::json::value::operator=(v268, v267);
        std::wstring::_Tidy_deallocate(&v470);
        if ( v439 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v439 + 192LL))(v439, 1);
        v320 = 0;
        pExceptionObject = 0;
        v322 = 0;
        v269 = (*(__int64 (__fastcall **)(_QWORD, _QWORD **))(*(_QWORD *)v317[0] + 56LL))(v317[0], &v320);
        if ( v269 < 0 )
          winrt::throw_hresult((unsigned int)v269, &pExceptionObject);
        v337 = v320;
        v270 = v265 | 0x8000;
        if ( v320 )
          v271 = (const unsigned __int16 *)v320[2];
        else
          v271 = &dword_180030C44;
        v272 = std::wstring::wstring(v354, v271);
        v273 = web::json::value::string(&v440, v272);
        std::wstring::wstring(&v470, L"Title");
        v274 = web::json::value::operator[](&v331, &v470);
        web::json::value::operator=(v274, v273);
        std::wstring::_Tidy_deallocate(&v470);
        if ( v440 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v440 + 192LL))(v440, 1);
        winrt::hstring::~hstring((winrt::hstring *)&v337);
        v320 = 0;
        pExceptionObject = 0;
        v322 = 0;
        v275 = (*(__int64 (__fastcall **)(_QWORD, _QWORD **))(*(_QWORD *)v317[0] + 64LL))(v317[0], &v320);
        if ( v275 < 0 )
          winrt::throw_hresult((unsigned int)v275, &pExceptionObject);
        v337 = v320;
        v254 = v270 | 0x10000;
        if ( v320 )
          v276 = (const unsigned __int16 *)v320[2];
        else
          v276 = &dword_180030C44;
        v277 = std::wstring::wstring(v354, v276);
        v278 = web::json::value::string(&v441, v277);
        std::wstring::wstring(&v470, L"Description");
        v279 = web::json::value::operator[](&v331, &v470);
        web::json::value::operator=(v279, v278);
        std::wstring::_Tidy_deallocate(&v470);
        if ( v441 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v441 + 192LL))(v441, 1);
        winrt::hstring::~hstring((winrt::hstring *)&v337);
        v280 = *(_QWORD *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
                            v317,
                            &v344);
        if ( v344 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v344);
        if ( v280 )
        {
          v281 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::OptionalActionInfo(
                   v317,
                   &v345);
          v282 = winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::RawUri(
                   v281,
                   v443);
          if ( *(_QWORD *)v282 )
            v283 = *(const unsigned __int16 **)(*(_QWORD *)v282 + 16LL);
          else
            v283 = &dword_180030C44;
          v284 = std::wstring::wstring(v354, v283);
          v285 = web::json::value::string(&v442, v284);
          std::wstring::wstring(&v470, L"MoreInfoUrl");
          v286 = web::json::value::operator[](&v331, &v470);
          web::json::value::operator=(v286, v285);
          std::wstring::_Tidy_deallocate(&v470);
          if ( v442 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v442 + 192LL))(v442, 1);
          winrt::hstring::~hstring((winrt::hstring *)v443);
          if ( v345 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v345);
        }
        v287 = web::json::value::operator[](&v332, v259++);
        web::json::value::operator=(v287, &v331);
        if ( v331 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v331 + 192LL))(v331, 1);
        if ( v317[0] )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v317);
        ++v260;
      }
      if ( v262 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v352);
      std::wstring::wstring(&v470, L"LocalizationInfo");
      v288 = web::json::value::operator[](&v335, &v470);
      web::json::value::operator=(v288, &v332);
      std::wstring::_Tidy_deallocate(&v470);
      if ( v332 )
        (*(void (__fastcall **)(unsigned int *, __int64))(*(_QWORD *)v332 + 192LL))(v332, 1);
      v253 = v333;
    }
    v289 = *(_QWORD *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
                        v253,
                        &v333);
    if ( v333 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v333);
    if ( v289 )
    {
      v290 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
               v253,
               &v347);
      LOWORD(v254) = v254 | 0x80;
      if ( (int)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(v290) < 0
        || (v291 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
                     v253,
                     &v346),
            LOWORD(v254) = v254 | 0x100,
            v292 = 0,
            (int)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(v291) > 30) )
      {
        v292 = 1;
      }
      if ( (v254 & 0x100) != 0 )
      {
        LOWORD(v254) = v254 & 0xFEFF;
        if ( v346 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v346);
      }
      if ( (v254 & 0x80u) != 0 )
      {
        LOWORD(v254) = v254 & 0xFF7F;
        if ( v347 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v347);
      }
      if ( v292 )
      {
        v313 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v452);
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)v354,
          L"ComplianceDeadlineInDays must be a non-negative value less than or equal to 30 days.");
        winrt::hresult_invalid_argument::hresult_invalid_argument(
          (winrt::hresult_invalid_argument *)&pExceptionObject,
          (const struct winrt::param::hstring *)v354,
          v313);
        throw (winrt::hresult_invalid_argument *)&pExceptionObject;
      }
      v293 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateOptionalInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfo>::ComplianceDeadlineInDays(
               v253,
               &v348);
      v294 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(v293);
      v295 = web::json::value::number(&v444, v294);
      std::wstring::wstring(&v470, L"ComplianceDeadlineInDays");
      v296 = web::json::value::operator[](&v335, &v470);
      web::json::value::operator=(v296, v295);
      std::wstring::_Tidy_deallocate(&v470);
      if ( v444 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v444 + 192LL))(v444, 1);
      if ( v348 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v348);
    }
    v297 = *(_QWORD *)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DeployInfo(
                        v253,
                        &v349);
    if ( v349 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v349);
    if ( v297 )
    {
      v298 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DeployInfo(
               v253,
               &v338);
      v299 = v254 | 0x200;
      if ( (int)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(v298) < 0
        || (v300 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DeployInfo(
                     v253,
                     &v350),
            v299 |= 0x400u,
            v301 = 0,
            (int)winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(v300) > 7) )
      {
        v301 = 1;
      }
      if ( (v299 & 0x400) != 0 )
      {
        v299 &= ~0x400u;
        if ( v350 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v350);
      }
      if ( (v299 & 0x200) != 0 && v338 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v338);
      if ( v301 )
      {
        v309 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v452);
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)v354,
          L"ComplianceGracePeriodInDays must be a non-negative value less than or equal to 7 days.");
        winrt::hresult_invalid_argument::hresult_invalid_argument(
          (winrt::hresult_invalid_argument *)&pExceptionObject,
          (const struct winrt::param::hstring *)v354,
          v309);
        throw (winrt::hresult_invalid_argument *)&pExceptionObject;
      }
      v302 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateExecutionInfo<winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfo>::DeployInfo(
               v253,
               &v351);
      v303 = winrt::impl::consume_Windows_Management_Update_IWindowsSoftwareUpdateVersion<winrt::Windows::Management::Update::IWindowsSoftwareUpdateVersion>::Major(v302);
      v304 = web::json::value::number(&v326, v303);
      std::wstring::wstring(&v470, L"ComplianceGracePeriodInDays");
      v305 = web::json::value::operator[](&v335, &v470);
      web::json::value::operator=(v305, v304);
      std::wstring::_Tidy_deallocate(&v470);
      if ( v326 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v326 + 192LL))(v326, 1);
      if ( v351 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v351);
    }
    std::wstring::wstring(&v470, L"OptionalInfo");
    v306 = web::json::value::operator[](&v318, &v470);
    web::json::value::operator=(v306, &v335);
    std::wstring::_Tidy_deallocate(&v470);
    if ( v335 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v335 + 192LL))(v335, 1);
  }
  v307 = v451;
  web::json::value::serialize(&v318, v451);
  if ( v318 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v318 + 192LL))(v318, 1);
  return v307;
}

```

## disassembly

```asm
0x180019118  push    rbp
0x18001911a  push    rbx
0x18001911b  push    rsi
0x18001911c  push    rdi
0x18001911d  push    r12
0x18001911f  push    r13
0x180019121  push    r14
0x180019123  push    r15
0x180019125  lea     rbp, [rsp-848h]
0x18001912d  sub     rsp, 948h
0x180019134  mov     rax, cs:__security_cookie
0x18001913b  xor     rax, rsp
0x18001913e  mov     [rbp+880h+var_50], rax
0x180019145  mov     rdi, r9
0x180019148  mov     [rbp+880h+var_8B0], r8
0x18001914c  mov     rbx, rdx
0x18001914f  mov     [rbp+880h+var_4D8], rcx
0x180019156  mov     [rbp+880h+var_8E0], rcx
0x18001915a  mov     rsi, [rbp+880h+arg_20]
0x180019161  mov     r14, [rbp+880h+arg_28]
0x180019168  mov     r15, [rbp+880h+arg_30]
0x18001916f  mov     r13, [rbp+880h+arg_38]
0x180019176  mov     rax, [rbp+880h+arg_40]
0x18001917d  mov     [rbp+880h+var_838], rax
0x180019181  mov     r12, [rbp+880h+arg_48]
0x180019188  mov     rax, [rbp+880h+arg_50]
0x18001918f  mov     [rbp+880h+var_840], rax
0x180019193  mov     rcx, [rbp+880h+arg_58]
0x18001919a  mov     [rbp+880h+var_858], rcx
0x18001919e  mov     rdx, [rbp+880h+arg_60]
0x1800191a5  mov     [rsp+980h+var_918], rdx
0x1800191aa  mov     rax, [rbp+880h+arg_68]
0x1800191b1  mov     [rbp+880h+var_8A8], rax
0x1800191b5  mov     rax, [rbp+880h+arg_70]
0x1800191bc  mov     [rbp+880h+var_848], rax
0x1800191c0  mov     rax, [rbp+880h+arg_78]
0x1800191c7  mov     [rbp+880h+var_850], rax
0x1800191cb  xor     r9d, r9d
0x1800191ce  mov     [rsp+980h+var_960], r9d
0x1800191d3  cmp     [rbx], r9
0x1800191d6  jz      loc_18001C98B
0x1800191dc  cmp     [rdi], r9
0x1800191df  jz      loc_18001C98B
0x1800191e5  cmp     [rsi], r9
0x1800191e8  jz      loc_18001C98B
0x1800191ee  cmp     [r14], r9
0x1800191f1  jz      loc_18001C98B
0x1800191f7  cmp     [r15], r9
0x1800191fa  jz      loc_18001C98B
0x180019200  mov     eax, [r8]
0x180019203  cmp     eax, 1
0x180019206  jnz     short loc_180019213
0x180019208  cmp     [rcx], r9
0x18001920b  jz      loc_18001C943
0x180019211  jmp     short loc_180019224
0x180019213  add     eax, 0FFFFFFFEh
0x180019216  cmp     eax, 1
0x180019219  ja      short loc_180019224
0x18001921b  cmp     [rdx], r9
0x18001921e  jz      loc_18001C9D3
0x180019224  xor     edx, edx
0x180019226  lea     rcx, [rsp+980h+var_928]
0x18001922b  call    ?object@value@json@web@@SA?AV123@_N@Z; web::json::value::object(bool)
0x180019230  nop
0x180019231  mov     rdx, [rbx]
0x180019234  xor     eax, eax
0x180019236  test    rdx, rdx
0x180019239  jz      short loc_180019241
0x18001923b  mov     rdx, [rdx+10h]
0x18001923f  jmp     short loc_180019248
0x180019241  lea     rdx, dword_180030C44
0x180019248  xorps   xmm0, xmm0
0x18001924b  movups  [rbp+880h+var_4B8], xmm0
0x180019252  mov     [rbp+880h+var_4A8], rax
0x180019259  mov     [rbp+880h+var_4A0], rax
0x180019260  or      r8, 0FFFFFFFFFFFFFFFFh
0x180019264  inc     r8
0x180019267  cmp     [rdx+r8*2], ax
0x18001926c  jnz     short loc_180019264
0x18001926e  lea     rcx, [rbp+880h+var_4B8]
0x180019275  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001927a  lea     rdx, [rbp+880h+var_4B8]
0x180019281  lea     rcx, [rbp+880h+var_818]
0x180019285  call    ?string@value@json@web@@SA?AV123@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::string(std::wstring)
0x18001928a  mov     rbx, rax
0x18001928d  xorps   xmm0, xmm0
0x180019290  movups  [rbp+880h+var_3D0], xmm0
0x180019297  xorps   xmm1, xmm1
0x18001929a  movdqu  [rbp+880h+var_3C0], xmm1
0x1800192a2  mov     r8d, 0Ah
0x1800192a8  lea     rdx, aProviderid; "ProviderId"
0x1800192af  lea     rcx, [rbp+880h+var_3D0]
0x1800192b6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800192bb  nop
0x1800192bc  lea     rdx, [rbp+880h+var_3D0]
0x1800192c3  lea     rcx, [rsp+980h+var_928]
0x1800192c8  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x1800192cd  mov     rcx, rax
0x1800192d0  mov     rdx, rbx
0x1800192d3  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x1800192d8  nop
0x1800192d9  lea     rcx, [rbp+880h+var_3D0]
0x1800192e0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800192e5  nop
0x1800192e6  mov     rcx, [rbp+880h+var_818]
0x1800192ea  test    rcx, rcx
0x1800192ed  jz      short loc_180019303
0x1800192ef  mov     rax, [rcx]
0x1800192f2  mov     edx, 1
0x1800192f7  mov     rax, [rax+0C0h]
0x1800192fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019303  mov     rdx, [rbp+880h+var_8B0]
0x180019307  mov     edx, [rdx]
0x180019309  lea     rcx, [rbp+880h+var_880]
0x18001930d  call    ?number@value@json@web@@SA?AV123@H@Z; web::json::value::number(int)
0x180019312  mov     rbx, rax
0x180019315  xorps   xmm0, xmm0
0x180019318  movups  [rbp+880h+var_3B0], xmm0
0x18001931f  xorps   xmm1, xmm1
0x180019322  movdqu  [rbp+880h+var_3A0], xmm1
0x18001932a  mov     r8d, 10h
0x180019330  lea     rdx, aInstallationty; "InstallationType"
0x180019337  lea     rcx, [rbp+880h+var_3B0]
0x18001933e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180019343  nop
0x180019344  lea     rdx, [rbp+880h+var_3B0]
0x18001934b  lea     rcx, [rsp+980h+var_928]
0x180019350  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x180019355  mov     rcx, rax
0x180019358  mov     rdx, rbx
0x18001935b  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x180019360  nop
0x180019361  lea     rcx, [rbp+880h+var_3B0]
0x180019368  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001936d  nop
0x18001936e  mov     rcx, [rbp+880h+var_880]
0x180019372  xor     ebx, ebx
0x180019374  test    rcx, rcx
0x180019377  jz      short loc_18001938B
0x180019379  mov     rax, [rcx]
0x18001937c  lea     edx, [rbx+1]
0x18001937f  mov     rax, [rax+0C0h]
0x180019386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001938b  mov     rax, [rdi]
0x18001938e  test    rax, rax
0x180019391  jz      short loc_180019399
0x180019393  mov     rdx, [rax+10h]
0x180019397  jmp     short loc_1800193A0
0x180019399  lea     rdx, dword_180030C44
0x1800193a0  xorps   xmm0, xmm0
0x1800193a3  movups  [rbp+880h+var_498], xmm0
0x1800193aa  mov     [rbp+880h+var_488], rbx
0x1800193b1  mov     [rbp+880h+var_480], rbx
0x1800193b8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800193bc  mov     r8, rdi
0x1800193bf  inc     r8
0x1800193c2  cmp     [rdx+r8*2], bx
0x1800193c7  jnz     short loc_1800193BF
0x1800193c9  lea     rcx, [rbp+880h+var_498]
0x1800193d0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800193d5  lea     rdx, [rbp+880h+var_498]
0x1800193dc  lea     rcx, [rbp+880h+var_820]
0x1800193e0  call    ?string@value@json@web@@SA?AV123@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::string(std::wstring)
0x1800193e5  mov     rbx, rax
0x1800193e8  xorps   xmm0, xmm0
0x1800193eb  movups  [rbp+880h+var_390], xmm0
0x1800193f2  xorps   xmm1, xmm1
0x1800193f5  movdqu  [rbp+880h+var_380], xmm1
0x1800193fd  mov     r8d, 8
0x180019403  lea     rdx, aUpdateid; "UpdateId"
0x18001940a  lea     rcx, [rbp+880h+var_390]
0x180019411  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180019416  nop
0x180019417  lea     rdx, [rbp+880h+var_390]
0x18001941e  lea     rcx, [rsp+980h+var_928]
0x180019423  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x180019428  mov     rcx, rax
0x18001942b  mov     rdx, rbx
0x18001942e  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x180019433  nop
0x180019434  lea     rcx, [rbp+880h+var_390]
0x18001943b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019440  nop
0x180019441  mov     rcx, [rbp+880h+var_820]
0x180019445  test    rcx, rcx
0x180019448  jz      short loc_18001945E
0x18001944a  mov     rax, [rcx]
0x18001944d  mov     edx, 1
0x180019452  mov     rax, [rax+0C0h]
0x180019459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001945e  mov     rax, [rsi]
0x180019461  xor     esi, esi
0x180019463  test    rax, rax
0x180019466  jz      short loc_18001946E
0x180019468  mov     rdx, [rax+10h]
0x18001946c  jmp     short loc_180019475
0x18001946e  lea     rdx, dword_180030C44
0x180019475  xorps   xmm0, xmm0
0x180019478  movups  [rbp+880h+var_6D8], xmm0
0x18001947f  mov     [rbp+880h+var_6C8], rsi
0x180019486  mov     [rbp+880h+var_6C0], rsi
0x18001948d  mov     r8, rdi
0x180019490  inc     r8
0x180019493  cmp     [rdx+r8*2], si
0x180019498  jnz     short loc_180019490
0x18001949a  lea     rcx, [rbp+880h+var_6D8]
0x1800194a1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800194a6  lea     rdx, [rbp+880h+var_6D8]
0x1800194ad  lea     rcx, [rbp+880h+var_828]
0x1800194b1  call    ?string@value@json@web@@SA?AV123@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::string(std::wstring)
0x1800194b6  mov     rbx, rax
0x1800194b9  xorps   xmm0, xmm0
0x1800194bc  movups  [rbp+880h+var_370], xmm0
0x1800194c3  xorps   xmm1, xmm1
0x1800194c6  movdqu  [rbp+880h+var_360], xmm1
0x1800194ce  mov     edi, 5
0x1800194d3  mov     r8d, edi
0x1800194d6  lea     rdx, aTitle_0; "Title"
0x1800194dd  lea     rcx, [rbp+880h+var_370]
0x1800194e4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800194e9  nop
0x1800194ea  lea     rdx, [rbp+880h+var_370]
0x1800194f1  lea     rcx, [rsp+980h+var_928]
0x1800194f6  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x1800194fb  mov     rcx, rax
0x1800194fe  mov     rdx, rbx
0x180019501  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x180019506  nop
0x180019507  lea     rcx, [rbp+880h+var_370]
0x18001950e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019513  nop
0x180019514  mov     rcx, [rbp+880h+var_828]
0x180019518  test    rcx, rcx
0x18001951b  jz      short loc_18001952F
0x18001951d  mov     rax, [rcx]
0x180019520  lea     edx, [rdi-4]
0x180019523  mov     rax, [rax+0C0h]
0x18001952a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001952f  mov     rax, [r14]
0x180019532  test    rax, rax
0x180019535  jz      short loc_18001953D
0x180019537  mov     rdx, [rax+10h]
0x18001953b  jmp     short loc_180019544
0x18001953d  lea     rdx, dword_180030C44
0x180019544  xorps   xmm0, xmm0
0x180019547  movups  [rsp+980h+var_958], xmm0
0x18001954c  mov     [rsp+980h+var_948], rsi
0x180019551  mov     [rsp+980h+var_940], rsi
0x180019556  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001955a  mov     r8, r14
0x18001955d  inc     r8
0x180019560  cmp     [rdx+r8*2], si
0x180019565  jnz     short loc_18001955D
0x180019567  lea     rcx, [rsp+980h+var_958]
0x18001956c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180019571  lea     rdx, [rsp+980h+var_958]
0x180019576  lea     rcx, [rbp+880h+var_830]
0x18001957a  call    ?string@value@json@web@@SA?AV123@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::string(std::wstring)
0x18001957f  mov     rbx, rax
0x180019582  xorps   xmm0, xmm0
0x180019585  movups  [rbp+880h+var_400], xmm0
0x18001958c  xorps   xmm1, xmm1
0x18001958f  movdqu  [rbp+880h+var_3F0], xmm1
0x180019597  mov     r8d, 0Bh
0x18001959d  lea     rdx, aDescription_0; "Description"
0x1800195a4  lea     rcx, [rbp+880h+var_400]
0x1800195ab  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800195b0  nop
0x1800195b1  lea     rdx, [rbp+880h+var_400]
0x1800195b8  lea     rcx, [rsp+980h+var_928]
0x1800195bd  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x1800195c2  mov     rcx, rax
0x1800195c5  mov     rdx, rbx
0x1800195c8  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x1800195cd  nop
0x1800195ce  lea     rcx, [rbp+880h+var_400]
0x1800195d5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800195da  nop
0x1800195db  mov     rcx, [rbp+880h+var_830]
0x1800195df  test    rcx, rcx
0x1800195e2  jz      short loc_1800195F8
0x1800195e4  mov     rax, [rcx]
0x1800195e7  mov     edx, 1
0x1800195ec  mov     rax, [rax+0C0h]
0x1800195f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195f8  lea     rdx, [rbp+880h+lpMem]
0x1800195ff  mov     rcx, r15
0x180019602  call    ?RawUri@?$consume_Windows_Foundation_IUriRuntimeClass@UIUriRuntimeClass@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::RawUri(void)
0x180019607  nop
0x180019608  mov     rdx, [rax]
0x18001960b  test    rdx, rdx
0x18001960e  jz      short loc_180019616
0x180019610  mov     rdx, [rdx+10h]
0x180019614  jmp     short loc_18001961D
0x180019616  lea     rdx, dword_180030C44
0x18001961d  xorps   xmm0, xmm0
0x180019620  movups  [rbp+880h+var_478], xmm0
0x180019627  mov     [rbp+880h+var_468], rsi
0x18001962e  mov     [rbp+880h+var_460], rsi
0x180019635  mov     r8, r14
  ... truncated ...
```
