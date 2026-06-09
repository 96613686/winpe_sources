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
  __int64 v117; // rdx
  __int64 v118; // rdx
  __int64 v119; // rdx
  __int64 v120; // rdx
  __int64 v121; // rdx
  __int64 v122; // rdx
  std::_Ref_count_base *v123; // rcx
  const struct _tlgProvider_t *v124; // rax
  __int64 v125; // rax
  __int64 v126; // rax
  __int64 v127; // rax
  __int64 v128; // rax
  __int64 v129; // rax
  __int64 v130; // rax
  __int64 v131; // rax
  __int64 v132; // rax
  __int64 v133; // rax
  __int64 v134; // rax
  __int64 v135; // rax
  __int64 v136; // rax
  __int64 v137; // rcx
  __int64 v138; // rax
  __int64 v139; // rax
  unsigned int v140; // eax
  __int64 v141; // rax
  __int64 v142; // rax
  __int64 v143; // rax
  __int64 v144; // rcx
  __int64 v145; // rax
  __int64 v146; // rax
  __int64 v147; // rax
  __int64 v148; // rax
  __int64 v149; // rax
  __int64 v150; // rax
  __int64 v151; // rbx
  __int64 v152; // rbx
  const OLECHAR *v153; // r15
  __int64 v154; // rax
  __int64 v155; // rax
  __int64 v156; // rax
  __int64 v157; // rax
  __int64 v158; // rax
  __int64 v159; // rax
  __int64 v160; // rax
  __int64 v161; // rax
  __int64 v162; // rax
  __int64 v163; // rax
  __int64 v164; // rax
  __int64 v165; // rax
  Update *v166; // rax
  __int64 v167; // rax
  __int64 v168; // rax
  __int64 v169; // rax
  __int64 v170; // rax
  __int64 v171; // rax
  __int64 v172; // rax
  __int64 v173; // rax
  __int64 v174; // rax
  __int64 v175; // rax
  __int64 v176; // rax
  __int64 v177; // rax
  __int64 v178; // rbx
  __int64 v179; // r13
  __int64 v180; // r12
  __int64 v181; // r15
  __int64 v182; // r14
  __int64 v183; // rsi
  __int64 v184; // rdi
  __int64 v185; // rbx
  int v186; // eax
  const struct _tlgProvider_t *v187; // rax
  _QWORD *v188; // rax
  _QWORD *v189; // rax
  __int64 v190; // rax
  __int64 v191; // rax
  __int64 v192; // rax
  __int64 v193; // rax
  __int64 v194; // rcx
  _QWORD *v195; // rax
  int v196; // eax
  int v197; // eax
  const wchar_t *v198; // rax
  __int64 v199; // rax
  __int64 v200; // rcx
  _QWORD *v201; // rax
  __int64 v202; // rax
  int v203; // ecx
  const wchar_t *v204; // rax
  Update *v205; // rbx
  __int64 v206; // rbx
  const OLECHAR *v207; // r15
  __int64 v208; // rax
  __int64 v209; // rax
  __int64 v210; // rax
  __int64 v211; // rax
  __int64 v212; // rax
  __int64 v213; // rax
  __int64 v214; // rax
  __int64 v215; // rax
  __int64 v216; // rax
  __int64 v217; // rax
  __int64 v218; // rax
  __int64 v219; // r8
  __int64 v220; // rdx
  __int64 v221; // rdx
  __int64 v222; // rdx
  __int64 v223; // rdx
  __int64 v224; // rdx
  __int64 v225; // rdx
  __int64 v226; // rax
  const struct _tlgProvider_t *v227; // rax
  __int64 v228; // rax
  __int64 v229; // rax
  __int64 v230; // rax
  __int64 v231; // rax
  __int64 v232; // rax
  __int64 v233; // rax
  __int64 v234; // rcx
  __int64 v235; // rax
  __int64 v236; // rax
  unsigned int v237; // eax
  __int64 v238; // rax
  __int64 v239; // rax
  __int64 v240; // rax
  __int64 v241; // rcx
  __int64 v242; // rax
  __int64 v243; // rax
  __int64 v244; // rax
  __int64 v245; // rax
  __int64 v246; // rax
  __int64 v247; // rax
  __int64 v248; // rbx
  __int64 v249; // rbx
  const OLECHAR *v250; // r15
  __int64 v251; // rax
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
  Update *v263; // rax
  __int64 v264; // rax
  __int64 v265; // rax
  __int64 v266; // rax
  __int64 v267; // rax
  __int64 v268; // rax
  __int64 v269; // rax
  __int64 v270; // rax
  __int64 v271; // rax
  __int64 v272; // rax
  __int64 v273; // rax
  __int64 v274; // rax
  __int64 v275; // rbx
  __int64 v276; // r13
  __int64 v277; // r12
  __int64 v278; // r15
  __int64 v279; // r14
  __int64 v280; // rsi
  __int64 v281; // rdi
  __int64 v282; // rbx
  int v283; // eax
  const struct _tlgProvider_t *v284; // rax
  __int64 v285; // rax
  __int64 v286; // rax
  __int64 v287; // rax
  __int64 v288; // rcx
  _QWORD *v289; // rax
  int v290; // eax
  int v291; // eax
  const wchar_t *v292; // rax
  __int64 v293; // rax
  __int64 v294; // rcx
  _QWORD *v295; // rax
  __int64 v296; // rax
  int v297; // ecx
  const wchar_t *v298; // rax
  Update *v299; // rbx
  __int64 MetadataValue; // rbx
  const OLECHAR *v301; // r15
  __int64 v302; // rax
  __int64 v303; // rax
  __int64 v304; // rax
  __int64 v305; // rax
  __int64 v306; // rax
  __int64 v307; // rax
  __int64 v308; // rax
  __int64 v309; // rax
  __int64 v310; // rax
  __int64 v311; // rax
  __int64 v312; // rax
  __int64 v313; // r8
  __int64 v314; // rdx
  __int64 v315; // rdx
  __int64 v316; // rdx
  __int64 v317; // rdx
  __int64 v318; // rdx
  const struct _tlgProvider_t *v319; // rax
  __int64 v320; // rax
  __int64 v321; // rax
  __int64 v322; // rax
  __int64 v323; // rax
  __int64 v324; // rax
  __int64 v325; // rax
  __int64 v326; // rcx
  __int64 v327; // rax
  __int64 v328; // rax
  unsigned int v329; // eax
  __int64 v330; // rax
  __int64 v331; // rax
  __int64 v332; // rax
  __int64 v333; // rcx
  __int64 v334; // rax
  __int64 v335; // rax
  __int64 v336; // rax
  __int64 v337; // rax
  __int64 v338; // rax
  __int64 v339; // rax
  __int64 v340; // rbx
  __int64 v341; // rbx
  const OLECHAR *v342; // r15
  __int64 v343; // rax
  __int64 v344; // rax
  __int64 v345; // rax
  __int64 v346; // rax
  __int64 v347; // rax
  __int64 v348; // rax
  __int64 v349; // rax
  __int64 v350; // rax
  __int64 v351; // rax
  __int64 v352; // rax
  __int64 v353; // rax
  __int64 v354; // rax
  Update *v355; // rax
  __int64 v356; // rax
  __int64 v357; // rax
  __int64 v358; // rax
  __int64 v359; // rax
  __int64 v360; // rax
  __int64 v361; // rax
  __int64 v362; // rax
  __int64 v363; // rax
  __int64 v364; // rax
  __int64 v365; // rax
  __int64 v366; // rax
  __int64 v367; // rbx
  __int64 v368; // r13
  __int64 v369; // r12
  __int64 v370; // r15
  __int64 v371; // r14
  __int64 v372; // rsi
  __int64 v373; // rdi
  __int64 v374; // rbx
  int v375; // eax
  const struct _tlgProvider_t *v376; // rax
  __int64 v377; // rax
  __int64 v378; // rax
  __int64 v379; // rax
  __int64 v380; // rcx
  _QWORD *v381; // rax
  int v382; // eax
  int v383; // eax
  const wchar_t *v384; // rax
  __int64 v385; // rax
  __int64 v386; // rcx
  _QWORD *v387; // rax
  __int64 v388; // rax
  int v389; // ecx
  const wchar_t *v390; // rax
  Update *v391; // rbx
  __int64 v392; // rbx
  const OLECHAR *v393; // r15
  __int64 v394; // rax
  __int64 v395; // rax
  __int64 v396; // rax
  __int64 v397; // rax
  __int64 v398; // rax
  __int64 v399; // rax
  __int64 v400; // rax
  __int64 v401; // rax
  __int64 v402; // rax
  __int64 v403; // rax
  __int64 v404; // rax
  __int64 v405; // r8
  _BYTE v406[4]; // [rsp+170h] [rbp-80h] BYREF
  int v407; // [rsp+174h] [rbp-7Ch] BYREF
  int v408; // [rsp+178h] [rbp-78h] BYREF
  int v409; // [rsp+17Ch] [rbp-74h] BYREF
  int v410; // [rsp+180h] [rbp-70h] BYREF
  int v411; // [rsp+184h] [rbp-6Ch] BYREF
  int v412; // [rsp+188h] [rbp-68h] BYREF
  DWORD CurrentThreadId; // [rsp+18Ch] [rbp-64h] BYREF
  DWORD v414; // [rsp+190h] [rbp-60h] BYREF
  int v415; // [rsp+194h] [rbp-5Ch] BYREF
  int v416; // [rsp+198h] [rbp-58h]
  _DWORD v417[3]; // [rsp+19Ch] [rbp-54h] BYREF
  __int64 v418; // [rsp+1A8h] [rbp-48h] BYREF
  __int64 v419; // [rsp+1B0h] [rbp-40h] BYREF
  int v420; // [rsp+1B8h] [rbp-38h] BYREF
  int v421; // [rsp+1BCh] [rbp-34h] BYREF
  int v422; // [rsp+1C0h] [rbp-30h] BYREF
  BOOL v423; // [rsp+1C4h] [rbp-2Ch] BYREF
  int v424; // [rsp+1C8h] [rbp-28h] BYREF
  int v425; // [rsp+1CCh] [rbp-24h] BYREF
  int v426; // [rsp+1D0h] [rbp-20h] BYREF
  int v427; // [rsp+1D4h] [rbp-1Ch] BYREF
  int v428; // [rsp+1D8h] [rbp-18h] BYREF
  int v429; // [rsp+1DCh] [rbp-14h] BYREF
  __int64 v430; // [rsp+1E0h] [rbp-10h] BYREF
  __int64 v431; // [rsp+1E8h] [rbp-8h] BYREF
  __int64 v432; // [rsp+1F0h] [rbp+0h] BYREF
  __int64 v433; // [rsp+1F8h] [rbp+8h] BYREF
  __int64 v434; // [rsp+200h] [rbp+10h] BYREF
  __int64 v435; // [rsp+208h] [rbp+18h] BYREF
  __int64 v436; // [rsp+210h] [rbp+20h] BYREF
  __int64 v437; // [rsp+218h] [rbp+28h] BYREF
  __int64 v438; // [rsp+220h] [rbp+30h] BYREF
  __int64 v439; // [rsp+228h] [rbp+38h] BYREF
  __int64 v440; // [rsp+230h] [rbp+40h] BYREF
  __int64 v441; // [rsp+238h] [rbp+48h] BYREF
  __int64 v442; // [rsp+240h] [rbp+50h] BYREF
  __int64 v443; // [rsp+248h] [rbp+58h] BYREF
  __int64 v444; // [rsp+250h] [rbp+60h] BYREF
  __int64 FailureInfo; // [rsp+258h] [rbp+68h]
  __int64 v446; // [rsp+260h] [rbp+70h] BYREF
  __int64 v447; // [rsp+268h] [rbp+78h] BYREF
  __int64 v448; // [rsp+270h] [rbp+80h]
  __int64 v449; // [rsp+278h] [rbp+88h]
  __int64 v450; // [rsp+280h] [rbp+90h] BYREF
  __int64 v451; // [rsp+288h] [rbp+98h]
  __int64 v452[2]; // [rsp+290h] [rbp+A0h] BYREF
  _OWORD pExceptionObject[2]; // [rsp+2A0h] [rbp+B0h] BYREF
  int v454; // [rsp+2C0h] [rbp+D0h] BYREF
  _BYTE v455[4]; // [rsp+2C4h] [rbp+D4h] BYREF
  _BYTE v456[4]; // [rsp+2C8h] [rbp+D8h] BYREF
  _BYTE v457[4]; // [rsp+2CCh] [rbp+DCh] BYREF
  __int64 v458; // [rsp+2D0h] [rbp+E0h] BYREF
  __int64 v459; // [rsp+2D8h] [rbp+E8h] BYREF
  __int64 v460; // [rsp+2E0h] [rbp+F0h] BYREF
  __int64 v461; // [rsp+2E8h] [rbp+F8h] BYREF
  __int64 v462; // [rsp+2F0h] [rbp+100h] BYREF
  int v463[2]; // [rsp+2F8h] [rbp+108h] BYREF
  _BYTE v464[8]; // [rsp+300h] [rbp+110h] BYREF
  std::_Ref_count_base *v465; // [rsp+308h] [rbp+118h]
  _BYTE v466[8]; // [rsp+310h] [rbp+120h] BYREF
  std::_Ref_count_base *v467; // [rsp+318h] [rbp+128h]
  _BYTE v468[8]; // [rsp+320h] [rbp+130h] BYREF
  std::_Ref_count_base *v469; // [rsp+328h] [rbp+138h]
  _BYTE v470[8]; // [rsp+330h] [rbp+140h] BYREF
  std::_Ref_count_base *v471; // [rsp+338h] [rbp+148h]
  __int128 v472; // [rsp+340h] [rbp+150h] BYREF
  __int64 v473; // [rsp+350h] [rbp+160h] BYREF
  _BYTE v474[16]; // [rsp+358h] [rbp+168h] BYREF
  _BYTE v475[8]; // [rsp+368h] [rbp+178h] BYREF
  _BYTE v476[8]; // [rsp+370h] [rbp+180h] BYREF
  _BYTE v477[8]; // [rsp+378h] [rbp+188h] BYREF
  _BYTE v478[8]; // [rsp+380h] [rbp+190h] BYREF
  _BYTE v479[8]; // [rsp+388h] [rbp+198h] BYREF
  _BYTE v480[8]; // [rsp+390h] [rbp+1A0h] BYREF
  _BYTE v481[8]; // [rsp+398h] [rbp+1A8h] BYREF
  _BYTE v482[8]; // [rsp+3A0h] [rbp+1B0h] BYREF
  _BYTE v483[8]; // [rsp+3A8h] [rbp+1B8h] BYREF
  _BYTE v484[8]; // [rsp+3B0h] [rbp+1C0h] BYREF
  _BYTE v485[8]; // [rsp+3B8h] [rbp+1C8h] BYREF
  _BYTE v486[8]; // [rsp+3C0h] [rbp+1D0h] BYREF
  _BYTE v487[8]; // [rsp+3C8h] [rbp+1D8h] BYREF
  _BYTE v488[8]; // [rsp+3D0h] [rbp+1E0h] BYREF
  _BYTE v489[8]; // [rsp+3D8h] [rbp+1E8h] BYREF
  _BYTE v490[8]; // [rsp+3E0h] [rbp+1F0h] BYREF
  std::_Ref_count_base *v491; // [rsp+3E8h] [rbp+1F8h]
  _BYTE v492[8]; // [rsp+3F0h] [rbp+200h] BYREF
  std::_Ref_count_base *v493; // [rsp+3F8h] [rbp+208h]
  _BYTE v494[8]; // [rsp+400h] [rbp+210h] BYREF
  std::_Ref_count_base *v495; // [rsp+408h] [rbp+218h]
  _BYTE v496[8]; // [rsp+410h] [rbp+220h] BYREF
  _BYTE v497[8]; // [rsp+418h] [rbp+228h] BYREF
  _BYTE v498[8]; // [rsp+420h] [rbp+230h] BYREF
  _BYTE v499[8]; // [rsp+428h] [rbp+238h] BYREF
  _BYTE v500[8]; // [rsp+430h] [rbp+240h] BYREF
  _BYTE v501[8]; // [rsp+438h] [rbp+248h] BYREF
  _BYTE v502[32]; // [rsp+440h] [rbp+250h] BYREF
  _BYTE v503[32]; // [rsp+460h] [rbp+270h] BYREF
  _BYTE v504[32]; // [rsp+480h] [rbp+290h] BYREF
  _BYTE v505[32]; // [rsp+4A0h] [rbp+2B0h] BYREF
  _BYTE v506[32]; // [rsp+4C0h] [rbp+2D0h] BYREF
  _BYTE v507[32]; // [rsp+4E0h] [rbp+2F0h] BYREF
  _BYTE v508[32]; // [rsp+500h] [rbp+310h] BYREF
  _BYTE v509[32]; // [rsp+520h] [rbp+330h] BYREF
  _BYTE v510[32]; // [rsp+540h] [rbp+350h] BYREF
  int v511; // [rsp+560h] [rbp+370h] BYREF
  char v512; // [rsp+564h] [rbp+374h]
  _BYTE v513[16]; // [rsp+568h] [rbp+378h] BYREF
  char v514; // [rsp+578h] [rbp+388h]
  _BYTE v515[8]; // [rsp+580h] [rbp+390h] BYREF

  v449 = a3;
  v7 = a1;
  v451 = a1;
  v8 = 0;
  v416 = 0;
  v9 = (Update **)(a1 + 352);
  v10 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(a1 + 352);
  (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v10 + 296LL))(v10, v513);
  System = SystemInterface::Providers::GetSystem(v490);
  v12 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(System);
  v13 = *(int *)(*(_QWORD *)(v12 + 8) + 4LL) + v12 + 8;
  v14 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v13 + 56LL))(v13, v474);
  v15 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v14);
  (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v15 + 48LL))(v15, v515);
  std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v474);
  std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v490);
  v16 = std::wstreambuf::setbuf(v515);
  v17 = (_BYTE *)std::wstreambuf::setbuf(v16);
  v18 = std::wstreambuf::setbuf(v515);
  v448 = std::get<1,bool,int>(v18);
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl'::`2'::impl);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::GetImpl'::`2'::impl);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::GetImpl'::`2'::impl) )
    {
      v226 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      Update::GetExtendedErrorResult(v226, &v511);
      FailureInfo = wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(v7);
      if ( !FailureInfo )
      {
        wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(v7);
        v284 = Windows::Telemetry::Base::Provider();
        v430 = (__int64)v284;
        if ( *(_DWORD *)v284 > 5u
          && (*((_QWORD *)v284 + 2) & 0x400000000000LL) != 0
          && (*((_QWORD *)v284 + 3) & 0x400000000000LL) == *((_QWORD *)v284 + 3) )
        {
          v450 = (__int64)"1507.2603.28012.0";
          v412 = *(_DWORD *)v448;
          v406[0] = *v17;
          v285 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 8LL))(a2, v502);
          v436 = std::string::c_str(v285);
          v437 = v7 + 416;
          v439 = *a4;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl) )
            v286 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(a5);
          else
            v286 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v7 + 384);
          v440 = v286;
          v287 = SystemInterface::Providers::GetSystem(v466);
          v288 = *(_QWORD *)v287 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v287 + 8LL) + 4LL);
          v289 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v288 + 96LL))(v288, v468);
          v290 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v289 + 8LL))(*v289);
          if ( v290 )
          {
            v291 = v290 - 1;
            if ( v291 )
            {
              if ( v291 != 1 )
              {
                std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
                throw (std::logic_error *)pExceptionObject;
              }
              v292 = L"Internet";
            }
            else
            {
              v292 = L"local only";
            }
          }
          else
          {
            v292 = L"none";
          }
          v441 = (__int64)v292;
          v293 = SystemInterface::Providers::GetSystem(v470);
          v294 = *(_QWORD *)v293 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v293 + 8LL) + 4LL);
          v295 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v294 + 8LL))(v294, v464);
          v452[0] = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v295 + 104LL))(*v295)
                  - (unsigned __int64)*(unsigned int *)(v7 + 344);
          v296 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v7 + 328) + 8LL))(
                   *(_QWORD *)(v7 + 328),
                   v474);
          std::chrono::duration_cast<std::chrono::duration<int,std::ratio<60,1>>,__int64,std::ratio<1,1000000>,0>(
            &v409,
            v296);
          v411 = v409;
          v410 = v512 != 0 ? v511 : 0;
          v442 = *(_QWORD *)v449;
          v297 = *(_DWORD *)(v7 + 380);
          if ( v297 )
          {
            if ( v297 != 1 )
            {
              std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Unknown action priority");
              throw (std::logic_error *)pExceptionObject;
            }
            v298 = L"Low";
          }
          else
          {
            v298 = L"Normal";
          }
          v443 = (__int64)v298;
          v408 = *(unsigned __int8 *)(v7 + 376);
          v299 = *v9;
          pExceptionObject[0] = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v509, L"id");
          MetadataValue = Update::GetMetadataValue(v299, &v472, pExceptionObject);
          v301 = &psz;
          v302 = web::json::value::value((web::json::value *)&v418, &psz);
          v303 = std::optional<web::json::value>::value_or<web::json::value>(MetadataValue, &v419, v302);
          v304 = web::json::value::as_string(v303);
          v444 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v304);
          v305 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 48LL))(*v9, v503);
          *(_QWORD *)&v417[1] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v305);
          v306 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 32LL))(*v9, v504);
          v438 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v306);
          v407 = (*(unsigned __int8 (__fastcall **)(Update *))(*(_QWORD *)*v9 + 640LL))(*v9);
          v415 = (*(unsigned __int8 (__fastcall **)(Update *))(*(_QWORD *)*v9 + 552LL))(*v9);
          v414 = Update::Seeker(*v9);
          v307 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 24LL))(*v9, v505);
          v435 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v307);
          if ( v514 )
          {
            v308 = std::optional<std::shared_ptr<Action>>::value(v513);
            v309 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v308);
            v310 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v309 + 8LL))(v309, v506);
            v8 = 256;
            v416 = 256;
            v301 = (const OLECHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v310);
          }
          v434 = (__int64)v301;
          v311 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v7 + 368) + 8LL))(
                   *(_QWORD *)(v7 + 368),
                   v507);
          v433 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v311);
          v312 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 8LL))(*v9, v508);
          v432 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v312);
          CurrentThreadId = GetCurrentThreadId();
          v313 = *(_QWORD *)(v7 + 272);
          v417[0] = *(_DWORD *)(v313 + 72);
          v431 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v430,
            (int)&byte_14049E1A1,
            v313 + 8,
            (__int64)&v431,
            (__int64)v417,
            (__int64)&CurrentThreadId,
            (__int64)&v432,
            (__int64)&v433,
            (__int64)&v434,
            (__int64)&v435,
            (__int64)&v414,
            (__int64)&v415,
            (__int64)&v407,
            (__int64)&v438,
            (__int64)&v417[1],
            (__int64)&v444,
            (__int64)&v408,
            (__int64)&v443,
            (__int64)&v442,
            (__int64)&v410,
            (__int64)&v411,
            (__int64)v452,
            (__int64)&v441,
            (__int64)&v440,
            (__int64)&v439,
            (__int64)&v437,
            (__int64)&v436,
            (__int64)v406,
            (__int64)&v412,
            (__int64)&v450);
          std::wstring::~wstring(v508, v314);
          std::wstring::~wstring(v507, v315);
          if ( (v8 & 0x100) != 0 )
            std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v506);
          std::wstring::~wstring(v505, v316);
          std::wstring::~wstring(v504, v317);
          std::wstring::~wstring(v503, v318);
          std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v419);
          std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v418);
          std::_Optional_construct_base<web::json::value>::~_Optional_construct_base<web::json::value>(&v472);
          if ( v465 )
            std::_Ref_count_base::_Decref(v465);
          if ( v471 )
            std::_Ref_count_base::_Decref(v471);
          if ( v469 )
            std::_Ref_count_base::_Decref(v469);
          if ( v467 )
            std::_Ref_count_base::_Decref(v467);
          std::string::_Tidy_deallocate(v502);
        }
        goto LABEL_169;
      }
      wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(v7);
      v227 = Windows::Telemetry::Base::Provider();
      v462 = (__int64)v227;
      if ( *(_DWORD *)v227 <= 5u
        || (*((_QWORD *)v227 + 2) & 0x400000000000LL) == 0
        || (*((_QWORD *)v227 + 3) & 0x400000000000LL) != *((_QWORD *)v227 + 3) )
      {
        goto LABEL_169;
      }
      v439 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v474,
               "1507.2603.28012.0");
      v440 = _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v457, v448);
      v441 = _tlgWrapAuto<bool>(v406, v17);
      v228 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 8LL))(a2, v502);
      v229 = std::string::c_str(v228);
      v452[0] = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                  v490,
                  v229);
      winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
        &v442,
        v7 + 416);
      v230 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(a4);
      v443 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v489,
               v230);
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl) )
        v231 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(a5);
      else
        v231 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v7 + 384);
      v444 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v488,
               v231);
      v232 = SystemInterface::Providers::GetSystem(v466);
      v233 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v232);
      v234 = *(int *)(*(_QWORD *)(v233 + 8) + 4LL) + v233 + 8;
      v235 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v234 + 96LL))(v234, v468);
      v236 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v235);
      v237 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v236 + 8LL))(v236);
      v238 = SystemInterface::to_wstring(v237);
      *(_QWORD *)&v417[1] = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                              v487,
                              v238);
      v239 = SystemInterface::Providers::GetSystem(v470);
      v240 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v239);
      v241 = *(int *)(*(_QWORD *)(v240 + 8) + 4LL) + v240 + 8;
      v242 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v241 + 8LL))(v241, v464);
      v243 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v242);
      v436 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v243 + 104LL))(v243)
           - (unsigned __int64)*(unsigned int *)(v7 + 344);
      v438 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(
               v486,
               &v436);
      v244 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v7 + 328);
      v245 = SystemInterface::Timer::Elapsed<std::chrono::duration<int,std::ratio<60,1>>>(v244, v456);
      v409 = std::chrono::duration<int,std::ratio<60,1>>::count(v245);
      v435 = _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v455, &v409);
      v412 = 0;
      v411 = std::optional<long>::value_or<long>(&v511, &v412);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v429, &v411);
      v246 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v449);
      v434 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v499,
               v246);
      v247 = to_wstring(*(unsigned int *)(v7 + 380));
      v433 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v485,
               v247);
      v410 = *(unsigned __int8 *)(v7 + 376);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v426, &v410);
      v248 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      pExceptionObject[0] = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v509, L"id");
      v249 = Update::GetMetadataValue(v248, &v472, pExceptionObject);
      v250 = &psz;
      v251 = web::json::value::value((web::json::value *)&v450, &psz);
      v252 = std::optional<web::json::value>::value_or<web::json::value>(v249, v463, v251);
      v253 = web::json::value::as_string(v252);
      v254 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v253);
      v432 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v484,
               v254);
      v255 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v256 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v255 + 48LL))(v255, v503);
      v257 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v256);
      v431 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v483,
               v257);
      v258 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v259 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v258 + 32LL))(v258, v504);
      v260 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v259);
      v430 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v482,
               v260);
      v261 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v408 = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v261 + 640LL))(v261);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v425, &v408);
      v262 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v407 = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v262 + 552LL))(v262);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v424, &v407);
      v263 = (Update *)std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v415 = Update::Seeker(v263);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v423, &v415);
      v264 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v265 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v264 + 24LL))(v264, v505);
      v266 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v265);
      v419 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v481,
               v266);
      if ( (unsigned __int8)std::optional<std::shared_ptr<Action>>::has_value(v513) )
      {
        v267 = std::optional<std::shared_ptr<Action>>::value(v513);
        v268 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v267);
        v269 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v268 + 8LL))(v268, v506);
        v416 = 64;
        v250 = (const OLECHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v269);
      }
      v418 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v480,
               v250);
      v270 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v7 + 368) + 8LL))(*(_QWORD *)(v7 + 368), v507);
      v271 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v270);
      v446 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v479,
               v271);
      v272 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v273 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v272 + 8LL))(v272, v508);
      v274 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v273);
      v447 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v478,
               v274);
      v275 = FailureInfo;
      v459 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v477,
               *(_QWORD *)(FailureInfo + 120));
      v276 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v476,
               *(_QWORD *)(v275 + 112));
      v414 = *(_DWORD *)(v275 + 104);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v422, &v414);
      v277 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v475,
               *(_QWORD *)(v275 + 96));
      v278 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v501,
               *(_QWORD *)(v275 + 88));
      CurrentThreadId = *(_DWORD *)(v275 + 80);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v421, &CurrentThreadId);
      v279 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v500,
               *(_QWORD *)(v275 + 72));
      v417[0] = *(_DWORD *)(v275 + 32);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v420, v417);
      v280 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v498,
               *(_QWORD *)(v275 + 24));
      v428 = *(_DWORD *)v275;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v473, &v428);
      v281 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v497,
               *(_QWORD *)(v275 + 128));
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v454, v275 + 64);
      v282 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v496,
               *(_QWORD *)(v275 + 56));
      v427 = *(_DWORD *)(FailureInfo + 8);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v458, &v427);
      v437 = 0x1000000;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(
        &v460,
        &v437);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(
        &v461,
        &`Windows::Telemetry::UpdateManager::UpdateAction::Stop'::`85'::_tlgActivityPrivacyTag);
      v283 = wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Id(v451);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v462,
        (int)&byte_14049E94B,
        v283,
        (__int64)&v461,
        (__int64)&v460,
        (__int64)&v458,
        v282,
        (__int64)&v454,
        v281,
        (__int64)&v473,
        v280,
        (__int64)&v420,
        v279,
        (__int64)&v421,
        v278,
        v277,
        (__int64)&v422,
        v276,
        v459,
        v447,
        v446,
        v418,
        v419,
        (__int64)&v423,
        (__int64)&v424,
        (__int64)&v425,
        v430,
        v431,
        v432,
        (__int64)&v426,
        v433,
        v434,
        (__int64)&v429,
        v435,
        v438,
        *(__int64 *)&v417[1],
        v444,
        v443,
        (__int64)&v442,
        v452[0],
        v441,
        v440,
        v439);
      std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v508);
      std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v507);
      if ( (v416 & 0x40) != 0 )
        std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v506);
      std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v505);
      std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v504);
      std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v503);
      std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(v463);
      std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v450);
      std::_Optional_construct_base<web::json::value>::~_Optional_construct_base<web::json::value>(&v472);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v464);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v470);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v468);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v466);
    }
    else
    {
      FailureInfo = wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(v7);
      if ( !FailureInfo )
      {
        wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(v7);
        v376 = Windows::Telemetry::Base::Provider();
        v430 = (__int64)v376;
        if ( *(_DWORD *)v376 > 5u
          && (*((_QWORD *)v376 + 2) & 0x400000000000LL) != 0
          && (*((_QWORD *)v376 + 3) & 0x400000000000LL) == *((_QWORD *)v376 + 3) )
        {
          v450 = (__int64)"1507.2603.28012.0";
          v412 = *(_DWORD *)v448;
          v406[0] = *v17;
          v377 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 8LL))(a2, v502);
          v436 = std::string::c_str(v377);
          v437 = v7 + 416;
          v439 = *a4;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl) )
            v378 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(a5);
          else
            v378 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v7 + 384);
          v440 = v378;
          v379 = SystemInterface::Providers::GetSystem(v466);
          v380 = *(_QWORD *)v379 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v379 + 8LL) + 4LL);
          v381 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v380 + 96LL))(v380, v468);
          v382 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v381 + 8LL))(*v381);
          if ( v382 )
          {
            v383 = v382 - 1;
            if ( v383 )
            {
              if ( v383 != 1 )
              {
                std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
                throw (std::logic_error *)pExceptionObject;
              }
              v384 = L"Internet";
            }
            else
            {
              v384 = L"local only";
            }
          }
          else
          {
            v384 = L"none";
          }
          v441 = (__int64)v384;
          v385 = SystemInterface::Providers::GetSystem(v470);
          v386 = *(_QWORD *)v385 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v385 + 8LL) + 4LL);
          v387 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v386 + 8LL))(v386, v464);
          v452[0] = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v387 + 104LL))(*v387)
                  - (unsigned __int64)*(unsigned int *)(v7 + 344);
          v388 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v7 + 328) + 8LL))(
                   *(_QWORD *)(v7 + 328),
                   v474);
          std::chrono::duration_cast<std::chrono::duration<int,std::ratio<60,1>>,__int64,std::ratio<1,1000000>,0>(
            &v409,
            v388);
          v411 = v409;
          v442 = *(_QWORD *)v449;
          v389 = *(_DWORD *)(v7 + 380);
          if ( v389 )
          {
            if ( v389 != 1 )
            {
              std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Unknown action priority");
              throw (std::logic_error *)pExceptionObject;
            }
            v390 = L"Low";
          }
          else
          {
            v390 = L"Normal";
          }
          v443 = (__int64)v390;
          v410 = *(unsigned __int8 *)(v7 + 376);
          v391 = *v9;
          pExceptionObject[0] = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v509, L"id");
          v392 = Update::GetMetadataValue(v391, &v472, pExceptionObject);
          v393 = &psz;
          v394 = web::json::value::value((web::json::value *)&v418, &psz);
          v395 = std::optional<web::json::value>::value_or<web::json::value>(v392, &v419, v394);
          v396 = web::json::value::as_string(v395);
          v444 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v396);
          v397 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 48LL))(*v9, v503);
          *(_QWORD *)&v417[1] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v397);
          v398 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 32LL))(*v9, v504);
          v438 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v398);
          v408 = (*(unsigned __int8 (__fastcall **)(Update *))(*(_QWORD *)*v9 + 640LL))(*v9);
          v407 = (*(unsigned __int8 (__fastcall **)(Update *))(*(_QWORD *)*v9 + 552LL))(*v9);
          v415 = Update::Seeker(*v9);
          v399 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 24LL))(*v9, v505);
          v435 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v399);
          if ( v514 )
          {
            v400 = std::optional<std::shared_ptr<Action>>::value(v513);
            v401 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v400);
            v402 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v401 + 8LL))(v401, v506);
            v8 = 2048;
            v416 = 2048;
            v393 = (const OLECHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v402);
          }
          v434 = (__int64)v393;
          v403 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v7 + 368) + 8LL))(
                   *(_QWORD *)(v7 + 368),
                   v507);
          v433 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v403);
          v404 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 8LL))(*v9, v508);
          v432 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v404);
          v414 = GetCurrentThreadId();
          v405 = *(_QWORD *)(v7 + 272);
          CurrentThreadId = *(_DWORD *)(v405 + 72);
          v431 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v430,
            (int)&byte_14049DECD,
            v405 + 8,
            (__int64)&v431,
            (__int64)&CurrentThreadId,
            (__int64)&v414,
            (__int64)&v432,
            (__int64)&v433,
            (__int64)&v434,
            (__int64)&v435,
            (__int64)&v415,
            (__int64)&v407,
            (__int64)&v408,
            (__int64)&v438,
            (__int64)&v417[1],
            (__int64)&v444,
            (__int64)&v410,
            (__int64)&v443,
            (__int64)&v442,
            (__int64)&v411,
            (__int64)v452,
            (__int64)&v441,
            (__int64)&v440,
            (__int64)&v439,
            (__int64)&v437,
            (__int64)&v436,
            (__int64)v406,
            (__int64)&v412,
            (__int64)&v450);
          std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v508);
          std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v507);
          if ( (v8 & 0x800) != 0 )
            std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v506);
          std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v505);
          std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v504);
          std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v503);
          std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v419);
          std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v418);
          std::_Optional_construct_base<web::json::value>::~_Optional_construct_base<web::json::value>(&v472);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v464);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v470);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v468);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v466);
          std::string::_Tidy_deallocate(v502);
        }
        goto LABEL_169;
      }
      wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(v7);
      v319 = Windows::Telemetry::Base::Provider();
      v461 = (__int64)v319;
      if ( *(_DWORD *)v319 <= 5u
        || (*((_QWORD *)v319 + 2) & 0x400000000000LL) == 0
        || (*((_QWORD *)v319 + 3) & 0x400000000000LL) != *((_QWORD *)v319 + 3) )
      {
        goto LABEL_169;
      }
      v437 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v474,
               "1507.2603.28012.0");
      v439 = _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v457, v448);
      v440 = _tlgWrapAuto<bool>(v406, v17);
      v320 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 8LL))(a2, v502);
      v321 = std::string::c_str(v320);
      v441 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v490,
               v321);
      winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
        v452,
        v7 + 416);
      v322 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(a4);
      v442 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v489,
               v322);
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl) )
        v323 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(a5);
      else
        v323 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v7 + 384);
      v443 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v488,
               v323);
      v324 = SystemInterface::Providers::GetSystem(v466);
      v325 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v324);
      v326 = *(int *)(*(_QWORD *)(v325 + 8) + 4LL) + v325 + 8;
      v327 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v326 + 96LL))(v326, v468);
      v328 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v327);
      v329 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v328 + 8LL))(v328);
      v330 = SystemInterface::to_wstring(v329);
      v444 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v487,
               v330);
      v331 = SystemInterface::Providers::GetSystem(v470);
      v332 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v331);
      v333 = *(int *)(*(_QWORD *)(v332 + 8) + 4LL) + v332 + 8;
      v334 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v333 + 8LL))(v333, v464);
      v335 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v334);
      v450 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v335 + 104LL))(v335)
           - (unsigned __int64)*(unsigned int *)(v7 + 344);
      *(_QWORD *)&v417[1] = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(
                              v486,
                              &v450);
      v336 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v7 + 328);
      v337 = SystemInterface::Timer::Elapsed<std::chrono::duration<int,std::ratio<60,1>>>(v336, v456);
      v409 = std::chrono::duration<int,std::ratio<60,1>>::count(v337);
      v438 = _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v455, &v409);
      v338 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v449);
      v435 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v499,
               v338);
      v339 = to_wstring(*(unsigned int *)(v7 + 380));
      v434 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v485,
               v339);
      v412 = *(unsigned __int8 *)(v7 + 376);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v428, &v412);
      v340 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      pExceptionObject[0] = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v509, L"id");
      v341 = Update::GetMetadataValue(v340, &v472, pExceptionObject);
      v342 = &psz;
      v343 = web::json::value::value((web::json::value *)v463, &psz);
      v344 = std::optional<web::json::value>::value_or<web::json::value>(v341, &v462, v343);
      v345 = web::json::value::as_string(v344);
      v346 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v345);
      v433 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v484,
               v346);
      v347 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v348 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v347 + 48LL))(v347, v503);
      v349 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v348);
      v432 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v483,
               v349);
      v350 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v351 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v350 + 32LL))(v350, v504);
      v352 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v351);
      v431 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v482,
               v352);
      v353 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v411 = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v353 + 640LL))(v353);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v427, &v411);
      v354 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v410 = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v354 + 552LL))(v354);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v429, &v410);
      v355 = (Update *)std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v408 = Update::Seeker(v355);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v426, &v408);
      v356 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v357 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v356 + 24LL))(v356, v505);
      v358 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v357);
      v430 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v481,
               v358);
      if ( (unsigned __int8)std::optional<std::shared_ptr<Action>>::has_value(v513) )
      {
        v359 = std::optional<std::shared_ptr<Action>>::value(v513);
        v360 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v359);
        v361 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v360 + 8LL))(v360, v506);
        v416 = 512;
        v342 = (const OLECHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v361);
      }
      v419 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v480,
               v342);
      v362 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v7 + 368) + 8LL))(*(_QWORD *)(v7 + 368), v507);
      v363 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v362);
      v418 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v479,
               v363);
      v364 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
      v365 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v364 + 8LL))(v364, v508);
      v366 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v365);
      v446 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v478,
               v366);
      v367 = FailureInfo;
      v447 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v477,
               *(_QWORD *)(FailureInfo + 120));
      v368 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v476,
               *(_QWORD *)(v367 + 112));
      v407 = *(_DWORD *)(v367 + 104);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v425, &v407);
      v369 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v475,
               *(_QWORD *)(v367 + 96));
      v370 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v501,
               *(_QWORD *)(v367 + 88));
      v415 = *(_DWORD *)(v367 + 80);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v424, &v415);
      v371 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v500,
               *(_QWORD *)(v367 + 72));
      v414 = *(_DWORD *)(v367 + 32);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v423, &v414);
      v372 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v498,
               *(_QWORD *)(v367 + 24));
      CurrentThreadId = *(_DWORD *)v367;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v422, &CurrentThreadId);
      v373 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v497,
               *(_QWORD *)(v367 + 128));
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v421, v367 + 64);
      v374 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
               v496,
               *(_QWORD *)(v367 + 56));
      v417[0] = *(_DWORD *)(FailureInfo + 8);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v420, v417);
      v436 = 0x1000000;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(
        &v459,
        &v436);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(
        &v460,
        &`Windows::Telemetry::UpdateManager::UpdateAction::Stop'::`118'::_tlgActivityPrivacyTag);
      v375 = wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Id(v451);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v461,
        (int)&dword_14049E32C,
        v375,
        (__int64)&v460,
        (__int64)&v459,
        (__int64)&v420,
        v374,
        (__int64)&v421,
        v373,
        (__int64)&v422,
        v372,
        (__int64)&v423,
        v371,
        (__int64)&v424,
        v370,
        v369,
        (__int64)&v425,
        v368,
        v447,
        v446,
        v418,
        v419,
        v430,
        (__int64)&v426,
        (__int64)&v429,
        (__int64)&v427,
        v431,
        v432,
        v433,
        (__int64)&v428,
        v434,
        v435,
        v438,
        *(__int64 *)&v417[1],
        v444,
        v443,
        v442,
        (__int64)v452,
        v441,
        v440,
        v439,
        v437);
      std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v508);
      std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v507);
      if ( (v416 & 0x200) != 0 )
        std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v506);
      std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v505);
      std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v504);
      std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v503);
      std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v462);
      std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(v463);
      std::_Optional_construct_base<web::json::value>::~_Optional_construct_base<web::json::value>(&v472);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v464);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v470);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v468);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v466);
    }
    std::string::_Tidy_deallocate(v502);
    goto LABEL_147;
  }
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::GetImpl'::`2'::impl);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::GetImpl'::`2'::impl) )
  {
    v19 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
    Update::GetExtendedErrorResult(v19, &v511);
    FailureInfo = wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(v7);
    if ( FailureInfo )
    {
      wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(v7);
      v20 = Windows::Telemetry::Base::Provider();
      v439 = (__int64)v20;
      if ( *(_DWORD *)v20 > 5u
        && (*((_QWORD *)v20 + 2) & 0x400000000000LL) != 0
        && (*((_QWORD *)v20 + 3) & 0x400000000000LL) == *((_QWORD *)v20 + 3) )
      {
        v461 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 &v450,
                 "1507.2603.28012.0");
        v21 = SystemInterface::Providers::GetSystem(&v472);
        v22 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v21);
        v23 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v22 + 40LL))(v22, v464);
        v24 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v23);
        v25 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v24 + 440LL))(v24, v507);
        v26 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v25);
        v460 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 v496,
                 v26);
        v448 = _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v455, v448);
        v459 = _tlgWrapAuto<bool>(v406, v17);
        v27 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 8LL))(a2, v506);
        v28 = std::string::c_str(v27);
        v447 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 v497,
                 v28);
        winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
          &v446,
          v7 + 416);
        v29 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(a4);
        v418 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 v498,
                 v29);
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl) )
          v30 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(a5);
        else
          v30 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v7 + 384);
        v419 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 v500,
                 v30);
        v31 = SystemInterface::Providers::GetSystem(v470);
        v32 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v31);
        v33 = v32 + *(int *)(*(_QWORD *)(v32 + 8) + 4LL);
        v34 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)(v33 + 8) + 96LL))(v33 + 8, v468);
        v35 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v34);
        v36 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
        v37 = SystemInterface::to_wstring(v36);
        v430 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 v501,
                 v37);
        v38 = SystemInterface::Providers::GetSystem(v466);
        v39 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v38);
        v40 = v39 + *(int *)(*(_QWORD *)(v39 + 8) + 4LL);
        v41 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)(v40 + 8) + 8LL))(v40 + 8, v494);
        v42 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v41);
        *(_QWORD *)v463 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v42 + 104LL))(v42)
                        - (unsigned __int64)*(unsigned int *)(v7 + 344);
        v431 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(
                 v475,
                 v463);
        v43 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v7 + 328);
        v44 = SystemInterface::Timer::Elapsed<std::chrono::duration<int,std::ratio<60,1>>>(v43, v456);
        LODWORD(v458) = std::chrono::duration<int,std::ratio<60,1>>::count(v44);
        v432 = _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v457, &v458);
        v454 = 0;
        LODWORD(v473) = std::optional<long>::value_or<long>(&v511, &v454);
        _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v428, &v473);
        v45 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v449);
        v449 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 v476,
                 v45);
        v46 = to_wstring(*(unsigned int *)(v7 + 380));
        v433 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 v477,
                 v46);
        v420 = *(unsigned __int8 *)(v7 + 376);
        _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v417, &v420);
        v47 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
        *(_OWORD *)v452 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                                       pExceptionObject,
                                       L"id");
        v48 = Update::GetMetadataValue(v47, v492, v452);
        v49 = &psz;
        v50 = web::json::value::value((web::json::value *)&v436, &psz);
        v51 = std::optional<web::json::value>::value_or<web::json::value>(v48, &v437, v50);
        v52 = web::json::value::as_string(v51);
        v53 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v52);
        v434 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 v478,
                 v53);
        v54 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
        v55 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v54 + 48LL))(v54, v505);
        v56 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v55);
        v435 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 v479,
                 v56);
        v57 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
        v58 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v57 + 32LL))(v57, v504);
        v59 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v58);
        v438 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 v480,
                 v59);
        v60 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
        v421 = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v60 + 640LL))(v60);
        _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&CurrentThreadId, &v421);
        v61 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
        v422 = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v61 + 552LL))(v61);
        _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v414, &v422);
        v62 = (Update *)std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
        v423 = Update::Seeker(v62);
        _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v415, &v423);
        v63 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
        v64 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v63 + 24LL))(v63, v503);
        v65 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v64);
        *(_QWORD *)&v417[1] = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                                v481,
                                v65);
        if ( (unsigned __int8)std::optional<std::shared_ptr<Action>>::has_value(v513) )
        {
          v66 = std::optional<std::shared_ptr<Action>>::value(v513);
          v67 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v66);
          v68 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v67 + 8LL))(v67, v502);
          v416 = 1;
          v49 = (const OLECHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v68);
        }
        v444 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 v482,
                 v49);
        v69 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v7 + 368) + 8LL))(*(_QWORD *)(v7 + 368), v510);
        v70 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v69);
        v443 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 v483,
                 v70);
        v71 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
        v72 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v71 + 8LL))(v71, v509);
        v73 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v72);
        v442 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                 v484,
                 v73);
        v74 = FailureInfo;
        v452[0] = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                    v485,
                    *(_QWORD *)(FailureInfo + 120));
        v75 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                v499,
                *(_QWORD *)(v74 + 112));
        v424 = *(_DWORD *)(v74 + 104);
        _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v407, &v424);
        v76 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                v486,
                *(_QWORD *)(v74 + 96));
        v77 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                v487,
                *(_QWORD *)(v74 + 88));
        v425 = *(_DWORD *)(v74 + 80);
        _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v408, &v425);
        v78 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                v488,
                *(_QWORD *)(v74 + 72));
        v426 = *(_DWORD *)(v74 + 32);
        _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v410, &v426);
        v79 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                v489,
                *(_QWORD *)(v74 + 24));
        v429 = *(_DWORD *)v74;
        _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v411, &v429);
        v80 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                v490,
                *(_QWORD *)(v74 + 128));
        _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v412, v74 + 64);
        v81 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                v474,
                *(_QWORD *)(v74 + 56));
        v427 = *(_DWORD *)(FailureInfo + 8);
        _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v409, &v427);
        v462 = 0x1000000;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(
          &v441,
          &v462);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(
          &v440,
          &`Windows::Telemetry::UpdateManager::UpdateAction::Stop'::`16'::_tlgActivityPrivacyTag);
        v82 = wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Id(v451);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
          v439,
          (int)&byte_14049ED4B,
          v82,
          (__int64)&v440,
          (__int64)&v441,
          (__int64)&v409,
          v81,
          (__int64)&v412,
          v80,
          (__int64)&v411,
          v79,
          (__int64)&v410,
          v78,
          (__int64)&v408,
          v77,
          v76,
          (__int64)&v407,
          v75,
          v452[0],
          v442,
          v443,
          v444,
          *(__int64 *)&v417[1],
          (__int64)&v415,
          (__int64)&v414,
          (__int64)&CurrentThreadId,
          v438,
          v435,
          v434,
          (__int64)v417,
          v433,
          v449,
          (__int64)&v428,
          v432,
          v431,
          v430,
          v419,
          v418,
          (__int64)&v446,
          v447,
          v459,
          v448,
          v460,
          v461);
        std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v509);
        std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v510);
        if ( (v416 & 1) != 0 )
          std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v502);
        std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v503);
        std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v504);
        std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v505);
        std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v437);
        std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v436);
        std::_Optional_construct_base<web::json::value>::~_Optional_construct_base<web::json::value>(v492);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v494);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v466);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v468);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v470);
        std::string::_Tidy_deallocate(v506);
        std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v507);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v464);
        v83 = &v472;
