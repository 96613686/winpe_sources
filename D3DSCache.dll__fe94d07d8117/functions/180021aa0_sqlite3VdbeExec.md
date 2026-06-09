# sqlite3VdbeExec

- ea: `0x180021aa0`
- end: `0x180027dbc`
- name: `sqlite3VdbeExec`
- size: `25372`
- prototype: ``
- caller_count: `2`
- callee_count: `154`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003e84c`
- `0x180055f3c`

## callees

- `0x18000594c`
- `0x180007a00`
- `0x18000b544`
- `0x180010de0`
- `0x1800115a0`
- `0x180011a14`
- `0x180012470`
- `0x180016b18`
- `0x180021aa0`
- `0x1800283fc`
- `0x1800286a0`
- `0x1800290c0`
- `0x18002b81c`
- `0x18002b8ec`
- `0x18002c520`
- `0x18002e290`
- `0x1800327d0`
- `0x1800333e0`
- `0x1800334f0`
- `0x180033ba0`
- `0x18003549c`
- `0x180035e80`
- `0x180037320`
- `0x180037454`
- `0x1800374f8`
- `0x1800379c8`
- `0x1800381a0`
- `0x180038a04`
- `0x180038c94`
- `0x180039198`
- `0x18003964c`
- `0x1800399c0`
- `0x18003a57c`
- `0x18003a860`
- `0x18003af40`
- `0x18003b5b4`
- `0x18003c8d4`
- `0x18003d068`
- `0x18003f71c`
- `0x1800418e4`
- `0x180042160`
- `0x180042184`
- `0x1800421a0`
- `0x180042468`
- `0x180042bb0`
- `0x180042dc4`
- `0x1800449f0`
- `0x180045374`
- `0x180053b48`
- `0x180053bcc`

## string_xrefs

- `0x180027475`: `cannot open savepoint - SQL statements in progress`
- `0x180027753`: `cannot commit transaction - SQL statements in progress`
- `0x1800277f4`: `cannot rollback - no transaction is active`
- `0x1800277fb`: `cannot commit - no transaction is active`

## pseudocode

```c
__int64 __fastcall sqlite3VdbeExec(__int64 *a1)
{
  __int128 v1; // xmm0
  __int64 *v2; // r12
  unsigned __int8 *v3; // rsi
  unsigned __int8 *i; // rdi
  __int64 v5; // r13
  __int64 v6; // r14
  unsigned __int64 v7; // rdx
  unsigned __int8 v8; // r11
  unsigned __int64 v9; // r9
  int v10; // eax
  __int64 IsValidNN; // rax
  unsigned int updated; // r15d
  __int64 v13; // r8
  __int64 v14; // rbx
  __int64 v15; // kr00_8
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 *v25; // rcx
  _QWORD *v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rbx
  __int64 v29; // rdx
  __int64 v30; // r8
  int v31; // eax
  __int64 v32; // r9
  __int64 v33; // r8
  __int64 v34; // rax
  __int64 v35; // r8
  __int64 v36; // rdx
  bool v37; // zf
  __int16 v38; // si
  int v39; // ebx
  __int64 v40; // r14
  __int64 v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rbx
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // rsi
  __int64 v48; // rbx
  int v49; // r14d
  __int64 v50; // rsi
  __int64 v51; // rbx
  int v52; // r14d
  __int64 v53; // rsi
  __int64 v54; // rbx
  unsigned __int64 v55; // rsi
  char v56; // r14
  __int64 v57; // r13
  __int16 v58; // r12
  __int64 v59; // rbx
  __int64 v60; // r14
  __int16 v61; // si
  unsigned __int64 v62; // r15
  __int64 v63; // rsi
  __int64 v64; // r15
  __int64 v65; // r14
  __int16 v66; // r8
  __int64 v67; // r15
  __int16 v68; // dx
  unsigned __int8 v69; // bl
  __int64 v70; // rdx
  __int64 v71; // r8
  int v72; // ecx
  int v73; // ecx
  int v74; // ecx
  int v75; // ecx
  __int128 v76; // rax
  double v77; // xmm7_8
  __int64 v78; // rdx
  __int64 v79; // r8
  __int64 v80; // rdx
  __int64 v81; // r8
  __int128 v82; // xmm6
  __int64 v83; // rbx
  __int64 v84; // rdx
  __int64 v85; // r8
  __int64 v86; // rax
  double v87; // xmm6_8
  __int64 v88; // rsi
  __int64 v89; // rdx
  __int64 v90; // r14
  __int64 v91; // rcx
  __int64 v92; // rbx
  __int64 v93; // rdx
  __int64 v94; // r8
  __int64 v95; // rax
  char v96; // cl
  __int64 v97; // rdx
  __int64 v98; // rbx
  __int64 v99; // rbx
  __int64 v100; // rbx
  double v101; // xmm0_8
  __int64 v102; // rbx
  __int64 v103; // r12
  __int64 v104; // r15
  __int16 v105; // r14
  __int16 v106; // si
  bool v107; // cc
  char v108; // cl
  char v109; // cl
  unsigned __int8 v110; // al
  int v111; // eax
  __int64 v112; // rbx
  int v113; // edx
  int v114; // r12d
  int v115; // ecx
  int v116; // r13d
  __int64 v117; // rsi
  int v118; // r8d
  __int64 v119; // r9
  __int64 v120; // rcx
  __int64 v121; // r8
  __int64 v122; // r15
  int v123; // ebx
  __int64 v124; // r8
  int v125; // ebx
  __int64 *v126; // rax
  __int64 v127; // r8
  __int64 v128; // rdx
  __int16 v129; // cx
  __int16 v130; // cx
  int v131; // eax
  __int64 v132; // r8
  __int64 v133; // rax
  __int64 v134; // r8
  __int64 v135; // rbx
  int v136; // eax
  __int64 v137; // r8
  __int64 v138; // rcx
  __int64 v139; // rsi
  __int64 v140; // rbx
  __int64 v141; // rdx
  __int64 v142; // r8
  __int64 v143; // r8
  __int64 v144; // r9
  unsigned __int64 v145; // rcx
  unsigned int v146; // edx
  int v147; // eax
  int v148; // eax
  __int64 v149; // rax
  __int64 v150; // rdx
  __int64 v151; // rcx
  __int64 v152; // rcx
  int v153; // ecx
  __int64 v154; // rdx
  __int64 v155; // rax
  unsigned int v156; // r14d
  __int64 v157; // rbx
  unsigned int *v158; // r13
  int v159; // eax
  __int64 v160; // rsi
  __int64 v161; // rdx
  int v162; // eax
  __int64 v163; // rdx
  __int64 v164; // r8
  unsigned int *v165; // r15
  __int64 Payload; // rax
  __int64 v167; // r8
  unsigned __int8 *v168; // rcx
  __int64 v169; // rax
  __int64 v170; // rcx
  int v171; // eax
  int *v172; // r14
  unsigned int v173; // eax
  int v174; // eax
  unsigned __int16 *v175; // rsi
  __int64 v176; // r15
  __int64 v177; // rcx
  unsigned __int8 *v178; // rsi
  unsigned __int64 v179; // r14
  unsigned __int64 v180; // r12
  __int64 v181; // r13
  __int64 v182; // rax
  __int64 v183; // rdx
  int v184; // eax
  __int64 v185; // rsi
  const void *v186; // r14
  size_t v187; // rbx
  __int64 v188; // rdx
  __int64 v189; // rdx
  char v190; // al
  __int64 v191; // rsi
  __int64 v192; // r14
  __int64 v193; // rbx
  int v194; // r15d
  __int16 v195; // ax
  __int16 v196; // cx
  __int16 v197; // cx
  _BYTE *v198; // rsi
  __int64 n; // rbx
  __int16 v200; // cx
  __int16 v201; // cx
  __int64 v202; // r15
  _BYTE *v203; // rbx
  int v204; // esi
  __int64 v205; // r12
  __int64 v206; // r13
  __int64 v207; // r9
  int v208; // eax
  int *v209; // r9
  int *v210; // rax
  __int64 *v211; // r14
  __int16 v212; // ax
  int *v213; // rbx
  __int64 v214; // rdx
  __int16 v215; // cx
  unsigned __int64 v216; // rdx
  int v217; // edx
  __int64 v218; // rax
  __int64 v219; // rcx
  unsigned int v220; // r15d
  unsigned int v221; // r14d
  __int64 v222; // rax
  int v223; // eax
  __int64 v224; // r14
  int v225; // esi
  int v226; // eax
  int v227; // ebx
  __int64 v228; // rdx
  __int64 v229; // r8
  __int64 v230; // r9
  int v231; // eax
  __int64 v232; // rbx
  _BYTE *v233; // rbx
  _BYTE *v234; // r14
  _BYTE *v235; // rsi
  int v236; // eax
  int *v237; // rbx
  unsigned __int64 v238; // rcx
  __int64 v239; // rdx
  unsigned __int64 v240; // rcx
  unsigned __int64 v241; // rcx
  int v242; // eax
  __int64 v243; // rcx
  __int64 v244; // rax
  __int64 v245; // rcx
  __int64 v246; // r8
  __int64 *v247; // rax
  unsigned int v248; // r12d
  const void *v249; // r14
  __int64 v250; // rsi
  _QWORD *v251; // rbx
  __int64 v252; // rax
  _QWORD *v253; // r15
  unsigned int v254; // esi
  int v255; // r13d
  __int64 v256; // r14
  __int64 v257; // rcx
  unsigned int v258; // eax
  int v259; // r14d
  int v260; // ebx
  int j; // esi
  int v262; // esi
  unsigned int v263; // r14d
  _QWORD *k; // rcx
  __int64 v265; // rdx
  __int64 v266; // r14
  __int64 v267; // rsi
  __int64 v268; // rbx
  int v269; // r8d
  __int64 v270; // rcx
  __int64 v271; // rdx
  __int64 v272; // rax
  __int64 v273; // r8
  __int64 v274; // rsi
  __int64 v275; // rbx
  __int64 v276; // r8
  __int64 v277; // rsi
  __int64 v278; // rbx
  __int64 v279; // rbx
  __int64 v280; // rax
  int v281; // ecx
  __int64 v282; // rax
  __int64 v283; // rdx
  __int64 v284; // rcx
  __int64 v285; // rcx
  __int64 v286; // rax
  __int64 v287; // r13
  BOOL v288; // r12d
  __int64 v289; // rsi
  __int16 v290; // r14
  __int64 v291; // rax
  __int64 v292; // r8
  __int16 v293; // cx
  __int64 v294; // r15
  int v295; // eax
  unsigned int v296; // eax
  __int64 v297; // r8
  int HasHint; // eax
  int v299; // esi
  char v300; // cl
  __int64 v301; // rax
  unsigned int v302; // eax
  __int64 v303; // rcx
  __int64 v304; // rax
  __int64 v305; // rbx
  int v306; // esi
  __int64 v307; // rax
  __int64 v308; // r8
  bool v309; // sf
  __int64 v310; // rcx
  unsigned int v311; // eax
  int v312; // r8d
  __int64 v313; // rdx
  int v314; // ecx
  __int64 v315; // rdx
  __int64 v316; // rcx
  __int64 v317; // rax
  __int64 v318; // rbx
  __int64 v319; // rcx
  int *v320; // r14
  __int64 v321; // rax
  __int64 v322; // rsi
  int v323; // ecx
  int m; // edx
  __int64 v325; // rcx
  __int128 v326; // xmm1
  __int64 v327; // rsi
  __int64 v328; // rbx
  __int64 v329; // rcx
  unsigned int v330; // eax
  __int64 v331; // rdx
  __int64 v332; // rax
  __int64 v333; // r8
  __int64 v334; // rdx
  _QWORD *v335; // r14
  __int64 v336; // rsi
  __int64 v337; // rbx
  __int64 v338; // rax
  __int64 v339; // rax
  __int64 v340; // rcx
  __int64 v341; // rbx
  __int64 v342; // rax
  __int64 v343; // rcx
  __int64 v344; // rax
  int v345; // ebx
  __int64 v346; // rcx
  __int64 v347; // r11
  __int64 v348; // r10
  __int64 v349; // rax
  __int64 v350; // r14
  __int64 v351; // rdx
  _QWORD *v352; // rbx
  __int64 v353; // rsi
  __int16 v354; // r8
  __int64 v355; // r9
  __int64 v356; // rdx
  __int64 v357; // rax
  __int64 v358; // r8
  int v359; // r12d
  __int64 v360; // rsi
  __int64 v361; // r14
  __int64 v362; // r15
  __int64 v363; // rbx
  __int64 v364; // rcx
  __int64 v365; // r8
  __int64 v366; // rdx
  __int64 v367; // rax
  __int64 v368; // rsi
  __int64 v369; // rdx
  __int64 v370; // rbx
  __int64 v371; // r8
  __int64 v372; // rdx
  __int64 v373; // r8
  __int64 v374; // rdx
  __int64 v375; // rsi
  __int64 v376; // rcx
  __int64 v377; // rbx
  __int64 *v378; // rcx
  __int64 v379; // rbx
  __int64 v380; // rdx
  __int64 v381; // r8
  __int64 v382; // rbx
  __int64 v383; // rdx
  __int64 v384; // rbx
  __int64 v385; // rcx
  __int64 v386; // rax
  __int64 v387; // rsi
  __int64 v388; // r14
  __int64 v389; // rcx
  __int64 v390; // rcx
  __int64 v391; // rax
  __int64 v392; // rbx
  __int64 v393; // rcx
  __int64 v394; // rax
  __int64 v395; // rcx
  __int64 v396; // rax
  __int64 v397; // rbx
  unsigned int v398; // eax
  __int64 v399; // rbx
  unsigned int v400; // eax
  __int64 v401; // rax
  __int64 v402; // rcx
  __int64 v403; // rsi
  __int64 v404; // rbx
  __int16 v405; // r8
  __int64 v406; // rcx
  __int64 v407; // r9
  __int64 v408; // rsi
  __int64 v409; // rbx
  __int64 v410; // rcx
  __int64 v411; // rax
  _QWORD *v412; // rbx
  __int64 v413; // rsi
  __int64 v414; // rax
  __int64 v415; // rdx
  __int64 v416; // rcx
  __int64 v417; // rax
  __int64 v418; // rbx
  __int64 v419; // r8
  __int64 v420; // rdx
  __int64 v421; // rcx
  __int64 v422; // rcx
  __int64 v423; // rax
  __int64 v424; // rdx
  __int64 v425; // rcx
  __int64 v426; // rbx
  __int64 v427; // rdx
  int v428; // ebx
  int v429; // ecx
  int v430; // ebx
  __int64 v431; // rbx
  unsigned int v432; // esi
  __int64 v433; // rcx
  __int64 v434; // rdx
  __int64 v435; // rcx
  __int64 v436; // rdx
  __int64 v437; // rax
  __int64 v438; // rdx
  __int64 v439; // rcx
  __int64 v440; // rax
  __int64 v441; // rcx
  _QWORD *v442; // rbx
  __int64 v443; // r8
  __int64 v444; // r9
  __int64 v445; // rbx
  char v446; // si
  int v447; // r14d
  const char *v448; // r8
  __int64 v449; // r9
  __int64 v450; // rbx
  __int64 v451; // r8
  __int64 v452; // rax
  __int64 v453; // rbx
  __int64 v454; // rdx
  __int64 v455; // r8
  __int64 v456; // rsi
  __int64 v457; // rbx
  __int64 v458; // r8
  __int64 v459; // r9
  __int64 v460; // rbx
  __int64 v461; // rax
  __int64 v462; // rsi
  __int64 v463; // rbx
  __int64 v464; // rax
  __int64 v465; // rbx
  __int64 v466; // r8
  int v467; // esi
  __int64 v468; // rbx
  __int64 v469; // r14
  __int64 v470; // r13
  __int64 v471; // r14
  bool v472; // sf
  unsigned __int8 **v473; // r15
  __int64 v474; // rsi
  int v475; // edx
  int v476; // r14d
  int v477; // r12d
  __int64 v478; // rbx
  __int64 v479; // rdx
  __int64 v480; // rcx
  __int64 v481; // rax
  __int64 v482; // rcx
  void *v483; // rcx
  int v484; // eax
  __int64 v485; // rax
  __int64 v486; // rcx
  __int64 v487; // rsi
  __int64 v488; // rbx
  __int64 v489; // rdx
  __int64 v490; // r8
  __int64 v491; // rcx
  __int64 v492; // r14
  __int64 v493; // rbx
  __int64 *v494; // rsi
  __int64 v495; // rdx
  __int64 v496; // rcx
  __int64 v497; // rcx
  __int64 v498; // rsi
  __int64 v499; // rax
  _DWORD *v500; // rbx
  __int64 v501; // rdx
  __int64 v502; // r8
  _DWORD *v503; // r8
  __int64 v504; // rax
  __int64 v505; // rdx
  __int64 v506; // rdx
  __int64 v507; // r8
  const char *v508; // rax
  __int64 v509; // rax
  __int64 v510; // rax
  __int64 v511; // rbx
  __int64 v512; // rdx
  __int64 v513; // r8
  int v514; // r8d
  int v515; // edx
  unsigned int v516; // eax
  __int64 v517; // r8
  int v518; // edx
  __int64 v519; // rbx
  __int64 v520; // r8
  __int64 v521; // r8
  __int64 v522; // r15
  __int64 v523; // r13
  __int64 v524; // r14
  unsigned int v525; // esi
  unsigned int v526; // ebx
  __int64 v527; // rax
  __int64 v528; // rdx
  __int64 v529; // r8
  unsigned int v530; // eax
  unsigned int v531; // eax
  __int64 v532; // rax
  __int64 v533; // rdx
  __int64 v534; // r8
  __int64 v535; // r8
  __int64 v536; // rax
  __int64 v537; // r9
  __int64 v538; // rbx
  __int64 v539; // rax
  unsigned int v540; // eax
  __int64 v541; // rdx
  __int64 v542; // rax
  __int64 v543; // rax
  __int64 *v544; // rbx
  __int64 v545; // rsi
  __int64 v546; // r9
  __int64 v547; // rax
  __int64 v548; // rsi
  _QWORD *v549; // rbx
  __int64 v550; // rcx
  __int64 *v551; // r10
  __int64 v552; // rax
  __int64 v553; // r9
  __int64 v554; // rsi
  _QWORD *v555; // rax
  __int64 v556; // r8
  _QWORD *v557; // rbx
  __int64 v558; // rax
  int v559; // r13d
  __int64 v560; // r11
  __int64 v561; // rdx
  int *v562; // r10
  __int64 v563; // r15
  int v564; // r9d
  __int64 **v565; // rbx
  __int64 v566; // rdx
  __int64 *v567; // r14
  __int64 v568; // rsi
  __int64 v569; // rax
  __int64 v570; // rsi
  __int64 v571; // rax
  __int64 v572; // rbx
  __int64 *v573; // r14
  __int64 v574; // r15
  __int16 v575; // ax
  __int64 v576; // rdx
  __int64 v577; // r8
  const char *v578; // rax
  __int64 v579; // rsi
  __int64 **v580; // rcx
  __int64 *v581; // rbx
  __int64 v582; // r14
  int v583; // r14d
  __int64 v584; // rbx
  __int64 v585; // rsi
  __int64 *v586; // rbx
  __int64 v587; // r10
  __int64 v588; // r9
  __int64 v589; // rdx
  char v590; // si
  __int64 v591; // r8
  __int64 v592; // rcx
  _QWORD *v593; // rbx
  unsigned int v594; // r8d
  __int64 v595; // r9
  __int64 v596; // rdx
  __int64 v597; // rbx
  __int64 v598; // rsi
  __int64 v599; // rdx
  __int64 v600; // rdx
  const char *v601; // rax
  __int64 v602; // rdx
  __int64 v603; // rdx
  __int64 v604; // rcx
  __int64 v605; // rbx
  unsigned __int64 v606; // rax
  __int64 v607; // rcx
  unsigned __int64 v608; // rdx
  unsigned __int64 v609; // r8
  __int64 v610; // rbx
  unsigned __int64 v611; // rax
  int v612; // r8d
  unsigned __int8 v613; // cf
  char v614; // al
  const char *v615; // r9
  __int64 v616; // rbx
  __int64 v617; // rbx
  int v618; // ecx
  __int64 v619; // rax
  __int64 v620; // rax
  __int64 v621; // rdx
  __int64 v622; // rbx
  __int64 v623; // rdx
  __int64 v624; // rcx
  __int64 v625; // rax
  __int64 v626; // rbx
  __int64 v627; // r15
  __int64 v628; // rax
  int v629; // ecx
  int v630; // r14d
  __int64 v631; // rcx
  __int64 v632; // r15
  __int64 v633; // rax
  __int64 v634; // r13
  int v635; // r12d
  unsigned __int8 v636; // cl
  __int64 *v637; // rax
  __int64 v638; // rbx
  unsigned __int8 v639; // cl
  __int64 v640; // rbx
  __int64 v641; // r8
  __int64 Cursor; // rax
  __int64 v643; // rcx
  unsigned int v644; // eax
  int v645; // ecx
  unsigned int v646; // eax
  const char *v647; // rdx
  const char *v648; // rax
  const char *v649; // r8
  int v650; // ebx
  int v651; // ecx
  char v652; // al
  const char *v653; // rdx
  __int64 v654; // rax
  const char *v655; // rax
  __int64 (__fastcall *v656)(_QWORD); // rax
  int v657; // eax
  __int64 v659; // [rsp+28h] [rbp-E0h]
  __int16 v660; // [rsp+48h] [rbp-C0h]
  unsigned int v661; // [rsp+4Ch] [rbp-BCh]
  unsigned int Table; // [rsp+50h] [rbp-B8h]
  unsigned int v663; // [rsp+50h] [rbp-B8h]
  unsigned __int64 v664; // [rsp+58h] [rbp-B0h]
  unsigned __int64 v665; // [rsp+60h] [rbp-A8h]
  unsigned __int8 *v666; // [rsp+68h] [rbp-A0h]
  __int64 v668; // [rsp+78h] [rbp-90h] BYREF
  int *v669; // [rsp+80h] [rbp-88h] BYREF
  __int64 v670; // [rsp+88h] [rbp-80h]
  unsigned int v671; // [rsp+90h] [rbp-78h] BYREF
  __int64 *v672; // [rsp+98h] [rbp-70h] BYREF
  __int64 v673; // [rsp+A0h] [rbp-68h]
  __int128 v674; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v675; // [rsp+B8h] [rbp-50h]
  __int128 v676; // [rsp+C8h] [rbp-40h]
  int v677; // [rsp+D8h] [rbp-30h]
  unsigned int v678; // [rsp+DCh] [rbp-2Ch] BYREF
  __int64 v679; // [rsp+E0h] [rbp-28h] BYREF
  unsigned int *v680; // [rsp+E8h] [rbp-20h]
  _OWORD v681[2]; // [rsp+F0h] [rbp-18h] BYREF
  __int128 v682; // [rsp+110h] [rbp+8h]
  __int64 v683; // [rsp+120h] [rbp+18h]
  __int128 v684; // [rsp+128h] [rbp+20h] BYREF
  __int128 v685; // [rsp+138h] [rbp+30h]
  __int128 v686; // [rsp+148h] [rbp+40h]
  __int64 v687; // [rsp+158h] [rbp+50h]
  _OWORD v688[2]; // [rsp+160h] [rbp+58h] BYREF
  __int128 v689; // [rsp+180h] [rbp+78h]
  __int64 v690; // [rsp+190h] [rbp+88h]
  char v691; // [rsp+198h] [rbp+90h] BYREF
  __int16 v692; // [rsp+199h] [rbp+91h]
  char v693; // [rsp+19Bh] [rbp+93h]
  int v694; // [rsp+19Ch] [rbp+94h]
  int v695; // [rsp+1E8h] [rbp+E0h]
  __int64 v696; // [rsp+1ECh] [rbp+E4h] BYREF

  v2 = a1;
  v3 = (unsigned __int8 *)a1[17];
  i = v3;
  v5 = *a1;
  v6 = a1[13];
  v7 = 0;
  v8 = *(_BYTE *)(*a1 + 100);
  v660 = v8;
  v666 = v3;
  v670 = *a1;
  v664 = 0;
  v673 = v6;
  if ( *((_DWORD *)a1 + 52) )
  {
    sqlite3VdbeEnter(a1, 0);
    v7 = 0;
    v8 = v660;
  }
  if ( *(_QWORD *)(v5 + 528) )
  {
    v7 = 0;
    v9 = (unsigned int)(*(_DWORD *)(v5 + 544) - *((_DWORD *)v2 + 57) % *(_DWORD *)(v5 + 544));
  }
  else
  {
    v9 = -1;
  }
  v665 = v9;
  if ( *((_DWORD *)v2 + 13) == 7 )
    goto LABEL_90;
  *((_DWORD *)v2 + 13) = 0;
  v2[9] = 0;
  v10 = *(_DWORD *)(v5 + 408);
  *(_DWORD *)(v5 + 664) = 0;
  if ( v10 )
    goto LABEL_1235;
  IsValidNN = *((int *)v2 + 12);
  updated = 0;
  Table = 0;
  v13 = 0;
  v661 = 0;
  v677 = 0;
  for ( i = &v3[24 * IsValidNN]; ; i += 24 )
  {
    v14 = *i;
    v664 = ++v7;
    if ( (_DWORD)v14 == 113 )
    {
LABEL_1145:
      if ( (v2[25] & 3) == 1 )
      {
        updated = 516;
        goto LABEL_309;
      }
      v630 = *((_DWORD *)i + 3);
      v631 = *(_QWORD *)(v5 + 32);
      v632 = *((unsigned int *)i + 2);
      v633 = 32LL * v630;
      v634 = *(_QWORD *)(v633 + v631 + 8);
      if ( (_BYTE)v14 == 113 )
      {
        v635 = *((_WORD *)i + 1) & 8 | 4;
        v636 = *(_BYTE *)(*(_QWORD *)(v633 + v631 + 24) + 112LL);
        v637 = a1;
        if ( v636 < *((_BYTE *)a1 + 197) )
          *((_BYTE *)a1 + 197) = v636;
      }
      else
      {
        v637 = a1;
        v635 = 0;
      }
      if ( (i[2] & 0x10) != 0 )
      {
        v638 = v673 + 56 * v632;
        v632 = sqlite3VdbeIntValue(v638, v7, v13);
        *(_QWORD *)v638 = v632;
        *(_WORD *)(v638 + 20) &= 0xF244u;
        *(_WORD *)(v638 + 20) |= 4u;
        v637 = a1;
      }
      v639 = i[1];
      if ( v639 == 0xF8 )
      {
        v640 = *((_QWORD *)i + 2);
        v641 = *(unsigned __int16 *)(v640 + 8);
      }
      else
      {
        v641 = 0;
        v640 = 0;
        if ( v639 == 0xFD )
          v641 = *((unsigned int *)i + 4);
      }
      Cursor = allocateCursor(v637, *((unsigned int *)i + 1), v641, 0);
      v277 = Cursor;
      if ( !Cursor )
        goto LABEL_88;
      v643 = *(_QWORD *)(Cursor + 48);
      *(_DWORD *)(Cursor + 8) |= 4u;
      *(_BYTE *)(Cursor + 1) = v630;
      *(_BYTE *)(Cursor + 2) = 1;
      *(_DWORD *)(Cursor + 68) = v632;
      v644 = sqlite3BtreeCursor(v634, v632, v635, v640, v643);
      v2 = a1;
      updated = v644;
      v5 = v670;
      *(_QWORD *)(v277 + 56) = v640;
      Table = v644;
      *(_BYTE *)(v277 + 4) = i[1] != 0xF8;
LABEL_1158:
      IsValidNN = *(_QWORD *)(v277 + 48);
      *(_BYTE *)(IsValidNN + 3) = i[2] & 3;
LABEL_576:
      if ( updated )
        goto LABEL_309;
LABEL_48:
      v7 = v664;
LABEL_49:
      v13 = v661;
LABEL_50:
      v3 = v666;
      v8 = v660;
      goto LABEL_108;
    }
    if ( (_DWORD)v14 != 118 )
      break;
LABEL_1125:
    v620 = *((int *)i + 3);
    if ( (int)v620 > 0 )
    {
      *(_DWORD *)(56 * v620 + v6 + 16) = 0;
      *(_QWORD *)(56LL * *((int *)i + 3) + v6 + 8) = &Src;
    }
    v621 = *((int *)i + 1);
    v622 = *(_QWORD *)(v2[15] + 8 * v621);
    if ( !v622 || (*(_BYTE *)(v622 + 8) & 8) != 0 || *((_DWORD *)i + 2) > *(__int16 *)(v622 + 72) )
    {
      v625 = allocateCursor(v2, v621, *((unsigned int *)i + 2), 0);
      v626 = v625;
      if ( !v625 )
        goto LABEL_90;
      *(_DWORD *)(v625 + 8) |= 1u;
      LODWORD(v659) = *((unsigned __int16 *)i + 1) | 5;
      updated = sqlite3BtreeOpen(*(_QWORD *)v5, 0, v5, v625 + 16, v659, 1054);
      if ( updated )
        goto LABEL_309;
      Table = sqlite3BtreeBeginTrans(*(_QWORD *)(v626 + 16), 1, 0);
      updated = Table;
      if ( !Table )
      {
        v627 = *((_QWORD *)i + 2);
        *(_QWORD *)(v626 + 56) = v627;
        if ( v627 )
        {
          Table = sqlite3BtreeCreateTable(*(_QWORD *)(v626 + 16), v626 + 68, *((unsigned __int16 *)i + 1) | 2u);
          if ( Table )
          {
            updated = Table;
          }
          else
          {
            updated = sqlite3BtreeCursor(
                        *(_QWORD *)(v626 + 16),
                        *(_DWORD *)(v626 + 68),
                        4,
                        v627,
                        *(_QWORD *)(v626 + 48));
            Table = updated;
          }
          *(_BYTE *)(v626 + 4) = 0;
        }
        else
        {
          v628 = *(_QWORD *)(v626 + 48);
          *(_DWORD *)(v626 + 68) = 1;
          updated = sqlite3BtreeCursor(*(_QWORD *)(v626 + 16), 1, 4, 0, v628);
          Table = updated;
          *(_BYTE *)(v626 + 4) = 1;
        }
      }
      v629 = 0;
      if ( *((_WORD *)i + 1) != 8 )
        v629 = 4;
      IsValidNN = *(_DWORD *)(v626 + 8) & 0xFFFFFFFB;
      *(_DWORD *)(v626 + 8) = IsValidNN | v629;
      if ( updated )
      {
        sqlite3BtreeClose(*(_QWORD *)(v626 + 16));
        goto LABEL_309;
      }
      v3 = v666;
      *(_BYTE *)(v626 + 2) = 1;
    }
    else
    {
      v623 = *(unsigned int *)(v622 + 68);
      v624 = *(_QWORD *)(v622 + 16);
      *(_QWORD *)(v622 + 24) = 0;
      *(_DWORD *)(v622 + 32) = 0;
      IsValidNN = sqlite3BtreeClearTable(v624, v623, 0);
      Table = IsValidNN;
      updated = IsValidNN;
      if ( (_DWORD)IsValidNN )
        goto LABEL_309;
      *(_BYTE *)(v622 + 2) = 1;
    }
LABEL_27:
    v7 = v664;
LABEL_28:
    v13 = v661;
    v8 = v660;
LABEL_108:
    v5 = v670;
    v6 = v673;
    v9 = v665;
  }
  if ( (_DWORD)v14 != 84 )
  {
    v15 = IsValidNN;
    IsValidNN = (__int64)&_ImageBase;
    switch ( *i )
    {
      case 0u:
        v248 = *((_DWORD *)i + 1);
        v249 = (const void *)*((_QWORD *)i + 2);
        if ( !v248 )
        {
          if ( *(int *)(v5 + 224) > 0 )
          {
            v647 = "cannot open savepoint - SQL statements in progress";
            goto LABEL_1177;
          }
          v250 = (int)sqlite3Strlen30(*((_QWORD *)i + 2), v7, v13);
          Table = sqlite3VtabSavepoint(v5, 0, (unsigned int)(*(_DWORD *)(v5 + 752) + *(_DWORD *)(v5 + 756)));
          updated = Table;
          if ( Table )
            goto LABEL_545;
          IsValidNN = sqlite3DbMallocRawNN(v5, v250 + 33);
          v251 = (_QWORD *)IsValidNN;
          if ( IsValidNN )
          {
            *(_QWORD *)IsValidNN = IsValidNN + 32;
            memcpy_0((void *)(IsValidNN + 32), v249, (int)v250 + 1);
            if ( *(_BYTE *)(v5 + 101) == (_BYTE)Table )
            {
              ++*(_DWORD *)(v5 + 752);
            }
            else
            {
              *(_BYTE *)(v5 + 101) = Table;
              *(_BYTE *)(v5 + 109) = 1;
            }
            v251[3] = *(_QWORD *)(v5 + 736);
            v252 = *(_QWORD *)(v5 + 760);
            *(_QWORD *)(v5 + 736) = v251;
            v251[1] = v252;
            IsValidNN = *(_QWORD *)(v5 + 768);
            v251[2] = IsValidNN;
          }
          goto LABEL_547;
        }
        v253 = *(_QWORD **)(v5 + 736);
        v254 = 0;
        LODWORD(v669) = 0;
        if ( !v253 )
        {
LABEL_1182:
          v2 = a1;
          sqlite3VdbeError(a1, "no such savepoint: %s", (const char *)v249);
          updated = 1;
          goto LABEL_309;
        }
        while ( (unsigned int)sqlite3StrICmp(*v253, v249) )
        {
          v253 = (_QWORD *)v253[3];
          if ( !v253 )
            goto LABEL_1182;
          LODWORD(v669) = ++v254;
        }
        if ( *(int *)(v5 + 224) > 0 && v248 == 1 )
        {
          v647 = "cannot release savepoint - SQL statements in progress";
LABEL_1177:
          v2 = a1;
          sqlite3VdbeError(a1, v647, v13);
LABEL_1178:
          updated = 5;
          goto LABEL_309;
        }
        if ( v253[3] || !*(_BYTE *)(v5 + 109) )
        {
          v255 = 0;
LABEL_522:
          v257 = v670;
          v258 = Table;
          v259 = *(_DWORD *)(v670 + 752);
          if ( v248 == 2 )
          {
            v260 = *(_DWORD *)(v670 + 44) & 1;
            for ( j = 0; j < *(_DWORD *)(v257 + 40); ++j )
            {
              v258 = sqlite3BtreeTripAllCursors(*(_QWORD *)(32LL * j + *(_QWORD *)(v257 + 32) + 8), 516, v260 ^ 1u);
              Table = v258;
              if ( v258 )
                goto LABEL_1237;
              v257 = v670;
            }
            v254 = (unsigned int)v669;
          }
          else
          {
            v260 = 0;
          }
          LODWORD(v669) = v259 + ~v254;
          v262 = 0;
          v263 = (unsigned int)v669;
          while ( v262 < *(_DWORD *)(v257 + 40) )
          {
            v258 = sqlite3BtreeSavepoint(*(_QWORD *)(32LL * v262 + *(_QWORD *)(v257 + 32) + 8), v248, v263);
            Table = v258;
            if ( v258 )
              goto LABEL_1237;
            v257 = v670;
            ++v262;
          }
          v256 = v670;
          if ( v260 )
          {
            sqlite3ExpirePreparedStatements(v670, 0, v13);
            sqlite3ResetAllSchemasOfConnection(v256);
            *(_DWORD *)(v256 + 44) |= 1u;
            v258 = Table;
          }
          if ( v258 )
          {
LABEL_1237:
            v2 = a1;
LABEL_1238:
            updated = Table;
            goto LABEL_308;
          }
          v254 = (unsigned int)v669;
          goto LABEL_537;
        }
        v255 = 1;
        if ( v248 != 1 )
          goto LABEL_522;
        v663 = sqlite3VdbeCheckFk(a1, 1, v13);
        if ( v663 )
        {
          updated = v663;
          v5 = v670;
LABEL_1255:
          v2 = a1;
LABEL_1256:
          v56 = HIBYTE(v660);
          v55 = v665;
          goto LABEL_1257;
        }
        v256 = v670;
        *(_BYTE *)(v670 + 101) = 1;
        if ( (unsigned int)sqlite3VdbeHalt(a1) == 5 )
        {
          updated = 5;
          v5 = v256;
          *((_DWORD *)a1 + 12) = -1431655765 * ((i - v666) >> 3);
          *(_BYTE *)(v256 + 101) = 0;
          *((_DWORD *)a1 + 13) = 5;
          goto LABEL_1255;
        }
        Table = *((_DWORD *)a1 + 13);
        if ( Table )
        {
          updated = *((_DWORD *)a1 + 13);
          v5 = v256;
          *(_BYTE *)(v256 + 101) = 0;
          v2 = a1;
          goto LABEL_309;
        }
        *(_BYTE *)(v256 + 109) = 0;
LABEL_537:
        for ( k = *(_QWORD **)(v256 + 736); k != v253; k = *(_QWORD **)(v256 + 736) )
        {
          *(_QWORD *)(v256 + 736) = k[3];
          sqlite3DbFree(v256, k);
          --*(_DWORD *)(v256 + 752);
        }
        if ( v248 == 1 )
        {
          *(_QWORD *)(v256 + 736) = v253[3];
          IsValidNN = sqlite3DbFree(v256, v253);
          v37 = v255 == 0;
          v5 = v670;
          if ( !v37 )
            goto LABEL_546;
          --*(_DWORD *)(v670 + 752);
        }
        else
        {
          v37 = v255 == 0;
          v5 = v670;
          *(_QWORD *)(v256 + 760) = v253[1];
          IsValidNN = v253[2];
          *(_QWORD *)(v256 + 768) = IsValidNN;
          if ( !v37 && v248 != 2 )
          {
LABEL_546:
            updated = Table;
            goto LABEL_547;
          }
        }
        IsValidNN = sqlite3VtabSavepoint(v5, v248, v254);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( (_DWORD)IsValidNN )
        {
LABEL_545:
          v2 = a1;
          goto LABEL_309;
        }
LABEL_547:
        v2 = a1;
        v7 = v664;
        if ( *((_BYTE *)a1 + 199) == 3 )
        {
          v55 = v665;
          updated = 101;
          v56 = HIBYTE(v660);
          goto LABEL_1258;
        }
        goto LABEL_49;
      case 1u:
        v650 = *((_DWORD *)i + 1);
        v651 = *((_DWORD *)i + 2);
        if ( v650 == *(unsigned __int8 *)(v5 + 101) )
        {
          if ( v650 )
          {
            v653 = "cannot rollback - no transaction is active";
            if ( !v651 )
              v653 = "cannot commit - no transaction is active";
          }
          else
          {
            v653 = "cannot start a transaction within a transaction";
          }
          sqlite3VdbeError(v2, v653, v13);
          updated = 1;
          goto LABEL_309;
        }
        if ( v651 )
        {
          sqlite3RollbackAll(v5, 516, v13);
          v652 = 1;
        }
        else
        {
          if ( v650 && *(int *)(v5 + 224) > 0 )
          {
            sqlite3VdbeError(v2, "cannot commit transaction - SQL statements in progress", v13);
            goto LABEL_1178;
          }
          updated = sqlite3VdbeCheckFk(v2, 1, v13);
          if ( updated )
            goto LABEL_1256;
          v652 = v650;
        }
        *(_BYTE *)(v5 + 101) = v652;
        if ( (unsigned int)sqlite3VdbeHalt(v2) == 5 )
        {
          updated = 5;
          *((_DWORD *)v2 + 12) = -1431655765 * ((i - v666) >> 3);
          *(_BYTE *)(v5 + 101) = 1 - v650;
          *((_DWORD *)v2 + 13) = 5;
        }
        else
        {
          sqlite3CloseSavepoints(v5);
          updated = 101;
          if ( *((_DWORD *)v2 + 13) )
            updated = 1;
        }
        goto LABEL_1256;
      case 2u:
        v265 = *((unsigned int *)i + 2);
        LODWORD(v669) = 0;
        if ( (_DWORD)v265 )
        {
          IsValidNN = *(_QWORD *)(v5 + 48);
          if ( (IsValidNN & 0x200100000LL) != 0 )
          {
            updated = 8;
            if ( (IsValidNN & 0x100000) == 0 )
              updated = 11;
            goto LABEL_309;
          }
        }
        v266 = *(_QWORD *)(v5 + 32);
        v267 = 32LL * *((int *)i + 1);
        v268 = *(_QWORD *)(v267 + v266 + 8);
        if ( !v268 )
          goto LABEL_562;
        IsValidNN = sqlite3BtreeBeginTrans(*(_QWORD *)(v267 + v266 + 8), v265, &v669);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( (_DWORD)IsValidNN )
        {
          v55 = v665;
          v56 = HIBYTE(v660);
          if ( (_BYTE)IsValidNN != 5 )
            goto LABEL_311;
          *((_DWORD *)v2 + 13) = IsValidNN;
          *((_DWORD *)v2 + 12) = -1431655765 * ((i - v666) >> 3);
          goto LABEL_1257;
        }
        if ( (v2[25] & 0x20) != 0 && *((_DWORD *)i + 2) && (!*(_BYTE *)(v5 + 101) || *(int *)(v5 + 220) > 1) )
        {
          v269 = *((_DWORD *)v2 + 16);
          if ( !v269 )
          {
            v269 = ++*(_DWORD *)(v5 + 756) + *(_DWORD *)(v5 + 752);
            *((_DWORD *)v2 + 16) = v269;
          }
          Table = sqlite3VtabSavepoint(v5, 0, (unsigned int)(v269 - 1));
          updated = Table;
          if ( !Table )
          {
            updated = sqlite3BtreeBeginStmt(v268, *((unsigned int *)v2 + 16));
            Table = updated;
          }
          v13 = v661;
          v8 = v660;
          v2[11] = *(_QWORD *)(v5 + 760);
          IsValidNN = *(_QWORD *)(v5 + 768);
          v2[12] = IsValidNN;
LABEL_562:
          if ( updated )
          {
LABEL_309:
            v55 = v665;
            goto LABEL_310;
          }
        }
        else
        {
          v13 = v661;
          v8 = v660;
        }
        if ( *((_WORD *)i + 1) )
        {
          if ( (_DWORD)v669 != *((_DWORD *)i + 3)
            || (IsValidNN = *((unsigned int *)i + 4),
                *(_DWORD *)(*(_QWORD *)(v267 + v266 + 24) + 4LL) != (_DWORD)IsValidNN) )
          {
            sqlite3DbFree(v5, v2[21]);
            v2[21] = sqlite3DbStrDup(v5, "database schema has changed");
            if ( **(_DWORD **)(32LL * *((int *)i + 1) + *(_QWORD *)(v5 + 32) + 24) != (_DWORD)v669 )
              sqlite3ResetOneSchema(v5);
            updated = 17;
            *((_DWORD *)v2 + 50) = v2[25] & 0xFFFFFFEC | 1;
            goto LABEL_309;
          }
        }
        v7 = v664;
        goto LABEL_107;
      case 3u:
        v514 = *((_DWORD *)i + 2);
        v515 = *((_DWORD *)i + 1);
        v695 = 0;
        v696 = -1;
        v516 = sqlite3Checkpoint(v5, v515, v514, (unsigned int)&v696, (__int64)&v696 + 4);
        Table = v516;
        updated = v516;
        if ( v516 )
        {
          if ( v516 != 5 )
            goto LABEL_309;
          updated = 0;
          v518 = 1;
          Table = 0;
          v695 = 1;
        }
        else
        {
          v518 = v695;
        }
        v519 = v6 + 56LL * *((int *)i + 3);
        sqlite3VdbeMemSetInt64(v519, v518, v517);
        sqlite3VdbeMemSetInt64(v519 + 56, (int)v696, v520);
        IsValidNN = sqlite3VdbeMemSetInt64(v519 + 112, SHIDWORD(v696), v521);
        goto LABEL_27;
      case 4u:
        v522 = out2Prerelease(v2, i, v13);
        v523 = *(_QWORD *)(32LL * *((int *)i + 1) + *(_QWORD *)(v5 + 32) + 8);
        v524 = **(_QWORD **)(v523 + 8);
        v525 = *(unsigned __int8 *)(v524 + 9);
        v526 = v525;
        if ( *((_DWORD *)i + 3) != -1 )
          v526 = *((_DWORD *)i + 3);
        if ( !(unsigned int)sqlite3PagerOkToChangeJournalMode(v524) )
          v526 = v525;
        v527 = sqlite3PagerFilename(v524, 1);
        if ( v526 == 5
          && (!(unsigned int)sqlite3Strlen30(v527, v528, v529) || !(unsigned int)sqlite3PagerWalSupported(v524)) )
        {
          v526 = v525;
LABEL_985:
          v530 = Table;
          goto LABEL_986;
        }
        if ( v526 == v525 || v525 != 5 && v526 != 5 )
          goto LABEL_985;
        if ( !*(_BYTE *)(v670 + 101) || *(int *)(v670 + 220) > 1 )
        {
          v649 = "into";
          if ( v526 != 5 )
            v649 = "out of";
          updated = 1;
          sqlite3VdbeError(v2, "cannot change %s wal mode from within a transaction", v649);
          v5 = v670;
          goto LABEL_309;
        }
        if ( v525 == 5 )
        {
          Table = sqlite3PagerCloseWal(v524, v670);
          if ( Table )
            goto LABEL_987;
          sqlite3PagerSetJournalMode(v524, v526);
        }
        else
        {
          if ( v525 == 4 )
            sqlite3PagerSetJournalMode(v524, 2);
          if ( Table )
            goto LABEL_987;
        }
        v530 = sqlite3BtreeSetVersion(v523, (unsigned int)(v526 == 5) + 1);
        Table = v530;
LABEL_986:
        if ( !v530 )
          goto LABEL_988;
LABEL_987:
        v526 = v525;
LABEL_988:
        v531 = sqlite3PagerSetJournalMode(v524, v526);
        *(_WORD *)(v522 + 20) = 8706;
        v532 = sqlite3JournalModename(v531);
        *(_QWORD *)(v522 + 8) = v532;
        *(_DWORD *)(v522 + 16) = sqlite3Strlen30(v532, v533, v534);
        *(_BYTE *)(v522 + 22) = 1;
        IsValidNN = sqlite3VdbeChangeEncoding(v522, (unsigned __int8)v660, v535);
        updated = Table;
        if ( !Table )
          goto LABEL_48;
        goto LABEL_308;
      case 5u:
        v536 = *((int *)i + 2);
        if ( (_DWORD)v536 )
          v537 = v6 + 56 * v536;
        else
          v537 = 0;
        IsValidNN = sqlite3RunVacuum(v2 + 21, v5, *((unsigned int *)i + 1), v537);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( !(_DWORD)IsValidNN )
          goto LABEL_27;
        goto LABEL_309;
      case 6u:
        v559 = 0;
        v560 = v2[14];
        v561 = 56LL * *((int *)i + 3);
        v562 = (int *)(v561 + v6 + 56);
        v563 = *(_QWORD *)(v2[15] + 8LL * *((int *)i + 1));
        v564 = *v562;
        v565 = *(__int64 ***)(v563 + 48);
        v566 = *(unsigned int *)(v561 + v673);
        v567 = *v565;
        v568 = **v565;
        if ( *v562 > 0 )
        {
          do
          {
            v569 = (unsigned int)v559++;
            *(_QWORD *)(v560 + 8 * v569) = &v562[14 * v559];
          }
          while ( v559 < v564 );
        }
        HIDWORD(v659) = HIDWORD(v560);
        Table = (*(__int64 (__fastcall **)(__int64 **, __int64, _QWORD))(v568 + 64))(v565, v566, *((_QWORD *)i + 2));
        sqlite3VtabImportErrmsg(v2, v567);
        if ( Table )
          goto LABEL_1238;
        IsValidNN = (*(__int64 (__fastcall **)(__int64 **))(v568 + 80))(v565);
        *(_BYTE *)(v563 + 2) = 0;
        if ( (_DWORD)IsValidNN )
          goto LABEL_1047;
        goto LABEL_146;
      case 7u:
        v37 = *(_BYTE *)(v5 + 103) == 0;
        v668 = 0;
        if ( !v37 )
          goto LABEL_90;
        IsValidNN = *((_QWORD *)i + 2);
        v586 = *(__int64 **)(IsValidNN + 16);
        if ( !v586 )
          goto LABEL_1206;
        v587 = *v586;
        if ( !*v586 )
          goto LABEL_1206;
        if ( !*(_QWORD *)(v587 + 104) )
          goto LABEL_108;
        v588 = 0;
        v589 = *((unsigned int *)i + 2);
        v590 = *(_BYTE *)(v5 + 108);
        v591 = v2[14];
        v592 = v6 + 56LL * *((int *)i + 3);
        if ( (int)v589 > 0 )
        {
          do
          {
            *(_QWORD *)(v591 + 8 * v588) = v592;
            v592 += 56;
            v588 = (unsigned int)(v588 + 1);
          }
          while ( (int)v588 < (int)v589 );
        }
        *(_BYTE *)(v5 + 108) = i[2];
        Table = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64 *))(v587 + 104))(
                  v586,
                  v589,
                  v591,
                  &v668);
        *(_BYTE *)(v5 + 108) = v590;
        updated = Table;
        IsValidNN = sqlite3VtabImportErrmsg(v2, v586);
        if ( !Table )
        {
          if ( *((_DWORD *)i + 1) )
          {
            IsValidNN = v668;
            *(_QWORD *)(v5 + 56) = v668;
          }
LABEL_1079:
          ++v2[7];
          goto LABEL_576;
        }
        if ( (_BYTE)Table != 19 )
          goto LABEL_1079;
        IsValidNN = *((_QWORD *)i + 2);
        if ( !*(_BYTE *)(IsValidNN + 28) )
          goto LABEL_1079;
        IsValidNN = *((unsigned __int16 *)i + 1);
        if ( (_WORD)IsValidNN != 4 )
        {
          if ( (_WORD)IsValidNN == 5 )
            LOBYTE(IsValidNN) = 2;
          *((_BYTE *)v2 + 196) = IsValidNN;
          goto LABEL_309;
        }
        updated = 0;
        Table = 0;
        goto LABEL_48;
      case 8u:
      case 0xB8u:
        v614 = *(_BYTE *)(v5 + 110);
        if ( (v614 & 0x41) != 0 && *((_BYTE *)v2 + 197) != 0xFE )
        {
          v615 = (const char *)*((_QWORD *)i + 2);
          if ( v615 || (v615 = (const char *)v2[31]) != 0 )
          {
            if ( (v614 & 0x40) != 0 )
            {
              v616 = sqlite3VdbeExpandSql(v2, v615, v13);
              (*(void (__fastcall **)(_QWORD, __int64))(v5 + 248))(*(_QWORD *)(v5 + 256), v616);
              sqlite3_free(v616);
            }
            else if ( *(int *)(v5 + 228) <= 1 )
            {
              (*(void (__fastcall **)(__int64, _QWORD, __int64 *))(v5 + 248))(1, *(_QWORD *)(v5 + 256), v2);
            }
            else
            {
              v617 = sqlite3MPrintf(v5, "-- %s", v615);
              (*(void (__fastcall **)(__int64, _QWORD, __int64 *, __int64))(v5 + 248))(
                1,
                *(_QWORD *)(v5 + 256),
                v2,
                v617);
              sqlite3DbFree(v5, v617);
            }
            v7 = v664;
            v13 = v661;
            v8 = v660;
          }
        }
        IsValidNN = *((unsigned int *)i + 1);
        if ( (int)IsValidNN < dword_1800C6B18 )
          goto LABEL_1124;
        if ( *i == 0xB8 )
          goto LABEL_108;
        v618 = 1;
        if ( *((int *)v2 + 36) > 1 )
        {
          do
          {
            v619 = v2[17];
            if ( *(_BYTE *)(v619 + 24LL * v618) == 15 )
              *(_DWORD *)(v619 + 24LL * v618 + 4) = 0;
            ++v618;
          }
          while ( v618 < *((_DWORD *)v2 + 36) );
          v7 = v664;
        }
        LODWORD(IsValidNN) = 0;
