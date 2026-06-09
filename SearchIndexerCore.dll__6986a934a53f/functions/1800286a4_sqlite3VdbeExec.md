# sqlite3VdbeExec

- ea: `0x1800286a4`
- end: `0x18002ecbb`
- name: `sqlite3VdbeExec`
- size: `26135`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `154`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180028360`
- `0x18007a8f0`

## callees

- `0x18000a710`
- `0x18000e818`
- `0x180015460`
- `0x18001eb90`
- `0x18001f740`
- `0x18001ff40`
- `0x1800201c0`
- `0x1800203a4`
- `0x1800205e0`
- `0x180022400`
- `0x1800226f0`
- `0x180022760`
- `0x180022790`
- `0x180022f90`
- `0x180024810`
- `0x180024840`
- `0x180024860`
- `0x180024880`
- `0x180024b60`
- `0x180024d90`
- `0x1800257e0`
- `0x180025a20`
- `0x18002619c`
- `0x1800286a4`
- `0x180031e2c`
- `0x180031f24`
- `0x180031f78`
- `0x180032060`
- `0x180032470`
- `0x1800325b0`
- `0x180033018`
- `0x180033ab0`
- `0x180034660`
- `0x1800348b0`
- `0x180034ad0`
- `0x180034b60`
- `0x180035550`
- `0x1800355a0`
- `0x1800356d4`
- `0x180035d1c`
- `0x1800391a0`
- `0x18003d380`
- `0x18003d990`
- `0x18003e860`
- `0x18003ecc0`
- `0x18003eed4`
- `0x18003f048`
- `0x18003f490`
- `0x18003f560`
- `0x18003faa8`

## string_xrefs

- `0x18002e87a`: `cannot open savepoint - SQL statements in progress`
- `0x18002e871`: `cannot commit transaction - SQL statements in progress`
- `0x18002e8a3`: `cannot rollback - no transaction is active`
- `0x18002e8aa`: `cannot commit - no transaction is active`

## pseudocode

```c
__int64 __fastcall sqlite3VdbeExec(__int64 *a1, unsigned __int64 a2, __int64 a3, __int64 a4)
{
  __int128 v4; // xmm0
  __int64 v5; // r15
  __int64 v6; // r10
  __int64 *v7; // r13
  __int64 v8; // r8
  unsigned __int8 *v9; // rdi
  __int64 v10; // r14
  unsigned __int64 v11; // rsi
  __int64 v12; // r11
  int v13; // eax
  __int64 v14; // rax
  unsigned int v15; // r12d
  __int64 v16; // rbx
  unsigned __int64 v17; // rsi
  __int64 v18; // r13
  __int64 v19; // r15
  __int16 v20; // r14
  unsigned __int16 v21; // si
  __int64 v22; // rdx
  char v23; // cl
  unsigned __int8 v24; // al
  int v25; // eax
  char v26; // cl
  int v27; // ebx
  int v28; // ebx
  int v29; // ebx
  int v30; // ebx
  __int64 v31; // rbx
  unsigned int v32; // eax
  unsigned __int64 ii; // rsi
  __int64 v34; // rcx
  int v35; // ebx
  __int64 v36; // rax
  unsigned int v37; // r14d
  __int64 v38; // rbx
  unsigned int *v39; // r13
  unsigned __int16 *v40; // rsi
  __int64 v41; // rdx
  __int64 v42; // rax
  __int64 v43; // rsi
  unsigned int v44; // eax
  unsigned int *v45; // r15
  unsigned __int8 *Payload; // rcx
  int *v47; // r14
  unsigned int v48; // eax
  int v49; // eax
  __int64 v50; // rcx
  __int64 v51; // r12
  unsigned __int8 *v52; // rsi
  unsigned int v53; // edi
  unsigned __int64 v54; // r14
  unsigned __int64 v55; // r15
  __int64 v56; // rax
  int v57; // esi
  __int64 v58; // rsi
  __int64 *v59; // r14
  __int64 *v60; // rcx
  int v61; // eax
  __int64 v62; // rax
  size_t v63; // rbx
  __int64 v64; // rdx
  int v65; // ebx
  int v66; // ebx
  int v67; // ebx
  __int64 *v68; // rax
  __int64 v69; // rcx
  __int64 v70; // rax
  unsigned int v71; // eax
  __int64 v72; // rax
  __int64 v73; // rsi
  _QWORD *v74; // rbx
  __int64 v75; // rcx
  __int64 *v76; // r10
  __int64 v77; // rax
  int v78; // ebx
  bool v79; // zf
  int v80; // ebx
  int v81; // ebx
  int v82; // ebx
  char v83; // al
  int v84; // eax
  int v85; // r12d
  __int64 v86; // r15
  __int64 v87; // rcx
  __int64 v88; // rax
  __int64 v89; // r13
  int v90; // r14d
  unsigned __int8 v91; // al
  __int64 v92; // rbx
  __int64 v93; // r8
  __int64 Cursor; // rax
  __int64 v95; // rsi
  __int64 v96; // rcx
  unsigned int v97; // eax
  int v98; // ebx
  int v99; // ebx
  char *v100; // rsi
  char v101; // al
  __int64 i; // rbx
  int v103; // ebx
  int v104; // ebx
  __int64 v105; // r14
  __int64 v106; // rsi
  __int64 v107; // rbx
  unsigned int v108; // eax
  int v109; // ebx
  int v110; // ebx
  int v111; // ebx
  int v112; // ebx
  __int64 v113; // rsi
  int v114; // eax
  __int64 v115; // rbx
  int v116; // ebx
  int v117; // ebx
  int v118; // ebx
  int v119; // ebx
  bool v120; // zf
  __int64 v121; // rcx
  int v122; // ecx
  unsigned int v123; // eax
  unsigned __int64 v124; // rdx
  int v126; // ebx
  int v127; // ebx
  int v128; // ebx
  __int64 v129; // rcx
  __int64 v130; // rax
  int v131; // ebx
  int v132; // ebx
  int v133; // ebx
  int v134; // ebx
  __int64 v135; // rax
  __int64 v136; // rcx
  __int64 v137; // rax
  __int64 v138; // r14
  _QWORD *v139; // rsi
  int HasHint; // eax
  int v141; // r15d
  BOOL v142; // r13d
  __int64 v143; // rax
  unsigned int v144; // eax
  _DWORD *v145; // rbx
  __int64 v146; // r8
  _DWORD *v147; // r8
  __int64 v148; // rax
  __int64 v149; // rdx
  __int64 v150; // rdx
  int v151; // eax
  const char *v152; // rax
  __int64 v153; // rcx
  __int64 v154; // rax
  __int64 v155; // rdx
  __int64 v156; // rcx
  __int64 v157; // rbx
  __int64 v158; // rdx
  unsigned int v159; // eax
  int v160; // ebx
  int v161; // ecx
  int v162; // ebx
  __int64 v163; // rcx
  __int64 v164; // rax
  __int64 v165; // rbx
  __int64 v166; // rcx
  int *v167; // r14
  int v168; // ecx
  int m; // edx
  int v170; // ebx
  __int64 v171; // rdx
  char *v172; // rsi
  __int64 v173; // r15
  __int64 v174; // r13
  int v175; // r12d
  int v176; // eax
  int *v177; // r13
  __int64 v178; // r14
  int v179; // eax
  int *v180; // r14
  int *j; // rbx
  __int16 v182; // cx
  unsigned __int64 v183; // rdx
  __int64 v184; // rax
  int v185; // edx
  __int64 v186; // rcx
  __int64 v187; // rax
  __int64 v188; // rsi
  int v189; // r12d
  __int64 v190; // rbx
  __int64 v191; // r15
  int v192; // eax
  _BYTE *v193; // rsi
  _BYTE *v194; // rbx
  _BYTE *v195; // r14
  unsigned __int64 v196; // rsi
  __int64 v197; // rax
  int v198; // eax
  __int64 v199; // rsi
  __int64 v200; // rbx
  __int64 v201; // rcx
  unsigned int v202; // eax
  unsigned __int64 v203; // rcx
  __int64 v204; // rdx
  int v205; // eax
  int v206; // eax
  int v207; // eax
  int v208; // eax
  unsigned int v209; // eax
  int v210; // eax
  __int64 v211; // rdx
  __int64 v212; // rcx
  __int64 v213; // rax
  int v214; // esi
  __int64 v215; // rbx
  __int16 v216; // r14
  __int16 v217; // r14
  __int64 v218; // rax
  __int64 v219; // rcx
  __int64 v220; // rsi
  __int64 v221; // rbx
  __int16 v222; // r8
  __int64 v223; // rcx
  __int64 v224; // r9
  unsigned int v225; // eax
  bool v226; // zf
  int v227; // ebx
  int v228; // ecx
  char v229; // al
  unsigned int v230; // r14d
  unsigned int v231; // esi
  int v232; // ebx
  int v233; // ebx
  __int64 v234; // rcx
  __int64 v235; // rax
  __int64 v236; // rbx
  unsigned int v237; // eax
  unsigned int v238; // eax
  __int64 v239; // rdx
  __int64 v240; // rcx
  int v241; // r14d
  __int64 v242; // rsi
  __int64 jj; // rbx
  __int16 v244; // ax
  int v245; // ebx
  int v246; // ebx
  __int64 v247; // rbx
  __int64 v248; // rdx
  int v249; // eax
  unsigned __int8 v250; // cl
  int v251; // ebx
  int v252; // ebx
  __int64 v253; // rsi
  __int64 v254; // rax
  int v255; // edx
  __int64 v256; // rsi
  __int16 v257; // r15
  __int64 v258; // rax
  __int16 v259; // cx
  __int64 v260; // r12
  unsigned int v261; // ecx
  char v262; // al
  __int64 v263; // rcx
  __int64 v264; // rax
  _QWORD *v265; // rbx
  __int64 v266; // rsi
  __int64 v267; // rax
  unsigned int v268; // eax
  unsigned int v269; // eax
  int v270; // ebx
  __int64 v271; // r15
  __int64 v272; // r13
  _QWORD *v273; // rax
  __int64 v274; // r14
  unsigned int v275; // esi
  unsigned int v276; // ebx
  __int64 v277; // rax
  unsigned int v278; // eax
  __int64 v279; // rdx
  __int64 v280; // rax
  const char *v281; // rax
  int v282; // r8d
  int v283; // edx
  unsigned int v284; // eax
  __int64 v285; // rsi
  __int64 v286; // rbx
  int v287; // r8d
  unsigned int v288; // eax
  unsigned int v289; // ebx
  const void *v290; // rsi
  __int64 v291; // r14
  unsigned int v292; // eax
  _QWORD *v293; // rax
  _QWORD *v294; // rbx
  __int64 v295; // rax
  _QWORD *v296; // r14
  unsigned int v297; // r13d
  int v298; // eax
  _QWORD *v299; // r12
  int v300; // esi
  unsigned int v301; // eax
  unsigned int v302; // eax
  int *v303; // r15
  int v304; // r12d
  int v305; // ebx
  int v306; // esi
  unsigned int v307; // eax
  int v308; // ebx
  unsigned int v309; // r12d
  _QWORD *v310; // rcx
  unsigned int v311; // eax
  __int64 v312; // r9
  int v313; // ebx
  __int64 v314; // rcx
  __int64 *v315; // rbx
  int v316; // r9d
  __int64 v317; // rdx
  char v318; // si
  __int64 v319; // r8
  __int64 v320; // rcx
  __int64 v321; // rax
  __int16 v322; // ax
  __int64 v323; // rdx
  __int64 v324; // rsi
  int *v325; // r11
  __int64 v326; // r13
  int v327; // r9d
  __int64 v328; // rdx
  __int64 **v329; // rbx
  __int64 *v330; // r15
  __int64 v331; // r14
  __int64 v332; // rax
  int v333; // eax
  __int64 v334; // rcx
  int v335; // ebx
  int v336; // ebx
  int v337; // ebx
  int v338; // ebx
  int v339; // eax
  bool v340; // zf
  __int64 v341; // r8
  unsigned __int64 v342; // rcx
  unsigned int v343; // edx
  int v344; // eax
  int v345; // eax
  int v346; // eax
  __int64 v347; // rax
  __int64 v348; // rbx
  __int16 v349; // ax
  __int64 v350; // rdx
  __int64 v351; // rcx
  __int64 v352; // rcx
  __int64 v353; // rdx
  __int64 v354; // rcx
  __int64 v355; // rdx
  __int64 v356; // rbx
  __int64 v357; // rcx
  __int64 v358; // rcx
  __int16 v359; // ax
  int v360; // ecx
  unsigned int v361; // eax
  int v362; // eax
  unsigned int v363; // eax
  __int64 v364; // rcx
  __int64 v365; // rax
  __int64 v366; // rbx
  unsigned int v367; // eax
  __int64 v368; // rcx
  __int64 v369; // rax
  __int64 v370; // rdx
  __int64 v371; // r8
  __int64 v372; // r9
  __int64 v373; // rcx
  __int128 v374; // xmm1
  __int64 v375; // rax
  __int64 v376; // rsi
  __int64 v377; // rcx
  __int64 v378; // rax
  __int64 v379; // rbx
  unsigned int v380; // eax
  int v381; // ebx
  int v382; // eax
  int v383; // ebx
  __int64 *v384; // rax
  __int64 v385; // r8
  __int64 v386; // rdx
  __int16 v387; // cx
  __int16 v388; // cx
  bool v389; // zf
  __int64 v390; // r8
  __int64 n; // rax
  int *v392; // r15
  int *v393; // r12
  __int64 v394; // rbx
  int v395; // r14d
  int v396; // r13d
  __int64 v397; // rsi
  __int64 v398; // rcx
  __int64 *v399; // rbx
  __int64 v400; // rdx
  __int64 v401; // rcx
  void *v402; // rcx
  int v403; // eax
  int v404; // esi
  __int64 v405; // rbx
  __int64 v406; // r14
  int v407; // eax
  __int64 v408; // r14
  bool v409; // sf
  int v410; // eax
  __int64 v411; // rax
  __int64 v412; // rbx
  bool v413; // zf
  unsigned int v414; // eax
  __int64 v415; // rcx
  __int64 v416; // rax
  __int64 v417; // rdx
  __int64 v418; // rcx
  __int64 v419; // rsi
  __int64 **v420; // rcx
  __int64 *v421; // rbx
  __int64 v422; // r14
  int v423; // eax
  int v424; // ebx
  int v425; // ebx
  int v426; // ebx
  __int64 v427; // rax
  __int64 v428; // rbx
  __int64 v429; // rsi
  int v430; // edx
  __int64 v431; // rdx
  int v432; // eax
  const char *v433; // rax
  __int64 v434; // rbx
  unsigned __int64 v435; // rax
  unsigned __int64 v436; // rdx
  int v437; // r8d
  unsigned __int8 v438; // cf
  int v439; // ebx
  __int64 v440; // rax
  __int64 v441; // rdx
  __int64 v442; // rax
  __int64 v443; // rax
  int v444; // eax
  int v445; // r14d
  __int64 v446; // rsi
  __int64 v447; // rbx
  int v448; // eax
  __int64 v449; // rax
  __int64 v450; // rdx
  __int64 v451; // rbx
  int v452; // eax
  __int64 v453; // rcx
  __int64 v454; // rbx
  __int64 v455; // rax
  int v456; // ebx
  int v457; // ebx
  int v458; // ebx
  __int64 v459; // rsi
  unsigned __int64 v460; // r8
  int v461; // ebx
  int v462; // eax
  int v463; // ecx
  int v464; // edx
  __int64 v465; // r12
  int v466; // r13d
  __int64 v467; // r15
  unsigned int v468; // eax
  __int64 v469; // rbx
  unsigned int v470; // eax
  __int64 v471; // rax
  __int64 v472; // rbx
  __int64 v473; // rcx
  __int64 v474; // rax
  __int64 v475; // rcx
  unsigned int v476; // eax
  __int64 *v477; // rax
  char v478; // al
  __int64 *v479; // rbx
  __int16 v480; // ax
  __int64 v481; // rax
  int v482; // eax
  unsigned __int64 v483; // rcx
  unsigned __int64 v484; // rcx
  __int16 v485; // cx
  __int16 v486; // cx
  int v487; // r15d
  __int64 v488; // r12
  __int64 v489; // r14
  __int64 v490; // rsi
  __int16 v491; // cx
  bool v492; // zf
  __int16 v493; // cx
  __int64 v494; // rdx
  int v495; // eax
  unsigned int v496; // eax
  __int64 v497; // rcx
  int v498; // eax
  int v499; // eax
  __int64 v500; // rcx
  unsigned int v501; // r9d
  unsigned int v502; // eax
  __int64 v503; // rcx
  __int64 v504; // rdx
  __int64 v505; // rax
  __int64 v506; // rsi
  __int64 v507; // rdx
  __int64 v508; // r14
  __int64 v509; // rbx
  __int64 v510; // rsi
  __int64 v511; // rbx
  unsigned int updated; // eax
  __int64 v513; // rbx
  __int64 v514; // rax
  char v515; // cl
  __int64 v516; // rdx
  int v517; // ebx
  int v518; // ebx
  int v519; // ebx
  __int64 v520; // rax
  __int64 v521; // rsi
  __int64 v522; // r14
  __int64 v523; // r15
  __int16 v524; // dx
  unsigned __int8 v525; // bl
  int v526; // ecx
  __int64 v527; // rdx
  __int64 v528; // r8
  int v529; // ecx
  int v530; // ecx
  int v531; // ecx
  __int128 v532; // rax
  int v533; // eax
  __int16 v534; // ax
  double v535; // xmm7_8
  __int128 v536; // xmm6
  __int64 v537; // rbx
  __int64 v538; // rax
  double v539; // xmm6_8
  int IsNaN; // eax
  __int16 v541; // ax
  __int64 v542; // r13
  __int16 v543; // r12
  __int64 v544; // rbx
  __int64 v545; // rsi
  int v546; // eax
  __int16 v547; // r14
  int v548; // eax
  unsigned __int64 v549; // r15
  __int64 v550; // rbx
  __int64 v551; // rax
  int v552; // ecx
  __int64 v553; // rsi
  __int64 v554; // rbx
  __int64 v555; // rax
  __int64 v556; // rdx
  __int64 v557; // rbx
  int v558; // ebx
  int v559; // ebx
  int v560; // ebx
  int v561; // ebx
  __int64 v562; // rax
  __int64 v563; // rdx
  __int64 v564; // rcx
  __int64 v565; // rax
  __int64 v566; // rdx
  __int64 v567; // rbx
  __int64 v568; // rdx
  __int64 v569; // rcx
  unsigned int v570; // eax
  __int64 v571; // rax
  _QWORD *v572; // rsi
  unsigned int v573; // eax
  unsigned int v574; // eax
  __int64 v575; // r15
  _DWORD *v576; // r14
  __int64 v577; // rcx
  unsigned int Table; // eax
  __int64 v579; // rax
  __int64 v580; // rbx
  int v581; // eax
  __int64 v582; // r9
  __int64 v583; // rax
  int v584; // ebx
  int v585; // ebx
  int v586; // ebx
  int v587; // ebx
  __int64 v588; // rcx
  __int64 v589; // rdx
  __int64 v590; // rax
  __int64 v591; // rbx
  __int64 v592; // r8
  _QWORD *v593; // rsi
  __int64 v594; // r14
  __int16 v595; // r8
  __int64 v596; // r9
  unsigned int v597; // eax
  __int64 *v598; // r14
  __int64 v599; // rsi
  unsigned int v600; // eax
  __int64 v601; // rbx
  __int64 v602; // rax
  __int64 v603; // rcx
  __int64 v604; // rbx
  __int64 v605; // rax
  __int64 v606; // rcx
  __int64 v607; // rax
  int v608; // ebx
  unsigned int v609; // eax
  _QWORD *v610; // rax
  __int64 v611; // rdx
  __int64 v612; // rdx
  int v613; // eax
  __int64 v614; // rcx
  __int64 v615; // rax
  __int64 v616; // rbx
  int v617; // eax
  int v618; // esi
  __int64 v619; // rax
  unsigned int v620; // eax
  bool v621; // sf
  __int64 v622; // rcx
  unsigned int v623; // eax
  __int64 v624; // r8
  int v625; // ebx
  int v626; // ebx
  int v627; // ebx
  int v628; // ebx
  __int64 v629; // rsi
  __int64 v630; // rbx
  __int64 v631; // rdx
  unsigned int v632; // eax
  int Writeable; // eax
  unsigned int v634; // eax
  __int64 v635; // rcx
  __int64 v636; // r8
  __int64 v637; // rdx
  __int64 v638; // rax
  unsigned int v639; // eax
  __int64 v640; // rax
  int v641; // r12d
  __int64 v642; // rsi
  __int64 v643; // r14
  __int64 v644; // r15
  __int64 v645; // rbx
  unsigned int v646; // eax
  void (__fastcall *v647)(_QWORD, __int64, __int64, _QWORD, _QWORD); // rax
  __int64 v648; // r8
  __int64 v649; // rax
  __int64 v650; // rdx
  __int64 v651; // rcx
  __int64 v652; // rsi
  __int64 v653; // rbx
  __int64 v654; // rax
  __int64 *v655; // rcx
  __int64 v656; // rbx
  unsigned int v657; // eax
  __int64 v658; // rbx
  __int64 v659; // rsi
  __int64 v660; // rbx
  unsigned int v661; // eax
  __int64 v662; // rcx
  __int64 v663; // rax
  __int64 v664; // rsi
  __int64 v665; // r14
  __int64 v666; // rcx
  int IsValidNN; // eax
  unsigned int v668; // eax
  __int64 v669; // rdx
  __int64 v670; // rax
  __int64 v671; // rbx
  unsigned int v672; // eax
  int v673; // eax
  const char *v674; // r8
  __int64 v675; // rdx
  __int64 v676; // rcx
  int v677; // ebx
  int v678; // ebx
  __int64 v679; // rcx
  __int64 v680; // rdx
  __int64 v681; // rax
  unsigned int v682; // eax
  __int64 v683; // rbx
  unsigned int v684; // esi
  __int64 v685; // rcx
  __int64 v686; // rdx
  __int64 v687; // rcx
  __int64 v688; // r8
  int v689; // ebx
  int v690; // ebx
  int v691; // ebx
  int v692; // ebx
  __int64 v693; // r9
  __int64 v694; // rbx
  unsigned int inited; // eax
  __int64 v696; // r8
  __int64 v697; // rax
  __int64 v698; // rbx
  __int64 v699; // rbx
  char v700; // si
  int v701; // r14d
  unsigned int v702; // eax
  const char *v703; // r8
  __int64 v704; // rax
  __int64 v705; // rcx
  _QWORD *v706; // rbx
  __int64 v707; // r8
  __int64 v708; // r9
  unsigned int v709; // eax
  int v710; // ebx
  int v711; // ebx
  int v712; // ebx
  int v713; // ebx
  __int64 v714; // rax
  __int64 v715; // rsi
  __int64 v716; // rbx
  __int64 v717; // rdx
  __int64 v718; // r8
  __int64 v719; // rsi
  int v720; // eax
  __int64 v721; // rdx
  int v722; // r9d
  __int64 v723; // rbx
  __int64 v724; // r9
  __int64 (__fastcall *v725)(_QWORD); // rax
  __int64 v726; // rbx
  int v727; // eax
  __int64 v728; // rcx
  __int64 v729; // r14
  __int64 v730; // rbx
  __int64 v731; // rdx
  __int64 v732; // rdx
  int v733; // eax
  __int64 v734; // rcx
  __int64 v735; // rsi
  __int64 v736; // rbx
  __int64 v737; // rax
  int v738; // ebx
  int v739; // ebx
  __int64 v740; // rax
  __int64 v741; // rax
  unsigned int v742; // eax
  int v743; // ebx
  int v744; // ebx
  int v745; // ebx
  __int64 v746; // rax
  __int64 *v747; // rbx
  __int64 v748; // rsi
  __int64 v749; // r9
  __int64 v750; // rax
  __int64 v751; // rax
  unsigned int v752; // eax
  __int64 v753; // rdx
  __int64 v754; // rax
  __int64 v755; // rbx
  unsigned int v756; // eax
  int v757; // ebx
  int v758; // ebx
  int v759; // ebx
  int v760; // ebx
  unsigned int v761; // r8d
  __int64 v762; // r9
  int v763; // r14d
  __int64 v764; // rbx
  __int64 v765; // rsi
  unsigned int v766; // eax
  __int64 v767; // rsi
  __int64 *v768; // r14
  __int64 v769; // r15
  __int16 v770; // ax
  __int64 v771; // rdx
  __int64 v772; // rsi
  _QWORD *v773; // rax
  _QWORD *v774; // rbx
  __int64 v775; // rax
  int v776; // ebx
  int v777; // ebx
  int v778; // ebx
  __int64 v779; // rbx
  __int64 v780; // rbx
  int k; // ecx
  __int64 v782; // rax
  __int64 v783; // rbx
  unsigned __int64 v784; // rax
  unsigned __int64 v785; // r8
  __int64 v786; // rdx
  __int64 v787; // rcx
  const char *v788; // r8
  const char *v789; // rdx
  const char *v790; // rdx
  unsigned int v791; // eax
  const char *v792; // rax
  __int64 (__fastcall *v793)(__int64); // rax
  __int64 v794; // rcx
  int v795; // eax
  unsigned __int8 v796; // [rsp+48h] [rbp-C0h]
  unsigned int v797; // [rsp+4Ch] [rbp-BCh]
  unsigned int v798; // [rsp+50h] [rbp-B8h]
  __int64 v799; // [rsp+58h] [rbp-B0h]
  __int64 v800; // [rsp+60h] [rbp-A8h]
  __int64 v801; // [rsp+68h] [rbp-A0h]
  __int64 v803; // [rsp+78h] [rbp-90h] BYREF
  __int64 v804; // [rsp+80h] [rbp-88h] BYREF
  __int64 v805; // [rsp+88h] [rbp-80h] BYREF
  unsigned int v806; // [rsp+90h] [rbp-78h] BYREF
  char v807; // [rsp+94h] [rbp-74h]
  unsigned __int64 v808; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int64 v809; // [rsp+A0h] [rbp-68h]
  __int128 v810; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v811; // [rsp+B8h] [rbp-50h]
  __int128 v812; // [rsp+C8h] [rbp-40h]
  int v813; // [rsp+D8h] [rbp-30h]
  int v814; // [rsp+DCh] [rbp-2Ch] BYREF
  __int64 v815; // [rsp+E0h] [rbp-28h] BYREF
  unsigned __int64 v816; // [rsp+E8h] [rbp-20h]
  unsigned int *v817; // [rsp+F0h] [rbp-18h]
  __int128 v818; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v819; // [rsp+108h] [rbp+0h]
  __int128 v820; // [rsp+118h] [rbp+10h]
  __int64 v821; // [rsp+128h] [rbp+20h]
  __int128 v822; // [rsp+130h] [rbp+28h] BYREF
  __int128 v823; // [rsp+140h] [rbp+38h]
  __int128 v824; // [rsp+150h] [rbp+48h]
  __int64 v825; // [rsp+160h] [rbp+58h]
  _OWORD v826[2]; // [rsp+168h] [rbp+60h] BYREF
  __int128 v827; // [rsp+188h] [rbp+80h]
  __int64 v828; // [rsp+198h] [rbp+90h]
  char v829; // [rsp+1A8h] [rbp+A0h] BYREF
  __int16 v830; // [rsp+1A9h] [rbp+A1h]
  char v831; // [rsp+1ABh] [rbp+A3h]
  int v832; // [rsp+1ACh] [rbp+A4h]
  int v833; // [rsp+1F8h] [rbp+F0h]
  __int64 v834; // [rsp+1FCh] [rbp+F4h] BYREF

  v5 = *a1;
  v6 = 0;
  v7 = a1;
  v8 = a1[17];
  v9 = (unsigned __int8 *)v8;
  v10 = a1[13];
  v11 = 0;
  LOBYTE(a4) = *(_BYTE *)(*a1 + 100);
  v796 = a4;
  v799 = v8;
  v801 = *a1;
  v807 = 0;
  v809 = 0;
  v800 = v10;
  if ( *((_DWORD *)a1 + 52) )
  {
    sqlite3VdbeEnter();
    LOBYTE(a4) = v796;
    v8 = (__int64)v9;
    v6 = 0;
  }
  if ( *(_QWORD *)(v5 + 528) )
  {
    HIDWORD(a2) = 0;
    v261 = *(_DWORD *)(v5 + 544);
    LODWORD(a2) = *((_DWORD *)v7 + 57) % v261;
    v816 = v261 - (unsigned int)a2;
  }
  else
  {
    v816 = -1;
  }
  v12 = 1;
  if ( *((_DWORD *)v7 + 13) == 7 )
    goto LABEL_1455;
  *((_DWORD *)v7 + 13) = 0;
  v7[9] = 0;
  v13 = *(_DWORD *)(v5 + 408);
  *(_DWORD *)(v5 + 664) = 0;
  if ( v13 )
    goto LABEL_1449;
  v14 = *((int *)v7 + 12);
  a2 = 0;
  v15 = 0;
  v798 = 0;
  v797 = 0;
  v813 = 0;
  v9 = (unsigned __int8 *)(v8 + 24 * v14);
LABEL_8:
  v16 = *v9;
  v17 = v12 + v11;
  v808 = (unsigned __int64)v9;
  v809 = v17;
  if ( (_DWORD)v16 == 92 )
  {
    if ( ((unsigned __int8)v12 & *(_BYTE *)(56LL * *((int *)v9 + 1) + v10 + 20)) == 0
      && ((unsigned __int8)v12 & *(_BYTE *)(56LL * *((int *)v9 + 3) + v10 + 20)) == 0 )
    {
      v62 = *((int *)v9 + 2);
LABEL_111:
      v34 = v10 + 56 * v62;
      goto LABEL_112;
    }
LABEL_46:
    v34 = v10 + 56LL * *((int *)v9 + 2);
    goto LABEL_47;
  }
  if ( (unsigned int)v16 > 0x5C )
  {
    if ( (unsigned int)v16 <= 0x8C )
    {
      if ( (_DWORD)v16 == 140 )
      {
        v263 = *((int *)v9 + 1);
        LODWORD(v803) = 0;
        *(_QWORD *)&v812 = 0;
        v264 = v7[15];
        v4 = 0;
        v810 = 0;
        v811 = 0;
        v265 = *(_QWORD **)(v264 + 8 * v263);
        v266 = v265[6];
        *(_QWORD *)&v810 = v265[7];
        WORD6(v811) = *((_WORD *)v9 + 6);
        v267 = *((int *)v9 + 2);
        BYTE14(v811) = 0;
        *((_QWORD *)&v810 + 1) = v10 + 56 * v267;
        v268 = sqlite3BtreeIndexMoveto(v266, &v810, &v803);
        v6 = 0;
        v798 = v268;
        v15 = v268;
        if ( v268 )
          goto LABEL_1459;
        if ( (_DWORD)v803 )
        {
          if ( *((_WORD *)v9 + 1) )
          {
            v673 = sqlite3WritableSchema(v5);
            v6 = 0;
            if ( !v673 )
            {
              v674 = "index corruption";
              v675 = 99937;
              v676 = 779;
              goto LABEL_1430;
            }
          }
        }
        else
        {
          LOBYTE(a2) = 4;
          v672 = sqlite3BtreeDelete(v266, a2);
          v6 = 0;
          v798 = v672;
          v15 = v672;
          if ( v672 )
            goto LABEL_1459;
        }
        v265[4] = 0;
        goto LABEL_49;
      }
      if ( (unsigned int)v16 <= 0x74 )
      {
        if ( (_DWORD)v16 != 116 )
        {
          if ( (unsigned int)v16 <= 0x69 )
          {
            if ( (_DWORD)v16 == 105 )
              goto LABEL_964;
            if ( (unsigned int)v16 <= 0x63 )
            {
              if ( (_DWORD)v16 == 99 )
              {
                v503 = *(_QWORD *)(v5 + 32);
                v504 = *((unsigned int *)v9 + 3);
                v505 = 32LL * *((int *)v9 + 1);
                LODWORD(v803) = 0;
                sqlite3BtreeGetMeta(*(_QWORD *)(v505 + v503 + 8), v504, &v803);
                v68 = (__int64 *)out2Prerelease(v7, v9);
                v69 = (int)v803;
                goto LABEL_133;
              }
              v35 = v16 - 94;
              if ( !v35 )
              {
                v4 = 0;
                v806 = 0;
                v822 = 0;
                v825 = 0;
                v36 = v7[15];
                v823 = 0;
                v824 = 0;
                v37 = *((_DWORD *)v9 + 2);
                v38 = *(_QWORD *)(v36 + 8LL * *((int *)v9 + 1));
                while ( 1 )
                {
                  LODWORD(v805) = v37;
                  while ( 1 )
                  {
                    v39 = *(unsigned int **)(v38 + 88);
                    v817 = v39;
                    if ( *(_DWORD *)(v38 + 32) != *((_DWORD *)a1 + 11) )
                      break;
                    if ( !(unsigned int)sqlite3BtreeEof(*(_QWORD *)(v38 + 48)) )
                    {
                      v40 = (unsigned __int16 *)(v38 + 74);
                      goto LABEL_66;
                    }
LABEL_77:
                    v44 = sqlite3VdbeHandleMovedCursor(v38);
                    v6 = 0;
                    v798 = v44;
                    v15 = v44;
                    if ( v44 )
                      goto LABEL_1458;
                  }
                  if ( *(_BYTE *)(v38 + 2) )
                  {
                    if ( *(_BYTE *)v38 == 3 && *(int *)(v38 + 36) > 0 )
                    {
                      v45 = (unsigned int *)(v38 + 108);
                      v497 = 56LL * *(int *)(v38 + 36);
                      v498 = *(_DWORD *)(v497 + v800 + 16);
                      *(_DWORD *)(v38 + 108) = v498;
                      *(_DWORD *)(v38 + 104) = v498;
                      Payload = *(unsigned __int8 **)(v497 + v800 + 8);
LABEL_80:
                      v47 = (int *)(v38 + 64);
                      *(_QWORD *)(v38 + 96) = Payload;
                      *(_DWORD *)(v38 + 32) = *((_DWORD *)a1 + 11);
                      v48 = *Payload;
                      *v39 = v48;
                      if ( v48 >= 0x80 )
                      {
                        LOBYTE(v49) = sqlite3GetVarint32(*(_QWORD *)(v38 + 96), v39);
                        v6 = 0;
                        v49 = (unsigned __int8)v49;
                        v12 = 1;
                      }
                      else
                      {
                        v12 = 1;
                        v49 = 1;
                      }
                      v40 = (unsigned __int16 *)(v38 + 74);
                      *v47 = v49;
                      *(_WORD *)(v38 + 74) = 0;
                      if ( *v45 >= *v39 )
                      {
                        v50 = *(_QWORD *)(v38 + 96);
                        goto LABEL_84;
                      }
                      *(_QWORD *)(v38 + 96) = 0;
                      *v45 = 0;
                      if ( *v39 > 0x18003 || *v39 > *(_DWORD *)(v38 + 104) )
                        goto LABEL_945;
                      v37 = v805;
LABEL_66:
                      if ( *v40 > v37 )
                      {
                        v41 = *(unsigned int *)(v38 + 4LL * v37 + 120);
                        v806 = *(_DWORD *)(v38 + 4LL * v37 + 120);
                        goto LABEL_95;
                      }
                      v47 = (int *)(v38 + 64);
                      if ( *(_DWORD *)(v38 + 64) >= *v39 )
                      {
                        v41 = 0;
                        v806 = 0;
                      }
                      else
                      {
                        v50 = *(_QWORD *)(v38 + 96);
                        v804 = v50;
                        if ( !v50 )
                        {
                          v4 = 0;
                          v822 = 0;
                          v823 = 0;
                          v825 = 0;
                          v824 = 0;
                          v71 = sqlite3VdbeMemFromBtreeZeroOffset(*(_QWORD *)(v38 + 48), *v39, &v822);
                          v6 = 0;
                          v798 = v71;
                          v15 = v71;
                          if ( v71 )
                            goto LABEL_1458;
                          v50 = *((_QWORD *)&v822 + 1);
LABEL_84:
                          v804 = v50;
                        }
                        v51 = *v40;
                        v12 = 1;
                        v52 = (unsigned __int8 *)(v50 + (unsigned int)*v47);
                        v53 = v805;
                        v54 = v50 + *v39;
                        v55 = v39[v51];
                        do
                        {
                          v806 = *v52;
                          *(_DWORD *)(v38 + 4LL * (int)v51 + 120) = v806;
                          if ( v806 >= 0x80 )
                          {
                            v52 += (unsigned __int8)sqlite3GetVarint32(v52, &v806);
                            *(_DWORD *)(v38 + 4LL * (int)v51 + 120) = v806;
                            v56 = (unsigned int)sqlite3VdbeSerialTypeLen(v806);
                            v12 = 1;
                          }
                          else
                          {
                            ++v52;
                            v56 = *((unsigned __int8 *)qword_1800B6000 + (unsigned __int8)v806);
                          }
                          v39 = v817;
                          v55 += v56;
                          LODWORD(v51) = v51 + 1;
                          v817[(int)v51] = v55;
                        }
                        while ( (unsigned int)v51 <= v53 && (unsigned __int64)v52 < v54 );
                        v9 = (unsigned __int8 *)v808;
                        if ( (unsigned __int64)v52 < v54 )
                        {
                          if ( v55 <= *(unsigned int *)(v38 + 104) )
                            goto LABEL_91;
LABEL_418:
                          v6 = 0;
                          if ( !*v39 )
                          {
                            LOWORD(v51) = 0;
                            LODWORD(v52) = v54;
                            goto LABEL_91;
                          }
                          if ( !*(_QWORD *)(v38 + 96) )
                          {
                            sqlite3VdbeMemRelease(&v822);
                            v6 = 0;
                            v12 = 1;
                          }
LABEL_945:
                          v8 = v799;
                          v499 = *(_DWORD *)(v799 + 12);
                          if ( v499 > 0 )
                          {
                            v15 = v798;
                            v9 = (unsigned __int8 *)(v799 + 24LL * (v499 - 1));
                            goto LABEL_71;
                          }
                          v791 = sqlite3ReportError(11, 96591, "database corruption");
                          v7 = a1;
LABEL_1439:
                          v15 = v791;
LABEL_393:
                          v6 = 0;
                          goto LABEL_1459;
                        }
                        if ( (unsigned __int64)v52 > v54 || v55 != *(_DWORD *)(v38 + 104) )
                          goto LABEL_418;
LABEL_91:
                        v57 = (_DWORD)v52 - v804;
                        *(_WORD *)(v38 + 74) = v51;
                        *(_DWORD *)(v38 + 64) = v57;
                        if ( !*(_QWORD *)(v38 + 96) )
                          sqlite3VdbeMemRelease(&v822);
                        v41 = v806;
                      }
                      v37 = v805;
                      if ( *(unsigned __int16 *)(v38 + 74) > (unsigned int)v805 )
                      {
LABEL_95:
                        v58 = v800 + 56LL * *((int *)v9 + 3);
                        if ( (*(_WORD *)(v58 + 20) & 0x9000) != 0 )
                        {
                          sqlite3VdbeMemSetNull(v800 + 56LL * *((int *)v9 + 3));
                          v41 = v806;
                        }
                        if ( *(_DWORD *)(v38 + 108) >= v39[v37 + 1] )
                        {
                          v59 = (__int64 *)(*(_QWORD *)(v38 + 96) + v39[v37]);
                          if ( (unsigned int)v41 < 0xC )
                          {
                            v60 = v59;
                            goto LABEL_100;
                          }
                          v5 = v801;
                          v63 = (unsigned int)(v41 - 12) >> 1;
                          *(_DWORD *)(v58 + 16) = v63;
                          *(_BYTE *)(v58 + 22) = v796;
                          v64 = (unsigned int)(v63 + 2);
                          if ( *(_DWORD *)(v58 + 32) >= (int)v64 )
                          {
                            *(_QWORD *)(v58 + 8) = *(_QWORD *)(v58 + 40);
LABEL_117:
                            memcpy_0(*(void **)(v58 + 8), v59, v63);
                            v15 = v798;
                            v6 = 0;
                            v7 = a1;
                            *(_BYTE *)(v63 + *(_QWORD *)(v58 + 8)) = 0;
                            v12 = 1;
                            *(_BYTE *)(v63 + *(_QWORD *)(v58 + 8) + 1) = 0;
                            *(_WORD *)(v58 + 20) = word_1800BF8F4[v806 & 1];
                            goto LABEL_118;
                          }
                          if ( (int)v63 <= *(_DWORD *)(v801 + 136) )
                          {
                            *(_WORD *)(v58 + 20) = 1;
                            if ( !(unsigned int)sqlite3VdbeMemGrow(v58, v64, 0) )
                              goto LABEL_117;
LABEL_269:
                            v7 = a1;
LABEL_1455:
                            sqlite3OomFault(v5);
                            sqlite3VdbeError(v7, "out of memory");
                            v15 = 7;
                            goto LABEL_393;
                          }
LABEL_1442:
                          v7 = a1;
LABEL_1443:
                          sqlite3VdbeError(v7, "string or blob too big");
                          v15 = 18;
                          goto LABEL_393;
                        }
                        *(_BYTE *)(v58 + 22) = v796;
                        v41 = v806;
                        v262 = v9[2] & 0xC0;
                        if ( !v262 || v262 != (char)0x80 && (v806 < 0xC || (v806 & 1) != 0 && v262 != -64) )
                        {
                          if ( !(unsigned int)sqlite3VdbeSerialTypeLen(v806) )
                          {
                            v41 = v806;
                            goto LABEL_459;
                          }
                          v501 = v39[v37];
                          v7 = a1;
                          v502 = vdbeColumnFromOverflow(v38, v37, v806, v501, *((_DWORD *)a1 + 11), v813, v58);
                          v6 = 0;
                          v798 = v502;
                          v15 = v502;
                          if ( v502 )
                          {
                            if ( v502 != 7 )
                            {
                              if ( v502 != 18 )
                                goto LABEL_1459;
                              goto LABEL_1443;
                            }
LABEL_1454:
                            v5 = v801;
                            goto LABEL_1455;
                          }
LABEL_493:
                          v5 = v801;
LABEL_198:
                          v10 = v800;
LABEL_49:
                          LOBYTE(a4) = v796;
                          goto LABEL_50;
                        }
LABEL_459:
                        v60 = &qword_1800B4FF0;
LABEL_100:
                        sqlite3VdbeSerialGet(v60, v41, v58);
                        v15 = v798;
                        v7 = a1;
LABEL_101:
                        v5 = v801;
LABEL_102:
                        v10 = v800;
LABEL_48:
                        v6 = 0;
                        goto LABEL_49;
                      }
                      v10 = v800;
                      v500 = v800 + 56LL * *((int *)v9 + 3);
                      if ( v9[1] == 0xF6 )
                        sqlite3VdbeMemShallowCopy(v500, *((_QWORD *)v9 + 2), 0x2000);
                      else
                        sqlite3VdbeMemSetNull(v500);
                      v15 = v798;
                      v5 = v801;
                    }
                    else
                    {
                      v10 = v800;
                      sqlite3VdbeMemSetNull(v800 + 56LL * *((int *)v9 + 3));
                    }
LABEL_502:
                    v7 = a1;
                    goto LABEL_48;
                  }
                  v43 = *(_QWORD *)(v38 + 48);
                  if ( !*(_BYTE *)(v38 + 3) )
                    break;
                  v494 = *(_QWORD *)(v38 + 16);
                  if ( !v494 || (v495 = *(_DWORD *)(v494 + 4LL * (v37 + 1))) == 0 )
                  {
                    v496 = sqlite3VdbeFinishMoveto(v38);
                    v6 = 0;
                    v798 = v496;
                    v15 = v496;
                    if ( !v496 )
                    {
LABEL_79:
                      getCellInfo(v43);
                      v45 = (unsigned int *)(v38 + 108);
                      *(_DWORD *)(v38 + 104) = *(_DWORD *)(v43 + 64);
                      Payload = (unsigned __int8 *)fetchPayload(v43, v38 + 108);
                      v6 = 0;
                      goto LABEL_80;
                    }
LABEL_1458:
                    v7 = a1;
                    goto LABEL_1459;
                  }
                  v38 = *(_QWORD *)(v38 + 40);
                  v37 = v495 - 1;
                }
                if ( !(unsigned int)sqlite3BtreeEof(*(_QWORD *)(v38 + 48)) )
                  goto LABEL_79;
                goto LABEL_77;
              }
              v98 = v35 - 1;
              if ( v98 )
              {
                v99 = v98 - 1;
                if ( !v99 )
                {
                  v100 = (char *)*((_QWORD *)v9 + 2);
                  v101 = *v100;
                  for ( i = v10 + 56LL * *((int *)v9 + 1); ; i += 56 )
                  {
                    LOBYTE(v8) = a4;
                    LOBYTE(a2) = v101;
                    applyAffinity(i, a2, v8);
                    if ( *v100 == 69 )
                    {
                      v485 = *(_WORD *)(i + 20);
                      if ( (v485 & 4) != 0 )
                      {
                        a2 = *(_QWORD *)i;
                        v8 = 0xFFFFFFFFFFFFLL;
                        if ( (unsigned __int64)(*(_QWORD *)i + 0x800000000000LL) > 0xFFFFFFFFFFFFLL )
                        {
                          v4 = 0;
                          v486 = v485 & 0xFFF1 | 8;
                          *(double *)i = (double)(int)a2;
                        }
                        else
                        {
                          v486 = v485 & 0xFFDB | 0x20;
                        }
                        *(_WORD *)(i + 20) = v486;
                      }
                    }
                    LOBYTE(a4) = v796;
                    v12 = 1;
                    ++v100;
                    v6 = 0;
                    v101 = *v100;
                    if ( !*v100 )
                      break;
                  }
LABEL_43:
                  a2 = v797;
LABEL_44:
                  v8 = v799;
                  goto LABEL_51;
                }
                v170 = v99 - 1;
                if ( v170 )
                {
                  if ( v170 != 1 )
                    goto LABEL_51;
                  v473 = *((int *)v9 + 1);
                  v474 = v7[15];
                  v804 = 0;
                  v475 = *(_QWORD *)(v474 + 8 * v473);
                  if ( *((_DWORD *)v9 + 3) )
                  {
                    v804 = sqlite3BtreeRowCountEst(*(_QWORD *)(v475 + 48));
                  }
                  else
                  {
                    v476 = sqlite3BtreeCount(v5, *(_QWORD *)(v475 + 48), &v804);
                    v6 = 0;
                    v798 = v476;
                    v15 = v476;
                    if ( v476 )
                      goto LABEL_1459;
                  }
                  v477 = (__int64 *)out2Prerelease(v7, v9);
                  *v477 = v804;
                  goto LABEL_1307;
                }
                v171 = 0;
                v172 = (char *)*((_QWORD *)v9 + 2);
                v173 = 0;
                v174 = 56LL * *((int *)v9 + 1);
                v175 = 0;
                v176 = *((_DWORD *)v9 + 2) - v12;
                LODWORD(v804) = 0;
                v177 = (int *)(v10 + v174);
                v178 = 14LL * v176;
                v179 = *((_DWORD *)v9 + 3);
                v180 = &v177[v178];
                v805 = 0;
                v808 = (unsigned __int64)v180;
                LODWORD(v803) = v179;
                if ( v172 )
                {
                  v478 = *v172;
                  v479 = (__int64 *)v177;
                  do
                  {
                    LOBYTE(v8) = v796;
                    LOBYTE(v171) = v478;
                    applyAffinity(v479, v171, v8);
                    if ( *v172 == 69 )
                    {
                      v480 = *((_WORD *)v479 + 10);
                      if ( (v480 & 4) != 0 )
                        *((_WORD *)v479 + 10) = v480 & 0xFFDB | 0x20;
                    }
                    v12 = 1;
                    v479 += 7;
                    v478 = *++v172;
                  }
                  while ( *v172 );
                  v175 = v804;
                  v171 = v805;
                  v180 = (int *)v808;
                }
                for ( j = v180; ; j -= 14 )
                {
                  v182 = *((_WORD *)j + 10);
                  if ( ((unsigned __int8)v182 & (unsigned __int8)v12) != 0 )
                  {
                    j[9] = (v182 & 0x400) != 0 ? 0xA : 0;
                    v175 += v12;
                  }
                  else
                  {
                    if ( (v182 & 0x24) != 0 )
                    {
                      v183 = *(_QWORD *)j;
                      if ( *(__int64 *)j < 0 )
                        v183 = ~v183;
                      v175 += v12;
                      if ( v183 <= 0x7F )
                      {
                        if ( (v12 & *(_QWORD *)j) == *(_QWORD *)j && *((_BYTE *)a1 + 197) >= 4u )
                        {
                          v185 = v183 + 8;
                        }
                        else
                        {
                          v173 += v12;
                          v185 = v12;
                        }
                        v187 = 36;
                        v186 = (__int64)j;
                      }
                      else
                      {
                        if ( v183 <= 0x7FFF )
                        {
                          v184 = 2;
                          goto LABEL_297;
                        }
                        if ( v183 > 0x7FFFFF )
                        {
                          if ( v183 > 0x7FFFFFFF )
                          {
                            if ( v183 > 0x7FFFFFFFFFFFLL )
                            {
                              v173 += 8;
                              if ( (v182 & 0x20) != 0 )
                              {
                                v4 = 0;
                                *(double *)&v4 = (double)(int)*(_QWORD *)j;
                                v185 = 7;
                                *((_WORD *)j + 10) = v182 & 0xFFD7 | 8;
                                *(_QWORD *)j = v4;
                              }
                              else
                              {
                                v185 = 6;
                              }
                            }
                            else
                            {
                              v173 += 6;
                              v185 = 5;
                            }
                          }
                          else
                          {
                            v184 = 4;
LABEL_297:
                            v173 += v184;
                            v185 = v184;
                          }
                        }
                        else
                        {
                          v173 += 3;
                          v185 = 3;
                        }
                        v186 = 36;
                        v187 = (__int64)j;
                      }
                      *(_DWORD *)(v186 + v187) = v185;
                      goto LABEL_300;
                    }
                    if ( (v182 & 8) != 0 )
                    {
                      v175 += v12;
                      j[9] = 7;
                      v173 += 8;
                    }
                    else
                    {
                      v230 = j[4];
                      v231 = ((v182 & 2 | 0x18u) >> 1) + 2 * v230;
                      if ( (v182 & 0x400) != 0 )
                      {
                        v481 = *j;
                        v231 += 2 * v481;
                        if ( v173 )
                        {
                          if ( (unsigned int)sqlite3VdbeMemExpandBlob(j) )
                            goto LABEL_1453;
                          v230 += *j;
                        }
                        else
                        {
                          v805 = v481 + v171;
                        }
                      }
                      v173 += v230;
                      v175 += sqlite3VarintLen_0(v231);
                      j[9] = v231;
                      v12 = 1;
                    }
                  }
LABEL_300:
                  if ( j == v177 )
                  {
                    v188 = v800 + 56LL * (int)v803;
                    if ( v175 > 126 )
                    {
                      v482 = sqlite3VarintLen_0(v175);
                      v189 = v482 + v175;
                      if ( v482 < (int)sqlite3VarintLen_0(v189) )
                        ++v189;
                    }
                    else
                    {
                      v189 = v12 + v175;
                    }
                    v190 = v189 + v173;
                    v191 = v805;
                    if ( v190 + v805 <= *(int *)(v188 + 32) )
                    {
                      v6 = 0;
                      *(_QWORD *)(v188 + 8) = *(_QWORD *)(v188 + 40);
                      goto LABEL_309;
                    }
                    if ( v190 + v805 > *(int *)(v801 + 136) )
                      goto LABEL_1442;
                    v192 = sqlite3VdbeMemClearAndResize(v188, (unsigned int)v190);
                    v6 = 0;
                    if ( v192 )
                      goto LABEL_1453;
LABEL_309:
                    *(_DWORD *)(v188 + 16) = v190;
                    *(_WORD *)(v188 + 20) = 16;
                    if ( v191 )
                    {
                      *(_DWORD *)v188 = v191;
                      *(_WORD *)(v188 + 20) = 1040;
                    }
                    v193 = *(_BYTE **)(v188 + 8);
                    v194 = &v193[v189];
                    if ( v189 >= 128 )
                    {
                      v195 = &v193[(int)sqlite3PutVarint_0(v193, v189)];
                      v6 = 0;
                    }
                    else
                    {
                      *v193 = v189;
                      v195 = v193 + 1;
                    }
                    v196 = v808;
                    while ( 2 )
                    {
                      v197 = (unsigned int)v177[9];
                      if ( (unsigned int)v197 <= 7 )
                      {
                        v12 = 1;
                        *v195++ = v197;
                        if ( (_DWORD)v197 )
                        {
                          v203 = *(_QWORD *)v177;
                          v204 = *((unsigned __int8 *)qword_1800B6000 + v197);
                          v205 = *((unsigned __int8 *)qword_1800B6000 + v197) - 1;
                          if ( v205 )
                          {
                            v206 = v205 - 1;
                            if ( v206 )
                            {
                              v207 = v206 - 1;
                              if ( v207 )
                              {
                                v208 = v207 - 1;
                                if ( v208 )
                                {
                                  if ( v208 != 2 )
                                  {
                                    v194[7] = v203;
                                    v483 = v203 >> 8;
                                    v194[6] = v483;
                                    v203 = v483 >> 8;
                                  }
                                  v194[5] = v203;
                                  v484 = v203 >> 8;
                                  v194[4] = v484;
                                  v203 = v484 >> 8;
                                }
                                v194[3] = v203;
                                v203 >>= 8;
                              }
                              v194[2] = v203;
                              v203 >>= 8;
                            }
                            v194[1] = v203;
                            v203 >>= 8;
                          }
                          *v194 = v203;
                          v194 += v204;
                        }
                      }
                      else if ( (unsigned int)v197 < 0x80 )
                      {
                        v12 = 1;
                        *v195++ = v197;
                        if ( (unsigned int)v197 >= 0xE && v177[4] > 0 )
                        {
LABEL_317:
                          memcpy_0(v194, *((const void **)v177 + 1), v177[4]);
                          v194 += v177[4];
                          v6 = 0;
                          goto LABEL_318;
                        }
                      }
                      else
                      {
                        v198 = sqlite3PutVarint_0(v195, (unsigned int)v197);
                        v6 = 0;
                        v195 += v198;
                        if ( v177[4] )
                          goto LABEL_317;
LABEL_318:
                        v12 = 1;
                      }
                      if ( v177 == (int *)v196 )
                      {
                        v7 = a1;
                        goto LABEL_322;
                      }
                      v177 += 14;
                      continue;
                    }
                  }
                  v171 = v805;
                }
              }
              v487 = 0;
              v488 = *((_QWORD *)v9 + 2);
              v489 = *(_QWORD *)(v488 + 8);
              v490 = v800 + 56LL * *((int *)v9 + 1);
              while ( 1 )
              {
                if ( v487 >= *(__int16 *)(v488 + 54) )
                {
                  v15 = v798;
                  v5 = v801;
                  v10 = v800;
                  goto LABEL_43;
                }
                if ( (*(_BYTE *)(v489 + 24LL * v487 + 18) & 0x60) != 0 )
                {
                  if ( (*(_BYTE *)(v489 + 24LL * v487 + 18) & 0x20) != 0 )
                    goto LABEL_924;
                  if ( *((_DWORD *)v9 + 3) )
                  {
                    v490 += 56;
                    goto LABEL_924;
                  }
                }
                LOBYTE(a2) = *(_BYTE *)(v489 + 24LL * v487 + 12);
                LOBYTE(v8) = a4;
                applyAffinity(v490, a2, v8);
                v8 = v490 + 20;
                v12 = 1;
                v491 = *(_WORD *)(v490 + 20);
                if ( (v491 & 1) == 0 )
                {
                  a2 = 2;
                  switch ( (*(_DWORD *)(v489 + 24LL * v487 + 8) >> 4) & 0xF )
                  {
                    case 2:
                      v492 = (v491 & 0x10) == 0;
LABEL_928:
                      if ( v492 )
                      {
                        _mm_lfence();
                        sqlite3VdbeError(
                          v7,
                          "cannot store %s value in %s column %s.%s",
                          off_1800B2E38[*((unsigned __int8 *)qword_1800B5270 + (*(_WORD *)v8 & 0x3F))],
                          off_1800D06E0[((*(_DWORD *)(v489 + 24LL * v487 + 8) >> 4) & 0xFu) - 1],
                          *(const char **)v488,
                          *(const char **)(v489 + 24LL * v487));
                        v15 = 3091;
                        goto LABEL_393;
                      }
                      break;
                    case 3:
                    case 4:
                      v492 = (v491 & 4) == 0;
                      goto LABEL_928;
                    case 5:
                      if ( (v491 & 4) == 0 )
                      {
                        v492 = (v491 & 0x28) == 0;
                        goto LABEL_928;
                      }
                      a4 = 0xFFFFFFFFFFFFLL;
                      if ( (unsigned __int64)(*(_QWORD *)v490 + 0x800000000000LL) > 0xFFFFFFFFFFFFLL )
                      {
                        v4 = 0;
                        v493 = v491 | 8;
                        *(double *)v490 = (double)(int)*(_QWORD *)v490;
                      }
                      else
                      {
                        v493 = v491 | 0x20;
                      }
                      a2 = v490 + 20;
                      *(_WORD *)v8 = v493;
                      *(_WORD *)v8 = v493 & 0xFFFB;
                      break;
                    case 6:
                      v492 = (v491 & 2) == 0;
                      goto LABEL_928;
                  }
                }
                v490 += 56;
                v6 = 0;
LABEL_924:
                LOBYTE(a4) = v796;
                v487 += v12;
              }
            }
            if ( (_DWORD)v16 != 100 )
            {
              if ( (_DWORD)v16 != 101 )
              {
                if ( (_DWORD)v16 != 102 && (unsigned int)(v16 - 103) > 1 )
                  goto LABEL_51;
LABEL_964:
                v506 = v10 + 56LL * *((int *)v9 + 1);
                v507 = v10 + 56LL * *((int *)v9 + 2);
                v508 = 56LL * *((int *)v9 + 3) + v10;
                if ( ((unsigned __int8)(*(_BYTE *)(v507 + 20) | *(_BYTE *)(v506 + 20)) & (unsigned __int8)v12) != 0 )
                {
                  sqlite3VdbeMemSetNull(v508);
                  goto LABEL_102;
                }
                v513 = sqlite3VdbeIntValue(v507);
                v514 = sqlite3VdbeIntValue(v506);
                v515 = *v9;
                v516 = v514;
                if ( *v9 == 102 )
                {
                  v513 &= v514;
LABEL_980:
                  v6 = 0;
LABEL_995:
                  *(_QWORD *)v508 = v513;
                  *(_WORD *)(v508 + 20) &= 0xF244u;
                  *(_WORD *)(v508 + 20) |= 4u;
LABEL_1023:
                  v10 = v800;
                  goto LABEL_1024;
                }
                if ( v515 == 103 )
                {
                  v513 |= v514;
                  goto LABEL_980;
                }
                v6 = 0;
                if ( !v514 )
                  goto LABEL_995;
                if ( v514 < 0 )
                {
                  v515 = -47 - v515;
                  if ( v514 <= -64 )
                    goto LABEL_988;
                  v516 = -v514;
                }
                if ( v516 < 64 )
                {
                  if ( v515 == 104 )
                  {
                    v513 <<= v516;
                  }
                  else if ( v513 >= 0 )
                  {
                    v513 = (unsigned __int64)v513 >> v516;
                  }
                  else
                  {
                    v513 = ((unsigned __int64)v513 >> v516) | (-1LL << (64 - (unsigned __int8)v516));
                  }
                  goto LABEL_995;
                }
LABEL_988:
                if ( v513 >= 0 || v515 == 104 )
                  v513 = 0;
                else
                  v513 = -1;
                goto LABEL_995;
              }
              v95 = *(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1));
              if ( v95 && *(_DWORD *)(v95 + 68) == *((_DWORD *)v9 + 2) )
              {
                v509 = *(_QWORD *)(v95 + 48);
                sqlite3_free(*(_QWORD *)(v509 + 24));
                v6 = 0;
                *(_QWORD *)(v509 + 24) = 0;
                v12 = 1;
                *(_BYTE *)v509 = 1;
LABEL_178:
                *(_BYTE *)(*(_QWORD *)(v95 + 48) + 3LL) = v9[2] & 3;
                goto LABEL_179;
              }
LABEL_169:
              if ( (v7[25] & 3) == (_BYTE)v12 )
              {
                v15 = 516;
                goto LABEL_1459;
              }
              v85 = *((_DWORD *)v9 + 3);
              v86 = *((unsigned int *)v9 + 2);
              v87 = *(_QWORD *)(v801 + 32);
              v88 = 32LL * v85;
              v89 = *(_QWORD *)(v88 + v87 + 8);
              if ( (_BYTE)v16 == 113 )
              {
                v90 = *((_WORD *)v9 + 1) & 8 | 4;
                v250 = *(_BYTE *)(*(_QWORD *)(v88 + v87 + 24) + 112LL);
                if ( v250 < *((_BYTE *)a1 + 197) )
                  *((_BYTE *)a1 + 197) = v250;
              }
              else
              {
                v90 = 0;
              }
              if ( (v9[2] & 0x10) != 0 )
              {
                v557 = v800 + 56 * v86;
                *(_QWORD *)v557 = sqlite3VdbeIntValue(v557);
                *(_WORD *)(v557 + 20) &= 0xF244u;
                *(_WORD *)(v557 + 20) |= 4u;
                LODWORD(v86) = *(_DWORD *)v557;
              }
              v91 = v9[1];
              if ( v91 == 0xF8 )
              {
                v92 = *((_QWORD *)v9 + 2);
                v93 = *(unsigned __int16 *)(v92 + 8);
              }
              else
              {
                v93 = 0;
                v92 = 0;
                if ( v91 == 0xFD )
                  v93 = *((unsigned int *)v9 + 4);
              }
              Cursor = allocateCursor(a1, *((unsigned int *)v9 + 1), v93, 0);
              v95 = Cursor;
              if ( !Cursor )
                goto LABEL_1453;
              v96 = *(_QWORD *)(Cursor + 48);
              *(_DWORD *)(Cursor + 8) |= 4u;
              *(_BYTE *)(Cursor + 1) = v85;
              *(_BYTE *)(Cursor + 2) = 1;
              *(_DWORD *)(Cursor + 68) = v86;
              v97 = sqlite3BtreeCursor(v89, v86, v90, v92, v96);
              v7 = a1;
              v15 = v97;
              v5 = v801;
              v10 = v800;
              *(_QWORD *)(v95 + 56) = v92;
              v798 = v97;
              v6 = 0;
              *(_BYTE *)(v95 + 4) = v9[1] != 0xF8;
              v12 = 1;
              goto LABEL_178;
            }
            v510 = *(_QWORD *)(v5 + 32);
            v511 = 32LL * *((int *)v9 + 1);
            updated = sqlite3BtreeUpdateMeta(
                        *(_QWORD *)(v511 + v510 + 8),
                        *((unsigned int *)v9 + 2),
                        *((unsigned int *)v9 + 3));
            v12 = 1;
            v798 = updated;
            v15 = updated;
            if ( *((_DWORD *)v9 + 2) == 1 )
            {
              **(_DWORD **)(v511 + v510 + 24) = *((_DWORD *)v9 + 3) - *((unsigned __int16 *)v9 + 1);
              *(_DWORD *)(v5 + 44) |= 1u;
              sqlite3FkClearTriggerCache(v5, *((unsigned int *)v9 + 1));
              v12 = 1;
            }
            else if ( *((_DWORD *)v9 + 2) == 2 )
            {
              *(_BYTE *)(*(_QWORD *)(v511 + v510 + 24) + 112LL) = v9[12];
            }
            if ( *((_DWORD *)v9 + 1) == 1 )
            {
              sqlite3ExpirePreparedStatements(v5, 0, v8);
              *((_DWORD *)v7 + 50) &= 0xFFFFFFFC;
              v12 = 1;
            }
            v6 = 0;
LABEL_179:
            if ( v15 )
              goto LABEL_1459;
            goto LABEL_119;
          }
          if ( (unsigned int)v16 > 0x6F )
          {
            if ( (_DWORD)v16 == 112 || (_DWORD)v16 == 113 )
              goto LABEL_169;
            if ( (_DWORD)v16 != 114 )
            {
              v550 = *(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 2));
              v551 = allocateCursor(v7, *((unsigned int *)v9 + 1), (unsigned int)*(__int16 *)(v550 + 72), 0);
              if ( !v551 )
                goto LABEL_1455;
              *(_DWORD *)(v551 + 8) |= 1u;
              *(_BYTE *)(v551 + 2) = 1;
              *(_QWORD *)(v551 + 56) = *(_QWORD *)(v550 + 56);
              *(_BYTE *)(v551 + 4) = *(_BYTE *)(v550 + 4);
              *(_DWORD *)(v551 + 68) = *(_DWORD *)(v550 + 68);
              v552 = *(_DWORD *)(v551 + 8) ^ (*(_DWORD *)(v550 + 8) ^ *(_DWORD *)(v551 + 8)) & 4;
              *(_DWORD *)(v551 + 8) = v552;
              *(_QWORD *)(v551 + 16) = *(_QWORD *)(v550 + 16);
              *(_DWORD *)(v551 + 8) = v552 | 8;
              *(_DWORD *)(v550 + 8) |= 8u;
              v15 = sqlite3BtreeCursor(
                      *(_QWORD *)(v551 + 16),
                      *(_DWORD *)(v551 + 68),
                      4,
                      *(_QWORD *)(v551 + 56),
                      *(_QWORD *)(v551 + 48));
              v798 = v15;
              goto LABEL_48;
            }
            v553 = v10 + 56LL * *((int *)v9 + 1);
            v554 = v10 + 56LL * *((int *)v9 + 2);
            sqlite3VdbeMemSetNull(v554);
            v12 = 1;
            if ( (*(_BYTE *)(v553 + 20) & 1) != 0 )
            {
              v6 = 0;
              goto LABEL_42;
            }
            *(_WORD *)(v554 + 20) = 4;
            v555 = ~sqlite3VdbeIntValue(v553);
LABEL_1072:
            *(_QWORD *)v554 = v555;
            goto LABEL_48;
          }
          if ( (_DWORD)v16 != 111 )
          {
            v517 = v16 - 106;
            if ( v517 )
            {
              v518 = v517 - 1;
              if ( v518 )
              {
                v519 = v518 - 1;
                if ( v519 )
                {
                  if ( (unsigned int)(v519 - 1) > 1 )
                    goto LABEL_51;
                }
              }
            }
            v520 = *((int *)v9 + 3);
            v521 = v10 + 56LL * *((int *)v9 + 1);
            v522 = 56LL * *((int *)v9 + 2) + v10;
            v815 = 0;
            v523 = v800 + 56 * v520;
            v524 = *(_WORD *)(v522 + 20);
            if ( (*(_BYTE *)(v521 + 20) & (unsigned __int8)v524 & 4) == 0 )
            {
              if ( ((unsigned __int8)(*(_BYTE *)(v521 + 20) | v524) & (unsigned __int8)v12) != 0 )
                goto LABEL_1040;
              v525 = numericType(v521);
              if ( (v525 & (unsigned __int8)numericType(v522) & 4) == 0 )
                goto LABEL_1025;
              v6 = 0;
              v12 = 1;
            }
            v526 = *v9;
            v527 = *(_QWORD *)v522;
            v528 = *(_QWORD *)v521;
            v815 = *(_QWORD *)v522;
            v529 = v526 - 106;
            if ( v529 )
            {
              v530 = v529 - 1;
              if ( v530 )
              {
                v531 = v530 - 1;
                if ( v531 )
                {
                  if ( v531 != 1 )
                  {
                    if ( v528 )
                    {
                      v532 = v527;
                      if ( v528 == -1 )
                        v528 = v12;
                      v815 = v532 % v528;
                      goto LABEL_1021;
                    }
                    goto LABEL_1040;
                  }
                  if ( !v528 )
                    goto LABEL_1040;
                  if ( v528 != -1 || v527 != 0x8000000000000000uLL )
                  {
                    v815 = v527 / v528;
LABEL_1021:
                    *(_QWORD *)v523 = v815;
                    v534 = *(_WORD *)(v523 + 20) & 0xF240 | 4;
LABEL_1022:
                    *(_WORD *)(v523 + 20) = v534;
                    v5 = v801;
                    goto LABEL_1023;
                  }
LABEL_1025:
                  v535 = sqlite3VdbeRealValue(v521);
                  *(double *)&v4 = sqlite3VdbeRealValue(v522);
                  *((_QWORD *)&v536 + 1) = *((_QWORD *)&v4 + 1);
                  switch ( *v9 )
                  {
                    case 'j':
                      v539 = *(double *)&v4 + v535;
                      break;
                    case 'k':
                      v539 = *(double *)&v4 - v535;
                      break;
                    case 'l':
                      v539 = *(double *)&v4 * v535;
                      break;
                    case 'm':
                      if ( v535 == 0.0 )
                        goto LABEL_1040;
                      v539 = *(double *)&v4 / v535;
                      break;
                    default:
                      v537 = sqlite3VdbeIntValue(v521);
                      v538 = sqlite3VdbeIntValue(v522);
                      v815 = v538;
                      if ( !v537 )
                        goto LABEL_1040;
                      v536 = 0;
                      if ( v537 == -1 )
                        v537 = 1;
                      v539 = (double)(int)(v538 % v537);
                      break;
                  }
                  *((_QWORD *)&v4 + 1) = *((_QWORD *)&v536 + 1);
                  IsNaN = sqlite3IsNaN();
                  v6 = 0;
                  if ( !IsNaN )
                  {
                    v541 = *(_WORD *)(v523 + 20);
                    *(double *)v523 = v539;
                    v534 = v541 & 0xF240 | 8;
                    goto LABEL_1022;
                  }
LABEL_1040:
                  sqlite3VdbeMemSetNull(v523);
                  goto LABEL_101;
                }
                v533 = sqlite3MulInt64(&v815, v528);
              }
              else
              {
                v533 = sqlite3SubInt64(&v815, v528);
              }
            }
            else
            {
              v533 = sqlite3AddInt64(&v815, v528);
            }
            v6 = 0;
            if ( !v533 )
              goto LABEL_1021;
            goto LABEL_1025;
          }
          v542 = v10 + 56LL * *((int *)v9 + 1);
          v543 = *(_WORD *)(v542 + 20);
          v544 = v10 + 56LL * *((int *)v9 + 2);
          v545 = v10 + 56LL * *((int *)v9 + 3);
          if ( ((unsigned __int8)(*(_BYTE *)(v544 + 20) | v543) & (unsigned __int8)v12) != 0 )
          {
            sqlite3VdbeMemSetNull(v545);
            v15 = v798;
            goto LABEL_502;
          }
          if ( (v543 & 0x12) != 0 )
          {
            if ( (v543 & 0x400) == 0 )
              goto LABEL_1051;
            v546 = sqlite3VdbeMemExpandBlob(v10 + 56LL * *((int *)v9 + 1));
          }
          else
          {
            LOBYTE(a2) = a4;
            v546 = sqlite3VdbeMemStringify(v10 + 56LL * *((int *)v9 + 1), a2, 0);
          }
          if ( v546 )
            goto LABEL_269;
          v543 = *(_WORD *)(v542 + 20) & 0xFFFD;
LABEL_1051:
          v547 = *(_WORD *)(v544 + 20);
          if ( (v547 & 0x12) != 0 )
          {
            if ( (v547 & 0x400) == 0 )
            {
LABEL_1057:
              LODWORD(v549) = *(_DWORD *)(v542 + 16) + *(_DWORD *)(v544 + 16);
              if ( (int)v549 > *(_DWORD *)(v801 + 136) )
                goto LABEL_1442;
              if ( (unsigned int)sqlite3VdbeMemGrow(v545, (unsigned int)(v549 + 2), v545 == v544) )
                goto LABEL_1453;
              v549 = (int)v549;
              *(_WORD *)(v545 + 20) &= 0xF242u;
              *(_WORD *)(v545 + 20) |= 2u;
              if ( v545 != v544 )
              {
                memcpy_0(*(void **)(v545 + 8), *(const void **)(v544 + 8), *(int *)(v544 + 16));
                *(_WORD *)(v544 + 20) = v547;
              }
              memcpy_0(
                (void *)(*(_QWORD *)(v545 + 8) + *(int *)(v544 + 16)),
                *(const void **)(v542 + 8),
                *(int *)(v542 + 16));
              LOBYTE(a4) = v796;
              v12 = 1;
              *(_WORD *)(v542 + 20) = v543;
              if ( v796 > 1u )
                v549 = (int)v549 & 0xFFFFFFFFFFFFFFFEuLL;
              v6 = 0;
              v15 = v798;
              v7 = a1;
              v10 = v800;
              v8 = v799;
              *(_BYTE *)(v549 + *(_QWORD *)(v545 + 8)) = 0;
              *(_BYTE *)(*(_QWORD *)(v545 + 8) + v549 + 1) = 0;
              *(_WORD *)(v545 + 20) |= 0x200u;
              *(_DWORD *)(v545 + 16) = v549;
              v5 = v801;
              *(_BYTE *)(v545 + 22) = v796;
              goto LABEL_628;
            }
            v548 = sqlite3VdbeMemExpandBlob(v544);
          }
          else
          {
            LOBYTE(a2) = v796;
            v548 = sqlite3VdbeMemStringify(v544, a2, 0);
          }
          if ( v548 )
            goto LABEL_269;
          v547 = *(_WORD *)(v544 + 20) & 0xFFFD;
          goto LABEL_1057;
        }
LABEL_1089:
        if ( *((int *)v9 + 3) > 0 )
        {
          *(_DWORD *)(56LL * *((int *)v9 + 3) + v10 + 16) = 0;
          *(_QWORD *)(56LL * *((int *)v9 + 3) + v10 + 8) = &Src;
        }
        v566 = *((int *)v9 + 1);
        v567 = *(_QWORD *)(v7[15] + 8 * v566);
        if ( !v567 || (*(_BYTE *)(v567 + 8) & 8) != 0 || *((_DWORD *)v9 + 2) > *(__int16 *)(v567 + 72) )
        {
          v571 = allocateCursor(v7, v566, *((unsigned int *)v9 + 2), 0);
          v567 = v571;
          if ( !v571 )
            goto LABEL_1455;
          *(_DWORD *)(v571 + 8) |= 1u;
          v572 = (_QWORD *)(v571 + 16);
          v573 = sqlite3BtreeOpen(*(_QWORD *)v5, 0, v5, v571 + 16, *((unsigned __int16 *)v9 + 1) | 5u, 1054);
          v6 = 0;
          v15 = v573;
          if ( v573 )
            goto LABEL_1459;
          v574 = sqlite3BtreeBeginTrans(*v572, 1, 0);
          v6 = 0;
          v798 = v574;
          v15 = v574;
          if ( !v574 )
          {
            v575 = *((_QWORD *)v9 + 2);
            v576 = (_DWORD *)(v567 + 68);
            v577 = *v572;
            *(_QWORD *)(v567 + 56) = v575;
            if ( v575 )
            {
              Table = sqlite3BtreeCreateTable(v577, v567 + 68, *((unsigned __int16 *)v9 + 1) | 2u);
              v6 = 0;
              v798 = Table;
              v15 = Table;
              if ( !Table )
              {
                v15 = sqlite3BtreeCursor(*v572, *v576, 4, v575, *(_QWORD *)(v567 + 48));
                v798 = v15;
                v6 = 0;
              }
              *(_BYTE *)(v567 + 4) = 0;
            }
            else
            {
              v579 = *(_QWORD *)(v567 + 48);
              *v576 = 1;
              v15 = sqlite3BtreeCursor(v577, 1, 4, 0, v579);
              v798 = v15;
              v6 = 0;
              *(_BYTE *)(v567 + 4) = 1;
            }
            v10 = v800;
            v5 = v801;
          }
          *(_DWORD *)(v567 + 8) = *(_DWORD *)(v567 + 8) & 0xFFFFFFFB | (*((_WORD *)v9 + 1) != 8 ? 4 : 0);
          if ( v15 )
          {
            sqlite3BtreeClose(*(_QWORD *)(v567 + 16));
            goto LABEL_393;
          }
        }
        else
        {
          v568 = *(unsigned int *)(v567 + 68);
          v569 = *(_QWORD *)(v567 + 16);
          *(_QWORD *)(v567 + 24) = 0;
          *(_DWORD *)(v567 + 32) = 0;
          v570 = sqlite3BtreeClearTable(v569, v568, 0);
          v6 = 0;
          v798 = v570;
          v15 = v570;
          if ( v570 )
            goto LABEL_1459;
        }
        v12 = 1;
        *(_BYTE *)(v567 + 2) = 1;
        goto LABEL_119;
      }
      if ( (unsigned int)v16 > 0x81 )
      {
        if ( (unsigned int)v16 > 0x87 )
        {
          switch ( (_DWORD)v16 )
          {
            case 0x88:
              v669 = *((int *)v9 + 1);
              v670 = *(_QWORD *)(v7[15] + 8 * v669);
              if ( !v670 )
              {
                LOBYTE(a4) = 3;
                v670 = allocateCursor(v7, v669, (unsigned int)v12, a4);
                v6 = 0;
                if ( !v670 )
                  goto LABEL_1455;
                *(_DWORD *)(v670 + 8) |= 8u;
                v12 = 1;
                *(_BYTE *)(v670 + 4) = 1;
                *(_QWORD *)(v670 + 48) = &dword_1800D0EA4;
                *(_DWORD *)(v670 + 36) = 0;
              }
              *(_BYTE *)(v670 + 2) = v12;
              *(_DWORD *)(v670 + 32) = 0;
              if ( !*(_BYTE *)v670 )
              {
                v671 = *(_QWORD *)(v670 + 48);
                sqlite3_free(*(_QWORD *)(v671 + 24));
                v6 = 0;
                *(_QWORD *)(v671 + 24) = 0;
                v12 = 1;
                *(_BYTE *)v671 = 1;
                goto LABEL_119;
              }
              goto LABEL_42;
            case 0x89:
LABEL_1233:
              v662 = *((int *)v9 + 1);
              v663 = v7[15];
              LODWORD(v803) = 0;
              v664 = *(_QWORD *)(v663 + 8 * v662);
              v665 = *(_QWORD *)(v664 + 48);
              if ( (_BYTE)v16 == 0x89 )
              {
                v666 = *(_QWORD *)(v664 + 48);
                *(_DWORD *)(v664 + 36) = -1;
                IsValidNN = sqlite3BtreeCursorIsValidNN(v666);
                v6 = 0;
                if ( IsValidNN )
                  goto LABEL_412;
              }
              v668 = sqlite3BtreeLast(v665, &v803);
              v6 = 0;
              v798 = v668;
              v15 = v668;
              *(_BYTE *)(v664 + 2) = v803;
              *(_BYTE *)(v664 + 3) = 0;
              *(_DWORD *)(v664 + 32) = 0;
              if ( v668 )
                goto LABEL_1459;
              if ( *((int *)v9 + 2) <= 0 )
                goto LABEL_412;
              if ( !(_DWORD)v803 )
                goto LABEL_198;
              goto LABEL_329;
            case 0x8A:
              v218 = v7[15];
              v4 = 0;
              v219 = *((int *)v9 + 1);
              v810 = 0;
              v811 = 0;
              v812 = 0;
              v220 = *(_QWORD *)(v218 + 8 * v219);
              v221 = v10 + 56LL * *((int *)v9 + 2);
              if ( ((unsigned __int8)v12 & v9[2]) != 0 )
                v7[7] += v12;
              if ( (*(_WORD *)(v221 + 20) & 0x400) != 0 )
              {
                v269 = sqlite3VdbeMemExpandBlob(v221);
                v6 = 0;
                v15 = v269;
                if ( v269 )
                  goto LABEL_1459;
              }
              v222 = *((_WORD *)v9 + 1);
              *((_QWORD *)&v810 + 1) = *(int *)(v221 + 16);
              *(_QWORD *)&v810 = *(_QWORD *)(v221 + 8);
              v223 = v10 + 56LL * *((int *)v9 + 3);
              LOWORD(v812) = *((_WORD *)v9 + 8);
              *((_QWORD *)&v811 + 1) = v223;
              if ( (v222 & 0x10) != 0 )
                v224 = *(unsigned int *)(v220 + 36);
              else
                v224 = 0;
              v225 = sqlite3BtreeInsert(*(_QWORD *)(v220 + 48), &v810, (unsigned __int8)v222 & 0x8A, v224);
              v6 = 0;
              *(_DWORD *)(v220 + 32) = 0;
              goto LABEL_370;
          }
          v659 = *(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1));
          v660 = v10 + 56LL * *((int *)v9 + 2);
          if ( (*(_WORD *)(v660 + 20) & 0x400) != 0 )
          {
            v661 = sqlite3VdbeMemExpandBlob(v10 + 56LL * *((int *)v9 + 2));
            v6 = 0;
            v15 = v661;
            if ( v661 )
              goto LABEL_1459;
          }
          v225 = sqlite3VdbeSorterWrite(v659, v660);
          goto LABEL_572;
        }
        if ( (_DWORD)v16 != 135 )
        {
          v625 = v16 - 130;
          if ( !v625 )
          {
            v641 = *((_DWORD *)v9 + 2);
            v642 = *(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1));
            if ( v9[1] == 0xFB && *(_QWORD *)(v5 + 320) )
            {
              v643 = *((_QWORD *)v9 + 2);
              v644 = *(_QWORD *)(32LL * *(char *)(v642 + 1) + *(_QWORD *)(v5 + 32));
              if ( (v9[2] & 2) != 0 && *(_BYTE *)(v642 + 4) )
              {
                v645 = *(_QWORD *)(v642 + 48);
                getCellInfo(v645);
                *(_QWORD *)(v642 + 80) = *(_QWORD *)(v645 + 48);
              }
            }
            else
            {
              v644 = 0;
              v643 = 0;
            }
            LOBYTE(a2) = v9[2];
            v646 = sqlite3BtreeDelete(*(_QWORD *)(v642 + 48), a2);
            v6 = 0;
            v798 = v646;
            *(_QWORD *)(v642 + 32) = 0;
            if ( v646 )
            {
              v15 = v646;
              goto LABEL_1459;
            }
            v12 = 1;
            ++v813;
            if ( (v641 & 1) != 0 )
            {
              ++v7[7];
              v647 = *(void (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _QWORD))(v801 + 320);
              if ( v647 )
              {
                if ( v643 && *(char *)(v643 + 48) >= 0 )
                {
                  v648 = v644;
                  v5 = v801;
                  v647(*(_QWORD *)(v801 + 312), 9, v648, *(_QWORD *)v643, *(_QWORD *)(v642 + 80));
                  v15 = 0;
                  goto LABEL_102;
                }
              }
            }
LABEL_322:
            v15 = v798;
            v5 = v801;
            goto LABEL_323;
          }
          v626 = v625 - 1;
          if ( !v626 )
          {
            v640 = v7[7];
            *(_QWORD *)(v5 + 128) += v640;
            *(_QWORD *)(v5 + 120) = v640;
            v7[7] = 0;
            goto LABEL_51;
          }
          v627 = v626 - 1;
          if ( v627 )
          {
            v628 = v627 - 1;
            if ( !v628 )
            {
              v634 = sqlite3VdbeSorterRowkey(
                       *(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1)),
                       v10 + 56LL * *((int *)v9 + 2));
              v6 = 0;
              v798 = v634;
              v15 = v634;
              if ( v634 )
                goto LABEL_1459;
              *(_DWORD *)(*(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 3)) + 32LL) = 0;
              goto LABEL_49;
            }
            if ( v628 != 1 )
              goto LABEL_51;
            v629 = out2Prerelease(v7, v9);
            v630 = *(_QWORD *)(*(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1)) + 48LL);
            getCellInfo(v630);
            v631 = *(unsigned int *)(v630 + 64);
            if ( (unsigned int)v631 > *(_DWORD *)(v5 + 136) )
              goto LABEL_1443;
            v632 = sqlite3VdbeMemFromBtreeZeroOffset(v630, v631, v629);
            v6 = 0;
            v798 = v632;
            v15 = v632;
            if ( v632 )
              goto LABEL_1459;
            if ( !*((_DWORD *)v9 + 3) && (*(_WORD *)(v629 + 20) & 0x4000) != 0 )
            {
              Writeable = sqlite3VdbeMemMakeWriteable(v629);
              v6 = 0;
              if ( Writeable )
                goto LABEL_1455;
              goto LABEL_49;
            }
            goto LABEL_41;
          }
          v635 = v7[15];
          v636 = *((unsigned int *)v9 + 4);
          v637 = 56LL * *((int *)v9 + 3);
          v638 = *((int *)v9 + 1);
          LODWORD(v803) = 0;
          v639 = sqlite3VdbeSorterCompare(*(_QWORD *)(v635 + 8 * v638), v10 + v637, v636, &v803);
          v6 = 0;
          v798 = v639;
          v15 = v639;
          if ( v639 )
            goto LABEL_1459;
          v340 = (_DWORD)v803 == 0;
