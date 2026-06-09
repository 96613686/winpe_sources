# sqlite3VdbeExec

- ea: `0x18002a050`
- end: `0x18003027c`
- name: `sqlite3VdbeExec`
- size: `25132`
- prototype: ``
- caller_count: `2`
- callee_count: `154`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180029bd0`
- `0x18006a2a0`

## callees

- `0x18000126c`
- `0x180004c04`
- `0x180005810`
- `0x180005b90`
- `0x180007dd8`
- `0x180009ed0`
- `0x18000a3e4`
- `0x18000a9e0`
- `0x18000aac0`
- `0x18000ab50`
- `0x18000ab78`
- `0x18000ad30`
- `0x18000f720`
- `0x180010390`
- `0x1800121c0`
- `0x180014360`
- `0x1800143f0`
- `0x180015248`
- `0x18001cea8`
- `0x18001d2b4`
- `0x18001eccc`
- `0x18001ed0c`
- `0x18001ff04`
- `0x1800200b0`
- `0x1800201c0`
- `0x1800203f0`
- `0x180020a94`
- `0x180020d40`
- `0x180020d70`
- `0x180020d90`
- `0x180022288`
- `0x180023884`
- `0x180023a00`
- `0x180024190`
- `0x1800241ec`
- `0x180024eb4`
- `0x1800256c4`
- `0x180025ff0`
- `0x1800275f0`
- `0x180027b20`
- `0x180027f58`
- `0x1800280fc`
- `0x180028540`
- `0x180028df4`
- `0x1800293e0`
- `0x18002a050`
- `0x18003fe98`
- `0x180043834`
- `0x180046938`
- `0x18004788c`

## string_xrefs

- `0x18002faf8`: `cannot open savepoint - SQL statements in progress`
- `0x18002fb01`: `cannot commit transaction - SQL statements in progress`
- `0x18002fd67`: `cannot rollback - no transaction is active`
- `0x18002fd6e`: `cannot commit - no transaction is active`

## pseudocode

```c
__int64 __fastcall sqlite3VdbeExec(unsigned __int64 *a1)
{
  __int128 v1; // xmm0
  unsigned __int8 *v2; // r10
  __int64 *v3; // r15
  unsigned __int64 v4; // rsi
  unsigned __int8 *v5; // rdi
  __int64 v6; // r12
  unsigned __int64 v7; // r13
  __int64 v8; // rdx
  int v9; // eax
  signed __int64 IsValidNN; // rax
  unsigned int updated; // r14d
  int v12; // r11d
  __int64 v13; // rbx
  unsigned __int64 v14; // r8
  unsigned __int64 v15; // rsi
  unsigned __int64 v16; // r9
  signed __int64 v17; // kr00_8
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rbx
  __int64 v21; // rdx
  __int64 v22; // rax
  unsigned int v23; // r13d
  __int64 v24; // rbx
  _DWORD *v25; // r12
  int v26; // eax
  unsigned __int16 *v27; // rsi
  __int64 v28; // rdx
  __int64 v29; // rsi
  const void *v30; // r14
  __int64 v31; // rbx
  unsigned int v32; // eax
  unsigned __int64 i; // r14
  __int64 v34; // rbx
  __int64 v35; // rsi
  _BYTE *v36; // rbx
  __int64 ii; // rsi
  size_t v38; // rbx
  __int64 v39; // rdx
  int *v40; // r15
  __int64 v41; // rdx
  __int64 v42; // r14
  __int64 v43; // rcx
  unsigned __int8 *v44; // rsi
  unsigned __int64 v45; // r12
  unsigned __int64 v46; // r13
  __int64 v47; // rax
  int v48; // esi
  bool v49; // zf
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 v53; // r13
  BOOL v54; // r12d
  __int64 v55; // rsi
  __int16 v56; // r15
  __int64 v57; // r14
  __int16 v58; // ax
  int v59; // eax
  __int64 v60; // rcx
  __int64 v61; // r12
  __int16 v62; // r14
  __int64 v63; // r15
  __int16 v64; // si
  __int64 v65; // rcx
  unsigned __int8 *v66; // rbx
  __int64 v67; // r13
  int v68; // r14d
  int v69; // r12d
  int *v70; // r15
  __int64 v71; // rax
  int *v72; // rax
  int *v73; // rbx
  __int64 v74; // r8
  unsigned __int64 v75; // rcx
  unsigned __int64 v76; // rdx
  int v77; // edx
  __int64 v78; // rax
  __int64 v79; // rcx
  __int64 v80; // rsi
  int v81; // r12d
  __int64 v82; // r14
  __int64 v83; // r13
  _BYTE *v84; // rsi
  _BYTE *v85; // r14
  _BYTE *v86; // rbx
  signed __int64 v87; // rsi
  __int64 v88; // rdx
  unsigned __int64 v89; // rcx
  __int64 v90; // rdx
  _DWORD *v91; // r14
  unsigned __int8 *Payload; // rcx
  int v93; // eax
  unsigned int v94; // eax
  int Varint32; // eax
  signed __int64 *v96; // rcx
  __int64 v97; // rax
  __int64 v98; // rsi
  _QWORD *v99; // rbx
  __int64 v100; // rcx
  __int64 *v101; // r10
  __int64 v102; // rax
  __int64 v103; // r9
  int v104; // r12d
  __int64 v105; // rcx
  __int64 v106; // r14
  __int64 *v107; // r10
  __int64 v108; // rax
  __int64 v109; // r13
  int v110; // r15d
  unsigned __int8 v111; // al
  __int64 v112; // rbx
  __int64 v113; // r8
  __int64 Cursor; // rax
  __int64 v115; // rsi
  __int64 v116; // rcx
  unsigned int v117; // eax
  char v118; // al
  int m; // ecx
  __int64 v120; // rax
  unsigned int v121; // r14d
  unsigned int v122; // esi
  int HasHint; // eax
  int v124; // esi
  char v125; // cl
  __int64 v126; // rax
  unsigned int v127; // eax
  __int64 v128; // rax
  __int64 v129; // rcx
  __int64 v130; // rsi
  __int64 v131; // rbx
  __int16 v132; // r8
  __int64 v133; // rcx
  __int64 v134; // r9
  __int64 v135; // rbx
  unsigned __int64 v136; // rax
  __int64 v137; // rcx
  unsigned __int64 v138; // rdx
  unsigned __int64 v139; // r8
  __int64 v140; // rcx
  __int64 v141; // rax
  __int64 v142; // rdx
  __int64 v143; // rcx
  __int64 v144; // rbx
  __int64 v145; // rdx
  int v146; // ebx
  int v147; // ecx
  int v148; // ebx
  __int64 v149; // rcx
  __int64 v150; // rcx
  __int64 v151; // rsi
  __int64 v152; // rbx
  __int64 v153; // rcx
  unsigned int v154; // eax
  __int64 v155; // rcx
  __int64 v156; // rdx
  signed __int64 v157; // rsi
  __int64 v158; // rcx
  __int64 v159; // rbx
  __int64 v160; // rdx
  __int64 v161; // r14
  __int64 v162; // rsi
  __int64 v163; // rbx
  char v164; // al
  unsigned __int8 v165; // cl
  char v166; // cl
  signed __int64 v167; // rbx
  char v168; // r12
  unsigned __int64 v169; // rdx
  __int64 v171; // rsi
  __int64 v172; // rbx
  __int64 v173; // rdx
  __int64 v174; // rcx
  __int64 v175; // r8
  unsigned int v176; // ecx
  int v177; // r8d
  __int64 v178; // rcx
  __int64 v179; // r8
  __int128 v180; // xmm1
  __int64 v181; // rcx
  __int64 v182; // rax
  __int64 v183; // rsi
  __int64 v184; // rcx
  int *v185; // r14
  unsigned int v186; // r12d
  int v187; // ecx
  __int16 v188; // r14
  int v189; // esi
  signed __int64 v190; // rbx
  __int64 v191; // rdx
  char v192; // al
  __int64 v193; // rbx
  __int64 v194; // rsi
  __int64 v195; // rdx
  const char *v196; // rax
  __int64 v197; // rcx
  int v198; // ecx
  __int64 v199; // r13
  signed __int64 v200; // r8
  int v201; // esi
  int v202; // r9d
  int v203; // ecx
  int v204; // r12d
  int v205; // edx
  __int64 v206; // rax
  __int64 v207; // r8
  __int64 v208; // r15
  __int64 v209; // rbx
  int v210; // r11d
  int v211; // esi
  __int64 v212; // r14
  __int64 v213; // rbx
  __int64 v214; // rcx
  __int64 v215; // rax
  __int64 v216; // rbx
  unsigned int v217; // eax
  __int64 v218; // rbx
  _DWORD *v219; // rbx
  __int64 v220; // r8
  _DWORD *v221; // r8
  __int64 v222; // rax
  __int64 v223; // rdx
  __int64 v224; // rdx
  const char *v225; // rax
  __int64 v226; // rax
  __int64 v227; // rcx
  __int64 v228; // rax
  __int64 v229; // rdx
  __int64 v230; // rbx
  __int64 v231; // rax
  __int64 v232; // r15
  __int64 v233; // rcx
  int v234; // ecx
  __int64 v235; // rcx
  __int64 v236; // rsi
  __int64 v237; // r14
  __int64 v238; // rbx
  __int64 v239; // rax
  unsigned __int8 v240; // cl
  __int64 v241; // rdx
  __int64 v242; // rcx
  __int64 v243; // rax
  __int64 v244; // rsi
  __int64 v245; // r14
  __int64 v246; // rax
  __int64 v247; // rbx
  __int64 v248; // rdx
  __int64 v249; // rsi
  __int64 v250; // rbx
  signed __int64 *v251; // r15
  __int64 *v252; // r12
  __int64 v253; // r13
  __int64 v254; // rbx
  __int64 v255; // rax
  __int64 v256; // rcx
  void *v257; // rcx
  signed __int64 v258; // rcx
  int v259; // eax
  unsigned __int8 v260; // cl
  __int64 v261; // rbx
  __int64 v262; // rax
  __int64 *v263; // r14
  __int64 v264; // rsi
  __int64 v265; // rax
  int v266; // esi
  int v267; // ecx
  char v268; // al
  int v269; // r14d
  __int64 v270; // rsi
  __int64 v271; // rbx
  unsigned __int8 v272; // al
  __int64 *v273; // rsi
  __int64 v274; // rcx
  __int64 v275; // rax
  _QWORD *v276; // rsi
  __int64 v277; // rbx
  __int64 v278; // rax
  __int64 v279; // rdx
  __int64 v280; // rdx
  __int64 v281; // rax
  __int64 v282; // rax
  signed __int64 v283; // rdx
  __int64 v284; // rax
  __int64 v285; // rdx
  __int64 v286; // rbx
  __int64 v287; // rcx
  __int64 v288; // rax
  __int64 v289; // rbx
  __int64 v290; // rcx
  int v291; // r12d
  __int64 v292; // rsi
  __int64 v293; // r15
  __int64 v294; // r14
  __int64 v295; // rdx
  __int64 v296; // rbx
  __int64 v297; // rbx
  __int64 v298; // rdx
  __int64 v299; // r8
  int v300; // eax
  __int64 v301; // r9
  unsigned __int8 v302; // si
  signed __int64 v303; // r8
  __int64 v304; // rcx
  __int64 v305; // rcx
  __int64 v306; // r10
  __int64 v307; // rax
  __int64 v308; // rbx
  __int64 v309; // rdx
  _QWORD *v310; // rsi
  __int64 v311; // r14
  __int16 v312; // r8
  __int64 v313; // r9
  __int64 v314; // rdx
  int v315; // r8d
  __int64 v316; // rdx
  int v317; // ecx
  __int64 v318; // rcx
  __int64 v319; // rax
  __int64 v320; // rcx
  __int64 *v321; // rax
  __int64 v322; // rax
  __int64 v323; // rbx
  __int64 v324; // rcx
  __int64 v325; // rax
  __int64 v326; // rdx
  __int64 v327; // rcx
  int v328; // eax
  __int64 v329; // rax
  __int64 v330; // rcx
  __int64 v331; // rax
  __int64 v332; // rbx
  int v333; // esi
  __int64 v334; // rax
  bool v335; // sf
  __int64 v336; // rcx
  unsigned int v337; // eax
  __int64 v338; // rsi
  __int64 v339; // r15
  __int64 v340; // r14
  __int16 v341; // r8
  __int64 v342; // r15
  __int16 v343; // dx
  int v344; // edx
  __int64 v345; // r8
  __int64 v346; // rcx
  __int64 v347; // rbx
  char v348; // si
  int v349; // r14d
  const char *v350; // r8
  __int64 v351; // rax
  __int64 v352; // rcx
  __int64 v353; // rbx
  unsigned __int64 v354; // rdx
  int v355; // r8d
  int v356; // edx
  int v357; // esi
  int v358; // r14d
  __int64 v359; // rdx
  __int64 v360; // rcx
  __int64 v361; // rdx
  __int64 v362; // rcx
  _QWORD *v363; // rdx
  __int64 v364; // rdx
  __int64 v365; // rcx
  __int64 v366; // r13
  __int64 v367; // rbx
  __int64 v368; // r14
  __int16 v369; // r12
  __int16 v370; // si
  unsigned __int64 v371; // r15
  unsigned __int8 v372; // bl
  int v373; // edx
  int v374; // edx
  double v375; // xmm7_8
  __int128 v376; // xmm6
  __int64 v377; // rbx
  __int64 v378; // rax
  double v379; // xmm6_8
  __int64 v380; // rbx
  __int64 v381; // rbx
  __int64 v382; // r8
  __int64 v383; // rbx
  double v384; // xmm0_8
  __int64 v385; // rbx
  int v386; // ebx
  int v387; // ebx
  __int64 *v388; // rax
  __int64 v389; // r8
  __int64 v390; // rdx
  __int16 v391; // cx
  __int16 v392; // cx
  int v393; // eax
  __int64 v394; // rbx
  int v395; // eax
  __int64 v396; // rsi
  __int64 v397; // rbx
  __int64 v398; // r8
  unsigned __int64 v399; // rcx
  unsigned int v400; // edx
  int v401; // eax
  __int64 v402; // rax
  __int64 v403; // rdx
  __int64 v404; // rcx
  __int64 v405; // rcx
  int v406; // ecx
  __int64 v407; // rdx
  __int64 v408; // rsi
  __int64 v409; // r14
  __int64 v410; // rbx
  int v411; // r15d
  __int64 v412; // r12
  __int16 v413; // ax
  __int16 v414; // cx
  __int64 v415; // rax
  __int16 v416; // cx
  __int16 v417; // cx
  __int16 v418; // cx
  __int16 v419; // ax
  __int64 v420; // rax
  int v421; // eax
  unsigned __int64 v422; // rcx
  unsigned __int64 v423; // rcx
  unsigned int v424; // r12d
  const void *v425; // r14
  __int64 v426; // rsi
  _QWORD *v427; // rbx
  __int64 v428; // rax
  _QWORD *v429; // r15
  unsigned int v430; // esi
  int v431; // r13d
  __int64 *v432; // rbx
  int v433; // r14d
  int v434; // ebx
  int k; // esi
  int v436; // esi
  unsigned int v437; // r14d
  _QWORD *j; // rcx
  __int64 v439; // rcx
  __int64 v440; // rdx
  __int64 v441; // rax
  __int64 v442; // rsi
  __int64 v443; // rbx
  __int64 v444; // rbx
  __int64 v445; // rbx
  __int64 v446; // rax
  int v447; // ecx
  __int64 v448; // rax
  __int64 v449; // rdx
  __int64 v450; // rcx
  int v451; // eax
  unsigned int v452; // eax
  __int64 v453; // rax
  __int64 v454; // rbx
  int n; // edx
  __int64 v456; // rdx
  __int64 v457; // rbx
  __int64 v458; // rax
  __int64 v459; // rcx
  __int64 v460; // rbx
  __int64 v461; // rax
  __int64 v462; // rcx
  __int64 v463; // rax
  int v464; // ebx
  __int64 v465; // rax
  __int64 v466; // r8
  __int64 v467; // rbx
  __int64 v468; // rcx
  __int64 v469; // r8
  __int64 v470; // rdx
  __int64 v471; // rax
  __int64 v472; // rsi
  __int64 v473; // rbx
  __int64 v474; // rdx
  __int64 *v475; // rcx
  __int64 v476; // rbx
  __int64 v477; // rcx
  const char *v478; // r8
  __int64 v479; // rdx
  __int64 v480; // rcx
  __int64 v481; // rcx
  __int64 v482; // rbx
  unsigned int v483; // esi
  __int64 v484; // rcx
  __int64 v485; // rdx
  __int64 v486; // rcx
  __int64 v487; // rdx
  __int64 v488; // rax
  signed __int64 v489; // rdx
  __int64 v490; // rcx
  __int64 v491; // rax
  __int64 v492; // rcx
  _QWORD *v493; // rbx
  __int64 v494; // r8
  __int64 v495; // r9
  __int64 v496; // r9
  __int64 v497; // rbx
  __int64 v498; // r8
  __int64 v499; // rbx
  __int64 v500; // rdx
  __int64 v501; // r8
  __int64 v502; // rsi
  int v503; // eax
  __int64 v504; // rdx
  int v505; // r9d
  __int64 v506; // rbx
  __int64 v507; // r9
  __int64 v508; // rax
  __int64 v509; // rsi
  __int64 v510; // rbx
  __int64 v511; // r14
  int v512; // esi
  __int64 v513; // rbx
  __int64 v514; // r14
  bool v515; // sf
  __int64 v516; // rax
  __int64 v517; // rcx
  __int64 v518; // rsi
  __int64 v519; // rbx
  __int64 v520; // r14
  __int64 v521; // rbx
  _QWORD *v522; // rsi
  __int64 v523; // rdx
  __int64 v524; // rcx
  __int64 v525; // rbx
  __int64 v526; // rax
  __int64 v527; // rcx
  __int64 v528; // rdx
  int v529; // r8d
  int v530; // edx
  unsigned int v531; // eax
  int v532; // edx
  __int64 v533; // rbx
  __int64 v534; // r15
  __int64 v535; // r13
  __int64 v536; // r14
  unsigned int v537; // esi
  unsigned int v538; // ebx
  __int64 v539; // rax
  __int64 v540; // rdx
  __int64 v541; // r8
  unsigned int v542; // eax
  unsigned int v543; // eax
  __int64 v544; // rax
  __int64 v545; // rdx
  __int64 v546; // r8
  __int64 v547; // rax
  __int64 v548; // r9
  __int64 v549; // r8
  __int64 v550; // rbx
  __int64 v551; // rax
  unsigned int v552; // eax
  __int64 v553; // rdx
  __int64 v554; // rax
  __int64 v555; // rax
  __int64 *v556; // rbx
  __int64 v557; // rsi
  __int64 v558; // r9
  __int64 v559; // rsi
  _QWORD *v560; // rax
  _QWORD *v561; // rbx
  __int64 v562; // rax
  int v563; // r13d
  __int64 v564; // rdx
  __int64 v565; // r15
  __int64 v566; // r10
  __int64 v567; // rdx
  int *v568; // r10
  __int64 *v569; // r12
  __int64 **v570; // rbx
  int v571; // r9d
  __int64 v572; // r11
  __int64 *v573; // r14
  __int64 v574; // rsi
  __int64 v575; // rax
  __int64 v576; // rsi
  __int64 *v577; // r14
  __int64 v578; // r15
  __int16 v579; // ax
  unsigned int v580; // eax
  __int64 v581; // rdx
  const char *v582; // rax
  __int64 v583; // rsi
  __int64 **v584; // rcx
  __int64 *v585; // rbx
  __int64 v586; // r14
  int v587; // eax
  int v588; // r14d
  __int64 v589; // rbx
  __int64 v590; // rsi
  __int64 *v591; // rbx
  __int64 v592; // r10
  __int64 v593; // r9
  __int64 v594; // rdx
  char v595; // si
  __int64 v596; // r8
  __int64 v597; // rcx
  __int16 v598; // ax
  _QWORD *v599; // rbx
  unsigned int v600; // r8d
  __int64 v601; // r9
  __int64 v602; // rdx
  __int64 v603; // rdx
  __int64 v604; // rdx
  __int64 v605; // rcx
  const char *v606; // r9
  __int64 v607; // rbx
  __int64 v608; // rbx
  int v609; // eax
  int v610; // eax
  __int64 v611; // rax
  const char *v612; // r8
  __int64 v613; // r8
  const char *v614; // r8
  const char *v615; // rdx
  unsigned int v616; // eax
  const char *v617; // rax
  unsigned int (__fastcall *v618)(__int64, unsigned __int64, unsigned __int64, unsigned __int64); // rax
  __int64 v619; // rcx
  __int64 v620; // [rsp+28h] [rbp-E0h]
  __int64 v621; // [rsp+28h] [rbp-E0h]
  char v622; // [rsp+48h] [rbp-C0h]
  unsigned int Table; // [rsp+4Ch] [rbp-BCh]
  unsigned __int8 v624; // [rsp+50h] [rbp-B8h]
  signed __int64 v625; // [rsp+58h] [rbp-B0h]
  __int64 *v626; // [rsp+60h] [rbp-A8h] BYREF
  unsigned __int64 v627; // [rsp+68h] [rbp-A0h]
  __int64 v628; // [rsp+70h] [rbp-98h] BYREF
  __int64 *v629; // [rsp+78h] [rbp-90h]
  unsigned int v630; // [rsp+80h] [rbp-88h] BYREF
  int v631; // [rsp+84h] [rbp-84h]
  signed __int64 v632; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int64 v633; // [rsp+90h] [rbp-78h]
  __int64 v634; // [rsp+98h] [rbp-70h]
  __int128 v635; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v636; // [rsp+B0h] [rbp-58h]
  __int128 v637; // [rsp+C0h] [rbp-48h]
  int v638; // [rsp+D0h] [rbp-38h]
  __int64 v639; // [rsp+D8h] [rbp-30h]
  unsigned int v640; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v641; // [rsp+E8h] [rbp-20h] BYREF
  unsigned __int64 v642; // [rsp+F0h] [rbp-18h]
  _OWORD v643[2]; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v644; // [rsp+118h] [rbp+10h]
  __int64 v645; // [rsp+128h] [rbp+20h]
  __int128 v646; // [rsp+130h] [rbp+28h] BYREF
  __int128 v647; // [rsp+140h] [rbp+38h]
  __int128 v648; // [rsp+150h] [rbp+48h]
  __int64 v649; // [rsp+160h] [rbp+58h]
  _OWORD v650[2]; // [rsp+168h] [rbp+60h] BYREF
  __int128 v651; // [rsp+188h] [rbp+80h]
  __int64 v652; // [rsp+198h] [rbp+90h]
  char v653; // [rsp+1A8h] [rbp+A0h] BYREF
  __int16 v654; // [rsp+1A9h] [rbp+A1h]
  char v655; // [rsp+1ABh] [rbp+A3h]
  int v656; // [rsp+1ACh] [rbp+A4h]
  int v657; // [rsp+1F8h] [rbp+F0h]
  __int64 v658; // [rsp+1FCh] [rbp+F4h] BYREF

  v2 = (unsigned __int8 *)a1[17];
  v3 = (__int64 *)a1;
  v4 = 0;
  v5 = v2;
  v6 = a1[13];
  v7 = *a1;
  v629 = (__int64 *)a1;
  v625 = (signed __int64)v2;
  v627 = v7;
  v8 = *(unsigned __int8 *)(v7 + 100);
  v624 = *(_BYTE *)(v7 + 100);
  v622 = 0;
  v633 = 0;
  v634 = v6;
  if ( *((_DWORD *)a1 + 52) )
  {
    sqlite3VdbeEnter();
    v8 = v624;
    v2 = v5;
  }
  if ( *(_QWORD *)(v7 + 528) )
  {
    v8 = v624;
    v642 = (unsigned int)(*(_DWORD *)(v7 + 544) - *((_DWORD *)v3 + 57) % *(_DWORD *)(v7 + 544));
  }
  else
  {
    v642 = -1;
  }
  if ( *((_DWORD *)v3 + 13) == 7 )
    goto LABEL_393;
  *((_DWORD *)v3 + 13) = 0;
  v3[9] = 0;
  v9 = *(_DWORD *)(v7 + 408);
  *(_DWORD *)(v7 + 664) = 0;
  if ( v9 )
  {
LABEL_1224:
    updated = 9;
    goto LABEL_260;
  }
  IsValidNN = *((int *)v3 + 12);
  updated = 0;
  v12 = 0;
  Table = 0;
  v631 = 0;
  v638 = 0;
  v5 = &v2[24 * IsValidNN];
  while ( 2 )
  {
    v13 = *v5;
    v14 = 0x180000000uLL;
    v15 = v4 + 1;
    v633 = v15;
    v16 = 0xAAAAAAAAAAAAAAABuLL;
    if ( (_DWORD)v13 == 94 )
    {
      v1 = 0;
      v649 = 0;
      v630 = 0;
      v22 = v3[15];
      v646 = 0;
      v647 = 0;
      v648 = 0;
      v23 = *((_DWORD *)v5 + 2);
      v24 = *(_QWORD *)(v22 + 8LL * *((int *)v5 + 1));
      while ( 1 )
      {
        LODWORD(v626) = v23;
        while ( 1 )
        {
          v25 = *(_DWORD **)(v24 + 88);
          v26 = *((_DWORD *)v3 + 11);
          v628 = (__int64)v25;
          if ( *(_DWORD *)(v24 + 32) != v26 )
            break;
          if ( !(unsigned int)sqlite3BtreeEof(*(_QWORD *)(v24 + 48)) )
          {
            v27 = (unsigned __int16 *)(v24 + 74);
            goto LABEL_21;
          }
LABEL_42:
          Table = sqlite3VdbeHandleMovedCursor(v24);
          updated = Table;
          if ( Table )
            goto LABEL_851;
        }
        if ( *(_BYTE *)(v24 + 2) )
        {
          if ( *(_BYTE *)v24 != 3 || (v325 = *(int *)(v24 + 36), (int)v325 <= 0) )
          {
            v50 = v634 + 56LL * *((int *)v5 + 3);
LABEL_1168:
            IsValidNN = sqlite3VdbeMemSetNull(v50);
            goto LABEL_28;
          }
          v326 = v634;
          v91 = (_DWORD *)(v24 + 108);
          v327 = 56 * v325;
          v328 = *(_DWORD *)(56 * v325 + v634 + 16);
          *(_DWORD *)(v24 + 108) = v328;
          *(_DWORD *)(v24 + 104) = v328;
          Payload = *(unsigned __int8 **)(v327 + v326 + 8);
LABEL_121:
          *(_QWORD *)(v24 + 96) = Payload;
          v93 = *((_DWORD *)v3 + 11);
          v40 = (int *)(v24 + 64);
          *(_DWORD *)(v24 + 32) = v93;
          v94 = *Payload;
          *v25 = v94;
          if ( v94 >= 0x80 )
            Varint32 = (unsigned __int8)sqlite3GetVarint32(*(_QWORD *)(v24 + 96), v25);
          else
            Varint32 = 1;
          v27 = (unsigned __int16 *)(v24 + 74);
          *v40 = Varint32;
          *(_WORD *)(v24 + 74) = 0;
          if ( *v91 >= *v25 )
          {
            v41 = *(_QWORD *)(v24 + 96);
            goto LABEL_125;
          }
          *(_QWORD *)(v24 + 96) = 0;
          *v91 = 0;
          if ( *v25 > 0x18003u || *v25 > *(_DWORD *)(v24 + 104) )
          {
LABEL_1171:
            v167 = v625;
            v610 = *(_DWORD *)(v625 + 12);
            if ( v610 > 0 )
            {
              IsValidNN = 3LL * (v610 - 1);
              v5 = (unsigned __int8 *)(v625 + 8 * IsValidNN);
              goto LABEL_28;
            }
            v616 = sqlite3ReportError(11, 96621, "database corruption");
            v3 = v629;
            updated = v616;
            v7 = v627;
LABEL_261:
            v168 = v622;
            goto LABEL_1232;
          }
LABEL_21:
          if ( *v27 > v23 )
          {
            v28 = *(unsigned int *)(v24 + 4LL * v23 + 120);
            v630 = *(_DWORD *)(v24 + 4LL * v23 + 120);
            goto LABEL_23;
          }
          v40 = (int *)(v24 + 64);
          if ( *(_DWORD *)(v24 + 64) >= *v25 )
          {
            v28 = 0;
            v630 = 0;
            goto LABEL_68;
          }
          v41 = *(_QWORD *)(v24 + 96);
          v639 = v41;
          if ( v41 )
            goto LABEL_53;
          v1 = 0;
          v646 = 0;
          v647 = 0;
          v649 = 0;
          v648 = 0;
          Table = sqlite3VdbeMemFromBtreeZeroOffset(*(_QWORD *)(v24 + 48), (unsigned int)*v25, &v646);
          updated = Table;
          if ( !Table )
          {
            v41 = *((_QWORD *)&v646 + 1);
LABEL_125:
            v639 = v41;
LABEL_53:
            v42 = *v27;
            v43 = v628;
            v44 = (unsigned __int8 *)(v41 + (unsigned int)*v40);
            v45 = (unsigned int)v25[v42];
            v46 = v41 + *(unsigned int *)v628;
            while ( 1 )
            {
              v630 = *v44;
              *(_DWORD *)(v24 + 4LL * (int)v42 + 120) = v630;
              if ( v630 >= 0x80 )
              {
                v44 += (unsigned __int8)sqlite3GetVarint32(v44, &v630);
                *(_DWORD *)(v24 + 4LL * (int)v42 + 120) = v630;
                LODWORD(v47) = sqlite3VdbeSerialTypeLen(v630);
                v43 = v628;
                v47 = (unsigned int)v47;
              }
              else
              {
                ++v44;
                v47 = *((unsigned __int8 *)qword_18009EF00 + (unsigned __int8)v630);
              }
              v45 += v47;
              LODWORD(v42) = v42 + 1;
              *(_DWORD *)(v43 + 4LL * (int)v42) = v45;
              if ( (unsigned int)v42 > (unsigned int)v626 )
                break;
              if ( (unsigned __int64)v44 >= v46 )
                goto LABEL_58;
            }
            if ( (unsigned __int64)v44 >= v46 )
            {
LABEL_58:
              if ( (unsigned __int64)v44 > v46 || v45 != *(_DWORD *)(v24 + 104) )
                goto LABEL_60;
LABEL_64:
              v25 = (_DWORD *)v628;
            }
            else
            {
              if ( v45 <= *(unsigned int *)(v24 + 104) )
                goto LABEL_64;
LABEL_60:
              v25 = (_DWORD *)v628;
              if ( *(_DWORD *)v628 )
              {
                if ( !*(_QWORD *)(v24 + 96) )
                  sqlite3VdbeMemRelease(&v646);
                goto LABEL_1171;
              }
              LOWORD(v42) = 0;
              LODWORD(v44) = v46;
            }
            v48 = (_DWORD)v44 - v639;
            v49 = *(_QWORD *)(v24 + 96) == 0;
            *(_WORD *)(v24 + 74) = v42;
            *(_DWORD *)(v24 + 64) = v48;
            if ( v49 )
              sqlite3VdbeMemRelease(&v646);
            v28 = v630;
            v23 = (unsigned int)v626;
LABEL_68:
            if ( *(unsigned __int16 *)(v24 + 74) <= v23 )
            {
              v50 = v634 + 56LL * *((int *)v5 + 3);
              if ( v5[1] == 0xF6 )
              {
                IsValidNN = sqlite3VdbeMemShallowCopy(v50, *((_QWORD *)v5 + 2), 0x2000);
                goto LABEL_28;
              }
              goto LABEL_1168;
            }
LABEL_23:
            v29 = v634 + 56LL * *((int *)v5 + 3);
            if ( (*(_WORD *)(v29 + 20) & 0x9000) != 0 )
            {
              sqlite3VdbeMemSetNull(v634 + 56LL * *((int *)v5 + 3));
              v28 = v630;
            }
            if ( *(_DWORD *)(v24 + 108) >= v25[v23 + 1] )
            {
              v30 = (const void *)(*(_QWORD *)(v24 + 96) + (unsigned int)v25[v23]);
              if ( (unsigned int)v28 < 0xC )
              {
                IsValidNN = sqlite3VdbeSerialGet(*(_QWORD *)(v24 + 96) + (unsigned int)v25[v23], v28, v29);
                goto LABEL_28;
              }
              v38 = (unsigned int)(v28 - 12) >> 1;
              *(_DWORD *)(v29 + 16) = v38;
              *(_BYTE *)(v29 + 22) = v624;
              v39 = (unsigned int)(v38 + 2);
              if ( *(_DWORD *)(v29 + 32) >= (int)v39 )
              {
                *(_QWORD *)(v29 + 8) = *(_QWORD *)(v29 + 40);
LABEL_50:
                memcpy_0(*(void **)(v29 + 8), v30, v38);
                *(_BYTE *)(v38 + *(_QWORD *)(v29 + 8)) = 0;
                *(_BYTE *)(*(_QWORD *)(v29 + 8) + v38 + 1) = 0;
                IsValidNN = (unsigned __int16)word_1800A7334[v630 & 1];
                *(_WORD *)(v29 + 20) = IsValidNN;
                goto LABEL_28;
              }
              v7 = v627;
              if ( (int)v38 <= *(_DWORD *)(v627 + 136) )
              {
                *(_WORD *)(v29 + 20) = 1;
                if ( !(unsigned int)sqlite3VdbeMemGrow(v29, v39, 0) )
                  goto LABEL_50;
                v3 = v629;
LABEL_393:
                sqlite3OomFault(v7);
                sqlite3VdbeError(v3, "out of memory");
                updated = 7;
                goto LABEL_260;
              }
              v3 = v629;
LABEL_285:
              sqlite3VdbeError(v3, "string or blob too big");
              updated = 18;
              goto LABEL_260;
            }
            *(_BYTE *)(v29 + 22) = v624;
            v191 = v630;
            v192 = v5[2] & 0xC0;
            if ( !v192 || v192 != (char)0x80 && (v630 < 0xC || (v630 & 1) != 0 && v192 != -64) )
            {
              if ( (unsigned int)sqlite3VdbeSerialTypeLen(v630) )
              {
                v3 = v629;
                IsValidNN = vdbeColumnFromOverflow(v24, v23, v630, v25[v23], *((_DWORD *)v629 + 11), v638, v29);
                Table = IsValidNN;
                updated = IsValidNN;
                if ( !(_DWORD)IsValidNN )
                  goto LABEL_28;
                if ( (_DWORD)IsValidNN != 7 )
                {
                  if ( (_DWORD)IsValidNN != 18 )
                    goto LABEL_851;
                  goto LABEL_284;
                }
LABEL_392:
                v7 = v627;
                goto LABEL_393;
              }
              v191 = v630;
            }
            IsValidNN = sqlite3VdbeSerialGet(&qword_18009E630, v191, v29);
            goto LABEL_28;
          }
LABEL_850:
          v3 = v629;
          goto LABEL_851;
        }
        v35 = *(_QWORD *)(v24 + 48);
        if ( !*(_BYTE *)(v24 + 3) )
          break;
        v90 = *(_QWORD *)(v24 + 16);
        if ( !v90 || (v609 = *(_DWORD *)(v90 + 4LL * (v23 + 1))) == 0 )
        {
          Table = sqlite3VdbeFinishMoveto(v24, v90, v14, v16);
          updated = Table;
          if ( !Table )
          {
LABEL_120:
            getCellInfo(v35);
            v91 = (_DWORD *)(v24 + 108);
            *(_DWORD *)(v24 + 104) = *(_DWORD *)(v35 + 64);
            Payload = (unsigned __int8 *)fetchPayload(v35, v24 + 108);
            goto LABEL_121;
          }
LABEL_851:
          v7 = v627;
          goto LABEL_260;
        }
        v24 = *(_QWORD *)(v24 + 40);
        v23 = v609 - 1;
      }
      if ( !(unsigned int)sqlite3BtreeEof(*(_QWORD *)(v24 + 48)) )
        goto LABEL_120;
      goto LABEL_42;
    }
    if ( (_DWORD)v13 == 39 )
    {
      v31 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1));
      v32 = sqlite3BtreeNext(*(_QWORD *)(v31 + 48), *((unsigned int *)v5 + 3));
LABEL_30:
      updated = v32;
      Table = v32;
      *(_DWORD *)(v31 + 32) = 0;
      if ( v32 )
      {
        if ( v32 != 101 )
          goto LABEL_260;
        *(_BYTE *)(v31 + 2) = 1;
        Table = 0;
      }
      else
      {
        *(_BYTE *)(v31 + 2) = 0;
        ++*((_DWORD *)v3 + *((unsigned __int16 *)v5 + 1) + 53);
LABEL_32:
        v5 = (unsigned __int8 *)(v625 + 24LL * (*((_DWORD *)v5 + 2) - 1));
      }
LABEL_33:
      IsValidNN = *(unsigned int *)(v7 + 408);
      if ( !(_DWORD)IsValidNN )
      {
        for ( i = v642; ; v642 = i )
        {
          if ( v15 < i )
            goto LABEL_28;
          IsValidNN = *(_QWORD *)(v7 + 528);
          if ( !IsValidNN )
            goto LABEL_28;
          v34 = *(unsigned int *)(v7 + 544);
          IsValidNN = ((__int64 (__fastcall *)(_QWORD, __int64, unsigned __int64, unsigned __int64))IsValidNN)(
                        *(_QWORD *)(v7 + 536),
                        v8,
                        v14,
                        v16);
          if ( (_DWORD)IsValidNN )
            break;
          i += v34;
        }
        v642 = -1;
      }
      goto LABEL_1224;
    }
    v17 = IsValidNN;
    IsValidNN = (int)v13;
    switch ( (int)v13 )
    {
      case 0:
        v424 = *((_DWORD *)v5 + 1);
        v425 = (const void *)*((_QWORD *)v5 + 2);
        if ( !v424 )
        {
          if ( *(int *)(v7 + 224) <= 0 )
          {
            v426 = (int)sqlite3Strlen30(*((_QWORD *)v5 + 2), v8, 0x180000000uLL);
            Table = sqlite3VtabSavepoint(v7, 0, (unsigned int)(*(_DWORD *)(v7 + 752) + *(_DWORD *)(v7 + 756)));
            if ( !Table )
            {
              IsValidNN = sqlite3DbMallocRawNN(v7, v426 + 33);
              v427 = (_QWORD *)IsValidNN;
              if ( IsValidNN )
              {
                *(_QWORD *)IsValidNN = IsValidNN + 32;
                memcpy_0((void *)(IsValidNN + 32), v425, (int)v426 + 1);
                if ( *(_BYTE *)(v7 + 101) )
                {
                  *(_BYTE *)(v7 + 101) = 0;
                  *(_BYTE *)(v7 + 109) = 1;
                }
                else
                {
                  ++*(_DWORD *)(v7 + 752);
                }
                v427[3] = *(_QWORD *)(v7 + 736);
                v428 = *(_QWORD *)(v7 + 760);
                *(_QWORD *)(v7 + 736) = v427;
                v427[1] = v428;
                IsValidNN = *(_QWORD *)(v7 + 768);
                v427[2] = IsValidNN;
              }
              goto LABEL_815;
            }
LABEL_259:
            updated = Table;
            goto LABEL_260;
          }
          sqlite3VdbeError(v3, "cannot open savepoint - SQL statements in progress");
LABEL_1190:
          updated = 5;
          goto LABEL_260;
        }
        v429 = *(_QWORD **)(v7 + 736);
        v430 = 0;
        LODWORD(v626) = 0;
        if ( !v429 )
        {
LABEL_1193:
          v3 = v629;
          sqlite3VdbeError(v629, "no such savepoint: %s", (const char *)v425);
          updated = 1;
          goto LABEL_260;
        }
        while ( (unsigned int)sqlite3StrICmp(*v429, v425) )
        {
          v429 = (_QWORD *)v429[3];
          if ( !v429 )
            goto LABEL_1193;
          LODWORD(v626) = ++v430;
        }
        if ( *(int *)(v7 + 224) > 0 && v424 == 1 )
        {
          v3 = v629;
          sqlite3VdbeError(v629, "cannot release savepoint - SQL statements in progress");
          goto LABEL_1190;
        }
        if ( v429[3] || !*(_BYTE *)(v7 + 109) )
        {
          v431 = 0;
        }
        else
        {
          v431 = 1;
          if ( v424 == 1 )
          {
            v432 = v629;
            updated = sqlite3VdbeCheckFk(v629, 1);
            if ( updated )
            {
              v7 = v627;
              v3 = v432;
LABEL_418:
              v167 = v625;
LABEL_419:
              v168 = v622;
              goto LABEL_420;
            }
            *(_BYTE *)(v627 + 101) = 1;
            if ( (unsigned int)sqlite3VdbeHalt(v432) == 5 )
            {
              v3 = v629;
              v167 = v625;
              v7 = v627;
              updated = 5;
              *((_DWORD *)v629 + 12) = -1431655765 * ((__int64)&v5[-v625] >> 3);
              *(_BYTE *)(v7 + 101) = 0;
              *((_DWORD *)v3 + 13) = 5;
              goto LABEL_419;
            }
            updated = *((_DWORD *)v432 + 13);
            Table = updated;
            if ( updated )
            {
              v7 = v627;
              v3 = v432;
              *(_BYTE *)(v627 + 101) = 0;
              goto LABEL_260;
            }
            v16 = v627;
            *(_BYTE *)(v627 + 109) = 0;
LABEL_805:
            for ( j = *(_QWORD **)(v16 + 736); j != v429; j = *(_QWORD **)(v16 + 736) )
            {
              *(_QWORD *)(v16 + 736) = j[3];
              sqlite3DbFree(v16, j);
              v16 = v627;
              --*(_DWORD *)(v627 + 752);
            }
            if ( v424 == 1 )
            {
              *(_QWORD *)(v16 + 736) = v429[3];
              IsValidNN = sqlite3DbFree(v16, v429);
              v49 = v431 == 0;
              v7 = v627;
              if ( v49 )
              {
                --*(_DWORD *)(v627 + 752);
                goto LABEL_812;
              }
            }
            else
            {
              v49 = v431 == 0;
              v7 = v627;
              *(_QWORD *)(v16 + 760) = v429[1];
              IsValidNN = v429[2];
              *(_QWORD *)(v16 + 768) = IsValidNN;
              if ( v49 || v424 == 2 )
              {
LABEL_812:
                IsValidNN = sqlite3VtabSavepoint(v7, v424, v430);
                v3 = v629;
                updated = IsValidNN;
                Table = IsValidNN;
                if ( (_DWORD)IsValidNN )
                  goto LABEL_260;
                goto LABEL_815;
              }
            }
            v3 = v629;
LABEL_815:
            if ( *((_BYTE *)v3 + 199) != 3 )
              goto LABEL_28;
            updated = 101;
            goto LABEL_418;
          }
        }
        v16 = v627;
        v433 = *(_DWORD *)(v627 + 752);
        if ( v424 == 2 )
        {
          v434 = *(_DWORD *)(v627 + 44) & 1;
          for ( k = 0; k < *(_DWORD *)(v16 + 40); ++k )
          {
            Table = sqlite3BtreeTripAllCursors(*(_QWORD *)(32LL * k + *(_QWORD *)(v16 + 32) + 8), 516, v434 ^ 1u);
            if ( Table )
            {
LABEL_1231:
              v3 = v629;
              updated = Table;
              v7 = v627;
              goto LABEL_260;
            }
            v16 = v627;
          }
          v430 = (unsigned int)v626;
        }
        else
        {
          v434 = 0;
        }
        LODWORD(v626) = v433 + ~v430;
        v436 = 0;
        v437 = (unsigned int)v626;
        while ( v436 < *(_DWORD *)(v16 + 40) )
        {
          Table = sqlite3BtreeSavepoint(*(_QWORD *)(32LL * v436 + *(_QWORD *)(v16 + 32) + 8), v424, v437);
          if ( Table )
            goto LABEL_1231;
          v16 = v627;
          ++v436;
        }
        if ( v434 )
        {
          sqlite3ExpirePreparedStatements(v16, 0);
          sqlite3ResetAllSchemasOfConnection(v627);
          v16 = v627;
          *(_DWORD *)(v627 + 44) |= 1u;
        }
        updated = Table;
        if ( Table )
          goto LABEL_850;
        v430 = (unsigned int)v626;
        goto LABEL_805;
      case 1:
        v266 = *((_DWORD *)v5 + 1);
        v267 = *((_DWORD *)v5 + 2);
        if ( v266 == *(unsigned __int8 *)(v7 + 101) )
        {
          if ( v266 )
          {
            v615 = "cannot rollback - no transaction is active";
            if ( !v267 )
              v615 = "cannot commit - no transaction is active";
            sqlite3VdbeError(v3, v615, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
          }
          else
          {
            sqlite3VdbeError(
              v3,
              "cannot start a transaction within a transaction",
              0x180000000uLL,
              0xAAAAAAAAAAAAAAABuLL);
          }
          updated = 1;
          goto LABEL_260;
        }
        if ( v267 )
        {
          sqlite3RollbackAll(v7, 516, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
          v268 = 1;
        }
        else
        {
          if ( v266 && *(int *)(v7 + 224) > 0 )
          {
            sqlite3VdbeError(v3, "cannot commit transaction - SQL statements in progress");
            goto LABEL_1190;
          }
          updated = sqlite3VdbeCheckFk(v3, 1);
          if ( updated )
            goto LABEL_418;
          v268 = v266;
        }
        *(_BYTE *)(v7 + 101) = v268;
        if ( (unsigned int)sqlite3VdbeHalt(v3) == 5 )
        {
          v167 = v625;
          updated = 5;
          *((_DWORD *)v3 + 12) = -1431655765 * ((__int64)&v5[-v625] >> 3);
          *(_BYTE *)(v7 + 101) = 1 - v266;
          *((_DWORD *)v3 + 13) = 5;
          goto LABEL_419;
        }
        sqlite3CloseSavepoints(v7);
        updated = 101;
        if ( *((_DWORD *)v3 + 13) )
          updated = 1;
        goto LABEL_418;
      case 2:
        v160 = *((unsigned int *)v5 + 2);
        LODWORD(v626) = 0;
        if ( (_DWORD)v160 )
        {
          IsValidNN = *(_QWORD *)(v7 + 48);
          if ( (IsValidNN & 0x200100000LL) != 0 )
          {
            updated = 8;
            if ( (IsValidNN & 0x100000) == 0 )
              updated = 11;
LABEL_260:
            v167 = v625;
            goto LABEL_261;
          }
        }
        v161 = *(_QWORD *)(v7 + 32);
        v162 = 32LL * *((int *)v5 + 1);
        v163 = *(_QWORD *)(v162 + v161 + 8);
        if ( v163 )
        {
          IsValidNN = sqlite3BtreeBeginTrans(*(_QWORD *)(v162 + v161 + 8), v160, &v626);
          Table = IsValidNN;
          if ( (_DWORD)IsValidNN )
          {
            updated = IsValidNN;
            v167 = v625;
            v168 = v622;
            if ( (_BYTE)IsValidNN != 5 )
              goto LABEL_1232;
            *((_DWORD *)v3 + 13) = IsValidNN;
            *((_DWORD *)v3 + 12) = -1431655765 * ((__int64)&v5[-v625] >> 3);
            goto LABEL_420;
          }
          if ( (v3[25] & 0x20) == 0 || !*((_DWORD *)v5 + 2) || *(_BYTE *)(v7 + 101) && *(int *)(v7 + 220) <= 1 )
            goto LABEL_205;
          v177 = *((_DWORD *)v3 + 16);
          if ( !v177 )
          {
            v177 = ++*(_DWORD *)(v7 + 756) + *(_DWORD *)(v7 + 752);
            *((_DWORD *)v3 + 16) = v177;
          }
          Table = sqlite3VtabSavepoint(v7, 0, (unsigned int)(v177 - 1));
          v176 = Table;
          if ( !Table )
          {
            v176 = sqlite3BtreeBeginStmt(v163, *((unsigned int *)v3 + 16));
            Table = v176;
          }
          v3[11] = *(_QWORD *)(v7 + 760);
          IsValidNN = *(_QWORD *)(v7 + 768);
          v3[12] = IsValidNN;
        }
        else
        {
          v176 = Table;
        }
        if ( v176 )
          goto LABEL_259;
LABEL_205:
        if ( *((_WORD *)v5 + 1) )
        {
          if ( (_DWORD)v626 != *((_DWORD *)v5 + 3)
            || (IsValidNN = *((unsigned int *)v5 + 4),
                *(_DWORD *)(*(_QWORD *)(v162 + v161 + 24) + 4LL) != (_DWORD)IsValidNN) )
          {
            sqlite3DbFree(v7, v3[21]);
            v3[21] = sqlite3DbStrDup(v7, "database schema has changed");
            if ( **(_DWORD **)(32LL * *((int *)v5 + 1) + *(_QWORD *)(v7 + 32) + 24) != (_DWORD)v626 )
              sqlite3ResetOneSchema(v7);
            updated = 17;
            *((_DWORD *)v3 + 50) = v3[25] & 0xFFFFFFEC | 1;
            goto LABEL_260;
          }
        }
        goto LABEL_28;
      case 3:
        v529 = *((_DWORD *)v5 + 2);
        v530 = *((_DWORD *)v5 + 1);
        v657 = 0;
        v658 = -1;
        v531 = sqlite3Checkpoint(v7, v530, v529, (unsigned int)&v658, (__int64)&v658 + 4);
        Table = v531;
        updated = v531;
        if ( v531 )
        {
          if ( v531 != 5 )
            goto LABEL_260;
          v532 = 1;
          Table = 0;
          v657 = 1;
        }
        else
        {
          v532 = v657;
        }
        v533 = v6 + 56LL * *((int *)v5 + 3);
        sqlite3VdbeMemSetInt64(v533, v532);
        sqlite3VdbeMemSetInt64(v533 + 56, (int)v658);
        IsValidNN = sqlite3VdbeMemSetInt64(v533 + 112, SHIDWORD(v658));
        goto LABEL_28;
      case 4:
        v534 = out2Prerelease(v3, v5);
        v535 = *(_QWORD *)(32LL * *((int *)v5 + 1) + *(_QWORD *)(v7 + 32) + 8);
        v536 = **(_QWORD **)(v535 + 8);
        v537 = *(unsigned __int8 *)(v536 + 9);
        v538 = v537;
        if ( *((_DWORD *)v5 + 3) != -1 )
          v538 = *((_DWORD *)v5 + 3);
        if ( !(unsigned int)sqlite3PagerOkToChangeJournalMode(v536) )
          v538 = v537;
        v539 = sqlite3PagerFilename(v536, 1);
        if ( v538 == 5
          && (!(unsigned int)sqlite3Strlen30(v539, v540, v541) || !(unsigned int)sqlite3PagerWalSupported(v536)) )
        {
          v538 = v537;
LABEL_1057:
          v542 = Table;
          goto LABEL_1058;
        }
        if ( v538 == v537 || v537 != 5 && v538 != 5 )
          goto LABEL_1057;
        if ( !*(_BYTE *)(v627 + 101) || *(int *)(v627 + 220) > 1 )
        {
          v3 = v629;
          v614 = "into";
          if ( v538 != 5 )
            v614 = "out of";
          updated = 1;
          sqlite3VdbeError(v629, "cannot change %s wal mode from within a transaction", v614);
          v7 = v627;
          goto LABEL_260;
        }
        if ( v537 == 5 )
        {
          Table = sqlite3PagerCloseWal(v536, v627);
          if ( Table )
            goto LABEL_1059;
          sqlite3PagerSetJournalMode(v536, v538);
        }
        else
        {
          if ( v537 == 4 )
            sqlite3PagerSetJournalMode(v536, 2);
          if ( Table )
            goto LABEL_1059;
        }
        v542 = sqlite3BtreeSetVersion(v535, (unsigned int)(v538 == 5) + 1);
        Table = v542;
LABEL_1058:
        if ( !v542 )
          goto LABEL_1060;
LABEL_1059:
        v538 = v537;
LABEL_1060:
        v543 = sqlite3PagerSetJournalMode(v536, v538);
        *(_WORD *)(v534 + 20) = 8706;
        v544 = sqlite3JournalModename(v543);
        *(_QWORD *)(v534 + 8) = v544;
        *(_DWORD *)(v534 + 16) = sqlite3Strlen30(v544, v545, v546);
        *(_BYTE *)(v534 + 22) = 1;
        IsValidNN = sqlite3VdbeChangeEncoding(v534, v624);
        updated = Table;
        if ( Table )
          goto LABEL_850;
        goto LABEL_28;
      case 5:
        v547 = *((int *)v5 + 2);
        if ( (_DWORD)v547 )
          v548 = v6 + 56 * v547;
        else
          v548 = 0;
        IsValidNN = sqlite3RunVacuum(v3 + 21, v7, *((unsigned int *)v5 + 1), v548);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( !(_DWORD)IsValidNN )
          goto LABEL_28;
        goto LABEL_260;
      case 6:
        v563 = 0;
        v564 = 56LL * *((int *)v5 + 3);
        v565 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1));
        v566 = v564 + 56;
        v567 = *(unsigned int *)(v564 + v6);
        v568 = (int *)(v6 + v566);
        v569 = v629;
        v570 = *(__int64 ***)(v565 + 48);
        v571 = *v568;
        v572 = v629[14];
        v573 = *v570;
        v574 = **v570;
        if ( *v568 > 0 )
        {
          do
          {
            v575 = (unsigned int)v563++;
            *(_QWORD *)(v572 + 8 * v575) = &v568[14 * v563];
          }
          while ( v563 < v571 );
        }
        HIDWORD(v620) = HIDWORD(v572);
        Table = (*(__int64 (__fastcall **)(__int64 **, __int64, _QWORD))(v574 + 64))(v570, v567, *((_QWORD *)v5 + 2));
        sqlite3VtabImportErrmsg(v569, v573);
        updated = Table;
        if ( Table )
        {
          v7 = v627;
          v3 = v569;
          goto LABEL_260;
        }
        IsValidNN = (*(__int64 (__fastcall **)(__int64 **))(v574 + 80))(v570);
        *(_BYTE *)(v565 + 2) = 0;
        if ( (_DWORD)IsValidNN )
          goto LABEL_77;
        goto LABEL_28;
      case 7:
        v49 = *(_BYTE *)(v7 + 103) == 0;
        v632 = 0;
        if ( !v49 )
          goto LABEL_393;
        IsValidNN = *((_QWORD *)v5 + 2);
        v591 = *(__int64 **)(IsValidNN + 16);
        if ( !v591 )
          goto LABEL_1208;
        v592 = *v591;
        if ( !*v591 )
          goto LABEL_1208;
        if ( !*(_QWORD *)(v592 + 104) )
          goto LABEL_28;
        v593 = 0;
        v594 = *((unsigned int *)v5 + 2);
        v595 = *(_BYTE *)(v7 + 108);
        v596 = v3[14];
        v597 = v6 + 56LL * *((int *)v5 + 3);
        if ( (int)v594 > 0 )
        {
          do
          {
            *(_QWORD *)(v596 + 8 * v593) = v597;
            v597 += 56;
            v593 = (unsigned int)(v593 + 1);
          }
          while ( (int)v593 < (int)v594 );
        }
        *(_BYTE *)(v7 + 108) = v5[2];
        Table = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, signed __int64 *))(v592 + 104))(
                  v591,
                  v594,
                  v596,
                  &v632);
        *(_BYTE *)(v7 + 108) = v595;
        updated = Table;
        IsValidNN = sqlite3VtabImportErrmsg(v3, v591);
        if ( Table )
        {
          if ( (_BYTE)Table == 19 )
          {
            IsValidNN = *((_QWORD *)v5 + 2);
            if ( *(_BYTE *)(IsValidNN + 28) )
            {
              v598 = *((_WORD *)v5 + 1);
              if ( v598 == 4 )
              {
                IsValidNN = 0;
                Table = 0;
                goto LABEL_28;
              }
              if ( v598 == 5 )
                LOBYTE(v598) = 2;
              *((_BYTE *)v3 + 196) = v598;
              goto LABEL_260;
            }
          }
        }
        else if ( *((_DWORD *)v5 + 1) )
        {
          IsValidNN = v632;
          *(_QWORD *)(v7 + 56) = v632;
        }
        ++v3[7];
        if ( Table )
          goto LABEL_260;
        goto LABEL_28;
      case 8:
      case 184:
        v118 = *(_BYTE *)(v7 + 110);
        if ( (v118 & 0x41) != 0 && *((_BYTE *)v3 + 197) != 0xFE )
        {
          v606 = (const char *)*((_QWORD *)v5 + 2);
          if ( v606 || (v606 = (const char *)v3[31]) != 0 )
          {
            if ( (v118 & 0x40) != 0 )
            {
              v607 = sqlite3VdbeExpandSql(v3, v606, 0x180000000uLL);
              (*(void (__fastcall **)(_QWORD, __int64))(v7 + 248))(*(_QWORD *)(v7 + 256), v607);
              sqlite3_free(v607);
            }
            else if ( *(int *)(v7 + 228) <= 1 )
            {
              (*(void (__fastcall **)(__int64, _QWORD, __int64 *))(v7 + 248))(1, *(_QWORD *)(v7 + 256), v3);
            }
            else
            {
              v608 = sqlite3MPrintf(v7, "-- %s", v606);
              (*(void (__fastcall **)(__int64, _QWORD, __int64 *, __int64))(v7 + 248))(
                1,
                *(_QWORD *)(v7 + 256),
                v3,
                v608);
              sqlite3DbFree(v7, v608);
            }
          }
        }
        IsValidNN = *((unsigned int *)v5 + 1);
        if ( (int)IsValidNN < dword_1800B57D8 )
          goto LABEL_152;
        if ( *v5 == 0xB8 )
          goto LABEL_28;
        for ( m = 1; m < *((_DWORD *)v3 + 36); ++m )
        {
          v120 = v3[17];
          if ( *(_BYTE *)(v120 + 24LL * m) == 15 )
            *(_DWORD *)(v120 + 24LL * m + 4) = 0;
        }
        LODWORD(IsValidNN) = 0;
