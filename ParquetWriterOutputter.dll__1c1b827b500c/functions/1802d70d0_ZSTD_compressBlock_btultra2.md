# ZSTD_compressBlock_btultra2

- ea: `0x1802d70d0`
- end: `0x1802da132`
- name: `ZSTD_compressBlock_btultra2`
- size: `12386`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1802b6fe0`
- `0x1802bb530`
- `0x1802bb540`
- `0x1802bb7b0`
- `0x1802bb7f0`
- `0x1802bb820`
- `0x1802bb8c0`
- `0x1802d70d0`
- `0x1802e26a0`
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
unsigned __int64 __fastcall ZSTD_compressBlock_btultra2(
        __int64 a1,
        __int64 a2,
        _DWORD *a3,
        unsigned __int64 a4,
        unsigned __int64 a5)
{
  unsigned __int64 v5; // rsi
  int v6; // r10d
  __int64 v7; // r12
  int v8; // r8d
  unsigned int v9; // eax
  unsigned __int64 v10; // r13
  __int64 v11; // rbx
  int v12; // edx
  unsigned __int64 v13; // rcx
  __int64 v14; // xmm2_8
  __int64 v15; // rbx
  __int64 v16; // r14
  bool v17; // zf
  unsigned int v18; // eax
  int v19; // esi
  BOOL v20; // r15d
  unsigned int v21; // edi
  __int64 v22; // r8
  __int64 v23; // rdx
  unsigned int v24; // r14d
  unsigned int v25; // eax
  unsigned int v26; // ebx
  __int64 v27; // rax
  __int64 v28; // r8
  unsigned int *v29; // r15
  int v30; // r8d
  char v31; // cl
  _DWORD *v32; // rdi
  unsigned int v33; // r10d
  _DWORD *v34; // r9
  int v35; // r11d
  unsigned int v36; // r9d
  unsigned int v37; // ecx
  unsigned int v38; // r11d
  unsigned int v39; // edx
  int v40; // ecx
  int v41; // eax
  int v42; // ecx
  unsigned int *v43; // r13
  unsigned int v44; // edi
  unsigned __int64 v45; // r12
  _DWORD *v46; // rcx
  unsigned int v47; // r11d
  unsigned int v48; // esi
  unsigned int *v49; // rbx
  unsigned int v50; // ecx
  unsigned int v51; // r8d
  int MINMATCH; // eax
  __int64 v53; // rcx
  __int64 v54; // r9
  _QWORD *v55; // rdx
  __int64 v56; // r8
  unsigned __int64 v57; // rcx
  _QWORD *v58; // r8
  _QWORD *v59; // r9
  unsigned __int64 v60; // rax
  int v61; // ecx
  __int64 v62; // rax
  _DWORD *v63; // rcx
  int v64; // eax
  int v65; // edx
  int v66; // r9d
  int v67; // esi
  _DWORD *v68; // r9
  unsigned __int64 v69; // r15
  unsigned __int64 v70; // r14
  unsigned int *v71; // rdi
  char *v72; // r11
  _QWORD *v73; // rdx
  unsigned __int64 v74; // rax
  char *v75; // rbx
  _QWORD *v76; // r8
  unsigned __int64 v77; // rcx
  unsigned __int64 v78; // r9
  _DWORD *v79; // rcx
  int v80; // eax
  unsigned int *v81; // rax
  unsigned int v82; // eax
  unsigned int v83; // ebx
  unsigned int v84; // eax
  __int64 v85; // rdx
  unsigned int v86; // ebx
  __int64 v87; // rax
  __int64 v88; // r8
  unsigned int *v89; // r15
  int v90; // r8d
  char v91; // cl
  _DWORD *v92; // rdi
  unsigned int v93; // r10d
  _DWORD *v94; // r9
  int v95; // r11d
  unsigned int v96; // r9d
  unsigned int v97; // ecx
  unsigned int v98; // r11d
  unsigned int v99; // edx
  int v100; // ecx
  int v101; // eax
  int v102; // ecx
  unsigned int v103; // edi
  unsigned __int64 v104; // r12
  _DWORD *v105; // rcx
  unsigned int v106; // r11d
  unsigned int v107; // esi
  unsigned int *v108; // rbx
  unsigned int v109; // ecx
  unsigned int v110; // r8d
  int v111; // eax
  __int64 v112; // rcx
  __int64 v113; // r9
  _QWORD *v114; // rdx
  __int64 v115; // r8
  unsigned __int64 v116; // rcx
  _QWORD *v117; // r8
  _QWORD *v118; // r9
  unsigned __int64 v119; // rax
  int v120; // ecx
  __int64 v121; // rax
  _DWORD *v122; // rcx
  int v123; // eax
  int v124; // edx
  int v125; // r9d
  int v126; // esi
  _DWORD *v127; // r9
  unsigned __int64 v128; // r15
  unsigned __int64 v129; // r14
  unsigned int *v130; // rdi
  char *v131; // r11
  _QWORD *v132; // rdx
  unsigned __int64 v133; // rax
  char *v134; // rbx
  _QWORD *v135; // r8
  unsigned __int64 v136; // rcx
  unsigned __int64 v137; // r9
  _DWORD *v138; // rcx
  int v139; // eax
  unsigned int v140; // eax
  __int64 v141; // rdx
  unsigned int v142; // ebx
  __int64 v143; // rax
  __int64 v144; // r8
  unsigned int *v145; // r15
  int v146; // r8d
  char v147; // cl
  _DWORD *v148; // rdi
  unsigned int v149; // r10d
  _DWORD *v150; // r9
  int v151; // r11d
  unsigned int v152; // r9d
  unsigned int v153; // ecx
  unsigned int v154; // r11d
  unsigned int v155; // edx
  int v156; // ecx
  int v157; // eax
  int v158; // ecx
  unsigned int v159; // edi
  unsigned __int64 v160; // r12
  _DWORD *v161; // rcx
  unsigned int v162; // r11d
  unsigned int v163; // esi
  unsigned int *v164; // rbx
  unsigned int v165; // ecx
  unsigned int v166; // r8d
  int v167; // eax
  __int64 v168; // rcx
  __int64 v169; // r9
  _QWORD *v170; // rdx
  __int64 v171; // r8
  unsigned __int64 v172; // rcx
  _QWORD *v173; // r8
  _QWORD *v174; // r9
  unsigned __int64 v175; // rax
  int v176; // ecx
  __int64 v177; // rax
  _DWORD *v178; // rcx
  int v179; // eax
  int v180; // edx
  int v181; // r9d
  int v182; // esi
  _DWORD *v183; // r9
  unsigned __int64 v184; // r15
  unsigned __int64 v185; // r14
  unsigned int *v186; // rdi
  char *v187; // r11
  _QWORD *v188; // rdx
  unsigned __int64 v189; // rax
  char *v190; // rbx
  _QWORD *v191; // r8
  unsigned __int64 v192; // rcx
  unsigned __int64 v193; // r9
  _DWORD *v194; // rcx
  int v195; // eax
  unsigned int v196; // eax
  __int64 v197; // rdx
  unsigned int v198; // esi
  unsigned int v199; // r10d
  __int64 v200; // rax
  unsigned int v201; // r10d
  __int64 v202; // r8
  unsigned int *v203; // r12
  unsigned int v204; // ebx
  char *v205; // r9
  int v206; // r8d
  _DWORD *v207; // rdi
  unsigned int v208; // ecx
  unsigned int v209; // r11d
  unsigned int v210; // edx
  int v211; // ecx
  int v212; // eax
  int v213; // ecx
  unsigned int v214; // r15d
  unsigned int v215; // r8d
  unsigned int v216; // r14d
  unsigned __int64 v217; // r13
  _DWORD *v218; // rcx
  unsigned int v219; // r11d
  unsigned int *v220; // rdi
  unsigned int v221; // ecx
  unsigned int v222; // r9d
  int v223; // eax
  __int64 v224; // rcx
  __int64 v225; // r10
  int v226; // r8d
  _QWORD *v227; // rdx
  __int64 v228; // r9
  _QWORD *v229; // r8
  unsigned __int64 v230; // r10
  unsigned __int64 v231; // rax
  int v232; // eax
  int v233; // eax
  int v234; // edx
  int v235; // r9d
  __int64 v236; // rax
  _DWORD *v237; // rcx
  unsigned __int64 v238; // r15
  unsigned int FirstIndexHash3; // eax
  unsigned int v240; // edi
  unsigned int v241; // r8d
  unsigned __int64 v242; // r14
  unsigned __int64 v243; // rax
  int v244; // r11d
  _DWORD *v245; // rdx
  int v246; // ecx
  int v247; // r11d
  unsigned int v248; // eax
  unsigned int v249; // esi
  unsigned int v250; // r12d
  _DWORD *v251; // r9
  unsigned __int64 v252; // r15
  unsigned __int64 v253; // r14
  unsigned int *v254; // rdi
  char *v255; // r10
  _QWORD *v256; // rdx
  unsigned __int64 v257; // rax
  _QWORD *v258; // r8
  signed __int64 v259; // rcx
  unsigned __int64 v260; // r9
  _DWORD *v261; // rcx
  int v262; // eax
  unsigned int v263; // eax
  __int64 v264; // rdx
  __int64 v265; // r11
  unsigned int *v266; // rax
  _DWORD *v267; // rcx
  int *v268; // r14
  unsigned int v269; // r13d
  __int64 v270; // rdx
  __int64 v271; // r15
  __int64 v272; // r8
  int v273; // eax
  _DWORD *v274; // r9
  unsigned int *v275; // rsi
  unsigned __int64 v276; // rcx
  unsigned int v277; // edi
  _DWORD *v278; // rax
  unsigned int *v279; // r12
  unsigned int *v280; // r15
  unsigned int v281; // ebx
  __int64 updated; // rax
  int v283; // r10d
  int v284; // r11d
  __int64 v285; // xmm1_8
  int v286; // r14d
  __int64 v287; // r12
  __int64 v288; // r9
  __int64 v289; // r8
  unsigned int v290; // ecx
  unsigned int v291; // edx
  unsigned int v292; // edx
  unsigned int v293; // ecx
  unsigned int v294; // r9d
  unsigned int v295; // eax
  __int64 v296; // rax
  unsigned int v297; // r8d
  unsigned int v298; // ecx
  _DWORD *v299; // r9
  __int64 v300; // rcx
  __int64 v301; // r15
  unsigned int v302; // eax
  unsigned int v303; // edi
  __int64 v304; // r13
  _DWORD *v305; // r12
  _DWORD *v306; // r14
  unsigned int v307; // esi
  int v308; // ebx
  int v309; // r8d
  int v310; // ebx
  int v311; // eax
  __int64 v312; // r8
  int v313; // eax
  _DWORD *v314; // rbx
  int v315; // r15d
  __int64 v316; // xmm0_8
  int v317; // eax
  int v318; // eax
  __int64 v319; // rbx
  __int64 v320; // r15
  int v321; // r14d
  unsigned int v322; // esi
  int v323; // r12d
  __int64 v324; // r8
  __int64 v325; // rdx
  unsigned int v326; // r15d
  unsigned int v327; // eax
  unsigned int v328; // ebx
  __int64 v329; // rax
  __int64 v330; // r8
  unsigned int *v331; // r12
  int v332; // r8d
  _DWORD *v333; // rsi
  unsigned int v334; // r10d
  _DWORD *v335; // r9
  int v336; // r11d
  unsigned int v337; // ecx
  unsigned int v338; // r11d
  unsigned int v339; // edx
  int v340; // ecx
  int v341; // eax
  int v342; // ecx
  unsigned __int64 v343; // r13
  unsigned int v344; // r11d
  unsigned int v345; // r14d
  _DWORD *v346; // rcx
  unsigned int v347; // esi
  unsigned int *v348; // rbx
  unsigned int v349; // ecx
  unsigned int v350; // r8d
  int v351; // eax
  __int64 v352; // rcx
  __int64 v353; // r9
  _QWORD *v354; // rdx
  __int64 v355; // r8
  unsigned __int64 v356; // rcx
  _QWORD *v357; // r8
  _QWORD *v358; // r9
  unsigned __int64 v359; // rax
  int v360; // ecx
  __int64 v361; // rax
  _DWORD *v362; // rcx
  int v363; // eax
  int v364; // edx
  int v365; // r9d
  unsigned int v366; // r14d
  unsigned __int64 v367; // r9
  _DWORD *v368; // r15
  _DWORD *v369; // r12
  unsigned int *v370; // rsi
  __int64 v371; // r11
  _QWORD *v372; // rdx
  unsigned __int64 v373; // rax
  char *v374; // rbx
  _QWORD *v375; // r8
  unsigned __int64 v376; // rcx
  unsigned __int64 v377; // r9
  _DWORD *v378; // rcx
  int v379; // eax
  unsigned int v380; // eax
  __int64 v381; // rdx
  _DWORD *v382; // rax
  unsigned int v383; // eax
  int *v384; // rax
  _DWORD *v385; // rax
  unsigned int v386; // ebx
  __int64 v387; // rax
  __int64 v388; // r8
  unsigned int *v389; // r12
  int v390; // r8d
  _DWORD *v391; // rsi
  unsigned int v392; // r10d
  _DWORD *v393; // r9
  int v394; // r11d
  unsigned int v395; // ecx
  unsigned int v396; // r11d
  unsigned int v397; // edx
  int v398; // ecx
  int v399; // eax
  int v400; // ecx
  unsigned __int64 v401; // r13
  unsigned int v402; // r11d
  unsigned int v403; // r14d
  _DWORD *v404; // rcx
  unsigned int v405; // esi
  unsigned int *v406; // rbx
  unsigned int v407; // ecx
  unsigned int v408; // r8d
  int v409; // eax
  __int64 v410; // rcx
  __int64 v411; // r9
  _QWORD *v412; // rdx
  __int64 v413; // r8
  unsigned __int64 v414; // rcx
  _QWORD *v415; // r8
  _QWORD *v416; // r9
  unsigned __int64 v417; // rax
  int v418; // ecx
  __int64 v419; // rax
  _DWORD *v420; // rcx
  int v421; // eax
  int v422; // edx
  int v423; // r9d
  unsigned int v424; // r14d
  unsigned __int64 v425; // r9
  _DWORD *v426; // r15
  _DWORD *v427; // r12
  unsigned int *v428; // rsi
  __int64 v429; // r11
  _QWORD *v430; // rdx
  unsigned __int64 v431; // rax
  char *v432; // rbx
  _QWORD *v433; // r8
  unsigned __int64 v434; // rcx
  unsigned __int64 v435; // r9
  _DWORD *v436; // rcx
  int v437; // eax
  unsigned int v438; // eax
  __int64 v439; // rdx
  _DWORD *v440; // rax
  unsigned int v441; // ebx
  __int64 v442; // rax
  __int64 v443; // r8
  unsigned int *v444; // r12
  int v445; // r8d
  _DWORD *v446; // rsi
  unsigned int v447; // r10d
  _DWORD *v448; // r9
  int v449; // r11d
  unsigned int v450; // ecx
  unsigned int v451; // r11d
  unsigned int v452; // edx
  int v453; // ecx
  int v454; // eax
  int v455; // ecx
  unsigned __int64 v456; // r13
  unsigned int v457; // r11d
  unsigned int v458; // r14d
  _DWORD *v459; // rcx
  unsigned int v460; // esi
  unsigned int *v461; // rbx
  unsigned int v462; // ecx
  unsigned int v463; // r8d
  int v464; // eax
  __int64 v465; // rcx
  __int64 v466; // r9
  _QWORD *v467; // rdx
  __int64 v468; // r8
  unsigned __int64 v469; // rcx
  _QWORD *v470; // r8
  _QWORD *v471; // r9
  unsigned __int64 v472; // rax
  int v473; // ecx
  __int64 v474; // rax
  _DWORD *v475; // rcx
  int v476; // eax
  int v477; // edx
  int v478; // r9d
  int v479; // r14d
  unsigned __int64 v480; // r9
  _DWORD *v481; // r15
  _DWORD *v482; // r12
  unsigned int *v483; // rsi
  __int64 v484; // r11
  _QWORD *v485; // rdx
  unsigned __int64 v486; // rax
  char *v487; // rbx
  _QWORD *v488; // r8
  unsigned __int64 v489; // rcx
  unsigned __int64 v490; // r9
  _DWORD *v491; // rcx
  int v492; // eax
  unsigned int v493; // eax
  __int64 v494; // rdx
  _DWORD *v495; // rax
  unsigned int v496; // r14d
  unsigned int v497; // r10d
  __int64 v498; // rax
  unsigned int v499; // r10d
  __int64 v500; // r8
  unsigned int *v501; // r13
  unsigned int v502; // ebx
  int v503; // r8d
  _DWORD *v504; // rsi
  unsigned int v505; // ecx
  unsigned int v506; // r11d
  unsigned int v507; // edx
  int v508; // ecx
  int v509; // eax
  int v510; // ecx
  unsigned int v511; // r8d
  unsigned int v512; // r12d
  unsigned int v513; // r11d
  _DWORD *v514; // rcx
  unsigned int v515; // r15d
  unsigned int *v516; // rsi
  unsigned int v517; // ecx
  unsigned int v518; // r9d
  int v519; // eax
  __int64 v520; // rcx
  __int64 v521; // r10
  int v522; // r8d
  _QWORD *v523; // rdx
  __int64 v524; // r9
  _QWORD *v525; // r8
  _DWORD *v526; // r10
  unsigned __int64 v527; // rax
  int v528; // eax
  int v529; // edx
  int v530; // r9d
  __int64 v531; // rax
  _DWORD *v532; // rcx
  unsigned __int64 v533; // r15
  _DWORD *v534; // r12
  unsigned int v535; // eax
  unsigned int v536; // esi
  unsigned int v537; // r8d
  unsigned __int64 v538; // rax
  int v539; // r11d
  _DWORD *v540; // rdx
  int v541; // ecx
  int v542; // r11d
  unsigned int v543; // eax
  int v544; // r14d
  unsigned __int64 v545; // r9
  _DWORD *v546; // r12
  _DWORD *v547; // r13
  unsigned int *v548; // rsi
  unsigned __int64 v549; // r10
  _QWORD *v550; // rdx
  unsigned __int64 v551; // rax
  _QWORD *v552; // r8
  signed __int64 v553; // rcx
  unsigned __int64 v554; // r9
  _DWORD *v555; // rcx
  int v556; // eax
  unsigned int v557; // eax
  __int64 v558; // rdx
  __int64 v559; // r11
  char *v560; // rax
  _DWORD *v561; // rsi
  unsigned int v562; // ecx
  unsigned int v563; // r13d
  unsigned int *v564; // r10
  int v565; // r14d
  __int64 v566; // rax
  _DWORD *v567; // r10
  int v568; // r11d
  unsigned int v569; // edx
  __int64 v570; // xmm1_8
  int v571; // r12d
  unsigned int v572; // esi
  __int64 v573; // r13
  unsigned int v574; // eax
  __int64 v575; // r10
  __int64 v576; // r9
  unsigned int v577; // ecx
  signed int v578; // r8d
  __int64 v579; // rcx
  unsigned int v580; // r8d
  int v581; // r10d
  unsigned int v582; // ecx
  __int64 v583; // rcx
  __int64 v584; // rdx
  unsigned int v585; // r9d
  unsigned int v586; // ecx
  __int64 v587; // rdx
  unsigned int v588; // ecx
  unsigned int v589; // r10d
  __int64 v590; // rax
  int v591; // eax
  unsigned int v592; // edi
  _DWORD *v593; // rdx
  __int64 v594; // rdx
  __int128 v595; // xmm0
  unsigned int v596; // eax
  int v597; // eax
  unsigned int v598; // r12d
  unsigned int v599; // esi
  __int64 v600; // rcx
  int v601; // eax
  _DWORD *v602; // r8
  __int128 v603; // xmm0
  __int64 v604; // xmm1_8
  __int64 v605; // rdx
  __int64 v606; // r8
  unsigned int v607; // ecx
  unsigned int v608; // eax
  unsigned __int64 v609; // r8
  __int64 v610; // rcx
  int v611; // ebx
  __int64 v612; // rdx
  unsigned int v613; // edi
  unsigned int v614; // r15d
  unsigned int v615; // ecx
  __int64 v616; // rcx
  int v617; // r8d
  unsigned int v618; // r14d
  unsigned __int64 v619; // rdx
  unsigned __int64 v620; // rbx
  __int64 v621; // rcx
  unsigned __int64 v622; // rdx
  __int64 v623; // rcx
  unsigned __int64 v624; // rax
  __int64 v625; // rcx
  unsigned __int64 v626; // rcx
  __int64 v627; // rcx
  unsigned __int64 v628; // rax
  __int64 v629; // rcx
  __int64 v630; // rcx
  __int64 v631; // rcx
  unsigned int v633; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v634; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v635; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v636; // [rsp+40h] [rbp-C0h]
  _DWORD *v637; // [rsp+48h] [rbp-B8h]
  unsigned int *v638; // [rsp+50h] [rbp-B0h]
  BOOL v639; // [rsp+58h] [rbp-A8h]
  _DWORD *v640; // [rsp+60h] [rbp-A0h]
  unsigned int v641; // [rsp+68h] [rbp-98h]
  unsigned int v642; // [rsp+6Ch] [rbp-94h]
  char *v643; // [rsp+70h] [rbp-90h]
  unsigned int v644; // [rsp+78h] [rbp-88h]
  int v645; // [rsp+7Ch] [rbp-84h]
  _DWORD *v646; // [rsp+80h] [rbp-80h]
  unsigned __int64 v647; // [rsp+88h] [rbp-78h]
  unsigned int v648; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v649; // [rsp+94h] [rbp-6Ch] BYREF
  _DWORD *v650; // [rsp+98h] [rbp-68h]
  unsigned __int64 v651; // [rsp+A0h] [rbp-60h]
  _DWORD *v652; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v653; // [rsp+B0h] [rbp-50h]
  int v654; // [rsp+B8h] [rbp-48h]
  int v655; // [rsp+BCh] [rbp-44h] BYREF
  unsigned __int64 v656; // [rsp+C0h] [rbp-40h]
  __int64 v657; // [rsp+C8h] [rbp-38h]
  int v658; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v659; // [rsp+D8h] [rbp-28h]
  int v660; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v661; // [rsp+E4h] [rbp-1Ch]
  int v662; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v663; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v664; // [rsp+F8h] [rbp-8h]
  char v665; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 v666; // [rsp+108h] [rbp+8h]
  __int128 v667; // [rsp+110h] [rbp+10h]
  __int64 v668; // [rsp+120h] [rbp+20h]
  int v669; // [rsp+128h] [rbp+28h]
  int v670; // [rsp+138h] [rbp+38h]
  __int128 v671; // [rsp+140h] [rbp+40h] BYREF
  __int64 v672; // [rsp+150h] [rbp+50h]
  int v673; // [rsp+158h] [rbp+58h]
  __int128 v674; // [rsp+160h] [rbp+60h] BYREF
  __int64 v675; // [rsp+170h] [rbp+70h]
  int v676; // [rsp+178h] [rbp+78h]
  __int128 v677; // [rsp+180h] [rbp+80h] BYREF
  __int64 v678; // [rsp+190h] [rbp+90h]
  int v679; // [rsp+198h] [rbp+98h]
  char v680[16]; // [rsp+1A0h] [rbp+A0h] BYREF
  char v681[24]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int64 v685; // [rsp+228h] [rbp+128h]
  unsigned int v686; // [rsp+230h] [rbp+130h]
  unsigned int v687; // [rsp+230h] [rbp+130h]
  unsigned int *v688; // [rsp+230h] [rbp+130h]
  unsigned int v689; // [rsp+230h] [rbp+130h]

  v685 = a4;
  v5 = a4;
  v6 = (int)a3;
  v7 = a1;
  if ( !*(_DWORD *)(a1 + 124) && *(_QWORD *)(a2 + 8) == *(_QWORD *)a2 )
  {
    v8 = *(_DWORD *)(a1 + 24);
    if ( v8 == *(_DWORD *)(a1 + 28) && (_DWORD)a4 - *(_DWORD *)(a1 + 8) == v8 && a5 > 0x400 )
      ZSTD_initStats_ultra(a1, a2, v6, a4, a5);
  }
  v9 = *(_DWORD *)(v7 + 204);
  v10 = v5 + a5;
  v11 = *(_QWORD *)(v7 + 8) + *(unsigned int *)(v7 + 24);
  v12 = 4095;
  v657 = v7 + 72;
  v636 = v5 + a5;
  v666 = v5 + a5 - 8;
  if ( v9 < 0xFFF )
    v12 = v9;
  v661 = v12;
  v654 = (*(_DWORD *)(v7 + 200) != 3) + 3;
  v660 = *(_DWORD *)(v7 + 36);
  v652 = *(_DWORD **)(v7 + 112);
  v646 = *(_DWORD **)(v7 + 104);
  ZSTD_rescaleFreqs(v7 + 72, v5, a5, 2);
  v13 = v5 + (v5 == v11);
  v647 = v13;
  if ( v13 < v5 + a5 - 8 )
  {
    v14 = v668;
    v662 = v669;
    do
    {
      v15 = *(unsigned int *)(v7 + 36);
      v16 = *(_QWORD *)(v7 + 8);
      v18 = v13 - v5;
      v17 = (_DWORD)v13 == (_DWORD)v5;
      v19 = *(_DWORD *)(v7 + 200);
      v20 = v17;
      v649 = v18;
      v639 = v17;
      if ( v13 < v16 + v15 )
        goto LABEL_755;
      v21 = v13 - v16;
      if ( (unsigned int)v15 < (int)v13 - (int)v16 )
      {
        do
          LODWORD(v15) = ZSTD_insertBt1(v7, (int)v16 + (int)v15, v10, v19, 0) + v15;
        while ( (unsigned int)v15 < v21 );
        v20 = v639;
        v13 = v647;
      }
      v22 = *(_QWORD *)(v7 + 48);
      *(_DWORD *)(v7 + 36) = v21;
      v23 = *(unsigned int *)(v7 + 192);
      if ( v19 != 3 )
      {
        v24 = 4095;
        if ( v19 != 5 )
        {
          v25 = *(_DWORD *)(v7 + 204);
          if ( (unsigned int)(v19 - 6) <= 1 )
          {
            if ( v25 < 0xFFF )
              v24 = *(_DWORD *)(v7 + 204);
            v26 = v13 - *(_QWORD *)(v7 + 8);
            v643 = *(char **)(v7 + 8);
            v641 = v26;
            v27 = ZSTD_hash6Ptr(v13, v23, v22);
            v29 = (unsigned int *)(v28 + 4 * v27);
            v30 = *(_DWORD *)(v7 + 28);
            v31 = *(_DWORD *)(v7 + 188) - 1;
            v32 = *(_DWORD **)(v7 + 64);
            v33 = *v29;
            v640 = v34;
            v35 = 1 << v31;
            v36 = 0;
            v37 = 0;
            v650 = v32;
            v38 = v35 - 1;
            v637 = 0;
            v634 = v38;
            if ( v38 < v26 )
              v37 = v26 - v38;
            v635 = v37;
            v39 = 1 << *(_DWORD *)(v7 + 184);
            v40 = v26 - v39;
            v41 = 1;
            if ( v26 - v30 <= v39 )
              v40 = v30;
            if ( *(_DWORD *)(v7 + 32) )
              v40 = v30;
            if ( v40 )
              v41 = v40;
            v42 = *(_DWORD *)(v7 + 196);
            v642 = v41;
            v686 = 0;
            v43 = &v32[2 * (v26 & v38)];
            v638 = v43 + 1;
            v633 = v26 + 9;
            v645 = 1 << v42;
            v44 = v26 - *(_DWORD *)(a1 + 24);
            v45 = (unsigned int)(v654 - 1);
            v46 = a3;
            v656 = v45;
            v47 = v639;
            v48 = v639 + 3;
            v49 = &a3[v639];
            while ( 1 )
            {
              if ( v47 == 3 )
                v50 = *v46 - 1;
              else
                v50 = *v49;
              v51 = 0;
              if ( v50 - 1 >= v44 )
                goto LABEL_53;
              MINMATCH = ZSTD_readMINMATCH(v647, 4, 0, -(__int64)v50);
              if ( MINMATCH == *(_DWORD *)(v54 + v53) )
                break;
LABEL_52:
              v36 = v686;
LABEL_53:
              if ( v51 > v45 )
              {
                v45 = v51;
                v62 = v36++;
                v63 = &v646[2 * v62];
                v63[1] = v51;
                *v63 = v47 - v639;
                v686 = v36;
                if ( v51 > v24 || v51 + v647 == v636 )
                  goto LABEL_84;
              }
              v46 = a3;
              ++v47;
              ++v49;
              if ( v47 >= v48 )
              {
                v67 = v645;
                *v29 = v641;
                while ( v67 )
                {
                  --v67;
                  if ( v33 < v642 )
                    break;
                  v68 = v637;
                  v69 = v647;
                  if ( v640 < v637 )
                    v68 = v640;
                  v70 = v636;
                  v71 = &v650[2 * (v33 & v634)];
                  v72 = &v643[v33];
                  v73 = (_QWORD *)((char *)v68 + v647);
                  v74 = v636 - 7;
                  v75 = (char *)v68 + v647;
                  v76 = (_QWORD *)((char *)v68 + (_QWORD)v72);
                  if ( (unsigned __int64)v68 + v647 >= v636 - 7 )
                    goto LABEL_68;
                  if ( *v76 != *v73 )
                  {
                    v77 = (unsigned int)ZSTD_NbCommonBytes(*v76 ^ *v73, v73, v76, v68);
                    goto LABEL_78;
                  }
                  ++v73;
                  ++v76;
                  if ( (unsigned __int64)v73 >= v74 )
                  {
LABEL_68:
                    if ( (unsigned __int64)v73 < v636 - 3 && *(_DWORD *)v76 == *(_DWORD *)v73 )
                    {
                      v73 = (_QWORD *)((char *)v73 + 4);
                      v76 = (_QWORD *)((char *)v76 + 4);
                    }
                    if ( (unsigned __int64)v73 < v636 - 1 && *(_WORD *)v76 == *(_WORD *)v73 )
                    {
                      v73 = (_QWORD *)((char *)v73 + 2);
                      v76 = (_QWORD *)((char *)v76 + 2);
                    }
                    if ( (unsigned __int64)v73 < v636 && *(_BYTE *)v76 == *(_BYTE *)v73 )
                      v73 = (_QWORD *)((char *)v73 + 1);
                    v77 = (char *)v73 - v75;
                  }
                  else
                  {
                    while ( *v76 == *v73 )
                    {
                      ++v73;
                      ++v76;
                      if ( (unsigned __int64)v73 >= v74 )
                        goto LABEL_68;
                    }
                    v84 = ZSTD_NbCommonBytes(*v76 ^ *v73, v73, v76, v68);
                    v77 = v85 - (_QWORD)v75 + v84;
                  }
LABEL_78:
                  v78 = (unsigned __int64)v68 + v77;
                  if ( v78 > v45 )
                  {
                    if ( v78 > v633 - v33 )
                      v633 = v33 + v78;
                    v45 = v78;
                    v79 = v646;
                    v80 = v641 - v33 + 2;
                    v646[2 * v686 + 1] = v78;
                    v79[2 * v686++] = v80;
                    if ( v78 > 0x1000 || v78 + v69 == v70 )
                      break;
                  }
                  if ( (unsigned __int8)v72[v78] >= *(_BYTE *)(v78 + v69) )
                  {
                    v637 = (_DWORD *)v78;
                    *v638 = v33;
                    if ( v33 <= v635 )
                    {
                      v81 = &v635;
                      goto LABEL_83;
                    }
                    v33 = *v71;
                    v638 = v71;
                  }
                  else
                  {
                    *v43 = v33;
                    v640 = (_DWORD *)v78;
                    if ( v33 <= v635 )
                    {
                      v43 = &v635;
                      break;
                    }
                    v33 = v71[1];
                    v43 = v71 + 1;
                  }
                }
LABEL_82:
                v81 = v638;
LABEL_83:
                *v81 = 0;
                v82 = v633 - 8;
                *v43 = 0;
                *(_DWORD *)(a1 + 36) = v82;
LABEL_84:
                v83 = v686;
                goto LABEL_333;
              }
            }
            v55 = (_QWORD *)(v53 + 4);
            v56 = v53 + 4;
            v57 = v636;
            v58 = (_QWORD *)(v54 + v56);
            v59 = v55;
            v60 = v636 - 7;
            if ( (unsigned __int64)v55 < v636 - 7 )
            {
              if ( *v58 != *v55 )
              {
                v61 = ZSTD_NbCommonBytes(*v58 ^ *v55, v55, v58, v55);
LABEL_51:
                v51 = v61 + 4;
                goto LABEL_52;
              }
              ++v55;
              ++v58;
              if ( (unsigned __int64)v55 < v60 )
              {
                while ( *v58 == *v55 )
                {
                  ++v55;
                  ++v58;
                  if ( (unsigned __int64)v55 >= v60 )
                    goto LABEL_40;
                }
                v64 = ZSTD_NbCommonBytes(*v58 ^ *v55, v55, v58, v59);
                v61 = v65 - v66 + v64;
                goto LABEL_51;
              }
LABEL_40:
              v57 = v636;
            }
            if ( (unsigned __int64)v55 < v57 - 3 && *(_DWORD *)v58 == *(_DWORD *)v55 )
            {
              v55 = (_QWORD *)((char *)v55 + 4);
              v58 = (_QWORD *)((char *)v58 + 4);
            }
            if ( (unsigned __int64)v55 < v57 - 1 && *(_WORD *)v58 == *(_WORD *)v55 )
            {
              v55 = (_QWORD *)((char *)v55 + 2);
              v58 = (_QWORD *)((char *)v58 + 2);
            }
            if ( (unsigned __int64)v55 < v57 && *(_BYTE *)v58 == *(_BYTE *)v55 )
              LODWORD(v55) = (_DWORD)v55 + 1;
            v61 = (_DWORD)v55 - (_DWORD)v59;
            goto LABEL_51;
          }
          if ( v25 < 0xFFF )
            v24 = *(_DWORD *)(v7 + 204);
          v86 = v13 - *(_QWORD *)(v7 + 8);
          v643 = *(char **)(v7 + 8);
          v641 = v86;
          v87 = ZSTD_hash4Ptr(v13, v23, v22);
          v89 = (unsigned int *)(v88 + 4 * v87);
          v90 = *(_DWORD *)(v7 + 28);
          v91 = *(_DWORD *)(v7 + 188) - 1;
          v92 = *(_DWORD **)(v7 + 64);
          v93 = *v89;
          v640 = v94;
          v95 = 1 << v91;
          v96 = 0;
          v97 = 0;
          v650 = v92;
          v98 = v95 - 1;
          v637 = 0;
          v634 = v98;
          if ( v98 < v86 )
            v97 = v86 - v98;
          v635 = v97;
          v99 = 1 << *(_DWORD *)(v7 + 184);
          v100 = v86 - v99;
          v101 = 1;
          if ( v86 - v90 <= v99 )
            v100 = v90;
          if ( *(_DWORD *)(v7 + 32) )
            v100 = v90;
          if ( v100 )
            v101 = v100;
          v102 = *(_DWORD *)(v7 + 196);
          v642 = v101;
          v686 = 0;
          v43 = &v92[2 * (v86 & v98)];
          v638 = v43 + 1;
          v633 = v86 + 9;
          v645 = 1 << v102;
          v103 = v86 - *(_DWORD *)(a1 + 24);
          v104 = (unsigned int)(v654 - 1);
          v105 = a3;
          v656 = v104;
          v106 = v639;
          v107 = v639 + 3;
          v108 = &a3[v639];
          while ( 1 )
          {
            if ( v106 == 3 )
              v109 = *v105 - 1;
            else
              v109 = *v108;
            v110 = 0;
            if ( v109 - 1 >= v103 )
              goto LABEL_130;
            v111 = ZSTD_readMINMATCH(v647, 4, 0, -(__int64)v109);
            if ( v111 == *(_DWORD *)(v113 + v112) )
              break;
LABEL_129:
            v96 = v686;
LABEL_130:
            if ( v110 > v104 )
            {
              v104 = v110;
              v121 = v96++;
              v122 = &v646[2 * v121];
              v122[1] = v110;
              *v122 = v106 - v639;
              v686 = v96;
              if ( v110 > v24 || v110 + v647 == v636 )
                goto LABEL_84;
            }
            v105 = a3;
            ++v106;
            ++v108;
            if ( v106 >= v107 )
            {
              v126 = v645;
              *v89 = v641;
              if ( !v126 )
                goto LABEL_82;
              while ( 2 )
              {
                --v126;
                if ( v93 < v642 )
                  goto LABEL_82;
                v127 = v637;
                v128 = v647;
                if ( v640 < v637 )
                  v127 = v640;
                v129 = v636;
                v130 = &v650[2 * (v93 & v634)];
                v131 = &v643[v93];
                v132 = (_QWORD *)((char *)v127 + v647);
                v133 = v636 - 7;
                v134 = (char *)v127 + v647;
                v135 = (_QWORD *)((char *)v127 + (_QWORD)v131);
                if ( (unsigned __int64)v127 + v647 < v636 - 7 )
                {
                  if ( *v135 != *v132 )
                  {
                    v136 = (unsigned int)ZSTD_NbCommonBytes(*v135 ^ *v132, v132, v135, v127);
LABEL_155:
                    v137 = (unsigned __int64)v127 + v136;
                    if ( v137 > v104 )
                    {
                      if ( v137 > v633 - v93 )
                        v633 = v93 + v137;
                      v104 = v137;
                      v138 = v646;
                      v139 = v641 - v93 + 2;
                      v646[2 * v686 + 1] = v137;
                      v138[2 * v686++] = v139;
                      if ( v137 > 0x1000 || v137 + v128 == v129 )
                        goto LABEL_82;
                    }
                    if ( (unsigned __int8)v131[v137] >= *(_BYTE *)(v137 + v128) )
                    {
                      v637 = (_DWORD *)v137;
                      *v638 = v93;
                      if ( v93 <= v635 )
                      {
                        v81 = &v634;
                        goto LABEL_83;
                      }
                      v93 = *v130;
                      v638 = v130;
                    }
                    else
                    {
                      *v43 = v93;
                      v640 = (_DWORD *)v137;
                      if ( v93 <= v635 )
                      {
                        v43 = &v634;
                        goto LABEL_82;
                      }
                      v93 = v130[1];
                      v43 = v130 + 1;
                    }
                    if ( !v126 )
                      goto LABEL_82;
                    continue;
                  }
                  ++v132;
                  ++v135;
                  if ( (unsigned __int64)v132 < v133 )
                  {
                    while ( *v135 == *v132 )
                    {
                      ++v132;
                      ++v135;
                      if ( (unsigned __int64)v132 >= v133 )
                        goto LABEL_145;
                    }
                    v140 = ZSTD_NbCommonBytes(*v135 ^ *v132, v132, v135, v127);
                    v136 = v141 - (_QWORD)v134 + v140;
                    goto LABEL_155;
                  }
                }
                break;
              }
LABEL_145:
              if ( (unsigned __int64)v132 < v636 - 3 && *(_DWORD *)v135 == *(_DWORD *)v132 )
              {
                v132 = (_QWORD *)((char *)v132 + 4);
                v135 = (_QWORD *)((char *)v135 + 4);
              }
              if ( (unsigned __int64)v132 < v636 - 1 && *(_WORD *)v135 == *(_WORD *)v132 )
              {
                v132 = (_QWORD *)((char *)v132 + 2);
                v135 = (_QWORD *)((char *)v135 + 2);
              }
              if ( (unsigned __int64)v132 < v636 && *(_BYTE *)v135 == *(_BYTE *)v132 )
                v132 = (_QWORD *)((char *)v132 + 1);
              v136 = (char *)v132 - v134;
              goto LABEL_155;
            }
          }
          v114 = (_QWORD *)(v112 + 4);
          v115 = v112 + 4;
          v116 = v636;
          v117 = (_QWORD *)(v113 + v115);
          v118 = v114;
          v119 = v636 - 7;
          if ( (unsigned __int64)v114 < v636 - 7 )
          {
            if ( *v117 != *v114 )
            {
              v120 = ZSTD_NbCommonBytes(*v117 ^ *v114, v114, v117, v114);
LABEL_128:
              v110 = v120 + 4;
              goto LABEL_129;
            }
            ++v114;
            ++v117;
            if ( (unsigned __int64)v114 < v119 )
            {
              while ( *v117 == *v114 )
              {
                ++v114;
                ++v117;
                if ( (unsigned __int64)v114 >= v119 )
                  goto LABEL_117;
              }
              v123 = ZSTD_NbCommonBytes(*v117 ^ *v114, v114, v117, v118);
              v120 = v124 - v125 + v123;
              goto LABEL_128;
            }
LABEL_117:
            v116 = v636;
          }
          if ( (unsigned __int64)v114 < v116 - 3 && *(_DWORD *)v117 == *(_DWORD *)v114 )
          {
            v114 = (_QWORD *)((char *)v114 + 4);
            v117 = (_QWORD *)((char *)v117 + 4);
          }
          if ( (unsigned __int64)v114 < v116 - 1 && *(_WORD *)v117 == *(_WORD *)v114 )
          {
            v114 = (_QWORD *)((char *)v114 + 2);
            v117 = (_QWORD *)((char *)v117 + 2);
          }
          if ( (unsigned __int64)v114 < v116 && *(_BYTE *)v117 == *(_BYTE *)v114 )
            LODWORD(v114) = (_DWORD)v114 + 1;
          v120 = (_DWORD)v114 - (_DWORD)v118;
          goto LABEL_128;
        }
        if ( *(_DWORD *)(v7 + 204) < 0xFFFu )
          v24 = *(_DWORD *)(v7 + 204);
        v142 = v13 - *(_QWORD *)(v7 + 8);
        v643 = *(char **)(v7 + 8);
        v641 = v142;
        v143 = ZSTD_hash5Ptr(v13, v23, v22);
        v145 = (unsigned int *)(v144 + 4 * v143);
        v146 = *(_DWORD *)(v7 + 28);
        v147 = *(_DWORD *)(v7 + 188) - 1;
        v148 = *(_DWORD **)(v7 + 64);
        v149 = *v145;
        v640 = v150;
        v151 = 1 << v147;
        v152 = 0;
        v153 = 0;
        v650 = v148;
        v154 = v151 - 1;
        v637 = 0;
        v634 = v154;
        if ( v154 < v142 )
          v153 = v142 - v154;
        v635 = v153;
        v155 = 1 << *(_DWORD *)(v7 + 184);
        v156 = v142 - v155;
        v157 = 1;
        if ( v142 - v146 <= v155 )
          v156 = v146;
        if ( *(_DWORD *)(v7 + 32) )
          v156 = v146;
        if ( v156 )
          v157 = v156;
        v158 = *(_DWORD *)(v7 + 196);
        v642 = v157;
        v686 = 0;
        v43 = &v148[2 * (v142 & v154)];
        v638 = v43 + 1;
        v633 = v142 + 9;
        v645 = 1 << v158;
        v159 = v142 - *(_DWORD *)(a1 + 24);
        v160 = (unsigned int)(v654 - 1);
        v161 = a3;
        v656 = v160;
        v162 = v639;
        v163 = v639 + 3;
        v164 = &a3[v639];
        while ( 1 )
        {
          if ( v162 == 3 )
            v165 = *v161 - 1;
          else
            v165 = *v164;
          v166 = 0;
          if ( v165 - 1 >= v159 )
            goto LABEL_205;
          v167 = ZSTD_readMINMATCH(v647, 4, 0, -(__int64)v165);
          if ( v167 == *(_DWORD *)(v169 + v168) )
            break;
LABEL_204:
          v152 = v686;
LABEL_205:
          if ( v166 > v160 )
          {
            v160 = v166;
            v177 = v152++;
            v178 = &v646[2 * v177];
            v178[1] = v166;
            *v178 = v162 - v639;
            v686 = v152;
            if ( v166 > v24 || v166 + v647 == v636 )
              goto LABEL_84;
          }
          v161 = a3;
          ++v162;
          ++v164;
          if ( v162 >= v163 )
          {
            v182 = v645;
            *v145 = v641;
            if ( !v182 )
              goto LABEL_82;
            while ( 2 )
            {
              --v182;
              if ( v149 < v642 )
                goto LABEL_82;
              v183 = v637;
              v184 = v647;
              if ( v640 < v637 )
                v183 = v640;
              v185 = v636;
              v186 = &v650[2 * (v149 & v634)];
              v187 = &v643[v149];
              v188 = (_QWORD *)((char *)v183 + v647);
              v189 = v636 - 7;
              v190 = (char *)v183 + v647;
              v191 = (_QWORD *)((char *)v183 + (_QWORD)v187);
              if ( (unsigned __int64)v183 + v647 < v636 - 7 )
              {
                if ( *v191 != *v188 )
                {
                  v192 = (unsigned int)ZSTD_NbCommonBytes(*v191 ^ *v188, v188, v191, v183);
LABEL_230:
                  v193 = (unsigned __int64)v183 + v192;
                  if ( v193 > v160 )
                  {
                    if ( v193 > v633 - v149 )
                      v633 = v193 + v149;
                    v160 = v193;
                    v194 = v646;
                    v195 = v641 - v149 + 2;
                    v646[2 * v686 + 1] = v193;
                    v194[2 * v686++] = v195;
                    if ( v193 > 0x1000 || v193 + v184 == v185 )
                      goto LABEL_82;
                  }
                  if ( (unsigned __int8)v187[v193] >= *(_BYTE *)(v193 + v184) )
                  {
                    v637 = (_DWORD *)v193;
                    *v638 = v149;
                    if ( v149 <= v635 )
                    {
                      v81 = &v648;
                      goto LABEL_83;
                    }
                    v149 = *v186;
                    v638 = v186;
                  }
                  else
                  {
                    *v43 = v149;
                    v640 = (_DWORD *)v193;
                    if ( v149 <= v635 )
                    {
                      v43 = &v648;
                      goto LABEL_82;
                    }
                    v149 = v186[1];
                    v43 = v186 + 1;
                  }
                  if ( !v182 )
                    goto LABEL_82;
                  continue;
                }
                ++v188;
                ++v191;
                if ( (unsigned __int64)v188 < v189 )
                {
                  while ( *v191 == *v188 )
                  {
                    ++v188;
                    ++v191;
                    if ( (unsigned __int64)v188 >= v189 )
                      goto LABEL_220;
                  }
                  v196 = ZSTD_NbCommonBytes(*v191 ^ *v188, v188, v191, v183);
                  v192 = v197 - (_QWORD)v190 + v196;
                  goto LABEL_230;
                }
              }
              break;
            }
LABEL_220:
            if ( (unsigned __int64)v188 < v636 - 3 && *(_DWORD *)v191 == *(_DWORD *)v188 )
            {
              v188 = (_QWORD *)((char *)v188 + 4);
              v191 = (_QWORD *)((char *)v191 + 4);
            }
            if ( (unsigned __int64)v188 < v636 - 1 && *(_WORD *)v191 == *(_WORD *)v188 )
            {
              v188 = (_QWORD *)((char *)v188 + 2);
              v191 = (_QWORD *)((char *)v191 + 2);
            }
            if ( (unsigned __int64)v188 < v636 && *(_BYTE *)v191 == *(_BYTE *)v188 )
              v188 = (_QWORD *)((char *)v188 + 1);
            v192 = (char *)v188 - v190;
            goto LABEL_230;
          }
        }
        v170 = (_QWORD *)(v168 + 4);
        v171 = v168 + 4;
        v172 = v636;
        v173 = (_QWORD *)(v169 + v171);
        v174 = v170;
        v175 = v636 - 7;
        if ( (unsigned __int64)v170 < v636 - 7 )
        {
          if ( *v173 != *v170 )
          {
            v176 = ZSTD_NbCommonBytes(*v173 ^ *v170, v170, v173, v170);
LABEL_203:
            v166 = v176 + 4;
            goto LABEL_204;
          }
          ++v170;
          ++v173;
          if ( (unsigned __int64)v170 < v175 )
          {
            while ( *v173 == *v170 )
            {
              ++v170;
              ++v173;
              if ( (unsigned __int64)v170 >= v175 )
                goto LABEL_192;
            }
            v179 = ZSTD_NbCommonBytes(*v173 ^ *v170, v170, v173, v174);
            v176 = v180 - v181 + v179;
            goto LABEL_203;
          }
LABEL_192:
          v172 = v636;
        }
        if ( (unsigned __int64)v170 < v172 - 3 && *(_DWORD *)v173 == *(_DWORD *)v170 )
        {
          v170 = (_QWORD *)((char *)v170 + 4);
          v173 = (_QWORD *)((char *)v173 + 4);
        }
        if ( (unsigned __int64)v170 < v172 - 1 && *(_WORD *)v173 == *(_WORD *)v170 )
        {
          v170 = (_QWORD *)((char *)v170 + 2);
          v173 = (_QWORD *)((char *)v173 + 2);
        }
        if ( (unsigned __int64)v170 < v172 && *(_BYTE *)v173 == *(_BYTE *)v170 )
          LODWORD(v170) = (_DWORD)v170 + 1;
        v176 = (_DWORD)v170 - (_DWORD)v174;
        goto LABEL_203;
      }
      v198 = 4095;
      if ( *(_DWORD *)(v7 + 204) < 0xFFFu )
        v198 = *(_DWORD *)(v7 + 204);
      v199 = v13 - *(_QWORD *)(v7 + 8);
      v637 = *(_DWORD **)(v7 + 8);
      v634 = v199;
      v200 = ZSTD_hash4Ptr(v13, v23, v22);
      v203 = (unsigned int *)(v202 + 4 * v200);
      v204 = *v203;
      v643 = v205;
      v206 = *(_DWORD *)(a1 + 28);
      v207 = *(_DWORD **)(a1 + 64);
      v208 = 0;
      v209 = (1 << (*(_DWORD *)(a1 + 188) - 1)) - 1;
      v650 = v207;
      v645 = v209;
      v651 = 0;
      if ( v209 < v201 )
        v208 = v201 - v209;
      v641 = v208;
      v210 = 1 << *(_DWORD *)(a1 + 184);
      v211 = v201 - v210;
      v212 = 1;
      if ( v201 - v206 <= v210 )
        v211 = v206;
      if ( *(_DWORD *)(a1 + 32) )
        v211 = v206;
      if ( v211 )
        v212 = v211;
      v213 = *(_DWORD *)(a1 + 196);
      v644 = v212;
      v687 = 0;
      v214 = v20 + 3;
      v215 = 0;
      v638 = &v207[2 * (v201 & v209)];
      v640 = v638 + 1;
      v633 = v201 + 9;
      v648 = 1 << v213;
      v216 = v201 - *(_DWORD *)(a1 + 24);
      v217 = (unsigned int)(v654 - 1);
      v218 = a3;
      v656 = v217;
      v219 = v639;
      v220 = &a3[v639];
      while ( 1 )
      {
        if ( v219 == 3 )
          v221 = *v218 - 1;
        else
          v221 = *v220;
        v222 = 0;
        if ( v221 - 1 >= v216 )
          goto LABEL_279;
        v670 = 1;
        v223 = ZSTD_readMINMATCH(v647, 3, (unsigned int)(*(_DWORD *)(v647 - v221) << 8), 0);
        if ( v223 != v226 )
        {
          v215 = v687;
LABEL_279:
          v230 = v636;
          goto LABEL_280;
        }
        v227 = (_QWORD *)(v224 + 3);
        v228 = v224 + 3;
        v229 = (_QWORD *)(v225 + v224 + 3);
        v230 = v636;
        v231 = v636 - 7;
        if ( v224 + 3 >= v636 - 7 )
          goto LABEL_760;
        if ( *v229 != *v227 )
        {
          v232 = ZSTD_NbCommonBytes(*v229 ^ *v227, v227, v229, v228);
          v215 = v687;
          v222 = v232 + 3;
          goto LABEL_280;
        }
        v227 = (_QWORD *)(v224 + 11);
        ++v229;
        if ( v224 + 11 >= v231 )
        {
LABEL_760:
        {
LABEL_267:
          if ( (unsigned __int64)v227 < v636 - 3 && *(_DWORD *)v229 == *(_DWORD *)v227 )
          {
            v227 = (_QWORD *)((char *)v227 + 4);
            v229 = (_QWORD *)((char *)v229 + 4);
          }
        }
          if ( (unsigned __int64)v227 < v636 - 1 && *(_WORD *)v229 == *(_WORD *)v227 )
          {
            v227 = (_QWORD *)((char *)v227 + 2);
            v229 = (_QWORD *)((char *)v229 + 2);
          }
          if ( (unsigned __int64)v227 < v636 && *(_BYTE *)v229 == *(_BYTE *)v227 )
            LODWORD(v227) = (_DWORD)v227 + 1;
          v215 = v687;
          v222 = (_DWORD)v227 - v224;
        }
        else
        {
          while ( *v229 == *v227 )
          {
            ++v227;
            ++v229;
            if ( (unsigned __int64)v227 >= v231 )
              goto LABEL_267;
          }
          v233 = ZSTD_NbCommonBytes(*v229 ^ *v227, v227, v229, v228);
          v215 = v687;
          v222 = v234 - v235 + v233 + 3;
        }
LABEL_280:
        if ( v222 > v217 )
        {
          v217 = v222;
          v236 = v215++;
          v237 = &v646[2 * v236];
          v237[1] = v222;
          *v237 = v219 - v639;
          v687 = v215;
          if ( v222 > v198 || v222 + v647 == v230 )
          {
            v83 = v215;
            goto LABEL_333;
          }
        }
        ++v219;
        ++v220;
        if ( v219 >= v214 )
          break;
        v218 = a3;
      }
      if ( v217 >= 3 )
      {
        v240 = v634;
LABEL_291:
        v241 = v644;
LABEL_292:
        v247 = v687;
        goto LABEL_293;
      }
      v238 = v647;
      FirstIndexHash3 = ZSTD_insertAndFindFirstIndexHash3(a1, &v660, v647);
      v240 = v634;
      v241 = v644;
      if ( FirstIndexHash3 < v644 || v634 - FirstIndexHash3 >= 0x40000 )
        goto LABEL_292;
      v242 = v636;
      v243 = ZSTD_count(v238, (char *)v637 + FirstIndexHash3, v636);
      if ( v243 < 3 )
        goto LABEL_291;
      v245 = v646;
      v246 = v244 + 2;
      v247 = 1;
      v217 = v243;
      v687 = 1;
      *v646 = v246;
      v245[1] = v243;
      if ( v243 > v198 || v243 + v238 == v242 )
      {
        v248 = v240 + 1;
        goto LABEL_332;
      }
      v241 = v644;
LABEL_293:
      v249 = v648;
      *v203 = v240;
      v250 = v633;
      if ( v249 )
      {
        while ( 2 )
        {
          --v249;
          if ( v204 < v241 )
            goto LABEL_330;
          v251 = (_DWORD *)v651;
          v252 = v647;
          if ( (unsigned __int64)v643 < v651 )
            v251 = v643;
          v253 = v636;
          v254 = &v650[2 * (v204 & v645)];
          v255 = (char *)v637 + v204;
          v256 = (_QWORD *)((char *)v251 + v647);
          v257 = v636 - 7;
          v258 = (_QWORD *)((char *)v251 + (_QWORD)v255);
          if ( (unsigned __int64)v251 + v647 < v636 - 7 )
          {
            if ( *v258 != *v256 )
            {
              v259 = (unsigned int)ZSTD_NbCommonBytes(*v258 ^ *v256, v256, v258, v251);
LABEL_314:
              v260 = (unsigned __int64)v251 + v259;
              if ( v260 <= v217 )
              {
                v247 = v687;
              }
              else
              {
                if ( v260 > v250 - v204 )
                  v250 = v204 + v260;
                v217 = v260;
                v261 = v646;
                v262 = v634 - v204 + 2;
                v646[2 * v687 + 1] = v260;
                v247 = v687 + 1;
                v261[2 * v687++] = v262;
                if ( v260 > 0x1000 || v260 + v252 == v253 )
                  goto LABEL_330;
              }
              if ( (unsigned __int8)v255[v260] >= *(_BYTE *)(v260 + v252) )
              {
                v651 = v260;
                *v640 = v204;
                if ( v204 <= v641 )
                {
                  v640 = &v633;
                  goto LABEL_330;
                }
                v204 = *v254;
                v640 = v254;
              }
              else
              {
                v643 = (char *)v260;
                *v638 = v204;
                if ( v204 <= v641 )
                {
                  v266 = &v633;
                  goto LABEL_331;
                }
                v204 = v254[1];
                v638 = v254 + 1;
              }
              if ( !v249 )
                goto LABEL_330;
              v241 = v644;
              continue;
            }
            ++v256;
            ++v258;
            if ( (unsigned __int64)v256 < v257 )
            {
              while ( *v258 == *v256 )
              {
                ++v256;
                ++v258;
                if ( (unsigned __int64)v256 >= v257 )
                  goto LABEL_304;
              }
              v263 = ZSTD_NbCommonBytes(*v258 ^ *v256, v256, v258, v251);
              v259 = v264 - v265 + v263;
              goto LABEL_314;
            }
          }
          break;
        }
LABEL_304:
        if ( (unsigned __int64)v256 < v636 - 3 && *(_DWORD *)v258 == *(_DWORD *)v256 )
        {
          v256 = (_QWORD *)((char *)v256 + 4);
          v258 = (_QWORD *)((char *)v258 + 4);
        }
        if ( (unsigned __int64)v256 < v636 - 1 && *(_WORD *)v258 == *(_WORD *)v256 )
        {
          v256 = (_QWORD *)((char *)v256 + 2);
          v258 = (_QWORD *)((char *)v258 + 2);
        }
        if ( (unsigned __int64)v256 < v636 && *(_BYTE *)v258 == *(_BYTE *)v256 )
          v256 = (_QWORD *)((char *)v256 + 1);
        v259 = (char *)v256 - ((char *)v251 + v647);
        goto LABEL_314;
      }
LABEL_330:
      v266 = v638;
LABEL_331:
      *v640 = 0;
      *v266 = 0;
      v248 = v250 - 8;
LABEL_332:
      v83 = v247;
      *(_DWORD *)(a1 + 36) = v248;
LABEL_333:
      if ( !v83 )
      {
        v13 = v647;
LABEL_755:
        v647 = ++v13;
        goto LABEL_756;
      }
      v267 = v652;
      v268 = a3;
      v269 = v649;
      v270 = v649;
      v271 = v657;
      v272 = v657;
      v652[4] = *a3;
      v267[5] = a3[1];
      v267[6] = a3[2];
      v267[2] = 0;
      v267[3] = v269;
      v273 = ZSTD_literalsContribution(v685, v270, v272, 2);
      v274 = v652;
      v275 = v646;
      *v652 = v273;
      if ( v275[2 * v83 - 1] > v661 )
      {
        *(_QWORD *)((char *)&v667 + 4) = *(_QWORD *)&v275[2 * v83 - 2];
        HIDWORD(v667) = v269;
LABEL_723:
        v589 = 0;
        v592 = 0;
        goto LABEL_724;
      }
      ZSTD_litLengthPrice(0, v271, 2);
      v276 = v656;
      v277 = v656 + 1;
      v278 = v652 + 7;
      do
      {
        *v278 = 0x40000000;
        v278 += 7;
        --v276;
      }
      while ( v276 );
      v279 = (unsigned int *)v83;
      v280 = v275;
      v638 = (unsigned int *)v83;
      v688 = v275;
      do
      {
        v281 = v280[1];
        updated = ZSTD_updateRep(v681, v268, *v280, v639);
        v285 = *(_QWORD *)updated;
        v286 = *(_DWORD *)(updated + 8);
        if ( v277 > v281 )
        {
          v299 = v652;
        }
        else
        {
          v287 = v657;
          do
          {
            _BitScanReverse((unsigned int *)&v288, v283 + 1);
            v289 = v277 - 3;
            if ( *(_DWORD *)(v287 + 80) == 1 )
            {
              _BitScanReverse(&v290, v277 - 2);
              v291 = v284 + ((v277 - 2) << 8 >> v290) + (((_DWORD)v288 + v290 + 16) << 8);
            }
            else
            {
              v292 = *(_DWORD *)(*(_QWORD *)(v287 + 24) + 4 * v288) + 1;
              _BitScanReverse(&v293, v292);
              v294 = *(_DWORD *)(v287 + 76) + (((_DWORD)v288 - v293) << 8) - (v292 << 8 >> v293);
              if ( (unsigned int)v289 <= 0x7F )
              {
                _mm_lfence();
                v296 = *((unsigned __int8 *)&qword_1803EF770[8] + v289);
              }
              else
              {
                _BitScanReverse(&v295, v289);
                LODWORD(v663) = 0;
                v296 = v295 + 36;
              }
              LODWORD(v664) = 0;
              v297 = *(_DWORD *)(*(_QWORD *)(v287 + 16) + 4 * v296) + 1;
              _BitScanReverse(&v298, v297);
              v291 = v294
                   + v284
                   + *(_DWORD *)(v287 + 72)
                   + ((*((_DWORD *)&qword_1803EF640[10] + v296) - v298) << 8)
                   - (v297 << 8 >> v298)
                   + 51;
            }
            v299 = v652;
            v300 = 7LL * v277;
            v652[v300 + 2] = v277++;
            *(_QWORD *)&v299[v300 + 4] = v285;
            v299[v300 + 1] = v283;
            v299[v300 + 3] = v269;
            v299[v300] = v291;
            v299[v300 + 6] = v286;
          }
          while ( v277 <= v281 );
          v280 = v688;
          v279 = v638;
        }
        v268 = a3;
        v280 += 2;
        v279 = (unsigned int *)((char *)v279 - 1);
        v688 = v280;
        v638 = v279;
      }
      while ( v279 );
      v301 = v657;
      v302 = 1;
      v303 = v277 - 1;
      v644 = 1;
      if ( !v303 )
      {
LABEL_720:
        v593 = &v299[7 * v303];
        v595 = *(_OWORD *)v593;
        v662 = v593[6];
        v14 = *((_QWORD *)v593 + 2);
        v667 = v595;
        v676 = v662;
        v674 = v595;
        v675 = v14;
        *(double *)&v595 = ZSTD_totalLen(&v674);
        if ( v303 > v596 )
        {
          v679 = *(_DWORD *)(v594 + 24);
          v677 = v595;
          v678 = v14;
          ZSTD_totalLen(&v677);
          v268 = a3;
          v592 = v303 - v597;
          v589 = 0;
          goto LABEL_724;
        }
        v268 = a3;
        goto LABEL_723;
      }
      while ( 2 )
      {
        v304 = v302;
        v305 = (_DWORD *)(v302 + v647);
        v306 = &v299[7 * v302 - 7];
        v640 = v305;
        if ( v306[2] )
          v307 = 1;
        else
          v307 = v306[3] + 1;
        v308 = *v306 - ZSTD_litLengthPrice(v307 - 1, v301, 2);
        v310 = ZSTD_rawLiteralsCost((char *)v305 - 1, (unsigned int)(v309 - 1), v301) + v308;
        v311 = ZSTD_litLengthPrice(v307, v301, 2);
        v299 = v652;
        v313 = v310 + v311;
        v314 = &v652[7 * v304];
        v315 = *v314;
        if ( v313 <= *v314 )
        {
          v316 = *((_QWORD *)v306 + 2);
          v315 = v313;
          *v314 = v313;
          v317 = v306[6];
          *((_QWORD *)v314 + 2) = v316;
          v314[6] = v317;
          *(_QWORD *)(v314 + 1) = 0;
          v314[3] = v307;
        }
        if ( (unsigned __int64)v305 > v666 )
          goto LABEL_712;
        if ( v644 == v303 )
          goto LABEL_720;
        v318 = v314[2];
        v639 = v318 != 0;
        if ( v318 )
          v641 = 0;
        else
          v641 = v314[3];
        v645 = v315 + ZSTD_litLengthPrice(0, v657, v312);
        v638 = v314 + 4;
        v319 = *(unsigned int *)(a1 + 36);
        v320 = *(_QWORD *)(a1 + 8);
        v321 = *(_DWORD *)(a1 + 200);
        if ( (unsigned __int64)v305 < v320 + v319 )
          goto LABEL_711;
        v322 = (_DWORD)v305 - v320;
        if ( (unsigned int)v319 < (int)v305 - (int)v320 )
        {
          v323 = v636;
          do
            LODWORD(v319) = ZSTD_insertBt1(a1, (int)v320 + (int)v319, v323, v321, 0) + v319;
          while ( (unsigned int)v319 < v322 );
          v305 = v640;
        }
        v324 = *(_QWORD *)(a1 + 48);
        *(_DWORD *)(a1 + 36) = v322;
        v325 = *(unsigned int *)(a1 + 192);
        if ( v321 != 3 )
        {
          v326 = 4095;
          if ( v321 != 5 )
          {
            v327 = *(_DWORD *)(a1 + 204);
            if ( (unsigned int)(v321 - 6) <= 1 )
            {
              if ( v327 < 0xFFF )
                v326 = *(_DWORD *)(a1 + 204);
              v328 = (_DWORD)v305 - *(_QWORD *)(a1 + 8);
              v659 = *(_QWORD *)(a1 + 8);
              v635 = v328;
              v329 = ZSTD_hash6Ptr(v305, v325, v324);
              v331 = (unsigned int *)(v330 + 4 * v329);
              v332 = *(_DWORD *)(a1 + 28);
              v333 = *(_DWORD **)(a1 + 64);
              v334 = *v331;
              v335 = v640;
              v336 = 1 << (*(_DWORD *)(a1 + 188) - 1);
              v337 = 0;
              v650 = v333;
              v338 = v336 - 1;
              v651 = 0;
              v653 = 0;
              v642 = v338;
              if ( v338 < v328 )
                v337 = v328 - v338;
              v633 = v337;
              v339 = 1 << *(_DWORD *)(a1 + 184);
              v340 = v328 - v339;
              v341 = 1;
              if ( v328 - v332 <= v339 )
                v340 = v332;
              if ( *(_DWORD *)(a1 + 32) )
                v340 = v332;
              if ( v340 )
                v341 = v340;
              v342 = *(_DWORD *)(a1 + 196);
              v343 = v656;
              v648 = v341;
              v689 = 0;
              v637 = &v333[2 * (v328 & v338)];
              v643 = (char *)(v637 + 1);
              v634 = v328 + 9;
              v649 = 1 << v342;
              v344 = v639;
              v345 = v328 - *(_DWORD *)(a1 + 24);
              v346 = v638;
              v347 = v639 + 3;
              v348 = &v638[v639];
              while ( 2 )
              {
                if ( v344 == 3 )
                  v349 = *v346 - 1;
                else
                  v349 = *v348;
                v350 = 0;
                if ( v349 - 1 >= v345 )
                  goto LABEL_405;
                v351 = ZSTD_readMINMATCH(v640, 4, 0, -(__int64)v349);
                if ( v351 != *(_DWORD *)(v353 + v352) )
                  goto LABEL_404;
                v354 = (_QWORD *)(v352 + 4);
                v355 = v352 + 4;
                v356 = v636;
                v357 = (_QWORD *)(v353 + v355);
                v358 = v354;
                v359 = v636 - 7;
                if ( (unsigned __int64)v354 < v636 - 7 )
                {
                  if ( *v357 != *v354 )
                  {
                    v360 = ZSTD_NbCommonBytes(*v357 ^ *v354, v354, v357, v354);
                    goto LABEL_403;
                  }
                  ++v354;
                  ++v357;
                  if ( (unsigned __int64)v354 < v359 )
                  {
                    while ( *v357 == *v354 )
                    {
                      ++v354;
                      ++v357;
                      if ( (unsigned __int64)v354 >= v359 )
                        goto LABEL_392;
                    }
                    v363 = ZSTD_NbCommonBytes(*v357 ^ *v354, v354, v357, v358);
                    v360 = v364 - v365 + v363;
LABEL_403:
                    v350 = v360 + 4;
LABEL_404:
                    v335 = v640;
LABEL_405:
                    if ( v350 > v343 )
                    {
                      v361 = v689;
                      v343 = v350;
                      ++v689;
                      v362 = &v646[2 * v361];
                      v362[1] = v350;
                      *v362 = v344 - v639;
                      if ( v350 > v326 || (_DWORD *)((char *)v335 + v350) == (_DWORD *)v636 )
                        goto LABEL_686;
                    }
                    v346 = v638;
                    ++v344;
                    ++v348;
                    if ( v344 >= v347 )
                    {
                      v366 = v649;
                      *v331 = v635;
                      if ( v366 )
                      {
                        while ( 1 )
                        {
                          --v366;
                          if ( v334 < v648 )
                            break;
                          v367 = v653;
                          v368 = v640;
                          if ( v651 < v653 )
                            v367 = v651;
                          v369 = (_DWORD *)v636;
                          v370 = &v650[2 * (v334 & v642)];
                          v371 = v659 + v334;
                          v372 = (_QWORD *)((char *)v640 + v367);
                          v373 = v636 - 7;
                          v374 = (char *)v640 + v367;
                          v375 = (_QWORD *)(v371 + v367);
                          if ( (unsigned __int64)v640 + v367 >= v636 - 7 )
                            goto LABEL_420;
                          if ( *v375 != *v372 )
                          {
                            v376 = (unsigned int)ZSTD_NbCommonBytes(*v375 ^ *v372, v372, v375, v367);
                            goto LABEL_430;
                          }
                          ++v372;
                          ++v375;
                          if ( (unsigned __int64)v372 >= v373 )
                          {
LABEL_420:
                            if ( (unsigned __int64)v372 < v636 - 3 && *(_DWORD *)v375 == *(_DWORD *)v372 )
                            {
                              v372 = (_QWORD *)((char *)v372 + 4);
                              v375 = (_QWORD *)((char *)v375 + 4);
                            }
                            if ( (unsigned __int64)v372 < v636 - 1 && *(_WORD *)v375 == *(_WORD *)v372 )
                            {
                              v372 = (_QWORD *)((char *)v372 + 2);
                              v375 = (_QWORD *)((char *)v375 + 2);
                            }
                            if ( (unsigned __int64)v372 < v636 && *(_BYTE *)v375 == *(_BYTE *)v372 )
                              v372 = (_QWORD *)((char *)v372 + 1);
                            v376 = (char *)v372 - v374;
                          }
                          else
                          {
                            while ( *v375 == *v372 )
                            {
                              ++v372;
                              ++v375;
                              if ( (unsigned __int64)v372 >= v373 )
                                goto LABEL_420;
                            }
                            v380 = ZSTD_NbCommonBytes(*v375 ^ *v372, v372, v375, v367);
                            v376 = v381 - (_QWORD)v374 + v380;
                          }
LABEL_430:
                          v377 = v376 + v367;
                          if ( v377 > v343 )
                          {
                            if ( v377 > v634 - v334 )
                              v634 = v334 + v377;
                            v343 = v377;
                            v378 = v646;
                            v379 = v635 - v334 + 2;
                            v646[2 * v689 + 1] = v377;
                            v378[2 * v689++] = v379;
                            if ( v377 > 0x1000 || (_DWORD *)((char *)v368 + v377) == v369 )
                              break;
                          }
                          if ( *(_BYTE *)(v371 + v377) >= *((_BYTE *)v368 + v377) )
                          {
                            v653 = v377;
                            *(_DWORD *)v643 = v334;
                            if ( v334 <= v633 )
                            {
                              v384 = (int *)&v649;
                              goto LABEL_445;
                            }
                            v334 = *v370;
                            v643 = (char *)v370;
                          }
                          else
                          {
                            v651 = v377;
                            *v637 = v334;
                            if ( v334 <= v633 )
                            {
                              *(_DWORD *)v643 = 0;
                              v649 = 0;
                              v383 = v634;
                              goto LABEL_684;
                            }
                            v334 = v370[1];
                            v637 = v370 + 1;
                          }
                          if ( !v366 )
                          {
                            v382 = v637;
                            *(_DWORD *)v643 = 0;
                            *v382 = 0;
                            v383 = v634;
                            goto LABEL_684;
                          }
                        }
                      }
LABEL_446:
                      v385 = v637;
                      *(_DWORD *)v643 = 0;
                      *v385 = 0;
                      v383 = v634;
LABEL_684:
                      v543 = v383 - 8;
                      goto LABEL_685;
                    }
                    continue;
                  }
LABEL_392:
                  v356 = v636;
                }
                break;
              }
              if ( (unsigned __int64)v354 < v356 - 3 && *(_DWORD *)v357 == *(_DWORD *)v354 )
              {
                v354 = (_QWORD *)((char *)v354 + 4);
                v357 = (_QWORD *)((char *)v357 + 4);
              }
              if ( (unsigned __int64)v354 < v356 - 1 && *(_WORD *)v357 == *(_WORD *)v354 )
              {
                v354 = (_QWORD *)((char *)v354 + 2);
                v357 = (_QWORD *)((char *)v357 + 2);
              }
              if ( (unsigned __int64)v354 < v356 && *(_BYTE *)v357 == *(_BYTE *)v354 )
                LODWORD(v354) = (_DWORD)v354 + 1;
              v360 = (_DWORD)v354 - (_DWORD)v358;
              goto LABEL_403;
            }
            if ( v327 < 0xFFF )
              v326 = *(_DWORD *)(a1 + 204);
            v386 = (_DWORD)v305 - *(_QWORD *)(a1 + 8);
            v659 = *(_QWORD *)(a1 + 8);
            v635 = v386;
            v387 = ZSTD_hash4Ptr(v305, v325, v324);
            v389 = (unsigned int *)(v388 + 4 * v387);
            v390 = *(_DWORD *)(a1 + 28);
            v391 = *(_DWORD **)(a1 + 64);
            v392 = *v389;
            v393 = v640;
            v394 = 1 << (*(_DWORD *)(a1 + 188) - 1);
            v395 = 0;
            v650 = v391;
            v396 = v394 - 1;
            v651 = 0;
            v653 = 0;
            v642 = v396;
            if ( v396 < v386 )
              v395 = v386 - v396;
            v633 = v395;
            v397 = 1 << *(_DWORD *)(a1 + 184);
            v398 = v386 - v397;
            v399 = 1;
            if ( v386 - v390 <= v397 )
              v398 = v390;
            if ( *(_DWORD *)(a1 + 32) )
              v398 = v390;
            if ( v398 )
              v399 = v398;
            v400 = *(_DWORD *)(a1 + 196);
            v401 = v656;
            v648 = v399;
            v689 = 0;
            v637 = &v391[2 * (v386 & v396)];
            v643 = (char *)(v637 + 1);
            v634 = v386 + 9;
            v649 = 1 << v400;
            v402 = v639;
            v403 = v386 - *(_DWORD *)(a1 + 24);
            v404 = v638;
            v405 = v639 + 3;
            v406 = &v638[v639];
            while ( 2 )
            {
              if ( v402 == 3 )
                v407 = *v404 - 1;
              else
                v407 = *v406;
              v408 = 0;
              if ( v407 - 1 >= v403 )
                goto LABEL_482;
              v409 = ZSTD_readMINMATCH(v640, 4, 0, -(__int64)v407);
              if ( v409 != *(_DWORD *)(v411 + v410) )
                goto LABEL_481;
              v412 = (_QWORD *)(v410 + 4);
              v413 = v410 + 4;
              v414 = v636;
              v415 = (_QWORD *)(v411 + v413);
              v416 = v412;
              v417 = v636 - 7;
              if ( (unsigned __int64)v412 < v636 - 7 )
              {
                if ( *v415 != *v412 )
                {
                  v418 = ZSTD_NbCommonBytes(*v415 ^ *v412, v412, v415, v412);
                  goto LABEL_480;
                }
                ++v412;
                ++v415;
                if ( (unsigned __int64)v412 < v417 )
                {
                  while ( *v415 == *v412 )
                  {
                    ++v412;
                    ++v415;
                    if ( (unsigned __int64)v412 >= v417 )
                      goto LABEL_469;
                  }
                  v421 = ZSTD_NbCommonBytes(*v415 ^ *v412, v412, v415, v416);
                  v418 = v422 - v423 + v421;
LABEL_480:
                  v408 = v418 + 4;
LABEL_481:
                  v393 = v640;
LABEL_482:
                  if ( v408 > v401 )
                  {
                    v419 = v689;
                    v401 = v408;
                    ++v689;
                    v420 = &v646[2 * v419];
                    v420[1] = v408;
                    *v420 = v402 - v639;
                    if ( v408 > v326 || (_DWORD *)((char *)v393 + v408) == (_DWORD *)v636 )
                      goto LABEL_686;
                  }
                  v404 = v638;
                  ++v402;
                  ++v406;
                  if ( v402 >= v405 )
                  {
                    v424 = v649;
                    *v389 = v635;
                    if ( !v424 )
                      goto LABEL_446;
                    while ( 2 )
                    {
                      --v424;
                      if ( v392 < v648 )
                        goto LABEL_446;
                      v425 = v653;
                      v426 = v640;
                      if ( v651 < v653 )
                        v425 = v651;
                      v427 = (_DWORD *)v636;
                      v428 = &v650[2 * (v392 & v642)];
                      v429 = v659 + v392;
                      v430 = (_QWORD *)((char *)v640 + v425);
                      v431 = v636 - 7;
                      v432 = (char *)v640 + v425;
                      v433 = (_QWORD *)(v429 + v425);
                      if ( (unsigned __int64)v640 + v425 < v636 - 7 )
                      {
                        if ( *v433 != *v430 )
                        {
                          v434 = (unsigned int)ZSTD_NbCommonBytes(*v433 ^ *v430, v430, v433, v425);
LABEL_507:
                          v435 = v434 + v425;
                          if ( v435 > v401 )
                          {
                            if ( v435 > v634 - v392 )
                              v634 = v435 + v392;
                            v401 = v435;
                            v436 = v646;
                            v437 = v635 - v392 + 2;
                            v646[2 * v689 + 1] = v435;
                            v436[2 * v689++] = v437;
                            if ( v435 > 0x1000 || (_DWORD *)((char *)v426 + v435) == v427 )
                              goto LABEL_446;
                          }
                          if ( *(_BYTE *)(v429 + v435) >= *((_BYTE *)v426 + v435) )
                          {
                            v653 = v435;
                            *(_DWORD *)v643 = v392;
                            if ( v392 <= v633 )
                            {
                              v384 = &v655;
                              goto LABEL_445;
                            }
                            v392 = *v428;
                            v643 = (char *)v428;
                          }
                          else
                          {
                            v651 = v435;
                            *v637 = v392;
                            if ( v392 <= v633 )
                            {
                              *(_DWORD *)v643 = 0;
                              v655 = 0;
                              v383 = v634;
                              goto LABEL_684;
                            }
                            v392 = v428[1];
                            v637 = v428 + 1;
                          }
                          if ( !v424 )
                          {
                            v440 = v637;
                            *(_DWORD *)v643 = 0;
                            *v440 = 0;
                            v383 = v634;
                            goto LABEL_684;
                          }
                          continue;
                        }
                        ++v430;
                        ++v433;
                        if ( (unsigned __int64)v430 < v431 )
                        {
                          while ( *v433 == *v430 )
                          {
                            ++v430;
                            ++v433;
                            if ( (unsigned __int64)v430 >= v431 )
                              goto LABEL_497;
                          }
                          v438 = ZSTD_NbCommonBytes(*v433 ^ *v430, v430, v433, v425);
                          v434 = v439 - (_QWORD)v432 + v438;
                          goto LABEL_507;
                        }
                      }
                      break;
                    }
LABEL_497:
                    if ( (unsigned __int64)v430 < v636 - 3 && *(_DWORD *)v433 == *(_DWORD *)v430 )
                    {
                      v430 = (_QWORD *)((char *)v430 + 4);
                      v433 = (_QWORD *)((char *)v433 + 4);
                    }
                    if ( (unsigned __int64)v430 < v636 - 1 && *(_WORD *)v433 == *(_WORD *)v430 )
                    {
                      v430 = (_QWORD *)((char *)v430 + 2);
                      v433 = (_QWORD *)((char *)v433 + 2);
                    }
                    if ( (unsigned __int64)v430 < v636 && *(_BYTE *)v433 == *(_BYTE *)v430 )
                      v430 = (_QWORD *)((char *)v430 + 1);
                    v434 = (char *)v430 - v432;
                    goto LABEL_507;
                  }
                  continue;
                }
LABEL_469:
                v414 = v636;
              }
              break;
            }
            if ( (unsigned __int64)v412 < v414 - 3 && *(_DWORD *)v415 == *(_DWORD *)v412 )
            {
              v412 = (_QWORD *)((char *)v412 + 4);
              v415 = (_QWORD *)((char *)v415 + 4);
            }
            if ( (unsigned __int64)v412 < v414 - 1 && *(_WORD *)v415 == *(_WORD *)v412 )
            {
              v412 = (_QWORD *)((char *)v412 + 2);
              v415 = (_QWORD *)((char *)v415 + 2);
            }
            if ( (unsigned __int64)v412 < v414 && *(_BYTE *)v415 == *(_BYTE *)v412 )
              LODWORD(v412) = (_DWORD)v412 + 1;
            v418 = (_DWORD)v412 - (_DWORD)v416;
            goto LABEL_480;
          }
          if ( *(_DWORD *)(a1 + 204) < 0xFFFu )
            v326 = *(_DWORD *)(a1 + 204);
          v441 = (_DWORD)v305 - *(_QWORD *)(a1 + 8);
          v659 = *(_QWORD *)(a1 + 8);
          v635 = v441;
          v442 = ZSTD_hash5Ptr(v305, v325, v324);
          v444 = (unsigned int *)(v443 + 4 * v442);
          v445 = *(_DWORD *)(a1 + 28);
          v446 = *(_DWORD **)(a1 + 64);
          v447 = *v444;
          v448 = v640;
          v449 = 1 << (*(_DWORD *)(a1 + 188) - 1);
          v450 = 0;
          v650 = v446;
          v451 = v449 - 1;
          v651 = 0;
          v653 = 0;
          v648 = v451;
          if ( v451 < v441 )
            v450 = v441 - v451;
          v633 = v450;
          v452 = 1 << *(_DWORD *)(a1 + 184);
          v453 = v441 - v452;
          v454 = 1;
          if ( v441 - v445 <= v452 )
            v453 = v445;
          if ( *(_DWORD *)(a1 + 32) )
            v453 = v445;
          if ( v453 )
            v454 = v453;
          v455 = *(_DWORD *)(a1 + 196);
          v456 = v656;
          v649 = v454;
          v689 = 0;
          v637 = &v446[2 * (v441 & v451)];
          v643 = (char *)(v637 + 1);
          v634 = v441 + 9;
          v655 = 1 << v455;
          v457 = v639;
          v458 = v441 - *(_DWORD *)(a1 + 24);
          v459 = v638;
          v460 = v639 + 3;
          v461 = &v638[v639];
          while ( 2 )
          {
            if ( v457 == 3 )
              v462 = *v459 - 1;
            else
              v462 = *v461;
            v463 = 0;
            if ( v462 - 1 >= v458 )
              goto LABEL_557;
            v464 = ZSTD_readMINMATCH(v640, 4, 0, -(__int64)v462);
            if ( v464 != *(_DWORD *)(v466 + v465) )
              goto LABEL_556;
            v467 = (_QWORD *)(v465 + 4);
            v468 = v465 + 4;
            v469 = v636;
            v470 = (_QWORD *)(v466 + v468);
            v471 = v467;
            v472 = v636 - 7;
            if ( (unsigned __int64)v467 < v636 - 7 )
            {
              if ( *v470 != *v467 )
              {
                v473 = ZSTD_NbCommonBytes(*v470 ^ *v467, v467, v470, v467);
                goto LABEL_555;
              }
              ++v467;
              ++v470;
              if ( (unsigned __int64)v467 < v472 )
              {
                while ( *v470 == *v467 )
                {
                  ++v467;
                  ++v470;
                  if ( (unsigned __int64)v467 >= v472 )
                    goto LABEL_544;
                }
                v476 = ZSTD_NbCommonBytes(*v470 ^ *v467, v467, v470, v471);
                v473 = v477 - v478 + v476;
LABEL_555:
                v463 = v473 + 4;
LABEL_556:
                v448 = v640;
LABEL_557:
                if ( v463 > v456 )
                {
                  v474 = v689;
                  v456 = v463;
                  ++v689;
                  v475 = &v646[2 * v474];
                  v475[1] = v463;
                  *v475 = v457 - v639;
                  if ( v463 > v326 || (_DWORD *)((char *)v448 + v463) == (_DWORD *)v636 )
                    goto LABEL_686;
                }
                v459 = v638;
                ++v457;
                ++v461;
                if ( v457 >= v460 )
                {
                  v479 = v655;
                  *v444 = v635;
                  if ( !v479 )
                    goto LABEL_446;
                  while ( 2 )
                  {
                    --v479;
                    if ( v447 < v649 )
                      goto LABEL_446;
                    v480 = v653;
                    v481 = v640;
                    if ( v651 < v653 )
                      v480 = v651;
                    v482 = (_DWORD *)v636;
                    v483 = &v650[2 * (v447 & v648)];
                    v484 = v659 + v447;
                    v485 = (_QWORD *)((char *)v640 + v480);
                    v486 = v636 - 7;
                    v487 = (char *)v640 + v480;
                    v488 = (_QWORD *)(v484 + v480);
                    if ( (unsigned __int64)v640 + v480 < v636 - 7 )
                    {
                      if ( *v488 != *v485 )
                      {
                        v489 = (unsigned int)ZSTD_NbCommonBytes(*v488 ^ *v485, v485, v488, v480);
LABEL_582:
                        v490 = v489 + v480;
                        if ( v490 > v456 )
                        {
                          if ( v490 > v634 - v447 )
                            v634 = v490 + v447;
                          v456 = v490;
                          v491 = v646;
                          v492 = v635 - v447 + 2;
                          v646[2 * v689 + 1] = v490;
                          v491[2 * v689++] = v492;
                          if ( v490 > 0x1000 || (_DWORD *)((char *)v481 + v490) == v482 )
                            goto LABEL_446;
                        }
                        if ( *(_BYTE *)(v484 + v490) >= *((_BYTE *)v481 + v490) )
                        {
                          v653 = v490;
                          *(_DWORD *)v643 = v447;
                          if ( v447 <= v633 )
                          {
                            v384 = &v658;
LABEL_445:
                            v643 = (char *)v384;
                            goto LABEL_446;
                          }
                          v447 = *v483;
                          v643 = (char *)v483;
                        }
                        else
                        {
                          v651 = v490;
                          *v637 = v447;
                          if ( v447 <= v633 )
                          {
                            *(_DWORD *)v643 = 0;
                            v658 = 0;
                            v383 = v634;
                            goto LABEL_684;
                          }
                          v447 = v483[1];
                          v637 = v483 + 1;
                        }
                        if ( !v479 )
                        {
                          v495 = v637;
                          *(_DWORD *)v643 = 0;
                          *v495 = 0;
                          v383 = v634;
                          goto LABEL_684;
                        }
                        continue;
                      }
                      ++v485;
                      ++v488;
                      if ( (unsigned __int64)v485 < v486 )
                      {
                        while ( *v488 == *v485 )
                        {
                          ++v485;
                          ++v488;
                          if ( (unsigned __int64)v485 >= v486 )
                            goto LABEL_572;
                        }
                        v493 = ZSTD_NbCommonBytes(*v488 ^ *v485, v485, v488, v480);
                        v489 = v494 - (_QWORD)v487 + v493;
                        goto LABEL_582;
                      }
                    }
                    break;
                  }
LABEL_572:
                  if ( (unsigned __int64)v485 < v636 - 3 && *(_DWORD *)v488 == *(_DWORD *)v485 )
                  {
                    v485 = (_QWORD *)((char *)v485 + 4);
                    v488 = (_QWORD *)((char *)v488 + 4);
                  }
                  if ( (unsigned __int64)v485 < v636 - 1 && *(_WORD *)v488 == *(_WORD *)v485 )
                  {
                    v485 = (_QWORD *)((char *)v485 + 2);
                    v488 = (_QWORD *)((char *)v488 + 2);
                  }
                  if ( (unsigned __int64)v485 < v636 && *(_BYTE *)v488 == *(_BYTE *)v485 )
                    v485 = (_QWORD *)((char *)v485 + 1);
                  v489 = (char *)v485 - v487;
                  goto LABEL_582;
                }
                continue;
              }
LABEL_544:
              v469 = v636;
            }
            break;
          }
          if ( (unsigned __int64)v467 < v469 - 3 && *(_DWORD *)v470 == *(_DWORD *)v467 )
          {
            v467 = (_QWORD *)((char *)v467 + 4);
            v470 = (_QWORD *)((char *)v470 + 4);
          }
          if ( (unsigned __int64)v467 < v469 - 1 && *(_WORD *)v470 == *(_WORD *)v467 )
          {
            v467 = (_QWORD *)((char *)v467 + 2);
            v470 = (_QWORD *)((char *)v470 + 2);
          }
          if ( (unsigned __int64)v467 < v469 && *(_BYTE *)v470 == *(_BYTE *)v467 )
            LODWORD(v467) = (_DWORD)v467 + 1;
          v473 = (_DWORD)v467 - (_DWORD)v471;
          goto LABEL_555;
        }
        v496 = 4095;
        if ( *(_DWORD *)(a1 + 204) < 0xFFFu )
          v496 = *(_DWORD *)(a1 + 204);
        v497 = (_DWORD)v305 - *(_QWORD *)(a1 + 8);
        v653 = *(_QWORD *)(a1 + 8);
        v634 = v497;
        v498 = ZSTD_hash4Ptr(v305, v325, v324);
        v501 = (unsigned int *)(v500 + 4 * v498);
        v502 = *v501;
        v503 = *(_DWORD *)(a1 + 28);
        v504 = *(_DWORD **)(a1 + 64);
        v505 = 0;
        v506 = (1 << (*(_DWORD *)(a1 + 188) - 1)) - 1;
        v664 = 0;
        v663 = 0;
        v650 = v504;
        v655 = v506;
        if ( v506 < v499 )
          v505 = v499 - v506;
        v642 = v505;
        v507 = 1 << *(_DWORD *)(a1 + 184);
        v508 = v499 - v507;
        v509 = 1;
        if ( v499 - v503 <= v507 )
          v508 = v503;
        if ( *(_DWORD *)(a1 + 32) )
          v508 = v503;
        if ( v508 )
          v509 = v508;
        v510 = *(_DWORD *)(a1 + 196);
        v633 = v509;
        v689 = 0;
        v511 = 0;
        v637 = &v504[2 * (v499 & v506)];
        v643 = (char *)(v637 + 1);
        v635 = v499 + 9;
        v658 = 1 << v510;
        v651 = v656;
        v512 = v499 - *(_DWORD *)(a1 + 24);
        v513 = v639;
        v514 = v638;
        v515 = v639 + 3;
        v516 = &v638[v639];
        while ( 2 )
        {
          if ( v513 == 3 )
            v517 = *v514 - 1;
          else
            v517 = *v516;
          v518 = 0;
          if ( v517 - 1 >= v512 )
          {
            v526 = (_DWORD *)v636;
          }
          else
          {
            LODWORD(v659) = 1;
            v519 = ZSTD_readMINMATCH(v640, 3, (unsigned int)(*(_DWORD *)((char *)v640 - v517) << 8), 0);
            if ( v519 == v522 )
            {
              v523 = (_QWORD *)(v520 + 3);
              v524 = v520 + 3;
              v525 = (_QWORD *)(v521 + v520 + 3);
              v526 = (_DWORD *)v636;
              v527 = v636 - 7;
              if ( v520 + 3 >= v636 - 7 )
                goto LABEL_619;
              if ( *v525 != *v523 )
              {
                v518 = ZSTD_NbCommonBytes(*v525 ^ *v523, v523, v525, v524) + 3;
                goto LABEL_632;
              }
              v523 = (_QWORD *)(v520 + 11);
              ++v525;
              if ( v520 + 11 >= v527 )
              {
LABEL_619:
                if ( (unsigned __int64)v523 < v636 - 3 && *(_DWORD *)v525 == *(_DWORD *)v523 )
                {
                  v523 = (_QWORD *)((char *)v523 + 4);
                  v525 = (_QWORD *)((char *)v525 + 4);
                }
                if ( (unsigned __int64)v523 < v636 - 1 && *(_WORD *)v525 == *(_WORD *)v523 )
                {
                  v523 = (_QWORD *)((char *)v523 + 2);
                  v525 = (_QWORD *)((char *)v525 + 2);
                }
                if ( (unsigned __int64)v523 < v636 && *(_BYTE *)v525 == *(_BYTE *)v523 )
                  LODWORD(v523) = (_DWORD)v523 + 1;
                v518 = (_DWORD)v523 - v520;
              }
              else
              {
                while ( *v525 == *v523 )
                {
                  ++v523;
                  ++v525;
                  if ( (unsigned __int64)v523 >= v527 )
                    goto LABEL_619;
                }
                v528 = ZSTD_NbCommonBytes(*v525 ^ *v523, v523, v525, v524);
                v518 = v529 - v530 + v528 + 3;
              }
            }
            else
            {
              v526 = (_DWORD *)v636;
            }
LABEL_632:
            v511 = v689;
          }
          if ( v518 > v651 )
          {
            v531 = v511++;
            v532 = &v646[2 * v531];
            v532[1] = v518;
            *v532 = v513 - v639;
            v651 = v518;
            v689 = v511;
            if ( v518 > v496 || (_DWORD *)((char *)v640 + v518) == v526 )
              goto LABEL_686;
          }
          ++v513;
          ++v516;
          if ( v513 < v515 )
          {
            v514 = v638;
            continue;
          }
          break;
        }
        v533 = v651;
        if ( v651 >= 3 )
        {
          v536 = v634;
          v537 = v633;
          goto LABEL_643;
        }
        v534 = v640;
        v535 = ZSTD_insertAndFindFirstIndexHash3(a1, &v660, v640);
        v536 = v634;
        v537 = v633;
        if ( v535 < v633 || v634 - v535 >= 0x40000 )
          goto LABEL_643;
        v538 = ZSTD_count(v534, v653 + v535, v636);
        if ( v538 < 3 )
        {
          v537 = v633;
LABEL_643:
          v542 = v689;
LABEL_644:
          v544 = v658;
          *v501 = v536;
          if ( !v544 )
          {
LABEL_682:
            v560 = (char *)v637;
LABEL_683:
            v689 = v542;
            *(_DWORD *)v643 = 0;
            *(_DWORD *)v560 = 0;
            v383 = v635;
            goto LABEL_684;
          }
          while ( 2 )
          {
            --v544;
            if ( v502 < v537 )
              goto LABEL_682;
            v545 = v663;
            v546 = v640;
            if ( v664 < v663 )
              v545 = v664;
            v547 = (_DWORD *)v636;
            v548 = &v650[2 * (v502 & v655)];
            v549 = v653 + v502;
            v550 = (_QWORD *)((char *)v640 + v545);
            v551 = v636 - 7;
            v552 = (_QWORD *)(v549 + v545);
            if ( (unsigned __int64)v640 + v545 < v636 - 7 )
            {
              if ( *v552 != *v550 )
              {
                v553 = (unsigned int)ZSTD_NbCommonBytes(*v552 ^ *v550, v550, v552, v545);
LABEL_666:
                v554 = v553 + v545;
                if ( v554 <= v533 )
                {
                  v542 = v689;
                }
                else
                {
                  if ( v554 > v635 - v502 )
                    v635 = v502 + v554;
                  v533 = v554;
                  v555 = v646;
                  v556 = v634 - v502 + 2;
                  v646[2 * v689 + 1] = v554;
                  v555[2 * v689] = v556;
                  v542 = ++v689;
                  if ( v554 > 0x1000 || (_DWORD *)((char *)v546 + v554) == v547 )
                    goto LABEL_682;
                }
                if ( *(_BYTE *)(v549 + v554) >= *((_BYTE *)v546 + v554) )
                {
                  v663 = v554;
                  *(_DWORD *)v643 = v502;
                  if ( v502 <= v642 )
                  {
                    v643 = &v665;
                    goto LABEL_682;
                  }
                  v502 = *v548;
                  v643 = (char *)v548;
                }
                else
                {
                  v664 = v554;
                  *v637 = v502;
                  if ( v502 <= v642 )
                  {
                    v560 = &v665;
                    goto LABEL_683;
                  }
                  v502 = v548[1];
                  v637 = v548 + 1;
                }
                if ( !v544 )
                  goto LABEL_682;
                v537 = v633;
                continue;
              }
              ++v550;
              ++v552;
              if ( (unsigned __int64)v550 < v551 )
              {
                while ( *v552 == *v550 )
                {
                  ++v550;
                  ++v552;
                  if ( (unsigned __int64)v550 >= v551 )
                    goto LABEL_656;
                }
                v557 = ZSTD_NbCommonBytes(*v552 ^ *v550, v550, v552, v545);
                v553 = v558 - v559 + v557;
                goto LABEL_666;
              }
            }
            break;
          }
LABEL_656:
          if ( (unsigned __int64)v550 < v636 - 3 && *(_DWORD *)v552 == *(_DWORD *)v550 )
          {
            v550 = (_QWORD *)((char *)v550 + 4);
            v552 = (_QWORD *)((char *)v552 + 4);
          }
          if ( (unsigned __int64)v550 < v636 - 1 && *(_WORD *)v552 == *(_WORD *)v550 )
          {
            v550 = (_QWORD *)((char *)v550 + 2);
            v552 = (_QWORD *)((char *)v552 + 2);
          }
          if ( (unsigned __int64)v550 < v636 && *(_BYTE *)v552 == *(_BYTE *)v550 )
            v550 = (_QWORD *)((char *)v550 + 1);
          v553 = (char *)v550 - ((char *)v640 + v545);
          goto LABEL_666;
        }
        v540 = v646;
        v541 = v539 + 2;
        v542 = 1;
        v533 = v538;
        v689 = 1;
        *v646 = v541;
        v17 = (_DWORD *)((char *)v534 + v538) == (_DWORD *)v636;
        v540[1] = v538;
        if ( v538 <= v496 && !v17 )
        {
          v537 = v633;
          goto LABEL_644;
        }
        v543 = v536 + 1;
        v689 = 1;
LABEL_685:
        *(_DWORD *)(a1 + 36) = v543;
LABEL_686:
        if ( !v689 )
        {
LABEL_711:
          v299 = v652;
LABEL_712:
          v302 = v644 + 1;
          v644 = v302;
          if ( v302 > v303 )
            goto LABEL_720;
          v301 = v657;
          continue;
        }
        break;
      }
      v561 = v646;
      v562 = v646[2 * v689 - 1];
      if ( v562 <= v661 && v562 + v644 < 0x1000 )
      {
        v563 = 0;
        v642 = 0;
        v564 = v646;
        v650 = v646;
        while ( 1 )
        {
          v565 = *v564;
          v566 = ZSTD_updateRep(v680, v638, *v564, v639);
          v569 = v567[1];
          v570 = *(_QWORD *)v566;
          v571 = *(_DWORD *)(v566 + 8);
          v572 = v563 ? v561[2 * v563 - 1] + 1 : v654;
          if ( v569 >= v572 )
            break;
          v299 = v652;
LABEL_709:
          v561 = v646;
          ++v563;
          v564 = v567 + 2;
          v642 = v563;
          v650 = v564;
          if ( v563 >= v689 )
            goto LABEL_712;
        }
        v573 = v657;
        v574 = v569 + v568;
        while ( 2 )
        {
          _BitScanReverse((unsigned int *)&v575, v565 + 1);
          v17 = *(_DWORD *)(v573 + 80) == 1;
          v576 = v574 - v568 - 3;
          LODWORD(v653) = 0;
          if ( v17 )
          {
            LODWORD(v651) = 0;
            _BitScanReverse(&v577, v576 + 1);
            v578 = ((unsigned int)(((_DWORD)v576 + 1) << 8) >> v577) + v645 + (((_DWORD)v575 + v577 + 16) << 8);
          }
          else
          {
            v579 = *(_QWORD *)(v573 + 24);
            LODWORD(v643) = 0;
            v580 = *(_DWORD *)(v579 + 4 * v575) + 1;
            _BitScanReverse((unsigned int *)&v579, v580);
            v581 = *(_DWORD *)(v573 + 76) + (((_DWORD)v575 - (_DWORD)v579) << 8) - (v580 << 8 >> v579);
            if ( (unsigned int)v576 <= 0x7F )
            {
              _mm_lfence();
              v583 = *((unsigned __int8 *)&qword_1803EF770[8] + v576);
            }
            else
            {
              _BitScanReverse(&v582, v576);
              LODWORD(v637) = 0;
              v583 = v582 + 36;
            }
            v584 = 4 * v583;
            LODWORD(v640) = 0;
            v585 = *(_DWORD *)(*(_QWORD *)(v573 + 16) + 4 * v583) + 1;
            _BitScanReverse(&v586, v585);
            v578 = v581
                 + v645
                 + *(_DWORD *)(v573 + 72)
                 + ((*(_DWORD *)((char *)&qword_1803EF640[10] + v584) - v586) << 8)
                 - (v585 << 8 >> v586)
                 + 51;
          }
          v299 = v652;
          if ( v574 <= v303 )
          {
            if ( v578 < v652[7 * v574] )
            {
              if ( v303 < v574 )
                goto LABEL_704;
LABEL_705:
              v587 = 7LL * v574;
              v588 = v641;
              *(_QWORD *)&v299[v587 + 4] = v570;
              v299[v587 + 6] = v571;
              v299[v587 + 2] = v574 - v568;
              v299[v587 + 1] = v565;
              v299[v587 + 3] = v588;
              v299[v587] = v578;
            }
            if ( --v574 - v568 < v572 )
            {
              v563 = v642;
              v567 = v650;
              goto LABEL_709;
            }
            continue;
          }
          break;
        }
        do
LABEL_704:
          v299[7 * ++v303] = 0x40000000;
        while ( v303 < v574 );
        goto LABEL_705;
      }
      v589 = 0;
      v274 = v652;
      DWORD1(v667) = v646[2 * v689 - 2];
      v590 = 7LL * v644;
      *((_QWORD *)&v667 + 1) = __PAIR64__(v641, v562);
      if ( v652[v590 + 2] )
        v591 = 0;
      else
        v591 = v652[v590 + 3];
      v268 = a3;
      v592 = 0;
      if ( v644 - v591 <= 0x1000 )
        v592 = v644 - v591;
LABEL_724:
      v598 = v592 + 1;
      v599 = v592 + 1;
      v600 = 7LL * (v592 + 1);
      v601 = v662;
      *(_OWORD *)&v274[v600] = v667;
      *(_QWORD *)&v274[v600 + 4] = v14;
      v274[v600 + 6] = v601;
      while ( v592 )
      {
        v602 = &v274[7 * v592];
        v603 = *(_OWORD *)v602;
        v673 = v602[6];
        v604 = *((_QWORD *)v602 + 2);
        v671 = v603;
        v672 = v604;
        *(double *)&v603 = ZSTD_totalLen(&v671);
        v605 = 7LL * --v599;
        *(_OWORD *)&v274[v605] = v603;
        *(_QWORD *)&v274[v605 + 4] = *(_QWORD *)(v606 + 16);
        v274[v605 + 6] = *(_DWORD *)(v606 + 24);
        v607 = v592;
        v592 -= v608;
        if ( v607 <= v608 )
          v592 = v589;
      }
      if ( v599 <= v598 )
      {
        v609 = v685;
        while ( 1 )
        {
          v610 = 7LL * v599;
          v611 = v274[v610 + 2];
          v612 = (unsigned int)v274[v610 + 3];
          v613 = v274[v610 + 1];
          v614 = v611 + v612;
          if ( v611 )
            break;
          v647 = v609 + v612;
LABEL_752:
          v268 = a3;
          ++v599;
          v589 = 0;
          if ( v599 > v598 )
            goto LABEL_753;
        }
        if ( v613 >= 3 )
        {
          v268[2] = v268[1];
          v268[1] = *v268;
          *v268 = v613 - 2;
          goto LABEL_740;
        }
        v615 = v589;
        LOBYTE(v615) = (_DWORD)v612 == 0;
        v616 = v613 + v615;
        if ( (_DWORD)v616 )
        {
          if ( (_DWORD)v616 == 3 )
          {
            v617 = *v268 - 1;
            goto LABEL_738;
          }
          v617 = v268[v616];
          if ( (unsigned int)v616 >= 2 )
LABEL_738:
            v268[2] = v268[1];
          v268[1] = *v268;
          *v268 = v617;
        }
LABEL_740:
        ZSTD_updateStats(v657, v612, v685, v613, v611);
        v618 = v611 - 3;
        v620 = v619;
        v621 = *(_QWORD *)(a2 + 24);
        if ( v619 + v685 <= v636 - 32 )
        {
          ZSTD_copy16(v621);
          if ( v620 > 0x10 )
          {
            ZSTD_copy16(*(_QWORD *)(a2 + 24) + 16LL);
            v624 = ZSTD_copy16(v623 + 16);
            v626 = v625 + 16;
            if ( v626 < v624 )
            {
              do
              {
                ZSTD_copy16(v626);
                v628 = ZSTD_copy16(v627 + 16);
                v626 = v629 + 16;
              }
              while ( v626 < v628 );
            }
LABEL_746:
            v622 = v685;
          }
          *(_QWORD *)(a2 + 24) += v620;
          v630 = *(_QWORD *)(a2 + 8);
          if ( v620 > 0xFFFF )
          {
            *(_DWORD *)(a2 + 72) = 1;
            *(_DWORD *)(a2 + 76) = (v630 - *(_QWORD *)a2) >> 3;
          }
          *(_WORD *)(v630 + 4) = v620;
          **(_DWORD **)(a2 + 8) = v613 + 1;
          v631 = *(_QWORD *)(a2 + 8);
          if ( v618 > 0xFFFF )
          {
            *(_DWORD *)(a2 + 72) = 2;
            *(_DWORD *)(a2 + 76) = (v631 - *(_QWORD *)a2) >> 3;
          }
          v274 = v652;
          *(_WORD *)(v631 + 6) = v618;
          *(_QWORD *)(a2 + 8) += 8LL;
          v685 = v614 + v622;
          v609 = v685;
          v647 = v685;
          goto LABEL_752;
        }
        ZSTD_safecopyLiterals(v621);
        goto LABEL_746;
      }
LABEL_753:
      ZSTD_setBasePrices(v657, 2);
      v13 = v647;
LABEL_756:
      v10 = v636;
      v7 = a1;
      v5 = v685;
    }
    while ( v13 < v666 );
  }
  return v10 - v5;
}

```