LABEL_604:
          v12 = 1;
          if ( v340 )
            goto LABEL_119;
          goto LABEL_69;
        }
        v808 = 0;
        v649 = out2Prerelease(v7, v9);
        v650 = *((int *)v9 + 1);
        v6 = 0;
        v651 = v7[15];
        v652 = v649;
        v653 = *(_QWORD *)(v651 + 8 * v650);
        if ( *(_BYTE *)(v653 + 2) )
        {
          v12 = 1;
          *(_WORD *)(v649 + 20) = 1;
          goto LABEL_119;
        }
        if ( *(_BYTE *)(v653 + 3) )
        {
          v654 = *(_QWORD *)(v653 + 80);
        }
        else if ( *(_BYTE *)v653 == 2 )
        {
          v655 = *(__int64 **)(v653 + 48);
          v656 = *v655;
          v798 = (*(__int64 (__fastcall **)(__int64 *, unsigned __int64 *))(*(_QWORD *)*v655 + 96LL))(v655, &v808);
          v15 = v798;
          sqlite3VtabImportErrmsg(v7, v656);
          v6 = 0;
          if ( v798 )
            goto LABEL_1459;
          v654 = v808;
        }
        else
        {
          v657 = sqlite3VdbeCursorRestore(*(_QWORD *)(v651 + 8 * v650));
          v6 = 0;
          v798 = v657;
          v15 = v657;
          if ( v657 )
            goto LABEL_1459;
          if ( *(_BYTE *)(v653 + 2) )
          {
            v12 = 1;
            *(_WORD *)(v652 + 20) = 1;
            goto LABEL_119;
          }
          v658 = *(_QWORD *)(v653 + 48);
          getCellInfo(v658);
          v654 = *(_QWORD *)(v658 + 48);
          v6 = 0;
        }