LABEL_1124:
        *((_DWORD *)i + 1) = IsValidNN + 1;
        ++*((_DWORD *)v2 + 59);
        goto LABEL_249;
      case 9u:
        goto LABEL_1065;
      case 0xAu:
        v16 = 56LL * *((int *)i + 1);
        *(_WORD *)(v16 + v6 + 20) = 4;
        *(_QWORD *)(v16 + v6) = (int)(-1431655765 * ((i - v3) >> 3));
        goto LABEL_1065;
      case 0xBu:
        v17 = 56LL * *((int *)i + 1);
        IsValidNN = *((_DWORD *)i + 3) - 1;
        *(_QWORD *)(v17 + v6) = IsValidNN;
        *(_WORD *)(v17 + v6 + 20) = 4;
        if ( !*((_DWORD *)i + 2) )
          goto LABEL_108;
        goto LABEL_249;
      case 0xCu:
        v20 = 56LL * *((int *)i + 1);
        v21 = *(int *)(v20 + v6);
        IsValidNN = (int)(-1431655765 * ((i - v3) >> 3));
        *(_WORD *)(v20 + v6 + 20) = 4;
        *(_QWORD *)(v20 + v6) = IsValidNN;
        v7 = v664;
        i = &v3[24 * v21];
        goto LABEL_108;
      case 0xDu:
        v99 = v6 + 56LL * *((int *)i + 1);
        IsValidNN = *(unsigned __int16 *)(v99 + 20);
        if ( (IsValidNN & 4) != 0 )
          goto LABEL_181;
        LOBYTE(v7) = 67;
        applyAffinity(v6 + 56LL * *((int *)i + 1), v7, v8);
        IsValidNN = *(unsigned __int16 *)(v99 + 20);
        if ( (IsValidNN & 4) != 0 )
        {
          v7 = v664;
          v13 = v661;
          v8 = v660;
LABEL_181:
          LOWORD(IsValidNN) = IsValidNN & 0xF240 | 4;
          *(_WORD *)(v99 + 20) = IsValidNN;
          goto LABEL_108;
        }
        if ( !*((_DWORD *)i + 2) )
        {
          updated = 20;
          goto LABEL_309;
        }
        goto LABEL_177;
      case 0xEu:
        if ( (int)v13 < 0 )
        {
          IsValidNN = *((_DWORD *)i + 1) - 1;
          i = &v3[24 * (int)IsValidNN];
          goto LABEL_108;
        }
        if ( !(_DWORD)v13 )
          goto LABEL_249;
        IsValidNN = *((_DWORD *)i + 3) - 1;
        i = &v3[24 * (int)IsValidNN];
        goto LABEL_108;
      case 0xFu:
        v143 = v2[33];
        if ( v143 )
        {
          v144 = *(_QWORD *)(v143 + 40);
          v145 = (unsigned __int64)(-1431655765 * (unsigned int)((__int64)&i[-v2[17]] >> 3)) >> 3;
          v146 = (-85 * (unsigned __int8)((__int64)&i[-v2[17]] >> 3)) & 7;
          v147 = *(unsigned __int8 *)(v145 + v144);
          if ( _bittest(&v147, v146) )
            goto LABEL_178;
          v148 = v147 | (1 << v146);
          v7 = v664;
          *(_BYTE *)(v145 + v144) = v148;
        }
        else if ( *(_DWORD *)(v2[17] + 4) == *((_DWORD *)i + 1) )
        {
          goto LABEL_179;
        }
        IsValidNN = v2[17];
        v13 = v661;
        *((_DWORD *)i + 1) = *(_DWORD *)(IsValidNN + 4);
        goto LABEL_108;
      case 0x10u:
        IsValidNN = sqlite3VdbeBooleanValue(v6 + 56LL * *((int *)i + 1), *((unsigned int *)i + 3), v13);
        v7 = v664;
        v13 = v661;
        v8 = v660;
        if ( !(_DWORD)IsValidNN )
          goto LABEL_108;
        goto LABEL_249;
      case 0x11u:
        IsValidNN = sqlite3VdbeBooleanValue(v6 + 56LL * *((int *)i + 1), *((_DWORD *)i + 3) == 0, v13);
        v7 = v664;
        v13 = v661;
        v8 = v660;
        if ( (_DWORD)IsValidNN )
          goto LABEL_108;
        goto LABEL_249;
      case 0x12u:
        v149 = *((int *)i + 1);
        if ( (int)v149 < 0 )
        {
          LOBYTE(v153) = *((_BYTE *)qword_1800B9DC0 + (*(_WORD *)(56LL * *((int *)i + 3) + v6 + 20) & 0x3F));
          goto LABEL_284;
        }
        v150 = *((int *)i + 3);
        v151 = *(_QWORD *)(v2[15] + 8 * v149);
        if ( (int)v150 >= *(unsigned __int16 *)(v151 + 74) )
        {
          v153 = *((_DWORD *)i + 4);
          v7 = v664;
LABEL_284:
          IsValidNN = 1;
          LOWORD(IsValidNN) = 1 << (v153 - 1);
          goto LABEL_285;
        }
        v152 = *(unsigned int *)(v151 + 4 * v150 + 120);
        v7 = v664;
        if ( (unsigned int)v152 < 0xC )
        {
          IsValidNN = *((unsigned __int8 *)&qword_1800BA5F0[1] + v152);
        }
        else
        {
          IsValidNN = 4;
          if ( (v152 & 1) == 0 )
            LOWORD(IsValidNN) = 8;
        }
