# ZSTD_compressBlock_btultra

- ea: `0x1802d40a0`
- end: `0x1802d70c8`
- name: `ZSTD_compressBlock_btultra`
- size: `12328`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1802b6fe0`
- `0x1802bb530`
- `0x1802bb540`
- `0x1802bb7b0`
- `0x1802bb7f0`
- `0x1802bb820`
- `0x1802bb8c0`
- `0x1802d40a0`
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
unsigned __int64 __fastcall ZSTD_compressBlock_btultra(
        __int64 a1,
        __int64 a2,
        _DWORD *a3,
        unsigned __int64 a4,
        __int64 a5)
{
  __int64 v5; // r12
  __int64 v6; // rcx
  int v7; // edx
  unsigned __int64 v8; // rdi
  unsigned int v9; // eax
  unsigned __int64 v10; // r13
  unsigned __int64 v11; // rsi
  __int64 v12; // rbx
  bool v13; // zf
  unsigned __int64 v14; // rcx
  __int64 v15; // xmm2_8
  __int64 v16; // rbx
  __int64 v17; // r14
  int v18; // esi
  BOOL v19; // r15d
  unsigned int v20; // edi
  __int64 v21; // r8
  __int64 v22; // rdx
  unsigned int v23; // r14d
  unsigned int v24; // eax
  unsigned int v25; // ebx
  __int64 v26; // rax
  __int64 v27; // r8
  unsigned int *v28; // r15
  int v29; // r8d
  char v30; // cl
  _DWORD *v31; // rdi
  unsigned int v32; // r10d
  _DWORD *v33; // r9
  int v34; // r11d
  unsigned int v35; // r9d
  unsigned int v36; // ecx
  unsigned int v37; // r11d
  unsigned int v38; // edx
  int v39; // ecx
  int v40; // eax
  int v41; // ecx
  unsigned int *v42; // r13
  unsigned int v43; // edi
  unsigned __int64 v44; // r12
  _DWORD *v45; // rcx
  unsigned int v46; // r11d
  unsigned int v47; // esi
  unsigned int *v48; // rbx
  unsigned int v49; // ecx
  unsigned int v50; // r8d
  int MINMATCH; // eax
  __int64 v52; // rcx
  __int64 v53; // r9
  _QWORD *v54; // rdx
  __int64 v55; // r8
  unsigned __int64 v56; // rcx
  _QWORD *v57; // r8
  _QWORD *v58; // r9
  unsigned __int64 v59; // rax
  int v60; // ecx
  __int64 v61; // rax
  _DWORD *v62; // rcx
  int v63; // eax
  int v64; // edx
  int v65; // r9d
  int v66; // esi
  _DWORD *v67; // r9
  unsigned __int64 v68; // r15
  unsigned __int64 v69; // r14
  unsigned int *v70; // rdi
  char *v71; // r11
  _QWORD *v72; // rdx
  unsigned __int64 v73; // rax
  char *v74; // rbx
  _QWORD *v75; // r8
  unsigned __int64 v76; // rcx
  unsigned __int64 v77; // r9
  _DWORD *v78; // rcx
  int v79; // eax
  unsigned int *v80; // rax
  unsigned int v81; // eax
  unsigned int v82; // ebx
  unsigned int v83; // eax
  __int64 v84; // rdx
  unsigned int v85; // ebx
  __int64 v86; // rax
  __int64 v87; // r8
  unsigned int *v88; // r15
  int v89; // r8d
  char v90; // cl
  _DWORD *v91; // rdi
  unsigned int v92; // r10d
  _DWORD *v93; // r9
  int v94; // r11d
  unsigned int v95; // r9d
  unsigned int v96; // ecx
  unsigned int v97; // r11d
  unsigned int v98; // edx
  int v99; // ecx
  int v100; // eax
  int v101; // ecx
  unsigned int v102; // edi
  unsigned __int64 v103; // r12
  _DWORD *v104; // rcx
  unsigned int v105; // r11d
  unsigned int v106; // esi
  unsigned int *v107; // rbx
  unsigned int v108; // ecx
  unsigned int v109; // r8d
  int v110; // eax
  __int64 v111; // rcx
  __int64 v112; // r9
  _QWORD *v113; // rdx
  __int64 v114; // r8
  unsigned __int64 v115; // rcx
  _QWORD *v116; // r8
  _QWORD *v117; // r9
  unsigned __int64 v118; // rax
  int v119; // ecx
  __int64 v120; // rax
  _DWORD *v121; // rcx
  int v122; // eax
  int v123; // edx
  int v124; // r9d
  int v125; // esi
  _DWORD *v126; // r9
  unsigned __int64 v127; // r15
  unsigned __int64 v128; // r14
  unsigned int *v129; // rdi
  char *v130; // r11
  _QWORD *v131; // rdx
  unsigned __int64 v132; // rax
  char *v133; // rbx
  _QWORD *v134; // r8
  unsigned __int64 v135; // rcx
  unsigned __int64 v136; // r9
  _DWORD *v137; // rcx
  int v138; // eax
  unsigned int v139; // eax
  __int64 v140; // rdx
  unsigned int v141; // ebx
  __int64 v142; // rax
  __int64 v143; // r8
  unsigned int *v144; // r15
  int v145; // r8d
  char v146; // cl
  _DWORD *v147; // rdi
  unsigned int v148; // r10d
  _DWORD *v149; // r9
  int v150; // r11d
  unsigned int v151; // r9d
  unsigned int v152; // ecx
  unsigned int v153; // r11d
  unsigned int v154; // edx
  int v155; // ecx
  int v156; // eax
  int v157; // ecx
  unsigned int v158; // edi
  unsigned __int64 v159; // r12
  _DWORD *v160; // rcx
  unsigned int v161; // r11d
  unsigned int v162; // esi
  unsigned int *v163; // rbx
  unsigned int v164; // ecx
  unsigned int v165; // r8d
  int v166; // eax
  __int64 v167; // rcx
  __int64 v168; // r9
  _QWORD *v169; // rdx
  __int64 v170; // r8
  unsigned __int64 v171; // rcx
  _QWORD *v172; // r8
  _QWORD *v173; // r9
  unsigned __int64 v174; // rax
  int v175; // ecx
  __int64 v176; // rax
  _DWORD *v177; // rcx
  int v178; // eax
  int v179; // edx
  int v180; // r9d
  int v181; // esi
  _DWORD *v182; // r9
  unsigned __int64 v183; // r15
  unsigned __int64 v184; // r14
  unsigned int *v185; // rdi
  char *v186; // r11
  _QWORD *v187; // rdx
  unsigned __int64 v188; // rax
  char *v189; // rbx
  _QWORD *v190; // r8
  unsigned __int64 v191; // rcx
  unsigned __int64 v192; // r9
  _DWORD *v193; // rcx
  int v194; // eax
  unsigned int v195; // eax
  __int64 v196; // rdx
  unsigned int v197; // esi
  unsigned int v198; // r10d
  __int64 v199; // rax
  unsigned int v200; // r10d
  __int64 v201; // r8
  unsigned int *v202; // r12
  unsigned int v203; // ebx
  char *v204; // r9
  int v205; // r8d
  _DWORD *v206; // rdi
  unsigned int v207; // ecx
  unsigned int v208; // r11d
  unsigned int v209; // edx
  int v210; // ecx
  int v211; // eax
  int v212; // ecx
  unsigned int v213; // r15d
  unsigned int v214; // r8d
  unsigned int v215; // r14d
  unsigned __int64 v216; // r13
  _DWORD *v217; // rcx
  unsigned int v218; // r11d
  unsigned int *v219; // rdi
  unsigned int v220; // ecx
  unsigned int v221; // r9d
  int v222; // eax
  __int64 v223; // rcx
  __int64 v224; // r10
  int v225; // r8d
  _QWORD *v226; // rdx
  __int64 v227; // r9
  _QWORD *v228; // r8
  unsigned __int64 v229; // r10
  unsigned __int64 v230; // rax
  int v231; // eax
  int v232; // eax
  int v233; // edx
  int v234; // r9d
  __int64 v235; // rax
  _DWORD *v236; // rcx
  unsigned __int64 v237; // r15
  unsigned int FirstIndexHash3; // eax
  unsigned int v239; // edi
  unsigned int v240; // r8d
  unsigned __int64 v241; // r14
  unsigned __int64 v242; // rax
  int v243; // r11d
  _DWORD *v244; // rdx
  int v245; // ecx
  int v246; // r11d
  unsigned int v247; // eax
  unsigned int v248; // esi
  unsigned int v249; // r12d
  _DWORD *v250; // r9
  unsigned __int64 v251; // r15
  unsigned __int64 v252; // r14
  unsigned int *v253; // rdi
  char *v254; // r10
  _QWORD *v255; // rdx
  unsigned __int64 v256; // rax
  _QWORD *v257; // r8
  signed __int64 v258; // rcx
  unsigned __int64 v259; // r9
  _DWORD *v260; // rcx
  int v261; // eax
  unsigned int v262; // eax
  __int64 v263; // rdx
  __int64 v264; // r11
  unsigned int *v265; // rax
  _DWORD *v266; // rcx
  int *v267; // r14
  unsigned int v268; // r13d
  __int64 v269; // rdx
  __int64 v270; // r15
  __int64 v271; // r8
  int v272; // eax
  _DWORD *v273; // r9
  unsigned int *v274; // rsi
  unsigned __int64 v275; // rcx
  unsigned int v276; // edi
  _DWORD *v277; // rax
  unsigned int *v278; // r12
  unsigned int *v279; // r15
  unsigned int v280; // ebx
  __int64 updated; // rax
  int v282; // r10d
  int v283; // r11d
  __int64 v284; // xmm1_8
  int v285; // r14d
  __int64 v286; // r12
  __int64 v287; // r9
  __int64 v288; // r8
  unsigned int v289; // ecx
  unsigned int v290; // edx
  unsigned int v291; // edx
  unsigned int v292; // ecx
  unsigned int v293; // r9d
  unsigned int v294; // eax
  __int64 v295; // rax
  unsigned int v296; // r8d
  unsigned int v297; // ecx
  _DWORD *v298; // r9
  __int64 v299; // rcx
  __int64 v300; // r15
  unsigned int v301; // eax
  unsigned int v302; // edi
  __int64 v303; // r13
  _DWORD *v304; // r12
  _DWORD *v305; // r14
  unsigned int v306; // esi
  int v307; // ebx
  int v308; // r8d
  int v309; // ebx
  int v310; // eax
  __int64 v311; // r8
  int v312; // eax
  _DWORD *v313; // rbx
  int v314; // r15d
  __int64 v315; // xmm0_8
  int v316; // eax
  int v317; // eax
  __int64 v318; // rbx
  __int64 v319; // r15
  int v320; // r14d
  unsigned int v321; // esi
  int v322; // r12d
  __int64 v323; // r8
  __int64 v324; // rdx
  unsigned int v325; // r15d
  unsigned int v326; // eax
  unsigned int v327; // ebx
  __int64 v328; // rax
  __int64 v329; // r8
  unsigned int *v330; // r12
  int v331; // r8d
  _DWORD *v332; // rsi
  unsigned int v333; // r10d
  _DWORD *v334; // r9
  int v335; // r11d
  unsigned int v336; // ecx
  unsigned int v337; // r11d
  unsigned int v338; // edx
  int v339; // ecx
  int v340; // eax
  int v341; // ecx
  unsigned __int64 v342; // r13
  unsigned int v343; // r11d
  unsigned int v344; // r14d
  _DWORD *v345; // rcx
  unsigned int v346; // esi
  unsigned int *v347; // rbx
  unsigned int v348; // ecx
  unsigned int v349; // r8d
  int v350; // eax
  __int64 v351; // rcx
  __int64 v352; // r9
  _QWORD *v353; // rdx
  __int64 v354; // r8
  unsigned __int64 v355; // rcx
  _QWORD *v356; // r8
  _QWORD *v357; // r9
  unsigned __int64 v358; // rax
  int v359; // ecx
  __int64 v360; // rax
  _DWORD *v361; // rcx
  int v362; // eax
  int v363; // edx
  int v364; // r9d
  unsigned int v365; // r14d
  unsigned __int64 v366; // r9
  _DWORD *v367; // r15
  _DWORD *v368; // r12
  unsigned int *v369; // rsi
  __int64 v370; // r11
  _QWORD *v371; // rdx
  unsigned __int64 v372; // rax
  char *v373; // rbx
  _QWORD *v374; // r8
  unsigned __int64 v375; // rcx
  unsigned __int64 v376; // r9
  _DWORD *v377; // rcx
  int v378; // eax
  unsigned int v379; // eax
  __int64 v380; // rdx
  _DWORD *v381; // rax
  unsigned int v382; // eax
  int *v383; // rax
  _DWORD *v384; // rax
  unsigned int v385; // ebx
  __int64 v386; // rax
  __int64 v387; // r8
  unsigned int *v388; // r12
  int v389; // r8d
  _DWORD *v390; // rsi
  unsigned int v391; // r10d
  _DWORD *v392; // r9
  int v393; // r11d
  unsigned int v394; // ecx
  unsigned int v395; // r11d
  unsigned int v396; // edx
  int v397; // ecx
  int v398; // eax
  int v399; // ecx
  unsigned __int64 v400; // r13
  unsigned int v401; // r11d
  unsigned int v402; // r14d
  _DWORD *v403; // rcx
  unsigned int v404; // esi
  unsigned int *v405; // rbx
  unsigned int v406; // ecx
  unsigned int v407; // r8d
  int v408; // eax
  __int64 v409; // rcx
  __int64 v410; // r9
  _QWORD *v411; // rdx
  __int64 v412; // r8
  unsigned __int64 v413; // rcx
  _QWORD *v414; // r8
  _QWORD *v415; // r9
  unsigned __int64 v416; // rax
  int v417; // ecx
  __int64 v418; // rax
  _DWORD *v419; // rcx
  int v420; // eax
  int v421; // edx
  int v422; // r9d
  unsigned int v423; // r14d
  unsigned __int64 v424; // r9
  _DWORD *v425; // r15
  _DWORD *v426; // r12
  unsigned int *v427; // rsi
  __int64 v428; // r11
  _QWORD *v429; // rdx
  unsigned __int64 v430; // rax
  char *v431; // rbx
  _QWORD *v432; // r8
  unsigned __int64 v433; // rcx
  unsigned __int64 v434; // r9
  _DWORD *v435; // rcx
  int v436; // eax
  unsigned int v437; // eax
  __int64 v438; // rdx
  _DWORD *v439; // rax
  unsigned int v440; // ebx
  __int64 v441; // rax
  __int64 v442; // r8
  unsigned int *v443; // r12
  int v444; // r8d
  _DWORD *v445; // rsi
  unsigned int v446; // r10d
  _DWORD *v447; // r9
  int v448; // r11d
  unsigned int v449; // ecx
  unsigned int v450; // r11d
  unsigned int v451; // edx
  int v452; // ecx
  int v453; // eax
  int v454; // ecx
  unsigned __int64 v455; // r13
  unsigned int v456; // r11d
  unsigned int v457; // r14d
  _DWORD *v458; // rcx
  unsigned int v459; // esi
  unsigned int *v460; // rbx
  unsigned int v461; // ecx
  unsigned int v462; // r8d
  int v463; // eax
  __int64 v464; // rcx
  __int64 v465; // r9
  _QWORD *v466; // rdx
  __int64 v467; // r8
  unsigned __int64 v468; // rcx
  _QWORD *v469; // r8
  _QWORD *v470; // r9
  unsigned __int64 v471; // rax
  int v472; // ecx
  __int64 v473; // rax
  _DWORD *v474; // rcx
  int v475; // eax
  int v476; // edx
  int v477; // r9d
  int v478; // r14d
  unsigned __int64 v479; // r9
  _DWORD *v480; // r15
  _DWORD *v481; // r12
  unsigned int *v482; // rsi
  __int64 v483; // r11
  _QWORD *v484; // rdx
  unsigned __int64 v485; // rax
  char *v486; // rbx
  _QWORD *v487; // r8
  unsigned __int64 v488; // rcx
  unsigned __int64 v489; // r9
  _DWORD *v490; // rcx
  int v491; // eax
  unsigned int v492; // eax
  __int64 v493; // rdx
  _DWORD *v494; // rax
  unsigned int v495; // r14d
  unsigned int v496; // r10d
  __int64 v497; // rax
  unsigned int v498; // r10d
  __int64 v499; // r8
  unsigned int *v500; // r13
  unsigned int v501; // ebx
  int v502; // r8d
  _DWORD *v503; // rsi
  unsigned int v504; // ecx
  unsigned int v505; // r11d
  unsigned int v506; // edx
  int v507; // ecx
  int v508; // eax
  int v509; // ecx
  unsigned int v510; // r8d
  unsigned int v511; // r12d
  unsigned int v512; // r11d
  _DWORD *v513; // rcx
  unsigned int v514; // r15d
  unsigned int *v515; // rsi
  unsigned int v516; // ecx
  unsigned int v517; // r9d
  int v518; // eax
  __int64 v519; // rcx
  __int64 v520; // r10
  int v521; // r8d
  _QWORD *v522; // rdx
  __int64 v523; // r9
  _QWORD *v524; // r8
  _DWORD *v525; // r10
  unsigned __int64 v526; // rax
  int v527; // eax
  int v528; // edx
  int v529; // r9d
  __int64 v530; // rax
  _DWORD *v531; // rcx
  unsigned __int64 v532; // r15
  _DWORD *v533; // r12
  unsigned int v534; // eax
  unsigned int v535; // esi
  unsigned int v536; // r8d
  unsigned __int64 v537; // rax
  int v538; // r11d
  _DWORD *v539; // rdx
  int v540; // ecx
  int v541; // r11d
  unsigned int v542; // eax
  int v543; // r14d
  unsigned __int64 v544; // r9
  _DWORD *v545; // r12
  _DWORD *v546; // r13
  unsigned int *v547; // rsi
  unsigned __int64 v548; // r10
  _QWORD *v549; // rdx
  unsigned __int64 v550; // rax
  _QWORD *v551; // r8
  signed __int64 v552; // rcx
  unsigned __int64 v553; // r9
  _DWORD *v554; // rcx
  int v555; // eax
  unsigned int v556; // eax
  __int64 v557; // rdx
  __int64 v558; // r11
  char *v559; // rax
  _DWORD *v560; // rsi
  unsigned int v561; // ecx
  unsigned int v562; // r13d
  unsigned int *v563; // r10
  int v564; // r14d
  __int64 v565; // rax
  _DWORD *v566; // r10
  int v567; // r11d
  unsigned int v568; // edx
  __int64 v569; // xmm1_8
  int v570; // r12d
  unsigned int v571; // esi
  __int64 v572; // r13
  unsigned int v573; // eax
  __int64 v574; // r10
  __int64 v575; // r9
  unsigned int v576; // ecx
  signed int v577; // r8d
  __int64 v578; // rcx
  unsigned int v579; // r8d
  int v580; // r10d
  unsigned int v581; // ecx
  __int64 v582; // rcx
  __int64 v583; // rdx
  unsigned int v584; // r9d
  unsigned int v585; // ecx
  __int64 v586; // rdx
  unsigned int v587; // ecx
  unsigned int v588; // r10d
  __int64 v589; // rax
  int v590; // eax
  unsigned int v591; // edi
  _DWORD *v592; // rdx
  __int64 v593; // rdx
  __int128 v594; // xmm0
  unsigned int v595; // eax
  int v596; // eax
  unsigned int v597; // r12d
  unsigned int v598; // esi
  __int64 v599; // rcx
  int v600; // eax
  _DWORD *v601; // r8
  __int128 v602; // xmm0
  __int64 v603; // xmm1_8
  __int64 v604; // rdx
  __int64 v605; // r8
  unsigned int v606; // ecx
  unsigned int v607; // eax
  unsigned __int64 v608; // r8
  __int64 v609; // rcx
  int v610; // ebx
  __int64 v611; // rdx
  unsigned int v612; // edi
  unsigned int v613; // r15d
  unsigned int v614; // ecx
  __int64 v615; // rcx
  int v616; // r8d
  unsigned int v617; // r14d
  unsigned __int64 v618; // rdx
  unsigned __int64 v619; // rbx
  __int64 v620; // rcx
  unsigned __int64 v621; // rdx
  __int64 v622; // rcx
  unsigned __int64 v623; // rax
  __int64 v624; // rcx
  unsigned __int64 v625; // rcx
  __int64 v626; // rcx
  unsigned __int64 v627; // rax
  __int64 v628; // rcx
  __int64 v629; // rcx
  __int64 v630; // rcx
  unsigned int v632; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v633; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v634; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v635; // [rsp+40h] [rbp-C0h]
  _DWORD *v636; // [rsp+48h] [rbp-B8h]
  unsigned int *v637; // [rsp+50h] [rbp-B0h]
  BOOL v638; // [rsp+58h] [rbp-A8h]
  _DWORD *v639; // [rsp+60h] [rbp-A0h]
  unsigned int v640; // [rsp+68h] [rbp-98h]
  unsigned int v641; // [rsp+6Ch] [rbp-94h]
  char *v642; // [rsp+70h] [rbp-90h]
  unsigned int v643; // [rsp+78h] [rbp-88h]
  int v644; // [rsp+7Ch] [rbp-84h]
  _DWORD *v645; // [rsp+80h] [rbp-80h]
  unsigned __int64 v646; // [rsp+88h] [rbp-78h]
  unsigned int v647; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v648; // [rsp+94h] [rbp-6Ch] BYREF
  _DWORD *v649; // [rsp+98h] [rbp-68h]
  unsigned __int64 v650; // [rsp+A0h] [rbp-60h]
  _DWORD *v651; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v652; // [rsp+B0h] [rbp-50h]
  int v653; // [rsp+B8h] [rbp-48h]
  int v654; // [rsp+BCh] [rbp-44h] BYREF
  unsigned __int64 v655; // [rsp+C0h] [rbp-40h]
  __int64 v656; // [rsp+C8h] [rbp-38h]
  int v657; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v658; // [rsp+D8h] [rbp-28h]
  int v659; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v660; // [rsp+E4h] [rbp-1Ch]
  int v661; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v662; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v663; // [rsp+F8h] [rbp-8h]
  char v664; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 v665; // [rsp+108h] [rbp+8h]
  __int128 v666; // [rsp+110h] [rbp+10h]
  __int64 v667; // [rsp+120h] [rbp+20h]
  int v668; // [rsp+128h] [rbp+28h]
  int v669; // [rsp+138h] [rbp+38h]
  __int128 v670; // [rsp+140h] [rbp+40h] BYREF
  __int64 v671; // [rsp+150h] [rbp+50h]
  int v672; // [rsp+158h] [rbp+58h]
  __int128 v673; // [rsp+160h] [rbp+60h] BYREF
  __int64 v674; // [rsp+170h] [rbp+70h]
  int v675; // [rsp+178h] [rbp+78h]
  __int128 v676; // [rsp+180h] [rbp+80h] BYREF
  __int64 v677; // [rsp+190h] [rbp+90h]
  int v678; // [rsp+198h] [rbp+98h]
  char v679[16]; // [rsp+1A0h] [rbp+A0h] BYREF
  char v680[24]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int64 v684; // [rsp+228h] [rbp+128h]
  unsigned int v685; // [rsp+230h] [rbp+130h]
  unsigned int v686; // [rsp+230h] [rbp+130h]
  unsigned int *v687; // [rsp+230h] [rbp+130h]
  unsigned int v688; // [rsp+230h] [rbp+130h]

  v684 = a4;
  v5 = a1;
  v6 = a1 + 72;
  v7 = 4095;
  v8 = a4;
  v656 = v6;
  v9 = *(_DWORD *)(v5 + 204);
  v10 = a4 + a5;
  v11 = a4 + a5 - 8;
  v12 = *(_QWORD *)(v5 + 8) + *(unsigned int *)(v5 + 24);
  v635 = a4 + a5;
  v665 = v11;
  if ( v9 < 0xFFF )
    v7 = v9;
  v13 = *(_DWORD *)(v5 + 200) == 3;
  v660 = v7;
  v653 = !v13 + 3;
  v659 = *(_DWORD *)(v5 + 36);
  v651 = *(_DWORD **)(v6 + 40);
  v645 = *(_DWORD **)(v6 + 32);
  ZSTD_rescaleFreqs(v6, a4, a5, 2);
  v14 = v8 + (v8 == v12);
  v646 = v14;
  if ( v14 < v11 )
  {
    v15 = v667;
    v661 = v668;
    do
    {
      v16 = *(unsigned int *)(v5 + 36);
      v17 = *(_QWORD *)(v5 + 8);
      v18 = *(_DWORD *)(v5 + 200);
      v19 = v14 == v8;
      v648 = v14 - v8;
      v638 = v19;
      if ( v14 < v17 + v16 )
        goto LABEL_749;
      v20 = v14 - v17;
      if ( (unsigned int)v16 < (int)v14 - (int)v17 )
      {
        do
          LODWORD(v16) = ZSTD_insertBt1(v5, (int)v17 + (int)v16, v10, v18, 0) + v16;
        while ( (unsigned int)v16 < v20 );
        v19 = v638;
        v14 = v646;
      }
      v21 = *(_QWORD *)(v5 + 48);
      *(_DWORD *)(v5 + 36) = v20;
      v22 = *(unsigned int *)(v5 + 192);
      if ( v18 != 3 )
      {
        v23 = 4095;
        if ( v18 != 5 )
        {
          v24 = *(_DWORD *)(v5 + 204);
          if ( (unsigned int)(v18 - 6) <= 1 )
          {
            if ( v24 < 0xFFF )
              v23 = *(_DWORD *)(v5 + 204);
            v25 = v14 - *(_QWORD *)(v5 + 8);
            v642 = *(char **)(v5 + 8);
            v640 = v25;
            v26 = ZSTD_hash6Ptr(v14, v22, v21);
            v28 = (unsigned int *)(v27 + 4 * v26);
            v29 = *(_DWORD *)(v5 + 28);
            v30 = *(_DWORD *)(v5 + 188) - 1;
            v31 = *(_DWORD **)(v5 + 64);
            v32 = *v28;
            v639 = v33;
            v34 = 1 << v30;
            v35 = 0;
            v36 = 0;
            v649 = v31;
            v37 = v34 - 1;
            v636 = 0;
            v633 = v37;
            if ( v37 < v25 )
              v36 = v25 - v37;
            v634 = v36;
            v38 = 1 << *(_DWORD *)(v5 + 184);
            v39 = v25 - v38;
            v40 = 1;
            if ( v25 - v29 <= v38 )
              v39 = v29;
            if ( *(_DWORD *)(v5 + 32) )
              v39 = v29;
            if ( v39 )
              v40 = v39;
            v41 = *(_DWORD *)(v5 + 196);
            v641 = v40;
            v685 = 0;
            v42 = &v31[2 * (v25 & v37)];
            v637 = v42 + 1;
            v632 = v25 + 9;
            v644 = 1 << v41;
            v43 = v25 - *(_DWORD *)(a1 + 24);
            v44 = (unsigned int)(v653 - 1);
            v45 = a3;
            v655 = v44;
            v46 = v638;
            v47 = v638 + 3;
            v48 = &a3[v638];
            while ( 1 )
            {
              if ( v46 == 3 )
                v49 = *v45 - 1;
              else
                v49 = *v48;
              v50 = 0;
              if ( v49 - 1 >= v43 )
                goto LABEL_47;
              MINMATCH = ZSTD_readMINMATCH(v646, 4, 0, -(__int64)v49);
              if ( MINMATCH == *(_DWORD *)(v53 + v52) )
                break;
LABEL_46:
              v35 = v685;
LABEL_47:
              if ( v50 > v44 )
              {
                v44 = v50;
                v61 = v35++;
                v62 = &v645[2 * v61];
                v62[1] = v50;
                *v62 = v46 - v638;
                v685 = v35;
                if ( v50 > v23 || v50 + v646 == v635 )
                  goto LABEL_78;
              }
              v45 = a3;
              ++v46;
              ++v48;
              if ( v46 >= v47 )
              {
                v66 = v644;
                *v28 = v640;
                while ( v66 )
                {
                  --v66;
                  if ( v32 < v641 )
                    break;
                  v67 = v636;
                  v68 = v646;
                  if ( v639 < v636 )
                    v67 = v639;
                  v69 = v635;
                  v70 = &v649[2 * (v32 & v633)];
                  v71 = &v642[v32];
                  v72 = (_QWORD *)((char *)v67 + v646);
                  v73 = v635 - 7;
                  v74 = (char *)v67 + v646;
                  v75 = (_QWORD *)((char *)v67 + (_QWORD)v71);
                  if ( (unsigned __int64)v67 + v646 >= v635 - 7 )
                    goto LABEL_62;
                  if ( *v75 != *v72 )
                  {
                    v76 = (unsigned int)ZSTD_NbCommonBytes(*v75 ^ *v72, v72, v75, v67);
                    goto LABEL_72;
                  }
                  ++v72;
                  ++v75;
                  if ( (unsigned __int64)v72 >= v73 )
                  {
LABEL_62:
                    if ( (unsigned __int64)v72 < v635 - 3 && *(_DWORD *)v75 == *(_DWORD *)v72 )
                    {
                      v72 = (_QWORD *)((char *)v72 + 4);
                      v75 = (_QWORD *)((char *)v75 + 4);
                    }
                    if ( (unsigned __int64)v72 < v635 - 1 && *(_WORD *)v75 == *(_WORD *)v72 )
                    {
                      v72 = (_QWORD *)((char *)v72 + 2);
                      v75 = (_QWORD *)((char *)v75 + 2);
                    }
                    if ( (unsigned __int64)v72 < v635 && *(_BYTE *)v75 == *(_BYTE *)v72 )
                      v72 = (_QWORD *)((char *)v72 + 1);
                    v76 = (char *)v72 - v74;
                  }
                  else
                  {
                    while ( *v75 == *v72 )
                    {
                      ++v72;
                      ++v75;
                      if ( (unsigned __int64)v72 >= v73 )
                        goto LABEL_62;
                    }
                    v83 = ZSTD_NbCommonBytes(*v75 ^ *v72, v72, v75, v67);
                    v76 = v84 - (_QWORD)v74 + v83;
                  }
LABEL_72:
                  v77 = (unsigned __int64)v67 + v76;
                  if ( v77 > v44 )
                  {
                    if ( v77 > v632 - v32 )
                      v632 = v32 + v77;
                    v44 = v77;
                    v78 = v645;
                    v79 = v640 - v32 + 2;
                    v645[2 * v685 + 1] = v77;
                    v78[2 * v685++] = v79;
                    if ( v77 > 0x1000 || v77 + v68 == v69 )
                      break;
                  }
                  if ( (unsigned __int8)v71[v77] >= *(_BYTE *)(v77 + v68) )
                  {
                    v636 = (_DWORD *)v77;
                    *v637 = v32;
                    if ( v32 <= v634 )
                    {
                      v80 = &v634;
                      goto LABEL_77;
                    }
                    v32 = *v70;
                    v637 = v70;
                  }
                  else
                  {
                    *v42 = v32;
                    v639 = (_DWORD *)v77;
                    if ( v32 <= v634 )
                    {
                      v42 = &v634;
                      break;
                    }
                    v32 = v70[1];
                    v42 = v70 + 1;
                  }
                }
LABEL_76:
                v80 = v637;
LABEL_77:
                *v80 = 0;
                v81 = v632 - 8;
                *v42 = 0;
                *(_DWORD *)(a1 + 36) = v81;
LABEL_78:
                v82 = v685;
                goto LABEL_327;
              }
            }
            v54 = (_QWORD *)(v52 + 4);
            v55 = v52 + 4;
            v56 = v635;
            v57 = (_QWORD *)(v53 + v55);
            v58 = v54;
            v59 = v635 - 7;
            if ( (unsigned __int64)v54 < v635 - 7 )
            {
              if ( *v57 != *v54 )
              {
                v60 = ZSTD_NbCommonBytes(*v57 ^ *v54, v54, v57, v54);
LABEL_45:
                v50 = v60 + 4;
                goto LABEL_46;
              }
              ++v54;
              ++v57;
              if ( (unsigned __int64)v54 < v59 )
              {
                while ( *v57 == *v54 )
                {
                  ++v54;
                  ++v57;
                  if ( (unsigned __int64)v54 >= v59 )
                    goto LABEL_34;
                }
                v63 = ZSTD_NbCommonBytes(*v57 ^ *v54, v54, v57, v58);
                v60 = v64 - v65 + v63;
                goto LABEL_45;
              }
LABEL_34:
              v56 = v635;
            }
            if ( (unsigned __int64)v54 < v56 - 3 && *(_DWORD *)v57 == *(_DWORD *)v54 )
            {
              v54 = (_QWORD *)((char *)v54 + 4);
              v57 = (_QWORD *)((char *)v57 + 4);
            }
            if ( (unsigned __int64)v54 < v56 - 1 && *(_WORD *)v57 == *(_WORD *)v54 )
            {
              v54 = (_QWORD *)((char *)v54 + 2);
              v57 = (_QWORD *)((char *)v57 + 2);
            }
            if ( (unsigned __int64)v54 < v56 && *(_BYTE *)v57 == *(_BYTE *)v54 )
              LODWORD(v54) = (_DWORD)v54 + 1;
            v60 = (_DWORD)v54 - (_DWORD)v58;
            goto LABEL_45;
          }
          if ( v24 < 0xFFF )
            v23 = *(_DWORD *)(v5 + 204);
          v85 = v14 - *(_QWORD *)(v5 + 8);
          v642 = *(char **)(v5 + 8);
          v640 = v85;
          v86 = ZSTD_hash4Ptr(v14, v22, v21);
          v88 = (unsigned int *)(v87 + 4 * v86);
          v89 = *(_DWORD *)(v5 + 28);
          v90 = *(_DWORD *)(v5 + 188) - 1;
          v91 = *(_DWORD **)(v5 + 64);
          v92 = *v88;
          v639 = v93;
          v94 = 1 << v90;
          v95 = 0;
          v96 = 0;
          v649 = v91;
          v97 = v94 - 1;
          v636 = 0;
          v633 = v97;
          if ( v97 < v85 )
            v96 = v85 - v97;
          v634 = v96;
          v98 = 1 << *(_DWORD *)(v5 + 184);
          v99 = v85 - v98;
          v100 = 1;
          if ( v85 - v89 <= v98 )
            v99 = v89;
          if ( *(_DWORD *)(v5 + 32) )
            v99 = v89;
          if ( v99 )
            v100 = v99;
          v101 = *(_DWORD *)(v5 + 196);
          v641 = v100;
          v685 = 0;
          v42 = &v91[2 * (v85 & v97)];
          v637 = v42 + 1;
          v632 = v85 + 9;
          v644 = 1 << v101;
          v102 = v85 - *(_DWORD *)(a1 + 24);
          v103 = (unsigned int)(v653 - 1);
          v104 = a3;
          v655 = v103;
          v105 = v638;
          v106 = v638 + 3;
          v107 = &a3[v638];
          while ( 1 )
          {
            if ( v105 == 3 )
              v108 = *v104 - 1;
            else
              v108 = *v107;
            v109 = 0;
            if ( v108 - 1 >= v102 )
              goto LABEL_124;
            v110 = ZSTD_readMINMATCH(v646, 4, 0, -(__int64)v108);
            if ( v110 == *(_DWORD *)(v112 + v111) )
              break;
LABEL_123:
            v95 = v685;
LABEL_124:
            if ( v109 > v103 )
            {
              v103 = v109;
              v120 = v95++;
              v121 = &v645[2 * v120];
              v121[1] = v109;
              *v121 = v105 - v638;
              v685 = v95;
              if ( v109 > v23 || v109 + v646 == v635 )
                goto LABEL_78;
            }
            v104 = a3;
            ++v105;
            ++v107;
            if ( v105 >= v106 )
            {
              v125 = v644;
              *v88 = v640;
              if ( !v125 )
                goto LABEL_76;
              while ( 2 )
              {
                --v125;
                if ( v92 < v641 )
                  goto LABEL_76;
                v126 = v636;
                v127 = v646;
                if ( v639 < v636 )
                  v126 = v639;
                v128 = v635;
                v129 = &v649[2 * (v92 & v633)];
                v130 = &v642[v92];
                v131 = (_QWORD *)((char *)v126 + v646);
                v132 = v635 - 7;
                v133 = (char *)v126 + v646;
                v134 = (_QWORD *)((char *)v126 + (_QWORD)v130);
                if ( (unsigned __int64)v126 + v646 < v635 - 7 )
                {
                  if ( *v134 != *v131 )
                  {
                    v135 = (unsigned int)ZSTD_NbCommonBytes(*v134 ^ *v131, v131, v134, v126);
LABEL_149:
                    v136 = (unsigned __int64)v126 + v135;
                    if ( v136 > v103 )
                    {
                      if ( v136 > v632 - v92 )
                        v632 = v92 + v136;
                      v103 = v136;
                      v137 = v645;
                      v138 = v640 - v92 + 2;
                      v645[2 * v685 + 1] = v136;
                      v137[2 * v685++] = v138;
                      if ( v136 > 0x1000 || v136 + v127 == v128 )
                        goto LABEL_76;
                    }
                    if ( (unsigned __int8)v130[v136] >= *(_BYTE *)(v136 + v127) )
                    {
                      v636 = (_DWORD *)v136;
                      *v637 = v92;
                      if ( v92 <= v634 )
                      {
                        v80 = &v633;
                        goto LABEL_77;
                      }
                      v92 = *v129;
                      v637 = v129;
                    }
                    else
                    {
                      *v42 = v92;
                      v639 = (_DWORD *)v136;
                      if ( v92 <= v634 )
                      {
                        v42 = &v633;
                        goto LABEL_76;
                      }
                      v92 = v129[1];
                      v42 = v129 + 1;
                    }
                    if ( !v125 )
                      goto LABEL_76;
                    continue;
                  }
                  ++v131;
                  ++v134;
                  if ( (unsigned __int64)v131 < v132 )
                  {
                    while ( *v134 == *v131 )
                    {
                      ++v131;
                      ++v134;
                      if ( (unsigned __int64)v131 >= v132 )
                        goto LABEL_139;
                    }
                    v139 = ZSTD_NbCommonBytes(*v134 ^ *v131, v131, v134, v126);
                    v135 = v140 - (_QWORD)v133 + v139;
                    goto LABEL_149;
                  }
                }
                break;
              }
LABEL_139:
              if ( (unsigned __int64)v131 < v635 - 3 && *(_DWORD *)v134 == *(_DWORD *)v131 )
              {
                v131 = (_QWORD *)((char *)v131 + 4);
                v134 = (_QWORD *)((char *)v134 + 4);
              }
              if ( (unsigned __int64)v131 < v635 - 1 && *(_WORD *)v134 == *(_WORD *)v131 )
              {
                v131 = (_QWORD *)((char *)v131 + 2);
                v134 = (_QWORD *)((char *)v134 + 2);
              }
              if ( (unsigned __int64)v131 < v635 && *(_BYTE *)v134 == *(_BYTE *)v131 )
                v131 = (_QWORD *)((char *)v131 + 1);
              v135 = (char *)v131 - v133;
              goto LABEL_149;
            }
          }
          v113 = (_QWORD *)(v111 + 4);
          v114 = v111 + 4;
          v115 = v635;
          v116 = (_QWORD *)(v112 + v114);
          v117 = v113;
          v118 = v635 - 7;
          if ( (unsigned __int64)v113 < v635 - 7 )
          {
            if ( *v116 != *v113 )
            {
              v119 = ZSTD_NbCommonBytes(*v116 ^ *v113, v113, v116, v113);
LABEL_122:
              v109 = v119 + 4;
              goto LABEL_123;
            }
            ++v113;
            ++v116;
            if ( (unsigned __int64)v113 < v118 )
            {
              while ( *v116 == *v113 )
              {
                ++v113;
                ++v116;
                if ( (unsigned __int64)v113 >= v118 )
                  goto LABEL_111;
              }
              v122 = ZSTD_NbCommonBytes(*v116 ^ *v113, v113, v116, v117);
              v119 = v123 - v124 + v122;
              goto LABEL_122;
            }
LABEL_111:
            v115 = v635;
          }
          if ( (unsigned __int64)v113 < v115 - 3 && *(_DWORD *)v116 == *(_DWORD *)v113 )
          {
            v113 = (_QWORD *)((char *)v113 + 4);
            v116 = (_QWORD *)((char *)v116 + 4);
          }
          if ( (unsigned __int64)v113 < v115 - 1 && *(_WORD *)v116 == *(_WORD *)v113 )
          {
            v113 = (_QWORD *)((char *)v113 + 2);
            v116 = (_QWORD *)((char *)v116 + 2);
          }
          if ( (unsigned __int64)v113 < v115 && *(_BYTE *)v116 == *(_BYTE *)v113 )
            LODWORD(v113) = (_DWORD)v113 + 1;
          v119 = (_DWORD)v113 - (_DWORD)v117;
          goto LABEL_122;
        }
        if ( *(_DWORD *)(v5 + 204) < 0xFFFu )
          v23 = *(_DWORD *)(v5 + 204);
        v141 = v14 - *(_QWORD *)(v5 + 8);
        v642 = *(char **)(v5 + 8);
        v640 = v141;
        v142 = ZSTD_hash5Ptr(v14, v22, v21);
        v144 = (unsigned int *)(v143 + 4 * v142);
        v145 = *(_DWORD *)(v5 + 28);
        v146 = *(_DWORD *)(v5 + 188) - 1;
        v147 = *(_DWORD **)(v5 + 64);
        v148 = *v144;
        v639 = v149;
        v150 = 1 << v146;
        v151 = 0;
        v152 = 0;
        v649 = v147;
        v153 = v150 - 1;
        v636 = 0;
        v633 = v153;
        if ( v153 < v141 )
          v152 = v141 - v153;
        v634 = v152;
        v154 = 1 << *(_DWORD *)(v5 + 184);
        v155 = v141 - v154;
        v156 = 1;
        if ( v141 - v145 <= v154 )
          v155 = v145;
        if ( *(_DWORD *)(v5 + 32) )
          v155 = v145;
        if ( v155 )
          v156 = v155;
        v157 = *(_DWORD *)(v5 + 196);
        v641 = v156;
        v685 = 0;
        v42 = &v147[2 * (v141 & v153)];
        v637 = v42 + 1;
        v632 = v141 + 9;
        v644 = 1 << v157;
        v158 = v141 - *(_DWORD *)(a1 + 24);
        v159 = (unsigned int)(v653 - 1);
        v160 = a3;
        v655 = v159;
        v161 = v638;
        v162 = v638 + 3;
        v163 = &a3[v638];
        while ( 1 )
        {
          if ( v161 == 3 )
            v164 = *v160 - 1;
          else
            v164 = *v163;
          v165 = 0;
          if ( v164 - 1 >= v158 )
            goto LABEL_199;
          v166 = ZSTD_readMINMATCH(v646, 4, 0, -(__int64)v164);
          if ( v166 == *(_DWORD *)(v168 + v167) )
            break;
LABEL_198:
          v151 = v685;
LABEL_199:
          if ( v165 > v159 )
          {
            v159 = v165;
            v176 = v151++;
            v177 = &v645[2 * v176];
            v177[1] = v165;
            *v177 = v161 - v638;
            v685 = v151;
            if ( v165 > v23 || v165 + v646 == v635 )
              goto LABEL_78;
          }
          v160 = a3;
          ++v161;
          ++v163;
          if ( v161 >= v162 )
          {
            v181 = v644;
            *v144 = v640;
            if ( !v181 )
              goto LABEL_76;
            while ( 2 )
            {
              --v181;
              if ( v148 < v641 )
                goto LABEL_76;
              v182 = v636;
              v183 = v646;
              if ( v639 < v636 )
                v182 = v639;
              v184 = v635;
              v185 = &v649[2 * (v148 & v633)];
              v186 = &v642[v148];
              v187 = (_QWORD *)((char *)v182 + v646);
              v188 = v635 - 7;
              v189 = (char *)v182 + v646;
              v190 = (_QWORD *)((char *)v182 + (_QWORD)v186);
              if ( (unsigned __int64)v182 + v646 < v635 - 7 )
              {
                if ( *v187 != *v190 )
                {
                  v191 = (unsigned int)ZSTD_NbCommonBytes(*v187 ^ *v190, v187, v190, v182);
LABEL_224:
                  v192 = (unsigned __int64)v182 + v191;
                  if ( v192 > v159 )
                  {
                    if ( v192 > v632 - v148 )
                      v632 = v192 + v148;
                    v159 = v192;
                    v193 = v645;
                    v194 = v640 - v148 + 2;
                    v645[2 * v685 + 1] = v192;
                    v193[2 * v685++] = v194;
                    if ( v192 > 0x1000 || v192 + v183 == v184 )
                      goto LABEL_76;
                  }
                  if ( (unsigned __int8)v186[v192] >= *(_BYTE *)(v192 + v183) )
                  {
                    v636 = (_DWORD *)v192;
                    *v637 = v148;
                    if ( v148 <= v634 )
                    {
                      v80 = &v647;
                      goto LABEL_77;
                    }
                    v148 = *v185;
                    v637 = v185;
                  }
                  else
                  {
                    *v42 = v148;
                    v639 = (_DWORD *)v192;
                    if ( v148 <= v634 )
                    {
                      v42 = &v647;
                      goto LABEL_76;
                    }
                    v148 = v185[1];
                    v42 = v185 + 1;
                  }
                  if ( !v181 )
                    goto LABEL_76;
                  continue;
                }
                ++v187;
                ++v190;
                if ( (unsigned __int64)v187 < v188 )
                {
                  while ( *v187 == *v190 )
                  {
                    ++v187;
                    ++v190;
                    if ( (unsigned __int64)v187 >= v188 )
                      goto LABEL_214;
                  }
                  v195 = ZSTD_NbCommonBytes(*v187 ^ *v190, v187, v190, v182);
                  v191 = v196 - (_QWORD)v189 + v195;
                  goto LABEL_224;
                }
              }
              break;
            }
LABEL_214:
            if ( (unsigned __int64)v187 < v635 - 3 && *(_DWORD *)v190 == *(_DWORD *)v187 )
            {
              v187 = (_QWORD *)((char *)v187 + 4);
              v190 = (_QWORD *)((char *)v190 + 4);
            }
            if ( (unsigned __int64)v187 < v635 - 1 && *(_WORD *)v190 == *(_WORD *)v187 )
            {
              v187 = (_QWORD *)((char *)v187 + 2);
              v190 = (_QWORD *)((char *)v190 + 2);
            }
            if ( (unsigned __int64)v187 < v635 && *(_BYTE *)v190 == *(_BYTE *)v187 )
              v187 = (_QWORD *)((char *)v187 + 1);
            v191 = (char *)v187 - v189;
            goto LABEL_224;
          }
        }
        v169 = (_QWORD *)(v167 + 4);
        v170 = v167 + 4;
        v171 = v635;
        v172 = (_QWORD *)(v168 + v170);
        v173 = v169;
        v174 = v635 - 7;
        if ( (unsigned __int64)v169 < v635 - 7 )
        {
          if ( *v169 != *v172 )
          {
            v175 = ZSTD_NbCommonBytes(*v169 ^ *v172, v169, v172, v169);
LABEL_197:
            v165 = v175 + 4;
            goto LABEL_198;
          }
          ++v169;
          ++v172;
          if ( (unsigned __int64)v169 < v174 )
          {
            while ( *v169 == *v172 )
            {
              ++v169;
              ++v172;
              if ( (unsigned __int64)v169 >= v174 )
                goto LABEL_186;
            }
            v178 = ZSTD_NbCommonBytes(*v169 ^ *v172, v169, v172, v173);
            v175 = v179 - v180 + v178;
            goto LABEL_197;
          }
LABEL_186:
          v171 = v635;
        }
        if ( (unsigned __int64)v169 < v171 - 3 && *(_DWORD *)v172 == *(_DWORD *)v169 )
        {
          v169 = (_QWORD *)((char *)v169 + 4);
          v172 = (_QWORD *)((char *)v172 + 4);
        }
        if ( (unsigned __int64)v169 < v171 - 1 && *(_WORD *)v172 == *(_WORD *)v169 )
        {
          v169 = (_QWORD *)((char *)v169 + 2);
          v172 = (_QWORD *)((char *)v172 + 2);
        }
        if ( (unsigned __int64)v169 < v171 && *(_BYTE *)v172 == *(_BYTE *)v169 )
          LODWORD(v169) = (_DWORD)v169 + 1;
        v175 = (_DWORD)v169 - (_DWORD)v173;
        goto LABEL_197;
      }
      v197 = 4095;
      if ( *(_DWORD *)(v5 + 204) < 0xFFFu )
        v197 = *(_DWORD *)(v5 + 204);
      v198 = v14 - *(_QWORD *)(v5 + 8);
      v636 = *(_DWORD **)(v5 + 8);
      v633 = v198;
      v199 = ZSTD_hash4Ptr(v14, v22, v21);
      v202 = (unsigned int *)(v201 + 4 * v199);
      v203 = *v202;
      v642 = v204;
      v205 = *(_DWORD *)(a1 + 28);
      v206 = *(_DWORD **)(a1 + 64);
      v207 = 0;
      v208 = (1 << (*(_DWORD *)(a1 + 188) - 1)) - 1;
      v649 = v206;
      v644 = v208;
      v650 = 0;
      if ( v208 < v200 )
        v207 = v200 - v208;
      v640 = v207;
      v209 = 1 << *(_DWORD *)(a1 + 184);
      v210 = v200 - v209;
      v211 = 1;
      if ( v200 - v205 <= v209 )
        v210 = v205;
      if ( *(_DWORD *)(a1 + 32) )
        v210 = v205;
      if ( v210 )
        v211 = v210;
      v212 = *(_DWORD *)(a1 + 196);
      v643 = v211;
      v686 = 0;
      v213 = v19 + 3;
      v214 = 0;
      v637 = &v206[2 * (v200 & v208)];
      v639 = v637 + 1;
      v632 = v200 + 9;
      v647 = 1 << v212;
      v215 = v200 - *(_DWORD *)(a1 + 24);
      v216 = (unsigned int)(v653 - 1);
      v217 = a3;
      v655 = v216;
      v218 = v638;
      v219 = &a3[v638];
      while ( 1 )
      {
        if ( v218 == 3 )
          v220 = *v217 - 1;
        else
          v220 = *v219;
        v221 = 0;
        if ( v220 - 1 >= v215 )
          goto LABEL_273;
        v669 = 1;
        v222 = ZSTD_readMINMATCH(v646, 3, (unsigned int)(*(_DWORD *)(v646 - v220) << 8), 0);
        if ( v222 != v225 )
        {
          v214 = v686;
LABEL_273:
          v229 = v635;
          goto LABEL_274;
        }
        v226 = (_QWORD *)(v223 + 3);
        v227 = v223 + 3;
        v228 = (_QWORD *)(v224 + v223 + 3);
        v229 = v635;
        v230 = v635 - 7;
        if ( v223 + 3 >= v635 - 7 )
          goto LABEL_754;
        if ( *v226 != *v228 )
        {
          v231 = ZSTD_NbCommonBytes(*v226 ^ *v228, v226, v228, v227);
          v214 = v686;
          v221 = v231 + 3;
          goto LABEL_274;
        }
        v226 = (_QWORD *)(v223 + 11);
        ++v228;
        if ( v223 + 11 >= v230 )
        {
LABEL_754:
        {
LABEL_261:
          if ( (unsigned __int64)v226 < v635 - 3 && *(_DWORD *)v228 == *(_DWORD *)v226 )
          {
            v226 = (_QWORD *)((char *)v226 + 4);
            v228 = (_QWORD *)((char *)v228 + 4);
          }
        }
          if ( (unsigned __int64)v226 < v635 - 1 && *(_WORD *)v228 == *(_WORD *)v226 )
          {
            v226 = (_QWORD *)((char *)v226 + 2);
            v228 = (_QWORD *)((char *)v228 + 2);
          }
          if ( (unsigned __int64)v226 < v635 && *(_BYTE *)v228 == *(_BYTE *)v226 )
            LODWORD(v226) = (_DWORD)v226 + 1;
          v214 = v686;
          v221 = (_DWORD)v226 - v223;
        }
        else
        {
          while ( *v226 == *v228 )
          {
            ++v226;
            ++v228;
            if ( (unsigned __int64)v226 >= v230 )
              goto LABEL_261;
          }
          v232 = ZSTD_NbCommonBytes(*v226 ^ *v228, v226, v228, v227);
          v214 = v686;
          v221 = v233 - v234 + v232 + 3;
        }
LABEL_274:
        if ( v221 > v216 )
        {
          v216 = v221;
          v235 = v214++;
          v236 = &v645[2 * v235];
          v236[1] = v221;
          *v236 = v218 - v638;
          v686 = v214;
          if ( v221 > v197 || v221 + v646 == v229 )
          {
            v82 = v214;
            goto LABEL_327;
          }
        }
        ++v218;
        ++v219;
        if ( v218 >= v213 )
          break;
        v217 = a3;
      }
      if ( v216 >= 3 )
      {
        v239 = v633;
LABEL_285:
        v240 = v643;
LABEL_286:
        v246 = v686;
        goto LABEL_287;
      }
      v237 = v646;
      FirstIndexHash3 = ZSTD_insertAndFindFirstIndexHash3(a1, &v659, v646);
      v239 = v633;
      v240 = v643;
      if ( FirstIndexHash3 < v643 || v633 - FirstIndexHash3 >= 0x40000 )
        goto LABEL_286;
      v241 = v635;
      v242 = ZSTD_count(v237, (char *)v636 + FirstIndexHash3, v635);
      if ( v242 < 3 )
        goto LABEL_285;
      v244 = v645;
      v245 = v243 + 2;
      v246 = 1;
      v216 = v242;
      v686 = 1;
      *v645 = v245;
      v244[1] = v242;
      if ( v242 > v197 || v242 + v237 == v241 )
      {
        v247 = v239 + 1;
        goto LABEL_326;
      }
      v240 = v643;
LABEL_287:
      v248 = v647;
      *v202 = v239;
      v249 = v632;
      if ( v248 )
      {
        while ( 2 )
        {
          --v248;
          if ( v203 < v240 )
            goto LABEL_324;
          v250 = (_DWORD *)v650;
          v251 = v646;
          if ( (unsigned __int64)v642 < v650 )
            v250 = v642;
          v252 = v635;
          v253 = &v649[2 * (v203 & v644)];
          v254 = (char *)v636 + v203;
          v255 = (_QWORD *)((char *)v250 + v646);
          v256 = v635 - 7;
          v257 = (_QWORD *)((char *)v250 + (_QWORD)v254);
          if ( (unsigned __int64)v250 + v646 < v635 - 7 )
          {
            if ( *v255 != *v257 )
            {
              v258 = (unsigned int)ZSTD_NbCommonBytes(*v255 ^ *v257, v255, v257, v250);
LABEL_308:
              v259 = (unsigned __int64)v250 + v258;
              if ( v259 <= v216 )
              {
                v246 = v686;
              }
              else
              {
                if ( v259 > v249 - v203 )
                  v249 = v203 + v259;
                v216 = v259;
                v260 = v645;
                v261 = v633 - v203 + 2;
                v645[2 * v686 + 1] = v259;
                v246 = v686 + 1;
                v260[2 * v686++] = v261;
                if ( v259 > 0x1000 || v259 + v251 == v252 )
                  goto LABEL_324;
              }
              if ( (unsigned __int8)v254[v259] >= *(_BYTE *)(v259 + v251) )
              {
                v650 = v259;
                *v639 = v203;
                if ( v203 <= v640 )
                {
                  v639 = &v632;
                  goto LABEL_324;
                }
                v203 = *v253;
                v639 = v253;
              }
              else
              {
                v642 = (char *)v259;
                *v637 = v203;
                if ( v203 <= v640 )
                {
                  v265 = &v632;
                  goto LABEL_325;
                }
                v203 = v253[1];
                v637 = v253 + 1;
              }
              if ( !v248 )
                goto LABEL_324;
              v240 = v643;
              continue;
            }
            ++v255;
            ++v257;
            if ( (unsigned __int64)v255 < v256 )
            {
              while ( *v255 == *v257 )
              {
                ++v255;
                ++v257;
                if ( (unsigned __int64)v255 >= v256 )
                  goto LABEL_298;
              }
              v262 = ZSTD_NbCommonBytes(*v255 ^ *v257, v255, v257, v250);
              v258 = v263 - v264 + v262;
              goto LABEL_308;
            }
          }
          break;
        }
LABEL_298:
        if ( (unsigned __int64)v255 < v635 - 3 && *(_DWORD *)v257 == *(_DWORD *)v255 )
        {
          v255 = (_QWORD *)((char *)v255 + 4);
          v257 = (_QWORD *)((char *)v257 + 4);
        }
        if ( (unsigned __int64)v255 < v635 - 1 && *(_WORD *)v257 == *(_WORD *)v255 )
        {
          v255 = (_QWORD *)((char *)v255 + 2);
          v257 = (_QWORD *)((char *)v257 + 2);
        }
        if ( (unsigned __int64)v255 < v635 && *(_BYTE *)v257 == *(_BYTE *)v255 )
          v255 = (_QWORD *)((char *)v255 + 1);
        v258 = (char *)v255 - ((char *)v250 + v646);
        goto LABEL_308;
      }
LABEL_324:
      v265 = v637;
LABEL_325:
      *v639 = 0;
      *v265 = 0;
      v247 = v249 - 8;
LABEL_326:
      v82 = v246;
      *(_DWORD *)(a1 + 36) = v247;
LABEL_327:
      if ( !v82 )
      {
        v14 = v646;
LABEL_749:
        v646 = ++v14;
        goto LABEL_750;
      }
      v266 = v651;
      v267 = a3;
      v268 = v648;
      v269 = v648;
      v270 = v656;
      v271 = v656;
      v651[4] = *a3;
      v266[5] = a3[1];
      v266[6] = a3[2];
      v266[2] = 0;
      v266[3] = v268;
      v272 = ZSTD_literalsContribution(v684, v269, v271, 2);
      v273 = v651;
      v274 = v645;
      *v651 = v272;
      if ( v274[2 * v82 - 1] > v660 )
      {
        *(_QWORD *)((char *)&v666 + 4) = *(_QWORD *)&v274[2 * v82 - 2];
        HIDWORD(v666) = v268;
LABEL_717:
        v588 = 0;
        v591 = 0;
        goto LABEL_718;
      }
      ZSTD_litLengthPrice(0, v270, 2);
      v275 = v655;
      v276 = v655 + 1;
      v277 = v651 + 7;
      do
      {
        *v277 = 0x40000000;
        v277 += 7;
        --v275;
      }
      while ( v275 );
      v278 = (unsigned int *)v82;
      v279 = v274;
      v637 = (unsigned int *)v82;
      v687 = v274;
      do
      {
        v280 = v279[1];
        updated = ZSTD_updateRep(v680, v267, *v279, v638);
        v284 = *(_QWORD *)updated;
        v285 = *(_DWORD *)(updated + 8);
        if ( v276 > v280 )
        {
          v298 = v651;
        }
        else
        {
          v286 = v656;
          do
          {
            _BitScanReverse((unsigned int *)&v287, v282 + 1);
            v288 = v276 - 3;
            if ( *(_DWORD *)(v286 + 80) == 1 )
            {
              _BitScanReverse(&v289, v276 - 2);
              v290 = v283 + ((v276 - 2) << 8 >> v289) + (((_DWORD)v287 + v289 + 16) << 8);
            }
            else
            {
              v291 = *(_DWORD *)(*(_QWORD *)(v286 + 24) + 4 * v287) + 1;
              _BitScanReverse(&v292, v291);
              v293 = *(_DWORD *)(v286 + 76) + (((_DWORD)v287 - v292) << 8) - (v291 << 8 >> v292);
              if ( (unsigned int)v288 <= 0x7F )
              {
                _mm_lfence();
                v295 = *((unsigned __int8 *)&qword_1803EF770[8] + v288);
              }
              else
              {
                _BitScanReverse(&v294, v288);
                LODWORD(v662) = 0;
                v295 = v294 + 36;
              }
              LODWORD(v663) = 0;
              v296 = *(_DWORD *)(*(_QWORD *)(v286 + 16) + 4 * v295) + 1;
              _BitScanReverse(&v297, v296);
              v290 = v293
                   + v283
                   + *(_DWORD *)(v286 + 72)
                   + ((*((_DWORD *)&qword_1803EF640[10] + v295) - v297) << 8)
                   - (v296 << 8 >> v297)
                   + 51;
            }
            v298 = v651;
            v299 = 7LL * v276;
            v651[v299 + 2] = v276++;
            *(_QWORD *)&v298[v299 + 4] = v284;
            v298[v299 + 1] = v282;
            v298[v299 + 3] = v268;
            v298[v299] = v290;
            v298[v299 + 6] = v285;
          }
          while ( v276 <= v280 );
          v279 = v687;
          v278 = v637;
        }
        v267 = a3;
        v279 += 2;
        v278 = (unsigned int *)((char *)v278 - 1);
        v687 = v279;
        v637 = v278;
      }
      while ( v278 );
      v300 = v656;
      v301 = 1;
      v302 = v276 - 1;
      v643 = 1;
      if ( !v302 )
      {
LABEL_714:
        v592 = &v298[7 * v302];
        v594 = *(_OWORD *)v592;
        v661 = v592[6];
        v15 = *((_QWORD *)v592 + 2);
        v666 = v594;
        v675 = v661;
        v673 = v594;
        v674 = v15;
        *(double *)&v594 = ZSTD_totalLen(&v673);
        if ( v302 > v595 )
        {
          v678 = *(_DWORD *)(v593 + 24);
          v676 = v594;
          v677 = v15;
          ZSTD_totalLen(&v676);
          v267 = a3;
          v591 = v302 - v596;
          v588 = 0;
          goto LABEL_718;
        }
        v267 = a3;
        goto LABEL_717;
      }
      while ( 2 )
      {
        v303 = v301;
        v304 = (_DWORD *)(v301 + v646);
        v305 = &v298[7 * v301 - 7];
        v639 = v304;
        if ( v305[2] )
          v306 = 1;
        else
          v306 = v305[3] + 1;
        v307 = *v305 - ZSTD_litLengthPrice(v306 - 1, v300, 2);
        v309 = ZSTD_rawLiteralsCost((char *)v304 - 1, (unsigned int)(v308 - 1), v300) + v307;
        v310 = ZSTD_litLengthPrice(v306, v300, 2);
        v298 = v651;
        v312 = v309 + v310;
        v313 = &v651[7 * v303];
        v314 = *v313;
        if ( v312 <= *v313 )
        {
          v315 = *((_QWORD *)v305 + 2);
          v314 = v312;
          *v313 = v312;
          v316 = v305[6];
          *((_QWORD *)v313 + 2) = v315;
          v313[6] = v316;
          *(_QWORD *)(v313 + 1) = 0;
          v313[3] = v306;
        }
        if ( (unsigned __int64)v304 > v665 )
          goto LABEL_706;
        if ( v643 == v302 )
          goto LABEL_714;
        v317 = v313[2];
        v638 = v317 != 0;
        if ( v317 )
          v640 = 0;
        else
          v640 = v313[3];
        v644 = v314 + ZSTD_litLengthPrice(0, v656, v311);
        v637 = v313 + 4;
        v318 = *(unsigned int *)(a1 + 36);
        v319 = *(_QWORD *)(a1 + 8);
        v320 = *(_DWORD *)(a1 + 200);
        if ( (unsigned __int64)v304 < v319 + v318 )
          goto LABEL_705;
        v321 = (_DWORD)v304 - v319;
        if ( (unsigned int)v318 < (int)v304 - (int)v319 )
        {
          v322 = v635;
          do
            LODWORD(v318) = ZSTD_insertBt1(a1, (int)v319 + (int)v318, v322, v320, 0) + v318;
          while ( (unsigned int)v318 < v321 );
          v304 = v639;
        }
        v323 = *(_QWORD *)(a1 + 48);
        *(_DWORD *)(a1 + 36) = v321;
        v324 = *(unsigned int *)(a1 + 192);
        if ( v320 != 3 )
        {
          v325 = 4095;
          if ( v320 != 5 )
          {
            v326 = *(_DWORD *)(a1 + 204);
            if ( (unsigned int)(v320 - 6) <= 1 )
            {
              if ( v326 < 0xFFF )
                v325 = *(_DWORD *)(a1 + 204);
              v327 = (_DWORD)v304 - *(_QWORD *)(a1 + 8);
              v658 = *(_QWORD *)(a1 + 8);
              v634 = v327;
              v328 = ZSTD_hash6Ptr(v304, v324, v323);
              v330 = (unsigned int *)(v329 + 4 * v328);
              v331 = *(_DWORD *)(a1 + 28);
              v332 = *(_DWORD **)(a1 + 64);
              v333 = *v330;
              v334 = v639;
              v335 = 1 << (*(_DWORD *)(a1 + 188) - 1);
              v336 = 0;
              v649 = v332;
              v337 = v335 - 1;
              v650 = 0;
              v652 = 0;
              v641 = v337;
              if ( v337 < v327 )
                v336 = v327 - v337;
              v632 = v336;
              v338 = 1 << *(_DWORD *)(a1 + 184);
              v339 = v327 - v338;
              v340 = 1;
              if ( v327 - v331 <= v338 )
                v339 = v331;
              if ( *(_DWORD *)(a1 + 32) )
                v339 = v331;
              if ( v339 )
                v340 = v339;
              v341 = *(_DWORD *)(a1 + 196);
              v342 = v655;
              v647 = v340;
              v688 = 0;
              v636 = &v332[2 * (v327 & v337)];
              v642 = (char *)(v636 + 1);
              v633 = v327 + 9;
              v648 = 1 << v341;
              v343 = v638;
              v344 = v327 - *(_DWORD *)(a1 + 24);
              v345 = v637;
              v346 = v638 + 3;
              v347 = &v637[v638];
              while ( 2 )
              {
                if ( v343 == 3 )
                  v348 = *v345 - 1;
                else
                  v348 = *v347;
                v349 = 0;
                if ( v348 - 1 >= v344 )
                  goto LABEL_399;
                v350 = ZSTD_readMINMATCH(v639, 4, 0, -(__int64)v348);
                if ( v350 != *(_DWORD *)(v352 + v351) )
                  goto LABEL_398;
                v353 = (_QWORD *)(v351 + 4);
                v354 = v351 + 4;
                v355 = v635;
                v356 = (_QWORD *)(v352 + v354);
                v357 = v353;
                v358 = v635 - 7;
                if ( (unsigned __int64)v353 < v635 - 7 )
                {
                  if ( *v356 != *v353 )
                  {
                    v359 = ZSTD_NbCommonBytes(*v356 ^ *v353, v353, v356, v353);
                    goto LABEL_397;
                  }
                  ++v353;
                  ++v356;
                  if ( (unsigned __int64)v353 < v358 )
                  {
                    while ( *v356 == *v353 )
                    {
                      ++v353;
                      ++v356;
                      if ( (unsigned __int64)v353 >= v358 )
                        goto LABEL_386;
                    }
                    v362 = ZSTD_NbCommonBytes(*v356 ^ *v353, v353, v356, v357);
                    v359 = v363 - v364 + v362;
LABEL_397:
                    v349 = v359 + 4;
LABEL_398:
                    v334 = v639;
LABEL_399:
                    if ( v349 > v342 )
                    {
                      v360 = v688;
                      v342 = v349;
                      ++v688;
                      v361 = &v645[2 * v360];
                      v361[1] = v349;
                      *v361 = v343 - v638;
                      if ( v349 > v325 || (_DWORD *)((char *)v334 + v349) == (_DWORD *)v635 )
                        goto LABEL_680;
                    }
                    v345 = v637;
                    ++v343;
                    ++v347;
                    if ( v343 >= v346 )
                    {
                      v365 = v648;
                      *v330 = v634;
                      if ( v365 )
                      {
                        while ( 1 )
                        {
                          --v365;
                          if ( v333 < v647 )
                            break;
                          v366 = v652;
                          v367 = v639;
                          if ( v650 < v652 )
                            v366 = v650;
                          v368 = (_DWORD *)v635;
                          v369 = &v649[2 * (v333 & v641)];
                          v370 = v658 + v333;
                          v371 = (_QWORD *)((char *)v639 + v366);
                          v372 = v635 - 7;
                          v373 = (char *)v639 + v366;
                          v374 = (_QWORD *)(v370 + v366);
                          if ( (unsigned __int64)v639 + v366 >= v635 - 7 )
                            goto LABEL_414;
                          if ( *v374 != *v371 )
                          {
                            v375 = (unsigned int)ZSTD_NbCommonBytes(*v374 ^ *v371, v371, v374, v366);
                            goto LABEL_424;
                          }
                          ++v371;
                          ++v374;
                          if ( (unsigned __int64)v371 >= v372 )
                          {
LABEL_414:
                            if ( (unsigned __int64)v371 < v635 - 3 && *(_DWORD *)v374 == *(_DWORD *)v371 )
                            {
                              v371 = (_QWORD *)((char *)v371 + 4);
                              v374 = (_QWORD *)((char *)v374 + 4);
                            }
                            if ( (unsigned __int64)v371 < v635 - 1 && *(_WORD *)v374 == *(_WORD *)v371 )
                            {
                              v371 = (_QWORD *)((char *)v371 + 2);
                              v374 = (_QWORD *)((char *)v374 + 2);
                            }
                            if ( (unsigned __int64)v371 < v635 && *(_BYTE *)v374 == *(_BYTE *)v371 )
                              v371 = (_QWORD *)((char *)v371 + 1);
                            v375 = (char *)v371 - v373;
                          }
                          else
                          {
                            while ( *v374 == *v371 )
                            {
                              ++v371;
                              ++v374;
                              if ( (unsigned __int64)v371 >= v372 )
                                goto LABEL_414;
                            }
                            v379 = ZSTD_NbCommonBytes(*v374 ^ *v371, v371, v374, v366);
                            v375 = v380 - (_QWORD)v373 + v379;
                          }
LABEL_424:
                          v376 = v375 + v366;
                          if ( v376 > v342 )
                          {
                            if ( v376 > v633 - v333 )
                              v633 = v333 + v376;
                            v342 = v376;
                            v377 = v645;
                            v378 = v634 - v333 + 2;
                            v645[2 * v688 + 1] = v376;
                            v377[2 * v688++] = v378;
                            if ( v376 > 0x1000 || (_DWORD *)((char *)v367 + v376) == v368 )
                              break;
                          }
                          if ( *(_BYTE *)(v370 + v376) >= *((_BYTE *)v367 + v376) )
                          {
                            v652 = v376;
                            *(_DWORD *)v642 = v333;
                            if ( v333 <= v632 )
                            {
                              v383 = (int *)&v648;
                              goto LABEL_439;
                            }
                            v333 = *v369;
                            v642 = (char *)v369;
                          }
                          else
                          {
                            v650 = v376;
                            *v636 = v333;
                            if ( v333 <= v632 )
                            {
                              *(_DWORD *)v642 = 0;
                              v648 = 0;
                              v382 = v633;
                              goto LABEL_678;
                            }
                            v333 = v369[1];
                            v636 = v369 + 1;
                          }
                          if ( !v365 )
                          {
                            v381 = v636;
                            *(_DWORD *)v642 = 0;
                            *v381 = 0;
                            v382 = v633;
                            goto LABEL_678;
                          }
                        }
                      }
LABEL_440:
                      v384 = v636;
                      *(_DWORD *)v642 = 0;
                      *v384 = 0;
                      v382 = v633;
LABEL_678:
                      v542 = v382 - 8;
                      goto LABEL_679;
                    }
                    continue;
                  }
LABEL_386:
                  v355 = v635;
                }
                break;
              }
              if ( (unsigned __int64)v353 < v355 - 3 && *(_DWORD *)v356 == *(_DWORD *)v353 )
              {
                v353 = (_QWORD *)((char *)v353 + 4);
                v356 = (_QWORD *)((char *)v356 + 4);
              }
              if ( (unsigned __int64)v353 < v355 - 1 && *(_WORD *)v356 == *(_WORD *)v353 )
              {
                v353 = (_QWORD *)((char *)v353 + 2);
                v356 = (_QWORD *)((char *)v356 + 2);
              }
              if ( (unsigned __int64)v353 < v355 && *(_BYTE *)v356 == *(_BYTE *)v353 )
                LODWORD(v353) = (_DWORD)v353 + 1;
              v359 = (_DWORD)v353 - (_DWORD)v357;
              goto LABEL_397;
            }
            if ( v326 < 0xFFF )
              v325 = *(_DWORD *)(a1 + 204);
            v385 = (_DWORD)v304 - *(_QWORD *)(a1 + 8);
            v658 = *(_QWORD *)(a1 + 8);
            v634 = v385;
            v386 = ZSTD_hash4Ptr(v304, v324, v323);
            v388 = (unsigned int *)(v387 + 4 * v386);
            v389 = *(_DWORD *)(a1 + 28);
            v390 = *(_DWORD **)(a1 + 64);
            v391 = *v388;
            v392 = v639;
            v393 = 1 << (*(_DWORD *)(a1 + 188) - 1);
            v394 = 0;
            v649 = v390;
            v395 = v393 - 1;
            v650 = 0;
            v652 = 0;
            v641 = v395;
            if ( v395 < v385 )
              v394 = v385 - v395;
            v632 = v394;
            v396 = 1 << *(_DWORD *)(a1 + 184);
            v397 = v385 - v396;
            v398 = 1;
            if ( v385 - v389 <= v396 )
              v397 = v389;
            if ( *(_DWORD *)(a1 + 32) )
              v397 = v389;
            if ( v397 )
              v398 = v397;
            v399 = *(_DWORD *)(a1 + 196);
            v400 = v655;
            v647 = v398;
            v688 = 0;
            v636 = &v390[2 * (v385 & v395)];
            v642 = (char *)(v636 + 1);
            v633 = v385 + 9;
            v648 = 1 << v399;
            v401 = v638;
            v402 = v385 - *(_DWORD *)(a1 + 24);
            v403 = v637;
            v404 = v638 + 3;
            v405 = &v637[v638];
            while ( 2 )
            {
              if ( v401 == 3 )
                v406 = *v403 - 1;
              else
                v406 = *v405;
              v407 = 0;
              if ( v406 - 1 >= v402 )
                goto LABEL_476;
              v408 = ZSTD_readMINMATCH(v639, 4, 0, -(__int64)v406);
              if ( v408 != *(_DWORD *)(v410 + v409) )
                goto LABEL_475;
              v411 = (_QWORD *)(v409 + 4);
              v412 = v409 + 4;
              v413 = v635;
              v414 = (_QWORD *)(v410 + v412);
              v415 = v411;
              v416 = v635 - 7;
              if ( (unsigned __int64)v411 < v635 - 7 )
              {
                if ( *v414 != *v411 )
                {
                  v417 = ZSTD_NbCommonBytes(*v414 ^ *v411, v411, v414, v411);
                  goto LABEL_474;
                }
                ++v411;
                ++v414;
                if ( (unsigned __int64)v411 < v416 )
                {
                  while ( *v414 == *v411 )
                  {
                    ++v411;
                    ++v414;
                    if ( (unsigned __int64)v411 >= v416 )
                      goto LABEL_463;
                  }
                  v420 = ZSTD_NbCommonBytes(*v414 ^ *v411, v411, v414, v415);
                  v417 = v421 - v422 + v420;
LABEL_474:
                  v407 = v417 + 4;
LABEL_475:
                  v392 = v639;
LABEL_476:
                  if ( v407 > v400 )
                  {
                    v418 = v688;
                    v400 = v407;
                    ++v688;
                    v419 = &v645[2 * v418];
                    v419[1] = v407;
                    *v419 = v401 - v638;
                    if ( v407 > v325 || (_DWORD *)((char *)v392 + v407) == (_DWORD *)v635 )
                      goto LABEL_680;
                  }
                  v403 = v637;
                  ++v401;
                  ++v405;
                  if ( v401 >= v404 )
                  {
                    v423 = v648;
                    *v388 = v634;
                    if ( !v423 )
                      goto LABEL_440;
                    while ( 2 )
                    {
                      --v423;
                      if ( v391 < v647 )
                        goto LABEL_440;
                      v424 = v652;
                      v425 = v639;
                      if ( v650 < v652 )
                        v424 = v650;
                      v426 = (_DWORD *)v635;
                      v427 = &v649[2 * (v391 & v641)];
                      v428 = v658 + v391;
                      v429 = (_QWORD *)((char *)v639 + v424);
                      v430 = v635 - 7;
                      v431 = (char *)v639 + v424;
                      v432 = (_QWORD *)(v428 + v424);
                      if ( (unsigned __int64)v639 + v424 < v635 - 7 )
                      {
                        if ( *v432 != *v429 )
                        {
                          v433 = (unsigned int)ZSTD_NbCommonBytes(*v432 ^ *v429, v429, v432, v424);
LABEL_501:
                          v434 = v433 + v424;
                          if ( v434 > v400 )
                          {
                            if ( v434 > v633 - v391 )
                              v633 = v434 + v391;
                            v400 = v434;
                            v435 = v645;
                            v436 = v634 - v391 + 2;
                            v645[2 * v688 + 1] = v434;
                            v435[2 * v688++] = v436;
                            if ( v434 > 0x1000 || (_DWORD *)((char *)v425 + v434) == v426 )
                              goto LABEL_440;
                          }
                          if ( *(_BYTE *)(v428 + v434) >= *((_BYTE *)v425 + v434) )
                          {
                            v652 = v434;
                            *(_DWORD *)v642 = v391;
                            if ( v391 <= v632 )
                            {
                              v383 = &v654;
                              goto LABEL_439;
                            }
                            v391 = *v427;
                            v642 = (char *)v427;
                          }
                          else
                          {
                            v650 = v434;
                            *v636 = v391;
                            if ( v391 <= v632 )
                            {
                              *(_DWORD *)v642 = 0;
                              v654 = 0;
                              v382 = v633;
                              goto LABEL_678;
                            }
                            v391 = v427[1];
                            v636 = v427 + 1;
                          }
                          if ( !v423 )
                          {
                            v439 = v636;
                            *(_DWORD *)v642 = 0;
                            *v439 = 0;
                            v382 = v633;
                            goto LABEL_678;
                          }
                          continue;
                        }
                        ++v429;
                        ++v432;
                        if ( (unsigned __int64)v429 < v430 )
                        {
                          while ( *v432 == *v429 )
                          {
                            ++v429;
                            ++v432;
                            if ( (unsigned __int64)v429 >= v430 )
                              goto LABEL_491;
                          }
                          v437 = ZSTD_NbCommonBytes(*v432 ^ *v429, v429, v432, v424);
                          v433 = v438 - (_QWORD)v431 + v437;
                          goto LABEL_501;
                        }
                      }
                      break;
                    }
LABEL_491:
                    if ( (unsigned __int64)v429 < v635 - 3 && *(_DWORD *)v432 == *(_DWORD *)v429 )
                    {
                      v429 = (_QWORD *)((char *)v429 + 4);
                      v432 = (_QWORD *)((char *)v432 + 4);
                    }
                    if ( (unsigned __int64)v429 < v635 - 1 && *(_WORD *)v432 == *(_WORD *)v429 )
                    {
                      v429 = (_QWORD *)((char *)v429 + 2);
                      v432 = (_QWORD *)((char *)v432 + 2);
                    }
                    if ( (unsigned __int64)v429 < v635 && *(_BYTE *)v432 == *(_BYTE *)v429 )
                      v429 = (_QWORD *)((char *)v429 + 1);
                    v433 = (char *)v429 - v431;
                    goto LABEL_501;
                  }
                  continue;
                }
LABEL_463:
                v413 = v635;
              }
              break;
            }
            if ( (unsigned __int64)v411 < v413 - 3 && *(_DWORD *)v414 == *(_DWORD *)v411 )
            {
              v411 = (_QWORD *)((char *)v411 + 4);
              v414 = (_QWORD *)((char *)v414 + 4);
            }
            if ( (unsigned __int64)v411 < v413 - 1 && *(_WORD *)v414 == *(_WORD *)v411 )
            {
              v411 = (_QWORD *)((char *)v411 + 2);
              v414 = (_QWORD *)((char *)v414 + 2);
            }
            if ( (unsigned __int64)v411 < v413 && *(_BYTE *)v414 == *(_BYTE *)v411 )
              LODWORD(v411) = (_DWORD)v411 + 1;
            v417 = (_DWORD)v411 - (_DWORD)v415;
            goto LABEL_474;
          }
          if ( *(_DWORD *)(a1 + 204) < 0xFFFu )
            v325 = *(_DWORD *)(a1 + 204);
          v440 = (_DWORD)v304 - *(_QWORD *)(a1 + 8);
          v658 = *(_QWORD *)(a1 + 8);
          v634 = v440;
          v441 = ZSTD_hash5Ptr(v304, v324, v323);
          v443 = (unsigned int *)(v442 + 4 * v441);
          v444 = *(_DWORD *)(a1 + 28);
          v445 = *(_DWORD **)(a1 + 64);
          v446 = *v443;
          v447 = v639;
          v448 = 1 << (*(_DWORD *)(a1 + 188) - 1);
          v449 = 0;
          v649 = v445;
          v450 = v448 - 1;
          v650 = 0;
          v652 = 0;
          v647 = v450;
          if ( v450 < v440 )
            v449 = v440 - v450;
          v632 = v449;
          v451 = 1 << *(_DWORD *)(a1 + 184);
          v452 = v440 - v451;
          v453 = 1;
          if ( v440 - v444 <= v451 )
            v452 = v444;
          if ( *(_DWORD *)(a1 + 32) )
            v452 = v444;
          if ( v452 )
            v453 = v452;
          v454 = *(_DWORD *)(a1 + 196);
          v455 = v655;
          v648 = v453;
          v688 = 0;
          v636 = &v445[2 * (v440 & v450)];
          v642 = (char *)(v636 + 1);
          v633 = v440 + 9;
          v654 = 1 << v454;
          v456 = v638;
          v457 = v440 - *(_DWORD *)(a1 + 24);
          v458 = v637;
          v459 = v638 + 3;
          v460 = &v637[v638];
          while ( 2 )
          {
            if ( v456 == 3 )
              v461 = *v458 - 1;
            else
              v461 = *v460;
            v462 = 0;
            if ( v461 - 1 >= v457 )
              goto LABEL_551;
            v463 = ZSTD_readMINMATCH(v639, 4, 0, -(__int64)v461);
            if ( v463 != *(_DWORD *)(v465 + v464) )
              goto LABEL_550;
            v466 = (_QWORD *)(v464 + 4);
            v467 = v464 + 4;
            v468 = v635;
            v469 = (_QWORD *)(v465 + v467);
            v470 = v466;
            v471 = v635 - 7;
            if ( (unsigned __int64)v466 < v635 - 7 )
            {
              if ( *v469 != *v466 )
              {
                v472 = ZSTD_NbCommonBytes(*v469 ^ *v466, v466, v469, v466);
                goto LABEL_549;
              }
              ++v466;
              ++v469;
              if ( (unsigned __int64)v466 < v471 )
              {
                while ( *v469 == *v466 )
                {
                  ++v466;
                  ++v469;
                  if ( (unsigned __int64)v466 >= v471 )
                    goto LABEL_538;
                }
                v475 = ZSTD_NbCommonBytes(*v469 ^ *v466, v466, v469, v470);
                v472 = v476 - v477 + v475;
LABEL_549:
                v462 = v472 + 4;
LABEL_550:
                v447 = v639;
LABEL_551:
                if ( v462 > v455 )
                {
                  v473 = v688;
                  v455 = v462;
                  ++v688;
                  v474 = &v645[2 * v473];
                  v474[1] = v462;
                  *v474 = v456 - v638;
                  if ( v462 > v325 || (_DWORD *)((char *)v447 + v462) == (_DWORD *)v635 )
                    goto LABEL_680;
                }
                v458 = v637;
                ++v456;
                ++v460;
                if ( v456 >= v459 )
                {
                  v478 = v654;
                  *v443 = v634;
                  if ( !v478 )
                    goto LABEL_440;
                  while ( 2 )
                  {
                    --v478;
                    if ( v446 < v648 )
                      goto LABEL_440;
                    v479 = v652;
                    v480 = v639;
                    if ( v650 < v652 )
                      v479 = v650;
                    v481 = (_DWORD *)v635;
                    v482 = &v649[2 * (v446 & v647)];
                    v483 = v658 + v446;
                    v484 = (_QWORD *)((char *)v639 + v479);
                    v485 = v635 - 7;
                    v486 = (char *)v639 + v479;
                    v487 = (_QWORD *)(v483 + v479);
                    if ( (unsigned __int64)v639 + v479 < v635 - 7 )
                    {
                      if ( *v487 != *v484 )
                      {
                        v488 = (unsigned int)ZSTD_NbCommonBytes(*v487 ^ *v484, v484, v487, v479);
LABEL_576:
                        v489 = v488 + v479;
                        if ( v489 > v455 )
                        {
                          if ( v489 > v633 - v446 )
                            v633 = v489 + v446;
                          v455 = v489;
                          v490 = v645;
                          v491 = v634 - v446 + 2;
                          v645[2 * v688 + 1] = v489;
                          v490[2 * v688++] = v491;
                          if ( v489 > 0x1000 || (_DWORD *)((char *)v480 + v489) == v481 )
                            goto LABEL_440;
                        }
                        if ( *(_BYTE *)(v483 + v489) >= *((_BYTE *)v480 + v489) )
                        {
                          v652 = v489;
                          *(_DWORD *)v642 = v446;
                          if ( v446 <= v632 )
                          {
                            v383 = &v657;
LABEL_439:
                            v642 = (char *)v383;
                            goto LABEL_440;
                          }
                          v446 = *v482;
                          v642 = (char *)v482;
                        }
                        else
                        {
                          v650 = v489;
                          *v636 = v446;
                          if ( v446 <= v632 )
                          {
                            *(_DWORD *)v642 = 0;
                            v657 = 0;
                            v382 = v633;
                            goto LABEL_678;
                          }
                          v446 = v482[1];
                          v636 = v482 + 1;
                        }
                        if ( !v478 )
                        {
                          v494 = v636;
                          *(_DWORD *)v642 = 0;
                          *v494 = 0;
                          v382 = v633;
                          goto LABEL_678;
                        }
                        continue;
                      }
                      ++v484;
                      ++v487;
                      if ( (unsigned __int64)v484 < v485 )
                      {
                        while ( *v487 == *v484 )
                        {
                          ++v484;
                          ++v487;
                          if ( (unsigned __int64)v484 >= v485 )
                            goto LABEL_566;
                        }
                        v492 = ZSTD_NbCommonBytes(*v487 ^ *v484, v484, v487, v479);
                        v488 = v493 - (_QWORD)v486 + v492;
                        goto LABEL_576;
                      }
                    }
                    break;
                  }
LABEL_566:
                  if ( (unsigned __int64)v484 < v635 - 3 && *(_DWORD *)v487 == *(_DWORD *)v484 )
                  {
                    v484 = (_QWORD *)((char *)v484 + 4);
                    v487 = (_QWORD *)((char *)v487 + 4);
                  }
                  if ( (unsigned __int64)v484 < v635 - 1 && *(_WORD *)v487 == *(_WORD *)v484 )
                  {
                    v484 = (_QWORD *)((char *)v484 + 2);
                    v487 = (_QWORD *)((char *)v487 + 2);
                  }
                  if ( (unsigned __int64)v484 < v635 && *(_BYTE *)v487 == *(_BYTE *)v484 )
                    v484 = (_QWORD *)((char *)v484 + 1);
                  v488 = (char *)v484 - v486;
                  goto LABEL_576;
                }
                continue;
              }
LABEL_538:
              v468 = v635;
            }
            break;
          }
          if ( (unsigned __int64)v466 < v468 - 3 && *(_DWORD *)v469 == *(_DWORD *)v466 )
          {
            v466 = (_QWORD *)((char *)v466 + 4);
            v469 = (_QWORD *)((char *)v469 + 4);
          }
          if ( (unsigned __int64)v466 < v468 - 1 && *(_WORD *)v469 == *(_WORD *)v466 )
          {
            v466 = (_QWORD *)((char *)v466 + 2);
            v469 = (_QWORD *)((char *)v469 + 2);
          }
          if ( (unsigned __int64)v466 < v468 && *(_BYTE *)v469 == *(_BYTE *)v466 )
            LODWORD(v466) = (_DWORD)v466 + 1;
          v472 = (_DWORD)v466 - (_DWORD)v470;
          goto LABEL_549;
        }
        v495 = 4095;
        if ( *(_DWORD *)(a1 + 204) < 0xFFFu )
          v495 = *(_DWORD *)(a1 + 204);
        v496 = (_DWORD)v304 - *(_QWORD *)(a1 + 8);
        v652 = *(_QWORD *)(a1 + 8);
        v633 = v496;
        v497 = ZSTD_hash4Ptr(v304, v324, v323);
        v500 = (unsigned int *)(v499 + 4 * v497);
        v501 = *v500;
        v502 = *(_DWORD *)(a1 + 28);
        v503 = *(_DWORD **)(a1 + 64);
        v504 = 0;
        v505 = (1 << (*(_DWORD *)(a1 + 188) - 1)) - 1;
        v663 = 0;
        v662 = 0;
        v649 = v503;
        v654 = v505;
        if ( v505 < v498 )
          v504 = v498 - v505;
        v641 = v504;
        v506 = 1 << *(_DWORD *)(a1 + 184);
        v507 = v498 - v506;
        v508 = 1;
        if ( v498 - v502 <= v506 )
          v507 = v502;
        if ( *(_DWORD *)(a1 + 32) )
          v507 = v502;
        if ( v507 )
          v508 = v507;
        v509 = *(_DWORD *)(a1 + 196);
        v632 = v508;
        v688 = 0;
        v510 = 0;
        v636 = &v503[2 * (v498 & v505)];
        v642 = (char *)(v636 + 1);
        v634 = v498 + 9;
        v657 = 1 << v509;
        v650 = v655;
        v511 = v498 - *(_DWORD *)(a1 + 24);
        v512 = v638;
        v513 = v637;
        v514 = v638 + 3;
        v515 = &v637[v638];
        while ( 2 )
        {
          if ( v512 == 3 )
            v516 = *v513 - 1;
          else
            v516 = *v515;
          v517 = 0;
          if ( v516 - 1 >= v511 )
          {
            v525 = (_DWORD *)v635;
          }
          else
          {
            LODWORD(v658) = 1;
            v518 = ZSTD_readMINMATCH(v639, 3, (unsigned int)(*(_DWORD *)((char *)v639 - v516) << 8), 0);
            if ( v518 == v521 )
            {
              v522 = (_QWORD *)(v519 + 3);
              v523 = v519 + 3;
              v524 = (_QWORD *)(v520 + v519 + 3);
              v525 = (_DWORD *)v635;
              v526 = v635 - 7;
              if ( v519 + 3 >= v635 - 7 )
                goto LABEL_613;
              if ( *v524 != *v522 )
              {
                v517 = ZSTD_NbCommonBytes(*v524 ^ *v522, v522, v524, v523) + 3;
                goto LABEL_626;
              }
              v522 = (_QWORD *)(v519 + 11);
              ++v524;
              if ( v519 + 11 >= v526 )
              {
LABEL_613:
                if ( (unsigned __int64)v522 < v635 - 3 && *(_DWORD *)v524 == *(_DWORD *)v522 )
                {
                  v522 = (_QWORD *)((char *)v522 + 4);
                  v524 = (_QWORD *)((char *)v524 + 4);
                }
                if ( (unsigned __int64)v522 < v635 - 1 && *(_WORD *)v524 == *(_WORD *)v522 )
                {
                  v522 = (_QWORD *)((char *)v522 + 2);
                  v524 = (_QWORD *)((char *)v524 + 2);
                }
                if ( (unsigned __int64)v522 < v635 && *(_BYTE *)v524 == *(_BYTE *)v522 )
                  LODWORD(v522) = (_DWORD)v522 + 1;
                v517 = (_DWORD)v522 - v519;
              }
              else
              {
                while ( *v524 == *v522 )
                {
                  ++v522;
                  ++v524;
                  if ( (unsigned __int64)v522 >= v526 )
                    goto LABEL_613;
                }
                v527 = ZSTD_NbCommonBytes(*v524 ^ *v522, v522, v524, v523);
                v517 = v528 - v529 + v527 + 3;
              }
            }
            else
            {
              v525 = (_DWORD *)v635;
            }
LABEL_626:
            v510 = v688;
          }
          if ( v517 > v650 )
          {
            v530 = v510++;
            v531 = &v645[2 * v530];
            v531[1] = v517;
            *v531 = v512 - v638;
            v650 = v517;
            v688 = v510;
            if ( v517 > v495 || (_DWORD *)((char *)v639 + v517) == v525 )
              goto LABEL_680;
          }
          ++v512;
          ++v515;
          if ( v512 < v514 )
          {
            v513 = v637;
            continue;
          }
          break;
        }
        v532 = v650;
        if ( v650 >= 3 )
        {
          v535 = v633;
          v536 = v632;
          goto LABEL_637;
        }
        v533 = v639;
        v534 = ZSTD_insertAndFindFirstIndexHash3(a1, &v659, v639);
        v535 = v633;
        v536 = v632;
        if ( v534 < v632 || v633 - v534 >= 0x40000 )
          goto LABEL_637;
        v537 = ZSTD_count(v533, v652 + v534, v635);
        if ( v537 < 3 )
        {
          v536 = v632;
LABEL_637:
          v541 = v688;
LABEL_638:
          v543 = v657;
          *v500 = v535;
          if ( !v543 )
          {
LABEL_676:
            v559 = (char *)v636;
LABEL_677:
            v688 = v541;
            *(_DWORD *)v642 = 0;
            *(_DWORD *)v559 = 0;
            v382 = v634;
            goto LABEL_678;
          }
          while ( 2 )
          {
            --v543;
            if ( v501 < v536 )
              goto LABEL_676;
            v544 = v662;
            v545 = v639;
            if ( v663 < v662 )
              v544 = v663;
            v546 = (_DWORD *)v635;
            v547 = &v649[2 * (v501 & v654)];
            v548 = v652 + v501;
            v549 = (_QWORD *)((char *)v639 + v544);
            v550 = v635 - 7;
            v551 = (_QWORD *)(v548 + v544);
            if ( (unsigned __int64)v639 + v544 < v635 - 7 )
            {
              if ( *v551 != *v549 )
              {
                v552 = (unsigned int)ZSTD_NbCommonBytes(*v551 ^ *v549, v549, v551, v544);
LABEL_660:
                v553 = v552 + v544;
                if ( v553 <= v532 )
                {
                  v541 = v688;
                }
                else
                {
                  if ( v553 > v634 - v501 )
                    v634 = v501 + v553;
                  v532 = v553;
                  v554 = v645;
                  v555 = v633 - v501 + 2;
                  v645[2 * v688 + 1] = v553;
                  v554[2 * v688] = v555;
                  v541 = ++v688;
                  if ( v553 > 0x1000 || (_DWORD *)((char *)v545 + v553) == v546 )
                    goto LABEL_676;
                }
                if ( *(_BYTE *)(v548 + v553) >= *((_BYTE *)v545 + v553) )
                {
                  v662 = v553;
                  *(_DWORD *)v642 = v501;
                  if ( v501 <= v641 )
                  {
                    v642 = &v664;
                    goto LABEL_676;
                  }
                  v501 = *v547;
                  v642 = (char *)v547;
                }
                else
                {
                  v663 = v553;
                  *v636 = v501;
                  if ( v501 <= v641 )
                  {
                    v559 = &v664;
                    goto LABEL_677;
                  }
                  v501 = v547[1];
                  v636 = v547 + 1;
                }
                if ( !v543 )
                  goto LABEL_676;
                v536 = v632;
                continue;
              }
              ++v549;
              ++v551;
              if ( (unsigned __int64)v549 < v550 )
              {
                while ( *v551 == *v549 )
                {
                  ++v549;
                  ++v551;
                  if ( (unsigned __int64)v549 >= v550 )
                    goto LABEL_650;
                }
                v556 = ZSTD_NbCommonBytes(*v551 ^ *v549, v549, v551, v544);
                v552 = v557 - v558 + v556;
                goto LABEL_660;
              }
            }
            break;
          }
LABEL_650:
          if ( (unsigned __int64)v549 < v635 - 3 && *(_DWORD *)v551 == *(_DWORD *)v549 )
          {
            v549 = (_QWORD *)((char *)v549 + 4);
            v551 = (_QWORD *)((char *)v551 + 4);
          }
          if ( (unsigned __int64)v549 < v635 - 1 && *(_WORD *)v551 == *(_WORD *)v549 )
          {
            v549 = (_QWORD *)((char *)v549 + 2);
            v551 = (_QWORD *)((char *)v551 + 2);
          }
          if ( (unsigned __int64)v549 < v635 && *(_BYTE *)v551 == *(_BYTE *)v549 )
            v549 = (_QWORD *)((char *)v549 + 1);
          v552 = (char *)v549 - ((char *)v639 + v544);
          goto LABEL_660;
        }
        v539 = v645;
        v540 = v538 + 2;
        v541 = 1;
        v532 = v537;
        v688 = 1;
        *v645 = v540;
        v13 = (_DWORD *)((char *)v533 + v537) == (_DWORD *)v635;
        v539[1] = v537;
        if ( v537 <= v495 && !v13 )
        {
          v536 = v632;
          goto LABEL_638;
        }
        v542 = v535 + 1;
        v688 = 1;
LABEL_679:
        *(_DWORD *)(a1 + 36) = v542;
LABEL_680:
        if ( !v688 )
        {
LABEL_705:
          v298 = v651;
LABEL_706:
          v301 = v643 + 1;
          v643 = v301;
          if ( v301 > v302 )
            goto LABEL_714;
          v300 = v656;
          continue;
        }
        break;
      }
      v560 = v645;
      v561 = v645[2 * v688 - 1];
      if ( v561 <= v660 && v561 + v643 < 0x1000 )
      {
        v562 = 0;
        v641 = 0;
        v563 = v645;
        v649 = v645;
        while ( 1 )
        {
          v564 = *v563;
          v565 = ZSTD_updateRep(v679, v637, *v563, v638);
          v568 = v566[1];
          v569 = *(_QWORD *)v565;
          v570 = *(_DWORD *)(v565 + 8);
          v571 = v562 ? v560[2 * v562 - 1] + 1 : v653;
          if ( v568 >= v571 )
            break;
          v298 = v651;
LABEL_703:
          v560 = v645;
          ++v562;
          v563 = v566 + 2;
          v641 = v562;
          v649 = v563;
          if ( v562 >= v688 )
            goto LABEL_706;
        }
        v572 = v656;
        v573 = v568 + v567;
        while ( 2 )
        {
          _BitScanReverse((unsigned int *)&v574, v564 + 1);
          v13 = *(_DWORD *)(v572 + 80) == 1;
          v575 = v573 - v567 - 3;
          LODWORD(v652) = 0;
          if ( v13 )
          {
            LODWORD(v650) = 0;
            _BitScanReverse(&v576, v575 + 1);
            v577 = ((unsigned int)(((_DWORD)v575 + 1) << 8) >> v576) + v644 + (((_DWORD)v574 + v576 + 16) << 8);
          }
          else
          {
            v578 = *(_QWORD *)(v572 + 24);
            LODWORD(v642) = 0;
            v579 = *(_DWORD *)(v578 + 4 * v574) + 1;
            _BitScanReverse((unsigned int *)&v578, v579);
            v580 = *(_DWORD *)(v572 + 76) + (((_DWORD)v574 - (_DWORD)v578) << 8) - (v579 << 8 >> v578);
            if ( (unsigned int)v575 <= 0x7F )
            {
              _mm_lfence();
              v582 = *((unsigned __int8 *)&qword_1803EF770[8] + v575);
            }
            else
            {
              _BitScanReverse(&v581, v575);
              LODWORD(v636) = 0;
              v582 = v581 + 36;
            }
            v583 = 4 * v582;
            LODWORD(v639) = 0;
            v584 = *(_DWORD *)(*(_QWORD *)(v572 + 16) + 4 * v582) + 1;
            _BitScanReverse(&v585, v584);
            v577 = v580
                 + v644
                 + *(_DWORD *)(v572 + 72)
                 + ((*(_DWORD *)((char *)&qword_1803EF640[10] + v583) - v585) << 8)
                 - (v584 << 8 >> v585)
                 + 51;
          }
          v298 = v651;
          if ( v573 <= v302 )
          {
            if ( v577 < v651[7 * v573] )
            {
              if ( v302 < v573 )
                goto LABEL_698;
LABEL_699:
              v586 = 7LL * v573;
              v587 = v640;
              *(_QWORD *)&v298[v586 + 4] = v569;
              v298[v586 + 6] = v570;
              v298[v586 + 2] = v573 - v567;
              v298[v586 + 1] = v564;
              v298[v586 + 3] = v587;
              v298[v586] = v577;
            }
            if ( --v573 - v567 < v571 )
            {
              v562 = v641;
              v566 = v649;
              goto LABEL_703;
            }
            continue;
          }
          break;
        }
        do
LABEL_698:
          v298[7 * ++v302] = 0x40000000;
        while ( v302 < v573 );
        goto LABEL_699;
      }
      v588 = 0;
      v273 = v651;
      DWORD1(v666) = v645[2 * v688 - 2];
      v589 = 7LL * v643;
      *((_QWORD *)&v666 + 1) = __PAIR64__(v640, v561);
      if ( v651[v589 + 2] )
        v590 = 0;
      else
        v590 = v651[v589 + 3];
      v267 = a3;
      v591 = 0;
      if ( v643 - v590 <= 0x1000 )
        v591 = v643 - v590;
LABEL_718:
      v597 = v591 + 1;
      v598 = v591 + 1;
      v599 = 7LL * (v591 + 1);
      v600 = v661;
      *(_OWORD *)&v273[v599] = v666;
      *(_QWORD *)&v273[v599 + 4] = v15;
      v273[v599 + 6] = v600;
      while ( v591 )
      {
        v601 = &v273[7 * v591];
        v602 = *(_OWORD *)v601;
        v672 = v601[6];
        v603 = *((_QWORD *)v601 + 2);
        v670 = v602;
        v671 = v603;
        *(double *)&v602 = ZSTD_totalLen(&v670);
        v604 = 7LL * --v598;
        *(_OWORD *)&v273[v604] = v602;
        *(_QWORD *)&v273[v604 + 4] = *(_QWORD *)(v605 + 16);
        v273[v604 + 6] = *(_DWORD *)(v605 + 24);
        v606 = v591;
        v591 -= v607;
        if ( v606 <= v607 )
          v591 = v588;
      }
      if ( v598 <= v597 )
      {
        v608 = v684;
        while ( 1 )
        {
          v609 = 7LL * v598;
          v610 = v273[v609 + 2];
          v611 = (unsigned int)v273[v609 + 3];
          v612 = v273[v609 + 1];
          v613 = v610 + v611;
          if ( v610 )
            break;
          v646 = v608 + v611;
LABEL_746:
          v267 = a3;
          ++v598;
          v588 = 0;
          if ( v598 > v597 )
            goto LABEL_747;
        }
        if ( v612 >= 3 )
        {
          v267[2] = v267[1];
          v267[1] = *v267;
          *v267 = v612 - 2;
          goto LABEL_734;
        }
        v614 = v588;
        LOBYTE(v614) = (_DWORD)v611 == 0;
        v615 = v612 + v614;
        if ( (_DWORD)v615 )
        {
          if ( (_DWORD)v615 == 3 )
          {
            v616 = *v267 - 1;
            goto LABEL_732;
          }
          v616 = v267[v615];
          if ( (unsigned int)v615 >= 2 )
LABEL_732:
            v267[2] = v267[1];
          v267[1] = *v267;
          *v267 = v616;
        }
LABEL_734:
        ZSTD_updateStats(v656, v611, v684, v612, v610);
        v617 = v610 - 3;
        v619 = v618;
        v620 = *(_QWORD *)(a2 + 24);
        if ( v618 + v684 <= v635 - 32 )
        {
          ZSTD_copy16(v620);
          if ( v619 > 0x10 )
          {
            ZSTD_copy16(*(_QWORD *)(a2 + 24) + 16LL);
            v623 = ZSTD_copy16(v622 + 16);
            v625 = v624 + 16;
            if ( v625 < v623 )
            {
              do
              {
                ZSTD_copy16(v625);
                v627 = ZSTD_copy16(v626 + 16);
                v625 = v628 + 16;
              }
              while ( v625 < v627 );
            }
LABEL_740:
            v621 = v684;
          }
          *(_QWORD *)(a2 + 24) += v619;
          v629 = *(_QWORD *)(a2 + 8);
          if ( v619 > 0xFFFF )
          {
            *(_DWORD *)(a2 + 72) = 1;
            *(_DWORD *)(a2 + 76) = (v629 - *(_QWORD *)a2) >> 3;
          }
          *(_WORD *)(v629 + 4) = v619;
          **(_DWORD **)(a2 + 8) = v612 + 1;
          v630 = *(_QWORD *)(a2 + 8);
          if ( v617 > 0xFFFF )
          {
            *(_DWORD *)(a2 + 72) = 2;
            *(_DWORD *)(a2 + 76) = (v630 - *(_QWORD *)a2) >> 3;
          }
          v273 = v651;
          *(_WORD *)(v630 + 6) = v617;
          *(_QWORD *)(a2 + 8) += 8LL;
          v684 = v613 + v621;
          v608 = v684;
          v646 = v684;
          goto LABEL_746;
        }
        ZSTD_safecopyLiterals(v620);
        goto LABEL_740;
      }
LABEL_747:
      ZSTD_setBasePrices(v656, 2);
      v14 = v646;
LABEL_750:
      v10 = v635;
      v5 = a1;
      v8 = v684;
    }
    while ( v14 < v665 );
  }
  return v10 - v8;
}

```