LABEL_1229:
        *(_QWORD *)v652 = v654;
        goto LABEL_49;
      }
      if ( (_DWORD)v16 == 129 )
      {
        if ( *((_DWORD *)v9 + 3) )
          v624 = *(_QWORD *)(56LL * *((int *)v9 + 3) + v10);
        else
          v624 = 0;
        v225 = sqlite3BtreeTransferRow(
                 *(_QWORD *)(*(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1)) + 48LL),
                 *(_QWORD *)(*(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 2)) + 48LL),
                 v624);
        goto LABEL_572;
      }
      if ( (unsigned int)v16 <= 0x7A )
      {
        if ( (_DWORD)v16 == 122 )
        {
          sqlite3VdbeFreeCursor(v7, *(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1)));
          v6 = 0;
          *(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1)) = 0;
          goto LABEL_49;
        }
        v558 = v16 - 117;
        if ( !v558 )
        {
          v580 = out2Prerelease(v7, v9);
          v581 = sqlite3Strlen30(*((_QWORD *)v9 + 2));
          *((_DWORD *)v9 + 1) = v581;
          if ( v796 != 1 )
          {
            LOBYTE(v582) = 1;
            v798 = sqlite3VdbeMemSetStr(v580, *((_QWORD *)v9 + 2), -1, v582, 0);
            v15 = v798;
            if ( v798 )
              goto LABEL_1443;
            if ( (unsigned int)sqlite3VdbeChangeEncoding(v580, v796) )
              goto LABEL_1455;
            *(_DWORD *)(v580 + 32) = 0;
            *(_WORD *)(v580 + 20) |= 0x2000u;
            if ( v9[1] == 0xFA )
              sqlite3DbFree(v5, *((_QWORD *)v9 + 2));
            v9[1] = -6;
            *((_QWORD *)v9 + 2) = *(_QWORD *)(v580 + 8);
            v581 = *(_DWORD *)(v580 + 16);
            *((_DWORD *)v9 + 1) = v581;
          }
          if ( v581 > *(_DWORD *)(v5 + 136) )
            goto LABEL_1443;
          *v9 = 73;
          goto LABEL_1115;
        }
        v559 = v558 - 1;
        if ( v559 )
        {
          v560 = v559 - 1;
          if ( v560 )
          {
            v561 = v560 - 1;
            if ( v561 )
            {
              if ( v561 != 1 )
                goto LABEL_51;
              LOBYTE(a4) = 3;
              v562 = allocateCursor(v7, *((unsigned int *)v9 + 1), *((unsigned int *)v9 + 3), a4);
              v6 = 0;
              if ( v562 )
              {
                v12 = 1;
                *(_BYTE *)(v562 + 2) = 1;
                *(_DWORD *)(v562 + 36) = *((_DWORD *)v9 + 2);
                *(_QWORD *)(v562 + 48) = &dword_1800D0EA4;
                *(_BYTE *)(v562 + 4) = 1;
                goto LABEL_119;
              }
              goto LABEL_1455;
            }
            v563 = *(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1));
            v564 = *(_QWORD *)(v563 + 24);
            *(_QWORD *)(v563 + 24) = v564 + 1;
            if ( !v564 )
              goto LABEL_69;
            goto LABEL_628;
          }
          LOBYTE(a4) = v12;
          v565 = allocateCursor(v7, *((unsigned int *)v9 + 1), *((unsigned int *)v9 + 2), a4);
          if ( !v565 )
            goto LABEL_1455;
          *(_QWORD *)(v565 + 56) = *((_QWORD *)v9 + 2);
          v225 = sqlite3VdbeSorterInit(v5, *((unsigned int *)v9 + 3), v565);
          goto LABEL_572;
        }
        goto LABEL_1089;
      }
      v584 = v16 - 124;
      if ( v584 )
      {
        v585 = v584 - 1;
        if ( !v585 )
        {
          v612 = *(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1));
          v613 = *(unsigned __int16 *)(v612 + 12);
          if ( v613 >= *((_DWORD *)v9 + 2) )
          {
            if ( v613 > *((_DWORD *)v9 + 3) )
              *(_WORD *)(v612 + 12) = *((_WORD *)v9 + 6);
            a2 = v797;
            goto LABEL_51;
          }
          *(_WORD *)(v612 + 12) = *((_WORD *)v9 + 4);
          goto LABEL_628;
        }
        v586 = v585 - 1;
        if ( v586 )
        {
          v587 = v586 - 1;
          if ( v587 )
          {
            if ( v587 != 1 )
              goto LABEL_51;
            v4 = 0;
            v588 = *((int *)v9 + 1);
            v589 = 56LL * *((int *)v9 + 2);
            v810 = 0;
            v811 = 0;
            v590 = v7[15];
            v812 = 0;
            v591 = *(_QWORD *)(v590 + 8 * v588);
            v79 = v9[1] == 0xFB;
            v592 = *(_QWORD *)(56LL * *((int *)v9 + 3) + v10);
            *((_QWORD *)&v810 + 1) = v592;
            if ( v79 && *(_QWORD *)(v5 + 320) )
            {
              v593 = (_QWORD *)*((_QWORD *)v9 + 2);
              v594 = *(_QWORD *)(32LL * *(char *)(v591 + 1) + *(_QWORD *)(v5 + 32));
            }
            else
            {
              v593 = 0;
              v594 = 0;
            }
            if ( ((unsigned __int8)v12 & v9[2]) != 0 )
            {
              v7[7] += v12;
              if ( (v9[2] & 0x20) != 0 )
                *(_QWORD *)(v5 + 56) = v592;
            }
            v595 = *((_WORD *)v9 + 1);
            *(_QWORD *)&v811 = *(_QWORD *)(v589 + v800 + 8);
            DWORD1(v812) = *(_DWORD *)(v589 + v800 + 16);
            if ( (v595 & 0x10) != 0 )
              v596 = *(unsigned int *)(v591 + 36);
            else
              v596 = 0;
            if ( (*(_WORD *)(v589 + v800 + 20) & 0x400) != 0 )
              DWORD2(v812) = *(_DWORD *)(v589 + v800);
            else
              DWORD2(v812) = 0;
            *(_QWORD *)&v810 = 0;
            v597 = sqlite3BtreeInsert(*(_QWORD *)(v591 + 48), &v810, (unsigned __int8)v595 & 0x8A, v596);
            v6 = 0;
            v798 = v597;
            *(_BYTE *)(v591 + 3) = 0;
            v15 = v597;
            *(_DWORD *)(v591 + 32) = 0;
            if ( v597 )
              goto LABEL_1459;
            v12 = 1;
            ++v813;
            if ( v593 )
            {
              (*(void (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, _QWORD))(v5 + 320))(
                *(_QWORD *)(v5 + 312),
                (v9[2] & 4) != 0 ? 23 : 18,
                v594,
                *v593,
                *((_QWORD *)&v810 + 1));
              goto LABEL_102;
            }
            goto LABEL_323;
          }
          v804 = 0;
          LODWORD(v805) = 0;
          v598 = (__int64 *)out2Prerelease(v7, v9);
          v599 = *(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1));
          if ( (*(_BYTE *)(v599 + 8) & 2) == 0 )
          {
            v600 = sqlite3BtreeLast(*(_QWORD *)(v599 + 48), &v805);
            v6 = 0;
            v798 = v600;
            v15 = v600;
            if ( v600 )
              goto LABEL_1459;
            if ( (_DWORD)v805 )
            {
              v804 = 1;
LABEL_1148:
              if ( *((_DWORD *)v9 + 3) )
              {
                v603 = v7[33];
                if ( v603 )
                {
                  while ( *(_QWORD *)(v603 + 8) )
                    v603 = *(_QWORD *)(v603 + 8);
                  v604 = *(_QWORD *)(v603 + 24) + 56LL * *((int *)v9 + 3);
                }
                else
                {
                  v604 = v800 + 56LL * *((int *)v9 + 3);
                }
                v605 = sqlite3VdbeIntValue(v604);
                *(_QWORD *)v604 = v605;
                *(_WORD *)(v604 + 20) &= 0xF244u;
                *(_WORD *)(v604 + 20) |= 4u;
                if ( v605 == 0x7FFFFFFFFFFFFFFFLL || (*(_BYTE *)(v599 + 8) & 2) != 0 )
                {
                  v15 = 13;
                  goto LABEL_393;
                }
                v606 = v605 + 1;
                v607 = v804;
                if ( v804 < v606 )
                {
                  v607 = v606;
                  v804 = v606;
                }
                *(_QWORD *)v604 = v607;
                v6 = 0;
              }
              if ( (*(_BYTE *)(v599 + 8) & 2) != 0 )
              {
                v608 = 0;
                while ( 1 )
                {
                  sqlite3_randomness(8, &v804);
                  v804 = (v804 & 0x3FFFFFFFFFFFFFFFLL) + 1;
                  v609 = sqlite3BtreeTableMoveto(*(_QWORD *)(v599 + 48), v804, 0, &v805);
                  v6 = 0;
                  v798 = v609;
                  v15 = v609;
                  if ( v609 )
                    goto LABEL_1459;
                  if ( (_DWORD)v805 )
                    break;
                  if ( ++v608 >= 100 )
                  {
                    v15 = 13;
                    goto LABEL_1459;
                  }
                }
              }
              *(_BYTE *)(v599 + 3) = 0;
              *(_DWORD *)(v599 + 32) = 0;
              *v598 = v804;
              goto LABEL_198;
            }
            v601 = *(_QWORD *)(v599 + 48);
            getCellInfo(v601);
            v602 = *(_QWORD *)(v601 + 48);
            v804 = v602;
            if ( v602 == 0x7FFFFFFFFFFFFFFFLL )
              *(_DWORD *)(v599 + 8) |= 2u;
            else
              v804 = v602 + 1;
          }
          v6 = 0;
          goto LABEL_1148;
        }
        v610 = (_QWORD *)out2Prerelease(v7, v9);
        v12 = 1;
        *v610 = *(_QWORD *)(*(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1)) + 24LL);
        v611 = *(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1));
        ++*(_QWORD *)(v611 + 24);