LABEL_285:
        if ( ((unsigned __int16)IsValidNN & *((_WORD *)i + 1)) != 0 )
        {
LABEL_249:
          IsValidNN = *((_DWORD *)i + 2) - 1;
          i = &v3[24 * (int)IsValidNN];
        }
        goto LABEL_108;
      case 0x13u:
        v133 = *((int *)i + 2);
        v134 = v6 + 56LL * *((int *)i + 1);
        v135 = v6 + 56 * v133;
        if ( (*(_BYTE *)(v134 + 20) & 1) != 0 )
        {
          v138 = v6 + 56 * v133;
LABEL_261:
          IsValidNN = sqlite3VdbeMemSetNull(v138);
        }
        else
        {
          v136 = sqlite3VdbeBooleanValue(v6 + 56LL * *((int *)i + 1), 0, v134);
          IsValidNN = sqlite3VdbeMemSetInt64(v135, v136 == 0, v137);
        }
        goto LABEL_27;
      case 0x14u:
        IsValidNN = v2[15];
        v154 = *(_QWORD *)(IsValidNN + 8LL * *((int *)i + 1));
        if ( !v154 || !*(_BYTE *)(v154 + 2) )
          goto LABEL_19;
        sqlite3VdbeMemSetNull(v6 + 56LL * *((int *)i + 3));
        goto LABEL_177;
      case 0x15u:
      case 0x16u:
      case 0x17u:
      case 0x18u:
        v285 = *((int *)i + 1);
        LODWORD(v669) = 0;
        *(_QWORD *)&v676 = 0;
        v1 = 0;
        v286 = v2[15];
        v674 = 0;
        v675 = 0;
        v287 = *(_QWORD *)(v286 + 8 * v285);
        *(_WORD *)(v287 + 2) = 0;
        *(_DWORD *)(v287 + 32) = 0;
        if ( *(_BYTE *)(v287 + 4) )
        {
          v288 = 0;
          v289 = v6 + 56LL * *((int *)i + 3);
          v290 = *(_WORD *)(v289 + 20);
          if ( (v290 & 0x2E) == 2 )
            applyNumericAffinity(v289, 0, v13);
          v291 = sqlite3VdbeIntValue(v289, v7, v13);
          v293 = *(_WORD *)(v289 + 20);
          v294 = v291;
          *(_WORD *)(v289 + 20) = v290;
          if ( (v293 & 0x24) == 0 )
          {
            if ( (v293 & 8) == 0 )
            {
              if ( (v293 & 1) != 0 || (unsigned int)v14 >= 0x17 )
              {
                v2 = a1;
LABEL_1047:
                updated = Table;
                goto LABEL_622;
              }
              Table = sqlite3BtreeLast(*(_QWORD *)(v287 + 48), &v669, v292);
              updated = Table;
              if ( Table )
                goto LABEL_599;
              goto LABEL_628;
            }
            v295 = sqlite3IntFloatCompare(v291);
            if ( v295 <= 0 )
            {
              if ( v295 < 0 && (v14 & 1) != 0 )
                LODWORD(v14) = v14 + 1;
            }
            else if ( (v14 & 1) == 0 )
            {
              LODWORD(v14) = v14 - 1;
            }
          }
          v296 = sqlite3BtreeTableMoveto(*(_QWORD *)(v287 + 48), v294, 0, &v669);
          *(_QWORD *)(v287 + 80) = v294;
          updated = v296;
          Table = v296;
          if ( v296 )
            goto LABEL_599;
        }
        else
        {
          HasHint = sqlite3BtreeCursorHasHint(*(_QWORD *)(v287 + 48), 2, v13);
          *(_QWORD *)&v674 = *(_QWORD *)(v287 + 56);
          WORD6(v675) = *((_WORD *)i + 8);
          v299 = HasHint;
          BYTE2(v676) = 0;
          v288 = HasHint != 0;
          v300 = 1;
          if ( (((_BYTE)v14 - 1) & 1) != 0 )
            v300 = -1;
          v301 = *((int *)i + 3);
          BYTE14(v675) = v300;
          *((_QWORD *)&v674 + 1) = v6 + 56 * v301;
          Table = sqlite3BtreeIndexMoveto(*(_QWORD *)(v287 + 48), &v674, &v669);
          updated = Table;
          if ( Table )
          {
LABEL_599:
            v2 = a1;
LABEL_308:
            v5 = v670;
            goto LABEL_309;
          }
          if ( v299 && !BYTE2(v676) )
            goto LABEL_628;
        }
        IsValidNN = (unsigned int)v669;
        if ( (int)v14 < 23 )
        {
          if ( (int)v669 <= 0 && ((_DWORD)v669 || (_DWORD)v14 != 21) )
          {
            IsValidNN = sqlite3BtreeEof(*(_QWORD *)(v287 + 48));
            goto LABEL_629;
          }
          LODWORD(v669) = 0;
          v302 = sqlite3BtreePrevious(*(_QWORD *)(v287 + 48), 0, v297);
        }
        else
        {
          if ( (int)v669 >= 0 && ((_DWORD)v669 || (_DWORD)v14 != 24) )
          {
            LODWORD(v669) = 0;
LABEL_630:
            v7 = v664;
            v13 = v661;
            v37 = !v288;
            v2 = a1;
            v3 = v666;
            v8 = v660;
            if ( !v37 )
              i += 24;
            goto LABEL_108;
          }
          LODWORD(v669) = 0;
          v302 = sqlite3BtreeNext(*(_QWORD *)(v287 + 48), 0, v297);
        }
        Table = v302;
        updated = v302;
        if ( v302 )
        {
          v2 = a1;
          if ( v302 != 101 )
            goto LABEL_308;
          Table = 0;
          LODWORD(v669) = 1;
          updated = 0;
          goto LABEL_622;
        }
LABEL_628:
        IsValidNN = (unsigned int)v669;
LABEL_629:
        if ( !(_DWORD)IsValidNN )
          goto LABEL_630;
        v2 = a1;
LABEL_622:
        v3 = v666;
LABEL_177:
        v8 = v660;
LABEL_178:
        v7 = v664;
LABEL_179:
        v13 = v661;
        goto LABEL_249;
      case 0x19u:
        IsValidNN = v2[15];
        v315 = *(_QWORD *)(IsValidNN + 8LL * *((int *)i + 1));
        if ( !v315 )
          goto LABEL_1064;
        v37 = *(_BYTE *)(v315 + 2) == 0;
        v7 = v664;
        if ( v37 )
          goto LABEL_108;
        goto LABEL_1065;
      case 0x1Au:
        IsValidNN = *(unsigned __int16 *)(*(_QWORD *)(v2[15] + 8LL * *((int *)i + 1)) + 12LL);
        if ( (int)IsValidNN >= *((_DWORD *)i + 4) )
          goto LABEL_108;
        goto LABEL_655;
      case 0x1Bu:
      case 0x1Cu:
      case 0x1Du:
LABEL_655:
        v316 = *((int *)i + 1);
        *(_QWORD *)&v676 = 0;
        v1 = 0;
        v317 = v2[15];
        v674 = 0;
        v675 = 0;
        v318 = *(_QWORD *)(v317 + 8 * v316);
        v319 = v6 + 56LL * *((int *)i + 3);
        WORD6(v675) = *((_WORD *)i + 8);
        *((_QWORD *)&v674 + 1) = v319;
        if ( WORD6(v675) )
        {
          v320 = (int *)(v318 + 36);
          *(_QWORD *)&v674 = *(_QWORD *)(v318 + 56);
          BYTE14(v675) = 0;
          updated = sqlite3BtreeIndexMoveto(*(_QWORD *)(v318 + 48), &v674, v318 + 36);
          Table = updated;
        }
        else
        {
          if ( (*(_WORD *)(v319 + 20) & 0x400) != 0 && (unsigned int)sqlite3VdbeMemExpandBlob(v319, v7, v13) )
            goto LABEL_90;
          v321 = sqlite3VdbeAllocUnpackedRecord(*(_QWORD *)(v318 + 56), v7, v13);
          v322 = v321;
          if ( !v321 )
            goto LABEL_90;
          sqlite3VdbeRecordUnpack(
            *(_QWORD *)(v318 + 56),
            *(unsigned int *)(*((_QWORD *)&v674 + 1) + 16LL),
            *(_QWORD *)(*((_QWORD *)&v674 + 1) + 8LL),
            v321);
          *(_BYTE *)(v322 + 30) = 0;
          v320 = (int *)(v318 + 36);
          Table = sqlite3BtreeIndexMoveto(*(_QWORD *)(v318 + 48), v322, v318 + 36);
          updated = Table;
          sqlite3DbFreeNN(v5, v322);
          v3 = v666;
        }
        if ( updated )
          goto LABEL_309;
        v323 = *v320;
        *(_BYTE *)(v318 + 3) = 0;
        *(_DWORD *)(v318 + 32) = 0;
        *(_BYTE *)(v318 + 2) = v323 != 0;
        IsValidNN = *i;
        if ( (_BYTE)IsValidNN == 29 )
        {
          v7 = v664;
          v13 = v661;
          v8 = v660;
          if ( !v323 )
            goto LABEL_249;
        }
        else
        {
          if ( v323 )
            goto LABEL_177;
          if ( (_BYTE)IsValidNN == 27 )
          {
            for ( m = 0; ; ++m )
            {
              IsValidNN = WORD6(v675);
              if ( m >= WORD6(v675) )
                break;
              if ( (*(_BYTE *)(56LL * m + *((_QWORD *)&v674 + 1) + 20) & 1) != 0 )
                goto LABEL_177;
            }
          }
          v7 = v664;
          v13 = v661;
          v8 = v660;
          if ( *i == 26 )
          {
            IsValidNN = *((unsigned __int16 *)i + 8);
            *(_WORD *)(v318 + 12) = IsValidNN;
          }
        }
        goto LABEL_108;
      case 0x1Eu:
        v325 = 56LL * *((int *)i + 3);
        v678 = 0;
        if ( (*(_BYTE *)(v325 + v6 + 20) & 0x24) != 0 )
          goto LABEL_676;
        LOBYTE(v7) = 67;
        v326 = *(_OWORD *)(v325 + v6 + 16);
        v681[0] = *(_OWORD *)(v325 + v6);
        v1 = *(_OWORD *)(v325 + v6 + 32);
        v681[1] = v326;
        *(_QWORD *)&v326 = *(_QWORD *)(v325 + v6 + 48);
        v682 = v1;
        v683 = v326;
        applyAffinity(v681, v7, v8);
        if ( (BYTE4(v681[1]) & 4) == 0 )
          goto LABEL_177;
        v327 = *(_QWORD *)&v681[0];
LABEL_677:
        v328 = *(_QWORD *)(v2[15] + 8LL * *((int *)i + 1));
        v329 = *(_QWORD *)(v328 + 48);
        v678 = 0;
        v330 = sqlite3BtreeTableMoveto(v329, v327, 0, &v678);
        *(_QWORD *)(v328 + 80) = v327;
        updated = v330;
        *(_WORD *)(v328 + 2) = 0;
        *(_DWORD *)(v328 + 32) = 0;
        Table = v330;
        IsValidNN = v678;
        *(_DWORD *)(v328 + 36) = v678;
        if ( !v678 )
          goto LABEL_680;
        if ( *((_DWORD *)i + 2) )
          goto LABEL_622;
        IsValidNN = sqlite3ReportError(11, 98564, "database corruption");
        updated = IsValidNN;
        Table = IsValidNN;
LABEL_680:
        if ( !updated )
          goto LABEL_48;
        goto LABEL_309;
      case 0x1Fu:
LABEL_676:
        v327 = *(_QWORD *)(56LL * *((int *)i + 3) + v6);
        goto LABEL_677;
      case 0x20u:
      case 0x89u:
        v385 = *((int *)i + 1);
        v386 = v2[15];
        LODWORD(v669) = 0;
        v387 = *(_QWORD *)(v386 + 8 * v385);
        v388 = *(_QWORD *)(v387 + 48);
        if ( (_BYTE)v14 == 0x89 )
        {
          v389 = *(_QWORD *)(v387 + 48);
          *(_DWORD *)(v387 + 36) = -1;
          IsValidNN = sqlite3BtreeCursorIsValidNN(v389, v7, v13);
          if ( (_DWORD)IsValidNN )
            goto LABEL_48;
        }
        updated = sqlite3BtreeLast(v388, &v669, v13);
        Table = updated;
        IsValidNN = (unsigned __int8)v669;
        *(_WORD *)(v387 + 2) = (unsigned __int8)v669;
        *(_DWORD *)(v387 + 32) = 0;
        if ( updated )
          goto LABEL_309;
        v7 = v664;
        v13 = v661;
        v3 = v666;
        v8 = v660;
        if ( *((int *)i + 2) <= 0 || !(_DWORD)v669 )
          goto LABEL_108;
        goto LABEL_249;
      case 0x21u:
        v390 = *((int *)i + 1);
        v391 = v2[15];
        LODWORD(v669) = 0;
        v392 = *(_QWORD *)(*(_QWORD *)(v391 + 8 * v390) + 48LL);
        Table = sqlite3BtreeFirst(v392, &v669, v13);
        updated = Table;
        if ( Table )
          goto LABEL_309;
        if ( (_DWORD)v669 )
        {
          v393 = -1;
        }
        else
        {
          v394 = sqlite3BtreeRowCountEst(v392);
          v393 = (__int16)sqlite3LogEst(v394);
        }
        IsValidNN = *((int *)i + 3);
        if ( v393 >= IsValidNN )
        {
          IsValidNN = *((int *)i + 4);
          if ( v393 <= IsValidNN )
          {
            LODWORD(v669) = 1;
            goto LABEL_177;
          }
        }
        LODWORD(v669) = 0;
        goto LABEL_27;
      case 0x22u:
      case 0x23u:
        ++*((_DWORD *)v2 + 55);
        goto LABEL_787;
      case 0x24u:
LABEL_787:
        v395 = *((int *)i + 1);
        v396 = v2[15];
        LODWORD(v669) = 0;
        v397 = *(_QWORD *)(v396 + 8 * v395);
        LODWORD(v669) = 1;
        if ( *(_BYTE *)v397 == 1 )
        {
          v398 = sqlite3VdbeSorterRewind(v397, &v669, v13);
        }
        else
        {
          v398 = sqlite3BtreeFirst(*(_QWORD *)(v397 + 48), &v669, v13);
          *(_BYTE *)(v397 + 3) = 0;
          *(_DWORD *)(v397 + 32) = 0;
        }
        Table = v398;
        updated = v398;
        if ( v398 )
          goto LABEL_309;
        IsValidNN = (unsigned __int8)v669;
        v7 = v664;
        v13 = v661;
        v8 = v660;
        *(_BYTE *)(v397 + 2) = (_BYTE)v669;
        if ( *((int *)i + 2) <= 0 || !(_DWORD)v669 )
          goto LABEL_108;
        goto LABEL_249;
      case 0x25u:
        v399 = *(_QWORD *)(v2[15] + 8LL * *((int *)i + 1));
        v400 = sqlite3VdbeSorterNext(v5, v399, v13);
        goto LABEL_797;
      case 0x26u:
        v399 = *(_QWORD *)(v2[15] + 8LL * *((int *)i + 1));
        v400 = sqlite3BtreePrevious(*(_QWORD *)(v399 + 48), *((unsigned int *)i + 3), v13);
        goto LABEL_797;
      case 0x27u:
        v399 = *(_QWORD *)(v2[15] + 8LL * *((int *)i + 1));
        v400 = sqlite3BtreeNext(*(_QWORD *)(v399 + 48), *((unsigned int *)i + 3), v13);
LABEL_797:
        updated = v400;
        Table = v400;
        *(_DWORD *)(v399 + 32) = 0;
        if ( !v400 )
        {
          *(_BYTE *)(v399 + 2) = 0;
          ++*((_DWORD *)v2 + *((unsigned __int16 *)i + 1) + 53);
LABEL_1063:
          v9 = v665;
LABEL_1064:
          v7 = v664;
LABEL_1065:
          i = &v3[24 * *((_DWORD *)i + 2) - 24];
          goto LABEL_881;
        }
        if ( v400 == 101 )
        {
          updated = 0;
          *(_BYTE *)(v399 + 2) = 1;
          Table = 0;
          goto LABEL_880;
        }
        goto LABEL_309;
      case 0x28u:
      case 0x29u:
      case 0x2Au:
      case 0x2Du:
        v422 = *((int *)i + 1);
        *(_QWORD *)&v676 = 0;
        v1 = 0;
        v423 = v2[15];
        v674 = 0;
        v675 = 0;
        v424 = *(_QWORD *)(v423 + 8 * v422);
        memset(v681, 0, sizeof(v681));
        *(_QWORD *)&v674 = *(_QWORD *)(v424 + 56);
        WORD6(v675) = *((_WORD *)i + 8);
        BYTE14(v675) = -((unsigned __int8)v14 < 0x2Au);
        v425 = 56LL * *((int *)i + 3);
        v682 = 0;
        v683 = 0;
        *((_QWORD *)&v674 + 1) = v6 + v425;
        v426 = *(_QWORD *)(v424 + 48);
        getCellInfo(v426, v424, v13);
        v427 = *(unsigned int *)(v426 + 64);
        if ( (unsigned int)(v427 - 1) > 0x7FFFFFFE )
        {
          updated = sqlite3ReportError(11, 99861, "database corruption");
          goto LABEL_309;
        }
        *((_QWORD *)&v681[1] + 1) = v5;
        WORD2(v681[1]) = 0;
        LODWORD(v682) = 0;
        Table = sqlite3VdbeMemFromBtreeZeroOffset(v426, v427, v681);
        updated = Table;
        if ( Table )
          goto LABEL_309;
        v428 = sqlite3VdbeRecordCompareWithSkip(LODWORD(v681[1]), *((_QWORD *)&v681[0] + 1), &v674, 0);
        IsValidNN = sqlite3VdbeMemReleaseMalloc(v681);
        v7 = v664;
        v429 = v428 + 1;
        v13 = v661;
        v430 = -v428;
        v8 = v660;
        if ( (*i & 1) != 0 )
          v430 = v429;
        if ( v430 <= 0 )
          goto LABEL_108;
        goto LABEL_249;
      case 0x2Bu:
      case 0x2Cu:
        v123 = sqlite3VdbeBooleanValue(v6 + 56LL * *((int *)i + 1), 2, v13);
        v125 = sqlite3VdbeBooleanValue(v6 + 56LL * *((int *)i + 2), 2, v124) + 2 * v123 + v123;
        v126 = &qword_1800B61E8;
        if ( *i != 44 )
          v126 = qword_1800B71B0;
        v127 = *((unsigned __int8 *)v126 + v125);
        v128 = 56LL * *((int *)i + 3);
        v129 = *(_WORD *)(v128 + v6 + 20);
        if ( (_BYTE)v127 == 2 )
        {
          IsValidNN = 62017;
          v130 = v129 & 0xF240 | 1;
        }
        else
        {
          IsValidNN = 62020;
          *(_QWORD *)(v128 + v6) = v127;
          v130 = v129 & 0xF240 | 4;
        }
        *(_WORD *)(v128 + v6 + 20) = v130;
        goto LABEL_27;
      case 0x2Eu:
        v464 = *((int *)i + 1);
        v668 = 0;
        v465 = v6 + 56 * v464;
        if ( (*(_BYTE *)(v465 + 20) & 0x10) != 0 && (unsigned int)sqlite3RowSetNext(*(_QWORD *)(v465 + 8), &v668, v13) )
        {
          sqlite3VdbeMemSetInt64(v6 + 56LL * *((int *)i + 3), v668, v466);
          goto LABEL_880;
        }
        sqlite3VdbeMemSetNull(v465);
        goto LABEL_1063;
      case 0x2Fu:
        IsValidNN = *((int *)i + 1);
        v467 = *((_DWORD *)i + 4);
        v468 = v6 + 56 * IsValidNN;
        v469 = *((int *)i + 3);
        if ( (*(_BYTE *)(v468 + 20) & 0x10) != 0 )
          goto LABEL_896;
        IsValidNN = sqlite3VdbeMemSetRowSet(v468, v7, v13);
        if ( (_DWORD)IsValidNN )
          goto LABEL_90;
        v7 = v664;
        v13 = v661;
        v8 = v660;
LABEL_896:
        v470 = v673;
        v471 = 56 * v469;
        v472 = v467 < 0;
        if ( !v467 )
          goto LABEL_899;
        IsValidNN = sqlite3RowSetTest(*(_QWORD *)(v468 + 8), (unsigned int)v467, *(_QWORD *)(v471 + v673));
        v7 = v664;
        v13 = v661;
        v8 = v660;
        if ( (_DWORD)IsValidNN )
        {
          v3 = v666;
          goto LABEL_249;
        }
        v472 = v467 < 0;
