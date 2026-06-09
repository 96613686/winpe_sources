# ZSTD_compressBlock_btultra_dictMatchState

- ea: `0x1802da140`
- end: `0x1802de8d8`
- name: `ZSTD_compressBlock_btultra_dictMatchState`
- size: `18328`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1802b6fe0`
- `0x1802bb530`
- `0x1802bb540`
- `0x1802bb5f0`
- `0x1802bb7b0`
- `0x1802bb7f0`
- `0x1802bb820`
- `0x1802bb8c0`
- `0x1802da140`
- `0x1802e56d0`
- `0x1802e5750`
- `0x1802e5c30`
- `0x1802e5cd0`
- `0x1802e5d20`
- `0x1802e5dc0`
- `0x1802e5dd0`
- `0x1802e6940`
- `0x1802e69f0`
- `0x1802e6a00`
- `0x1802e6a80`

## pseudocode

```c
unsigned __int64 __fastcall ZSTD_compressBlock_btultra_dictMatchState(
        __int64 a1,
        __int64 a2,
        int *a3,
        unsigned __int64 a4,
        __int64 a5)
{
  __int64 v5; // r12
  __int64 v6; // rcx
  int v7; // edx
  unsigned __int64 v8; // rdi
  unsigned int v9; // eax
  unsigned __int64 v10; // r14
  unsigned __int64 v11; // rsi
  __int64 v12; // rbx
  bool v13; // zf
  unsigned __int64 v14; // r11
  __int64 v15; // xmm2_8
  __int64 v16; // rbx
  __int64 v17; // r15
  int v18; // esi
  BOOL v19; // r13d
  unsigned int v20; // edi
  __int64 v21; // r8
  __int64 v22; // rdx
  int v23; // ecx
  unsigned int v24; // eax
  __int64 v25; // rsi
  bool v26; // cc
  unsigned int v27; // eax
  __int64 v28; // rax
  unsigned int v29; // r10d
  __int64 v30; // r8
  unsigned int v31; // ebx
  _DWORD *v32; // rax
  __int64 v33; // r8
  unsigned int v34; // r15d
  __int64 v35; // rdi
  int v36; // r11d
  unsigned int v37; // ecx
  unsigned int v38; // r11d
  __int64 *v39; // r9
  unsigned int v40; // edx
  int v41; // edx
  int v42; // eax
  int v43; // r12d
  unsigned int *v44; // rax
  unsigned int v45; // r11d
  unsigned int v46; // r9d
  unsigned int v47; // edx
  char v48; // cl
  unsigned int v49; // ecx
  unsigned int v50; // r11d
  unsigned int v51; // ecx
  unsigned int v52; // edi
  int *v53; // rcx
  _BOOL8 v54; // rax
  unsigned int v55; // r13d
  unsigned int *v56; // rsi
  unsigned int v57; // eax
  unsigned int v58; // r10d
  unsigned __int64 v59; // r8
  int v60; // eax
  __int64 v61; // r9
  unsigned __int64 v62; // r10
  _QWORD *v63; // rdx
  _QWORD *v64; // r8
  unsigned __int64 v65; // rax
  unsigned __int64 v66; // r9
  int v67; // eax
  int v68; // edx
  int v69; // r9d
  unsigned __int64 v70; // r9
  unsigned int v71; // ecx
  int MINMATCH; // eax
  _DWORD *v73; // r9
  int v74; // eax
  _DWORD *v75; // rdx
  unsigned __int64 v76; // r13
  unsigned __int64 v77; // rsi
  unsigned int *v78; // rdi
  __int64 *v79; // r9
  unsigned __int64 v80; // rax
  __int64 v81; // r10
  _QWORD *v82; // rdx
  signed __int64 v83; // rcx
  unsigned __int64 v84; // r9
  _DWORD *v85; // rcx
  unsigned int v86; // eax
  __int64 v87; // rdx
  __int64 v88; // r11
  unsigned int *v89; // rax
  __int64 v90; // rax
  unsigned __int64 v91; // r9
  unsigned __int64 v92; // r8
  unsigned int v93; // edi
  __int64 v94; // rcx
  unsigned __int64 v95; // r15
  unsigned __int64 v96; // rbx
  char *v97; // r8
  __int64 v98; // rax
  __int64 v99; // rsi
  __int64 v100; // r11
  _DWORD *v101; // rcx
  unsigned __int8 v102; // al
  unsigned __int8 v103; // cl
  bool v104; // cf
  unsigned int v105; // esi
  unsigned int v106; // eax
  __int64 v107; // rax
  unsigned int v108; // r10d
  __int64 v109; // r8
  unsigned int v110; // ebx
  _DWORD *v111; // rax
  __int64 v112; // r8
  __int64 v113; // rdi
  int v114; // r11d
  unsigned int v115; // ecx
  unsigned int v116; // r11d
  __int64 *v117; // r9
  unsigned int v118; // edx
  int v119; // edx
  int v120; // eax
  int v121; // r12d
  unsigned int *v122; // rax
  unsigned int v123; // r11d
  unsigned int v124; // r9d
  unsigned int v125; // edx
  char v126; // cl
  unsigned int v127; // ecx
  unsigned int v128; // r11d
  unsigned int v129; // ecx
  unsigned int v130; // edi
  int *v131; // rcx
  _BOOL8 v132; // rax
  unsigned int v133; // r13d
  unsigned int *v134; // rsi
  unsigned int v135; // eax
  unsigned int v136; // r10d
  unsigned __int64 v137; // r8
  int v138; // eax
  __int64 v139; // r9
  unsigned __int64 v140; // r10
  _QWORD *v141; // rdx
  _QWORD *v142; // r8
  unsigned __int64 v143; // rax
  unsigned __int64 v144; // r9
  int v145; // eax
  int v146; // edx
  int v147; // r9d
  unsigned __int64 v148; // r9
  unsigned int v149; // ecx
  int v150; // eax
  _DWORD *v151; // r9
  int v152; // eax
  _DWORD *v153; // rdx
  unsigned __int64 v154; // r13
  unsigned __int64 v155; // rsi
  unsigned int *v156; // rdi
  __int64 *v157; // r9
  unsigned __int64 v158; // rax
  __int64 v159; // r10
  _QWORD *v160; // rdx
  signed __int64 v161; // rcx
  unsigned __int64 v162; // r9
  _DWORD *v163; // rcx
  unsigned int v164; // eax
  __int64 v165; // rdx
  __int64 v166; // r11
  unsigned int *v167; // rax
  __int64 v168; // rax
  unsigned __int64 v169; // r9
  unsigned __int64 v170; // r8
  unsigned int v171; // edi
  __int64 v172; // rcx
  unsigned __int64 v173; // r15
  unsigned __int64 v174; // rbx
  char *v175; // r8
  __int64 v176; // rax
  __int64 v177; // rsi
  __int64 v178; // r11
  _DWORD *v179; // rcx
  unsigned __int8 v180; // al
  unsigned __int8 v181; // cl
  __int64 v182; // rsi
  __int64 v183; // rax
  unsigned int v184; // r10d
  __int64 v185; // r8
  unsigned int v186; // ebx
  _DWORD *v187; // rax
  __int64 v188; // r8
  __int64 v189; // rdi
  char v190; // cl
  int v191; // r11d
  unsigned int v192; // ecx
  unsigned int v193; // r11d
  __int64 *v194; // r9
  unsigned int v195; // edx
  int v196; // edx
  int v197; // eax
  int v198; // r12d
  unsigned int *v199; // rax
  unsigned int v200; // r11d
  unsigned int v201; // r9d
  unsigned int v202; // edx
  int v203; // ecx
  unsigned int v204; // edi
  unsigned int v205; // ecx
  unsigned int v206; // r11d
  unsigned int v207; // ecx
  unsigned int v208; // edi
  int *v209; // rcx
  _BOOL8 v210; // rax
  unsigned int v211; // r13d
  unsigned int *v212; // rsi
  unsigned int v213; // eax
  unsigned int v214; // r10d
  unsigned __int64 v215; // r8
  int v216; // eax
  __int64 v217; // r9
  unsigned __int64 v218; // r10
  _QWORD *v219; // rdx
  _QWORD *v220; // r8
  unsigned __int64 v221; // rax
  unsigned __int64 v222; // r9
  int v223; // eax
  int v224; // edx
  int v225; // r9d
  unsigned __int64 v226; // r9
  unsigned int v227; // ecx
  int v228; // eax
  _DWORD *v229; // r9
  int v230; // eax
  _DWORD *v231; // rdx
  unsigned __int64 v232; // r13
  unsigned __int64 v233; // rsi
  unsigned int *v234; // rdi
  __int64 *v235; // r9
  unsigned __int64 v236; // rax
  __int64 v237; // r10
  _QWORD *v238; // rdx
  signed __int64 v239; // rcx
  unsigned __int64 v240; // r9
  _DWORD *v241; // rcx
  unsigned int v242; // eax
  __int64 v243; // rdx
  __int64 v244; // r11
  unsigned int *v245; // rax
  __int64 v246; // rax
  unsigned __int64 v247; // r9
  unsigned __int64 v248; // r8
  unsigned int v249; // edi
  __int64 v250; // rcx
  unsigned __int64 v251; // r15
  unsigned __int64 v252; // rbx
  char *v253; // r8
  __int64 v254; // rax
  __int64 v255; // rsi
  __int64 v256; // r11
  _DWORD *v257; // rcx
  unsigned __int8 v258; // al
  unsigned __int8 v259; // cl
  unsigned int v260; // eax
  unsigned int v261; // r13d
  __int64 *v262; // r10
  __int64 v263; // rax
  unsigned int v264; // r9d
  __int64 v265; // r8
  unsigned int v266; // ebx
  _DWORD *v267; // rax
  __int64 v268; // r8
  unsigned int v269; // r15d
  __int64 v270; // rdi
  char v271; // cl
  __int64 v272; // r10
  unsigned int v273; // r11d
  unsigned int v274; // ecx
  unsigned int v275; // edx
  int v276; // r10d
  int v277; // eax
  int v278; // r12d
  unsigned int *v279; // rax
  unsigned int v280; // r11d
  unsigned int v281; // edx
  int v282; // ecx
  unsigned int v283; // r10d
  unsigned int v284; // ecx
  unsigned int v285; // edx
  unsigned int v286; // edi
  int *v287; // rcx
  unsigned int v288; // r11d
  int *v289; // rsi
  unsigned int v290; // eax
  unsigned int v291; // r8d
  unsigned int v292; // r9d
  int v293; // eax
  __int64 v294; // rcx
  __int64 v295; // r10
  int v296; // r8d
  _QWORD *v297; // rdx
  __int64 v298; // r9
  _QWORD *v299; // r8
  unsigned __int64 v300; // rax
  int v301; // eax
  int v302; // edx
  int v303; // r9d
  __int64 v304; // r8
  int v305; // eax
  int v306; // ecx
  int v307; // r10d
  int v308; // r8d
  int v309; // eax
  _DWORD *v310; // rdx
  unsigned __int64 v311; // rdx
  unsigned __int64 v312; // rsi
  unsigned int FirstIndexHash3; // eax
  unsigned int v314; // r8d
  unsigned __int64 v315; // rax
  int v316; // r11d
  _DWORD *v317; // rdx
  int v318; // ecx
  int v319; // r11d
  unsigned int *v320; // rdi
  unsigned __int64 v321; // rax
  unsigned __int64 v322; // r9
  char *v323; // r10
  _QWORD *v324; // rdx
  char *v325; // r8
  unsigned __int64 v326; // rcx
  unsigned __int64 v327; // r9
  _DWORD *v328; // rcx
  unsigned int v329; // eax
  __int64 v330; // rdx
  __int64 v331; // r11
  unsigned int *v332; // rax
  __int64 v333; // rax
  unsigned __int64 v334; // r8
  unsigned __int64 v335; // r10
  unsigned __int64 v336; // r9
  unsigned int v337; // edi
  __int64 v338; // rcx
  unsigned __int64 v339; // r15
  char *v340; // rbx
  char *v341; // r8
  unsigned __int64 v342; // r12
  __int64 v343; // rax
  __int64 v344; // rsi
  __int64 v345; // r11
  unsigned int v346; // eax
  _DWORD *v347; // rcx
  unsigned __int8 v348; // al
  unsigned __int8 v349; // cl
  _DWORD *v350; // rcx
  unsigned int v351; // ebx
  __int64 v352; // r12
  __int64 v353; // r8
  int v354; // eax
  _DWORD *v355; // r9
  unsigned int *v356; // r15
  unsigned int v357; // r10d
  unsigned int v358; // edi
  unsigned int v359; // r13d
  unsigned int v360; // esi
  __int64 v361; // rcx
  int v362; // eax
  _DWORD *v363; // r8
  __int128 v364; // xmm0
  __int64 v365; // xmm1_8
  __int64 v366; // rdx
  __int64 v367; // r8
  unsigned int v368; // ecx
  unsigned int v369; // eax
  unsigned __int64 v370; // r8
  __int64 v371; // rcx
  int v372; // ebx
  __int64 v373; // rdx
  unsigned int v374; // edi
  unsigned int v375; // r12d
  unsigned __int64 v376; // rcx
  unsigned int v377; // edi
  _DWORD *v378; // rax
  unsigned int v379; // r14d
  unsigned int *v380; // r12
  unsigned __int64 v381; // r13
  unsigned int v382; // ebx
  __int64 updated; // rax
  int v384; // r10d
  int v385; // r11d
  __int64 v386; // xmm1_8
  int v387; // r15d
  __int64 v388; // r14
  __int64 v389; // r9
  __int64 v390; // r8
  unsigned int v391; // ecx
  unsigned int v392; // edx
  unsigned int v393; // edx
  unsigned int v394; // ecx
  unsigned int v395; // r9d
  unsigned int v396; // eax
  __int64 v397; // rax
  unsigned int v398; // r8d
  unsigned int v399; // ecx
  _DWORD *v400; // r9
  __int64 v401; // rcx
  unsigned int v402; // eax
  __int64 v403; // r12
  unsigned int v404; // edi
  unsigned int v405; // r11d
  unsigned __int64 v406; // r13
  _DWORD *v407; // r15
  unsigned int v408; // esi
  int v409; // ebx
  int v410; // r8d
  int v411; // ebx
  int v412; // eax
  __int64 v413; // r8
  unsigned int v414; // r11d
  int v415; // eax
  _DWORD *v416; // rbx
  int v417; // r12d
  __int64 v418; // xmm0_8
  int v419; // eax
  int v420; // eax
  int v421; // eax
  __int64 v422; // r10
  unsigned __int64 v423; // r11
  __int64 v424; // rbx
  __int64 v425; // r12
  int v426; // r15d
  unsigned int v427; // esi
  __int64 v428; // r13
  unsigned int v429; // ebx
  __int64 v430; // r8
  __int64 v431; // rdx
  unsigned int v432; // eax
  __int64 v433; // rax
  unsigned int v434; // r9d
  unsigned __int64 v435; // r11
  __int64 v436; // r8
  unsigned int v437; // r15d
  __int64 v438; // r10
  __int64 v439; // r12
  char v440; // cl
  unsigned int v441; // ecx
  unsigned int v442; // r10d
  __int64 v443; // rsi
  unsigned int v444; // edx
  int v445; // r8d
  int v446; // eax
  int v447; // ecx
  unsigned __int64 v448; // rax
  unsigned int v449; // r10d
  unsigned int v450; // edx
  char v451; // cl
  unsigned int v452; // ecx
  _DWORD *v453; // rcx
  unsigned int v454; // edx
  unsigned int v455; // r12d
  unsigned int v456; // r10d
  unsigned int *v457; // r13
  unsigned int v458; // eax
  __int64 v459; // r9
  unsigned __int64 v460; // r8
  int v461; // eax
  __int64 v462; // r9
  _QWORD *v463; // rdx
  _QWORD *v464; // r8
  unsigned __int64 v465; // rax
  unsigned __int64 v466; // r9
  int v467; // eax
  int v468; // edx
  int v469; // r9d
  int v470; // eax
  __int64 v471; // rdx
  __int64 v472; // rcx
  _DWORD *v473; // r11
  __int64 v474; // rsi
  char *v475; // r11
  unsigned __int64 v476; // r8
  unsigned __int64 v477; // rcx
  __int64 v478; // rax
  int v479; // ebx
  __int64 v480; // r11
  _DWORD *v481; // rcx
  int v482; // r12d
  unsigned int v483; // esi
  unsigned __int64 v484; // r13
  unsigned int *v485; // rbx
  unsigned __int64 v486; // rax
  unsigned __int64 v487; // r9
  unsigned __int64 v488; // r10
  _QWORD *v489; // rdx
  char *v490; // r11
  signed __int64 v491; // rcx
  unsigned __int64 v492; // r9
  _DWORD *v493; // rcx
  unsigned int v494; // eax
  __int64 v495; // rdx
  __int64 v496; // r11
  unsigned int *v497; // rax
  __int64 v498; // rax
  unsigned __int64 v499; // rdi
  unsigned __int64 v500; // r8
  unsigned int v501; // esi
  _DWORD *v502; // rcx
  unsigned __int64 v503; // r15
  unsigned __int64 v504; // rbx
  unsigned __int64 v505; // r8
  __int64 v506; // rax
  __int64 v507; // r14
  __int64 v508; // r11
  _DWORD *v509; // rcx
  unsigned int v510; // ecx
  unsigned __int8 v511; // al
  unsigned __int8 v512; // cl
  __int64 v513; // rax
  unsigned int v514; // r9d
  unsigned __int64 v515; // r11
  __int64 v516; // r8
  unsigned int v517; // r15d
  __int64 v518; // r10
  _DWORD *v519; // r12
  char v520; // cl
  unsigned int v521; // ecx
  unsigned int v522; // r10d
  __int64 v523; // rsi
  unsigned int v524; // edx
  int v525; // r8d
  int v526; // eax
  int v527; // ecx
  unsigned __int64 v528; // rax
  unsigned int v529; // r10d
  unsigned int v530; // edx
  char v531; // cl
  unsigned int v532; // ecx
  _DWORD *v533; // rcx
  unsigned int v534; // edx
  unsigned int v535; // r12d
  unsigned int v536; // r10d
  unsigned int *v537; // r13
  unsigned int v538; // eax
  __int64 v539; // r9
  unsigned __int64 v540; // r8
  int v541; // eax
  __int64 v542; // r9
  _QWORD *v543; // rdx
  _QWORD *v544; // r8
  unsigned __int64 v545; // rax
  unsigned __int64 v546; // r9
  int v547; // eax
  int v548; // edx
  int v549; // r9d
  int v550; // eax
  __int64 v551; // rdx
  __int64 v552; // rcx
  _DWORD *v553; // r11
  __int64 v554; // rsi
  char *v555; // r11
  unsigned __int64 v556; // r8
  __int64 v557; // rcx
  __int64 v558; // rax
  int v559; // ebx
  __int64 v560; // r11
  _DWORD *v561; // rcx
  int v562; // r12d
  unsigned int v563; // esi
  unsigned __int64 v564; // r13
  unsigned int *v565; // rbx
  unsigned __int64 v566; // rax
  unsigned __int64 v567; // r9
  __int64 v568; // r10
  _QWORD *v569; // rdx
  char *v570; // r11
  signed __int64 v571; // rcx
  unsigned __int64 v572; // r9
  _DWORD *v573; // rcx
  unsigned int v574; // eax
  __int64 v575; // rdx
  __int64 v576; // r11
  __int64 *v577; // rax
  __int64 v578; // rax
  unsigned __int64 v579; // rdi
  unsigned __int64 v580; // r8
  unsigned int v581; // esi
  _DWORD *v582; // rcx
  unsigned __int64 v583; // r15
  unsigned __int64 v584; // rbx
  unsigned __int64 v585; // r8
  __int64 v586; // rax
  __int64 v587; // r14
  __int64 v588; // r11
  _DWORD *v589; // rcx
  unsigned int v590; // ecx
  unsigned __int8 v591; // al
  unsigned __int8 v592; // cl
  unsigned int v593; // eax
  __int64 v594; // rax
  unsigned int v595; // r9d
  unsigned __int64 v596; // r11
  __int64 v597; // r8
  unsigned int v598; // r15d
  __int64 v599; // r10
  _DWORD *v600; // r12
  char v601; // cl
  unsigned int v602; // ecx
  unsigned int v603; // r10d
  __int64 v604; // rsi
  unsigned int v605; // edx
  int v606; // r8d
  int v607; // eax
  int v608; // ecx
  unsigned __int64 v609; // rax
  unsigned int v610; // r10d
  unsigned int v611; // edx
  int v612; // ecx
  unsigned int v613; // ecx
  _DWORD *v614; // rcx
  unsigned int v615; // edx
  unsigned int v616; // r12d
  unsigned int v617; // r10d
  unsigned int *v618; // r13
  unsigned int v619; // eax
  __int64 v620; // r9
  unsigned __int64 v621; // r8
  int v622; // eax
  __int64 v623; // r9
  _QWORD *v624; // rdx
  _QWORD *v625; // r8
  unsigned __int64 v626; // rax
  unsigned __int64 v627; // r9
  int v628; // eax
  int v629; // edx
  int v630; // r9d
  int v631; // eax
  __int64 v632; // rdx
  __int64 v633; // rcx
  _DWORD *v634; // r11
  __int64 v635; // rsi
  char *v636; // r11
  unsigned __int64 v637; // r8
  unsigned __int64 v638; // rcx
  __int64 v639; // rax
  int v640; // ebx
  __int64 v641; // r11
  _DWORD *v642; // rcx
  int v643; // r12d
  unsigned int v644; // esi
  unsigned __int64 v645; // r13
  unsigned int *v646; // rbx
  unsigned __int64 v647; // rax
  unsigned __int64 v648; // r9
  __int64 v649; // r10
  _QWORD *v650; // rdx
  char *v651; // r11
  signed __int64 v652; // rcx
  unsigned __int64 v653; // r9
  _DWORD *v654; // rcx
  unsigned int v655; // eax
  __int64 v656; // rdx
  __int64 v657; // r11
  unsigned int *v658; // rax
  __int64 v659; // rax
  unsigned __int64 v660; // rdi
  unsigned __int64 v661; // r8
  unsigned int v662; // esi
  _DWORD *v663; // rcx
  unsigned __int64 v664; // r15
  unsigned __int64 v665; // rbx
  unsigned __int64 v666; // r8
  __int64 v667; // rax
  __int64 v668; // r14
  __int64 v669; // r11
  _DWORD *v670; // rcx
  unsigned int v671; // ecx
  unsigned __int8 v672; // al
  unsigned __int8 v673; // cl
  unsigned int v674; // eax
  __int64 v675; // rax
  unsigned int v676; // r9d
  unsigned __int64 v677; // r11
  __int64 v678; // r8
  unsigned int v679; // r15d
  __int64 v680; // r10
  __int64 v681; // r12
  char v682; // cl
  unsigned int v683; // ecx
  unsigned int v684; // r10d
  __int64 v685; // rsi
  unsigned int v686; // edx
  int v687; // r8d
  int v688; // eax
  int v689; // ecx
  unsigned __int64 v690; // rax
  unsigned int v691; // r10d
  unsigned int v692; // edx
  int v693; // ecx
  unsigned int v694; // ecx
  _DWORD *v695; // rcx
  unsigned int v696; // edx
  unsigned int v697; // r12d
  unsigned int v698; // r10d
  unsigned int *v699; // r13
  unsigned int v700; // eax
  unsigned int v701; // r8d
  __int64 v702; // r9
  int v703; // eax
  __int64 v704; // r10
  int v705; // r8d
  _QWORD *v706; // rdx
  unsigned __int64 v707; // r9
  _QWORD *v708; // r8
  unsigned __int64 v709; // rax
  int v710; // ecx
  unsigned __int64 v711; // r8
  __int64 v712; // rax
  _DWORD *v713; // rcx
  int v714; // eax
  int v715; // edx
  int v716; // r9d
  __int64 v717; // r8
  int v718; // eax
  __int64 v719; // rdx
  __int64 v720; // rcx
  __int64 v721; // r11
  int v722; // r8d
  __int64 v723; // rsi
  __int64 v724; // r11
  unsigned __int64 v725; // r8
  unsigned __int64 v726; // rcx
  __int64 v727; // rax
  int v728; // ebx
  __int64 v729; // r11
  unsigned int v730; // eax
  unsigned int v731; // esi
  unsigned __int64 v732; // r8
  unsigned __int64 v733; // r12
  unsigned __int64 v734; // rax
  int v735; // r11d
  _DWORD *v736; // rdx
  int v737; // ecx
  int v738; // r11d
  int v739; // r13d
  unsigned int v740; // esi
  unsigned int *v741; // rbx
  unsigned __int64 v742; // rax
  unsigned __int64 v743; // r9
  __int64 v744; // r10
  _QWORD *v745; // rdx
  unsigned __int64 v746; // rcx
  unsigned __int64 v747; // r9
  _DWORD *v748; // rcx
  unsigned int v749; // eax
  __int64 v750; // rdx
  __int64 v751; // r11
  unsigned int *v752; // rax
  __int64 v753; // rax
  unsigned int v754; // r9d
  unsigned __int64 v755; // rdi
  unsigned __int64 v756; // r8
  unsigned int v757; // esi
  __int64 v758; // rcx
  unsigned __int64 v759; // r15
  __int64 v760; // rbx
  unsigned __int64 v761; // r12
  unsigned __int64 v762; // r8
  unsigned __int64 v763; // rax
  __int64 v764; // rax
  __int64 v765; // r14
  __int64 v766; // r11
  unsigned int v767; // eax
  _DWORD *v768; // rcx
  unsigned int v769; // ecx
  unsigned __int8 v770; // al
  unsigned __int8 v771; // cl
  _DWORD *v772; // rbx
  unsigned int v773; // ecx
  unsigned int v774; // r13d
  unsigned int *v775; // r10
  int v776; // r15d
  __int64 v777; // rax
  _DWORD *v778; // r10
  unsigned int v779; // edx
  __int64 v780; // xmm1_8
  unsigned int v781; // esi
  int v782; // r14d
  __int64 v783; // r13
  unsigned int v784; // eax
  __int64 v785; // r10
  __int64 v786; // r9
  unsigned int v787; // ecx
  signed int v788; // r8d
  __int64 v789; // rcx
  unsigned int v790; // r8d
  int v791; // r10d
  unsigned int v792; // ecx
  __int64 v793; // rcx
  __int64 v794; // rdx
  unsigned int v795; // r9d
  unsigned int v796; // ecx
  __int64 v797; // rdx
  unsigned int v798; // ecx
  __int64 v799; // rax
  int v800; // eax
  _DWORD *v801; // rdx
  __int64 v802; // rdx
  __int128 v803; // xmm0
  unsigned int v804; // eax
  int v805; // eax
  unsigned int v806; // ecx
  __int64 v807; // rcx
  int v808; // r8d
  unsigned int v809; // r15d
  unsigned __int64 v810; // rdx
  unsigned __int64 v811; // rbx
  __int64 v812; // rcx
  unsigned __int64 v813; // rdx
  __int64 v814; // r10
  __int64 v815; // rcx
  unsigned __int64 v816; // rax
  __int64 v817; // rcx
  unsigned __int64 v818; // rcx
  __int64 v819; // rcx
  unsigned __int64 v820; // rax
  __int64 v821; // rcx
  __int64 v822; // rcx
  __int64 v823; // rcx
  unsigned int v825; // [rsp+30h] [rbp-D0h]
  unsigned int v826; // [rsp+30h] [rbp-D0h]
  unsigned int v827; // [rsp+30h] [rbp-D0h]
  unsigned int v828; // [rsp+30h] [rbp-D0h]
  unsigned int v829; // [rsp+30h] [rbp-D0h]
  unsigned int v830; // [rsp+30h] [rbp-D0h]
  unsigned int v831; // [rsp+30h] [rbp-D0h]
  unsigned int v832; // [rsp+30h] [rbp-D0h]
  unsigned int v833; // [rsp+34h] [rbp-CCh]
  unsigned int v834; // [rsp+34h] [rbp-CCh]
  unsigned int v835; // [rsp+34h] [rbp-CCh]
  unsigned int v836; // [rsp+34h] [rbp-CCh]
  unsigned int v837; // [rsp+34h] [rbp-CCh]
  unsigned int *v838; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v839; // [rsp+38h] [rbp-C8h]
  unsigned int *v840; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v841; // [rsp+38h] [rbp-C8h]
  unsigned int *v842; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v843; // [rsp+38h] [rbp-C8h]
  unsigned int *v844; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v845; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v846; // [rsp+38h] [rbp-C8h]
  unsigned int v847; // [rsp+40h] [rbp-C0h]
  unsigned int v848; // [rsp+40h] [rbp-C0h]
  unsigned int v849; // [rsp+40h] [rbp-C0h]
  unsigned int v850; // [rsp+40h] [rbp-C0h]
  unsigned int v851; // [rsp+40h] [rbp-C0h]
  int v852; // [rsp+40h] [rbp-C0h]
  int v853; // [rsp+40h] [rbp-C0h]
  int v854; // [rsp+40h] [rbp-C0h]
  int v855; // [rsp+40h] [rbp-C0h]
  unsigned int v856; // [rsp+40h] [rbp-C0h]
  unsigned int *v857; // [rsp+48h] [rbp-B8h]
  unsigned int *v858; // [rsp+48h] [rbp-B8h]
  unsigned int *v859; // [rsp+48h] [rbp-B8h]
  unsigned int *v860; // [rsp+48h] [rbp-B8h]
  unsigned int *v861; // [rsp+48h] [rbp-B8h]
  unsigned int *v862; // [rsp+48h] [rbp-B8h]
  unsigned int *v863; // [rsp+48h] [rbp-B8h]
  unsigned int *v864; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v865; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v866; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v867; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v868; // [rsp+48h] [rbp-B8h]
  unsigned int v869; // [rsp+50h] [rbp-B0h]
  unsigned int v870; // [rsp+50h] [rbp-B0h]
  unsigned int v871; // [rsp+50h] [rbp-B0h]
  unsigned int v872; // [rsp+50h] [rbp-B0h]
  unsigned int v873; // [rsp+50h] [rbp-B0h]
  unsigned int v874; // [rsp+54h] [rbp-ACh]
  unsigned int v875; // [rsp+54h] [rbp-ACh]
  unsigned int v876; // [rsp+54h] [rbp-ACh]
  unsigned int v877; // [rsp+54h] [rbp-ACh]
  unsigned int v878; // [rsp+54h] [rbp-ACh]
  unsigned int v879; // [rsp+54h] [rbp-ACh]
  unsigned int v880; // [rsp+54h] [rbp-ACh]
  int v881; // [rsp+54h] [rbp-ACh]
  int v882; // [rsp+54h] [rbp-ACh]
  unsigned int v883; // [rsp+58h] [rbp-A8h]
  unsigned int v884; // [rsp+58h] [rbp-A8h]
  unsigned int v885; // [rsp+58h] [rbp-A8h]
  unsigned int v886; // [rsp+58h] [rbp-A8h]
  int v887; // [rsp+58h] [rbp-A8h]
  int v888; // [rsp+58h] [rbp-A8h]
  unsigned int v889; // [rsp+58h] [rbp-A8h]
  unsigned int v890; // [rsp+58h] [rbp-A8h]
  int v891; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v892; // [rsp+60h] [rbp-A0h]
  unsigned int v893; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v894; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int *v895; // [rsp+70h] [rbp-90h]
  unsigned __int64 v896; // [rsp+78h] [rbp-88h]
  unsigned int v897; // [rsp+80h] [rbp-80h]
  BOOL v898; // [rsp+84h] [rbp-7Ch]
  unsigned int v899; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v900; // [rsp+8Ch] [rbp-74h]
  unsigned int v901; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v902; // [rsp+98h] [rbp-68h]
  _DWORD *v903; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v904; // [rsp+A8h] [rbp-58h]
  unsigned int v905; // [rsp+B0h] [rbp-50h]
  unsigned int v906; // [rsp+B4h] [rbp-4Ch]
  _DWORD *v907; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v908; // [rsp+C0h] [rbp-40h]
  unsigned int v909; // [rsp+C8h] [rbp-38h]
  __int64 v910; // [rsp+D0h] [rbp-30h]
  __int64 v911; // [rsp+D8h] [rbp-28h]
  unsigned int v912; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v913; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v914; // [rsp+F0h] [rbp-10h]
  __int64 v915; // [rsp+F8h] [rbp-8h] BYREF
  unsigned int v916; // [rsp+100h] [rbp+0h] BYREF
  unsigned int v917; // [rsp+104h] [rbp+4h] BYREF
  unsigned int v918; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int64 v919; // [rsp+110h] [rbp+10h]
  _DWORD *v920; // [rsp+118h] [rbp+18h]
  unsigned __int64 v921; // [rsp+120h] [rbp+20h]
  int v922; // [rsp+128h] [rbp+28h]
  unsigned __int64 v923; // [rsp+130h] [rbp+30h]
  unsigned __int64 v924; // [rsp+138h] [rbp+38h]
  __int64 v925; // [rsp+140h] [rbp+40h]
  int v926; // [rsp+148h] [rbp+48h]
  unsigned int v927; // [rsp+14Ch] [rbp+4Ch]
  int v928; // [rsp+150h] [rbp+50h] BYREF
  __int64 v929; // [rsp+158h] [rbp+58h]
  unsigned __int64 v930; // [rsp+160h] [rbp+60h]
  __int128 v931; // [rsp+168h] [rbp+68h]
  __int64 v932; // [rsp+178h] [rbp+78h]
  int v933; // [rsp+180h] [rbp+80h]
  __int128 v934; // [rsp+190h] [rbp+90h] BYREF
  __int64 v935; // [rsp+1A0h] [rbp+A0h]
  int v936; // [rsp+1A8h] [rbp+A8h]
  __int128 v937; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v938; // [rsp+1C0h] [rbp+C0h]
  int v939; // [rsp+1C8h] [rbp+C8h]
  __int128 v940; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v941; // [rsp+1E0h] [rbp+E0h]
  int v942; // [rsp+1E8h] [rbp+E8h]
  char v943[16]; // [rsp+1F0h] [rbp+F0h] BYREF
  char v944[24]; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int64 v948; // [rsp+278h] [rbp+178h]
  unsigned int v949; // [rsp+280h] [rbp+180h]
  unsigned int *v950; // [rsp+280h] [rbp+180h]
  unsigned int v951; // [rsp+280h] [rbp+180h]

  v948 = a4;
  v5 = a1;
  v6 = a1 + 72;
  v7 = 4095;
  v8 = a4;
  v925 = v6;
  v9 = *(_DWORD *)(v5 + 204);
  v10 = a4 + a5;
  v11 = a4 + a5 - 8;
  v12 = *(_QWORD *)(v5 + 8) + *(unsigned int *)(v5 + 24);
  v919 = a4 + a5;
  if ( v9 < 0xFFF )
    v7 = v9;
  v13 = *(_DWORD *)(v5 + 200) == 3;
  v927 = v7;
  v922 = !v13 + 3;
  v928 = *(_DWORD *)(v5 + 36);
  v920 = *(_DWORD **)(v6 + 40);
  v907 = *(_DWORD **)(v6 + 32);
  ZSTD_rescaleFreqs(v6, a4, a5, 2);
  v14 = v8 + (v8 == v12);
  v892 = v14;
  if ( v14 < v11 )
  {
    v15 = v932;
    v926 = v933;
    do
    {
      v16 = *(unsigned int *)(v5 + 36);
      v17 = *(_QWORD *)(v5 + 8);
      v18 = *(_DWORD *)(v5 + 200);
      v19 = v14 == v8;
      v905 = v14 - v8;
      v898 = v19;
      if ( v14 < v17 + v16 )
        goto LABEL_1003;
      v20 = v14 - v17;
      if ( (unsigned int)v16 < (int)v14 - (int)v17 )
      {
        do
          LODWORD(v16) = ZSTD_insertBt1(v5, (int)v17 + (int)v16, v10, v18, 0) + v16;
        while ( (unsigned int)v16 < v20 );
        v19 = v898;
        v14 = v892;
      }
      v21 = *(_QWORD *)(v5 + 48);
      *(_DWORD *)(v5 + 36) = v20;
      v22 = *(unsigned int *)(v5 + 192);
      if ( v18 != 3 )
      {
        v23 = 4095;
        if ( v18 != 5 )
        {
          v24 = v18 - 6;
          v25 = *(_QWORD *)(v5 + 8);
          v26 = v24 <= 1;
          v911 = v25;
          v27 = *(_DWORD *)(v5 + 204);
          if ( v26 )
          {
            if ( v27 < 0xFFF )
              v23 = *(_DWORD *)(v5 + 204);
            v899 = v23;
            v825 = v14 - v25;
            v28 = ZSTD_hash6Ptr(v14, v22, v21);
            v31 = *(_DWORD *)(v30 + 4 * v28);
            v32 = (_DWORD *)(v30 + 4 * v28);
            v33 = *(unsigned int *)(v5 + 24);
            v34 = v29 + 9;
            v35 = *(_QWORD *)(v5 + 64);
            v36 = 1 << (*(_DWORD *)(v5 + 188) - 1);
            v903 = v32;
            v37 = 0;
            v38 = v36 - 1;
            v902 = v39;
            v900 = v38;
            v913 = v25 + v33;
            v910 = v35;
            v904 = 0;
            v909 = v33;
            v847 = v29 + 9;
            if ( v38 < v29 )
              v37 = v29 - v38;
            v906 = v37;
            v40 = 1 << *(_DWORD *)(v5 + 184);
            v26 = v29 - *(_DWORD *)(v5 + 28) <= v40;
            v41 = v29 - v40;
            v42 = 1;
            if ( v26 )
              v41 = *(_DWORD *)(v5 + 28);
            if ( *(_DWORD *)(v5 + 32) )
              v41 = *(_DWORD *)(v5 + 28);
            if ( v41 )
              v42 = v41;
            v43 = 1 << *(_DWORD *)(v5 + 196);
            v883 = v42;
            v949 = 0;
            v838 = (unsigned int *)(v35 + 8LL * (v29 & v38));
            v857 = v838 + 1;
            v908 = *(_QWORD *)(a1 + 176);
            v44 = *(unsigned int **)v908;
            v45 = *(_QWORD *)v908 - *(_QWORD *)(v908 + 8);
            v914 = *(_QWORD *)(v908 + 8);
            v46 = *(_DWORD *)(v908 + 28);
            v47 = v41 - v45;
            v895 = v44;
            LODWORD(v44) = *(_DWORD *)(v908 + 192);
            v48 = *(_DWORD *)(v908 + 188) - 1;
            v893 = v45;
            v874 = v46;
            v869 = v47;
            v833 = (unsigned int)v44;
            LODWORD(v44) = v45 - v46;
            v901 = (1 << v48) - 1;
            v49 = v45;
            v50 = v19 + 3;
            v51 = v49 - v901;
            v897 = v19 + 3;
            v52 = v19;
            if ( v901 >= (unsigned int)v44 )
              v51 = v46;
            v924 = (unsigned int)(v922 - 1);
            v894 = v51;
            v53 = a3;
            v896 = v924;
            v54 = v19;
            v55 = v29 - v33;
            v56 = (unsigned int *)&a3[v54];
            while ( 1 )
            {
              if ( v52 == 3 )
                v57 = *v53 - 1;
              else
                v57 = *v56;
              v58 = v29 - v57;
              v59 = 0;
              if ( v57 - 1 >= v55 )
              {
                v70 = v914 + v58 - (unsigned __int64)v47;
                v71 = v909 - v58;
                v62 = v892;
                if ( v57 - 1 < v825 - v47 - v874 && v71 - 1 >= 3 )
                {
                  MINMATCH = ZSTD_readMINMATCH(v892, 4, 0, v70);
                  if ( MINMATCH == *v73 )
                  {
                    v74 = ZSTD_count_2segments((int)v62 + 4, (int)v73 + 4, v10, (_DWORD)v895, v913);
                    v50 = v897;
                    v62 = v892;
                    v59 = (unsigned int)(v74 + 4);
                  }
                }
              }
              else
              {
                v60 = ZSTD_readMINMATCH(v892, 4, 0, -(__int64)v57);
                if ( v60 == *(_DWORD *)(v61 + v62) )
                {
                  v63 = (_QWORD *)(v62 + 4);
                  v64 = (_QWORD *)(v61 + v62 + 4);
                  v65 = v10 - 7;
                  v66 = v62 + 4;
                  if ( v62 + 4 >= v10 - 7 )
                    goto LABEL_37;
                  if ( *v64 != *v63 )
                  {
                    v59 = (unsigned int)ZSTD_NbCommonBytes(*v64 ^ *v63, v63, v64, v66) + 4;
                    goto LABEL_51;
                  }
                  v63 = (_QWORD *)(v62 + 12);
                  ++v64;
                  if ( v62 + 12 >= v65 )
                  {
LABEL_37:
                    if ( (unsigned __int64)v63 < v10 - 3 && *(_DWORD *)v64 == *(_DWORD *)v63 )
                    {
                      v63 = (_QWORD *)((char *)v63 + 4);
                      v64 = (_QWORD *)((char *)v64 + 4);
                    }
                    if ( (unsigned __int64)v63 < v10 - 1 && *(_WORD *)v64 == *(_WORD *)v63 )
                    {
                      v63 = (_QWORD *)((char *)v63 + 2);
                      v64 = (_QWORD *)((char *)v64 + 2);
                    }
                    if ( (unsigned __int64)v63 < v10 && *(_BYTE *)v64 == *(_BYTE *)v63 )
                      LODWORD(v63) = (_DWORD)v63 + 1;
                    v59 = (unsigned int)((_DWORD)v63 - v62);
                  }
                  else
                  {
                    while ( *v64 == *v63 )
                    {
                      ++v63;
                      ++v64;
                      if ( (unsigned __int64)v63 >= v65 )
                        goto LABEL_37;
                    }
                    v67 = ZSTD_NbCommonBytes(*v64 ^ *v63, v63, v64, v66);
                    v59 = (unsigned int)(v68 - v69 + v67 + 4);
                  }
                }
              }
LABEL_51:
              if ( (unsigned int)v59 > v896 )
              {
                v75 = &v907[2 * v949];
                *v75 = v52 - v898;
                v896 = (unsigned int)v59;
                v75[1] = v59;
                ++v949;
                if ( (unsigned int)v59 > v899 || v62 + (unsigned int)v59 == v10 )
                  goto LABEL_222;
              }
              v47 = v869;
              ++v52;
              v53 = a3;
              ++v56;
              if ( v52 >= v50 )
              {
                v76 = v892;
                *v903 = v825;
                if ( v43 )
                {
                  v77 = v896;
                  do
                  {
                    --v43;
                    if ( v31 < v883 )
                      goto LABEL_88;
                    v76 = v892;
                    v78 = (unsigned int *)(v910 + 8LL * (v31 & v900));
                    v79 = (__int64 *)v904;
                    v80 = v10 - 7;
                    if ( (unsigned __int64)v902 < v904 )
                      v79 = v902;
                    v81 = v911 + v31;
                    v82 = (__int64 *)((char *)v79 + v892);
                    v59 = (unsigned __int64)v79 + v81;
                    if ( (unsigned __int64)v79 + v892 >= v80 )
                      goto LABEL_65;
                    if ( *(_QWORD *)v59 != *v82 )
                    {
                      v83 = (unsigned int)ZSTD_NbCommonBytes(*(_QWORD *)v59 ^ *v82, v82, v59, v79);
                      goto LABEL_75;
                    }
                    ++v82;
                    v59 += 8LL;
                    if ( (unsigned __int64)v82 >= v80 )
                    {
LABEL_65:
                      if ( (unsigned __int64)v82 < v10 - 3 && *(_DWORD *)v59 == *(_DWORD *)v82 )
                      {
                        v82 = (_QWORD *)((char *)v82 + 4);
                        v59 += 4LL;
                      }
                      if ( (unsigned __int64)v82 < v10 - 1 && *(_WORD *)v59 == *(_WORD *)v82 )
                      {
                        v82 = (_QWORD *)((char *)v82 + 2);
                        v59 += 2LL;
                      }
                      if ( (unsigned __int64)v82 < v10 && *(_BYTE *)v59 == *(_BYTE *)v82 )
                        v82 = (_QWORD *)((char *)v82 + 1);
                      v83 = (char *)v82 - ((char *)v79 + v892);
                    }
                    else
                    {
                      while ( *(_QWORD *)v59 == *v82 )
                      {
                        ++v82;
                        v59 += 8LL;
                        if ( (unsigned __int64)v82 >= v80 )
                          goto LABEL_65;
                      }
                      v86 = ZSTD_NbCommonBytes(*(_QWORD *)v59 ^ *v82, v82, v59, v79);
                      v83 = v87 - v88 + v86;
                    }
LABEL_75:
                    v84 = (unsigned __int64)v79 + v83;
                    if ( v84 > v77 )
                    {
                      if ( v84 > v34 - v31 )
                      {
                        v34 = v84 + v31;
                        v847 = v84 + v31;
                      }
                      v85 = &v907[2 * v949];
                      v85[1] = v84;
                      *v85 = v825 - v31 + 2;
                      ++v949;
                      v896 = v84;
                      if ( v84 > 0x1000 || v84 + v892 == v10 )
                      {
                        v43 = 0;
                        goto LABEL_88;
                      }
                      v77 = v84;
                    }
                    if ( *(_BYTE *)(v81 + v84) >= *(_BYTE *)(v84 + v892) )
                    {
                      v904 = v84;
                      *v857 = v31;
                      if ( v31 <= v906 )
                      {
                        v857 = &v899;
                        goto LABEL_88;
                      }
                      v31 = *v78;
                      v857 = v78;
                    }
                    else
                    {
                      v902 = (__int64 *)v84;
                      *v838 = v31;
                      if ( v31 <= v906 )
                      {
                        v89 = &v899;
                        goto LABEL_89;
                      }
                      v31 = v78[1];
                      v838 = v78 + 1;
                    }
                  }
                  while ( v43 );
                }
                --v43;
LABEL_88:
                v89 = v838;
LABEL_89:
                *v857 = 0;
                *v89 = 0;
                if ( v43 )
                {
                  v90 = ZSTD_hash6Ptr(v76, v833, v59);
                  v91 = 0;
                  v839 = 0;
                  v92 = 0;
                  v93 = *(_DWORD *)(*(_QWORD *)(v908 + 48) + 4 * v90);
                  v94 = *(_QWORD *)(v908 + 64);
                  v910 = v94;
                  while ( 1 )
                  {
                    v903 = (_DWORD *)v92;
                    v909 = v34;
                    v897 = v43 - 1;
                    if ( v93 <= v874 )
                      break;
                    v95 = v91;
                    if ( v92 < v91 )
                      v95 = v92;
                    v96 = v93 + v914;
                    v858 = (unsigned int *)(v94 + 8LL * (v901 & v93));
                    v97 = (char *)v10;
                    if ( (unsigned __int64)v895 + v892 - v96 < v10 )
                      v97 = (char *)v895 + v892 - v96;
                    v98 = ZSTD_count(v95 + v892, v96 + v95, v97);
                    v99 = v98;
                    if ( (unsigned int *)(v98 + v100) == v895 )
                      v99 = ZSTD_count(v98 + v95 + v892, v913, v10) + v98;
                    v92 = v95 + v99;
                    if ( v95 + v99 + v93 >= v893 )
                      v96 = v93 + v911 + v869;
                    if ( v92 <= v896 )
                    {
                      v34 = v847;
                    }
                    else
                    {
                      v34 = v93 + v869 + v92;
                      v101 = v907;
                      v907[2 * v949 + 1] = v92;
                      v101[2 * v949] = v825 - (v93 + v869) + 2;
                      v896 = v92;
                      ++v949;
                      if ( v92 <= v847 - (v93 + v869) )
                        v34 = v909;
                      v847 = v34;
                      if ( v92 > 0x1000 || v92 + v892 == v10 )
                        break;
                    }
                    if ( v93 <= v894 )
                      break;
                    v102 = *(_BYTE *)(v96 + v92);
                    v103 = *(_BYTE *)(v92 + v892);
                    if ( v102 >= v103 )
                    {
                      v93 = *v858;
                      v91 = v92;
                      v839 = v92;
                    }
                    else
                    {
                      v93 = v858[1];
                      v91 = v839;
                    }
                    v43 = v897;
                    v104 = v102 < v103;
                    v94 = v910;
                    if ( !v104 )
                      v92 = (unsigned __int64)v903;
                    if ( !v897 )
                    {
                      v105 = v949;
                      v106 = v34 - 8;
                      goto LABEL_444;
                    }
                  }
                }
LABEL_221:
                *(_DWORD *)(a1 + 36) = v34 - 8;
LABEL_222:
                v105 = v949;
                goto LABEL_445;
              }
              v29 = v825;
            }
          }
          if ( v27 < 0xFFF )
            v23 = *(_DWORD *)(v5 + 204);
          v901 = v23;
          v826 = v14 - v25;
          v107 = ZSTD_hash4Ptr(v14, v22, v21);
          v110 = *(_DWORD *)(v109 + 4 * v107);
          v111 = (_DWORD *)(v109 + 4 * v107);
          v112 = *(unsigned int *)(v5 + 24);
          v34 = v108 + 9;
          v113 = *(_QWORD *)(v5 + 64);
          v114 = 1 << (*(_DWORD *)(v5 + 188) - 1);
          v903 = v111;
          v115 = 0;
          v116 = v114 - 1;
          v902 = v117;
          v897 = v116;
          v913 = v25 + v112;
          v910 = v113;
          v904 = 0;
          v894 = v112;
          v848 = v108 + 9;
          if ( v116 < v108 )
            v115 = v108 - v116;
          v906 = v115;
          v118 = 1 << *(_DWORD *)(v5 + 184);
          v26 = v108 - *(_DWORD *)(v5 + 28) <= v118;
          v119 = v108 - v118;
          v120 = 1;
          if ( v26 )
            v119 = *(_DWORD *)(v5 + 28);
          if ( *(_DWORD *)(v5 + 32) )
            v119 = *(_DWORD *)(v5 + 28);
          if ( v119 )
            v120 = v119;
          v121 = 1 << *(_DWORD *)(v5 + 196);
          v909 = v120;
          v949 = 0;
          v840 = (unsigned int *)(v113 + 8LL * (v108 & v116));
          v859 = v840 + 1;
          v908 = *(_QWORD *)(a1 + 176);
          v122 = *(unsigned int **)v908;
          v123 = *(_QWORD *)v908 - *(_QWORD *)(v908 + 8);
          v914 = *(_QWORD *)(v908 + 8);
          v124 = *(_DWORD *)(v908 + 28);
          v125 = v119 - v123;
          v895 = v122;
          LODWORD(v122) = *(_DWORD *)(v908 + 192);
          v126 = *(_DWORD *)(v908 + 188) - 1;
          v900 = v123;
          v875 = v124;
          v870 = v125;
          v899 = (unsigned int)v122;
          LODWORD(v122) = v123 - v124;
          v884 = (1 << v126) - 1;
          v127 = v123;
          v128 = v19 + 3;
          v129 = v127 - v884;
          v893 = v19 + 3;
          v130 = v19;
          if ( v884 >= (unsigned int)v122 )
            v129 = v124;
          v924 = (unsigned int)(v922 - 1);
          v834 = v129;
          v131 = a3;
          v896 = v924;
          v132 = v19;
          v133 = v108 - v112;
          v134 = (unsigned int *)&a3[v132];
          while ( 1 )
          {
            if ( v130 == 3 )
              v135 = *v131 - 1;
            else
              v135 = *v134;
            v136 = v108 - v135;
            v137 = 0;
            if ( v135 - 1 >= v133 )
            {
              v148 = v914 + v136 - (unsigned __int64)v125;
              v149 = v894 - v136;
              v140 = v892;
              if ( v135 - 1 < v826 - v125 - v875 && v149 - 1 >= 3 )
              {
                v150 = ZSTD_readMINMATCH(v892, 4, 0, v148);
                if ( v150 == *v151 )
                {
                  v152 = ZSTD_count_2segments((int)v140 + 4, (int)v151 + 4, v10, (_DWORD)v895, v913);
                  v128 = v893;
                  v140 = v892;
                  v137 = (unsigned int)(v152 + 4);
                }
              }
            }
            else
            {
              v138 = ZSTD_readMINMATCH(v892, 4, 0, -(__int64)v135);
              if ( v138 == *(_DWORD *)(v139 + v140) )
              {
                v141 = (_QWORD *)(v140 + 4);
                v142 = (_QWORD *)(v139 + v140 + 4);
                v143 = v10 - 7;
                v144 = v140 + 4;
                if ( v140 + 4 >= v10 - 7 )
                  goto LABEL_142;
                if ( *v142 != *v141 )
                {
                  v137 = (unsigned int)ZSTD_NbCommonBytes(*v142 ^ *v141, v141, v142, v144) + 4;
                  goto LABEL_156;
                }
                v141 = (_QWORD *)(v140 + 12);
                ++v142;
                if ( v140 + 12 >= v143 )
                {
LABEL_142:
                  if ( (unsigned __int64)v141 < v10 - 3 && *(_DWORD *)v142 == *(_DWORD *)v141 )
                  {
                    v141 = (_QWORD *)((char *)v141 + 4);
                    v142 = (_QWORD *)((char *)v142 + 4);
                  }
                  if ( (unsigned __int64)v141 < v10 - 1 && *(_WORD *)v142 == *(_WORD *)v141 )
                  {
                    v141 = (_QWORD *)((char *)v141 + 2);
                    v142 = (_QWORD *)((char *)v142 + 2);
                  }
                  if ( (unsigned __int64)v141 < v10 && *(_BYTE *)v142 == *(_BYTE *)v141 )
                    LODWORD(v141) = (_DWORD)v141 + 1;
                  v137 = (unsigned int)((_DWORD)v141 - v140);
                }
                else
                {
                  while ( *v142 == *v141 )
                  {
                    ++v141;
                    ++v142;
                    if ( (unsigned __int64)v141 >= v143 )
                      goto LABEL_142;
                  }
                  v145 = ZSTD_NbCommonBytes(*v142 ^ *v141, v141, v142, v144);
                  v137 = (unsigned int)(v146 - v147 + v145 + 4);
                }
              }
            }
LABEL_156:
            if ( (unsigned int)v137 > v896 )
            {
              v153 = &v907[2 * v949];
              *v153 = v130 - v898;
              v896 = (unsigned int)v137;
              v153[1] = v137;
              ++v949;
              if ( (unsigned int)v137 > v901 || v140 + (unsigned int)v137 == v10 )
                goto LABEL_222;
            }
            v125 = v870;
            ++v130;
            v131 = a3;
            ++v134;
            if ( v130 >= v128 )
            {
              v154 = v892;
              *v903 = v826;
              if ( !v121 )
              {
LABEL_192:
                --v121;
LABEL_193:
                v167 = v840;
LABEL_194:
                *v859 = 0;
                *v167 = 0;
                if ( v121 )
                {
                  v168 = ZSTD_hash4Ptr(v154, v899, v137);
                  v169 = 0;
                  v841 = 0;
                  v170 = 0;
                  v171 = *(_DWORD *)(*(_QWORD *)(v908 + 48) + 4 * v168);
                  v172 = *(_QWORD *)(v908 + 64);
                  v910 = v172;
                  while ( 1 )
                  {
                    v903 = (_DWORD *)v170;
                    v894 = v34;
                    v893 = v121 - 1;
                    if ( v171 <= v875 )
                      break;
                    v173 = v169;
                    if ( v170 < v169 )
                      v173 = v170;
                    v174 = v171 + v914;
                    v860 = (unsigned int *)(v172 + 8LL * (v171 & v884));
                    v175 = (char *)v10;
                    if ( (unsigned __int64)v895 + v892 - v174 < v10 )
                      v175 = (char *)v895 + v892 - v174;
                    v176 = ZSTD_count(v173 + v892, v174 + v173, v175);
                    v177 = v176;
                    if ( (unsigned int *)(v176 + v178) == v895 )
                      v177 = ZSTD_count(v176 + v173 + v892, v913, v10) + v176;
                    v170 = v177 + v173;
                    if ( v177 + v173 + v171 >= v900 )
                      v174 = v171 + v911 + v870;
                    if ( v170 <= v896 )
                    {
                      v34 = v848;
                    }
                    else
                    {
                      v34 = v870 + v171 + v170;
                      v179 = v907;
                      v907[2 * v949 + 1] = v170;
                      v179[2 * v949] = v826 - (v870 + v171) + 2;
                      v896 = v170;
                      ++v949;
                      if ( v170 <= v848 - (v870 + v171) )
                        v34 = v894;
                      v848 = v34;
                      if ( v170 > 0x1000 || v170 + v892 == v10 )
                        goto LABEL_221;
                    }
                    if ( v171 > v834 )
                    {
                      v180 = *(_BYTE *)(v174 + v170);
                      v181 = *(_BYTE *)(v170 + v892);
                      if ( v180 >= v181 )
                      {
                        v171 = *v860;
                        v169 = v170;
                        v841 = v170;
                      }
                      else
                      {
                        v171 = v860[1];
                        v169 = v841;
                      }
                      v121 = v893;
                      v104 = v180 < v181;
                      v172 = v910;
                      if ( !v104 )
                        v170 = (unsigned __int64)v903;
                      if ( v893 )
                        continue;
                    }
                    goto LABEL_221;
                  }
                }
                goto LABEL_221;
              }
              v155 = v896;
              while ( 2 )
              {
                --v121;
                if ( v110 < v909 )
                  goto LABEL_193;
                v154 = v892;
                v156 = (unsigned int *)(v910 + 8LL * (v110 & v897));
                v157 = (__int64 *)v904;
                v158 = v10 - 7;
                if ( (unsigned __int64)v902 < v904 )
                  v157 = v902;
                v159 = v911 + v110;
                v160 = (__int64 *)((char *)v157 + v892);
                v137 = (unsigned __int64)v157 + v159;
                if ( (unsigned __int64)v157 + v892 < v158 )
                {
                  if ( *(_QWORD *)v137 != *v160 )
                  {
                    v161 = (unsigned int)ZSTD_NbCommonBytes(*(_QWORD *)v137 ^ *v160, v160, v137, v157);
LABEL_180:
                    v162 = (unsigned __int64)v157 + v161;
                    if ( v162 > v155 )
                    {
                      if ( v162 > v34 - v110 )
                      {
                        v34 = v110 + v162;
                        v848 = v110 + v162;
                      }
                      v163 = &v907[2 * v949];
                      v163[1] = v162;
                      *v163 = v826 - v110 + 2;
                      ++v949;
                      v896 = v162;
                      if ( v162 > 0x1000 || v162 + v892 == v10 )
                      {
                        v121 = 0;
                        goto LABEL_193;
                      }
                      v155 = v162;
                    }
                    if ( *(_BYTE *)(v159 + v162) >= *(_BYTE *)(v162 + v892) )
                    {
                      v904 = v162;
                      *v859 = v110;
                      if ( v110 <= v906 )
                      {
                        v859 = &v894;
                        goto LABEL_193;
                      }
                      v110 = *v156;
                      v859 = v156;
                    }
                    else
                    {
                      v902 = (__int64 *)v162;
                      *v840 = v110;
                      if ( v110 <= v906 )
                      {
                        v167 = &v894;
                        goto LABEL_194;
                      }
                      v110 = v156[1];
                      v840 = v156 + 1;
                    }
                    if ( !v121 )
                      goto LABEL_192;
                    continue;
                  }
                  ++v160;
                  v137 += 8LL;
                  if ( (unsigned __int64)v160 < v158 )
                  {
                    while ( *(_QWORD *)v137 == *v160 )
                    {
                      ++v160;
                      v137 += 8LL;
                      if ( (unsigned __int64)v160 >= v158 )
                        goto LABEL_170;
                    }
                    v164 = ZSTD_NbCommonBytes(*(_QWORD *)v137 ^ *v160, v160, v137, v157);
                    v161 = v165 - v166 + v164;
                    goto LABEL_180;
                  }
                }
                break;
              }
LABEL_170:
              if ( (unsigned __int64)v160 < v10 - 3 && *(_DWORD *)v137 == *(_DWORD *)v160 )
              {
                v160 = (_QWORD *)((char *)v160 + 4);
                v137 += 4LL;
              }
              if ( (unsigned __int64)v160 < v10 - 1 && *(_WORD *)v137 == *(_WORD *)v160 )
              {
                v160 = (_QWORD *)((char *)v160 + 2);
                v137 += 2LL;
              }
              if ( (unsigned __int64)v160 < v10 && *(_BYTE *)v137 == *(_BYTE *)v160 )
                v160 = (_QWORD *)((char *)v160 + 1);
              v161 = (char *)v160 - ((char *)v157 + v892);
              goto LABEL_180;
            }
            v108 = v826;
          }
        }
        v182 = *(_QWORD *)(v5 + 8);
        if ( *(_DWORD *)(v5 + 204) < 0xFFFu )
          v23 = *(_DWORD *)(v5 + 204);
        v911 = *(_QWORD *)(v5 + 8);
        v901 = v23;
        v827 = v14 - v182;
        v183 = ZSTD_hash5Ptr(v14, v22, v21);
        v186 = *(_DWORD *)(v185 + 4 * v183);
        v187 = (_DWORD *)(v185 + 4 * v183);
        v188 = *(unsigned int *)(v5 + 24);
        v34 = v184 + 9;
        v189 = *(_QWORD *)(v5 + 64);
        v190 = *(_DWORD *)(v5 + 188) - 1;
        v903 = v187;
        v191 = 1 << v190;
        v913 = v182 + v188;
        v192 = 0;
        v193 = v191 - 1;
        v902 = v194;
        v897 = v193;
        v910 = v189;
        v904 = 0;
        v894 = v188;
        if ( v193 < v184 )
          v192 = v184 - v193;
        v849 = v184 + 9;
        v906 = v192;
        v195 = 1 << *(_DWORD *)(v5 + 184);
        v26 = v184 - *(_DWORD *)(v5 + 28) <= v195;
        v196 = v184 - v195;
        v197 = 1;
        if ( v26 )
          v196 = *(_DWORD *)(v5 + 28);
        if ( *(_DWORD *)(v5 + 32) )
          v196 = *(_DWORD *)(v5 + 28);
        if ( v196 )
          v197 = v196;
        v198 = 1 << *(_DWORD *)(v5 + 196);
        v909 = v197;
        v949 = 0;
        v842 = (unsigned int *)(v189 + 8LL * (v184 & v193));
        v861 = v842 + 1;
        v908 = *(_QWORD *)(a1 + 176);
        v199 = *(unsigned int **)v908;
        v200 = *(_QWORD *)v908 - *(_QWORD *)(v908 + 8);
        v914 = *(_QWORD *)(v908 + 8);
        v201 = *(_DWORD *)(v908 + 28);
        v202 = v196 - v200;
        v895 = v199;
        LODWORD(v199) = *(_DWORD *)(v908 + 192);
        v203 = *(_DWORD *)(v908 + 188);
        v871 = v202;
        v900 = v200;
        v876 = v201;
        v899 = (unsigned int)v199;
        LODWORD(v199) = v200 - v201;
        v204 = 1 << (v203 - 1);
        v205 = v200;
        --v204;
        v206 = v19 + 3;
        v207 = v205 - v204;
        v885 = v204;
        v104 = v204 < (unsigned int)v199;
        v893 = v19 + 3;
        v208 = v19;
        if ( !v104 )
          v207 = v201;
        v835 = v207;
        v209 = a3;
        v924 = (unsigned int)(v922 - 1);
        v896 = v924;
        v210 = v19;
        v211 = v184 - v188;
        v212 = (unsigned int *)&a3[v210];
        while ( 1 )
        {
          if ( v208 == 3 )
            v213 = *v209 - 1;
          else
            v213 = *v212;
          v214 = v184 - v213;
          v215 = 0;
          if ( v213 - 1 >= v211 )
          {
            v226 = v914 + v214 - (unsigned __int64)v202;
            v227 = v894 - v214;
            v218 = v892;
            if ( v213 - 1 < v827 - v202 - v876 && v227 - 1 >= 3 )
            {
              v228 = ZSTD_readMINMATCH(v892, 4, 0, v226);
              if ( v228 == *v229 )
              {
                v230 = ZSTD_count_2segments((int)v218 + 4, (int)v229 + 4, v10, (_DWORD)v895, v913);
                v206 = v893;
                v218 = v892;
                v215 = (unsigned int)(v230 + 4);
              }
            }
          }
          else
          {
            v216 = ZSTD_readMINMATCH(v892, 4, 0, -(__int64)v213);
            if ( v216 == *(_DWORD *)(v217 + v218) )
            {
              v219 = (_QWORD *)(v218 + 4);
              v220 = (_QWORD *)(v217 + v218 + 4);
              v221 = v10 - 7;
              v222 = v218 + 4;
              if ( v218 + 4 >= v10 - 7 )
                goto LABEL_248;
              if ( *v219 != *v220 )
              {
                v215 = (unsigned int)ZSTD_NbCommonBytes(*v219 ^ *v220, v219, v220, v222) + 4;
                goto LABEL_262;
              }
              v219 = (_QWORD *)(v218 + 12);
              ++v220;
              if ( v218 + 12 >= v221 )
              {
LABEL_248:
                if ( (unsigned __int64)v219 < v10 - 3 && *(_DWORD *)v220 == *(_DWORD *)v219 )
                {
                  v219 = (_QWORD *)((char *)v219 + 4);
                  v220 = (_QWORD *)((char *)v220 + 4);
                }
                if ( (unsigned __int64)v219 < v10 - 1 && *(_WORD *)v220 == *(_WORD *)v219 )
                {
                  v219 = (_QWORD *)((char *)v219 + 2);
                  v220 = (_QWORD *)((char *)v220 + 2);
                }
                if ( (unsigned __int64)v219 < v10 && *(_BYTE *)v220 == *(_BYTE *)v219 )
                  LODWORD(v219) = (_DWORD)v219 + 1;
                v215 = (unsigned int)((_DWORD)v219 - v218);
              }
              else
              {
                while ( *v219 == *v220 )
                {
                  ++v219;
                  ++v220;
                  if ( (unsigned __int64)v219 >= v221 )
                    goto LABEL_248;
                }
                v223 = ZSTD_NbCommonBytes(*v219 ^ *v220, v219, v220, v222);
                v215 = (unsigned int)(v224 - v225 + v223 + 4);
              }
            }
          }
LABEL_262:
          if ( (unsigned int)v215 > v896 )
          {
            v231 = &v907[2 * v949];
            *v231 = v208 - v898;
            v896 = (unsigned int)v215;
            v231[1] = v215;
            ++v949;
            if ( (unsigned int)v215 > v901 || v218 + (unsigned int)v215 == v10 )
              goto LABEL_222;
          }
          v202 = v871;
          ++v208;
          v209 = a3;
          ++v212;
          if ( v208 >= v206 )
          {
            v232 = v892;
            *v903 = v827;
            if ( !v198 )
            {
LABEL_298:
              --v198;
LABEL_299:
              v245 = v842;
LABEL_300:
              *v861 = 0;
              *v245 = 0;
              if ( v198 )
              {
                v246 = ZSTD_hash5Ptr(v232, v899, v215);
                v247 = 0;
                v843 = 0;
                v248 = 0;
                v249 = *(_DWORD *)(*(_QWORD *)(v908 + 48) + 4 * v246);
                v250 = *(_QWORD *)(v908 + 64);
                v910 = v250;
                while ( 1 )
                {
                  v903 = (_DWORD *)v248;
                  v894 = v34;
                  v893 = v198 - 1;
                  if ( v249 <= v876 )
                    break;
                  v251 = v247;
                  if ( v248 < v247 )
                    v251 = v248;
                  v252 = v249 + v914;
                  v253 = (char *)v10;
                  v862 = (unsigned int *)(v250 + 8LL * (v885 & v249));
                  if ( (unsigned __int64)v895 + v892 - v252 < v10 )
                    v253 = (char *)v895 + v892 - v252;
                  v254 = ZSTD_count(v251 + v892, v252 + v251, v253);
                  v255 = v254;
                  if ( (unsigned int *)(v254 + v256) == v895 )
                    v255 = ZSTD_count(v254 + v251 + v892, v913, v10) + v254;
                  v248 = v255 + v251;
                  if ( v255 + v251 + v249 >= v900 )
                    v252 = v911 + v871 + (unsigned __int64)v249;
                  if ( v248 <= v896 )
                  {
                    v34 = v849;
                  }
                  else
                  {
                    v34 = v249 + v871 + v248;
                    v257 = v907;
                    v907[2 * v949 + 1] = v248;
                    v257[2 * v949] = v827 - (v249 + v871) + 2;
                    v896 = v248;
                    ++v949;
                    if ( v248 <= v849 - (v249 + v871) )
                      v34 = v894;
                    v849 = v34;
                    if ( v248 > 0x1000 || v248 + v892 == v10 )
                      goto LABEL_221;
                  }
                  if ( v249 <= v835 )
                    goto LABEL_221;
                  v258 = *(_BYTE *)(v252 + v248);
                  v259 = *(_BYTE *)(v248 + v892);
                  if ( v258 >= v259 )
                  {
                    v249 = *v862;
                    v247 = v248;
                    v843 = v248;
                  }
                  else
                  {
                    v249 = v862[1];
                    v247 = v843;
                  }
                  v198 = v893;
                  v104 = v258 < v259;
                  v250 = v910;
                  if ( !v104 )
                    v248 = (unsigned __int64)v903;
                  if ( !v893 )
                  {
                    v105 = v949;
                    v106 = v34 - 8;
                    goto LABEL_444;
                  }
                }
              }
              goto LABEL_221;
            }
            v233 = v896;
            while ( 2 )
            {
              --v198;
              if ( v186 < v909 )
                goto LABEL_299;
              v232 = v892;
              v234 = (unsigned int *)(v910 + 8LL * (v186 & v897));
              v235 = (__int64 *)v904;
              v236 = v10 - 7;
              if ( (unsigned __int64)v902 < v904 )
                v235 = v902;
              v237 = v911 + v186;
              v238 = (__int64 *)((char *)v235 + v892);
              v215 = (unsigned __int64)v235 + v237;
              if ( (unsigned __int64)v235 + v892 < v236 )
              {
                if ( *v238 != *(_QWORD *)v215 )
                {
                  v239 = (unsigned int)ZSTD_NbCommonBytes(*v238 ^ *(_QWORD *)v215, v238, v215, v235);
LABEL_286:
                  v240 = (unsigned __int64)v235 + v239;
                  if ( v240 > v233 )
                  {
                    if ( v240 > v34 - v186 )
                    {
                      v34 = v240 + v186;
                      v849 = v240 + v186;
                    }
                    v241 = &v907[2 * v949];
                    v241[1] = v240;
                    *v241 = v827 - v186 + 2;
                    ++v949;
                    v896 = v240;
                    if ( v240 > 0x1000 || v240 + v892 == v10 )
                    {
                      v198 = 0;
                      goto LABEL_299;
                    }
                    v233 = v240;
                  }
                  if ( *(_BYTE *)(v237 + v240) >= *(_BYTE *)(v240 + v892) )
                  {
                    v904 = v240;
                    *v861 = v186;
                    if ( v186 <= v906 )
                    {
                      v861 = &v893;
                      goto LABEL_299;
                    }
                    v186 = *v234;
                    v861 = v234;
                  }
                  else
                  {
                    v902 = (__int64 *)v240;
                    *v842 = v186;
                    if ( v186 <= v906 )
                    {
                      v245 = &v893;
                      goto LABEL_300;
                    }
                    v186 = v234[1];
                    v842 = v234 + 1;
                  }
                  if ( !v198 )
                    goto LABEL_298;
                  continue;
                }
                ++v238;
                v215 += 8LL;
                if ( (unsigned __int64)v238 < v236 )
                {
                  while ( *v238 == *(_QWORD *)v215 )
                  {
                    ++v238;
                    v215 += 8LL;
                    if ( (unsigned __int64)v238 >= v236 )
                      goto LABEL_276;
                  }
                  v242 = ZSTD_NbCommonBytes(*v238 ^ *(_QWORD *)v215, v238, v215, v235);
                  v239 = v243 - v244 + v242;
                  goto LABEL_286;
                }
              }
              break;
            }
LABEL_276:
            if ( (unsigned __int64)v238 < v10 - 3 && *(_DWORD *)v215 == *(_DWORD *)v238 )
            {
              v238 = (_QWORD *)((char *)v238 + 4);
              v215 += 4LL;
            }
            if ( (unsigned __int64)v238 < v10 - 1 && *(_WORD *)v215 == *(_WORD *)v238 )
            {
              v238 = (_QWORD *)((char *)v238 + 2);
              v215 += 2LL;
            }
            if ( (unsigned __int64)v238 < v10 && *(_BYTE *)v215 == *(_BYTE *)v238 )
              v238 = (_QWORD *)((char *)v238 + 1);
            v239 = (char *)v238 - ((char *)v235 + v892);
            goto LABEL_286;
          }
          v184 = v827;
        }
      }
      v260 = *(_DWORD *)(v5 + 204);
      v261 = 4095;
      v262 = *(__int64 **)(v5 + 8);
      v902 = v262;
      if ( v260 < 0xFFF )
        v261 = v260;
      v828 = v14 - (_DWORD)v262;
      v263 = ZSTD_hash4Ptr(v14, v22, v21);
      v266 = *(_DWORD *)(v265 + 4 * v263);
      v267 = (_DWORD *)(v265 + 4 * v263);
      v268 = *(unsigned int *)(v5 + 24);
      v269 = v264 + 9;
      v270 = *(_QWORD *)(v5 + 64);
      v271 = *(_DWORD *)(v5 + 188) - 1;
      v903 = v267;
      v910 = v270;
      v915 = v272 + v268;
      v273 = (1 << v271) - 1;
      v904 = 0;
      v909 = v273;
      v914 = 0;
      v274 = 0;
      v894 = v268;
      if ( v273 < v264 )
        v274 = v264 - v273;
      v850 = v264 + 9;
      v906 = v274;
      v275 = 1 << *(_DWORD *)(v5 + 184);
      v276 = v264 - v275;
      v949 = 0;
      v277 = 1;
      if ( v264 - *(_DWORD *)(v5 + 28) <= v275 )
        v276 = *(_DWORD *)(v5 + 28);
      if ( *(_DWORD *)(v5 + 32) )
        v276 = *(_DWORD *)(v5 + 28);
      if ( v276 )
        v277 = v276;
      v278 = 1 << *(_DWORD *)(v5 + 196);
      v872 = v277;
      v844 = (unsigned int *)(v270 + 8LL * (v264 & v273));
      v863 = v844 + 1;
      v908 = *(_QWORD *)(a1 + 176);
      v279 = *(unsigned int **)v908;
      v280 = *(_QWORD *)v908 - *(_QWORD *)(v908 + 8);
      v913 = *(_QWORD *)(v908 + 8);
      v281 = *(_DWORD *)(v908 + 28);
      v895 = v279;
      LODWORD(v279) = *(_DWORD *)(v908 + 192);
      v282 = *(_DWORD *)(v908 + 188);
      v900 = v276 - v280;
      v886 = v280;
      v877 = v281;
      v897 = (unsigned int)v279;
      v283 = (1 << (v282 - 1)) - 1;
      v284 = v280 - v283;
      v899 = v283;
      if ( v283 >= v280 - v281 )
        v284 = v281;
      v924 = (unsigned int)(v922 - 1);
      v896 = v924;
      v285 = v264 - v268;
      v836 = v284;
      v286 = v898;
      v287 = a3;
      v901 = v264 - v268;
      v288 = v898 + 3;
      v893 = v898 + 3;
      v289 = &a3[v898];
      while ( 1 )
      {
        v290 = v286 == 3 ? *v287 - 1 : *v289;
        v291 = v264 - v290;
        v292 = 0;
        if ( v290 - 1 >= v285 )
        {
          if ( v290 - 1 < v828 - v900 - v877 && v894 - v291 - 1 >= 3 )
          {
            v304 = (unsigned int)(*(_DWORD *)(v913 + v291 - (unsigned __int64)v900) << 8);
            LODWORD(v911) = 1;
            v305 = ZSTD_readMINMATCH(v892, 3, v304, 0);
            if ( v305 == v308 )
            {
              v309 = ZSTD_count_2segments(v306 + 3, v307 + 3, v10, (_DWORD)v895, v915);
              v288 = v893;
              v292 = v309 + 3;
            }
          }
        }
        else
        {
          v912 = 1;
          v293 = ZSTD_readMINMATCH(v892, 3, (unsigned int)(*(_DWORD *)(v892 - v290) << 8), 0);
          if ( v293 != v296 )
            goto LABEL_366;
          v297 = (_QWORD *)(v294 + 3);
          v298 = v294 + 3;
          v299 = (_QWORD *)(v295 + v294 + 3);
          v300 = v10 - 7;
          if ( v294 + 3 >= v10 - 7 )
            goto LABEL_1008;
          if ( *v297 != *v299 )
          {
            v292 = ZSTD_NbCommonBytes(*v297 ^ *v299, v297, v299, v298) + 3;
            goto LABEL_366;
          }
          v297 = (_QWORD *)(v294 + 11);
          ++v299;
          if ( v294 + 11 >= v300 )
          {
LABEL_1008:
          {
LABEL_352:
            if ( (unsigned __int64)v297 < v10 - 3 && *(_DWORD *)v299 == *(_DWORD *)v297 )
            {
              v297 = (_QWORD *)((char *)v297 + 4);
              v299 = (_QWORD *)((char *)v299 + 4);
            }
          }
            if ( (unsigned __int64)v297 < v10 - 1 && *(_WORD *)v299 == *(_WORD *)v297 )
            {
              v297 = (_QWORD *)((char *)v297 + 2);
              v299 = (_QWORD *)((char *)v299 + 2);
            }
            if ( (unsigned __int64)v297 < v10 && *(_BYTE *)v299 == *(_BYTE *)v297 )
              LODWORD(v297) = (_DWORD)v297 + 1;
            v292 = (_DWORD)v297 - v294;
          }
          else
          {
            while ( *v297 == *v299 )
            {
              ++v297;
              ++v299;
              if ( (unsigned __int64)v297 >= v300 )
                goto LABEL_352;
            }
            v301 = ZSTD_NbCommonBytes(*v297 ^ *v299, v297, v299, v298);
            v292 = v302 - v303 + v301 + 3;
          }
        }
LABEL_366:
        if ( v292 <= v896 )
        {
          v311 = v892;
        }
        else
        {
          v310 = &v907[2 * v949];
          *v310 = v286 - v898;
          v896 = v292;
          v310[1] = v292;
          v311 = v892;
          ++v949;
          if ( v292 > v261 || v892 + v292 == v10 )
            goto LABEL_222;
        }
        ++v286;
        ++v289;
        if ( v286 >= v288 )
          break;
        v285 = v901;
        v264 = v828;
        v287 = a3;
      }
      v312 = v896;
      if ( v896 >= 3 )
        goto LABEL_377;
      FirstIndexHash3 = ZSTD_insertAndFindFirstIndexHash3(a1, &v928, v311);
      v314 = v872;
      if ( FirstIndexHash3 < v872 || v828 - FirstIndexHash3 >= 0x40000 )
        goto LABEL_378;
      v315 = ZSTD_count(v892, (char *)v902 + FirstIndexHash3, v10);
      if ( v315 < 3 )
      {
LABEL_377:
        v314 = v872;
LABEL_378:
        v319 = v949;
        goto LABEL_379;
      }
      v317 = v907;
      v318 = v316 + 2;
      v896 = v315;
      v319 = 1;
      v312 = v315;
      v949 = 1;
      *v907 = v318;
      v317[1] = v315;
      if ( v315 > v261 || v315 + v892 == v10 )
      {
        v106 = v828 + 1;
        goto LABEL_443;
      }
      v314 = v872;
LABEL_379:
      *v903 = v828;
      if ( v278 )
      {
        while ( 2 )
        {
          --v278;
          if ( v266 < v314 )
            goto LABEL_417;
          v320 = (unsigned int *)(v910 + 8LL * (v266 & v909));
          v321 = v10 - 7;
          v322 = v914;
          if ( v904 < v914 )
            v322 = v904;
          v323 = (char *)v902 + v266;
          v324 = (_QWORD *)(v322 + v892);
          v325 = &v323[v322];
          if ( v322 + v892 < v321 )
          {
            if ( *v324 != *(_QWORD *)v325 )
            {
              v326 = (unsigned int)ZSTD_NbCommonBytes(*v324 ^ *(_QWORD *)v325, v324, v325, v322);
LABEL_400:
              v327 = v326 + v322;
              if ( v327 <= v312 )
              {
                v319 = v949;
              }
              else
              {
                if ( v327 > v269 - v266 )
                {
                  v269 = v327 + v266;
                  v850 = v327 + v266;
                }
                v328 = v907;
                v907[2 * v949 + 1] = v327;
                v328[2 * v949] = v828 - v266 + 2;
                v896 = v327;
                v319 = ++v949;
                v312 = v327;
                if ( v327 > 0x1000 || v327 + v892 == v10 )
                {
                  v278 = 0;
                  goto LABEL_417;
                }
              }
              if ( (unsigned __int8)v323[v327] >= *(_BYTE *)(v327 + v892) )
              {
                v914 = v327;
                *v863 = v266;
                if ( v266 <= v906 )
                {
                  v863 = &v901;
                  goto LABEL_417;
                }
                v266 = *v320;
                v863 = v320;
              }
              else
              {
                v904 = v327;
                *v844 = v266;
                if ( v266 <= v906 )
                {
                  v332 = &v901;
                  goto LABEL_418;
                }
                v266 = v320[1];
                v844 = v320 + 1;
              }
              if ( !v278 )
                goto LABEL_416;
              v314 = v872;
              continue;
            }
            ++v324;
            v325 += 8;
            if ( (unsigned __int64)v324 < v321 )
            {
              while ( *v324 == *(_QWORD *)v325 )
              {
                ++v324;
                v325 += 8;
                if ( (unsigned __int64)v324 >= v321 )
                  goto LABEL_390;
              }
              v329 = ZSTD_NbCommonBytes(*v324 ^ *(_QWORD *)v325, v324, v325, v322);
              v326 = v330 - v331 + v329;
              goto LABEL_400;
            }
          }
          break;
        }
LABEL_390:
        if ( (unsigned __int64)v324 < v10 - 3 && *(_DWORD *)v325 == *(_DWORD *)v324 )
        {
          v324 = (_QWORD *)((char *)v324 + 4);
          v325 += 4;
        }
        if ( (unsigned __int64)v324 < v10 - 1 && *(_WORD *)v325 == *(_WORD *)v324 )
        {
          v324 = (_QWORD *)((char *)v324 + 2);
          v325 += 2;
        }
        if ( (unsigned __int64)v324 < v10 && *v325 == *(_BYTE *)v324 )
          v324 = (_QWORD *)((char *)v324 + 1);
        v326 = (unsigned __int64)v324 - v322 - v892;
        goto LABEL_400;
      }
LABEL_416:
      --v278;
LABEL_417:
      v332 = v844;
LABEL_418:
      *v863 = 0;
      *v332 = 0;
      if ( v278 )
      {
        v333 = ZSTD_hash4Ptr(v892, v897, 0);
        v336 = (unsigned int)v334;
        v845 = v334;
        v337 = *(_DWORD *)(*(_QWORD *)(v908 + 48) + 4 * v333);
        v338 = *(_QWORD *)(v908 + 64);
        v910 = v338;
        while ( 1 )
        {
          v903 = (_DWORD *)v334;
          v894 = v269;
          v893 = v278 - 1;
          if ( v337 <= v877 )
            break;
          v339 = v336;
          if ( v334 < v336 )
            v339 = v334;
          v340 = (char *)(v337 + v913);
          v341 = (char *)v10;
          v864 = (unsigned int *)(v338 + 8LL * (v899 & v337));
          v342 = v339 + v335;
          if ( (unsigned __int64)v895 + v335 - (_QWORD)v340 < v10 )
            v341 = (char *)v895 + v335 - (_QWORD)v340;
          v343 = ZSTD_count(v339 + v335, &v340[v339], v341);
          v344 = v343;
          if ( (unsigned int *)(v343 + v345) == v895 )
            v344 = ZSTD_count(v343 + v342, v915, v10) + v343;
          v334 = v344 + v339;
          v346 = v900;
          if ( v344 + v339 + v337 >= v886 )
            v340 = (char *)v902 + v900 + (unsigned __int64)v337;
          v335 = v892;
          if ( v334 <= v896 )
          {
            v269 = v850;
            v319 = v949;
          }
          else
          {
            v269 = v334 + v337 + v900;
            v347 = v907;
            v907[2 * v949 + 1] = v334;
            v347[2 * v949] = v828 - (v337 + v346) + 2;
            v319 = v949 + 1;
            v896 = v334;
            ++v949;
            if ( v334 <= v850 - (v337 + v346) )
              v269 = v894;
            v850 = v269;
            if ( v334 > 0x1000 || v334 + v892 == v10 )
              break;
          }
          if ( v337 > v836 )
          {
            v348 = v340[v334];
            v349 = *(_BYTE *)(v334 + v892);
            if ( v348 >= v349 )
            {
              v337 = *v864;
              v336 = v334;
              v845 = v334;
            }
            else
            {
              v337 = v864[1];
              v336 = v845;
            }
            v278 = v893;
            v104 = v348 < v349;
            v338 = v910;
            if ( !v104 )
              v334 = (unsigned __int64)v903;
            if ( v893 )
              continue;
          }
          break;
        }
      }
      v106 = v269 - 8;
LABEL_443:
      v105 = v319;
LABEL_444:
      *(_DWORD *)(a1 + 36) = v106;
LABEL_445:
      if ( !v105 )
      {
        v14 = v892;
LABEL_1003:
        v892 = ++v14;
        goto LABEL_1004;
      }
      v350 = v920;
      v351 = v905;
      v352 = v925;
      v353 = v925;
      v920[4] = *a3;
      v350[5] = a3[1];
      v350[6] = a3[2];
      v350[2] = 0;
      v350[3] = v351;
      v354 = ZSTD_literalsContribution(v948, v351, v353, 2);
      v355 = v920;
      v356 = v907;
      *v920 = v354;
      if ( v356[2 * v105 - 1] > v927 )
      {
        *(_QWORD *)((char *)&v931 + 4) = *(_QWORD *)&v356[2 * v105 - 2];
        HIDWORD(v931) = v351;
        goto LABEL_448;
      }
      ZSTD_litLengthPrice(0, v352, 2);
      v376 = v924;
      v377 = v924 + 1;
      v378 = v920 + 7;
      do
      {
        *v378 = 0x40000000;
        v378 += 7;
        --v376;
      }
      while ( v376 );
      v379 = v898;
      v380 = v356;
      v381 = v105;
      v896 = v105;
      v950 = v356;
      do
      {
        v382 = v380[1];
        updated = ZSTD_updateRep(v943, a3, *v380, v379);
        v386 = *(_QWORD *)updated;
        v387 = *(_DWORD *)(updated + 8);
        if ( v377 > v382 )
        {
          v400 = v920;
        }
        else
        {
          v388 = v925;
          do
          {
            _BitScanReverse((unsigned int *)&v389, v385 + 1);
            v390 = v377 - 3;
            if ( *(_DWORD *)(v388 + 80) == 1 )
            {
              _BitScanReverse(&v391, v377 - 2);
              v392 = v384 + ((v377 - 2) << 8 >> v391) + (((_DWORD)v389 + v391 + 16) << 8);
            }
            else
            {
              v393 = *(_DWORD *)(*(_QWORD *)(v388 + 24) + 4 * v389) + 1;
              _BitScanReverse(&v394, v393);
              v395 = *(_DWORD *)(v388 + 76) + (((_DWORD)v389 - v394) << 8) - (v393 << 8 >> v394);
              if ( (unsigned int)v390 <= 0x7F )
              {
                _mm_lfence();
                v397 = *((unsigned __int8 *)&qword_1803EF770[8] + v390);
              }
              else
              {
                _BitScanReverse(&v396, v390);
                v397 = v396 + 36;
              }
              v398 = *(_DWORD *)(*(_QWORD *)(v388 + 16) + 4 * v397) + 1;
              _BitScanReverse(&v399, v398);
              v392 = v395
                   + v384
                   + *(_DWORD *)(v388 + 72)
                   + ((*((_DWORD *)&qword_1803EF640[10] + v397) - v399) << 8)
                   - (v398 << 8 >> v399)
                   + 51;
            }
            v400 = v920;
            v401 = 7LL * v377;
            v402 = v905;
            v920[v401 + 2] = v377++;
            *(_QWORD *)&v400[v401 + 4] = v386;
            v400[v401 + 1] = v385;
            v400[v401 + 3] = v402;
            v400[v401] = v392;
            v400[v401 + 6] = v387;
          }
          while ( v377 <= v382 );
          v380 = v950;
          v381 = v896;
          v379 = v898;
        }
        v380 += 2;
        --v381;
        v950 = v380;
        v896 = v381;
      }
      while ( v381 );
      v10 = v919;
      v403 = v925;
      v404 = v377 - 1;
      v405 = 1;
      v873 = v404;
      v900 = 1;
      if ( !v404 )
      {
LABEL_978:
        v801 = &v400[7 * v404];
        v803 = *(_OWORD *)v801;
        v926 = v801[6];
        v15 = *((_QWORD *)v801 + 2);
        v931 = v803;
        v936 = v926;
        v934 = v803;
        v935 = v15;
        *(double *)&v803 = ZSTD_totalLen(&v934);
        if ( v404 <= v804 )
        {
LABEL_448:
          v357 = 0;
          v358 = 0;
        }
        else
        {
          v939 = *(_DWORD *)(v802 + 24);
          v937 = v803;
          v938 = v15;
          ZSTD_totalLen(&v937);
          v358 = v404 - v805;
          v357 = 0;
        }
        goto LABEL_449;
      }
      while ( 2 )
      {
        v406 = v892 + v405;
        v846 = v406;
        v407 = &v400[7 * v405 - 7];
        if ( v407[2] )
          v408 = 1;
        else
          v408 = v407[3] + 1;
        v409 = *v407 - ZSTD_litLengthPrice(v408 - 1, v403, 2);
        v411 = ZSTD_rawLiteralsCost(v406 - 1, (unsigned int)(v410 - 1), v403) + v409;
        v412 = ZSTD_litLengthPrice(v408, v403, 2);
        v414 = v900;
        v415 = v411 + v412;
        v400 = v920;
        v416 = &v920[7 * v900];
        v417 = *v416;
        if ( v415 <= *v416 )
        {
          v418 = *((_QWORD *)v407 + 2);
          v417 = v415;
          *v416 = v415;
          v419 = v407[6];
          *((_QWORD *)v416 + 2) = v418;
          v416[6] = v419;
          *(_QWORD *)(v416 + 1) = 0;
          v416[3] = v408;
        }
        if ( v406 > v10 - 8 )
          goto LABEL_970;
        if ( v414 == v404 )
          goto LABEL_978;
        v420 = v416[2];
        v898 = v420 != 0;
        if ( v420 )
          v906 = 0;
        else
          v906 = v416[3];
        v421 = ZSTD_litLengthPrice(0, v925, v413);
        v422 = a1;
        v423 = v406;
        v909 = v417 + v421;
        v896 = (unsigned __int64)(v416 + 4);
        v424 = *(unsigned int *)(a1 + 36);
        v425 = *(_QWORD *)(a1 + 8);
        v426 = *(_DWORD *)(a1 + 200);
        if ( v406 < v425 + v424 )
        {
          v414 = v900;
LABEL_969:
          v400 = v920;
LABEL_970:
          v405 = v414 + 1;
          v900 = v405;
          if ( v405 > v404 )
            goto LABEL_978;
          v403 = v925;
          continue;
        }
        break;
      }
      v427 = v406 - v425;
      if ( (unsigned int)v424 < (int)v406 - (int)v425 )
      {
        do
          LODWORD(v424) = ZSTD_insertBt1(a1, (int)v425 + (int)v424, v10, v426, 0) + v424;
        while ( (unsigned int)v424 < v427 );
        v404 = v873;
        v423 = v406;
        v422 = a1;
      }
      v428 = *(_QWORD *)(v422 + 8);
      v429 = 4095;
      v430 = *(_QWORD *)(v422 + 48);
      *(_DWORD *)(v422 + 36) = v427;
      v431 = *(unsigned int *)(v422 + 192);
      if ( v426 == 3 )
      {
        v674 = *(_DWORD *)(v422 + 204);
        v911 = v428;
        if ( v674 < 0xFFF )
          v429 = v674;
        v832 = v423 - v428;
        LODWORD(v915) = v429;
        v675 = ZSTD_hash4Ptr(v423, v431, v430);
        v679 = *(_DWORD *)(v678 + 4 * v675);
        v681 = *(_QWORD *)(v680 + 64);
        v682 = *(_DWORD *)(v680 + 188) - 1;
        v921 = v678 + 4 * v675;
        LODWORD(v680) = 1 << v682;
        v683 = 0;
        v684 = v680 - 1;
        v908 = 0;
        v923 = 0;
        v685 = *(unsigned int *)(a1 + 24);
        v912 = v684;
        v929 = v681;
        v917 = v685;
        v951 = 0;
        v903 = (_DWORD *)(v685 + v428);
        if ( v684 < v676 )
          v683 = v676 - v684;
        v899 = v683;
        v686 = 1 << *(_DWORD *)(a1 + 184);
        v687 = v676 - v686;
        v688 = 1;
        if ( v676 - *(_DWORD *)(a1 + 28) <= v686 )
          v687 = *(_DWORD *)(a1 + 28);
        if ( *(_DWORD *)(a1 + 32) )
          v687 = *(_DWORD *)(a1 + 28);
        v689 = *(_DWORD *)(a1 + 196);
        if ( v687 )
          v688 = v687;
        v856 = v688;
        v895 = (unsigned int *)(v681 + 8LL * (v676 & v684));
        v902 = (__int64 *)(v895 + 1);
        v837 = v676 + 9;
        v881 = 1 << v689;
        v930 = *(_QWORD *)(a1 + 176);
        v690 = *(_QWORD *)v930;
        v691 = *(_QWORD *)v930 - *(_QWORD *)(v930 + 8);
        v910 = *(_QWORD *)(v930 + 8);
        v692 = *(_DWORD *)(v930 + 28);
        v904 = v690;
        LODWORD(v690) = *(_DWORD *)(v930 + 192);
        v693 = *(_DWORD *)(v930 + 188);
        v905 = v687 - v691;
        v893 = v691;
        v897 = v692;
        v916 = v690;
        v894 = (1 << (v693 - 1)) - 1;
        v694 = v691 - v894;
        v868 = v924;
        if ( v894 >= v691 - v692 )
          v694 = v692;
        v901 = v694;
        v695 = (_DWORD *)v896;
        v696 = v676 - v685;
        v697 = v898;
        v918 = v676 - v685;
        v698 = v898 + 3;
        v891 = v898 + 3;
        v699 = (unsigned int *)(v896 + 4LL * v898);
        while ( 1 )
        {
          if ( v697 == 3 )
            v700 = *v695 - 1;
          else
            v700 = *v699;
          v701 = v676 - v700;
          v702 = 0;
          if ( v700 - 1 >= v696 )
          {
            if ( v700 - 1 >= v832 - v905 - v897
              || (unsigned int)v685 - v701 - 1 < 3
              || (v717 = (unsigned int)(*(_DWORD *)(v910 + v701 - (unsigned __int64)v905) << 8),
                  LODWORD(v914) = 1,
                  v718 = ZSTD_readMINMATCH(v846, 3, v717, 0),
                  v718 != v722) )
            {
              v677 = v846;
              goto LABEL_853;
            }
            v723 = v720 + 3;
            v724 = v719 + v721;
            v725 = v10;
            v726 = v720 + 3 - v724 + v904;
            if ( v726 < v10 )
              v725 = v726;
            v727 = ZSTD_count(v723, v724, v725);
            v728 = v727;
            if ( v727 + v729 == v904 )
              v728 = ZSTD_count(v727 + v723, v903, v10) + v727;
            v677 = v846;
            v702 = (unsigned int)(v728 + 3);
            v429 = v915;
            LODWORD(v685) = v917;
          }
          else
          {
            LODWORD(v913) = 1;
            v703 = ZSTD_readMINMATCH(v677, 3, (unsigned int)(*(_DWORD *)(v677 - v700) << 8), 0);
            if ( v703 == v705 )
            {
              v706 = (_QWORD *)(v677 + 3);
              v707 = v677 + 3;
              v708 = (_QWORD *)(v677 + v704 + 3);
              v709 = v10 - 7;
              if ( v677 + 3 < v10 - 7 )
              {
                if ( *v708 != *v706 )
                {
                  v710 = ZSTD_NbCommonBytes(*v708 ^ *v706, v706, v708, v707);
LABEL_851:
                  v702 = (unsigned int)(v710 + 3);
                  goto LABEL_852;
                }
                v706 = (_QWORD *)(v677 + 11);
                ++v708;
                if ( v677 + 11 < v709 )
                {
                  while ( *v708 == *v706 )
                  {
                    ++v706;
                    ++v708;
                    if ( (unsigned __int64)v706 >= v709 )
                      goto LABEL_841;
                  }
                  v714 = ZSTD_NbCommonBytes(*v708 ^ *v706, v706, v708, v707);
                  v710 = v715 - v716 + v714;
                  goto LABEL_851;
                }
              }
LABEL_841:
              if ( (unsigned __int64)v706 < v10 - 3 && *(_DWORD *)v708 == *(_DWORD *)v706 )
              {
                v706 = (_QWORD *)((char *)v706 + 4);
                v708 = (_QWORD *)((char *)v708 + 4);
              }
              if ( (unsigned __int64)v706 < v10 - 1 && *(_WORD *)v708 == *(_WORD *)v706 )
              {
                v706 = (_QWORD *)((char *)v706 + 2);
                v708 = (_QWORD *)((char *)v708 + 2);
              }
              if ( (unsigned __int64)v706 < v10 && *(_BYTE *)v708 == *(_BYTE *)v706 )
                LODWORD(v706) = (_DWORD)v706 + 1;
              v710 = (_DWORD)v706 - v707;
              goto LABEL_851;
            }
          }
LABEL_852:
          v698 = v891;
LABEL_853:
          v711 = v868;
          if ( (unsigned int)v702 > v868 )
          {
            v712 = v951;
            v711 = (unsigned int)v702;
            ++v951;
            v713 = &v907[2 * v712];
            v713[1] = v702;
            *v713 = v697 - v898;
            v868 = (unsigned int)v702;
            if ( (unsigned int)v702 > v429 || v702 + v677 == v10 )
              goto LABEL_941;
          }
          ++v697;
          ++v699;
          if ( v697 >= v698 )
          {
            if ( v711 >= 3 )
            {
              v733 = v846;
              v731 = v832;
LABEL_872:
              v738 = v951;
              goto LABEL_873;
            }
            v730 = ZSTD_insertAndFindFirstIndexHash3(a1, &v928, v677);
            v731 = v832;
            v732 = v856;
            v733 = v846;
            if ( v730 < v856 || v832 - v730 >= 0x40000 )
            {
              v738 = v951;
              goto LABEL_874;
            }
            v734 = ZSTD_count(v846, v911 + v730, v10);
            if ( v734 < 3 )
              goto LABEL_872;
            v736 = v907;
            v737 = v735 + 2;
            v738 = 1;
            v868 = v734;
            v951 = 1;
            *v907 = v737;
            v736[1] = v734;
            if ( v734 > v429 || v734 + v846 == v10 )
            {
              v951 = 1;
              *(_DWORD *)(a1 + 36) = v832 + 1;
              goto LABEL_941;
            }
LABEL_873:
            v732 = v856;
LABEL_874:
            v739 = v881;
            *(_DWORD *)v921 = v731;
            if ( !v881 )
            {
LABEL_912:
              --v739;
LABEL_913:
              v752 = v895;
LABEL_914:
              *(_DWORD *)v902 = 0;
              *v752 = 0;
              if ( v739 )
              {
                v753 = ZSTD_hash4Ptr(v733, v916, v732);
                v755 = v754;
                v756 = v754;
                v757 = *(_DWORD *)(*(_QWORD *)(v930 + 48) + 4 * v753);
                v758 = *(_QWORD *)(v930 + 64);
                v929 = v758;
                while ( 1 )
                {
                  v930 = v756;
                  LODWORD(v915) = v837;
                  v882 = v739 - 1;
                  if ( v757 <= v897 )
                    break;
                  v759 = v755;
                  if ( v756 < v755 )
                    v759 = v756;
                  v760 = v757 + v910;
                  v761 = v759 + v733;
                  v762 = v10;
                  v908 = v758 + 8LL * (v894 & v757);
                  v763 = v761 - (v760 + v759);
                  if ( v763 + v904 < v10 )
                    v762 = v763 + v904;
                  v764 = ZSTD_count(v761, v760 + v759, v762);
                  v765 = v764;
                  if ( v764 + v766 == v904 )
                    v765 = ZSTD_count(v764 + v761, v903, v919) + v764;
                  v756 = v765 + v759;
                  v767 = v905;
                  if ( v765 + v759 + v757 >= v893 )
                    v760 = v911 + v905 + (unsigned __int64)v757;
                  v733 = v846;
                  v10 = v919;
                  if ( v756 <= v868 )
                  {
                    v738 = v951;
                  }
                  else
                  {
                    v768 = v907;
                    v907[2 * v951 + 1] = v756;
                    v768[2 * v951] = v832 - (v757 + v767) + 2;
                    v769 = v757 + v767 + v756;
                    v868 = v756;
                    v738 = ++v951;
                    if ( v756 <= v837 - (v757 + v767) )
                      v769 = v915;
                    v837 = v769;
                    if ( v756 > 0x1000 || v756 + v846 == v10 )
                      break;
                  }
                  if ( v757 > v901 )
                  {
                    v770 = *(_BYTE *)(v760 + v756);
                    v771 = *(_BYTE *)(v756 + v846);
                    if ( v770 >= v771 )
                    {
                      v757 = *(_DWORD *)v908;
                      v755 = v756;
                    }
                    else
                    {
                      v757 = *(_DWORD *)(v908 + 4);
                    }
                    --v739;
                    v104 = v770 < v771;
                    v758 = v929;
                    if ( !v104 )
                      v756 = v930;
                    if ( v882 )
                      continue;
                  }
                  break;
                }
                v404 = v873;
              }
              v951 = v738;
              goto LABEL_940;
            }
            v740 = v837;
            while ( 2 )
            {
              --v739;
              if ( v679 < (unsigned int)v732 )
                goto LABEL_913;
              v741 = (unsigned int *)(v929 + 8LL * (v679 & v912));
              v742 = v10 - 7;
              v743 = v923;
              if ( v908 < v923 )
                v743 = v908;
              v744 = v911 + v679;
              v745 = (_QWORD *)(v743 + v733);
              v732 = v744 + v743;
              if ( v743 + v733 < v742 )
              {
                if ( *(_QWORD *)v732 != *v745 )
                {
                  v746 = (unsigned int)ZSTD_NbCommonBytes(*(_QWORD *)v732 ^ *v745, v745, v732, v743);
LABEL_896:
                  v747 = v746 + v743;
                  if ( v747 <= v868 )
                  {
                    v738 = v951;
                  }
                  else
                  {
                    if ( v747 > v740 - v679 )
                    {
                      v837 = v747 + v679;
                      v740 = v747 + v679;
                    }
                    v748 = v907;
                    v907[2 * v951 + 1] = v747;
                    v748[2 * v951] = v832 - v679 + 2;
                    v738 = v951 + 1;
                    v868 = v747;
                    ++v951;
                    if ( v747 > 0x1000 || v747 + v733 == v10 )
                    {
                      v739 = 0;
                      goto LABEL_913;
                    }
                  }
                  if ( *(_BYTE *)(v744 + v747) >= *(_BYTE *)(v747 + v733) )
                  {
                    v923 = v747;
                    *(_DWORD *)v902 = v679;
                    if ( v679 <= v899 )
                    {
                      v902 = (__int64 *)&v918;
                      goto LABEL_913;
                    }
                    v679 = *v741;
                    v902 = (__int64 *)v741;
                  }
                  else
                  {
                    v908 = v747;
                    *v895 = v679;
                    if ( v679 <= v899 )
                    {
                      v752 = &v918;
                      goto LABEL_914;
                    }
                    v679 = v741[1];
                    v895 = v741 + 1;
                  }
                  if ( !v739 )
                    goto LABEL_912;
                  v732 = v856;
                  continue;
                }
                ++v745;
                v732 += 8LL;
                if ( (unsigned __int64)v745 < v742 )
                {
                  while ( *(_QWORD *)v732 == *v745 )
                  {
                    ++v745;
                    v732 += 8LL;
                    if ( (unsigned __int64)v745 >= v742 )
                      goto LABEL_886;
                  }
                  v749 = ZSTD_NbCommonBytes(*(_QWORD *)v732 ^ *v745, v745, v732, v743);
                  v746 = v750 - v751 + v749;
                  goto LABEL_896;
                }
              }
              break;
            }
LABEL_886:
            if ( (unsigned __int64)v745 < v10 - 3 && *(_DWORD *)v732 == *(_DWORD *)v745 )
            {
              v745 = (_QWORD *)((char *)v745 + 4);
              v732 += 4LL;
            }
            if ( (unsigned __int64)v745 < v10 - 1 && *(_WORD *)v732 == *(_WORD *)v745 )
            {
              v745 = (_QWORD *)((char *)v745 + 2);
              v732 += 2LL;
            }
            if ( (unsigned __int64)v745 < v10 && *(_BYTE *)v732 == *(_BYTE *)v745 )
              v745 = (_QWORD *)((char *)v745 + 1);
            v746 = (unsigned __int64)v745 - v743 - v733;
            goto LABEL_896;
          }
          v696 = v918;
          v676 = v832;
          v695 = (_DWORD *)v896;
        }
      }
      if ( v426 == 5 )
      {
        v593 = *(_DWORD *)(v422 + 204);
        v911 = v428;
        if ( v593 < 0xFFF )
          v429 = v593;
        v831 = v423 - v428;
        v917 = v429;
        v594 = ZSTD_hash5Ptr(v423, v431, v430);
        v598 = *(_DWORD *)(v597 + 4 * v594);
        v600 = *(_DWORD **)(v599 + 64);
        v601 = *(_DWORD *)(v599 + 188) - 1;
        v921 = v597 + 4 * v594;
        LODWORD(v599) = 1 << v601;
        v602 = 0;
        v603 = v599 - 1;
        v908 = 0;
        v923 = 0;
        v604 = *(unsigned int *)(a1 + 24);
        v894 = v603;
        v903 = v600;
        v918 = v604;
        v951 = 0;
        v913 = v604 + v428;
        if ( v603 < v595 )
          v602 = v595 - v603;
        v880 = v602;
        v605 = 1 << *(_DWORD *)(a1 + 184);
        v606 = v595 - v605;
        v607 = 1;
        if ( v595 - *(_DWORD *)(a1 + 28) <= v605 )
          v606 = *(_DWORD *)(a1 + 28);
        if ( *(_DWORD *)(a1 + 32) )
          v606 = *(_DWORD *)(a1 + 28);
        v608 = *(_DWORD *)(a1 + 196);
        if ( v606 )
          v607 = v606;
        v916 = v607;
        v895 = &v600[2 * (v595 & v603)];
        v902 = (__int64 *)(v895 + 1);
        v837 = v595 + 9;
        v854 = 1 << v608;
        v910 = *(_QWORD *)(a1 + 176);
        v609 = *(_QWORD *)v910;
        v610 = *(_QWORD *)v910 - *(_QWORD *)(v910 + 8);
        v914 = *(_QWORD *)(v910 + 8);
        v611 = *(_DWORD *)(v910 + 28);
        v904 = v609;
        LODWORD(v609) = *(_DWORD *)(v910 + 192);
        v612 = *(_DWORD *)(v910 + 188);
        v890 = v606 - v610;
        v897 = v610;
        v905 = v611;
        v893 = v609;
        v901 = (1 << (v612 - 1)) - 1;
        v613 = v610 - v901;
        v867 = v924;
        if ( v901 >= v610 - v611 )
          v613 = v611;
        v899 = v613;
        v614 = (_DWORD *)v896;
        v615 = v595 - v604;
        v616 = v898;
        v912 = v595 - v604;
        v617 = v898 + 3;
        LODWORD(v915) = v898 + 3;
        v618 = (unsigned int *)(v896 + 4LL * v898);
        while ( 1 )
        {
          if ( v616 == 3 )
            v619 = *v614 - 1;
          else
            v619 = *v618;
          v620 = v595 - v619;
          v621 = 0;
          if ( v619 - 1 >= v615 )
          {
            if ( v619 - 1 < v831 - v890 - v905 && (unsigned int)(v604 - v620 - 1) >= 3 )
            {
              v631 = ZSTD_readMINMATCH(v846, 4, 0, v620);
              if ( v631 == *v634 )
              {
                v635 = v633 + 4;
                v636 = (char *)v634 + v632;
                v637 = v10;
                v638 = v633 + 4 - (_QWORD)v636 + v904;
                if ( v638 < v10 )
                  v637 = v638;
                v639 = ZSTD_count(v635, v636, v637);
                v640 = v639;
                if ( v639 + v641 == v904 )
                  v640 = ZSTD_count(v639 + v635, v913, v10) + v639;
                v617 = v915;
                v621 = (unsigned int)(v640 + 4);
                v429 = v917;
                LODWORD(v604) = v918;
              }
            }
            v596 = v846;
          }
          else
          {
            v622 = ZSTD_readMINMATCH(v596, 4, 0, -(__int64)v619);
            if ( v622 == *(_DWORD *)(v623 + v596) )
            {
              v624 = (_QWORD *)(v596 + 4);
              v625 = (_QWORD *)(v596 + v623 + 4);
              v626 = v10 - 7;
              v627 = v596 + 4;
              if ( v596 + 4 >= v10 - 7 )
                goto LABEL_733;
              if ( *v625 != *v624 )
              {
                v621 = (unsigned int)ZSTD_NbCommonBytes(*v625 ^ *v624, v624, v625, v627) + 4;
                goto LABEL_752;
              }
              v624 = (_QWORD *)(v596 + 12);
              ++v625;
              if ( v596 + 12 >= v626 )
              {
LABEL_733:
                if ( (unsigned __int64)v624 < v10 - 3 && *(_DWORD *)v625 == *(_DWORD *)v624 )
                {
                  v624 = (_QWORD *)((char *)v624 + 4);
                  v625 = (_QWORD *)((char *)v625 + 4);
                }
                if ( (unsigned __int64)v624 < v10 - 1 && *(_WORD *)v625 == *(_WORD *)v624 )
                {
                  v624 = (_QWORD *)((char *)v624 + 2);
                  v625 = (_QWORD *)((char *)v625 + 2);
                }
                if ( (unsigned __int64)v624 < v10 && *(_BYTE *)v625 == *(_BYTE *)v624 )
                  LODWORD(v624) = (_DWORD)v624 + 1;
                v621 = (unsigned int)((_DWORD)v624 - v596);
              }
              else
              {
                while ( *v625 == *v624 )
                {
                  ++v624;
                  ++v625;
                  if ( (unsigned __int64)v624 >= v626 )
                    goto LABEL_733;
                }
                v628 = ZSTD_NbCommonBytes(*v625 ^ *v624, v624, v625, v627);
                v621 = (unsigned int)(v629 - v630 + v628 + 4);
              }
            }
          }
LABEL_752:
          if ( (unsigned int)v621 > v867 )
          {
            v642 = &v907[2 * v951];
            *v642 = v616 - v898;
            v642[1] = v621;
            v867 = (unsigned int)v621;
            ++v951;
            if ( (unsigned int)v621 > v429 || v596 + v621 == v10 )
              goto LABEL_941;
          }
          v615 = v912;
          ++v616;
          v614 = (_DWORD *)v896;
          ++v618;
          if ( v616 >= v617 )
          {
            v643 = v854;
            *(_DWORD *)v921 = v831;
            if ( !v854 )
            {
LABEL_789:
              --v643;
LABEL_790:
              v658 = v895;
LABEL_791:
              *(_DWORD *)v902 = 0;
              *v658 = 0;
              if ( !v643 )
                goto LABEL_940;
              v659 = ZSTD_hash5Ptr(v596, v893, v621);
              v660 = 0;
              v661 = 0;
              v662 = *(_DWORD *)(*(_QWORD *)(v910 + 48) + 4 * v659);
              v663 = *(_DWORD **)(v910 + 64);
              v903 = v663;
              while ( 1 )
              {
                v921 = v661;
                LODWORD(v915) = v837;
                v855 = v643 - 1;
                if ( v662 <= v905 )
                  goto LABEL_598;
                v664 = v660;
                if ( v661 < v660 )
                  v664 = v661;
                v665 = v662 + v914;
                v666 = v10;
                v908 = (unsigned __int64)&v663[2 * (v901 & v662)];
                if ( v846 - v665 + v904 < v10 )
                  v666 = v846 - v665 + v904;
                v667 = ZSTD_count(v664 + v846, v665 + v664, v666);
                v668 = v667;
                if ( v667 + v669 == v904 )
                  v668 = ZSTD_count(v667 + v664 + v846, v913, v919) + v667;
                v661 = v668 + v664;
                if ( v668 + v664 + v662 >= v897 )
                  v665 = v911 + v890 + (unsigned __int64)v662;
                v10 = v919;
                if ( v661 > v867 )
                {
                  v670 = v907;
                  v907[2 * v951 + 1] = v661;
                  v670[2 * v951] = v831 - (v662 + v890) + 2;
                  v671 = v661 + v662 + v890;
                  v867 = v661;
                  ++v951;
                  if ( v661 <= v837 - (v662 + v890) )
                    v671 = v915;
                  v837 = v671;
                  if ( v661 > 0x1000 || v661 + v846 == v10 )
                    goto LABEL_598;
                }
                if ( v662 <= v899 )
                  goto LABEL_598;
                v672 = *(_BYTE *)(v665 + v661);
                v673 = *(_BYTE *)(v661 + v846);
                if ( v672 >= v673 )
                {
                  v662 = *(_DWORD *)v908;
                  v660 = v661;
                }
                else
                {
                  v662 = *(_DWORD *)(v908 + 4);
                }
                --v643;
                v104 = v672 < v673;
                v663 = v903;
                if ( !v104 )
                  v661 = v921;
                if ( !v855 )
                {
                  v404 = v873;
                  goto LABEL_940;
                }
              }
            }
            v644 = v837;
            v645 = v867;
            while ( 2 )
            {
              --v643;
              if ( v598 < v916 )
                goto LABEL_790;
              v646 = &v903[2 * (v598 & v894)];
              v647 = v10 - 7;
              v648 = v923;
              if ( v908 < v923 )
                v648 = v908;
              v649 = v911 + v598;
              v650 = (_QWORD *)(v648 + v596);
              v621 = v649 + v648;
              v651 = (char *)v650;
              if ( (unsigned __int64)v650 < v647 )
              {
                if ( *(_QWORD *)v621 != *v650 )
                {
                  v652 = (unsigned int)ZSTD_NbCommonBytes(*(_QWORD *)v621 ^ *v650, v650, v621, v648);
LABEL_776:
                  v653 = v652 + v648;
                  if ( v653 <= v645 )
                  {
                    v596 = v846;
                  }
                  else
                  {
                    if ( v653 > v644 - v598 )
                    {
                      v837 = v653 + v598;
                      v644 = v653 + v598;
                    }
                    v596 = v846;
                    v654 = &v907[2 * v951];
                    v654[1] = v653;
                    *v654 = v831 - v598 + 2;
                    ++v951;
                    v867 = v653;
                    if ( v653 > 0x1000 || v653 + v846 == v10 )
                    {
                      v643 = 0;
                      goto LABEL_790;
                    }
                    v645 = v653;
                  }
                  if ( *(_BYTE *)(v649 + v653) >= *(_BYTE *)(v653 + v596) )
                  {
                    v923 = v653;
                    *(_DWORD *)v902 = v598;
                    if ( v598 <= v880 )
                    {
                      v902 = (__int64 *)&v917;
                      goto LABEL_790;
                    }
                    v598 = *v646;
                    v902 = (__int64 *)v646;
                  }
                  else
                  {
                    v908 = v653;
                    *v895 = v598;
                    if ( v598 <= v880 )
                    {
                      v658 = &v917;
                      goto LABEL_791;
                    }
                    v598 = v646[1];
                    v895 = v646 + 1;
                  }
                  if ( !v643 )
                    goto LABEL_789;
                  continue;
                }
                ++v650;
                v621 += 8LL;
                if ( (unsigned __int64)v650 < v647 )
                {
                  while ( *(_QWORD *)v621 == *v650 )
                  {
                    ++v650;
                    v621 += 8LL;
                    if ( (unsigned __int64)v650 >= v647 )
                      goto LABEL_766;
                  }
                  v655 = ZSTD_NbCommonBytes(*(_QWORD *)v621 ^ *v650, v650, v621, v648);
                  v652 = v656 - v657 + v655;
                  goto LABEL_776;
                }
              }
              break;
            }
LABEL_766:
            if ( (unsigned __int64)v650 < v10 - 3 && *(_DWORD *)v621 == *(_DWORD *)v650 )
            {
              v650 = (_QWORD *)((char *)v650 + 4);
              v621 += 4LL;
            }
            if ( (unsigned __int64)v650 < v10 - 1 && *(_WORD *)v621 == *(_WORD *)v650 )
            {
              v650 = (_QWORD *)((char *)v650 + 2);
              v621 += 2LL;
            }
            if ( (unsigned __int64)v650 < v10 && *(_BYTE *)v621 == *(_BYTE *)v650 )
              v650 = (_QWORD *)((char *)v650 + 1);
            v652 = (char *)v650 - v651;
            goto LABEL_776;
          }
          v595 = v831;
        }
      }
      v432 = *(_DWORD *)(v422 + 204);
      if ( (unsigned int)(v426 - 6) > 1 )
      {
        v911 = v428;
        if ( v432 < 0xFFF )
          v429 = v432;
        v830 = v423 - v428;
        v917 = v429;
        v513 = ZSTD_hash4Ptr(v423, v431, v430);
        v517 = *(_DWORD *)(v516 + 4 * v513);
        v519 = *(_DWORD **)(v518 + 64);
        v520 = *(_DWORD *)(v518 + 188) - 1;
        v921 = v516 + 4 * v513;
        LODWORD(v518) = 1 << v520;
        v521 = 0;
        v522 = v518 - 1;
        v908 = 0;
        v923 = 0;
        v523 = *(unsigned int *)(a1 + 24);
        v894 = v522;
        v903 = v519;
        v918 = v523;
        v951 = 0;
        v913 = v523 + v428;
        if ( v522 < v514 )
          v521 = v514 - v522;
        v879 = v521;
        v524 = 1 << *(_DWORD *)(a1 + 184);
        v525 = v514 - v524;
        v526 = 1;
        if ( v514 - *(_DWORD *)(a1 + 28) <= v524 )
          v525 = *(_DWORD *)(a1 + 28);
        if ( *(_DWORD *)(a1 + 32) )
          v525 = *(_DWORD *)(a1 + 28);
        v527 = *(_DWORD *)(a1 + 196);
        if ( v525 )
          v526 = v525;
        v916 = v526;
        v895 = &v519[2 * (v514 & v522)];
        v902 = (__int64 *)(v895 + 1);
        v837 = v514 + 9;
        v852 = 1 << v527;
        v910 = *(_QWORD *)(a1 + 176);
        v528 = *(_QWORD *)v910;
        v529 = *(_QWORD *)v910 - *(_QWORD *)(v910 + 8);
        v914 = *(_QWORD *)(v910 + 8);
        v530 = *(_DWORD *)(v910 + 28);
        v889 = v525 - v529;
        v904 = v528;
        LODWORD(v528) = *(_DWORD *)(v910 + 192);
        v531 = *(_DWORD *)(v910 + 188) - 1;
        v897 = v529;
        v905 = v530;
        v893 = v528;
        v901 = (1 << v531) - 1;
        v532 = v529 - v901;
        v866 = v924;
        if ( v901 >= v529 - v530 )
          v532 = v530;
        v899 = v532;
        v533 = (_DWORD *)v896;
        v534 = v514 - v523;
        v535 = v898;
        v912 = v514 - v523;
        v536 = v898 + 3;
        LODWORD(v915) = v898 + 3;
        v537 = (unsigned int *)(v896 + 4LL * v898);
        while ( 1 )
        {
          if ( v535 == 3 )
            v538 = *v533 - 1;
          else
            v538 = *v537;
          v539 = v514 - v538;
          v540 = 0;
          if ( v538 - 1 >= v534 )
          {
            if ( v538 - 1 < v830 - v889 - v905 && (unsigned int)(v523 - v539 - 1) >= 3 )
            {
              v550 = ZSTD_readMINMATCH(v846, 4, 0, v539);
              if ( v550 == *v553 )
              {
                v554 = v552 + 4;
                v555 = (char *)v553 + v551;
                v104 = v552 + 4 + v904 - (unsigned __int64)v555 < v10;
                v556 = v10;
                v557 = v552 + 4;
                if ( v104 )
                  v556 = v554 + v904 - (_QWORD)v555;
                v558 = ZSTD_count(v557, v555, v556);
                v559 = v558;
                if ( v558 + v560 == v904 )
                  v559 = ZSTD_count(v558 + v554, v913, v10) + v558;
                v536 = v915;
                v540 = (unsigned int)(v559 + 4);
                v429 = v917;
                LODWORD(v523) = v918;
              }
            }
            v515 = v846;
          }
          else
          {
            v541 = ZSTD_readMINMATCH(v515, 4, 0, -(__int64)v538);
            if ( v541 == *(_DWORD *)(v542 + v515) )
            {
              v543 = (_QWORD *)(v515 + 4);
              v544 = (_QWORD *)(v515 + v542 + 4);
              v545 = v10 - 7;
              v546 = v515 + 4;
              if ( v515 + 4 >= v10 - 7 )
                goto LABEL_624;
              if ( *v544 != *v543 )
              {
                v540 = (unsigned int)ZSTD_NbCommonBytes(*v544 ^ *v543, v543, v544, v546) + 4;
                goto LABEL_643;
              }
              v543 = (_QWORD *)(v515 + 12);
              ++v544;
              if ( v515 + 12 >= v545 )
              {
LABEL_624:
                if ( (unsigned __int64)v543 < v10 - 3 && *(_DWORD *)v544 == *(_DWORD *)v543 )
                {
                  v543 = (_QWORD *)((char *)v543 + 4);
                  v544 = (_QWORD *)((char *)v544 + 4);
                }
                if ( (unsigned __int64)v543 < v10 - 1 && *(_WORD *)v544 == *(_WORD *)v543 )
                {
                  v543 = (_QWORD *)((char *)v543 + 2);
                  v544 = (_QWORD *)((char *)v544 + 2);
                }
                if ( (unsigned __int64)v543 < v10 && *(_BYTE *)v544 == *(_BYTE *)v543 )
                  LODWORD(v543) = (_DWORD)v543 + 1;
                v540 = (unsigned int)((_DWORD)v543 - v515);
              }
              else
              {
                while ( *v544 == *v543 )
                {
                  ++v543;
                  ++v544;
                  if ( (unsigned __int64)v543 >= v545 )
                    goto LABEL_624;
                }
                v547 = ZSTD_NbCommonBytes(*v544 ^ *v543, v543, v544, v546);
                v540 = (unsigned int)(v548 - v549 + v547 + 4);
              }
            }
          }
LABEL_643:
          if ( (unsigned int)v540 > v866 )
          {
            v561 = &v907[2 * v951];
            *v561 = v535 - v898;
            v561[1] = v540;
            v866 = (unsigned int)v540;
            ++v951;
            if ( (unsigned int)v540 > v429 || v540 + v515 == v10 )
              goto LABEL_941;
          }
          v534 = v912;
          ++v535;
          v533 = (_DWORD *)v896;
          ++v537;
          if ( v535 >= v536 )
          {
            v562 = v852;
            *(_DWORD *)v921 = v830;
            if ( v852 )
            {
              v563 = v837;
              v564 = v866;
              do
              {
                --v562;
                if ( v517 < v916 )
                  goto LABEL_681;
                v565 = &v903[2 * (v517 & v894)];
                v566 = v10 - 7;
                v567 = v923;
                if ( v908 < v923 )
                  v567 = v908;
                v568 = v911 + v517;
                v569 = (_QWORD *)(v567 + v515);
                v540 = v568 + v567;
                v570 = (char *)v569;
                if ( (unsigned __int64)v569 >= v566 )
                  goto LABEL_657;
                if ( *(_QWORD *)v540 != *v569 )
                {
                  v571 = (unsigned int)ZSTD_NbCommonBytes(*(_QWORD *)v540 ^ *v569, v569, v540, v567);
                  goto LABEL_667;
                }
                ++v569;
                v540 += 8LL;
                if ( (unsigned __int64)v569 >= v566 )
                {
LABEL_657:
                  if ( (unsigned __int64)v569 < v10 - 3 && *(_DWORD *)v540 == *(_DWORD *)v569 )
                  {
                    v569 = (_QWORD *)((char *)v569 + 4);
                    v540 += 4LL;
                  }
                  if ( (unsigned __int64)v569 < v10 - 1 && *(_WORD *)v540 == *(_WORD *)v569 )
                  {
                    v569 = (_QWORD *)((char *)v569 + 2);
                    v540 += 2LL;
                  }
                  if ( (unsigned __int64)v569 < v10 && *(_BYTE *)v540 == *(_BYTE *)v569 )
                    v569 = (_QWORD *)((char *)v569 + 1);
                  v571 = (char *)v569 - v570;
                }
                else
                {
                  while ( *(_QWORD *)v540 == *v569 )
                  {
                    ++v569;
                    v540 += 8LL;
                    if ( (unsigned __int64)v569 >= v566 )
                      goto LABEL_657;
                  }
                  v574 = ZSTD_NbCommonBytes(*(_QWORD *)v540 ^ *v569, v569, v540, v567);
                  v571 = v575 - v576 + v574;
                }
LABEL_667:
                v572 = v571 + v567;
                if ( v572 <= v564 )
                {
                  v515 = v846;
                }
                else
                {
                  if ( v572 > v563 - v517 )
                  {
                    v837 = v572 + v517;
                    v563 = v572 + v517;
                  }
                  v515 = v846;
                  v573 = &v907[2 * v951];
                  v573[1] = v572;
                  *v573 = v830 - v517 + 2;
                  ++v951;
                  v866 = v572;
                  if ( v572 > 0x1000 || v572 + v846 == v10 )
                  {
                    v562 = 0;
                    goto LABEL_681;
                  }
                  v564 = v572;
                }
                if ( *(_BYTE *)(v568 + v572) >= *(_BYTE *)(v572 + v515) )
                {
                  v923 = v572;
                  *(_DWORD *)v902 = v517;
                  if ( v517 <= v879 )
                  {
                    v902 = &v915;
                    goto LABEL_681;
                  }
                  v517 = *v565;
                  v902 = (__int64 *)v565;
                }
                else
                {
                  v908 = v572;
                  *v895 = v517;
                  if ( v517 <= v879 )
                  {
                    v577 = &v915;
                    goto LABEL_682;
                  }
                  v517 = v565[1];
                  v895 = v565 + 1;
                }
              }
              while ( v562 );
            }
            --v562;
LABEL_681:
            v577 = (__int64 *)v895;
LABEL_682:
            *(_DWORD *)v902 = 0;
            *(_DWORD *)v577 = 0;
            if ( !v562 )
              goto LABEL_940;
            v578 = ZSTD_hash4Ptr(v515, v893, v540);
            v579 = 0;
            v580 = 0;
            v581 = *(_DWORD *)(*(_QWORD *)(v910 + 48) + 4 * v578);
            v582 = *(_DWORD **)(v910 + 64);
            v903 = v582;
            while ( 1 )
            {
              v921 = v580;
              LODWORD(v915) = v837;
              v853 = v562 - 1;
              if ( v581 <= v905 )
                break;
              v583 = v579;
              if ( v580 < v579 )
                v583 = v580;
              v584 = v581 + v914;
              v908 = (unsigned __int64)&v582[2 * (v901 & v581)];
              v585 = v10;
              if ( v846 + v904 - v584 < v10 )
                v585 = v846 + v904 - v584;
              v586 = ZSTD_count(v583 + v846, v584 + v583, v585);
              v587 = v586;
              if ( v586 + v588 == v904 )
                v587 = ZSTD_count(v586 + v583 + v846, v913, v919) + v586;
              v580 = v583 + v587;
              if ( v583 + v587 + v581 >= v897 )
                v584 = v911 + v889 + (unsigned __int64)v581;
              v10 = v919;
              if ( v580 > v866 )
              {
                v589 = v907;
                v907[2 * v951 + 1] = v580;
                v589[2 * v951] = v830 - (v581 + v889) + 2;
                v590 = v581 + v889 + v580;
                v866 = v580;
                ++v951;
                if ( v580 <= v837 - (v581 + v889) )
                  v590 = v915;
                v837 = v590;
                if ( v580 > 0x1000 || v580 + v846 == v10 )
                  break;
              }
              if ( v581 <= v899 )
                break;
              v591 = *(_BYTE *)(v584 + v580);
              v592 = *(_BYTE *)(v580 + v846);
              if ( v591 >= v592 )
              {
                v581 = *(_DWORD *)v908;
                v579 = v580;
              }
              else
              {
                v581 = *(_DWORD *)(v908 + 4);
              }
              --v562;
              v104 = v591 < v592;
              v582 = v903;
              if ( !v104 )
                v580 = v921;
              if ( !v853 )
              {
                v404 = v873;
                goto LABEL_940;
              }
            }
LABEL_598:
            v404 = v873;
            goto LABEL_940;
          }
          v514 = v830;
        }
      }
      v908 = v428;
      if ( v432 < 0xFFF )
        v429 = v432;
      v829 = v423 - v428;
      v893 = v429;
      v433 = ZSTD_hash6Ptr(v423, v431, v430);
      v437 = *(_DWORD *)(v436 + 4 * v433);
      v439 = *(_QWORD *)(v438 + 64);
      v440 = *(_DWORD *)(v438 + 188) - 1;
      v903 = (_DWORD *)(v436 + 4 * v433);
      LODWORD(v438) = 1 << v440;
      v441 = 0;
      v442 = v438 - 1;
      v914 = 0;
      v913 = 0;
      v443 = *(unsigned int *)(a1 + 24);
      v916 = v442;
      v910 = v439;
      v901 = v443;
      v951 = 0;
      v923 = v443 + v428;
      if ( v442 < v434 )
        v441 = v434 - v442;
      v878 = v441;
      v444 = 1 << *(_DWORD *)(a1 + 184);
      v445 = v434 - v444;
      v446 = 1;
      if ( v434 - *(_DWORD *)(a1 + 28) <= v444 )
        v445 = *(_DWORD *)(a1 + 28);
      if ( *(_DWORD *)(a1 + 32) )
        v445 = *(_DWORD *)(a1 + 28);
      v447 = *(_DWORD *)(a1 + 196);
      if ( v445 )
        v446 = v445;
      v899 = v446;
      v895 = (unsigned int *)(v439 + 8LL * (v434 & v442));
      v902 = (__int64 *)(v895 + 1);
      v837 = v434 + 9;
      v887 = 1 << v447;
      v921 = *(_QWORD *)(a1 + 176);
      v448 = *(_QWORD *)v921;
      v449 = *(_QWORD *)v921 - *(_QWORD *)(v921 + 8);
      v911 = *(_QWORD *)(v921 + 8);
      v450 = *(_DWORD *)(v921 + 28);
      v851 = v445 - v449;
      v904 = v448;
      LODWORD(v448) = *(_DWORD *)(v921 + 192);
      v451 = *(_DWORD *)(v921 + 188) - 1;
      v917 = v449;
      v905 = v450;
      v912 = v448;
      v918 = (1 << v451) - 1;
      v452 = v449 - v918;
      v865 = v924;
      if ( v918 >= v449 - v450 )
        v452 = v450;
      LODWORD(v915) = v452;
      v453 = (_DWORD *)v896;
      v454 = v434 - v443;
      v455 = v898;
      v897 = v434 - v443;
      v456 = v898 + 3;
      v894 = v898 + 3;
      v457 = (unsigned int *)(v896 + 4LL * v898);
      while ( 2 )
      {
        if ( v455 == 3 )
          v458 = *v453 - 1;
        else
          v458 = *v457;
        v459 = v434 - v458;
        v460 = 0;
        if ( v458 - 1 >= v454 )
        {
          if ( v458 - 1 < v829 - v851 - v905 && (unsigned int)(v443 - v459 - 1) >= 3 )
          {
            v470 = ZSTD_readMINMATCH(v846, 4, 0, v459);
            if ( v470 == *v473 )
            {
              v474 = v472 + 4;
              v475 = (char *)v473 + v471;
              v476 = v10;
              v477 = v472 + 4 - (_QWORD)v475 + v904;
              if ( v477 < v10 )
                v476 = v477;
              v478 = ZSTD_count(v474, v475, v476);
              v479 = v478;
              if ( v478 + v480 == v904 )
                v479 = ZSTD_count(v478 + v474, v923, v10) + v478;
              v456 = v894;
              v460 = (unsigned int)(v479 + 4);
              v429 = v893;
              LODWORD(v443) = v901;
            }
          }
          v435 = v846;
        }
        else
        {
          v461 = ZSTD_readMINMATCH(v435, 4, 0, -(__int64)v458);
          if ( v461 == *(_DWORD *)(v462 + v435) )
          {
            v463 = (_QWORD *)(v435 + 4);
            v464 = (_QWORD *)(v435 + v462 + 4);
            v465 = v10 - 7;
            v466 = v435 + 4;
            if ( v435 + 4 >= v10 - 7 )
              goto LABEL_515;
            if ( *v464 != *v463 )
            {
              v460 = (unsigned int)ZSTD_NbCommonBytes(*v464 ^ *v463, v463, v464, v466) + 4;
              goto LABEL_534;
            }
            v463 = (_QWORD *)(v435 + 12);
            ++v464;
            if ( v435 + 12 >= v465 )
            {
LABEL_515:
              if ( (unsigned __int64)v463 < v10 - 3 && *(_DWORD *)v464 == *(_DWORD *)v463 )
              {
                v463 = (_QWORD *)((char *)v463 + 4);
                v464 = (_QWORD *)((char *)v464 + 4);
              }
              if ( (unsigned __int64)v463 < v10 - 1 && *(_WORD *)v464 == *(_WORD *)v463 )
              {
                v463 = (_QWORD *)((char *)v463 + 2);
                v464 = (_QWORD *)((char *)v464 + 2);
              }
              if ( (unsigned __int64)v463 < v10 && *(_BYTE *)v464 == *(_BYTE *)v463 )
                LODWORD(v463) = (_DWORD)v463 + 1;
              v460 = (unsigned int)((_DWORD)v463 - v435);
            }
            else
            {
              while ( *v464 == *v463 )
              {
                ++v463;
                ++v464;
                if ( (unsigned __int64)v463 >= v465 )
                  goto LABEL_515;
              }
              v467 = ZSTD_NbCommonBytes(*v464 ^ *v463, v463, v464, v466);
              v460 = (unsigned int)(v468 - v469 + v467 + 4);
            }
          }
        }
LABEL_534:
        if ( (unsigned int)v460 > v865 )
        {
          v481 = &v907[2 * v951];
          *v481 = v455 - v898;
          v481[1] = v460;
          v865 = (unsigned int)v460;
          ++v951;
          if ( (unsigned int)v460 > v429 || v460 + v435 == v10 )
            goto LABEL_941;
        }
        v454 = v897;
        ++v455;
        v453 = (_DWORD *)v896;
        ++v457;
        if ( v455 < v456 )
        {
          v434 = v829;
          continue;
        }
        break;
      }
      v482 = v887;
      *v903 = v829;
      if ( v887 )
      {
        v483 = v837;
        v484 = v865;
        do
        {
          --v482;
          if ( v437 < v899 )
            goto LABEL_572;
          v485 = (unsigned int *)(v910 + 8LL * (v437 & v916));
          v486 = v10 - 7;
          v487 = v913;
          if ( v914 < v913 )
            v487 = v914;
          v488 = v908 + v437;
          v489 = (_QWORD *)(v487 + v435);
          v460 = v488 + v487;
          v490 = (char *)v489;
          if ( (unsigned __int64)v489 >= v486 )
            goto LABEL_548;
          if ( *(_QWORD *)v460 != *v489 )
          {
            v491 = (unsigned int)ZSTD_NbCommonBytes(*(_QWORD *)v460 ^ *v489, v489, v460, v487);
            goto LABEL_558;
          }
          ++v489;
          v460 += 8LL;
          if ( (unsigned __int64)v489 >= v486 )
          {
LABEL_548:
            if ( (unsigned __int64)v489 < v10 - 3 && *(_DWORD *)v460 == *(_DWORD *)v489 )
            {
              v489 = (_QWORD *)((char *)v489 + 4);
              v460 += 4LL;
            }
            if ( (unsigned __int64)v489 < v10 - 1 && *(_WORD *)v460 == *(_WORD *)v489 )
            {
              v489 = (_QWORD *)((char *)v489 + 2);
              v460 += 2LL;
            }
            if ( (unsigned __int64)v489 < v10 && *(_BYTE *)v460 == *(_BYTE *)v489 )
              v489 = (_QWORD *)((char *)v489 + 1);
            v491 = (char *)v489 - v490;
          }
          else
          {
            while ( *(_QWORD *)v460 == *v489 )
            {
              ++v489;
              v460 += 8LL;
              if ( (unsigned __int64)v489 >= v486 )
                goto LABEL_548;
            }
            v494 = ZSTD_NbCommonBytes(*(_QWORD *)v460 ^ *v489, v489, v460, v487);
            v491 = v495 - v496 + v494;
          }
LABEL_558:
          v492 = v491 + v487;
          if ( v492 <= v484 )
          {
            v435 = v846;
          }
          else
          {
            if ( v492 > v483 - v437 )
            {
              v837 = v437 + v492;
              v483 = v437 + v492;
            }
            v435 = v846;
            v493 = &v907[2 * v951];
            v493[1] = v492;
            *v493 = v829 - v437 + 2;
            ++v951;
            v865 = v492;
            if ( v492 > 0x1000 || v492 + v846 == v10 )
            {
              v482 = 0;
              goto LABEL_572;
            }
            v484 = v492;
          }
          if ( *(_BYTE *)(v488 + v492) >= *(_BYTE *)(v492 + v435) )
          {
            v913 = v492;
            *(_DWORD *)v902 = v437;
            if ( v437 <= v878 )
            {
              v902 = (__int64 *)&v916;
              goto LABEL_572;
            }
            v437 = *v485;
            v902 = (__int64 *)v485;
          }
          else
          {
            v914 = v492;
            *v895 = v437;
            if ( v437 <= v878 )
            {
              v497 = &v916;
              goto LABEL_573;
            }
            v437 = v485[1];
            v895 = v485 + 1;
          }
        }
        while ( v482 );
      }
      --v482;
LABEL_572:
      v497 = v895;
LABEL_573:
      *(_DWORD *)v902 = 0;
      *v497 = 0;
      if ( v482 )
      {
        v498 = ZSTD_hash6Ptr(v435, v912, v460);
        v499 = 0;
        v500 = 0;
        v501 = *(_DWORD *)(*(_QWORD *)(v921 + 48) + 4 * v498);
        v502 = *(_DWORD **)(v921 + 64);
        v903 = v502;
        do
        {
          v921 = v500;
          v912 = v837;
          v888 = v482 - 1;
          if ( v501 <= v905 )
            break;
          v503 = v499;
          if ( v500 < v499 )
            v503 = v500;
          v504 = v501 + v911;
          v895 = &v502[2 * (v918 & v501)];
          v505 = v10;
          if ( v846 + v904 - v504 < v10 )
            v505 = v846 + v904 - v504;
          v506 = ZSTD_count(v503 + v846, v504 + v503, v505);
          v507 = v506;
          if ( v506 + v508 == v904 )
            v507 = ZSTD_count(v506 + v503 + v846, v923, v919) + v506;
          v500 = v507 + v503;
          if ( v507 + v503 + v501 >= v917 )
            v504 = v908 + v851 + (unsigned __int64)v501;
          v10 = v919;
          if ( v500 > v865 )
          {
            v509 = v907;
            v907[2 * v951 + 1] = v500;
            v509[2 * v951] = v829 - (v501 + v851) + 2;
            v510 = v500 + v501 + v851;
            v865 = v500;
            ++v951;
            if ( v500 <= v837 - (v501 + v851) )
              v510 = v912;
            v837 = v510;
            if ( v500 > 0x1000 || v500 + v846 == v10 )
              break;
          }
          if ( v501 <= (unsigned int)v915 )
            break;
          v511 = *(_BYTE *)(v504 + v500);
          v512 = *(_BYTE *)(v500 + v846);
          if ( v511 >= v512 )
          {
            v501 = *v895;
            v499 = v500;
          }
          else
          {
            v501 = v895[1];
          }
          --v482;
          v104 = v511 < v512;
          v502 = v903;
          if ( !v104 )
            v500 = v921;
        }
        while ( v888 );
        goto LABEL_598;
      }
LABEL_940:
      *(_DWORD *)(a1 + 36) = v837 - 8;
LABEL_941:
      v414 = v900;
      if ( !v951 )
        goto LABEL_969;
      v772 = v907;
      v773 = v907[2 * v951 - 1];
      if ( v773 <= v927 && v773 + v900 < 0x1000 )
      {
        v774 = 0;
        v897 = 0;
        v775 = v907;
        v903 = v907;
        while ( 1 )
        {
          v776 = *v775;
          v777 = ZSTD_updateRep(v944, v896, *v775, v898);
          v779 = v778[1];
          v780 = *(_QWORD *)v777;
          LODWORD(v915) = *(_DWORD *)(v777 + 8);
          v781 = v774 ? v772[2 * v774 - 1] + 1 : v922;
          if ( v779 >= v781 )
            break;
          v400 = v920;
LABEL_966:
          ++v774;
          v775 = v778 + 2;
          v897 = v774;
          v903 = v775;
          if ( v774 >= v951 )
          {
            v10 = v919;
            goto LABEL_970;
          }
        }
        v782 = v915;
        v783 = v925;
        v784 = v779 + v414;
        while ( 2 )
        {
          _BitScanReverse((unsigned int *)&v785, v776 + 1);
          v13 = *(_DWORD *)(v783 + 80) == 1;
          v786 = v784 - v414 - 3;
          LODWORD(v904) = 0;
          if ( v13 )
          {
            LODWORD(v902) = 0;
            _BitScanReverse(&v787, v786 + 1);
            v788 = ((unsigned int)(((_DWORD)v786 + 1) << 8) >> v787) + v909 + (((_DWORD)v785 + v787 + 16) << 8);
          }
          else
          {
            v789 = *(_QWORD *)(v783 + 24);
            LODWORD(v895) = 0;
            v790 = *(_DWORD *)(v789 + 4 * v785) + 1;
            _BitScanReverse((unsigned int *)&v789, v790);
            v791 = *(_DWORD *)(v783 + 76) + (((_DWORD)v785 - (_DWORD)v789) << 8) - (v790 << 8 >> v789);
            if ( (unsigned int)v786 <= 0x7F )
            {
              _mm_lfence();
              v793 = *((unsigned __int8 *)&qword_1803EF770[8] + v786);
            }
            else
            {
              _BitScanReverse(&v792, v786);
              v793 = v792 + 36;
            }
            v794 = 4 * v793;
            v795 = *(_DWORD *)(*(_QWORD *)(v783 + 16) + 4 * v793) + 1;
            _BitScanReverse(&v796, v795);
            v788 = v791
                 + v909
                 + *(_DWORD *)(v783 + 72)
                 + ((*(_DWORD *)((char *)&qword_1803EF640[10] + v794) - v796) << 8)
                 - (v795 << 8 >> v796)
                 + 51;
          }
          v400 = v920;
          if ( v784 <= v404 )
          {
            if ( v788 < v920[7 * v784] )
            {
              if ( v404 < v784 )
                goto LABEL_960;
LABEL_962:
              v797 = 7LL * v784;
              v798 = v906;
              *(_QWORD *)&v400[v797 + 4] = v780;
              v400[v797 + 6] = v782;
              v400[v797 + 2] = v784 - v414;
              v400[v797 + 1] = v776;
              v400[v797 + 3] = v798;
              v400[v797] = v788;
            }
            if ( --v784 - v414 < v781 )
            {
              v774 = v897;
              v778 = v903;
              v414 = v900;
              v772 = v907;
              goto LABEL_966;
            }
            continue;
          }
          break;
        }
        do
LABEL_960:
          v400[7 * ++v404] = 0x40000000;
        while ( v404 < v784 );
        v873 = v404;
        goto LABEL_962;
      }
      v357 = 0;
      v355 = v920;
      DWORD1(v931) = v907[2 * v951 - 2];
      v799 = 7LL * v900;
      *((_QWORD *)&v931 + 1) = __PAIR64__(v906, v773);
      if ( v920[v799 + 2] )
        v800 = 0;
      else
        v800 = v920[v799 + 3];
      v358 = 0;
      if ( v900 - v800 <= 0x1000 )
        v358 = v900 - v800;
LABEL_449:
      v359 = v358 + 1;
      v360 = v358 + 1;
      v361 = 7LL * (v358 + 1);
      v362 = v926;
      *(_OWORD *)&v355[v361] = v931;
      *(_QWORD *)&v355[v361 + 4] = v15;
      v355[v361 + 6] = v362;
      while ( v358 )
      {
        v363 = &v355[7 * v358];
        v364 = *(_OWORD *)v363;
        v942 = v363[6];
        v365 = *((_QWORD *)v363 + 2);
        v940 = v364;
        v941 = v365;
        *(double *)&v364 = ZSTD_totalLen(&v940);
        v366 = 7LL * --v360;
        *(_OWORD *)&v355[v366] = v364;
        *(_QWORD *)&v355[v366 + 4] = *(_QWORD *)(v367 + 16);
        v355[v366 + 6] = *(_DWORD *)(v367 + 24);
        v368 = v358;
        v358 -= v369;
        if ( v368 <= v369 )
          v358 = v357;
      }
      if ( v360 <= v359 )
      {
        v370 = v948;
        while ( 1 )
        {
          v371 = 7LL * v360;
          v372 = v355[v371 + 2];
          v373 = (unsigned int)v355[v371 + 3];
          v374 = v355[v371 + 1];
          v375 = v372 + v373;
          if ( v372 )
            break;
          v892 = v370 + v373;
LABEL_1000:
          ++v360;
          v357 = 0;
          if ( v360 > v359 )
            goto LABEL_1001;
        }
        if ( v374 >= 3 )
        {
          a3[2] = a3[1];
          a3[1] = *a3;
          *a3 = v374 - 2;
          goto LABEL_988;
        }
        v806 = v357;
        LOBYTE(v806) = (_DWORD)v373 == 0;
        v807 = v374 + v806;
        if ( (_DWORD)v807 )
        {
          if ( (_DWORD)v807 == 3 )
          {
            v808 = *a3 - 1;
            goto LABEL_986;
          }
          v808 = a3[v807];
          if ( (unsigned int)v807 >= 2 )
LABEL_986:
            a3[2] = a3[1];
          a3[1] = *a3;
          *a3 = v808;
        }
LABEL_988:
        ZSTD_updateStats(v925, v373, v948, v374, v372);
        v809 = v372 - 3;
        v811 = v810;
        v812 = *(_QWORD *)(a2 + 24);
        if ( v810 + v948 <= v10 - 32 )
        {
          ZSTD_copy16(v812);
          if ( v811 > 0x10 )
          {
            ZSTD_copy16(*(_QWORD *)(v814 + 24) + 16LL);
            v816 = ZSTD_copy16(v815 + 16);
            v818 = v817 + 16;
            if ( v818 < v816 )
            {
              do
              {
                ZSTD_copy16(v818);
                v820 = ZSTD_copy16(v819 + 16);
                v818 = v821 + 16;
              }
              while ( v818 < v820 );
            }
LABEL_994:
            v813 = v948;
          }
          *(_QWORD *)(v814 + 24) += v811;
          v822 = *(_QWORD *)(v814 + 8);
          if ( v811 > 0xFFFF )
          {
            *(_DWORD *)(v814 + 72) = 1;
            *(_DWORD *)(v814 + 76) = (v822 - *(_QWORD *)v814) >> 3;
          }
          *(_WORD *)(v822 + 4) = v811;
          **(_DWORD **)(v814 + 8) = v374 + 1;
          v823 = *(_QWORD *)(v814 + 8);
          if ( v809 > 0xFFFF )
          {
            *(_DWORD *)(v814 + 72) = 2;
            *(_DWORD *)(v814 + 76) = (v823 - *(_QWORD *)v814) >> 3;
          }
          v355 = v920;
          *(_WORD *)(v823 + 6) = v809;
          *(_QWORD *)(v814 + 8) += 8LL;
          v948 = v375 + v813;
          v370 = v948;
          v892 = v948;
          goto LABEL_1000;
        }
        ZSTD_safecopyLiterals(v812);
        v814 = a2;
        goto LABEL_994;
      }
LABEL_1001:
      ZSTD_setBasePrices(v925, 2);
      v14 = v892;
LABEL_1004:
      v5 = a1;
      v8 = v948;
    }
    while ( v14 < v10 - 8 );
  }
  return v10 - v8;
}