LABEL_152:
        *((_DWORD *)v5 + 1) = IsValidNN + 1;
        ++*((_DWORD *)v3 + 59);
        goto LABEL_77;
      case 9:
        goto LABEL_32;
      case 10:
        v227 = 56LL * *((int *)v5 + 1);
        *(_WORD *)(v227 + v6 + 20) = 4;
        *(_QWORD *)(v227 + v6) = (int)(-1431655765 * ((__int64)&v5[-v625] >> 3));
        goto LABEL_32;
      case 11:
        v235 = 56LL * *((int *)v5 + 1);
        IsValidNN = *((_DWORD *)v5 + 3) - 1;
        *(_QWORD *)(v235 + v6) = IsValidNN;
        *(_WORD *)(v235 + v6 + 20) = 4;
        if ( !*((_DWORD *)v5 + 2) )
          goto LABEL_28;
        goto LABEL_77;
      case 12:
        v173 = 56LL * *((int *)v5 + 1);
        v174 = *(int *)(v173 + v6);
        IsValidNN = (int)(-1431655765 * ((__int64)&v5[-v625] >> 3));
        *(_WORD *)(v173 + v6 + 20) = 4;
        *(_QWORD *)(v173 + v6) = IsValidNN;
        v5 = (unsigned __int8 *)(v625 + 24 * v174);
        goto LABEL_28;
      case 13:
        v381 = v6 + 56LL * *((int *)v5 + 1);
        IsValidNN = *(unsigned __int16 *)(v381 + 20);
        if ( (IsValidNN & 4) != 0
          || (v382 = (unsigned __int8)v8,
              LOBYTE(v8) = 67,
              applyAffinity(v6 + 56LL * *((int *)v5 + 1), v8, v382, 0xAAAAAAAAAAAAAAABuLL),
              IsValidNN = *(unsigned __int16 *)(v381 + 20),
              (IsValidNN & 4) != 0) )
        {
          LOWORD(IsValidNN) = IsValidNN & 0xF240 | 4;
          *(_WORD *)(v381 + 20) = IsValidNN;
          goto LABEL_28;
        }
        if ( !*((_DWORD *)v5 + 2) )
        {
          updated = 20;
          goto LABEL_260;
        }
        goto LABEL_77;
      case 14:
        if ( v12 < 0 )
        {
          v59 = *((_DWORD *)v5 + 1);
          goto LABEL_78;
        }
        if ( !v12 )
          goto LABEL_77;
        v59 = *((_DWORD *)v5 + 3);
        goto LABEL_78;
      case 15:
        v175 = v3[33];
        if ( !v175 )
        {
          if ( *(_DWORD *)(v3[17] + 4) == *((_DWORD *)v5 + 1) )
            goto LABEL_77;
          goto LABEL_249;
        }
        v398 = *(_QWORD *)(v175 + 40);
        v399 = (unsigned __int64)(-1431655765 * (unsigned int)((__int64)&v5[-v3[17]] >> 3)) >> 3;
        v400 = (-85 * (unsigned __int8)((__int64)&v5[-v3[17]] >> 3)) & 7;
        v401 = *(unsigned __int8 *)(v399 + v398);
        if ( !_bittest(&v401, v400) )
        {
          *(_BYTE *)(v399 + v398) = v401 | (1 << v400);
LABEL_249:
          IsValidNN = v3[17];
          *((_DWORD *)v5 + 1) = *(_DWORD *)(IsValidNN + 4);
          goto LABEL_28;
        }
        goto LABEL_77;
      case 16:
        IsValidNN = sqlite3VdbeBooleanValue(v6 + 56LL * *((int *)v5 + 1), *((unsigned int *)v5 + 3));
        if ( !(_DWORD)IsValidNN )
          goto LABEL_28;
        goto LABEL_77;
      case 17:
        IsValidNN = sqlite3VdbeBooleanValue(v6 + 56LL * *((int *)v5 + 1), *((_DWORD *)v5 + 3) == 0);
        if ( (_DWORD)IsValidNN )
          goto LABEL_28;
        goto LABEL_77;
      case 18:
        v402 = *((int *)v5 + 1);
        if ( (int)v402 < 0 )
        {
          LOBYTE(v406) = *((_BYTE *)qword_18009EC50 + (*(_WORD *)(56LL * *((int *)v5 + 3) + v6 + 20) & 0x3F));
          goto LABEL_705;
        }
        v403 = *((int *)v5 + 3);
        v404 = *(_QWORD *)(v3[15] + 8 * v402);
        if ( (int)v403 >= *(unsigned __int16 *)(v404 + 74) )
        {
          v406 = *((_DWORD *)v5 + 4);
LABEL_705:
          IsValidNN = 1;
          LOWORD(IsValidNN) = 1 << (v406 - 1);
          goto LABEL_706;
        }
        v405 = *(unsigned int *)(v404 + 4 * v403 + 120);
        if ( (unsigned int)v405 < 0xC )
        {
          IsValidNN = *((unsigned __int8 *)&qword_1800A6560[1] + v405);
        }
        else
        {
          IsValidNN = 4;
          if ( (v405 & 1) == 0 )
            LOWORD(IsValidNN) = 8;
        }