LABEL_899:
        if ( !v472 )
        {
          IsValidNN = sqlite3RowSetInsert(*(_QWORD *)(v468 + 8), *(_QWORD *)(v471 + v470), v13);
          goto LABEL_48;
        }
        goto LABEL_107;
      case 0x30u:
        v473 = (unsigned __int8 **)*((_QWORD *)i + 2);
        if ( !*((_WORD *)i + 1) )
          goto LABEL_905;
        IsValidNN = v2[33];
        if ( !IsValidNN )
          goto LABEL_905;
        while ( *(unsigned __int8 **)(IsValidNN + 48) != v473[4] )
        {
          IsValidNN = *(_QWORD *)(IsValidNN + 8);
          if ( !IsValidNN )
          {
LABEL_905:
            if ( *((_DWORD *)v2 + 70) >= *(_DWORD *)(v5 + 176) )
            {
              updated = 1;
              sqlite3VdbeError(v2, "too many levels of trigger recursion", v13);
              goto LABEL_309;
            }
            v474 = v6 + 56LL * *((int *)i + 3);
            if ( (*(_BYTE *)(v474 + 20) & 0x10) != 0 )
            {
              v478 = *(_QWORD *)(v474 + 8);
              goto LABEL_914;
            }
            v475 = *((_DWORD *)v473 + 4);
            v476 = v475 + *((_DWORD *)v473 + 3) + 1;
            if ( v475 )
              v476 = v475 + *((_DWORD *)v473 + 3);
            v477 = (*((_DWORD *)v473 + 2) + 7) / 8 + 8 * (v475 + 7 * (v476 + 2));
            v478 = sqlite3DbMallocZero(v5, v477);
            if ( v478 )
            {
              sqlite3VdbeMemRelease(v474);
              *(_QWORD *)(v474 + 48) = sqlite3VdbeFrameMemDel;
              v479 = v478 + 112;
              *(_DWORD *)(v474 + 16) = v477;
              v2 = a1;
              *(_WORD *)(v474 + 20) = 4112;
              *(_QWORD *)(v474 + 8) = v478;
              *(_QWORD *)v478 = a1;
              *(_DWORD *)(v478 + 88) = v476;
              *(_DWORD *)(v478 + 92) = *((_DWORD *)v473 + 4);
              *(_DWORD *)(v478 + 76) = -1431655765 * ((i - v666) >> 3);
              *(_QWORD *)(v478 + 24) = a1[13];
              *(_DWORD *)(v478 + 84) = *((_DWORD *)a1 + 9);
              *(_QWORD *)(v478 + 32) = a1[15];
              *(_DWORD *)(v478 + 72) = *((_DWORD *)a1 + 10);
              *(_QWORD *)(v478 + 16) = a1[17];
              *(_DWORD *)(v478 + 80) = *((_DWORD *)a1 + 36);
              *(_QWORD *)(v478 + 48) = v473[4];
              v480 = v478 + 56 * (v476 + 2LL);
              if ( v478 + 112 != v480 )
              {
                do
                {
                  *(_QWORD *)(v479 + 24) = v5;
                  *(_WORD *)(v479 + 20) = 0;
                  v479 += 56;
                }
                while ( v479 != v480 );
              }
LABEL_914:
              ++*((_DWORD *)v2 + 70);
              *(_QWORD *)(v478 + 8) = v2[33];
              *(_QWORD *)(v478 + 56) = *(_QWORD *)(v5 + 56);
              *(_QWORD *)(v478 + 96) = v2[7];
              v481 = *v2;
              v673 = v478 + 112;
              *(_QWORD *)(v478 + 104) = *(_QWORD *)(v481 + 120);
              *(_QWORD *)(v478 + 64) = v2[37];
              v2[37] = 0;
              v2[7] = 0;
              v2[13] = v478 + 112;
              v2[33] = v478;
              v482 = *(int *)(v478 + 88);
              *((_DWORD *)v2 + 9) = v482;
              *((_DWORD *)v2 + 10) = *(unsigned __int16 *)(v478 + 92);
              v2[15] = v478 + 112 + 56 * v482;
              v483 = (void *)(v478 + 112 + 8 * (7 * v482 + *((int *)v473 + 4)));
              *(_QWORD *)(v478 + 40) = v483;
              memset_0(v483, 0, (*((_DWORD *)v473 + 2) + 7) / 8);
              v3 = *v473;
              v2[17] = (__int64)*v473;
              v484 = *((_DWORD *)v473 + 2);
              updated = Table;
              i = v3 - 24;
              v666 = v3;
              *((_DWORD *)v2 + 36) = v484;
LABEL_880:
              v9 = v665;
              v7 = v664;
LABEL_881:
              IsValidNN = *(unsigned int *)(v5 + 408);
              if ( !(_DWORD)IsValidNN )
              {
                while ( 1 )
                {
                  if ( v7 < v9 )
                    goto LABEL_28;
                  IsValidNN = *(_QWORD *)(v5 + 528);
                  if ( !IsValidNN )
                    goto LABEL_28;
                  v460 = *(unsigned int *)(v5 + 544);
                  IsValidNN = ((__int64 (__fastcall *)(_QWORD))IsValidNN)(*(_QWORD *)(v5 + 536));
                  if ( (_DWORD)IsValidNN )
                    break;
                  v7 = v664;
                  v9 = v460 + v665;
                  v665 += v460;
                }
                v55 = -1;
                updated = 9;
LABEL_310:
                v56 = HIBYTE(v660);
                goto LABEL_311;
              }
LABEL_1235:
              updated = 9;
              goto LABEL_309;
            }
LABEL_89:
            v2 = a1;
LABEL_90:
            sqlite3OomFault(v5);
            sqlite3VdbeError(v2, "out of memory");
            updated = 7;
            goto LABEL_309;
          }
        }
        updated = Table;
        goto LABEL_108;
      case 0x31u:
        if ( *((_DWORD *)i + 1) )
        {
          if ( !*(_QWORD *)(v5 + 760) && !*(_QWORD *)(v5 + 768) )
            goto LABEL_249;
        }
        else if ( !v2[10] && !*(_QWORD *)(v5 + 768) )
        {
          goto LABEL_249;
        }
        goto LABEL_108;
      case 0x32u:
        IsValidNN = *((int *)i + 1);
        if ( (*(_BYTE *)(56 * IsValidNN + v6 + 20) & 1) == 0 )
          goto LABEL_108;
        goto LABEL_249;
      case 0x33u:
        IsValidNN = *((int *)i + 1);
        if ( (*(_BYTE *)(56 * IsValidNN + v6 + 20) & 1) != 0 )
          goto LABEL_108;
        goto LABEL_249;
      case 0x34u:
      case 0x35u:
      case 0x36u:
      case 0x37u:
      case 0x38u:
      case 0x39u:
        IsValidNN = *((int *)i + 3);
        v103 = v6 + 56LL * *((int *)i + 1);
        v104 = v6 + 56 * IsValidNN;
        v105 = *(_WORD *)(v103 + 20);
        v106 = *(_WORD *)(v104 + 20);
        if ( ((unsigned __int8)v105 & (unsigned __int8)v106 & 4) != 0 )
        {
          v107 = *(_QWORD *)v104 <= *(_QWORD *)v103;
          updated = Table;
          v2 = a1;
          v3 = v666;
          if ( v107 )
          {
            if ( *((_BYTE *)&qword_1800ADCF0[25] + v14 + 4) )
              goto LABEL_249;
            v13 = 0xFFFFFFFFLL;
            v661 = -1;
          }
          else
          {
            if ( byte_1800ADDC8[v14] )
              goto LABEL_249;
            v13 = 1;
            v661 = 1;
          }
          goto LABEL_108;
        }
        v108 = v105 | v106;
        if ( (((unsigned __int8)v105 | (unsigned __int8)v106) & 1) == 0 )
        {
          v110 = i[2] & 0x47;
          if ( v110 < 0x43u )
          {
            if ( v110 == 66 && (v108 & 2) != 0 )
            {
              if ( (v105 & 2) != 0 )
              {
                *(_WORD *)(v103 + 20) = v105 & 0xFFD3;
              }
              else if ( (v105 & 0x2C) != 0 )
              {
                LOBYTE(v13) = 1;
                sqlite3VdbeMemStringify(v103, v8, v13);
                v8 = v660;
                v105 = *(_WORD *)(v103 + 20) ^ (v105 ^ *(_WORD *)(v103 + 20)) & 0xDBF;
                if ( v103 == v104 )
                  v106 = v105 | 2;
              }
              if ( (v106 & 2) != 0 )
              {
                *(_WORD *)(v104 + 20) &= 0xFFD3u;
              }
              else if ( (v106 & 0x2C) != 0 )
              {
                LOBYTE(v13) = 1;
                sqlite3VdbeMemStringify(v104, v8, v13);
                v106 = *(_WORD *)(v104 + 20) ^ (*(_WORD *)(v104 + 20) ^ v106) & 0xDBF;
              }
            }
          }
          else if ( (v108 & 2) != 0 )
          {
            if ( (v105 & 0x2E) == 2 )
            {
              applyNumericAffinity(v103, 0, v13);
              v106 = *(_WORD *)(v104 + 20);
            }
            if ( (v106 & 0x2E) == 2 )
              applyNumericAffinity(v104, 0, v13);
          }
          v111 = sqlite3MemCompare(v104, v103, *((_QWORD *)i + 2));
          v8 = v660;
          v13 = (unsigned int)v111;
          v661 = v111;
          if ( v111 < 0 )
          {
LABEL_225:
            IsValidNN = *i;
            v109 = *((_BYTE *)&qword_1800ADCF0[25] + IsValidNN + 4);
            goto LABEL_203;
          }
          IsValidNN = *i;
          v661 = v13;
          if ( !(_DWORD)v13 )
          {
LABEL_227:
            v109 = byte_1800ADDC2[IsValidNN];
LABEL_203:
            v7 = v664;
            *(_WORD *)(v104 + 20) = v106;
            updated = Table;
            v3 = v666;
            *(_WORD *)(v103 + 20) = v105;
            v2 = a1;
            if ( !v109 )
              goto LABEL_108;
            goto LABEL_249;
          }
LABEL_202:
          v109 = byte_1800ADDC8[IsValidNN];
          goto LABEL_203;
        }
        IsValidNN = *((unsigned __int16 *)i + 1);
        if ( (IsValidNN & 0x80u) != 0LL )
        {
          if ( ((unsigned __int8)v105 & (unsigned __int8)v106 & 1) != 0 && (v106 & 0x100) == 0 )
          {
            IsValidNN = *i;
            v13 = 0;
            v661 = 0;
            goto LABEL_227;
          }
          if ( (v106 & 1) != 0 )
          {
            v13 = 0xFFFFFFFFLL;
            v661 = -1;
            goto LABEL_225;
          }
          IsValidNN = *i;
          v13 = 1;
          v661 = 1;
          goto LABEL_202;
        }
        v2 = a1;
        updated = Table;
        v3 = v666;
        if ( (IsValidNN & 0x10) != 0 )
          goto LABEL_249;
        v13 = 1;
        v661 = 1;
        goto LABEL_108;
      case 0x3Au:
        if ( (_DWORD)v13 )
          goto LABEL_108;
        goto LABEL_249;
      case 0x3Bu:
        IsValidNN = *((int *)i + 1);
        v491 = *(_QWORD *)(56 * IsValidNN + v6);
        if ( v491 <= 0 )
          goto LABEL_19;
        *(_QWORD *)(56 * IsValidNN + v6) = v491 - *((int *)i + 3);
        goto LABEL_249;
      case 0x3Cu:
        v496 = 56LL * *((int *)i + 1);
        IsValidNN = *(_QWORD *)(v496 + v6);
        if ( !IsValidNN )
          goto LABEL_108;
        if ( IsValidNN > 0 )
          *(_QWORD *)(v496 + v6) = IsValidNN - 1;
        goto LABEL_249;
      case 0x3Du:
        v497 = 56LL * *((int *)i + 1);
        IsValidNN = *(_QWORD *)(v497 + v6);
        if ( IsValidNN == 0x8000000000000000uLL )
          goto LABEL_108;
        *(_QWORD *)(v497 + v6) = --IsValidNN;
        if ( IsValidNN )
          goto LABEL_108;
        goto LABEL_249;
      case 0x3Eu:
        IsValidNN = sqlite3BtreeIncrVacuum(*(_QWORD *)(32LL * *((int *)i + 1) + *(_QWORD *)(v5 + 32) + 8), v7, v13);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( !(_DWORD)IsValidNN )
          goto LABEL_27;
        if ( (_DWORD)IsValidNN != 101 )
          goto LABEL_309;
        updated = 0;
        Table = 0;
        goto LABEL_177;
      case 0x3Fu:
        IsValidNN = v2[15];
        v579 = *(_QWORD *)(IsValidNN + 8LL * *((int *)i + 1));
        if ( *(_BYTE *)(v579 + 2) )
          goto LABEL_107;
        v580 = *(__int64 ***)(v579 + 48);
        v581 = *v580;
        v582 = **v580;
        Table = (*(__int64 (__fastcall **)(__int64 **, unsigned __int64, __int64))(v582 + 72))(v580, v7, v13);
        updated = Table;
        sqlite3VtabImportErrmsg(v2, v581);
        if ( Table )
          goto LABEL_309;
        if ( (*(unsigned int (__fastcall **)(_QWORD))(v582 + 80))(*(_QWORD *)(v579 + 48)) )
          goto LABEL_879;
        v3 = v666;
        goto LABEL_1063;
      case 0x40u:
        v610 = 56LL * *((int *)i + 1);
        v611 = filterHash(v6, i, v13);
        v8 = v660;
        v612 = *(char *)(((v611 % (8 * *(_DWORD *)(v610 + v6 + 16))) >> 3) + *(_QWORD *)(v610 + v6 + 8));
        v7 = v664;
        IsValidNN = (v611 % (8 * *(_DWORD *)(v610 + v6 + 16))) & 7;
        v613 = _bittest(&v612, IsValidNN);
        v13 = v661;
        if ( !v613 )
        {
          ++*((_DWORD *)v2 + 61);
          goto LABEL_249;
        }
        ++*((_DWORD *)v2 + 60);
        goto LABEL_108;
      case 0x41u:
      case 0x42u:
        v597 = *((_QWORD *)i + 2);
        v598 = v6 + 56LL * *((int *)i + 3);
        if ( *(_QWORD *)v597 != v598 )
        {
          v599 = (unsigned int)*(unsigned __int8 *)(v597 + 42) - 1;
          *(_QWORD *)(v597 + 24) = v2;
          *(_QWORD *)v597 = v598;
          for ( *(_BYTE *)(v597 + 40) = v8; (int)v599 >= 0; v599 = (unsigned int)(v599 - 1) )
            *(_QWORD *)(v597 + 8 * v599 + 48) = v6 + 56LL * ((int)v599 + *((_DWORD *)i + 2));
        }
        *(_WORD *)(v598 + 20) &= 0xF241u;
        *(_WORD *)(v598 + 20) |= 1u;
        (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)(v597 + 8) + 24LL))(
          v597,
          *(unsigned __int8 *)(v597 + 42),
          v597 + 48);
        IsValidNN = *(unsigned int *)(v597 + 36);
        if ( !(_DWORD)IsValidNN )
          goto LABEL_48;
        if ( (int)IsValidNN > 0 )
        {
          LOBYTE(v600) = 1;
          v601 = (const char *)sqlite3ValueText(v598, v600);
          sqlite3VdbeError(v2, "%s", v601);
          updated = *(_DWORD *)(v597 + 36);
          Table = updated;
        }
        IsValidNN = sqlite3VdbeDeleteAuxData(v5, v2 + 37, *(unsigned int *)(v597 + 32), *((unsigned int *)i + 1));
        *(_DWORD *)(v597 + 36) = 0;
        goto LABEL_576;
      case 0x43u:
        IsValidNN = 56LL * *((int *)i + 1);
        if ( (*(_BYTE *)(IsValidNN + v6 + 20) & 4) != 0 )
        {
          IsValidNN = *(_QWORD *)(IsValidNN + v6);
          i = &v3[24 * IsValidNN];
        }
        goto LABEL_108;
      case 0x44u:
        v18 = 56LL * *((int *)i + 1);
        v19 = 3LL * *(_QWORD *)(v18 + v6);
        *(_QWORD *)(v18 + v6) = (int)(-1431655765 * ((__int64)&i[-v2[17]] >> 3) - 1);
        IsValidNN = *(_DWORD *)&v3[8 * v19 + 8] - 1;
        i = &v3[24 * (int)IsValidNN];
        goto LABEL_19;
      case 0x45u:
        IsValidNN = *((int *)i + 3);
        if ( (*(_BYTE *)(56 * IsValidNN + v6 + 20) & 1) == 0 )
          goto LABEL_108;
        goto LABEL_22;
      case 0x46u:
LABEL_22:
        v22 = v2[33];
        if ( !v22 || *((_DWORD *)i + 1) )
        {
          v645 = *((_DWORD *)i + 1);
          *((_DWORD *)v2 + 13) = v645;
          *((_BYTE *)v2 + 196) = i[8];
          if ( v645 )
          {
            if ( *((_WORD *)i + 1) )
            {
              sqlite3VdbeError(v2, "%s constraint failed", off_1800AA3A0[*((unsigned __int16 *)i + 1)]);
              if ( *((_QWORD *)i + 2) )
                v2[21] = sqlite3MPrintf(v5, "%z: %s", v2[21]);
            }
            else
            {
              sqlite3VdbeError(v2, "%s", *((const char **)i + 2));
            }
            sqlite3_log(
              *((unsigned int *)i + 1),
              "abort at %d in [%s]: %s",
              -1431655765 * ((i - v3) >> 3),
              (const char *)v2[31],
              (const char *)v2[21]);
          }
          v646 = sqlite3VdbeHalt(v2);
          v7 = v664;
          updated = v646;
          v55 = v665;
          v56 = HIBYTE(v660);
          if ( v646 == 5 )
          {
            *((_DWORD *)v2 + 13) = 5;
          }
          else
          {
            updated = 101;
            if ( *((_DWORD *)v2 + 13) )
              updated = 1;
          }
          goto LABEL_1258;
        }
        v23 = *(_QWORD *)(v22 + 8);
        --*((_DWORD *)v2 + 70);
        v2[33] = v23;
        v24 = v2[7];
        *(_QWORD *)(v5 + 128) += v24;
        *(_QWORD *)(v5 + 120) = v24;
        LODWORD(IsValidNN) = sqlite3VdbeFrameRestore(v22, v7, v13);
        if ( *((_DWORD *)i + 2) == 4 )
          LODWORD(IsValidNN) = *(_DWORD *)(v2[17] + 24LL * (int)IsValidNN + 8) - 1;
        v3 = (unsigned __int8 *)v2[17];
        IsValidNN = (int)IsValidNN;
        v673 = v2[13];
        v666 = v3;
        i = &v3[24 * (int)IsValidNN];
        goto LABEL_27;
      case 0x47u:
        v25 = (__int64 *)out2Prerelease(v2, i, v13);
        IsValidNN = *((int *)i + 1);
        *v25 = IsValidNN;
        goto LABEL_27;
      case 0x48u:
        v26 = (_QWORD *)out2Prerelease(v2, i, v13);
        IsValidNN = *((_QWORD *)i + 2);
        *v26 = *(_QWORD *)IsValidNN;
        goto LABEL_27;
      case 0x49u:
        goto LABEL_40;
      case 0x4Au:
      case 0x4Bu:
        IsValidNN = out2Prerelease(v2, i, v13);
        v38 = 257;
        v39 = *((_DWORD *)i + 3) - *((_DWORD *)i + 2);
        v40 = IsValidNN;
        if ( !*((_DWORD *)i + 1) )
          v38 = 1;
        *(_WORD *)(IsValidNN + 20) = v38;
        *(_DWORD *)(IsValidNN + 16) = 0;
        if ( v39 <= 0 )
          goto LABEL_67;
        do
        {
          v40 += 56;
          IsValidNN = sqlite3VdbeMemSetNull(v40);
          --v39;
          *(_WORD *)(v40 + 20) = v38;
          *(_DWORD *)(v40 + 16) = 0;
        }
        while ( v39 > 0 );
        goto LABEL_48;
      case 0x4Cu:
        v41 = 56LL * *((int *)i + 1);
        IsValidNN = 65473;
        *(_WORD *)(v41 + v6 + 20) &= 0xFFC1u;
        *(_WORD *)(v41 + v6 + 20) |= 1u;
        goto LABEL_108;
      case 0x4Du:
        v42 = out2Prerelease(v2, i, v13);
        v43 = *((_QWORD *)i + 2);
        v44 = v42;
        if ( v43 )
        {
          IsValidNN = sqlite3VdbeMemSetStr(v42, v43, *((int *)i + 1), 0, 0);
        }
        else
        {
          sqlite3VdbeMemSetZeroBlob(v42, *((unsigned int *)i + 1));
          IsValidNN = sqlite3VdbeMemExpandBlob(v44, v45, v46);
          if ( (_DWORD)IsValidNN )
            goto LABEL_90;
        }
        v8 = v660;
        *(_BYTE *)(v44 + 22) = v660;
LABEL_57:
        v7 = v664;
LABEL_58:
        v13 = v661;
        goto LABEL_108;
      case 0x4Eu:
        v47 = v2[16] + 56LL * *((int *)i + 1);
        if ( (unsigned int)sqlite3VdbeMemTooBig(v47 - 56, v7, v13) )
          goto LABEL_1194;
        v48 = v6 + 56LL * *((int *)i + 2);
        if ( (*(_WORD *)(v48 + 20) & 0x9000) != 0 )
          sqlite3VdbeMemSetNull(v6 + 56LL * *((int *)i + 2));
        v1 = *(_OWORD *)(v47 - 56);
        *(_OWORD *)v48 = v1;
        *(_QWORD *)(v48 + 16) = *(_QWORD *)(v47 - 40);
        IsValidNN = *(unsigned __int16 *)(v48 + 20);
        LOWORD(IsValidNN) = IsValidNN & 0x8FBF | 0x2040;
        *(_WORD *)(v48 + 20) = IsValidNN;
        goto LABEL_48;
      case 0x4Fu:
        v49 = *((_DWORD *)i + 3);
        v50 = v673 + 56LL * *((int *)i + 1);
        v51 = v673 + 56LL * *((int *)i + 2);
        do
        {
          sqlite3VdbeMemRelease(v51);
          IsValidNN = 0x4000;
          *(_OWORD *)v51 = *(_OWORD *)v50;
          *(_OWORD *)(v51 + 16) = *(_OWORD *)(v50 + 16);
          v1 = *(_OWORD *)(v50 + 32);
          *(_OWORD *)(v51 + 32) = v1;
          *(_QWORD *)(v51 + 48) = *(_QWORD *)(v50 + 48);
          *(_WORD *)(v50 + 20) = 1;
          *(_DWORD *)(v50 + 32) = 0;
          if ( (*(_WORD *)(v51 + 20) & 0x4000) != 0 )
          {
            IsValidNN = sqlite3VdbeMemMakeWriteable(v51);
            if ( (_DWORD)IsValidNN )
              goto LABEL_90;
          }
          v50 += 56;
          v51 += 56;
          --v49;
        }
        while ( v49 );
LABEL_67:
        v7 = v664;
        goto LABEL_49;
      case 0x50u:
        v52 = *((_DWORD *)i + 3);
        v53 = v673 + 56LL * *((int *)i + 1);
        v54 = v673 + 56LL * *((int *)i + 2);
        while ( 2 )
        {
          sqlite3VdbeMemShallowCopy(v54, v53, 0x4000);
          if ( (*(_WORD *)(v54 + 20) & 0x4000) != 0 && (unsigned int)sqlite3VdbeMemMakeWriteable(v54) )
            goto LABEL_90;
          IsValidNN = *(unsigned __int16 *)(v54 + 20);
          if ( (IsValidNN & 0x800) != 0 && (i[2] & 2) != 0 )
          {
            LOWORD(IsValidNN) = IsValidNN & 0xF7FF;
            *(_WORD *)(v54 + 20) = IsValidNN;
          }
          if ( v52 )
          {
            --v52;
            v54 += 56;
            v53 += 56;
            continue;
          }
          goto LABEL_48;
        }
      case 0x51u:
        IsValidNN = sqlite3VdbeMemShallowCopy(v6 + 56LL * *((int *)i + 2), v6 + 56LL * *((int *)i + 1), 0x4000);
        goto LABEL_27;
      case 0x52u:
        IsValidNN = sqlite3VdbeMemSetInt64(v6 + 56LL * *((int *)i + 2), *(_QWORD *)(56LL * *((int *)i + 1) + v6), v13);
        goto LABEL_27;
      case 0x53u:
        IsValidNN = sqlite3VdbeCheckFk(v2, 0, v13);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( !(_DWORD)IsValidNN )
          goto LABEL_27;
        v55 = v665;
        v56 = HIBYTE(v660);
        goto LABEL_311;
      case 0x54u:
      case 0x59u:
      case 0x5Du:
      case 0x71u:
      case 0x76u:
      case 0x7Bu:
        goto LABEL_108;
      case 0x55u:
        IsValidNN = *((int *)i + 1);
        if ( !(_DWORD)IsValidNN )
          goto LABEL_108;
        IsValidNN = sqlite3VdbeMemSetInt64(v6 + 56 * IsValidNN, 0, v13);
        goto LABEL_27;
      case 0x56u:
        v98 = v6 + 56LL * *((int *)i + 1);
        IsValidNN = sqlite3VdbeIntValue(v98, v7, v13);
        *(_QWORD *)v98 = IsValidNN;
        *(_WORD *)(v98 + 20) &= 0xF244u;
        *(_WORD *)(v98 + 20) |= 4u;
        *(_QWORD *)v98 = IsValidNN + *((int *)i + 2);
        goto LABEL_27;
      case 0x57u:
        IsValidNN = *((int *)i + 1);
        v100 = v6 + 56 * IsValidNN;
        if ( (*(_BYTE *)(v100 + 20) & 0x24) == 0 )
          goto LABEL_108;
        v101 = sqlite3VdbeRealValue(v6 + 56 * IsValidNN, v7, v13);
        IsValidNN = 62024;
        *(double *)v100 = v101;
        *(_WORD *)(v100 + 20) &= 0xF248u;
        *(_WORD *)(v100 + 20) |= 8u;
        goto LABEL_27;
      case 0x58u:
        v102 = v6 + 56LL * *((int *)i + 1);
        if ( (*(_WORD *)(v102 + 20) & 0x400) == 0 )
          goto LABEL_187;
        updated = sqlite3VdbeMemExpandBlob(v6 + 56LL * *((int *)i + 1), v7, v13);
        if ( !updated )
        {
          v8 = v660;
LABEL_187:
          IsValidNN = sqlite3VdbeMemCast(v102, i[8], v8);
          Table = IsValidNN;
          updated = IsValidNN;
          if ( !(_DWORD)IsValidNN )
            goto LABEL_27;
        }
        goto LABEL_309;
      case 0x5Au:
        if ( (i[2] & 1) != 0 )
          v112 = *((_QWORD *)i - 1) + 4LL;
        else
          v112 = 0;
        v113 = *((_DWORD *)i + 1);
        v114 = 0;
        v115 = *((_DWORD *)i + 2);
        v116 = *((_DWORD *)i + 3);
        v117 = *((_QWORD *)i + 2);
        LODWORD(v672) = v113;
        LODWORD(v669) = v115;
        while ( 2 )
        {
          if ( v114 >= v116 )
          {
            v2 = a1;
            updated = Table;
            v7 = v664;
            goto LABEL_50;
          }
          if ( v112 )
            v118 = *(_DWORD *)(v112 + 4LL * v114);
          else
            v118 = v114;
          v119 = 56LL * (unsigned int)(v118 + v115);
          v120 = (unsigned int)(v118 + v113);
          v121 = *(_QWORD *)(v117 + 8LL * v114 + 32);
          LODWORD(v668) = *(_BYTE *)(*(_QWORD *)(v117 + 24) + v114) & 1;
          v122 = v673 + 56 * v120;
          v680 = (unsigned int *)(v673 + v119);
          IsValidNN = sqlite3MemCompare(v122, v673 + v119, v121);
          v661 = IsValidNN;
          v13 = (unsigned int)IsValidNN;
          if ( !(_DWORD)IsValidNN )
          {
            v113 = (int)v672;
            ++v114;
            v115 = (int)v669;
            continue;
          }
          break;
        }
        IsValidNN = *(_QWORD *)(v117 + 24);
        if ( (*(_BYTE *)(v114 + IsValidNN) & 2) != 0 )
        {
          if ( (*(_BYTE *)(v122 + 20) & 1) != 0 || (IsValidNN = (__int64)v680, (v680[5] & 1) != 0) )
          {
            v13 = (unsigned int)-(int)v13;
            v661 = v13;
          }
        }
        v2 = a1;
        updated = Table;
        v7 = v664;
        v3 = v666;
        v8 = v660;
        if ( (_DWORD)v668 )
        {
          v13 = (unsigned int)-(int)v13;
          v661 = v13;
        }
        goto LABEL_108;
      case 0x5Bu:
        v131 = sqlite3VdbeBooleanValue(v6 + 56LL * *((int *)i + 1), *((unsigned int *)i + 3), v13);
        IsValidNN = sqlite3VdbeMemSetInt64(v6 + 56LL * *((int *)i + 2), v131 ^ (unsigned __int64)*((int *)i + 4), v132);
        goto LABEL_27;
      case 0x5Cu:
        if ( (*(_BYTE *)(56LL * *((int *)i + 1) + v6 + 20) & 1) != 0
          || (*(_BYTE *)(56LL * *((int *)i + 3) + v6 + 20) & 1) != 0 )
        {
          goto LABEL_290;
        }
        IsValidNN = sqlite3VdbeMemSetInt64(v6 + 56LL * *((int *)i + 2), 0, v13);
        goto LABEL_27;
      case 0x5Eu:
        v1 = 0;
        v687 = 0;
        v671 = 0;
        v155 = v2[15];
        v684 = 0;
        v685 = 0;
        v686 = 0;
        v156 = *((_DWORD *)i + 2);
        v157 = *(_QWORD *)(v155 + 8LL * *((int *)i + 1));
