# Windows::Telemetry::UpdateManager::UpdateAction::Stop(SystemInterface::Telemetry::CorrelationVector &,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x140276614`
- end: `0x14027a78e`
- name: `?Stop@UpdateAction@UpdateManager@Telemetry@Windows@@QEAAXAEAVCorrelationVector@3SystemInterface@@V?$basic_zstring_view@_W@wil@@11@Z`
- size: `16762`
- prototype: ``
- caller_count: `2`
- callee_count: `55`
- tags: `registry_config, installer_update`

## callers

- `0x140290a40`
- `0x140290a90`

## callees

- `0x1400017c0`
- `0x140002328`
- `0x140002338`
- `0x14000243c`
- `0x14000a334`
- `0x14000aa60`
- `0x14000af3c`
- `0x14000b650`
- `0x14000bb10`
- `0x14000c200`
- `0x14000c6bc`
- `0x14000cd94`
- `0x140021164`
- `0x140021474`
- `0x140024de0`
- `0x1400288b0`
- `0x140029f90`
- `0x14002a224`
- `0x14002a244`
- `0x14002a258`
- `0x14002a7d8`
- `0x14002cac0`
- `0x14002cc08`
- `0x14003f448`
- `0x140044c68`
- `0x140044f20`
- `0x140045170`
- `0x140045404`
- `0x140045688`
- `0x14004594c`
- `0x140049bc8`
- `0x140050700`
- `0x140078ed4`
- `0x14007940c`
- `0x1400794d8`
- `0x140079b44`
- `0x140079c7c`
- `0x1400aa570`
- `0x1400aa590`
- `0x1400b54c0`
- `0x1400c1d98`
- `0x1400c74d0`
- `0x14011bf34`
- `0x14012d7d8`
- `0x140183608`
- `0x140268c70`
- `0x140268cbc`
- `0x140276614`
- `0x14029bf6c`
- `0x14029c0ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14027758e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140278591`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14027952b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14027a419`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14027758e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140278591`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14027952b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14027a419`

## pseudocode

```c
// Hidden C++ exception states: #wind=165
void __fastcall Windows::Telemetry::UpdateManager::UpdateAction::Stop(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        __int64 a5)
{
  __int64 v7; // rdi
  __int16 v8; // r14
  Update **v9; // rsi
  __int64 v10; // rax
  __int64 System; // rax
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  _BYTE *v17; // r13
  __int64 v18; // rax
  __int64 v19; // rax
  const struct _tlgProvider_t *v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // r8
  __int64 v34; // rax
  __int64 v35; // rax
  unsigned int v36; // eax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // r8
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rbx
  __int64 v48; // rbx
  const OLECHAR *v49; // r15
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rax
  Update *v62; // rax
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // rbx
  __int64 v75; // r13
  __int64 v76; // r12
  __int64 v77; // r15
  __int64 v78; // r14
  __int64 v79; // rsi
  __int64 v80; // rdi
  __int64 v81; // rbx
  int v82; // eax
  __int128 *v83; // rcx
  const struct _tlgProvider_t *v84; // rax
  _QWORD *v85; // rax
  _QWORD *v86; // rax
  __int64 v87; // rax
  __int64 v88; // rax
  __int64 v89; // rax
  __int64 v90; // rax
  __int64 v91; // rcx
  _QWORD *v92; // rax
  int v93; // eax
  int v94; // eax
  const wchar_t *v95; // rax
  __int64 v96; // rax
  __int64 v97; // rcx
  _QWORD *v98; // rax
  __int64 v99; // rax
  int v100; // ecx
  const wchar_t *v101; // rax
  Update *v102; // rbx
  __int64 v103; // rbx
  const OLECHAR *v104; // r15
  __int64 v105; // rax
  __int64 v106; // rax
  __int64 v107; // rax
  __int64 v108; // rax
  __int64 v109; // rax
  __int64 v110; // rax
  __int64 v111; // rax
  __int64 v112; // rax
  __int64 v113; // rax
  __int64 v114; // rax
  __int64 v115; // rax
  __int64 v116; // r8
  std::_Ref_count_base *v117; // rcx
  const struct _tlgProvider_t *v118; // rax
  __int64 v119; // rax
  __int64 v120; // rax
  __int64 v121; // rax
  __int64 v122; // rax
  __int64 v123; // rax
  __int64 v124; // rax
  __int64 v125; // rax
  __int64 v126; // rax
  __int64 v127; // rax
  __int64 v128; // rax
  __int64 v129; // rax
  __int64 v130; // rax
  __int64 v131; // rcx
  __int64 v132; // rax
  __int64 v133; // rax
  unsigned int v134; // eax
  __int64 v135; // rax
  __int64 v136; // rax
  __int64 v137; // rax
  __int64 v138; // rcx
  __int64 v139; // rax
  __int64 v140; // rax
  __int64 v141; // rax
  __int64 v142; // rax
  __int64 v143; // rax
  __int64 v144; // rax
  __int64 v145; // rbx
  __int64 v146; // rbx
  const OLECHAR *v147; // r15
  __int64 v148; // rax
  __int64 v149; // rax
  __int64 v150; // rax
  __int64 v151; // rax
  __int64 v152; // rax
  __int64 v153; // rax
  __int64 v154; // rax
  __int64 v155; // rax
  __int64 v156; // rax
  __int64 v157; // rax
  __int64 v158; // rax
  __int64 v159; // rax
  Update *v160; // rax
  __int64 v161; // rax
  __int64 v162; // rax
  __int64 v163; // rax
  __int64 v164; // rax
  __int64 v165; // rax
  __int64 v166; // rax
  __int64 v167; // rax
  __int64 v168; // rax
  __int64 v169; // rax
  __int64 v170; // rax
  __int64 v171; // rax
  __int64 v172; // rbx
  __int64 v173; // r13
  __int64 v174; // r12
  __int64 v175; // r15
  __int64 v176; // r14
  __int64 v177; // rsi
  __int64 v178; // rdi
  __int64 v179; // rbx
  int v180; // eax
  const struct _tlgProvider_t *v181; // rax
  _QWORD *v182; // rax
  _QWORD *v183; // rax
  __int64 v184; // rax
  __int64 v185; // rax
  __int64 v186; // rax
  __int64 v187; // rax
  __int64 v188; // rcx
  _QWORD *v189; // rax
  int v190; // eax
  int v191; // eax
  const wchar_t *v192; // rax
  __int64 v193; // rax
  __int64 v194; // rcx
  _QWORD *v195; // rax
  __int64 v196; // rax
  int v197; // ecx
  const wchar_t *v198; // rax
  Update *v199; // rbx
  __int64 v200; // rbx
  const OLECHAR *v201; // r15
  __int64 v202; // rax
  __int64 v203; // rax
  __int64 v204; // rax
  __int64 v205; // rax
  __int64 v206; // rax
  __int64 v207; // rax
  __int64 v208; // rax
  __int64 v209; // rax
  __int64 v210; // rax
  __int64 v211; // rax
  __int64 v212; // rax
  __int64 v213; // r8
  __int64 v214; // rax
  const struct _tlgProvider_t *v215; // rax
  __int64 v216; // rax
  __int64 v217; // rax
  __int64 v218; // rax
  __int64 v219; // rax
  __int64 v220; // rax
  __int64 v221; // rax
  __int64 v222; // rcx
  __int64 v223; // rax
  __int64 v224; // rax
  unsigned int v225; // eax
  __int64 v226; // rax
  __int64 v227; // rax
  __int64 v228; // rax
  __int64 v229; // rcx
  __int64 v230; // rax
  __int64 v231; // rax
  __int64 v232; // rax
  __int64 v233; // rax
  __int64 v234; // rax
  __int64 v235; // rax
  __int64 v236; // rbx
  __int64 v237; // rbx
  const OLECHAR *v238; // r15
  __int64 v239; // rax
  __int64 v240; // rax
  __int64 v241; // rax
  __int64 v242; // rax
  __int64 v243; // rax
  __int64 v244; // rax
  __int64 v245; // rax
  __int64 v246; // rax
  __int64 v247; // rax
  __int64 v248; // rax
  __int64 v249; // rax
  __int64 v250; // rax
  Update *v251; // rax
  __int64 v252; // rax
  __int64 v253; // rax
  __int64 v254; // rax
  __int64 v255; // rax
  __int64 v256; // rax
  __int64 v257; // rax
  __int64 v258; // rax
  __int64 v259; // rax
  __int64 v260; // rax
  __int64 v261; // rax
  __int64 v262; // rax
  __int64 v263; // rbx
  __int64 v264; // r13
  __int64 v265; // r12
  __int64 v266; // r15
  __int64 v267; // r14
  __int64 v268; // rsi
  __int64 v269; // rdi
  __int64 v270; // rbx
  int v271; // eax
  const struct _tlgProvider_t *v272; // rax
  __int64 v273; // rax
  __int64 v274; // rax
  __int64 v275; // rax
  __int64 v276; // rcx
  _QWORD *v277; // rax
  int v278; // eax
  int v279; // eax
  const wchar_t *v280; // rax
  __int64 v281; // rax
  __int64 v282; // rcx
  _QWORD *v283; // rax
  __int64 v284; // rax
  int v285; // ecx
  const wchar_t *v286; // rax
  Update *v287; // rbx
  __int64 MetadataValue; // rbx
  const OLECHAR *v289; // r15
  __int64 v290; // rax
  __int64 v291; // rax
  __int64 v292; // rax
  __int64 v293; // rax
  __int64 v294; // rax
  __int64 v295; // rax
  __int64 v296; // rax
  __int64 v297; // rax
  __int64 v298; // rax
  __int64 v299; // rax
  __int64 v300; // rax
  __int64 v301; // r8
  const struct _tlgProvider_t *v302; // rax
  __int64 v303; // rax
  __int64 v304; // rax
  __int64 v305; // rax
  __int64 v306; // rax
  __int64 v307; // rax
  __int64 v308; // rax
  __int64 v309; // rcx
  __int64 v310; // rax
  __int64 v311; // rax
  unsigned int v312; // eax
  __int64 v313; // rax
  __int64 v314; // rax
  __int64 v315; // rax
  __int64 v316; // rcx
  __int64 v317; // rax
  __int64 v318; // rax
  __int64 v319; // rax
  __int64 v320; // rax
  __int64 v321; // rax
  __int64 v322; // rax
  __int64 v323; // rbx
  __int64 v324; // rbx
  const OLECHAR *v325; // r15
  __int64 v326; // rax
  __int64 v327; // rax
  __int64 v328; // rax
  __int64 v329; // rax
  __int64 v330; // rax
  __int64 v331; // rax
  __int64 v332; // rax
  __int64 v333; // rax
  __int64 v334; // rax
  __int64 v335; // rax
  __int64 v336; // rax
  __int64 v337; // rax
  Update *v338; // rax
  __int64 v339; // rax
  __int64 v340; // rax
  __int64 v341; // rax
  __int64 v342; // rax
  __int64 v343; // rax
  __int64 v344; // rax
  __int64 v345; // rax
  __int64 v346; // rax
  __int64 v347; // rax
  __int64 v348; // rax
  __int64 v349; // rax
  __int64 v350; // rbx
  __int64 v351; // r13
  __int64 v352; // r12
  __int64 v353; // r15
  __int64 v354; // r14
  __int64 v355; // rsi
  __int64 v356; // rdi
  __int64 v357; // rbx
  int v358; // eax
  const struct _tlgProvider_t *v359; // rax
  __int64 v360; // rax
  __int64 v361; // rax
  __int64 v362; // rax
  __int64 v363; // rcx
  _QWORD *v364; // rax
  int v365; // eax
  int v366; // eax
  const wchar_t *v367; // rax
  __int64 v368; // rax
  __int64 v369; // rcx
  _QWORD *v370; // rax
  __int64 v371; // rax
  int v372; // ecx
  const wchar_t *v373; // rax
  Update *v374; // rbx
  __int64 v375; // rbx
  const OLECHAR *v376; // r15
  __int64 v377; // rax
  __int64 v378; // rax
  __int64 v379; // rax
  __int64 v380; // rax
  __int64 v381; // rax
  __int64 v382; // rax
  __int64 v383; // rax
  __int64 v384; // rax
  __int64 v385; // rax
  __int64 v386; // rax
  __int64 v387; // rax
  __int64 v388; // r8
  _BYTE v389[4]; // [rsp+170h] [rbp-80h] BYREF
  int v390; // [rsp+174h] [rbp-7Ch] BYREF
  int v391; // [rsp+178h] [rbp-78h] BYREF
  int v392; // [rsp+17Ch] [rbp-74h] BYREF
  int v393; // [rsp+180h] [rbp-70h] BYREF
  int v394; // [rsp+184h] [rbp-6Ch] BYREF
  int v395; // [rsp+188h] [rbp-68h] BYREF
  DWORD CurrentThreadId; // [rsp+18Ch] [rbp-64h] BYREF
  DWORD v397; // [rsp+190h] [rbp-60h] BYREF
  int v398; // [rsp+194h] [rbp-5Ch] BYREF
  int v399; // [rsp+198h] [rbp-58h]
  _DWORD v400[3]; // [rsp+19Ch] [rbp-54h] BYREF
  __int64 v401; // [rsp+1A8h] [rbp-48h] BYREF
  __int64 v402; // [rsp+1B0h] [rbp-40h] BYREF
  int v403; // [rsp+1B8h] [rbp-38h] BYREF
  int v404; // [rsp+1BCh] [rbp-34h] BYREF
  int v405; // [rsp+1C0h] [rbp-30h] BYREF
  BOOL v406; // [rsp+1C4h] [rbp-2Ch] BYREF
  int v407; // [rsp+1C8h] [rbp-28h] BYREF
  int v408; // [rsp+1CCh] [rbp-24h] BYREF
  int v409; // [rsp+1D0h] [rbp-20h] BYREF
  int v410; // [rsp+1D4h] [rbp-1Ch] BYREF
  int v411; // [rsp+1D8h] [rbp-18h] BYREF
  int v412; // [rsp+1DCh] [rbp-14h] BYREF
  __int64 v413; // [rsp+1E0h] [rbp-10h] BYREF
  __int64 v414; // [rsp+1E8h] [rbp-8h] BYREF
  __int64 v415; // [rsp+1F0h] [rbp+0h] BYREF
  __int64 v416; // [rsp+1F8h] [rbp+8h] BYREF
  __int64 v417; // [rsp+200h] [rbp+10h] BYREF
  __int64 v418; // [rsp+208h] [rbp+18h] BYREF
  __int64 v419; // [rsp+210h] [rbp+20h] BYREF
  __int64 v420; // [rsp+218h] [rbp+28h] BYREF
  __int64 v421; // [rsp+220h] [rbp+30h] BYREF
  __int64 v422; // [rsp+228h] [rbp+38h] BYREF
  __int64 v423; // [rsp+230h] [rbp+40h] BYREF
  __int64 v424; // [rsp+238h] [rbp+48h] BYREF
  __int64 v425; // [rsp+240h] [rbp+50h] BYREF
  __int64 v426; // [rsp+248h] [rbp+58h] BYREF
  __int64 v427; // [rsp+250h] [rbp+60h] BYREF
  __int64 FailureInfo; // [rsp+258h] [rbp+68h]
  __int64 v429; // [rsp+260h] [rbp+70h] BYREF
  __int64 v430; // [rsp+268h] [rbp+78h] BYREF
  __int64 v431; // [rsp+270h] [rbp+80h]
  __int64 v432; // [rsp+278h] [rbp+88h]
  __int64 v433; // [rsp+280h] [rbp+90h] BYREF
  __int64 v434; // [rsp+288h] [rbp+98h]
  __int64 v435[2]; // [rsp+290h] [rbp+A0h] BYREF
  _OWORD pExceptionObject[2]; // [rsp+2A0h] [rbp+B0h] BYREF
  int v437; // [rsp+2C0h] [rbp+D0h] BYREF
  _BYTE v438[4]; // [rsp+2C4h] [rbp+D4h] BYREF
  _BYTE v439[4]; // [rsp+2C8h] [rbp+D8h] BYREF
  _BYTE v440[4]; // [rsp+2CCh] [rbp+DCh] BYREF
  __int64 v441; // [rsp+2D0h] [rbp+E0h] BYREF
  __int64 v442; // [rsp+2D8h] [rbp+E8h] BYREF
  __int64 v443; // [rsp+2E0h] [rbp+F0h] BYREF
  __int64 v444; // [rsp+2E8h] [rbp+F8h] BYREF
  __int64 v445; // [rsp+2F0h] [rbp+100h] BYREF
  int v446[2]; // [rsp+2F8h] [rbp+108h] BYREF
  _BYTE v447[8]; // [rsp+300h] [rbp+110h] BYREF
  std::_Ref_count_base *v448; // [rsp+308h] [rbp+118h]
  _BYTE v449[8]; // [rsp+310h] [rbp+120h] BYREF
  std::_Ref_count_base *v450; // [rsp+318h] [rbp+128h]
  _BYTE v451[8]; // [rsp+320h] [rbp+130h] BYREF
  std::_Ref_count_base *v452; // [rsp+328h] [rbp+138h]
  _BYTE v453[8]; // [rsp+330h] [rbp+140h] BYREF
  std::_Ref_count_base *v454; // [rsp+338h] [rbp+148h]
  __int128 v455; // [rsp+340h] [rbp+150h] BYREF
  __int64 v456; // [rsp+350h] [rbp+160h] BYREF
  _BYTE v457[16]; // [rsp+358h] [rbp+168h] BYREF
  _BYTE v458[8]; // [rsp+368h] [rbp+178h] BYREF
  _BYTE v459[8]; // [rsp+370h] [rbp+180h] BYREF
  _BYTE v460[8]; // [rsp+378h] [rbp+188h] BYREF
  _BYTE v461[8]; // [rsp+380h] [rbp+190h] BYREF
  _BYTE v462[8]; // [rsp+388h] [rbp+198h] BYREF
  _BYTE v463[8]; // [rsp+390h] [rbp+1A0h] BYREF
  _BYTE v464[8]; // [rsp+398h] [rbp+1A8h] BYREF
  _BYTE v465[8]; // [rsp+3A0h] [rbp+1B0h] BYREF
  _BYTE v466[8]; // [rsp+3A8h] [rbp+1B8h] BYREF
  _BYTE v467[8]; // [rsp+3B0h] [rbp+1C0h] BYREF
  _BYTE v468[8]; // [rsp+3B8h] [rbp+1C8h] BYREF
  _BYTE v469[8]; // [rsp+3C0h] [rbp+1D0h] BYREF
  _BYTE v470[8]; // [rsp+3C8h] [rbp+1D8h] BYREF
  _BYTE v471[8]; // [rsp+3D0h] [rbp+1E0h] BYREF
  _BYTE v472[8]; // [rsp+3D8h] [rbp+1E8h] BYREF
  _BYTE v473[8]; // [rsp+3E0h] [rbp+1F0h] BYREF
  std::_Ref_count_base *v474; // [rsp+3E8h] [rbp+1F8h]
  _BYTE v475[8]; // [rsp+3F0h] [rbp+200h] BYREF
  std::_Ref_count_base *v476; // [rsp+3F8h] [rbp+208h]
  _BYTE v477[8]; // [rsp+400h] [rbp+210h] BYREF
  std::_Ref_count_base *v478; // [rsp+408h] [rbp+218h]
  _BYTE v479[8]; // [rsp+410h] [rbp+220h] BYREF
  _BYTE v480[8]; // [rsp+418h] [rbp+228h] BYREF
  _BYTE v481[8]; // [rsp+420h] [rbp+230h] BYREF
  _BYTE v482[8]; // [rsp+428h] [rbp+238h] BYREF
  _BYTE v483[8]; // [rsp+430h] [rbp+240h] BYREF
  _BYTE v484[8]; // [rsp+438h] [rbp+248h] BYREF
  _BYTE v485[32]; // [rsp+440h] [rbp+250h] BYREF
  _BYTE v486[32]; // [rsp+460h] [rbp+270h] BYREF
  _BYTE v487[32]; // [rsp+480h] [rbp+290h] BYREF
  _BYTE v488[32]; // [rsp+4A0h] [rbp+2B0h] BYREF
  _BYTE v489[32]; // [rsp+4C0h] [rbp+2D0h] BYREF
  _BYTE v490[32]; // [rsp+4E0h] [rbp+2F0h] BYREF
  _BYTE v491[32]; // [rsp+500h] [rbp+310h] BYREF
  _BYTE v492[32]; // [rsp+520h] [rbp+330h] BYREF
  _BYTE v493[32]; // [rsp+540h] [rbp+350h] BYREF
  int v494; // [rsp+560h] [rbp+370h] BYREF
  char v495; // [rsp+564h] [rbp+374h]
  _BYTE v496[16]; // [rsp+568h] [rbp+378h] BYREF
  char v497; // [rsp+578h] [rbp+388h]
  _BYTE v498[8]; // [rsp+580h] [rbp+390h] BYREF

  v432 = a3;
  v7 = a1;
  v434 = a1;
  v8 = 0;
  v399 = 0;
  v9 = (Update **)(a1 + 352);
  v10 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(a1 + 352);
  (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v10 + 296LL))(v10, v496);
  System = SystemInterface::Providers::GetSystem(v473);
  v12 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(System);
  v13 = *(int *)(*(_QWORD *)(v12 + 8) + 4LL) + v12 + 8;
  v14 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v13 + 56LL))(v13, v457);
  v15 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v14);
  (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v15 + 48LL))(v15, v498);
  std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v457);
  std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v473);
  v16 = std::wstreambuf::setbuf(v498);
  v17 = (_BYTE *)std::wstreambuf::setbuf(v16);
  v18 = std::wstreambuf::setbuf(v498);
  v431 = std::get<1,bool,int>(v18);
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl'::`2'::impl);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::GetImpl'::`2'::impl);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::GetImpl'::`2'::impl) )
    {
      v214 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      Update::GetExtendedErrorResult(v214, &v494);
      FailureInfo = wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(v7);
      if ( !FailureInfo )
      {
        wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(v7);
        v272 = Windows::Telemetry::Base::Provider();
        v413 = (__int64)v272;
        if ( *(_DWORD *)v272 > 5u
          && (*((_QWORD *)v272 + 2) & 0x400000000000LL) != 0
          && (*((_QWORD *)v272 + 3) & 0x400000000000LL) == *((_QWORD *)v272 + 3) )
        {
          v433 = (__int64)"1507.2603.28012.0";
          v395 = *(_DWORD *)v431;
          v389[0] = *v17;
          v273 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 8LL))(a2, v485);
          v419 = std::string::c_str(v273);
          v420 = v7 + 416;
          v422 = *a4;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl) )
            v274 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(a5);
          else
            v274 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v7 + 384);
          v423 = v274;
          v275 = SystemInterface::Providers::GetSystem(v449);
          v276 = *(_QWORD *)v275 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v275 + 8LL) + 4LL);
          v277 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v276 + 96LL))(v276, v451);
          v278 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v277 + 8LL))(*v277);
          if ( v278 )
          {
            v279 = v278 - 1;
            if ( v279 )
            {
              if ( v279 != 1 )
              {
                std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
                throw (std::logic_error *)pExceptionObject;
              }
              v280 = L"Internet";
            }
            else
            {
              v280 = L"local only";
            }
          }
          else
          {
            v280 = L"none";
          }
          v424 = (__int64)v280;
          v281 = SystemInterface::Providers::GetSystem(v453);
          v282 = *(_QWORD *)v281 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v281 + 8LL) + 4LL);
          v283 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v282 + 8LL))(v282, v447);
          v435[0] = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v283 + 104LL))(*v283)
                  - (unsigned __int64)*(unsigned int *)(v7 + 344);
          v284 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v7 + 328) + 8LL))(
                   *(_QWORD *)(v7 + 328),
                   v457);
          std::chrono::duration_cast<std::chrono::duration<int,std::ratio<60,1>>,__int64,std::ratio<1,1000000>,0>(
            &v392,
            v284);
          v394 = v392;
          v393 = v495 != 0 ? v494 : 0;
          v425 = *(_QWORD *)v432;
          v285 = *(_DWORD *)(v7 + 380);
          if ( v285 )
          {
            if ( v285 != 1 )
            {
              std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Unknown action priority");
              throw (std::logic_error *)pExceptionObject;
            }
            v286 = L"Low";
          }
          else
          {
            v286 = L"Normal";
          }
          v426 = (__int64)v286;
          v391 = *(unsigned __int8 *)(v7 + 376);
          v287 = *v9;
          pExceptionObject[0] = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v492, L"id");
          MetadataValue = Update::GetMetadataValue(v287, &v455, pExceptionObject);
          v289 = &psz;
          v290 = web::json::value::value((web::json::value *)&v401, &psz);
          v291 = std::optional<web::json::value>::value_or<web::json::value>(MetadataValue, &v402, v290);
          v292 = web::json::value::as_string(v291);
          v427 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v292);
          v293 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 48LL))(*v9, v486);
          *(_QWORD *)&v400[1] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v293);
          v294 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 32LL))(*v9, v487);
          v421 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v294);
          v390 = (*(unsigned __int8 (__fastcall **)(Update *))(*(_QWORD *)*v9 + 640LL))(*v9);
          v398 = (*(unsigned __int8 (__fastcall **)(Update *))(*(_QWORD *)*v9 + 552LL))(*v9);
          v397 = Update::Seeker(*v9);
          v295 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 24LL))(*v9, v488);
          v418 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v295);
          if ( v497 )
          {
            v296 = std::optional<std::shared_ptr<Action>>::value(v496);
            v297 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v296);
            v298 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v297 + 8LL))(v297, v489);
            v8 = 256;
            v399 = 256;
            v289 = (const OLECHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v298);
          }
          v417 = (__int64)v289;
          v299 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v7 + 368) + 8LL))(
                   *(_QWORD *)(v7 + 368),
                   v490);
          v416 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v299);
          v300 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 8LL))(*v9, v491);
          v415 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v300);
          CurrentThreadId = GetCurrentThreadId();
          v301 = *(_QWORD *)(v7 + 272);
          v400[0] = *(_DWORD *)(v301 + 72);
          v414 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v413,
            (int)&byte_14049E1A1,
            v301 + 8,
            (__int64)&v414,
            (__int64)v400,
            (__int64)&CurrentThreadId,
            (__int64)&v415,
            (__int64)&v416,
            (__int64)&v417,
            (__int64)&v418,
            (__int64)&v397,
            (__int64)&v398,
            (__int64)&v390,
            (__int64)&v421,
            (__int64)&v400[1],
            (__int64)&v427,
            (__int64)&v391,
            (__int64)&v426,
            (__int64)&v425,
            (__int64)&v393,
            (__int64)&v394,
            (__int64)v435,
            (__int64)&v424,
            (__int64)&v423,
            (__int64)&v422,
            (__int64)&v420,
            (__int64)&v419,
            (__int64)v389,
            (__int64)&v395,
            (__int64)&v433);
          std::wstring::~wstring(v491);
          std::wstring::~wstring(v490);
          if ( (v8 & 0x100) != 0 )
            std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v489);
          std::wstring::~wstring(v488);
          std::wstring::~wstring(v487);
          std::wstring::~wstring(v486);
          std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v402);
          std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v401);
          std::_Optional_construct_base<web::json::value>::~_Optional_construct_base<web::json::value>(&v455);
          if ( v448 )
            std::_Ref_count_base::_Decref(v448);
          if ( v454 )
            std::_Ref_count_base::_Decref(v454);
          if ( v452 )
            std::_Ref_count_base::_Decref(v452);
          if ( v450 )
            std::_Ref_count_base::_Decref(v450);
          std::string::_Tidy_deallocate(v485);
        }
        goto LABEL_169;
      }
      wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(v7);
      v215 = Windows::Telemetry::Base::Provider();
      v445 = (__int64)v215;
      if ( *(_DWORD *)v215 <= 5u
        || (*((_QWORD *)v215 + 2) & 0x400000000000LL) == 0
        || (*((_QWORD *)v215 + 3) & 0x400000000000LL) != *((_QWORD *)v215 + 3) )
      {
        goto LABEL_169;
      }
      v422 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v457,
               "1507.2603.28012.0");
      v423 = _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v440, v431);
      v424 = _tlgWrapAuto<bool>(v389, v17);
      v216 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 8LL))(a2, v485);
      v217 = std::string::c_str(v216);
      v435[0] = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                  v473,
                  v217);
      winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
        &v425,
        v7 + 416);
      v218 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(a4);
      v426 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v472,
               v218);
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl) )
        v219 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(a5);
      else
        v219 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v7 + 384);
      v427 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v471,
               v219);
      v220 = SystemInterface::Providers::GetSystem(v449);
      v221 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v220);
      v222 = *(int *)(*(_QWORD *)(v221 + 8) + 4LL) + v221 + 8;
      v223 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v222 + 96LL))(v222, v451);
      v224 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v223);
      v225 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v224 + 8LL))(v224);
      v226 = SystemInterface::to_wstring(v225);
      *(_QWORD *)&v400[1] = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                              v470,
                              v226);
      v227 = SystemInterface::Providers::GetSystem(v453);
      v228 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v227);
      v229 = *(int *)(*(_QWORD *)(v228 + 8) + 4LL) + v228 + 8;
      v230 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v229 + 8LL))(v229, v447);
      v231 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v230);
      v419 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v231 + 104LL))(v231)
           - (unsigned __int64)*(unsigned int *)(v7 + 344);
      v421 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(
               v469,
               &v419);
      v232 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v7 + 328);
      v233 = SystemInterface::Timer::Elapsed<std::chrono::duration<int,std::ratio<60,1>>>(v232, v439);
      v392 = std::chrono::duration<int,std::ratio<60,1>>::count(v233);
      v418 = _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v438, &v392);
      v395 = 0;
      v394 = std::optional<long>::value_or<long>(&v494, &v395);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v412, &v394);
      v234 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v432);
      v417 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v482,
               v234);
      v235 = to_wstring(*(unsigned int *)(v7 + 380));
      v416 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v468,
               v235);
      v393 = *(unsigned __int8 *)(v7 + 376);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v409, &v393);
      v236 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      pExceptionObject[0] = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v492, L"id");
      v237 = Update::GetMetadataValue(v236, &v455, pExceptionObject);
      v238 = &psz;
      v239 = web::json::value::value((web::json::value *)&v433, &psz);
      v240 = std::optional<web::json::value>::value_or<web::json::value>(v237, v446, v239);
      v241 = web::json::value::as_string(v240);
      v242 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v241);
      v415 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v467,
               v242);
      v243 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v244 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v243 + 48LL))(v243, v486);
      v245 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v244);
      v414 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v466,
               v245);
      v246 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v247 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v246 + 32LL))(v246, v487);
      v248 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v247);
      v413 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v465,
               v248);
      v249 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v391 = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v249 + 640LL))(v249);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v408, &v391);
      v250 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v390 = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v250 + 552LL))(v250);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v407, &v390);
      v251 = (Update *)std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v398 = Update::Seeker(v251);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v406, &v398);
      v252 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v253 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v252 + 24LL))(v252, v488);
      v254 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v253);
      v402 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v464,
               v254);
      if ( (unsigned __int8)std::optional<std::shared_ptr<Action>>::has_value(v496) )
      {
        v255 = std::optional<std::shared_ptr<Action>>::value(v496);
        v256 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v255);
        v257 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v256 + 8LL))(v256, v489);
        v399 = 64;
        v238 = (const OLECHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v257);
      }
      v401 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v463,
               v238);
      v258 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v7 + 368) + 8LL))(*(_QWORD *)(v7 + 368), v490);
      v259 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v258);
      v429 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v462,
               v259);
      v260 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v261 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v260 + 8LL))(v260, v491);
      v262 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v261);
      v430 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v461,
               v262);
      v263 = FailureInfo;
      v442 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v460,
               *(_QWORD *)(FailureInfo + 120));
      v264 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v459,
               *(_QWORD *)(v263 + 112));
      v397 = *(_DWORD *)(v263 + 104);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v405, &v397);
      v265 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v458,
               *(_QWORD *)(v263 + 96));
      v266 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v484,
               *(_QWORD *)(v263 + 88));
      CurrentThreadId = *(_DWORD *)(v263 + 80);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v404, &CurrentThreadId);
      v267 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v483,
               *(_QWORD *)(v263 + 72));
      v400[0] = *(_DWORD *)(v263 + 32);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v403, v400);
      v268 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v481,
               *(_QWORD *)(v263 + 24));
      v411 = *(_DWORD *)v263;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v456, &v411);
      v269 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v480,
               *(_QWORD *)(v263 + 128));
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v437, v263 + 64);
      v270 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v479,
               *(_QWORD *)(v263 + 56));
      v410 = *(_DWORD *)(FailureInfo + 8);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v441, &v410);
      v420 = 0x1000000;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(
        &v443,
        &v420);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(
        &v444,
        &`Windows::Telemetry::UpdateManager::UpdateAction::Stop'::`85'::_tlgActivityPrivacyTag);
      v271 = wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Id(v434);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v445,
        (int)&byte_14049E94B,
        v271,
        (__int64)&v444,
        (__int64)&v443,
        (__int64)&v441,
        v270,
        (__int64)&v437,
        v269,
        (__int64)&v456,
        v268,
        (__int64)&v403,
        v267,
        (__int64)&v404,
        v266,
        v265,
        (__int64)&v405,
        v264,
        v442,
        v430,
        v429,
        v401,
        v402,
        (__int64)&v406,
        (__int64)&v407,
        (__int64)&v408,
        v413,
        v414,
        v415,
        (__int64)&v409,
        v416,
        v417,
        (__int64)&v412,
        v418,
        v421,
        *(__int64 *)&v400[1],
        v427,
        v426,
        (__int64)&v425,
        v435[0],
        v424,
        v423,
        v422);
      std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v491);
      std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v490);
      if ( (v399 & 0x40) != 0 )
        std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v489);
      std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v488);
      std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v487);
      std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v486);
      std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(v446);
      std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v433);
      std::_Optional_construct_base<web::json::value>::~_Optional_construct_base<web::json::value>(&v455);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v447);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v453);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v451);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v449);
    }
    else
    {
      FailureInfo = wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(v7);
      if ( !FailureInfo )
      {
        wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(v7);
        v359 = Windows::Telemetry::Base::Provider();
        v413 = (__int64)v359;
        if ( *(_DWORD *)v359 > 5u
          && (*((_QWORD *)v359 + 2) & 0x400000000000LL) != 0
          && (*((_QWORD *)v359 + 3) & 0x400000000000LL) == *((_QWORD *)v359 + 3) )
        {
          v433 = (__int64)"1507.2603.28012.0";
          v395 = *(_DWORD *)v431;
          v389[0] = *v17;
          v360 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 8LL))(a2, v485);
          v419 = std::string::c_str(v360);
          v420 = v7 + 416;
          v422 = *a4;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl) )
            v361 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(a5);
          else
            v361 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v7 + 384);
          v423 = v361;
          v362 = SystemInterface::Providers::GetSystem(v449);
          v363 = *(_QWORD *)v362 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v362 + 8LL) + 4LL);
          v364 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v363 + 96LL))(v363, v451);
          v365 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v364 + 8LL))(*v364);
          if ( v365 )
          {
            v366 = v365 - 1;
            if ( v366 )
            {
              if ( v366 != 1 )
              {
                std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
                throw (std::logic_error *)pExceptionObject;
              }
              v367 = L"Internet";
            }
            else
            {
              v367 = L"local only";
            }
          }
          else
          {
            v367 = L"none";
          }
          v424 = (__int64)v367;
          v368 = SystemInterface::Providers::GetSystem(v453);
          v369 = *(_QWORD *)v368 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v368 + 8LL) + 4LL);
          v370 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v369 + 8LL))(v369, v447);
          v435[0] = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v370 + 104LL))(*v370)
                  - (unsigned __int64)*(unsigned int *)(v7 + 344);
          v371 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v7 + 328) + 8LL))(
                   *(_QWORD *)(v7 + 328),
                   v457);
          std::chrono::duration_cast<std::chrono::duration<int,std::ratio<60,1>>,__int64,std::ratio<1,1000000>,0>(
            &v392,
            v371);
          v394 = v392;
          v425 = *(_QWORD *)v432;
          v372 = *(_DWORD *)(v7 + 380);
          if ( v372 )
          {
            if ( v372 != 1 )
            {
              std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Unknown action priority");
              throw (std::logic_error *)pExceptionObject;
            }
            v373 = L"Low";
          }
          else
          {
            v373 = L"Normal";
          }
          v426 = (__int64)v373;
          v393 = *(unsigned __int8 *)(v7 + 376);
          v374 = *v9;
          pExceptionObject[0] = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v492, L"id");
          v375 = Update::GetMetadataValue(v374, &v455, pExceptionObject);
          v376 = &psz;
          v377 = web::json::value::value((web::json::value *)&v401, &psz);
          v378 = std::optional<web::json::value>::value_or<web::json::value>(v375, &v402, v377);
          v379 = web::json::value::as_string(v378);
          v427 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v379);
          v380 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 48LL))(*v9, v486);
          *(_QWORD *)&v400[1] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v380);
          v381 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 32LL))(*v9, v487);
          v421 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v381);
          v391 = (*(unsigned __int8 (__fastcall **)(Update *))(*(_QWORD *)*v9 + 640LL))(*v9);
          v390 = (*(unsigned __int8 (__fastcall **)(Update *))(*(_QWORD *)*v9 + 552LL))(*v9);
          v398 = Update::Seeker(*v9);
          v382 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 24LL))(*v9, v488);
          v418 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v382);
          if ( v497 )
          {
            v383 = std::optional<std::shared_ptr<Action>>::value(v496);
            v384 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v383);
            v385 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v384 + 8LL))(v384, v489);
            v8 = 2048;
            v399 = 2048;
            v376 = (const OLECHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v385);
          }
          v417 = (__int64)v376;
          v386 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v7 + 368) + 8LL))(
                   *(_QWORD *)(v7 + 368),
                   v490);
          v416 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v386);
          v387 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 8LL))(*v9, v491);
          v415 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v387);
          v397 = GetCurrentThreadId();
          v388 = *(_QWORD *)(v7 + 272);
          CurrentThreadId = *(_DWORD *)(v388 + 72);
          v414 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v413,
            (int)&byte_14049DECD,
            v388 + 8,
            (__int64)&v414,
            (__int64)&CurrentThreadId,
            (__int64)&v397,
            (__int64)&v415,
            (__int64)&v416,
            (__int64)&v417,
            (__int64)&v418,
            (__int64)&v398,
            (__int64)&v390,
            (__int64)&v391,
            (__int64)&v421,
            (__int64)&v400[1],
            (__int64)&v427,
            (__int64)&v393,
            (__int64)&v426,
            (__int64)&v425,
            (__int64)&v394,
            (__int64)v435,
            (__int64)&v424,
            (__int64)&v423,
            (__int64)&v422,
            (__int64)&v420,
            (__int64)&v419,
            (__int64)v389,
            (__int64)&v395,
            (__int64)&v433);
          std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v491);
          std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v490);
          if ( (v8 & 0x800) != 0 )
            std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v489);
          std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v488);
          std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v487);
          std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v486);
          std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v402);
          std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v401);
          std::_Optional_construct_base<web::json::value>::~_Optional_construct_base<web::json::value>(&v455);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v447);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v453);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v451);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v449);
          std::string::_Tidy_deallocate(v485);
        }
        goto LABEL_169;
      }
      wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(v7);
      v302 = Windows::Telemetry::Base::Provider();
      v444 = (__int64)v302;
      if ( *(_DWORD *)v302 <= 5u
        || (*((_QWORD *)v302 + 2) & 0x400000000000LL) == 0
        || (*((_QWORD *)v302 + 3) & 0x400000000000LL) != *((_QWORD *)v302 + 3) )
      {
        goto LABEL_169;
      }
      v420 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v457,
               "1507.2603.28012.0");
      v422 = _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v440, v431);
      v423 = _tlgWrapAuto<bool>(v389, v17);
      v303 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 8LL))(a2, v485);
      v304 = std::string::c_str(v303);
      v424 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v473,
               v304);
      winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
        v435,
        v7 + 416);
      v305 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(a4);
      v425 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v472,
               v305);
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl) )
        v306 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(a5);
      else
        v306 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v7 + 384);
      v426 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v471,
               v306);
      v307 = SystemInterface::Providers::GetSystem(v449);
      v308 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v307);
      v309 = *(int *)(*(_QWORD *)(v308 + 8) + 4LL) + v308 + 8;
      v310 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v309 + 96LL))(v309, v451);
      v311 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v310);
      v312 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v311 + 8LL))(v311);
      v313 = SystemInterface::to_wstring(v312);
      v427 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v470,
               v313);
      v314 = SystemInterface::Providers::GetSystem(v453);
      v315 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v314);
      v316 = *(int *)(*(_QWORD *)(v315 + 8) + 4LL) + v315 + 8;
      v317 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v316 + 8LL))(v316, v447);
      v318 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v317);
      v433 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v318 + 104LL))(v318)
           - (unsigned __int64)*(unsigned int *)(v7 + 344);
      *(_QWORD *)&v400[1] = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(
                              v469,
                              &v433);
      v319 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v7 + 328);
      v320 = SystemInterface::Timer::Elapsed<std::chrono::duration<int,std::ratio<60,1>>>(v319, v439);
      v392 = std::chrono::duration<int,std::ratio<60,1>>::count(v320);
      v421 = _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v438, &v392);
      v321 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v432);
      v418 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v482,
               v321);
      v322 = to_wstring(*(unsigned int *)(v7 + 380));
      v417 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v468,
               v322);
      v395 = *(unsigned __int8 *)(v7 + 376);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v411, &v395);
      v323 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      pExceptionObject[0] = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v492, L"id");
      v324 = Update::GetMetadataValue(v323, &v455, pExceptionObject);
      v325 = &psz;
      v326 = web::json::value::value((web::json::value *)v446, &psz);
      v327 = std::optional<web::json::value>::value_or<web::json::value>(v324, &v445, v326);
      v328 = web::json::value::as_string(v327);
      v329 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v328);
      v416 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v467,
               v329);
      v330 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v331 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v330 + 48LL))(v330, v486);
      v332 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v331);
      v415 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v466,
               v332);
      v333 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v334 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v333 + 32LL))(v333, v487);
      v335 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v334);
      v414 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v465,
               v335);
      v336 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v394 = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v336 + 640LL))(v336);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v410, &v394);
      v337 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v393 = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v337 + 552LL))(v337);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v412, &v393);
      v338 = (Update *)std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v391 = Update::Seeker(v338);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v409, &v391);
      v339 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v340 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v339 + 24LL))(v339, v488);
      v341 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v340);
      v413 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v464,
               v341);
      if ( (unsigned __int8)std::optional<std::shared_ptr<Action>>::has_value(v496) )
      {
        v342 = std::optional<std::shared_ptr<Action>>::value(v496);
        v343 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v342);
        v344 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v343 + 8LL))(v343, v489);
        v399 = 512;
        v325 = (const OLECHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v344);
      }
      v402 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v463,
               v325);
      v345 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v7 + 368) + 8LL))(*(_QWORD *)(v7 + 368), v490);
      v346 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v345);
      v401 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v462,
               v346);
      v347 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v348 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v347 + 8LL))(v347, v491);
      v349 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v348);
      v429 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v461,
               v349);
      v350 = FailureInfo;
      v430 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v460,
               *(_QWORD *)(FailureInfo + 120));
      v351 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v459,
               *(_QWORD *)(v350 + 112));
      v390 = *(_DWORD *)(v350 + 104);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v408, &v390);
      v352 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v458,
               *(_QWORD *)(v350 + 96));
      v353 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v484,
               *(_QWORD *)(v350 + 88));
      v398 = *(_DWORD *)(v350 + 80);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v407, &v398);
      v354 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v483,
               *(_QWORD *)(v350 + 72));
      v397 = *(_DWORD *)(v350 + 32);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v406, &v397);
      v355 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v481,
               *(_QWORD *)(v350 + 24));
      CurrentThreadId = *(_DWORD *)v350;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v405, &CurrentThreadId);
      v356 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v480,
               *(_QWORD *)(v350 + 128));
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v404, v350 + 64);
      v357 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v479,
               *(_QWORD *)(v350 + 56));
      v400[0] = *(_DWORD *)(FailureInfo + 8);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v403, v400);
      v419 = 0x1000000;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(
        &v442,
        &v419);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(
        &v443,
        &`Windows::Telemetry::UpdateManager::UpdateAction::Stop'::`118'::_tlgActivityPrivacyTag);
      v358 = wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Id(v434);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v444,
        (int)&dword_14049E32C,
        v358,
        (__int64)&v443,
        (__int64)&v442,
        (__int64)&v403,
        v357,
        (__int64)&v404,
        v356,
        (__int64)&v405,
        v355,
        (__int64)&v406,
        v354,
        (__int64)&v407,
        v353,
        v352,
        (__int64)&v408,
        v351,
        v430,
        v429,
        v401,
        v402,
        v413,
        (__int64)&v409,
        (__int64)&v412,
        (__int64)&v410,
        v414,
        v415,
        v416,
        (__int64)&v411,
        v417,
        v418,
        v421,
        *(__int64 *)&v400[1],
        v427,
        v426,
        v425,
        (__int64)v435,
        v424,
        v423,
        v422,
        v420);
      std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v491);
      std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v490);
      if ( (v399 & 0x200) != 0 )
        std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v489);
      std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v488);
      std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v487);
      std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v486);
      std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v445);
      std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(v446);
      std::_Optional_construct_base<web::json::value>::~_Optional_construct_base<web::json::value>(&v455);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v447);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v453);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v451);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v449);
    }
    std::string::_Tidy_deallocate(v485);
    goto LABEL_147;
  }
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::GetImpl'::`2'::impl);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::GetImpl'::`2'::impl) )
  {
    v19 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
    Update::GetExtendedErrorResult(v19, &v494);
    FailureInfo = wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(v7);
    if ( FailureInfo )
    {
      wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(v7);
      v20 = Windows::Telemetry::Base::Provider();
      v422 = (__int64)v20;
      if ( *(_DWORD *)v20 > 5u
        && (*((_QWORD *)v20 + 2) & 0x400000000000LL) != 0
        && (*((_QWORD *)v20 + 3) & 0x400000000000LL) == *((_QWORD *)v20 + 3) )
      {
        v444 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 &v433,
                 "1507.2603.28012.0");
        v21 = SystemInterface::Providers::GetSystem(&v455);
        v22 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v21);
        v23 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v22 + 40LL))(v22, v447);
        v24 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v23);
        v25 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v24 + 440LL))(v24, v490);
        v26 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v25);
        v443 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 v479,
                 v26);
        v431 = _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v438, v431);
        v442 = _tlgWrapAuto<bool>(v389, v17);
        v27 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 8LL))(a2, v489);
        v28 = std::string::c_str(v27);
        v430 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 v480,
                 v28);
        winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
          &v429,
          v7 + 416);
        v29 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(a4);
        v401 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 v481,
                 v29);
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl) )
          v30 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(a5);
        else
          v30 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v7 + 384);
        v402 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 v483,
                 v30);
        v31 = SystemInterface::Providers::GetSystem(v453);
        v32 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v31);
        v33 = v32 + *(int *)(*(_QWORD *)(v32 + 8) + 4LL);
        v34 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)(v33 + 8) + 96LL))(v33 + 8, v451);
        v35 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v34);
        v36 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
        v37 = SystemInterface::to_wstring(v36);
        v413 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 v484,
                 v37);
        v38 = SystemInterface::Providers::GetSystem(v449);
        v39 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v38);
        v40 = v39 + *(int *)(*(_QWORD *)(v39 + 8) + 4LL);
        v41 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)(v40 + 8) + 8LL))(v40 + 8, v477);
        v42 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v41);
        *(_QWORD *)v446 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v42 + 104LL))(v42)
                        - (unsigned __int64)*(unsigned int *)(v7 + 344);
        v414 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(
                 v458,
                 v446);
        v43 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v7 + 328);
        v44 = SystemInterface::Timer::Elapsed<std::chrono::duration<int,std::ratio<60,1>>>(v43, v439);
        LODWORD(v441) = std::chrono::duration<int,std::ratio<60,1>>::count(v44);
        v415 = _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v440, &v441);
        v437 = 0;
        LODWORD(v456) = std::optional<long>::value_or<long>(&v494, &v437);
        _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v411, &v456);
        v45 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v432);
        v432 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 v459,
                 v45);
        v46 = to_wstring(*(unsigned int *)(v7 + 380));
        v416 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 v460,
                 v46);
        v403 = *(unsigned __int8 *)(v7 + 376);
        _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v400, &v403);
        v47 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
        *(_OWORD *)v435 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                                       pExceptionObject,
                                       L"id");
        v48 = Update::GetMetadataValue(v47, v475, v435);
        v49 = &psz;
        v50 = web::json::value::value((web::json::value *)&v419, &psz);
        v51 = std::optional<web::json::value>::value_or<web::json::value>(v48, &v420, v50);
        v52 = web::json::value::as_string(v51);
        v53 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v52);
        v417 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 v461,
                 v53);
        v54 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
        v55 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v54 + 48LL))(v54, v488);
        v56 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v55);
        v418 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 v462,
                 v56);
        v57 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
        v58 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v57 + 32LL))(v57, v487);
        v59 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v58);
        v421 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 v463,
                 v59);
        v60 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
        v404 = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v60 + 640LL))(v60);
        _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&CurrentThreadId, &v404);
        v61 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
        v405 = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v61 + 552LL))(v61);
        _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v397, &v405);
        v62 = (Update *)std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
        v406 = Update::Seeker(v62);
        _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v398, &v406);
        v63 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
        v64 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v63 + 24LL))(v63, v486);
        v65 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v64);
        *(_QWORD *)&v400[1] = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                                v464,
                                v65);
        if ( (unsigned __int8)std::optional<std::shared_ptr<Action>>::has_value(v496) )
        {
          v66 = std::optional<std::shared_ptr<Action>>::value(v496);
          v67 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v66);
          v68 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v67 + 8LL))(v67, v485);
          v399 = 1;
          v49 = (const OLECHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v68);
        }
        v427 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 v465,
                 v49);
        v69 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v7 + 368) + 8LL))(*(_QWORD *)(v7 + 368), v493);
        v70 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v69);
        v426 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 v466,
                 v70);
        v71 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
        v72 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v71 + 8LL))(v71, v492);
        v73 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v72);
        v425 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 v467,
                 v73);
        v74 = FailureInfo;
        v435[0] = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                    v468,
                    *(_QWORD *)(FailureInfo + 120));
        v75 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                v482,
                *(_QWORD *)(v74 + 112));
        v407 = *(_DWORD *)(v74 + 104);
        _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v390, &v407);
        v76 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                v469,
                *(_QWORD *)(v74 + 96));
        v77 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                v470,
                *(_QWORD *)(v74 + 88));
        v408 = *(_DWORD *)(v74 + 80);
        _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v391, &v408);
        v78 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                v471,
                *(_QWORD *)(v74 + 72));
        v409 = *(_DWORD *)(v74 + 32);
        _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v393, &v409);
        v79 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                v472,
                *(_QWORD *)(v74 + 24));
        v412 = *(_DWORD *)v74;
        _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v394, &v412);
        v80 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                v473,
                *(_QWORD *)(v74 + 128));
        _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v395, v74 + 64);
        v81 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                v457,
                *(_QWORD *)(v74 + 56));
        v410 = *(_DWORD *)(FailureInfo + 8);
        _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v392, &v410);
        v445 = 0x1000000;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(
          &v424,
          &v445);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(
          &v423,
          &`Windows::Telemetry::UpdateManager::UpdateAction::Stop'::`16'::_tlgActivityPrivacyTag);
        v82 = wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Id(v434);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
          v422,
          (int)&byte_14049ED4B,
          v82,
          (__int64)&v423,
          (__int64)&v424,
          (__int64)&v392,
          v81,
          (__int64)&v395,
          v80,
          (__int64)&v394,
          v79,
          (__int64)&v393,
          v78,
          (__int64)&v391,
          v77,
          v76,
          (__int64)&v390,
          v75,
          v435[0],
          v425,
          v426,
          v427,
          *(__int64 *)&v400[1],
          (__int64)&v398,
          (__int64)&v397,
          (__int64)&CurrentThreadId,
          v421,
          v418,
          v417,
          (__int64)v400,
          v416,
          v432,
          (__int64)&v411,
          v415,
          v414,
          v413,
          v402,
          v401,
          (__int64)&v429,
          v430,
          v442,
          v431,
          v443,
          v444);
        std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v492);
        std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v493);
        if ( (v399 & 1) != 0 )
          std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v485);
        std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v486);
        std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v487);
        std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v488);
        std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v420);
        std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v419);
        std::_Optional_construct_base<web::json::value>::~_Optional_construct_base<web::json::value>(v475);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v477);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v449);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v451);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v453);
        std::string::_Tidy_deallocate(v489);
        std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v490);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v447);
        v83 = &v455;
