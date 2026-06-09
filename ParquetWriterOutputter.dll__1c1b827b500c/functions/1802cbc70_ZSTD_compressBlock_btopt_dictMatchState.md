# ZSTD_compressBlock_btopt_dictMatchState

- ea: `0x1802cbc70`
- end: `0x1802d0436`
- name: `ZSTD_compressBlock_btopt_dictMatchState`
- size: `18374`
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
- `0x1802cbc70`
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
unsigned __int64 __fastcall ZSTD_compressBlock_btopt_dictMatchState(
        __int64 a1,
        __int64 a2,
        int *a3,
        unsigned __int64 a4,
        __int64 a5)
{
  __int64 v5; // r15
  __int64 v6; // rcx
  int v7; // edx
  unsigned __int64 v8; // rdi
  unsigned int v9; // eax
  unsigned __int64 v10; // r12
  unsigned __int64 v11; // rsi
  __int64 v12; // rbx
  bool v13; // zf
  unsigned __int64 v14; // r11
  __int64 v15; // xmm2_8
  __int64 v16; // rbx
  __int64 v17; // r14
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
  unsigned int v34; // r14d
  __int64 v35; // rdi
  int v36; // r11d
  unsigned int v37; // ecx
  unsigned int v38; // r11d
  __int64 *v39; // r9
  unsigned int v40; // edx
  int v41; // edx
  int v42; // eax
  int v43; // r15d
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
  unsigned __int64 v95; // r14
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
  int v121; // r15d
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
  unsigned __int64 v173; // r14
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
  int v198; // r15d
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
  unsigned __int64 v251; // r14
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
  unsigned int v269; // r14d
  __int64 v270; // rdi
  char v271; // cl
  __int64 v272; // r10
  unsigned int v273; // r11d
  unsigned int v274; // ecx
  unsigned int v275; // edx
  int v276; // r10d
  int v277; // eax
  int v278; // r15d
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
  unsigned __int64 v339; // r14
  char *v340; // rbx
  char *v341; // r8
  unsigned __int64 v342; // r15
  __int64 v343; // rax
  __int64 v344; // rsi
  __int64 v345; // r11
  _DWORD *v346; // rcx
  unsigned __int8 v347; // al
  unsigned __int8 v348; // cl
  _DWORD *v349; // rcx
  unsigned int v350; // ebx
  __int64 v351; // r15
  __int64 v352; // r8
  int v353; // eax
  _DWORD *v354; // r9
  unsigned int *v355; // r14
  unsigned int v356; // r10d
  unsigned int v357; // edi
  unsigned int v358; // r13d
  unsigned int v359; // esi
  __int64 v360; // rcx
  int v361; // eax
  _DWORD *v362; // r8
  __int128 v363; // xmm0
  __int64 v364; // xmm1_8
  __int64 v365; // rdx
  __int64 v366; // r8
  unsigned int v367; // ecx
  unsigned int v368; // eax
  unsigned __int64 v369; // r8
  __int64 v370; // rcx
  int v371; // ebx
  __int64 v372; // rdx
  unsigned int v373; // edi
  unsigned int v374; // r15d
  unsigned __int64 v375; // rcx
  unsigned int v376; // edi
  _DWORD *v377; // rax
  unsigned int v378; // r12d
  unsigned int *v379; // r13
  unsigned int v380; // ebx
  unsigned int v381; // esi
  __int64 updated; // rax
  unsigned __int64 v383; // r10
  int v384; // r11d
  __int64 v385; // xmm1_8
  int v386; // r15d
  __int64 v387; // r12
  __int64 v388; // r8
  __int64 v389; // r9
  unsigned int v390; // ecx
  int v391; // edx
  unsigned int v392; // eax
  int v393; // r10d
  unsigned int v394; // eax
  __int64 v395; // rax
  __int64 v396; // rdx
  _DWORD *v397; // r9
  __int64 v398; // rcx
  unsigned int v399; // eax
  __int64 v400; // r15
  unsigned int v401; // edi
  unsigned int v402; // ecx
  unsigned __int64 v403; // r13
  _DWORD *v404; // r14
  unsigned int v405; // esi
  int v406; // ebx
  int v407; // ebx
  int v408; // eax
  __int64 v409; // r8
  _DWORD *v410; // rbx
  int v411; // r15d
  __int64 v412; // xmm0_8
  int v413; // eax
  int v414; // eax
  int v415; // eax
  __int64 v416; // r10
  unsigned __int64 v417; // r11
  __int64 v418; // rbx
  __int64 v419; // r15
  int v420; // r14d
  unsigned int v421; // esi
  __int64 v422; // r13
  unsigned int v423; // ebx
  __int64 v424; // r8
  __int64 v425; // rdx
  unsigned int v426; // eax
  __int64 v427; // rax
  unsigned int v428; // r9d
  unsigned __int64 v429; // r11
  __int64 v430; // r8
  unsigned int v431; // r14d
  __int64 v432; // r10
  __int64 v433; // r15
  char v434; // cl
  unsigned int v435; // ecx
  unsigned int v436; // r10d
  __int64 v437; // rsi
  unsigned int v438; // edx
  int v439; // r8d
  int v440; // eax
  int v441; // ecx
  unsigned __int64 v442; // rax
  unsigned int v443; // r10d
  unsigned int v444; // edx
  char v445; // cl
  unsigned int v446; // ecx
  _DWORD *v447; // rcx
  unsigned int v448; // edx
  unsigned int v449; // r15d
  unsigned int v450; // r10d
  unsigned int *v451; // r13
  unsigned int v452; // eax
  __int64 v453; // r9
  unsigned __int64 v454; // r8
  int v455; // eax
  __int64 v456; // r9
  _QWORD *v457; // rdx
  _QWORD *v458; // r8
  unsigned __int64 v459; // rax
  unsigned __int64 v460; // r9
  int v461; // eax
  int v462; // edx
  int v463; // r9d
  int v464; // eax
  __int64 v465; // rdx
  __int64 v466; // rcx
  _DWORD *v467; // r11
  __int64 v468; // rsi
  char *v469; // r11
  unsigned __int64 v470; // r8
  unsigned __int64 v471; // rcx
  __int64 v472; // rax
  int v473; // ebx
  __int64 v474; // r11
  _DWORD *v475; // rcx
  int v476; // r15d
  unsigned int v477; // esi
  unsigned __int64 v478; // r13
  unsigned int *v479; // rbx
  unsigned __int64 v480; // rax
  unsigned __int64 v481; // r9
  unsigned __int64 v482; // r10
  _QWORD *v483; // rdx
  char *v484; // r11
  signed __int64 v485; // rcx
  unsigned __int64 v486; // r9
  _DWORD *v487; // rcx
  unsigned int v488; // eax
  __int64 v489; // rdx
  __int64 v490; // r11
  unsigned int *v491; // rax
  __int64 v492; // rax
  unsigned __int64 v493; // rdi
  unsigned __int64 v494; // r8
  unsigned int v495; // esi
  _DWORD *v496; // rcx
  unsigned __int64 v497; // r15
  unsigned __int64 v498; // rbx
  unsigned __int64 v499; // r8
  __int64 v500; // rax
  __int64 v501; // r14
  __int64 v502; // r11
  _DWORD *v503; // rcx
  unsigned int v504; // ecx
  unsigned __int8 v505; // al
  unsigned __int8 v506; // cl
  __int64 v507; // rax
  unsigned int v508; // r9d
  unsigned __int64 v509; // r11
  __int64 v510; // r8
  unsigned int v511; // r14d
  __int64 v512; // r10
  _DWORD *v513; // r15
  char v514; // cl
  unsigned int v515; // ecx
  unsigned int v516; // r10d
  __int64 v517; // rsi
  unsigned int v518; // edx
  int v519; // r8d
  int v520; // eax
  int v521; // ecx
  unsigned __int64 v522; // rax
  unsigned int v523; // r10d
  unsigned int v524; // edx
  char v525; // cl
  unsigned int v526; // ecx
  _DWORD *v527; // rcx
  unsigned int v528; // edx
  unsigned int v529; // r15d
  unsigned int v530; // r10d
  unsigned int *v531; // r13
  unsigned int v532; // eax
  __int64 v533; // r9
  unsigned __int64 v534; // r8
  int v535; // eax
  __int64 v536; // r9
  _QWORD *v537; // rdx
  _QWORD *v538; // r8
  unsigned __int64 v539; // rax
  unsigned __int64 v540; // r9
  int v541; // eax
  int v542; // edx
  int v543; // r9d
  int v544; // eax
  __int64 v545; // rdx
  __int64 v546; // rcx
  _DWORD *v547; // r11
  __int64 v548; // rsi
  char *v549; // r11
  unsigned __int64 v550; // r8
  __int64 v551; // rcx
  __int64 v552; // rax
  int v553; // ebx
  __int64 v554; // r11
  _DWORD *v555; // rcx
  int v556; // r15d
  unsigned int v557; // esi
  unsigned __int64 v558; // r13
  unsigned int *v559; // rbx
  unsigned __int64 v560; // rax
  unsigned __int64 v561; // r9
  unsigned __int64 v562; // r10
  _QWORD *v563; // rdx
  char *v564; // r11
  signed __int64 v565; // rcx
  unsigned __int64 v566; // r9
  _DWORD *v567; // rcx
  unsigned int v568; // eax
  __int64 v569; // rdx
  __int64 v570; // r11
  __int64 *v571; // rax
  __int64 v572; // rax
  unsigned __int64 v573; // rdi
  unsigned __int64 v574; // r8
  unsigned int v575; // esi
  _DWORD *v576; // rcx
  unsigned __int64 v577; // r15
  unsigned __int64 v578; // rbx
  unsigned __int64 v579; // r8
  __int64 v580; // rax
  __int64 v581; // r14
  __int64 v582; // r11
  _DWORD *v583; // rcx
  unsigned int v584; // ecx
  unsigned __int8 v585; // al
  unsigned __int8 v586; // cl
  unsigned int v587; // eax
  __int64 v588; // rax
  unsigned int v589; // r9d
  unsigned __int64 v590; // r11
  __int64 v591; // r8
  unsigned int v592; // r14d
  __int64 v593; // r10
  _DWORD *v594; // r15
  char v595; // cl
  unsigned int v596; // ecx
  unsigned int v597; // r10d
  __int64 v598; // rsi
  unsigned int v599; // edx
  int v600; // r8d
  int v601; // eax
  int v602; // ecx
  unsigned __int64 v603; // rax
  unsigned int v604; // r10d
  unsigned int v605; // edx
  int v606; // ecx
  unsigned int v607; // ecx
  _DWORD *v608; // rcx
  unsigned int v609; // edx
  unsigned int v610; // r15d
  unsigned int v611; // r10d
  unsigned int *v612; // r13
  unsigned int v613; // eax
  __int64 v614; // r9
  unsigned __int64 v615; // r8
  int v616; // eax
  __int64 v617; // r9
  _QWORD *v618; // rdx
  _QWORD *v619; // r8
  unsigned __int64 v620; // rax
  unsigned __int64 v621; // r9
  int v622; // eax
  int v623; // edx
  int v624; // r9d
  int v625; // eax
  __int64 v626; // rdx
  __int64 v627; // rcx
  _DWORD *v628; // r11
  __int64 v629; // rsi
  char *v630; // r11
  unsigned __int64 v631; // r8
  unsigned __int64 v632; // rcx
  __int64 v633; // rax
  int v634; // ebx
  __int64 v635; // r11
  _DWORD *v636; // rcx
  int v637; // r15d
  unsigned int v638; // esi
  unsigned __int64 v639; // r13
  unsigned int *v640; // rbx
  unsigned __int64 v641; // rax
  unsigned __int64 v642; // r9
  unsigned __int64 v643; // r10
  _QWORD *v644; // rdx
  char *v645; // r11
  signed __int64 v646; // rcx
  unsigned __int64 v647; // r9
  _DWORD *v648; // rcx
  unsigned int v649; // eax
  __int64 v650; // rdx
  __int64 v651; // r11
  unsigned int *v652; // rax
  __int64 v653; // rax
  unsigned __int64 v654; // rdi
  unsigned __int64 v655; // r8
  unsigned int v656; // esi
  _DWORD *v657; // rcx
  unsigned __int64 v658; // r15
  unsigned __int64 v659; // rbx
  unsigned __int64 v660; // r8
  __int64 v661; // rax
  __int64 v662; // r14
  __int64 v663; // r11
  _DWORD *v664; // rcx
  unsigned int v665; // ecx
  unsigned __int8 v666; // al
  unsigned __int8 v667; // cl
  unsigned int v668; // eax
  __int64 v669; // rax
  unsigned int v670; // r9d
  unsigned __int64 v671; // r11
  __int64 v672; // r8
  unsigned int v673; // r14d
  __int64 v674; // r10
  __int64 v675; // r15
  char v676; // cl
  unsigned int v677; // ecx
  unsigned int v678; // r10d
  __int64 v679; // rsi
  unsigned int v680; // edx
  int v681; // r8d
  int v682; // eax
  int v683; // ecx
  unsigned __int64 v684; // rax
  unsigned int v685; // r10d
  unsigned int v686; // edx
  int v687; // ecx
  unsigned int v688; // ecx
  _DWORD *v689; // rcx
  unsigned int v690; // edx
  unsigned int v691; // r15d
  unsigned int v692; // r10d
  unsigned int *v693; // r13
  unsigned int v694; // eax
  unsigned int v695; // r8d
  __int64 v696; // r9
  int v697; // eax
  __int64 v698; // r10
  int v699; // r8d
  _QWORD *v700; // rdx
  unsigned __int64 v701; // r9
  _QWORD *v702; // r8
  unsigned __int64 v703; // rax
  int v704; // ecx
  unsigned __int64 v705; // r8
  __int64 v706; // rax
  _DWORD *v707; // rcx
  int v708; // eax
  int v709; // edx
  int v710; // r9d
  __int64 v711; // r8
  int v712; // eax
  __int64 v713; // rdx
  __int64 v714; // rcx
  __int64 v715; // r11
  int v716; // r8d
  __int64 v717; // rsi
  __int64 v718; // r11
  unsigned __int64 v719; // r8
  unsigned __int64 v720; // rcx
  __int64 v721; // rax
  int v722; // ebx
  __int64 v723; // r11
  unsigned int v724; // eax
  unsigned int v725; // esi
  unsigned __int64 v726; // r8
  unsigned __int64 v727; // r15
  unsigned __int64 v728; // rax
  int v729; // r11d
  _DWORD *v730; // rdx
  int v731; // ecx
  int v732; // r11d
  int v733; // r13d
  unsigned int v734; // esi
  unsigned int *v735; // rbx
  unsigned __int64 v736; // rax
  unsigned __int64 v737; // r9
  __int64 v738; // r10
  _QWORD *v739; // rdx
  unsigned __int64 v740; // rcx
  unsigned __int64 v741; // r9
  _DWORD *v742; // rcx
  unsigned int v743; // eax
  __int64 v744; // rdx
  __int64 v745; // r11
  unsigned int *v746; // rax
  __int64 v747; // rax
  unsigned int v748; // r9d
  unsigned __int64 v749; // rdi
  unsigned __int64 v750; // r8
  unsigned int v751; // esi
  __int64 v752; // rcx
  unsigned __int64 v753; // r15
  __int64 v754; // rbx
  unsigned __int64 v755; // r8
  __int64 v756; // rax
  __int64 v757; // r14
  __int64 v758; // r11
  unsigned int v759; // eax
  _DWORD *v760; // rcx
  unsigned int v761; // ecx
  unsigned __int8 v762; // al
  unsigned __int8 v763; // cl
  _DWORD *v764; // r14
  unsigned int v765; // esi
  unsigned int v766; // ecx
  unsigned int *v767; // rbx
  unsigned int v768; // r12d
  int v769; // r15d
  __int64 v770; // rax
  unsigned int v771; // r10d
  unsigned int v772; // edx
  unsigned int v773; // r11d
  __int64 v774; // xmm1_8
  unsigned int v775; // r14d
  __int64 v776; // r12
  unsigned int v777; // eax
  int v778; // esi
  unsigned int v779; // ebx
  __int64 v780; // r9
  __int64 v781; // r10
  unsigned int v782; // edx
  signed int v783; // r8d
  unsigned int v784; // ecx
  int v785; // r11d
  unsigned int v786; // ecx
  __int64 v787; // rcx
  __int64 v788; // r8
  int v789; // edx
  __int64 v790; // rcx
  __int64 v791; // rdx
  __int64 v792; // rax
  _DWORD *v793; // rdx
  __int128 v794; // xmm0
  __int64 v795; // rdx
  unsigned int v796; // ecx
  __int64 v797; // rcx
  int v798; // r8d
  unsigned int v799; // r14d
  unsigned __int64 v800; // rdx
  unsigned __int64 v801; // rbx
  __int64 v802; // rcx
  unsigned __int64 v803; // rdx
  __int64 v804; // r10
  __int64 v805; // rcx
  unsigned __int64 v806; // rax
  __int64 v807; // rcx
  unsigned __int64 v808; // rcx
  __int64 v809; // rcx
  unsigned __int64 v810; // rax
  __int64 v811; // rcx
  __int64 v812; // rcx
  __int64 v813; // rcx
  unsigned int v815; // [rsp+30h] [rbp-D0h]
  unsigned int v816; // [rsp+30h] [rbp-D0h]
  unsigned int v817; // [rsp+30h] [rbp-D0h]
  unsigned int v818; // [rsp+30h] [rbp-D0h]
  unsigned int v819; // [rsp+30h] [rbp-D0h]
  unsigned int *v820; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v821; // [rsp+38h] [rbp-C8h]
  unsigned int *v822; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v823; // [rsp+38h] [rbp-C8h]
  unsigned int *v824; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v825; // [rsp+38h] [rbp-C8h]
  unsigned int *v826; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v827; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v828; // [rsp+38h] [rbp-C8h]
  unsigned int v829; // [rsp+40h] [rbp-C0h]
  unsigned int v830; // [rsp+40h] [rbp-C0h]
  unsigned int v831; // [rsp+40h] [rbp-C0h]
  unsigned int v832; // [rsp+40h] [rbp-C0h]
  unsigned int v833; // [rsp+40h] [rbp-C0h]
  int v834; // [rsp+40h] [rbp-C0h]
  int v835; // [rsp+40h] [rbp-C0h]
  int v836; // [rsp+40h] [rbp-C0h]
  int v837; // [rsp+40h] [rbp-C0h]
  unsigned int v838; // [rsp+40h] [rbp-C0h]
  unsigned int v839; // [rsp+44h] [rbp-BCh]
  unsigned int v840; // [rsp+44h] [rbp-BCh]
  unsigned int v841; // [rsp+44h] [rbp-BCh]
  unsigned int v842; // [rsp+44h] [rbp-BCh]
  unsigned int v843; // [rsp+44h] [rbp-BCh]
  unsigned int v844; // [rsp+44h] [rbp-BCh]
  unsigned int v845; // [rsp+44h] [rbp-BCh]
  unsigned int v846; // [rsp+44h] [rbp-BCh]
  unsigned int *v847; // [rsp+48h] [rbp-B8h]
  unsigned int *v848; // [rsp+48h] [rbp-B8h]
  unsigned int *v849; // [rsp+48h] [rbp-B8h]
  unsigned int *v850; // [rsp+48h] [rbp-B8h]
  unsigned int *v851; // [rsp+48h] [rbp-B8h]
  unsigned int *v852; // [rsp+48h] [rbp-B8h]
  unsigned int *v853; // [rsp+48h] [rbp-B8h]
  unsigned int *v854; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v855; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v856; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v857; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v858; // [rsp+48h] [rbp-B8h]
  unsigned int v859; // [rsp+50h] [rbp-B0h]
  unsigned int v860; // [rsp+50h] [rbp-B0h]
  unsigned int v861; // [rsp+50h] [rbp-B0h]
  unsigned int v862; // [rsp+50h] [rbp-B0h]
  unsigned int v863; // [rsp+50h] [rbp-B0h]
  unsigned int v864; // [rsp+54h] [rbp-ACh]
  unsigned int v865; // [rsp+54h] [rbp-ACh]
  unsigned int v866; // [rsp+54h] [rbp-ACh]
  unsigned int v867; // [rsp+54h] [rbp-ACh]
  unsigned int v868; // [rsp+54h] [rbp-ACh]
  unsigned int v869; // [rsp+58h] [rbp-A8h]
  unsigned int v870; // [rsp+58h] [rbp-A8h]
  unsigned int v871; // [rsp+58h] [rbp-A8h]
  unsigned int v872; // [rsp+58h] [rbp-A8h]
  unsigned int v873; // [rsp+58h] [rbp-A8h]
  unsigned int v874; // [rsp+58h] [rbp-A8h]
  unsigned int v875; // [rsp+58h] [rbp-A8h]
  int v876; // [rsp+58h] [rbp-A8h]
  int v877; // [rsp+58h] [rbp-A8h]
  unsigned int v878; // [rsp+5Ch] [rbp-A4h]
  unsigned int v879; // [rsp+5Ch] [rbp-A4h]
  unsigned int v880; // [rsp+5Ch] [rbp-A4h]
  unsigned int v881; // [rsp+5Ch] [rbp-A4h]
  int v882; // [rsp+5Ch] [rbp-A4h]
  int v883; // [rsp+5Ch] [rbp-A4h]
  unsigned int v884; // [rsp+5Ch] [rbp-A4h]
  unsigned int v885; // [rsp+5Ch] [rbp-A4h]
  int v886; // [rsp+5Ch] [rbp-A4h]
  unsigned __int64 v887; // [rsp+60h] [rbp-A0h]
  unsigned int v888; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v889; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int *v890; // [rsp+70h] [rbp-90h]
  unsigned __int64 v891; // [rsp+78h] [rbp-88h]
  unsigned int v892; // [rsp+80h] [rbp-80h]
  BOOL v893; // [rsp+84h] [rbp-7Ch]
  unsigned int v894; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v895; // [rsp+8Ch] [rbp-74h] BYREF
  __int64 *v896; // [rsp+90h] [rbp-70h]
  _DWORD *v897; // [rsp+98h] [rbp-68h]
  unsigned __int64 v898; // [rsp+A0h] [rbp-60h]
  unsigned int v899; // [rsp+A8h] [rbp-58h]
  unsigned int v900; // [rsp+ACh] [rbp-54h]
  _DWORD *v901; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v902; // [rsp+B8h] [rbp-48h]
  unsigned int v903; // [rsp+C0h] [rbp-40h]
  __int64 v904; // [rsp+C8h] [rbp-38h]
  unsigned int v905; // [rsp+D0h] [rbp-30h]
  __int64 v906; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v907; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v908; // [rsp+E8h] [rbp-18h]
  unsigned int v909; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v910; // [rsp+F4h] [rbp-Ch] BYREF
  unsigned int v911; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v912; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 v913; // [rsp+108h] [rbp+8h]
  _DWORD *v914; // [rsp+110h] [rbp+10h]
  unsigned __int64 v915; // [rsp+118h] [rbp+18h]
  unsigned __int64 v916; // [rsp+120h] [rbp+20h]
  int v917; // [rsp+128h] [rbp+28h]
  unsigned __int64 v918; // [rsp+130h] [rbp+30h]
  __int64 v919; // [rsp+138h] [rbp+38h]
  int v920; // [rsp+140h] [rbp+40h]
  unsigned int v921; // [rsp+144h] [rbp+44h]
  int v922; // [rsp+148h] [rbp+48h] BYREF
  __int64 v923; // [rsp+150h] [rbp+50h]
  unsigned __int64 v924; // [rsp+158h] [rbp+58h]
  __int128 v925; // [rsp+160h] [rbp+60h]
  __int64 v926; // [rsp+170h] [rbp+70h]
  int v927; // [rsp+178h] [rbp+78h]
  __int128 v928; // [rsp+180h] [rbp+80h] BYREF
  __int64 v929; // [rsp+190h] [rbp+90h]
  int v930; // [rsp+198h] [rbp+98h]
  __int128 v931; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v932; // [rsp+1B0h] [rbp+B0h]
  int v933; // [rsp+1B8h] [rbp+B8h]
  __int128 v934; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v935; // [rsp+1D0h] [rbp+D0h]
  int v936; // [rsp+1D8h] [rbp+D8h]
  char v937[16]; // [rsp+1E0h] [rbp+E0h] BYREF
  char v938[24]; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned __int64 v942; // [rsp+268h] [rbp+168h]
  unsigned int v943; // [rsp+270h] [rbp+170h]
  unsigned int *v944; // [rsp+270h] [rbp+170h]
  unsigned int v945; // [rsp+270h] [rbp+170h]

  v942 = a4;
  v5 = a1;
  v6 = a1 + 72;
  v7 = 4095;
  v8 = a4;
  v919 = v6;
  v9 = *(_DWORD *)(v5 + 204);
  v10 = a4 + a5;
  v11 = a4 + a5 - 8;
  v12 = *(_QWORD *)(v5 + 8) + *(unsigned int *)(v5 + 24);
  v913 = a4 + a5;
  if ( v9 < 0xFFF )
    v7 = v9;
  v13 = *(_DWORD *)(v5 + 200) == 3;
  v921 = v7;
  v917 = !v13 + 3;
  v922 = *(_DWORD *)(v5 + 36);
  v914 = *(_DWORD **)(v6 + 40);
  v901 = *(_DWORD **)(v6 + 32);
  ZSTD_rescaleFreqs(v6, a4, a5, 0);
  v14 = v8 + (v8 == v12);
  v887 = v14;
  if ( v14 < v11 )
  {
    v15 = v926;
    v920 = v927;
    do
    {
      v16 = *(unsigned int *)(v5 + 36);
      v17 = *(_QWORD *)(v5 + 8);
      v18 = *(_DWORD *)(v5 + 200);
      v19 = v14 == v8;
      v899 = v14 - v8;
      v893 = v19;
      if ( v14 < v17 + v16 )
        goto LABEL_1010;
      v20 = v14 - v17;
      if ( (unsigned int)v16 < (int)v14 - (int)v17 )
      {
        do
          LODWORD(v16) = ZSTD_insertBt1(v5, (int)v17 + (int)v16, v10, v18, 0) + v16;
        while ( (unsigned int)v16 < v20 );
        v19 = v893;
        v14 = v887;
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
          v906 = v25;
          v27 = *(_DWORD *)(v5 + 204);
          if ( v26 )
          {
            if ( v27 < 0xFFF )
              v23 = *(_DWORD *)(v5 + 204);
            v894 = v23;
            v859 = v14 - v25;
            v28 = ZSTD_hash6Ptr(v14, v22, v21);
            v31 = *(_DWORD *)(v30 + 4 * v28);
            v32 = (_DWORD *)(v30 + 4 * v28);
            v33 = *(unsigned int *)(v5 + 24);
            v34 = v29 + 9;
            v35 = *(_QWORD *)(v5 + 64);
            v36 = 1 << (*(_DWORD *)(v5 + 188) - 1);
            v897 = v32;
            v37 = 0;
            v38 = v36 - 1;
            v896 = v39;
            v839 = v38;
            v907 = v25 + v33;
            v904 = v35;
            v898 = 0;
            v903 = v33;
            v829 = v29 + 9;
            if ( v38 < v29 )
              v37 = v29 - v38;
            v900 = v37;
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
            v878 = v42;
            v943 = 0;
            v820 = (unsigned int *)(v35 + 8LL * (v29 & v38));
            v847 = v820 + 1;
            v902 = *(_QWORD *)(a1 + 176);
            v44 = *(unsigned int **)v902;
            v45 = *(_QWORD *)v902 - *(_QWORD *)(v902 + 8);
            v908 = *(_QWORD *)(v902 + 8);
            v46 = *(_DWORD *)(v902 + 28);
            v47 = v41 - v45;
            v890 = v44;
            LODWORD(v44) = *(_DWORD *)(v902 + 192);
            v48 = *(_DWORD *)(v902 + 188) - 1;
            v888 = v45;
            v869 = v46;
            v864 = v47;
            v815 = (unsigned int)v44;
            LODWORD(v44) = v45 - v46;
            v895 = (1 << v48) - 1;
            v49 = v45;
            v50 = v19 + 3;
            v51 = v49 - v895;
            v892 = v19 + 3;
            v52 = v19;
            if ( v895 >= (unsigned int)v44 )
              v51 = v46;
            v918 = (unsigned int)(v917 - 1);
            v889 = v51;
            v53 = a3;
            v891 = v918;
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
                v70 = v908 + v58 - (unsigned __int64)v47;
                v71 = v903 - v58;
                v62 = v887;
                if ( v57 - 1 < v859 - v47 - v869 && v71 - 1 >= 3 )
                {
                  MINMATCH = ZSTD_readMINMATCH(v887, 4, 0, v70);
                  if ( MINMATCH == *v73 )
                  {
                    v74 = ZSTD_count_2segments((int)v62 + 4, (int)v73 + 4, v10, (_DWORD)v890, v907);
                    v50 = v892;
                    v62 = v887;
                    v59 = (unsigned int)(v74 + 4);
                  }
                }
              }
              else
              {
                v60 = ZSTD_readMINMATCH(v887, 4, 0, -(__int64)v57);
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
              if ( (unsigned int)v59 > v891 )
              {
                v75 = &v901[2 * v943];
                *v75 = v52 - v893;
                v891 = (unsigned int)v59;
                v75[1] = v59;
                ++v943;
                if ( (unsigned int)v59 > v894 || v62 + (unsigned int)v59 == v10 )
                  goto LABEL_222;
              }
              v47 = v864;
              ++v52;
              v53 = a3;
              ++v56;
              if ( v52 >= v50 )
              {
                v76 = v887;
                *v897 = v859;
                if ( v43 )
                {
                  v77 = v891;
                  do
                  {
                    --v43;
                    if ( v31 < v878 )
                      goto LABEL_88;
                    v76 = v887;
                    v78 = (unsigned int *)(v904 + 8LL * (v31 & v839));
                    v79 = (__int64 *)v898;
                    v80 = v10 - 7;
                    if ( (unsigned __int64)v896 < v898 )
                      v79 = v896;
                    v81 = v906 + v31;
                    v82 = (__int64 *)((char *)v79 + v887);
                    v59 = (unsigned __int64)v79 + v81;
                    if ( (unsigned __int64)v79 + v887 >= v80 )
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
                      v83 = (char *)v82 - ((char *)v79 + v887);
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
                        v829 = v84 + v31;
                      }
                      v85 = &v901[2 * v943];
                      v85[1] = v84;
                      *v85 = v859 - v31 + 2;
                      ++v943;
                      v891 = v84;
                      if ( v84 > 0x1000 || v84 + v887 == v10 )
                      {
                        v43 = 0;
                        goto LABEL_88;
                      }
                      v77 = v84;
                    }
                    if ( *(_BYTE *)(v81 + v84) >= *(_BYTE *)(v84 + v887) )
                    {
                      v898 = v84;
                      *v847 = v31;
                      if ( v31 <= v900 )
                      {
                        v847 = &v894;
                        goto LABEL_88;
                      }
                      v31 = *v78;
                      v847 = v78;
                    }
                    else
                    {
                      v896 = (__int64 *)v84;
                      *v820 = v31;
                      if ( v31 <= v900 )
                      {
                        v89 = &v894;
                        goto LABEL_89;
                      }
                      v31 = v78[1];
                      v820 = v78 + 1;
                    }
                  }
                  while ( v43 );
                }
                --v43;
LABEL_88:
                v89 = v820;
LABEL_89:
                *v847 = 0;
                *v89 = 0;
                if ( v43 )
                {
                  v90 = ZSTD_hash6Ptr(v76, v815, v59);
                  v91 = 0;
                  v821 = 0;
                  v92 = 0;
                  v93 = *(_DWORD *)(*(_QWORD *)(v902 + 48) + 4 * v90);
                  v94 = *(_QWORD *)(v902 + 64);
                  v904 = v94;
                  while ( 1 )
                  {
                    v897 = (_DWORD *)v92;
                    v903 = v34;
                    v892 = v43 - 1;
                    if ( v93 <= v869 )
                      break;
                    v95 = v91;
                    if ( v92 < v91 )
                      v95 = v92;
                    v96 = v93 + v908;
                    v848 = (unsigned int *)(v94 + 8LL * (v895 & v93));
                    v97 = (char *)v10;
                    if ( (unsigned __int64)v890 + v887 - v96 < v10 )
                      v97 = (char *)v890 + v887 - v96;
                    v98 = ZSTD_count(v95 + v887, v96 + v95, v97);
                    v99 = v98;
                    if ( (unsigned int *)(v98 + v100) == v890 )
                      v99 = ZSTD_count(v98 + v95 + v887, v907, v10) + v98;
                    v92 = v95 + v99;
                    if ( v95 + v99 + v93 >= v888 )
                      v96 = v93 + v906 + v864;
                    if ( v92 <= v891 )
                    {
                      v34 = v829;
                    }
                    else
                    {
                      v34 = v93 + v864 + v92;
                      v101 = v901;
                      v901[2 * v943 + 1] = v92;
                      v101[2 * v943] = v859 - (v93 + v864) + 2;
                      v891 = v92;
                      ++v943;
                      if ( v92 <= v829 - (v93 + v864) )
                        v34 = v903;
                      v829 = v34;
                      if ( v92 > 0x1000 || v92 + v887 == v10 )
                        break;
                    }
                    if ( v93 <= v889 )
                      break;
                    v102 = *(_BYTE *)(v96 + v92);
                    v103 = *(_BYTE *)(v92 + v887);
                    if ( v102 >= v103 )
                    {
                      v93 = *v848;
                      v91 = v92;
                      v821 = v92;
                    }
                    else
                    {
                      v93 = v848[1];
                      v91 = v821;
                    }
                    v43 = v892;
                    v104 = v102 < v103;
                    v94 = v904;
                    if ( !v104 )
                      v92 = (unsigned __int64)v897;
                    if ( !v892 )
                    {
                      v105 = v943;
                      v106 = v34 - 8;
                      goto LABEL_444;
                    }
                  }
                }
LABEL_221:
                *(_DWORD *)(a1 + 36) = v34 - 8;
LABEL_222:
                v105 = v943;
                goto LABEL_445;
              }
              v29 = v859;
            }
          }
          if ( v27 < 0xFFF )
            v23 = *(_DWORD *)(v5 + 204);
          v895 = v23;
          v860 = v14 - v25;
          v107 = ZSTD_hash4Ptr(v14, v22, v21);
          v110 = *(_DWORD *)(v109 + 4 * v107);
          v111 = (_DWORD *)(v109 + 4 * v107);
          v112 = *(unsigned int *)(v5 + 24);
          v34 = v108 + 9;
          v113 = *(_QWORD *)(v5 + 64);
          v114 = 1 << (*(_DWORD *)(v5 + 188) - 1);
          v897 = v111;
          v115 = 0;
          v116 = v114 - 1;
          v896 = v117;
          v892 = v116;
          v907 = v25 + v112;
          v904 = v113;
          v898 = 0;
          v889 = v112;
          v830 = v108 + 9;
          if ( v116 < v108 )
            v115 = v108 - v116;
          v900 = v115;
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
          v903 = v120;
          v943 = 0;
          v822 = (unsigned int *)(v113 + 8LL * (v108 & v116));
          v849 = v822 + 1;
          v902 = *(_QWORD *)(a1 + 176);
          v122 = *(unsigned int **)v902;
          v123 = *(_QWORD *)v902 - *(_QWORD *)(v902 + 8);
          v908 = *(_QWORD *)(v902 + 8);
          v124 = *(_DWORD *)(v902 + 28);
          v125 = v119 - v123;
          v890 = v122;
          v126 = *(_DWORD *)(v902 + 188) - 1;
          v840 = v123;
          v870 = v124;
          v865 = v125;
          v894 = *(_DWORD *)(v902 + 192);
          LODWORD(v122) = v123 - v124;
          v879 = (1 << v126) - 1;
          v127 = v123;
          v128 = v19 + 3;
          v129 = v127 - v879;
          v888 = v19 + 3;
          v130 = v19;
          if ( v879 >= (unsigned int)v122 )
            v129 = v124;
          v918 = (unsigned int)(v917 - 1);
          v816 = v129;
          v131 = a3;
          v891 = v918;
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
              v148 = v908 + v136 - (unsigned __int64)v125;
              v149 = v889 - v136;
              v140 = v887;
              if ( v135 - 1 < v860 - v125 - v870 && v149 - 1 >= 3 )
              {
                v150 = ZSTD_readMINMATCH(v887, 4, 0, v148);
                if ( v150 == *v151 )
                {
                  v152 = ZSTD_count_2segments((int)v140 + 4, (int)v151 + 4, v10, (_DWORD)v890, v907);
                  v128 = v888;
                  v140 = v887;
                  v137 = (unsigned int)(v152 + 4);
                }
              }
            }
            else
            {
              v138 = ZSTD_readMINMATCH(v887, 4, 0, -(__int64)v135);
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
            if ( (unsigned int)v137 > v891 )
            {
              v153 = &v901[2 * v943];
              *v153 = v130 - v893;
              v891 = (unsigned int)v137;
              v153[1] = v137;
              ++v943;
              if ( (unsigned int)v137 > v895 || v140 + (unsigned int)v137 == v10 )
                goto LABEL_222;
            }
            v125 = v865;
            ++v130;
            v131 = a3;
            ++v134;
            if ( v130 >= v128 )
            {
              v154 = v887;
              *v897 = v860;
              if ( !v121 )
              {
LABEL_192:
                --v121;
LABEL_193:
                v167 = v822;
LABEL_194:
                *v849 = 0;
                *v167 = 0;
                if ( v121 )
                {
                  v168 = ZSTD_hash4Ptr(v154, v894, v137);
                  v169 = 0;
                  v823 = 0;
                  v170 = 0;
                  v171 = *(_DWORD *)(*(_QWORD *)(v902 + 48) + 4 * v168);
                  v172 = *(_QWORD *)(v902 + 64);
                  v904 = v172;
                  while ( 1 )
                  {
                    v897 = (_DWORD *)v170;
                    v889 = v34;
                    v888 = v121 - 1;
                    if ( v171 <= v870 )
                      break;
                    v173 = v169;
                    if ( v170 < v169 )
                      v173 = v170;
                    v174 = v171 + v908;
                    v175 = (char *)v10;
                    v850 = (unsigned int *)(v172 + 8LL * (v171 & v879));
                    if ( (unsigned __int64)v890 + v887 - v174 < v10 )
                      v175 = (char *)v890 + v887 - v174;
                    v176 = ZSTD_count(v173 + v887, v174 + v173, v175);
                    v177 = v176;
                    if ( (unsigned int *)(v176 + v178) == v890 )
                      v177 = ZSTD_count(v176 + v173 + v887, v907, v10) + v176;
                    v170 = v177 + v173;
                    if ( v177 + v173 + v171 >= v840 )
                      v174 = v171 + v906 + v865;
                    if ( v170 <= v891 )
                    {
                      v34 = v830;
                    }
                    else
                    {
                      v34 = v865 + v171 + v170;
                      v179 = v901;
                      v901[2 * v943 + 1] = v170;
                      v179[2 * v943] = v860 - (v865 + v171) + 2;
                      v891 = v170;
                      ++v943;
                      if ( v170 <= v830 - (v865 + v171) )
                        v34 = v889;
                      v830 = v34;
                      if ( v170 > 0x1000 || v170 + v887 == v10 )
                        goto LABEL_221;
                    }
                    if ( v171 > v816 )
                    {
                      v180 = *(_BYTE *)(v174 + v170);
                      v181 = *(_BYTE *)(v170 + v887);
                      if ( v180 >= v181 )
                      {
                        v171 = *v850;
                        v169 = v170;
                        v823 = v170;
                      }
                      else
                      {
                        v171 = v850[1];
                        v169 = v823;
                      }
                      v121 = v888;
                      v104 = v180 < v181;
                      v172 = v904;
                      if ( !v104 )
                        v170 = (unsigned __int64)v897;
                      if ( v888 )
                        continue;
                    }
                    goto LABEL_221;
                  }
                }
                goto LABEL_221;
              }
              v155 = v891;
              while ( 2 )
              {
                --v121;
                if ( v110 < v903 )
                  goto LABEL_193;
                v154 = v887;
                v156 = (unsigned int *)(v904 + 8LL * (v110 & v892));
                v157 = (__int64 *)v898;
                v158 = v10 - 7;
                if ( (unsigned __int64)v896 < v898 )
                  v157 = v896;
                v159 = v906 + v110;
                v160 = (__int64 *)((char *)v157 + v887);
                v137 = (unsigned __int64)v157 + v159;
                if ( (unsigned __int64)v157 + v887 < v158 )
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
                        v830 = v110 + v162;
                      }
                      v163 = &v901[2 * v943];
                      v163[1] = v162;
                      *v163 = v860 - v110 + 2;
                      ++v943;
                      v891 = v162;
                      if ( v162 > 0x1000 || v162 + v887 == v10 )
                      {
                        v121 = 0;
                        goto LABEL_193;
                      }
                      v155 = v162;
                    }
                    if ( *(_BYTE *)(v159 + v162) >= *(_BYTE *)(v162 + v887) )
                    {
                      v898 = v162;
                      *v849 = v110;
                      if ( v110 <= v900 )
                      {
                        v849 = &v889;
                        goto LABEL_193;
                      }
                      v110 = *v156;
                      v849 = v156;
                    }
                    else
                    {
                      v896 = (__int64 *)v162;
                      *v822 = v110;
                      if ( v110 <= v900 )
                      {
                        v167 = &v889;
                        goto LABEL_194;
                      }
                      v110 = v156[1];
                      v822 = v156 + 1;
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
              v161 = (char *)v160 - ((char *)v157 + v887);
              goto LABEL_180;
            }
            v108 = v860;
          }
        }
        v182 = *(_QWORD *)(v5 + 8);
        if ( *(_DWORD *)(v5 + 204) < 0xFFFu )
          v23 = *(_DWORD *)(v5 + 204);
        v906 = *(_QWORD *)(v5 + 8);
        v895 = v23;
        v861 = v14 - v182;
        v183 = ZSTD_hash5Ptr(v14, v22, v21);
        v186 = *(_DWORD *)(v185 + 4 * v183);
        v187 = (_DWORD *)(v185 + 4 * v183);
        v188 = *(unsigned int *)(v5 + 24);
        v34 = v184 + 9;
        v189 = *(_QWORD *)(v5 + 64);
        v190 = *(_DWORD *)(v5 + 188) - 1;
        v897 = v187;
        v191 = 1 << v190;
        v907 = v182 + v188;
        v192 = 0;
        v193 = v191 - 1;
        v896 = v194;
        v892 = v193;
        v904 = v189;
        v898 = 0;
        v889 = v188;
        if ( v193 < v184 )
          v192 = v184 - v193;
        v831 = v184 + 9;
        v900 = v192;
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
        v903 = v197;
        v943 = 0;
        v824 = (unsigned int *)(v189 + 8LL * (v184 & v193));
        v851 = v824 + 1;
        v902 = *(_QWORD *)(a1 + 176);
        v199 = *(unsigned int **)v902;
        v200 = *(_QWORD *)v902 - *(_QWORD *)(v902 + 8);
        v908 = *(_QWORD *)(v902 + 8);
        v201 = *(_DWORD *)(v902 + 28);
        v202 = v196 - v200;
        v890 = v199;
        v203 = *(_DWORD *)(v902 + 188);
        v866 = v202;
        v841 = v200;
        v871 = v201;
        v894 = *(_DWORD *)(v902 + 192);
        LODWORD(v199) = v200 - v201;
        v204 = 1 << (v203 - 1);
        v205 = v200;
        --v204;
        v206 = v19 + 3;
        v207 = v205 - v204;
        v880 = v204;
        v104 = v204 < (unsigned int)v199;
        v888 = v19 + 3;
        v208 = v19;
        if ( !v104 )
          v207 = v201;
        v817 = v207;
        v209 = a3;
        v918 = (unsigned int)(v917 - 1);
        v891 = v918;
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
            v226 = v908 + v214 - (unsigned __int64)v202;
            v227 = v889 - v214;
            v218 = v887;
            if ( v213 - 1 < v861 - v202 - v871 && v227 - 1 >= 3 )
            {
              v228 = ZSTD_readMINMATCH(v887, 4, 0, v226);
              if ( v228 == *v229 )
              {
                v230 = ZSTD_count_2segments((int)v218 + 4, (int)v229 + 4, v10, (_DWORD)v890, v907);
                v206 = v888;
                v218 = v887;
                v215 = (unsigned int)(v230 + 4);
              }
            }
          }
          else
          {
            v216 = ZSTD_readMINMATCH(v887, 4, 0, -(__int64)v213);
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
          if ( (unsigned int)v215 > v891 )
          {
            v231 = &v901[2 * v943];
            *v231 = v208 - v893;
            v891 = (unsigned int)v215;
            v231[1] = v215;
            ++v943;
            if ( (unsigned int)v215 > v895 || v218 + (unsigned int)v215 == v10 )
              goto LABEL_222;
          }
          v202 = v866;
          ++v208;
          v209 = a3;
          ++v212;
          if ( v208 >= v206 )
          {
            v232 = v887;
            *v897 = v861;
            if ( !v198 )
            {
LABEL_298:
              --v198;
LABEL_299:
              v245 = v824;
LABEL_300:
              *v851 = 0;
              *v245 = 0;
              if ( v198 )
              {
                v246 = ZSTD_hash5Ptr(v232, v894, v215);
                v247 = 0;
                v825 = 0;
                v248 = 0;
                v249 = *(_DWORD *)(*(_QWORD *)(v902 + 48) + 4 * v246);
                v250 = *(_QWORD *)(v902 + 64);
                v904 = v250;
                while ( 1 )
                {
                  v897 = (_DWORD *)v248;
                  v889 = v34;
                  v888 = v198 - 1;
                  if ( v249 <= v871 )
                    break;
                  v251 = v247;
                  if ( v248 < v247 )
                    v251 = v248;
                  v252 = v249 + v908;
                  v253 = (char *)v10;
                  v852 = (unsigned int *)(v250 + 8LL * (v880 & v249));
                  if ( (unsigned __int64)v890 + v887 - v252 < v10 )
                    v253 = (char *)v890 + v887 - v252;
                  v254 = ZSTD_count(v251 + v887, v252 + v251, v253);
                  v255 = v254;
                  if ( (unsigned int *)(v254 + v256) == v890 )
                    v255 = ZSTD_count(v254 + v251 + v887, v907, v10) + v254;
                  v248 = v255 + v251;
                  if ( v255 + v251 + v249 >= v841 )
                    v252 = v906 + v866 + (unsigned __int64)v249;
                  if ( v248 <= v891 )
                  {
                    v34 = v831;
                  }
                  else
                  {
                    v34 = v249 + v866 + v248;
                    v257 = v901;
                    v901[2 * v943 + 1] = v248;
                    v257[2 * v943] = v861 - (v249 + v866) + 2;
                    v891 = v248;
                    ++v943;
                    if ( v248 <= v831 - (v249 + v866) )
                      v34 = v889;
                    v831 = v34;
                    if ( v248 > 0x1000 || v248 + v887 == v10 )
                      goto LABEL_221;
                  }
                  if ( v249 <= v817 )
                    goto LABEL_221;
                  v258 = *(_BYTE *)(v252 + v248);
                  v259 = *(_BYTE *)(v248 + v887);
                  if ( v258 >= v259 )
                  {
                    v249 = *v852;
                    v247 = v248;
                    v825 = v248;
                  }
                  else
                  {
                    v249 = v852[1];
                    v247 = v825;
                  }
                  v198 = v888;
                  v104 = v258 < v259;
                  v250 = v904;
                  if ( !v104 )
                    v248 = (unsigned __int64)v897;
                  if ( !v888 )
                  {
                    v105 = v943;
                    v106 = v34 - 8;
                    goto LABEL_444;
                  }
                }
              }
              goto LABEL_221;
            }
            v233 = v891;
            while ( 2 )
            {
              --v198;
              if ( v186 < v903 )
                goto LABEL_299;
              v232 = v887;
              v234 = (unsigned int *)(v904 + 8LL * (v186 & v892));
              v235 = (__int64 *)v898;
              v236 = v10 - 7;
              if ( (unsigned __int64)v896 < v898 )
                v235 = v896;
              v237 = v906 + v186;
              v238 = (__int64 *)((char *)v235 + v887);
              v215 = (unsigned __int64)v235 + v237;
              if ( (unsigned __int64)v235 + v887 < v236 )
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
                      v831 = v240 + v186;
                    }
                    v241 = &v901[2 * v943];
                    v241[1] = v240;
                    *v241 = v861 - v186 + 2;
                    ++v943;
                    v891 = v240;
                    if ( v240 > 0x1000 || v240 + v887 == v10 )
                    {
                      v198 = 0;
                      goto LABEL_299;
                    }
                    v233 = v240;
                  }
                  if ( *(_BYTE *)(v237 + v240) >= *(_BYTE *)(v240 + v887) )
                  {
                    v898 = v240;
                    *v851 = v186;
                    if ( v186 <= v900 )
                    {
                      v851 = &v888;
                      goto LABEL_299;
                    }
                    v186 = *v234;
                    v851 = v234;
                  }
                  else
                  {
                    v896 = (__int64 *)v240;
                    *v824 = v186;
                    if ( v186 <= v900 )
                    {
                      v245 = &v888;
                      goto LABEL_300;
                    }
                    v186 = v234[1];
                    v824 = v234 + 1;
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
            v239 = (char *)v238 - ((char *)v235 + v887);
            goto LABEL_286;
          }
          v184 = v861;
        }
      }
      v260 = *(_DWORD *)(v5 + 204);
      v261 = 4095;
      v262 = *(__int64 **)(v5 + 8);
      v896 = v262;
      if ( v260 < 0xFFF )
        v261 = v260;
      v862 = v14 - (_DWORD)v262;
      v263 = ZSTD_hash4Ptr(v14, v22, v21);
      v266 = *(_DWORD *)(v265 + 4 * v263);
      v267 = (_DWORD *)(v265 + 4 * v263);
      v268 = *(unsigned int *)(v5 + 24);
      v269 = v264 + 9;
      v270 = *(_QWORD *)(v5 + 64);
      v271 = *(_DWORD *)(v5 + 188) - 1;
      v897 = v267;
      v904 = v270;
      v912 = v272 + v268;
      v273 = (1 << v271) - 1;
      v898 = 0;
      v903 = v273;
      v908 = 0;
      v274 = 0;
      v889 = v268;
      if ( v273 < v264 )
        v274 = v264 - v273;
      v832 = v264 + 9;
      v900 = v274;
      v275 = 1 << *(_DWORD *)(v5 + 184);
      v276 = v264 - v275;
      v943 = 0;
      v277 = 1;
      if ( v264 - *(_DWORD *)(v5 + 28) <= v275 )
        v276 = *(_DWORD *)(v5 + 28);
      if ( *(_DWORD *)(v5 + 32) )
        v276 = *(_DWORD *)(v5 + 28);
      if ( v276 )
        v277 = v276;
      v278 = 1 << *(_DWORD *)(v5 + 196);
      v867 = v277;
      v826 = (unsigned int *)(v270 + 8LL * (v264 & v273));
      v853 = v826 + 1;
      v902 = *(_QWORD *)(a1 + 176);
      v279 = *(unsigned int **)v902;
      v280 = *(_QWORD *)v902 - *(_QWORD *)(v902 + 8);
      v907 = *(_QWORD *)(v902 + 8);
      v281 = *(_DWORD *)(v902 + 28);
      v890 = v279;
      v282 = *(_DWORD *)(v902 + 188);
      v842 = v276 - v280;
      v881 = v280;
      v872 = v281;
      v892 = *(_DWORD *)(v902 + 192);
      v283 = (1 << (v282 - 1)) - 1;
      v284 = v280 - v283;
      v894 = v283;
      if ( v283 >= v280 - v281 )
        v284 = v281;
      v918 = (unsigned int)(v917 - 1);
      v891 = v918;
      v285 = v264 - v268;
      v818 = v284;
      v286 = v893;
      v287 = a3;
      v895 = v264 - v268;
      v288 = v893 + 3;
      v888 = v893 + 3;
      v289 = &a3[v893];
      while ( 1 )
      {
        v290 = v286 == 3 ? *v287 - 1 : *v289;
        v291 = v264 - v290;
        v292 = 0;
        if ( v290 - 1 >= v285 )
        {
          if ( v290 - 1 < v862 - v842 - v872 && v889 - v291 - 1 >= 3 )
          {
            v304 = (unsigned int)(*(_DWORD *)(v907 + v291 - (unsigned __int64)v842) << 8);
            LODWORD(v906) = 1;
            v305 = ZSTD_readMINMATCH(v887, 3, v304, 0);
            if ( v305 == v308 )
            {
              v309 = ZSTD_count_2segments(v306 + 3, v307 + 3, v10, (_DWORD)v890, v912);
              v288 = v888;
              v292 = v309 + 3;
            }
          }
        }
        else
        {
          LODWORD(v916) = 1;
          v293 = ZSTD_readMINMATCH(v887, 3, (unsigned int)(*(_DWORD *)(v887 - v290) << 8), 0);
          if ( v293 != v296 )
            goto LABEL_366;
          v297 = (_QWORD *)(v294 + 3);
          v298 = v294 + 3;
          v299 = (_QWORD *)(v295 + v294 + 3);
          v300 = v10 - 7;
          if ( v294 + 3 >= v10 - 7 )
            goto LABEL_1015;
          if ( *v297 != *v299 )
          {
            v292 = ZSTD_NbCommonBytes(*v297 ^ *v299, v297, v299, v298) + 3;
            goto LABEL_366;
          }
          v297 = (_QWORD *)(v294 + 11);
          ++v299;
          if ( v294 + 11 >= v300 )
          {
LABEL_1015:
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
        if ( v292 <= v891 )
        {
          v311 = v887;
        }
        else
        {
          v310 = &v901[2 * v943];
          *v310 = v286 - v893;
          v891 = v292;
          v310[1] = v292;
          v311 = v887;
          ++v943;
          if ( v292 > v261 || v887 + v292 == v10 )
            goto LABEL_222;
        }
        ++v286;
        ++v289;
        if ( v286 >= v288 )
          break;
        v285 = v895;
        v264 = v862;
        v287 = a3;
      }
      v312 = v891;
      if ( v891 >= 3 )
        goto LABEL_377;
      FirstIndexHash3 = ZSTD_insertAndFindFirstIndexHash3(a1, &v922, v311);
      v314 = v867;
      if ( FirstIndexHash3 < v867 || v862 - FirstIndexHash3 >= 0x40000 )
        goto LABEL_378;
      v315 = ZSTD_count(v887, (char *)v896 + FirstIndexHash3, v10);
      if ( v315 < 3 )
      {
LABEL_377:
        v314 = v867;
LABEL_378:
        v319 = v943;
        goto LABEL_379;
      }
      v317 = v901;
      v318 = v316 + 2;
      v891 = v315;
      v319 = 1;
      v312 = v315;
      v943 = 1;
      *v901 = v318;
      v317[1] = v315;
      if ( v315 > v261 || v315 + v887 == v10 )
      {
        v106 = v862 + 1;
        goto LABEL_443;
      }
      v314 = v867;
LABEL_379:
      *v897 = v862;
      if ( v278 )
      {
        while ( 2 )
        {
          --v278;
          if ( v266 < v314 )
            goto LABEL_417;
          v320 = (unsigned int *)(v904 + 8LL * (v266 & v903));
          v321 = v10 - 7;
          v322 = v908;
          if ( v898 < v908 )
            v322 = v898;
          v323 = (char *)v896 + v266;
          v324 = (_QWORD *)(v322 + v887);
          v325 = &v323[v322];
          if ( v322 + v887 < v321 )
          {
            if ( *v324 != *(_QWORD *)v325 )
            {
              v326 = (unsigned int)ZSTD_NbCommonBytes(*v324 ^ *(_QWORD *)v325, v324, v325, v322);
LABEL_400:
              v327 = v326 + v322;
              if ( v327 <= v312 )
              {
                v319 = v943;
              }
              else
              {
                if ( v327 > v269 - v266 )
                {
                  v269 = v327 + v266;
                  v832 = v327 + v266;
                }
                v328 = v901;
                v901[2 * v943 + 1] = v327;
                v328[2 * v943] = v862 - v266 + 2;
                v891 = v327;
                v319 = ++v943;
                v312 = v327;
                if ( v327 > 0x1000 || v327 + v887 == v10 )
                {
                  v278 = 0;
                  goto LABEL_417;
                }
              }
              if ( (unsigned __int8)v323[v327] >= *(_BYTE *)(v327 + v887) )
              {
                v908 = v327;
                *v853 = v266;
                if ( v266 <= v900 )
                {
                  v853 = &v895;
                  goto LABEL_417;
                }
                v266 = *v320;
                v853 = v320;
              }
              else
              {
                v898 = v327;
                *v826 = v266;
                if ( v266 <= v900 )
                {
                  v332 = &v895;
                  goto LABEL_418;
                }
                v266 = v320[1];
                v826 = v320 + 1;
              }
              if ( !v278 )
                goto LABEL_416;
              v314 = v867;
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
        v326 = (unsigned __int64)v324 - v322 - v887;
        goto LABEL_400;
      }
LABEL_416:
      --v278;
LABEL_417:
      v332 = v826;
LABEL_418:
      *v853 = 0;
      *v332 = 0;
      if ( v278 )
      {
        v333 = ZSTD_hash4Ptr(v887, v892, 0);
        v336 = (unsigned int)v334;
        v827 = v334;
        v337 = *(_DWORD *)(*(_QWORD *)(v902 + 48) + 4 * v333);
        v338 = *(_QWORD *)(v902 + 64);
        v904 = v338;
        while ( 1 )
        {
          v897 = (_DWORD *)v334;
          v889 = v269;
          v888 = v278 - 1;
          if ( v337 <= v872 )
            break;
          v339 = v336;
          if ( v334 < v336 )
            v339 = v334;
          v340 = (char *)(v337 + v907);
          v341 = (char *)v10;
          v854 = (unsigned int *)(v338 + 8LL * (v894 & v337));
          v342 = v339 + v335;
          if ( (unsigned __int64)v890 + v335 - (_QWORD)v340 < v10 )
            v341 = (char *)v890 + v335 - (_QWORD)v340;
          v343 = ZSTD_count(v339 + v335, &v340[v339], v341);
          v344 = v343;
          if ( (unsigned int *)(v343 + v345) == v890 )
            v344 = ZSTD_count(v343 + v342, v912, v10) + v343;
          v334 = v344 + v339;
          if ( v344 + v339 + v337 >= v881 )
            v340 = (char *)v896 + v842 + (unsigned __int64)v337;
          v335 = v887;
          if ( v334 <= v891 )
          {
            v269 = v832;
            v319 = v943;
          }
          else
          {
            v269 = v334 + v337 + v842;
            v346 = v901;
            v901[2 * v943 + 1] = v334;
            v346[2 * v943] = v862 - (v337 + v842) + 2;
            v319 = v943 + 1;
            v891 = v334;
            ++v943;
            if ( v334 <= v832 - (v337 + v842) )
              v269 = v889;
            v832 = v269;
            if ( v334 > 0x1000 || v334 + v887 == v10 )
              break;
          }
          if ( v337 > v818 )
          {
            v347 = v340[v334];
            v348 = *(_BYTE *)(v334 + v887);
            if ( v347 >= v348 )
            {
              v337 = *v854;
              v336 = v334;
              v827 = v334;
            }
            else
            {
              v337 = v854[1];
              v336 = v827;
            }
            v278 = v888;
            v104 = v347 < v348;
            v338 = v904;
            if ( !v104 )
              v334 = (unsigned __int64)v897;
            if ( v888 )
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
        v14 = v887;
LABEL_1010:
        v887 = ++v14;
        goto LABEL_1011;
      }
      v349 = v914;
      v350 = v899;
      v351 = v919;
      v352 = v919;
      v914[4] = *a3;
      v349[5] = a3[1];
      v349[6] = a3[2];
      v349[2] = 0;
      v349[3] = v350;
      v353 = ZSTD_literalsContribution(v942, v350, v352, 0);
      v354 = v914;
      v355 = v901;
      *v914 = v353;
      if ( v355[2 * v105 - 1] > v921 )
      {
        *(_QWORD *)((char *)&v925 + 4) = *(_QWORD *)&v355[2 * v105 - 2];
        HIDWORD(v925) = v350;
        goto LABEL_448;
      }
      ZSTD_litLengthPrice(0, v351, 0);
      v375 = v918;
      v376 = v918 + 1;
      v377 = v914 + 7;
      do
      {
        *v377 = 0x40000000;
        v377 += 7;
        --v375;
      }
      while ( v375 );
      v378 = v893;
      v379 = v355;
      v891 = v105;
      v944 = v355;
      do
      {
        v380 = *v379;
        v381 = v379[1];
        updated = ZSTD_updateRep(v937, a3, *v379, v378);
        v385 = *(_QWORD *)updated;
        v386 = *(_DWORD *)(updated + 8);
        if ( v376 > v381 )
        {
          v397 = v914;
        }
        else
        {
          v387 = v919;
          do
          {
            _BitScanReverse((unsigned int *)&v388, v380 + 1);
            v389 = v376 - 3;
            if ( *(_DWORD *)(v387 + 80) == 1 )
            {
              _BitScanReverse(&v390, v376 - 2);
              v391 = v384 + ((v390 + (_DWORD)v388 + 16) << 8);
            }
            else
            {
              _BitScanReverse(&v392, *(_DWORD *)(*(_QWORD *)(v387 + 24) + 4 * v388) + 1);
              v393 = *(_DWORD *)(v387 + 76) + (((_DWORD)v388 - v392) << 8);
              if ( (unsigned int)v388 >= 0x14 )
                v393 = ((_DWORD)v388 << 9) + v393 - 9728;
              if ( (unsigned int)v389 <= 0x7F )
              {
                _mm_lfence();
                v395 = *((unsigned __int8 *)&qword_1803EF770[8] + v389);
              }
              else
              {
                _BitScanReverse(&v394, v389);
                v395 = v394 + 36;
              }
              v396 = 4 * v395;
              _BitScanReverse((unsigned int *)&v395, *(_DWORD *)(*(_QWORD *)(v387 + 16) + 4 * v395) + 1);
              v391 = v384
                   + *(_DWORD *)(v387 + 72)
                   + ((*(_DWORD *)((char *)&qword_1803EF640[10] + v396) - (_DWORD)v395) << 8)
                   + v393
                   + 51;
            }
            v397 = v914;
            v398 = 7LL * v376;
            v399 = v899;
            v914[v398 + 2] = v376++;
            *(_QWORD *)&v397[v398 + 4] = v385;
            v397[v398 + 1] = v380;
            v397[v398 + 3] = v399;
            v397[v398] = v391;
            v397[v398 + 6] = v386;
          }
          while ( v376 <= v381 );
          v379 = v944;
          v383 = v891;
          v378 = v893;
        }
        v379 += 2;
        v944 = v379;
        v891 = v383 - 1;
      }
      while ( v383 != 1 );
      v10 = v913;
      v400 = v919;
      v401 = v376 - 1;
      v402 = 1;
      v863 = v401;
      v868 = 1;
      if ( !v401 )
      {
LABEL_985:
        v793 = &v397[7 * v401];
        v794 = *(_OWORD *)v793;
        v920 = v793[6];
        v15 = *((_QWORD *)v793 + 2);
        v925 = v794;
        v930 = v920;
        v928 = v794;
        v929 = v15;
        if ( v401 <= (unsigned int)((__int64 (__fastcall *)(__int128 *))ZSTD_totalLen)(&v928) )
        {
LABEL_448:
          v356 = 0;
          v357 = 0;
        }
        else
        {
          v933 = *(_DWORD *)(v795 + 24);
          v931 = v794;
          v932 = v15;
          v357 = v401 - ((__int64 (__fastcall *)(__int128 *))ZSTD_totalLen)(&v931);
          v356 = 0;
        }
        goto LABEL_449;
      }
      while ( 2 )
      {
        v403 = v887 + v402;
        v828 = v403;
        v404 = &v397[7 * v402 - 7];
        if ( v404[2] )
          v405 = 1;
        else
          v405 = v404[3] + 1;
        v406 = *v404 - ZSTD_litLengthPrice(v405 - 1, v400, 0);
        v407 = ZSTD_rawLiteralsCost(v403 - 1, 1, v400) + v406;
        v408 = v407 + ZSTD_litLengthPrice(v405, v400, 0);
        v397 = v914;
        v410 = &v914[7 * v868];
        v411 = *v410;
        if ( v408 <= *v410 )
        {
          v412 = *((_QWORD *)v404 + 2);
          v411 = v408;
          *v410 = v408;
          v413 = v404[6];
          *((_QWORD *)v410 + 2) = v412;
          v410[6] = v413;
          *(_QWORD *)(v410 + 1) = 0;
          v410[3] = v405;
        }
        if ( v403 > v10 - 8 )
          goto LABEL_976;
        if ( v868 == v401 )
          goto LABEL_985;
        if ( v397[7 * v868 + 7] <= v411 + 128 )
          goto LABEL_976;
        v414 = v410[2];
        v893 = v414 != 0;
        if ( v414 )
          v900 = 0;
        else
          v900 = v410[3];
        v415 = ZSTD_litLengthPrice(0, v919, v409);
        v416 = a1;
        v417 = v403;
        v903 = v411 + v415;
        v891 = (unsigned __int64)(v410 + 4);
        v418 = *(unsigned int *)(a1 + 36);
        v419 = *(_QWORD *)(a1 + 8);
        v420 = *(_DWORD *)(a1 + 200);
        if ( v403 < v419 + v418 )
          goto LABEL_975;
        v421 = v403 - v419;
        if ( (unsigned int)v418 < (int)v403 - (int)v419 )
        {
          do
            LODWORD(v418) = ZSTD_insertBt1(a1, (int)v419 + (int)v418, v10, v420, 0) + v418;
          while ( (unsigned int)v418 < v421 );
          v401 = v863;
          v417 = v403;
          v416 = a1;
        }
        v422 = *(_QWORD *)(v416 + 8);
        v423 = 4095;
        v424 = *(_QWORD *)(v416 + 48);
        *(_DWORD *)(v416 + 36) = v421;
        v425 = *(unsigned int *)(v416 + 192);
        if ( v420 == 3 )
        {
          v668 = *(_DWORD *)(v416 + 204);
          v906 = v422;
          if ( v668 < 0xFFF )
            v423 = v668;
          v846 = v417 - v422;
          LODWORD(v912) = v423;
          v669 = ZSTD_hash4Ptr(v417, v425, v424);
          v673 = *(_DWORD *)(v672 + 4 * v669);
          v675 = *(_QWORD *)(v674 + 64);
          v676 = *(_DWORD *)(v674 + 188) - 1;
          v915 = v672 + 4 * v669;
          LODWORD(v674) = 1 << v676;
          v677 = 0;
          v678 = v674 - 1;
          v902 = 0;
          v916 = 0;
          v679 = *(unsigned int *)(a1 + 24);
          v905 = v678;
          v923 = v675;
          v909 = v679;
          v945 = 0;
          v897 = (_DWORD *)(v679 + v422);
          if ( v678 < v670 )
            v677 = v670 - v678;
          v894 = v677;
          v680 = 1 << *(_DWORD *)(a1 + 184);
          v681 = v670 - v680;
          v682 = 1;
          if ( v670 - *(_DWORD *)(a1 + 28) <= v680 )
            v681 = *(_DWORD *)(a1 + 28);
          if ( *(_DWORD *)(a1 + 32) )
            v681 = *(_DWORD *)(a1 + 28);
          v683 = *(_DWORD *)(a1 + 196);
          if ( v681 )
            v682 = v681;
          v838 = v682;
          v890 = (unsigned int *)(v675 + 8LL * (v670 & v678));
          v896 = (__int64 *)(v890 + 1);
          v819 = v670 + 9;
          v876 = 1 << v683;
          v924 = *(_QWORD *)(a1 + 176);
          v684 = *(_QWORD *)v924;
          v685 = *(_QWORD *)v924 - *(_QWORD *)(v924 + 8);
          v904 = *(_QWORD *)(v924 + 8);
          v686 = *(_DWORD *)(v924 + 28);
          v898 = v684;
          LODWORD(v684) = *(_DWORD *)(v924 + 192);
          v687 = *(_DWORD *)(v924 + 188);
          v899 = v681 - v685;
          v888 = v685;
          v892 = v686;
          v910 = v684;
          v889 = (1 << (v687 - 1)) - 1;
          v688 = v685 - v889;
          v858 = v918;
          if ( v889 >= v685 - v686 )
            v688 = v686;
          v895 = v688;
          v689 = (_DWORD *)v891;
          v690 = v670 - v679;
          v691 = v893;
          v911 = v670 - v679;
          v692 = v893 + 3;
          v886 = v893 + 3;
          v693 = (unsigned int *)(v891 + 4LL * v893);
          while ( 1 )
          {
            if ( v691 == 3 )
              v694 = *v689 - 1;
            else
              v694 = *v693;
            v695 = v670 - v694;
            v696 = 0;
            if ( v694 - 1 >= v690 )
            {
              if ( v694 - 1 >= v846 - v899 - v892
                || (unsigned int)v679 - v695 - 1 < 3
                || (v711 = (unsigned int)(*(_DWORD *)(v904 + v695 - (unsigned __int64)v899) << 8),
                    LODWORD(v908) = 1,
                    v712 = ZSTD_readMINMATCH(v828, 3, v711, 0),
                    v712 != v716) )
              {
                v671 = v828;
                goto LABEL_859;
              }
              v717 = v714 + 3;
              v718 = v713 + v715;
              v719 = v10;
              v720 = v714 + 3 - v718 + v898;
              if ( v720 < v10 )
                v719 = v720;
              v721 = ZSTD_count(v717, v718, v719);
              v722 = v721;
              if ( v721 + v723 == v898 )
                v722 = ZSTD_count(v721 + v717, v897, v10) + v721;
              v671 = v828;
              v696 = (unsigned int)(v722 + 3);
              v423 = v912;
              LODWORD(v679) = v909;
            }
            else
            {
              LODWORD(v907) = 1;
              v697 = ZSTD_readMINMATCH(v671, 3, (unsigned int)(*(_DWORD *)(v671 - v694) << 8), 0);
              if ( v697 == v699 )
              {
                v700 = (_QWORD *)(v671 + 3);
                v701 = v671 + 3;
                v702 = (_QWORD *)(v671 + v698 + 3);
                v703 = v10 - 7;
                if ( v671 + 3 < v10 - 7 )
                {
                  if ( *v702 != *v700 )
                  {
                    v704 = ZSTD_NbCommonBytes(*v702 ^ *v700, v700, v702, v701);
LABEL_857:
                    v696 = (unsigned int)(v704 + 3);
                    goto LABEL_858;
                  }
                  v700 = (_QWORD *)(v671 + 11);
                  ++v702;
                  if ( v671 + 11 < v703 )
                  {
                    while ( *v702 == *v700 )
                    {
                      ++v700;
                      ++v702;
                      if ( (unsigned __int64)v700 >= v703 )
                        goto LABEL_847;
                    }
                    v708 = ZSTD_NbCommonBytes(*v702 ^ *v700, v700, v702, v701);
                    v704 = v709 - v710 + v708;
                    goto LABEL_857;
                  }
                }
LABEL_847:
                if ( (unsigned __int64)v700 < v10 - 3 && *(_DWORD *)v702 == *(_DWORD *)v700 )
                {
                  v700 = (_QWORD *)((char *)v700 + 4);
                  v702 = (_QWORD *)((char *)v702 + 4);
                }
                if ( (unsigned __int64)v700 < v10 - 1 && *(_WORD *)v702 == *(_WORD *)v700 )
                {
                  v700 = (_QWORD *)((char *)v700 + 2);
                  v702 = (_QWORD *)((char *)v702 + 2);
                }
                if ( (unsigned __int64)v700 < v10 && *(_BYTE *)v702 == *(_BYTE *)v700 )
                  LODWORD(v700) = (_DWORD)v700 + 1;
                v704 = (_DWORD)v700 - v701;
                goto LABEL_857;
              }
            }
LABEL_858:
            v692 = v886;
LABEL_859:
            v705 = v858;
            if ( (unsigned int)v696 > v858 )
            {
              v706 = v945;
              v705 = (unsigned int)v696;
              ++v945;
              v707 = &v901[2 * v706];
              v707[1] = v696;
              *v707 = v691 - v893;
              v858 = (unsigned int)v696;
              if ( (unsigned int)v696 > v423 || v696 + v671 == v10 )
                goto LABEL_947;
            }
            ++v691;
            ++v693;
            if ( v691 >= v692 )
            {
              if ( v705 >= 3 )
              {
                v727 = v828;
                v725 = v846;
LABEL_878:
                v732 = v945;
                goto LABEL_879;
              }
              v724 = ZSTD_insertAndFindFirstIndexHash3(a1, &v922, v671);
              v725 = v846;
              v726 = v838;
              v727 = v828;
              if ( v724 < v838 || v846 - v724 >= 0x40000 )
              {
                v732 = v945;
                goto LABEL_880;
              }
              v728 = ZSTD_count(v828, v906 + v724, v10);
              if ( v728 < 3 )
                goto LABEL_878;
              v730 = v901;
              v731 = v729 + 2;
              v732 = 1;
              v858 = v728;
              v945 = 1;
              *v901 = v731;
              v730[1] = v728;
              if ( v728 > v423 || v728 + v828 == v10 )
              {
                v945 = 1;
                *(_DWORD *)(a1 + 36) = v846 + 1;
                goto LABEL_947;
              }
LABEL_879:
              v726 = v838;
LABEL_880:
              v733 = v876;
              *(_DWORD *)v915 = v725;
              if ( !v876 )
              {
LABEL_918:
                --v733;
LABEL_919:
                v746 = v890;
LABEL_920:
                *(_DWORD *)v896 = 0;
                *v746 = 0;
                if ( v733 )
                {
                  v747 = ZSTD_hash4Ptr(v727, v910, v726);
                  v749 = v748;
                  v750 = v748;
                  v751 = *(_DWORD *)(*(_QWORD *)(v924 + 48) + 4 * v747);
                  v752 = *(_QWORD *)(v924 + 64);
                  v923 = v752;
                  while ( 1 )
                  {
                    v924 = v750;
                    LODWORD(v912) = v819;
                    if ( v751 <= v892 )
                      break;
                    v753 = v749;
                    if ( v750 < v749 )
                      v753 = v750;
                    v754 = v751 + v904;
                    v755 = v913;
                    v902 = v752 + 8LL * (v889 & v751);
                    if ( v828 - v754 + v898 < v913 )
                      v755 = v828 - v754 + v898;
                    v756 = ZSTD_count(v753 + v828, v754 + v753, v755);
                    v757 = v756;
                    v10 = v913;
                    if ( v756 + v758 == v898 )
                      v757 = ZSTD_count(v756 + v753 + v828, v897, v913) + v756;
                    v750 = v757 + v753;
                    v759 = v899;
                    if ( v757 + v753 + v751 >= v888 )
                      v754 = v906 + v899 + (unsigned __int64)v751;
                    if ( v750 <= v858 )
                    {
                      v732 = v945;
                    }
                    else
                    {
                      v760 = v901;
                      v901[2 * v945 + 1] = v750;
                      v760[2 * v945] = v846 - (v751 + v759) + 2;
                      v761 = v750 + v751 + v759;
                      v858 = v757 + v753;
                      v732 = ++v945;
                      if ( v750 <= v819 - (v751 + v759) )
                        v761 = v912;
                      v819 = v761;
                      if ( v750 > 0x1000 || v750 + v828 == v10 )
                        break;
                    }
                    if ( v751 > v895 )
                    {
                      v762 = *(_BYTE *)(v754 + v750);
                      v763 = *(_BYTE *)(v750 + v828);
                      if ( v762 >= v763 )
                      {
                        v751 = *(_DWORD *)v902;
                        v749 = v757 + v753;
                      }
                      else
                      {
                        v751 = *(_DWORD *)(v902 + 4);
                      }
                      v877 = --v733;
                      v104 = v762 < v763;
                      v752 = v923;
                      if ( !v104 )
                        v750 = v924;
                      if ( v877 )
                        continue;
                    }
                    break;
                  }
                  v401 = v863;
                }
                v945 = v732;
                goto LABEL_946;
              }
              v734 = v819;
              while ( 2 )
              {
                --v733;
                if ( v673 < (unsigned int)v726 )
                  goto LABEL_919;
                v735 = (unsigned int *)(v923 + 8LL * (v673 & v905));
                v736 = v10 - 7;
                v737 = v916;
                if ( v902 < v916 )
                  v737 = v902;
                v738 = v906 + v673;
                v739 = (_QWORD *)(v737 + v727);
                v726 = v738 + v737;
                if ( v737 + v727 < v736 )
                {
                  if ( *(_QWORD *)v726 != *v739 )
                  {
                    v740 = (unsigned int)ZSTD_NbCommonBytes(*(_QWORD *)v726 ^ *v739, v739, v726, v737);
LABEL_902:
                    v741 = v740 + v737;
                    if ( v741 <= v858 )
                    {
                      v732 = v945;
                    }
                    else
                    {
                      if ( v741 > v734 - v673 )
                      {
                        v819 = v741 + v673;
                        v734 = v741 + v673;
                      }
                      v742 = v901;
                      v901[2 * v945 + 1] = v741;
                      v742[2 * v945] = v846 - v673 + 2;
                      v732 = v945 + 1;
                      v858 = v741;
                      ++v945;
                      if ( v741 > 0x1000 || v741 + v727 == v10 )
                      {
                        v733 = 0;
                        goto LABEL_919;
                      }
                    }
                    if ( *(_BYTE *)(v738 + v741) >= *(_BYTE *)(v741 + v727) )
                    {
                      v916 = v741;
                      *(_DWORD *)v896 = v673;
                      if ( v673 <= v894 )
                      {
                        v896 = (__int64 *)&v911;
                        goto LABEL_919;
                      }
                      v673 = *v735;
                      v896 = (__int64 *)v735;
                    }
                    else
                    {
                      v902 = v741;
                      *v890 = v673;
                      if ( v673 <= v894 )
                      {
                        v746 = &v911;
                        goto LABEL_920;
                      }
                      v673 = v735[1];
                      v890 = v735 + 1;
                    }
                    if ( !v733 )
                      goto LABEL_918;
                    v726 = v838;
                    continue;
                  }
                  ++v739;
                  v726 += 8LL;
                  if ( (unsigned __int64)v739 < v736 )
                  {
                    while ( *(_QWORD *)v726 == *v739 )
                    {
                      ++v739;
                      v726 += 8LL;
                      if ( (unsigned __int64)v739 >= v736 )
                        goto LABEL_892;
                    }
                    v743 = ZSTD_NbCommonBytes(*(_QWORD *)v726 ^ *v739, v739, v726, v737);
                    v740 = v744 - v745 + v743;
                    goto LABEL_902;
                  }
                }
                break;
              }
LABEL_892:
              if ( (unsigned __int64)v739 < v10 - 3 && *(_DWORD *)v726 == *(_DWORD *)v739 )
              {
                v739 = (_QWORD *)((char *)v739 + 4);
                v726 += 4LL;
              }
              if ( (unsigned __int64)v739 < v10 - 1 && *(_WORD *)v726 == *(_WORD *)v739 )
              {
                v739 = (_QWORD *)((char *)v739 + 2);
                v726 += 2LL;
              }
              if ( (unsigned __int64)v739 < v10 && *(_BYTE *)v726 == *(_BYTE *)v739 )
                v739 = (_QWORD *)((char *)v739 + 1);
              v740 = (unsigned __int64)v739 - v737 - v727;
              goto LABEL_902;
            }
            v690 = v911;
            v670 = v846;
            v689 = (_DWORD *)v891;
          }
        }
        if ( v420 == 5 )
        {
          v587 = *(_DWORD *)(v416 + 204);
          v916 = v422;
          if ( v587 < 0xFFF )
            v423 = v587;
          v845 = v417 - v422;
          v909 = v423;
          v588 = ZSTD_hash5Ptr(v417, v425, v424);
          v592 = *(_DWORD *)(v591 + 4 * v588);
          v594 = *(_DWORD **)(v593 + 64);
          v595 = *(_DWORD *)(v593 + 188) - 1;
          v915 = v591 + 4 * v588;
          LODWORD(v593) = 1 << v595;
          v596 = 0;
          v597 = v593 - 1;
          v902 = 0;
          v908 = 0;
          v598 = *(unsigned int *)(a1 + 24);
          v889 = v597;
          v897 = v594;
          v911 = v598;
          v945 = 0;
          v906 = v598 + v422;
          if ( v597 < v589 )
            v596 = v589 - v597;
          v875 = v596;
          v599 = 1 << *(_DWORD *)(a1 + 184);
          v600 = v589 - v599;
          v601 = 1;
          if ( v589 - *(_DWORD *)(a1 + 28) <= v599 )
            v600 = *(_DWORD *)(a1 + 28);
          if ( *(_DWORD *)(a1 + 32) )
            v600 = *(_DWORD *)(a1 + 28);
          v602 = *(_DWORD *)(a1 + 196);
          if ( v600 )
            v601 = v600;
          v910 = v601;
          v890 = &v594[2 * (v589 & v597)];
          v896 = (__int64 *)(v890 + 1);
          v819 = v589 + 9;
          v836 = 1 << v602;
          v904 = *(_QWORD *)(a1 + 176);
          v603 = *(_QWORD *)v904;
          v604 = *(_QWORD *)v904 - *(_QWORD *)(v904 + 8);
          v907 = *(_QWORD *)(v904 + 8);
          v605 = *(_DWORD *)(v904 + 28);
          v898 = v603;
          LODWORD(v603) = *(_DWORD *)(v904 + 192);
          v606 = *(_DWORD *)(v904 + 188);
          v885 = v600 - v604;
          v892 = v604;
          v899 = v605;
          v888 = v603;
          v895 = (1 << (v606 - 1)) - 1;
          v607 = v604 - v895;
          v857 = v918;
          if ( v895 >= v604 - v605 )
            v607 = v605;
          v894 = v607;
          v608 = (_DWORD *)v891;
          v609 = v589 - v598;
          v610 = v893;
          v905 = v589 - v598;
          v611 = v893 + 3;
          LODWORD(v912) = v893 + 3;
          v612 = (unsigned int *)(v891 + 4LL * v893);
          while ( 1 )
          {
            if ( v610 == 3 )
              v613 = *v608 - 1;
            else
              v613 = *v612;
            v614 = v589 - v613;
            v615 = 0;
            if ( v613 - 1 >= v609 )
            {
              if ( v613 - 1 < v845 - v885 - v899 && (unsigned int)(v598 - v614 - 1) >= 3 )
              {
                v625 = ZSTD_readMINMATCH(v828, 4, 0, v614);
                if ( v625 == *v628 )
                {
                  v629 = v627 + 4;
                  v630 = (char *)v628 + v626;
                  v631 = v10;
                  v632 = v627 + 4 - (_QWORD)v630 + v898;
                  if ( v632 < v10 )
                    v631 = v632;
                  v633 = ZSTD_count(v629, v630, v631);
                  v634 = v633;
                  if ( v633 + v635 == v898 )
                    v634 = ZSTD_count(v633 + v629, v906, v10) + v633;
                  v611 = v912;
                  v615 = (unsigned int)(v634 + 4);
                  v423 = v909;
                  LODWORD(v598) = v911;
                }
              }
              v590 = v828;
            }
            else
            {
              v616 = ZSTD_readMINMATCH(v590, 4, 0, -(__int64)v613);
              if ( v616 == *(_DWORD *)(v617 + v590) )
              {
                v618 = (_QWORD *)(v590 + 4);
                v619 = (_QWORD *)(v590 + v617 + 4);
                v620 = v10 - 7;
                v621 = v590 + 4;
                if ( v590 + 4 >= v10 - 7 )
                  goto LABEL_738;
                if ( *v619 != *v618 )
                {
                  v615 = (unsigned int)ZSTD_NbCommonBytes(*v619 ^ *v618, v618, v619, v621) + 4;
                  goto LABEL_757;
                }
                v618 = (_QWORD *)(v590 + 12);
                ++v619;
                if ( v590 + 12 >= v620 )
                {
LABEL_738:
                  if ( (unsigned __int64)v618 < v10 - 3 && *(_DWORD *)v619 == *(_DWORD *)v618 )
                  {
                    v618 = (_QWORD *)((char *)v618 + 4);
                    v619 = (_QWORD *)((char *)v619 + 4);
                  }
                  if ( (unsigned __int64)v618 < v10 - 1 && *(_WORD *)v619 == *(_WORD *)v618 )
                  {
                    v618 = (_QWORD *)((char *)v618 + 2);
                    v619 = (_QWORD *)((char *)v619 + 2);
                  }
                  if ( (unsigned __int64)v618 < v10 && *(_BYTE *)v619 == *(_BYTE *)v618 )
                    LODWORD(v618) = (_DWORD)v618 + 1;
                  v615 = (unsigned int)((_DWORD)v618 - v590);
                }
                else
                {
                  while ( *v619 == *v618 )
                  {
                    ++v618;
                    ++v619;
                    if ( (unsigned __int64)v618 >= v620 )
                      goto LABEL_738;
                  }
                  v622 = ZSTD_NbCommonBytes(*v619 ^ *v618, v618, v619, v621);
                  v615 = (unsigned int)(v623 - v624 + v622 + 4);
                }
              }
            }
LABEL_757:
            if ( (unsigned int)v615 > v857 )
            {
              v636 = &v901[2 * v945];
              *v636 = v610 - v893;
              v636[1] = v615;
              v857 = (unsigned int)v615;
              ++v945;
              if ( (unsigned int)v615 > v423 || v590 + v615 == v10 )
                goto LABEL_947;
            }
            v609 = v905;
            ++v610;
            v608 = (_DWORD *)v891;
            ++v612;
            if ( v610 >= v611 )
            {
              v637 = v836;
              *(_DWORD *)v915 = v845;
              if ( !v836 )
              {
LABEL_794:
                --v637;
LABEL_795:
                v652 = v890;
LABEL_796:
                *(_DWORD *)v896 = 0;
                *v652 = 0;
                if ( !v637 )
                  goto LABEL_946;
                v653 = ZSTD_hash5Ptr(v590, v888, v615);
                v654 = 0;
                v655 = 0;
                v656 = *(_DWORD *)(*(_QWORD *)(v904 + 48) + 4 * v653);
                v657 = *(_DWORD **)(v904 + 64);
                v897 = v657;
                while ( 1 )
                {
                  v915 = v655;
                  LODWORD(v912) = v819;
                  v837 = v637 - 1;
                  if ( v656 <= v899 )
                    goto LABEL_602;
                  v658 = v654;
                  if ( v655 < v654 )
                    v658 = v655;
                  v659 = v656 + v907;
                  v660 = v913;
                  v902 = (unsigned __int64)&v657[2 * (v895 & v656)];
                  if ( v828 - v659 + v898 < v913 )
                    v660 = v828 - v659 + v898;
                  v661 = ZSTD_count(v658 + v828, v659 + v658, v660);
                  v662 = v661;
                  v10 = v913;
                  if ( v661 + v663 == v898 )
                    v662 = ZSTD_count(v661 + v658 + v828, v906, v913) + v661;
                  v655 = v662 + v658;
                  if ( v662 + v658 + v656 >= v892 )
                    v659 = v916 + v885 + (unsigned __int64)v656;
                  if ( v655 > v857 )
                  {
                    v664 = v901;
                    v901[2 * v945 + 1] = v655;
                    v664[2 * v945] = v845 - (v656 + v885) + 2;
                    v665 = v655 + v656 + v885;
                    v857 = v662 + v658;
                    ++v945;
                    if ( v655 <= v819 - (v656 + v885) )
                      v665 = v912;
                    v819 = v665;
                    if ( v655 > 0x1000 || v655 + v828 == v10 )
                      goto LABEL_602;
                  }
                  if ( v656 <= v894 )
                    goto LABEL_602;
                  v666 = *(_BYTE *)(v659 + v655);
                  v667 = *(_BYTE *)(v655 + v828);
                  if ( v666 >= v667 )
                  {
                    v656 = *(_DWORD *)v902;
                    v654 = v662 + v658;
                  }
                  else
                  {
                    v656 = *(_DWORD *)(v902 + 4);
                  }
                  v637 = v837;
                  v104 = v666 < v667;
                  v657 = v897;
                  if ( !v104 )
                    v655 = v915;
                  if ( !v837 )
                  {
                    v401 = v863;
                    goto LABEL_946;
                  }
                }
              }
              v638 = v819;
              v639 = v857;
              while ( 2 )
              {
                --v637;
                if ( v592 < v910 )
                  goto LABEL_795;
                v640 = &v897[2 * (v592 & v889)];
                v641 = v10 - 7;
                v642 = v908;
                if ( v902 < v908 )
                  v642 = v902;
                v643 = v916 + v592;
                v644 = (_QWORD *)(v642 + v590);
                v615 = v643 + v642;
                v645 = (char *)v644;
                if ( (unsigned __int64)v644 < v641 )
                {
                  if ( *(_QWORD *)v615 != *v644 )
                  {
                    v646 = (unsigned int)ZSTD_NbCommonBytes(*(_QWORD *)v615 ^ *v644, v644, v615, v642);
LABEL_781:
                    v647 = v646 + v642;
                    if ( v647 <= v639 )
                    {
                      v590 = v828;
                    }
                    else
                    {
                      if ( v647 > v638 - v592 )
                      {
                        v819 = v647 + v592;
                        v638 = v647 + v592;
                      }
                      v590 = v828;
                      v648 = &v901[2 * v945];
                      v648[1] = v647;
                      *v648 = v845 - v592 + 2;
                      ++v945;
                      v857 = v647;
                      if ( v647 > 0x1000 || v647 + v828 == v10 )
                      {
                        v637 = 0;
                        goto LABEL_795;
                      }
                      v639 = v647;
                    }
                    if ( *(_BYTE *)(v643 + v647) >= *(_BYTE *)(v647 + v590) )
                    {
                      v908 = v647;
                      *(_DWORD *)v896 = v592;
                      if ( v592 <= v875 )
                      {
                        v896 = (__int64 *)&v909;
                        goto LABEL_795;
                      }
                      v592 = *v640;
                      v896 = (__int64 *)v640;
                    }
                    else
                    {
                      v902 = v647;
                      *v890 = v592;
                      if ( v592 <= v875 )
                      {
                        v652 = &v909;
                        goto LABEL_796;
                      }
                      v592 = v640[1];
                      v890 = v640 + 1;
                    }
                    if ( !v637 )
                      goto LABEL_794;
                    continue;
                  }
                  ++v644;
                  v615 += 8LL;
                  if ( (unsigned __int64)v644 < v641 )
                  {
                    while ( *(_QWORD *)v615 == *v644 )
                    {
                      ++v644;
                      v615 += 8LL;
                      if ( (unsigned __int64)v644 >= v641 )
                        goto LABEL_771;
                    }
                    v649 = ZSTD_NbCommonBytes(*(_QWORD *)v615 ^ *v644, v644, v615, v642);
                    v646 = v650 - v651 + v649;
                    goto LABEL_781;
                  }
                }
                break;
              }
LABEL_771:
              if ( (unsigned __int64)v644 < v10 - 3 && *(_DWORD *)v615 == *(_DWORD *)v644 )
              {
                v644 = (_QWORD *)((char *)v644 + 4);
                v615 += 4LL;
              }
              if ( (unsigned __int64)v644 < v10 - 1 && *(_WORD *)v615 == *(_WORD *)v644 )
              {
                v644 = (_QWORD *)((char *)v644 + 2);
                v615 += 2LL;
              }
              if ( (unsigned __int64)v644 < v10 && *(_BYTE *)v615 == *(_BYTE *)v644 )
                v644 = (_QWORD *)((char *)v644 + 1);
              v646 = (char *)v644 - v645;
              goto LABEL_781;
            }
            v589 = v845;
          }
        }
        v426 = *(_DWORD *)(v416 + 204);
        if ( (unsigned int)(v420 - 6) > 1 )
        {
          v916 = v422;
          if ( v426 < 0xFFF )
            v423 = v426;
          v844 = v417 - v422;
          v909 = v423;
          v507 = ZSTD_hash4Ptr(v417, v425, v424);
          v511 = *(_DWORD *)(v510 + 4 * v507);
          v513 = *(_DWORD **)(v512 + 64);
          v514 = *(_DWORD *)(v512 + 188) - 1;
          v915 = v510 + 4 * v507;
          LODWORD(v512) = 1 << v514;
          v515 = 0;
          v516 = v512 - 1;
          v902 = 0;
          v908 = 0;
          v517 = *(unsigned int *)(a1 + 24);
          v889 = v516;
          v897 = v513;
          v911 = v517;
          v945 = 0;
          v906 = v517 + v422;
          if ( v516 < v508 )
            v515 = v508 - v516;
          v874 = v515;
          v518 = 1 << *(_DWORD *)(a1 + 184);
          v519 = v508 - v518;
          v520 = 1;
          if ( v508 - *(_DWORD *)(a1 + 28) <= v518 )
            v519 = *(_DWORD *)(a1 + 28);
          if ( *(_DWORD *)(a1 + 32) )
            v519 = *(_DWORD *)(a1 + 28);
          v521 = *(_DWORD *)(a1 + 196);
          if ( v519 )
            v520 = v519;
          v910 = v520;
          v890 = &v513[2 * (v508 & v516)];
          v896 = (__int64 *)(v890 + 1);
          v819 = v508 + 9;
          v834 = 1 << v521;
          v904 = *(_QWORD *)(a1 + 176);
          v522 = *(_QWORD *)v904;
          v523 = *(_QWORD *)v904 - *(_QWORD *)(v904 + 8);
          v907 = *(_QWORD *)(v904 + 8);
          v524 = *(_DWORD *)(v904 + 28);
          v884 = v519 - v523;
          v898 = v522;
          LODWORD(v522) = *(_DWORD *)(v904 + 192);
          v525 = *(_DWORD *)(v904 + 188) - 1;
          v892 = v523;
          v899 = v524;
          v888 = v522;
          v895 = (1 << v525) - 1;
          v526 = v523 - v895;
          v856 = v918;
          if ( v895 >= v523 - v524 )
            v526 = v524;
          v894 = v526;
          v527 = (_DWORD *)v891;
          v528 = v508 - v517;
          v529 = v893;
          v905 = v508 - v517;
          v530 = v893 + 3;
          LODWORD(v912) = v893 + 3;
          v531 = (unsigned int *)(v891 + 4LL * v893);
          while ( 1 )
          {
            if ( v529 == 3 )
              v532 = *v527 - 1;
            else
              v532 = *v531;
            v533 = v508 - v532;
            v534 = 0;
            if ( v532 - 1 >= v528 )
            {
              if ( v532 - 1 < v844 - v884 - v899 && (unsigned int)(v517 - v533 - 1) >= 3 )
              {
                v544 = ZSTD_readMINMATCH(v828, 4, 0, v533);
                if ( v544 == *v547 )
                {
                  v548 = v546 + 4;
                  v549 = (char *)v547 + v545;
                  v104 = v546 + 4 + v898 - (unsigned __int64)v549 < v10;
                  v550 = v10;
                  v551 = v546 + 4;
                  if ( v104 )
                    v550 = v548 + v898 - (_QWORD)v549;
                  v552 = ZSTD_count(v551, v549, v550);
                  v553 = v552;
                  if ( v552 + v554 == v898 )
                    v553 = ZSTD_count(v552 + v548, v906, v10) + v552;
                  v530 = v912;
                  v534 = (unsigned int)(v553 + 4);
                  v423 = v909;
                  LODWORD(v517) = v911;
                }
              }
              v509 = v828;
            }
            else
            {
              v535 = ZSTD_readMINMATCH(v509, 4, 0, -(__int64)v532);
              if ( v535 == *(_DWORD *)(v536 + v509) )
              {
                v537 = (_QWORD *)(v509 + 4);
                v538 = (_QWORD *)(v509 + v536 + 4);
                v539 = v10 - 7;
                v540 = v509 + 4;
                if ( v509 + 4 >= v10 - 7 )
                  goto LABEL_628;
                if ( *v538 != *v537 )
                {
                  v534 = (unsigned int)ZSTD_NbCommonBytes(*v538 ^ *v537, v537, v538, v540) + 4;
                  goto LABEL_647;
                }
                v537 = (_QWORD *)(v509 + 12);
                ++v538;
                if ( v509 + 12 >= v539 )
                {
LABEL_628:
                  if ( (unsigned __int64)v537 < v10 - 3 && *(_DWORD *)v538 == *(_DWORD *)v537 )
                  {
                    v537 = (_QWORD *)((char *)v537 + 4);
                    v538 = (_QWORD *)((char *)v538 + 4);
                  }
                  if ( (unsigned __int64)v537 < v10 - 1 && *(_WORD *)v538 == *(_WORD *)v537 )
                  {
                    v537 = (_QWORD *)((char *)v537 + 2);
                    v538 = (_QWORD *)((char *)v538 + 2);
                  }
                  if ( (unsigned __int64)v537 < v10 && *(_BYTE *)v538 == *(_BYTE *)v537 )
                    LODWORD(v537) = (_DWORD)v537 + 1;
                  v534 = (unsigned int)((_DWORD)v537 - v509);
                }
                else
                {
                  while ( *v538 == *v537 )
                  {
                    ++v537;
                    ++v538;
                    if ( (unsigned __int64)v537 >= v539 )
                      goto LABEL_628;
                  }
                  v541 = ZSTD_NbCommonBytes(*v538 ^ *v537, v537, v538, v540);
                  v534 = (unsigned int)(v542 - v543 + v541 + 4);
                }
              }
            }
LABEL_647:
            if ( (unsigned int)v534 > v856 )
            {
              v555 = &v901[2 * v945];
              *v555 = v529 - v893;
              v555[1] = v534;
              v856 = (unsigned int)v534;
              ++v945;
              if ( (unsigned int)v534 > v423 || v534 + v509 == v10 )
                goto LABEL_947;
            }
            v528 = v905;
            ++v529;
            v527 = (_DWORD *)v891;
            ++v531;
            if ( v529 >= v530 )
            {
              v556 = v834;
              *(_DWORD *)v915 = v844;
              if ( v834 )
              {
                v557 = v819;
                v558 = v856;
                do
                {
                  --v556;
                  if ( v511 < v910 )
                    goto LABEL_685;
                  v559 = &v897[2 * (v511 & v889)];
                  v560 = v10 - 7;
                  v561 = v908;
                  if ( v902 < v908 )
                    v561 = v902;
                  v562 = v916 + v511;
                  v563 = (_QWORD *)(v561 + v509);
                  v534 = v562 + v561;
                  v564 = (char *)v563;
                  if ( (unsigned __int64)v563 >= v560 )
                    goto LABEL_661;
                  if ( *(_QWORD *)v534 != *v563 )
                  {
                    v565 = (unsigned int)ZSTD_NbCommonBytes(*(_QWORD *)v534 ^ *v563, v563, v534, v561);
                    goto LABEL_671;
                  }
                  ++v563;
                  v534 += 8LL;
                  if ( (unsigned __int64)v563 >= v560 )
                  {
LABEL_661:
                    if ( (unsigned __int64)v563 < v10 - 3 && *(_DWORD *)v534 == *(_DWORD *)v563 )
                    {
                      v563 = (_QWORD *)((char *)v563 + 4);
                      v534 += 4LL;
                    }
                    if ( (unsigned __int64)v563 < v10 - 1 && *(_WORD *)v534 == *(_WORD *)v563 )
                    {
                      v563 = (_QWORD *)((char *)v563 + 2);
                      v534 += 2LL;
                    }
                    if ( (unsigned __int64)v563 < v10 && *(_BYTE *)v534 == *(_BYTE *)v563 )
                      v563 = (_QWORD *)((char *)v563 + 1);
                    v565 = (char *)v563 - v564;
                  }
                  else
                  {
                    while ( *(_QWORD *)v534 == *v563 )
                    {
                      ++v563;
                      v534 += 8LL;
                      if ( (unsigned __int64)v563 >= v560 )
                        goto LABEL_661;
                    }
                    v568 = ZSTD_NbCommonBytes(*(_QWORD *)v534 ^ *v563, v563, v534, v561);
                    v565 = v569 - v570 + v568;
                  }
LABEL_671:
                  v566 = v565 + v561;
                  if ( v566 <= v558 )
                  {
                    v509 = v828;
                  }
                  else
                  {
                    if ( v566 > v557 - v511 )
                    {
                      v819 = v566 + v511;
                      v557 = v566 + v511;
                    }
                    v509 = v828;
                    v567 = &v901[2 * v945];
                    v567[1] = v566;
                    *v567 = v844 - v511 + 2;
                    ++v945;
                    v856 = v566;
                    if ( v566 > 0x1000 || v566 + v828 == v10 )
                    {
                      v556 = 0;
                      goto LABEL_685;
                    }
                    v558 = v566;
                  }
                  if ( *(_BYTE *)(v562 + v566) >= *(_BYTE *)(v566 + v509) )
                  {
                    v908 = v566;
                    *(_DWORD *)v896 = v511;
                    if ( v511 <= v874 )
                    {
                      v896 = &v912;
                      goto LABEL_685;
                    }
                    v511 = *v559;
                    v896 = (__int64 *)v559;
                  }
                  else
                  {
                    v902 = v566;
                    *v890 = v511;
                    if ( v511 <= v874 )
                    {
                      v571 = &v912;
                      goto LABEL_686;
                    }
                    v511 = v559[1];
                    v890 = v559 + 1;
                  }
                }
                while ( v556 );
              }
              --v556;
LABEL_685:
              v571 = (__int64 *)v890;
LABEL_686:
              *(_DWORD *)v896 = 0;
              *(_DWORD *)v571 = 0;
              if ( !v556 )
                goto LABEL_946;
              v572 = ZSTD_hash4Ptr(v509, v888, v534);
              v573 = 0;
              v574 = 0;
              v575 = *(_DWORD *)(*(_QWORD *)(v904 + 48) + 4 * v572);
              v576 = *(_DWORD **)(v904 + 64);
              v897 = v576;
              while ( 1 )
              {
                v915 = v574;
                LODWORD(v912) = v819;
                v835 = v556 - 1;
                if ( v575 <= v899 )
                  break;
                v577 = v573;
                if ( v574 < v573 )
                  v577 = v574;
                v578 = v575 + v907;
                v579 = v913;
                v902 = (unsigned __int64)&v576[2 * (v895 & v575)];
                if ( v828 + v898 - v578 < v913 )
                  v579 = v828 + v898 - v578;
                v580 = ZSTD_count(v577 + v828, v578 + v577, v579);
                v581 = v580;
                v10 = v913;
                if ( v580 + v582 == v898 )
                  v581 = ZSTD_count(v580 + v577 + v828, v906, v913) + v580;
                v574 = v577 + v581;
                if ( v577 + v581 + v575 >= v892 )
                  v578 = v916 + v884 + (unsigned __int64)v575;
                if ( v574 > v856 )
                {
                  v583 = v901;
                  v901[2 * v945 + 1] = v574;
                  v583[2 * v945] = v844 - (v575 + v884) + 2;
                  v584 = v575 + v884 + v574;
                  v856 = v577 + v581;
                  ++v945;
                  if ( v574 <= v819 - (v575 + v884) )
                    v584 = v912;
                  v819 = v584;
                  if ( v574 > 0x1000 || v574 + v828 == v10 )
                    break;
                }
                if ( v575 <= v894 )
                  break;
                v585 = *(_BYTE *)(v578 + v574);
                v586 = *(_BYTE *)(v574 + v828);
                if ( v585 >= v586 )
                {
                  v575 = *(_DWORD *)v902;
                  v573 = v577 + v581;
                }
                else
                {
                  v575 = *(_DWORD *)(v902 + 4);
                }
                v556 = v835;
                v104 = v585 < v586;
                v576 = v897;
                if ( !v104 )
                  v574 = v915;
                if ( !v835 )
                {
                  v401 = v863;
                  goto LABEL_946;
                }
              }
LABEL_602:
              v401 = v863;
              goto LABEL_946;
            }
            v508 = v844;
          }
        }
        v902 = v422;
        if ( v426 < 0xFFF )
          v423 = v426;
        v843 = v417 - v422;
        v888 = v423;
        v427 = ZSTD_hash6Ptr(v417, v425, v424);
        v431 = *(_DWORD *)(v430 + 4 * v427);
        v433 = *(_QWORD *)(v432 + 64);
        v434 = *(_DWORD *)(v432 + 188) - 1;
        v897 = (_DWORD *)(v430 + 4 * v427);
        LODWORD(v432) = 1 << v434;
        v435 = 0;
        v436 = v432 - 1;
        v908 = 0;
        v907 = 0;
        v437 = *(unsigned int *)(a1 + 24);
        v910 = v436;
        v904 = v433;
        v895 = v437;
        v945 = 0;
        v916 = v437 + v422;
        if ( v436 < v428 )
          v435 = v428 - v436;
        v873 = v435;
        v438 = 1 << *(_DWORD *)(a1 + 184);
        v439 = v428 - v438;
        v440 = 1;
        if ( v428 - *(_DWORD *)(a1 + 28) <= v438 )
          v439 = *(_DWORD *)(a1 + 28);
        if ( *(_DWORD *)(a1 + 32) )
          v439 = *(_DWORD *)(a1 + 28);
        v441 = *(_DWORD *)(a1 + 196);
        if ( v439 )
          v440 = v439;
        v894 = v440;
        v890 = (unsigned int *)(v433 + 8LL * (v428 & v436));
        v896 = (__int64 *)(v890 + 1);
        v819 = v428 + 9;
        v882 = 1 << v441;
        v915 = *(_QWORD *)(a1 + 176);
        v442 = *(_QWORD *)v915;
        v443 = *(_QWORD *)v915 - *(_QWORD *)(v915 + 8);
        v906 = *(_QWORD *)(v915 + 8);
        v444 = *(_DWORD *)(v915 + 28);
        v833 = v439 - v443;
        v898 = v442;
        LODWORD(v442) = *(_DWORD *)(v915 + 192);
        v445 = *(_DWORD *)(v915 + 188) - 1;
        v909 = v443;
        v899 = v444;
        v905 = v442;
        v911 = (1 << v445) - 1;
        v446 = v443 - v911;
        v855 = v918;
        if ( v911 >= v443 - v444 )
          v446 = v444;
        LODWORD(v912) = v446;
        v447 = (_DWORD *)v891;
        v448 = v428 - v437;
        v449 = v893;
        v892 = v428 - v437;
        v450 = v893 + 3;
        v889 = v893 + 3;
        v451 = (unsigned int *)(v891 + 4LL * v893);
        while ( 2 )
        {
          if ( v449 == 3 )
            v452 = *v447 - 1;
          else
            v452 = *v451;
          v453 = v428 - v452;
          v454 = 0;
          if ( v452 - 1 >= v448 )
          {
            if ( v452 - 1 < v843 - v833 - v899 && (unsigned int)(v437 - v453 - 1) >= 3 )
            {
              v464 = ZSTD_readMINMATCH(v828, 4, 0, v453);
              if ( v464 == *v467 )
              {
                v468 = v466 + 4;
                v469 = (char *)v467 + v465;
                v470 = v10;
                v471 = v466 + 4 - (_QWORD)v469 + v898;
                if ( v471 < v10 )
                  v470 = v471;
                v472 = ZSTD_count(v468, v469, v470);
                v473 = v472;
                if ( v472 + v474 == v898 )
                  v473 = ZSTD_count(v472 + v468, v916, v10) + v472;
                v450 = v889;
                v454 = (unsigned int)(v473 + 4);
                v423 = v888;
                LODWORD(v437) = v895;
              }
            }
            v429 = v828;
          }
          else
          {
            v455 = ZSTD_readMINMATCH(v429, 4, 0, -(__int64)v452);
            if ( v455 == *(_DWORD *)(v456 + v429) )
            {
              v457 = (_QWORD *)(v429 + 4);
              v458 = (_QWORD *)(v429 + v456 + 4);
              v459 = v10 - 7;
              v460 = v429 + 4;
              if ( v429 + 4 >= v10 - 7 )
                goto LABEL_518;
              if ( *v458 != *v457 )
              {
                v454 = (unsigned int)ZSTD_NbCommonBytes(*v458 ^ *v457, v457, v458, v460) + 4;
                goto LABEL_537;
              }
              v457 = (_QWORD *)(v429 + 12);
              ++v458;
              if ( v429 + 12 >= v459 )
              {
LABEL_518:
                if ( (unsigned __int64)v457 < v10 - 3 && *(_DWORD *)v458 == *(_DWORD *)v457 )
                {
                  v457 = (_QWORD *)((char *)v457 + 4);
                  v458 = (_QWORD *)((char *)v458 + 4);
                }
                if ( (unsigned __int64)v457 < v10 - 1 && *(_WORD *)v458 == *(_WORD *)v457 )
                {
                  v457 = (_QWORD *)((char *)v457 + 2);
                  v458 = (_QWORD *)((char *)v458 + 2);
                }
                if ( (unsigned __int64)v457 < v10 && *(_BYTE *)v458 == *(_BYTE *)v457 )
                  LODWORD(v457) = (_DWORD)v457 + 1;
                v454 = (unsigned int)((_DWORD)v457 - v429);
              }
              else
              {
                while ( *v458 == *v457 )
                {
                  ++v457;
                  ++v458;
                  if ( (unsigned __int64)v457 >= v459 )
                    goto LABEL_518;
                }
                v461 = ZSTD_NbCommonBytes(*v458 ^ *v457, v457, v458, v460);
                v454 = (unsigned int)(v462 - v463 + v461 + 4);
              }
            }
          }
LABEL_537:
          if ( (unsigned int)v454 > v855 )
          {
            v475 = &v901[2 * v945];
            *v475 = v449 - v893;
            v475[1] = v454;
            v855 = (unsigned int)v454;
            ++v945;
            if ( (unsigned int)v454 > v423 || v454 + v429 == v10 )
              goto LABEL_947;
          }
          v448 = v892;
          ++v449;
          v447 = (_DWORD *)v891;
          ++v451;
          if ( v449 < v450 )
          {
            v428 = v843;
            continue;
          }
          break;
        }
        v476 = v882;
        *v897 = v843;
        if ( v882 )
        {
          v477 = v819;
          v478 = v855;
          do
          {
            --v476;
            if ( v431 < v894 )
              goto LABEL_575;
            v479 = (unsigned int *)(v904 + 8LL * (v431 & v910));
            v480 = v10 - 7;
            v481 = v907;
            if ( v908 < v907 )
              v481 = v908;
            v482 = v902 + v431;
            v483 = (_QWORD *)(v481 + v429);
            v454 = v482 + v481;
            v484 = (char *)v483;
            if ( (unsigned __int64)v483 >= v480 )
              goto LABEL_551;
            if ( *(_QWORD *)v454 != *v483 )
            {
              v485 = (unsigned int)ZSTD_NbCommonBytes(*(_QWORD *)v454 ^ *v483, v483, v454, v481);
              goto LABEL_561;
            }
            ++v483;
            v454 += 8LL;
            if ( (unsigned __int64)v483 >= v480 )
            {
LABEL_551:
              if ( (unsigned __int64)v483 < v10 - 3 && *(_DWORD *)v454 == *(_DWORD *)v483 )
              {
                v483 = (_QWORD *)((char *)v483 + 4);
                v454 += 4LL;
              }
              if ( (unsigned __int64)v483 < v10 - 1 && *(_WORD *)v454 == *(_WORD *)v483 )
              {
                v483 = (_QWORD *)((char *)v483 + 2);
                v454 += 2LL;
              }
              if ( (unsigned __int64)v483 < v10 && *(_BYTE *)v454 == *(_BYTE *)v483 )
                v483 = (_QWORD *)((char *)v483 + 1);
              v485 = (char *)v483 - v484;
            }
            else
            {
              while ( *(_QWORD *)v454 == *v483 )
              {
                ++v483;
                v454 += 8LL;
                if ( (unsigned __int64)v483 >= v480 )
                  goto LABEL_551;
              }
              v488 = ZSTD_NbCommonBytes(*(_QWORD *)v454 ^ *v483, v483, v454, v481);
              v485 = v489 - v490 + v488;
            }
LABEL_561:
            v486 = v485 + v481;
            if ( v486 <= v478 )
            {
              v429 = v828;
            }
            else
            {
              if ( v486 > v477 - v431 )
              {
                v819 = v431 + v486;
                v477 = v431 + v486;
              }
              v429 = v828;
              v487 = &v901[2 * v945];
              v487[1] = v486;
              *v487 = v843 - v431 + 2;
              ++v945;
              v855 = v486;
              if ( v486 > 0x1000 || v486 + v828 == v10 )
              {
                v476 = 0;
                goto LABEL_575;
              }
              v478 = v486;
            }
            if ( *(_BYTE *)(v482 + v486) >= *(_BYTE *)(v486 + v429) )
            {
              v907 = v486;
              *(_DWORD *)v896 = v431;
              if ( v431 <= v873 )
              {
                v896 = (__int64 *)&v910;
                goto LABEL_575;
              }
              v431 = *v479;
              v896 = (__int64 *)v479;
            }
            else
            {
              v908 = v486;
              *v890 = v431;
              if ( v431 <= v873 )
              {
                v491 = &v910;
                goto LABEL_576;
              }
              v431 = v479[1];
              v890 = v479 + 1;
            }
          }
          while ( v476 );
        }
        --v476;
LABEL_575:
        v491 = v890;
LABEL_576:
        *(_DWORD *)v896 = 0;
        *v491 = 0;
        if ( v476 )
        {
          v492 = ZSTD_hash6Ptr(v429, v905, v454);
          v493 = 0;
          v494 = 0;
          v495 = *(_DWORD *)(*(_QWORD *)(v915 + 48) + 4 * v492);
          v496 = *(_DWORD **)(v915 + 64);
          v897 = v496;
          do
          {
            v915 = v494;
            v905 = v819;
            v883 = v476 - 1;
            if ( v495 <= v899 )
              break;
            v497 = v493;
            if ( v494 < v493 )
              v497 = v494;
            v498 = v495 + v906;
            v499 = v913;
            v890 = &v496[2 * (v911 & v495)];
            if ( v828 + v898 - v498 < v913 )
              v499 = v828 + v898 - v498;
            v500 = ZSTD_count(v497 + v828, v498 + v497, v499);
            v501 = v500;
            v10 = v913;
            if ( v500 + v502 == v898 )
              v501 = ZSTD_count(v500 + v497 + v828, v916, v913) + v500;
            v494 = v501 + v497;
            if ( v501 + v497 + v495 >= v909 )
              v498 = v902 + v833 + (unsigned __int64)v495;
            if ( v494 > v855 )
            {
              v503 = v901;
              v901[2 * v945 + 1] = v494;
              v503[2 * v945] = v843 - (v495 + v833) + 2;
              v504 = v495 + v833 + v494;
              v855 = v501 + v497;
              ++v945;
              if ( v494 <= v819 - (v495 + v833) )
                v504 = v905;
              v819 = v504;
              if ( v494 > 0x1000 || v494 + v828 == v10 )
                break;
            }
            if ( v495 <= (unsigned int)v912 )
              break;
            v505 = *(_BYTE *)(v498 + v494);
            v506 = *(_BYTE *)(v494 + v828);
            if ( v505 >= v506 )
            {
              v495 = *v890;
              v493 = v501 + v497;
            }
            else
            {
              v495 = v890[1];
            }
            v476 = v883;
            v104 = v505 < v506;
            v496 = v897;
            if ( !v104 )
              v494 = v915;
          }
          while ( v883 );
          goto LABEL_602;
        }
LABEL_946:
        *(_DWORD *)(a1 + 36) = v819 - 8;
LABEL_947:
        if ( !v945 )
        {
LABEL_975:
          v397 = v914;
LABEL_976:
          v402 = v868 + 1;
          v868 = v402;
          if ( v402 > v401 )
            goto LABEL_985;
          v400 = v919;
          continue;
        }
        break;
      }
      v764 = v901;
      v765 = v868;
      v766 = v901[2 * v945 - 1];
      if ( v766 <= v921 && v766 + v868 < 0x1000 )
      {
        v892 = 0;
        v767 = v901;
        v768 = v945;
        v897 = v901;
        do
        {
          v769 = *v767;
          v770 = ZSTD_updateRep(v938, v891, *v767, v893);
          v772 = v767[1];
          v773 = *(_DWORD *)(v770 + 8);
          v774 = *(_QWORD *)v770;
          v905 = v773;
          if ( v771 )
            v775 = v764[2 * v771 - 1] + 1;
          else
            v775 = v917;
          if ( v772 < v775 )
          {
            v397 = v914;
          }
          else
          {
            v776 = v919;
            v777 = v772 + v765;
            v778 = -v765;
            do
            {
              v779 = v778 + v777;
              _BitScanReverse((unsigned int *)&v780, v769 + 1);
              v13 = *(_DWORD *)(v776 + 80) == 1;
              v781 = v778 + v777 - 3;
              LODWORD(v898) = 0;
              if ( v13 )
              {
                LODWORD(v896) = 0;
                _BitScanReverse(&v782, v781 + 1);
                v783 = v903 + ((v782 + (_DWORD)v780 + 16) << 8);
              }
              else
              {
                LODWORD(v890) = 0;
                _BitScanReverse(&v784, *(_DWORD *)(*(_QWORD *)(v776 + 24) + 4 * v780) + 1);
                v785 = *(_DWORD *)(v776 + 76) + (((_DWORD)v780 - v784) << 8);
                if ( (unsigned int)v780 >= 0x14 )
                  v785 = ((_DWORD)v780 << 9) + v785 - 9728;
                if ( (unsigned int)v781 <= 0x7F )
                {
                  _mm_lfence();
                  v787 = *((unsigned __int8 *)&qword_1803EF770[8] + v781);
                }
                else
                {
                  _BitScanReverse(&v786, v781);
                  v787 = v786 + 36;
                }
                v788 = 4 * v787;
                _BitScanReverse((unsigned int *)&v787, *(_DWORD *)(*(_QWORD *)(v776 + 16) + 4 * v787) + 1);
                v789 = *(_DWORD *)((char *)&qword_1803EF640[10] + v788);
                LODWORD(v788) = v785 + 51;
                v773 = v905;
                v783 = v903 + *(_DWORD *)(v776 + 72) + ((v789 - (_DWORD)v787) << 8) + v788;
              }
              v397 = v914;
              if ( v777 > v401 )
                goto LABEL_1016;
              if ( v783 >= v914[7 * v777] )
                break;
              if ( v401 < v777 )
              {
LABEL_1016:
                do
                  v397[7 * ++v401] = 0x40000000;
                while ( v401 < v777 );
                v863 = v401;
              }
              v790 = v777--;
              v791 = 7 * v790;
              v397[v791 + 3] = v900;
              *(_QWORD *)&v397[v791 + 4] = v774;
              v397[v791 + 2] = v779;
              v397[v791 + 1] = v769;
              v397[v791] = v783;
              v397[v791 + 6] = v773;
            }
            while ( v778 + v777 >= v775 );
            v771 = v892;
            v767 = v897;
            v768 = v945;
            v765 = v868;
          }
          v764 = v901;
          v767 += 2;
          v892 = v771 + 1;
          v897 = v767;
        }
        while ( v771 + 1 < v768 );
        v10 = v913;
        goto LABEL_976;
      }
      v356 = 0;
      v354 = v914;
      DWORD1(v925) = v901[2 * v945 - 2];
      v792 = 7LL * v868;
      *((_QWORD *)&v925 + 1) = __PAIR64__(v900, v766);
      if ( v914[v792 + 2] )
      {
        v357 = 0;
        if ( v868 <= 0x1000 )
          v357 = v868;
      }
      else
      {
        v357 = 0;
        if ( v868 - v914[v792 + 3] <= 0x1000 )
          v357 = v868 - v914[v792 + 3];
      }
LABEL_449:
      v358 = v357 + 1;
      v359 = v357 + 1;
      v360 = 7LL * (v357 + 1);
      v361 = v920;
      *(_OWORD *)&v354[v360] = v925;
      *(_QWORD *)&v354[v360 + 4] = v15;
      v354[v360 + 6] = v361;
      while ( v357 )
      {
        v362 = &v354[7 * v357];
        v363 = *(_OWORD *)v362;
        v936 = v362[6];
        v364 = *((_QWORD *)v362 + 2);
        v934 = v363;
        v935 = v364;
        *(double *)&v363 = ZSTD_totalLen(&v934);
        v365 = 7LL * --v359;
        *(_OWORD *)&v354[v365] = v363;
        *(_QWORD *)&v354[v365 + 4] = *(_QWORD *)(v366 + 16);
        v354[v365 + 6] = *(_DWORD *)(v366 + 24);
        v367 = v357;
        v357 -= v368;
        if ( v367 <= v368 )
          v357 = v356;
      }
      if ( v359 <= v358 )
      {
        v369 = v942;
        while ( 1 )
        {
          v370 = 7LL * v359;
          v371 = v354[v370 + 2];
          v372 = (unsigned int)v354[v370 + 3];
          v373 = v354[v370 + 1];
          v374 = v371 + v372;
          if ( v371 )
            break;
          v887 = v369 + v372;
LABEL_1007:
          ++v359;
          v356 = 0;
          if ( v359 > v358 )
            goto LABEL_1008;
        }
        if ( v373 >= 3 )
        {
          a3[2] = a3[1];
          a3[1] = *a3;
          *a3 = v373 - 2;
          goto LABEL_995;
        }
        v796 = v356;
        LOBYTE(v796) = (_DWORD)v372 == 0;
        v797 = v373 + v796;
        if ( (_DWORD)v797 )
        {
          if ( (_DWORD)v797 == 3 )
          {
            v798 = *a3 - 1;
            goto LABEL_993;
          }
          v798 = a3[v797];
          if ( (unsigned int)v797 >= 2 )
LABEL_993:
            a3[2] = a3[1];
          a3[1] = *a3;
          *a3 = v798;
        }
LABEL_995:
        ZSTD_updateStats(v919, v372, v942, v373, v371);
        v799 = v371 - 3;
        v801 = v800;
        v802 = *(_QWORD *)(a2 + 24);
        if ( v800 + v942 <= v10 - 32 )
        {
          ZSTD_copy16(v802);
          if ( v801 > 0x10 )
          {
            ZSTD_copy16(*(_QWORD *)(v804 + 24) + 16LL);
            v806 = ZSTD_copy16(v805 + 16);
            v808 = v807 + 16;
            if ( v808 < v806 )
            {
              do
              {
                ZSTD_copy16(v808);
                v810 = ZSTD_copy16(v809 + 16);
                v808 = v811 + 16;
              }
              while ( v808 < v810 );
            }
LABEL_1001:
            v803 = v942;
          }
          *(_QWORD *)(v804 + 24) += v801;
          v812 = *(_QWORD *)(v804 + 8);
          if ( v801 > 0xFFFF )
          {
            *(_DWORD *)(v804 + 72) = 1;
            *(_DWORD *)(v804 + 76) = (v812 - *(_QWORD *)v804) >> 3;
          }
          *(_WORD *)(v812 + 4) = v801;
          **(_DWORD **)(v804 + 8) = v373 + 1;
          v813 = *(_QWORD *)(v804 + 8);
          if ( v799 > 0xFFFF )
          {
            *(_DWORD *)(v804 + 72) = 2;
            *(_DWORD *)(v804 + 76) = (v813 - *(_QWORD *)v804) >> 3;
          }
          v354 = v914;
          *(_WORD *)(v813 + 6) = v799;
          *(_QWORD *)(v804 + 8) += 8LL;
          v942 = v374 + v803;
          v369 = v942;
          v887 = v942;
          goto LABEL_1007;
        }
        ZSTD_safecopyLiterals(v802);
        v804 = a2;
        goto LABEL_1001;
      }
LABEL_1008:
      ZSTD_setBasePrices(v919, 0);
      v14 = v887;
LABEL_1011:
      v5 = a1;
      v8 = v942;
    }
    while ( v14 < v10 - 8 );
  }
  return v10 - v8;
}

```

## disassembly

```asm
0x1802cbc70  mov     [rsp-8+arg_18], r9
0x1802cbc75  mov     [rsp-8+arg_10], r8
0x1802cbc7a  mov     [rsp-8+arg_8], rdx
0x1802cbc7f  mov     [rsp-8+arg_0], rcx
0x1802cbc84  push    rbp
0x1802cbc85  push    rbx
0x1802cbc86  push    rsi
0x1802cbc87  push    rdi
0x1802cbc88  push    r12
0x1802cbc8a  push    r15
0x1802cbc8c  lea     rbp, [rsp-118h]
0x1802cbc94  sub     rsp, 218h
0x1802cbc9b  mov     r8, [rbp+140h+arg_20]
0x1802cbca2  mov     r15, rcx
0x1802cbca5  add     rcx, 48h ; 'H'
0x1802cbca9  mov     edx, 0FFFh
0x1802cbcae  mov     rdi, r9
0x1802cbcb1  mov     [rbp+140h+var_108], rcx
0x1802cbcb5  mov     eax, [r15+0CCh]
0x1802cbcbc  lea     r12, [r9+r8]
0x1802cbcc0  mov     ebx, [r15+18h]
0x1802cbcc4  lea     rsi, [r12-8]
0x1802cbcc9  add     rbx, [r15+8]
0x1802cbccd  cmp     eax, edx
0x1802cbccf  mov     [rbp+140h+var_138], r12
0x1802cbcd3  cmovb   edx, eax
0x1802cbcd6  xor     eax, eax
0x1802cbcd8  cmp     dword ptr [r15+0C8h], 3
0x1802cbce0  mov     [rbp+140h+var_FC], edx
0x1802cbce3  mov     rdx, rdi
0x1802cbce6  setnz   al
0x1802cbce9  xor     r9d, r9d
0x1802cbcec  add     eax, 3
0x1802cbcef  mov     [rbp+140h+var_118], eax
0x1802cbcf2  mov     eax, [r15+24h]
0x1802cbcf6  mov     [rbp+140h+var_F8], eax
0x1802cbcf9  mov     rax, [rcx+28h]
0x1802cbcfd  mov     [rbp+140h+var_130], rax
0x1802cbd01  mov     rax, [rcx+20h]
0x1802cbd05  mov     [rbp+140h+var_190], rax
0x1802cbd09  call    ZSTD_rescaleFreqs
0x1802cbd0e  xor     r9d, r9d
0x1802cbd11  cmp     rdi, rbx
0x1802cbd14  mov     r11d, r9d
0x1802cbd17  setz    r11b
0x1802cbd1b  add     r11, rdi
0x1802cbd1e  mov     [rsp+240h+var_1E0], r11
0x1802cbd23  cmp     r11, rsi
0x1802cbd26  jnb     loc_1802D0420
0x1802cbd2c  mov     eax, [rbp+140h+var_C8]
0x1802cbd2f  movsd   xmm2, [rbp+140h+var_D0]
0x1802cbd34  mov     [rsp+240h+var_30], r13
0x1802cbd3c  mov     [rsp+240h+var_38], r14
0x1802cbd44  mov     [rbp+140h+var_100], eax
0x1802cbd47  nop     word ptr [rax+rax+00000000h]
0x1802cbd50  mov     ebx, [r15+24h]
0x1802cbd54  mov     eax, r11d
0x1802cbd57  mov     r14, [r15+8]
0x1802cbd5b  sub     eax, edi
0x1802cbd5d  mov     esi, [r15+0C8h]
0x1802cbd64  mov     r13d, r9d
0x1802cbd67  setz    r13b
0x1802cbd6b  mov     [rbp+140h+var_198], eax
0x1802cbd6e  mov     [rbp+140h+var_1BC], r13d
0x1802cbd72  lea     rax, [r14+rbx]
0x1802cbd76  cmp     r11, rax
0x1802cbd79  jb      loc_1802D03E6
0x1802cbd7f  mov     edi, r11d
0x1802cbd82  sub     edi, r14d
0x1802cbd85  cmp     ebx, edi
0x1802cbd87  jnb     short loc_1802CBDBA
0x1802cbd89  xor     r13d, r13d
0x1802cbd8c  nop     dword ptr [rax+00h]
0x1802cbd90  mov     edx, ebx
0x1802cbd92  mov     r9d, esi
0x1802cbd95  add     rdx, r14
0x1802cbd98  mov     dword ptr [rsp+240h+var_220], r13d
0x1802cbd9d  mov     r8, r12
0x1802cbda0  mov     rcx, r15
0x1802cbda3  call    ZSTD_insertBt1
0x1802cbda8  add     ebx, eax
0x1802cbdaa  cmp     ebx, edi
0x1802cbdac  jb      short loc_1802CBD90
0x1802cbdae  mov     r13d, [rbp+140h+var_1BC]
0x1802cbdb2  xor     r9d, r9d
0x1802cbdb5  mov     r11, [rsp+240h+var_1E0]
0x1802cbdba  mov     r8, [r15+30h]
0x1802cbdbe  mov     [r15+24h], edi
0x1802cbdc2  mov     edx, [r15+0C0h]
0x1802cbdc9  cmp     esi, 3
0x1802cbdcc  jz      loc_1802CD38F
0x1802cbdd2  mov     ecx, 0FFFh
0x1802cbdd7  mov     r10d, r11d
0x1802cbdda  cmp     esi, 5
0x1802cbddd  jz      loc_1802CCC5A
0x1802cbde3  lea     eax, [rsi-6]
0x1802cbde6  mov     rsi, [r15+8]
0x1802cbdea  cmp     eax, 1
0x1802cbded  mov     [rbp+140h+var_168], rsi
0x1802cbdf1  mov     eax, [r15+0CCh]
0x1802cbdf8  ja      loc_1802CC51F
0x1802cbdfe  cmp     eax, ecx
0x1802cbe00  cmovb   ecx, eax
0x1802cbe03  sub     r10d, esi
0x1802cbe06  mov     [rbp+140h+var_1B8], ecx
0x1802cbe09  mov     rcx, r11
0x1802cbe0c  mov     [rsp+240h+var_1F0], r10d
0x1802cbe11  call    ZSTD_hash6Ptr
0x1802cbe16  mov     ebx, [r8+rax*4]
0x1802cbe1a  lea     rax, [r8+rax*4]
0x1802cbe1e  mov     r8d, [r15+18h]
0x1802cbe22  lea     r14d, [r10+9]
0x1802cbe26  mov     ecx, [r15+0BCh]
0x1802cbe2d  mov     r11d, 1
0x1802cbe33  mov     rdi, [r15+40h]
0x1802cbe37  dec     ecx
0x1802cbe39  shl     r11d, cl
0x1802cbe3c  mov     edx, 1
0x1802cbe41  mov     [rbp+140h+var_1A8], rax
0x1802cbe45  xor     ecx, ecx
0x1802cbe47  dec     r11d
0x1802cbe4a  mov     [rbp+140h+var_1B0], r9
0x1802cbe4e  lea     rax, [rsi+r8]
0x1802cbe52  mov     [rsp+240h+var_1FC], r11d
0x1802cbe57  mov     [rbp+140h+var_160], rax
0x1802cbe5b  mov     r9d, r10d
0x1802cbe5e  mov     eax, r10d
0x1802cbe61  mov     [rbp+140h+var_178], rdi
0x1802cbe65  sub     eax, r11d
0x1802cbe68  mov     [rbp+140h+var_1A0], 0
0x1802cbe70  cmp     r11d, r10d
0x1802cbe73  mov     [rbp+140h+var_180], r8d
0x1802cbe77  mov     [rsp+240h+var_200], r14d
0x1802cbe7c  cmovb   ecx, eax
0x1802cbe7f  mov     eax, r10d
0x1802cbe82  mov     [rbp+140h+var_194], ecx
0x1802cbe85  mov     ecx, [r15+0B8h]
0x1802cbe8c  shl     edx, cl
0x1802cbe8e  mov     ecx, [r15+1Ch]
0x1802cbe92  sub     r9d, edx
0x1802cbe95  sub     eax, ecx
0x1802cbe97  cmp     eax, edx
0x1802cbe99  mov     edx, r9d
0x1802cbe9c  mov     eax, 1
0x1802cbea1  cmovbe  edx, ecx
0x1802cbea4  cmp     dword ptr [r15+20h], 0
0x1802cbea9  cmovnz  edx, ecx
0x1802cbeac  mov     ecx, [r15+0C4h]
0x1802cbeb3  test    edx, edx
0x1802cbeb5  mov     r15d, 1
0x1802cbebb  cmovnz  eax, edx
0x1802cbebe  shl     r15d, cl
0x1802cbec1  mov     [rsp+240h+var_1E4], eax
0x1802cbec5  xor     esi, esi
0x1802cbec7  mov     eax, r11d
0x1802cbeca  mov     dword ptr [rbp+140h+arg_20], esi
0x1802cbed0  and     eax, r10d
0x1802cbed3  add     eax, eax
0x1802cbed5  lea     rax, [rdi+rax*4]
0x1802cbed9  mov     edi, 1
0x1802cbede  mov     [rsp+240h+var_208], rax
0x1802cbee3  add     rax, 4
0x1802cbee7  mov     [rsp+240h+var_1F8], rax
0x1802cbeec  mov     rax, [rbp+140h+arg_0]
0x1802cbef3  mov     rcx, [rax+0B0h]
0x1802cbefa  mov     [rbp+140h+var_188], rcx
0x1802cbefe  mov     rax, [rcx]
0x1802cbf01  mov     r9, [rcx+8]
0x1802cbf05  mov     r11d, eax
0x1802cbf08  sub     r11d, r9d
0x1802cbf0b  mov     [rbp+140h+var_158], r9
0x1802cbf0f  mov     r9d, [rcx+1Ch]
0x1802cbf13  sub     edx, r11d
0x1802cbf16  mov     [rsp+240h+var_1D0], rax
0x1802cbf1b  mov     eax, [rcx+0C0h]
0x1802cbf21  mov     ecx, [rcx+0BCh]
0x1802cbf27  dec     ecx
0x1802cbf29  mov     [rsp+240h+var_1D8], r11d
0x1802cbf2e  shl     edi, cl
0x1802cbf30  mov     [rsp+240h+var_1E8], r9d
0x1802cbf35  mov     [rsp+240h+var_1EC], edx
0x1802cbf39  mov     [rsp+240h+var_210], eax
0x1802cbf3d  dec     edi
0x1802cbf3f  mov     eax, r11d
0x1802cbf42  sub     eax, r9d
0x1802cbf45  mov     [rbp+140h+var_1B4], edi
0x1802cbf48  mov     ecx, r11d
0x1802cbf4b  lea     r11d, [r13+3]
0x1802cbf4f  sub     ecx, edi
0x1802cbf51  mov     [rbp+140h+var_1C0], r11d
0x1802cbf55  cmp     edi, eax
0x1802cbf57  mov     eax, [rbp+140h+var_118]
0x1802cbf5a  dec     eax
0x1802cbf5c  mov     edi, r13d
0x1802cbf5f  cmovnb  ecx, r9d
0x1802cbf63  mov     [rbp+140h+var_110], rax
0x1802cbf67  mov     [rsp+240h+var_1D4], ecx
0x1802cbf6b  mov     rcx, [rbp+140h+arg_10]
0x1802cbf72  mov     [rsp+240h+var_1C8], rax
0x1802cbf77  mov     eax, r13d
0x1802cbf7a  mov     r13d, r10d
0x1802cbf7d  sub     r13d, r8d
0x1802cbf80  lea     rsi, [rcx+rax*4]
0x1802cbf84  jmp     short loc_1802CBF8B
0x1802cbf86  mov     r10d, [rsp+240h+var_1F0]
0x1802cbf8b  cmp     edi, 3
0x1802cbf8e  jnz     short loc_1802CBF96
0x1802cbf90  mov     eax, [rcx]
0x1802cbf92  dec     eax
0x1802cbf94  jmp     short loc_1802CBF98
0x1802cbf96  mov     eax, [rsi]
0x1802cbf98  sub     r10d, eax
0x1802cbf9b  lea     ecx, [rax-1]
0x1802cbf9e  xor     r8d, r8d
0x1802cbfa1  cmp     ecx, r13d
0x1802cbfa4  jnb     loc_1802CC083
0x1802cbfaa  mov     r10, [rsp+240h+var_1E0]
0x1802cbfaf  lea     edx, [r8+4]
0x1802cbfb3  mov     r9d, eax
0x1802cbfb6  mov     rcx, r10
0x1802cbfb9  neg     r9
0x1802cbfbc  call    ZSTD_readMINMATCH
0x1802cbfc1  cmp     eax, [r9+r10]
0x1802cbfc5  jnz     loc_1802CC0F6
0x1802cbfcb  lea     rdx, [r10+4]
0x1802cbfcf  lea     r8, [r10+4]
0x1802cbfd3  add     r8, r9
0x1802cbfd6  lea     rax, [r12-7]
0x1802cbfdb  mov     r9, rdx
0x1802cbfde  cmp     rdx, rax
0x1802cbfe1  jnb     short loc_1802CC01D
0x1802cbfe3  mov     rcx, [rdx]
0x1802cbfe6  xor     rcx, [r8]
0x1802cbfe9  jz      short loc_1802CBFFB
0x1802cbfeb  call    ZSTD_NbCommonBytes
0x1802cbff0  mov     ecx, eax
0x1802cbff2  lea     r8d, [rcx+4]
0x1802cbff6  jmp     loc_1802CC0F6
0x1802cbffb  add     rdx, 8
0x1802cbfff  add     r8, 8
0x1802cc003  cmp     rdx, rax
0x1802cc006  jnb     short loc_1802CC01D
0x1802cc008  mov     rcx, [rdx]
0x1802cc00b  xor     rcx, [r8]
0x1802cc00e  jnz     short loc_1802CC070
0x1802cc010  add     rdx, 8
0x1802cc014  add     r8, 8
0x1802cc018  cmp     rdx, rax
0x1802cc01b  jb      short loc_1802CC008
0x1802cc01d  lea     rax, [r12-3]
0x1802cc022  cmp     rdx, rax
0x1802cc025  jnb     short loc_1802CC036
0x1802cc027  mov     eax, [rdx]
0x1802cc029  cmp     [r8], eax
0x1802cc02c  jnz     short loc_1802CC036
0x1802cc02e  add     rdx, 4
0x1802cc032  add     r8, 4
0x1802cc036  lea     rax, [r12-1]
0x1802cc03b  cmp     rdx, rax
0x1802cc03e  jnb     short loc_1802CC051
0x1802cc040  movzx   eax, word ptr [rdx]
0x1802cc043  cmp     [r8], ax
0x1802cc047  jnz     short loc_1802CC051
0x1802cc049  add     rdx, 2
0x1802cc04d  add     r8, 2
0x1802cc051  cmp     rdx, r12
0x1802cc054  jnb     short loc_1802CC061
0x1802cc056  movzx   eax, byte ptr [rdx]
0x1802cc059  cmp     [r8], al
0x1802cc05c  jnz     short loc_1802CC061
0x1802cc05e  inc     rdx
0x1802cc061  mov     rcx, rdx
0x1802cc064  sub     rcx, r9
0x1802cc067  lea     r8d, [rcx+4]
0x1802cc06b  jmp     loc_1802CC0F6
0x1802cc070  call    ZSTD_NbCommonBytes
0x1802cc075  mov     ecx, eax
0x1802cc077  sub     rdx, r9
0x1802cc07a  add     rcx, rdx
0x1802cc07d  lea     r8d, [rcx+4]
0x1802cc081  jmp     short loc_1802CC0F6
0x1802cc083  mov     eax, edx
0x1802cc085  mov     r9d, r10d
0x1802cc088  sub     r9, rax
0x1802cc08b  mov     eax, [rsp+240h+var_1F0]
0x1802cc08f  add     r9, [rbp+140h+var_158]
0x1802cc093  sub     eax, edx
0x1802cc095  sub     eax, [rsp+240h+var_1E8]
0x1802cc099  xor     edx, edx
0x1802cc09b  cmp     ecx, eax
0x1802cc09d  mov     ecx, [rbp+140h+var_180]
0x1802cc0a0  setb    dl
0x1802cc0a3  sub     ecx, r10d
0x1802cc0a6  mov     r10, [rsp+240h+var_1E0]
0x1802cc0ab  xor     eax, eax
0x1802cc0ad  dec     ecx
0x1802cc0af  cmp     ecx, 3
0x1802cc0b2  setnb   al
0x1802cc0b5  test    eax, edx
0x1802cc0b7  jz      short loc_1802CC0F6
  ... truncated ...
```