LABEL_297:
        LODWORD(v669) = v156;
        while ( 2 )
        {
          v158 = *(unsigned int **)(v157 + 88);
          v159 = *((_DWORD *)v2 + 11);
          v680 = v158;
          if ( *(_DWORD *)(v157 + 32) == v159 )
          {
            if ( (unsigned int)sqlite3BtreeEof(*(_QWORD *)(v157 + 48)) )
              goto LABEL_307;
            v167 = v673;
            v175 = (unsigned __int16 *)(v157 + 74);
          }
          else
          {
            if ( *(_BYTE *)(v157 + 2) )
            {
              if ( *(_BYTE *)v157 != 3 || (v169 = *(int *)(v157 + 36), (int)v169 <= 0) )
              {
                IsValidNN = sqlite3VdbeMemSetNull(v673 + 56LL * *((int *)i + 3));
                goto LABEL_48;
              }
              v167 = v673;
              v165 = (unsigned int *)(v157 + 108);
              v170 = 56 * v169;
              v171 = *(_DWORD *)(56 * v169 + v673 + 16);
              *(_DWORD *)(v157 + 108) = v171;
              *(_DWORD *)(v157 + 104) = v171;
              v168 = *(unsigned __int8 **)(v170 + v167 + 8);
            }
            else
            {
              v160 = *(_QWORD *)(v157 + 48);
              if ( !*(_BYTE *)(v157 + 3) )
              {
                if ( !(unsigned int)sqlite3BtreeEof(*(_QWORD *)(v157 + 48)) )
                  goto LABEL_314;
LABEL_307:
                Table = sqlite3VdbeHandleMovedCursor(v157);
                updated = Table;
                if ( Table )
                  goto LABEL_308;
                continue;
              }
              v161 = *(_QWORD *)(v157 + 16);
              if ( v161 )
              {
                v162 = *(_DWORD *)(v161 + 4LL * (v156 + 1));
                if ( v162 )
                {
                  v157 = *(_QWORD *)(v157 + 40);
                  v156 = v162 - 1;
                  goto LABEL_297;
                }
              }
              Table = sqlite3VdbeFinishMoveto(v157, v161, v13);
              updated = Table;
              if ( Table )
                goto LABEL_308;
LABEL_314:
              getCellInfo(v160, v163, v164);
              v165 = (unsigned int *)(v157 + 108);
              *(_DWORD *)(v157 + 104) = *(_DWORD *)(v160 + 64);
              Payload = fetchPayload(v160, v157 + 108);
              v167 = v673;
              v168 = (unsigned __int8 *)Payload;
            }
            *(_QWORD *)(v157 + 96) = v168;
            v172 = (int *)(v157 + 64);
            *(_DWORD *)(v157 + 32) = *((_DWORD *)v2 + 11);
            v173 = *v168;
            *v158 = v173;
            if ( v173 >= 0x80 )
            {
              LOBYTE(v174) = sqlite3GetVarint32(*(_QWORD *)(v157 + 96), v158, v167);
              v167 = v673;
              v174 = (unsigned __int8)v174;
            }
            else
            {
              v174 = 1;
            }
            v175 = (unsigned __int16 *)(v157 + 74);
            *v172 = v174;
            *(_WORD *)(v157 + 74) = 0;
            if ( *v165 >= *v158 )
            {
              v176 = *(_QWORD *)(v157 + 96);
              goto LABEL_330;
            }
            *(_QWORD *)(v157 + 96) = 0;
            *v165 = 0;
            if ( *v158 > 0x18003 || *v158 > *(_DWORD *)(v157 + 104) )
              goto LABEL_352;
            v156 = (unsigned int)v669;
            updated = Table;
          }
          break;
        }
        if ( *v175 > v156 )
        {
          v183 = *(unsigned int *)(v157 + 4LL * v156 + 120);
          v671 = *(_DWORD *)(v157 + 4LL * v156 + 120);
          goto LABEL_359;
        }
        v172 = (int *)(v157 + 64);
        if ( *(_DWORD *)(v157 + 64) >= *v158 )
        {
          v183 = 0;
          v671 = 0;
          goto LABEL_355;
        }
        v176 = *(_QWORD *)(v157 + 96);
        if ( !v176 )
        {
          v1 = 0;
          v684 = 0;
          v685 = 0;
          v687 = 0;
          v686 = 0;
          Table = sqlite3VdbeMemFromBtreeZeroOffset(*(_QWORD *)(v157 + 48), *v158, &v684);
          updated = Table;
          if ( Table )
            goto LABEL_308;
          v176 = *((_QWORD *)&v684 + 1);
        }
LABEL_330:
        v177 = *v175;
        v178 = (unsigned __int8 *)(v176 + (unsigned int)*v172);
        v179 = v176 + *v158;
        LODWORD(v672) = v177;
        v180 = v158[v177];
        while ( 1 )
        {
          v671 = *v178;
          v181 = (int)v177;
          *(_DWORD *)(v157 + 4LL * (int)v177 + 120) = v671;
          if ( v671 >= 0x80 )
          {
            v178 += (unsigned __int8)sqlite3GetVarint32(v178, &v671, v167);
            *(_DWORD *)(v157 + 4 * v181 + 120) = v671;
            LODWORD(v182) = sqlite3VdbeSerialTypeLen(v671);
            LODWORD(v177) = (_DWORD)v672;
            v182 = (unsigned int)v182;
          }
          else
          {
            ++v178;
            v182 = *((unsigned __int8 *)qword_1800AE060 + (unsigned __int8)v671);
          }
          v158 = v680;
          LODWORD(v177) = v177 + 1;
          v180 += v182;
          LODWORD(v672) = v177;
          v680[(int)v177] = v180;
          if ( (unsigned int)v177 > (unsigned int)v669 )
            break;
          if ( (unsigned __int64)v178 >= v179 )
            goto LABEL_341;
        }
        if ( (unsigned __int64)v178 < v179 )
        {
          if ( v180 <= *(unsigned int *)(v157 + 104) )
            goto LABEL_343;
        }
        else
        {
LABEL_341:
          if ( (unsigned __int64)v178 <= v179 && v180 == *(_DWORD *)(v157 + 104) )
            goto LABEL_343;
        }
        if ( !*v158 )
        {
          LOWORD(v177) = 0;
          LODWORD(v178) = v179;
LABEL_343:
          *(_WORD *)(v157 + 74) = v177;
          v37 = *(_QWORD *)(v157 + 96) == 0;
          *(_DWORD *)(v157 + 64) = (_DWORD)v178 - v176;
          if ( v37 )
            sqlite3VdbeMemRelease(&v684);
          v183 = v671;
          v2 = a1;
          updated = Table;
          v167 = v673;
LABEL_355:
          v156 = (unsigned int)v669;
          if ( *(unsigned __int16 *)(v157 + 74) <= (unsigned int)v669 )
          {
            v91 = v167 + 56LL * *((int *)i + 3);
            if ( i[1] == 0xF6 )
              IsValidNN = sqlite3VdbeMemShallowCopy(v91, *((_QWORD *)i + 2), 0x2000);
            else
LABEL_153:
              IsValidNN = sqlite3VdbeMemSetNull(v91);
            goto LABEL_48;
          }
LABEL_359:
          v185 = v167 + 56LL * *((int *)i + 3);
          if ( (*(_WORD *)(v185 + 20) & 0x9000) != 0 )
          {
            sqlite3VdbeMemSetNull(v167 + 56LL * *((int *)i + 3));
            v183 = v671;
          }
          if ( *(_DWORD *)(v157 + 108) < v158[v156 + 1] )
          {
            *(_BYTE *)(v185 + 22) = v660;
            v189 = v671;
            v190 = i[2] & 0xC0;
            if ( v190 && (v190 == (char)0x80 || v671 >= 0xC && ((v671 & 1) == 0 || v190 == -64)) )
              goto LABEL_377;
            if ( !(unsigned int)sqlite3VdbeSerialTypeLen(v671) )
            {
              v189 = v671;
LABEL_377:
              IsValidNN = sqlite3VdbeSerialGet(&qword_1800ADE90, v189, v185);
              goto LABEL_48;
            }
            IsValidNN = vdbeColumnFromOverflow(v157, v156, v671, v158[v156], *((_DWORD *)v2 + 11), v677, v185);
            Table = IsValidNN;
            updated = IsValidNN;
            if ( !(_DWORD)IsValidNN )
              goto LABEL_48;
            v5 = v670;
            if ( (_DWORD)IsValidNN == 7 )
              goto LABEL_90;
            if ( (_DWORD)IsValidNN != 18 )
              goto LABEL_309;
LABEL_1194:
            sqlite3VdbeError(v2, "string or blob too big");
            updated = 18;
            goto LABEL_309;
          }
          v186 = (const void *)(*(_QWORD *)(v157 + 96) + v158[v156]);
          if ( (unsigned int)v183 < 0xC )
          {
            IsValidNN = sqlite3VdbeSerialGet(v186, v183, v185);
            goto LABEL_48;
          }
          v187 = (unsigned int)(v183 - 12) >> 1;
          *(_DWORD *)(v185 + 16) = v187;
          *(_BYTE *)(v185 + 22) = v660;
          v188 = (unsigned int)(v187 + 2);
          if ( *(_DWORD *)(v185 + 32) >= (int)v188 )
          {
            *(_QWORD *)(v185 + 8) = *(_QWORD *)(v185 + 40);
          }
          else
          {
            v5 = v670;
            if ( (int)v187 > *(_DWORD *)(v670 + 136) )
              goto LABEL_1194;
            *(_WORD *)(v185 + 20) = 1;
            if ( (unsigned int)sqlite3VdbeMemGrow(v185, v188, 0) )
              goto LABEL_90;
          }
          memcpy_0(*(void **)(v185 + 8), v186, v187);
          v7 = v664;
          v13 = v661;
          v8 = v660;
          *(_BYTE *)(v187 + *(_QWORD *)(v185 + 8)) = 0;
          *(_BYTE *)(v187 + *(_QWORD *)(v185 + 8) + 1) = 0;
          IsValidNN = (unsigned __int16)word_1800B8AE8[v671 & 1];
          *(_WORD *)(v185 + 20) = IsValidNN;
          v3 = v666;
          goto LABEL_108;
        }
        if ( !*(_QWORD *)(v157 + 96) )
          sqlite3VdbeMemRelease(&v684);
        v2 = a1;
LABEL_352:
        v3 = v666;
        v184 = *((_DWORD *)v666 + 3);
        if ( v184 <= 0 )
        {
          updated = sqlite3ReportError(11, 96310, "database corruption");
          goto LABEL_308;
        }
        updated = Table;
        v7 = v664;
        IsValidNN = 3LL * (v184 - 1);
        i = &v666[8 * IsValidNN];
        goto LABEL_28;
      case 0x5Fu:
        v191 = *((_QWORD *)i + 2);
        v192 = *(_QWORD *)(v191 + 8);
        v193 = v673 + 56LL * *((int *)i + 1);
        v194 = 0;
        while ( 2 )
        {
          IsValidNN = (unsigned int)*(__int16 *)(v191 + 54);
          if ( v194 >= (int)IsValidNN )
            goto LABEL_104;
          v195 = *(_WORD *)(v192 + 24LL * v194 + 18);
          if ( (v195 & 0x60) == 0 )
            goto LABEL_387;
          if ( (v195 & 0x20) != 0 )
            goto LABEL_407;
          if ( *((_DWORD *)i + 3) )
            goto LABEL_406;
LABEL_387:
          applyAffinity(v193, *(unsigned __int8 *)(v192 + 24LL * v194 + 12), v8);
          v196 = *(_WORD *)(v193 + 20);
          if ( (v196 & 1) != 0 )
            goto LABEL_405;
          switch ( (*(_DWORD *)(v192 + 24LL * v194 + 8) >> 4) & 0xF )
          {
            case 2:
              if ( (v196 & 0x10) != 0 )
                goto LABEL_405;
              break;
            case 3:
            case 4:
              if ( (v196 & 4) != 0 )
                goto LABEL_405;
              break;
            case 5:
              if ( (v196 & 4) != 0 )
              {
                if ( (unsigned __int64)(*(_QWORD *)v193 + 0x800000000000LL) > 0xFFFFFFFFFFFFLL )
                {
                  v1 = 0;
                  v197 = v196 | 8;
                  *(double *)v193 = (double)(int)*(_QWORD *)v193;
                }
                else
                {
                  v197 = v196 | 0x20;
                }
                *(_WORD *)(v193 + 20) = v197;
                *(_WORD *)(v193 + 20) = v197 & 0xFFFB;
                goto LABEL_405;
              }
              if ( (v196 & 0x28) != 0 )
              {
LABEL_405:
                v8 = v660;
LABEL_406:
                v193 += 56;
LABEL_407:
                ++v194;
                continue;
              }
              break;
            default:
              if ( ((*(_DWORD *)(v192 + 24LL * v194 + 8) >> 4) & 0xF) == 6 && (v196 & 2) == 0 )
                goto LABEL_394;
              goto LABEL_405;
          }
          break;
        }
LABEL_394:
        _mm_lfence();
        v2 = a1;
        sqlite3VdbeError(
          a1,
          "cannot store %s value in %s column %s.%s",
          off_1800AAF50[*((unsigned __int8 *)qword_1800B9DC0 + (*(_WORD *)(v193 + 20) & 0x3F))],
          off_1800C6610[(unsigned int)((unsigned __int8)*(_DWORD *)(v192 + 24LL * v194 + 8) >> 4) - 1],
          *(const char **)v191,
          *(const char **)(v192 + 24LL * v194));
        updated = 3091;
        goto LABEL_309;
      case 0x60u:
        v198 = (_BYTE *)*((_QWORD *)i + 2);
        LOBYTE(IsValidNN) = *v198;
        for ( n = v6 + 56LL * *((int *)i + 1); ; n += 56 )
        {
          applyAffinity(n, (unsigned __int8)IsValidNN, v8);
          if ( *v198 == 69 )
          {
            v200 = *(_WORD *)(n + 20);
            if ( (v200 & 4) != 0 )
            {
              if ( (unsigned __int64)(*(_QWORD *)n + 0x800000000000LL) > 0xFFFFFFFFFFFFLL )
              {
                v1 = 0;
                v201 = v200 & 0xFFF1 | 8;
                *(double *)n = (double)(int)*(_QWORD *)n;
              }
              else
              {
                v201 = v200 & 0xFFDB | 0x20;
              }
              *(_WORD *)(n + 20) = v201;
            }
          }
          IsValidNN = (unsigned __int8)*++v198;
          v8 = v660;
          if ( !(_BYTE)IsValidNN )
            break;
        }
        goto LABEL_105;
      case 0x61u:
        v202 = 0;
        v203 = (_BYTE *)*((_QWORD *)i + 2);
        v204 = 0;
        v205 = *((int *)i + 3);
        v206 = 0;
        v207 = 56LL * *((int *)i + 1);
        v208 = *((_DWORD *)i + 2) - 1;
        v668 = 0;
        v209 = (int *)(v6 + v207);
        v672 = (__int64 *)v209;
        v210 = &v209[14 * v208];
        v669 = v210;
        if ( v203 )
        {
          v211 = (__int64 *)v209;
          do
          {
            applyAffinity(v211, (unsigned __int8)*v203, v8);
            if ( *v203 == 69 )
            {
              v212 = *((_WORD *)v211 + 10);
              if ( (v212 & 4) != 0 )
                *((_WORD *)v211 + 10) = v212 & 0xFFDB | 0x20;
            }
            v8 = v660;
            ++v203;
            v211 += 7;
          }
          while ( *v203 );
          v209 = (int *)v672;
          v202 = 0;
          v210 = v669;
        }
        v213 = v210;
        v214 = 1024;
        while ( 2 )
        {
          v215 = *((_WORD *)v213 + 10);
          if ( (v215 & 1) != 0 )
          {
            v213[9] = (v215 & 0x400) != 0 ? 0xA : 0;
            ++v204;
LABEL_458:
            if ( v213 != v209 )
            {
              v213 -= 14;
              continue;
            }
            v224 = v673 + 56 * v205;
            if ( v204 > 126 )
            {
              v226 = sqlite3VarintLen(v204, 1024, v13, v209);
              v225 = v226 + v204;
              v227 = v226;
              v231 = sqlite3VarintLen(v225, v228, v229, v230);
              v209 = (int *)v672;
              if ( v227 < v231 )
                ++v225;
            }
            else
            {
              v225 = v204 + 1;
            }
            v232 = v225 + v668;
            if ( v232 + v206 <= *(int *)(v224 + 32) )
            {
              *(_QWORD *)(v224 + 8) = *(_QWORD *)(v224 + 40);
LABEL_469:
              *(_DWORD *)(v224 + 16) = v232;
              *(_WORD *)(v224 + 20) = 16;
              if ( v206 )
              {
                *(_DWORD *)v224 = v206;
                *(_WORD *)(v224 + 20) = 1040;
              }
              v233 = *(_BYTE **)(v224 + 8);
              v234 = &v233[v225];
              if ( v225 >= 128 )
              {
                v236 = sqlite3PutVarint(v233, v225, v13, v209);
                v209 = (int *)v672;
                v235 = &v233[v236];
              }
              else
              {
                *v233 = v225;
                v235 = v233 + 1;
              }
              v237 = v669;
              while ( 1 )
              {
                IsValidNN = (unsigned int)v209[9];
                if ( (unsigned int)IsValidNN > 7 )
                {
                  if ( (unsigned int)IsValidNN >= 0x80 )
                  {
                    v242 = sqlite3PutVarint(v235, (unsigned int)v209[9], v13, v209);
                    v209 = (int *)v672;
                    v235 += v242;
                    IsValidNN = *((int *)v672 + 4);
                    if ( !(_DWORD)IsValidNN )
                      goto LABEL_494;
LABEL_493:
                    memcpy_0(v234, *((const void **)v209 + 1), IsValidNN);
                    v209 = (int *)v672;
                    IsValidNN = *((int *)v672 + 4);
                    v234 += IsValidNN;
                    goto LABEL_494;
                  }
                  *v235++ = IsValidNN;
                  if ( (unsigned int)IsValidNN >= 0xE )
                  {
                    IsValidNN = v209[4];
                    if ( (int)IsValidNN > 0 )
                      goto LABEL_493;
                  }
                }
                else
                {
                  *v235++ = IsValidNN;
                  if ( (_DWORD)IsValidNN )
                  {
                    v238 = *(_QWORD *)v209;
                    v239 = *((unsigned __int8 *)qword_1800AE060 + IsValidNN);
                    IsValidNN = (unsigned int)*((unsigned __int8 *)qword_1800AE060 + IsValidNN) - 1;
                    if ( (_DWORD)IsValidNN )
                    {
                      IsValidNN = (unsigned int)(IsValidNN - 1);
                      if ( (_DWORD)IsValidNN )
                      {
                        IsValidNN = (unsigned int)(IsValidNN - 1);
                        if ( (_DWORD)IsValidNN )
                        {
                          IsValidNN = (unsigned int)(IsValidNN - 1);
                          if ( (_DWORD)IsValidNN )
                          {
                            if ( (_DWORD)IsValidNN != 2 )
                            {
                              v234[7] = v238;
                              v240 = v238 >> 8;
                              v234[6] = v240;
                              v238 = v240 >> 8;
                            }
                            v234[5] = v238;
                            v241 = v238 >> 8;
                            v234[4] = v241;
                            v238 = v241 >> 8;
                          }
                          v234[3] = v238;
                          v238 >>= 8;
                        }
                        v234[2] = v238;
                        v238 >>= 8;
                      }
                      v234[1] = v238;
                      v238 >>= 8;
                    }
                    *v234 = v238;
                    v234 += v239;
                  }
                }
LABEL_494:
                if ( v209 == v237 )
                {
                  v2 = a1;
                  updated = Table;
                  goto LABEL_48;
                }
                v209 += 14;
                v672 = (__int64 *)v209;
              }
            }
            if ( v232 + v206 > *(int *)(v670 + 136) )
            {
              v5 = v670;
LABEL_1193:
              v2 = a1;
              goto LABEL_1194;
            }
            if ( !(unsigned int)sqlite3VdbeMemClearAndResize(v224, (unsigned int)v232, v13, v209) )
            {
              v209 = (int *)v672;
              goto LABEL_469;
            }
LABEL_88:
            v5 = v670;
            goto LABEL_89;
          }
          break;
        }
        if ( (v215 & 0x24) != 0 )
        {
          v13 = *(_QWORD *)v213;
          v216 = *(_QWORD *)v213;
          if ( *(__int64 *)v213 < 0 )
            v216 = ~v216;
          ++v204;
          if ( v216 > 0x7F )
          {
            if ( v216 > 0x7FFF )
            {
              if ( v216 > 0x7FFFFF )
              {
                if ( v216 > 0x7FFFFFFF )
                {
                  if ( v216 > 0x7FFFFFFFFFFFLL )
                  {
                    v202 += 8;
                    v668 = v202;
                    if ( (v215 & 0x20) != 0 )
                    {
                      v1 = 0;
                      v217 = 7;
                      *((_WORD *)v213 + 10) = v215 & 0xFFD7 | 8;
                      *(double *)v213 = (double)(int)v13;
                    }
                    else
                    {
                      v217 = 6;
                    }
                  }
                  else
                  {
                    v202 += 6;
                    v217 = 5;
                    v668 = v202;
                  }
                }
                else
                {
                  v202 += 4;
                  v217 = 4;
                  v668 = v202;
                }
              }
              else
              {
                v202 += 3;
                v217 = 3;
                v668 = v202;
              }
            }
            else
            {
              v202 += 2;
              v217 = 2;
              v668 = v202;
            }
            v219 = 36;
            v218 = (__int64)v213;
          }
          else
          {
            if ( (*(_QWORD *)v213 & 1LL) == v13 && *((_BYTE *)a1 + 197) >= 4u )
            {
              v217 = v216 + 8;
            }
            else
            {
              ++v202;
              v217 = 1;
              v668 = v202;
            }
            v218 = 36;
            v219 = (__int64)v213;
          }
          *(_DWORD *)(v219 + v218) = v217;
        }
        else
        {
          if ( (v215 & 8) != 0 )
          {
            ++v204;
            v213[9] = 7;
            v202 += 8;
            v668 = v202;
            goto LABEL_458;
          }
          v220 = v213[4];
          v221 = ((v215 & 2 | 0x18u) >> 1) + 2 * v220;
          if ( (v215 & 0x400) != 0 )
          {
            v222 = *v213;
            v221 += 2 * v222;
            if ( v668 )
            {
              if ( (unsigned int)sqlite3VdbeMemExpandBlob(v213, 1024, v13) )
                goto LABEL_88;
              v220 += *v213;
            }
            else
            {
              v206 += v222;
            }
          }
          v202 = v220 + v668;
          v668 = v202;
          v223 = sqlite3VarintLen(v221, v214, v13, v209);
          v209 = (int *)v672;
          v204 += v223;
          v213[9] = v221;
        }
        v214 = 1024;
        goto LABEL_458;
      case 0x62u:
        v37 = *((_DWORD *)i + 3) == 0;
        v243 = *((int *)i + 1);
        v244 = v2[15];
        v668 = 0;
        v245 = *(_QWORD *)(v244 + 8 * v243);
        if ( v37 )
        {
          Table = sqlite3BtreeCount(v5, *(_QWORD *)(v245 + 48), &v668);
          updated = Table;
          if ( Table )
            goto LABEL_309;
        }
        else
        {
          v668 = sqlite3BtreeRowCountEst(*(_QWORD *)(v245 + 48));
        }
        v247 = (__int64 *)out2Prerelease(v2, i, v246);
        *v247 = v668;
        goto LABEL_880;
      case 0x63u:
        v270 = *(_QWORD *)(v5 + 32);
        v271 = *((unsigned int *)i + 3);
        v272 = 32LL * *((int *)i + 1);
        LODWORD(v672) = 0;
        sqlite3BtreeGetMeta(*(_QWORD *)(v272 + v270 + 8), v271, &v672);
        IsValidNN = out2Prerelease(v2, i, v273);
        *(_QWORD *)IsValidNN = (int)v672;
        goto LABEL_27;
      case 0x64u:
        v274 = *(_QWORD *)(v5 + 32);
        v275 = 32LL * *((int *)i + 1);
        updated = sqlite3BtreeUpdateMeta(
                    *(_QWORD *)(v275 + v274 + 8),
                    *((unsigned int *)i + 2),
                    *((unsigned int *)i + 3));
        Table = updated;
        IsValidNN = *((unsigned int *)i + 2);
        if ( (_DWORD)IsValidNN == 1 )
        {
          **(_DWORD **)(v275 + v274 + 24) = *((_DWORD *)i + 3) - *((unsigned __int16 *)i + 1);
          *(_DWORD *)(v5 + 44) |= 1u;
          IsValidNN = sqlite3FkClearTriggerCache(v5, *((unsigned int *)i + 1));
        }
        else if ( (_DWORD)IsValidNN == 2 )
        {
          IsValidNN = i[12];
          *(_BYTE *)(*(_QWORD *)(v275 + v274 + 24) + 112LL) = IsValidNN;
        }
        if ( *((_DWORD *)i + 1) != 1 )
          goto LABEL_576;
        IsValidNN = sqlite3ExpirePreparedStatements(v5, 0, v276);
        goto LABEL_575;
      case 0x65u:
        v277 = *(_QWORD *)(v2[15] + 8LL * *((int *)i + 1));
        if ( !v277 || *(_DWORD *)(v277 + 68) != *((_DWORD *)i + 2) )
          goto LABEL_1145;
        v278 = *(_QWORD *)(v277 + 48);
        sqlite3_free(*(_QWORD *)(v278 + 24));
        *(_QWORD *)(v278 + 24) = 0;
        *(_BYTE *)v278 = 1;
        goto LABEL_1158;
      case 0x66u:
      case 0x67u:
      case 0x68u:
      case 0x69u:
        v88 = v6 + 56LL * *((int *)i + 1);
        v89 = v6 + 56LL * *((int *)i + 2);
        v90 = 56LL * *((int *)i + 3) + v6;
        if ( ((*(_BYTE *)(v88 + 20) | *(_BYTE *)(v89 + 20)) & 1) != 0 )
        {
          v91 = v90;
          goto LABEL_153;
        }
        v92 = sqlite3VdbeIntValue(v89, v89, v13);
        v95 = sqlite3VdbeIntValue(v88, v93, v94);
        v96 = *i;
        v97 = v95;
        if ( *i == 102 )
        {
          v92 &= v95;
          goto LABEL_172;
        }
        if ( v96 == 103 )
        {
          v92 |= v95;
          goto LABEL_172;
        }
        if ( !v95 )
          goto LABEL_172;
        if ( v95 >= 0 )
          goto LABEL_162;
        v96 = -47 - v96;
        if ( v95 <= -64 )
          goto LABEL_164;
        v97 = -v95;
LABEL_162:
        if ( v97 < 64 )
        {
          if ( v96 == 104 )
          {
            v92 <<= v97;
          }
          else if ( v92 >= 0 )
          {
            v92 = (unsigned __int64)v92 >> v97;
          }
          else
          {
            v92 = ((unsigned __int64)v92 >> v97) | (-1LL << (64 - (unsigned __int8)v97));
          }
        }
        else
        {
LABEL_164:
          if ( v92 >= 0 || v96 == 104 )
            v92 = 0;
          else
            v92 = -1;
        }
LABEL_172:
        IsValidNN = 62020;
        *(_QWORD *)v90 = v92;
        *(_WORD *)(v90 + 20) &= 0xF244u;
        *(_WORD *)(v90 + 20) |= 4u;
        goto LABEL_48;
      case 0x6Au:
      case 0x6Bu:
      case 0x6Cu:
      case 0x6Du:
      case 0x6Eu:
        v63 = v6 + 56LL * *((int *)i + 1);
        v64 = 56LL * *((int *)i + 3);
        v65 = 56LL * *((int *)i + 2) + v6;
        v679 = 0;
        v66 = *(_WORD *)(v63 + 20);
        v67 = v673 + v64;
        v68 = *(_WORD *)(v65 + 20);
        if ( ((unsigned __int8)v66 & (unsigned __int8)v68 & 4) != 0 )
          goto LABEL_113;
        if ( (((unsigned __int8)v66 | (unsigned __int8)v68) & 1) != 0 )
          goto LABEL_145;
        v69 = numericType(v63);
        if ( (v69 & (unsigned __int8)numericType(v65) & 4) == 0 )
          goto LABEL_126;
        v8 = v660;