```

## disassembly

```asm
0x1802da140  mov     [rsp-8+arg_18], r9
0x1802da145  mov     [rsp-8+arg_10], r8
0x1802da14a  mov     [rsp-8+arg_8], rdx
0x1802da14f  mov     [rsp-8+arg_0], rcx
0x1802da154  push    rbp
0x1802da155  push    rbx
0x1802da156  push    rsi
0x1802da157  push    rdi
0x1802da158  push    r12
0x1802da15a  push    r14
0x1802da15c  lea     rbp, [rsp-128h]
0x1802da164  sub     rsp, 228h
0x1802da16b  mov     r8, [rbp+150h+arg_20]
0x1802da172  mov     r12, rcx
0x1802da175  add     rcx, 48h ; 'H'
0x1802da179  mov     edx, 0FFFh
0x1802da17e  mov     rdi, r9
0x1802da181  mov     [rbp+150h+var_110], rcx
0x1802da185  mov     eax, [r12+0CCh]
0x1802da18d  lea     r14, [r9+r8]
0x1802da191  mov     ebx, [r12+18h]
0x1802da196  lea     rsi, [r14-8]
0x1802da19a  add     rbx, [r12+8]
0x1802da19f  mov     r9d, 2
0x1802da1a5  cmp     eax, edx
0x1802da1a7  mov     [rbp+150h+var_140], r14
0x1802da1ab  cmovb   edx, eax
0x1802da1ae  xor     eax, eax
0x1802da1b0  cmp     dword ptr [r12+0C8h], 3
0x1802da1b9  mov     [rbp+150h+var_104], edx
0x1802da1bc  mov     rdx, rdi
0x1802da1bf  setnz   al
0x1802da1c2  add     eax, 3
0x1802da1c5  mov     [rbp+150h+var_128], eax
0x1802da1c8  mov     eax, [r12+24h]
0x1802da1cd  mov     [rbp+150h+var_100], eax
0x1802da1d0  mov     rax, [rcx+28h]
0x1802da1d4  mov     [rbp+150h+var_138], rax
0x1802da1d8  mov     rax, [rcx+20h]
0x1802da1dc  mov     [rbp+150h+var_198], rax
0x1802da1e0  call    ZSTD_rescaleFreqs
0x1802da1e5  xor     r9d, r9d
0x1802da1e8  cmp     rdi, rbx
0x1802da1eb  mov     r11d, r9d
0x1802da1ee  setz    r11b
0x1802da1f2  add     r11, rdi
0x1802da1f5  mov     [rsp+250h+var_1F0], r11
0x1802da1fa  cmp     r11, rsi
0x1802da1fd  jnb     loc_1802DE8C2
0x1802da203  mov     eax, [rbp+150h+var_D0]
0x1802da209  movsd   xmm2, [rbp+150h+var_D8]
0x1802da20e  mov     [rsp+250h+var_30], r13
0x1802da216  mov     [rsp+250h+var_38], r15
0x1802da21e  mov     [rbp+150h+var_108], eax
0x1802da221  mov     ebx, [r12+24h]
0x1802da226  mov     eax, r11d
0x1802da229  mov     r15, [r12+8]
0x1802da22e  sub     eax, edi
0x1802da230  mov     esi, [r12+0C8h]
0x1802da238  mov     r13d, r9d
0x1802da23b  setz    r13b
0x1802da23f  mov     [rbp+150h+var_1A0], eax
0x1802da242  mov     [rbp+150h+var_1CC], r13d
0x1802da246  lea     rax, [r15+rbx]
0x1802da24a  cmp     r11, rax
0x1802da24d  jb      loc_1802DE889
0x1802da253  mov     edi, r11d
0x1802da256  sub     edi, r15d
0x1802da259  cmp     ebx, edi
0x1802da25b  jnb     short loc_1802DA28A
0x1802da25d  xor     r13d, r13d
0x1802da260  mov     edx, ebx
0x1802da262  mov     r9d, esi
0x1802da265  add     rdx, r15
0x1802da268  mov     dword ptr [rsp+250h+var_230], r13d
0x1802da26d  mov     r8, r14
0x1802da270  mov     rcx, r12
0x1802da273  call    ZSTD_insertBt1
0x1802da278  add     ebx, eax
0x1802da27a  cmp     ebx, edi
0x1802da27c  jb      short loc_1802DA260
0x1802da27e  mov     r13d, [rbp+150h+var_1CC]
0x1802da282  xor     r9d, r9d
0x1802da285  mov     r11, [rsp+250h+var_1F0]
0x1802da28a  mov     r8, [r12+30h]
0x1802da28f  mov     [r12+24h], edi
0x1802da294  mov     edx, [r12+0C0h]
0x1802da29c  cmp     esi, 3
0x1802da29f  jz      loc_1802DB86E
0x1802da2a5  mov     ecx, 0FFFh
0x1802da2aa  mov     r10d, r11d
0x1802da2ad  cmp     esi, 5
0x1802da2b0  jz      loc_1802DB137
0x1802da2b6  lea     eax, [rsi-6]
0x1802da2b9  mov     rsi, [r12+8]
0x1802da2be  cmp     eax, 1
0x1802da2c1  mov     [rbp+150h+var_178], rsi
0x1802da2c5  mov     eax, [r12+0CCh]
0x1802da2cd  ja      loc_1802DA9FF
0x1802da2d3  cmp     eax, ecx
0x1802da2d5  cmovb   ecx, eax
0x1802da2d8  sub     r10d, esi
0x1802da2db  mov     [rbp+150h+var_1C8], ecx
0x1802da2de  mov     rcx, r11
0x1802da2e1  mov     [rsp+250h+var_220], r10d
0x1802da2e6  call    ZSTD_hash6Ptr
0x1802da2eb  mov     ebx, [r8+rax*4]
0x1802da2ef  lea     rax, [r8+rax*4]
0x1802da2f3  mov     r8d, [r12+18h]
0x1802da2f8  lea     r15d, [r10+9]
0x1802da2fc  mov     ecx, [r12+0BCh]
0x1802da304  mov     r11d, 1
0x1802da30a  mov     rdi, [r12+40h]
0x1802da30f  dec     ecx
0x1802da311  shl     r11d, cl
0x1802da314  mov     edx, 1
0x1802da319  mov     [rbp+150h+var_1B0], rax
0x1802da31d  xor     ecx, ecx
0x1802da31f  dec     r11d
0x1802da322  mov     [rbp+150h+var_1B8], r9
0x1802da326  lea     rax, [rsi+r8]
0x1802da32a  mov     [rbp+150h+var_1C4], r11d
0x1802da32e  mov     [rbp+150h+var_168], rax
0x1802da332  mov     r9d, r10d
0x1802da335  mov     eax, r10d
0x1802da338  mov     [rbp+150h+var_180], rdi
0x1802da33c  sub     eax, r11d
0x1802da33f  mov     [rbp+150h+var_1A8], 0
0x1802da347  cmp     r11d, r10d
0x1802da34a  mov     [rbp+150h+var_188], r8d
0x1802da34e  mov     [rsp+250h+var_210], r15d
0x1802da353  cmovb   ecx, eax
0x1802da356  mov     eax, r10d
0x1802da359  mov     [rbp+150h+var_19C], ecx
0x1802da35c  mov     ecx, [r12+0B8h]
0x1802da364  shl     edx, cl
0x1802da366  mov     ecx, [r12+1Ch]
0x1802da36b  sub     r9d, edx
0x1802da36e  sub     eax, ecx
0x1802da370  cmp     eax, edx
0x1802da372  mov     edx, r9d
0x1802da375  mov     eax, 1
0x1802da37a  cmovbe  edx, ecx
0x1802da37d  cmp     dword ptr [r12+20h], 0
0x1802da383  cmovnz  edx, ecx
0x1802da386  mov     ecx, [r12+0C4h]
0x1802da38e  test    edx, edx
0x1802da390  mov     r12d, 1
0x1802da396  cmovnz  eax, edx
0x1802da399  shl     r12d, cl
0x1802da39c  mov     [rsp+250h+var_1F8], eax
0x1802da3a0  xor     esi, esi
0x1802da3a2  mov     eax, r11d
0x1802da3a5  mov     dword ptr [rbp+150h+arg_20], esi
0x1802da3ab  and     eax, r10d
0x1802da3ae  add     eax, eax
0x1802da3b0  lea     rax, [rdi+rax*4]
0x1802da3b4  mov     edi, 1
0x1802da3b9  mov     [rsp+250h+var_218], rax
0x1802da3be  add     rax, 4
0x1802da3c2  mov     [rsp+250h+var_208], rax
0x1802da3c7  mov     rax, [rbp+150h+arg_0]
0x1802da3ce  mov     rcx, [rax+0B0h]
0x1802da3d5  mov     [rbp+150h+var_190], rcx
0x1802da3d9  mov     rax, [rcx]
0x1802da3dc  mov     r9, [rcx+8]
0x1802da3e0  mov     r11d, eax
0x1802da3e3  sub     r11d, r9d
0x1802da3e6  mov     [rbp+150h+var_160], r9
0x1802da3ea  mov     r9d, [rcx+1Ch]
0x1802da3ee  sub     edx, r11d
0x1802da3f1  mov     [rsp+250h+var_1E0], rax
0x1802da3f6  mov     eax, [rcx+0C0h]
0x1802da3fc  mov     ecx, [rcx+0BCh]
0x1802da402  dec     ecx
0x1802da404  mov     [rsp+250h+var_1E8], r11d
0x1802da409  shl     edi, cl
0x1802da40b  mov     [rsp+250h+var_1FC], r9d
0x1802da410  mov     [rsp+250h+var_200], edx
0x1802da414  mov     [rsp+250h+var_21C], eax
0x1802da418  dec     edi
0x1802da41a  mov     eax, r11d
0x1802da41d  sub     eax, r9d
0x1802da420  mov     [rbp+150h+var_1C0], edi
0x1802da423  mov     ecx, r11d
0x1802da426  lea     r11d, [r13+3]
0x1802da42a  sub     ecx, edi
0x1802da42c  mov     [rbp+150h+var_1D0], r11d
0x1802da430  cmp     edi, eax
0x1802da432  mov     eax, [rbp+150h+var_128]
0x1802da435  dec     eax
0x1802da437  mov     edi, r13d
0x1802da43a  cmovnb  ecx, r9d
0x1802da43e  mov     [rbp+150h+var_118], rax
0x1802da442  mov     [rsp+250h+var_1E4], ecx
0x1802da446  mov     rcx, [rbp+150h+arg_10]
0x1802da44d  mov     [rsp+250h+var_1D8], rax
0x1802da452  mov     eax, r13d
0x1802da455  mov     r13d, r10d
0x1802da458  sub     r13d, r8d
0x1802da45b  lea     rsi, [rcx+rax*4]
0x1802da45f  jmp     short loc_1802DA466
0x1802da461  mov     r10d, [rsp+250h+var_220]
0x1802da466  cmp     edi, 3
0x1802da469  jnz     short loc_1802DA471
0x1802da46b  mov     eax, [rcx]
0x1802da46d  dec     eax
0x1802da46f  jmp     short loc_1802DA473
0x1802da471  mov     eax, [rsi]
0x1802da473  sub     r10d, eax
0x1802da476  lea     ecx, [rax-1]
0x1802da479  xor     r8d, r8d
0x1802da47c  cmp     ecx, r13d
0x1802da47f  jnb     loc_1802DA55E
0x1802da485  mov     r10, [rsp+250h+var_1F0]
0x1802da48a  lea     edx, [r8+4]
0x1802da48e  mov     r9d, eax
0x1802da491  mov     rcx, r10
0x1802da494  neg     r9
0x1802da497  call    ZSTD_readMINMATCH
0x1802da49c  cmp     eax, [r9+r10]
0x1802da4a0  jnz     loc_1802DA5D1
0x1802da4a6  lea     rdx, [r10+4]
0x1802da4aa  lea     r8, [r10+4]
0x1802da4ae  add     r8, r9
0x1802da4b1  lea     rax, [r14-7]
0x1802da4b5  mov     r9, rdx
0x1802da4b8  cmp     rdx, rax
0x1802da4bb  jnb     short loc_1802DA4F7
0x1802da4bd  mov     rcx, [rdx]
0x1802da4c0  xor     rcx, [r8]
0x1802da4c3  jz      short loc_1802DA4D5
0x1802da4c5  call    ZSTD_NbCommonBytes
0x1802da4ca  mov     ecx, eax
0x1802da4cc  lea     r8d, [rcx+4]
0x1802da4d0  jmp     loc_1802DA5D1
0x1802da4d5  add     rdx, 8
0x1802da4d9  add     r8, 8
0x1802da4dd  cmp     rdx, rax
0x1802da4e0  jnb     short loc_1802DA4F7
0x1802da4e2  mov     rcx, [rdx]
0x1802da4e5  xor     rcx, [r8]
0x1802da4e8  jnz     short loc_1802DA548
0x1802da4ea  add     rdx, 8
0x1802da4ee  add     r8, 8
0x1802da4f2  cmp     rdx, rax
0x1802da4f5  jb      short loc_1802DA4E2
0x1802da4f7  lea     rax, [r14-3]
0x1802da4fb  cmp     rdx, rax
0x1802da4fe  jnb     short loc_1802DA50F
0x1802da500  mov     eax, [rdx]
0x1802da502  cmp     [r8], eax
0x1802da505  jnz     short loc_1802DA50F
0x1802da507  add     rdx, 4
0x1802da50b  add     r8, 4
0x1802da50f  lea     rax, [r14-1]
0x1802da513  cmp     rdx, rax
0x1802da516  jnb     short loc_1802DA529
0x1802da518  movzx   eax, word ptr [rdx]
0x1802da51b  cmp     [r8], ax
0x1802da51f  jnz     short loc_1802DA529
0x1802da521  add     rdx, 2
0x1802da525  add     r8, 2
0x1802da529  cmp     rdx, r14
0x1802da52c  jnb     short loc_1802DA539
0x1802da52e  movzx   eax, byte ptr [rdx]
0x1802da531  cmp     [r8], al
0x1802da534  jnz     short loc_1802DA539
0x1802da536  inc     rdx
0x1802da539  mov     rcx, rdx
0x1802da53c  sub     rcx, r9
0x1802da53f  lea     r8d, [rcx+4]
0x1802da543  jmp     loc_1802DA5D1
0x1802da548  call    ZSTD_NbCommonBytes
0x1802da54d  mov     ecx, eax
0x1802da54f  sub     rdx, r9
0x1802da552  add     rcx, rdx
0x1802da555  lea     r8d, [rcx+4]
0x1802da559  jmp     loc_1802DA5D1
0x1802da55e  mov     eax, edx
0x1802da560  mov     r9d, r10d
0x1802da563  sub     r9, rax
0x1802da566  mov     eax, [rsp+250h+var_220]
0x1802da56a  add     r9, [rbp+150h+var_160]
0x1802da56e  sub     eax, edx
0x1802da570  sub     eax, [rsp+250h+var_1FC]
0x1802da574  xor     edx, edx
0x1802da576  cmp     ecx, eax
0x1802da578  mov     ecx, [rbp+150h+var_188]
0x1802da57b  setb    dl
0x1802da57e  sub     ecx, r10d
0x1802da581  mov     r10, [rsp+250h+var_1F0]
0x1802da586  xor     eax, eax
0x1802da588  dec     ecx
0x1802da58a  cmp     ecx, 3
0x1802da58d  setnb   al
0x1802da590  test    eax, edx
0x1802da592  jz      short loc_1802DA5D1
0x1802da594  mov     edx, 4
0x1802da599  mov     rcx, r10
  ... truncated ...
```