LABEL_717:
        v8 = v799;
        goto LABEL_719;
      }
      v614 = *((int *)v9 + 7);
      *(_QWORD *)&v812 = 0;
      v4 = 0;
      v615 = v7[15];
      LODWORD(v803) = 0;
      v810 = 0;
      v811 = 0;
      v616 = *(_QWORD *)(v615 + 8 * v614);
      v617 = sqlite3BtreeCursorIsValidNN(*(_QWORD *)(v616 + 48));
      v6 = 0;
      if ( v617 )
      {
        v618 = *((_DWORD *)v9 + 1);
        *(_QWORD *)&v810 = *(_QWORD *)(v616 + 56);
        WORD6(v811) = *((_WORD *)v9 + 20);
        v619 = *((int *)v9 + 9);
        BYTE14(v811) = 0;
        LODWORD(v803) = 0;
        *((_QWORD *)&v810 + 1) = v10 + 56 * v619;
        while ( 1 )
        {
          v620 = sqlite3VdbeIdxKeyCompare(v5, v616, &v810, &v803);
          v6 = 0;
          v798 = v620;
          v15 = v620;
          if ( v620 )
            goto LABEL_1459;
          v621 = (int)v803 < 0;
          if ( (int)v803 > 0 )
          {
            if ( !*((_WORD *)v9 + 1) )
              goto LABEL_1184;
            v621 = (int)v803 < 0;
          }
          if ( !v621 )
            goto LABEL_329;
          if ( v618 <= 0 )
            goto LABEL_41;
          v622 = *(_QWORD *)(v616 + 48);
          *(_DWORD *)(v616 + 32) = 0;
          v623 = sqlite3BtreeNext(v622, 0);
          v6 = 0;
          v15 = v623;
          if ( v623 )
            break;
          --v618;
        }
        if ( v623 != 101 )
          goto LABEL_1459;
        v15 = 0;
        v798 = 0;
LABEL_1184:
        v9 += 24;
        goto LABEL_329;
      }
      goto LABEL_1361;
    }
    if ( (unsigned int)v16 > 0xA3 )
    {
      if ( (unsigned int)v16 <= 0xAE )
      {
        if ( (_DWORD)v16 != 174 )
        {
          if ( (unsigned int)v16 <= 0xA9 )
          {
            if ( (_DWORD)v16 == 169 )
            {
              if ( v9[12] || (*(_QWORD *)(v5 + 48) & 0x400000000LL) == 0 )
              {
                v742 = sqlite3BtreeLockTable(
                         *(_QWORD *)(32LL * *((int *)v9 + 1) + *(_QWORD *)(v5 + 32) + 8),
                         *((unsigned int *)v9 + 2));
                v6 = 0;
                v798 = v742;
                v15 = v742;
                if ( v742 )
                {
                  if ( (_BYTE)v742 != 6 )
                    goto LABEL_1459;
                  sqlite3VdbeError(v7, "database table is locked: %s", *((_QWORD *)v9 + 2));
                  goto LABEL_393;
                }
                goto LABEL_49;
              }
              goto LABEL_44;
            }
            v245 = v16 - 164;
            if ( v245 )
            {
              v246 = v245 - 1;
              if ( v246 )
              {
                v738 = v246 - 1;
                if ( v738 )
                {
                  v739 = v738 - 1;
                  if ( v739 )
                  {
                    if ( v739 == 1 )
                    {
                      v740 = *(_QWORD *)(*(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1)) + 48LL);
                      *(_BYTE *)(v740 + 1) &= ~0x40u;
                    }
                  }
                  else
                  {
                    v741 = *(_QWORD *)(*(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1)) + 48LL);
                    *(_BYTE *)(v741 + 1) |= 0x40u;
                  }
                  goto LABEL_51;
                }
                if ( *((_DWORD *)v9 + 1) )
                {
                  *((_DWORD *)v7 + 50) ^= ((unsigned __int8)*((_DWORD *)v7 + 50)
                                         ^ (unsigned __int8)(v12 + *((_DWORD *)v9 + 2)))
                                        & 3;
                  goto LABEL_51;
                }
                sqlite3ExpirePreparedStatements(v5, *((unsigned int *)v9 + 2), v8);
                goto LABEL_48;
              }
            }
            v247 = v10 + 56LL * *((int *)v9 + 1);
            if ( *((_DWORD *)v9 + 3) )
            {
              v15 = sqlite3VdbeMemAggValue(v247, v10 + 56LL * *((int *)v9 + 3), *((_QWORD *)v9 + 2));
              v798 = v15;
              v247 = v10 + 56LL * *((int *)v9 + 3);
            }
            else
            {
              v15 = sqlite3VdbeMemFinalize(v247, *((_QWORD *)v9 + 2));
              v798 = v15;
            }
            if ( !v15 )
            {
              sqlite3VdbeChangeEncoding(v247, v796);
              goto LABEL_48;
            }
            LOBYTE(v248) = 1;
            v788 = (const char *)sqlite3ValueText(v247, v248);
            v789 = "%s";
            goto LABEL_1451;
          }
          v743 = v16 - 170;
          if ( !v743 )
          {
            v755 = *((_QWORD *)v9 + 2);
            v756 = sqlite3VtabBegin(v5, v755);
            v6 = 0;
            v798 = v756;
            v15 = v756;
            if ( !v755 )
              goto LABEL_688;
            sqlite3VtabImportErrmsg(v7, *(_QWORD *)(v755 + 16));
            goto LABEL_687;
          }
          v744 = v743 - 1;
          if ( !v744 )
          {
            v4 = 0;
            v821 = 0;
            v751 = *((int *)v9 + 2);
            *(_QWORD *)&v819 = 0;
            v818 = 0;
            v820 = 0;
            *((_QWORD *)&v819 + 1) = v5;
            v752 = sqlite3VdbeMemCopy(&v818, v10 + 56 * v751);
            LOBYTE(v753) = 1;
            v798 = v752;
            v15 = v752;
            v754 = sqlite3ValueText(&v818, v753);
            if ( v754 )
            {
              v15 = sqlite3VtabCallCreate(v5, *((unsigned int *)v9 + 1), v754, v7 + 21);
              v798 = v15;
            }
            sqlite3VdbeMemRelease(&v818);
            goto LABEL_687;
          }
          v745 = v744 - 1;
          if ( v745 )
          {
            if ( v745 != 1 )
              goto LABEL_51;
            v746 = *((_QWORD *)v9 + 2);
            v804 = 0;
            v747 = *(__int64 **)(v746 + 16);
            if ( v747 )
            {
              v748 = *v747;
              if ( *v747 )
              {
                v798 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v748 + 48))(v747, &v804);
                v15 = v798;
                sqlite3VtabImportErrmsg(v7, v747);
                v6 = 0;
                if ( v798 )
                  goto LABEL_1459;
                LOBYTE(v749) = 2;
                *(_QWORD *)v804 = v747;
                v750 = allocateCursor(v7, *((unsigned int *)v9 + 1), 0, v749);
                v6 = 0;
                if ( v750 )
                {
                  v12 = 1;
                  *(_QWORD *)(v750 + 48) = v804;
                  ++*((_DWORD *)v747 + 2);
                  goto LABEL_119;
                }
                (*(void (__fastcall **)(__int64))(v748 + 56))(v804);
                goto LABEL_1455;
              }
            }
            goto LABEL_1428;
          }
          *(_DWORD *)(v5 + 232) += v12;
          v225 = sqlite3VtabCallDestroy(v5, *((unsigned int *)v9 + 1), *((_QWORD *)v9 + 2));
          --*(_DWORD *)(v5 + 232);
LABEL_572:
          v6 = 0;
LABEL_370:
          v15 = v225;
          v798 = v225;
          v226 = v225 == 0;
          goto LABEL_371;
        }
        v72 = *((int *)v9 + 2);
        v804 = 0;
        v73 = v10 + 56 * v72;
        sqlite3VdbeMemSetNull(v73);
        v74 = (_QWORD *)*((_QWORD *)v9 + 2);
        v6 = 0;
        v75 = v74[10];
        if ( !v75 )
          goto LABEL_41;
        v76 = *(__int64 **)(v75 + 16);
        v77 = *v76;
        ++*(_DWORD *)(v75 + 24);
        v15 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, __int64 *))(v77 + 192))(
                v76,
                *(_QWORD *)(32LL * *((int *)v9 + 1) + *(_QWORD *)(v5 + 32)),
                *v74,
                *((unsigned int *)v9 + 3),
                &v804);
        v798 = v15;
        sqlite3VtabUnlock(v74[10]);
        v6 = 0;
        if ( !v15 )
        {
          if ( v804 )
          {
            LOBYTE(a4) = 1;
            sqlite3VdbeMemSetStr(v73, v804, -1, a4, sqlite3_free);
            goto LABEL_48;
          }
          goto LABEL_41;
        }
LABEL_1447:
        sqlite3_free(v804);
        goto LABEL_393;
      }
      if ( (unsigned int)v16 <= 0xB4 )
      {
        if ( (_DWORD)v16 == 180 )
        {
          *(_WORD *)(56LL * *((int *)v9 + 1) + v10 + 20) &= ~0x800u;
          goto LABEL_51;
        }
        v757 = v16 - 175;
        if ( !v757 )
        {
          v772 = *(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1));
          v773 = (_QWORD *)sqlite3_malloc64(16);
          v774 = v773;
          if ( !v773 )
            goto LABEL_1455;
          *v773 = *(_QWORD *)(v772 + 48);
          v773[1] = v10 + 56LL * *((int *)v9 + 3);
          v775 = out2Prerelease(v7, v9);
          *(_WORD *)(v775 + 20) = 1;
          sqlite3VdbeMemSetPointer(v775, v774, "ValueList", sqlite3VdbeValueListFree);
          goto LABEL_48;
        }
        v758 = v757 - 1;
        if ( !v758 )
        {
          v4 = 0;
          v828 = 0;
          v830 = 0;
          memset(v826, 0, sizeof(v826));
          v831 = 0;
          v827 = 0;
          memset_0(&v829, 0, 0x45u);
          v767 = *(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1));
          v356 = v10 + 56LL * *((int *)v9 + 3);
          if ( *(_BYTE *)(v767 + 2) )
          {
LABEL_637:
            v34 = v356;
            goto LABEL_47;
          }
          v768 = **(__int64 ***)(v767 + 48);
          v769 = *v768;
          BYTE8(v827) = v796;
          *(_QWORD *)&v826[0] = v356;
          v832 = 0x1000000;
          *((_QWORD *)&v826[0] + 1) = &v829;
          if ( (v9[2] & 1) != 0 )
          {
            sqlite3VdbeMemSetNull(v356);
            v770 = 1025;
            *(_DWORD *)v356 = 0;
          }
          else
          {
            v770 = *(_WORD *)(v356 + 20) & 0xF240 | 1;
          }
          *(_WORD *)(v356 + 20) = v770;
          v798 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *, _QWORD))(v769 + 88))(
                   *(_QWORD *)(v767 + 48),
                   v826,
                   *((unsigned int *)v9 + 2));
          v15 = v798;
          sqlite3VtabImportErrmsg(v7, v768);
          if ( SDWORD1(v827) > 0 )
          {
            LOBYTE(v771) = 1;
            v281 = (const char *)sqlite3ValueText(v356, v771);
            sqlite3VdbeError(v7, "%s", v281);
            v15 = DWORD1(v827);
            v798 = DWORD1(v827);
          }
          sqlite3VdbeChangeEncoding(v356, v796);
LABEL_492:
          v6 = 0;
          if ( v15 )
            goto LABEL_1459;
          goto LABEL_493;
        }
        v759 = v758 - 1;
        if ( !v759 )
        {
          v763 = *(_DWORD *)(v5 + 48);
          *(_QWORD *)(v5 + 48) |= 0x4000000uLL;
          v764 = *(_QWORD *)(*((_QWORD *)v9 + 2) + 16LL);
          v765 = v800 + 56LL * *((int *)v9 + 1);
          v766 = sqlite3VdbeChangeEncoding(v765, (unsigned int)v12);
          v6 = 0;
          v15 = v766;
          if ( v766 )
            goto LABEL_1459;
          v798 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v764 + 152LL))(v764, *(_QWORD *)(v765 + 8));
          v15 = v798;
          if ( (v763 & 0x4000000) == 0 )
            *(_QWORD *)(v5 + 48) &= ~0x4000000uLL;
          sqlite3VtabImportErrmsg(v7, v764);
          *((_DWORD *)v7 + 50) &= 0xFFFFFFFC;
          v6 = 0;
          if ( v798 )
            goto LABEL_1459;
          goto LABEL_198;
        }
        v760 = v759 - 1;
        if ( !v760 )
        {
          v440 = out2Prerelease(v7, v9);
          v441 = *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(32LL * *((int *)v9 + 1) + *(_QWORD *)(v5 + 32) + 8) + 8LL)
                                 + 64LL);
          goto LABEL_820;
        }
        if ( v760 != 1 )
          goto LABEL_51;
        v554 = out2Prerelease(v7, v9);
        v761 = *((_DWORD *)v9 + 3);
        v762 = *(_QWORD *)(32LL * *((int *)v9 + 1) + *(_QWORD *)(v5 + 32) + 8);
        v556 = 0;
        if ( v761 )
        {
          v556 = *(unsigned int *)(*(_QWORD *)(v762 + 8) + 64LL);
          if ( (unsigned int)v556 < v761 )
            v556 = v761;
        }
        v555 = (unsigned int)sqlite3BtreeMaxPageCount(v762, v556);
        goto LABEL_1072;
      }
      v776 = v16 - 181;
      if ( v776 )
      {
        v777 = v776 - 1;
        if ( !v777 )
        {
          v786 = 56LL * *((int *)v9 + 1);
          v787 = 56LL * *((int *)v9 + 2);
          if ( ((unsigned __int8)v12 & *(_BYTE *)(v786 + v10 + 20)) != 0 )
          {
            *(_WORD *)(v787 + v10 + 20) &= ~0x800u;
          }
          else
          {
            *(_WORD *)(v787 + v10 + 20) |= 0x800u;
            *(_BYTE *)(v787 + v10 + 23) = *(_BYTE *)(v786 + v10);
          }
          goto LABEL_628;
        }
        v778 = v777 - 1;
        if ( !v778 )
        {
          v783 = 56LL * *((int *)v9 + 1);
          v784 = filterHash(v10, v9);
          v785 = (v784 % (8 * *(_DWORD *)(v783 + v10 + 16))) >> 3;
          *(_BYTE *)(v785 + *(_QWORD *)(v783 + v10 + 8)) |= 1 << ((v784 % (8 * *(_DWORD *)(v783 + v10 + 16))) & 7);
          goto LABEL_48;
        }
        if ( v778 != 1 )
          goto LABEL_51;
LABEL_162:
        v83 = *(_BYTE *)(v5 + 110);
        if ( (v83 & 0x41) != 0 && *((_BYTE *)v7 + 197) != 0xFE )
        {
          a4 = *((_QWORD *)v9 + 2);
          if ( a4 || (a4 = v7[31]) != 0 )
          {
            if ( (v83 & 0x40) != 0 )
            {
              v779 = sqlite3VdbeExpandSql(v7, a4);
              (*(void (__fastcall **)(_QWORD, __int64))(v5 + 248))(*(_QWORD *)(v5 + 256), v779);
              sqlite3_free(v779);
            }
            else if ( *(_DWORD *)(v5 + 228) <= (int)v12 )
            {
              (*(void (__fastcall **)(_QWORD, _QWORD, __int64 *))(v5 + 248))(
                (unsigned int)v12,
                *(_QWORD *)(v5 + 256),
                v7);
            }
            else
            {
              v780 = sqlite3MPrintf(v5, "-- %s", (const char *)a4);
              (*(void (__fastcall **)(__int64, _QWORD, __int64 *, __int64))(v5 + 248))(
                1,
                *(_QWORD *)(v5 + 256),
                v7,
                v780);
              sqlite3DbFree(v5, v780);
            }
            v8 = v799;
            v6 = 0;
            a2 = v797;
            v12 = 1;
          }
        }
        v84 = *((_DWORD *)v9 + 1);
        if ( v84 >= dword_1800D0A18 )
        {
          if ( *v9 == 0xB8 )
            goto LABEL_165;
          for ( k = v12; k < *((_DWORD *)v7 + 36); k += v12 )
          {
            v782 = v7[17];
            if ( *(_BYTE *)(v782 + 24LL * k) == 15 )
              *(_DWORD *)(v782 + 24LL * k + 4) = 0;
          }
          v84 = 0;
        }
        *((_DWORD *)v9 + 1) = v84 + 1;
        *((_DWORD *)v7 + 59) += v12;
        goto LABEL_70;
      }
      v34 = v10 + 56LL * *((int *)v9 + 2);
      if ( (*(_WORD *)(56LL * *((int *)v9 + 1) + v10 + 20) & 0x800) != 0 )
        goto LABEL_112;
