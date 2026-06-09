# ZSTD_compressBlock_btopt_extDict

- ea: `0x1802d0440`
- end: `0x1802d409c`
- name: `ZSTD_compressBlock_btopt_extDict`
- size: `15452`
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
- `0x1802d0440`
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
char *__fastcall ZSTD_compressBlock_btopt_extDict(__int64 a1, __int64 a2, int *a3, unsigned __int64 a4, __int64 a5)
{
  unsigned int v5; // eax
  __int64 v6; // r13
  __int64 v7; // rdi
  __int64 v8; // rbx
  unsigned __int64 v9; // rsi
  int v10; // ecx
  bool v11; // zf
  char *v12; // r15
  unsigned __int64 v13; // r14
  unsigned __int64 v14; // rcx
  __int64 v15; // xmm2_8
  __int64 v16; // rbx
  __int64 v17; // r14
  unsigned int v18; // eax
  int v19; // esi
  BOOL v20; // r12d
  unsigned int v21; // edi
  unsigned int v22; // r13d
  __int64 v23; // r8
  __int64 v24; // rdx
  _DWORD *v25; // r9
  unsigned int v26; // eax
  __int64 v27; // rax
  unsigned int v28; // r10d
  __int64 v29; // r8
  unsigned int v30; // r15d
  _DWORD *v31; // rbx
  char v32; // cl
  unsigned int v33; // ecx
  unsigned int v34; // r8d
  unsigned __int64 v35; // r11
  _DWORD *v36; // r11
  __int64 v37; // r9
  unsigned int v38; // edx
  int v39; // esi
  int v40; // eax
  int v41; // ecx
  unsigned int v42; // r12d
  int v43; // eax
  int *v44; // rcx
  unsigned int v45; // r14d
  unsigned int v46; // ebx
  unsigned int *v47; // rdi
  unsigned int v48; // eax
  __int64 v49; // r9
  unsigned int v50; // r8d
  int v51; // eax
  __int64 v52; // rcx
  __int64 v53; // r9
  char *v54; // rdx
  __int64 v55; // r8
  unsigned __int64 v56; // rcx
  _QWORD *v57; // r8
  char *v58; // r9
  unsigned __int64 v59; // rax
  int v60; // eax
  int v61; // edx
  int v62; // r9d
  int v63; // eax
  int v64; // ecx
  _DWORD *v65; // r10
  int v66; // eax
  _DWORD *v67; // rdx
  char *v68; // rax
  char *v69; // r9
  unsigned int v70; // r10d
  unsigned __int64 v71; // r11
  unsigned __int64 v72; // r14
  unsigned __int64 v73; // rsi
  unsigned __int64 v74; // rbx
  unsigned int *v75; // r13
  char *v76; // rdx
  char *v77; // r12
  unsigned __int64 v78; // r9
  char *v79; // rdi
  char *v80; // r8
  unsigned __int64 v81; // rax
  unsigned __int64 v82; // rbx
  unsigned int v83; // eax
  __int64 v84; // rdx
  __int64 v85; // r9
  unsigned __int64 v86; // r14
  char *v87; // r8
  __int64 v88; // rsi
  __int64 v89; // r11
  _DWORD *v90; // rcx
  unsigned __int64 v91; // r11
  bool v92; // cf
  _DWORD *v93; // rcx
  int v94; // eax
  unsigned int *v95; // rax
  unsigned int *v96; // rax
  __int64 v97; // rax
  unsigned int v98; // r10d
  __int64 v99; // r8
  unsigned int v100; // r15d
  _DWORD *v101; // rbx
  char v102; // cl
  unsigned int v103; // ecx
  unsigned int v104; // r8d
  unsigned __int64 v105; // r11
  _DWORD *v106; // r11
  __int64 v107; // r9
  unsigned int v108; // edx
  int v109; // esi
  int v110; // eax
  int v111; // ecx
  unsigned int v112; // r12d
  int v113; // eax
  int *v114; // rcx
  unsigned int v115; // r14d
  unsigned int v116; // ebx
  unsigned int *v117; // rdi
  unsigned int v118; // eax
  __int64 v119; // r9
  unsigned int v120; // r8d
  int v121; // eax
  __int64 v122; // rcx
  __int64 v123; // r9
  char *v124; // rdx
  __int64 v125; // r8
  unsigned __int64 v126; // rcx
  _QWORD *v127; // r8
  char *v128; // r9
  unsigned __int64 v129; // rax
  int v130; // eax
  int v131; // edx
  int v132; // r9d
  int v133; // eax
  int v134; // ecx
  _DWORD *v135; // r10
  int v136; // eax
  _DWORD *v137; // rdx
  char *v138; // rax
  char *v139; // r9
  unsigned int v140; // r10d
  unsigned __int64 v141; // r11
  unsigned __int64 v142; // r14
  unsigned __int64 v143; // rsi
  unsigned __int64 v144; // rbx
  unsigned int *v145; // r13
  char *v146; // rdx
  char *v147; // r12
  unsigned __int64 v148; // r9
  char *v149; // rdi
  char *v150; // r8
  unsigned __int64 v151; // rax
  unsigned __int64 v152; // rbx
  unsigned int v153; // eax
  __int64 v154; // rdx
  __int64 v155; // r9
  unsigned __int64 v156; // r14
  char *v157; // r8
  __int64 v158; // rsi
  __int64 v159; // r11
  _DWORD *v160; // rcx
  unsigned __int64 v161; // r11
  _DWORD *v162; // rcx
  int v163; // eax
  unsigned int v164; // ebx
  __int64 v165; // rax
  unsigned int v166; // r10d
  __int64 v167; // r8
  unsigned int v168; // r15d
  _DWORD *v169; // rbx
  char v170; // cl
  unsigned int v171; // ecx
  unsigned int v172; // r8d
  unsigned __int64 v173; // r11
  _DWORD *v174; // r11
  __int64 v175; // r9
  unsigned int v176; // edx
  int v177; // esi
  int v178; // eax
  int v179; // ecx
  unsigned int v180; // r12d
  int v181; // eax
  int *v182; // rcx
  unsigned int v183; // r14d
  unsigned int v184; // ebx
  unsigned int *v185; // rdi
  unsigned int v186; // eax
  __int64 v187; // r9
  unsigned int v188; // r8d
  int v189; // eax
  __int64 v190; // rcx
  __int64 v191; // r9
  char *v192; // rdx
  __int64 v193; // r8
  unsigned __int64 v194; // rcx
  _QWORD *v195; // r8
  char *v196; // r9
  unsigned __int64 v197; // rax
  int v198; // eax
  int v199; // edx
  int v200; // r9d
  int MINMATCH; // eax
  int v202; // ecx
  _DWORD *v203; // r10
  int v204; // eax
  _DWORD *v205; // rdx
  char *v206; // rax
  char *v207; // r9
  unsigned int v208; // r10d
  unsigned __int64 v209; // r11
  unsigned __int64 v210; // r14
  unsigned __int64 v211; // rsi
  unsigned __int64 v212; // rbx
  unsigned int *v213; // r13
  char *v214; // rdx
  char *v215; // r12
  unsigned __int64 v216; // r9
  char *v217; // rdi
  char *v218; // r8
  unsigned __int64 v219; // rax
  unsigned __int64 v220; // rbx
  unsigned int v221; // eax
  __int64 v222; // rdx
  __int64 v223; // r9
  unsigned __int64 v224; // r14
  char *v225; // r8
  __int64 v226; // rsi
  __int64 v227; // r11
  _DWORD *v228; // rcx
  unsigned __int64 v229; // r11
  _DWORD *v230; // rcx
  int v231; // eax
  unsigned int v232; // eax
  _DWORD *v233; // r10
  __int64 v234; // rax
  unsigned int v235; // r9d
  __int64 v236; // r8
  unsigned int v237; // r15d
  _DWORD *v238; // r11
  int v239; // ecx
  __int64 v240; // r14
  unsigned int v241; // ebx
  unsigned int v242; // ecx
  unsigned int v243; // r8d
  __int64 v244; // r10
  unsigned int v245; // edx
  int v246; // esi
  int v247; // eax
  int v248; // ecx
  unsigned int v249; // r11d
  int v250; // eax
  int *v251; // rcx
  _BOOL8 v252; // rax
  unsigned int v253; // r12d
  unsigned int *v254; // rdi
  unsigned int v255; // eax
  unsigned int v256; // r8d
  unsigned int v257; // r9d
  int v258; // eax
  __int64 v259; // rcx
  __int64 v260; // r10
  int v261; // r8d
  char *v262; // rdx
  __int64 v263; // r9
  _QWORD *v264; // r8
  unsigned __int64 v265; // rax
  int v266; // eax
  int v267; // edx
  int v268; // r9d
  __int64 v269; // r8
  int v270; // eax
  int v271; // ecx
  int v272; // r10d
  int v273; // r8d
  int v274; // eax
  unsigned __int64 v275; // r10
  _DWORD *v276; // rdx
  unsigned int v277; // r8d
  char *v278; // rax
  unsigned __int64 v279; // rdi
  unsigned int v280; // eax
  unsigned int v281; // esi
  unsigned int v282; // r8d
  unsigned int v283; // ebx
  unsigned __int64 v284; // rax
  char *v285; // r11
  _DWORD *v286; // rcx
  int v287; // r9d
  unsigned int v288; // r11d
  unsigned __int64 v289; // r14
  _DWORD *v290; // rbx
  unsigned int *v291; // r13
  unsigned __int64 v292; // r12
  char *v293; // rdi
  char *v294; // rdx
  char *v295; // r9
  _QWORD *v296; // r8
  unsigned __int64 v297; // rax
  unsigned __int64 v298; // rbx
  unsigned int v299; // eax
  __int64 v300; // rdx
  __int64 v301; // r9
  char *v302; // r14
  char *v303; // r8
  __int64 v304; // rsi
  __int64 v305; // r11
  _DWORD *v306; // rcx
  unsigned __int64 v307; // r11
  _DWORD *v308; // rcx
  unsigned int *v309; // rax
  _DWORD *v310; // rcx
  int *v311; // r15
  unsigned int v312; // edi
  __int64 v313; // rdx
  __int64 v314; // r13
  __int64 v315; // r8
  int v316; // eax
  _DWORD *v317; // r9
  unsigned int *v318; // r14
  unsigned int v319; // r10d
  unsigned int v320; // edi
  unsigned int v321; // r12d
  unsigned int v322; // esi
  __int64 v323; // rcx
  int v324; // eax
  _DWORD *v325; // r8
  __int128 v326; // xmm0
  __int64 v327; // xmm1_8
  __int64 v328; // rdx
  __int64 v329; // r8
  unsigned int v330; // ecx
  unsigned int v331; // eax
  __int64 v332; // r13
  unsigned __int64 v333; // r8
  __int64 v334; // rcx
  int v335; // ebx
  __int64 v336; // rdx
  unsigned int v337; // edi
  unsigned int v338; // r15d
  unsigned __int64 v339; // rcx
  unsigned int v340; // edi
  _DWORD *v341; // rax
  unsigned __int64 v342; // r13
  unsigned int *v343; // r12
  unsigned int v344; // ebx
  unsigned int v345; // esi
  __int64 updated; // rax
  int v347; // r11d
  __int64 v348; // xmm1_8
  int v349; // r15d
  __int64 v350; // r13
  __int64 v351; // r8
  __int64 v352; // r9
  unsigned int v353; // ecx
  int v354; // edx
  __int64 v355; // rax
  int v356; // r10d
  unsigned int v357; // eax
  __int64 v358; // rax
  __int64 v359; // rdx
  _DWORD *v360; // r9
  __int64 v361; // rcx
  unsigned int v362; // eax
  __int64 v363; // r13
  unsigned int v364; // edi
  unsigned int v365; // eax
  __int64 v366; // r15
  unsigned int *v367; // r12
  _DWORD *v368; // r14
  unsigned int v369; // esi
  int v370; // ebx
  int v371; // ebx
  int v372; // eax
  _BOOL8 v373; // r8
  int v374; // eax
  _DWORD *v375; // rbx
  int v376; // r15d
  __int64 v377; // xmm0_8
  int v378; // eax
  int v379; // eax
  BOOL v380; // ecx
  __int64 v381; // rbx
  __int64 v382; // r15
  int v383; // r14d
  unsigned int v384; // esi
  int v385; // r11d
  __int64 v386; // r9
  __int64 v387; // r8
  __int64 v388; // rdx
  unsigned int v389; // eax
  unsigned int v390; // esi
  __int64 v391; // rax
  __int64 v392; // r8
  unsigned int v393; // r13d
  __int64 v394; // rbx
  unsigned __int64 v395; // r10
  char v396; // cl
  __int64 v397; // r9
  unsigned int v398; // ecx
  unsigned int v399; // r8d
  unsigned int v400; // edx
  int v401; // ecx
  int v402; // r12d
  int v403; // eax
  int v404; // ecx
  int v405; // eax
  unsigned int v406; // r8d
  int v407; // eax
  _DWORD *v408; // rcx
  unsigned int v409; // edx
  unsigned int v410; // r14d
  unsigned int v411; // r10d
  unsigned int *v412; // r15
  unsigned int v413; // eax
  __int64 v414; // r9
  int v415; // eax
  __int64 v416; // rcx
  __int64 v417; // r9
  unsigned int v418; // r11d
  char *v419; // rdx
  __int64 v420; // r8
  unsigned __int64 v421; // rcx
  _QWORD *v422; // r8
  char *v423; // r9
  unsigned __int64 v424; // rax
  int v425; // eax
  int v426; // edx
  int v427; // r9d
  int v428; // eax
  __int64 v429; // rdx
  __int64 v430; // rcx
  _DWORD *v431; // r11
  unsigned __int64 v432; // r8
  __int64 v433; // rsi
  char *v434; // rdx
  unsigned __int64 v435; // rcx
  __int64 v436; // r11
  _DWORD *v437; // rcx
  char *v438; // rax
  char *v439; // r9
  unsigned int v440; // r11d
  unsigned __int64 v441; // r14
  unsigned __int64 v442; // r15
  unsigned __int64 v443; // rbx
  _DWORD *v444; // r10
  char *v445; // r12
  char *v446; // rsi
  char *v447; // rdx
  char *v448; // r9
  char *v449; // r8
  unsigned __int64 v450; // rax
  unsigned __int64 v451; // rbx
  unsigned int v452; // eax
  __int64 v453; // rdx
  __int64 v454; // r9
  char *v455; // r15
  char *v456; // r8
  __int64 v457; // r14
  __int64 v458; // r11
  __int64 v459; // rcx
  unsigned __int64 v460; // r11
  _DWORD *v461; // rcx
  int v462; // eax
  unsigned int *v463; // rax
  unsigned int *v464; // rax
  unsigned int v465; // esi
  __int64 v466; // rax
  __int64 v467; // r8
  unsigned int v468; // r13d
  __int64 v469; // rbx
  unsigned __int64 v470; // r14
  char v471; // cl
  __int64 v472; // r9
  unsigned int v473; // ecx
  unsigned int v474; // r8d
  unsigned int v475; // edx
  int v476; // ecx
  int v477; // r10d
  int v478; // eax
  int v479; // ecx
  int v480; // eax
  unsigned int v481; // r8d
  int v482; // eax
  _DWORD *v483; // rcx
  unsigned int v484; // edx
  unsigned int v485; // r14d
  unsigned int v486; // r12d
  unsigned int *v487; // r15
  unsigned int v488; // eax
  __int64 v489; // r9
  int v490; // eax
  __int64 v491; // rcx
  __int64 v492; // r9
  unsigned int v493; // r11d
  char *v494; // rsi
  char *v495; // rdx
  _QWORD *v496; // r8
  unsigned __int64 v497; // rax
  __int64 v498; // r9
  int v499; // eax
  int v500; // edx
  int v501; // r9d
  int v502; // eax
  __int64 v503; // rdx
  __int64 v504; // rcx
  _DWORD *v505; // r11
  __int64 v506; // r8
  __int64 v507; // rsi
  char *v508; // rdx
  __int64 v509; // rax
  __int64 v510; // rcx
  __int64 v511; // r11
  __int64 v512; // rcx
  int v513; // eax
  _DWORD *v514; // rcx
  unsigned int *v515; // r9
  unsigned int v516; // r14d
  unsigned int v517; // r11d
  unsigned __int64 v518; // r15
  unsigned __int64 v519; // rbx
  _DWORD *v520; // r10
  char *v521; // rdx
  char *v522; // r12
  char *v523; // r9
  char *v524; // rsi
  char *v525; // r8
  unsigned __int64 v526; // rax
  unsigned __int64 v527; // rbx
  unsigned int v528; // eax
  __int64 v529; // rdx
  __int64 v530; // r9
  char *v531; // r15
  char *v532; // r8
  __int64 v533; // r14
  __int64 v534; // r11
  __int64 v535; // rcx
  unsigned __int64 v536; // r11
  _DWORD *v537; // rcx
  unsigned int *v538; // rax
  unsigned int v539; // eax
  unsigned int v540; // esi
  __int64 v541; // rax
  __int64 v542; // r8
  unsigned int v543; // r13d
  __int64 v544; // rbx
  unsigned __int64 v545; // r10
  char v546; // cl
  __int64 v547; // r9
  unsigned int v548; // ecx
  unsigned int v549; // r8d
  unsigned int v550; // edx
  int v551; // ecx
  int v552; // r12d
  int v553; // eax
  int v554; // ecx
  int v555; // eax
  unsigned int v556; // r8d
  int v557; // eax
  _DWORD *v558; // rcx
  unsigned int v559; // edx
  unsigned int v560; // r14d
  unsigned int v561; // r10d
  unsigned int *v562; // r15
  unsigned int v563; // eax
  __int64 v564; // r9
  int v565; // eax
  __int64 v566; // rcx
  __int64 v567; // r9
  unsigned int v568; // r11d
  char *v569; // rdx
  __int64 v570; // r8
  unsigned __int64 v571; // rcx
  _QWORD *v572; // r8
  char *v573; // r9
  unsigned __int64 v574; // rax
  int v575; // eax
  int v576; // edx
  int v577; // r9d
  int v578; // eax
  __int64 v579; // rdx
  __int64 v580; // rcx
  _DWORD *v581; // r11
  unsigned __int64 v582; // r8
  __int64 v583; // rsi
  char *v584; // rdx
  unsigned __int64 v585; // rcx
  __int64 v586; // r11
  _DWORD *v587; // rcx
  char *v588; // rax
  char *v589; // r9
  unsigned int v590; // r11d
  unsigned __int64 v591; // r14
  unsigned __int64 v592; // r15
  unsigned __int64 v593; // rbx
  _DWORD *v594; // r10
  char *v595; // r12
  char *v596; // rsi
  char *v597; // rdx
  char *v598; // r9
  char *v599; // r8
  unsigned __int64 v600; // rax
  unsigned __int64 v601; // rbx
  unsigned int v602; // eax
  __int64 v603; // rdx
  __int64 v604; // r9
  char *v605; // r15
  char *v606; // r8
  __int64 v607; // r14
  __int64 v608; // r11
  __int64 v609; // rcx
  unsigned __int64 v610; // r11
  _DWORD *v611; // rcx
  int v612; // eax
  unsigned int v613; // eax
  unsigned int v614; // ebx
  __int64 v615; // rax
  __int64 v616; // r8
  unsigned int v617; // r13d
  unsigned __int64 v618; // rsi
  __int64 v619; // r10
  char v620; // cl
  unsigned int v621; // r8d
  __int64 v622; // r9
  unsigned int v623; // r9d
  unsigned int v624; // ecx
  unsigned int v625; // edx
  int v626; // r12d
  int v627; // eax
  int v628; // ecx
  int v629; // eax
  _DWORD *v630; // rcx
  unsigned int v631; // edx
  unsigned int v632; // r14d
  unsigned int v633; // r10d
  unsigned int *v634; // r15
  unsigned int v635; // eax
  unsigned int v636; // r8d
  int v637; // eax
  __int64 v638; // rcx
  __int64 v639; // r10
  unsigned int v640; // r11d
  int v641; // r8d
  char *v642; // rdx
  __int64 v643; // r9
  _DWORD *v644; // r8
  unsigned __int64 v645; // rax
  int v646; // eax
  int v647; // eax
  int v648; // edx
  int v649; // r9d
  __int64 v650; // r8
  int v651; // eax
  __int64 v652; // rdx
  __int64 v653; // rcx
  __int64 v654; // r11
  int v655; // r8d
  unsigned __int64 v656; // r8
  __int64 v657; // rsi
  __int64 v658; // rdx
  unsigned __int64 v659; // rcx
  __int64 v660; // rbx
  __int64 v661; // r11
  unsigned __int64 v662; // r8
  __int64 v663; // rax
  _DWORD *v664; // rcx
  unsigned int *v665; // r14
  unsigned int FirstIndexHash3; // eax
  unsigned int v667; // r8d
  unsigned int v668; // ebx
  unsigned __int64 v669; // rax
  int v670; // r11d
  char *v671; // r9
  _DWORD *v672; // rcx
  int v673; // edx
  int v674; // r14d
  unsigned int v675; // r11d
  _DWORD *v676; // r15
  _DWORD *v677; // rbx
  _DWORD *v678; // r10
  char *v679; // r12
  char *v680; // rsi
  char *v681; // rdx
  char *v682; // r9
  _QWORD *v683; // r8
  unsigned __int64 v684; // rax
  unsigned __int64 v685; // rbx
  unsigned int v686; // eax
  __int64 v687; // rdx
  __int64 v688; // r9
  char *v689; // r15
  char *v690; // r8
  __int64 v691; // r14
  __int64 v692; // r11
  __int64 v693; // rcx
  unsigned __int64 v694; // r11
  _DWORD *v695; // rcx
  _DWORD *v696; // rax
  _DWORD *v697; // r14
  unsigned int v698; // ebx
  unsigned int v699; // ecx
  unsigned int v700; // r13d
  unsigned int *v701; // r10
  unsigned int v702; // r15d
  __int64 v703; // rax
  unsigned int *v704; // r10
  unsigned int v705; // edx
  unsigned int v706; // r11d
  __int64 v707; // xmm1_8
  unsigned int v708; // r14d
  __int64 v709; // r13
  unsigned int v710; // eax
  int v711; // esi
  unsigned int v712; // ebx
  __int64 v713; // r9
  __int64 v714; // r10
  unsigned int v715; // edx
  signed int v716; // r8d
  unsigned int v717; // ecx
  int v718; // r11d
  unsigned int v719; // ecx
  __int64 v720; // rcx
  __int64 v721; // r8
  int v722; // edx
  __int64 v723; // rcx
  __int64 v724; // rdx
  _DWORD *v725; // rdx
  __int64 v726; // rdx
  __int128 v727; // xmm0
  unsigned int v728; // eax
  int v729; // eax
  __int64 v730; // rax
  unsigned int v731; // ecx
  __int64 v732; // rcx
  int v733; // r8d
  unsigned int v734; // r14d
  unsigned __int64 v735; // rdx
  unsigned __int64 v736; // rbx
  __int64 v737; // rcx
  unsigned __int64 v738; // rdx
  __int64 v739; // r10
  __int64 v740; // rcx
  unsigned __int64 v741; // rax
  __int64 v742; // rcx
  unsigned __int64 v743; // rcx
  __int64 v744; // rcx
  unsigned __int64 v745; // rax
  __int64 v746; // rcx
  __int64 v747; // rcx
  __int64 v748; // rcx
  char *v750; // [rsp+30h] [rbp-D0h]
  unsigned int v751; // [rsp+38h] [rbp-C8h] BYREF
  int v752; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned int v753; // [rsp+40h] [rbp-C0h]
  unsigned int *v754; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v755; // [rsp+50h] [rbp-B0h]
  unsigned int v756; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v757; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v758; // [rsp+68h] [rbp-98h]
  unsigned __int64 v759; // [rsp+70h] [rbp-90h]
  BOOL v760; // [rsp+78h] [rbp-88h]
  unsigned __int64 v761; // [rsp+80h] [rbp-80h]
  unsigned int v762; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v763; // [rsp+8Ch] [rbp-74h]
  unsigned int v764; // [rsp+90h] [rbp-70h]
  _DWORD *v765; // [rsp+98h] [rbp-68h]
  unsigned __int64 v766; // [rsp+A0h] [rbp-60h]
  unsigned int v767; // [rsp+A8h] [rbp-58h]
  _DWORD *v768; // [rsp+B0h] [rbp-50h]
  unsigned int v769; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int *v770; // [rsp+C0h] [rbp-40h]
  _DWORD *v771; // [rsp+C8h] [rbp-38h]
  int v772; // [rsp+D0h] [rbp-30h]
  _DWORD *v773; // [rsp+D8h] [rbp-28h]
  unsigned int v774; // [rsp+E0h] [rbp-20h]
  int v775; // [rsp+E4h] [rbp-1Ch] BYREF
  unsigned int v776; // [rsp+E8h] [rbp-18h] BYREF
  unsigned int v777; // [rsp+ECh] [rbp-14h] BYREF
  unsigned int *v778; // [rsp+F0h] [rbp-10h]
  _DWORD *v779; // [rsp+F8h] [rbp-8h]
  _DWORD *v780; // [rsp+100h] [rbp+0h]
  _DWORD *v781; // [rsp+108h] [rbp+8h]
  int v782; // [rsp+110h] [rbp+10h]
  unsigned __int64 v783; // [rsp+118h] [rbp+18h]
  __int64 v784; // [rsp+120h] [rbp+20h]
  unsigned __int64 v785; // [rsp+128h] [rbp+28h]
  int v786; // [rsp+130h] [rbp+30h] BYREF
  unsigned int v787; // [rsp+134h] [rbp+34h]
  int v788; // [rsp+138h] [rbp+38h]
  __int64 v789; // [rsp+140h] [rbp+40h]
  unsigned __int64 v790; // [rsp+148h] [rbp+48h]
  __int128 v791; // [rsp+150h] [rbp+50h]
  __int64 v792; // [rsp+160h] [rbp+60h]
  int v793; // [rsp+168h] [rbp+68h]
  int v794; // [rsp+170h] [rbp+70h]
  __int128 v795; // [rsp+180h] [rbp+80h] BYREF
  __int64 v796; // [rsp+190h] [rbp+90h]
  int v797; // [rsp+198h] [rbp+98h]
  __int128 v798; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v799; // [rsp+1B0h] [rbp+B0h]
  int v800; // [rsp+1B8h] [rbp+B8h]
  __int128 v801; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v802; // [rsp+1D0h] [rbp+D0h]
  int v803; // [rsp+1D8h] [rbp+D8h]
  char v804[16]; // [rsp+1E0h] [rbp+E0h] BYREF
  char v805[24]; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned __int64 v809; // [rsp+268h] [rbp+168h]
  unsigned int v810; // [rsp+270h] [rbp+170h]
  unsigned int v811; // [rsp+270h] [rbp+170h]
  unsigned int *v812; // [rsp+270h] [rbp+170h]
  unsigned int v813; // [rsp+270h] [rbp+170h]

  v809 = a4;
  v5 = *(_DWORD *)(a1 + 204);
  v6 = a1 + 72;
  v7 = a1;
  v8 = *(_QWORD *)(a1 + 8) + *(unsigned int *)(a1 + 24);
  v9 = a4;
  v10 = 4095;
  v784 = v6;
  if ( v5 < 0xFFF )
    v10 = v5;
  v11 = *(_DWORD *)(v7 + 200) == 3;
  v12 = (char *)(a4 + a5);
  v787 = v10;
  v13 = a4 + a5 - 8;
  v750 = (char *)(a4 + a5);
  v790 = v13;
  v782 = !v11 + 3;
  v786 = *(_DWORD *)(v7 + 36);
  v779 = *(_DWORD **)(v6 + 40);
  v773 = *(_DWORD **)(v6 + 32);
  ZSTD_rescaleFreqs(v6, a4, a5, 0);
  v14 = v9 + (v9 == v8);
  v766 = v14;
  if ( v14 < v13 )
  {
    v15 = v792;
    v788 = v793;
    while ( 1 )
    {
      v16 = *(unsigned int *)(v7 + 36);
      v17 = *(_QWORD *)(v7 + 8);
      v18 = v14 - v9;
      v11 = (_DWORD)v14 == (_DWORD)v9;
      v19 = *(_DWORD *)(v7 + 200);
      v20 = v11;
      v763 = v18;
      v760 = v11;
      if ( v14 < v17 + v16 )
        goto LABEL_869;
      v21 = v14 - v17;
      if ( (unsigned int)v16 < (int)v14 - (int)v17 )
      {
        do
          LODWORD(v16) = ZSTD_insertBt1(a1, (int)v17 + (int)v16, (_DWORD)v12, v19, 1) + v16;
        while ( (unsigned int)v16 < v21 );
        v20 = v760;
        v14 = v766;
      }
      v22 = 4095;
      v23 = *(_QWORD *)(a1 + 48);
      *(_DWORD *)(a1 + 36) = v21;
      v24 = *(unsigned int *)(a1 + 192);
      if ( v19 == 3 )
        break;
      v25 = *(_DWORD **)(a1 + 8);
      v768 = v25;
      if ( v19 == 5 )
      {
        if ( *(_DWORD *)(a1 + 204) < 0xFFFu )
          v22 = *(_DWORD *)(a1 + 204);
        v753 = v14 - (_DWORD)v25;
        v165 = ZSTD_hash5Ptr(v14, v24, v23);
        v168 = *(_DWORD *)(v167 + 4 * v165);
        v169 = *(_DWORD **)(a1 + 64);
        v170 = *(_DWORD *)(a1 + 188) - 1;
        v778 = (unsigned int *)(v167 + 4 * v165);
        v754 = *(unsigned int **)(a1 + 16);
        LODWORD(v167) = 1 << v170;
        v171 = 0;
        v172 = v167 - 1;
        v758 = v173;
        v759 = v173;
        v174 = (_DWORD *)*(unsigned int *)(a1 + 24);
        v771 = v169;
        v764 = v172;
        v772 = (int)v174;
        v765 = v174;
        v770 = (_DWORD *)((char *)v174 + v175);
        if ( v172 < v166 )
          v171 = v166 - v172;
        v767 = v171;
        v176 = 1 << *(_DWORD *)(a1 + 184);
        v177 = v166 - v176;
        v178 = 1;
        if ( v166 - *(_DWORD *)(a1 + 28) <= v176 )
          v177 = *(_DWORD *)(a1 + 28);
        if ( *(_DWORD *)(a1 + 32) )
          v177 = *(_DWORD *)(a1 + 28);
        v179 = *(_DWORD *)(a1 + 196);
        if ( v177 )
          v178 = v177;
        v774 = v178;
        v180 = v20 + 3;
        v810 = 0;
        v757 = (unsigned __int64)&v169[2 * (v166 & v172)];
        v761 = v757 + 4;
        v752 = v166 + 9;
        v181 = 1 << v179;
        v182 = a3;
        v751 = v181;
        v785 = (unsigned int)(v782 - 1);
        v183 = v166 - (_DWORD)v174;
        v755 = v785;
        v184 = v760;
        v185 = (unsigned int *)&a3[v760];
        while ( 1 )
        {
          if ( v184 == 3 )
            v186 = *v182 - 1;
          else
            v186 = *v185;
          v187 = v166 - v186;
          v188 = 0;
          if ( v186 - 1 >= v183 )
          {
            if ( v186 - 1 < v753 - v177 && (unsigned int)((_DWORD)v174 - v187 - 1) >= 3 )
            {
              MINMATCH = ZSTD_readMINMATCH(v766, 4, 0, v187);
              if ( MINMATCH == *v203 )
              {
                v204 = ZSTD_count_2segments(v202 + 4, (int)v203 + 4, (_DWORD)v750, (int)v765 + (int)v754, (__int64)v770);
                LODWORD(v174) = v772;
                v188 = v204 + 4;
              }
            }
            v166 = v753;
            goto LABEL_226;
          }
          v189 = ZSTD_readMINMATCH(v766, 4, 0, -(__int64)v186);
          if ( v189 == *(_DWORD *)(v191 + v190) )
          {
            v192 = (char *)(v190 + 4);
            v193 = v190 + 4;
            v194 = (unsigned __int64)v750;
            v195 = (_QWORD *)(v191 + v193);
            v196 = v192;
            v197 = (unsigned __int64)(v750 - 7);
            if ( v192 >= v750 - 7 )
              goto LABEL_211;
            if ( *(_QWORD *)v192 == *v195 )
            {
              v192 += 8;
              ++v195;
              if ( (unsigned __int64)v192 < v197 )
              {
                while ( *(_QWORD *)v192 == *v195 )
                {
                  v192 += 8;
                  ++v195;
                  if ( (unsigned __int64)v192 >= v197 )
                    goto LABEL_210;
                }
                v198 = ZSTD_NbCommonBytes(*(_QWORD *)v192 ^ *v195, v192, v195, v196);
                v188 = v199 - v200 + v198 + 4;
                goto LABEL_226;
              }
LABEL_210:
              v194 = (unsigned __int64)v750;
LABEL_211:
              if ( (unsigned __int64)v192 < v194 - 3 && *(_DWORD *)v195 == *(_DWORD *)v192 )
              {
                v192 += 4;
                v195 = (_QWORD *)((char *)v195 + 4);
              }
              if ( (unsigned __int64)v192 < v194 - 1 && *(_WORD *)v195 == *(_WORD *)v192 )
              {
                v192 += 2;
                v195 = (_QWORD *)((char *)v195 + 2);
              }
              if ( (unsigned __int64)v192 < v194 && *(_BYTE *)v195 == *v192 )
                LODWORD(v192) = (_DWORD)v192 + 1;
              v188 = (_DWORD)v192 - (_DWORD)v196 + 4;
              goto LABEL_226;
            }
            v188 = ZSTD_NbCommonBytes(*(_QWORD *)v192 ^ *v195, v192, v195, v192) + 4;
          }
LABEL_226:
          if ( v188 <= v755 )
          {
            v207 = v750;
          }
          else
          {
            v205 = &v773[2 * v810];
            *v205 = v184 - v760;
            v755 = v188;
            v206 = (char *)(v766 + v188);
            ++v810;
            v207 = v750;
            v205[1] = v188;
            if ( v188 > v22 || v206 == v750 )
              goto LABEL_187;
          }
          v182 = a3;
          ++v184;
          ++v185;
          if ( v184 >= v180 )
          {
            *v778 = v166;
            v208 = v751;
            if ( !v751 )
              goto LABEL_185;
            v209 = v758;
            v210 = v766;
            v211 = v758;
            while ( 2 )
            {
              v751 = --v208;
              if ( v168 < v774 )
                goto LABEL_185;
              v212 = v211;
              if ( v209 < v211 )
                v212 = v209;
              v213 = &v771[2 * (v168 & v764)];
              if ( v212 + v168 < (unsigned __int64)v765 )
              {
                v224 = v212 + v210;
                v215 = (char *)v754 + v168;
                v225 = v207;
                if ( (char *)v765 + v224 - (v168 + v212) < v207 )
                  v225 = (char *)v765 + v224 - (v168 + v212);
                v226 = ZSTD_count(v224, (char *)v754 + v168 + v212, v225);
                v228 = (_DWORD *)(v226 + v227);
                v229 = (unsigned __int64)v765;
                if ( v228 == (unsigned int *)((char *)v754 + (_QWORD)v765) )
                  v226 += ZSTD_count(v226 + v224, v770, v750);
                v208 = v751;
                v220 = v226 + v212;
                v211 = v759;
                v210 = v766;
                v92 = v220 + v168 < v229;
                v209 = v758;
                if ( !v92 )
                  v215 = (char *)v768 + v168;
                v217 = v750;
                goto LABEL_261;
              }
              v214 = (char *)(v212 + v210);
              v215 = (char *)v768 + v168;
              v216 = v212 + v210;
              v217 = v750;
              v218 = &v215[v212];
              v219 = (unsigned __int64)(v750 - 7);
              if ( v212 + v210 < (unsigned __int64)(v750 - 7) )
              {
                if ( *(_QWORD *)v214 != *(_QWORD *)v218 )
                {
                  v220 = (unsigned int)ZSTD_NbCommonBytes(*(_QWORD *)v214 ^ *(_QWORD *)v218, v214, v218, v216) + v212;
LABEL_261:
                  if ( v220 > v755 )
                  {
                    if ( v220 > v752 - v168 )
                      v752 = v168 + v220;
                    v230 = v773;
                    v231 = v753 - v168 + 2;
                    v773[2 * v810 + 1] = v220;
                    v230[2 * v810] = v231;
                    v755 = v220;
                    ++v810;
                    if ( v220 > 0x1000 || v220 + v210 == (_QWORD)v217 )
                      goto LABEL_185;
                  }
                  if ( (unsigned __int8)v215[v220] >= *(_BYTE *)(v220 + v210) )
                  {
                    v211 = v220;
                    v759 = v220;
                    *(_DWORD *)v761 = v168;
                    if ( v168 <= v767 )
                    {
                      v96 = &v751;
LABEL_184:
                      v761 = (unsigned __int64)v96;
                      goto LABEL_185;
                    }
                    v168 = *v213;
                    v761 = (unsigned __int64)v213;
                  }
                  else
                  {
                    v209 = v220;
                    v758 = v220;
                    *(_DWORD *)v757 = v168;
                    if ( v168 <= v767 )
                    {
                      v95 = &v751;
                      goto LABEL_186;
                    }
                    v168 = v213[1];
                    v757 = (unsigned __int64)(v213 + 1);
                  }
                  if ( !v208 )
                    goto LABEL_185;
                  v207 = v750;
                  continue;
                }
                v214 += 8;
                v218 += 8;
                if ( (unsigned __int64)v214 < v219 )
                {
                  while ( *(_QWORD *)v214 == *(_QWORD *)v218 )
                  {
                    v214 += 8;
                    v218 += 8;
                    if ( (unsigned __int64)v214 >= v219 )
                      goto LABEL_243;
                  }
                  v221 = ZSTD_NbCommonBytes(*(_QWORD *)v214 ^ *(_QWORD *)v218, v214, v218, v216);
                  v220 = v222 - v223 + v221 + v212;
                  goto LABEL_261;
                }
              }
              break;
            }
LABEL_243:
            if ( v214 < v750 - 3 && *(_DWORD *)v218 == *(_DWORD *)v214 )
            {
              v214 += 4;
              v218 += 4;
            }
            if ( v214 < v750 - 1 && *(_WORD *)v218 == *(_WORD *)v214 )
            {
              v214 += 2;
              v218 += 2;
            }
            if ( v214 < v750 && *v218 == *v214 )
              ++v214;
            v220 = (unsigned __int64)&v214[-v210];
            goto LABEL_261;
          }
        }
      }
      v26 = *(_DWORD *)(a1 + 204);
      if ( (unsigned int)(v19 - 6) > 1 )
      {
        if ( v26 < 0xFFF )
          v22 = *(_DWORD *)(a1 + 204);
        v753 = v14 - (_DWORD)v25;
        v97 = ZSTD_hash4Ptr(v14, v24, v23);
        v100 = *(_DWORD *)(v99 + 4 * v97);
        v101 = *(_DWORD **)(a1 + 64);
        v102 = *(_DWORD *)(a1 + 188) - 1;
        v778 = (unsigned int *)(v99 + 4 * v97);
        v754 = *(unsigned int **)(a1 + 16);
        LODWORD(v99) = 1 << v102;
        v103 = 0;
        v104 = v99 - 1;
        v758 = v105;
        v759 = v105;
        v106 = (_DWORD *)*(unsigned int *)(a1 + 24);
        v771 = v101;
        v764 = v104;
        v772 = (int)v106;
        v765 = v106;
        v770 = (_DWORD *)((char *)v106 + v107);
        if ( v104 < v98 )
          v103 = v98 - v104;
        v767 = v103;
        v108 = 1 << *(_DWORD *)(a1 + 184);
        v109 = v98 - v108;
        v110 = 1;
        if ( v98 - *(_DWORD *)(a1 + 28) <= v108 )
          v109 = *(_DWORD *)(a1 + 28);
        if ( *(_DWORD *)(a1 + 32) )
          v109 = *(_DWORD *)(a1 + 28);
        v111 = *(_DWORD *)(a1 + 196);
        if ( v109 )
          v110 = v109;
        v774 = v110;
        v112 = v20 + 3;
        v810 = 0;
        v757 = (unsigned __int64)&v101[2 * (v98 & v104)];
        v761 = v757 + 4;
        v752 = v98 + 9;
        v113 = 1 << v111;
        v114 = a3;
        v751 = v113;
        v785 = (unsigned int)(v782 - 1);
        v115 = v98 - (_DWORD)v106;
        v755 = v785;
        v116 = v760;
        v117 = (unsigned int *)&a3[v760];
        while ( 1 )
        {
          if ( v116 == 3 )
            v118 = *v114 - 1;
          else
            v118 = *v117;
          v119 = v98 - v118;
          v120 = 0;
          if ( v118 - 1 >= v115 )
          {
            if ( v118 - 1 < v753 - v109 && (unsigned int)((_DWORD)v106 - v119 - 1) >= 3 )
            {
              v133 = ZSTD_readMINMATCH(v766, 4, 0, v119);
              if ( v133 == *v135 )
              {
                v136 = ZSTD_count_2segments(v134 + 4, (int)v135 + 4, (_DWORD)v750, (int)v765 + (int)v754, (__int64)v770);
                LODWORD(v106) = v772;
                v120 = v136 + 4;
              }
            }
            v98 = v753;
            goto LABEL_136;
          }
          v121 = ZSTD_readMINMATCH(v766, 4, 0, -(__int64)v118);
          if ( v121 == *(_DWORD *)(v123 + v122) )
          {
            v124 = (char *)(v122 + 4);
            v125 = v122 + 4;
            v126 = (unsigned __int64)v750;
            v127 = (_QWORD *)(v123 + v125);
            v128 = v124;
            v129 = (unsigned __int64)(v750 - 7);
            if ( v124 >= v750 - 7 )
              goto LABEL_121;
            if ( *v127 == *(_QWORD *)v124 )
            {
              v124 += 8;
              ++v127;
              if ( (unsigned __int64)v124 < v129 )
              {
                while ( *v127 == *(_QWORD *)v124 )
                {
                  v124 += 8;
                  ++v127;
                  if ( (unsigned __int64)v124 >= v129 )
                    goto LABEL_120;
                }
                v130 = ZSTD_NbCommonBytes(*v127 ^ *(_QWORD *)v124, v124, v127, v128);
                v120 = v131 - v132 + v130 + 4;
                goto LABEL_136;
              }
LABEL_120:
              v126 = (unsigned __int64)v750;
LABEL_121:
              if ( (unsigned __int64)v124 < v126 - 3 && *(_DWORD *)v127 == *(_DWORD *)v124 )
              {
                v124 += 4;
                v127 = (_QWORD *)((char *)v127 + 4);
              }
              if ( (unsigned __int64)v124 < v126 - 1 && *(_WORD *)v127 == *(_WORD *)v124 )
              {
                v124 += 2;
                v127 = (_QWORD *)((char *)v127 + 2);
              }
              if ( (unsigned __int64)v124 < v126 && *(_BYTE *)v127 == *v124 )
                LODWORD(v124) = (_DWORD)v124 + 1;
              v120 = (_DWORD)v124 - (_DWORD)v128 + 4;
              goto LABEL_136;
            }
            v120 = ZSTD_NbCommonBytes(*v127 ^ *(_QWORD *)v124, v124, v127, v124) + 4;
          }
LABEL_136:
          if ( v120 <= v755 )
          {
            v139 = v750;
          }
          else
          {
            v137 = &v773[2 * v810];
            *v137 = v116 - v760;
            v755 = v120;
            v138 = (char *)(v766 + v120);
            ++v810;
            v139 = v750;
            v137[1] = v120;
            if ( v120 > v22 || v138 == v750 )
              goto LABEL_187;
          }
          v114 = a3;
          ++v116;
          ++v117;
          if ( v116 >= v112 )
          {
            *v778 = v98;
            v140 = v751;
            if ( !v751 )
              goto LABEL_185;
            v141 = v758;
            v142 = v766;
            v143 = v758;
            while ( 2 )
            {
              v751 = --v140;
              if ( v100 < v774 )
                goto LABEL_185;
              v144 = v143;
              if ( v141 < v143 )
                v144 = v141;
              v145 = &v771[2 * (v100 & v764)];
              if ( v100 + v144 < (unsigned __int64)v765 )
              {
                v156 = v144 + v142;
                v157 = v139;
                v147 = (char *)v754 + v100;
                if ( (char *)v765 + v156 - v144 - v100 < v139 )
                  v157 = (char *)v765 + v156 - v144 - v100;
                v158 = ZSTD_count(v156, (char *)v754 + v100 + v144, v157);
                v160 = (_DWORD *)(v158 + v159);
                v161 = (unsigned __int64)v765;
                if ( v160 == (unsigned int *)((char *)v754 + (_QWORD)v765) )
                  v158 += ZSTD_count(v158 + v156, v770, v750);
                v140 = v751;
                v152 = v158 + v144;
                v143 = v759;
                v142 = v766;
                v92 = v100 + v152 < v161;
                v141 = v758;
                if ( !v92 )
                  v147 = (char *)v768 + v100;
                v149 = v750;
                goto LABEL_171;
              }
              v146 = (char *)(v144 + v142);
              v147 = (char *)v768 + v100;
              v148 = v144 + v142;
              v149 = v750;
              v150 = &v147[v144];
              v151 = (unsigned __int64)(v750 - 7);
              if ( v144 + v142 < (unsigned __int64)(v750 - 7) )
              {
                if ( *(_QWORD *)v150 != *(_QWORD *)v146 )
                {
                  v152 = (unsigned int)ZSTD_NbCommonBytes(*(_QWORD *)v150 ^ *(_QWORD *)v146, v146, v150, v148) + v144;
LABEL_171:
                  if ( v152 > v755 )
                  {
                    if ( v152 > v752 - v100 )
                      v752 = v152 + v100;
                    v162 = v773;
                    v163 = v753 - v100 + 2;
                    v773[2 * v810 + 1] = v152;
                    v162[2 * v810] = v163;
                    v755 = v152;
                    ++v810;
                    if ( v152 > 0x1000 || v152 + v142 == (_QWORD)v149 )
                      goto LABEL_185;
                  }
                  if ( (unsigned __int8)v147[v152] >= *(_BYTE *)(v152 + v142) )
                  {
                    v143 = v152;
                    v759 = v152;
                    *(_DWORD *)v761 = v100;
                    if ( v100 <= v767 )
                    {
                      v96 = &v762;
                      goto LABEL_184;
                    }
                    v100 = *v145;
                    v761 = (unsigned __int64)v145;
                  }
                  else
                  {
                    v141 = v152;
                    v758 = v152;
                    *(_DWORD *)v757 = v100;
                    if ( v100 <= v767 )
                    {
                      v95 = &v762;
                      goto LABEL_186;
                    }
                    v100 = v145[1];
                    v757 = (unsigned __int64)(v145 + 1);
                  }
                  if ( !v140 )
                    goto LABEL_185;
                  v139 = v750;
                  continue;
                }
                v146 += 8;
                v150 += 8;
                if ( (unsigned __int64)v146 < v151 )
                {
                  while ( *(_QWORD *)v150 == *(_QWORD *)v146 )
                  {
                    v146 += 8;
                    v150 += 8;
                    if ( (unsigned __int64)v146 >= v151 )
                      goto LABEL_153;
                  }
                  v153 = ZSTD_NbCommonBytes(*(_QWORD *)v150 ^ *(_QWORD *)v146, v146, v150, v148);
                  v152 = v154 - v155 + v153 + v144;
                  goto LABEL_171;
                }
              }
              break;
            }
LABEL_153:
            if ( v146 < v750 - 3 && *(_DWORD *)v150 == *(_DWORD *)v146 )
            {
              v146 += 4;
              v150 += 4;
            }
            if ( v146 < v750 - 1 && *(_WORD *)v150 == *(_WORD *)v146 )
            {
              v146 += 2;
              v150 += 2;
            }
            if ( v146 < v750 && *v150 == *v146 )
              ++v146;
            v152 = (unsigned __int64)&v146[-v142];
            goto LABEL_171;
          }
        }
      }
      if ( v26 < 0xFFF )
        v22 = *(_DWORD *)(a1 + 204);
      v753 = v14 - (_DWORD)v25;
      v27 = ZSTD_hash6Ptr(v14, v24, v23);
      v30 = *(_DWORD *)(v29 + 4 * v27);
      v31 = *(_DWORD **)(a1 + 64);
      v32 = *(_DWORD *)(a1 + 188) - 1;
      v778 = (unsigned int *)(v29 + 4 * v27);
      v754 = *(unsigned int **)(a1 + 16);
      LODWORD(v29) = 1 << v32;
      v33 = 0;
      v34 = v29 - 1;
      v758 = v35;
      v759 = v35;
      v36 = (_DWORD *)*(unsigned int *)(a1 + 24);
      v771 = v31;
      v764 = v34;
      v772 = (int)v36;
      v765 = v36;
      v770 = (_DWORD *)((char *)v36 + v37);
      if ( v34 < v28 )
        v33 = v28 - v34;
      v767 = v33;
      v38 = 1 << *(_DWORD *)(a1 + 184);
      v39 = v28 - v38;
      v40 = 1;
      if ( v28 - *(_DWORD *)(a1 + 28) <= v38 )
        v39 = *(_DWORD *)(a1 + 28);
      if ( *(_DWORD *)(a1 + 32) )
        v39 = *(_DWORD *)(a1 + 28);
      v41 = *(_DWORD *)(a1 + 196);
      if ( v39 )
        v40 = v39;
      v774 = v40;
      v42 = v20 + 3;
      v810 = 0;
      v757 = (unsigned __int64)&v31[2 * (v28 & v34)];
      v761 = v757 + 4;
      v752 = v28 + 9;
      v43 = 1 << v41;
      v44 = a3;
      v751 = v43;
      v785 = (unsigned int)(v782 - 1);
      v45 = v28 - (_DWORD)v36;
      v755 = v785;
      v46 = v760;
      v47 = (unsigned int *)&a3[v760];
      do
      {
        if ( v46 == 3 )
          v48 = *v44 - 1;
        else
          v48 = *v47;
        v49 = v28 - v48;
        v50 = 0;
        if ( v48 - 1 >= v45 )
        {
          if ( v48 - 1 < v753 - v39 && (unsigned int)((_DWORD)v36 - v49 - 1) >= 3 )
          {
            v63 = ZSTD_readMINMATCH(v766, 4, 0, v49);
            if ( v63 == *v65 )
            {
              v66 = ZSTD_count_2segments(v64 + 4, (int)v65 + 4, (_DWORD)v750, (int)v765 + (int)v754, (__int64)v770);
              LODWORD(v36) = v772;
              v50 = v66 + 4;
            }
          }
          v28 = v753;
        }
        else
        {
          v51 = ZSTD_readMINMATCH(v766, 4, 0, -(__int64)v48);
          if ( v51 != *(_DWORD *)(v53 + v52) )
            goto LABEL_50;
          v54 = (char *)(v52 + 4);
          v55 = v52 + 4;
          v56 = (unsigned __int64)v750;
          v57 = (_QWORD *)(v53 + v55);
          v58 = v54;
          v59 = (unsigned __int64)(v750 - 7);
          if ( v54 >= v750 - 7 )
            goto LABEL_35;
          if ( *v57 != *(_QWORD *)v54 )
          {
            v50 = ZSTD_NbCommonBytes(*v57 ^ *(_QWORD *)v54, v54, v57, v54) + 4;
            goto LABEL_50;
          }
          v54 += 8;
          ++v57;
          if ( (unsigned __int64)v54 >= v59 )
          {
LABEL_34:
            v56 = (unsigned __int64)v750;
LABEL_35:
            if ( (unsigned __int64)v54 < v56 - 3 && *(_DWORD *)v57 == *(_DWORD *)v54 )
            {
              v54 += 4;
              v57 = (_QWORD *)((char *)v57 + 4);
            }
            if ( (unsigned __int64)v54 < v56 - 1 && *(_WORD *)v57 == *(_WORD *)v54 )
            {
              v54 += 2;
              v57 = (_QWORD *)((char *)v57 + 2);
            }
            if ( (unsigned __int64)v54 < v56 && *(_BYTE *)v57 == *v54 )
              LODWORD(v54) = (_DWORD)v54 + 1;
            v50 = (_DWORD)v54 - (_DWORD)v58 + 4;
            goto LABEL_50;
          }
          while ( *v57 == *(_QWORD *)v54 )
          {
            v54 += 8;
            ++v57;
            if ( (unsigned __int64)v54 >= v59 )
              goto LABEL_34;
          }
          v60 = ZSTD_NbCommonBytes(*v57 ^ *(_QWORD *)v54, v54, v57, v58);
          v50 = v61 - v62 + v60 + 4;
        }
LABEL_50:
        if ( v50 <= v755 )
        {
          v69 = v750;
        }
        else
        {
          v67 = &v773[2 * v810];
          *v67 = v46 - v760;
          v755 = v50;
          v68 = (char *)(v766 + v50);
          ++v810;
          v69 = v750;
          v67[1] = v50;
          if ( v50 > v22 || v68 == v750 )
            goto LABEL_187;
        }
        v44 = a3;
        ++v46;
        ++v47;
      }
      while ( v46 < v42 );
      *v778 = v28;
      v70 = v751;
      if ( v751 )
      {
        v71 = v758;
        v72 = v766;
        v73 = v758;
        while ( 1 )
        {
          v751 = --v70;
          if ( v30 < v774 )
            break;
          v74 = v73;
          if ( v71 < v73 )
            v74 = v71;
          v75 = &v771[2 * (v30 & v764)];
          if ( v74 + v30 < (unsigned __int64)v765 )
          {
            v86 = v74 + v72;
            v87 = v69;
            v77 = (char *)v754 + v30;
            if ( (char *)v765 + v86 - v74 - v30 < v69 )
              v87 = (char *)v765 + v86 - v74 - v30;
            v88 = ZSTD_count(v86, (char *)v754 + v30 + v74, v87);
            v90 = (_DWORD *)(v88 + v89);
            v91 = (unsigned __int64)v765;
            if ( v90 == (unsigned int *)((char *)v754 + (_QWORD)v765) )
              v88 += ZSTD_count(v88 + v86, v770, v750);
            v70 = v751;
            v82 = v88 + v74;
            v73 = v759;
            v72 = v766;
            v92 = v82 + v30 < v91;
            v71 = v758;
            if ( !v92 )
              v77 = (char *)v768 + v30;
            v79 = v750;
          }
          else
          {
            v76 = (char *)(v74 + v72);
            v77 = (char *)v768 + v30;
            v78 = v74 + v72;
            v79 = v750;
            v80 = &v77[v74];
            v81 = (unsigned __int64)(v750 - 7);
            if ( v74 + v72 >= (unsigned __int64)(v750 - 7) )
              goto LABEL_67;
            if ( *(_QWORD *)v80 != *(_QWORD *)v76 )
            {
              v82 = (unsigned int)ZSTD_NbCommonBytes(*(_QWORD *)v80 ^ *(_QWORD *)v76, v76, v80, v78) + v74;
              goto LABEL_85;
            }
            v76 += 8;
            v80 += 8;
            if ( (unsigned __int64)v76 >= v81 )
            {
LABEL_67:
              if ( v76 < v750 - 3 && *(_DWORD *)v80 == *(_DWORD *)v76 )
              {
                v76 += 4;
                v80 += 4;
              }
              if ( v76 < v750 - 1 && *(_WORD *)v80 == *(_WORD *)v76 )
              {
                v76 += 2;
                v80 += 2;
              }
              if ( v76 < v750 && *v80 == *v76 )
                ++v76;
              v82 = (unsigned __int64)&v76[-v72];
            }
            else
            {
              while ( *(_QWORD *)v80 == *(_QWORD *)v76 )
              {
                v76 += 8;
                v80 += 8;
                if ( (unsigned __int64)v76 >= v81 )
                  goto LABEL_67;
              }
              v83 = ZSTD_NbCommonBytes(*(_QWORD *)v80 ^ *(_QWORD *)v76, v76, v80, v78);
              v82 = v84 - v85 + v83 + v74;
            }
          }
LABEL_85:
          if ( v82 > v755 )
          {
            if ( v82 > v752 - v30 )
              v752 = v82 + v30;
            v93 = v773;
            v94 = v753 - v30 + 2;
            v773[2 * v810 + 1] = v82;
            v93[2 * v810] = v94;
            v755 = v82;
            ++v810;
            if ( v82 > 0x1000 || v82 + v72 == (_QWORD)v79 )
              break;
          }
          if ( (unsigned __int8)v77[v82] >= *(_BYTE *)(v82 + v72) )
          {
            v73 = v82;
            v759 = v82;
            *(_DWORD *)v761 = v30;
            if ( v30 <= v767 )
            {
              v96 = &v769;
              goto LABEL_184;
            }
            v30 = *v75;
            v761 = (unsigned __int64)v75;
          }
          else
          {
            v71 = v82;
            v758 = v82;
            *(_DWORD *)v757 = v30;
            if ( v30 <= v767 )
            {
              v95 = &v769;
              goto LABEL_186;
            }
            v30 = v75[1];
            v757 = (unsigned __int64)(v75 + 1);
          }
          if ( !v70 )
            break;
          v69 = v750;
        }
      }
LABEL_185:
      v95 = (unsigned int *)v757;
LABEL_186:
      *(_DWORD *)v761 = 0;
      *v95 = 0;
      *(_DWORD *)(a1 + 36) = v752 - 8;
LABEL_187:
      v164 = v810;
LABEL_376:
      if ( !v164 )
      {
        v14 = v766;
LABEL_869:
        v766 = ++v14;
        goto LABEL_870;
      }
      v310 = v779;
      v311 = a3;
      v312 = v763;
      v313 = v763;
      v314 = v784;
      v315 = v784;
      v779[4] = *a3;
      v310[5] = a3[1];
      v310[6] = a3[2];
      v310[2] = 0;
      v310[3] = v312;
      v316 = ZSTD_literalsContribution(v809, v313, v315, 0);
      v317 = v779;
      v318 = v773;
      *v779 = v316;
      if ( v318[2 * v164 - 1] > v787 )
      {
        *(_QWORD *)((char *)&v791 + 4) = *(_QWORD *)&v318[2 * v164 - 2];
        HIDWORD(v791) = v312;
        goto LABEL_379;
      }
      ZSTD_litLengthPrice(0, v314, 0);
      v339 = v785;
      v340 = v785 + 1;
      v341 = v779 + 7;
      do
      {
        *v341 = 0x40000000;
        v341 += 7;
        --v339;
      }
      while ( v339 );
      v342 = v164;
      v343 = v318;
      v757 = v164;
      v812 = v318;
      do
      {
        v344 = *v343;
        v345 = v343[1];
        updated = ZSTD_updateRep(v804, v311, *v343, v760);
        v348 = *(_QWORD *)updated;
        v349 = *(_DWORD *)(updated + 8);
        if ( v340 > v345 )
        {
          v360 = v779;
        }
        else
        {
          v350 = v784;
          do
          {
            _BitScanReverse((unsigned int *)&v351, v344 + 1);
            v11 = *(_DWORD *)(v350 + 80) == 1;
            v352 = v340 - 3;
            LODWORD(v783) = 0;
            if ( v11 )
            {
              LODWORD(v781) = 0;
              _BitScanReverse(&v353, v340 - 2);
              v354 = v347 + ((v353 + (_DWORD)v351 + 16) << 8);
            }
            else
            {
              v355 = *(_QWORD *)(v350 + 24);
              LODWORD(v780) = 0;
              _BitScanReverse((unsigned int *)&v355, *(_DWORD *)(v355 + 4 * v351) + 1);
              v356 = *(_DWORD *)(v350 + 76) + (((_DWORD)v351 - (_DWORD)v355) << 8);
              if ( (unsigned int)v351 >= 0x14 )
                v356 = ((_DWORD)v351 << 9) + v356 - 9728;
              if ( (unsigned int)v352 <= 0x7F )
              {
                _mm_lfence();
                v358 = *((unsigned __int8 *)&qword_1803EF770[8] + v352);
              }
              else
              {
                _BitScanReverse(&v357, v352);
                LODWORD(v771) = 0;
                v358 = v357 + 36;
              }
              v359 = 4 * v358;
              LODWORD(v768) = 0;
              _BitScanReverse((unsigned int *)&v358, *(_DWORD *)(*(_QWORD *)(v350 + 16) + 4 * v358) + 1);
              v354 = v347
                   + *(_DWORD *)(v350 + 72)
                   + ((*(_DWORD *)((char *)&qword_1803EF640[10] + v359) - (_DWORD)v358) << 8)
                   + v356
                   + 51;
            }
            v360 = v779;
            v361 = 7LL * v340;
            v362 = v763;
            v779[v361 + 2] = v340++;
            *(_QWORD *)&v360[v361 + 4] = v348;
            v360[v361 + 1] = v344;
            v360[v361 + 3] = v362;
            v360[v361] = v354;
            v360[v361 + 6] = v349;
          }
          while ( v340 <= v345 );
          v343 = v812;
          v342 = v757;
        }
        v311 = a3;
        v343 += 2;
        --v342;
        v812 = v343;
        v757 = v342;
      }
      while ( v342 );
      v363 = v784;
      v364 = v340 - 1;
      v365 = 1;
      v772 = v364;
      v753 = 1;
      if ( !v364 )
      {
LABEL_837:
        v725 = &v360[7 * v364];
        v727 = *(_OWORD *)v725;
        v788 = v725[6];
        v15 = *((_QWORD *)v725 + 2);
        v791 = v727;
        v797 = v788;
        v795 = v727;
        v796 = v15;
        *(double *)&v727 = ZSTD_totalLen(&v795);
        if ( v364 <= v728 )
        {
LABEL_379:
          v319 = 0;
          v320 = 0;
        }
        else
        {
          v800 = *(_DWORD *)(v726 + 24);
          v798 = v727;
          v799 = v15;
          ZSTD_totalLen(&v798);
          v320 = v364 - v729;
          v319 = 0;
        }
        goto LABEL_380;
      }
      while ( 2 )
      {
        v366 = v365;
        v367 = (unsigned int *)(v365 + v766);
        v368 = &v360[7 * v365 - 7];
        v754 = v367;
        if ( v368[2] )
          v369 = 1;
        else
          v369 = v368[3] + 1;
        v370 = *v368 - ZSTD_litLengthPrice(v369 - 1, v363, 0);
        v371 = ZSTD_rawLiteralsCost((char *)v367 - 1, 1, v363) + v370;
        v372 = ZSTD_litLengthPrice(v369, v363, 0);
        v360 = v779;
        v374 = v371 + v372;
        v375 = &v779[7 * v366];
        v376 = *v375;
        if ( v374 <= *v375 )
        {
          v377 = *((_QWORD *)v368 + 2);
          v376 = v374;
          *v375 = v374;
          v378 = v368[6];
          *((_QWORD *)v375 + 2) = v377;
          v375[6] = v378;
          *(_QWORD *)(v375 + 1) = v373;
          v375[3] = v369;
        }
        if ( (unsigned __int64)v367 > v790 )
          goto LABEL_836;
        if ( v753 == v364 )
          goto LABEL_837;
        if ( v360[7 * v753 + 7] <= v376 + 128 )
          goto LABEL_836;
        v379 = v375[2];
        v380 = v373;
        LOBYTE(v380) = v379 != 0;
        v760 = v380;
        if ( v379 )
          v767 = v373;
        else
          v767 = v375[3];
        v774 = v376 + ZSTD_litLengthPrice(0, v363, 0);
        v757 = (unsigned __int64)(v375 + 4);
        v381 = *(unsigned int *)(a1 + 36);
        v382 = *(_QWORD *)(a1 + 8);
        v383 = *(_DWORD *)(a1 + 200);
        if ( (unsigned __int64)v367 < v382 + v381 )
        {
          v360 = v779;
          goto LABEL_836;
        }
        v384 = (_DWORD)v367 - v382;
        if ( (unsigned int)v381 < (int)v367 - (int)v382 )
        {
          do
            LODWORD(v381) = ZSTD_insertBt1(a1, (int)v382 + (int)v381, (_DWORD)v750, v383, 1) + v381;
          while ( (unsigned int)v381 < v384 );
          v364 = v772;
          v367 = v754;
        }
        v385 = 4095;
        v386 = *(_QWORD *)(a1 + 8);
        v387 = *(_QWORD *)(a1 + 48);
        *(_DWORD *)(a1 + 36) = v384;
        v388 = *(unsigned int *)(a1 + 192);
        if ( v383 == 3 )
        {
          v613 = *(_DWORD *)(a1 + 204);
          v781 = (_DWORD *)v386;
          if ( v613 < 0xFFF )
            v385 = v613;
          v614 = (_DWORD)v367 - v386;
          v756 = (_DWORD)v367 - v386;
          v762 = v385;
          v615 = ZSTD_hash4Ptr(v367, v388, v387);
          v617 = *(_DWORD *)(v616 + 4 * v615);
          v618 = *(unsigned int *)(a1 + 24);
          v619 = *(_QWORD *)(a1 + 64);
          v620 = *(_DWORD *)(a1 + 188) - 1;
          v778 = (unsigned int *)(v616 + 4 * v615);
          v768 = 0;
          v621 = (1 << v620) - 1;
          v783 = 0;
          v758 = *(_QWORD *)(a1 + 16);
          v780 = (_DWORD *)(v618 + v622);
          v623 = 0;
          v789 = v619;
          v777 = v621;
          v775 = v618;
          v624 = 0;
          v761 = v618;
          if ( v621 < v614 )
            v624 = v614 - v621;
          v813 = 0;
          v764 = v624;
          v625 = 1 << *(_DWORD *)(a1 + 184);
          v626 = v614 - v625;
          v627 = 1;
          if ( v614 - *(_DWORD *)(a1 + 28) <= v625 )
            v626 = *(_DWORD *)(a1 + 28);
          if ( *(_DWORD *)(a1 + 32) )
            v626 = *(_DWORD *)(a1 + 28);
          v628 = *(_DWORD *)(a1 + 196);
          if ( v626 )
            v627 = v626;
          v751 = v627;
          v755 = v619 + 8LL * (v614 & v621);
          v771 = (_DWORD *)(v755 + 4);
          v763 = v614 + 9;
          v629 = 1 << v628;
          v630 = (_DWORD *)v757;
          v631 = v614 - v618;
          v752 = v629;
          v759 = v785;
          v632 = v760;
          v776 = v614 - v618;
          v633 = v760 + 3;
          v769 = v760 + 3;
          v634 = (unsigned int *)(v757 + 4LL * v760);
          while ( 1 )
          {
            if ( v632 == 3 )
              v635 = *v630 - 1;
            else
              v635 = *v634;
            v636 = v614 - v635;
            if ( v635 - 1 >= v631 )
            {
              if ( v635 - 1 < v614 - v626 && (unsigned int)v618 - v636 - 1 >= 3 )
              {
                v650 = (unsigned int)(*(_DWORD *)(v758 + v636) << 8);
                LODWORD(v765) = 1;
                v651 = ZSTD_readMINMATCH(v754, 3, v650, 0);
                if ( v651 == v655 )
                {
                  v656 = (unsigned __int64)v750;
                  v657 = v653 + 3;
                  v658 = v652 + v654;
                  v659 = v653 + 3 - v658 + v758 + v761;
                  if ( v659 < (unsigned __int64)v750 )
                    v656 = v659;
                  v660 = ZSTD_count(v657, v658, v656);
                  if ( v660 + v661 == v758 + v761 )
                    LODWORD(v660) = ZSTD_count(v660 + v657, v780, v750) + v660;
                  LODWORD(v618) = v775;
                  v623 = v660 + 3;
                  v614 = v756;
                  v633 = v769;
                }
              }
              v640 = v762;
            }
            else
            {
              LODWORD(v770) = 1;
              v637 = ZSTD_readMINMATCH(v754, 3, *(unsigned int *)((char *)v754 - v635) << 8, 0);
              if ( v637 != v641 )
                goto LABEL_736;
              v642 = (char *)(v638 + 3);
              v643 = v638 + 3;
              v644 = (_DWORD *)(v639 + v638 + 3);
              v645 = (unsigned __int64)(v750 - 7);
              if ( v638 + 3 >= (unsigned __int64)(v750 - 7) )
              {
LABEL_726:
                if ( v642 < v750 - 3 && *v644 == *(_DWORD *)v642 )
                {
                  v642 += 4;
                  ++v644;
                }
                if ( v642 < v750 - 1 && *(_WORD *)v644 == *(_WORD *)v642 )
                {
                  v642 += 2;
                  v644 = (_DWORD *)((char *)v644 + 2);
                }
                if ( v642 < v750 && *(_BYTE *)v644 == *v642 )
                  LODWORD(v642) = (_DWORD)v642 + 1;
                v623 = (_DWORD)v642 - v638;
LABEL_736:
                v633 = v769;
                goto LABEL_746;
              }
              if ( *(_QWORD *)v644 != *(_QWORD *)v642 )
              {
                v646 = ZSTD_NbCommonBytes(*(_QWORD *)v644 ^ *(_QWORD *)v642, v642, v644, v643);
                v633 = v769;
                v623 = v646 + 3;
              }
              else
              {
                v642 = (char *)(v638 + 11);
                v644 += 2;
                if ( v638 + 11 >= v645 )
                  goto LABEL_726;
                while ( *(_QWORD *)v644 == *(_QWORD *)v642 )
                {
                  v642 += 8;
                  v644 += 2;
                  if ( (unsigned __int64)v642 >= v645 )
                    goto LABEL_726;
                }
                v647 = ZSTD_NbCommonBytes(*(_QWORD *)v644 ^ *(_QWORD *)v642, v642, v644, v643);
                v633 = v769;
                v623 = v648 - v649 + v647 + 3;
              }
            }
LABEL_746:
            v662 = v759;
            if ( v623 > v759 )
            {
              v663 = v813;
              v662 = v623;
              ++v813;
              v664 = &v773[2 * v663];
              v664[1] = v623;
              *v664 = v632 - v760;
              v759 = v623;
              if ( v623 > v640 || (char *)v754 + v623 == v750 )
                goto LABEL_806;
            }
            ++v632;
            ++v634;
            if ( v632 >= v633 )
            {
              if ( v662 >= 3 )
              {
                v671 = v750;
                goto LABEL_759;
              }
              v665 = v754;
              FirstIndexHash3 = ZSTD_insertAndFindFirstIndexHash3(a1, &v786, v754);
              v667 = v751;
              v668 = v614 - FirstIndexHash3;
              if ( FirstIndexHash3 >= v751 && v668 < 0x40000 )
              {
                if ( FirstIndexHash3 < (unsigned int)v618 )
                {
                  v669 = ZSTD_count_2segments(
                           (_DWORD)v665,
                           FirstIndexHash3 + (unsigned int)v758,
                           (_DWORD)v750,
                           (int)v758 + (int)v618,
                           (__int64)v780);
                  v670 = 0;
                }
                else
                {
                  v669 = ZSTD_count(v665, (char *)v781 + FirstIndexHash3, v750);
                }
                v671 = v750;
                if ( v669 >= 3 )
                {
                  v672 = v773;
                  v673 = v670;
                  v759 = v669;
                  v813 = 1;
                  *v773 = v668 + 2;
                  v672[1] = v669;
                  LODWORD(v672) = v670;
                  LOBYTE(v673) = (char *)v665 + v669 == v750;
                  LOBYTE(v672) = v669 > v762;
                  if ( (unsigned int)v672 | v673 )
                  {
                    v813 = 1;
                    *(_DWORD *)(a1 + 36) = v756 + 1;
                    goto LABEL_806;
                  }
                }
LABEL_759:
                v667 = v751;
              }
              else
              {
                v671 = v750;
              }
              v674 = v752;
              v675 = v756;
              *v778 = v756;
              if ( !v674 )
              {
LABEL_804:
                v696 = (_DWORD *)v755;
LABEL_805:
                *v771 = 0;
                *v696 = 0;
                *(_DWORD *)(a1 + 36) = v763 - 8;
                goto LABEL_806;
              }
              v676 = v768;
              while ( 2 )
              {
                v752 = --v674;
                if ( v617 < v667 )
                  goto LABEL_804;
                v677 = (_DWORD *)v783;
                if ( (unsigned __int64)v676 < v783 )
                  v677 = v676;
                v678 = (_DWORD *)(v789 + 8LL * (v617 & v777));
                v765 = v678;
                if ( (unsigned __int64)v677 + v617 < v761 )
                {
                  v689 = (char *)v754 + (_QWORD)v677;
                  v679 = (char *)(v617 + v758);
                  v690 = v671;
                  if ( (char *)v754 + v761 - v617 < v671 )
                    v690 = (char *)v754 + v761 - v617;
                  v691 = ZSTD_count((char *)v754 + (_QWORD)v677, (char *)v677 + v617 + v758, v690);
                  v693 = v691 + v692;
                  v694 = v761;
                  if ( v693 == v761 + v758 )
                    v691 += ZSTD_count(&v689[v691], v780, v750);
                  v678 = v765;
                  v685 = (unsigned __int64)v677 + v691;
                  v674 = v752;
                  v676 = v768;
                  v92 = v617 + v685 < v694;
                  v675 = v756;
                  if ( !v92 )
                    v679 = (char *)v781 + v617;
                  v680 = v750;
                  goto LABEL_791;
                }
                v679 = (char *)v781 + v617;
                v680 = v750;
                v681 = (char *)v754 + (_QWORD)v677;
                v682 = (char *)v754 + (_QWORD)v677;
                v683 = (_QWORD *)((char *)v677 + (_QWORD)v679);
                v684 = (unsigned __int64)(v750 - 7);
                if ( (char *)v754 + (unsigned __int64)v677 < v750 - 7 )
                {
                  if ( *v683 != *(_QWORD *)v681 )
                  {
                    v685 = (unsigned __int64)v677
                         + (unsigned int)ZSTD_NbCommonBytes(*v683 ^ *(_QWORD *)v681, v681, v683, v682);
LABEL_791:
                    if ( v685 > v759 )
                    {
                      if ( v685 > v763 - v617 )
                        v763 = v685 + v617;
                      v695 = v773;
                      v773[2 * v813 + 1] = v685;
                      v695[2 * v813] = v675 - v617 + 2;
                      v759 = v685;
                      ++v813;
                      if ( v685 > 0x1000 || (char *)v754 + v685 == v680 )
                        goto LABEL_804;
                    }
                    if ( (unsigned __int8)v679[v685] >= *((_BYTE *)v754 + v685) )
                    {
                      v783 = v685;
                      *v771 = v617;
                      if ( v617 <= v764 )
                      {
                        v771 = &v752;
                        goto LABEL_804;
                      }
                      v617 = *v678;
                      v771 = v678;
                    }
                    else
                    {
                      v676 = (_DWORD *)v685;
                      v768 = (_DWORD *)v685;
                      *(_DWORD *)v755 = v617;
                      if ( v617 <= v764 )
                      {
                        v696 = &v752;
                        goto LABEL_805;
                      }
                      v617 = v678[1];
                      v755 = (unsigned __int64)(v678 + 1);
                    }
                    if ( !v674 )
                      goto LABEL_804;
                    v671 = v750;
                    v667 = v751;
                    continue;
                  }
                  v681 += 8;
                  ++v683;
                  if ( (unsigned __int64)v681 < v684 )
                  {
                    while ( *v683 == *(_QWORD *)v681 )
                    {
                      v681 += 8;
                      ++v683;
                      if ( (unsigned __int64)v681 >= v684 )
                        goto LABEL_773;
                    }
                    v686 = ZSTD_NbCommonBytes(*v683 ^ *(_QWORD *)v681, v681, v683, v682);
                    v685 = (unsigned __int64)v677 + v687 - v688 + v686;
                    goto LABEL_791;
                  }
                }
                break;
              }
LABEL_773:
              if ( v681 < v750 - 3 && *(_DWORD *)v683 == *(_DWORD *)v681 )
              {
                v681 += 4;
                v683 = (_QWORD *)((char *)v683 + 4);
              }
              if ( v681 < v750 - 1 && *(_WORD *)v683 == *(_WORD *)v681 )
              {
                v681 += 2;
                v683 = (_QWORD *)((char *)v683 + 2);
              }
              if ( v681 < v750 && *(_BYTE *)v683 == *v681 )
                ++v681;
              v685 = v681 - (char *)v754;
              goto LABEL_791;
            }
            v631 = v776;
            v623 = 0;
            v630 = (_DWORD *)v757;
          }
        }
        if ( v383 == 5 )
        {
          v539 = *(_DWORD *)(a1 + 204);
          v780 = (_DWORD *)v386;
          if ( v539 < 0xFFF )
            v385 = v539;
          v540 = (_DWORD)v367 - v386;
          v763 = (_DWORD)v367 - v386;
          v752 = v385;
          v541 = ZSTD_hash5Ptr(v367, v388, v387);
          v543 = *(_DWORD *)(v542 + 4 * v541);
          v544 = *(unsigned int *)(a1 + 24);
          v545 = *(_QWORD *)(a1 + 64);
          v546 = *(_DWORD *)(a1 + 188) - 1;
          v778 = (unsigned int *)(v542 + 4 * v541);
          v758 = *(_QWORD *)(a1 + 16);
          v771 = (_DWORD *)(v544 + v547);
          LODWORD(v542) = 1 << v546;
          v548 = 0;
          v549 = v542 - 1;
          v765 = 0;
          v770 = 0;
          v756 = v549;
          v783 = v545;
          if ( v549 < v540 )
            v548 = v540 - v549;
          v776 = v544;
          v769 = v548;
          v550 = 1 << *(_DWORD *)(a1 + 184);
          v551 = *(_DWORD *)(a1 + 28);
          v552 = v540 - v550;
          v759 = v544;
          v553 = 1;
          if ( v540 - v551 <= v550 )
            v552 = v551;
          if ( *(_DWORD *)(a1 + 32) )
            v552 = v551;
          v554 = *(_DWORD *)(a1 + 196);
          if ( v552 )
            v553 = v552;
          v764 = v553;
          v555 = v540 & v549;
          v556 = 0;
          v813 = 0;
          v755 = v545 + 4LL * (unsigned int)(2 * v555);
          v768 = (_DWORD *)(v755 + 4);
          v762 = v540 + 9;
          v557 = 1 << v554;
          v558 = (_DWORD *)v757;
          v559 = v540 - v544;
          v751 = v557;
          v761 = v785;
          v560 = v760;
          v777 = v540 - v544;
          v561 = v760 + 3;
          v775 = v760 + 3;
          v562 = (unsigned int *)(v757 + 4LL * v760);
          while ( 1 )
          {
            if ( v560 == 3 )
              v563 = *v558 - 1;
            else
              v563 = *v562;
            v564 = v540 - v563;
            if ( v563 - 1 >= v559 )
            {
              if ( v563 - 1 < v540 - v552 && (unsigned int)(v544 - v564 - 1) >= 3 )
              {
                v578 = ZSTD_readMINMATCH(v754, 4, 0, v564);
                if ( v578 == *v581 )
                {
                  v582 = (unsigned __int64)v750;
                  v583 = v580 + 4;
                  v584 = (char *)v581 + v579;
                  v585 = v580 + 4 - (_QWORD)v584 + v758 + v759;
                  if ( v585 < (unsigned __int64)v750 )
                    v582 = v585;
                  v544 = ZSTD_count(v583, v584, v582);
                  if ( v544 + v586 == v758 + v759 )
                    LODWORD(v544) = ZSTD_count(v544 + v583, v771, v750) + v544;
                  v561 = v775;
                  v556 = v544 + 4;
                  LODWORD(v544) = v776;
                  v540 = v763;
                }
              }
              v568 = v752;
            }
            else
            {
              v565 = ZSTD_readMINMATCH(v754, 4, 0, -(__int64)v563);
              if ( v565 != *(_DWORD *)(v567 + v566) )
                goto LABEL_653;
              v569 = (char *)(v566 + 4);
              v570 = v566 + 4;
              v571 = (unsigned __int64)v750;
              v572 = (_QWORD *)(v567 + v570);
              v573 = v569;
              v574 = (unsigned __int64)(v750 - 7);
              if ( v569 >= v750 - 7 )
                goto LABEL_634;
              if ( *v572 != *(_QWORD *)v569 )
              {
                v556 = ZSTD_NbCommonBytes(*v572 ^ *(_QWORD *)v569, v569, v572, v569) + 4;
                goto LABEL_653;
              }
              v569 += 8;
              ++v572;
              if ( (unsigned __int64)v569 >= v574 )
              {
LABEL_633:
                v571 = (unsigned __int64)v750;
LABEL_634:
                if ( (unsigned __int64)v569 < v571 - 3 && *(_DWORD *)v572 == *(_DWORD *)v569 )
                {
                  v569 += 4;
                  v572 = (_QWORD *)((char *)v572 + 4);
                }
                if ( (unsigned __int64)v569 < v571 - 1 && *(_WORD *)v572 == *(_WORD *)v569 )
                {
                  v569 += 2;
                  v572 = (_QWORD *)((char *)v572 + 2);
                }
                if ( (unsigned __int64)v569 < v571 && *(_BYTE *)v572 == *v569 )
                  LODWORD(v569) = (_DWORD)v569 + 1;
                v556 = (_DWORD)v569 - (_DWORD)v573 + 4;
                goto LABEL_653;
              }
              while ( *v572 == *(_QWORD *)v569 )
              {
                v569 += 8;
                ++v572;
                if ( (unsigned __int64)v569 >= v574 )
                  goto LABEL_633;
              }
              v575 = ZSTD_NbCommonBytes(*v572 ^ *(_QWORD *)v569, v569, v572, v573);
              v556 = v576 - v577 + v575 + 4;
            }
LABEL_653:
            if ( v556 <= v761 )
            {
              v589 = v750;
            }
            else
            {
              v587 = &v773[2 * v813];
              *v587 = v560 - v760;
              v588 = (char *)v754 + v556;
              v587[1] = v556;
              v761 = v556;
              ++v813;
              v589 = v750;
              if ( v556 > v568 || v588 == v750 )
                goto LABEL_806;
            }
            v559 = v777;
            ++v560;
            v558 = (_DWORD *)v757;
            ++v562;
            if ( v560 >= v561 )
            {
              v590 = v751;
              *v778 = v540;
              if ( !v590 )
                goto LABEL_702;
              v591 = (unsigned __int64)v765;
              v592 = (unsigned __int64)v765;
              while ( 2 )
              {
                v751 = --v590;
                if ( v543 < v764 )
                  goto LABEL_702;
                v593 = v592;
                if ( v591 < v592 )
                  v593 = v591;
                v594 = (_DWORD *)(v783 + 8LL * (v543 & v756));
                v781 = v594;
                if ( v543 + v593 < v759 )
                {
                  v605 = (char *)v754 + v593;
                  v595 = (char *)(v543 + v758);
                  v606 = v589;
                  if ( (char *)v754 + v759 - v543 < v589 )
                    v606 = (char *)v754 + v759 - v543;
                  v607 = ZSTD_count((char *)v754 + v593, v543 + v758 + v593, v606);
                  v609 = v607 + v608;
                  v610 = v759;
                  if ( v609 == v759 + v758 )
                    v607 += ZSTD_count(&v605[v607], v771, v750);
                  v594 = v781;
                  v601 = v607 + v593;
                  v591 = (unsigned __int64)v765;
                  v592 = (unsigned __int64)v770;
                  v92 = v543 + v601 < v610;
                  v590 = v751;
                  if ( !v92 )
                    v595 = (char *)v780 + v543;
                  v596 = v750;
                  goto LABEL_688;
                }
                v595 = (char *)v780 + v543;
                v596 = v750;
                v597 = (char *)v754 + v593;
                v598 = (char *)v754 + v593;
                v599 = &v595[v593];
                v600 = (unsigned __int64)(v750 - 7);
                if ( (char *)v754 + v593 < v750 - 7 )
                {
                  if ( *(_QWORD *)v599 != *(_QWORD *)v597 )
                  {
                    v601 = (unsigned int)ZSTD_NbCommonBytes(*(_QWORD *)v599 ^ *(_QWORD *)v597, v597, v599, v598) + v593;
LABEL_688:
                    if ( v601 > v761 )
                    {
                      if ( v601 > v762 - v543 )
                        v762 = v601 + v543;
                      v611 = v773;
                      v612 = v763 - v543 + 2;
                      v773[2 * v813 + 1] = v601;
                      v611[2 * v813] = v612;
                      v761 = v601;
                      ++v813;
                      if ( v601 > 0x1000 || (char *)v754 + v601 == v596 )
                        goto LABEL_702;
                    }
                    if ( (unsigned __int8)v595[v601] >= *((_BYTE *)v754 + v601) )
                    {
                      v592 = v601;
                      v770 = (unsigned int *)v601;
                      *v768 = v543;
                      if ( v543 <= v769 )
                      {
                        v464 = &v777;
LABEL_701:
                        v768 = v464;
                        goto LABEL_702;
                      }
                      v543 = *v594;
                      v768 = v594;
                    }
                    else
                    {
                      v591 = v601;
                      v765 = (_DWORD *)v601;
                      *(_DWORD *)v755 = v543;
                      if ( v543 <= v769 )
                      {
                        v463 = &v777;
                        goto LABEL_703;
                      }
                      v543 = v594[1];
                      v755 = (unsigned __int64)(v594 + 1);
                    }
                    if ( !v590 )
                      goto LABEL_702;
                    v589 = v750;
                    continue;
                  }
                  v597 += 8;
                  v599 += 8;
                  if ( (unsigned __int64)v597 < v600 )
                  {
                    while ( *(_QWORD *)v599 == *(_QWORD *)v597 )
                    {
                      v597 += 8;
                      v599 += 8;
                      if ( (unsigned __int64)v597 >= v600 )
                        goto LABEL_670;
                    }
                    v602 = ZSTD_NbCommonBytes(*(_QWORD *)v599 ^ *(_QWORD *)v597, v597, v599, v598);
                    v601 = v603 - v604 + v602 + v593;
                    goto LABEL_688;
                  }
                }
                break;
              }
LABEL_670:
              if ( v597 < v750 - 3 && *(_DWORD *)v599 == *(_DWORD *)v597 )
              {
                v597 += 4;
                v599 += 4;
              }
              if ( v597 < v750 - 1 && *(_WORD *)v599 == *(_WORD *)v597 )
              {
                v597 += 2;
                v599 += 2;
              }
              if ( v597 < v750 && *v599 == *v597 )
                ++v597;
              v601 = v597 - (char *)v754;
              goto LABEL_688;
            }
            v556 = 0;
          }
        }
        v389 = *(_DWORD *)(a1 + 204);
        if ( (unsigned int)(v383 - 6) > 1 )
        {
          v771 = (_DWORD *)v386;
          if ( v389 < 0xFFF )
            v385 = v389;
          v465 = (_DWORD)v367 - v386;
          v756 = (_DWORD)v367 - v386;
          v752 = v385;
          v466 = ZSTD_hash4Ptr(v367, v388, v387);
          v468 = *(_DWORD *)(v467 + 4 * v466);
          v469 = *(unsigned int *)(a1 + 24);
          v470 = *(_QWORD *)(a1 + 64);
          v471 = *(_DWORD *)(a1 + 188) - 1;
          v778 = (unsigned int *)(v467 + 4 * v466);
          v758 = *(_QWORD *)(a1 + 16);
          v768 = (_DWORD *)(v469 + v472);
          LODWORD(v467) = 1 << v471;
          v473 = 0;
          v474 = v467 - 1;
          v765 = 0;
          v781 = 0;
          v769 = v474;
          v783 = v470;
          if ( v474 < v465 )
            v473 = v465 - v474;
          v776 = v469;
          v763 = v473;
          v475 = 1 << *(_DWORD *)(a1 + 184);
          v476 = *(_DWORD *)(a1 + 28);
          v477 = v465 - v475;
          v759 = v469;
          v478 = 1;
          if ( v465 - v476 <= v475 )
            v477 = v476;
          if ( *(_DWORD *)(a1 + 32) )
            v477 = v476;
          v479 = *(_DWORD *)(a1 + 196);
          v775 = v477;
          if ( v477 )
            v478 = v477;
          v764 = v478;
          v480 = v465 & v474;
          v481 = 0;
          v813 = 0;
          v755 = v470 + 4LL * (unsigned int)(2 * v480);
          v770 = (unsigned int *)(v755 + 4);
          v762 = v465 + 9;
          v482 = 1 << v479;
          v483 = (_DWORD *)v757;
          v484 = v465 - v469;
          v751 = v482;
          v761 = v785;
          v485 = v760;
          v777 = v465 - v469;
          v486 = v760 + 3;
          v487 = (unsigned int *)(v757 + 4LL * v760);
          while ( 1 )
          {
            if ( v485 == 3 )
              v488 = *v483 - 1;
            else
              v488 = *v487;
            v489 = v465 - v488;
            if ( v488 - 1 >= v484 )
            {
              if ( v488 - 1 < v465 - v477
                && (unsigned int)(v469 - v489 - 1) >= 3
                && (v502 = ZSTD_readMINMATCH(v754, 4, 0, v489), v502 == *v505) )
              {
                v506 = (__int64)v750;
                v507 = v504 + 4;
                v508 = (char *)v505 + v503;
                v509 = v504 + 4 + v758 + v759 - (_QWORD)v508;
                v510 = v504 + 4;
                if ( v510 + v758 + v759 - (unsigned __int64)v508 < (unsigned __int64)v750 )
                  v506 = v509;
                v469 = ZSTD_count(v510, v508, v506);
                if ( v469 + v511 == v758 + v759 )
                {
                  v512 = v469 + v507;
                  v494 = v750;
                  v513 = ZSTD_count(v512, v768, v750);
                  v477 = v775;
                  v481 = v513 + v469 + 4;
                  LODWORD(v469) = v776;
                }
                else
                {
                  v494 = v750;
                  v481 = v469 + 4;
                  LODWORD(v469) = v776;
                  v477 = v775;
                }
              }
              else
              {
                v494 = v750;
              }
              v493 = v752;
            }
            else
            {
              v490 = ZSTD_readMINMATCH(v754, 4, 0, -(__int64)v488);
              v494 = v750;
              if ( v490 != *(_DWORD *)(v492 + v491) )
                goto LABEL_558;
              v495 = (char *)(v491 + 4);
              v496 = (_QWORD *)(v492 + v491 + 4);
              v497 = (unsigned __int64)(v750 - 7);
              v498 = v491 + 4;
              if ( v491 + 4 >= (unsigned __int64)(v750 - 7) )
                goto LABEL_538;
              if ( *v496 != *(_QWORD *)v495 )
              {
                v481 = ZSTD_NbCommonBytes(*v496 ^ *(_QWORD *)v495, v495, v496, v498) + 4;
                goto LABEL_558;
              }
              v495 = (char *)(v491 + 12);
              ++v496;
              if ( v491 + 12 >= v497 )
              {
LABEL_538:
                if ( v495 < v750 - 3 && *(_DWORD *)v496 == *(_DWORD *)v495 )
                {
                  v495 += 4;
                  v496 = (_QWORD *)((char *)v496 + 4);
                }
                if ( v495 < v750 - 1 && *(_WORD *)v496 == *(_WORD *)v495 )
                {
                  v495 += 2;
                  v496 = (_QWORD *)((char *)v496 + 2);
                }
                if ( v495 < v750 && *(_BYTE *)v496 == *v495 )
                  LODWORD(v495) = (_DWORD)v495 + 1;
                v481 = (_DWORD)v495 - v491;
              }
              else
              {
                while ( *v496 == *(_QWORD *)v495 )
                {
                  v495 += 8;
                  ++v496;
                  if ( (unsigned __int64)v495 >= v497 )
                    goto LABEL_538;
                }
                v499 = ZSTD_NbCommonBytes(*v496 ^ *(_QWORD *)v495, v495, v496, v498);
                v481 = v500 - v501 + v499 + 4;
              }
            }
LABEL_558:
            if ( v481 <= v761 )
            {
              v515 = v754;
            }
            else
            {
              v514 = &v773[2 * v813];
              *v514 = v485 - v760;
              v514[1] = v481;
              ++v813;
              v515 = v754;
              v761 = v481;
              if ( v481 > v493 || (char *)v754 + v481 == v494 )
                goto LABEL_806;
            }
            v484 = v777;
            ++v485;
            v465 = v756;
            ++v487;
            v483 = (_DWORD *)v757;
            if ( v485 >= v486 )
            {
              v516 = v756;
              v517 = v751;
              *v778 = v756;
              if ( !v517 )
              {
LABEL_608:
                v538 = (unsigned int *)v755;
LABEL_609:
                *v770 = 0;
                *v538 = 0;
                *(_DWORD *)(a1 + 36) = v762 - 8;
                goto LABEL_806;
              }
              v518 = (unsigned __int64)v765;
              while ( 2 )
              {
                v751 = --v517;
                if ( v468 < v764 )
                  goto LABEL_608;
                v519 = (unsigned __int64)v781;
                if ( v518 < (unsigned __int64)v781 )
                  v519 = v518;
                v520 = (_DWORD *)(v783 + 8LL * (v468 & v769));
                v780 = v520;
                if ( v519 + v468 < v759 )
                {
                  v531 = (char *)v515 + v519;
                  v532 = v750;
                  v522 = (char *)(v758 + v468);
                  if ( (char *)v515 + v759 - v468 < v750 )
                    v532 = (char *)v515 + v759 - v468;
                  v533 = ZSTD_count((char *)v515 + v519, v758 + v468 + v519, v532);
                  v535 = v533 + v534;
                  v536 = v759;
                  if ( v535 == v759 + v758 )
                    v533 += ZSTD_count(&v531[v533], v768, v750);
                  v520 = v780;
                  v527 = v533 + v519;
                  v516 = v756;
                  v518 = (unsigned __int64)v765;
                  v92 = v527 + v468 < v536;
                  v517 = v751;
                  if ( !v92 )
                    v522 = (char *)v771 + v468;
                  v524 = v750;
                  goto LABEL_593;
                }
                v521 = (char *)v515 + v519;
                v522 = (char *)v771 + v468;
                v523 = v521;
                v524 = v750;
                v525 = &v522[v519];
                v526 = (unsigned __int64)(v750 - 7);
                if ( v521 < v750 - 7 )
                {
                  if ( *(_QWORD *)v525 != *(_QWORD *)v521 )
                  {
                    v527 = (unsigned int)ZSTD_NbCommonBytes(*(_QWORD *)v525 ^ *(_QWORD *)v521, v521, v525, v521) + v519;
LABEL_593:
                    if ( v527 <= v761 )
                    {
                      v515 = v754;
                    }
                    else
                    {
                      if ( v527 > v762 - v468 )
                        v762 = v527 + v468;
                      v515 = v754;
                      v537 = &v773[2 * v813];
                      v537[1] = v527;
                      *v537 = v516 - v468 + 2;
                      v761 = v527;
                      ++v813;
                      if ( v527 > 0x1000 || (char *)v515 + v527 == v524 )
                        goto LABEL_608;
                    }
                    if ( (unsigned __int8)v522[v527] >= *((_BYTE *)v515 + v527) )
                    {
                      v781 = (_DWORD *)v527;
                      *v770 = v468;
                      if ( v468 <= v763 )
                      {
                        v770 = &v776;
                        goto LABEL_608;
                      }
                      v468 = *v520;
                      v770 = v520;
                    }
                    else
                    {
                      v518 = v527;
                      v765 = (_DWORD *)v527;
                      *(_DWORD *)v755 = v468;
                      if ( v468 <= v763 )
                      {
                        v538 = &v776;
                        goto LABEL_609;
                      }
                      v468 = v520[1];
                      v755 = (unsigned __int64)(v520 + 1);
                    }
                    if ( !v517 )
                      goto LABEL_608;
                    continue;
                  }
                  v521 += 8;
                  v525 += 8;
                  if ( (unsigned __int64)v521 < v526 )
                  {
                    while ( *(_QWORD *)v525 == *(_QWORD *)v521 )
                    {
                      v521 += 8;
                      v525 += 8;
                      if ( (unsigned __int64)v521 >= v526 )
                        goto LABEL_575;
                    }
                    v528 = ZSTD_NbCommonBytes(*(_QWORD *)v525 ^ *(_QWORD *)v521, v521, v525, v523);
                    v527 = v529 - v530 + v528 + v519;
                    goto LABEL_593;
                  }
                }
                break;
              }
LABEL_575:
              if ( v521 < v750 - 3 && *(_DWORD *)v525 == *(_DWORD *)v521 )
              {
                v521 += 4;
                v525 += 4;
              }
              if ( v521 < v750 - 1 && *(_WORD *)v525 == *(_WORD *)v521 )
              {
                v521 += 2;
                v525 += 2;
              }
              if ( v521 < v750 && *v525 == *v521 )
                ++v521;
              v527 = v521 - v523 + v519;
              goto LABEL_593;
            }
            v481 = 0;
          }
        }
        v780 = (_DWORD *)v386;
        if ( v389 < 0xFFF )
          v385 = v389;
        v390 = (_DWORD)v367 - v386;
        v763 = (_DWORD)v367 - v386;
        v752 = v385;
        v391 = ZSTD_hash6Ptr(v367, v388, v387);
        v393 = *(_DWORD *)(v392 + 4 * v391);
        v394 = *(unsigned int *)(a1 + 24);
        v395 = *(_QWORD *)(a1 + 64);
        v396 = *(_DWORD *)(a1 + 188) - 1;
        v778 = (unsigned int *)(v392 + 4 * v391);
        v758 = *(_QWORD *)(a1 + 16);
        v771 = (_DWORD *)(v394 + v397);
        LODWORD(v392) = 1 << v396;
        v398 = 0;
        v399 = v392 - 1;
        v765 = 0;
        v770 = 0;
        v775 = v399;
        v783 = v395;
        if ( v399 < v390 )
          v398 = v390 - v399;
        v756 = v394;
        v769 = v398;
        v400 = 1 << *(_DWORD *)(a1 + 184);
        v401 = *(_DWORD *)(a1 + 28);
        v402 = v390 - v400;
        v759 = v394;
        v403 = 1;
        if ( v390 - v401 <= v400 )
          v402 = v401;
        if ( *(_DWORD *)(a1 + 32) )
          v402 = v401;
        v404 = *(_DWORD *)(a1 + 196);
        if ( v402 )
          v403 = v402;
        v776 = v403;
        v405 = v390 & v399;
        v406 = 0;
        v813 = 0;
        v755 = v395 + 4LL * (unsigned int)(2 * v405);
        v768 = (_DWORD *)(v755 + 4);
        v762 = v390 + 9;
        v407 = 1 << v404;
        v408 = (_DWORD *)v757;
        v409 = v390 - v394;
        v751 = v407;
        v761 = v785;
        v410 = v760;
        v777 = v390 - v394;
        v411 = v760 + 3;
        v764 = v760 + 3;
        v412 = (unsigned int *)(v757 + 4LL * v760);
        while ( 2 )
        {
          if ( v410 == 3 )
            v413 = *v408 - 1;
          else
            v413 = *v412;
          v414 = v390 - v413;
          if ( v413 - 1 >= v409 )
          {
            if ( v413 - 1 < v390 - v402 && (unsigned int)(v394 - v414 - 1) >= 3 )
            {
              v428 = ZSTD_readMINMATCH(v754, 4, 0, v414);
              if ( v428 == *v431 )
              {
                v432 = (unsigned __int64)v750;
                v433 = v430 + 4;
                v434 = (char *)v431 + v429;
                v435 = v430 + 4 - (_QWORD)v434 + v758 + v759;
                if ( v435 < (unsigned __int64)v750 )
                  v432 = v435;
                v394 = ZSTD_count(v433, v434, v432);
                if ( v394 + v436 == v758 + v759 )
                  LODWORD(v394) = ZSTD_count(v394 + v433, v771, v750) + v394;
                v411 = v764;
                v406 = v394 + 4;
                LODWORD(v394) = v756;
                v390 = v763;
              }
            }
            v418 = v752;
            goto LABEL_467;
          }
          v415 = ZSTD_readMINMATCH(v754, 4, 0, -(__int64)v413);
          if ( v415 != *(_DWORD *)(v417 + v416) )
            goto LABEL_467;
          v419 = (char *)(v416 + 4);
          v420 = v416 + 4;
          v421 = (unsigned __int64)v750;
          v422 = (_QWORD *)(v417 + v420);
          v423 = v419;
          v424 = (unsigned __int64)(v750 - 7);
          if ( v419 >= v750 - 7 )
            goto LABEL_448;
          if ( *v422 != *(_QWORD *)v419 )
          {
            v406 = ZSTD_NbCommonBytes(*v422 ^ *(_QWORD *)v419, v419, v422, v419) + 4;
            goto LABEL_467;
          }
          v419 += 8;
          ++v422;
          if ( (unsigned __int64)v419 >= v424 )
          {
LABEL_447:
            v421 = (unsigned __int64)v750;
LABEL_448:
            if ( (unsigned __int64)v419 < v421 - 3 && *(_DWORD *)v422 == *(_DWORD *)v419 )
            {
              v419 += 4;
              v422 = (_QWORD *)((char *)v422 + 4);
            }
            if ( (unsigned __int64)v419 < v421 - 1 && *(_WORD *)v422 == *(_WORD *)v419 )
            {
              v419 += 2;
              v422 = (_QWORD *)((char *)v422 + 2);
            }
            if ( (unsigned __int64)v419 < v421 && *(_BYTE *)v422 == *v419 )
              LODWORD(v419) = (_DWORD)v419 + 1;
            v406 = (_DWORD)v419 - (_DWORD)v423 + 4;
            goto LABEL_467;
          }
          while ( *v422 == *(_QWORD *)v419 )
          {
            v419 += 8;
            ++v422;
            if ( (unsigned __int64)v419 >= v424 )
              goto LABEL_447;
          }
          v425 = ZSTD_NbCommonBytes(*v422 ^ *(_QWORD *)v419, v419, v422, v423);
          v406 = v426 - v427 + v425 + 4;
LABEL_467:
          if ( v406 <= v761 )
          {
            v439 = v750;
          }
          else
          {
            v437 = &v773[2 * v813];
            *v437 = v410 - v760;
            v438 = (char *)v754 + v406;
            v437[1] = v406;
            v761 = v406;
            ++v813;
            v439 = v750;
            if ( v406 > v418 || v438 == v750 )
              goto LABEL_806;
          }
          v409 = v777;
          ++v410;
          v408 = (_DWORD *)v757;
          ++v412;
          if ( v410 < v411 )
          {
            v406 = 0;
            continue;
          }
          break;
        }
        v440 = v751;
        *v778 = v390;
        if ( v440 )
        {
          v441 = (unsigned __int64)v765;
          v442 = (unsigned __int64)v765;
          while ( 1 )
          {
            v751 = --v440;
            if ( v393 < v776 )
              break;
            v443 = v442;
            if ( v441 < v442 )
              v443 = v441;
            v444 = (_DWORD *)(v783 + 8LL * (v393 & v775));
            v781 = v444;
            if ( v393 + v443 < v759 )
            {
              v455 = (char *)v754 + v443;
              v445 = (char *)(v393 + v758);
              v456 = v439;
              if ( (char *)v754 + v759 - v393 < v439 )
                v456 = (char *)v754 + v759 - v393;
              v457 = ZSTD_count((char *)v754 + v443, v393 + v758 + v443, v456);
              v459 = v457 + v458;
              v460 = v759;
              if ( v459 == v759 + v758 )
                v457 += ZSTD_count(&v455[v457], v771, v750);
              v444 = v781;
              v451 = v457 + v443;
              v441 = (unsigned __int64)v765;
              v442 = (unsigned __int64)v770;
              v92 = v393 + v451 < v460;
              v440 = v751;
              if ( !v92 )
                v445 = (char *)v780 + v393;
              v446 = v750;
            }
            else
            {
              v445 = (char *)v780 + v393;
              v446 = v750;
              v447 = (char *)v754 + v443;
              v448 = (char *)v754 + v443;
              v449 = &v445[v443];
              v450 = (unsigned __int64)(v750 - 7);
              if ( (char *)v754 + v443 >= v750 - 7 )
                goto LABEL_484;
              if ( *(_QWORD *)v449 != *(_QWORD *)v447 )
              {
                v451 = (unsigned int)ZSTD_NbCommonBytes(*(_QWORD *)v449 ^ *(_QWORD *)v447, v447, v449, v448) + v443;
                goto LABEL_502;
              }
              v447 += 8;
              v449 += 8;
              if ( (unsigned __int64)v447 >= v450 )
              {
LABEL_484:
                if ( v447 < v750 - 3 && *(_DWORD *)v449 == *(_DWORD *)v447 )
                {
                  v447 += 4;
                  v449 += 4;
                }
                if ( v447 < v750 - 1 && *(_WORD *)v449 == *(_WORD *)v447 )
                {
                  v447 += 2;
                  v449 += 2;
                }
                if ( v447 < v750 && *v449 == *v447 )
                  ++v447;
                v451 = v447 - (char *)v754;
              }
              else
              {
                while ( *(_QWORD *)v449 == *(_QWORD *)v447 )
                {
                  v447 += 8;
                  v449 += 8;
                  if ( (unsigned __int64)v447 >= v450 )
                    goto LABEL_484;
                }
                v452 = ZSTD_NbCommonBytes(*(_QWORD *)v449 ^ *(_QWORD *)v447, v447, v449, v448);
                v451 = v453 - v454 + v452 + v443;
              }
            }
LABEL_502:
            if ( v451 > v761 )
            {
              if ( v451 > v762 - v393 )
                v762 = v451 + v393;
              v461 = v773;
              v462 = v763 - v393 + 2;
              v773[2 * v813 + 1] = v451;
              v461[2 * v813] = v462;
              v761 = v451;
              ++v813;
              if ( v451 > 0x1000 || (char *)v754 + v451 == v446 )
                break;
            }
            if ( (unsigned __int8)v445[v451] >= *((_BYTE *)v754 + v451) )
            {
              v442 = v451;
              v770 = (unsigned int *)v451;
              *v768 = v393;
              if ( v393 <= v769 )
              {
                v464 = (unsigned int *)&v775;
                goto LABEL_701;
              }
              v393 = *v444;
              v768 = v444;
            }
            else
            {
              v441 = v451;
              v765 = (_DWORD *)v451;
              *(_DWORD *)v755 = v393;
              if ( v393 <= v769 )
              {
                v463 = (unsigned int *)&v775;
                goto LABEL_703;
              }
              v393 = v444[1];
              v755 = (unsigned __int64)(v444 + 1);
            }
            if ( !v440 )
              break;
            v439 = v750;
          }
        }
LABEL_702:
        v463 = (unsigned int *)v755;
LABEL_703:
        *v768 = 0;
        *v463 = 0;
        *(_DWORD *)(a1 + 36) = v762 - 8;
LABEL_806:
        if ( !v813 )
        {
          v360 = v779;
          goto LABEL_835;
        }
        v697 = v773;
        v698 = v753;
        v699 = v773[2 * v813 - 1];
        if ( v699 <= v787 && v699 + v753 < 0x1000 )
        {
          v700 = 0;
          v764 = 0;
          v701 = v773;
          v778 = v773;
          do
          {
            v702 = *v701;
            v703 = ZSTD_updateRep(v805, v757, *v701, v760);
            v705 = v704[1];
            v706 = *(_DWORD *)(v703 + 8);
            v707 = *(_QWORD *)v703;
            v763 = v706;
            if ( v700 )
              v708 = v697[2 * v700 - 1] + 1;
            else
              v708 = v782;
            if ( v705 < v708 )
            {
              v360 = v779;
            }
            else
            {
              v709 = v784;
              v710 = v705 + v698;
              v711 = -v698;
              do
              {
                v712 = v711 + v710;
                _BitScanReverse((unsigned int *)&v713, v702 + 1);
                v11 = *(_DWORD *)(v709 + 80) == 1;
                v714 = v711 + v710 - 3;
                LODWORD(v761) = 0;
                if ( v11 )
                {
                  LODWORD(v759) = 0;
                  _BitScanReverse(&v715, v714 + 1);
                  v716 = v774 + ((v715 + (_DWORD)v713 + 16) << 8);
                }
                else
                {
                  LODWORD(v758) = 0;
                  _BitScanReverse(&v717, *(_DWORD *)(*(_QWORD *)(v709 + 24) + 4 * v713) + 1);
                  v718 = *(_DWORD *)(v709 + 76) + (((_DWORD)v713 - v717) << 8);
                  if ( (unsigned int)v713 >= 0x14 )
                    v718 = ((_DWORD)v713 << 9) + v718 - 9728;
                  if ( (unsigned int)v714 <= 0x7F )
                  {
                    _mm_lfence();
                    v720 = *((unsigned __int8 *)&qword_1803EF770[8] + v714);
                  }
                  else
                  {
                    _BitScanReverse(&v719, v714);
                    LODWORD(v755) = 0;
                    v720 = v719 + 36;
                  }
                  v721 = 4 * v720;
                  LODWORD(v754) = 0;
                  _BitScanReverse((unsigned int *)&v720, *(_DWORD *)(*(_QWORD *)(v709 + 16) + 4 * v720) + 1);
                  v722 = *(_DWORD *)((char *)&qword_1803EF640[10] + v721);
                  LODWORD(v721) = v718 + 51;
                  v706 = v763;
                  v716 = v774 + *(_DWORD *)(v709 + 72) + ((v722 - (_DWORD)v720) << 8) + v721;
                }
                v360 = v779;
                if ( v710 > v364 )
                  goto LABEL_874;
                if ( v716 >= v779[7 * v710] )
                  break;
                if ( v364 < v710 )
                {
LABEL_874:
                  do
                    v360[7 * ++v364] = 0x40000000;
                  while ( v364 < v710 );
                  v772 = v364;
                }
                v723 = v710--;
                v724 = 7 * v723;
                v360[v724 + 3] = v767;
                *(_QWORD *)&v360[v724 + 4] = v707;
                v360[v724 + 2] = v712;
                v360[v724 + 1] = v702;
                v360[v724] = v716;
                v360[v724 + 6] = v706;
              }
              while ( v711 + v710 >= v708 );
              v700 = v764;
              v704 = v778;
              v698 = v753;
            }
            v697 = v773;
            ++v700;
            v701 = v704 + 2;
            v764 = v700;
            v778 = v701;
          }
          while ( v700 < v813 );
LABEL_835:
          v363 = v784;
LABEL_836:
          v365 = v753 + 1;
          v753 = v365;
          if ( v365 > v364 )
            goto LABEL_837;
          continue;
        }
        break;
      }
      v319 = 0;
      v317 = v779;
      DWORD1(v791) = v773[2 * v813 - 2];
      v730 = 7LL * v753;
      *((_QWORD *)&v791 + 1) = __PAIR64__(v767, v699);
      if ( v779[v730 + 2] )
      {
        v320 = 0;
        if ( v753 <= 0x1000 )
          v320 = v753;
      }
      else
      {
        v320 = 0;
        if ( v753 - v779[v730 + 3] <= 0x1000 )
          v320 = v753 - v779[v730 + 3];
      }
LABEL_380:
      v321 = v320 + 1;
      v322 = v320 + 1;
      v323 = 7LL * (v320 + 1);
      v324 = v788;
      *(_OWORD *)&v317[v323] = v791;
      *(_QWORD *)&v317[v323 + 4] = v15;
      v317[v323 + 6] = v324;
      while ( v320 )
      {
        v325 = &v317[7 * v320];
        v326 = *(_OWORD *)v325;
        v803 = v325[6];
        v327 = *((_QWORD *)v325 + 2);
        v801 = v326;
        v802 = v327;
        *(double *)&v326 = ZSTD_totalLen(&v801);
        v328 = 7LL * --v322;
        *(_OWORD *)&v317[v328] = v326;
        *(_QWORD *)&v317[v328 + 4] = *(_QWORD *)(v329 + 16);
        v317[v328 + 6] = *(_DWORD *)(v329 + 24);
        v330 = v320;
        v320 -= v331;
        if ( v330 <= v331 )
          v320 = v319;
      }
      v332 = v784;
      if ( v322 <= v321 )
      {
        v333 = v809;
        while ( 1 )
        {
          v334 = 7LL * v322;
          v335 = v317[v334 + 2];
          v336 = (unsigned int)v317[v334 + 3];
          v337 = v317[v334 + 1];
          v338 = v335 + v336;
          if ( v335 )
            break;
          v766 = v333 + v336;
LABEL_866:
          ++v322;
          v319 = 0;
          if ( v322 > v321 )
            goto LABEL_867;
        }
        if ( v337 >= 3 )
        {
          a3[2] = a3[1];
          a3[1] = *a3;
          *a3 = v337 - 2;
          goto LABEL_854;
        }
        v731 = v319;
        LOBYTE(v731) = (_DWORD)v336 == 0;
        v732 = v337 + v731;
        if ( (_DWORD)v732 )
        {
          if ( (_DWORD)v732 == 3 )
          {
            v733 = *a3 - 1;
            goto LABEL_852;
          }
          v733 = a3[v732];
          if ( (unsigned int)v732 >= 2 )
LABEL_852:
            a3[2] = a3[1];
          a3[1] = *a3;
          *a3 = v733;
        }
LABEL_854:
        ZSTD_updateStats(v332, v336, v809, v337, v335);
        v734 = v335 - 3;
        v736 = v735;
        v737 = *(_QWORD *)(a2 + 24);
        if ( v735 + v809 <= (unsigned __int64)(v750 - 32) )
        {
          ZSTD_copy16(v737);
          if ( v736 > 0x10 )
          {
            ZSTD_copy16(*(_QWORD *)(v739 + 24) + 16LL);
            v741 = ZSTD_copy16(v740 + 16);
            v743 = v742 + 16;
            if ( v743 < v741 )
            {
              do
              {
                ZSTD_copy16(v743);
                v745 = ZSTD_copy16(v744 + 16);
                v743 = v746 + 16;
              }
              while ( v743 < v745 );
            }
LABEL_860:
            v738 = v809;
          }
          *(_QWORD *)(v739 + 24) += v736;
          v747 = *(_QWORD *)(v739 + 8);
          if ( v736 > 0xFFFF )
          {
            *(_DWORD *)(v739 + 72) = 1;
            *(_DWORD *)(v739 + 76) = (v747 - *(_QWORD *)v739) >> 3;
          }
          *(_WORD *)(v747 + 4) = v736;
          **(_DWORD **)(v739 + 8) = v337 + 1;
          v748 = *(_QWORD *)(v739 + 8);
          if ( v734 > 0xFFFF )
          {
            *(_DWORD *)(v739 + 72) = 2;
            *(_DWORD *)(v739 + 76) = (v748 - *(_QWORD *)v739) >> 3;
          }
          v317 = v779;
          *(_WORD *)(v748 + 6) = v734;
          *(_QWORD *)(v739 + 8) += 8LL;
          v809 = v338 + v738;
          v333 = v809;
          v766 = v809;
          goto LABEL_866;
        }
        ZSTD_safecopyLiterals(v737);
        v739 = a2;
        goto LABEL_860;
      }
LABEL_867:
      ZSTD_setBasePrices(v332, 0);
      v14 = v766;
LABEL_870:
      v12 = v750;
      v7 = a1;
      v9 = v809;
      if ( v14 >= v790 )
        return &v12[-v9];
    }
    v232 = *(_DWORD *)(a1 + 204);
    v233 = *(_DWORD **)(a1 + 8);
    v765 = v233;
    if ( v232 < 0xFFF )
      v22 = v232;
    v753 = v14 - (_DWORD)v233;
    v234 = ZSTD_hash4Ptr(v14, v24, v23);
    v237 = *(_DWORD *)(v236 + 4 * v234);
    v238 = *(_DWORD **)(a1 + 64);
    v239 = *(_DWORD *)(a1 + 188);
    v778 = (unsigned int *)(v236 + 4 * v234);
    v240 = *(unsigned int *)(a1 + 24);
    v241 = v20;
    v755 = *(_QWORD *)(a1 + 16);
    LODWORD(v236) = 1 << (v239 - 1);
    v242 = 0;
    v243 = v236 - 1;
    v758 = 0;
    v768 = 0;
    v761 = v244 + v240;
    v771 = v238;
    v774 = v243;
    v770 = (unsigned int *)v240;
    if ( v243 < v235 )
      v242 = v235 - v243;
    v767 = v242;
    v245 = 1 << *(_DWORD *)(a1 + 184);
    v246 = v235 - v245;
    v247 = 1;
    if ( v235 - *(_DWORD *)(a1 + 28) <= v245 )
      v246 = *(_DWORD *)(a1 + 28);
    if ( *(_DWORD *)(a1 + 32) )
      v246 = *(_DWORD *)(a1 + 28);
    v248 = *(_DWORD *)(a1 + 196);
    if ( v246 )
      v247 = v246;
    v756 = v247;
    v811 = 0;
    v754 = &v238[2 * (v235 & v243)];
    v249 = v20 + 3;
    v772 = v20 + 3;
    v759 = (unsigned __int64)(v754 + 1);
    v752 = v235 + 9;
    v250 = 1 << v248;
    v251 = a3;
    v751 = v250;
    v785 = (unsigned int)(v782 - 1);
    v757 = v785;
    v252 = v20;
    v253 = v235 - v240;
    v254 = (unsigned int *)&a3[v252];
    while ( 1 )
    {
      if ( v241 == 3 )
        v255 = *v251 - 1;
      else
        v255 = *v254;
      v256 = v235 - v255;
      v257 = 0;
      if ( v255 - 1 >= v253 )
      {
        if ( v255 - 1 < v753 - v246 && (unsigned int)v240 - v256 - 1 >= 3 )
        {
          v269 = (unsigned int)(*(_DWORD *)(v755 + v256) << 8);
          LODWORD(v789) = 1;
          v270 = ZSTD_readMINMATCH(v766, 3, v269, 0);
          if ( v270 == v273 )
          {
            v274 = ZSTD_count_2segments(v271 + 3, v272 + 3, (_DWORD)v750, (int)v240 + (int)v755, v761);
            v249 = v772;
            v257 = v274 + 3;
          }
        }
      }
      else
      {
        v794 = 1;
        v258 = ZSTD_readMINMATCH(v766, 3, (unsigned int)(*(_DWORD *)(v766 - v255) << 8), 0);
        if ( v258 == v261 )
        {
          v262 = (char *)(v259 + 3);
          v263 = v259 + 3;
          v264 = (_QWORD *)(v260 + v259 + 3);
          v265 = (unsigned __int64)(v750 - 7);
          if ( v259 + 3 >= (unsigned __int64)(v750 - 7) )
            goto LABEL_296;
          if ( *(_QWORD *)v262 != *v264 )
          {
            v257 = ZSTD_NbCommonBytes(*(_QWORD *)v262 ^ *v264, v262, v264, v263) + 3;
            goto LABEL_310;
          }
          v262 = (char *)(v259 + 11);
          ++v264;
          if ( v259 + 11 >= v265 )
          {
LABEL_296:
            if ( v262 < v750 - 3 && *(_DWORD *)v264 == *(_DWORD *)v262 )
            {
              v262 += 4;
              v264 = (_QWORD *)((char *)v264 + 4);
            }
            if ( v262 < v750 - 1 && *(_WORD *)v264 == *(_WORD *)v262 )
            {
              v262 += 2;
              v264 = (_QWORD *)((char *)v264 + 2);
            }
            if ( v262 < v750 && *(_BYTE *)v264 == *v262 )
              LODWORD(v262) = (_DWORD)v262 + 1;
            v257 = (_DWORD)v262 - v259;
          }
          else
          {
            while ( *(_QWORD *)v262 == *v264 )
            {
              v262 += 8;
              ++v264;
              if ( (unsigned __int64)v262 >= v265 )
                goto LABEL_296;
            }
            v266 = ZSTD_NbCommonBytes(*(_QWORD *)v262 ^ *v264, v262, v264, v263);
            v257 = v267 - v268 + v266 + 3;
          }
        }
      }
LABEL_310:
      v275 = v757;
      if ( v257 > v757 )
      {
        v275 = v257;
        v276 = &v773[2 * v811];
        *v276 = v241 - v760;
        v277 = v811 + 1;
        v757 = v257;
        v278 = (char *)(v766 + v257);
        v276[1] = v257;
        ++v811;
        if ( v257 > v22 || v278 == v750 )
        {
          v164 = v277;
          goto LABEL_376;
        }
      }
      ++v241;
      ++v254;
      if ( v241 >= v249 )
      {
        if ( v275 >= 3 )
        {
          v281 = v753;
          goto LABEL_326;
        }
        v279 = v766;
        v280 = ZSTD_insertAndFindFirstIndexHash3(a1, &v786, v766);
        v281 = v753;
        v282 = v756;
        v283 = v753 - v280;
        if ( v280 < v756 || v753 - v280 >= 0x40000 )
        {
          v275 = v757;
          v287 = v811;
          goto LABEL_328;
        }
        if ( v280 < (unsigned int)v240 )
        {
          v284 = ZSTD_count_2segments(v279, (unsigned int)v755 + v280, (_DWORD)v750, (int)v755 + (int)v240, v761);
          v285 = v750;
        }
        else
        {
          v284 = ZSTD_count(v279, (char *)v765 + v280, v750);
        }
        if ( v284 < 3 )
        {
          v275 = v757;
LABEL_326:
          v287 = v811;
          goto LABEL_327;
        }
        v286 = v773;
        v275 = v284;
        v757 = v284;
        v287 = 1;
        v811 = 1;
        *v773 = v283 + 2;
        v286[1] = v284;
        if ( v284 > v22 || v284 + v279 == (_QWORD)v285 )
        {
          *(_DWORD *)(a1 + 36) = v281 + 1;
          goto LABEL_375;
        }
LABEL_327:
        v282 = v756;
LABEL_328:
        v288 = v751;
        *v778 = v281;
        if ( !v288 )
        {
LABEL_373:
          v309 = v754;
LABEL_374:
          *(_DWORD *)v759 = 0;
          *v309 = 0;
          *(_DWORD *)(a1 + 36) = v752 - 8;
LABEL_375:
          v164 = v287;
          goto LABEL_376;
        }
        v289 = v758;
        while ( 2 )
        {
          v751 = --v288;
          if ( v237 < v282 )
            goto LABEL_373;
          v290 = v768;
          if ( v289 < (unsigned __int64)v768 )
            v290 = (_DWORD *)v289;
          v291 = &v771[2 * (v237 & v774)];
          if ( (_DWORD *)((char *)v290 + v237) < v770 )
          {
            v302 = (char *)v290 + v766;
            v292 = v237 + v755;
            v303 = v750;
            if ( (char *)v770 + v766 - v237 < v750 )
              v303 = (char *)v770 + v766 - v237;
            v304 = ZSTD_count((char *)v290 + v766, (char *)v290 + v237 + v755, v303);
            v306 = (_DWORD *)(v304 + v305);
            v307 = (unsigned __int64)v770;
            if ( v306 == (unsigned int *)((char *)v770 + v755) )
              v304 += ZSTD_count(&v302[v304], v761, v750);
            v275 = v757;
            v298 = (unsigned __int64)v290 + v304;
            v281 = v753;
            v289 = v758;
            v92 = v298 + v237 < v307;
            v288 = v751;
            if ( !v92 )
              v292 = (unsigned __int64)v765 + v237;
            v293 = v750;
            goto LABEL_358;
          }
          v292 = (unsigned __int64)v765 + v237;
          v293 = v750;
          v294 = (char *)v290 + v766;
          v295 = (char *)v290 + v766;
          v296 = (_QWORD *)((char *)v290 + v292);
          v297 = (unsigned __int64)(v750 - 7);
          if ( (char *)v290 + v766 < v750 - 7 )
          {
            if ( *(_QWORD *)v294 != *v296 )
            {
              v298 = (unsigned __int64)v290
                   + (unsigned int)ZSTD_NbCommonBytes(*(_QWORD *)v294 ^ *v296, v294, v296, v295);
LABEL_358:
              if ( v298 <= v275 )
              {
                v287 = v811;
              }
              else
              {
                if ( v298 > v752 - v237 )
                  v752 = v298 + v237;
                v308 = v773;
                v773[2 * v811 + 1] = v298;
                v308[2 * v811] = v281 - v237 + 2;
                v287 = v811 + 1;
                v757 = v298;
                ++v811;
                v275 = v298;
                if ( v298 > 0x1000 || v298 + v766 == (_QWORD)v293 )
                  goto LABEL_373;
              }
              if ( *(_BYTE *)(v292 + v298) >= *(_BYTE *)(v298 + v766) )
              {
                v768 = (_DWORD *)v298;
                *(_DWORD *)v759 = v237;
                if ( v237 <= v767 )
                {
                  v759 = (unsigned __int64)&v756;
                  goto LABEL_373;
                }
                v237 = *v291;
                v759 = (unsigned __int64)v291;
              }
              else
              {
                v289 = v298;
                v758 = v298;
                *v754 = v237;
                if ( v237 <= v767 )
                {
                  v309 = &v756;
                  goto LABEL_374;
                }
                v237 = v291[1];
                v754 = v291 + 1;
              }
              if ( !v288 )
                goto LABEL_373;
              v282 = v756;
              continue;
            }
            v294 += 8;
            ++v296;
            if ( (unsigned __int64)v294 < v297 )
            {
              while ( *(_QWORD *)v294 == *v296 )
              {
                v294 += 8;
                ++v296;
                if ( (unsigned __int64)v294 >= v297 )
                  goto LABEL_340;
              }
              v299 = ZSTD_NbCommonBytes(*(_QWORD *)v294 ^ *v296, v294, v296, v295);
              v298 = (unsigned __int64)v290 + v300 - v301 + v299;
              goto LABEL_358;
            }
          }
          break;
        }
LABEL_340:
        if ( v294 < v750 - 3 && *(_DWORD *)v296 == *(_DWORD *)v294 )
        {
          v294 += 4;
          v296 = (_QWORD *)((char *)v296 + 4);
        }
        if ( v294 < v750 - 1 && *(_WORD *)v296 == *(_WORD *)v294 )
        {
          v294 += 2;
          v296 = (_QWORD *)((char *)v296 + 2);
        }
        if ( v294 < v750 && *(_BYTE *)v296 == *v294 )
          ++v294;
        v298 = (unsigned __int64)&v294[-v766];
        goto LABEL_358;
      }
      v235 = v753;
      v251 = a3;
    }
  }
  return &v12[-v9];
}

