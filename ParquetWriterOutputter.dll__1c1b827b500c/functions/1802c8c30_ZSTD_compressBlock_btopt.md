# ZSTD_compressBlock_btopt

- ea: `0x1802c8c30`
- end: `0x1802cbc69`
- name: `ZSTD_compressBlock_btopt`
- size: `12345`
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
- `0x1802c8c30`
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
unsigned __int64 __fastcall ZSTD_compressBlock_btopt(__int64 a1, __int64 a2, int *a3, unsigned __int64 a4, __int64 a5)
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
  int *v45; // rcx
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
  int *v104; // rcx
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
  int *v160; // rcx
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
  int *v217; // rcx
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
  int *v267; // r15
  unsigned int v268; // edi
  __int64 v269; // rdx
  __int64 v270; // r13
  __int64 v271; // r8
  int v272; // eax
  _DWORD *v273; // r9
  unsigned int *v274; // r14
  unsigned int v275; // r10d
  unsigned int v276; // edi
  unsigned int v277; // r12d
  unsigned int v278; // esi
  __int64 v279; // rcx
  int v280; // eax
  _DWORD *v281; // r8
  __int128 v282; // xmm0
  __int64 v283; // xmm1_8
  __int64 v284; // rdx
  __int64 v285; // r8
  unsigned int v286; // ecx
  unsigned int v287; // eax
  __int64 v288; // r13
  unsigned __int64 v289; // r8
  __int64 v290; // rcx
  int v291; // ebx
  __int64 v292; // rdx
  unsigned int v293; // edi
  unsigned int v294; // r15d
  unsigned __int64 v295; // rcx
  unsigned int v296; // edi
  _DWORD *v297; // rax
  unsigned int *v298; // r13
  unsigned int *v299; // r12
  unsigned int v300; // ebx
  unsigned int v301; // esi
  __int64 updated; // rax
  int v303; // r11d
  __int64 v304; // xmm1_8
  int v305; // r15d
  __int64 v306; // r13
  __int64 v307; // r8
  __int64 v308; // r9
  unsigned int v309; // ecx
  int v310; // edx
  unsigned int v311; // eax
  int v312; // r10d
  unsigned int v313; // eax
  __int64 v314; // rax
  __int64 v315; // rdx
  _DWORD *v316; // r9
  __int64 v317; // rcx
  unsigned int v318; // eax
  __int64 v319; // r13
  unsigned int v320; // eax
  unsigned int v321; // edi
  __int64 v322; // r15
  _DWORD *v323; // r12
  _DWORD *v324; // r14
  unsigned int v325; // esi
  int v326; // ebx
  int v327; // ebx
  int v328; // eax
  __int64 v329; // r8
  int v330; // eax
  _DWORD *v331; // rbx
  int v332; // r15d
  __int64 v333; // xmm0_8
  int v334; // eax
  int v335; // eax
  unsigned int v336; // ecx
  __int64 v337; // rbx
  __int64 v338; // r15
  int v339; // r14d
  unsigned int v340; // esi
  int v341; // r12d
  __int64 v342; // r8
  __int64 v343; // rdx
  unsigned int v344; // r15d
  unsigned int v345; // eax
  unsigned int v346; // ebx
  __int64 v347; // rax
  __int64 v348; // r8
  unsigned int *v349; // r12
  int v350; // r8d
  _DWORD *v351; // rsi
  unsigned int v352; // r10d
  _DWORD *v353; // r9
  int v354; // r11d
  unsigned int v355; // ecx
  unsigned int v356; // r11d
  unsigned int v357; // edx
  int v358; // ecx
  int v359; // eax
  int v360; // ecx
  unsigned __int64 v361; // r13
  unsigned int v362; // r11d
  unsigned int v363; // r14d
  _DWORD *v364; // rcx
  unsigned int v365; // esi
  unsigned int *v366; // rbx
  unsigned int v367; // ecx
  unsigned int v368; // r8d
  int v369; // eax
  __int64 v370; // rcx
  __int64 v371; // r9
  _QWORD *v372; // rdx
  __int64 v373; // r8
  unsigned __int64 v374; // rcx
  _QWORD *v375; // r8
  _QWORD *v376; // r9
  unsigned __int64 v377; // rax
  int v378; // ecx
  __int64 v379; // rax
  _DWORD *v380; // rcx
  int v381; // eax
  int v382; // edx
  int v383; // r9d
  unsigned int v384; // r14d
  unsigned __int64 v385; // r9
  _DWORD *v386; // r15
  _DWORD *v387; // r12
  unsigned int *v388; // rsi
  __int64 v389; // r11
  _QWORD *v390; // rdx
  unsigned __int64 v391; // rax
  char *v392; // rbx
  _QWORD *v393; // r8
  unsigned __int64 v394; // rcx
  unsigned __int64 v395; // r9
  _DWORD *v396; // rcx
  int v397; // eax
  unsigned int v398; // eax
  __int64 v399; // rdx
  _DWORD *v400; // rax
  unsigned int v401; // eax
  int *v402; // rax
  _DWORD *v403; // rax
  unsigned int v404; // ebx
  __int64 v405; // rax
  __int64 v406; // r8
  unsigned int *v407; // r12
  int v408; // r8d
  _DWORD *v409; // rsi
  unsigned int v410; // r10d
  _DWORD *v411; // r9
  int v412; // r11d
  unsigned int v413; // ecx
  unsigned int v414; // r11d
  unsigned int v415; // edx
  int v416; // ecx
  int v417; // eax
  int v418; // ecx
  unsigned __int64 v419; // r13
  unsigned int v420; // r11d
  unsigned int v421; // r14d
  _DWORD *v422; // rcx
  unsigned int v423; // esi
  unsigned int *v424; // rbx
  unsigned int v425; // ecx
  unsigned int v426; // r8d
  int v427; // eax
  __int64 v428; // rcx
  __int64 v429; // r9
  _QWORD *v430; // rdx
  __int64 v431; // r8
  unsigned __int64 v432; // rcx
  _QWORD *v433; // r8
  _QWORD *v434; // r9
  unsigned __int64 v435; // rax
  int v436; // ecx
  __int64 v437; // rax
  _DWORD *v438; // rcx
  int v439; // eax
  int v440; // edx
  int v441; // r9d
  unsigned int v442; // r14d
  unsigned __int64 v443; // r9
  _DWORD *v444; // r15
  _DWORD *v445; // r12
  unsigned int *v446; // rsi
  __int64 v447; // r11
  _QWORD *v448; // rdx
  unsigned __int64 v449; // rax
  char *v450; // rbx
  _QWORD *v451; // r8
  unsigned __int64 v452; // rcx
  unsigned __int64 v453; // r9
  _DWORD *v454; // rcx
  int v455; // eax
  unsigned int v456; // eax
  __int64 v457; // rdx
  _DWORD *v458; // rax
  unsigned int v459; // ebx
  __int64 v460; // rax
  __int64 v461; // r8
  unsigned int *v462; // r12
  int v463; // r8d
  _DWORD *v464; // rsi
  unsigned int v465; // r10d
  _DWORD *v466; // r9
  int v467; // r11d
  unsigned int v468; // ecx
  unsigned int v469; // r11d
  unsigned int v470; // edx
  int v471; // ecx
  int v472; // eax
  int v473; // ecx
  unsigned __int64 v474; // r13
  unsigned int v475; // r11d
  unsigned int v476; // r14d
  _DWORD *v477; // rcx
  unsigned int v478; // esi
  unsigned int *v479; // rbx
  unsigned int v480; // ecx
  unsigned int v481; // r8d
  int v482; // eax
  __int64 v483; // rcx
  __int64 v484; // r9
  _QWORD *v485; // rdx
  __int64 v486; // r8
  unsigned __int64 v487; // rcx
  _QWORD *v488; // r8
  _QWORD *v489; // r9
  unsigned __int64 v490; // rax
  int v491; // ecx
  __int64 v492; // rax
  _DWORD *v493; // rcx
  int v494; // eax
  int v495; // edx
  int v496; // r9d
  int v497; // r14d
  unsigned __int64 v498; // r9
  _DWORD *v499; // r15
  _DWORD *v500; // r12
  unsigned int *v501; // rsi
  __int64 v502; // r11
  _QWORD *v503; // rdx
  unsigned __int64 v504; // rax
  char *v505; // rbx
  _QWORD *v506; // r8
  unsigned __int64 v507; // rcx
  unsigned __int64 v508; // r9
  _DWORD *v509; // rcx
  int v510; // eax
  unsigned int v511; // eax
  __int64 v512; // rdx
  _DWORD *v513; // rax
  unsigned int v514; // r14d
  unsigned int v515; // r10d
  __int64 v516; // rax
  unsigned int v517; // r10d
  __int64 v518; // r8
  unsigned int *v519; // r13
  unsigned int v520; // ebx
  int v521; // r8d
  _DWORD *v522; // rsi
  unsigned int v523; // ecx
  unsigned int v524; // r11d
  unsigned int v525; // edx
  int v526; // ecx
  int v527; // eax
  int v528; // ecx
  unsigned int v529; // r8d
  unsigned int v530; // r12d
  unsigned int v531; // r11d
  _DWORD *v532; // rcx
  unsigned int v533; // r15d
  unsigned int *v534; // rsi
  unsigned int v535; // ecx
  unsigned int v536; // r9d
  int v537; // eax
  __int64 v538; // rcx
  __int64 v539; // r10
  int v540; // r8d
  _QWORD *v541; // rdx
  __int64 v542; // r9
  _QWORD *v543; // r8
  _DWORD *v544; // r10
  unsigned __int64 v545; // rax
  int v546; // eax
  int v547; // edx
  int v548; // r9d
  __int64 v549; // rax
  _DWORD *v550; // rcx
  unsigned __int64 v551; // r15
  _DWORD *v552; // r12
  unsigned int v553; // eax
  unsigned int v554; // esi
  unsigned int v555; // r8d
  unsigned __int64 v556; // rax
  int v557; // r11d
  _DWORD *v558; // rdx
  int v559; // ecx
  int v560; // r11d
  unsigned int v561; // eax
  int v562; // r14d
  unsigned __int64 v563; // r9
  _DWORD *v564; // r12
  _DWORD *v565; // r13
  unsigned int *v566; // rsi
  unsigned __int64 v567; // r10
  _QWORD *v568; // rdx
  unsigned __int64 v569; // rax
  _QWORD *v570; // r8
  signed __int64 v571; // rcx
  unsigned __int64 v572; // r9
  _DWORD *v573; // rcx
  int v574; // eax
  unsigned int v575; // eax
  __int64 v576; // rdx
  __int64 v577; // r11
  char *v578; // rax
  _DWORD *v579; // r14
  unsigned int v580; // ebx
  unsigned int v581; // ecx
  unsigned int v582; // r13d
  unsigned int *v583; // r10
  int v584; // r15d
  __int64 v585; // rax
  _DWORD *v586; // r10
  unsigned int v587; // edx
  int v588; // r11d
  __int64 v589; // xmm1_8
  unsigned int v590; // r14d
  __int64 v591; // r13
  unsigned int v592; // eax
  int v593; // esi
  unsigned int v594; // ebx
  __int64 v595; // r9
  __int64 v596; // r10
  unsigned int v597; // edx
  signed int v598; // r8d
  unsigned int v599; // ecx
  int v600; // r11d
  unsigned int v601; // ecx
  __int64 v602; // rcx
  __int64 v603; // r8
  int v604; // edx
  __int64 v605; // rcx
  __int64 v606; // rdx
  _DWORD *v607; // rdx
  __int64 v608; // rdx
  __int128 v609; // xmm0
  unsigned int v610; // eax
  int v611; // eax
  __int64 v612; // rax
  unsigned int v613; // ecx
  __int64 v614; // rcx
  int v615; // r8d
  unsigned int v616; // r14d
  unsigned __int64 v617; // rdx
  unsigned __int64 v618; // rbx
  __int64 v619; // rcx
  unsigned __int64 v620; // rdx
  __int64 v621; // r10
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
  unsigned int v638; // [rsp+58h] [rbp-A8h]
  unsigned int v639; // [rsp+5Ch] [rbp-A4h]
  unsigned int v640; // [rsp+60h] [rbp-A0h]
  _DWORD *v641; // [rsp+68h] [rbp-98h]
  unsigned int v642; // [rsp+70h] [rbp-90h]
  char *v643; // [rsp+78h] [rbp-88h]
  int v644; // [rsp+80h] [rbp-80h]
  _DWORD *v645; // [rsp+88h] [rbp-78h]
  unsigned __int64 v646; // [rsp+90h] [rbp-70h]
  unsigned int v647; // [rsp+98h] [rbp-68h] BYREF
  _DWORD *v648; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v649; // [rsp+A8h] [rbp-58h]
  unsigned int v650; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD *v651; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v652; // [rsp+C0h] [rbp-40h]
  int v653; // [rsp+C8h] [rbp-38h]
  int v654; // [rsp+CCh] [rbp-34h] BYREF
  __int64 v655; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v656; // [rsp+D8h] [rbp-28h]
  int v657; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v658; // [rsp+E8h] [rbp-18h]
  int v659; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v660; // [rsp+F4h] [rbp-Ch]
  int v661; // [rsp+F8h] [rbp-8h]
  int v662; // [rsp+FCh] [rbp-4h]
  unsigned __int64 v663; // [rsp+100h] [rbp+0h]
  unsigned __int64 v664; // [rsp+108h] [rbp+8h]
  char v665; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v666; // [rsp+118h] [rbp+18h]
  __int128 v667; // [rsp+120h] [rbp+20h]
  __int64 v668; // [rsp+130h] [rbp+30h]
  int v669; // [rsp+138h] [rbp+38h]
  int v670; // [rsp+148h] [rbp+48h]
  __int128 v671; // [rsp+150h] [rbp+50h] BYREF
  __int64 v672; // [rsp+160h] [rbp+60h]
  int v673; // [rsp+168h] [rbp+68h]
  __int128 v674; // [rsp+170h] [rbp+70h] BYREF
  __int64 v675; // [rsp+180h] [rbp+80h]
  int v676; // [rsp+188h] [rbp+88h]
  __int128 v677; // [rsp+190h] [rbp+90h] BYREF
  __int64 v678; // [rsp+1A0h] [rbp+A0h]
  int v679; // [rsp+1A8h] [rbp+A8h]
  char v680[16]; // [rsp+1B0h] [rbp+B0h] BYREF
  char v681[24]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int64 v685; // [rsp+238h] [rbp+138h]
  unsigned int v686; // [rsp+240h] [rbp+140h]
  unsigned int v687; // [rsp+240h] [rbp+140h]
  unsigned int *v688; // [rsp+240h] [rbp+140h]
  unsigned int v689; // [rsp+240h] [rbp+140h]

  v685 = a4;
  v5 = a1;
  v6 = a1 + 72;
  v7 = 4095;
  v8 = a4;
  v655 = v6;
  v9 = *(_DWORD *)(v5 + 204);
  v10 = a4 + a5;
  v11 = a4 + a5 - 8;
  v12 = *(_QWORD *)(v5 + 8) + *(unsigned int *)(v5 + 24);
  v635 = a4 + a5;
  v666 = v11;
  if ( v9 < 0xFFF )
    v7 = v9;
  v13 = *(_DWORD *)(v5 + 200) == 3;
  v660 = v7;
  v653 = !v13 + 3;
  v659 = *(_DWORD *)(v5 + 36);
  v651 = *(_DWORD **)(v6 + 40);
  v645 = *(_DWORD **)(v6 + 32);
  ZSTD_rescaleFreqs(v6, a4, a5, 0);
  v14 = v8 + (v8 == v12);
  v646 = v14;
  if ( v14 < v11 )
  {
    v15 = v668;
    v661 = v669;
    do
    {
      v16 = *(unsigned int *)(v5 + 36);
      v17 = *(_QWORD *)(v5 + 8);
      v18 = *(_DWORD *)(v5 + 200);
      v19 = v14 == v8;
      v640 = v14 - v8;
      v638 = v19;
      if ( v14 < v17 + v16 )
        goto LABEL_754;
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
            v643 = *(char **)(v5 + 8);
            v642 = v25;
            v26 = ZSTD_hash6Ptr(v14, v22, v21);
            v28 = (unsigned int *)(v27 + 4 * v26);
            v29 = *(_DWORD *)(v5 + 28);
            v30 = *(_DWORD *)(v5 + 188) - 1;
            v31 = *(_DWORD **)(v5 + 64);
            v32 = *v28;
            v641 = v33;
            v34 = 1 << v30;
            v35 = 0;
            v36 = 0;
            v648 = v31;
            v37 = v34 - 1;
            v636 = 0;
            v639 = v37;
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
            v633 = v40;
            v686 = 0;
            v42 = &v31[2 * (v25 & v37)];
            v637 = v42 + 1;
            v632 = v25 + 9;
            v644 = 1 << v41;
            v43 = v25 - *(_DWORD *)(a1 + 24);
            v44 = (unsigned int)(v653 - 1);
            v45 = a3;
            v656 = v44;
            v46 = v638;
            v47 = v638 + 3;
            v48 = (unsigned int *)&a3[v638];
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
              v35 = v686;
LABEL_47:
              if ( v50 > v44 )
              {
                v44 = v50;
                v61 = v35++;
                v62 = &v645[2 * v61];
                v62[1] = v50;
                *v62 = v46 - v638;
                v686 = v35;
                if ( v50 > v23 || v50 + v646 == v635 )
                  goto LABEL_78;
              }
              v45 = a3;
              ++v46;
              ++v48;
              if ( v46 >= v47 )
              {
                v66 = v644;
                *v28 = v642;
                while ( v66 )
                {
                  --v66;
                  if ( v32 < v633 )
                    break;
                  v67 = v636;
                  v68 = v646;
                  if ( v641 < v636 )
                    v67 = v641;
                  v69 = v635;
                  v70 = &v648[2 * (v32 & v639)];
                  v71 = &v643[v32];
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
                    v79 = v642 - v32 + 2;
                    v645[2 * v686 + 1] = v77;
                    v78[2 * v686++] = v79;
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
                    v641 = (_DWORD *)v77;
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
                v82 = v686;
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
          v643 = *(char **)(v5 + 8);
          v642 = v85;
          v86 = ZSTD_hash4Ptr(v14, v22, v21);
          v88 = (unsigned int *)(v87 + 4 * v86);
          v89 = *(_DWORD *)(v5 + 28);
          v90 = *(_DWORD *)(v5 + 188) - 1;
          v91 = *(_DWORD **)(v5 + 64);
          v92 = *v88;
          v641 = v93;
          v94 = 1 << v90;
          v95 = 0;
          v96 = 0;
          v648 = v91;
          v97 = v94 - 1;
          v636 = 0;
          v639 = v97;
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
          v633 = v100;
          v686 = 0;
          v42 = &v91[2 * (v85 & v97)];
          v637 = v42 + 1;
          v632 = v85 + 9;
          v644 = 1 << v101;
          v102 = v85 - *(_DWORD *)(a1 + 24);
          v103 = (unsigned int)(v653 - 1);
          v104 = a3;
          v656 = v103;
          v105 = v638;
          v106 = v638 + 3;
          v107 = (unsigned int *)&a3[v638];
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
            v95 = v686;
LABEL_124:
            if ( v109 > v103 )
            {
              v103 = v109;
              v120 = v95++;
              v121 = &v645[2 * v120];
              v121[1] = v109;
              *v121 = v105 - v638;
              v686 = v95;
              if ( v109 > v23 || v109 + v646 == v635 )
                goto LABEL_78;
            }
            v104 = a3;
            ++v105;
            ++v107;
            if ( v105 >= v106 )
            {
              v125 = v644;
              *v88 = v642;
              if ( !v125 )
                goto LABEL_76;
              while ( 2 )
              {
                --v125;
                if ( v92 < v633 )
                  goto LABEL_76;
                v126 = v636;
                v127 = v646;
                if ( v641 < v636 )
                  v126 = v641;
                v128 = v635;
                v129 = &v648[2 * (v92 & v639)];
                v130 = &v643[v92];
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
                      v138 = v642 - v92 + 2;
                      v645[2 * v686 + 1] = v136;
                      v137[2 * v686++] = v138;
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
                      v641 = (_DWORD *)v136;
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
        v643 = *(char **)(v5 + 8);
        v642 = v141;
        v142 = ZSTD_hash5Ptr(v14, v22, v21);
        v144 = (unsigned int *)(v143 + 4 * v142);
        v145 = *(_DWORD *)(v5 + 28);
        v146 = *(_DWORD *)(v5 + 188) - 1;
        v147 = *(_DWORD **)(v5 + 64);
        v148 = *v144;
        v641 = v149;
        v150 = 1 << v146;
        v151 = 0;
        v152 = 0;
        v648 = v147;
        v153 = v150 - 1;
        v636 = 0;
        v639 = v153;
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
        v633 = v156;
        v686 = 0;
        v42 = &v147[2 * (v141 & v153)];
        v637 = v42 + 1;
        v632 = v141 + 9;
        v644 = 1 << v157;
        v158 = v141 - *(_DWORD *)(a1 + 24);
        v159 = (unsigned int)(v653 - 1);
        v160 = a3;
        v656 = v159;
        v161 = v638;
        v162 = v638 + 3;
        v163 = (unsigned int *)&a3[v638];
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
          v151 = v686;
LABEL_199:
          if ( v165 > v159 )
          {
            v159 = v165;
            v176 = v151++;
            v177 = &v645[2 * v176];
            v177[1] = v165;
            *v177 = v161 - v638;
            v686 = v151;
            if ( v165 > v23 || v165 + v646 == v635 )
              goto LABEL_78;
          }
          v160 = a3;
          ++v161;
          ++v163;
          if ( v161 >= v162 )
          {
            v181 = v644;
            *v144 = v642;
            if ( !v181 )
              goto LABEL_76;
            while ( 2 )
            {
              --v181;
              if ( v148 < v633 )
                goto LABEL_76;
              v182 = v636;
              v183 = v646;
              if ( v641 < v636 )
                v182 = v641;
              v184 = v635;
              v185 = &v648[2 * (v148 & v639)];
              v186 = &v643[v148];
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
                    v194 = v642 - v148 + 2;
                    v645[2 * v686 + 1] = v192;
                    v193[2 * v686++] = v194;
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
                    v641 = (_DWORD *)v192;
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
      v643 = v204;
      v205 = *(_DWORD *)(a1 + 28);
      v206 = *(_DWORD **)(a1 + 64);
      v207 = 0;
      v208 = (1 << (*(_DWORD *)(a1 + 188) - 1)) - 1;
      v648 = v206;
      v644 = v208;
      v649 = 0;
      if ( v208 < v200 )
        v207 = v200 - v208;
      v642 = v207;
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
      v639 = v211;
      v687 = 0;
      v213 = v19 + 3;
      v214 = 0;
      v637 = &v206[2 * (v200 & v208)];
      v641 = v637 + 1;
      v632 = v200 + 9;
      v647 = 1 << v212;
      v215 = v200 - *(_DWORD *)(a1 + 24);
      v216 = (unsigned int)(v653 - 1);
      v217 = a3;
      v656 = v216;
      v218 = v638;
      v219 = (unsigned int *)&a3[v638];
      while ( 1 )
      {
        if ( v218 == 3 )
          v220 = *v217 - 1;
        else
          v220 = *v219;
        v221 = 0;
        if ( v220 - 1 >= v215 )
          goto LABEL_273;
        v670 = 1;
        v222 = ZSTD_readMINMATCH(v646, 3, (unsigned int)(*(_DWORD *)(v646 - v220) << 8), 0);
        if ( v222 != v225 )
        {
          v214 = v687;
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
          goto LABEL_759;
        if ( *v226 != *v228 )
        {
          v231 = ZSTD_NbCommonBytes(*v226 ^ *v228, v226, v228, v227);
          v214 = v687;
          v221 = v231 + 3;
          goto LABEL_274;
        }
        v226 = (_QWORD *)(v223 + 11);
        ++v228;
        if ( v223 + 11 >= v230 )
        {
LABEL_759:
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
          v214 = v687;
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
          v214 = v687;
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
          v687 = v214;
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
        v240 = v639;
LABEL_286:
        v246 = v687;
        goto LABEL_287;
      }
      v237 = v646;
      FirstIndexHash3 = ZSTD_insertAndFindFirstIndexHash3(a1, &v659, v646);
      v239 = v633;
      v240 = v639;
      if ( FirstIndexHash3 < v639 || v633 - FirstIndexHash3 >= 0x40000 )
        goto LABEL_286;
      v241 = v635;
      v242 = ZSTD_count(v237, (char *)v636 + FirstIndexHash3, v635);
      if ( v242 < 3 )
        goto LABEL_285;
      v244 = v645;
      v245 = v243 + 2;
      v246 = 1;
      v216 = v242;
      v687 = 1;
      *v645 = v245;
      v244[1] = v242;
      if ( v242 > v197 || v242 + v237 == v241 )
      {
        v247 = v239 + 1;
        goto LABEL_326;
      }
      v240 = v639;
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
          v250 = (_DWORD *)v649;
          v251 = v646;
          if ( (unsigned __int64)v643 < v649 )
            v250 = v643;
          v252 = v635;
          v253 = &v648[2 * (v203 & v644)];
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
                v246 = v687;
              }
              else
              {
                if ( v259 > v249 - v203 )
                  v249 = v203 + v259;
                v216 = v259;
                v260 = v645;
                v261 = v633 - v203 + 2;
                v645[2 * v687 + 1] = v259;
                v246 = v687 + 1;
                v260[2 * v687++] = v261;
                if ( v259 > 0x1000 || v259 + v251 == v252 )
                  goto LABEL_324;
              }
              if ( (unsigned __int8)v254[v259] >= *(_BYTE *)(v259 + v251) )
              {
                v649 = v259;
                *v641 = v203;
                if ( v203 <= v642 )
                {
                  v641 = &v632;
                  goto LABEL_324;
                }
                v203 = *v253;
                v641 = v253;
              }
              else
              {
                v643 = (char *)v259;
                *v637 = v203;
                if ( v203 <= v642 )
                {
                  v265 = &v632;
                  goto LABEL_325;
                }
                v203 = v253[1];
                v637 = v253 + 1;
              }
              if ( !v248 )
                goto LABEL_324;
              v240 = v639;
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
      *v641 = 0;
      *v265 = 0;
      v247 = v249 - 8;
LABEL_326:
      v82 = v246;
      *(_DWORD *)(a1 + 36) = v247;
LABEL_327:
      if ( !v82 )
      {
        v14 = v646;
LABEL_754:
        v646 = ++v14;
        goto LABEL_755;
      }
      v266 = v651;
      v267 = a3;
      v268 = v640;
      v269 = v640;
      v270 = v655;
      v271 = v655;
      v651[4] = *a3;
      v266[5] = a3[1];
      v266[6] = a3[2];
      v266[2] = 0;
      v266[3] = v268;
      v272 = ZSTD_literalsContribution(v685, v269, v271, 0);
      v273 = v651;
      v274 = v645;
      *v651 = v272;
      if ( v274[2 * v82 - 1] > v660 )
      {
        *(_QWORD *)((char *)&v667 + 4) = *(_QWORD *)&v274[2 * v82 - 2];
        HIDWORD(v667) = v268;
        goto LABEL_330;
      }
      ZSTD_litLengthPrice(0, v270, 0);
      v295 = v656;
      v296 = v656 + 1;
      v297 = v651 + 7;
      do
      {
        *v297 = 0x40000000;
        v297 += 7;
        --v295;
      }
      while ( v295 );
      v298 = (unsigned int *)v82;
      v299 = v274;
      v637 = (unsigned int *)v82;
      v688 = v274;
      do
      {
        v300 = *v299;
        v301 = v299[1];
        updated = ZSTD_updateRep(v681, v267, *v299, v638);
        v304 = *(_QWORD *)updated;
        v305 = *(_DWORD *)(updated + 8);
        if ( v296 > v301 )
        {
          v316 = v651;
        }
        else
        {
          v306 = v655;
          do
          {
            _BitScanReverse((unsigned int *)&v307, v300 + 1);
            v308 = v296 - 3;
            if ( *(_DWORD *)(v306 + 80) == 1 )
            {
              _BitScanReverse(&v309, v296 - 2);
              v310 = v303 + ((v309 + (_DWORD)v307 + 16) << 8);
            }
            else
            {
              _BitScanReverse(&v311, *(_DWORD *)(*(_QWORD *)(v306 + 24) + 4 * v307) + 1);
              v312 = *(_DWORD *)(v306 + 76) + (((_DWORD)v307 - v311) << 8);
              if ( (unsigned int)v307 >= 0x14 )
                v312 = ((_DWORD)v307 << 9) + v312 - 9728;
              if ( (unsigned int)v308 <= 0x7F )
              {
                _mm_lfence();
                v314 = *((unsigned __int8 *)&qword_1803EF770[8] + v308);
              }
              else
              {
                _BitScanReverse(&v313, v308);
                LODWORD(v664) = 0;
                v314 = v313 + 36;
              }
              v315 = 4 * v314;
              LODWORD(v663) = 0;
              _BitScanReverse((unsigned int *)&v314, *(_DWORD *)(*(_QWORD *)(v306 + 16) + 4 * v314) + 1);
              v310 = v303
                   + *(_DWORD *)(v306 + 72)
                   + ((*(_DWORD *)((char *)&qword_1803EF640[10] + v315) - (_DWORD)v314) << 8)
                   + v312
                   + 51;
            }
            v316 = v651;
            v317 = 7LL * v296;
            v318 = v640;
            v651[v317 + 2] = v296++;
            *(_QWORD *)&v316[v317 + 4] = v304;
            v316[v317 + 1] = v300;
            v316[v317 + 3] = v318;
            v316[v317] = v310;
            v316[v317 + 6] = v305;
          }
          while ( v296 <= v301 );
          v299 = v688;
          v298 = v637;
        }
        v267 = a3;
        v299 += 2;
        v298 = (unsigned int *)((char *)v298 - 1);
        v688 = v299;
        v637 = v298;
      }
      while ( v298 );
      v319 = v655;
      v320 = 1;
      v321 = v296 - 1;
      v639 = 1;
      if ( !v321 )
        goto LABEL_722;
      while ( 2 )
      {
        v322 = v320;
        v323 = (_DWORD *)(v320 + v646);
        v324 = &v316[7 * v320 - 7];
        v641 = v323;
        if ( v324[2] )
          v325 = 1;
        else
          v325 = v324[3] + 1;
        v326 = *v324 - ZSTD_litLengthPrice(v325 - 1, v319, 0);
        v327 = ZSTD_rawLiteralsCost((char *)v323 - 1, 1, v319) + v326;
        v328 = ZSTD_litLengthPrice(v325, v319, 0);
        v316 = v651;
        v330 = v327 + v328;
        v331 = &v651[7 * v322];
        v332 = *v331;
        if ( v330 <= *v331 )
        {
          v333 = *((_QWORD *)v324 + 2);
          v332 = v330;
          *v331 = v330;
          v334 = v324[6];
          *((_QWORD *)v331 + 2) = v333;
          v331[6] = v334;
          *(_QWORD *)(v331 + 1) = v329;
          v331[3] = v325;
        }
        if ( (unsigned __int64)v323 > v666 )
          goto LABEL_721;
        if ( v639 == v321 )
        {
LABEL_722:
          v607 = &v316[7 * v321];
          v609 = *(_OWORD *)v607;
          v661 = v607[6];
          v15 = *((_QWORD *)v607 + 2);
          v667 = v609;
          v676 = v661;
          v674 = v609;
          v675 = v15;
          *(double *)&v609 = ZSTD_totalLen(&v674);
          if ( v321 > v610 )
          {
            v679 = *(_DWORD *)(v608 + 24);
            v677 = v609;
            v678 = v15;
            ZSTD_totalLen(&v677);
            v276 = v321 - v611;
            v275 = 0;
            goto LABEL_331;
          }
LABEL_330:
          v275 = 0;
          v276 = 0;
          goto LABEL_331;
        }
        if ( v316[7 * v639 + 7] <= v332 + 128 )
          goto LABEL_721;
        v335 = v331[2];
        v336 = v329;
        LOBYTE(v336) = v335 != 0;
        v638 = v336;
        if ( v335 )
          v642 = v329;
        else
          v642 = v331[3];
        v644 = v332 + ZSTD_litLengthPrice(0, v319, 0);
        v637 = v331 + 4;
        v337 = *(unsigned int *)(a1 + 36);
        v338 = *(_QWORD *)(a1 + 8);
        v339 = *(_DWORD *)(a1 + 200);
        if ( (unsigned __int64)v323 < v338 + v337 )
        {
          v316 = v651;
          goto LABEL_721;
        }
        v340 = (_DWORD)v323 - v338;
        if ( (unsigned int)v337 < (int)v323 - (int)v338 )
        {
          v341 = v635;
          do
            LODWORD(v337) = ZSTD_insertBt1(a1, (int)v338 + (int)v337, v341, v339, 0) + v337;
          while ( (unsigned int)v337 < v340 );
          v323 = v641;
        }
        v342 = *(_QWORD *)(a1 + 48);
        *(_DWORD *)(a1 + 36) = v340;
        v343 = *(unsigned int *)(a1 + 192);
        if ( v339 != 3 )
        {
          v344 = 4095;
          if ( v339 != 5 )
          {
            v345 = *(_DWORD *)(a1 + 204);
            if ( (unsigned int)(v339 - 6) <= 1 )
            {
              if ( v345 < 0xFFF )
                v344 = *(_DWORD *)(a1 + 204);
              v346 = (_DWORD)v323 - *(_QWORD *)(a1 + 8);
              v658 = *(_QWORD *)(a1 + 8);
              v640 = v346;
              v347 = ZSTD_hash6Ptr(v323, v343, v342);
              v349 = (unsigned int *)(v348 + 4 * v347);
              v350 = *(_DWORD *)(a1 + 28);
              v351 = *(_DWORD **)(a1 + 64);
              v352 = *v349;
              v353 = v641;
              v354 = 1 << (*(_DWORD *)(a1 + 188) - 1);
              v355 = 0;
              v648 = v351;
              v356 = v354 - 1;
              v649 = 0;
              v652 = 0;
              v650 = v356;
              if ( v356 < v346 )
                v355 = v346 - v356;
              v634 = v355;
              v357 = 1 << *(_DWORD *)(a1 + 184);
              v358 = v346 - v357;
              v359 = 1;
              if ( v346 - v350 <= v357 )
                v358 = v350;
              if ( *(_DWORD *)(a1 + 32) )
                v358 = v350;
              if ( v358 )
                v359 = v358;
              v360 = *(_DWORD *)(a1 + 196);
              v361 = v656;
              v632 = v359;
              v689 = 0;
              v636 = &v351[2 * (v346 & v356)];
              v643 = (char *)(v636 + 1);
              v633 = v346 + 9;
              v647 = 1 << v360;
              v362 = v638;
              v363 = v346 - *(_DWORD *)(a1 + 24);
              v364 = v637;
              v365 = v638 + 3;
              v366 = &v637[v638];
              while ( 2 )
              {
                if ( v362 == 3 )
                  v367 = *v364 - 1;
                else
                  v367 = *v366;
                v368 = 0;
                if ( v367 - 1 >= v363 )
                  goto LABEL_411;
                v369 = ZSTD_readMINMATCH(v641, 4, 0, -(__int64)v367);
                if ( v369 != *(_DWORD *)(v371 + v370) )
                  goto LABEL_410;
                v372 = (_QWORD *)(v370 + 4);
                v373 = v370 + 4;
                v374 = v635;
                v375 = (_QWORD *)(v371 + v373);
                v376 = v372;
                v377 = v635 - 7;
                if ( (unsigned __int64)v372 < v635 - 7 )
                {
                  if ( *v375 != *v372 )
                  {
                    v378 = ZSTD_NbCommonBytes(*v375 ^ *v372, v372, v375, v372);
                    goto LABEL_409;
                  }
                  ++v372;
                  ++v375;
                  if ( (unsigned __int64)v372 < v377 )
                  {
                    while ( *v375 == *v372 )
                    {
                      ++v372;
                      ++v375;
                      if ( (unsigned __int64)v372 >= v377 )
                        goto LABEL_398;
                    }
                    v381 = ZSTD_NbCommonBytes(*v375 ^ *v372, v372, v375, v376);
                    v378 = v382 - v383 + v381;
LABEL_409:
                    v368 = v378 + 4;
LABEL_410:
                    v353 = v641;
LABEL_411:
                    if ( v368 > v361 )
                    {
                      v379 = v689;
                      v361 = v368;
                      ++v689;
                      v380 = &v645[2 * v379];
                      v380[1] = v368;
                      *v380 = v362 - v638;
                      if ( v368 > v344 || (_DWORD *)((char *)v353 + v368) == (_DWORD *)v635 )
                        goto LABEL_692;
                    }
                    v364 = v637;
                    ++v362;
                    ++v366;
                    if ( v362 >= v365 )
                    {
                      v384 = v647;
                      *v349 = v640;
                      if ( v384 )
                      {
                        while ( 1 )
                        {
                          --v384;
                          if ( v352 < v632 )
                            break;
                          v385 = v652;
                          v386 = v641;
                          if ( v649 < v652 )
                            v385 = v649;
                          v387 = (_DWORD *)v635;
                          v388 = &v648[2 * (v352 & v650)];
                          v389 = v658 + v352;
                          v390 = (_QWORD *)((char *)v641 + v385);
                          v391 = v635 - 7;
                          v392 = (char *)v641 + v385;
                          v393 = (_QWORD *)(v389 + v385);
                          if ( (unsigned __int64)v641 + v385 >= v635 - 7 )
                            goto LABEL_426;
                          if ( *v393 != *v390 )
                          {
                            v394 = (unsigned int)ZSTD_NbCommonBytes(*v393 ^ *v390, v390, v393, v385);
                            goto LABEL_436;
                          }
                          ++v390;
                          ++v393;
                          if ( (unsigned __int64)v390 >= v391 )
                          {
LABEL_426:
                            if ( (unsigned __int64)v390 < v635 - 3 && *(_DWORD *)v393 == *(_DWORD *)v390 )
                            {
                              v390 = (_QWORD *)((char *)v390 + 4);
                              v393 = (_QWORD *)((char *)v393 + 4);
                            }
                            if ( (unsigned __int64)v390 < v635 - 1 && *(_WORD *)v393 == *(_WORD *)v390 )
                            {
                              v390 = (_QWORD *)((char *)v390 + 2);
                              v393 = (_QWORD *)((char *)v393 + 2);
                            }
                            if ( (unsigned __int64)v390 < v635 && *(_BYTE *)v393 == *(_BYTE *)v390 )
                              v390 = (_QWORD *)((char *)v390 + 1);
                            v394 = (char *)v390 - v392;
                          }
                          else
                          {
                            while ( *v393 == *v390 )
                            {
                              ++v390;
                              ++v393;
                              if ( (unsigned __int64)v390 >= v391 )
                                goto LABEL_426;
                            }
                            v398 = ZSTD_NbCommonBytes(*v393 ^ *v390, v390, v393, v385);
                            v394 = v399 - (_QWORD)v392 + v398;
                          }
LABEL_436:
                          v395 = v394 + v385;
                          if ( v395 > v361 )
                          {
                            if ( v395 > v633 - v352 )
                              v633 = v352 + v395;
                            v361 = v395;
                            v396 = v645;
                            v397 = v640 - v352 + 2;
                            v645[2 * v689 + 1] = v395;
                            v396[2 * v689++] = v397;
                            if ( v395 > 0x1000 || (_DWORD *)((char *)v386 + v395) == v387 )
                              break;
                          }
                          if ( *(_BYTE *)(v389 + v395) >= *((_BYTE *)v386 + v395) )
                          {
                            v652 = v395;
                            *(_DWORD *)v643 = v352;
                            if ( v352 <= v634 )
                            {
                              v402 = (int *)&v650;
                              goto LABEL_451;
                            }
                            v352 = *v388;
                            v643 = (char *)v388;
                          }
                          else
                          {
                            v649 = v395;
                            *v636 = v352;
                            if ( v352 <= v634 )
                            {
                              *(_DWORD *)v643 = 0;
                              v650 = 0;
                              v401 = v633;
                              goto LABEL_690;
                            }
                            v352 = v388[1];
                            v636 = v388 + 1;
                          }
                          if ( !v384 )
                          {
                            v400 = v636;
                            *(_DWORD *)v643 = 0;
                            *v400 = 0;
                            v401 = v633;
                            goto LABEL_690;
                          }
                        }
                      }
LABEL_452:
                      v403 = v636;
                      *(_DWORD *)v643 = 0;
                      *v403 = 0;
                      v401 = v633;
LABEL_690:
                      v561 = v401 - 8;
                      goto LABEL_691;
                    }
                    continue;
                  }
LABEL_398:
                  v374 = v635;
                }
                break;
              }
              if ( (unsigned __int64)v372 < v374 - 3 && *(_DWORD *)v375 == *(_DWORD *)v372 )
              {
                v372 = (_QWORD *)((char *)v372 + 4);
                v375 = (_QWORD *)((char *)v375 + 4);
              }
              if ( (unsigned __int64)v372 < v374 - 1 && *(_WORD *)v375 == *(_WORD *)v372 )
              {
                v372 = (_QWORD *)((char *)v372 + 2);
                v375 = (_QWORD *)((char *)v375 + 2);
              }
              if ( (unsigned __int64)v372 < v374 && *(_BYTE *)v375 == *(_BYTE *)v372 )
                LODWORD(v372) = (_DWORD)v372 + 1;
              v378 = (_DWORD)v372 - (_DWORD)v376;
              goto LABEL_409;
            }
            if ( v345 < 0xFFF )
              v344 = *(_DWORD *)(a1 + 204);
            v404 = (_DWORD)v323 - *(_QWORD *)(a1 + 8);
            v658 = *(_QWORD *)(a1 + 8);
            v640 = v404;
            v405 = ZSTD_hash4Ptr(v323, v343, v342);
            v407 = (unsigned int *)(v406 + 4 * v405);
            v408 = *(_DWORD *)(a1 + 28);
            v409 = *(_DWORD **)(a1 + 64);
            v410 = *v407;
            v411 = v641;
            v412 = 1 << (*(_DWORD *)(a1 + 188) - 1);
            v413 = 0;
            v648 = v409;
            v414 = v412 - 1;
            v649 = 0;
            v652 = 0;
            v632 = v414;
            if ( v414 < v404 )
              v413 = v404 - v414;
            v634 = v413;
            v415 = 1 << *(_DWORD *)(a1 + 184);
            v416 = v404 - v415;
            v417 = 1;
            if ( v404 - v408 <= v415 )
              v416 = v408;
            if ( *(_DWORD *)(a1 + 32) )
              v416 = v408;
            if ( v416 )
              v417 = v416;
            v418 = *(_DWORD *)(a1 + 196);
            v419 = v656;
            v647 = v417;
            v689 = 0;
            v636 = &v409[2 * (v404 & v414)];
            v643 = (char *)(v636 + 1);
            v633 = v404 + 9;
            v650 = 1 << v418;
            v420 = v638;
            v421 = v404 - *(_DWORD *)(a1 + 24);
            v422 = v637;
            v423 = v638 + 3;
            v424 = &v637[v638];
            while ( 2 )
            {
              if ( v420 == 3 )
                v425 = *v422 - 1;
              else
                v425 = *v424;
              v426 = 0;
              if ( v425 - 1 >= v421 )
                goto LABEL_488;
              v427 = ZSTD_readMINMATCH(v641, 4, 0, -(__int64)v425);
              if ( v427 != *(_DWORD *)(v429 + v428) )
                goto LABEL_487;
              v430 = (_QWORD *)(v428 + 4);
              v431 = v428 + 4;
              v432 = v635;
              v433 = (_QWORD *)(v429 + v431);
              v434 = v430;
              v435 = v635 - 7;
              if ( (unsigned __int64)v430 < v635 - 7 )
              {
                if ( *v433 != *v430 )
                {
                  v436 = ZSTD_NbCommonBytes(*v433 ^ *v430, v430, v433, v430);
                  goto LABEL_486;
                }
                ++v430;
                ++v433;
                if ( (unsigned __int64)v430 < v435 )
                {
                  while ( *v433 == *v430 )
                  {
                    ++v430;
                    ++v433;
                    if ( (unsigned __int64)v430 >= v435 )
                      goto LABEL_475;
                  }
                  v439 = ZSTD_NbCommonBytes(*v433 ^ *v430, v430, v433, v434);
                  v436 = v440 - v441 + v439;
LABEL_486:
                  v426 = v436 + 4;
LABEL_487:
                  v411 = v641;
LABEL_488:
                  if ( v426 > v419 )
                  {
                    v437 = v689;
                    v419 = v426;
                    ++v689;
                    v438 = &v645[2 * v437];
                    v438[1] = v426;
                    *v438 = v420 - v638;
                    if ( v426 > v344 || (_DWORD *)((char *)v411 + v426) == (_DWORD *)v635 )
                      goto LABEL_692;
                  }
                  v422 = v637;
                  ++v420;
                  ++v424;
                  if ( v420 >= v423 )
                  {
                    v442 = v650;
                    *v407 = v640;
                    if ( !v442 )
                      goto LABEL_452;
                    while ( 2 )
                    {
                      --v442;
                      if ( v410 < v647 )
                        goto LABEL_452;
                      v443 = v652;
                      v444 = v641;
                      if ( v649 < v652 )
                        v443 = v649;
                      v445 = (_DWORD *)v635;
                      v446 = &v648[2 * (v410 & v632)];
                      v447 = v658 + v410;
                      v448 = (_QWORD *)((char *)v641 + v443);
                      v449 = v635 - 7;
                      v450 = (char *)v641 + v443;
                      v451 = (_QWORD *)(v447 + v443);
                      if ( (unsigned __int64)v641 + v443 < v635 - 7 )
                      {
                        if ( *v451 != *v448 )
                        {
                          v452 = (unsigned int)ZSTD_NbCommonBytes(*v451 ^ *v448, v448, v451, v443);
LABEL_513:
                          v453 = v452 + v443;
                          if ( v453 > v419 )
                          {
                            if ( v453 > v633 - v410 )
                              v633 = v453 + v410;
                            v419 = v453;
                            v454 = v645;
                            v455 = v640 - v410 + 2;
                            v645[2 * v689 + 1] = v453;
                            v454[2 * v689++] = v455;
                            if ( v453 > 0x1000 || (_DWORD *)((char *)v444 + v453) == v445 )
                              goto LABEL_452;
                          }
                          if ( *(_BYTE *)(v447 + v453) >= *((_BYTE *)v444 + v453) )
                          {
                            v652 = v453;
                            *(_DWORD *)v643 = v410;
                            if ( v410 <= v634 )
                            {
                              v402 = &v654;
                              goto LABEL_451;
                            }
                            v410 = *v446;
                            v643 = (char *)v446;
                          }
                          else
                          {
                            v649 = v453;
                            *v636 = v410;
                            if ( v410 <= v634 )
                            {
                              *(_DWORD *)v643 = 0;
                              v654 = 0;
                              v401 = v633;
                              goto LABEL_690;
                            }
                            v410 = v446[1];
                            v636 = v446 + 1;
                          }
                          if ( !v442 )
                          {
                            v458 = v636;
                            *(_DWORD *)v643 = 0;
                            *v458 = 0;
                            v401 = v633;
                            goto LABEL_690;
                          }
                          continue;
                        }
                        ++v448;
                        ++v451;
                        if ( (unsigned __int64)v448 < v449 )
                        {
                          while ( *v451 == *v448 )
                          {
                            ++v448;
                            ++v451;
                            if ( (unsigned __int64)v448 >= v449 )
                              goto LABEL_503;
                          }
                          v456 = ZSTD_NbCommonBytes(*v451 ^ *v448, v448, v451, v443);
                          v452 = v457 - (_QWORD)v450 + v456;
                          goto LABEL_513;
                        }
                      }
                      break;
                    }
LABEL_503:
                    if ( (unsigned __int64)v448 < v635 - 3 && *(_DWORD *)v451 == *(_DWORD *)v448 )
                    {
                      v448 = (_QWORD *)((char *)v448 + 4);
                      v451 = (_QWORD *)((char *)v451 + 4);
                    }
                    if ( (unsigned __int64)v448 < v635 - 1 && *(_WORD *)v451 == *(_WORD *)v448 )
                    {
                      v448 = (_QWORD *)((char *)v448 + 2);
                      v451 = (_QWORD *)((char *)v451 + 2);
                    }
                    if ( (unsigned __int64)v448 < v635 && *(_BYTE *)v451 == *(_BYTE *)v448 )
                      v448 = (_QWORD *)((char *)v448 + 1);
                    v452 = (char *)v448 - v450;
                    goto LABEL_513;
                  }
                  continue;
                }
LABEL_475:
                v432 = v635;
              }
              break;
            }
            if ( (unsigned __int64)v430 < v432 - 3 && *(_DWORD *)v433 == *(_DWORD *)v430 )
            {
              v430 = (_QWORD *)((char *)v430 + 4);
              v433 = (_QWORD *)((char *)v433 + 4);
            }
            if ( (unsigned __int64)v430 < v432 - 1 && *(_WORD *)v433 == *(_WORD *)v430 )
            {
              v430 = (_QWORD *)((char *)v430 + 2);
              v433 = (_QWORD *)((char *)v433 + 2);
            }
            if ( (unsigned __int64)v430 < v432 && *(_BYTE *)v433 == *(_BYTE *)v430 )
              LODWORD(v430) = (_DWORD)v430 + 1;
            v436 = (_DWORD)v430 - (_DWORD)v434;
            goto LABEL_486;
          }
          if ( *(_DWORD *)(a1 + 204) < 0xFFFu )
            v344 = *(_DWORD *)(a1 + 204);
          v459 = (_DWORD)v323 - *(_QWORD *)(a1 + 8);
          v658 = *(_QWORD *)(a1 + 8);
          v640 = v459;
          v460 = ZSTD_hash5Ptr(v323, v343, v342);
          v462 = (unsigned int *)(v461 + 4 * v460);
          v463 = *(_DWORD *)(a1 + 28);
          v464 = *(_DWORD **)(a1 + 64);
          v465 = *v462;
          v466 = v641;
          v467 = 1 << (*(_DWORD *)(a1 + 188) - 1);
          v468 = 0;
          v648 = v464;
          v469 = v467 - 1;
          v649 = 0;
          v652 = 0;
          v647 = v469;
          if ( v469 < v459 )
            v468 = v459 - v469;
          v634 = v468;
          v470 = 1 << *(_DWORD *)(a1 + 184);
          v471 = v459 - v470;
          v472 = 1;
          if ( v459 - v463 <= v470 )
            v471 = v463;
          if ( *(_DWORD *)(a1 + 32) )
            v471 = v463;
          if ( v471 )
            v472 = v471;
          v473 = *(_DWORD *)(a1 + 196);
          v474 = v656;
          v650 = v472;
          v689 = 0;
          v636 = &v464[2 * (v459 & v469)];
          v643 = (char *)(v636 + 1);
          v633 = v459 + 9;
          v654 = 1 << v473;
          v475 = v638;
          v476 = v459 - *(_DWORD *)(a1 + 24);
          v477 = v637;
          v478 = v638 + 3;
          v479 = &v637[v638];
          while ( 2 )
          {
            if ( v475 == 3 )
              v480 = *v477 - 1;
            else
              v480 = *v479;
            v481 = 0;
            if ( v480 - 1 >= v476 )
              goto LABEL_563;
            v482 = ZSTD_readMINMATCH(v641, 4, 0, -(__int64)v480);
            if ( v482 != *(_DWORD *)(v484 + v483) )
              goto LABEL_562;
            v485 = (_QWORD *)(v483 + 4);
            v486 = v483 + 4;
            v487 = v635;
            v488 = (_QWORD *)(v484 + v486);
            v489 = v485;
            v490 = v635 - 7;
            if ( (unsigned __int64)v485 < v635 - 7 )
            {
              if ( *v488 != *v485 )
              {
                v491 = ZSTD_NbCommonBytes(*v488 ^ *v485, v485, v488, v485);
                goto LABEL_561;
              }
              ++v485;
              ++v488;
              if ( (unsigned __int64)v485 < v490 )
              {
                while ( *v488 == *v485 )
                {
                  ++v485;
                  ++v488;
                  if ( (unsigned __int64)v485 >= v490 )
                    goto LABEL_550;
                }
                v494 = ZSTD_NbCommonBytes(*v488 ^ *v485, v485, v488, v489);
                v491 = v495 - v496 + v494;
LABEL_561:
                v481 = v491 + 4;
LABEL_562:
                v466 = v641;
LABEL_563:
                if ( v481 > v474 )
                {
                  v492 = v689;
                  v474 = v481;
                  ++v689;
                  v493 = &v645[2 * v492];
                  v493[1] = v481;
                  *v493 = v475 - v638;
                  if ( v481 > v344 || (_DWORD *)((char *)v466 + v481) == (_DWORD *)v635 )
                    goto LABEL_692;
                }
                v477 = v637;
                ++v475;
                ++v479;
                if ( v475 >= v478 )
                {
                  v497 = v654;
                  *v462 = v640;
                  if ( !v497 )
                    goto LABEL_452;
                  while ( 2 )
                  {
                    --v497;
                    if ( v465 < v650 )
                      goto LABEL_452;
                    v498 = v652;
                    v499 = v641;
                    if ( v649 < v652 )
                      v498 = v649;
                    v500 = (_DWORD *)v635;
                    v501 = &v648[2 * (v465 & v647)];
                    v502 = v658 + v465;
                    v503 = (_QWORD *)((char *)v641 + v498);
                    v504 = v635 - 7;
                    v505 = (char *)v641 + v498;
                    v506 = (_QWORD *)(v502 + v498);
                    if ( (unsigned __int64)v641 + v498 < v635 - 7 )
                    {
                      if ( *v506 != *v503 )
                      {
                        v507 = (unsigned int)ZSTD_NbCommonBytes(*v506 ^ *v503, v503, v506, v498);
LABEL_588:
                        v508 = v507 + v498;
                        if ( v508 > v474 )
                        {
                          if ( v508 > v633 - v465 )
                            v633 = v508 + v465;
                          v474 = v508;
                          v509 = v645;
                          v510 = v640 - v465 + 2;
                          v645[2 * v689 + 1] = v508;
                          v509[2 * v689++] = v510;
                          if ( v508 > 0x1000 || (_DWORD *)((char *)v499 + v508) == v500 )
                            goto LABEL_452;
                        }
                        if ( *(_BYTE *)(v502 + v508) >= *((_BYTE *)v499 + v508) )
                        {
                          v652 = v508;
                          *(_DWORD *)v643 = v465;
                          if ( v465 <= v634 )
                          {
                            v402 = &v657;
LABEL_451:
                            v643 = (char *)v402;
                            goto LABEL_452;
                          }
                          v465 = *v501;
                          v643 = (char *)v501;
                        }
                        else
                        {
                          v649 = v508;
                          *v636 = v465;
                          if ( v465 <= v634 )
                          {
                            *(_DWORD *)v643 = 0;
                            v657 = 0;
                            v401 = v633;
                            goto LABEL_690;
                          }
                          v465 = v501[1];
                          v636 = v501 + 1;
                        }
                        if ( !v497 )
                        {
                          v513 = v636;
                          *(_DWORD *)v643 = 0;
                          *v513 = 0;
                          v401 = v633;
                          goto LABEL_690;
                        }
                        continue;
                      }
                      ++v503;
                      ++v506;
                      if ( (unsigned __int64)v503 < v504 )
                      {
                        while ( *v506 == *v503 )
                        {
                          ++v503;
                          ++v506;
                          if ( (unsigned __int64)v503 >= v504 )
                            goto LABEL_578;
                        }
                        v511 = ZSTD_NbCommonBytes(*v506 ^ *v503, v503, v506, v498);
                        v507 = v512 - (_QWORD)v505 + v511;
                        goto LABEL_588;
                      }
                    }
                    break;
                  }
LABEL_578:
                  if ( (unsigned __int64)v503 < v635 - 3 && *(_DWORD *)v506 == *(_DWORD *)v503 )
                  {
                    v503 = (_QWORD *)((char *)v503 + 4);
                    v506 = (_QWORD *)((char *)v506 + 4);
                  }
                  if ( (unsigned __int64)v503 < v635 - 1 && *(_WORD *)v506 == *(_WORD *)v503 )
                  {
                    v503 = (_QWORD *)((char *)v503 + 2);
                    v506 = (_QWORD *)((char *)v506 + 2);
                  }
                  if ( (unsigned __int64)v503 < v635 && *(_BYTE *)v506 == *(_BYTE *)v503 )
                    v503 = (_QWORD *)((char *)v503 + 1);
                  v507 = (char *)v503 - v505;
                  goto LABEL_588;
                }
                continue;
              }
LABEL_550:
              v487 = v635;
            }
            break;
          }
          if ( (unsigned __int64)v485 < v487 - 3 && *(_DWORD *)v488 == *(_DWORD *)v485 )
          {
            v485 = (_QWORD *)((char *)v485 + 4);
            v488 = (_QWORD *)((char *)v488 + 4);
          }
          if ( (unsigned __int64)v485 < v487 - 1 && *(_WORD *)v488 == *(_WORD *)v485 )
          {
            v485 = (_QWORD *)((char *)v485 + 2);
            v488 = (_QWORD *)((char *)v488 + 2);
          }
          if ( (unsigned __int64)v485 < v487 && *(_BYTE *)v488 == *(_BYTE *)v485 )
            LODWORD(v485) = (_DWORD)v485 + 1;
          v491 = (_DWORD)v485 - (_DWORD)v489;
          goto LABEL_561;
        }
        v514 = 4095;
        if ( *(_DWORD *)(a1 + 204) < 0xFFFu )
          v514 = *(_DWORD *)(a1 + 204);
        v515 = (_DWORD)v323 - *(_QWORD *)(a1 + 8);
        v652 = *(_QWORD *)(a1 + 8);
        v633 = v515;
        v516 = ZSTD_hash4Ptr(v323, v343, v342);
        v519 = (unsigned int *)(v518 + 4 * v516);
        v520 = *v519;
        v521 = *(_DWORD *)(a1 + 28);
        v522 = *(_DWORD **)(a1 + 64);
        v523 = 0;
        v524 = (1 << (*(_DWORD *)(a1 + 188) - 1)) - 1;
        v663 = 0;
        v664 = 0;
        v648 = v522;
        v654 = v524;
        if ( v524 < v517 )
          v523 = v517 - v524;
        v640 = v523;
        v525 = 1 << *(_DWORD *)(a1 + 184);
        v526 = v517 - v525;
        v527 = 1;
        if ( v517 - v521 <= v525 )
          v526 = v521;
        if ( *(_DWORD *)(a1 + 32) )
          v526 = v521;
        if ( v526 )
          v527 = v526;
        v528 = *(_DWORD *)(a1 + 196);
        v632 = v527;
        v689 = 0;
        v529 = 0;
        v636 = &v522[2 * (v517 & v524)];
        v643 = (char *)(v636 + 1);
        v634 = v517 + 9;
        v657 = 1 << v528;
        v649 = v656;
        v530 = v517 - *(_DWORD *)(a1 + 24);
        v531 = v638;
        v532 = v637;
        v533 = v638 + 3;
        v534 = &v637[v638];
        while ( 2 )
        {
          if ( v531 == 3 )
            v535 = *v532 - 1;
          else
            v535 = *v534;
          v536 = 0;
          if ( v535 - 1 >= v530 )
          {
            v544 = (_DWORD *)v635;
          }
          else
          {
            LODWORD(v658) = 1;
            v537 = ZSTD_readMINMATCH(v641, 3, (unsigned int)(*(_DWORD *)((char *)v641 - v535) << 8), 0);
            if ( v537 == v540 )
            {
              v541 = (_QWORD *)(v538 + 3);
              v542 = v538 + 3;
              v543 = (_QWORD *)(v539 + v538 + 3);
              v544 = (_DWORD *)v635;
              v545 = v635 - 7;
              if ( v538 + 3 >= v635 - 7 )
                goto LABEL_625;
              if ( *v543 != *v541 )
              {
                v536 = ZSTD_NbCommonBytes(*v543 ^ *v541, v541, v543, v542) + 3;
                goto LABEL_638;
              }
              v541 = (_QWORD *)(v538 + 11);
              ++v543;
              if ( v538 + 11 >= v545 )
              {
LABEL_625:
                if ( (unsigned __int64)v541 < v635 - 3 && *(_DWORD *)v543 == *(_DWORD *)v541 )
                {
                  v541 = (_QWORD *)((char *)v541 + 4);
                  v543 = (_QWORD *)((char *)v543 + 4);
                }
                if ( (unsigned __int64)v541 < v635 - 1 && *(_WORD *)v543 == *(_WORD *)v541 )
                {
                  v541 = (_QWORD *)((char *)v541 + 2);
                  v543 = (_QWORD *)((char *)v543 + 2);
                }
                if ( (unsigned __int64)v541 < v635 && *(_BYTE *)v543 == *(_BYTE *)v541 )
                  LODWORD(v541) = (_DWORD)v541 + 1;
                v536 = (_DWORD)v541 - v538;
              }
              else
              {
                while ( *v543 == *v541 )
                {
                  ++v541;
                  ++v543;
                  if ( (unsigned __int64)v541 >= v545 )
                    goto LABEL_625;
                }
                v546 = ZSTD_NbCommonBytes(*v543 ^ *v541, v541, v543, v542);
                v536 = v547 - v548 + v546 + 3;
              }
            }
            else
            {
              v544 = (_DWORD *)v635;
            }
LABEL_638:
            v529 = v689;
          }
          if ( v536 > v649 )
          {
            v549 = v529++;
            v550 = &v645[2 * v549];
            v550[1] = v536;
            *v550 = v531 - v638;
            v649 = v536;
            v689 = v529;
            if ( v536 > v514 || (_DWORD *)((char *)v641 + v536) == v544 )
              goto LABEL_692;
          }
          ++v531;
          ++v534;
          if ( v531 < v533 )
          {
            v532 = v637;
            continue;
          }
          break;
        }
        v551 = v649;
        if ( v649 >= 3 )
        {
          v554 = v633;
          v555 = v632;
          goto LABEL_649;
        }
        v552 = v641;
        v553 = ZSTD_insertAndFindFirstIndexHash3(a1, &v659, v641);
        v554 = v633;
        v555 = v632;
        if ( v553 < v632 || v633 - v553 >= 0x40000 )
          goto LABEL_649;
        v556 = ZSTD_count(v552, v652 + v553, v635);
        if ( v556 < 3 )
        {
          v555 = v632;
LABEL_649:
          v560 = v689;
LABEL_650:
          v562 = v657;
          *v519 = v554;
          if ( !v562 )
          {
LABEL_688:
            v578 = (char *)v636;
LABEL_689:
            v689 = v560;
            *(_DWORD *)v643 = 0;
            *(_DWORD *)v578 = 0;
            v401 = v634;
            goto LABEL_690;
          }
          while ( 2 )
          {
            --v562;
            if ( v520 < v555 )
              goto LABEL_688;
            v563 = v664;
            v564 = v641;
            if ( v663 < v664 )
              v563 = v663;
            v565 = (_DWORD *)v635;
            v566 = &v648[2 * (v520 & v654)];
            v567 = v652 + v520;
            v568 = (_QWORD *)((char *)v641 + v563);
            v569 = v635 - 7;
            v570 = (_QWORD *)(v567 + v563);
            if ( (unsigned __int64)v641 + v563 < v635 - 7 )
            {
              if ( *v570 != *v568 )
              {
                v571 = (unsigned int)ZSTD_NbCommonBytes(*v570 ^ *v568, v568, v570, v563);
LABEL_672:
                v572 = v571 + v563;
                if ( v572 <= v551 )
                {
                  v560 = v689;
                }
                else
                {
                  if ( v572 > v634 - v520 )
                    v634 = v520 + v572;
                  v551 = v572;
                  v573 = v645;
                  v574 = v633 - v520 + 2;
                  v645[2 * v689 + 1] = v572;
                  v573[2 * v689] = v574;
                  v560 = ++v689;
                  if ( v572 > 0x1000 || (_DWORD *)((char *)v564 + v572) == v565 )
                    goto LABEL_688;
                }
                if ( *(_BYTE *)(v567 + v572) >= *((_BYTE *)v564 + v572) )
                {
                  v664 = v572;
                  *(_DWORD *)v643 = v520;
                  if ( v520 <= v640 )
                  {
                    v643 = &v665;
                    goto LABEL_688;
                  }
                  v520 = *v566;
                  v643 = (char *)v566;
                }
                else
                {
                  v663 = v572;
                  *v636 = v520;
                  if ( v520 <= v640 )
                  {
                    v578 = &v665;
                    goto LABEL_689;
                  }
                  v520 = v566[1];
                  v636 = v566 + 1;
                }
                if ( !v562 )
                  goto LABEL_688;
                v555 = v632;
                continue;
              }
              ++v568;
              ++v570;
              if ( (unsigned __int64)v568 < v569 )
              {
                while ( *v570 == *v568 )
                {
                  ++v568;
                  ++v570;
                  if ( (unsigned __int64)v568 >= v569 )
                    goto LABEL_662;
                }
                v575 = ZSTD_NbCommonBytes(*v570 ^ *v568, v568, v570, v563);
                v571 = v576 - v577 + v575;
                goto LABEL_672;
              }
            }
            break;
          }
LABEL_662:
          if ( (unsigned __int64)v568 < v635 - 3 && *(_DWORD *)v570 == *(_DWORD *)v568 )
          {
            v568 = (_QWORD *)((char *)v568 + 4);
            v570 = (_QWORD *)((char *)v570 + 4);
          }
          if ( (unsigned __int64)v568 < v635 - 1 && *(_WORD *)v570 == *(_WORD *)v568 )
          {
            v568 = (_QWORD *)((char *)v568 + 2);
            v570 = (_QWORD *)((char *)v570 + 2);
          }
          if ( (unsigned __int64)v568 < v635 && *(_BYTE *)v570 == *(_BYTE *)v568 )
            v568 = (_QWORD *)((char *)v568 + 1);
          v571 = (char *)v568 - ((char *)v641 + v563);
          goto LABEL_672;
        }
        v558 = v645;
        v559 = v557 + 2;
        v560 = 1;
        v551 = v556;
        v689 = 1;
        *v645 = v559;
        v13 = (_DWORD *)((char *)v552 + v556) == (_DWORD *)v635;
        v558[1] = v556;
        if ( v556 <= v514 && !v13 )
        {
          v555 = v632;
          goto LABEL_650;
        }
        v561 = v554 + 1;
        v689 = 1;
LABEL_691:
        *(_DWORD *)(a1 + 36) = v561;
LABEL_692:
        if ( !v689 )
        {
          v316 = v651;
          goto LABEL_720;
        }
        v579 = v645;
        v580 = v639;
        v581 = v645[2 * v689 - 1];
        if ( v581 <= v660 && v581 + v639 < 0x1000 )
        {
          v582 = 0;
          v640 = 0;
          v583 = v645;
          v648 = v645;
          do
          {
            v584 = *v583;
            v585 = ZSTD_updateRep(v680, v637, *v583, v638);
            v587 = v586[1];
            v588 = *(_DWORD *)(v585 + 8);
            v589 = *(_QWORD *)v585;
            v662 = v588;
            if ( v582 )
              v590 = v579[2 * v582 - 1] + 1;
            else
              v590 = v653;
            if ( v587 < v590 )
            {
              v316 = v651;
            }
            else
            {
              v591 = v655;
              v592 = v587 + v580;
              v593 = -v580;
              do
              {
                v594 = v593 + v592;
                _BitScanReverse((unsigned int *)&v595, v584 + 1);
                v13 = *(_DWORD *)(v591 + 80) == 1;
                v596 = v593 + v592 - 3;
                LODWORD(v652) = 0;
                if ( v13 )
                {
                  LODWORD(v649) = 0;
                  _BitScanReverse(&v597, v596 + 1);
                  v598 = v644 + ((v597 + (_DWORD)v595 + 16) << 8);
                }
                else
                {
                  LODWORD(v643) = 0;
                  _BitScanReverse(&v599, *(_DWORD *)(*(_QWORD *)(v591 + 24) + 4 * v595) + 1);
                  v600 = *(_DWORD *)(v591 + 76) + (((_DWORD)v595 - v599) << 8);
                  if ( (unsigned int)v595 >= 0x14 )
                    v600 = ((_DWORD)v595 << 9) + v600 - 9728;
                  if ( (unsigned int)v596 <= 0x7F )
                  {
                    _mm_lfence();
                    v602 = *((unsigned __int8 *)&qword_1803EF770[8] + v596);
                  }
                  else
                  {
                    _BitScanReverse(&v601, v596);
                    LODWORD(v636) = 0;
                    v602 = v601 + 36;
                  }
                  v603 = 4 * v602;
                  LODWORD(v641) = 0;
                  _BitScanReverse((unsigned int *)&v602, *(_DWORD *)(*(_QWORD *)(v591 + 16) + 4 * v602) + 1);
                  v604 = *(_DWORD *)((char *)&qword_1803EF640[10] + v603);
                  LODWORD(v603) = v600 + 51;
                  v588 = v662;
                  v598 = v644 + *(_DWORD *)(v591 + 72) + ((v604 - (_DWORD)v602) << 8) + v603;
                }
                v316 = v651;
                if ( v592 > v321 )
                  goto LABEL_760;
                if ( v598 >= v651[7 * v592] )
                  break;
                if ( v321 < v592 )
                {
LABEL_760:
                  do
                    v316[7 * ++v321] = 0x40000000;
                  while ( v321 < v592 );
                }
                v605 = v592--;
                v606 = 7 * v605;
                v316[v606 + 3] = v642;
                *(_QWORD *)&v316[v606 + 4] = v589;
                v316[v606 + 2] = v594;
                v316[v606 + 1] = v584;
                v316[v606] = v598;
                v316[v606 + 6] = v588;
              }
              while ( v593 + v592 >= v590 );
              v582 = v640;
              v586 = v648;
              v580 = v639;
            }
            v579 = v645;
            ++v582;
            v583 = v586 + 2;
            v640 = v582;
            v648 = v583;
          }
          while ( v582 < v689 );
LABEL_720:
          v319 = v655;
LABEL_721:
          v320 = v639 + 1;
          v639 = v320;
          if ( v320 > v321 )
            goto LABEL_722;
          continue;
        }
        break;
      }
      v275 = 0;
      v273 = v651;
      DWORD1(v667) = v645[2 * v689 - 2];
      v612 = 7LL * v639;
      *((_QWORD *)&v667 + 1) = __PAIR64__(v642, v581);
      if ( v651[v612 + 2] )
      {
        v276 = 0;
        if ( v639 <= 0x1000 )
          v276 = v639;
      }
      else
      {
        v276 = 0;
        if ( v639 - v651[v612 + 3] <= 0x1000 )
          v276 = v639 - v651[v612 + 3];
      }
LABEL_331:
      v277 = v276 + 1;
      v278 = v276 + 1;
      v279 = 7LL * (v276 + 1);
      v280 = v661;
      *(_OWORD *)&v273[v279] = v667;
      *(_QWORD *)&v273[v279 + 4] = v15;
      v273[v279 + 6] = v280;
      while ( v276 )
      {
        v281 = &v273[7 * v276];
        v282 = *(_OWORD *)v281;
        v673 = v281[6];
        v283 = *((_QWORD *)v281 + 2);
        v671 = v282;
        v672 = v283;
        *(double *)&v282 = ZSTD_totalLen(&v671);
        v284 = 7LL * --v278;
        *(_OWORD *)&v273[v284] = v282;
        *(_QWORD *)&v273[v284 + 4] = *(_QWORD *)(v285 + 16);
        v273[v284 + 6] = *(_DWORD *)(v285 + 24);
        v286 = v276;
        v276 -= v287;
        if ( v286 <= v287 )
          v276 = v275;
      }
      v288 = v655;
      if ( v278 <= v277 )
      {
        v289 = v685;
        while ( 1 )
        {
          v290 = 7LL * v278;
          v291 = v273[v290 + 2];
          v292 = (unsigned int)v273[v290 + 3];
          v293 = v273[v290 + 1];
          v294 = v291 + v292;
          if ( v291 )
            break;
          v646 = v289 + v292;
LABEL_751:
          ++v278;
          v275 = 0;
          if ( v278 > v277 )
            goto LABEL_752;
        }
        if ( v293 >= 3 )
        {
          a3[2] = a3[1];
          a3[1] = *a3;
          *a3 = v293 - 2;
          goto LABEL_739;
        }
        v613 = v275;
        LOBYTE(v613) = (_DWORD)v292 == 0;
        v614 = v293 + v613;
        if ( (_DWORD)v614 )
        {
          if ( (_DWORD)v614 == 3 )
          {
            v615 = *a3 - 1;
            goto LABEL_737;
          }
          v615 = a3[v614];
          if ( (unsigned int)v614 >= 2 )
LABEL_737:
            a3[2] = a3[1];
          a3[1] = *a3;
          *a3 = v615;
        }
LABEL_739:
        ZSTD_updateStats(v288, v292, v685, v293, v291);
        v616 = v291 - 3;
        v618 = v617;
        v619 = *(_QWORD *)(a2 + 24);
        if ( v617 + v685 <= v635 - 32 )
        {
          ZSTD_copy16(v619);
          if ( v618 > 0x10 )
          {
            ZSTD_copy16(*(_QWORD *)(v621 + 24) + 16LL);
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
LABEL_745:
            v620 = v685;
          }
          *(_QWORD *)(v621 + 24) += v618;
          v629 = *(_QWORD *)(v621 + 8);
          if ( v618 > 0xFFFF )
          {
            *(_DWORD *)(v621 + 72) = 1;
            *(_DWORD *)(v621 + 76) = (v629 - *(_QWORD *)v621) >> 3;
          }
          *(_WORD *)(v629 + 4) = v618;
          **(_DWORD **)(v621 + 8) = v293 + 1;
          v630 = *(_QWORD *)(v621 + 8);
          if ( v616 > 0xFFFF )
          {
            *(_DWORD *)(v621 + 72) = 2;
            *(_DWORD *)(v621 + 76) = (v630 - *(_QWORD *)v621) >> 3;
          }
          v273 = v651;
          *(_WORD *)(v630 + 6) = v616;
          *(_QWORD *)(v621 + 8) += 8LL;
          v685 = v294 + v620;
          v289 = v685;
          v646 = v685;
          goto LABEL_751;
        }
        ZSTD_safecopyLiterals(v619);
        v621 = a2;
        goto LABEL_745;
      }
LABEL_752:
      ZSTD_setBasePrices(v288, 0);
      v14 = v646;
LABEL_755:
      v10 = v635;
      v5 = a1;
      v8 = v685;
    }
    while ( v14 < v666 );
  }
  return v10 - v8;
}

```

## disassembly

```asm
0x1802c8c30  mov     [rsp-8+arg_18], r9
0x1802c8c35  mov     [rsp-8+arg_10], r8
0x1802c8c3a  mov     [rsp-8+arg_8], rdx
0x1802c8c3f  mov     [rsp-8+arg_0], rcx
0x1802c8c44  push    rbp
0x1802c8c45  push    rbx
0x1802c8c46  push    rsi
0x1802c8c47  push    rdi
0x1802c8c48  push    r12
0x1802c8c4a  push    r13
0x1802c8c4c  lea     rbp, [rsp-0E8h]
0x1802c8c54  sub     rsp, 1E8h
0x1802c8c5b  mov     r8, [rbp+110h+arg_20]
0x1802c8c62  mov     r12, rcx
0x1802c8c65  add     rcx, 48h ; 'H'
0x1802c8c69  mov     edx, 0FFFh
0x1802c8c6e  mov     rdi, r9
0x1802c8c71  mov     [rbp+110h+var_140], rcx
0x1802c8c75  mov     eax, [r12+0CCh]
0x1802c8c7d  lea     r13, [r9+r8]
0x1802c8c81  mov     ebx, [r12+18h]
0x1802c8c86  lea     rsi, [r13-8]
0x1802c8c8a  add     rbx, [r12+8]
0x1802c8c8f  cmp     eax, edx
0x1802c8c91  mov     [rsp+210h+var_1D0], r13
0x1802c8c96  mov     [rbp+110h+var_F8], rsi
0x1802c8c9a  cmovb   edx, eax
0x1802c8c9d  xor     eax, eax
0x1802c8c9f  cmp     dword ptr [r12+0C8h], 3
0x1802c8ca8  mov     [rbp+110h+var_11C], edx
0x1802c8cab  mov     rdx, rdi
0x1802c8cae  setnz   al
0x1802c8cb1  xor     r9d, r9d
0x1802c8cb4  add     eax, 3
0x1802c8cb7  mov     [rbp+110h+var_148], eax
0x1802c8cba  mov     eax, [r12+24h]
0x1802c8cbf  mov     [rbp+110h+var_120], eax
0x1802c8cc2  mov     rax, [rcx+28h]
0x1802c8cc6  mov     [rbp+110h+var_158], rax
0x1802c8cca  mov     rax, [rcx+20h]
0x1802c8cce  mov     [rbp+110h+var_188], rax
0x1802c8cd2  call    ZSTD_rescaleFreqs
0x1802c8cd7  xor     r9d, r9d
0x1802c8cda  cmp     rdi, rbx
0x1802c8cdd  mov     ecx, r9d
0x1802c8ce0  setz    cl
0x1802c8ce3  add     rcx, rdi
0x1802c8ce6  mov     [rbp+110h+var_180], rcx
0x1802c8cea  cmp     rcx, rsi
0x1802c8ced  jnb     loc_1802CBC53
0x1802c8cf3  mov     eax, [rbp+110h+var_D8]
0x1802c8cf6  movsd   xmm2, [rbp+110h+var_E0]
0x1802c8cfb  mov     [rsp+210h+var_30], r14
0x1802c8d03  mov     [rsp+210h+var_38], r15
0x1802c8d0b  mov     [rbp+110h+var_118], eax
0x1802c8d0e  xchg    ax, ax
0x1802c8d10  mov     ebx, [r12+24h]
0x1802c8d15  mov     eax, ecx
0x1802c8d17  mov     r14, [r12+8]
0x1802c8d1c  sub     eax, edi
0x1802c8d1e  mov     esi, [r12+0C8h]
0x1802c8d26  mov     r15d, r9d
0x1802c8d29  setz    r15b
0x1802c8d2d  mov     [rsp+210h+var_1B0], eax
0x1802c8d31  mov     [rsp+210h+var_1B8], r15d
0x1802c8d36  lea     rax, [r14+rbx]
0x1802c8d3a  cmp     rcx, rax
0x1802c8d3d  jb      loc_1802CBC19
0x1802c8d43  mov     edi, ecx
0x1802c8d45  sub     edi, r14d
0x1802c8d48  cmp     ebx, edi
0x1802c8d4a  jnb     short loc_1802C8D7A
0x1802c8d4c  xor     r15d, r15d
0x1802c8d4f  nop
0x1802c8d50  mov     edx, ebx
0x1802c8d52  mov     r9d, esi
0x1802c8d55  add     rdx, r14
0x1802c8d58  mov     [rsp+210h+var_1F0], r15d
0x1802c8d5d  mov     r8, r13
0x1802c8d60  mov     rcx, r12
0x1802c8d63  call    ZSTD_insertBt1
0x1802c8d68  add     ebx, eax
0x1802c8d6a  cmp     ebx, edi
0x1802c8d6c  jb      short loc_1802C8D50
0x1802c8d6e  mov     r15d, [rsp+210h+var_1B8]
0x1802c8d73  xor     r9d, r9d
0x1802c8d76  mov     rcx, [rbp+110h+var_180]
0x1802c8d7a  mov     r8, [r12+30h]
0x1802c8d7f  mov     [r12+24h], edi
0x1802c8d84  mov     edx, [r12+0C0h]
0x1802c8d8c  cmp     esi, 3
0x1802c8d8f  jz      loc_1802C9A92
0x1802c8d95  mov     r14d, 0FFFh
0x1802c8d9b  mov     ebx, ecx
0x1802c8d9d  cmp     esi, 5
0x1802c8da0  jz      loc_1802C9654
0x1802c8da6  lea     eax, [rsi-6]
0x1802c8da9  cmp     eax, 1
0x1802c8dac  mov     eax, [r12+0CCh]
0x1802c8db4  ja      loc_1802C921C
0x1802c8dba  cmp     eax, r14d
0x1802c8dbd  cmovb   r14d, eax
0x1802c8dc1  mov     rax, [r12+8]
0x1802c8dc6  sub     ebx, eax
0x1802c8dc8  mov     [rsp+210h+var_198], rax
0x1802c8dcd  mov     [rsp+210h+var_1A0], ebx
0x1802c8dd1  call    ZSTD_hash6Ptr
0x1802c8dd6  mov     ecx, [r12+0BCh]
0x1802c8dde  lea     r15, [r8+rax*4]
0x1802c8de2  mov     r8d, [r12+1Ch]
0x1802c8de7  dec     ecx
0x1802c8de9  mov     rdi, [r12+40h]
0x1802c8dee  mov     eax, ebx
0x1802c8df0  mov     r10d, [r15]
0x1802c8df3  mov     edx, 1
0x1802c8df8  mov     r11d, 1
0x1802c8dfe  mov     [rsp+210h+var_1A8], r9
0x1802c8e03  shl     r11d, cl
0x1802c8e06  xor     r9d, r9d
0x1802c8e09  xor     ecx, ecx
0x1802c8e0b  mov     [rbp+110h+var_170], rdi
0x1802c8e0f  dec     r11d
0x1802c8e12  mov     [rsp+210h+var_1C8], r9
0x1802c8e17  sub     eax, r11d
0x1802c8e1a  mov     [rsp+210h+var_1B4], r11d
0x1802c8e1f  cmp     r11d, ebx
0x1802c8e22  cmovb   ecx, eax
0x1802c8e25  mov     eax, ebx
0x1802c8e27  sub     eax, r8d
0x1802c8e2a  mov     [rsp+210h+var_1D8], ecx
0x1802c8e2e  mov     ecx, [r12+0B8h]
0x1802c8e36  shl     edx, cl
0x1802c8e38  mov     ecx, ebx
0x1802c8e3a  sub     ecx, edx
0x1802c8e3c  cmp     eax, edx
0x1802c8e3e  mov     eax, 1
0x1802c8e43  cmovbe  ecx, r8d
0x1802c8e47  cmp     [r12+20h], r9d
0x1802c8e4c  cmovnz  ecx, r8d
0x1802c8e50  test    ecx, ecx
0x1802c8e52  cmovnz  eax, ecx
0x1802c8e55  mov     ecx, [r12+0C4h]
0x1802c8e5d  mov     [rsp+210h+var_1DC], eax
0x1802c8e61  xor     edx, edx
0x1802c8e63  mov     eax, r11d
0x1802c8e66  mov     dword ptr [rbp+110h+arg_20], edx
0x1802c8e6c  and     eax, ebx
0x1802c8e6e  add     eax, eax
0x1802c8e70  lea     r13, [rdi+rax*4]
0x1802c8e74  mov     edi, ebx
0x1802c8e76  lea     rax, [r13+4]
0x1802c8e7a  mov     [rsp+210h+var_1C0], rax
0x1802c8e7f  lea     eax, [rbx+9]
0x1802c8e82  mov     [rsp+210h+var_1E0], eax
0x1802c8e86  mov     eax, 1
0x1802c8e8b  shl     eax, cl
0x1802c8e8d  mov     rcx, [rbp+110h+arg_0]
0x1802c8e94  mov     [rbp+110h+var_190], eax
0x1802c8e97  mov     eax, [rbp+110h+var_148]
0x1802c8e9a  dec     eax
0x1802c8e9c  sub     edi, [rcx+18h]
0x1802c8e9f  mov     r12d, eax
0x1802c8ea2  mov     rcx, [rbp+110h+arg_10]
0x1802c8ea9  mov     [rbp+110h+var_138], rax
0x1802c8ead  mov     eax, [rsp+210h+var_1B8]
0x1802c8eb1  mov     r11d, eax
0x1802c8eb4  lea     esi, [rax+3]
0x1802c8eb7  lea     rbx, [rcx+rax*4]
0x1802c8ebb  nop     dword ptr [rax+rax+00h]
0x1802c8ec0  cmp     r11d, 3
0x1802c8ec4  jnz     short loc_1802C8ECC
0x1802c8ec6  mov     ecx, [rcx]
0x1802c8ec8  dec     ecx
0x1802c8eca  jmp     short loc_1802C8ECE
0x1802c8ecc  mov     ecx, [rbx]
0x1802c8ece  lea     eax, [rcx-1]
0x1802c8ed1  mov     r8d, edx
0x1802c8ed4  cmp     eax, edi
0x1802c8ed6  jnb     loc_1802C8FA5
0x1802c8edc  mov     r9d, ecx
0x1802c8edf  mov     edx, 4
0x1802c8ee4  mov     rcx, [rbp+110h+var_180]
0x1802c8ee8  neg     r9
0x1802c8eeb  call    ZSTD_readMINMATCH
0x1802c8ef0  cmp     eax, [r9+rcx]
0x1802c8ef4  jnz     loc_1802C8F9E
0x1802c8efa  lea     rdx, [rcx+4]
0x1802c8efe  lea     r8, [rcx+4]
0x1802c8f02  mov     rcx, [rsp+210h+var_1D0]
0x1802c8f07  add     r8, r9
0x1802c8f0a  mov     r9, rdx
0x1802c8f0d  lea     rax, [rcx-7]
0x1802c8f11  cmp     rdx, rax
0x1802c8f14  jnb     short loc_1802C8F52
0x1802c8f16  mov     rcx, [rdx]
0x1802c8f19  xor     rcx, [r8]
0x1802c8f1c  jz      short loc_1802C8F27
0x1802c8f1e  call    ZSTD_NbCommonBytes
0x1802c8f23  mov     ecx, eax
0x1802c8f25  jmp     short loc_1802C8F9A
0x1802c8f27  add     rdx, 8
0x1802c8f2b  add     r8, 8
0x1802c8f2f  cmp     rdx, rax
0x1802c8f32  jnb     short loc_1802C8F4D
0x1802c8f34  mov     rcx, [rdx]
0x1802c8f37  xor     rcx, [r8]
0x1802c8f3a  jnz     loc_1802C8FF7
0x1802c8f40  add     rdx, 8
0x1802c8f44  add     r8, 8
0x1802c8f48  cmp     rdx, rax
0x1802c8f4b  jb      short loc_1802C8F34
0x1802c8f4d  mov     rcx, [rsp+210h+var_1D0]
0x1802c8f52  lea     rax, [rcx-3]
0x1802c8f56  cmp     rdx, rax
0x1802c8f59  jnb     short loc_1802C8F6A
0x1802c8f5b  mov     eax, [rdx]
0x1802c8f5d  cmp     [r8], eax
0x1802c8f60  jnz     short loc_1802C8F6A
0x1802c8f62  add     rdx, 4
0x1802c8f66  add     r8, 4
0x1802c8f6a  lea     rax, [rcx-1]
0x1802c8f6e  cmp     rdx, rax
0x1802c8f71  jnb     short loc_1802C8F84
0x1802c8f73  movzx   eax, word ptr [rdx]
0x1802c8f76  cmp     [r8], ax
0x1802c8f7a  jnz     short loc_1802C8F84
0x1802c8f7c  add     rdx, 2
0x1802c8f80  add     r8, 2
0x1802c8f84  cmp     rdx, rcx
0x1802c8f87  jnb     short loc_1802C8F94
0x1802c8f89  movzx   eax, byte ptr [rdx]
0x1802c8f8c  cmp     [r8], al
0x1802c8f8f  jnz     short loc_1802C8F94
0x1802c8f91  inc     rdx
0x1802c8f94  mov     rcx, rdx
0x1802c8f97  sub     rcx, r9
0x1802c8f9a  lea     r8d, [rcx+4]
0x1802c8f9e  mov     r9d, dword ptr [rbp+110h+arg_20]
0x1802c8fa5  mov     edx, r8d
0x1802c8fa8  cmp     rdx, r12
0x1802c8fab  jbe     short loc_1802C9006
0x1802c8fad  mov     rcx, [rbp+110h+var_188]
0x1802c8fb1  mov     r12d, edx
0x1802c8fb4  mov     eax, r9d
0x1802c8fb7  inc     r9d
0x1802c8fba  lea     rcx, [rcx+rax*8]
0x1802c8fbe  mov     eax, r11d
0x1802c8fc1  mov     [rcx+4], r8d
0x1802c8fc5  sub     eax, [rsp+210h+var_1B8]
0x1802c8fc9  mov     [rcx], eax
0x1802c8fcb  mov     rax, [rbp+110h+var_180]
0x1802c8fcf  add     rax, rdx
0x1802c8fd2  mov     dword ptr [rbp+110h+arg_20], r9d
0x1802c8fd9  xor     edx, edx
0x1802c8fdb  cmp     rax, [rsp+210h+var_1D0]
0x1802c8fe0  mov     ecx, edx
0x1802c8fe2  mov     eax, edx
0x1802c8fe4  setz    cl
0x1802c8fe7  cmp     r8d, r14d
0x1802c8fea  setnbe  al
0x1802c8fed  or      ecx, eax
0x1802c8fef  jnz     loc_1802C919B
0x1802c8ff5  jmp     short loc_1802C9008
0x1802c8ff7  call    ZSTD_NbCommonBytes
0x1802c8ffc  mov     ecx, eax
0x1802c8ffe  sub     rdx, r9
0x1802c9001  add     rcx, rdx
0x1802c9004  jmp     short loc_1802C8F9A
0x1802c9006  xor     edx, edx
0x1802c9008  mov     rcx, [rbp+110h+arg_10]
0x1802c900f  inc     r11d
0x1802c9012  add     rbx, 4
0x1802c9016  cmp     r11d, esi
0x1802c9019  jb      loc_1802C8EC0
0x1802c901f  mov     esi, [rbp+110h+var_190]
0x1802c9022  mov     eax, [rsp+210h+var_1A0]
0x1802c9026  mov     [r15], eax
0x1802c9029  test    esi, esi
0x1802c902b  jz      loc_1802C917F
0x1802c9031  dec     esi
0x1802c9033  cmp     r10d, [rsp+210h+var_1DC]
0x1802c9038  jb      loc_1802C917F
0x1802c903e  mov     eax, [rsp+210h+var_1B4]
0x1802c9042  mov     r15, [rsp+210h+var_1C8]
0x1802c9047  and     eax, r10d
0x1802c904a  mov     rcx, [rbp+110h+var_170]
0x1802c904e  add     eax, eax
0x1802c9050  cmp     [rsp+210h+var_1A8], r15
0x1802c9055  mov     r9, r15
0x1802c9058  mov     r15, [rbp+110h+var_180]
0x1802c905c  cmovb   r9, [rsp+210h+var_1A8]
0x1802c9062  mov     r14, [rsp+210h+var_1D0]
0x1802c9067  lea     rdi, [rcx+rax*4]
0x1802c906b  mov     r11d, r10d
0x1802c906e  add     r11, [rsp+210h+var_198]
0x1802c9073  lea     rdx, [r9+r15]
0x1802c9077  lea     rax, [r14-7]
0x1802c907b  mov     rbx, rdx
0x1802c907e  lea     r8, [r11+r9]
0x1802c9082  cmp     rdx, rax
  ... truncated ...
```