LABEL_58:
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v83);
LABEL_147:
        v7 = v434;
        goto LABEL_169;
      }
      goto LABEL_169;
    }
    wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(v7);
    v84 = Windows::Telemetry::Base::Provider();
    v401 = (__int64)v84;
    if ( *(_DWORD *)v84 <= 5u
      || (*((_QWORD *)v84 + 2) & 0x400000000000LL) == 0
      || (*((_QWORD *)v84 + 3) & 0x400000000000LL) != *((_QWORD *)v84 + 3) )
    {
      goto LABEL_169;
    }
    v419 = (__int64)"1507.2603.28012.0";
    v85 = (_QWORD *)SystemInterface::Providers::GetSystem(v473);
    v86 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v85 + 40LL))(*v85, v475);
    v87 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v86 + 440LL))(*v86, v491);
    v420 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v87);
    v395 = *(_DWORD *)v431;
    v389[0] = *v17;
    v88 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 8LL))(a2, v493);
    v422 = std::string::c_str(v88);
    v423 = v7 + 416;
    v424 = *a4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl) )
      v89 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(a5);
    else
      v89 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v7 + 384);
    v435[0] = v89;
    v90 = SystemInterface::Providers::GetSystem(v477);
    v91 = *(_QWORD *)v90 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v90 + 8LL) + 4LL);
    v92 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v91 + 96LL))(v91, v449);
    v93 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v92 + 8LL))(*v92);
    if ( v93 )
    {
      v94 = v93 - 1;
      if ( v94 )
      {
        if ( v94 != 1 )
        {
          std::logic_error::logic_error((std::logic_error *)v492, "Invalid connectivity level");
          throw (std::logic_error *)v492;
        }
        v95 = L"Internet";
      }
      else
      {
        v95 = L"local only";
      }
    }
    else
    {
      v95 = L"none";
    }
    v425 = (__int64)v95;
    v96 = SystemInterface::Providers::GetSystem(v451);
    v97 = *(_QWORD *)v96 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v96 + 8LL) + 4LL);
    v98 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v97 + 8LL))(v97, v453);
    v426 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v98 + 104LL))(*v98)
         - (unsigned __int64)*(unsigned int *)(v7 + 344);
    v99 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v7 + 328) + 8LL))(*(_QWORD *)(v7 + 328), v457);
    std::chrono::duration_cast<std::chrono::duration<int,std::ratio<60,1>>,__int64,std::ratio<1,1000000>,0>(&v392, v99);
    v394 = v392;
    v393 = v495 != 0 ? v494 : 0;
    v427 = *(_QWORD *)v432;
    v100 = *(_DWORD *)(v7 + 380);
    if ( v100 )
    {
      if ( v100 != 1 )
      {
        std::logic_error::logic_error((std::logic_error *)v492, "Unknown action priority");
        throw (std::logic_error *)v492;
      }
      v101 = L"Low";
    }
    else
    {
      v101 = L"Normal";
    }
    *(_QWORD *)&v400[1] = v101;
    v391 = *(unsigned __int8 *)(v7 + 376);
    v102 = *v9;
    v455 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(pExceptionObject, L"id");
    v103 = Update::GetMetadataValue(v102, v447, &v455);
    v104 = &psz;
    v105 = web::json::value::value((web::json::value *)&v430, &psz);
    v106 = std::optional<web::json::value>::value_or<web::json::value>(v103, &v429, v105);
    v107 = web::json::value::as_string(v106);
    v421 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v107);
    v108 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 48LL))(*v9, v485);
    v418 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v108);
    v109 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 32LL))(*v9, v486);
    v417 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v109);
    v390 = (*(unsigned __int8 (__fastcall **)(Update *))(*(_QWORD *)*v9 + 640LL))(*v9);
    v398 = (*(unsigned __int8 (__fastcall **)(Update *))(*(_QWORD *)*v9 + 552LL))(*v9);
    v397 = Update::Seeker(*v9);
    v110 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 24LL))(*v9, v487);
    v416 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v110);
    if ( v497 )
    {
      v111 = std::optional<std::shared_ptr<Action>>::value(v496);
      v112 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v111);
      v113 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v112 + 8LL))(v112, v488);
      LOBYTE(v8) = 4;
      v399 = 4;
      v104 = (const OLECHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v113);
    }
    v415 = (__int64)v104;
    v114 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v7 + 368) + 8LL))(*(_QWORD *)(v7 + 368), v489);
    v414 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v114);
    v115 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 8LL))(*v9, v490);
    v413 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v115);
    CurrentThreadId = GetCurrentThreadId();
    v116 = *(_QWORD *)(v7 + 272);
    v400[0] = *(_DWORD *)(v116 + 72);
    v402 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
      v401,
      (int)&word_14049EFB6,
      v116 + 8,
      (__int64)&v402,
      (__int64)v400,
      (__int64)&CurrentThreadId,
      (__int64)&v413,
      (__int64)&v414,
      (__int64)&v415,
      (__int64)&v416,
      (__int64)&v397,
      (__int64)&v398,
      (__int64)&v390,
      (__int64)&v417,
      (__int64)&v418,
      (__int64)&v421,
      (__int64)&v391,
      (__int64)&v400[1],
      (__int64)&v427,
      (__int64)&v393,
      (__int64)&v394,
      (__int64)&v426,
      (__int64)&v425,
      (__int64)v435,
      (__int64)&v424,
      (__int64)&v423,
      (__int64)&v422,
      (__int64)v389,
      (__int64)&v395,
      (__int64)&v420,
      (__int64)&v419);
    std::wstring::~wstring(v490);
    std::wstring::~wstring(v489);
    if ( (v8 & 4) != 0 )
      std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v488);
    std::wstring::~wstring(v487);
    std::wstring::~wstring(v486);
    std::wstring::~wstring(v485);
    std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v429);
    std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v430);
    std::_Optional_construct_base<web::json::value>::~_Optional_construct_base<web::json::value>(v447);
    if ( v454 )
      std::_Ref_count_base::_Decref(v454);
    if ( v452 )
      std::_Ref_count_base::_Decref(v452);
    if ( v450 )
      std::_Ref_count_base::_Decref(v450);
    if ( v478 )
      std::_Ref_count_base::_Decref(v478);
    std::string::_Tidy_deallocate(v493);
    std::wstring::~wstring(v491);
    if ( v476 )
      std::_Ref_count_base::_Decref(v476);
    v117 = v474;