LABEL_113:
        v72 = *i;
        v70 = *(_QWORD *)v65;
        v71 = *(_QWORD *)v63;
        v679 = *(_QWORD *)v65;
        v73 = v72 - 106;
        if ( v73 )
        {
          v74 = v73 - 1;
          if ( v74 )
          {
            v75 = v74 - 1;
            if ( v75 )
            {
              if ( v75 != 1 )
              {
                if ( !v71 )
                  goto LABEL_145;
                v76 = v70;
                if ( v71 == -1 )
                  v71 = 1;
                v679 = v76 % v71;
                goto LABEL_138;
              }
              if ( !v71 )
                goto LABEL_145;
              if ( v71 != -1 || v70 != 0x8000000000000000uLL )
              {
                v679 = v70 / v71;
LABEL_138:
                *(_QWORD *)v67 = v679;
                IsValidNN = *(unsigned __int16 *)(v67 + 20);
                LOWORD(IsValidNN) = IsValidNN & 0xF240 | 4;
                goto LABEL_148;
              }
            }
            else if ( !(unsigned int)sqlite3MulInt64(&v679, v71) )
            {
              goto LABEL_137;
            }
          }
          else if ( !(unsigned int)sqlite3SubInt64(&v679, v71) )
          {
            goto LABEL_137;
          }
        }
        else if ( !(unsigned int)sqlite3AddInt64(&v679, v71) )
        {
LABEL_137:
          v8 = v660;
          goto LABEL_138;
        }
LABEL_126:
        v77 = sqlite3VdbeRealValue(v63, v70, v71);
        *(double *)&v1 = sqlite3VdbeRealValue(v65, v78, v79);
        *((_QWORD *)&v82 + 1) = *((_QWORD *)&v1 + 1);
        switch ( *i )
        {
          case 'j':
            v87 = *(double *)&v1 + v77;
            break;
          case 'k':
            v87 = *(double *)&v1 - v77;
            break;
          case 'l':
            v87 = *(double *)&v1 * v77;
            break;
          case 'm':
            if ( v77 == 0.0 )
              goto LABEL_145;
            v87 = *(double *)&v1 / v77;
            break;
          default:
            v83 = sqlite3VdbeIntValue(v63, v80, v81);
            v86 = sqlite3VdbeIntValue(v65, v84, v85);
            v679 = v86;
            if ( !v83 )
              goto LABEL_145;
            v82 = 0;
            if ( v83 == -1 )
              v83 = 1;
            v87 = (double)(int)(v86 % v83);
            break;
        }
        *((_QWORD *)&v1 + 1) = *((_QWORD *)&v82 + 1);
        if ( (unsigned int)sqlite3IsNaN() )
        {
LABEL_145:
          IsValidNN = sqlite3VdbeMemSetNull(v67);
          goto LABEL_146;
        }
        IsValidNN = *(unsigned __int16 *)(v67 + 20);
        v8 = v660;
        LOWORD(IsValidNN) = IsValidNN & 0xF240 | 8;
        *(double *)v67 = v87;
LABEL_148:
        v7 = v664;
        *(_WORD *)(v67 + 20) = IsValidNN;
        updated = Table;
        goto LABEL_106;
      case 0x6Fu:
        v57 = v6 + 56LL * *((int *)i + 1);
        v58 = *(_WORD *)(v57 + 20);
        v59 = v6 + 56LL * *((int *)i + 2);
        v60 = 56LL * *((int *)i + 3) + v6;
        if ( ((*(_BYTE *)(v59 + 20) | (unsigned __int8)v58) & 1) != 0 )
        {
          IsValidNN = sqlite3VdbeMemSetNull(v60);
          v2 = a1;
          goto LABEL_27;
        }
        if ( (v58 & 0x12) == 0 )
        {
          if ( (unsigned int)sqlite3VdbeMemStringify(v57, v8, 0) )
            goto LABEL_88;
LABEL_85:
          v8 = v660;
          v58 = *(_WORD *)(v57 + 20) & 0xFFFD;
          goto LABEL_91;
        }
        if ( (v58 & 0x400) != 0 )
        {
          if ( (unsigned int)sqlite3VdbeMemExpandBlob(v57, v7, v13) )
            goto LABEL_88;
          goto LABEL_85;
        }
LABEL_91:
        v61 = *(_WORD *)(v59 + 20);
        if ( (v61 & 0x12) != 0 )
        {
          if ( (v61 & 0x400) == 0 )
            goto LABEL_97;
          if ( (unsigned int)sqlite3VdbeMemExpandBlob(v59, v7, v13) )
            goto LABEL_88;
        }
        else if ( (unsigned int)sqlite3VdbeMemStringify(v59, v8, 0) )
        {
          goto LABEL_88;
        }
        v61 = *(_WORD *)(v59 + 20) & 0xFFFD;
LABEL_97:
        LODWORD(v62) = *(_DWORD *)(v59 + 16) + *(_DWORD *)(v57 + 16);
        if ( (int)v62 > *(_DWORD *)(v670 + 136) )
        {
          v5 = v670;
          goto LABEL_1193;
        }
        if ( (unsigned int)sqlite3VdbeMemGrow(v60, (unsigned int)(v62 + 2), v60 == v59) )
          goto LABEL_88;
        v62 = (int)v62;
        *(_WORD *)(v60 + 20) &= 0xF242u;
        *(_WORD *)(v60 + 20) |= 2u;
        if ( v60 != v59 )
        {
          memcpy_0(*(void **)(v60 + 8), *(const void **)(v59 + 8), *(int *)(v59 + 16));
          *(_WORD *)(v59 + 20) = v61;
        }
        memcpy_0((void *)(*(_QWORD *)(v60 + 8) + *(int *)(v59 + 16)), *(const void **)(v57 + 8), *(int *)(v57 + 16));
        v8 = v660;
        *(_WORD *)(v57 + 20) = v58;
        if ( (unsigned __int8)v660 > 1u )
          v62 = (int)v62 & 0xFFFFFFFFFFFFFFFEuLL;
        *(_BYTE *)(v62 + *(_QWORD *)(v60 + 8)) = 0;
        *(_BYTE *)(*(_QWORD *)(v60 + 8) + v62 + 1) = 0;
        IsValidNN = 512;
        *(_WORD *)(v60 + 20) |= 0x200u;
        *(_DWORD *)(v60 + 16) = v62;
        *(_BYTE *)(v60 + 22) = v660;
LABEL_104:
        v2 = a1;
        updated = Table;
LABEL_105:
        v7 = v664;
LABEL_106:
        v13 = v661;
LABEL_107:
        v3 = v666;
        goto LABEL_108;
      case 0x70u:
        goto LABEL_1145;
      case 0x72u:
        v139 = v6 + 56LL * *((int *)i + 1);
        v140 = v6 + 56LL * *((int *)i + 2);
        IsValidNN = sqlite3VdbeMemSetNull(v140);
        if ( (*(_BYTE *)(v139 + 20) & 1) == 0 )
        {
          *(_WORD *)(v140 + 20) = 4;
          IsValidNN = ~sqlite3VdbeIntValue(v139, v141, v142);
          *(_QWORD *)v140 = IsValidNN;
        }
        goto LABEL_48;
      case 0x73u:
        v279 = *(_QWORD *)(v2[15] + 8LL * *((int *)i + 2));
        v280 = allocateCursor(v2, *((unsigned int *)i + 1), (unsigned int)*(__int16 *)(v279 + 72), 0);
        if ( !v280 )
          goto LABEL_90;
        *(_DWORD *)(v280 + 8) |= 1u;
        *(_BYTE *)(v280 + 2) = 1;
        *(_QWORD *)(v280 + 56) = *(_QWORD *)(v279 + 56);
        *(_BYTE *)(v280 + 4) = *(_BYTE *)(v279 + 4);
        *(_DWORD *)(v280 + 68) = *(_DWORD *)(v279 + 68);
        v281 = *(_DWORD *)(v280 + 8) ^ (*(_DWORD *)(v279 + 8) ^ *(_DWORD *)(v280 + 8)) & 4;
        *(_DWORD *)(v280 + 8) = v281;
        *(_QWORD *)(v280 + 16) = *(_QWORD *)(v279 + 16);
        *(_DWORD *)(v280 + 8) = v281 | 8;
        *(_DWORD *)(v279 + 8) |= 8u;
        IsValidNN = sqlite3BtreeCursor(
                      *(_QWORD *)(v280 + 16),
                      *(_DWORD *)(v280 + 68),
                      4,
                      *(_QWORD *)(v280 + 56),
                      *(_QWORD *)(v280 + 48));
        updated = IsValidNN;
        Table = IsValidNN;
        goto LABEL_27;
      case 0x74u:
        goto LABEL_1125;
      case 0x75u:
        v28 = out2Prerelease(v2, i, v13);
        v31 = sqlite3Strlen30(*((_QWORD *)i + 2), v29, v30);
        *((_DWORD *)i + 1) = v31;
        if ( (_BYTE)v660 == 1 )
          goto LABEL_38;
        LOBYTE(v32) = 1;
        Table = sqlite3VdbeMemSetStr(v28, *((_QWORD *)i + 2), -1, v32, 0);
        updated = Table;
        if ( Table )
          goto LABEL_1194;
        if ( (unsigned int)sqlite3VdbeChangeEncoding(v28, (unsigned __int8)v660, v33) )
          goto LABEL_90;
        *(_DWORD *)(v28 + 32) = 0;
        *(_WORD *)(v28 + 20) |= 0x2000u;
        if ( i[1] == 0xFA )
          sqlite3DbFree(v5, *((_QWORD *)i + 2));
        i[1] = -6;
        *((_QWORD *)i + 2) = *(_QWORD *)(v28 + 8);
        v31 = *(_DWORD *)(v28 + 16);
        *((_DWORD *)i + 1) = v31;
LABEL_38:
        if ( v31 > *(_DWORD *)(v5 + 136) )
          goto LABEL_1194;
        *i = 73;
LABEL_40:
        v34 = out2Prerelease(v2, i, v13);
        v8 = v660;
        v35 = v34;
        *(_WORD *)(v34 + 20) = 8706;
        *(_QWORD *)(v34 + 8) = *((_QWORD *)i + 2);
        *(_DWORD *)(v34 + 16) = *((_DWORD *)i + 1);
        *(_BYTE *)(v34 + 22) = v660;
        IsValidNN = *((int *)i + 3);
        if ( (int)IsValidNN <= 0 )
          goto LABEL_57;
        v36 = 56 * IsValidNN;
        IsValidNN = *((unsigned __int16 *)i + 1);
        v37 = *(_QWORD *)(v36 + v6) == IsValidNN;
        v7 = v664;
        if ( v37 )
          *(_WORD *)(v35 + 20) = 8720;
        v13 = v661;
        goto LABEL_108;
      case 0x77u:
        LOBYTE(v9) = 1;
        v282 = allocateCursor(v2, *((unsigned int *)i + 1), *((unsigned int *)i + 2), v9);
        if ( !v282 )
          goto LABEL_90;
        *(_QWORD *)(v282 + 56) = *((_QWORD *)i + 2);
        IsValidNN = sqlite3VdbeSorterInit(v5, *((unsigned int *)i + 3), v282);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( !(_DWORD)IsValidNN )
          goto LABEL_27;
        goto LABEL_309;
      case 0x78u:
        v283 = *(_QWORD *)(v2[15] + 8LL * *((int *)i + 1));
        v284 = *(_QWORD *)(v283 + 24);
        IsValidNN = v284 + 1;
        *(_QWORD *)(v283 + 24) = v284 + 1;
        v7 = v664;
        if ( v284 )
          goto LABEL_108;
        goto LABEL_249;
      case 0x79u:
        LOBYTE(v9) = 3;
        IsValidNN = allocateCursor(v2, *((unsigned int *)i + 1), *((unsigned int *)i + 3), v9);
        if ( !IsValidNN )
          goto LABEL_90;
        *(_BYTE *)(IsValidNN + 2) = 1;
        *(_DWORD *)(IsValidNN + 36) = *((_DWORD *)i + 2);
        *(_QWORD *)(IsValidNN + 48) = &dword_1800C79C4;
        *(_BYTE *)(IsValidNN + 4) = 1;
        goto LABEL_27;
      case 0x7Au:
        sqlite3VdbeFreeCursor(v2, *(_QWORD *)(v2[15] + 8LL * *((int *)i + 1)), v13);
        IsValidNN = v2[15];
        *(_QWORD *)(IsValidNN + 8LL * *((int *)i + 1)) = 0;
        goto LABEL_27;
      case 0x7Cu:
        v303 = *((int *)i + 7);
        *(_QWORD *)&v676 = 0;
        v1 = 0;
        v304 = v2[15];
        LODWORD(v669) = 0;
        v674 = 0;
        v675 = 0;
        v305 = *(_QWORD *)(v304 + 8 * v303);
        IsValidNN = sqlite3BtreeCursorIsValidNN(*(_QWORD *)(v305 + 48), v7, v13);
        if ( !(_DWORD)IsValidNN )
          goto LABEL_27;
        v306 = *((_DWORD *)i + 1);
        *(_QWORD *)&v674 = *(_QWORD *)(v305 + 56);
        WORD6(v675) = *((_WORD *)i + 20);
        v307 = *((int *)i + 9);
        BYTE14(v675) = 0;
        *((_QWORD *)&v674 + 1) = v6 + 56 * v307;
        LODWORD(v669) = 0;
        while ( 2 )
        {
          Table = sqlite3VdbeIdxKeyCompare(v5, v305, &v674, &v669);
          updated = Table;
          if ( Table )
            goto LABEL_309;
          IsValidNN = (unsigned int)v669;
          v309 = (int)v669 < 0;
          if ( (int)v669 <= 0 )
            goto LABEL_638;
          if ( !*((_WORD *)i + 1) )
            goto LABEL_644;
          v309 = (int)v669 < 0;
LABEL_638:
          if ( !v309 )
            goto LABEL_622;
          if ( v306 <= 0 )
            goto LABEL_48;
          v310 = *(_QWORD *)(v305 + 48);
          *(_DWORD *)(v305 + 32) = 0;
          v311 = sqlite3BtreeNext(v310, 0, v308);
          updated = v311;
          if ( !v311 )
          {
            --v306;
            continue;
          }
          break;
        }
        if ( v311 != 101 )
          goto LABEL_309;
        updated = 0;
        Table = 0;
LABEL_644:
        i += 24;
        goto LABEL_622;
      case 0x7Du:
        IsValidNN = v2[15];
        v312 = *((_DWORD *)i + 2);
        v313 = *(_QWORD *)(IsValidNN + 8LL * *((int *)i + 1));
        v314 = *(unsigned __int16 *)(v313 + 12);
        if ( v314 >= v312 )
        {
          IsValidNN = *((unsigned int *)i + 3);
          v13 = v661;
          if ( v314 > (int)IsValidNN )
            *(_WORD *)(v313 + 12) = IsValidNN;
          v7 = v664;
        }
        else
        {
          *(_WORD *)(v313 + 12) = v312;
          v7 = v664;
          v13 = v661;
        }
        goto LABEL_108;
      case 0x7Eu:
        *(_QWORD *)out2Prerelease(v2, i, v13) = *(_QWORD *)(*(_QWORD *)(v2[15] + 8LL * *((int *)i + 1)) + 24LL);
        IsValidNN = v2[15];
        v331 = *(_QWORD *)(IsValidNN + 8LL * *((int *)i + 1));
        ++*(_QWORD *)(v331 + 24);
        goto LABEL_27;
      case 0x7Fu:
        v668 = 0;
        LODWORD(v669) = 0;
        v332 = out2Prerelease(v2, i, v13);
        v334 = *((int *)i + 1);
        v335 = (_QWORD *)v332;
        v336 = *(_QWORD *)(v2[15] + 8 * v334);
        if ( (*(_BYTE *)(v336 + 8) & 2) != 0 )
          goto LABEL_690;
        Table = sqlite3BtreeLast(*(_QWORD *)(v336 + 48), &v669, v333);
        updated = Table;
        if ( Table )
          goto LABEL_309;
        if ( (_DWORD)v669 )
        {
          v668 = 1;
        }
        else
        {
          v337 = *(_QWORD *)(v336 + 48);
          getCellInfo(v337, v334, v333);
          v338 = *(_QWORD *)(v337 + 48);
          v668 = v338;
          if ( v338 == 0x7FFFFFFFFFFFFFFFLL )
            *(_DWORD *)(v336 + 8) |= 2u;
          else
            v668 = v338 + 1;
        }
LABEL_690:
        v339 = *((int *)i + 3);
        if ( !(_DWORD)v339 )
          goto LABEL_701;
        v340 = v2[33];
        if ( v340 )
        {
          for ( ; *(_QWORD *)(v340 + 8); v340 = *(_QWORD *)(v340 + 8) )
            ;
          v341 = *(_QWORD *)(v340 + 24) + 56LL * *((int *)i + 3);
        }
        else
        {
          v341 = v673 + 56 * v339;
        }
        v342 = sqlite3VdbeIntValue(v341, v334, v333);
        *(_QWORD *)v341 = v342;
        *(_WORD *)(v341 + 20) &= 0xF244u;
        *(_WORD *)(v341 + 20) |= 4u;
        if ( v342 == 0x7FFFFFFFFFFFFFFFLL || (*(_BYTE *)(v336 + 8) & 2) != 0 )
          goto LABEL_706;
        v343 = v342 + 1;
        v344 = v668;
        if ( v668 < v343 )
        {
          v344 = v343;
          v668 = v343;
        }
        *(_QWORD *)v341 = v344;
LABEL_701:
        if ( (*(_BYTE *)(v336 + 8) & 2) == 0 )
          goto LABEL_707;
        v345 = 0;
        while ( 2 )
        {
          sqlite3_randomness(8, &v668);
          v668 = (v668 & 0x3FFFFFFFFFFFFFFFLL) + 1;
          Table = sqlite3BtreeTableMoveto(*(_QWORD *)(v336 + 48), v668, 0, &v669);
          updated = Table;
          if ( Table )
            goto LABEL_309;
          if ( !(_DWORD)v669 )
          {
            if ( ++v345 >= 100 )
            {
LABEL_706:
              updated = 13;
              goto LABEL_309;
            }
            continue;
          }
          break;
        }
LABEL_707:
        v7 = v664;
        *(_BYTE *)(v336 + 3) = 0;
        *(_DWORD *)(v336 + 32) = 0;
        IsValidNN = v668;
        *v335 = v668;
        goto LABEL_49;
      case 0x80u:
        v1 = 0;
        v346 = *((int *)i + 1);
        v347 = v673;
        v348 = 56LL * *((int *)i + 2);
        v674 = 0;
        v675 = 0;
        v349 = v2[15];
        v676 = 0;
        v350 = *(_QWORD *)(v349 + 8 * v346);
        v37 = i[1] == 0xFB;
        v351 = *(_QWORD *)(56LL * *((int *)i + 3) + v673);
        *((_QWORD *)&v674 + 1) = v351;
        if ( v37 && *(_QWORD *)(v5 + 320) )
        {
          v352 = (_QWORD *)*((_QWORD *)i + 2);
          v353 = *(_QWORD *)(32LL * *(char *)(v350 + 1) + *(_QWORD *)(v5 + 32));
        }
        else
        {
          v352 = 0;
          v353 = 0;
        }
        if ( (i[2] & 1) != 0 )
        {
          ++v2[7];
          if ( (i[2] & 0x20) != 0 )
            *(_QWORD *)(v5 + 56) = v351;
        }
        v354 = *((_WORD *)i + 1);
        *(_QWORD *)&v675 = *(_QWORD *)(v348 + v347 + 8);
        DWORD1(v676) = *(_DWORD *)(v348 + v347 + 16);
        if ( (v354 & 0x10) != 0 )
          v355 = *(unsigned int *)(v350 + 36);
        else
          v355 = 0;
        if ( (*(_WORD *)(v348 + v347 + 20) & 0x400) != 0 )
          DWORD2(v676) = *(_DWORD *)(v348 + v347);
        else
          DWORD2(v676) = 0;
        *(_QWORD *)&v674 = 0;
        IsValidNN = sqlite3BtreeInsert(*(_QWORD *)(v350 + 48), &v674, (unsigned __int8)v354 & 0x8A, v355);
        Table = IsValidNN;
        updated = IsValidNN;
        *(_BYTE *)(v350 + 3) = 0;
        *(_DWORD *)(v350 + 32) = 0;
        if ( (_DWORD)IsValidNN )
          goto LABEL_309;
        ++v677;
        if ( v352 )
        {
          v356 = 23;
          if ( (i[2] & 4) == 0 )
            v356 = 18;
          IsValidNN = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _QWORD))(v5 + 320))(
                        *(_QWORD *)(v5 + 312),
                        v356,
                        v353,
                        *v352,
                        *((_QWORD *)&v674 + 1));
        }
        goto LABEL_48;
      case 0x81u:
        v357 = *((int *)i + 3);
        if ( (_DWORD)v357 )
          v358 = *(_QWORD *)(56 * v357 + v6);
        else
          v358 = 0;
        IsValidNN = sqlite3BtreeTransferRow(
                      *(_QWORD *)(*(_QWORD *)(v2[15] + 8LL * *((int *)i + 1)) + 48LL),
                      *(_QWORD *)(*(_QWORD *)(v2[15] + 8LL * *((int *)i + 2)) + 48LL),
                      v358);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( !(_DWORD)IsValidNN )
          goto LABEL_27;
        goto LABEL_309;
      case 0x82u:
        v359 = *((_DWORD *)i + 2);
        v360 = *(_QWORD *)(a1[15] + 8LL * *((int *)i + 1));
        if ( i[1] == 0xFB && *(_QWORD *)(v5 + 320) )
        {
          v361 = *((_QWORD *)i + 2);
          v362 = *(_QWORD *)(32LL * *(char *)(v360 + 1) + *(_QWORD *)(v5 + 32));
          if ( (i[2] & 2) != 0 && *(_BYTE *)(v360 + 4) )
          {
            v363 = *(_QWORD *)(v360 + 48);
            getCellInfo(v363, v7, v13);
            *(_QWORD *)(v360 + 80) = *(_QWORD *)(v363 + 48);
          }
        }
        else
        {
          v362 = 0;
          v361 = 0;
        }
        IsValidNN = sqlite3BtreeDelete(*(_QWORD *)(v360 + 48), i[2]);
        Table = IsValidNN;
        *(_QWORD *)(v360 + 32) = 0;
        if ( (_DWORD)IsValidNN )
        {
          v2 = a1;
          updated = IsValidNN;
          goto LABEL_309;
        }
        ++v677;
        v37 = (v359 & 1) == 0;
        v2 = a1;
        if ( !v37 && (++a1[7], (IsValidNN = *(_QWORD *)(v5 + 320)) != 0) && v361 && *(char *)(v361 + 48) >= 0 )
        {
          IsValidNN = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, _QWORD, _QWORD))IsValidNN)(
                        *(_QWORD *)(v5 + 312),
                        9,
                        v362,
                        *(_QWORD *)v361,
                        *(_QWORD *)(v360 + 80));
          updated = 0;
        }
        else
        {
LABEL_146:
          updated = Table;
        }
        goto LABEL_48;
      case 0x83u:
        IsValidNN = v2[7];
        *(_QWORD *)(v5 + 128) += IsValidNN;
        *(_QWORD *)(v5 + 120) = IsValidNN;
        v2[7] = 0;
        goto LABEL_108;
      case 0x84u:
        v364 = v2[15];
        v365 = *((unsigned int *)i + 4);
        v366 = 56LL * *((int *)i + 3);
        v367 = *((int *)i + 1);
        LODWORD(v672) = 0;
        IsValidNN = sqlite3VdbeSorterCompare(*(_QWORD *)(v364 + 8 * v367), v6 + v366, v365, &v672);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( (_DWORD)IsValidNN )
          goto LABEL_309;
        v7 = v664;
        v13 = v661;
        v8 = v660;
        if ( !(_DWORD)v672 )
          goto LABEL_108;
        goto LABEL_249;
      case 0x85u:
        Table = sqlite3VdbeSorterRowkey(*(_QWORD *)(v2[15] + 8LL * *((int *)i + 1)), v6 + 56LL * *((int *)i + 2), v13);
        updated = Table;
        if ( Table )
          goto LABEL_309;
        IsValidNN = v2[15];
        *(_DWORD *)(*(_QWORD *)(IsValidNN + 8LL * *((int *)i + 3)) + 32LL) = 0;
        goto LABEL_27;
      case 0x86u:
        v368 = out2Prerelease(v2, i, v13);
        v369 = *(_QWORD *)(v2[15] + 8LL * *((int *)i + 1));
        v370 = *(_QWORD *)(v369 + 48);
        getCellInfo(v370, v369, v371);
        v372 = *(unsigned int *)(v370 + 64);
        if ( (unsigned int)v372 > *(_DWORD *)(v5 + 136) )
          goto LABEL_1194;
        IsValidNN = sqlite3VdbeMemFromBtreeZeroOffset(v370, v372, v368);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( (_DWORD)IsValidNN )
          goto LABEL_309;
        if ( *((_DWORD *)i + 3) )
          goto LABEL_48;
        IsValidNN = 0x4000;
        if ( (*(_WORD *)(v368 + 20) & 0x4000) == 0 )
          goto LABEL_48;
        IsValidNN = sqlite3VdbeMemMakeWriteable(v368);
        if ( !(_DWORD)IsValidNN )
          goto LABEL_48;
        goto LABEL_90;
      case 0x87u:
        v668 = 0;
        IsValidNN = out2Prerelease(v2, i, v13);
        v374 = *((int *)i + 1);
        v375 = IsValidNN;
        v376 = v2[15];
        v377 = *(_QWORD *)(v376 + 8 * v374);
        if ( *(_BYTE *)(v377 + 2) )
        {
          v7 = v664;
          *(_WORD *)(IsValidNN + 20) = 1;
          goto LABEL_49;
        }
        if ( *(_BYTE *)(v377 + 3) )
        {
          IsValidNN = *(_QWORD *)(v377 + 80);
        }
        else if ( *(_BYTE *)v377 == 2 )
        {
          v378 = *(__int64 **)(v377 + 48);
          v379 = *v378;
          Table = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*(_QWORD *)*v378 + 96LL))(v378, &v668);
          updated = Table;
          sqlite3VtabImportErrmsg(v2, v379);
          if ( Table )
            goto LABEL_309;
          IsValidNN = v668;
        }
        else
        {
          IsValidNN = sqlite3VdbeCursorRestore(*(_QWORD *)(v376 + 8 * v374), v374, v373);
          Table = IsValidNN;
          updated = IsValidNN;
          if ( (_DWORD)IsValidNN )
            goto LABEL_309;
          if ( *(_BYTE *)(v377 + 2) )
          {
            v7 = v664;
            *(_WORD *)(v375 + 20) = 1;
            goto LABEL_49;
          }
          v382 = *(_QWORD *)(v377 + 48);
          getCellInfo(v382, v380, v381);
          IsValidNN = *(_QWORD *)(v382 + 48);
        }
        *(_QWORD *)v375 = IsValidNN;
        goto LABEL_48;
      case 0x88u:
        v383 = *((int *)i + 1);
        IsValidNN = *(_QWORD *)(v2[15] + 8 * v383);
        if ( IsValidNN )
          goto LABEL_770;
        LOBYTE(v9) = 3;
        IsValidNN = allocateCursor(v2, v383, 1, v9);
        if ( !IsValidNN )
          goto LABEL_90;
        v13 = v661;
        v8 = v660;
        *(_DWORD *)(IsValidNN + 8) |= 8u;
        *(_DWORD *)(IsValidNN + 36) = 0;
        *(_QWORD *)(IsValidNN + 48) = &dword_1800C79C4;
        *(_BYTE *)(IsValidNN + 4) = 1;
