# ZSTD_compressBlock_btultra_extDict

- ea: `0x1802de8e0`
- end: `0x1802e2575`
- name: `ZSTD_compressBlock_btultra_extDict`
- size: `15509`
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
- `0x1802de8e0`
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
unsigned __int64 __fastcall ZSTD_compressBlock_btultra_extDict(
        __int64 a1,
        __int64 a2,
        int *a3,
        unsigned __int64 a4,
        __int64 a5)
{
  __int64 v5; // r13
  __int64 v6; // rcx
  int v7; // edx
  unsigned __int64 v8; // rdi
  unsigned int v9; // eax
  unsigned __int64 v10; // r15
  unsigned __int64 v11; // rsi
  __int64 v12; // rbx
  bool v13; // zf
  unsigned __int64 v14; // rcx
  __int64 v15; // xmm2_8
  __int64 v16; // rbx
  __int64 v17; // r14
  int v18; // esi
  BOOL v19; // r12d
  unsigned int v20; // edi
  unsigned int v21; // r13d
  __int64 v22; // r8
  __int64 v23; // rdx
  _DWORD *v24; // r9
  unsigned int v25; // eax
  __int64 v26; // rax
  unsigned int v27; // r10d
  __int64 v28; // r8
  unsigned int v29; // r15d
  __int64 v30; // rbx
  char v31; // cl
  unsigned int v32; // ecx
  unsigned int v33; // r8d
  unsigned int *v34; // r11
  _DWORD *v35; // r11
  __int64 v36; // r9
  unsigned int v37; // edx
  int v38; // esi
  int v39; // eax
  int v40; // ecx
  unsigned int v41; // r12d
  int v42; // eax
  int *v43; // rcx
  unsigned int v44; // r14d
  unsigned int v45; // ebx
  unsigned int *v46; // rdi
  unsigned int v47; // eax
  __int64 v48; // r9
  unsigned int v49; // r8d
  int v50; // eax
  __int64 v51; // rcx
  __int64 v52; // r9
  _QWORD *v53; // rdx
  __int64 v54; // r8
  unsigned __int64 v55; // rcx
  _QWORD *v56; // r8
  _QWORD *v57; // r9
  unsigned __int64 v58; // rax
  int v59; // eax
  int v60; // edx
  int v61; // r9d
  int v62; // eax
  int v63; // ecx
  _DWORD *v64; // r10
  int v65; // eax
  _DWORD *v66; // rdx
  unsigned __int64 v67; // rax
  unsigned __int64 v68; // r9
  unsigned int v69; // r10d
  unsigned __int64 v70; // r11
  unsigned __int64 v71; // r14
  unsigned int *v72; // rsi
  unsigned __int64 v73; // rbx
  unsigned int *v74; // r13
  _QWORD *v75; // rdx
  char *v76; // r12
  unsigned __int64 v77; // r9
  unsigned __int64 v78; // rdi
  char *v79; // r8
  unsigned __int64 v80; // rax
  unsigned __int64 v81; // rbx
  unsigned int v82; // eax
  __int64 v83; // rdx
  __int64 v84; // r9
  unsigned __int64 v85; // r14
  char *v86; // r8
  __int64 v87; // rsi
  __int64 v88; // r11
  _DWORD *v89; // rcx
  unsigned __int64 v90; // r11
  bool v91; // cf
  _DWORD *v92; // rcx
  int v93; // eax
  unsigned int *v94; // rax
  unsigned int *v95; // rax
  __int64 v96; // rax
  unsigned int v97; // r10d
  __int64 v98; // r8
  unsigned int v99; // r15d
  __int64 v100; // rbx
  char v101; // cl
  unsigned int v102; // ecx
  unsigned int v103; // r8d
  unsigned int *v104; // r11
  _DWORD *v105; // r11
  __int64 v106; // r9
  unsigned int v107; // edx
  int v108; // esi
  int v109; // eax
  int v110; // ecx
  unsigned int v111; // r12d
  int v112; // eax
  int *v113; // rcx
  unsigned int v114; // r14d
  unsigned int v115; // ebx
  unsigned int *v116; // rdi
  unsigned int v117; // eax
  __int64 v118; // r9
  unsigned int v119; // r8d
  int v120; // eax
  __int64 v121; // rcx
  __int64 v122; // r9
  _QWORD *v123; // rdx
  __int64 v124; // r8
  unsigned __int64 v125; // rcx
  _QWORD *v126; // r8
  _QWORD *v127; // r9
  unsigned __int64 v128; // rax
  int v129; // eax
  int v130; // edx
  int v131; // r9d
  int v132; // eax
  int v133; // ecx
  _DWORD *v134; // r10
  int v135; // eax
  _DWORD *v136; // rdx
  unsigned __int64 v137; // rax
  unsigned __int64 v138; // r9
  unsigned int v139; // r10d
  unsigned __int64 v140; // r11
  unsigned __int64 v141; // r14
  unsigned int *v142; // rsi
  unsigned __int64 v143; // rbx
  unsigned int *v144; // r13
  _QWORD *v145; // rdx
  char *v146; // r12
  unsigned __int64 v147; // r9
  unsigned __int64 v148; // rdi
  char *v149; // r8
  unsigned __int64 v150; // rax
  unsigned __int64 v151; // rbx
  unsigned int v152; // eax
  __int64 v153; // rdx
  __int64 v154; // r9
  unsigned __int64 v155; // r14
  char *v156; // r8
  __int64 v157; // rsi
  __int64 v158; // r11
  _DWORD *v159; // rcx
  unsigned __int64 v160; // r11
  _DWORD *v161; // rcx
  int v162; // eax
  unsigned int v163; // ebx
  __int64 v164; // rax
  unsigned int v165; // r10d
  __int64 v166; // r8
  unsigned int v167; // r15d
  __int64 v168; // rbx
  char v169; // cl
  unsigned int v170; // ecx
  unsigned int v171; // r8d
  unsigned int *v172; // r11
  _DWORD *v173; // r11
  __int64 v174; // r9
  unsigned int v175; // edx
  int v176; // esi
  int v177; // eax
  int v178; // ecx
  unsigned int v179; // r12d
  int v180; // eax
  int *v181; // rcx
  unsigned int v182; // r14d
  unsigned int v183; // ebx
  unsigned int *v184; // rdi
  unsigned int v185; // eax
  __int64 v186; // r9
  unsigned int v187; // r8d
  int v188; // eax
  __int64 v189; // rcx
  __int64 v190; // r9
  _QWORD *v191; // rdx
  __int64 v192; // r8
  unsigned __int64 v193; // rcx
  _QWORD *v194; // r8
  _QWORD *v195; // r9
  unsigned __int64 v196; // rax
  int v197; // eax
  int v198; // edx
  int v199; // r9d
  int MINMATCH; // eax
  int v201; // ecx
  _DWORD *v202; // r10
  int v203; // eax
  _DWORD *v204; // rdx
  unsigned __int64 v205; // rax
  unsigned __int64 v206; // r9
  unsigned int v207; // r10d
  unsigned __int64 v208; // r11
  unsigned __int64 v209; // r14
  unsigned int *v210; // rsi
  unsigned __int64 v211; // rbx
  unsigned int *v212; // r13
  _QWORD *v213; // rdx
  char *v214; // r12
  unsigned __int64 v215; // r9
  unsigned __int64 v216; // rdi
  char *v217; // r8
  unsigned __int64 v218; // rax
  unsigned __int64 v219; // rbx
  unsigned int v220; // eax
  __int64 v221; // rdx
  __int64 v222; // r9
  unsigned __int64 v223; // r14
  char *v224; // r8
  __int64 v225; // rsi
  __int64 v226; // r11
  _DWORD *v227; // rcx
  unsigned __int64 v228; // r11
  _DWORD *v229; // rcx
  int v230; // eax
  unsigned int v231; // eax
  _DWORD *v232; // r10
  __int64 v233; // rax
  unsigned int v234; // r9d
  __int64 v235; // r8
  unsigned int v236; // r15d
  __int64 v237; // r11
  int v238; // ecx
  unsigned int *v239; // r14
  unsigned int v240; // ebx
  unsigned int v241; // ecx
  unsigned int v242; // r8d
  __int64 v243; // r10
  unsigned int v244; // edx
  int v245; // esi
  int v246; // eax
  int v247; // ecx
  unsigned int v248; // r11d
  int v249; // eax
  int *v250; // rcx
  _BOOL8 v251; // rax
  unsigned int v252; // r12d
  unsigned int *v253; // rdi
  unsigned int v254; // eax
  unsigned int v255; // r8d
  unsigned int v256; // r9d
  int v257; // eax
  __int64 v258; // rcx
  __int64 v259; // r10
  int v260; // r8d
  _QWORD *v261; // rdx
  __int64 v262; // r9
  _QWORD *v263; // r8
  unsigned __int64 v264; // rax
  int v265; // eax
  int v266; // edx
  int v267; // r9d
  __int64 v268; // r8
  int v269; // eax
  int v270; // ecx
  int v271; // r10d
  int v272; // r8d
  int v273; // eax
  unsigned __int64 v274; // r10
  _DWORD *v275; // rdx
  unsigned int v276; // r8d
  unsigned __int64 v277; // rax
  unsigned __int64 v278; // rdi
  unsigned int v279; // eax
  unsigned int v280; // esi
  unsigned int v281; // r8d
  unsigned int v282; // ebx
  unsigned __int64 v283; // rax
  unsigned __int64 v284; // r11
  _DWORD *v285; // rcx
  int v286; // r9d
  unsigned int v287; // r11d
  unsigned __int64 v288; // r14
  _DWORD *v289; // rbx
  unsigned int *v290; // r13
  unsigned __int64 v291; // r12
  unsigned __int64 v292; // rdi
  _QWORD *v293; // rdx
  char *v294; // r9
  _QWORD *v295; // r8
  unsigned __int64 v296; // rax
  unsigned __int64 v297; // rbx
  unsigned int v298; // eax
  __int64 v299; // rdx
  __int64 v300; // r9
  char *v301; // r14
  char *v302; // r8
  __int64 v303; // rsi
  __int64 v304; // r11
  _DWORD *v305; // rcx
  unsigned int *v306; // r11
  _DWORD *v307; // rcx
  unsigned int *v308; // rax
  _DWORD *v309; // rcx
  unsigned int v310; // r13d
  __int64 v311; // r14
  __int64 v312; // r8
  int v313; // eax
  _DWORD *v314; // r9
  unsigned int *v315; // rsi
  unsigned __int64 v316; // rcx
  unsigned int v317; // edi
  _DWORD *v318; // rax
  unsigned __int64 v319; // r12
  unsigned int *v320; // r15
  unsigned int v321; // ebx
  __int64 updated; // rax
  int v323; // r10d
  int v324; // r11d
  __int64 v325; // xmm1_8
  int v326; // r14d
  __int64 v327; // r12
  __int64 v328; // r9
  __int64 v329; // r8
  unsigned int v330; // ecx
  unsigned int v331; // edx
  __int64 v332; // rax
  unsigned int v333; // edx
  unsigned int v334; // ecx
  unsigned int v335; // r9d
  unsigned int v336; // eax
  __int64 v337; // rax
  unsigned int v338; // r8d
  unsigned int v339; // ecx
  _DWORD *v340; // r9
  __int64 v341; // rcx
  unsigned int v342; // edi
  unsigned int v343; // eax
  __int64 v344; // r15
  unsigned int *v345; // r12
  _DWORD *v346; // r14
  unsigned int v347; // esi
  __int64 v348; // r13
  int v349; // ebx
  int v350; // r8d
  int v351; // ebx
  int v352; // eax
  __int64 v353; // r8
  int v354; // eax
  _DWORD *v355; // rbx
  int v356; // r15d
  __int64 v357; // xmm0_8
  int v358; // eax
  int v359; // eax
  __int64 v360; // rbx
  __int64 v361; // r15
  int v362; // r14d
  unsigned int v363; // esi
  int v364; // r11d
  __int64 v365; // r9
  __int64 v366; // r8
  __int64 v367; // rdx
  unsigned int v368; // eax
  unsigned int v369; // esi
  __int64 v370; // rax
  __int64 v371; // r8
  unsigned int v372; // r13d
  __int64 v373; // rbx
  unsigned __int64 v374; // r10
  char v375; // cl
  __int64 v376; // r9
  unsigned int v377; // ecx
  unsigned int v378; // r8d
  unsigned int v379; // edx
  int v380; // ecx
  int v381; // r12d
  int v382; // eax
  int v383; // ecx
  int v384; // eax
  unsigned int v385; // r8d
  int v386; // eax
  _DWORD *v387; // rcx
  unsigned int v388; // edx
  unsigned int v389; // r14d
  unsigned int v390; // r10d
  unsigned int *v391; // r15
  unsigned int v392; // eax
  __int64 v393; // r9
  int v394; // eax
  __int64 v395; // rcx
  __int64 v396; // r9
  unsigned int v397; // r11d
  _DWORD *v398; // rsi
  _QWORD *v399; // rdx
  _QWORD *v400; // r8
  unsigned __int64 v401; // rax
  __int64 v402; // r9
  int v403; // eax
  int v404; // edx
  int v405; // r9d
  int v406; // eax
  __int64 v407; // rdx
  __int64 v408; // rcx
  _DWORD *v409; // r11
  unsigned __int64 v410; // r8
  __int64 v411; // rsi
  char *v412; // rdx
  unsigned __int64 v413; // rcx
  __int64 v414; // r11
  __int64 v415; // rcx
  int v416; // eax
  _DWORD *v417; // rcx
  unsigned int *v418; // r9
  unsigned int v419; // r14d
  unsigned int v420; // r11d
  unsigned __int64 v421; // r15
  unsigned __int64 v422; // rbx
  _DWORD *v423; // r10
  _QWORD *v424; // rdx
  unsigned __int64 v425; // r12
  char *v426; // r9
  _DWORD *v427; // rsi
  _QWORD *v428; // r8
  unsigned __int64 v429; // rax
  unsigned __int64 v430; // rbx
  unsigned int v431; // eax
  __int64 v432; // rdx
  __int64 v433; // r9
  char *v434; // r15
  char *v435; // r8
  __int64 v436; // r14
  __int64 v437; // r11
  _DWORD *v438; // rcx
  unsigned int *v439; // r11
  _DWORD *v440; // rcx
  unsigned int *v441; // rax
  unsigned int *v442; // rax
  unsigned int v443; // esi
  __int64 v444; // rax
  __int64 v445; // r8
  unsigned int v446; // r13d
  __int64 v447; // rbx
  unsigned __int64 v448; // r14
  char v449; // cl
  __int64 v450; // r9
  unsigned int v451; // ecx
  unsigned int v452; // r8d
  unsigned int v453; // edx
  int v454; // ecx
  int v455; // r10d
  int v456; // eax
  int v457; // ecx
  int v458; // eax
  unsigned int v459; // r8d
  int v460; // eax
  _DWORD *v461; // rcx
  unsigned int v462; // edx
  unsigned int v463; // r14d
  unsigned int v464; // r12d
  unsigned int *v465; // r15
  unsigned int v466; // eax
  __int64 v467; // r9
  int v468; // eax
  __int64 v469; // rcx
  __int64 v470; // r9
  unsigned int v471; // r11d
  _DWORD *v472; // rsi
  _QWORD *v473; // rdx
  _QWORD *v474; // r8
  unsigned __int64 v475; // rax
  __int64 v476; // r9
  int v477; // eax
  int v478; // edx
  int v479; // r9d
  int v480; // eax
  __int64 v481; // rdx
  __int64 v482; // rcx
  _DWORD *v483; // r11
  __int64 v484; // r8
  __int64 v485; // rsi
  char *v486; // rdx
  __int64 v487; // rax
  __int64 v488; // rcx
  __int64 v489; // r11
  __int64 v490; // rcx
  int v491; // eax
  _DWORD *v492; // rcx
  unsigned int *v493; // r9
  unsigned int v494; // r14d
  unsigned int v495; // r11d
  unsigned __int64 v496; // r15
  unsigned __int64 v497; // rbx
  _DWORD *v498; // r10
  _QWORD *v499; // rdx
  unsigned __int64 v500; // r12
  char *v501; // r9
  _DWORD *v502; // rsi
  _QWORD *v503; // r8
  unsigned __int64 v504; // rax
  unsigned __int64 v505; // rbx
  unsigned int v506; // eax
  __int64 v507; // rdx
  __int64 v508; // r9
  char *v509; // r15
  char *v510; // r8
  __int64 v511; // r14
  __int64 v512; // r11
  _DWORD *v513; // rcx
  unsigned int *v514; // r11
  _DWORD *v515; // rcx
  unsigned int v516; // esi
  __int64 v517; // rax
  __int64 v518; // r8
  unsigned int v519; // r13d
  __int64 v520; // rbx
  unsigned __int64 v521; // r10
  char v522; // cl
  __int64 v523; // r9
  unsigned int v524; // ecx
  unsigned int v525; // r8d
  unsigned int v526; // edx
  int v527; // ecx
  int v528; // r12d
  int v529; // eax
  int v530; // ecx
  int v531; // eax
  unsigned int v532; // r8d
  int v533; // eax
  _DWORD *v534; // rcx
  unsigned int v535; // edx
  unsigned int v536; // r14d
  unsigned int v537; // r10d
  unsigned int *v538; // r15
  unsigned int v539; // eax
  __int64 v540; // r9
  int v541; // eax
  __int64 v542; // rcx
  __int64 v543; // r9
  unsigned int v544; // r11d
  _DWORD *v545; // rsi
  _QWORD *v546; // rdx
  _QWORD *v547; // r8
  unsigned __int64 v548; // rax
  __int64 v549; // r9
  int v550; // eax
  int v551; // edx
  int v552; // r9d
  int v553; // eax
  __int64 v554; // rdx
  __int64 v555; // rcx
  _DWORD *v556; // r11
  unsigned __int64 v557; // r8
  __int64 v558; // rsi
  char *v559; // rdx
  unsigned __int64 v560; // rcx
  __int64 v561; // r11
  __int64 v562; // rcx
  int v563; // eax
  _DWORD *v564; // rcx
  unsigned int *v565; // r9
  unsigned int v566; // r14d
  unsigned int v567; // r11d
  unsigned __int64 v568; // r15
  unsigned __int64 v569; // rbx
  _DWORD *v570; // r10
  _QWORD *v571; // rdx
  unsigned __int64 v572; // r12
  char *v573; // r9
  _DWORD *v574; // rsi
  _QWORD *v575; // r8
  unsigned __int64 v576; // rax
  unsigned __int64 v577; // rbx
  unsigned int v578; // eax
  __int64 v579; // rdx
  __int64 v580; // r9
  char *v581; // r15
  char *v582; // r8
  __int64 v583; // r14
  __int64 v584; // r11
  _DWORD *v585; // rcx
  unsigned int *v586; // r11
  _DWORD *v587; // rcx
  unsigned int v588; // eax
  unsigned int v589; // ebx
  __int64 v590; // rax
  __int64 v591; // r8
  unsigned int v592; // r13d
  unsigned int *v593; // rsi
  __int64 v594; // r10
  char v595; // cl
  unsigned int v596; // r8d
  __int64 v597; // r9
  unsigned int v598; // r9d
  unsigned int v599; // ecx
  unsigned int v600; // edx
  int v601; // r12d
  int v602; // eax
  int v603; // ecx
  int v604; // eax
  _DWORD *v605; // rcx
  unsigned int v606; // edx
  unsigned int v607; // r14d
  unsigned int v608; // r10d
  unsigned int *v609; // r15
  unsigned int v610; // eax
  unsigned int v611; // r8d
  int v612; // eax
  __int64 v613; // rcx
  __int64 v614; // r10
  unsigned int v615; // r11d
  _DWORD *v616; // rbx
  int v617; // r8d
  _QWORD *v618; // rdx
  __int64 v619; // r9
  _QWORD *v620; // r8
  unsigned __int64 v621; // rax
  int v622; // eax
  int v623; // eax
  int v624; // edx
  int v625; // r9d
  __int64 v626; // r8
  int v627; // eax
  __int64 v628; // rdx
  __int64 v629; // rcx
  __int64 v630; // r11
  int v631; // r8d
  unsigned __int64 v632; // r8
  __int64 v633; // rsi
  __int64 v634; // rdx
  unsigned __int64 v635; // rcx
  __int64 v636; // rbx
  __int64 v637; // r11
  unsigned __int64 v638; // r8
  __int64 v639; // rax
  _DWORD *v640; // rcx
  unsigned int *v641; // r15
  unsigned int FirstIndexHash3; // eax
  unsigned int v643; // r14d
  unsigned int v644; // r8d
  unsigned int v645; // ebx
  unsigned __int64 v646; // rax
  int v647; // r11d
  char *v648; // r9
  _DWORD *v649; // rcx
  int v650; // edx
  int v651; // r15d
  _DWORD *v652; // r10
  unsigned __int64 v653; // rbx
  _DWORD *v654; // r11
  char *v655; // r12
  unsigned int *v656; // rsi
  unsigned __int64 v657; // rax
  _QWORD *v658; // rdx
  char *v659; // r8
  char *v660; // r9
  unsigned __int64 v661; // rbx
  unsigned int v662; // eax
  __int64 v663; // rdx
  __int64 v664; // r9
  char *v665; // r15
  char *v666; // r8
  __int64 v667; // r14
  __int64 v668; // r11
  _DWORD *v669; // rcx
  _DWORD *v670; // rcx
  _DWORD *v671; // rax
  _DWORD *v672; // rsi
  unsigned int v673; // ecx
  unsigned int v674; // r13d
  unsigned int *v675; // r10
  unsigned int v676; // r14d
  __int64 v677; // rax
  unsigned int *v678; // r10
  int v679; // r11d
  unsigned int v680; // edx
  __int64 v681; // xmm1_8
  int v682; // r12d
  unsigned int v683; // esi
  __int64 v684; // r13
  unsigned int v685; // eax
  __int64 v686; // r10
  __int64 v687; // r9
  unsigned int v688; // ecx
  signed int v689; // r8d
  __int64 v690; // rcx
  unsigned int v691; // r8d
  int v692; // r10d
  unsigned int v693; // ecx
  __int64 v694; // rcx
  __int64 v695; // rdx
  unsigned int v696; // r9d
  unsigned int v697; // ecx
  __int64 v698; // rdx
  unsigned int v699; // ecx
  _DWORD *v700; // rdx
  __int64 v701; // rdx
  __int128 v702; // xmm0
  unsigned int v703; // eax
  int v704; // eax
  unsigned int v705; // edi
  unsigned int v706; // r10d
  __int64 v707; // rax
  int v708; // eax
  unsigned int v709; // r12d
  unsigned int v710; // esi
  __int64 v711; // rcx
  int v712; // eax
  _DWORD *v713; // r8
  __int128 v714; // xmm0
  __int64 v715; // xmm1_8
  __int64 v716; // rdx
  __int64 v717; // r8
  unsigned int v718; // ecx
  unsigned int v719; // eax
  unsigned __int64 v720; // r8
  __int64 v721; // rcx
  int v722; // ebx
  __int64 v723; // rdx
  unsigned int v724; // edi
  unsigned int v725; // r15d
  unsigned int v726; // ecx
  __int64 v727; // rcx
  int v728; // r8d
  unsigned int v729; // r14d
  unsigned __int64 v730; // rdx
  unsigned __int64 v731; // rbx
  __int64 v732; // rcx
  unsigned __int64 v733; // rdx
  __int64 v734; // rcx
  unsigned __int64 v735; // rax
  __int64 v736; // rcx
  unsigned __int64 v737; // rcx
  __int64 v738; // rcx
  unsigned __int64 v739; // rax
  __int64 v740; // rcx
  __int64 v741; // rcx
  __int64 v742; // rcx
  unsigned __int64 v744; // [rsp+30h] [rbp-D0h]
  unsigned int v745; // [rsp+38h] [rbp-C8h] BYREF
  int v746; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned int v747; // [rsp+40h] [rbp-C0h]
  unsigned int v748; // [rsp+44h] [rbp-BCh]
  unsigned __int64 v749; // [rsp+48h] [rbp-B8h]
  unsigned int *v750; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v751; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v752; // [rsp+60h] [rbp-A0h]
  unsigned int *v753; // [rsp+68h] [rbp-98h]
  unsigned __int64 v754; // [rsp+70h] [rbp-90h]
  BOOL v755; // [rsp+78h] [rbp-88h]
  unsigned int v756; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v757; // [rsp+80h] [rbp-80h]
  _DWORD *v758; // [rsp+88h] [rbp-78h]
  unsigned __int64 v759; // [rsp+90h] [rbp-70h]
  unsigned int v760; // [rsp+98h] [rbp-68h]
  unsigned int v761; // [rsp+9Ch] [rbp-64h] BYREF
  unsigned int *v762; // [rsp+A0h] [rbp-60h]
  _DWORD *v763; // [rsp+A8h] [rbp-58h]
  unsigned int v764; // [rsp+B0h] [rbp-50h] BYREF
  int v765; // [rsp+B4h] [rbp-4Ch] BYREF
  int v766; // [rsp+B8h] [rbp-48h]
  __int64 v767; // [rsp+C0h] [rbp-40h]
  _DWORD *v768; // [rsp+C8h] [rbp-38h]
  unsigned int v769; // [rsp+D0h] [rbp-30h]
  int v770; // [rsp+D4h] [rbp-2Ch] BYREF
  unsigned int v771; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int *v772; // [rsp+E0h] [rbp-20h]
  _DWORD *v773; // [rsp+E8h] [rbp-18h]
  _DWORD *v774; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v775; // [rsp+F8h] [rbp-8h]
  int v776; // [rsp+100h] [rbp+0h]
  unsigned __int64 v777; // [rsp+108h] [rbp+8h]
  __int64 v778; // [rsp+110h] [rbp+10h]
  unsigned __int64 v779; // [rsp+118h] [rbp+18h]
  int v780; // [rsp+120h] [rbp+20h]
  unsigned int v781; // [rsp+124h] [rbp+24h]
  int v782; // [rsp+128h] [rbp+28h] BYREF
  __int64 v783; // [rsp+130h] [rbp+30h]
  unsigned __int64 v784; // [rsp+138h] [rbp+38h]
  __int128 v785; // [rsp+140h] [rbp+40h]
  __int64 v786; // [rsp+150h] [rbp+50h]
  int v787; // [rsp+158h] [rbp+58h]
  __int128 v788; // [rsp+160h] [rbp+60h] BYREF
  __int64 v789; // [rsp+170h] [rbp+70h]
  int v790; // [rsp+178h] [rbp+78h]
  __int128 v791; // [rsp+180h] [rbp+80h] BYREF
  __int64 v792; // [rsp+190h] [rbp+90h]
  int v793; // [rsp+198h] [rbp+98h]
  __int128 v794; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v795; // [rsp+1B0h] [rbp+B0h]
  int v796; // [rsp+1B8h] [rbp+B8h]
  char v797[16]; // [rsp+1C0h] [rbp+C0h] BYREF
  char v798[24]; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int64 v802; // [rsp+248h] [rbp+148h]
  unsigned int v803; // [rsp+250h] [rbp+150h]
  unsigned int v804; // [rsp+250h] [rbp+150h]
  unsigned int *v805; // [rsp+250h] [rbp+150h]
  unsigned int v806; // [rsp+250h] [rbp+150h]

  v802 = a4;
  v5 = a1;
  v6 = a1 + 72;
  v7 = 4095;
  v8 = a4;
  v778 = v6;
  v9 = *(_DWORD *)(v5 + 204);
  v10 = a4 + a5;
  v11 = a4 + a5 - 8;
  v12 = *(_QWORD *)(v5 + 8) + *(unsigned int *)(v5 + 24);
  v744 = a4 + a5;
  v784 = v11;
  if ( v9 < 0xFFF )
    v7 = v9;
  v13 = *(_DWORD *)(v5 + 200) == 3;
  v781 = v7;
  v776 = !v13 + 3;
  v782 = *(_DWORD *)(v5 + 36);
  v773 = *(_DWORD **)(v6 + 40);
  v768 = *(_DWORD **)(v6 + 32);
  ZSTD_rescaleFreqs(v6, a4, a5, 2);
  v14 = v8 + (v8 == v12);
  v759 = v14;
  if ( v14 < v11 )
  {
    v15 = v786;
    v780 = v787;
    while ( 1 )
    {
      v16 = *(unsigned int *)(v5 + 36);
      v17 = *(_QWORD *)(v5 + 8);
      v18 = *(_DWORD *)(v5 + 200);
      v19 = v14 == v8;
      v765 = v14 - v8;
      v755 = v19;
      if ( v14 < v17 + v16 )
        goto LABEL_864;
      v20 = v14 - v17;
      if ( (unsigned int)v16 < (int)v14 - (int)v17 )
      {
        do
          LODWORD(v16) = ZSTD_insertBt1(v5, (int)v17 + (int)v16, v10, v18, 1) + v16;
        while ( (unsigned int)v16 < v20 );
        v14 = v759;
      }
      v21 = 4095;
      v22 = *(_QWORD *)(a1 + 48);
      *(_DWORD *)(a1 + 36) = v20;
      v23 = *(unsigned int *)(a1 + 192);
      if ( v18 == 3 )
        break;
      v24 = *(_DWORD **)(a1 + 8);
      v763 = v24;
      if ( v18 == 5 )
      {
        if ( *(_DWORD *)(a1 + 204) < 0xFFFu )
          v21 = *(_DWORD *)(a1 + 204);
        v747 = v14 - (_DWORD)v24;
        v164 = ZSTD_hash5Ptr(v14, v23, v22);
        v167 = *(_DWORD *)(v166 + 4 * v164);
        v168 = *(_QWORD *)(a1 + 64);
        v169 = *(_DWORD *)(a1 + 188) - 1;
        v772 = (unsigned int *)(v166 + 4 * v164);
        v750 = *(unsigned int **)(a1 + 16);
        LODWORD(v166) = 1 << v169;
        v170 = 0;
        v171 = v166 - 1;
        v751 = (unsigned __int64)v172;
        v753 = v172;
        v173 = (_DWORD *)*(unsigned int *)(a1 + 24);
        v767 = v168;
        v757 = v171;
        v766 = (int)v173;
        v758 = v173;
        v762 = (_DWORD *)((char *)v173 + v174);
        if ( v171 < v165 )
          v170 = v165 - v171;
        v760 = v170;
        v175 = 1 << *(_DWORD *)(a1 + 184);
        v176 = v165 - v175;
        v177 = 1;
        if ( v165 - *(_DWORD *)(a1 + 28) <= v175 )
          v176 = *(_DWORD *)(a1 + 28);
        if ( *(_DWORD *)(a1 + 32) )
          v176 = *(_DWORD *)(a1 + 28);
        v178 = *(_DWORD *)(a1 + 196);
        if ( v176 )
          v177 = v176;
        v769 = v177;
        v179 = v19 + 3;
        v803 = 0;
        v752 = v168 + 8LL * (v165 & v171);
        v754 = v752 + 4;
        v746 = v165 + 9;
        v180 = 1 << v178;
        v181 = a3;
        v745 = v180;
        v779 = (unsigned int)(v776 - 1);
        v182 = v165 - (_DWORD)v173;
        v749 = v779;
        v183 = v755;
        v184 = (unsigned int *)&a3[v755];
        while ( 1 )
        {
          if ( v183 == 3 )
            v185 = *v181 - 1;
          else
            v185 = *v184;
          v186 = v165 - v185;
          v187 = 0;
          if ( v185 - 1 >= v182 )
          {
            if ( v185 - 1 < v747 - v176 && (unsigned int)((_DWORD)v173 - v186 - 1) >= 3 )
            {
              MINMATCH = ZSTD_readMINMATCH(v759, 4, 0, v186);
              if ( MINMATCH == *v202 )
              {
                v203 = ZSTD_count_2segments(v201 + 4, (int)v202 + 4, v744, (int)v758 + (int)v750, (__int64)v762);
                LODWORD(v173) = v766;
                v187 = v203 + 4;
              }
            }
            v165 = v747;
            goto LABEL_226;
          }
          v188 = ZSTD_readMINMATCH(v759, 4, 0, -(__int64)v185);
          if ( v188 == *(_DWORD *)(v190 + v189) )
          {
            v191 = (_QWORD *)(v189 + 4);
            v192 = v189 + 4;
            v193 = v744;
            v194 = (_QWORD *)(v190 + v192);
            v195 = v191;
            v196 = v744 - 7;
            if ( (unsigned __int64)v191 >= v744 - 7 )
              goto LABEL_211;
            if ( *v191 == *v194 )
            {
              ++v191;
              ++v194;
              if ( (unsigned __int64)v191 < v196 )
              {
                while ( *v191 == *v194 )
                {
                  ++v191;
                  ++v194;
                  if ( (unsigned __int64)v191 >= v196 )
                    goto LABEL_210;
                }
                v197 = ZSTD_NbCommonBytes(*v191 ^ *v194, v191, v194, v195);
                v187 = v198 - v199 + v197 + 4;
                goto LABEL_226;
              }
LABEL_210:
              v193 = v744;
LABEL_211:
              if ( (unsigned __int64)v191 < v193 - 3 && *(_DWORD *)v194 == *(_DWORD *)v191 )
              {
                v191 = (_QWORD *)((char *)v191 + 4);
                v194 = (_QWORD *)((char *)v194 + 4);
              }
              if ( (unsigned __int64)v191 < v193 - 1 && *(_WORD *)v194 == *(_WORD *)v191 )
              {
                v191 = (_QWORD *)((char *)v191 + 2);
                v194 = (_QWORD *)((char *)v194 + 2);
              }
              if ( (unsigned __int64)v191 < v193 && *(_BYTE *)v194 == *(_BYTE *)v191 )
                LODWORD(v191) = (_DWORD)v191 + 1;
              v187 = (_DWORD)v191 - (_DWORD)v195 + 4;
              goto LABEL_226;
            }
            v187 = ZSTD_NbCommonBytes(*v191 ^ *v194, v191, v194, v191) + 4;
          }
LABEL_226:
          if ( v187 <= v749 )
          {
            v206 = v744;
          }
          else
          {
            v204 = &v768[2 * v803];
            *v204 = v183 - v755;
            v749 = v187;
            v205 = v759 + v187;
            ++v803;
            v206 = v744;
            v204[1] = v187;
            if ( v187 > v21 || v205 == v744 )
              goto LABEL_187;
          }
          v181 = a3;
          ++v183;
          ++v184;
          if ( v183 >= v179 )
          {
            *v772 = v165;
            v207 = v745;
            if ( !v745 )
              goto LABEL_185;
            v208 = v751;
            v209 = v759;
            v210 = (unsigned int *)v751;
            while ( 2 )
            {
              v745 = --v207;
              if ( v167 < v769 )
                goto LABEL_185;
              v211 = (unsigned __int64)v210;
              if ( v208 < (unsigned __int64)v210 )
                v211 = v208;
              v212 = (unsigned int *)(v767 + 8LL * (v167 & v757));
              if ( v211 + v167 < (unsigned __int64)v758 )
              {
                v223 = v211 + v209;
                v214 = (char *)v750 + v167;
                v224 = (char *)v206;
                if ( (unsigned __int64)v758 + v223 - (v167 + v211) < v206 )
                  v224 = (char *)v758 + v223 - (v167 + v211);
                v225 = ZSTD_count(v223, (char *)v750 + v167 + v211, v224);
                v227 = (_DWORD *)(v225 + v226);
                v228 = (unsigned __int64)v758;
                if ( v227 == (unsigned int *)((char *)v750 + (_QWORD)v758) )
                  v225 += ZSTD_count(v225 + v223, v762, v744);
                v207 = v745;
                v219 = v225 + v211;
                v210 = v753;
                v209 = v759;
                v91 = v219 + v167 < v228;
                v208 = v751;
                if ( !v91 )
                  v214 = (char *)v763 + v167;
                v216 = v744;
                goto LABEL_261;
              }
              v213 = (_QWORD *)(v211 + v209);
              v214 = (char *)v763 + v167;
              v215 = v211 + v209;
              v216 = v744;
              v217 = &v214[v211];
              v218 = v744 - 7;
              if ( v211 + v209 < v744 - 7 )
              {
                if ( *v213 != *(_QWORD *)v217 )
                {
                  v219 = (unsigned int)ZSTD_NbCommonBytes(*v213 ^ *(_QWORD *)v217, v213, v217, v215) + v211;
LABEL_261:
                  if ( v219 > v749 )
                  {
                    if ( v219 > v746 - v167 )
                      v746 = v167 + v219;
                    v229 = v768;
                    v230 = v747 - v167 + 2;
                    v768[2 * v803 + 1] = v219;
                    v229[2 * v803] = v230;
                    v749 = v219;
                    ++v803;
                    if ( v219 > 0x1000 || v219 + v209 == v216 )
                      goto LABEL_185;
                  }
                  if ( (unsigned __int8)v214[v219] >= *(_BYTE *)(v219 + v209) )
                  {
                    v210 = (unsigned int *)v219;
                    v753 = (unsigned int *)v219;
                    *(_DWORD *)v754 = v167;
                    if ( v167 <= v760 )
                    {
                      v95 = &v756;
LABEL_184:
                      v754 = (unsigned __int64)v95;
                      goto LABEL_185;
                    }
                    v167 = *v212;
                    v754 = (unsigned __int64)v212;
                  }
                  else
                  {
                    v208 = v219;
                    v751 = v219;
                    *(_DWORD *)v752 = v167;
                    if ( v167 <= v760 )
                    {
                      v94 = &v756;
                      goto LABEL_186;
                    }
                    v167 = v212[1];
                    v752 = (unsigned __int64)(v212 + 1);
                  }
                  if ( !v207 )
                    goto LABEL_185;
                  v206 = v744;
                  continue;
                }
                ++v213;
                v217 += 8;
                if ( (unsigned __int64)v213 < v218 )
                {
                  while ( *v213 == *(_QWORD *)v217 )
                  {
                    ++v213;
                    v217 += 8;
                    if ( (unsigned __int64)v213 >= v218 )
                      goto LABEL_243;
                  }
                  v220 = ZSTD_NbCommonBytes(*v213 ^ *(_QWORD *)v217, v213, v217, v215);
                  v219 = v221 - v222 + v220 + v211;
                  goto LABEL_261;
                }
              }
              break;
            }
LABEL_243:
            if ( (unsigned __int64)v213 < v744 - 3 && *(_DWORD *)v217 == *(_DWORD *)v213 )
            {
              v213 = (_QWORD *)((char *)v213 + 4);
              v217 += 4;
            }
            if ( (unsigned __int64)v213 < v744 - 1 && *(_WORD *)v217 == *(_WORD *)v213 )
            {
              v213 = (_QWORD *)((char *)v213 + 2);
              v217 += 2;
            }
            if ( (unsigned __int64)v213 < v744 && *v217 == *(_BYTE *)v213 )
              v213 = (_QWORD *)((char *)v213 + 1);
            v219 = (unsigned __int64)v213 - v209;
            goto LABEL_261;
          }
        }
      }
      v25 = *(_DWORD *)(a1 + 204);
      if ( (unsigned int)(v18 - 6) > 1 )
      {
        if ( v25 < 0xFFF )
          v21 = *(_DWORD *)(a1 + 204);
        v747 = v14 - (_DWORD)v24;
        v96 = ZSTD_hash4Ptr(v14, v23, v22);
        v99 = *(_DWORD *)(v98 + 4 * v96);
        v100 = *(_QWORD *)(a1 + 64);
        v101 = *(_DWORD *)(a1 + 188) - 1;
        v772 = (unsigned int *)(v98 + 4 * v96);
        v750 = *(unsigned int **)(a1 + 16);
        LODWORD(v98) = 1 << v101;
        v102 = 0;
        v103 = v98 - 1;
        v751 = (unsigned __int64)v104;
        v753 = v104;
        v105 = (_DWORD *)*(unsigned int *)(a1 + 24);
        v767 = v100;
        v757 = v103;
        v766 = (int)v105;
        v758 = v105;
        v762 = (_DWORD *)((char *)v105 + v106);
        if ( v103 < v97 )
          v102 = v97 - v103;
        v760 = v102;
        v107 = 1 << *(_DWORD *)(a1 + 184);
        v108 = v97 - v107;
        v109 = 1;
        if ( v97 - *(_DWORD *)(a1 + 28) <= v107 )
          v108 = *(_DWORD *)(a1 + 28);
        if ( *(_DWORD *)(a1 + 32) )
          v108 = *(_DWORD *)(a1 + 28);
        v110 = *(_DWORD *)(a1 + 196);
        if ( v108 )
          v109 = v108;
        v769 = v109;
        v111 = v19 + 3;
        v803 = 0;
        v752 = v100 + 8LL * (v97 & v103);
        v754 = v752 + 4;
        v746 = v97 + 9;
        v112 = 1 << v110;
        v113 = a3;
        v745 = v112;
        v779 = (unsigned int)(v776 - 1);
        v114 = v97 - (_DWORD)v105;
        v749 = v779;
        v115 = v755;
        v116 = (unsigned int *)&a3[v755];
        while ( 1 )
        {
          if ( v115 == 3 )
            v117 = *v113 - 1;
          else
            v117 = *v116;
          v118 = v97 - v117;
          v119 = 0;
          if ( v117 - 1 >= v114 )
          {
            if ( v117 - 1 < v747 - v108 && (unsigned int)((_DWORD)v105 - v118 - 1) >= 3 )
            {
              v132 = ZSTD_readMINMATCH(v759, 4, 0, v118);
              if ( v132 == *v134 )
              {
                v135 = ZSTD_count_2segments(v133 + 4, (int)v134 + 4, v744, (int)v758 + (int)v750, (__int64)v762);
                LODWORD(v105) = v766;
                v119 = v135 + 4;
              }
            }
            v97 = v747;
            goto LABEL_136;
          }
          v120 = ZSTD_readMINMATCH(v759, 4, 0, -(__int64)v117);
          if ( v120 == *(_DWORD *)(v122 + v121) )
          {
            v123 = (_QWORD *)(v121 + 4);
            v124 = v121 + 4;
            v125 = v744;
            v126 = (_QWORD *)(v122 + v124);
            v127 = v123;
            v128 = v744 - 7;
            if ( (unsigned __int64)v123 >= v744 - 7 )
              goto LABEL_121;
            if ( *v126 == *v123 )
            {
              ++v123;
              ++v126;
              if ( (unsigned __int64)v123 < v128 )
              {
                while ( *v126 == *v123 )
                {
                  ++v123;
                  ++v126;
                  if ( (unsigned __int64)v123 >= v128 )
                    goto LABEL_120;
                }
                v129 = ZSTD_NbCommonBytes(*v126 ^ *v123, v123, v126, v127);
                v119 = v130 - v131 + v129 + 4;
                goto LABEL_136;
              }
LABEL_120:
              v125 = v744;
LABEL_121:
              if ( (unsigned __int64)v123 < v125 - 3 && *(_DWORD *)v126 == *(_DWORD *)v123 )
              {
                v123 = (_QWORD *)((char *)v123 + 4);
                v126 = (_QWORD *)((char *)v126 + 4);
              }
              if ( (unsigned __int64)v123 < v125 - 1 && *(_WORD *)v126 == *(_WORD *)v123 )
              {
                v123 = (_QWORD *)((char *)v123 + 2);
                v126 = (_QWORD *)((char *)v126 + 2);
              }
              if ( (unsigned __int64)v123 < v125 && *(_BYTE *)v126 == *(_BYTE *)v123 )
                LODWORD(v123) = (_DWORD)v123 + 1;
              v119 = (_DWORD)v123 - (_DWORD)v127 + 4;
              goto LABEL_136;
            }
            v119 = ZSTD_NbCommonBytes(*v126 ^ *v123, v123, v126, v123) + 4;
          }
LABEL_136:
          if ( v119 <= v749 )
          {
            v138 = v744;
          }
          else
          {
            v136 = &v768[2 * v803];
            *v136 = v115 - v755;
            v749 = v119;
            v137 = v759 + v119;
            ++v803;
            v138 = v744;
            v136[1] = v119;
            if ( v119 > v21 || v137 == v744 )
              goto LABEL_187;
          }
          v113 = a3;
          ++v115;
          ++v116;
          if ( v115 >= v111 )
          {
            *v772 = v97;
            v139 = v745;
            if ( !v745 )
              goto LABEL_185;
            v140 = v751;
            v141 = v759;
            v142 = (unsigned int *)v751;
            while ( 2 )
            {
              v745 = --v139;
              if ( v99 < v769 )
                goto LABEL_185;
              v143 = (unsigned __int64)v142;
              if ( v140 < (unsigned __int64)v142 )
                v143 = v140;
              v144 = (unsigned int *)(v767 + 8LL * (v99 & v757));
              if ( v99 + v143 < (unsigned __int64)v758 )
              {
                v155 = v143 + v141;
                v156 = (char *)v138;
                v146 = (char *)v750 + v99;
                if ( (unsigned __int64)v758 + v155 - v143 - v99 < v138 )
                  v156 = (char *)v758 + v155 - (v99 + v143);
                v157 = ZSTD_count(v155, (char *)v750 + v99 + v143, v156);
                v159 = (_DWORD *)(v157 + v158);
                v160 = (unsigned __int64)v758;
                if ( v159 == (unsigned int *)((char *)v750 + (_QWORD)v758) )
                  v157 += ZSTD_count(v157 + v155, v762, v744);
                v139 = v745;
                v151 = v157 + v143;
                v142 = v753;
                v141 = v759;
                v91 = v99 + v151 < v160;
                v140 = v751;
                if ( !v91 )
                  v146 = (char *)v763 + v99;
                v148 = v744;
                goto LABEL_171;
              }
              v145 = (_QWORD *)(v143 + v141);
              v146 = (char *)v763 + v99;
              v147 = v143 + v141;
              v148 = v744;
              v149 = &v146[v143];
              v150 = v744 - 7;
              if ( v143 + v141 < v744 - 7 )
              {
                if ( *(_QWORD *)v149 != *v145 )
                {
                  v151 = (unsigned int)ZSTD_NbCommonBytes(*(_QWORD *)v149 ^ *v145, v145, v149, v147) + v143;
LABEL_171:
                  if ( v151 > v749 )
                  {
                    if ( v151 > v746 - v99 )
                      v746 = v151 + v99;
                    v161 = v768;
                    v162 = v747 - v99 + 2;
                    v768[2 * v803 + 1] = v151;
                    v161[2 * v803] = v162;
                    v749 = v151;
                    ++v803;
                    if ( v151 > 0x1000 || v151 + v141 == v148 )
                      goto LABEL_185;
                  }
                  if ( (unsigned __int8)v146[v151] >= *(_BYTE *)(v151 + v141) )
                  {
                    v142 = (unsigned int *)v151;
                    v753 = (unsigned int *)v151;
                    *(_DWORD *)v754 = v99;
                    if ( v99 <= v760 )
                    {
                      v95 = &v764;
                      goto LABEL_184;
                    }
                    v99 = *v144;
                    v754 = (unsigned __int64)v144;
                  }
                  else
                  {
                    v140 = v151;
                    v751 = v151;
                    *(_DWORD *)v752 = v99;
                    if ( v99 <= v760 )
                    {
                      v94 = &v764;
                      goto LABEL_186;
                    }
                    v99 = v144[1];
                    v752 = (unsigned __int64)(v144 + 1);
                  }
                  if ( !v139 )
                    goto LABEL_185;
                  v138 = v744;
                  continue;
                }
                ++v145;
                v149 += 8;
                if ( (unsigned __int64)v145 < v150 )
                {
                  while ( *(_QWORD *)v149 == *v145 )
                  {
                    ++v145;
                    v149 += 8;
                    if ( (unsigned __int64)v145 >= v150 )
                      goto LABEL_153;
                  }
                  v152 = ZSTD_NbCommonBytes(*(_QWORD *)v149 ^ *v145, v145, v149, v147);
                  v151 = v153 - v154 + v152 + v143;
                  goto LABEL_171;
                }
              }
              break;
            }
LABEL_153:
            if ( (unsigned __int64)v145 < v744 - 3 && *(_DWORD *)v149 == *(_DWORD *)v145 )
            {
              v145 = (_QWORD *)((char *)v145 + 4);
              v149 += 4;
            }
            if ( (unsigned __int64)v145 < v744 - 1 && *(_WORD *)v149 == *(_WORD *)v145 )
            {
              v145 = (_QWORD *)((char *)v145 + 2);
              v149 += 2;
            }
            if ( (unsigned __int64)v145 < v744 && *v149 == *(_BYTE *)v145 )
              v145 = (_QWORD *)((char *)v145 + 1);
            v151 = (unsigned __int64)v145 - v141;
            goto LABEL_171;
          }
        }
      }
      if ( v25 < 0xFFF )
        v21 = *(_DWORD *)(a1 + 204);
      v747 = v14 - (_DWORD)v24;
      v26 = ZSTD_hash6Ptr(v14, v23, v22);
      v29 = *(_DWORD *)(v28 + 4 * v26);
      v30 = *(_QWORD *)(a1 + 64);
      v31 = *(_DWORD *)(a1 + 188) - 1;
      v772 = (unsigned int *)(v28 + 4 * v26);
      v750 = *(unsigned int **)(a1 + 16);
      LODWORD(v28) = 1 << v31;
      v32 = 0;
      v33 = v28 - 1;
      v751 = (unsigned __int64)v34;
      v753 = v34;
      v35 = (_DWORD *)*(unsigned int *)(a1 + 24);
      v767 = v30;
      v757 = v33;
      v766 = (int)v35;
      v758 = v35;
      v762 = (_DWORD *)((char *)v35 + v36);
      if ( v33 < v27 )
        v32 = v27 - v33;
      v760 = v32;
      v37 = 1 << *(_DWORD *)(a1 + 184);
      v38 = v27 - v37;
      v39 = 1;
      if ( v27 - *(_DWORD *)(a1 + 28) <= v37 )
        v38 = *(_DWORD *)(a1 + 28);
      if ( *(_DWORD *)(a1 + 32) )
        v38 = *(_DWORD *)(a1 + 28);
      v40 = *(_DWORD *)(a1 + 196);
      if ( v38 )
        v39 = v38;
      v769 = v39;
      v41 = v19 + 3;
      v803 = 0;
      v752 = v30 + 8LL * (v27 & v33);
      v754 = v752 + 4;
      v746 = v27 + 9;
      v42 = 1 << v40;
      v43 = a3;
      v745 = v42;
      v779 = (unsigned int)(v776 - 1);
      v44 = v27 - (_DWORD)v35;
      v749 = v779;
      v45 = v755;
      v46 = (unsigned int *)&a3[v755];
      do
      {
        if ( v45 == 3 )
          v47 = *v43 - 1;
        else
          v47 = *v46;
        v48 = v27 - v47;
        v49 = 0;
        if ( v47 - 1 >= v44 )
        {
          if ( v47 - 1 < v747 - v38 && (unsigned int)((_DWORD)v35 - v48 - 1) >= 3 )
          {
            v62 = ZSTD_readMINMATCH(v759, 4, 0, v48);
            if ( v62 == *v64 )
            {
              v65 = ZSTD_count_2segments(v63 + 4, (int)v64 + 4, v744, (int)v758 + (int)v750, (__int64)v762);
              LODWORD(v35) = v766;
              v49 = v65 + 4;
            }
          }
          v27 = v747;
        }
        else
        {
          v50 = ZSTD_readMINMATCH(v759, 4, 0, -(__int64)v47);
          if ( v50 != *(_DWORD *)(v52 + v51) )
            goto LABEL_50;
          v53 = (_QWORD *)(v51 + 4);
          v54 = v51 + 4;
          v55 = v744;
          v56 = (_QWORD *)(v52 + v54);
          v57 = v53;
          v58 = v744 - 7;
          if ( (unsigned __int64)v53 >= v744 - 7 )
            goto LABEL_35;
          if ( *v56 != *v53 )
          {
            v49 = ZSTD_NbCommonBytes(*v56 ^ *v53, v53, v56, v53) + 4;
            goto LABEL_50;
          }
          ++v53;
          ++v56;
          if ( (unsigned __int64)v53 >= v58 )
          {
LABEL_34:
            v55 = v744;
LABEL_35:
            if ( (unsigned __int64)v53 < v55 - 3 && *(_DWORD *)v56 == *(_DWORD *)v53 )
            {
              v53 = (_QWORD *)((char *)v53 + 4);
              v56 = (_QWORD *)((char *)v56 + 4);
            }
            if ( (unsigned __int64)v53 < v55 - 1 && *(_WORD *)v56 == *(_WORD *)v53 )
            {
              v53 = (_QWORD *)((char *)v53 + 2);
              v56 = (_QWORD *)((char *)v56 + 2);
            }
            if ( (unsigned __int64)v53 < v55 && *(_BYTE *)v56 == *(_BYTE *)v53 )
              LODWORD(v53) = (_DWORD)v53 + 1;
            v49 = (_DWORD)v53 - (_DWORD)v57 + 4;
            goto LABEL_50;
          }
          while ( *v56 == *v53 )
          {
            ++v53;
            ++v56;
            if ( (unsigned __int64)v53 >= v58 )
              goto LABEL_34;
          }
          v59 = ZSTD_NbCommonBytes(*v56 ^ *v53, v53, v56, v57);
          v49 = v60 - v61 + v59 + 4;
        }
LABEL_50:
        if ( v49 <= v749 )
        {
          v68 = v744;
        }
        else
        {
          v66 = &v768[2 * v803];
          *v66 = v45 - v755;
          v749 = v49;
          v67 = v759 + v49;
          ++v803;
          v68 = v744;
          v66[1] = v49;
          if ( v49 > v21 || v67 == v744 )
            goto LABEL_187;
        }
        v43 = a3;
        ++v45;
        ++v46;
      }
      while ( v45 < v41 );
      *v772 = v27;
      v69 = v745;
      if ( v745 )
      {
        v70 = v751;
        v71 = v759;
        v72 = (unsigned int *)v751;
        while ( 1 )
        {
          v745 = --v69;
          if ( v29 < v769 )
            break;
          v73 = (unsigned __int64)v72;
          if ( v70 < (unsigned __int64)v72 )
            v73 = v70;
          v74 = (unsigned int *)(v767 + 8LL * (v29 & v757));
          if ( v73 + v29 < (unsigned __int64)v758 )
          {
            v85 = v73 + v71;
            v86 = (char *)v68;
            v76 = (char *)v750 + v29;
            if ( (unsigned __int64)v758 + v85 - v73 - v29 < v68 )
              v86 = (char *)v758 + v85 - v73 - v29;
            v87 = ZSTD_count(v85, (char *)v750 + v29 + v73, v86);
            v89 = (_DWORD *)(v87 + v88);
            v90 = (unsigned __int64)v758;
            if ( v89 == (unsigned int *)((char *)v750 + (_QWORD)v758) )
              v87 += ZSTD_count(v87 + v85, v762, v744);
            v69 = v745;
            v81 = v87 + v73;
            v72 = v753;
            v71 = v759;
            v91 = v81 + v29 < v90;
            v70 = v751;
            if ( !v91 )
              v76 = (char *)v763 + v29;
            v78 = v744;
          }
          else
          {
            v75 = (_QWORD *)(v73 + v71);
            v76 = (char *)v763 + v29;
            v77 = v73 + v71;
            v78 = v744;
            v79 = &v76[v73];
            v80 = v744 - 7;
            if ( v73 + v71 >= v744 - 7 )
              goto LABEL_67;
            if ( *(_QWORD *)v79 != *v75 )
            {
              v81 = (unsigned int)ZSTD_NbCommonBytes(*(_QWORD *)v79 ^ *v75, v75, v79, v77) + v73;
              goto LABEL_85;
            }
            ++v75;
            v79 += 8;
            if ( (unsigned __int64)v75 >= v80 )
            {
LABEL_67:
              if ( (unsigned __int64)v75 < v744 - 3 && *(_DWORD *)v79 == *(_DWORD *)v75 )
              {
                v75 = (_QWORD *)((char *)v75 + 4);
                v79 += 4;
              }
              if ( (unsigned __int64)v75 < v744 - 1 && *(_WORD *)v79 == *(_WORD *)v75 )
              {
                v75 = (_QWORD *)((char *)v75 + 2);
                v79 += 2;
              }
              if ( (unsigned __int64)v75 < v744 && *v79 == *(_BYTE *)v75 )
                v75 = (_QWORD *)((char *)v75 + 1);
              v81 = (unsigned __int64)v75 - v71;
            }
            else
            {
              while ( *(_QWORD *)v79 == *v75 )
              {
                ++v75;
                v79 += 8;
                if ( (unsigned __int64)v75 >= v80 )
                  goto LABEL_67;
              }
              v82 = ZSTD_NbCommonBytes(*(_QWORD *)v79 ^ *v75, v75, v79, v77);
              v81 = v83 - v84 + v82 + v73;
            }
          }
LABEL_85:
          if ( v81 > v749 )
          {
            if ( v81 > v746 - v29 )
              v746 = v81 + v29;
            v92 = v768;
            v93 = v747 - v29 + 2;
            v768[2 * v803 + 1] = v81;
            v92[2 * v803] = v93;
            v749 = v81;
            ++v803;
            if ( v81 > 0x1000 || v81 + v71 == v78 )
              break;
          }
          if ( (unsigned __int8)v76[v81] >= *(_BYTE *)(v81 + v71) )
          {
            v72 = (unsigned int *)v81;
            v753 = (unsigned int *)v81;
            *(_DWORD *)v754 = v29;
            if ( v29 <= v760 )
            {
              v95 = &v761;
              goto LABEL_184;
            }
            v29 = *v74;
            v754 = (unsigned __int64)v74;
          }
          else
          {
            v70 = v81;
            v751 = v81;
            *(_DWORD *)v752 = v29;
            if ( v29 <= v760 )
            {
              v94 = &v761;
              goto LABEL_186;
            }
            v29 = v74[1];
            v752 = (unsigned __int64)(v74 + 1);
          }
          if ( !v69 )
            break;
          v68 = v744;
        }
      }
LABEL_185:
      v94 = (unsigned int *)v752;
LABEL_186:
      *(_DWORD *)v754 = 0;
      *v94 = 0;
      *(_DWORD *)(a1 + 36) = v746 - 8;
LABEL_187:
      v163 = v803;
LABEL_376:
      if ( !v163 )
      {
        v14 = v759;
LABEL_864:
        v759 = ++v14;
        goto LABEL_865;
      }
      v309 = v773;
      v310 = v765;
      v311 = v778;
      v312 = v778;
      v773[4] = *a3;
      v309[5] = a3[1];
      v309[6] = a3[2];
      v309[2] = 0;
      v309[3] = v310;
      v313 = ZSTD_literalsContribution(v802, v310, v312, 2);
      v314 = v773;
      v315 = v768;
      *v773 = v313;
      if ( v315[2 * v163 - 1] > v781 )
      {
        *(_QWORD *)((char *)&v785 + 4) = *(_QWORD *)&v315[2 * v163 - 2];
        HIDWORD(v785) = v310;
LABEL_832:
        v706 = 0;
        v705 = 0;
        goto LABEL_833;
      }
      ZSTD_litLengthPrice(0, v311, 2);
      v316 = v779;
      v317 = v779 + 1;
      v318 = v773 + 7;
      do
      {
        *v318 = 0x40000000;
        v318 += 7;
        --v316;
      }
      while ( v316 );
      v319 = v163;
      v320 = v315;
      v752 = v163;
      v805 = v315;
      do
      {
        v321 = v320[1];
        updated = ZSTD_updateRep(v798, a3, *v320, v755);
        v325 = *(_QWORD *)updated;
        v326 = *(_DWORD *)(updated + 8);
        if ( v317 > v321 )
        {
          v340 = v773;
        }
        else
        {
          v327 = v778;
          do
          {
            _BitScanReverse((unsigned int *)&v328, v324 + 1);
            v13 = *(_DWORD *)(v327 + 80) == 1;
            v329 = v317 - 3;
            v748 = 0;
            if ( v13 )
            {
              LODWORD(v775) = 0;
              _BitScanReverse(&v330, v317 - 2);
              v331 = v323 + ((v317 - 2) << 8 >> v330) + (((_DWORD)v328 + v330 + 16) << 8);
            }
            else
            {
              v332 = *(_QWORD *)(v327 + 24);
              LODWORD(v774) = 0;
              v333 = *(_DWORD *)(v332 + 4 * v328) + 1;
              _BitScanReverse(&v334, v333);
              v335 = *(_DWORD *)(v327 + 76) + (((_DWORD)v328 - v334) << 8) - (v333 << 8 >> v334);
              if ( (unsigned int)v329 <= 0x7F )
              {
                _mm_lfence();
                v337 = *((unsigned __int8 *)&qword_1803EF770[8] + v329);
              }
              else
              {
                _BitScanReverse(&v336, v329);
                LODWORD(v767) = 0;
                v337 = v336 + 36;
              }
              LODWORD(v763) = 0;
              v338 = *(_DWORD *)(*(_QWORD *)(v327 + 16) + 4 * v337) + 1;
              _BitScanReverse(&v339, v338);
              v331 = v335
                   + v323
                   + *(_DWORD *)(v327 + 72)
                   + ((*((_DWORD *)&qword_1803EF640[10] + v337) - v339) << 8)
                   - (v338 << 8 >> v339)
                   + 51;
            }
            v340 = v773;
            v341 = 7LL * v317;
            v773[v341 + 2] = v317++;
            *(_QWORD *)&v340[v341 + 4] = v325;
            v340[v341 + 1] = v324;
            v340[v341 + 3] = v310;
            v340[v341] = v331;
            v340[v341 + 6] = v326;
          }
          while ( v317 <= v321 );
          v320 = v805;
          v319 = v752;
        }
        v320 += 2;
        --v319;
        v805 = v320;
        v752 = v319;
      }
      while ( v319 );
      v342 = v317 - 1;
      v343 = 1;
      v766 = v342;
      v747 = 1;
      if ( !v342 )
      {
LABEL_823:
        v700 = &v340[7 * v342];
        v702 = *(_OWORD *)v700;
        v780 = v700[6];
        v15 = *((_QWORD *)v700 + 2);
        v785 = v702;
        v793 = v780;
        v791 = v702;
        v792 = v15;
        *(double *)&v702 = ZSTD_totalLen(&v791);
        if ( v342 > v703 )
        {
          v796 = *(_DWORD *)(v701 + 24);
          v794 = v702;
          v795 = v15;
          ZSTD_totalLen(&v794);
          LODWORD(v311) = v778;
          v705 = v342 - v704;
          v706 = 0;
          goto LABEL_833;
        }
        LODWORD(v311) = v778;
        goto LABEL_832;
      }
      while ( 2 )
      {
        v344 = v343;
        v345 = (unsigned int *)(v343 + v759);
        v346 = &v340[7 * v343 - 7];
        v750 = v345;
        if ( v346[2] )
          v347 = 1;
        else
          v347 = v346[3] + 1;
        v348 = v778;
        v349 = *v346 - ZSTD_litLengthPrice(v347 - 1, v778, 2);
        v351 = ZSTD_rawLiteralsCost((char *)v345 - 1, (unsigned int)(v350 - 1), v348) + v349;
        v352 = ZSTD_litLengthPrice(v347, v348, 2);
        v340 = v773;
        v354 = v351 + v352;
        v355 = &v773[7 * v344];
        v356 = *v355;
        if ( v354 <= *v355 )
        {
          v357 = *((_QWORD *)v346 + 2);
          v356 = v354;
          *v355 = v354;
          v358 = v346[6];
          *((_QWORD *)v355 + 2) = v357;
          v355[6] = v358;
          *(_QWORD *)(v355 + 1) = 0;
          v355[3] = v347;
        }
        if ( (unsigned __int64)v345 > v784 )
          goto LABEL_822;
        if ( v747 == v342 )
          goto LABEL_823;
        v359 = v355[2];
        v755 = v359 != 0;
        if ( v359 )
          v760 = 0;
        else
          v760 = v355[3];
        v769 = v356 + ZSTD_litLengthPrice(0, v348, v353);
        v752 = (unsigned __int64)(v355 + 4);
        v360 = *(unsigned int *)(a1 + 36);
        v361 = *(_QWORD *)(a1 + 8);
        v362 = *(_DWORD *)(a1 + 200);
        if ( (unsigned __int64)v345 < v361 + v360 )
        {
LABEL_821:
          v340 = v773;
LABEL_822:
          v343 = v747 + 1;
          v747 = v343;
          if ( v343 > v342 )
            goto LABEL_823;
          continue;
        }
        break;
      }
      v363 = (_DWORD)v345 - v361;
      if ( (unsigned int)v360 < (int)v345 - (int)v361 )
      {
        do
          LODWORD(v360) = ZSTD_insertBt1(a1, (int)v361 + (int)v360, v744, v362, 1) + v360;
        while ( (unsigned int)v360 < v363 );
        v342 = v766;
        v345 = v750;
      }
      v364 = 4095;
      v365 = *(_QWORD *)(a1 + 8);
      v366 = *(_QWORD *)(a1 + 48);
      *(_DWORD *)(a1 + 36) = v363;
      v367 = *(unsigned int *)(a1 + 192);
      if ( v362 != 3 )
      {
        v767 = v365;
        if ( v362 != 5 )
        {
          v368 = *(_DWORD *)(a1 + 204);
          if ( (unsigned int)(v362 - 6) <= 1 )
          {
            if ( v368 < 0xFFF )
              v364 = *(_DWORD *)(a1 + 204);
            v369 = (_DWORD)v345 - v365;
            v748 = (_DWORD)v345 - v365;
            v746 = v364;
            v370 = ZSTD_hash6Ptr(v345, v367, v366);
            v372 = *(_DWORD *)(v371 + 4 * v370);
            v373 = *(unsigned int *)(a1 + 24);
            v374 = *(_QWORD *)(a1 + 64);
            v375 = *(_DWORD *)(a1 + 188) - 1;
            v772 = (unsigned int *)(v371 + 4 * v370);
            v751 = *(_QWORD *)(a1 + 16);
            v763 = (_DWORD *)(v373 + v376);
            LODWORD(v371) = 1 << v375;
            v377 = 0;
            v378 = v371 - 1;
            v758 = 0;
            v775 = 0;
            v770 = v378;
            v777 = v374;
            if ( v378 < v369 )
              v377 = v369 - v378;
            v757 = v373;
            v761 = v377;
            v379 = 1 << *(_DWORD *)(a1 + 184);
            v380 = *(_DWORD *)(a1 + 28);
            v381 = v369 - v379;
            v753 = (unsigned int *)v373;
            v382 = 1;
            if ( v369 - v380 <= v379 )
              v381 = v380;
            if ( *(_DWORD *)(a1 + 32) )
              v381 = v380;
            v383 = *(_DWORD *)(a1 + 196);
            if ( v381 )
              v382 = v381;
            v771 = v382;
            v384 = v369 & v378;
            v385 = 0;
            v806 = 0;
            v749 = v374 + 4LL * (unsigned int)(2 * v384);
            v762 = (unsigned int *)(v749 + 4);
            v756 = v369 + 9;
            v386 = 1 << v383;
            v387 = (_DWORD *)v752;
            v388 = v369 - v373;
            v745 = v386;
            v754 = v779;
            v389 = v755;
            v764 = v369 - v373;
            v390 = v755 + 3;
            v765 = v755 + 3;
            v391 = (unsigned int *)(v752 + 4LL * v755);
            while ( 2 )
            {
              if ( v389 == 3 )
                v392 = *v387 - 1;
              else
                v392 = *v391;
              v393 = v369 - v392;
              if ( v392 - 1 >= v388 )
              {
                if ( v392 - 1 < v369 - v381
                  && (unsigned int)(v373 - v393 - 1) >= 3
                  && (v406 = ZSTD_readMINMATCH(v750, 4, 0, v393), v406 == *v409) )
                {
                  v410 = v744;
                  v411 = v408 + 4;
                  v412 = (char *)v409 + v407;
                  v413 = (unsigned __int64)v753 + v751 + v408 + 4 - (_QWORD)v412;
                  if ( v413 < v744 )
                    v410 = v413;
                  v373 = ZSTD_count(v411, v412, v410);
                  if ( (unsigned int *)(v373 + v414) == (unsigned int *)((char *)v753 + v751) )
                  {
                    v415 = v373 + v411;
                    v398 = (_DWORD *)v744;
                    v416 = ZSTD_count(v415, v763, v744);
                    v390 = v765;
                    v385 = v416 + v373 + 4;
                    LODWORD(v373) = v757;
                  }
                  else
                  {
                    v398 = (_DWORD *)v744;
                    v385 = v373 + 4;
                    LODWORD(v373) = v757;
                    v390 = v765;
                  }
                }
                else
                {
                  v398 = (_DWORD *)v744;
                }
                v397 = v746;
              }
              else
              {
                v394 = ZSTD_readMINMATCH(v750, 4, 0, -(__int64)v392);
                v398 = (_DWORD *)v744;
                if ( v394 != *(_DWORD *)(v396 + v395) )
                  goto LABEL_455;
                v399 = (_QWORD *)(v395 + 4);
                v400 = (_QWORD *)(v396 + v395 + 4);
                v401 = v744 - 7;
                v402 = v395 + 4;
                if ( v395 + 4 >= v744 - 7 )
                  goto LABEL_435;
                if ( *v400 != *v399 )
                {
                  v385 = ZSTD_NbCommonBytes(*v400 ^ *v399, v399, v400, v402) + 4;
                  goto LABEL_455;
                }
                v399 = (_QWORD *)(v395 + 12);
                ++v400;
                if ( v395 + 12 >= v401 )
                {
LABEL_435:
                  if ( (unsigned __int64)v399 < v744 - 3 && *(_DWORD *)v400 == *(_DWORD *)v399 )
                  {
                    v399 = (_QWORD *)((char *)v399 + 4);
                    v400 = (_QWORD *)((char *)v400 + 4);
                  }
                  if ( (unsigned __int64)v399 < v744 - 1 && *(_WORD *)v400 == *(_WORD *)v399 )
                  {
                    v399 = (_QWORD *)((char *)v399 + 2);
                    v400 = (_QWORD *)((char *)v400 + 2);
                  }
                  if ( (unsigned __int64)v399 < v744 && *(_BYTE *)v400 == *(_BYTE *)v399 )
                    LODWORD(v399) = (_DWORD)v399 + 1;
                  v385 = (_DWORD)v399 - v395;
                }
                else
                {
                  while ( *v400 == *v399 )
                  {
                    ++v399;
                    ++v400;
                    if ( (unsigned __int64)v399 >= v401 )
                      goto LABEL_435;
                  }
                  v403 = ZSTD_NbCommonBytes(*v400 ^ *v399, v399, v400, v402);
                  v385 = v404 - v405 + v403 + 4;
                }
              }
LABEL_455:
              if ( v385 <= v754 )
              {
                v418 = v750;
              }
              else
              {
                v417 = &v768[2 * v806];
                *v417 = v389 - v755;
                v417[1] = v385;
                ++v806;
                v418 = v750;
                v754 = v385;
                if ( v385 > v397 || (unsigned int *)((char *)v750 + v385) == v398 )
                  goto LABEL_795;
              }
              v388 = v764;
              ++v389;
              v369 = v748;
              ++v391;
              v387 = (_DWORD *)v752;
              if ( v389 < v390 )
              {
                v385 = 0;
                continue;
              }
              break;
            }
            v419 = v748;
            v420 = v745;
            *v772 = v748;
            if ( v420 )
            {
              v421 = (unsigned __int64)v758;
              do
              {
                v745 = --v420;
                if ( v372 < v771 )
                  break;
                v422 = v775;
                if ( v421 < v775 )
                  v422 = v421;
                v423 = (_DWORD *)(v777 + 8LL * (v372 & v770));
                v774 = v423;
                if ( v372 + v422 < (unsigned __int64)v753 )
                {
                  v434 = (char *)v418 + v422;
                  v425 = v372 + v751;
                  v435 = (char *)v744;
                  if ( (unsigned int *)((char *)v753 + (_QWORD)v418 - v372) < (unsigned int *)v744 )
                    v435 = (char *)v753 + (_QWORD)v418 - v372;
                  v436 = ZSTD_count((char *)v418 + v422, v372 + v751 + v422, v435);
                  v438 = (_DWORD *)(v436 + v437);
                  v439 = v753;
                  if ( v438 == (unsigned int *)((char *)v753 + v751) )
                    v436 += ZSTD_count(&v434[v436], v763, v744);
                  v423 = v774;
                  v430 = v436 + v422;
                  v419 = v748;
                  v421 = (unsigned __int64)v758;
                  v91 = v372 + v430 < (unsigned __int64)v439;
                  v420 = v745;
                  if ( !v91 )
                    v425 = v372 + v767;
                  v427 = (_DWORD *)v744;
                }
                else
                {
                  v424 = (_QWORD *)((char *)v418 + v422);
                  v425 = v372 + v767;
                  v426 = (char *)v424;
                  v427 = (_DWORD *)v744;
                  v428 = (_QWORD *)(v425 + v422);
                  v429 = v744 - 7;
                  if ( (unsigned __int64)v424 >= v744 - 7 )
                    goto LABEL_472;
                  if ( *v428 != *v424 )
                  {
                    v430 = (unsigned int)ZSTD_NbCommonBytes(*v428 ^ *v424, v424, v428, v424) + v422;
                    goto LABEL_490;
                  }
                  ++v424;
                  ++v428;
                  if ( (unsigned __int64)v424 >= v429 )
                  {
LABEL_472:
                    if ( (unsigned __int64)v424 < v744 - 3 && *(_DWORD *)v428 == *(_DWORD *)v424 )
                    {
                      v424 = (_QWORD *)((char *)v424 + 4);
                      v428 = (_QWORD *)((char *)v428 + 4);
                    }
                    if ( (unsigned __int64)v424 < v744 - 1 && *(_WORD *)v428 == *(_WORD *)v424 )
                    {
                      v424 = (_QWORD *)((char *)v424 + 2);
                      v428 = (_QWORD *)((char *)v428 + 2);
                    }
                    if ( (unsigned __int64)v424 < v744 && *(_BYTE *)v428 == *(_BYTE *)v424 )
                      v424 = (_QWORD *)((char *)v424 + 1);
                    v430 = (char *)v424 - v426 + v422;
                  }
                  else
                  {
                    while ( *v428 == *v424 )
                    {
                      ++v424;
                      ++v428;
                      if ( (unsigned __int64)v424 >= v429 )
                        goto LABEL_472;
                    }
                    v431 = ZSTD_NbCommonBytes(*v428 ^ *v424, v424, v428, v426);
                    v430 = v432 - v433 + v431 + v422;
                  }
                }
LABEL_490:
                if ( v430 <= v754 )
                {
                  v418 = v750;
                }
                else
                {
                  if ( v430 > v756 - v372 )
                    v756 = v430 + v372;
                  v418 = v750;
                  v440 = &v768[2 * v806];
                  v440[1] = v430;
                  *v440 = v419 - v372 + 2;
                  v754 = v430;
                  ++v806;
                  if ( v430 > 0x1000 || (unsigned int *)((char *)v418 + v430) == v427 )
                    break;
                }
                if ( *(_BYTE *)(v425 + v430) >= *((_BYTE *)v418 + v430) )
                {
                  v775 = v430;
                  *v762 = v372;
                  if ( v372 <= v761 )
                  {
                    v442 = (unsigned int *)&v770;
                    goto LABEL_598;
                  }
                  v372 = *v423;
                  v762 = v423;
                }
                else
                {
                  v421 = v430;
                  v758 = (_DWORD *)v430;
                  *(_DWORD *)v749 = v372;
                  if ( v372 <= v761 )
                  {
                    v441 = (unsigned int *)&v770;
                    goto LABEL_600;
                  }
                  v372 = v423[1];
                  v749 = (unsigned __int64)(v423 + 1);
                }
              }
              while ( v420 );
            }
LABEL_599:
            v441 = (unsigned int *)v749;
LABEL_600:
            *v762 = 0;
            *v441 = 0;
            *(_DWORD *)(a1 + 36) = v756 - 8;
            goto LABEL_795;
          }
          if ( v368 < 0xFFF )
            v364 = *(_DWORD *)(a1 + 204);
          v443 = (_DWORD)v345 - v365;
          v748 = (_DWORD)v345 - v365;
          v746 = v364;
          v444 = ZSTD_hash4Ptr(v345, v367, v366);
          v446 = *(_DWORD *)(v445 + 4 * v444);
          v447 = *(unsigned int *)(a1 + 24);
          v448 = *(_QWORD *)(a1 + 64);
          v449 = *(_DWORD *)(a1 + 188) - 1;
          v772 = (unsigned int *)(v445 + 4 * v444);
          v751 = *(_QWORD *)(a1 + 16);
          v763 = (_DWORD *)(v447 + v450);
          LODWORD(v445) = 1 << v449;
          v451 = 0;
          v452 = v445 - 1;
          v758 = 0;
          v775 = 0;
          v764 = v452;
          v777 = v448;
          if ( v452 < v443 )
            v451 = v443 - v452;
          v771 = v447;
          v761 = v451;
          v453 = 1 << *(_DWORD *)(a1 + 184);
          v454 = *(_DWORD *)(a1 + 28);
          v455 = v443 - v453;
          v753 = (unsigned int *)v447;
          v456 = 1;
          if ( v443 - v454 <= v453 )
            v455 = v454;
          if ( *(_DWORD *)(a1 + 32) )
            v455 = v454;
          v457 = *(_DWORD *)(a1 + 196);
          v770 = v455;
          if ( v455 )
            v456 = v455;
          v757 = v456;
          v458 = v443 & v452;
          v459 = 0;
          v806 = 0;
          v749 = v448 + 4LL * (unsigned int)(2 * v458);
          v762 = (unsigned int *)(v749 + 4);
          v756 = v443 + 9;
          v460 = 1 << v457;
          v461 = (_DWORD *)v752;
          v462 = v443 - v447;
          v745 = v460;
          v754 = v779;
          v463 = v755;
          v765 = v443 - v447;
          v464 = v755 + 3;
          v465 = (unsigned int *)(v752 + 4LL * v755);
          while ( 2 )
          {
            if ( v463 == 3 )
              v466 = *v461 - 1;
            else
              v466 = *v465;
            v467 = v443 - v466;
            if ( v466 - 1 >= v462 )
            {
              if ( v466 - 1 < v443 - v455
                && (unsigned int)(v447 - v467 - 1) >= 3
                && (v480 = ZSTD_readMINMATCH(v750, 4, 0, v467), v480 == *v483) )
              {
                v484 = v744;
                v485 = v482 + 4;
                v486 = (char *)v483 + v481;
                v487 = v482 + 4 + (char *)v753 + v751 - v486;
                v488 = v482 + 4;
                if ( v488 + (char *)v753 + v751 - v486 < v744 )
                  v484 = v487;
                v447 = ZSTD_count(v488, v486, v484);
                if ( (unsigned int *)(v447 + v489) == (unsigned int *)((char *)v753 + v751) )
                {
                  v490 = v447 + v485;
                  v472 = (_DWORD *)v744;
                  v491 = ZSTD_count(v490, v763, v744);
                  v455 = v770;
                  v459 = v491 + v447 + 4;
                  LODWORD(v447) = v771;
                }
                else
                {
                  v472 = (_DWORD *)v744;
                  v459 = v447 + 4;
                  LODWORD(v447) = v771;
                  v455 = v770;
                }
              }
              else
              {
                v472 = (_DWORD *)v744;
              }
              v471 = v746;
              goto LABEL_548;
            }
            v468 = ZSTD_readMINMATCH(v750, 4, 0, -(__int64)v466);
            v472 = (_DWORD *)v744;
            if ( v468 == *(_DWORD *)(v470 + v469) )
            {
              v473 = (_QWORD *)(v469 + 4);
              v474 = (_QWORD *)(v470 + v469 + 4);
              v475 = v744 - 7;
              v476 = v469 + 4;
              if ( v469 + 4 < v744 - 7 )
              {
                if ( *v474 != *v473 )
                {
                  v459 = ZSTD_NbCommonBytes(*v474 ^ *v473, v473, v474, v476) + 4;
                  goto LABEL_548;
                }
                v473 = (_QWORD *)(v469 + 12);
                ++v474;
                if ( v469 + 12 < v475 )
                {
                  while ( *v474 == *v473 )
                  {
                    ++v473;
                    ++v474;
                    if ( (unsigned __int64)v473 >= v475 )
                      goto LABEL_528;
                  }
                  v477 = ZSTD_NbCommonBytes(*v474 ^ *v473, v473, v474, v476);
                  v459 = v478 - v479 + v477 + 4;
                  goto LABEL_548;
                }
              }
LABEL_528:
              if ( (unsigned __int64)v473 < v744 - 3 && *(_DWORD *)v474 == *(_DWORD *)v473 )
              {
                v473 = (_QWORD *)((char *)v473 + 4);
                v474 = (_QWORD *)((char *)v474 + 4);
              }
              if ( (unsigned __int64)v473 < v744 - 1 && *(_WORD *)v474 == *(_WORD *)v473 )
              {
                v473 = (_QWORD *)((char *)v473 + 2);
                v474 = (_QWORD *)((char *)v474 + 2);
              }
              if ( (unsigned __int64)v473 < v744 && *(_BYTE *)v474 == *(_BYTE *)v473 )
                LODWORD(v473) = (_DWORD)v473 + 1;
              v459 = (_DWORD)v473 - v469;
            }
LABEL_548:
            if ( v459 <= v754 )
            {
              v493 = v750;
            }
            else
            {
              v492 = &v768[2 * v806];
              *v492 = v463 - v755;
              v492[1] = v459;
              ++v806;
              v493 = v750;
              v754 = v459;
              if ( v459 > v471 || (unsigned int *)((char *)v750 + v459) == v472 )
                goto LABEL_795;
            }
            v462 = v765;
            ++v463;
            v443 = v748;
            ++v465;
            v461 = (_DWORD *)v752;
            if ( v463 >= v464 )
            {
              v494 = v748;
              v495 = v745;
              *v772 = v748;
              if ( !v495 )
                goto LABEL_599;
              v496 = (unsigned __int64)v758;
              while ( 2 )
              {
                v745 = --v495;
                if ( v446 < v757 )
                  goto LABEL_599;
                v497 = v775;
                if ( v496 < v775 )
                  v497 = v496;
                v498 = (_DWORD *)(v777 + 8LL * (v446 & v764));
                v774 = v498;
                if ( v497 + v446 < (unsigned __int64)v753 )
                {
                  v509 = (char *)v493 + v497;
                  v510 = (char *)v744;
                  v500 = v751 + v446;
                  if ( (unsigned int *)((char *)v753 + (_QWORD)v493 - v446) < (unsigned int *)v744 )
                    v510 = (char *)v753 + (_QWORD)v493 - v446;
                  v511 = ZSTD_count((char *)v493 + v497, v751 + v446 + v497, v510);
                  v513 = (_DWORD *)(v511 + v512);
                  v514 = v753;
                  if ( v513 == (unsigned int *)((char *)v753 + v751) )
                    v511 += ZSTD_count(&v509[v511], v763, v744);
                  v498 = v774;
                  v505 = v511 + v497;
                  v494 = v748;
                  v496 = (unsigned __int64)v758;
                  v91 = v505 + v446 < (unsigned __int64)v514;
                  v495 = v745;
                  if ( !v91 )
                    v500 = v446 + v767;
                  v502 = (_DWORD *)v744;
                  goto LABEL_583;
                }
                v499 = (_QWORD *)((char *)v493 + v497);
                v500 = v446 + v767;
                v501 = (char *)v499;
                v502 = (_DWORD *)v744;
                v503 = (_QWORD *)(v500 + v497);
                v504 = v744 - 7;
                if ( (unsigned __int64)v499 < v744 - 7 )
                {
                  if ( *v503 != *v499 )
                  {
                    v505 = (unsigned int)ZSTD_NbCommonBytes(*v503 ^ *v499, v499, v503, v499) + v497;
LABEL_583:
                    if ( v505 <= v754 )
                    {
                      v493 = v750;
                    }
                    else
                    {
                      if ( v505 > v756 - v446 )
                        v756 = v505 + v446;
                      v493 = v750;
                      v515 = &v768[2 * v806];
                      v515[1] = v505;
                      *v515 = v494 - v446 + 2;
                      v754 = v505;
                      ++v806;
                      if ( v505 > 0x1000 || (unsigned int *)((char *)v493 + v505) == v502 )
                        goto LABEL_599;
                    }
                    if ( *(_BYTE *)(v500 + v505) >= *((_BYTE *)v493 + v505) )
                    {
                      v775 = v505;
                      *v762 = v446;
                      if ( v446 <= v761 )
                      {
                        v442 = &v771;
                        goto LABEL_598;
                      }
                      v446 = *v498;
                      v762 = v498;
                    }
                    else
                    {
                      v496 = v505;
                      v758 = (_DWORD *)v505;
                      *(_DWORD *)v749 = v446;
                      if ( v446 <= v761 )
                      {
                        v441 = &v771;
                        goto LABEL_600;
                      }
                      v446 = v498[1];
                      v749 = (unsigned __int64)(v498 + 1);
                    }
                    if ( !v495 )
                      goto LABEL_599;
                    continue;
                  }
                  ++v499;
                  ++v503;
                  if ( (unsigned __int64)v499 < v504 )
                  {
                    while ( *v503 == *v499 )
                    {
                      ++v499;
                      ++v503;
                      if ( (unsigned __int64)v499 >= v504 )
                        goto LABEL_565;
                    }
                    v506 = ZSTD_NbCommonBytes(*v503 ^ *v499, v499, v503, v501);
                    v505 = v507 - v508 + v506 + v497;
                    goto LABEL_583;
                  }
                }
                break;
              }
LABEL_565:
              if ( (unsigned __int64)v499 < v744 - 3 && *(_DWORD *)v503 == *(_DWORD *)v499 )
              {
                v499 = (_QWORD *)((char *)v499 + 4);
                v503 = (_QWORD *)((char *)v503 + 4);
              }
              if ( (unsigned __int64)v499 < v744 - 1 && *(_WORD *)v503 == *(_WORD *)v499 )
              {
                v499 = (_QWORD *)((char *)v499 + 2);
                v503 = (_QWORD *)((char *)v503 + 2);
              }
              if ( (unsigned __int64)v499 < v744 && *(_BYTE *)v503 == *(_BYTE *)v499 )
                v499 = (_QWORD *)((char *)v499 + 1);
              v505 = (char *)v499 - v501 + v497;
              goto LABEL_583;
            }
            v459 = 0;
            continue;
          }
        }
        if ( *(_DWORD *)(a1 + 204) < 0xFFFu )
          v364 = *(_DWORD *)(a1 + 204);
        v516 = (_DWORD)v345 - v365;
        v748 = (_DWORD)v345 - v365;
        v746 = v364;
        v517 = ZSTD_hash5Ptr(v345, v367, v366);
        v519 = *(_DWORD *)(v518 + 4 * v517);
        v520 = *(unsigned int *)(a1 + 24);
        v521 = *(_QWORD *)(a1 + 64);
        v522 = *(_DWORD *)(a1 + 188) - 1;
        v772 = (unsigned int *)(v518 + 4 * v517);
        v751 = *(_QWORD *)(a1 + 16);
        v763 = (_DWORD *)(v520 + v523);
        LODWORD(v518) = 1 << v522;
        v524 = 0;
        v525 = v518 - 1;
        v758 = 0;
        v775 = 0;
        v764 = v525;
        v777 = v521;
        if ( v525 < v516 )
          v524 = v516 - v525;
        v771 = v520;
        v761 = v524;
        v526 = 1 << *(_DWORD *)(a1 + 184);
        v527 = *(_DWORD *)(a1 + 28);
        v528 = v516 - v526;
        v753 = (unsigned int *)v520;
        v529 = 1;
        if ( v516 - v527 <= v526 )
          v528 = v527;
        if ( *(_DWORD *)(a1 + 32) )
          v528 = v527;
        v530 = *(_DWORD *)(a1 + 196);
        if ( v528 )
          v529 = v528;
        v757 = v529;
        v531 = v516 & v525;
        v532 = 0;
        v806 = 0;
        v749 = v521 + 4LL * (unsigned int)(2 * v531);
        v762 = (unsigned int *)(v749 + 4);
        v756 = v516 + 9;
        v533 = 1 << v530;
        v534 = (_DWORD *)v752;
        v535 = v516 - v520;
        v745 = v533;
        v754 = v779;
        v536 = v755;
        v765 = v516 - v520;
        v537 = v755 + 3;
        v770 = v755 + 3;
        v538 = (unsigned int *)(v752 + 4LL * v755);
        while ( 2 )
        {
          if ( v536 == 3 )
            v539 = *v534 - 1;
          else
            v539 = *v538;
          v540 = v516 - v539;
          if ( v539 - 1 >= v535 )
          {
            if ( v539 - 1 < v516 - v528
              && (unsigned int)(v520 - v540 - 1) >= 3
              && (v553 = ZSTD_readMINMATCH(v750, 4, 0, v540), v553 == *v556) )
            {
              v557 = v744;
              v558 = v555 + 4;
              v559 = (char *)v556 + v554;
              v560 = (unsigned __int64)v753 + v751 + v555 + 4 - (_QWORD)v559;
              if ( v560 < v744 )
                v557 = v560;
              v520 = ZSTD_count(v558, v559, v557);
              if ( (unsigned int *)(v520 + v561) == (unsigned int *)((char *)v753 + v751) )
              {
                v562 = v520 + v558;
                v545 = (_DWORD *)v744;
                v563 = ZSTD_count(v562, v763, v744);
                v537 = v770;
                v532 = v563 + v520 + 4;
                LODWORD(v520) = v771;
              }
              else
              {
                v545 = (_DWORD *)v744;
                v532 = v520 + 4;
                LODWORD(v520) = v771;
                v537 = v770;
              }
            }
            else
            {
              v545 = (_DWORD *)v744;
            }
            v544 = v746;
            goto LABEL_644;
          }
          v541 = ZSTD_readMINMATCH(v750, 4, 0, -(__int64)v539);
          v545 = (_DWORD *)v744;
          if ( v541 == *(_DWORD *)(v543 + v542) )
          {
            v546 = (_QWORD *)(v542 + 4);
            v547 = (_QWORD *)(v543 + v542 + 4);
            v548 = v744 - 7;
            v549 = v542 + 4;
            if ( v542 + 4 < v744 - 7 )
            {
              if ( *v547 != *v546 )
              {
                v532 = ZSTD_NbCommonBytes(*v547 ^ *v546, v546, v547, v549) + 4;
                goto LABEL_644;
              }
              v546 = (_QWORD *)(v542 + 12);
              ++v547;
              if ( v542 + 12 < v548 )
              {
                while ( *v547 == *v546 )
                {
                  ++v546;
                  ++v547;
                  if ( (unsigned __int64)v546 >= v548 )
                    goto LABEL_624;
                }
                v550 = ZSTD_NbCommonBytes(*v547 ^ *v546, v546, v547, v549);
                v532 = v551 - v552 + v550 + 4;
                goto LABEL_644;
              }
            }
LABEL_624:
            if ( (unsigned __int64)v546 < v744 - 3 && *(_DWORD *)v547 == *(_DWORD *)v546 )
            {
              v546 = (_QWORD *)((char *)v546 + 4);
              v547 = (_QWORD *)((char *)v547 + 4);
            }
            if ( (unsigned __int64)v546 < v744 - 1 && *(_WORD *)v547 == *(_WORD *)v546 )
            {
              v546 = (_QWORD *)((char *)v546 + 2);
              v547 = (_QWORD *)((char *)v547 + 2);
            }
            if ( (unsigned __int64)v546 < v744 && *(_BYTE *)v547 == *(_BYTE *)v546 )
              LODWORD(v546) = (_DWORD)v546 + 1;
            v532 = (_DWORD)v546 - v542;
          }
LABEL_644:
          if ( v532 <= v754 )
          {
            v565 = v750;
          }
          else
          {
            v564 = &v768[2 * v806];
            *v564 = v536 - v755;
            v564[1] = v532;
            ++v806;
            v565 = v750;
            v754 = v532;
            if ( v532 > v544 || (unsigned int *)((char *)v750 + v532) == v545 )
              goto LABEL_795;
          }
          v535 = v765;
          ++v536;
          v516 = v748;
          ++v538;
          v534 = (_DWORD *)v752;
          if ( v536 >= v537 )
          {
            v566 = v748;
            v567 = v745;
            *v772 = v748;
            if ( !v567 )
              goto LABEL_599;
            v568 = (unsigned __int64)v758;
            while ( 2 )
            {
              v745 = --v567;
              if ( v519 < v757 )
                goto LABEL_599;
              v569 = v775;
              if ( v568 < v775 )
                v569 = v568;
              v570 = (_DWORD *)(v777 + 8LL * (v519 & v764));
              v774 = v570;
              if ( v519 + v569 < (unsigned __int64)v753 )
              {
                v581 = (char *)v565 + v569;
                v572 = v519 + v751;
                v582 = (char *)v744;
                if ( (unsigned int *)((char *)v753 + (_QWORD)v565 - v519) < (unsigned int *)v744 )
                  v582 = (char *)v753 + (_QWORD)v565 - v519;
                v583 = ZSTD_count((char *)v565 + v569, v519 + v751 + v569, v582);
                v585 = (_DWORD *)(v583 + v584);
                v586 = v753;
                if ( v585 == (unsigned int *)((char *)v753 + v751) )
                  v583 += ZSTD_count(&v581[v583], v763, v744);
                v570 = v774;
                v577 = v583 + v569;
                v566 = v748;
                v568 = (unsigned __int64)v758;
                v91 = v519 + v577 < (unsigned __int64)v586;
                v567 = v745;
                if ( !v91 )
                  v572 = v519 + v767;
                v574 = (_DWORD *)v744;
                goto LABEL_679;
              }
              v571 = (_QWORD *)((char *)v565 + v569);
              v572 = v519 + v767;
              v573 = (char *)v571;
              v574 = (_DWORD *)v744;
              v575 = (_QWORD *)(v572 + v569);
              v576 = v744 - 7;
              if ( (unsigned __int64)v571 < v744 - 7 )
              {
                if ( *v575 != *v571 )
                {
                  v577 = (unsigned int)ZSTD_NbCommonBytes(*v575 ^ *v571, v571, v575, v571) + v569;
LABEL_679:
                  if ( v577 <= v754 )
                  {
                    v565 = v750;
                  }
                  else
                  {
                    if ( v577 > v756 - v519 )
                      v756 = v577 + v519;
                    v565 = v750;
                    v587 = &v768[2 * v806];
                    v587[1] = v577;
                    *v587 = v566 - v519 + 2;
                    v754 = v577;
                    ++v806;
                    if ( v577 > 0x1000 || (unsigned int *)((char *)v565 + v577) == v574 )
                      goto LABEL_599;
                  }
                  if ( *(_BYTE *)(v572 + v577) >= *((_BYTE *)v565 + v577) )
                  {
                    v775 = v577;
                    *v762 = v519;
                    if ( v519 <= v761 )
                    {
                      v442 = (unsigned int *)&v765;
LABEL_598:
                      v762 = v442;
                      goto LABEL_599;
                    }
                    v519 = *v570;
                    v762 = v570;
                  }
                  else
                  {
                    v568 = v577;
                    v758 = (_DWORD *)v577;
                    *(_DWORD *)v749 = v519;
                    if ( v519 <= v761 )
                    {
                      v441 = (unsigned int *)&v765;
                      goto LABEL_600;
                    }
                    v519 = v570[1];
                    v749 = (unsigned __int64)(v570 + 1);
                  }
                  if ( !v567 )
                    goto LABEL_599;
                  continue;
                }
                ++v571;
                ++v575;
                if ( (unsigned __int64)v571 < v576 )
                {
                  while ( *v575 == *v571 )
                  {
                    ++v571;
                    ++v575;
                    if ( (unsigned __int64)v571 >= v576 )
                      goto LABEL_661;
                  }
                  v578 = ZSTD_NbCommonBytes(*v575 ^ *v571, v571, v575, v573);
                  v577 = v579 - v580 + v578 + v569;
                  goto LABEL_679;
                }
              }
              break;
            }
LABEL_661:
            if ( (unsigned __int64)v571 < v744 - 3 && *(_DWORD *)v575 == *(_DWORD *)v571 )
            {
              v571 = (_QWORD *)((char *)v571 + 4);
              v575 = (_QWORD *)((char *)v575 + 4);
            }
            if ( (unsigned __int64)v571 < v744 - 1 && *(_WORD *)v575 == *(_WORD *)v571 )
            {
              v571 = (_QWORD *)((char *)v571 + 2);
              v575 = (_QWORD *)((char *)v575 + 2);
            }
            if ( (unsigned __int64)v571 < v744 && *(_BYTE *)v575 == *(_BYTE *)v571 )
              v571 = (_QWORD *)((char *)v571 + 1);
            v577 = (char *)v571 - v573 + v569;
            goto LABEL_679;
          }
          v532 = 0;
          continue;
        }
      }
      v588 = *(_DWORD *)(a1 + 204);
      v774 = (_DWORD *)v365;
      if ( v588 < 0xFFF )
        v364 = v588;
      v589 = (_DWORD)v345 - v365;
      v748 = (_DWORD)v345 - v365;
      v756 = v364;
      v590 = ZSTD_hash4Ptr(v345, v367, v366);
      v592 = *(_DWORD *)(v591 + 4 * v590);
      v593 = (unsigned int *)*(unsigned int *)(a1 + 24);
      v594 = *(_QWORD *)(a1 + 64);
      v595 = *(_DWORD *)(a1 + 188) - 1;
      v772 = (unsigned int *)(v591 + 4 * v590);
      v775 = 0;
      v596 = (1 << v595) - 1;
      v777 = 0;
      v751 = *(_QWORD *)(a1 + 16);
      v767 = (__int64)v593 + v597;
      v598 = 0;
      v783 = v594;
      v765 = v596;
      v770 = (int)v593;
      v599 = 0;
      v753 = v593;
      if ( v596 < v589 )
        v599 = v589 - v596;
      v806 = 0;
      v757 = v599;
      v600 = 1 << *(_DWORD *)(a1 + 184);
      v601 = v589 - v600;
      v602 = 1;
      if ( v589 - *(_DWORD *)(a1 + 28) <= v600 )
        v601 = *(_DWORD *)(a1 + 28);
      if ( *(_DWORD *)(a1 + 32) )
        v601 = *(_DWORD *)(a1 + 28);
      v603 = *(_DWORD *)(a1 + 196);
      if ( v601 )
        v602 = v601;
      v745 = v602;
      v749 = v594 + 8LL * (v589 & v596);
      v763 = (_DWORD *)(v749 + 4);
      v761 = v589 + 9;
      v604 = 1 << v603;
      v605 = (_DWORD *)v752;
      v606 = v589 - (_DWORD)v593;
      v746 = v604;
      v754 = v779;
      v607 = v755;
      v771 = v589 - (_DWORD)v593;
      v608 = v755 + 3;
      v764 = v755 + 3;
      v609 = (unsigned int *)(v752 + 4LL * v755);
      while ( 2 )
      {
        if ( v607 == 3 )
          v610 = *v605 - 1;
        else
          v610 = *v609;
        v611 = v589 - v610;
        if ( v610 - 1 >= v606 )
        {
          if ( v610 - 1 < v589 - v601 && (unsigned int)v593 - v611 - 1 >= 3 )
          {
            v626 = (unsigned int)(*(_DWORD *)(v751 + v611) << 8);
            LODWORD(v758) = 1;
            v627 = ZSTD_readMINMATCH(v750, 3, v626, 0);
            if ( v627 == v631 )
            {
              v632 = v744;
              v633 = v629 + 3;
              v634 = v628 + v630;
              v635 = (unsigned __int64)v753 + v751 + v629 + 3 - v634;
              if ( v635 < v744 )
                v632 = v635;
              v636 = ZSTD_count(v633, v634, v632);
              if ( (unsigned int *)(v636 + v637) == (unsigned int *)((char *)v753 + v751) )
                LODWORD(v636) = ZSTD_count(v636 + v633, v767, v744) + v636;
              LODWORD(v593) = v770;
              v598 = v636 + 3;
              v608 = v764;
            }
          }
          v615 = v756;
          v616 = (_DWORD *)v744;
          goto LABEL_736;
        }
        LODWORD(v762) = 1;
        v612 = ZSTD_readMINMATCH(v750, 3, *(unsigned int *)((char *)v750 - v610) << 8, 0);
        v616 = (_DWORD *)v744;
        if ( v612 != v617 )
          goto LABEL_726;
        v618 = (_QWORD *)(v613 + 3);
        v619 = v613 + 3;
        v620 = (_QWORD *)(v614 + v613 + 3);
        v621 = v744 - 7;
        if ( v613 + 3 >= v744 - 7 )
          goto LABEL_716;
        if ( *v620 != *v618 )
        {
          v622 = ZSTD_NbCommonBytes(*v620 ^ *v618, v618, v620, v619);
          v608 = v764;
          v598 = v622 + 3;
          goto LABEL_736;
        }
        v618 = (_QWORD *)(v613 + 11);
        ++v620;
        if ( v613 + 11 >= v621 )
        {
LABEL_716:
          if ( (unsigned __int64)v618 < v744 - 3 && *(_DWORD *)v620 == *(_DWORD *)v618 )
          {
            v618 = (_QWORD *)((char *)v618 + 4);
            v620 = (_QWORD *)((char *)v620 + 4);
          }
          if ( (unsigned __int64)v618 < v744 - 1 && *(_WORD *)v620 == *(_WORD *)v618 )
          {
            v618 = (_QWORD *)((char *)v618 + 2);
            v620 = (_QWORD *)((char *)v620 + 2);
          }
          if ( (unsigned __int64)v618 < v744 && *(_BYTE *)v620 == *(_BYTE *)v618 )
            LODWORD(v618) = (_DWORD)v618 + 1;
          v598 = (_DWORD)v618 - v613;
LABEL_726:
          v608 = v764;
          goto LABEL_736;
        }
        while ( *v620 == *v618 )
        {
          ++v618;
          ++v620;
          if ( (unsigned __int64)v618 >= v621 )
            goto LABEL_716;
        }
        v623 = ZSTD_NbCommonBytes(*v620 ^ *v618, v618, v620, v619);
        v608 = v764;
        v598 = v624 - v625 + v623 + 3;
LABEL_736:
        v638 = v754;
        if ( v598 > v754 )
        {
          v639 = v806;
          v638 = v598;
          ++v806;
          v640 = &v768[2 * v639];
          v640[1] = v598;
          *v640 = v607 - v755;
          v754 = v598;
          if ( v598 > v615 || (unsigned int *)((char *)v750 + v598) == v616 )
            goto LABEL_795;
        }
        ++v607;
        ++v609;
        if ( v607 < v608 )
        {
          v606 = v771;
          v598 = 0;
          v589 = v748;
          v605 = (_DWORD *)v752;
          continue;
        }
        break;
      }
      if ( v638 >= 3 )
      {
        v648 = (char *)v744;
        v643 = v748;
        goto LABEL_749;
      }
      v641 = v750;
      FirstIndexHash3 = ZSTD_insertAndFindFirstIndexHash3(a1, &v782, v750);
      v643 = v748;
      v644 = v745;
      v645 = v748 - FirstIndexHash3;
      if ( FirstIndexHash3 >= v745 && v748 - FirstIndexHash3 < 0x40000 )
      {
        if ( FirstIndexHash3 < (unsigned int)v593 )
        {
          v646 = ZSTD_count_2segments(
                   (_DWORD)v641,
                   FirstIndexHash3 + (unsigned int)v751,
                   v744,
                   (int)v751 + (int)v593,
                   v767);
          v647 = 0;
        }
        else
        {
          v646 = ZSTD_count(v641, (char *)v774 + FirstIndexHash3, v744);
        }
        v648 = (char *)v744;
        if ( v646 >= 3 )
        {
          v649 = v768;
          v650 = v647;
          v754 = v646;
          v806 = 1;
          *v768 = v645 + 2;
          v649[1] = v646;
          LODWORD(v649) = v647;
          LOBYTE(v650) = (unsigned int *)((char *)v641 + v646) == (unsigned int *)v744;
          LOBYTE(v649) = v646 > v756;
          if ( (unsigned int)v649 | v650 )
          {
            v806 = 1;
            *(_DWORD *)(a1 + 36) = v643 + 1;
            goto LABEL_795;
          }
        }
LABEL_749:
        v644 = v745;
      }
      else
      {
        v648 = (char *)v744;
      }
      v651 = v746;
      *v772 = v643;
      if ( v651 )
      {
        while ( 2 )
        {
          v746 = --v651;
          if ( v592 < v644 )
            goto LABEL_793;
          v652 = (_DWORD *)(v783 + 8LL * (v592 & v765));
          v653 = v777;
          v758 = v652;
          if ( v775 < v777 )
            v653 = v775;
          if ( v592 + v653 < (unsigned __int64)v753 )
          {
            v665 = (char *)v750 + v653;
            v655 = (char *)(v592 + v751);
            v666 = v648;
            if ( (char *)v753 + (unsigned __int64)v750 - v592 < v648 )
              v666 = (char *)v753 + (_QWORD)v750 - v592;
            v667 = ZSTD_count((char *)v750 + v653, v592 + v751 + v653, v666);
            v669 = (_DWORD *)(v667 + v668);
            v654 = (_DWORD *)v744;
            if ( v669 == (unsigned int *)((char *)v753 + v751) )
              v667 += ZSTD_count(&v665[v667], v767, v744);
            v652 = v758;
            v661 = v667 + v653;
            v643 = v748;
            v651 = v746;
            if ( v592 + v661 >= (unsigned __int64)v753 )
              v655 = (char *)v774 + v592;
            v656 = v750;
            goto LABEL_780;
          }
          v654 = (_DWORD *)v744;
          v655 = (char *)v774 + v592;
          v656 = v750;
          v657 = v744 - 7;
          v658 = (_QWORD *)((char *)v750 + v653);
          v659 = &v655[v653];
          v660 = (char *)v750 + v653;
          if ( (unsigned __int64)v750 + v653 < v744 - 7 )
          {
            if ( *(_QWORD *)v659 != *v658 )
            {
              v661 = (unsigned int)ZSTD_NbCommonBytes(*(_QWORD *)v659 ^ *v658, v658, v659, v660) + v653;
LABEL_780:
              if ( v661 > v754 )
              {
                if ( v661 > v761 - v592 )
                  v761 = v661 + v592;
                v670 = v768;
                v768[2 * v806 + 1] = v661;
                v670[2 * v806] = v643 - v592 + 2;
                v754 = v661;
                ++v806;
                if ( v661 > 0x1000 || (unsigned int *)((char *)v656 + v661) == v654 )
                  goto LABEL_793;
              }
              if ( (unsigned __int8)v655[v661] >= *((_BYTE *)v656 + v661) )
              {
                v777 = v661;
                *v763 = v592;
                if ( v592 <= v757 )
                {
                  v763 = &v746;
                  goto LABEL_793;
                }
                v592 = *v652;
                v763 = v652;
              }
              else
              {
                v775 = v661;
                *(_DWORD *)v749 = v592;
                if ( v592 <= v757 )
                {
                  v671 = &v746;
                  goto LABEL_794;
                }
                v592 = v652[1];
                v749 = (unsigned __int64)(v652 + 1);
              }
              if ( !v651 )
                goto LABEL_793;
              v648 = (char *)v744;
              v644 = v745;
              continue;
            }
            ++v658;
            v659 += 8;
            if ( (unsigned __int64)v658 < v657 )
            {
              while ( *(_QWORD *)v659 == *v658 )
              {
                ++v658;
                v659 += 8;
                if ( (unsigned __int64)v658 >= v657 )
                  goto LABEL_762;
              }
              v662 = ZSTD_NbCommonBytes(*(_QWORD *)v659 ^ *v658, v658, v659, v660);
              v661 = v663 - v664 + v662 + v653;
              goto LABEL_780;
            }
          }
          break;
        }
LABEL_762:
        if ( (unsigned __int64)v658 < v744 - 3 && *(_DWORD *)v659 == *(_DWORD *)v658 )
        {
          v658 = (_QWORD *)((char *)v658 + 4);
          v659 += 4;
        }
        if ( (unsigned __int64)v658 < v744 - 1 && *(_WORD *)v659 == *(_WORD *)v658 )
        {
          v658 = (_QWORD *)((char *)v658 + 2);
          v659 += 2;
        }
        if ( (unsigned __int64)v658 < v744 && *v659 == *(_BYTE *)v658 )
          v658 = (_QWORD *)((char *)v658 + 1);
        v661 = (char *)v658 - (char *)v750;
        goto LABEL_780;
      }
LABEL_793:
      v671 = (_DWORD *)v749;
LABEL_794:
      *v763 = 0;
      *v671 = 0;
      *(_DWORD *)(a1 + 36) = v761 - 8;
LABEL_795:
      if ( !v806 )
        goto LABEL_821;
      v672 = v768;
      v673 = v768[2 * v806 - 1];
      if ( v673 <= v781 && v673 + v747 < 0x1000 )
      {
        v674 = 0;
        v757 = 0;
        v675 = v768;
        v772 = v768;
        while ( 1 )
        {
          v676 = *v675;
          v677 = ZSTD_updateRep(v797, v752, *v675, v755);
          v680 = v678[1];
          v681 = *(_QWORD *)v677;
          v682 = *(_DWORD *)(v677 + 8);
          v683 = v674 ? v672[2 * v674 - 1] + 1 : v776;
          if ( v680 >= v683 )
            break;
          v340 = v773;
LABEL_819:
          v672 = v768;
          ++v674;
          v675 = v678 + 2;
          v757 = v674;
          v772 = v675;
          if ( v674 >= v806 )
            goto LABEL_822;
        }
        v684 = v778;
        v685 = v680 + v679;
        while ( 2 )
        {
          _BitScanReverse((unsigned int *)&v686, v676 + 1);
          v13 = *(_DWORD *)(v684 + 80) == 1;
          v687 = v685 - v679 - 3;
          LODWORD(v754) = 0;
          if ( v13 )
          {
            LODWORD(v753) = 0;
            _BitScanReverse(&v688, v687 + 1);
            v689 = ((unsigned int)(((_DWORD)v687 + 1) << 8) >> v688) + v769 + (((_DWORD)v686 + v688 + 16) << 8);
          }
          else
          {
            v690 = *(_QWORD *)(v684 + 24);
            LODWORD(v751) = 0;
            v691 = *(_DWORD *)(v690 + 4 * v686) + 1;
            _BitScanReverse((unsigned int *)&v690, v691);
            v692 = *(_DWORD *)(v684 + 76) + (((_DWORD)v686 - (_DWORD)v690) << 8) - (v691 << 8 >> v690);
            if ( (unsigned int)v687 <= 0x7F )
            {
              _mm_lfence();
              v694 = *((unsigned __int8 *)&qword_1803EF770[8] + v687);
            }
            else
            {
              _BitScanReverse(&v693, v687);
              LODWORD(v749) = 0;
              v694 = v693 + 36;
            }
            v695 = 4 * v694;
            LODWORD(v750) = 0;
            v696 = *(_DWORD *)(*(_QWORD *)(v684 + 16) + 4 * v694) + 1;
            _BitScanReverse(&v697, v696);
            v689 = v692
                 + v769
                 + *(_DWORD *)(v684 + 72)
                 + ((*(_DWORD *)((char *)&qword_1803EF640[10] + v695) - v697) << 8)
                 - (v696 << 8 >> v697)
                 + 51;
          }
          v340 = v773;
          if ( v685 <= v342 )
          {
            if ( v689 < v773[7 * v685] )
            {
              if ( v342 < v685 )
                goto LABEL_813;
LABEL_815:
              v698 = 7LL * v685;
              v699 = v760;
              *(_QWORD *)&v340[v698 + 4] = v681;
              v340[v698 + 6] = v682;
              v340[v698 + 2] = v685 - v679;
              v340[v698 + 1] = v676;
              v340[v698 + 3] = v699;
              v340[v698] = v689;
            }
            if ( --v685 - v679 < v683 )
            {
              v674 = v757;
              v678 = v772;
              goto LABEL_819;
            }
            continue;
          }
          break;
        }
        do
LABEL_813:
          v340[7 * ++v342] = 0x40000000;
        while ( v342 < v685 );
        v766 = v342;
        goto LABEL_815;
      }
      v706 = 0;
      v314 = v773;
      DWORD1(v785) = v768[2 * v806 - 2];
      v707 = 7LL * v747;
      *((_QWORD *)&v785 + 1) = __PAIR64__(v760, v673);
      if ( v773[v707 + 2] )
        v708 = 0;
      else
        v708 = v773[v707 + 3];
      LODWORD(v311) = v778;
      v705 = 0;
      if ( v747 - v708 <= 0x1000 )
        v705 = v747 - v708;
LABEL_833:
      v709 = v705 + 1;
      v710 = v705 + 1;
      v711 = 7LL * (v705 + 1);
      v712 = v780;
      *(_OWORD *)&v314[v711] = v785;
      *(_QWORD *)&v314[v711 + 4] = v15;
      v314[v711 + 6] = v712;
      while ( v705 )
      {
        v713 = &v314[7 * v705];
        v714 = *(_OWORD *)v713;
        v790 = v713[6];
        v715 = *((_QWORD *)v713 + 2);
        v788 = v714;
        v789 = v715;
        *(double *)&v714 = ZSTD_totalLen(&v788);
        v716 = 7LL * --v710;
        *(_OWORD *)&v314[v716] = v714;
        *(_QWORD *)&v314[v716 + 4] = *(_QWORD *)(v717 + 16);
        v314[v716 + 6] = *(_DWORD *)(v717 + 24);
        v718 = v705;
        v705 -= v719;
        if ( v718 <= v719 )
          v705 = v706;
      }
      if ( v710 <= v709 )
      {
        v720 = v802;
        while ( 1 )
        {
          v721 = 7LL * v710;
          v722 = v314[v721 + 2];
          v723 = (unsigned int)v314[v721 + 3];
          v724 = v314[v721 + 1];
          v725 = v722 + v723;
          if ( v722 )
            break;
          v759 = v720 + v723;
LABEL_861:
          LODWORD(v311) = v778;
          ++v710;
          v706 = 0;
          if ( v710 > v709 )
            goto LABEL_862;
        }
        if ( v724 >= 3 )
        {
          a3[2] = a3[1];
          a3[1] = *a3;
          *a3 = v724 - 2;
          goto LABEL_849;
        }
        v726 = v706;
        LOBYTE(v726) = (_DWORD)v723 == 0;
        v727 = v724 + v726;
        if ( (_DWORD)v727 )
        {
          if ( (_DWORD)v727 == 3 )
          {
            v728 = *a3 - 1;
            goto LABEL_847;
          }
          v728 = a3[v727];
          if ( (unsigned int)v727 >= 2 )
LABEL_847:
            a3[2] = a3[1];
          a3[1] = *a3;
          *a3 = v728;
        }
LABEL_849:
        ZSTD_updateStats(v311, v723, v802, v724, v722);
        v729 = v722 - 3;
        v731 = v730;
        v732 = *(_QWORD *)(a2 + 24);
        if ( v730 + v802 <= v744 - 32 )
        {
          ZSTD_copy16(v732);
          if ( v731 > 0x10 )
          {
            ZSTD_copy16(*(_QWORD *)(a2 + 24) + 16LL);
            v735 = ZSTD_copy16(v734 + 16);
            v737 = v736 + 16;
            if ( v737 < v735 )
            {
              do
              {
                ZSTD_copy16(v737);
                v739 = ZSTD_copy16(v738 + 16);
                v737 = v740 + 16;
              }
              while ( v737 < v739 );
            }
LABEL_855:
            v733 = v802;
          }
          *(_QWORD *)(a2 + 24) += v731;
          v741 = *(_QWORD *)(a2 + 8);
          if ( v731 > 0xFFFF )
          {
            *(_DWORD *)(a2 + 72) = 1;
            *(_DWORD *)(a2 + 76) = (v741 - *(_QWORD *)a2) >> 3;
          }
          *(_WORD *)(v741 + 4) = v731;
          **(_DWORD **)(a2 + 8) = v724 + 1;
          v742 = *(_QWORD *)(a2 + 8);
          if ( v729 > 0xFFFF )
          {
            *(_DWORD *)(a2 + 72) = 2;
            *(_DWORD *)(a2 + 76) = (v742 - *(_QWORD *)a2) >> 3;
          }
          v314 = v773;
          *(_WORD *)(v742 + 6) = v729;
          *(_QWORD *)(a2 + 8) += 8LL;
          v802 = v725 + v733;
          v720 = v802;
          v759 = v802;
          goto LABEL_861;
        }
        ZSTD_safecopyLiterals(v732);
        goto LABEL_855;
      }
LABEL_862:
      ZSTD_setBasePrices(v778, 2);
      v14 = v759;
LABEL_865:
      v10 = v744;
      v5 = a1;
      v8 = v802;
      if ( v14 >= v784 )
        return v10 - v8;
    }
    v231 = *(_DWORD *)(a1 + 204);
    v232 = *(_DWORD **)(a1 + 8);
    v758 = v232;
    if ( v231 < 0xFFF )
      v21 = v231;
    v747 = v14 - (_DWORD)v232;
    v233 = ZSTD_hash4Ptr(v14, v23, v22);
    v236 = *(_DWORD *)(v235 + 4 * v233);
    v237 = *(_QWORD *)(a1 + 64);
    v238 = *(_DWORD *)(a1 + 188);
    v772 = (unsigned int *)(v235 + 4 * v233);
    v239 = (unsigned int *)*(unsigned int *)(a1 + 24);
    v240 = v19;
    v749 = *(_QWORD *)(a1 + 16);
    LODWORD(v235) = 1 << (v238 - 1);
    v241 = 0;
    v242 = v235 - 1;
    v751 = 0;
    v763 = 0;
    v754 = (unsigned __int64)v239 + v243;
    v767 = v237;
    v769 = v242;
    v762 = v239;
    if ( v242 < v234 )
      v241 = v234 - v242;
    v760 = v241;
    v244 = 1 << *(_DWORD *)(a1 + 184);
    v245 = v234 - v244;
    v246 = 1;
    if ( v234 - *(_DWORD *)(a1 + 28) <= v244 )
      v245 = *(_DWORD *)(a1 + 28);
    if ( *(_DWORD *)(a1 + 32) )
      v245 = *(_DWORD *)(a1 + 28);
    v247 = *(_DWORD *)(a1 + 196);
    if ( v245 )
      v246 = v245;
    v748 = v246;
    v804 = 0;
    v750 = (unsigned int *)(v237 + 8LL * (v234 & v242));
    v248 = v19 + 3;
    v766 = v19 + 3;
    v753 = v750 + 1;
    v746 = v234 + 9;
    v249 = 1 << v247;
    v250 = a3;
    v745 = v249;
    v779 = (unsigned int)(v776 - 1);
    v752 = v779;
    v251 = v19;
    v252 = v234 - (_DWORD)v239;
    v253 = (unsigned int *)&a3[v251];
    while ( 1 )
    {
      if ( v240 == 3 )
        v254 = *v250 - 1;
      else
        v254 = *v253;
      v255 = v234 - v254;
      v256 = 0;
      if ( v254 - 1 >= v252 )
      {
        if ( v254 - 1 < v747 - v245 && (unsigned int)v239 - v255 - 1 >= 3 )
        {
          v268 = (unsigned int)(*(_DWORD *)(v749 + v255) << 8);
          LODWORD(v777) = 1;
          v269 = ZSTD_readMINMATCH(v759, 3, v268, 0);
          if ( v269 == v272 )
          {
            v273 = ZSTD_count_2segments(v270 + 3, v271 + 3, v744, (int)v239 + (int)v749, v754);
            v248 = v766;
            v256 = v273 + 3;
          }
        }
      }
      else
      {
        LODWORD(v783) = 1;
        v257 = ZSTD_readMINMATCH(v759, 3, (unsigned int)(*(_DWORD *)(v759 - v254) << 8), 0);
        if ( v257 == v260 )
        {
          v261 = (_QWORD *)(v258 + 3);
          v262 = v258 + 3;
          v263 = (_QWORD *)(v259 + v258 + 3);
          v264 = v744 - 7;
          if ( v258 + 3 >= v744 - 7 )
            goto LABEL_296;
          if ( *v261 != *v263 )
          {
            v256 = ZSTD_NbCommonBytes(*v261 ^ *v263, v261, v263, v262) + 3;
            goto LABEL_310;
          }
          v261 = (_QWORD *)(v258 + 11);
          ++v263;
          if ( v258 + 11 >= v264 )
          {
LABEL_296:
            if ( (unsigned __int64)v261 < v744 - 3 && *(_DWORD *)v263 == *(_DWORD *)v261 )
            {
              v261 = (_QWORD *)((char *)v261 + 4);
              v263 = (_QWORD *)((char *)v263 + 4);
            }
            if ( (unsigned __int64)v261 < v744 - 1 && *(_WORD *)v263 == *(_WORD *)v261 )
            {
              v261 = (_QWORD *)((char *)v261 + 2);
              v263 = (_QWORD *)((char *)v263 + 2);
            }
            if ( (unsigned __int64)v261 < v744 && *(_BYTE *)v263 == *(_BYTE *)v261 )
              LODWORD(v261) = (_DWORD)v261 + 1;
            v256 = (_DWORD)v261 - v258;
          }
          else
          {
            while ( *v261 == *v263 )
            {
              ++v261;
              ++v263;
              if ( (unsigned __int64)v261 >= v264 )
                goto LABEL_296;
            }
            v265 = ZSTD_NbCommonBytes(*v261 ^ *v263, v261, v263, v262);
            v256 = v266 - v267 + v265 + 3;
          }
        }
      }
LABEL_310:
      v274 = v752;
      if ( v256 > v752 )
      {
        v274 = v256;
        v275 = &v768[2 * v804];
        *v275 = v240 - v755;
        v276 = v804 + 1;
        v752 = v256;
        v277 = v759 + v256;
        v275[1] = v256;
        ++v804;
        if ( v256 > v21 || v277 == v744 )
        {
          v163 = v276;
          goto LABEL_376;
        }
      }
      ++v240;
      ++v253;
      if ( v240 >= v248 )
      {
        if ( v274 >= 3 )
        {
          v280 = v747;
          goto LABEL_326;
        }
        v278 = v759;
        v279 = ZSTD_insertAndFindFirstIndexHash3(a1, &v782, v759);
        v280 = v747;
        v281 = v748;
        v282 = v747 - v279;
        if ( v279 < v748 || v747 - v279 >= 0x40000 )
        {
          v274 = v752;
          v286 = v804;
          goto LABEL_328;
        }
        if ( v279 < (unsigned int)v239 )
        {
          v283 = ZSTD_count_2segments(v278, (unsigned int)v749 + v279, v744, (int)v749 + (int)v239, v754);
          v284 = v744;
        }
        else
        {
          v283 = ZSTD_count(v278, (char *)v758 + v279, v744);
        }
        if ( v283 < 3 )
        {
          v274 = v752;
LABEL_326:
          v286 = v804;
          goto LABEL_327;
        }
        v285 = v768;
        v274 = v283;
        v752 = v283;
        v286 = 1;
        v804 = 1;
        *v768 = v282 + 2;
        v285[1] = v283;
        if ( v283 > v21 || v283 + v278 == v284 )
        {
          *(_DWORD *)(a1 + 36) = v280 + 1;
          goto LABEL_375;
        }
LABEL_327:
        v281 = v748;
LABEL_328:
        v287 = v745;
        *v772 = v280;
        if ( !v287 )
        {
LABEL_373:
          v308 = v750;
LABEL_374:
          *v753 = 0;
          *v308 = 0;
          *(_DWORD *)(a1 + 36) = v746 - 8;
LABEL_375:
          v163 = v286;
          goto LABEL_376;
        }
        v288 = v751;
        while ( 2 )
        {
          v745 = --v287;
          if ( v236 < v281 )
            goto LABEL_373;
          v289 = v763;
          if ( v288 < (unsigned __int64)v763 )
            v289 = (_DWORD *)v288;
          v290 = (unsigned int *)(v767 + 8LL * (v236 & v769));
          if ( (_DWORD *)((char *)v289 + v236) < v762 )
          {
            v301 = (char *)v289 + v759;
            v291 = v236 + v749;
            v302 = (char *)v744;
            if ( (unsigned __int64)v762 + v759 - v236 < v744 )
              v302 = (char *)v762 + v759 - v236;
            v303 = ZSTD_count((char *)v289 + v759, (char *)v289 + v236 + v749, v302);
            v305 = (_DWORD *)(v303 + v304);
            v306 = v762;
            if ( v305 == (unsigned int *)((char *)v762 + v749) )
              v303 += ZSTD_count(&v301[v303], v754, v744);
            v274 = v752;
            v297 = (unsigned __int64)v289 + v303;
            v280 = v747;
            v288 = v751;
            v91 = v297 + v236 < (unsigned __int64)v306;
            v287 = v745;
            if ( !v91 )
              v291 = (unsigned __int64)v758 + v236;
            v292 = v744;
            goto LABEL_358;
          }
          v291 = (unsigned __int64)v758 + v236;
          v292 = v744;
          v293 = (_QWORD *)((char *)v289 + v759);
          v294 = (char *)v289 + v759;
          v295 = (_QWORD *)((char *)v289 + v291);
          v296 = v744 - 7;
          if ( (unsigned __int64)v289 + v759 < v744 - 7 )
          {
            if ( *v293 != *v295 )
            {
              v297 = (unsigned __int64)v289 + (unsigned int)ZSTD_NbCommonBytes(*v293 ^ *v295, v293, v295, v294);
LABEL_358:
              if ( v297 <= v274 )
              {
                v286 = v804;
              }
              else
              {
                if ( v297 > v746 - v236 )
                  v746 = v297 + v236;
                v307 = v768;
                v768[2 * v804 + 1] = v297;
                v307[2 * v804] = v280 - v236 + 2;
                v286 = v804 + 1;
                v752 = v297;
                ++v804;
                v274 = v297;
                if ( v297 > 0x1000 || v297 + v759 == v292 )
                  goto LABEL_373;
              }
              if ( *(_BYTE *)(v291 + v297) >= *(_BYTE *)(v297 + v759) )
              {
                v763 = (_DWORD *)v297;
                *v753 = v236;
                if ( v236 <= v760 )
                {
                  v753 = &v745;
                  goto LABEL_373;
                }
                v236 = *v290;
                v753 = v290;
              }
              else
              {
                v288 = v297;
                v751 = v297;
                *v750 = v236;
                if ( v236 <= v760 )
                {
                  v308 = &v745;
                  goto LABEL_374;
                }
                v236 = v290[1];
                v750 = v290 + 1;
              }
              if ( !v287 )
                goto LABEL_373;
              v281 = v748;
              continue;
            }
            ++v293;
            ++v295;
            if ( (unsigned __int64)v293 < v296 )
            {
              while ( *v293 == *v295 )
              {
                ++v293;
                ++v295;
                if ( (unsigned __int64)v293 >= v296 )
                  goto LABEL_340;
              }
              v298 = ZSTD_NbCommonBytes(*v293 ^ *v295, v293, v295, v294);
              v297 = (unsigned __int64)v289 + v299 - v300 + v298;
              goto LABEL_358;
            }
          }
          break;
        }
LABEL_340:
        if ( (unsigned __int64)v293 < v744 - 3 && *(_DWORD *)v295 == *(_DWORD *)v293 )
        {
          v293 = (_QWORD *)((char *)v293 + 4);
          v295 = (_QWORD *)((char *)v295 + 4);
        }
        if ( (unsigned __int64)v293 < v744 - 1 && *(_WORD *)v295 == *(_WORD *)v293 )
        {
          v293 = (_QWORD *)((char *)v293 + 2);
          v295 = (_QWORD *)((char *)v295 + 2);
        }
        if ( (unsigned __int64)v293 < v744 && *(_BYTE *)v295 == *(_BYTE *)v293 )
          v293 = (_QWORD *)((char *)v293 + 1);
        v297 = (unsigned __int64)v293 - v759;
        goto LABEL_358;
      }
      v234 = v747;
      v250 = a3;
    }
  }
  return v10 - v8;
}