## disassembly

```asm
0x1802d70d0  mov     [rsp-8+arg_18], r9
0x1802d70d5  mov     [rsp-8+arg_10], r8
0x1802d70da  mov     [rsp-8+arg_8], rdx
0x1802d70df  mov     [rsp-8+arg_0], rcx
0x1802d70e4  push    rbp
0x1802d70e5  push    rbx
0x1802d70e6  push    rsi
0x1802d70e7  push    rdi
0x1802d70e8  push    r12
0x1802d70ea  push    r13
0x1802d70ec  push    r14
0x1802d70ee  lea     rbp, [rsp-0D0h]
0x1802d70f6  sub     rsp, 1D0h
0x1802d70fd  cmp     dword ptr [rcx+7Ch], 0
0x1802d7101  mov     rsi, r9
0x1802d7104  mov     rdi, [rbp+100h+arg_20]
0x1802d710b  mov     r10, r8
0x1802d710e  mov     r12, rcx
0x1802d7111  jnz     short loc_1802D7146
0x1802d7113  mov     rax, [rdx]
0x1802d7116  cmp     [rdx+8], rax
0x1802d711a  jnz     short loc_1802D7146
0x1802d711c  mov     r8d, [rcx+18h]
0x1802d7120  cmp     r8d, [rcx+1Ch]
0x1802d7124  jnz     short loc_1802D7146
0x1802d7126  mov     eax, esi
0x1802d7128  sub     eax, [rcx+8]
0x1802d712b  cmp     eax, r8d
0x1802d712e  jnz     short loc_1802D7146
0x1802d7130  cmp     rdi, 400h
0x1802d7137  jbe     short loc_1802D7146
0x1802d7139  mov     r8, r10
0x1802d713c  mov     [rsp+200h+var_1E0], rdi
0x1802d7141  call    ZSTD_initStats_ultra
0x1802d7146  mov     eax, [r12+0CCh]
0x1802d714e  lea     rcx, [r12+48h]
0x1802d7153  mov     ebx, [r12+18h]
0x1802d7158  lea     r13, [rsi+rdi]
0x1802d715c  add     rbx, [r12+8]
0x1802d7161  lea     r14, [r13-8]
0x1802d7165  mov     edx, 0FFFh
0x1802d716a  mov     [rbp+100h+var_138], rcx
0x1802d716e  cmp     eax, edx
0x1802d7170  mov     [rsp+200h+var_1C0], r13
0x1802d7175  mov     r9d, 2
0x1802d717b  mov     [rbp+100h+var_F8], r14
0x1802d717f  cmovb   edx, eax
0x1802d7182  mov     r8, rdi
0x1802d7185  xor     eax, eax
0x1802d7187  mov     [rbp+100h+var_11C], edx
0x1802d718a  cmp     dword ptr [r12+0C8h], 3
0x1802d7193  mov     rdx, rsi
0x1802d7196  setnz   al
0x1802d7199  add     eax, 3
0x1802d719c  mov     [rbp+100h+var_148], eax
0x1802d719f  mov     eax, [r12+24h]
0x1802d71a4  mov     [rbp+100h+var_120], eax
0x1802d71a7  mov     rax, [rcx+28h]
0x1802d71ab  mov     [rbp+100h+var_158], rax
0x1802d71af  mov     rax, [rcx+20h]
0x1802d71b3  mov     [rbp+100h+var_180], rax
0x1802d71b7  call    ZSTD_rescaleFreqs
0x1802d71bc  xor     r9d, r9d
0x1802d71bf  cmp     rsi, rbx
0x1802d71c2  mov     ecx, r9d
0x1802d71c5  setz    cl
0x1802d71c8  add     rcx, rsi
0x1802d71cb  mov     [rbp+100h+var_178], rcx
0x1802d71cf  cmp     rcx, r14
0x1802d71d2  jnb     loc_1802DA11A
0x1802d71d8  mov     eax, [rbp+100h+var_D8]
0x1802d71db  movsd   xmm2, [rbp+100h+var_E0]
0x1802d71e0  mov     [rbp+100h+var_118], eax
0x1802d71e3  mov     [rsp+200h+var_38], r15
0x1802d71eb  nop     dword ptr [rax+rax+00h]
0x1802d71f0  mov     ebx, [r12+24h]
0x1802d71f5  mov     eax, ecx
0x1802d71f7  mov     r14, [r12+8]
0x1802d71fc  sub     eax, esi
0x1802d71fe  mov     esi, [r12+0C8h]
0x1802d7206  mov     r15d, r9d
0x1802d7209  setz    r15b
0x1802d720d  mov     [rbp+100h+var_16C], eax
0x1802d7210  mov     [rsp+200h+var_1A8], r15d
0x1802d7215  lea     rax, [r14+rbx]
0x1802d7219  cmp     rcx, rax
0x1802d721c  jb      loc_1802DA0E8
0x1802d7222  mov     edi, ecx
0x1802d7224  sub     edi, r14d
0x1802d7227  cmp     ebx, edi
0x1802d7229  jnb     short loc_1802D725A
0x1802d722b  xor     r15d, r15d
0x1802d722e  xchg    ax, ax
0x1802d7230  mov     edx, ebx
0x1802d7232  mov     r9d, esi
0x1802d7235  add     rdx, r14
0x1802d7238  mov     dword ptr [rsp+200h+var_1E0], r15d
0x1802d723d  mov     r8, r13
0x1802d7240  mov     rcx, r12
0x1802d7243  call    ZSTD_insertBt1
0x1802d7248  add     ebx, eax
0x1802d724a  cmp     ebx, edi
0x1802d724c  jb      short loc_1802D7230
0x1802d724e  mov     r15d, [rsp+200h+var_1A8]
0x1802d7253  xor     r9d, r9d
0x1802d7256  mov     rcx, [rbp+100h+var_178]
0x1802d725a  mov     r8, [r12+30h]
0x1802d725f  mov     [r12+24h], edi
0x1802d7264  mov     edx, [r12+0C0h]
0x1802d726c  cmp     esi, 3
0x1802d726f  jz      loc_1802D7F72
0x1802d7275  mov     r14d, 0FFFh
0x1802d727b  mov     ebx, ecx
0x1802d727d  cmp     esi, 5
0x1802d7280  jz      loc_1802D7B34
0x1802d7286  lea     eax, [rsi-6]
0x1802d7289  cmp     eax, 1
0x1802d728c  mov     eax, [r12+0CCh]
0x1802d7294  ja      loc_1802D76FC
0x1802d729a  cmp     eax, r14d
0x1802d729d  cmovb   r14d, eax
0x1802d72a1  mov     rax, [r12+8]
0x1802d72a6  sub     ebx, eax
0x1802d72a8  mov     [rsp+200h+var_190], rax
0x1802d72ad  mov     [rsp+200h+var_198], ebx
0x1802d72b1  call    ZSTD_hash6Ptr
0x1802d72b6  mov     ecx, [r12+0BCh]
0x1802d72be  lea     r15, [r8+rax*4]
0x1802d72c2  mov     r8d, [r12+1Ch]
0x1802d72c7  dec     ecx
0x1802d72c9  mov     rdi, [r12+40h]
0x1802d72ce  mov     eax, ebx
0x1802d72d0  mov     r10d, [r15]
0x1802d72d3  mov     edx, 1
0x1802d72d8  mov     r11d, 1
0x1802d72de  mov     [rsp+200h+var_1A0], r9
0x1802d72e3  shl     r11d, cl
0x1802d72e6  xor     r9d, r9d
0x1802d72e9  xor     ecx, ecx
0x1802d72eb  mov     [rbp+100h+var_168], rdi
0x1802d72ef  dec     r11d
0x1802d72f2  mov     [rsp+200h+var_1B8], r9
0x1802d72f7  sub     eax, r11d
0x1802d72fa  mov     [rsp+200h+var_1CC], r11d
0x1802d72ff  cmp     r11d, ebx
0x1802d7302  cmovb   ecx, eax
0x1802d7305  mov     eax, ebx
0x1802d7307  sub     eax, r8d
0x1802d730a  mov     [rsp+200h+var_1C8], ecx
0x1802d730e  mov     ecx, [r12+0B8h]
0x1802d7316  shl     edx, cl
0x1802d7318  mov     ecx, ebx
0x1802d731a  sub     ecx, edx
0x1802d731c  cmp     eax, edx
0x1802d731e  mov     eax, 1
0x1802d7323  cmovbe  ecx, r8d
0x1802d7327  cmp     [r12+20h], r9d
0x1802d732c  cmovnz  ecx, r8d
0x1802d7330  test    ecx, ecx
0x1802d7332  cmovnz  eax, ecx
0x1802d7335  mov     ecx, [r12+0C4h]
0x1802d733d  mov     [rsp+200h+var_194], eax
0x1802d7341  xor     edx, edx
0x1802d7343  mov     eax, r11d
0x1802d7346  mov     dword ptr [rbp+100h+arg_20], edx
0x1802d734c  and     eax, ebx
0x1802d734e  add     eax, eax
0x1802d7350  lea     r13, [rdi+rax*4]
0x1802d7354  mov     edi, ebx
0x1802d7356  lea     rax, [r13+4]
0x1802d735a  mov     [rsp+200h+var_1B0], rax
0x1802d735f  lea     eax, [rbx+9]
0x1802d7362  mov     [rsp+200h+var_1D0], eax
0x1802d7366  mov     eax, 1
0x1802d736b  shl     eax, cl
0x1802d736d  mov     rcx, [rbp+100h+arg_0]
0x1802d7374  mov     [rsp+200h+var_184], eax
0x1802d7378  mov     eax, [rbp+100h+var_148]
0x1802d737b  dec     eax
0x1802d737d  sub     edi, [rcx+18h]
0x1802d7380  mov     r12d, eax
0x1802d7383  mov     rcx, [rbp+100h+arg_10]
0x1802d738a  mov     [rbp+100h+var_140], rax
0x1802d738e  mov     eax, [rsp+200h+var_1A8]
0x1802d7392  mov     r11d, eax
0x1802d7395  lea     esi, [rax+3]
0x1802d7398  lea     rbx, [rcx+rax*4]
0x1802d739c  nop     dword ptr [rax+00h]
0x1802d73a0  cmp     r11d, 3
0x1802d73a4  jnz     short loc_1802D73AC
0x1802d73a6  mov     ecx, [rcx]
0x1802d73a8  dec     ecx
0x1802d73aa  jmp     short loc_1802D73AE
0x1802d73ac  mov     ecx, [rbx]
0x1802d73ae  lea     eax, [rcx-1]
0x1802d73b1  mov     r8d, edx
0x1802d73b4  cmp     eax, edi
0x1802d73b6  jnb     loc_1802D7485
0x1802d73bc  mov     r9d, ecx
0x1802d73bf  mov     edx, 4
0x1802d73c4  mov     rcx, [rbp+100h+var_178]
0x1802d73c8  neg     r9
0x1802d73cb  call    ZSTD_readMINMATCH
0x1802d73d0  cmp     eax, [r9+rcx]
0x1802d73d4  jnz     loc_1802D747E
0x1802d73da  lea     rdx, [rcx+4]
0x1802d73de  lea     r8, [rcx+4]
0x1802d73e2  mov     rcx, [rsp+200h+var_1C0]
0x1802d73e7  add     r8, r9
0x1802d73ea  mov     r9, rdx
0x1802d73ed  lea     rax, [rcx-7]
0x1802d73f1  cmp     rdx, rax
0x1802d73f4  jnb     short loc_1802D7432
0x1802d73f6  mov     rcx, [rdx]
0x1802d73f9  xor     rcx, [r8]
0x1802d73fc  jz      short loc_1802D7407
0x1802d73fe  call    ZSTD_NbCommonBytes
0x1802d7403  mov     ecx, eax
0x1802d7405  jmp     short loc_1802D747A
0x1802d7407  add     rdx, 8
0x1802d740b  add     r8, 8
0x1802d740f  cmp     rdx, rax
0x1802d7412  jnb     short loc_1802D742D
0x1802d7414  mov     rcx, [rdx]
0x1802d7417  xor     rcx, [r8]
0x1802d741a  jnz     loc_1802D74D7
0x1802d7420  add     rdx, 8
0x1802d7424  add     r8, 8
0x1802d7428  cmp     rdx, rax
0x1802d742b  jb      short loc_1802D7414
0x1802d742d  mov     rcx, [rsp+200h+var_1C0]
0x1802d7432  lea     rax, [rcx-3]
0x1802d7436  cmp     rdx, rax
0x1802d7439  jnb     short loc_1802D744A
0x1802d743b  mov     eax, [rdx]
0x1802d743d  cmp     [r8], eax
0x1802d7440  jnz     short loc_1802D744A
0x1802d7442  add     rdx, 4
0x1802d7446  add     r8, 4
0x1802d744a  lea     rax, [rcx-1]
0x1802d744e  cmp     rdx, rax
0x1802d7451  jnb     short loc_1802D7464
0x1802d7453  movzx   eax, word ptr [rdx]
0x1802d7456  cmp     [r8], ax
0x1802d745a  jnz     short loc_1802D7464
0x1802d745c  add     rdx, 2
0x1802d7460  add     r8, 2
0x1802d7464  cmp     rdx, rcx
0x1802d7467  jnb     short loc_1802D7474
0x1802d7469  movzx   eax, byte ptr [rdx]
0x1802d746c  cmp     [r8], al
0x1802d746f  jnz     short loc_1802D7474
0x1802d7471  inc     rdx
0x1802d7474  mov     rcx, rdx
0x1802d7477  sub     rcx, r9
0x1802d747a  lea     r8d, [rcx+4]
0x1802d747e  mov     r9d, dword ptr [rbp+100h+arg_20]
0x1802d7485  mov     edx, r8d
0x1802d7488  cmp     rdx, r12
0x1802d748b  jbe     short loc_1802D74E6
0x1802d748d  mov     rcx, [rbp+100h+var_180]
0x1802d7491  mov     r12d, edx
0x1802d7494  mov     eax, r9d
0x1802d7497  inc     r9d
0x1802d749a  lea     rcx, [rcx+rax*8]
0x1802d749e  mov     eax, r11d
0x1802d74a1  mov     [rcx+4], r8d
0x1802d74a5  sub     eax, [rsp+200h+var_1A8]
0x1802d74a9  mov     [rcx], eax
0x1802d74ab  mov     rax, [rbp+100h+var_178]
0x1802d74af  add     rax, rdx
0x1802d74b2  mov     dword ptr [rbp+100h+arg_20], r9d
0x1802d74b9  xor     edx, edx
0x1802d74bb  cmp     rax, [rsp+200h+var_1C0]
0x1802d74c0  mov     ecx, edx
0x1802d74c2  mov     eax, edx
0x1802d74c4  setz    cl
0x1802d74c7  cmp     r8d, r14d
0x1802d74ca  setnbe  al
0x1802d74cd  or      ecx, eax
0x1802d74cf  jnz     loc_1802D767B
0x1802d74d5  jmp     short loc_1802D74E8
0x1802d74d7  call    ZSTD_NbCommonBytes
0x1802d74dc  mov     ecx, eax
0x1802d74de  sub     rdx, r9
0x1802d74e1  add     rcx, rdx
0x1802d74e4  jmp     short loc_1802D747A
0x1802d74e6  xor     edx, edx
0x1802d74e8  mov     rcx, [rbp+100h+arg_10]
0x1802d74ef  inc     r11d
0x1802d74f2  add     rbx, 4
0x1802d74f6  cmp     r11d, esi
0x1802d74f9  jb      loc_1802D73A0
0x1802d74ff  mov     esi, [rsp+200h+var_184]
0x1802d7503  mov     eax, [rsp+200h+var_198]
0x1802d7507  mov     [r15], eax
0x1802d750a  test    esi, esi
0x1802d750c  jz      loc_1802D765F
0x1802d7512  dec     esi
0x1802d7514  cmp     r10d, [rsp+200h+var_194]
  ... truncated ...
```