LABEL_58:
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v83);
LABEL_147:
        v7 = v451;
        goto LABEL_169;
      }
      goto LABEL_169;
    }
    wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(v7);
    v84 = Windows::Telemetry::Base::Provider();
    v418 = (__int64)v84;
    if ( *(_DWORD *)v84 <= 5u
      || (*((_QWORD *)v84 + 2) & 0x400000000000LL) == 0
      || (*((_QWORD *)v84 + 3) & 0x400000000000LL) != *((_QWORD *)v84 + 3) )
    {
      goto LABEL_169;
    }
    v436 = (__int64)"1507.2603.28012.0";
    v85 = (_QWORD *)SystemInterface::Providers::GetSystem(v490);
    v86 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v85 + 40LL))(*v85, v492);
    v87 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v86 + 440LL))(*v86, v508);
    v437 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v87);
    v412 = *(_DWORD *)v448;
    v406[0] = *v17;
    v88 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 8LL))(a2, v510);
    v439 = std::string::c_str(v88);
    v440 = v7 + 416;
    v441 = *a4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl) )
      v89 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(a5);
    else
      v89 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v7 + 384);
    v452[0] = v89;
    v90 = SystemInterface::Providers::GetSystem(v494);
    v91 = *(_QWORD *)v90 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v90 + 8LL) + 4LL);
    v92 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v91 + 96LL))(v91, v466);
    v93 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v92 + 8LL))(*v92);
    if ( v93 )
    {
      v94 = v93 - 1;
      if ( v94 )
      {
        if ( v94 != 1 )
        {
          std::logic_error::logic_error((std::logic_error *)v509, "Invalid connectivity level");
          throw (std::logic_error *)v509;
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
    v442 = (__int64)v95;
    v96 = SystemInterface::Providers::GetSystem(v468);
    v97 = *(_QWORD *)v96 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v96 + 8LL) + 4LL);
    v98 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v97 + 8LL))(v97, v470);
    v443 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v98 + 104LL))(*v98)
         - (unsigned __int64)*(unsigned int *)(v7 + 344);
    v99 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v7 + 328) + 8LL))(*(_QWORD *)(v7 + 328), v474);
    std::chrono::duration_cast<std::chrono::duration<int,std::ratio<60,1>>,__int64,std::ratio<1,1000000>,0>(&v409, v99);
    v411 = v409;
    v410 = v512 != 0 ? v511 : 0;
    v444 = *(_QWORD *)v449;
    v100 = *(_DWORD *)(v7 + 380);
    if ( v100 )
    {
      if ( v100 != 1 )
      {
        std::logic_error::logic_error((std::logic_error *)v509, "Unknown action priority");
        throw (std::logic_error *)v509;
      }
      v101 = L"Low";
    }
    else
    {
      v101 = L"Normal";
    }
    *(_QWORD *)&v417[1] = v101;
    v408 = *(unsigned __int8 *)(v7 + 376);
    v102 = *v9;
    v472 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(pExceptionObject, L"id");
    v103 = Update::GetMetadataValue(v102, v464, &v472);
    v104 = &psz;
    v105 = web::json::value::value((web::json::value *)&v447, &psz);
    v106 = std::optional<web::json::value>::value_or<web::json::value>(v103, &v446, v105);
    v107 = web::json::value::as_string(v106);
    v438 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v107);
    v108 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 48LL))(*v9, v502);
    v435 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v108);
    v109 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 32LL))(*v9, v503);
    v434 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v109);
    v407 = (*(unsigned __int8 (__fastcall **)(Update *))(*(_QWORD *)*v9 + 640LL))(*v9);
    v415 = (*(unsigned __int8 (__fastcall **)(Update *))(*(_QWORD *)*v9 + 552LL))(*v9);
    v414 = Update::Seeker(*v9);
    v110 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 24LL))(*v9, v504);
    v433 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v110);
    if ( v514 )
    {
      v111 = std::optional<std::shared_ptr<Action>>::value(v513);
      v112 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v111);
      v113 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v112 + 8LL))(v112, v505);
      LOBYTE(v8) = 4;
      v416 = 4;
      v104 = (const OLECHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v113);
    }
    v432 = (__int64)v104;
    v114 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v7 + 368) + 8LL))(*(_QWORD *)(v7 + 368), v506);
    v431 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v114);
    v115 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 8LL))(*v9, v507);
    v430 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v115);
    CurrentThreadId = GetCurrentThreadId();
    v116 = *(_QWORD *)(v7 + 272);
    v417[0] = *(_DWORD *)(v116 + 72);
    v419 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
      v418,
      (int)&word_14049EFB6,
      v116 + 8,
      (__int64)&v419,
      (__int64)v417,
      (__int64)&CurrentThreadId,
      (__int64)&v430,
      (__int64)&v431,
      (__int64)&v432,
      (__int64)&v433,
      (__int64)&v414,
      (__int64)&v415,
      (__int64)&v407,
      (__int64)&v434,
      (__int64)&v435,
      (__int64)&v438,
      (__int64)&v408,
      (__int64)&v417[1],
      (__int64)&v444,
      (__int64)&v410,
      (__int64)&v411,
      (__int64)&v443,
      (__int64)&v442,
      (__int64)v452,
      (__int64)&v441,
      (__int64)&v440,
      (__int64)&v439,
      (__int64)v406,
      (__int64)&v412,
      (__int64)&v437,
      (__int64)&v436);
    std::wstring::~wstring(v507, v117);
    std::wstring::~wstring(v506, v118);
    if ( (v8 & 4) != 0 )
      std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v505);
    std::wstring::~wstring(v504, v119);
    std::wstring::~wstring(v503, v120);
    std::wstring::~wstring(v502, v121);
    std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v446);
    std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v447);
    std::_Optional_construct_base<web::json::value>::~_Optional_construct_base<web::json::value>(v464);
    if ( v471 )
      std::_Ref_count_base::_Decref(v471);
    if ( v469 )
      std::_Ref_count_base::_Decref(v469);
    if ( v467 )
      std::_Ref_count_base::_Decref(v467);
    if ( v495 )
      std::_Ref_count_base::_Decref(v495);
    std::string::_Tidy_deallocate(v510);
    std::wstring::~wstring(v508, v122);
    if ( v493 )
      std::_Ref_count_base::_Decref(v493);
    v123 = v491;