LABEL_90:
    if ( v117 )
      std::_Ref_count_base::_Decref(v117);
    goto LABEL_169;
  }
  FailureInfo = wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(v7);
  if ( !FailureInfo )
  {
    wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(v7);
    v181 = Windows::Telemetry::Base::Provider();
    v401 = (__int64)v181;
    if ( *(_DWORD *)v181 <= 5u
      || (*((_QWORD *)v181 + 2) & 0x400000000000LL) == 0
      || (*((_QWORD *)v181 + 3) & 0x400000000000LL) != *((_QWORD *)v181 + 3) )
    {
      goto LABEL_169;
    }
    v419 = (__int64)"1507.2603.28012.0";
    v182 = (_QWORD *)SystemInterface::Providers::GetSystem(v475);
    v183 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v182 + 40LL))(*v182, v477);
    v184 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v183 + 440LL))(*v183, v493);
    v420 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v184);
    v395 = *(_DWORD *)v431;
    v389[0] = *v17;
    v185 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 8LL))(a2, v485);
    v422 = std::string::c_str(v185);
    v423 = v7 + 416;
    v424 = *a4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl) )
      v186 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(a5);
    else
      v186 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v7 + 384);
    v435[0] = v186;
    v187 = SystemInterface::Providers::GetSystem(v449);
    v188 = *(_QWORD *)v187 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v187 + 8LL) + 4LL);
    v189 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v188 + 96LL))(v188, v451);
    v190 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v189 + 8LL))(*v189);
    if ( v190 )
    {
      v191 = v190 - 1;
      if ( v191 )
      {
        if ( v191 != 1 )
        {
          std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
          throw (std::logic_error *)pExceptionObject;
        }
        v192 = L"Internet";
      }
      else
      {
        v192 = L"local only";
      }
    }
    else
    {
      v192 = L"none";
    }
    v425 = (__int64)v192;
    v193 = SystemInterface::Providers::GetSystem(v453);
    v194 = *(_QWORD *)v193 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v193 + 8LL) + 4LL);
    v195 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v194 + 8LL))(v194, v447);
    v426 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v195 + 104LL))(*v195)
         - (unsigned __int64)*(unsigned int *)(v7 + 344);
    v196 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v7 + 328) + 8LL))(*(_QWORD *)(v7 + 328), v457);
    std::chrono::duration_cast<std::chrono::duration<int,std::ratio<60,1>>,__int64,std::ratio<1,1000000>,0>(&v392, v196);
    v394 = v392;
    v427 = *(_QWORD *)v432;
    v197 = *(_DWORD *)(v7 + 380);
    if ( v197 )
    {
      if ( v197 != 1 )
      {
        std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Unknown action priority");
        throw (std::logic_error *)pExceptionObject;
      }
      v198 = L"Low";
    }
    else
    {
      v198 = L"Normal";
    }
    *(_QWORD *)&v400[1] = v198;
    v393 = *(unsigned __int8 *)(v7 + 376);
    v199 = *v9;
    pExceptionObject[0] = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v492, L"id");
    v200 = Update::GetMetadataValue(v199, &v455, pExceptionObject);
    v201 = &psz;
    v202 = web::json::value::value((web::json::value *)&v430, &psz);
    v203 = std::optional<web::json::value>::value_or<web::json::value>(v200, &v429, v202);
    v204 = web::json::value::as_string(v203);
    v421 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v204);
    v205 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 48LL))(*v9, v486);
    v418 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v205);
    v206 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 32LL))(*v9, v487);
    v417 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v206);
    v391 = (*(unsigned __int8 (__fastcall **)(Update *))(*(_QWORD *)*v9 + 640LL))(*v9);
    v390 = (*(unsigned __int8 (__fastcall **)(Update *))(*(_QWORD *)*v9 + 552LL))(*v9);
    v398 = Update::Seeker(*v9);
    v207 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 24LL))(*v9, v488);
    v416 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v207);
    if ( v497 )
    {
      v208 = std::optional<std::shared_ptr<Action>>::value(v496);
      v209 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v208);
      v210 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v209 + 8LL))(v209, v489);
      LOBYTE(v8) = 32;
      v399 = 32;
      v201 = (const OLECHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v210);
    }
    v415 = (__int64)v201;
    v211 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v7 + 368) + 8LL))(*(_QWORD *)(v7 + 368), v490);
    v414 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v211);
    v212 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 8LL))(*v9, v491);
    v413 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v212);
    v397 = GetCurrentThreadId();
    v213 = *(_QWORD *)(v7 + 272);
    CurrentThreadId = *(_DWORD *)(v213 + 72);
    v402 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
      v401,
      (int)&byte_14049E7CD,
      v213 + 8,
      (__int64)&v402,
      (__int64)&CurrentThreadId,
      (__int64)&v397,
      (__int64)&v413,
      (__int64)&v414,
      (__int64)&v415,
      (__int64)&v416,
      (__int64)&v398,
      (__int64)&v390,
      (__int64)&v391,
      (__int64)&v417,
      (__int64)&v418,
      (__int64)&v421,
      (__int64)&v393,
      (__int64)&v400[1],
      (__int64)&v427,
      (__int64)&v394,
      (__int64)&v426,
      (__int64)&v425,
      (__int64)v435,
      (__int64)&v424,
      (__int64)&v423,
      (__int64)&v422,
      (__int64)v389,
      (__int64)&v395,
      (__int64)&v420,
      (__int64)&v419);
    std::wstring::~wstring(v491);
    std::wstring::~wstring(v490);
    if ( (v8 & 0x20) != 0 )
      std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v489);
    std::wstring::~wstring(v488);
    std::wstring::~wstring(v487);
    std::wstring::~wstring(v486);
    std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v429);
    std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v430);
    std::_Optional_construct_base<web::json::value>::~_Optional_construct_base<web::json::value>(&v455);
    if ( v448 )
      std::_Ref_count_base::_Decref(v448);
    if ( v454 )
      std::_Ref_count_base::_Decref(v454);
    if ( v452 )
      std::_Ref_count_base::_Decref(v452);
    if ( v450 )
      std::_Ref_count_base::_Decref(v450);
    std::string::_Tidy_deallocate(v485);
    std::wstring::~wstring(v493);
    if ( v478 )
      std::_Ref_count_base::_Decref(v478);
    v117 = v476;
    goto LABEL_90;
  }
  wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(v7);
  v118 = Windows::Telemetry::Base::Provider();
  *(_QWORD *)v446 = v118;
  if ( *(_DWORD *)v118 > 5u
    && (*((_QWORD *)v118 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v118 + 3) & 0x400000000000LL) == *((_QWORD *)v118 + 3) )
  {
    v422 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v457,
             "1507.2603.28012.0");
    v119 = SystemInterface::Providers::GetSystem(pExceptionObject);
    v120 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v119);
    v121 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v120 + 40LL))(v120, v475);
    v122 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v121);
    v123 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v122 + 440LL))(v122, v493);
    v124 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v123);
    v423 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v473,
             v124);
    v424 = _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v440, v431);
    v435[0] = _tlgWrapAuto<bool>(v389, v17);
    v125 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 8LL))(a2, v485);
    v126 = std::string::c_str(v125);
    v425 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v472,
             v126);
    winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
      &v426,
      v7 + 416);
    v127 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(a4);
    v427 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v471,
             v127);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl) )
      v128 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(a5);
    else
      v128 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v7 + 384);
    *(_QWORD *)&v400[1] = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                            v470,
                            v128);
    v129 = SystemInterface::Providers::GetSystem(v477);
    v130 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v129);
    v131 = *(int *)(*(_QWORD *)(v130 + 8) + 4LL) + v130 + 8;
    v132 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v131 + 96LL))(v131, v449);
    v133 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v132);
    v134 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v133 + 8LL))(v133);
    v135 = SystemInterface::to_wstring(v134);
    v421 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v469,
             v135);
    v136 = SystemInterface::Providers::GetSystem(v451);
    v137 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v136);
    v138 = *(int *)(*(_QWORD *)(v137 + 8) + 4LL) + v137 + 8;
    v139 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v138 + 8LL))(v138, v453);
    v140 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v139);
    v419 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v140 + 104LL))(v140)
         - (unsigned __int64)*(unsigned int *)(v7 + 344);
    v418 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(
             v482,
             &v419);
    v141 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v7 + 328);
    v142 = SystemInterface::Timer::Elapsed<std::chrono::duration<int,std::ratio<60,1>>>(v141, v439);
    v392 = std::chrono::duration<int,std::ratio<60,1>>::count(v142);
    v417 = _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v438, &v392);
    v143 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v432);
    v416 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v468,
             v143);
    v144 = to_wstring(*(unsigned int *)(v7 + 380));
    v415 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v467,
             v144);
    v395 = *(unsigned __int8 *)(v7 + 376);
    _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v411, &v395);
    v145 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
    v455 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v492, L"id");
    v146 = Update::GetMetadataValue(v145, v447, &v455);
    v147 = &psz;
    v148 = web::json::value::value((web::json::value *)&v456, &psz);
    v149 = std::optional<web::json::value>::value_or<web::json::value>(v146, &v494, v148);
    v150 = web::json::value::as_string(v149);
    v151 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v150);
    v414 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v466,
             v151);
    v152 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
    v153 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v152 + 48LL))(v152, v486);
    v154 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v153);
    v413 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v465,
             v154);
    v155 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
    v156 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v155 + 32LL))(v155, v487);
    v157 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v156);
    v402 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v464,
             v157);
    v158 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
    v394 = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v158 + 640LL))(v158);
    _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v410, &v394);
    v159 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
    v393 = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v159 + 552LL))(v159);
    _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v412, &v393);
    v160 = (Update *)std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
    v391 = Update::Seeker(v160);
    _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v409, &v391);
    v161 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
    v162 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v161 + 24LL))(v161, v488);
    v163 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v162);
    v401 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v463,
             v163);
    if ( (unsigned __int8)std::optional<std::shared_ptr<Action>>::has_value(v496) )
    {
      v164 = std::optional<std::shared_ptr<Action>>::value(v496);
      v165 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v164);
      v166 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v165 + 8LL))(v165, v489);
      v399 = 8;
      v147 = (const OLECHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v166);
    }
    v429 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v462,
             v147);
    v167 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v7 + 368) + 8LL))(*(_QWORD *)(v7 + 368), v490);
    v168 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v167);
    v430 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v461,
             v168);
    v169 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
    v170 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v169 + 8LL))(v169, v491);
    v171 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v170);
    v442 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v460,
             v171);
    v172 = FailureInfo;
    v443 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v459,
             *(_QWORD *)(FailureInfo + 120));
    v173 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v458,
             *(_QWORD *)(v172 + 112));
    v390 = *(_DWORD *)(v172 + 104);
    _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v408, &v390);
    v174 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v484,
             *(_QWORD *)(v172 + 96));
    v175 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v483,
             *(_QWORD *)(v172 + 88));
    v398 = *(_DWORD *)(v172 + 80);
    _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v407, &v398);
    v176 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v481,
             *(_QWORD *)(v172 + 72));
    v397 = *(_DWORD *)(v172 + 32);
    _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v406, &v397);
    v177 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v480,
             *(_QWORD *)(v172 + 24));
    CurrentThreadId = *(_DWORD *)v172;
    _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v405, &CurrentThreadId);
    v178 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v479,
             *(_QWORD *)(v172 + 128));
    _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v404, v172 + 64);
    v179 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             &v433,
             *(_QWORD *)(v172 + 56));
    v400[0] = *(_DWORD *)(FailureInfo + 8);
    _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v403, v400);
    v420 = 0x1000000;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(
      &v444,
      &v420);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(
      &v445,
      &`Windows::Telemetry::UpdateManager::UpdateAction::Stop'::`49'::_tlgActivityPrivacyTag);
    v180 = wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Id(v434);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
      v446[0],
      (int)&unk_14049E578,
      v180,
      (__int64)&v445,
      (__int64)&v444,
      (__int64)&v403,
      v179,
      (__int64)&v404,
      v178,
      (__int64)&v405,
      v177,
      (__int64)&v406,
      v176,
      (__int64)&v407,
      v175,
      v174,
      (__int64)&v408,
      v173,
      v443,
      v442,
      v430,
      v429,
      v401,
      (__int64)&v409,
      (__int64)&v412,
      (__int64)&v410,
      v402,
      v413,
      v414,
      (__int64)&v411,
      v415,
      v416,
      v417,
      v418,
      v421,
      *(__int64 *)&v400[1],
      v427,
      (__int64)&v426,
      v425,
      v435[0],
      v424,
      v423,
      v422);
    std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v491);
    std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v490);
    if ( (v399 & 8) != 0 )
      std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v489);
    std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v488);
    std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v487);
    std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v486);
    std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v494);
    std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v456);
    std::_Optional_construct_base<web::json::value>::~_Optional_construct_base<web::json::value>(v447);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v453);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v451);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v449);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v477);
    std::string::_Tidy_deallocate(v485);
    std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v493);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v475);
    v83 = pExceptionObject;
    goto LABEL_58;
  }