LABEL_770:
        v37 = *(_BYTE *)IsValidNN == 0;
        *(_BYTE *)(IsValidNN + 2) = 1;
        *(_DWORD *)(IsValidNN + 32) = 0;
        if ( !v37 )
        {
LABEL_19:
          v7 = v664;
          goto LABEL_108;
        }
        v384 = *(_QWORD *)(IsValidNN + 48);
        IsValidNN = sqlite3_free(*(_QWORD *)(v384 + 24));
        *(_QWORD *)(v384 + 24) = 0;
        *(_BYTE *)v384 = 1;
        goto LABEL_27;
      case 0x8Au:
        v401 = v2[15];
        v1 = 0;
        v402 = *((int *)i + 1);
        v674 = 0;
        v675 = 0;
        v676 = 0;
        v403 = *(_QWORD *)(v401 + 8 * v402);
        v404 = v6 + 56LL * *((int *)i + 2);
        if ( (i[2] & 1) != 0 )
          ++v2[7];
        if ( (*(_WORD *)(v404 + 20) & 0x400) == 0 || (updated = sqlite3VdbeMemExpandBlob(v404, v7, v13)) == 0 )
        {
          v405 = *((_WORD *)i + 1);
          *((_QWORD *)&v674 + 1) = *(int *)(v404 + 16);
          *(_QWORD *)&v674 = *(_QWORD *)(v404 + 8);
          v406 = v6 + 56LL * *((int *)i + 3);
          LOWORD(v676) = *((_WORD *)i + 8);
          *((_QWORD *)&v675 + 1) = v406;
          v407 = (v405 & 0x10) != 0 ? *(unsigned int *)(v403 + 36) : 0LL;
          IsValidNN = sqlite3BtreeInsert(*(_QWORD *)(v403 + 48), &v674, (unsigned __int8)v405 & 0x8A, v407);
          Table = IsValidNN;
          updated = IsValidNN;
          *(_DWORD *)(v403 + 32) = 0;
          if ( !(_DWORD)IsValidNN )
            goto LABEL_48;
        }
        goto LABEL_309;
      case 0x8Bu:
        v408 = *(_QWORD *)(v2[15] + 8LL * *((int *)i + 1));
        v409 = v6 + 56LL * *((int *)i + 2);
        if ( (*(_WORD *)(v409 + 20) & 0x400) == 0
          || (updated = sqlite3VdbeMemExpandBlob(v6 + 56LL * *((int *)i + 2), v7, v13)) == 0 )
        {
          IsValidNN = sqlite3VdbeSorterWrite(v408, v409, v13);
          Table = IsValidNN;
          updated = IsValidNN;
          if ( !(_DWORD)IsValidNN )
            goto LABEL_48;
        }
        goto LABEL_309;
      case 0x8Cu:
        v410 = *((int *)i + 1);
        LODWORD(v672) = 0;
        *(_QWORD *)&v676 = 0;
        v411 = v2[15];
        v1 = 0;
        v674 = 0;
        v675 = 0;
        v412 = *(_QWORD **)(v411 + 8 * v410);
        v413 = v412[6];
        *(_QWORD *)&v674 = v412[7];
        WORD6(v675) = *((_WORD *)i + 6);
        v414 = *((int *)i + 2);
        BYTE14(v675) = 0;
        *((_QWORD *)&v674 + 1) = v6 + 56 * v414;
        Table = sqlite3BtreeIndexMoveto(v413, &v674, &v672);
        updated = Table;
        if ( Table )
          goto LABEL_309;
        if ( (_DWORD)v672 )
        {
          if ( *((_WORD *)i + 1) && !(unsigned int)sqlite3WritableSchema(v5) )
          {
            updated = sqlite3ReportError(779, 99656, "index corruption");
            goto LABEL_309;
          }
        }
        else
        {
          LOBYTE(v415) = 4;
          Table = sqlite3BtreeDelete(v413, v415);
          updated = Table;
          if ( Table )
            goto LABEL_309;
        }
        IsValidNN = 0;
        v412[4] = 0;
        goto LABEL_48;
      case 0x8Du:
      case 0x8Eu:
        v416 = *((int *)i + 1);
        v417 = v2[15];
        v668 = 0;
        v418 = *(_QWORD *)(v417 + 8 * v416);
        Table = sqlite3VdbeCursorRestore(v418, v7, v13);
        updated = Table;
        if ( Table )
          goto LABEL_309;
        if ( *(_BYTE *)(v418 + 2) )
        {
LABEL_290:
          IsValidNN = sqlite3VdbeMemSetNull(v6 + 56LL * *((int *)i + 2));
        }
        else
        {
          v668 = 0;
          Table = sqlite3VdbeIdxRowid(v5, *(_QWORD *)(v418 + 48), &v668);
          updated = Table;
          if ( Table )
            goto LABEL_309;
          if ( *i == 0x8D )
          {
            v420 = *(_QWORD *)(v2[15] + 8LL * *((int *)i + 3));
            *(_BYTE *)(v420 + 2) = 0;
            *(_QWORD *)(v420 + 80) = v668;
            *(_BYTE *)(v420 + 3) = 1;
            *(_DWORD *)(v420 + 32) = 0;
            IsValidNN = *((_QWORD *)i + 2);
            *(_QWORD *)(v420 + 16) = IsValidNN;
            *(_QWORD *)(v420 + 40) = v418;
          }
          else
          {
            IsValidNN = out2Prerelease(v2, i, v419);
            *(_QWORD *)IsValidNN = v668;
          }
        }
        goto LABEL_27;
      case 0x8Fu:
        IsValidNN = v2[15];
        v421 = *(_QWORD *)(IsValidNN + 8LL * *((int *)i + 1));
        if ( !*(_BYTE *)(v421 + 3) )
          goto LABEL_108;
        IsValidNN = sqlite3VdbeFinishMoveto(v421, v7, v13);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( !(_DWORD)IsValidNN )
          goto LABEL_27;
        goto LABEL_309;
      case 0x90u:
        LODWORD(v669) = 0;
        v431 = out2Prerelease(v2, i, v13);
        *(_WORD *)(v431 + 20) = 1;
        if ( *(_DWORD *)(v5 + 220) > *(_DWORD *)(v5 + 232) + 1 )
        {
          updated = 6;
          *((_BYTE *)v2 + 196) = 2;
          goto LABEL_309;
        }
        v432 = *((_DWORD *)i + 3);
        v433 = *(_QWORD *)(v5 + 32);
        v434 = *((unsigned int *)i + 1);
        LODWORD(v669) = 0;
        updated = sqlite3BtreeDropTable(*(_QWORD *)(32LL * (int)v432 + v433 + 8), v434, &v669);
        Table = updated;
        *(_WORD *)(v431 + 20) = 4;
        IsValidNN = (int)v669;
        *(_QWORD *)v431 = (int)v669;
        if ( updated )
          goto LABEL_309;
        if ( (_DWORD)v669 )
        {
          sqlite3RootPageMoved(v5, v432, (unsigned int)v669, *((unsigned int *)i + 1));
          IsValidNN = v432 + 1;
          HIBYTE(v660) = v432 + 1;
        }
        goto LABEL_48;
      case 0x91u:
        v435 = *(_QWORD *)(v5 + 32);
        v436 = *((unsigned int *)i + 1);
        v437 = 32LL * *((int *)i + 2);
        v668 = 0;
        IsValidNN = sqlite3BtreeClearTable(*(_QWORD *)(v437 + v435 + 8), v436, &v668);
        updated = IsValidNN;
        Table = IsValidNN;
        if ( *((_DWORD *)i + 3) )
        {
          v438 = v668;
          v2[7] += v668;
          IsValidNN = *((int *)i + 3);
          if ( (int)IsValidNN > 0 )
            *(_QWORD *)(56 * IsValidNN + v6) += v438;
        }
        if ( !updated )
          goto LABEL_27;
        goto LABEL_309;
      case 0x92u:
        v439 = *(_QWORD *)(v2[15] + 8LL * *((int *)i + 1));
        if ( *(_BYTE *)v439 == 1 )
        {
          IsValidNN = sqlite3VdbeSorterReset(v5, *(_QWORD *)(v439 + 48), v13);
        }
        else
        {
          IsValidNN = sqlite3BtreeClearTable(
                        *(_QWORD *)(*(_QWORD *)(v439 + 48) + 8LL),
                        *(unsigned int *)(*(_QWORD *)(v439 + 48) + 80LL),
                        0);
          Table = IsValidNN;
          updated = IsValidNN;
          if ( (_DWORD)IsValidNN )
            goto LABEL_309;
        }
        goto LABEL_27;
      case 0x93u:
        LODWORD(v669) = 0;
        v440 = out2Prerelease(v2, i, v13);
        v441 = *(_QWORD *)(v5 + 32);
        v442 = (_QWORD *)v440;
        v443 = *((unsigned int *)i + 3);
        v444 = 32LL * *((int *)i + 1);
        LODWORD(v669) = 0;
        IsValidNN = sqlite3BtreeCreateTable(*(_QWORD *)(v444 + v441 + 8), &v669, v443);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( (_DWORD)IsValidNN )
          goto LABEL_309;
        *v442 = (unsigned int)v669;
        goto LABEL_27;
      case 0x94u:
        ++*(_BYTE *)(v5 + 112);
        v37 = (i[4] & 1) == 0;
        v445 = *(_QWORD *)(v5 + 512);
        v446 = *(_BYTE *)(v5 + 110);
        v447 = *(_DWORD *)(v5 + 744);
        v668 = 0;
        if ( !v37 )
        {
          *(_QWORD *)(v5 + 512) = 0;
          *(_BYTE *)(v5 + 110) = 0;
        }
        if ( (i[4] & 2) != 0 )
          *(_DWORD *)(v5 + 744) = *((_DWORD *)i + 2);
        IsValidNN = sqlite3_exec(v5, *((_QWORD *)i + 2), 0, 0, (__int64)&v668);
        v448 = (const char *)v668;
        updated = IsValidNN;
        --*(_BYTE *)(v5 + 112);
        Table = IsValidNN;
        *(_QWORD *)(v5 + 512) = v445;
        *(_BYTE *)(v5 + 110) = v446;
        *(_DWORD *)(v5 + 744) = v447;
        if ( !v448 && !(_DWORD)IsValidNN )
          goto LABEL_48;
        sqlite3VdbeError(v2, "%s", v448);
        sqlite3_free(v668);
        if ( updated == 7 )
          goto LABEL_90;
        goto LABEL_309;
      case 0x95u:
        v449 = *((_QWORD *)i + 2);
        v450 = *((int *)i + 1);
        v1 = 0;
        *(_QWORD *)&v676 = 0;
        v674 = 0;
        v675 = 0;
        if ( v449 )
        {
          v451 = *(_QWORD *)(v5 + 32);
          *(_QWORD *)&v674 = v5;
          LODWORD(v675) = v450;
          *((_QWORD *)&v674 + 1) = v2 + 21;
          DWORD2(v675) = 0;
          LODWORD(v676) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(32 * v450 + v451 + 8) + 8LL) + 64LL);
          v452 = sqlite3MPrintf(
                   v5,
                   "SELECT*FROM\"%w\".%s WHERE %s ORDER BY rowid",
                   *(_QWORD *)(32 * v450 + v451),
                   "sqlite_master",
                   v449);
          v453 = v452;
          if ( !v452 )
          {
            sqlite3ResetAllSchemasOfConnection(v5);
            goto LABEL_90;
          }
          *(_BYTE *)(v5 + 197) = 1;
          DWORD1(v675) = 0;
          HIDWORD(v675) = 0;
          Table = sqlite3_exec(v5, v452, (unsigned int)sqlite3InitCallback, (unsigned int)&v674, 0);
          updated = Table;
          if ( !Table )
          {
            updated = DWORD1(v675);
            Table = DWORD1(v675);
            if ( !DWORD1(v675) && !HIDWORD(v675) )
            {
              updated = sqlite3ReportError(11, 100154, "database corruption");
              Table = updated;
            }
          }
          IsValidNN = sqlite3DbFreeNN(v5, v453);
          *(_BYTE *)(v5 + 197) = 0;
        }
        else
        {
          sqlite3SchemaClear(*(_QWORD *)(32 * v450 + *(_QWORD *)(v5 + 32) + 24), v7, v13);
          *(_DWORD *)(v5 + 44) &= ~0x10u;
          IsValidNN = sqlite3InitOne(v5, (unsigned int)v450, v2 + 21, *((unsigned __int16 *)i + 1));
          *(_DWORD *)(v5 + 44) |= 1u;
          updated = IsValidNN;
          *((_DWORD *)v2 + 50) &= 0xFFFFFFFC;
          Table = IsValidNN;
        }
        if ( updated )
        {
          sqlite3ResetAllSchemasOfConnection(v5);
          if ( updated != 7 )
            goto LABEL_309;
          goto LABEL_90;
        }
        goto LABEL_27;
      case 0x96u:
        IsValidNN = sqlite3AnalysisLoad(v5, *((unsigned int *)i + 1), v13);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( !(_DWORD)IsValidNN )
          goto LABEL_27;
        goto LABEL_309;
      case 0x97u:
        IsValidNN = sqlite3UnlinkAndDeleteTable(v5, *((unsigned int *)i + 1), *((_QWORD *)i + 2));
        goto LABEL_27;
      case 0x98u:
        IsValidNN = sqlite3UnlinkAndDeleteIndex(v5, *((unsigned int *)i + 1), *((_QWORD *)i + 2));
        goto LABEL_27;
      case 0x99u:
        v27 = out2Prerelease(v2, i, v13);
        *(_WORD *)(v27 + 20) = 8;
        IsValidNN = *((_QWORD *)i + 2);
        *(_QWORD *)v27 = *(_QWORD *)IsValidNN;
        goto LABEL_27;
      case 0x9Au:
        IsValidNN = sqlite3UnlinkAndDeleteTrigger(v5, *((unsigned int *)i + 1), *((_QWORD *)i + 2));
        goto LABEL_27;
      case 0x9Bu:
        v454 = *((int *)i + 1);
        v455 = *((_QWORD *)i + 2);
        LODWORD(v672) = 0;
        v668 = 0;
        v456 = 56 * v454;
        v457 = v6 + 56LL * ((int)v454 + 1);
        Table = sqlite3BtreeIntegrityCheck(
                  v5,
                  *(_QWORD *)(32LL * *((unsigned __int16 *)i + 1) + *(_QWORD *)(v5 + 32) + 8),
                  (int)v455 + 4,
                  (int)v6 + 56 * *((_DWORD *)i + 3),
                  *((_DWORD *)i + 2),
                  *(_DWORD *)(56 * v454 + v6) + 1,
                  (__int64)&v672,
                  (__int64)&v668);
        updated = Table;
        sqlite3VdbeMemSetNull(v457);
        if ( !(_DWORD)v672 )
          goto LABEL_878;
        if ( Table )
          goto LABEL_1199;
        LOBYTE(v459) = 1;
        *(_QWORD *)(v456 + v6) -= (int)v672 - 1;
        sqlite3VdbeMemSetStr(v457, v668, -1, v459, sqlite3_free);
LABEL_878:
        sqlite3VdbeChangeEncoding(v457, (unsigned __int8)v660, v458);
LABEL_879:
        v3 = v666;
        goto LABEL_880;
      case 0x9Cu:
        v461 = *((int *)i + 1);
        v462 = *((int *)i + 2);
        v463 = v6 + 56 * v461;
        if ( (*(_BYTE *)(v463 + 20) & 0x10) == 0 && (unsigned int)sqlite3VdbeMemSetRowSet(v6 + 56 * v461, v7, v13) )
          goto LABEL_90;
        IsValidNN = sqlite3RowSetInsert(*(_QWORD *)(v463 + 8), *(_QWORD *)(56 * v462 + v6), v13);
        goto LABEL_48;
      case 0x9Du:
        v485 = out2Prerelease(v2, i, v13);
        IsValidNN = sqlite3VdbeMemShallowCopy(
                      v485,
                      *(_QWORD *)(v2[33] + 24)
                    + 56LL
                    * (*((_DWORD *)i + 1) + *(_DWORD *)(*(_QWORD *)(v2[33] + 16) + 24LL * *(int *)(v2[33] + 76) + 4)),
                      0x4000);
        goto LABEL_27;
      case 0x9Eu:
        IsValidNN = *((int *)i + 2);
        if ( (*(_DWORD *)(v5 + 48) & 0x80000) != 0 )
        {
          *(_QWORD *)(v5 + 768) += IsValidNN;
        }
        else if ( *((_DWORD *)i + 1) )
        {
          *(_QWORD *)(v5 + 760) += IsValidNN;
        }
        else
        {
          v2[10] += IsValidNN;
        }
        goto LABEL_108;
      case 0x9Fu:
        v486 = v2[33];
        if ( v486 )
        {
          for ( ; *(_QWORD *)(v486 + 8); v486 = *(_QWORD *)(v486 + 8) )
            ;
          v487 = *(_QWORD *)(v486 + 24) + 56LL * *((int *)i + 1);
        }
        else
        {
          v487 = v6 + 56LL * *((int *)i + 1);
        }
        *(_QWORD *)v487 = sqlite3VdbeIntValue(v487, v7, v13);
        *(_WORD *)(v487 + 20) &= 0xF244u;
        *(_WORD *)(v487 + 20) |= 4u;
        v488 = v6 + 56LL * *((int *)i + 2);
        IsValidNN = sqlite3VdbeIntValue(v488, v489, v490);
        *(_WORD *)(v488 + 20) &= 0xF244u;
        *(_WORD *)(v488 + 20) |= 4u;
        v7 = v664;
        v13 = v661;
        v8 = v660;
        *(_QWORD *)v488 = IsValidNN;
        if ( *(_QWORD *)v487 < IsValidNN )
          *(_QWORD *)v487 = IsValidNN;
        v3 = v666;
        goto LABEL_108;
      case 0xA0u:
        v492 = *((int *)i + 3);
        v493 = 56LL * *((int *)i + 1);
        v668 = 0;
        v494 = (__int64 *)out2Prerelease(v2, i, v13);
        IsValidNN = v673;
        v668 = *(_QWORD *)(v493 + v673);
        if ( v668 <= 0 )
          goto LABEL_943;
        v495 = *(_QWORD *)(56 * v492 + v673);
        if ( v495 <= 0 )
          v495 = 0;
        IsValidNN = sqlite3AddInt64(&v668, v495);
        if ( (_DWORD)IsValidNN )
        {
LABEL_943:
          *v494 = -1;
        }
        else
        {
          IsValidNN = v668;
          *v494 = v668;
        }
        goto LABEL_48;
      case 0xA1u:
      case 0xA2u:
        v498 = *((unsigned __int16 *)i + 1);
        v499 = sqlite3DbMallocRawNN(v5, 8 * v498 + 104);
        if ( !v499 )
          goto LABEL_90;
        *(_QWORD *)(v499 + 16) = 0;
        *(_QWORD *)v499 = v499 + 8 * (v498 + 6);
        *(_WORD *)(v499 + 8 * v498 + 68) = 1;
        *(_QWORD *)(v499 + 8 * v498 + 72) = v5;
        *(_DWORD *)(v499 + 8 * v498 + 80) = 0;
        *(_QWORD *)(v499 + 8) = *((_QWORD *)i + 2);
        *(_BYTE *)(v499 + 42) = v498;
        v3 = v666;
        *(_QWORD *)(v499 + 24) = v2;
        *(_DWORD *)(v499 + 32) = -1431655765 * ((i - v666) >> 3);
        *(_BYTE *)(v499 + 40) = v660;
        *(_BYTE *)(v499 + 41) = 0;
        *(_DWORD *)(v499 + 36) = 0;
        *(_WORD *)i = -3677;
        *((_QWORD *)i + 2) = v499;
        goto LABEL_952;
      case 0xA3u:
LABEL_952:
        v500 = (_DWORD *)*((_QWORD *)i + 2);
        v501 = v6 + 56LL * *((int *)i + 3);
        if ( *((_QWORD *)v500 + 2) != v501 )
        {
          v502 = (unsigned int)*((unsigned __int8 *)v500 + 42) - 1;
          for ( *((_QWORD *)v500 + 2) = v501; (int)v502 >= 0; v502 = (unsigned int)(v502 - 1) )
            *(_QWORD *)&v500[2 * v502 + 12] = v6 + 56LL * ((int)v502 + *((_DWORD *)i + 2));
        }
        ++*(_DWORD *)(v501 + 16);
        v503 = v500 + 12;
        v504 = *((_QWORD *)v500 + 1);
        v505 = *((unsigned __int8 *)v500 + 42);
        if ( *((_DWORD *)i + 1) )
          (*(void (__fastcall **)(_DWORD *, __int64, _DWORD *))(v504 + 48))(v500, v505, v503);
        else
          (*(void (__fastcall **)(_DWORD *, __int64, _DWORD *))(v504 + 24))(v500, v505, v503);
        IsValidNN = (unsigned int)v500[9];
        if ( !(_DWORD)IsValidNN )
          goto LABEL_27;
        if ( (int)IsValidNN > 0 )
        {
          LOBYTE(v506) = 1;
          v508 = (const char *)sqlite3ValueText(*(_QWORD *)v500, v506);
          sqlite3VdbeError(v2, "%s", v508);
          updated = v500[9];
          Table = updated;
        }
        if ( *((_BYTE *)v500 + 41) )
        {
          v509 = *((int *)i - 5);
          if ( (_DWORD)v509 )
            sqlite3VdbeMemSetInt64(v6 + 56 * v509, 1, v507);
          *((_BYTE *)v500 + 41) = 0;
        }
        sqlite3VdbeMemRelease(*(_QWORD *)v500);
        IsValidNN = *(_QWORD *)v500;
        *(_WORD *)(*(_QWORD *)v500 + 20LL) = 1;
        v500[9] = 0;
        if ( updated )
          goto LABEL_309;
        v7 = v664;
        goto LABEL_28;
      case 0xA4u:
      case 0xA5u:
        v510 = *((int *)i + 3);
        v511 = v6 + 56LL * *((int *)i + 1);
        if ( (_DWORD)v510 )
        {
          updated = sqlite3VdbeMemAggValue(v6 + 56LL * *((int *)i + 1), v6 + 56 * v510, *((_QWORD *)i + 2));
          Table = updated;
          v511 = v6 + 56LL * *((int *)i + 3);
        }
        else
        {
          updated = sqlite3VdbeMemFinalize(v6 + 56LL * *((int *)i + 1), *((_QWORD *)i + 2), v13);
          Table = updated;
        }
        if ( updated )
        {
          LOBYTE(v512) = 1;
          v648 = (const char *)sqlite3ValueText(v511, v512);
          sqlite3VdbeError(v2, "%s", v648);
          goto LABEL_309;
        }
        IsValidNN = sqlite3VdbeChangeEncoding(v511, (unsigned __int8)v660, v513);
        goto LABEL_27;
      case 0xA6u:
        if ( !*((_DWORD *)i + 1) )
        {
          IsValidNN = sqlite3ExpirePreparedStatements(v5, *((unsigned int *)i + 2), v13);
          goto LABEL_27;
        }
        IsValidNN = *((unsigned int *)v2 + 50);
        *((_DWORD *)v2 + 50) = IsValidNN ^ ((unsigned __int8)IsValidNN ^ (unsigned __int8)(*((_DWORD *)i + 2) + 1)) & 3;
        goto LABEL_108;
      case 0xA7u:
        IsValidNN = *(_QWORD *)(*(_QWORD *)(v2[15] + 8LL * *((int *)i + 1)) + 48LL);
        *(_BYTE *)(IsValidNN + 1) |= 0x40u;
        goto LABEL_108;
      case 0xA8u:
        IsValidNN = *(_QWORD *)(*(_QWORD *)(v2[15] + 8LL * *((int *)i + 1)) + 48LL);
        *(_BYTE *)(IsValidNN + 1) &= ~0x40u;
        goto LABEL_108;
      case 0xA9u:
        if ( !i[12] )
        {
          IsValidNN = 0x400000000LL;
          if ( (*(_QWORD *)(v5 + 48) & 0x400000000LL) != 0 )
            goto LABEL_58;
        }
        IsValidNN = sqlite3BtreeLockTable(
                      *(_QWORD *)(32LL * *((int *)i + 1) + *(_QWORD *)(v5 + 32) + 8),
                      *((unsigned int *)i + 2));
        Table = IsValidNN;
        updated = IsValidNN;
        if ( !(_DWORD)IsValidNN )
          goto LABEL_27;
        if ( (_BYTE)IsValidNN == 6 )
          sqlite3VdbeError(v2, "database table is locked: %s", *((const char **)i + 2));
        goto LABEL_309;
      case 0xAAu:
        v538 = *((_QWORD *)i + 2);
        IsValidNN = sqlite3VtabBegin(v5, v538, v13);
        Table = IsValidNN;
        updated = IsValidNN;
        if ( v538 )
          IsValidNN = sqlite3VtabImportErrmsg(v2, *(_QWORD *)(v538 + 16));
        if ( !updated )
          goto LABEL_27;
        goto LABEL_309;
      case 0xABu:
        *((_QWORD *)&v681[1] + 1) = v5;
        memset(v681, 0, 24);
        v683 = 0;
        v1 = 0;
        v539 = *((int *)i + 2);
        v682 = 0;
        v540 = sqlite3VdbeMemCopy(v681, v6 + 56 * v539, v13);
        LOBYTE(v541) = 1;
        Table = v540;
        updated = v540;
        v542 = sqlite3ValueText(v681, v541);
        if ( v542 )
        {
          updated = sqlite3VtabCallCreate(v5, *((unsigned int *)i + 1), v542, v2 + 21);
          Table = updated;
        }
        IsValidNN = sqlite3VdbeMemRelease(v681);
        if ( !updated )
          goto LABEL_27;
        goto LABEL_309;
      case 0xACu:
        ++*(_DWORD *)(v5 + 232);
        IsValidNN = sqlite3VtabCallDestroy(v5, *((unsigned int *)i + 1), *((_QWORD *)i + 2));
        --*(_DWORD *)(v5 + 232);
        updated = IsValidNN;
        Table = IsValidNN;
        if ( !(_DWORD)IsValidNN )
          goto LABEL_27;
        goto LABEL_309;
      case 0xADu:
        v543 = *((_QWORD *)i + 2);
        v668 = 0;
        v544 = *(__int64 **)(v543 + 16);
        if ( !v544 || (v545 = *v544) == 0 )
        {
LABEL_1206:
          updated = 6;
          goto LABEL_309;
        }
        Table = (*(__int64 (__fastcall **)(__int64 *, __int64 *, __int64))(v545 + 48))(v544, &v668, v13);
        updated = Table;
        sqlite3VtabImportErrmsg(v2, v544);
        if ( Table )
          goto LABEL_309;
        LOBYTE(v546) = 2;
        *(_QWORD *)v668 = v544;
        IsValidNN = allocateCursor(v2, *((unsigned int *)i + 1), 0, v546);
        if ( !IsValidNN )
        {
          (*(void (__fastcall **)(__int64))(v545 + 56))(v668);
          goto LABEL_90;
        }
        *(_QWORD *)(IsValidNN + 48) = v668;
        ++*((_DWORD *)v544 + 2);
        goto LABEL_48;
      case 0xAEu:
        v547 = *((int *)i + 2);
        v668 = 0;
        v548 = v6 + 56 * v547;
        IsValidNN = sqlite3VdbeMemSetNull(v548);
        v549 = (_QWORD *)*((_QWORD *)i + 2);
        v550 = v549[10];
        if ( !v550 )
          goto LABEL_48;
        v551 = *(__int64 **)(v550 + 16);
        v552 = *v551;
        ++*(_DWORD *)(v550 + 24);
        updated = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, __int64 *))(v552 + 192))(
                    v551,
                    *(_QWORD *)(32LL * *((int *)i + 1) + *(_QWORD *)(v5 + 32)),
                    *v549,
                    *((unsigned int *)i + 3),
                    &v668);
        Table = updated;
        IsValidNN = sqlite3VtabUnlock(v549[10]);
        if ( updated )
        {
LABEL_1199:
          sqlite3_free(v668);
          goto LABEL_309;
        }
        if ( v668 )
        {
          LOBYTE(v553) = 1;
          IsValidNN = sqlite3VdbeMemSetStr(v548, v668, -1, v553, sqlite3_free);
        }
        goto LABEL_48;
      case 0xAFu:
        v554 = *(_QWORD *)(v2[15] + 8LL * *((int *)i + 1));
        v555 = (_QWORD *)sqlite3_malloc64(16, v7, v13);
        v557 = v555;
        if ( !v555 )
          goto LABEL_90;
        *v555 = *(_QWORD *)(v554 + 48);
        v555[1] = v6 + 56LL * *((int *)i + 3);
        v558 = out2Prerelease(v2, i, v556);
        *(_WORD *)(v558 + 20) = 1;
        IsValidNN = sqlite3VdbeMemSetPointer(v558, v557, "ValueList", sqlite3VdbeValueListFree);
        goto LABEL_48;
      case 0xB0u:
        v1 = 0;
        v690 = 0;
        memset(v688, 0, sizeof(v688));
        v692 = 0;
        v693 = 0;
        v689 = 0;
        memset_0(&v691, 0, 0x45u);
        v570 = *(_QWORD *)(v2[15] + 8LL * *((int *)i + 1));
        v571 = *((int *)i + 3);
        v572 = v6 + 56 * v571;
        if ( *(_BYTE *)(v570 + 2) )
        {
          IsValidNN = sqlite3VdbeMemSetNull(v6 + 56 * v571);
        }
        else
        {
          v37 = (i[2] & 1) == 0;
          v573 = **(__int64 ***)(v570 + 48);
          v574 = *v573;
          BYTE8(v689) = v660;
          *((_QWORD *)&v688[0] + 1) = &v691;
          *(_QWORD *)&v688[0] = v572;
          v694 = 0x1000000;
          if ( v37 )
          {
            v575 = *(_WORD *)(v572 + 20) & 0xF240 | 1;
          }
          else
          {
            sqlite3VdbeMemSetNull(v572);
            v575 = 1025;
            *(_DWORD *)v572 = 0;
          }
          *(_WORD *)(v572 + 20) = v575;
          Table = (*(__int64 (__fastcall **)(_QWORD, _OWORD *, _QWORD))(v574 + 88))(
                    *(_QWORD *)(v570 + 48),
                    v688,
                    *((unsigned int *)i + 2));
          updated = Table;
          sqlite3VtabImportErrmsg(v2, v573);
          if ( SDWORD1(v689) > 0 )
          {
            LOBYTE(v576) = 1;
            v578 = (const char *)sqlite3ValueText(v572, v576);
            sqlite3VdbeError(v2, "%s", v578);
            updated = DWORD1(v689);
            Table = DWORD1(v689);
          }
          IsValidNN = sqlite3VdbeChangeEncoding(v572, (unsigned __int8)v660, v577);
          if ( updated )
            goto LABEL_309;
        }
        goto LABEL_48;
      case 0xB1u:
        v583 = *(_DWORD *)(v5 + 48);
        *(_QWORD *)(v5 + 48) |= 0x4000000uLL;
        v584 = *(_QWORD *)(*((_QWORD *)i + 2) + 16LL);
        v585 = v673 + 56LL * *((int *)i + 1);
        updated = sqlite3VdbeChangeEncoding(v585, 1, v13);
        if ( updated )
          goto LABEL_309;
        Table = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v584 + 152LL))(v584, *(_QWORD *)(v585 + 8));
        updated = Table;
        if ( (v583 & 0x4000000) == 0 )
          *(_QWORD *)(v5 + 48) &= ~0x4000000uLL;
        IsValidNN = sqlite3VtabImportErrmsg(v2, v584);