```

## disassembly

```asm
0x1802de8e0  mov     [rsp-8+arg_18], r9
0x1802de8e5  mov     [rsp-8+arg_10], r8
0x1802de8ea  mov     [rsp-8+arg_8], rdx
0x1802de8ef  mov     [rsp-8+arg_0], rcx
0x1802de8f4  push    rbp
0x1802de8f5  push    rbx
0x1802de8f6  push    rsi
0x1802de8f7  push    rdi
0x1802de8f8  push    r13
0x1802de8fa  push    r15
0x1802de8fc  lea     rbp, [rsp-0F8h]
0x1802de904  sub     rsp, 1F8h
0x1802de90b  mov     r8, [rbp+120h+arg_20]
0x1802de912  mov     r13, rcx
0x1802de915  add     rcx, 48h ; 'H'
0x1802de919  mov     edx, 0FFFh
0x1802de91e  mov     rdi, r9
0x1802de921  mov     [rbp+120h+var_110], rcx
0x1802de925  mov     eax, [r13+0CCh]
0x1802de92c  lea     r15, [r9+r8]
0x1802de930  mov     ebx, [r13+18h]
0x1802de934  lea     rsi, [r15-8]
0x1802de938  add     rbx, [r13+8]
0x1802de93c  mov     r9d, 2
0x1802de942  cmp     eax, edx
0x1802de944  mov     [rsp+220h+var_1F0], r15
0x1802de949  mov     [rbp+120h+var_E8], rsi
0x1802de94d  cmovb   edx, eax
0x1802de950  xor     eax, eax
0x1802de952  cmp     dword ptr [r13+0C8h], 3
0x1802de95a  mov     [rbp+120h+var_FC], edx
0x1802de95d  mov     rdx, rdi
0x1802de960  setnz   al
0x1802de963  add     eax, 3
0x1802de966  mov     [rbp+120h+var_120], eax
0x1802de969  mov     eax, [r13+24h]
0x1802de96d  mov     [rbp+120h+var_F8], eax
0x1802de970  mov     rax, [rcx+28h]
0x1802de974  mov     [rbp+120h+var_138], rax
0x1802de978  mov     rax, [rcx+20h]
0x1802de97c  mov     [rbp+120h+var_158], rax
0x1802de980  call    ZSTD_rescaleFreqs
0x1802de985  xor     r11d, r11d
0x1802de988  cmp     rdi, rbx
0x1802de98b  mov     ecx, r11d
0x1802de98e  setz    cl
0x1802de991  add     rcx, rdi
0x1802de994  mov     [rbp+120h+var_190], rcx
0x1802de998  cmp     rcx, rsi
0x1802de99b  jnb     loc_1802E255F
0x1802de9a1  mov     eax, [rbp+120h+var_C8]
0x1802de9a4  movsd   xmm2, [rbp+120h+var_D0]
0x1802de9a9  mov     [rsp+220h+var_30], r12
0x1802de9b1  mov     [rsp+220h+var_38], r14
0x1802de9b9  mov     [rbp+120h+var_100], eax
0x1802de9bc  nop     dword ptr [rax+00h]
0x1802de9c0  mov     ebx, [r13+24h]
0x1802de9c4  mov     eax, ecx
0x1802de9c6  mov     r14, [r13+8]
0x1802de9ca  sub     eax, edi
0x1802de9cc  mov     esi, [r13+0C8h]
0x1802de9d3  mov     r12d, r11d
0x1802de9d6  setz    r12b
0x1802de9da  mov     [rbp+120h+var_16C], eax
0x1802de9dd  mov     [rsp+220h+var_1A8], r12d
0x1802de9e2  lea     rax, [r14+rbx]
0x1802de9e6  cmp     rcx, rax
0x1802de9e9  jb      loc_1802E2525
0x1802de9ef  mov     edi, ecx
0x1802de9f1  sub     edi, r14d
0x1802de9f4  cmp     ebx, edi
0x1802de9f6  jnb     short loc_1802DEA28
0x1802de9f8  nop     dword ptr [rax+rax+00000000h]
0x1802dea00  mov     edx, ebx
0x1802dea02  mov     r9d, esi
0x1802dea05  add     rdx, r14
0x1802dea08  mov     dword ptr [rsp+220h+var_200], 1
0x1802dea10  mov     r8, r15
0x1802dea13  mov     rcx, r13
0x1802dea16  call    ZSTD_insertBt1
0x1802dea1b  add     ebx, eax
0x1802dea1d  cmp     ebx, edi
0x1802dea1f  jb      short loc_1802DEA00
0x1802dea21  mov     rcx, [rbp+120h+var_190]
0x1802dea25  xor     r11d, r11d
0x1802dea28  mov     r14, [rbp+120h+arg_0]
0x1802dea2f  mov     r13d, 0FFFh
0x1802dea35  mov     r8, [r14+30h]
0x1802dea39  mov     [r14+24h], edi
0x1802dea3d  mov     edx, [r14+0C0h]
0x1802dea44  cmp     esi, 3
0x1802dea47  jz      loc_1802DFB42
0x1802dea4d  mov     r9, [r14+8]
0x1802dea51  mov     r10d, ecx
0x1802dea54  mov     [rbp+120h+var_178], r9
0x1802dea58  cmp     esi, 5
0x1802dea5b  jz      loc_1802DF5B6
0x1802dea61  lea     eax, [rsi-6]
0x1802dea64  cmp     eax, 1
0x1802dea67  mov     eax, [r14+0CCh]
0x1802dea6e  ja      loc_1802DF004
0x1802dea74  cmp     eax, r13d
0x1802dea77  cmovb   r13d, eax
0x1802dea7b  sub     r10d, r9d
0x1802dea7e  mov     [rsp+220h+var_1E0], r10d
0x1802dea83  call    ZSTD_hash6Ptr
0x1802dea88  mov     r15d, [r8+rax*4]
0x1802dea8c  lea     rax, [r8+rax*4]
0x1802dea90  mov     ecx, [r14+0BCh]
0x1802dea97  mov     edx, 1
0x1802dea9c  mov     rbx, [r14+40h]
0x1802deaa0  dec     ecx
0x1802deaa2  mov     [rbp+120h+var_140], rax
0x1802deaa6  mov     r8d, 1
0x1802deaac  mov     rax, [r14+10h]
0x1802deab0  mov     esi, r10d
0x1802deab3  mov     [rsp+220h+var_1D0], rax
0x1802deab8  shl     r8d, cl
0x1802deabb  xor     ecx, ecx
0x1802deabd  dec     r8d
0x1802deac0  mov     [rsp+220h+var_1C8], r11
0x1802deac5  mov     [rsp+220h+var_1B8], r11
0x1802deaca  mov     r11d, [r14+18h]
0x1802deace  mov     [rbp+120h+var_160], rbx
0x1802dead2  mov     [rbp+120h+var_1A0], r8d
0x1802dead6  mov     [rbp+120h+var_168], r11d
0x1802deada  lea     rax, [r9+r11]
0x1802deade  mov     [rbp+120h+var_198], r11
0x1802deae2  mov     [rbp+120h+var_180], rax
0x1802deae6  mov     eax, r10d
0x1802deae9  sub     eax, r8d
0x1802deaec  cmp     r8d, r10d
0x1802deaef  cmovb   ecx, eax
0x1802deaf2  mov     eax, r10d
0x1802deaf5  mov     [rbp+120h+var_188], ecx
0x1802deaf8  mov     ecx, [r14+0B8h]
0x1802deaff  shl     edx, cl
0x1802deb01  mov     ecx, [r14+1Ch]
0x1802deb05  sub     esi, edx
0x1802deb07  sub     eax, ecx
0x1802deb09  cmp     eax, edx
0x1802deb0b  mov     eax, 1
0x1802deb10  cmovbe  esi, ecx
0x1802deb13  cmp     dword ptr [r14+20h], 0
0x1802deb18  cmovnz  esi, ecx
0x1802deb1b  mov     ecx, [r14+0C4h]
0x1802deb22  test    esi, esi
0x1802deb24  mov     r14d, r10d
0x1802deb27  cmovnz  eax, esi
0x1802deb2a  xor     edx, edx
0x1802deb2c  mov     [rbp+120h+var_150], eax
0x1802deb2f  add     r12d, 3
0x1802deb33  mov     eax, r8d
0x1802deb36  mov     dword ptr [rbp+120h+arg_20], edx
0x1802deb3c  and     eax, r10d
0x1802deb3f  add     eax, eax
0x1802deb41  lea     rax, [rbx+rax*4]
0x1802deb45  mov     [rsp+220h+var_1C0], rax
0x1802deb4a  add     rax, 4
0x1802deb4e  mov     [rsp+220h+var_1B0], rax
0x1802deb53  lea     eax, [r10+9]
0x1802deb57  mov     [rsp+220h+var_1E4], eax
0x1802deb5b  mov     eax, 1
0x1802deb60  shl     eax, cl
0x1802deb62  mov     rcx, [rbp+120h+arg_10]
0x1802deb69  mov     [rsp+220h+var_1E8], eax
0x1802deb6d  mov     eax, [rbp+120h+var_120]
0x1802deb70  dec     eax
0x1802deb72  mov     [rbp+120h+var_108], rax
0x1802deb76  sub     r14d, r11d
0x1802deb79  mov     [rsp+220h+var_1D8], rax
0x1802deb7e  mov     eax, [rsp+220h+var_1A8]
0x1802deb82  mov     ebx, eax
0x1802deb84  lea     rdi, [rcx+rax*4]
0x1802deb88  cmp     ebx, 3
0x1802deb8b  jnz     short loc_1802DEB93
0x1802deb8d  mov     eax, [rcx]
0x1802deb8f  dec     eax
0x1802deb91  jmp     short loc_1802DEB95
0x1802deb93  mov     eax, [rdi]
0x1802deb95  mov     r9d, r10d
0x1802deb98  lea     ecx, [rax-1]
0x1802deb9b  sub     r9d, eax
0x1802deb9e  mov     r8d, edx
0x1802deba1  cmp     ecx, r14d
0x1802deba4  jnb     loc_1802DEC8B
0x1802debaa  mov     rcx, [rbp+120h+var_190]
0x1802debae  mov     edx, 4
0x1802debb3  mov     r9d, eax
0x1802debb6  neg     r9
0x1802debb9  call    ZSTD_readMINMATCH
0x1802debbe  cmp     eax, [r9+rcx]
0x1802debc2  jnz     loc_1802DECF6
0x1802debc8  lea     rdx, [rcx+4]
0x1802debcc  lea     r8, [rcx+4]
0x1802debd0  mov     rcx, [rsp+220h+var_1F0]
0x1802debd5  add     r8, r9
0x1802debd8  mov     r9, rdx
0x1802debdb  lea     rax, [rcx-7]
0x1802debdf  cmp     rdx, rax
0x1802debe2  jnb     short loc_1802DEC2A
0x1802debe4  mov     rcx, [rdx]
0x1802debe7  xor     rcx, [r8]
0x1802debea  jz      short loc_1802DEBFC
0x1802debec  call    ZSTD_NbCommonBytes
0x1802debf1  mov     ecx, eax
0x1802debf3  lea     r8d, [rcx+4]
0x1802debf7  jmp     loc_1802DECF6
0x1802debfc  add     rdx, 8
0x1802dec00  add     r8, 8
0x1802dec04  cmp     rdx, rax
0x1802dec07  jnb     short loc_1802DEC25
0x1802dec09  nop     dword ptr [rax+00000000h]
0x1802dec10  mov     rcx, [rdx]
0x1802dec13  xor     rcx, [r8]
0x1802dec16  jnz     short loc_1802DEC78
0x1802dec18  add     rdx, 8
0x1802dec1c  add     r8, 8
0x1802dec20  cmp     rdx, rax
0x1802dec23  jb      short loc_1802DEC10
0x1802dec25  mov     rcx, [rsp+220h+var_1F0]
0x1802dec2a  lea     rax, [rcx-3]
0x1802dec2e  cmp     rdx, rax
0x1802dec31  jnb     short loc_1802DEC42
0x1802dec33  mov     eax, [rdx]
0x1802dec35  cmp     [r8], eax
0x1802dec38  jnz     short loc_1802DEC42
0x1802dec3a  add     rdx, 4
0x1802dec3e  add     r8, 4
0x1802dec42  lea     rax, [rcx-1]
0x1802dec46  cmp     rdx, rax
0x1802dec49  jnb     short loc_1802DEC5C
0x1802dec4b  movzx   eax, word ptr [rdx]
0x1802dec4e  cmp     [r8], ax
0x1802dec52  jnz     short loc_1802DEC5C
0x1802dec54  add     rdx, 2
0x1802dec58  add     r8, 2
0x1802dec5c  cmp     rdx, rcx
0x1802dec5f  jnb     short loc_1802DEC6C
0x1802dec61  movzx   eax, byte ptr [rdx]
0x1802dec64  cmp     [r8], al
0x1802dec67  jnz     short loc_1802DEC6C
0x1802dec69  inc     rdx
0x1802dec6c  mov     rcx, rdx
0x1802dec6f  sub     rcx, r9
0x1802dec72  lea     r8d, [rcx+4]
0x1802dec76  jmp     short loc_1802DECF6
0x1802dec78  call    ZSTD_NbCommonBytes
0x1802dec7d  mov     ecx, eax
0x1802dec7f  sub     rdx, r9
0x1802dec82  add     rcx, rdx
0x1802dec85  lea     r8d, [rcx+4]
0x1802dec89  jmp     short loc_1802DECF6
0x1802dec8b  mov     eax, [rsp+220h+var_1E0]
0x1802dec8f  sub     eax, esi
0x1802dec91  mov     r10d, r9d
0x1802dec94  add     r10, [rsp+220h+var_1D0]
0x1802dec99  cmp     ecx, eax
0x1802dec9b  mov     ecx, r11d
0x1802dec9e  setb    dl
0x1802deca1  sub     ecx, r9d
0x1802deca4  xor     eax, eax
0x1802deca6  dec     ecx
0x1802deca8  cmp     ecx, 3
0x1802decab  setnb   al
0x1802decae  test    eax, edx
0x1802decb0  jz      short loc_1802DECF1
0x1802decb2  mov     rcx, [rbp+120h+var_190]
0x1802decb6  mov     edx, 4
0x1802decbb  call    ZSTD_readMINMATCH
0x1802decc0  cmp     eax, [r10]
0x1802decc3  jnz     short loc_1802DECF1
0x1802decc5  mov     rax, [rbp+120h+var_180]
0x1802decc9  lea     rdx, [r10+4]
0x1802deccd  mov     r9, [rsp+220h+var_1D0]
0x1802decd2  add     rcx, 4
0x1802decd6  add     r9, [rbp+120h+var_198]
0x1802decda  mov     r8, [rsp+220h+var_1F0]
0x1802decdf  mov     [rsp+220h+var_200], rax
0x1802dece4  call    ZSTD_count_2segments
0x1802dece9  mov     r11d, [rbp+120h+var_168]
0x1802deced  lea     r8d, [rax+4]
0x1802decf1  mov     r10d, [rsp+220h+var_1E0]
0x1802decf6  mov     eax, r8d
0x1802decf9  cmp     rax, [rsp+220h+var_1D8]
0x1802decfe  jbe     short loc_1802DED4F
0x1802ded00  mov     r9d, dword ptr [rbp+120h+arg_20]
0x1802ded07  mov     ecx, ebx
0x1802ded09  sub     ecx, [rsp+220h+var_1A8]
0x1802ded0d  mov     rdx, [rbp+120h+var_158]
0x1802ded11  lea     rdx, [rdx+r9*8]
0x1802ded15  inc     r9d
0x1802ded18  mov     [rdx], ecx
0x1802ded1a  mov     [rsp+220h+var_1D8], rax
0x1802ded1f  add     rax, [rbp+120h+var_190]
0x1802ded23  mov     dword ptr [rbp+120h+arg_20], r9d
0x1802ded2a  mov     r9, [rsp+220h+var_1F0]
0x1802ded2f  mov     [rdx+4], r8d
0x1802ded33  xor     edx, edx
0x1802ded35  cmp     rax, r9
  ... truncated ...
```