LABEL_47:
      sqlite3VdbeMemSetNull(v34);
      goto LABEL_48;
    }
    if ( (_DWORD)v16 == 163 )
    {
LABEL_256:
      v145 = (_DWORD *)*((_QWORD *)v9 + 2);
      v146 = v10 + 56LL * *((int *)v9 + 3);
      if ( *((_QWORD *)v145 + 2) != v146 )
      {
        v255 = *((unsigned __int8 *)v145 + 42);
        *((_QWORD *)v145 + 2) = v146;
        while ( 1 )
        {
          v255 -= v12;
          if ( v255 < 0 )
            break;
          *(_QWORD *)&v145[2 * v255 + 12] = v10 + 56LL * (v255 + *((_DWORD *)v9 + 2));
        }
      }
      *(_DWORD *)(v146 + 16) += v12;
      v147 = v145 + 12;
      v148 = *((_QWORD *)v145 + 1);
      v149 = *((unsigned __int8 *)v145 + 42);
      if ( *((_DWORD *)v9 + 1) )
        (*(void (__fastcall **)(_DWORD *, __int64, _DWORD *))(v148 + 48))(v145, v149, v147);
      else
        (*(void (__fastcall **)(_DWORD *, __int64, _DWORD *))(v148 + 24))(v145, v149, v147);
      v151 = v145[9];
      v6 = 0;
      if ( !v151 )
        goto LABEL_41;
      if ( v151 > 0 )
      {
        LOBYTE(v150) = 1;
        v152 = (const char *)sqlite3ValueText(*(_QWORD *)v145, v150);
        sqlite3VdbeError(v7, "%s", v152);
        v15 = v145[9];
        v798 = v15;
      }
      if ( *((_BYTE *)v145 + 41) )
      {
        if ( *((_DWORD *)v9 - 5) )
          sqlite3VdbeMemSetInt64(v10 + 56LL * *((int *)v9 - 5));
        *((_BYTE *)v145 + 41) = 0;
      }
      sqlite3VdbeMemRelease(*(_QWORD *)v145);
      v12 = 1;
      v6 = 0;
      *(_WORD *)(*(_QWORD *)v145 + 20LL) = 1;
      v145[9] = 0;
      goto LABEL_179;
    }
    if ( (unsigned int)v16 > 0x98 )
    {
      if ( (unsigned int)v16 <= 0x9E )
      {
        if ( (_DWORD)v16 == 158 )
        {
          v728 = *((int *)v9 + 2);
          if ( (*(_DWORD *)(v5 + 48) & 0x80000) != 0 )
          {
            *(_QWORD *)(v5 + 768) += v728;
          }
          else if ( *((_DWORD *)v9 + 1) )
          {
            *(_QWORD *)(v5 + 760) += v728;
          }
          else
          {
            v7[10] += v728;
          }
          goto LABEL_51;
        }
        v710 = v16 - 153;
        if ( !v710 )
        {
          v440 = out2Prerelease(v7, v9);
          *(_WORD *)(v440 + 20) = 8;
LABEL_818:
          v441 = **((_QWORD **)v9 + 2);
LABEL_820:
          *(_QWORD *)v440 = v441;
          goto LABEL_48;
        }
        v711 = v710 - 1;
        if ( !v711 )
        {
          sqlite3UnlinkAndDeleteTrigger(v5, *((unsigned int *)v9 + 1), *((_QWORD *)v9 + 2));
          goto LABEL_48;
        }
        v712 = v711 - 1;
        if ( v712 )
        {
          v713 = v712 - 1;
          if ( !v713 )
          {
            v714 = *((int *)v9 + 1);
            v715 = *((int *)v9 + 2);
            v716 = v10 + 56 * v714;
            if ( (*(_BYTE *)(v716 + 20) & 0x10) == 0 && (unsigned int)sqlite3VdbeMemSetRowSet(v10 + 56 * v714) )
              goto LABEL_1455;
            sqlite3RowSetInsert(*(_QWORD *)(v716 + 8), *(_QWORD *)(56 * v715 + v10));
            goto LABEL_48;
          }
          if ( v713 != 1 )
            goto LABEL_51;
          v212 = out2Prerelease(v7, v9);
          v211 = *(_QWORD *)(v7[33] + 24)
               + 56LL * (*((_DWORD *)v9 + 1) + *(_DWORD *)(*(_QWORD *)(v7[33] + 16) + 24LL * *(int *)(v7[33] + 76) + 4));
          goto LABEL_348;
        }
        v717 = *((int *)v9 + 1);
        v718 = *((_QWORD *)v9 + 2);
        v719 = 56 * v717;
        v720 = v717 + 1;
        LODWORD(v803) = 0;
        v721 = *(_QWORD *)(v5 + 32);
        v722 = 56 * *((_DWORD *)v9 + 3);
        v804 = 0;
        v723 = v10 + 56LL * v720;
        v798 = sqlite3BtreeIntegrityCheck(
                 v5,
                 *(_QWORD *)(32LL * *((unsigned __int16 *)v9 + 1) + v721 + 8),
                 (int)v718 + 4,
                 (int)v10 + v722,
                 *((_DWORD *)v9 + 2),
                 (int)v12 + *(_DWORD *)(v719 + v10),
                 (__int64)&v803,
                 (__int64)&v804);
        v15 = v798;
        sqlite3VdbeMemSetNull(v723);
        if ( (_DWORD)v803 )
        {
          if ( v798 )
            goto LABEL_1447;
          LOBYTE(v724) = 1;
          *(_QWORD *)(v719 + v10) -= (int)v803 - 1;
          sqlite3VdbeMemSetStr(v723, v804, -1, v724, sqlite3_free);
        }
        sqlite3VdbeChangeEncoding(v723, v796);
        goto LABEL_1307;
      }
      v251 = v16 - 159;
      if ( !v251 )
      {
        v734 = v7[33];
        if ( v734 )
        {
          while ( *(_QWORD *)(v734 + 8) )
            v734 = *(_QWORD *)(v734 + 8);
          v735 = *(_QWORD *)(v734 + 24) + 56LL * *((int *)v9 + 1);
        }
        else
        {
          v735 = v10 + 56LL * *((int *)v9 + 1);
        }
        *(_QWORD *)v735 = sqlite3VdbeIntValue(v735);
        *(_WORD *)(v735 + 20) &= 0xF244u;
        *(_WORD *)(v735 + 20) |= 4u;
        v736 = v10 + 56LL * *((int *)v9 + 2);
        v737 = sqlite3VdbeIntValue(v736);
        a2 = v797;
        *(_WORD *)(v736 + 20) &= 0xF244u;
        v6 = 0;
        LOBYTE(a4) = v796;
        *(_WORD *)(v736 + 20) |= 4u;
        *(_QWORD *)v736 = v737;
        v12 = 1;
        if ( *(_QWORD *)v735 < v737 )
          *(_QWORD *)v735 = v737;
        goto LABEL_44;
      }
      v252 = v251 - 1;
      if ( !v252 )
      {
        v729 = *((int *)v9 + 3);
        v730 = 56LL * *((int *)v9 + 1);
        v804 = 0;
        v652 = out2Prerelease(v7, v9);
        v6 = 0;
        v804 = *(_QWORD *)(v730 + v800);
        if ( v804 <= 0 )
        {
          v10 = v800;
        }
        else
        {
          v731 = 56 * v729;
          v10 = v800;
          v732 = *(_QWORD *)(v731 + v800);
          if ( v732 <= 0 )
            v732 = 0;
          v733 = sqlite3AddInt64(&v804, v732);
          v6 = 0;
          if ( !v733 )
          {
            v654 = v804;
            goto LABEL_1229;
          }
        }
        *(_QWORD *)v652 = -1;
        goto LABEL_49;
      }
      if ( (unsigned int)(v252 - 1) > 1 )
        goto LABEL_51;
      v253 = *((unsigned __int16 *)v9 + 1);
      v254 = sqlite3DbMallocRawNN(v5, 8 * v253 + 104);
      if ( !v254 )
        goto LABEL_1455;
      *(_QWORD *)(v254 + 16) = 0;
      *(_QWORD *)v254 = v254 + 8 * (v253 + 6);
      LODWORD(v12) = 1;
      *(_WORD *)(v254 + 8 * v253 + 68) = 1;
      *(_QWORD *)(v254 + 8 * v253 + 72) = v5;
      *(_DWORD *)(v254 + 8 * v253 + 80) = 0;
      *(_QWORD *)(v254 + 8) = *((_QWORD *)v9 + 2);
      *(_QWORD *)(v254 + 24) = v7;
      *(_DWORD *)(v254 + 32) = -1431655765 * ((__int64)&v9[-v799] >> 3);
      *(_BYTE *)(v254 + 40) = v796;
      *(_BYTE *)(v254 + 41) = 0;
      *(_DWORD *)(v254 + 36) = 0;
      *(_BYTE *)(v254 + 42) = v253;
      *(_WORD *)v9 = -3677;
      *((_QWORD *)v9 + 2) = v254;
      goto LABEL_256;
    }
    if ( (_DWORD)v16 == 152 )
    {
      sqlite3UnlinkAndDeleteIndex(v5, *((unsigned int *)v9 + 1), *((_QWORD *)v9 + 2));
      goto LABEL_48;
    }
    if ( (unsigned int)v16 <= 0x92 )
    {
      if ( (_DWORD)v16 == 146 )
      {
        v688 = *(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1));
        if ( *(_BYTE *)v688 == (_BYTE)v12 )
        {
          sqlite3VdbeSorterReset(v5, *(_QWORD *)(v688 + 48));
          goto LABEL_48;
        }
        v225 = sqlite3BtreeClearTable(
                 *(_QWORD *)(*(_QWORD *)(v688 + 48) + 8LL),
                 *(unsigned int *)(*(_QWORD *)(v688 + 48) + 80LL),
                 0);
        goto LABEL_572;
      }
      v232 = v16 - 141;
      if ( v232 )
      {
        v233 = v232 - 1;
        if ( v233 )
        {
          v677 = v233 - 1;
          if ( !v677 )
          {
            v687 = *(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1));
            if ( !*(_BYTE *)(v687 + 3) )
              goto LABEL_51;
            v225 = sqlite3VdbeFinishMoveto(v687);
            goto LABEL_572;
          }
          v678 = v677 - 1;
          if ( v678 )
          {
            if ( v678 != 1 )
              goto LABEL_51;
            v679 = *(_QWORD *)(v5 + 32);
            v680 = *((unsigned int *)v9 + 1);
            v681 = 32LL * *((int *)v9 + 2);
            v808 = 0;
            v682 = sqlite3BtreeClearTable(*(_QWORD *)(v681 + v679 + 8), v680, &v808);
            v6 = 0;
            v798 = v682;
            v15 = v682;
            if ( *((_DWORD *)v9 + 3) )
            {
              a2 = v808;
              v7[7] += v808;
              if ( *((int *)v9 + 3) > 0 )
                *(_QWORD *)(56LL * *((int *)v9 + 3) + v10) += a2;
            }
            goto LABEL_688;
          }
          LODWORD(v805) = 0;
          v683 = out2Prerelease(v7, v9);
          *(_WORD *)(v683 + 20) = 1;
          if ( *(_DWORD *)(v5 + 220) > *(_DWORD *)(v5 + 232) + 1 )
          {
            v15 = 6;
            *((_BYTE *)v7 + 196) = 2;
            goto LABEL_393;
          }
          v684 = *((_DWORD *)v9 + 3);
          v685 = *(_QWORD *)(v5 + 32);
          v686 = *((unsigned int *)v9 + 1);
          LODWORD(v805) = 0;
          v15 = sqlite3BtreeDropTable(*(_QWORD *)(32LL * (int)v684 + v685 + 8), v686, &v805);
          v798 = v15;
          v6 = 0;
          *(_WORD *)(v683 + 20) = 4;
          *(_QWORD *)v683 = (int)v805;
          if ( v15 )
            goto LABEL_1459;
          if ( (_DWORD)v805 )
          {
            sqlite3RootPageMoved(v5, v684, (unsigned int)v805, *((unsigned int *)v9 + 1));
            v12 = 1;
            v807 = v684 + 1;
            goto LABEL_717;
          }
LABEL_1361:
          LOBYTE(a4) = v796;
          v12 = 1;
          a2 = v797;
          goto LABEL_44;
        }
      }
      v234 = *((int *)v9 + 1);
      v235 = v7[15];
      v804 = 0;
      v236 = *(_QWORD *)(v235 + 8 * v234);
      v237 = sqlite3VdbeCursorRestore(v236);
      v6 = 0;
      v798 = v237;
      v15 = v237;
      if ( v237 )
        goto LABEL_1459;
      if ( !*(_BYTE *)(v236 + 2) )
      {
        v804 = 0;
        v238 = sqlite3VdbeIdxRowid(v5, *(_QWORD *)(v236 + 48), &v804);
        v6 = 0;
        v798 = v238;
        v15 = v238;
        if ( v238 )
          goto LABEL_1459;
        if ( *v9 == 0x8D )
        {
          v12 = v238 + 1;
          v239 = *(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 3));
          *(_BYTE *)(v239 + 2) = 0;
          *(_QWORD *)(v239 + 80) = v804;
          *(_BYTE *)(v239 + 3) = v238 + 1;
          *(_DWORD *)(v239 + 32) = 0;
          *(_QWORD *)(v239 + 16) = *((_QWORD *)v9 + 2);
          *(_QWORD *)(v239 + 40) = v236;
          goto LABEL_119;
        }
        v68 = (__int64 *)out2Prerelease(v7, v9);
        v69 = v804;
        goto LABEL_133;
      }
      goto LABEL_46;
    }
    v689 = v16 - 147;
    if ( !v689 )
    {
      LODWORD(v803) = 0;
      v704 = out2Prerelease(v7, v9);
      v705 = *(_QWORD *)(v5 + 32);
      v706 = (_QWORD *)v704;
      v707 = *((unsigned int *)v9 + 3);
      v708 = 32LL * *((int *)v9 + 1);
      LODWORD(v803) = 0;
      v709 = sqlite3BtreeCreateTable(*(_QWORD *)(v708 + v705 + 8), &v803, v707);
      v6 = 0;
      v798 = v709;
      v15 = v709;
      if ( v709 )
        goto LABEL_1459;
      *v706 = (unsigned int)v803;
      goto LABEL_49;
    }
    v690 = v689 - 1;
    if ( !v690 )
    {
      *(_BYTE *)(v5 + 112) += v12;
      v699 = *(_QWORD *)(v5 + 512);
      v700 = *(_BYTE *)(v5 + 110);
      v701 = *(_DWORD *)(v5 + 744);
      v804 = 0;
      if ( ((unsigned __int8)v12 & v9[4]) != 0 )
      {
        *(_QWORD *)(v5 + 512) = 0;
        *(_BYTE *)(v5 + 110) = 0;
      }
      if ( (v9[4] & 2) != 0 )
        *(_DWORD *)(v5 + 744) = *((_DWORD *)v9 + 2);
      v702 = sqlite3_exec(v5, *((_QWORD *)v9 + 2), 0, 0, (__int64)&v804);
      v703 = (const char *)v804;
      v6 = 0;
      --*(_BYTE *)(v5 + 112);
      v15 = v702;
      v798 = v702;
      *(_QWORD *)(v5 + 512) = v699;
      *(_BYTE *)(v5 + 110) = v700;
      *(_DWORD *)(v5 + 744) = v701;
      if ( !v703 && !v702 )
        goto LABEL_198;
      sqlite3VdbeError(v7, "%s", v703);
      sqlite3_free(v804);
LABEL_1288:
      if ( v15 != 7 )
        goto LABEL_393;
      goto LABEL_1455;
    }
    v691 = v690 - 1;
    if ( v691 )
    {
      v692 = v691 - 1;
      if ( v692 )
      {
        if ( v692 != 1 )
          goto LABEL_51;
        sqlite3UnlinkAndDeleteTable(v5, *((unsigned int *)v9 + 1), *((_QWORD *)v9 + 2));
        goto LABEL_48;
      }
      v225 = sqlite3AnalysisLoad(v5, *((unsigned int *)v9 + 1));
      goto LABEL_572;
    }
    v693 = *((_QWORD *)v9 + 2);
    v694 = *((int *)v9 + 1);
    v4 = 0;
    *(_QWORD *)&v812 = 0;
    v810 = 0;
    v811 = 0;
    if ( v693 )
    {
      v696 = *(_QWORD *)(v5 + 32);
      *(_QWORD *)&v810 = v5;
      LODWORD(v811) = v694;
      *((_QWORD *)&v810 + 1) = v7 + 21;
      DWORD2(v811) = 0;
      LODWORD(v812) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(32 * v694 + v696 + 8) + 8LL) + 64LL);
      v697 = sqlite3MPrintf(
               v5,
               "SELECT*FROM\"%w\".%s WHERE %s ORDER BY rowid",
               *(_QWORD *)(32 * v694 + v696),
               "sqlite_master",
               v693);
      v698 = v697;
      if ( !v697 )
      {
        v15 = 7;
LABEL_1446:
        sqlite3ResetAllSchemasOfConnection(v5);
        goto LABEL_1288;
      }
      *(_BYTE *)(v5 + 197) = 1;
      DWORD1(v811) = 0;
      HIDWORD(v811) = 0;
      v798 = sqlite3_exec(v5, v697, (unsigned int)sqlite3InitCallback, (unsigned int)&v810, 0);
      v15 = v798;
      if ( !v798 )
      {
        v15 = DWORD1(v811);
        v798 = DWORD1(v811);
        if ( !DWORD1(v811) && !HIDWORD(v811) )
        {
          v15 = sqlite3ReportError(11, 100435, "database corruption");
          v798 = v15;
        }
      }
      sqlite3DbFreeNN(v5, v698);
      v6 = 0;
      *(_BYTE *)(v5 + 197) = 0;
      v12 = 1;
    }
    else
    {
      sqlite3SchemaClear(*(_QWORD *)(32 * v694 + *(_QWORD *)(v5 + 32) + 24));
      *(_DWORD *)(v5 + 44) &= ~0x10u;
      inited = sqlite3InitOne(v5, (unsigned int)v694, v7 + 21, *((unsigned __int16 *)v9 + 1));
      v12 = 1;
      v798 = inited;
      *(_DWORD *)(v5 + 44) |= 1u;
      v15 = inited;
      *((_DWORD *)v7 + 50) &= 0xFFFFFFFC;
      v6 = 0;
    }
    if ( !v15 )
      goto LABEL_119;
    goto LABEL_1446;
  }
  if ( (unsigned int)v16 <= 0x2D )
  {
    if ( (_DWORD)v16 == 45 )
      goto LABEL_270;
    if ( (unsigned int)v16 > 0x16 )
    {
      if ( (unsigned int)v16 > 0x22 )
      {
        if ( (unsigned int)v16 <= 0x28 )
        {
          if ( (_DWORD)v16 != 40 )
          {
            v27 = v16 - 35;
            if ( v27 )
            {
              v28 = v27 - 1;
              if ( v28 )
              {
                v29 = v28 - 1;
                if ( v29 )
                {
                  v30 = v29 - 1;
                  if ( v30 )
                  {
                    if ( v30 != 1 )
                      goto LABEL_51;
                    v31 = *(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1));
                    v32 = sqlite3BtreeNext(*(_QWORD *)(v31 + 48), *((unsigned int *)v9 + 3));
                  }
                  else
                  {
                    v31 = *(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1));
                    v32 = sqlite3BtreePrevious(*(_QWORD *)(v31 + 48), *((unsigned int *)v9 + 3));
                  }
                }
                else
                {
                  v31 = *(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1));
                  v32 = sqlite3VdbeSorterNext(v5, v31);
                }
                v15 = v32;
                v798 = v32;
                v6 = 0;
                *(_DWORD *)(v31 + 32) = 0;
                if ( v32 )
                {
                  if ( v32 != 101 )
                    goto LABEL_1459;
                  v15 = 0;
                  v798 = 0;
                  *(_BYTE *)(v31 + 2) = 1;
                  goto LABEL_38;
                }
                *(_BYTE *)(v31 + 2) = 0;
                LODWORD(v12) = 1;
                ++*((_DWORD *)v7 + *((unsigned __int16 *)v9 + 1) + 53);
                goto LABEL_36;
              }
              goto LABEL_702;
            }
LABEL_701:
            *((_DWORD *)v7 + 55) += v12;
LABEL_702:
            v377 = *((int *)v9 + 1);
            v378 = v7[15];
            LODWORD(v805) = 0;
            v379 = *(_QWORD *)(v378 + 8 * v377);
            LODWORD(v805) = v12;
            if ( *(_BYTE *)v379 == (_BYTE)v12 )
            {
              v380 = sqlite3VdbeSorterRewind(v379, &v805);
              v6 = 0;
            }
            else
            {
              v380 = sqlite3BtreeFirst(*(_QWORD *)(v379 + 48), &v805);
              v6 = 0;
              *(_BYTE *)(v379 + 3) = 0;
              *(_DWORD *)(v379 + 32) = 0;
            }
            v798 = v380;
            v15 = v380;
            if ( v380 )
              goto LABEL_1459;
            *(_BYTE *)(v379 + 2) = v805;
            if ( *((int *)v9 + 2) <= 0 )
              goto LABEL_41;
            v340 = (_DWORD)v805 == 0;
            goto LABEL_604;
          }
          goto LABEL_270;
        }
        if ( (_DWORD)v16 != 41 && (_DWORD)v16 != 42 )
        {
          if ( (unsigned int)(v16 - 43) > 1 )
            goto LABEL_51;
          v381 = sqlite3VdbeBooleanValue(v10 + 56LL * *((int *)v9 + 1), 2);
          v382 = sqlite3VdbeBooleanValue(v10 + 56LL * *((int *)v9 + 2), 2);
          v12 = 1;
          v383 = v382 + 2 * v381 + v381;
          v384 = &qword_1800BD2D0;
          if ( *v9 != 44 )
            v384 = qword_1800BE0C0;
          v385 = *((unsigned __int8 *)v384 + v383);
          v386 = 56LL * *((int *)v9 + 3);
          v387 = *(_WORD *)(v386 + v10 + 20);
          if ( (_BYTE)v385 == 2 )
          {
            v388 = v387 & 0xF240 | 1;
          }
          else
          {
            *(_QWORD *)(v386 + v10) = v385;
            v388 = v387 & 0xF240 | 4;
          }
          *(_WORD *)(v386 + v10 + 20) = v388;
          goto LABEL_717;
        }
LABEL_270:
        v153 = *((int *)v9 + 1);
        *(_QWORD *)&v812 = 0;
        v4 = 0;
        v154 = v7[15];
        v810 = 0;
        v811 = 0;
        v155 = *(_QWORD *)(v154 + 8 * v153);
        v818 = 0;
        v819 = 0;
        *(_QWORD *)&v810 = *(_QWORD *)(v155 + 56);
        WORD6(v811) = *((_WORD *)v9 + 8);
        BYTE14(v811) = -((unsigned __int8)v16 < 0x2Au);
        v156 = 56LL * *((int *)v9 + 3);
        v820 = 0;
        v821 = 0;
        *((_QWORD *)&v810 + 1) = v10 + v156;
        v157 = *(_QWORD *)(v155 + 48);
        getCellInfo(v157);
        v158 = *(unsigned int *)(v157 + 64);
        if ( (unsigned int)(v158 - 1) <= 0x7FFFFFFE )
        {
          *((_QWORD *)&v819 + 1) = v5;
          WORD2(v819) = 0;
          LODWORD(v820) = 0;
          v159 = sqlite3VdbeMemFromBtreeZeroOffset(v157, v158, &v818);
          v6 = 0;
          v798 = v159;
          v15 = v159;
          if ( v159 )
            goto LABEL_1459;
          v160 = sqlite3VdbeRecordCompareWithSkip((unsigned int)v819, *((_QWORD *)&v818 + 1), &v810, 0);
          sqlite3VdbeMemReleaseMalloc(&v818);
          v161 = v160 + 1;
          v6 = 0;
          v162 = -v160;
          v12 = 1;
          if ( (*v9 & 1) != 0 )
            v162 = v161;
          if ( v162 <= 0 )
            goto LABEL_119;
          goto LABEL_69;
        }
        v674 = "database corruption";
        v675 = 100142;
        v676 = 11;
LABEL_1430:
        v791 = sqlite3ReportError(v676, v675, v674);
        goto LABEL_1439;
      }
      if ( (_DWORD)v16 == 34 )
        goto LABEL_701;
      if ( (unsigned int)v16 <= 0x1C )
      {
        if ( (_DWORD)v16 != 28 )
        {
          if ( (_DWORD)v16 == 23 || (_DWORD)v16 == 24 )
          {
LABEL_246:
            v136 = *((int *)v9 + 1);
            *(_QWORD *)&v812 = 0;
            v4 = 0;
            v137 = v7[15];
            LODWORD(v805) = 0;
            v810 = 0;
            v811 = 0;
            v138 = *(_QWORD *)(v137 + 8 * v136);
            *(_WORD *)(v138 + 2) = 0;
            *(_DWORD *)(v138 + 32) = 0;
            if ( *(_BYTE *)(v138 + 4) )
            {
              v142 = 0;
              v256 = v800 + 56LL * *((int *)v9 + 3);
              v257 = *(_WORD *)(v256 + 20);
              if ( (v257 & 0x2E) == 2 )
                applyNumericAffinity(v256, 0);
              v258 = sqlite3VdbeIntValue(v256);
              v259 = *(_WORD *)(v256 + 20);
              v260 = v258;
              *(_WORD *)(v256 + 20) = v257;
              if ( (v259 & 0x24) == 0 )
              {
                if ( (v259 & 8) == 0 )
                {
                  v12 = 1;
                  if ( (v259 & 1) != 0 || (unsigned int)v16 >= 0x17 )
                  {
                    v15 = v798;
                    v6 = 0;
                    goto LABEL_69;
                  }
                  v361 = sqlite3BtreeLast(*(_QWORD *)(v138 + 48), &v805);
                  v6 = 0;
                  v798 = v361;
                  v15 = v361;
                  if ( v361 )
                    goto LABEL_1458;
                  goto LABEL_343;
                }
                v362 = sqlite3IntFloatCompare(v258);
                if ( v362 <= 0 )
                {
                  if ( v362 < 0 && (v16 & 1) != 0 )
                    LODWORD(v16) = v16 + 1;
                }
                else if ( (v16 & 1) == 0 )
                {
                  LODWORD(v16) = v16 - 1;
                }
              }
              v139 = (_QWORD *)(v138 + 48);
              v363 = sqlite3BtreeTableMoveto(*(_QWORD *)(v138 + 48), v260, 0, &v805);
              v6 = 0;
              *(_QWORD *)(v138 + 80) = v260;
              v798 = v363;
              v15 = v363;
              if ( v363 )
                goto LABEL_1458;
            }
            else
            {
              v139 = (_QWORD *)(v138 + 48);
              HasHint = sqlite3BtreeCursorHasHint(*(_QWORD *)(v138 + 48), 2);
              *(_QWORD *)&v810 = *(_QWORD *)(v138 + 56);
              WORD6(v811) = *((_WORD *)v9 + 8);
              v141 = HasHint;
              BYTE2(v812) = 0;
              v142 = HasHint != 0;
              v143 = *((int *)v9 + 3);
              BYTE14(v811) = (((_BYTE)v16 - 1) & 1) != 0 ? -1 : 1;
              *((_QWORD *)&v810 + 1) = v800 + 56 * v143;
              v144 = sqlite3BtreeIndexMoveto(*(_QWORD *)(v138 + 48), &v810, &v805);
              v6 = 0;
              v798 = v144;
              v15 = v144;
              if ( v144 )
                goto LABEL_1458;
              if ( v141 && !BYTE2(v812) )
                goto LABEL_343;
            }
            if ( (int)v16 < 23 )
            {
              if ( (int)v805 <= 0 && ((_DWORD)v805 || (_DWORD)v16 != 21) )
              {
                v210 = sqlite3BtreeEof(*v139);
                v6 = 0;
                goto LABEL_344;
              }
              LODWORD(v805) = 0;
              v209 = sqlite3BtreePrevious(*v139, 0);
            }
            else
            {
              if ( (int)v805 >= 0 && ((_DWORD)v805 || (_DWORD)v16 != 24) )
              {
                LODWORD(v805) = 0;
LABEL_253:
                v5 = v801;
                v10 = v800;
                v79 = !v142;
                a2 = v797;
                LOBYTE(a4) = v796;
                v7 = a1;
                v12 = 1;
                if ( !v79 )
                  v9 += 24;
                goto LABEL_44;
              }
              LODWORD(v805) = 0;
              v209 = sqlite3BtreeNext(*v139, 0);
            }
            v6 = 0;
            v798 = v209;
            v15 = v209;
            if ( v209 )
            {
              if ( v209 != 101 )
                goto LABEL_1458;
              v12 = 1;
              v798 = 0;
              v210 = 1;
              v15 = 0;
LABEL_345:
              if ( v210 )
                goto LABEL_69;
              goto LABEL_253;
            }
LABEL_343:
            v210 = v805;
LABEL_344:
            v12 = 1;
            goto LABEL_345;
          }
          if ( (_DWORD)v16 == 25 )
          {
            a2 = *(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1));
            if ( !a2 || *(_BYTE *)(a2 + 2) )
              goto LABEL_37;
            goto LABEL_628;
          }
          if ( (_DWORD)v16 == 26
            && *(unsigned __int16 *)(*(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1)) + 12LL) >= *((int *)v9 + 4) )
          {
            goto LABEL_51;
          }
        }