LABEL_706:
        if ( ((unsigned __int16)IsValidNN & *((_WORD *)v5 + 1)) == 0 )
          goto LABEL_28;
        goto LABEL_77;
      case 19:
        v394 = v6 + 56LL * *((int *)v5 + 2);
        if ( (*(_BYTE *)(v6 + 56LL * *((int *)v5 + 1) + 20) & 1) != 0 )
          goto LABEL_1114;
        v395 = sqlite3VdbeBooleanValue(v6 + 56LL * *((int *)v5 + 1), 0);
        IsValidNN = sqlite3VdbeMemSetInt64(v394, v395 == 0);
        goto LABEL_28;
      case 20:
        IsValidNN = v3[15];
        v407 = *(_QWORD *)(IsValidNN + 8LL * *((int *)v5 + 1));
        if ( !v407 || !*(_BYTE *)(v407 + 2) )
          goto LABEL_28;
        sqlite3VdbeMemSetNull(v6 + 56LL * *((int *)v5 + 3));
        goto LABEL_77;
      case 21:
      case 22:
      case 23:
      case 24:
        v51 = *((int *)v5 + 1);
        *(_QWORD *)&v637 = 0;
        v1 = 0;
        v52 = v3[15];
        LODWORD(v626) = 0;
        v635 = 0;
        v636 = 0;
        v53 = *(_QWORD *)(v52 + 8 * v51);
        v49 = *(_BYTE *)(v53 + 4) == 0;
        *(_WORD *)(v53 + 2) = 0;
        *(_DWORD *)(v53 + 32) = 0;
        if ( v49 )
        {
          HasHint = sqlite3BtreeCursorHasHint(*(_QWORD *)(v53 + 48), 2, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
          *(_QWORD *)&v635 = *(_QWORD *)(v53 + 56);
          WORD6(v636) = *((_WORD *)v5 + 8);
          BYTE2(v637) = 0;
          v54 = HasHint != 0;
          v124 = HasHint;
          v125 = 1;
          if ( (((_BYTE)v13 - 1) & 1) != 0 )
            v125 = -1;
          v126 = *((int *)v5 + 3);
          BYTE14(v636) = v125;
          *((_QWORD *)&v635 + 1) = v634 + 56 * v126;
          Table = sqlite3BtreeIndexMoveto(*(_QWORD *)(v53 + 48), &v635, &v626);
          updated = Table;
          if ( Table )
            goto LABEL_851;
          if ( v124 && !BYTE2(v637) )
            goto LABEL_164;
        }
        else
        {
          v54 = 0;
          v55 = v634 + 56LL * *((int *)v5 + 3);
          v56 = *(_WORD *)(v55 + 20);
          if ( (v56 & 0x2E) == 2 )
            applyNumericAffinity(v634 + 56LL * *((int *)v5 + 3), 0, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
          v57 = sqlite3_value_int64(v55);
          v58 = *(_WORD *)(v55 + 20);
          *(_WORD *)(v55 + 20) = v56;
          if ( (v58 & 0x24) == 0 )
          {
            if ( (v58 & 8) == 0 )
            {
              if ( (v58 & 1) != 0 || (unsigned int)v13 >= 0x17 )
                goto LABEL_77;
              Table = sqlite3BtreeLast(*(_QWORD *)(v53 + 48), &v626);
              updated = Table;
              if ( Table )
                goto LABEL_850;
LABEL_164:
              IsValidNN = (unsigned int)v626;
LABEL_165:
              if ( (_DWORD)IsValidNN )
                goto LABEL_77;
LABEL_166:
              if ( v54 )
                v5 += 24;
              goto LABEL_28;
            }
            v451 = sqlite3IntFloatCompare(v57);
            if ( v451 <= 0 )
            {
              if ( v451 < 0 && (v13 & 1) != 0 )
                LODWORD(v13) = v13 + 1;
            }
            else if ( (v13 & 1) == 0 )
            {
              LODWORD(v13) = v13 - 1;
            }
          }
          v452 = sqlite3BtreeTableMoveto(*(_QWORD *)(v53 + 48), v57, 0, &v626);
          v3 = v629;
          *(_QWORD *)(v53 + 80) = v57;
          updated = v452;
          Table = v452;
          if ( v452 )
            goto LABEL_851;
        }
        IsValidNN = (unsigned int)v626;
        if ( (int)v13 < 23 )
        {
          if ( (int)v626 <= 0 && ((_DWORD)v626 || (_DWORD)v13 != 21) )
          {
            IsValidNN = sqlite3BtreeEof(*(_QWORD *)(v53 + 48));
            goto LABEL_165;
          }
          LODWORD(v626) = 0;
          v127 = sqlite3BtreePrevious(*(_QWORD *)(v53 + 48), 0);
        }
        else
        {
          if ( (int)v626 >= 0 && ((_DWORD)v626 || (_DWORD)v13 != 24) )
          {
            LODWORD(v626) = 0;
            goto LABEL_166;
          }
          LODWORD(v626) = 0;
          v127 = sqlite3BtreeNext(*(_QWORD *)(v53 + 48), 0);
        }
        Table = v127;
        updated = v127;
        if ( !v127 )
          goto LABEL_164;
        if ( v127 != 101 )
          goto LABEL_851;
        Table = 0;
LABEL_864:
        LODWORD(v626) = 1;
        goto LABEL_77;
      case 25:
        IsValidNN = v3[15];
        v8 = *(_QWORD *)(IsValidNN + 8LL * *((int *)v5 + 1));
        if ( !v8 || *(_BYTE *)(v8 + 2) )
          goto LABEL_32;
        goto LABEL_28;
      case 26:
        IsValidNN = *(unsigned __int16 *)(*(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1)) + 12LL);
        if ( (int)IsValidNN >= *((_DWORD *)v5 + 4) )
          goto LABEL_28;
        goto LABEL_266;
      case 27:
      case 28:
      case 29:
LABEL_266:
        v181 = *((int *)v5 + 1);
        *(_QWORD *)&v637 = 0;
        v1 = 0;
        v182 = v3[15];
        v635 = 0;
        v636 = 0;
        v183 = *(_QWORD *)(v182 + 8 * v181);
        v184 = v6 + 56LL * *((int *)v5 + 3);
        WORD6(v636) = *((_WORD *)v5 + 8);
        *((_QWORD *)&v635 + 1) = v184;
        if ( WORD6(v636) )
        {
          v185 = (int *)(v183 + 36);
          *(_QWORD *)&v635 = *(_QWORD *)(v183 + 56);
          BYTE14(v636) = 0;
          v186 = sqlite3BtreeIndexMoveto(*(_QWORD *)(v183 + 48), &v635, v183 + 36);
          Table = v186;
        }
        else
        {
          if ( (*(_WORD *)(v184 + 20) & 0x400) != 0 && (unsigned int)sqlite3VdbeMemExpandBlob(v184) )
            goto LABEL_393;
          v453 = sqlite3VdbeAllocUnpackedRecord(*(_QWORD *)(v183 + 56), v8, v14, v16);
          v454 = v453;
          if ( !v453 )
            goto LABEL_393;
          sqlite3VdbeRecordUnpack(
            *(_QWORD *)(v183 + 56),
            *(unsigned int *)(*((_QWORD *)&v635 + 1) + 16LL),
            *(_QWORD *)(*((_QWORD *)&v635 + 1) + 8LL),
            v453);
          *(_BYTE *)(v454 + 30) = 0;
          v185 = (int *)(v183 + 36);
          Table = sqlite3BtreeIndexMoveto(*(_QWORD *)(v183 + 48), v454, v183 + 36);
          v186 = Table;
          sqlite3DbFreeNN(v7, v454);
        }
        if ( v186 )
          goto LABEL_259;
        v187 = *v185;
        *(_BYTE *)(v183 + 3) = 0;
        *(_DWORD *)(v183 + 32) = 0;
        *(_BYTE *)(v183 + 2) = v187 != 0;
        IsValidNN = *v5;
        if ( (_BYTE)IsValidNN == 29 )
        {
          if ( !v187 )
            goto LABEL_77;
        }
        else
        {
          if ( v187 )
            goto LABEL_77;
          if ( (_BYTE)IsValidNN == 27 )
          {
            for ( n = 0; ; ++n )
            {
              IsValidNN = WORD6(v636);
              if ( n >= WORD6(v636) )
                break;
              if ( (*(_BYTE *)(56LL * n + *((_QWORD *)&v635 + 1) + 20) & 1) != 0 )
                goto LABEL_77;
            }
          }
          else if ( (_BYTE)IsValidNN == 26 )
          {
            IsValidNN = *((unsigned __int16 *)v5 + 8);
            *(_WORD *)(v183 + 12) = IsValidNN;
          }
        }
        goto LABEL_28;
      case 30:
        v150 = 56LL * *((int *)v5 + 3);
        v640 = 0;
        if ( (*(_BYTE *)(v150 + v6 + 20) & 0x24) != 0 )
          goto LABEL_188;
        v179 = (unsigned __int8)v8;
        LOBYTE(v8) = 67;
        v180 = *(_OWORD *)(v150 + v6 + 16);
        v643[0] = *(_OWORD *)(v150 + v6);
        v1 = *(_OWORD *)(v150 + v6 + 32);
        v643[1] = v180;
        *(_QWORD *)&v180 = *(_QWORD *)(v150 + v6 + 48);
        v644 = v1;
        v645 = v180;
        applyAffinity(v643, v8, v179, 0xAAAAAAAAAAAAAAABuLL);
        if ( (BYTE4(v643[1]) & 4) == 0 )
          goto LABEL_77;
        v151 = *(_QWORD *)&v643[0];
LABEL_189:
        v152 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1));
        v153 = *(_QWORD *)(v152 + 48);
        v640 = 0;
        v154 = sqlite3BtreeTableMoveto(v153, v151, 0, &v640);
        *(_QWORD *)(v152 + 80) = v151;
        updated = v154;
        *(_WORD *)(v152 + 2) = 0;
        *(_DWORD *)(v152 + 32) = 0;
        Table = v154;
        IsValidNN = v640;
        *(_DWORD *)(v152 + 36) = v640;
        if ( !v640 )
          goto LABEL_192;
        if ( *((_DWORD *)v5 + 2) )
          goto LABEL_77;
        IsValidNN = sqlite3ReportError(11, 98879, "database corruption");
        updated = IsValidNN;
        Table = IsValidNN;
LABEL_192:
        if ( updated )
          goto LABEL_260;
        goto LABEL_28;
      case 31:
LABEL_188:
        v151 = *(_QWORD *)(56LL * *((int *)v5 + 3) + v6);
        goto LABEL_189;
      case 32:
      case 137:
        v242 = *((int *)v5 + 1);
        v243 = v3[15];
        LODWORD(v626) = 0;
        v244 = *(_QWORD *)(v243 + 8 * v242);
        v245 = *(_QWORD *)(v244 + 48);
        if ( (_BYTE)v13 == 0x89 )
        {
          v477 = *(_QWORD *)(v244 + 48);
          *(_DWORD *)(v244 + 36) = -1;
          IsValidNN = sqlite3BtreeCursorIsValidNN(v477, v8, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
          if ( (_DWORD)IsValidNN )
            goto LABEL_28;
        }
        updated = sqlite3BtreeLast(v245, &v626);
        Table = updated;
        IsValidNN = (unsigned __int8)v626;
        *(_WORD *)(v244 + 2) = (unsigned __int8)v626;
        *(_DWORD *)(v244 + 32) = 0;
        if ( updated )
          goto LABEL_260;
        if ( *((int *)v5 + 2) <= 0 || !(_DWORD)v626 )
          goto LABEL_28;
        goto LABEL_77;
      case 33:
        v287 = *((int *)v5 + 1);
        v288 = v3[15];
        LODWORD(v626) = 0;
        v289 = *(_QWORD *)(*(_QWORD *)(v288 + 8 * v287) + 48LL);
        Table = sqlite3BtreeFirst(v289, &v626, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
        updated = Table;
        if ( Table )
          goto LABEL_260;
        if ( (_DWORD)v626 )
        {
          v290 = -1;
        }
        else
        {
          v329 = sqlite3BtreeRowCountEst(v289);
          v290 = (__int16)sqlite3LogEst(v329);
        }
        IsValidNN = *((int *)v5 + 3);
        if ( v290 >= IsValidNN )
        {
          IsValidNN = *((int *)v5 + 4);
          if ( v290 <= IsValidNN )
            goto LABEL_864;
        }
        LODWORD(v626) = 0;
        goto LABEL_28;
      case 34:
      case 35:
        ++*((_DWORD *)v3 + 55);
        goto LABEL_328;
      case 36:
LABEL_328:
        v214 = *((int *)v5 + 1);
        v215 = v3[15];
        LODWORD(v626) = 0;
        v216 = *(_QWORD *)(v215 + 8 * v214);
        LODWORD(v626) = 1;
        if ( *(_BYTE *)v216 == 1 )
        {
          v217 = sqlite3VdbeSorterRewind(v216, &v626, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
        }
        else
        {
          v217 = sqlite3BtreeFirst(*(_QWORD *)(v216 + 48), &v626, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
          *(_BYTE *)(v216 + 3) = 0;
          *(_DWORD *)(v216 + 32) = 0;
        }
        Table = v217;
        updated = v217;
        if ( v217 )
          goto LABEL_260;
        IsValidNN = (unsigned __int8)v626;
        *(_BYTE *)(v216 + 2) = (_BYTE)v626;
        if ( *((int *)v5 + 2) <= 0 || (_DWORD)v626 == updated )
          goto LABEL_28;
        goto LABEL_77;
      case 37:
        v31 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1));
        v32 = sqlite3VdbeSorterNext(v7, v31, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
        goto LABEL_30;
      case 38:
        v31 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1));
        v32 = sqlite3BtreePrevious(*(_QWORD *)(v31 + 48), *((unsigned int *)v5 + 3));
        goto LABEL_30;
      case 40:
      case 41:
      case 42:
      case 45:
        v140 = *((int *)v5 + 1);
        *(_QWORD *)&v637 = 0;
        v1 = 0;
        v141 = v3[15];
        v635 = 0;
        v636 = 0;
        v142 = *(_QWORD *)(v141 + 8 * v140);
        memset(v643, 0, sizeof(v643));
        *(_QWORD *)&v635 = *(_QWORD *)(v142 + 56);
        WORD6(v636) = *((_WORD *)v5 + 8);
        BYTE14(v636) = -((unsigned __int8)v13 < 0x2Au);
        v143 = 56LL * *((int *)v5 + 3);
        v644 = 0;
        v645 = 0;
        *((_QWORD *)&v635 + 1) = v6 + v143;
        v144 = *(_QWORD *)(v142 + 48);
        getCellInfo(v144);
        v145 = *(unsigned int *)(v144 + 64);
        if ( (unsigned int)(v145 - 1) > 0x7FFFFFFE )
        {
          v478 = "database corruption";
          v479 = 100176;
          v480 = 11;
          goto LABEL_1198;
        }
        *((_QWORD *)&v643[1] + 1) = v7;
        WORD2(v643[1]) = 0;
        LODWORD(v644) = 0;
        Table = sqlite3VdbeMemFromBtreeZeroOffset(v144, v145, v643);
        updated = Table;
        if ( Table )
          goto LABEL_260;
        v146 = sqlite3VdbeRecordCompareWithSkip(LODWORD(v643[1]), *((_QWORD *)&v643[0] + 1), &v635, 0);
        IsValidNN = sqlite3VdbeMemReleaseMalloc(v643);
        v147 = v146 + 1;
        v148 = -v146;
        if ( (*v5 & 1) != 0 )
          v148 = v147;
        if ( v148 > 0 )
        {
LABEL_77:
          v59 = *((_DWORD *)v5 + 2);
LABEL_78:
          v60 = 3LL * (v59 - 1);
          IsValidNN = v625;
          v5 = (unsigned __int8 *)(v625 + 8 * v60);
        }
LABEL_28:
        v4 = v633;
        v5 += 24;
        v3 = v629;
        updated = Table;
        v7 = v627;
        v6 = v634;
        v8 = v624;
        v12 = v631;
        continue;
      case 43:
      case 44:
        v386 = sqlite3VdbeBooleanValue(v6 + 56LL * *((int *)v5 + 1), 2);
        v387 = sqlite3VdbeBooleanValue(v6 + 56LL * *((int *)v5 + 2), 2) + 2 * v386 + v386;
        v388 = qword_1800A7850;
        if ( *v5 != 44 )
          v388 = &qword_1800A7808;
        v389 = *((unsigned __int8 *)v388 + v387);
        v390 = 56LL * *((int *)v5 + 3);
        v391 = *(_WORD *)(v390 + v6 + 20);
        if ( (_BYTE)v389 == 2 )
        {
          IsValidNN = 62017;
          v392 = v391 & 0xF240 | 1;
        }
        else
        {
          IsValidNN = 62020;
          *(_QWORD *)(v390 + v6) = v389;
          v392 = v391 & 0xF240 | 4;
        }
        *(_WORD *)(v390 + v6 + 20) = v392;
        goto LABEL_28;
      case 46:
        v322 = *((int *)v5 + 1);
        v632 = 0;
        v323 = v6 + 56 * v322;
        if ( (*(_BYTE *)(v323 + 20) & 0x10) == 0
          || !(unsigned int)sqlite3RowSetNext(*(_QWORD *)(v323 + 8), &v632, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL) )
        {
          sqlite3VdbeMemSetNull(v323);
          goto LABEL_32;
        }
        sqlite3VdbeMemSetInt64(v6 + 56LL * *((int *)v5 + 3), v632);
        goto LABEL_33;
      case 47:
        IsValidNN = *((int *)v5 + 1);
        v511 = *((int *)v5 + 3);
        v512 = *((_DWORD *)v5 + 4);
        v513 = v6 + 56 * IsValidNN;
        if ( (*(_BYTE *)(v513 + 20) & 0x10) == 0 )
        {
          IsValidNN = sqlite3VdbeMemSetRowSet(v6 + 56 * IsValidNN, v8, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
          if ( (_DWORD)IsValidNN )
            goto LABEL_393;
        }
        v514 = 56 * v511;
        v515 = v512 < 0;
        if ( !v512 )
          goto LABEL_1004;
        IsValidNN = sqlite3RowSetTest(*(_QWORD *)(v513 + 8), (unsigned int)v512, *(_QWORD *)(v514 + v6), v16);
        if ( (_DWORD)IsValidNN )
          goto LABEL_77;
        v515 = v512 < 0;
LABEL_1004:
        if ( !v515 )
          IsValidNN = sqlite3RowSetInsert(*(_QWORD *)(v513 + 8), *(_QWORD *)(v514 + v6), v14, v16);
        goto LABEL_28;
      case 48:
        v251 = (signed __int64 *)*((_QWORD *)v5 + 2);
        v252 = v629;
        if ( !*((_WORD *)v5 + 1) )
          goto LABEL_398;
        IsValidNN = v629[33];
        if ( !IsValidNN )
          goto LABEL_398;
        do
        {
          if ( *(_QWORD *)(IsValidNN + 48) == v251[4] )
            goto LABEL_28;
          IsValidNN = *(_QWORD *)(IsValidNN + 8);
        }
        while ( IsValidNN );
LABEL_398:
        if ( *((_DWORD *)v629 + 70) >= *(_DWORD *)(v7 + 176) )
        {
          v3 = v629;
          updated = 1;
          sqlite3VdbeError(v629, "too many levels of trigger recursion", 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
          goto LABEL_260;
        }
        v253 = v634 + 56LL * *((int *)v5 + 3);
        if ( (*(_BYTE *)(v253 + 20) & 0x10) != 0 )
        {
          v254 = *(_QWORD *)(v253 + 8);
          v7 = v627;
LABEL_401:
          ++*((_DWORD *)v252 + 70);
          *(_QWORD *)(v254 + 8) = v252[33];
          *(_QWORD *)(v254 + 56) = *(_QWORD *)(v7 + 56);
          *(_QWORD *)(v254 + 96) = v252[7];
          v255 = *v252;
          v634 = v254 + 112;
          *(_QWORD *)(v254 + 104) = *(_QWORD *)(v255 + 120);
          *(_QWORD *)(v254 + 64) = v252[37];
          v252[13] = v254 + 112;
          v252[37] = 0;
          v252[7] = 0;
          v252[33] = v254;
          v256 = *(int *)(v254 + 88);
          *((_DWORD *)v252 + 9) = v256;
          *((_DWORD *)v252 + 10) = *(unsigned __int16 *)(v254 + 92);
          v252[15] = v254 + 112 + 56 * v256;
          v257 = (void *)(v254 + 112 + 8 * (7 * v256 + *((int *)v251 + 4)));
          *(_QWORD *)(v254 + 40) = v257;
          memset_0(v257, 0, (*((_DWORD *)v251 + 2) + 7) / 8);
          v258 = *v251;
          v252[17] = *v251;
          v259 = *((_DWORD *)v251 + 2);
          v3 = v629;
          v625 = v258;
          v5 = (unsigned __int8 *)(v258 - 24);
          *((_DWORD *)v629 + 36) = v259;
          goto LABEL_33;
        }
        v356 = *((_DWORD *)v251 + 4);
        v357 = v356 + *((_DWORD *)v251 + 3);
        if ( !v356 )
          ++v357;
        v358 = (*((_DWORD *)v251 + 2) + 7) / 8 + 8 * (v356 + 7 * (v357 + 2));
        v254 = sqlite3DbMallocZero(v627, v358);
        if ( v254 )
        {
          sqlite3VdbeMemRelease(v253);
          *(_QWORD *)(v253 + 48) = sqlite3VdbeFrameMemDel;
          *(_WORD *)(v253 + 20) = 4112;
          *(_QWORD *)(v253 + 8) = v254;
          *(_DWORD *)(v253 + 16) = v358;
          v7 = v627;
          *(_QWORD *)v254 = v252;
          *(_DWORD *)(v254 + 88) = v357;
          *(_DWORD *)(v254 + 92) = *((_DWORD *)v251 + 4);
          v359 = v254 + 112;
          *(_DWORD *)(v254 + 76) = -1431655765 * ((__int64)&v5[-v625] >> 3);
          *(_QWORD *)(v254 + 24) = v252[13];
          *(_DWORD *)(v254 + 84) = *((_DWORD *)v252 + 9);
          *(_QWORD *)(v254 + 32) = v252[15];
          *(_DWORD *)(v254 + 72) = *((_DWORD *)v252 + 10);
          *(_QWORD *)(v254 + 16) = v252[17];
          *(_DWORD *)(v254 + 80) = *((_DWORD *)v252 + 36);
          *(_QWORD *)(v254 + 48) = v251[4];
          v360 = v254 + 56 * (v357 + 2LL);
          if ( v254 + 112 != v360 )
          {
            do
            {
              *(_QWORD *)(v359 + 24) = v7;
              *(_WORD *)(v359 + 20) = 0;
              v359 += 56;
            }
            while ( v359 != v360 );
          }
          v15 = v633;
          goto LABEL_401;
        }
        goto LABEL_391;
      case 49:
        if ( *((_DWORD *)v5 + 1) )
        {
          if ( !*(_QWORD *)(v7 + 760) && !*(_QWORD *)(v7 + 768) )
            goto LABEL_77;
        }
        else if ( !v3[10] && !*(_QWORD *)(v7 + 768) )
        {
          goto LABEL_77;
        }
        goto LABEL_28;
      case 50:
        IsValidNN = *((int *)v5 + 1);
        v178 = *(_QWORD *)(56 * IsValidNN + v6);
        if ( v178 <= 0 )
          goto LABEL_28;
        *(_QWORD *)(56 * IsValidNN + v6) = v178 - *((int *)v5 + 3);
        goto LABEL_77;
      case 51:
        IsValidNN = *((int *)v5 + 1);
        if ( (*(_BYTE *)(56 * IsValidNN + v6 + 20) & 1) == 0 )
          goto LABEL_28;
        goto LABEL_77;
      case 52:
        IsValidNN = *((int *)v5 + 1);
        if ( (*(_BYTE *)(56 * IsValidNN + v6 + 20) & 1) != 0 )
          goto LABEL_28;
        goto LABEL_77;
      case 53:
      case 54:
      case 55:
      case 56:
      case 57:
      case 58:
        v61 = 56LL * *((int *)v5 + 1) + v6;
        v62 = *(_WORD *)(v61 + 20);
        v63 = v634 + 56LL * *((int *)v5 + 3);
        v64 = *(_WORD *)(v63 + 20);
        if ( ((unsigned __int8)v62 & (unsigned __int8)v64 & 4) != 0 )
        {
          IsValidNN = *(_QWORD *)v61;
          if ( *(_QWORD *)v63 > *(_QWORD *)v61 )
          {
            if ( byte_18009E837[v13] )
              goto LABEL_77;
            v631 = 1;
          }
          else if ( *(_QWORD *)v63 < *(_QWORD *)v61 )
          {
            if ( *((_BYTE *)&qword_18009E760[25] + v13 + 3) )
              goto LABEL_77;
            v631 = -1;
          }
          else
          {
            if ( byte_18009E831[v13] )
              goto LABEL_77;
            v631 = 0;
          }
        }
        else
        {
          v164 = v62 | v64;
          if ( (((unsigned __int8)v62 | (unsigned __int8)v64) & 1) == 0 )
          {
            v165 = v5[2] & 0x47;
            if ( v165 >= 0x43u )
            {
              if ( (v164 & 2) != 0 )
              {
                if ( (v62 & 0x2E) == 2 )
                {
                  applyNumericAffinity(v61, 0, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
                  v64 = *(_WORD *)(v63 + 20);
                }
                if ( (v64 & 0x2E) == 2 )
                  applyNumericAffinity(v63, 0, v14, v16);
              }
            }
            else if ( v165 == 66 && (v164 & 2) != 0 )
            {
              if ( (v62 & 2) != 0 )
              {
                *(_WORD *)(v61 + 20) = v62 & 0xFFD3;
              }
              else if ( (v62 & 0x2C) != 0 )
              {
                LOBYTE(v14) = 1;
                sqlite3VdbeMemStringify(v61, v8, v14, 0xAAAAAAAAAAAAAAABuLL);
                v8 = v624;
                v62 = *(_WORD *)(v61 + 20) ^ (v62 ^ *(_WORD *)(v61 + 20)) & 0xDBF;
                if ( v61 == v63 )
                  v64 = v62 | 2;
              }
              if ( (v64 & 2) != 0 )
              {
                *(_WORD *)(v63 + 20) &= 0xFFD3u;
              }
              else if ( (v64 & 0x2C) != 0 )
              {
                LOBYTE(v14) = 1;
                sqlite3VdbeMemStringify(v63, v8, v14, v16);
                v64 = *(_WORD *)(v63 + 20) ^ (*(_WORD *)(v63 + 20) ^ v64) & 0xDBF;
              }
            }
            v631 = sqlite3MemCompare(v63, v61, *((_QWORD *)v5 + 2));
            if ( v631 < 0 )
              goto LABEL_229;
            IsValidNN = *v5;
            if ( !v631 )
              goto LABEL_338;
            goto LABEL_663;
          }
          IsValidNN = *((unsigned __int16 *)v5 + 1);
          if ( (IsValidNN & 0x80u) != 0LL )
          {
            if ( ((unsigned __int8)v62 & (unsigned __int8)v64 & 1) != 0 && (v64 & 0x100) == 0 )
            {
              IsValidNN = *v5;
              v631 = 0;
LABEL_338:
              v166 = byte_18009E831[IsValidNN];
LABEL_230:
              *(_WORD *)(v63 + 20) = v64;
              *(_WORD *)(v61 + 20) = v62;
              if ( v166 )
                goto LABEL_77;
              goto LABEL_28;
            }
            if ( (v64 & 1) != 0 )
            {
              v631 = -1;
LABEL_229:
              IsValidNN = *v5;
              v166 = *((_BYTE *)&qword_18009E760[25] + IsValidNN + 3);
              goto LABEL_230;
            }
            IsValidNN = *v5;
            v631 = 1;
LABEL_663:
            v166 = byte_18009E837[IsValidNN];
            goto LABEL_230;
          }
          if ( (IsValidNN & 0x10) != 0 )
            goto LABEL_77;
          v631 = 1;
        }
        goto LABEL_28;
      case 59:
        if ( v12 )
          goto LABEL_28;
        goto LABEL_77;
      case 60:
        v524 = 56LL * *((int *)v5 + 1);
        IsValidNN = *(_QWORD *)(v524 + v6);
        if ( !IsValidNN )
          goto LABEL_28;
        if ( IsValidNN > 0 )
          *(_QWORD *)(v524 + v6) = IsValidNN - 1;
        goto LABEL_77;
      case 61:
        v324 = 56LL * *((int *)v5 + 1);
        IsValidNN = *(_QWORD *)(v324 + v6);
        if ( IsValidNN == 0x8000000000000000uLL )
          goto LABEL_28;
        *(_QWORD *)(v324 + v6) = --IsValidNN;
        if ( IsValidNN )
          goto LABEL_28;
        goto LABEL_77;
      case 62:
        IsValidNN = sqlite3BtreeIncrVacuum(
                      *(_QWORD *)(32LL * *((int *)v5 + 1) + *(_QWORD *)(v7 + 32) + 8),
                      v8,
                      0x180000000uLL,
                      0xAAAAAAAAAAAAAAABuLL);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( !(_DWORD)IsValidNN )
          goto LABEL_28;
        if ( (_DWORD)IsValidNN != 101 )
          goto LABEL_260;
        Table = 0;
        goto LABEL_77;
      case 63:
        IsValidNN = v3[15];
        v583 = *(_QWORD *)(IsValidNN + 8LL * *((int *)v5 + 1));
        if ( *(_BYTE *)(v583 + 2) )
          goto LABEL_28;
        v584 = *(__int64 ***)(v583 + 48);
        v585 = *v584;
        v586 = **v584;
        Table = (*(__int64 (__fastcall **)(__int64 **, __int64, unsigned __int64, unsigned __int64))(v586 + 72))(
                  v584,
                  v8,
                  0x180000000uLL,
                  0xAAAAAAAAAAAAAAABuLL);
        sqlite3VtabImportErrmsg(v3, v585);
        if ( Table )
          goto LABEL_259;
        v587 = (*(__int64 (__fastcall **)(_QWORD))(v586 + 80))(*(_QWORD *)(v583 + 48));
        v15 = v633;
        if ( v587 )
          goto LABEL_33;
        goto LABEL_32;
      case 64:
        v353 = 56LL * *((int *)v5 + 1);
        v354 = filterHash(v6, v5, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL)
             % (unsigned __int64)(8 * *(_DWORD *)(v353 + v6 + 16));
        v355 = *(char *)((v354 >> 3) + *(_QWORD *)(v353 + v6 + 8));
        IsValidNN = v354 & 7;
        if ( !_bittest(&v355, v354 & 7) )
        {
          ++*((_DWORD *)v3 + 61);
          goto LABEL_77;
        }
        ++*((_DWORD *)v3 + 60);
        goto LABEL_28;
      case 65:
      case 66:
        v193 = *((_QWORD *)v5 + 2);
        v194 = v6 + 56LL * *((int *)v5 + 3);
        if ( *(_QWORD *)v193 != v194 )
        {
          *(_BYTE *)(v193 + 40) = v8;
          v280 = (unsigned int)*(unsigned __int8 *)(v193 + 42) - 1;
          *(_QWORD *)(v193 + 24) = v3;
          for ( *(_QWORD *)v193 = v194; (int)v280 >= 0; v280 = (unsigned int)(v280 - 1) )
            *(_QWORD *)(v193 + 8 * v280 + 48) = v6 + 56LL * ((int)v280 + *((_DWORD *)v5 + 2));
        }
        *(_WORD *)(v194 + 20) &= 0xF241u;
        *(_WORD *)(v194 + 20) |= 1u;
        (*(void (__fastcall **)(__int64, _QWORD, __int64, unsigned __int64))(*(_QWORD *)(v193 + 8) + 24LL))(
          v193,
          *(unsigned __int8 *)(v193 + 42),
          v193 + 48,
          0xAAAAAAAAAAAAAAABuLL);
        IsValidNN = *(unsigned int *)(v193 + 36);
        if ( !(_DWORD)IsValidNN )
          goto LABEL_28;
        if ( (int)IsValidNN > 0 )
        {
          LOBYTE(v195) = 1;
          v196 = (const char *)sqlite3ValueText(v194, v195);
          sqlite3VdbeError(v3, "%s", v196);
          updated = *(_DWORD *)(v193 + 36);
          Table = updated;
        }
        IsValidNN = sqlite3VdbeDeleteAuxData(v7, v3 + 37, *(unsigned int *)(v193 + 32), *((unsigned int *)v5 + 1));
        *(_DWORD *)(v193 + 36) = 0;
        if ( !updated )
          goto LABEL_28;
        goto LABEL_260;
      case 67:
        IsValidNN = 56LL * *((int *)v5 + 1);
        if ( (*(_BYTE *)(IsValidNN + v6 + 20) & 4) != 0 )
        {
          v155 = 3LL * *(_QWORD *)(IsValidNN + v6);
          IsValidNN = v625;
          v5 = (unsigned __int8 *)(v625 + 8 * v155);
        }
        goto LABEL_28;
      case 68:
        v351 = *((int *)v5 + 1);
        v352 = 3LL * *(_QWORD *)(56 * v351 + v6);
        *(_QWORD *)(56 * v351 + v6) = (int)(-1431655765 * ((__int64)&v5[-v3[17]] >> 3) - 1);
        IsValidNN = *(_DWORD *)(v625 + 8 * v352 + 8) - 1;
        v5 = (unsigned __int8 *)(v625 + 24LL * (int)IsValidNN);
        goto LABEL_28;
      case 69:
        IsValidNN = *((int *)v5 + 3);
        if ( (*(_BYTE *)(56 * IsValidNN + v6 + 20) & 1) == 0 )
          goto LABEL_28;
        goto LABEL_298;
      case 70:
LABEL_298:
        v197 = v3[33];
        if ( v197 && !*((_DWORD *)v5 + 1) )
        {
          v281 = *(_QWORD *)(v197 + 8);
          --*((_DWORD *)v3 + 70);
          v3[33] = v281;
          v282 = v3[7];
          *(_QWORD *)(v7 + 128) += v282;
          *(_QWORD *)(v7 + 120) = v282;
          LODWORD(IsValidNN) = sqlite3VdbeFrameRestore(v197, v8, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
          if ( *((_DWORD *)v5 + 2) == 4 )
            LODWORD(IsValidNN) = *(_DWORD *)(v3[17] + 24LL * (int)IsValidNN + 8) - 1;
          v283 = v3[17];
          IsValidNN = (int)IsValidNN;
          v634 = v3[13];
          v625 = v283;
          v5 = (unsigned __int8 *)(v283 + 24LL * (int)IsValidNN);
          goto LABEL_28;
        }
        v198 = *((_DWORD *)v5 + 1);
        *((_DWORD *)v3 + 13) = v198;
        *((_BYTE *)v3 + 196) = v5[8];
        if ( !v198 )
        {
          v167 = v625;
          goto LABEL_301;
        }
        v611 = *((int *)v5 + 3);
        if ( (int)v611 > 0 && !v5[1] )
        {
          LOBYTE(v8) = 1;
          v612 = (const char *)sqlite3ValueText(v6 + 56 * v611, v8);
          goto LABEL_1185;
        }
        if ( *((_WORD *)v5 + 1) )
        {
          sqlite3VdbeError(v3, "%s constraint failed", off_18009BFF8[*((unsigned __int16 *)v5 + 1)]);
          if ( *((_QWORD *)v5 + 2) )
            v3[21] = sqlite3MPrintf(v7, "%z: %s", v3[21]);
        }
        else
        {
          v612 = (const char *)*((_QWORD *)v5 + 2);
LABEL_1185:
          sqlite3VdbeError(v3, "%s", v612);
        }
        v167 = v625;
        sqlite3_log(
          *((unsigned int *)v5 + 1),
          "abort at %d in [%s]: %s",
          -1431655765 * ((__int64)&v5[-v625] >> 3),
          (const char *)v3[31],
          (const char *)v3[21]);
LABEL_301:
        v168 = v622;
        updated = sqlite3VdbeHalt(v3);
        if ( updated == 5 )
        {
          *((_DWORD *)v3 + 13) = 5;
        }
        else
        {
          updated = 101;
          if ( *((_DWORD *)v3 + 13) )
            updated = 1;
        }
LABEL_236:
        while ( 1 )
        {
          v169 = v642;
          if ( v15 < v642 )
            break;
          v618 = *(unsigned int (__fastcall **)(__int64, unsigned __int64, unsigned __int64, unsigned __int64))(v7 + 528);
          if ( !v618 )
            break;
          v619 = *(_QWORD *)(v7 + 536);
          v642 += *(unsigned int *)(v7 + 544);
          if ( v618(v619, v642, v14, v16) )
          {
            v642 = -1;
            updated = 9;
LABEL_1232:
            if ( *(_BYTE *)(v7 + 103) )
            {
              updated = 7;
            }
            else if ( updated == 8458 )
            {
              updated = sqlite3ReportError(11, 102527, "database corruption");
            }
            if ( !v3[21] && updated != 3082 )
            {
              v617 = (const char *)sqlite3ErrStr(updated);
              sqlite3VdbeError(v3, "%s", v617);
            }
            *((_DWORD *)v3 + 13) = updated;
            sqlite3SystemError(v7, updated);
            sqlite3_log(
              updated,
              "statement aborts at %d: [%s] %s",
              -1431655765 * ((__int64)&v5[-v167] >> 3),
              (const char *)v3[31],
              (const char *)v3[21]);
            if ( *((_BYTE *)v3 + 199) == 2 )
              sqlite3VdbeHalt(v3);
            if ( updated == 3082 )
            {
              sqlite3OomFault(v7);
            }
            else if ( updated == 11 && !*(_BYTE *)(v7 + 101) )
            {
              *(_QWORD *)(v7 + 48) |= 0x200000000uLL;
            }
            updated = 1;
            if ( v168 )
              sqlite3ResetOneSchema(v7);
LABEL_420:
            v15 = v633;
            continue;
          }
        }
        *((_DWORD *)v3 + 57) += v15;
        if ( *((_DWORD *)v3 + 52) )
          sqlite3VdbeLeave(v3, v169, v14, v16);
        return updated;
      case 71:
        v96 = (signed __int64 *)out2Prerelease(v3, v5);
        IsValidNN = *((int *)v5 + 1);
        *v96 = IsValidNN;
        goto LABEL_28;
      case 72:
        v363 = (_QWORD *)out2Prerelease(v3, v5);
        IsValidNN = *((_QWORD *)v5 + 2);
        *v363 = *(_QWORD *)IsValidNN;
        goto LABEL_28;
      case 73:
        v302 = v624;
        goto LABEL_483;
      case 74:
      case 75:
        IsValidNN = out2Prerelease(v3, v5);
        v188 = 257;
        v189 = *((_DWORD *)v5 + 3) - *((_DWORD *)v5 + 2);
        v190 = IsValidNN;
        if ( !*((_DWORD *)v5 + 1) )
          v188 = 1;
        *(_WORD *)(IsValidNN + 20) = v188;
        for ( *(_DWORD *)(IsValidNN + 16) = 0; v189 > 0; *(_DWORD *)(v190 + 16) = 0 )
        {
          v190 += 56LL;
          IsValidNN = sqlite3VdbeMemSetNull(v190);
          --v189;
          *(_WORD *)(v190 + 20) = v188;
        }
        goto LABEL_28;
      case 76:
        v365 = 56LL * *((int *)v5 + 1);
        IsValidNN = 65473;
        *(_WORD *)(v365 + v6 + 20) &= 0xFFC1u;
        *(_WORD *)(v365 + v6 + 20) |= 1u;
        goto LABEL_28;
      case 77:
        v284 = out2Prerelease(v3, v5);
        v285 = *((_QWORD *)v5 + 2);
        v286 = v284;
        if ( v285 )
        {
          IsValidNN = sqlite3VdbeMemSetStr(v284, v285, *((int *)v5 + 1), 0, 0);
        }
        else
        {
          sqlite3VdbeMemSetZeroBlob(v284, *((unsigned int *)v5 + 1));
          IsValidNN = sqlite3VdbeMemExpandBlob(v286);
          if ( (_DWORD)IsValidNN )
            goto LABEL_393;
        }
        *(_BYTE *)(v286 + 22) = v624;
        goto LABEL_28;
      case 78:
        v171 = v3[16] + 56LL * *((int *)v5 + 1);
        if ( (unsigned int)sqlite3VdbeMemTooBig(v171 - 56, v8, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL) )
          goto LABEL_285;
        v172 = v6 + 56LL * *((int *)v5 + 2);
        if ( (*(_WORD *)(v172 + 20) & 0x9000) != 0 )
          sqlite3VdbeMemSetNull(v6 + 56LL * *((int *)v5 + 2));
        v1 = *(_OWORD *)(v171 - 56);
        *(_OWORD *)v172 = v1;
        *(_QWORD *)(v172 + 16) = *(_QWORD *)(v171 - 40);
        IsValidNN = *(unsigned __int16 *)(v172 + 20);
        LOWORD(IsValidNN) = IsValidNN & 0x8FBF | 0x2040;
        *(_WORD *)(v172 + 20) = IsValidNN;
        goto LABEL_28;
      case 79:
        v269 = *((_DWORD *)v5 + 3);
        v270 = v6 + 56LL * *((int *)v5 + 1);
        v271 = v6 + 56LL * *((int *)v5 + 2);
        while ( 1 )
        {
          sqlite3VdbeMemRelease(v271);
          IsValidNN = 0x4000;
          *(_OWORD *)v271 = *(_OWORD *)v270;
          *(_OWORD *)(v271 + 16) = *(_OWORD *)(v270 + 16);
          v1 = *(_OWORD *)(v270 + 32);
          *(_OWORD *)(v271 + 32) = v1;
          *(_QWORD *)(v271 + 48) = *(_QWORD *)(v270 + 48);
          *(_WORD *)(v270 + 20) = 1;
          *(_DWORD *)(v270 + 32) = 0;
          if ( (*(_WORD *)(v271 + 20) & 0x4000) != 0 )
          {
            IsValidNN = sqlite3VdbeMemMakeWriteable(v271);
            if ( (_DWORD)IsValidNN )
              goto LABEL_393;
          }
          v270 += 56;
          v271 += 56;
          if ( !--v269 )
            goto LABEL_28;
        }
      case 80:
        v211 = *((_DWORD *)v5 + 3);
        v212 = v6 + 56LL * *((int *)v5 + 1);
        v213 = v6 + 56LL * *((int *)v5 + 2);
        while ( 2 )
        {
          sqlite3VdbeMemShallowCopy(v213, v212, 0x4000);
          if ( (*(_WORD *)(v213 + 20) & 0x4000) != 0 && (unsigned int)sqlite3VdbeMemMakeWriteable(v213) )
            goto LABEL_393;
          IsValidNN = *(unsigned __int16 *)(v213 + 20);
          if ( (IsValidNN & 0x800) != 0 && (v5[2] & 2) != 0 )
          {
            LOWORD(IsValidNN) = IsValidNN & 0xF7FF;
            *(_WORD *)(v213 + 20) = IsValidNN;
          }
          if ( v211 )
          {
            --v211;
            v213 += 56;
            v212 += 56;
            continue;
          }
          goto LABEL_28;
        }
      case 81:
        IsValidNN = sqlite3VdbeMemShallowCopy(v6 + 56LL * *((int *)v5 + 2), v6 + 56LL * *((int *)v5 + 1), 0x4000);
        goto LABEL_28;
      case 82:
        IsValidNN = sqlite3VdbeMemSetInt64(v6 + 56LL * *((int *)v5 + 2), *(_QWORD *)(56LL * *((int *)v5 + 1) + v6));
        goto LABEL_28;
      case 83:
        IsValidNN = sqlite3VdbeCheckFk(v3, 0);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( !(_DWORD)IsValidNN )
          goto LABEL_28;
        goto LABEL_260;
      case 84:
        *((_DWORD *)v3 + 11) = (*((_DWORD *)v3 + 11) + 2) | 1;
        v3[20] = v6 + 56LL * *((int *)v5 + 1);
        if ( *(_BYTE *)(v7 + 103) )
          goto LABEL_393;
        if ( (*(_BYTE *)(v7 + 110) & 4) != 0 )
        {
          (*(void (__fastcall **)(__int64, _QWORD, __int64 *, _QWORD))(v7 + 248))(4, *(_QWORD *)(v7 + 256), v3, 0);
          v16 = 0xAAAAAAAAAAAAAAABuLL;
        }
        v167 = v625;
        v168 = v622;
        updated = 100;
        *((_DWORD *)v3 + 12) = -1431655765 * ((__int64)&v5[-v625] >> 3) + 1;
        goto LABEL_236;
      case 85:
        IsValidNN = *((int *)v5 + 1);
        if ( (_DWORD)IsValidNN )
          IsValidNN = sqlite3VdbeMemSetInt64(v6 + 56 * IsValidNN, 0);
        goto LABEL_28;
      case 86:
        v380 = v6 + 56LL * *((int *)v5 + 1);
        IsValidNN = sqlite3_value_int64(v380);
        *(_QWORD *)v380 = IsValidNN;
        *(_WORD *)(v380 + 20) &= 0xF244u;
        *(_WORD *)(v380 + 20) |= 4u;
        *(_QWORD *)v380 = IsValidNN + *((int *)v5 + 2);
        goto LABEL_28;
      case 87:
        IsValidNN = *((int *)v5 + 1);
        v383 = v6 + 56 * IsValidNN;
        if ( (*(_BYTE *)(v383 + 20) & 0x24) != 0 )
        {
          v384 = sqlite3VdbeRealValue(v6 + 56 * IsValidNN);
          IsValidNN = 62024;
          *(double *)v383 = v384;
          *(_WORD *)(v383 + 20) &= 0xF248u;
          *(_WORD *)(v383 + 20) |= 8u;
        }
        goto LABEL_28;
      case 88:
        v385 = v6 + 56LL * *((int *)v5 + 1);
        if ( (*(_WORD *)(v385 + 20) & 0x400) == 0 )
          goto LABEL_655;
        updated = sqlite3VdbeMemExpandBlob(v6 + 56LL * *((int *)v5 + 1));
        if ( !updated )
        {
          LOBYTE(v8) = v624;
LABEL_655:
          IsValidNN = sqlite3VdbeMemCast(v385, v5[8], (unsigned __int8)v8, v16);
          Table = IsValidNN;
          updated = IsValidNN;
          if ( !(_DWORD)IsValidNN )
            goto LABEL_28;
        }
        goto LABEL_260;
      case 90:
        if ( (v5[2] & 1) != 0 )
          v199 = *((_QWORD *)v5 - 1) + 4LL;
        else
          v199 = 0;
        v200 = *((_QWORD *)v5 + 2);
        v201 = 0;
        v202 = *((_DWORD *)v5 + 1);
        v203 = *((_DWORD *)v5 + 2);
        v204 = *((_DWORD *)v5 + 3);
        v632 = v200;
        LODWORD(v626) = v202;
        LODWORD(v639) = v203;
        while ( 2 )
        {
          if ( v201 < v204 )
          {
            if ( v199 )
              v205 = *(_DWORD *)(v199 + 4LL * v201);
            else
              v205 = v201;
            v206 = *(_QWORD *)(v200 + 24);
            v207 = *(_QWORD *)(v200 + 8LL * v201 + 32);
            v208 = v634 + 56LL * (unsigned int)(v205 + v203);
            LODWORD(v628) = *(_BYTE *)(v206 + v201) & 1;
            v209 = v634 + 56LL * (unsigned int)(v205 + v202);
            IsValidNN = sqlite3MemCompare(v209, v208, v207);
            v631 = IsValidNN;
            v210 = IsValidNN;
            if ( !(_DWORD)IsValidNN )
            {
              v200 = v632;
              ++v201;
              v202 = (int)v626;
              v203 = v639;
              continue;
            }
            IsValidNN = *(_QWORD *)(v632 + 24);
            if ( (*(_BYTE *)(v201 + IsValidNN) & 2) != 0
              && ((*(_BYTE *)(v209 + 20) & 1) != 0 || (*(_BYTE *)(v208 + 20) & 1) != 0) )
            {
              v210 = -v210;
              v631 = v210;
            }
            if ( (_DWORD)v628 )
              v631 = -v210;
          }
          break;
        }
        goto LABEL_28;
      case 91:
        v393 = sqlite3VdbeBooleanValue(v6 + 56LL * *((int *)v5 + 1), *((unsigned int *)v5 + 3));
        IsValidNN = sqlite3VdbeMemSetInt64(v6 + 56LL * *((int *)v5 + 2), v393 ^ (unsigned __int64)*((int *)v5 + 4));
        goto LABEL_28;
      case 92:
        if ( (*(_BYTE *)(56LL * *((int *)v5 + 1) + v6 + 20) & 1) != 0
          || (*(_BYTE *)(56LL * *((int *)v5 + 3) + v6 + 20) & 1) != 0 )
        {
          goto LABEL_219;
        }
        IsValidNN = sqlite3VdbeMemSetInt64(v6 + 56LL * *((int *)v5 + 2), 0);
        goto LABEL_28;
      case 95:
        v408 = *((_QWORD *)v5 + 2);
        v409 = *(_QWORD *)(v408 + 8);
        v410 = v6 + 56LL * *((int *)v5 + 1);
        v411 = 0;
        while ( 2 )
        {
          IsValidNN = (unsigned int)*(__int16 *)(v408 + 54);
          if ( v411 >= (int)IsValidNN )
            goto LABEL_28;
          v412 = 3LL * v411;
          v413 = *(_WORD *)(v409 + 24LL * v411 + 18);
          if ( (v413 & 0x60) == 0 )
            goto LABEL_719;
          if ( (v413 & 0x20) != 0 )
            goto LABEL_739;
          if ( *((_DWORD *)v5 + 3) )
            goto LABEL_738;
LABEL_719:
          applyAffinity(v410, *(unsigned __int8 *)(v409 + 24LL * v411 + 12), (unsigned __int8)v8, v16);
          v414 = *(_WORD *)(v410 + 20);
          if ( (v414 & 1) != 0 )
            goto LABEL_737;
          switch ( (*(_DWORD *)(v409 + 24LL * v411 + 8) >> 4) & 0xF )
          {
            case 2:
              if ( (v414 & 0x10) != 0 )
                goto LABEL_737;
              break;
            case 3:
            case 4:
              if ( (v414 & 4) != 0 )
                goto LABEL_737;
              break;
            case 5:
              if ( (v414 & 4) != 0 )
              {
                v16 = 0xFFFFFFFFFFFFLL;
                if ( (unsigned __int64)(*(_QWORD *)v410 + 0x800000000000LL) > 0xFFFFFFFFFFFFLL )
                {
                  v1 = 0;
                  v416 = v414 | 8;
                  *(double *)v410 = (double)(int)*(_QWORD *)v410;
                }
                else
                {
                  v416 = v414 | 0x20;
                }
                *(_WORD *)(v410 + 20) = v416;
                *(_WORD *)(v410 + 20) = v416 & 0xFFFB;
                goto LABEL_737;
              }
              if ( (v414 & 0x28) != 0 )
              {
LABEL_737:
                LOBYTE(v8) = v624;
LABEL_738:
                v410 += 56;
LABEL_739:
                ++v411;
                continue;
              }
              break;
            default:
              if ( ((*(_DWORD *)(v409 + 24LL * v411 + 8) >> 4) & 0xF) == 6 && (v414 & 2) == 0 )
                goto LABEL_726;
              goto LABEL_737;
          }
          break;
        }
LABEL_726:
        _mm_lfence();
        v415 = v411;
        v3 = v629;
        sqlite3VdbeError(
          v629,
          "cannot store %s value in %s column %s.%s",
          off_18009CBA0[*((unsigned __int8 *)qword_18009EC50 + (*(_WORD *)(v410 + 20) & 0x3F))],
          off_1800B5540[((*(_DWORD *)(v409 + 8 * v412 + 8) >> 4) & 0xFu) - 1],
          *(const char **)v408,
          *(const char **)(v409 + 24 * v415));
        updated = 3091;
        goto LABEL_260;
      case 96:
        v36 = (_BYTE *)*((_QWORD *)v5 + 2);
        LOBYTE(IsValidNN) = *v36;
        for ( ii = v6 + 56LL * *((int *)v5 + 1); ; ii += 56 )
        {
          applyAffinity(ii, (unsigned __int8)IsValidNN, (unsigned __int8)v8, v16);
          if ( *v36 == 69 )
          {
            v417 = *(_WORD *)(ii + 20);
            if ( (v417 & 4) != 0 )
            {
              if ( (unsigned __int64)(*(_QWORD *)ii + 0x800000000000LL) > 0xFFFFFFFFFFFFLL )
              {
                v1 = 0;
                v418 = v417 & 0xFFF1 | 8;
                *(double *)ii = (double)(int)*(_QWORD *)ii;
              }
              else
              {
                v418 = v417 & 0xFFDB | 0x20;
              }
              *(_WORD *)(ii + 20) = v418;
            }
          }
          IsValidNN = (unsigned __int8)*++v36;
          if ( !(_BYTE)IsValidNN )
            break;
          LOBYTE(v8) = v624;
        }
        goto LABEL_28;
      case 97:
        v65 = 0;
        v66 = (unsigned __int8 *)*((_QWORD *)v5 + 2);
        v67 = 0;
        v68 = *((_DWORD *)v5 + 3);
        v69 = 0;
        v70 = (int *)(v634 + 56LL * *((int *)v5 + 1));
        v71 = 14LL * (*((_DWORD *)v5 + 2) - 1);
        v639 = 0;
        v72 = &v70[v71];
        v626 = (__int64 *)v70;
        v632 = (signed __int64)v72;
        LODWORD(v628) = v68;
        if ( v66 )
        {
          v272 = *v66;
          v273 = (__int64 *)v70;
          do
          {
            applyAffinity(v273, v272, (unsigned __int8)v8, v16);
            if ( *v66 == 69 )
            {
              v419 = *((_WORD *)v273 + 10);
              if ( (v419 & 4) != 0 )
                *((_WORD *)v273 + 10) = v419 & 0xFFDB | 0x20;
            }
            v272 = *++v66;
            LOBYTE(v8) = v624;
            v273 += 7;
          }
          while ( v272 );
          v70 = (int *)v626;
          v65 = v639;
          v72 = (int *)v632;
        }
        v73 = v72;
        while ( 2 )
        {
          v74 = *((unsigned __int16 *)v73 + 10);
          if ( (v74 & 1) != 0 )
          {
            LOWORD(v74) = -(v74 & 0x400);
            v73[9] = (_WORD)v74 != 0 ? 0xA : 0;
            ++v69;
            goto LABEL_96;
          }
          if ( (v74 & 0x24) == 0 )
          {
            if ( (v74 & 8) != 0 )
            {
              ++v69;
              v73[9] = 7;
              v67 += 8;
            }
            else
            {
              v121 = v73[4];
              v122 = ((unsigned __int64)(v74 & 2 | 0x18) >> 1) + 2 * v121;
              if ( (v74 & 0x400) != 0 )
              {
                v420 = *v73;
                v122 += 2 * v420;
                if ( v67 )
                {
                  if ( (unsigned int)sqlite3VdbeMemExpandBlob(v73) )
                    goto LABEL_391;
                  v121 += *v73;
                }
                else
                {
                  v639 = v420 + v65;
                }
              }
              v67 += v121;
              v69 += sqlite3VarintLen(v122);
              v73[9] = v122;
            }
LABEL_96:
            if ( v73 != v70 )
            {
              v65 = v639;
              v73 -= 14;
              continue;
            }
            v80 = v634 + 56LL * (int)v628;
            if ( v69 > 126 )
            {
              v421 = sqlite3VarintLen(v69);
              v81 = v421 + v69;
              if ( v421 < (int)sqlite3VarintLen(v81) )
                ++v81;
            }
            else
            {
              v81 = v69 + 1;
            }
            v82 = v81 + v67;
            v83 = v639;
            if ( v82 + v639 <= *(int *)(v80 + 32) )
            {
              *(_QWORD *)(v80 + 8) = *(_QWORD *)(v80 + 40);
LABEL_102:
              *(_DWORD *)(v80 + 16) = v82;
              *(_WORD *)(v80 + 20) = 16;
              if ( v83 )
              {
                *(_DWORD *)v80 = v83;
                *(_WORD *)(v80 + 20) = 1040;
              }
              v84 = *(_BYTE **)(v80 + 8);
              v85 = &v84[v81];
              if ( v81 >= 128 )
              {
                v86 = &v84[(int)sqlite3PutVarint(v84, v81, v74, v16)];
              }
              else
              {
                *v84 = v81;
                v86 = v84 + 1;
              }
              v87 = v632;
              while ( 1 )
              {
                IsValidNN = (unsigned int)v70[9];
                if ( (unsigned int)IsValidNN <= 7 )
                {
                  *v86++ = IsValidNN;
                  if ( !(_DWORD)IsValidNN )
                    goto LABEL_116;
                  v88 = *((unsigned __int8 *)qword_18009EF00 + IsValidNN);
                  v89 = *(_QWORD *)v70;
                  if ( (_BYTE)v88 == 2 )
                  {
LABEL_114:
                    v85[1] = v89;
                    v89 >>= 8;
                  }
                  else
                  {
                    IsValidNN = (unsigned int)(v88 - 1);
                    if ( (_DWORD)v88 != 1 )
                    {
                      IsValidNN = (unsigned int)(v88 - 3);
                      if ( (_DWORD)v88 != 3 )
                      {
                        IsValidNN = (unsigned int)(v88 - 4);
                        if ( (_DWORD)v88 != 4 )
                        {
                          if ( (_DWORD)v88 != 6 )
                          {
                            v85[7] = v89;
                            v422 = v89 >> 8;
                            v85[6] = v422;
                            v89 = v422 >> 8;
                          }
                          v85[5] = v89;
                          v423 = v89 >> 8;
                          v85[4] = v423;
                          v89 = v423 >> 8;
                        }
                        v85[3] = v89;
                        v89 >>= 8;
                      }
                      v85[2] = v89;
                      v89 >>= 8;
                      goto LABEL_114;
                    }
                  }
                  *v85 = v89;
                  v85 += v88;
                  goto LABEL_116;
                }
                if ( (unsigned int)IsValidNN >= 0x80 )
                  break;
                *v86++ = IsValidNN;
                if ( (unsigned int)IsValidNN >= 0xE )
                {
                  IsValidNN = v70[4];
                  if ( (int)IsValidNN > 0 )
                    goto LABEL_186;
                }
LABEL_116:
                if ( v70 == (int *)v87 )
                  goto LABEL_28;
                v70 += 14;
              }
              v149 = (int)sqlite3PutVarint(v86, (unsigned int)v70[9], v74, v16);
              IsValidNN = v70[4];
              v86 += v149;
              if ( !(_DWORD)IsValidNN )
                goto LABEL_116;
LABEL_186:
              memcpy_0(v85, *((const void **)v70 + 1), IsValidNN);
              IsValidNN = v70[4];
              v85 += IsValidNN;
              goto LABEL_116;
            }
            if ( v82 + v639 > *(int *)(v627 + 136) )
            {
              v3 = v629;
LABEL_284:
              v7 = v627;
              goto LABEL_285;
            }
            if ( !(unsigned int)sqlite3VdbeMemClearAndResize(v80, (unsigned int)v82, v74, v16) )
              goto LABEL_102;
LABEL_391:
            v3 = v629;
            goto LABEL_392;
          }
          break;
        }
        v75 = *(_QWORD *)v73;
        v76 = *(_QWORD *)v73;
        if ( *(__int64 *)v73 < 0 )
          v76 = ~v76;
        ++v69;
        if ( v76 <= 0x7F )
        {
          if ( (*(_QWORD *)v73 & 1LL) == v75 && *((_BYTE *)v629 + 197) >= 4u )
          {
            v77 = v76 + 8;
          }
          else
          {
            ++v67;
            v77 = 1;
          }
          v78 = 36;
          v79 = (__int64)v73;
          goto LABEL_95;
        }
        if ( v76 > 0x7FFF )
        {
          if ( v76 <= 0x7FFFFF )
          {
            v67 += 3;
            v77 = 3;
            v79 = 36;
            v78 = (__int64)v73;
            goto LABEL_95;
          }
          if ( v76 > 0x7FFFFFFF )
          {
            if ( v76 > 0x7FFFFFFFFFFFLL )
            {
              v67 += 8;
              if ( (v74 & 0x20) != 0 )
              {
                v1 = 0;
                v77 = 7;
                LOWORD(v74) = v74 & 0xFFD7 | 8;
                *((_WORD *)v73 + 10) = v74;
                *(double *)v73 = (double)(int)v75;
              }
              else
              {
                v77 = 6;
              }
            }
            else
            {
              v67 += 6;
              v77 = 5;
            }
          }
          else
          {
            v67 += 4;
            v77 = 4;
          }
        }
        else
        {
          v67 += 2;
          v77 = 2;
        }
        v79 = 36;
        v78 = (__int64)v73;
LABEL_95:
        *(_DWORD *)(v79 + v78) = v77;
        goto LABEL_96;
      case 98:
        v49 = *((_DWORD *)v5 + 3) == 0;
        v318 = *((int *)v5 + 1);
        v319 = v3[15];
        v628 = 0;
        v320 = *(_QWORD *)(v319 + 8 * v318);
        if ( v49 )
        {
          Table = sqlite3BtreeCount(v7, *(_QWORD *)(v320 + 48), &v628, 0xAAAAAAAAAAAAAAABuLL);
          updated = Table;
          if ( Table )
            goto LABEL_260;
        }
        else
        {
          v628 = sqlite3BtreeRowCountEst(*(_QWORD *)(v320 + 48));
        }
        v321 = (__int64 *)out2Prerelease(v3, v5);
        *v321 = v628;
        goto LABEL_33;
      case 99:
        v439 = *(_QWORD *)(v7 + 32);
        v440 = *((unsigned int *)v5 + 3);
        v441 = 32LL * *((int *)v5 + 1);
        LODWORD(v626) = 0;
        sqlite3BtreeGetMeta(*(_QWORD *)(v441 + v439 + 8), v440, &v626, 0xAAAAAAAAAAAAAAABuLL);
        IsValidNN = out2Prerelease(v3, v5);
        *(_QWORD *)IsValidNN = (int)v626;
        goto LABEL_28;
      case 100:
        v442 = *(_QWORD *)(v7 + 32);
        v443 = 32LL * *((int *)v5 + 1);
        updated = sqlite3BtreeUpdateMeta(
                    *(_QWORD *)(v443 + v442 + 8),
                    *((unsigned int *)v5 + 2),
                    *((unsigned int *)v5 + 3),
                    0xAAAAAAAAAAAAAAABuLL);
        Table = updated;
        IsValidNN = *((unsigned int *)v5 + 2);
        if ( (_DWORD)IsValidNN == 1 )
        {
          **(_DWORD **)(v443 + v442 + 24) = *((_DWORD *)v5 + 3) - *((unsigned __int16 *)v5 + 1);
          *(_DWORD *)(v7 + 44) |= 1u;
          IsValidNN = sqlite3FkClearTriggerCache(v7, *((unsigned int *)v5 + 1));
        }
        else if ( (_DWORD)IsValidNN == 2 )
        {
          IsValidNN = v5[12];
          *(_BYTE *)(*(_QWORD *)(v443 + v442 + 24) + 112LL) = IsValidNN;
        }
        if ( *((_DWORD *)v5 + 1) == 1 )
        {
          IsValidNN = sqlite3ExpirePreparedStatements(v7, 0);
          *((_DWORD *)v3 + 50) &= 0xFFFFFFFC;
        }
        if ( !updated )
          goto LABEL_28;
        goto LABEL_260;
      case 101:
        v115 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1));
        if ( !v115 || *(_DWORD *)(v115 + 68) != *((_DWORD *)v5 + 2) )
          goto LABEL_132;
        v444 = *(_QWORD *)(v115 + 48);
        sqlite3_free(*(_QWORD *)(v444 + 24));
        *(_QWORD *)(v444 + 24) = 0;
        *(_BYTE *)v444 = 1;
        goto LABEL_139;
      case 102:
      case 113:
LABEL_132:
        if ( (v3[25] & 3) == 1 )
        {
          updated = 516;
          goto LABEL_260;
        }
        v104 = *((_DWORD *)v5 + 3);
        v105 = *(_QWORD *)(v7 + 32);
        v106 = *((unsigned int *)v5 + 2);
        v107 = v629;
        v108 = 32LL * v104;
        v109 = *(_QWORD *)(v108 + v105 + 8);
        if ( (_BYTE)v13 == 113 )
        {
          v110 = *((_WORD *)v5 + 1) & 8 | 4;
          v260 = *(_BYTE *)(*(_QWORD *)(v108 + v105 + 24) + 112LL);
          if ( v260 < *((_BYTE *)v629 + 197) )
            *((_BYTE *)v629 + 197) = v260;
          if ( (v5[2] & 0x10) != 0 )
          {
            v261 = v634 + 56 * v106;
            v262 = sqlite3_value_int64(v261);
            v107 = v629;
            LODWORD(v106) = v262;
            *(_QWORD *)v261 = v262;
            *(_WORD *)(v261 + 20) &= 0xF244u;
            *(_WORD *)(v261 + 20) |= 4u;
          }
        }
        else
        {
          v110 = 0;
        }
        v111 = v5[1];
        if ( v111 == 0xF8 )
        {
          v112 = *((_QWORD *)v5 + 2);
          v113 = *(unsigned __int16 *)(v112 + 8);
        }
        else
        {
          v113 = 0;
          v112 = 0;
          if ( v111 == 0xFD )
            v113 = *((unsigned int *)v5 + 4);
        }
        Cursor = allocateCursor(v107, *((unsigned int *)v5 + 1), v113, 0);
        v115 = Cursor;
        if ( !Cursor )
          goto LABEL_391;
        v116 = *(_QWORD *)(Cursor + 48);
        *(_DWORD *)(Cursor + 8) |= 4u;
        *(_BYTE *)(Cursor + 1) = v104;
        *(_BYTE *)(Cursor + 2) = 1;
        *(_DWORD *)(Cursor + 68) = v106;
        v117 = sqlite3BtreeCursor(v109, v106, v110, v112, v116);
        v3 = v629;
        updated = v117;
        v7 = v627;
        *(_QWORD *)(v115 + 56) = v112;
        Table = v117;
        *(_BYTE *)(v115 + 4) = v5[1] != 0xF8;
LABEL_139:
        IsValidNN = *(_QWORD *)(v115 + 48);
        *(_BYTE *)(IsValidNN + 3) = v5[2] & 3;
        if ( updated )
          goto LABEL_260;
        goto LABEL_28;
      case 103:
      case 104:
      case 105:
      case 106:
        v236 = v6 + 56LL * *((int *)v5 + 1);
        v237 = v6 + 56LL * *((int *)v5 + 3);
        if ( ((*(_BYTE *)(v236 + 20) | *(_BYTE *)(v6 + 56LL * *((int *)v5 + 2) + 20)) & 1) != 0 )
        {
          IsValidNN = sqlite3VdbeMemSetNull(v6 + 56LL * *((int *)v5 + 3));
          goto LABEL_28;
        }
        v238 = sqlite3_value_int64(v6 + 56LL * *((int *)v5 + 2));
        v239 = sqlite3_value_int64(v236);
        v240 = *v5;
        v241 = v239;
        if ( *v5 == 103 )
        {
          v238 &= v239;
LABEL_375:
          IsValidNN = 62020;
          *(_QWORD *)v237 = v238;
          *(_WORD *)(v237 + 20) &= 0xF244u;
          *(_WORD *)(v237 + 20) |= 4u;
          goto LABEL_28;
        }
        if ( v240 == 104 )
        {
          v238 |= v239;
          goto LABEL_375;
        }
        if ( !v239 )
          goto LABEL_375;
        if ( v239 >= 0 )
          goto LABEL_634;
        v240 = -45 - v240;
        if ( v239 > -64 )
        {
          v241 = -v239;
LABEL_634:
          if ( v241 < 64 )
          {
            if ( v240 == 105 )
            {
              v238 <<= v241;
            }
            else if ( v238 >= 0 )
            {
              v238 = (unsigned __int64)v238 >> v241;
            }
            else
            {
              v238 = ((unsigned __int64)v238 >> v241) | (-1LL << (64 - (unsigned __int8)v241));
            }
            goto LABEL_375;
          }
        }
        if ( v238 >= 0 || v240 == 105 )
          v238 = 0;
        else
          v238 = -1;
        goto LABEL_375;
      case 107:
      case 108:
      case 109:
      case 110:
      case 111:
        v338 = v6 + 56LL * *((int *)v5 + 1);
        v339 = 56LL * *((int *)v5 + 3);
        v340 = v6 + 56LL * *((int *)v5 + 2);
        v641 = 0;
        v341 = *(_WORD *)(v338 + 20);
        v342 = v6 + v339;
        v343 = *(_WORD *)(v340 + 20);
        if ( ((unsigned __int8)v341 & (unsigned __int8)v343 & 4) != 0 )
          goto LABEL_526;
        if ( (((unsigned __int8)v341 | (unsigned __int8)v343) & 1) != 0 )
          goto LABEL_624;
        v372 = numericType(v338);
        if ( (v372 & (unsigned __int8)numericType(v340) & 4) == 0 )
          goto LABEL_609;
LABEL_526:
        v344 = *v5;
        v345 = *(_QWORD *)v340;
        v346 = *(_QWORD *)v338;
        v641 = *(_QWORD *)v340;
        if ( v344 == 107 )
        {
          if ( !(unsigned int)sqlite3AddInt64(&v641, v346) )
          {
LABEL_528:
            *(_QWORD *)v342 = v641;
            IsValidNN = *(unsigned __int16 *)(v342 + 20);
            LOWORD(IsValidNN) = IsValidNN & 0xF240 | 4;
LABEL_529:
            *(_WORD *)(v342 + 20) = IsValidNN;
            goto LABEL_28;
          }
        }
        else
        {
          v373 = v344 - 108;
          if ( v373 )
          {
            v374 = v373 - 1;
            if ( v374 )
            {
              if ( v374 != 1 )
              {
                if ( v346 )
                {
                  if ( v346 == -1 )
                    v346 = 1;
                  v641 = v345 % v346;
                  goto LABEL_528;
                }
                goto LABEL_624;
              }
              if ( !v346 )
                goto LABEL_624;
              if ( v346 != -1 || v345 != 0x8000000000000000uLL )
              {
                v641 = v345 / v346;
                goto LABEL_528;
              }
            }
            else if ( !(unsigned int)sqlite3MulInt64(&v641, v346, v345, v16) )
            {
              goto LABEL_528;
            }
          }
          else if ( !(unsigned int)sqlite3SubInt64(&v641, v346, v345, v16) )
          {
            goto LABEL_528;
          }
        }
LABEL_609:
        v375 = sqlite3VdbeRealValue(v338);
        *(double *)&v1 = sqlite3VdbeRealValue(v340);
        *((_QWORD *)&v376 + 1) = *((_QWORD *)&v1 + 1);
        switch ( *v5 )
        {
          case 'k':
            v379 = *(double *)&v1 + v375;
            break;
          case 'l':
            v379 = *(double *)&v1 - v375;
            break;
          case 'm':
            v379 = *(double *)&v1 * v375;
            break;
          case 'n':
            if ( v375 == 0.0 )
              goto LABEL_624;
            v379 = *(double *)&v1 / v375;
            break;
          default:
            v377 = sqlite3_value_int64(v338);
            v378 = sqlite3_value_int64(v340);
            v641 = v378;
            if ( !v377 )
              goto LABEL_624;
            v376 = 0;
            if ( v377 == -1 )
              v377 = 1;
            v379 = (double)(int)(v378 % v377);
            break;
        }
        *((_QWORD *)&v1 + 1) = *((_QWORD *)&v376 + 1);
        if ( !(unsigned int)sqlite3IsNaN() )
        {
          IsValidNN = *(unsigned __int16 *)(v342 + 20);
          *(double *)v342 = v379;
          LOWORD(IsValidNN) = IsValidNN & 0xF240 | 8;
          goto LABEL_529;
        }
LABEL_624:
        IsValidNN = sqlite3VdbeMemSetNull(v342);
        goto LABEL_28;
      case 112:
        v366 = v6 + 56LL * *((int *)v5 + 1);
        v367 = v6 + 56LL * *((int *)v5 + 2);
        v368 = v6 + 56LL * *((int *)v5 + 3);
        v369 = *(_WORD *)(v366 + 20);
        if ( ((*(_BYTE *)(v367 + 20) | (unsigned __int8)v369) & 1) != 0 )
        {
          IsValidNN = sqlite3VdbeMemSetNull(v368);
          goto LABEL_28;
        }
        if ( (v369 & 0x12) != 0 )
        {
          if ( (v369 & 0x400) == 0 )
            goto LABEL_579;
          if ( (unsigned int)sqlite3VdbeMemExpandBlob(v366) )
            goto LABEL_392;
        }
        else if ( (unsigned int)sqlite3VdbeMemStringify(v366, v8, 0, 0xAAAAAAAAAAAAAAABuLL) )
        {
          goto LABEL_392;
        }
        v8 = v624;
        v369 = *(_WORD *)(v366 + 20) & 0xFFFD;
LABEL_579:
        v370 = *(_WORD *)(v367 + 20);
        if ( (v370 & 0x12) != 0 )
        {
          if ( (v370 & 0x400) == 0 )
            goto LABEL_585;
          if ( (unsigned int)sqlite3VdbeMemExpandBlob(v367) )
            goto LABEL_392;
        }
        else if ( (unsigned int)sqlite3VdbeMemStringify(v367, v8, 0, v16) )
        {
          goto LABEL_392;
        }
        v370 = *(_WORD *)(v367 + 20) & 0xFFFD;
LABEL_585:
        LODWORD(v371) = *(_DWORD *)(v366 + 16) + *(_DWORD *)(v367 + 16);
        if ( (int)v371 > *(_DWORD *)(v627 + 136) )
        {
          v3 = v629;
          v7 = v627;
          goto LABEL_285;
        }
        if ( (unsigned int)sqlite3VdbeMemGrow(v368, (unsigned int)(v371 + 2), v368 == v367) )
          goto LABEL_391;
        v371 = (int)v371;
        *(_WORD *)(v368 + 20) &= 0xF242u;
        *(_WORD *)(v368 + 20) |= 2u;
        if ( v368 != v367 )
        {
          memcpy_0(*(void **)(v368 + 8), *(const void **)(v367 + 8), *(int *)(v367 + 16));
          *(_WORD *)(v367 + 20) = v370;
        }
        memcpy_0((void *)(*(_QWORD *)(v368 + 8) + *(int *)(v367 + 16)), *(const void **)(v366 + 8), *(int *)(v366 + 16));
        *(_WORD *)(v366 + 20) = v369;
        if ( v624 > 1u )
          v371 = (int)v371 & 0xFFFFFFFFFFFFFFFEuLL;
        *(_BYTE *)(v371 + *(_QWORD *)(v368 + 8)) = 0;
        *(_BYTE *)(*(_QWORD *)(v368 + 8) + v371 + 1) = 0;
        IsValidNN = 512;
        *(_WORD *)(v368 + 20) |= 0x200u;
        *(_DWORD *)(v368 + 16) = v371;
        *(_BYTE *)(v368 + 22) = v624;
        goto LABEL_28;
      case 114:
        v445 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 2));
        v446 = allocateCursor(v3, *((unsigned int *)v5 + 1), (unsigned int)*(__int16 *)(v445 + 72), 0);
        if ( !v446 )
          goto LABEL_393;
        *(_DWORD *)(v446 + 8) |= 1u;
        *(_BYTE *)(v446 + 2) = 1;
        *(_QWORD *)(v446 + 56) = *(_QWORD *)(v445 + 56);
        *(_BYTE *)(v446 + 4) = *(_BYTE *)(v445 + 4);
        *(_DWORD *)(v446 + 68) = *(_DWORD *)(v445 + 68);
        v447 = *(_DWORD *)(v446 + 8) ^ (*(_DWORD *)(v445 + 8) ^ *(_DWORD *)(v446 + 8)) & 4;
        *(_DWORD *)(v446 + 8) = v447;
        *(_QWORD *)(v446 + 16) = *(_QWORD *)(v445 + 16);
        *(_DWORD *)(v446 + 8) = v447 | 8;
        *(_DWORD *)(v445 + 8) |= 8u;
        IsValidNN = sqlite3BtreeCursor(
                      *(_QWORD *)(v446 + 16),
                      *(_DWORD *)(v446 + 68),
                      4,
                      *(_QWORD *)(v446 + 56),
                      *(_QWORD *)(v446 + 48));
        Table = IsValidNN;
        goto LABEL_28;
      case 115:
        v396 = v6 + 56LL * *((int *)v5 + 1);
        v397 = v6 + 56LL * *((int *)v5 + 2);
        IsValidNN = sqlite3VdbeMemSetNull(v397);
        if ( (*(_BYTE *)(v396 + 20) & 1) == 0 )
        {
          *(_WORD *)(v397 + 20) = 4;
          IsValidNN = ~sqlite3_value_int64(v396);
          *(_QWORD *)v397 = IsValidNN;
        }
        goto LABEL_28;
      case 116:
      case 117:
        v228 = *((int *)v5 + 3);
        if ( (int)v228 > 0 )
        {
          *(_DWORD *)(56 * v228 + v6 + 16) = 0;
          *(_QWORD *)(56LL * *((int *)v5 + 3) + v6 + 8) = qword_18009EEF0;
        }
        v229 = *((int *)v5 + 1);
        v230 = *(_QWORD *)(v3[15] + 8 * v229);
        if ( !v230 || (*(_BYTE *)(v230 + 8) & 8) != 0 || *((_DWORD *)v5 + 2) > *(__int16 *)(v230 + 72) )
        {
          v231 = allocateCursor(v3, v229, *((unsigned int *)v5 + 2), 0);
          v230 = v231;
          if ( !v231 )
            goto LABEL_393;
          *(_DWORD *)(v231 + 8) |= 1u;
          LODWORD(v620) = *((unsigned __int16 *)v5 + 1) | 5;
          updated = sqlite3BtreeOpen(*(_QWORD *)v7, 0, v7, v231 + 16, v620, 1054);
          if ( updated )
            goto LABEL_260;
          Table = sqlite3BtreeBeginTrans(*(_QWORD *)(v230 + 16), 1, 0);
          updated = Table;
          if ( !Table )
          {
            v232 = *((_QWORD *)v5 + 2);
            v233 = *(_QWORD *)(v230 + 16);
            *(_QWORD *)(v230 + 56) = v232;
            if ( v232 )
            {
              Table = sqlite3BtreeCreateTable(v233, v230 + 68, *((unsigned __int16 *)v5 + 1) | 2u);
              if ( Table )
              {
                updated = Table;
              }
              else
              {
                updated = sqlite3BtreeCursor(
                            *(_QWORD *)(v230 + 16),
                            *(_DWORD *)(v230 + 68),
                            4,
                            v232,
                            *(_QWORD *)(v230 + 48));
                Table = updated;
              }
              *(_BYTE *)(v230 + 4) = 0;
            }
            else
            {
              v621 = *(_QWORD *)(v230 + 48);
              *(_DWORD *)(v230 + 68) = 1;
              updated = sqlite3BtreeCursor(v233, 1, 4, 0, v621);
              Table = updated;
              *(_BYTE *)(v230 + 4) = 1;
            }
            v3 = v629;
          }
          v234 = 0;
          if ( *((_WORD *)v5 + 1) != 8 )
            v234 = 4;
          IsValidNN = *(_DWORD *)(v230 + 8) & 0xFFFFFFFB;
          *(_DWORD *)(v230 + 8) = IsValidNN | v234;
          if ( updated )
          {
            sqlite3BtreeClose(*(_QWORD *)(v230 + 16));
            goto LABEL_260;
          }
        }
        else
        {
          v361 = *(unsigned int *)(v230 + 68);
          v362 = *(_QWORD *)(v230 + 16);
          *(_QWORD *)(v230 + 24) = 0;
          *(_DWORD *)(v230 + 32) = 0;
          IsValidNN = sqlite3BtreeClearTable(v362, v361, 0);
          Table = IsValidNN;
          updated = IsValidNN;
          if ( (_DWORD)IsValidNN )
            goto LABEL_260;
        }
        *(_BYTE *)(v230 + 2) = 1;
        goto LABEL_28;
      case 118:
        v297 = out2Prerelease(v3, v5);
        v300 = sqlite3Strlen30(*((_QWORD *)v5 + 2), v298, v299);
        v302 = v624;
        *((_DWORD *)v5 + 1) = v300;
        if ( v624 == 1 )
          goto LABEL_481;
        LOBYTE(v301) = 1;
        Table = sqlite3VdbeMemSetStr(v297, *((_QWORD *)v5 + 2), -1, v301, 0);
        if ( Table )
          goto LABEL_285;
        if ( (unsigned int)sqlite3VdbeChangeEncoding(v297, v624) )
          goto LABEL_393;
        *(_DWORD *)(v297 + 32) = 0;
        *(_WORD *)(v297 + 20) |= 0x2000u;
        if ( v5[1] == 0xFA )
          sqlite3DbFree(v7, *((_QWORD *)v5 + 2));
        v5[1] = -6;
        *((_QWORD *)v5 + 2) = *(_QWORD *)(v297 + 8);
        v300 = *(_DWORD *)(v297 + 16);
        *((_DWORD *)v5 + 1) = v300;
LABEL_481:
        if ( v300 > *(_DWORD *)(v7 + 136) )
          goto LABEL_285;
        *v5 = 73;
LABEL_483:
        IsValidNN = out2Prerelease(v3, v5);
        v303 = IsValidNN;
        *(_WORD *)(IsValidNN + 20) = 8706;
        *(_QWORD *)(IsValidNN + 8) = *((_QWORD *)v5 + 2);
        *(_DWORD *)(IsValidNN + 16) = *((_DWORD *)v5 + 1);
        *(_BYTE *)(IsValidNN + 22) = v302;
        v304 = *((int *)v5 + 3);
        if ( (int)v304 > 0 )
        {
          IsValidNN = *((unsigned __int16 *)v5 + 1);
          if ( *(_QWORD *)(56 * v304 + v6) == IsValidNN )
            *(_WORD *)(v303 + 20) = 8720;
        }
        goto LABEL_28;
      case 119:
        LOBYTE(v16) = 1;
        v448 = allocateCursor(v3, *((unsigned int *)v5 + 1), *((unsigned int *)v5 + 2), v16);
        if ( !v448 )
          goto LABEL_393;
        *(_QWORD *)(v448 + 56) = *((_QWORD *)v5 + 2);
        IsValidNN = sqlite3VdbeSorterInit(v7, *((unsigned int *)v5 + 3), v448);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( !(_DWORD)IsValidNN )
          goto LABEL_28;
        goto LABEL_260;
      case 120:
        v449 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1));
        v450 = *(_QWORD *)(v449 + 24);
        IsValidNN = v450 + 1;
        *(_QWORD *)(v449 + 24) = v450 + 1;
        if ( v450 )
          goto LABEL_28;
        goto LABEL_77;
      case 121:
        LOBYTE(v16) = 3;
        IsValidNN = allocateCursor(v3, *((unsigned int *)v5 + 1), *((unsigned int *)v5 + 3), v16);
        if ( !IsValidNN )
          goto LABEL_393;
        *(_BYTE *)(IsValidNN + 2) = 1;
        *(_DWORD *)(IsValidNN + 36) = *((_DWORD *)v5 + 2);
        *(_QWORD *)(IsValidNN + 48) = &dword_1800B5BF4;
        *(_BYTE *)(IsValidNN + 4) = 1;
        goto LABEL_28;
      case 122:
        sqlite3VdbeFreeCursor(v3, *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1)), 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
        IsValidNN = v3[15];
        *(_QWORD *)(IsValidNN + 8LL * *((int *)v5 + 1)) = 0;
        goto LABEL_28;
      case 124:
        v330 = *((int *)v5 + 7);
        *(_QWORD *)&v637 = 0;
        v1 = 0;
        v331 = v3[15];
        LODWORD(v626) = 0;
        v635 = 0;
        v636 = 0;
        v332 = *(_QWORD *)(v331 + 8 * v330);
        IsValidNN = sqlite3BtreeCursorIsValidNN(*(_QWORD *)(v332 + 48), v8, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
        if ( !(_DWORD)IsValidNN )
          goto LABEL_28;
        v333 = *((_DWORD *)v5 + 1);
        *(_QWORD *)&v635 = *(_QWORD *)(v332 + 56);
        WORD6(v636) = *((_WORD *)v5 + 20);
        v334 = *((int *)v5 + 9);
        BYTE14(v636) = 0;
        *((_QWORD *)&v635 + 1) = v6 + 56 * v334;
        LODWORD(v626) = 0;
        while ( 2 )
        {
          Table = sqlite3VdbeIdxKeyCompare(v7, v332, &v635, &v626);
          updated = Table;
          if ( Table )
            goto LABEL_260;
          IsValidNN = (unsigned int)v626;
          v335 = (int)v626 < 0;
          if ( (int)v626 <= 0 )
            goto LABEL_521;
          if ( !*((_WORD *)v5 + 1) )
            goto LABEL_874;
          v335 = (int)v626 < 0;
LABEL_521:
          if ( !v335 )
            goto LABEL_77;
          if ( v333 <= 0 )
            goto LABEL_28;
          v336 = *(_QWORD *)(v332 + 48);
          *(_DWORD *)(v332 + 32) = 0;
          v337 = sqlite3BtreeNext(v336, 0);
          updated = v337;
          if ( !v337 )
          {
            --v333;
            continue;
          }
          break;
        }
        if ( v337 != 101 )
          goto LABEL_260;
        Table = 0;
LABEL_874:
        v5 += 24;
        goto LABEL_77;
      case 125:
        IsValidNN = v3[15];
        v315 = *((_DWORD *)v5 + 2);
        v316 = *(_QWORD *)(IsValidNN + 8LL * *((int *)v5 + 1));
        v317 = *(unsigned __int16 *)(v316 + 12);
        if ( v317 < v315 )
        {
          *(_WORD *)(v316 + 12) = v315;
        }
        else
        {
          IsValidNN = *((unsigned int *)v5 + 3);
          if ( v317 > (int)IsValidNN )
            *(_WORD *)(v316 + 12) = IsValidNN;
        }
        goto LABEL_28;
      case 126:
        *(_QWORD *)out2Prerelease(v3, v5) = *(_QWORD *)(*(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1)) + 24LL);
        IsValidNN = v3[15];
        v456 = *(_QWORD *)(IsValidNN + 8LL * *((int *)v5 + 1));
        ++*(_QWORD *)(v456 + 24);
        goto LABEL_28;
      case 127:
        v628 = 0;
        LODWORD(v626) = 0;
        v263 = (__int64 *)out2Prerelease(v3, v5);
        v264 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1));
        if ( (*(_BYTE *)(v264 + 8) & 2) != 0 )
          goto LABEL_409;
        Table = sqlite3BtreeLast(*(_QWORD *)(v264 + 48), &v626);
        if ( Table )
          goto LABEL_259;
        if ( (_DWORD)v626 )
        {
          v628 = 1;
        }
        else
        {
          v457 = *(_QWORD *)(v264 + 48);
          getCellInfo(v457);
          v458 = *(_QWORD *)(v457 + 48);
          v628 = v458;
          if ( v458 == 0x7FFFFFFFFFFFFFFFLL )
            *(_DWORD *)(v264 + 8) |= 2u;
          else
            v628 = v458 + 1;
        }