LABEL_90:
    if ( v123 )
      std::_Ref_count_base::_Decref(v123);
    goto LABEL_169;
  }
  FailureInfo = wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(v7);
  if ( !FailureInfo )
  {
    wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(v7);
    v187 = Windows::Telemetry::Base::Provider();
    v418 = (__int64)v187;
    if ( *(_DWORD *)v187 <= 5u
      || (*((_QWORD *)v187 + 2) & 0x400000000000LL) == 0
      || (*((_QWORD *)v187 + 3) & 0x400000000000LL) != *((_QWORD *)v187 + 3) )
    {
      goto LABEL_169;
    }
    v436 = (__int64)"1507.2603.28012.0";
    v188 = (_QWORD *)SystemInterface::Providers::GetSystem(v492);
    v189 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v188 + 40LL))(*v188, v494);
    v190 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v189 + 440LL))(*v189, v510);
    v437 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v190);
    v412 = *(_DWORD *)v448;
    v406[0] = *v17;
    v191 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 8LL))(a2, v502);
    v439 = std::string::c_str(v191);
    v440 = v7 + 416;
    v441 = *a4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl) )
      v192 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(a5);
    else
      v192 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v7 + 384);
    v452[0] = v192;
    v193 = SystemInterface::Providers::GetSystem(v466);
    v194 = *(_QWORD *)v193 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v193 + 8LL) + 4LL);
    v195 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v194 + 96LL))(v194, v468);
    v196 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v195 + 8LL))(*v195);
    if ( v196 )
    {
      v197 = v196 - 1;
      if ( v197 )
      {
        if ( v197 != 1 )
        {
          std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Invalid connectivity level");
          throw (std::logic_error *)pExceptionObject;
        }
        v198 = L"Internet";
      }
      else
      {
        v198 = L"local only";
      }
    }
    else
    {
      v198 = L"none";
    }
    v442 = (__int64)v198;
    v199 = SystemInterface::Providers::GetSystem(v470);
    v200 = *(_QWORD *)v199 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v199 + 8LL) + 4LL);
    v201 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v200 + 8LL))(v200, v464);
    v443 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v201 + 104LL))(*v201)
         - (unsigned __int64)*(unsigned int *)(v7 + 344);
    v202 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v7 + 328) + 8LL))(*(_QWORD *)(v7 + 328), v474);
    std::chrono::duration_cast<std::chrono::duration<int,std::ratio<60,1>>,__int64,std::ratio<1,1000000>,0>(&v409, v202);
    v411 = v409;
    v444 = *(_QWORD *)v449;
    v203 = *(_DWORD *)(v7 + 380);
    if ( v203 )
    {
      if ( v203 != 1 )
      {
        std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Unknown action priority");
        throw (std::logic_error *)pExceptionObject;
      }
      v204 = L"Low";
    }
    else
    {
      v204 = L"Normal";
    }
    *(_QWORD *)&v417[1] = v204;
    v410 = *(unsigned __int8 *)(v7 + 376);
    v205 = *v9;
    pExceptionObject[0] = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v509, L"id");
    v206 = Update::GetMetadataValue(v205, &v472, pExceptionObject);
    v207 = &psz;
    v208 = web::json::value::value((web::json::value *)&v447, &psz);
    v209 = std::optional<web::json::value>::value_or<web::json::value>(v206, &v446, v208);
    v210 = web::json::value::as_string(v209);
    v438 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v210);
    v211 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 48LL))(*v9, v503);
    v435 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v211);
    v212 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 32LL))(*v9, v504);
    v434 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v212);
    v408 = (*(unsigned __int8 (__fastcall **)(Update *))(*(_QWORD *)*v9 + 640LL))(*v9);
    v407 = (*(unsigned __int8 (__fastcall **)(Update *))(*(_QWORD *)*v9 + 552LL))(*v9);
    v415 = Update::Seeker(*v9);
    v213 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 24LL))(*v9, v505);
    v433 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v213);
    if ( v514 )
    {
      v214 = std::optional<std::shared_ptr<Action>>::value(v513);
      v215 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v214);
      v216 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v215 + 8LL))(v215, v506);
      LOBYTE(v8) = 32;
      v416 = 32;
      v207 = (const OLECHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v216);
    }
    v432 = (__int64)v207;
    v217 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v7 + 368) + 8LL))(*(_QWORD *)(v7 + 368), v507);
    v431 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v217);
    v218 = (*(__int64 (__fastcall **)(Update *, _BYTE *))(*(_QWORD *)*v9 + 8LL))(*v9, v508);
    v430 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v218);
    v414 = GetCurrentThreadId();
    v219 = *(_QWORD *)(v7 + 272);
    CurrentThreadId = *(_DWORD *)(v219 + 72);
    v419 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
      v418,
      (int)&byte_14049E7CD,
      v219 + 8,
      (__int64)&v419,
      (__int64)&CurrentThreadId,
      (__int64)&v414,
      (__int64)&v430,
      (__int64)&v431,
      (__int64)&v432,
      (__int64)&v433,
      (__int64)&v415,
      (__int64)&v407,
      (__int64)&v408,
      (__int64)&v434,
      (__int64)&v435,
      (__int64)&v438,
      (__int64)&v410,
      (__int64)&v417[1],
      (__int64)&v444,
      (__int64)&v411,
      (__int64)&v443,
      (__int64)&v442,
      (__int64)v452,
      (__int64)&v441,
      (__int64)&v440,
      (__int64)&v439,
      (__int64)v406,
      (__int64)&v412,
      (__int64)&v437,
      (__int64)&v436);
    std::wstring::~wstring(v508, v220);
    std::wstring::~wstring(v507, v221);
    if ( (v8 & 0x20) != 0 )
      std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v506);
    std::wstring::~wstring(v505, v222);
    std::wstring::~wstring(v504, v223);
    std::wstring::~wstring(v503, v224);
    std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v446);
    std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v447);
    std::_Optional_construct_base<web::json::value>::~_Optional_construct_base<web::json::value>(&v472);
    if ( v465 )
      std::_Ref_count_base::_Decref(v465);
    if ( v471 )
      std::_Ref_count_base::_Decref(v471);
    if ( v469 )
      std::_Ref_count_base::_Decref(v469);
    if ( v467 )
      std::_Ref_count_base::_Decref(v467);
    std::string::_Tidy_deallocate(v502);
    std::wstring::~wstring(v510, v225);
    if ( v495 )
      std::_Ref_count_base::_Decref(v495);
    v123 = v493;
    goto LABEL_90;
  }
  wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(v7);
  v124 = Windows::Telemetry::Base::Provider();
  *(_QWORD *)v463 = v124;
  if ( *(_DWORD *)v124 > 5u
    && (*((_QWORD *)v124 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v124 + 3) & 0x400000000000LL) == *((_QWORD *)v124 + 3) )
  {
    v439 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v474,
             "1507.2603.28012.0");
    v125 = SystemInterface::Providers::GetSystem(pExceptionObject);
    v126 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v125);
    v127 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v126 + 40LL))(v126, v492);
    v128 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v127);
    v129 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v128 + 440LL))(v128, v510);
    v130 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v129);
    v440 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v490,
             v130);
    v441 = _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v457, v448);
    v452[0] = _tlgWrapAuto<bool>(v406, v17);
    v131 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 8LL))(a2, v502);
    v132 = std::string::c_str(v131);
    v442 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v489,
             v132);
    winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
      &v443,
      v7 + 416);
    v133 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(a4);
    v444 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v488,
             v133);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_WU_ExtendedErrorCode>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UpdateModeCaching>::GetImpl'::`2'::impl) )
      v134 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(a5);
    else
      v134 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v7 + 384);
    *(_QWORD *)&v417[1] = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
                            v487,
                            v134);
    v135 = SystemInterface::Providers::GetSystem(v494);
    v136 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v135);
    v137 = *(int *)(*(_QWORD *)(v136 + 8) + 4LL) + v136 + 8;
    v138 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v137 + 96LL))(v137, v466);
    v139 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v138);
    v140 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v139 + 8LL))(v139);
    v141 = SystemInterface::to_wstring(v140);
    v438 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v486,
             v141);
    v142 = SystemInterface::Providers::GetSystem(v468);
    v143 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v142);
    v144 = *(int *)(*(_QWORD *)(v143 + 8) + 4LL) + v143 + 8;
    v145 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v144 + 8LL))(v144, v470);
    v146 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v145);
    v436 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v146 + 104LL))(v146)
         - (unsigned __int64)*(unsigned int *)(v7 + 344);
    v435 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(
             v499,
             &v436);
    v147 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v7 + 328);
    v148 = SystemInterface::Timer::Elapsed<std::chrono::duration<int,std::ratio<60,1>>>(v147, v456);
    v409 = std::chrono::duration<int,std::ratio<60,1>>::count(v148);
    v434 = _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v455, &v409);
    v149 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v449);
    v433 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v485,
             v149);
    v150 = to_wstring(*(unsigned int *)(v7 + 380));
    v432 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v484,
             v150);
    v412 = *(unsigned __int8 *)(v7 + 376);
    _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v428, &v412);
    v151 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
    v472 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v509, L"id");
    v152 = Update::GetMetadataValue(v151, v464, &v472);
    v153 = &psz;
    v154 = web::json::value::value((web::json::value *)&v473, &psz);
    v155 = std::optional<web::json::value>::value_or<web::json::value>(v152, &v511, v154);
    v156 = web::json::value::as_string(v155);
    v157 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v156);
    v431 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v483,
             v157);
    v158 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
    v159 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v158 + 48LL))(v158, v503);
    v160 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v159);
    v430 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v482,
             v160);
    v161 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
    v162 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v161 + 32LL))(v161, v504);
    v163 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v162);
    v419 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v481,
             v163);
    v164 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
    v411 = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v164 + 640LL))(v164);
    _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v427, &v411);
    v165 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
    v410 = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v165 + 552LL))(v165);
    _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v429, &v410);
    v166 = (Update *)std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
    v408 = Update::Seeker(v166);
    _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v426, &v408);
    v167 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
    v168 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v167 + 24LL))(v167, v505);
    v169 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v168);
    v418 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v480,
             v169);
    if ( (unsigned __int8)std::optional<std::shared_ptr<Action>>::has_value(v513) )
    {
      v170 = std::optional<std::shared_ptr<Action>>::value(v513);
      v171 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v170);
      v172 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v171 + 8LL))(v171, v506);
      v416 = 8;
      v153 = (const OLECHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v172);
    }
    v446 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v479,
             v153);
    v173 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v7 + 368) + 8LL))(*(_QWORD *)(v7 + 368), v507);
    v174 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v173);
    v447 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v478,
             v174);
    v175 = std::shared_ptr<SystemInterface::Reboot>::operator-><SystemInterface::Reboot,0>(v9);
    v176 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v175 + 8LL))(v175, v508);
    v177 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v176);
    v459 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v477,
             v177);
    v178 = FailureInfo;
    v460 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v476,
             *(_QWORD *)(FailureInfo + 120));
    v179 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v475,
             *(_QWORD *)(v178 + 112));
    v407 = *(_DWORD *)(v178 + 104);
    _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v425, &v407);
    v180 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v501,
             *(_QWORD *)(v178 + 96));
    v181 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v500,
             *(_QWORD *)(v178 + 88));
    v415 = *(_DWORD *)(v178 + 80);
    _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v424, &v415);
    v182 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v498,
             *(_QWORD *)(v178 + 72));
    v414 = *(_DWORD *)(v178 + 32);
    _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v423, &v414);
    v183 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v497,
             *(_QWORD *)(v178 + 24));
    CurrentThreadId = *(_DWORD *)v178;
    _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v422, &CurrentThreadId);
    v184 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             v496,
             *(_QWORD *)(v178 + 128));
    _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v421, v178 + 64);
    v185 = winrt::impl::root_implements<winrt::impl::reference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IReference<enum winrt::Windows::Management::Update::WindowsSoftwareUpdateRestartReason>,winrt::Windows::Foundation::IPropertyValue>::abi_guard::abi_guard(
             &v450,
             *(_QWORD *)(v178 + 56));
    v417[0] = *(_DWORD *)(FailureInfo + 8);
    _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(&v420, v417);
    v437 = 0x1000000;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(
      &v461,
      &v437);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void sqlite3_free(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(
      &v462,
      &`Windows::Telemetry::UpdateManager::UpdateAction::Stop'::`49'::_tlgActivityPrivacyTag);
    v186 = wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Id(v451);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
      v463[0],
      (int)&unk_14049E578,
      v186,
      (__int64)&v462,
      (__int64)&v461,
      (__int64)&v420,
      v185,
      (__int64)&v421,
      v184,
      (__int64)&v422,
      v183,
      (__int64)&v423,
      v182,
      (__int64)&v424,
      v181,
      v180,
      (__int64)&v425,
      v179,
      v460,
      v459,
      v447,
      v446,
      v418,
      (__int64)&v426,
      (__int64)&v429,
      (__int64)&v427,
      v419,
      v430,
      v431,
      (__int64)&v428,
      v432,
      v433,
      v434,
      v435,
      v438,
      *(__int64 *)&v417[1],
      v444,
      (__int64)&v443,
      v442,
      v452[0],
      v441,
      v440,
      v439);
    std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v508);
    std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v507);
    if ( (v416 & 8) != 0 )
      std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v506);
    std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v505);
    std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v504);
    std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v503);
    std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v511);
    std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v473);
    std::_Optional_construct_base<web::json::value>::~_Optional_construct_base<web::json::value>(v464);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v470);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v468);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v466);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v494);
    std::string::_Tidy_deallocate(v502);
    std::tuple<std::optional<long>,std::wstring>::~tuple<std::optional<long>,std::wstring>(v510);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v492);
    v83 = pExceptionObject;
    goto LABEL_58;
  }
LABEL_169:
  wil::ActivityBase<Windows::WU::Telemetry::WuProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(v7);
  ActionState::~ActionState((ActionState *)v513);
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