LABEL_277:
        v163 = *((int *)v9 + 1);
        *(_QWORD *)&v812 = 0;
        v4 = 0;
        v164 = v7[15];
        v810 = 0;
        v811 = 0;
        v165 = *(_QWORD *)(v164 + 8 * v163);
        v166 = v10 + 56LL * *((int *)v9 + 3);
        WORD6(v811) = *((_WORD *)v9 + 8);
        *((_QWORD *)&v810 + 1) = v166;
        if ( WORD6(v811) )
        {
          v167 = (int *)(v165 + 36);
          *(_QWORD *)&v810 = *(_QWORD *)(v165 + 56);
          BYTE14(v811) = 0;
          v15 = sqlite3BtreeIndexMoveto(*(_QWORD *)(v165 + 48), &v810, v165 + 36);
          v798 = v15;
        }
        else
        {
          if ( (*(_WORD *)(v166 + 20) & 0x400) != 0 && (unsigned int)sqlite3VdbeMemExpandBlob(v166) )
            goto LABEL_1455;
          v375 = sqlite3VdbeAllocUnpackedRecord(*(_QWORD *)(v165 + 56));
          v376 = v375;
          if ( !v375 )
            goto LABEL_1455;
          sqlite3VdbeRecordUnpack(
            *(_QWORD *)(v165 + 56),
            *(unsigned int *)(*((_QWORD *)&v810 + 1) + 16LL),
            *(_QWORD *)(*((_QWORD *)&v810 + 1) + 8LL),
            v375);
          *(_BYTE *)(v376 + 30) = 0;
          v167 = (int *)(v165 + 36);
          v798 = sqlite3BtreeIndexMoveto(*(_QWORD *)(v165 + 48), v376, v165 + 36);
          v15 = v798;
          sqlite3DbFreeNN(v5, v376);
        }
        v6 = 0;
        if ( v15 )
          goto LABEL_1459;
        v168 = *v167;
        *(_BYTE *)(v165 + 3) = 0;
        *(_DWORD *)(v165 + 32) = 0;
        *(_BYTE *)(v165 + 2) = v168 != 0;
        if ( *v9 == 29 )
        {
          v12 = 1;
          if ( v168 )
            goto LABEL_118;
          goto LABEL_69;
        }
        if ( v168 )
          goto LABEL_329;
        v12 = 1;
        if ( *v9 != 27 )
        {
          v10 = v800;
          a2 = v797;
          LOBYTE(a4) = v796;
          if ( *v9 == 26 )
            *(_WORD *)(v165 + 12) = *((_WORD *)v9 + 8);
          goto LABEL_44;
        }
        for ( m = 0; m < WORD6(v811); ++m )
        {
          if ( (*(_BYTE *)(56LL * m + *((_QWORD *)&v810 + 1) + 20) & 1) != 0 )
            goto LABEL_69;
        }
        goto LABEL_323;
      }
      switch ( (_DWORD)v16 )
      {
        case 0x1D:
          goto LABEL_277;
        case 0x1E:
          v373 = 56LL * *((int *)v9 + 3);
          v814 = 0;
          if ( (*(_BYTE *)(v373 + v10 + 20) & 0x24) == 0 )
          {
            LOBYTE(v8) = a4;
            LOBYTE(a2) = 67;
            v374 = *(_OWORD *)(v373 + v10 + 16);
            v818 = *(_OWORD *)(v373 + v10);
            v4 = *(_OWORD *)(v373 + v10 + 32);
            v819 = v374;
            *(_QWORD *)&v374 = *(_QWORD *)(v373 + v10 + 48);
            v820 = v4;
            v821 = v374;
            applyAffinity(&v818, a2, v8);
            v6 = 0;
            if ( (BYTE4(v819) & 4) == 0 )
              goto LABEL_329;
            v199 = v818;
            goto LABEL_327;
          }
LABEL_326:
          v199 = *(_QWORD *)(56LL * *((int *)v9 + 3) + v10);
LABEL_327:
          v200 = *(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1));
          v201 = *(_QWORD *)(v200 + 48);
          v814 = 0;
          v202 = sqlite3BtreeTableMoveto(v201, v199, 0, &v814);
          v6 = 0;
          *(_QWORD *)(v200 + 80) = v199;
          *(_WORD *)(v200 + 2) = 0;
          v15 = v202;
          *(_DWORD *)(v200 + 32) = 0;
          v798 = v202;
          *(_DWORD *)(v200 + 36) = v814;
          if ( !v814 )
          {
LABEL_688:
            v226 = v15 == 0;
LABEL_371:
            if ( !v226 )
              goto LABEL_1459;
            goto LABEL_49;
          }
          if ( *((_DWORD *)v9 + 2) )
            goto LABEL_329;
          v15 = sqlite3ReportError(11, 98845, "database corruption");
          v798 = v15;
LABEL_687:
          v6 = 0;
          goto LABEL_688;
        case 0x1F:
          goto LABEL_326;
      }
      if ( (_DWORD)v16 != 32 )
      {
        v364 = *((int *)v9 + 1);
        v365 = v7[15];
        LODWORD(v805) = 0;
        v366 = *(_QWORD *)(*(_QWORD *)(v365 + 8 * v364) + 48LL);
        v367 = sqlite3BtreeFirst(v366, &v805);
        v6 = 0;
        v798 = v367;
        v15 = v367;
        if ( v367 )
          goto LABEL_1459;
        if ( (_DWORD)v805 )
        {
          v368 = -1;
        }
        else
        {
          v369 = sqlite3BtreeRowCountEst(v366);
          v368 = (__int16)sqlite3LogEst(v369, v370, v371, v372);
          v6 = 0;
        }
        if ( v368 < *((int *)v9 + 3) || v368 > *((int *)v9 + 4) )
        {
          LODWORD(v805) = 0;
          goto LABEL_49;
        }
        v12 = 1;
        LODWORD(v805) = 1;
        goto LABEL_69;
      }
      goto LABEL_1233;
    }
    if ( (_DWORD)v16 == 22 )
      goto LABEL_246;
    if ( (unsigned int)v16 > 0xB )
    {
      if ( (unsigned int)v16 <= 0x11 )
      {
        if ( (_DWORD)v16 == 17 )
        {
          v61 = sqlite3VdbeBooleanValue(v10 + 56LL * *((int *)v9 + 1), *((_DWORD *)v9 + 3) == 0);
          v6 = 0;
          v12 = 1;
          if ( v61 )
            goto LABEL_42;
LABEL_69:
          v8 = v799;
LABEL_70:
          v9 = (unsigned __int8 *)(v8 + 24LL * (*((_DWORD *)v9 + 2) - (int)v12));
LABEL_71:
          v7 = a1;
          v5 = v801;
          v10 = v800;
          goto LABEL_72;
        }
        v335 = v16 - 12;
        if ( !v335 )
        {
          v350 = 56LL * *((int *)v9 + 1);
          *(_WORD *)(v350 + v10 + 20) = 4;
          v351 = *(int *)(v350 + v10);
          *(_QWORD *)(v350 + v10) = (int)(-1431655765 * ((__int64)&v9[-v8] >> 3));
          v352 = 3 * v351;
          goto LABEL_626;
        }
        v336 = v335 - 1;
        if ( v336 )
        {
          v337 = v336 - 1;
          if ( !v337 )
          {
            if ( (a2 & 0x80000000) == 0LL )
            {
              if ( (_DWORD)a2 )
                v346 = *((_DWORD *)v9 + 3);
              else
                v346 = *((_DWORD *)v9 + 2);
            }
            else
            {
              v346 = *((_DWORD *)v9 + 1);
            }
            v347 = v346 - (int)v12;
            goto LABEL_615;
          }
          v338 = v337 - 1;
          if ( !v338 )
          {
            v341 = v7[33];
            if ( v341 )
            {
              a4 = *(_QWORD *)(v341 + 40);
              v342 = (unsigned __int64)(-1431655765 * (unsigned int)((__int64)&v9[-v7[17]] >> 3)) >> 3;
              v343 = (-85 * (unsigned __int8)((__int64)&v9[-v7[17]] >> 3)) & 7;
              v344 = *(unsigned __int8 *)(v342 + a4);
              if ( _bittest(&v344, v343) )
                goto LABEL_69;
              v345 = v344 | (1 << v343);
              a2 = v797;
              *(_BYTE *)(v342 + a4) = v345;
            }
            else if ( *(_DWORD *)(v7[17] + 4) == *((_DWORD *)v9 + 1) )
            {
              goto LABEL_69;
            }
            v8 = v799;
            *((_DWORD *)v9 + 1) = *(_DWORD *)(v7[17] + 4);
            goto LABEL_73;
          }
          if ( v338 != 1 )
            goto LABEL_51;
          v339 = sqlite3VdbeBooleanValue(v10 + 56LL * *((int *)v9 + 1), *((unsigned int *)v9 + 3));
          v6 = 0;
          v340 = v339 == 0;
          goto LABEL_604;
        }
        v348 = v10 + 56LL * *((int *)v9 + 1);
        v349 = *(_WORD *)(v348 + 20);
        if ( (v349 & 4) == 0 )
        {
          LOBYTE(v8) = a4;
          LOBYTE(a2) = 67;
          applyAffinity(v10 + 56LL * *((int *)v9 + 1), a2, v8);
          v349 = *(_WORD *)(v348 + 20);
          v6 = 0;
          if ( (v349 & 4) == 0 )
          {
            if ( !*((_DWORD *)v9 + 2) )
            {
              v15 = 20;
              goto LABEL_1459;
            }
            goto LABEL_329;
          }
          v8 = v799;
          v12 = 1;
          a2 = v797;
        }
        a4 = 62020;
        *(_WORD *)(v348 + 20) = v349 & 0xF240 | 4;
LABEL_165:
        LOBYTE(a4) = v796;
        goto LABEL_51;
      }
      if ( (_DWORD)v16 != 18 )
      {
        if ( (_DWORD)v16 != 19 )
        {
          if ( (_DWORD)v16 != 20 )
            goto LABEL_246;
          v355 = *(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1));
          if ( !v355 || !*(_BYTE *)(v355 + 2) )
            goto LABEL_628;
          sqlite3VdbeMemSetNull(v10 + 56LL * *((int *)v9 + 3));
          v6 = 0;
LABEL_329:
          v12 = 1;
          goto LABEL_69;
        }
        v356 = v10 + 56LL * *((int *)v9 + 2);
        if ( ((unsigned __int8)v12 & *(_BYTE *)(v10 + 56LL * *((int *)v9 + 1) + 20)) == 0 )
        {
          sqlite3VdbeBooleanValue(v10 + 56LL * *((int *)v9 + 1), 0);
          v34 = v356;
          goto LABEL_112;
        }
        goto LABEL_637;
      }
      if ( *((int *)v9 + 1) < 0 )
      {
        LOBYTE(v360) = *((_BYTE *)qword_1800B5270 + (*(_WORD *)(56LL * *((int *)v9 + 3) + v10 + 20) & 0x3F));
      }
      else
      {
        v357 = *(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1));
        if ( *((_DWORD *)v9 + 3) < (int)*(unsigned __int16 *)(v357 + 74) )
        {
          v358 = *(unsigned int *)(v357 + 4LL * *((int *)v9 + 3) + 120);
          if ( (unsigned int)v358 < 0xC )
            v359 = *((unsigned __int8 *)&qword_1800C11B0[1] + v358);
          else
            v359 = ((unsigned __int8)v12 & (unsigned __int8)v358) != 0 ? 4 : 8;
          goto LABEL_646;
        }
        v360 = *((_DWORD *)v9 + 4);
      }
      v359 = (_WORD)v12 << (v360 - v12);
LABEL_646:
      v120 = ((unsigned __int16)v359 & *((_WORD *)v9 + 1)) == 0;
      goto LABEL_215;
    }
    if ( (_DWORD)v16 == 11 )
    {
      v334 = 56LL * *((int *)v9 + 1);
      *(_QWORD *)(v334 + v10) = *((_DWORD *)v9 + 3) - (int)v12;
      *(_WORD *)(v334 + v10 + 20) = 4;
      if ( !*((_DWORD *)v9 + 2) )
        goto LABEL_51;
      goto LABEL_69;
    }
    if ( (unsigned int)v16 > 5 )
    {
      v80 = v16 - 6;
      if ( !v80 )
      {
        v323 = 56LL * *((int *)v9 + 3);
        v324 = a1[14];
        v325 = (int *)(v323 + v10 + 56);
        v326 = *(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1));
        v327 = *v325;
        v328 = *(unsigned int *)(v323 + v800);
        v329 = *(__int64 ***)(v326 + 48);
        v330 = *v329;
        v331 = **v329;
        if ( *v325 > 0 )
        {
          do
          {
            v332 = (unsigned int)v6;
            LODWORD(v6) = v6 + 1;
            *(_QWORD *)(v324 + 8 * v332) = &v325[14 * (int)v6];
          }
          while ( (int)v6 < v327 );
        }
        v15 = (*(__int64 (__fastcall **)(__int64 **, __int64, _QWORD))(v331 + 64))(v329, v328, *((_QWORD *)v9 + 2));
        v798 = v15;
        sqlite3VtabImportErrmsg(a1, v330);
        v6 = 0;
        if ( v15 )
          goto LABEL_1458;
        v333 = (*(__int64 (__fastcall **)(__int64 **))(v331 + 80))(v329);
        v6 = 0;
        v12 = 1;
        *(_BYTE *)(v326 + 2) = 0;
        if ( !v333 )
        {
          v7 = a1;
          v5 = v801;
          goto LABEL_118;
        }
        goto LABEL_69;
      }
      v81 = v80 - 1;
      if ( v81 )
      {
        v82 = v81 - 1;
        if ( v82 )
        {
          v313 = v82 - 1;
          if ( v313 )
          {
            if ( v313 != 1 )
              goto LABEL_51;
            a2 = 0xAAAAAAAAAAAAAAABuLL;
            v314 = 56LL * *((int *)v9 + 1);
            *(_WORD *)(v314 + v10 + 20) = 4;
            *(_QWORD *)(v314 + v10) = (int)(-1431655765 * ((__int64)&v9[-v8] >> 3));
          }
          goto LABEL_37;
        }
        goto LABEL_162;
      }
      v804 = 0;
      if ( *(_BYTE *)(v5 + 103) )
        goto LABEL_1455;
      v315 = *(__int64 **)(*((_QWORD *)v9 + 2) + 16LL);
      if ( v315 )
      {
        v6 = *v315;
        if ( *v315 )
        {
          if ( !*(_QWORD *)(v6 + 104) )
          {
            v6 = 0;
            goto LABEL_1042;
          }
          v316 = 0;
          v317 = *((unsigned int *)v9 + 2);
          v318 = *(_BYTE *)(v5 + 108);
          v319 = v7[14];
          v320 = v10 + 56LL * *((int *)v9 + 3);
          if ( (int)v317 > 0 )
          {
            do
            {
              v321 = (unsigned int)v316++;
              *(_QWORD *)(v319 + 8 * v321) = v320;
              v320 += 56;
            }
            while ( v316 < (int)v317 );
            v10 = v800;
          }
          *(_BYTE *)(v5 + 108) = v9[2];
          v798 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64 *))(v6 + 104))(v315, v317, v319, &v804);
          *(_BYTE *)(v5 + 108) = v318;
          v15 = v798;
          sqlite3VtabImportErrmsg(v7, v315);
          v6 = 0;
          if ( !v798 )
          {
            if ( *((_DWORD *)v9 + 1) )
              *(_QWORD *)(v5 + 56) = v804;
            goto LABEL_586;
          }
          if ( (_BYTE)v798 != 19 || !*(_BYTE *)(*((_QWORD *)v9 + 2) + 28LL) )
          {
LABEL_586:
            v12 = 1;
            ++v7[7];
            goto LABEL_179;
          }
          v322 = *((_WORD *)v9 + 1);
          if ( v322 != 4 )
          {
            if ( v322 == 5 )
              LOBYTE(v322) = 2;
            *((_BYTE *)v7 + 196) = v322;
            goto LABEL_1459;
          }
          v15 = 0;
          v798 = 0;
LABEL_1024:
          v8 = v799;
          a2 = v797;
          LOBYTE(a4) = v796;
LABEL_1042:
          v12 = 1;
          goto LABEL_51;
        }
      }