LABEL_409:
        v265 = *((int *)v5 + 3);
        if ( !(_DWORD)v265 )
          goto LABEL_410;
        v459 = v3[33];
        if ( v459 )
        {
          for ( ; *(_QWORD *)(v459 + 8); v459 = *(_QWORD *)(v459 + 8) )
            ;
          v460 = *(_QWORD *)(v459 + 24) + 56 * v265;
        }
        else
        {
          v460 = v6 + 56 * v265;
        }
        v461 = sqlite3_value_int64(v460);
        *(_QWORD *)v460 = v461;
        *(_WORD *)(v460 + 20) &= 0xF244u;
        *(_WORD *)(v460 + 20) |= 4u;
        if ( v461 == 0x7FFFFFFFFFFFFFFFLL || (*(_BYTE *)(v264 + 8) & 2) != 0 )
          goto LABEL_914;
        v462 = v461 + 1;
        v463 = v628;
        if ( v628 < v462 )
        {
          v463 = v462;
          v628 = v462;
        }
        *(_QWORD *)v460 = v463;
LABEL_410:
        if ( (*(_BYTE *)(v264 + 8) & 2) == 0 )
          goto LABEL_411;
        v464 = 0;
        while ( 2 )
        {
          sqlite3_randomness(8, &v628);
          v628 = (v628 & 0x3FFFFFFFFFFFFFFFLL) + 1;
          Table = sqlite3BtreeTableMoveto(*(_QWORD *)(v264 + 48), v628, 0, &v626);
          if ( Table )
            goto LABEL_259;
          if ( !(_DWORD)v626 )
          {
            if ( ++v464 >= 100 )
            {
LABEL_914:
              updated = 13;
              goto LABEL_260;
            }
            continue;
          }
          break;
        }