LABEL_169:
  wil::ActivityBase<Windows::WU::Telemetry::WuProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(v7);
  ActionState::~ActionState((ActionState *)v496);
}

```

## disassembly

```asm
0x140276614  push    rbp
0x140276616  push    rbx
0x140276617  push    rsi
0x140276618  push    rdi
0x140276619  push    r12
0x14027661b  push    r13
0x14027661d  push    r14
0x14027661f  push    r15
0x140276621  lea     rbp, [rsp-3A8h]
0x140276629  sub     rsp, 598h
0x140276630  mov     rax, cs:__security_cookie
0x140276637  xor     rax, rsp
0x14027663a  mov     [rbp+3E0h+var_48], rax
0x140276641  mov     r12, r9
0x140276644  mov     [rbp+3E0h+var_358], r8
0x14027664b  mov     rbx, rdx
0x14027664e  mov     rdi, rcx
0x140276651  mov     [rbp+3E0h+var_348], rcx
0x140276658  mov     r15, [rbp+3E0h+arg_20]
0x14027665f  xor     r14d, r14d
0x140276662  mov     [rbp+3E0h+var_438], r14d
0x140276666  lea     rsi, [rcx+160h]
0x14027666d  mov     rcx, rsi
0x140276670  call    ??$?CVReboot@SystemInterface@@$0A@@?$shared_ptr@VReboot@SystemInterface@@@std@@QEBAPEAVReboot@SystemInterface@@XZ; std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(void)
0x140276675  mov     r8, rax
0x140276678  mov     rcx, [rax]
0x14027667b  mov     rax, [rcx+128h]
0x140276682  lea     rdx, [rbp+3E0h+var_68]
0x140276689  mov     rcx, r8
0x14027668c  call    _guard_dispatch_icall
0x140276691  nop
0x140276692  lea     rcx, [rbp+3E0h+var_1F0]
0x140276699  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x14027669e  nop
0x14027669f  mov     rcx, rax
0x1402766a2  call    ??$?CVReboot@SystemInterface@@$0A@@?$shared_ptr@VReboot@SystemInterface@@@std@@QEBAPEAVReboot@SystemInterface@@XZ; std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(void)
0x1402766a7  mov     rcx, [rax+8]
0x1402766ab  movsxd  rdx, dword ptr [rcx+4]
0x1402766af  lea     rcx, [rax+8]
0x1402766b3  add     rcx, rdx
0x1402766b6  mov     rax, [rcx]
0x1402766b9  lea     rdx, [rbp+3E0h+var_278]
0x1402766c0  mov     rax, [rax+38h]
0x1402766c4  call    _guard_dispatch_icall
0x1402766c9  nop
0x1402766ca  mov     rcx, rax
0x1402766cd  call    ??$?CVReboot@SystemInterface@@$0A@@?$shared_ptr@VReboot@SystemInterface@@@std@@QEBAPEAVReboot@SystemInterface@@XZ; std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(void)
0x1402766d2  mov     r8, rax
0x1402766d5  mov     rcx, [rax]
0x1402766d8  mov     rax, [rcx+30h]
0x1402766dc  lea     rdx, [rbp+3E0h+var_50]
0x1402766e3  mov     rcx, r8
0x1402766e6  call    _guard_dispatch_icall
0x1402766eb  nop
0x1402766ec  lea     rcx, [rbp+3E0h+var_278]; void *
0x1402766f3  call    ??1?$shared_ptr@VInputBuilder@RebootDowntime@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(void)
0x1402766f8  nop
0x1402766f9  lea     rcx, [rbp+3E0h+var_1F0]; void *
0x140276700  call    ??1?$shared_ptr@VInputBuilder@RebootDowntime@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(void)
0x140276705  lea     rcx, [rbp+3E0h+var_50]
0x14027670c  call    ?setbuf@?$basic_streambuf@_WU?$char_traits@_W@std@@@std@@MEAAPEAV12@PEA_W_J@Z; std::wstreambuf::setbuf(wchar_t *,__int64)
0x140276711  mov     rcx, rax
0x140276714  call    ?setbuf@?$basic_streambuf@_WU?$char_traits@_W@std@@@std@@MEAAPEAV12@PEA_W_J@Z; std::wstreambuf::setbuf(wchar_t *,__int64)
0x140276719  mov     r13, rax
0x14027671c  lea     rcx, [rbp+3E0h+var_50]
0x140276723  call    ?setbuf@?$basic_streambuf@_WU?$char_traits@_W@std@@@std@@MEAAPEAV12@PEA_W_J@Z; std::wstreambuf::setbuf(wchar_t *,__int64)
0x140276728  mov     rcx, rax
0x14027672b  call    ??$get@$00_NH@std@@YA$$QEBH$$QEBU?$pair@_NH@0@@Z; std::get<1,bool,int>(std::pair<bool,int> const &&)
0x140276730  mov     [rbp+3E0h+var_360], rax
0x140276737  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections> `wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl(void)'::`2'::impl
0x14027673e  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabledPreCheck(void)
0x140276743  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections> `wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl(void)'::`2'::impl
0x14027674a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(void)
0x14027674f  test    al, al
0x140276751  jz      loc_1402787EE
0x140276757  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::GetImpl(void)'::`2'::impl
0x14027675e  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabledPreCheck(void)
0x140276763  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::GetImpl(void)'::`2'::impl
0x14027676a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabled(void)
0x14027676f  test    al, al
0x140276771  jz      loc_1402777E9
0x140276777  mov     rcx, rsi
0x14027677a  call    ??$?CVReboot@SystemInterface@@$0A@@?$shared_ptr@VReboot@SystemInterface@@@std@@QEBAPEAVReboot@SystemInterface@@XZ; std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(void)
0x14027677f  lea     rdx, [rbp+3E0h+var_70]
0x140276786  mov     rcx, rax
0x140276789  call    ?GetExtendedErrorResult@Update@@QEBA?AV?$optional@J@std@@XZ; Update::GetExtendedErrorResult(void)
0x14027678e  mov     rcx, rdi
0x140276791  call    ?GetFailureInfo@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAPEBUFailureInfo@2@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(void)
0x140276796  mov     [rbp+3E0h+var_378], rax
0x14027679a  mov     rcx, rdi
0x14027679d  test    rax, rax
0x1402767a0  jz      loc_140277186
0x1402767a6  call    ?zInternalStop@?$ActivityBase@VBaseCore@Telemetry@Windows@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1402767ab  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x1402767b0  mov     [rbp+3E0h+var_3A8], rax
0x1402767b4  cmp     dword ptr [rax], 5
0x1402767b7  jbe     loc_14027A61E
0x1402767bd  mov     rdx, 400000000000h
0x1402767c7  test    [rax+10h], rdx
0x1402767cb  jz      loc_14027A61E
0x1402767d1  mov     rcx, [rax+18h]
0x1402767d5  and     rcx, rdx
0x1402767d8  cmp     rcx, [rax+18h]
0x1402767dc  jnz     loc_14027A61E
0x1402767e2  lea     rdx, a15072603280120; "1507.2603.28012.0"
0x1402767e9  lea     rcx, [rbp+3E0h+var_350]
0x1402767f0  call    ??0abi_guard@?$root_implements@U?$reference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@impl@winrt@@U?$IReference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@Foundation@Windows@3@UIPropertyValue@563@@impl@winrt@@QEAA@AEAU?$reference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@23@@Z; winrt::impl::root_implements<winrt::impl::reference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(winrt::impl::reference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason> &)
0x1402767f5  mov     [rbp+3E0h+var_2E8], rax
0x1402767fc  lea     rcx, [rbp+3E0h+var_290]
0x140276803  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x140276808  nop
0x140276809  mov     rcx, rax
0x14027680c  call    ??$?CVReboot@SystemInterface@@$0A@@?$shared_ptr@VReboot@SystemInterface@@@std@@QEBAPEAVReboot@SystemInterface@@XZ; std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(void)
0x140276811  mov     r8, rax
0x140276814  mov     rcx, [rax]
0x140276817  mov     rax, [rcx+28h]
0x14027681b  lea     rdx, [rbp+3E0h+var_2D0]
0x140276822  mov     rcx, r8
0x140276825  call    _guard_dispatch_icall
0x14027682a  nop
0x14027682b  mov     rcx, rax
0x14027682e  call    ??$?CVReboot@SystemInterface@@$0A@@?$shared_ptr@VReboot@SystemInterface@@@std@@QEBAPEAVReboot@SystemInterface@@XZ; std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(void)
0x140276833  mov     r8, rax
0x140276836  mov     rcx, [rax]
0x140276839  mov     rax, [rcx+1B8h]
0x140276840  lea     rdx, [rbp+3E0h+var_F0]
0x140276847  mov     rcx, r8
0x14027684a  call    _guard_dispatch_icall
0x14027684f  nop
0x140276850  mov     rcx, rax
0x140276853  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x140276858  mov     rdx, rax
0x14027685b  lea     rcx, [rbp+3E0h+var_1C0]
0x140276862  call    ??0abi_guard@?$root_implements@U?$reference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@impl@winrt@@U?$IReference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@Foundation@Windows@3@UIPropertyValue@563@@impl@winrt@@QEAA@AEAU?$reference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@23@@Z; winrt::impl::root_implements<winrt::impl::reference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(winrt::impl::reference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason> &)
0x140276867  mov     [rbp+3E0h+var_2F0], rax
0x14027686e  mov     rdx, [rbp+3E0h+var_360]
0x140276875  lea     rcx, [rbp+3E0h+var_310+4]
0x14027687c  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x140276881  mov     [rbp+3E0h+var_360], rax
0x140276888  mov     rdx, r13
0x14027688b  lea     rcx, [rbp+3E0h+var_460]
0x14027688f  call    ??$_tlgWrapAuto@_N@@YA?AU?$_tlgWrapperByVal@$00@@AEB_N@Z; _tlgWrapAuto<bool>(bool const &)
0x140276894  mov     [rbp+3E0h+var_2F8], rax
0x14027689b  mov     rcx, [rbx]
0x14027689e  mov     rax, [rcx+8]
0x1402768a2  lea     rdx, [rbp+3E0h+var_110]
0x1402768a9  mov     rcx, rbx
0x1402768ac  call    _guard_dispatch_icall
0x1402768b1  nop
0x1402768b2  mov     rcx, rax
0x1402768b5  call    ?c_str@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAPEBDXZ; std::string::c_str(void)
0x1402768ba  mov     rdx, rax
0x1402768bd  lea     rcx, [rbp+3E0h+var_1B8]
0x1402768c4  call    ??0abi_guard@?$root_implements@U?$reference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@impl@winrt@@U?$IReference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@Foundation@Windows@3@UIPropertyValue@563@@impl@winrt@@QEAA@AEAU?$reference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@23@@Z; winrt::impl::root_implements<winrt::impl::reference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(winrt::impl::reference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason> &)
0x1402768c9  mov     [rbp+3E0h+var_368], rax
0x1402768cd  lea     rdx, [rdi+1A0h]
0x1402768d4  lea     rcx, [rbp+3E0h+var_370]
0x1402768d8  call    ??0abi_guard@?$root_implements@U?$reference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@impl@winrt@@U?$IReference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@Foundation@Windows@3@UIPropertyValue@563@@impl@winrt@@QEAA@AEAU?$reference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@23@@Z; winrt::impl::root_implements<winrt::impl::reference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(winrt::impl::reference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason> &)
0x1402768dd  mov     rcx, r12
0x1402768e0  call    ??$?CVReboot@SystemInterface@@$0A@@?$shared_ptr@VReboot@SystemInterface@@@std@@QEBAPEAVReboot@SystemInterface@@XZ; std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(void)
0x1402768e5  mov     rdx, rax
0x1402768e8  lea     rcx, [rbp+3E0h+var_1B0]
0x1402768ef  call    ??0abi_guard@?$root_implements@U?$reference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@impl@winrt@@U?$IReference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@Foundation@Windows@3@UIPropertyValue@563@@impl@winrt@@QEAA@AEAU?$reference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@23@@Z; winrt::impl::root_implements<winrt::impl::reference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(winrt::impl::reference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason> &)
0x1402768f4  mov     [rbp+3E0h+var_428], rax
0x1402768f8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UpdateModeCaching@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UpdateModeCaching@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UpdateModeCaching> `wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl(void)'::`2'::impl
0x1402768ff  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabledPreCheck(void)
0x140276904  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UpdateModeCaching@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UpdateModeCaching@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UpdateModeCaching> `wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl(void)'::`2'::impl
0x14027690b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UpdateModeCaching@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::__private_IsEnabled(void)
0x140276910  test    al, al
0x140276912  jz      short loc_14027691E
0x140276914  mov     rcx, r15
0x140276917  call    ??$?CVReboot@SystemInterface@@$0A@@?$shared_ptr@VReboot@SystemInterface@@@std@@QEBAPEAVReboot@SystemInterface@@XZ; std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(void)
0x14027691c  jmp     short loc_14027692A
0x14027691e  lea     rcx, [rdi+180h]
0x140276925  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x14027692a  mov     rdx, rax
0x14027692d  lea     rcx, [rbp+3E0h+var_1A0]
0x140276934  call    ??0abi_guard@?$root_implements@U?$reference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@impl@winrt@@U?$IReference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@Foundation@Windows@3@UIPropertyValue@563@@impl@winrt@@QEAA@AEAU?$reference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@23@@Z; winrt::impl::root_implements<winrt::impl::reference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(winrt::impl::reference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason> &)
0x140276939  mov     [rbp+3E0h+var_420], rax
0x14027693d  lea     rcx, [rbp+3E0h+var_2A0]
0x140276944  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x140276949  nop
0x14027694a  mov     rcx, rax
0x14027694d  call    ??$?CVReboot@SystemInterface@@$0A@@?$shared_ptr@VReboot@SystemInterface@@@std@@QEBAPEAVReboot@SystemInterface@@XZ; std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(void)
0x140276952  mov     rcx, [rax+8]
0x140276956  movsxd  r8, dword ptr [rcx+4]
0x14027695a  add     r8, rax
0x14027695d  mov     rcx, [r8+8]
0x140276961  mov     rax, [rcx+60h]
0x140276965  lea     rdx, [rbp+3E0h+var_2B0]
0x14027696c  lea     rcx, [r8+8]
0x140276970  call    _guard_dispatch_icall
0x140276975  nop
0x140276976  mov     rcx, rax
0x140276979  call    ??$?CVReboot@SystemInterface@@$0A@@?$shared_ptr@VReboot@SystemInterface@@@std@@QEBAPEAVReboot@SystemInterface@@XZ; std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(void)
0x14027697e  mov     rdx, rax
0x140276981  mov     rcx, [rax]
0x140276984  mov     rax, [rcx+8]
0x140276988  mov     rcx, rdx
0x14027698b  call    _guard_dispatch_icall
0x140276990  mov     ecx, eax
0x140276992  call    ?to_wstring@SystemInterface@@YA@W4ConnectivityLevel@Network@1@@Z; SystemInterface::to_wstring(SystemInterface::Network::ConnectivityLevel)
0x140276997  mov     rdx, rax
0x14027699a  lea     rcx, [rbp+3E0h+var_198]
0x1402769a1  call    ??0abi_guard@?$root_implements@U?$reference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@impl@winrt@@U?$IReference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@Foundation@Windows@3@UIPropertyValue@563@@impl@winrt@@QEAA@AEAU?$reference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@23@@Z; winrt::impl::root_implements<winrt::impl::reference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(winrt::impl::reference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason> &)
0x1402769a6  mov     [rbp+3E0h+var_3F0], rax
0x1402769aa  lea     rcx, [rbp+3E0h+var_2C0]
0x1402769b1  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x1402769b6  nop
0x1402769b7  mov     rcx, rax
0x1402769ba  call    ??$?CVReboot@SystemInterface@@$0A@@?$shared_ptr@VReboot@SystemInterface@@@std@@QEBAPEAVReboot@SystemInterface@@XZ; std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(void)
0x1402769bf  mov     rcx, [rax+8]
0x1402769c3  movsxd  r8, dword ptr [rcx+4]
0x1402769c7  add     r8, rax
0x1402769ca  mov     rcx, [r8+8]
0x1402769ce  mov     rax, [rcx+8]
0x1402769d2  lea     rdx, [rbp+3E0h+var_1D0]
0x1402769d9  lea     rcx, [r8+8]
0x1402769dd  call    _guard_dispatch_icall
0x1402769e2  nop
0x1402769e3  mov     rcx, rax
0x1402769e6  call    ??$?CVReboot@SystemInterface@@$0A@@?$shared_ptr@VReboot@SystemInterface@@@std@@QEBAPEAVReboot@SystemInterface@@XZ; std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(void)
0x1402769eb  mov     rdx, rax
0x1402769ee  mov     rcx, [rax]
0x1402769f1  mov     rax, [rcx+68h]
0x1402769f5  mov     rcx, rdx
0x1402769f8  call    _guard_dispatch_icall
0x1402769fd  mov     ecx, eax
0x1402769ff  mov     eax, [rdi+158h]
0x140276a05  sub     rcx, rax
0x140276a08  mov     qword ptr [rbp+3E0h+var_2D8], rcx
0x140276a0f  lea     rdx, [rbp+3E0h+var_2D8]
0x140276a16  lea     rcx, [rbp+3E0h+var_268]
0x140276a1d  call    ??$?0PEAD$$V@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?sqlite3_free@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@$$QEAPEAD@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(char * &&)
0x140276a22  mov     [rbp+3E0h+var_3E8], rax
0x140276a26  lea     rcx, [rdi+148h]
0x140276a2d  call    ??$?CVReboot@SystemInterface@@$0A@@?$shared_ptr@VReboot@SystemInterface@@@std@@QEBAPEAVReboot@SystemInterface@@XZ; std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(void)
0x140276a32  lea     rdx, [rbp+3E0h+var_308]
0x140276a39  mov     rcx, rax
0x140276a3c  call    ??$Elapsed@V?$duration@HU?$ratio@$0DM@$00@std@@@chrono@std@@@Timer@SystemInterface@@QEBA?AV?$duration@HU?$ratio@$0DM@$00@std@@@chrono@std@@XZ; SystemInterface::Timer::Elapsed<std::chrono::duration<int,std::ratio<60,1>>>(void)
0x140276a41  mov     rcx, rax
0x140276a44  call    ?count@?$duration@HU?$ratio@$0DM@$00@std@@@chrono@std@@QEBAHXZ; std::chrono::duration<int,std::ratio<60,1>>::count(void)
0x140276a49  mov     dword ptr [rbp+3E0h+var_300], eax
0x140276a4f  lea     rdx, [rbp+3E0h+var_300]
0x140276a56  lea     rcx, [rbp+3E0h+var_304]
0x140276a5d  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x140276a62  mov     [rbp+3E0h+var_3E0], rax
0x140276a66  mov     dword ptr [rbp+3E0h+var_310], 0
0x140276a70  lea     rdx, [rbp+3E0h+var_310]
0x140276a77  lea     rcx, [rbp+3E0h+var_70]
0x140276a7e  call    ??$value_or@J@?$optional@J@std@@QEGBAJ$$QEAJ@Z; std::optional<long>::value_or<long>(long &&)
0x140276a83  mov     dword ptr [rbp+3E0h+var_280], eax
0x140276a89  lea     rdx, [rbp+3E0h+var_280]
0x140276a90  lea     rcx, [rbp+3E0h+var_3F8]
0x140276a94  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x140276a99  mov     rcx, [rbp+3E0h+var_358]
0x140276aa0  call    ??$?CVReboot@SystemInterface@@$0A@@?$shared_ptr@VReboot@SystemInterface@@@std@@QEBAPEAVReboot@SystemInterface@@XZ; std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(void)
0x140276aa5  mov     rdx, rax
0x140276aa8  lea     rcx, [rbp+3E0h+var_260]
0x140276aaf  call    ??0abi_guard@?$root_implements@U?$reference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@impl@winrt@@U?$IReference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@Foundation@Windows@3@UIPropertyValue@563@@impl@winrt@@QEAA@AEAU?$reference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@23@@Z; winrt::impl::root_implements<winrt::impl::reference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(winrt::impl::reference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason> &)
0x140276ab4  mov     [rbp+3E0h+var_358], rax
0x140276abb  mov     ecx, [rdi+17Ch]
0x140276ac1  call    ?to_wstring@@YA@W4ActionPriority@@@Z; to_wstring(ActionPriority)
0x140276ac6  mov     rdx, rax
0x140276ac9  lea     rcx, [rbp+3E0h+var_258]
0x140276ad0  call    ??0abi_guard@?$root_implements@U?$reference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@impl@winrt@@U?$IReference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@Foundation@Windows@3@UIPropertyValue@563@@impl@winrt@@QEAA@AEAU?$reference@W4WindowsSoftwareUpdateRestartReason@Update@Management@Windows@winrt@@@23@@Z; winrt::impl::root_implements<winrt::impl::reference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(winrt::impl::reference<winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason> &)
0x140276ad5  mov     [rbp+3E0h+var_3D8], rax
0x140276ad9  movzx   ecx, byte ptr [rdi+178h]
0x140276ae0  mov     dword ptr [rbp+3E0h+var_418], ecx
0x140276ae3  lea     rdx, [rbp+3E0h+var_418]
0x140276ae7  lea     rcx, [rbp+3E0h+var_434]
0x140276aeb  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x140276af0  mov     rcx, rsi
0x140276af3  call    ??$?CVReboot@SystemInterface@@$0A@@?$shared_ptr@VReboot@SystemInterface@@@std@@QEBAPEAVReboot@SystemInterface@@XZ; std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(void)
0x140276af8  mov     rbx, rax
0x140276afb  lea     rdx, aId_1; "id"
0x140276b02  lea     rcx, [rbp+3E0h+pExceptionObject]
0x140276b09  call    ??$?0$02@?$basic_zstring_view@_W@wil@@QEAA@AEAY02$$CB_W@Z; wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(wchar_t const (&)[3])
0x140276b0e  movups  xmm0, xmmword ptr [rax]
0x140276b11  movdqu  xmmword ptr [rbp+3E0h+var_340], xmm0
0x140276b19  lea     r8, [rbp+3E0h+var_340]
0x140276b20  lea     rdx, [rbp+3E0h+var_1E0]
0x140276b27  mov     rcx, rbx
0x140276b2a  call    ?GetMetadataValue@Update@@QEBA?AV?$optional@Vvalue@json@web@@@std@@V?$basic_zstring_view@_W@wil@@@Z; Update::GetMetadataValue(wil::basic_zstring_view<wchar_t>)
0x140276b2f  mov     rbx, rax
0x140276b32  lea     r15, psz
0x140276b39  mov     rdx, r15; wchar_t *
0x140276b3c  lea     rcx, [rbp+3E0h+var_3C0]; this
0x140276b40  call    ??0value@json@web@@QEAA@PEB_W@Z; web::json::value::value(wchar_t const *)
0x140276b45  nop
0x140276b46  mov     r8, rax
0x140276b49  lea     rdx, [rbp+3E0h+var_3B8]
0x140276b4d  mov     rcx, rbx
0x140276b50  call    ??$value_or@Vvalue@json@web@@@?$optional@Vvalue@json@web@@@std@@QEHAA?AVvalue@json@web@@$$QEAV234@@Z; std::optional<web::json::value>::value_or<web::json::value>(web::json::value &&)
0x140276b55  nop
0x140276b56  mov     rcx, rax
0x140276b59  call    ?as_string@value@json@web@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; web::json::value::as_string(void)
0x140276b5e  mov     rcx, rax
0x140276b61  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x140276b66  mov     rdx, rax
  ... truncated ...
```