LABEL_575:
        *((_DWORD *)v2 + 50) &= 0xFFFFFFFC;
        goto LABEL_576;
      case 0xB2u:
        IsValidNN = out2Prerelease(v2, i, v13);
        *(_QWORD *)IsValidNN = *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(32LL * *((int *)i + 1)
                                                                       + *(_QWORD *)(v5 + 32)
                                                                       + 8)
                                                           + 8LL)
                                               + 64LL);
        goto LABEL_27;
      case 0xB3u:
        v593 = (_QWORD *)out2Prerelease(v2, i, v13);
        v594 = *((_DWORD *)i + 3);
        v595 = *(_QWORD *)(32LL * *((int *)i + 1) + *(_QWORD *)(v5 + 32) + 8);
        v596 = 0;
        if ( v594 )
        {
          v596 = *(unsigned int *)(*(_QWORD *)(v595 + 8) + 64LL);
          if ( (unsigned int)v596 < v594 )
            v596 = v594;
        }
        IsValidNN = (unsigned int)sqlite3BtreeMaxPageCount(v595, v596);
        *v593 = (unsigned int)IsValidNN;
        goto LABEL_27;
      case 0xB4u:
        IsValidNN = 63487;
        *(_WORD *)(56LL * *((int *)i + 1) + v6 + 20) &= ~0x800u;
        goto LABEL_108;
      case 0xB5u:
        v602 = 56LL * *((int *)i + 1);
        v138 = v6 + 56LL * *((int *)i + 2);
        if ( (*(_WORD *)(v602 + v6 + 20) & 0x800) == 0 )
          goto LABEL_261;
        IsValidNN = sqlite3VdbeMemSetInt64(v138, *(unsigned __int8 *)(v602 + v6 + 23), v13);
        goto LABEL_27;
      case 0xB6u:
        v603 = 56LL * *((int *)i + 1);
        v604 = 56LL * *((int *)i + 2);
        if ( (*(_BYTE *)(v603 + v6 + 20) & 1) != 0 )
        {
          v7 = v664;
          IsValidNN = 63487;
          *(_WORD *)(v604 + v6 + 20) &= ~0x800u;
        }
        else
        {
          *(_WORD *)(v604 + v6 + 20) |= 0x800u;
          IsValidNN = *(unsigned __int8 *)(v603 + v6);
          v7 = v664;
          *(_BYTE *)(v604 + v6 + 23) = IsValidNN;
        }
        goto LABEL_108;
      case 0xB7u:
        v605 = 56LL * *((int *)i + 1);
        v606 = filterHash(v6, i, v13);
        v607 = *(_QWORD *)(v605 + v6 + 8);
        v608 = (v606 % (8 * *(_DWORD *)(v605 + v6 + 16))) & 7;
        v609 = (v606 % (8 * *(_DWORD *)(v605 + v6 + 16))) >> 3;
        IsValidNN = (unsigned int)*(char *)(v609 + v607);
        LODWORD(IsValidNN) = IsValidNN | (1 << v608);
        *(_BYTE *)(v609 + v607) = IsValidNN;
        goto LABEL_27;
      default:
        IsValidNN = v15;
        goto LABEL_108;
    }
  }
  *((_DWORD *)v2 + 11) = (*((_DWORD *)v2 + 11) + 2) | 1;
  v2[20] = v6 + 56LL * *((int *)i + 1);
  if ( *(_BYTE *)(v5 + 103) )
    goto LABEL_90;
  if ( (*(_BYTE *)(v5 + 110) & 4) != 0 )
  {
    (*(void (__fastcall **)(__int64, _QWORD, __int64 *, _QWORD))(v5 + 248))(4, *(_QWORD *)(v5 + 256), v2, 0);
    v7 = v664;
  }
  v56 = HIBYTE(v660);
  v654 = i - v3;
  v55 = v665;
  updated = 100;
  *((_DWORD *)v2 + 12) = -1431655765 * (v654 >> 3) + 1;
LABEL_1258:
  while ( v7 >= v55 )
  {
    v656 = *(__int64 (__fastcall **)(_QWORD))(v5 + 528);
    if ( !v656 )
      break;
    v55 += *(unsigned int *)(v5 + 544);
    v657 = v656(*(_QWORD *)(v5 + 536));
    v7 = v664;
    if ( v657 )
    {
      v55 = -1;
      updated = 9;
LABEL_311:
      if ( *(_BYTE *)(v5 + 103) )
      {
        updated = 7;
      }
      else if ( updated == 8458 )
      {
        updated = sqlite3ReportError(11, 102186, "database corruption");
      }
      if ( !v2[21] && updated != 3082 )
      {
        v655 = (const char *)sqlite3ErrStr(updated);
        sqlite3VdbeError(v2, "%s", v655);
      }
      *((_DWORD *)v2 + 13) = updated;
      sqlite3SystemError(v5, updated);
      sqlite3_log(
        updated,
        "statement aborts at %d: [%s] %s",
        -1431655765 * ((i - v666) >> 3),
        (const char *)v2[31],
        (const char *)v2[21]);
      if ( *((_BYTE *)v2 + 199) == 2 )
        sqlite3VdbeHalt(v2);
      if ( updated == 3082 )
      {
        sqlite3OomFault(v5);
      }
      else if ( updated == 11 && !*(_BYTE *)(v5 + 101) )
      {
        *(_QWORD *)(v5 + 48) |= 0x200000000uLL;
      }
      updated = 1;
      if ( v56 )
        sqlite3ResetOneSchema(v5);
LABEL_1257:
      v7 = v664;
    }
  }
  *((_DWORD *)v2 + 57) += v7;
  if ( *((_DWORD *)v2 + 52) )
    sqlite3VdbeLeave(v2);
  return updated;
}

```

## disassembly

```asm
0x180021aa0  mov     r11, rsp
0x180021aa3  push    rbp
0x180021aa4  push    r12
0x180021aa6  lea     rbp, [r11-158h]
0x180021aad  sub     rsp, 248h
0x180021ab4  mov     rax, cs:__security_cookie
0x180021abb  xor     rax, rsp
0x180021abe  mov     [rbp+150h+var_60], rax
0x180021ac5  mov     [r11+18h], rsi
0x180021ac9  mov     r12, rcx
0x180021acc  mov     rsi, [rcx+88h]
0x180021ad3  mov     [r11+20h], rdi
0x180021ad7  mov     rdi, rsi
0x180021ada  mov     [r11-18h], r13
0x180021ade  mov     r13, [rcx]
0x180021ae1  mov     [r11-20h], r14
0x180021ae5  mov     r14, [r12+68h]
0x180021aea  mov     [rsp+250h+var_1E8], rcx
0x180021aef  xor     ecx, ecx
0x180021af1  mov     edx, ecx
0x180021af3  movzx   r11d, byte ptr [r13+64h]
0x180021af8  mov     byte ptr [rsp+250h+var_210], r11b
0x180021afd  mov     [rsp+250h+var_1F0], rsi
0x180021b02  mov     [rbp+150h+var_1D0], r13
0x180021b06  mov     byte ptr [rsp+250h+var_210+1], 0
0x180021b0b  mov     [rsp+250h+var_200], rcx
0x180021b10  mov     [rbp+150h+var_1B8], r14
0x180021b14  cmp     [r12+0D0h], ecx
0x180021b1c  jz      short loc_180021B33
0x180021b1e  mov     rcx, r12
0x180021b21  call    sqlite3VdbeEnter
0x180021b26  mov     rdx, [rsp+250h+var_200]
0x180021b2b  xor     ecx, ecx
0x180021b2d  movzx   r11d, byte ptr [rsp+250h+var_210]
0x180021b33  cmp     qword ptr [r13+210h], 0
0x180021b3b  jz      short loc_180021B5E
0x180021b3d  mov     ecx, [r13+220h]
0x180021b44  xor     edx, edx
0x180021b46  mov     eax, [r12+0E4h]
0x180021b4e  div     ecx
0x180021b50  sub     ecx, edx
0x180021b52  mov     rdx, [rsp+250h+var_200]
0x180021b57  mov     r9d, ecx
0x180021b5a  xor     ecx, ecx
0x180021b5c  jmp     short loc_180021B65
0x180021b5e  mov     r9, 0FFFFFFFFFFFFFFFFh
0x180021b65  cmp     dword ptr [r12+34h], 7
0x180021b6b  mov     [rsp+250h+arg_8], rbx
0x180021b73  mov     [rsp+250h+var_20], r15
0x180021b7b  movaps  [rsp+250h+var_38+8], xmm6
0x180021b83  movaps  [rsp+250h+var_48+8], xmm7
0x180021b8b  movaps  [rsp+250h+var_58+8], xmm8
0x180021b94  mov     [rsp+250h+var_1F8], r9
0x180021b99  jz      loc_1800222D3
0x180021b9f  mov     [r12+34h], ecx
0x180021ba4  mov     [r12+48h], rcx
0x180021ba9  mov     eax, [r13+198h]
0x180021bb0  mov     [r13+298h], ecx
0x180021bb7  test    eax, eax
0x180021bb9  jnz     loc_1800278C6
0x180021bbf  movsxd  rax, dword ptr [r12+30h]
0x180021bc4  mov     r15d, ecx
0x180021bc7  mov     dword ptr [rsp+250h+var_208], ecx
0x180021bcb  mov     r8d, ecx
0x180021bce  mov     [rsp+44h], ecx
0x180021bd2  mov     r10d, 1
0x180021bd8  mov     [rbp+150h+var_180], ecx
0x180021bdb  xorps   xmm8, xmm8
0x180021bdf  lea     rcx, [rax+rax*2]
0x180021be3  lea     rdi, [rsi+rcx*8]
0x180021be7  lea     rcx, __ImageBase
0x180021bee  xchg    ax, ax
0x180021bf0  movzx   ebx, byte ptr [rdi]
0x180021bf3  inc     rdx
0x180021bf6  mov     [rsp+250h+var_200], rdx
0x180021bfb  cmp     ebx, 71h ; 'q'
0x180021bfe  jz      loc_1800271E6; jumptable 0000000180021C36 case 112
0x180021c04  cmp     ebx, 76h ; 'v'
0x180021c07  jz      loc_180027041; jumptable 0000000180021C36 case 116
0x180021c0d  cmp     ebx, 54h ; 'T'
0x180021c10  jz      loc_18002781B
0x180021c16  cmp     ebx, 0B8h; switch 185 cases
0x180021c1c  ja      def_180021C36; jumptable 0000000180021C36 default case
0x180021c22  movsxd  rax, ebx
0x180021c25  mov     ecx, ds:(jpt_180021C36 - 180000000h)[rcx+rax*4]
0x180021c2c  lea     rax, __ImageBase
0x180021c33  add     rcx, rax
0x180021c36  jmp     rcx; switch jump
0x180021c38  movsxd  rax, dword ptr [rdi+4]; jumptable 0000000180021C36 case 10
0x180021c3c  mov     r8, 0AAAAAAAAAAAAAAABh
0x180021c46  imul    rcx, rax, 38h ; '8'
0x180021c4a  mov     rax, rdi
0x180021c4d  sub     rax, rsi
0x180021c50  sar     rax, 3
0x180021c54  imul    rax, r8
0x180021c58  mov     word ptr [rcx+r14+14h], 4
0x180021c60  cdqe
0x180021c62  mov     [rcx+r14], rax
0x180021c66  jmp     loc_180026B14; jumptable 0000000180021C36 case 9
0x180021c6b  movsxd  rax, dword ptr [rdi+4]; jumptable 0000000180021C36 case 67
0x180021c6f  imul    rax, 38h ; '8'
0x180021c73  test    byte ptr [rax+r14+14h], 4
0x180021c79  jz      loc_18002240A; jumptable 0000000180021C36 cases 84,89,93,113,118,123
0x180021c7f  mov     rax, [rax+r14]
0x180021c83  lea     rcx, [rax+rax*2]
0x180021c87  lea     rdi, [rsi+rcx*8]
0x180021c8b  jmp     loc_18002240A; jumptable 0000000180021C36 cases 84,89,93,113,118,123
0x180021c90  movsxd  rax, dword ptr [rdi+4]; jumptable 0000000180021C36 case 11
0x180021c94  imul    rcx, rax, 38h ; '8'
0x180021c98  mov     eax, [rdi+0Ch]
0x180021c9b  dec     eax
0x180021c9d  cdqe
0x180021c9f  mov     [rcx+r14], rax
0x180021ca3  mov     word ptr [rcx+r14+14h], 4
0x180021cab  cmp     dword ptr [rdi+8], 0
0x180021caf  jz      loc_18002240A; jumptable 0000000180021C36 cases 84,89,93,113,118,123
0x180021cb5  jmp     loc_180022C89
0x180021cba  movsxd  rax, dword ptr [rdi+4]; jumptable 0000000180021C36 case 68
0x180021cbe  sub     rdi, [r12+88h]
0x180021cc6  imul    rdx, rax, 38h ; '8'
0x180021cca  sar     rdi, 3
0x180021cce  mov     rax, [rdx+r14]
0x180021cd2  lea     rcx, [rax+rax*2]
0x180021cd6  mov     rax, 0AAAAAAAAAAAAAAABh
0x180021ce0  imul    rax, rdi
0x180021ce4  dec     eax
0x180021ce6  cdqe
0x180021ce8  mov     [rdx+r14], rax
0x180021cec  mov     eax, [rsi+rcx*8+8]
0x180021cf0  dec     eax
0x180021cf2  cdqe
0x180021cf4  lea     rcx, [rax+rax*2]
0x180021cf8  lea     rdi, [rsi+rcx*8]
0x180021cfc  mov     rdx, [rsp+250h+var_200]
0x180021d01  jmp     loc_18002240A; jumptable 0000000180021C36 cases 84,89,93,113,118,123
0x180021d06  movsxd  rax, dword ptr [rdi+4]; jumptable 0000000180021C36 case 12
0x180021d0a  sub     rdi, rsi
0x180021d0d  imul    rdx, rax, 38h ; '8'
0x180021d11  sar     rdi, 3
0x180021d15  mov     rax, 0AAAAAAAAAAAAAAABh
0x180021d1f  imul    rax, rdi
0x180021d23  movsxd  rcx, dword ptr [rdx+r14]
0x180021d27  cdqe
0x180021d29  mov     word ptr [rdx+r14+14h], 4
0x180021d31  mov     [rdx+r14], rax
0x180021d35  mov     rdx, [rsp+250h+var_200]
0x180021d3a  lea     rcx, [rcx+rcx*2]
0x180021d3e  lea     rdi, [rsi+rcx*8]
0x180021d42  jmp     loc_18002240A; jumptable 0000000180021C36 cases 84,89,93,113,118,123
0x180021d47  movsxd  rax, dword ptr [rdi+0Ch]; jumptable 0000000180021C36 case 69
0x180021d4b  imul    rcx, rax, 38h ; '8'
0x180021d4f  test    byte ptr [rcx+r14+14h], 1
0x180021d55  jz      loc_18002240A; jumptable 0000000180021C36 cases 84,89,93,113,118,123
0x180021d5b  mov     rcx, [r12+108h]; jumptable 0000000180021C36 case 70
0x180021d63  test    rcx, rcx
0x180021d66  jz      loc_18002734C
0x180021d6c  cmp     dword ptr [rdi+4], 0
0x180021d70  jnz     loc_18002734C
0x180021d76  mov     rax, [rcx+8]
0x180021d7a  dec     dword ptr [r12+118h]
0x180021d82  mov     [r12+108h], rax
0x180021d8a  mov     rax, [r12+38h]
0x180021d8f  add     [r13+80h], rax
0x180021d96  mov     [r13+78h], rax
0x180021d9a  call    sqlite3VdbeFrameRestore
0x180021d9f  cmp     dword ptr [rdi+8], 4
0x180021da3  jnz     short loc_180021DB9
0x180021da5  cdqe
0x180021da7  lea     rcx, [rax+rax*2]
0x180021dab  mov     rax, [r12+88h]
0x180021db3  mov     eax, [rax+rcx*8+8]
0x180021db7  dec     eax
0x180021db9  mov     rsi, [r12+88h]
0x180021dc1  mov     rcx, [r12+68h]
0x180021dc6  cdqe
0x180021dc8  mov     [rbp+150h+var_1B8], rcx
0x180021dcc  mov     [rsp+250h+var_1F0], rsi
0x180021dd1  lea     rcx, [rax+rax*2]
0x180021dd5  lea     rdi, [rsi+rcx*8]
0x180021dd9  mov     rdx, [rsp+250h+var_200]
0x180021dde  mov     r10d, 1
0x180021de4  mov     r8d, [rsp+44h]
0x180021de9  movzx   r11d, byte ptr [rsp+250h+var_210]
0x180021def  jmp     loc_18002240A; jumptable 0000000180021C36 cases 84,89,93,113,118,123
0x180021df4  mov     rdx, rdi; jumptable 0000000180021C36 case 71
0x180021df7  mov     rcx, r12
0x180021dfa  call    out2Prerelease
0x180021dff  mov     rcx, rax
0x180021e02  movsxd  rax, dword ptr [rdi+4]
0x180021e06  mov     [rcx], rax
0x180021e09  jmp     short loc_180021DD9
0x180021e0b  mov     rdx, rdi; jumptable 0000000180021C36 case 72
0x180021e0e  mov     rcx, r12
0x180021e11  call    out2Prerelease
0x180021e16  mov     rdx, rax
0x180021e19  mov     rax, [rdi+10h]
0x180021e1d  mov     rcx, [rax]
0x180021e20  mov     [rdx], rcx
0x180021e23  jmp     short loc_180021DD9
0x180021e25  mov     rdx, rdi; jumptable 0000000180021C36 case 153
0x180021e28  mov     rcx, r12
0x180021e2b  call    out2Prerelease
0x180021e30  mov     rdx, rax
0x180021e33  mov     word ptr [rax+14h], 8
0x180021e39  mov     rax, [rdi+10h]
0x180021e3d  mov     rcx, [rax]
0x180021e40  mov     [rdx], rcx
0x180021e43  jmp     short loc_180021DD9
0x180021e45  mov     rdx, rdi; jumptable 0000000180021C36 case 117
0x180021e48  mov     rcx, r12
0x180021e4b  call    out2Prerelease
0x180021e50  mov     rcx, [rdi+10h]
0x180021e54  mov     rbx, rax
0x180021e57  call    sqlite3Strlen30
0x180021e5c  cmp     byte ptr [rsp+250h+var_210], 1
0x180021e61  mov     [rdi+4], eax
0x180021e64  jz      short loc_180021ED9
0x180021e66  mov     rdx, [rdi+10h]
0x180021e6a  mov     r9b, 1
0x180021e6d  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180021e74  mov     [rsp+250h+var_230], 0
0x180021e7d  mov     rcx, rbx
0x180021e80  call    sqlite3VdbeMemSetStr
0x180021e85  mov     dword ptr [rsp+250h+var_208], eax
0x180021e89  mov     r15d, eax
0x180021e8c  test    eax, eax
0x180021e8e  jnz     loc_1800275E5
0x180021e94  movzx   edx, byte ptr [rsp+250h+var_210]
0x180021e99  mov     rcx, rbx
0x180021e9c  call    sqlite3VdbeChangeEncoding
0x180021ea1  test    eax, eax
0x180021ea3  jnz     loc_1800222D3
0x180021ea9  mov     [rbx+20h], eax
0x180021eac  mov     eax, 2000h
0x180021eb1  or      [rbx+14h], ax
0x180021eb5  cmp     byte ptr [rdi+1], 0FAh
0x180021eb9  jnz     short loc_180021EC7
0x180021ebb  mov     rdx, [rdi+10h]
0x180021ebf  mov     rcx, r13
0x180021ec2  call    sqlite3DbFree
0x180021ec7  mov     byte ptr [rdi+1], 0FAh
0x180021ecb  mov     rax, [rbx+8]
0x180021ecf  mov     [rdi+10h], rax
0x180021ed3  mov     eax, [rbx+10h]
0x180021ed6  mov     [rdi+4], eax
0x180021ed9  cmp     eax, [r13+88h]
0x180021ee0  jg      loc_1800275E5
0x180021ee6  mov     byte ptr [rdi], 49h ; 'I'
0x180021ee9  mov     rdx, rdi; jumptable 0000000180021C36 case 73
0x180021eec  mov     rcx, r12
0x180021eef  call    out2Prerelease
0x180021ef4  movzx   r11d, byte ptr [rsp+250h+var_210]
0x180021efa  mov     r8, rax
0x180021efd  mov     word ptr [rax+14h], 2202h
0x180021f03  mov     rcx, [rdi+10h]
0x180021f07  mov     [rax+8], rcx
0x180021f0b  mov     ecx, [rdi+4]
0x180021f0e  mov     [rax+10h], ecx
0x180021f11  mov     [rax+16h], r11b
0x180021f15  movsxd  rax, dword ptr [rdi+0Ch]
0x180021f19  test    eax, eax
0x180021f1b  jle     loc_180022039
0x180021f21  imul    rdx, rax, 38h ; '8'
0x180021f25  movzx   eax, word ptr [rdi+2]
0x180021f29  lea     rcx, __ImageBase
0x180021f30  mov     r10d, 1
0x180021f36  cmp     [rdx+r14], rax
0x180021f3a  mov     rdx, [rsp+250h+var_200]
0x180021f3f  jnz     short loc_180021F48
0x180021f41  mov     word ptr [r8+14h], 2210h
0x180021f48  mov     r8d, [rsp+44h]
0x180021f4d  jmp     def_180021C36; jumptable 0000000180021C36 default case
0x180021f52  mov     rdx, rdi; jumptable 0000000180021C36 cases 74,75
0x180021f55  mov     rcx, r12
0x180021f58  call    out2Prerelease
0x180021f5d  mov     ebx, [rdi+0Ch]
0x180021f60  mov     esi, 101h
0x180021f65  sub     ebx, [rdi+8]
0x180021f68  mov     r10d, 1
0x180021f6e  cmp     dword ptr [rdi+4], 0
0x180021f72  mov     r14, rax
0x180021f75  cmovz   si, r10w
0x180021f7a  xor     r13d, r13d
0x180021f7d  mov     [rax+14h], si
0x180021f81  mov     [rax+10h], r13d
0x180021f85  test    ebx, ebx
0x180021f87  jle     loc_18002213C
0x180021f8d  add     r14, 38h ; '8'
0x180021f91  mov     rcx, r14
0x180021f94  call    sqlite3VdbeMemSetNull
0x180021f99  dec     ebx
0x180021f9b  mov     [r14+14h], si
0x180021fa0  mov     [r14+10h], r13d
0x180021fa4  test    ebx, ebx
0x180021fa6  jg      short loc_180021F8D
0x180021fa8  mov     rdx, [rsp+250h+var_200]
0x180021fad  mov     r10d, 1
0x180021fb3  mov     r8d, [rsp+44h]
0x180021fb8  mov     rsi, [rsp+250h+var_1F0]
0x180021fbd  movzx   r11d, byte ptr [rsp+250h+var_210]
  ... truncated ...
```