LABEL_1428:
      v15 = 6;
      goto LABEL_1459;
    }
    if ( (_DWORD)v16 == 5 )
    {
      if ( *((_DWORD *)v9 + 2) )
        v312 = v10 + 56LL * *((int *)v9 + 2);
      else
        v312 = 0;
      v225 = sqlite3RunVacuum(v7 + 21, v5, *((unsigned int *)v9 + 1), v312);
      goto LABEL_572;
    }
    if ( (_DWORD)v16 )
    {
      v103 = v16 - 1;
      if ( v103 )
      {
        v104 = v103 - 1;
        if ( !v104 )
        {
          a2 = *((unsigned int *)v9 + 2);
          LODWORD(v803) = 0;
          if ( (_DWORD)a2 && (*(_QWORD *)(v5 + 48) & 0x200100000LL) != 0 )
          {
            v15 = (*(_QWORD *)(v5 + 48) & 0x100000LL) != 0 ? 8 : 11;
            goto LABEL_1459;
          }
          v105 = *(_QWORD *)(v5 + 32);
          v106 = 32LL * *((int *)v9 + 1);
          v107 = *(_QWORD *)(v106 + v105 + 8);
          if ( v107 )
          {
            v108 = sqlite3BtreeBeginTrans(*(_QWORD *)(v106 + v105 + 8), a2, &v803);
            v6 = 0;
            v798 = v108;
            v15 = v108;
            if ( v108 )
            {
              if ( (_BYTE)v108 != 5 )
                goto LABEL_1459;
              *((_DWORD *)v7 + 13) = v108;
              *((_DWORD *)v7 + 12) = -1431655765 * ((__int64)&v9[-v799] >> 3);
              goto LABEL_357;
            }
            if ( (v7[25] & 0x20) == 0 || !*((_DWORD *)v9 + 2) || *(_BYTE *)(v5 + 101) && *(int *)(v5 + 220) <= 1 )
            {
LABEL_195:
              if ( *((_WORD *)v9 + 1)
                && ((_DWORD)v803 != *((_DWORD *)v9 + 3)
                 || *(_DWORD *)(*(_QWORD *)(v106 + v105 + 24) + 4LL) != *((_DWORD *)v9 + 4)) )
              {
                sqlite3DbFree(v5, v7[21]);
                v7[21] = sqlite3DbStrDup(v5, "database schema has changed");
                a2 = *((int *)v9 + 1);
                if ( **(_DWORD **)(32 * a2 + *(_QWORD *)(v5 + 32) + 24) != (_DWORD)v803 )
                  sqlite3ResetOneSchema(v5);
                v15 = 17;
                *((_DWORD *)v7 + 50) = v7[25] & 0xFFFFFFEC | 1;
                goto LABEL_393;
              }
              goto LABEL_198;
            }
            v287 = *((_DWORD *)v7 + 16);
            if ( !v287 )
            {
              v287 = ++*(_DWORD *)(v5 + 756) + *(_DWORD *)(v5 + 752);
              *((_DWORD *)v7 + 16) = v287;
            }
            v288 = sqlite3VtabSavepoint(v5, 0, (unsigned int)(v287 - 1));
            v6 = 0;
            v798 = v288;
            v15 = v288;
            if ( !v288 )
            {
              v15 = sqlite3BtreeBeginStmt(v107, *((unsigned int *)v7 + 16));
              v798 = v15;
              v6 = 0;
            }
            v7[11] = *(_QWORD *)(v5 + 760);
            v7[12] = *(_QWORD *)(v5 + 768);
          }
          if ( v15 )
            goto LABEL_1459;
          goto LABEL_195;
        }
        v270 = v104 - 1;
        if ( !v270 )
        {
          v282 = *((_DWORD *)v9 + 2);
          v283 = *((_DWORD *)v9 + 1);
          v833 = 0;
          v834 = -1;
          v284 = sqlite3Checkpoint(v5, v283, v282, (unsigned int)&v834, (__int64)&v834 + 4);
          v6 = 0;
          v798 = v284;
          v15 = v284;
          if ( v284 )
          {
            if ( v284 != 5 )
              goto LABEL_1459;
            v15 = 0;
            v798 = 0;
            v833 = 1;
          }
          v285 = 0;
          v286 = v10 + 56LL * *((int *)v9 + 3);
          do
          {
            sqlite3VdbeMemSetInt64(v286);
            v286 += 56;
            ++v285;
          }
          while ( v285 != 3 );
          goto LABEL_502;
        }
        if ( v270 != 1 )
          goto LABEL_51;
        v271 = out2Prerelease(v7, v9);
        v272 = *(_QWORD *)(32LL * *((int *)v9 + 1) + *(_QWORD *)(v801 + 32) + 8);
        v273 = *(_QWORD **)(v272 + 8);
        v274 = *v273;
        v275 = *(unsigned __int8 *)(*v273 + 9LL);
        v276 = v275;
        if ( *((_DWORD *)v9 + 3) != -1 )
          v276 = *((_DWORD *)v9 + 3);
        if ( !(unsigned int)sqlite3PagerOkToChangeJournalMode(*v273) )
          v276 = v275;
        v277 = sqlite3PagerFilename(v274, 1);
        if ( v276 == 5 && (!(unsigned int)sqlite3Strlen30(v277) || !(unsigned int)sqlite3PagerWalSupported(v274)) )
        {
          v276 = v275;
          goto LABEL_488;
        }
        if ( v276 == v275 || v275 != 5 && v276 != 5 )
        {
LABEL_488:
          if ( !v15 )
          {
LABEL_490:
            v278 = sqlite3PagerSetJournalMode(v274, v276);
            *(_WORD *)(v271 + 20) = 8706;
            v280 = sqlite3JournalModename(v278, v279);
            *(_QWORD *)(v271 + 8) = v280;
            *(_DWORD *)(v271 + 16) = sqlite3Strlen30(v280);
            *(_BYTE *)(v271 + 22) = 1;
            sqlite3VdbeChangeEncoding(v271, v796);
            v7 = a1;
            goto LABEL_492;
          }
LABEL_489:
          v276 = v275;
          goto LABEL_490;
        }
        if ( *(_BYTE *)(v801 + 101) && *(int *)(v801 + 220) <= 1 )
        {
          if ( v275 == 5 )
          {
            v798 = sqlite3PagerCloseWal(v274, v801);
            v15 = v798;
            if ( v798 )
              goto LABEL_489;
            sqlite3PagerSetJournalMode(v274, v276);
          }
          else
          {
            if ( v275 == 4 )
              sqlite3PagerSetJournalMode(v274, 2);
            if ( v15 )
              goto LABEL_489;
          }
          v15 = sqlite3BtreeSetVersion(v272, (unsigned int)(v276 == 5) + 1);
          v798 = v15;
          goto LABEL_488;
        }
        v7 = a1;
        v788 = "into";
        v15 = 1;
        v789 = "cannot change %s wal mode from within a transaction";
        if ( v276 != 5 )
          v788 = "out of";
LABEL_1451:
        sqlite3VdbeError(v7, v789, v788);
        goto LABEL_393;
      }
      v227 = *((_DWORD *)v9 + 1);
      v228 = *((_DWORD *)v9 + 2);
      if ( v227 != *(unsigned __int8 *)(v5 + 101) )
      {
        if ( v228 )
        {
          sqlite3RollbackAll(v5, 516);
          v229 = 1;
        }
        else
        {
          if ( v227 && *(int *)(v5 + 224) > 0 )
          {
            sqlite3VdbeError(v7, "cannot commit transaction - SQL statements in progress");
LABEL_1417:
            v15 = 5;
            goto LABEL_393;
          }
          v15 = sqlite3VdbeCheckFk(v7, (unsigned int)v12);
          if ( v15 )
          {
LABEL_357:
            v8 = v801;
            goto LABEL_358;
          }
          v229 = v227;
        }
        *(_BYTE *)(v5 + 101) = v229;
        if ( (unsigned int)sqlite3VdbeHalt(v7) == 5 )
        {
          v15 = 5;
          *((_DWORD *)v7 + 12) = -1431655765 * ((__int64)&v9[-v799] >> 3);
          *(_BYTE *)(v5 + 101) = 1 - v227;
          *((_DWORD *)v7 + 13) = 5;
        }
        else
        {
          sqlite3CloseSavepoints(v5);
          v15 = *((_DWORD *)v7 + 13) != 0 ? 1 : 101;
        }
        v8 = v801;
        goto LABEL_358;
      }
      if ( v227 )
      {
        v790 = "cannot rollback - no transaction is active";
        if ( !v228 )
          v790 = "cannot commit - no transaction is active";
        sqlite3VdbeError(v7, v790);
      }
      else
      {
        sqlite3VdbeError(v7, "cannot start a transaction within a transaction");
      }
    }
    else
    {
      v289 = *((_DWORD *)v9 + 1);
      v290 = (const void *)*((_QWORD *)v9 + 2);
      LODWORD(v803) = v289;
      if ( !v289 )
      {
        if ( *(int *)(v5 + 224) <= 0 )
        {
          v291 = (int)sqlite3Strlen30(v290);
          v292 = sqlite3VtabSavepoint(v5, 0, (unsigned int)(*(_DWORD *)(v5 + 752) + *(_DWORD *)(v5 + 756)));
          v6 = 0;
          v798 = v292;
          v15 = v292;
          if ( v292 )
            goto LABEL_1459;
          v293 = (_QWORD *)sqlite3DbMallocRawNN(v5, v291 + 33);
          v6 = 0;
          v294 = v293;
          if ( v293 )
          {
            *v293 = v293 + 4;
            memcpy_0(v293 + 4, v290, (int)v291 + 1);
            v6 = 0;
            if ( *(_BYTE *)(v5 + 101) )
            {
              *(_BYTE *)(v5 + 101) = 0;
              *(_BYTE *)(v5 + 109) = 1;
            }
            else
            {
              ++*(_DWORD *)(v5 + 752);
            }
            v294[3] = *(_QWORD *)(v5 + 736);
            v295 = *(_QWORD *)(v5 + 760);
            *(_QWORD *)(v5 + 736) = v294;
            v294[1] = v295;
            v294[2] = *(_QWORD *)(v5 + 768);
          }
          goto LABEL_564;
        }
        sqlite3VdbeError(v7, "cannot open savepoint - SQL statements in progress");
        goto LABEL_1417;
      }
      v296 = *(_QWORD **)(v5 + 736);
      v297 = 0;
      while ( v296 )
      {
        v298 = sqlite3StrICmp(*v296, v290);
        v6 = 0;
        if ( !v298 )
        {
          if ( *(int *)(v5 + 224) > 0 && v289 == 1 )
          {
            v7 = a1;
            sqlite3VdbeError(a1, "cannot release savepoint - SQL statements in progress");
            goto LABEL_1417;
          }
          v299 = v296 + 3;
          v804 = (__int64)(v296 + 3);
          if ( v296[3] || !*(_BYTE *)(v5 + 109) )
          {
            LODWORD(v805) = 0;
          }
          else
          {
            LODWORD(v805) = 1;
            v300 = 1;
            if ( v289 == 1 )
            {
              v301 = sqlite3VdbeCheckFk(a1, 1);
              v8 = v801;
              if ( v301 )
              {
                v15 = v301;
                v7 = a1;
                goto LABEL_358;
              }
              *(_BYTE *)(v801 + 101) = 1;
              if ( (unsigned int)sqlite3VdbeHalt(a1) == 5 )
              {
                v8 = v801;
                v7 = a1;
                v15 = 5;
                *((_DWORD *)a1 + 12) = -1431655765 * ((__int64)&v9[-v799] >> 3);
                *(_BYTE *)(v801 + 101) = 0;
                *((_DWORD *)a1 + 13) = 5;
                goto LABEL_358;
              }
              v302 = *((_DWORD *)a1 + 13);
              v6 = 0;
              a4 = v801;
              v798 = v302;
              if ( v302 )
                *(_BYTE *)(v801 + 101) = 0;
              else
                *(_BYTE *)(v801 + 109) = 0;
              v303 = (int *)(v801 + 752);
              goto LABEL_550;
            }
          }
          a4 = v801;
          v303 = (int *)(v5 + 752);
          v304 = *v303;
          if ( v289 == 2 )
          {
            v305 = 0;
            v306 = *(_DWORD *)(v801 + 44) & 1;
            while ( v305 < *(_DWORD *)(a4 + 40) )
            {
              v307 = sqlite3BtreeTripAllCursors(*(_QWORD *)(32LL * v305 + *(_QWORD *)(a4 + 32) + 8), 516, v306 ^ 1u);
              v6 = 0;
              v798 = v307;
              if ( v307 )
                goto LABEL_1457;
              a4 = v801;
              ++v305;
            }
          }
          else
          {
            v306 = 0;
          }
          v302 = v798;
          v297 = v304 + ~v297;
          v308 = 0;
          v309 = v803;
          while ( v308 < *(_DWORD *)(a4 + 40) )
          {
            v302 = sqlite3BtreeSavepoint(*(_QWORD *)(32LL * v308 + *(_QWORD *)(a4 + 32) + 8), v309, v297);
            v6 = 0;
            v798 = v302;
            if ( v302 )
              goto LABEL_1457;
            a4 = v801;
            ++v308;
          }
          if ( v306 )
          {
            sqlite3ExpirePreparedStatements(a4, 0, v8);
            sqlite3ResetAllSchemasOfConnection(v801);
            a4 = v801;
            v302 = v798;
            *(_DWORD *)(v801 + 44) |= 1u;
            v6 = 0;
          }
          v300 = v805;
          v289 = v309;
          v299 = (_QWORD *)v804;
LABEL_550:
          if ( v302 )
          {
LABEL_1457:
            v15 = v798;
            goto LABEL_1458;
          }
          v310 = *(_QWORD **)(a4 + 736);
          if ( v310 != v296 )
          {
            do
            {
              *(_QWORD *)(a4 + 736) = v310[3];
              sqlite3DbFree(a4, v310);
              --*v303;
              a4 = v801;
              v310 = *(_QWORD **)(v801 + 736);
            }
            while ( v310 != v296 );
            v300 = v805;
            v6 = 0;
          }
          v12 = 1;
          if ( v289 != 1 )
          {
            v5 = v801;
            *(_QWORD *)(v801 + 760) = v296[1];
            *(_QWORD *)(v801 + 768) = v296[2];
            if ( v300 && v289 != 2 )
            {
              v15 = v798;
              v7 = a1;
              goto LABEL_565;
            }
LABEL_557:
            v311 = sqlite3VtabSavepoint(v5, v289, v297);
            v6 = 0;
            v798 = v311;
            v15 = v311;
            if ( !v311 )
              goto LABEL_563;
            goto LABEL_1458;
          }
          *(_QWORD *)(a4 + 736) = *v299;
          sqlite3DbFree(a4, v296);
          v6 = 0;
          if ( !v300 )
          {
            --*v303;
            v5 = v801;
            goto LABEL_557;
          }
          v15 = v798;
          v5 = v801;
LABEL_563:
          v7 = a1;
LABEL_564:
          v12 = 1;
LABEL_565:
          if ( *((_BYTE *)v7 + 199) == 3 )
          {
            v15 = 101;
            goto LABEL_357;
          }
LABEL_118:
          v10 = v800;
LABEL_119:
          v8 = v799;
LABEL_72:
          a2 = v797;
LABEL_73:
          LOBYTE(a4) = v796;
LABEL_51:
          v11 = v809;
          v9 += 24;
          goto LABEL_8;
        }
        v296 = (_QWORD *)v296[3];
        ++v297;
      }
      v7 = a1;
      sqlite3VdbeError(a1, "no such savepoint: %s", (const char *)v290);
    }
    v15 = 1;
    goto LABEL_393;
  }
  if ( (unsigned int)v16 <= 0x44 )
  {
    if ( (_DWORD)v16 != 68 )
    {
      if ( (unsigned int)v16 <= 0x39 )
      {
        if ( (_DWORD)v16 == 57 )
          goto LABEL_15;
        if ( (unsigned int)v16 > 0x33 )
        {
          if ( (_DWORD)v16 != 52 && (_DWORD)v16 != 53 && (_DWORD)v16 != 54 && (unsigned int)(v16 - 55) > 1 )
            goto LABEL_51;
LABEL_15:
          v18 = v10 + 56LL * *((int *)v9 + 1);
          v19 = v10 + 56LL * *((int *)v9 + 3);
          v20 = *(_WORD *)(v18 + 20);
          v21 = *(_WORD *)(v19 + 20);
          v22 = v21;
          LOWORD(v22) = v20 & v21;
          if ( ((unsigned __int8)v20 & (unsigned __int8)v21 & 4) != 0 )
          {
            if ( *(_QWORD *)v19 <= *(_QWORD *)v18 )
            {
              v70 = *v9;
              if ( *(_QWORD *)v19 < *(_QWORD *)v18 )
              {
                if ( *((_BYTE *)&qword_1800B4ED0[25] + v70 + 4) )
                  goto LABEL_70;
                a2 = 0xFFFFFFFFLL;
              }
              else
              {
                if ( *((_BYTE *)&qword_1800B4ED0[26] + v70 + 2) )
                  goto LABEL_70;
                a2 = 0;
              }
LABEL_138:
              v7 = a1;
              v5 = v801;
              v10 = v800;
              v797 = a2;
              goto LABEL_51;
            }
            v413 = *((_BYTE *)&qword_1800B4ED0[27] + v16) == 0;
          }
          else
          {
            v23 = v20 | v21;
            if ( ((unsigned __int8)(v20 | v21) & (unsigned __int8)v12) == 0 )
            {
              v24 = v9[2] & 0x47;
              if ( v24 >= 0x43u )
              {
                if ( (v23 & 2) != 0 )
                {
                  if ( (v20 & 0x2E) == 2 )
                  {
                    applyNumericAffinity(v18, 0);
                    v21 = *(_WORD *)(v19 + 20);
                  }
                  if ( (v21 & 0x2E) == 2 )
                    applyNumericAffinity(v19, 0);
                }
              }
              else if ( v24 == 66 && (v23 & 2) != 0 )
              {
                if ( (v20 & 2) != 0 )
                {
                  *(_WORD *)(v18 + 20) = v20 & 0xFFD3;
                }
                else if ( (v20 & 0x2C) != 0 )
                {
                  LOBYTE(v8) = v12;
                  LOBYTE(v22) = a4;
                  sqlite3VdbeMemStringify(v18, v22, v8);
                  v20 = *(_WORD *)(v18 + 20) ^ (*(_WORD *)(v18 + 20) ^ v20) & 0xDBF;
                  LOBYTE(v12) = 1;
                  if ( v18 == v19 )
                    v21 = v20 | 2;
                }
                if ( (v21 & 2) != 0 )
                {
                  *(_WORD *)(v19 + 20) &= 0xFFD3u;
                }
                else if ( (v21 & 0x2C) != 0 )
                {
                  LOBYTE(v22) = v796;
                  LOBYTE(v8) = v12;
                  sqlite3VdbeMemStringify(v19, v22, v8);
                  v21 = *(_WORD *)(v19 + 20) ^ (*(_WORD *)(v19 + 20) ^ v21) & 0xDBF;
                }
              }
              v25 = sqlite3MemCompare(v19, v18, *((_QWORD *)v9 + 2));
              v8 = v799;
              v6 = 0;
              v797 = v25;
              a2 = (unsigned int)v25;
              v12 = 1;
              if ( v25 < 0 )
                goto LABEL_20;
              goto LABEL_405;
            }
            if ( (v9[2] & 0x80u) != 0 )
            {
              if ( (v22 & 1) != 0 && (v21 & 0x100) == 0 )
              {
                a2 = 0;
              }
              else
              {
                if ( ((unsigned __int8)v21 & (unsigned __int8)v12) != 0 )
                {
                  a2 = 0xFFFFFFFFLL;
                  v797 = -1;
LABEL_20:
                  v26 = *((_BYTE *)&qword_1800B4ED0[25] + *v9 + 4);
                  goto LABEL_21;
                }
                a2 = (unsigned int)v12;
              }
              v797 = a2;
LABEL_405:
              v240 = *v9;
              if ( (_DWORD)a2 )
                v26 = *((_BYTE *)&qword_1800B4ED0[27] + v240);
              else
                v26 = *((_BYTE *)&qword_1800B4ED0[26] + v240 + 2);
LABEL_21:
              *(_WORD *)(v19 + 20) = v21;
              *(_WORD *)(v18 + 20) = v20;
              if ( !v26 )
              {
                v7 = a1;
                v5 = v801;
                v10 = v800;
                goto LABEL_73;
              }
              goto LABEL_69;
            }
            v413 = (v9[2] & 0x10) == 0;
          }
          if ( !v413 )
            goto LABEL_70;
          a2 = (unsigned int)v12;
          goto LABEL_138;
        }
        if ( (_DWORD)v16 == 51 )
        {
          if ( ((unsigned __int8)v12 & *(_BYTE *)(56LL * *((int *)v9 + 1) + v10 + 20)) != 0 )
            goto LABEL_51;
          goto LABEL_70;
        }
        v116 = v16 - 46;
        if ( v116 )
        {
          v117 = v116 - 1;
          if ( v117 )
          {
            v118 = v117 - 1;
            if ( v118 )
            {
              v119 = v118 - 1;
              if ( v119 )
              {
                if ( v119 != 1 )
                  goto LABEL_51;
                v120 = ((unsigned __int8)v12 & *(_BYTE *)(56LL * *((int *)v9 + 1) + v10 + 20)) == 0;
LABEL_215:
                if ( v120 )
                  goto LABEL_51;
                goto LABEL_70;
              }
              if ( *((_DWORD *)v9 + 1) )
                v389 = *(_QWORD *)(v5 + 760) == 0;
              else
                v389 = v7[10] == 0;
              if ( !v389 )
                goto LABEL_51;
              v79 = *(_QWORD *)(v5 + 768) == 0;
LABEL_155:
              if ( !v79 )
                goto LABEL_51;
              goto LABEL_70;
            }
            v390 = *((_QWORD *)v9 + 2);
            v804 = v390;
            if ( *((_WORD *)v9 + 1) )
            {
              for ( n = v7[33]; ; n = *(_QWORD *)(n + 8) )
              {
                if ( !n )
                  goto LABEL_730;
                if ( *(_QWORD *)(n + 48) == *(_QWORD *)(v390 + 32) )
                  break;
              }
              v8 = v799;
              goto LABEL_51;
            }
LABEL_730:
            if ( *((_DWORD *)v7 + 70) >= *(_DWORD *)(v5 + 176) )
            {
              v15 = v12;
              sqlite3VdbeError(v7, "too many levels of trigger recursion");
              goto LABEL_393;
            }
            v392 = (int *)(v390 + 16);
            v393 = (int *)(v390 + 8);
            v394 = v10 + 56LL * *((int *)v9 + 3);
            if ( (*(_BYTE *)(v394 + 20) & 0x10) != 0 )
            {
              v397 = *(_QWORD *)(v394 + 8);
              v399 = (__int64 *)v390;
LABEL_740:
              *((_DWORD *)v7 + 70) += v12;
              v10 = v397 + 112;
              *(_QWORD *)(v397 + 8) = v7[33];
              v800 = v397 + 112;
              *(_QWORD *)(v397 + 56) = *(_QWORD *)(v801 + 56);
              *(_QWORD *)(v397 + 96) = v7[7];
              *(_QWORD *)(v397 + 104) = *(_QWORD *)(*v7 + 120);
              *(_QWORD *)(v397 + 64) = v7[37];
              v7[37] = 0;
              v7[7] = 0;
              v7[33] = v397;
              v7[13] = v397 + 112;
              v401 = *(int *)(v397 + 88);
              *((_DWORD *)v7 + 9) = v401;
              *((_DWORD *)v7 + 10) = *(unsigned __int16 *)(v397 + 92);
              v7[15] = v397 + 112 + 56 * v401;
              v402 = (void *)(v397 + 112 + 8 * (*v392 + 7 * v401));
              *(_QWORD *)(v397 + 40) = v402;
              memset_0(v402, 0, (*v393 + 7) / 8);
              v8 = *v399;
              v5 = v801;
              v7[17] = *v399;
              v403 = *v393;
              v15 = v798;
              v9 = (unsigned __int8 *)(v8 - 24);
              v799 = v8;
              *((_DWORD *)v7 + 36) = v403;
LABEL_1307:
              v6 = 0;
              goto LABEL_38;
            }
            v395 = *v392 + *(_DWORD *)(v390 + 12) + 1;
            if ( *v392 )
              v395 = *v392 + *(_DWORD *)(v390 + 12);
            v396 = (*v393 + 7) / 8 + 8 * (*v392 + 7 * (v395 + 2));
            v397 = sqlite3DbMallocZero(v801, v396);
            if ( v397 )
            {
              sqlite3VdbeMemRelease(v394);
              *(_QWORD *)(v394 + 48) = sqlite3VdbeFrameMemDel;
              v398 = v397 + 112;
              *(_DWORD *)(v394 + 16) = v396;
              v7 = a1;
              *(_WORD *)(v394 + 20) = 4112;
              *(_QWORD *)(v394 + 8) = v397;
              v399 = (__int64 *)v804;
              *(_QWORD *)v397 = a1;
              *(_DWORD *)(v397 + 88) = v395;
              *(_DWORD *)(v397 + 92) = *v392;
              *(_DWORD *)(v397 + 76) = -1431655765 * ((__int64)&v9[-v799] >> 3);
              *(_QWORD *)(v397 + 24) = a1[13];
              *(_DWORD *)(v397 + 84) = *((_DWORD *)a1 + 9);
              *(_QWORD *)(v397 + 32) = a1[15];
              *(_DWORD *)(v397 + 72) = *((_DWORD *)a1 + 10);
              *(_QWORD *)(v397 + 16) = a1[17];
              *(_DWORD *)(v397 + 80) = *((_DWORD *)a1 + 36);
              *(_QWORD *)(v397 + 48) = v399[4];
              v400 = v397 + 56 * (v395 + 2LL);
              if ( v397 + 112 != v400 )
              {
                do
                {
                  *(_WORD *)(v398 + 20) = 0;
                  *(_QWORD *)(v398 + 24) = v801;
                  v398 += 56;
                }
                while ( v398 != v400 );
                v7 = a1;
              }
              LODWORD(v12) = 1;
              goto LABEL_740;
            }
LABEL_1453:
            v7 = a1;
            goto LABEL_1454;
          }
          v404 = *((_DWORD *)v9 + 4);
          v405 = v10 + 56LL * *((int *)v9 + 1);
          v406 = *((int *)v9 + 3);
          if ( (*(_BYTE *)(v405 + 20) & 0x10) == 0 )
          {
            v407 = sqlite3VdbeMemSetRowSet(v405);
            v6 = 0;
            if ( v407 )
              goto LABEL_1455;
          }
          v408 = 56 * v406;
          v409 = v404 < 0;
          if ( !v404 )
          {
LABEL_746:
            if ( v409 )
              goto LABEL_198;
            sqlite3RowSetInsert(*(_QWORD *)(v405 + 8), *(_QWORD *)(v408 + v800));
            goto LABEL_102;
          }
          v410 = sqlite3RowSetTest(*(_QWORD *)(v405 + 8), (unsigned int)v404, *(_QWORD *)(v408 + v800));
          v6 = 0;
          if ( !v410 )
          {
            v409 = v404 < 0;
            goto LABEL_746;
          }
          goto LABEL_329;
        }
        v411 = *((int *)v9 + 1);
        v804 = 0;
        v412 = v10 + 56 * v411;
        if ( (*(_BYTE *)(v412 + 20) & 0x10) != 0 && (unsigned int)sqlite3RowSetNext(*(_QWORD *)(v412 + 8), &v804) )
        {
          sqlite3VdbeMemSetInt64(v10 + 56LL * *((int *)v9 + 3));
          goto LABEL_1307;
        }
        sqlite3VdbeMemSetNull(v412);
        v6 = 0;
        goto LABEL_795;
      }
      if ( (unsigned int)v16 <= 0x3F )
      {
        if ( (_DWORD)v16 == 63 )
        {
          v419 = *(_QWORD *)(v7[15] + 8LL * *((int *)v9 + 1));
          if ( *(_BYTE *)(v419 + 2) )
            goto LABEL_51;
          v420 = *(__int64 ***)(v419 + 48);
          v421 = *v420;
          v422 = **v420;
          v798 = (*(__int64 (**)(void))(v422 + 72))();
          v15 = v798;
          sqlite3VtabImportErrmsg(v7, v421);
          v6 = 0;
          if ( v798 )
            goto LABEL_1459;
          v423 = (*(__int64 (__fastcall **)(_QWORD))(v422 + 80))(*(_QWORD *)(v419 + 48));
          v10 = v800;
          v6 = 0;
          if ( v423 )
            goto LABEL_38;
LABEL_795:
          LODWORD(v12) = 1;
LABEL_36:
          v8 = v799;
LABEL_37:
          v9 = (unsigned __int8 *)(v8 + 24LL * (*((_DWORD *)v9 + 2) - (int)v12));
LABEL_38:
          if ( *(_DWORD *)(v5 + 408) )
            goto LABEL_1449;
          for ( ii = v816; v809 >= ii; v816 = ii )
          {
            v725 = *(__int64 (__fastcall **)(_QWORD))(v5 + 528);
            if ( !v725 )
              break;
            v726 = *(unsigned int *)(v5 + 544);
            v727 = v725(*(_QWORD *)(v5 + 536));
            v6 = 0;
            if ( v727 )
              goto LABEL_1448;
            ii += v726;
          }
          goto LABEL_41;
        }
        v78 = v16 - 58;
        if ( !v78 )
        {
          v79 = (_DWORD)a2 == 0;
          goto LABEL_155;
        }
        v126 = v78 - 1;
        if ( v126 )
        {
          v127 = v126 - 1;
          if ( !v127 )
          {
            v415 = 56LL * *((int *)v9 + 1);
            v416 = *(_QWORD *)(v415 + v10);
            if ( !v416 )
              goto LABEL_51;
            if ( v416 > 0 )
              *(_QWORD *)(v415 + v10) = v416 - 1;
            goto LABEL_70;
          }
          v128 = v127 - 1;
          if ( !v128 )
          {
            v129 = 56LL * *((int *)v9 + 1);
            v130 = *(_QWORD *)(v129 + v10);
            if ( v130 == 0x8000000000000000uLL )
              goto LABEL_51;
            v42 = v130 - 1;
            *(_QWORD *)(v129 + v10) = v42;
            if ( v42 )
              goto LABEL_51;
            goto LABEL_69;
          }
          if ( v128 != 1 )
            goto LABEL_51;
          v414 = sqlite3BtreeIncrVacuum(*(_QWORD *)(32LL * *((int *)v9 + 1) + *(_QWORD *)(v5 + 32) + 8));
          v6 = 0;
          v798 = v414;
          v15 = v414;
          if ( !v414 )
            goto LABEL_41;
          if ( v414 != 101 )
            goto LABEL_1459;
          v15 = 0;
          v798 = 0;
          goto LABEL_329;
        }
        v417 = 56LL * *((int *)v9 + 1);
        v418 = *(_QWORD *)(v417 + v10);
        if ( v418 > 0 )
        {
          *(_QWORD *)(v417 + v10) = v418 - *((int *)v9 + 3);
          goto LABEL_70;
        }
LABEL_628:
        a2 = v797;
        goto LABEL_51;
      }
      v424 = v16 - 64;
      if ( v424 )
      {
        v425 = v424 - 1;
        if ( v425 )
        {
          v426 = v425 - 1;
          if ( v426 )
          {
            if ( v426 != 1 )
              goto LABEL_51;
            v427 = 56LL * *((int *)v9 + 1);
            if ( (*(_BYTE *)(v427 + v10 + 20) & 4) == 0 )
              goto LABEL_51;
            v347 = *(_QWORD *)(v427 + v10);
LABEL_615:
            v9 = (unsigned __int8 *)(v8 + 24 * v347);
            goto LABEL_51;
          }
        }
        v428 = *((_QWORD *)v9 + 2);
        v429 = v10 + 56LL * *((int *)v9 + 3);
        if ( *(_QWORD *)v428 != v429 )
        {
          v430 = *(unsigned __int8 *)(v428 + 42);
          *(_QWORD *)(v428 + 24) = v7;
          *(_QWORD *)v428 = v429;
          *(_BYTE *)(v428 + 40) = a4;
          while ( 1 )
          {
            v430 -= v12;
            if ( v430 < 0 )
              break;
            *(_QWORD *)(v428 + 8LL * (unsigned int)v430 + 48) = v10 + 56LL * (v430 + *((_DWORD *)v9 + 2));
          }
        }
        *(_WORD *)(v429 + 20) &= 0xF241u;
        *(_WORD *)(v429 + 20) |= v12;
        (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)(v428 + 8) + 24LL))(
          v428,
          *(unsigned __int8 *)(v428 + 42),
          v428 + 48);
        v432 = *(_DWORD *)(v428 + 36);
        v6 = 0;
        if ( v432 )
        {
          if ( v432 > 0 )
          {
            LOBYTE(v431) = 1;
            v433 = (const char *)sqlite3ValueText(v429, v431);
            sqlite3VdbeError(v7, "%s", v433);
            v15 = *(_DWORD *)(v428 + 36);
            v798 = v15;
          }
          sqlite3VdbeDeleteAuxData(v5, v7 + 37, *(unsigned int *)(v428 + 32), *((unsigned int *)v9 + 1));
          v6 = 0;
          *(_DWORD *)(v428 + 36) = 0;
          goto LABEL_688;
        }
LABEL_41:
        v12 = 1;
LABEL_42:
        LOBYTE(a4) = v796;
        goto LABEL_43;
      }
      v434 = 56LL * *((int *)v9 + 1);
      v435 = filterHash(v10, v9);
      v12 = 1;
      v436 = v435 % (8 * *(_DWORD *)(v434 + v10 + 16));
      v437 = *(char *)((v436 >> 3) + *(_QWORD *)(v434 + v10 + 8));
      v438 = _bittest(&v437, v436 & 7);
      v8 = v799;
      if ( !v438 )
      {
        ++*((_DWORD *)v7 + 61);
        v6 = 0;
        goto LABEL_70;
      }
      ++*((_DWORD *)v7 + 60);
LABEL_719:
      a2 = v797;
      v6 = 0;
      LOBYTE(a4) = v796;
      goto LABEL_51;
    }
    v353 = 56LL * *((int *)v9 + 1);
    v354 = 3LL * *(_QWORD *)(v353 + v10);
    *(_QWORD *)(v353 + v10) = (int)(-1431655765 * ((__int64)&v9[-v7[17]] >> 3) - v12);
    v352 = 3LL * (*(_DWORD *)(v8 + 8 * v354 + 8) - (int)v12);
