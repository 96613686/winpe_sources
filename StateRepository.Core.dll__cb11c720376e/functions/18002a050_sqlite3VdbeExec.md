# sqlite3VdbeExec

- ea: `0x18002a050`
- end: `0x18003027c`
- name: `sqlite3VdbeExec`
- size: `25132`
- prototype: `__int64 __fastcall(_QWORD)`
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
  __int64 v77; // rax
  __int64 v78; // rcx
  __int64 v79; // rsi
  int v80; // r12d
  __int64 v81; // r14
  __int64 v82; // r13
  _BYTE *v83; // rsi
  _BYTE *v84; // r14
  _BYTE *v85; // rbx
  signed __int64 v86; // rsi
  __int64 v87; // rdx
  unsigned __int64 v88; // rcx
  __int64 v89; // rdx
  _DWORD *v90; // r14
  unsigned __int8 *Payload; // rcx
  int v92; // eax
  unsigned int v93; // eax
  int Varint32; // eax
  signed __int64 *v95; // rcx
  __int64 v96; // rax
  __int64 v97; // rsi
  _QWORD *v98; // rbx
  __int64 v99; // rcx
  __int64 *v100; // r10
  __int64 v101; // rax
  __int64 v102; // r9
  int v103; // r12d
  __int64 v104; // rcx
  __int64 v105; // r14
  __int64 *v106; // r10
  __int64 v107; // rax
  __int64 v108; // r13
  int v109; // r15d
  unsigned __int8 v110; // al
  __int64 v111; // rbx
  __int64 v112; // r8
  __int64 Cursor; // rax
  __int64 v114; // rsi
  __int64 v115; // rcx
  unsigned int v116; // eax
  char v117; // al
  int m; // ecx
  __int64 v119; // rax
  unsigned int v120; // r14d
  unsigned int v121; // esi
  int HasHint; // eax
  int v123; // esi
  char v124; // cl
  __int64 v125; // rax
  unsigned int v126; // eax
  __int64 v127; // rax
  __int64 v128; // rcx
  __int64 v129; // rsi
  __int64 v130; // rbx
  __int16 v131; // r8
  __int64 v132; // rcx
  __int64 v133; // r9
  __int64 v134; // rbx
  unsigned __int64 v135; // rax
  __int64 v136; // rcx
  unsigned __int64 v137; // rdx
  unsigned __int64 v138; // r8
  __int64 v139; // rcx
  __int64 v140; // rax
  __int64 v141; // rdx
  __int64 v142; // rcx
  __int64 v143; // rbx
  __int64 v144; // rdx
  int v145; // ebx
  int v146; // ecx
  int v147; // ebx
  __int64 v148; // rcx
  __int64 v149; // rcx
  __int64 v150; // rsi
  __int64 v151; // rbx
  __int64 v152; // rcx
  unsigned int v153; // eax
  __int64 v154; // rcx
  __int64 v155; // rdx
  signed __int64 v156; // rsi
  __int64 v157; // rcx
  __int64 v158; // rbx
  __int64 v159; // rdx
  __int64 v160; // r14
  __int64 v161; // rsi
  __int64 v162; // rbx
  char v163; // al
  unsigned __int8 v164; // cl
  char v165; // cl
  signed __int64 v166; // rbx
  char v167; // r12
  unsigned __int64 v168; // rdx
  __int64 v170; // rsi
  __int64 v171; // rbx
  __int64 v172; // rdx
  __int64 v173; // rcx
  __int64 v174; // r8
  unsigned int v175; // ecx
  int v176; // r8d
  __int64 v177; // rcx
  __int64 v178; // r8
  __int128 v179; // xmm1
  __int64 v180; // rcx
  __int64 v181; // rax
  __int64 v182; // rsi
  __int64 v183; // rcx
  int *v184; // r14
  unsigned int v185; // r12d
  int v186; // ecx
  __int16 v187; // r14
  int v188; // esi
  signed __int64 v189; // rbx
  __int64 v190; // rdx
  char v191; // al
  __int64 v192; // rbx
  __int64 v193; // rsi
  __int64 v194; // rdx
  const char *v195; // rax
  __int64 v196; // rcx
  int v197; // ecx
  __int64 v198; // r13
  signed __int64 v199; // r8
  int v200; // esi
  int v201; // r9d
  int v202; // ecx
  int v203; // r12d
  int v204; // edx
  __int64 v205; // rax
  __int64 v206; // r8
  __int64 v207; // r15
  __int64 v208; // rbx
  int v209; // r11d
  int v210; // esi
  __int64 v211; // r14
  __int64 v212; // rbx
  __int64 v213; // rcx
  __int64 v214; // rax
  __int64 v215; // rbx
  unsigned int v216; // eax
  __int64 v217; // rbx
  _DWORD *v218; // rbx
  __int64 v219; // r8
  _DWORD *v220; // r8
  __int64 v221; // rax
  __int64 v222; // rdx
  __int64 v223; // rdx
  const char *v224; // rax
  __int64 v225; // rax
  __int64 v226; // rcx
  __int64 v227; // rax
  __int64 v228; // rdx
  __int64 v229; // rbx
  __int64 v230; // rax
  __int64 v231; // r15
  __int64 v232; // rcx
  int v233; // ecx
  __int64 v234; // rcx
  __int64 v235; // rsi
  __int64 v236; // r14
  __int64 v237; // rbx
  __int64 v238; // rax
  unsigned __int8 v239; // cl
  __int64 v240; // rdx
  __int64 v241; // rcx
  __int64 v242; // rax
  __int64 v243; // rsi
  __int64 v244; // r14
  __int64 v245; // rax
  __int64 v246; // rbx
  __int64 v247; // rdx
  __int64 v248; // rsi
  __int64 v249; // rbx
  signed __int64 *v250; // r15
  __int64 *v251; // r12
  __int64 v252; // r13
  __int64 v253; // rbx
  __int64 v254; // rax
  __int64 v255; // rcx
  void *v256; // rcx
  signed __int64 v257; // rcx
  int v258; // eax
  unsigned __int8 v259; // cl
  __int64 v260; // rbx
  __int64 v261; // rax
  __int64 *v262; // r14
  __int64 v263; // rsi
  __int64 v264; // rax
  int v265; // esi
  int v266; // ecx
  char v267; // al
  int v268; // r14d
  __int64 v269; // rsi
  __int64 v270; // rbx
  unsigned __int8 v271; // al
  __int64 *v272; // rsi
  __int64 v273; // rcx
  __int64 v274; // rax
  _QWORD *v275; // rsi
  __int64 v276; // rbx
  __int64 v277; // rax
  __int64 v278; // rdx
  __int64 v279; // rdx
  __int64 v280; // rax
  __int64 v281; // rax
  signed __int64 v282; // rdx
  __int64 v283; // rax
  __int64 v284; // rdx
  __int64 v285; // rbx
  __int64 v286; // rcx
  __int64 v287; // rax
  __int64 v288; // rbx
  __int64 v289; // rcx
  int v290; // r12d
  __int64 v291; // rsi
  __int64 v292; // r15
  __int64 v293; // r14
  __int64 v294; // rdx
  __int64 v295; // rbx
  __int64 v296; // rbx
  int v297; // eax
  __int64 v298; // r9
  unsigned __int8 v299; // si
  signed __int64 v300; // r8
  __int64 v301; // rcx
  __int64 v302; // rcx
  __int64 v303; // r10
  __int64 v304; // rax
  __int64 v305; // rbx
  __int64 v306; // rdx
  _QWORD *v307; // rsi
  __int64 v308; // r14
  __int16 v309; // r8
  __int64 v310; // r9
  __int64 v311; // rdx
  int v312; // r8d
  __int64 v313; // rdx
  int v314; // ecx
  __int64 v315; // rcx
  __int64 v316; // rax
  __int64 v317; // rcx
  __int64 *v318; // rax
  __int64 v319; // rax
  __int64 v320; // rbx
  __int64 v321; // rcx
  __int64 v322; // rax
  __int64 v323; // rdx
  __int64 v324; // rcx
  int v325; // eax
  __int64 v326; // rax
  __int64 v327; // rcx
  __int64 v328; // rax
  __int64 v329; // rbx
  int v330; // esi
  __int64 v331; // rax
  bool v332; // sf
  __int64 v333; // rcx
  unsigned int v334; // eax
  __int64 v335; // rsi
  __int64 v336; // r15
  __int64 v337; // r14
  __int16 v338; // r8
  __int64 v339; // r15
  __int16 v340; // dx
  int v341; // edx
  __int64 v342; // r8
  __int64 v343; // rcx
  __int64 v344; // rbx
  char v345; // si
  int v346; // r14d
  const char *v347; // r8
  __int64 v348; // rax
  __int64 v349; // rcx
  __int64 v350; // rbx
  unsigned __int64 v351; // rdx
  int v352; // r8d
  int v353; // edx
  int v354; // esi
  int v355; // r14d
  __int64 v356; // rdx
  __int64 v357; // rcx
  __int64 v358; // rdx
  __int64 v359; // rcx
  _QWORD *v360; // rdx
  __int64 v361; // rdx
  __int64 v362; // rcx
  __int64 v363; // r13
  __int64 v364; // rbx
  __int64 v365; // r14
  __int16 v366; // r12
  __int16 v367; // si
  unsigned __int64 v368; // r15
  unsigned __int8 v369; // bl
  int v370; // edx
  int v371; // edx
  double v372; // xmm7_8
  __int128 v373; // xmm6
  __int64 v374; // rbx
  __int64 v375; // rax
  double v376; // xmm6_8
  __int64 v377; // rbx
  __int64 v378; // rbx
  __int64 v379; // r8
  __int64 v380; // rbx
  double v381; // xmm0_8
  __int64 v382; // rbx
  int v383; // ebx
  int v384; // ebx
  __int64 *v385; // rax
  __int64 v386; // r8
  __int64 v387; // rdx
  __int16 v388; // cx
  __int16 v389; // cx
  __int64 v390; // rbx
  __int64 v391; // rsi
  __int64 v392; // rbx
  __int64 v393; // r8
  unsigned __int64 v394; // rcx
  unsigned int v395; // edx
  int v396; // eax
  __int64 v397; // rax
  __int64 v398; // rdx
  __int64 v399; // rcx
  __int64 v400; // rcx
  int v401; // ecx
  __int64 v402; // rdx
  __int64 v403; // rsi
  __int64 v404; // r14
  __int64 v405; // rbx
  int v406; // r15d
  __int64 v407; // r12
  __int16 v408; // ax
  __int16 v409; // cx
  __int64 v410; // rax
  __int16 v411; // cx
  __int16 v412; // cx
  __int16 v413; // cx
  __int16 v414; // ax
  __int64 v415; // rax
  int v416; // eax
  __int64 v417; // rdx
  __int64 v418; // r8
  __int64 v419; // r9
  unsigned __int64 v420; // rcx
  unsigned __int64 v421; // rcx
  unsigned int v422; // r12d
  const void *v423; // r14
  __int64 v424; // rsi
  _QWORD *v425; // rbx
  __int64 v426; // rax
  _QWORD *v427; // r15
  unsigned int v428; // esi
  int v429; // r13d
  __int64 *v430; // rbx
  int v431; // r14d
  int v432; // ebx
  int k; // esi
  int v434; // esi
  unsigned int v435; // r14d
  _QWORD *j; // rcx
  __int64 v437; // rcx
  __int64 v438; // rdx
  __int64 v439; // rax
  __int64 v440; // rsi
  __int64 v441; // rbx
  __int64 v442; // rbx
  __int64 v443; // rbx
  __int64 v444; // rax
  int v445; // ecx
  __int64 v446; // rax
  __int64 v447; // rdx
  __int64 v448; // rcx
  int v449; // eax
  unsigned int v450; // eax
  __int64 v451; // rax
  __int64 v452; // rbx
  int n; // edx
  __int64 v454; // rdx
  __int64 v455; // rbx
  __int64 v456; // rax
  __int64 v457; // rcx
  __int64 v458; // rbx
  __int64 v459; // rax
  __int64 v460; // rcx
  __int64 v461; // rax
  int v462; // ebx
  __int64 v463; // rax
  __int64 v464; // r8
  __int64 v465; // rbx
  __int64 v466; // rcx
  __int64 v467; // r8
  __int64 v468; // rdx
  __int64 v469; // rax
  __int64 v470; // rsi
  __int64 v471; // rbx
  __int64 v472; // rdx
  __int64 *v473; // rcx
  __int64 v474; // rbx
  __int64 v475; // rcx
  const char *v476; // r8
  __int64 v477; // rdx
  __int64 v478; // rcx
  __int64 v479; // rcx
  __int64 v480; // rbx
  unsigned int v481; // esi
  __int64 v482; // rcx
  __int64 v483; // rdx
  __int64 v484; // rcx
  __int64 v485; // rdx
  __int64 v486; // rax
  signed __int64 v487; // rdx
  __int64 v488; // rcx
  __int64 v489; // rax
  __int64 v490; // rcx
  _QWORD *v491; // rbx
  __int64 v492; // r8
  __int64 v493; // r9
  __int64 v494; // r9
  __int64 v495; // rbx
  __int64 v496; // r8
  __int64 v497; // rbx
  __int64 v498; // rdx
  __int64 v499; // r8
  __int64 v500; // rsi
  int v501; // eax
  __int64 v502; // rdx
  int v503; // r9d
  __int64 v504; // rbx
  __int64 v505; // r9
  __int64 v506; // rax
  __int64 v507; // rsi
  __int64 v508; // rbx
  __int64 v509; // r14
  int v510; // esi
  __int64 v511; // rbx
  __int64 v512; // r14
  bool v513; // sf
  __int64 v514; // rax
  __int64 v515; // rcx
  __int64 v516; // rsi
  __int64 v517; // rbx
  __int64 v518; // r14
  __int64 v519; // rbx
  _QWORD *v520; // rsi
  __int64 v521; // rdx
  __int64 v522; // rcx
  __int64 v523; // rbx
  __int64 v524; // rax
  __int64 v525; // rcx
  __int64 v526; // rdx
  int v527; // r8d
  int v528; // edx
  unsigned int v529; // eax
  __int64 v530; // rbx
  __int64 v531; // r15
  __int64 v532; // r13
  __int64 v533; // r14
  unsigned int v534; // esi
  unsigned int v535; // ebx
  __int64 v536; // rax
  unsigned int v537; // eax
  unsigned int v538; // eax
  __int64 v539; // rax
  __int64 v540; // rax
  __int64 v541; // r9
  __int64 v542; // r8
  __int64 v543; // rbx
  __int64 v544; // rax
  unsigned int v545; // eax
  __int64 v546; // rdx
  __int64 v547; // rax
  __int64 v548; // rax
  __int64 *v549; // rbx
  __int64 v550; // rsi
  __int64 v551; // r9
  __int64 v552; // rsi
  _QWORD *v553; // rax
  _QWORD *v554; // rbx
  __int64 v555; // rax
  int v556; // r13d
  __int64 v557; // rdx
  __int64 v558; // r15
  __int64 v559; // r10
  __int64 v560; // rdx
  int *v561; // r10
  __int64 *v562; // r12
  __int64 **v563; // rbx
  int v564; // r9d
  __int64 v565; // r11
  __int64 *v566; // r14
  __int64 v567; // rsi
  __int64 v568; // rax
  __int64 v569; // rsi
  __int64 *v570; // r14
  __int64 v571; // r15
  __int16 v572; // ax
  unsigned int v573; // eax
  __int64 v574; // rdx
  const char *v575; // rax
  __int64 v576; // rsi
  __int64 **v577; // rcx
  __int64 *v578; // rbx
  __int64 v579; // r14
  int v580; // eax
  int v581; // r14d
  __int64 v582; // rbx
  __int64 v583; // rsi
  __int64 *v584; // rbx
  __int64 v585; // r10
  __int64 v586; // r9
  __int64 v587; // rdx
  char v588; // si
  __int64 v589; // r8
  __int64 v590; // rcx
  __int16 v591; // ax
  _QWORD *v592; // rbx
  unsigned int v593; // r8d
  __int64 v594; // r9
  __int64 v595; // rdx
  __int64 v596; // rdx
  __int64 v597; // rcx
  const char *v598; // r9
  __int64 v599; // rbx
  __int64 v600; // rbx
  int v601; // eax
  int v602; // eax
  __int64 v603; // rax
  const char *v604; // r8
  __int64 v605; // r8
  const char *v606; // r8
  const char *v607; // rdx
  unsigned int v608; // eax
  const char *v609; // rax
  unsigned int (__fastcall *v610)(__int64, unsigned __int64, unsigned __int64, unsigned __int64); // rax
  __int64 v611; // rcx
  __int64 v612; // [rsp+28h] [rbp-E0h]
  char v613; // [rsp+48h] [rbp-C0h]
  unsigned int Table; // [rsp+4Ch] [rbp-BCh]
  unsigned __int8 v615; // [rsp+50h] [rbp-B8h]
  signed __int64 v616; // [rsp+58h] [rbp-B0h]
  __int64 *v617; // [rsp+60h] [rbp-A8h] BYREF
  unsigned __int64 v618; // [rsp+68h] [rbp-A0h]
  __int64 v619; // [rsp+70h] [rbp-98h] BYREF
  __int64 *v620; // [rsp+78h] [rbp-90h]
  unsigned int v621; // [rsp+80h] [rbp-88h] BYREF
  int v622; // [rsp+84h] [rbp-84h]
  signed __int64 v623; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int64 v624; // [rsp+90h] [rbp-78h]
  __int64 v625; // [rsp+98h] [rbp-70h]
  __int128 v626; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v627; // [rsp+B0h] [rbp-58h]
  __int128 v628; // [rsp+C0h] [rbp-48h]
  int v629; // [rsp+D0h] [rbp-38h]
  __int64 v630; // [rsp+D8h] [rbp-30h]
  unsigned int v631; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v632; // [rsp+E8h] [rbp-20h] BYREF
  unsigned __int64 v633; // [rsp+F0h] [rbp-18h]
  _OWORD v634[2]; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v635; // [rsp+118h] [rbp+10h]
  __int64 v636; // [rsp+128h] [rbp+20h]
  __int128 v637; // [rsp+130h] [rbp+28h] BYREF
  __int128 v638; // [rsp+140h] [rbp+38h]
  __int128 v639; // [rsp+150h] [rbp+48h]
  __int64 v640; // [rsp+160h] [rbp+58h]
  _OWORD v641[2]; // [rsp+168h] [rbp+60h] BYREF
  __int128 v642; // [rsp+188h] [rbp+80h]
  __int64 v643; // [rsp+198h] [rbp+90h]
  char v644; // [rsp+1A8h] [rbp+A0h] BYREF
  __int16 v645; // [rsp+1A9h] [rbp+A1h]
  char v646; // [rsp+1ABh] [rbp+A3h]
  int v647; // [rsp+1ACh] [rbp+A4h]
  int v648; // [rsp+1F8h] [rbp+F0h]
  __int64 v649; // [rsp+1FCh] [rbp+F4h] BYREF

  v2 = (unsigned __int8 *)a1[17];
  v3 = (__int64 *)a1;
  v4 = 0;
  v5 = v2;
  v6 = a1[13];
  v7 = *a1;
  v620 = (__int64 *)a1;
  v616 = (signed __int64)v2;
  v618 = v7;
  v8 = *(unsigned __int8 *)(v7 + 100);
  v615 = *(_BYTE *)(v7 + 100);
  v613 = 0;
  v624 = 0;
  v625 = v6;
  if ( *((_DWORD *)a1 + 52) )
  {
    sqlite3VdbeEnter();
    v8 = v615;
    v2 = v5;
  }
  if ( *(_QWORD *)(v7 + 528) )
  {
    v8 = v615;
    v633 = (unsigned int)(*(_DWORD *)(v7 + 544) - *((_DWORD *)v3 + 57) % *(_DWORD *)(v7 + 544));
  }
  else
  {
    v633 = -1;
  }
  if ( *((_DWORD *)v3 + 13) == 7 )
    goto LABEL_393;
  *((_DWORD *)v3 + 13) = 0;
  v3[9] = 0;
  v9 = *(_DWORD *)(v7 + 408);
  *(_DWORD *)(v7 + 664) = 0;
  if ( v9 )
  {
LABEL_1222:
    updated = 9;
    goto LABEL_260;
  }
  IsValidNN = *((int *)v3 + 12);
  updated = 0;
  v12 = 0;
  Table = 0;
  v622 = 0;
  v629 = 0;
  v5 = &v2[24 * IsValidNN];
  while ( 2 )
  {
    v13 = *v5;
    v14 = 0x180000000uLL;
    v15 = v4 + 1;
    v624 = v15;
    v16 = 0xAAAAAAAAAAAAAAABuLL;
    if ( (_DWORD)v13 == 94 )
    {
      v1 = 0;
      v640 = 0;
      v621 = 0;
      v22 = v3[15];
      v637 = 0;
      v638 = 0;
      v639 = 0;
      v23 = *((_DWORD *)v5 + 2);
      v24 = *(_QWORD *)(v22 + 8LL * *((int *)v5 + 1));
      while ( 1 )
      {
        LODWORD(v617) = v23;
        while ( 1 )
        {
          v25 = *(_DWORD **)(v24 + 88);
          v26 = *((_DWORD *)v3 + 11);
          v619 = (__int64)v25;
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
            goto LABEL_850;
        }
        if ( *(_BYTE *)(v24 + 2) )
        {
          if ( *(_BYTE *)v24 != 3 || (v322 = *(int *)(v24 + 36), (int)v322 <= 0) )
          {
            v50 = v625 + 56LL * *((int *)v5 + 3);
LABEL_1166:
            IsValidNN = sqlite3VdbeMemSetNull(v50);
            goto LABEL_28;
          }
          v323 = v625;
          v90 = (_DWORD *)(v24 + 108);
          v324 = 56 * v322;
          v325 = *(_DWORD *)(56 * v322 + v625 + 16);
          *(_DWORD *)(v24 + 108) = v325;
          *(_DWORD *)(v24 + 104) = v325;
          Payload = *(unsigned __int8 **)(v324 + v323 + 8);
LABEL_121:
          *(_QWORD *)(v24 + 96) = Payload;
          v92 = *((_DWORD *)v3 + 11);
          v40 = (int *)(v24 + 64);
          *(_DWORD *)(v24 + 32) = v92;
          v93 = *Payload;
          *v25 = v93;
          if ( v93 >= 0x80 )
            Varint32 = (unsigned __int8)sqlite3GetVarint32(*(_QWORD *)(v24 + 96), v25);
          else
            Varint32 = 1;
          v27 = (unsigned __int16 *)(v24 + 74);
          *v40 = Varint32;
          *(_WORD *)(v24 + 74) = 0;
          if ( *v90 >= *v25 )
          {
            v41 = *(_QWORD *)(v24 + 96);
            goto LABEL_125;
          }
          *(_QWORD *)(v24 + 96) = 0;
          *v90 = 0;
          if ( *v25 > 0x18003u || *v25 > *(_DWORD *)(v24 + 104) )
          {
LABEL_1169:
            v166 = v616;
            v602 = *(_DWORD *)(v616 + 12);
            if ( v602 > 0 )
            {
              IsValidNN = 3LL * (v602 - 1);
              v5 = (unsigned __int8 *)(v616 + 8 * IsValidNN);
              goto LABEL_28;
            }
            v608 = sqlite3ReportError(11, 96621, "database corruption");
            v3 = v620;
            updated = v608;
            v7 = v618;
LABEL_261:
            v167 = v613;
            goto LABEL_1230;
          }
LABEL_21:
          if ( *v27 > v23 )
          {
            v28 = *(unsigned int *)(v24 + 4LL * v23 + 120);
            v621 = *(_DWORD *)(v24 + 4LL * v23 + 120);
            goto LABEL_23;
          }
          v40 = (int *)(v24 + 64);
          if ( *(_DWORD *)(v24 + 64) >= *v25 )
          {
            v28 = 0;
            v621 = 0;
            goto LABEL_68;
          }
          v41 = *(_QWORD *)(v24 + 96);
          v630 = v41;
          if ( v41 )
            goto LABEL_53;
          v1 = 0;
          v637 = 0;
          v638 = 0;
          v640 = 0;
          v639 = 0;
          Table = sqlite3VdbeMemFromBtreeZeroOffset(*(_QWORD *)(v24 + 48), (unsigned int)*v25, &v637);
          updated = Table;
          if ( !Table )
          {
            v41 = *((_QWORD *)&v637 + 1);
LABEL_125:
            v630 = v41;
LABEL_53:
            v42 = *v27;
            v43 = v619;
            v44 = (unsigned __int8 *)(v41 + (unsigned int)*v40);
            v45 = (unsigned int)v25[v42];
            v46 = v41 + *(unsigned int *)v619;
            while ( 1 )
            {
              v621 = *v44;
              *(_DWORD *)(v24 + 4LL * (int)v42 + 120) = v621;
              if ( v621 >= 0x80 )
              {
                v44 += (unsigned __int8)sqlite3GetVarint32(v44, &v621);
                *(_DWORD *)(v24 + 4LL * (int)v42 + 120) = v621;
                LODWORD(v47) = sqlite3VdbeSerialTypeLen(v621);
                v43 = v619;
                v47 = (unsigned int)v47;
              }
              else
              {
                ++v44;
                v47 = *((unsigned __int8 *)qword_18009EF00 + (unsigned __int8)v621);
              }
              v45 += v47;
              LODWORD(v42) = v42 + 1;
              *(_DWORD *)(v43 + 4LL * (int)v42) = v45;
              if ( (unsigned int)v42 > (unsigned int)v617 )
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
              v25 = (_DWORD *)v619;
            }
            else
            {
              if ( v45 <= *(unsigned int *)(v24 + 104) )
                goto LABEL_64;
LABEL_60:
              v25 = (_DWORD *)v619;
              if ( *(_DWORD *)v619 )
              {
                if ( !*(_QWORD *)(v24 + 96) )
                  sqlite3VdbeMemRelease(&v637);
                goto LABEL_1169;
              }
              LOWORD(v42) = 0;
              LODWORD(v44) = v46;
            }
            v48 = (_DWORD)v44 - v630;
            v49 = *(_QWORD *)(v24 + 96) == 0;
            *(_WORD *)(v24 + 74) = v42;
            *(_DWORD *)(v24 + 64) = v48;
            if ( v49 )
              sqlite3VdbeMemRelease(&v637);
            v28 = v621;
            v23 = (unsigned int)v617;
LABEL_68:
            if ( *(unsigned __int16 *)(v24 + 74) <= v23 )
            {
              v50 = v625 + 56LL * *((int *)v5 + 3);
              if ( v5[1] == 0xF6 )
              {
                IsValidNN = sqlite3VdbeMemShallowCopy(v50, *((_QWORD *)v5 + 2), 0x2000);
                goto LABEL_28;
              }
              goto LABEL_1166;
            }
LABEL_23:
            v29 = v625 + 56LL * *((int *)v5 + 3);
            if ( (*(_WORD *)(v29 + 20) & 0x9000) != 0 )
            {
              sqlite3VdbeMemSetNull(v625 + 56LL * *((int *)v5 + 3));
              v28 = v621;
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
              *(_BYTE *)(v29 + 22) = v615;
              v39 = (unsigned int)(v38 + 2);
              if ( *(_DWORD *)(v29 + 32) >= (int)v39 )
              {
                *(_QWORD *)(v29 + 8) = *(_QWORD *)(v29 + 40);
LABEL_50:
                memcpy_0(*(void **)(v29 + 8), v30, v38);
                *(_BYTE *)(v38 + *(_QWORD *)(v29 + 8)) = 0;
                *(_BYTE *)(*(_QWORD *)(v29 + 8) + v38 + 1) = 0;
                IsValidNN = (unsigned __int16)word_1800A7334[v621 & 1];
                *(_WORD *)(v29 + 20) = IsValidNN;
                goto LABEL_28;
              }
              v7 = v618;
              if ( (int)v38 <= *(_DWORD *)(v618 + 136) )
              {
                *(_WORD *)(v29 + 20) = 1;
                if ( !(unsigned int)sqlite3VdbeMemGrow(v29, v39, 0) )
                  goto LABEL_50;
                v3 = v620;
LABEL_393:
                sqlite3OomFault(v7);
                sqlite3VdbeError(v3, "out of memory");
                updated = 7;
                goto LABEL_260;
              }
              v3 = v620;
LABEL_285:
              sqlite3VdbeError(v3, "string or blob too big");
              updated = 18;
              goto LABEL_260;
            }
            *(_BYTE *)(v29 + 22) = v615;
            v190 = v621;
            v191 = v5[2] & 0xC0;
            if ( !v191 || v191 != (char)0x80 && (v621 < 0xC || (v621 & 1) != 0 && v191 != -64) )
            {
              if ( (unsigned int)sqlite3VdbeSerialTypeLen(v621) )
              {
                v3 = v620;
                IsValidNN = vdbeColumnFromOverflow(v24, v23, v621, v25[v23], *((_DWORD *)v620 + 11), v629, v29);
                Table = IsValidNN;
                updated = IsValidNN;
                if ( !(_DWORD)IsValidNN )
                  goto LABEL_28;
                if ( (_DWORD)IsValidNN != 7 )
                {
                  if ( (_DWORD)IsValidNN != 18 )
                    goto LABEL_850;
                  goto LABEL_284;
                }
LABEL_392:
                v7 = v618;
                goto LABEL_393;
              }
              v190 = v621;
            }
            IsValidNN = sqlite3VdbeSerialGet(&qword_18009E630, v190, v29);
            goto LABEL_28;
          }
LABEL_849:
          v3 = v620;
          goto LABEL_850;
        }
        v35 = *(_QWORD *)(v24 + 48);
        if ( !*(_BYTE *)(v24 + 3) )
          break;
        v89 = *(_QWORD *)(v24 + 16);
        if ( !v89 || (v601 = *(_DWORD *)(v89 + 4LL * (v23 + 1))) == 0 )
        {
          Table = sqlite3VdbeFinishMoveto(v24, v89, v14, v16);
          updated = Table;
          if ( !Table )
          {
LABEL_120:
            getCellInfo(v35);
            v90 = (_DWORD *)(v24 + 108);
            *(_DWORD *)(v24 + 104) = *(_DWORD *)(v35 + 64);
            Payload = (unsigned __int8 *)fetchPayload(v35, v24 + 108);
            goto LABEL_121;
          }
LABEL_850:
          v7 = v618;
          goto LABEL_260;
        }
        v24 = *(_QWORD *)(v24 + 40);
        v23 = v601 - 1;
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
        v5 = (unsigned __int8 *)(v616 + 24LL * (*((_DWORD *)v5 + 2) - 1));
      }
LABEL_33:
      IsValidNN = *(unsigned int *)(v7 + 408);
      if ( !(_DWORD)IsValidNN )
      {
        for ( i = v633; ; v633 = i )
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
        v633 = -1;
      }
      goto LABEL_1222;
    }
    v17 = IsValidNN;
    IsValidNN = (int)v13;
    switch ( (int)v13 )
    {
      case 0:
        v422 = *((_DWORD *)v5 + 1);
        v423 = (const void *)*((_QWORD *)v5 + 2);
        if ( !v422 )
        {
          if ( *(int *)(v7 + 224) <= 0 )
          {
            v424 = (int)sqlite3Strlen30(*((_QWORD *)v5 + 2));
            Table = sqlite3VtabSavepoint(v7, 0, (unsigned int)(*(_DWORD *)(v7 + 752) + *(_DWORD *)(v7 + 756)));
            if ( !Table )
            {
              IsValidNN = sqlite3DbMallocRawNN(v7, v424 + 33);
              v425 = (_QWORD *)IsValidNN;
              if ( IsValidNN )
              {
                *(_QWORD *)IsValidNN = IsValidNN + 32;
                memcpy_0((void *)(IsValidNN + 32), v423, (int)v424 + 1);
                if ( *(_BYTE *)(v7 + 101) )
                {
                  *(_BYTE *)(v7 + 101) = 0;
                  *(_BYTE *)(v7 + 109) = 1;
                }
                else
                {
                  ++*(_DWORD *)(v7 + 752);
                }
                v425[3] = *(_QWORD *)(v7 + 736);
                v426 = *(_QWORD *)(v7 + 760);
                *(_QWORD *)(v7 + 736) = v425;
                v425[1] = v426;
                IsValidNN = *(_QWORD *)(v7 + 768);
                v425[2] = IsValidNN;
              }
              goto LABEL_814;
            }
LABEL_259:
            updated = Table;
            goto LABEL_260;
          }
          sqlite3VdbeError(v3, "cannot open savepoint - SQL statements in progress");
LABEL_1188:
          updated = 5;
          goto LABEL_260;
        }
        v427 = *(_QWORD **)(v7 + 736);
        v428 = 0;
        LODWORD(v617) = 0;
        if ( !v427 )
        {
LABEL_1191:
          v3 = v620;
          sqlite3VdbeError(v620, "no such savepoint: %s", (const char *)v423);
          updated = 1;
          goto LABEL_260;
        }
        while ( (unsigned int)sqlite3StrICmp(*v427, v423) )
        {
          v427 = (_QWORD *)v427[3];
          if ( !v427 )
            goto LABEL_1191;
          LODWORD(v617) = ++v428;
        }
        if ( *(int *)(v7 + 224) > 0 && v422 == 1 )
        {
          v3 = v620;
          sqlite3VdbeError(v620, "cannot release savepoint - SQL statements in progress");
          goto LABEL_1188;
        }
        if ( v427[3] || !*(_BYTE *)(v7 + 109) )
        {
          v429 = 0;
        }
        else
        {
          v429 = 1;
          if ( v422 == 1 )
          {
            v430 = v620;
            updated = sqlite3VdbeCheckFk(v620, 1);
            if ( updated )
            {
              v7 = v618;
              v3 = v430;
LABEL_418:
              v166 = v616;
LABEL_419:
              v167 = v613;
              goto LABEL_420;
            }
            *(_BYTE *)(v618 + 101) = 1;
            if ( (unsigned int)sqlite3VdbeHalt(v430) == 5 )
            {
              v3 = v620;
              v166 = v616;
              v7 = v618;
              updated = 5;
              *((_DWORD *)v620 + 12) = -1431655765 * ((__int64)&v5[-v616] >> 3);
              *(_BYTE *)(v7 + 101) = 0;
              *((_DWORD *)v3 + 13) = 5;
              goto LABEL_419;
            }
            updated = *((_DWORD *)v430 + 13);
            Table = updated;
            if ( updated )
            {
              v7 = v618;
              v3 = v430;
              *(_BYTE *)(v618 + 101) = 0;
              goto LABEL_260;
            }
            v16 = v618;
            *(_BYTE *)(v618 + 109) = 0;
LABEL_804:
            for ( j = *(_QWORD **)(v16 + 736); j != v427; j = *(_QWORD **)(v16 + 736) )
            {
              *(_QWORD *)(v16 + 736) = j[3];
              sqlite3DbFree(v16, j);
              v16 = v618;
              --*(_DWORD *)(v618 + 752);
            }
            if ( v422 == 1 )
            {
              *(_QWORD *)(v16 + 736) = v427[3];
              IsValidNN = sqlite3DbFree(v16, v427);
              v49 = v429 == 0;
              v7 = v618;
              if ( v49 )
              {
                --*(_DWORD *)(v618 + 752);
                goto LABEL_811;
              }
            }
            else
            {
              v49 = v429 == 0;
              v7 = v618;
              *(_QWORD *)(v16 + 760) = v427[1];
              IsValidNN = v427[2];
              *(_QWORD *)(v16 + 768) = IsValidNN;
              if ( v49 || v422 == 2 )
              {
LABEL_811:
                IsValidNN = sqlite3VtabSavepoint(v7, v422, v428);
                v3 = v620;
                updated = IsValidNN;
                Table = IsValidNN;
                if ( (_DWORD)IsValidNN )
                  goto LABEL_260;
                goto LABEL_814;
              }
            }
            v3 = v620;
LABEL_814:
            if ( *((_BYTE *)v3 + 199) != 3 )
              goto LABEL_28;
            updated = 101;
            goto LABEL_418;
          }
        }
        v16 = v618;
        v431 = *(_DWORD *)(v618 + 752);
        if ( v422 == 2 )
        {
          v432 = *(_DWORD *)(v618 + 44) & 1;
          for ( k = 0; k < *(_DWORD *)(v16 + 40); ++k )
          {
            Table = sqlite3BtreeTripAllCursors(*(_QWORD *)(32LL * k + *(_QWORD *)(v16 + 32) + 8), 516, v432 ^ 1u);
            if ( Table )
            {
LABEL_1229:
              v3 = v620;
              updated = Table;
              v7 = v618;
              goto LABEL_260;
            }
            v16 = v618;
          }
          v428 = (unsigned int)v617;
        }
        else
        {
          v432 = 0;
        }
        LODWORD(v617) = v431 + ~v428;
        v434 = 0;
        v435 = (unsigned int)v617;
        while ( v434 < *(_DWORD *)(v16 + 40) )
        {
          Table = sqlite3BtreeSavepoint(*(_QWORD *)(32LL * v434 + *(_QWORD *)(v16 + 32) + 8), v422, v435);
          if ( Table )
            goto LABEL_1229;
          v16 = v618;
          ++v434;
        }
        if ( v432 )
        {
          sqlite3ExpirePreparedStatements(v16, 0);
          sqlite3ResetAllSchemasOfConnection(v618);
          v16 = v618;
          *(_DWORD *)(v618 + 44) |= 1u;
        }
        updated = Table;
        if ( Table )
          goto LABEL_849;
        v428 = (unsigned int)v617;
        goto LABEL_804;
      case 1:
        v265 = *((_DWORD *)v5 + 1);
        v266 = *((_DWORD *)v5 + 2);
        if ( v265 == *(unsigned __int8 *)(v7 + 101) )
        {
          if ( v265 )
          {
            v607 = "cannot rollback - no transaction is active";
            if ( !v266 )
              v607 = "cannot commit - no transaction is active";
            sqlite3VdbeError(v3, v607, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
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
        if ( v266 )
        {
          sqlite3RollbackAll(v7, 516, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
          v267 = 1;
        }
        else
        {
          if ( v265 && *(int *)(v7 + 224) > 0 )
          {
            sqlite3VdbeError(v3, "cannot commit transaction - SQL statements in progress");
            goto LABEL_1188;
          }
          updated = sqlite3VdbeCheckFk(v3, 1);
          if ( updated )
            goto LABEL_418;
          v267 = v265;
        }
        *(_BYTE *)(v7 + 101) = v267;
        if ( (unsigned int)sqlite3VdbeHalt(v3) == 5 )
        {
          v166 = v616;
          updated = 5;
          *((_DWORD *)v3 + 12) = -1431655765 * ((__int64)&v5[-v616] >> 3);
          *(_BYTE *)(v7 + 101) = 1 - v265;
          *((_DWORD *)v3 + 13) = 5;
          goto LABEL_419;
        }
        sqlite3CloseSavepoints(v7);
        updated = 101;
        if ( *((_DWORD *)v3 + 13) )
          updated = 1;
        goto LABEL_418;
      case 2:
        v159 = *((unsigned int *)v5 + 2);
        LODWORD(v617) = 0;
        if ( (_DWORD)v159 )
        {
          IsValidNN = *(_QWORD *)(v7 + 48);
          if ( (IsValidNN & 0x200100000LL) != 0 )
          {
            updated = 8;
            if ( (IsValidNN & 0x100000) == 0 )
              updated = 11;
LABEL_260:
            v166 = v616;
            goto LABEL_261;
          }
        }
        v160 = *(_QWORD *)(v7 + 32);
        v161 = 32LL * *((int *)v5 + 1);
        v162 = *(_QWORD *)(v161 + v160 + 8);
        if ( v162 )
        {
          IsValidNN = sqlite3BtreeBeginTrans(*(_QWORD *)(v161 + v160 + 8), v159, &v617);
          Table = IsValidNN;
          if ( (_DWORD)IsValidNN )
          {
            updated = IsValidNN;
            v166 = v616;
            v167 = v613;
            if ( (_BYTE)IsValidNN != 5 )
              goto LABEL_1230;
            *((_DWORD *)v3 + 13) = IsValidNN;
            *((_DWORD *)v3 + 12) = -1431655765 * ((__int64)&v5[-v616] >> 3);
            goto LABEL_420;
          }
          if ( (v3[25] & 0x20) == 0 || !*((_DWORD *)v5 + 2) || *(_BYTE *)(v7 + 101) && *(int *)(v7 + 220) <= 1 )
            goto LABEL_205;
          v176 = *((_DWORD *)v3 + 16);
          if ( !v176 )
          {
            v176 = ++*(_DWORD *)(v7 + 756) + *(_DWORD *)(v7 + 752);
            *((_DWORD *)v3 + 16) = v176;
          }
          Table = sqlite3VtabSavepoint(v7, 0, (unsigned int)(v176 - 1));
          v175 = Table;
          if ( !Table )
          {
            v175 = sqlite3BtreeBeginStmt(v162, *((unsigned int *)v3 + 16));
            Table = v175;
          }
          v3[11] = *(_QWORD *)(v7 + 760);
          IsValidNN = *(_QWORD *)(v7 + 768);
          v3[12] = IsValidNN;
        }
        else
        {
          v175 = Table;
        }
        if ( v175 )
          goto LABEL_259;
LABEL_205:
        if ( *((_WORD *)v5 + 1) )
        {
          if ( (_DWORD)v617 != *((_DWORD *)v5 + 3)
            || (IsValidNN = *((unsigned int *)v5 + 4),
                *(_DWORD *)(*(_QWORD *)(v161 + v160 + 24) + 4LL) != (_DWORD)IsValidNN) )
          {
            sqlite3DbFree(v7, v3[21]);
            v3[21] = sqlite3DbStrDup(v7, "database schema has changed");
            if ( **(_DWORD **)(32LL * *((int *)v5 + 1) + *(_QWORD *)(v7 + 32) + 24) != (_DWORD)v617 )
              sqlite3ResetOneSchema(v7);
            updated = 17;
            *((_DWORD *)v3 + 50) = v3[25] & 0xFFFFFFEC | 1;
            goto LABEL_260;
          }
        }
        goto LABEL_28;
      case 3:
        v527 = *((_DWORD *)v5 + 2);
        v528 = *((_DWORD *)v5 + 1);
        v648 = 0;
        v649 = -1;
        v529 = sqlite3Checkpoint(v7, v528, v527, (unsigned int)&v649, (__int64)&v649 + 4);
        Table = v529;
        updated = v529;
        if ( !v529 )
          goto LABEL_1046;
        if ( v529 != 5 )
          goto LABEL_260;
        Table = 0;
        v648 = 1;
LABEL_1046:
        v530 = v6 + 56LL * *((int *)v5 + 3);
        sqlite3VdbeMemSetInt64(v530);
        sqlite3VdbeMemSetInt64(v530 + 56);
        IsValidNN = sqlite3VdbeMemSetInt64(v530 + 112);
        goto LABEL_28;
      case 4:
        v531 = out2Prerelease(v3, v5);
        v532 = *(_QWORD *)(32LL * *((int *)v5 + 1) + *(_QWORD *)(v7 + 32) + 8);
        v533 = **(_QWORD **)(v532 + 8);
        v534 = *(unsigned __int8 *)(v533 + 9);
        v535 = v534;
        if ( *((_DWORD *)v5 + 3) != -1 )
          v535 = *((_DWORD *)v5 + 3);
        if ( !(unsigned int)sqlite3PagerOkToChangeJournalMode(v533) )
          v535 = v534;
        v536 = sqlite3PagerFilename(v533, 1);
        if ( v535 == 5 && (!(unsigned int)sqlite3Strlen30(v536) || !(unsigned int)sqlite3PagerWalSupported(v533)) )
        {
          v535 = v534;
LABEL_1055:
          v537 = Table;
          goto LABEL_1056;
        }
        if ( v535 == v534 || v534 != 5 && v535 != 5 )
          goto LABEL_1055;
        if ( !*(_BYTE *)(v618 + 101) || *(int *)(v618 + 220) > 1 )
        {
          v3 = v620;
          v606 = "into";
          if ( v535 != 5 )
            v606 = "out of";
          updated = 1;
          sqlite3VdbeError(v620, "cannot change %s wal mode from within a transaction", v606);
          v7 = v618;
          goto LABEL_260;
        }
        if ( v534 == 5 )
        {
          Table = sqlite3PagerCloseWal(v533, v618);
          if ( Table )
            goto LABEL_1057;
          sqlite3PagerSetJournalMode(v533, v535);
        }
        else
        {
          if ( v534 == 4 )
            sqlite3PagerSetJournalMode(v533, 2);
          if ( Table )
            goto LABEL_1057;
        }
        v537 = sqlite3BtreeSetVersion(v532, (unsigned int)(v535 == 5) + 1);
        Table = v537;
LABEL_1056:
        if ( !v537 )
          goto LABEL_1058;
LABEL_1057:
        v535 = v534;
LABEL_1058:
        v538 = sqlite3PagerSetJournalMode(v533, v535);
        *(_WORD *)(v531 + 20) = 8706;
        v539 = sqlite3JournalModename(v538);
        *(_QWORD *)(v531 + 8) = v539;
        *(_DWORD *)(v531 + 16) = sqlite3Strlen30(v539);
        *(_BYTE *)(v531 + 22) = 1;
        IsValidNN = sqlite3VdbeChangeEncoding(v531, v615);
        updated = Table;
        if ( Table )
          goto LABEL_849;
        goto LABEL_28;
      case 5:
        v540 = *((int *)v5 + 2);
        if ( (_DWORD)v540 )
          v541 = v6 + 56 * v540;
        else
          v541 = 0;
        IsValidNN = sqlite3RunVacuum(v3 + 21, v7, *((unsigned int *)v5 + 1), v541);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( !(_DWORD)IsValidNN )
          goto LABEL_28;
        goto LABEL_260;
      case 6:
        v556 = 0;
        v557 = 56LL * *((int *)v5 + 3);
        v558 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1));
        v559 = v557 + 56;
        v560 = *(unsigned int *)(v557 + v6);
        v561 = (int *)(v6 + v559);
        v562 = v620;
        v563 = *(__int64 ***)(v558 + 48);
        v564 = *v561;
        v565 = v620[14];
        v566 = *v563;
        v567 = **v563;
        if ( *v561 > 0 )
        {
          do
          {
            v568 = (unsigned int)v556++;
            *(_QWORD *)(v565 + 8 * v568) = &v561[14 * v556];
          }
          while ( v556 < v564 );
        }
        Table = (*(__int64 (__fastcall **)(__int64 **, __int64, _QWORD))(v567 + 64))(v563, v560, *((_QWORD *)v5 + 2));
        sqlite3VtabImportErrmsg(v562, v566);
        updated = Table;
        if ( Table )
        {
          v7 = v618;
          v3 = v562;
          goto LABEL_260;
        }
        IsValidNN = (*(__int64 (__fastcall **)(__int64 **))(v567 + 80))(v563);
        *(_BYTE *)(v558 + 2) = 0;
        if ( (_DWORD)IsValidNN )
          goto LABEL_77;
        goto LABEL_28;
      case 7:
        v49 = *(_BYTE *)(v7 + 103) == 0;
        v623 = 0;
        if ( !v49 )
          goto LABEL_393;
        IsValidNN = *((_QWORD *)v5 + 2);
        v584 = *(__int64 **)(IsValidNN + 16);
        if ( !v584 )
          goto LABEL_1206;
        v585 = *v584;
        if ( !*v584 )
          goto LABEL_1206;
        if ( !*(_QWORD *)(v585 + 104) )
          goto LABEL_28;
        v586 = 0;
        v587 = *((unsigned int *)v5 + 2);
        v588 = *(_BYTE *)(v7 + 108);
        v589 = v3[14];
        v590 = v6 + 56LL * *((int *)v5 + 3);
        if ( (int)v587 > 0 )
        {
          do
          {
            *(_QWORD *)(v589 + 8 * v586) = v590;
            v590 += 56;
            v586 = (unsigned int)(v586 + 1);
          }
          while ( (int)v586 < (int)v587 );
        }
        *(_BYTE *)(v7 + 108) = v5[2];
        Table = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, signed __int64 *))(v585 + 104))(
                  v584,
                  v587,
                  v589,
                  &v623);
        *(_BYTE *)(v7 + 108) = v588;
        updated = Table;
        IsValidNN = sqlite3VtabImportErrmsg(v3, v584);
        if ( Table )
        {
          if ( (_BYTE)Table == 19 )
          {
            IsValidNN = *((_QWORD *)v5 + 2);
            if ( *(_BYTE *)(IsValidNN + 28) )
            {
              v591 = *((_WORD *)v5 + 1);
              if ( v591 == 4 )
              {
                IsValidNN = 0;
                Table = 0;
                goto LABEL_28;
              }
              if ( v591 == 5 )
                LOBYTE(v591) = 2;
              *((_BYTE *)v3 + 196) = v591;
              goto LABEL_260;
            }
          }
        }
        else if ( *((_DWORD *)v5 + 1) )
        {
          IsValidNN = v623;
          *(_QWORD *)(v7 + 56) = v623;
        }
        ++v3[7];
        if ( Table )
          goto LABEL_260;
        goto LABEL_28;
      case 8:
      case 184:
        v117 = *(_BYTE *)(v7 + 110);
        if ( (v117 & 0x41) != 0 && *((_BYTE *)v3 + 197) != 0xFE )
        {
          v598 = (const char *)*((_QWORD *)v5 + 2);
          if ( v598 || (v598 = (const char *)v3[31]) != 0 )
          {
            if ( (v117 & 0x40) != 0 )
            {
              v599 = sqlite3VdbeExpandSql(v3, v598, 0x180000000uLL);
              (*(void (__fastcall **)(_QWORD, __int64))(v7 + 248))(*(_QWORD *)(v7 + 256), v599);
              sqlite3_free(v599);
            }
            else if ( *(int *)(v7 + 228) <= 1 )
            {
              (*(void (__fastcall **)(__int64, _QWORD, __int64 *))(v7 + 248))(1, *(_QWORD *)(v7 + 256), v3);
            }
            else
            {
              v600 = sqlite3MPrintf(v7, "-- %s", v598);
              (*(void (__fastcall **)(__int64, _QWORD, __int64 *, __int64))(v7 + 248))(
                1,
                *(_QWORD *)(v7 + 256),
                v3,
                v600);
              sqlite3DbFree(v7, v600);
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
          v119 = v3[17];
          if ( *(_BYTE *)(v119 + 24LL * m) == 15 )
            *(_DWORD *)(v119 + 24LL * m + 4) = 0;
        }
        LODWORD(IsValidNN) = 0;
LABEL_152:
        *((_DWORD *)v5 + 1) = IsValidNN + 1;
        ++*((_DWORD *)v3 + 59);
        goto LABEL_77;
      case 9:
        goto LABEL_32;
      case 10:
        v226 = 56LL * *((int *)v5 + 1);
        *(_WORD *)(v226 + v6 + 20) = 4;
        *(_QWORD *)(v226 + v6) = (int)(-1431655765 * ((__int64)&v5[-v616] >> 3));
        goto LABEL_32;
      case 11:
        v234 = 56LL * *((int *)v5 + 1);
        IsValidNN = *((_DWORD *)v5 + 3) - 1;
        *(_QWORD *)(v234 + v6) = IsValidNN;
        *(_WORD *)(v234 + v6 + 20) = 4;
        if ( !*((_DWORD *)v5 + 2) )
          goto LABEL_28;
        goto LABEL_77;
      case 12:
        v172 = 56LL * *((int *)v5 + 1);
        v173 = *(int *)(v172 + v6);
        IsValidNN = (int)(-1431655765 * ((__int64)&v5[-v616] >> 3));
        *(_WORD *)(v172 + v6 + 20) = 4;
        *(_QWORD *)(v172 + v6) = IsValidNN;
        v5 = (unsigned __int8 *)(v616 + 24 * v173);
        goto LABEL_28;
      case 13:
        v378 = v6 + 56LL * *((int *)v5 + 1);
        IsValidNN = *(unsigned __int16 *)(v378 + 20);
        if ( (IsValidNN & 4) != 0
          || (v379 = (unsigned __int8)v8,
              LOBYTE(v8) = 67,
              applyAffinity(v6 + 56LL * *((int *)v5 + 1), v8, v379, 0xAAAAAAAAAAAAAAABuLL),
              IsValidNN = *(unsigned __int16 *)(v378 + 20),
              (IsValidNN & 4) != 0) )
        {
          LOWORD(IsValidNN) = IsValidNN & 0xF240 | 4;
          *(_WORD *)(v378 + 20) = IsValidNN;
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
        v174 = v3[33];
        if ( !v174 )
        {
          if ( *(_DWORD *)(v3[17] + 4) == *((_DWORD *)v5 + 1) )
            goto LABEL_77;
          goto LABEL_249;
        }
        v393 = *(_QWORD *)(v174 + 40);
        v394 = (unsigned __int64)(-1431655765 * (unsigned int)((__int64)&v5[-v3[17]] >> 3)) >> 3;
        v395 = (-85 * (unsigned __int8)((__int64)&v5[-v3[17]] >> 3)) & 7;
        v396 = *(unsigned __int8 *)(v394 + v393);
        if ( !_bittest(&v396, v395) )
        {
          *(_BYTE *)(v394 + v393) = v396 | (1 << v395);
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
        v397 = *((int *)v5 + 1);
        if ( (int)v397 < 0 )
        {
          LOBYTE(v401) = *((_BYTE *)qword_18009EC50 + (*(_WORD *)(56LL * *((int *)v5 + 3) + v6 + 20) & 0x3F));
          goto LABEL_704;
        }
        v398 = *((int *)v5 + 3);
        v399 = *(_QWORD *)(v3[15] + 8 * v397);
        if ( (int)v398 >= *(unsigned __int16 *)(v399 + 74) )
        {
          v401 = *((_DWORD *)v5 + 4);
LABEL_704:
          IsValidNN = 1;
          LOWORD(IsValidNN) = 1 << (v401 - 1);
          goto LABEL_705;
        }
        v400 = *(unsigned int *)(v399 + 4 * v398 + 120);
        if ( (unsigned int)v400 < 0xC )
        {
          IsValidNN = *((unsigned __int8 *)&qword_1800A6560[1] + v400);
        }
        else
        {
          IsValidNN = 4;
          if ( (v400 & 1) == 0 )
            LOWORD(IsValidNN) = 8;
        }
LABEL_705:
        if ( ((unsigned __int16)IsValidNN & *((_WORD *)v5 + 1)) == 0 )
          goto LABEL_28;
        goto LABEL_77;
      case 19:
        v390 = v6 + 56LL * *((int *)v5 + 2);
        if ( (*(_BYTE *)(v6 + 56LL * *((int *)v5 + 1) + 20) & 1) != 0 )
          goto LABEL_1112;
        sqlite3VdbeBooleanValue(v6 + 56LL * *((int *)v5 + 1), 0);
        IsValidNN = sqlite3VdbeMemSetInt64(v390);
        goto LABEL_28;
      case 20:
        IsValidNN = v3[15];
        v402 = *(_QWORD *)(IsValidNN + 8LL * *((int *)v5 + 1));
        if ( !v402 || !*(_BYTE *)(v402 + 2) )
          goto LABEL_28;
        sqlite3VdbeMemSetNull(v6 + 56LL * *((int *)v5 + 3));
        goto LABEL_77;
      case 21:
      case 22:
      case 23:
      case 24:
        v51 = *((int *)v5 + 1);
        *(_QWORD *)&v628 = 0;
        v1 = 0;
        v52 = v3[15];
        LODWORD(v617) = 0;
        v626 = 0;
        v627 = 0;
        v53 = *(_QWORD *)(v52 + 8 * v51);
        v49 = *(_BYTE *)(v53 + 4) == 0;
        *(_WORD *)(v53 + 2) = 0;
        *(_DWORD *)(v53 + 32) = 0;
        if ( v49 )
        {
          HasHint = sqlite3BtreeCursorHasHint(*(_QWORD *)(v53 + 48), 2, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
          *(_QWORD *)&v626 = *(_QWORD *)(v53 + 56);
          WORD6(v627) = *((_WORD *)v5 + 8);
          BYTE2(v628) = 0;
          v54 = HasHint != 0;
          v123 = HasHint;
          v124 = 1;
          if ( (((_BYTE)v13 - 1) & 1) != 0 )
            v124 = -1;
          v125 = *((int *)v5 + 3);
          BYTE14(v627) = v124;
          *((_QWORD *)&v626 + 1) = v625 + 56 * v125;
          Table = sqlite3BtreeIndexMoveto(*(_QWORD *)(v53 + 48), &v626, &v617);
          updated = Table;
          if ( Table )
            goto LABEL_850;
          if ( v123 && !BYTE2(v628) )
            goto LABEL_164;
        }
        else
        {
          v54 = 0;
          v55 = v625 + 56LL * *((int *)v5 + 3);
          v56 = *(_WORD *)(v55 + 20);
          if ( (v56 & 0x2E) == 2 )
            applyNumericAffinity(v625 + 56LL * *((int *)v5 + 3), 0, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
          v57 = sqlite3_value_int64(v55);
          v58 = *(_WORD *)(v55 + 20);
          *(_WORD *)(v55 + 20) = v56;
          if ( (v58 & 0x24) == 0 )
          {
            if ( (v58 & 8) == 0 )
            {
              if ( (v58 & 1) != 0 || (unsigned int)v13 >= 0x17 )
                goto LABEL_77;
              Table = sqlite3BtreeLast(*(_QWORD *)(v53 + 48), &v617);
              updated = Table;
              if ( Table )
                goto LABEL_849;
LABEL_164:
              IsValidNN = (unsigned int)v617;
LABEL_165:
              if ( (_DWORD)IsValidNN )
                goto LABEL_77;
LABEL_166:
              if ( v54 )
                v5 += 24;
              goto LABEL_28;
            }
            v449 = sqlite3IntFloatCompare(v57);
            if ( v449 <= 0 )
            {
              if ( v449 < 0 && (v13 & 1) != 0 )
                LODWORD(v13) = v13 + 1;
            }
            else if ( (v13 & 1) == 0 )
            {
              LODWORD(v13) = v13 - 1;
            }
          }
          v450 = sqlite3BtreeTableMoveto(*(_QWORD *)(v53 + 48), v57, 0, &v617);
          v3 = v620;
          *(_QWORD *)(v53 + 80) = v57;
          updated = v450;
          Table = v450;
          if ( v450 )
            goto LABEL_850;
        }
        IsValidNN = (unsigned int)v617;
        if ( (int)v13 < 23 )
        {
          if ( (int)v617 <= 0 && ((_DWORD)v617 || (_DWORD)v13 != 21) )
          {
            IsValidNN = sqlite3BtreeEof(*(_QWORD *)(v53 + 48));
            goto LABEL_165;
          }
          LODWORD(v617) = 0;
          v126 = sqlite3BtreePrevious(*(_QWORD *)(v53 + 48), 0);
        }
        else
        {
          if ( (int)v617 >= 0 && ((_DWORD)v617 || (_DWORD)v13 != 24) )
          {
            LODWORD(v617) = 0;
            goto LABEL_166;
          }
          LODWORD(v617) = 0;
          v126 = sqlite3BtreeNext(*(_QWORD *)(v53 + 48), 0);
        }
        Table = v126;
        updated = v126;
        if ( !v126 )
          goto LABEL_164;
        if ( v126 != 101 )
          goto LABEL_850;
        Table = 0;
LABEL_863:
        LODWORD(v617) = 1;
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
        v180 = *((int *)v5 + 1);
        *(_QWORD *)&v628 = 0;
        v1 = 0;
        v181 = v3[15];
        v626 = 0;
        v627 = 0;
        v182 = *(_QWORD *)(v181 + 8 * v180);
        v183 = v6 + 56LL * *((int *)v5 + 3);
        WORD6(v627) = *((_WORD *)v5 + 8);
        *((_QWORD *)&v626 + 1) = v183;
        if ( WORD6(v627) )
        {
          v184 = (int *)(v182 + 36);
          *(_QWORD *)&v626 = *(_QWORD *)(v182 + 56);
          BYTE14(v627) = 0;
          v185 = sqlite3BtreeIndexMoveto(*(_QWORD *)(v182 + 48), &v626, v182 + 36);
          Table = v185;
        }
        else
        {
          if ( (*(_WORD *)(v183 + 20) & 0x400) != 0 && (unsigned int)sqlite3VdbeMemExpandBlob(v183) )
            goto LABEL_393;
          v451 = sqlite3VdbeAllocUnpackedRecord(*(_QWORD *)(v182 + 56));
          v452 = v451;
          if ( !v451 )
            goto LABEL_393;
          sqlite3VdbeRecordUnpack(
            *(_QWORD *)(v182 + 56),
            *(unsigned int *)(*((_QWORD *)&v626 + 1) + 16LL),
            *(_QWORD *)(*((_QWORD *)&v626 + 1) + 8LL),
            v451);
          *(_BYTE *)(v452 + 30) = 0;
          v184 = (int *)(v182 + 36);
          Table = sqlite3BtreeIndexMoveto(*(_QWORD *)(v182 + 48), v452, v182 + 36);
          v185 = Table;
          sqlite3DbFreeNN(v7, v452);
        }
        if ( v185 )
          goto LABEL_259;
        v186 = *v184;
        *(_BYTE *)(v182 + 3) = 0;
        *(_DWORD *)(v182 + 32) = 0;
        *(_BYTE *)(v182 + 2) = v186 != 0;
        IsValidNN = *v5;
        if ( (_BYTE)IsValidNN == 29 )
        {
          if ( !v186 )
            goto LABEL_77;
        }
        else
        {
          if ( v186 )
            goto LABEL_77;
          if ( (_BYTE)IsValidNN == 27 )
          {
            for ( n = 0; ; ++n )
            {
              IsValidNN = WORD6(v627);
              if ( n >= WORD6(v627) )
                break;
              if ( (*(_BYTE *)(56LL * n + *((_QWORD *)&v626 + 1) + 20) & 1) != 0 )
                goto LABEL_77;
            }
          }
          else if ( (_BYTE)IsValidNN == 26 )
          {
            IsValidNN = *((unsigned __int16 *)v5 + 8);
            *(_WORD *)(v182 + 12) = IsValidNN;
          }
        }
        goto LABEL_28;
      case 30:
        v149 = 56LL * *((int *)v5 + 3);
        v631 = 0;
        if ( (*(_BYTE *)(v149 + v6 + 20) & 0x24) != 0 )
          goto LABEL_188;
        v178 = (unsigned __int8)v8;
        LOBYTE(v8) = 67;
        v179 = *(_OWORD *)(v149 + v6 + 16);
        v634[0] = *(_OWORD *)(v149 + v6);
        v1 = *(_OWORD *)(v149 + v6 + 32);
        v634[1] = v179;
        *(_QWORD *)&v179 = *(_QWORD *)(v149 + v6 + 48);
        v635 = v1;
        v636 = v179;
        applyAffinity(v634, v8, v178, 0xAAAAAAAAAAAAAAABuLL);
        if ( (BYTE4(v634[1]) & 4) == 0 )
          goto LABEL_77;
        v150 = *(_QWORD *)&v634[0];
LABEL_189:
        v151 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1));
        v152 = *(_QWORD *)(v151 + 48);
        v631 = 0;
        v153 = sqlite3BtreeTableMoveto(v152, v150, 0, &v631);
        *(_QWORD *)(v151 + 80) = v150;
        updated = v153;
        *(_WORD *)(v151 + 2) = 0;
        *(_DWORD *)(v151 + 32) = 0;
        Table = v153;
        IsValidNN = v631;
        *(_DWORD *)(v151 + 36) = v631;
        if ( !v631 )
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
        v150 = *(_QWORD *)(56LL * *((int *)v5 + 3) + v6);
        goto LABEL_189;
      case 32:
      case 137:
        v241 = *((int *)v5 + 1);
        v242 = v3[15];
        LODWORD(v617) = 0;
        v243 = *(_QWORD *)(v242 + 8 * v241);
        v244 = *(_QWORD *)(v243 + 48);
        if ( (_BYTE)v13 == 0x89 )
        {
          v475 = *(_QWORD *)(v243 + 48);
          *(_DWORD *)(v243 + 36) = -1;
          IsValidNN = sqlite3BtreeCursorIsValidNN(v475, v8, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
          if ( (_DWORD)IsValidNN )
            goto LABEL_28;
        }
        updated = sqlite3BtreeLast(v244, &v617);
        Table = updated;
        IsValidNN = (unsigned __int8)v617;
        *(_WORD *)(v243 + 2) = (unsigned __int8)v617;
        *(_DWORD *)(v243 + 32) = 0;
        if ( updated )
          goto LABEL_260;
        if ( *((int *)v5 + 2) <= 0 || !(_DWORD)v617 )
          goto LABEL_28;
        goto LABEL_77;
      case 33:
        v286 = *((int *)v5 + 1);
        v287 = v3[15];
        LODWORD(v617) = 0;
        v288 = *(_QWORD *)(*(_QWORD *)(v287 + 8 * v286) + 48LL);
        Table = sqlite3BtreeFirst(v288, &v617, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
        updated = Table;
        if ( Table )
          goto LABEL_260;
        if ( (_DWORD)v617 )
        {
          v289 = -1;
        }
        else
        {
          v326 = sqlite3BtreeRowCountEst(v288);
          v289 = (__int16)sqlite3LogEst(v326);
        }
        IsValidNN = *((int *)v5 + 3);
        if ( v289 >= IsValidNN )
        {
          IsValidNN = *((int *)v5 + 4);
          if ( v289 <= IsValidNN )
            goto LABEL_863;
        }
        LODWORD(v617) = 0;
        goto LABEL_28;
      case 34:
      case 35:
        ++*((_DWORD *)v3 + 55);
        goto LABEL_328;
      case 36:
LABEL_328:
        v213 = *((int *)v5 + 1);
        v214 = v3[15];
        LODWORD(v617) = 0;
        v215 = *(_QWORD *)(v214 + 8 * v213);
        LODWORD(v617) = 1;
        if ( *(_BYTE *)v215 == 1 )
        {
          v216 = sqlite3VdbeSorterRewind(v215, &v617, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
        }
        else
        {
          v216 = sqlite3BtreeFirst(*(_QWORD *)(v215 + 48), &v617, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
          *(_BYTE *)(v215 + 3) = 0;
          *(_DWORD *)(v215 + 32) = 0;
        }
        Table = v216;
        updated = v216;
        if ( v216 )
          goto LABEL_260;
        IsValidNN = (unsigned __int8)v617;
        *(_BYTE *)(v215 + 2) = (_BYTE)v617;
        if ( *((int *)v5 + 2) <= 0 || (_DWORD)v617 == updated )
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
        v139 = *((int *)v5 + 1);
        *(_QWORD *)&v628 = 0;
        v1 = 0;
        v140 = v3[15];
        v626 = 0;
        v627 = 0;
        v141 = *(_QWORD *)(v140 + 8 * v139);
        memset(v634, 0, sizeof(v634));
        *(_QWORD *)&v626 = *(_QWORD *)(v141 + 56);
        WORD6(v627) = *((_WORD *)v5 + 8);
        BYTE14(v627) = -((unsigned __int8)v13 < 0x2Au);
        v142 = 56LL * *((int *)v5 + 3);
        v635 = 0;
        v636 = 0;
        *((_QWORD *)&v626 + 1) = v6 + v142;
        v143 = *(_QWORD *)(v141 + 48);
        getCellInfo(v143);
        v144 = *(unsigned int *)(v143 + 64);
        if ( (unsigned int)(v144 - 1) > 0x7FFFFFFE )
        {
          v476 = "database corruption";
          v477 = 100176;
          v478 = 11;
          goto LABEL_1196;
        }
        *((_QWORD *)&v634[1] + 1) = v7;
        WORD2(v634[1]) = 0;
        LODWORD(v635) = 0;
        Table = sqlite3VdbeMemFromBtreeZeroOffset(v143, v144, v634);
        updated = Table;
        if ( Table )
          goto LABEL_260;
        v145 = sqlite3VdbeRecordCompareWithSkip(LODWORD(v634[1]), *((_QWORD *)&v634[0] + 1), &v626, 0);
        IsValidNN = sqlite3VdbeMemReleaseMalloc(v634);
        v146 = v145 + 1;
        v147 = -v145;
        if ( (*v5 & 1) != 0 )
          v147 = v146;
        if ( v147 > 0 )
        {
LABEL_77:
          v59 = *((_DWORD *)v5 + 2);
LABEL_78:
          v60 = 3LL * (v59 - 1);
          IsValidNN = v616;
          v5 = (unsigned __int8 *)(v616 + 8 * v60);
        }
LABEL_28:
        v4 = v624;
        v5 += 24;
        v3 = v620;
        updated = Table;
        v7 = v618;
        v6 = v625;
        v8 = v615;
        v12 = v622;
        continue;
      case 43:
      case 44:
        v383 = sqlite3VdbeBooleanValue(v6 + 56LL * *((int *)v5 + 1), 2);
        v384 = sqlite3VdbeBooleanValue(v6 + 56LL * *((int *)v5 + 2), 2) + 2 * v383 + v383;
        v385 = qword_1800A7850;
        if ( *v5 != 44 )
          v385 = &qword_1800A7808;
        v386 = *((unsigned __int8 *)v385 + v384);
        v387 = 56LL * *((int *)v5 + 3);
        v388 = *(_WORD *)(v387 + v6 + 20);
        if ( (_BYTE)v386 == 2 )
        {
          IsValidNN = 62017;
          v389 = v388 & 0xF240 | 1;
        }
        else
        {
          IsValidNN = 62020;
          *(_QWORD *)(v387 + v6) = v386;
          v389 = v388 & 0xF240 | 4;
        }
        *(_WORD *)(v387 + v6 + 20) = v389;
        goto LABEL_28;
      case 46:
        v319 = *((int *)v5 + 1);
        v623 = 0;
        v320 = v6 + 56 * v319;
        if ( (*(_BYTE *)(v320 + 20) & 0x10) == 0
          || !(unsigned int)sqlite3RowSetNext(*(_QWORD *)(v320 + 8), &v623, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL) )
        {
          sqlite3VdbeMemSetNull(v320);
          goto LABEL_32;
        }
        sqlite3VdbeMemSetInt64(v6 + 56LL * *((int *)v5 + 3));
        goto LABEL_33;
      case 47:
        IsValidNN = *((int *)v5 + 1);
        v509 = *((int *)v5 + 3);
        v510 = *((_DWORD *)v5 + 4);
        v511 = v6 + 56 * IsValidNN;
        if ( (*(_BYTE *)(v511 + 20) & 0x10) == 0 )
        {
          IsValidNN = sqlite3VdbeMemSetRowSet(v6 + 56 * IsValidNN, v8, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
          if ( (_DWORD)IsValidNN )
            goto LABEL_393;
        }
        v512 = 56 * v509;
        v513 = v510 < 0;
        if ( !v510 )
          goto LABEL_1003;
        IsValidNN = sqlite3RowSetTest(*(_QWORD *)(v511 + 8), (unsigned int)v510, *(_QWORD *)(v512 + v6), v16);
        if ( (_DWORD)IsValidNN )
          goto LABEL_77;
        v513 = v510 < 0;
LABEL_1003:
        if ( !v513 )
          IsValidNN = sqlite3RowSetInsert(*(_QWORD *)(v511 + 8), *(_QWORD *)(v512 + v6), v14, v16);
        goto LABEL_28;
      case 48:
        v250 = (signed __int64 *)*((_QWORD *)v5 + 2);
        v251 = v620;
        if ( !*((_WORD *)v5 + 1) )
          goto LABEL_398;
        IsValidNN = v620[33];
        if ( !IsValidNN )
          goto LABEL_398;
        do
        {
          if ( *(_QWORD *)(IsValidNN + 48) == v250[4] )
            goto LABEL_28;
          IsValidNN = *(_QWORD *)(IsValidNN + 8);
        }
        while ( IsValidNN );
LABEL_398:
        if ( *((_DWORD *)v620 + 70) >= *(_DWORD *)(v7 + 176) )
        {
          v3 = v620;
          updated = 1;
          sqlite3VdbeError(v620, "too many levels of trigger recursion", 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
          goto LABEL_260;
        }
        v252 = v625 + 56LL * *((int *)v5 + 3);
        if ( (*(_BYTE *)(v252 + 20) & 0x10) != 0 )
        {
          v253 = *(_QWORD *)(v252 + 8);
          v7 = v618;
LABEL_401:
          ++*((_DWORD *)v251 + 70);
          *(_QWORD *)(v253 + 8) = v251[33];
          *(_QWORD *)(v253 + 56) = *(_QWORD *)(v7 + 56);
          *(_QWORD *)(v253 + 96) = v251[7];
          v254 = *v251;
          v625 = v253 + 112;
          *(_QWORD *)(v253 + 104) = *(_QWORD *)(v254 + 120);
          *(_QWORD *)(v253 + 64) = v251[37];
          v251[13] = v253 + 112;
          v251[37] = 0;
          v251[7] = 0;
          v251[33] = v253;
          v255 = *(int *)(v253 + 88);
          *((_DWORD *)v251 + 9) = v255;
          *((_DWORD *)v251 + 10) = *(unsigned __int16 *)(v253 + 92);
          v251[15] = v253 + 112 + 56 * v255;
          v256 = (void *)(v253 + 112 + 8 * (7 * v255 + *((int *)v250 + 4)));
          *(_QWORD *)(v253 + 40) = v256;
          memset_0(v256, 0, (*((_DWORD *)v250 + 2) + 7) / 8);
          v257 = *v250;
          v251[17] = *v250;
          v258 = *((_DWORD *)v250 + 2);
          v3 = v620;
          v616 = v257;
          v5 = (unsigned __int8 *)(v257 - 24);
          *((_DWORD *)v620 + 36) = v258;
          goto LABEL_33;
        }
        v353 = *((_DWORD *)v250 + 4);
        v354 = v353 + *((_DWORD *)v250 + 3);
        if ( !v353 )
          ++v354;
        v355 = (*((_DWORD *)v250 + 2) + 7) / 8 + 8 * (v353 + 7 * (v354 + 2));
        v253 = sqlite3DbMallocZero(v618, v355);
        if ( v253 )
        {
          sqlite3VdbeMemRelease(v252);
          *(_QWORD *)(v252 + 48) = sqlite3VdbeFrameMemDel;
          *(_WORD *)(v252 + 20) = 4112;
          *(_QWORD *)(v252 + 8) = v253;
          *(_DWORD *)(v252 + 16) = v355;
          v7 = v618;
          *(_QWORD *)v253 = v251;
          *(_DWORD *)(v253 + 88) = v354;
          *(_DWORD *)(v253 + 92) = *((_DWORD *)v250 + 4);
          v356 = v253 + 112;
          *(_DWORD *)(v253 + 76) = -1431655765 * ((__int64)&v5[-v616] >> 3);
          *(_QWORD *)(v253 + 24) = v251[13];
          *(_DWORD *)(v253 + 84) = *((_DWORD *)v251 + 9);
          *(_QWORD *)(v253 + 32) = v251[15];
          *(_DWORD *)(v253 + 72) = *((_DWORD *)v251 + 10);
          *(_QWORD *)(v253 + 16) = v251[17];
          *(_DWORD *)(v253 + 80) = *((_DWORD *)v251 + 36);
          *(_QWORD *)(v253 + 48) = v250[4];
          v357 = v253 + 56 * (v354 + 2LL);
          if ( v253 + 112 != v357 )
          {
            do
            {
              *(_QWORD *)(v356 + 24) = v7;
              *(_WORD *)(v356 + 20) = 0;
              v356 += 56;
            }
            while ( v356 != v357 );
          }
          v15 = v624;
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
        v177 = *(_QWORD *)(56 * IsValidNN + v6);
        if ( v177 <= 0 )
          goto LABEL_28;
        *(_QWORD *)(56 * IsValidNN + v6) = v177 - *((int *)v5 + 3);
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
        v63 = v625 + 56LL * *((int *)v5 + 3);
        v64 = *(_WORD *)(v63 + 20);
        if ( ((unsigned __int8)v62 & (unsigned __int8)v64 & 4) != 0 )
        {
          IsValidNN = *(_QWORD *)v61;
          if ( *(_QWORD *)v63 > *(_QWORD *)v61 )
          {
            if ( byte_18009E837[v13] )
              goto LABEL_77;
            v622 = 1;
          }
          else if ( *(_QWORD *)v63 < *(_QWORD *)v61 )
          {
            if ( *((_BYTE *)&qword_18009E760[25] + v13 + 3) )
              goto LABEL_77;
            v622 = -1;
          }
          else
          {
            if ( byte_18009E831[v13] )
              goto LABEL_77;
            v622 = 0;
          }
        }
        else
        {
          v163 = v62 | v64;
          if ( (((unsigned __int8)v62 | (unsigned __int8)v64) & 1) == 0 )
          {
            v164 = v5[2] & 0x47;
            if ( v164 >= 0x43u )
            {
              if ( (v163 & 2) != 0 )
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
            else if ( v164 == 66 && (v163 & 2) != 0 )
            {
              if ( (v62 & 2) != 0 )
              {
                *(_WORD *)(v61 + 20) = v62 & 0xFFD3;
              }
              else if ( (v62 & 0x2C) != 0 )
              {
                LOBYTE(v14) = 1;
                sqlite3VdbeMemStringify(v61, v8, v14, 0xAAAAAAAAAAAAAAABuLL);
                v8 = v615;
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
            v622 = sqlite3MemCompare(v63, v61, *((_QWORD *)v5 + 2));
            if ( v622 < 0 )
              goto LABEL_229;
            IsValidNN = *v5;
            if ( !v622 )
              goto LABEL_338;
            goto LABEL_662;
          }
          IsValidNN = *((unsigned __int16 *)v5 + 1);
          if ( (IsValidNN & 0x80u) != 0LL )
          {
            if ( ((unsigned __int8)v62 & (unsigned __int8)v64 & 1) != 0 && (v64 & 0x100) == 0 )
            {
              IsValidNN = *v5;
              v622 = 0;
LABEL_338:
              v165 = byte_18009E831[IsValidNN];
LABEL_230:
              *(_WORD *)(v63 + 20) = v64;
              *(_WORD *)(v61 + 20) = v62;
              if ( v165 )
                goto LABEL_77;
              goto LABEL_28;
            }
            if ( (v64 & 1) != 0 )
            {
              v622 = -1;
LABEL_229:
              IsValidNN = *v5;
              v165 = *((_BYTE *)&qword_18009E760[25] + IsValidNN + 3);
              goto LABEL_230;
            }
            IsValidNN = *v5;
            v622 = 1;
LABEL_662:
            v165 = byte_18009E837[IsValidNN];
            goto LABEL_230;
          }
          if ( (IsValidNN & 0x10) != 0 )
            goto LABEL_77;
          v622 = 1;
        }
        goto LABEL_28;
      case 59:
        if ( v12 )
          goto LABEL_28;
        goto LABEL_77;
      case 60:
        v522 = 56LL * *((int *)v5 + 1);
        IsValidNN = *(_QWORD *)(v522 + v6);
        if ( !IsValidNN )
          goto LABEL_28;
        if ( IsValidNN > 0 )
          *(_QWORD *)(v522 + v6) = IsValidNN - 1;
        goto LABEL_77;
      case 61:
        v321 = 56LL * *((int *)v5 + 1);
        IsValidNN = *(_QWORD *)(v321 + v6);
        if ( IsValidNN == 0x8000000000000000uLL )
          goto LABEL_28;
        *(_QWORD *)(v321 + v6) = --IsValidNN;
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
        v576 = *(_QWORD *)(IsValidNN + 8LL * *((int *)v5 + 1));
        if ( *(_BYTE *)(v576 + 2) )
          goto LABEL_28;
        v577 = *(__int64 ***)(v576 + 48);
        v578 = *v577;
        v579 = **v577;
        Table = (*(__int64 (__fastcall **)(__int64 **, __int64, unsigned __int64, unsigned __int64))(v579 + 72))(
                  v577,
                  v8,
                  0x180000000uLL,
                  0xAAAAAAAAAAAAAAABuLL);
        sqlite3VtabImportErrmsg(v3, v578);
        if ( Table )
          goto LABEL_259;
        v580 = (*(__int64 (__fastcall **)(_QWORD))(v579 + 80))(*(_QWORD *)(v576 + 48));
        v15 = v624;
        if ( v580 )
          goto LABEL_33;
        goto LABEL_32;
      case 64:
        v350 = 56LL * *((int *)v5 + 1);
        v351 = filterHash(v6, v5, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL)
             % (unsigned __int64)(8 * *(_DWORD *)(v350 + v6 + 16));
        v352 = *(char *)((v351 >> 3) + *(_QWORD *)(v350 + v6 + 8));
        IsValidNN = v351 & 7;
        if ( !_bittest(&v352, v351 & 7) )
        {
          ++*((_DWORD *)v3 + 61);
          goto LABEL_77;
        }
        ++*((_DWORD *)v3 + 60);
        goto LABEL_28;
      case 65:
      case 66:
        v192 = *((_QWORD *)v5 + 2);
        v193 = v6 + 56LL * *((int *)v5 + 3);
        if ( *(_QWORD *)v192 != v193 )
        {
          *(_BYTE *)(v192 + 40) = v8;
          v279 = (unsigned int)*(unsigned __int8 *)(v192 + 42) - 1;
          *(_QWORD *)(v192 + 24) = v3;
          for ( *(_QWORD *)v192 = v193; (int)v279 >= 0; v279 = (unsigned int)(v279 - 1) )
            *(_QWORD *)(v192 + 8 * v279 + 48) = v6 + 56LL * ((int)v279 + *((_DWORD *)v5 + 2));
        }
        *(_WORD *)(v193 + 20) &= 0xF241u;
        *(_WORD *)(v193 + 20) |= 1u;
        (*(void (__fastcall **)(__int64, _QWORD, __int64, unsigned __int64))(*(_QWORD *)(v192 + 8) + 24LL))(
          v192,
          *(unsigned __int8 *)(v192 + 42),
          v192 + 48,
          0xAAAAAAAAAAAAAAABuLL);
        IsValidNN = *(unsigned int *)(v192 + 36);
        if ( !(_DWORD)IsValidNN )
          goto LABEL_28;
        if ( (int)IsValidNN > 0 )
        {
          LOBYTE(v194) = 1;
          v195 = (const char *)sqlite3ValueText(v193, v194);
          sqlite3VdbeError(v3, "%s", v195);
          updated = *(_DWORD *)(v192 + 36);
          Table = updated;
        }
        IsValidNN = sqlite3VdbeDeleteAuxData(v7, v3 + 37, *(unsigned int *)(v192 + 32), *((unsigned int *)v5 + 1));
        *(_DWORD *)(v192 + 36) = 0;
        if ( !updated )
          goto LABEL_28;
        goto LABEL_260;
      case 67:
        IsValidNN = 56LL * *((int *)v5 + 1);
        if ( (*(_BYTE *)(IsValidNN + v6 + 20) & 4) != 0 )
        {
          v154 = 3LL * *(_QWORD *)(IsValidNN + v6);
          IsValidNN = v616;
          v5 = (unsigned __int8 *)(v616 + 8 * v154);
        }
        goto LABEL_28;
      case 68:
        v348 = *((int *)v5 + 1);
        v349 = 3LL * *(_QWORD *)(56 * v348 + v6);
        *(_QWORD *)(56 * v348 + v6) = (int)(-1431655765 * ((__int64)&v5[-v3[17]] >> 3) - 1);
        IsValidNN = *(_DWORD *)(v616 + 8 * v349 + 8) - 1;
        v5 = (unsigned __int8 *)(v616 + 24LL * (int)IsValidNN);
        goto LABEL_28;
      case 69:
        IsValidNN = *((int *)v5 + 3);
        if ( (*(_BYTE *)(56 * IsValidNN + v6 + 20) & 1) == 0 )
          goto LABEL_28;
        goto LABEL_298;
      case 70:
LABEL_298:
        v196 = v3[33];
        if ( v196 && !*((_DWORD *)v5 + 1) )
        {
          v280 = *(_QWORD *)(v196 + 8);
          --*((_DWORD *)v3 + 70);
          v3[33] = v280;
          v281 = v3[7];
          *(_QWORD *)(v7 + 128) += v281;
          *(_QWORD *)(v7 + 120) = v281;
          LODWORD(IsValidNN) = sqlite3VdbeFrameRestore(v196, v8, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
          if ( *((_DWORD *)v5 + 2) == 4 )
            LODWORD(IsValidNN) = *(_DWORD *)(v3[17] + 24LL * (int)IsValidNN + 8) - 1;
          v282 = v3[17];
          IsValidNN = (int)IsValidNN;
          v625 = v3[13];
          v616 = v282;
          v5 = (unsigned __int8 *)(v282 + 24LL * (int)IsValidNN);
          goto LABEL_28;
        }
        v197 = *((_DWORD *)v5 + 1);
        *((_DWORD *)v3 + 13) = v197;
        *((_BYTE *)v3 + 196) = v5[8];
        if ( !v197 )
        {
          v166 = v616;
          goto LABEL_301;
        }
        v603 = *((int *)v5 + 3);
        if ( (int)v603 > 0 && !v5[1] )
        {
          LOBYTE(v8) = 1;
          v604 = (const char *)sqlite3ValueText(v6 + 56 * v603, v8);
          goto LABEL_1183;
        }
        if ( *((_WORD *)v5 + 1) )
        {
          sqlite3VdbeError(v3, "%s constraint failed", off_18009BFF8[*((unsigned __int16 *)v5 + 1)]);
          if ( *((_QWORD *)v5 + 2) )
            v3[21] = sqlite3MPrintf(v7, "%z: %s", v3[21]);
        }
        else
        {
          v604 = (const char *)*((_QWORD *)v5 + 2);
LABEL_1183:
          sqlite3VdbeError(v3, "%s", v604);
        }
        v166 = v616;
        sqlite3_log(
          *((unsigned int *)v5 + 1),
          "abort at %d in [%s]: %s",
          -1431655765 * ((__int64)&v5[-v616] >> 3),
          (const char *)v3[31],
          (const char *)v3[21]);
LABEL_301:
        v167 = v613;
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
          v168 = v633;
          if ( v15 < v633 )
            break;
          v610 = *(unsigned int (__fastcall **)(__int64, unsigned __int64, unsigned __int64, unsigned __int64))(v7 + 528);
          if ( !v610 )
            break;
          v611 = *(_QWORD *)(v7 + 536);
          v633 += *(unsigned int *)(v7 + 544);
          if ( v610(v611, v633, v14, v16) )
          {
            v633 = -1;
            updated = 9;
LABEL_1230:
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
              v609 = (const char *)sqlite3ErrStr(updated);
              sqlite3VdbeError(v3, "%s", v609);
            }
            *((_DWORD *)v3 + 13) = updated;
            sqlite3SystemError(v7, updated);
            sqlite3_log(
              updated,
              "statement aborts at %d: [%s] %s",
              -1431655765 * ((__int64)&v5[-v166] >> 3),
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
            if ( v167 )
              sqlite3ResetOneSchema(v7);
LABEL_420:
            v15 = v624;
            continue;
          }
        }
        *((_DWORD *)v3 + 57) += v15;
        if ( *((_DWORD *)v3 + 52) )
          sqlite3VdbeLeave(v3, v168, v14, v16);
        return updated;
      case 71:
        v95 = (signed __int64 *)out2Prerelease(v3, v5);
        IsValidNN = *((int *)v5 + 1);
        *v95 = IsValidNN;
        goto LABEL_28;
      case 72:
        v360 = (_QWORD *)out2Prerelease(v3, v5);
        IsValidNN = *((_QWORD *)v5 + 2);
        *v360 = *(_QWORD *)IsValidNN;
        goto LABEL_28;
      case 73:
        v299 = v615;
        goto LABEL_483;
      case 74:
      case 75:
        IsValidNN = out2Prerelease(v3, v5);
        v187 = 257;
        v188 = *((_DWORD *)v5 + 3) - *((_DWORD *)v5 + 2);
        v189 = IsValidNN;
        if ( !*((_DWORD *)v5 + 1) )
          v187 = 1;
        *(_WORD *)(IsValidNN + 20) = v187;
        for ( *(_DWORD *)(IsValidNN + 16) = 0; v188 > 0; *(_DWORD *)(v189 + 16) = 0 )
        {
          v189 += 56LL;
          IsValidNN = sqlite3VdbeMemSetNull(v189);
          --v188;
          *(_WORD *)(v189 + 20) = v187;
        }
        goto LABEL_28;
      case 76:
        v362 = 56LL * *((int *)v5 + 1);
        IsValidNN = 65473;
        *(_WORD *)(v362 + v6 + 20) &= 0xFFC1u;
        *(_WORD *)(v362 + v6 + 20) |= 1u;
        goto LABEL_28;
      case 77:
        v283 = out2Prerelease(v3, v5);
        v284 = *((_QWORD *)v5 + 2);
        v285 = v283;
        if ( v284 )
        {
          IsValidNN = sqlite3VdbeMemSetStr(v283, v284, *((int *)v5 + 1), 0, 0);
        }
        else
        {
          sqlite3VdbeMemSetZeroBlob(v283, *((unsigned int *)v5 + 1));
          IsValidNN = sqlite3VdbeMemExpandBlob(v285);
          if ( (_DWORD)IsValidNN )
            goto LABEL_393;
        }
        *(_BYTE *)(v285 + 22) = v615;
        goto LABEL_28;
      case 78:
        v170 = v3[16] + 56LL * *((int *)v5 + 1);
        if ( (unsigned int)sqlite3VdbeMemTooBig(v170 - 56, v8, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL) )
          goto LABEL_285;
        v171 = v6 + 56LL * *((int *)v5 + 2);
        if ( (*(_WORD *)(v171 + 20) & 0x9000) != 0 )
          sqlite3VdbeMemSetNull(v6 + 56LL * *((int *)v5 + 2));
        v1 = *(_OWORD *)(v170 - 56);
        *(_OWORD *)v171 = v1;
        *(_QWORD *)(v171 + 16) = *(_QWORD *)(v170 - 40);
        IsValidNN = *(unsigned __int16 *)(v171 + 20);
        LOWORD(IsValidNN) = IsValidNN & 0x8FBF | 0x2040;
        *(_WORD *)(v171 + 20) = IsValidNN;
        goto LABEL_28;
      case 79:
        v268 = *((_DWORD *)v5 + 3);
        v269 = v6 + 56LL * *((int *)v5 + 1);
        v270 = v6 + 56LL * *((int *)v5 + 2);
        while ( 1 )
        {
          sqlite3VdbeMemRelease(v270);
          IsValidNN = 0x4000;
          *(_OWORD *)v270 = *(_OWORD *)v269;
          *(_OWORD *)(v270 + 16) = *(_OWORD *)(v269 + 16);
          v1 = *(_OWORD *)(v269 + 32);
          *(_OWORD *)(v270 + 32) = v1;
          *(_QWORD *)(v270 + 48) = *(_QWORD *)(v269 + 48);
          *(_WORD *)(v269 + 20) = 1;
          *(_DWORD *)(v269 + 32) = 0;
          if ( (*(_WORD *)(v270 + 20) & 0x4000) != 0 )
          {
            IsValidNN = sqlite3VdbeMemMakeWriteable(v270);
            if ( (_DWORD)IsValidNN )
              goto LABEL_393;
          }
          v269 += 56;
          v270 += 56;
          if ( !--v268 )
            goto LABEL_28;
        }
      case 80:
        v210 = *((_DWORD *)v5 + 3);
        v211 = v6 + 56LL * *((int *)v5 + 1);
        v212 = v6 + 56LL * *((int *)v5 + 2);
        while ( 2 )
        {
          sqlite3VdbeMemShallowCopy(v212, v211, 0x4000);
          if ( (*(_WORD *)(v212 + 20) & 0x4000) != 0 && (unsigned int)sqlite3VdbeMemMakeWriteable(v212) )
            goto LABEL_393;
          IsValidNN = *(unsigned __int16 *)(v212 + 20);
          if ( (IsValidNN & 0x800) != 0 && (v5[2] & 2) != 0 )
          {
            LOWORD(IsValidNN) = IsValidNN & 0xF7FF;
            *(_WORD *)(v212 + 20) = IsValidNN;
          }
          if ( v210 )
          {
            --v210;
            v212 += 56;
            v211 += 56;
            continue;
          }
          goto LABEL_28;
        }
      case 81:
        IsValidNN = sqlite3VdbeMemShallowCopy(v6 + 56LL * *((int *)v5 + 2), v6 + 56LL * *((int *)v5 + 1), 0x4000);
        goto LABEL_28;
      case 82:
        goto LABEL_709;
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
        v166 = v616;
        v167 = v613;
        updated = 100;
        *((_DWORD *)v3 + 12) = -1431655765 * ((__int64)&v5[-v616] >> 3) + 1;
        goto LABEL_236;
      case 85:
        IsValidNN = *((int *)v5 + 1);
        if ( (_DWORD)IsValidNN )
          IsValidNN = sqlite3VdbeMemSetInt64(v6 + 56 * IsValidNN);
        goto LABEL_28;
      case 86:
        v377 = v6 + 56LL * *((int *)v5 + 1);
        IsValidNN = sqlite3_value_int64(v377);
        *(_QWORD *)v377 = IsValidNN;
        *(_WORD *)(v377 + 20) &= 0xF244u;
        *(_WORD *)(v377 + 20) |= 4u;
        *(_QWORD *)v377 = IsValidNN + *((int *)v5 + 2);
        goto LABEL_28;
      case 87:
        IsValidNN = *((int *)v5 + 1);
        v380 = v6 + 56 * IsValidNN;
        if ( (*(_BYTE *)(v380 + 20) & 0x24) != 0 )
        {
          v381 = sqlite3VdbeRealValue(v6 + 56 * IsValidNN);
          IsValidNN = 62024;
          *(double *)v380 = v381;
          *(_WORD *)(v380 + 20) &= 0xF248u;
          *(_WORD *)(v380 + 20) |= 8u;
        }
        goto LABEL_28;
      case 88:
        v382 = v6 + 56LL * *((int *)v5 + 1);
        if ( (*(_WORD *)(v382 + 20) & 0x400) == 0 )
          goto LABEL_654;
        updated = sqlite3VdbeMemExpandBlob(v6 + 56LL * *((int *)v5 + 1));
        if ( !updated )
        {
          LOBYTE(v8) = v615;
LABEL_654:
          IsValidNN = sqlite3VdbeMemCast(v382, v5[8], (unsigned __int8)v8, v16);
          Table = IsValidNN;
          updated = IsValidNN;
          if ( !(_DWORD)IsValidNN )
            goto LABEL_28;
        }
        goto LABEL_260;
      case 90:
        if ( (v5[2] & 1) != 0 )
          v198 = *((_QWORD *)v5 - 1) + 4LL;
        else
          v198 = 0;
        v199 = *((_QWORD *)v5 + 2);
        v200 = 0;
        v201 = *((_DWORD *)v5 + 1);
        v202 = *((_DWORD *)v5 + 2);
        v203 = *((_DWORD *)v5 + 3);
        v623 = v199;
        LODWORD(v617) = v201;
        LODWORD(v630) = v202;
        while ( 2 )
        {
          if ( v200 < v203 )
          {
            if ( v198 )
              v204 = *(_DWORD *)(v198 + 4LL * v200);
            else
              v204 = v200;
            v205 = *(_QWORD *)(v199 + 24);
            v206 = *(_QWORD *)(v199 + 8LL * v200 + 32);
            v207 = v625 + 56LL * (unsigned int)(v204 + v202);
            LODWORD(v619) = *(_BYTE *)(v205 + v200) & 1;
            v208 = v625 + 56LL * (unsigned int)(v204 + v201);
            IsValidNN = sqlite3MemCompare(v208, v207, v206);
            v622 = IsValidNN;
            v209 = IsValidNN;
            if ( !(_DWORD)IsValidNN )
            {
              v199 = v623;
              ++v200;
              v201 = (int)v617;
              v202 = v630;
              continue;
            }
            IsValidNN = *(_QWORD *)(v623 + 24);
            if ( (*(_BYTE *)(v200 + IsValidNN) & 2) != 0
              && ((*(_BYTE *)(v208 + 20) & 1) != 0 || (*(_BYTE *)(v207 + 20) & 1) != 0) )
            {
              v209 = -v209;
              v622 = v209;
            }
            if ( (_DWORD)v619 )
              v622 = -v209;
          }
          break;
        }
        goto LABEL_28;
      case 91:
        sqlite3VdbeBooleanValue(v6 + 56LL * *((int *)v5 + 1), *((unsigned int *)v5 + 3));
        IsValidNN = sqlite3VdbeMemSetInt64(v6 + 56LL * *((int *)v5 + 2));
        goto LABEL_28;
      case 92:
        if ( (*(_BYTE *)(56LL * *((int *)v5 + 1) + v6 + 20) & 1) != 0
          || (*(_BYTE *)(56LL * *((int *)v5 + 3) + v6 + 20) & 1) != 0 )
        {
          goto LABEL_219;
        }
LABEL_709:
        IsValidNN = sqlite3VdbeMemSetInt64(v6 + 56LL * *((int *)v5 + 2));
        goto LABEL_28;
      case 95:
        v403 = *((_QWORD *)v5 + 2);
        v404 = *(_QWORD *)(v403 + 8);
        v405 = v6 + 56LL * *((int *)v5 + 1);
        v406 = 0;
        while ( 2 )
        {
          IsValidNN = (unsigned int)*(__int16 *)(v403 + 54);
          if ( v406 >= (int)IsValidNN )
            goto LABEL_28;
          v407 = 3LL * v406;
          v408 = *(_WORD *)(v404 + 24LL * v406 + 18);
          if ( (v408 & 0x60) == 0 )
            goto LABEL_718;
          if ( (v408 & 0x20) != 0 )
            goto LABEL_738;
          if ( *((_DWORD *)v5 + 3) )
            goto LABEL_737;
LABEL_718:
          applyAffinity(v405, *(unsigned __int8 *)(v404 + 24LL * v406 + 12), (unsigned __int8)v8, v16);
          v409 = *(_WORD *)(v405 + 20);
          if ( (v409 & 1) != 0 )
            goto LABEL_736;
          switch ( (*(_DWORD *)(v404 + 24LL * v406 + 8) >> 4) & 0xF )
          {
            case 2:
              if ( (v409 & 0x10) != 0 )
                goto LABEL_736;
              break;
            case 3:
            case 4:
              if ( (v409 & 4) != 0 )
                goto LABEL_736;
              break;
            case 5:
              if ( (v409 & 4) != 0 )
              {
                v16 = 0xFFFFFFFFFFFFLL;
                if ( (unsigned __int64)(*(_QWORD *)v405 + 0x800000000000LL) > 0xFFFFFFFFFFFFLL )
                {
                  v1 = 0;
                  v411 = v409 | 8;
                  *(double *)v405 = (double)(int)*(_QWORD *)v405;
                }
                else
                {
                  v411 = v409 | 0x20;
                }
                *(_WORD *)(v405 + 20) = v411;
                *(_WORD *)(v405 + 20) = v411 & 0xFFFB;
                goto LABEL_736;
              }
              if ( (v409 & 0x28) != 0 )
              {
LABEL_736:
                LOBYTE(v8) = v615;
LABEL_737:
                v405 += 56;
LABEL_738:
                ++v406;
                continue;
              }
              break;
            default:
              if ( ((*(_DWORD *)(v404 + 24LL * v406 + 8) >> 4) & 0xF) == 6 && (v409 & 2) == 0 )
                goto LABEL_725;
              goto LABEL_736;
          }
          break;
        }
LABEL_725:
        _mm_lfence();
        v410 = v406;
        v3 = v620;
        sqlite3VdbeError(
          v620,
          "cannot store %s value in %s column %s.%s",
          off_18009CBA0[*((unsigned __int8 *)qword_18009EC50 + (*(_WORD *)(v405 + 20) & 0x3F))],
          off_1800B5540[((*(_DWORD *)(v404 + 8 * v407 + 8) >> 4) & 0xFu) - 1],
          *(const char **)v403,
          *(const char **)(v404 + 24 * v410));
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
            v412 = *(_WORD *)(ii + 20);
            if ( (v412 & 4) != 0 )
            {
              if ( (unsigned __int64)(*(_QWORD *)ii + 0x800000000000LL) > 0xFFFFFFFFFFFFLL )
              {
                v1 = 0;
                v413 = v412 & 0xFFF1 | 8;
                *(double *)ii = (double)(int)*(_QWORD *)ii;
              }
              else
              {
                v413 = v412 & 0xFFDB | 0x20;
              }
              *(_WORD *)(ii + 20) = v413;
            }
          }
          IsValidNN = (unsigned __int8)*++v36;
          if ( !(_BYTE)IsValidNN )
            break;
          LOBYTE(v8) = v615;
        }
        goto LABEL_28;
      case 97:
        v65 = 0;
        v66 = (unsigned __int8 *)*((_QWORD *)v5 + 2);
        v67 = 0;
        v68 = *((_DWORD *)v5 + 3);
        v69 = 0;
        v70 = (int *)(v625 + 56LL * *((int *)v5 + 1));
        v71 = 14LL * (*((_DWORD *)v5 + 2) - 1);
        v630 = 0;
        v72 = &v70[v71];
        v617 = (__int64 *)v70;
        v623 = (signed __int64)v72;
        LODWORD(v619) = v68;
        if ( v66 )
        {
          v271 = *v66;
          v272 = (__int64 *)v70;
          do
          {
            applyAffinity(v272, v271, (unsigned __int8)v8, v16);
            if ( *v66 == 69 )
            {
              v414 = *((_WORD *)v272 + 10);
              if ( (v414 & 4) != 0 )
                *((_WORD *)v272 + 10) = v414 & 0xFFDB | 0x20;
            }
            v271 = *++v66;
            v8 = v615;
            v272 += 7;
          }
          while ( v271 );
          v70 = (int *)v617;
          v65 = v630;
          v72 = (int *)v623;
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
              v120 = v73[4];
              v121 = ((unsigned __int64)(v74 & 2 | 0x18) >> 1) + 2 * v120;
              if ( (v74 & 0x400) != 0 )
              {
                v415 = *v73;
                v121 += 2 * v415;
                if ( v67 )
                {
                  if ( (unsigned int)sqlite3VdbeMemExpandBlob(v73) )
                    goto LABEL_391;
                  v120 += *v73;
                }
                else
                {
                  v630 = v415 + v65;
                }
              }
              v67 += v120;
              v69 += sqlite3VarintLen(v121, v8, v74, v16);
              v73[9] = v121;
            }
LABEL_96:
            if ( v73 != v70 )
            {
              v65 = v630;
              v73 -= 14;
              continue;
            }
            v79 = v625 + 56LL * (int)v619;
            if ( v69 > 126 )
            {
              v416 = sqlite3VarintLen(v69, v8, v74, v16);
              v80 = v416 + v69;
              if ( v416 < (int)sqlite3VarintLen(v80, v417, v418, v419) )
                ++v80;
            }
            else
            {
              v80 = v69 + 1;
            }
            v81 = v80 + v67;
            v82 = v630;
            if ( v81 + v630 <= *(int *)(v79 + 32) )
            {
              *(_QWORD *)(v79 + 8) = *(_QWORD *)(v79 + 40);
LABEL_102:
              *(_DWORD *)(v79 + 16) = v81;
              *(_WORD *)(v79 + 20) = 16;
              if ( v82 )
              {
                *(_DWORD *)v79 = v82;
                *(_WORD *)(v79 + 20) = 1040;
              }
              v83 = *(_BYTE **)(v79 + 8);
              v84 = &v83[v80];
              if ( v80 >= 128 )
              {
                v85 = &v83[(int)sqlite3PutVarint(v83, v80, v74, v16)];
              }
              else
              {
                *v83 = v80;
                v85 = v83 + 1;
              }
              v86 = v623;
              while ( 1 )
              {
                IsValidNN = (unsigned int)v70[9];
                if ( (unsigned int)IsValidNN <= 7 )
                {
                  *v85++ = IsValidNN;
                  if ( !(_DWORD)IsValidNN )
                    goto LABEL_116;
                  v87 = *((unsigned __int8 *)qword_18009EF00 + IsValidNN);
                  v88 = *(_QWORD *)v70;
                  if ( (_BYTE)v87 == 2 )
                  {
LABEL_114:
                    v84[1] = v88;
                    v88 >>= 8;
                  }
                  else
                  {
                    IsValidNN = (unsigned int)(v87 - 1);
                    if ( (_DWORD)v87 != 1 )
                    {
                      IsValidNN = (unsigned int)(v87 - 3);
                      if ( (_DWORD)v87 != 3 )
                      {
                        IsValidNN = (unsigned int)(v87 - 4);
                        if ( (_DWORD)v87 != 4 )
                        {
                          if ( (_DWORD)v87 != 6 )
                          {
                            v84[7] = v88;
                            v420 = v88 >> 8;
                            v84[6] = v420;
                            v88 = v420 >> 8;
                          }
                          v84[5] = v88;
                          v421 = v88 >> 8;
                          v84[4] = v421;
                          v88 = v421 >> 8;
                        }
                        v84[3] = v88;
                        v88 >>= 8;
                      }
                      v84[2] = v88;
                      v88 >>= 8;
                      goto LABEL_114;
                    }
                  }
                  *v84 = v88;
                  v84 += v87;
                  goto LABEL_116;
                }
                if ( (unsigned int)IsValidNN >= 0x80 )
                  break;
                *v85++ = IsValidNN;
                if ( (unsigned int)IsValidNN >= 0xE )
                {
                  IsValidNN = v70[4];
                  if ( (int)IsValidNN > 0 )
                    goto LABEL_186;
                }
LABEL_116:
                if ( v70 == (int *)v86 )
                  goto LABEL_28;
                v70 += 14;
              }
              v148 = (int)sqlite3PutVarint(v85, (unsigned int)v70[9], v74, v16);
              IsValidNN = v70[4];
              v85 += v148;
              if ( !(_DWORD)IsValidNN )
                goto LABEL_116;
LABEL_186:
              memcpy_0(v84, *((const void **)v70 + 1), IsValidNN);
              IsValidNN = v70[4];
              v84 += IsValidNN;
              goto LABEL_116;
            }
            if ( v81 + v630 > *(int *)(v618 + 136) )
            {
              v3 = v620;
LABEL_284:
              v7 = v618;
              goto LABEL_285;
            }
            if ( !(unsigned int)sqlite3VdbeMemClearAndResize(v79, (unsigned int)v81) )
              goto LABEL_102;
LABEL_391:
            v3 = v620;
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
          if ( (*(_QWORD *)v73 & 1LL) == v75 && *((_BYTE *)v620 + 197) >= 4u )
          {
            v8 = (unsigned int)(v76 + 8);
          }
          else
          {
            ++v67;
            v8 = 1;
          }
          v77 = 36;
          v78 = (__int64)v73;
          goto LABEL_95;
        }
        if ( v76 > 0x7FFF )
        {
          if ( v76 <= 0x7FFFFF )
          {
            v67 += 3;
            v8 = 3;
            v78 = 36;
            v77 = (__int64)v73;
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
                v8 = 7;
                LOWORD(v74) = v74 & 0xFFD7 | 8;
                *((_WORD *)v73 + 10) = v74;
                *(double *)v73 = (double)(int)v75;
              }
              else
              {
                v8 = 6;
              }
            }
            else
            {
              v67 += 6;
              v8 = 5;
            }
          }
          else
          {
            v67 += 4;
            v8 = 4;
          }
        }
        else
        {
          v67 += 2;
          v8 = 2;
        }
        v78 = 36;
        v77 = (__int64)v73;
LABEL_95:
        *(_DWORD *)(v78 + v77) = v8;
        goto LABEL_96;
      case 98:
        v49 = *((_DWORD *)v5 + 3) == 0;
        v315 = *((int *)v5 + 1);
        v316 = v3[15];
        v619 = 0;
        v317 = *(_QWORD *)(v316 + 8 * v315);
        if ( v49 )
        {
          Table = sqlite3BtreeCount(v7, *(_QWORD *)(v317 + 48), &v619, 0xAAAAAAAAAAAAAAABuLL);
          updated = Table;
          if ( Table )
            goto LABEL_260;
        }
        else
        {
          v619 = sqlite3BtreeRowCountEst(*(_QWORD *)(v317 + 48));
        }
        v318 = (__int64 *)out2Prerelease(v3, v5);
        *v318 = v619;
        goto LABEL_33;
      case 99:
        v437 = *(_QWORD *)(v7 + 32);
        v438 = *((unsigned int *)v5 + 3);
        v439 = 32LL * *((int *)v5 + 1);
        LODWORD(v617) = 0;
        sqlite3BtreeGetMeta(*(_QWORD *)(v439 + v437 + 8), v438, &v617);
        IsValidNN = out2Prerelease(v3, v5);
        *(_QWORD *)IsValidNN = (int)v617;
        goto LABEL_28;
      case 100:
        v440 = *(_QWORD *)(v7 + 32);
        v441 = 32LL * *((int *)v5 + 1);
        updated = sqlite3BtreeUpdateMeta(
                    *(_QWORD *)(v441 + v440 + 8),
                    *((unsigned int *)v5 + 2),
                    *((unsigned int *)v5 + 3));
        Table = updated;
        IsValidNN = *((unsigned int *)v5 + 2);
        if ( (_DWORD)IsValidNN == 1 )
        {
          **(_DWORD **)(v441 + v440 + 24) = *((_DWORD *)v5 + 3) - *((unsigned __int16 *)v5 + 1);
          *(_DWORD *)(v7 + 44) |= 1u;
          IsValidNN = sqlite3FkClearTriggerCache(v7, *((unsigned int *)v5 + 1));
        }
        else if ( (_DWORD)IsValidNN == 2 )
        {
          IsValidNN = v5[12];
          *(_BYTE *)(*(_QWORD *)(v441 + v440 + 24) + 112LL) = IsValidNN;
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
        v114 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1));
        if ( !v114 || *(_DWORD *)(v114 + 68) != *((_DWORD *)v5 + 2) )
          goto LABEL_132;
        v442 = *(_QWORD *)(v114 + 48);
        sqlite3_free(*(_QWORD *)(v442 + 24));
        *(_QWORD *)(v442 + 24) = 0;
        *(_BYTE *)v442 = 1;
        goto LABEL_139;
      case 102:
      case 113:
LABEL_132:
        if ( (v3[25] & 3) == 1 )
        {
          updated = 516;
          goto LABEL_260;
        }
        v103 = *((_DWORD *)v5 + 3);
        v104 = *(_QWORD *)(v7 + 32);
        v105 = *((unsigned int *)v5 + 2);
        v106 = v620;
        v107 = 32LL * v103;
        v108 = *(_QWORD *)(v107 + v104 + 8);
        if ( (_BYTE)v13 == 113 )
        {
          v109 = *((_WORD *)v5 + 1) & 8 | 4;
          v259 = *(_BYTE *)(*(_QWORD *)(v107 + v104 + 24) + 112LL);
          if ( v259 < *((_BYTE *)v620 + 197) )
            *((_BYTE *)v620 + 197) = v259;
          if ( (v5[2] & 0x10) != 0 )
          {
            v260 = v625 + 56 * v105;
            v261 = sqlite3_value_int64(v260);
            v106 = v620;
            LODWORD(v105) = v261;
            *(_QWORD *)v260 = v261;
            *(_WORD *)(v260 + 20) &= 0xF244u;
            *(_WORD *)(v260 + 20) |= 4u;
          }
        }
        else
        {
          v109 = 0;
        }
        v110 = v5[1];
        if ( v110 == 0xF8 )
        {
          v111 = *((_QWORD *)v5 + 2);
          v112 = *(unsigned __int16 *)(v111 + 8);
        }
        else
        {
          v112 = 0;
          v111 = 0;
          if ( v110 == 0xFD )
            v112 = *((unsigned int *)v5 + 4);
        }
        Cursor = allocateCursor(v106, *((unsigned int *)v5 + 1), v112, 0);
        v114 = Cursor;
        if ( !Cursor )
          goto LABEL_391;
        v115 = *(_QWORD *)(Cursor + 48);
        *(_DWORD *)(Cursor + 8) |= 4u;
        *(_BYTE *)(Cursor + 1) = v103;
        *(_BYTE *)(Cursor + 2) = 1;
        *(_DWORD *)(Cursor + 68) = v105;
        v116 = sqlite3BtreeCursor(v108, v105, v109, v111, v115);
        v3 = v620;
        updated = v116;
        v7 = v618;
        *(_QWORD *)(v114 + 56) = v111;
        Table = v116;
        *(_BYTE *)(v114 + 4) = v5[1] != 0xF8;
LABEL_139:
        IsValidNN = *(_QWORD *)(v114 + 48);
        *(_BYTE *)(IsValidNN + 3) = v5[2] & 3;
        if ( updated )
          goto LABEL_260;
        goto LABEL_28;
      case 103:
      case 104:
      case 105:
      case 106:
        v235 = v6 + 56LL * *((int *)v5 + 1);
        v236 = v6 + 56LL * *((int *)v5 + 3);
        if ( ((*(_BYTE *)(v235 + 20) | *(_BYTE *)(v6 + 56LL * *((int *)v5 + 2) + 20)) & 1) != 0 )
        {
          IsValidNN = sqlite3VdbeMemSetNull(v6 + 56LL * *((int *)v5 + 3));
          goto LABEL_28;
        }
        v237 = sqlite3_value_int64(v6 + 56LL * *((int *)v5 + 2));
        v238 = sqlite3_value_int64(v235);
        v239 = *v5;
        v240 = v238;
        if ( *v5 == 103 )
        {
          v237 &= v238;
LABEL_375:
          IsValidNN = 62020;
          *(_QWORD *)v236 = v237;
          *(_WORD *)(v236 + 20) &= 0xF244u;
          *(_WORD *)(v236 + 20) |= 4u;
          goto LABEL_28;
        }
        if ( v239 == 104 )
        {
          v237 |= v238;
          goto LABEL_375;
        }
        if ( !v238 )
          goto LABEL_375;
        if ( v238 >= 0 )
          goto LABEL_633;
        v239 = -45 - v239;
        if ( v238 > -64 )
        {
          v240 = -v238;
LABEL_633:
          if ( v240 < 64 )
          {
            if ( v239 == 105 )
            {
              v237 <<= v240;
            }
            else if ( v237 >= 0 )
            {
              v237 = (unsigned __int64)v237 >> v240;
            }
            else
            {
              v237 = ((unsigned __int64)v237 >> v240) | (-1LL << (64 - (unsigned __int8)v240));
            }
            goto LABEL_375;
          }
        }
        if ( v237 >= 0 || v239 == 105 )
          v237 = 0;
        else
          v237 = -1;
        goto LABEL_375;
      case 107:
      case 108:
      case 109:
      case 110:
      case 111:
        v335 = v6 + 56LL * *((int *)v5 + 1);
        v336 = 56LL * *((int *)v5 + 3);
        v337 = v6 + 56LL * *((int *)v5 + 2);
        v632 = 0;
        v338 = *(_WORD *)(v335 + 20);
        v339 = v6 + v336;
        v340 = *(_WORD *)(v337 + 20);
        if ( ((unsigned __int8)v338 & (unsigned __int8)v340 & 4) != 0 )
          goto LABEL_526;
        if ( (((unsigned __int8)v338 | (unsigned __int8)v340) & 1) != 0 )
          goto LABEL_623;
        v369 = numericType(v335);
        if ( (v369 & (unsigned __int8)numericType(v337) & 4) == 0 )
          goto LABEL_608;
LABEL_526:
        v341 = *v5;
        v342 = *(_QWORD *)v337;
        v343 = *(_QWORD *)v335;
        v632 = *(_QWORD *)v337;
        if ( v341 == 107 )
        {
          if ( !(unsigned int)sqlite3AddInt64(&v632, v343) )
          {
LABEL_528:
            *(_QWORD *)v339 = v632;
            IsValidNN = *(unsigned __int16 *)(v339 + 20);
            LOWORD(IsValidNN) = IsValidNN & 0xF240 | 4;
LABEL_529:
            *(_WORD *)(v339 + 20) = IsValidNN;
            goto LABEL_28;
          }
        }
        else
        {
          v370 = v341 - 108;
          if ( v370 )
          {
            v371 = v370 - 1;
            if ( v371 )
            {
              if ( v371 != 1 )
              {
                if ( v343 )
                {
                  if ( v343 == -1 )
                    v343 = 1;
                  v632 = v342 % v343;
                  goto LABEL_528;
                }
                goto LABEL_623;
              }
              if ( !v343 )
                goto LABEL_623;
              if ( v343 != -1 || v342 != 0x8000000000000000uLL )
              {
                v632 = v342 / v343;
                goto LABEL_528;
              }
            }
            else if ( !(unsigned int)sqlite3MulInt64(&v632, v343, v342, v16) )
            {
              goto LABEL_528;
            }
          }
          else if ( !(unsigned int)sqlite3SubInt64(&v632, v343, v342, v16) )
          {
            goto LABEL_528;
          }
        }
LABEL_608:
        v372 = sqlite3VdbeRealValue(v335);
        *(double *)&v1 = sqlite3VdbeRealValue(v337);
        *((_QWORD *)&v373 + 1) = *((_QWORD *)&v1 + 1);
        switch ( *v5 )
        {
          case 'k':
            v376 = *(double *)&v1 + v372;
            break;
          case 'l':
            v376 = *(double *)&v1 - v372;
            break;
          case 'm':
            v376 = *(double *)&v1 * v372;
            break;
          case 'n':
            if ( v372 == 0.0 )
              goto LABEL_623;
            v376 = *(double *)&v1 / v372;
            break;
          default:
            v374 = sqlite3_value_int64(v335);
            v375 = sqlite3_value_int64(v337);
            v632 = v375;
            if ( !v374 )
              goto LABEL_623;
            v373 = 0;
            if ( v374 == -1 )
              v374 = 1;
            v376 = (double)(int)(v375 % v374);
            break;
        }
        *((_QWORD *)&v1 + 1) = *((_QWORD *)&v373 + 1);
        if ( !(unsigned int)sqlite3IsNaN() )
        {
          IsValidNN = *(unsigned __int16 *)(v339 + 20);
          *(double *)v339 = v376;
          LOWORD(IsValidNN) = IsValidNN & 0xF240 | 8;
          goto LABEL_529;
        }
LABEL_623:
        IsValidNN = sqlite3VdbeMemSetNull(v339);
        goto LABEL_28;
      case 112:
        v363 = v6 + 56LL * *((int *)v5 + 1);
        v364 = v6 + 56LL * *((int *)v5 + 2);
        v365 = v6 + 56LL * *((int *)v5 + 3);
        v366 = *(_WORD *)(v363 + 20);
        if ( ((*(_BYTE *)(v364 + 20) | (unsigned __int8)v366) & 1) != 0 )
        {
          IsValidNN = sqlite3VdbeMemSetNull(v365);
          goto LABEL_28;
        }
        if ( (v366 & 0x12) != 0 )
        {
          if ( (v366 & 0x400) == 0 )
            goto LABEL_578;
          if ( (unsigned int)sqlite3VdbeMemExpandBlob(v363) )
            goto LABEL_392;
        }
        else if ( (unsigned int)sqlite3VdbeMemStringify(v363, v8, 0, 0xAAAAAAAAAAAAAAABuLL) )
        {
          goto LABEL_392;
        }
        v8 = v615;
        v366 = *(_WORD *)(v363 + 20) & 0xFFFD;
LABEL_578:
        v367 = *(_WORD *)(v364 + 20);
        if ( (v367 & 0x12) != 0 )
        {
          if ( (v367 & 0x400) == 0 )
            goto LABEL_584;
          if ( (unsigned int)sqlite3VdbeMemExpandBlob(v364) )
            goto LABEL_392;
        }
        else if ( (unsigned int)sqlite3VdbeMemStringify(v364, v8, 0, v16) )
        {
          goto LABEL_392;
        }
        v367 = *(_WORD *)(v364 + 20) & 0xFFFD;
LABEL_584:
        LODWORD(v368) = *(_DWORD *)(v363 + 16) + *(_DWORD *)(v364 + 16);
        if ( (int)v368 > *(_DWORD *)(v618 + 136) )
        {
          v3 = v620;
          v7 = v618;
          goto LABEL_285;
        }
        if ( (unsigned int)sqlite3VdbeMemGrow(v365, (unsigned int)(v368 + 2), v365 == v364) )
          goto LABEL_391;
        v368 = (int)v368;
        *(_WORD *)(v365 + 20) &= 0xF242u;
        *(_WORD *)(v365 + 20) |= 2u;
        if ( v365 != v364 )
        {
          memcpy_0(*(void **)(v365 + 8), *(const void **)(v364 + 8), *(int *)(v364 + 16));
          *(_WORD *)(v364 + 20) = v367;
        }
        memcpy_0((void *)(*(_QWORD *)(v365 + 8) + *(int *)(v364 + 16)), *(const void **)(v363 + 8), *(int *)(v363 + 16));
        *(_WORD *)(v363 + 20) = v366;
        if ( v615 > 1u )
          v368 = (int)v368 & 0xFFFFFFFFFFFFFFFEuLL;
        *(_BYTE *)(v368 + *(_QWORD *)(v365 + 8)) = 0;
        *(_BYTE *)(*(_QWORD *)(v365 + 8) + v368 + 1) = 0;
        IsValidNN = 512;
        *(_WORD *)(v365 + 20) |= 0x200u;
        *(_DWORD *)(v365 + 16) = v368;
        *(_BYTE *)(v365 + 22) = v615;
        goto LABEL_28;
      case 114:
        v443 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 2));
        v444 = allocateCursor(v3, *((unsigned int *)v5 + 1), (unsigned int)*(__int16 *)(v443 + 72), 0);
        if ( !v444 )
          goto LABEL_393;
        *(_DWORD *)(v444 + 8) |= 1u;
        *(_BYTE *)(v444 + 2) = 1;
        *(_QWORD *)(v444 + 56) = *(_QWORD *)(v443 + 56);
        *(_BYTE *)(v444 + 4) = *(_BYTE *)(v443 + 4);
        *(_DWORD *)(v444 + 68) = *(_DWORD *)(v443 + 68);
        v445 = *(_DWORD *)(v444 + 8) ^ (*(_DWORD *)(v443 + 8) ^ *(_DWORD *)(v444 + 8)) & 4;
        *(_DWORD *)(v444 + 8) = v445;
        *(_QWORD *)(v444 + 16) = *(_QWORD *)(v443 + 16);
        *(_DWORD *)(v444 + 8) = v445 | 8;
        *(_DWORD *)(v443 + 8) |= 8u;
        IsValidNN = sqlite3BtreeCursor(
                      *(_QWORD *)(v444 + 16),
                      *(_DWORD *)(v444 + 68),
                      4,
                      *(_QWORD *)(v444 + 56),
                      *(_QWORD *)(v444 + 48));
        Table = IsValidNN;
        goto LABEL_28;
      case 115:
        v391 = v6 + 56LL * *((int *)v5 + 1);
        v392 = v6 + 56LL * *((int *)v5 + 2);
        IsValidNN = sqlite3VdbeMemSetNull(v392);
        if ( (*(_BYTE *)(v391 + 20) & 1) == 0 )
        {
          *(_WORD *)(v392 + 20) = 4;
          IsValidNN = ~sqlite3_value_int64(v391);
          *(_QWORD *)v392 = IsValidNN;
        }
        goto LABEL_28;
      case 116:
      case 117:
        v227 = *((int *)v5 + 3);
        if ( (int)v227 > 0 )
        {
          *(_DWORD *)(56 * v227 + v6 + 16) = 0;
          *(_QWORD *)(56LL * *((int *)v5 + 3) + v6 + 8) = qword_18009EEF0;
        }
        v228 = *((int *)v5 + 1);
        v229 = *(_QWORD *)(v3[15] + 8 * v228);
        if ( !v229 || (*(_BYTE *)(v229 + 8) & 8) != 0 || *((_DWORD *)v5 + 2) > *(__int16 *)(v229 + 72) )
        {
          v230 = allocateCursor(v3, v228, *((unsigned int *)v5 + 2), 0);
          v229 = v230;
          if ( !v230 )
            goto LABEL_393;
          *(_DWORD *)(v230 + 8) |= 1u;
          updated = sqlite3BtreeOpen(*(_QWORD *)v7, 0, v7, v230 + 16, *((unsigned __int16 *)v5 + 1) | 5u, 1054);
          if ( updated )
            goto LABEL_260;
          Table = sqlite3BtreeBeginTrans(*(_QWORD *)(v229 + 16), 1, 0);
          updated = Table;
          if ( !Table )
          {
            v231 = *((_QWORD *)v5 + 2);
            v232 = *(_QWORD *)(v229 + 16);
            *(_QWORD *)(v229 + 56) = v231;
            if ( v231 )
            {
              Table = sqlite3BtreeCreateTable(v232, v229 + 68, *((unsigned __int16 *)v5 + 1) | 2u);
              if ( Table )
              {
                updated = Table;
              }
              else
              {
                updated = sqlite3BtreeCursor(
                            *(_QWORD *)(v229 + 16),
                            *(_DWORD *)(v229 + 68),
                            4,
                            v231,
                            *(_QWORD *)(v229 + 48));
                Table = updated;
              }
              *(_BYTE *)(v229 + 4) = 0;
            }
            else
            {
              v612 = *(_QWORD *)(v229 + 48);
              *(_DWORD *)(v229 + 68) = 1;
              updated = sqlite3BtreeCursor(v232, 1, 4, 0, v612);
              Table = updated;
              *(_BYTE *)(v229 + 4) = 1;
            }
            v3 = v620;
          }
          v233 = 0;
          if ( *((_WORD *)v5 + 1) != 8 )
            v233 = 4;
          IsValidNN = *(_DWORD *)(v229 + 8) & 0xFFFFFFFB;
          *(_DWORD *)(v229 + 8) = IsValidNN | v233;
          if ( updated )
          {
            sqlite3BtreeClose(*(_QWORD *)(v229 + 16));
            goto LABEL_260;
          }
        }
        else
        {
          v358 = *(unsigned int *)(v229 + 68);
          v359 = *(_QWORD *)(v229 + 16);
          *(_QWORD *)(v229 + 24) = 0;
          *(_DWORD *)(v229 + 32) = 0;
          IsValidNN = sqlite3BtreeClearTable(v359, v358, 0);
          Table = IsValidNN;
          updated = IsValidNN;
          if ( (_DWORD)IsValidNN )
            goto LABEL_260;
        }
        *(_BYTE *)(v229 + 2) = 1;
        goto LABEL_28;
      case 118:
        v296 = out2Prerelease(v3, v5);
        v297 = sqlite3Strlen30(*((_QWORD *)v5 + 2));
        v299 = v615;
        *((_DWORD *)v5 + 1) = v297;
        if ( v615 == 1 )
          goto LABEL_481;
        LOBYTE(v298) = 1;
        Table = sqlite3VdbeMemSetStr(v296, *((_QWORD *)v5 + 2), -1, v298, 0);
        if ( Table )
          goto LABEL_285;
        if ( (unsigned int)sqlite3VdbeChangeEncoding(v296, v615) )
          goto LABEL_393;
        *(_DWORD *)(v296 + 32) = 0;
        *(_WORD *)(v296 + 20) |= 0x2000u;
        if ( v5[1] == 0xFA )
          sqlite3DbFree(v7, *((_QWORD *)v5 + 2));
        v5[1] = -6;
        *((_QWORD *)v5 + 2) = *(_QWORD *)(v296 + 8);
        v297 = *(_DWORD *)(v296 + 16);
        *((_DWORD *)v5 + 1) = v297;
LABEL_481:
        if ( v297 > *(_DWORD *)(v7 + 136) )
          goto LABEL_285;
        *v5 = 73;
LABEL_483:
        IsValidNN = out2Prerelease(v3, v5);
        v300 = IsValidNN;
        *(_WORD *)(IsValidNN + 20) = 8706;
        *(_QWORD *)(IsValidNN + 8) = *((_QWORD *)v5 + 2);
        *(_DWORD *)(IsValidNN + 16) = *((_DWORD *)v5 + 1);
        *(_BYTE *)(IsValidNN + 22) = v299;
        v301 = *((int *)v5 + 3);
        if ( (int)v301 > 0 )
        {
          IsValidNN = *((unsigned __int16 *)v5 + 1);
          if ( *(_QWORD *)(56 * v301 + v6) == IsValidNN )
            *(_WORD *)(v300 + 20) = 8720;
        }
        goto LABEL_28;
      case 119:
        LOBYTE(v16) = 1;
        v446 = allocateCursor(v3, *((unsigned int *)v5 + 1), *((unsigned int *)v5 + 2), v16);
        if ( !v446 )
          goto LABEL_393;
        *(_QWORD *)(v446 + 56) = *((_QWORD *)v5 + 2);
        IsValidNN = sqlite3VdbeSorterInit(v7, *((unsigned int *)v5 + 3), v446);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( !(_DWORD)IsValidNN )
          goto LABEL_28;
        goto LABEL_260;
      case 120:
        v447 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1));
        v448 = *(_QWORD *)(v447 + 24);
        IsValidNN = v448 + 1;
        *(_QWORD *)(v447 + 24) = v448 + 1;
        if ( v448 )
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
        v327 = *((int *)v5 + 7);
        *(_QWORD *)&v628 = 0;
        v1 = 0;
        v328 = v3[15];
        LODWORD(v617) = 0;
        v626 = 0;
        v627 = 0;
        v329 = *(_QWORD *)(v328 + 8 * v327);
        IsValidNN = sqlite3BtreeCursorIsValidNN(*(_QWORD *)(v329 + 48), v8, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
        if ( !(_DWORD)IsValidNN )
          goto LABEL_28;
        v330 = *((_DWORD *)v5 + 1);
        *(_QWORD *)&v626 = *(_QWORD *)(v329 + 56);
        WORD6(v627) = *((_WORD *)v5 + 20);
        v331 = *((int *)v5 + 9);
        BYTE14(v627) = 0;
        *((_QWORD *)&v626 + 1) = v6 + 56 * v331;
        LODWORD(v617) = 0;
        while ( 2 )
        {
          Table = sqlite3VdbeIdxKeyCompare(v7, v329, &v626, &v617);
          updated = Table;
          if ( Table )
            goto LABEL_260;
          IsValidNN = (unsigned int)v617;
          v332 = (int)v617 < 0;
          if ( (int)v617 <= 0 )
            goto LABEL_521;
          if ( !*((_WORD *)v5 + 1) )
            goto LABEL_873;
          v332 = (int)v617 < 0;
LABEL_521:
          if ( !v332 )
            goto LABEL_77;
          if ( v330 <= 0 )
            goto LABEL_28;
          v333 = *(_QWORD *)(v329 + 48);
          *(_DWORD *)(v329 + 32) = 0;
          v334 = sqlite3BtreeNext(v333, 0);
          updated = v334;
          if ( !v334 )
          {
            --v330;
            continue;
          }
          break;
        }
        if ( v334 != 101 )
          goto LABEL_260;
        Table = 0;
LABEL_873:
        v5 += 24;
        goto LABEL_77;
      case 125:
        IsValidNN = v3[15];
        v312 = *((_DWORD *)v5 + 2);
        v313 = *(_QWORD *)(IsValidNN + 8LL * *((int *)v5 + 1));
        v314 = *(unsigned __int16 *)(v313 + 12);
        if ( v314 < v312 )
        {
          *(_WORD *)(v313 + 12) = v312;
        }
        else
        {
          IsValidNN = *((unsigned int *)v5 + 3);
          if ( v314 > (int)IsValidNN )
            *(_WORD *)(v313 + 12) = IsValidNN;
        }
        goto LABEL_28;
      case 126:
        *(_QWORD *)out2Prerelease(v3, v5) = *(_QWORD *)(*(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1)) + 24LL);
        IsValidNN = v3[15];
        v454 = *(_QWORD *)(IsValidNN + 8LL * *((int *)v5 + 1));
        ++*(_QWORD *)(v454 + 24);
        goto LABEL_28;
      case 127:
        v619 = 0;
        LODWORD(v617) = 0;
        v262 = (__int64 *)out2Prerelease(v3, v5);
        v263 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1));
        if ( (*(_BYTE *)(v263 + 8) & 2) != 0 )
          goto LABEL_409;
        Table = sqlite3BtreeLast(*(_QWORD *)(v263 + 48), &v617);
        if ( Table )
          goto LABEL_259;
        if ( (_DWORD)v617 )
        {
          v619 = 1;
        }
        else
        {
          v455 = *(_QWORD *)(v263 + 48);
          getCellInfo(v455);
          v456 = *(_QWORD *)(v455 + 48);
          v619 = v456;
          if ( v456 == 0x7FFFFFFFFFFFFFFFLL )
            *(_DWORD *)(v263 + 8) |= 2u;
          else
            v619 = v456 + 1;
        }
LABEL_409:
        v264 = *((int *)v5 + 3);
        if ( !(_DWORD)v264 )
          goto LABEL_410;
        v457 = v3[33];
        if ( v457 )
        {
          for ( ; *(_QWORD *)(v457 + 8); v457 = *(_QWORD *)(v457 + 8) )
            ;
          v458 = *(_QWORD *)(v457 + 24) + 56 * v264;
        }
        else
        {
          v458 = v6 + 56 * v264;
        }
        v459 = sqlite3_value_int64(v458);
        *(_QWORD *)v458 = v459;
        *(_WORD *)(v458 + 20) &= 0xF244u;
        *(_WORD *)(v458 + 20) |= 4u;
        if ( v459 == 0x7FFFFFFFFFFFFFFFLL || (*(_BYTE *)(v263 + 8) & 2) != 0 )
          goto LABEL_913;
        v460 = v459 + 1;
        v461 = v619;
        if ( v619 < v460 )
        {
          v461 = v460;
          v619 = v460;
        }
        *(_QWORD *)v458 = v461;
LABEL_410:
        if ( (*(_BYTE *)(v263 + 8) & 2) == 0 )
          goto LABEL_411;
        v462 = 0;
        while ( 2 )
        {
          sqlite3_randomness(8, &v619);
          v619 = (v619 & 0x3FFFFFFFFFFFFFFFLL) + 1;
          Table = sqlite3BtreeTableMoveto(*(_QWORD *)(v263 + 48), v619, 0, &v617);
          if ( Table )
            goto LABEL_259;
          if ( !(_DWORD)v617 )
          {
            if ( ++v462 >= 100 )
            {
LABEL_913:
              updated = 13;
              goto LABEL_260;
            }
            continue;
          }
          break;
        }
LABEL_411:
        *(_BYTE *)(v263 + 3) = 0;
        *(_DWORD *)(v263 + 32) = 0;
        IsValidNN = v619;
        *v262 = v619;
        goto LABEL_28;
      case 128:
        v1 = 0;
        v302 = *((int *)v5 + 1);
        v303 = 56LL * *((int *)v5 + 2);
        v626 = 0;
        v627 = 0;
        v304 = v3[15];
        v628 = 0;
        v305 = *(_QWORD *)(v304 + 8 * v302);
        v49 = v5[1] == 0xFB;
        v306 = *(_QWORD *)(56LL * *((int *)v5 + 3) + v6);
        *((_QWORD *)&v626 + 1) = v306;
        if ( v49 && *(_QWORD *)(v7 + 320) )
        {
          v307 = (_QWORD *)*((_QWORD *)v5 + 2);
          v308 = *(_QWORD *)(32LL * *(char *)(v305 + 1) + *(_QWORD *)(v7 + 32));
        }
        else
        {
          v307 = 0;
          v308 = 0;
        }
        if ( (v5[2] & 1) != 0 )
        {
          ++v3[7];
          if ( (v5[2] & 0x20) != 0 )
            *(_QWORD *)(v7 + 56) = v306;
        }
        v309 = *((_WORD *)v5 + 1);
        *(_QWORD *)&v627 = *(_QWORD *)(v303 + v6 + 8);
        DWORD1(v628) = *(_DWORD *)(v303 + v6 + 16);
        if ( (v309 & 0x10) != 0 )
          v310 = *(unsigned int *)(v305 + 36);
        else
          v310 = 0;
        if ( (*(_WORD *)(v303 + v6 + 20) & 0x400) != 0 )
          DWORD2(v628) = *(_DWORD *)(v303 + v6);
        else
          DWORD2(v628) = 0;
        *(_QWORD *)&v626 = 0;
        IsValidNN = sqlite3BtreeInsert(*(_QWORD *)(v305 + 48), &v626, (unsigned __int8)v309 & 0x8A, v310);
        Table = IsValidNN;
        *(_BYTE *)(v305 + 3) = 0;
        *(_DWORD *)(v305 + 32) = 0;
        if ( (_DWORD)IsValidNN )
          goto LABEL_259;
        ++v629;
        if ( v307 )
        {
          v311 = 23;
          if ( (v5[2] & 4) == 0 )
            v311 = 18;
          IsValidNN = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _QWORD))(v7 + 320))(
                        *(_QWORD *)(v7 + 312),
                        v311,
                        v308,
                        *v307,
                        *((_QWORD *)&v626 + 1));
        }
        goto LABEL_28;
      case 129:
        v463 = *((int *)v5 + 3);
        if ( (_DWORD)v463 )
          v464 = *(_QWORD *)(56 * v463 + v6);
        else
          v464 = 0;
        IsValidNN = sqlite3BtreeTransferRow(
                      *(_QWORD *)(*(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1)) + 48LL),
                      *(_QWORD *)(*(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 2)) + 48LL),
                      v464);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( !(_DWORD)IsValidNN )
          goto LABEL_28;
        goto LABEL_260;
      case 130:
        v290 = *((_DWORD *)v5 + 2);
        v291 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1));
        if ( v5[1] == 0xFB && *(_QWORD *)(v7 + 320) )
        {
          v293 = *((_QWORD *)v5 + 2);
          v292 = *(_QWORD *)(32LL * *(char *)(v291 + 1) + *(_QWORD *)(v7 + 32));
          if ( (v5[2] & 2) != 0 && *(_BYTE *)(v291 + 4) )
          {
            v465 = *(_QWORD *)(v291 + 48);
            getCellInfo(v465);
            *(_QWORD *)(v291 + 80) = *(_QWORD *)(v465 + 48);
          }
        }
        else
        {
          v292 = 0;
          v293 = 0;
        }
        IsValidNN = sqlite3BtreeDelete(*(_QWORD *)(v291 + 48), v5[2]);
        Table = IsValidNN;
        *(_QWORD *)(v291 + 32) = 0;
        if ( (_DWORD)IsValidNN )
        {
          v3 = v620;
          goto LABEL_259;
        }
        ++v629;
        if ( (v290 & 1) != 0 )
        {
          ++v620[7];
          IsValidNN = *(_QWORD *)(v7 + 320);
          if ( IsValidNN )
          {
            if ( v293 && *(char *)(v293 + 48) >= 0 )
              IsValidNN = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, _QWORD, _QWORD))IsValidNN)(
                            *(_QWORD *)(v7 + 312),
                            9,
                            v292,
                            *(_QWORD *)v293,
                            *(_QWORD *)(v291 + 80));
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
        v466 = v3[15];
        v467 = *((unsigned int *)v5 + 4);
        v468 = 56LL * *((int *)v5 + 3);
        v469 = *((int *)v5 + 1);
        LODWORD(v617) = 0;
        IsValidNN = sqlite3VdbeSorterCompare(*(_QWORD *)(v466 + 8 * v469), v6 + v468, v467, &v617);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( (_DWORD)IsValidNN )
          goto LABEL_260;
        if ( !(_DWORD)v617 )
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
        v470 = out2Prerelease(v3, v5);
        v471 = *(_QWORD *)(*(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1)) + 48LL);
        getCellInfo(v471);
        v472 = *(unsigned int *)(v471 + 64);
        if ( (unsigned int)v472 > *(_DWORD *)(v7 + 136) )
          goto LABEL_285;
        IsValidNN = sqlite3VdbeMemFromBtreeZeroOffset(v471, v472, v470);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( (_DWORD)IsValidNN )
          goto LABEL_260;
        if ( *((_DWORD *)v5 + 3) )
          goto LABEL_28;
        IsValidNN = 0x4000;
        if ( (*(_WORD *)(v470 + 20) & 0x4000) == 0 )
          goto LABEL_28;
        IsValidNN = sqlite3VdbeMemMakeWriteable(v470);
        if ( !(_DWORD)IsValidNN )
          goto LABEL_28;
        goto LABEL_393;
      case 135:
        v623 = 0;
        IsValidNN = out2Prerelease(v3, v5);
        v155 = *((int *)v5 + 1);
        v156 = IsValidNN;
        v157 = v3[15];
        v158 = *(_QWORD *)(v157 + 8 * v155);
        if ( !*(_BYTE *)(v158 + 2) )
        {
          if ( *(_BYTE *)(v158 + 3) )
          {
            IsValidNN = *(_QWORD *)(v158 + 80);
          }
          else if ( *(_BYTE *)v158 == 2 )
          {
            v473 = *(__int64 **)(v158 + 48);
            v474 = *v473;
            Table = (*(__int64 (__fastcall **)(__int64 *, signed __int64 *))(*(_QWORD *)*v473 + 96LL))(v473, &v623);
            updated = Table;
            sqlite3VtabImportErrmsg(v3, v474);
            if ( Table )
              goto LABEL_260;
            IsValidNN = v623;
          }
          else
          {
            IsValidNN = sqlite3VdbeCursorRestore(*(_QWORD *)(v157 + 8 * v155));
            Table = IsValidNN;
            updated = IsValidNN;
            if ( (_DWORD)IsValidNN )
              goto LABEL_260;
            if ( *(_BYTE *)(v158 + 2) )
            {
              *(_WORD *)(v156 + 20) = 1;
              goto LABEL_28;
            }
            v217 = *(_QWORD *)(v158 + 48);
            getCellInfo(v217);
            IsValidNN = *(_QWORD *)(v217 + 48);
          }
          *(_QWORD *)v156 = IsValidNN;
          goto LABEL_28;
        }
        *(_WORD *)(IsValidNN + 20) = 1;
        goto LABEL_28;
      case 136:
        v294 = *((int *)v5 + 1);
        IsValidNN = *(_QWORD *)(v3[15] + 8 * v294);
        if ( IsValidNN )
          goto LABEL_478;
        LOBYTE(v16) = 3;
        IsValidNN = allocateCursor(v3, v294, 1, v16);
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
          v295 = *(_QWORD *)(IsValidNN + 48);
          IsValidNN = sqlite3_free(*(_QWORD *)(v295 + 24));
          *(_QWORD *)(v295 + 24) = 0;
          *(_BYTE *)v295 = 1;
        }
        goto LABEL_28;
      case 138:
        v127 = v3[15];
        v1 = 0;
        v128 = *((int *)v5 + 1);
        v626 = 0;
        v627 = 0;
        v628 = 0;
        v129 = *(_QWORD *)(v127 + 8 * v128);
        v130 = v6 + 56LL * *((int *)v5 + 2);
        if ( (v5[2] & 1) != 0 )
          ++v3[7];
        if ( (*(_WORD *)(v130 + 20) & 0x400) != 0 )
        {
          updated = sqlite3VdbeMemExpandBlob(v130);
          if ( updated )
            goto LABEL_260;
        }
        v131 = *((_WORD *)v5 + 1);
        *((_QWORD *)&v626 + 1) = *(int *)(v130 + 16);
        *(_QWORD *)&v626 = *(_QWORD *)(v130 + 8);
        v132 = v6 + 56LL * *((int *)v5 + 3);
        LOWORD(v628) = *((_WORD *)v5 + 8);
        *((_QWORD *)&v627 + 1) = v132;
        v133 = (v131 & 0x10) != 0 ? *(unsigned int *)(v129 + 36) : 0LL;
        IsValidNN = sqlite3BtreeInsert(*(_QWORD *)(v129 + 48), &v626, (unsigned __int8)v131 & 0x8A, v133);
        Table = IsValidNN;
        updated = IsValidNN;
        *(_DWORD *)(v129 + 32) = 0;
        if ( (_DWORD)IsValidNN )
          goto LABEL_260;
        goto LABEL_28;
      case 139:
        v248 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1));
        v249 = v6 + 56LL * *((int *)v5 + 2);
        if ( (*(_WORD *)(v249 + 20) & 0x400) != 0 )
        {
          updated = sqlite3VdbeMemExpandBlob(v6 + 56LL * *((int *)v5 + 2));
          if ( updated )
            goto LABEL_260;
        }
        IsValidNN = sqlite3VdbeSorterWrite(v248, v249, v14, v16);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( (_DWORD)IsValidNN )
          goto LABEL_260;
        goto LABEL_28;
      case 140:
        v273 = *((int *)v5 + 1);
        LODWORD(v617) = 0;
        *(_QWORD *)&v628 = 0;
        v274 = v3[15];
        v1 = 0;
        v626 = 0;
        v627 = 0;
        v275 = *(_QWORD **)(v274 + 8 * v273);
        v276 = v275[6];
        *(_QWORD *)&v626 = v275[7];
        WORD6(v627) = *((_WORD *)v5 + 6);
        v277 = *((int *)v5 + 2);
        BYTE14(v627) = 0;
        *((_QWORD *)&v626 + 1) = v6 + 56 * v277;
        Table = sqlite3BtreeIndexMoveto(v276, &v626, &v617);
        updated = Table;
        if ( Table )
          goto LABEL_260;
        if ( (_DWORD)v617 )
        {
          if ( *((_WORD *)v5 + 1) && !(unsigned int)sqlite3WritableSchema(v7) )
          {
            v476 = "index corruption";
            v477 = 99971;
            v478 = 779;
LABEL_1196:
            updated = sqlite3ReportError(v478, v477, v476);
            goto LABEL_260;
          }
        }
        else
        {
          LOBYTE(v278) = 4;
          Table = sqlite3BtreeDelete(v276, v278);
          updated = Table;
          if ( Table )
            goto LABEL_260;
        }
        IsValidNN = 0;
        v275[4] = 0;
        goto LABEL_28;
      case 141:
      case 142:
        v18 = *((int *)v5 + 1);
        v19 = v3[15];
        v619 = 0;
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
          v619 = 0;
          Table = sqlite3VdbeIdxRowid(v7, *(_QWORD *)(v20 + 48), &v619);
          updated = Table;
          if ( Table )
            goto LABEL_260;
          if ( *v5 == 0x8D )
          {
            v21 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 3));
            *(_BYTE *)(v21 + 2) = 0;
            *(_QWORD *)(v21 + 80) = v619;
            *(_BYTE *)(v21 + 3) = 1;
            *(_DWORD *)(v21 + 32) = 0;
            IsValidNN = *((_QWORD *)v5 + 2);
            *(_QWORD *)(v21 + 16) = IsValidNN;
            *(_QWORD *)(v21 + 40) = v20;
          }
          else
          {
            IsValidNN = out2Prerelease(v3, v5);
            *(_QWORD *)IsValidNN = v619;
          }
        }
        goto LABEL_28;
      case 143:
        IsValidNN = v3[15];
        v479 = *(_QWORD *)(IsValidNN + 8LL * *((int *)v5 + 1));
        if ( !*(_BYTE *)(v479 + 3) )
          goto LABEL_28;
        IsValidNN = sqlite3VdbeFinishMoveto(v479, v8, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( !(_DWORD)IsValidNN )
          goto LABEL_28;
        goto LABEL_260;
      case 144:
        LODWORD(v617) = 0;
        v480 = out2Prerelease(v3, v5);
        *(_WORD *)(v480 + 20) = 1;
        if ( *(_DWORD *)(v7 + 220) > *(_DWORD *)(v7 + 232) + 1 )
        {
          updated = 6;
          *((_BYTE *)v3 + 196) = 2;
          goto LABEL_260;
        }
        v481 = *((_DWORD *)v5 + 3);
        v482 = *(_QWORD *)(v7 + 32);
        v483 = *((unsigned int *)v5 + 1);
        LODWORD(v617) = 0;
        updated = sqlite3BtreeDropTable(*(_QWORD *)(32LL * (int)v481 + v482 + 8), v483, &v617);
        Table = updated;
        *(_WORD *)(v480 + 20) = 4;
        IsValidNN = (int)v617;
        *(_QWORD *)v480 = (int)v617;
        if ( updated )
          goto LABEL_260;
        if ( (_DWORD)v617 )
        {
          sqlite3RootPageMoved(v7, v481, (unsigned int)v617, *((unsigned int *)v5 + 1));
          IsValidNN = v481 + 1;
          v613 = v481 + 1;
        }
        goto LABEL_28;
      case 145:
        v484 = *(_QWORD *)(v7 + 32);
        v485 = *((unsigned int *)v5 + 1);
        v486 = 32LL * *((int *)v5 + 2);
        v623 = 0;
        IsValidNN = sqlite3BtreeClearTable(*(_QWORD *)(v486 + v484 + 8), v485, &v623);
        updated = IsValidNN;
        Table = IsValidNN;
        if ( *((_DWORD *)v5 + 3) )
        {
          v487 = v623;
          v3[7] += v623;
          IsValidNN = *((int *)v5 + 3);
          if ( (int)IsValidNN > 0 )
            *(_QWORD *)(56 * IsValidNN + v6) += v487;
        }
        if ( !updated )
          goto LABEL_28;
        goto LABEL_260;
      case 146:
        v488 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1));
        if ( *(_BYTE *)v488 == 1 )
        {
          IsValidNN = sqlite3VdbeSorterReset(v7, *(_QWORD *)(v488 + 48), 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
        }
        else
        {
          IsValidNN = sqlite3BtreeClearTable(
                        *(_QWORD *)(*(_QWORD *)(v488 + 48) + 8LL),
                        *(unsigned int *)(*(_QWORD *)(v488 + 48) + 80LL),
                        0);
          Table = IsValidNN;
          updated = IsValidNN;
          if ( (_DWORD)IsValidNN )
            goto LABEL_260;
        }
        goto LABEL_28;
      case 147:
        LODWORD(v617) = 0;
        v489 = out2Prerelease(v3, v5);
        v490 = *(_QWORD *)(v7 + 32);
        v491 = (_QWORD *)v489;
        v492 = *((unsigned int *)v5 + 3);
        v493 = 32LL * *((int *)v5 + 1);
        LODWORD(v617) = 0;
        IsValidNN = sqlite3BtreeCreateTable(*(_QWORD *)(v493 + v490 + 8), &v617, v492);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( (_DWORD)IsValidNN )
          goto LABEL_260;
        *v491 = (unsigned int)v617;
        goto LABEL_28;
      case 148:
        ++*(_BYTE *)(v7 + 112);
        v49 = (v5[4] & 1) == 0;
        v344 = *(_QWORD *)(v7 + 512);
        v345 = *(_BYTE *)(v7 + 110);
        v346 = *(_DWORD *)(v7 + 744);
        v619 = 0;
        if ( !v49 )
        {
          *(_QWORD *)(v7 + 512) = 0;
          *(_BYTE *)(v7 + 110) = 0;
        }
        if ( (v5[4] & 2) != 0 )
          *(_DWORD *)(v7 + 744) = *((_DWORD *)v5 + 2);
        IsValidNN = sqlite3_exec(v7, *((_QWORD *)v5 + 2), 0, 0, (__int64)&v619);
        v347 = (const char *)v619;
        --*(_BYTE *)(v7 + 112);
        *(_DWORD *)(v7 + 744) = v346;
        updated = IsValidNN;
        Table = IsValidNN;
        *(_QWORD *)(v7 + 512) = v344;
        *(_BYTE *)(v7 + 110) = v345;
        if ( !v347 && !(_DWORD)IsValidNN )
          goto LABEL_28;
        sqlite3VdbeError(v3, "%s", v347);
        sqlite3_free(v619);
        if ( updated != 7 )
          goto LABEL_260;
        goto LABEL_393;
      case 149:
        v494 = *((_QWORD *)v5 + 2);
        v495 = *((int *)v5 + 1);
        v1 = 0;
        *(_QWORD *)&v628 = 0;
        v626 = 0;
        v627 = 0;
        if ( v494 )
        {
          v496 = *(_QWORD *)(v7 + 32);
          *(_QWORD *)&v626 = v7;
          LODWORD(v627) = v495;
          *((_QWORD *)&v626 + 1) = v3 + 21;
          DWORD2(v627) = 0;
          LODWORD(v628) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(32 * v495 + v496 + 8) + 8LL) + 64LL);
          v497 = sqlite3MPrintf(
                   v7,
                   "SELECT*FROM\"%w\".%s WHERE %s ORDER BY rowid",
                   *(_QWORD *)(32 * v495 + v496),
                   "sqlite_master",
                   v494);
          if ( !v497 )
          {
            sqlite3ResetAllSchemasOfConnection(v7);
            goto LABEL_393;
          }
          *(_BYTE *)(v7 + 197) = 1;
          DWORD1(v627) = 0;
          HIDWORD(v627) = 0;
          Table = sqlite3_exec(v7, v497, (unsigned int)sqlite3InitCallback, (unsigned int)&v626, 0);
          updated = Table;
          if ( !Table )
          {
            updated = DWORD1(v627);
            Table = DWORD1(v627);
            if ( !DWORD1(v627) && !HIDWORD(v627) )
            {
              updated = sqlite3ReportError(11, 100469, "database corruption");
              Table = updated;
            }
          }
          IsValidNN = sqlite3DbFreeNN(v7, v497);
          *(_BYTE *)(v7 + 197) = 0;
        }
        else
        {
          sqlite3SchemaClear(*(_QWORD *)(32 * v495 + *(_QWORD *)(v7 + 32) + 24), v8, 0x180000000uLL);
          *(_DWORD *)(v7 + 44) &= ~0x10u;
          IsValidNN = sqlite3InitOne(v7, (unsigned int)v495, v3 + 21, *((unsigned __int16 *)v5 + 1));
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
        v361 = out2Prerelease(v3, v5);
        *(_WORD *)(v361 + 20) = 8;
        IsValidNN = *((_QWORD *)v5 + 2);
        *(_QWORD *)v361 = *(_QWORD *)IsValidNN;
        goto LABEL_28;
      case 155:
        v498 = *((int *)v5 + 1);
        v499 = *((_QWORD *)v5 + 2);
        v500 = 56 * v498;
        v501 = v498 + 1;
        LODWORD(v617) = 0;
        v502 = *(_QWORD *)(v7 + 32);
        v503 = 56 * *((_DWORD *)v5 + 3);
        v619 = 0;
        v504 = v6 + 56LL * v501;
        Table = sqlite3BtreeIntegrityCheck(
                  v7,
                  *(_QWORD *)(32LL * *((unsigned __int16 *)v5 + 1) + v502 + 8),
                  (int)v499 + 4,
                  (int)v6 + v503,
                  *((_DWORD *)v5 + 2),
                  *(_DWORD *)(v500 + v6) + 1,
                  (__int64)&v617,
                  (__int64)&v619);
        updated = Table;
        sqlite3VdbeMemSetNull(v504);
        if ( !(_DWORD)v617 )
          goto LABEL_992;
        if ( Table )
          goto LABEL_1199;
        LOBYTE(v505) = 1;
        *(_QWORD *)(v500 + v6) -= (int)v617 - 1;
        sqlite3VdbeMemSetStr(v504, v619, -1, v505, sqlite3_free);
LABEL_992:
        sqlite3VdbeChangeEncoding(v504, v615);
        v15 = v624;
        goto LABEL_33;
      case 156:
        v506 = *((int *)v5 + 1);
        v507 = *((int *)v5 + 2);
        v508 = v6 + 56 * v506;
        if ( (*(_BYTE *)(v508 + 20) & 0x10) == 0
          && (unsigned int)sqlite3VdbeMemSetRowSet(v6 + 56 * v506, v8, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL) )
        {
          goto LABEL_393;
        }
        IsValidNN = sqlite3RowSetInsert(*(_QWORD *)(v508 + 8), *(_QWORD *)(56 * v507 + v6), v14, v16);
        goto LABEL_28;
      case 157:
        v514 = out2Prerelease(v3, v5);
        IsValidNN = sqlite3VdbeMemShallowCopy(
                      v514,
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
        v515 = v3[33];
        if ( v515 )
        {
          for ( ; *(_QWORD *)(v515 + 8); v515 = *(_QWORD *)(v515 + 8) )
            ;
          v516 = *(_QWORD *)(v515 + 24) + 56LL * *((int *)v5 + 1);
        }
        else
        {
          v516 = v6 + 56LL * *((int *)v5 + 1);
        }
        *(_QWORD *)v516 = sqlite3_value_int64(v516);
        *(_WORD *)(v516 + 20) &= 0xF244u;
        *(_WORD *)(v516 + 20) |= 4u;
        v517 = v6 + 56LL * *((int *)v5 + 2);
        IsValidNN = sqlite3_value_int64(v517);
        *(_WORD *)(v517 + 20) &= 0xF244u;
        *(_WORD *)(v517 + 20) |= 4u;
        *(_QWORD *)v517 = IsValidNN;
        if ( *(_QWORD *)v516 < IsValidNN )
          *(_QWORD *)v516 = IsValidNN;
        goto LABEL_28;
      case 160:
        v518 = *((int *)v5 + 3);
        v519 = 56LL * *((int *)v5 + 1);
        v619 = 0;
        IsValidNN = out2Prerelease(v3, v5);
        v520 = (_QWORD *)IsValidNN;
        v619 = *(_QWORD *)(v519 + v6);
        if ( v619 <= 0 )
          goto LABEL_1034;
        v521 = *(_QWORD *)(56 * v518 + v6);
        if ( v521 <= 0 )
          v521 = 0;
        IsValidNN = sqlite3AddInt64(&v619, v521);
        if ( (_DWORD)IsValidNN )
        {
LABEL_1034:
          *v520 = -1;
        }
        else
        {
          IsValidNN = v619;
          *v520 = v619;
        }
        goto LABEL_28;
      case 161:
      case 162:
        v523 = *((unsigned __int16 *)v5 + 1);
        v524 = sqlite3DbMallocRawNN(v7, 8 * v523 + 104);
        if ( !v524 )
          goto LABEL_393;
        v525 = v524 + 8 * (v523 + 6);
        *(_QWORD *)v524 = v525;
        *(_WORD *)(v525 + 20) = 1;
        *(_QWORD *)(v525 + 24) = v7;
        *(_DWORD *)(v525 + 32) = 0;
        *(_QWORD *)(v524 + 16) = 0;
        *(_QWORD *)(v524 + 8) = *((_QWORD *)v5 + 2);
        *(_QWORD *)(v524 + 24) = v3;
        *(_DWORD *)(v524 + 32) = -1431655765 * ((__int64)&v5[-v616] >> 3);
        *(_BYTE *)(v524 + 40) = v615;
        *(_BYTE *)(v524 + 41) = 0;
        *(_DWORD *)(v524 + 36) = 0;
        *(_BYTE *)(v524 + 42) = v523;
        *(_WORD *)v5 = -3677;
        *((_QWORD *)v5 + 2) = v524;
        goto LABEL_340;
      case 163:
LABEL_340:
        v218 = (_DWORD *)*((_QWORD *)v5 + 2);
        v219 = v6 + 56LL * *((int *)v5 + 3);
        if ( *((_QWORD *)v218 + 2) != v219 )
        {
          v526 = (unsigned int)*((unsigned __int8 *)v218 + 42) - 1;
          for ( *((_QWORD *)v218 + 2) = v219; (int)v526 >= 0; v526 = (unsigned int)(v526 - 1) )
            *(_QWORD *)&v218[2 * v526 + 12] = v6 + 56LL * ((int)v526 + *((_DWORD *)v5 + 2));
        }
        ++*(_DWORD *)(v219 + 16);
        v220 = v218 + 12;
        v221 = *((_QWORD *)v218 + 1);
        v222 = *((unsigned __int8 *)v218 + 42);
        if ( *((_DWORD *)v5 + 1) )
          (*(void (__fastcall **)(_DWORD *, __int64, _DWORD *, unsigned __int64))(v221 + 48))(v218, v222, v220, v16);
        else
          (*(void (__fastcall **)(_DWORD *, __int64, _DWORD *, unsigned __int64))(v221 + 24))(v218, v222, v220, v16);
        IsValidNN = (unsigned int)v218[9];
        if ( !(_DWORD)IsValidNN )
          goto LABEL_28;
        if ( (int)IsValidNN > 0 )
        {
          LOBYTE(v223) = 1;
          v224 = (const char *)sqlite3ValueText(*(_QWORD *)v218, v223);
          sqlite3VdbeError(v3, "%s", v224);
          updated = v218[9];
          Table = updated;
        }
        if ( *((_BYTE *)v218 + 41) )
        {
          v225 = *((int *)v5 - 5);
          if ( (_DWORD)v225 )
            sqlite3VdbeMemSetInt64(v6 + 56 * v225);
          *((_BYTE *)v218 + 41) = 0;
        }
        sqlite3VdbeMemRelease(*(_QWORD *)v218);
        IsValidNN = *(_QWORD *)v218;
        *(_WORD *)(*(_QWORD *)v218 + 20LL) = 1;
        v218[9] = 0;
        if ( !updated )
          goto LABEL_28;
        goto LABEL_260;
      case 164:
      case 165:
        v245 = *((int *)v5 + 3);
        v246 = v6 + 56LL * *((int *)v5 + 1);
        if ( (_DWORD)v245 )
        {
          updated = sqlite3VdbeMemAggValue(
                      v6 + 56LL * *((int *)v5 + 1),
                      v6 + 56 * v245,
                      *((_QWORD *)v5 + 2),
                      0xAAAAAAAAAAAAAAABuLL);
          Table = updated;
          v246 = v6 + 56LL * *((int *)v5 + 3);
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
          LOBYTE(v247) = 1;
          v605 = sqlite3ValueText(v246, v247);
          sqlite3VdbeError(v3, "%s", v605);
          goto LABEL_260;
        }
        IsValidNN = sqlite3VdbeChangeEncoding(v246, v615);
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
        v542 = v5[12];
        if ( !(_BYTE)v542 )
        {
          IsValidNN = 0x400000000LL;
          if ( (*(_QWORD *)(v7 + 48) & 0x400000000LL) != 0 )
            goto LABEL_28;
        }
        IsValidNN = sqlite3BtreeLockTable(
                      *(_QWORD *)(32LL * *((int *)v5 + 1) + *(_QWORD *)(v7 + 32) + 8),
                      *((unsigned int *)v5 + 2),
                      v542,
                      0xAAAAAAAAAAAAAAABuLL);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( !(_DWORD)IsValidNN )
          goto LABEL_28;
        if ( (_BYTE)IsValidNN == 6 )
          sqlite3VdbeError(v3, "database table is locked: %s", *((_QWORD *)v5 + 2));
        goto LABEL_260;
      case 170:
        v543 = *((_QWORD *)v5 + 2);
        IsValidNN = sqlite3VtabBegin(v7, v543, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( v543 )
          IsValidNN = sqlite3VtabImportErrmsg(v3, *(_QWORD *)(v543 + 16));
        if ( !updated )
          goto LABEL_28;
        goto LABEL_260;
      case 171:
        v544 = *((int *)v5 + 2);
        v1 = 0;
        v635 = 0;
        memset(v634, 0, 24);
        v636 = 0;
        *((_QWORD *)&v634[1] + 1) = v7;
        v545 = sqlite3VdbeMemCopy(v634, v6 + 56 * v544, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
        LOBYTE(v546) = 1;
        Table = v545;
        updated = v545;
        v547 = sqlite3ValueText(v634, v546);
        if ( v547 )
        {
          updated = sqlite3VtabCallCreate(v7, *((unsigned int *)v5 + 1), v547, v3 + 21);
          Table = updated;
        }
        IsValidNN = sqlite3VdbeMemRelease(v634);
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
        v548 = *((_QWORD *)v5 + 2);
        v619 = 0;
        v549 = *(__int64 **)(v548 + 16);
        if ( !v549 || (v550 = *v549) == 0 )
        {
LABEL_1206:
          updated = 6;
          goto LABEL_260;
        }
        Table = (*(__int64 (__fastcall **)(__int64 *, __int64 *, unsigned __int64, unsigned __int64))(v550 + 48))(
                  v549,
                  &v619,
                  0x180000000uLL,
                  0xAAAAAAAAAAAAAAABuLL);
        updated = Table;
        sqlite3VtabImportErrmsg(v3, v549);
        if ( Table )
          goto LABEL_260;
        LOBYTE(v551) = 2;
        *(_QWORD *)v619 = v549;
        IsValidNN = allocateCursor(v3, *((unsigned int *)v5 + 1), 0, v551);
        if ( IsValidNN )
        {
          *(_QWORD *)(IsValidNN + 48) = v619;
          ++*((_DWORD *)v549 + 2);
          goto LABEL_28;
        }
        (*(void (__fastcall **)(__int64))(v550 + 56))(v619);
        goto LABEL_393;
      case 174:
        v96 = *((int *)v5 + 2);
        v619 = 0;
        v97 = v6 + 56 * v96;
        IsValidNN = sqlite3VdbeMemSetNull(v97);
        v98 = (_QWORD *)*((_QWORD *)v5 + 2);
        v99 = v98[10];
        if ( !v99 )
          goto LABEL_28;
        v100 = *(__int64 **)(v99 + 16);
        v101 = *v100;
        ++*(_DWORD *)(v99 + 24);
        updated = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, __int64 *))(v101 + 192))(
                    v100,
                    *(_QWORD *)(32LL * *((int *)v5 + 1) + *(_QWORD *)(v7 + 32)),
                    *v98,
                    *((unsigned int *)v5 + 3),
                    &v619);
        Table = updated;
        IsValidNN = sqlite3VtabUnlock(v98[10]);
        if ( updated )
        {
LABEL_1199:
          sqlite3_free(v619);
          goto LABEL_260;
        }
        if ( v619 )
        {
          LOBYTE(v102) = 1;
          IsValidNN = sqlite3VdbeMemSetStr(v97, v619, -1, v102, sqlite3_free);
        }
        goto LABEL_28;
      case 175:
        v552 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1));
        v553 = (_QWORD *)sqlite3_malloc64(16);
        v554 = v553;
        if ( !v553 )
          goto LABEL_393;
        *v553 = *(_QWORD *)(v552 + 48);
        v553[1] = v6 + 56LL * *((int *)v5 + 3);
        v555 = out2Prerelease(v3, v5);
        *(_WORD *)(v555 + 20) = 1;
        IsValidNN = sqlite3VdbeMemSetPointer(v555, v554, "ValueList", sqlite3VdbeValueListFree);
        goto LABEL_28;
      case 176:
        v1 = 0;
        v643 = 0;
        memset(v641, 0, sizeof(v641));
        v645 = 0;
        v646 = 0;
        v642 = 0;
        memset_0(&v644, 0, 0x45u);
        v569 = *(_QWORD *)(v3[15] + 8LL * *((int *)v5 + 1));
        v390 = v6 + 56LL * *((int *)v5 + 3);
        if ( *(_BYTE *)(v569 + 2) )
        {
LABEL_1112:
          IsValidNN = sqlite3VdbeMemSetNull(v390);
          goto LABEL_28;
        }
        v49 = (v5[2] & 1) == 0;
        v570 = **(__int64 ***)(v569 + 48);
        v571 = *v570;
        *(_QWORD *)&v641[0] = v6 + 56LL * *((int *)v5 + 3);
        BYTE8(v642) = v615;
        v647 = 0x1000000;
        *((_QWORD *)&v641[0] + 1) = &v644;
        if ( v49 )
        {
          v572 = *(_WORD *)(v390 + 20) & 0xF240 | 1;
        }
        else
        {
          sqlite3VdbeMemSetNull(v390);
          v572 = 1025;
          *(_DWORD *)v390 = 0;
        }
        *(_WORD *)(v390 + 20) = v572;
        v573 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *, _QWORD))(v571 + 88))(
                 *(_QWORD *)(v569 + 48),
                 v641,
                 *((unsigned int *)v5 + 2));
        v3 = v620;
        Table = v573;
        sqlite3VtabImportErrmsg(v620, v570);
        if ( SDWORD1(v642) <= 0 )
        {
          updated = Table;
        }
        else
        {
          LOBYTE(v574) = 1;
          v575 = (const char *)sqlite3ValueText(v390, v574);
          sqlite3VdbeError(v3, "%s", v575);
          updated = DWORD1(v642);
          Table = DWORD1(v642);
        }
        IsValidNN = sqlite3VdbeChangeEncoding(v390, v615);
        if ( !updated )
          goto LABEL_28;
        goto LABEL_260;
      case 177:
        v581 = *(_DWORD *)(v7 + 48);
        *(_QWORD *)(v7 + 48) |= 0x4000000uLL;
        v582 = *(_QWORD *)(*((_QWORD *)v5 + 2) + 16LL);
        v583 = v6 + 56LL * *((int *)v5 + 1);
        Table = sqlite3VdbeChangeEncoding(v583, 1);
        if ( Table )
          goto LABEL_259;
        Table = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v582 + 152LL))(v582, *(_QWORD *)(v583 + 8));
        if ( (v581 & 0x4000000) == 0 )
          *(_QWORD *)(v7 + 48) &= ~0x4000000uLL;
        IsValidNN = sqlite3VtabImportErrmsg(v3, v582);
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
        v592 = (_QWORD *)out2Prerelease(v3, v5);
        v593 = *((_DWORD *)v5 + 3);
        v594 = *(_QWORD *)(32LL * *((int *)v5 + 1) + *(_QWORD *)(v7 + 32) + 8);
        v595 = 0;
        if ( v593 )
        {
          v595 = *(unsigned int *)(*(_QWORD *)(v594 + 8) + 64LL);
          if ( (unsigned int)v595 < v593 )
            v595 = v593;
        }
        IsValidNN = (unsigned int)sqlite3BtreeMaxPageCount(v594, v595);
        *v592 = (unsigned int)IsValidNN;
        goto LABEL_28;
      case 180:
        IsValidNN = 63487;
        *(_WORD *)(56LL * *((int *)v5 + 1) + v6 + 20) &= ~0x800u;
        goto LABEL_28;
      case 181:
        v50 = v6 + 56LL * *((int *)v5 + 2);
        if ( (*(_WORD *)(56LL * *((int *)v5 + 1) + v6 + 20) & 0x800) == 0 )
          goto LABEL_1166;
        IsValidNN = sqlite3VdbeMemSetInt64(v50);
        goto LABEL_28;
      case 182:
        v596 = 56LL * *((int *)v5 + 1);
        v597 = 56LL * *((int *)v5 + 2);
        if ( (*(_BYTE *)(v596 + v6 + 20) & 1) != 0 )
        {
          IsValidNN = 63487;
          *(_WORD *)(v597 + v6 + 20) &= ~0x800u;
        }
        else
        {
          *(_WORD *)(v597 + v6 + 20) |= 0x800u;
          IsValidNN = *(unsigned __int8 *)(v596 + v6);
          *(_BYTE *)(v597 + v6 + 23) = IsValidNN;
        }
        goto LABEL_28;
      case 183:
        v134 = 56LL * *((int *)v5 + 1);
        v135 = filterHash(v6, v5, 0x180000000uLL, 0xAAAAAAAAAAAAAAABuLL);
        v136 = *(_QWORD *)(v134 + v6 + 8);
        v137 = (v135 % (8 * *(_DWORD *)(v134 + v6 + 16))) & 7;
        v138 = (v135 % (8 * *(_DWORD *)(v134 + v6 + 16))) >> 3;
        IsValidNN = (unsigned int)*(char *)(v138 + v136);
        LODWORD(IsValidNN) = IsValidNN | (1 << v137);
        *(_BYTE *)(v138 + v136) = IsValidNN;
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