```

## disassembly

```asm
0x1802d0440  mov     [rsp-8+arg_18], r9
0x1802d0445  mov     [rsp-8+arg_10], r8
0x1802d044a  mov     [rsp-8+arg_8], rdx
0x1802d044f  mov     [rsp-8+arg_0], rcx
0x1802d0454  push    rbp
0x1802d0455  push    rbx
0x1802d0456  push    rsi
0x1802d0457  push    rdi
0x1802d0458  push    r13
0x1802d045a  push    r14
0x1802d045c  push    r15
0x1802d045e  lea     rbp, [rsp-110h]
0x1802d0466  sub     rsp, 210h
0x1802d046d  mov     eax, [rcx+0CCh]
0x1802d0473  lea     r13, [rcx+48h]
0x1802d0477  mov     ebx, [rcx+18h]
0x1802d047a  mov     rdi, rcx
0x1802d047d  add     rbx, [rcx+8]
0x1802d0481  mov     rsi, r9
0x1802d0484  mov     r8, [rbp+140h+arg_20]
0x1802d048b  mov     ecx, 0FFFh
0x1802d0490  cmp     eax, ecx
0x1802d0492  mov     [rbp+140h+var_120], r13
0x1802d0496  mov     rdx, rsi
0x1802d0499  cmovb   ecx, eax
0x1802d049c  xor     eax, eax
0x1802d049e  cmp     dword ptr [rdi+0C8h], 3
0x1802d04a5  lea     r15, [r9+r8]
0x1802d04a9  mov     [rbp+140h+var_10C], ecx
0x1802d04ac  lea     r14, [r15-8]
0x1802d04b0  setnz   al
0x1802d04b3  mov     [rsp+240h+var_210], r15
0x1802d04b8  add     eax, 3
0x1802d04bb  mov     [rbp+140h+var_F8], r14
0x1802d04bf  mov     [rbp+140h+var_130], eax
0x1802d04c2  xor     r9d, r9d
0x1802d04c5  mov     eax, [rdi+24h]
0x1802d04c8  mov     rcx, r13
0x1802d04cb  mov     [rbp+140h+var_110], eax
0x1802d04ce  mov     rax, [r13+28h]
0x1802d04d2  mov     [rbp+140h+var_148], rax
0x1802d04d6  mov     rax, [r13+20h]
0x1802d04da  mov     [rbp+140h+var_168], rax
0x1802d04de  call    ZSTD_rescaleFreqs
0x1802d04e3  xor     r11d, r11d
0x1802d04e6  cmp     rsi, rbx
0x1802d04e9  mov     ecx, r11d
0x1802d04ec  setz    cl
0x1802d04ef  add     rcx, rsi
0x1802d04f2  mov     [rbp+140h+var_1A0], rcx
0x1802d04f6  cmp     rcx, r14
0x1802d04f9  jnb     loc_1802D4084
0x1802d04ff  mov     eax, [rbp+140h+var_D8]
0x1802d0502  movsd   xmm2, [rbp+140h+var_E0]
0x1802d0507  mov     [rbp+140h+var_108], eax
0x1802d050a  mov     [rsp+240h+var_38], r12
0x1802d0512  mov     ebx, [rdi+24h]
0x1802d0515  mov     eax, ecx
0x1802d0517  mov     r14, [rdi+8]
0x1802d051b  sub     eax, esi
0x1802d051d  mov     esi, [rdi+0C8h]
0x1802d0523  mov     r12d, r11d
0x1802d0526  setz    r12b
0x1802d052a  mov     [rbp+140h+var_1B4], eax
0x1802d052d  mov     [rsp+240h+var_1C8], r12d
0x1802d0532  lea     rax, [r14+rbx]
0x1802d0536  cmp     rcx, rax
0x1802d0539  jb      loc_1802D4052
0x1802d053f  mov     edi, ecx
0x1802d0541  sub     edi, r14d
0x1802d0544  cmp     ebx, edi
0x1802d0546  jnb     short loc_1802D057D
0x1802d0548  mov     r12, [rbp+140h+arg_0]
0x1802d054f  nop
0x1802d0550  mov     edx, ebx
0x1802d0552  mov     r9d, esi
0x1802d0555  add     rdx, r14
0x1802d0558  mov     dword ptr [rsp+240h+var_220], 1
0x1802d0560  mov     r8, r15
0x1802d0563  mov     rcx, r12
0x1802d0566  call    ZSTD_insertBt1
0x1802d056b  add     ebx, eax
0x1802d056d  cmp     ebx, edi
0x1802d056f  jb      short loc_1802D0550
0x1802d0571  mov     r12d, [rsp+240h+var_1C8]
0x1802d0576  xor     r11d, r11d
0x1802d0579  mov     rcx, [rbp+140h+var_1A0]
0x1802d057d  mov     r14, [rbp+140h+arg_0]
0x1802d0584  mov     r13d, 0FFFh
0x1802d058a  mov     r8, [r14+30h]
0x1802d058e  mov     [r14+24h], edi
0x1802d0592  mov     edx, [r14+0C0h]
0x1802d0599  cmp     esi, 3
0x1802d059c  jz      loc_1802D168E
0x1802d05a2  mov     r9, [r14+8]
0x1802d05a6  mov     r10d, ecx
0x1802d05a9  mov     [rbp+140h+var_190], r9
0x1802d05ad  cmp     esi, 5
0x1802d05b0  jz      loc_1802D10FF
0x1802d05b6  lea     eax, [rsi-6]
0x1802d05b9  cmp     eax, 1
0x1802d05bc  mov     eax, [r14+0CCh]
0x1802d05c3  ja      loc_1802D0B52
0x1802d05c9  cmp     eax, r13d
0x1802d05cc  cmovb   r13d, eax
0x1802d05d0  sub     r10d, r9d
0x1802d05d3  mov     [rsp+240h+var_200], r10d
0x1802d05d8  call    ZSTD_hash6Ptr
0x1802d05dd  mov     r15d, [r8+rax*4]
0x1802d05e1  lea     rax, [r8+rax*4]
0x1802d05e5  mov     ecx, [r14+0BCh]
0x1802d05ec  mov     edx, 1
0x1802d05f1  mov     rbx, [r14+40h]
0x1802d05f5  dec     ecx
0x1802d05f7  mov     [rbp+140h+var_150], rax
0x1802d05fb  mov     r8d, 1
0x1802d0601  mov     rax, [r14+10h]
0x1802d0605  mov     esi, r10d
0x1802d0608  mov     [rsp+240h+var_1F8], rax
0x1802d060d  shl     r8d, cl
0x1802d0610  xor     ecx, ecx
0x1802d0612  dec     r8d
0x1802d0615  mov     [rsp+240h+var_1D8], r11
0x1802d061a  mov     [rsp+240h+var_1D0], r11
0x1802d061f  mov     r11d, [r14+18h]
0x1802d0623  mov     [rbp+140h+var_178], rbx
0x1802d0627  mov     [rbp+140h+var_1B0], r8d
0x1802d062b  mov     [rbp+140h+var_170], r11d
0x1802d062f  lea     rax, [r9+r11]
0x1802d0633  mov     [rbp+140h+var_1A8], r11
0x1802d0637  mov     [rbp+140h+var_180], rax
0x1802d063b  mov     eax, r10d
0x1802d063e  sub     eax, r8d
0x1802d0641  cmp     r8d, r10d
0x1802d0644  cmovb   ecx, eax
0x1802d0647  mov     eax, r10d
0x1802d064a  mov     [rbp+140h+var_198], ecx
0x1802d064d  mov     ecx, [r14+0B8h]
0x1802d0654  shl     edx, cl
0x1802d0656  mov     ecx, [r14+1Ch]
0x1802d065a  sub     esi, edx
0x1802d065c  sub     eax, ecx
0x1802d065e  cmp     eax, edx
0x1802d0660  mov     eax, 1
0x1802d0665  cmovbe  esi, ecx
0x1802d0668  cmp     dword ptr [r14+20h], 0
0x1802d066d  cmovnz  esi, ecx
0x1802d0670  mov     ecx, [r14+0C4h]
0x1802d0677  test    esi, esi
0x1802d0679  mov     r14d, r10d
0x1802d067c  cmovnz  eax, esi
0x1802d067f  xor     edx, edx
0x1802d0681  mov     [rbp+140h+var_160], eax
0x1802d0684  add     r12d, 3
0x1802d0688  mov     eax, r8d
0x1802d068b  mov     dword ptr [rbp+140h+arg_20], edx
0x1802d0691  and     eax, r10d
0x1802d0694  add     eax, eax
0x1802d0696  lea     rax, [rbx+rax*4]
0x1802d069a  mov     [rsp+240h+var_1E0], rax
0x1802d069f  add     rax, 4
0x1802d06a3  mov     [rbp+140h+var_1C0], rax
0x1802d06a7  lea     eax, [r10+9]
0x1802d06ab  mov     [rsp+240h+var_204], eax
0x1802d06af  mov     eax, 1
0x1802d06b4  shl     eax, cl
0x1802d06b6  mov     rcx, [rbp+140h+arg_10]
0x1802d06bd  mov     [rsp+240h+var_208], eax
0x1802d06c1  mov     eax, [rbp+140h+var_130]
0x1802d06c4  dec     eax
0x1802d06c6  mov     [rbp+140h+var_118], rax
0x1802d06ca  sub     r14d, r11d
0x1802d06cd  mov     [rsp+240h+var_1F0], rax
0x1802d06d2  mov     eax, [rsp+240h+var_1C8]
0x1802d06d6  mov     ebx, eax
0x1802d06d8  lea     rdi, [rcx+rax*4]
0x1802d06dc  nop     dword ptr [rax+00h]
0x1802d06e0  cmp     ebx, 3
0x1802d06e3  jnz     short loc_1802D06EB
0x1802d06e5  mov     eax, [rcx]
0x1802d06e7  dec     eax
0x1802d06e9  jmp     short loc_1802D06ED
0x1802d06eb  mov     eax, [rdi]
0x1802d06ed  mov     r9d, r10d
0x1802d06f0  lea     ecx, [rax-1]
0x1802d06f3  sub     r9d, eax
0x1802d06f6  mov     r8d, edx
0x1802d06f9  cmp     ecx, r14d
0x1802d06fc  jnb     loc_1802D07DC
0x1802d0702  mov     rcx, [rbp+140h+var_1A0]
0x1802d0706  mov     edx, 4
0x1802d070b  mov     r9d, eax
0x1802d070e  neg     r9
0x1802d0711  call    ZSTD_readMINMATCH
0x1802d0716  cmp     eax, [r9+rcx]
0x1802d071a  jnz     loc_1802D0847
0x1802d0720  lea     rdx, [rcx+4]
0x1802d0724  lea     r8, [rcx+4]
0x1802d0728  mov     rcx, [rsp+240h+var_210]
0x1802d072d  add     r8, r9
0x1802d0730  mov     r9, rdx
0x1802d0733  lea     rax, [rcx-7]
0x1802d0737  cmp     rdx, rax
0x1802d073a  jnb     short loc_1802D077B
0x1802d073c  mov     rcx, [rdx]
0x1802d073f  xor     rcx, [r8]
0x1802d0742  jz      short loc_1802D0754
0x1802d0744  call    ZSTD_NbCommonBytes
0x1802d0749  mov     ecx, eax
0x1802d074b  lea     r8d, [rcx+4]
0x1802d074f  jmp     loc_1802D0847
0x1802d0754  add     rdx, 8
0x1802d0758  add     r8, 8
0x1802d075c  cmp     rdx, rax
0x1802d075f  jnb     short loc_1802D0776
0x1802d0761  mov     rcx, [rdx]
0x1802d0764  xor     rcx, [r8]
0x1802d0767  jnz     short loc_1802D07C9
0x1802d0769  add     rdx, 8
0x1802d076d  add     r8, 8
0x1802d0771  cmp     rdx, rax
0x1802d0774  jb      short loc_1802D0761
0x1802d0776  mov     rcx, [rsp+240h+var_210]
0x1802d077b  lea     rax, [rcx-3]
0x1802d077f  cmp     rdx, rax
0x1802d0782  jnb     short loc_1802D0793
0x1802d0784  mov     eax, [rdx]
0x1802d0786  cmp     [r8], eax
0x1802d0789  jnz     short loc_1802D0793
0x1802d078b  add     rdx, 4
0x1802d078f  add     r8, 4
0x1802d0793  lea     rax, [rcx-1]
0x1802d0797  cmp     rdx, rax
0x1802d079a  jnb     short loc_1802D07AD
0x1802d079c  movzx   eax, word ptr [rdx]
0x1802d079f  cmp     [r8], ax
0x1802d07a3  jnz     short loc_1802D07AD
0x1802d07a5  add     rdx, 2
0x1802d07a9  add     r8, 2
0x1802d07ad  cmp     rdx, rcx
0x1802d07b0  jnb     short loc_1802D07BD
0x1802d07b2  movzx   eax, byte ptr [rdx]
0x1802d07b5  cmp     [r8], al
0x1802d07b8  jnz     short loc_1802D07BD
0x1802d07ba  inc     rdx
0x1802d07bd  mov     rcx, rdx
0x1802d07c0  sub     rcx, r9
0x1802d07c3  lea     r8d, [rcx+4]
0x1802d07c7  jmp     short loc_1802D0847
0x1802d07c9  call    ZSTD_NbCommonBytes
0x1802d07ce  mov     ecx, eax
0x1802d07d0  sub     rdx, r9
0x1802d07d3  add     rcx, rdx
0x1802d07d6  lea     r8d, [rcx+4]
0x1802d07da  jmp     short loc_1802D0847
0x1802d07dc  mov     eax, [rsp+240h+var_200]
0x1802d07e0  sub     eax, esi
0x1802d07e2  mov     r10d, r9d
0x1802d07e5  add     r10, [rsp+240h+var_1F8]
0x1802d07ea  cmp     ecx, eax
0x1802d07ec  mov     ecx, r11d
0x1802d07ef  setb    dl
0x1802d07f2  sub     ecx, r9d
0x1802d07f5  xor     eax, eax
0x1802d07f7  dec     ecx
0x1802d07f9  cmp     ecx, 3
0x1802d07fc  setnb   al
0x1802d07ff  test    eax, edx
0x1802d0801  jz      short loc_1802D0842
0x1802d0803  mov     rcx, [rbp+140h+var_1A0]
0x1802d0807  mov     edx, 4
0x1802d080c  call    ZSTD_readMINMATCH
0x1802d0811  cmp     eax, [r10]
0x1802d0814  jnz     short loc_1802D0842
0x1802d0816  mov     rax, [rbp+140h+var_180]
0x1802d081a  lea     rdx, [r10+4]
0x1802d081e  mov     r9, [rsp+240h+var_1F8]
0x1802d0823  add     rcx, 4
0x1802d0827  add     r9, [rbp+140h+var_1A8]
0x1802d082b  mov     r8, [rsp+240h+var_210]
0x1802d0830  mov     [rsp+240h+var_220], rax
0x1802d0835  call    ZSTD_count_2segments
0x1802d083a  mov     r11d, [rbp+140h+var_170]
0x1802d083e  lea     r8d, [rax+4]
0x1802d0842  mov     r10d, [rsp+240h+var_200]
0x1802d0847  mov     eax, r8d
0x1802d084a  cmp     rax, [rsp+240h+var_1F0]
0x1802d084f  jbe     short loc_1802D08A0
0x1802d0851  mov     r9d, dword ptr [rbp+140h+arg_20]
0x1802d0858  mov     ecx, ebx
0x1802d085a  sub     ecx, [rsp+240h+var_1C8]
0x1802d085e  mov     rdx, [rbp+140h+var_168]
0x1802d0862  lea     rdx, [rdx+r9*8]
0x1802d0866  inc     r9d
0x1802d0869  mov     [rdx], ecx
0x1802d086b  mov     [rsp+240h+var_1F0], rax
0x1802d0870  add     rax, [rbp+140h+var_1A0]
0x1802d0874  mov     dword ptr [rbp+140h+arg_20], r9d
0x1802d087b  mov     r9, [rsp+240h+var_210]
0x1802d0880  mov     [rdx+4], r8d
  ... truncated ...
```