LABEL_626:
    v9 = (unsigned __int8 *)(v8 + 8 * v352);
    goto LABEL_628;
  }
  if ( (unsigned int)v16 <= 0x50 )
  {
    if ( (_DWORD)v16 != 80 )
    {
      if ( (unsigned int)v16 > 0x4A )
      {
        v109 = v16 - 75;
        if ( v109 )
        {
          v110 = v109 - 1;
          if ( !v110 )
          {
            v453 = 56LL * *((int *)v9 + 1);
            *(_WORD *)(v453 + v10 + 20) &= 0xFFC1u;
            *(_WORD *)(v453 + v10 + 20) |= v12;
            goto LABEL_51;
          }
          v111 = v110 - 1;
          if ( v111 )
          {
            v112 = v111 - 1;
            if ( v112 )
            {
              if ( v112 == 1 )
              {
                v445 = *((_DWORD *)v9 + 3);
                v446 = v800 + 56LL * *((int *)v9 + 1);
                v447 = v800 + 56LL * *((int *)v9 + 2);
                do
                {
                  sqlite3VdbeMemRelease(v447);
                  v6 = 0;
                  v12 = 1;
                  *(_OWORD *)v447 = *(_OWORD *)v446;
                  *(_OWORD *)(v447 + 16) = *(_OWORD *)(v446 + 16);
                  v4 = *(_OWORD *)(v446 + 32);
                  *(_OWORD *)(v447 + 32) = v4;
                  *(_QWORD *)(v447 + 48) = *(_QWORD *)(v446 + 48);
                  *(_WORD *)(v446 + 20) = 1;
                  *(_DWORD *)(v446 + 32) = 0;
                  if ( (*(_WORD *)(v447 + 20) & 0x4000) != 0 )
                  {
                    v448 = sqlite3VdbeMemMakeWriteable(v447);
                    v6 = 0;
                    if ( v448 )
                      goto LABEL_1455;
                    v12 = 1;
                  }
                  v446 += 56;
                  v447 += 56;
                  --v445;
                }
                while ( v445 );
                goto LABEL_118;
              }
              goto LABEL_51;
            }
            v113 = v7[16] + 56LL * *((int *)v9 + 1);
            v114 = sqlite3VdbeMemTooBig(v113 - 56);
            v6 = 0;
            if ( v114 )
              goto LABEL_1443;
            v115 = v10 + 56LL * *((int *)v9 + 2);
            if ( (*(_WORD *)(v115 + 20) & 0x9000) != 0 )
            {
              sqlite3VdbeMemSetNull(v10 + 56LL * *((int *)v9 + 2));
              v6 = 0;
            }
            v4 = *(_OWORD *)(v113 - 56);
            *(_OWORD *)v115 = v4;
            *(_QWORD *)(v115 + 16) = *(_QWORD *)(v113 - 40);
            *(_WORD *)(v115 + 20) = *(_WORD *)(v115 + 20) & 0x8FBF | 0x2040;
            goto LABEL_49;
          }
          v449 = out2Prerelease(v7, v9);
          v450 = *((_QWORD *)v9 + 2);
          v451 = v449;
          if ( v450 )
          {
            sqlite3VdbeMemSetStr(v449, v450, *((int *)v9 + 1), 0, 0);
            v6 = 0;
          }
          else
          {
            sqlite3VdbeMemSetZeroBlob(v449, *((unsigned int *)v9 + 1));
            v452 = sqlite3VdbeMemExpandBlob(v451);
            v6 = 0;
            if ( v452 )
              goto LABEL_1455;
          }
          LOBYTE(a4) = v796;
          *(_BYTE *)(v451 + 22) = v796;
LABEL_50:
          v8 = v799;
          v12 = 1;
          a2 = v797;
          goto LABEL_51;
        }
      }
      else if ( (_DWORD)v16 != 74 )
      {
        v65 = v16 - 69;
        if ( v65 )
        {
          v66 = v65 - 1;
          if ( v66 )
          {
            v67 = v66 - 1;
            if ( !v67 )
            {
              v68 = (__int64 *)out2Prerelease(v7, v9);
              v69 = *((int *)v9 + 1);
LABEL_133:
              *v68 = v69;
              goto LABEL_48;
            }
            v439 = v67 - 1;
            if ( v439 )
            {
              if ( v439 != 1 )
                goto LABEL_51;
LABEL_1115:
              v583 = out2Prerelease(v7, v9);
              LOBYTE(a4) = v796;
              v6 = 0;
              *(_WORD *)(v583 + 20) = 8706;
              v12 = 1;
              *(_QWORD *)(v583 + 8) = *((_QWORD *)v9 + 2);
              *(_DWORD *)(v583 + 16) = *((_DWORD *)v9 + 1);
              *(_BYTE *)(v583 + 22) = v796;
              if ( *((int *)v9 + 3) <= 0 )
                goto LABEL_43;
              a2 = v797;
              if ( *(_QWORD *)(56LL * *((int *)v9 + 3) + v10) == *((unsigned __int16 *)v9 + 1) )
                *(_WORD *)(v583 + 20) = 8720;
              goto LABEL_44;
            }
            v440 = out2Prerelease(v7, v9);
            goto LABEL_818;
          }
        }
        else if ( ((unsigned __int8)v12 & *(_BYTE *)(56LL * *((int *)v9 + 3) + v10 + 20)) == 0 )
        {
          goto LABEL_51;
        }
        v121 = v7[33];
        if ( !v121 || *((_DWORD *)v9 + 1) )
        {
          v122 = *((_DWORD *)v9 + 1);
          *((_DWORD *)v7 + 13) = v122;
          *((_BYTE *)v7 + 196) = v9[8];
          if ( v122 )
          {
            if ( *((_WORD *)v9 + 1) )
            {
              sqlite3VdbeError(v7, "%s constraint failed", off_1800B28F0[*((unsigned __int16 *)v9 + 1)]);
              if ( *((_QWORD *)v9 + 2) )
                v7[21] = sqlite3MPrintf(v5, "%z: %s", v7[21]);
            }
            else
            {
              sqlite3VdbeError(v7, "%s", *((const char **)v9 + 2));
            }
            sqlite3_log(
              *((unsigned int *)v9 + 1),
              "abort at %d in [%s]: %s",
              -1431655765 * ((__int64)&v9[-v799] >> 3),
              (const char *)v7[31],
              (const char *)v7[21]);
          }
          v123 = sqlite3VdbeHalt(v7);
          v8 = v801;
          v15 = v123;
          if ( v123 == 5 )
            *((_DWORD *)v7 + 13) = 5;
          else
            v15 = *((_DWORD *)v7 + 13) != 0 ? 1 : 101;
          goto LABEL_222;
        }
        v442 = *(_QWORD *)(v121 + 8);
        --*((_DWORD *)v7 + 70);
        v7[33] = v442;
        v443 = v7[7];
        *(_QWORD *)(v5 + 128) += v443;
        *(_QWORD *)(v5 + 120) = v443;
        v444 = sqlite3VdbeFrameRestore();
        v12 = 1;
        if ( *((_DWORD *)v9 + 2) == 4 )
          v444 = *(_DWORD *)(v7[17] + 24LL * v444 + 8) - 1;
        v8 = v7[17];
        v10 = v7[13];
        v799 = v8;
        v800 = v10;
        v9 = (unsigned __int8 *)(v8 + 24LL * v444);
        goto LABEL_719;
      }
      v213 = out2Prerelease(v7, v9);
      v12 = 1;
      v214 = *((_DWORD *)v9 + 3) - *((_DWORD *)v9 + 2);
      v215 = v213;
      v6 = 0;
      v216 = *((_DWORD *)v9 + 1) != 0 ? 0x100 : 0;
      *(_DWORD *)(v213 + 16) = 0;
      v217 = v216 + 1;
      *(_WORD *)(v213 + 20) = v217;
      if ( v214 > 0 )
      {
        do
        {
          v215 += 56;
          sqlite3VdbeMemSetNull(v215);
          v6 = 0;
          *(_WORD *)(v215 + 20) = v217;
          *(_DWORD *)(v215 + 16) = 0;
          v12 = 1;
          --v214;
        }
        while ( v214 > 0 );
        goto LABEL_118;
      }
LABEL_323:
      v10 = v800;
      goto LABEL_42;
    }
    v241 = *((_DWORD *)v9 + 3);
    v242 = v800 + 56LL * *((int *)v9 + 1);
    for ( jj = v800 + 56LL * *((int *)v9 + 2); ; jj += 56 )
    {
      sqlite3VdbeMemShallowCopy(jj, v242, 0x4000);
      if ( (*(_WORD *)(jj + 20) & 0x4000) != 0 )
      {
        v249 = sqlite3VdbeMemMakeWriteable(jj);
        v6 = 0;
        if ( v249 )
          goto LABEL_1455;
      }
      else
      {
        v6 = 0;
      }
      v244 = *(_WORD *)(jj + 20);
      if ( (v244 & 0x800) != 0 && (v9[2] & 2) != 0 )
        *(_WORD *)(jj + 20) = v244 & 0xF7FF;
      if ( !v241 )
        break;
      --v241;
      v242 += 56;
    }
LABEL_412:
    v10 = v800;
    goto LABEL_41;
  }
  if ( (unsigned int)v16 > 0x56 )
  {
    v456 = v16 - 87;
    if ( !v456 )
    {
      v471 = *((int *)v9 + 1);
      v472 = v10 + 56 * v471;
      if ( (*(_BYTE *)(v472 + 20) & 0x24) == 0 )
        goto LABEL_51;
      *(double *)v472 = sqlite3VdbeRealValue(v10 + 56 * v471);
      *(_WORD *)(v472 + 20) &= 0xF248u;
      *(_WORD *)(v472 + 20) |= 8u;
      goto LABEL_48;
    }
    v457 = v456 - 1;
    if ( v457 )
    {
      v458 = v457 - 2;
      if ( !v458 )
      {
        if ( ((unsigned __int8)v12 & v9[2]) != 0 )
          v459 = *((_QWORD *)v9 - 1) + 4LL;
        else
          v459 = 0;
        v460 = *((_QWORD *)v9 + 2);
        v461 = 0;
        v462 = *((_DWORD *)v9 + 3);
        a4 = *((unsigned int *)v9 + 1);
        v463 = *((_DWORD *)v9 + 2);
        v808 = v460;
        LODWORD(v803) = v462;
        LODWORD(v805) = a4;
        LODWORD(v804) = v463;
        while ( 1 )
        {
          if ( v461 >= v462 )
          {
            v15 = v798;
            v7 = a1;
            v5 = v801;
            v10 = v800;
            LOBYTE(a4) = v796;
            goto LABEL_44;
          }
          v464 = v459 ? *(_DWORD *)(v459 + 4LL * v461) : v461;
          v465 = v800 + 56LL * (unsigned int)(v464 + v463);
          v466 = (unsigned __int8)(v12 & *(_BYTE *)(v461 + *(_QWORD *)(v460 + 24)));
          v467 = v800 + 56LL * (unsigned int)(v464 + a4);
          v468 = sqlite3MemCompare(v467, v465, *(_QWORD *)(v460 + 8LL * v461 + 32));
          v6 = 0;
          v797 = v468;
          a2 = v468;
          v12 = 1;
          if ( v468 )
            break;
          v460 = v808;
          ++v461;
          v462 = v803;
          a4 = (unsigned int)v805;
          v463 = v804;
        }
        if ( (*(_BYTE *)(v461 + *(_QWORD *)(v808 + 24)) & 2) != 0
          && ((*(_BYTE *)(v467 + 20) & 1) != 0 || (*(_BYTE *)(v465 + 20) & 1) != 0) )
        {
          a2 = -v468;
          v797 = -v468;
        }
        v15 = v798;
        v79 = v466 == 0;
        v7 = a1;
        v5 = v801;
        v10 = v800;
        LOBYTE(a4) = v796;
        if ( !v79 )
        {
          a2 = (unsigned int)-(int)a2;
          v797 = a2;
        }
        goto LABEL_44;
      }
      if ( v458 != 1 )
        goto LABEL_51;
      sqlite3VdbeBooleanValue(v10 + 56LL * *((int *)v9 + 1), *((unsigned int *)v9 + 3));
      v34 = v10 + 56LL * *((int *)v9 + 2);
LABEL_112:
      sqlite3VdbeMemSetInt64(v34);
      goto LABEL_48;
    }
    v469 = v10 + 56LL * *((int *)v9 + 1);
    if ( (*(_WORD *)(v469 + 20) & 0x400) != 0 )
    {
      v470 = sqlite3VdbeMemExpandBlob(v10 + 56LL * *((int *)v9 + 1));
      v6 = 0;
      v15 = v470;
      if ( v470 )
        goto LABEL_1459;
    }
    LOBYTE(v8) = v796;
    LOBYTE(a2) = v9[8];
    v225 = sqlite3VdbeMemCast(v469, a2, v8);
    goto LABEL_572;
  }
  if ( (_DWORD)v16 == 86 )
  {
    v454 = v10 + 56LL * *((int *)v9 + 1);
    v455 = sqlite3VdbeIntValue(v454);
    *(_QWORD *)v454 = v455;
    *(_WORD *)(v454 + 20) &= 0xF244u;
    *(_WORD *)(v454 + 20) |= 4u;
    *(_QWORD *)v454 = v455 + *((int *)v9 + 2);
    goto LABEL_48;
  }
  v131 = v16 - 81;
  if ( !v131 )
  {
    v211 = v10 + 56LL * *((int *)v9 + 1);
    v212 = v10 + 56LL * *((int *)v9 + 2);
LABEL_348:
    sqlite3VdbeMemShallowCopy(v212, v211, 0x4000);
    goto LABEL_48;
  }
  v132 = v131 - 1;
  if ( !v132 )
  {
    v34 = v10 + 56LL * *((int *)v9 + 2);
    goto LABEL_112;
  }
  v133 = v132 - 1;
  if ( !v133 )
  {
    v225 = sqlite3VdbeCheckFk(v7, 0);
    goto LABEL_572;
  }
  v134 = v133 - 1;
  if ( v134 )
  {
    if ( v134 != 1 || !*((_DWORD *)v9 + 1) )
      goto LABEL_51;
    v62 = *((int *)v9 + 1);
    goto LABEL_111;
  }
  *((_DWORD *)v7 + 11) = v12 | (*((_DWORD *)v7 + 11) + 2);
  v7[20] = v10 + 56LL * *((int *)v9 + 1);
  if ( *(_BYTE *)(v5 + 103) )
    goto LABEL_1455;
  if ( (*(_BYTE *)(v5 + 110) & 4) != 0 )
  {
    (*(void (__fastcall **)(__int64, _QWORD, __int64 *, _QWORD))(v5 + 248))(4, *(_QWORD *)(v5 + 256), v7, 0);
    v8 = v799;
    LODWORD(v12) = 1;
  }
  v135 = (__int64)&v9[-v8];
  v15 = 100;
  v8 = v801;
  *((_DWORD *)v7 + 12) = v12 - 1431655765 * (v135 >> 3);
LABEL_222:
  while ( 1 )
  {
    v124 = v816;
    if ( v17 < v816 )
      break;
    v793 = *(__int64 (__fastcall **)(__int64))(v8 + 528);
    if ( !v793 )
      break;
    v794 = *(_QWORD *)(v8 + 536);
    v816 += *(unsigned int *)(v8 + 544);
    v795 = v793(v794);
    v8 = v801;
    v6 = 0;
    if ( v795 )
    {
LABEL_1448:
      v816 = -1;
LABEL_1449:
      v15 = 9;
LABEL_1459:
      if ( *(_BYTE *)(v801 + 103) == (_BYTE)v6 )
      {
        if ( v15 == 8458 )
        {
          v15 = sqlite3ReportError(11, 102467, "database corruption");
          v6 = 0;
        }
      }
      else
      {
        v15 = 7;
      }
      if ( v7[21] == v6 && v15 != 3082 )
      {
        v792 = (const char *)sqlite3ErrStr(v15, a2, v8);
        sqlite3VdbeError(v7, "%s", v792);
      }
      *((_DWORD *)v7 + 13) = v15;
      sqlite3SystemError(v801, v15);
      sqlite3_log(
        v15,
        "statement aborts at %d: [%s] %s",
        -1431655765 * ((__int64)&v9[-v799] >> 3),
        (const char *)v7[31],
        (const char *)v7[21]);
      if ( *((_BYTE *)v7 + 199) == 2 )
        sqlite3VdbeHalt(v7);
      if ( v15 == 3082 )
      {
        sqlite3OomFault(v801);
        goto LABEL_1470;
      }
      if ( v15 == 11 )
      {
        v8 = v801;
        if ( !*(_BYTE *)(v801 + 101) )
          *(_QWORD *)(v801 + 48) |= 0x200000000uLL;
      }
      else
      {
LABEL_1470:
        v8 = v801;
      }
      v15 = 1;
      if ( v807 )
      {
        sqlite3ResetOneSchema(v8);
        v8 = v801;
      }
LABEL_358:
      v17 = v809;
      continue;
    }
  }
  *((_DWORD *)v7 + 57) += v17;
  if ( *((_DWORD *)v7 + 52) )
    sqlite3VdbeLeave(v7, v124, v8);
  return v15;
}

```

## disassembly

```asm
0x1800286a4  mov     rax, rsp
0x1800286a7  push    rbp
0x1800286a8  push    rbx
0x1800286a9  push    rsi
0x1800286aa  push    rdi
0x1800286ab  push    r12
0x1800286ad  push    r13
0x1800286af  push    r14
0x1800286b1  push    r15
0x1800286b3  lea     rbp, [rax-188h]
0x1800286ba  sub     rsp, 248h
0x1800286c1  movaps  xmmword ptr [rax-58h], xmm6
0x1800286c5  movaps  xmmword ptr [rax-68h], xmm7
0x1800286c9  movaps  xmmword ptr [rax-78h], xmm8
0x1800286ce  mov     rax, cs:__security_cookie
0x1800286d5  xor     rax, rsp
0x1800286d8  mov     [rbp+180h+var_80], rax
0x1800286df  mov     r15, [rcx]
0x1800286e2  xor     r10d, r10d
0x1800286e5  mov     r13, rcx
0x1800286e8  mov     r8, [rcx+88h]
0x1800286ef  mov     rdi, r8
0x1800286f2  mov     r14, [rcx+68h]
0x1800286f6  mov     esi, r10d
0x1800286f9  mov     qword ptr [rsp+280h+var_218], rcx
0x1800286fe  mov     r9b, [r15+64h]
0x180028702  mov     byte ptr [rsp+280h+var_240], r9b
0x180028707  mov     [rsp+280h+var_230], r8
0x18002870c  mov     [rsp+280h+var_220], r15
0x180028711  mov     [rbp+180h+var_1F4], r10b
0x180028715  mov     [rbp+180h+var_1E8], r10
0x180028719  mov     [rsp+280h+var_228], r14
0x18002871e  cmp     [rcx+0D0h], r10d
0x180028725  jnz     loc_18002A42E
0x18002872b  cmp     [r15+210h], r10
0x180028732  jnz     loc_18002A2D4
0x180028738  mov     [rbp+180h+var_1A0], 0FFFFFFFFFFFFFFFFh
0x180028740  cmp     dword ptr [r13+34h], 7
0x180028745  mov     r11d, 1
0x18002874b  jz      loc_18002EB0B
0x180028751  mov     [r13+34h], r10d
0x180028755  mov     [r13+48h], r10
0x180028759  mov     eax, [r15+198h]
0x180028760  mov     [r15+298h], r10d
0x180028767  test    eax, eax
0x180028769  jnz     loc_18002EAD0
0x18002876f  movsxd  rax, dword ptr [r13+30h]
0x180028773  mov     edx, r10d
0x180028776  mov     r12d, r10d
0x180028779  mov     dword ptr [rsp+280h+var_238], r10d
0x18002877e  mov     [rsp+280h+var_23C], edx
0x180028782  xorps   xmm8, xmm8
0x180028786  mov     [rbp+180h+var_1B0], r10d
0x18002878a  lea     rcx, [rax+rax*2]
0x18002878e  lea     rdi, [r8+rcx*8]
0x180028792  lea     ecx, [r11+3]
0x180028796  movzx   ebx, byte ptr [rdi]
0x180028799  add     rsi, r11
0x18002879c  mov     [rbp+180h+var_1F0], rdi
0x1800287a0  mov     eax, 5
0x1800287a5  mov     [rbp+180h+var_1E8], rsi
0x1800287a9  cmp     ebx, 5Ch ; '\'
0x1800287ac  jz      loc_180028978
0x1800287b2  ja      loc_1800289C4
0x1800287b8  cmp     ebx, 2Dh ; '-'
0x1800287bb  jbe     loc_180028894
0x1800287c1  cmp     ebx, 44h ; 'D'
0x1800287c4  ja      loc_180028DD0
0x1800287ca  jz      loc_18002AEC7
0x1800287d0  cmp     ebx, 39h ; '9'
0x1800287d3  ja      loc_180028FC9
0x1800287d9  jnz     loc_1800292D1
0x1800287df  movsxd  rax, dword ptr [rdi+4]
0x1800287e3  imul    r13, rax, 38h ; '8'
0x1800287e7  movsxd  rax, dword ptr [rdi+0Ch]
0x1800287eb  imul    r15, rax, 38h ; '8'
0x1800287ef  add     r13, r14
0x1800287f2  add     r15, r14
0x1800287f5  movzx   r14d, word ptr [r13+14h]
0x1800287fa  movzx   esi, word ptr [r15+14h]
0x1800287ff  movzx   edx, si
0x180028802  and     dx, r14w
0x180028806  test    dl, 4
0x180028809  jnz     loc_180028E20
0x18002880f  movzx   ecx, si
0x180028812  or      cx, r14w
0x180028816  test    r11b, cl
0x180028819  jnz     loc_18002B903
0x18002881f  mov     al, [rdi+2]
0x180028822  and     al, 47h
0x180028824  cmp     al, 43h ; 'C'
0x180028826  jnb     loc_18002B943
0x18002882c  cmp     al, 42h ; 'B'
0x18002882e  jz      loc_180028D96
0x180028834  mov     r8, [rdi+10h]
0x180028838  mov     rdx, r13
0x18002883b  mov     rcx, r15
0x18002883e  call    sqlite3MemCompare
0x180028843  mov     r8, [rsp+280h+var_230]
0x180028848  xor     r10d, r10d
0x18002884b  mov     [rsp+280h+var_23C], eax
0x18002884f  mov     edx, eax
0x180028851  lea     r11d, [r10+1]
0x180028855  test    eax, eax
0x180028857  jns     loc_180029FC3
0x18002885d  movzx   eax, byte ptr [rdi]
0x180028860  lea     rcx, __ImageBase
0x180028867  mov     cl, [rax+rcx+0B4F9Ch]
0x18002886e  mov     [r15+14h], si
0x180028873  mov     [r13+14h], r14w
0x180028878  test    cl, cl
0x18002887a  jnz     loc_180028A90
0x180028880  mov     r13, qword ptr [rsp+280h+var_218]
0x180028885  mov     r15, [rsp+280h+var_220]
0x18002888a  mov     r14, [rsp+280h+var_228]
0x18002888f  jmp     loc_180028AB8
0x180028894  jz      loc_1800296E0
0x18002889a  cmp     ebx, 16h
0x18002889d  jbe     loc_180028C91
0x1800288a3  cmp     ebx, 22h ; '"'
0x1800288a6  jbe     loc_1800294B8
0x1800288ac  cmp     ebx, 28h ; '('
0x1800288af  ja      loc_18002B43B
0x1800288b5  jz      loc_1800296E0
0x1800288bb  sub     ebx, 23h ; '#'
0x1800288be  jz      loc_18002B3CE
0x1800288c4  sub     ebx, 1
0x1800288c7  jz      loc_18002B3D5
0x1800288cd  sub     ebx, 1
0x1800288d0  jz      loc_18002B397
0x1800288d6  sub     ebx, 1
0x1800288d9  jz      loc_18002B37A
0x1800288df  cmp     ebx, 1
0x1800288e2  jnz     loc_1800289B7
0x1800288e8  movsxd  rcx, dword ptr [rdi+4]
0x1800288ec  mov     rax, [r13+78h]
0x1800288f0  mov     edx, [rdi+0Ch]
0x1800288f3  mov     rbx, [rax+rcx*8]
0x1800288f7  mov     rcx, [rbx+30h]
0x1800288fb  call    sqlite3BtreeNext
0x180028900  mov     r12d, eax
0x180028903  mov     dword ptr [rsp+280h+var_238], eax
0x180028907  xor     r10d, r10d
0x18002890a  mov     [rbx+20h], r10d
0x18002890e  test    eax, eax
0x180028910  jnz     loc_18002B3B3
0x180028916  mov     [rbx+2], r10b
0x18002891a  lea     r11d, [r12+1]
0x18002891f  movzx   eax, word ptr [rdi+2]
0x180028923  add     [r13+rax*4+0D4h], r11d
0x18002892b  mov     r8, [rsp+280h+var_230]
0x180028930  mov     eax, [rdi+8]
0x180028933  sub     eax, r11d
0x180028936  cdqe
0x180028938  lea     rcx, [rax+rax*2]
0x18002893c  lea     rdi, [r8+rcx*8]
0x180028940  mov     eax, [r15+198h]
0x180028947  test    eax, eax
0x180028949  jnz     loc_18002EAD0
0x18002894f  mov     rsi, [rbp+180h+var_1A0]
0x180028953  cmp     [rbp+180h+var_1E8], rsi
0x180028957  jnb     loc_18002DFE5
0x18002895d  mov     r11d, 1
0x180028963  mov     r9b, byte ptr [rsp+280h+var_240]
0x180028968  mov     edx, [rsp+280h+var_23C]
0x18002896c  mov     ecx, 4
0x180028971  mov     r8, [rsp+280h+var_230]
0x180028976  jmp     short loc_1800289B7
0x180028978  movsxd  rax, dword ptr [rdi+4]
0x18002897c  imul    rcx, rax, 38h ; '8'
0x180028980  test    [rcx+r14+14h], r11b
0x180028985  jz      loc_180028CDD
0x18002898b  movsxd  rax, dword ptr [rdi+8]
0x18002898f  imul    rcx, rax, 38h ; '8'
0x180028993  add     rcx, r14
0x180028996  call    sqlite3VdbeMemSetNull
0x18002899b  xor     r10d, r10d
0x18002899e  mov     r9b, byte ptr [rsp+280h+var_240]
0x1800289a3  mov     r8, [rsp+280h+var_230]
0x1800289a8  mov     r11d, 1
0x1800289ae  mov     edx, [rsp+280h+var_23C]
0x1800289b2  mov     ecx, 4
0x1800289b7  mov     rsi, [rbp+180h+var_1E8]
0x1800289bb  add     rdi, 18h
0x1800289bf  jmp     loc_180028796
0x1800289c4  mov     eax, 8Ch
0x1800289c9  cmp     ebx, eax
0x1800289cb  ja      loc_180028EF9
0x1800289d1  jz      loc_18002A384
0x1800289d7  cmp     ebx, 74h ; 't'
0x1800289da  ja      loc_180029C77
0x1800289e0  jz      loc_18002CE2D
0x1800289e6  cmp     ebx, 69h ; 'i'
0x1800289e9  ja      loc_180029045
0x1800289ef  jz      loc_18002C674
0x1800289f5  cmp     ebx, 63h ; 'c'
0x1800289f8  ja      loc_18002C651
0x1800289fe  jz      loc_18002C619
0x180028a04  sub     ebx, 5Eh ; '^'
0x180028a07  jnz     loc_180029146
0x180028a0d  xorps   xmm0, xmm0
0x180028a10  mov     [rbp+180h+var_1F8], r10d
0x180028a14  movups  [rbp+180h+var_158], xmm0
0x180028a18  xor     eax, eax
0x180028a1a  mov     [rbp+180h+var_128], rax
0x180028a1e  mov     rax, [r13+78h]
0x180028a22  movups  [rbp+180h+var_148], xmm0
0x180028a26  movups  [rbp+180h+var_138], xmm0
0x180028a2a  movsxd  rcx, dword ptr [rdi+4]
0x180028a2e  mov     r14d, [rdi+8]
0x180028a32  mov     rbx, [rax+rcx*8]
0x180028a36  mov     dword ptr [rbp+180h+var_200], r14d
0x180028a3a  mov     rax, qword ptr [rsp+280h+var_218]
0x180028a3f  mov     r13, [rbx+58h]
0x180028a43  mov     [rbp+180h+var_198], r13
0x180028a47  mov     eax, [rax+2Ch]
0x180028a4a  cmp     [rbx+20h], eax
0x180028a4d  jnz     short loc_180028AC2
0x180028a4f  mov     rcx, [rbx+30h]
0x180028a53  call    sqlite3BtreeEof
0x180028a58  xor     r10d, r10d
0x180028a5b  test    eax, eax
0x180028a5d  jnz     loc_180028AE6
0x180028a63  lea     rsi, [rbx+4Ah]
0x180028a67  movzx   eax, word ptr [rsi]
0x180028a6a  cmp     eax, r14d
0x180028a6d  jbe     loc_180028E66
0x180028a73  mov     eax, r14d
0x180028a76  mov     edx, [rbx+rax*4+78h]
0x180028a7a  mov     [rbp+180h+var_1F8], edx
0x180028a7d  jmp     loc_180028C2A
0x180028a82  sub     rax, 1
0x180028a86  mov     [rcx+r14], rax
0x180028a8a  jnz     loc_1800289B2
0x180028a90  mov     r8, [rsp+280h+var_230]
0x180028a95  mov     eax, [rdi+8]
0x180028a98  sub     eax, r11d
0x180028a9b  cdqe
0x180028a9d  lea     rcx, [rax+rax*2]
0x180028aa1  lea     rdi, [r8+rcx*8]
0x180028aa5  mov     r13, qword ptr [rsp+280h+var_218]
0x180028aaa  mov     r15, [rsp+280h+var_220]
0x180028aaf  mov     r14, [rsp+280h+var_228]
0x180028ab4  mov     edx, [rsp+280h+var_23C]
0x180028ab8  mov     r9b, byte ptr [rsp+280h+var_240]
0x180028abd  jmp     loc_1800289B2
0x180028ac2  cmp     [rbx+2], r10b
0x180028ac6  jnz     loc_18002C489
0x180028acc  mov     rsi, [rbx+30h]
0x180028ad0  cmp     [rbx+3], r10b
0x180028ad4  jnz     loc_18002C449
0x180028ada  mov     rcx, rsi
0x180028add  call    sqlite3BtreeEof
0x180028ae2  test    eax, eax
0x180028ae4  jz      short loc_180028B05
0x180028ae6  mov     rcx, rbx
0x180028ae9  call    sqlite3VdbeHandleMovedCursor
0x180028aee  xor     r10d, r10d
0x180028af1  mov     dword ptr [rsp+280h+var_238], eax
0x180028af5  mov     r12d, eax
0x180028af8  test    eax, eax
0x180028afa  jz      loc_180028A3A
0x180028b00  jmp     loc_18002EB39
0x180028b05  mov     rcx, rsi
0x180028b08  call    getCellInfo
0x180028b0d  mov     eax, [rsi+40h]
0x180028b10  lea     r15, [rbx+6Ch]
0x180028b14  mov     rdx, r15
0x180028b17  mov     [rbx+68h], eax
0x180028b1a  mov     rcx, rsi
0x180028b1d  call    fetchPayload
0x180028b22  mov     rcx, rax
0x180028b25  xor     r10d, r10d
0x180028b28  mov     rax, qword ptr [rsp+280h+var_218]
0x180028b2d  lea     r14, [rbx+40h]
0x180028b31  mov     [rbx+60h], rcx
0x180028b35  mov     eax, [rax+2Ch]
0x180028b38  mov     [rbx+20h], eax
0x180028b3b  movzx   eax, byte ptr [rcx]
0x180028b3e  mov     [r13+0], eax
0x180028b42  cmp     eax, 80h
0x180028b47  jnb     loc_18002C4B9
0x180028b4d  mov     r11d, 1
0x180028b53  mov     eax, r11d
0x180028b56  mov     rcx, r14
0x180028b59  lea     rsi, [rbx+4Ah]
0x180028b5d  mov     [rcx], eax
0x180028b5f  mov     [rsi], r10w
0x180028b63  mov     eax, [r13+0]
0x180028b67  cmp     [r15], eax
0x180028b6a  jb      loc_18002C4D4
0x180028b70  mov     rcx, [rbx+60h]
0x180028b74  mov     [rsp+280h+var_208], rcx
0x180028b79  movzx   r12d, word ptr [rsi]
0x180028b7d  mov     r11d, 1
0x180028b83  mov     esi, [r14]
0x180028b86  mov     r14d, [r13+0]
0x180028b8a  add     rsi, rcx
0x180028b8d  mov     edi, dword ptr [rbp+180h+var_200]
0x180028b90  add     r14, rcx
  ... truncated ...
```