## disassembly

```asm
0x1802d40a0  mov     [rsp-8+arg_18], r9
0x1802d40a5  mov     [rsp-8+arg_10], r8
0x1802d40aa  mov     [rsp-8+arg_8], rdx
0x1802d40af  mov     [rsp-8+arg_0], rcx
0x1802d40b4  push    rbp
0x1802d40b5  push    rbx
0x1802d40b6  push    rsi
0x1802d40b7  push    rdi
0x1802d40b8  push    r12
0x1802d40ba  push    r13
0x1802d40bc  lea     rbp, [rsp-0D8h]
0x1802d40c4  sub     rsp, 1D8h
0x1802d40cb  mov     r8, [rbp+100h+arg_20]
0x1802d40d2  mov     r12, rcx
0x1802d40d5  add     rcx, 48h ; 'H'
0x1802d40d9  mov     edx, 0FFFh
0x1802d40de  mov     rdi, r9
0x1802d40e1  mov     [rbp+100h+var_138], rcx
0x1802d40e5  mov     eax, [r12+0CCh]
0x1802d40ed  lea     r13, [r9+r8]
0x1802d40f1  mov     ebx, [r12+18h]
0x1802d40f6  lea     rsi, [r13-8]
0x1802d40fa  add     rbx, [r12+8]
0x1802d40ff  mov     r9d, 2
0x1802d4105  cmp     eax, edx
0x1802d4107  mov     [rsp+200h+var_1C0], r13
0x1802d410c  mov     [rbp+100h+var_F8], rsi
0x1802d4110  cmovb   edx, eax
0x1802d4113  xor     eax, eax
0x1802d4115  cmp     dword ptr [r12+0C8h], 3
0x1802d411e  mov     [rbp+100h+var_11C], edx
0x1802d4121  mov     rdx, rdi
0x1802d4124  setnz   al
0x1802d4127  add     eax, 3
0x1802d412a  mov     [rbp+100h+var_148], eax
0x1802d412d  mov     eax, [r12+24h]
0x1802d4132  mov     [rbp+100h+var_120], eax
0x1802d4135  mov     rax, [rcx+28h]
0x1802d4139  mov     [rbp+100h+var_158], rax
0x1802d413d  mov     rax, [rcx+20h]
0x1802d4141  mov     [rbp+100h+var_180], rax
0x1802d4145  call    ZSTD_rescaleFreqs
0x1802d414a  xor     r9d, r9d
0x1802d414d  cmp     rdi, rbx
0x1802d4150  mov     ecx, r9d
0x1802d4153  setz    cl
0x1802d4156  add     rcx, rdi
0x1802d4159  mov     [rbp+100h+var_178], rcx
0x1802d415d  cmp     rcx, rsi
0x1802d4160  jnb     loc_1802D70B2
0x1802d4166  mov     eax, [rbp+100h+var_D8]
0x1802d4169  movsd   xmm2, [rbp+100h+var_E0]
0x1802d416e  mov     [rsp+200h+var_30], r14
0x1802d4176  mov     [rsp+200h+var_38], r15
0x1802d417e  mov     [rbp+100h+var_118], eax
0x1802d4181  mov     ebx, [r12+24h]
0x1802d4186  mov     eax, ecx
0x1802d4188  mov     r14, [r12+8]
0x1802d418d  sub     eax, edi
0x1802d418f  mov     esi, [r12+0C8h]
0x1802d4197  mov     r15d, r9d
0x1802d419a  setz    r15b
0x1802d419e  mov     [rbp+100h+var_16C], eax
0x1802d41a1  mov     [rsp+200h+var_1A8], r15d
0x1802d41a6  lea     rax, [r14+rbx]
0x1802d41aa  cmp     rcx, rax
0x1802d41ad  jb      loc_1802D7078
0x1802d41b3  mov     edi, ecx
0x1802d41b5  sub     edi, r14d
0x1802d41b8  cmp     ebx, edi
0x1802d41ba  jnb     short loc_1802D41EA
0x1802d41bc  xor     r15d, r15d
0x1802d41bf  nop
0x1802d41c0  mov     edx, ebx
0x1802d41c2  mov     r9d, esi
0x1802d41c5  add     rdx, r14
0x1802d41c8  mov     [rsp+200h+var_1E0], r15d
0x1802d41cd  mov     r8, r13
0x1802d41d0  mov     rcx, r12
0x1802d41d3  call    ZSTD_insertBt1
0x1802d41d8  add     ebx, eax
0x1802d41da  cmp     ebx, edi
0x1802d41dc  jb      short loc_1802D41C0
0x1802d41de  mov     r15d, [rsp+200h+var_1A8]
0x1802d41e3  xor     r9d, r9d
0x1802d41e6  mov     rcx, [rbp+100h+var_178]
0x1802d41ea  mov     r8, [r12+30h]
0x1802d41ef  mov     [r12+24h], edi
0x1802d41f4  mov     edx, [r12+0C0h]
0x1802d41fc  cmp     esi, 3
0x1802d41ff  jz      loc_1802D4F02
0x1802d4205  mov     r14d, 0FFFh
0x1802d420b  mov     ebx, ecx
0x1802d420d  cmp     esi, 5
0x1802d4210  jz      loc_1802D4AC4
0x1802d4216  lea     eax, [rsi-6]
0x1802d4219  cmp     eax, 1
0x1802d421c  mov     eax, [r12+0CCh]
0x1802d4224  ja      loc_1802D468C
0x1802d422a  cmp     eax, r14d
0x1802d422d  cmovb   r14d, eax
0x1802d4231  mov     rax, [r12+8]
0x1802d4236  sub     ebx, eax
0x1802d4238  mov     [rsp+200h+var_190], rax
0x1802d423d  mov     [rsp+200h+var_198], ebx
0x1802d4241  call    ZSTD_hash6Ptr
0x1802d4246  mov     ecx, [r12+0BCh]
0x1802d424e  lea     r15, [r8+rax*4]
0x1802d4252  mov     r8d, [r12+1Ch]
0x1802d4257  dec     ecx
0x1802d4259  mov     rdi, [r12+40h]
0x1802d425e  mov     eax, ebx
0x1802d4260  mov     r10d, [r15]
0x1802d4263  mov     edx, 1
0x1802d4268  mov     r11d, 1
0x1802d426e  mov     [rsp+200h+var_1A0], r9
0x1802d4273  shl     r11d, cl
0x1802d4276  xor     r9d, r9d
0x1802d4279  xor     ecx, ecx
0x1802d427b  mov     [rbp+100h+var_168], rdi
0x1802d427f  dec     r11d
0x1802d4282  mov     [rsp+200h+var_1B8], r9
0x1802d4287  sub     eax, r11d
0x1802d428a  mov     [rsp+200h+var_1CC], r11d
0x1802d428f  cmp     r11d, ebx
0x1802d4292  cmovb   ecx, eax
0x1802d4295  mov     eax, ebx
0x1802d4297  sub     eax, r8d
0x1802d429a  mov     [rsp+200h+var_1C8], ecx
0x1802d429e  mov     ecx, [r12+0B8h]
0x1802d42a6  shl     edx, cl
0x1802d42a8  mov     ecx, ebx
0x1802d42aa  sub     ecx, edx
0x1802d42ac  cmp     eax, edx
0x1802d42ae  mov     eax, 1
0x1802d42b3  cmovbe  ecx, r8d
0x1802d42b7  cmp     [r12+20h], r9d
0x1802d42bc  cmovnz  ecx, r8d
0x1802d42c0  test    ecx, ecx
0x1802d42c2  cmovnz  eax, ecx
0x1802d42c5  mov     ecx, [r12+0C4h]
0x1802d42cd  mov     [rsp+200h+var_194], eax
0x1802d42d1  xor     edx, edx
0x1802d42d3  mov     eax, r11d
0x1802d42d6  mov     dword ptr [rbp+100h+arg_20], edx
0x1802d42dc  and     eax, ebx
0x1802d42de  add     eax, eax
0x1802d42e0  lea     r13, [rdi+rax*4]
0x1802d42e4  mov     edi, ebx
0x1802d42e6  lea     rax, [r13+4]
0x1802d42ea  mov     [rsp+200h+var_1B0], rax
0x1802d42ef  lea     eax, [rbx+9]
0x1802d42f2  mov     [rsp+200h+var_1D0], eax
0x1802d42f6  mov     eax, 1
0x1802d42fb  shl     eax, cl
0x1802d42fd  mov     rcx, [rbp+100h+arg_0]
0x1802d4304  mov     [rsp+200h+var_184], eax
0x1802d4308  mov     eax, [rbp+100h+var_148]
0x1802d430b  dec     eax
0x1802d430d  sub     edi, [rcx+18h]
0x1802d4310  mov     r12d, eax
0x1802d4313  mov     rcx, [rbp+100h+arg_10]
0x1802d431a  mov     [rbp+100h+var_140], rax
0x1802d431e  mov     eax, [rsp+200h+var_1A8]
0x1802d4322  mov     r11d, eax
0x1802d4325  lea     esi, [rax+3]
0x1802d4328  lea     rbx, [rcx+rax*4]
0x1802d432c  nop     dword ptr [rax+00h]
0x1802d4330  cmp     r11d, 3
0x1802d4334  jnz     short loc_1802D433C
0x1802d4336  mov     ecx, [rcx]
0x1802d4338  dec     ecx
0x1802d433a  jmp     short loc_1802D433E
0x1802d433c  mov     ecx, [rbx]
0x1802d433e  lea     eax, [rcx-1]
0x1802d4341  mov     r8d, edx
0x1802d4344  cmp     eax, edi
0x1802d4346  jnb     loc_1802D4415
0x1802d434c  mov     r9d, ecx
0x1802d434f  mov     edx, 4
0x1802d4354  mov     rcx, [rbp+100h+var_178]
0x1802d4358  neg     r9
0x1802d435b  call    ZSTD_readMINMATCH
0x1802d4360  cmp     eax, [r9+rcx]
0x1802d4364  jnz     loc_1802D440E
0x1802d436a  lea     rdx, [rcx+4]
0x1802d436e  lea     r8, [rcx+4]
0x1802d4372  mov     rcx, [rsp+200h+var_1C0]
0x1802d4377  add     r8, r9
0x1802d437a  mov     r9, rdx
0x1802d437d  lea     rax, [rcx-7]
0x1802d4381  cmp     rdx, rax
0x1802d4384  jnb     short loc_1802D43C2
0x1802d4386  mov     rcx, [rdx]
0x1802d4389  xor     rcx, [r8]
0x1802d438c  jz      short loc_1802D4397
0x1802d438e  call    ZSTD_NbCommonBytes
0x1802d4393  mov     ecx, eax
0x1802d4395  jmp     short loc_1802D440A
0x1802d4397  add     rdx, 8
0x1802d439b  add     r8, 8
0x1802d439f  cmp     rdx, rax
0x1802d43a2  jnb     short loc_1802D43BD
0x1802d43a4  mov     rcx, [rdx]
0x1802d43a7  xor     rcx, [r8]
0x1802d43aa  jnz     loc_1802D4467
0x1802d43b0  add     rdx, 8
0x1802d43b4  add     r8, 8
0x1802d43b8  cmp     rdx, rax
0x1802d43bb  jb      short loc_1802D43A4
0x1802d43bd  mov     rcx, [rsp+200h+var_1C0]
0x1802d43c2  lea     rax, [rcx-3]
0x1802d43c6  cmp     rdx, rax
0x1802d43c9  jnb     short loc_1802D43DA
0x1802d43cb  mov     eax, [rdx]
0x1802d43cd  cmp     [r8], eax
0x1802d43d0  jnz     short loc_1802D43DA
0x1802d43d2  add     rdx, 4
0x1802d43d6  add     r8, 4
0x1802d43da  lea     rax, [rcx-1]
0x1802d43de  cmp     rdx, rax
0x1802d43e1  jnb     short loc_1802D43F4
0x1802d43e3  movzx   eax, word ptr [rdx]
0x1802d43e6  cmp     [r8], ax
0x1802d43ea  jnz     short loc_1802D43F4
0x1802d43ec  add     rdx, 2
0x1802d43f0  add     r8, 2
0x1802d43f4  cmp     rdx, rcx
0x1802d43f7  jnb     short loc_1802D4404
0x1802d43f9  movzx   eax, byte ptr [rdx]
0x1802d43fc  cmp     [r8], al
0x1802d43ff  jnz     short loc_1802D4404
0x1802d4401  inc     rdx
0x1802d4404  mov     rcx, rdx
0x1802d4407  sub     rcx, r9
0x1802d440a  lea     r8d, [rcx+4]
0x1802d440e  mov     r9d, dword ptr [rbp+100h+arg_20]
0x1802d4415  mov     edx, r8d
0x1802d4418  cmp     rdx, r12
0x1802d441b  jbe     short loc_1802D4476
0x1802d441d  mov     rcx, [rbp+100h+var_180]
0x1802d4421  mov     r12d, edx
0x1802d4424  mov     eax, r9d
0x1802d4427  inc     r9d
0x1802d442a  lea     rcx, [rcx+rax*8]
0x1802d442e  mov     eax, r11d
0x1802d4431  mov     [rcx+4], r8d
0x1802d4435  sub     eax, [rsp+200h+var_1A8]
0x1802d4439  mov     [rcx], eax
0x1802d443b  mov     rax, [rbp+100h+var_178]
0x1802d443f  add     rax, rdx
0x1802d4442  mov     dword ptr [rbp+100h+arg_20], r9d
0x1802d4449  xor     edx, edx
0x1802d444b  cmp     rax, [rsp+200h+var_1C0]
0x1802d4450  mov     ecx, edx
0x1802d4452  mov     eax, edx
0x1802d4454  setz    cl
0x1802d4457  cmp     r8d, r14d
0x1802d445a  setnbe  al
0x1802d445d  or      ecx, eax
0x1802d445f  jnz     loc_1802D460B
0x1802d4465  jmp     short loc_1802D4478
0x1802d4467  call    ZSTD_NbCommonBytes
0x1802d446c  mov     ecx, eax
0x1802d446e  sub     rdx, r9
0x1802d4471  add     rcx, rdx
0x1802d4474  jmp     short loc_1802D440A
0x1802d4476  xor     edx, edx
0x1802d4478  mov     rcx, [rbp+100h+arg_10]
0x1802d447f  inc     r11d
0x1802d4482  add     rbx, 4
0x1802d4486  cmp     r11d, esi
0x1802d4489  jb      loc_1802D4330
0x1802d448f  mov     esi, [rsp+200h+var_184]
0x1802d4493  mov     eax, [rsp+200h+var_198]
0x1802d4497  mov     [r15], eax
0x1802d449a  test    esi, esi
0x1802d449c  jz      loc_1802D45EF
0x1802d44a2  dec     esi
0x1802d44a4  cmp     r10d, [rsp+200h+var_194]
0x1802d44a9  jb      loc_1802D45EF
0x1802d44af  mov     eax, [rsp+200h+var_1CC]
0x1802d44b3  mov     r15, [rsp+200h+var_1B8]
0x1802d44b8  and     eax, r10d
0x1802d44bb  mov     rcx, [rbp+100h+var_168]
0x1802d44bf  add     eax, eax
0x1802d44c1  cmp     [rsp+200h+var_1A0], r15
0x1802d44c6  mov     r9, r15
0x1802d44c9  mov     r15, [rbp+100h+var_178]
0x1802d44cd  cmovb   r9, [rsp+200h+var_1A0]
0x1802d44d3  mov     r14, [rsp+200h+var_1C0]
0x1802d44d8  lea     rdi, [rcx+rax*4]
0x1802d44dc  mov     r11d, r10d
0x1802d44df  add     r11, [rsp+200h+var_190]
0x1802d44e4  lea     rdx, [r9+r15]
0x1802d44e8  lea     rax, [r14-7]
0x1802d44ec  mov     rbx, rdx
0x1802d44ef  lea     r8, [r11+r9]
0x1802d44f3  cmp     rdx, rax
0x1802d44f6  jnb     short loc_1802D4539
  ... truncated ...
```