LABEL_411:
        *(_BYTE *)(v264 + 3) = 0;
        *(_DWORD *)(v264 + 32) = 0;
        IsValidNN = v628;
        *v263 = v628;
        goto LABEL_28;
      case 128:
        v1 = 0;
        v305 = *((int *)v5 + 1);
        v306 = 56LL * *((int *)v5 + 2);
        v635 = 0;
        v636 = 0;
        v307 = v3[15];
        v637 = 0;
        v308 = *(_QWORD *)(v307 + 8 * v305);
        v49 = v5[1] == 0xFB;
        v309 = *(_QWORD *)(56LL * *((int *)v5 + 3) + v6);
        *((_QWORD *)&v635 + 1) = v309;
        if ( v49 && *(_QWORD *)(v7 + 320) )
        {
          v310 = (_QWORD *)*((_QWORD *)v5 + 2);
          v311 = *(_QWORD *)(32LL * *(char *)(v308 + 1) + *(_QWORD *)(v7 + 32));
        }
        else
        {
          v310 = 0;
          v311 = 0;
        }
        if ( (v5[2] & 1) != 0 )
        {
          ++v3[7];
          if ( (v5[2] & 0x20) != 0 )
            *(_QWORD *)(v7 + 56) = v309;
        }
        v312 = *((_WORD *)v5 + 1);
        *(_QWORD *)&v636 = *(_QWORD *)(v306 + v6 + 8);
        DWORD1(v637) = *(_DWORD *)(v306 + v6 + 16);
        if ( (v312 & 0x10) != 0 )
          v313 = *(unsigned int *)(v308 + 36);
        else
          v313 = 0;
        if ( (*(_WORD *)(v306 + v6 + 20) & 0x400) != 0 )
          DWORD2(v637) = *(_DWORD *)(v306 + v6);
        else
          DWORD2(v637) = 0;
        *(_QWORD *)&v635 = 0;
        IsValidNN = sqlite3BtreeInsert(*(_QWORD *)(v308 + 48), &v635, (unsigned __int8)v312 & 0x8A, v313);
        Table = IsValidNN;
        *(_BYTE *)(v308 + 3) = 0;
        *(_DWORD *)(v308 + 32) = 0;
        if ( (_DWORD)IsValidNN )
          goto LABEL_259;
        ++v638;
        if ( v310 )
        {
          v314 = 23;
          if ( (v5[2] & 4) == 0 )
            v314 = 18;
          IsValidNN = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _QWORD))(v7 + 320))(
                        *(_QWORD *)(v7 + 312),
                        v314,
                        v311,
                        *v310,
                        *((_QWORD *)&v635 + 1));
        }
        goto LABEL_28;
      case 129:
        v465 = *((int *)v5 + 3);
        if ( (_DWORD)v465 )
          v466 = *(_QWORD *)(56 * v465 + v6);
        else
          v466 = 0;
        IsValidNN = sqlite3BtreeTransferRow(
                      *(_QWORD *)(*(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1)) + 48LL),
                      *(_QWORD *)(*(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 2)) + 48LL),
                      v466);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( !(_DWORD)IsValidNN )
          goto LABEL_28;
        goto LABEL_260;
      case 130:
        v291 = *((_DWORD *)v5 + 2);
        v292 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1));
        if ( v5[1] == 0xFB && *(_QWORD *)(v7 + 320) )
        {
          v294 = *((_QWORD *)v5 + 2);
          v293 = *(_QWORD *)(32LL * *(char *)(v292 + 1) + *(_QWORD *)(v7 + 32));
          if ( (v5[2] & 2) != 0 && *(_BYTE *)(v292 + 4) )
          {
            v467 = *(_QWORD *)(v292 + 48);
            getCellInfo(v467);
            *(_QWORD *)(v292 + 80) = *(_QWORD *)(v467 + 48);
          }
        }
        else
        {
          v293 = 0;
          v294 = 0;
        }
        IsValidNN = sqlite3BtreeDelete(*(_QWORD *)(v292 + 48), v5[2]);
        Table = IsValidNN;
        *(_QWORD *)(v292 + 32) = 0;
        if ( (_DWORD)IsValidNN )
        {
          v3 = v629;
          goto LABEL_259;
        }
        ++v638;
        if ( (v291 & 1) != 0 )
        {
          ++v629[7];
          IsValidNN = *(_QWORD *)(v7 + 320);
          if ( IsValidNN )
          {
            if ( v294 && *(char *)(v294 + 48) >= 0 )
              IsValidNN = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, _QWORD, _QWORD))IsValidNN)(
                            *(_QWORD *)(v7 + 312),
                            9,
                            v293,
                            *(_QWORD *)v294,
                            *(_QWORD *)(v292 + 80));
          }
        }
        goto LABEL_28;
      case 131:
        IsValidNN = v3[7];
        *(_QWORD *)(v7 + 128) += IsValidNN;
        *(_QWORD *)(v7 + 120) = IsValidNN;
        v3[7] = 0;
        goto LABEL_28;
      case 132:
        v468 = v3[15];
        v469 = *((unsigned int *)v5 + 4);
        v470 = 56LL * *((int *)v5 + 3);
        v471 = *((int *)v5 + 1);
        LODWORD(v626) = 0;
        IsValidNN = sqlite3VdbeSorterCompare(*(_QWORD *)(v468 + 8 * v471), v6 + v470, v469, &v626);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( (_DWORD)IsValidNN )
          goto LABEL_260;
        if ( !(_DWORD)v626 )
          goto LABEL_28;
        goto LABEL_77;
      case 133:
        Table = sqlite3VdbeSorterRowkey(
                  *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1)),
                  v6 + 56LL * *((int *)v5 + 2),
                  0x180000000uLL,
                  0xAAAAAAAAAAAAAAABuLL);
        updated = Table;
        if ( Table )
          goto LABEL_260;
        IsValidNN = v3[15];
        *(_DWORD *)(*(_QWORD *)(IsValidNN + 8LL * *((int *)v5 + 3)) + 32LL) = 0;
        goto LABEL_28;
      case 134:
        v472 = out2Prerelease(v3, v5);
        v473 = *(_QWORD *)(*(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1)) + 48LL);
        getCellInfo(v473);
        v474 = *(unsigned int *)(v473 + 64);
        if ( (unsigned int)v474 > *(_DWORD *)(v7 + 136) )
          goto LABEL_285;
        IsValidNN = sqlite3VdbeMemFromBtreeZeroOffset(v473, v474, v472);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( (_DWORD)IsValidNN )
          goto LABEL_260;
        if ( *((_DWORD *)v5 + 3) )
          goto LABEL_28;
        IsValidNN = 0x4000;
        if ( (*(_WORD *)(v472 + 20) & 0x4000) == 0 )
          goto LABEL_28;
        IsValidNN = sqlite3VdbeMemMakeWriteable(v472);
        if ( !(_DWORD)IsValidNN )
          goto LABEL_28;
        goto LABEL_393;
      case 135:
        v632 = 0;
        IsValidNN = out2Prerelease(v3, v5);
        v156 = *((int *)v5 + 1);
        v157 = IsValidNN;
        v158 = v3[15];
        v159 = *(_QWORD *)(v158 + 8 * v156);
        if ( !*(_BYTE *)(v159 + 2) )
        {
          if ( *(_BYTE *)(v159 + 3) )
          {
            IsValidNN = *(_QWORD *)(v159 + 80);
          }
          else if ( *(_BYTE *)v159 == 2 )
          {
            v475 = *(__int64 **)(v159 + 48);
            v476 = *v475;
            Table = (*(__int64 (__fastcall **)(__int64 *, signed __int64 *))(*(_QWORD *)*v475 + 96LL))(v475, &v632);
            updated = Table;
            sqlite3VtabImportErrmsg(v3, v476);
            if ( Table )
              goto LABEL_260;
            IsValidNN = v632;
          }
          else
          {
            IsValidNN = sqlite3VdbeCursorRestore(*(_QWORD *)(v158 + 8 * v156));
            Table = IsValidNN;
            updated = IsValidNN;
            if ( (_DWORD)IsValidNN )
              goto LABEL_260;
            if ( *(_BYTE *)(v159 + 2) )
            {
              *(_WORD *)(v157 + 20) = 1;
              goto LABEL_28;
            }
            v218 = *(_QWORD *)(v159 + 48);
            getCellInfo(v218);
            IsValidNN = *(_QWORD *)(v218 + 48);
          }
          *(_QWORD *)v157 = IsValidNN;
          goto LABEL_28;
        }
        *(_WORD *)(IsValidNN + 20) = 1;
        goto LABEL_28;
      case 136:
        v295 = *((int *)v5 + 1);
        IsValidNN = *(_QWORD *)(v3[15] + 8 * v295);
        if ( IsValidNN )
          goto LABEL_478;
        LOBYTE(v16) = 3;
        IsValidNN = allocateCursor(v3, v295, 1, v16);
        if ( !IsValidNN )
          goto LABEL_393;
        *(_DWORD *)(IsValidNN + 8) |= 8u;
        *(_QWORD *)(IsValidNN + 48) = &dword_1800B5BF4;
        *(_DWORD *)(IsValidNN + 36) = 0;
        *(_BYTE *)(IsValidNN + 4) = 1;
LABEL_478:
        v49 = *(_BYTE *)IsValidNN == 0;
        *(_BYTE *)(IsValidNN + 2) = 1;
        *(_DWORD *)(IsValidNN + 32) = 0;
        if ( v49 )
        {
          v296 = *(_QWORD *)(IsValidNN + 48);
          IsValidNN = sqlite3_free(*(_QWORD *)(v296 + 24));
          *(_QWORD *)(v296 + 24) = 0;
          *(_BYTE *)v296 = 1;
        }
        goto LABEL_28;
      case 138:
        v128 = v3[15];
        v1 = 0;
        v129 = *((int *)v5 + 1);
        v635 = 0;
        v636 = 0;
        v637 = 0;
        v130 = *(_QWORD *)(v128 + 8 * v129);
        v131 = v6 + 56LL * *((int *)v5 + 2);
        if ( (v5[2] & 1) != 0 )
          ++v3[7];
        if ( (*(_WORD *)(v131 + 20) & 0x400) != 0 )
        {
          updated = sqlite3VdbeMemExpandBlob(v131);
          if ( updated )
            goto LABEL_260;
        }
        v132 = *((_WORD *)v5 + 1);
        *((_QWORD *)&v635 + 1) = *(int *)(v131 + 16);
        *(_QWORD *)&v635 = *(_QWORD *)(v131 + 8);
        v133 = v6 + 56LL * *((int *)v5 + 3);
        LOWORD(v637) = *((_WORD *)v5 + 8);
        *((_QWORD *)&v636 + 1) = v133;
        v134 = (v132 & 0x10) != 0 ? *(unsigned int *)(v130 + 36) : 0LL;
        IsValidNN = sqlite3BtreeInsert(*(_QWORD *)(v130 + 48), &v635, (unsigned __int8)v132 & 0x8A, v134);
        Table = IsValidNN;
        updated = IsValidNN;
        *(_DWORD *)(v130 + 32) = 0;
        if ( (_DWORD)IsValidNN )
          goto LABEL_260;
        goto LABEL_28;
      case 139:
        v249 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1));
        v250 = v6 + 56LL * *((int *)v5 + 2);
        if ( (*(_WORD *)(v250 + 20) & 0x400) != 0 )
        {
          updated = sqlite3VdbeMemExpandBlob(v6 + 56LL * *((int *)v5 + 2));
          if ( updated )
            goto LABEL_260;
        }
        IsValidNN = sqlite3VdbeSorterWrite(v249, v250, v14, v16);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( (_DWORD)IsValidNN )
          goto LABEL_260;
        goto LABEL_28;
      case 140:
        v274 = *((int *)v5 + 1);
        LODWORD(v626) = 0;
        *(_QWORD *)&v637 = 0;
        v275 = v3[15];
        v1 = 0;
        v635 = 0;
        v636 = 0;
        v276 = *(_QWORD **)(v275 + 8 * v274);
        v277 = v276[6];
        *(_QWORD *)&v635 = v276[7];
        WORD6(v636) = *((_WORD *)v5 + 6);
        v278 = *((int *)v5 + 2);
        BYTE14(v636) = 0;
        *((_QWORD *)&v635 + 1) = v6 + 56 * v278;
        Table = sqlite3BtreeIndexMoveto(v277, &v635, &v626);
        updated = Table;
        if ( Table )
          goto LABEL_260;
        if ( (_DWORD)v626 )
        {
          if ( *((_WORD *)v5 + 1) && !(unsigned int)sqlite3WritableSchema(v7) )
          {
            v478 = "index corruption";
            v479 = 99971;
            v480 = 779;
LABEL_1198:
            updated = sqlite3ReportError(v480, v479, v478);
            goto LABEL_260;
          }
        }
        else
        {
          LOBYTE(v279) = 4;
          Table = sqlite3BtreeDelete(v277, v279);
          updated = Table;
          if ( Table )
            goto LABEL_260;
        }
        IsValidNN = 0;
        v276[4] = 0;
        goto LABEL_28;
      case 141:
      case 142:
        v18 = *((int *)v5 + 1);
        v19 = v3[15];
        v628 = 0;
        v20 = *(_QWORD *)(v19 + 8 * v18);
        Table = sqlite3VdbeCursorRestore(v20);
        updated = Table;
        if ( Table )
          goto LABEL_260;
        if ( *(_BYTE *)(v20 + 2) )
        {
LABEL_219:
          IsValidNN = sqlite3VdbeMemSetNull(v6 + 56LL * *((int *)v5 + 2));
        }
        else
        {
          v628 = 0;
          Table = sqlite3VdbeIdxRowid(v7, *(_QWORD *)(v20 + 48), &v628);
          updated = Table;
          if ( Table )
            goto LABEL_260;
          if ( *v5 == 0x8D )
          {
            v21 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 3));
            *(_BYTE *)(v21 + 2) = 0;
            *(_QWORD *)(v21 + 80) = v628;
            *(_BYTE *)(v21 + 3) = 1;
            *(_DWORD *)(v21 + 32) = 0;
            IsValidNN = *((_QWORD *)v5 + 2);
            *(_QWORD *)(v21 + 16) = IsValidNN;
            *(_QWORD *)(v21 + 40) = v20;
          }
          else
          {
            IsValidNN = out2Prerelease(v3, v5);
            *(_QWORD *)IsValidNN = v628;
          }
        }
        goto LABEL_28;
      case 143:
        IsValidNN = v3[15];
        v481 = *(_QWORD *)(IsValidNN + 8LL * *((int *)v5 + 1));
        if ( !*(_BYTE *)(v481 + 3) )
          goto LABEL_28;
        IsValidNN = sqlite3VdbeFinishMoveto(v481, v8, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( !(_DWORD)IsValidNN )
          goto LABEL_28;
        goto LABEL_260;
      case 144:
        LODWORD(v626) = 0;
        v482 = out2Prerelease(v3, v5);
        *(_WORD *)(v482 + 20) = 1;
        if ( *(_DWORD *)(v7 + 220) > *(_DWORD *)(v7 + 232) + 1 )
        {
          updated = 6;
          *((_BYTE *)v3 + 196) = 2;
          goto LABEL_260;
        }
        v483 = *((_DWORD *)v5 + 3);
        v484 = *(_QWORD *)(v7 + 32);
        v485 = *((unsigned int *)v5 + 1);
        LODWORD(v626) = 0;
        updated = sqlite3BtreeDropTable(*(_QWORD *)(32LL * (int)v483 + v484 + 8), v485, &v626);
        Table = updated;
        *(_WORD *)(v482 + 20) = 4;
        IsValidNN = (int)v626;
        *(_QWORD *)v482 = (int)v626;
        if ( updated )
          goto LABEL_260;
        if ( (_DWORD)v626 )
        {
          sqlite3RootPageMoved(v7, v483, (unsigned int)v626, *((unsigned int *)v5 + 1));
          IsValidNN = v483 + 1;
          v622 = v483 + 1;
        }
        goto LABEL_28;
      case 145:
        v486 = *(_QWORD *)(v7 + 32);
        v487 = *((unsigned int *)v5 + 1);
        v488 = 32LL * *((int *)v5 + 2);
        v632 = 0;
        IsValidNN = sqlite3BtreeClearTable(*(_QWORD *)(v488 + v486 + 8), v487, &v632);
        updated = IsValidNN;
        Table = IsValidNN;
        if ( *((_DWORD *)v5 + 3) )
        {
          v489 = v632;
          v3[7] += v632;
          IsValidNN = *((int *)v5 + 3);
          if ( (int)IsValidNN > 0 )
            *(_QWORD *)(56 * IsValidNN + v6) += v489;
        }
        if ( !updated )
          goto LABEL_28;
        goto LABEL_260;
      case 146:
        v490 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1));
        if ( *(_BYTE *)v490 == 1 )
        {
          IsValidNN = sqlite3VdbeSorterReset(v7, *(_QWORD *)(v490 + 48), 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
        }
        else
        {
          IsValidNN = sqlite3BtreeClearTable(
                        *(_QWORD *)(*(_QWORD *)(v490 + 48) + 8LL),
                        *(unsigned int *)(*(_QWORD *)(v490 + 48) + 80LL),
                        0);
          Table = IsValidNN;
          updated = IsValidNN;
          if ( (_DWORD)IsValidNN )
            goto LABEL_260;
        }
        goto LABEL_28;
      case 147:
        LODWORD(v626) = 0;
        v491 = out2Prerelease(v3, v5);
        v492 = *(_QWORD *)(v7 + 32);
        v493 = (_QWORD *)v491;
        v494 = *((unsigned int *)v5 + 3);
        v495 = 32LL * *((int *)v5 + 1);
        LODWORD(v626) = 0;
        IsValidNN = sqlite3BtreeCreateTable(*(_QWORD *)(v495 + v492 + 8), &v626, v494);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( (_DWORD)IsValidNN )
          goto LABEL_260;
        *v493 = (unsigned int)v626;
        goto LABEL_28;
      case 148:
        ++*(_BYTE *)(v7 + 112);
        v49 = (v5[4] & 1) == 0;
        v347 = *(_QWORD *)(v7 + 512);
        v348 = *(_BYTE *)(v7 + 110);
        v349 = *(_DWORD *)(v7 + 744);
        v628 = 0;
        if ( !v49 )
        {
          *(_QWORD *)(v7 + 512) = 0;
          *(_BYTE *)(v7 + 110) = 0;
        }
        if ( (v5[4] & 2) != 0 )
          *(_DWORD *)(v7 + 744) = *((_DWORD *)v5 + 2);
        IsValidNN = sqlite3_exec(v7, *((_QWORD *)v5 + 2), 0, 0, (__int64)&v628);
        v350 = (const char *)v628;
        --*(_BYTE *)(v7 + 112);
        *(_DWORD *)(v7 + 744) = v349;
        updated = IsValidNN;
        Table = IsValidNN;
        *(_QWORD *)(v7 + 512) = v347;
        *(_BYTE *)(v7 + 110) = v348;
        if ( !v350 && !(_DWORD)IsValidNN )
          goto LABEL_28;
        sqlite3VdbeError(v3, "%s", v350);
        sqlite3_free(v628);
        if ( updated != 7 )
          goto LABEL_260;
        goto LABEL_393;
      case 149:
        v496 = *((_QWORD *)v5 + 2);
        v497 = *((int *)v5 + 1);
        v1 = 0;
        *(_QWORD *)&v637 = 0;
        v635 = 0;
        v636 = 0;
        if ( v496 )
        {
          v498 = *(_QWORD *)(v7 + 32);
          *(_QWORD *)&v635 = v7;
          LODWORD(v636) = v497;
          *((_QWORD *)&v635 + 1) = v3 + 21;
          DWORD2(v636) = 0;
          LODWORD(v637) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(32 * v497 + v498 + 8) + 8LL) + 64LL);
          v499 = sqlite3MPrintf(
                   v7,
                   "SELECT*FROM\"%w\".%s WHERE %s ORDER BY rowid",
                   *(_QWORD *)(32 * v497 + v498),
                   "sqlite_master",
                   v496);
          if ( !v499 )
          {
            sqlite3ResetAllSchemasOfConnection(v7);
            goto LABEL_393;
          }
          *(_BYTE *)(v7 + 197) = 1;
          DWORD1(v636) = 0;
          HIDWORD(v636) = 0;
          Table = sqlite3_exec(v7, v499, (unsigned int)sqlite3InitCallback, (unsigned int)&v635, 0);
          updated = Table;
          if ( !Table )
          {
            updated = DWORD1(v636);
            Table = DWORD1(v636);
            if ( !DWORD1(v636) && !HIDWORD(v636) )
            {
              updated = sqlite3ReportError(11, 100469, "database corruption");
              Table = updated;
            }
          }
          IsValidNN = sqlite3DbFreeNN(v7, v499);
          *(_BYTE *)(v7 + 197) = 0;
        }
        else
        {
          sqlite3SchemaClear(*(_QWORD *)(32 * v497 + *(_QWORD *)(v7 + 32) + 24), v8, 0x180000000uLL);
          *(_DWORD *)(v7 + 44) &= ~0x10u;
          IsValidNN = sqlite3InitOne(v7, (unsigned int)v497, v3 + 21, *((unsigned __int16 *)v5 + 1));
          *(_DWORD *)(v7 + 44) |= 1u;
          updated = IsValidNN;
          *((_DWORD *)v3 + 50) &= 0xFFFFFFFC;
          Table = IsValidNN;
        }
        if ( !updated )
          goto LABEL_28;
        sqlite3ResetAllSchemasOfConnection(v7);
        if ( updated != 7 )
          goto LABEL_260;
        goto LABEL_393;
      case 150:
        IsValidNN = sqlite3AnalysisLoad(v7, *((unsigned int *)v5 + 1), 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( !(_DWORD)IsValidNN )
          goto LABEL_28;
        goto LABEL_260;
      case 151:
        IsValidNN = sqlite3UnlinkAndDeleteTable(
                      v7,
                      *((unsigned int *)v5 + 1),
                      *((_QWORD *)v5 + 2),
                      0xAAAAAAAAAAAAAAABuLL);
        goto LABEL_28;
      case 152:
        IsValidNN = sqlite3UnlinkAndDeleteIndex(
                      v7,
                      *((unsigned int *)v5 + 1),
                      *((_QWORD *)v5 + 2),
                      0xAAAAAAAAAAAAAAABuLL);
        goto LABEL_28;
      case 153:
        IsValidNN = sqlite3UnlinkAndDeleteTrigger(
                      v7,
                      *((unsigned int *)v5 + 1),
                      *((_QWORD *)v5 + 2),
                      0xAAAAAAAAAAAAAAABuLL);
        goto LABEL_28;
      case 154:
        v364 = out2Prerelease(v3, v5);
        *(_WORD *)(v364 + 20) = 8;
        IsValidNN = *((_QWORD *)v5 + 2);
        *(_QWORD *)v364 = *(_QWORD *)IsValidNN;
        goto LABEL_28;
      case 155:
        v500 = *((int *)v5 + 1);
        v501 = *((_QWORD *)v5 + 2);
        v502 = 56 * v500;
        v503 = v500 + 1;
        LODWORD(v626) = 0;
        v504 = *(_QWORD *)(v7 + 32);
        v505 = 56 * *((_DWORD *)v5 + 3);
        v628 = 0;
        v506 = v6 + 56LL * v503;
        Table = sqlite3BtreeIntegrityCheck(
                  v7,
                  *(_QWORD *)(32LL * *((unsigned __int16 *)v5 + 1) + v504 + 8),
                  (int)v501 + 4,
                  (int)v6 + v505,
                  *((_DWORD *)v5 + 2),
                  *(_DWORD *)(v502 + v6) + 1,
                  (__int64)&v626,
                  (__int64)&v628);
        updated = Table;
        sqlite3VdbeMemSetNull(v506);
        if ( !(_DWORD)v626 )
          goto LABEL_993;
        if ( Table )
          goto LABEL_1201;
        LOBYTE(v507) = 1;
        *(_QWORD *)(v502 + v6) -= (int)v626 - 1;
        sqlite3VdbeMemSetStr(v506, v628, -1, v507, sqlite3_free);
LABEL_993:
        sqlite3VdbeChangeEncoding(v506, v624);
        v15 = v633;
        goto LABEL_33;
      case 156:
        v508 = *((int *)v5 + 1);
        v509 = *((int *)v5 + 2);
        v510 = v6 + 56 * v508;
        if ( (*(_BYTE *)(v510 + 20) & 0x10) == 0
          && (unsigned int)sqlite3VdbeMemSetRowSet(v6 + 56 * v508, v8, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL) )
        {
          goto LABEL_393;
        }
        IsValidNN = sqlite3RowSetInsert(*(_QWORD *)(v510 + 8), *(_QWORD *)(56 * v509 + v6), v14, v16);
        goto LABEL_28;
      case 157:
        v516 = out2Prerelease(v3, v5);
        IsValidNN = sqlite3VdbeMemShallowCopy(
                      v516,
                      *(_QWORD *)(v3[33] + 24)
                    + 56LL
                    * (*((_DWORD *)v5 + 1) + *(_DWORD *)(*(_QWORD *)(v3[33] + 16) + 24LL * *(int *)(v3[33] + 76) + 4)),
                      0x4000);
        goto LABEL_28;
      case 158:
        IsValidNN = *((int *)v5 + 2);
        if ( (*(_DWORD *)(v7 + 48) & 0x80000) != 0 )
        {
          *(_QWORD *)(v7 + 768) += IsValidNN;
        }
        else if ( *((_DWORD *)v5 + 1) )
        {
          *(_QWORD *)(v7 + 760) += IsValidNN;
        }
        else
        {
          v3[10] += IsValidNN;
        }
        goto LABEL_28;
      case 159:
        v517 = v3[33];
        if ( v517 )
        {
          for ( ; *(_QWORD *)(v517 + 8); v517 = *(_QWORD *)(v517 + 8) )
            ;
          v518 = *(_QWORD *)(v517 + 24) + 56LL * *((int *)v5 + 1);
        }
        else
        {
          v518 = v6 + 56LL * *((int *)v5 + 1);
        }
        *(_QWORD *)v518 = sqlite3_value_int64(v518);
        *(_WORD *)(v518 + 20) &= 0xF244u;
        *(_WORD *)(v518 + 20) |= 4u;
        v519 = v6 + 56LL * *((int *)v5 + 2);
        IsValidNN = sqlite3_value_int64(v519);
        *(_WORD *)(v519 + 20) &= 0xF244u;
        *(_WORD *)(v519 + 20) |= 4u;
        *(_QWORD *)v519 = IsValidNN;
        if ( *(_QWORD *)v518 < IsValidNN )
          *(_QWORD *)v518 = IsValidNN;
        goto LABEL_28;
      case 160:
        v520 = *((int *)v5 + 3);
        v521 = 56LL * *((int *)v5 + 1);
        v628 = 0;
        IsValidNN = out2Prerelease(v3, v5);
        v522 = (_QWORD *)IsValidNN;
        v628 = *(_QWORD *)(v521 + v6);
        if ( v628 <= 0 )
          goto LABEL_1035;
        v523 = *(_QWORD *)(56 * v520 + v6);
        if ( v523 <= 0 )
          v523 = 0;
        IsValidNN = sqlite3AddInt64(&v628, v523);
        if ( (_DWORD)IsValidNN )
        {
LABEL_1035:
          *v522 = -1;
        }
        else
        {
          IsValidNN = v628;
          *v522 = v628;
        }
        goto LABEL_28;
      case 161:
      case 162:
        v525 = *((unsigned __int16 *)v5 + 1);
        v526 = sqlite3DbMallocRawNN(v7, 8 * v525 + 104);
        if ( !v526 )
          goto LABEL_393;
        v527 = v526 + 8 * (v525 + 6);
        *(_QWORD *)v526 = v527;
        *(_WORD *)(v527 + 20) = 1;
        *(_QWORD *)(v527 + 24) = v7;
        *(_DWORD *)(v527 + 32) = 0;
        *(_QWORD *)(v526 + 16) = 0;
        *(_QWORD *)(v526 + 8) = *((_QWORD *)v5 + 2);
        *(_QWORD *)(v526 + 24) = v3;
        *(_DWORD *)(v526 + 32) = -1431655765 * ((__int64)&v5[-v625] >> 3);
        *(_BYTE *)(v526 + 40) = v624;
        *(_BYTE *)(v526 + 41) = 0;
        *(_DWORD *)(v526 + 36) = 0;
        *(_BYTE *)(v526 + 42) = v525;
        *(_WORD *)v5 = -3677;
        *((_QWORD *)v5 + 2) = v526;
        goto LABEL_340;
      case 163:
LABEL_340:
        v219 = (_DWORD *)*((_QWORD *)v5 + 2);
        v220 = v6 + 56LL * *((int *)v5 + 3);
        if ( *((_QWORD *)v219 + 2) != v220 )
        {
          v528 = (unsigned int)*((unsigned __int8 *)v219 + 42) - 1;
          for ( *((_QWORD *)v219 + 2) = v220; (int)v528 >= 0; v528 = (unsigned int)(v528 - 1) )
            *(_QWORD *)&v219[2 * v528 + 12] = v6 + 56LL * ((int)v528 + *((_DWORD *)v5 + 2));
        }
        ++*(_DWORD *)(v220 + 16);
        v221 = v219 + 12;
        v222 = *((_QWORD *)v219 + 1);
        v223 = *((unsigned __int8 *)v219 + 42);
        if ( *((_DWORD *)v5 + 1) )
          (*(void (__fastcall **)(_DWORD *, __int64, _DWORD *, unsigned __int64))(v222 + 48))(v219, v223, v221, v16);
        else
          (*(void (__fastcall **)(_DWORD *, __int64, _DWORD *, unsigned __int64))(v222 + 24))(v219, v223, v221, v16);
        IsValidNN = (unsigned int)v219[9];
        if ( !(_DWORD)IsValidNN )
          goto LABEL_28;
        if ( (int)IsValidNN > 0 )
        {
          LOBYTE(v224) = 1;
          v225 = (const char *)sqlite3ValueText(*(_QWORD *)v219, v224);
          sqlite3VdbeError(v3, "%s", v225);
          updated = v219[9];
          Table = updated;
        }
        if ( *((_BYTE *)v219 + 41) )
        {
          v226 = *((int *)v5 - 5);
          if ( (_DWORD)v226 )
            sqlite3VdbeMemSetInt64(v6 + 56 * v226, 1);
          *((_BYTE *)v219 + 41) = 0;
        }
        sqlite3VdbeMemRelease(*(_QWORD *)v219);
        IsValidNN = *(_QWORD *)v219;
        *(_WORD *)(*(_QWORD *)v219 + 20LL) = 1;
        v219[9] = 0;
        if ( !updated )
          goto LABEL_28;
        goto LABEL_260;
      case 164:
      case 165:
        v246 = *((int *)v5 + 3);
        v247 = v6 + 56LL * *((int *)v5 + 1);
        if ( (_DWORD)v246 )
        {
          updated = sqlite3VdbeMemAggValue(
                      v6 + 56LL * *((int *)v5 + 1),
                      v6 + 56 * v246,
                      *((_QWORD *)v5 + 2),
                      0xAAAAAAAAAAAAAAABuLL);
          Table = updated;
          v247 = v6 + 56LL * *((int *)v5 + 3);
        }
        else
        {
          updated = sqlite3VdbeMemFinalize(
                      v6 + 56LL * *((int *)v5 + 1),
                      *((_QWORD *)v5 + 2),
                      0x180000000uLL,
                      0xAAAAAAAAAAAAAAABuLL);
          Table = updated;
        }
        if ( updated )
        {
          LOBYTE(v248) = 1;
          v613 = sqlite3ValueText(v247, v248);
          sqlite3VdbeError(v3, "%s", v613);
          goto LABEL_260;
        }
        IsValidNN = sqlite3VdbeChangeEncoding(v247, v624);
        goto LABEL_28;
      case 166:
        if ( *((_DWORD *)v5 + 1) )
        {
          IsValidNN = *((unsigned int *)v3 + 50);
          *((_DWORD *)v3 + 50) = IsValidNN
                               ^ ((unsigned __int8)IsValidNN
                                ^ (unsigned __int8)(*((_DWORD *)v5 + 2) + 1))
                               & 3;
        }
        else
        {
          IsValidNN = sqlite3ExpirePreparedStatements(v7, *((unsigned int *)v5 + 2));
        }
        goto LABEL_28;
      case 167:
        IsValidNN = *(_QWORD *)(*(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1)) + 48LL);
        *(_BYTE *)(IsValidNN + 1) |= 0x40u;
        goto LABEL_28;
      case 168:
        IsValidNN = *(_QWORD *)(*(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1)) + 48LL);
        *(_BYTE *)(IsValidNN + 1) &= ~0x40u;
        goto LABEL_28;
      case 169:
        v549 = v5[12];
        if ( !(_BYTE)v549 )
        {
          IsValidNN = 0x400000000LL;
          if ( (*(_QWORD *)(v7 + 48) & 0x400000000LL) != 0 )
            goto LABEL_28;
        }
        IsValidNN = sqlite3BtreeLockTable(
                      *(_QWORD *)(32LL * *((int *)v5 + 1) + *(_QWORD *)(v7 + 32) + 8),
                      *((unsigned int *)v5 + 2),
                      v549,
                      0xAAAAAAAAAAAAAAABuLL);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( !(_DWORD)IsValidNN )
          goto LABEL_28;
        if ( (_BYTE)IsValidNN == 6 )
          sqlite3VdbeError(v3, "database table is locked: %s", *((_QWORD *)v5 + 2));
        goto LABEL_260;
      case 170:
        v550 = *((_QWORD *)v5 + 2);
        IsValidNN = sqlite3VtabBegin(v7, v550, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( v550 )
          IsValidNN = sqlite3VtabImportErrmsg(v3, *(_QWORD *)(v550 + 16));
        if ( !updated )
          goto LABEL_28;
        goto LABEL_260;
      case 171:
        v551 = *((int *)v5 + 2);
        v1 = 0;
        v644 = 0;
        memset(v643, 0, 24);
        v645 = 0;
        *((_QWORD *)&v643[1] + 1) = v7;
        v552 = sqlite3VdbeMemCopy(v643, v6 + 56 * v551, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
        LOBYTE(v553) = 1;
        Table = v552;
        updated = v552;
        v554 = sqlite3ValueText(v643, v553);
        if ( v554 )
        {
          updated = sqlite3VtabCallCreate(v7, *((unsigned int *)v5 + 1), v554, v3 + 21);
          Table = updated;
        }
        IsValidNN = sqlite3VdbeMemRelease(v643);
        if ( !updated )
          goto LABEL_28;
        goto LABEL_260;
      case 172:
        ++*(_DWORD *)(v7 + 232);
        IsValidNN = sqlite3VtabCallDestroy(v7, *((unsigned int *)v5 + 1), *((_QWORD *)v5 + 2), 0xAAAAAAAAAAAAAAABuLL);
        --*(_DWORD *)(v7 + 232);
        updated = IsValidNN;
        Table = IsValidNN;
        if ( !(_DWORD)IsValidNN )
          goto LABEL_28;
        goto LABEL_260;
      case 173:
        v555 = *((_QWORD *)v5 + 2);
        v628 = 0;
        v556 = *(__int64 **)(v555 + 16);
        if ( !v556 || (v557 = *v556) == 0 )
        {
LABEL_1208:
          updated = 6;
          goto LABEL_260;
        }
        Table = (*(__int64 (__fastcall **)(__int64 *, __int64 *, unsigned __int64, unsigned __int64))(v557 + 48))(
                  v556,
                  &v628,
                  0x180000000uLL,
                  0xAAAAAAAAAAAAAAABuLL);
        updated = Table;
        sqlite3VtabImportErrmsg(v3, v556);
        if ( Table )
          goto LABEL_260;
        LOBYTE(v558) = 2;
        *(_QWORD *)v628 = v556;
        IsValidNN = allocateCursor(v3, *((unsigned int *)v5 + 1), 0, v558);
        if ( IsValidNN )
        {
          *(_QWORD *)(IsValidNN + 48) = v628;
          ++*((_DWORD *)v556 + 2);
          goto LABEL_28;
        }
        (*(void (__fastcall **)(__int64))(v557 + 56))(v628);
        goto LABEL_393;
      case 174:
        v97 = *((int *)v5 + 2);
        v628 = 0;
        v98 = v6 + 56 * v97;
        IsValidNN = sqlite3VdbeMemSetNull(v98);
        v99 = (_QWORD *)*((_QWORD *)v5 + 2);
        v100 = v99[10];
        if ( !v100 )
          goto LABEL_28;
        v101 = *(__int64 **)(v100 + 16);
        v102 = *v101;
        ++*(_DWORD *)(v100 + 24);
        updated = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, __int64 *))(v102 + 192))(
                    v101,
                    *(_QWORD *)(32LL * *((int *)v5 + 1) + *(_QWORD *)(v7 + 32)),
                    *v99,
                    *((unsigned int *)v5 + 3),
                    &v628);
        Table = updated;
        IsValidNN = sqlite3VtabUnlock(v99[10]);
        if ( updated )
        {
LABEL_1201:
          sqlite3_free(v628);
          goto LABEL_260;
        }
        if ( v628 )
        {
          LOBYTE(v103) = 1;
          IsValidNN = sqlite3VdbeMemSetStr(v98, v628, -1, v103, sqlite3_free);
        }
        goto LABEL_28;
      case 175:
        v559 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1));
        v560 = (_QWORD *)sqlite3_malloc64(16, v8, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
        v561 = v560;
        if ( !v560 )
          goto LABEL_393;
        *v560 = *(_QWORD *)(v559 + 48);
        v560[1] = v6 + 56LL * *((int *)v5 + 3);
        v562 = out2Prerelease(v3, v5);
        *(_WORD *)(v562 + 20) = 1;
        IsValidNN = sqlite3VdbeMemSetPointer(v562, v561, "ValueList", sqlite3VdbeValueListFree);
        goto LABEL_28;
      case 176:
        v1 = 0;
        v652 = 0;
        memset(v650, 0, sizeof(v650));
        v654 = 0;
        v655 = 0;
        v651 = 0;
        memset_0(&v653, 0, 0x45u);
        v576 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1));
        v394 = v6 + 56LL * *((int *)v5 + 3);
        if ( *(_BYTE *)(v576 + 2) )
        {
LABEL_1114:
          IsValidNN = sqlite3VdbeMemSetNull(v394);
          goto LABEL_28;
        }
        v49 = (v5[2] & 1) == 0;
        v577 = **(__int64 ***)(v576 + 48);
        v578 = *v577;
        *(_QWORD *)&v650[0] = v6 + 56LL * *((int *)v5 + 3);
        BYTE8(v651) = v624;
        v656 = 0x1000000;
        *((_QWORD *)&v650[0] + 1) = &v653;
        if ( v49 )
        {
          v579 = *(_WORD *)(v394 + 20) & 0xF240 | 1;
        }
        else
        {
          sqlite3VdbeMemSetNull(v394);
          v579 = 1025;
          *(_DWORD *)v394 = 0;
        }
        *(_WORD *)(v394 + 20) = v579;
        v580 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *, _QWORD))(v578 + 88))(
                 *(_QWORD *)(v576 + 48),
                 v650,
                 *((unsigned int *)v5 + 2));
        v3 = v629;
        Table = v580;
        sqlite3VtabImportErrmsg(v629, v577);
        if ( SDWORD1(v651) <= 0 )
        {
          updated = Table;
        }
        else
        {
          LOBYTE(v581) = 1;
          v582 = (const char *)sqlite3ValueText(v394, v581);
          sqlite3VdbeError(v3, "%s", v582);
          updated = DWORD1(v651);
          Table = DWORD1(v651);
        }
        IsValidNN = sqlite3VdbeChangeEncoding(v394, v624);
        if ( !updated )
          goto LABEL_28;
        goto LABEL_260;
      case 177:
        v588 = *(_DWORD *)(v7 + 48);
        *(_QWORD *)(v7 + 48) |= 0x4000000uLL;
        v589 = *(_QWORD *)(*((_QWORD *)v5 + 2) + 16LL);
        v590 = v6 + 56LL * *((int *)v5 + 1);
        Table = sqlite3VdbeChangeEncoding(v590, 1);
        if ( Table )
          goto LABEL_259;
        Table = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v589 + 152LL))(v589, *(_QWORD *)(v590 + 8));
        if ( (v588 & 0x4000000) == 0 )
          *(_QWORD *)(v7 + 48) &= ~0x4000000uLL;
        IsValidNN = sqlite3VtabImportErrmsg(v3, v589);
        *((_DWORD *)v3 + 50) &= 0xFFFFFFFC;
        updated = Table;
        if ( !Table )
          goto LABEL_28;
        goto LABEL_260;
      case 178:
        IsValidNN = out2Prerelease(v3, v5);
        *(_QWORD *)IsValidNN = *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(32LL * *((int *)v5 + 1)
                                                                       + *(_QWORD *)(v7 + 32)
                                                                       + 8)
                                                           + 8LL)
                                               + 64LL);
        goto LABEL_28;
      case 179:
        v599 = (_QWORD *)out2Prerelease(v3, v5);
        v600 = *((_DWORD *)v5 + 3);
        v601 = *(_QWORD *)(32LL * *((int *)v5 + 1) + *(_QWORD *)(v7 + 32) + 8);
        v602 = 0;
        if ( v600 )
        {
          v602 = *(unsigned int *)(*(_QWORD *)(v601 + 8) + 64LL);
          if ( (unsigned int)v602 < v600 )
            v602 = v600;
        }
        IsValidNN = (unsigned int)sqlite3BtreeMaxPageCount(v601, v602);
        *v599 = (unsigned int)IsValidNN;
        goto LABEL_28;
      case 180:
        IsValidNN = 63487;
        *(_WORD *)(56LL * *((int *)v5 + 1) + v6 + 20) &= ~0x800u;
        goto LABEL_28;
      case 181:
        v603 = 56LL * *((int *)v5 + 1);
        v50 = v6 + 56LL * *((int *)v5 + 2);
        if ( (*(_WORD *)(v603 + v6 + 20) & 0x800) == 0 )
          goto LABEL_1168;
        IsValidNN = sqlite3VdbeMemSetInt64(v50, *(unsigned __int8 *)(v603 + v6 + 23));
        goto LABEL_28;
      case 182:
        v604 = 56LL * *((int *)v5 + 1);
        v605 = 56LL * *((int *)v5 + 2);
        if ( (*(_BYTE *)(v604 + v6 + 20) & 1) != 0 )
        {
          IsValidNN = 63487;
          *(_WORD *)(v605 + v6 + 20) &= ~0x800u;
        }
        else
        {
          *(_WORD *)(v605 + v6 + 20) |= 0x800u;
          IsValidNN = *(unsigned __int8 *)(v604 + v6);
          *(_BYTE *)(v605 + v6 + 23) = IsValidNN;
        }
        goto LABEL_28;
      case 183:
        v135 = 56LL * *((int *)v5 + 1);
        v136 = filterHash(v6, v5, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
        v137 = *(_QWORD *)(v135 + v6 + 8);
        v138 = (v136 % (8 * *(_DWORD *)(v135 + v6 + 16))) & 7;
        v139 = (v136 % (8 * *(_DWORD *)(v135 + v6 + 16))) >> 3;
        IsValidNN = (unsigned int)*(char *)(v139 + v137);
        LODWORD(IsValidNN) = IsValidNN | (1 << v138);
        *(_BYTE *)(v139 + v137) = IsValidNN;
        goto LABEL_28;
      default:
        IsValidNN = v17;
        goto LABEL_28;
    }
  }
}

```

## disassembly

```asm
0x18002a050  mov     r11, rsp
0x18002a053  push    rbp
0x18002a054  push    r15
0x18002a056  lea     rbp, [r11-168h]
0x18002a05d  sub     rsp, 258h
0x18002a064  mov     rax, cs:__security_cookie
0x18002a06b  xor     rax, rsp
0x18002a06e  mov     [rbp+160h+var_60], rax
0x18002a075  mov     r10, [rcx+88h]
0x18002a07c  mov     r15, rcx
0x18002a07f  mov     [r11+18h], rsi
0x18002a083  xor     esi, esi
0x18002a085  mov     [r11+20h], rdi
0x18002a089  mov     rdi, r10
0x18002a08c  mov     [r11-18h], r12
0x18002a090  mov     r12, [rcx+68h]
0x18002a094  mov     [r11-20h], r13
0x18002a098  mov     r13, [rcx]
0x18002a09b  mov     qword ptr [rsp+260h+var_1F0], rcx
0x18002a0a0  mov     [rsp+260h+var_210], r10
0x18002a0a5  mov     [rsp+260h+var_200], r13
0x18002a0aa  movzx   edx, byte ptr [r13+64h]
0x18002a0af  mov     byte ptr [rsp+260h+var_218], dl
0x18002a0b3  mov     [rsp+260h+var_220], 0
0x18002a0b8  mov     [rbp+160h+var_1D8], rsi
0x18002a0bc  mov     [rbp+160h+var_1D0], r12
0x18002a0c0  cmp     [rcx+0D0h], esi
0x18002a0c6  jnz     loc_18002CCE1
0x18002a0cc  cmp     [r13+210h], rsi
0x18002a0d3  jnz     loc_18002BAB5
0x18002a0d9  mov     [rbp+160h+var_178], 0FFFFFFFFFFFFFFFFh
0x18002a0e1  cmp     dword ptr [r15+34h], 7
0x18002a0e6  mov     [rsp+260h+arg_8], rbx
0x18002a0ee  mov     [rsp+260h+var_20], r14
0x18002a0f6  movaps  [rsp+260h+var_38+8], xmm6
0x18002a0fe  movaps  [rsp+260h+var_48+8], xmm7
0x18002a106  movaps  [rsp+260h+var_58+8], xmm8
0x18002a10f  jz      loc_18002BDB6
0x18002a115  mov     [r15+34h], esi
0x18002a119  mov     [r15+48h], rsi
0x18002a11d  mov     eax, [r13+198h]
0x18002a124  mov     [r13+298h], esi
0x18002a12b  test    eax, eax
0x18002a12d  jnz     loc_18002FD96
0x18002a133  movsxd  rax, dword ptr [r15+30h]
0x18002a137  xor     r14d, r14d
0x18002a13a  xor     r11d, r11d
0x18002a13d  mov     [rsp+260h+var_21C], r14d
0x18002a142  mov     [rsp+260h+var_1E4], r11d
0x18002a147  xorps   xmm8, xmm8
0x18002a14b  mov     [rbp+160h+var_198], esi
0x18002a14e  lea     rcx, [rax+rax*2]
0x18002a152  lea     rdi, [r10+rcx*8]
0x18002a156  movzx   ebx, byte ptr [rdi]
0x18002a159  lea     r8, cs:180000000h
0x18002a160  inc     rsi
0x18002a163  mov     r10d, 1
0x18002a169  mov     [rbp+160h+var_1D8], rsi
0x18002a16d  mov     r9, 0AAAAAAAAAAAAAAABh
0x18002a177  cmp     ebx, 5Eh ; '^'
0x18002a17a  jz      loc_18002A23B
0x18002a180  cmp     ebx, 27h ; '''
0x18002a183  jz      loc_18002A320
0x18002a189  cmp     ebx, 0B8h; switch 185 cases
0x18002a18f  ja      def_18002A1A3; jumptable 000000018002A1A3 default case, cases 39,89,93,94,123
0x18002a195  movsxd  rax, ebx
0x18002a198  mov     ecx, ds:(jpt_18002A1A3 - 180000000h)[r8+rax*4]
0x18002a1a0  add     rcx, r8
0x18002a1a3  jmp     rcx; switch jump
0x18002a1a5  movsxd  rcx, dword ptr [rdi+4]; jumptable 000000018002A1A3 cases 141,142
0x18002a1a9  mov     rax, [r15+78h]
0x18002a1ad  mov     [rsp+260h+var_1F8], 0
0x18002a1b6  mov     rbx, [rax+rcx*8]
0x18002a1ba  mov     rcx, rbx
0x18002a1bd  call    sqlite3VdbeCursorRestore
0x18002a1c2  mov     [rsp+260h+var_21C], eax
0x18002a1c6  mov     r14d, eax
0x18002a1c9  test    eax, eax
0x18002a1cb  jnz     loc_18002B40A
0x18002a1d1  cmp     [rbx+2], al
0x18002a1d4  jnz     loc_18002B0E7
0x18002a1da  xor     esi, esi
0x18002a1dc  lea     r8, [rsp+260h+var_1F8]
0x18002a1e1  mov     [rsp+260h+var_1F8], rsi
0x18002a1e6  mov     rcx, r13
0x18002a1e9  mov     rdx, [rbx+30h]
0x18002a1ed  call    sqlite3VdbeIdxRowid
0x18002a1f2  mov     [rsp+260h+var_21C], eax
0x18002a1f6  mov     r14d, eax
0x18002a1f9  test    eax, eax
0x18002a1fb  jnz     loc_18002B40A
0x18002a201  cmp     byte ptr [rdi], 8Dh
0x18002a204  jnz     loc_18002ACF2
0x18002a20a  mov     rax, [r15+78h]
0x18002a20e  movsxd  rcx, dword ptr [rdi+0Ch]
0x18002a212  mov     rdx, [rax+rcx*8]
0x18002a216  mov     [rdx+2], sil
0x18002a21a  mov     rax, [rsp+260h+var_1F8]
0x18002a21f  mov     [rdx+50h], rax
0x18002a223  mov     byte ptr [rdx+3], 1
0x18002a227  mov     [rdx+20h], esi
0x18002a22a  mov     rax, [rdi+10h]
0x18002a22e  mov     [rdx+10h], rax
0x18002a232  mov     [rdx+28h], rbx
0x18002a236  jmp     def_18002A1A3; jumptable 000000018002A1A3 default case, cases 39,89,93,94,123
0x18002a23b  xorps   xmm0, xmm0
0x18002a23e  xor     eax, eax
0x18002a240  mov     [rbp+160h+var_108], rax
0x18002a244  mov     [rsp+260h+var_1E8], eax
0x18002a248  mov     rax, [r15+78h]
0x18002a24c  movups  [rbp+160h+var_138], xmm0
0x18002a250  movups  [rbp+160h+var_128], xmm0
0x18002a254  movups  [rbp+160h+var_118], xmm0
0x18002a258  movsxd  rcx, dword ptr [rdi+4]
0x18002a25c  mov     r13d, [rdi+8]
0x18002a260  mov     rbx, [rax+rcx*8]
0x18002a264  mov     dword ptr [rsp+260h+var_208], r13d
0x18002a269  mov     r12, [rbx+58h]
0x18002a26d  mov     eax, [r15+2Ch]
0x18002a271  mov     [rsp+260h+var_1F8], r12
0x18002a276  cmp     [rbx+20h], eax
0x18002a279  jnz     loc_18002A3C1
0x18002a27f  mov     rcx, [rbx+30h]
0x18002a283  call    sqlite3BtreeEof
0x18002a288  test    eax, eax
0x18002a28a  jnz     loc_18002A3E9
0x18002a290  lea     rsi, [rbx+4Ah]
0x18002a294  movzx   eax, word ptr [rsi]
0x18002a297  cmp     eax, r13d
0x18002a29a  jbe     loc_18002A4AC
0x18002a2a0  mov     eax, r13d
0x18002a2a3  mov     edx, [rbx+rax*4+78h]
0x18002a2a7  mov     [rsp+260h+var_1E8], edx
0x18002a2ab  movsxd  rax, dword ptr [rdi+0Ch]
0x18002a2af  imul    rsi, rax, 38h ; '8'
0x18002a2b3  mov     eax, 9000h
0x18002a2b8  add     rsi, [rbp+160h+var_1D0]
0x18002a2bc  test    [rsi+14h], ax
0x18002a2c0  jnz     loc_18002F9E9
0x18002a2c6  lea     eax, [r13+1]
0x18002a2ca  mov     eax, [r12+rax*4]
0x18002a2ce  cmp     [rbx+6Ch], eax
0x18002a2d1  jb      loc_18002B599
0x18002a2d7  mov     eax, r13d
0x18002a2da  mov     r14d, [r12+rax*4]
0x18002a2de  add     r14, [rbx+60h]
0x18002a2e2  cmp     edx, 0Ch
0x18002a2e5  jnb     loc_18002A449
0x18002a2eb  mov     r8, rsi
0x18002a2ee  mov     rcx, r14
0x18002a2f1  call    sqlite3VdbeSerialGet
0x18002a2f6  mov     rsi, [rbp+160h+var_1D8]; jumptable 000000018002A1A3 default case, cases 39,89,93,94,123
0x18002a2fa  add     rdi, 18h
0x18002a2fe  mov     r15, qword ptr [rsp+260h+var_1F0]
0x18002a303  mov     r14d, [rsp+260h+var_21C]
0x18002a308  mov     r13, [rsp+260h+var_200]
0x18002a30d  mov     r12, [rbp+160h+var_1D0]
0x18002a311  movzx   edx, byte ptr [rsp+260h+var_218]
0x18002a316  mov     r11d, [rsp+260h+var_1E4]
0x18002a31b  jmp     loc_18002A156
0x18002a320  movsxd  rcx, dword ptr [rdi+4]
0x18002a324  mov     rax, [r15+78h]
0x18002a328  mov     edx, [rdi+0Ch]
0x18002a32b  mov     rbx, [rax+rcx*8]
0x18002a32f  mov     rcx, [rbx+30h]
0x18002a333  call    sqlite3BtreeNext
0x18002a338  mov     r14d, eax
0x18002a33b  mov     [rsp+260h+var_21C], eax
0x18002a33f  mov     dword ptr [rbx+20h], 0
0x18002a346  test    eax, eax
0x18002a348  jnz     loc_18002C396
0x18002a34e  mov     [rbx+2], al
0x18002a351  movzx   eax, word ptr [rdi+2]
0x18002a355  inc     dword ptr [r15+rax*4+0D4h]
0x18002a35d  mov     eax, [rdi+8]; jumptable 000000018002A1A3 case 9
0x18002a360  dec     eax
0x18002a362  cdqe
0x18002a364  lea     rcx, [rax+rax*2]
0x18002a368  mov     rax, [rsp+260h+var_210]
0x18002a36d  lea     rdi, [rax+rcx*8]
0x18002a371  mov     eax, [r13+198h]
0x18002a378  test    eax, eax
0x18002a37a  jnz     loc_18002FD96
0x18002a380  mov     r14, [rbp+160h+var_178]
0x18002a384  cmp     rsi, r14
0x18002a387  jb      def_18002A1A3; jumptable 000000018002A1A3 default case, cases 39,89,93,94,123
0x18002a38d  mov     rax, [r13+210h]
0x18002a394  test    rax, rax
0x18002a397  jz      def_18002A1A3; jumptable 000000018002A1A3 default case, cases 39,89,93,94,123
0x18002a39d  mov     rcx, [r13+218h]
0x18002a3a4  mov     ebx, [r13+220h]
0x18002a3ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3b0  test    eax, eax
0x18002a3b2  jnz     loc_18002FD8E
0x18002a3b8  add     r14, rbx
0x18002a3bb  mov     [rbp+160h+var_178], r14
0x18002a3bf  jmp     short loc_18002A384
0x18002a3c1  cmp     byte ptr [rbx+2], 0
0x18002a3c5  jnz     loc_18002C807
0x18002a3cb  cmp     byte ptr [rbx+3], 0
0x18002a3cf  mov     rsi, [rbx+30h]
0x18002a3d3  jnz     loc_18002A86B
0x18002a3d9  mov     rcx, rsi
0x18002a3dc  call    sqlite3BtreeEof
0x18002a3e1  test    eax, eax
0x18002a3e3  jz      loc_18002A88F
0x18002a3e9  mov     rcx, rbx
0x18002a3ec  call    sqlite3VdbeHandleMovedCursor
0x18002a3f1  mov     [rsp+260h+var_21C], eax
0x18002a3f5  mov     r14d, eax
0x18002a3f8  test    eax, eax
0x18002a3fa  jz      loc_18002A269
0x18002a400  jmp     loc_18002E0D2
0x18002a405  movsxd  rax, dword ptr [rdi+4]; jumptable 000000018002A1A3 case 96
0x18002a409  mov     rbx, [rdi+10h]
0x18002a40d  imul    rsi, rax, 38h ; '8'
0x18002a411  movzx   eax, byte ptr [rbx]
0x18002a414  add     rsi, r12
0x18002a417  movzx   r8d, dl
0x18002a41b  mov     rcx, rsi
0x18002a41e  movzx   edx, al
0x18002a421  call    applyAffinity
0x18002a426  cmp     byte ptr [rbx], 45h ; 'E'
0x18002a429  jz      loc_18002D87F
0x18002a42f  movzx   eax, byte ptr [rbx+1]
0x18002a433  inc     rbx
0x18002a436  test    al, al
0x18002a438  jz      def_18002A1A3; jumptable 000000018002A1A3 default case, cases 39,89,93,94,123
0x18002a43e  movzx   edx, byte ptr [rsp+260h+var_218]
0x18002a443  add     rsi, 38h ; '8'
0x18002a447  jmp     short loc_18002A417
0x18002a449  movzx   ecx, byte ptr [rsp+260h+var_218]
0x18002a44e  lea     ebx, [rdx-0Ch]
0x18002a451  shr     ebx, 1
0x18002a453  mov     [rsi+10h], ebx
0x18002a456  mov     [rsi+16h], cl
0x18002a459  lea     edx, [rbx+2]
0x18002a45c  cmp     [rsi+20h], edx
0x18002a45f  jl      loc_18002B086
0x18002a465  mov     rax, [rsi+28h]
0x18002a469  mov     [rsi+8], rax
0x18002a46d  mov     rcx, [rsi+8]; void *
0x18002a471  mov     r8, rbx; Size
0x18002a474  mov     rdx, r14; Src
0x18002a477  call    memcpy_0
0x18002a47c  mov     rax, [rsi+8]
0x18002a480  lea     rcx, cs:180000000h
0x18002a487  mov     byte ptr [rbx+rax], 0
0x18002a48b  mov     rax, [rsi+8]
0x18002a48f  mov     byte ptr [rax+rbx+1], 0
0x18002a494  mov     eax, [rsp+260h+var_1E8]
0x18002a498  and     eax, 1
0x18002a49b  movzx   eax, ds:rva word_1800A7334[rcx+rax*2]
0x18002a4a3  mov     [rsi+14h], ax
0x18002a4a7  jmp     def_18002A1A3; jumptable 000000018002A1A3 default case, cases 39,89,93,94,123
0x18002a4ac  mov     eax, [r12]
0x18002a4b0  lea     r15, [rbx+40h]
0x18002a4b4  cmp     [r15], eax
0x18002a4b7  jnb     loc_18002B0FC
0x18002a4bd  mov     rdx, [rbx+60h]
0x18002a4c1  mov     [rbp+160h+var_190], rdx
0x18002a4c5  test    rdx, rdx
0x18002a4c8  jz      loc_18002C0F6
0x18002a4ce  movzx   r14d, word ptr [rsi]
0x18002a4d2  mov     rax, [rsp+260h+var_1F8]
0x18002a4d7  mov     esi, [r15]
0x18002a4da  mov     rcx, rax
0x18002a4dd  add     rsi, rdx
0x18002a4e0  mov     r12d, [r12+r14*4]
0x18002a4e4  mov     r13d, [rax]
0x18002a4e7  add     r13, rdx
0x18002a4ea  nop     word ptr [rax+rax+00h]
0x18002a4f0  movzx   eax, byte ptr [rsi]
0x18002a4f3  mov     [rsp+260h+var_1E8], eax
0x18002a4f7  movsxd  r15, r14d
0x18002a4fa  mov     [rbx+r15*4+78h], eax
0x18002a4ff  mov     eax, [rsp+260h+var_1E8]
0x18002a503  cmp     eax, 80h
0x18002a508  jnb     loc_18002B107
0x18002a50e  movzx   eax, al
0x18002a511  lea     rdx, cs:180000000h
0x18002a518  inc     rsi
0x18002a51b  movzx   eax, byte ptr [rax+rdx+9EF00h]
0x18002a523  add     r12, rax
0x18002a526  inc     r14d
0x18002a529  movsxd  rax, r14d
0x18002a52c  mov     [rcx+rax*4], r12d
0x18002a530  cmp     r14d, dword ptr [rsp+260h+var_208]
0x18002a535  ja      short loc_18002A561
0x18002a537  cmp     rsi, r13
0x18002a53a  jb      short loc_18002A4F0
0x18002a53c  cmp     rsi, r13
0x18002a53f  ja      short loc_18002A549
0x18002a541  mov     eax, [rbx+68h]
0x18002a544  cmp     r12, rax
0x18002a547  jz      short loc_18002A56E
0x18002a549  mov     r12, [rsp+260h+var_1F8]
0x18002a54e  cmp     dword ptr [r12], 0
0x18002a553  jnz     loc_18002F9B7
0x18002a559  xor     r14d, r14d
  ... truncated ...
```
